# Evaluator-Only Rubric: Evaluation 002

Prepared before execution. Never supply to reviewers. Score intended behavioral detection separately from formatting and speculative suggestions.

## Expected Findings

| Case | ID | Expected finding | Evidence | Appropriate action |
| --- | --- | --- | --- | --- |
| A | E4 | Pending-review access after active-list expiry is unspecified, despite a separate queue | requirements Aging And Review; owner decisions establish separate pending status but no post-expiry rule | Illustrate day eight and ask the owner what should happen to queue visibility. Do not invent retention or assume that a separate queue guarantees indefinite access. |
| B | E5 | Current descriptions agree on Vue/SQLite but contradict selected React/Postgres direction | requirements Selected Components and Authority; workflow selected components; model SQLite direction; owner decisions Accepted Component Direction and Change Authority | Identify both frontend and database drift; recommend correcting documents to preserve accepted direction unless a subsequent owner decision changes it. Do not select a new stack or present agreed technologies as undecided. |

## Scores

For each expected finding: detection (0/1), paired relevant evidence (0/1), appropriate supported correction or owner question (0/1). Maximum 6 points. E5 detection requires both frontend and database drift. E4 must be treated as newly surfaced missing behavior, not merely a previously acknowledged open question.

Also record consequence, explicit confidence, and boundary-example coverage for each finding. Stable IDs, scope summary, and numbered next steps remain expected. Useful repetition, deferred calendar/mobile features, known deletion retention, and undecided backend/schema/hosting are not new defects merely because they exist.

Report unexpected suggestions separately. Assess their evidence before labeling false positives. Penalize no implemented software for defects in proposed documents. No tools, editing, coaching, or implementation are allowed.

## Limits

These cases are synthetic and deliberately small. One pass cannot prove broad effectiveness or speed. The same parent authors and scores the tests. The control is from evaluation 001, not freshly repeated here. Compare against unchanged V0 first; do not rewrite the prompt merely because a second evaluation exists.
