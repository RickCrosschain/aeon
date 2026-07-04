Heartbeat complete. `HEARTBEAT_OK · STATUS_PAGE=DEGRADED`

## Summary

Ran the heartbeat skill for the 2026-07-04 08:00 slot (executed 09:37 UTC).

**Checks:**
- **P0 — Failed/stuck skills:** `heartbeat` lifetime success rate is 44% (43/97), tripping the chronic-failure flag — but `consecutive_failures: 0`, `last_status: success`, and last success was ~13.5h ago (self-check >36h does not fire). This is the known intermittent gateway-exit / zero-token detection bug, already tracked by **ISS-001** (open, critical). No stuck/dispatched skills; no ≥3 consecutive failures. Other skills (autoresearch, strategy-builder, soul-builder) all ✅.
- **P1:** No open PRs, no open issues.
- **P2:** MEMORY.md priorities are known onboarding items, nothing new.
- **P3:** Only heartbeat is enabled; dispatching on schedule. No missing skills.

**Overall status:** 🔴 DEGRADED (chronic-failure P0 fires).

**Actions:**
- **No notification sent** — ISS-001 / heartbeat degradation is already in recent logs and was notified 2026-06-19, well within the 48h dedup window. Nothing new to report.
- **Regenerated `docs/status.md`** → DEGRADED, 1 open issue, 4-skill health table, next run 14:00 UTC. Token pulse omitted (no `articles/token-report-*.md` exists).

**Files modified:**
- `docs/status.md` — refreshed public status page
- `memory/logs/2026-07-04.md` — created with today's run log

**Follow-up:** ISS-001 remains open and unresolved — heartbeat's fleet-health metrics stay unreliable until the gateway exit-code / zero-token detection bug is repaired. This has now recurred daily for ~2 weeks; worth prioritizing skill-repair on the underlying detection logic.
