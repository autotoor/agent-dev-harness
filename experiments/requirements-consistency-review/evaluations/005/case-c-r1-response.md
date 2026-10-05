## F-01: Minimum Loan Information

**Classification: blocking decision for member-view implementation.** The promised surface and its timing are settled: members must see their own loans after checkout and return. Minimum visible information remains unspecified, and stored fields do not establish display requirements. The owner explicitly plans to select that information during UI specification. ([requirements.md, Authority And Scope / Loan Contract]; [owner-decisions.md, Promised Member Surface])

Without that selection, implementing the final member view would require inventing display policy. This blocks that particular implementation step, not all work.

**Confidence:** High that the information selection is missing; high that it is required before implementing the member surface. There is no evidence of immediate project-wide urgency or a completed implementation defect.

**Smallest owner question:** What minimum loan information must members see after checkout and after return?

Staff checkout/return transitions, storage work, and UI specification can continue. ([requirements.md, Release Boundary And Work Sequence])

## F-01: Overdue Badge Inclusion And Styling

**Classification: useful clarification during the planned mock review.** Badge inclusion and exact styling remain undecided, but its optional status and decision sequence are already settled: presentation review follows agreement on minimum loan information. ([requirements.md, Optional Presentation]; [owner-decisions.md, Presentation And Deferred Capabilities])

The affected step is mock review and any subsequent optional badge implementation. The candidate’s demand to decide badge presentation before any work proceeds is **unsupported**: neither the member-view promise nor state-transition work requires this badge.

**Confidence:** High that presentation choices remain open; high that they are not a release blocker.

**Smallest design question, at mock review:** Should the mock include a separate overdue badge, and, if included, what styling should it use?

Minimum-information selection, UI specification, state transitions, and storage work can continue.

## F-02: Waitlist

**Classification: unsupported finding.** Waitlists are explicitly deferred, and the owner explicitly says they must not be required before delivering the loan view or state transitions. A potential improvement to the lending experience does not establish an unresolved first-release requirement. ([requirements.md, Release Boundary And Work Sequence]; [owner-decisions.md, Presentation And Deferred Capabilities])

No in-scope implementation step is blocked, and no owner question is needed to resolve this finding.

**Confidence:** High that the release scope answers the claim; high that no first-release urgency is supported.

## Recommended Next Step

Resolve minimum visible loan information in the already planned owner/UI specification stage. Keep badge review in its recorded sequence and retain the waitlist deferral.

1. Select minimum loan information with the owner before implementing the member surface.
2. Continue independent checkout/return transitions and storage work.
3. Review optional badge presentation after the minimum information is agreed.
