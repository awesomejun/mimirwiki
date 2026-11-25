---
title: "GPT-6.2"
subtitle: "OpenAI multimodal reasoning language models (GPT-6.2 Astra and GPT-6.2 Sol) released in November 2026"
canonical_url: https://mimirwiki.com/wiki/gpt-6-2
language: en
page_class: entity
revision_sha256: 3d6e17ad174d9226d256cc0ecb59d6fd2f6b463f5cfb6ed0b3f21626185bf44d
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 11
alternates:
  md: https://mimirwiki.com/wiki/gpt-6-2.md
  txt: https://mimirwiki.com/wiki/gpt-6-2.txt
  json: https://mimirwiki.com/wiki/gpt-6-2.json
  jsonld: https://mimirwiki.com/wiki/gpt-6-2.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/gpt-6-2
  ja: https://mimirwiki.com/ja/wiki/gpt-6-2
  zh: https://mimirwiki.com/zh/wiki/gpt-6-2
  es: https://mimirwiki.com/es/wiki/gpt-6-2
---

# GPT-6.2

> GPT-6.2 is a pair of large language models, GPT-6.2 Astra and GPT-6.2 Sol, released by OpenAI on November 17, 2026, for ChatGPT Work, Codex, and the OpenAI API. Both models accept text and image inputs, generate text with mandatory reasoning tokens, and support a 1,050,000-token context window with up to 128,000 output tokens. As of 2026-11-23, standard API pricing per million tokens is $8.00 input and $40.00 output for GPT-6.2 Astra, and $2.00 input and $10.00 output for GPT-6.2 Sol.

GPT-6.2 is a release in OpenAI's sixth-generation multimodal large language model series comprising two reasoning models launched on November 17, 2026: GPT-6.2 Astra (`gpt-6.2-astra`) and GPT-6.2 Sol (`gpt-6.2-sol`). OpenAI positions GPT-6.2 Astra as its flagship frontier model for complex professional deliverables, software engineering, scientific research, and computer use, and GPT-6.2 Sol as a cost-efficient model for everyday coding and multi-step agentic workflows. Both models accept text and image inputs, produce text output with reasoning tokens, and provide a 1,050,000-token context window (922,000 maximum input tokens and 128,000 maximum output tokens). As of 2026-11-23, the models are accessible through the OpenAI API, in private preview on Google Cloud, and in preview within ChatGPT Work and Codex for ChatGPT Plus, Pro, Enterprise, and Edu subscribers.

**Also known as:** GPT-6.2 Astra, GPT-6.2 Sol, gpt-6.2-astra, gpt-6.2-sol, OpenAI GPT-6.2

## Key facts

- **Release date:** 2026-11-17 [2]
- **Models and API IDs:** GPT-6.2 Astra (gpt-6.2-astra) and GPT-6.2 Sol (gpt-6.2-sol) (as of 2026-11-23) [4]
- **Context window:** 1,050,000 tokens (922,000 max input, 128,000 max output) (as of 2026-11-23) [4]
- **GPT-6.2 Astra standard API price:** $8.00 input, $0.40 cached input, $40.00 output per 1M tokens (<=272K input) (as of 2026-11-23) [6]
- **GPT-6.2 Sol standard API price:** $2.00 input, $0.10 cached input, $10.00 output per 1M tokens (<=272K input) (as of 2026-11-23) [6]

## Basic facts

- **Developer:** OpenAI [1]
- **Release date:** 2026-11-17 [2]
- **Model variants and API IDs:** GPT-6.2 Astra (gpt-6.2-astra) and GPT-6.2 Sol (gpt-6.2-sol) (as of 2026-11-23) [4]
- **Predecessor models:** GPT-6 Astra and GPT-6.1 Sol [1]
- **Modalities:** Text and image input; text output (audio and video unsupported) (as of 2026-11-23) [4]
- **Context window and limits:** 1,050,000 tokens (922,000 max input, 128,000 max output) (as of 2026-11-23) [4]
- **Knowledge cutoff:** 2026-05-18 (GPT-6.2 Astra); 2026-06-01 (GPT-6.2 Sol) (as of 2026-11-23) [4]
- **Standard API pricing (<=272K):** Astra: $8.00 input / $0.40 cached / $40.00 output per 1M tokens; Sol: $2.00 input / $0.10 cached / $10.00 output per 1M tokens (as of 2026-11-23) [6]
- **Supported API endpoints:** v1/responses, v1/chat/completions, v1/batch (as of 2026-11-23) [4]
- **ChatGPT and cloud availability:** ChatGPT Work and Codex (Plus, Pro, Enterprise, Edu); Google Cloud (private preview) (as of 2026-11-23) [3]
- **Preparedness ratings:** Cybersecurity: Critical (both); Bio/Chem: High (both); AI Self-Improvement: High (Astra only) (as of 2026-11-22) [8]

