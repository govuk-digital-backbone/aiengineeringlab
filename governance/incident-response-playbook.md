> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Incident Response Playbook

> Procedures for identifying, responding to, and learning from incidents related to AI coding assistant usage.

## Purpose

This playbook provides standardised procedures for handling security incidents, data exposures, and other adverse events involving AI Engineering Labs. It ensures consistent, timely responses that minimise harm and support organisational learning.

Use this playbook when:

- Sensitive data has been exposed to an AI tool
- AI-generated code has introduced a security vulnerability
- A service compromise is suspected
- Unusual AI behaviour suggests a potential issue
- Any event occurs that could harm the organisation through AI tool usage

## Incident classification

### Severity levels

| Severity | Description | Response Time | Examples |
|----------|-------------|---------------|----------|
| **P1 - Critical** | Immediate threat to data, systems, or operations | Within 1 hour | SECRET data exposed; active exploitation of AI-generated vulnerability; credential compromise |
| **P2 - High** | Significant risk requiring urgent attention | Within 4 hours | OFFICIAL-SENSITIVE data exposed; security vulnerability in production; bulk PII exposure |
| **P3 - Medium** | Notable incident requiring prompt response | Within 24 hours | OFFICIAL data inadvertently shared; vulnerability detected pre-deployment; single PII record exposed |
| **P4 - Low** | Minor incident for awareness and tracking | Within 72 hours | Near-miss events; policy violations without data exposure; process failures caught in review |

### Incident categories

| Category | Code | Description |
|----------|------|-------------|
| Data exposure | DE | Sensitive data shared with AI tool |
| Code vulnerability | CV | Security flaw in AI-generated code |
| Credential leak | CL | Secrets, keys, or passwords exposed |
| Service compromise | SC | AI tool or integration compromised |
| Policy violation | PV | Guardrails or usage policy breached |
| IP/Licence issue | IP | Copyright or licensing concern |
| Availability | AV | Service outage impacting operations |
| Other | OT | Incidents not fitting other categories |

---

## Incident response process

### Phase 1: Detection and reporting

#### How to report an incident

**Immediate actions for the person discovering the incident:**

1. **Stop** - Do not continue the activity that caused or revealed the incident
2. **Do not attempt to fix** - Preserve evidence; do not delete prompts, outputs, or logs
3. **Report immediately** using one of these channels:

| Channel | Use for | Contact |
|---------|---------|---------|
| Security incident hotline | P1/P2 incidents | [PLACEHOLDER] |
| Security email | All incidents | [PLACEHOLDER: security@department.gov.uk] |
| Service desk | P3/P4 incidents | [PLACEHOLDER: Service desk details] |
| Line manager | If unsure of severity | Direct contact |

4. **Complete initial report** with:
   - What happened (brief description)
   - When it happened (date/time)
   - Which AI tool was involved
   - What data or systems may be affected
   - Your contact details

#### Detection sources

Incidents may be detected through:

| Source | Examples |
|--------|----------|
| Self-reporting | Engineer realises they shared sensitive data |
| Code review | Reviewer identifies vulnerability or exposed secret |
| Automated scanning | SAST/secret detection tools flag issues |
| Security monitoring | Anomaly detection in AI tool usage patterns |
| External notification | Vendor, third party, or security researcher report |
| Audit | Periodic review identifies historical issues |

---

### Phase 2: Triage and assessment

#### Initial triage (within 30 minutes of report)

The Security Team or designated incident handler will:

1. **Acknowledge receipt** to the reporter
2. **Assign incident ID** using format: `AIENG-[YYYY]-[NNNN]`
3. **Gather initial facts:**
   - Confirm what occurred
   - Identify AI tool(s) involved
   - Determine data classification affected
   - Establish timeline
4. **Assign severity level** using classification table above
5. **Identify incident owner** responsible for resolution
6. **Notify stakeholders** per escalation matrix

#### Escalation matrix

