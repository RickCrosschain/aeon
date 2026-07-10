HEARTBEAT_OK · STATUS_PAGE=DEGRADED

## Summary

Ran the heartbeat ambient check for 2026-07-10 08:00 slot.

**Findings (all priority tiers):**
- **P0** — Only `heartbeat` chronic-failure fires: lifetime success_rate 33% (49/149). The last three tracked runs succeeded, so `consecutive_failures: 0` and the API-degradation + >36h self-check flags stay cleared. Root cause is the known ISS-001 gateway exit-code / zero-token success-detection bug (still open).
- **P1** — No open PRs, no open GitHub issues.
- **P2/P3** — Nothing new flagged; only `heartbeat` enabled, dispatching on schedule.

**Notification:** None sent. The chronic-failure condition is unchanged from the 07-09 20:11 run, already notified 07-09 08:40 and continuously logged — well within the 48h dedup window. No new or worsened condition.

**Files modified:**
- `docs/status.md` — regenerated → 🔴 DEGRADED, 1 open issue, heartbeat ✅/33%/cf 0. Token pulse omitted (no `articles/token-report-*.md`).
- `memory/logs/2026-07-10.md` — created with the run's findings and actions.

**Follow-up needed:** ISS-001 still needs skill-repair on the gateway success-detection path — the intermittent zero-token failures keep lifetime success_rate below 50%, holding overall status at DEGRADED and making fleet health metrics unreliable.
