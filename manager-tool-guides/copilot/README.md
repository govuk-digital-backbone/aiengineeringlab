> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# GitHub Copilot - Manager Tool Guide

## Audience

Engineering managers, technical leads, and delivery managers responsible for AICA adoption in their teams.

## Purpose

This guide provides engineering managers with practical guidance for implementing GitHub Copilot within UK government departments. It covers capabilities assessment, security considerations, phased rollout strategies, and success measurement to support informed decision-making and sustainable adoption.

## What's in this guide

This guide is organised into the following sections:

**Understanding GitHub Copilot**
- [What GitHub Copilot does](#what-github-copilot-does) - Core capabilities and interaction modes
- [How it compares with other AICAs](#how-it-compares-with-other-aicas) - Feature comparison and when to use different tools
- [Copilot models and task suitability](#copilot-models-and-task-suitability) - Choosing the right model for different tasks

**Implementation planning**
- [Government-specific considerations](#government-specific-considerations) - Security classifications, data residency, and procurement
- [Getting started](#getting-started) - Licensing options and installation process
- [Training requirements](#training-requirements) - Engineer and manager training programmes

**Managing adoption**
- [Measuring success](#measuring-success) - Quality metrics and troubleshooting
- [Policy configuration reference](#policy-configuration-reference) - Content exclusions and IDE settings

**Additional resources**
- [Related resources](#related-resources) - Links to official documentation, government guidance, and repository materials
- [Contributing](#contributing) - How to improve this guide
- [Support and contact](#support-and-contact) - Getting help

## Prerequisites

Before reading this guide, you should understand:

- Your team's current development workflow and tooling
- Basic software development lifecycle concepts
- Your department's security classification requirements
- The [AI Engineering Lab maturity assessment](../assessment/README.md) framework

## What GitHub Copilot does

GitHub Copilot provides real-time code suggestions directly in your team's development environment. It generates code completions, entire functions, tests, and documentation based on context from the current file.

**Primary capabilities:**

- Autocomplete code as engineers type
- Generate implementation from function signatures or comments
- Create unit tests based on existing code
- Produce documentation and code explanations
- Suggest fixes for errors and warnings

**Copilot interaction modes:**

GitHub Copilot offers several ways to interact with AI assistance, each suited for different tasks:

| Mode | Description | Best for | Available in |
|------|-------------|----------|--------------|
| **Inline suggestions** | Real-time completions as you type | Quick code completion, boilerplate | All tiers |
| **Copilot Chat** | Conversational interface in IDE | Explanations, debugging, questions | All tiers |
| **Copilot Edits** | Multi-file editing with AI assistance | Refactoring across files, applying patterns | Business/Enterprise |
| **Copilot Workspace** | Plan and implement features from issues | Feature planning, task breakdown | Enterprise only |
| **Agent mode** | Autonomous task execution with approval | Complex multi-step tasks, investigations | Enterprise only |

**When to use each mode:**

- **Inline suggestions**: Daily coding, implementing known patterns, writing tests
- **Chat**: Understanding unfamiliar code, debugging errors, generating documentation
- **Edits**: Renaming variables across files, applying security fixes, refactoring
- **Workspace**: Planning new features, breaking down epics, designing implementations
- **Agent mode**: Investigating bugs across codebase, migrating frameworks, comprehensive refactoring

**Best suited for:**

- Teams seeking productivity gains in routine coding tasks
- Projects with substantial boilerplate or repetitive patterns
- Accelerating test coverage creation
- Supporting less experienced engineers with examples

**Not designed for:**

- Complex architectural decisions requiring codebase-wide understanding
- Security-critical code generation without thorough review
- Replacing code review and quality assurance processes
- Full-stack application generation from requirements

## How it compares with other AICAs

For a detailed comparison of GitHub Copilot with other AI code assistants, see the [comparative guidance](../comparative-guidance.md).

**When to combine with other tools:**

- Use Claude Code for complex refactoring or architectural questions
- Use Claude with GitHub MCP server for AI-assisted code reviews, pull request analysis, and issue management
- Use Amazon Q for AWS-specific deployment tasks
- Use government MCP servers with Claude for standards compliance checking

### MCP servers and extended workflows

For detailed guidance on MCP servers and integration with other AI code assistants, see the MCP servers documentation in the repository.

## Copilot models and task suitability

GitHub Copilot uses different models depending on the task. Understanding which model suits which task helps set appropriate expectations.

### Model comparison

| Model | Provider | Best for | Cost | Notes |
|---|---|---|---|---|
| GPT-4.1 | OpenAI | General coding, fast completions | Included | No premium requests on paid plans |
| GPT-5 mini | OpenAI | Balanced speed and capability | Included | No premium requests on paid plans |
| GPT-5 | OpenAI | Complex code generation, debugging | 1x | Strong general-purpose model |
| GPT-5.1 | OpenAI | Latest OpenAI capabilities | 1x | Enhanced reasoning |
| GPT-5.2 | OpenAI | Most advanced OpenAI model | 1x | Best for complex tasks |
| Claude Haiku 4.5 | Anthropic | Fast responses, simple tasks | 0.33x | Cost-effective option |
| Claude Sonnet 4 | Anthropic | Balanced reasoning and speed | 1x | Good all-rounder |
| Claude Sonnet 4.5 | Anthropic | Advanced coding tasks | 1x | Strong code understanding |
| Claude Opus 4.1 | Anthropic | Deep reasoning, complex refactoring | 10x | Best for architectural decisions |
| Claude Opus 4.5 | Anthropic | Most advanced Claude model | 3x | Superior reasoning capabilities |
| Gemini 2.5 Pro | Google | Multimodal tasks, large context | 1x | Good for visual and code tasks |
| Grok Code Fast 1 | xAI | Fast code generation | 0.25x | Currently complimentary |
| Raptor mini | Fine-tuned GPT-5 mini | Optimised completions | Included | Preview - tuned for coding |

### Recommended models by task

| Task | Recommended model | Why |
|---|---|---|
| Autocomplete as you type | GPT-4.1 or Raptor mini (default) | Fast response, no premium cost |
| Generate unit tests | GPT-5 or Claude Sonnet 4.5 | Better understanding of edge cases |
| Debug complex issues | Claude Opus 4.5 or GPT-5.2 | Superior reasoning about code behaviour |
| Write boilerplate code | GPT-5 mini or Claude Haiku 4.5 | Sufficient for repetitive patterns, cost-effective |
| Refactor legacy code | Claude Opus 4.1 or GPT-5.1 | Needs deep understanding of code structure |
| Implement algorithms | GPT-5.2 | Optimised for mathematical reasoning |
| Generate documentation | GPT-5 or Claude Sonnet 4 | Strong natural language generation |
| SQL query generation | GPT-5.1 | Better syntax accuracy and optimisation |
| Security code review | Claude Sonnet 4.5 | Strong pattern recognition for vulnerabilities |
| API client generation | GPT-5 mini | Template-based, doesn't need premium model |
| Multimodal tasks (images + code) | Gemini 2.5 Pro | Best multimodal support |

### Controlling model selection

In Copilot Chat, you can select models from the model picker dropdown. When using **Auto** mode, Copilot automatically selects the best model based on your task and current availability.

**Included models** (no premium requests on paid plans):
- GPT-4.1
- GPT-5 mini
- Raptor mini

**Premium models** (consume premium requests):
- All Claude models (Haiku, Sonnet, Opus variants)
- GPT-5, GPT-5.1, GPT-5.2
- Gemini models
- Grok Code Fast 1 (currently complimentary)

**Note**: Model availability depends on your license tier. Business and Enterprise tiers have access to all models. Premium model usage counts towards your organisation's monthly allowance.

### Adding additional models

You can add more models beyond those available by default using your own API keys. This allows access to:
- Additional model versions
- Models from other providers
- Local or self-hosted models

For configuration details, see [Changing the AI model for GitHub Copilot Chat](https://docs.github.com/en/copilot/how-tos/use-ai-models/change-the-chat-model).

For detailed model capabilities and limitations, see:
- [GitHub Copilot supported models](https://docs.github.com/en/copilot/reference/ai-models/supported-models)
- [AI model comparison](https://docs.github.com/en/copilot/reference/ai-models/model-comparison)

## Government-specific considerations

### Security classification

GitHub Copilot sends code snippets to GitHub's servers for processing. This means:

- **OFFICIAL**: Generally acceptable with appropriate content exclusions configured
- **OFFICIAL-SENSITIVE**: Requires risk assessment and strict content exclusions
- **SECRET and above**: Not appropriate for these classifications

Consult your departmental security team before deployment. Reference [NCSC guidance on cloud services](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) for risk assessment.

### Content exclusions

You must configure Copilot to exclude sensitive files and patterns. Recommended exclusions for government projects:

```yaml
# Environment and configuration files
**/.env
**/.env.*
**/secrets/**
**/config/production.yml
**/config/production/**

# AWS and API credentials
**/credentials
**/aws/config
**/.aws/**
**/api-keys/**

# Department-specific patterns
**/citizen-data/**
**/personal-identifiable-information/**
**/security-configurations/**
```

### Data residency

As of January 2025, GitHub Copilot processes requests through Azure OpenAI Service. Check your department's data residency requirements before deployment.

### Intellectual property

Copilot Business and Enterprise tiers include IP indemnity, meaning GitHub provides legal protection if generated code infringes copyright. Individual tier does not include this protection.

For government projects, use Business or Enterprise tier only.

## Getting started

### Installation process

**Step 1: Organisation setup**

1. Enable Copilot in your GitHub organisation settings
2. Configure content exclusion policies
3. Assign licenses to pilot users
4. Enable usage metrics collection

**Step 2: Engineer installation**

For VS Code:
```bash
# Install extensions
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
```

For JetBrains IDEs:
- Settings → Plugins → Search "GitHub Copilot" → Install

**Step 3: Authentication**

Engineers authenticate using their GitHub accounts. If using Enterprise Managed Users, configure SAML single sign-on through your identity provider.

**Step 4: Verification**

Test installation by opening a code file. Copilot should show inline suggestions as you type. If not, check authentication status in the extension settings.


## Training requirements

### Engineer training (45 minutes)

**Module 1: Basic usage** (15 minutes)
- Accepting and rejecting suggestions
- Keyboard shortcuts
- Enabling/disabling for specific file types
- When to trust suggestions vs. manual coding

**Module 2: Effective prompting** (15 minutes)
- Writing comments that generate good code
- Using function names and signatures strategically
- Providing context through imports and surrounding code
- Common patterns that work well

**Module 3: Security and quality** (15 minutes)
- Reviewing generated code critically
- Recognising and rejecting insecure patterns
- Content exclusions and when they apply
- Integration with code review process

**Format**: Live demonstration with hands-on practice using real project examples.

### Manager briefing (30 minutes)

**Topics:**
- Capability overview and realistic expectations
- Usage metrics and how to interpret them
- Policy configuration and content exclusions
- Addressing team concerns about AI tools
- Return on investment calculation

**Format**: Presentation with Q&A session.

## Measuring success

### Quality metrics

For quality metrics please refer to the monitoring and evaluation framework documentation.

### Common troubleshooting scenarios

#### Inline suggestions not appearing

**Symptoms:**
- No autocomplete suggestions while typing
- Extension appears inactive

**Solutions:**
1. Verify extension is enabled and authenticated in IDE settings
2. Check that file type is not excluded in Copilot settings
3. Ensure inline suggestions are enabled: `"editor.inlineSuggest.enabled": true`
4. Restart IDE and check network connectivity
5. Sign out and sign back in to refresh authentication

#### Copilot Chat not responding

**Symptoms:**
- Chat window opens but no responses
- Error messages in chat interface

**Solutions:**
1. Check GitHub service status at [githubstatus.com](https://www.githubstatus.com/)
2. Verify license is active in GitHub organisation settings
3. Clear chat history and restart conversation
4. Check corporate proxy/firewall allows Copilot endpoints
5. Update to latest extension version

#### Agent mode failures

**Symptoms:**
- Agent tasks fail to complete
- Timeout errors or incomplete work

**Solutions:**
1. Break down complex tasks into smaller, more specific requests
2. Ensure agent has sufficient permissions for requested operations
3. Check repository size and complexity (very large repos may struggle)
4. Review task requirements - agent works best with clear, bounded objectives
5. Monitor agent progress and provide clarifications when requested

For detailed troubleshooting of Copilot agent mode specifically, see [Troubleshooting GitHub Copilot coding agent](https://docs.github.com/en/copilot/using-github-copilot/using-github-copilot-coding-agent-in-your-ide/troubleshooting-github-copilot-coding-agent).

#### Poor suggestion quality

**Symptoms:**
- Suggestions don't match project patterns
- Irrelevant or incorrect code generated

**Solutions:**
1. Provide more context via descriptive comments and function signatures
2. Ensure relevant imports and dependencies are visible in file
3. Use more specific variable and function names
4. Check if content exclusions are blocking helpful context
5. Try using Copilot Chat for complex scenarios instead of inline
6. For Enterprise customers: verify custom model fine-tuning is configured

**Effective prompting:**

Understanding how to communicate with Copilot effectively can dramatically improve suggestion quality. See the [prompt library](../../prompt-library/README.md) for tested prompts and patterns.


#### Performance issues

**Symptoms:**
- Slow suggestion generation
- IDE lagging when Copilot active

**Solutions:**
1. Reduce number of active IDE extensions
2. Check network connectivity and latency
3. Clear extension cache and reload IDE
4. Update to latest Copilot extension version
5. Check system resources (CPU, memory)

#### Enterprise-specific issues

**Symptoms:**
- License assignment not working
- Policy changes not taking effect
- Usage metrics not appearing

**Solutions:**
1. Verify user is member of correct GitHub organisation
2. Check seat assignment in organisation Copilot settings
3. Allow 15-30 minutes for policy changes to propagate
4. Ensure user has signed out and back in after policy updates
5. Contact GitHub support for billing or access issues

### Security incidents

If a engineer discovers or accepts code containing:
- Hardcoded secrets or credentials
- Known security vulnerabilities
- Data protection violations

**Immediate actions:**
1. Do not commit the code
2. Report to your security team using standard incident process
3. Document the suggestion for analysis
4. Update content exclusions if pattern-based

**Follow-up:**
- Review similar code in recent commits
- Update team training materials
- Share learning without blame

## Policy configuration reference

### Recommended content exclusions

```yaml
# Secrets and credentials
**/.env
**/.env.*
**/secrets/**
**/*.key
**/*.pem
**/credentials
**/.aws/**

# Configuration files
**/config/production.yml
**/config/production/**
**/terraform/production/**

# Citizen data
**/citizen-data/**
**/personal-identifiable-information/**
**/user-data/**

# Security configurations
**/security-configurations/**
**/auth-config/**
**/firewall-rules/**

# Legacy code (if applicable)
**/legacy/**
**/deprecated/**
```

### IDE-level settings

Example VS Code configuration:

```json
{
  "github.copilot.enable": {
    "*": true,
    "yaml": false,
    "plaintext": false,
    "markdown": true
  },
  "github.copilot.editor.enableAutoCompletions": true,
  "editor.inlineSuggest.enabled": true,
  "github.copilot.advanced": {
    "debug.overrideEngine": "default",
    "debug.testOverrideProxyUrl": "",
    "debug.overrideProxyUrl": ""
  }
}
```

Disable Copilot for specific file types where suggestions aren't helpful or may be risky.

### Organisation-level settings

Configure in GitHub organisation settings:

1. Navigate to Settings → Copilot
2. Enable Copilot for organisation
3. Configure suggestion matching (block suggestions matching public code if required)
4. Set content exclusion repository
5. Enable telemetry collection for usage insights

## Related resources

### Official GitHub resources

- [GitHub Copilot documentation](https://docs.github.com/en/copilot) - Complete official documentation
- [Copilot model comparison](https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide#ai-models-for-copilot-chat) - Detailed model capabilities and selection
- [Copilot Trust Center](https://resources.github.com/copilot-trust-center/) - Security, privacy, and compliance information
- [Getting started with Copilot](https://docs.github.com/en/copilot/getting-started-with-github-copilot) - Initial setup guides
- [Copilot best practices](https://github.blog/ai-and-ml/github-copilot/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/) - Tips and effective usage patterns

### Enterprise and security

- [Managing Copilot in your organisation](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization) - Policy configuration and administration
- [Copilot content exclusions](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/setting-policies-for-copilot-in-your-organization/excluding-content-from-github-copilot) - Configuring what Copilot can access
- [Copilot for Business vs Enterprise](https://docs.github.com/en/copilot/overview-of-github-copilot/github-copilot-features#github-copilot-business-and-github-copilot-enterprise) - Feature comparison
- [Usage metrics and reporting](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/reviewing-usage-data-for-github-copilot-in-your-organization) - Measuring adoption and impact

### Government procurement

- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [GitHub on G-Cloud](https://www.digitalmarketplace.service.gov.uk/) - Search for GitHub Enterprise and Copilot offerings
- [TechUK Software Reseller Framework](https://www.techuk.org/) - Alternative procurement route

### NCSC guidance

- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - Assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - Security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - Handling security issues

### Repository resources

- [AI SDLC Playbook](../../playbooks/ai-sdlc-playbook.md) - Integrating AICAs across development lifecycle
- [Model Selection Playbook](../../playbooks/model-selection.md) - Choosing appropriate models for tasks

### Providing feedback

We welcome feedback to improve these materials. You can:

- Raise an issue in [PLACEHOLDER: issue tracker location]
- Submit improvements via pull request (see [CONTRIBUTING.md](../../CONTRIBUTING.md))
- Contact the team at [PLACEHOLDER: team email address]
- Use the feedback mechanism in your department's AI Engineering Lab community

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines. 

We encourage contributions from across government to keep this repository current and comprehensive. Share your team's experience, lessons learned, and effective practices to help other government departments.

Before contributing, please read [CONTRIBUTING.md](../../CONTRIBUTING.md) which covers:

- Content standards and style guide
- Review and approval process
- Accessibility requirements
- How to submit changes

## Support and contact

| Need | Contact |
|------|---------|
| General enquiries | [PLACEHOLDER: team email] |
| FDE support requests | [PLACEHOLDER: FDE request process] |
| Urgent issues | [PLACEHOLDER: escalation contact] |
| Content feedback | [PLACEHOLDER: feedback mechanism] |

[PLACEHOLDER: Add relevant Slack/Teams channels if available]

## Licence

This repository is published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

You are encouraged to use and adapt these materials for your own government context.

When reusing content, please:

- Maintain attribution to this repository
- Share improvements back via contribution
- Ensure adaptations remain suitable for government use
