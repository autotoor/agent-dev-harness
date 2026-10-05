# Fixture Author Instructions

The author received this message with no parent history, no tools, and no review prompt or prior results. The fixture was then clarified by the parent before freezing; see run record for those changes.

```text
Prepare a small synthetic semantic requirements-review fixture in a domain other than school email, calendars, or team request lists. Do not use tools or inspect files. You have no access to the review prompt, prior outputs, or tuning examples; do not try to infer them. Return one JSON object only with keys domain, seededDocuments, controlDocuments, expectedFinding, limitations. Each documents value maps requirements.md, workflow.md, model.md, owner-decisions.md to complete short Markdown strings.

Use the same four documents in a seeded case and a resolved control; the control should differ only in the clause(s) needed to resolve one unstated user-visible lifecycle interaction. Do not explicitly label that interaction as an open question in the seeded documents. The reviewer must be able to infer the missing observable rule by comparing stated behavior. Avoid planting literal contradictions. Specify the other relevant actors, permissions, states, time basis, transitions, and failure behavior so the negative control is genuinely useful within a small first-release scope. Include one intentionally deferred capability and one acknowledged open implementation choice; neither should be a defect. No private data or credentials.

expectedFinding should contain id, evidence, boundaryScenario, supportedOutcomes, unspecifiedOutcome, appropriateOwnerQuestion, and controlResolution. A separate limitations string should disclose any remaining ambiguity. Do not invent outputs from a reviewer or test. This is fixture authoring only, not grading. Keep all documents together under about 1000 words.
```
