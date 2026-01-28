> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Amazon Q - security and support guidance

> Central home for Amazon Q security best practices and support content across government departments.

## Audience

Engineering managers, technical leads, and delivery managers responsible for AI Engineering Lab adoption in their teams.

## Purpose

This guide provides engineering managers with practical guidance for implementing Amazon Q within UK government departments. It covers security considerations, troubleshooting issues and incident reporting.

## What's in this guide

This guide is organised into the following sections.

**Operational guidance**
- [Security best practices](#security-best-practices) - policy configuration and daily security practices
- [Support and escalation](#support-and-escalation) - troubleshooting and support pathways

**Additional resources**
- [Related resources](#related-resources) - links to official documentation, government guidance, and repository materials
- [Contributing](#contributing) - how to improve this guide
- [Support and contact](#support-and-contact) - getting help

## Prerequisites

Before reading this guide, you should understand:
- your team's current development workflow and tooling
- basic software development lifecycle concepts
- your department's security classification requirements
- the AI Engineering Lab maturity assessment framework (see [maturity assessment framework](../../assessment/maturity-assessment-framework.md) and [team classification guide](../../assessment/team-classification-guide.md))
- reviewed manager-tool-guides for [Amazon Q](./README.md)

## Security best practices

### For managers

The policy configuration steps are as follows:

1. Configure content exclusions before any engineer access.
2. Review exclusion patterns quarterly or after incidents.
3. Enable usage analytics via AWS console.
4. Establish clear escalation path for security concerns.
5. Configure IAM policies with least-privilege access.

Monitoring activities include:
- review usage patterns in AWS CloudWatch
- check for unusual acceptance rates (very high or very low)
- monitor security scan results across team
- conduct periodic audits of generated code in production
- review IAM permissions granted to engineers

Communication activities include:
- share security expectations clearly during training
- reinforce that all code requires review regardless of source
- document and share security incidents as learning opportunities
- encourage reporting of concerning suggestions without blame
- promote use of '/review' command before PRs

### For engineers

Daily practices include:
- never accept suggestions containing API keys, passwords, or tokens
- review all security-critical code (authentication, encryption, input validation) with extra scrutiny
- verify generated SQL queries for injection vulnerabilities
- check generated AWS SDK calls for proper error handling
- ensure IAM policies follow least-privilege principle
- run '/review' command before submitting PRs
- validate CloudFormation templates for security misconfigurations

When to avoid Amazon Q:
- implementing cryptographic algorithms
- writing security controls (authentication, authorisation)
- processing citizen data or personal information
- making critical infrastructure decisions without review
- configuring production IAM policies without validation

AWS-specific security considerations include:
- verify S3 bucket policies do not allow public access
- check IAM roles have appropriate trust relationships
- ensure security groups follow least-privilege network access
- validate KMS key policies and encryption settings
- review CloudWatch logging and monitoring configurations

## Support and escalation

### Engineer support

The tier 1 self-service resources are:
- [Amazon Q Engineer documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/)
- [Getting started guide](https://aws.amazon.com/q/developer/getting-started/)
- [AWS re:Post for Amazon Q](https://repost.aws/tags/TA4ckYf2i3Rh-L8LJ8eKPxqg/amazon-q)
- internal knowledge base (if established)

The tier 2 team support options are:
- internal Slack or Teams channel
- champion network
- weekly office hours

The tier 3 AWS support options are:
- AWS Support Center (requires AWS Support plan)
- response time depends on support tier (Engineer, Business, Enterprise)
- Amazon Q engineer Pro includes enhanced support

### Common troubleshooting scenarios

#### Inline suggestions not appearing

Symptoms include:
- no autocomplete suggestions while typing
- extension appears inactive

The solutions are as follows:

1. Verify AWS Toolkit extension is installed and enabled.
2. Check authentication status - ensure connected to IAM Identity Center.
3. Verify Amazon Q engineer Pro license is assigned.
4. Check that file type is supported (Python, Java, JavaScript, TypeScript, and similar).
5. Restart IDE and check network connectivity.
6. Review IAM permissions for Amazon Q access.

#### Q Chat not responding

Symptoms include:
- chat window opens but no responses
- error messages in chat interface

The solutions are as follows:

1. Check AWS service health at [AWS Health Dashboard](https://health.aws.amazon.com/).
2. Verify license is active in IAM Identity Center.
3. Clear chat history and restart conversation.
4. Check corporate proxy or firewall allows AWS endpoints.
5. Update to latest AWS Toolkit version.
6. Verify IAM permissions include 'codewhisperer:GenerateRecommendations'.

#### Agent mode failures

Symptoms include:
- '/dev' commands fail to complete
- timeout errors or incomplete work
- agent gets stuck in loops

The solutions are as follows:

1. Break down complex tasks into smaller, more specific requests.
2. Ensure workspace has clear structure and dependencies.
3. Check repository size (very large repos may struggle).
4. Provide more specific requirements in the prompt.
5. Review agent progress and provide clarifications when requested.
6. Verify sufficient context is available (not excluded by content filters).

#### Security scan issues

Symptoms include:
- '/review' command fails or returns no results
- scan takes very long time
- false positives in scan results

The solutions are as follows:

1. Ensure file is in supported language.
2. Check file size (very large files may timeout).
3. Review scan results carefully - some findings may be intentional.
4. Configure scan sensitivity if available.
5. Report false positives to AWS support for model improvement.

#### Authentication problems

Symptoms include:
- cannot connect to IAM Identity Center
- 'Unauthorised' errors
- license not recognised

The solutions are as follows:

1. Verify IAM Identity Center start URL is correct.
2. Check user is assigned to correct group with Q access.
3. Ensure Amazon Q engineer Pro license is assigned to user.
4. Try signing out and back in.
5. Clear cached credentials and re-authenticate.
6. Verify IAM policies allow Amazon Q access.
7. Contact AWS administrator to verify license assignment.

#### Poor suggestion quality

Symptoms include:
- suggestions do not match project patterns
- irrelevant or incorrect code generated
- AWS SDK calls use outdated patterns

The solutions are as follows:

1. Provide more context via descriptive comments and function signatures.
2. Ensure relevant imports and dependencies are visible.
3. Use more specific variable and function names.
4. Check if content exclusions are blocking helpful context.
5. Try using Q Chat for complex scenarios instead of inline.
6. For AWS tasks, be explicit about service versions and SDKs.

**Examples of effective prompting:**

**Example 1: generating AWS Lambda function**

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

**Why it's better:** specifies AWS services, data flow, validation rules, error conditions, and SDK preference.

**Example 2: creating CloudFormation template**

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

**Why it's better:** describes complete architecture, specifies AWS services, includes operational requirements (logging, IAM), and mentions desired CloudFormation features.

**Example 3: implementing IAM policy**

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

**Why it's better:** specifies exact resources, actions needed, and security principle to follow.

General tips for better prompts with Amazon Q include:
- be specific about AWS services and versions
- include resource names and ARNs when known
- mention error handling and edge cases
- specify IAM permission requirements
- reference AWS best practices explicitly
- include operational requirements (logging, monitoring)

#### Performance issues

Symptoms include:
- slow suggestion generation
- IDE lagging when Amazon Q active

The solutions are as follows:

1. Reduce number of active IDE extensions.
2. Check network connectivity and latency to AWS.
3. Clear extension cache and reload IDE.
4. Update to latest AWS Toolkit version.
5. Check system resources (CPU, memory).
6. Verify no proxy issues affecting AWS connectivity.

#### Enterprise-specific issues

Symptoms include:
- license assignment not working
- policy changes not taking effect
- usage metrics not appearing

The solutions are as follows:

1. Verify user is in correct IAM Identity Center group.
2. Check license assignment in AWS console.
3. Allow 15 to 30 minutes for policy changes to propagate.
4. Ensure user has signed out and back in after policy updates.
5. Contact AWS support for billing or access issues.
6. Review CloudTrail logs for permission errors.

### Security incidents

If an engineer discovers or accepts code containing:
- hardcoded secrets or credentials
- known security vulnerabilities
- data protection violations
- insecure AWS configurations

The immediate actions are as follows:

1. Do not commit the code.
2. Report to your security team using standard incident process.
3. Document the suggestion for analysis.
4. Update content exclusions if pattern-based.
5. Run '/review' command to check for similar issues.

Follow-up activities include:
- review similar code in recent commits
- update team training materials
- share learning without blame
- report issue to AWS if appropriate

## Related resources

### Official AWS resources

- [Amazon Q Engineer documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/) - complete official documentation
- [Amazon Q Engineer features](https://aws.amazon.com/q/developer/) - feature overview and capabilities
- [Getting started with Amazon Q](https://aws.amazon.com/q/developer/getting-started/) - initial setup guides
- [Amazon Q Engineer pricing](https://aws.amazon.com/q/developer/pricing/) - licensing and cost information
- [AWS re:Post for Amazon Q](https://repost.aws/tags/TA4ckYf2i3Rh-L8LJ8eKPxqg/amazon-q) - community questions and answers

### Enterprise and security

- [Managing Amazon Q in your organisation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-iam.html) - IAM and access control
- [Amazon Q security](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security.html) - security features and best practices
- [Content exclusions](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-data-protection.html) - configuring what Amazon Q can access
- [AWS Artifact](https://aws.amazon.com/artifact/) - compliance reports and certifications

### Government procurement

- [Crown Commercial Service G-Cloud 14](https://www.crowncommercial.gov.uk/agreements/g-cloud-14) - UK government cloud services framework
- [AWS on G-Cloud](https://www.digitalmarketplace.service.gov.uk/) - search for AWS services including Amazon Q
- [TechUK framework](https://www.techuk.org/) - alternative procurement route

### NCSC guidance

- [Cloud security principles](https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles) - assessing cloud services
- [Secure development and deployment guidance](https://www.ncsc.gov.uk/collection/developers-collection) - security best practices
- [Vulnerability disclosure](https://www.ncsc.gov.uk/information/vulnerability-disclosure-toolkit) - handling security issues

### Repository resources

- [AI SDLC playbook](../../playbooks/ai-sdlc-playbook.md) - integrating AI Engineering Lab tools across development lifecycle
- [Model selection playbook](../../playbooks/model-selection.md) - choosing appropriate tools for tasks
- [GitHub Copilot manager guide](../copilot/README.md) - complementary tool for inline completions

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for contribution guidelines.

We encourage contributions from across government to keep this repository current and comprehensive. Share your team's experience, lessons learned, and effective practices to help other government departments.

Before contributing, read [CONTRIBUTING.md](../../CONTRIBUTING.md) which covers:
- content standards and style guide
- review and approval process
- accessibility requirements
- how to submit changes

## Support and contact

| Need | Contact |
|------|---------|
| General enquiries | to be confirmed |
| FDE support requests | to be confirmed |
| Urgent issues | to be confirmed |
| Content feedback | to be confirmed |

Contact channels to be confirmed.

## Licence

This repository is published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

You are encouraged to use and adapt these materials for your own government context.

When reusing content:
- maintain attribution to this repository
- share improvements back via contribution
- ensure adaptations remain suitable for government use