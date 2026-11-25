---
title: "Perplexity"
subtitle: "AI-powered answer engine and multi-provider developer API platform offering the Agent, Orchestrator, Search, Context, Monitor, Embeddings, and Decisions APIs"
canonical_url: https://mimirwiki.com/wiki/perplexity
language: en
page_class: entity
revision_sha256: e44173829a94ff6c41eb449ec9a028ecf23f90465cb40f1b79f04e970ff235cd
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/perplexity.md
  txt: https://mimirwiki.com/wiki/perplexity.txt
  json: https://mimirwiki.com/wiki/perplexity.json
  jsonld: https://mimirwiki.com/wiki/perplexity.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/perplexity
  ja: https://mimirwiki.com/ja/wiki/perplexity
  zh: https://mimirwiki.com/zh/wiki/perplexity
  es: https://mimirwiki.com/es/wiki/perplexity
---

# Perplexity

> Perplexity operates a web-grounded AI answer engine and a seven-service developer API platform comprising the Agent API (`POST https://api.perplexity.ai/v1/agent`), Orchestrator API, Search API ($5.00 per 1,000 standard requests or $1.00 per 1,000 Fast Search requests, with up to 5 queries per request), Context API, Monitor API ($1.00 per 1,000 runs or fetched URLs), Embeddings API, and Decisions API. After ending legacy Sonar Chat Completions support on September 27, 2026, Perplexity transitioned developers to the Open Responses-compatible Agent API, which provides unified access to OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, NVIDIA, and Sonar models with built-in web, finance, and people search, code sandboxes, and MCP tools.

Perplexity is an artificial intelligence research and answer-engine platform that combines real-time web indexing with large language models to deliver citation-grounded answers, autonomous agentic research, and developer APIs. Following the sunset of legacy Sonar Chat Completions support on September 27, 2026, Perplexity's developer platform (`docs.perplexity.ai`) is organized around seven modular services: the multi-provider Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API, and Decisions API, alongside the `pplx` command-line interface and official Model Context Protocol (MCP) servers.

**Also known as:** Perplexity, Agent API, Orchestrator API, Search API, PerplexityBot, Answer Engine

## Key facts

- **Core API Platform Suite:** Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API, Decisions API [7]
- **Sonar Deprecation Milestone:** September 27, 2026 (Sonar Chat Completions support ended; synchronous calls reformulated to Agent API) [5]
- **Agent API Capabilities:** Open Responses standard, 5 effort tiers (fast to xhigh), multi-provider routing, sandboxes, Finance & People search [5]
- **Search & Monitor API Pricing:** Search API: $5.00/1K requests ($1.00/1K Fast Search, up to 5 queries/req); Monitor API: $1.00/1K runs or URLs [4]
- **Web Crawlers & IP Feeds:** PerplexityBot/1.0 (21 IPv4 prefixes) and Perplexity-User/1.0 (10 IPv4 prefixes); neither trains foundation models [1]

## Basic facts

- **Platform Name:** Perplexity (Perplexity API Platform & Answer Engine) [7]
- **Primary Agent Endpoint:** POST https://api.perplexity.ai/v1/agent [6]
- **API Standard Compatibility:** Open Responses standard (Agent API); OpenAI & Anthropic request formats (Orchestrator API) [5]
- **Supported Model Families:** Perplexity Sonar, OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, NVIDIA [5]
- **Agent Effort Presets:** fast (default), low, medium, high, xhigh [5]
- **Search API Pricing:** $5.00 / 1,000 requests (standard web); $1.00 / 1,000 requests (search_type: "fast") [4]
- **Monitor API Pricing:** $0.001 per succeeded Search run ($1/1K); $0.001 per counted fetched Page URL ($1/1K) [4]
- **Legacy Sonar Sunset Date:** September 27, 2026 (Sonar Chat Completions support ended) [5]
- **CLI & MCP Integrations:** Perplexity CLI (pplx), Perplexity API MCP Server, Perplexity Computer MCP Server, Decider for Mac [7]
- **Official Web Crawlers:** PerplexityBot/1.0 (perplexitybot.json) & Perplexity-User/1.0 (perplexity-user.json) [1]

