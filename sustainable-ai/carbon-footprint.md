
> Alpha
> This is a new service. Your feedback will help us to improve it.
> https://github.com/govuk-digital-backbone/aiengineeringlab/discussions

# Carbon footprint of AI coding assistants

A kgCO2e analysis of different AI coding assistants.

## Introduction

You need to understand the carbon footprint of AI coding assistants to support sustainable technology decisions. This document sets out carbon emission estimates in kilograms of CO2 equivalent for four AI tools used in the DSIT AI Engineering Lab programme. These tools are GitHub Copilot, Amazon Q, Claude Code and Gemini Code Assist.

AI companies rarely publish emissions data. The estimates here come from independent research, academic studies and vendor information where available. Treat these figures as indicative. Actual emissions vary by infrastructure, data centre location and usage patterns.

## Understanding kgCO2e

kgCO2e means kilograms of carbon dioxide equivalent. This measures greenhouse gas emissions by converting all gases into equivalent CO2 based on warming potential.

1kg of CO2e is equivalent to:

- driving a petrol car for around 2.5 miles
- charging a smartphone around 120 times
- watching around 5 hours of streamed video
- making around 5,000 online searches

## Carbon emissions from inference and training

Inference now represents more than 80% of total AI electricity use. Training uses significant power but takes place far less often. Inference happens for every interaction and creates most operational emissions.

Inference emissions for coding assistants serving large engineering teams exceed the training emissions spread across the model lifetime.

## Estimated carbon footprint by tool

### GitHub Copilot

Estimated emissions per interaction show:

- 0.1 to 0.5 grams CO2e per code suggestion
- 100 to 500 grams CO2e per 1,000 code completions
- 1 to 5 kilograms CO2e per 10,000 interactions

Annual use for one engineer shows:

- around 1.1 to 5.5 kilograms CO2e per year
- equivalent to driving around 4 to 22 kilometres

Deployment features include:

- Microsoft Azure infrastructure with varied renewable energy use
- smaller models that support inline suggestions
- chat mode that uses larger models and increases emissions

### Amazon Q

Estimated emissions per interaction show:

- 0.08 to 0.4 grams CO2e per code suggestion
- 80 to 400 grams CO2e per 1,000 code completions
- 0.8 to 4 kilograms CO2e per 10,000 interactions

Annual use for one engineer shows:

- around 0.9 to 4.4 kilograms CO2e per year
- equivalent to driving around 3.5 to 17.5 kilometres

Deployment features include:

- AWS infrastructure with strong renewable energy commitments
- a move towards 100% renewable energy by 2025
- regional variation in carbon intensity
- optimisation for inference efficiency

### Claude Code

Estimated emissions per interaction show:

- 0.3 to 0.8 grams CO2e per code suggestion
- 300 to 800 grams CO2e per 1,000 code completions
- 3 to 8 kilograms CO2e per 10,000 interactions

Annual use for one engineer shows:

- around 3.3 to 8.8 kilograms CO2e per year
- equivalent to driving around 13 to 35 kilometres

Efficiency improvements include:

- extended thinking methods that reduce energy use
- energy use of 17.045 watt hours for long form input
- a focus on inference optimisation

Deployment features include:

- AWS and Google Cloud infrastructure
- renewable energy commitments
- limited emissions reporting

### Gemini Code Assist

Estimated emissions per interaction show:

- 0.03 to 0.15 grams CO2e per code suggestion
- 30 to 150 grams CO2e per 1,000 code completions
- 0.3 to 1.5 kilograms CO2e per 10,000 interactions

Annual use for one engineer shows:

- around 0.33 to 1.65 kilograms CO2e per year
- equivalent to driving around 1.3 to 6.6 kilometres

Efficiency features include:

- published methodology from 2025
- median Gemini prompt output of around 0.03 grams CO2e
- a 33 times energy reduction in one year
- a 44 times carbon reduction in one year

Deployment features include:

- Google TPU infrastructure
- renewable energy matched to 100% in 2023
- detailed carbon accounting including PUE and WUE

## Comparative analysis

### Emissions ranking from lowest to highest for 10,000 interactions

| AI coding assistant | CO2e emissions |
|---------------------|----------------|
| Gemini Code Assist  | 0.3 to 1.5 kilograms |
| Amazon Q            | 0.8 to 4 kilograms   |
| GitHub Copilot      | 1 to 5 kilograms     |
| Claude Code         | 3 to 8 kilograms     |

