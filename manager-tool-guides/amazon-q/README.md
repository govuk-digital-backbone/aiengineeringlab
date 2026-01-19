> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Amazon Q - Manager Tool Guide

> Central home for Amazon Q best practices content across government departments.

## Audience

Engineering managers, technical leads, and delivery managers responsible for AI Engineering Lab adoption in their teams.

## Purpose

This guide provides engineering managers with practical guidance for implementing Amazon Q within UK government departments. It covers capabilities assessment, security considerations, phased rollout strategies, and success measurement to support informed decision-making and sustainable adoption.

## What's in this guide

This guide is organised into the following sections:

**Understanding Amazon Q**
- [What Amazon Q does](#what-amazon-q-does) - Core capabilities and interaction modes
- [How it compares with other AICAs](#how-it-compares-with-other-aicas) - Feature comparison and when to use different tools
- [Q models and task suitability](#q-models-and-task-suitability) - Choosing the right model for different tasks

**Implementation planning**
- [Government-specific considerations](#government-specific-considerations) - Security classifications, data residency, and procurement
- [Getting started](#getting-started) - Licensing options and installation process
- [Phased rollout approach](#phased-rollout-approach) - Pilot through to full team adoption
- [Training requirements](#training-requirements) - Engineer and manager training programmes

**Managing adoption**
- [Measuring success](#measuring-success) - Metrics, ROI calculation, and feedback collection
- [Common implementation challenges](#common-implementation-challenges) - Addressing resistance and technical issues
- [Integration with development workflow](#integration-with-development-workflow) - Code review, Git workflow, testing, and CI/CD

**Operational guidance**
- [Security best practices](#security-best-practices) - Policy configuration and daily security practices
- [Support and escalation](#support-and-escalation) - Troubleshooting and support pathways
- [Policy configuration reference](#policy-configuration-reference) - Content exclusions and settings

**Additional resources**
- [Related resources](#related-resources) - Links to official documentation, government guidance, and repository materials
- [Contributing](#contributing) - How to improve this guide
- [Support and contact](#support-and-contact) - Getting help

## Prerequisites

Before reading this guide, you should understand:

- Your team's current development workflow and tooling
- Basic software development lifecycle concepts
- Your department's security classification requirements
- The [AI Engineering Lab maturity assessment](../assessment/README.md) framework

## What Amazon Q does

Amazon Q Engineer provides AI-powered code assistance integrated with AWS services and development workflows. It generates code suggestions, explains existing code, and helps with AWS-specific tasks directly in your IDE and command line.

**Primary capabilities:**

- Autocomplete code as engineers type
- Generate implementations from comments or function signatures
- Create and update unit tests
- Explain code and answer technical questions
- Assist with AWS service integration and infrastructure code
- Perform security scans and code reviews
- Support application modernisation and transformation

**Amazon Q interaction modes:**

Amazon Q offers several ways to interact with AI assistance, each suited for different tasks:

| Mode | Description | Best for | Available in |
|------|-------------|----------|--------------|
| **Inline suggestions** | Real-time completions as you type | Quick code completion, boilerplate | All tiers |
| **Q Chat** | Conversational interface in IDE | Explanations, debugging, AWS questions | All tiers |
| **Agent mode** | Autonomous multi-step task execution | Feature implementation, refactoring, testing | Engineer Pro |
| **Command line** | Terminal-based AI assistance | CLI workflows, script generation | All tiers |
| **Code reviews** | Automated security and quality scanning | PR reviews, security analysis | Engineer Pro |
| **Code transformation** | Large-scale code upgrades | Java version upgrades, framework migrations | Engineer Pro |

**When to use each mode:**

- **Inline suggestions**: Daily coding, implementing patterns, writing boilerplate
- **Chat**: Understanding AWS services, debugging, architecture questions
- **Agent mode**: Implementing features from requirements, comprehensive refactoring
- **Command line**: DevOps tasks, AWS CLI operations, script generation
- **Code reviews**: Security scanning, best practice validation
- **Code transformation**: Upgrading Java versions, modernising legacy applications

**Best suited for:**

- Teams working extensively with AWS services
- Projects requiring AWS infrastructure as code
- Java application modernisation initiatives
- Security-conscious development workflows
- Teams needing integrated code scanning

**Not designed for:**

- Non-AWS cloud provider specific tasks
- Complex architectural decisions without human oversight
- Replacing comprehensive security audits
- Fully autonomous production deployments

## How it compares with other AICAs

| Capability | Amazon Q Engineer | GitHub Copilot | Claude Code |
|---|---|---|---|
| Inline completion | Good | Excellent | Not available |
| Chat assistance | Good | Good | Excellent |
| Codebase understanding | Repository-wide | Current file only | Multi-file context |
| Execution capability | Limited | No | No |
| AWS integration | Native | Limited | Via API |
| Security scanning | Built-in | Separate tool | Not available |
| Code transformation | Java upgrades | Not available | Manual |
| Primary use case | AWS workflows | Fast completion | Reasoning tasks |

**When to choose Amazon Q:**

- Your team primarily works with AWS services
- You need integrated security scanning in your workflow
- Java modernisation is a priority
- You want built-in code review capabilities
- Your infrastructure is primarily AWS-based
- You need assistance with AWS CLI and CloudFormation

**When to combine with other tools:**

- Use GitHub Copilot for faster inline completions in non-AWS contexts
- Use Claude Code for complex architectural reasoning
- Use Claude with AWS MCP server for enhanced AWS resource management
- Combine Q's security scanning with manual security reviews

### AWS MCP server for enhanced workflows

The AWS MCP (Model Context Protocol) server enables AI assistants like Claude to interact with AWS resources, providing complementary capabilities to Amazon Q's native AWS integration.

**AWS MCP server capabilities:**

- **Resource management**: Query and manage AWS resources across services
- **Cost analysis**: Review AWS spending and optimisation opportunities
- **Security posture**: Analyse IAM policies and security configurations
- **Infrastructure review**: Examine CloudFormation and Terraform configurations
- **Service recommendations**: Get guidance on AWS service selection

**Example workflow combining Amazon Q and AWS MCP:**

1. Engineer uses Amazon Q inline suggestions for AWS SDK code
2. Engineer uses Q Chat for CloudFormation template generation
3. Engineering manager uses Claude with AWS MCP server to review infrastructure security
4. Claude analyses IAM policies and suggests least-privilege improvements
5. Manager reviews AI analysis and implements approved changes

**Setting up AWS MCP server:**

The AWS MCP server is available for use with Claude and other MCP-compatible AI assistants. For configuration details, see:
- [AWS MCP server documentation](https://github.com/modelcontextprotocol/servers/tree/main/src/aws)
- [MCP integration guide](../mcp-servers/aws-integration.md)

**Government considerations:**

- AWS MCP server requires IAM credentials with appropriate permissions
- Use IAM roles with least-privilege access
- Configure resource-level permissions to limit scope
- Review data handling policies with your security team
- Ensure compliance with your department's AWS usage policies
- Consider using read-only permissions for analysis tasks

## Q models and task suitability

Amazon Q Engineer uses different models optimised for various development tasks. Understanding model capabilities helps set appropriate expectations and choose the right approach.

### Model comparison

| Model | Best for | Response time | Context window | Cost tier |
|---|---|---|---|---|
| Amazon Q Engineer | Code generation, AWS integration, general development | Fast (1-2s) | Large (100K+ tokens) | Standard |
| Amazon Q Engineer Pro | Advanced features, security scanning, transformations | Fast (1-2s) | Large (100K+ tokens) | Premium |

**Note**: Amazon Q uses AWS's proprietary models optimised for code generation and AWS service integration. Unlike some competitors, Q doesn't expose multiple model options to users - the appropriate model is selected automatically based on the task.

### Recommended features by task

| Task | Recommended approach | Why |
|---|---|---|
| Autocomplete as you type | Inline suggestions | Optimised for fast, context-aware completions |
| Generate unit tests | Agent mode (Pro) | Can create comprehensive test suites |
| Debug AWS integration issues | Q Chat | Direct access to AWS documentation and patterns |
| Write CloudFormation templates | Q Chat | Trained on AWS infrastructure patterns |
| Refactor legacy code | Agent mode (Pro) | Multi-file understanding and modification |
| Security code review | Code review feature (Pro) | Built-in security scanning |
| Upgrade Java applications | Code transformation (Pro) | Specialised for Java version migrations |
| Generate documentation | Q Chat | Good natural language generation |
| Implement AWS SDK calls | Inline suggestions | Trained on AWS SDK patterns |
| Optimise AWS costs | Q Chat | Can suggest cost-effective alternatives |

### Controlling feature usage

In Amazon Q, you interact with different capabilities through:

**IDE commands:**
- `/dev` - Agent mode for feature implementation
- `/test` - Generate unit tests
- `/doc` - Generate documentation
- `/review` - Security and code quality review
- `/transform` - Code transformation (Java upgrades)

**Chat commands:**
- Ask questions directly in Q Chat
- Reference workspace with `@workspace`
- Get AWS-specific help with service names

**Example usage:**

## Government-specific considerations

### Security classification

Amazon Q Engineer processes code snippets through AWS services. This means:

- **OFFICIAL**: Generally acceptable with appropriate content exclusions configured
- **OFFICIAL-SENSITIVE**: Requires risk assessment and strict content exclusions
- **SECRET and above**: Not appropriate for these classifications

Consult your departmental security team before deployment. Reference [NCSC guidance on cloud services](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) for risk assessment.

### Content exclusions

You must configure Amazon Q to exclude sensitive files and patterns. Recommended exclusions for government projects:

```yaml
# Environment and configuration files
**/.env
**/.env.*
**/secrets/**
**/config/production.yml
**/config/production/**

# AWS credentials and configuration
**/credentials
**/.aws/credentials
**/.aws/config
**/aws-exports.js

# API keys and tokens
**/api-keys/**
**/*-key.json
**/*-credentials.json

# Department-specific patterns
**/citizen-data/**
**/personal-identifiable-information/**
**/security-configurations/**
**/terraform/production/**
```

### Data residency

Amazon Q Engineer processes requests through AWS services in AWS regions. As of January 2025:

- Code suggestions are processed in AWS US regions
- No customer code is stored or used for model training
- Telemetry data follows AWS data residency policies

Check your department's data residency requirements before deployment. For UK government, verify compliance with data sovereignty requirements.

### Intellectual property

Amazon Q Engineer Pro includes IP indemnity, meaning AWS provides legal protection if generated code infringes copyright. Free tier does not include this protection.

For government projects, use Amazon Q Engineer Pro only.

## Getting started

### Licensing options

**Amazon Q Engineer (Free)**:
- Free for individual engineers
- Not recommended for government projects
- No IP indemnity or enterprise controls
- Limited features (no agent mode, transformations, or security scans)

**Amazon Q Engineer Pro**: $19/month per user
- Recommended for government teams
- IP indemnity included
- Full feature access including agent mode
- Security scanning and code reviews
- Code transformation capabilities
- Administrative controls via IAM Identity Center
- Usage analytics and reporting
- No training on your code

### Procurement routes

Amazon Q Engineer is available through:

1. **Crown Commercial Service G-Cloud 14**: Search for AWS offerings including Amazon Q
2. **AWS Enterprise Agreement**: For departments with existing AWS Enterprise Support
3. **AWS Marketplace**: Direct subscription with consolidated billing
4. **TechUK Framework**: Through authorised AWS resellers

Consult the procurement guidance documentation for detailed pathways.

### Installation process

**Step 1: AWS account setup**

1. Set up IAM Identity Center (if not already configured)
2. Create user groups for Amazon Q access
3. Assign Amazon Q Engineer Pro licenses
4. Configure content exclusion policies (via AWS console)

**Step 2: Engineer installation**

For VS Code:
```bash
# Install AWS Toolkit extension (includes Amazon Q)
code --install-extension amazonwebservices.aws-toolkit-vscode
```

For JetBrains IDEs:
- Settings → Plugins → Search "AWS Toolkit" → Install

For Visual Studio:
- Extensions → Manage Extensions → Search "AWS Toolkit" → Install

**Step 3: Authentication**

Engineers authenticate using IAM Identity Center:

1. Open AWS Toolkit in IDE
2. Click "Connect to AWS"
3. Select "Use IAM Identity Center"
4. Enter your organisation's start URL
5. Complete browser-based authentication
6. Select AWS Builder ID or IAM Identity Center profile

**Step 4: Verification**

Test installation by:
1. Opening a code file (Python, Java, JavaScript, etc.)
2. Start typing - inline suggestions should appear
3. Open Q Chat panel and ask a question
4. Verify authentication status shows "Connected"

## Phased rollout approach

### Phase 1: Pilot (weeks 1-4)

**Objective**: Validate effectiveness and identify issues

**Activities:**
- Select 5-10 engineers across different experience levels
- Focus on AWS-related projects or infrastructure work
- Schedule weekly feedback sessions
- Document effective usage patterns, especially for AWS tasks
- Test security scanning features on real code

**Success criteria:**
- 70%+ of pilot users actively using Amazon Q
- No security incidents
- Documented productivity benefits for AWS tasks
- Clear implementation guidance for wider rollout
- Positive feedback on security scanning features

### Phase 2: Team expansion (weeks 5-12)

**Objective**: Scale to full engineering team

**Activities:**
- Roll out to entire team in groups of 10-15
- Deliver 45-minute training sessions per group
- Share pilot user success stories, especially AWS use cases
- Establish support channels (Slack, Teams, or email)
- Create internal knowledge base of effective prompts

**Success criteria:**
- 80%+ license activation rate
- Acceptance rate above 20%
- Engineers report time savings on AWS tasks
- No increase in security vulnerabilities
- Active use of security scanning features

### Phase 3: Optimisation (ongoing)

**Objective**: Maximise value and address friction

**Activities:**
- Review monthly usage analytics via AWS console
- Refine content exclusion policies based on incidents
- Update training materials based on common questions
- Share wins across department
- Explore advanced features (agent mode, transformations)

**Success criteria:**
- Consistent month-on-month usage
- Declining support tickets
- Measurable productivity improvements
- Positive engineer satisfaction scores
- Successful use of advanced features

## Training requirements

### Engineer training (60 minutes)

**Module 1: Basic usage** (20 minutes)
- Accepting and rejecting inline suggestions
- Using Q Chat for questions and explanations
- Keyboard shortcuts and IDE integration
- When to use Q vs manual coding
- Understanding suggestion confidence levels

**Module 2: AWS-specific features** (20 minutes)
- Getting help with AWS services
- Generating CloudFormation and CDK code
- Using Q for AWS CLI commands
- Troubleshooting AWS SDK integration
- Best practices for infrastructure as code

**Module 3: Advanced features and security** (20 minutes)
- Using agent mode for feature implementation (`/dev`)
- Running security scans (`/review`)
- Generating comprehensive tests (`/test`)
- Reviewing generated code critically
- Content exclusions and when they apply
- Integration with code review process

**Format**: Live demonstration with hands-on practice using real AWS projects.

### Manager briefing (30 minutes)

**Topics:**
- Capability overview and realistic expectations
- AWS-specific advantages and use cases
- Usage metrics and how to interpret them (via AWS console)
- Policy configuration and content exclusions
- Addressing team concerns about AI tools
- Return on investment calculation
- Security scanning and compliance features

**Format**: Presentation with Q&A session.

## Measuring success

### Quantitative metrics

**Adoption metrics:**
- License activation rate (target: 90%+)
- Daily active users (target: 80%+ of activated licenses)
- Suggestion acceptance rate (target: 20-30%)
- Security scan usage (target: weekly per engineer)

**Productivity metrics:**
- Lines of code accepted per engineer per day
- Time spent on AWS integration tasks (via engineer survey)
- CloudFormation/CDK template generation time
- Pull request cycle time
- Test coverage increase rate

**Quality metrics:**
- Security vulnerabilities detected by Q reviews
- Code review comments per PR (should remain stable)
- Bug escape rate (should not increase)
- AWS best practice compliance

### Qualitative feedback

Conduct monthly engineer surveys asking:

1. How often do you use Amazon Q? (Daily / Weekly / Rarely / Never)
2. For which tasks is Amazon Q most helpful?
3. How helpful are the AWS-specific features?
4. Has Amazon Q affected your productivity? (Much faster / Somewhat faster / No change / Slower)
5. Do you feel confident reviewing Q-generated code?
6. How useful is the security scanning feature?

### Return on investment calculation

```
Monthly cost = $19 per engineer × number of licenses
Monthly time saved = hours saved per engineer × number of active users
Hourly rate = annual salary ÷ 1,800 (approximate working hours)

ROI = (time saved × hourly rate - monthly cost) ÷ monthly cost × 100
```

**Example for a team of 20 engineers:**
- Monthly cost: $380 (£300 approx)
- Time saved per engineer: 6 hours/month (conservative estimate)
- Average hourly rate: £45
- Monthly value: 20 × 6 × £45 = £5,400
- ROI: ((£5,400 - £300) ÷ £300) × 100 = 1,600%

Typical payback period: 1-2 months based on AWS customer case studies showing 10-20% productivity improvements.

**Additional value from security scanning:**
- Reduced security vulnerabilities in production
- Faster security review cycles
- Earlier detection of issues (shift-left)

## Common implementation challenges

### Challenge: Engineers not using the tool

**Symptoms:**
- Low activation rates after 2 weeks
- Acceptance rates below 15%
- Feedback indicates suggestions are "not helpful"

**Interventions:**
1. Check content exclusions aren't too restrictive
2. Verify engineers understand keyboard shortcuts
3. Provide pairing sessions with effective users
4. Share specific AWS use case examples
5. Demonstrate agent mode for complex tasks
6. Show security scanning benefits

### Challenge: Security concerns from team

**Symptoms:**
- Engineers questioning code suggestions
- Reluctance to accept any generated code
- Requests to disable tool

**Interventions:**
1. Clarify that code review process remains unchanged
2. Demonstrate content exclusion configuration
3. Show built-in security scanning features
4. Reference IP indemnity coverage
5. Share NCSC guidance compliance
6. Demonstrate that Q helps identify security issues

### Challenge: Over-reliance on suggestions

**Symptoms:**
- Decreased code review thoroughness
- Accepting suggestions without understanding them
- Reduced manual problem-solving attempts

**Interventions:**
1. Reinforce code review standards
2. Include "understanding of implementation" in review checklist
3. Encourage treating suggestions as first drafts
4. Pair junior engineers with seniors during adoption
5. Emphasise security scanning as complement, not replacement

### Challenge: AWS-specific confusion

**Symptoms:**
- Suggestions don't match team's AWS patterns
- Generated CloudFormation templates need significant modification
- Confusion about AWS service recommendations

**Interventions:**
1. Provide AWS-specific training on Q usage
2. Create internal library of effective AWS prompts
3. Document team's AWS architecture patterns
4. Use Q Chat to ask clarifying questions about AWS services
5. Leverage agent mode for complex AWS integrations

### Challenge: Variable suggestion quality

**Symptoms:**
- Inconsistent helpfulness across different codebases
- Better suggestions in some languages than others
- Suggestions don't match project patterns

**Interventions:**
1. Improve context through better comments and function signatures
2. Ensure relevant code is visible in workspace
3. Use Q Chat for complex scenarios instead of inline
4. Check if content exclusions are blocking helpful context
5. Use agent mode for multi-file context understanding

## Integration with development workflow

### Code review process

Amazon Q-generated code should pass through the same review process as human-written code. Recommended review checklist:

- [ ] Logic correctness and edge case handling
- [ ] No hardcoded secrets or sensitive data
- [ ] Compliance with team coding standards
- [ ] Appropriate error handling
- [ ] Security implications considered (use `/review` command)
- [ ] AWS best practices followed
- [ ] Test coverage adequate
- [ ] Performance and cost characteristics acceptable
- [ ] IAM permissions follow least-privilege principle

**Using Q's built-in code review:**

Before submitting PRs, engineers should run:
```
/review
```

This triggers Amazon Q's security and code quality scan, which checks for:
- Security vulnerabilities
- Code quality issues
- AWS best practice violations
- Potential bugs

**Responsible use guidance:**

- Review all AI-generated code with the same rigour as human-written code
- Understand the code before accepting it into your codebase
- Test thoroughly, especially AWS integrations and error conditions
- Be aware of potential security vulnerabilities in suggestions
- Maintain accountability - the engineer approving the code is responsible for it
- Use `/review` command but don't rely on it exclusively

### Git workflow

No changes needed to your existing Git workflow. Amazon Q operates at the IDE level and doesn't affect commits, branches, or merges.

Some teams choose to document AI usage in commit messages:

```
feat: Add S3 bucket lifecycle policy

Implemented lifecycle rules using Amazon Q assistance for
AWS SDK integration. Security scan passed. IAM permissions reviewed.
```

This is optional and should align with your team's commit message conventions.

### Testing strategy

Treat Amazon Q-generated code as untested until proven otherwise:

1. **Unit tests**: Use `/test` command to generate test scaffolding, then review and enhance
2. **Integration tests**: Manually verify AWS service interactions
3. **Security tests**: Run `/review` and SAST tools on all code
4. **AWS-specific tests**: Test IAM permissions, resource limits, error handling
5. **Manual review**: Code review remains mandatory

### CI/CD pipeline

Amazon Q doesn't require changes to your pipeline. Ensure existing quality gates remain in place:

- Linting and formatting checks
- Unit test execution and coverage thresholds
- Static analysis and security scanning
- Integration and end-to-end test suites
- AWS resource validation (CloudFormation linting, etc.)

Generated code must pass all gates before merging.

**Optional enhancement**: Consider integrating Amazon Q security scanning into CI/CD for automated security checks.

## Security best practices

### For managers

**Policy configuration:**

1. Configure content exclusions before any engineer access
2. Review exclusion patterns quarterly or after incidents
3. Enable usage analytics via AWS console
4. Establish clear escalation path for security concerns
5. Configure IAM policies with least-privilege access

**Monitoring:**

- Review usage patterns in AWS CloudWatch
- Check for unusual acceptance rates (very high or very low)
- Monitor security scan results across team
- Conduct periodic audits of generated code in production
- Review IAM permissions granted to engineers

**Communication:**

- Share security expectations clearly during training
- Reinforce that all code requires review regardless of source
- Document and share security incidents as learning opportunities
- Encourage reporting of concerning suggestions without blame
- Promote use of `/review` command before PRs

### For engineers

**Daily practices:**

- Never accept suggestions containing API keys, passwords, or tokens
- Review all security-critical code (authentication, encryption, input validation) with extra scrutiny
- Verify generated SQL queries for injection vulnerabilities
- Check generated AWS SDK calls for proper error handling
- Ensure IAM policies follow least-privilege principle
- Run `/review` command before submitting PRs
- Validate CloudFormation templates for security misconfigurations

**When to avoid Amazon Q:**

- Implementing cryptographic algorithms
- Writing security controls (authentication, authorisation)
- Processing citizen data or personal information
- Making critical infrastructure decisions without review
- Configuring production IAM policies without validation

**AWS-specific security considerations:**

- Verify S3 bucket policies don't allow public access
- Check IAM roles have appropriate trust relationships
- Ensure security groups follow least-privilege network access
- Validate KMS key policies and encryption settings
- Review CloudWatch logging and monitoring configurations

## Support and escalation

### Engineer support

**Tier 1: Self-service**
- [Amazon Q Engineer documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/)
- [Getting started guide](https://aws.amazon.com/q/developer/getting-started/)
- [AWS re:Post for Amazon Q](https://repost.aws/tags/TA4ckYf2i3Rh-L8LJ8eKPxqg/amazon-q)
- Internal knowledge base (if established)

**Tier 2: Team support**
- Internal Slack/Teams channel
- Champion network (see [champion-programme.md](../community/champion-programme.md))
- Weekly office hours

**Tier 3: AWS support**
- AWS Support Center (requires AWS Support plan)
- Response time depends on support tier (Engineer/Business/Enterprise)
- Amazon Q Engineer Pro includes enhanced support

### Common troubleshooting scenarios

#### Inline suggestions not appearing

**Symptoms:**
- No autocomplete suggestions while typing
- Extension appears inactive

**Solutions:**
1. Verify AWS Toolkit extension is installed and enabled
2. Check authentication status - ensure connected to IAM Identity Center
3. Verify Amazon Q Engineer Pro license is assigned
4. Check that file type is supported (Python, Java, JavaScript, TypeScript, etc.)
5. Restart IDE and check network connectivity
6. Review IAM permissions for Amazon Q access

#### Q Chat not responding

**Symptoms:**
- Chat window opens but no responses
- Error messages in chat interface

**Solutions:**
1. Check AWS service health at [AWS Health Dashboard](https://health.aws.amazon.com/)
2. Verify license is active in IAM Identity Center
3. Clear chat history and restart conversation
4. Check corporate proxy/firewall allows AWS endpoints
5. Update to latest AWS Toolkit version
6. Verify IAM permissions include `codewhisperer:GenerateRecommendations`

#### Agent mode failures

**Symptoms:**
- `/dev` commands fail to complete
- Timeout errors or incomplete work
- Agent gets stuck in loops

**Solutions:**
1. Break down complex tasks into smaller, more specific requests
2. Ensure workspace has clear structure and dependencies
3. Check repository size (very large repos may struggle)
4. Provide more specific requirements in the prompt
5. Review agent progress and provide clarifications when requested
6. Verify sufficient context is available (not excluded by content filters)

#### Security scan issues

**Symptoms:**
- `/review` command fails or returns no results
- Scan takes very long time
- False positives in scan results

**Solutions:**
1. Ensure file is in supported language
2. Check file size (very large files may timeout)
3. Review scan results carefully - some findings may be intentional
4. Configure scan sensitivity if available
5. Report false positives to AWS support for model improvement

#### Authentication problems

**Symptoms:**
- Cannot connect to IAM Identity Center
- "Unauthorized" errors
- License not recognized

**Solutions:**
1. Verify IAM Identity Center start URL is correct
2. Check user is assigned to correct group with Q access
3. Ensure Amazon Q Engineer Pro license is assigned to user
4. Try signing out and back in
5. Clear cached credentials and re-authenticate
6. Verify IAM policies allow Amazon Q access
7. Contact AWS administrator to verify license assignment

#### Poor suggestion quality

**Symptoms:**
- Suggestions don't match project patterns
- Irrelevant or incorrect code generated
- AWS SDK calls use outdated patterns

**Solutions:**
1. Provide more context via descriptive comments and function signatures
2. Ensure relevant imports and dependencies are visible
3. Use more specific variable and function names
4. Check if content exclusions are blocking helpful context
5. Try using Q Chat for complex scenarios instead of inline
6. For AWS tasks, be explicit about service versions and SDKs

**Examples of effective prompting:**

**Example 1: Generating AWS Lambda function**

**Poor prompt:**
```python
# lambda function
def handler(event, context):
```

**Good prompt:**
```python
# AWS Lambda function to process S3 event notifications. Extract object key,
# validate file type (only .json and .csv), read content from S3, transform
# data, and write to DynamoDB table 'ProcessedData'. Include error handling
# for missing objects and DynamoDB throttling. Use boto3 SDK.
def process_s3_event(event, context):
```

**Why it's better:** Specifies AWS services, data flow, validation rules, error conditions, and SDK preference.

**Example 2: Creating CloudFormation template**

**Poor prompt:**
```yaml
# cloudformation template
Resources:
```

**Good prompt:**
```yaml
# CloudFormation template for serverless API: API Gateway REST API with
# Lambda integration, DynamoDB table with on-demand billing, CloudWatch
# Logs with 7-day retention, IAM roles with least-privilege permissions.
# Include outputs for API endpoint and table name. Use AWS::Serverless
# transform for simplified syntax.
AWSTemplateFormatVersion: '2010-09-09'
Transform: AWS::Serverless-2016-10-31
Resources:
```

**Why it's better:** Describes complete architecture, specifies AWS services, includes operational requirements (logging, IAM), and mentions desired CloudFormation features.

**Example 3: Implementing IAM policy**

**Poor prompt:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
```

**Good prompt:**
```json
# IAM policy for Lambda function to: read from S3 bucket 'data-input-bucket'
# with prefix 'incoming/', write to DynamoDB table 'ProcessedRecords',
# write logs to CloudWatch Logs group '/aws/lambda/data-processor'.
# Follow least-privilege principle with resource-level permissions.
{
  "Version": "2012-10-17",
  "Statement": [
```

**Why it's better:** Specifies exact resources, actions needed, and security principle to follow.

**General tips for better prompts with Amazon Q:**
- Be specific about AWS services and versions
- Include resource names and ARNs when known
- Mention error handling and edge cases
- Specify IAM permission requirements
- Reference AWS best practices explicitly
- Include operational requirements (logging, monitoring)

#### Performance issues

**Symptoms:**
- Slow suggestion generation
- IDE lagging when Amazon Q active

**Solutions:**
1. Reduce number of active IDE extensions
2. Check network connectivity and latency to AWS
3. Clear extension cache and reload IDE
4. Update to latest AWS Toolkit version
5. Check system resources (CPU, memory)
6. Verify no proxy issues affecting AWS connectivity

#### Enterprise-specific issues

**Symptoms:**
- License assignment not working
- Policy changes not taking effect
- Usage metrics not appearing

**Solutions:**
1. Verify user is in correct IAM Identity Center group
2. Check license assignment in AWS console
3. Allow 15-30 minutes for policy changes to propagate
4. Ensure user has signed out and back in after policy updates
5. Contact AWS support for billing or access issues
6. Review CloudTrail logs for permission errors

### Security incidents

If a engineer discovers or accepts code containing:
- Hardcoded secrets or credentials
- Known security vulnerabilities
- Data protection violations
- Insecure AWS configurations

**Immediate actions:**
1. Do not commit the code
2. Report to your security team using standard incident process
3. Document the suggestion for analysis
4. Update content exclusions if pattern-based
5. Run `/review` command to check for similar issues

**Follow-up:**
- Review similar code in recent commits
- Update team training materials
- Share learning without blame
- Report issue to AWS if appropriate

## Policy configuration reference

### Recommended content exclusions

Configure in AWS console under Amazon Q Engineer settings:

```yaml
# Secrets and credentials
**/.env
**/.env.*
**/secrets/**
**/*.key
**/*.pem
**/credentials
**/.aws/**

# AWS-specific sensitive files
**/aws-exports.js
**/amplify-config.json
**/terraform.tfstate
**/terraform.tfstate.backup

# Configuration files
**/config/production.yml
**/config/production/**
**/terraform/production/**
**/cloudformation/production/**

# Citizen data
**/citizen-data/**
**/personal-identifiable-information/**
**/user-data/**

# Security configurations
**/security-configurations/**
**/iam-policies/production/**
**/security-groups/production/**
```

### IDE-level settings

Example VS Code configuration:

```json
{
  "aws.codeWhisperer.includeSuggestionsWithCodeReferences": false,
  "aws.codeWhisperer.shareCodeWhispererContentWithAWS": false,
  "aws.suppressPrompts": {
    "codeWhispererNewWelcomeMessage": true
  },
  "editor.inlineSuggest.enabled": true
}
```

Disable Amazon Q for specific file types where suggestions aren't helpful:

```json
{
  "aws.codeWhisperer.enabledLanguages": {
    "python": true,
    "javascript": true,
    "typescript": true,
    "java": true,
    "yaml": false,
    "plaintext": false
  }
}
```

### Organisation-level settings

Configure in AWS console:

1. Navigate to IAM Identity Center → Applications → Amazon Q Engineer
2. Assign users and groups
3. Configure content exclusions (Settings → Content Exclusions)
4. Set up usage analytics (CloudWatch integration)
5. Configure sharing preferences (opt-out of telemetry if required)

**IAM policy example for Amazon Q access:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "codewhisperer:GenerateRecommendations",
        "codewhisperer:GetCodeAnalysis"
      ],
      "Resource": "*"
    }
  ]
}
```

## Next steps

1. **Assess readiness**: Complete the [maturity assessment](../assessment/README.md) to determine if your team is ready for Amazon Q
2. **Review security**: Consult your security team about content exclusions for your specific projects
3. **Verify AWS access**: Ensure IAM Identity Center is configured and users can be assigned
4. **Start procurement**: Follow [procurement guidance](./procurement-guidance.md) to acquire licenses
5. **Plan pilot**: Identify 5-10 pilot users, prioritising those working with AWS
6. **Measure impact**: Set baseline metrics before deployment

## Related resources

### Official AWS resources

- [Amazon Q Engineer documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/) - Complete official documentation
- [Amazon Q Engineer features](https://aws.amazon.com/q/developer/) - Feature overview and capabilities
- [Getting started with Amazon Q](https://aws.amazon.com/q/developer/getting-started/) - Initial setup guides
- [Amazon Q Engineer pricing](https://aws.amazon.com/q/developer/pricing/) - Licensing and cost information
- [AWS re:Post for Amazon Q](https://repost.aws/tags/TA4ckYf2i3Rh-L8LJ8eKPxqg/amazon-q) - Community questions and answers

### Enterprise and security

- [Managing Amazon Q in your organisation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-iam.html) - IAM and access control
- [Amazon Q security](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security.html) - Security features and best practices
- [Content exclusions](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-data-protection.html) - Configuring what Amazon Q can access
- [AWS Artifact](https://aws.amazon.com/artifact/) - Compliance reports and certifications

### Government procurement

- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [AWS on G-Cloud](https://www.digitalmarketplace.service.gov.uk/) - Search for AWS services including Amazon Q
- [TechUK Framework](https://www.techuk.org/) - Alternative procurement route

### NCSC guidance

- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - Assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - Security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - Handling security issues

### Repository resources

- [AI SDLC Playbook](../playbooks/ai-sdlc-playbook.md) - Integrating AICAs across development lifecycle
- [Model Selection Playbook](../playbooks/model-selection.md) - Choosing appropriate tools for tasks
- [GitHub Copilot Manager Guide](../copilot/README.md) - Complementary tool for inline completions

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines. 

We encourage contributions from across government to keep this repository current and comprehensive. Share your team's experience, lessons learned, and effective practices to help other government departments.

Before contributing, please read [CONTRIBUTING.md](../../CONTRIBUTING.md) which covers:

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