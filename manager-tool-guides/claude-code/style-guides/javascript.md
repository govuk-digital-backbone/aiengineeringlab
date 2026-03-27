# JavaScript style guide for CLAUDE.md

Paste the relevant sections of this file into your project's `CLAUDE.md` to enforce JavaScript coding standards aligned with the [GDS Way JavaScript guidance](https://gds-way.digital.cabinet-office.gov.uk/manuals/programming-languages/js.html).

---

## JavaScript coding standards

Follow the [StandardJS](https://standardjs.com) style or the [GOV.UK Frontend JavaScript conventions](https://frontend.design-system.service.gov.uk/coding-standards/js/). Use [ESLint](https://eslint.org) with the appropriate GDS configuration for linting.

### Formatting

You should:

- use 2-space indentation - never use tabs
- limit lines to 100 characters
- use semicolons at the end of statements
- use single quotes for strings unless the string contains a single quote
- use [prettier](https://prettier.io) for automatic formatting where the team agrees on it

### Syntax and language features

You should:

- use ES2015+ (ES6+) syntax - do not use `var`; use `const` by default and `let` when reassignment is needed
- use arrow functions for callbacks and anonymous functions
- use template literals (`` `Hello, ${name}` ``) instead of string concatenation
- use destructuring assignment for objects and arrays where it improves readability
- use default parameter values instead of conditional assignments inside function bodies
- use `async`/`await` for asynchronous code - avoid callback pyramids and long `.then()` chains

### Modules

You should:

- use ES module syntax (`import`/`export`) for new code
- use `require`/`module.exports` only in Node.js projects that cannot use ES modules
- export one primary thing per file - name the file after the export
- avoid circular dependencies

### Naming

You should:

- use `camelCase` for variables and function names
- use `PascalCase` for classes and constructor functions
- use `UPPER_SNAKE_CASE` for module-level constants that are truly constant
- use descriptive names - avoid single-letter variables except in short loop bodies

### Functions and classes

You should:

- keep functions under 20 lines where possible
- write JSDoc comments for all exported functions
- prefer pure functions without side effects
- avoid mutating function arguments

### Frontend JavaScript

You should:

- follow the [GOV.UK Design System](https://design-system.service.gov.uk) patterns and components
- use progressive enhancement - ensure core functionality works without JavaScript
- do not rely on JavaScript for rendering critical page content
- use the GOV.UK Frontend npm package rather than reimplementing components
- write accessible JavaScript - do not remove focus indicators or break keyboard navigation

### Error handling

You should:

- handle promise rejections explicitly - use `try`/`catch` with `async`/`await`
- never silently swallow errors - log them with enough context to debug
- validate and sanitise all user input before processing

### Testing

You should:

- write tests using [Jest](https://jestjs.io) or [Vitest](https://vitest.dev)
- write end-to-end tests using [Cypress](https://cypress.io) or [Playwright](https://playwright.dev)
- name test files `*.test.js` or `*.spec.js` alongside the file under test
- avoid testing implementation details - test behaviour and output

### Tooling

You should:

- run `eslint` and your formatter check in CI
- use `npm ci` in CI pipelines to ensure reproducible installs from `package-lock.json`
- commit `package-lock.json` to source control
- avoid installing unnecessary dependencies - audit with `npm audit` regularly

### Security

You should:

- never hardcode secrets, API keys, or credentials - use environment variables
- sanitise all user-supplied content before inserting into the DOM to prevent XSS
- use `Content-Security-Policy` headers and avoid `eval()` and `innerHTML` with user data
- set appropriate CORS policies on APIs
