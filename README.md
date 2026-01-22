> **ALPHA**:
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab repository

This is the central home for all AI Engineering Lab best practice content across government departments.

| Field | Value |
|-------|-------|
| Title | AI Engineering Lab Repository |
| Version | 0.1.0 |
| Status | Draft |


## About this repository

This repository provides reusable guidance, templates, training materials, and best practices for safely and effectively adopting AI code assistants across government.

## Quick navigation

| Section | Description |
|---------|-------------|
| [Governance](./governance/) | Guardrails, compliance, and department-specific frameworks |
| [Playbooks](./playbooks/) | AI SDLC, context engineering, and model selection guidance |
| [Manager Tool Guides](./manager-tool-guides/) | Tool deployment and management guidance for leads |
| [Prompt Library](./prompt-library/) | Tested prompts organised by task and language |
| [Training Materials](./training-materials/) | Onboarding, scenarios, and guided learning paths |
| [Quality Metrics](./quality-metrics/) | Quality strategy and measurement frameworks |

## Who this repository is for

- software engineers and engineers looking for guidance on using AI assistants effectively
- technical leads and architects who are establishing team standards and patterns
- delivery managers and product owners who are planning adoption within their teams
- senior responsible owners (SROs) who require governance and compliance assurance
- forward deployed engineers (FDEs) who support intensive adoption engagements

## Quick start by role

### I'm a engineer wanting to use AI code assistants

1. Read the [AI-SDLC Playbook](playbooks/ai-sdlc-playbook.md) for integration guidance.
2. Review the [Guardrails](governance/guardrails-base.md) to understand usage boundaries.
3. Explore the [Prompt Library](prompt-library/README.md) for proven patterns.

### I'm a technical lead setting up my team

1. Review [Context Engineering](playbooks/context-engineering.md) for repository setup.
2. Establish baseline metrics using the [Quality Strategy](quality-metrics/quality-strategy.md).
3. Consider requesting [FDE support](#forward-deployed-engineering-support) for your rollout.

### I'm a manager selecting tools for my department

1. Start with [Comparative Guidance](manager-tool-guides/comparative-guidance.md).
2. Review tool-specific guides: [GitHub Copilot](manager-tool-guides/copilot/README.md) | [Amazon Q](manager-tool-guides/amazon-q/README.md).
3. Review the [Model Selection Playbook](playbooks/model-selection.md).

### I'm an SRO needing governance assurance

1. Review all governance documentation in the [governance](./governance/) folder.
2. Understand the [Risk Register Template](governance/risk-register-template.md).
3. Review the [Incident Response Playbook](governance/incident-response-playbook.md).

## Repository structure 
```
├── README.md                    # You are here
├── CONTRIBUTING.md              # How to contribute to this repository
│
├── assessment/                  # Readiness and maturity evaluation
│   ├── maturity-assessment-framework.md
│   ├── team-classification-guide.md
│   └── assessment-questionnaires/
│       ├── delivery-manager-assessment.md
│       ├── individual-engineer-assessment.md
│       └── technical-lead-assessment.md
│
├── governance/                  # Policy and guardrails
│   ├── guardrails-base.md
│   ├── incident-response-playbook.md
│   ├── risk-register-template.md
│
├── manager-tool-guides/         # Tool selection and management
│   ├── comparative-guidance.md
│   ├── amazon-q/
│   │   └── README.md
│   └── copilot/
│       └── README.md
│
├── playbooks/                   # Operational guidance
│   ├── ai-code-assistant-instructions.md
│   ├── ai-sdlc-playbook.md
│   ├── context-engineering.md
│   ├── model-selection.md
│   └── prompt-engineering.md
│
├── prompt-library/              # Reusable prompt patterns
│   ├── README.md
│   ├── prompt-template.md
│   └── by-task-type/
│       └── README.md
│
├── quality-metrics/             # Measurement and reporting
│   ├── measurement-playbook.md
│   ├── quality-strategy.md
│
└── training-materials/          # Learning resources
    ├── README.md
    ├── recommended-resources.md
    └── guided-training/
        └── README.md
```

## Forward deployed engineering support

The programme maintains a pool of expert senior engineers with extensive AI assistant experience. FDEs provide intensive, hands-on support for teams requiring additional help.

**FDE support is appropriate for:**

- teams with low AI maturity requiring intensive guidance
- complex technical environments or niche requirements
- critical adoption challenges requiring immediate intervention
- capturing learnings for repository enhancement

**To request FDE support:**

1. complete the readiness checklist
2. submit a request via [PLACEHOLDER: request mechanism - form/email/service desk]
3. await triage and allocation, which will be within 10 working days

## Learning formats available

This repository supports multiple learning approaches to accommodate different needs and preferences.

| Format | Description | Best for |
|--------|-------------|----------|
| Written guides | Detailed documentation you can read at your own pace | Reference and deep understanding |
| Interactive modules | Self-paced online learning with exercises | Structured skill building |
| Video content | Demonstrations and walkthroughs | Visual learners |
| Guided workshops | Instructor-led sessions (face-to-face or remote) | Team onboarding and complex topics |
| Case studies | Real-world examples from government adoption | Practical context and lessons learned |

All materials are designed to meet GOV.UK content standards and include accommodations for neurodiverse learners.

## How to use this repository

### Find what you need by:

- using the [quick start guides](#quick-start-by-role) above based on your role
- browsing the [repository structure](https://github.com/govuk-digital-backbone/aiengineeringlab/edit/feature/v1-release-v0.0.1/README.md#repository-structure)) for specific topics
- using your browser or IDE search functionality within documents

### Stay current by:

- reviewing documents against their stated review dates

### Providing feedback

We welcome feedback to improve these materials. You can:

- raise an issue in [PLACEHOLDER: issue tracker location]
- submit improvements via pull request (see [CONTRIBUTING.md](CONTRIBUTING.md))
- contact the team at [PLACEHOLDER: team email address]
- use the feedback mechanism in your department's AI Engineering Lab community

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government to keep this repository current and comprehensive.

Before contributing, you must read [CONTRIBUTING.md](CONTRIBUTING.md) which covers:

- content standards and style guide
- review and approval process
- accessibility requirements
- how to submit changes

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

When reusing content, you must:

- maintain attribution to this repository
- share improvements back via contribution
- ensure adaptations remain suitable for government use

---
