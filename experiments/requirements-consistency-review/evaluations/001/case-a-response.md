## Scope And Authority

Reviewed `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md` only. Requirements and recorded owner decisions govern first-release behavior; workflow and model are proposals, not implemented behavior. No repository guidance was supplied.

Document roles: requirements define behavior and acceptance criteria; owner decisions record accepted direction and unresolved choices; workflow describes proposed intake; model describes proposed concepts. No historical checkpoint or implemented current-state document was supplied.

## Findings

**F1 · High · Contract contradiction: Intake rejects valid undated requests**

- **Evidence:** `requirements.md` → Request Coverage and Acceptance Criteria permit submission without a deadline and require active-list visibility during the seven-day window. `owner-decisions.md` → Recorded Owner Decisions confirms these requests must not be discarded. `workflow.md` → Proposed Intake Workflow requires a due date to save and rejects undated requests.
- **Consequence:** The proposed intake prevents a required first-release request type from ever reaching the list.
- **Boundary scenario:** An authorized member submits a request without a due date. Confirmed required outcome: accept it, explicitly indicate no deadline, and retain it in the active list for its applicable window. The workflow instead rejects it.
- **Confidence:** High.
- **Supported correction:** Align the proposed workflow with optional due dates; do not synthesize a deadline.

**F2 · High · Cardinality contradiction: Model cannot represent multiple assignees**

- **Evidence:** `requirements.md` → Assignments and Acceptance Criteria require multiple assignees sharing one request. `owner-decisions.md` → Recorded Owner Decisions confirms that direction. `model.md` → Proposed Conceptual Model explicitly makes exactly one `assigneeId` the complete assignment representation, excluding a collection or relationship.
- **Consequence:** The proposed model cannot express required assignment behavior. Duplicating requests to accommodate assignees would also conflict with shared identity and single-update semantics.
- **Boundary scenario:** One request belongs to two members. Confirmed required outcome: one team-view request, visibility in both member views, and an update changing that shared request once.
- **Confidence:** High.
- **Supported correction:** Revise the conceptual assignment representation to support several assignees per shared request. Existing decisions do not prescribe a database or persistence design.

## Acknowledged Open Interaction

Pending-review aging remains explicitly undecided, so it is **not a new defect**.

`requirements.md` → Aging And Review defines active-list expiry and a pending-status queue without approve/reject controls. `owner-decisions.md` → Recorded Owner Decisions explicitly leaves queue aging unresolved.

For an undated request submitted October 1, October 1–7 are its seven active-list calendar dates; it leaves that list on October 8. If it also needs approval, its pending-review visibility on October 8 is unconfirmed. The focused owner question is: **Should pending-review visibility continue independently of active-list expiry, follow that expiry, or use another rule?**

Calendar export is deferred, post-team-deletion retention is explicitly open, and acceptance-criterion repetition usefully reinforces behavior. None is reported as a defect.

## Checks And Next Step

No tools, deterministic checks, filesystem inspection, edits, or implementation tests were performed, as requested.

Recommended next step: authorize correction of the two proposed descriptions to match settled decisions. Resolve queue aging separately when ready.

1. Authorize documentation corrections for F1 and F2 only.
2. Record a pending-review aging decision before authorizing corrections.
3. Provide a custom next step or queue-aging rule.
