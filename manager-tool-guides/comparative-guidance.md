> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Comparative Guidance

> A tool-agnostic framework for evaluating, selecting, and managing AI Engineering Labs across government.

## Purpose

This guide helps technical leads, delivery managers, and senior decision-makers evaluate AI Engineering Labs for their teams and departments. It provides objective comparison criteria, questions to ask vendors, and guidance on matching tools to team contexts.

This guide does not recommend specific tools. Instead, it equips you to make informed decisions based on your team's needs, security requirements, and ways of working.

## Tools in scope

The DSIT AI Engineering Lab Programme Phase 1 includes licences for:

| Tool | Vendor | Primary Interface |
|------|--------|-------------------|
| GitHub Copilot Enterprise | Microsoft/GitHub | IDE extension, Chat, CLI |
| Claude Code | Anthropic | CLI, IDE extension, API |
| Amazon Kiro or Q Engineer | AWS | CLI, IDE extension, Console |
| Gemini Code Assist | Google | IDE extension, Cloud Console |

For tool-specific implementation guidance, see:

- [GitHub Copilot Guide](copilot/README.md)
- [Amazon Q Engineer Guide](amazon-q/README.md)

---

## Evaluation framework

### Category 1: Security and compliance

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **Data residency** | Where is data processed and stored? UK/EEA options available? | High |
| **Data retention** | How long are prompts/code retained? Can retention be disabled? | High |
| **Training data usage** | Is your code used to train models? Can this be disabled? | High |
| **Security certifications** | ISO 27001, SOC 2 Type II, Cyber Essentials Plus? | High |
| **Government accreditation** | Approved on G-Cloud? Any department-specific approvals? | High |
| **Encryption** | In-transit and at-rest encryption standards? | Medium |
| **Access controls** | SSO integration, MFA support, RBAC capabilities? | Medium |
| **Audit logging** | What usage logs are available? Export capabilities? | Medium |
| **Vulnerability disclosure** | Clear process for reporting and handling security issues? | Medium |

#### Security comparison matrix

| Feature | GitHub Copilot Enterprise | Claude Code | Amazon Q Engineer | Gemini Code Assist |
|---------|---------------------------|-------------|--------------------|--------------------|
| UK data residency | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| No training on your code | ✅ (Enterprise) | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| SOC 2 Type II | ✅ | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| ISO 27001 | ✅ | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| G-Cloud listed | ✅ | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| SSO/SAML support | ✅ | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Audit logs | ✅ | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

> **Note:** Security features change frequently. Verify current status with vendors and your security team before deployment.

---

### Category 2: Capabilities and features

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **Code completion** | Inline suggestions quality and speed? | High |
| **Chat interface** | Natural language interaction for explanations/refactoring? | High |
| **Context awareness** | How much codebase context can it use? | High |
| **Multi-file editing** | Can it modify multiple files in one operation? | Medium |
| **Test generation** | Quality of generated unit/integration tests? | Medium |
| **Documentation** | Can it generate meaningful documentation? | Medium |
| **Code review** | Can it review PRs and suggest improvements? | Medium |
| **Agentic capabilities** | Can it execute multi-step tasks autonomously? | Low-Medium |
| **Custom instructions** | Can you configure coding standards/preferences? | Medium |

#### Capability comparison matrix

| Capability | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|------------|----------------|-------------|----------|---------------------|
| Inline completion | ✅ Strong | ✅ Via IDE | ✅ Strong | ✅ Strong |
| Chat interface | ✅ Copilot Chat | ✅ Native | ✅ Q Chat | ✅ Gemini Chat |
| Codebase context | ✅ Repo indexing | ✅ Large context | ✅ Workspace | ✅ Code customisation |
| Multi-file edits | ✅ Copilot Edits | ✅ Native | ⚠️ Limited | ⚠️ Limited |
| Test generation | ✅ Good | ✅ Strong | ✅ Good | ✅ Good |
| PR review | ✅ Native | ⚠️ Manual | ✅ Native | ⚠️ Limited |
| Agentic mode | ✅ Copilot Agent | ✅ Strong | ⚠️ Preview | ⚠️ Limited |
| CLI interface | ✅ Copilot CLI | ✅ Native | ✅ Q CLI | ⚠️ Limited |

> **Legend:** ✅ Strong capability | ⚠️ Limited/Preview | ❌ Not available

---

### Category 3: Language and framework support

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **Primary languages** | Support quality for your main languages? | High |
| **Framework awareness** | Understanding of frameworks you use? | High |
| **Legacy languages** | Support for COBOL, VB6, older Java versions? | Varies |
| **Infrastructure as Code** | Terraform, CloudFormation, Ansible support? | Medium |
| **Markup/Config** | YAML, JSON, XML, Markdown support? | Low |

#### Language support matrix

