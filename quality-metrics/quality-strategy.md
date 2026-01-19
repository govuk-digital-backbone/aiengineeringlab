> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab Quality Strategy

> Strategic framework for measuring success and demonstrating value across the AI Engineering Lab programme.

## Purpose

This strategy defines what success looks like for AI Engineering Lab adoption and how we measure it. It provides a consistent approach across all participating departments while allowing flexibility for local context.

Use this strategy to:

- Understand programme success criteria and targets
- Align departmental measurement with programme goals
- Report consistently across the programme
- Make evidence-based decisions about adoption approach

For practical implementation guidance, see [Measurement Playbook](measurement-playbook.md).

---

## Strategic objectives

The AI Engineering Lab programme aims to achieve five strategic objectives:

| Objective | Description | Why it matters |
|-----------|-------------|----------------|
| **Adoption** | AI tools actively used by allocated engineers | Investment only delivers value if tools are used |
| **Productivity** | Measurable improvement in engineer efficiency | Core value proposition of AI assistants |
| **Quality** | Code quality maintained or improved | Speed must not sacrifice quality |
| **Satisfaction** | Positive engineer and stakeholder experience | Sustainable adoption requires satisfaction |
| **Sustainability** | Adoption continues beyond programme support | Long-term value, not temporary uplift |

---

## Success criteria

### Programme-level targets

These targets apply across the AI Engineering Lab programme:

| Metric | Target | Rationale |
|--------|--------|-----------|
| Licence activation | 100% within 48 hours | Previous trial achieved only 66-75%; structured support should achieve full activation |
| Daily active usage | >80% of activated licences | High usage indicates tools embedded in workflow |
| Training attendance | ≥70% of allocated users | Training correlates with successful adoption |
| Training satisfaction | ≥8.0/10 | Quality training accelerates proficiency |
| Champion engagement | 200 identified, 50+ actively contributing | Champions sustain adoption beyond programme |
| Use cases documented | ≥2 with measured benefits | Evidence base for future investment |
| Reusable blueprint | Complete and validated | Enables wider public sector rollout |

### Tiered success framework

Success builds progressively through four tiers:

```
┌─────────────────────────────────────────────────────────────┐
│  Tier 4: BUSINESS OUTCOMES                                  │
│  Faster delivery, reduced costs, increased capacity         │
├─────────────────────────────────────────────────────────────┤
│  Tier 3: QUALITY & DELIVERY                                 │
│  Maintained quality, improved throughput, reduced rework    │
├─────────────────────────────────────────────────────────────┤
│  Tier 2: PRODUCTIVITY                                       │
│  Time savings, faster task completion, efficiency gains     │
├─────────────────────────────────────────────────────────────┤
│  Tier 1: ADOPTION                                           │
│  Tools activated, actively used, training completed         │
└─────────────────────────────────────────────────────────────┘
```

**Progression principle:** Higher tiers only matter if lower tiers are achieved. There's no productivity gain without adoption; no business outcome without sustained quality.

---

## Tier 1: Adoption metrics

**Question answered:** Are people using the tools?

### Metrics

| Metric | Definition | Target | Measurement frequency |
|--------|------------|--------|----------------------|
| Licence activation rate | Licences activated / Licences allocated | 100% within 48 hours | Daily during rollout |
| Daily active users (DAU) | Users with activity today / Activated users | >80% | Daily |
| Weekly active users (WAU) | Users with activity this week / Activated users | >90% | Weekly |
| Training completion | Users completing core training / Allocated users | ≥70% | Weekly |
| Feature adoption breadth | Features used per user (completion, chat, etc.) | Increasing trend | Monthly |

### Leading indicators

Early warning signs of adoption issues:

| Indicator | Warning threshold | Action trigger |
|-----------|-------------------|----------------|
| Activation delay | >48 hours | Immediate outreach |
| DAU decline | <70% for 3 consecutive days | FDE intervention |
| Training non-attendance | <50% by week 2 | DM escalation |
| Feature usage narrow | Only 1 feature used after 2 weeks | Additional training |

### Segmentation

Analyse adoption by:

- Department
- Team maturity level (Starting/Developing/Established)
- Tool (Copilot/Claude/Q/Gemini)
- Role (engineer/tech lead/etc.)
- Work type (modernisation/greenfield/maintenance)

---

## Tier 2: Productivity metrics

