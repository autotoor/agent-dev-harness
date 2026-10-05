# Candidate Findings

## F-01: Edit Actor Rule

`requirements.md` -> Editing describes successful updates without saying whether the creator, assignees, owner, or every current member may make them. `owner-decisions.md` -> Accepted Scope confirms web/API edits but records no actor choice.

Scenario: a current member who is neither creator nor assignee submits a date edit. The documents specify validity and shared persistence but not whether that member is authorized. Clarify the actor rule before implementing editing.

## F-02: Calendar Export

`requirements.md` -> Release Boundary and `owner-decisions.md` -> Deferred Work omit calendar export from this release. A calendar export would help members use requests elsewhere. Add export to the release requirements before development proceeds.