| Severity | Immediate Notification | Within 4 Hours | Within 24 Hours |
|----------|------------------------|----------------|-----------------|
| P1 | SIRO, Security Lead, SRO, IT Director | CISO, DPO (if personal data) | Permanent Secretary (if required) |
| P2 | Security Lead, SRO | SIRO, DPO (if personal data) | Programme Board |
| P3 | Security Lead | SRO | Included in weekly report |
| P4 | - | Security Lead | Included in monthly report |

#### Assessment questions

| Question | Purpose |
|----------|---------|
| What data was exposed? | Determine classification and sensitivity |
| How much data? | Scope the exposure |
| Who has access to the AI tool's logs/data? | Understand potential access |
| Is the data still accessible? | Determine if retrieval is possible |
| Has the vulnerability been exploited? | Assess actual vs potential harm |
| Are other systems affected? | Identify lateral impact |
| Is the incident ongoing? | Determine containment urgency |

---

### Phase 3: Containment

#### Immediate containment actions by incident type

##### Data exposure (DE)

| Action | Responsibility | Timeframe |
|--------|----------------|-----------|
| Terminate active AI session | User/Security | Immediate |
| Revoke user's AI tool access (if serious) | IT Admin | Within 1 hour |
| Contact vendor to request data deletion | Security Lead | Within 4 hours |
| Document what was shared (from memory/logs) | User | Within 2 hours |
| Assess if data persists | Security Lead | Within 24 hours |

##### Code vulnerability (CV)

| Action | Responsibility | Timeframe |
|--------|----------------|-----------|
| Identify all locations of vulnerable code | Development team | Within 2 hours |
| Remove or disable affected code in production | DevOps | Immediate (P1/P2) |
| Block deployment pipeline if pre-production | DevOps | Immediate |
| Create hotfix branch | Development team | Within 4 hours |
| Scan for exploitation evidence | Security team | Within 4 hours |

##### Credential leak (CL)

| Action | Responsibility | Timeframe |
|--------|----------------|-----------|
| Rotate affected credentials immediately | IT Admin/DevOps | Within 30 minutes |
| Revoke old credentials | IT Admin | Within 1 hour |
| Audit usage of compromised credentials | Security team | Within 4 hours |
| Update all systems using the credentials | DevOps | Within 24 hours |
| Scan repositories for credential exposure | Security team | Within 4 hours |

##### Service compromise (SC)

| Action | Responsibility | Timeframe |
|--------|----------------|-----------|
| Isolate affected systems | IT/Security | Immediate |
| Disable AI tool integration | IT Admin | Within 30 minutes |
| Preserve logs and forensic evidence | Security team | Immediate |
| Engage vendor security team | Security Lead | Within 1 hour |
| Notify NCSC if significant | SIRO | Within 24 hours |

#### Containment verification

Before proceeding to eradication, confirm:

- [ ] Immediate threat has been neutralised
- [ ] Affected systems/data have been isolated
- [ ] Evidence has been preserved
- [ ] Spread has been prevented
- [ ] Stakeholders have been notified

---

### Phase 4: Eradication and recovery

#### Eradication activities

| Activity | Description |
|----------|-------------|
| Root cause analysis | Determine how the incident occurred |
| Vulnerability remediation | Fix the underlying security flaw |
| Malicious content removal | Remove any compromised code or data |
| Control gap closure | Implement missing controls that allowed incident |
| Vendor coordination | Work with AI tool vendor on their remediation |

#### Recovery activities

| Activity | Description |
|----------|-------------|
| Service restoration | Return AI tools to operational status |
| Access reinstatement | Restore user access with appropriate controls |
| Monitoring enhancement | Implement additional monitoring for recurrence |
| Verification testing | Confirm systems are secure before full restoration |
| User communication | Inform affected users of resolution and any required actions |

#### Recovery approval

| Severity | Approval Required |
|----------|-------------------|
| P1 | SIRO and Security Lead |
| P2 | Security Lead |
| P3 | Incident Owner |
| P4 | Incident Owner |

