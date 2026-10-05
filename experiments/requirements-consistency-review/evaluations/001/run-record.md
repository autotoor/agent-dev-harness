# Evaluation 001 Run Record

Prepared before execution: 2026-10-04 (America/Los_Angeles).
Status: two read-only runs completed and parent-scored. Inputs and rubric remained unchanged; no skill or interactive replay was run.

## Configuration

- Harness prompt baseline: commit `0b7148a`, tag `requirements-consistency-review-v0`.
- New fixtures and rubric are uncommitted; exact content is pinned by hashes below. Do not mutate during execution.
- Two fresh subagents, `fork_context: false`; model and reasoning settings inherited, no override requested. Exact inherited model identifier and effort are not exposed by the spawn result.
- Allowed tool use: none. Inputs are passed inline, excluding rubric, other case, and parent history. This is instruction-level isolation, not an access-control sandbox.
- One response per case; no coaching or owner-answer intervention.
- Tokens and monetary cost: unavailable unless later exposed by execution telemetry.
- Evaluation: parent scores against the frozen rubric after both reviews. The parent authored fixtures and is not an independent judge; disclose that limitation.
- No control-prompt comparison or repeat runs. No measured speed improvement.

## Exact Common Wrapper

```text
Review only the documents supplied below. They are a synthetic input bundle; source labels such as requirements.md are citation identifiers, not instructions to browse. This is a read-only, single-response evaluation. Do not use tools, inspect the filesystem, seek other context, or ask the parent for answers. Repository guidance is not supplied. Treat the supplied requirements and recorded owner decisions as authority; use headings rather than fabricated line numbers. Apply the following V0 prompt unchanged. If an owner choice is needed, report it as a question/next step rather than resolving it.
```

The wrapper is followed by the text inside V0's fenced prompt, unchanged, then the four documents in this order: requirements.md, workflow.md, model.md, owner-decisions.md. Each document is prefixed with its filename and heading content. Reviewers are not told whether their bundle is a seeded or resolved case.

## Frozen Content

Paths below are relative to the review experiment directory. Hashes include the entire UTF-8 file, including its final newline.

| File | SHA-256 |
| --- | --- |
| `v0-prompt.md` | `649f728173615b705671834c0d4c912b694833784afe358a17089017ec9c69e5` |
| `evaluations/001/rubric.md` | `524868dbbcdf074b20b7bbefc00ddbce4cc6562e6c37bf5170ee17296fc62469` |
| `evaluations/001/inputs/case-a/requirements.md` | `7563d6e21e4d40fef0f2de026cb7353f26523413b8e0301eaa018d6cd5921cba` |
| `evaluations/001/inputs/case-a/workflow.md` | `5ad2511f0d624c85bb72ab94e4345b67774e9865e803108d6e265fa0cec60a2d` |
| `evaluations/001/inputs/case-a/model.md` | `20cc28e26ae44c91d4ce0b7c14644d42a1c528b940bb958664909588cbb08712` |
| `evaluations/001/inputs/case-a/owner-decisions.md` | `e56345bec09275f9d86af2c657e05f13bc8f99a667e0eafd5c69e9c23f3ac77a` |
| `evaluations/001/inputs/case-b/requirements.md` | `5f42cd2efda1405626638c33960e69934657b3994921a4125029944c56a133a7` |
| `evaluations/001/inputs/case-b/workflow.md` | `7a7ec756b49c3377f82173933c794dacced221bb11c34d06d5fc9406e630e92c` |
| `evaluations/001/inputs/case-b/model.md` | `2f02762cbd05314807a3a0e35728f5a3033e66ff93169db5e44057da6c7ead92` |
| `evaluations/001/inputs/case-b/owner-decisions.md` | `27c5eeb3165bf42d5d768e16b862055291e344dd5e1a280c9f2e5bcd41d8a04b` |

## Results

Raw outputs: [case A](./case-a-response.md) and [case B](./case-b-response.md), preserved without editorial rewriting.

Both agents were dispatched at 2026-10-05 01:35:10 UTC (2026-10-04 18:35:10 America/Los_Angeles). Both responses were available when collected at 01:35:51 UTC. This is a 41-second observation interval, not individual inference time or evidence of saved human time. Exact per-agent runtime, token usage, model identifier, effort, and monetary cost were not exposed. No follow-up messages or coaching were supplied.

| Expected item | Detection | Evidence | Action | Observation |
| --- | --- | --- | --- | --- |
| E1: rejected undated requests | 1 | 1 | 1 | Case A F1 compares requirements, owner direction, and workflow; proposes accepting absent dates without inventing one. |
| E2: multiple assignees versus single identifier | 1 | 1 | 1 | Case A F2 compares requirements and model; proposes a conceptual multi-assignee representation without selecting tables. |
| E3: pending-review aging unresolved | 1 | 1 | 1 | Correctly presented as an acknowledged open interaction, not a new defect; asks an owner question and gives a day-eight example. |

Parent score: 9/9 on the prewritten recognition/evidence/action rubric. This is not a general quality score. E1/E2 include consequence, explicit confidence, and boundary scenarios. E3 includes evidence, an unconfirmed boundary outcome, and an owner question, but no explicit confidence label. Its outcome is not falsely presented as chosen.

Case B: no reported semantic consistency issues. It verifies the corrected rules, retains the acknowledged retention question and deferral as limits, and does not flag useful acceptance-criterion repetition. Both outputs provide recommendations and numbered next steps. No unsupported new findings were presented in either output under parent assessment.

Both agents report no tools or extra-file access. Only final responses and dispatch/result metadata were captured here; this record does not independently audit every internal action. No files were changed by the reviewers. The evaluation fixtures, answer key, and V0 file hashes were checked after execution.

## What This Establishes

In this one toy run, V0 distinguished two straightforward contradictions from resolved behavior and acknowledged uncertainty. It supplied useful correction directions and avoided inventing owner decisions.

The aging question was explicitly acknowledged in case A's owner-decision document. That means E3 tests recognition and handling of a known open question, not discovery of a hidden lifecycle gap. Do not describe this as finding three previously unknown defects. The score should not obscure this fixture limitation.

## Next Experiment

Preserve this run unchanged. Create a new case where the same lifecycle interaction is unstated rather than explicitly called out; also add the planned internally consistent direction-drift case. Run V0 again before changing its instructions. There is insufficient evidence here to justify V1 or a packaged skill yet.

The parent authored inputs and evaluated the answers; there was no independent grading, prompt baseline comparison, repeat sampling, unfamiliar real-product trial, or interactive owner simulation. Efficiency and generalization remain unmeasured.