### Programme scale impact

#### Annual carbon footprint for 500 engineers

| AI coding assistant | CO2e emissions |
|---------------------|----------------|
| Gemini Code Assist  | 165 to 825 kilograms |
| Amazon Q            | 450 to 2,200 kilograms |
| GitHub Copilot      | 550 to 2,750 kilograms |
| Claude Code         | 1,650 to 4,400 kilograms |

#### Real world comparison for 500 engineers

| AI coding assistant | Driving distance in miles | Trips from London to Edinburgh |
|---------------------|---------------------------|-------------------------------|
| Gemini              | 410 to 2,050              | 1 to 3                        |
| Amazon Q            | 1,120 to 5,470            | 3 to 14                       |
| GitHub Copilot      | 1,370 to 6,835            | 3 to 17                       |
| Claude              | 4,100 to 10,935           | 10 to 28                      |

## Factors affecting actual emissions

### Usage patterns

Chat interactions produce higher emissions because they use larger context windows:

- generating between 3 and 5 times more emissions
- increasing emissions by around 400% when prompts are poor
- generating between 10 and 30 times more emissions when using reasoning models

### Infrastructure variables

Emissions vary by data centre location.

| Location | Typical CO2 per kilowatt hour consumption |
|----------|-------------------------------------------|
| France | 56 grams |
| UK | 230 grams |
| Germany | 380 grams |
| USA | 445 grams |

Hardware efficiency varies. Efficiency is typically increased with:

- H100 and H200 GPUs
- Google TPUs designed for inference
- modern data centres with power use effectiveness of 1.1 to 1.2

Age of infrastructure also affects efficiency. Emissions typically increase with:

- older GPUs, as energy use increases
- older facilities, which may have PUE between 1.5 and 2.0

### Temporal factors

Model updates improve efficiency. Renewable energy availability varies with season and time of day.

## Sustainability recommendations

### Tool selection

Gemini Code Assist provides the lowest carbon footprint where efficiency is the priority. Amazon Q offers balanced efficiency and strong sustainability commitments. Select models based on functional need and carbon impact.

### Usage optimisation

You can reduce emissions through:

- inline suggestions instead of chat where practical
- precise prompts that reduce token output
- early cancellation of unneeded generation
- smaller models for simple tasks

### Monitoring and reporting

You should support sustainability by:

- monitoring usage and token patterns
- setting guidance for efficient consumption
- reporting carbon metrics in programme reporting
- helping engineers understand environmental impact

## Limitations and caveats

### Data transparency

Most vendors do not publish per query emissions. Estimates use academic research, industry benchmarks and limited disclosures.

### Scope boundaries

The estimates cover scope 3 inference emissions. They exclude training emissions, device power use, network energy use, embodied carbon and wider infrastructure overhead.

### Variability

Actual emissions vary by prompt complexity, response length, grid intensity and server load. The range can vary by 2 to 5 times.

## Conclusion

Carbon footprints vary across AI coding assistants. Gemini Code Assist shows the lowest emissions. Claude Code shows the highest. Programme scale use across 500 engineers results in annual emissions between 0.17 and 4.4 tonnes CO2e depending on tool choice.

While these emissions are modest compared to other organisational activities (equivalent to 1 to 28 return trips from London to Edinburgh), they represent an opportunity for informed decision-making. As AI adoption scales across government, tool selection based on efficiency, combined with optimised usage patterns, can meaningfully reduce environmental impact while maintaining productivity gains.

You should:

- include carbon footprint in tool comparison framework
- request vendor transparency on emissions data
- monitor usage patterns and intervene on inefficient consumption
- educate users on the environmental context of AI tool usage
- report carbon metrics alongside productivity and adoption data


## References

### Gemini Code Assist

['Measuring the environmental impact of AI inference.'](https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference), technical report on Gemini Apps median prompt: 0.24 Wh energy, 0.03 gCO2e emissions. 

