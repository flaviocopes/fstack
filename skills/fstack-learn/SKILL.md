---
name: fstack-learn
description: Capture one lesson from recent work into LEARNED.md. Use after shipping, when something surprising happened, or when a non-obvious fix would save future time.
---

# /fstack-learn

Capture one lesson so the next session starts smarter.

## When to use

- After `/fstack-push` completes.
- When a bug had a non-obvious cause.
- When a decision took longer than it should have.
- When the user invokes `/fstack-learn`.

## Steps

1. Look at the recent work and pick **one** lesson. Not two. Not a list.
2. Read `LEARNED.md` in the project root if it exists.
3. Check for a duplicate. If the same lesson is already there, say so and stop.
4. Skip routine facts. Do not log "added a component" or "fixed a typo".
5. Write the entry. Max three lines, this format:

```
## 2026-07-11 — Theme flash on load
The theme must be set in a blocking inline script, not in React.
Anything set after hydration flashes the wrong theme.
```

6. Append the entry to `LEARNED.md`. Create the file if it is missing.
7. Show the user exactly what was added.

## Entry rules

- Line 1: `## date — short title`
- Line 2: the lesson itself.
- Line 3: optional context or consequence. Omit if line 2 is enough.
- No essays. If it needs more than three lines, it belongs in a doc, not here.

## Must NOT

- Write more than one lesson per run.
- Log routine facts that would not save future-you real time.
- Duplicate an existing entry.
- Ask the user to approve before appending. Append, show, done.

## Example

> Agent: "Added to LEARNED.md:
>
> ## 2026-07-11 — Theme flash on load
> The theme must be set in a blocking inline script, not in React.
> Anything set after hydration flashes the wrong theme."
