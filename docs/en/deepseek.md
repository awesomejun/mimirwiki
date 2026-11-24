---
title: "DeepSeek"
subtitle: "Chinese artificial intelligence research laboratory developing the DeepSeek-V4, DeepSeek-R1, and DeepSeek-V3 foundation models"
canonical_url: https://mimirwiki.com/wiki/deepseek
language: en
page_class: entity
revision_sha256: 633a03f867c266346c37126164846c3a1efca264cad0698fd543b568b1ae8cfe
date_modified: 2026-11-23
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
---

# DeepSeek

> As of November 2026, DeepSeek's developer platform serves two primary 1-million-token context models: deepseek-flash (DeepSeek-V4.1-Flash-1017) and deepseek-v4-pro (DeepSeek-V4-Pro-0813), both supporting up to 384K output tokens alongside dynamic peak/off-peak pricing, native Search/Fetch/OCR/Speech APIs, and free built-in server-side web search (enabled November 18, 2026). Earlier open-weight milestones include DeepSeek-V3 (671B total / 37B active parameters) and the MIT-licensed DeepSeek-R1 reasoning family.

DeepSeek (officially Hangzhou DeepSeek Artificial Intelligence Co., Ltd. and Beijing DeepSeek Artificial Intelligence Co., Ltd.) is a Chinese artificial intelligence research company founded in 2023 and headquartered in Hangzhou, Zhejiang. It develops open-weight and API-hosted large language models utilizing Multi-head Latent Attention (MLA) and DeepSeekMoE architectures, including DeepSeek-V2, DeepSeek-V3, the reinforcement-learning reasoning model DeepSeek-R1, and the multimodal DeepSeek-V4 series.

**Also known as:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd., Beijing DeepSeek Artificial Intelligence Co., Ltd., 深度求索

## Key facts

- **Legal Entities:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. / Beijing DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Current Production Models:** deepseek-flash (DeepSeek-V4.1-Flash-1017) & deepseek-v4-pro (DeepSeek-V4-Pro-0813) (as of 2026-11-23) [1]
- **Context & Max Output:** 1M token context window; up to 384K maximum output tokens (as of 2026-11-23) [1]
- **Open-Weight Reasoning Milestone:** DeepSeek-R1 (MIT License, January 2025) & DeepSeek-V3 (671B/37B MoE, December 2024) [4]

## Basic facts

- **Official Name:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Headquarters:** Hangzhou, Zhejiang, China [7]
- **Core Architectures:** Multi-head Latent Attention (MLA), DeepSeekMoE, Multi-Token Prediction (MTP) [5]
- **Flagship API Models (Nov 2026):** DeepSeek-V4.1-Flash-1017 (deepseek-flash), DeepSeek-V4-Pro-0813 (deepseek-v4-pro) [1]
- **API Context & Output:** 1,000,000 context tokens / 384,000 max output tokens (64K default) [1]
- **API Concurrency Limits:** 2,500 concurrent requests (deepseek-flash); 500 concurrent requests (deepseek-v4-pro) [2]
- **Multimodal & Tool APIs:** Search API, Fetch API, OCR API, Speech-to-Text API, server-side search_Option [1]
- **Open-Source License (R1):** MIT License (weights and code for DeepSeek-R1 and distilled models) [4]

## Company Overview and Architectural Foundations

DeepSeek operates through Hangzhou DeepSeek Artificial Intelligence Co., Ltd. and Beijing DeepSeek Artificial Intelligence Co., Ltd., building frontier foundation models and developer APIs [1][7]. The laboratory gained global recognition across 2024 and 2025 by publishing detailed architectural technical reports and releasing open-weight Mixture-of-Experts (MoE) and reasoning models trained at a fraction of typical frontier compute budgets [4][5][6].

DeepSeek's foundation models are built on two core structural innovations introduced in **DeepSeek-V2** (May 2024, 236B total parameters with 21B active per token) and scaled in **DeepSeek-V3** (December 2024, 671B total parameters with 37B active per token) [5][6]: - **Multi-head Latent Attention (MLA)**: Compresses Key-Value (KV) cache representations into a low-rank latent vector during inference, dramatically reducing memory bandwidth overhead on long-context sequences [5][6]. - **DeepSeekMoE with Auxiliary-Loss-Free Load Balancing**: Uses fine-grained routed experts alongside shared experts, replacing performance-degrading auxiliary load-balancing losses with a dynamic bias-adjustment routing strategy and a Multi-Token Prediction (MTP) training objective [5]. DeepSeek-V3 was pre-trained on 14.8 trillion tokens using FP8 mixed-precision training across only 2.788 million H800 GPU hours [5].

