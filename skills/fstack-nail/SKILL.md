---
name: fstack-nail
description: Nail down an unclear task before any work starts. Ask questions, confirm a 3-line summary, then stop. Use when the task is vague or /fstack routes here for clarification.
---

# /fstack-nail

Nail down the task before planning or coding. Ask a few plain questions. Get a confirmed summary. Stop there.

## When to use

- The task is vague or has important unanswered questions.
- `/fstack` routed here because the idea needs clarification.
- The user wants to nail down what they mean before moving on.

## Steps

1. Read the request. Look at the relevant parts of the codebase.
2. Ask at most **5 questions**, all in one message. Plain questions, no sub-bullets. Only ask what you cannot infer from the code or conversation.
3. **Stop and wait** for answers. Do not plan or code while waiting.
4. Reply with a **3-line summary**:
   - What we're building.
   - The one constraint that matters most.
   - What success looks like.
5. Ask the user to confirm. Do nothing else until they do.

## If you have more than 5 questions

The task is too big. Say so. Suggest splitting it into smaller tasks. Do not ask all 8 questions.

## Must NOT

- Ask questions whose answers are already in the codebase or conversation.
- Ask more than 5 questions, ever.
- Start planning or coding. This skill ends at the confirmed summary.

## Example

> Agent: "Three questions before I start: 1) Should dark mode follow the OS setting or a manual toggle? 2) Does it need to persist across visits? 3) Any pages excluded?"
>
> User: *(answers)*
>
> Agent: "Summary: manual toggle in the header, persisted in localStorage, applies everywhere. Main constraint: no flash of wrong theme on load. Success: toggle works and survives refresh. Confirm?"
>
> User: "Yes."
>
> Agent: *(stops. User can invoke `/fstack-plan` next.)*
