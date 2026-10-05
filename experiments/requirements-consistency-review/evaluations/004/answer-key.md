# Evaluator-Only Lending Answer Key

Authored before reviewer execution. Never include in reviewer inputs. This is an expected question, not authority to decide an outcome in the seeded case.

```json
{
  "id": "suspension-confirmed-reservation-lifecycle",
  "evidence": [
    {
      "document": "requirements.md",
      "clause": "Confirmed reservations exclusively hold their tool; suspended members cannot check out tools."
    },
    {
      "document": "workflow.md",
      "clause": "Staff may suspend members at any time, while cancellation and expiration release reservation holds."
    },
    {
      "document": "model.md",
      "clause": "Reservation status and membership status are separate; terminal reservation states cannot be restored."
    }
  ],
  "boundaryScenario": "An active member has a confirmed reservation with 12 hours remaining. Staff suspend the member before checkout. The member opens their reservation view, and another active member attempts to reserve the same tool.",
  "supportedOutcomes": [
    "The suspended member cannot create another reservation or check out this tool.",
    "Any existing outstanding loan retains its due date and can be returned.",
    "If the reservation becomes canceled, its tool is released and the member sees the cancellation reason.",
    "If the reservation remains confirmed, its hold persists until cancellation or expiration."
  ],
  "unspecifiedOutcome": "The seeded documents do not determine whether suspension preserves or terminates an existing confirmed reservation, so its displayed status and the tool's availability after suspension are unspecified.",
  "appropriateOwnerQuestion": "When a member is suspended before pickup, should their confirmed reservations remain held until their deadlines, or be canceled immediately and release the tools?",
  "controlResolution": "The control adds one workflow clause: suspension atomically cancels remaining confirmed reservations with reason account_suspended. Existing expiration precedence handles reservations already at their deadlines; terminal states prevent reinstatement from reviving canceled reservations."
}
```

Author limitations: This fixture specifies observable state and allocation behavior, not exact interface wording or transport-error recovery. The seeded case's reinstatement consequences for prior confirmed reservations depend on the same missing suspension rule. Waitlists and concurrency mechanism selection are deliberately outside the finding. No reviewer execution or grading is claimed.
