# Team Request Tracker Requirements

## Authority

Recorded owner decisions define accepted direction. Current descriptions must preserve that direction unless a subsequent owner-approved change is recorded. No superseding decision is supplied.

## Product Behavior

Members submit requests with optional deadlines. Requests have multiple assignees, one shared identity, and pending status when approval is needed. Undated requests leave the active list after seven calendar dates including submission day; pending requests remain in a separate queue after leaving that list. Resolution controls come later.

## Selected Components

The first-release web application uses Vue and a SQLite database. These are selected components, not alternatives awaiting evaluation. Backend framework, physical schema, and hosting are undecided.

## Acceptance Criteria

Retain undated requests without inventing deadlines. Show shared requests in all applicable member views. Preserve pending queue access when an undated request leaves the active list.

## Deferred And Open

Mobile delivery and calendar export are deferred. Team-deletion retention is an acknowledged open question before production deployment.
