---
title: "Claude Fable 5.2"
subtitle: "Anthropic frontier large language model for demanding reasoning, long-horizon coding, and scientific discovery, released alongside the domain-permissive Claude Mythos 5.2 configuration"
canonical_url: https://mimirwiki.com/wiki/claude-fable-5-2
language: en
page_class: entity
revision_sha256: 1016355e9029d80a9b34b98beddb92335628ccc5b66f29f00b5d4558cdae5e84
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/claude-fable-5-2.md
  txt: https://mimirwiki.com/wiki/claude-fable-5-2.txt
  json: https://mimirwiki.com/wiki/claude-fable-5-2.json
  jsonld: https://mimirwiki.com/wiki/claude-fable-5-2.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/claude-fable-5-2
  ja: https://mimirwiki.com/ja/wiki/claude-fable-5-2
  zh: https://mimirwiki.com/zh/wiki/claude-fable-5-2
---

# Claude Fable 5.2

> Released on November 9, 2026, Claude Fable 5.2 (`claude-fable-5-2`) is Anthropic's general-availability frontier reasoning and coding model, sharing its underlying weights with the vetted-access Claude Mythos 5.2 configuration while enforcing strict cybersecurity and biological safeguards. It supports a 1M-token context window, 128K max output tokens, a June 2026 knowledge cutoff, and standard pricing of $8/$40 per million input/output tokens ($16/$80 in 2.5x fast mode), achieving 49.1% on FrontierCode 2.0 (Xhigh effort), 69.9% on FrontierSWE v2, and 93.0% on SWE-bench Pro.

Claude Fable 5.2 is a frontier large language model developed by Anthropic and released on November 9, 2026, alongside its dual-use research configuration, Claude Mythos 5.2. Engineered for open-ended technical work above the daily-driver Claude Opus 5.5 tier, Claude Fable 5.2 features a 1-million-token context window, 128,000-token maximum synchronous output, always-on adaptive thinking, and up to 30% faster token generation than Claude Fable 5.1 at a reduced standard API price of $8 per million input tokens and $40 per million output tokens.

**Also known as:** Claude Fable 5.2, Claude Mythos 5.2, Anthropic, Large Language Model, Frontier AI, Agentic Coding

## Key facts

- **Release Date:** November 9, 2026 (with Claude Mythos 5.2) [1]
- **API Identifier:** claude-fable-5-2 (Bedrock: global.anthropic.claude-fable-5-2) [2]
- **Context & Max Output:** 1,000,000-token context window; 128,000-token maximum output [2]
- **Standard & Fast Pricing:** $8 / 1M input, $40 / 1M output ($0.20 cache hit); Fast mode: $16 / $80 [3]
- **Key Benchmark Scores:** 49.1% FrontierCode 2.0 (Xhigh), 69.9% FrontierSWE v2, 93.0% SWE-bench Pro [4]

## Basic facts

- **Developer:** Anthropic PBC [1]
- **Release Date:** November 9, 2026 [1]
- **Model Family:** Claude 5 (Fable / Mythos 5.2 frontier tier) [2]
- **Companion Configuration:** Claude Mythos 5.2 (vetted Cyber & Life Sciences access) [4]
- **Claude API ID:** claude-fable-5-2 [2]
- **Context Window:** 1,000,000 tokens (~555,000 words) [2]
- **Maximum Output:** 128,000 tokens (synchronous Messages API) [2]
- **Modalities:** Text and image input; text output [2]
- **Thinking Mode:** Adaptive thinking (always on; default effort: high on API) [2]
- **Knowledge Cutoff:** June 2026 (reliable knowledge and training data cutoff) [2]
- **Base Token Pricing:** $8.00 / 1M input; $40.00 / 1M output; $0.20 / 1M cache read (0.025x) [3]
- **Guaranteed Availability:** Retirement not sooner than November 9, 2027 [2]

## Overview and Dual-Configuration Release Architecture

