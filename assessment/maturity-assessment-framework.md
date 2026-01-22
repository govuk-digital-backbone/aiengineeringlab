> **ALPHA**:
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab maturity assessment framework

This is a structured approach to assessing team readiness and determining appropriate support levels for AI code assistant adoption.

## Purpose

This framework provides a consistent method for evaluating teams before AI Engineering Lab deployment. The assessment determines:

- current team maturity level (Starting, Developing, or Established)
- appropriate support intensity from the programme
- tailored adoption roadmap and training needs
- specific risks and blockers to address

Every team entering the AI Engineering Lab programme must complete this assessment as part of the initial onboarding and foundation phase.

## Assessment overview

### Who is assessed

| Role | Assessment Method | Purpose |
|------|-------------------|---------|
| Delivery manager | Questionnaire and interview | Team context, delivery pressures, change appetite |
| Technical lead | Questionnaire and interview | Technical environment, patterns, constraints |
| Individual engineers | Questionnaire | Skills baseline, attitudes, concerns |

### Assessment timeline

| Activity | Duration | Participants |
|----------|----------|--------------|
| Questionnaire distribution | Day 1 | All team members |
| Questionnaire completion | Days 1 to 3 | Individual completion |
| DM interview | Day 4 | Delivery manager and assessor |
| Tech Lead interview | Day 4 | Technical lead and assessor |
| Analysis and classification | Day 5 | Assessment team |
| Roadmap planning session | Day 5 | Team leads and FDE |

**Total assessment time:** 5 working days per team

### Assessment outputs

1. Maturity classification - Starting, Developing, or Established
2. Adoption roadmap - tailored plan with milestones
3. Risk register entries - team-specific risks identified
4. Support allocation - FDE intensity and duration
5. Training plan - required training modules and format

---

## Maturity levels

### Level 1: Starting

**Description:** teams with limited AI assistant experience, significant constraints, or substantial support needs.

| Dimension | Indicators |
|-----------|------------|
| Experience | Little or no prior AI assistant usage |
| Technical environment | Complex constraints, legacy systems, limited tooling |
| Team composition | Higher proportion of junior engineers |
| Change capacity | Limited bandwidth due to delivery pressures |
| Attitudes | Significant scepticism or resistance present |

**Support model:**

- embedded FDE support (dedicated FDE for 2 to 4 weeks)
- intensive hands-on training (face-to-face workshops)
- daily check-ins during initial adoption
- high-touch change management

**Typical duration to progress:** 6 to 8 weeks to Developing.

---

### Level 2: Developing

**Description:** teams with some AI experience or good foundational capabilities, requiring moderate support to build proficiency.

| Dimension | Indicators |
|-----------|------------|
| Experience | Some team members have used AI assistants |
| Technical environment | Standard tooling, some constraints manageable |
| Team composition | Mix of experience levels |
| Change capacity | Reasonable bandwidth for adoption activities |
| Attitudes | Generally positive, some concerns to address |

**Support model:**

- shared FDE support (FDE covers multiple teams)
- blended training (mix of self-paced and guided)
- weekly check-ins
- standard change management approach

**Typical duration to progress:** 4 to 6 weeks to Established.

---

### Level 3: Established

**Description:** teams ready for largely self-sufficient adoption with minimal direct support.

| Dimension | Indicators |
|-----------|------------|
| Experience | Multiple team members actively using AI assistants |
| Technical environment | Modern tooling, few constraints |
| Team composition | Experienced team with strong practices |
| Change capacity | Good bandwidth, proactive about adoption |
| Attitudes | Enthusiastic, potential champions identified |

**Support model:**

- self-service with on-demand FDE consultation
- self-paced training with optional workshops
- bi-weekly or monthly check-ins
- light-touch change management

**Role in programme:** Established teams often become role models and sources of champions for other teams.

---

## Assessment dimensions

The assessment evaluates teams across six dimensions, each contributing to the overall maturity classification.

### Dimension 1: technical environment

