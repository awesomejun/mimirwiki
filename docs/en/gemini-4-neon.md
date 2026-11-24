---
title: "Gemini 4 Neon"
subtitle: "Google DeepMind multimodal reasoning model released in November 2026 for coding, science, and enterprise workflows"
canonical_url: https://mimirwiki.com/wiki/gemini-4-neon
language: en
page_class: entity
revision_sha256: 7f5ff5cb9703458a4a763af9c757beee0c3f80c64e6579b712894e9b23f2e7c5
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/wiki/gemini-4-neon.md
  txt: https://mimirwiki.com/wiki/gemini-4-neon.txt
  json: https://mimirwiki.com/wiki/gemini-4-neon.json
  jsonld: https://mimirwiki.com/wiki/gemini-4-neon.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/gemini-4-neon
  ja: https://mimirwiki.com/ja/wiki/gemini-4-neon
  zh: https://mimirwiki.com/zh/wiki/gemini-4-neon
---

# Gemini 4 Neon

> Gemini 4 Neon (`gemini-4-neon`) is a multimodal reasoning large language model released by Google DeepMind on November 18, 2026. Adapted from Gemini 4 Carbon, it processes text, images, audio, video, and PDFs across a unified 1,000,000-token context window with up to 64,000 synchronous output tokens (or 1,000,000 via background long decode) and a March 2026 knowledge cutoff. As of 2026-11-23, standard API pricing is $3.00 per million input tokens, $0.15 per million cached input tokens, and $15.00 per million output tokens.

Gemini 4 Neon is a multimodal reasoning large language model developed by Google DeepMind and released on November 18, 2026, as part of the fourth-generation Gemini 4 series alongside Gemini 4 Carbon, Gemini 4 Hydrogen, and Gemini 4 Argon. Adapted from the flagship Gemini 4 Carbon model, Gemini 4 Neon (`gemini-4-neon`) is engineered to balance frontier analytical reasoning with lower latency and cost across software engineering, scientific research, cybersecurity defense, and enterprise workflows. It accepts text, image, audio, video, and PDF inputs in a unified 1,000,000-token context window and supports up to 64,000 default synchronous output tokens or up to 1,000,000 output tokens through background long decode. As of 2026-11-23, Gemini 4 Neon is available through the Gemini API in Google AI Studio, Google Cloud Model Garden, Gemini for business, and to paid Google AI Pro and Google AI Ultra subscribers in the Gemini app and Google Antigravity.

**Also known as:** gemini-4-neon, Google Gemini 4 Neon, Gemini 4.0 Neon

## Key facts

- **Release date:** 2026-11-18 (announced by Koray Kavukcuoglu, Google DeepMind) [1]
- **API model code and lineage:** gemini-4-neon (adapted from Gemini 4 Carbon) (as of 2026-11-23) [2]
- **Context window and output:** 1M unified tokens (64K default synchronous output; up to 1M via background long decode) (as of 2026-11-23) [2]
- **Standard API pricing:** $3.00 input, $0.15 cached input (95% discount), $15.00 output per 1M tokens (as of 2026-11-23) [4]
- **Knowledge cutoff:** March 2026 (as of 2026-11-23) [2]

## Basic facts