## Seven-Pillar Perplexity API Platform Architecture

By late 2026, Perplexity evolved from a single search-augmented chat endpoint into a modular seven-API developer platform (`docs.perplexity.ai`) accompanied by official Python and TypeScript SDKs (`perplexity` and `@perplexity-ai/perplexity_ai`), the `pplx` command-line interface (Perplexity CLI), the Perplexity API MCP Server, and the Perplexity Computer MCP Server:[5][6][7]

1. **Agent API (`POST https://api.perplexity.ai/v1/agent`)**: A unified, Open Responses-compatible multi-provider agent interface that executes an internal reasoning-and-tool loop, returning a typed `output` array containing structured `search_results` items and cited `message` items.[5][6] 2. **Orchestrator API**: A multi-provider routing gateway allowing developers to call Anthropic, OpenAI, Google, xAI, and open-weight models using a single Perplexity API key in either the OpenAI or Anthropic request format, supporting automatic model routing (`perplexity/auto`), deployment failover, cross-turn reasoning preservation, and prompt caching.[7] 3. **Search API (`POST /search`)**: A pure retrieval API returning ranked web results as JSON with extracted page text in each result's `snippet`, without invoking a generative language model or charging token fees.[4][7] 4. **Context API**: Extracts clean Markdown, HTML, outbound links, query-relevant highlights, and freshness/criteria scores from known URLs.[7] 5. **Monitor API**: Runs scheduled or event-driven Search monitors and Page URL monitors to track web changes over time.[4][7] 6. **Embeddings API**: Generates vector representations including Standard Embeddings, Contextualized Embeddings, and Contextualized Embeddings v2.[4][7] 7. **Decisions API**: Produces calibrated probability estimates for forecasting and decision-making workloads (paired with the Decider for Mac client).[4][7]

## Transition from Sonar Chat Completions to the Agent API

Perplexity officially ended support for its legacy Sonar Chat Completions endpoint (`POST https://api.perplexity.ai/v1/sonar`) on September 27, 2026.[5] To preserve backward compatibility for existing production deployments, synchronous and streaming Sonar requests continue to function by being automatically reformulated on the backend into Agent API requests on a model-by-model basis, whereas legacy asynchronous Sonar requests are no longer reformulated or supported and must migrate to Agent API background mode.[5]

Unlike Sonar Chat Completions, which accepted a `messages` array restricted to Perplexity's Sonar models and returned an untyped `choices` array, the Agent API accepts an `input` payload and conforms to the portable Open Responses specification.[5] Through a single Perplexity API key, developers can select models across eight model families: Perplexity's own Sonar models, OpenAI (such as `openai/gpt-5.6-luna`), Anthropic, Google, xAI, Z.AI, Moonshot AI, and NVIDIA, with configurable model fallback chains.[4][5]

The Agent API includes research-tuned `effort` presets (`fast`, `low`, `medium`, `high`, and `xhigh`) and reusable versioned Profiles that pre-configure loop bounds, token budgets, and built-in tools:[5][7]

- **Search as Code & Multi-Source Grounding**: Built-in Web Search, URL fetching, Finance Search, and People Search.[5]
- **Code Execution Sandbox**: An isolated container sandbox that executes generated code to compute exact mathematical results, analyze data, and return generated files within a single API request.[5][7]
- **MCP & Custom Functions**: Native client support for external Model Context Protocol (MCP) servers alongside caller-defined custom function tools.[5]

## Search, Monitor, and Agent API Pricing Mechanics

Perplexity operates a pay-as-you-go billing model across all APIs with no mandatory monthly subscription.[6] On the Agent and Orchestrator APIs, token costs are billed transparently at published per-model rates alongside separate per-invocation or container-time tool charges (for example, code sandboxes are billed per started 20-minute block of container execution time plus any SDK web searches executed inside the sandbox, while certain built-in tool invocations are billed at $1.00 per 1,000 invocations).[4][6]

