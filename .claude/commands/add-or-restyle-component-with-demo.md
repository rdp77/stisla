---
name: add-or-restyle-component-with-demo
description: Workflow command scaffold for add-or-restyle-component-with-demo in stisla.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-restyle-component-with-demo

Use this workflow when working on **add-or-restyle-component-with-demo** in `stisla`.

## Goal

Implements a new UI component or restyles an existing one, and adds a corresponding demo documentation page.

## Common Files

- `src/scss/components/_*.scss`
- `src/scss/bundles/stisla-full.scss`
- `src/scss/tokens/_variables.scss`
- `src/scss/tokens/_variables-dark.scss`
- `src/site/pages/*.njk`
- `src/site/partials/_site-sidebar.njk`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update the component SCSS file in src/scss/components/_component-name.scss
- Import the component in src/scss/bundles/stisla-full.scss
- Add or update theme tokens in src/scss/tokens/_variables.scss and/or _variables-dark.scss if needed
- Create a demo page in src/site/pages/component-name.njk
- Optionally update src/site/partials/_site-sidebar.njk to add the new page to the sidebar

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.