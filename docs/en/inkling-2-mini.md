---
title: "Inkling 2 Mini"
subtitle: "Thinking Machines Lab open-weight looped Mixture-of-Experts vision-language model engineered for local laptop and workstation inference"
canonical_url: https://mimirwiki.com/wiki/inkling-2-mini
language: en
page_class: entity
revision_sha256: 1bb6980c112aa9426452400eb238264f50f171933ac762d6b04e8a150c10a326
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/wiki/inkling-2-mini.md
  txt: https://mimirwiki.com/wiki/inkling-2-mini.txt
  json: https://mimirwiki.com/wiki/inkling-2-mini.json
  jsonld: https://mimirwiki.com/wiki/inkling-2-mini.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/inkling-2-mini
---

# Inkling 2 Mini

> Released on November 20, 2026, under the Apache 2.0 license, Inkling 2 Mini (`thinkingmachines/Inkling-2-Mini`) is a 26.4B-parameter looped Mixture-of-Experts vision-language model with a 1-million-token context window. By cycling through its 12 middle layers three times per token (48 logical layer visits, 3.4B unique active parameters, 5.4B effective activations) and training natively in 4-bit NVFP4 and 8-bit MXFP8 (~20 GB footprint), it runs offline on consumer laptops while scoring 48.2% on DeepSWE v1.1, 79.2% on SWE-bench Verified, and 20.1 on the Artificial Analysis Intelligence Index v5.0.

Inkling 2 Mini is an open-weight vision-language model released on November 20, 2026, by Thinking Machines Lab, the artificial intelligence research company led by former OpenAI chief technology officer Mira Murati. Built on a 24-layer looped Mixture-of-Experts (MoE) Transformer architecture with 26.4 billion total parameters, the model executes its middle 12 layers three times per token to yield 48 effective layer applications and 5.4 billion effective weight activations per token from 3.4 billion unique active parameters, running locally within an approximately 20 GB mixed-precision (NVFP4/MXFP8) footprint under an Apache 2.0 license.

**Also known as:** Inkling 2 Mini, Thinking Machines Lab, Looped Transformer, Mixture-of-Experts, Open-Weight AI, Local LLM

## Key facts

- **Release Date & License:** November 20, 2026; Apache 2.0 (with Acceptable Use Policy) [1]
- **Architecture:** 24-layer Looped MoE (48 layer visits; 8 of 128 SwiGLU experts routed) [2]
- **Parameter Counts:** 26.4B total, 3.4B unique active, 5.4B effective activations per token [1]
- **Native Precision & Footprint:** NVFP4 (first 20 layers) + MXFP8 (last 4 layers); ~20 GB checkpoint (17.5 GB 4-bit GGUF) [3]
- **Benchmark Highlights:** 48.2% DeepSWE v1.1, 79.2% SWE-bench Verified, 77.9% SWE-bench Pro v2 Hard, 20.1 AAv5 [1]

## Basic facts

- **Developer:** Thinking Machines Lab [1]
- **Release Date:** November 20, 2026 [1]
- **Model ID:** thinkingmachines/Inkling-2-Mini [2]
- **Research Companion:** thinkingmachines/TML-d24-varloop-research (variable 1-5 loop passes) [2]
- **Architecture:** Looped sparse Mixture-of-Experts Transformer (24 physical / 48 logical layers) [2]
- **Parameters:** 26.4B total / 3.4B unique active / 5.4B effective weight activations per token [1]
- **Context Window:** 1,000,000 tokens [5]
- **Modalities:** Text and image input; text output [5]
- **Numeric Precision:** Native NVFP4 (layers 0-19) and MXFP8 (layers 20-23) [1]
- **Memory Requirements:** ~20 GB native checkpoint (32 GB RAM/VRAM recommended; 17-18 GB for 4-bit GGUF) [5]
- **First-Party API Pricing:** $0.15 / 1M input; $0.50 / 1M output; $0.015 / 1M cache hit (on Tinker) [4]
- **License:** Apache 2.0 (accompanied by Model Acceptable Use Policy) [5]

