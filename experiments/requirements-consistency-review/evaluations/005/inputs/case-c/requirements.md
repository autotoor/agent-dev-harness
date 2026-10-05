# Community Lending Member View

## Authority And Scope

This document and recorded owner decisions govern the synthetic first release. Members may view only their own reservations and loans; staff may view all records. The release includes a member loan view after checkout and return. It does not yet specify the minimum information that view must expose.

## Loan Contract

Staff checkout creates an outstanding loan with a due date, and staff return changes it to returned. Both successful transitions update the member view. Stored data includes status, due date, and return time. The existence of a data field does not require displaying it. This case does not ask for a review of loan eligibility, timing, or persistence mechanisms.

## Optional Presentation

A separately styled overdue badge is an optional presentation idea for mock review, not an accepted first-release requirement. Absence of that badge does not change the loan's due date or prevent returns. Exact visual styling and any badge inclusion will be considered after agreeing on the minimum loan information.

## Release Boundary And Work Sequence

Waitlists and notifications are deferred. Staff checkout/return state transitions and storage work can proceed separately from the final member view. No member-view implementation has been completed.
