Heartbeat complete.

## Summary

Ran the full heartbeat check for the 2026-06-27 08:00 slot (executed 09:37 UTC).

**Findings (all known, nothing new):**
- **P0 — chronic failure:** `heartbeat` lifetime success_rate is 30% (23/77), which trips the chronic-failure flag. But `consecutive_failures: 0`, `last_status: success`, and last success was ~12.7h ago — so this is the same intermittent gateway-exit / zero-token bug already tracked by **ISS-001** (open, critical), not a fresh regression. The other three skills (autoresearch, strategy-builder, soul-builder) are all ✅ at 100%.
- **P1:** No open PRs, no open issues.
- **P2:** No new flagged memory items.
- **P3:** Only `heartbeat` is enabled; it's dispatching on schedule. No missing skills.

**Actions:**
- **No notification sent** — heartbeat degradation / ISS-001 is in the last 5 days of logs and within the 48h dedup window.
- Regenerated `docs/status.md` → **🔴 DEGRADED**, 1 open issue, next run 14:00 UTC. Token pulse section omitted (no `articles/token-report-*.md` exists).
- Logged to `memory/logs/2026-06-27.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-06-27.md`

**Follow-up:** ISS-001 remains the standing open item — heartbeat's gateway exit-code / zero-token detection bug keeps its lifetime metrics unreliable. It needs a repair skill (skill-repair) to actually close it; the recent run-level successes are masking it but not fixing it.

`HEARTBEAT_OK · STATUS_PAGE=DEGRADED`