## DeepSeek-R1 and Reinforcement Learning for Reasoning

In January 2025, DeepSeek released **DeepSeek-R1** and **DeepSeek-R1-Zero** under the permissive MIT License, demonstrating that large-scale pure reinforcement learning (RL) without prior supervised fine-tuning (SFT) can induce self-verification, reflection, and extended chain-of-thought (CoT) reasoning in language models [4].

While `DeepSeek-R1-Zero` applied Group Relative Policy Optimization (GRPO) directly to the base model, `DeepSeek-R1` incorporated multi-stage training with cold-start CoT data and rejection sampling to eliminate language mixing and improve readability, matching OpenAI-o1-1217 performance across mathematics, code competition, and STEM reasoning benchmarks [4]. DeepSeek also released six dense distilled models ranging from 1.5B to 70B parameters (based on Qwen and Llama architectures) distilled from DeepSeek-R1 outputs [4].

## DeepSeek-V4 Series, Pricing, and Developer Platform (2026)

By late 2026, DeepSeek transitioned its production API platform (`api.deepseek.com`) to the multimodal **DeepSeek-V4** architecture, consolidating chat, reasoning (`thinking`), vision, and audio input into two primary model endpoints with a **1,000,000-token context window** and up to **384,000 maximum output tokens** (64K default) [1]:

| API Model Alias | Underlying Model Version | Peak Pricing (08:00-24:00 UTC+8) | Off-Peak Pricing (00:00-08:00 UTC+8) | Concurrency Limit |
| --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` (released Oct 20, 2026) | $0.03/M input (cache hit), $0.30/M input (miss, <=256K), $0.50/M (>256K); $1.50-$2.50/M output | $0.03/M (cache hit), $0.15/M (<=256K), $0.25/M (>256K); $0.75-$1.25/M output | 2,500 concurrent requests [1][2] |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` (released Aug 19, 2026) | $0.20/M input (cache hit), $2.00/M input (miss, <=256K), $4.00/M (>256K); $12.00-$18.00/M output | $0.20/M (cache hit), $1.00/M (<=256K), $2.00/M (>256K); $6.00-$9.00/M output | 500 concurrent requests [1][2] |

Both models accept text, image, and audio inputs and output text, JSON mode, function tool calls, and Reasoning Content [1]. When audio tokens are submitted, audio input is billed at higher per-million rates ($1.00-$4.00/M for `deepseek-flash` and $7.00-$28.00/M for `deepseek-v4-pro` depending on context bracket and cache status) [1]. Legacy aliases such as `deepseek-chat` and `deepseek-reasoner` automatically map to the V4 series endpoints [1].

## Built-in Web Search, Utility APIs, and Rate Governance

On November 18, 2026, DeepSeek upgraded its chat completions endpoint to support native server-side web search and page fetching via the `search_Option` parameter, providing built-in search execution free of extra per-query search charges during the promotional rollout [1][3]. For standalone programmatic pipelines, DeepSeek also exposes dedicated utility endpoints [1]: - **Search API**: $5.00 per 1,000 queries [1]. - **Fetch API**: $1.00 per 1,000 URL fetches [1]. - **OCR API**: $1.00 per 1,000 document pages [1]. - **Speech-to-Text API**: $0.10 per hour of audio transcription [1].

