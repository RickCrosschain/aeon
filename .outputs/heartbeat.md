Heartbeat complete. All checks ran; nothing new needs attention.

**HEARTBEAT_OK · STATUS_PAGE=DEGRADED** (P0 chronic-failure only — no new condition, no notification sent)

## Summary

Ran the heartbeat skill for the 20:00 UTC slot on 2026-07-25.

**Checks:**
- **P0 — Skills:** `heartbeat` is `success`, cf 0, last_success ~5.3h ago. Self-check and API-degradation flags cleared. Only the **chronic-failure** flag fires (lifetime success_rate 0.49 = 96/196) — the same intermittent ISS-001 gateway/zero-token success-detection bug. No failed or stuck skills. autoresearch/strategy-builder/soul-builder all ✅ (dispatch-only).
- **P1:** No open PRs, no urgent/open GitHub issues.
- **P2:** No new memory follow-ups.
- **P3:** Only heartbeat enabled; dispatching on schedule. No missing skills.

**Notification:** None sent — ISS-001 chronic-failure was already escalated (07-09) and is continuously logged; condition unchanged, well within the 48h dedup window.

**Files modified:**
- `docs/status.md` — regenerated → 🔴 DEGRADED, 1 open issue (ISS-001), heartbeat row ✅ 49% / cf 0, next run 2026-07-26 08:00 UTC. Token pulse omitted (no `articles/token-report-*.md`).
- `memory/logs/2026-07-25.md` — appended the 20:00-slot run entry.

**Follow-up:** ISS-001 (critical) remains open — the gateway exit-code / zero-token success-detection bug keeps ~half of tracked heartbeat runs recorded as failed. Needs a repair skill to fix the success-detection logic; fleet health metrics stay unreliable until then.
