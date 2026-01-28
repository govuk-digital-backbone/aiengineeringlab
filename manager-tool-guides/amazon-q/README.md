> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Amazon Q - manager tool guide

> Central home for Amazon Q best practices content across government departments.

## Audience

Engineering managers, technical leads, and delivery managers responsible for AI Engineering Lab adoption in their teams.

## Purpose

This guide provides engineering managers with practical guidance for implementing Amazon Q within UK government departments. It covers capabilities assessment, security considerations, phased rollout strategies, and success measurement to support informed decision-making and sustainable adoption.

## What's in this guide

This guide is organised into the following sections:

**Understanding Amazon Q**
- [What Amazon Q does](#what-amazon-q-does) - core capabilities and interaction modes
- [How it compares with other AI Engineering Lab tools](#how-it-compares-with-other-ai-engineering-lab-tools) - feature comparison and when to use different tools
- [Q models and task suitability](#q-models-and-task-suitability) - choosing the right model for different tasks

**Implementation planning**
- [Government-specific considerations](#government-specific-considerations) - security classifications, data residency, and procurement
- [Getting started](#getting-started) - licensing options and installation process
- [Phased rollout approach](#phased-rollout-approach) - pilot through to full team adoption
- [Training requirements](#training-requirements) - engineer and manager training programmes

**Managing adoption**
- [Measuring success](#measuring-success) - metrics, ROI calculation, and feedback collection
- [Common implementation challenges](#common-implementation-challenges) - addressing resistance and technical issues
- [Integration with development workflow](#integration-with-development-workflow) - code review, Git workflow, testing, and CI/CD

**Additional resources**
- [Related resources](#related-resources) - links to official documentation, government guidance, and repository materials
- [Contributing](#contributing) - how to improve this guide
- [Support and contact](#support-and-contact) - getting help

## Prerequisites

Before reading this guide, you should understand:

- your team's current development workflow and tooling
- basic software development lifecycle concepts
- your department's security classification requirements
- the AI Engineering Lab maturity assessment framework (see [maturity assessment framework](../../assessment/maturity-assessment-framework.md) and [team classification guide](../../assessment/team-classification-guide.md))

## What Amazon Q does

Amazon Q Engineer provides AI-powered code assistance integrated with AWS services and development workflows. It generates code suggestions, explains existing code, and helps with AWS-specific tasks directly in your IDE and command line.

**Primary capabilities:**

- autocomplete code as engineers type
- generate implementations from comments or function signatures
- create and update unit tests
- explain code and answer technical questions
- assist with AWS service integration and infrastructure code
- perform security scans and code reviews
- support application modernisation and transformation

**Amazon Q interaction modes:**

Amazon Q offers several ways to interact with AI assistance, each suited for different tasks:

| Mode | Description | Best for | Available in |
|------|-------------|----------|--------------|
| Inline suggestions | Real-time completions as you type | Quick code completion, boilerplate | All tiers |
| Q Chat | Conversational interface in IDE | Explanations, debugging, AWS questions | All tiers |
| Agent mode | Autonomous multi-step task execution | Feature implementation, refactoring, testing | Engineer Pro |
| Command line | Terminal-based AI assistance | CLI workflows, script generation | All tiers |
| Code reviews | Automated security and quality scanning | PR reviews, security analysis | Engineer Pro |
| Code transformation | Large-scale code upgrades | Java version upgrades, framework migrations | Engineer Pro |

**When to use each mode:**

- inline suggestions: daily coding, implementing patterns, writing boilerplate
- chat: understanding AWS services, debugging, architecture questions
- agent mode: implementing features from requirements, comprehensive refactoring
- command line: DevOps tasks, AWS CLI operations, script generation
- code reviews: security scanning, best practice validation
- code transformation: upgrading Java versions, modernising legacy applications

**Best suited for:**

- teams working extensively with AWS services
- projects requiring AWS infrastructure as code
- Java application modernisation initiatives
- security-conscious development workflows
- teams needing integrated code scanning

**Not designed for:**

- non-AWS cloud provider specific tasks
- complex architectural decisions without human oversight
- replacing comprehensive security audits
- fully autonomous production deployments

## How it compares with other AI Engineering Lab tools

| Capability | Amazon Q Engineer | GitHub Copilot | Claude Code |
|---|---|---|---|
| Inline completion | Good | Excellent | Not available |
| Chat assistance | Good | Good | Excellent |
| Codebase understanding | Repository-wide | Current file only | Multi-file context |
| Execution capability | Limited | No | No |
| AWS integration | Native | Limited | Via API |
| Security scanning | Built-in | Separate tool | Not available |
| Code transformation | Java upgrades | Not available | Manual |
| Primary use case | AWS workflows | Fast completion | Reasoning tasks |

**When to choose Amazon Q:**

- your team primarily works with AWS services
- you need integrated security scanning in your workflow
- Java modernisation is a priority
- you want built-in code review capabilities
- your infrastructure is primarily AWS-based
- you need assistance with AWS CLI and CloudFormation

**When to combine with other tools:**

- use GitHub Copilot for faster inline completions in non-AWS contexts
- use Claude Code for complex architectural reasoning
- use Claude with AWS MCP server for enhanced AWS resource management
- combine Q's security scanning with manual security reviews

### AWS MCP server for enhanced workflows

The AWS MCP (Model Context Protocol) server enables AI assistants like Claude to interact with AWS resources, providing complementary capabilities to Amazon Q's native AWS integration.

**AWS MCP server capabilities:**

- resource management: query and manage AWS resources across services
- cost analysis: review AWS spending and optimisation opportunities
- security posture: analyse IAM policies and security configurations
- infrastructure review: examine CloudFormation and Terraform configurations
- service recommendations: get guidance on AWS service selection

**Example workflow combining Amazon Q and AWS MCP:**

1. Engineer uses Amazon Q inline suggestions for AWS SDK code.
2. Engineer uses Q Chat for CloudFormation template generation.
3. Engineering manager uses Claude with AWS MCP server to review infrastructure security.
4. Claude analyses IAM policies and suggests least-privilege improvements.
5. Manager reviews AI analysis and implements approved changes.

**Setting up AWS MCP server:**

The AWS MCP server is available for use with Claude and other MCP-compatible AI assistants. For configuration details, see:
- [AWS MCP server documentation](https://github.com/modelcontextprotocol/servers/tree/main/src/aws)

**Government considerations:**

- AWS MCP server requires IAM credentials with appropriate permissions
- use IAM roles with least-privilege access
- configure resource-level permissions to limit scope
- review data handling policies with your security team
- ensure compliance with your department's AWS usage policies
- consider using read-only permissions for analysis tasks

## Q models and task suitability

Amazon Q Engineer uses different models optimised for various development tasks. Understanding model capabilities helps set appropriate expectations and choose the right approach.

### Model comparison

| Model | Best for | Response time | Context window | Cost tier |
|---|---|---|---|---|
| Amazon Q Engineer | Code generation, AWS integration, general development | Fast (1 to 2 seconds) | Large (100,000+ tokens) | Standard |
| Amazon Q Engineer Pro | Advanced features, security scanning, transformations | Fast (1 to 2 seconds) | Large (100,000+ tokens) | Premium |

**Note**: Amazon Q uses AWS's proprietary models optimised for code generation and AWS service integration. Unlike some competitors, Q does not expose multiple model options to users - the appropriate model is selected automatically based on the task.

### Recommended features by task

| Task | Recommended approach | Why |
|---|---|---|
| Autocomplete as you type | Inline suggestions | Optimised for fast, context-aware completions |
| Generate unit tests | Agent mode (Pro) | Can create comprehensive test suites |
| Debug AWS integration issues | Q Chat | Direct access to AWS documentation and patterns |
| Write CloudFormation templates | Q Chat | Trained on AWS infrastructure patterns |
| Refactor legacy code | Agent mode (Pro) | Multi-file understanding and modification |
| Security code review | Code review feature (Pro) | Built-in security scanning |
| Upgrade Java applications | Code transformation (Pro) | Specialised for Java version migrations |
| Generate documentation | Q Chat | Good natural language generation |
| Implement AWS SDK calls | Inline suggestions | Trained on AWS SDK patterns |
| Optimise AWS costs | Q Chat | Can suggest cost-effective alternatives |

### Controlling feature usage

In Amazon Q, you interact with different capabilities through:

**IDE commands:**
- `/dev` - agent mode for feature implementation
- `/test` - generate unit tests
- `/doc` - generate documentation
- `/review` - security and code quality review
- `/transform` - code transformation (Java upgrades)

**Chat commands:**
- ask questions directly in Q Chat
- reference workspace with `@workspace`
- get AWS-specific help with service names

## Government-specific considerations

### Security classification

Amazon Q Engineer processes code snippets through AWS services. This means:

- OFFICIAL: generally acceptable with appropriate content exclusions configured
- OFFICIAL-SENSITIVE: requires risk assessment and strict content exclusions
- SECRET and above: not appropriate for these classifications

Consult your departmental security team before deployment. Reference [NCSC guidance on cloud services](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) for risk assessment.

### Content exclusions

You must configure Amazon Q to exclude sensitive files and patterns. Recommended exclusions for government projects:

```yaml
# Environment and configuration files
**/.env
**/.env.*
**/secrets/**
**/config/production.yml
**/config/production/**

# AWS credentials and configuration
**/credentials
**/.aws/credentials
**/.aws/config
**/aws-exports.js

# API keys and tokens
**/api-keys/**
**/*-key.json
**/*-credentials.json

# Department-specific patterns
**/citizen-data/**
**/personal-identifiable-information/**
**/security-configurations/**
**/terraform/production/**
```

### Data residency

Amazon Q Engineer processes requests through AWS services in AWS regions. As of January 2025:

- code suggestions are processed in AWS US regions
- no customer code is stored or used for model training
- telemetry data follows AWS data residency policies

Check your department's data residency requirements before deployment. For UK government, verify compliance with data sovereignty requirements.

### Intellectual property

Amazon Q Engineer Pro includes IP indemnity, meaning AWS provides legal protection if generated code infringes copyright. Free tier does not include this protection.

For government projects, use Amazon Q Engineer Pro only.

## Getting started

### Licensing options

**Amazon Q Engineer (Free)**:
- free for individual engineers
- not recommended for government projects
- no IP indemnity or enterprise controls
- limited features (no agent mode, transformations, or security scans)

**Amazon Q Engineer Pro**: $19 per month per user
- recommended for government teams
- IP indemnity included
- full feature access including agent mode
- security scanning and code reviews
- code transformation capabilities
- administrative controls via IAM Identity Center
- usage analytics and reporting
- no training on your code

### Procurement routes

Amazon Q Engineer is available through:

1. Crown Commercial Service G-Cloud 14: search for AWS offerings including Amazon Q.
2. AWS Enterprise Agreement: for departments with existing AWS Enterprise Support.
3. AWS Marketplace: direct subscription with consolidated billing.
4. TechUK Framework: through authorised AWS resellers.

Consult the procurement guidance documentation for detailed pathways.

### Installation process

**Step 1: AWS account setup**

1. Set up IAM Identity Center (if not already configured).
2. Create user groups for Amazon Q access.
3. Assign Amazon Q Engineer Pro licenses.
4. Configure content exclusion policies (via AWS console).

**Step 2: Engineer installation**

For VS Code:
```bash
# Install AWS Toolkit extension (includes Amazon Q)
code --install-extension amazonwebservices.aws-toolkit-vscode
```

For JetBrains IDEs:
- Settings → Plugins → Search "AWS Toolkit" → Install

For Visual Studio:
- Extensions → Manage Extensions → Search "AWS Toolkit" → Install

**Step 3: Authentication**

Engineers authenticate using IAM Identity Center:

1. Open AWS Toolkit in IDE.
2. Click "Connect to AWS".
3. Select "Use IAM Identity Center".
4. Enter your organisation's start URL.
5. Complete browser-based authentication.
6. Select AWS Builder ID or IAM Identity Center profile.

**Step 4: Verification**

Test installation by:
1. Opening a code file (Python, Java, JavaScript, and similar).
2. Start typing - inline suggestions should appear.
3. Open Q Chat panel and ask a question.
4. Verify authentication status shows "Connected".

## Phased rollout approach

### Phase 1: pilot (weeks 1 to 4)

**Objective**: validate effectiveness and identify issues

**Activities:**
- select 5 to 10 engineers across different experience levels
- focus on AWS-related projects or infrastructure work
- schedule weekly feedback sessions
- document effective usage patterns, especially for AWS tasks
- test security scanning features on real code

**Success criteria:**
- 70% or more of pilot users actively using Amazon Q
- no security incidents
- documented productivity benefits for AWS tasks
- clear implementation guidance for wider rollout
- positive feedback on security scanning features

### Phase 2: team expansion (weeks 5 to 12)

**Objective**: scale to full engineering team

**Activities:**
- roll out to entire team in groups of 10 to 15
- deliver 45-minute training sessions per group
- share pilot user success stories, especially AWS use cases
- establish support channels (Slack, Teams, or email)
- create internal knowledge base of effective prompts

**Success criteria:**
- 80% or more license activation rate
- acceptance rate above 20%
- engineers report time savings on AWS tasks
- no increase in security vulnerabilities
- active use of security scanning features

### Phase 3: optimisation (ongoing)

**Objective**: maximise value and address friction

**Activities:**
- review monthly usage analytics via AWS console
- refine content exclusion policies based on incidents
- update training materials based on common questions
- share wins across department
- explore advanced features (agent mode, transformations)

**Success criteria:**
- consistent month-on-month usage
- declining support tickets
- measurable productivity improvements
- positive engineer satisfaction scores
- successful use of advanced features

## Training requirements

### Engineer training (60 minutes)

**Module 1: basic usage** (20 minutes)
- accepting and rejecting inline suggestions
- using Q Chat for questions and explanations
- keyboard shortcuts and IDE integration
- when to use Q versus manual coding
- understanding suggestion confidence levels

**Module 2: AWS-specific features** (20 minutes)
- getting help with AWS services
- generating CloudFormation and CDK code
- using Q for AWS CLI commands
- troubleshooting AWS SDK integration
- best practices for infrastructure as code

**Module 3: advanced features and security** (20 minutes)
- using agent mode for feature implementation (`/dev`)
- running security scans (`/review`)
- generating comprehensive tests (`/test`)
- reviewing generated code critically
- content exclusions and when they apply
- integration with code review process

**Format**: live demonstration with hands-on practice using real AWS projects.

### Manager briefing (30 minutes)

**Topics:**
- capability overview and realistic expectations
- AWS-specific advantages and use cases
- usage metrics and how to interpret them (via AWS console)
- policy configuration and content exclusions
- addressing team concerns about AI tools
- return on investment calculation
- security scanning and compliance features

**Format**: presentation with Q&A session.

## Measuring success

### Quantitative metrics

**Adoption metrics:**
- license activation rate (target: 90% or more)
- daily active users (target: 80% or more of activated licenses)
- suggestion acceptance rate (target: 20% to 30%)
- security scan usage (target: weekly per engineer)

**Productivity metrics:**
- lines of code accepted per engineer per day
- time spent on AWS integration tasks (via engineer survey)
- CloudFormation and CDK template generation time
- pull request cycle time
- test coverage increase rate

**Quality metrics:**
- security vulnerabilities detected by Q reviews
- code review comments per PR (should remain stable)
- bug escape rate (should not increase)
- AWS best practice compliance

### Qualitative feedback

Conduct monthly engineer surveys asking:

1. How often do you use Amazon Q? (Daily, Weekly, Rarely, Never)
2. For which tasks is Amazon Q most helpful?
3. How helpful are the AWS-specific features?
4. Has Amazon Q affected your productivity? (Much faster, Somewhat faster, No change, Slower)
5. Do you feel confident reviewing Q-generated code?
6. How useful is the security scanning feature?

### Return on investment calculation

```
Monthly cost = $19 per engineer × number of licenses
Monthly time saved = hours saved per engineer × number of active users
Hourly rate = annual salary ÷ 1,800 (approximate working hours)

ROI = (time saved × hourly rate - monthly cost) ÷ monthly cost × 100
```

**Example for a team of 20 engineers:**
- monthly cost: $380 (£300 approx)
- time saved per engineer: 6 hours per month (conservative estimate)
- average hourly rate: £45
- monthly value: 20 × 6 × £45 = £5,400
- ROI: ((£5,400 - £300) ÷ £300) × 100 = 1,600%

Typical payback period: 1 to 2 months based on AWS customer case studies showing 10% to 20% productivity improvements.

**Additional value from security scanning:**
- reduced security vulnerabilities in production
- faster security review cycles
- earlier detection of issues (shift-left)

## Common implementation challenges

### Challenge: engineers not using the tool

**Symptoms:**
- low activation rates after 2 weeks
- acceptance rates below 15%
- feedback indicates suggestions are "not helpful"

**Interventions:**
1. Check content exclusions are not too restrictive.
2. Verify engineers understand keyboard shortcuts.
3. Provide pairing sessions with effective users.
4. Share specific AWS use case examples.
5. Demonstrate agent mode for complex tasks.
6. Show security scanning benefits.

### Challenge: security concerns from team

**Symptoms:**
- engineers questioning code suggestions
- reluctance to accept any generated code
- requests to disable tool

**Interventions:**
1. Clarify that code review process remains unchanged.
2. Demonstrate content exclusion configuration.
3. Show built-in security scanning features.
4. Reference IP indemnity coverage.
5. Share NCSC guidance compliance.
6. Demonstrate that Q helps identify security issues.

### Challenge: over-reliance on suggestions

**Symptoms:**
- decreased code review thoroughness
- accepting suggestions without understanding them
- reduced manual problem-solving attempts

**Interventions:**
1. Reinforce code review standards.
2. Include "understanding of implementation" in review checklist.
3. Encourage treating suggestions as first drafts.
4. Pair junior engineers with seniors during adoption.
5. Emphasise security scanning as complement, not replacement.

### Challenge: AWS-specific confusion

**Symptoms:**
- suggestions do not match team's AWS patterns
- generated CloudFormation templates need significant modification
- confusion about AWS service recommendations

**Interventions:**
1. Provide AWS-specific training on Q usage.
2. Create internal library of effective AWS prompts.
3. Document team's AWS architecture patterns.
4. Use Q Chat to ask clarifying questions about AWS services.
5. Use agent mode for complex AWS integrations.

### Challenge: variable suggestion quality

**Symptoms:**
- inconsistent helpfulness across different codebases
- better suggestions in some languages than others
- suggestions do not match project patterns

**Interventions:**
1. Improve context through better comments and function signatures.
2. Ensure relevant code is visible in workspace.
3. Use Q Chat for complex scenarios instead of inline.
4. Check if content exclusions are blocking helpful context.
5. Use agent mode for multi-file context understanding.

## Integration with development workflow

### Code review process

Amazon Q-generated code should pass through the same review process as human-written code. Recommended review checklist:

- logic correctness and edge case handling
- no hardcoded secrets or sensitive data
- compliance with team coding standards
- appropriate error handling
- security implications considered (use `/review` command)
- AWS best practices followed
- test coverage adequate
- performance and cost characteristics acceptable
- IAM permissions follow least-privilege principle

**Using Q's built-in code review:**

Before submitting PRs, engineers should run:
```
/review
```

This triggers Amazon Q's security and code quality scan, which checks for:
- security vulnerabilities
- code quality issues
- AWS best practice violations
- potential bugs

**Responsible use guidance:**

- review all AI-generated code with the same rigour as human-written code
- understand the code before accepting it into your codebase
- test thoroughly, especially AWS integrations and error conditions
- be aware of potential security vulnerabilities in suggestions
- maintain accountability - the engineer approving the code is responsible for it
- use `/review` command but do not rely on it exclusively

### Git workflow

No changes needed to your existing Git workflow. Amazon Q operates at the IDE level and does not affect commits, branches, or merges.

Some teams choose to document AI usage in commit messages:

```
feat: Add S3 bucket lifecycle policy

Implemented lifecycle rules using Amazon Q assistance for
AWS SDK integration. Security scan passed. IAM permissions reviewed.
```

This is optional and should align with your team's commit message conventions.

### Testing strategy

Treat Amazon Q-generated code as untested until proven otherwise:

1. Unit tests: use `/test` command to generate test scaffolding, then review and enhance.
2. Integration tests: manually verify AWS service interactions.
3. Security tests: run `/review` and SAST tools on all code.
4. AWS-specific tests: test IAM permissions, resource limits, error handling.
5. Manual review: code review remains mandatory.

### CI/CD pipeline

Amazon Q does not require changes to your pipeline. Ensure existing quality gates remain in place:

- linting and formatting checks
- unit test execution and coverage thresholds
- static analysis and security scanning
- integration and end-to-end test suites
- AWS resource validation (CloudFormation linting, and similar)

Generated code must pass all gates before merging.

**Optional enhancement**: consider integrating Amazon Q security scanning into CI/CD for automated security checks.

## Policy configuration reference

### Recommended content exclusions

Configure in AWS console under Amazon Q Engineer settings:

```yaml
# Secrets and credentials
**/.env
**/.env.*
**/secrets/**
**/*.key
**/*.pem
**/credentials
**/.aws/**

# AWS-specific sensitive files
**/aws-exports.js
**/amplify-config.json
**/terraform.tfstate
**/terraform.tfstate.backup

# Configuration files
**/config/production.yml
**/config/production/**
**/terraform/production/**
**/cloudformation/production/**

# Citizen data
**/citizen-data/**
**/personal-identifiable-information/**
**/user-data/**

# Security configurations
**/security-configurations/**
**/iam-policies/production/**
**/security-groups/production/**
```

### IDE-level settings

Example VS Code configuration:

```json
{
  "aws.codeWhisperer.includeSuggestionsWithCodeReferences": false,
  "aws.codeWhisperer.shareCodeWhispererContentWithAWS": false,
  "aws.suppressPrompts": {
    "codeWhispererNewWelcomeMessage": true
  },
  "editor.inlineSuggest.enabled": true
}
```

Disable Amazon Q for specific file types where suggestions are not helpful:

```json
{
  "aws.codeWhisperer.enabledLanguages": {
    "python": true,
    "javascript": true,
    "typescript": true,
    "java": true,
    "yaml": false,
    "plaintext": false
  }
}
```

### Organisation-level settings

Configure in AWS console:

1. Navigate to IAM Identity Center → Applications → Amazon Q Engineer.
2. Assign users and groups.
3. Configure content exclusions (Settings → Content Exclusions).
4. Set up usage analytics (CloudWatch integration).
5. Configure sharing preferences (opt-out of telemetry if required).

**IAM policy example for Amazon Q access:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "codewhisperer:GenerateRecommendations",
        "codewhisperer:GetCodeAnalysis"
      ],
      "Resource": "*"
    }
  ]
}
```

## Next steps

1. Assess readiness: complete the maturity assessment (see [maturity assessment framework](../../assessment/maturity-assessment-framework.md) and [team classification guide](../../assessment/team-classification-guide.md)) to determine if your team is ready for Amazon Q.
2. Review security: consult your security team about content exclusions for your specific projects.
3. Verify AWS access: ensure IAM Identity Center is configured and users can be assigned.
4. Start procurement: acquire licenses through appropriate procurement routes (see [Getting started](#getting-started) section).
5. Plan pilot: identify 5 to 10 pilot users, prioritising those working with AWS.
6. Measure impact: set baseline metrics before deployment.

## Related resources

### Official AWS resources

- [Amazon Q Engineer documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/) - complete official documentation
- [Amazon Q Engineer features](https://aws.amazon.com/q/developer/) - feature overview and capabilities
- [Getting started with Amazon Q](https://aws.amazon.com/q/developer/getting-started/) - initial setup guides
- [Amazon Q Engineer pricing](https://aws.amazon.com/q/developer/pricing/) - licensing and cost information
- [AWS re:Post for Amazon Q](https://repost.aws/tags/TA4ckYf2i3Rh-L8LJ8eKPxqg/amazon-q) - community questions and answers

### Enterprise and security

- [Managing Amazon Q in your organisation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-iam.html) - IAM and access control
- [Amazon Q security](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security.html) - security features and best practices
- [Content exclusions](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-data-protection.html) - configuring what Amazon Q can access
- [AWS Artifact](https://aws.amazon.com/artifact/) - compliance reports and certifications

### Government procurement

- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [AWS on G-Cloud](https://www.digitalmarketplace.service.gov.uk/) - search for AWS services including Amazon Q
- [TechUK Framework](https://www.techuk.org/) - alternative procurement route

### NCSC guidance

- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - handling security issues

### Repository resources

- [AI SDLC Playbook](../../playbooks/ai-sdlc-playbook.md) - integrating AI Engineering Lab tools across development lifecycle
- [Model Selection Playbook](../../playbooks/model-selection.md) - choosing appropriate tools for tasks
- [GitHub Copilot Manager Guide](../copilot/README.md) - complementary tool for inline completions

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government to keep this repository current and comprehensive. Share your team's experience, lessons learned, and effective practices to help other government departments.

Before contributing, read [CONTRIBUTING.md](../../CONTRIBUTING.md) which covers:

- content standards and style guide
- review and approval process
- accessibility requirements
- how to submit changes


## Support and contact

| Need | Contact |
|------|---------|
| General enquiries | to be confirmed |
| FDE support requests | to be confirmed |
| Urgent issues | to be confirmed |
| Content feedback | to be confirmed |

Contact details to be confirmed.

## Licence

This repository is published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

You are encouraged to use and adapt these materials for your own government context.

When reusing content:

- maintain attribution to this repository
- share improvements back via contribution
- ensure adaptations remain suitable for government use.