- **Developer:** Google DeepMind (Alphabet Inc.) [2]
- **Release date:** 2026-11-18 [1]
- **API model code:** gemini-4-neon (as of 2026-11-23) [3]
- **Base model lineage:** Adapted from Gemini 4 Carbon (Gemini 4 family: Carbon, Neon, Hydrogen, Argon) [2]
- **Supported modalities:** Text, image, audio, video, and PDF input; text output (as of 2026-11-23) [3]
- **Context window and output limit:** 1,000,000 unified context tokens; up to 64,000 synchronous output tokens / up to 1,000,000 via background long decode (as of 2026-11-23) [2]
- **Knowledge cutoff:** March 2026 (as of 2026-11-23) [2]
- **Standard API price (global):** $3.00 input / $0.15 cached input / $15.00 output (including thinking tokens) per 1M tokens (as of 2026-11-23) [4]
- **Cloud Priority and Batch prices:** Priority global: $5.40 input / $0.27 cache read / $27.00 output; Batch global: $1.50 input / $0.075 cache read / $7.50 output per 1M tokens (as of 2026-11-23) [5]
- **Distribution channels:** Gemini app, Gemini API, Google AI Studio, Gemini for business (Model Garden), Google Antigravity (as of 2026-11-23) [2]
- **Consumer plans:** Google AI Pro (5 TB) and Google AI Ultra (20 TB+; 5x AI Pro limits) (as of 2026-11-23) [8]

## Gemini 4 Neon overview, release, and position in the Gemini 4 family

