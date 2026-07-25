Heartbeat complete. All priority checks ran; no new attention items, so no notification was sent (dedup on ISS-001), and the public status page was regenerated.

## Summary

**Checks (all green except the known chronic-failure flag):**
- **P0** — No failed or stuck skills. `heartbeat` is currently healthy: `last_status: success`, `consecutive_failures: 0`, last success 2026-07-25 08:20 UTC (~6.7h ago). Self-check (<36h) and API-degradation flags cleared. The only firing condition is **chronic-failure**: lifetime `success_rate 0.49` (95/195) — the long-standing **ISS-001** gateway exit-code / zero-token success-detection bug. `autoresearch`, `strategy-builder`, `soul-builder` all ✅ (dispatch-only).
- **P1** — No open PRs, no urgent issues, no open GitHub issues.
- **P2** — MEMORY.md Next Priorities unchanged (known onboarding items).
- **P3** — Only `heartbeat` enabled; dispatching on schedule. No missing skills.

**Actions:**
- **No notification** — ISS-001 was escalated 07-09 and is continuously logged; condition unchanged (chronic-failure only, cf 0), well within the 48h dedup window. Nothing new or worse.
- Regenerated **`docs/status.md`** → 🔴 DEGRADED, 1 open issue, heartbeat 49% / cf 0, next run 2026-07-25 20:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- Appended log entry to **`memory/logs/2026-07-25.md`**.

**Files modified:** `docs/status.md`, `memory/logs/2026-07-25.md`

**Follow-up:** ISS-001 remains open (critical) — the underlying gateway success-detection bug keeps fleet metrics unreliable and holds overall status at DEGRADED. No repair skill is enabled to close it.

`HEARTBEAT_OK · STATUS_PAGE=DEGRADED`
