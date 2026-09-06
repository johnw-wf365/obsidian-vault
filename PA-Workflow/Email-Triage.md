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

## Daily Triage Process

1. Scan inbox for new unread emails
2. Classify each email (P1-P4)
3. Apply appropriate label
4. Take autonomous action where pre-approved
5. Flag P1 items via Telegram DM
6. Queue P2 items for John's review
7. Log summary in [[PA-Workflow/Daily-Briefing]]
