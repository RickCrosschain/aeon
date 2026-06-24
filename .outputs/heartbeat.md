Heartbeat complete.

## Summary

Ran all heartbeat checks against `memory/cron-state.json`, `aeon.yml`, and the issue tracker.

**Findings:**
- **P0 — Chronic failure:** `heartbeat` lifetime success_rate is 22% (15/69) → chronic-failure flag fires (success_rate < 0.5, total_runs ≥ 5). However `consecutive_failures: 0`, `last_status: success`, `last_success: 2026-06-24 10:38 UTC` — its recent runs are all succeeding. Root cause is the intermittent gateway exit-code / zero-token detection bug, **already tracked by ISS-001 (open, critical)**. No new/stuck/degraded skills (autoresearch / strategy-builder / soul-builder all ✅).
- **P1:** No open PRs, no open issues (`gh` confirmed empty).
- **P2:** MEMORY.md Next Priorities are known onboarding items, nothing new.
- **P3:** Only heartbeat is enabled; dispatching on schedule. No missing skills.

**Overall: 🔴 DEGRADED** (chronic-failure P0 fires).

**Actions:**
- **No notification sent** — ISS-001 / heartbeat degradation is already in the 2026-06-21/22/23/24 logs and was notified 2026-06-19 (within the 48h dedup window).
- Regenerated `docs/status.md` → DEGRADED, 1 open issue, 4-skill health table, next run 2026-06-24 20:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- Appended log entry to `memory/logs/2026-06-24.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-06-24.md`.

**Follow-up:** ISS-001 remains open and unresolved — the gateway exit-code/zero-token detection bug needs skill-repair to investigate the workflow's success-detection logic. Heartbeat's lifetime metrics will stay unreliable until then.

`HEARTBEAT_OK · STATUS_PAGE=DEGRADED`
