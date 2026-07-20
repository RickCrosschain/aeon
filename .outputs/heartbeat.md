Heartbeat complete. `HEARTBEAT_OK` conditions apply to notification (nothing new to surface), but overall fleet status is `STATUS_PAGE=DEGRADED`.

## Summary

Ran the **heartbeat** skill for the 2026-07-20 20:00 slot (executed 21:08 UTC).

**Findings (all priority tiers):**
- **P0:** Only the chronic-failure flag fires — `heartbeat` lifetime `success_rate` is 45% (81/181), the long-standing **ISS-001** gateway exit-code / zero-token success-detection bug. `consecutive_failures: 0`, last success ~6.4h ago, so API-degradation and >36h self-check flags stay cleared. No failed/stuck skills; other skills (autoresearch, strategy-builder, soul-builder) all ✅.
- **P1:** No open PRs, no open GitHub issues.
- **P2:** MEMORY.md — nothing new flagged.
- **P3:** Only heartbeat is on a cron schedule and it's dispatching on time; no missing scheduled skills.

**Actions:**
- **No notification sent** — ISS-001 is unchanged and already notified/logged continuously, well within the 48h dedup window.
- Regenerated `docs/status.md` → 🔴 DEGRADED, 1 open issue, heartbeat row ✅ 45% / cf 0, next-run line 2026-07-21 08:00 UTC. Token pulse section omitted (no `articles/token-report-*.md` exists).

**Files modified:**
- `docs/status.md` — regenerated public status page
- `memory/logs/2026-07-20.md` — appended 21:08 UTC run log

**Follow-up needed:** ISS-001 remains the one open item — the intermittent success-detection bug keeps lifetime success rate under 50% and holds fleet status at DEGRADED. A repair skill (skill-repair) targeting the gateway exit-code / zero-token handling is the path to close it; it stays flagged but doesn't warrant a repeat notification.
