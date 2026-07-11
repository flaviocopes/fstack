---
name: roast
description: Stress-test a product idea before any code gets written. Use when you have an idea and want honest pushback, or you are not sure something is worth building.
---

# /roast

Honest pushback on a product idea before anyone writes code. The goal is not to kill the idea. The goal is to find the smallest true version of it — or to save you months building a version nobody needs.

## When to use

- You have a product idea and want it challenged.
- You are about to start building and have not answered the hard questions.
- Someone asks "is this worth building?"

## Steps

1. Read the idea. Look at any notes, code, or links that exist.
2. Ask up to **5 hard questions**, all in one message. Pick the ones this idea actually needs:
   - Who is the one person who needs this most? Describe them, specifically.
   - What do they do today to solve this, even badly? What does that cost them?
   - What is the strongest evidence someone wants this? Someone who would be upset if it vanished, not someone who said "cool".
   - What is the smallest version someone would pay for this week?
   - How will the first 100 people find it?
3. **Stop and wait** for answers. A vague answer gets one follow-up push, not three.
4. Deliver the roast, in three parts:
   - **What is real.** The parts backed by evidence or a lived problem.
   - **What is wishful.** The parts held up by hope. Say it plainly.
   - **The wedge.** The smallest version worth building. Shippable in days, not months.
5. End with one verdict line: **Build the wedge**, **Shrink it**, or **Don't build it: [reason]**.
6. **Stop and ask** what to do next. If building, suggest `/align` with the wedge as the task.

## The principles it checks against

- The status quo is the real competitor. If people solve this with "nothing", the pain is probably not real.
- Small and shipped beats big and planned. The first version should exist in days.
- Charge real money, simply. If the pricing needs a spreadsheet, the product is not ready.
- Build for one specific person. Often that person is you. That is fine — say so.
- A demo is not a product. Auth, boundaries, and failure handling arrive later, with interest.
- Distribution is part of the product. If nobody can find it, it does not exist.
- Boring tech ships. Pick the stack you already know.

## Must NOT

- Flatter. If the idea is weak, say so plainly and say why.
- Kill ideas for sport. Every roast ends with the best small version, even when the verdict is harsh.
- Invent numbers, market sizes, or fake research.
- Start planning or building. The skill ends at the verdict.

## Example

> User: `/roast` an app where AI generates personalized bedtime stories for kids
>
> Agent: "Three questions: 1) Who is the one parent you know who needs this most, and what do they do tonight instead? 2) What evidence do you have that they want this — has anyone asked you for it, or paid for something like it? 3) What is the smallest version someone would pay for this week?"
>
> User: *(answers)*
>
> Agent: "What is real: you have a four-year-old and you invent a story every night. You are the user, and the problem is lived.
>
> What is wishful: 'parents will pay a monthly subscription'. Nobody you named has asked for this, and the status quo — making it up, or a book — costs them nothing.
>
> The wedge: one themed story pack on a one-page site, one-time price. No app, no accounts, no generation pipeline.
>
> **Shrink it.** Build the pack, show it to five parents. If three pay, `/align` the next slice."