| Language/Framework | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|--------------------|----------------|-------------|----------|---------------------|
| Java / Spring | ✅ Excellent | ✅ Excellent | ✅ Excellent | ✅ Excellent |
| .NET / C# | ✅ Excellent | ✅ Excellent | ✅ Good | ✅ Good |
| Python | ✅ Excellent | ✅ Excellent | ✅ Excellent | ✅ Excellent |
| JavaScript/TypeScript | ✅ Excellent | ✅ Excellent | ✅ Excellent | ✅ Excellent |
| Go | ✅ Good | ✅ Good | ✅ Good | ✅ Good |
| Ruby | ✅ Good | ✅ Good | ⚠️ Moderate | ⚠️ Moderate |
| COBOL | ⚠️ Limited | ⚠️ Limited | ✅ Good (mainframe focus) | ⚠️ Limited |
| Terraform | ✅ Good | ✅ Good | ✅ Excellent (AWS) | ✅ Good (GCP) |
| GOV.UK Frontend | ⚠️ Moderate | ⚠️ Moderate | ⚠️ Limited | ⚠️ Limited |

> **Note:** Quality varies by specific use case. Conduct proof-of-concept testing with your actual codebase.

---

### Category 4: Integration and deployment

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **IDE support** | Works with your team's IDEs? | High |
| **Git integration** | GitHub, GitLab, Azure DevOps, Bitbucket? | High |
| **CI/CD integration** | Can it integrate with pipelines? | Medium |
| **API availability** | Programmatic access for custom tooling? | Low-Medium |
| **Offline capability** | Can it work without internet? (Usually no) | Low |

#### IDE support matrix

| IDE | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|-----|----------------|-------------|----------|---------------------|
| VS Code | ✅ | ✅ | ✅ | ✅ |
| JetBrains (IntelliJ, etc.) | ✅ | ✅ | ✅ | ✅ |
| Visual Studio | ✅ | ⚠️ Limited | ✅ | ⚠️ Limited |
| Neovim/Vim | ✅ | ✅ (CLI) | ⚠️ Limited | ⚠️ Limited |
| Eclipse | ⚠️ Limited | ❌ | ✅ | ⚠️ Limited |
| AWS Cloud9 | ⚠️ Limited | ❌ | ✅ Native | ❌ |

---

### Category 5: Cost and licensing

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **Licence model** | Per-user, per-organisation, consumption-based? | High |
| **Tier options** | Different tiers for different needs? | Medium |
| **Premium features** | What requires additional payment? | Medium |
| **Volume discounts** | Available for large deployments? | Medium |
| **True-up process** | How are additional users handled? | Low |

#### Pricing model overview

| Aspect | GitHub Copilot | Claude Code | Amazon Q | Gemini Code Assist |
|--------|----------------|-------------|----------|---------------------|
| Model | Per user/month | Consumption + subscription | Per user/month | Per user/month |
| Enterprise tier | ✅ Available | ✅ Available | ✅ Available | ✅ Available |
| Premium models | Included | Additional credits | Included | Included |

> **Note:** DSIT is procuring licences centrally for Phase 1. Pricing details are for future reference and business case development.

---

### Category 6: Support and ecosystem

| Criterion | Questions to Consider | Weight |
|-----------|----------------------|--------|
| **Vendor support** | SLA, support channels, response times? | High |
| **Documentation** | Quality and currency of documentation? | Medium |
| **Community** | Active community, forums, resources? | Medium |
| **Training resources** | Vendor-provided training available? | Medium |
| **Partner ecosystem** | Integration partners, consultancies? | Low |

---

## Matching tools to team context

### Decision factors

Different tools suit different contexts. Consider:

| Factor | Implications |
|--------|--------------|
| **Existing ecosystem** | Teams on Azure/GitHub may benefit from Copilot; AWS-heavy teams from Q |
| **Primary languages** | Some tools excel at specific languages |
| **Work type** | Greenfield vs legacy modernisation vs maintenance |
| **Security posture** | Some departments have stricter requirements |
| **Team maturity** | Starting teams may need simpler tools |
| **Agentic needs** | Complex refactoring may benefit from agentic capabilities |

### Recommended evaluation approach

#### Step 1: Define requirements (Week 1)

- Document must-have security requirements
- List primary languages and frameworks
- Identify integration requirements (IDE, Git, CI/CD)
- Determine budget constraints
- Capture any department-specific restrictions

#### Step 2: Shortlist tools (Week 1)

Using this guide and security requirements, identify 1-2 tools for proof of concept.

#### Step 3: Conduct proof of concept (Weeks 2-4)

| Activity                    | Purpose |
|-----------------------------|---------|
| Install and configure       | Validate integration with your environment |
| Test with real code         | Assess quality on your actual codebase |
| Evaluate multiple use cases | Code completion, testing, documentation, refactoring |
| Gather engineer feedback    | Assess usability and satisfaction |
| Review security logs        | Confirm compliance with requirements |

**PoC evaluation template:**