**Question answered:** Are engineers more efficient?

### Metrics

| Metric | Definition | Target | Measurement frequency |
|--------|------------|--------|----------------------|
| Suggestion acceptance rate | AI suggestions accepted / Suggestions shown | Baseline + positive trend | Weekly |
| Time on task | Time to complete comparable tasks | Decreasing vs baseline | Sprint |
| Code commit frequency | Commits per engineer per day | Increasing vs baseline | Weekly |
| Lead time for changes | Time from commit to production | Decreasing vs baseline | Sprint |
| Engineer velocity | Story points per engineer per sprint | Baseline + improvement | Sprint |

### Productivity targets (indicative)

Based on industry benchmarks and programme evidence:

| Metric | Indicative target | Notes |
|--------|-------------------|-------|
| Commit frequency | +15% by month 3 | More frequent, smaller commits |
| Lead time | -20% | Faster path to production |
| Code review cycle time | -25% | Faster reviews with AI assistance |
| Time on routine tasks | -30 to 50% | Largest gains on boilerplate, tests |

### Measurement cautions

- Compare teams to their own baselines, not each other
- Account for sprint-to-sprint variation
- Control for team changes, holidays, major releases
- Balance speed metrics with quality metrics

---

## Tier 3: Quality and delivery metrics

**Question answered:** Is the code good and delivery reliable?

### Metrics

| Metric | Definition | Target | Measurement frequency |
|--------|------------|--------|----------------------|
| Defect density | Defects per story/feature | Maintain or reduce | Sprint |
| Change failure rate | Failed deployments / Total deployments | Maintain or reduce | Monthly |
| Code review findings | Significant issues per PR | Maintain or reduce | Sprint |
| Test coverage | % code covered by automated tests | Maintain or increase | Sprint |
| Technical debt score | SonarQube or equivalent | Maintain or improve | Monthly |
| Rework rate | Stories reopened / Stories completed | Maintain or reduce | Sprint |

### Quality targets

| Metric | Target | Rationale |
|--------|--------|-----------|
| Defect density | -15 to 20% | AI should reduce errors, not increase them |
| Change failure rate | Maintain or reduce | Speed must not sacrifice stability |
| Test coverage | Maintain or +5-10% | AI-assisted test generation should improve coverage |
| Technical debt | -20% remediation cost | AI helps address debt faster |

### Quality safeguards

To ensure AI adoption doesn't compromise quality:

| Safeguard | Implementation |
|-----------|----------------|
| Mandatory code review | All AI-generated code reviewed by human |
| Security scanning | AI code passes same security checks |
| Test requirements | AI-generated code must include tests |
| Quality gates | CI/CD gates unchanged or strengthened |

---

## Tier 4: Business outcome metrics

**Question answered:** Is the programme delivering organisational value?

### Metrics

| Metric | Definition | Target | Measurement frequency |
|--------|------------|--------|----------------------|
| Time to delivery | Calendar time to deliver features | Decreasing | Quarterly |
| Development cost per feature | Total cost / Features delivered | Decreasing | Quarterly |
| Effective capacity | Work delivered without headcount increase | Increasing | Quarterly |
| Contractor dependency | Contractor ratio or spend | Decreasing | Quarterly |
| Engineer retention | Turnover rate | Maintaining or improving | Annually |
| Service delivery improvement | User-facing service metrics | Improving | Quarterly |

### Business case alignment

Connect metrics to government priorities:

| Priority | Related metrics |
|----------|-----------------|
| Efficiency savings | Cost per feature, contractor reduction |
| Digital transformation acceleration | Time to delivery, capacity increase |
| Civil service capability | Skills development, contractor reduction |
| Service quality | Defect rates, service delivery metrics |

### Long-term value indicators

| Indicator | Measurement | Target |
|-----------|-------------|--------|
| Self-sufficiency | Teams operating without FDE support | >80% by programme end |
| Community health | Active champions, community engagement | Growing engagement |
| Knowledge assets | Repository contributions, reusable materials | Comprehensive coverage |
| Replication readiness | Blueprint completeness | Ready for Phase 2 |

---

## Satisfaction metrics

**Question answered:** How do people feel about it?

### Engineer satisfaction

