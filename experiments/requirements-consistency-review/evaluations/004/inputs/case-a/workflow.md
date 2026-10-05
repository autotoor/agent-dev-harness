# Proposed Intake And Display Workflow

Validate member authorization, nonempty text, and valid assignees, then save one shared request with optional due date and supplied pending state. A failed save retains existing content and indicates failure. All authorized viewers have identical access to active lists, member filters, and the pending queue.

Use saved dates and current UTC date. Apply seven-calendar-date undated and due-date-inclusive dated windows to active lists and member filters. Pending items remain in the queue regardless of date. Expired ordinary items have no visible access path; no deletion is implied. Recalculate at display and midnight/resume. Load failures show saved content with a failure indicator and current-date placement, not a successful refresh.

No application exists. Database/framework/schema selection and deletion retention are explicitly open. Calendar export, archive browsing, pending resolution, and membership administration are deferred.