## Overview and Looped Mixture-of-Experts Architecture

Thinking Machines Lab, the San Francisco artificial intelligence research company founded and led by former OpenAI chief technology officer Mira Murati, released Inkling 2 Mini on November 20, 2026, as an open-weight vision-language model tailored for local laptops, desktop workstations, and autonomous coding agents.[1][3] Derived from Thinking Machines' mainline predictive scaling ladder and positioned below the larger Inkling 2 Small model, Inkling 2 Mini is licensed under Apache 2.0 (paired with a Model Acceptable Use Policy) and supports multimodal text and image inputs across a 1-million-token context window.[1][2][5]

Rather than relying solely on long externalized chain-of-thought (CoT) text transcripts or larger parameter counts, Inkling 2 Mini introduces a looped Mixture-of-Experts (MoE) Transformer design.[1][2][3] The text decoder stores 24 physical layers with a hidden dimension of 2,304 (half the 4,608 width of Inkling 2 Small) and an expert intermediate width of 1,152, routing each token to 8 of 128 SwiGLU experts per layer visit (compared with 8 of 384 experts in Inkling 2 Small).[2] The 24 physical layers are organized into four six-layer blocks that execute 48 logical layer visits per token:[1][2]

- **Prelude Block (Layers 0-5)**: Runs once per token to project embeddings into internal representations.[1][2]
- **Looped Core Blocks (Layers 6-17)**: The two middle six-layer blocks execute three consecutive passes per token while sharing the same stored weights (`6 + 3 * 12 + 6 = 48` layer applications).[1][2] In internal scaling studies across 28 evaluations, looping the middle 12 layers outperformed looping the final 12 layers on 27 tasks, providing a 1.51x to 1.91x compute-equivalent loss gain at training step 2,000 (and requiring 140% more inference compute for a non-looping baseline to match its loss on 512K-token agentic traces).[1][3]
- **Final Block (Layers 18-23)**: Runs once per token to decode the refined internal representation.[1][2]

