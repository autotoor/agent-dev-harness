# Evaluator-Only Rubric: Evaluation 003

Written before execution. Never supply to reviewers. Apply identical scoring to both prompt versions. Preserve the expected outcomes from evaluations 001/002 rather than changing the answer key to favor V1.

## Target Cases

For each response on lifecycle or direction drift, award detection, evidence, and action independently (0/1 each). Two repetitions give a maximum of 6 per case and 12 across both target cases for each version.

- Lifecycle detection: report pending-review visibility after active-list expiry as a missing observable product decision, not merely state that no contradiction exists. Evidence: compare active-list aging and separate queue/owner direction. Action: ask a focused owner question without selecting retention behavior. A day-eight example is useful but not a substitute for asking about the unknown queue outcome.
- Direction detection: identify both Vue/React and SQLite/Postgres changes relative to accepted owner direction. Evidence: pair current descriptions with owner authority. Action: recommend correcting descriptions to preserve the selected stack unless a new owner decision changes it; do not reopen the choice or make it unselected.

Track explicit confidence, consequences, and scenario quality separately. Prioritized stable IDs, scope/limits, and numbered next steps remain required by both versions.

## Control And Regression Checks

For each control response, record whether it raises any new findings. Expected: no seeded defect and no invented post-expiry ambiguity, because continued pending-queue access is explicit. Useful repetition, intentionally deferred controls/features, and acknowledged deletion retention should not become new defects.

Across all cases, record unsupported findings, invented product decisions, selection of implementation details, reopened settled choices, tool use, or unapproved editing. Human-assess novel suggestions before deciding whether they are unsupported. A generic optional suggestion is not automatically a defect, but counts as an observation if it dilutes the recommended next step.

## Decision Rule

A promising V1 result requires actionable lifecycle detection in both repetitions, preserved direction findings in both repetitions, and no unsupported control findings in either repetition. If not met, report mixed/regressed/inconclusive rather than tune again within this run. Even if met, only advance to broader or held-out tests; do not claim a validated skill or speed benefit.

Compare individual responses, not just totals. With two runs per cell, report observed counts without percentages implying reliability. A repeated V0 success would also show that the original miss is variable rather than universal.
