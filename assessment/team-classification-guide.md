> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Team Classification Guide

> Detailed criteria and guidance for classifying teams as Starting, Developing, or Established.

## Purpose

This guide provides detailed criteria for classifying teams following the maturity assessment. It helps assessors make consistent classification decisions and helps teams understand what their classification means.

Use this guide to:

- Make consistent classification decisions across teams
- Explain classification rationale to teams
- Identify specific areas for improvement
- Plan appropriate support interventions

For the full assessment process, see [Maturity Assessment Framework](maturity-assessment-framework.md).

---

## Classification overview

| Level | Description | Support Model | Typical Programme Duration |
|-------|-------------|---------------|---------------------------|
| **Starting** | Teams requiring intensive support to begin adoption | Embedded FDE, high-touch | 6-8 weeks to Developing |
| **Developing** | Teams building proficiency with moderate support | Shared FDE, blended | 4-6 weeks to Established |
| **Established** | Teams ready for self-sufficient adoption | On-demand consultation | Ongoing self-service |

---

## Starting classification

### Profile summary

Starting teams have limited AI assistant experience, face significant constraints, or have substantial barriers to adoption. They require intensive, hands-on support to successfully begin using AI coding assistants.

### Identifying characteristics

#### Technical indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Complex legacy environment | Mainframe, COBOL, outdated frameworks, minimal tooling |
| Non-standard development setup | No consistent IDE, complex local environment requirements |
| Limited CI/CD maturity | Manual deployments, no automated testing pipeline |
| Security constraints | Air-gapped networks, complex approval processes, OFFICIAL-SENSITIVE+ data |
| Poor documentation | Tribal knowledge, outdated or missing architecture docs |

#### Team indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Limited AI experience | <20% of team have used any AI coding tools |
| Junior-heavy composition | >50% of team are junior engineers |
| High turnover | Significant team changes in past 6 months |
| Knowledge silos | Key knowledge held by 1-2 individuals |
| Limited learning culture | No time allocated for learning, no knowledge sharing |

#### Delivery indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Critical deadline pressure | Major delivery commitment within 8 weeks |
| Change fatigue | Team has undergone major changes recently |
| No protected time | Cannot allocate any time for training or adoption |
| Uncertain management support | Manager ambivalent or unsupportive |
| Resource constraints | Team understaffed for current commitments |

#### Attitude indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Active resistance | Vocal opposition from team members |
| Strong scepticism | "This won't work for us" mindset |
| Job security concerns | Fear that AI will replace engineers |
| Previous negative experience | Bad experience with AI tools or failed initiatives |
| Trust issues | Distrust of management motives for adoption |

### Support approach for Starting teams

| Element | Approach |
|---------|----------|
| FDE model | Embedded (dedicated FDE for 2-4 weeks) |
| Training | Face-to-face workshops, guided hands-on |
| Check-ins | Daily during first 2 weeks |
| Change management | High-touch, address resistance directly |
| Focus | Build basic confidence, quick wins, address concerns |

### What Starting teams need to progress

1. **Basic tool proficiency** - Team can use AI for simple tasks
2. **Reduced resistance** - No active blockers to adoption
3. **Established workflows** - AI integrated into daily work
4. **Support sustainability** - Can work independently for short periods
5. **Champion emergence** - At least one enthusiastic team member

---

## Developing classification

### Profile summary

Developing teams have foundational capabilities or some AI experience. They need moderate support to build proficiency and establish sustainable practices. Most teams enter at or quickly progress to this level.

### Identifying characteristics

#### Technical indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Standard tooling | Common IDEs, modern version control |
| Reasonable CI/CD | Automated builds, some automated testing |
| Mixed codebase | Some legacy, some modern code |
| Manageable constraints | Security requirements understood and addressed |
| Basic documentation | README exists, some architecture documentation |

#### Team indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Some AI experience | 20-50% of team have used AI coding tools |
| Mixed experience levels | Balance of junior, mid, and senior engineers |
| Stable core team | Some changes but core team intact |
| Knowledge sharing exists | Some demos, documentation, or pairing |
| Learning interest | Team interested in improving practices |

#### Delivery indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Moderate pressure | Deliverables but manageable workload |
| Some capacity | Can allocate 2-4 hours/week for adoption activities |
| Management support | Manager supportive of adoption |
| Reasonable stability | No major changes imminent |