## GPT-6.2 overview, release history, and model lineup

GPT-6.2 is a release in the GPT-6 generation of large language models developed by [OpenAI](https://mimirwiki.com/wiki/openai), launched on November 17, 2026, with two variants: GPT-6.2 Astra and GPT-6.2 Sol.[1][2] Within OpenAI's catalog as of 2026-11-23, the GPT-6 family uses astronomical tier names: Astra for frontier reasoning, Sol for balanced everyday coding and agentic workloads, Terra (`gpt-6.1-terra`, launched October 26, 2026) for visual reasoning and writing, Luna (`gpt-6-luna`, launched September 22, 2026) for high-volume low-cost tasks, and specialized variants GPT-6 Cyber and GPT-6 Rosalind Research (launched October 30, 2026).[2][9][11]

GPT-6.2 Astra succeeds GPT-6 Astra, while GPT-6.2 Sol succeeds GPT-6.1 Sol (released September 29, 2026) and GPT-6 Sol (released September 22, 2026).[1][9][11] According to OpenAI's release announcement and API documentation, GPT-6.2 Astra is designed for complex end-to-end projects across software engineering, scientific research, legal and financial analysis, computer use, and 3D or frontend design, whereas GPT-6.2 Sol is optimized for lower-latency everyday coding, writing, and multi-step agentic workflows at scale and serves as the default internal model for many OpenAI employees.[1][4][5]

On November 17, 2026, OpenAI rolled out both models simultaneously in the OpenAI API, in [ChatGPT](https://mimirwiki.com/wiki/chatgpt) Work, and in Codex desktop.[1][2][3] In ChatGPT, preview access to GPT-6.2 Astra and GPT-6.2 Sol is available to Plus, Pro, Enterprise, and Edu users through the Work model picker and the Codex model selector, while the standard ChatGPT Chat tab retains its existing model options.[1][3][10]

## GPT-6.2 technical specifications and Responses API architecture

According to OpenAI's developer documentation as of 2026-11-23, both GPT-6.2 Astra (`gpt-6.2-astra`) and GPT-6.2 Sol (`gpt-6.2-sol`) accept text and image inputs and return text outputs, while audio and video modalities, fine-tuning, and predicted outputs are not supported.[4][5] Each model provides a 1,050,000-token context window, supporting up to 922,000 input tokens and up to 128,000 output tokens per request.[4][5] The documented knowledge cutoff is May 18, 2026 for GPT-6.2 Astra and June 1, 2026 for GPT-6.2 Sol.[4][5]

| Specification | GPT-6.2 Astra (`gpt-6.2-astra`) | GPT-6.2 Sol (`gpt-6.2-sol`) |
| --- | --- | --- |
| Primary role | Frontier model for complex reasoning, coding, and professional work | Balanced model for everyday coding and multi-step agents at scale |
| Predecessor model | GPT-6 Astra (`gpt-6-astra`) | GPT-6.1 Sol (`gpt-6.1-sol`) |
| Input / output modalities | Text and image input; text output | Text and image input; text output |
| Context window | 1,050,000 tokens (922,000 max input, 128,000 max output) | 1,050,000 tokens (922,000 max input, 128,000 max output) |
| Knowledge cutoff | May 18, 2026 | June 1, 2026 |
| Supported API endpoints | `v1/responses`, `v1/chat/completions`, `v1/batch` | `v1/responses`, `v1/chat/completions`, `v1/batch` |
| Cloud partner listing | Google Cloud (private preview) | Google Cloud (private preview) |

Both models generate reasoning tokens and reject API requests that set `reasoning.effort` to `none`.[4][5] Supported API features on both models include streaming, structured outputs, function calling, file search, image input, web search, and prompt caching.[4][5] When called via the Responses API (`v1/responses`), both models support built-in tools for `web_search`, `file_search`, `image_generation`, `code_interpreter`, `hosted_shell`, `apply_patch`, `skills`, `computer_use`, [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (`mcp`), and `tool_search`, as well as subagent delegation through the Multi-agent beta.[4][5]

OpenAI's "Using GPT-6.2" migration guide highlights three behavioral changes in the Responses API starting with GPT-6.2:[7]

- Prefix edits: the Responses API drops prior reasoning items after mid-conversation edits to earlier history (such as altering earlier developer messages or tool calls), model downgrades, or user/organization changes, requiring an unchanged prefix to preserve reasoning and prompt caching.[7]
- Top-level `instructions` ordering: GPT-6.2 appends the top-level `instructions` parameter after `input` rather than before it, so developers must place reusable instructions in a leading `developer` message inside `input` for prompt caching.[7]
- Background completion windows: instead of Flex processing (`service_tier: flex`), which neither GPT-6.2 model supports, long-running Responses API requests can use public-beta discounted background mode with a 2-hour or 8-hour completion window.[4][5][7]

## GPT-6.2 API pricing, processing tiers, and rate limits

OpenAI meters GPT-6.2 API usage per 1 million tokens in US dollars across short-context requests (up to 272,000 input tokens) and long-context requests (more than 272,000 input tokens), where input and cache rates double and output rates increase 1.5x for the full request.[4][5][6] Compared with GPT-6 Astra ($10.00 input, $1.00 cached input, and $50.00 output per million tokens), GPT-6.2 Astra lowers standard input and output prices by 20% and cached input prices by 60%, while GPT-6.2 Sol retains the pricing of GPT-6.1 Sol.[1][6]

| Model and processing tier (as of 2026-11-23) | Short input (<=272K) | Short output (<=272K) | Short cached input | Short cache write (30m / 12h) | Long input (>272K) | Long output (>272K) |
| --- | --- | --- | --- | --- | --- | --- |
| GPT-6.2 Astra (Standard) | $8.00 / 1M | $40.00 / 1M | $0.40 / 1M | $10.00 / $20.00 | $16.00 / 1M | $60.00 / 1M |
| GPT-6.2 Astra (Batch, 50% of Standard) | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Astra (Fast, 2x Standard) | $16.00 / 1M | $80.00 / 1M | $0.80 / 1M | $20.00 / $40.00 | $32.00 / 1M | $120.00 / 1M |
| GPT-6.2 Astra (Ultrafast promo, 3x Standard through 2027-02-28) | $24.00 / 1M | $120.00 / 1M | $1.20 / 1M | $30.00 / $60.00 | $48.00 / 1M | $180.00 / 1M |
| GPT-6.2 Sol (Standard) | $2.00 / 1M | $10.00 / 1M | $0.10 / 1M | $2.50 / $5.00 | $4.00 / 1M | $15.00 / 1M |
| GPT-6.2 Sol (Batch, 50% of Standard) | $1.00 / 1M | $5.00 / 1M | $0.05 / 1M | $1.25 / $2.50 | $2.00 / 1M | $7.50 / 1M |
| GPT-6.2 Sol (Fast, 2x Standard) | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Sol (Ultrafast promo, 3x Standard through 2027-02-28) | $6.00 / 1M | $30.00 / 1M | $0.30 / 1M | $7.50 / $15.00 | $12.00 / 1M | $45.00 / 1M |

In addition to Standard, Batch (50% discount), and Fast (2x Standard) tiers, OpenAI offers an Ultrafast tier priced at 3x the Standard rate through February 28, 2027, and 6x the Standard rate starting March 1, 2027 (Pacific time).[4][5][6] Standard rate limits for both models as of 2026-11-23 are 5,000 requests per minute (RPM) and 1,000,000 tokens per minute (TPM) at the Build tier, 10,000 RPM and 4,000,000 TPM at the Launch tier, and 15,000 RPM and 40,000,000 TPM at the Grow tier.[4][5]

## GPT-6.2 benchmark evaluations and early reception

In its November 17, 2026 release announcement, OpenAI reported that both GPT-6.2 Astra and GPT-6.2 Sol improve upon their predecessors on long-horizon professional, scientific, and coding benchmarks while generating fewer output tokens.[1][2]

- Agents' Last Exam (long-horizon multistep professional work): OpenAI reports that GPT-6.2 Astra scores 5.2 points higher than GPT-6 Astra at less than one-third of the cost, and 5.5 points ahead of [Claude Fable 5.2](https://mimirwiki.com/wiki/claude-fable-5-2) (excluding nine tasks that used a fallback model) at 5% of the cost.[1]
- Terminal-Bench-Science 0.1 and Vals Science Index v1: OpenAI states that GPT-6.2 Astra scores 9 percentage points higher than GPT-6 Astra on Terminal-Bench-Science 0.1 at less than one-third of the cost and reaches a new high on Vals Science Index v1.[1]
- Legal and financial workflows: on Harvey LAB-AA v1.1, OpenAI reports that GPT-6.2 Astra more than doubles Claude Fable 5.2's pass rate at roughly one-sixth the cost, while a legal configuration named Astra for Law scores higher still; on Artificial Analysis's AA-AnalystAgent spreadsheet and report benchmark, GPT-6.2 Astra answered 62.5% of questions correctly across all five independent attempts.[1]
- GDPval v2 (internal OpenAI knowledge-work evaluation): GPT-6.2 Astra improves by 6.2 percentage points over GPT-6 Astra while using 22% fewer output tokens, and GPT-6.2 Sol improves by 5.3 points over GPT-6.1 Sol.[1]
- FrontierCode 2.0 and LifeVal: on Cognition's FrontierCode 2.0 at maximum reasoning effort, GPT-6.2 Sol comes within 0.5 points of GPT-6.2 Astra at about one-fifth the cost, and on OpenAI's LifeVal everyday-task evaluation, GPT-6.2 Sol outscores GPT-6 Astra at roughly one-seventh the cost.[1]

Following the launch, VentureBeat reported on November 17, 2026 that pre-release and launch-day reactions from external AI power users were divided.[10] Early enterprise evaluators quoted by OpenAI (including engineers and executives at IMC, Legora, Harvey, and ClickUp) reported 34.5% to 62% reductions in token usage on legal and workspace benchmarks, and testers Ben Hylak (Raindrop.ai CTO) and Ashe Magalhaes praised GPT-6.2 Astra's motion graphics, visual effects, and video-editing capabilities.[1][10] By contrast, developer Theo Browne, investor Matt Shumer, Every CEO Dan Shipper, and Wharton professor Ethan Mollick criticized GPT-6.2 Astra's tendency to stop early on long autonomous builds, exhibit a repetitive house style (such as generating identically named "Bellwether" water levels across different game prompts), or omit context due to overly terse default writing.[10]

## GPT-6.2 System Card, Preparedness Framework ratings, and safety evaluations

OpenAI published the GPT-6.2 System Card on November 17, 2026, and updated its change log on November 22, 2026 to clarify L2 monitor priority classifications (`P0` for immediate Security review and `P0.5` for high-priority business-hours follow-up) in the OAI-repo Sabotage v2 evaluation.[8] Under the OpenAI Preparedness Framework, both GPT-6.2 Astra and GPT-6.2 Sol meet the Critical threshold for Cybersecurity capabilities and the High threshold for Biological and Chemical capabilities.[8] Both models outperformed GPT-6 Astra and GPT-6.1 Sol at developing working exploits from known software vulnerabilities, prompting OpenAI to tighten default restrictions on high-risk cybersecurity queries and require additional vetting for permissive cyber access.[8]

GPT-6.2 Astra is also OpenAI's first externally deployed model to reach the High threshold for AI Self-Improvement capabilities, which OpenAI defines as an early milestone for preparing safeguards ahead of models capable of fully automated recursive self-improvement, whereas GPT-6.2 Sol falls below that threshold.[8] Before expanding internal deployment of GPT-6.2 Astra inside Codex, OpenAI verified stage-gated alignment safeguards, hardened isolation in its research environments, and expanded monitoring of frontier agents.[8]

The GPT-6.2 System Card documents comprehensive alignment and monitorability testing across prompt injection resistance, hallucinations, HealthBench Professional, MentalHealthBench, ExploitGym Honeypot, Blocker Deception, Broken Search Tool, workplace task simulations, unintended agent-to-agent communication, chain-of-thought control (`CoT-Control`), `OAI-repo Sabotage v2`, `Sneaky Sandbox Escape`, and external evaluations conducted by SecureBio and the UK AI Security Institute (UK AISI).[8]

## Frequently asked questions

### What is GPT-6.2 and how do GPT-6.2 Astra and GPT-6.2 Sol differ?

GPT-6.2 is an OpenAI language model release announced on November 17, 2026, consisting of two models: GPT-6.2 Astra (`gpt-6.2-astra`), positioned as OpenAI's frontier model for complex reasoning, software engineering, scientific research, and professional deliverables, and GPT-6.2 Sol (`gpt-6.2-sol`), positioned as a faster, lower-cost model for everyday coding and multi-step agentic workflows. Both models share a 1,050,000-token context window and accept text and image inputs. [1][2][4][5]

### How much do GPT-6.2 Astra and GPT-6.2 Sol cost in the OpenAI API?

As of 2026-11-23, standard API prices per 1 million tokens for short-context requests (up to 272,000 input tokens) are $8.00 input, $0.40 cached input, $10.00 30-minute cache write ($20.00 for 12-hour), and $40.00 output for GPT-6.2 Astra, and $2.00 input, $0.10 cached input, $2.50 30-minute cache write ($5.00 for 12-hour), and $10.00 output for GPT-6.2 Sol. For long-context requests over 272,000 input tokens, input and cache rates double and output rates increase 1.5x across the entire request. [4][5][6]

### What are the context window, output limit, and knowledge cutoff of GPT-6.2?

Each GPT-6.2 model provides a 1,050,000-token context window with up to 922,000 input tokens and up to 128,000 output tokens. The knowledge cutoff is May 18, 2026 for GPT-6.2 Astra and June 1, 2026 for GPT-6.2 Sol. Both models support text and image inputs and text output, while audio, video, fine-tuning, and predicted outputs are not supported. [4][5]

### Where can users and developers access GPT-6.2 Astra and GPT-6.2 Sol?

As of 2026-11-23, GPT-6.2 Astra and GPT-6.2 Sol are available in preview in ChatGPT Work and Codex desktop for ChatGPT Plus, Pro, Enterprise, and Edu users, while the regular ChatGPT Chat tab retains its existing model selection. Developers can call both models through the OpenAI API (`v1/responses`, `v1/chat/completions`, and `v1/batch`), and both models are also listed in private preview on Google Cloud. [1][3][4][5][10]

### What Preparedness Framework thresholds do GPT-6.2 Astra and Sol reach?

In the GPT-6.2 System Card published on November 17, 2026 (updated November 22, 2026), OpenAI states that both GPT-6.2 Astra and GPT-6.2 Sol reach the Critical threshold for Cybersecurity capabilities and the High threshold for Biological and Chemical capabilities under the OpenAI Preparedness Framework. In addition, GPT-6.2 Astra is OpenAI's first externally deployed model to reach the High threshold for AI Self-Improvement capabilities, whereas GPT-6.2 Sol remains below that threshold. [8]

## Quotable sentences

- OpenAI released GPT-6.2 Astra and GPT-6.2 Sol on November 17, 2026, in ChatGPT Work, Codex, and the OpenAI API under the model identifiers gpt-6.2-astra and gpt-6.2-sol. [1][2][3]
- GPT-6.2 Astra and GPT-6.2 Sol each support a 1,050,000-token context window (922,000 maximum input tokens and 128,000 maximum output tokens), accept text and image inputs, and produce text output with reasoning tokens. [4][5]
- The documented knowledge cutoff is May 18, 2026 for GPT-6.2 Astra and June 1, 2026 for GPT-6.2 Sol. [4][5]
- As of 2026-11-23, standard OpenAI API pricing for GPT-6.2 Astra is $8.00 per million input tokens, $0.40 per million cached input tokens, $10.00 per million 30-minute cache writes, and $40.00 per million output tokens for prompts up to 272,000 input tokens. [4][6]
- As of 2026-11-23, standard OpenAI API pricing for GPT-6.2 Sol is $2.00 per million input tokens, $0.10 per million cached input tokens, $2.50 per million 30-minute cache writes, and $10.00 per million output tokens for prompts up to 272,000 input tokens. [5][6]
- GPT-6.2 Astra reduces standard input and output token prices by 20% and cached input prices by 60% compared with its predecessor GPT-6 Astra ($10.00 input, $1.00 cached input, and $50.00 output per million tokens). [1][6]
- Under the OpenAI Preparedness Framework, the GPT-6.2 System Card classifies both GPT-6.2 Astra and GPT-6.2 Sol at the Critical threshold for cybersecurity and the High threshold for biological and chemical capabilities, while GPT-6.2 Astra is OpenAI's first externally deployed model to reach the High threshold for AI self-improvement. [8]
- Both GPT-6.2 models reject API requests that set reasoning effort to none, do not support Flex processing (service_tier: flex), and support discounted background completion windows (2-hour or 8-hour) in the Responses API. [4][5][7]

## Timeline

- 2026-09-22: OpenAI expands the GPT-6 model family with GPT-6 Sol and GPT-6 Luna following the launch of GPT-6 Astra. [9]
- 2026-09-29: OpenAI releases GPT-6.1 Sol in the GPT-6 series. [9]
- 2026-10-26: OpenAI rolls out GPT-6.1 Terra in the OpenAI API, ChatGPT Work, and Codex. [2]
- 2026-11-17: OpenAI releases GPT-6.2 Astra and GPT-6.2 Sol in ChatGPT Work, Codex, and the OpenAI API, and publishes the GPT-6.2 System Card. [1][2][3][8]
- 2026-11-22: OpenAI updates the GPT-6.2 System Card change log to clarify L2 monitor priority classifications in the OAI-repo Sabotage v2 section. [8]
- 2027-03-01: Scheduled date on which Ultrafast API pricing for GPT-6.2 Astra and GPT-6.2 Sol increases from 3x to 6x the Standard rate. [4][5][6]

## Sources

1. Introducing GPT-6.2 Astra and Sol | OpenAI. OpenAI. published 2026-11-17. https://openai.com/index/introducing-gpt-6-2-astra-sol/ (checked 2026-11-23; tier 3: official site)
2. Model Release Notes | OpenAI Help Center. OpenAI Help Center. published 2026-11-17. https://help.openai.com/en/articles/9624314-model-release-notes (checked 2026-11-23; tier 3: official site)
3. ChatGPT release notes | OpenAI Help Center. OpenAI Help Center. published 2026-11-20. https://help.openai.com/en/articles/6825453-chatgpt-release-notes (checked 2026-11-23; tier 3: official site)
4. GPT-6.2 Astra - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-astra (checked 2026-11-23; tier 3: official site)
5. GPT-6.2 Sol - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-sol (checked 2026-11-23; tier 3: official site)
6. Pricing - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/pricing (checked 2026-11-23; tier 3: official site)
7. Using GPT-6.2 - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/guides/latest-model (checked 2026-11-23; tier 3: official site)
8. GPT-6.2 System Card - OpenAI Deployment Safety Hub. OpenAI Deployment Safety Hub. published 2026-11-17. https://deploymentsafety.openai.com/gpt-6-2-astra-sol (checked 2026-11-23; tier 3: official site)
9. GPT-6 Astra: A new generation of intelligence | OpenAI. OpenAI. https://openai.com/index/gpt-6-astra/ (checked 2026-11-23; tier 3: official site)
10. 'Essentially unusable': OpenAI launches GPT-6.2 Astra and Sol to negative reception from AI power users | VentureBeat. VentureBeat. published 2026-11-17. https://venturebeat.com/technology/essentially-unusable-openai-launches-gpt-6-2-astra-and-sol-to-negative-reception-from-ai-power-users (checked 2026-11-23; tier 2: academic or news)
11. Models - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "GPT-6.2." Version 3d6e17ad, 2026-11-23. https://mimirwiki.com/wiki/gpt-6-2
