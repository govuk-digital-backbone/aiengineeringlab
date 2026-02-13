> **ALPHA**
> This is a new service. Your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# GitHub Copilot manager tool guide

## Purpose

This guide provides engineering managers with practical guidance for implementing GitHub Copilot within UK government departments. It covers capabilities assessment, security considerations, phased rollout strategies, and success measurement to support informed decision-making and sustainable adoption.

## Audience

This guide is for:

- engineering managers responsible for AI Engineering Lab adoption in their teams
- technical leads overseeing tool implementation and developer workflows
- delivery managers coordinating rollout and measuring adoption success

## What is in this guide

This guide is organised into the following sections.

1. Understanding GitHub Copilot

- [what GitHub Copilot does](#what-github-copilot-does) - core capabilities and interaction modes
- [how it compares with other AI code assistants](#how-it-compares-with-other-ai-code-assistants) - feature comparison and when to use different tools
- [Copilot models and task suitability](#copilot-models-and-task-suitability) - choosing the right model for different tasks

2. Implementation planning

- [government-specific considerations](#government-specific-considerations) - security classifications, data residency, and procurement
- [safe usage guidance: prototyping vs production](../../user-tool-guides/github-copilot/safe-usage-prototyping-vs-production.md) - differentiated controls for different environments
- [getting started](#getting-started) - licensing options and installation process
- [training requirements](#training-requirements) - engineer and manager training programmes

3. Managing adoption

- [measuring success](#measuring-success) - quality metrics and troubleshooting
- [policy configuration reference](#policy-configuration-reference) - content exclusions and IDE settings

4. Additional resources

- [related resources](#related-resources) - links to official documentation, government guidance, and repository materials
- [contributing](#contributing) - how to improve this guide

## Before you start

Before reading this guide, you should understand:

- your team's current development workflow and tooling
- basic software development lifecycle concepts
- your department's security classification requirements
- the [AI Engineering Lab maturity assessment](../../assessment/maturity-assessment-framework.md) framework

## What GitHub Copilot does

GitHub Copilot provides real-time code suggestions directly in your team's development environment. It generates code completions, entire functions, tests, and documentation based on context from the current file.

Primary capabilities include:

- autocompleting code as engineers type
- generating implementation from function signatures or comments
- creating unit tests based on existing code
- producing documentation and code explanations
- suggesting fixes for errors and warnings

### Copilot interaction modes

GitHub Copilot offers several ways to interact with AI assistance, each suited for different tasks:

| Mode | Description | Best for | Available in |
|------|-------------|----------|--------------|
| Inline suggestions | Real-time completions as you type | Quick code completion, boilerplate | All tiers |
| Copilot Chat | Conversational interface in IDE | Explanations, debugging, questions | All tiers |
| Copilot Edits | Multi-file editing with AI assistance | Refactoring across files, applying patterns | Business and Enterprise |
| Copilot Workspace | Plan and implement features from issues | Feature planning, task breakdown | Enterprise only |
| Agent mode | Autonomous task execution with approval | Complex multi-step tasks, investigations | Enterprise only |

Each mode is suited to specific tasks, including:

- inline suggestions for daily coding, implementing known patterns, and writing tests
- chat for understanding unfamiliar code, debugging errors, and generating documentation
- edits for renaming variables across files, applying security fixes, and refactoring
- workspace for planning new features, breaking down epics, and designing implementations
- agent mode for investigating bugs across codebase, migrating frameworks, and comprehensive refactoring

### Best suited for

GitHub Copilot is best suited for:

- teams seeking productivity gains in routine coding tasks
- projects with substantial boilerplate or repetitive patterns
- accelerating test coverage creation
- supporting less experienced engineers with examples

### Not designed for

GitHub Copilot is not designed for:

- complex architectural decisions requiring codebase-wide understanding
- security-critical code generation without thorough review
- replacing code review and quality assurance processes
- full-stack application generation from requirements

## How it compares with other AI code assistants

For a detailed comparison of GitHub Copilot with other AI code assistants, see the [comparative guidance](../comparative-guidance.md).

### When to combine with other tools

Consider combining GitHub Copilot with other tools when:

- you need Claude Code for complex refactoring or architectural questions
- you need Claude with GitHub MCP server for AI-assisted code reviews, pull request analysis, and issue management
- you need Amazon Q for AWS-specific deployment tasks
- you need government MCP servers with Claude for standards compliance checking

### MCP servers and extended workflows

For detailed guidance on MCP servers and integration with other AI code assistants, see the MCP servers documentation in the AI Engineering Lab repository.

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
| API client generation | GPT-5 mini | Template-based, does not need premium model |
| Multimodal tasks (images and code) | Gemini 2.5 Pro | Best multimodal support |

### Controlling model selection

In Copilot Chat, you can select models from the model picker dropdown. When using Auto mode, Copilot automatically selects the best model based on your task and current availability.

Included models (no premium requests on paid plans) are:

- GPT-4.1
- GPT-5 mini
- Raptor mini

Premium models (consume premium requests) are:

- all Claude models (Haiku, Sonnet, Opus variants)
- GPT-5, GPT-5.1, GPT-5.2
- Gemini models
- Grok Code Fast 1 (currently complimentary)

Model availability depends on your license tier. Business and Enterprise tiers have access to all models. Premium model usage counts towards your organisation's monthly allowance.

### Adding additional models

You can add more models beyond those available by default using your own API keys. This allows access to:

- additional model versions
- models from other providers
- local or self-hosted models

For configuration details, see [Changing the AI model for GitHub Copilot Chat](https://docs.github.com/en/copilot/how-tos/use-ai-models/change-the-chat-model).

For detailed model capabilities and limitations, see:

- [GitHub Copilot supported models](https://docs.github.com/en/copilot/reference/ai-models/supported-models)
- [AI model comparison](https://docs.github.com/en/copilot/reference/ai-models/model-comparison)

## Government-specific considerations

### Security classification

GitHub Copilot sends code snippets to GitHub's servers for processing. This means:

- OFFICIAL: generally acceptable with appropriate content exclusions configured
- OFFICIAL-SENSITIVE: requires risk assessment and strict content exclusions
- SECRET and above: not appropriate for these classifications

Consult your departmental security team before deployment. Reference [NCSC guidance on cloud services](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) for risk assessment.

### Content exclusions

You must configure Copilot to exclude sensitive files and patterns. Recommended exclusions for government projects:

```yaml
# Environment and configuration files
/.env
/.env.
/secrets/
/config/production.yml
/config/production/

# AWS and API credentials
/credentials
/aws/config
/.aws/
/api-keys/

# Department-specific patterns
/citizen-data/
/personal-identifiable-information/
/security-configurations/
```

### Data residency

As of January 2025, GitHub Copilot processes requests through Azure OpenAI Service. Check your department's data residency requirements before deployment.

### Intellectual property

Copilot Business and Enterprise tiers include IP indemnity, meaning GitHub provides legal protection if generated code infringes copyright. Individual tier does not include this protection.

For government projects, use Business or Enterprise tier only.

## Getting started

### Installation process

To get started with GitHub Copilot, complete the following steps.

#### Step 1: organisation setup

1. Enable Copilot in your GitHub organisation settings.
2. Configure content exclusion policies.
3. Assign licenses to pilot users.
4. Enable usage metrics collection.

#### Step 2: engineer installation

For VS Code:

```bash
# Install extensions
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
```

For JetBrains IDEs:

- Settings → Plugins → Search "GitHub Copilot" → Install

#### Step 3: authentication

Engineers authenticate using their GitHub accounts. If using Enterprise Managed Users, configure SAML single sign-on through your identity provider.

#### Step 4: verification

Test installation by opening a code file. Copilot should show inline suggestions as you type. If not, check authentication status in the extension settings.

## Training requirements

### Engineer training (45 minutes)

Module 1: basic usage (15 minutes)

This module covers:

- accepting and rejecting suggestions
- keyboard shortcuts
- enabling and disabling for specific file types
- when to trust suggestions versus manual coding

Module 2: effective prompting (15 minutes)

This module covers:

- writing comments that generate good code
- using function names and signatures strategically
- providing context through imports and surrounding code
- common patterns that work well

Module 3: security and quality (15 minutes)

This module covers:

- reviewing generated code critically
- recognising and rejecting insecure patterns
- content exclusions and when they apply
- integration with code review process

Format: This training should be delivered as a live demonstration with hands-on practice using real project examples.

### Manager briefing (30 minutes)

This briefing covers:

- capability overview and realistic expectations
- usage metrics and how to interpret them
- policy configuration and content exclusions
- addressing team concerns about AI tools

Format: This briefing should be delivered as a presentation with a Q&A session.

## Measuring success

### Quality metrics

For quality metrics refer to the monitoring and evaluation framework documentation.

### Common troubleshooting scenarios

#### Inline suggestions not appearing

Symptoms include:

- no autocomplete suggestions while typing
- extension appears inactive

Follow these steps to resolve the issue.

1. Verify extension is enabled and authenticated in IDE settings.
2. Check that file type is not excluded in Copilot settings.
3. Ensure inline suggestions are enabled: `"editor.inlineSuggest.enabled": true`.
4. Restart IDE and check network connectivity.
5. Sign out and sign back in to refresh authentication.

#### Copilot Chat not responding

Symptoms include:

- the chat window opening with no responses
- error messages in chat interface

Follow these steps to resolve the issue.

1. Check GitHub service status at [githubstatus.com](https://www.githubstatus.com/).
2. Verify license is active in GitHub organisation settings.
3. Clear chat history and restart conversation.
4. Check corporate proxy or firewall allows Copilot endpoints.
5. Update to latest extension version.

#### Agent mode failures

Symptoms include:

- agent tasks failing to complete
- timeout errors or incomplete work

Follow these steps to resolve the issue.

1. Break down complex tasks into smaller, more specific requests.
2. Ensure agent has sufficient permissions for requested operations.
3. Check repository size and complexity (very large repos may struggle).
4. Review task requirements - agent works best with clear, bounded objectives.
5. Monitor agent progress and provide clarifications when requested.

For detailed troubleshooting of Copilot agent mode specifically, see [Troubleshooting GitHub Copilot coding agent](https://docs.github.com/en/copilot/using-github-copilot/using-github-copilot-coding-agent-in-your-ide/troubleshooting-github-copilot-coding-agent).

#### Poor suggestion quality

Symptoms include:

- suggestions not matching project patterns
- irrelevant or incorrect code generated

Follow these steps to resolve the issue.

1. Provide more context via descriptive comments and function signatures.
2. Ensure relevant imports and dependencies are visible in file.
3. Use more specific variable and function names.
4. Check if content exclusions are blocking helpful context.
5. Try using Copilot Chat for complex scenarios instead of inline.
6. For Enterprise customers: verify custom model fine-tuning is configured.

Understanding how to communicate with Copilot effectively can dramatically improve suggestion quality. See the [prompt library](../../prompt-library/) for tested prompts and patterns.

#### Performance issues

Symptoms include:

- slow suggestion generation
- IDE lagging when Copilot is active

Follow these steps to resolve the issue.

1. Reduce the number of active IDE extensions.
2. Check network connectivity and latency.
3. Clear extension cache and reload IDE.
4. Update to latest Copilot extension version.
5. Check system resources (CPU, memory).

#### Enterprise-specific issues

Symptoms include:

- license assignment not working
- policy changes not taking effect
- usage metrics not appearing

Follow these steps to resolve the issue.

1. Verify user is member of correct GitHub organisation.
2. Check seat assignment in organisation Copilot settings.
3. Allow 15 to 30 minutes for policy changes to propagate.
4. Ensure user has signed out and back in after policy updates.
5. Contact GitHub support for billing or access issues.

### Security incidents

If an engineer discovers or accepts code containing:

- hardcoded secrets or credentials
- known security vulnerabilities
- data protection violations

They must take the following immediate actions.

1. Do not commit the code.
2. Report to your security team using standard incident process.
3. Document the suggestion for analysis.
4. Update content exclusions if pattern-based.

They must follow-up by:

- reviewing similar code in recent commits
- updating the team training materials
- sharing learning without blame

## Policy configuration reference

### Recommended content exclusions

```yaml
# Secrets and credentials
/.env
/.env.
/secrets/
/*.key
/*.pem
/credentials
/.aws/

# Configuration files
/config/production.yml
/config/production/
/terraform/production/

# Citizen data
/citizen-data/
/personal-identifiable-information/
/user-data/

# Security configurations
/security-configurations/
/auth-config/
/firewall-rules/

# Legacy code (if applicable)
/legacy/
/deprecated/
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

Disable Copilot for specific file types where suggestions are not helpful or may be risky.

### Organisation-level settings

Configure your organisation-level settings.

1. Navigate to Settings → Copilot.
2. Enable Copilot for organisation.
3. Configure suggestion matching (block suggestions matching public code if required).
4. Set content exclusion repository.
5. Enable telemetry collection for usage insights.

## Related resources

### Official GitHub resources
Official GitHub resources include:

- [GitHub Copilot documentation](https://docs.github.com/en/copilot) - complete official documentation
- [Copilot model comparison](https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide#ai-models-for-copilot-chat) - detailed model capabilities and selection
- [Copilot Trust Center](https://resources.github.com/copilot-trust-center/) - security, privacy, and compliance information
- [getting started with Copilot](https://docs.github.com/en/copilot/getting-started-with-github-copilot) - initial setup guides
- [Copilot best practices](https://github.blog/ai-and-ml/github-copilot/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/) - tips and effective usage patterns

### Enterprise and security
Enterprise and security resources include:
- [Managing Copilot in your organisation](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization) - policy configuration and administration
- [Copilot content exclusions](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/setting-policies-for-copilot-in-your-organization/excluding-content-from-github-copilot) - configuring what Copilot can access
- [Usage metrics and reporting](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/reviewing-usage-data-for-github-copilot-in-your-organization) - measuring adoption and impact

### Government procurement
Government procurement resources include:
- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [GitHub on G-Cloud](https://www.digitalmarketplace.service.gov.uk/) - search for GitHub Enterprise and Copilot offerings
- [TechUK Software Reseller Framework](https://www.techuk.org/) - alternative procurement route

### NCSC guidance
NCSC guidance includes:
- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - handling security issues

### Repository resources
Repository resources include:
- [Safe usage guidance: prototyping vs production](../../user-tool-guides/github-copilot/safe-usage-prototyping-vs-production.md) - differentiated controls for prototyping and production environments
- [AI SDLC Playbook](../../playbooks/ai-sdlc-playbook.md) - integrating AI code assistants across development lifecycle
- [Model Selection Playbook](../../playbooks/model-selection.md) - choosing appropriate models for tasks
- [Base guardrails](../../governance/guardrails-base.md) - foundational security controls for all AI tool usage

### Providing feedback

You can provide feedback to improve these materials by:

- raising an issue in the issue tracker (location to be confirmed)
- submitting improvements via pull request (see [CONTRIBUTING.md](../../CONTRIBUTING.md))
- contacting the team at the team email address (to be confirmed)
- using the feedback mechanism in your department's AI Engineering Lab community

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

When reusing content, you should:

- maintain attribution to this repository
- share improvements back via contribution
- ensure adaptations remain suitable for government use