#### Attitude indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Cautiously positive | Open to trying, want to see results |
| Some concerns | Questions about quality, security, workflow |
| Mixed enthusiasm | Some keen, some neutral, few resistant |
| Pragmatic mindset | "Show me it works" attitude |
| Potential champions | 1-2 people who could become champions |

### Support approach for Developing teams

| Element | Approach |
|---------|----------|
| FDE model | Shared (FDE across 2-3 teams, 2-3 days/week) |
| Training | Blended (self-paced + facilitated sessions) |
| Check-ins | Weekly |
| Change management | Standard approach, address concerns as they arise |
| Focus | Build proficiency, advanced techniques, identify champions |

### What Developing teams need to progress

1. **Consistent daily usage** - >80% of team using tools daily
2. **Quality output** - AI-generated code passing reviews consistently
3. **Advanced techniques** - Team using context engineering, complex prompting
4. **Self-sufficiency** - Minimal FDE support needed
5. **Active champion** - At least one person supporting others, contributing to community

---

## Established classification

### Profile summary

Established teams are ready for self-sufficient AI Engineering Lab adoption. They have strong foundational practices, experienced team members, and positive attitudes. They require minimal direct support and can serve as role models for other teams.

### Identifying characteristics

#### Technical indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Modern tooling | Standardised IDE, modern frameworks |
| Mature CI/CD | Comprehensive automated testing, continuous deployment |
| Well-maintained codebase | Low technical debt, regular refactoring |
| Clear security posture | Security requirements clear and met |
| Strong documentation | Up-to-date docs, architecture decision records |

#### Team indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Significant AI experience | >50% of team have used AI coding tools |
| Senior presence | Strong senior engineers who mentor others |
| Stable team | Low turnover, strong team cohesion |
| Active learning culture | Regular learning activities, conference attendance |
| Strong knowledge sharing | Pairing, mob programming, internal tech talks |

#### Delivery indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Manageable workload | Sustainable pace, time for improvement |
| Capacity for adoption | Can dedicate meaningful time to AI adoption |
| Strong management support | Manager actively championing adoption |
| Proactive improvement | Team seeks out improvement opportunities |

#### Attitude indicators

| Indicator | What it looks like |
|-----------|-------------------|
| Enthusiastic | Eager to use and experiment with AI tools |
| Confident | Comfortable trying new approaches |
| Quality-focused | Want AI to improve quality, not just speed |
| Willing to share | Happy to help other teams, contribute to programme |
| Champions present | Multiple people who could lead adoption |

### Support approach for Established teams

| Element | Approach |
|---------|----------|
| FDE model | On-demand consultation |
| Training | Self-paced with optional advanced workshops |
| Check-ins | Bi-weekly or monthly |
| Change management | Light-touch, team self-manages |
| Focus | Optimisation, advanced use cases, champion development |

### Role of Established teams in programme

Established teams contribute to the broader programme:

| Contribution | Description |
|--------------|-------------|
| Champions | Provide champions for community of practice |
| Case studies | Share success stories and lessons learned |
| Pattern development | Pioneer advanced patterns for repository |
| Peer support | Help other teams through community channels |
| Demos | Showcase effective AI usage to other departments |

---

## Classification decision guide

### Decision flowchart

```
START
  │
  ├─► Are there blocking security/compliance issues?
  │     YES → Cannot proceed (resolve first)
  │     NO ↓
  │
  ├─► Is there active, widespread resistance (>50% team)?
  │     YES → Starting (address resistance first)
  │     NO ↓
  │
  ├─► Is there a critical deadline within 4 weeks?
  │     YES → Starting (or defer adoption)
  │     NO ↓
  │
  ├─► Has <20% of team used AI coding tools?
  │     YES → Likely Starting
  │     NO ↓
  │
  ├─► Has >50% of team used AI coding tools AND
  │   team has strong practices AND
  │   team is enthusiastic?
  │     YES → Likely Established
  │     NO ↓
  │
  └─► Default → Developing
```

### Scoring-based classification

If using dimension scoring from the [Maturity Assessment Framework](maturity-assessment-framework.md):

| Average Score | Classification |
|---------------|----------------|
| 1.0 - 1.7 | Starting |
| 1.8 - 2.4 | Developing |
| 2.5 - 3.0 | Established |

### Override conditions

Certain conditions override the score-based classification:

| Condition | Override |
|-----------|----------|
| No security approval | Maximum: Starting |
| Critical deadline within 4 weeks | Maximum: Starting |
| >50% active resistance | Maximum: Starting |
| No management support | Maximum: Starting |
| Air-gapped environment (cloud tools) | Not suitable for cloud AI tools |
| Active champions + >80% daily usage | Minimum: Developing |

### Borderline cases

For teams scoring near classification boundaries (e.g., 1.7-1.8 or 2.4-2.5):

1. **Review qualitative factors** - Do interview notes suggest higher or lower?
2. **Consider trajectory** - Is the team improving or facing new challenges?
3. **Apply "benefit of doubt"** - When uncertain, classify lower to ensure adequate support
4. **Document rationale** - Record why borderline decision was made
5. **Plan early reassessment** - Schedule check-in at 2 weeks instead of 4

---

## Dimension-specific guidance

### Technical environment scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | Non-standard IDEs, legacy VCS, no CI/CD, manual deployments, >70% legacy code, complex local setup |
| 2 (Developing) | Standard IDE with some variation, Git workflows, basic CI/CD, 30-70% legacy code, documented setup |
| 3 (Established) | Standardised IDE, mature Git practices, comprehensive CI/CD, <30% legacy, containerised/automated setup |

### Team composition scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | >50% junior, <20% AI experience, limited learning time, siloed knowledge |
| 2 (Developing) | Mixed levels, 20-50% AI experience, some learning activities, some knowledge sharing |
| 3 (Established) | Strong senior presence, >50% AI experience, active learning culture, systematic knowledge transfer |

### Delivery context scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | Critical deadline <8 weeks, recent major changes, no time for training, uncertain management support |
| 2 (Developing) | Moderate pressure, some recent changes, can allocate some time, supportive management |
| 3 (Established) | Manageable workload, stable period, can dedicate time, management actively championing |

### Security posture scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | OFFICIAL-SENSITIVE+, significant restrictions, complex compliance, security concerns unresolved |
| 2 (Developing) | OFFICIAL-SENSITIVE with controls, some restrictions, moderate compliance, security engaged |
| 3 (Established) | OFFICIAL only, standard requirements, security approved, clear posture |

### Attitudes scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | Sceptical/resistant, significant concerns, no champions, negative prior experience |
| 2 (Developing) | Cautiously positive, some concerns, potential champions, mixed enthusiasm |
| 3 (Established) | Enthusiastic, concerns managed, active champions, positive prior experience |

### Ways of working scoring

| Score | Criteria |
|-------|----------|
| 1 (Starting) | Informal/no standards, limited testing, minimal docs, high technical debt |
| 2 (Developing) | Documented but inconsistent standards, reasonable testing, basic docs, moderate debt |
| 3 (Established) | Clear enforced standards, comprehensive testing, good docs, managed debt |

---

## Common classification scenarios

### Scenario 1: Legacy modernisation team

**Context:** Team maintaining 15-year-old Java application, planning modernisation.

**Assessment findings:**
- Technical: Java 8, Subversion, limited CI/CD (Score: 1)
- Team: Mixed experience, 30% used AI tools (Score: 2)
- Delivery: Modernisation starting in 3 months (Score: 2)
- Security: OFFICIAL, standard requirements (Score: 3)
- Attitudes: Interested, see AI helping modernisation (Score: 2)
- Ways of working: Basic standards, reasonable testing (Score: 2)

**Average: 2.0 → Developing**

**Rationale:** Despite legacy technical environment, team is stable, has capacity, and sees AI as helpful for modernisation. Developing classification with focus on legacy-specific techniques.

---

### Scenario 2: High-pressure delivery team

**Context:** Team building new citizen-facing service with go-live in 6 weeks.

**Assessment findings:**
- Technical: Modern stack, good CI/CD (Score: 3)
- Team: Experienced, 60% used AI tools (Score: 3)
- Delivery: Critical deadline in 6 weeks (Score: 1)
- Security: OFFICIAL, approved (Score: 3)
- Attitudes: Enthusiastic but time-poor (Score: 2)
- Ways of working: Strong practices (Score: 3)

**Average: 2.5 → Established**

**However:** Critical deadline override applies.

**Classification: Starting (deferred)**

**Rationale:** Despite strong indicators, team cannot allocate time for adoption. Recommend deferring intensive adoption until after go-live, with self-service resources available for interested individuals now.