**What we assess:** the technical constraints and enablers affecting AI assistant adoption.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| IDE standardisation | Multiple IDEs, no standard | Preferred IDE with flexibility | Standardised IDE across team |
| Source control | Complex branching, legacy VCS | Standard Git workflows | Modern Git practices, CI/CD |
| Code review process | Ad-hoc or no formal process | Basic PR reviews | Thorough reviews with standards |
| Security tooling | Manual or no scanning | Basic SAST/dependency scanning | Comprehensive security pipeline |
| Development environment | Complex local setup | Documented setup process | Containerised/automated setup |
| Legacy code proportion | >70% legacy | 30 to 70% legacy | <30% legacy |

**Key questions:**

- what IDEs does the team use?
- how is source control managed?
- what security scanning is in place?
- how much of the codebase is legacy?
---
### Dimension 2: team composition and skills

**What we assess:** the team's skill levels and composition affecting adoption speed.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| Seniority mix | Predominantly junior | Mixed levels | Strong senior presence |
| AI familiarity | <20% have used AI tools | 20 to 50% have used AI tools | >50% have used AI tools |
| Learning culture | Limited time for learning | Some learning activities | Active learning culture |
| Pair programming | Rarely practiced | Sometimes practiced | Regular practice |
| Knowledge sharing | Ad-hoc | Regular demos/sessions | Systematic knowledge transfer |

**Key questions:**

- what is the team's seniority distribution?
- how many team members have used AI coding assistants?
- how does the team share knowledge?
---
### Dimension 3: delivery context

**What we assess:** current delivery pressures and capacity for adoption activities.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| Delivery pressure | Critical deadline within 8 weeks | Moderate pressure | Manageable workload |
| Change fatigue | Recent major changes | Some recent changes | Stable period |
| Protected time | Cannot allocate time for training | Can allocate some time | Can dedicate time to adoption |
| Management support | Limited or uncertain | Supportive | Actively championing |
| Team stability | High turnover or recent changes | Some changes | Stable team |

**Key questions:**

- what are the team's upcoming delivery commitments?
- has the team experienced significant recent changes?
- can the team allocate time for training?
---
### Dimension 4: security and compliance posture

**What we assess:** security requirements and constraints affecting tool deployment.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| Security constraints | Significant restrictions | Some restrictions | Standard requirements |
| Compliance requirements | Complex regulatory environment | Moderate compliance needs | Standard compliance |
| Security team engagement | Security concerns unresolved | Security engaged | Security approved |
| Air-gap requirements | Partial air-gap constraints | Network restrictions | Standard network access |

**Key questions:**

- what classification of data does the team work with?
- are there specific security constraints?
- has security team been consulted?
---
### Dimension 5: attitudes and change readiness

**What we assess:** team attitudes toward AI assistants and readiness for change.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| Overall sentiment | Sceptical or resistant | Mixed or cautiously positive | Enthusiastic |
| Concerns | Significant unaddressed concerns | Some concerns to address | Concerns understood and managed |
| Champions | No clear champions | Potential champions identified | Active champions present |
| Previous AI experience | Negative or no experience | Neutral experience | Positive experience |
| Job security concerns | Significant concerns | Some concerns | Concerns addressed |

**Key questions:**

- how does the team feel about AI coding assistants?
- what concerns do team members have?
- are there potential champions in the team?
---
### Dimension 6: ways of working

**What we assess:** current development practices affecting AI integration.

| Factor | Starting | Developing | Established |
|--------|----------|------------|-------------|
| Coding standards | Informal or absent | Documented but inconsistent | Clear and enforced |
| Testing practices | Limited testing | Reasonable test coverage | Comprehensive testing |
| Documentation | Minimal documentation | Basic documentation | Well-documented codebase |
| Refactoring habits | Rarely refactor | Occasional refactoring | Regular refactoring |
| Technical debt | High technical debt | Moderate technical debt | Managed technical debt |

**Key questions:**

- does the team have documented coding standards?
- what is the testing culture like?
- how is technical debt managed?

---

## Scoring methodology

### Dimension scoring

Each dimension is scored 1 to 3 based on assessment findings.

| Score | Level | Description |
|-------|-------|-------------|
| 1 | Starting | Most factors indicate significant challenges |
| 2 | Developing | Mix of factors, some challenges, some strengths |
| 3 | Established | Most factors indicate readiness |

