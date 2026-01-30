> ALPHA
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Using instruction files for AI code assistants

## Executive summary

This playbook provides practical guidance on creating and managing instruction files for AI code assistants across government projects. Instruction files ensure AI tools understand your project's standards, compliance requirements and coding patterns, reducing the need to repeat context in every interaction.

Key benefits include:

- consistency - AI suggestions align with government standards (GDS Service Manual, Digital Service Standard, Web Content Accessibility Guidelines (WCAG))
- efficiency - reduce time spent explaining context in each prompt
- compliance - embed regulatory requirements directly into AI workflows
- quality - maintain code quality and architectural patterns across teams

This playbook covers:

- three levels of instructions (personal, repository, organisation)
- what to include for government projects
- integration with GDS Service Manual and Digital Service Standard
- security and compliance considerations
- practical templates and implementation guidance

## Scope and audience

### Who should use this playbook

Primary audience includes:

- software engineers using AI code assistants on government projects
- technical leads establishing coding standards
- DevOps engineers setting up repositories

Secondary audience includes:

- service owners ensuring compliance requirements are met
- security teams reviewing AI tool usage
- senior engineers onboarding new team members

### What this playbook covers

This playbook covers:

- creating instruction files for AI code assistants (GitHub Copilot, Claude Code, Amazon Q, Gemini)
- structuring instructions at personal, repository and organisation levels
- integrating government standards and compliance requirements
- templates and examples for common scenarios

### Related documentation

Related documentation includes:

- 'GDS Service Manual' at https://www.gov.uk/service-manual
- 'Government Digital Service Standard' at https://www.gov.uk/service-manual/service-standard
- 'GOV.UK Design System' at https://design-system.service.gov.uk/
- 'WCAG 2.1 Guidelines' at https://www.w3.org/WAI/WCAG21/quickref/
- 'NCSC Cloud Security Guidance' at https://www.ncsc.gov.uk/collection/cloud-security

## Safety and handling

Instruction files are part of your project documentation. Treat them as potentially shareable artefacts.

You must:

- never include credentials, secrets, API keys or production data
- keep content at the correct security classification for the repository
- review AI-generated changes as you would any other code (peer review, tests, threat modelling where appropriate)

You should:

- prefer linking to authoritative guidance rather than copying long policy text
- assign an owner and review cadence (for example, quarterly or when standards change)

For fuller guidance on risks and mitigations, link to your governance and security material (for example, 'governance/guardrails-base.md' and 'mcp-servers/mcp-security-risks-and-mitigations.md').

## Introduction

The scenario: you want AI assistants to automatically follow your project's standards every time, without having to repeat context in every prompt.

Instruction files are configuration files that tell AI assistants about your coding standards, patterns and requirements. They ensure consistency across your team and reduce the need to provide the same context repeatedly.

For government projects, instruction files are particularly valuable for:

- embedding compliance requirements (WCAG, General Data Protection Regulation (GDPR), security classifications)
- maintaining consistency with GDS patterns and standards
- ensuring accessibility is considered from the start
- applying security policies automatically

## Government standards integration

This playbook is about how to use instruction files, so keep standards content short and reference the authoritative source.

In practice, your repository instructions should:

- link to the Digital Service Standard and GDS Service Manual
- state the accessibility requirement (WCAG 2.1 AA) and any tooling expectations
- state the security classification and the most important handling rules
- summarise GDPR and data protection expectations relevant to code (for example, 'no Personally Identifiable Information (PII) in logs')

Example snippet (copy and paste into a repo instruction file):

```markdown
## Government requirements
- Digital Service Standard: https://www.gov.uk/service-manual/service-standard
- Service Manual: https://www.gov.uk/service-manual
- Accessibility: WCAG 2.1 AA (reference: https://www.w3.org/WAI/WCAG21/quickref/)
- Security classification: OFFICIAL (do not include secrets or production data in prompts)
- Data protection: no PII in application logs and minimise collected data
```

If you need detailed organisational policy text, keep it in governance documents and link to it from the instruction file.

## Levels of custom instructions

Custom instructions can be set at three different levels, each serving a different purpose.

### Personal custom instructions

Personal instructions apply to all your interactions with the AI assistant, across all repositories and organisations. These are ideal for your individual preferences and working style.

Use personal instructions for:

