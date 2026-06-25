Heartbeat complete.

**HEARTBEAT_OK · STATUS_PAGE=DEGRADED**

## Summary

Ran the heartbeat priority checks for the 2026-06-25 08:00 UTC slot.

**Findings (all known / deduped — no notification sent):**
- **P0:** `heartbeat` lifetime success rate 24% (17/71) fires the chronic-failure flag, but `consecutive_failures: 0`, `last_status: success`, `last_success` ~12h ago (self-check does *not* fire). Intermittent gateway-exit / zero-token root cause already tracked by **ISS-001** (open, critical). All other skills (autoresearch, strategy-builder, soul-builder) healthy.
- **P1:** No open PRs, no open issues.
- **P2:** MEMORY.md flags are known onboarding items.
- **P3:** Only heartbeat enabled; dispatching on schedule. No missing skills.

**No notification** — ISS-001 / heartbeat degradation is within the 48h dedup window (logged 06-22/23/24, notified 06-19).

**Files modified:**
- `docs/status.md` — regenerated → 🔴 DEGRADED, 1 open issue, 4-skill health table, next run 2026-06-25 14:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- `memory/logs/2026-06-25.md` — created with this run's findings.

**Follow-up:** ISS-001 remains the only actionable item — the intermittent gateway exit-code / zero-token detection bug keeps heartbeat's lifetime success rate suppressed despite recent runs all succeeding. Needs the repair path (skill-repair / gateway fix), not another heartbeat cycle.
