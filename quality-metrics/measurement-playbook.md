> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# AI Engineering Lab measurement playbook

> Practical guidance for implementing measurement and demonstrating the value of AI Engineering Lab adoption.

## Purpose

This playbook provides step-by-step guidance for collecting, analysing, and reporting metrics related to AI Engineering Lab adoption. It helps teams and programmes demonstrate value, identify issues early, and make data-driven decisions.

Use this playbook to:

- establish baseline metrics before AI tool deployment
- implement ongoing measurement during adoption
- create meaningful reports for stakeholders
- identify and respond to adoption issues
- build the evidence base for future investment

For the strategic measurement framework, see [Quality Strategy](quality-strategy.md).

---

## Measurement principles

### Measure what matters

Focus on metrics that:

| Principle | Guidance |
|-----------|----------|
| Drive decisions | If a metric will not change behaviour, reconsider collecting it |
| Are actionable | Teams should be able to influence the metric |
| Balance outcomes | Include adoption, productivity, quality, and satisfaction |
| Avoid gaming | Metrics should encourage desired behaviours |
| Respect privacy | Never measure individual engineer performance punitively |

### Start simple

Begin with a small set of core metrics, add complexity only when needed, automate collection where possible, and prioritise accuracy over comprehensiveness.

### Context matters

Compare teams to their own baselines, not other teams. Account for differences in work type, tech stack, and team composition. Recognise that metrics improve over time as proficiency grows.

---

## Leading versus lagging indicators

Understanding the difference between leading and lagging indicators helps in predicting problems before they impact outcomes and take timely corrective action.

### Definitions

| Type | Definition | Characteristics |
|------|------------|-----------------|
| Leading indicators | Predictive metrics that signal future performance | Early warning, actionable, influence outcomes |
| Lagging indicators | Outcome metrics that confirm what has happened | Historical, confirmatory, measure results |

Principle: monitor leading indicators to prevent problems and track lagging indicators to confirm success.

### AI Engineering Lab metrics classified

#### Adoption metrics

| Metric | Type | Why |
|--------|------|-----|
| Licence activation rate | Leading | Predicts future usage - no activation means no adoption |
| Daily active users | Leading | Early signal of engagement - decline predicts productivity issues |
| Training attendance | Leading | Training completion predicts proficiency and effective usage |
| Feature adoption breadth | Leading | Using multiple features predicts deeper, sustained adoption |
| Training satisfaction | Leading | Satisfaction predicts knowledge retention and application |

#### Productivity metrics

| Metric | Type | Why |
|--------|------|-----|
| Suggestion acceptance rate | Leading | High acceptance predicts productivity gains - declining rate signals issues |
| Time on task | Lagging | Confirms productivity improvement after adoption |
| Cycle time | Lagging | Outcome measure of delivery speed |
| Throughput (velocity) | Lagging | Confirms sustained productivity improvement |
| Code commit frequency | Leading | Early signal of changed working patterns |

#### Quality metrics

| Metric | Type | Why |
|--------|------|-----|
| Code review findings | Leading | Issues caught in review predict production defects |
| Test coverage | Leading | Coverage predicts defect detection capability |
| Security scan results | Leading | Vulnerabilities found early predict production security |
| Defect rate | Lagging | Confirms quality outcomes |
| Change failure rate | Lagging | Confirms deployment reliability |
| Technical debt score | Lagging | Confirms long-term code health |

#### Satisfaction metrics

| Metric | Type | Why |
|--------|------|-----|
| Engineer confidence | Leading | Confidence predicts sustained usage and advocacy |
| Training satisfaction | Leading | Satisfaction predicts skill application |
| Workflow integration score | Leading | Integration predicts sustained adoption |
| Engineer satisfaction | Lagging | Confirms overall experience |
| Net Promoter Score (NPS) | Lagging | Confirms advocacy and programme success |

#### Business outcome metrics

| Metric | Type | Why |
|--------|------|-----|
| Forward Deployed Engineer (FDE) support requests | Leading | Declining requests predict self-sufficiency |
| Champion activity | Leading | Active champions predict sustainable adoption |
| Time to delivery | Lagging | Confirms business value |
| Cost per feature | Lagging | Confirms efficiency gains |
| Contractor dependency | Lagging | Confirms capacity building |

