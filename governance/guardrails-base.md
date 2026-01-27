> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# AI Engineering Lab guardrails - base configuration

> Baseline security and usage boundaries for AI Engineering Lab deployments across government.

## Purpose

This document defines the foundational guardrails that apply to all AI Engineering Lab deployments. These guardrails protect government systems, data, and intellectual property while enabling productive use of AI tools.

Departments should use this as a starting point and create department-specific variants where additional controls are required. See [Creating department-specific guardrails](#creating-department-specific-guardrails) for guidance.

## Who this applies to

These guardrails apply to all personnel using AI coding assistants on government projects, including civil servants, contractors, and suppliers with access to government code repositories or development environments.

## In this document

Use the links below to navigate to each guardrail category:

| Category | Purpose |
|----------|---------|
| [Data handling](#data-handling-guardrails) | what can and cannot be shared with AI tools |
| [Code security](#code-security-guardrails) | securing AI-generated code |
| [Usage boundaries](#usage-boundary-guardrails) | where AI assistants should not be used |
| [Output validation](#output-validation-guardrails) | verifying AI-generated content |
| [Monitoring and audit](#monitoring-and-audit-guardrails) | tracking and accountability |

---

## Data handling guardrails

### G-DH-01: Data classification limits

AI coding assistants must only be used with data classified at OFFICIAL or below, unless the specific tool has been accredited for higher classifications.

| Classification | AI assistant usage |
|----------------|-------------------|
| OFFICIAL | permitted with standard controls |
| OFFICIAL-SENSITIVE | permitted with enhanced controls and tool-specific accreditation |
| SECRET | not permitted |
| TOP SECRET | not permitted |

Cloud-based AI assistants transmit data to external servers. Organisations handling OFFICIAL-SENSITIVE data must assess whether their AI tool's enterprise licence provides adequate security controls (such as data residency, encryption, access controls, and audit logging) and ensure deployment aligns with the Government Security Policy Framework and NCSC cloud security principles.

### G-DH-02: Prohibited data types

The following data types must never be included in prompts, code comments, or context provided to AI assistants:

| Prohibited data | Examples |
|-----------------|----------|
| personal data (PII) | names, addresses, NI numbers, dates of birth |
| authentication credentials | API keys, passwords, tokens, certificates |
| security configurations | firewall rules, security group configs, WAF rules |
| classified information | information marked above OFFICIAL |
| protected operational data | case details, investigation information, intelligence |
| financial account data | bank details, payment card numbers |
| health information | medical records, health identifiers |
| biometric data | fingerprints, facial recognition data |
| case or investigation data | active case details, investigation notes, suspect information |
| critical IP or algorithms | proprietary algorithms identified during assessment stage |
| export-controlled content | code subject to ITAR, EAR, or UK export controls |

If prohibited data is accidentally shared with an AI tool, report immediately through your department's security incident process and refer to the [Incident Response Playbook](incident-response-playbook.md).

### G-DH-03: Code repository restrictions

Before using AI assistants with code from a repository, verify the following:

1. The repository does not contain embedded secrets or credentials.
2. The repository does not contain data above OFFICIAL classification.
3. The repository is not subject to export control restrictions.
4. You have authorisation to share the code with third-party services.

### G-DH-04: Prompt hygiene

When crafting prompts, you should use anonymised or synthetic data in examples, and avoid exposing real system architecture or security-relevant patterns. Specific actions include:

- replace real identifiers with placeholders (for example, `USER_ID_123`, `example@gov.uk`)
- strip comments containing sensitive context before sharing code
- avoid referencing specific system names, IP addresses, or internal URLs

**Example - before (problematic):**
```python
# Connects to the case management API at https://internal-api.department.gov.uk:8443
# Uses service account: svc_case_processor / Password: CaseProc2024!
# Contact John Smith (john.smith@department.gov.uk) if issues
def get_case_details(case_id):
    ...
```

**Example - after (safe):**
```python
# Connects to case management API
# Uses service account credentials from environment
def get_case_details(case_id):
    ...
```

### G-DH-05: Context window awareness

AI assistants may retain context within a session. You must take the following actions:

- start new sessions when switching between projects with different classification levels
- not assume previous prompts are forgotten within a session
- clear context explicitly when available in the tool
- avoid mixing work across multiple departments in a single session

---

## Code security guardrails

### G-CS-01: Mandatory human review

All AI-generated code must be reviewed by a qualified human before taking any of the following actions:

- committing to a shared repository
- deploying to any environment (including development)
- using in security-sensitive functions

The minimum review scope should include:

| Check | Description |
|-------|-------------|
| logic correctness | does the code do what was intended? |
| security vulnerabilities | SQL injection, XSS, path traversal and similar |
| dependency safety | are suggested packages from trusted sources? |
| credential exposure | no hardcoded secrets or credentials? |
| licence compliance | compatible with project licensing? |

### G-CS-02: Security scanning requirements

AI-generated code must pass through the same security tooling as human-written code:

| Tool type | Requirement | Timing |
|-----------|-------------|--------|
| SAST (static analysis) | mandatory | pre-commit or CI pipeline |
| dependency scanning | mandatory | pre-commit or CI pipeline |
| secret detection | mandatory | pre-commit hook |
| DAST (dynamic analysis) | where applicable | pre-deployment |
| container scanning | where applicable | pre-deployment |

Do not bypass security scanning because code was AI-generated. AI-generated code may contain vulnerabilities that automated tools can detect.

### G-CS-03: Dependency verification

When AI assistants suggest external packages or libraries, you should take the following steps:

1. Verify the package exists and is actively maintained.
2. Check the package source (prefer official repositories).
3. Review the package's security history.
4. Confirm licence compatibility.
5. Check for known vulnerabilities in the suggested version.

Warning signs to look out for include:

- packages with very few downloads or stars
- packages not updated in over 12 months
- packages with known CVEs in suggested version
- packages from unofficial or mirrored repositories

### G-CS-04: No AI in cryptographic implementations

Do not use AI assistants to perform the following tasks:

- implement cryptographic algorithms
- generate cryptographic keys
- design authentication or authorisation logic
- create security token handling code

Cryptographic code requires specialist knowledge. Subtle errors can create severe vulnerabilities that may not be detected by standard testing.

Instead, use established, audited libraries and follow NCSC guidance on cryptographic implementations.

### G-CS-05: Prompt injection awareness

AI-generated code may be vulnerable to prompt injection if it processes user input that is later sent to AI systems.

When building systems that use AI, you should take the following precautions:

- sanitise all user input before including in prompts
- use parameterised prompts where possible
- implement input length limits
- monitor for unusual prompt patterns

---

## Usage boundary guardrails

### G-UB-01: Prohibited use cases

AI code assistants must not be used for the following purposes:

| Prohibited use | Rationale |
|----------------|-----------|
| security-critical system core logic | requires specialist security review |
| safety-critical systems | life-safety implications require formal methods |
| cryptographic implementations | see [G-CS-04](#g-cs-04-no-ai-in-cryptographic-implementations) |
| systems handling SECRET or above data | classification restrictions |
| generating malicious code or exploits | ethical and legal restrictions |
| circumventing security controls | violation of security policy |
| air-gapped or isolated environments | network connectivity restrictions |

### G-UB-02: Appropriate use cases

AI code assistants are well-suited for the following purposes:

| Appropriate use | Notes |
|-----------------|-------|
| boilerplate code generation | tests, CRUD operations, data models |
| code explanation and documentation | understanding legacy code |
| refactoring suggestions | improving code structure |
| test case generation | unit tests, integration tests |
| learning and exploration | understanding new frameworks |
| code review assistance | secondary review, not replacement |
| prototyping and proofs of concept | rapid iteration, non-production |

### G-UB-03: Tool-specific boundaries

Some AI assistants have specific restrictions based on their accreditation status:

| Tool | Current status | Restrictions |
|------|----------------|--------------|
| GitHub Copilot Enterprise | to be confirmed | to be confirmed |
| Claude Code | to be confirmed | to be confirmed |
| Amazon Q Engineer | to be confirmed | to be confirmed |
| Gemini Code Assist | to be confirmed | to be confirmed |

Check with your department's security team for current accreditation status before deployment.

### G-UB-04: Environment restrictions

| Environment | AI assistant usage |
|-------------|-------------------|
| local development | permitted |
| cloud development environments | permitted with approved tools |
| CI/CD pipelines | requires security review |
| production environments | not permitted for real-time code generation |
| air-gapped networks | not permitted (no connectivity) |
| secure enclaves | not permitted without specific accreditation |

### G-UB-05: Agentic AI and autonomous features

Agentic AI refers to AI models that can execute multi-step tasks autonomously, interact with external systems, or take actions without human approval at each step. This includes background agents, Bugbot, computer-using agents (CUAs), and similar capabilities.

Agentic AI features (for example, autonomous development assistants or background agents) may be used for development tasks under controlled conditions, operating within defined task boundaries and subject to interruption, but require additional oversight.

#### Permitted uses (with standard controls)

| Feature type | Status | Notes |
|--------------|--------|-------|
| code completion and suggestions | permitted | standard review applies |
| chat-based assistance | permitted | standard review applies |
| automated code review suggestions | permitted | human decision on actions |
| agent-assisted scaffolding | permitted | review output before use |
| agent-assisted test generation | permitted | review and validate tests |
| background agents for refactoring | permitted with approval | requires team lead approval, review all changes |

#### Restricted uses (require security lead approval)

| Feature type | Status | Approval required |
|--------------|--------|-------------------|
| agents creating repositories | restricted | team lead and security lead |
| agents with file system write access | restricted | security lead |
| agents executing shell commands | restricted | security lead |
| agents interacting with external APIs | restricted | security lead |

#### Prohibited uses

| Feature type | Status | Rationale |
|--------------|--------|-----------|
| autonomous access to production systems | prohibited | unacceptable risk |
| agents with access to credentials or secrets | prohibited | security risk |
| computer use or screen control on government systems | prohibited | accountability and audit gaps |
| unattended task execution without human checkpoints | prohibited | lack of oversight |
| agents granted access to government accounts | prohibited | authentication and authorisation bypass |

The programme supports controlled experimentation with agentic features for productivity gains (evidence shows 10% to 25% efficiency improvements in brownfield modernisation). However, autonomous access to government systems creates accountability gaps and unacceptable security risks, including the potential for indirect privilege escalation where combinations of otherwise permitted tools or actions could result in restricted outcomes.

For experimentation with restricted features, take the following steps:

1. Document the use case and expected benefits.
2. Identify specific controls and human checkpoints.
3. Obtain security lead approval before use.
4. Conduct in isolated or sandboxed environments where possible.
5. Log all agent actions for audit purposes.
6. Review and commit all outputs manually.

---

## Output validation guardrails

### G-OV-01: Factual verification

AI assistants may generate plausible but incorrect information. Always verify the following:

- API signatures and method names against official documentation
- configuration syntax against current tool versions
- security recommendations against NCSC or vendor guidance
- regulatory claims against authoritative sources

### G-OV-02: Code functionality testing

All AI-generated code must be tested before use:

| Test type | Requirement |
|-----------|-------------|
| unit tests | mandatory for all generated functions |
| integration tests | required when interacting with other systems |
| edge case testing | required for input validation logic |
| security testing | required for authentication or authorisation code |

Do not assume AI-generated code is correct because it looks reasonable or compiles successfully.

### G-OV-03: Licence compliance verification

AI-generated code may inadvertently reproduce licensed content. Before using generated code, take the following steps:

1. Review for unusual similarity to known open source projects.
2. Run through licence compliance tooling where available.
3. Document the AI tool used for provenance tracking.
4. Consult legal team if uncertain about licence implications.

### G-OV-04: Hallucination detection

Watch for common AI hallucination patterns:

| Pattern | Example | Action |
|---------|---------|--------|
| non-existent packages | `import gov_uk_utils` (does not exist) | verify package exists |
| fabricated APIs | `response.get_secure_data()` (not a real method) | check documentation |
| outdated syntax | deprecated method calls | verify against current version |
| invented configuration | non-existent config options | test in isolated environment |

---

## Ethical use guardrails

### G-ET-01: Ethical review triggers

Identify whether any teams work on systems that require additional ethical consideration:

| System type | Ethical review required | Review owner |
|-------------|------------------------|--------------|
| citizen-facing services | yes - document AI usage | department lead |
| decision-support systems | yes - assess impact on decisions | department lead and security lead |
| automated decision-making | yes - GDPR Article 22 assessment | department DPO |
| benefits or entitlements processing | yes - fairness review | department lead |
| law enforcement or justice systems | yes - legal and ethical review | department legal and security lead |
| healthcare or clinical systems | yes - clinical safety review | clinical safety officer |
| critical national infrastructure | yes - impact assessment | security lead |
| AI-assisted systems where outputs materially influence human decisions affecting individuals, even where final decisions remain human-made | yes - assess degree of reliance and impact | department lead and security lead |

During assessment, record which teams work on these system types in the security posture review. Flag for additional controls in department-specific guardrails.

### G-ET-02: Transparency and documentation

When AI code assistants are used in developing systems that affect citizens or public decisions, take the following actions:

1. Document AI involvement in technical records and architecture decision records.
2. Assess output bias risk particularly for systems processing citizen data.
3. Ensure human review of AI-generated code in citizen-facing logic paths.
4. Consider disclosure requirements based on department transparency policies.
5. Retain sufficient documentation and decision records to support audit, assurance, and post-hoc review.

Government has a responsibility to be transparent about how services are built. Departments should be able to answer questions about AI usage in service development.

### G-ET-03: Human judgment requirements

AI code assistants support but do not replace professional judgment. Human review must be informed and contextual, meaning reviewers understand the system's purpose, limitations, and potential impacts relevant to their decision. Final decisions must be made by qualified humans for the following areas:

| Area | Requirement |
|------|-------------|
| security architecture | security professional sign-off |
| legal or compliance logic | legal team review |
| clinical or safety-critical code | appropriate professional review |
| policy implementation | policy owner verification |
| accessibility compliance | accessibility specialist review |

AI may assist with research, drafting, code generation, test creation, and documentation. Humans must decide on architecture choices, compliance interpretations, policy implementation, and safety-critical logic.

### G-ET-04: Escalation for novel use cases

If a proposed use of AI code assistants raises ethical concerns not covered by these guardrails, take the following steps:

1. Raise with department lead and security lead.
2. Document the concern and proposed approach.
3. Escalate to programme governance if cross-department implications.
4. Do not proceed until guidance is provided.

Examples requiring escalation include AI-generated code for algorithmic decision-making about individuals, use in politically sensitive systems, and novel agentic AI applications not covered by G-UB-05.

Outcomes of escalations should be recorded to support consistent handling of similar novel use cases across teams.

---

## Monitoring and audit guardrails

### G-MA-01: Usage logging

Departments should maintain logs of AI assistant usage with the following elements:

| Log element | Purpose |
|-------------|---------|
| user identity | accountability |
| tool used | audit trail |
| timestamp | timeline reconstruction |
| project or repository | scope identification |

Do not log prompt content as it may contain sensitive information.

### G-MA-02: Telemetry configuration

Configure AI assistant telemetry settings according to department policy:

| Setting | Recommendation |
|---------|----------------|
| code snippet sharing | disable unless required and approved |
| prompt logging by vendor | understand vendor policy before enabling |
| usage analytics | enable for adoption metrics |
| error reporting | enable for support purposes |

Review vendor data handling policies and ensure they meet government requirements.

### G-MA-03: Incident reporting

Report the following to your security team:

- accidental exposure of classified or sensitive data
- AI-generated code that introduced a security vulnerability
- suspected prompt injection attempts
- unusual AI behaviour or responses suggesting compromise

Use existing security incident reporting channels. See [Incident Response Playbook](incident-response-playbook.md) for detailed procedures.

### G-MA-04: Periodic review

AI assistant usage should be reviewed according to the following schedule:

| Review | Frequency | Scope |
|--------|-----------|-------|
| usage metrics | monthly | adoption, active users, patterns |
| security incidents | monthly | AI-related incidents, near-misses |
| guardrails effectiveness | quarterly | policy compliance, gaps identified |
| tool accreditation | annually | continued suitability |

---

## Creating department-specific guardrails

This base configuration may be extended for department-specific requirements.

### Extension process

Follow these steps to create department-specific guardrails:

1. Start with this base - copy guardrails-base.md as your starting point.
2. Identify additional requirements - review with your security team.
3. Add department-specific controls - use the G-DEPT-XX numbering convention.
4. Do not weaken base controls - department guardrails must be equal or stricter.
5. Document rationale - explain why additional controls are needed.
6. Obtain approval - security lead sign-off before deployment.
7. Register with the AI Engineering Lab - submit to AI Engineering Lab repository for cross-government visibility.

### Common department extensions

| Department context | Typical additional controls |
|--------------------|-----------------------------|
| law enforcement | enhanced logging, additional prohibited data types |
| defence-adjacent | export control verification, nationality restrictions |
| healthcare | additional PII categories, clinical safety review |
| financial | PCI-DSS alignment, fraud prevention considerations |
| critical infrastructure | air-gap considerations, OT and IT boundary controls |

### Template for department extension

```markdown
---
title: AI Engineering Lab guardrails - [Department Name]
version: 0.1.0
extends: guardrails-base.md v0.1.0
status: Draft
owner: [Department Security Team]
classification: [OFFICIAL or OFFICIAL-SENSITIVE]
---

# Department-specific guardrails

## Additional controls

### G-DEPT-01: [Control name]
[Description]

Rationale: [Why this is needed for your department]

## Modified controls

### G-XX-XX: [Original control reference]
Base requirement: [Original text]
Department modification: [How it differs]
Rationale: [Why modification is needed]
```

---

## Checks before using AI coding assistants

### Self-assessment checklist

Before using AI code assistants, verify the following:

- [ ] I have completed AI code assistant training
- [ ] I understand the data classification of my project
- [ ] the tool I am using is approved for my department
- [ ] I know how to report security incidents
- [ ] I have reviewed department-specific guardrails (if any)

### Manager verification

Team leads should verify the following:

- [ ] all team members have completed training
- [ ] department-specific guardrails are documented and communicated
- [ ] security scanning is integrated into the development pipeline
- [ ] code review processes include AI-generated code verification
- [ ] incident reporting channels are established

---

## Related documents

- [Incident Response Playbook](incident-response-playbook.md) - security incident handling
- [Risk Register Template](risk-register-template.md) - risk documentation
- [AI-SDLC Playbook](../playbooks/ai-sdlc-playbook.md) - development lifecycle integration

## References

- [NCSC AI Security Guidance](https://www.ncsc.gov.uk/collection/ai)
- [NCSC Cloud Security Principles](https://www.ncsc.gov.uk/collection/cloud-security)
- [NCSC Secure Development Guidance](https://www.ncsc.gov.uk/collection/developers-collection)
- [Government Security Classifications](https://www.gov.uk/government/publications/government-security-classifications)
- [Technology Code of Practice](https://www.gov.uk/guidance/the-technology-code-of-practice)
- [OWASP Secure Coding Practices](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)
- [OWASP LLM Top 10](https://genai.owasp.org/llm-top-10/)
- [OWASP Agentic AI Threats](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/)

---