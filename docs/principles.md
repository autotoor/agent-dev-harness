# Harness Principles

## Feedforward

Feedforward artifacts guide work before it starts:

- Project charters
- Task contracts
- Architecture decisions
- Coding standards
- Fixture policies
- Review rubrics

Good feedforward reduces ambiguity without freezing implementation details too early.

## Feedback

Feedback artifacts detect whether work is good enough:

- Tests
- Type checks
- Linters
- Build checks
- Fixture replay
- Evaluation scripts
- Human or model-assisted reviews

Prefer deterministic feedback first. Use inferential review for judgment-heavy questions that tests cannot fully answer.

## Prefer Scripts For Deterministic Tasks

Do not use an agent to complete a task that can easily and reliably be done by a script, formatter, linter, compiler, test runner, or other deterministic tool.

Use scripts for:

- Formatting.
- Linting.
- Type checking.
- Unit tests.
- Build checks.
- Static analysis.
- Fixture replay.
- Mechanical file generation.

Use agents for:

- Ambiguous product or architecture judgment.
- Translating requirements into implementation plans.
- Explaining tradeoffs.
- Reviewing failures and proposing fixes.
- Updating docs and decisions based on context.
- Creating or improving scripts when deterministic automation is missing.

The harness should make the scripted path easy to find and run. Agents should call those scripts, interpret their results, and update project state when needed.

## Context Durability

Long-running projects need durable context outside a single chat:

- Decisions should be written down.
- Project state should be inspectable.
- Open questions should be explicit.
- Handoffs should tell the next worker what changed, what was verified, and what remains risky.

## Markdown-Tracked State

Project state should be stored in plain Markdown files wherever practical:

- Current goals
- Decisions
- Open questions
- Active specs
- Quality gates
- Handoffs
- Review notes
- Known risks

Markdown makes state easy for humans, agents, Git, and future tooling to inspect. It should be treated as an operational source of truth, not only as retrospective documentation.

## Progressive Disclosure

The harness should reveal detail only when it is useful.

Top-level files should tell a worker where they are, what matters now, and where to go next. Deeper files can hold richer details, examples, rubrics, and edge cases. This keeps the harness usable for quick tasks while still supporting complex work.

Prefer:

- Short entry-point documents.
- Links to deeper guidance.
- Task-specific checklists.
- Templates that start simple and allow optional sections.
- Summaries that point to details rather than duplicating them everywhere.

Avoid making every task load the entire project history before useful work can begin.

## Offload Separable Work To Subagents

Use subagents to reduce main-thread context size when a task is separable and the main worker only needs the result, not every intermediate detail.

Choose whether to offload based on three axes:

- Separability: can the task be completed with a bounded context and clear output?
- Ability: does the subagent have the reasoning depth, tools, and domain context needed to do the task well?
- Cost: is the expected value worth the additional model/tool cost and coordination overhead?

Good subagent tasks:

- Focused research.
- Codebase inventory.
- Test failure triage.
- Requirements critique from a specific role.
- Fixture review.
- Drafting options for a contained decision.
- Comparing alternatives against a rubric.

Keep work in the main thread when:

- The task requires direct user collaboration.
- The work is highly coupled to active edits.
- The subagent would need broad, sensitive, or ambiguous context.
- The result must be continuously steered by the main worker.

Subagent outputs should be compact and actionable:

- Findings.
- Evidence or file references.
- Risks.
- Recommended next steps.
- Open questions.

Do not offload merely to avoid understanding the work. The main worker remains responsible for integrating the result and making final decisions.

Prefer cheaper or narrower agents for bounded tasks such as inventory, summarization, fixture review, or checklist-style critique. Use stronger agents for ambiguous architecture, product, safety, or debugging work where poor judgment would be expensive.

## Reusable Tasks Become Skills

If a small agentic task is reusable outside the current project or harness flow, package it as a skill rather than burying it inside one project's docs or scripts.

Good skill candidates have:

- A clear trigger.
- Repeatable steps.
- Reusable behavior across projects.
- Enough nuance that plain documentation is not sufficient.
- Likely future use independent of this harness.

Examples:

- Create a static HTML UI mock from requirements.
- Review requirements from a privacy or safety perspective.
- Convert diagram notes into an Excalidraw-ready structure.
- Generate an OpenSpec proposal from a product requirements document.
- Create synthetic fixture emails from a scenario.
- Review a blog post for public-safety leaks.
- Update product docs after implementation changes.

Do not turn every checklist into a skill too early. Start with Markdown guidance, observe repeated use, then extract a focused skill when the task proves reusable.

## Project Separation

The harness should provide reusable practices and templates. Product repositories should own:

- Domain fixtures
- Product requirements
- Stack-specific implementation
- Real acceptance tests
- Sensitive or private context

## Improvement Loop

When an agent or human repeats a mistake, update the harness:

- Add a checklist item.
- Add a quality gate.
- Improve a template.
- Write a short decision record.
- Capture a better example.
