# HTML and CSS style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce HTML and CSS coding standards aligned with the [GDS Way HTML and CSS guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/html-css.html).

---

## HTML and CSS coding standards

Follow the [GOV.UK Design System](https://design-system.service.gov.uk) and the [GOV.UK Frontend](https://frontend.design-system.service.gov.uk) conventions. Use [stylelint](https://stylelint.io) with the `stylelint-config-gds` configuration for CSS linting.

### HTML

#### Formatting

You should:

- use 2-space indentation - never use tabs
- use lowercase for all HTML element names and attribute names
- always quote attribute values using double quotes
- omit the trailing slash on void elements (use `<br>` not `<br />`)
- add a newline at the end of every file

#### Structure

You should:

- use semantic HTML5 elements (`<main>`, `<nav>`, `<header>`, `<footer>`, `<article>`, `<section>`, `<aside>`)
- use `<h1>` through `<h6>` for headings in a logical document hierarchy. Do not skip heading levels
- use `<button>` for actions and `<a>` for navigation. Do not style a `<div>` or `<span>` as a button
- use `<label>` elements for all form inputs - associate them explicitly using `for` and `id` attributes
- include a `lang` attribute on the `<html>` element (`lang="en"`)

#### Accessibility

You should:

- all images must have an `alt` attribute - use an empty `alt=""` for decorative images
- use ARIA attributes sparingly and only where native HTML semantics are insufficient
- ensure interactive elements are reachable and operable by keyboard
- ensure colour contrast meets [WCAG 2.1 AA](https://www.w3.org/TR/WCAG21/) (4.5:1 for normal text, 3:1 for large text)
- test with a screen reader (NVDA, VoiceOver, or JAWS) before releasing

#### GOV.UK Design System

You should:

- use [GOV.UK Frontend](https://frontend.design-system.service.gov.uk) components and patterns rather than reimplementing them
- follow the [GOV.UK service manual](https://www.gov.uk/service-manual) for interaction patterns and user research
- use the GOV.UK crown and branding assets from the official npm package

### CSS

#### Formatting

You should:

- use 2-space indentation
- place each selector, property, and closing brace on its own line
- use a space before the opening brace and after the colon in declarations
- use lowercase and hyphens for class names (kebab-case)
- use shorthand properties where appropriate

#### Naming and structure

You should:

- use [BEM (Block Element Modifier)](https://getbem.com) naming conventions for component-level CSS
- prefix component class names with a namespace relevant to your project or team
- avoid using IDs for styling - reserve IDs for JavaScript hooks and accessibility targets
- use CSS custom properties (variables) for shared values like colours, spacing, and typography

#### Specificity and cascade

You should:

- keep specificity low - avoid `!important` except to override third-party styles
- do not use inline styles in HTML except for dynamically computed values that cannot be expressed as classes
- structure CSS in the following order within a file: custom properties, base resets, layout, components, utilities

#### Sass and pre-processing

You should:

- use [Sass](https://sass-lang.com) (`.scss` syntax) if a pre-processor is required
- follow the [GOV.UK Frontend Sass conventions](https://frontend.design-system.service.gov.uk/coding-standards/css/)
- limit nesting to 3 levels maximum
- use `@use` and `@forward` instead of `@import` in new Sass code
- keep mixins and functions in dedicated partial files

#### Tooling

You should:

- run `stylelint` in your CI pipeline - fix all warnings before merging
- use [PostCSS Autoprefixer](https://github.com/postcss/autoprefixer) to handle vendor prefixes automatically
- run accessibility checks using [axe-core](https://github.com/dequelabs/axe-core) or [pa11y](https://pa11y.org) in CI

#### Performance

You should:

- minimise CSS file size - remove unused rules using [PurgeCSS](https://purgecss.com) or equivalent
- avoid CSS that triggers layout reflow - prefer `transform` and `opacity` for animations
- load critical CSS inline for above-the-fold content where performance is a concern