### Using leading indicators for early intervention

Leading indicators enable proactive management. Define thresholds and responses:

| Leading indicator | Warning threshold | Action threshold | Response |
|-------------------|-------------------|------------------|----------|
| Licence activation | less than 90% at 48 hours | less than 80% at 1 week | Direct outreach to non-activated users |
| Daily active users | less than 75% for 3 days | less than 60% for 1 week | FDE intervention, identify blockers |
| Training attendance | less than 60% at week 2 | less than 50% at week 3 | DM escalation, reschedule sessions |
| Acceptance rate trend | Declining 2 weeks | Declining 3 weeks | Context engineering support |
| Engineer confidence | less than 3.5/5 average | less than 3.0/5 average | Additional training, address concerns |
| Code review findings | Increasing trend | more than 2x baseline | Reinforce review practices |
| FDE support requests | Not declining by week 4 | Increasing after week 4 | Assess readiness, extend support |

### Using lagging indicators for confirmation

Lagging indicators confirm whether interventions worked and outcomes were achieved:

| Lagging indicator | Confirms | Review frequency |
|-------------------|----------|------------------|
| Defect rate | Quality maintained during adoption | Sprint or monthly |
| Cycle time | Productivity gains realised | Sprint or monthly |
| Engineer satisfaction | Positive overall experience | Monthly |
| Time to delivery | Business value achieved | Quarterly |
| Contractor dependency | Capacity building successful | Quarterly |

### Balancing your measurement portfolio

A healthy measurement approach includes both types:

Recommended balance:
- 60% leading indicators (early warning, actionable) including adoption signals, engagement patterns, and quality predictors
- 40% lagging indicators (outcome confirmation) including productivity outcomes, quality outcomes, and business outcomes

Common pitfall: over-reliance on lagging indicators. By the time defect rates rise or satisfaction drops, the damage is done. Prioritise leading indicators for day-to-day management.

### Leading indicator dashboard

For operational monitoring, prioritise these leading indicators:

| Indicator | Target | Check frequency | Escalation |
|-----------|--------|-----------------|------------|
| Activation rate | 100% within 48 hours | Daily during rollout | Immediate if less than 80% |
| Daily active users | more than 80% | Daily | After 3 days less than 70% |
| Acceptance rate trend | Stable or improving | Weekly | After 2 weeks declining |
| Engineer confidence | 3.5/5 or higher | Bi-weekly | If less than 3.0 |
| Training completion | 70% or higher | Weekly | If less than 50% at midpoint |
| Code review issues | Stable or improving | Weekly | If increasing 2 sprints |

---

## Metric tiers

### Tier 1: adoption metrics

Purpose: are people using the tools?

| Metric | Definition | Target | Collection method |
|--------|------------|--------|-------------------|
| Licence activation | percentage of allocated licences activated | 100% within 48 hours | Tool admin console |
| Daily active users | percentage of activated users using tool daily | more than 80% | Tool analytics |
| Weekly active users | percentage of activated users using tool weekly | more than 90% | Tool analytics |
| Feature breadth | Number of features used (completion, chat, and similar) | Increasing over time | Tool analytics |

Why it matters: adoption metrics are leading indicators. Low adoption signals issues before they impact outcomes.

---

### Tier 2: productivity metrics

Purpose: is work getting done faster?

| Metric | Definition | Target | Collection method |
|--------|------------|--------|-------------------|
| Code suggestion acceptance rate | percentage of AI suggestions accepted | Baseline and trend | Tool analytics |
| Time to first commit | Time from task start to first commit | Decreasing | Git analytics |
| Cycle time | Time from commit to production | Decreasing | CI/CD analytics |
| Throughput | Stories or tasks completed per sprint | Baseline and improvement | Project management tool |

Why it matters: productivity metrics show whether AI tools are accelerating delivery.

Caution: productivity metrics can be misleading. More code is not always better. Balance with quality metrics.

---

### Tier 3: quality metrics

Purpose: is the code good?

