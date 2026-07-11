---
name: plan
description: Write a short PLAN.md the user approves before building. Use after /align confirms, or when the user asks for a plan and the idea is already clear.
---

# /plan

Turn confirmed understanding into a short written plan. The user approves it before any building starts.

## When to use

- After `/align` confirms the summary.
- The user asks for a plan and the idea is already clear.
- `/fstack` routed here because there is no plan yet.

## Steps

1. Write or update `PLAN.md` in the project root.
2. Use exactly four sections (see below). No other headings.
3. Show the plan to the user.
4. **Stop and ask** for approval. Do not implement until they approve.
5. If any step feels big, split it or cut it. Do not nest sub-steps.

## PLAN.md format

### What we're doing

2–4 sentences. Plain language. What and why.

### Steps

Numbered list. Max 7 steps. Each step small enough to finish and verify in one sitting.

### What we're NOT doing

Mandatory. Never leave this empty. List tempting extras that are out of scope.

### How we'll know it works

1–3 plain checks. Things you can actually try, like "toggle the switch, refresh, theme persists".

## Must NOT

- Exceed one page. If longer, split the task into multiple plans.
- Add headings beyond the four sections.
- Start implementing. The plan ends at approval.

## Example "What we're NOT doing"

> **What we're NOT doing**
> - No theme customization beyond light/dark
> - No per-page theme overrides
> - No settings page — just the header toggle

## Example interaction

> Agent: *(writes PLAN.md, shows it)*
>
> "Here is the plan. Four sections: what we're doing, steps, what we're not doing, how we'll know it works. Approve this before I build?"
>
> User: "Approved."
>
> Agent: *(stops. User can invoke `/build` next.)*
