> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Best Practice Repository
---

| Field | Value |
|-------|-------|
| Title | AI Engineering Lab Best Practice Repository |
| Version | 0.1.0 |
| Status | Draft |
---

> Central home for all AI Engineering Lab best practice content across government departments.

## About this repository

This repository provides reusable guidance, templates, training materials, and best practices for safely and effectively adopting AI code assistants across government.

## Quick Navigation

| Section | Description |
|---------|-------------|
| [Governance](./governance/) | Guardrails, compliance, and department-specific frameworks |
| [Playbooks](./playbooks/) | AI SDLC, context engineering, and model selection guidance |
| [Manager Tool Guides](./manager-tool-guides/) | Tool deployment and management guidance for leads |
| [Prompt Library](./prompt-library/) | Tested prompts organised by task and language |
| [Training Materials](./training-materials/) | Onboarding, scenarios, and guided learning paths |
| [Quality Metrics](./quality-metrics/) | Quality strategy and measurement frameworks |

## Who this repository is for

- **Software engineers and engineers** seeking practical guidance on using AI assistants effectively
- **Technical leads and architects** establishing team standards and patterns
- **Delivery managers and product owners** planning adoption within their teams
- **Senior Responsible Owners (SROs)** requiring governance and compliance assurance
- **Forward Deployed Engineers (FDEs)** supporting intensive adoption engagements

## Quick start by role

### I'm a engineer wanting to use AI code assistants

1. Read the [AI-SDLC Playbook](playbooks/ai-sdlc-playbook.md) for integration guidance
2. Review the [Guardrails](governance/guardrails-base.md) to understand usage boundaries
3. Explore the [Prompt Library](prompt-library/README.md) for proven patterns

### I'm a technical lead setting up my team

1. Review [Context Engineering](playbooks/context-engineering.md) for repository setup
2. Establish baseline metrics using the [Quality Strategy](quality-metrics/quality-strategy.md)
3. Consider requesting [FDE support](#forward-deployed-engineering-support) for your rollout

### I'm a manager selecting tools for my department

1. Start with [Comparative Guidance](manager-tool-guides/comparative-guidance.md)
2. Review tool-specific guides: [GitHub Copilot](manager-tool-guides/copilot/README.md) | [Amazon Q](manager-tool-guides/amazon-q/README.md)
3. Review the [Model Selection Playbook](playbooks/model-selection.md)

### I'm an SRO needing governance assurance

1. Review all governance documentation in the [governance](./governance/) folder
2. Understand the [Risk Register Template](governance/risk-register-template.md)
3. Review the [Incident Response Playbook](governance/incident-response-playbook.md)

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

## Forward Deployed Engineering support

The programme maintains a pool of expert senior engineers with extensive AI assistant experience. Forward Deployed Engineers (FDEs) provide intensive, hands-on support for teams requiring additional help.

**FDE support is appropriate for:**

- Teams with low AI maturity requiring intensive guidance
- Complex technical environments or niche requirements
- Critical adoption challenges requiring immediate intervention
- Capturing learnings for repository enhancement

**To request FDE support:**

1. Complete the readiness checklist
2. Submit a request via [PLACEHOLDER: request mechanism - form/email/service desk]
3. Await triage and allocation (typical response within [PLACEHOLDER: X] working days)

## Learning formats available

This repository supports multiple learning approaches to accommodate different needs and preferences:

| Format | Description | Best for |
|--------|-------------|----------|
| Written guides | Detailed documentation you can read at your own pace | Reference and deep understanding |
| Interactive modules | Self-paced online learning with exercises | Structured skill building |
| Video content | Demonstrations and walkthroughs | Visual learners |
| Guided workshops | Instructor-led sessions (face-to-face or remote) | Team onboarding and complex topics |
| Case studies | Real-world examples from government adoption | Practical context and lessons learned |

All materials are designed to meet GOV.UK content standards and include accommodations for neurodiverse learners.

## How to use this repository

### Finding what you need

- Use the [quick start guides](#quick-start-by-role) above based on your role
- Browse the [repository structure](#repository-structure) for specific topics
- Use your browser or IDE search functionality within documents

### Staying current

- [PLACEHOLDER: Subscribe to updates via email/RSS/Teams channel]
- Review documents against their stated review dates

### Providing feedback

We welcome feedback to improve these materials. You can:

- Raise an issue in [PLACEHOLDER: issue tracker location]
- Submit improvements via pull request (see [CONTRIBUTING.md](CONTRIBUTING.md))
- Contact the team at [PLACEHOLDER: team email address]
- Use the feedback mechanism in your department's AI Engineering Lab community

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government to keep this repository current and comprehensive.

Before contributing, please read [CONTRIBUTING.md](CONTRIBUTING.md) which covers:

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

---