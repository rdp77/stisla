```markdown
# stisla Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches the core development patterns, coding conventions, and collaborative workflows used in the **stisla** repository—a modern JavaScript project built with Vite. The codebase focuses on modular Bootstrap-based UI components, custom theming via SCSS tokens, and a documentation/demo site powered by Nunjucks. You'll learn how to contribute new components, manage design tokens, extend the demo infrastructure, and update architectural documentation, all while following established conventions and commit patterns.

## Coding Conventions

- **File Naming:** Use `kebab-case` for all files.
  - Example: `site-sidebar.njk`, `site.js`, `variables-dark.scss`
- **Import Style:** Always use relative imports.
  ```js
  // Good
  import { myFunction } from './utils.js';
  ```
- **Export Style:** Use named exports.
  ```js
  // Good
  export function myFunction() { ... }
  ```
- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/) with these prefixes:
  - `feat`: New features or components
  - `fix`: Bug fixes
  - `docs`: Documentation changes
  - `refactor`: Code refactoring
  - `chore`: Maintenance tasks
  - Example: `feat: add card component with demo page`
- **SCSS Structure:** 
  - Components: `src/scss/components/_component-name.scss`
  - Bundles: `src/scss/bundles/stisla-full.scss`
  - Tokens: `src/scss/tokens/_variables.scss`, `_variables-dark.scss`
- **Demo Pages:** Nunjucks templates in `src/site/pages/*.njk`
- **Documentation:** Main spec/roadmap in `V3.md`

## Workflows

### Add or Restyle Component with Demo
**Trigger:** When adding a new Bootstrap-based component, restyling an existing one, or documenting it on the site  
**Command:** `/new-component`

1. **Create or update the SCSS file** for the component in `src/scss/components/_component-name.scss`.
2. **Import the component** in `src/scss/bundles/stisla-full.scss`:
   ```scss
   @import '../components/component-name';
   ```
3. **Add or update theme tokens** in `src/scss/tokens/_variables.scss` and/or `_variables-dark.scss` if needed.
4. **Create a demo page** in `src/site/pages/component-name.njk`:
   ```njk
   {% extends "layouts/base.njk" %}
   {% block content %}
     <h1>Component Name Demo</h1>
     {% include "partials/_component-name-demo.njk" %}
   {% endblock %}
   ```
5. **Optionally update the sidebar** in `src/site/partials/_site-sidebar.njk` to link the new page.

---

### Add or Update Design Tokens
**Trigger:** When introducing or adjusting design tokens for theming, surfaces, or color  
**Command:** `/edit-token`

1. **Edit or add variables** in `src/scss/tokens/_variables.scss` and/or `_variables-dark.scss`:
   ```scss
   $stisla-primary: #007bff;
   ```
2. **Optionally update runtime CSS vars** in `src/scss/tokens/_root.scss`.
3. **Update affected component SCSS files** to use the new/changed tokens.
4. **Update documentation** in `V3.md` if the token model changes.

---

### Add or Update Demo Infrastructure
**Trigger:** When enhancing how component demos are rendered, styled, or interacted with  
**Command:** `/edit-demo-infra`

1. **Edit or add Nunjucks partials/macros** in `src/site/partials/_demo.njk`.
2. **Edit or add site scripts** in `src/site/scripts/site.js`.
3. **Edit or add site styles** in `src/site/styles/site.scss`.
4. **Edit or add Nunjucks filters or build tools** in:
   - `tools/nunjucks-filters.mjs`
   - `tools/render-site.mjs`
   - `tools/vite-plugin-nunjucks.mjs`
5. **Update documentation** in `V3.md` if site conventions or demo patterns change.

---

### Update Architecture or Spec Documentation
**Trigger:** When documenting architectural decisions, updating the roadmap, or clarifying workflow rules  
**Command:** `/edit-spec`

1. **Edit `V3.md`** to add or update sections on architecture, tokens, repo layout, workflows, or open questions.
2. **Optionally update related files** (e.g., `src/site/layouts/base.njk`) if documentation reflects implementation changes.

## Testing Patterns

- **Test Files:** Use the pattern `*.test.*` (e.g., `button.test.js`).
- **Testing Framework:** Not specified in the repository (add documentation if you introduce or identify one).
- **Best Practice:** Place tests alongside the code they test, using named exports for test utilities.

## Commands

| Command           | Purpose                                                                 |
|-------------------|-------------------------------------------------------------------------|
| /new-component    | Add or restyle a component and its demo page                            |
| /edit-token       | Add or update design tokens for theming                                 |
| /edit-demo-infra  | Improve or extend demo/documentation infrastructure                     |
| /edit-spec        | Update architectural documentation or project roadmap                   |
```