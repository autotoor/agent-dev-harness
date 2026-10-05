# Evaluation 001: Synthetic Request Tracker

Prepared: 2026-10-04. Status: two read-only runs completed; raw responses and parent scoring are in the run record.

This is a small generic harness test, not a product fixture or an application implementation. Two cases use synthetic team-request documents. The reviewer receives one case and the unchanged V0 prompt, not the other case, rubric, answer key, or parent conversation.

## Files

- `inputs/case-a/`: one reviewer input bundle.
- `inputs/case-b/`: a separate reviewer input bundle.
- [rubric.md](./rubric.md): evaluator-only expected findings and scoring rules.
- [run-record.md](./run-record.md): frozen inputs, execution configuration, raw outputs, and scored observations.

## Procedure

Provide a case's documents inline to a fresh subagent with `fork_context: false`. Do not expose directory names identifying expected outcomes, the answer key, or previous reviewer responses. Instruct it not to use tools or read other files. This is input isolation by instruction and context, not a filesystem security boundary.

Use the same V0 prompt, wrapper, inherited model/settings, and allowed tools for both runs. The only wrapper difference is the supplied case's content. No edits, owner questions answered during the run, or coaching are allowed. Each agent returns one read-only review. The parent then scores the results using the prewritten rubric and records unexpected findings separately.

These tiny cases test basic detection and restraint, not cross-project generalization, simulated-owner behavior, or a speed improvement. No repeated runs or baseline prompt comparison are included in this first evaluation.
