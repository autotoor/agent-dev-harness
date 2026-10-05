## Findings

**F-001 | High Priority | Drift From Accepted Direction**

The proposed component choices contradict the recorded owner decisions.

**Paired evidence:**

- `owner-decisions.md` → **Accepted Component Direction** selects React and Postgres. **Change Authority** requires a new owner decision to change those selections and records none.
- `requirements.md` → **Authority** recognizes recorded owner decisions as authoritative, but **Selected Components** declares Vue and SQLite selected for the first release.
- `workflow.md` → **Proposed Architecture And Workflow** repeats Vue and SQLite as selected direction.
- `model.md` → **Proposed Model And Persistence Direction** repeats SQLite as selected.

**Consequence:** Someone following the requirements, workflow, and model could build against technologies that conflict with accepted direction. Their agreement with each other does not establish authorization to supersede the owner decisions.

**Confidence:** High. Both the selections and the change-authority rule are explicit.

**Supported correction:** Align the current requirements and proposed documents with React and Postgres. Preserve backend framework, physical schema, and hosting as undecided. This correction follows the existing decision; it does not require choosing technologies or reopening that decision.

## Boundary Scenarios

- **Undated, pending, multiple assignees:** Submission day counts as the first of seven calendar dates of active-list eligibility. After that window, the request leaves the active list but remains accessible in the separate pending queue. Applicable member views share one request identity. These outcomes are supported by `requirements.md` → **Product Behavior / Acceptance Criteria** and `owner-decisions.md` → **Accepted Behavior**.
- **Initially resolving a pending request:** The queue is display-only, with resolution controls deferred. The requirements’ deferral is consistent with that accepted behavior.
- **Selecting components from the proposed workflow:** Vue and SQLite would contradict the recorded decision. React and Postgres remain the authoritative selections.

No additional semantic defect was found in the supplied behavior contracts. Team-deletion retention is explicitly acknowledged as open, and mobile delivery and calendar export are deferred; these are not new findings.

## Scope And Limits

Reviewed only the four supplied documents:

- `requirements.md`: authoritative behavior, first-release boundary, acceptance criteria, and open/deferred scope.
- `owner-decisions.md`: authoritative human-approved decisions and change authority.
- `workflow.md`: proposed architecture/workflow and explicit current-state statement that no application exists.
- `model.md`: proposed conceptual model and persistence direction.

No repository guidance, historical checkpoint, or separate overview was supplied. No tools or deterministic checks were run, as instructed. This review makes no implementation or test-pass claims.

## Recommended Next Step

Use F-001 to authorize a focused documentation correction preserving the recorded decisions. Select:

1. Authorize correction of the component references in the three affected documents.
2. Keep the documents unchanged and hand this finding to their owner.
3. Provide a custom next step.
