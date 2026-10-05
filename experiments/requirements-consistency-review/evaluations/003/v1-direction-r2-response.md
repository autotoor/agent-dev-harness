Found one contradiction with accepted direction and two missing product decisions affecting active-list visibility.

### F01 · P1 · Drift From Accepted Direction
**Evidence:** `owner-decisions.md` → Accepted Component Direction and Change Authority specify React and Postgres, with no approved replacement. `requirements.md` → Selected Components instead selects Vue and SQLite; `workflow.md` → Proposed Architecture And Workflow repeats both replacements; `model.md` → Proposed Model And Persistence Direction repeats SQLite.

**Consequence:** The current documents present unapproved technologies as settled choices, so implementation could follow the wrong baseline.

**Confidence:** High.

**Supported correction:** Align those descriptions with the recorded React/Postgres decision. Backend framework, physical schema, and hosting remain undecided. No new technology choice is needed.

### F02 · P2 · Missing Dated-Request Lifecycle
**Evidence:** `requirements.md` → Product Behavior defines active-list expiry for **undated** requests only. `workflow.md` → Proposed Architecture And Workflow says active-list eligibility follows the requirements, but provides no rule for dated requests.

**Boundary scenario:** A request is submitted with a deadline, remains pending, and passes its deadline.

**Confirmed:** Deadlines are permitted, and accepted behavior preserves pending queue access after active-list expiry (`owner-decisions.md` → Accepted Behavior).

**Unspecified:** Whether passing the deadline causes active-list expiry at all. The queue-retention decision does not establish that trigger.

**Consequence:** The documents cannot determine whether members continue seeing this request in the active list.

**Confidence:** High.

**Owner question:** What determines when a dated request leaves the active list, including when its deadline has passed?

### F03 · P2 · Missing Calendar-Date Boundary
**Evidence:** `requirements.md` → Product Behavior specifies seven calendar dates including submission day. `model.md` → Proposed Model And Persistence Direction mentions submission dates and the active window, but neither document defines whose calendar determines those dates.

**Boundary scenario:** An undated pending request reaches the start of its eighth calendar date for one member while another member is still on the seventh date.

**Confirmed:** Submission day counts as the first date; the request leaves the active list after the seventh counted date, while pending queue access persists (`requirements.md` → Product Behavior and Acceptance Criteria).

**Unspecified:** Which timezone governs submission day and expiry, and therefore whether members share one expiry instant.

**Consequence:** Members could see inconsistent active-list membership for the same shared request.

**Confidence:** High.

**Owner question:** Which timezone governs the seven-calendar-date window?

### Scope And Handoff
Reviewed all four supplied documents. Requirements provide behavior and acceptance criteria; owner decisions establish accepted authority; workflow and model describe proposed architecture and persistence. No historical checkpoint or implemented application is supplied; workflow explicitly states that implementation has not begun.

Optional deadlines, multiple assignees, shared identity, pending queue retention, and deferred resolution controls are consistent. Mobile delivery, calendar export, and the acknowledged team-deletion retention question are not new findings. No tools, deterministic checks, edits, or implementation tests were performed, as requested.

Recommended next step: correct the component drift using existing authority, then obtain the two visibility decisions. Select:

1. Separately authorize documentation alignment to React/Postgres.
2. Provide owner answers for F02 and F03.
3. Give a custom next step or narrower follow-up scope.
