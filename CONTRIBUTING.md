> **ALPHA**
> This is a new service – your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.
# Contributing to this repository

> How to propose, submit, and review contributions to the AI Engineering Lab repository.

Thank you for your interest in improving this repository. Contributions from across government help keep these materials current, comprehensive, and practically useful.

## Before you contribute

### Who can contribute

This repository welcomes contributions from:

- civil servants across all government departments
- contractors and suppliers working on government projects
- arm's length bodies and agencies
- Forward Deployed Engineers (FDEs) capturing learnings from engagements

### Types of contribution

| Contribution type | Examples | Process |
|-------------------|----------|---------|
| Bug fixes | Typos, broken links, factual errors | Quick fix process |
| Minor improvements | Clarifications, additional examples, formatting | Standard process |
| New content | New playbooks, prompts, case studies | Full review process |
| Structural changes | New sections, reorganisation | Proposal required |
| Tool-specific guides | New AI assistant coverage | Full review and security assessment |

### What we are looking for

We welcome:

- practical examples from real adoption experiences
- prompts that have proven effective in government contexts
- case studies (anonymised where necessary)
- accessibility improvements
- corrections to outdated information
- integration patterns for government technology stacks
- translations or plain English improvements

### What requires additional review

The following contributions require security or governance review before merging:

- content relating to security controls or guardrails
- tool-specific configuration guidance
- incident response procedures
- any content mentioning specific vulnerabilities
- integration patterns involving authentication or secrets

### Writing style

