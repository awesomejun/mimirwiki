---
title: "Claude"
subtitle: "AI assistant and family of large language models developed by Anthropic, PBC"
canonical_url: https://mimirwiki.com/wiki/claude
language: en
page_class: entity
revision_sha256: 569e801dc001b9e94cc0eb2b2f83eef6ddb855a573cc59e58a7e392defc9cb1f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 14
alternates:
  md: https://mimirwiki.com/wiki/claude.md
  txt: https://mimirwiki.com/wiki/claude.txt
  json: https://mimirwiki.com/wiki/claude.json
  jsonld: https://mimirwiki.com/wiki/claude.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/claude
  ja: https://mimirwiki.com/ja/wiki/claude
  zh: https://mimirwiki.com/zh/wiki/claude
---

# Claude

> Claude is an AI assistant and large language model family developed by Anthropic, PBC, first launched on March 14, 2023. As of 2026-11-23, its latest models are Fable 5.2, Opus 5.5, Sonnet 5.5, and Haiku 5.5, each supporting a 1 million token context window. Claude is available through subscriptions, API, Claude Code, and cloud platforms.

Claude is an AI assistant and family of large language models developed by Anthropic, PBC, a Delaware Public Benefit Corporation headquartered in San Francisco, California. Anthropic publicly introduced Claude on March 14, 2023, through a chat interface and developer API, and later expanded the product line to include Claude Code for terminal and IDE software development, Claude Cowork for desktop workflows, and the Claude Platform API. As of 2026-11-23, the current model lineup consists of Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, and Claude Haiku 5.5, each offering a 1 million token context window and 128,000 maximum output tokens. Claude is available through Free, Pro, Max, Ultra, Team, Enterprise, and Education plans, through Anthropic's first-party API, and on Amazon Bedrock, Google Cloud, and Microsoft Foundry.

**Also known as:** Claude AI, Claude.ai, Claude Platform

## Key facts

- **Developer:** Anthropic, PBC (San Francisco, California) [1]
- **Initial public launch:** 2023-03-14 [3]
- **Latest models:** Claude Fable 5.2, Opus 5.5, Sonnet 5.5, and Haiku 5.5 (as of 2026-11-23) [4]
- **Context window:** 1 million tokens across all four latest models (128K max output) (as of 2026-11-23) [4]
- **Individual subscription plans:** Free ($0), Pro ($17/month billed annually or $20 monthly), Max ($100/month), Ultra ($200/month) (as of 2026-11-23) [6]

## Basic facts

- **Developer:** Anthropic, PBC (Delaware Public Benefit Corporation) [1]
- **Initial public launch:** 2023-03-14 (Claude and Claude Instant) [3]
- **Model lines:** Haiku, Sonnet, Opus, Fable, Mythos (as of 2026-11-23) [4]
- **Latest models:** Claude Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5 (as of 2026-11-23) [4]
- **Context window and max output:** 1,000,000 input tokens; 128,000 output tokens (latest models) (as of 2026-11-23) [4]
- **Knowledge and training cutoff:** June 2026 (Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5) (as of 2026-11-23) [4]
- **API base token pricing:** From $0.10/$0.50 (Haiku 5.5) to $8/$40 (Fable 5.2) per million input/output tokens (as of 2026-11-23) [5]
- **Platforms and clients:** Web, Desktop, iOS, Android, Claude Code, and Claude Platform API (as of 2026-11-23) [6]
- **Cloud platforms:** Amazon Bedrock, Claude Platform on AWS, Google Cloud, Microsoft Foundry (as of 2026-11-23) [4]
- **Alignment method:** Constitutional AI (supervised self-revision and RLAIF) [2]
- **Integration protocol:** Model Context Protocol (MCP), open-sourced 2024-11-25 [11]
- **Supported regions:** 185 listed countries and regions plus their territories (policy effective 2026-11-12) (as of 2026-11-23) [14]

## Claude overview, launch history, and product lineup

