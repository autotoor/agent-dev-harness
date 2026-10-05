# Proposed Conceptual Model

A Request has an ID, text, optional due date, submission date, and exactly one `assigneeId`. This single identifier is the complete assignment representation; no assignment collection or join relationship is proposed.

Pending approval is a request status. Physical tables and persistence mechanisms are undecided.
