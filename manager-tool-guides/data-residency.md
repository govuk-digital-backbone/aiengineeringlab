> **ALPHA**
> This is a new service. Your [feedback](https://github.com/govuk-digital-backbone/aiengineeringlab/discussions) will help us to improve it.

# AI code assistant data residency
Data residency refers to the geographic location where data is stored and processed, which is critical for compliance with regulations like UK data protection laws and organizational security requirements.

Data residency for DSIT recommended AI coding tools. This guidance focuses on suitability for UK residency.

| Tool | Explicit UK data residency | UK residency assurance | Summary |
|---|---|---|---|
| GitHub Copilot | No | Low | EU only for enterprise with no UK option |
| Amazon Kiro | No explicit guarantee | Low to medium | Implicit through AWS or local execution |
| Amazon Q | Yes when configured | Medium to high | UK London region when tightly pinned |
| Gemini Code Assist Enterprise | Yes | High | UK storage and processing |
| Claude Code | No | Medium | EU regional option planned, UK not available |

If you must make a defensible claim of UK only data residency, the strongest option currently available is:

- Gemini Code Assist Enterprise on Google Cloud  
- Amazon Q when explicitly pinned to the AWS London region  

## GitHub Copilot

### Residency overview

GitHub Copilot inherits its data residency from GitHub Enterprise Cloud. GitHub supports EU data residency which became generally available in October 2024.

The UK is not available as a selectable residency region.

### Implications

Code context and prompts may be processed in EU or US regions. This meets many EU GDPR requirements but does not meet UK only sovereignty requirements.

### Verdict

GitHub Copilot is EU resident, not UK resident.

### References

[GitHub Enterprise Cloud data residency](https://docs.github.com/en/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency)

[GitHub announcement on EU data residency](https://github.com/newsroom/press-releases/data-residency-in-the-eu)

[GitHub changelog EU residency](https://github.blog/changelog/2024-10-29-github-enterprise-cloud-data-residency-in-the-eu-is-generally-available/)

## Amazon Kiro

### What it is

Amazon Kiro is an agent based AI IDE and command line tool. It runs partly on the developer machine and partly against AWS hosted services.

### Residency overview

Amazon does not publish a Kiro specific data residency commitment. Data location depends on the local execution context and the AWS services and regions that are indirectly used.

### Implications

Residency is implicit rather than contractually guaranteed. This creates a weak position for regulated or audited UK only requirements.

### Verdict

Amazon Kiro is UK capable in practice, but without any explicit UK residency guarantee.

### References

[Transform DevOps practice with Kiro](https://aws.amazon.com/blogs/publicsector/transform-devops-practice-with-kiro-ai-powered-agents/)

[Kiro official site](https://kiro.dev/)

[Kiro launch and positioning](https://www.geekwire.com/2025/amazons-surprise-indie-hit-kiro-launches-broadly-in-bid-to-reshape-ai-powered-software-development/)

## Amazon Q developer and business

### Residency overview

Amazon Q services are available in multiple AWS regions including Europe London. Some Amazon Q variants support region local storage and processing.

### Key caveat

Cross region processing can occur by default. Administrators must take action to:

- pin services to the London region  
- restrict cross region inference and access  

### Implications

With strong AWS governance controls, Amazon Q can meet UK residency requirements. Without those controls, residency guarantees are weakened.

### Verdict

Amazon Q UK residency is achievable, but configuration and governance are required.

### References

[Supported regions](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/regions.html)

[EU region launch](https://aws-news.com/article/01963573-891b-093c-5176-af1477748270)

[Amazon Q Business Europe and data sovereignty](https://www.itpro.com/technology/artificial-intelligence/amazon-q-business-europe-data-sovereignty)

[Amazon Q in QuickSight](https://community.amazonquicksight.com/t/amazon-q-in-quicksight-is-now-available-in-5-additional-regions/34268)

## Gemini Code Assist enterprise on Google Cloud

### Residency overview

Gemini Code Assist inherits Gemini enterprise data residency controls.

When used through Google Cloud enterprise editions, data storage and processing can be restricted to the UK region. This includes both prompt data and generated outputs.

### Implications

Gemini Code Assist provides the strongest current option for defensible UK only residency.

Controls are explicit, documented, and enforceable through Google Cloud configuration.

### Verdict

Gemini Code is UK resident for storage and processing. High confidence option for regulated environments.

### References

[Gemini Enterprise locations & data residency](https://docs.cloud.google.com/gemini/enterprise/docs/locations)

[Google Cloud blog – UK ML processing for Gemini](https://blog.google/company-news/inside-google/around-the-globe/google-europe/united-kingdom/data-residency-machine-learning-processing-uk/)

[IT Pro – Google Cloud announces UK Gemini residency](https://www.itpro.com/cloud/cloud-computing/google-cloud-announces-new-data-residency-flexibility-for-uk-firms-accelerator-for-regional-startups)

## Claude Code

### Residency overview

Claude Code can be used directly via **Anthropic** or via hyperscalers.

By default, when Claude Code is hosted and managed by Anthropic, customer data may be processed in multiple global locations. Customer data is stored in the United States by default.

### Implications

Regional data residency options are limited at present. UK data residency is not currently available.

### Verdict

Not UK-resident today. EU regional support is planned but not yet in GA.

### References

[Anthropic server locations](https://privacy.claude.com/en/articles/7996890-where-are-your-servers-located-do-you-host-your-models-on-eu-servers)

[Claude API data residency controls](https://platform.claude.com/docs/en/build-with-claude/data-residency)

[Claude regional compliance and roadmap](https://claude.com/regional-compliance)

[Anthropic as subprocessor](https://learn.microsoft.com/en-us/copilot/microsoft-365/connect-to-ai-subprocessor)

