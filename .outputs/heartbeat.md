Heartbeat complete.

## Summary

Ran all heartbeat checks (14:00 slot, executed 16:00 UTC on 2026-06-25). No new conditions — findings match the established pattern, so **no notification was sent** (deduped).

**Checks:**
- **P0 — Failed/stuck skills:** No failed or stuck skills. `heartbeat` lifetime success_rate is 25% (18/72) → chronic-failure flag fires, but `consecutive_failures: 0`, `last_status: success`, `last_success` ~7.5h ago (self-check not stale). Root cause is the intermittent gateway exit-code / zero-token detection bug, already tracked by **ISS-001** (open, critical). autoresearch / strategy-builder / soul-builder all ✅.
- **P1 — PRs/issues:** No open PRs, no open issues.
- **P2 — Memory flags:** MEMORY.md Next Priorities = known onboarding items, nothing new.
- **P3 — Missing skills:** Only `heartbeat` enabled; dispatching on schedule.

**Overall:** 🔴 DEGRADED (chronic-failure P0)

**Files modified:**
- `docs/status.md` — regenerated (🔴 DEGRADED, 1 open issue, 4 skills, next run 20:00 UTC; token pulse omitted, no token report exists)
- `memory/logs/2026-06-25.md` — appended 16:00 UTC entry

**Follow-up:** ISS-001 remains the only open lever — heartbeat's fleet-health metrics stay unreliable until the gateway exit-code / zero-token detection bug is repaired (skill-repair / autoresearch territory).

`HEARTBEAT_OK · STATUS_PAGE=DEGRADED`
