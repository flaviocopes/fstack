---
name: fstack
description: Route a task to the right fstack skill when you invoke /fstack, ask which skill to use, or describe work without naming a skill.
---

# /fstack

The front door for fstack. Read what the user wants. Pick one skill. Run it. Stop.

## When to use

- The user invokes `/fstack`.
- The user asks which fstack skill fits their task.
- The user describes work and mentions fstack without naming a skill.

## Steps

1. Read the user's request.
2. Match it to one of the nine skills below.
3. Say which skill you picked and why, in one sentence.
4. Run that skill. Do not chain others.

## Routing map

| Situation | Skill |
|---|---|
| Product idea, not sure it's worth building | `/roast` |
| New project, the agent lacks business context | `/interview` |
| Vague or new idea for this project | `/align` |
| Idea is clear, no plan exists | `/plan` |
| Plan exists and is approved | `/build` |
| Feels bloated or too complex | `/simplify` |
| Work is done, needs review | `/check` |
| Something worth remembering just happened | `/learn` |
| Reviewed and ready to go out | `/ship` |

## Stop and ask

If you truly cannot tell which skill fits, ask **one** clarifying question. Then route.

If still ambiguous after the answer, route to `/align`. That is what it is for.

## Must NOT

- Chain multiple skills. Pick one, run it, stop.
- Ask more than one clarifying question before routing.
- Plan, code, or review inside this skill. Route and hand off.

## Example

> User: `/fstack I want to add dark mode to my site`
>
> Agent: "This is a new feature with no plan yet, so I'll start with `/align` to make sure I understand what you want." *(runs /align)*