- your preferred coding style and conventions
- language preferences (British and American English)
- communication preferences (verbosity, tone)
- accessibility requirements specific to you
- your areas of expertise or learning

Example content includes:

- 'Use British English spelling'
- 'Prefer functional programming patterns'
- 'Always include JSDoc comments for public APIs'
- 'I am experienced with Python but new to TypeScript'

### Repository custom instructions

Repository instructions apply to everyone working on a specific repository. These ensure consistency across the team for that project.

Use repository instructions for:

- tech stack and versions
- project-specific patterns and architecture
- build, test and deployment processes
- code quality standards for this project
- integration points and APIs
- project-specific compliance requirements

Example content includes:

- 'This project uses FastAPI 0.104 with async and await patterns'
- 'Always run `npm run lint` before committing'
- 'Use the repository pattern for database access'
- 'API responses must be under 200ms'
- 'Security classification: OFFICIAL'

### Organisation custom instructions

Organisation instructions apply to all repositories within your organisation. These maintain consistency across all your organisation's projects.

Use organisation instructions for:

- organisation-wide coding standards
- compliance and regulatory requirements
- security policies that apply to all projects
- branding and documentation guidelines
- common tools and frameworks
- cross-cutting government standards

Example content includes:

- 'All projects must meet WCAG 2.1 AA standards'
- 'Use GOV.UK Design System for public-facing services'
- 'Follow GDS Service Manual guidance'
- 'All user actions must be audit logged'

## Tool support and file locations

Different AI code assistants look for different repository instruction files. To avoid repetition, keep one canonical set of repository instructions and (if needed) mirror it into the tool-specific filename(s).

| Tool | Repository instruction file | Notes |
| --- | --- | --- |
| GitHub Copilot | `.github/copilot-instructions.md` | Supports personal and organisation instructions in settings - Combines instructions with priority Personal then Repository then Organisation |
| Claude Code (Cline) | `.clinerules` (and optionally `.clineignore`) | Reads automatically on each interaction - Good for detailed engineering and architecture rules |
| Amazon Q | `.amazonq/instructions.md` | Useful for AWS patterns (IAM, CDK and CloudFormation, Well-Architected) |
| Gemini (IDEs) | `.gemini-instructions.md` | Good for structured context - Keep it short and specific |
| Web chat tools (no repo awareness) | `AI_INSTRUCTIONS.md` | These tools do not automatically read your repo - Paste the relevant sections at the start of a session |

### Quick setup (repository-level)

1. Create the relevant file for your tool (see table).
2. Add tech stack, most important patterns, links to standards and handling rules (no secrets, no production data).
3. Commit the file so it applies consistently for the team.
4. Review periodically (owner and cadence).

## What to include in instruction files

### Technical standards

Technical standards include:

- tech stack and versions
- code style guidelines
- formatting rules
- architectural patterns
- dependencies and package management

### Frontend-specific instructions

Frontend-specific instructions include:

- framework and version (React, Vue, Angular and similar)
- component patterns and structure
- state management approach
- styling methodology (CSS Modules, Tailwind and similar)
- GOV.UK frontend integration
- accessibility requirements (WCAG 2.1 AA)
- browser support requirements
- performance budgets

### Backend-specific instructions

Backend-specific instructions include:

- framework and language version
- API design patterns (REST, GraphQL and similar)
- database patterns and ORM usage
- authentication and authorisation approach
- error handling patterns
- logging and monitoring requirements (with GDPR compliance)
- rate limiting and throttling rules
- security headers and CORS policies

### Security requirements

Security requirements include:

- security classification (OFFICIAL, SECRET and similar)
- authentication mechanisms
- authorisation patterns
- input validation rules
- data encryption requirements
- secret management
- vulnerability scanning requirements
- NCSC guidance compliance

### Government and enterprise requirements

Government and enterprise requirements include:

- compliance standards (WCAG 2.1 AA, GDS, GDPR and similar)
- Digital Service Standard requirements
- GDS Service Manual alignment
- audit and logging requirements
- data protection rules
- branding guidelines (GOV.UK Design System)

### Testing standards

Testing standards include:

- testing frameworks and tools
- coverage requirements (minimum percentages)
- test naming conventions
- what needs testing (unit, integration, E2E, security, accessibility)
- mock and fixture patterns
- accessibility testing tools (axe, WAVE, Pa11y)

