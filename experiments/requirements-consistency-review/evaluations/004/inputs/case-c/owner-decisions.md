# Owner Decisions
Only staff change membership status, perform checkout, or record returns. Members see only their own records; staff see all records. Only members cancel their own confirmed reservations through the ordinary cancellation action.

No fees, renewals, or manual staff reservation overrides in this release. Automatic transitions explicitly required by the workflow are not manual overrides. Waitlists are intentionally deferred.

Open implementation choice: use database locking or compare-and-swap to enforce serialized transitions. Either must preserve atomic writes and exclusive tool allocation.
