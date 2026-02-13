> **ALPHA**
> This is a new service - your feedback will help us to improve it.

# AI Coding Assistant Security Policy

> Organisational security policy for the adoption and use of AI coding assistants in UK government contexts.

## Purpose

This document establishes the security policy framework for AI coding assistant adoption across government. It defines:

- policy scope and applicability
- roles and responsibilities
- policy statements (mandates)
- compliance and assurance requirements
- exception and escalation processes

This policy governs the [guardrails base](../governance/guardrails-base.md) and all department-specific extensions. The guardrails provide technical controls. This policy provides the governance mandate.

---

## Document hierarchy

| Document | Purpose | Audience |
|----------|---------|----------|
| **This policy** | Mandates and governance | SROs, SIROs, Security Leads |
| [Threat model](threat-modelling.md) | Risk assessment and threat catalogue | Security teams |
| [Guardrails base](../governance/guardrails-base.md) | Technical controls | All users |
| Tool guides | Tool-specific implementation | Users of specific tools |
| Playbooks | Operational procedures | Security practitioners |

---

## Scope and applicability

### In scope

This policy applies to the following categories.

| Category | Details |
|----------|---------|
| Tools | All AI coding assistants including GitHub Copilot, Amazon Q Developer, Amazon Kiro, Cursor, Windsurf, Devin, Claude Code, Claude.ai, Gemini Code Assist, GitLab Duo, JetBrains AI Assistant, self-hosted LLM solutions |
| Personnel | Civil servants, contractors, and suppliers with access to government code repositories or development environments |
| Environments | Development, test, staging, and production-adjacent environments |
| Data | All data classifications up to OFFICIAL-SENSITIVE (with appropriate controls) |

### Out of scope

| Category | Notes |
|----------|-------|
| Non-coding AI systems | Covered by separate AI governance policies |
| SECRET and above | Requires separate policy with enhanced controls |
| Isolated research sandboxes | Where no government data is present and no connection to government systems exists |

---

## Alignment with UK government frameworks

This policy aligns with and supports compliance with the following frameworks.

| Framework | Alignment |
|-----------|-----------|
| UK AI Playbook for government (2025) | Supports all 10 principles, particularly Principles 3, 4, and 10 |
| NCSC Guidelines for Secure AI System Development | Implements secure design, development, deployment, and operation phases |
| NCSC Machine Learning Security Principles | Addresses all 5 lifecycle phases |
| Government Security Classifications | Enforces classification boundaries |
| Technology Code of Practice | Supports secure development and operation requirements |
| Cyber Essentials | Baseline security requirements apply |

---

## Roles and responsibilities

### Senior responsible owner (SRO)

The SRO is accountable for the AI coding assistant adoption programme.

Responsibilities include:

- approving the AI coding assistant adoption strategy
- ensuring adequate resourcing for security controls
- reporting to governance boards on adoption progress and risks
- escalating critical risks to departmental leadership

### Senior information risk owner (SIRO)

The SIRO is accountable for information risk arising from AI coding assistant use.

Responsibilities include:

- approving deployment of L5 (fully autonomous) AI tools
- accepting residual risk after controls are applied
- approving exceptions to this policy
- ensuring risk register includes AI-related risks

### AI security lead

The AI Security Lead provides day-to-day security oversight.

Responsibilities include:

- maintaining this policy and associated guardrails
- conducting security assessments of new AI tools
- interpreting policy requirements for specific situations
- managing the approved tools list
- reviewing security incidents involving AI tools
- reporting security metrics to SIRO

### Development team leads

Team leads ensure their teams comply with this policy.

Responsibilities include:

- verifying team members have completed required training
- implementing guardrails in team workflows
- reviewing AI-generated code before merge
- escalating security incidents
- maintaining team-level risk awareness

### Individual Users

All users of AI coding assistants must comply with this policy.

Responsibilities include:

- completing mandatory training before using AI tools
- following guardrails and tool-specific guidance
- reviewing all AI-generated code before committing
- reporting security incidents promptly
- maintaining awareness of data classification requirements

