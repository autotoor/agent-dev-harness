## F-01: Error Presentation

**Classification: useful clarification.**

The required distinction is settled: a no-data failure must look different from a successful empty result. Exact wording, layout, and icon choice remain unspecified, explicitly assigned to static mock review. That review precedes final interface implementation. [requirements.md, Presentation; owner-decisions.md, Design Sequence]

The consequence is a planned design dependency for the **final UI implementation**, not an unresolved loading-policy decision. The data contract and all three loading outcomes can proceed independently. [requirements.md, Presentation]

Confidence is high that presentation details remain open, and high that they can be resolved in the planned review. There is no evidence of an urgent blocker to current contract work.

Smallest design question: **Does the proposed no-data error mock visibly distinguish unavailable data from a successful empty result?**

## F-02: Missing No-Data Failure Outcome

**Classification: unsupported finding.**

The alleged missing outcome is already specified. A failed load without saved content must show a data-unavailable error, with neither an empty-result message nor a zero record count. Recorded owner decisions confirm that this outcome never establishes that the board is empty. [requirements.md, Loading Outcomes; owner-decisions.md, Loading Contract]

The absence of fallback content does not leave the semantics open. Asking the owner to choose between an error and an empty list would reopen a settled decision. No policy question remains; presentation details are covered by F-01.

The affected implementation step is **loading-state handling**: implement the prescribed no-data error outcome. Confidence is high that the alleged semantic gap is absent, so this finding creates no decision urgency.

## Recommended Next Step

Proceed with the settled loading contract and resolve F-01 during the scheduled static mock review. No owner policy decision is needed.

1. Implement the data contract and three loading outcomes now.
2. Review no-data error copy, layout, and icon choice in static mocks before final UI implementation.
3. Close F-02 as already answered by the requirements and recorded decisions.
