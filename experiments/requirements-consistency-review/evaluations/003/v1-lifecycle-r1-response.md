## Findings

**F-01 | P2 | Missing Product Decision: Pending Review And Aging**

**Evidence:** `requirements.md` → “Aging And Review” says undated requests leave the active list after seven calendar dates including submission day, while approval requests appear in a separate queue. `owner-decisions.md` → “Recorded Owner Decisions” confirms separate pending status and defers resolution controls, but does not define the queue’s aging behavior.

**Boundary scenario:** An undated request submitted Monday is still pending approval the following Monday.

- **Confirmed:** Its seven-date active-list window covers Monday through Sunday. Pending review appears separately from the ordinary list, and first-release owner resolution controls are unavailable.
- **Unspecified:** Whether it remains visible in the pending-review queue after that window expires.

**Consequence:** The documents permit different user-visible outcomes: continued access to unresolved requests or their disappearance from both lists.

**Confidence:** High that queue visibility after aging is unspecified.

**Owner question:** Does the seven-date limit apply only to active-list eligibility, leaving unresolved requests visible in pending review, or should pending-review visibility also expire?

**F-02 | P2 | Missing Product Decision: Dated Request Eligibility**

**Evidence:** `requirements.md` → “Request Coverage” and “Aging And Review” define an active window for undated requests but supply no equivalent eligibility rule for dated requests. `workflow.md` → “Proposed Intake Workflow” accepts dated requests and delegates display to the requirements’ eligibility rules.

**Boundary scenario:** A request has a Friday due date and does not need approval. The team opens the list on Saturday.

- **Confirmed:** Intake accepts the supplied due date without inventing another date. If assigned to two members, it remains one shared request.
- **Unspecified:** Whether the overdue request stays active, leaves the list, or receives another visible treatment. The seven-date rule explicitly covers undated requests.

**Consequence:** The proposed workflow cannot determine which dated requests users can see after their deadlines.

**Confidence:** High.

**Owner question:** What determines active-list eligibility for dated requests, particularly after the due date passes?

## Scope And Limits

Reviewed `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md`. Requirements and recorded owner decisions explicitly govern the first release; workflow and model documents are proposals, and no application exists. No repository guidance was supplied.

No direct contradictions were found. Multiple assignees, shared identity, optional deadlines, and separate pending status align across the documents. Acceptance-criterion repetition is useful. Calendar export, team-deletion retention, framework selection, and database selection are acknowledged deferred or open matters, not new findings.

This was a supplied-document semantic review only. No tools, deterministic checks, or implementation tests were run.

## Recommended Next Step

Record the two visibility decisions before refining the proposed workflow. Select:

1. Address F-01 first: state whether pending review persists after the undated window.
2. Address F-02 first: state how dated requests enter and leave the active list.
3. Address both together, or provide a custom response.

These options request owner decisions; this review does not choose their outcomes.