---

## Policy statements

### PS-01: tool approval required

**Statement:** AI coding assistants must be approved before use on government projects.

**Requirements:**

| Requirement | Details |
|-------------|---------|
| Security assessment | Tool must be assessed against this policy and threat model |
| Data protection | DPIA required where personal data may be processed |
| Vendor assessment | Supplier must meet government vendor security requirements |
| Configuration | Tool must be configurable to meet guardrails |
| Audit capability | Tool must provide adequate logging for accountability |

**Authority:** AI Security Lead approves tools; SIRO approves L5 autonomous tools.

**Reference:** UK AI Playbook Principle 6 (Right tool for the job)

---

### PS-02: data classification compliance

**Statement:** AI coding assistants must only be used with data appropriate to their accreditation level.

**Requirements:**

| Classification | Requirement |
|----------------|-------------|
| OFFICIAL | Permitted with standard controls (guardrails-base) |
| OFFICIAL-SENSITIVE | Permitted only with enterprise licence providing enhanced controls, and tool-specific accreditation |
| SECRET | Not permitted with any current AI coding assistant |
| TOP SECRET | Not permitted with any current AI coding assistant |

**Prohibited data types (regardless of classification):**

- authentication credentials, API keys, tokens, certificates
- personal data (PII) unless anonymised
- security configurations (firewall rules, WAF configs)
- active case or investigation data
- export-controlled content

**Controls:** G-DH-01 through G-DH-05

**Reference:** Government Security Classifications, NCSC Cloud Security Principles

---

### PS-03: mandatory human oversight

**Statement:** AI-generated code must be reviewed by a human before deployment.

**Requirements:**

| Autonomy level (L) | Human oversight requirement |
|----------------|----------------------------|
| L1 to L2 (Suggestive/Assistive) | Human accepts each suggestion, review before commit |
| L3 (Collaborative) | Human review at checkpoints, review before merge |
| L4 (Autonomous) | Human review at checkpoints and time intervals, review before merge |
| L5 (Fully Autonomous) | Continuous monitoring capability, dual-approval for merge |

Meaningful review means the reviewer:

- understands what the code does
- has verified no obvious security issues
- has confirmed tests pass and are meaningful
- has verified compliance with coding standards

Rubber-stamping of AI output does not constitute meaningful review.

**Controls:** G-CS-01, G-AG-06, G-AG-07

**Reference:** UK AI Playbook Principle 4 (Human control at the right stage), NCSC ML Security Principles 1.2

---

### PS-04: secure development integration

**Statement:** AI-generated code must pass through the same security controls as human-written code.

**Requirements:**

| Control type | Requirement |
|--------------|-------------|
| Static analysis (SAST) | Mandatory before merge |
| Dependency scanning | Mandatory before merge |
| Secret detection | Mandatory (pre-commit hook preferred) |
| Dynamic analysis (DAST) | Where applicable, before production deployment |
| Container scanning | Where applicable, before deployment |

AI-generated code must not bypass security gates. The origin of code (human or AI) does not exempt it from security requirements.

**Controls:** G-CS-02

**Reference:** NCSC Secure Development and Deployment, OWASP Secure Coding Practices

---

### PS-05: agentic AI governance

**Statement:** AI tools with autonomous capabilities must be governed proportionate to their autonomy level.

**Requirements:**

| Autonomy level (L)| Governance requirement |
|----------------|----------------------|
| L1 to L2 | Standard guardrails apply |
| L3 | Checkpoint controls, branch isolation recommended |
| L4 | Checkpoint controls, time limits, kill switch required, branch isolation required |
| L5 | SIRO approval required, security assessment required, enhanced monitoring, dual-approval for output |

L5 tools are not approved for general use without explicit SIRO approval and dedicated security assessment.

**Controls:** G-AG-01 through G-AG-08

**Reference:** UK AI Playbook Principle 4, Anthropic Responsible Scaling Policy, OWASP Agentic AI Threats

---

### PS-06: training requirements

