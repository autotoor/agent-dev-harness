The supplied documents agree on the settled first-release behavior. I found two missing product decisions affecting request visibility, rather than direct contradictions.

### F-01 · Medium · Missing Product Decision: Access After Aging Out

**Evidence:** `requirements.md` → “Request Coverage,” “Assignments,” and “Aging And Review”; `owner-decisions.md` → “Recorded Owner Decisions.”

**Boundary scenario:** An undated request assigned to two members is submitted September 27 and does not need approval.

**Confirmed:** It leaves the active request list on October 4. Both assignees reference one shared request; updates do not create separate copies.

**Unspecified:** Whether the request remains accessible in either member’s view or through another access path. Continued queue access is guaranteed only for pending requests. The direction that undated requests “must not be discarded” does not establish how users access ordinary requests after expiration.

**Consequence:** The documents permit different user experiences, including a retained request becoming inaccessible to its assignees.

**Confidence:** High that post-window access is unspecified.

**Owner question:** After an ordinary undated request leaves the active list, where, if anywhere, should team members and assignees still be able to see it?

### F-02 · Medium · Missing Product Decision: Dated-Request Eligibility

**Evidence:** `requirements.md` → “Request Coverage” and “Aging And Review”; `workflow.md` → “Proposed Intake Workflow”; `model.md` → “Proposed Conceptual Model.”

**Boundary scenario:** Two requests are submitted September 27. One has no deadline; the other has an October 3 deadline. Consider their visibility on October 4.

**Confirmed:** The undated request is outside its active-list window. If pending, it remains accessible in the review queue.

**Unspecified:** Whether the dated request remains active after its deadline or follows another expiration rule. The workflow delegates eligibility to the requirements, but those requirements define an active-list expiration rule only for undated requests.

**Consequence:** Readers cannot determine the active list’s contents for dated requests, including overdue requests.

**Confidence:** High that dated-request eligibility is unspecified.

**Owner question:** What determines when a dated request leaves the active list, particularly after its deadline?

### Scope And Limits

Reviewed `requirements.md`, `workflow.md`, `model.md`, and `owner-decisions.md`. Requirements and recorded owner decisions are authoritative; workflow and model are proposed descriptions. Acceptance criteria usefully repeat the behavior. No implemented behavior, historical checkpoint, or repository guidance was supplied.

Calendar export, retention after team deletion, owner resolution controls, and persistence choices are explicitly deferred or open; they are not new defects. No tools, deterministic checks, or implementation tests were run, as instructed.

Recommended next step: record the visibility decisions before revising the proposed workflow. Select:

1. Answer F-01 first.
2. Answer F-02 first.
3. Answer both together.
4. Provide a custom next step.
