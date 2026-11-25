---
title: "DeepSeek"
subtitle: "Chinese artificial intelligence research laboratory developing the DeepSeek-V4, DeepSeek-R1, and DeepSeek-V3 foundation models"
canonical_url: https://mimirwiki.com/wiki/deepseek
language: en
page_class: entity
revision_sha256: a200fa1bbbef6750765677b50f4d380083fc5e29ba4edd1be4e5358cea1d78de
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/deepseek.md
  txt: https://mimirwiki.com/wiki/deepseek.txt
  json: https://mimirwiki.com/wiki/deepseek.json
  jsonld: https://mimirwiki.com/wiki/deepseek.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/deepseek
  ja: https://mimirwiki.com/ja/wiki/deepseek
  zh: https://mimirwiki.com/zh/wiki/deepseek
  es: https://mimirwiki.com/es/wiki/deepseek
---

# DeepSeek

> As of November 2026, DeepSeek's API lists two models with a 1M context length and a maximum output of 384K: deepseek-flash (DeepSeek-V4.1-Flash-1017) and deepseek-v4-pro (DeepSeek-V4-Pro-0813). Off-peak prices are half of peak prices, and Search, Fetch, OCR and speech APIs are offered separately. Since 12:00 Beijing Time on November 18, 2026, server-side search and web fetch tool calls made while calling a model are no longer billed. Earlier models include DeepSeek-V3 (671B total / 37B activated parameters) and the DeepSeek-R1 reasoning model.

DeepSeek is a Chinese artificial intelligence company whose services are provided by Hangzhou DeepSeek Artificial Intelligence Co., Ltd., a company with its registered address in China. It develops large language models built on Multi-head Latent Attention (MLA) and DeepSeekMoE architectures, including DeepSeek-V2, DeepSeek-V3, the reinforcement-learning reasoning model DeepSeek-R1, and the DeepSeek-V4 series served through its API.

**Also known as:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd., 深度求索

## Key facts

- **Legal Entities:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Current Production Models:** deepseek-flash (DeepSeek-V4.1-Flash-1017) & deepseek-v4-pro (DeepSeek-V4-Pro-0813) (as of 2026-11-25) [1]
- **Context & Max Output:** 1M token context window; up to 384K maximum output tokens (as of 2026-11-25) [1]
- **Open-Weight Reasoning Milestone:** DeepSeek-R1 (MIT License, January 2025) & DeepSeek-V3 (671B/37B MoE, December 2024) [4]

## Basic facts

- **Official Name:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Registered Address:** China [7]
- **Core Architectures:** Multi-head Latent Attention (MLA), DeepSeekMoE, Multi-Token Prediction (MTP) [5]
- **Flagship API Models (Nov 2026):** DeepSeek-V4.1-Flash-1017 (deepseek-flash), DeepSeek-V4-Pro-0813 (deepseek-v4-pro) [1]
- **API Context & Output:** 1M context length / 384K maximum output [1]
- **API Concurrency Limits:** 2,500 concurrent requests (deepseek-flash); 500 concurrent requests (deepseek-v4-pro) [2]
- **Multimodal & Tool APIs:** Search API, Fetch API, file parsing and OCR API, Speech to Text (ASR), Text to Speech (TTS) [1]
- **Open-Source License (R1):** MIT License (weights and code for DeepSeek-R1 and distilled models) [4]

## Company Overview and Architectural Foundations

DeepSeek's services are provided by Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]. The company has published technical reports on its model architectures and has released Mixture-of-Experts (MoE) and reasoning models [4][5][6].

DeepSeek's models use two architectures introduced in **DeepSeek-V2** (May 2024, 236B total parameters with 21B activated per token) and adopted in **DeepSeek-V3** (December 2024, 671B total parameters with 37B activated per token) [5][6]: - **Multi-head Latent Attention (MLA)**: Compresses the Key-Value (KV) cache into a latent vector to make inference efficient [5][6]. - **DeepSeekMoE**: Uses sparse computation with routed and shared experts. DeepSeek-V3 adds an auxiliary-loss-free strategy for load balancing and a Multi-Token Prediction (MTP) training objective [5][6]. DeepSeek-V3 was pre-trained on 14.8 trillion tokens with FP8 mixed-precision training, and its technical report states that the full training required 2.788M H800 GPU hours [5].

## DeepSeek-R1 and Reinforcement Learning for Reasoning