**Statement:** personnel must complete AI security training before using AI coding assistants.

**Requirements:**

| Training | Audience | Frequency |
|----------|----------|-----------|
| AI coding assistant security awareness | All users | Before first use, then annually |
| Prompt injection awareness | All users | Before first use |
| Tool-specific training | Users of specific tools | Before using that tool |
| Agentic AI security | Users of L4-L5 tools | Before using agentic features |
| Security lead training | AI Security Leads | Before assuming role, then annually |

Training completion must be recorded and verifiable.

**Reference:** UK AI Playbook Principle 9 (Skills and expertise), NCSC ML Security Principles 1.1

---

### PS-07: incident reporting

**Statement:** security incidents involving AI coding assistants must be reported promptly.

**Requirements:**

| Incident type | Reporting timeframe | Report to |
|---------------|--------------------|-----------| 
| Data breach (credentials, PII, classified) | Immediately | Security team, then SIRO |
| Suspected prompt injection | Within 4 hours | AI Security Lead |
| Unexpected autonomous action | Immediately (after kill switch) | AI Security Lead |
| Vulnerability in AI-generated code | Within 24 hours | Security team |
| Near-miss events | Within 48 hours | AI Security Lead |

**The response must:**

- follow [Incident Response Playbook](../governance/incident-response-playbook.md)
- preserve evidence (do not delete AI output)
- document timeline and actions taken

**Reference:** NCSC Incident Management, NCSC ML Security Principles 4.3

---

### PS-08: audit and accountability

**Statement:** AI coding assistant usage must be auditable.

**Requirements:**

| Requirement | Details |
|-------------|---------|
| Usage logging | Tools must log who used them, when, and for what purpose |
| Code attribution | AI-generated code should be identifiable in version control |
| Prompt retention | Organisations should consider prompt logging (balancing privacy) |
| Audit access | Security teams must have access to logs |
| Retention period | Logs retained per organisational retention policy (minimum 12 months recommended) |

**Sensitive data in logs:**

Logs themselves must not contain sensitive data. Prompt logging must be balanced against data protection requirements.

**Controls:** G-MA-01, G-MA-02

**Reference:** UK AI Playbook Principle 10 (Organisational policies and assurance), NCSC ML Security Principles 3.2

---

### PS-09: third-party and supply chain

**Statement:** AI coding assistant supply chains must be assessed and managed.

**Requirements:**

| Requirement | Details |
|-------------|---------|
| Vendor assessment | AI providers must meet government supplier security requirements |
| Approved model sources | Only approved model providers may be used |
| Dependency verification | AI-suggested dependencies must be verified before use |
| Contract requirements | Contracts must address data handling, security, and exit provisions |
| Exit strategy | Plans must exist for tool discontinuation |

**Controls:** G-CS-03

**Reference:** UK AI Playbook Principle 8 (Commercial considerations), NCSC Supply Chain Security, NCSC ML Security Principles 2.1

---

### PS-10: continuous improvement

**Statement:** this policy and associated controls must be continuously improved.

**Requirements:**

| Activity | Frequency | Owner |
|----------|-----------|-------|
| Policy review | Annually (minimum) | AI Security Lead |
| Threat model update | Quarterly, or when new threats emerge | AI Security Lead |
| Guardrails review | Quarterly | AI Security Lead |
| Lessons learned review | After significant incidents | AI Security Lead |
| Corpus update monitoring | Monthly | AI Security Lead |

**Triggers for immediate review include:**

- major security incident involving AI tools
- new NCSC or UK Government guidance
- significant new threat disclosed (e.g., new prompt injection technique)
- major new tool capability (e.g., new autonomy features)

**Reference:** UK AI Playbook Principle 7 (Open and collaborative), NCSC ML Security Principles 5.2

---

### PS-11: tool-type specific requirements

**Statement:** Different types of AI coding assistants have specific security requirements appropriate to their architecture and risk profile.

This policy recognises four distinct tool categories, each with unique security considerations.

---

#### 11.1 Cloud-hosted AI assistants

