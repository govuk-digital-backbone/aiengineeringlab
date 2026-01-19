> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Risk Register Template

> A standardised template for documenting and managing risks associated with AI Engineering Lab adoption.

## Purpose

This template provides a consistent approach to identifying, assessing, and managing risks across all AI Engineering Lab deployments. It aligns with government risk management frameworks and ensures risks are visible, owned, and actively managed.

Use this template to:

- Document risks identified during assessments
- Track risks throughout the adoption lifecycle
- Provide assurance to Senior Responsible Owners (SROs)
- Support security accreditation processes
- Enable cross-government learning from risk patterns

## How to use this template

1. **Copy this template** for each department or programme deployment
2. **Complete the risk register** using the pre-populated common risks as a starting point
3. **Add deployment-specific risks** identified during assessment
4. **Assign owners** for each risk
5. **Review regularly** (minimum monthly during active adoption)
6. **Escalate** risks that exceed tolerance to programme governance

---

## Risk assessment methodology

### Likelihood scoring

| Score | Likelihood | Description |
|-------|------------|-------------|
| 1 | Rare | May occur only in exceptional circumstances (<5% probability) |
| 2 | Unlikely | Could occur but not expected (5-20% probability) |
| 3 | Possible | Might occur at some point (20-50% probability) |
| 4 | Likely | Will probably occur in most circumstances (50-80% probability) |
| 5 | Almost certain | Expected to occur (>80% probability) |

### Impact scoring

| Score | Impact | Description |
|-------|--------|-------------|
| 1 | Negligible | Minor inconvenience, no lasting effect |
| 2 | Minor | Limited impact, resolved within normal operations |
| 3 | Moderate | Noticeable impact requiring management attention |
| 4 | Major | Significant impact on objectives, requires senior attention |
| 5 | Severe | Critical impact, potential for lasting damage or regulatory breach |

### Risk rating matrix

|              | Negligible (1) | Minor (2) | Moderate (3) | Major (4) | Severe (5) |
|--------------|----------------|-----------|--------------|-----------|------------|
| **Almost certain (5)** | 5 (Medium) | 10 (Medium) | 15 (High) | 20 (Very High) | 25 (Very High) |
| **Likely (4)** | 4 (Low) | 8 (Medium) | 12 (High) | 16 (High) | 20 (Very High) |
| **Possible (3)** | 3 (Low) | 6 (Medium) | 9 (Medium) | 12 (High) | 15 (High) |
| **Unlikely (2)** | 2 (Low) | 4 (Low) | 6 (Medium) | 8 (Medium) | 10 (Medium) |
| **Rare (1)** | 1 (Low) | 2 (Low) | 3 (Low) | 4 (Low) | 5 (Medium) |

### Risk tolerance thresholds

| Rating | Score Range | Response Required |
|--------|-------------|-------------------|
| Very High | 20-25 | Immediate escalation to SRO; consider stopping activity |
| High | 12-19 | Active management required; escalate to programme board |
| Medium | 5-11 | Monitor and manage; include in regular reporting |
| Low | 1-4 | Accept and monitor; review at next scheduled assessment |

---

## Risk register

### Deployment information

| Field | Value |
|-------|-------|
| Department/Programme | [PLACEHOLDER: Department name] |
| AI Tools in scope | [PLACEHOLDER: e.g., GitHub Copilot, Claude Code] |
| Risk register owner | [PLACEHOLDER: Name and role] |
| Created date | [PLACEHOLDER: Date] |
| Last reviewed | [PLACEHOLDER: Date] |
| Next review due | [PLACEHOLDER: Date] |

---

### Category 1: Data and information security risks

#### RISK-SEC-01: Sensitive data exposure to AI tools

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-SEC-01 |
| **Category** | Security |
| **Risk description** | Engineers inadvertently share sensitive, classified, or personal data with AI code assistants through prompts, code context, or file uploads |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 4 (Likely) |
| **Impact (inherent)** | 4 (Major) |
| **Inherent risk score** | 16 (High) |
| **Existing controls** | - Guardrails documentation and training<br>- Data classification guidance<br>- Pre-commit secret scanning |
| **Likelihood (residual)** | 3 (Possible) |
| **Impact (residual)** | 4 (Major) |
| **Residual risk score** | 12 (High) |
| **Additional mitigations planned** | [PLACEHOLDER: e.g., Enhanced monitoring, additional training] |
| **Target risk score** | 8 (Medium) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-SEC-02: Credential exposure in generated code

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-SEC-02 |
| **Category** | Security |
| **Risk description** | AI assistants generate code containing hardcoded credentials, API keys, or connection strings that are committed to repositories |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 4 (Major) |
| **Inherent risk score** | 12 (High) |
| **Existing controls** | - Pre-commit hooks for secret detection<br>- Code review requirements<br>- Guardrails training |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 4 (Major) |
| **Residual risk score** | 8 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-SEC-03: Data residency and sovereignty

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-SEC-03 |
| **Category** | Security |
| **Risk description** | Code and prompts are processed or stored in jurisdictions outside the UK/EEA, potentially violating data sovereignty requirements |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 9 (Medium) |
| **Existing controls** | - Vendor data residency verification<br>- DPA review<br>- Tool accreditation process |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 3 (Moderate) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 6 (Medium) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

