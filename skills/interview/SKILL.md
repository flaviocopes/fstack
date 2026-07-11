---
name: interview
description: Interview the user about the product behind the project and record the answers in AGENTS.md (or CLAUDE.md). Use when starting a project, or when the agent keeps guessing at business context it should already know.
---

# /interview

A structured interview about the product behind the code. The answers go into the project's agent context file, so every future session starts knowing what you are building, for whom, and why.

## When to use

- You are starting a new project.
- The agent keeps making product guesses it should not have to make.
- After `/roast`, when the verdict was to build.

## Steps

1. Read the project first: README, AGENTS.md or CLAUDE.md, the code. Note what is already answered. Never ask something the project already tells you.
2. Pick the question areas that fit this project from the list below. Write the actual questions yourself, tuned to this specific product. Do not copy the samples word for word.
3. Ask in rounds of **3 to 5 questions**. Wait for answers before the next round. Stop after about 4 rounds, or earlier if the user says enough. "I don't know" is a valid answer — record it as an open question, do not push past it twice.
4. Draft a **Product context** section in plain markdown. Show it to the user.
5. **Stop and ask** before writing anything. Then add the section to AGENTS.md — or CLAUDE.md if that is what the project uses. If neither exists, create AGENTS.md. Never delete what is already there; if the section exists, update it.

## Question areas

Pick what fits. Skip what does not. Add areas this project needs that are not listed.

- **Demand** — Is there enough customer demand for this? Are people already searching for it, and where? How easy is it to get someone to sign up?
- **Customer** — Who exactly is this for? Where do they spend their time? Who pays, and is that the same person who uses it?
- **Business model** — What is the pricing? Can price times realistic volume produce revenue worth the effort? One-time or recurring, and why?
- **Founder fit** — Is this an industry or category you want to be in for years? What is your unfair advantage here?
- **Status quo** — What do people use today instead, even badly? What would make them switch?
- **Distribution** — How will the first 100 people find it? What channel do you already have?
- **Scope** — What is in the first version? What is deliberately out?
- **Risks** — What is most likely to kill this? Which single assumption, if wrong, ends the project?
- **Success** — What does "working" look like in six months? What number would tell you to stop?

## The artifact

The section written to the context file looks like this:

```markdown
## Product context

- **Product:** one line on what this is.
- **Customer:** who it is for, specifically.
- **Demand:** the evidence, in one line.
- **Business model:** pricing and why it can work.
- **Status quo:** what it replaces.
- **Distribution:** how people find it.
- **Not doing:** what is deliberately out of scope.
- **Open questions:** everything answered "I don't know".
```

One line per answer. This is context for an agent, not a business plan. If an answer needs a paragraph, it is two answers.

## Must NOT

- Use a fixed questionnaire. Choose and phrase every question for this specific project.
- Ask everything at once. Rounds of 3 to 5, then wait.
- Answer the questions for the user, or invent facts to fill gaps.
- Overwrite or delete existing content in AGENTS.md or CLAUDE.md.
- Give a verdict on the idea. That is `/roast`'s job. This skill records; it does not judge.

## Example

> User: `/interview`
>
> Agent: *(reads README and code)* "This looks like an invoicing tool for freelancers. First round, three questions: 1) Who is the one freelancer you are building this for — what kind of work do they do? 2) What do they use today to send invoices, and what does it cost them? 3) Are you planning one-time pricing or a subscription, and why?"
>
> User: *(answers, third answer is "not sure yet")*
>
> Agent: *(two more rounds, then)* "Here is the Product context section I would add to AGENTS.md — pricing is listed under open questions. Want me to write it?"
