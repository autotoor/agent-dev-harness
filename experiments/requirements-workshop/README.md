# Requirements Workshop Experiment

This directory records the evolution of the proposed `requirements-workshop` skill before it is extracted into a reusable skill.

The experiment separates generic harness artifacts from product-specific workshop state:

- Keep reusable prompt versions and generic evaluation notes here.
- Keep product answers, decisions, open questions, and requirements changes in the product repository.
- Use synthetic excerpts if an example is needed in this public harness repository.

## Versioning

Create a new prompt version only when the reusable instructions materially change. Do not overwrite an earlier version after it has been used.

For each trial, record:

- Prompt version.
- Product and workshop phase, without private product data.
- What the prompt helped produce.
- Questions that were vague, repetitive, premature, or missing.
- Places where the agent assumed a decision instead of asking.
- Changes proposed for the next prompt version.

Git history should preserve the exact prompt and the evidence that motivated each revision. A future skill should emerge from repeated observations rather than being designed entirely in advance.

## Current Artifacts

- [`v0-prompt.md`](./v0-prompt.md): deliberately simple, untested starting prompt.
- [`trial-notes-template.md`](./trial-notes-template.md): public-safe structure for recording what a trial taught us.