The DeepSeek-R1 paper, submitted to arXiv on January 22, 2025, describes **DeepSeek-R1** and **DeepSeek-R1-Zero** and reports that reasoning abilities of large language models can be incentivized through pure reinforcement learning (RL), without human-labeled reasoning trajectories, and that behaviors such as self-reflection and verification emerged during training [4].

`DeepSeek-R1-Zero` was trained with Group Relative Policy Optimization (GRPO) without a supervised fine-tuning phase before RL. Because it showed poor readability and language mixing, `DeepSeek-R1` used a multi-stage pipeline with cold-start chain-of-thought data, rejection sampling, RL and supervised fine-tuning [4]. The paper reports performance on par with OpenAI-o1-1217 on math tasks, and that OpenAI-o1-1217 outperforms DeepSeek-R1 on engineering-oriented coding tasks [4]. DeepSeek also made six distilled models publicly available, from 1.5B to 70B parameters, based on Qwen and Llama models [4].

## DeepSeek-V4 Series, Pricing, and Developer Platform (2026)

DeepSeek's API (`api.deepseek.com`) added DeepSeek-V4-Pro and DeepSeek-V4-Flash on April 24, 2026 [3]. As of November 2026 the pricing page lists two models, each with a **1M context length** and a **maximum output of 384K** [1]:

| Model name | Model version | Input, cache hit (peak / off-peak) | Input, cache miss (peak / off-peak) | Output (peak / off-peak) | Concurrency limit |
| --- | --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` | $0.006 / $0.003 | $0.30 / $0.15 | $1.20 / $0.60 | 2,500 |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` | $0.044 / $0.022 | $1.32 / $0.66 | $3.96 / $1.98 | 500 |

Prices are per 1M tokens [1][2]. Off-peak rates are half of peak rates. Peak hours are 01:00-04:00 and 06:00-10:00 UTC, Monday through Friday, excluding Chinese public holidays [1]. Both models support thinking and non-thinking modes, JSON output, tool calls, the Responses API and an Anthropic-format API. Vision is supported on `deepseek-flash` and not on `deepseek-v4-pro` [1]. The legacy model names `deepseek-v4-flash` and `deepseek-v4-flash-vision-exp` are served by DeepSeek-V4.1-Flash-1017 [1].

According to the change log, the GA release of DeepSeek-V4-Pro was rolled out on August 13, 2026, DeepSeek-V4.1-Flash was released on September 10, 2026, and it was upgraded to DeepSeek-V4.1-Flash-1017 on October 17, 2026 [3].

## Built-in Web Search, Utility APIs, and Rate Governance

On November 13, 2026, DeepSeek opened web search, file input, URL reading and model safety features to developers for the `deepseek-flash` model in its Messages, Responses and Chat Completions APIs, and offered Search and Fetch, OCR, ASR and TTS as standalone APIs [3]. The pricing page lists these prices [1]: - **Search API (text)**: $0.75 per 1,000 successful requests [1]. - **Fetch API**: $0.75 per 1,000 successful requests [1]. - **File parsing and OCR API**: $0.225 per 1,000 pages [1]. - **Speech to Text (ASR)**: list price $0.116 per hour of audio, limited-time price $0.058 [1]. - **Text to Speech (TTS)**: list price $0.45 per 10,000 characters, limited-time price $0.225 [1].

Starting 12:00 on November 18, 2026 (Beijing Time, UTC+8), server-side search and web fetch tool calls triggered when calling a model are no longer billed. The results they return are added to the model context and billed as model token usage [1].

Concurrency limits are calculated at the account level: 2,500 for `deepseek-flash` and 500 for `deepseek-v4-pro`. Requests above the limit receive an HTTP 429 error code [2]. Developers can pass a `user_id` parameter, which DeepSeek uses for content safety isolation, KVCache isolation and scheduling isolation. For regular API users, all `user_id` values are combined for the concurrency limit. For accounts with increased concurrency quotas, each `user_id` is also limited to 2,500 for `deepseek-flash` and 500 for `deepseek-v4-pro` [2].

## Data Governance and Privacy Policy

According to DeepSeek's Privacy Policy (last updated February 10, 2026), the services are provided and controlled by Hangzhou DeepSeek Artificial Intelligence Co., Ltd., with its registered address in China [7]. The policy states that DeepSeek collects, processes and stores personal data in the **People's Republic of China** [7]. It lists a right to opt out of the use of personal data for training its models or optimizing its technologies [7]. The policy does not cover personal data collected from end users of applications that developers build on DeepSeek's open platform; it says the developer operating the application is the controller of that data [7]. DeepSeek has also made distilled DeepSeek-R1 models publicly available [4].

## Frequently asked questions

