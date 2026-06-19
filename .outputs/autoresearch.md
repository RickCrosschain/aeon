The autoresearch skill requires a `var=` parameter set to the name of the skill to evolve. Per the skill's own instructions (line 9):

> If `${var}` is empty, abort with: "autoresearch requires var= set to a skill name" and exit.

No `var=` was provided in this invocation, so I'm aborting as instructed.

**autoresearch requires var= set to a skill name**

## Summary

- **Action:** Read and began executing `skills/autoresearch/SKILL.md`.
- **Result:** Aborted at step 0 — the skill is a meta-skill that evolves a *named target skill*, and no `var=` (target skill name) was supplied. The skill explicitly mandates aborting in this case before doing any research or generating variations.
- **Files created/modified:** None.
- **Follow-up needed:** Re-run with a target, e.g. `var=token-movers` (or whichever skill you want evolved). Available skills live under `skills/`. If this is being driven by a cron/chain, set the `var` input in `aeon.yml` for the autoresearch step.

To proceed, tell me which skill to evolve and I'll run the full pipeline (research → 4 variations → score → winning PR).