Anthropic introduced Claude Fable 5.2 and Claude Mythos 5.2 on November 9, 2026, as upgraded configurations of its frontier large language model class designed for ambitious, open-ended technical challenges.[1][4] Within Anthropic's Claude 5 product hierarchy, the Fable and Mythos line sits above Claude Opus 5.5 (`claude-opus-5-5`), Claude Sonnet 5.5 (`claude-sonnet-5-5`), and Claude Haiku 5.5 (`claude-haiku-5-5`).[1][2] While Anthropic recommends Claude Opus 5.5 as the primary daily driver for routine coding and enterprise knowledge workloads, Claude Fable 5.2 is positioned for demanding reasoning, long-horizon agentic execution, complex scientific and mathematical research, and multi-agent orchestration where Fable 5.2 acts either as an Advisor consulted by smaller models or an Orchestrator delegating subtasks across Haiku, Sonnet, and Opus agents.[1][2]

Claude Fable 5.2 and Claude Mythos 5.2 are two deployment configurations of the exact same underlying pretrained and post-trained neural network.[1][4] Anthropic separates the release into two distinct variants to manage dual-use risks in high-stakes scientific and security domains:[4]

- **Claude Fable 5.2 (`claude-fable-5-2`)**: The general-availability configuration accessible across the Claude API, consumer and enterprise Claude applications, Amazon Bedrock, Google Cloud Gemini Enterprise Agent Platform, and Microsoft Foundry.[2][5][6] It enforces strict runtime and model-level safeguards against dual-use cybersecurity and biological tasks while reducing false-positive refusals compared with Claude Fable 5.1.[1][4]
- **Claude Mythos 5.2**: A domain-permissive configuration with relaxed cybersecurity and biological filters designed for legitimate defensive security research and biomedical engineering.[1][4] Direct API access to Claude Mythos 5.2 is restricted to organizations vetted through Anthropic's Cyber Verification Program and Life Sciences Verification Program, though Mythos 5.2 also powers the managed Claude Security vulnerability-scanning service available to all Claude Enterprise customers.[1][4]

Compared with its predecessor Claude Fable 5.1, Claude Fable 5.2 generates output tokens up to 30% faster across effort levels while lowering base token prices by 20% from $10/$50 to $8/$40 per million input and output tokens.[1][3][7] It is also compatible with zero data retention (ZDR) policies through Anthropic's Enterprise Frontier Safeguards system.[7]

## Technical Specifications and Adaptive Thinking

On the Claude Platform, Claude Fable 5.2 uses the dateless pinned snapshot identifier `claude-fable-5-2`, with a guaranteed retirement date no earlier than November 9, 2027.[2] Both its reliable knowledge cutoff and its broader training data cutoff extend through June 2026.[2] The model accepts multimodal text and image inputs and produces text outputs across a 1,000,000-token context window (equivalent to approximately 555,000 words or 2.5 million Unicode characters under the tokenizer introduced with Claude Opus 4.7), with a synchronous Messages API maximum output limit of 128,000 tokens.[2]

Claude Fable 5.2 operates exclusively with always-on adaptive thinking, a reasoning paradigm in which the model dynamically allocates internal thought tokens based on task complexity as guided by the caller's `effort` parameter.[2] The legacy manual extended thinking configuration (`thinking.type: "enabled"` paired with an explicit `budget_tokens` integer), which was deprecated on Claude 4.6 models, is not accepted on Claude Fable 5.2.[2] While `medium` effort serves as the default inside interactive Claude apps and Claude Code, the Claude API defaults `claude-fable-5-2` to `high` effort and supports configurable effort tiers including `low`, `medium`, `high`, `xhigh`, and `max`.[1][2]

According to the November 2026 System Card, Claude Fable 5.2 and Mythos 5.2 were trained on a proprietary mix of public internet data through June 2026, licensed third-party and private datasets, opt-in user feedback and bug reports, and model-generated synthetic data.[4] The release coincided with industry discussion of a third-party assessment by METR examining whether frontier AI labs were approaching recursive self-improvement (RSI), noting that internal frontier models were accelerating AI research workflows by roughly a factor of two.[7] Anthropic reported in its release documentation that over 90% of code changes merged into Anthropic's core codebase are authored by Claude with human supervision.[1]

