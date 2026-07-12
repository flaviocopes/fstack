---
name: fstack-check
description: Review finished work with three questions before shipping. Use when work is done and needs review, or after /fstack-build finishes all plan steps.
---

# /fstack-check

Review finished work before shipping. Answer three questions with evidence. Report and stop. Do not fix anything.

## When to use

- The user invokes `/fstack-check`.
- `/fstack-build` finished all plan steps.
- `/fstack` routed here because work is done and needs review.

## Steps

Answer exactly three questions, in order, with evidence.

### 1. Does it work?

Prove it by running it. Tests, the dev server, the actual command. "It should work" is not an answer. Paste the actual output.

### 2. Does it match the plan?

Diff the work against `PLAN.md`. Flag anything built that was not planned. Flag anything planned that was not built.

Then check blast radius. List what else this change could affect: callers, styles, routes, configs. Confirm each is fine.

### 3. Is it simple?

Quick pass with the `/fstack-simplify` smell list. If something smells, say so and suggest running `/fstack-simplify`. Do not run it automatically.

## Verdict

End with one line:

- **Ready to ship** — or —
- **Not ready: [reason]**

**Stop and ask** the user what to do next. Do not fix what you found.

## Must NOT

- Fix things it finds. Report, suggest, stop. The user decides.
- Skip the "prove it works" step, even for small changes.
- Add review dimensions. Three questions only. No security theater, no style nits.

## Example

> **Does it work?** Ran `npm test` — 42 passed, 0 failed. Loaded the page, toggled dark mode, refreshed — theme persisted.
>
> **Does it match the plan?** All 4 steps done. Nothing extra built. Blast radius: header component and global CSS — both look fine.
>
> **Is it simple?** `ThemeProvider` wrapper has one caller. Consider `/fstack-simplify` to drop it.
>
> **Ready to ship**
