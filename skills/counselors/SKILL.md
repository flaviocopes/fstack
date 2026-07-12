---
name: counselors
description: Ask the same question to the 3 most capable models available and synthesize their independent answers into one verdict. Use for decisions big enough to want more than one opinion.
---

# /counselors

A council of three models on one question. Each counselor answers independently, then the answers get compared and resolved into one definitive recommendation — with each counselor's opinion summarized, especially where they disagree.

## When to use

- A decision is big enough that one model's opinion is not enough.
- Architecture choices, tricky trade-offs, "should we do X or Y" questions.
- You want a second opinion on a plan, a diff, or a design before committing to it.

## Steps

1. Turn the question into one **self-contained brief**: the question, the relevant context (files, constraints, what was already tried), and the answer format you want. Every counselor gets this exact brief and nothing else.
2. Pick the council: the **3 most capable models available** in this environment. Tell the user who is on the council before dispatching. If the environment cannot mix models, run 3 independent sessions of the best one — independent runs still surface disagreement. If the environment cannot run independent agents at all, say so and answer directly. Never fake a council.
3. Dispatch the same brief to each counselor, **in parallel and read-only**. No counselor sees another's answer.
4. Read all three answers. Map where they agree and where they disagree.
5. Deliver the result in two parts:
   - **The verdict.** One definitive answer. When the counselors disagree, pick a side and say why — do not average.
   - **The council.** One summary per counselor, 2 to 3 lines each, model named. Flag every disagreement and how the verdict resolves it. A 2–1 split is reported as 2–1.
6. **Stop.** Acting on the verdict is a separate decision. If the user wants to build, suggest `/plan` or `/build`.

## Must NOT

- Let counselors see each other's answers before giving their own. Independence is the whole point.
- Average disagreement into mush. "All approaches have merit" is not a verdict.
- Hide dissent. If one counselor disagrees, the user hears about it and why.
- Let counselors change files. The council reads and opines; it never writes.
- Convene the council for trivial questions. Three models on "what should I name this variable" is waste.

## Example

> User: `/counselors` should we move auth from server sessions to JWTs?
>
> Agent: "Council: [the 3 strongest models available here]. Sending each the same brief: your auth code, the scaling constraint you mentioned, and the question. Back in a few minutes."
>
> *(three independent answers come back)*
>
> Agent: "**Verdict: keep server sessions.** The council split 2–1.
>
> **Counselor 1** — keep sessions. Your app is server-rendered with one backend; JWTs add revocation problems and solve a distribution problem you do not have.
>
> **Counselor 2** — keep sessions, same core reason. Adds: if the API later needs tokens, mint short-lived ones from the session rather than switching wholesale.
>
> **Counselor 3** — move to JWTs, arguing for the future multi-service case. I sided against because that case is hypothetical and the revocation cost is immediate.
>
> Want this turned into a note in the plan, or leave it as a decision?"

## Credit

This distills the council-of-advisors pattern from [counselors](https://github.com/aarondfrancis/counselors) by Aaron Francis. His CLI fans a prompt out to locally installed agent CLIs; this skill uses whatever your environment already has. If the `counselors` CLI is installed, it is a fine way to run the fan-out.