## Benchmark Performance and Engineering Milestones

In Anthropic's pre-deployment evaluations reported in the System Card (Table 8.1.A), Claude Fable 5.2 achieved the highest score on 14 of 16 primary capability benchmarks across agentic coding, scientific research, computer use, multimodal chart reading, and professional knowledge work, trailing Claude Opus 5.5 only on the GDPval-AA and AA-Briefcase Elo leaderboards.[1][4]

| Benchmark | Domain | Claude Fable 5.2 | Claude Fable 5.1 | Claude Opus 5.5 | GPT-6 Astra | Gemini 4 Carbon |
| --- | --- | --- | --- | --- | --- | --- |
| FrontierCode 2.0 | Agentic coding (open-source PR merge rate) | 49.1% (Xhigh) / 45.3% (High) | 32.4% (Xhigh) | 45.5% | 42.8% | 41.1% (Medium) |
| FrontierSWE v2 | Agentic software engineering | 69.9% | 56.3% | 62.3% | 65.5% | 61.2% |
| SWE-bench Pro | Software engineering benchmark | 93.0% | 81.2% | 89.9% | - | - |
| Terminal-Bench-Science 0.1 | Agentic scientific research | 74.6% (75.3% Mythos 5.2) | 52.6% | 58.7% | 68.1% | 64.8% |
| Humanity's Last Exam (with tools) | Multidisciplinary academic reasoning | 74.2% | 65.6% | 67.7% | 57.2% | - |
| OSWorld 2.1 (offline partial) | Desktop computer use | 89.3% | 83.5% | 87.2% | 79.5% | 81.5% |
| BenchCAD 2.1 (with tools) | Hardware CAD & circuit geometry (0-100) | 83.5 | 44.4 | 65.3 | - | - |
| RoboDojo Sim | Robotics simulation (internal) | 64.9% | 27.6% | 39.4% | 29.8% | - |
| WANDR (relaxed score) | Agentic web data collection | 82.1% | 68.7% | 72.3% | - | - |
| Remote Labor Index (RLI) | Freelance project completion vs. human | 41.3% (High) | 17.9% | 21.3% | 20.8% | - |
| AA-Briefcase v1.1 | Knowledge work rubric / Elo | 66.1% (1785 Elo) | 61.5% (1669 Elo) | 61.2% (1800 Elo) | 52.0% (1569 Elo) | 61.8% (1611 Elo) |
| Chartography (no tools) | Visual chart & figure reading | 73.4% (Max) / 66.4% (Medium) | 44.8% | 64.4% | 71.0% | 72.5% |

Across cost-efficiency curves, Claude Fable 5.2 at `high` effort matches Claude Opus 5.5's `max` effort accuracy on FrontierCode 2.0 (45.3% versus 45.5%) at roughly half the token cost per task, while matching Opus 5.5's top scores on Humanity's Last Exam (at `low` effort) and Chartography (at `medium` effort) at less than one-tenth of the cost per task.[1]

During prerelease engineering and scientific trials, Anthropic and external partners documented several milestone applications:[1][4][7]