**Tools in category:** GitHub Copilot, Amazon Q Developer, Gemini Code Assist, Claude.ai

**Architecture:** code context sent to external cloud provider for inference; suggestions returned to IDE.

**Requirements:**

| Requirement | Details |
|-------------|---------|
| Licensing | Enterprise licence required for OFFICIAL-SENSITIVE data |
| Data residency | EU/UK regions only for government data; must be contractually specified |
| Deployment patterns | Standard SaaS (OFFICIAL only), VPC/Private network (OFFICIAL-SENSITIVE with approval) |
| Authentication | SSO integration mandatory for teams >10 users; MFA enforced |
| API controls | Rate limits and quotas configured to prevent abuse |
| Monitoring | Usage analytics enabled for compliance and security monitoring |
| Data retention | Provider data retention policies reviewed and approved |

**Tool specific notes**

GitHub Copilot must have:
  - enterprise cloud or GitHub Enterprise Server required for government
  - business plan not sufficient for OFFICIAL-SENSITIVE
  - code referencing feature enabled to identify public code matches
  - content exclusions configured for sensitive repositories
  
Amazon Q Developer must have:
  - AWS Bedrock backend (not SaaS endpoint)
  - AWS region restricted to UK (eu-west-2) or approved EU regions
  - IAM policies enforce least privilege access
  - CloudTrail logging mandatory
  
Gemini Code Assist must have:
  - Vertex AI (not consumer Google AI)
  - data residency controls configured for EU/UK
  - cloud logging enabled
  - Duet AI enterprise features only
  
- Claude.ai must have:
  - enterprise plan required (not Pro or Free)
  - data retention controls configured (no training on prompts)
  - usage tracked via API keys per team

**Primary threats:** T-DE-01, T-CH-01, T-CH-02, T-SC-02

**Key controls:** G-DH-01-05, PS-09, PS-11

---

#### 11.2 IDE-integrated agents

**Tools in category:** Cursor, Windsurf, GitHub Copilot (IDE extension), Amazon Kiro, Claude Code

**Architecture:** hybrid model with local context processing and selective cloud API calls; may include local caching/indexing.

**Requirements:**

| Requirement | Details |
|-------------|---------|
| IDE security baseline | IDE must meet minimum security requirements (patching, authentication) |
| Extension vetting | All IDE extensions undergo security review before approval |
| Context isolation | Per-project context isolation; no cross-project leakage |
| Local cache security | Encrypted storage for local cache/index data |
| Network controls | All cloud communication via approved corporate proxy/VPN |
| Audit logging | IDE-level logging where available (VS Code audit logs, etc.) |

**Extension vetting process:**

| Extension type | Review requirement |
|----------------|-------------------|
| Open-source | Source code security review; supply chain assessment |
| Closed-source | Vendor security questionnaire; SOC 2 / ISO 27001 certification |
| Official tool extensions | Standard vendor assessment (PS-09) |
| Third-party extensions | Enhanced scrutiny; SIRO approval for OFFICIAL-SENSITIVE use |

**Tool specific notes**

Cursor must have:
  - team plan required for government use
  - SOC 2 Type II compliance verified annually
  - privacy mode enabled (local processing preference)
  - Cursor Rules feature reviewed for security implications
  - local indexing cache encrypted at rest
  
Windsurf must have:
  - Cascade (agentic) mode requires L4 controls
  - privacy mode mandatory for government use
  - no telemetry to Codeium servers
  - context window limits enforced
  
GitHub Copilot (IDE extension) must have:
  - managed through GitHub Enterprise and extension updates controlled
  - telemetry settings reviewed and configured
  - offline mode not available (requires connectivity)
  
Amazon Kiro must have:
  - AWS CLI v2.15+ required
  - MFA mandatory for AWS authentication
  - IAM roles used (not access keys)
  - steering files security-reviewed before use
  - agent hooks disabled by default; require approval per use
  
Claude Code must have:
  - no persistent context between sessions
  - tool use requires explicit approval per tool
  - filesystem access scoped to project directory only

