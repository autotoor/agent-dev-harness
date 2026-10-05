# Model
Member: active or suspended.
Reservation: confirmed, canceled, expired, or checked_out; includes member, tool, pickup_deadline, and optional cancellation_reason. Canceled, expired, and checked_out are terminal.
Loan: outstanding or returned; includes member, tool, due_at, and returned_at. Overdue is derived from outstanding and now >= due_at; it does not block returns.

All timestamps use server UTC. Actions are serialized and evaluated at commit time. Before evaluating any action or rendering a view, confirmed reservations whose deadlines have arrived expire. Checkout requires now < pickup_deadline.

A tool may have at most one confirmed reservation or outstanding loan.