['Measuring the environmental impact of delivering AI at Google Scale.'](https://arxiv.org/pdf/2508.15734), comprehensive methodology including PUE, WUE, and full infrastructure overhead.

['In a first, Google has released data on how much energy an AI prompt uses.'](https://www.technologyreview.com/2025/08/21/1122288/google-gemini-ai-energy/), analysis of Google's disclosure methodology.

### Claude Code

['How Hungry is AI? Benchmarking Energy, Water, and Carbon Footprint of LLM Inference.'](https://www.researchgate.net/publication/391741710_How_Hungry_is_AI_Benchmarking_Energy_Water_and_Carbon_Footprint_of_LLM_Inference), Claude 3.7 Sonnet eco-efficiency score: 0.825, 17.045 Wh for long-form input. Independent academic benchmarking of Claude models across energy, water, and carbon metrics.

### GitHub Copilot

GitHub Changelog (2025). Multiple announcements detailing GPT-4o Copilot, GPT-4.1 Copilot, and GPT-4.5 model deployments. No direct carbon emissions data published. Multiple citations including [GPT-4.1 general availability](https://github.blog/changelog/2025-05-08-openai-gpt-4-1-is-now-generally-available-in-github-copilot-as-the-new-default-model/), [GPT-4o deprecation](https://github.blog/changelog/2025-08-06-deprecation-of-gpt-4o-in-copilot-chat/), [GPT-4o Copilot code completion](https://github.blog/changelog/2025-03-27-gpt-4o-copilot-your-new-code-completion-model-is-now-generally-available/), [GPT-4.1 code completion](https://github.blog/changelog/2025-08-27-copilot-code-completion-now-uses-the-gpt-4-1-copilot-model/) and [GPT-4.5 deprecation](https://github.blog/changelog/2025-06-20-upcoming-deprecation-of-o1-gpt-4-5-o3-mini-and-gpt-4o/).

OpenAI CEO Sam Altman (June 2025). ChatGPT query estimate: 0.34 Wh per query. Cited in multiple sources as reference for GPT-4o-level inference. Multiple citations including ['ChatGPT energy usage is 0.34 Wh per query'](https://www.devsustainability.com/p/chatgpt-energy-usage-is-034-wh-per), ['ChatGPT queries consume 0.34 watt-hours of electricity and 0.000085 gallons of water'](https://www.datacenterdynamics.com/en/news/sam-altman-chatgpt-queries-consume-034-watt-hours-of-electricity-and-0000085-gallons-of-water/) and ['Let’s Analyze OpenAI’s Claims About ChatGPT Energy Use'](https://towardsdatascience.com/lets-analyze-openais-claims-about-chatgpt-energy-use/).

['Green My LLM: Studying the key factors affecting the energy consumption of code assistants.'](https://arxiv.org/abs/2411.11892), an analysis of code assistant energy consumption patterns (not GitHub Copilot specifically, but applicable insights).

### Amazon Q

Amazon Sustainability Report (July 2025). General sustainability commitments and AWS renewable energy targets. No per-query emissions data published for Amazon Q. Multiple citations including [Main sustainability page](https://sustainability.aboutamazon.com/), [Report (2024)](https://sustainability.aboutamazon.com/2024-amazon-sustainability-report.pdf), [Sustainability in the Cloud](https://sustainability.aboutamazon.com/environment/the-cloud) and [Progress](https://sustainability.aboutamazon.com/progress).

AWS has committed to 100% renewable energy by 2025 (mentioned in multiple sustainability reports).

Estimates extrapolated from industry benchmarks for similar-sized models on AWS infrastructure.

### General AI emissions research

['What's the carbon footprint of using ChatGPT or Gemini?'](https://hannahritchie.substack.com/p/ai-footprint-august-2025), an analysis of AI emissions estimates and methodology comparison.

['Carbon Footprint Evaluation of Code Generation through LLM as a Service.'](https://link.springer.com/chapter/10.1007/978-3-658-45010-6_15), a framework for evaluating embodied and operational carbon in code generation.

Multiple sources (2023 to 2025). Industry consensus that inference now represents 80% and over of total AI electricity consumption, not training.

### Important notes on data quality

| Vendor | Notes |
|--------|-------|
| Google (Gemini) | Only vendor with published, peer-reviewed methodology and actual measured data (not estimates) |
| Anthropic (Claude) | Limited emissions data. Estimates based on independent academic benchmarking. |
| GitHub and Microsoft (Copilot) | No direct emissions disclosure. Estimates based on underlying GPT-4o and 4.1 model data. |
| Amazon (Q) | No published per-query emissions data. Estimates based on AWS infrastructure sustainability reports and industry benchmarks |