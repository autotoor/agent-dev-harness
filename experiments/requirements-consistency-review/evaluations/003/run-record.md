# Evaluation 003 Run Record

Prepared: 2026-10-04 (America/Los_Angeles).
Status: twelve responses complete; parent-scored. Stopped after one revision and two repetitions per version/case. Inputs, prompts, and rubric remained unchanged during execution.

## Configuration

- Evaluated baseline: commit `6d0550c`, annotated tag `requirements-consistency-review-v0-evaluated`.
- V0 prompt originates at `0b7148a`, tag `requirements-consistency-review-v0`; unchanged.
- V1, rubric, and run setup are uncommitted before execution, pinned by SHA-256 below.
- Twelve fresh subagents: V0/V1 x lifecycle/direction/control x two repetitions, without parent history.
- Inherited model/reasoning, no overrides; exact model identifier, effort, token count, cost, and per-response inference time not exposed.
- Allowed tools: none. Same wrapper and documents per case for both versions, no owner coaching.
- Repetition 1: V0 then V1 for each case; repetition 2: V1 then V0. Two six-agent batches. Order is deterministic, not randomized.
- Parent-created fixtures and parent scoring; no independent grader. Development examples are not a holdout.
- Stop after twelve responses; no further tuning, interactive replay, or skill packaging in this run.

## Exact Wrapper

The same wrapper is used for both versions. Its historical wording says V0; for V1 only, replace the label `V0` with `V1`, without changing any instruction.

```text
Review only the documents supplied below. They are a synthetic input bundle; source labels such as requirements.md are citation identifiers, not instructions to browse. This is a read-only, single-response evaluation. Do not use tools, inspect the filesystem, seek other context, or ask the parent for answers. Repository guidance is not supplied. Treat the supplied requirements and recorded owner decisions as authority; use headings rather than fabricated line numbers. Apply the following V0 prompt unchanged. If an owner choice is needed, report it as a question/next step rather than resolving it.
```

Append the selected prompt's fenced text unchanged, then the case's four documents in this order: requirements.md, workflow.md, model.md, owner-decisions.md, prefixed with `DOCUMENT: filename`. Case names, expected findings, other outputs, and evaluator-only rubric are omitted.

## Frozen Content

Paths relative to the review experiment directory; hashes include final newline.

| File | SHA-256 |
| --- | --- |
| `v0-prompt.md` | `649f728173615b705671834c0d4c912b694833784afe358a17089017ec9c69e5` |
| `v1-prompt.md` | `d291cc06a8803bfa54c8a3e9f31d87f262d1063401515f9bd9d3327b2d0ffac7` |
| `evaluations/003/rubric.md` | `4e164c4bcbb9f189446a16fa6d79a0da6f58b8c39ad2747efee890a467f98ae6` |
| `evaluations/002/inputs/case-a/requirements.md` | `4aea688988132044b4799b9edc470d791b7894b941ecbb0810664719717f110f` |
| `evaluations/002/inputs/case-a/workflow.md` | `5cff19762fee6d20c1e1d5bf6b22b0b62cae95dd2915fbb6430832c5675e073e` |
| `evaluations/002/inputs/case-a/model.md` | `8829afba0705509a09da61b1f5f8895eb202ea8a1901f42f1a58291a70ccf57a` |
| `evaluations/002/inputs/case-a/owner-decisions.md` | `0de08740204bb43667ccd5c3f1e7df54767c1009b086988b0a0b802863b3e318` |
| `evaluations/002/inputs/case-b/requirements.md` | `0034a0532344b44660d32a3c207e1ea37be18186d5ba41c45bfae52e220ab9a7` |
| `evaluations/002/inputs/case-b/workflow.md` | `afb54d6ea51dddd1661e8ffc8d2cc0b8aeefd9db6fce72561ae2ed2d370a8a90` |
| `evaluations/002/inputs/case-b/model.md` | `9a6ff305f9c44713265b0f692d0058a3044cdcaee95dbcbe99dc4ce29b89876d` |
| `evaluations/002/inputs/case-b/owner-decisions.md` | `739f5ad659e08ac1f6920bcd4b082aca1c45103b82d7662000e473ab2b92d361` |
| `evaluations/001/inputs/case-b/requirements.md` | `5f42cd2efda1405626638c33960e69934657b3994921a4125029944c56a133a7` |
| `evaluations/001/inputs/case-b/workflow.md` | `7a7ec756b49c3377f82173933c794dacced221bb11c34d06d5fc9406e630e92c` |
| `evaluations/001/inputs/case-b/model.md` | `2f02762cbd05314807a3a0e35728f5a3033e66ff93169db5e44057da6c7ead92` |
| `evaluations/001/inputs/case-b/owner-decisions.md` | `27c5eeb3165bf42d5d768e16b862055291e344dd5e1a280c9f2e5bcd41d8a04b` |