---

### Phase 5: Post-incident activities

#### Incident report

Complete a post-incident report within:

| Severity | Report Due |
|----------|------------|
| P1 | 5 working days |
| P2 | 10 working days |
| P3 | 15 working days |
| P4 | Included in monthly summary |

**Report contents:**

1. **Executive summary** - What happened, impact, resolution
2. **Timeline** - Chronological sequence of events
3. **Root cause analysis** - Why it happened
4. **Impact assessment** - What was affected and how
5. **Response evaluation** - How well we responded
6. **Lessons learned** - What we can improve
7. **Recommendations** - Specific actions to prevent recurrence

#### Lessons learned session

For P1 and P2 incidents, conduct a blameless post-incident review:

| Element | Description |
|---------|-------------|
| Attendees | Incident team, affected team leads, Security, AI Engineering Lab programme |
| Timing | Within 10 working days of incident closure |
| Duration | 60-90 minutes |
| Output | Documented lessons and action items |
| Focus | Process improvement, not blame |

#### Knowledge sharing

| Action | Audience | Timing |
|--------|----------|--------|
| Update guardrails if gap identified | All users | Within 5 days |
| Add to training materials if relevant | Future users | Next training update |
| Share anonymised lessons | Cross-government | Within 15 days |
| Update risk register | Programme governance | Within 5 days |
| Brief champion network (if appropriate) | Champions | Next community session |

---

## Specific incident playbooks

### Playbook A: Personal data exposed to AI tool

**Scenario:** A engineer accidentally includes real customer PII in a prompt.

**Immediate actions:**

1. End the AI session immediately
2. Do not attempt to "undo" by asking AI to forget
3. Document exactly what was shared
4. Report to Security and DPO within 1 hour

**Assessment:**

- How many data subjects affected?
- What categories of personal data?
- Is the AI tool provider a processor under GDPR?
- What does the vendor's DPA say about data retention?

**Containment:**

- Request vendor delete session data (reference DPA terms)
- Assess notification requirements (ICO, data subjects)

**Regulatory considerations:**

| Condition | Action |
|-----------|--------|
| High risk to individuals | Notify ICO within 72 hours |
| Risk to individuals | Document in breach register |
| Unlikely risk | Document decision not to notify |

### Playbook B: Security vulnerability deployed to production

**Scenario:** AI-generated code containing SQL injection vulnerability reaches production.

**Immediate actions:**

1. Assess if vulnerability is being exploited (check logs)
2. If exploited: invoke major security incident process
3. If not exploited: implement emergency change to disable/fix

**Assessment:**

- What data could be accessed via the vulnerability?
- How long has the vulnerability been in production?
- Is there evidence of exploitation?
- What compensating controls exist (WAF, input validation)?

**Containment:**

- Deploy hotfix or disable affected functionality
- Implement WAF rule if available
- Increase monitoring on affected endpoints

**Recovery:**

- Full code review of AI-generated sections in the application
- Retrospective security testing
- Update code review checklist

### Playbook C: API key committed to repository

**Scenario:** AI suggests code containing a hardcoded API key which is committed.

**Immediate actions:**

1. Rotate the API key immediately - assume compromised
2. Check if repository is public or has been cloned
3. Remove from repository history (not just current version)

**Assessment:**

- What does the API key provide access to?
- Has the key been used since exposure?
- Who has had access to the repository?

**Containment:**

```bash
# Remove from git history (example using git-filter-repo)
git filter-repo --invert-paths --path 
```

**Prevention:**

- Enable pre-commit hooks for secret detection
- Review CI/CD secret scanning configuration
- Reinforce training on secret management

### Playbook D: Suspected prompt injection attack

**Scenario:** AI assistant produces unexpected output suggesting malicious prompt injection.

**Immediate actions:**

1. Stop using the affected AI session
2. Do not execute any suggested commands or code
3. Screenshot/document the suspicious output
4. Report to Security

