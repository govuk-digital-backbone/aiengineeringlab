# Using Instruction Files for AI Code Assistants

## Executive Summary

This playbook provides practical guidance on creating and managing instruction files for AI code assistants across government projects. Instruction files ensure AI tools understand your project's standards, compliance requirements, and coding patterns, reducing the need to repeat context in every interaction.

**Key benefits:**
- **Consistency:** AI suggestions align with government standards (GDS Service Manual, Digital Service Standard, WCAG)
- **Efficiency:** Reduce time spent explaining context in each prompt
- **Compliance:** Embed regulatory requirements directly into AI workflows
- **Quality:** Maintain code quality and architectural patterns across teams

**This playbook covers:**
- Three levels of instructions (personal, repository, organisation)
- What to include for government projects
- Integration with GDS Service Manual and Digital Service Standard
- Security and compliance considerations
- Practical templates and implementation guidance

## Scope and Audience

### Who Should Use This Playbook

**Primary audience:**
- Software engineers using AI code assistants on government projects
- Technical leads establishing coding standards
- DevOps engineers setting up repositories

**Secondary audience:**
- Service owners ensuring compliance requirements are met
- Security teams reviewing AI tool usage
- Senior engineers onboarding new team members

### What This Playbook Covers

- Creating instruction files for AI code assistants (GitHub Copilot, Claude Code, Amazon Q, Gemini)
- Structuring instructions at personal, repository, and organisation levels
- Integrating government standards and compliance requirements
- Templates and examples for common scenarios

### Related Documentation