### What are DeepSeek's main API models as of November 2026?

DeepSeek's API lists two models: deepseek-flash (model version DeepSeek-V4.1-Flash-1017) and deepseek-v4-pro (model version DeepSeek-V4-Pro-0813). Both have a 1M context length and a maximum output of 384K. [1][3]

### How does DeepSeek's peak and off-peak API pricing work?

Off-peak rates are half of peak rates. Peak hours are 01:00-04:00 and 06:00-10:00 UTC, Monday through Friday, excluding Chinese public holidays; all other hours are off-peak. For example, deepseek-flash cache-miss input costs $0.30 per 1M tokens at peak and $0.15 off-peak, and output costs $1.20 at peak and $0.60 off-peak. [1]

### How do DeepSeek's API rate limits and user_id concurrency controls work?

Concurrency limits are calculated at the account level: 2,500 for deepseek-flash and 500 for deepseek-v4-pro. Requests above the limit receive an HTTP 429 error code. For regular API users, all user_id values are combined for the limit. For accounts with increased concurrency quotas, each user_id is also limited to 2,500 for deepseek-flash and 500 for deepseek-v4-pro. [2]

### What architectural innovations made DeepSeek-V3 and DeepSeek-R1 notable?

DeepSeek-V3 (671B total parameters, 37B active per token) combined Multi-head Latent Attention (MLA) for low-memory KV caching with an auxiliary-loss-free DeepSeekMoE router and FP8 training. DeepSeek-R1 then applied large-scale pure reinforcement learning (GRPO) and multi-stage cold-start training to achieve frontier reasoning performance under an open MIT License. [4][5]

### Where does DeepSeek store data sent to its hosted web app and API?

DeepSeek's Privacy Policy states that it collects, processes and stores personal data in the People's Republic of China, and that the services are provided and controlled by Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. The policy does not cover end users of applications that developers build on DeepSeek's open platform. [4][7]

## Quotable sentences

- DeepSeek's production API endpoints deepseek-flash (DeepSeek-V4.1-Flash-1017) and deepseek-v4-pro (DeepSeek-V4-Pro-0813) both support a 1M token context window and up to 384K output tokens. [1][3]
- DeepSeek's off-peak API rates are half of its peak rates; peak hours are 01:00-04:00 and 06:00-10:00 UTC, Monday through Friday, excluding Chinese public holidays. [1]
- DeepSeek's account-level API concurrency limits are 2,500 for deepseek-flash and 500 for deepseek-v4-pro; for accounts with increased quotas, the same limits also apply to each user_id. [2]
- Since 12:00 on November 18, 2026 (Beijing Time), server-side search and web fetch tool calls triggered when calling a DeepSeek model are no longer billed; the returned results are billed as model token usage. [1]
- DeepSeek-V3 is a 671B-parameter Mixture-of-Experts model with 37B active parameters per token trained on 14.8T tokens, and DeepSeek-R1 was released under the MIT License in January 2025. [4][5]

## Timeline

- 2024-05: DeepSeek publishes the DeepSeek-V2 technical report introducing Multi-head Latent Attention (MLA) and a 236B/21B MoE architecture. [6]
- 2024-12: DeepSeek releases DeepSeek-V3, a 671B-parameter (37B active) Mixture-of-Experts model pre-trained on 14.8 trillion tokens with FP8 precision. [5]
- 2025-01: DeepSeek releases DeepSeek-R1, DeepSeek-R1-Zero, and six distilled reasoning models under the open-source MIT License. [4]
- 2026-08-13: The GA release of DeepSeek-V4-Pro is rolled out on the app, web and API under the model name deepseek-v4-pro. [1][3]
- 2026-10-17: DeepSeek V4.1 Flash is upgraded to DeepSeek-V4.1-Flash-1017, served under the model name deepseek-flash. [1][3]
- 2026-11-18: From 12:00 Beijing Time, server-side search and web fetch tool calls triggered when calling a model are no longer billed. [1]

## Sources

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (checked 2026-11-25; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (checked 2026-11-25; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. published 2026-11-13. https://api-docs.deepseek.com/updates (checked 2026-11-25; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. published 2025-01-22. https://arxiv.org/abs/2501.12948 (checked 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. published 2024-12-27. https://arxiv.org/abs/2412.19437 (checked 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. published 2024-05-07. https://arxiv.org/abs/2405.04434 (checked 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (checked 2026-11-25; tier 3: official site)

## Cite this page

Mimirwiki. "DeepSeek." Version a200fa1b, 2026-11-25. https://mimirwiki.com/wiki/deepseek