### Documentation and communication

Documentation and communication includes:

- comment style and when to comment
- documentation tone and format
- error message guidelines (plain language, actionable)
- language preferences (British English for government)
- README and changelog requirements
- API documentation standards

### Performance and quality

Performance and quality includes:

- response time requirements
- optimisation rules
- code complexity limits
- linting and analysis tools
- code review requirements
- monitoring and observability

## Template structures

### Personal instructions template

```markdown
# My personal AI assistant instructions

## Language and style
- use British English spelling
- prefer concise responses with examples
- [Your communication preferences]

## Coding preferences
- [Your preferred languages and frameworks]
- [Code style preferences]
- [Documentation preferences]

## My experience level
- experienced with: [languages and tools you know well]
- learning: [areas you're developing]

## Accessibility
- [Any specific accessibility needs for how AI communicates with you]
```

### Repository instructions template

```markdown
# AI assistant instructions - [Project Name]

## Project context
[Brief description of what this project does and who uses it]

## Government standards compliance
- digital service standard: [which points apply - reference https://www.gov.uk/service-manual/service-standard]
- GDS service manual: [relevant sections - reference https://www.gov.uk/service-manual]
- WCAG 2.1 AA compliance required
- Security classification: [OFFICIAL, SECRET and similar]
- GDPR compliance required

## Tech stack
- [Language and version]
- [Framework and version]
- [Database]
- [Key dependencies]

## Critical requirements

All code must meet these requirements:

- all code must meet WCAG 2.1 AA standards
- follow GOV.UK Design System patterns for UI
- security classification: [classification] - handle accordingly
- all user actions must be audit logged
- no PII in application logs

## Code style
- [Style guide to follow - for example, PEP 8, Airbnb JavaScript]
- British English in all code comments and documentation
- [Documentation requirements]
- [Naming conventions]
- [File organisation]

## Architecture and patterns
[Description of important patterns - repositories, services and similar]

## Frontend guidelines
- use GOV.UK frontend components (version X.X)
- component structure: [your pattern]
- state management: [approach]
- styling: [methodology]
- browser support: [requirements]
- accessibility testing: axe DevTools on all components

## Backend guidelines
- API patterns: [REST, GraphQL and similar]
- database access: [patterns]
- authentication: [approach]
- authorisation: [approach]
- error handling: [patterns]
- logging: actions and outcomes only, no PII

## Testing standards
- testing framework: [tool]
- minimum coverage: [percentage]
- required tests:
  - unit tests for all business logic
  - integration tests for API endpoints
  - accessibility tests for all UI components
  - security tests for authentication and authorisation

## Build and deployment
- build commands: [commands]
- environment setup: [steps]
- deployment process: [overview]

## Performance requirements
- page load: [target]
- API response: [target]
- time to interactive: [target]

## Security guidelines
- input validation: all user input must be validated
- SQL injection prevention: use parameterised queries only
- XSS prevention: escape all user-generated content
- CSRF protection: required on all state-changing operations
- rate limiting: [rules]

## Data protection
- collect minimal data only
- no PII in logs
- data retention: [period]
- encryption: at rest and in transit

## When you're not sure

1. Check existing code in [directory or file].
2. Refer to [team wiki or documentation].
3. Ask [team lead or channel].
4. Prioritise: security then accessibility then performance then speed of delivery.
5. When in doubt, follow GDS patterns.
```

### Organisation instructions template

