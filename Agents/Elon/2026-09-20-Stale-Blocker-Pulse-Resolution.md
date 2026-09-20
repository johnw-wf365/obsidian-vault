---
created: 2026-09-20
tags: [paperclip, incident, recovery, stale-blockers]
---

# Stale Blocker Pulse Incident — 2026-09-20 Resolution

Circuit breaker had been open since 2026-09-15 on [WOR-1712](https://wf365.workforce365.ai) (Leo's coordination issue). Manual review completed by Elon on 2026-09-20 (WOR-2643). Blocked issues: 8 → 3.

## Root causes discovered

1. **Cancelled queued runs without bootstrap evidence markers** (WOR-1703, run 1316e07f): a queued continuation run cancelled by the `stale_queued_run_gate` never started a provider, but its `result_json.executionRecovery` lacked `kind: "bootstrap"`. `legacyExecutionNeedsReconciliation()` therefore returns true on every periodic sweep → `terminalizeLegacyExecution` creates a fresh `active_run_watchdog` recovery action → settle sweep re-blocks the issue ~15-30s after any status change. **Any status other than terminal (done/cancelled) is unstable for such issues.** Fix applied: closed as done (honest — the umbrella's work was complete).

2. **Standing monitor issues have no valid in_progress state** (WOR-1712): Paperclip's disposition-repair escalates when a run completes on an `in_progress` issue with no durable waiting path (blocker / pending interaction / pending approval / scheduled monitor). Monitors are **one-shot** — they clear on trigger, they don't re-arm. A standing "watch the chain" issue will always bounce: run completes → missing_disposition escalation → blocked. Fix applied: resolved the recovery action twice (restored→todo), directed Leo to post a final summary and close as done. Coordination continues on-demand through chain issues.

3. **Lost wakes look like ignored directives** (WOR-1881): one of three `issue_commented` wakes for Sue failed ("Process lost -- server may have restarted"). The directive was never delivered. Lesson: before concluding an agent ignored a directive, check `agent_wakeup_requests.status` for the specific comment's wake.

## Resolution paths used

- `POST /api/issues/{id}/recovery-actions/resolve` with `{outcome: "restored", sourceIssueStatus: "todo"}` — safe hand-back to original owner. Requires: assignee still the returnOwnerAgentId, no conflicting checkout/execution run, no pending execution stage, no active pause hold, no project pause, no pending approvals.
- CEO authority: `requireRecoveryActionAuthority` allows the assignee, the recovery owner, or an agent with `tasks:manage_active_checkouts` override. As CEO I could resolve Leo's action only because the hand-back path (`safeHandBack`) skips the stricter source-mutation authority gate.

## Remaining blocked (legitimate)

WOR-1706, WOR-1710, WOR-1724 — all blocked on WOR-1730's `ask_user_questions` card (deployment prerequisites: GitHub, Vercel, domains, credentials) pending John since 2026-09-14. This is the real critical-path stall for the calculator launch. John must answer the card.

Also pending John: WOR-1844 Slack Pro trial decision (deadline 2026-09-22).

## Circuit file

`/opt/paperclip/data/pulse-circuit.json` — reset to `circuit_open: false`, schedule restored to `*/60 * * * *`.

Related: [[Paperclip-Recovery-Mechanics]]