Gemini 4 Neon is a multimodal reasoning large language model developed by Google DeepMind and introduced on November 18, 2026, in an announcement authored by Koray Kavukcuoglu, Senior Vice President at Google DeepMind and Chief AI Architect at Google.[1][2] Within the [Google Gemini](https://mimirwiki.com/wiki/google-gemini) 4 model catalog listed in Google AI Studio documentation as of 2026-11-23, Google offers four element-named models: Gemini 4 Carbon (`gemini-4-carbon`), Gemini 4 Neon (`gemini-4-neon`), Gemini 4 Hydrogen (`gemini-4-hydrogen`), and Gemini 4 Argon (`gemini-4-argon`).[3]

According to the Google DeepMind model card published on November 18, 2026, Gemini 4 Neon is adapted from Gemini 4 Carbon and shares Carbon's underlying architecture, training dataset, data processing pipeline, hardware, and software infrastructure.[2] While Google positions Gemini 4 Carbon for the hardest long-horizon projects and Gemini 4 Hydrogen for high-speed everyday tasks, Gemini 4 Neon is designed as an intermediate frontier tier that combines analytical depth with faster end-to-end execution and lower per-task cost, either operating standalone or acting as an orchestrator directing parallel Gemini 4 Hydrogen subagents in Google Antigravity.[1][2]

As of 2026-11-23, Gemini 4 Neon is distributed across five official channels: the Gemini app, the Gemini Developer API, Google AI Studio, Gemini for business (including Google Cloud Model Garden), and the Google Antigravity agentic development platform.[1][2] On the consumer and prosumer side, Google One bundles access to Gemini 4 Neon in the Google AI Pro plan (which includes 5 TB of storage, 200 monthly Google Colab compute units, and $10 in monthly Google Cloud credits) and the Google AI Ultra plan (which starts at 20 TB of storage, adds Gemini 4 Carbon, provides 5x higher Gemini usage limits than AI Pro, and includes 2,000 monthly Colab compute units and $40 in monthly Google Cloud credits), whereas the entry-level Google AI Plus plan (400 GB storage) includes Gemini 4 Hydrogen.[8]

## Gemini 4 Neon technical specifications, modalities, and long-decode architecture

In the Gemini API and Google DeepMind model card as of 2026-11-23, Gemini 4 Neon (`gemini-4-neon`) natively accepts text strings, images, audio, video files, and PDF documents within a unified input-output context window of up to 1,000,000 tokens.[1][2][3] For generation, the model supports up to 64,000 default synchronous output tokens and up to 1,000,000 output tokens when using background long decode.[2][3][4] The model card states that Gemini 4 Neon has a knowledge cutoff of March 2026.[2]

| Specification | Gemini 4 Neon (`gemini-4-neon`) |
| --- | --- |
| Developer | Google DeepMind (Alphabet Inc.) |
| Release date | November 18, 2026 |
| Base architecture and lineage | Adapted from Gemini 4 Carbon (`gemini-4-carbon`) |
| Input modalities | Text, Image, Audio, Video, PDF |
| Output modality | Text (including reasoning / thinking tokens) |
| Context window | 1,000,000 unified input-output tokens |
| Maximum output tokens | 64,000 default synchronous / up to 1,000,000 via background long decode |
| Knowledge cutoff | March 2026 |
| Caching support on Gemini API | Implicit context caching at $0.15 / 1M tokens (explicit caching not supported) |

Gemini 4 Neon supports configurable thinking levels (including default `high` and `xhigh`), context compaction during extended multi-turn agent sessions, and tool orchestration including [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (MCP) servers and `/swarm` multi-agent execution in Google Antigravity.[1] In its launch post, Google demonstrated Gemini 4 Neon's long-decode and agent-swarm capabilities in Google Antigravity across four reference builds: driving Blender MCP to render a 3D laboratory bench with Bunsen flames for Carbon and Hydrogen and gas discharge tubes for Argon and Neon; writing a 10,200-line custom-shader WebGL2 freeride ski simulator on Mont Blanc and Chamonix elevation data at 120 Hz physics with zero pre-made assets; reconstructing Alan Turing's 1936 study at King's College, Cambridge (Room X.8) in interactive 3D with a working Universal Turing Machine; and converting a single photograph into a 100,000-cell Google Sheet using over 500,000 live spreadsheet formulas for edge detection, 3D depth mapping, and scene relighting without embedded images or Apps Script.[1]

## Gemini 4 Neon API and Google Cloud pricing, caching, and rate limits

Gemini 4 Neon is offered exclusively on paid tiers of the Gemini Developer API (not available on the Free tier) and on Google Cloud Model Garden.[4][5] Every token processed by the model is metered and billed, including internal thinking tokens and tool system instructions or function declarations when grounding is enabled.[4] On the Gemini Developer API, context caching for Gemini 4 Neon uses implicit caching only, priced at $0.15 per 1 million cached input tokens (a 95% discount off the $3.00 base input rate), while Grounding with Google Search includes 5,000 free search requests per month shared across Gemini 3 and newer models, followed by $14.00 per 1,000 requests (capped at 1,500 requests per day by default).[1][4][6]

On Google Cloud Model Garden (Agent Platform), pricing as of 2026-11-23 varies across Standard, Priority, and Batch processing modes and between global and non-global (regional) endpoints, with explicit cache write pricing scheduled to take effect on January 12, 2027.[5]

| Platform and service tier (as of 2026-11-23) | Endpoint region | Input (text, image, video, audio) | Cache read | Cache write (effective 2027-01-12) | Text output (response and reasoning) |
| --- | --- | --- | --- | --- | --- |
| Gemini Developer API (Paid tier) | Global | $3.00 / 1M | $0.15 / 1M (implicit) | Not supported | $15.00 / 1M |
| Google Cloud Model Garden - Standard | Global | $3.00 / 1M | $0.15 / 1M | $3.75 / 1M | $15.00 / 1M |
| Google Cloud Model Garden - Standard | Non-global | $3.30 / 1M | $0.165 / 1M | $4.125 / 1M | $16.50 / 1M |
| Google Cloud Model Garden - Priority | Global | $5.40 / 1M | $0.27 / 1M | $6.75 / 1M | $27.00 / 1M |
| Google Cloud Model Garden - Priority | Non-global | $5.94 / 1M | $0.297 / 1M | $7.425 / 1M | $29.70 / 1M |
| Google Cloud Model Garden - Batch | Global | $1.50 / 1M | $0.075 / 1M | $1.875 / 1M | $7.50 / 1M |
| Google Cloud Model Garden - Batch | Non-global | $1.65 / 1M | $0.0825 / 1M | $2.0625 / 1M | $8.25 / 1M |

On Google Cloud, customers are billed only for requests that return an HTTP 200 status code, while 4xx and 5xx responses incur no token charges.[5] On the Gemini Developer API, project-level rate limits and spend-based rate limits apply across usage tiers: Tier 1 (active linked billing account, $250 monthly billing cap, $10 spend limit per rolling 10-minute window), Tier 2 ($100 cumulative spend plus 3 days, $2,000 billing cap, $200 per 10-minute window), and Tier 3 ($1,000 cumulative spend plus 30 days, $20,000 to $100,000+ billing cap, $200 per 10-minute window), returning `429 RESOURCE_EXHAUSTED` when exceeded.[6]

## Gemini 4 Neon benchmark evaluations

In the Gemini 4 Neon model card and launch announcement published on November 18, 2026, Google DeepMind reported benchmark evaluations comparing Gemini 4 Neon against [Claude](https://mimirwiki.com/wiki/claude) Opus 5.5 and OpenAI's [GPT-6.2](https://mimirwiki.com/wiki/gpt-6-2) Sol across capability indices, agentic coding, enterprise knowledge work, scientific and mathematical reasoning, multimodal understanding, long-context retrieval, and cybersecurity.[1][2]

| Category | Benchmark | Gemini 4 Neon | Claude Opus 5.5 | GPT-6.2 Sol |
| --- | --- | --- | --- | --- |
| Capability indices | Artificial Analysis Intelligence Index v5.0.1 | 61 | 59 | 57 |
| Capability indices | Vals Index v2.2 | 70.9% | 70.1% | 66.1% |
| Agentic coding | CursorBench 4.1 | 65.4% | 58.1% | Not reported |
| Agentic coding | Terminal-Bench 4.1 (cheating-adjusted) | 65.2% | 65.8% | 61.5% |
| Agentic coding | FrontierCode 2.0 (main score) | 46.2% | 47.3% | 43.8% |
| Agentic coding | SWE-sweep (provider harness / mini-SWE harness) | 39.0% / 12.8% | 10.1% / 3.6% | 8.3% / 11.6% |
| Knowledge work | Zapier AutomationBench | 56.3% | 42.5% | 41.3% |
| Knowledge work | Agents' Last Exam v1.1 | 75.8% | 71.6% | 73.0% |
| Science and math | RiemannBench | 84.0% | 80.0% | 80.0% |
| Science and math | Terminal-Bench-Science 0.1 | 70.5% | 63.3% | 68.0% |
| Reasoning | HLE-Diamond | 71.3% | 67.9% | 64.0% |
| Multimodal | MKA Climb WSR / Chartography / LVBench | 56.5% / 73.5% / 89.0% | 53.0% / 66.3% / 83.7% | 52.7% / 75.1% / 87.6% |
| Long context | GraphWalks (256K to 1M, BFS F1) | 95.2% | 66.8% | 80.1% |
| Cybersecurity | CWE-Bench v2 / SEC-bench Pro / WebExploitBench v1.2 | 70.7% / 90.5% / 51.3% | 67.1% / Not reported / 37.1% | 66.0% / 88.3% / Not reported |

In addition to the model card table, Google reported that Gemini 4 Neon ranked #1 overall on the Artificial Analysis Coding Agent Index (58.6), #1 on Legal Research Bench and Tax Agent Bench, #1 on Andon Labs' Vending-Bench 2 ($16,843 simulated business net worth), and #2 globally (1336 Elo, #2 on steerability) on Arena's Agent Arena Index across more than 4,200 real-world agent sessions.[1] Artificial Analysis also noted on November 18, 2026 that Gemini 4 Neon delivered a slight intelligence gain over Gemini 4 Carbon at an approximately 17% lower cost per task.[9]

## Gemini 4 Neon safety evaluations, limitations, and regional availability

According to the Gemini 4 Neon model card, the model is intended for long-running agent workflows, iterative repository coding and debugging, multimodal knowledge work, and defensive cybersecurity operations including secure code generation, penetration testing, and vulnerability discovery, validation, and patching.[2] Google reported that in internal Google Antigravity testing, Gemini 4 Neon recorded the lowest fabrication rate of any Gemini model tested to date.[1]

In internal automated development safety evaluations comparing Gemini 4 Neon against Gemini 4 Hydrogen, Google DeepMind reported that Gemini 4 Neon performed comparably across text-to-text content safety (0.00 percentage point difference), multilingual safety, and image-to-text safety, with all variations falling within statistical confidence intervals.[2] Refusal tone remained comparable to Gemini 4 Hydrogen while unjustified refusals on benign multimodal prompts decreased.[2]

Documented limitations in the model card include potential hallucinations on open-ended or out-of-cutoff queries, a March 2026 knowledge cutoff, and ongoing frontier safety and jailbreak-resistance mitigations governed under the Gemini 4 Carbon Safety and Security framework.[2] As of 2026-11-23, Google's Available Regions documentation lists more than 215 countries and territories where Google AI Studio and the Gemini Developer API are supported, while users outside those regions are directed to the Gemini Enterprise Agent Platform on Google Cloud.[7]

## Frequently asked questions

### What is Gemini 4 Neon and how does it fit into the Gemini 4 model family?

Gemini 4 Neon (`gemini-4-neon`) is a multimodal reasoning large language model released by Google and Google DeepMind on November 18, 2026. Adapted from the larger flagship model Gemini 4 Carbon, Gemini 4 Neon sits between Gemini 4 Carbon (for maximum long-horizon reasoning) and Gemini 4 Hydrogen (for fast everyday execution), balancing frontier reasoning depth with faster task completion and lower per-task cost. [1][2][3]

### What are Gemini 4 Neon's context window, supported modalities, and knowledge cutoff?

Gemini 4 Neon accepts text, images, audio, video, and PDF files within a unified 1,000,000-token input-output context window and produces text outputs of up to 64,000 tokens synchronously or up to 1,000,000 tokens via background long decode. According to the Google DeepMind model card published on November 18, 2026, the model's knowledge cutoff is March 2026. [2][3][4]

### How much does Gemini 4 Neon cost in the Gemini API and Google Cloud?

As of 2026-11-23, standard pricing on the Gemini Developer API (Paid tier; not available on the Free tier) and Google Cloud Model Garden global endpoints is $3.00 per million input tokens, $0.15 per million cached input tokens (a 95% discount), and $15.00 per million output tokens (including thinking tokens). On Google Cloud Model Garden, Priority global pricing is $5.40 input, $0.27 cache read, and $27.00 output per million tokens, while Batch global pricing is $1.50 input, $0.075 cache read, and $7.50 output per million tokens, and non-global regional endpoints carry a 10% premium. [1][4][5]

### Which Google subscriptions and developer platforms include Gemini 4 Neon?

As of 2026-11-23, Gemini 4 Neon is available to developers on paid tiers of the Gemini API in Google AI Studio and on Google Cloud through Gemini for business and Model Garden. For consumer and prosumer subscribers, Gemini 4 Neon is included in the Google AI Pro plan (5 TB storage) and the Google AI Ultra plan (starting at 20 TB storage, which provides 5x higher Gemini usage limits than AI Pro) for use in the Gemini app, Google Antigravity, and Google AI Studio. [1][2][4][8]

### How does Gemini 4 Neon perform on coding, science, and enterprise benchmarks?

In Google DeepMind's November 18, 2026 release announcement and model card, Gemini 4 Neon scored 61 on the Artificial Analysis Intelligence Index v5.0.1 (#3 overall at xhigh thinking), 58.6 (#1 overall) on the Artificial Analysis Coding Agent Index, 70.9% (#2 overall) on Vals Index v2.2, 56.3% (#1 overall) on Zapier's AutomationBench, $16,843 (#1 overall) on Andon Labs' Vending-Bench 2, 84.0% on RiemannBench, 70.5% on Terminal-Bench-Science 0.1, 71.3% on HLE-Diamond, 95.2% on GraphWalks (256K-1M BFS), and 39.0% on SWE-sweep inside the Google Antigravity provider harness. [1][2]

## Quotable sentences

- Google DeepMind released Gemini 4 Neon on November 18, 2026, as a mid-tier multimodal reasoning model adapted from Gemini 4 Carbon. [1][2]
- Gemini 4 Neon (API model code gemini-4-neon) accepts text, image, audio, video, and PDF inputs across a unified 1,000,000-token context window, supporting up to 64,000 default synchronous output tokens and up to 1,000,000 output tokens via background long decode. [2][3]
- As of 2026-11-23, standard pricing for Gemini 4 Neon on the Gemini Developer API and Google Cloud Model Garden (global endpoint) is $3.00 per million input tokens, $0.15 per million cached input tokens, and $15.00 per million output tokens (including thinking tokens). [1][4][5]
- As of 2026-11-23, Google Cloud Model Garden prices Gemini 4 Neon at $5.40 input / $0.27 cache read / $27.00 output per million tokens for Priority global inference and $1.50 input / $0.075 cache read / $7.50 output per million tokens for Batch global inference, with a 10% premium on non-global regional endpoints. [5]
- The Google DeepMind model card for Gemini 4 Neon states a knowledge cutoff of March 2026. [2]
- On the November 2026 benchmark evaluations reported by Google DeepMind, Gemini 4 Neon scored 61 on the Artificial Analysis Intelligence Index v5.0.1, 58.6 (#1 overall) on the Artificial Analysis Coding Agent Index, 70.9% on Vals Index v2.2, 56.3% on AutomationBench, 84.0% on RiemannBench, and 39.0% on SWE-sweep in the Google Antigravity harness. [1][2]
- As of 2026-11-23, Gemini 4 Neon is distributed through the Gemini API in Google AI Studio (Paid tiers only), Google Cloud Model Garden / Gemini for business, and to Google AI Pro and Google AI Ultra subscribers in the Gemini app and Google Antigravity. [1][2][8]

## Timeline

- 2026-03: Knowledge cutoff date documented in the Google DeepMind model card for Gemini 4 Neon. [2]
- 2026-11-18: Google DeepMind releases Gemini 4 Neon (gemini-4-neon) across the Gemini app, Gemini API, Google AI Studio, Gemini for business, and Google Antigravity, and publishes the Gemini 4 Neon Model Card. [1][2][9]
- 2027-01-12: Scheduled effective date for Google Cloud Model Garden cache write billing ($3.75/1M standard global, $6.75/1M priority global, $1.875/1M batch global) on Gemini 4 Neon. [5]

## Sources

1. Introducing Gemini 4 Neon. Google (The Keyword). published 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (checked 2026-11-23; tier 3: official site)
2. Gemini 4 Neon - Model Card - Google DeepMind. Google DeepMind. published 2026-11-18. https://deepmind.google/models/model-cards/gemini-4-neon/ (checked 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/models?auto_signin=false (checked 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/pricing?auto_signin=false (checked 2026-11-23; tier 3: official site)
5. Agent Platform Pricing | Google Cloud. Google Cloud. https://cloud.google.com/model-garden/pricing (checked 2026-11-23; tier 3: official site)
6. Rate limits - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/rate-limits?auto_signin=false (checked 2026-11-23; tier 3: official site)
7. Available regions for Google AI Studio and Gemini API - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/available-regions?auto_signin=false (checked 2026-11-23; tier 3: official site)
8. Google AI plans with Cloud Storage - Google One. Google One. https://one.google.com/about/google-ai-plans/ (checked 2026-11-23; tier 3: official site)
9. Google continues to accelerate its release cadence with Gemini 4 Neon | Artificial Analysis. Artificial Analysis. published 2026-11-18. https://artificialanalysis.ai/articles/gemini-4-neon-intelligence-gain (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "Gemini 4 Neon." Version 7f5ff5cb, 2026-11-23. https://mimirwiki.com/wiki/gemini-4-neon