---

### Category 2: Code quality and security risks

#### RISK-CODE-01: Security vulnerabilities in generated code

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-CODE-01 |
| **Category** | Code Quality |
| **Risk description** | AI-generated code contains security vulnerabilities (e.g., SQL injection, XSS, insecure deserialisation) that are not detected before deployment |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 4 (Likely) |
| **Impact (inherent)** | 4 (Major) |
| **Inherent risk score** | 16 (High) |
| **Existing controls** | - Mandatory code review<br>- SAST/DAST integration<br>- Security scanning in CI/CD |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 4 (Major) |
| **Residual risk score** | 8 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-CODE-02: Malicious or vulnerable dependencies

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-CODE-02 |
| **Category** | Code Quality |
| **Risk description** | AI assistants suggest packages or libraries that are malicious, abandoned, or contain known vulnerabilities |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 4 (Major) |
| **Inherent risk score** | 12 (High) |
| **Existing controls** | - Dependency scanning tools<br>- Approved package repositories<br>- Engineer verification guidance |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 3 (Moderate) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 6 (Medium) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-CODE-03: Functional defects from AI hallucination

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-CODE-03 |
| **Category** | Code Quality |
| **Risk description** | AI-generated code appears correct but contains logical errors or references non-existent APIs/methods, leading to runtime failures |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 4 (Likely) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 12 (High) |
| **Existing controls** | - Mandatory testing of AI-generated code<br>- Code review requirements<br>- Engineer training on hallucination patterns |
| **Likelihood (residual)** | 3 (Possible) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

---

### Category 3: Intellectual property and legal risks

#### RISK-IP-01: Licence compliance violations

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-IP-01 |
| **Category** | Legal/IP |
| **Risk description** | AI-generated code inadvertently reproduces copyrighted or incompatibly-licensed code from training data, creating legal exposure |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 9 (Medium) |
| **Existing controls** | - Licence compliance scanning<br>- Vendor indemnification review<br>- Code provenance documentation |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 3 (Moderate) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 6 (Medium) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-IP-02: Unclear IP ownership

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-IP-02 |
| **Category** | Legal/IP |
| **Risk description** | Uncertainty over intellectual property ownership of AI-generated code creates complications for procurement, licensing, or future commercialisation |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 2 (Unlikely) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 6 (Medium) |
| **Existing controls** | - Contract review for IP terms<br>- Legal guidance documentation<br>- Crown copyright application |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 4 (Low) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

---

### Category 4: Adoption and operational risks

#### RISK-ADO-01: Low adoption and wasted investment

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-ADO-01 |
| **Category** | Adoption |
| **Risk description** | Licences are procured but not activated or actively used, resulting in wasted investment and failure to realise productivity benefits |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 9 (Medium) |
| **Existing controls** | - Daily usage monitoring<br>- FDE support for low-maturity teams<br>- Champion network<br>- Training programme |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 3 (Moderate) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 3 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-ADO-02: Engineer resistance

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-ADO-02 |
| **Category** | Adoption |
| **Risk description** | Engineers resist using AI tools due to scepticism, concerns about job security, or preference for existing workflows, undermining adoption targets |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 9 (Medium) |
| **Existing controls** | - Resistance identification<br>- Change management approach (ADKAR)<br>- Champion peer influence<br>- Success story sharing |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 4 (Low) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-ADO-03: Skills degradation

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-ADO-03 |
| **Category** | Adoption |
| **Risk description** | Over-reliance on AI assistants leads to degradation of fundamental coding skills, particularly among junior engineers |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 3 (Moderate) |
| **Inherent risk score** | 9 (Medium) |
| **Existing controls** | - Training emphasis on AI as augmentation<br>- Code review requirements<br>- Balanced use guidance |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 4 (Low) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

