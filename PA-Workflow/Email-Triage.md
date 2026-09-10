# Email Triage Rules

**Owner:** Sue (PA to Chairman)
**Last Updated:** 2026-09-06

## Priority Classification

### P1 — URGENT (Flag immediately, Telegram DM John)
- Client/customer issues or escalations
- Board/Director communications requiring response
- Investor/VC follow-ups with deadlines
- Legal or compliance matters
- Time-sensitive opportunities

### P2 — IMPORTANT (Draft response for John's review)
- Internal WF365 team decisions needed
- Meeting requests from key stakeholders
- Project updates requiring acknowledgment
- Partnership or vendor communications

### P3 — ROUTINE (Handle autonomously)
- Routine team updates → Draft holding reply
- Calendar invites from known contacts → Create with confirmation
- Newsletter/subscription content → Archive
- General inquiries → Route to appropriate team member

### P4 — NOISE (Archive/delete without action)
- Promotions and marketing spam
- LinkedIn notifications
- Slack digests (non-urgent)
- Automated system notifications

## Labeling Architecture

```
@Action Required    — Needs John's decision or response
@Awaiting Reply     — Waiting for external response
@Reading Pile       — Informational, read when convenient
@Drafted            — Response drafted, awaiting John's approval
@Delegated          — Routed to team member
@Archived           — No action needed, filed for reference
```

## Autonomous Actions (Pre-Approved)

| Action | Condition | Notes |
|--------|-----------|-------|
| Draft routine response | P3 emails only | Save as draft, never send without approval |
| Archive/delete spam | P4 classification | No notification needed |
| Flag important/urgent | P1 classification | Telegram DM to John immediately |
| Create calendar invite | Meeting request from known contact | With John's confirmation first |
| Send holding reply | P3 emails needing time | "John will respond by [date]" |

## Domain-Specific Rules

### BuildUp Emails
- **From:** `@skool.com`, `@buildup.com`, `@justbuildup.com`, BuildUp Bootcamp
- **Action:** Always apply Gmail label `BuildUp`
- **Classification:**
  - Event reminders, weekly digests, post notifications → P4 (NOISE → Archive after labeling)
  - Membership/account related → P2 (IMPORTANT — draft response for John)
  - General Q&A or community posts → P3 (ROUTINE → file for reference)
- **Age rule:** If email is over 14 days old → archive (remove from inbox, keep labeled)

### Paul-Agent Communications
- **From:** `paul-agent@workforce365.ai`, Carbon Voice notifications routed to Paul, UpCloud mentions of "Paul's connection unavailable"
- **Action:** Always apply Gmail label `paul-agent`, archive (remove from inbox), **keep marked as unread**
- **Classification:** All P3 (automated system alerts, health check notifications)

## Temporary Rule — BuildUp Email Monitor

- **From:** `hello@justbuildup.com`
- **Trigger:** Email arrives and is unread
- **Action:**
  1. Mark email as **read** (leave in inbox, do not archive)
  2. DM John Warnes on Telegram: *"New email from hello@justbuildup.com in your inbox. Do you still want this address monitored?"*
- **If John replies "no":** Remove this temporary rule from Email-Triage.md

## Transcription

- **Tool:** `whisper-transcribe` (local, no API keys needed)
- **Location:** `/opt/whisper.cpp/`, wrapper at `/usr/local/bin/whisper-transcribe`
- **Models:** tiny (75MB, fast), base (140MB), small (500MB), medium (1.5GB), large-v3 (3GB)
- **Supports:** mp4, mkv, mov, mp3, wav, flac, ogg, m4a, aac
- **Output formats:** text, srt, vtt, json, csv
- **Usage:** `whisper-transcribe <file> [model] [format]`

## Daily Triage Process

1. Scan inbox for new unread emails
2. Classify each email (P1-P4)
3. Apply appropriate label
4. **Apply domain-specific rules (above) where triggered**
5. Take autonomous action where pre-approved
6. Flag P1 items via Telegram DM
7. Queue P2 items for John's review
8. Log summary in [[PA-Workflow/Daily-Briefing]]
