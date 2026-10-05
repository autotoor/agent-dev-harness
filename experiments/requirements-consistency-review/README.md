# Requirements Consistency Review Experiment

This experiment develops a bounded semantic review before extracting the proposed `requirements-consistency-review` skill. It is separate from the requirements workshop prompt: a reconciliation pass numbered V1 does not mean the workshop prompt has reached V1.

## Artifacts

- [v0-prompt.md](./v0-prompt.md): initial reusable prompt, not yet trialed as written.
- [manual-trial-notes.md](./manual-trial-notes.md): evidence from the manual reviews that motivated the prompt, not results from running it.
- [evaluation-plan.md](./evaluation-plan.md): agreed plan for read-only review tests followed by simulated-owner conversation replay; not yet executed.

Keep product decisions, review records, and domain-specific scenarios in the product repository. This experiment owns generic instructions and evaluation observations only.

## Next Trial

Run the prompt against a fixed baseline in read-only mode. Record the baseline, input document roles, findings, false positives, missed seeded issues, and whether decisions were preserved. Test synthetic document sets with:

1. A contradiction between a requirement and a workflow.
2. A lifecycle boundary left unspecified.
3. A consistent requirement repeated usefully as an acceptance criterion.
4. An explicitly deferred capability and a known open decision.
5. Internally consistent documents that contradict supplied human-approved direction.

These are planned evaluation cases, not existing fixtures or completed tests. Small synthetic generic test documents can live here; actual product fixtures remain in their product repository.

Do not package a skill until trials demonstrate useful findings without treating every open question or repeated sentence as a defect. Preserve used prompt versions unchanged and create new versions for material revisions.
