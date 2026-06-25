Heartbeat complete. All checks ran; nothing new needs attention.

## Summary

Ran the **heartbeat** skill (20:00 UTC slot) — full check sweep against `cron-state.json`, `aeon.yml`, PRs, issues, and memory.

**Findings (overall: 🔴 DEGRADED):**
- **P0 — chronic failure:** `heartbeat` lifetime success_rate 26% (19/73) fires the chronic-failure flag. But `consecutive_failures: 0`, `last_status: success`, last success ~4h ago — the failure is the intermittent gateway-exit / zero-token bug already tracked by **ISS-001** (open, critical). Self-check (>36h stale) does not fire. Other three skills (autoresearch, strategy-builder, soul-builder) all ✅.
- **P1:** no open PRs, no open issues.
- **P2:** nothing new flagged in MEMORY.md.
- **P3:** only heartbeat enabled in `aeon.yml`; dispatching on schedule. No missing skills.

**Actions:**
- **No notification sent** — the only flagged item (ISS-001 / heartbeat degradation) is already in the last several days of logs and inside the 48h dedup window.
- Regenerated `docs/status.md` (🔴 DEGRADED, 1 open issue, 4-skill health table, next run 2026-06-26 08:00 UTC; token pulse omitted — no `articles/token-report-*.md`).
- Appended a log entry to `memory/logs/2026-06-25.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-06-25.md`

HEARTBEAT_OK · STATUS_PAGE=DEGRADED — no new actionable items (ISS-001 within dedup window).

No follow-up required beyond the existing open ISS-001, which needs a skill-repair pass to fix the gateway exit-code / zero-token detection bug at its root.