Claude is developed by [Anthropic](https://mimirwiki.com/wiki/anthropic), PBC, a Delaware Public Benefit Corporation with principal executive offices at 548 Market Street, PMB 90375, San Francisco, California 94104.[1] According to Amendment No. 3 to Form S-1 filed with [SEC EDGAR](https://mimirwiki.com/wiki/sec-edgar) on November 17, 2026, Anthropic is led by co-founders Dario Amodei (Chief Executive Officer) and Daniela Amodei (President).[1] Anthropic publicly introduced Claude on March 14, 2023, after a closed alpha with early partners including Notion, Quora (through Poe), and DuckDuckGo (for DuckAssist), along with Juni Learning, Robin AI, and AssemblyAI.[3]

At its March 2023 release, Claude was offered through a chat interface and a developer console API in two versions: Claude and a lighter, lower-cost option named Claude Instant.[3] Anthropic stated that the initial release handled tasks including summarization, search, collaborative writing, question answering, and coding.[3]

As of 2026-11-23, Anthropic's product overview lists a broader suite built around the Claude models, including the Claude chat application on web, desktop, iOS, and Android, Claude Code, Claude Cowork, Claude Duet (in research preview with a waitlist), Claude Platform, Claude Tag, and specialized offerings named Claude Security and Claude Science.[6][7] Documented capabilities across Claude applications include Artifacts, Design, Docs, Slides, Data, Sheets and Whiteboards (beta), Connectors, Plugins, Skills, Extensions, Voice mode, Web search, Research, task scheduling, Claude in Chrome, Claude for Google Workspace, and Claude for Microsoft 365.[6][7] In September 2026, Anthropic began merging Claude Cowork and Claude.ai into a single application so users can move between chat queries and multi-step desktop tasks within one conversation.[1]

## Claude model lineup and specifications

Claude models are organized by Anthropic into five model lines reported in the `line` field of the Models API (`GET /v1/models`): `haiku`, `sonnet`, `opus`, `fable`, and `mythos`.[4] As of 2026-11-23, Claude Platform Docs lists four models in the current lineup: Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, and Claude Haiku 5.5.[4] All four models accept text and image input, produce text output, and support multilingual processing, vision, tool use, and adaptive thinking.[4]

| Model | Claude API ID | Context window | Max output | Thinking and default effort | Knowledge cutoff | Earliest retirement |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | `claude-fable-5-2` | 1M tokens | 128K tokens | Adaptive (always on), high | June 2026 | November 9, 2027 |
| Claude Opus 5.5 | `claude-opus-5-5` | 1M tokens | 128K tokens | Adaptive (always on), medium | June 2026 | September 22, 2027 |
| Claude Sonnet 5.5 | `claude-sonnet-5-5` | 1M tokens | 128K tokens | Adaptive, high | June 2026 | September 28, 2027 |
| Claude Haiku 5.5 | `claude-haiku-5-5` | 1M tokens | 128K tokens | Adaptive, medium | June 2026 | October 7, 2027 |

In Claude Platform Docs, Anthropic designates Claude Fable 5.2 for demanding reasoning and long-horizon agentic work, Claude Opus 5.5 for general workloads and long-running agentic coding and knowledge work, Claude Sonnet 5.5 for combined speed and capability, and Claude Haiku 5.5 for high-volume, latency-sensitive tasks such as classification, extraction, and routing.[4] For all four models, both the reliable knowledge cutoff and the training data cutoff are listed as June 2026.[4]

As of 2026-11-23, Claude Platform Docs also lists additional and earlier models alongside the current four: Claude Mythos 5.2, Claude Fable 5.1 and 5, Claude Mythos 5.1 and 5, Claude Opus 5, 4.8, 4.7, 4.6, 4.5, 4.1, and 4, Claude Sonnet 5, 4.6, 4.5, and 4, and Claude Haiku 4.5.[4] Earlier models including Claude Opus 4.5, Claude Sonnet 4.5, Claude Sonnet 4, and Claude Haiku 4.5 have a 200,000-token context window and 64,000-token maximum output, while Claude Opus 4.1 and Claude Opus 4 have a 200,000-token context window and 32,000-token maximum output.[4]

Developers can inspect model specifications programmatically through the `GET /v1/models` endpoint, which filters by lifecycle stage (`active`, `deprecated`, or `retired`) and returns `max_input_tokens`, `max_tokens`, `line`, and a `capabilities` object covering settings such as `thinking.types.disabled`, `thinking.types.between_tools`, `server_tools` (web search and code execution), and programmatic tool calling.[4] Anthropic's Form S-1/A-3 also defines Claude capabilities including computer use (observing and interacting with graphical user interfaces through clicking, typing, and navigating applications) and interleaved thinking (inserting discrete reasoning steps between consecutive tool calls within a single response).[1]

## Claude Platform API pricing and developer features

Claude API usage on the Claude Platform is metered per million tokens (MTok) in US dollars across base input, base output, prompt caching, and batch processing rates.[5] As of 2026-11-23, Claude Platform Docs publishes the following rates for the four current models.[5]

| Model | Base input | Base output | Cache write (5m / 1h) | Cache hit | Batch input / output |
| --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | $8 / MTok | $40 / MTok | $10 / $16 per MTok | $0.20 / MTok | $4 / $20 per MTok |
| Claude Opus 5.5 | $4 / MTok | $20 / MTok | $5 / $8 per MTok | $0.20 / MTok | $2 / $10 per MTok |
| Claude Sonnet 5.5 | $2 / MTok | $10 / MTok | $2.50 / $4 per MTok | $0.10 / MTok | $1 / $5 per MTok |
| Claude Haiku 5.5 (prompts up to 100K tokens) | $0.10 / MTok | $0.50 / MTok | $0.125 / $0.20 per MTok | $0.01 / MTok | $0.05 / $0.25 per MTok |
| Claude Haiku 5.5 (prompts over 100K tokens) | $0.50 / MTok | $2.50 / MTok | $0.625 / $1 per MTok | $0.05 / MTok | $0.25 / $1.25 per MTok |

Prompt caching applies fixed multipliers to base input prices: 1.25x for 5-minute cache writes and 2x for 1-hour cache writes, with cache read multipliers of 0.025x on Fable 5.2, Mythos 5.2, Fable 5.1, and Mythos 5.1, 0.05x on Opus 5.5 and Sonnet 5.5, and 0.1x on all other models.[5] The Batch API provides a 50% discount on both input and output tokens for asynchronous requests.[5] Fast mode offers up to 2.5x higher output tokens per second at double standard pricing on supported models ($16/$80 per MTok for Fable 5.2 and Mythos 5.2, $8/$40 per MTok for Opus 5.5, and $10/$50 per MTok for Opus 5 and Opus 4.8) and cannot be combined with the Batch API.[5]

For Claude 4.6 and later models, selecting US-only inference through the `inference_geo: "us"` parameter applies a 1.1x multiplier to all token pricing categories on the first-party API, Claude Platform on AWS, Anthropic-managed Google Cloud deployments, and Azure US Data Zone Standard deployments in Microsoft Foundry.[5] Anthropic documents that Claude 4.7 and later models (along with Claude Mythos Preview) use a newer tokenizer that produces approximately 30% more tokens for the same text compared with Claude Sonnet 4.6 and earlier models.[5] Among additional models listed on 2026-11-23, base input and output prices per MTok are $8/$40 for Claude Mythos 5.2, $10/$50 for Fable 5.1, Fable 5, Mythos 5.1, and Mythos 5, $5/$25 for Opus 5 through Opus 4.5, $15/$75 for Opus 4.1 and Opus 4, $2/$10 for Sonnet 5, $3/$15 for Sonnet 4.6 through Sonnet 4, and $1/$5 for Haiku 4.5.[5]

In addition to token rates, `claude.com/pricing` lists separate charges for three Claude Platform features as of 2026-11-23: Managed Agents at $0.08 per session-hour of active runtime (plus standard token rates), Web search at $10 per 1,000 searches (excluding token usage), and sandboxed Python Code execution with 50 free hours per day per organization followed by $0.05 per hour per container.[6]

As of 2026-11-23, the Claude API enforces organization-level spend limits and rate limits measured in requests per minute (RPM), input tokens per minute (ITPM), and output tokens per minute (OTPM), returning HTTP 429 responses when exceeded.[12] Monthly spend caps by standard usage tier are $500 USD on Start, $1,000 USD on Build, and $200,000 USD on Scale, while new accounts may start in an Evaluation tier; default ITPM limits count only uncached `input_tokens` and `cache_creation_input_tokens` and exclude `cache_read_input_tokens`, and Managed Agents enforce 300 RPM on create endpoints and 1,200 RPM on read endpoints.[12] For firewall allowlisting as of 2026-11-23, Anthropic documents fixed inbound IP ranges of `160.79.104.0/23`, `153.61.224.0/22`, and IPv6 `2607:6bc0::/48`, and outbound IPv4 ranges of `160.79.104.0/21` and `153.61.208.0/20` for outbound requests such as MCP tool calls, web search, and web fetch.[13]

## Claude consumer, team, enterprise, and education plans

Claude is offered to individual users, teams, large organizations, and universities through subscription plans published on `claude.com/pricing`.[6] As of 2026-11-23, the pricing page lists four individual tiers (Free, Pro, Max, and Ultra), a Team tier with Standard and Premium seats, an Enterprise tier available through self-serve and sales-assisted options, and a university-wide Education plan.[6]

| Plan | Listed price (USD) | Billing terms | Documented allowances and features |
| --- | --- | --- | --- |
| Free | $0 | No charge | Limited 5-hour and weekly usage; Sonnet and Haiku models; web, desktop, iOS, and Android chat; Artifacts, Design, Slides, Docs, web search, code execution, Voice mode, up to 5 Projects |
| Pro | $17/month annual ($200 up front) or $20/month monthly | Monthly or annual | 1x baseline 5-hour and weekly usage; adds Opus access, Fable via usage credits, Claude Code, Claude Science, Claude Data, Sheets and Whiteboards (beta), Research, task scheduling, Claude in Chrome, Microsoft 365 and Outlook |
| Max | $100/month | Monthly | 5x Pro 5-hour and weekly usage; Fable up to 50% of weekly limits; $100/month in API credits; early feature access and priority access during high traffic |
| Ultra | $200/month | Monthly | No 5-hour limit for verified accounts; 10x Pro weekly usage; Fable up to 50% of weekly limits; $200/month in API credits; early feature access and priority access during high traffic |
| Team | Standard: $20/seat/month annual ($25 monthly); Premium: $100/seat/month annual ($125 monthly) | Monthly or annual (2 to 150 seats) | Mix-and-match seats; Premium offers 5x Standard usage and Fable up to 50% of weekly limits; adds Claude Cowork, Claude Tag, Enterprise search, project sharing, SSO, domain verification, central billing, usage analytics, up to $500/month pooled API credits |
| Enterprise | $20/seat/month base + usage at API rates | Annual (20-seat minimum) | Adds org and user spend limits, role-based access, SCIM, audit logs, Compliance API, custom data retention, domain capture, network-level access control, IP allowlisting, HIPAA-ready offering, inference hooks, Claude Security (beta) |

On individual plans (Free, Pro, Max, and Ultra), Anthropic lists model training as opt-out, while on Team and Enterprise plans customer content is excluded from model training by default.[6] All tiers list a context window of up to 1 million tokens depending on the model, and usage limits depend on model selection, chat length, and file size.[6]

Sales-assisted Enterprise plans add options absent from self-serve Enterprise, including AWS Marketplace availability, consultation, tiered incentives on committed spend, trials, customer success support at qualifying spend thresholds, and invoicing with net terms.[6] Anthropic also offers an Education plan for universities covering students, faculty, and staff at discounted rates, including an academic research and learning mode and dedicated API credits, with pricing not publicly listed.[6]

Under Anthropic's Supported Regions Policy effective November 12, 2026, Claude applications (Claude.ai, Claude Code, and Cowork), the Claude API, and Claude models offered via cloud platforms and authorized resellers are available only in 185 listed countries and regions along with their territories and dependencies.[14] The policy excludes access by individuals physically located in unlisted regions and by entities incorporated, headquartered, or majority-owned or controlled in unlisted regions.[14]

## Claude Code, Claude Cowork, and cloud platform availability

Claude Code is Anthropic's agentic coding tool, first made available as a research preview in February 2025.[1][8] According to Anthropic's Form S-1/A-3 and the official GitHub repository (`anthropics/claude-code`), Claude Code runs in the terminal, in IDEs, or via `@claude` mentions on GitHub, inspecting codebases, planning, writing, testing, and debugging code, and managing Git workflows through natural language commands in a persistent local or sandboxed cloud execution environment.[1][8] Anthropic's Form S-1/A-3 notes that NASA engineers used Claude Code to plan and write navigation commands for the Mars Perseverance rover.[1]

As of 2026-11-23, the public `anthropics/claude-code` repository on GitHub recorded 156.8k stars, 25.1k forks, and 1,110 commits.[8] Installation methods listed in the repository README as of 2026-11-23 include the shell script (`curl -fsSL https://claude.ai/install.sh | bash`) and Homebrew cask (`brew install --cask claude-code`) on macOS and Linux, and the PowerShell script (`irm https://claude.ai/install.ps1 | iex`) and WinGet (`winget install Anthropic.ClaudeCode`) on Windows, while installation via npm (`@anthropic-ai/claude-code`) is marked deprecated.[8] Extending this agentic architecture to desktop knowledge work, Anthropic released Claude Cowork as a research preview in January 2026 to read files, navigate applications, and execute multi-step workflows on a user's desktop, and began merging Claude Cowork with Claude.ai in September 2026.[1]

Outside Anthropic's first-party API, Claude models are distributed through major cloud platforms.[4][5] On Amazon Web Services, Claude models are available through Amazon Bedrock (which lists current releases including Claude Fable 5.2, Opus 5.5, Sonnet 5.5, and Haiku 5.5 and integrates with Amazon Bedrock AgentCore for autonomous agents running up to eight hours) and through Claude Platform on AWS.[4][5][9] On Google Cloud, Claude models are offered through Model Garden on the Gemini Enterprise Agent Platform in both Google-managed and Anthropic-managed deployments, covering Fable 5 through 5.2, Opus 4.5 through 5.5, Sonnet 4.5 through 5.5, and Haiku 4.5 and 5.5 as of 2026-11-23.[4][5][10] Claude models are also available on Azure through Microsoft Foundry.[4][5]

Cloud billing models vary by channel as of 2026-11-23.[5] On partner-operated platforms (Amazon Bedrock and Google-managed Claude Models on Google Cloud), the cloud provider invoices customers directly, and regional or multi-region endpoints include a 10% premium over global endpoints for Claude 4.5 and later models.[5] On Anthropic-operated marketplace platforms (Claude Platform on AWS via AWS Marketplace and Claude in Microsoft Foundry via Azure Marketplace), Anthropic rates token usage in US dollars at standard rates, converts the total into Claude Consumption Units (CCUs) at $0.01 USD per CCU, reports CCUs hourly, and bills monthly in arrears.[5]

## Claude training with Constitutional AI and Model Context Protocol support

Claude models are aligned using Constitutional AI, a training method described by Yuntao Bai and 50 co-authors at Anthropic in the December 15, 2022 arXiv paper "Constitutional AI: Harmlessness from AI Feedback."[2][9] Under this method, human oversight is supplied through a written list of rules or principles, and training takes place in two stages.[2] In the supervised learning stage, an initial model generates outputs, critiques and revises those outputs against the written principles, and is fine-tuned on the revised responses.[2] In the reinforcement learning stage, called Reinforcement Learning from AI Feedback (RLAIF), an AI model evaluates pairs of sampled responses to create a preference dataset, a preference model is trained on that dataset, and reinforcement learning uses that preference model as its reward signal.[2] Both stages can use chain-of-thought reasoning so that the assistant explains its objections when responding to harmful queries.[2]

In Anthropic's Form S-1/A-3 filed November 17, 2026, Constitutional AI is defined as training models against a set of written principles referred to as Claude's constitution, organized around four priorities: being broadly safe, broadly ethical, compliant with Anthropic's guidelines, and genuinely helpful.[1] Through this process, models evaluate, critique, and revise their own responses against auditable written principles.[1]

Claude also connects to external tools and data systems through the [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (MCP), an open standard created at Anthropic by David Soria Parra and Justin Spahr-Summers and open-sourced on November 25, 2024.[11] MCP defines a client-server architecture in which data sources expose access through MCP servers and AI applications act as MCP clients to maintain two-way connections.[11] At launch, Anthropic released the MCP specification and SDKs, added local MCP server support to the Claude Desktop applications across all Claude.ai plans, and published open-source pre-built MCP servers for systems including Google Drive, Slack, GitHub, Git, Postgres, and Puppeteer.[11] Anthropic's launch announcement named Block and Apollo as early adopters integrating MCP, along with developer tool companies Zed, Replit, Codeium, and Sourcegraph working with the protocol.[11]

## Frequently asked questions

### What are the latest Claude models as of 2026-11-23?

As of 2026-11-23, Claude Platform Docs lists four models in the current lineup: Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, and Claude Haiku 5.5. All four models provide a 1 million token context window, up to 128,000 output tokens, adaptive thinking, vision, tool use, and a June 2026 knowledge cutoff. [4]

### How much do Claude subscription plans cost?

As of 2026-11-23, Claude offers four individual tiers: Free ($0), Pro ($17 per month billed annually at $200 up front, or $20 billed monthly), Max ($100 per month), and Ultra ($200 per month). Team plans for 2 to 150 seats list Standard seats at $20 per seat per month annually ($25 monthly) and Premium seats at $100 per seat per month annually ($125 monthly), while Enterprise starts at $20 per seat per month billed annually with a 20-seat minimum plus usage billed at API rates. [6]

### What are the Claude API token prices?

As of 2026-11-23, base Claude API pricing per million input and output tokens is $8 and $40 for Claude Fable 5.2, $4 and $20 for Claude Opus 5.5, and $2 and $10 for Claude Sonnet 5.5. Claude Haiku 5.5 is priced at $0.10 input and $0.50 output per million tokens for prompts up to 100,000 tokens, and $0.50 input and $2.50 output for prompts over 100,000 tokens. The Batch API applies a 50% discount to input and output token rates. [5]

### What is Claude Code and which plans include it?

Claude Code is Anthropic's agentic coding tool, released as a research preview in February 2025, that runs in a terminal, IDE, or through @claude mentions on GitHub to plan, write, test, and debug code and manage Git workflows. As of 2026-11-23, Claude Code is included in the Pro, Max, Ultra, Team, and Enterprise plans, and is not included in the Free plan. [1][6][8]

### Which cloud platforms offer Claude models?

As of 2026-11-23, Claude models are available on Amazon Web Services through Amazon Bedrock and Claude Platform on AWS, on Google Cloud through Model Garden on the Gemini Enterprise Agent Platform in Google-managed and Anthropic-managed deployments, and on Azure through Microsoft Foundry. On Amazon Bedrock and Google-managed Google Cloud deployments, regional or multi-region endpoints carry a 10% premium over global endpoints for Claude 4.5 and later models. [4][5][9][10]

### How do Constitutional AI and the Model Context Protocol relate to Claude?

Constitutional AI, introduced by Anthropic researchers in December 2022, trains Claude models to evaluate, critique, and revise their own outputs against a written set of principles through supervised learning and Reinforcement Learning from AI Feedback (RLAIF). The Model Context Protocol (MCP), open-sourced by Anthropic on November 25, 2024, is an open client-server standard that connects Claude applications, including Claude Desktop, to external data sources and tools. [1][2][11]

## Quotable sentences

- Anthropic, PBC publicly introduced Claude and Claude Instant on March 14, 2023, through a chat interface and developer API. [3]
- As of 2026-11-23, the latest Claude model lineup consists of Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, and Claude Haiku 5.5, each with a 1 million token context window and 128,000 maximum output tokens. [4]
- As of 2026-11-23, standard Claude API pricing per million input and output tokens is $8 and $40 for Fable 5.2, $4 and $20 for Opus 5.5, $2 and $10 for Sonnet 5.5, and $0.10 and $0.50 for Haiku 5.5 prompts up to 100,000 tokens. [5]
- As of 2026-11-23, Claude individual subscription plans are priced at $0 for Free, $17 per month billed annually ($20 monthly) for Pro, $100 per month for Max, and $200 per month for Ultra. [6]
- Anthropic released Claude Code as a research preview in February 2025 and Claude Cowork as a research preview in January 2026. [1]
- As of 2026-11-23, Claude models are available on Amazon Bedrock, Claude Platform on AWS, Google Cloud, and Microsoft Foundry. [4][5][9][10]
- Anthropic researchers submitted the Constitutional AI paper describing supervised self-revision and Reinforcement Learning from AI Feedback (RLAIF) to arXiv on December 15, 2022. [2]
- Anthropic open-sourced the Model Context Protocol (MCP) specification, SDKs, and local Claude Desktop server support on November 25, 2024. [11]

## Timeline

- 2022-12-15: Yuntao Bai and 50 co-authors at Anthropic submit the paper "Constitutional AI: Harmlessness from AI Feedback" to arXiv. [2]
- 2023-03-14: Anthropic publicly introduces Claude and Claude Instant through a chat interface and developer API following a closed alpha with early partners. [3]
- 2024-11-25: Anthropic open-sources the Model Context Protocol (MCP), releasing the specification, SDKs, pre-built servers, and local MCP support in Claude Desktop. [11]
- 2025-02: Anthropic releases the coding agent Claude Code as a research preview. [1]
- 2026-01: Anthropic releases Claude Cowork for multi-step desktop workflows as a research preview. [1]
- 2026-09: Anthropic begins merging Claude Cowork and Claude.ai into a unified application. [1]
- 2026-11-17: Anthropic, PBC files Amendment No. 3 to its Form S-1 registration statement with the U.S. Securities and Exchange Commission. [1]

## Sources

1. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). published 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (checked 2026-11-23; tier 1: government or public registry)
2. [2212.08073] Constitutional AI: Harmlessness from AI Feedback. arXiv (Bai et al., Anthropic). published 2022-12-15. https://arxiv.org/abs/2212.08073 (checked 2026-11-23; tier 2: academic or news)
3. Introducing Claude \ Anthropic. Anthropic. published 2023-03-14. https://www.anthropic.com/news/introducing-claude (checked 2026-11-23; tier 3: official site)
4. Models overview - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/models/overview (checked 2026-11-23; tier 3: official site)
5. Pricing - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/about-claude/pricing (checked 2026-11-23; tier 3: official site)
6. Plans & pricing | Claude by Anthropic. Anthropic. https://claude.com/pricing (checked 2026-11-23; tier 3: official site)
7. Claude | The AI assistant for work. Anthropic. https://claude.com/product/overview (checked 2026-11-23; tier 3: official site)
8. GitHub - anthropics/claude-code: Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands. · GitHub. Anthropic (GitHub). https://github.com/anthropics/claude-code (checked 2026-11-23; tier 3: official site)
9. Claude by Anthropic - Models in Amazon Bedrock - AWS. Amazon Web Services. https://aws.amazon.com/bedrock/anthropic/ (checked 2026-11-23; tier 3: official site)
10. Anthropic's Claude on Google Cloud models | Gemini Enterprise Agent Platform | Google Cloud Documentation. Google Cloud. https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/partner-models/claude (checked 2026-11-23; tier 3: official site)
11. Introducing the Model Context Protocol \ Anthropic. Anthropic. published 2024-11-25. https://www.anthropic.com/news/model-context-protocol (checked 2026-11-23; tier 3: official site)
12. Rate limits - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/rate-limits (checked 2026-11-23; tier 3: official site)
13. IP addresses - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/ip-addresses (checked 2026-11-23; tier 3: official site)
14. Supported Regions Policy \ Anthropic. Anthropic. published 2026-11-12. https://www.anthropic.com/supported-countries (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Claude." Version 569e801d, 2026-11-23. https://mimirwiki.com/wiki/claude