**Primary threats:** T-DE-01, T-DE-03, T-IDE-01, T-IDE-02, T-PI-02

**Key controls:** G-DH-05, G-CS-03, PS-11, full disk encryption

---

#### 11.3 autonomous agents

**Tools in category:** Devin, Amazon Kiro (frontier agent mode), Claude Code (agentic mode with extended permissions)

**Architecture:** extended autonomous operation; can execute multi-step tasks, run tests, create branches, and interact with external systems over minutes to hours.

**Requirements (beyond L4/L5 controls in G-AG-XX):**

| Requirement | Details |
|-------------|---------|
| Security assessment | Dedicated security assessment required per deployment |
| Sandbox mandatory | Isolated environment required for all autonomous operations |
| SIRO approval | Required for L5 tools (Devin, Kiro frontier mode) |
| Kill switch testing | Tested before every extended session (>30 min) |
| Dual-approval | All generated pull requests require two human approvers |
| Security standby | Security team available during extended L5 sessions |
| Post-session review | Security review of all actions after session completion |
| Incident response | Pre-approved incident response plan specific to tool |

**Sandbox environment requirements:**

| Component | Requirement |
|-----------|-------------|
| Isolation | Separate cloud account/project; no production access |
| Network | Network isolated from production; internet access restricted to allowlist |
| Credentials | No production credentials; dev/test credentials only; time-limited |
| Resources | Resource limits enforced (compute, storage, API call quotas) |
| Monitoring | Enhanced logging and monitoring; real-time alerts |
| Data | Clone of production data (anonymised); or synthetic data only |

**Tool specific notes:**

Devin must have:
  - dedicated tenant (not shared infrastructure)
  - not permitted on shared development infrastructure
  - must operate in fully isolated sandbox
  - session time limit: 2 hours maximum before mandatory review
  - dual-approval mandatory for all PRs
  - security team on-call during operation
  - comprehensive logging of all actions to immutable log store
  
Amazon Kiro (frontier agent mode) must have:
  - steering files must be security-reviewed before use
  - agent hooks reviewed and approved per session
  - spec-driven mode preferred over vibe-driven mode
  - multi-model routing: only approved models may be used
  - AWS resource tagging for cost tracking and kill switch
  - CloudWatch alarms for unexpected API usage
  
Claude Code (agentic mode with extended permissions) must have:
  - tool permissions explicitly granted per session
  - filesystem access scoped and logged
  - network access logged and restricted
  - extended thinking operations monitored for loops
  - session recording for audit purposes

**Primary threats:** T-AG-01, T-AG-02, T-AG-03, T-AG-04, T-PI-02, T-AV-02

**Key controls:** G-AG-01-08, PS-05, Sandbox architecture, Kill switch, Dual-approval

---

#### 11.4 self-hosted solutions

**Tools in category:** Local LLM deployments, Ollama, LocalAI, LM Studio, private model hosting, air-gapped deployments

**Architecture:** model and inference engine hosted on government-controlled infrastructure. No external API calls.

**Requirements:**

| Category | Details |
|----------|---------|
| Infrastructure baseline | Dedicated compute; encrypted storage; network isolation where appropriate |
| Model provenance | Models from approved sources only; cryptographic verification |
| Supply chain | ML-BOM (Machine Learning Bill of Materials) required |
| Update management | Regular model and infrastructure updates; vulnerability scanning |
| Access controls | Least privilege; MFA where applicable |
| Monitoring | Local logging and monitoring; no external telemetry |

**Infrastructure baseline requirements:**

| Component | Requirement |
|-----------|-------------|
| Compute | Dedicated infrastructure; not shared with other workloads |
| Storage | Encrypted at rest (model files, cache, logs) |
| Network | Isolated VLAN or air-gapped as appropriate to data classification |
| Operating system | Hardened OS; CIS benchmarks applied; regular patching |
| Access | Bastion/jump host for administrative access; MFA required |

**Model provenance requirements:**

