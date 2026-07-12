---
name: fstack-design
description: Fix AI-generated design so it matches the project's existing styles and is genuinely good. Use when new UI looks off, inconsistent, or like generic AI slop.
---

# /fstack-design

Agents write design slop: random gradients, five font sizes, off-palette colors, spacing that never repeats. This skill makes UI adhere to the styles the project already has, and cleans up the rest against plain design sense.

The rule it enforces: **match what exists first.** New UI should look like it belongs, not like it was pasted in from another app.

## When to use

- New or changed UI looks off, generic, or inconsistent with the rest.
- An agent just built a screen and it feels like slop.
- You invoke `/fstack-design` on a page, component, or the whole UI.

## Steps

1. Learn the existing design system **before touching anything**. Read the stylesheets, tokens, theme, and a few well-made existing components. Note the real palette, the type scale, the spacing scale, radius, shadows, and the component patterns already in use.
2. Review the target UI against two things:
   - **The existing system** — where does it invent colors, sizes, spacing, or components instead of reusing what exists?
   - **Plain design sense** — hierarchy, alignment, consistent spacing, restraint. Flag the slop tells: unmotivated gradients, too many font sizes, inconsistent padding, random shadows, emoji as icons, off-palette one-off colors, redundant wrapper divs.
3. Produce a short findings list. Each item: what is off, and the existing token or pattern it should use instead.
4. **Stop and ask** which to apply.
5. Fix the approved items, **one screen or component at a time**, reusing existing tokens and classes — never inventing new ones unless the user agrees the system genuinely lacks something. Show the diff.

## Must NOT

- Invent new colors, fonts, spacing values, or components when the project already has ones that fit.
- Redesign. This aligns and cleans up; it does not reimagine the product.
- Add a UI framework or component library to "fix" things.
- Apply changes without approval.

## Example

> User: `/fstack-design` the new settings page looks off
>
> Agent: "Read the design system first. Findings on the settings page:
> 1. Uses `#3b82f6` for the save button — the app's primary is `--color-accent`. Use the token.
> 2. Three heading sizes here; the rest of the app uses two (`--text-lg`, `--text-base`). Drop the middle one.
> 3. Card padding is `18px` — every other card uses `--space-4` (16px). Match it.
> 4. Gradient header background — nothing else in the app uses gradients. Use the flat surface color.
> 5. Emoji icons in the tabs; the app uses the icon set in `src/icons`. Swap them.
>
> Fix all, or pick? I'll do it one section at a time and show the diff."
