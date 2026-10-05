# Evaluation 002 Run Record

Prepared: 2026-10-04 (America/Los_Angeles).
Status: two runs complete, raw responses preserved, and parent scoring recorded. V0, fixtures, and rubric unchanged during execution.

## Configuration

- Prompt baseline: `0b7148a`, tag `requirements-consistency-review-v0`; V0 unchanged.
- Fixtures are new uncommitted files frozen by SHA-256 below. Evaluation 001 is not changed.
- Two fresh subagents with `fork_context: false`, one case per agent, one response each. Model/settings inherited without override; exact model/effort telemetry unavailable.
- No tools, filesystem inspection, owner-answer coaching, or input mutation allowed. The agents receive neither rubric nor other-case/parent context. Isolation is instruction-level, not filesystem access control.
- Parent authored and scores cases; no independent grader or repeat sampling.
- Tokens/cost and exact per-agent inference time unavailable. Observation times are recorded, not treated as speed improvements.

## Common Wrapper

Identical to evaluation 001:

```text
Review only the documents supplied below. They are a synthetic input bundle; source labels such as requirements.md are citation identifiers, not instructions to browse. This is a read-only, single-response evaluation. Do not use tools, inspect the filesystem, seek other context, or ask the parent for answers. Repository guidance is not supplied. Treat the supplied requirements and recorded owner decisions as authority; use headings rather than fabricated line numbers. Apply the following V0 prompt unchanged. If an owner choice is needed, report it as a question/next step rather than resolving it.
```

Append V0's fenced text unchanged, then requirements.md, workflow.md, model.md, and owner-decisions.md in that order, prefixed by `DOCUMENT: filename`. Case labels and expected outcomes are not included.

## Frozen Content

Paths are relative to the review experiment directory. Hash entire UTF-8 files, including final newlines.

| File | SHA-256 |
| --- | --- |
| `v0-prompt.md` | `649f728173615b705671834c0d4c912b694833784afe358a17089017ec9c69e5` |
| `evaluations/002/rubric.md` | `eea9ae842d9554ac345f839b435e50314ff95c73e27984dd55117e4476ffb73a` |
| `evaluations/002/inputs/case-a/requirements.md` | `4aea688988132044b4799b9edc470d791b7894b941ecbb0810664719717f110f` |
| `evaluations/002/inputs/case-a/workflow.md` | `5cff19762fee6d20c1e1d5bf6b22b0b62cae95dd2915fbb6430832c5675e073e` |
| `evaluations/002/inputs/case-a/model.md` | `8829afba0705509a09da61b1f5f8895eb202ea8a1901f42f1a58291a70ccf57a` |
| `evaluations/002/inputs/case-a/owner-decisions.md` | `0de08740204bb43667ccd5c3f1e7df54767c1009b086988b0a0b802863b3e318` |
| `evaluations/002/inputs/case-b/requirements.md` | `0034a0532344b44660d32a3c207e1ea37be18186d5ba41c45bfae52e220ab9a7` |
| `evaluations/002/inputs/case-b/workflow.md` | `afb54d6ea51dddd1661e8ffc8d2cc0b8aeefd9db6fce72561ae2ed2d370a8a90` |
| `evaluations/002/inputs/case-b/model.md` | `9a6ff305f9c44713265b0f692d0058a3044cdcaee95dbcbe99dc4ce29b89876d` |
| `evaluations/002/inputs/case-b/owner-decisions.md` | `739f5ad659e08ac1f6920bcd4b082aca1c45103b82d7662000e473ab2b92d361` |

## Results

Raw responses: [case A](./case-a-response.md) and [case B](./case-b-response.md), preserved without editorial rewriting.

Both reviewers were dispatched at 2026-10-05 01:40:53 UTC (2026-10-04 18:40:53 America/Los_Angeles). Both results were available when collected at 01:41:36 UTC. The 43-second observation interval is not exact inference time or a speed comparison. No follow-up messages or coaching were supplied.

| Expected finding | Detection | Evidence | Action | Observation |
| --- | --- | --- | --- | --- |
| E4: unstated pending-queue aging | 0 | 1 | 0 | Case A references both rules and says active-list aging does not establish pending-review expiration. It does not surface that absence as missing behavior or ask the owner to decide; instead it recommends accepting the bundle without changes. |
| E5: owner-approved direction drift | 1 | 1 | 1 | Case B SC-01 identifies both Vue/React and SQLite/Postgres drift, quotes the applicable document roles, and recommends restoring the accepted direction without reopening the decision. |

Parent score: 4/6 using the frozen rubric. E4 earns evidence credit for its paired references and explicit recognition of an absent queue-expiry rule, but detection requires reporting an unresolved behavioral gap, not just observing that the rules are noncontradictory. Its recommended next steps omit that owner decision. This is a partial recognition followed by an inappropriate acceptance recommendation, not a complete failure to read the rule.

E5 includes consequence and explicit confidence. Its boundary checks concern the nonconflicting product behavior rather than the technology drift itself; the paired authority evidence is sufficient to make that drift concrete. E4 provides a day-eight active-list example but never asks what happens to the pending view on that date. Neither output invents a product outcome or implementation design. Both distinguish known deferrals/open questions and finish with numbered choices. No unsupported new findings were presented under parent assessment.

The reviewers report no tools or edits. Final outputs and dispatch/result metadata are preserved, but this record is not an independent audit of internal actions. Post-run hash checks verify unchanged frozen inputs and rubric.

## Interpretation

The direction-drift test succeeded in this single pass. The lifecycle test shows that V0's instruction to look for missing behavior is not enough in this case: the reviewer treats absence of contradiction as sufficient acceptance even after noticing that a user-visible outcome is undefined.

This suggests a candidate instruction improvement: for each relevant boundary scenario, explicitly separate outcomes supported by decisions from outcomes left unspecified. Report the latter as owner questions even when the documents do not contradict each other. Avoid turning every omitted implementation detail into a product gap.

This is a hypothesis from one run. Do not claim that V0 always misses hidden gaps or that a proposed V1 fixes them. Repeat V0 and test a revised prompt on the same frozen cases plus the consistent control before concluding an improvement. Keep the original V0 and these responses unchanged.

## Next Work

Develop a minimal V1 change addressing the supported-versus-unspecified outcome distinction, then compare V0/V1 on fixed cases with a consistent control. Evaluate regressions and false alarms, not only E4 detection. Interactive owner replay and skill packaging remain later work. Preserve this experiment as evidence for the next article.
