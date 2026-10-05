# Evaluation 003: Repeated V0/V1 Comparison

Prepared: 2026-10-04. One bounded revision; two repetitions per version/case, twelve responses total. See [run record](./run-record.md) for outcomes and [rubric](./rubric.md) for evaluator-only scoring.

## Hypothesis

V1 adds an explicit supported-versus-unspecified outcome check in step 3. It may turn the lifecycle absence noticed in evaluation 002 into an actionable owner question, without causing new unsupported findings on the consistent control or losing recognition of direction drift.

## Fixed Cases

- Lifecycle: evaluation 002 case A, unchanged.
- Direction drift: evaluation 002 case B, unchanged.
- Consistent control: evaluation 001 case B, unchanged.

Inputs and rubric are frozen by hashes before execution. Use the same wrapper and tool restrictions as prior runs. Fresh subagents receive no parent history, other-case outputs, or answer key. Inherited model/settings are not overridden; exact model telemetry is unavailable. This is instruction-level isolation, not an access-control sandbox.

Run repetition 1 in mixed V0/V1 dispatch order, collect and close all six agents, then run repetition 2 with reversed version order. These are two observations per cell, not enough to estimate a stable success rate. Parent grading is not independent.

Stop after these twelve responses. Do not mutate the candidate, fixtures, or rubric, coach the reviewers, or make further prompt revisions in this run. Preserve regressions and inconclusive results. This development suite is not a held-out test; no speed or generalization claim follows from passing it.
