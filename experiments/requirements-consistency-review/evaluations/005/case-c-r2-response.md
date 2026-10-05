## F-01: Minimum Visible Loan Information

**Blocking decision for member-view implementation only.** The promised view and the absence of selected minimum information are explicit. Stored status, due date, and return time do not establish display requirements. The owner has already assigned this selection to the UI specification stage. Sources: `requirements.md` — Authority And Scope, Loan Contract; `owner-decisions.md` — Promised Member Surface.

What remains unspecified is which information members must see after checkout and return. Without that selection, the final member view lacks an agreed content contract. This is a planned prerequisite, not evidence of an implementation defect.

Smallest owner/design question: **What minimum loan information must the member view show after checkout and after return?**

Confidence that the information is unspecified: **high**. Confidence in urgency: **high before member-view implementation**, but no evidence that it must be resolved immediately. UI specification work and staff transition/storage work can continue.

## F-01: Separate Overdue Badge And Styling

**Useful clarification for mock review; unsupported as a prerequisite to all work.** Both authority documents settle that the badge is optional. Its inclusion and styling remain open, but are expressly scheduled for consideration after minimum loan information is agreed. Sources: `requirements.md` — Optional Presentation; `owner-decisions.md` — Presentation And Deferred Capabilities.

The consequence is limited to presentation specification and mock review. The candidate’s demand to decide the badge before work proceeds overstates its urgency.

Smallest design question, at mock review: **Should the loan-view mock include a separate overdue badge?** Styling can be considered if inclusion is selected.

Confidence that presentation details remain unspecified: **high**. Confidence that they block current work: **low**, given the explicit sequence and optional status. Minimum-content specification and staff transition/storage work can continue.

## F-02: Waitlist

**Unsupported finding.** Waitlists are explicitly deferred, and the owner explicitly says they are not required before delivering either the loan view or state transitions. Sources: `requirements.md` — Release Boundary And Work Sequence; `owner-decisions.md` — Presentation And Deferred Capabilities.

The proposed experience improvement supplies no concrete first-release defect. No waitlist policy question is needed for this release, and no in-scope implementation step is blocked. Confidence in this classification: **high**.

## Recommended Next Step

Resolve minimum visible loan information during the planned UI specification stage, before implementing the member surface. Keep badge consideration at mock review and retain the recorded waitlist deferral.

1. Select minimum loan information with the owner as part of UI specification.
2. Continue staff checkout/return transitions and storage work while that selection is pending.
3. After minimum information is agreed, review the optional badge in mocks.