| Metric | Definition | Target | Collection method |
|--------|------------|--------|-------------------|
| Defect rate | Defects per story or feature | Maintaining or decreasing | Issue tracking |
| Code review feedback | Rework requested in reviews | Maintaining or decreasing | Pull Request (PR) analytics |
| Security vulnerabilities | Issues found by SAST or DAST | Maintaining or decreasing | Security tools |
| Test coverage | percentage of code covered by tests | Maintaining or increasing | Test tooling |
| Technical debt | SonarQube or equivalent score | Maintaining or improving | Code analysis |

Why it matters: quality metrics ensure speed improvements do not sacrifice code quality.

---

### Tier 4: satisfaction metrics

Purpose: how do people feel about it?

| Metric | Definition | Target | Collection method |
|--------|------------|--------|-------------------|
| Engineer satisfaction | Survey score on AI tool experience | 8.0/10 or higher | Survey |
| Training satisfaction | Survey score on training quality | 8.0/10 or higher | Post-training survey |
| NPS | Would you recommend to a colleague? | Positive NPS | Survey |
| Confidence level | Self-reported confidence using tools | Increasing | Survey |

Why it matters: satisfied engineers adopt more deeply and sustain usage long-term.

---

### Tier 5: business outcome metrics

Purpose: is the programme delivering value?

| Metric | Definition | Target | Collection method |
|--------|------------|--------|-------------------|
| Time to delivery | Time to deliver features or services | Decreasing | Project tracking |
| Cost per feature | Development cost per feature | Decreasing | Financial tracking |
| Engineer capacity | Effective capacity increase | Measurable increase | Capacity planning |
| Contractor dependency | Ratio of contractors to civil servants | Decreasing | HR data |

Why it matters: business metrics justify continued investment and inform future phases.

Note: business metrics require longer timeframes to demonstrate change.

---

## Implementation steps

### Step 1: establish baselines (week 1 to 2)

Before deploying AI tools, capture current state metrics.

Baseline checklist:

1. Identify which metrics you will track.
2. Determine data sources for each metric.
3. Collect 4 to 8 weeks of historical data where available.
4. Document current values as baseline.
5. Note any contextual factors (team changes, major releases, and similar).

Baseline data to collect:

| Category | Data points |
|----------|-------------|
| Delivery | Sprint velocity, cycle time, throughput |
| Quality | Defect rates, code review metrics, test coverage |
| Engineer experience | Current satisfaction (if surveyed) |
| Team context | Team size, composition, current projects |

Baseline template:

```markdown
## Baseline metrics - [Team Name]

Baseline period: [start date] to [end date]
Collected by: [Name]
Collection date: [date]

### Delivery metrics
- Average sprint velocity: [X] story points
- Average cycle time: [X] days
- Average throughput: [X] stories or sprint

### Quality metrics
- Defect rate: [X] defects per story
- Average PR review cycles: [X]
- Test coverage: [X]%
- SonarQube score: [X]

### Team context
- Team size: [X] engineers
- Seniority mix: [X] junior, [X] mid, [X] senior
- Primary technology: [technology stack]
- Current project phase: [phase]

### Notes
[Any relevant context]
```

---

### Step 2: configure data collection (week 2 to 3)

Set up automated and manual data collection.

Automated collection:

| Data source | Metrics | Setup required |
|-------------|---------|----------------|
| AI tool admin console | Activation, usage, acceptance rates | Admin access, export schedule |
| Git, GitHub, or GitLab | Commit frequency, PR metrics | API integration or manual export |
| CI/CD platform | Build times, deployment frequency | Dashboard or API access |
| Issue tracker (Jira and similar) | Velocity, defects, cycle time | Report configuration |
| Code analysis (SonarQube) | Quality scores, coverage | Existing integration |

Manual collection:

| Data source | Metrics | Collection method |
|-------------|---------|-------------------|
| Engineer surveys | Satisfaction, confidence, NPS | Regular survey (monthly recommended) |
| Training feedback | Training satisfaction | Post-training survey |
| FDE observations | Qualitative insights | Engagement reports |
| Team retrospectives | Adoption feedback | Retro notes |

#### Survey template - engineer satisfaction:

```
AI Engineering Lab feedback survey

1. How satisfied are you with the AI Engineering Lab? (1 to 10)

2. How confident do you feel using the AI Engineering Lab? (1 to 10)

3. How often do you use the AI Engineering Lab? (select one)

- multiple times per day
- daily
- several times per week
- weekly or less
- rarely or never

4. Which features do you use most? (select all that apply)
- [ ] code completion
- [ ] chat or Q and A
- [ ] test generation
- [ ] documentation
- [ ] refactoring
- [ ] code explanation
- [ ] other: [specify]

5. What is working well?

[Free text]

6. What could be improved?

[Free text]

7. Would you recommend this tool to a colleague? (0 to 10 NPS)
```

---

### Step 3: implement monitoring dashboards (week 3 to 4)

Create dashboards for ongoing visibility.

#### Dashboard components:

| Section | Content | Audience |
|---------|---------|----------|
| Adoption summary | Activation percentage, daily active users, trend | All |
| Team breakdown | Per-team adoption metrics | Programme team |
| Productivity indicators | Acceptance rate, throughput trend | Technical leads |
| Quality indicators | Defect trend, coverage trend | Technical leads |
| Alerts | Teams below thresholds | Programme team |

#### Suggested tools:

Tools commonly used in government include Power BI, Grafana (if already in use), or simple spreadsheet for smaller programmes.

#### Alert thresholds:

| Metric | Warning threshold | Action threshold |
|--------|-------------------|------------------|
| Licence activation | less than 90% after 48 hours | less than 80% after 1 week |
| Daily active usage | less than 70% | less than 50% |
| Acceptance rate | Declining 3 consecutive weeks | Declined more than 20% from baseline |
| Satisfaction score | less than 7.0 | less than 6.0 |

---

### Step 4: establish reporting cadence (ongoing)

Set up regular reporting rhythms.

#### Reporting schedule:

| Report | Frequency | Audience | Content |
|--------|-----------|----------|---------|
| Adoption dashboard | Real-time | Programme team | Current metrics, alerts |
| Weekly summary | Weekly | Programme team, DMs | Important metrics, issues, actions |
| Monthly report | Monthly | Programme board, SROs | Trends, insights, decisions needed |
| Quarterly review | Quarterly | Senior leadership | Business impact, strategic recommendations |

#### Weekly summary template:

```markdown
## AI Engineering Lab weekly metrics summary

Week ending: [date]
Prepared by: [Name]

### Headlines
- [Important highlight or concern]
- [Important highlight or concern]

### Adoption
| Metric | This week | Last week | Trend |
|--------|-----------|-----------|-------|
| Activated licences | X/Y (Z%) | | up, down, or stable |
| Daily active users | X% | | up, down, or stable |

### Teams requiring attention
| Team | Issue | Action |
|------|-------|--------|
| [Team] | [Issue] | [Action planned] |

### Actions from last week
| Action | Status |
|--------|--------|
| [Action] | [Complete, in progress, or blocked] |

### Actions for next week
- [Action 1]
- [Action 2]
```

---

### Step 5: analyse and act on data (ongoing)

Turn data into insights and actions.

#### Analysis activities:

| Activity | Frequency | Purpose |
|----------|-----------|---------|
| Trend analysis | Weekly | Identify patterns over time |
| Cohort comparison | Monthly | Compare similar teams |
| Correlation analysis | Monthly | Understand relationships between metrics |
| Qualitative synthesis | Monthly | Combine survey feedback with quantitative data |

#### Common patterns and responses:

| Pattern | Possible causes | Recommended actions |
|---------|-----------------|---------------------|
| High activation, low daily usage | Tool not integrated into workflow, concerns, friction | FDE engagement, workflow integration support |
| Declining acceptance rate | Poor context, wrong use cases, frustration | Context engineering training, prompt improvement |
| Low satisfaction despite usage | Quality issues, forced adoption, unmet expectations | Survey deep-dive, address specific concerns |
| Quality metrics declining | Over-reliance without review, inadequate testing | Reinforce review practices, quality training |
| Team variation | Different maturity, tech stacks, support levels | Investigate outliers, share successful patterns |

#### Escalation criteria:

| Condition | Escalate to |
|-----------|-------------|
| Single team below thresholds | FDE and delivery manager |
| Multiple teams below thresholds | Programme board |
| Programme-wide metric decline | SRO |
| Security or quality incident | Security lead, SRO |

---

## Measuring specific scenarios

### Measuring a pilot team

