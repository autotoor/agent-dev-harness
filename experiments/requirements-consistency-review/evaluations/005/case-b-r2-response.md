### F-01: Error Presentation

**Classification: useful clarification.** The required distinction is settled: a failed load without saved content must visibly differ from a successful empty result. Exact wording, layout, and icon choice remain unspecified and are explicitly assigned to static mock review. ([requirements.md → Presentation]; [owner-decisions.md → Design Sequence])

The consequence is limited to final interface presentation. Mock review must resolve these details before final UI implementation, but they do not block the data contract or loading-state behavior. This is a planned design dependency, not a missing loading-policy decision.

Confidence that presentation details remain unspecified is high. Confidence that they urgently block current work is low; their timing is already established.

Smallest design question: **Which copy, layout, and icon treatment should the static mock use to make unavailable data visibly distinct from a successful empty result?**

The data contract and all three loading outcomes can continue independently. ([requirements.md → Presentation])

### F-02: Missing No-Data Failure Outcome

**Classification: unsupported finding.** The alleged omission is already answered. A failed load without saved content must show a data-unavailable error, never an empty-result message or a zero record count. The owner explicitly reaffirmed this distinction. ([requirements.md → Loading Outcomes]; [owner-decisions.md → Loading Contract])

The absence of fallback content does not make the outcome unspecified. Showing a successful empty result would violate the recorded contract. The affected implementation step is loading-state handling, which can proceed using that contract without another owner decision.

Confidence that the claimed semantic gap is absent is high. There is no supported unresolved policy question or decision urgency here. Presentation details remain open only as covered by F-01.

### Recommended Next Step

Proceed with loading-state implementation and resolve F-01 through the scheduled static mock review. No blocking owner decision is supported by these documents.

1. Implement the data contract and three specified loading outcomes now.
2. Review the unavailable-data presentation in static mocks before implementing the final interface.
