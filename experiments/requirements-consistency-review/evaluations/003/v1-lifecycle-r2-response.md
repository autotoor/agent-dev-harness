Found two missing product decisions that affect which requests users can see. The supplied documents otherwise agree on intake, shared assignments, and first-release scope.

### F1 — Pending Review After Aging
**Priority:** High · **Category:** Missing lifecycle decision · **Confidence:** High

**Evidence:** `requirements.md` → **Aging And Review** removes undated requests from the active list after seven calendar dates and places approval requests in a separate queue. `owner-decisions.md` → **Recorded Owner Decisions** confirms separate pending-review display and defers resolution controls.

**Boundary scenario:** An undated request is still pending approval on its eighth calendar date.

- **Confirmed:** Its ordinary active-list eligibility has ended. First-release owner-facing resolution controls are unavailable.
- **Unspecified:** Whether it remains visible in the pending-review queue or disappears from that queue too.

**Consequence:** Applying aging to both views could hide unresolved requests; exempting the queue could keep them visible indefinitely. Neither outcome is established by the recorded decisions.

**Owner question:** Does the seven-date aging rule affect only the ordinary active list, or also the pending-review queue? If it affects both, where, if anywhere, can users see an aged pending request?

### F2 — Dated Request Eligibility
**Priority:** Medium · **Category:** Missing time-boundary decision · **Confidence:** High

**Evidence:** `requirements.md` → **Request Coverage** and **Aging And Review** establish active-list treatment for undated requests only. `workflow.md` → **Proposed Intake Workflow** accepts dated requests and delegates display to the requirements’ eligibility rules, which do not define dated-request eligibility.

**Boundary scenario:** An ordinary request has a due date of October 4; the team opens the list on October 5.

- **Confirmed:** Intake accepts the dated request. Multiple assignees reference one shared request.
- **Unspecified:** Whether the request remains active as overdue, leaves the list, or appears elsewhere. Eligibility on the due date itself is also undefined.

**Consequence:** The proposed workflow cannot determine what users see when a dated request reaches or passes its deadline.

**Owner question:** What makes a dated request eligible for the active list, including on its due date and afterward?

### Scope And Limits
Reviewed only `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md`. Requirements and recorded owner decisions are authoritative. Acceptance criteria repeat useful behavioral checks; workflow and conceptual model are proposals, explicitly not implemented behavior. No repository guidance, overview, historical checkpoint, or separate current-state document was supplied.

No contradictions were found in accepting undated requests, preserving a shared request across assignees, displaying pending review separately, or deferring resolution controls and calendar export. Acknowledged retention and technology questions are not new defects.

No tools, deterministic scripts, or implementation tests were run, as instructed. Findings concern semantic coverage only.

### Recommended Next Step
Record the two visibility decisions before further specification work. Select:

1. Address F1: clarify pending-review visibility after aging.
2. Address F2: clarify dated-request active-list eligibility.
3. Address both together.
4. Provide a custom response or additional recorded decision.
