The supplied documents are consistent on transition precedence and staff/member permissions. Two user-facing decisions remain unspecified; neither is a contradiction.

### Scope And Authority

Reviewed `requirements.md` → **Requirements**, `workflow.md` → **Workflow**, `model.md` → **Model**, and `owner-decisions.md` → **Owner Decisions**.

Requirements define behavior and visibility; workflow defines actions and failures; model defines states, timing, and allocation constraints; owner decisions record approved permissions, exclusions, and an open implementation choice. No repository guidance, separate acceptance criteria, historical checkpoint, or implementation evidence was supplied.

This was a read-only semantic review. Per your evaluation constraints, no tools, deterministic checks, or implementation tests were run.

### Findings

**R1 · P2 · Missing Product Decision: Member Allocation Limit**

- **Paired evidence:** `requirements.md` → **Requirements** says an active member reserves “one available tool.” `model.md` → **Model** limits allocation per tool but gives no limit per member.
- **Boundary scenario:** An active member already has a confirmed reservation for tool A and attempts to reserve available tool B.
- **Confirmed:** Each reservation concerns one tool; tool B cannot have a competing confirmed reservation or outstanding loan.
- **Unspecified:** Whether the member’s existing reservation or loan prevents another reservation.
- **Consequence:** The documents support exclusive allocation but do not establish whether a member can hold multiple allocations across different tools.
- **Confidence:** Medium. “One” may describe each reservation rather than a member-wide limit.
- **Owner question:** Does “one available tool” mean one tool per reservation, with no member-wide cap, or a cap on simultaneous allocations? If capped, do confirmed reservations and outstanding loans count together?

**R2 · P2 · Missing Product Decision: Member-Visible Loan Information**

- **Paired evidence:** `requirements.md` → **Requirements** grants members access to their own records and specifies reservation display fields. `model.md` → **Model** defines loan status, due date, return time, and derived overdue state; `workflow.md` → **Workflow** defines checkout and return transitions.
- **Boundary scenario:** A member’s loan reaches its due date, then staff record its return.
- **Confirmed:** At `now >= due_at`, an outstanding loan is overdue; returns remain allowed. Return closes the loan, releases the tool, and updates the member view immediately after commit.
- **Unspecified:** Which loan information members see, including whether overdue is displayed and whether its appearance must update when the due date passes.
- **Consequence:** Own-record access and immediate updates do not establish the visible loan contract.
- **Confidence:** High that loan presentation is unspecified; no contradiction is asserted.
- **Owner question:** Which loan fields must members see: due date, outstanding/returned status, overdue indication, and return time? If overdue is shown, when must that indication refresh?

### Settled Boundary Behavior

At the exact pickup deadline, checkout is invalid: expiration happens before action evaluation, and checkout requires `now < pickup_deadline`. If suspension commits at that boundary, the reservation has already expired; suspension cancels only remaining confirmed reservations. Reinstatement restores permissions without reviving terminal reservations. These outcomes follow from **Model**, **Workflow**, and **Owner Decisions**.

The locking-versus-compare-and-swap choice is explicitly open. Waitlists, notifications, fees, renewals, and manual staff overrides are explicitly excluded or deferred, so they are not findings.

### Recommended Next Step

Clarify the two user-facing contracts before changing documentation. Select:

1. Address R1: state the member allocation limit and what counts toward it.
2. Address R2: state required loan display fields and overdue refresh behavior.
3. Address both.
4. Provide a custom response, including an explicit decision to defer either question.
