> ALPHA
> This is a new service. Your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# GitHub Copilot premium credit management

This guidance explains how enterprise premium credits work in GitHub Copilot, how to manage them effectively, and what happens when you reach your allowance limits.

## Who this is for

This guide is for:

- engineers who need to understand credit usage and what happens when they run out
- enterprise administrators and organisation owners managing GitHub Copilot and configuring billing policies

## Before you start

Before using this guidance, you should:

- have GitHub Copilot Business or Enterprise enabled for your organisation
- understand your organisation's billing structure
- have administrator or owner permissions to manage policies

See also [billing for GitHub Copilot in organisations and enterprises](https://docs.github.com/en/copilot/concepts/billing/organizations-and-enterprises).

## Contents

[What are enterprise premium credits](#what-are-enterprise-premium-credits)

[Managing premium credits](#managing-premium-credits)

[When you run out of credits](#when-you-run-out-of-credits)

[Monitoring and optimising usage](#monitoring-and-optimising-usage)

## What are enterprise premium credits

### Understanding premium credits

Premium credits (also called premium requests) are a unit of measurement for using advanced AI capabilities in GitHub Copilot. Think of them as credits you spend when you use more powerful models or advanced features that require additional computing resources.

A premium request is any interaction where you ask Copilot to use premium features. Examples include generating code with a premium AI model, getting a pull request reviewed, or using autonomous coding features. Each time you use these capabilities, you consume premium requests based on the feature and model complexity.

### What is included in your plan

All paid Copilot plans include unlimited:

- code completions using included models (GPT-5 mini, GPT-4.1, GPT-4o)
- chat interactions using included models
- basic code suggestions and explanations

Your monthly premium request allowance includes:

- a set number of premium requests to use advanced models and features
- the exact number depends on your plan (see table below)
- allowances reset on the first of each month at 00:00:00 Coordinated Universal Time (UTC)
- unused requests do not carry over to the next month

The included models (GPT-5 mini, GPT-4.1, GPT-4o) do not consume premium requests on paid plans, so you can use them unlimited times for everyday coding tasks.

For more detail on how requests are counted and billed, see [Requests in GitHub Copilot](https://docs.github.com/en/copilot/concepts/billing/copilot-requests).

### Plans and premium request allowances

Different Copilot plans include different monthly premium request allowances per user.

All prices are shown in US dollars (USD).

| Plan | Monthly cost per user | Premium requests included |
|------|----------------------|--------------------------|
| Free | $0 USD | 50 premium requests |
| Pro | $10 USD | 300 premium requests |
| Pro+ | $39 USD | 1,500 premium requests |
| Business | $19 USD | 300 premium requests |
| Enterprise | $39 USD | 1,000 premium requests |

For a full comparison of plans and allowances, see [Plans for GitHub Copilot](https://github.com/features/copilot/plans).

### What consumes premium requests

Premium requests power advanced Copilot features and models. The number consumed varies based on the model complexity and feature used.

#### Advanced AI models

When you select a more powerful AI model beyond the included ones, each interaction consumes premium requests based on its multiplier. The multiplier reflects how much more computing power the model requires. Some models have a multiplier below 1, so one chat uses a fraction of a premium request (for example, 0.33× means about one-third of a request per chat).

| Model | Type | Multiplier | Premium requests per chat |
|-------|------|------------|---------------------------|
| Claude Opus 4.6 (latest) | Premium | 3× | 3 |
| Claude Opus 4.5 | Premium | 3× | 3 |
| Claude Haiku 4.5 | Premium | 0.33× | 0.33 |
| Claude Sonnet 4.5 | Premium | 1× | 1 |
| GPT-5.1 | Premium | 1× | 1 |
| GPT-5 mini | Included | 0× | Unlimited on paid plans |
| GPT-4.1 | Included | 0× | Unlimited on paid plans |
| GPT-4o | Included | 0× | Unlimited on paid plans |

These models are suitable for most everyday development tasks and do not consume premium requests.

Important note on model availability:

Your organisation or enterprise administrator can control which models are available to you through Copilot policies. You may not see a model listed above in your integrated development environment (IDE) because:

- your administrator may have restricted access to certain models to control costs or meet governance requirements
- your plan may not include access to that specific model
- the model may be in preview and not yet available to your organisation

Enterprise owners can define model policies that apply across the entire enterprise, or delegate control to individual organisation owners. These policies determine which AI models are accessible beyond the basic included models.

If you need access to a specific model that is not available, contact your organisation administrator or Copilot administrator.

For details on controlling which models and features are available to your users, see [GitHub Copilot policies](https://docs.github.com/en/copilot/concepts/policies).

Note: Model availability and multipliers may change. Check the model picker in your IDE for current options.

#### Features that consume premium requests

The table below shows which features consume premium requests and whether you can avoid costs by using included models.

| Feature | Where you use it | Free with included models? | Premium request cost |
|---------|------------------|---------------------------|---------------------|
| Code completions | Your IDE | Yes (always free) | 0 requests |
| [Copilot Chat](https://docs.github.com/en/copilot/concepts/billing/copilot-requests#premium-features) | Your IDE | Yes | 0 requests with GPT-4.1, GPT-4o, GPT-5 mini<br>1 request per message with other models |
| Agent mode | Your IDE chat | Yes | Same as Chat above |
| [Code Review](https://docs.github.com/en/copilot/concepts/agents/code-review) | GitHub.com or IDE | No | 1 request per review (always) |
| [Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) | GitHub.com | No | 1 request per session + 1 per steering comment |
| [Copilot CLI](https://docs.github.com/copilot/concepts/agents/about-copilot-cli) | Your terminal | No | 1 request per prompt (always)<br>Stops working when quota exhausted |
| Spark | GitHub.com | No | 4 requests per prompt (fixed) |
| Spaces | GitHub.com | No | 1 request per message |

Costs shown are before model multipliers. Premium models multiply the base cost (for example, Claude Opus 4.6 at 3× means 3 requests per use).

### Understanding agent mode vs coding agent

These features have similar names but work differently.

Agent mode works in your integrated development environment (IDE) as part of [Copilot Chat](https://docs.github.com/en/copilot/concepts/billing/copilot-requests#premium-features). You type messages and get responses. You can use included models (free) or premium models (costs credits).

Copilot coding agent works on [GitHub.com](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) autonomously. You assign it a task and it creates pull requests without your involvement. Always uses premium models.

Example: using Agent mode in Visual Studio (VS) Code with GPT-4.1 and sending 10 messages costs 0 premium requests. Using Copilot coding agent to create one pull request costs 1 premium request.

### Important notes on specific features

Copilot CLI does not support included models. When you run out of premium requests, [CLI stops working entirely](https://docs.github.com/copilot/concepts/agents/about-copilot-cli). You cannot fall back to GPT-4.1 or GPT-4o like you can in Chat.

Copilot coding agent pricing [changed in July 2025](https://github.com/orgs/community/discussions/165798) from 30 to 100+ requests per session to just 1 request per session, making it much more cost-effective.

## Managing premium credits

Enterprise administrators should configure policies and budgets to control spending. Development teams should monitor their individual usage.

### Step 1: review current usage

Before making changes, [download a usage report](https://docs.github.com/en/billing/how-tos/products/view-productlicense-use) to see which developers frequently hit limits. Identify power users, contact them to understand their requirements, and analyse which models and features cause the most usage.

### Step 2: configure billing policies

Navigate to your [enterprise or organisation policy settings](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/manage-request-allowances) and review the 'Premium request paid usage' policy.

Policy option can be:

- enabled (default) to allow users to exceed their allowance with charges at $0.04 USD per request
- enabled for specific products to allow paid usage only for selected AI tools (Copilot, Spark, coding agent)
- disabled to block all premium requests beyond the included allowance

### Step 3: set budgets

[Set up budgets](https://docs.github.com/en/billing/tutorials/set-up-budgets) to control spending.

Bundled premium requests budget (recommended). This manages all premium request stock keeping units (SKUs) together in one unified view.

Individual stock keeping unit (SKU) budgets. This sets separate budgets for each AI tool (Copilot, Spark, coding agent) for granular control and cost allocation.

### Step 4: choose hard or soft limits

The 'Stop usage when budget limit is reached' setting can be:

- enabled to create a hard limit (blocks usage when budget exhausted, no surprise charges)
- disabled to create a soft limit (allows overages with charges at $0.04 USD per request)

See [when you run out of credits](#when-you-run-out-of-credits) for detailed comparison, benefits and example costs.

### Step 5: enable budget alerts

Enable budget threshold alerts at 75%, 90% and 100% of budget consumption. Configure these in your billing settings to notify administrators before you reach limits.

### Step 6: enable additional paid requests (if needed)

To use premium requests beyond your monthly allowance, ensure the 'Premium request paid usage' policy is enabled (it is by default) and set a budget.

For individual users, navigate to GitHub profile settings, select billing, and [set a budget for additional premium requests](https://docs.github.com/en/billing/tutorials/set-up-budgets).

For enterprises and organisations, ensure the policy is enabled and [configure budgets](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/manage-request-allowances) at enterprise, organisation or cost centre level.

If you receive licences from multiple sources, you must [select a billing entity](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/multiple-licences) using the 'Usage billed to' dropdown. If you do not select one, premium requests will be blocked.

### First-time setup checklist

The 'Premium request paid usage' policy is enabled by default, meaning users can exceed their allowance and charges accrue automatically at $0.04 USD per request. Without setting a budget, costs can grow throughout the billing cycle with no automatic limit.

When first configuring Copilot:

- set budget caps immediately to control spending (see [Step 3: Set budgets](#step-3-set-budgets))
- enable budget threshold alerts at 75%, 90% and 100% for early warning (see [Step 5: Enable budget alerts](#step-5-enable-budget-alerts))
- [download usage reports](https://docs.github.com/en/billing/understanding-billing-for-your-enterprise/billing-reports-reference) weekly during initial deployment to establish baseline patterns
- monitor the billing dashboard at least monthly

Without budget limits, users continue using premium models beyond their allowance and charges accrue throughout the billing cycle. You will not receive notification until the bill arrives at the end of the cycle. Set budget caps and alerts immediately to regain control.

### Accounts created before August 2025

Accounts created before 22 August 2025 have a default $0 USD budget that automatically blocks premium requests over the allowance. [GitHub will remove all $0 USD budgets starting 2 December 2025](https://github.com/orgs/community/discussions/173899). After removal, paid overages will be enabled by default. Review your budget settings before December 2025.

## When you run out of credits

GitHub Copilot's behaviour when you exceed your premium request allowance depends on whether you configured a budget cap.

### With a budget cap (hard limit)

When 'Stop usage when budget limit is reached' is enabled:

- premium request usage stops when budget exhausted
- users automatically switch to included models (GPT-5 mini, GPT-4.1, GPT-4o)
- no charges beyond the budget
- usage resumes when budget resets or you increase it

Benefits include predictable costs, no unexpected billing and clear spending controls.

Considerations include that it may disrupt workflows if limits are reached unexpectedly, it requires active budget management and it needs clear communication to users.

### Without a budget cap (soft limit by default)

When no budget cap is set or 'Stop usage when budget limit is reached' is disabled:

- Copilot automatically switches you to included models for the remainder of the billing cycle
- you can still use Copilot with included models - basic code completions and chat remain available
- [additional premium requests](https://docs.github.com/en/billing/concepts/product-billing/github-copilot-premium-requests) are billed at $0.04 USD per request after model multipliers (for example, Claude Opus 4.6 at 3× = $0.12 USD per use)
- access to premium models and Code Review will be restricted until your monthly allowance resets or you increase your budget

Benefits include uninterrupted workflow, flexibility for varying needs and better support for unpredictable usage patterns.

Considerations include that costs can escalate without monitoring, it requires close usage tracking and there is potential for unexpected bills.

You will see this message in your IDE:

> 'You have exceeded your premium request allowance. We have automatically switched you to an included model (GPT-5 mini, GPT-4.1, or GPT-4o). Enable additional paid premium requests to continue using premium models.'

This is not an error. It is how the system maintains service availability whilst controlling costs.

### What remains available

When premium requests are exhausted, you retain access to:

- unlimited code completions with included models (GPT-5 mini, GPT-4.1, GPT-4o)
- Copilot Chat with included models
- all basic IDE integrations
- standard code suggestions

You cannot use:

- premium AI models (Claude Opus 4.6, Claude Opus 4.5, Claude Sonnet 4.5, GPT-5)
- Copilot Code Review on pull requests
- Copilot CLI (stops working entirely)
- features requiring premium model access

Response times for included models may vary during high usage and may be [subject to rate limiting](https://docs.github.com/en/copilot/concepts/rate-limits).

### Enterprise budget hierarchy

Enterprise-level budgets act as a failsafe for all spending. The budget hierarchy includes:

- cost centre budgets for specific teams or departments
- organisation budgets for individual organisations within the enterprise
- enterprise budget as an overall limit applying to all usage

If the enterprise budget is exhausted, usage is blocked even if lower-level budgets have remaining funds. Creating new budgets does not override existing budgets. If any applicable budget with 'Stop usage when budget limit is reached' enabled is exhausted, additional premium requests are blocked.

### Example scenario
```
A development team of 50 users on Copilot Business (300 premium requests per user per month) has these costs:

Without budget cap:

- included: 15,000 premium requests
- actual usage: 30,000 premium requests
- overage: 15,000 × $0.04 USD = $600 USD
- total: $950 USD subscription + $600 USD overage = $1,550 USD

With $200 USD budget cap:

- included: 15,000 premium requests
- budget allows: additional 5,000 requests ($200 USD ÷ $0.04 USD)
- total available: 20,000 requests
- once reached: premium features stop, basic features continue
- total: $950 USD subscription + $200 USD budget = $1,150 USD (controlled)
```
## Monitoring and optimising usage

Control costs whilst maintaining developer productivity through monitoring and smart model selection.

### Track your usage

#### In your IDE

Click the Copilot status icon to view current consumption, see which models you are using, and check remaining allowance.

#### On GitHub.com 

Navigate to Settings → Copilot to view your [monthly usage dashboard](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/monitor-premium-requests), download reports, and configure billing preferences.

### Optimise your usage

#### Use included models for routine tasks

GPT-5 mini, GPT-4.1 and GPT-4o are very capable and consume no premium requests. Use them for routine coding, refactoring and documentation. Reserve premium models for complex problems requiring advanced reasoning.

#### Choose models wisely

One interaction costs:

- $0 USD for GPT-4.1, GPT-4.o and GPT-5 mini (included models)
- $0.12 USD for Claude Opus 4.6 or 4.5 (3× multiplier models)
- $0.04 USD for GPT-5.1 (1× multiplier model)

#### Use coding agent for multi-file tasks

Coding agent uses one request per session, making it cost-effective for complex work. [Enable it](https://docs.github.com/en/copilot/how-tos/set-up/disable-enable-copilot-agent) in repositories where autonomous pull request creation provides value. Disable it where you prefer manual development.

#### Monitor and communicate

Download usage reports monthly to identify high consumers. Contact them to understand workflows and share best practices. Explain to your teams how premium requests work, when to use included vs premium models, and cost implications of different choices.

GitHub Copilot models, pricing, and features are subject to change. This guidance was last updated February 2026. Always verify current information on the [official GitHub Copilot documentation](https://docs.github.com/en/copilot).

GitHub Copilot is billed in US dollars (USD). UK government departments should apply current exchange rates when converting to pounds (GBP) for budget planning. All pricing in this document is shown in USD as per GitHub's official pricing.

## Further reading

See [Plans for GitHub Copilot](https://github.com/features/copilot/plans) for pricing and plan comparisons, and [Requests in GitHub Copilot](https://docs.github.com/en/copilot/concepts/billing/copilot-requests) for how premium requests work. To configure allowances, see [Managing the premium request allowance](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/manage-request-allowances). For budget configuration and tracking, see [Setting up budgets](https://docs.github.com/en/billing/tutorials/set-up-budgets) and [Monitoring usage](https://docs.github.com/en/copilot/how-tos/manage-and-track-spending/monitor-premium-requests).

For the latest feature updates, see the [GitHub Copilot changelog](https://github.blog/changelog/label/copilot/).

See the [GitHub Copilot getting started guide](getting-started.md) for initial setup and safe usage, the [advanced use guide](advanced-use.md) for advanced features and techniques, and the [customisation guide](customisation-guide.md) for custom instructions and configuration.
