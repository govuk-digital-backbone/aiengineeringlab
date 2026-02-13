> **ALPHA**
> This is a new service. Your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Amazon Kiro manager tool guide

> Autonomous AI development environment that works alongside developers through specification-driven workflows and persistent context.
    
## Purpose
This guide provides engineering managers with practical guidance for implementing Amazon Kiro within UK government departments. It covers capabilities assessment, security considerations, phased rollout strategies, and success measurement to support informed decision-making and sustainable adoption.
This guide also explains how it differs from other AI code assistants, and how to use it effectively for complex software development tasks.

## Who this is for
This guide is for:
- software engineers working on complex, long-lived applications
- technical leads evaluating autonomous coding tools
- API developers and backend teams requiring structured development
- engineering teams needing persistent, context-aware AI assistance
    
    
## What's in this guide
    
This guide is organised into the following sections.

**Understanding Amazon Kiro**
- [What Amazon Kiro does](#what-amazon-kiro-does) - core capabilities and interaction modes
- [How it compares with other AI code assistants](#how-it-compares-with-other-ai-code-assistants) - feature comparison and when to use different tools
- [Amazon Kiro models and task suitability](#amazon-kiro-models-and-task-suitability) - choosing the right model for different tasks
    
**Implementation planning:**
- [UK Government-specific considerations](#uk-government-specific-considerations) - security classifications, data residency, and procurement
- [Getting started](#getting-started) - licensing options and installation process
- [Training requirements](#training-requirements) - engineer and manager training programmes

**Managing adoption:**
- [Measuring success](#measuring-success) - quality metrics  
- [Common troubleshooting scenarios](#common-troubleshooting-scenarios) - symptoms and solutions
- [Policy configuration reference](#policy-configuration-reference) - content exclusions and IDE settings
- [Integration with development workflow](#integration-with-development-workflow) - Code review, Git workflow, testing, and CI/CD


**Additional resources:**
- [Related resources](#related-resources) - links to official documentation, government guidance, and repository materials
- [Contributing](#contributing) - how to improve this guide
- [Licence](#licence) - open licences
    
## Before you start
You need:
- a clear understanding of your application’s language and stack
- familiarity with version control and development workflows
- an AWS account and identity setup if using cloud integrations
- a development environment (IDE/CLI/VS code)
- awareness of AI limitations and cost model
- testing and validation practices in place

Note: you do not need an AWS account to use Kiro.
    
## What Amazon Kiro does
Amazon Kiro is an AI powered software development assistant that helps developers design, write, test, and maintain code by converting natural language requirements into structured engineering outputs.
Think of it as AI that understands software development workflows, not just code autocomplete.

**Kiro's primary capabilities include:**

- providing autonomous task execution 
- supporting specification-driven development 
- turning ideas into engineering specs 
- generating and modifies code 
- creating tests and documentation 
- acting as an agent that can perform tasks
- providing steering files for persistent knowledge 
- providing agent hooks for automation 
- providing multi-model intelligence

**Amazon Kiro interaction modes**

Amazon Kiro supports multiple interaction modes, each designed for a different stage of software development.

| Mode | Description | Best suited for |
|------|-------------|-----------------|
| Chat / Conversational Mode | A natural-language interface | Asking questions or giving instructions, high-level guidance, understanding existing code, similar to ChatGPT | 
| Spec / Planning Mode (Design-Oriented) | A structured mode where Kiro helps turn requirements into engineering artifacts | Functional requirements, technical design and task breakdowns |
| Code Generation / Edit Mode | Kiro directly writes or modifies code in your repository | Creating new files, adding features, refactoring existing code, fixing bugs |
| Test Generation Mode | Focused on generating tests alongside code | Unit tests, test scaffolding, edge-case coverage |
| Documentation Mode | Generates or updates developer documentation | README sections, API documentation, Inline comments, design docs |
| Agentic / Multi-Step Task Mode | Kiro acts as an agent | Plan a task, execute multiple steps, iterate based on feedback, this is task-oriented |


**When to use each mode**
- chat - ask questions
- spec - plan the work
- code - implement
- test - validate
- docs - explain
- agent - do all of it together

## How it compares with other AI code assistants

**Quick comparison matrix**
| AI Tool | What it is | Strengths |
|---------|------------|-----------|
| Amazon Kiro | AI-first IDE + CLI with spec-driven workflow | Specs → design → tasks, agent hooks, Model Context Protocol (MCP), autopilot, VS Code settings/plugins compatibility |
| Amazon Q Developer | AWS coding assistant in IDE/CLI + AWS console help | AWS-native software development lifecycle (SDLC) help, IDE + CLI, transformation capabilities (Java/.NET), governance features |
| GitHub Copilot | Ubiquitous AI assistant inside many IDEs + GitHub | Broad IDE support, agent/chat, multiple model choices, strong GitHub workflow integration |
| Cursor | AI-first VS Code-style editor | AI native editor, agents, Bugbot, usage based model API pricing approach |
| Windsurf (Codeium) | Agentic IDE + plugins, prompt-credit model | Free tier, multiple model providers, team controls and “Fast Context” options |
| JetBrains AI (Junie) | Agentic assistant inside JetBrains IDEs | Deep JetBrains IDE integration, credit based plans, Junie agent in AI chat |
| Anthropic Claude (Claude Code) | Claude with terminal/desktop extensions | Claude Pro includes access to Claude Code “on the web and in your terminal”, strong general reasoning | 

## Amazon Kiro models and task suitability
Kiro doesn’t use a single model. It’s built on Amazon Bedrock, meaning it can use multiple large language models under the hood. The primary models currently powering Kiro are Anthropic Claude Sonnet 4.0 and Sonnet 3.7.
| Model	| Strengths	| Typical Tasks |
|-------|-----------|---------------|
| Claude Sonnet 4.0	| Best balance of reasoning, code understanding, and detailed output | Complex specs → code tasks, multi-step planning, design artifacts | 
| Claude Sonnet 3.7	| Fallback model: slightly lighter and faster	| Less intensive tasks, chats, simple code generation |
| Auto routing (internal routing mix) |	Dynamically selects models for efficiency |	Efficiently balances quality vs cost on tasks |

Kiro combines these models into different interaction/task contexts that influence which model capabilities are used most effectively:
| Modes | Best used | Model Suitability |
|-------|-----------|-------------------|
| Vibe Mode (Chat / Conversational) | Asked about code, getting quick clarifications, debugging explanations, Exploratory learning, immediate help, understanding segments of code | Uses conversational reasoning models (Claude variants) to interpret and respond to questions |
| Spec-Driven Planning Mode | High-level requirement and structured output, generates structured spec artifacts | Excellent for complex planning and early stage design when deep reasoning and project context are required |
| Autopilot / Task Execution Mode | Automatically generate or modify code, run tasks end-to-end autonomously |  Heavy use of robust reasoning models to plan and sequence tasks, propagate context across files, and maintain coherence |
| Agent Hooks Mode | Automated actions triggered by events,  update tests when a file changes, trigger documentation updates | Streamlines repetitive tasks by invoking agents with relevant model contexts |
| Steering Rules / External Context Mode | Consistent conventions across tasks | Maintain consistency, especially in large projects where repeated conventions matter |

For detailed model capabilities and limitations, see:

- [Amazon Kiro supported models](https://kiro.dev/)
- [AI model comparison](https://docs.github.com/en/copilot/reference/ai-models/model-comparison)

# UK Government-specific considerations
Unlike the EU, UK uses principle-based regulatory approach, regulated through existing legal frameworks and sector specific guidance, with additional guidance for public sector AI ethics and governance.

### Security classification

Regulatory Context: AI must align with broad expectations that regulators will apply within existing legal regimes. Its Key principles include: safety, security, transparency, fairness, accountability and governance.

AI Playbook for the UK Government: Government departments must follow the following principles.

- using AI lawfully, ethically and responsibly

- maintaining human oversight

- understanding and managing the AI lifecycle

- being open and transparent about AI use

- applying ethical considerations at each stage

Transparency & Algorithmic Accountability: If an AI system influences decisions in public services, departments often must register it under frameworks like the Algorithmic Transparency Recording Standard(ATRS).
Failing to document or disclose systems undermines public trust and may violate transparency expectations for public authorities.

Data Protection Laws (General Data Protection Regulation(GDPR) & Data Protection Act 2018): Use of AI tools must comply with UK GDPR, which governs personal data processing. You must justify why personal data is processed and justifications are necessary. Only provide minimum data needed to Kiro and avoid feeding unnecessary personal data into language models. If AI processing is likely to pose high risk to individuals’ rights and freedom, a Data Protection Impact Assessments(DPIA) is required.

Ethics & Human Control: Critical decisions should involve meaningful human review and it should be fair use.

Security & Risk Management: Protect infrastructure and data, evaluate and mitigate risks early through robust risk management frameworks to ensure AI tools does not expose sensitive government data or jeopardise system integrity.

Consult your departmental security team before deployment. Reference [NCSC guidance on cloud services](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) for risk assessment.

### Content exclusions
Amazon Kiro supports configurable file‑access denial patterns. AWS documentation confirms that Kiro relies on AWS security and follows a shared responsibility model where users are responsible for protecting sensitive files within their project workspace.
### Sensitive-file exclusion patterns in Kiro 
```yaml
{
  "permissions": {
    "deny": [
      "Read(.env)",
      "Read(env.json)",
      "Read(.env.*)",
      "Read(**/.env)",
      "Read(**/.env.*)",
      "Read(**/secrets.*)",
      "Read(**/*.key)",
      "Read(**/*.pem)",
      "Read(**/config/production.*)",
      "Read(**/.git/config)",
      "Read(**/node_modules/**)"
    ]
  }
}
```
### Exclusion Patterns for Government Projects
```yaml
# Credential & Secret Files: Highly sensitive and always excluded
**/*.pem
**/*.key
**/*.pfx
**/*.p12
**/secrets.*
**/.secrets/**
**/*.gpg
**/*.asc
**/private/**

# Environment / Configuration Files: Contain system variables and sensitive paths
.env
.env.*
*/config/production.*
config/*.secure.yaml
config/*.secret.json
**/application-*.yml
**/cluster-config/*

# Identity & Authentication Material: Avoid agent access to cryptographic trust stores
**/certs/**
**/keystore.*
**/truststore.*

# Government‑specific sensitive artifacts: Depending on classification boundaries
**/FOUO/**
**/CUI/**
**/ITAR/**
**/NOFORN/**
**/export-controlled/**

# Infrastructure as Code Privacy Controls: To prevent revealing cloud architecture secrets
**/terraform.tfstate
**/terraform.tfvars
**/*credentials*
**/aws-config/**
**/*.kube/config

# Logs, Audit Files, and System Metadata: May leak operational details
**/*.log
**/audit/**
**/sysinfo/**
**/.git/**

# Build Artifacts & Third‑Party Code: Unnecessary and may include embedded secrets
**/node_modules/**
**/dist/**
**/build/**
```

**Amazon Kiro Data Residency in the UK**

Amazon Kiro does not currently store data in a UK-based AWS Region. Kiro’s supported data‑storage regions are documented under “Supported Regions” according to the official Kiro documentation. This complies with EU/EEA data residency requirements but not strict UK‑sovereign residency.

The supported regions are:
- US East (N. Virginia)
- Europe (Frankfurt)

**Intellectual Property for Amazon Kiro**

Amazon Kiro’s IP framework is governed by AWS licensing terms, which define ownership, usage rights, and IP protections for both Amazon and the user.

According to the official Kiro license:
- Kiro IDE and Kiro CLI are owned by Amazon and are licensed as AWS content under AWS IP license
- you retain ownership of your own code, data, prompts, and project files
- you own the output generated by Kiro
- Kiro uses open‑source libraries under their own licenses
- Amazon maintains a robust IP protection framework that extends to AWS services

# Getting started

Amazon Kiro is not a standalone CLI or package you install like Terraform or Docker. It is an AI-powered development environment / IDE experience that integrates with AWS services and is accessed through supported IDEs and AWS authentication. So the installation is environment setup + access enablement + IDE configuration.

Below is the complete, step‑by‑step Amazon Kiro installation guide.

Step 1: System Requirements
- supported OS: Windows 10/11 (64‑bit), macOS (Intel & Apple Silicon), Linux (Ubuntu 18.04+, Fedora 32+, or similar)
- memory: Minimum 4GB RAM (8GB+ recommended)
- storage: ~500MB free space
- internet: Required for AI features (Bedrock inference, updates)
- some advanced workflows require Node.js 20+ (optional but recommended for dev tasks)

Step 2: AWS Account
- you need an active AWS account
- permissions to use Amazon Bedrock, create IAM roles/policies and access developer tools

Note: In enterprises/government, this usually means going through your cloud/platform team.

Step 3: Amazon Kiro
- download the installer for: Windows, macOS (Intel/ARM), Linux (Deb/Ubuntu or universal)

Step 4: Supported Operating System
- macOS
- linux
- windows

Step 5: Supported IDE, Kiro is designed to work inside modern IDE workflows
- VS Code (primary)
- jetBrains IDEs (depending on rollout)

Step 6: Kiro runs on Amazon Bedrock, this is mandatory
- enable Bedrock for your account (first-time only)
- request access to required models, Anthropic Claude Sonnet family
- without Bedrock enabled, Kiro will not function
- create or use an IAM role/user with least privilege
- read/write access to code repositories (locally)

Step 7: Configure AWS Credentials Locally
- aws configure
- or use AWS SSO, Environment variables, Credential profiles and Verify: aws sts get-caller-identity

Step 8: Install the Amazon Kiro IDE Extension
- in VS Code, search for Amazon Kiro and install the extension
- restart VS Code and Kiro panel / sidebar appears
- open a project repository and verify

Step 9: Common Installation Issues (and Fixes)
- "Model access denied": Bedrock not enabled or model access not approved
- "AWS credentials not found": Fix aws configure or SSO login
- "Kiro can’t see my files": Open the project folder correctly in VS Code

# Training requirements
These are mandatory foundational requirements before a user can begin using Kiro effectively.

Module 1: Environment Preparation Training (60 minutes)
- AWS account + access setup
- Kiro IDE or Kiro CLI installation
- optional DevOps / advanced setup

Module 2: Core Skills Training (90 minutes)
- understanding Kiro’s core workflow – specs, hooks, steering
- hands‑on first project

Module 3: Feature‑Focused Learning Tracks (120 minutes, flexible)
- beginner track – foundations
- intermediate track – specs, hooks, context
- advanced track – production workflows

### Total Training Time Estimate
| Level | Time Required | Who Needs It |
|-------|---------------|--------------|
| Basic / Getting Started | 1–2 hours | Individual developers | 
| Core Kiro Workflow | 1.5–3 hours | All users | 
| Intermediate Features | 1.5–2 hours | Regular users | 
| Advanced (Production) | 1.5–2 hours | Senior devs, DevOps |
| Enterprise Admin | 1–1.5 hours | Team leads, cloud admins |

# Measuring success
Measuring success in Kiro is based on three primary dimensions
- usage & activity metrics (quantitative tracking)
- developer productivity & workflow outcomes
- quality, automation, and DevOps improvements

### Using Kiro’s Built‑In User Activity Metrics
- daily user activity, per individual
- detailed usage metrics for each developer
- frequency of Kiro interactions
- metrics generated automatically every day at 00:00 UTC
- Kiro outputs daily CSV analytics to an S3 bucket (s3://bucketName/prefix/AWSLogs/accountId/KiroLogs/)
- this helps measure success by measuring adoption rate, feature usage distribution, user productivity patterns over time and team‑level gaps

### Productivity & Delivery Metrics
| Metric | What to Measure |
|--------|-----------------|
| Lead time for changes | Time from code start → production |
| Cycle time | Time per feature or story |
| PR turnaround time | Time to review and merge |
| Deployment frequency | How often code ships |

### Code Quality & Maintainability
| Metric | Why It Matters |
|--------|----------------|
| Unit test coverage | Kiro often generates tests |
| Test failure rate	| Quality of generated code |
| Lint / static analysis issues	| Consistency |
| Defect rate post-release | Real quality signal |

### Security & Compliance Metrics
| Metric | Measurement |
|--------|-------------|
| Security findings per PR | Static/IaC scans |
| Secrets leaked | Must be zero |
| Policy violations | Coding or infra standards |
| DPIA / audit findings	| Governance health |

### Documentation and Knowledge Quality Metrics
| Metric | Indicator |
|--------|-----------|
| README completeness | Up-to-date docs |
| API documentation coverage | Accuracy |
| Onboarding time | New dev ramp-up |
| Tribal knowledge reduction | Fewer ad-hoc explanations |

Success with Amazon Kiro is measured across productivity, code quality, security, governance, and developer experience. Key indicators include reduced delivery time, improved test coverage and documentation, stable or improved security outcomes, effective human oversight, and positive developer feedback, not just faster code generation.

# Common troubleshooting scenarios
- #### Authentication / Access issues
    Symptoms: 
    - can’t sign in, not authorized, feature disabled

    Solutions:
    - check correct AWS account & region
    - IAM role has required permissions
    - session hasn’t expired (SSO timeouts are common)

- #### Tool not responding or timing out
    Symptoms: 
    - Prompts hang, no output, slow responses
    
    Solutions:
    - network/proxy/firewall blocking outbound calls
    - corporate VPN interfering
    - retry in a different region or workspace

- #### Code generation errors
    Symptoms: 
    - incomplete code, hallucinated APIs, wrong language
    
    Solutions:
    - prompt too vague or missing constraints
    - project context not loaded or indexed
    - unsupported framework or SDK version

- #### IDE integration problems
    Symptoms: 
    - plugin not loading, commands missing
    
    Solutions:
    - plugin version matches IDE version
    - restart IDE after install/update
    - clear local cache / reinstall extension

- #### Permissions to modify repositories
    Symptoms: 
    - read-only behavior, failed commits
    
    Solutions:
    - repo access (GitHub / CodeCommit / Bitbucket)
    - local Git credentials vs AWS credentials mismatch

- #### SSL Error: unable to get local issuer certificate
    Symptoms:
    - missing or broken OS trust certificates
    
    Solutions:
    - run: curl https://baidu.com

- #### Session Timeouts (Enterprise Users): Forced logout after ~8 hours
    Symptoms: 
    - identity center default timeout

    Solutions:
    - admin can increase session duration in IAM identity center settings

- #### MCP / CLI Integration Issues
    Symptoms: 
    - MCP server not connecting

    Solutions:
    - install missing dependencies
    - re-run Kiro CLI setup

# Policy configuration reference

- identity‑based policies for Amazon Kiro (IAM policies): AWS Kiro relies heavily on IAM for authorization and requires explicit IAM permissions in managing Kiro subscriptions, accessing console, managing KMS keys and controlling user/agent permissions.
- service‑linked roles for Kiro: Key properties
    - are created automatically when you subscribe to Kiro
    - are predefined trust and permission policies
    - only Kiro can assume these roles
    - cannot be manually attached or modified
    - must be deleted only after deleting related Kiro resources

- Kiro project-level configuration policies (.kiro/directory): Stored inside the project, runtime policies
    - steering policies (.kiro/steering/*.md)
    - permissions and execution policies (.kiro/permissions.json)
    - MCP policies (.kiro/settings/mcp.json): Essential for compliance‑sensitive or restricted environments.
      
      MCP (Model Context Protocol) defines tool execution permissions.
      
      A typical MCP configuration looks like:
      ```yaml
      {
      "mcpServers": {
        "server-name": {
          "command": "uvx",
          "args": ["package@latest"],
          "env": { "ENV_VAR": "value" },
          "disabled": false,
          "autoApprove": ["tool1", "tool2"], 
          "timeout": 60000
         }
       }
      }
- automation and execution control policies: operational policy configuration.
    - autopilot mode: Kiro executes multi‑step actions automatically, creates/modifies/deletes files and runs shell commands without asking.
    - supervised mode: Requires user approval for each action and prevents unauthorized changes.

- data protection and security policies
    - shared responsibility model
    - URL fetching security policy
    - enterprise data residency and IAM identity center

- real‑time security validation policies (using MCP servers): Run automatically while coding using MCP
    - checkov (IaC scanning)
    - semgrep (application code scanning)
    - bandit (Python security scanning)

### Kiro Policy Types
| Policy Type | Location | Purpose | Source |
| ------------| ---------| -------| -------|
| IAM Identity-Based |IAM console | Admin/user permissions for Kiro console & subscription management | [kiro.dev] |
| Service-Linked Roles | IAM | Allows Kiro backend to call AWS services securely | [kiro.dev] | 
| Steering Policies | .kiro/steering/ | Coding standards, rules, conventions | [kiro.directory] |
| MCP Policies | .kiro/settings/mcp.json | Tool permissions, auto-approvals, server connections | [github.com] |
| Runtime Modes | User settings | Execution safety (autopilot vs supervised) | [kiro.dev] |
| Data‑Protection Policies | AWS account/Kiro console | Data location, URL ingestion, compliance alignment | [kiro.dev] | 
| Security Validation Policies | MCP server configs | Static analysis, IaC scanning, vulnerability checking |  [docs.aws.amazon.com] | 

# Integration with development workflow
 
- Kiro as an agentic IDE integrated into the Dev workflow
- specs integrate into the workflow (Planning → Execution → Review)
```
Developer Prompt → Spec Generation → Task List → Code Generation → Tests → Documentation
```
- agent hooks event‑driven workflow automation
- steering integration project standards as Policy
```
Steering Files → AI Behavior → Code Consistency Across the Project
```
- MCP servers integration with external tools in the workflow
```
Kiro → MCP → External Tool → Result Returned into IDE
```
- agentic chat conversational development integrated into the workflow
- CLI integration terminal and DevOps workflow automation
```
CI/CD → Kiro CLI → Generate IaC → Validate → Deploy
```
### Kiro Integrates Into Dev Workflows
| Workflow Area | How Kiro Integrates | Sources | 
| --------------| --------------------| --------|
| Planning | Specs (requirements → tasks) | [github.com] | 
| Active Development | Agent chat + code generation|  [geeky-gadgets.com] |
| Automation | Agent Hooks triggered by dev events | [kiro.dev] |
| Project Rules | Steering controlling AI behavior | [github.com] | 
| Tooling | MCP Servers (GitHub, AWS, Docker, security) | [kiro.dev], [d1.awsstatic.com] |
| DevOps | CLI automates deployments & IaC | [aws.amazon.com] |

# Related resources

Links to official Amazon Kiro resources:

- [[Kiro Quick Start Guide - Get Started in 10 Minutes | Kiro Directory](https://kiro.directory/quickstart/)
- https://commonslibrary.parliament.uk/research-briefings/cbp-10003/
- https://www.lawgazette.co.uk/practice-points/ai-regulation-what-uk-businesses-need-to-know/5123086.article
- https://www.gov.uk/government/publications/ai-playbook-for-the-uk-government/artificial-intelligence-playbook-for-the-uk-government-html
- https://kiro.dev/docs/enterprise/supported-regions/
- https://kiro.dev/docs/privacy-and-security/
- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [TechUK Software Reseller Framework](https://www.techuk.org/) - alternative procurement route

### NCSC guidance

Links to NCSC guidance:

- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - handling security issues

### Repository resources

Links to repository resources:

- [AI SDLC Playbook](../../playbooks/ai-sdlc-playbook.md) - integrating AI code assistants across development lifecycle
- [Model Selection Playbook](../../playbooks/model-selection.md) - choosing appropriate models for tasks

## Providing feedback

We welcome feedback to improve these materials. You can:

- raise an issue in the issue tracker (location to be confirmed)
- submit improvements via pull request (see [CONTRIBUTING.md](../../CONTRIBUTING.md))
- contact the team at the team email address (to be confirmed)
- use the feedback mechanism in your department's AI Engineering Lab community

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government to keep this repository current and comprehensive. Share your team's experience, lessons learned, and effective practices to help other government departments.

Before contributing, read [CONTRIBUTING.md](../../CONTRIBUTING.md) which covers:

- content standards and style guide
- review and approval process
- accessibility requirements
- how to submit changes

## Licence

This repository is published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

You are encouraged to use and adapt these materials for your own government context.

When reusing content:

- maintain attribution to this repository
- share improvements back via contribution
- ensure adaptations remain suitable for government use
