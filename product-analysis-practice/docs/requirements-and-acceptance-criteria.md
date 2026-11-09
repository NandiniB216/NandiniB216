# Requirements and Acceptance Criteria

## Functional requirements

### FR-01 — Session information

The system shall display the duration, space requirement, equipment requirement and a plain-language description for each session.

**Acceptance criteria**
- Given a user views the session list, when the list loads, then each session displays its available details.
- Given a required detail is unavailable, when the session is displayed, then the system labels it as unavailable rather than inventing a value.

### FR-02 — Session selection

The system shall allow a user to select a session and review its details before starting.

**Acceptance criteria**
- Given a user selects a session, when its details open, then the selected session name and requirements are visible.
- Given a user returns to the list, when the list reappears, then the user can choose another session.

### FR-03 — Readiness confirmation

The system shall provide a preparation step before the session begins.

**Acceptance criteria**
- Given a user has opened session details, when they choose to begin, then preparation information is shown before the session starts.
- Given the user is not ready, when they choose to go back, then the session does not start.

### FR-04 — Pause and resume

The system shall distinguish a paused session from a completed session.

**Acceptance criteria**
- Given a session is active, when the user pauses it, then the interface displays a paused state.
- Given a session is paused, when the user resumes, then the session returns to the active state.
- A paused session must not be counted as completed.

### FR-05 — Incomplete session

The system shall distinguish an early exit from successful completion.

**Acceptance criteria**
- Given a session is active, when the user exits before all required steps are complete, then the session is marked incomplete.
- Given a session is incomplete, when the summary is shown, then it does not display a completion success state.

### FR-06 — Completion summary

The system shall show a completion summary only when all required session steps are complete.

**Acceptance criteria**
- Given all required steps are complete, when the user finishes, then a completion summary is displayed.
- Given one or more required steps remain incomplete, when the user exits, then a completion summary is not displayed.

## Non-functional requirements

- **Usability:** instructions use plain language and one primary action per step.
- **Accessibility:** controls have accessible names, visible focus and keyboard support.
- **Privacy:** request only permissions needed for a clearly explained feature.
- **Reliability:** the interface must not show completion when the session state is incomplete.
- **Transparency:** unavailable or unverified information is labelled clearly.

## Business rules

| ID | Rule |
|---|---|
| BR-01 | A session is not started until the user confirms readiness. |
| BR-02 | Paused and incomplete sessions are not counted as completed. |
| BR-03 | Completion requires all mandatory steps to be completed. |
| BR-04 | Missing session metadata is displayed as unavailable, not inferred. |
| BR-05 | No clinical suitability or health outcome is inferred by the planner. |

## Open questions

- What counts as a mandatory step for each session?
- Should users be able to resume after closing the application?
- What accessibility standards and assistive technologies must be supported?
- Who approves the session content and safety language?
