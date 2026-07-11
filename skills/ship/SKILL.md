---
name: ship
description: Run tests, commit, push, and open a PR for reviewed work. Use when /check said "Ready to ship" and the user wants the change out the door.
---

# /ship

Get reviewed work out the door. Tests first, then commit, push, and PR.

## When to use

- `/check` ended with "Ready to ship".
- The user says to ship after a successful review.

Do not ship if `/check` has not passed or the user has not confirmed.

## Steps

1. Run the project's test suite, or the closest equivalent.
   If anything fails, stop. Report the failure. Do not commit or push.

2. Write a one-paragraph summary of what is being shipped.
   Include what changed and why it matters.

3. Show the summary to the user and wait for go-ahead.
   Do not commit until they confirm.

4. Commit with a plain one-line message describing the change.

5. Push to the current branch.

6. If the project uses pull requests, open one.
   Use the summary from step 2 as the PR body.
   If the project does not use PRs, stop after the push.

7. Suggest `/learn` if anything from this cycle is worth keeping.

## Must NOT

- Deploy. Shipping ends at push or PR.
- Force-push.
- Skip hooks.
- Amend commits that are already on the remote.
- Ship when tests fail.
- Ship when `/check` has not said "Ready to ship".
- Commit or push before the user approves the summary.

## Example

> Agent: "Tests passed. Shipping: dark mode toggle in the header, preference stored in localStorage, no flash on load. Ready to commit and push?"
>
> User: "Yes."
>
> Agent: "Committed, pushed, PR opened. Worth running `/learn` about the inline script fix?"
