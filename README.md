# Agent Dev Harness

Agent Dev Harness is a reusable development harness for AI-assisted software projects. It captures the working system around an agent: task contracts, project context, quality gates, evaluation loops, handoff files, recovery practices, and reusable templates.

The harness is intentionally generic. Product-specific fixtures, domain rules, and acceptance tests should live in the product repository that uses the harness.

## Goals

- Make long-running agentic development easier to inspect, resume, and improve.
- Turn repeated mistakes into durable guidance, checks, or templates.
- Separate feedforward guidance from feedback sensors.
- Support deterministic checks before inferential review.
- Provide reusable project adapters without imposing one product architecture.

## Initial Structure

- [docs/principles.md](./docs/principles.md): working principles for the harness.
- [docs/repository-contract.md](./docs/repository-contract.md): how a project repo can adopt the harness.
- [templates/task-contract.md](./templates/task-contract.md): reusable task framing template.
- [templates/architecture-decision.md](./templates/architecture-decision.md): lightweight ADR template.
- [templates/project-handoff.md](./templates/project-handoff.md): context handoff template.

## Non-Goals

- Storing product-specific fixtures.
- Replacing a project repo's tests, linters, or build system.
- Encoding assumptions about a single stack, framework, or product.
