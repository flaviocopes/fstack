---
name: fstack
description: The fstack front door. Invoke /fstack alone to list every skill, or with a task to route it to the right one.
---

# /fstack

The front door for fstack. Read what the user wants. Pick one skill. Run it. Stop.

## When to use

- The user invokes `/fstack`.
- The user asks which fstack skill fits their task.
- The user describes work and mentions fstack without naming a skill.

## Steps

1. Read the user's request.
2. **If there is no task** — the user typed `/fstack` alone, or just asked what fstack can do — list the twelve skills with a one-line description each, then stop and ask what they want to do. Do not route or guess. This is the menu below.
3. **If there is a task** — match it to one of the twelve skills below.
4. Say which skill you picked and why, in one sentence.
5. Run that skill. Do not chain others.

## The skills

When there is no task, show this list:

| Skill | What it does |
|---|---|
| `/fstack-roast` | Stress-test a product idea. Ends with a verdict and the smallest version worth building. |
| `/fstack-interview` | Ask about the product — demand, customer, pricing, risks — and record the answers in AGENTS.md. |
| `/fstack-nail` | Ask up to 5 questions, nail down a 3-line summary, get your yes before any work starts. |
| `/fstack-plan` | Write a one-page plan with a mandatory "what we're NOT doing" section. |
| `/fstack-build` | Implement the plan one small step at a time, asking at real choices. |
| `/fstack-simplify` | Audit for unnecessary complexity and propose deletions — one file or the whole codebase. |
| `/fstack-design` | Make UI match the project's existing styles and clean up design slop. |
| `/fstack-counselors` | Ask the 3 most capable models the same question and synthesize one verdict. |
| `/fstack-check` | Review finished work: does it work, does it match the plan, is it simple. |
| `/fstack-document` | Write docs/ for the project, ELI5 to deep. Run again to update them. |
| `/fstack-learn` | Capture one lesson in three lines, so future sessions start smarter. |
| `/fstack-push` | Commit any uncommitted work and push to the remote. Nothing else. |

## Routing map

| Situation | Skill |
|---|---|
| Product idea, not sure it's worth building | `/fstack-roast` |
| New project, the agent lacks business context | `/fstack-interview` |
| Vague or new idea for this project | `/fstack-nail` |
| Idea is clear, no plan exists | `/fstack-plan` |
| Plan exists and is approved | `/fstack-build` |
| Feels bloated or sloppy — one file or the whole codebase | `/fstack-simplify` |
| UI looks off or inconsistent with the rest | `/fstack-design` |
| Big decision, one opinion is not enough | `/fstack-counselors` |
| Work is done, needs review | `/fstack-check` |
| Project needs docs, or the docs have gone stale | `/fstack-document` |
| Something worth remembering just happened | `/fstack-learn` |
| Just want it committed and pushed | `/fstack-push` |

## Stop and ask

If you truly cannot tell which skill fits, ask **one** clarifying question. Then route.

If still ambiguous after the answer, route to `/fstack-nail`. That is what it is for.

## Must NOT

- Route when there is no task. List the skills and ask instead.
- Chain multiple skills. Pick one, run it, stop.
- Ask more than one clarifying question before routing.
- Plan, code, or review inside this skill. Route and hand off.

## Example

> User: `/fstack`
>
> Agent: *(lists the twelve skills with one-line descriptions)* "That's the full set. What do you want to do?"

> User: `/fstack I want to add dark mode to my site`
>
> Agent: "This is a new feature with no plan yet, so I'll start with `/fstack-nail` to make sure I understand what you want." *(runs /fstack-nail)*
