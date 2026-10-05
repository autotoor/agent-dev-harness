# Proposed Skills

This file captures reusable agentic tasks that may become harness skills after their workflows have been exercised manually. An entry is a design hypothesis, not an implemented skill.

## Requirements Workshop

Proposed skill name: `requirements-workshop`

Purpose: guide a product owner through eliciting, developing, challenging, and completing product requirements until they are ready for formal specification.

Development status: being exercised as a versioned prompt experiment under `experiments/requirements-workshop/`. The initial prompt is intentionally simple and should evolve from recorded trials before this proposal becomes a skill.

Candidate phases:

1. **Orient**: identify the product idea, intended users, current evidence, constraints, and authoritative source files.
2. **Elicit**: ask focused questions that expose goals, user journeys, assumptions, non-goals, risks, and unresolved decisions.
3. **Develop**: turn answers into coherent requirements, acceptance criteria, product boundaries, and explicit open questions.
4. **Review panel**: examine the developing requirements through multiple bounded perspectives, such as user, product, privacy and safety, implementation, and harness concerns.
5. **Reconcile**: surface contradictions and gaps from the panel, return them to the product owner for decisions, and update the requirements without allowing a simulated reviewer to become authoritative.
6. **Readiness check**: determine whether the requirements are clear enough to move into a formal specification workflow and record what remains unresolved.

The review panel is one phase of the workshop, not a separate end in itself. Its perspectives may be handled sequentially, in parallel by subagents when appropriate, or by one agent using explicit review lenses. The main worker should integrate the findings, and the human product owner remains authoritative for product decisions.

Candidate inputs:

- Existing product notes or requirements draft.
- Known users and desired outcomes.
- Current architecture or policy constraints, when relevant.
- Open questions and prior decisions.

Candidate outputs:

- Updated product requirements.
- Explicit goals and non-goals.
- User journeys and acceptance criteria.
- Privacy, safety, and operational constraints.
- Resolved decisions and remaining open questions.
- A readiness assessment for formal specification.

Extraction criteria:

- Run the process manually on enough projects or requirements passes to identify a stable sequence.
- Separate generic workshop behavior from product-specific review roles and domain rules.
- Define how the skill resumes without repeating settled questions.
- Define compact handoffs for any panel work delegated to subagents.
- Add a small fixture set that demonstrates incomplete, contradictory, and specification-ready requirements.

## Requirements Consistency Review

Proposed skill name: `requirements-consistency-review`

Purpose: inspect requirements and related documents for contradictions, harmful duplication, missing behavior, and drift from authoritative product decisions. This is a reusable bounded review that the requirements workshop may invoke during its review phase.

Trigger: a requirements milestone, a substantial requirements revision, or preparation for formal specification.

Candidate workflow:

1. Identify the baseline, authoritative decisions, document roles, and release boundary.
2. Compare requirements with acceptance criteria, schemas, workflows, overview, and agent entry-point guidance.
3. Distinguish contradictions, known unresolved gaps, unspecified lifecycle behavior, and intentional repetition.
4. Test interactions with a small number of synthetic boundary scenarios.
5. Return prioritized findings with paired evidence, consequence, confidence, and a concrete question or correction.
6. Preserve accepted decisions; propose product choices for human resolution.

Review dimensions include actor permissions, child/category cardinality, date uncertainty, state transitions, failure behavior, source-rule changes, and evidence/retention boundaries. Adapt these dimensions to the product rather than requiring email-specific concepts everywhere.

Outputs: a concise review record, scenario candidates, and proposed reconciliation actions. Treat acknowledged schema proposals as incomplete contracts rather than implementation bugs. Do not equate document length with quality or automatically remove repeated acceptance criteria.

Development status: the first manual trial is recorded in `experiments/requirements-workshop/v0-trial-notes.md`. Follow-up evidence, the reusable V0 prompt, and the first small synthetic evaluation are in [the review experiment](../experiments/requirements-consistency-review/README.md). That evaluation exercises contradiction detection, a consistent control, and handling of an acknowledged open question; hidden-gap discovery and broader trials remain pending. Deterministic link and formatting checks should remain scripts; agents should handle semantic comparison.
