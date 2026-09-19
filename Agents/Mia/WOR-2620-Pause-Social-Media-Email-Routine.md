# WOR-2620 — Decision: Pause Social Media Email Check Routine

**Date:** 2026-09-19
**Decider:** [[Mia]] (Marketing Specialist — Marketing owner + Dan's manager per [[Agents/Dan/Initial-Task-Brief|Dan's Task Brief]])
**Status:** ✅ Complete — routine paused 2026-09-19T18:30:38Z, verified by Mia via API (WOR-2621 done)

## Decision

**Pause the "Dan: Social Media Email Check" routine (ID 7dc5e516-f438-4887-b71a-34f64e8ab4bf) now.** Do not archive — archiving is terminal and cannot be undone; pausing is reversible.

## Evidence (from WOR-2619, verified 2026-09-19)

- `social-media@workforce365.ai` is **not an alias** on the Gmail account — sendAs API shows only johnw@workforce365.ai
- Gmail label "social-media" (Label_6) has 0 messages ever (messagesTotal: 0)
- Search `to:social-media@workforce365.ai in:anywhere` (incl. spam/trash) → 0 results
- Both available OAuth tokens (main + Sue profile) authenticate as johnw@workforce365.ai
- Cost: 73 routine run issues on 2026-09-19 alone (~96/day), each closing "done — no messages found"

## Rationale

1. John's WOR-1674 order (15-min check) was premised on the alias existing — false
2. CLEAN SLATE (WOR-1769, Sep 14) halted all non-calculator/social-media work — the routine outlived its directive
3. Pure waste with zero possible output
4. Reversible: pause, don't archive

## Execution path

- Dan owns the routine; agents can only manage routines assigned to themselves → authorization issued via standalone task [[WOR-2621 — Pause Routine Task]] (WOR-2621), assigned to Dan
- WOR-2620 blocked on WOR-2621 → Mia auto-woken on completion to verify
- Dan also closes orphaned routine instances (e.g. WOR-1964)

## Reactivation criteria (all three required)

1. `social-media@workforce365.ai` alias actually exists (Google Workspace admin action — **John only**)
2. Social media work resumes post-CLEAN-SLATE
3. Explicit authorization from Mia

## Related

- [[WOR-1668 — Social Media Presence]] (in_review) — blocked by the same alias gap; alias is a registration prerequisite
- [[Social-Media-Audit-2026-09-14]] — context: no active social presence exists yet
- [[Agents/Dan/Initial-Task-Brief|Dan's Task Brief]] — source of the false "emails arrive in John's Gmail" assumption
MD
