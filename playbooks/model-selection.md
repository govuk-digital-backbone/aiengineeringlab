> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Model selection guide

> Guidance on selecting the right AI code assistant and model for your task.

## Purpose

This guide helps engineers and teams choose appropriate AI code assistants and models based on their work type, task requirements and cost considerations. It supports the programme's goal of optimising cost to use trade-offs while maintaining productivity gains.

## Tools in scope

The AI Engineering Lab programme includes 4 AI code assistants:

- GitHub Copilot Enterprise by Microsoft and GitHub
- Claude Code by Anthropic
- Amazon Q Engineer by AWS
- Gemini Code Assist by Google

Each tool has different strengths, pricing models and model options. This guide will be updated as comparative evidence emerges from programme deployments.

---

## Selection by work type

Teams are cohorted by work type during assessment. Different work types may benefit from different tools or approaches.

### Modernisation projects

Work involving legacy system updates, language migrations and refactoring.

Evidence from deployments:

| Project | Tool used | Task | Result |
|---------|-----------|------|--------|
| Celink Loan Boarding | Amazon Q | EGL to Java migration | 33 days saved, $17,000 net saving |
| Sucden Financial | GitHub Copilot | Windows services to cloud microservices, SOAP to REST | 30% to 35% productivity gain |
| SCA Project | Cursor (Claude 3.7) | VB6 to .NET and Blazor modernisation | 10% to 25% efficiency gains |

### Application development

New application development, feature building.

Evidence from deployments:

| Project | Tool used | Task | Result |
|---------|-----------|------|--------|
| CAFCASS | GitHub Copilot | Angular, .NET, TypeScript development | 20% average productivity gain |
| Department of Transport | GitHub Copilot | General development and prototyping | 30% to 40% for prototyping |

### Test generation

Unit tests, integration tests, Behaviour-Driven Development (BDD) and Playwright tests.

Evidence from deployments:

| Project | Tool used | Task | Result |
|---------|-----------|------|--------|
| Celink | Amazon Q | Manual test case writing | 30 days reduced to 10 to 12 days (60% saving) |
| Department of Transport | GitHub Copilot | Test automation | 70% to 80% productivity gain |
| NEPO | GitHub Copilot (Claude 3.7) | Unit testing | 1 day reduced to 1.5 to 2 hours (75% saving) |
| Wood Project | GitHub Copilot | Unit testing | 20% to 30% gain |

### Legacy system maintenance

Maintaining and enhancing existing systems.

Evidence from deployments:

| Project | Tool used | Task | Result |
|---------|-----------|------|--------|
| Wood Project | GitHub Copilot | Legacy system maintenance | 10% to 20% overall gain |
| Sucden Financial | GitHub Copilot | Working with legacy code during migration | Particularly effective |

### Data and infrastructure

Data engineering, infrastructure automation, platform work.

Evidence: Limited specific evidence in current programme data. Will be updated as data and infrastructure teams are onboarded.

---

## Important considerations when selecting models

When choosing an AI model for your tool, consider these 2 primary characteristics.

### Model curiosity level

Model curiosity levels include:

- high curiosity: models that ask questions, dive deeper and explore problems broadly
- low curiosity: models that stick closely to instructions without much exploration

### Model agency level

Model agency levels include:

- high agency: models willing to go beyond your prompt and solve problems independently
- low agency: models that execute exactly what you ask without going further

---

## Model recommendations by use case

### Fast, iterative development

Best models: Claude 4.5 Haiku, Gemini 3 Pro or Flash.

Characteristics: fast response times, solid code quality, medium agency.

Use when:

- making quick code changes
- simple bug fixes
- rapid prototyping
- straightforward implementations

### Deep problem analysis and new projects

Best models: GPT-5.2, Claude Opus 4.5.

Characteristics: very high curiosity, excellent at reasoning through complex problems.

Use when:

- approaching a new codebase
- working on unfamiliar technologies
- need broad exploration of solutions
- complex architectural decisions
- want the model to think outside the box

### Daily driver for most tasks

Best model: Claude 4.5 Sonnet.

Characteristics: strong reasoning, excellent code generation, balanced agency.

Use when:

- general development work
- building features
- code reviews and explanations
- most coding tasks that need reliable, high quality output

### Precise, instruction-following tasks

Best model: Claude 4.5 Sonnet or older versions for lower agency.

Characteristics: balanced agency, executes what you ask for.

Use when:

- you want stricter adherence to requirements
- simple, well defined tasks
- do not want the model to add extra features
- need more predictable output

### Creative problem solving

Best models: Claude 4.5 Opus or GPT-5.2 (Thinking).

Characteristics: higher agency, goes above and beyond, validates solutions.

Use when:

- want the model to suggest improvements
- need alternative approaches explored
- benefit from additional testing and validation
- want comprehensive solutions

---

## Model personality comparison