For retrieval and monitoring workloads, Perplexity bills strictly by request or run unit with zero token charges:[4]

| API Service | Mode / Unit | Price per 1,000 Units | Per-Unit Cost & Billing Rules |
| --- | --- | --- | --- |
| Search API | Standard Web Search (`POST /search`) | $5.00 / 1K requests | $0.005 per successful request; a single request can batch an array of up to 5 queries (up to 20 results) as 1 billing unit |
| Search API | Fast Search (`search_type: "fast"`) | $1.00 / 1K requests | $0.001 per successful request (lower-latency retrieval; up to 5 queries per request counted as 1 billing unit) |
| Monitor API | Search Monitor Run | $1.00 / 1K runs | $0.001 per succeeded Search run, regardless of the number of searches or results inside the run |
| Monitor API | Page Monitor Fetch | $1.00 / 1K URLs | $0.001 per counted fetched URL in a succeeded Page run |

On the Search API, invalid requests, rate-limited (`429`) requests, and upstream errors are never billed, while a valid HTTP 200 response is billed as one unit even if a query matches zero results.[4] On the Monitor API, failed and skipped runs incur no charge.[4]

## Perplexity Crawlers (PerplexityBot and Perplexity-User) and WAF Rules

Perplexity collects and verifies web information through two distinct HTTP user agents, neither of which is used to crawl content for training AI foundation models:[1]

1. **`PerplexityBot`**: The automated indexing crawler used to surface and link websites in Perplexity search results.[1] It respects `robots.txt` directives (reflecting changes within approximately 24 hours), sends the user-agent string `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)`, and publishes its official IPv4 allowlist at `https://www.perplexity.ai/perplexitybot.json`.[1] As of the `2026-11-18T16:30:18` feed update, `perplexitybot.json` lists 21 `/32` IPv4 prefixes across `107.20.236.150/32`, `18.210.92.235/32`, `18.97.1.228/32`, `18.97.9.96/32` through `18.97.9.103/32`, `3.222.232.239/32`, `3.224.62.45/32`, and `3.41.218.160/32` through `3.41.218.167/32`.[2] 2. **`Perplexity-User`**: The live user-action fetcher triggered when a user asks Perplexity a question that requires visiting a specific web page to answer and cite.[1] Because fetches are initiated directly by user requests, `Perplexity-User` generally ignores `robots.txt` rules, identifies itself as `Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)`, and publishes its IPv4 allowlist at `https://www.perplexity.ai/perplexity-user.json` (which as of `2026-10-28T16:48:51` lists 10 `/32` IPv4 prefixes: `18.97.43.80/32` through `18.97.43.87/32`, `34.193.163.52/32`, and `44.208.221.197/32`).[1][3]

For site operators using Web Application Firewalls (WAF) such as Cloudflare WAF or AWS WAF, Perplexity recommends combining `http.user_agent` substring matching with source IP verification against the live JSON endpoints (`perplexitybot.json` and `perplexity-user.json`) in a high-priority `Skip` or `Allow` rule, noting that Cloudflare's free Bot Fight Mode cannot be bypassed via custom WAF rules and may still challenge Perplexity bots if left enabled.[1]

## Frequently asked questions

### What happened to Perplexity's Sonar Chat Completions API?

