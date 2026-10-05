# Review And Conversation Evaluation Plan

Status: agreed direction, 2026-10-04. Evaluations [001](./evaluations/001/run-record.md) and [002](./evaluations/002/run-record.md) informed the [V0/V1 comparison](./evaluations/003/run-record.md). The [unchanged-V1 follow-up](./evaluations/004/run-record.md) tests sharper controls and unfamiliar lending content. A [post-run parent assessment](./evaluations/004/finding-assessment.md) now distinguishes implementation blockers from useful clarifications and splits the loan-display finding. Target detection is promising; specificity remains inconclusive. Human confirmation of these classifications and a bounded prioritization-test plan are proposed next, not automatic V2 tuning. Independent grading, interactive replay, and skill packaging remain pending.

## Goal

Next proposed bounded work is the [prioritization test](./prioritization-test-plan.md). Owner approved the prepared setup and commit/push checkpoint. [Evaluation 005](./evaluations/005/README.md) has three bundles, rubric, standalone prioritization-v0, dispatch specification, and unchanged approved preparation hashes. The test isolates classification of supplied findings; it is not a V1 rerun or a V2 revision. Separate execution approval and hash reverification are required before any runs.

Test whether reusable instructions help produce coherent, consistent requirements with less backtracking. Treat speed and quality improvements as hypotheses until measured.

## Stage 1: Read-Only Review

Give a reviewer an immutable older requirements snapshot and its related documents. Do not supply the latest requirements or known-finding answer key to that reviewer. Evaluate known-gap detection, supporting evidence, false alarms, and preservation of accepted scope.

Also review a resolved snapshot to see whether the prompt keeps reporting corrected findings. The latest documents are not perfect ground truth: independently assess unexpected findings rather than automatically scoring them as wrong.

Start with a small synthetic generic document set with explicit expected findings and a consistent control. Product snapshot replays and product-specific fixtures belong in the product repository or isolated trial checkout, not this generic harness repository.

## Stage 2: Interactive Replay

1. A working agent receives older documents and instructions to resolve a bounded set of findings in an isolated copy.
2. An answer agent receives a frozen answer key derived from later human-approved decisions, not freedom to design the product.
3. A parent orchestrates questions and responses without coaching the worker toward the target. It need not forward unrelated context.
4. The answer agent answers only the question asked, does not volunteer missing requirements, and says when the recorded decisions do not supply an answer. Record unsupported questions for human assessment rather than inventing choices.
5. An evaluator examines resulting behavior, cross-document agreement, and decision preservation against the frozen rubric. It must not help the worker during the trial.

The parent may initially perform these steps manually. Separate roles and restricted inputs do not imply that orchestration code or a finished skill already exists.

## Evaluation

Compare behavioral outcomes, not Markdown wording. Score known findings separately from plausible new findings. Record:

- Known gaps found and missed; unsupported findings and evidence quality.
- Accepted decisions preserved, unintended choices, and remaining contradictions.
- Coverage of expected boundary outcomes and clarity of unresolved questions.
- Repeated questions, human interventions, turns, elapsed time, and available token/cost data. Mark unavailable measurements as unavailable.

Freeze prompt version, input commit, answer key, rubric, and allowed tools before a run. Record model/configuration and any intervention. Compare prompt versions on the same inputs and conditions; repeat runs when practical rather than drawing conclusions from one output.

## Sequence

1. Prepare a small synthetic case and control, answer key, and rubric.
2. Run the existing V0 review prompt without editing it during the run.
3. Record findings, misses, and false alarms before proposing revisions.
4. Preserve V0 and create V1 only if observed results justify changes.
5. Try interactive replay on two or three bounded findings.
6. Evaluate unfamiliar cases and real human use before claiming general usefulness or extracting a skill.

This tests two related tasks separately: detecting problems and working with an owner to resolve them. Do not attribute results from the second task to a read-only review prompt.