| Metric | Definition | Target | Frequency |
|--------|------------|--------|-----------|
| Overall satisfaction | "How satisfied are you with AI tools?" (1-10) | ≥8.0 | Monthly |
| Net Promoter Score | "Would you recommend to a colleague?" (-100 to +100) | Positive | Monthly |
| Confidence level | "How confident are you using AI tools?" (1-10) | Increasing | Monthly |
| Workflow integration | "AI tools fit well into my workflow" (1-5) | ≥4.0 | Monthly |
| Training satisfaction | Post-training survey score | ≥8.0 | Post-training |

### Stakeholder satisfaction

| Stakeholder | Key concerns | Measurement |
|-------------|--------------|-------------|
| Technical leads | Quality, standards compliance | Quarterly survey |
| Delivery managers | Delivery performance, team health | Quarterly survey |
| SROs | Value for money, risk management | Quarterly review |
| Security teams | Compliance, incident rates | Quarterly review |

### Sentiment tracking

Beyond scores, track qualitative sentiment:

| Channel | Frequency | Analysis |
|---------|-----------|----------|
| Survey free text | Monthly | Theme extraction |
| Retrospective feedback | Per sprint | Issue identification |
| Community channels | Ongoing | Sentiment monitoring |
| FDE observations | Per engagement | Qualitative insights |

---

## Adaptability metrics

Beyond measuring adoption and productivity, tracking adaptability helps ensure teams and the programme can respond to change and sustain success long-term.

### Why measure adaptability

| Reason | Description |
|--------|-------------|
| Sustain adoption | Adaptable teams maintain adoption through changes in tools, team composition, and priorities |
| Scale effectively | Adaptability indicators predict readiness to expand AI usage |
| Build resilience | Teams that adapt well recover faster from setbacks |
| Future-proof investment | Adaptable workforce can adopt future AI capabilities |

### Adaptability dimensions

#### Operational agility

**Question answered:** How flexibly can teams respond to changing needs?

| Metric | Definition | Leading/Lagging | Target |
|--------|------------|-----------------|--------|
| Cross-tool proficiency | % of engineers proficient in 2+ AI tools | Leading | >30% by programme end |
| Team onboarding time | Days to onboard new team to AI tools | Lagging | Decreasing trend |
| FDE redeployment speed | Days to redeploy FDE to new team | Leading | <5 days |
| Support request resolution | Time to resolve AI-related issues | Lagging | Decreasing trend |
| Practice adoption speed | Time from new practice introduced to team adoption | Lagging | Decreasing trend |

**Operational agility indicators:**

| Indicator | What it signals | How to measure |
|-----------|-----------------|----------------|
| Teams sharing practices | Knowledge flows across teams | Cross-team contributions to repository |
| Self-service resolution | Teams solve problems independently | % of issues resolved without FDE |
| Rapid experimentation | Teams try new AI features/techniques | New feature adoption within 2 weeks of release |

---

#### Workforce readiness

**Question answered:** Are people equipped for current and future AI-assisted development?

| Metric | Definition | Leading/Lagging | Target |
|--------|------------|-----------------|--------|
| Skills currency | % of team trained on latest tool features | Leading | >80% within 4 weeks of major updates |
| Learning velocity | Time from training to demonstrated competency | Lagging | Decreasing trend |
| Champion density | Champions per 100 engineers | Leading | ≥2 per 100 engineers |
| Knowledge contribution | Repository contributions per team | Leading | ≥1 per team per quarter |
| Willingness to change | Survey score on openness to new practices | Leading | ≥4.0/5 |
| Internal mobility | Engineers moving to AI-focused roles/projects | Lagging | Increasing trend |

**Workforce readiness indicators:**

| Indicator | What it signals | How to measure |
|-----------|-----------------|----------------|
| Proactive learning | Engineers seek out AI skills | Self-initiated training completion |
| Peer teaching | Knowledge multiplies through team | Champion-led sessions delivered |
| Experimentation culture | Safe to try and fail | New techniques tried per sprint |
| Career development | AI skills valued in progression | AI skills in role expectations |

---

### Measuring adaptability in practice

#### Team adaptability assessment

Add these questions to periodic team assessments:

```markdown
## Adaptability Check-in

1. How confident is the team in adopting new AI features? (1-5)

2. How quickly could the team onboard a new member to AI tools?
   [ ] <1 week  
   [ ] 1-2 weeks  
   [ ] 2-4 weeks  
   [ ] >4 weeks

3. If your primary AI tool was unavailable, could the team use an alternative?
   [ ] Yes, immediately  
   [ ] Yes, with some adjustment  
   [ ] No

4. How often does the team experiment with new AI techniques?
   [ ] Weekly  
   [ ] Monthly  
   [ ] Quarterly  
   [ ] Rarely

5. How many team members could help onboard another team?
   [ ] 0  
   [ ] 1-2  
   [ ] 3+
```

