Heartbeat complete.

## Summary

Ran the **heartbeat** skill (20:00 slot, 2026-07-29 22:05 UTC).

**Findings by tier:**
- **P0 — DEGRADED:** `heartbeat`'s own prior dispatch is recorded as `last_status: failed` (`consecutive_failures: 2`, `last_error` = truncated gateway `modelUsage` JSON). This is the exact **ISS-001** signature — the gateway exit-code / zero-token success-detection bug that flags heartbeat as failed even when the run completes normally. The failed-skill P0 flag fires → overall 🔴 DEGRADED. Other P0 conditions stay cleared: cf 2 < 3 (no API-degradation), success_rate 108/210 = 51% ≥ 50% (no chronic), last_success ~6.6h ago (self-check OK), dispatch within 45min (not stuck).
- **P1:** No open PRs, no open/urgent GitHub issues.
- **P2/P3:** Nothing new in MEMORY.md; only `heartbeat` enabled and dispatching on schedule — no missing skills.

**Actions:**
- **No notification sent** — the failed skill is heartbeat itself = ISS-001 (open critical, already notified 2026-07-09, in every log within the 48h dedup window). Recurring known artifact, nothing genuinely broken → dedup skip.
- Regenerated `docs/status.md` → 🔴 DEGRADED, 1 open issue, heartbeat row ❌ failed / 51% / cf 2, next run 2026-07-30 08:00 UTC. Token pulse omitted (no token report file).
- Appended log entry to `memory/logs/2026-07-29.md`.

**Files modified:** `docs/status.md`, `memory/logs/2026-07-29.md`.

**Follow-up:** ISS-001 (critical) remains open and unrepaired — the gateway success-detection bug keeps corrupting fleet-health metrics and now flips the public status page red. A repair skill (skill-repair) needs to address the gateway exit-code handling to clear it.

STATUS_PAGE=DEGRADED — wrote docs/status.md
