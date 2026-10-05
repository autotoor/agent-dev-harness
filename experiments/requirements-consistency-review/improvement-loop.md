# Prompt Evaluation And Improvement Loop

Agreed: 2026-10-04. Run, evaluate, diagnose, revise, and run again. A convincing response or a familiar example passing is not enough evidence to package a skill.

## Preserve Each Iteration

Record the exact prompt version and diff, observed failure, proposed explanation, and intended change. Freeze input documents, expected outcomes, and scoring rules before execution. Record model/settings when exposed, allowed tools, raw responses, scores, false alarms, interventions, and available timing/cost data. Mark unavailable telemetry explicitly.

Separate changes to fixtures from changes to prompts. A weak test may need better inputs rather than new instructions. Preserve failed attempts and surprising outputs instead of overwriting them.

## Compare Fairly

Use the same frozen cases, wrapper, tool permissions, and model settings where controllable for both versions. Repeat runs to expose variability. Retain a consistent control and distinguish known open questions, intentionally deferred behavior, and unspecified implementation mechanisms from missing user-visible behavior.

Cases used to tune the prompt are development cases, not held-out validation. Add unfamiliar cases or a separately prepared holdout before broader claims. Do not coach a reviewer using the answer key. Record any departures from protocol.

## First Comparison Boundary

Evaluation 003 will compare unchanged V0 with one minimal V1 addition on evaluation 002's two cases and evaluation 001's consistent control. Use two fresh runs per version/case: twelve responses total. Stop after this one revision and comparison, whether the result improves, regresses, or remains unclear. No automatic further tuning, owner simulation, or skill packaging.

Desired result: actionable recognition of the unstated lifecycle gap, preserved recognition of both direction changes, and no unsupported new findings on the control. If mixed, preserve the evidence and propose a next experiment rather than silently continuing until the examples pass.

## Commits And Tags

Increment prompt versions for material instruction changes that are tested. Repeated runs keep the same prompt version; fixture-only changes receive a new evaluation number. Do not reserve a version number for a final good result or rename failed candidates away. A selected candidate can receive a descriptive milestone tag independently of its prompt version.

1. Commit completed V0 evaluations and tag the baseline `requirements-consistency-review-v0-evaluated`. Keep `requirements-consistency-review-v0` unchanged.
2. Save new instructions under a new prompt version. Identify runs with file hashes even before their iteration is committed.
3. Commit the prompt change, frozen comparison setup, raw responses, scoring, and conclusion as a coherent iteration. Do not erase an unsuccessful revision.
4. Use annotated milestone tags for article-linked comparisons or versions selected for further trials; tags describe the checkpoint, not proof that it is production-ready. Proposed first comparison tag: `requirements-consistency-review-v1-evaluated`.
5. Push checkpoints before publishing snapshot or compare links. Blog commits are independent and describe the corresponding harness stage through links. Do not tag every wording edit or move prior tags.

## Article Evidence

Show observation, hypothesis, prompt diff, and actual result, including regressions and limits. Distinguish prompt testing from skill packaging and review from interactive requirement development. An evaluation loop may reduce backtracking, but saved time and generalization must be measured rather than assumed.