#### Programme adaptability dashboard

| Metric | Current | Target | Trend |
|--------|---------|--------|-------|
| Cross-tool proficiency | X% | >30% | ↑↓→ |
| Average team onboarding time | X days | <10 days | ↑↓→ |
| Champion density | X per 100 | ≥2 per 100 | ↑↓→ |
| Self-service resolution rate | X% | >70% | ↑↓→ |
| Willingness to change score | X/5 | ≥4.0/5 | ↑↓→ |

---

### Adaptability maturity levels

| Level | Characteristics | Indicators |
|-------|-----------------|------------|
| **Reactive** | Teams struggle with change, heavily dependent on support | Low self-service, slow onboarding, resistance to new features |
| **Responsive** | Teams adapt when required with moderate support | Moderate self-service, standard onboarding time, accept new features |
| **Proactive** | Teams anticipate and prepare for change | High self-service, fast onboarding, actively seek new features |
| **Generative** | Teams drive change and help others adapt | Contribute to repository, mentor other teams, champion new practices |

**Target:** Move all teams to at least "Responsive" by programme end, with 30% at "Proactive" or "Generative".

---

### Building adaptability

Actions to improve adaptability metrics:

| Metric gap | Intervention |
|------------|--------------|
| Low cross-tool proficiency | Introduce secondary tool familiarisation |
| Slow team onboarding | Create onboarding playbook, assign buddy |
| Low champion density | Targeted champion recruitment and enablement |
| Low willingness to change | Address concerns, showcase benefits, involve sceptics |
| Low knowledge contribution | Recognise contributions, reduce friction to contribute |
| High support dependency | Gradual support reduction, build self-service resources |

---

## Comparative analysis

### Cross-tool comparison

Where teams use different tools, compare:

| Dimension | Metrics |
|-----------|---------|
| Adoption speed | Time to >80% DAU |
| Productivity impact | Acceptance rate, time savings |
| Quality impact | Defect rates by tool |
| Satisfaction | Scores by tool |
| Cost effectiveness | Value delivered per licence cost |

**Caution:** Control for team differences. Tool comparisons require similar team contexts.

### Cross-department comparison

Compare departments on:

| Dimension | Purpose |
|-----------|---------|
| Adoption trajectory | Identify fast/slow adopters |
| Support efficiency | FDE time to achieve outcomes |
| Pattern effectiveness | Which approaches work best |
| Maturity progression | Speed through Starting→Developing→Established |

**Use for:** Identifying transferable practices, not ranking departments.

### Work type analysis

Compare by work type cohort:

| Work type | Specific metrics of interest |
|-----------|------------------------------|
| Modernisation | Legacy code understanding, refactoring speed |
| Greenfield | Time to first deployment, code quality |
| Maintenance | Bug fix time, regression rates |
| Data engineering | Pipeline development speed, data quality |
| Infrastructure | IaC development speed, deployment reliability |

---

## Reporting framework

### Report types and audiences

| Report | Frequency | Audience | Focus |
|--------|-----------|----------|-------|
| Operational dashboard | Real-time | Programme team | Adoption alerts, daily metrics |
| Weekly summary | Weekly | Programme team, DMs | Progress, issues, actions |
| Monthly report | Monthly | Programme board | Trends, insights, decisions |
| Quarterly review | Quarterly | SROs, senior leadership | Business outcomes, strategic direction |
| Final evaluation | Programme end | DSIT, senior stakeholders | Overall impact, lessons, recommendations |

### Dashboard design principles

| Principle | Implementation |
|-----------|----------------|
| Lead with headlines | Key metrics and alerts at top |
| Show trends | Direction matters more than point-in-time |
| Enable drill-down | Summary → department → team |
| Highlight exceptions | Automatic flagging of concerns |
| Provide context | Targets, baselines, explanations |

### Monthly report structure

