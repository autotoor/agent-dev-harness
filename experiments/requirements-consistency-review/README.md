# Requirements Consistency Review Experiment

This experiment develops a bounded semantic review before extracting the proposed `requirements-consistency-review` skill. It is separate from the requirements workshop prompt: a reconciliation pass numbered V1 does not mean the workshop prompt has reached V1.

## Artifacts

- [v0-prompt.md](./v0-prompt.md): initial reusable prompt, unchanged; exercised with a controlled wrapper in evaluation 001.
- [v1-prompt.md](./v1-prompt.md): candidate addition about unspecified user-visible boundary outcomes; evaluated separately from V0.
- [manual-trial-notes.md](./manual-trial-notes.md): evidence from the manual reviews that motivated the prompt, not results from running it.
- [evaluation-plan.md](./evaluation-plan.md): agreed plan; the first small read-only test is complete, while simulated-owner replay remains pending.
- [improvement-loop.md](./improvement-loop.md): iteration records, comparisons, stopping rules, and commit/tag checkpoints.
- [evaluation 001](./evaluations/001/README.md): small synthetic review cases and evaluator-only rubric; see its run record for execution status.
- [evaluation 002](./evaluations/002/README.md): an unstated lifecycle interaction and internally consistent documents that drift from human-approved direction; see its run record for status.
- [evaluation 003](./evaluations/003/README.md): bounded repeated comparison of V0/V1 on fixed development cases and a consistent control; see its run record for results.
- [evaluation 004](./evaluations/004/README.md): unchanged V1 on a sharper request control and a newly authored lending case/control; see its run record for status.
- [prioritization-test-plan.md](./prioritization-test-plan.md): preserved design for the separate classification task; its six-response batch is complete.
- [evaluation 005](./evaluations/005/README.md): fourteen scored units across six responses matched the classification rubric; raw evidence and limits are recorded. Parent grading is not independent validation or improvement evidence for V1.

Keep product decisions, review records, and domain-specific scenarios in the product repository. This experiment owns generic instructions and evaluation observations only.

## Next Trial

Run the prompt against a fixed baseline in read-only mode. Record the baseline, input document roles, findings, false positives, missed seeded issues, and whether decisions were preserved. Test synthetic document sets with:

1. A contradiction between a requirement and a workflow.
2. A lifecycle boundary left unspecified.
3. A consistent requirement repeated usefully as an acceptance criterion.
4. An explicitly deferred capability and a known open decision.
5. Internally consistent documents that contradict supplied human-approved direction.

Evaluation 001 supplies small generic fixtures for contradictions, useful repetition, a deferred feature, and acknowledged uncertainty. Its aging case was explicitly identified as undecided, so evaluation 002 adds an unstated lifecycle interaction and documents drifting from supplied human decisions. Run records distinguish prepared inputs from completed results. Actual product fixtures remain in their product repository.

Do not package a skill until trials demonstrate useful findings without treating every open question or repeated sentence as a defect. Preserve used prompt versions unchanged and create new versions for material revisions.
