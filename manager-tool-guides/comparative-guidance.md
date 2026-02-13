> ALPHA
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# AI Engineering Lab comparative guidance

> A tool-agnostic framework for evaluating, selecting, and managing AI Engineering Labs across government.

## Purpose

This guide helps technical leads, delivery managers, and senior decision-makers evaluate AI Engineering Labs for their teams and departments. It provides objective comparison criteria, questions to ask vendors, and guidance on matching tools to team contexts.

This guide does not recommend specific tools. Instead, it equips you to make informed decisions based on your team's needs, security requirements, and ways of working.

## Tools in scope

The DSIT AI Engineering Lab Programme Phase 1 includes licences for:

| Tool | Vendor | Primary interface |
|------|--------|-------------------|
| GitHub Copilot Enterprise | Microsoft/GitHub | IDE extension, chat, CLI |
| Claude Code | Anthropic | CLI, IDE extension, API |
| Amazon Kiro or Q Engineer | AWS | CLI, IDE extension, console |
| Gemini Code Assist | Google | IDE extension, cloud console |

For tool-specific implementation guidance, see:

- [GitHub Copilot guide](github-copilot/)
- [Amazon Q engineer guide](amazon-q/)

---

## Evaluation framework

### Category 1: security and compliance

The table below shows criteria you should consider when evaluating security and compliance aspects:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| Data residency | Where is data processed and stored? UK or EEA options available? | high |
| Data retention | How long are prompts and code retained? Can retention be disabled? | high |
| Training data usage | Is your code used to train models? Can this be disabled? | high |
| Security certifications | ISO 27001, SOC 2 Type II, Cyber Essentials Plus? | high |
| Government accreditation | Approved on G-Cloud? Any department-specific approvals? | high |
| Encryption | In-transit and at-rest encryption standards? | medium |
| Access controls | SSO integration, MFA support, RBAC capabilities? | medium |
| Audit logging | What usage logs are available? Export capabilities? | medium |
| Vulnerability disclosure | Clear process for reporting and handling security issues? | medium |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

---

### Category 2: capabilities and features

The table below shows criteria you should consider when evaluating capabilities and features:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| Code completion | Inline suggestions quality and speed? | high |
| Chat interface | Natural language interaction for explanations and refactoring? | high |
| Context awareness | How much codebase context can it use? | high |
| Multi-file editing | Can it modify multiple files in one operation? | medium |
| Test generation | Quality of generated unit and integration tests? | medium |
| Documentation | Can it generate meaningful documentation? | medium |
| Code review | Can it review PRs and suggest improvements? | medium |
| Agentic capabilities | Can it run multi-step tasks autonomously? | low to medium |
| Custom instructions | Can you configure coding standards and preferences? | medium |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

#### Capability comparison matrix

| Capability | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|------------|----------------|-------------|----------|---------------------|
| Inline completion | strong | via IDE | strong | strong |
| Chat interface | Copilot Chat | native | Q Chat | Gemini Chat |
| Codebase context | repo indexing | large context | workspace | code customisation |
| Multi-file edits | Copilot Edits | native | limited | limited |
| Test generation | good | strong | good | good |
| PR review | native | manual | native | limited |
| Agentic mode | Copilot Agent | strong | preview | limited |
| CLI interface | Copilot CLI | native | Q CLI | limited |

Legend: strong capability, limited or preview, not available

---

### Category 3: language and framework support

The table below shows criteria you should consider when evaluating language and framework support:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| Primary languages | Support quality for your main languages? | high |
| Framework awareness | Understanding of frameworks you use? | high |
| Legacy languages | Support for COBOL, VB6, older Java versions? | varies |
| Infrastructure as code | Terraform, CloudFormation, Ansible support? | medium |
| Markup and config | YAML, JSON, XML, Markdown support? | low |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

#### Language support matrix

| Language or framework | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|--------------------|----------------|-------------|----------|---------------------|
| Java and Spring | excellent | excellent | excellent | excellent |
| .NET and C# | excellent | excellent | good | good |
| Python | excellent | excellent | excellent | excellent |
| JavaScript and TypeScript | excellent | excellent | excellent | excellent |
| Go | good | good | good | good |
| Ruby | good | good | moderate | moderate |
| COBOL | limited | limited | good (mainframe focus) | limited |
| Terraform | good | good | excellent (AWS) | good (GCP) |
| GOV.UK Frontend | moderate | moderate | limited | limited |

Note: quality varies by specific use case. Conduct proof-of-concept testing with your actual codebase.

---

### Category 4: integration and deployment

The table below shows criteria you should consider when evaluating integration and deployment:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| IDE support | Works with your team's IDEs? | high |
| Git integration | GitHub, GitLab, Azure DevOps, Bitbucket? | high |
| CI and CD integration | Can it integrate with pipelines? | medium |
| API availability | Programmatic access for custom tooling? | low to medium |
| Offline capability | Can it work without internet? (usually no) | low |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