```markdown
# [Organisation Name] AI assistant instructions

## Organisation standards
All projects within [Organisation] must follow these standards.

### Government compliance
- all services must meet the digital service standard: https://www.gov.uk/service-manual/service-standard
- follow the GDS Service Manual: https://www.gov.uk/service-manual
- WCAG 2.1 AA compliance mandatory
- technology choices must align with service manual recommendations

### Language and tone
- British English spelling in all code and documentation
- plain language for user-facing content (reading age 9 to 12)
- no jargon in citizen-facing interfaces
- error messages must be actionable and clear

### Coding standards
- [Style guides that apply to all projects]
- [Documentation requirements]
- [Code review process]
- all code must be peer reviewed before merging

### Security policy
- security classifications must be clearly marked
- no credentials or secrets in code repositories
- all secrets stored in approved secret management tools
- follow NCSC Cloud Security Principles: https://www.ncsc.gov.uk/collection/cloud-security
- multi-factor authentication required for all access

### Data protection (GDPR)
- data minimisation: collect only what's needed
- purpose limitation: use data only for stated purpose
- no PII in application logs or error messages
- right to erasure: implement soft delete with anonymisation
- data retention policies must be documented and enforced

### Accessibility (WCAG 2.1 AA)
- all services must be accessible to users with disabilities
- test with assistive technologies (JAWS, NVDA, VoiceOver)
- keyboard navigation must work for all interactions
- colour contrast must meet WCAG requirements (4.5 to 1 for normal text, 3 to 1 for large text)
- automated testing with axe or Pa11y in CI pipeline
- reference: https://www.w3.org/WAI/WCAG21/quickref/

### Design and branding
- use GOV.UK design system for citizen-facing services: https://design-system.service.gov.uk/
- use GOV.UK frontend toolkit
- internal services should follow [internal design system]
- crown copyright notice on all appropriate content

### Tools and frameworks
- approved languages: [list]
- approved frameworks: [list]
- deprecated technologies to avoid: [list]
- cloud platforms: [approved platforms]

### Testing requirements
- minimum 80% code coverage for all projects
- unit, integration and E2E tests required
- accessibility tests required for all UI
- security tests for authentication and authorisation
- performance tests for critical user journeys

### Quality standards
- all code must pass linting
- no critical security vulnerabilities in dependencies
- code complexity limits: [specify]
- documentation required for all public APIs

### Deployment and operations
- all changes via pull request with peer review
- CI/CD pipeline must include: lint, test, security scan
- deployment must be approved by [role]
- monitoring and alerting required for all production services
```

## Maintaining instruction files

As your project evolves, keep the instructions current.

### Regular review

Review activities include:

- review instruction files quarterly or when standards change
- check instructions against current codebase
- update for new patterns that have emerged
- remove outdated information
- verify links to external documentation still work

### Triggers for updates

Update instruction files when:

- tech stack changes (new framework version, new dependencies)
- compliance requirements change (new WCAG version, new GDS guidance)
- security classifications change
- new patterns emerge in the codebase
- team feedback identifies issues with AI suggestions
- major architectural changes occur

### Ownership and responsibility

Ownership and responsibility includes:

- assign a maintainer for each instruction file
- repository instructions: technical lead for that project
- organisation instructions: senior technical leadership
- include ownership information in the instruction file itself

## Getting started

1. Create the right file for your tool (for example, `.github/copilot-instructions.md`).
2. Add only the essentials: tech stack, most important patterns and links to standards.
3. Add handling rules: classification, 'no secrets' and 'no production data'.
4. Review regularly: set an owner and a review date.

## Useful links and resources

### Official documentation

Official documentation includes:

- 'Configure Custom Instructions for GitHub Copilot' at https://docs.github.com/en/copilot/customizing-copilot/configure-custom-instructions-for-github-copilot - overview of custom instructions at all levels
- 'Adding Personal Custom Instructions' at https://docs.github.com/en/copilot/customizing-copilot/adding-personal-custom-instructions-for-github-copilot - set up your personal preferences
- 'Adding Repository Custom Instructions' at https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot - detailed guide to repository-level instructions
- 'Adding Organisation Custom Instructions' at https://docs.github.com/en/copilot/customizing-copilot/adding-organization-custom-instructions-for-github-copilot - organisation-wide standards

### Government standards

Government standards include:

- 'GDS Service Manual' at https://www.gov.uk/service-manual - guidance for building government services
- 'Government Digital Service Standard' at https://www.gov.uk/service-manual/service-standard - the 14-point standard
- 'GOV.UK Design System' at https://design-system.service.gov.uk/ - design patterns and components
- 'WCAG 2.1 Quick Reference' at https://www.w3.org/WAI/WCAG21/quickref/ - accessibility guidelines
- 'NCSC Cloud Security Guidance' at https://www.ncsc.gov.uk/collection/cloud-security - security principles for cloud

### Example instruction files

- 'GitHub Awesome Copilot - Instructions Examples' at https://github.com/github/awesome-copilot/tree/main/instructions - collection of real-world copilot-instructions.md examples from various projects