---
name: add-or-update-design-tokens
description: Workflow command scaffold for add-or-update-design-tokens in stisla.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-design-tokens

Use this workflow when working on **add-or-update-design-tokens** in `stisla`.

## Goal

Adds or updates design tokens for color, surface, or theme variables, affecting multiple components.

## Common Files

- `src/scss/tokens/_variables.scss`
- `src/scss/tokens/_variables-dark.scss`
- `src/scss/tokens/_root.scss`
- `src/scss/components/_*.scss`
- `V3.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add variables in src/scss/tokens/_variables.scss and/or _variables-dark.scss
- Optionally update src/scss/tokens/_root.scss for runtime CSS vars
- Update affected component SCSS files to use the new/changed tokens
- Update V3.md documentation if the token model changes

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.