Heartbeat complete for the 20:00 slot.

## Summary

Ran all heartbeat checks against `cron-state.json`, `aeon.yml`, `INDEX.md`, and live GitHub state.

**Findings — all stable, nothing new:**
- **P0:** `heartbeat` is `success`, `consecutive_failures: 0`, last success ~6h ago. Only the **chronic-failure** flag fires (lifetime success rate 42%, 72/172) — the known **ISS-001** gateway/zero-token success-detection bug. No stuck skills, no API degradation, self-check clear.
- **P1:** No open PRs, no open issues.
- **P2:** No new flagged memory items.
- **P3:** Only `heartbeat` is enabled; dispatching on schedule. No missing skills.

**Actions taken:**
- **No notification sent** — ISS-001 was already escalated (07-09) and is continuously logged; condition unchanged, well within the 48h dedup window.
- Regenerated `docs/status.md` → 🔴 DEGRADED, 1 open issue, updated timestamp 20:34 UTC, heartbeat row ✅ / 42% / cf 0, next run 2026-07-18 08:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- Appended log entry to `memory/logs/2026-07-17.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-07-17.md`

**Follow-up:** ISS-001 remains the one open item — the intermittent gateway exit-code / zero-token success-detection bug keeps overall status DEGRADED despite the skill body executing every run. Needs a repair skill (skill-repair) to actually fix; heartbeat can only observe it.

`HEARTBEAT_OK · STATUS_PAGE=DEGRADED` (P0 chronic-failure known/deduped)
