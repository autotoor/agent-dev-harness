# Evaluation 004: Sharper Controls And An Unfamiliar Case

Prepared: 2026-10-04. Keep the V1 prompt from `ab99dae` unchanged. This follow-up changes fixtures, not the prompt; no V2 is created.

## Cases

- Case A: new request-tracker control explicitly defines dated eligibility, UTC, member-view expiry, queue audience, and ordinary-item post-expiry access. Earlier controls remain unchanged.
- Case B: community tool lending, with one unstated suspension/reservation interaction.
- Case C: the same lending documents with that interaction resolved by one workflow clause.

A fresh fixture-author subagent received no parent conversation, reviewer prompt, or earlier outputs. Its [instructions](./author-prompt.md), [raw response](./author-response.json), and [expected finding](./answer-key.md) are preserved. The parent clarified identical secondary details in both lending cases before freezing: exact elapsed intervals, already-authorized viewing permissions, rejected terminal/duplicate actions, and manual versus automatic overrides. The missing suspension outcome itself was not supplied in case B.

The lending case was not used while creating V1. It is an unfamiliar synthetic transfer check, not an independent real-world validation dataset. The same inherited model family may underlie author/reviewer/parent; exact model telemetry is unavailable. Parent preflight and scoring are disclosed, and the answer key stays out of reviewer inputs.

## Bound

Run V1 twice on each of three cases: six fresh read-only reviewers. Use the unchanged wrapper from evaluation 003, no tools, no parent history, no answer key, and no coaching. Freeze [rubric](./rubric.md) and inputs before dispatch. Stop after six responses, assess control findings, and record results in [run record](./run-record.md). Do not repair fixtures during the run or tune another prompt automatically.

## Post-Run Assessment

The [additional-question assessment](./finding-assessment.md) separates access decisions, wording/UI clarifications, and compound display findings. It is a later parent assessment, not independent validation or a revised answer key. Frozen inputs, scores, raw responses, and V1 are unchanged. Review the classifications before designing any new prioritization test.