#### IDE support matrix

| IDE | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|-----|----------------|-------------|----------|---------------------|
| VS Code | yes | yes | yes | yes |
| JetBrains (IntelliJ and similar) | yes | yes | yes | yes |
| Visual Studio | yes | limited | yes | limited |
| Neovim and Vim | yes | yes (CLI) | limited | limited |
| Eclipse | limited | no | yes | limited |
| AWS Cloud9 | limited | no | native | no |

---

### Category 5: cost and licensing

The table below shows criteria you should consider when evaluating cost and licensing:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| Licence model | Per-user, per-organisation, consumption-based? | high |
| Tier options | Different tiers for different needs? | medium |
| Premium features | What requires additional payment? | medium |
| Volume discounts | Available for large deployments? | medium |
| True-up process | How are additional users handled? | low |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

#### Pricing model overview

| Aspect | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|--------|----------------|-------------|----------|---------------------|
| Model | per user per month | consumption plus subscription | per user per month | per user per month |
| Enterprise tier | available | available | available | available |
| Premium models | included | additional credits | included | included |

Note: DSIT is procuring licences centrally for Phase 1. Pricing details are for future reference and business case development.

---

### Category 6: support and ecosystem

The table below shows criteria you should consider when evaluating support and ecosystem:

| Criterion | Questions to consider | Weight |
|-----------|----------------------|--------|
| Vendor support | SLA, support channels, response times? | high |
| Documentation | Quality and currency of documentation? | medium |
| Community | Active community, forums, resources? | medium |
| Training resources | Vendor-provided training available? | medium |
| Partner ecosystem | Integration partners, consultancies? | low |

The 'weight' column indicates the relative importance of each criterion when making your evaluation decision.

---

## Matching tools to team context

### Decision factors

Different tools suit different contexts. The table below shows factors to consider:

| Factor | Implications |
|--------|--------------|
| Existing ecosystem | Teams on Azure and GitHub may benefit from Copilot. AWS-heavy teams may benefit from Q. |
| Primary languages | Some tools excel at specific languages |
| Work type | Greenfield compared to legacy modernisation compared to maintenance |
| Security posture | Some departments have stricter requirements |
| Team maturity | Starting teams may need simpler tools |
| Agentic needs | Complex refactoring may benefit from agentic capabilities |

### Recommended evaluation approach

#### Step 1: define requirements (Week 1)

1. Document must-have security requirements.
2. List primary languages and frameworks.
3. Identify integration requirements (IDE, Git, CI and CD).
4. Determine budget constraints.
5. Capture any department-specific restrictions.

#### Step 2: shortlist tools (Week 1)

Using this guide and security requirements, identify one to 2 tools for proof of concept.

#### Step 3: conduct proof of concept (Weeks 2 to 4)

The table below shows activities to complete during your proof of concept:

| Activity | Purpose |
|----------|---------|
| Install and configure | Validate integration with your environment |
| Test with real code | Assess quality on your actual codebase |
| Evaluate multiple use cases | Code completion, testing, documentation, refactoring |
| Gather engineer feedback | Assess usability and satisfaction |
| Review security logs | Confirm compliance with requirements |

PoC evaluation template:

```
| Criterion                | Weight | Tool A score (1 to 5) | Tool B score (1 to 5) |
|--------------------------|--------|-----------------------|-----------------------|
| Code completion quality  | 20%    | [score 1-5]           | [score 1-5]           |
| Security compliance      | 25%    | [score 1-5]           | [score 1-5]           |
| Language support         | 15%    | [score 1-5]           | [score 1-5]           |
| Integration ease         | 15%    | [score 1-5]           | [score 1-5]           |
| Engineer satisfaction    | 15%    | [score 1-5]           | [score 1-5]           |
| Support quality          | 10%    | [score 1-5]           | [score 1-5]           |
| Weighted total           | 100%   | [calculate]           | [calculate]           |
```

#### Step 4: make recommendation (Week 5)

You should make a recommendation that documents the following information.

1. Evaluation criteria and weighting.
2. PoC findings and scores.
3. Engineer feedback summary.
4. Security assessment outcome.
5. Recommendation with rationale.
6. Implementation considerations.

---

## Multi-tool strategies

### When to consider multiple tools

The table below shows scenarios where multiple tools may be appropriate:

| Scenario | Rationale |
|----------|-----------|
| Different team needs | Legacy team needs COBOL support. Modern team needs agentic features. |
| Risk mitigation | Avoid single-vendor dependency |
| Best-of-breed | Use each tool for its strengths |
| Pilot comparison | Test tools before standardising |

### Multi-tool considerations

The table below shows considerations when using multiple tools:

| Consideration | Guidance |
|---------------|----------|
| Training complexity | Multiple tools mean more training burden |
| Support complexity | Multiple vendor relationships to manage |
| Context sharing | Learnings may not transfer between tools |
| Cost management | Track usage across multiple platforms |
| Guardrails consistency | Ensure consistent security controls |

### Recommended approach

For most departments, start with a single tool for initial adoption, then consider introducing additional tools once the first is embedded. This allows:

- focused training and support
- clear metrics attribution
- simpler change management
- easier troubleshooting

---

## Tool selection for common scenarios

### Scenario 1: Java modernisation team

Context: This example team is modernising legacy Java 8 applications to Java 17 and 21 with Spring Boot.

Key requirements include:

- strong Java and Spring understanding
- refactoring capabilities
- test generation

You should consider the following:

- all tools have good Java support
- Amazon Q has specific Java modernisation features
- Claude Code's agentic mode suits large refactoring

### Scenario 2: full-stack GOV.UK service team

Context: This example team is building a citizen-facing service using GOV.UK Frontend and a Node.js backend.

Key requirements include:

- JavaScript and TypeScript excellence
- understanding of GOV.UK patterns
- accessibility awareness

You should consider the following:

- MCP servers with GOV.UK standards for compliance
- all tools handle JS and TS well
- you may need custom context for GOV.UK Frontend patterns

### Scenario 3: data engineering team

Context: This example team is building data pipelines with Python, SQL, and cloud services.

Key requirements include:

- Python data libraries such as 'pandas'
- SQL generation and optimisation
- cloud service integration

You should consider the following::

- Amazon Q integrates well with AWS data services
- Gemini integrates with BigQuery and GCP
- all tools handle Python well

### Scenario 4: legacy COBOL maintenance

Context: This example team is maintaining critical COBOL systems with occasional modernisation.

Key requirements include:

- COBOL understanding
- mainframe context
- modernisation assistance

You should consider the following:

- Amazon Q has specific mainframe and COBOL features
- there's limited COBOL support across other tools
- you may need specialised prompting

### Scenario 5: infrastructure and platform team

Context: This example team is managing cloud infrastructure with Terraform, Kubernetes, and CI/CD.

Key requirements include:

- IaC support (Terraform, CloudFormation)
- Kubernetes and Helm understanding
- pipeline scripting

You should consider the following:

- Amazon Q is excellent for AWS CloudFormation
- Gemini is excellent for GCP resources
- GitHub Copilot is good for general Terraform
- your tool choice may align with cloud provider

---

## Questions to ask vendors

### Security and compliance

1. Where are prompts and code processed geographically?
2. What is your data retention policy? Can it be customised?
3. Is customer code used to train or improve models?
4. What security certifications do you hold?
5. Can you provide a SOC 2 Type II report?
6. What is your vulnerability disclosure process?
7. How do you handle security incidents affecting customers?
8. What audit logs are available and for how long?

### Technical capabilities

1. What is the context window size for code understanding?
2. How does the tool handle large monorepos?
3. What languages and frameworks have the best support?
4. Can custom instructions and rules be configured organisation-wide?
5. What API access is available for custom integrations?
6. How often are the underlying models updated?

### Commercial and support

1. What support SLAs are available?
2. What training resources do you provide?
3. How are new users provisioned and deprovisioned?
4. What usage analytics and reporting is available?
5. What is the contract exit process?
6. Can we pilot before full commitment?

---

## Ongoing tool management

### Usage monitoring

The table below shows metrics to monitor and their purpose:

| Metric | Purpose | Frequency |
|--------|---------|-----------|
| Active users | Licence utilisation | weekly |
| Suggestions accepted | Tool effectiveness | weekly |
| Features used | Adoption depth | monthly |
| Cost per user | Value assessment | monthly |

### Periodic review

The table below shows reviews to conduct and their frequency:

| Review | Frequency | Focus |
|--------|-----------|-------|
| Usage review | monthly | Adoption, utilisation, issues |
| Security review | quarterly | Compliance, incidents, updates |
| Value assessment | quarterly | Productivity impact, ROI |
| Tool reassessment | annually | Market changes, new options |

### Exit planning

Regardless of tool selection, you should maintain exit capability by:

- documenting tool-specific configurations
- avoiding deep proprietary integrations where possible
- ensuring code works without AI assistance
- maintaining tool-agnostic training materials
- tracking contract end dates and renewal terms

---

## Related documents

- [GitHub Copilot Guide](github-copilot/)
- [Amazon Q Engineer Guide](amazon-q/)
- [Model Selection Playbook](../playbooks/model-selection.md)

## References

- [G-Cloud Digital Marketplace](https://www.digitalmarketplace.service.gov.uk/g-cloud)
- [NCSC Cloud Security Principles](https://www.ncsc.gov.uk/collection/cloud-security)
- [Technology Code of Practice](https://www.gov.uk/guidance/the-technology-code-of-practice)