All content must follow [GOV.UK content design principles](https://www.gov.uk/guidance/content-design/writing-for-gov-uk):

1. Use plain English, avoid jargon and explain technical terms on their first use.
2. Use active voice. Write 'Review the code' not 'The code should be reviewed'.
3. Front-load information and put the most important point first.
4. Keep sentences short and aim for 25 words or fewer per sentence.
5. Use short paragraphs with one idea per paragraph and 2 to 3 sentences maximum.
6. Be direct. Use 'you' to address the reader and use 'we' for the repository team.

**KB NOTE: each numbered step must be a single, complete sentence, starting with an uppercase letter and ending with a full stop (not a question mark). I have changed the first step as an example.**

### Formatting standards

Headings must:

- use sentence case (capitalise first word only)
- use heading levels sequentially (do not skip from H2 to H4)
- keep headings descriptive and actionable

Lists:

- use bullet points for unordered items
- use numbered lists only for sequential steps
- start each item with a capital letter
- do not use full stops at the end of list items unless they are complete sentences

Code examples:

- use fenced code blocks with language identifiers
- keep examples concise and focused
- include comments explaining non-obvious elements
- test all code examples before submitting

Links:

- use descriptive link text (not 'click here')
- use relative links for internal repository references
- check all links work before submitting

**KB NOTE: bulletpoints must always have a lead-in line which, together with each bullet, makes a complete sentence. I have adjusted the first list as an example - "Headings must:".** 

## Accessibility requirements

All contributions must meet the following accessibility standards.

**KB NOTE: no lead-in line required for checkboxes. Edited above sentence so it ends with a period, not a colon.**

### Text content

- [ ] Use clear, simple language (aim for reading age 9)
- [ ] Provide alt text descriptions for any images
- [ ] Do not use colour alone to convey meaning
- [ ] Define acronyms on first use
- [ ] Use descriptive link text

### Structure

- [ ] Use proper heading hierarchy
- [ ] Use semantic markup (lists, tables, headings)
- [ ] Keep tables simple and avoid merged cells
- [ ] Provide table headers for data tables

### Code examples

- [ ] Do not rely on syntax highlighting alone
- [ ] Include comments for complex logic
- [ ] Ensure examples are screen-reader friendly when rendered

### Cognitive accessibility

- [ ] Break complex content into manageable chunks
- [ ] Use consistent terminology throughout
- [ ] Provide summaries for long documents
- [ ] Include practical examples alongside theory

For detailed guidance, see the repository's accessibility documentation.

**KB NOTE: These checkboxes are correctly formatted; uppercase letter and full stop. For reference, they follow [these rules](https://service-manual.ons.gov.uk/design-system/components/checkboxes).**

## Contribution process

### Quick fixes (typos, broken links)

1. Fork the repository.
2. Make your change in a new branch.
3. Submit a pull request with a clear description.
4. A maintainer will review and merge within 5 working days.

### Standard contributions

Standard contributions include improvements, clarifications, and new examples.

1. Check existing content and ensure your contribution is not duplicating existing material.
2. Open an issue first and describe what you are proposing and why.
3. Wait for feedback. A maintainer will respond within 5 working days.
4. Fork and branch. Create a branch with a descriptive name using format: 'type/brief-description'. Examples: 'fix/broken-copilot-link', 'add/terraform-prompt-examples'.
5. Make your changes and follow content standards above.
6. Self-review and check against the quality checklist below.
7. Submit pull request and reference the original issue.
8. Respond to feedback and make requested changes promptly.
9. Approval and merge. Maintainers will merge approved contributions.

**KB NOTE: As above, numbered steps are single, complete sentences and there is no lead-in line. I have adjusted the first 2 as an example. 'Quick fixes' doesn't need anything other than the steps and subtitle but 'standard contributions' requires an extra sentence to clarify what they are.**

### New content or structural changes

For significant new content or repository changes:

1. Submit a proposal and open an issue using the 'Content Proposal' template.
2. Include in your proposal: what you are proposing, why it is needed, who will benefit, outline of content structure, estimated effort, and any security or governance considerations.
3. Proposal review. The team will review within 5 working days.
4. Approval to proceed. You will receive feedback and approval (or suggestions for alternative approaches).
5. Create content and follow the standard contribution process above.
6. Enhanced review. New content receives additional scrutiny from subject matter experts.

## Quality checklist

Before submitting, verify your contribution against this checklist:

### Content quality

- [ ] Follows GOV.UK writing style
- [ ] Accurate and factually correct
- [ ] Provides practical, actionable guidance
- [ ] Includes relevant examples
- [ ] Appropriate for government context
- [ ] Does not duplicate existing content

### Technical accuracy

- [ ] Code examples are tested and working
- [ ] Commands and configurations are correct
- [ ] Version numbers and links are current
- [ ] Tool-specific guidance matches current tool versions

### Security and governance

- [ ] Suitable for OFFICIAL classification
- [ ] Does not expose sensitive information
- [ ] Follows security best practices
- [ ] Does not include real credentials, keys, or secrets
- [ ] Aligns with guardrails and compliance requirements

### Accessibility

- [ ] Meets accessibility requirements above
- [ ] Tested with accessibility tools where applicable

### Metadata

- [ ] Document metadata is complete
- [ ] Version number is appropriate
- [ ] Links to related documents are included
- [ ] References are properly cited

### What reviewers check

Maintainers review contributions for:

1. Alignment. Does it fit the repository's purpose and scope?
2. Quality. Does it meet content standards?
3. Accuracy. Is the technical content correct?
4. Security. Is it safe for government use?
5. Accessibility. Does it meet accessibility standards?
6. Consistency. Does it align with existing content?

### Review outcomes

- **Approved** - Merged as submitted
- **Approved with changes** - Minor edits made by maintainer before merge
- **Changes requested** - Feedback provided and contributor makes updates
- **Declined** - Does not meet requirements and feedback provided

**KB NOTE: don't use bold for emphasis.**

## Recognition

Contributors are recognised through:

- attribution in document metadata where appropriate
- listing in the repository's contributors file
- acknowledgement in release notes for significant contributions

## Getting help

If you need assistance with contributing:

| Need | Contact |
|------|---------|
| Process questions | gdsengineeringexcellence@dsit.gov.uk |
| Technical guidance | to be confirmed |
| Content standards | to be confirmed |
| Accessibility advice | to be confirmed |

**KB NOTE: each cell in a table should start with an uppercase letter and no full stops. You do not use a lead-in line but you can add a full sentence above if the table needs additional explanation. Full layout [rules are here](https://service-manual.ons.gov.uk/design-system/components/table).

## Intellectual property

By contributing to this repository, you confirm that:

1. Your contribution is your own original work, or you have permission to submit it.
2. You have the right to grant the licence below.
3. Your contribution does not infringe any third-party intellectual property rights.
4. Your contribution is suitable for publication under the Open Government Licence.

Contributions are published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

## Related documents

- [README.md](README.md) - Repository overview
- [Repository structure](REPOSITORY-STRUCTURE.md) - Repository structure outline

## References

- [GOV.UK Content Design Guide](https://www.gov.uk/guidance/content-design)
- [GOV.UK Writing for GOV.UK](https://www.gov.uk/guidance/content-design/writing-for-gov-uk)
- [Civil Service Code](https://www.gov.uk/government/publications/civil-service-code/the-civil-service-code)
- [Open Government Licence](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