| Requirement | Details |
|-------------|---------|
| Approved sources | Hugging Face (verified publishers), vendor official repos, approved academic sources |
| Verification | SHA-256 hash verification of model files against published hashes |
| License review | Model license compatible with government use |
| Supply chain | Document model training data sources, fine-tuning data if applicable |
| ML-BOM | Machine Learning Bill of Materials documenting all components |
| Security audit | For models used with OFFICIAL-SENSITIVE: security audit of model origin |

**Update management:**

| Component | Frequency | Process |
|-----------|-----------|---------|
| Model updates | Per vendor release schedule | Hash verification; changelog review; regression testing |
| Inference engine | Monthly (or when CVE published) | Vulnerability scanning; patch testing; rollback plan |
| Operating system | Monthly | Standard patching process; inference engine compatibility verified |
| Dependencies | Monthly | Dependency scanning; vulnerability assessment |

**Air-gap deployment additional requirements:**

| Requirement | Details |
|-------------|---------|
| Physical isolation | Network physically disconnected; no wireless |
| Model transfer | Via approved removable media process; virus scanning; hash verification |
| No telemetry | All telemetry, update checks, and external connections disabled |
| Local logging | All logging to local syslog; no external log shipping |
| Documentation | Air-gap compliance verification documented quarterly |
| Maintenance | Scheduled maintenance windows for physical media transfers |

**Approved self-hosted model sources:**

*(To be defined per department risk appetite; examples below)*

| Source | Trust Level | Use Cases |
|--------|-------------|-----------|
| Vendor official (OpenAI, Anthropic, etc.) | High | General use if licensed |
| Hugging Face (verified publishers) | Medium-High | Open-source models |
| Meta Llama official releases | High | Open-source, community vetted |
| Mistral official releases | High | Open-source, commercial options |
| Academic (after review) | Medium | Research, experimentation |

**Prohibited self-hosted scenarios include:**

- models from unknown or unverified sources
- models without license verification
- fine-tuning on unvetted training data
- internet-connected "self-hosted" without network controls

**Tool specific notes**

Ollama must have:
  - model library restricted to approved models
  - version pinning enforced (no automatic updates)
  - API access restricted to localhost or authorized IPs
  - resource limits configured (CPU, memory, GPU)
  
LocalAI / LM Studio must have:
  - model path restricted to approved directory
  - no model download from tool (manual verification required)
  - API endpoint authentication enabled
  - logging configured to central syslog

**Primary threats:** T-SA-01, T-SA-02, T-SA-03, T-SA-04, T-CS-01

**Key controls:** PS-11 (provenance), G-CS-02 (scanning), Infrastructure hardening, Air-gap controls

---

## Compliance and assurance

### Compliance verification

| Method | Frequency | Scope |
|--------|-----------|-------|
| Self-assessment | Quarterly | All teams using AI tools |
| Spot checks | Ad hoc | Random sample of teams |
| Security review | Annually | Full programme review |
| Internal audit | As scheduled | Per audit programme |
| External audit | As required | Per contractual or regulatory requirements |

### Self-assessment checklist

Teams should verify:

- [ ] all team members have completed required training
- [ ] approved tools only are in use
- [ ] security scanning is integrated in CI/CD pipeline
- [ ] code review process includes AI-generated code verification
- [ ] incident reporting channels are known and accessible
- [ ] department-specific guardrails are documented (if applicable)
- [ ] tool-type specific requirements met (PS-11)

### Non-compliance

| Severity | Examples | Response |
|----------|----------|----------|
| Minor | Training not current, documentation gaps | Corrective action within 30 days |
| Moderate | Guardrails not fully implemented, delayed incident reporting | Escalation to Team Lead, corrective action within 14 days |
| Major | Prohibited data shared with AI, L5 tool used without approval | Escalation to SIRO, immediate remediation, potential access suspension |
| Critical | Data breach, security incident with significant impact | Escalation to SRO, incident response activation, formal investigation |

---

## Exceptions process

### When exceptions may be granted

Exceptions may be considered when:

- business requirement cannot be met within policy constraints
- risk is understood, documented, and accepted
- compensating controls are in place
- exception is time-limited

Exceptions should not be granted for:

- circumventing security controls for convenience
- using unapproved tools without assessment
- handling SECRET or above data with AI tools
- bypassing mandatory human review

### Exception authority

| Exception type | Authority | Duration |
|---------------|-----------|----------|
| Temporary operational | AI Security Lead | Up to 30 days |
| Extended operational | SIRO | Up to 12 months |
| L5 tool deployment | SIRO | Per deployment, requires security assessment |
| Policy deviation | SIRO | Up to 12 months, requires risk acceptance |

### Exception documentation

All exceptions must be documented with:

- business justification
- risk assessment
- compensating controls
- time limit and review date
- approval authority signature
- risk acceptance statement

Exceptions must be recorded in the risk register.

---

## Policy review and maintenance

| Activity | Frequency | Owner |
|----------|-----------|-------|
| Full policy review | Annually | AI Security Lead, approved by SIRO |
| Minor updates (references, clarifications) | As needed | AI Security Lead |
| Emergency updates (new threats) | Immediately | AI Security Lead, ratified by SIRO |

### Change control

| Change type | Approval |
|-------------|----------|
| Editorial (typos, formatting) | AI Security Lead |
| Minor (clarifications, reference updates) | AI Security Lead |
| Moderate (new controls, process changes) | SIRO |
| Major (scope changes, new policy statements) | SRO |

---

## Related documents

### Governance

- [threat model](threat-modelling.md) - Risk assessment and threat catalogue
- [guardrails base](../governance/guardrails-base.md) - Technical control implementation

### Operational

- [incident response playbook](../governance/incident-response-playbook.md) - incident handling

---

## References

### UK Government (tier 1)

- [UK AI Playbook for Government (2025)](https://www.gov.uk/government/publications/ai-playbook-for-the-uk-government/artificial-intelligence-playbook-for-the-uk-government-html)
- [NCSC Guidelines for Secure AI System Development](https://www.ncsc.gov.uk/collection/guidelines-secure-ai-system-development)
- [NCSC Principles for the Security of Machine Learning](https://www.ncsc.gov.uk/files/Principles-for-the-security-of-machine-learning.pdf)
- [NCSC Cloud Security Principles](https://www.ncsc.gov.uk/collection/cloud-security)
- [NCSC Secure Development and Deployment](https://www.ncsc.gov.uk/collection/developers-collection)
- [Government Security Classifications](https://www.gov.uk/government/publications/government-security-classifications)
- [Technology Code of Practice](https://www.gov.uk/guidance/the-technology-code-of-practice)
- [Cyber Essentials Scheme](https://www.ncsc.gov.uk/cyberessentials/overview)

### Standards (tier 3)

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ISO/IEC 42001:2023 AI Management System](https://www.iso.org/standard/81230.html)
- [OWASP LLM Top 10 (2025)](https://genai.owasp.org/llm-top-10/)
- [OWASP Agentic AI Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/)
- [MITRE ATLAS](https://atlas.mitre.org/)

### Vendor (tier 4)

- [Anthropic Responsible Scaling Policy](https://www.anthropic.com/news/anthropics-responsible-scaling-policy)
- [GitHub Copilot Trust Center](https://resources.github.com/copilot-trust-center/)

---

## Document control

| Field | Value |
|-------|-------|
| Version | 1.0.0 |
| Status | Draft |
| Classification | OFFICIAL |
| Owner | AI Security Lead |
| Approved by | [SIRO - pending] |
| Created | 2026-02-05 |
| Updated | 2026-02-10 |
| Review date | 2027-02-09 |

### Version history

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1.0 | 2026-02-05 | AI Security Lead | Initial draft |
| 1.0.0 | 2026-02-09 | AI Security Lead | Added PS-11 comprehensive tool-type requirements covering all 4 categories |
| 1.0.1 | 2026-02-10 | AI Security Lead | Applied GDS style guide formatting: bullet points start with lower case |
