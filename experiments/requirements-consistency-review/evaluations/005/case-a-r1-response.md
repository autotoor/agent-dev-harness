## F-01: Edit Actor Rule

**Classification: blocking decision for edit controls and write endpoints.**

Settled: web and API editing are promised; all current members can read requests; equal read access does not grant write access. Validity, shared updates, and failure preservation are specified. Unauthenticated and nonmember access must be rejected. ([requirements.md, Authority And Release; Reading And Identity; Editing]; [owner-decisions.md, Accepted Scope])

Unspecified: which current members may edit a particular request. The proposed scenario therefore has no defined authorization outcome. This decision is needed before implementing authorization for either editing interface. It does not block the entire release’s development: read-only lists, date rendering, and shared request storage can proceed separately. ([requirements.md, Work Sequence])

**Confidence:** high that the actor rule is missing; high that it blocks editing authorization; no support for treating it as an immediate blocker to read-only work. No production editing endpoint exists yet. ([requirements.md, Work Sequence])

**Smallest owner question:** Which current members are authorized to edit a particular request?

## F-02: Calendar Export

**Classification: unsupported finding.**

Settled: calendar export is explicitly outside the first release and intentionally deferred. Its potential usefulness does not establish a missing release requirement or a reason to halt development. The read-only list remains useful without it. ([requirements.md, Release Boundary]; [owner-decisions.md, Deferred Work])

Unspecified: future export design. That omission has no concrete first-release consequence and requires no owner question for this assessment.

**Affected implementation step:** none in the first release. Continue the planned work without adding export.

**Confidence:** high that future design is unspecified; high that this creates no first-release urgency.

## Recommended Next Step

Resolve the edit actor rule before building editing authorization. Continue the independently specified work; retain the recorded export deferral.

1. Record the owner’s edit-authority decision now, then proceed with web and API editing.
2. Proceed with read-only lists, date rendering, and shared storage while the edit-authority decision remains pending.
