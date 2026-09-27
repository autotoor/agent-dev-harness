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
