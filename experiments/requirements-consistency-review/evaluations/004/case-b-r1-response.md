## Scope and Authority

Reviewed `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md` only. Requirements and recorded owner decisions are authoritative; workflow describes operations, and model describes states, timing, and allocation constraints. No separate acceptance criteria, repository guidance, historical checkpoint, or implementation evidence was supplied.

The release excludes email, fees, renewals, manual staff reservation overrides, and waitlists. The locking versus compare-and-swap choice is explicitly open and is not a defect. No tools or deterministic checks were run, as requested.

## Finding

**SC-01 | P2 | Missing lifecycle decision: suspension of an existing reservation**

- **Evidence:** `requirements.md` → Requirements prohibits suspended members from reserving or checking out and explicitly preserves existing loan due dates. `workflow.md` → Workflow permits suspension at any time but does not specify its effect on an existing confirmed reservation. `model.md` → Model makes confirmed reservations exclusive holds. `owner-decisions.md` → Owner Decisions prohibits manual staff reservation overrides.
- **Consequence:** A member suspended after reserving cannot collect the tool. Whether suspension preserves or automatically terminates that reservation determines whether the member continues to see a confirmed reservation and whether another member can reserve the tool.
- **Confidence:** High that no suspension-triggered reservation transition is explicitly documented; medium that this represents an omitted decision rather than intended preservation.
- **Owner question:** Does suspension leave existing confirmed reservations holding their tools until member cancellation or deadline expiration, or should suspension trigger a specified automatic transition? Manual staff cancellation remains excluded by the recorded decision.

No direct contradictions were found.

## Boundary Scenarios

| Scenario | Supported outcome | Unspecified outcome |
|---|---|---|
| A member is suspended while holding a confirmed reservation. | Checkout is prohibited. The member retains access to their records. Ordinary cancellation remains available to the owning member because its permission is not restricted to active members. | Whether suspension itself changes the reservation or releases its tool: **SC-01**. |
| Checkout commits exactly at the pickup deadline. | Expiration runs first; checkout fails because it requires `now < pickup_deadline`. The reservation releases the tool. | None identified. |
| Suspension and checkout occur concurrently. | Serialization determines their order. Suspension first prevents checkout; checkout first creates a loan whose due date survives subsequent suspension. | None at the product level; the serialization mechanism is an acknowledged implementation choice. |
| A suspended member returns an overdue loan. | Return is permitted, staff records it, the loan closes, and the tool becomes available. Overdue status does not block return. | None identified. |

These are documentation judgments, not implementation test results.

## Recommended Next Step

Resolve SC-01 before making documentation changes. The owner can select:

1. Confirm that suspension preserves existing confirmed reservations until member cancellation or expiration.
2. Specify an automatic suspension-triggered transition, including the resulting status, tool release, and member-visible reason.
3. Provide a custom lifecycle rule.

Options 2 and 3 require a new explicit owner decision; this review does not authorize either.
