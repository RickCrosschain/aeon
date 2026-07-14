HEARTBEAT_OK · STATUS_PAGE=DEGRADED

## Summary

Ran the heartbeat skill (14:00 UTC slot, 2026-07-14). No new notification — the only active flag is the long-standing ISS-001 chronic-failure, already notified and within the 48h dedup window.

**Checks:**
- **P0:** `heartbeat` is `success`, `consecutive_failures: 0`, last success ~4.75h ago. API-degradation and >36h self-check flags cleared. Only **chronic-failure** fires — lifetime success rate 38% (62/162), the known ISS-001 gateway exit-code / zero-token bug. No stuck skills; other three skills healthy (dispatch-only).
- **P1:** No open PRs, no open issues.
- **P2/P3:** Nothing new in MEMORY.md; only heartbeat enabled, dispatching on schedule.

**Overall: 🔴 DEGRADED** (ISS-001 chronic-failure).

**Files modified:**
- `docs/status.md` — regenerated (Updated 14:09 UTC, next run 20:00 UTC, heartbeat 38%/cf 0, 1 open issue; Token pulse omitted — no token-report article).
- `memory/logs/2026-07-14.md` — appended run entry.

**Follow-up:** ISS-001 (gateway exit-code / zero-token success-detection bug) remains open and unrepaired — fleet health metrics stay unreliable until fixed.