### Overall classification

Average scores are calculated across all six dimensions.

| Average Score | Classification |
|---------------|----------------|
| 1.0 to 1.7 | Starting |
| 1.8 to 2.4 | Developing |
| 2.5 to 3.0 | Established |

### Classification override rules

Certain factors automatically constrain classification regardless of score.

| Condition | Maximum Classification |
|-----------|------------------------|
| No security approval | Starting |
| Critical delivery deadline within 4 weeks | Starting |
| >50% team actively resistant | Starting |
| No management support | Starting |
| Air-gapped environment (for cloud tools) | Not suitable |

### Example scoring

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical environment | 2 | Standard Git, some legacy code |
| Team composition | 2 | Mixed experience, 30% used AI tools |
| Delivery context | 1 | Major release in 6 weeks |
| Security posture | 3 | OFFICIAL only, security approved |
| Attitudes | 2 | Cautiously positive, some concerns |
| Ways of working | 2 | Good testing, needs documentation |
| **Average** | **2.0** | **Developing** |

However, with a major release in 6 weeks, consider delaying intensive adoption or providing lighter-touch support until after the release.

---

## Assessment process

### Step 1: preparation

**Before the assessment begins:**

- [ ] Identify team to be assessed
- [ ] Confirm DM and Tech Lead availability for interviews
- [ ] Distribute questionnaires to all team members
- [ ] Set deadline for questionnaire completion (48 hours)
- [ ] Schedule interview slots

**Information to gather in advance:**

- team size and composition
- current project and delivery commitments
- technology stack overview
- any known constraints or concerns

### Step 2: questionnaire completion

**Questionnaires**

| Questionnaire | Recipient | Time Required |
|---------------|-----------|---------------|
| [Delivery manager assessment](assessment-questionnaires/delivery-manager-assessment.md) | Delivery manager | 20 to 30 minutes |
| [Technical lead assessment](assessment-questionnaires/technical-lead-assessment.md) | Technical lead | 20 to 30 minutes |
| [Individual engineer assessment](assessment-questionnaires/individual-engineer-assessment.md) | All engineers | 15 to 20 minutes |

**Questionnaire distribution**

You should:
- send via email or Teams with clear deadline
- emphasise confidentiality of individual responses
- explain the purpose and how results will be used
- provide a contact for questions

### Step 3: interviews

**Delivery manager interview (45 minutes)**

In this interview, you should:
- review questionnaire responses
- explore delivery context and constraints
- understand team dynamics and change history
- identify management support level
- discuss realistic time allocation

**Technical lead interview (45 minutes)**

In this interview, you should:
- review questionnaire responses
- deep-dive on technical environment
- understand security and compliance context
- identify technical blockers
- discuss integration approach

**Interview tips**

For all interviews, you should:
- use the questionnaire responses as starting point
- ask open-ended follow-up questions
- listen for unstated concerns
- note specific examples given
- identify potential champions

### Step 4: analysis and classification

**Analysis activities**

You must:
1. aggregate individual engineer responses
2. score each dimension based on all inputs
3. calculate average score
4. apply override rules if applicable
5. identify specific risks and blockers
6. draft initial roadmap recommendations

**Classification review**

You must:
- discuss borderline cases with assessment team
- consider qualitative factors not captured in the scoring
- ensure classification feels right given overall picture

### Step 5: roadmap planning session

**Session structure (60 to 90 minutes):**

| Segment | Duration | Content |
|---------|----------|---------|
| Assessment findings | 15 min | Share classification and key findings |
| Discussion | 20 min | Address questions, validate findings |
| Roadmap drafting | 30 min | Agree milestones and support approach |
| Next steps | 15 min | Confirm immediate actions |

**Roadmap elements to agree upon**

These are:
- the target go-live date for AI tools
- training approach and scheduling
- FDE support allocation
- key milestones and check-ins
- success metrics
- risk mitigations

---

## Support allocation guidelines

### FDE allocation by maturity

