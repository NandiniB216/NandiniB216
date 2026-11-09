# User Journey and Proposed Flow

## Happy path

1. User opens the session planner.
2. User reviews available sessions.
3. User compares duration, space and equipment requirements.
4. User selects a session.
5. User reads preparation and suitability information.
6. User confirms readiness.
7. User follows the session instructions.
8. User can pause or exit.
9. User sees a completion summary only after the session is marked complete.

## Text flow

```text
Open planner
    |
Browse sessions
    |
Select a session
    |
Review duration / space / equipment
    |
Ready to begin?
  /       \
No         Yes
|           |
Return      Start session
to browse   |
            Follow steps
            |
       Pause or continue?
         /       \
      Pause     Continue
        |          |
    Resume or   Finish all
       exit       steps
                    |
              Completion summary
```

## Important alternate paths

| Situation | Expected experience |
|---|---|
| User is not ready | Return to session details without losing selection |
| User exits before starting | Return to browse; do not record a completion |
| User pauses | Show a clear paused state and a resume action |
| User exits mid-session | Mark as incomplete, not completed |
| User loses connectivity | Explain whether progress is saved; do not promise recovery until implemented |
| User needs help | Provide plain-language instructions and a route back to the current step |

## Product decisions to validate

- Whether users need a guest path or account sign-in
- Whether progress should persist after closing the page
- Whether sessions should be filterable by duration and space
- Whether a user can switch sessions after starting

These are open questions, not settled requirements.
