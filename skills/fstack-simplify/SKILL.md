---
name: fstack-simplify
description: Audit for unnecessary complexity and propose deletions — from a single file to the whole codebase. Use when something feels bloated, over-engineered, or sloppy.
---

# /fstack-simplify

Audit for unnecessary complexity and propose deletions. Only deletions — never additions. Works at any scope: a plan, a diff, a file, or the entire codebase. Nothing gets applied without approval.

## When to use

- The user invokes `/fstack-simplify` on a plan, diff, file, folder, or whole project.
- `/fstack-check` spotted complexity and suggested running this skill.
- Something feels bloated, over-engineered, or sloppy — one file or the whole thing.

## Steps

1. Read the target. If it is the whole codebase, first get the lay of the land — file tree, entry points, dependencies, what is actually used.
2. Hunt for these smells:
   - Dead code — unused files, exports, functions, imports
   - Abstractions with one caller, or layers that only pass data through
   - Config options nobody asked for
   - Dependencies that replace a few lines of code
   - Error handling for situations that can't happen
   - Comments that just restate the code, or "for the future" code the future never needed
   - Copy-paste blocks that drifted instead of being shared
   - Words in docs or comments a beginner wouldn't know
3. Produce a list of proposed **deletions and reductions**. Each item is one line: what to remove, and what you'd lose (usually: nothing). For a whole-codebase pass, **rank** them and group by area, safe high-value cuts first.
4. **Stop and ask** which ones to apply.
5. Apply the approved ones. For a large pass, apply **one batch at a time** and run the tests or build between batches. If something breaks, stop and report before continuing.

## Must NOT

- Propose additions. This skill only removes and reduces.
- Rewrite working code to a different style. Simpler, not different.
- Remove something just because it is unfamiliar. If you are unsure it is unused, leave it and say so.
- Touch generated files, vendored code, or lockfiles.
- Apply anything without approval, or apply a whole batch before checking the last one passed.

## Example output

> Can be less (ranked):
> 1. Delete `src/utils/legacy/` — 4 files, zero imports. Lose: nothing.
> 2. Delete `ThemeProvider` abstraction — one consumer, a hook does it. Lose: nothing.
> 3. Remove `theme-config.json` — two values, inline them. Lose: nothing.
> 4. Drop the `clsx` dependency — used once, template literal works. Lose: nothing.
>
> Which should I apply? For a big sweep I go one batch at a time and run tests between.