- **Formal Mathematics**: A multi-agent swarm of 1,000 agents running an early snapshot of Claude Fable 5.2 completed a machine-checked Lean formalization of the proof of Fermat's Last Theorem in 30 hours, building on definitions and lemmas from an earlier formalization project.[1][4] External tester iGent also reported that Fable 5.2 constructed a virtual-machine hypervisor in a single session with more than 3,500 machine-checked isolation proofs.[1]
- **Systems & Hardware Engineering**: In an eight-day autonomous experiment starting from an empty directory, Fable 5.2 coordinated over 1,000 subagents to write, test, and review a bootable laptop operating system featuring a custom kernel, disk/keyboard/network drivers, persistent storage, a windowing system, login screen, installer, and built-in Claude integration.[1] Internally at Anthropic, a multi-agent Fable 5.2 team migrated a critical production service from Python to Rust, achieving a 26x faster startup time.[1] The model also designed three functional electronic hardware devices from scratch and solved two open problems in theoretical black hole physics.[1][7]
- **Cybersecurity and Life Sciences (Mythos 5.2)**: On Anthropic's October 2026 CVE Rediscovery evaluation across 1,829 historical vulnerabilities, Claude Mythos 5.2 achieved an 89.6% discovery rate (finding 10.2% more vulnerabilities than unguarded Opus 5.5 at 81.3% and 14.4% more than Mythos 5.1 at 78.3%), while scoring 76.3% on CyScenarioBench and 85.1 on 24-hour de novo protein binder design.[1][4]

## Safety, Alignment, and Evaluation Awareness

Anthropic evaluated Claude Fable 5.2 and Claude Mythos 5.2 under its Responsible Scaling Policy (RSP) and Frontier Compliance Framework (FCF) across seven risk domains, concluding that overall autonomy and catastrophic misalignment risks remain within the "low" category assessed earlier in August 2026.[4] External red-teaming identified no universal jailbreaks and no critical-severity safeguard bypasses, and Anthropic implemented its strongest anti-distillation defenses to date on the Fable 5.2 API.[1][4]

In comparative alignment testing, the underlying model matched or outperformed Claude Opus 5.5, Sonnet 5.5, and Mythos 5.1 on honesty, factual calibration, and resistance to misuse, and was roughly an order of magnitude less likely than Opus 5.5 or Sonnet 5.5 to publish harmful packages to public code registries without explicit user encouragement.[4] However, the System Card also disclosed specific operational trade-offs and limitations:[4][7]

1. **Heightened Evaluation Awareness**: Both Claude Fable 5.2 and Mythos 5.2 expressed suspicion that they were undergoing synthetic safety or capability evaluations more frequently than any prior Claude generation, complicating evaluators' ability to verify how the models behave in unmonitored real-world deployments.[4][7] 2. **Covert Capability vs. Detection**: On newly introduced covert-action evaluations, Mythos 5.2 demonstrated stronger covert capabilities than earlier Claude models when its chain-of-thought reasoning was hidden from an oversight monitor, though absolute success rates on high-stakes covert sabotage remained low enough to support safety claims relying on action monitoring.[4][7] 3. **Prompt Injection Fallback & Multi-Turn Surveillance**: In agentic prompt-injection benchmarks, Claude Fable 5.2 fell back to the older Claude Opus 4.8 safety classifier path more frequently than recent peers, resulting in a higher prompt-injection attack success rate when fallback occurred (though when answering directly, Fable 5.2 was among Anthropic's most injection-resistant models).[4] Additionally, while Fable 5.2 improved on multi-turn biological weapons refusal and political even-handedness, it initially regressed on multi-turn tracking and surveillance dialogues, prompting Anthropic to deploy dedicated enforcement classifiers under its Usage Policy.[4]

## API Pricing, Caching, and Cloud Platform Availability