Support for Sonar Chat Completions ended on September 27, 2026, and it was superseded by the Perplexity Agent API (POST https://api.perplexity.ai/v1/agent). Existing synchronous and streaming Sonar requests continue to work because Perplexity automatically reformulates them on the backend into Agent API calls, but asynchronous Sonar requests are no longer supported and must be migrated to Agent API background mode. [5]

### How is Perplexity's Search API priced and billed?

The Search API returns ranked web results with extracted text snippets as JSON without invoking an LLM or charging token fees. Standard Search costs $5.00 per 1,000 successful POST /search requests ($0.005 per request), and Fast Search (search_type: "fast") costs $1.00 per 1,000 successful requests ($0.001 per request). A single POST /search call can include an array of up to five queries and is still billed as just one billing unit. Invalid, rate-limited, or failed requests are not billed. [4]

### What is the difference between Perplexity's Agent API and Orchestrator API?

The Agent API follows the Open Responses specification and runs a complete multi-step agentic loop with built-in tools (web search, Finance Search, People Search, URL fetching, 20-minute code execution sandboxes, and MCP servers) and pre-tuned effort levels (fast, low, medium, high, xhigh), returning a cited answer and typed search results. The Orchestrator API is a multi-provider model gateway that lets developers call Anthropic, OpenAI, Google, xAI, and open-weight models in standard OpenAI or Anthropic request formats with perplexity/auto routing, deployment failover, and prompt caching. [7]

### What is the difference between PerplexityBot and Perplexity-User in robots.txt?

PerplexityBot/1.0 is Perplexity's automated search crawler that indexes websites so they can appear in Perplexity search results; it obeys robots.txt rules (updating within 24 hours) and uses IPs published at perplexity.ai/perplexitybot.json. Perplexity-User/1.0 fetches specific pages on demand when a live user asks Perplexity a question; because it acts on a user's direct request, it generally ignores robots.txt and uses IPs at perplexity.ai/perplexity-user.json. Neither crawler collects data to train AI foundation models. [1]

## Quotable sentences

- Perplexity ended support for legacy Sonar Chat Completions on September 27, 2026, automatically reformulating synchronous and streaming Sonar calls into Agent API requests while discontinuing asynchronous Sonar requests in favor of background mode. [5]
- The Perplexity API Platform consists of seven core APIs: Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API, and Decisions API, alongside the pplx CLI and MCP servers. [4][7]
- The Agent API (POST https://api.perplexity.ai/v1/agent) follows the Open Responses standard, offers five effort levels (fast, low, medium, high, xhigh), and routes across Sonar, OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, and NVIDIA models with built-in web, finance, and people search, code sandboxes, and MCP integration. [5][6]
- Perplexity's Search API charges $5.00 per 1,000 successful standard requests or $1.00 per 1,000 Fast Search requests with no token fees, counting a request containing an array of up to five queries as a single billing unit. [4]
- Perplexity operates two web agents, PerplexityBot/1.0 (21 published IPv4 /32 prefixes as of November 18, 2026) for search indexing and Perplexity-User/1.0 (10 published IPv4 /32 prefixes as of October 28, 2026) for user-initiated fetches, and states that neither bot crawls content to train AI foundation models. [1][2][3]

## Timeline

- 2026-09-27: Perplexity ends official support for legacy Sonar Chat Completions, transitioning developers to the Open Responses-based Agent API. [5]
- 2026-10-28: Perplexity updates the published IPv4 allowlist feed for Perplexity-User (perplexity-user.json) with 10 /32 prefixes. [3]
- 2026-11-18: Perplexity updates the published IPv4 allowlist feed for PerplexityBot (perplexitybot.json) with 21 /32 prefixes. [2]

## Sources

1. Perplexity Crawlers - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/resources/perplexity-crawlers (checked 2026-11-23; tier 3: official site)
2. PerplexityBot Published IPv4 Prefixes (perplexitybot.json). Perplexity. published 2026-11-18. https://www.perplexity.ai/perplexitybot.json (checked 2026-11-23; tier 3: official site)
3. Perplexity-User Published IPv4 Prefixes (perplexity-user.json). Perplexity. published 2026-10-28. https://www.perplexity.ai/perplexity-user.json (checked 2026-11-23; tier 3: official site)
4. Pricing - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/getting-started/pricing (checked 2026-11-23; tier 3: official site)
5. Migrate from Sonar to the Agent API - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/migrate-from-sonar/overview (checked 2026-11-23; tier 3: official site)
6. Agent API Quickstart - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/quickstart (checked 2026-11-23; tier 3: official site)
7. Perplexity API Documentation Index (llms.txt). Perplexity. https://docs.perplexity.ai/llms.txt (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Perplexity." Version e4417382, 2026-11-23. https://mimirwiki.com/wiki/perplexity
