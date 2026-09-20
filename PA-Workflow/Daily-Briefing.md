# Daily Briefing

**Owner:** Sue (PA to Chairman)
**Last Updated:** 2026-09-06
**Cadence:** Daily, end of day (London time)

## Briefing Template

# Daily Briefing — 2026-09-09

## 📧 Email Summary
- **Unread:** 50 → 7 remaining in inbox
- **P1 Urgent:** 0
- **P2 Important:** 1 — UpCloud Accounts & Billing (4 emails, needs response)
- **Actioned autonomously:** 43 archived (P4 noise), 2 marked read (GitHub PAT, GWS invoice)

## 📅 Tomorrow's Calendar
- No events scheduled for Sep 10

## ⚡ Items Needing Your Attention
1. **UpCloud billing issue** — Invite sent to paul-agent@workforce365.ai but you're logged in as johnw@. Taylor confirmed email must match invite. Suggested action: log in with paul-agent@ or ask Taylor to resend invite to johnw@.

## 📝 Drafts Awaiting Approval
1. **Re: Accounts and Billing (UpCloud)** — "Thanks Taylor, please resend the invite to johnw@workforce365.ai — that's the account I use for billing."

## 🔮 Coming Up This Week
- No upcoming events on calendar

## 📊 Pattern Notes
- Heavy noise volume from LinkedIn (connection requests, job opportunities), Tailscale (product updates), Carbon Voice (promotions), and Proton (upsell). All archived.
- BuildUp emails properly labeled and archived per domain rules.
- GitHub PAT "paperclip=hermes-1" confirmed legitimate — marked read.

---

```markdown
# Daily Briefing — [Date]

## 📧 Email Summary
- **Unread:** [count]
- **P1 Urgent:** [count] — [brief list]
- **P2 Important:** [count] — [brief list]
- **Actioned autonomously:** [count]

## 📅 Tomorrow's Calendar
- [Time] — [Event] with [Who]
- [Time] — [Event] with [Who]
- **Deep work:** 06:00–09:00 (protected)

## ⚡ Items Needing Your Attention
1. [Item] — [Why it matters] — [Suggested action]
2. ...

## 📝 Drafts Awaiting Approval
1. [Email to X] — [Summary of draft]
2. ...

## 🔮 Coming Up This Week
- [Date] — [Event/Deadline]
- [Date] — [Event/Deadline]

## 📊 Pattern Notes
- [Observation about John's rhythm/preferences]
```

## Delivery

- **Channel:** Telegram DM to John (chat id `6473711033` — see `channel_directory.json`)
- **Timing:** 09:00 London (routine `bd3d0f65` fires the run)
- **Format:** Short bullets, conclusion first, emoji section markers, no markdown headers
- **Urgent items:** Flagged immediately, not held for daily briefing

### Telegram send procedure (verified working 2026-09-20)
```bash
cd /root/.hermes/profiles/sue
export $(grep -E "^TELEGRAM_BOT_TOKEN=" .env | head -1)
curl -sS -X POST "https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage" \
  -H "Content-Type: application/json" \
  -d "$(jq -n --arg chat_id "6473711033" --arg text "$MSG" '{chat_id:$chat_id, text:$text}')"
# Check response .ok == true and capture message_id as delivery proof
```
Never print or paste the token value anywhere. Also save the briefing to
`Agents/Sue/Daily-Briefings/YYYY-MM-DD.md` and post it as the run issue comment.

## Weekly Summary (Friday)

Additional to daily briefing:
- Week-in-review: decisions made, meetings held
- Next week preview: key events, prep needed
- Stakeholder matrix updates
- Expense/invoice reconciliation status