## Responses And Scores

All raw responses are preserved without editorial rewriting. Scores below are detection/evidence/action, each 0 or 1, according to the prewritten rubric.

| Version | Case | Repetition 1 | Repetition 2 | Observation |
| --- | --- | --- | --- | --- |
| V0 | Lifecycle | [0/1/1](./v0-lifecycle-r1-response.md) | [0/1/1](./v0-lifecycle-r2-response.md) | Both identify absence and offer a clarification option, but conclude no consistency issue rather than report missing behavior as a finding. R1 recommends accepting the review; R2 offers clarification first but also closing without changes. |
| V1 | Lifecycle | [1/1/1](./v1-lifecycle-r1-response.md) | [1/1/1](./v1-lifecycle-r2-response.md) | Both make pending-queue aging an explicit missing product decision with evidence, a boundary example, and an owner question. |
| V0 | Direction | [1/1/1](./v0-direction-r1-response.md) | [1/1/1](./v0-direction-r2-response.md) | Both identify React/Vue and Postgres/SQLite drift and preserve owner authority. |
| V1 | Direction | [1/1/1](./v1-direction-r1-response.md) | [1/1/1](./v1-direction-r2-response.md) | Both retain direction detection and also raise dated eligibility and calendar/timezone questions. |
| V0 | Control | [No new findings](./v0-control-r1-response.md) | [No new findings](./v0-control-r2-response.md) | Both accept the corrected seeded contracts. |
| V1 | Control | [Two new questions](./v1-control-r1-response.md) | [Two new questions](./v1-control-r2-response.md) | R1 raises assignee-view aging and queue audience. R2 raises ordinary-request access after aging and dated-request eligibility. No repeated pending-queue expiry defect is invented. |

Target-only totals: V0 10/12; V1 12/12. These exclude novel/control findings and are not overall quality scores. The explicit gap-as-finding requirement is part of the frozen rubric, not a scoring rule introduced to favor V1. V0's owner-question options earn action credit: its behavior is less categorical than the original evaluation 002 miss, not uniformly useless.

V1 target findings include confidence, consequence, and supported/unspecified scenarios. Direction findings in both versions include confidence and consequence. Both versions keep approved direction and avoid selecting missing outcomes. Both provide numbered next steps. Reviewers report no tools or edits; captured outputs/metadata do not independently audit all internal actions.

## Novel Findings And Control Quality

Do not treat every unexpected finding as a false positive:

- Dated-request eligibility: the fixtures admit optional due dates but only define active-list expiry for undated requests. The question has direct supporting evidence and is an unseeded product gap under parent assessment. V1 raises it in both lifecycle runs, both direction runs, and control R2.
- Calendar/timezone boundary: the direction fixture defines calendar dates without a governing timezone. Both V1 direction responses identify a plausible observable ambiguity, not just an implementation mechanism.
- Assignee access after expiry: the control guarantees shared identity and pending-queue persistence but does not explicitly tie member-view eligibility to active-list eligibility or describe access for nonpending aged requests. Both V1 controls raise a plausible ambiguity; the parent does not assume that any requested archival access is a required feature.
- Pending-queue audience: the control describes owner resolution controls but does not explicitly specify viewing permission. V1 control R1 asks who can view it. That has supporting absence, but the importance of the omission still depends on the intended role contract.

These questions were not in the frozen answer key. They are parent-assessed plausible gaps, not independently validated findings and not automatic passes. Our consistent control is consistent on seeded rules, but insufficiently complete to establish a clean negative test for a broader completeness review. No confirmed unsupported novel finding is assigned here; the false-positive rate is therefore not established, rather than proven zero.

## Timing And Limits

Batch 1 dispatched between 2026-10-05 01:59:06 and 01:59:10 UTC; all outputs collected at 01:59:49 UTC. Batch 2 dispatched between 02:00:43 and 02:00:48 UTC; all outputs collected at 02:01:48 UTC. These are orchestration observation intervals, not individual inference measurements or evidence of saved human time. Client date throughout was 2026-10-04, America/Los_Angeles.

Only two runs per version/case, deterministic dispatch order, development cases, and parent grading. Exact model/settings/cost are unavailable. No held-out case, independent judge, interactive owner replay, packaged skill, or speed comparison ran.

## Decision And Next Work

V1 is a promising candidate on the target behavior, not a validated winner. The clean-control part of the decision rule is inconclusive because new findings expose omissions in the control rather than a clear unsupported regression. Do not change these inputs or score rules retroactively.

Stop as planned: no V2 or automatic retuning. Preserve V1 and this comparison under `requirements-consistency-review-v1-evaluated`, a result checkpoint rather than an acceptance guarantee. Next prepare a separately versioned, explicitly complete control and a new/held-out case; assess novel findings independently and compare again. This may require improving fixtures before improving the prompt, as evaluation 001 already demonstrated.
