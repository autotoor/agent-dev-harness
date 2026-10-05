# Recorded Owner Decisions

## Loading Contract

Preserve the distinction between successfully empty, failed with saved data, and failed with no saved data. The last outcome is an error with unavailable data, never evidence that the board is empty.

## Design Sequence

Review copy and layout in static mocks before implementing the final interface. That review does not choose storage or change loading semantics. The first release remains read-only.
