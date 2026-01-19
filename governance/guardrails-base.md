> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Guardrails - Base Configuration

> Baseline security and usage boundaries for AI Engineering Lab deployments across government.

## Purpose

This document defines the foundational guardrails that apply to all AI Engineering Lab deployments. These guardrails protect government systems, data, and intellectual property while enabling productive use of AI tools.

Departments should use this as a starting point and create department-specific variants where additional controls are required. See [Creating department-specific guardrails](#creating-department-specific-guardrails) for guidance.

## Who this applies to

These guardrails apply to all personnel using AI coding assistants on government projects, including civil servants, contractors, and suppliers with access to government code repositories or development environments.

## Guardrail categories

| Category | Purpose |
|----------|---------|
| [Data handling](#data-handling-guardrails) | What can and cannot be shared with AI tools |
| [Code security](#code-security-guardrails) | Securing AI-generated code |
| [Usage boundaries](#usage-boundary-guardrails) | Where AI assistants should not be used |
| [Output validation](#output-validation-guardrails) | Verifying AI-generated content |
| [Monitoring and audit](#monitoring-and-audit-guardrails) | Tracking and accountability |

---

## Data handling guardrails

### G-DH-01: Data classification limits

AI coding assistants must only be used with data classified at **OFFICIAL** or below, unless the specific tool has been accredited for higher classifications.

| Classification | AI Assistant Usage |
|----------------|-------------------|
| OFFICIAL | ✅ Permitted with standard controls |
| OFFICIAL-SENSITIVE | ⚠️ Permitted with enhanced controls and tool-specific accreditation |
| SECRET | ❌ Not permitted |
| TOP SECRET | ❌ Not permitted |

**Rationale:** Cloud-based AI assistants transmit data to external servers. Organisations handling OFFICIAL-SENSITIVE data must assess whether their AI tool's enterprise licence provides adequate security controls (such as data residency, encryption, access controls, and audit logging) and ensure deployment aligns with the Government Security Policy Framework and NCSC cloud security principles.

### G-DH-02: Prohibited data types

Never include the following in prompts, code comments, or context provided to AI assistants:

| Prohibited Data | Examples |
|-----------------|----------|
| Personal data (PII) | Names, addresses, NI numbers, dates of birth |
| Authentication credentials | API keys, passwords, tokens, certificates |
| Security configurations | Firewall rules, security group configs, WAF rules |
| Classified information | Information marked above OFFICIAL |
| Protected operational data | Case details, investigation information, intelligence |
| Financial account data | Bank details, payment card numbers |
| Health information | Medical records, health identifiers |
| Biometric data | Fingerprints, facial recognition data |

**Action if exposed:** If prohibited data is accidentally shared with an AI tool, report immediately via your department's security incident process and refer to the [Incident Response Playbook](incident-response-playbook.md).

### G-DH-03: Code repository restrictions

Before using AI assistants with code from a repository, verify:

1. The repository does not contain embedded secrets or credentials
2. The repository does not contain data above OFFICIAL classification
3. The repository is not subject to export control restrictions
4. You have authorisation to share the code with third-party services

### G-DH-04: Prompt hygiene

When crafting prompts:

- Use anonymised or synthetic data in examples
- Replace real identifiers with placeholders (e.g., `USER_ID_123`, `example@gov.uk`)
- Strip comments containing sensitive context before sharing code
- Avoid referencing specific system names, IP addresses, or internal URLs

**Example - Before (problematic):**
```python
# Connects to the MoJ case management API at https://internal-api.moj.gov.uk
# Uses service account: svc_case_processor
def get_case_details(case_id):
    ...
```

**Example - After (safe):**
```python
# Connects to case management API
# Uses service account credentials from environment
def get_case_details(case_id):
    ...
```

### G-DH-05: Context window awareness

Be aware that AI assistants may retain context within a session:

- Start new sessions when switching between projects with different classification levels
- Do not assume previous prompts are "forgotten" within a session
- Clear context explicitly when available in the tool
- Avoid mixing work across multiple departments in a single session

---

## Code security guardrails

### G-CS-01: Mandatory human review

All AI-generated code MUST be reviewed by a qualified human before:

- Committing to a shared repository
- Deploying to any environment (including development)
- Using in security-sensitive functions

**Minimum review scope:**

| Check | Description |
|-------|-------------|
| Logic correctness | Does the code do what was intended? |
| Security vulnerabilities | SQL injection, XSS, path traversal, etc. |
| Dependency safety | Are suggested packages from trusted sources? |
| Credential exposure | No hardcoded secrets or credentials? |
| Licence compliance | Compatible with project licensing? |

### G-CS-02: Security scanning requirements

AI-generated code must pass through the same security tooling as human-written code:

| Tool Type | Requirement | Timing |
|-----------|-------------|--------|
| SAST (Static Analysis) | Mandatory | Pre-commit or CI pipeline |
| Dependency scanning | Mandatory | Pre-commit or CI pipeline |
| Secret detection | Mandatory | Pre-commit hook |
| DAST (Dynamic Analysis) | Where applicable | Pre-deployment |
| Container scanning | Where applicable | Pre-deployment |

**Do not bypass security scanning** because code was AI-generated. AI-generated code may contain vulnerabilities that automated tools can detect.

### G-CS-03: Dependency verification

When AI assistants suggest external packages or libraries:

1. Verify the package exists and is actively maintained
2. Check the package source (prefer official repositories)
3. Review the package's security history
4. Confirm licence compatibility
5. Check for known vulnerabilities in the suggested version

**Warning signs:**

- Packages with very few downloads or stars
- Packages not updated in over 12 months
- Packages with known CVEs in suggested version
- Packages from unofficial or mirrored repositories

### G-CS-04: No AI in cryptographic implementations

Do not use AI assistants to:

- Implement cryptographic algorithms
- Generate cryptographic keys
- Design authentication or authorisation logic
- Create security token handling code

**Rationale:** Cryptographic code requires specialist knowledge. Subtle errors can create severe vulnerabilities that may not be detected by standard testing.

**Instead:** Use established, audited libraries and follow NCSC guidance on cryptographic implementations.

### G-CS-05: Prompt injection awareness

Be aware that AI-generated code may be vulnerable to prompt injection if it processes user input that is later sent to AI systems.

When building systems that use AI:

- Sanitise all user input before including in prompts
- Use parameterised prompts where possible
- Implement input length limits
- Monitor for unusual prompt patterns

---

## Usage boundary guardrails

### G-UB-01: Prohibited use cases

AI code assistants must not be used for:

| Prohibited Use | Rationale |
|----------------|-----------|
| Security-critical system core logic | Requires specialist security review |
| Safety-critical systems | Life-safety implications require formal methods |
| Cryptographic implementations | See [G-CS-04](#g-cs-04-no-ai-in-cryptographic-implementations) |
| Systems handling SECRET+ data | Classification restrictions |
| Generating malicious code or exploits | Ethical and legal restrictions |
| Circumventing security controls | Violation of security policy |
| Air-gapped or isolated environments | Network connectivity restrictions |

### G-UB-02: Appropriate use cases

AI code assistants are well-suited for:

| Appropriate Use | Notes |
|-----------------|-------|
| Boilerplate code generation | Tests, CRUD operations, data models |
| Code explanation and documentation | Understanding legacy code |
| Refactoring suggestions | Improving code structure |
| Test case generation | Unit tests, integration tests |
| Learning and exploration | Understanding new frameworks |
| Code review assistance | Secondary review, not replacement |
| Prototyping and POCs | Rapid iteration, non-production |

### G-UB-03: Tool-specific boundaries

Some AI assistants have specific restrictions based on their accreditation status:

| Tool | Current Status | Restrictions |
|------|----------------|--------------|
| GitHub Copilot Enterprise | [PLACEHOLDER: Accreditation status] | [PLACEHOLDER: Specific restrictions] |
| Claude Code | [PLACEHOLDER: Accreditation status] | [PLACEHOLDER: Specific restrictions] |
| Amazon Q Engineer | [PLACEHOLDER: Accreditation status] | [PLACEHOLDER: Specific restrictions] |
| Gemini Code Assist | [PLACEHOLDER: Accreditation status] | [PLACEHOLDER: Specific restrictions] |

Check with your department's security team for current accreditation status before deployment.

### G-UB-04: Environment restrictions

| Environment | AI Assistant Usage |
|-------------|-------------------|
| Local development | ✅ Permitted |
| Cloud development environments | ✅ Permitted with approved tools |
| CI/CD pipelines | ⚠️ Requires security review |
| Production environments | ❌ Not permitted for real-time code generation |
| Air-gapped networks | ❌ Not permitted (no connectivity) |
| Secure enclaves | ❌ Not permitted without specific accreditation |

---

## Output validation guardrails

### G-OV-01: Factual verification

AI assistants may generate plausible but incorrect information. Always verify:

- API signatures and method names against official documentation
- Configuration syntax against current tool versions
- Security recommendations against NCSC or vendor guidance
- Regulatory claims against authoritative sources

### G-OV-02: Code functionality testing

All AI-generated code must be tested before use:

| Test Type | Requirement |
|-----------|-------------|
| Unit tests | Mandatory for all generated functions |
| Integration tests | Required when interacting with other systems |
| Edge case testing | Required for input validation logic |
| Security testing | Required for authentication/authorisation code |

**Do not assume AI-generated code is correct** because it looks reasonable or compiles successfully.

### G-OV-03: Licence compliance verification

AI-generated code may inadvertently reproduce licensed content. Before using generated code:

1. Review for unusual similarity to known open source projects
2. Run through licence compliance tooling where available
3. Document the AI tool used for provenance tracking
4. Consult legal team if uncertain about licence implications

### G-OV-04: Hallucination detection

Watch for common AI hallucination patterns:

| Pattern | Example | Action |
|---------|---------|--------|
| Non-existent packages | `import gov_uk_utils` (doesn't exist) | Verify package exists |
| Fabricated APIs | `response.get_secure_data()` (not a real method) | Check documentation |
| Outdated syntax | Deprecated method calls | Verify against current version |
| Invented configuration | Non-existent config options | Test in isolated environment |

---

## Monitoring and audit guardrails

### G-MA-01: Usage logging

Departments should maintain logs of AI assistant usage:

| Log Element | Purpose |
|-------------|---------|
| User identity | Accountability |
| Tool used | Audit trail |
| Timestamp | Timeline reconstruction |
| Project/repository | Scope identification |

**Note:** Do not log prompt content as it may contain sensitive information.

### G-MA-02: Telemetry configuration

Configure AI assistant telemetry settings according to department policy:

| Setting | Recommendation |
|---------|----------------|
| Code snippet sharing | Disable unless required and approved |
| Prompt logging by vendor | Understand vendor policy before enabling |
| Usage analytics | Enable for adoption metrics |
| Error reporting | Enable for support purposes |

Review vendor data handling policies and ensure they meet government requirements.

### G-MA-03: Incident reporting

Report the following to your security team:

- Accidental exposure of classified or sensitive data
- AI-generated code that introduced a security vulnerability
- Suspected prompt injection attempts
- Unusual AI behaviour or responses suggesting compromise

Use existing security incident reporting channels. See [Incident Response Playbook](incident-response-playbook.md) for detailed procedures.

### G-MA-04: Periodic review

AI assistant usage should be reviewed:

| Review | Frequency | Scope |
|--------|-----------|-------|
| Usage metrics | Monthly | Adoption, active users, patterns |
| Security incidents | Monthly | AI-related incidents, near-misses |
| Guardrails effectiveness | Quarterly | Policy compliance, gaps identified |
| Tool accreditation | Annually | Continued suitability |

---

## Creating department-specific guardrails

This base configuration may be extended for department-specific requirements.

### Extension process

1. **Start with this base** - Copy guardrails-base.md as your starting point
2. **Identify additional requirements** - Review with your security team
3. **Add department-specific controls** - Use the G-DEPT-XX numbering convention
4. **Do not weaken base controls** - Department guardrails must be equal or stricter
5. **Document rationale** - Explain why additional controls are needed
6. **Obtain approval** - Security Lead sign-off before deployment
7. **Register with the AI Engineering Lab** - Submit to repository for cross-government visibility

### Common department extensions

| Department Context | Typical Additional Controls |
|--------------------|-----------------------------|
| Law enforcement | Enhanced logging, additional prohibited data types |
| Defence-adjacent | Export control verification, nationality restrictions |
| Healthcare | Additional PII categories, clinical safety review |
| Financial | PCI-DSS alignment, fraud prevention considerations |
| Critical infrastructure | Air-gap considerations, OT/IT boundary controls |

### Template for department extension

```markdown
---
title: AI Engineering Lab Guardrails - [Department Name]
version: 0.1.0
extends: guardrails-base.md v0.1.0
status: Draft
owner: [Department Security Team]
classification: [OFFICIAL/OFFICIAL-SENSITIVE]
---

# Department-Specific Guardrails

## Additional controls

### G-DEPT-01: [Control name]
[Description]

**Rationale:** [Why this is needed for your department]

## Modified controls

### G-XX-XX: [Original control reference]
**Base requirement:** [Original text]
**Department modification:** [How it differs]
**Rationale:** [Why modification is needed]
```

---

## Compliance verification

### Self-assessment checklist

Before using AI Engineering Labs, verify:

- [ ] I have completed AI Engineering Lab training
- [ ] I understand the data classification of my project
- [ ] The tool I'm using is approved for my department
- [ ] I know how to report security incidents
- [ ] I have reviewed department-specific guardrails (if any)

### Manager verification

Team leads should verify:

- [ ] All team members have completed training
- [ ] Department-specific guardrails are documented and communicated
- [ ] Security scanning is integrated into the development pipeline
- [ ] Code review processes include AI-generated code verification
- [ ] Incident reporting channels are established

---

## Related documents

- [Incident Response Playbook](incident-response-playbook.md) - Security incident handling
- [Risk Register Template](risk-register-template.md) - Risk documentation
- [AI-SDLC Playbook](../playbooks/ai-sdlc-playbook.md) - Development lifecycle integration

## References

- [NCSC Cloud Security Principles](https://www.ncsc.gov.uk/collection/cloud-security)
- [NCSC Secure Development Guidance](https://www.ncsc.gov.uk/collection/developers-collection)
- [Government Security Classifications](https://www.gov.uk/government/publications/government-security-classifications)
- [Technology Code of Practice](https://www.gov.uk/guidance/the-technology-code-of-practice)
- [OWASP Secure Coding Practices](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

---