- [GDS Service Manual](https://www.gov.uk/service-manual)
- [Government Digital Service Standard](https://www.gov.uk/service-manual/service-standard)
- [GOV.UK Design System](https://design-system.service.gov.uk/)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [NCSC Cloud Security Guidance](https://www.ncsc.gov.uk/collection/cloud-security)

## Safety and Handling

Instruction files are part of your project documentation. Treat them as potentially shareable artefacts.

**Must:**
- Never include credentials, secrets, API keys, or production data.
- Keep content at the correct security classification for the repository.
- Review AI-generated changes as you would any other code (peer review, tests, threat modelling where appropriate).

**Should:**
- Prefer linking to authoritative guidance rather than copying long policy text.
- Assign an owner and review cadence (for example, quarterly or when standards change).

For fuller guidance on risks and mitigations, link to your governance/security material (for example, [governance/guardrails-base.md](../governance/guardrails-base.md) and [mcp-servers/mcp-security-risks-and-mitigations.md](../mcp-servers/mcp-security-risks-and-mitigations.md)).

## Introduction

**The scenario:** You want AI assistants to automatically follow your project's standards every time, without having to repeat context in every prompt.

Instruction files are configuration files that tell AI assistants about your coding standards, patterns, and requirements. They ensure consistency across your team and reduce the need to provide the same context repeatedly.

For government projects, instruction files are particularly valuable for:
- Embedding compliance requirements (WCAG, GDPR, security classifications)
- Maintaining consistency with GDS patterns and standards
- Ensuring accessibility is considered from the start
- Applying security policies automatically

## Government Standards Integration

This playbook is about *how to use* instruction files, so keep standards content short and reference the authoritative source.

**In practice, your repository instructions should:**
- Link to the Digital Service Standard and GDS Service Manual.
- State the accessibility requirement (WCAG 2.1 AA) and any tooling expectations.
- State the security classification and the key “must not” handling rules.
- Summarise GDPR/data protection expectations relevant to code (for example, “no PII in logs”).

**Example snippet (copy-paste into a repo instruction file):**
```markdown
## Government requirements
- Digital Service Standard: https://www.gov.uk/service-manual/service-standard
- Service Manual: https://www.gov.uk/service-manual
- Accessibility: WCAG 2.1 AA (reference: https://www.w3.org/WAI/WCAG21/quickref/)
- Security classification: OFFICIAL (do not include secrets; no production data in prompts)
- Data protection: no PII in application logs; minimise collected data
```

If you need detailed organisational policy text, keep it in governance documents and link to it from the instruction file.

## Levels of Custom Instructions

Custom instructions can be set at three different levels, each serving a different purpose:

### Personal Custom Instructions

Personal instructions apply to all your interactions with the AI assistant, across all repositories and organisations. These are ideal for your individual preferences and working style.

**Use personal instructions for:**
- Your preferred coding style and conventions
- Language preferences (British/American English)
- Communication preferences (verbosity, tone)
- Accessibility requirements specific to you
- Your areas of expertise or learning

**Example content:**
- "Use British English spelling"
- "Prefer functional programming patterns"
- "Always include JSDoc comments for public APIs"
- "I'm experienced with Python but new to TypeScript"

### Repository Custom Instructions

Repository instructions apply to everyone working on a specific repository. These ensure consistency across the team for that project.

**Use repository instructions for:**
- Tech stack and versions
- Project-specific patterns and architecture
- Build, test, and deployment processes
- Code quality standards for this project
- Integration points and APIs
- Project-specific compliance requirements

**Example content:**
- "This project uses FastAPI 0.104 with async/await patterns"
- "Always run `npm run lint` before committing"
- "Use the repository pattern for database access"
- "API responses must be under 200ms"
- "Security classification: OFFICIAL"

### Organisation Custom Instructions

Organisation instructions apply to all repositories within your organisation. These maintain consistency across all your organisation's projects.

**Use organisation instructions for:**
- Organisation-wide coding standards
- Compliance and regulatory requirements
- Security policies that apply to all projects
- Branding and documentation guidelines
- Common tools and frameworks
- Cross-cutting government standards

**Example content:**
- "All projects must meet WCAG 2.1 AA standards"
- "Use GOV.UK Design System for public-facing services"
- "Follow GDS Service Manual guidance"
- "All user actions must be audit logged"

## Tool Support and File Locations

Different AI code assistants look for different repository instruction files. To avoid repetition, keep one canonical set of repository instructions and (if needed) mirror it into the tool-specific filename(s).

| Tool | Repository instruction file | Notes |
| --- | --- | --- |
| GitHub Copilot | `.github/copilot-instructions.md` | Supports personal + organisation instructions in settings; combines instructions with priority Personal > Repository > Organisation. |
| Claude Code (Cline) | `.clinerules` (and optionally `.clineignore`) | Reads automatically on each interaction. Good for detailed engineering and architecture rules. |
| Amazon Q | `.amazonq/instructions.md` | Useful for AWS patterns (IAM, CDK/CloudFormation, Well-Architected). |
| Gemini (IDEs) | `.gemini-instructions.md` | Good for structured context; keep it short and specific. |
| Web chat tools (no repo awareness) | `AI_INSTRUCTIONS.md` | These tools do not automatically read your repo. Paste the relevant sections at the start of a session. |

### Quick setup (repository-level)
1. Create the relevant file for your tool (see table).
2. Add: tech stack, key patterns, links to standards, and handling rules (no secrets, no production data).
3. Commit the file so it applies consistently for the team.
4. Review periodically (owner + cadence).

## What to Include in Instruction Files

### Technical Standards
- Tech stack and versions
- Code style guidelines
- Formatting rules
- Architectural patterns
- Dependencies and package management

### Frontend-Specific Instructions
- Framework and version (React, Vue, Angular, etc.)
- Component patterns and structure
- State management approach
- Styling methodology (CSS Modules, Tailwind, etc.)
- GOV.UK Frontend integration
- Accessibility requirements (WCAG 2.1 AA)
- Browser support requirements
- Performance budgets

### Backend-Specific Instructions
- Framework and language version
- API design patterns (REST, GraphQL, etc.)
- Database patterns and ORM usage
- Authentication and authorisation approach
- Error handling patterns
- Logging and monitoring requirements (with GDPR compliance)
- Rate limiting and throttling rules
- Security headers and CORS policies

### Security Requirements
- Security classification (OFFICIAL, SECRET, etc.)
- Authentication mechanisms
- Authorisation patterns
- Input validation rules
- Data encryption requirements
- Secret management
- Vulnerability scanning requirements
- NCSC guidance compliance

### Government/Enterprise Requirements
- Compliance standards (WCAG 2.1 AA, GDS, GDPR, etc.)
- Digital Service Standard requirements
- GDS Service Manual alignment
- Audit and logging requirements
- Data protection rules
- Branding guidelines (GOV.UK Design System)

### Testing Standards
- Testing frameworks and tools
- Coverage requirements (minimum percentages)
- Test naming conventions
- What needs testing (unit, integration, E2E, security, accessibility)
- Mock and fixture patterns
- Accessibility testing tools (axe, WAVE, Pa11y)

### Documentation and Communication
- Comment style and when to comment
- Documentation tone and format
- Error message guidelines (plain language, actionable)
- Language preferences (British English for government)
- README and changelog requirements
- API documentation standards

### Performance and Quality
- Response time requirements
- Optimisation rules
- Code complexity limits
- Linting and analysis tools
- Code review requirements
- Monitoring and observability

## Template Structures

### Personal Instructions Template

```markdown
# My Personal AI Assistant Instructions

## Language and Style
- Use British English spelling
- Prefer concise responses with examples
- [Your communication preferences]

## Coding Preferences
- [Your preferred languages and frameworks]
- [Code style preferences]
- [Documentation preferences]

## My Experience Level
- Experienced with: [languages/tools you know well]
- Learning: [areas you're developing]

## Accessibility
- [Any specific accessibility needs for how AI communicates with you]
```

### Repository Instructions Template

```markdown
# AI Assistant Instructions - [Project Name]

## Project Context
[Brief description of what this project does and who uses it]

## Government Standards Compliance
- Digital Service Standard: [which points apply - reference https://www.gov.uk/service-manual/service-standard]
- GDS Service Manual: [relevant sections - reference https://www.gov.uk/service-manual]
- WCAG 2.1 AA compliance required
- Security classification: [OFFICIAL/SECRET/etc.]
- GDPR compliance required

## Tech Stack
- [Language and version]
- [Framework and version]
- [Database]
- [Key dependencies]

## Critical Requirements
1. All code must meet WCAG 2.1 AA standards
2. Follow GOV.UK Design System patterns for UI
3. Security classification: [classification] - handle accordingly
4. All user actions must be audit logged
5. No PII in application logs

## Code Style
- [Style guide to follow - e.g., PEP 8, Airbnb JavaScript]
- British English in all code comments and documentation
- [Documentation requirements]
- [Naming conventions]
- [File organisation]

## Architecture and Patterns
[Description of key patterns - repositories, services, etc.]

## Frontend Guidelines
- Use GOV.UK Frontend components (version X.X)
- Component structure: [your pattern]
- State management: [approach]
- Styling: [methodology]
- Browser support: [requirements]
- Accessibility testing: axe DevTools on all components

## Backend Guidelines
- API patterns: [REST/GraphQL/etc.]
- Database access: [patterns]
- Authentication: [approach]
- Authorisation: [approach]
- Error handling: [patterns]
- Logging: Actions and outcomes only, no PII

## Testing Standards
- Testing framework: [tool]
- Minimum coverage: [percentage]
- Required tests:
  - Unit tests for all business logic
  - Integration tests for API endpoints
  - Accessibility tests for all UI components
  - Security tests for authentication/authorisation

## Build and Deployment
- Build commands: [commands]
- Environment setup: [steps]
- Deployment process: [overview]

## Performance Requirements
- Page load: [target]
- API response: [target]
- Time to Interactive: [target]

## Security Guidelines
- Input validation: All user input must be validated
- SQL injection prevention: Use parameterised queries only
- XSS prevention: Escape all user-generated content
- CSRF protection: Required on all state-changing operations
- Rate limiting: [rules]

## Data Protection
- Collect minimal data only
- No PII in logs
- Data retention: [period]
- Encryption: At rest and in transit

## When You're Not Sure
1. Check existing code in [directory/file]
2. Refer to [team wiki/documentation]
3. Ask [team lead/channel]
4. Prioritise: Security > Accessibility > Performance > Speed of delivery
5. When in doubt, follow GDS patterns
```

### Organisation Instructions Template

```markdown
# [Organisation Name] AI Assistant Instructions

## Organisation Standards
All projects within [Organisation] must follow these standards.

### Government Compliance
- All services must meet the Digital Service Standard: https://www.gov.uk/service-manual/service-standard
- Follow the GDS Service Manual: https://www.gov.uk/service-manual
- WCAG 2.1 AA compliance mandatory
- Technology choices must align with Service Manual recommendations

### Language and Tone
- British English spelling in all code and documentation
- Plain language for user-facing content (reading age 9-12)
- No jargon in citizen-facing interfaces
- Error messages must be actionable and clear

### Coding Standards
- [Style guides that apply to all projects]
- [Documentation requirements]
- [Code review process]
- All code must be peer reviewed before merging

### Security Policy
- Security classifications must be clearly marked
- No credentials or secrets in code repositories
- All secrets stored in approved secret management tools
- Follow NCSC Cloud Security Principles: https://www.ncsc.gov.uk/collection/cloud-security
- Multi-factor authentication required for all access

### Data Protection (GDPR)
- Data minimisation: collect only what's needed
- Purpose limitation: use data only for stated purpose
- No PII in application logs or error messages
- Right to erasure: implement soft delete with anonymisation
- Data retention policies must be documented and enforced

### Accessibility (WCAG 2.1 AA)
- All services must be accessible to users with disabilities
- Test with assistive technologies (JAWS, NVDA, VoiceOver)
- Keyboard navigation must work for all interactions
- Colour contrast must meet WCAG requirements (4.5:1 for normal text, 3:1 for large text)
- Automated testing with axe or Pa11y in CI pipeline
- Reference: https://www.w3.org/WAI/WCAG21/quickref/

### Design and Branding
- Use GOV.UK Design System for citizen-facing services: https://design-system.service.gov.uk/
- Use GOV.UK Frontend toolkit
- Internal services should follow [internal design system]
- Crown copyright notice on all appropriate content

### Tools and Frameworks
- Approved languages: [list]
- Approved frameworks: [list]
- Deprecated technologies to avoid: [list]
- Cloud platforms: [approved platforms]

### Testing Requirements
- Minimum 80% code coverage for all projects
- Unit, integration, and E2E tests required
- Accessibility tests required for all UI
- Security tests for authentication/authorisation
- Performance tests for critical user journeys

### Quality Standards
- All code must pass linting
- No critical security vulnerabilities in dependencies
- Code complexity limits: [specify]
- Documentation required for all public APIs

### Deployment and Operations
- All changes via pull request with peer review
- CI/CD pipeline must include: lint, test, security scan
- Deployment must be approved by [role]
- Monitoring and alerting required for all production services
```



## Maintaining Instruction Files

As your project evolves, keep the instructions current:

### Regular Review
- Review instruction files quarterly or when standards change
- Check instructions against current codebase
- Update for new patterns that have emerged
- Remove outdated information
- Verify links to external documentation still work

### Triggers for Updates
Update instruction files when:
- Tech stack changes (new framework version, new dependencies)
- Compliance requirements change (new WCAG version, new GDS guidance)
- Security classifications change
- New patterns emerge in the codebase
- Team feedback identifies issues with AI suggestions
- Major architectural changes occur

### Ownership and Responsibility
- Assign a maintainer for each instruction file
- Repository instructions: Technical lead for that project
- Organisation instructions: Senior technical leadership
- Include ownership information in the instruction file itself

## Getting Started

1. **Create the right file for your tool** (for example, `.github/copilot-instructions.md`).
2. **Add only the essentials:** tech stack, key patterns, and links to standards.
3. **Add handling rules:** classification, “no secrets”, and “no production data”.
4. **Review regularly:** set an owner and a review date.

## Useful Links and Resources

### Official Documentation
- [Configure Custom Instructions for GitHub Copilot](https://docs.github.com/en/copilot/customizing-copilot/configure-custom-instructions-for-github-copilot) - Overview of custom instructions at all levels
- [Adding Personal Custom Instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-personal-custom-instructions-for-github-copilot) - Set up your personal preferences
- [Adding Repository Custom Instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot) - Detailed guide to repository-level instructions
- [Adding Organisation Custom Instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-organization-custom-instructions-for-github-copilot) - Organisation-wide standards

### Government Standards
- [GDS Service Manual](https://www.gov.uk/service-manual) - Guidance for building government services
- [Government Digital Service Standard](https://www.gov.uk/service-manual/service-standard) - The 14-point standard
- [GOV.UK Design System](https://design-system.service.gov.uk/) - Design patterns and components
- [WCAG 2.1 Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/) - Accessibility guidelines
- [NCSC Cloud Security Guidance](https://www.ncsc.gov.uk/collection/cloud-security) - Security principles for cloud

### Example Instruction Files
- [GitHub Awesome Copilot - Instructions Examples](https://github.com/github/awesome-copilot/tree/main/instructions) - Collection of real-world copilot-instructions.md examples from various projects

---