Unlike providers that enforce strict Tokens-Per-Minute (TPM) or Requests-Per-Minute (RPM) ceilings by spend tier, DeepSeek governs throughput primarily by active in-flight concurrency (2,500 concurrent requests for `deepseek-flash` and 500 for `deepseek-v4-pro`) [2]. To protect multi-tenant applications from single-user abuse, developers can pass a `user_id` parameter in API payloads, which caps any individual end-user ID to **10 concurrent requests** (returning HTTP `429 Too Many Requests` only for that `user_id` while leaving the parent organization's global pool unaffected) [2].

## Data Governance and Privacy Policy

According to DeepSeek's Privacy Policy, consumer web, mobile app, and platform services are operated by Hangzhou DeepSeek Artificial Intelligence Co., Ltd. and Beijing DeepSeek Artificial Intelligence Co., Ltd. [7]. User prompts, uploaded files, conversation histories, and interaction logs collected through DeepSeek's services are stored on servers located in the **People's Republic of China** and governed by PRC data protection and cybersecurity laws [7]. While consumer interaction data may be reviewed for safety compliance and service improvement unless opted out where applicable, open-weight distributions of DeepSeek-V2, DeepSeek-V3, and DeepSeek-R1 allow enterprises to self-host the model weights on private infrastructure with zero external telemetry [4][5][7].

## Frequently asked questions

### What are DeepSeek's main API models as of November 2026?

DeepSeek offers two primary production API models: deepseek-flash (powered by DeepSeek-V4.1-Flash-1017) for high-throughput multimodal reasoning and coding, and deepseek-v4-pro (powered by DeepSeek-V4-Pro-0813) for frontier deep reasoning. Both models feature a 1-million-token context window and up to 384,000 maximum output tokens. [1][3]

### How does DeepSeek's peak and off-peak API pricing work?

DeepSeek discounts API token prices by 50% on cache-miss input and output tokens during off-peak hours (00:00 to 08:00 Beijing Time / UTC+8, corresponding to 16:00 to 00:00 UTC). For example, deepseek-flash input (<=256K context, cache miss) drops from $0.30/M tokens during peak hours to $0.15/M tokens off-peak, while output drops from $1.50/M to $0.75/M. [1]

### How do DeepSeek's API rate limits and user_id concurrency controls work?

DeepSeek enforces in-flight concurrency caps of 2,500 simultaneous requests for deepseek-flash and 500 for deepseek-v4-pro. If a developer passes an end-user identifier in the user_id field, DeepSeek restricts that specific user_id to 10 concurrent requests so one end user cannot exhaust the developer's account-wide quota. [2]

### What architectural innovations made DeepSeek-V3 and DeepSeek-R1 notable?

DeepSeek-V3 (671B total parameters, 37B active per token) combined Multi-head Latent Attention (MLA) for low-memory KV caching with an auxiliary-loss-free DeepSeekMoE router and FP8 training. DeepSeek-R1 then applied large-scale pure reinforcement learning (GRPO) and multi-stage cold-start training to achieve frontier reasoning performance under an open MIT License. [4][5]

### Where does DeepSeek store data sent to its hosted web app and API?

Under DeepSeek's Privacy Policy, data transmitted to DeepSeek's hosted consumer and platform services is stored on servers located in the People's Republic of China and managed by Hangzhou DeepSeek Artificial Intelligence Co., Ltd. Organizations requiring local data residency can self-host DeepSeek's open-weight models. [4][7]

## Quotable sentences

- DeepSeek's production API endpoints deepseek-flash (DeepSeek-V4.1-Flash-1017) and deepseek-v4-pro (DeepSeek-V4-Pro-0813) both support a 1M token context window and up to 384K output tokens. [1][3]
- DeepSeek offers 50% off-peak pricing discounts between 00:00 and 08:00 UTC+8 (16:00-00:00 UTC) for cache-miss inputs and outputs on both deepseek-flash and deepseek-v4-pro. [1]
- DeepSeek caps API concurrency at 2,500 in-flight requests for deepseek-flash and 500 for deepseek-v4-pro, with an optional per-end-user cap of 10 concurrent requests via the user_id parameter. [2]
- On November 18, 2026, DeepSeek enabled built-in server-side web search and fetch in its chat completions API free of additional search query fees. [1][3]
- DeepSeek-V3 is a 671B-parameter Mixture-of-Experts model with 37B active parameters per token trained on 14.8T tokens, and DeepSeek-R1 was released under the MIT License in January 2025. [4][5]

## Timeline

- 2024-05: DeepSeek publishes the DeepSeek-V2 technical report introducing Multi-head Latent Attention (MLA) and a 236B/21B MoE architecture. [6]
- 2024-12: DeepSeek releases DeepSeek-V3, a 671B-parameter (37B active) Mixture-of-Experts model pre-trained on 14.8 trillion tokens with FP8 precision. [5]
- 2025-01: DeepSeek releases DeepSeek-R1, DeepSeek-R1-Zero, and six distilled reasoning models under the open-source MIT License. [4]
- 2026-08-19: DeepSeek launches DeepSeek-V4-Pro-0813 (deepseek-v4-pro) on its API platform with 1M context and multimodal text, image, and audio input. [1][3]
- 2026-10-20: DeepSeek deploys DeepSeek-V4.1-Flash-1017 as the underlying model for the high-throughput deepseek-flash endpoint. [1][3]
- 2026-11-18: DeepSeek enables built-in server-side web search and page fetching inside its chat completions API at no additional search fee. [1][3]

## Sources

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (checked 2026-11-23; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (checked 2026-11-23; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. published 2026-11-18. https://api-docs.deepseek.com/updates (checked 2026-11-23; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. published 2025-01-22. https://arxiv.org/abs/2501.12948 (checked 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. published 2024-12-27. https://arxiv.org/abs/2412.19437 (checked 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. published 2024-05-07. https://arxiv.org/abs/2405.04434 (checked 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "DeepSeek." Version 633a03f8, 2026-11-23. https://mimirwiki.com/wiki/deepseek
