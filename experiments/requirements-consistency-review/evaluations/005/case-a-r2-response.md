### F-01: Edit Actor Rule

**Classification: blocking decision for edit authorization.**

Settled: web and API editing are promised; valid authorized edits must update the shared request, while invalid edits and failed writes preserve it. Unauthenticated and nonmember access is rejected. Equal read access does not grant write access. ([requirements.md], **Authority And Release**, **Editing**; [owner-decisions.md], **Accepted Scope**.)

Unspecified: which current members may edit a particular request. The scenario therefore has a concrete unresolved consequence: the web controls and API cannot determine whether to permit that member’s edit.

Affected step: implementing authorization for edit controls and write endpoints. This does **not** block all development: read-only lists, date rendering, and shared request storage can continue. ([requirements.md], **Work Sequence**.)

Confidence that the rule is missing: **high**. Confidence in urgency: **high before edit authorization is built**, but no immediate production exposure is established because no production editing endpoint exists.

Smallest owner question: **Which current members may edit a request through the web interface and API?**

### F-02: Calendar Export

**Classification: unsupported finding.**

Settled: calendar export is explicitly outside the first release and intentionally deferred; the owner also records that the read-only list remains useful without it. ([requirements.md], **Release Boundary**; [owner-decisions.md], **Deferred Work**.)

Unspecified: future export design. That omission has no concrete first-release consequence. The claim that export could help members does not establish a release requirement or justify blocking development.

Affected step: none in the authorized release. Confidence in the classification: **high**; confidence that this requires urgent clarification: **low**, because the scope decision is already recorded. No owner question is needed.

### Recommended Next Step

Resolve the edit actor rule before implementing edit authorization, while continuing the explicitly independent work. Keep calendar export deferred.

1. Record the owner’s answer to the edit actor question, then implement consistent web/API authorization.
2. Continue read-only lists, date rendering, and shared storage while that decision remains pending.
