---
name: fstack-document
description: Write documentation for the whole project into docs/, from an ELI5 overview to deeper explanations. Run it again to update the docs with changes since they were written. Use for a new project's docs or to refresh stale ones.
---

# /fstack-document

Write documentation about the current project into `.md` files, in three layers: a plain-English overview, a how-it-works explanation, and a deeper reference. Run it once to create the docs. Run it again and it updates them to match the code as it is now.

## When to use

- The project has little or no documentation.
- The docs exist but have drifted from the code.
- The user invokes `/fstack-document`.

## Steps

1. Read the project: structure, entry points, main modules, data model, config, and how to run and test it.
2. Check whether `docs/` already has the fstack doc set (the three files below).
   - **If not** — create mode.
   - **If yes** — update mode. Re-read the project, compare against the existing docs, and change only what the code changed. Keep human edits where they still hold. Do not rewrite from scratch.
3. Write or update these three files, plain to deep:
   - `docs/overview.md` — **ELI5.** What this project is, what it does, who it is for, in words a non-expert understands. No jargon.
   - `docs/architecture.md` — **How it works.** The main pieces, how they fit, how data flows, the decisions that shaped it.
   - `docs/reference.md` — **The details.** Directories and key files, config and environment, how to run, test, and build.
4. Show a short summary of what you wrote or changed. In update mode, say what was added, what was revised, and anything that looks removed from the code.

## Keeping it in sync

- Match the docs to the code as it is now — not the git history, not a changelog.
- If a file, module, or feature the docs mention no longer exists, flag it and remove that part.
- If something new exists that the docs miss, add it in the right layer.

## Must NOT

- Sprawl into many files. Three layers, three files. If a section grows huge, it is a sign the project itself may be too complex.
- Invent behavior. Document what the code does, not what it should do. If something is unclear, say so rather than guessing.
- Rewrite docs the code did not change. Update mode touches only what moved.
- Include secrets — keys, tokens, or `.env` values.

## Example

> User: `/fstack-document`
>
> Agent: "No `docs/` yet, so creating the set. Wrote three files:
> - `docs/overview.md` — what the app is, in plain words.
> - `docs/architecture.md` — Astro pages, the Convex backend, the auth flow.
> - `docs/reference.md` — directory map, env vars, and the run/test/build commands.
> Skim them?"

> User: `/fstack-document` *(a week later)*
>
> Agent: "Docs exist — update mode. Changes: added the new `/api/export` route to architecture and reference. Revised the auth section — it moved from sessions to magic links. The `themes` module the docs mentioned is gone from the code; I removed that paragraph."