---

### Scenario 3: Security-constrained team

**Context:** Team working on law enforcement system with strict security requirements.

**Assessment findings:**
- Technical: Modern but constrained environment (Score: 2)
- Team: Experienced, 40% AI experience (Score: 2)
- Delivery: Manageable workload (Score: 3)
- Security: OFFICIAL-SENSITIVE, significant constraints (Score: 1)
- Attitudes: Positive but cautious about security (Score: 2)
- Ways of working: Strong practices (Score: 3)

**Average: 2.2 → Developing**

**Rationale:** Developing classification but with security-focused onboarding. FDE engagement should prioritise guardrails configuration and security-safe workflows. May need extended timeline for security approvals.

---

### Scenario 4: Resistant team

**Context:** Team where engineers are sceptical about AI tools.

**Assessment findings:**
- Technical: Good environment (Score: 3)
- Team: Experienced but negative prior AI experience (Score: 2)
- Delivery: Reasonable capacity (Score: 2)
- Security: Standard (Score: 3)
- Attitudes: 40% resistant, 30% neutral, 30% positive (Score: 1)
- Ways of working: Strong (Score: 3)

**Average: 2.3 → Developing**

**Rationale:** Despite good technical foundations, attitude score pulls down average. Developing classification with heavy change management focus. FDE should prioritise working with resistant individuals, demonstrating value, and building from the 30% who are positive.

---

### Scenario 5: Champion-ready team

**Context:** Team with several AI enthusiasts already experimenting.

**Assessment findings:**
- Technical: Modern, well-maintained (Score: 3)
- Team: Mixed, but 3 engineers already using AI extensively (Score: 3)
- Delivery: Stable, capacity available (Score: 3)
- Security: OFFICIAL, approved (Score: 3)
- Attitudes: Enthusiastic, multiple potential champions (Score: 3)
- Ways of working: Strong practices (Score: 3)

**Average: 3.0 → Established**

**Rationale:** Clear Established classification. Focus on enabling existing enthusiasts as champions, capturing their patterns for repository, and connecting them to community. Light-touch support only.

---

## Classification communication

### Communicating to teams

When sharing classification with teams:

**Do:**
- Explain what the classification means for support they'll receive
- Frame as "matching support to needs" not judgement
- Highlight strengths identified in assessment
- Be clear about path to progression
- Answer questions openly

**Don't:**
- Present as a grade or ranking
- Compare teams to each other
- Make teams feel "behind"
- Suggest classification is permanent
- Dismiss concerns about classification

### Template for classification communication

```
Team Classification Summary

Team: [Name]
Classification: [Starting/Developing/Established]
Assessment date: [Date]

What this means:
[2-3 sentences explaining the classification and support model]

Key strengths identified:
- [Strength 1]
- [Strength 2]
- [Strength 3]

Areas for development:
- [Area 1]
- [Area 2]

Your support plan:
- FDE model: [Embedded/Shared/On-demand]
- Training: [Approach]
- Check-in frequency: [Frequency]

Next steps:
1. [Immediate action]
2. [Short-term action]
3. [Medium-term goal]

Questions? Contact [Name] at [Email]
```

---

## Reassessment and progression

### When to reassess

| Trigger | Action |
|---------|--------|
| Scheduled interval | Every 4 weeks during active adoption |
| Significant change | Team composition, delivery context, or technical environment changes |
| Progression request | Team believes they've met progression criteria |
| Support concern | FDE or DM believes classification doesn't match reality |

### Progression approval

| Transition | Approval required |
|------------|-------------------|
| Starting → Developing | FDE + Programme team |
| Developing → Established | FDE + Programme team |
| Downgrade (any) | Programme team + DM agreement |

### Documenting progression

Record:
- Previous classification and date
- New classification and date
- Evidence supporting change
- Updated support plan
- Next reassessment date

---

## Related documents

- [Maturity Assessment Framework](maturity-assessment-framework.md) - Full assessment process
- [Delivery Manager Assessment](assessment-questionnaires/delivery-manager-assessment.md) - DM questionnaire
- [Technical Lead Assessment](assessment-questionnaires/technical-lead-assessment.md) - Tech Lead questionnaire
- [Individual Engineer Assessment](assessment-questionnaires/individual-engineer-assessment.md) - Engineer questionnaire