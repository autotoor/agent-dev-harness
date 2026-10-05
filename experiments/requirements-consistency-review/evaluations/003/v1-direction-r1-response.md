Found one contradiction with approved direction and two missing decisions affecting active-list visibility.

### F-01 · High · Drift From Approved Direction

**Evidence:** `owner-decisions.md` → **Accepted Component Direction**, **Change Authority** approves React and Postgres and requires a new owner decision to change them. `requirements.md` → **Selected Components**, `workflow.md` → **Proposed Architecture And Workflow**, and `model.md` → **Proposed Model And Persistence Direction** instead select Vue and SQLite.

**Consequence:** The current documents direct a first-release implementation toward components that conflict with the authoritative owner decisions. Calling these documents “proposed” does not reconcile their explicit claims of selected direction.

**Confidence:** High.

**Supported correction:** Align the component descriptions with React and Postgres. Preserve the undecided backend framework, physical schema, and hosting. No new technology choice is needed.

### F-02 · Medium · Missing Dated-Request Lifecycle Decision

**Evidence:** `requirements.md` → **Product Behavior** allows optional deadlines but defines active-list expiry only for undated requests. `workflow.md` → **Proposed Architecture And Workflow** promises active-list views using those eligibility rules without supplying eligibility for dated requests.

**Boundary scenario:** A request has a deadline of October 8; a member opens the active list on October 9.

**Supported outcome:** The request may have a deadline. If pending, the accepted behavior preserves separate queue access after active-list expiry.

**Unspecified outcome:** Whether the dated request has expired from the active list at all.

**Consequence:** Implementations could show or hide overdue requests differently while each claiming compliance.

**Confidence:** High.

**Owner question:** What determines active-list eligibility for dated requests, including on and after their deadline?

### F-03 · Medium · Missing Calendar Boundary Decision

**Evidence:** `requirements.md` → **Product Behavior** specifies seven calendar dates including submission day. `model.md` → **Proposed Model And Persistence Direction** records submission dates and a seven-day active window, but neither specifies which timezone determines those dates.

**Boundary scenario:** An undated pending request is submitted near midnight, and members view it from different timezones around its expiry boundary.

**Supported outcome:** Submission day counts as the first date; expiry preserves pending queue access. The queue remains display-only initially, per `owner-decisions.md` → **Accepted Behavior**.

**Unspecified outcome:** Which calendar governs submission day and the transition out of the active list.

**Consequence:** Members could receive different active-list visibility for the same shared request.

**Confidence:** High.

**Owner question:** Which timezone governs submission dates and calendar-date expiry?

### Scope And Handoff

Reviewed all four supplied documents. Owner decisions establish authority; requirements provide behavior and acceptance criteria; workflow and model describe proposed architecture and persistence. No implementation exists according to the supplied workflow. No repository guidance or historical checkpoint was supplied.

Mobile delivery, calendar export, later resolution controls, and the acknowledged team-deletion retention question are not new findings. Acceptance-criterion repetition usefully reinforces the behavior. No tools, deterministic checks, edits, or implementation tests were performed under the review-only constraint.

Recommended next step: record the two missing visibility decisions and separately authorize correcting the component drift.

1. Authorize component-document alignment with the existing React/Postgres decision.
2. Provide answers to F-02 and F-03.
3. Address both together.
4. Give a custom response or prioritize a subset.