---

### Category 5: Service and vendor risks

#### RISK-VEN-01: Service availability and dependency

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-VEN-01 |
| **Category** | Vendor |
| **Risk description** | AI assistant service outages disrupt engineer productivity, particularly for teams that have become highly dependent on the tools |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 2 (Minor) |
| **Inherent risk score** | 6 (Medium) |
| **Existing controls** | - Vendor SLA monitoring<br>- Training on working without AI<br>- Multiple tool familiarity |
| **Likelihood (residual)** | 3 (Possible) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 6 (Medium) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 6 (Medium) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-VEN-02: Vendor lock-in

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-VEN-02 |
| **Category** | Vendor |
| **Risk description** | Deep integration with a specific AI tool creates switching costs and dependency, reducing negotiating leverage and flexibility |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 2 (Minor) |
| **Inherent risk score** | 6 (Medium) |
| **Existing controls** | - Tool-agnostic training<br>- Exit strategy requirements<br>- Multi-tool exposure |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 4 (Low) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

#### RISK-VEN-03: Premium credit exhaustion

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-VEN-03 |
| **Category** | Vendor |
| **Risk description** | Teams exhaust allocated premium model credits faster than anticipated, leading to service degradation or unexpected costs |
| **Risk owner** | [PLACEHOLDER: Name] |
| **Likelihood (inherent)** | 3 (Possible) |
| **Impact (inherent)** | 2 (Minor) |
| **Inherent risk score** | 6 (Medium) |
| **Existing controls** | - Credit usage monitoring<br>- Allocation policies<br>- Intervention triggers |
| **Likelihood (residual)** | 2 (Unlikely) |
| **Impact (residual)** | 2 (Minor) |
| **Residual risk score** | 4 (Low) |
| **Additional mitigations planned** | [PLACEHOLDER] |
| **Target risk score** | 4 (Low) |
| **Status** | Open |
| **Last updated** | [PLACEHOLDER: Date] |

---

## Adding deployment-specific risks

Use this template for risks unique to your deployment:

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-[CAT]-[NN] |
| **Category** | [Security / Code Quality / Legal/IP / Adoption / Vendor / Other] |
| **Risk description** | [Clear description of what could go wrong] |
| **Risk owner** | [Name and role] |
| **Likelihood (inherent)** | [1-5] |
| **Impact (inherent)** | [1-5] |
| **Inherent risk score** | [Likelihood × Impact] |
| **Existing controls** | [What's already in place] |
| **Likelihood (residual)** | [1-5 after controls] |
| **Impact (residual)** | [1-5 after controls] |
| **Residual risk score** | [Likelihood × Impact] |
| **Additional mitigations planned** | [What else will be done] |
| **Target risk score** | [Desired end state] |
| **Status** | [Open / Mitigating / Closed / Accepted] |
| **Last updated** | [Date] |

---

## Risk review log

| Review Date | Reviewer | Changes Made | Next Review |
|-------------|----------|--------------|-------------|
| [PLACEHOLDER] | [PLACEHOLDER] | Initial register created | [PLACEHOLDER] |
| | | | |
| | | | |

---

## Escalation record

| Date | Risk ID | Escalated To | Reason | Outcome |
|------|---------|--------------|--------|---------|
| | | | | |
| | | | | |

---

## Summary dashboard

### Current risk profile

| Rating | Count | Risk IDs |
|--------|-------|----------|
| Very High (20-25) | 0 | - |
| High (12-19) | 0 | - |
| Medium (5-11) | [COUNT] | [LIST] |
| Low (1-4) | [COUNT] | [LIST] |

### Trend

| Period | Very High | High | Medium | Low | Direction |
|--------|-----------|------|--------|-----|-----------|
| Current | | | | | |
| Previous | | | | | |
| Change | | | | | ↑↓→ |

---

## Related documents

- [Guardrails Base](guardrails-base.md) - Security controls
- [Incident Response Playbook](incident-response-playbook.md) - When risks materialise
- [Quality Strategy](../quality-metrics/quality-strategy.md) - Metrics for monitoring

## References

- [GOV.UK Orange Book](https://www.gov.uk/government/publications/orange-book) - Risk management guidance
- [Government Functional Standard GovS 002](https://www.gov.uk/government/publications/project-delivery-functional-standard) - Project delivery
- [NCSC Risk Management Guidance](https://www.ncsc.gov.uk/collection/risk-management-collection)