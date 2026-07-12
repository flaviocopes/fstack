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
2. **If there is no task** — the user typed `/fstack` alone, or just asked what fstack can do — list the ten skills with a one-line description each, then stop and ask what they want to do. Do not route or guess. This is the menu below.
3. **If there is a task** — match it to one of the ten skills below.
4. Say which skill you picked and why, in one sentence.
5. Run that skill. Do not chain others.

## The skills

When there is no task, show this list:

| Skill | What it does |
|---|---|
| `/roast` | Stress-test a product idea. Ends with a verdict and the smallest version worth building. |
| `/interview` | Ask about the product — demand, customer, pricing, risks — and record the answers in AGENTS.md. |
| `/align` | Ask up to 5 questions, then confirm a short summary before any work starts. |
| `/plan` | Write a one-page plan with a mandatory "what we're NOT doing" section. |
| `/build` | Implement the plan one small step at a time, asking at real choices. |
| `/simplify` | Audit a plan, diff, or file and propose deletions. Only deletions. |
| `/counselors` | Ask the 3 most capable models the same question and synthesize one verdict. |
| `/check` | Review finished work: does it work, does it match the plan, is it simple. |
| `/learn` | Capture one lesson in three lines, so future sessions start smarter. |
| `/ship` | Tests, commit, push, PR. Stops there — deploying is your call. |

## Routing map

| Situation | Skill |
|---|---|
| Product idea, not sure it's worth building | `/roast` |
| New project, the agent lacks business context | `/interview` |
| Vague or new idea for this project | `/align` |
| Idea is clear, no plan exists | `/plan` |
| Plan exists and is approved | `/build` |
| Feels bloated or too complex | `/simplify` |
| Big decision, one opinion is not enough | `/counselors` |
| Work is done, needs review | `/check` |
| Something worth remembering just happened | `/learn` |
| Reviewed and ready to go out | `/ship` |

## Stop and ask

If you truly cannot tell which skill fits, ask **one** clarifying question. Then route.

If still ambiguous after the answer, route to `/align`. That is what it is for.

## Must NOT

- Route when there is no task. List the skills and ask instead.
- Chain multiple skills. Pick one, run it, stop.
- Ask more than one clarifying question before routing.
- Plan, code, or review inside this skill. Route and hand off.

## Example

> User: `/fstack`
>
> Agent: *(lists the ten skills with one-line descriptions)* "That's the full set. What do you want to do?"

> User: `/fstack I want to add dark mode to my site`
>
> Agent: "This is a new feature with no plan yet, so I'll start with `/align` to make sure I understand what you want." *(runs /align)*
