# PA Workflow — Chairman's Office

**Owner:** Sue (PA to Chairman)
**Last Updated:** 2026-09-06
**Status:** Active

This folder contains the complete PA workflow for John Warnes, Chairman of WorkForce365.ai. It is the single source of truth for all administrative operations.

## Structure

| File | Purpose |
|------|---------|
| [[PA-Workflow/Email-Triage]] | Email triage rules, labels, and autonomous actions |
| [[PA-Workflow/Calendar-Management]] | Calendar rules, deep work blocks, scheduling |
| [[PA-Workflow/Stakeholder-Priority]] | Key people and prioritization matrix |
| [[PA-Workflow/Daily-Briefing]] | Daily summary template and cadence |
| [[PA-Workflow/Rhythm-Log]] | Learning John's patterns over time |

## John's Preferences (Confirmed 2026-09-06)

- **Email priorities:** Client/customer > Internal WF365 team > Board/Directors > Investor/VC
- **Autonomous actions:** Draft routine responses, Archive spam, Flag important/urgent, Create calendar invites (with confirmation), Send holding replies
- **Deep work hours:** 6:00–9:00 London time (DO NOT DISTURB)
- **Time zone:** London (GMT/BST)
- **Summary frequency:** Daily, end of day
- **Urgent items:** Telegram DM directly to John
- **Key people:** Learn from email patterns (ongoing)

## All Recurring Tasks (Paperclip Routines)

### PA Workflow — Daily Schedule (London Time)

| Time | Job | Paperclip Routine | What Happens |
|------|-----|------------------|-------------|
| 08:30 | Email Triage | `61b2096f` | Classify inbox P1-P4, act autonomously on P3/P4, flag P1 via Telegram |
| 08:45 | Calendar Monitor | `6dec5b02` | Scan next 48h, flag conflicts, prep for high-stakes meetings |
| 09:00 | Daily Briefing | `bd3d0f65` | End-of-day summary sent via Telegram DM |
| Fri 16:00 | Weekly Rhythm Review | `24fc15aa` | Pattern analysis, stakeholder matrix update, workflow refinements |

### System Maintenance

| Schedule | Job | Paperclip Routine | What Happens |
|----------|-----|------------------|-------------|
| Every 6h | Obsidian Vault Monitor | `1c998455` | Check vault for recent activity |
| Every 60m | Archive Noise Emails | `9bba4052` | Archive Carbon/Slack/Tailscale emails |

### Migration Note

All recurring tasks have been moved from Hermes cron jobs to Paperclip routines. The Hermes cron jobs are now **paused** and serve as backups only. Paperclip is the single source of truth for all scheduled work.

## Operating Principles

1. **Paperclip is the control plane** — all recurring tasks must be Paperclip routines, visible and manageable from the board
2. **Never mention Hermes backend details** to John — he only cares about what's in Paperclip
3. **Conclusion first** — Lead with the answer, then context if needed
4. **Proactive gatekeeping** — Filter noise, escalate only what matters
5. **Predictive execution** — Anticipate needs before they're stated
6. **Ironclad discretion** — All information stays in the Chairman's office
7. **No fragmented memory** — Everything documented in Obsidian, not scattered files
