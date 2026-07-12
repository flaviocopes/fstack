---
name: fstack-push
description: Commit any uncommitted work and push it to the remote. Nothing else — no tests, no PR, no deploy. Use when you just want your changes saved and pushed.
---

# /fstack-push

Commit whatever is uncommitted, then push to the remote. That is the whole job.

## When to use

- You want your current work committed and pushed, now.
- The user invokes `/fstack-push`.

## Steps

1. Check the working tree. If there are uncommitted changes, stage them and commit with a plain one-line message describing what changed. If everything is already committed, skip to the push.
2. Push the current branch to its remote.
3. Report what happened in one line: the commit (if any) and the push result.

## Must NOT

- Run tests, open a PR, or deploy. This skill only commits and pushes.
- Force-push, or push to a different branch than the current one.
- Skip hooks.
- Amend commits that are already on the remote.
- Commit files that look like secrets — `.env`, keys, credentials. Warn instead.

## Example

> User: `/fstack-push`
>
> Agent: "Committed 'Add export button to settings' and pushed to `main`. Done."

> User: `/fstack-push` *(nothing uncommitted)*
>
> Agent: "Nothing to commit. Pushed the 2 local commits to `main`."