| Criterion | Weight | Tool A Score (1-5) | Tool B Score (1-5) |
|-----------|--------|--------------------|--------------------|
| Code completion quality | 20% | | |
| Security compliance | 25% | | |
| Language support | 15% | | |
| Integration ease | 15% | | |
| Engineer satisfaction | 15% | | |
| Support quality | 10% | | |
| **Weighted total** | 100% | | |

#### Step 4: Make recommendation (Week 5)

Document:

- Evaluation criteria and weighting
- PoC findings and scores
- Engineer feedback summary
- Security assessment outcome
- Recommendation with rationale
- Implementation considerations

---

## Multi-tool strategies

### When to consider multiple tools

| Scenario | Rationale |
|----------|-----------|
| Different team needs | Legacy team needs COBOL support; modern team needs agentic features |
| Risk mitigation | Avoid single-vendor dependency |
| Best-of-breed | Use each tool for its strengths |
| Pilot comparison | Test tools before standardising |

### Multi-tool considerations

| Consideration | Guidance |
|---------------|----------|
| Training complexity | Multiple tools = more training burden |
| Support complexity | Multiple vendor relationships to manage |
| Context sharing | Learnings may not transfer between tools |
| Cost management | Track usage across multiple platforms |
| Guardrails consistency | Ensure consistent security controls |

### Recommended approach

For most departments, **start with a single tool** for initial adoption, then consider introducing additional tools once the first is embedded. This allows:

- Focused training and support
- Clear metrics attribution
- Simpler change management
- Easier troubleshooting

---

## Tool selection for common scenarios

### Scenario 1: Java modernisation team

**Context:** Team modernising legacy Java 8 applications to Java 17/21 with Spring Boot.

**Key requirements:**
- Strong Java/Spring understanding
- Refactoring capabilities
- Test generation

**Considerations:**
- All tools have good Java support
- Amazon Q has specific Java modernisation features
- Claude Code's agentic mode suits large refactoring

### Scenario 2: Full-stack GOV.UK service team

**Context:** Team building citizen-facing service using GOV.UK Frontend, Node.js backend.

**Key requirements:**
- JavaScript/TypeScript excellence
- Understanding of GOV.UK patterns
- Accessibility awareness

**Considerations:**
- Consider MCP servers with GOV.UK standards for compliance
- All tools handle JS/TS well
- May need custom context for GOV.UK Frontend patterns

### Scenario 3: Data engineering team

**Context:** Team building data pipelines with Python, SQL, and cloud services.

**Key requirements:**
- Python data libraries (pandas, etc.)
- SQL generation and optimisation
- Cloud service integration

**Considerations:**
- Amazon Q integrates well with AWS data services
- Gemini integrates with BigQuery/GCP
- All tools handle Python well

### Scenario 4: Legacy COBOL maintenance

**Context:** Team maintaining critical COBOL systems with occasional modernisation.

**Key requirements:**
- COBOL understanding
- Mainframe context
- Modernisation assistance

**Considerations:**
- Amazon Q has specific mainframe/COBOL features
- Limited COBOL support across other tools
- May need specialised prompting

### Scenario 5: Infrastructure/Platform team

**Context:** Team managing cloud infrastructure with Terraform, Kubernetes, CI/CD.

**Key requirements:**
- IaC support (Terraform, CloudFormation)
- Kubernetes/Helm understanding
- Pipeline scripting

**Considerations:**
- Amazon Q excellent for AWS CloudFormation
- Gemini excellent for GCP resources
- GitHub Copilot good for general Terraform
- Tool choice may align with cloud provider

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
3. What languages/frameworks have the best support?
4. Can custom instructions/rules be configured organisation-wide?
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

| Metric | Purpose | Frequency |
|--------|---------|-----------|
| Active users | Licence utilisation | Weekly |
| Suggestions accepted | Tool effectiveness | Weekly |
| Features used | Adoption depth | Monthly |
| Cost per user | Value assessment | Monthly |

### Periodic review

| Review | Frequency | Focus |
|--------|-----------|-------|
| Usage review | Monthly | Adoption, utilisation, issues |
| Security review | Quarterly | Compliance, incidents, updates |
| Value assessment | Quarterly | Productivity impact, ROI |
| Tool reassessment | Annually | Market changes, new options |

### Exit planning

Regardless of tool selection, maintain exit capability:

- Document tool-specific configurations
- Avoid deep proprietary integrations where possible
- Ensure code works without AI assistance
- Maintain tool-agnostic training materials
- Track contract end dates and renewal terms

---

## Related documents

- [GitHub Copilot Guide](copilot/README.md)
- [Amazon Q Engineer Guide](amazon-q/README.md)
- [Model Selection Playbook](../playbooks/model-selection.md)

## References

- [G-Cloud Digital Marketplace](https://www.digitalmarketplace.service.gov.uk/g-cloud)
- [NCSC Cloud Security Principles](https://www.ncsc.gov.uk/collection/cloud-security)
- [Technology Code of Practice](https://www.gov.uk/guidance/the-technology-code-of-practice)