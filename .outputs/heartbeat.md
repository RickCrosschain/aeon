Heartbeat complete. `HEARTBEAT_OK · STATUS_PAGE=DEGRADED` (no new attention items — the one P0 flag is the already-tracked ISS-001, suppressed by dedup).

## Summary

Ran the **heartbeat** skill for the 2026-06-27 14:00 UTC slot.

**Checks:**
- **P0 — Failed/stuck skills:** `heartbeat` lifetime success_rate is 31% (24/78), tripping the chronic-failure flag — but `consecutive_failures: 0`, `last_status: success`, and `last_success` only ~4.5h ago (self-check >36h does *not* fire). This is the known intermittent gateway-exit / zero-token bug already tracked by **ISS-001** (open, critical). autoresearch / strategy-builder / soul-builder all ✅.
- **P1:** No open PRs, no open issues (`gh` both empty).
- **P2:** No new flagged memory items (MEMORY.md only holds known onboarding notes).
- **P3:** Only `heartbeat` is enabled in aeon.yml; dispatching on schedule. No missing skills.

**Overall: 🔴 DEGRADED** (chronic-failure P0 fires, driven entirely by ISS-001).

**Actions:**
- **No notification sent** — the ISS-001 / heartbeat degradation is in every daily log since 2026-06-22 and was notified 2026-06-19, well inside the 48h dedup window.
- Regenerated **`docs/status.md`** → DEGRADED, 1 open issue, 4-skill health table, next run 2026-06-27 20:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- Logged the run to **`memory/logs/2026-06-27.md`**.

**Files modified:** `docs/status.md`, `memory/logs/2026-06-27.md`

**Follow-up:** ISS-001 remains open — needs skill-repair to fix gateway success-detection (zero-token-but-valid result being treated as a failed gateway attempt). No new action from this run.
