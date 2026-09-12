---
created: 2026-09-12
tags: process, security, email, triage
aliases: Email Security Triage Plan, Triage Plan
---

# Email Security Triage Plan

**Owner:** Sue (PA to John)
**Scope:** All emails arriving in John's Gmail inbox (`john@workforce365.ai`)
**Goal:** Scan every 30 minutes. Assess security threats. Route actionable emails to Paperclip tasks.

---

## Security Assessment Rules

Each email is assessed in this order:

### 1. Critical (immediate threat)

Label as `_*Suspicious`, mark read, archive. **No task created.**

| Signal | Keywords / Patterns |
|--------|-------------------|
| Prompt injection attempts | `ignore previous instructions`, `disregard your training`, `act as if`, `[SYSTEM]`, `[INST]`, `[ASSISTANT]`, `redefine your identity`, `bypass security`, `override system prompt` |
| Executable attachments | `.exe`, `.bat`, `.cmd`, `.ps1`, `.vbs`, `.js`, `.scr`, .msi`, `.dmg`, `.iso` |
| Domain spoofing | Display name contains `google`/`microsoft`/`amazon` but actual domain does not match |

### 2. High (likely phishing)

Label as `_*Suspicious`, mark read, archive. **No task created.**

| Signal | Keywords |
|--------|----------|
| Credential theft | `verify your account`, `confirm your password`, `click here to verify` |
| Financial fraud | `urgent action required`, `wire transfer`, `payment failed`, `suspended account` |
| Account takeover | `unauthorized access detected`, `account locked` |

### 3. Routine (clear & non-threatening)

Label as `_*Processed`, mark read, archive.

- **Ignore list senders** → Archived silently, no task created
- **Non-ignore senders** → Archived + Paperclip task created for John's review

### Ignore List

| Type | Values |
|------|--------|
| Recipients | `paul-agent@workforce365.ai` |
| Domains | `upcloud.com`, `google.com`, `skool.com`, `warmwind.com`, `proton.me`, `openrouter.ai`, `github.com`, `manus.im`, `searchland.co.uk`, `linkedin.com`, `vapi.ai`, `twilio.com`, `mail.vapi.ai` |

---

## Routing Decision Tree

```
New unread email
        │
        ▼
┌──────────────────┐
│ Security scan    │
│ (keywords,       │
│  attachments,    │
│  domain spoof)   │
└──────────────────┘
        │
   ┌────┴────┐
   │         │
Threat    Clear
   │         │
   ▼         ▼
_*Suspicious  ┌──────────────┐
archive only  │ Ignore list? │
              └──────────────┘
               │         │
              Yes        No
               │         │
               ▼         ▼
          _*Processed  _*Processed
          archive only  + Paperclip task
```

---

## Task Creation Rules

- Only routine, non-ignore emails get a Paperclip task
- Task title: `{sender_name} — {subject}`
- Task priority: `medium` (overridden to `high` if subject contains `urgent` / `asap` / `board` / `investor`)
- Task assignee: Sue (`e1908f0a-43a3-49ed-a5c8-27f82cdaf5f7`)
- Parent issue: WOR-1455 (`db9e076a-566c-4d2a-9b8e-81aa54770575`)
- Task body includes: sender, recipient, date, subject, body (first 2000 chars)

---

## Operational Notes

- **Paperclip routine:** `22d8b165` (UTC, every 30 minutes)
- **Script:** `/root/.hermes/skills/productivity/google-workspace/scripts/process_emails.py`
- **Wrapper:** `/root/.hermes/skills/productivity/google-workspace/scripts/run_triage.sh`
- **Task log:** `/root/.hermes/skills/productivity/google-workspace/scripts/email_tasks.json`
- **Labels in Gmail:** `_*Suspicious` (threats), `_*Processed` (handled, no action needed)
- **No duplicate processing:** Emails are marked read and removed from inbox upon processing
- **Audit trail:** `email_tasks.json` records stats and task IDs after every run