Every six-layer block comprises five sliding-window attention layers (with a 1,024-token local window) and one full-attention layer featuring dynamic key and value short convolutions, 24 query heads, 8 key-value heads, learned relative position logits, a learned attention sink, and an output gate.[2] While all three passes through layers 6-17 reuse the same parameter weights, each of the 48 visits maintains its own distinct KV cache and short-convolution state.[2] To pass information across iterations, Inkling 2 Mini implements attention residuals (building on Kimi Team's 2026 attention residual formulation): every pass through the looped core begins with the Prelude Block's output, while passes 2 and 3 also attend over two residual blocks from the preceding pass ("cross-pass messages") via learned queries and four rank-64 gating controllers that mix the prior message into the query, key, value, and MoE inputs.[1][2]

In total, Inkling 2 Mini contains 26.4 billion physical parameters, activates 3.4 billion unique parameters on a single pass (3.1 billion unique weights per text token), and applies 5.4 billion effective weight activations per token across the three loop passes.[1][4][5]

## Expert Pruning, Distillation Healing, and Native NVFP4 Training

To compress a frontier-capable reasoning architecture into a ~20 GB memory footprint that fits in consumer laptop memory, Thinking Machines modified its mainline training pipeline through mid-training expert pruning and native low-bit precision training:[1][3]

1. **Two-Thirds Expert Pruning and Distillation Healing**: Starting from a wider mainline checkpoint with 384 experts per layer, Thinking Machines pruned two-thirds of the experts down to 128 experts per layer.[1][2][3] The pruned network was then "healed" by distilling 1 trillion tokens from a larger internal Inkling model, followed by supervised fine-tuning (SFT) and 2.2 trillion tokens of reinforcement learning (RL).[3] 2. **Native NVFP4 and MXFP8 Precision**: Instead of relying on post-training quantization that can degrade agentic coding accuracy, Thinking Machines trained and deployed the first 20 physical layers natively in 4-bit NVFP4 precision and the final four layers in 8-bit MXFP8 precision.[1][3] Because the distributed weights match the numerical format used during training, the upstream mixed-precision checkpoint requires approximately 20 GB of memory without post-training quantization loss.[3][5] 3. **Configurable Numeric Reasoning Effort**: The model's chat template accepts a `reasoning_effort` parameter expressed either as a named tier or a continuous float between `0.0` and `0.99`, injected into the prompt as a system message: `none` (`0.0`), `minimal` (`0.1`), `low` (`0.2`), `medium` (`0.7`), `high` (`0.9`, the default), `xhigh` (`0.99`), and `max` (`0.99`).[2] Even at the minimum setting, internal reasoning is not completely disabled.[5]

## Benchmark Performance and Energy Efficiency

Across 48 standardized benchmarks comparing sub-100B open-weight models (including Alibaba's dense Qwen3.8-27B, Google DeepMind's Gemma 4 31B, Meta's Muse Glimmer, and NVIDIA's 124.5B Nemotron 3.5 Super VL), Inkling 2 Mini ranked first in 32 evaluations.[1][2] On the Artificial Analysis Intelligence Index v5.0 (AAv5), Inkling 2 Mini scored 20.1, tying the dense Qwen3.8-27B while using roughly 5x fewer active parameters, 2.8x less total compute (active parameters multiplied by tokens), 4x less wall-clock time per task (9.0 minutes versus 38.2 minutes), and 6x lower cost per task ($0.59 versus $3.53 at Thinking Machines' first-party Tinker API rates of $0.15/1M input, $0.50/1M output, and $0.015/1M cache hits).[1][3][4]

| Benchmark | Category | Inkling 2 Mini (5.4B eff. / 26.4B) | Qwen3.8-27B (27B Dense) | Gemma 4 31B (30.7B Dense) | Muse Glimmer (30B Dense) | Nemotron 3.5 Super VL (12B / 124.5B) |
| --- | --- | --- | --- | --- | --- | --- |
| AA Intelligence Index v5.0 | Aggregate Intelligence | 20.1 (Tied 1st) | 20.1 (Tied 1st) | 4.4 | 6.3 | 13.6 |
| Vals Index v2.2 | Aggregate Enterprise / Coding | 46.5% | - | - | - | 29.8% |
| DeepSWE v1.1 | Agentic Software Engineering | 48.2% | 42.2% | 0.3% | 4.4% | 24.7% |
| SWE-bench Pro v2 (Hard) | Hard Software Engineering (51 tasks) | 77.9% | 73.8% | 14.2% | 44.3% | 44.1% |
| SWE-bench Verified | Bash-only Software Engineering | 79.2% | 77.8% | 46.1% | 76.0% | 71.1% |
| FrontierCode v2.0 | Open-Source PR Merging | 15.1% | 14.9% | 0.0% | 1.5% | 6.1% |
| Terminal Bench v4.0 | Terminal Agent Execution | 5.6% (Tied 1st) | 5.6% (Tied 1st) | 0.0% | 0.5% | 0.0% |
| BrowseComp | Agentic Web Browsing (with compaction) | 79.0% | 61.6% | 37.0% | 63.9% | 78.9% |
| DeepSearchQA | Deep Search Question Answering | 85.3% | 79.7% | 61.7% | 74.6% | 77.7% |
| MCP Atlas Public | Model Context Protocol Tool Use | 82.7% | 77.3% | 54.2% | 75.5% | 67.7% |
| OmniDocBench v1.6 | Document Vision Understanding | 92.8% | 91.5% | 82.5% | 90.4% | 77.9% |
| LongBench v2 | Long-Context Reasoning | 66.9% | 52.3% | 52.9% | 33.1% | 62.1% |
| AA-Omniscience v1.1 | Parametric Factuality / Non-Hallucination | -8.6 (63.4%) | -6.4 (71.4%) | -48.5 (14.5%) | -32.2 (16.4%) | -2.9 (69.5%) |

In energy-efficiency testing conducted by researchers at Stanford University's Hazy Research Lab and Scaling Intelligence Lab using the Intelligence per Watt methodology on an NVIDIA DGX Spark (128 GB), Inkling 2 Mini (running at MXFP8 precision with low reasoning effort) achieved 0.703 intelligence per joule, outperforming Qwen3.6-35B-A3B (0.430 at NVFP4), Gemma-4-26B-A4B (0.159 at NVFP4), and Qwen3.5-27B (0.036 at INT4).[1][3]

Because looping increases sequential reasoning compute per token without expanding the total number of stored parameters, parametric factual recall remains bounded by its 26.4B total weight capacity: on AA-Omniscience v1.1, Inkling 2 Mini scores -8.6 with a 63.4% non-hallucination rate, trailing denser models when search tools are disabled.[1][3] It also trails Qwen3.8-27B on multi-turn conversational constraints (50.0% on MultiChallenge and 33.4% on ComplexConstraints v1.1) and can exhibit repetitive reasoning loops during prolonged debugging sessions.[1][5]

## Chain-of-Thought Monitorability and Variable-Loop Research

A central AI safety question surrounding looped transformers is whether performing multiple recurrent passes internally in latent space reduces chain-of-thought (CoT) monitorability by allowing the model to reason without externalizing its thoughts in text.[1][3] To enable systematic oversight research, Thinking Machines released a companion variable-loop research checkpoint, `thinkingmachines/TML-d24-varloop-research`, trained to execute between 1 and 5 passes through the middle 12 layers (configurable at inference time via `text_config={"loop_num_passes": N}`), and partnered with the National Deep Inference Fabric (NDIF) and Goodfire for mechanistic interpretability studies.[1][2][3]

In Thinking Machines' monitorability experiments on the variable-loop model:[1][3]

- **Latent No-CoT Horizon Expansion**: When restricted from producing visible chain-of-thought tokens, the model's effective task time horizon more than doubled from 16 seconds at 1 loop pass to 37 seconds at 3 loop passes, and its accuracy on serial reasoning tasks continued improving out to 10 loop passes (twice the maximum depth seen during training).[1][3]
- **CoT Compression vs. Legibility**: As loop depth increased, the model's visible chain-of-thought transcripts became more than 50% shorter, yet human and automated monitors found that the remaining CoT traces stayed legible and faithful.[1][3]
- **Sabotage and Misbehavior Evaluations**: Adding recurrent loop passes produced no upward trend in covert agentic sabotage on the LinuxArena control benchmark.[1][3] On internal safety evaluations, Inkling 2 Mini recorded lower rates of general misbehavior (9.8%), covert misbehavior (8.3%), and destructive actions (10.2%) than Gemma 4 31B, Muse Glimmer, Qwen3.8-27B, and Nemotron 3.5 Super VL, while scoring 89.5% on FORTRESS (adversarial) and 97.8% on StrongREJECT.[1]

## Local Deployment, Hardware Requirements, and Runtime Ecosystem

Inkling 2 Mini launched with day-zero inference support across cloud and local runtimes, including Thinking Machines' Tinker platform, Hugging Face `transformers` (`AutoModelForMultimodalLM`), `llama.cpp` and Llama App, LM Studio, Unsloth Desktop, MLX on Apple Silicon, Ollama, EXO, and SGLang for datacenter GPUs, alongside a DSpark speculative-decoding drafter model.[1][2][3][5][6] Thinking Machines demonstrated the model running completely offline in airplane mode on an Apple M5 Pro MacBook Pro (48 GB unified memory), where it built a playable 3D flight simulator in minutes and simultaneously powered 20 persistent autonomous AI villagers in the "Thinkyville" town simulation.[1][3]

| Quantization / Format | Approximate File Size | Minimum RAM / VRAM | Notes & Runtime Compatibility |
| --- | --- | --- | --- |
| Upstream Mixed-Precision (NVFP4 + MXFP8) | ~20.0 GB | 32 GB recommended | Native training precision; ideal for 32 GB+ Apple Silicon Macs or 32 GB+ GPU VRAM |
| 8-Bit GGUF (`UD-Q8_K_XL` / `Q8_0`) | ~24.0 GB | 24 GB | Lossless full-precision equivalent for llama.cpp and Unsloth |
| 4-Bit GGUF (`UD-Q4_K_XL` / `IQ4_NL`) | 17.5 - 17.6 GB | 17 - 18 GB | Recommended local GGUF quant; requires ~18 GB system memory |
| 3-Bit / 2-Bit / 1-Bit Dynamic GGUF | 9.0 - 15.0 GB | 9 - 15 GB | Unsloth Dynamic 3.0 GGUFs for 16 GB consumer laptops |
| Vision Projector (`mmproj-F16.gguf`) | +639 MB | +0.7 GB | Add-on projector required for multimodal image and document inputs in GGUF |

For local GGUF execution in `llama.cpp` or Unsloth, recommended sampling parameters are `temperature = 1.0`, `top_p = 1.0`, `top_k = 0`, and `min_p = 0.0`, using a build with looped-layer layout support and per-expert NVFP4 scales (such as `ggml-org/Inkling-2-Mini-GGUF` or `unsloth/Inkling-2-Mini-GGUF`).[2][6]

## Frequently asked questions

### How does Inkling 2 Mini's looped transformer architecture work?

Instead of passing each token through its 24 physical layers only once, Inkling 2 Mini divides its decoder into four blocks of six layers. The first block (layers 0-5) runs once, the middle two blocks (layers 6-17) run three times in a loop reusing the same stored weights, and the final block (layers 18-23) runs once. Gated attention-residual messages pass intermediate information from one loop iteration to the next, resulting in 48 layer applications and 5.4 billion effective weight activations per token while storing only 24 layers (26.4 billion total parameters, 3.4 billion unique active parameters). [2]

### What hardware is required to run Inkling 2 Mini locally?

The upstream mixed-precision checkpoint (natively trained in 4-bit NVFP4 and 8-bit MXFP8) is approximately 20 GB, for which Thinking Machines Lab recommends at least 32 GB of unified memory on Apple Silicon Macs or 32 GB of GPU VRAM. Using 4-bit GGUF quantizations (such as UD-Q4_K_XL or IQ4_NL, roughly 17.5-17.6 GB) in LM Studio, llama.cpp, or Unsloth Desktop, the model can run on systems with 16 GB to 18 GB of RAM, while 8-bit lossless GGUF requires 24 GB. [5]

### How does Inkling 2 Mini compare to Qwen3.8-27B?

On the Artificial Analysis Intelligence Index v5.0, Inkling 2 Mini ties Alibaba's dense Qwen3.8-27B at a score of 20.1 while outperforming it on agentic coding and search benchmarks including DeepSWE v1.1 (48.2% vs. 42.2%), SWE-bench Verified (79.2% vs. 77.8%), and BrowseComp (79.0% vs. 61.6%). Because Inkling 2 Mini activates only 5.4B effective parameters per token compared to 27B in the dense Qwen model, it uses roughly 2.8x less compute, completes Intelligence Index tasks 4x faster (9.0 vs. 38.2 minutes), and costs 6x less per task ($0.59 vs. $3.53). However, Qwen3.8-27B scores higher on tool-free parametric factual recall (AA-Omniscience) and multi-constraint chat instructions. [4]

### What is the TML-d24-varloop-research model released alongside Inkling 2 Mini?

TML-d24-varloop-research is an open-weight research checkpoint that shares Inkling 2 Mini's 24-layer MoE architecture but was trained to accept a variable number of passes (from 1 to 5, and tested up to 10) through its middle 12 layers via the loop_num_passes configuration parameter. Thinking Machines Lab released it so safety and interpretability researchers can measure how recurrent latent looping affects chain-of-thought length, monitorability, and reasoning depth. [2]

## Quotable sentences

- Thinking Machines Lab released Inkling 2 Mini on November 20, 2026, under an Apache 2.0 license as a 26.4-billion-parameter looped Mixture-of-Experts vision-language model supporting a 1-million-token context window. [1][2][5]
- Inkling 2 Mini's 24 physical decoder layers execute 48 logical layer visits per token by running layers 0-5 once, looping layers 6-17 three times with shared weights and cross-pass attention residual messages, and running layers 18-23 once, yielding 3.4B unique active parameters and 5.4B effective weight activations per token. [1][2][5]
- The model was compressed by pruning two-thirds of its experts (from 384 to 128 per layer), distilling 1 trillion healing tokens from a larger Inkling model followed by 2.2 trillion RL tokens, and training the first 20 layers natively in NVFP4 and the last 4 layers in MXFP8 for an approximately 20 GB footprint. [1][2][3]
- On standardized evaluations, Inkling 2 Mini leads all sub-100B open-weight models on DeepSWE v1.1 (48.2%), SWE-bench Pro v2 Hard (77.9%), SWE-bench Verified (79.2%), BrowseComp (79.0%), DeepSearchQA (85.3%), and OmniDocBench v1.6 (92.8%), while tying Qwen3.8-27B at 20.1 on the Artificial Analysis Intelligence Index v5.0. [1][3][4]
- In Stanford University's Intelligence per Watt evaluation on an NVIDIA DGX Spark, Inkling 2 Mini scored 0.703 intelligence per joule, outperforming Qwen3.6-35B-A3B (0.430), Gemma-4-26B-A4B (0.159), and Qwen3.5-27B (0.036). [1][3]
- Experiments on the companion variable-loop checkpoint (TML-d24-varloop-research) showed that increasing loop passes from 1 to 3 expanded the model's no-CoT reasoning horizon from 16 seconds to 37 seconds while maintaining chain-of-thought legibility and showing no increase in agentic sabotage. [1][2][3]

## Timeline

- 2018: Dehghani et al. publish Universal Transformers, establishing foundational concepts for weight-sharing recurrent transformer layers cited by Thinking Machines Lab. [1]
- 2026-11-20: Thinking Machines Lab releases Inkling 2 Mini and the companion TML-d24-varloop-research checkpoint under the Apache 2.0 license with day-zero support in Transformers, llama.cpp, MLX, SGLang, LM Studio, and Unsloth. [1]
- 2026-11-21: Independent benchmark analyses confirm Inkling 2 Mini on the Pareto frontier of the Artificial Analysis Intelligence Index v5.0 with a score of 20.1. [3]

## Sources

1. Introducing Inkling 2 Mini - Thinking Machines Lab. Thinking Machines Lab. published 2026-11-20. https://thinkingmachines.ai/news/inkling-2-mini/ (checked 2026-11-23; tier 3: official site)
2. Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup. Hugging Face. published 2026-11-20. https://huggingface.co/blog/inkling2mini (checked 2026-11-23; tier 3: official site)
3. Thinking Machines wows with Inkling 2 Mini looped transformer model that runs locally on laptops. VentureBeat. published 2026-11-21. https://venturebeat.com/technology/thinking-machines-wows-with-inkling-2-mini-looped-transformer-model-that-runs-locally-on-laptops (checked 2026-11-23; tier 2: academic or news)
4. Thinking Machines has released Inkling 2 Mini, an open weights looped transformer. Artificial Analysis. published 2026-11-20. https://artificialanalysis.ai/articles/inkling-2-mini (checked 2026-11-23; tier 2: academic or news)
5. Inkling 2 Mini - LM Studio Model Directory. Element Labs (LM Studio). https://lmstudio.ai/models/inkling-2-mini (checked 2026-11-23; tier 3: official site)
6. Inkling 2 Mini - Run Locally Guide | Unsloth Documentation. Unsloth. https://unsloth.ai/docs/models/inkling-2-mini (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Inkling 2 Mini." Version 1bb6980c, 2026-11-23. https://mimirwiki.com/wiki/inkling-2-mini
