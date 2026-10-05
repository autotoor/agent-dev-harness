# Team Request Tracker Requirements

## Scope And Authority

These requirements and the owner decisions define first-release behavior. Workflow and model documents are proposed descriptions to check against them, not implemented software.

## Request Coverage

An authorized team member can submit a request without a due date. Keep it visible in the active request list and explicitly show that no deadline was supplied. Never invent a due date.

## Assignments

A request may be assigned to multiple team members. Show one shared request in the team view and in each assignee's view. An update changes the shared request once.

## Aging And Review

Undated requests leave the active request list after seven calendar dates including submission day. Requests needing owner approval appear in a pending-review queue. At day eight, an undated pending request leaves the active list but remains in that queue until the owner resolves it. The queue is a separate access path; leaving the active list does not remove queue access. This release has no owner-facing approve/reject controls yet; the queue shows pending status only.

## Acceptance Criteria

A request with no deadline is retained in the active list during its seven-day window, labeled without a deadline. A request assigned to two members appears once in the team view and in both member views. A pending undated request submitted September 27 is out of the active list on October 4 and still accessible in the pending queue.

## Deferred And Open

Calendar export is deferred. Data retention after team deletion is explicitly open and must be decided before production deployment. Neither is a chosen first-release behavior.