For early pilot teams, collect richer data including detailed time tracking on specific tasks (with consent), before and after comparison on similar tasks, qualitative engineer diaries, and detailed error or issue logs.

#### Pilot measurement timeline:

| Phase | Duration | Focus |
|-------|----------|-------|
| Baseline | 2 weeks | Establish pre-AI metrics |
| Onboarding | 1 week | Track activation, initial issues |
| Early adoption | 2 to 4 weeks | Monitor learning curve, quick wins |
| Steady state | 4 weeks or more | Measure sustainable impact |
| Retrospective | 1 week | Comprehensive analysis, lessons learned |

---

### Measuring productivity gains

Productivity measurement requires care to avoid misleading conclusions.

#### Recommended approach:

1. Define comparable work units - stories of similar size, bug fixes, specific task types.
2. Control for variables - same engineer, similar complexity, similar codebase area.
3. Measure elapsed time - from task start to completion.
4. Account for quality - only count work that passes review.

What not to do:

- compare different engineers
- compare different types of work
- measure lines of code produced
- ignore quality in speed comparisons
- extrapolate from small samples

Productivity calculation example:

```
Task type: unit test creation for existing function
Sample size: 20 comparable tasks (10 pre-AI, 10 post-AI)

Pre-AI average: 45 minutes per function
Post-AI average: 18 minutes per function

Time reduction: 60%
Quality check: all tests passed review, coverage equivalent

Conclusion: 60% time reduction for unit test creation, quality maintained
```

---

### Measuring ROI

For business case and investment justification:

#### Cost components:

| Cost type | Elements |
|-----------|----------|
| Licence costs | Per-user fees, premium features |
| Implementation costs | Training time, FDE support, setup effort |
| Ongoing costs | Support, administration, training refresh |

#### Benefit components:

| Benefit type | Measurement approach |
|--------------|---------------------|
| Time savings | Hours saved × hourly rate |
| Quality improvements | Reduced defect remediation costs |
| Capacity increase | Additional work delivered without headcount |
| Contractor reduction | Contractor days replaced by productivity gain |

#### ROI calculation:

```
Annual benefit = (Hours saved per engineer × Number of engineers × Hourly rate)
                 + (Defect reduction × Average defect cost)
                 + (Additional features delivered × Feature value)

Annual cost = (Licence cost × Users)
              + (Training cost)
              + (Support cost)

ROI = (Annual benefit - Annual cost) / Annual cost × 100%
```

Caution: be conservative in benefit estimates. Overinflated ROI damages credibility.

---

### Measuring Return On Learning Investment (ROLI)

Beyond tool ROI, measuring the return on training and enablement investment demonstrates the value of the learning programme and identifies where to focus future investment.

#### Why measure ROLI:

Measuring ROLI helps justify training investment to stakeholders, identify which training formats deliver most value, optimise future training design, and demonstrate link between learning and outcomes.

#### ROLI framework:

```
ROLI = (Value of improved performance - Learning investment) / Learning investment × 100%
```

#### Learning investment components:

| Cost type | Elements | How to calculate |
|-----------|----------|------------------|
| Direct training costs | Facilitator time, materials, venues | Actual spend |
| Participant time | Hours in training × hourly rate | Training hours × participant count × average rate |
| FDE enablement | FDE hours supporting team | FDE hours × rate |
| Lost productivity | Work not done during training | Estimated sprint capacity reduction |
| Infrastructure | LMS, tools, lab environments | Allocated costs |

#### Value of improved performance:

| Benefit type | Measurement approach |
|--------------|---------------------|
| Time to proficiency | Days from training to effective usage |
| Productivity uplift | Pre and post training productivity comparison |
| Quality improvement | Error reduction after training |
| Reduced support needs | Fewer questions, less FDE time required |
| Knowledge multiplication | Champions trained who then train others |

#### ROLI metrics to track:

| Metric | Definition | Target |
|--------|------------|--------|
| Training effectiveness | percentage achieving proficiency within 4 weeks | more than 80% |
| Knowledge retention | Assessment scores at 30, 60, or 90 days | more than 70% retention |
| Behaviour change | Observable use of trained techniques | Demonstrated in code reviews |
| Time to value | Days from training to measurable productivity gain | less than 14 days |
| Support reduction | FDE or support hours per engineer over time | Decreasing trend |
| Multiplier effect | Engineers enabled by each champion | more than 5 per champion |