| Classification | FDE Model | Typical Allocation |
|----------------|-----------|-------------------|
| Starting | Embedded | 1 FDE dedicated for 2 to 4 weeks |
| Developing | Shared | 1 FDE across 2 to 3 teams, 2 to 3 days/week per team |
| Established | On-demand | FDE available for consultation, no regular allocation |

### Training allocation by maturity

| Classification | Training Approach |
|----------------|-------------------|
| Starting | Face-to-face workshops, guided hands-on sessions, daily support |
| Developing | Blended learning, mix of self-paced and facilitated sessions |
| Established | Self-paced modules, optional workshops, peer learning |

### Check-in frequency by maturity

| Classification | Check-in Frequency | Check-in Focus |
|----------------|-------------------|----------------|
| Starting | Daily (first 2 weeks), then twice weekly | Usage, blockers, immediate support needs |
| Developing | Weekly | Progress, emerging issues, training completion |
| Established | Bi-weekly or monthly | Metrics, optimisation, champion activities |

---

## Progression between levels

Teams are expected to progress through maturity levels during the programme.

### Progression criteria: Starting → Developing

| Criterion | Evidence Required |
|-----------|-------------------|
| Tool activation | 100% of licences activated |
| Basic proficiency | Team completing basic prompts successfully |
| Reduced resistance | No active resistance blocking adoption |
| Support need reduction | Can work independently for short periods |
| Training completion | Core training modules completed |

### Progression criteria: Developing → Established

| Criterion | Evidence Required |
|-----------|-------------------|
| Daily active usage | >80% of team using tools daily |
| Quality output | AI-generated code passing reviews consistently |
| Self-sufficiency | Minimal FDE support needed |
| Knowledge sharing | Team sharing tips and patterns internally |
| Champion active | At least one team champion contributing to community |

### Reassessment process

- formal reassessment at 4-week intervals during active adoption
- lightweight check weekly during FDE engagement
- progression decision made jointly by FDE, DM, and programme team

---

## Special circumstances

### High-constraint environments

Teams with significant security or technical constraints may require:

- extended assessment period
- security-focused deep-dive
- custom guardrails development
- delayed deployment pending approvals

### Teams under delivery pressure

For teams with imminent deadlines:

- consider delaying intensive adoption
- offer awareness training only
- schedule full adoption for post-delivery
- provide self-service resources for interested individuals

### Distributed or multi-site teams

Additional considerations include:

- assessing each location if practices differ
- considering timezone impact on support
- planning for remote training delivery
- ensuring consistent tooling across sites

### Mixed-maturity teams

If assessment reveals significant variation within a team, you should:

- consider splitting into cohorts
- pair experienced with inexperienced members
- provide differentiated training paths
- use internal champions for peer support

---

## Reporting and governance

### Assessment outputs

Each assessment produces:

| Output | Audience | Purpose |
|--------|----------|---------|
| Assessment summary | Team, Programme | Overview of findings and classification |
| Detailed scoring | Programme team | Supporting evidence for classification |
| Risk register entries | Governance | Risks requiring monitoring |
| Roadmap | Team, Programme | Agreed adoption plan |

### Programme-level reporting

Assessment data feeds into:

- a weekly dashboard with teams assessed, classifications and blockers
- cohort analysis whith patterns across similar teams
- resource planning, including FDE allocation and scheduling
- risk reporting with aggregated risks across programme

### Continuous improvement

Assessment process improvements are based on:

- assessor feedback after each assessment
- team feedback on assessment experience
- accuracy of classifications such as *'did the support level prove appropriate?'*
- time-to-proficiency by classification

---

## Related documents

- [Team Classification Guide](team-classification-guide.md) - Detailed classification criteria
- [Delivery Manager Assessment](assessment-questionnaires/delivery-manager-assessment.md) - DM questionnaire
- [Technical Lead Assessment](assessment-questionnaires/technical-lead-assessment.md) - Tech Lead questionnaire
- [Individual Engineer Assessment](assessment-questionnaires/individual-engineer-assessment.md) - Engineer questionnaire

## References

- [DSIT AI Engineering Lab Programme Implementation Plan](/) - Programme context
- [Government Digital Service Capability Framework](https://www.gov.uk/government/collections/digital-data-and-technology-profession-capability-framework)
