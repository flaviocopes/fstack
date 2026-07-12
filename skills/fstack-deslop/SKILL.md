---
name: fstack-deslop
description: Sweep a whole codebase for AI slop and unnecessary complexity, then remove it in approved batches. Use when a project has grown bloated, or after a stretch of agent-written code.
---

# /fstack-deslop

A codebase-wide cleanup pass. Find the slop and the complexity nobody needs, rank it, and remove it — ruthlessly, but with your yes on each batch.

This is the big brother of `/fstack-simplify`. Simplify cuts one file or diff in the loop. Deslop audits the whole project and works through a ranked hit list.

## When to use

- The project has grown bloated over time.
- After a stretch of agent-written code, which tends to over-build.
- You invoke `/fstack-deslop`.

## Steps

1. Get the lay of the land: file tree, entry points, dependencies, and how big things are. Note what is actually used.
2. Hunt for slop across the codebase:
   - Dead code — unused files, exports, functions, variables, imports.
   - Abstractions with one caller. Layers that only pass data through.
   - Dependencies that replace a few lines of code.
   - Config and options nobody uses.
   - Error handling for cases that cannot happen.
   - Comments that restate the code, or narrate what a line does.
   - Copy-paste blocks that drifted instead of being shared.
   - "For the future" code that the future never needed.
   - Duplicated helpers doing the same job under different names.
3. Produce a **ranked removal plan**. Group by area. Each item is one line: what to remove, and what is lost (usually: nothing). Put the safe, high-value cuts first.
4. **Stop and ask** which groups to apply.
5. Remove the approved groups **one batch at a time**. After each batch, run the tests or the build. If something breaks, stop and report before continuing.
6. End with a short summary: what was removed, how many lines and files, what you left alone and why.

## Must NOT

- Delete anything without approval, or delete a whole batch before checking the last one passed.
- Add features, rewrite working code into a different style, or "improve" while removing. Removal only. Simpler, not different.
- Remove something just because it is unfamiliar. If you are unsure it is unused, leave it and say so.
- Touch generated files, vendored code, or lockfiles.

## Example

> User: `/fstack-deslop`
>
> Agent: "Swept the codebase. Ranked removal plan:
>
> **Dead code (safe)**
> 1. `src/utils/legacy/` — 4 files, zero imports. Lose: nothing.
> 2. 11 unused exports across `helpers.ts`. Lose: nothing.
>
> **Over-abstraction**
> 3. `RepositoryFactory` — one implementation, one caller. Inline it. Lose: nothing.
> 4. `useConfig` hook wrapping a single constant. Lose: nothing.
>
> **Dependencies**
> 5. Drop `lodash` — used for one `groupBy`, 6 lines replace it.
>
> Apply all, or pick groups? I'll remove one batch at a time and run tests between."
