> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI-assisted software development lifecycle

This playbook provides guidance on integrating AI Coding Assistants (AICAs) across all phases of the software development lifecycle. It is designed for UK government teams delivering digital services and complements the [Government Service Manual](https://www.gov.uk/service-manual) and [AI Playbook for the UK Government](https://www.gov.uk/government/publications/ai-playbook-for-the-uk-government).

## Who this is for

This guidance is for anyone involved in delivering software in government, including engineers, technical architects, delivery managers, product managers, QA engineers and technical leads. It assumes basic familiarity with AICA tools but accommodates teams at all maturity levels.

## Before you start

Before integrating AICAs into your workflow, ensure you have:

- Completed your department's AI Engineering Lab onboarding and received tool access
- Reviewed the [guardrails-base.md](../governance/guardrails-base.md) for your organisation
- Understood your team's data classification and what can be shared with AI tools
- Familiarised yourself with the [context-engineering.md](context-engineering.md) approach

## Core principles

When using AICAs throughout the SDLC, apply these principles consistently:

**Human oversight remains essential.** AICAs accelerate work but do not replace professional judgement. All AI-generated outputs require human review, particularly for security-sensitive code, architectural decisions and user-facing content.

**Context drives quality.** The effectiveness of AICA outputs depends directly on the context you provide. Invest time in context engineering to achieve better results.

**Verify before committing.** Never commit AI-generated code without understanding what it does. Run tests, review logic and validate against requirements.

**Continuous compliance.** Use MCP servers and guardrails to embed government standards (TCoP, WCAG, NCSC, Service Standard) into your workflow from the start, not as an afterthought.

---

## SDLC phases

The following sections describe how to use AICAs effectively at each phase of the software development lifecycle. Each phase includes practical guidance, example prompts and anti-patterns to avoid.

---

## Plan

**Purpose:** Decide what to build next and break work into deliverable units.

### How AICAs help

AICAs can accelerate planning activities by helping teams analyse requirements, identify technical considerations and structure work effectively. They work best when given clear context about your service, users and constraints.

### Recommended activities

**Analyse user stories and acceptance criteria.** Share user stories with your AICA to identify ambiguities, missing edge cases or technical implications. This surfaces questions early rather than during development.

```
Example prompt:
"Review this user story and acceptance criteria. Identify any ambiguities, 
missing edge cases, or technical considerations we should clarify before 
development begins.

User story: [paste story]
Acceptance criteria: [paste criteria]
Our tech stack: [brief description]"
```

**Generate technical approach options.** When facing implementation decisions, ask your AICA to outline alternative approaches with trade-offs. Use this as input to team discussions, not as the final decision.

**Estimate complexity.** AICAs can help identify technical complexity factors in stories, though human judgement remains essential for accurate estimation.

**Create spike documentation.** When investigating unknowns, use AICAs to structure your spike, identify questions to answer and document findings.

### Anti-patterns to avoid

- Accepting AI-generated estimates without team validation
- Using AICAs to write user stories without user research input
- Skipping human review of technical approach recommendations

### Quality indicators

- Stories have clear acceptance criteria before development starts
- Technical approach is understood and agreed by the team
- Dependencies and risks are identified early

---

## Code

**Purpose:** Write software that solves user problems while meeting government standards.

### How AICAs help

AICAs provide the most significant productivity gains during coding, offering real-time suggestions, generating boilerplate, explaining unfamiliar code and helping implement patterns correctly.

### Recommended activities

**Use inline completion thoughtfully.** AICA suggestions work best when you have clear intent. Write meaningful function names and comments first, then let the tool suggest implementations.

**Generate boilerplate with context.** When creating new components, provide your coding standards and architectural patterns as context. This produces more consistent, compliant code.

```
Example prompt:
"Create a Spring Boot REST controller for managing [resource]. 
Follow these patterns:
- Use constructor injection
- Apply our standard error handling approach
- Include OpenAPI annotations
- Follow NCSC secure coding guidelines

Existing controller for reference: [paste example]"
```

**Explain and document existing code.** When working with legacy or unfamiliar code, use AICAs to generate explanations and documentation. Always verify accuracy against the actual behaviour.

**Refactor with guardrails.** When refactoring, provide your coding standards and ask AICAs to suggest improvements. Review suggestions against your team's patterns.

**Generate unit tests alongside code.** Write tests as you develop, using AICAs to generate test cases from your implementation. Ensure tests are meaningful, not just coverage padding.

### Context engineering for better code

The quality of AICA code suggestions depends heavily on context. Provide:

- **Project context:** Architecture decisions, coding standards, technology choices
- **Local context:** Related files, interfaces, data models
- **Intent context:** What you are trying to achieve and why
- **Constraint context:** Security requirements, performance needs, accessibility standards

See [context-engineering.md](context-engineering.md) for detailed guidance.

### Security considerations

- Never paste secrets, credentials or API keys into AICA prompts
- Review generated code for security vulnerabilities before committing
- Use SAST tools to validate AI-generated code
- Be cautious with AI-generated SQL, authentication and authorisation code
- Validate input handling and output encoding in generated code
- Configure coding agents to exclude sensitive files. Agentic coding tools should be configured to avoid reading .env files, .env.local, credential files, or any other files containing environment variables or secrets. Add these patterns to your agent's ignore configuration to prevent accidental exposure of sensitive data.

### Anti-patterns to avoid

- Accepting suggestions without understanding the code
- Ignoring security implications of generated code
- Using AICAs as a substitute for understanding your codebase
- Generating large amounts of code without incremental testing
- Copying AI suggestions that violate your coding standards

### Quality indicators

- Code follows team conventions and passes linting
- Generated code has appropriate test coverage
- Security-sensitive code receives additional review
- Engineers can explain what their code does

---

## Build

**Purpose:** Prepare code changes for testing by compiling, packaging and validating.

### How AICAs help

AICAs assist with build configuration, dependency management and resolving build failures. They can explain error messages and suggest fixes, reducing time spent debugging build issues.

### Recommended activities

**Diagnose build failures.** Share build error logs with your AICA to get explanations and suggested fixes. Include relevant configuration files for context.

```
Example prompt:
"This Maven build is failing with the following error. Explain the cause 
and suggest how to fix it.

Error log: [paste log]
Relevant pom.xml section: [paste section]"
```

**Optimise build configuration.** AICAs can suggest improvements to build scripts, dependency management and CI pipeline configuration.

**Generate build documentation.** Create clear build instructions for your repository, ensuring new team members can get started quickly.

**Resolve dependency conflicts.** When facing dependency issues, AICAs can help analyse conflicts and suggest resolution strategies.

### Anti-patterns to avoid

- Applying suggested fixes without understanding the root cause
- Ignoring security warnings in dependency suggestions
- Making build configuration changes without testing

### Quality indicators

- Builds complete successfully and consistently
- Build times are reasonable and optimised
- Dependencies are up to date and secure
- Build process is documented and reproducible

---

## Test

**Purpose:** Ensure everything works properly and meets quality standards.

### How AICAs help

AICAs significantly accelerate test creation, helping generate unit tests, integration tests and test data. They can identify edge cases and suggest test scenarios humans might miss.

### Recommended activities

**Generate unit tests from implementation.** After writing code, use AICAs to generate comprehensive unit tests. Specify your testing framework and conventions.

```
Example prompt:
"Generate JUnit 5 tests for this service class. Include:
- Happy path scenarios
- Edge cases and boundary conditions
- Error handling paths
- Use Mockito for dependencies
- Follow AAA (Arrange-Act-Assert) pattern

Class to test: [paste class]
Dependencies to mock: [list]"
```

**Identify missing test scenarios.** Share your code and existing tests, asking the AICA to identify gaps in coverage.

**Generate test data.** Create realistic test data sets that cover various scenarios, including edge cases and invalid inputs.

**Write BDD scenarios.** Generate Gherkin scenarios from requirements, ensuring comprehensive coverage of user journeys.

**Create accessibility test cases.** Generate test cases that verify WCAG compliance for user-facing components.

### Test quality considerations

AI-generated tests require careful review. Check that tests:

- Actually verify meaningful behaviour, not just achieve coverage
- Use appropriate assertions (not just checking for no exceptions)
- Are maintainable and readable
- Do not duplicate existing tests
- Cover security-relevant scenarios

### Anti-patterns to avoid

- Generating tests purely to increase coverage metrics
- Accepting tests without verifying they test the right behaviour
- Using AI-generated test data that contains realistic personal data
- Skipping review of test assertions

### Quality indicators

- Tests verify actual requirements, not just implementation
- Coverage is meaningful, not just numerical
- Tests run reliably without flakiness
- Edge cases and error paths are covered

---

## Release

**Purpose:** Coordinate launching new features safely.

### How AICAs help

AICAs assist with release preparation, including generating release notes, creating deployment checklists and documenting changes.

### Recommended activities

**Generate release notes.** Summarise changes from commit history or ticket descriptions into user-friendly release notes.

```
Example prompt:
"Generate release notes for version [X.Y.Z] based on these changes. 
Write for a technical audience but keep it clear and scannable.

Changes:
[paste commit messages or ticket summaries]

Previous version notes for style reference:
[paste previous notes]"
```

**Create deployment checklists.** Generate environment-specific checklists to ensure consistent, safe deployments.

**Document breaking changes.** Identify and clearly document any breaking changes, including migration steps for consumers.

**Prepare rollback procedures.** Document rollback steps for each significant change in the release.

### Anti-patterns to avoid

- Publishing AI-generated release notes without review
- Automating release decisions without human approval
- Skipping rollback planning for complex changes

### Quality indicators

- Release notes are accurate and complete
- Deployment checklists are followed consistently
- Breaking changes are communicated in advance
- Rollback procedures are tested and documented

---

## Deploy

**Purpose:** Put your service live for users safely and reliably.

### How AICAs help

AICAs assist with infrastructure configuration, deployment scripts and troubleshooting deployment issues. They can generate and review infrastructure-as-code.

### Recommended activities

**Generate infrastructure configuration.** Create Terraform, CloudFormation or Kubernetes configurations with appropriate security settings.

```
Example prompt:
"Generate a Terraform configuration for an AWS ECS service with:
- Application load balancer
- Auto-scaling based on CPU utilisation
- CloudWatch logging
- Security groups following least-privilege principles
- Tags for cost allocation

Follow NCSC cloud security principles."
```

**Review infrastructure changes.** Before applying infrastructure changes, use AICAs to review configurations for security issues and best practices.

**Troubleshoot deployment failures.** Share deployment logs and configuration to diagnose issues quickly.

**Generate deployment runbooks.** Create step-by-step deployment guides for operations teams.

### Security considerations

- Review all generated infrastructure code for security misconfigurations
- Never include credentials in infrastructure-as-code
- Validate network configurations and access controls
- Ensure logging and monitoring are properly configured

### Anti-patterns to avoid

- Deploying AI-generated infrastructure without security review
- Using overly permissive security configurations from suggestions
- Skipping testing of deployment scripts

### Quality indicators

- Deployments are automated and repeatable
- Infrastructure follows security best practices
- Rollback procedures work reliably
- Deployment time is minimised

---

## Operate

**Purpose:** Keep your service running smoothly for users.

### How AICAs help

AICAs assist with incident response, operational documentation and analysing system behaviour. They can help interpret logs, suggest remediation steps and document incidents.

### Recommended activities

**Analyse incidents.** During incidents, use AICAs to quickly interpret error logs and suggest investigation paths.

```
Example prompt:
"We're experiencing increased latency on our API. Analyse these logs 
and metrics to suggest likely causes and investigation steps.

Error logs: [paste relevant logs]
Metrics: [describe current vs normal values]
Recent changes: [list recent deployments]"
```

**Generate runbooks.** Create operational runbooks for common scenarios, including monitoring alerts and their remediation steps.

**Document incidents.** After resolution, generate incident reports that capture timeline, root cause and preventive actions.

**Optimise performance.** Analyse performance data and suggest optimisation opportunities.

### Anti-patterns to avoid

- Relying solely on AI suggestions during critical incidents
- Implementing suggested fixes without understanding the problem
- Generating runbooks without validation by operations teams

### Quality indicators

- Incidents are resolved quickly with clear documentation
- Runbooks are accurate and up to date
- Service meets availability and performance targets
- On-call burden is manageable

---

## Monitor

**Purpose:** Learn from real usage to improve the service.

### How AICAs help

AICAs assist with interpreting monitoring data, identifying patterns and suggesting improvements based on observed behaviour.

### Recommended activities

**Analyse usage patterns.** Use AICAs to identify trends, anomalies and opportunities in service metrics.

```
Example prompt:
"Analyse these service metrics from the past month. Identify:
- Unusual patterns or anomalies
- Performance degradation trends
- Opportunities for optimisation
- Potential capacity concerns

Metrics data: [paste or describe data]"
```

**Generate dashboards.** Create monitoring dashboard configurations that surface the most important metrics.

**Define alerts.** Develop alerting rules that catch real problems without causing alert fatigue.

**Summarise user feedback.** Analyse support tickets, feedback and error reports to identify improvement priorities.

### Anti-patterns to avoid

- Acting on AI-identified patterns without validation
- Creating excessive alerts based on suggestions
- Ignoring context that the AI cannot see

### Quality indicators

- Dashboards show actionable information
- Alerts indicate real problems requiring attention
- Service improvements are driven by data
- User satisfaction is measured and improving

---

## Continuous compliance

Throughout all SDLC phases, use MCP servers to maintain continuous compliance with government standards. This includes:

- **Technology Code of Practice (TCoP):** Architecture and technology choices
- **WCAG 2.2 AA:** Accessibility requirements
- **NCSC guidelines:** Security practices
- **Government Service Standard:** Service design and delivery

Configure your AI Engineering Lab tools to reference these standards automatically, catching compliance issues during development rather than at assessment.

---

## Getting help

If you encounter challenges using AI coding assistants effectively:

1. Check the [prompt-library](../prompt-library/) for tested prompts for common scenarios
2. Consult your team's AI Engineering Lab champion for guidance
3. Raise questions in the cross-government AI Engineering Lab community channels
4. Request support from the Forward Deployed Engineering team for complex adoption challenges

---

## Related resources

- [Context engineering playbook](context-engineering.md)
- [Model selection guidance](model-selection.md)
- [Guardrails base configuration](../governance/guardrails-base.md)
- [Government AI Playbook](https://www.gov.uk/government/publications/ai-playbook-for-the-uk-government)
- [Service Manual](https://www.gov.uk/service-manual)
- [Version1 UK Gov Example AI SDLC](https://github.com/Version1/uk-gov-example-ai-sdlc)

---

## Contributing

To suggest improvements or report issues, see [CONTRIBUTING.md](../CONTRIBUTING.md).