#### ROLI calculation example:

```
Training programme: Engineer Foundations (1 day workshop)

INVESTMENT:
- Facilitator cost: £800
- Venue and materials: £200
- Participant time (10 engineers × 8 hours × £50/hour): £4,000
- Lost sprint capacity: £1,000
- Total investment: £6,000

VALUE (measured over 3 months):
- Time savings: 10 engineers × 2 hours/week × 12 weeks × £50/hour = £12,000
- Reduced defect remediation: £1,500
- Reduced support requests: £500
- Total value: £14,000

ROLI = (£14,000 - £6,000) / £6,000 × 100% = 133%
```

#### Comparing training formats by ROLI:

| Format | Typical investment | Typical time to value | Best for |
|--------|-------------------|----------------------|----------|
| Self-paced modules | Low (£50 to £100/person) | 2 to 4 weeks | Established teams, refreshers |
| Guided workshops | Medium (£300 to £500/person) | 1 to 2 weeks | Starting or developing teams |
| Embedded FDE | High (£1,000 to £2,000/person) | less than 1 week | Starting teams, complex environments |
| Champion-led peer training | Very low (£20 to £50/person) | 2 to 3 weeks | Scaling across teams |

#### Optimising ROLI:

| Finding | Action |
|---------|--------|
| Long time to value | Add more hands-on practice, reduce theory |
| Low knowledge retention | Implement spaced reinforcement, quick reference guides |
| High support needs post-training | Identify gaps, enhance training content |
| Champion multiplier low | Better champion enablement, protected time |
| Self-paced completion low | Shorter modules, better engagement design |

#### ROLI reporting template:

```markdown
## ROLI report - [Training programme or period]

### Investment summary
| Component | Cost |
|-----------|------|
| Direct training costs | £X |
| Participant time | £X |
| FDE enablement | £X |
| Infrastructure | £X |
| Total investment | £X |

### Value realised
| Benefit | Value | Measurement method |
|---------|-------|-------------------|
| Productivity gains | £X | Time tracking comparison |
| Quality improvements | £X | Defect reduction |
| Support reduction | £X | FDE hours saved |
| Total value | £X | |

### ROLI calculation
- ROLI: X%
- Payback period: X weeks

### Insights
- [What worked well]
- [What could improve]
- [Recommendations for future investment]
```

---

## Tool-specific measurement

### GitHub Copilot metrics

Available from admin console:

Available metrics include seat activation and usage, suggestions shown versus accepted, languages and file types used, and active users over time.

API access: GitHub Copilot API for programmatic access to usage data.

---

### Claude Code metrics

Available:

Available metrics include session frequency and duration, token usage, and feature usage patterns.

Collection method: The specific collection method depends on the Claude deployment model.

---

### Amazon Q Engineer metrics

Available from AWS console:

Available metrics include active users, suggestions and acceptances, and feature usage (completion, chat, security scans).

Integration: CloudWatch metrics available for dashboards.

---

### Gemini Code Assist metrics

Available from Google Cloud console:

Available metrics include active users, suggestion acceptance, and feature usage.

Integration: Cloud Monitoring for custom dashboards.

---

## When metrics are not available

Not all teams can collect all metrics. This section provides guidance for common constraints.

### Assess your measurement capability

Before starting, identify what you can and cannot collect:

| Question | If no | Impact |
|----------|-------|--------|
| Do you have admin access to AI tool console? | Cannot collect tool-native usage metrics | Use self-reported usage |
| Do you have Git or CI analytics? | Cannot automate delivery metrics | Use manual sampling or proxy metrics |
| Do you have issue tracker access? | Cannot automate quality metrics | Use manual defect tracking |
| Can you run engineer surveys? | Cannot collect satisfaction data | Use informal feedback channels |
| Do you have baseline historical data? | Cannot show before and after comparison | Start baseline now, compare future periods |

### Minimum viable measurement

If resources are constrained, focus on these essential metrics:

| Metric | Why essential | Simplest collection method |
|--------|---------------|---------------------------|
| Licence activation | Confirms tools are accessible | Manual count from admin console |
| Weekly active usage | Confirms tools are being used | Brief weekly team check-in |
| Engineer sentiment | Early warning of issues | Monthly 3-question survey |
| Qualitative feedback | Context for numbers | Retrospective discussions |

#### Three-question minimum survey:

```
1. How often did you use the AI assistant this week?
   Daily, several times, once or twice, not at all

2. How helpful was it? (1 to 10)

3. Any issues or feedback? [Free text]
```

### Alternative approaches by constraint

#### Constraint: no access to AI tool analytics

Problem: cannot see usage data from tool admin console.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Self-reported usage | Weekly survey asking frequency of use |
| Spot checks | Periodic observation during pairing sessions |
| Proxy metrics | IDE extension installed (yes or no), tool visible in screenshots |
| FDE observation | FDE reports on usage during engagement |

Limitations: Self-reported data may be less accurate. Triangulate with multiple sources.

---

#### Constraint: no Git or CI/CD analytics

Problem: Cannot automatically measure commits, cycle time, deployment frequency.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Manual sampling | Review 10 PRs per sprint, record metrics manually |
| Sprint-level tracking | Use velocity from sprint ceremonies |
| Team estimation | Ask team to estimate time spent on tasks |
| Project milestones | Track feature delivery dates |

Simplified delivery tracking template:

```markdown
## Sprint delivery summary - [Sprint X]

Stories completed: [X]
Story points delivered: [X]
Average days per story: [X]
PRs merged: [X]
Deployments: [X]

Notes: [Any context affecting delivery]
```

---

#### Constraint: no code quality tools (SonarQube and similar)

Problem: Cannot automatically measure code quality, coverage, technical debt.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Manual code review scoring | Reviewers rate quality on simple scale |
| Defect tracking | Count bugs found in testing or production |
| Test presence | Count of tests added (not coverage percentage) |
| Rework rate | Track stories reopened after completion |

Simple quality scorecard:

```markdown
## Sprint quality summary - [Sprint X]

PRs reviewed: [X]
PRs requiring significant rework: [X]
Defects found in testing: [X]
Defects found in production: [X]
Stories reopened: [X]

Quality rating (team assessment): [Good, acceptable, or concerning]
```

---

#### Constraint: cannot run formal surveys

Problem: No access to survey tools, or surveys not permitted.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Retrospective feedback | Add AI tools as standing retro topic |
| Informal check-ins | DM asks team members during 1 to 1s |
| Show of hands | Quick poll in team meetings |
| Champion feedback | Champion collects informal feedback |
| FDE observations | FDE reports on team sentiment |

Retrospective prompt:

```
AI Engineering Lab check-in (5 minutes)

- What is working well with AI tools?
- What is frustrating or not working?
- What would help you use them more effectively?
```

---

#### Constraint: no historical baseline data

Problem: Cannot show improvement because there is no "before" measurement.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Start baseline now | Measure first 2 weeks without AI, then enable |
| Comparative baseline | Compare to similar team not yet using AI |
| Delayed baseline | Compare early adoption to later adoption |
| Industry benchmarks | Use published benchmarks as reference |
| Qualitative baseline | Document current pain points, revisit later |

Qualitative baseline template:

```markdown
## Qualitative baseline - [Team name]

Date: [Date]

### Current pain points
1. [Pain point 1 - for example, "Writing tests takes too long"]
2. [Pain point 2]
3. [Pain point 3]

### Time estimates for common tasks
- Writing unit tests for a function: approximately [X] minutes
- Understanding unfamiliar code: approximately [X] minutes
- Writing boilerplate code: approximately [X] minutes

### Team sentiment on AI tools (pre-adoption)
[Summary of expectations, concerns, attitudes]
```

---

#### Constraint: limited time for measurement activities

Problem: Team cannot dedicate time to measurement overhead.

Alternatives:

| Alternative | How to implement |
|-------------|------------------|
| Automate everything possible | Prioritise metrics from automated sources |
| Sample do not census | Measure subset of work, not everything |
| Lightweight rituals | 5-minute metrics check-in, not lengthy analysis |
| Combine with existing | Add to existing retrospectives, not separate meetings |
| Programme-level collection | Central team collects, reducing team burden |

Time budget guide:

| Activity | Maximum time investment |
|----------|------------------------|
| Weekly metrics collection | 15 minutes (ideally automated) |
| Monthly survey completion | 5 minutes per engineer |
| Sprint metrics summary | 10 minutes per sprint |
| Quarterly analysis | 1 hour per quarter |

---

### Metric substitution guide

When primary metrics are not available, use these substitutes:

| Primary metric | Substitute | Trade-off |
|----------------|------------|-----------|
| Daily active users (from tool) | Self-reported usage frequency | Less accurate, potential bias |
| Acceptance rate (from tool) | Engineer perception of usefulness | Subjective, but still valuable |
| Cycle time (from Git) | Sprint velocity trend | Less granular, but directional |
| Code coverage (from tools) | Tests added per story | Less precise, but indicates effort |
| Defect density (from tracker) | Bugs discussed in retro | Incomplete, but captures major issues |
| NPS (from survey) | "Would recommend?" in retro | Less rigorous, but captures sentiment |

### Documenting measurement limitations

Always document what you can and cannot measure:

```markdown
## Measurement capability - [Team name]

### Available metrics
- [Metric]: [Source]
- [Metric]: [Source]

### Unavailable metrics
- [Metric]: [Reason unavailable] → [Alternative approach]
- [Metric]: [Reason unavailable] → [Alternative approach]

### Known limitations
- [Limitation and impact on analysis]

### Improvement plan
- [Action to improve measurement capability]
```

### Escalating measurement blockers

If critical metrics cannot be collected:

| Blocker | Escalate to | Potential resolution |
|---------|-------------|---------------------|
| No admin access to AI tool | Programme team | Request access or central reporting |
| No Git or CI analytics | Technical lead | Implement basic analytics tooling |
| Surveys not permitted | Delivery manager | Seek approval or use alternatives |
| No time for measurement | Programme team | Reduce requirements or provide support |

---

## Common measurement pitfalls

| Pitfall | Problem | Avoidance |
|---------|---------|-----------|
| Measuring too much | Data overload, analysis paralysis | Start with 5 to 7 core metrics |
| Measuring too little | Missing important signals | Cover all four tiers |
| Vanity metrics | High numbers that do not indicate value | Focus on actionable metrics |
| Gaming metrics | Behaviour changes to hit targets, not improve | Use balanced scorecard approach |
| Individual measurement | Creates fear, resistance, gaming | Always measure at team level |
| Ignoring context | Misleading comparisons | Compare teams to own baseline |
| Delayed measurement | Issues discovered too late | Real-time adoption metrics |
| No baseline | Cannot demonstrate improvement | Always baseline first |

---

## Privacy and ethics

### Data handling principles

| Principle | Implementation |
|-----------|----------------|
| Team-level reporting | Never report individual engineer metrics |
| Aggregation | Minimum group size of 5 for reporting |
| Transparency | Tell engineers what is measured and why |
| Consent | Obtain consent for surveys and detailed tracking |
| Purpose limitation | Use data only for adoption improvement |
| Retention | Delete detailed data after analysis |

### What not to measure

Do not measure:

- individual engineer acceptance rates
- individual productivity comparisons
- keystrokes or time spent coding
- prompt content (privacy and security risk)
- personal performance rankings

### Communicating about measurement

Do say:
- "We are measuring adoption to identify where teams need more support"
- "Metrics are at team level to understand patterns"
- "Your survey feedback helps us improve the programme"

Do not say:
- "We are tracking who is using the tools"
- "Top performers will be recognised"
- "Teams will be ranked"

---

## Related documents

- [Quality Strategy](quality-strategy.md) - strategic measurement framework
- [Maturity Assessment Framework](../assessment/maturity-assessment-framework.md) - team assessment metrics
- [FDE Engagement Model](../playbooks/fde-engagement-model.md) - engagement success metrics
- [Compliance Checklist](../governance/compliance-checklist.md) - monitoring requirements

## References

- [DORA Metrics](https://dora.dev/guides/dora-metrics-four-keys/) - software delivery performance
- [GDS Service Manual - Measuring success](https://www.gov.uk/service-manual/measuring-success)
- [Accelerate (Forsgren, Humble, Kim)](https://itrevolution.com/product/accelerate/) - DevOps metrics research