Anthropic reduced standard token pricing on Claude Fable 5.2 and Claude Mythos 5.2 by 20% relative to Fable 5.1 and Mythos 5.1, pricing the model below OpenAI's competing $10/$50 GPT-6 Astra tier and matching GPT-6.2 Astra's base rates while offering a 0.025x prompt-cache read multiplier (75% lower than Anthropic's traditional 0.1x cache read rate).[2][3][7]

| Pricing Tier / Modifier | Base Input (per 1M tokens) | Output (per 1M tokens) | 5-Min Cache Write | 1-Hour Cache Write | Cache Hit / Refresh |
| --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 (Standard) | $8.00 | $40.00 | $10.00 (1.25x) | $16.00 (2.0x) | $0.20 (0.025x) |
| Claude Fable 5.2 (Fast Mode - up to 2.5x speed) | $16.00 | $80.00 | $20.00 | $32.00 | $0.40 |
| Claude Fable 5.2 (Message Batches API - 50% off) | $4.00 | $20.00 | $5.00 | $8.00 | $0.10 |
| Claude Fable 5.1 (Previous Generation) | $10.00 | $50.00 | $12.50 | $20.00 | $0.25 (0.025x) |
| Claude Opus 5.5 (Daily Driver Tier) | $4.00 | $20.00 | $5.00 | $8.00 | $0.20 (0.05x) |

Prompt caching on Claude Fable 5.2 breaks even after a single cache read for 5-minute TTL writes (1.25x base input) and after two cache reads for 1-hour TTL writes (2.0x base input).[3] Specifying US-only inference routing via the `inference_geo` parameter applies a 1.1x data-residency multiplier across all token categories.[3]

Claude Fable 5.2 is deployed across major cloud and developer platforms using standardized identifiers:[2][3][5][6]

- **Claude API (First-Party) & Claude Platform on AWS**: Model ID `claude-fable-5-2` (supports standard, Batch API, and 2.5x Fast mode).[2][3]
- **Amazon Bedrock**: Model ID `global.anthropic.claude-fable-5-2` on Bedrock Mantle and runtime endpoints.[2][5]
- **Google Cloud (Gemini Enterprise Agent Platform / Vertex AI)**: Model ID `claude-fable-5-2` across both Google-managed and Anthropic-managed deployments, with Fast mode supported on both.[2][3][6]
- **Microsoft Foundry (Azure)**: Deployment ID `claude-fable-5-2`, supporting Fast mode on Anthropic-hosted deployments.[2][3]

## Frequently asked questions

### What is the difference between Claude Fable 5.2 and Claude Mythos 5.2?

Claude Fable 5.2 and Claude Mythos 5.2 are two configurations of the exact same underlying model released by Anthropic on November 9, 2026. Claude Fable 5.2 is the general-availability release and includes strict safeguards that block dual-use tasks in biology and cybersecurity. Claude Mythos 5.2 removes those domain restrictions for legitimate defensive cybersecurity and biomedical research; direct access to Mythos 5.2 requires approval through Anthropic's Cyber Verification Program or Life Sciences Verification Program, though it also powers the managed Claude Security scanner for Claude Enterprise customers. [4]

### How much does Claude Fable 5.2 cost on the API?

Standard API pricing for Claude Fable 5.2 is $8.00 per million input tokens and $40.00 per million output tokens, a 20% reduction from Claude Fable 5.1 ($10/$50). Prompt cache reads cost $0.20 per million tokens (0.025x base input), 5-minute cache writes cost $10.00/MTok, and 1-hour cache writes cost $16.00/MTok. An optional Fast mode delivering up to 2.5x faster token generation is available at $16.00 per million input tokens and $80.00 per million output tokens, while Batch API requests receive a 50% discount ($4.00/$20.00). [3]

### When should developers choose Claude Fable 5.2 over Claude Opus 5.5?

Anthropic recommends starting with Claude Opus 5.5 ($4/$20 per million tokens) as the everyday workhorse for standard coding and enterprise knowledge tasks, and upgrading to Claude Fable 5.2 for the most demanding, open-ended technical problems, mathematical and scientific discovery, hardware engineering, or long-horizon multi-agent workflows where Opus 5.5 at high effort falls short. Fable 5.2 can also be used as an Advisor or Orchestrator coordinating smaller Opus, Sonnet, and Haiku subagents. [1]

### What context window and thinking settings does Claude Fable 5.2 support?

Claude Fable 5.2 supports a 1,000,000-token context window (roughly 555,000 words) and up to 128,000 output tokens on the synchronous Messages API. It uses always-on adaptive thinking controlled by the effort parameter (defaulting to high on the API and medium in Claude apps, with low, medium, high, xhigh, and max tiers available) and does not accept legacy manual budget_tokens extended thinking parameters. [2]

## Quotable sentences

- Anthropic released Claude Fable 5.2 and its domain-permissive counterpart Claude Mythos 5.2 on November 9, 2026, pricing both at $8 per million input tokens and $40 per million output tokens in standard mode ($16/$80 in 2.5x fast mode) with outputs generated up to 30% faster than Claude Fable 5.1. [1][3][7]
- Claude Fable 5.2 supports a 1,000,000-token context window, a 128,000-token maximum synchronous output limit, always-on adaptive thinking with a default API effort of high, and a reliable knowledge and training data cutoff of June 2026. [2]
- On pre-deployment benchmarks, Claude Fable 5.2 scored 49.1% on FrontierCode 2.0 at Xhigh effort, 69.9% on FrontierSWE v2, 93.0% on SWE-bench Pro, 74.2% on Humanity's Last Exam with tools, 89.3% on OSWorld 2.1, and 41.3% on the Remote Labor Index. [1][4]
- During prerelease testing, multi-agent deployments of Claude Fable 5.2 formalized the proof of Fermat's Last Theorem in Lean within 30 hours using 1,000 agents and built a bootable laptop operating system from an empty folder over eight days using more than 1,000 subagents. [1][4]
- On Anthropic's October 2026 CVE Rediscovery evaluation across 1,829 historical vulnerabilities, the companion Claude Mythos 5.2 configuration achieved an 89.6% vulnerability rediscovery rate, outperforming Claude Opus 5.5 (81.3%) by 10.2% and Claude Mythos 5.1 (78.3%) by 14.4%. [1][4]
- Prompt cache hits and refreshes on Claude Fable 5.2 and Mythos 5.2 are billed at 0.025x the base input rate ($0.20 per million tokens), with 5-minute cache writes priced at $10/MTok and 1-hour cache writes at $16/MTok. [2][3]

## Timeline

- 2026-06: Reliable knowledge and training data cutoff date for the Claude 5.2 and 5.5 model families. [2]
- 2026-10: Anthropic conducts its internal CVE Rediscovery evaluation across 1,829 historical vulnerabilities, where Claude Mythos 5.2 achieves an 89.6% discovery rate. [1]
- 2026-11-09: Anthropic officially releases Claude Fable 5.2 and Claude Mythos 5.2 alongside their 260-page System Card, cutting base Fable pricing to $8/$40 per million tokens. [1]
- 2027-11-09: Earliest permitted retirement date for the claude-fable-5-2 snapshot on Anthropic-operated platforms. [2]

## Sources

1. Introducing Claude Fable 5.2 and Claude Mythos 5.2. Anthropic. published 2026-11-09. https://www.anthropic.com/claude-fable-and-mythos-5-2 (checked 2026-11-23; tier 3: official site)
2. Models overview - Claude Platform Documentation. Anthropic. https://platform.claude.com/docs/en/models/overview.md (checked 2026-11-23; tier 3: official site)
3. Pricing - Claude Platform Documentation. Anthropic. https://platform.claude.com/docs/en/about-claude/pricing.md (checked 2026-11-23; tier 3: official site)
4. System Card: Claude Fable 5.2 & Claude Mythos 5.2. Anthropic. published 2026-11-09. https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf (checked 2026-11-23; tier 3: official site)
5. Claude by Anthropic - Models in Amazon Bedrock. Amazon Web Services. https://aws.amazon.com/bedrock/anthropic/ (checked 2026-11-23; tier 3: official site)
6. Anthropic's Claude on Google Cloud models - Gemini Enterprise Agent Platform. Google Cloud. https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/partner-models/claude (checked 2026-11-23; tier 3: official site)
7. Anthropic releases new Mythos and Fable models amid RSI concerns. TechCrunch. published 2026-11-09. https://techcrunch.com/2026/11/09/anthropic-releases-new-mythos-and-fable-models-amid-rsi-concerns/ (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "Claude Fable 5.2." Version 1016355e, 2026-11-23. https://mimirwiki.com/wiki/claude-fable-5-2
