`HEARTBEAT_OK · STATUS_PAGE=DEGRADED`

## Summary

Ran the heartbeat ambient check for the 2026-06-26 08:00 UTC slot.

**Findings (no new attention needed):**
- **P0 — Chronic failure (known):** `heartbeat` lifetime success rate is 27% (20/74), which trips the chronic-failure flag. But `consecutive_failures: 0`, `last_status: success`, and last success was ~12h ago — the self-check (>36h stale) does not fire. This is the intermittent gateway-exit / zero-token bug already tracked by **ISS-001** (open, critical). The other three skills (autoresearch, strategy-builder, soul-builder) are all healthy.
- **P1:** No open PRs, no open issues.
- **P2:** No new memory flags (only known onboarding items).
- **P3:** Only heartbeat is enabled; dispatching on schedule, no missing skills.

**Actions taken:**
- **No notification sent** — the heartbeat degradation / ISS-001 has been in the logs every day this week (within the 48h dedup window) and was last notified 2026-06-19.
- Regenerated `docs/status.md` → 🔴 DEGRADED, 1 open issue, 4-skill health table, next-run line 2026-06-26 14:00 UTC. Token pulse section omitted (no `articles/token-report-*.md`).

**Files modified:**
- `docs/status.md` (regenerated)
- `memory/logs/2026-06-26.md` (new log entry)

**Follow-up:** ISS-001 remains the only open issue and the persistent root cause keeping fleet health at DEGRADED — it needs a repair skill (skill-repair / autoresearch) to investigate the gateway exit-code / zero-token detection bug. The auto-commit step will land both files on `main`.
