> ALPHA
> This is a new service. Your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# Agent mode billing and credit consumption

This guide explains how agent mode in the integrated development environment (IDE) consumes premium requests. It covers how to choose the right model for each task and how administrators can control which models engineers can use.

## Contents

[Who this is for](#who-this-is-for)

[Before you start](#before-you-start)

[How agent mode charges premium requests](#how-agent-mode-charges-premium-requests)

[What auto model selection does in agent mode](#what-auto-model-selection-does-in-agent-mode)

[Whether you are warned before agent mode uses a premium model](#whether-you-are-warned-before-agent-mode-uses-a-premium-model)

[How to constrain agent mode to included models](#how-to-constrain-agent-mode-to-included-models)

[How administrators can control agent mode model access](#how-administrators-can-control-agent-mode-model-access)

[Choosing the right model for your task](#choosing-the-right-model-for-your-task)

[Practical tips for using agent mode without exhausting your allowance](#practical-tips-for-using-agent-mode-without-exhausting-your-allowance)

## Who this is for

This guide is for:

- engineers who use agent mode and want to understand how it affects their premium request allowance
- enterprise administrators and organisation owners who need to control model access and prevent unexpected costs

## Before you start

Before reading this guide, you should understand how premium credits work and what your monthly allowance includes. Read the [GitHub Copilot premium credit management guide](premium-credit-management.md) for the foundational concepts, plan allowances, and model multiplier table.

## How agent mode charges premium requests

Each prompt you enter in agent mode counts as one premium request, multiplied by the model's multiplier. Internal tool calls made during a single response do not count as separate charges. These include:

- reading files
- running terminal commands
- searching the codebase

Only the prompts you enter are billed. Tool calls or background steps taken by the agent are not charged. Read more about [agent mode](https://docs.github.com/en/copilot/how-tos/chat-with-copilot/chat-in-ide#using-agent-mode).

Agent mode does not switch to a different model mid-session, regardless of task complexity. If you select GPT-4.1, all responses use GPT-4.1 and no premium requests are consumed.

This matters because complex tasks require many messages. A multi-file refactoring job might involve 20 or more back-and-forth exchanges. Each one counts as a premium request if you are using a premium model.

The table below compares typical agent mode sessions across different task types and model choices. These figures are illustrative estimates based on our experience. Your actual usage will vary depending on:

- how you prompt
- how precise your instructions are
- how much iteration the task requires

| Task | Typical messages | Included model (0x) | Claude Sonnet 4.5 (1x) | Claude Opus 4.5 (3x) | % of Business plan (300 requests) with Opus 4.5 |
|------|-----------------|---------------------|------------------------|----------------------|--------------------------------------------------|
| Single-file bug fix | 3 to 5 | 0 requests | 3 to 5 requests | 9 to 15 requests | 3% to 5% |
| Multi-file refactoring | 15 to 25 | 0 requests | 15 to 25 requests | 45 to 75 requests | 15% to 25% |
| Feature implementation | 20 to 40 | 0 requests | 20 to 40 requests | 60 to 120 requests | 20% to 40% |
| Test generation for a module | 5 to 10 | 0 requests | 5 to 10 requests | 15 to 30 requests | 5% to 10% |

Engineers who regularly use premium models on complex tasks can exhaust a 300-request business plan allowance within a few focused sessions.

## What auto model selection does in agent mode

When you select 'Auto', it [automatically chooses a model](https://docs.github.com/en/copilot/concepts/auto-model-selection) based on current availability. It only selects models with multipliers of 1x or below, so it will never select Claude Opus or other high-cost models.

The models it may currently select include:

- GPT-4.1
- GPT-5 mini
- GPT-5.1-Codex-Max
- Claude Haiku 4.5
- Claude Sonnet 4.5

Auto model selection can select free included models, so not every request costs a premium credit. If your allowance runs out, it will switch to a 0x included model automatically.

When using auto model selection:

- it selects one model and uses it for the entire chat session
- you cannot preview which model it will choose before sending your prompt
- hover over the response after it is generated to see which model was used
- start a new chat session to switch to a different model

On paid plans, [auto model selection applies a 10% discount to the model multiplier](https://docs.github.com/en/copilot/concepts/billing/copilot-requests). For example, if Auto selects Claude Sonnet 4.5 (normally 1x), you are charged 0.9 of a premium request per message. This discount applies to Copilot Chat and agent mode in the IDE, but not to the Copilot coding agent on GitHub.com. If you are using auto model selection outside VS Code, read the [about Copilot auto model selection](https://docs.github.com/en/copilot/concepts/auto-model-selection) guide to confirm whether the discount applies.

Auto model selection is generally available in VS Code. It is in public preview for Visual Studio, JetBrains, Xcode, and Eclipse. For those IDEs, your administrator must enable the 'Editor preview features' policy before 'Auto' appears in the model picker.

Auto model selection respects administrator model policies and will not route to any model your organisation has disabled.

## Whether you are warned before agent mode uses a premium model

Agent mode does not prompt you before it charges a premium request. The charge occurs when you send each message. You can see the model currently selected in the model picker before you send a message. You can also see which model processed each response by hovering over it in the chat window after it is generated. [Check your usage dashboard in GitHub settings](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/monitor-premium-requests) to monitor your current consumption.

## How to constrain agent mode to included models

You can use agent mode without consuming any premium requests by selecting an included model in the model picker before starting your session.

Follow these steps to select an included model.

1. Open the Copilot Chat panel in your IDE.
2. Select the mode dropdown and choose Agent.
3. Open the model picker and select GPT-4.1, GPT-4o, or GPT-5 mini.
4. Send your prompt. No premium requests are consumed.

You can also select auto model selection on a paid plan. As described in [What auto model selection does in agent mode](#what-auto-model-selection-does-in-agent-mode), it will not select Opus-class or other high-cost models.

## How administrators can control agent mode model access

Enterprise and organisation administrators can restrict which models are available in agent mode using the model policy in GitHub Copilot settings. [Model policies apply equally to both chat and agent mode](https://docs.github.com/en/copilot/how-tos/use-ai-models/configure-access-to-ai-models) because both use the same model picker.

For a step-by-step walkthrough of restricting models, setting spending limits, and monitoring usage by engineer, read [Managing agent mode and premium credit spend](../../manager-tool-guides/github-copilot/README.md#managing-agent-mode-and-premium-credit-spend) in the GitHub Copilot manager tool guide.

Model policies have three states: enabled, disabled, and unconfigured. Unconfigured defaults to disabled. You can use model policies to:

- enable or disable individual models for all Copilot features across your organisation
- disable Autopilot mode in VS Code for all engineers by enabling the ChatToolsAutoApprove policy in your Copilot settings

There is no way to exclude a model from auto routing only while keeping it available for manual selection. Administrators cannot set a default model for engineers. GitHub controls the platform-wide default, which has been GPT-4.1 since May 2025.

For full guidance on model policy configuration, read [configuring access to AI models in GitHub Copilot](https://docs.github.com/en/copilot/how-tos/use-ai-models/configure-access-to-ai-models).

### Enforcing included model use through model policies

Whilst administrators cannot set a default model for engineers, they can disable all premium models to prevent engineers from using any model that costs a premium request. Auto model selection will then only route to the remaining free included models: GPT-4.1, GPT-4o, and GPT-5 mini.

Follow these steps to enforce included-only model use.

1. Navigate to your organisation settings on GitHub.com.
2. Select Copilot, then Policies, then AI models.
3. Disable every model with a multiplier above 0x. This includes Claude Haiku 4.5 (0.33x), Claude Sonnet 4.5 (1x), GPT-5.1 and all other premium models.
4. Save your changes. The restriction applies immediately across all features and IDEs.

Note that 'above 0x' includes any premium model, even low-cost ones such as Claude Haiku 4.5 (0.33x) and Grok Code Fast 1 (0.25x).

Engineers lose manual access to any model you disable, so consider which approach suits your team.

| Approach | Disable these models | Engineers can use | Auto cost per message |
|----------|---------------------|-------------------|-----------------------|
| Strict (zero premium cost) | All models above 0x | GPT-4.1, GPT-4o, GPT-5 mini only | Not applicable |
| Middle-ground (near-zero cost) | All models at 1x and above | Sub-1x models (for example, Claude Haiku 4.5) also available | Approximately 0.30 per message |

Both options affect manual selection and Auto routing.

### Controlling auto model selection in preview IDEs

For preview IDEs, you can remove auto model selection as an option by disabling the 'Editor preview features' policy. Engineers will then need to select a model manually and retain access to all models you have not disabled.

### Adding custom models

Organisation owners can integrate custom models from supported AI providers using their own API keys. Enterprise owners can further control which organisations have access to custom models. Read [Configuring access to AI models in GitHub Copilot](https://docs.github.com/en/copilot/how-tos/use-ai-models/configure-access-to-ai-models) for setup steps.

## Choosing the right model for your task

Selecting the right model for the type of work you are doing is the most effective way to control premium request consumption. The table below maps common task types to the recommended model and its cost. For a full technical comparison of all available models, including context window sizes and capability details, read the [GitHub Copilot model comparison](https://docs.github.com/en/copilot/reference/ai-models/model-comparison).

| Task type | Recommended model | Cost on paid plan |
|-----------|------------------|-------------------|
| Writing functions, tests, refactoring, documentation, debugging | GPT-4.1 | Free (no premium requests consumed) |
| Complex business logic where an included model gave insufficient output | GPT-5.1 | 1 premium request per message ($0.04 USD at overage rate) |
| Complex problem-solving, sophisticated reasoning, and architecture decisions | Claude Opus 4.5 or Claude Opus 4.6 | 3 premium requests per message ($0.12 USD at overage rate) |

Use included models as your default. Move to a premium model only when the included model cannot meet your need.

## Practical tips for using agent mode without exhausting your allowance

Write precise prompts that give Copilot enough context in one go. Fewer messages means fewer premium requests.

For multi-file implementation, use the [Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) instead of agent mode with a premium model. It charges one request for the entire session.

Start a new chat session for each distinct task. Prior messages build up in context and make responses longer.

Before a long session, check your remaining allowance in GitHub settings under Copilot. This helps you decide whether to use an included model or a premium one.

[Monitor your usage dashboard after each session](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/monitor-premium-requests) to see how many requests it consumed. This helps you calibrate future model choices.

You can also enforce cost controls at the repository level using hooks. The [GitHub Copilot customisation guide](customisation-guide.md#hooks) covers how to set up hooks for cost tracking, security validation, and audit logging.

## Further reading

[Auto model selection generally available in VS Code](https://github.blog/changelog/2025-12-10-auto-model-selection-is-generally-available-in-github-copilot-in-visual-studio-code/) announced the December 2025 release

[GitHub Copilot advanced use guide](advanced-use.md) describes agent mode workflows including refactoring and test generation

[Copilot CLI billing guide](copilot-cli-billing.md) explains how CLI autopilot billing differs from IDE agent mode