## Findings

No direct contradictions found. Two user-facing outcomes remain unspecified.

### SC-01 · Medium · Missing Cardinality Decision
**Evidence:** `requirements.md` → Requirements says an active member reserves “one available tool.” `model.md` → Model limits each tool to one confirmed reservation or outstanding loan, but gives no member-level limit.

**Boundary scenario:** An active member has a confirmed reservation for tool A and attempts to reserve available tool B.

- **Confirmed:** Each reservation concerns one tool, and neither tool may be allocated twice.
- **Unspecified:** Whether a member may hold multiple reservations or reserve while already borrowing another tool.

**Consequence:** The documents support different interpretations of which reservation requests are valid.

**Confidence:** High that member-level cardinality is unspecified; medium that “one” was intended as a limit.

**Owner question:** Does “one available tool” mean one tool per reservation, or a member-level allocation limit? If a limit applies, do confirmed reservations and outstanding loans count together?

### SC-02 · Low · Missing Member-View Decision
**Evidence:** `requirements.md` → Requirements grants members access to their own records and names reservation status, pickup deadline, and cancellation reason as visible information. `workflow.md` → Workflow establishes loan due dates; `model.md` → Model defines loan status, return timestamps, and derived overdue status.

**Boundary scenario:** A reservation is checked out, then its outstanding loan reaches `due_at`.

- **Confirmed:** Checkout creates a loan, updates the member view immediately, and overdue status becomes true at `now >= due_at`. Returns remain permitted.
- **Unspecified:** Which loan information the member sees, including the due date and any overdue indication.

**Consequence:** Access to loan records is settled, but their visible content is insufficiently defined to establish the member experience.

**Confidence:** Medium. “View their own records” might intend access to all modeled fields, but that interpretation is not explicit.

**Owner question:** Must members see loan status and due date, and must the view explicitly indicate overdue status?

## Consistency Checks

The supplied decisions resolve these interactions:

- **Checkout exactly at the pickup deadline:** The reservation expires before action evaluation. Checkout fails without creating a loan.
- **Suspension exactly at the pickup deadline:** Expiration runs first. The expired reservation remains terminal; suspension cancels only remaining confirmed reservations with `account_suspended`.
- **Reinstatement after suspension:** Reservation and checkout permissions return. Canceled reservations remain terminal.
- **Suspension during an outstanding loan:** Its due date remains unchanged, and staff may record its return.

Waitlists, fees, renewals, and manual staff overrides are explicitly outside the release. Locking versus compare-and-swap is an acknowledged implementation choice, not a semantic defect.

## Scope And Limits

Reviewed only `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md`, using headings as citation identifiers. Requirements establish behavior and release scope; workflow establishes transitions and failure outcomes; model establishes states, timing, and exclusivity; owner decisions settle authority and exclusions. No historical checkpoint, separate acceptance criteria, implementation evidence, or repository guidance was supplied.

No tools, deterministic scripts, edits, or implementation tests were run, as requested.

## Recommended Next Step

Resolve SC-01 first, then clarify SC-02 if member-view acceptance coverage is needed. Select:

1. Answer the member-level allocation question.
2. Answer both allocation and loan-visibility questions.
3. Provide a custom response or explain which existing wording already settles either finding.
