# Proposed Conceptual Model

A Request has ID, text, UTC submission date, optional UTC due date, valid assignee identifier collection, and a supplied pending flag. Views share identity. Active/member-filter eligibility is derived from the current-date windows, not a separate expiration rule.

All authorized viewers can access all views. Pending-queue eligibility depends only on pending state, not date or assignee. Expired ordinary items have no visible access path. Storage and deletion retention are undecided; resolution, archives, and membership administration are deferred.
