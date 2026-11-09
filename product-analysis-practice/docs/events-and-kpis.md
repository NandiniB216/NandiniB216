# Product Events and Success Measures

These are proposed analytics definitions for a hypothetical product. No events have been implemented and no performance data exists.

## Event taxonomy

| Event | Trigger | Useful properties |
|---|---|---|
| session_list_viewed | Session list becomes visible | session_count |
| session_details_viewed | A session detail page opens | session_id |
| session_selected | User selects a session | session_id |
| readiness_viewed | Preparation step appears | session_id |
| session_started | User confirms and session begins | session_id |
| session_paused | User pauses an active session | session_id, elapsed_seconds |
| session_resumed | User resumes a paused session | session_id, elapsed_seconds |
| session_exited | User exits before completion | session_id, session_state |
| session_completed | All mandatory steps are complete | session_id, elapsed_seconds |

Do not collect sensitive health information in event properties. Use pseudonymous identifiers and follow the applicable privacy and retention policy.

## KPI definitions

| KPI | Definition | Interpretation caution |
|---|---|---|
| Session detail-view rate | Unique sessions with details viewed ÷ unique session-list viewers | Indicates exploration, not satisfaction |
| Session start rate | Unique session starts ÷ unique session-detail viewers | May reflect suitability, clarity or other factors |
| Completion rate | Completed sessions ÷ started sessions | Define treatment of pauses and repeat attempts |
| Early-exit rate | Sessions exited before completion ÷ started sessions | Segment by session and device before drawing conclusions |
| Pause rate | Paused sessions ÷ started sessions | Pausing is not necessarily a negative outcome |

## Measurement plan

1. Confirm event definitions and state transitions.
2. Validate event firing in a test environment.
3. Check duplicate and missing events.
4. Establish a baseline before setting targets.
5. Segment by session type and device where appropriate.
6. Avoid interpreting product engagement as clinical benefit.

## Guardrails

- Do not claim the product improves health or recovery from these events.
- Do not treat correlation as causation.
- Do not set numerical targets without baseline evidence.
