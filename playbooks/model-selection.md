> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Model Selection Guide

> Guidance on selecting the right AI code assistant and model for your task.

## Purpose

This guide helps engineers and teams choose appropriate AI code assistants and models based on their work type, task requirements, and cost considerations. It supports the programme's goal of optimising cost-to-utilisation trade-offs while maintaining productivity gains.

## Tools in scope

The AI Engineering Lab programme includes four AI code assistants:

| Tool | Vendor | Licence Volume |
|------|--------|----------------|
| GitHub Copilot Enterprise | Microsoft/GitHub | 1,000 |
| Claude Code | Anthropic | 1,000 |
| Amazon Q Engineer | AWS | 500 |
| Gemini Code Assist | Google | 500-750 |

Each tool has different strengths, pricing models, and model options. This guide will be updated as comparative evidence emerges from programme deployments.

---

## Selection by work type

Teams are cohorted by work type during assessment. Different work types may benefit from different tools or approaches.

### Modernisation projects

Work involving legacy system updates, language migrations, and refactoring.

**Evidence from deployments:**

| Project | Tool Used | Task | Result |
|---------|-----------|------|--------|
| Celink Loan Boarding | Amazon Q | EGL to Java migration | 33 days saved, $17,000 net saving |
| Sucden Financial | GitHub Copilot | Windows services to cloud microservices, SOAP to REST | 30-35% productivity gain |
| SCA Project | Cursor (Claude 3.7) | VB6 to .NET/Blazor modernisation | 10-25% efficiency gains |

### Application development

New application development, feature building.

**Evidence from deployments:**

| Project | Tool Used | Task | Result |
|---------|-----------|------|--------|
| CAFCASS | GitHub Copilot | Angular, .NET, TypeScript development | 20% average productivity gain |
| Department of Transport | GitHub Copilot | General development and prototyping | 30-40% for prototyping |

### Test generation

Unit tests, integration tests, BDD/Playwright tests.

**Evidence from deployments:**

| Project | Tool Used | Task | Result |
|---------|-----------|------|--------|
| Celink | Amazon Q | Manual test case writing | 30 days reduced to 10-12 days (60% saving) |
| Department of Transport | GitHub Copilot | Test automation | 70-80% productivity gain |
| NEPO | GitHub Copilot (Claude 3.7) | Unit testing | 1 day reduced to 1.5-2 hours (75% saving) |
| Wood Project | GitHub Copilot | Unit testing | 20-30% gain |

### Legacy system maintenance

Maintaining and enhancing existing systems.

**Evidence from deployments:**

| Project | Tool Used | Task | Result |
|---------|-----------|------|--------|
| Wood Project | GitHub Copilot | Legacy system maintenance | 10-20% overall gain |
| Sucden Financial | GitHub Copilot | Working with legacy code during migration | Particularly effective |

### Data and infrastructure

Data engineering, infrastructure automation, platform work.

**Evidence:** Limited specific evidence in current programme data. Will be updated as data/infrastructure teams are onboarded.

---

## Premium credit management

Teams learn which AI code assistant models and approaches suit different tasks, optimising cost-to-utilisation trade-offs and preventing licence waste.

**Principle:** Use premium models for complex reasoning tasks, and smaller/standard models for specialist or routine tasks.

Sustainable usage patterns across billing periods ensure that premium model calls are distributed effectively without exhausting limits early, maintaining consistent impact throughout the period.

Credit allocation is based on team size and maturity, with monitoring set up to track usage. Intervention occurs if burn rate is unsustainable.

---

## Multi-model approach

For complex problems, consider using multiple models to validate solutions.

**Technique:** Present the same problem to different AI assistants, then have each evaluate the other's solution.

**Process:**

1. Present the problem to Model A (e.g., GitHub Copilot)
2. Present the same problem to Model B (e.g., Claude)
3. Ask Model A to evaluate Model B's solution
4. Ask Model B to evaluate Model A's solution
5. Synthesise the best approach based on their analysis

Each model will evaluate and return analysis. This approach adds overhead but can improve solution quality for important problems.

---

## Comparative analysis

The programme is designed to generate evidence-based recommendations for tool-to-task matching.

**Approach:**

- Teams are cohorted by work type (modernisation, application development, legacy maintenance, data projects, infrastructure)
- Different tools are deployed across similar cohorts
- Differential impact is tracked as teams progress through maturity levels
- Evidence feeds back into this guide

**Current status:** Comparative data collection is ongoing. This section will be updated with findings as evidence accumulates.

---

## Related documents

- [GitHub Copilot Guide](../manager-tool-guides/copilot/README.md)
- [Amazon Q Engineer Guide](../manager-tool-guides/amazon-q/README.md)
- [Tool Comparative Guidance](../manager-tool-guides/comparative-guidance.md) to select appropriate tools
- [Prompt Library](../prompt-library/README.md) for ready-to-use examples

---

## Document history

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | January 2026 | Kyle Lyttle | Initial draft based on programme evidence |

---

*This guide is a living document. As the programme generates more comparative evidence, recommendations will be refined. Contribute your experiences via the Champion network.*
