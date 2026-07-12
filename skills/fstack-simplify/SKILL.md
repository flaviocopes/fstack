---
name: fstack-simplify
description: Audit a plan, diff, or file for unnecessary complexity and propose deletions. Use when something feels bloated, over-engineered, or harder than it should be.
---

# /fstack-simplify

Audit a plan, diff, file, or folder for unnecessary complexity. Propose deletions and reductions only. Nothing gets applied without approval.

## When to use

- The user invokes `/fstack-simplify` on a plan, diff, file, or folder.
- `/fstack-check` spotted complexity and suggested running this skill.
- Something feels bloated, over-engineered, or harder than it should be.

## Steps

1. Read the target.
2. Hunt for these smells:
   - Abstractions with one caller
   - Config options nobody asked for
   - Dependencies that replace 10 lines of code
   - Error handling for situations that can't happen
   - Files, helpers, or layers that exist "for the future"
   - Words in docs or comments a beginner wouldn't know
3. Produce a short list of proposed **deletions and reductions**. Each item is one line: what to remove, and what you'd lose (usually: nothing).
4. **Stop and ask** which ones to apply.
5. Apply only the approved ones.

## Must NOT

- Propose additions. This skill only removes and reduces.
- Rewrite working code to a different style. Simpler, not different.
- Apply anything without approval.

## Example output

> Can be less:
> 1. Delete `ThemeProvider` abstraction — one consumer, a hook does it. Lose: nothing.
> 2. Remove `theme-config.json` — two values, inline them. Lose: nothing.
> 3. Drop the `clsx` dependency — used once, template literal works. Lose: nothing.
>
> Which should I apply?
