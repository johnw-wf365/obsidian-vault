# Email Triage: Known Good Senders

**Last updated:** 2026-09-09T21:37:00Z
**Updated by:** Sue
**Source:** Aug 2026 spam false positives + manual additions

Senders who may be flagged by Gmail but are legitimate. Used during spam queue scanning to automate false-positive detection.

## Known Good

| Sender Domain | Example | Added |
|---|---|---|
| `slack.com` | no-reply@slack.com | 2026-09-09 |
| `tasklet.ai` | notifications@tasklet.ai, news@tasklet.ai | 2026-09-09 |
| `agents.tasklet.ai` | notifications@agents.tasklet.ai | 2026-09-09 |

## Decision Rules

During spam scan:
1. Extract sender domain from email
2. Check against known-good list above
3. If match → mark as **false positive** → rescue to inbox (remove SPAM, add INBOX, add `_*Processed`, remove UNREAD)
4. If no match → classify as:
   - Newsletter/promotion (subject/snippet contains "unsubscribe", "newsletter", "product update") → archive with `_*Processed` (keep in spam)
   - Unclassifiable → leave in spam, report to John

## How to Update

To add a sender: append to the Known Good table above with date and source.
To remove: mark as ~~strikethrough~~ with removal date and reason.

**Note:** This list lives in the Obsidian vault as the single source of truth. Heartbeat routines read from this file.