```markdown
## AI Engineering Lab Monthly Report - [Month Year]

### Executive summary
- [3-5 bullet headlines]

### Programme health
| Metric | Target | Actual | Trend | Status |
|--------|--------|--------|-------|--------|
| [Metric] | [X] | [Y] | ↑↓→ | 🟢🟡🔴 |

### Adoption
- Licences activated: X/Y (Z%)
- Daily active users: X%
- Training completion: X%

### Productivity & quality
- [Key metrics with trend]

### Satisfaction
- Engineer satisfaction: X/10
- NPS: X

### Highlights
- [Successes and positive developments]

### Concerns and actions
| Concern | Impact | Action | Owner | Due |
|---------|--------|--------|-------|-----|

### Decisions required
- [Any decisions needed from board]

### Next month focus
- [Priorities for coming month]
```

---

## Governance and accountability

### Metric ownership

| Metric category | Data owner | Analysis owner | Action owner |
|-----------------|------------|----------------|--------------|
| Adoption | Programme operations | Programme operations | Programme Leads |
| Productivity | Department teams | Programme operations | FDEs, Tech leads |
| Quality | Department teams | Programme operations | Tech leads |
| Satisfaction | Programme operations | Programme operations | Programme Leads |
| Business outcomes | Departments | Programme operations | SROs |

### Review rhythm

| Review | Frequency | Participants | Decisions |
|--------|-----------|--------------|-----------|
| Daily stand-up | Daily | Programme team | Immediate interventions |
| Weekly review | Weekly | Programme leads | Tactical adjustments |
| Monthly board | Monthly | Programme board | Resource allocation, escalations |
| Quarterly steering | Quarterly | SROs, DSIT | Strategic direction |

### Escalation triggers

| Condition | Escalate to | Timeline |
|-----------|-------------|----------|
| Single team below adoption threshold | FDE lead | Within 48 hours |
| Department below adoption threshold | Programme board | Within 1 week |
| Quality metrics declining | Tech lead, Security | Within 1 week |
| Satisfaction below 6.0 | Programme board | Within 1 week |
| Programme-wide metric decline | SRO, DSIT | Immediate |

---

## Continuous improvement

### Metric review cycle

| Activity | Frequency | Purpose |
|----------|-----------|---------|
| Metric relevance review | Quarterly | Retire unused metrics, add emerging needs |
| Target calibration | Quarterly | Adjust targets based on evidence |
| Collection method audit | Quarterly | Ensure data quality |
| Benchmark update | Annually | Refresh industry comparisons |

### Learning loops

| Loop | Mechanism | Output |
|------|-----------|--------|
| Team → Programme | FDE reports, metrics | Pattern identification |
| Programme → Teams | Best practice sharing | Improved approaches |
| Programme → Repository | Documented learnings | Reusable knowledge |
| Programme → Future phases | Evaluation report | Blueprint refinement |

### Success pattern capture

When teams achieve strong results:

1. Identify the factors contributing to success
2. Document the approach and context
3. Assess transferability to other teams
4. Add to repository as recommended practice
5. Share through champion network

---

## Data quality and integrity

### Data quality principles

| Principle | Implementation |
|-----------|----------------|
| Accuracy | Validate data sources, cross-check anomalies |
| Completeness | Track coverage, address gaps |
| Timeliness | Define freshness requirements, monitor lag |
| Consistency | Use standard definitions, avoid ambiguity |

### Known data limitations

| Limitation | Impact | Mitigation |
|------------|--------|------------|
| Self-reported data | Potential bias | Triangulate with observed data |
| Tool analytics gaps | Incomplete picture | Supplement with surveys |
| Baseline variability | Comparison challenges | Document context |
| Attribution difficulty | Cannot isolate AI impact | Use control comparisons where possible |

### Data governance

| Requirement | Implementation |
|-------------|----------------|
| Privacy | Team-level aggregation minimum, no individual reporting |
| Security | Data classification OFFICIAL, secure storage |
| Retention | Retain for programme duration + 2 years |
| Access | Role-based access to dashboards and data |

---

## Related documents

- [Measurement Playbook](measurement-playbook.md) - Practical implementation guidance
- [Maturity Assessment Framework](../assessment/maturity-assessment-framework.md) - Team-level assessment

## References

- [DORA State of DevOps](https://dora.dev/) - Industry benchmarks
- [GDS Service Manual - Measuring success](https://www.gov.uk/service-manual/measuring-success)
- [HM Treasury Magenta Book](https://www.gov.uk/government/publications/the-magenta-book) - Evaluation guidance
