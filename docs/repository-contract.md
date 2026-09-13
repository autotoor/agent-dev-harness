# Repository Contract

A project can adopt this harness by adding a small local configuration layer that explains how the generic harness applies to that project.

Recommended project-local files:

```text
AGENTS.md
.harness/
  project.md
  architecture.md
  code-style.md
  quality-gates.md
  workflows.md
docs/
  product/
  architecture/
  decisions/
  implementation/
```

## `AGENTS.md`

The product repository should have an `AGENTS.md` file at its root. This is the first file an agent should read before making changes.

`AGENTS.md` should use progressive disclosure:

- Start with the shortest useful orientation.
- State the most important rules directly.
- Link to deeper `.harness/` documents for details.
- Avoid duplicating long guidance in multiple places.
- Keep project-specific practices in the product repository.

Recommended sections:

- Project purpose
- Current operating mode
- Code style essentials
- Architecture essentials
- Testing and quality gates
- Safety/privacy constraints
- Links to deeper harness docs

## `.harness/project.md`

Describes the project goal, audience, domain constraints, privacy rules, and important repositories or services.

## `.harness/architecture.md`

Describes architectural boundaries, approved patterns, module ownership, data-flow rules, and important design decisions.

## `.harness/code-style.md`

Describes language, formatting, naming, API, error-handling, and documentation practices that are too detailed for `AGENTS.md`.

## `.harness/quality-gates.md`

Lists commands and checks that should run before work is considered complete.

Examples:

- Format
- Lint
- Typecheck
- Unit tests
- Integration tests
- Fixture replay

## `.harness/workflows.md`

Describes how common work should proceed.

Examples:

- Add a feature
- Fix a bug
- Add a fixture
- Update documentation
- Prepare a release

## Product Documentation

Product repositories should maintain up-to-date documentation beyond OpenSpec when it helps future humans and agents understand the system.

OpenSpec is useful for proposed changes, behavior specs, design notes, and task lists. Additional documentation should capture durable product and implementation knowledge that remains true across many changes.

Recommended documentation areas:

```text
docs/
  product/
    overview.md
    requirements.md
    user-journeys.md
  architecture/
    overview.md
    data-model.md
    workflows.md
  decisions/
    0001-example-decision.md
  implementation/
    current-state.md
    operations.md
```

## Decision Log

Key decisions should be recorded when they materially affect product behavior, architecture, dependencies, safety, data handling, or development workflow.

Decision records should explain:

- Context
- Decision
- Consequences
- Alternatives considered
- Date/status

Use the architecture decision template when the decision is architectural. Use lighter notes for smaller product or implementation decisions.

## Contract Rule

The harness should not require product-specific material to live in the harness repository. The project repository remains the source of truth for its domain.
