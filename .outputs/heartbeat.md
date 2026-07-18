HEARTBEAT_OK · STATUS_PAGE=DEGRADED

## Summary

Ran the heartbeat skill for the 2026-07-18 08:00 slot. All priority checks came back clean except the known, already-tracked issue:

- **P0:** No failed or stuck skills. Only the **chronic-failure** flag fires on `heartbeat` itself — lifetime success_rate 0.42 (73/173) — which is **ISS-001** (gateway exit-code / zero-token success-detection bug). `consecutive_failures: 0`, last real failure 2026-07-09; recent runs all succeed, so API-degradation and >36h self-check flags stay cleared.
- **P1:** No open PRs, no urgent issues.
- **P2:** No new flagged memory items.
- **P3:** Only heartbeat is enabled; dispatching on schedule, no missing skills.

**Notification:** none sent — the sole finding is ISS-001, already notified and continuously logged, well within the 48h dedup window and unchanged.

**Files modified:**
- `docs/status.md` — regenerated: 🔴 DEGRADED, 1 open issue, heartbeat 42% / cf 0 / last run 2026-07-17 20:35 UTC, next run 2026-07-18 14:00 UTC. Token pulse omitted (no token-report file).
- `memory/logs/2026-07-18.md` — appended run log.

**Follow-up:** ISS-001 remains open — the DEGRADED status is driven entirely by the historical success-detection bug, not by any live skill failure. Repairing that gateway exit-code handling is the only thing that clears the board to 🟢 OK.
