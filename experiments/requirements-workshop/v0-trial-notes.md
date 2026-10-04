# Requirements Workshop: Version 0 Trial Notes

Reviewed: 2026-10-04

Prompt: [`v0-prompt.md`](./v0-prompt.md)

Product checkpoint: [requirements-workshop-v0](https://github.com/kid-scheduler/school-email-assistant/tree/requirements-workshop-v0), commit `f35d4a62bfc472c2efc33f150f73d996cb6d781e`. The checkpoint is merged into product main and retained as an annotated tag and stage branch.

## Observed Results

- The task read existing product documentation, identified conflicting release boundaries, and asked focused questions.
- It established a digest-first, one-inbox pilot and separated mailbox authorization from household viewing.
- It identified role-specific event times and preserved source specificity separately from interpretation uncertainty.
- It updated repository documents as answers arrived and adapted to qualitative pilot criteria when the owner could not supply a numeric time baseline.

## Process Weaknesses

- Orient had entry questions but no completion test or required transition checkpoint. Work expanded into authentication and detailed display rules.
- The task reopened a history-window decision; the owner asked it to check prior documentation, and it acknowledged the unnecessary question.
- Frequent updates repeated detailed behavior across requirements, overview, and current-state files.
- Owner approvals authorized decisions, but the process initially did not clearly distinguish an essential release requirement from an accepted, tunable default. The checkpoint later introduced that distinction.
- The public checkpoint generalized personal discovery evidence. Public-safe recording should be built into the prompt from the start.
- Preservation weakened an earlier product-owner stack direction into an unselected proposal. Decision reconciliation must use authoritative human instructions as well as repository text.

## Output Review

The product review records concrete contract gaps: undated digest items versus date-rejecting workflow validation; multiple-child assignments versus single-child schema fields; and undefined lifecycle or precedence when approval rules change or review items age out. Some schema/workflow gaps were already acknowledged in the checkpoint, and should be described as unresolved reconciliation rather than surprise discoveries.

See the product repository's `docs/product/requirements-workshop-v0-review.md` for evidence and proposed next actions. Product-specific resolutions stay there.

## Proposed Next Prompt Changes

- Explicit phase exit criteria and a summary checkpoint before advancing.
- Search settled decisions before asking new questions.
- Preserve human-approved direction and record any proposed change explicitly.
- Distinguish requirements, trial defaults, hypotheses, and unresolved decisions.
- Keep top-level state concise and link to authoritative behavioral details.
- Add a bounded consistency review before formal specification.

Version 0 remains unchanged. Version 1 has not yet been created or tested. A separate proposed review skill can be trialed independently and later invoked during the workshop's review phase.