| Model | Speed | Curiosity | Agency | Best for |
|-------|-------|-----------|---------|----------|
| GPT-5.2 | Very fast | Medium | Medium | Rapid development |
| Gemini 3.5 Pro | Very fast | Medium | Medium to high | Fast iterations, impulsive execution |
| Claude 4.5 Haiku | Fast | Medium | Medium | Fast tasks with reasoning |
| Claude 4.5 Sonnet | Medium | Medium | Medium | Stable, predictable coding |
| Claude 4.5 Opus | Medium to slow | High | Very high | Comprehensive solutions |

---

## Multi-model approach

For complex problems, consider using multiple models to validate solutions.

Technique: present the same problem to different AI assistants, then have each evaluate the other's solution.

To use multi-model validation, complete these steps.

1. Present the problem to Model A, for example GitHub Copilot.
2. Present the same problem to Model B, for example Claude.
3. Ask Model A to evaluate Model B's solution.
4. Ask Model B to evaluate Model A's solution.
5. Create the best approach based on their analysis.

Each model will evaluate and return analysis. This approach adds overhead but can improve solution quality for important problems.

---

## Practical tips for model selection

### When you are unsure

When you are unsure which model to use:

- start with auto mode: many platforms offer automatic model selection based on task and capacity
- use your daily driver: Claude 4.5 Sonnet works well for most tasks
- switch mid conversation: if you are not getting the results you want, try a different model

### Common switching scenarios

You should switch models when:

- stuck in a loop: switch to a different model for a fresh perspective
- need more creativity: move from low agency to high agency models
- want faster responses: switch to GPT-5.2 or Gemini 3.5 Pro
- need deeper analysis: switch to Claude 4.5 Opus or other deep reasoning models

### Context and efficiency

Consider these factors for context and efficiency:

- separate chat sessions: use different models for different types of tasks
- consider response time: balance quality needs with speed requirements
- match verbosity preference: some models are more verbose than others

---

## Premium credit management

Teams learn which AI code assistant models and approaches suit different tasks, optimising cost to use trade-offs and preventing licence waste.

Principle: use premium models for complex reasoning tasks and smaller or standard models for specialist or routine tasks.

Sustainable usage patterns across billing periods ensure that premium model calls are distributed effectively without exhausting limits early, maintaining consistent impact throughout the period.

Credit allocation is based on team size and maturity, with monitoring set up to track usage. Intervention occurs if burn rate is unsustainable.

---

## Comparative analysis

The programme is designed to generate evidence-based recommendations for tool to task matching.

The programme uses this approach:

- teams are cohorted by work type, including modernisation, application development, legacy maintenance, data projects and infrastructure
- different tools are deployed across similar cohorts
- differential impact is tracked as teams progress through maturity levels
- evidence feeds back into this guide

Current status: comparative data collection is ongoing. This section will be updated with findings as evidence accumulates.

---

## Advanced considerations

### Task specific optimisation

Task-specific model recommendations include:

- code explanation: high curiosity models such as Claude 4.5 Opus
- bug fixing: balanced models such as Claude 4.5 Sonnet
- feature implementation: lower agency models for precision
- architecture design: high curiosity and high agency models

### Team considerations

Team-level considerations include:

- consistency: establish team standards for model selection
- documentation: some models excel at generating comprehensive documentation
- code reviews: models with higher agency can provide more thorough feedback

### Cost and capacity

Cost and capacity factors include:

- auto mode: considers model availability and cost
- peak usage: have backup model preferences
- budget constraints: balance model capability with usage costs

---

## Getting started

1. Begin with a balanced model such as Claude 4.5 Sonnet.
2. Experiment with different models for the same task.
3. Note which models work best for your specific use cases.
4. Build your personal quiver of 3 to 4 go-to models.
5. Do not be afraid to switch if you are not getting good results.

Remember: model selection is highly personal and task dependent. What works best for one developer or use case may not work for another. The important thing is experimentation and building familiarity with different model characteristics.

## Related documents

- 'GitHub Copilot Guide' (../manager-tool-guides/copilot/README.md)
- 'Amazon Q Engineer Guide' (../manager-tool-guides/amazon-q/README.md)
- 'Tool Comparative Guidance' (../manager-tool-guides/comparative-guidance.md) to select appropriate tools
- 'Prompt Library' (../prompt-library/README.md) for ready to use examples

---

### Vendor documentation

- 'Claude API Documentation' (https://docs.anthropic.com/claude/docs) - official Anthropic Claude documentation
- 'OpenAI API Documentation' (https://platform.openai.com/docs) - GPT models and API reference
- 'Google AI Studio Documentation' (https://ai.google.dev/gemini-api/docs) - Gemini models documentation
- 'Anthropic Prompt Engineering Guide' (https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) - Claude specific prompting techniques
- 'OpenAI Prompt Engineering Guide' (https://platform.openai.com/docs/guides/prompt-engineering) - best practices for GPT models

## Contributing

See 'CONTRIBUTING.md' (../../CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government. Share your team's experience, lessons learned and effective practices to help other departments.