**Assessment:**

- What triggered the unusual behaviour?
- Was user input involved that could contain injection?
- Is this a vulnerability in our application or the AI tool?

**Containment:**

- Review application for prompt injection vulnerabilities
- Implement input sanitisation
- Consider rate limiting AI interactions

**Vendor notification:**

- Report to AI tool vendor if it appears to be a tool vulnerability
- Share details (sanitised) with the Platform team for cross-government awareness

---

## Roles and responsibilities

| Role | Responsibilities |
|------|------------------|
| **Reporter** | Identify and report incident promptly; preserve evidence; cooperate with investigation |
| **Incident Owner** | Coordinate response; make decisions within authority; communicate status; ensure resolution |
| **Security Lead** | Provide security expertise; assess risk; advise on containment; liaise with NCSC if needed |
| **IT/DevOps** | Execute technical containment and recovery actions; preserve logs |
| **SIRO** | Approve major decisions; accountable for information risk; escalate to board if needed |
| **DPO** | Assess personal data impact; advise on ICO notification; ensure GDPR compliance |
| **SRO** | Programme-level decisions; stakeholder communication; resource allocation |
| **Communications** | Manage internal/external messaging if required |

---

## Communication templates

### Initial notification (internal)

```
Subject: [SEVERITY] AI Engineering Lab Security Incident - AIENG-[YYYY]-[NNNN]

An incident involving AI Engineering Lab usage has been reported.

Incident ID: AIENG-[YYYY]-[NNNN]
Severity: [P1/P2/P3/P4]
Category: [Category]
Status: [Investigating/Contained/Resolved]

Summary: [Brief description - 2-3 sentences]

Affected: [Systems/data/users affected]

Current actions: [What is being done]

Incident Owner: [Name]
Next update: [Time]

Please direct questions to [contact].
```

### Status update

```
Subject: UPDATE [#N] - AIENG-[YYYY]-[NNNN] - [Brief description]

Status: [Investigating/Contained/Resolving/Resolved]

Progress since last update:
- [Action completed]
- [Action completed]

Current focus:
- [Ongoing action]

Blockers/risks:
- [Any issues]

Next update: [Time]
```

### Incident closure

```
Subject: CLOSED - AIENG-[YYYY]-[NNNN] - [Brief description]

This incident has been resolved and closed.

Resolution: [How it was resolved]

Impact: [Final assessment of impact]

Post-incident report: [Link - for P1/P2]

Lessons learned session: [Date/time - for P1/P2]

Questions: Contact [Incident Owner]
```

---

## Metrics and reporting

### Incident metrics to track

| Metric | Description |
|--------|-------------|
| Total incidents | Count by severity and category |
| Mean time to detect (MTTD) | Time from occurrence to detection |
| Mean time to respond (MTTR) | Time from detection to containment |
| Mean time to resolve | Time from detection to closure |
| Incidents by AI tool | Distribution across tools |
| Incidents by team | Identify teams needing support |
| Repeat incidents | Same root cause recurring |

### Reporting cadence

| Report | Frequency | Audience | Content |
|--------|-----------|----------|---------|
| Incident summary | Weekly | Security Lead, SRO | Open incidents, key metrics |
| Monthly report | Monthly | Programme Board | Trends, lessons learned, recommendations |
| Quarterly review | Quarterly | SIRO, Senior Leadership | Strategic risks, control effectiveness |

---

## Related documents

- [Guardrails Base](guardrails-base.md) - Security controls to prevent incidents
- [Risk Register Template](risk-register-template.md) - Risk documentation
- [Department Security Incident Process] - [PLACEHOLDER: Link to existing process]

## References

- [NCSC Incident Management Guidance](https://www.ncsc.gov.uk/collection/incident-management)
- [ICO Personal Data Breach Guidance](https://ico.org.uk/for-organisations/report-a-breach/)
- [Government Security Classifications](https://www.gov.uk/government/publications/government-security-classifications)