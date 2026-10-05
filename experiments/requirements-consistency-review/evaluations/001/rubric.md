# Evaluator-Only Rubric

Written before execution. Never include this file in reviewer inputs. Score behavior and evidence, not prose similarity. This toy suite does not claim completeness of the supplied requirements.

## Expected Findings In Case A

| ID | Expected finding | Evidence | Expected response |
| --- | --- | --- | --- |
| E1 | Workflow rejects required undated requests | requirements Request Coverage and Acceptance Criteria; workflow validation | Identify the conflict and recommend accepting missing due dates without inventing one; do not ask the owner to reconfirm this settled direction. |
| E2 | Model cannot represent required multiple assignees | requirements Assignments; model complete single `assigneeId` representation | Identify the mismatch and suggest a multi-assignee relationship without selecting physical tables. |
| E3 | Day-eight pending-review access is unspecified | requirements Aging And Review; owner decisions absent queue-aging decision | Ask what should happen to queue access after active-list expiry; use a boundary example and do not claim a chosen outcome. |

## Case B Control

E1, E2, and E3 are resolved. The reviewer should not report these as outstanding findings. It may state that no material consistency issues were found within scope, while mentioning review limits and known open decisions.

## Per-Finding Scoring For Case A

- Detection: 0 absent or wrong; 1 identifies the relevant gap correctly.
- Evidence: 0 absent/incorrect; 1 names both relevant document sections or explicitly links the interacting rules.
- Action: 0 invents a rule, reopens a settled decision, or gives no useful next action; 1 proposes a supported correction for E1/E2 or an owner question for E3.

Maximum: 9 points across E1-E3. Also record whether each finding includes a consequence, confidence, and a concrete scenario as requested by V0; do not hide omissions behind the aggregate score.

## Restraint Checks For Both Cases

- Does not report useful acceptance-criterion repetition as harmful duplication.
- Does not report calendar export deferral as a missing first-release feature.
- Distinguishes the acknowledged deletion-retention question from a newly discovered contradiction.
- Describes proposed documentation gaps, not implemented software bugs.
- Does not choose framework, schema, new product behavior, or start implementation.
- Ends with a recommendation and numbered next-step options.

Record violations individually, not folded into detection score. Record tool use or attempted extra-file access as a run-protocol violation. Any novel finding requires human assessment of supporting evidence: plausible unseeded gaps are not automatically false positives, and an unreviewed suggestion is not automatically correct.

## Decision After This Run

This first run can justify a limited prompt revision or a larger evaluation, not packaging the skill or claiming speed improvements. No comparison prompt, repeated sampling, unfamiliar product trial, interactive replay, or runtime test is part of this run.
