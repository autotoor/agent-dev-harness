# Manual Review Evidence

Recorded: 2026-10-04. These observations precede [the reusable V0 prompt](./v0-prompt.md); they do not constitute a trial of that prompt or a packaged skill.

## Preserved Baselines

The public reference product preserves three documentation checkpoints:

- [Initial workshop](https://github.com/kid-scheduler/school-email-assistant/tree/requirements-workshop-v0), `f35d4a6`.
- [Reconciliation and independent follow-up review](https://github.com/kid-scheduler/school-email-assistant/tree/requirements-reconciliation-v1), `10d49aa`.
- [Follow-up findings resolved](https://github.com/kid-scheduler/school-email-assistant/tree/requirements-reconciliation-v1-resolved), `c4703f4`.

Detailed domain findings and synthetic acceptance scenarios remain in that repository. These checkpoints establish documentation history, not runtime correctness or full specification readiness.

## What Helped

- Comparing requirements to conceptual models and workflows exposed contradictions that rereading the requirements alone did not.
- Checking supplied human decisions exposed direction drift even where repository documents agreed with one another.
- Lifecycle and boundary examples turned broad gaps into questions an owner could answer.
- A follow-up review found interactions introduced or clarified by reconciliation; a resolved finding list was not a guarantee of completeness.
- Stable finding IDs and linked evidence separated historical findings from their current resolution status.
- Numbered choices and an explicit next step reduced interaction effort. Stopping at the assigned boundary avoided accidental scope expansion.

## Guardrails For The Prompt

- Preserve accepted scope; do not recommend expanding the first release merely to close a future question.
- Do not mistake useful repetition for harmful duplication or a proposed schema for a running defect.
- Distinguish deterministic documentation checks, semantic review, human approval, and executable verification.
- Review independently first; reconcile in a separately authorized phase. Keep product decisions out of generic harness instructions.

## What Remains Unproven

No controlled evaluation of the V0 prompt has run. Its recall, false-positive rate, cross-project usefulness, cost, and delegation benefits are unknown. Next: trial it on small synthetic consistent, contradictory, and intentionally incomplete document sets before extracting a skill.
