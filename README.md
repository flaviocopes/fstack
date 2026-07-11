# fstack — the simple stack

Agent skills that ask: can this be less?

## The problem

Skill collections keep growing. 30 skills, personas, pipelines, voice triggers. You can't hold that in your head, so you stop using it.

## The idea

fstack is 10 skills. Plain names, one job each.

The agent works in small steps and checks in with you. You approve; it executes. No long autonomous runs.

One skill — `/simplify` — exists only to remove things. No other stack has that.

## Install

```bash
npx skills@latest add flaviocopes/fstack
```

That's it. No dependencies, no build step, no config.

## The core loop

```
align → plan → build → check → ship
```

Before the loop:

- `/roast` — when you have a product idea and want honest pushback before writing code
- `/interview` — when the agent should know the business behind the project; it asks, you answer, the answers land in AGENTS.md

Sprinkle in anywhere:

- `/simplify` — when something feels bloated
- `/learn` — when something is worth remembering

Don't know where to start? `/fstack` is the front door. Describe what you want and it picks the right skill.

## The 10 skills

| Skill | What it does |
|---|---|
| `/fstack` | The front door. Picks the right skill for your request. |
| `/roast` | Stress-tests a product idea. Ends with a verdict and the smallest version worth building. |
| `/interview` | Interviews you about the product — demand, customer, pricing, risks — and records the answers in AGENTS.md. |
| `/align` | Asks up to 5 questions, then confirms a 3-line summary before any work starts. |
| `/plan` | Writes a one-page plan with a mandatory "what we're NOT doing" section. |
| `/build` | Implements the plan one small step at a time, asking at real choices. |
| `/simplify` | Audits a plan, diff, or file and proposes deletions. Only deletions. |
| `/check` | Three questions: does it work, does it match the plan, is it simple. |
| `/learn` | Captures one lesson in three lines, so future sessions start smarter. |
| `/ship` | Tests, commit, push, PR. Stops there — deploying is your call. |

## Philosophy

1. Short sentences. One idea per sentence.
2. Short paragraphs, then a blank line.
3. No jargon. If a plumber wouldn't understand the word, find a simpler one.
4. No personas. Skills describe steps, not characters.
5. One job per skill.
6. Prefer deletion. When something can be shorter, make it shorter.
7. Every skill fits in ~150 lines. If it doesn't, it's doing too much.
8. The human drives. Skills pause at decision points and ask.
9. Agent-agnostic. Plain markdown, no hardcoded tool names.
10. Plain-English tone. Like explaining to a friend.

## Credits

fstack exists because of the stacks it distills. [gstack](https://github.com/garrytan/gstack) by Garry Tan gave it the full lifecycle idea and, through office hours, the idea-roasting step. [pstack](https://cursor.com/marketplace/cursor/pstack) by Lauren Tan gave it design-before-code and blast-radius thinking. [Compound Engineering](https://github.com/EveryInc/compound-engineering-plugin) by Every gave it the plan artifact and the lesson-capture step. [Matt Pocock's skills](https://github.com/mattpocock/skills) gave it grilling, the two-axis review, and the small-skills shape. Go look at all four — they're generous, thoughtful work.

## License

MIT
