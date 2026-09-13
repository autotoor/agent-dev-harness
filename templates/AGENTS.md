# AGENTS.md

This file is the entry point for AI agents and human contributors working in this repository. It should stay short and link to deeper guidance when detail is needed.

## Project Purpose

Describe what this project does, who it serves, and what outcome matters most.

## Current Operating Mode

State the current phase of work.

Examples:

- Requirements
- Specification
- UI mocks
- Implementation
- Hardening
- Release

## Essential Rules

- Keep changes scoped to the task.
- Preserve user-authored work.
- Update Markdown-tracked state when decisions, risks, or open questions change.
- Update product docs, architecture docs, and decision logs when implementation changes make them stale.
- Prefer deterministic checks before subjective review.
- Follow progressive disclosure: read deeper docs when the task needs them.

## Code Style Essentials

Summarize only the highest-priority style rules here.

For detailed guidance, see:

- `.harness/code-style.md`

## Architecture Essentials

Summarize only the most important architectural boundaries here.

For detailed guidance, see:

- `.harness/architecture.md`

## Quality Gates

Before considering work complete, run the checks listed in:

- `.harness/quality-gates.md`

If a check cannot run, record why in the handoff or final response.

## Workflows

Use the workflow guidance in:

- `.harness/workflows.md`

## Project State

Keep durable project state in Markdown files. This can include:

- Current goals
- Decisions
- Open questions
- Active specs
- Handoffs
- Risks
- Review notes

## Product And Architecture Docs

Keep durable product and implementation documentation current when meaningful changes land.

Recommended locations:

- `docs/product/`
- `docs/architecture/`
- `docs/decisions/`
- `docs/implementation/`

## Safety And Privacy

List project-specific data, privacy, security, or compliance rules here. Link to deeper details when needed.
