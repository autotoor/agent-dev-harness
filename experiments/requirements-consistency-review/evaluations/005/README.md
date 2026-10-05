# Evaluation 005: Prioritizing Supplied Findings

Prepared and setup approved: 2026-10-04. Owner selected approval plus commit/push of the preparation checkpoint. Status: setup frozen for preservation; awaiting separate execution approval. No runs or results.

## Review This Setup

- [Plan](../../prioritization-test-plan.md): classification only, six responses, stop after the batch.
- [Prompt](../../prioritization-v0-prompt.md): prepared standalone classification prompt, not consistency-review V2.
- [Case A requirements](./inputs/case-a/requirements.md), [decisions](./inputs/case-a/owner-decisions.md), [findings](./inputs/case-a/candidate-findings.md): exposed updates without write authority, plus an export demand.
- [Case B requirements](./inputs/case-b/requirements.md), [decisions](./inputs/case-b/owner-decisions.md), [findings](./inputs/case-b/candidate-findings.md): settled no-data error behavior, unsettled presentation, and a mistaken absence claim.
- [Case C requirements](./inputs/case-c/requirements.md), [decisions](./inputs/case-c/owner-decisions.md), [findings](./inputs/case-c/candidate-findings.md): compound loan-display question and a waitlist demand.
- [Evaluator-only rubric](./rubric.md): expected categories, evidence, actions, and limitations. Never supply to classifiers.
- [Dispatch specification](./dispatch.md): exact wrapper and assembly order; never supply this whole file or this README to classifiers.
- [Prepared hashes](./prepared-content-sha256.md): original review snapshot, adopted unchanged as the approved setup hashes. Reverify before dispatch; preserve any later edits as a new snapshot.

These are new development cases, not external validation. The parent authored the cases and rubric with knowledge of evaluation 004. No independent grader or owner simulation is included.

## Execution Gate

Owner approved preserving this setup as `requirements-prioritization-v0-prepared`. The checkpoint includes the assessment and plan; its name records preparation, not evaluation success. Original hashes remain unchanged. Recheck live Git/remote state for checkpoint publication. Obtain separate authorization to run the six classifiers; approval to prepare and preserve files is not execution approval. No run has been performed.

Run two fresh, no-history classifiers per case. Use the same prompt and wrapper, but each classifier sees only its own three documents. No tools or coaching; instruction-level isolation is not a security boundary. Record exact dispatches, inherited settings when available, all raw responses, scores by finding, and any protocol departure. Stop after six even if the outcome is mixed. Do not alter tests or create another prompt revision during execution.
