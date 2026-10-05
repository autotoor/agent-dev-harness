# Team Request Tracker Requirements

## Authority And Scope

Requirements and recorded owner decisions govern this synthetic first-release display. Workflow/model documents are proposed, not running software. This case resolves earlier display ambiguities without selecting storage mechanisms.

## Actors And Access

The owner and current authorized team members can view the team active list, any member's active-list filter, and the pending-review queue. All viewers have the same permissions, without per-assignee restrictions. Member filters apply assignee membership and the ordinary active-list window, not a separate retention rule. The owner is also a member.

## Intake And Shared Identity

Authorized members submit requests with optional due date, one or more valid member assignees, and a pending flag. Unauthorized submissions, empty text, or invalid assignees are rejected without saving. A successful save creates one shared request. Updates replace its details once in all applicable views. Failed saves leave the previous version intact with an error indication. Membership administration and pending-state changes are outside this display-only release.

## Date And Display Rules

All calendar dates use UTC. Undated requests are active for seven dates including submission day. Dated requests are active through their due date inclusive; afterward they leave the active list without a completion claim. Requests submitted with past due dates start outside the active list.

The same expiry rules apply to member filters. Pending requests remain in the queue for every authorized viewer regardless of date. Expired ordinary requests have no visible access path in this release; disappearance does not imply deletion. Resolution controls are deferred, so display does not change pending state.

Calculate eligibility from saved dates and current UTC date at display and midnight/resume; do not reinterpret due dates. If fresh data cannot load, show last saved content with a failure indicator and current-date placement, without asserting a successful refresh.

## Acceptance Criteria

An undated request submitted September 27 leaves active lists and member filters October 4. If pending it remains in the queue for all viewers; otherwise it has no visible access path. A request due October 3 leaves active lists October 4, independently of pending visibility. Multiple assignees share one request; failed saves retain the last saved version.

## Deferred And Open

Calendar export, archive browsing, pending resolution, and membership administration are deferred. Database/framework/schema selection and team-deletion retention are acknowledged open choices. No production deployment is authorized before retention is decided.
