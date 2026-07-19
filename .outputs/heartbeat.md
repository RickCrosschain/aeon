Heartbeat complete for the 20:00 UTC slot.

## Summary

Ran the heartbeat skill (20:00 UTC slot, 2026-07-19). All priority checks executed against `cron-state.json`, `aeon.yml`, `issues/INDEX.md`, and GitHub.

**Findings:**
- **P0** — Only the **chronic-failure** flag fires: heartbeat lifetime `success_rate` 0.44 (78/178). This is the ongoing **ISS-001** gateway exit-code / zero-token success-detection bug. `consecutive_failures: 0`, `last_success` ~6h ago — API-degradation and >36h self-check flags stay cleared. No failed or stuck skills.
- **P1** — No open PRs, no urgent issues.
- **P2/P3** — Nothing new in MEMORY.md; only heartbeat is enabled and it's dispatching on schedule. No missing skills.

**Overall: 🔴 DEGRADED** (P0 chronic-failure), unchanged since 07-09.

**Actions:**
- **No notification** — ISS-001 already notified 07-09 and continuously logged; condition unchanged, within 48h dedup.
- Regenerated `docs/status.md` (DEGRADED, 1 open issue, next run 2026-07-20 08:00 UTC; token pulse omitted — no token-report article).
- Logged to `memory/logs/2026-07-19.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-07-19.md`

HEARTBEAT_OK · STATUS_PAGE=DEGRADED (chronic-failure only; no new conditions)
