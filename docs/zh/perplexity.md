---
title: "Perplexity"
subtitle: "AI 驱动的回答引擎与多提供商开发者 API 平台，提供 Agent、Orchestrator、Search、Context、Monitor、Embeddings 和 Decisions API"
canonical_url: https://mimirwiki.com/zh/wiki/perplexity
language: zh
page_class: entity
revision_sha256: fd90e6ee60ee8de624e4083bdaf87fed92e6ee432ac3d3e8b4f692b822f01d35
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/zh/wiki/perplexity.md
  txt: https://mimirwiki.com/zh/wiki/perplexity.txt
  json: https://mimirwiki.com/zh/wiki/perplexity.json
  jsonld: https://mimirwiki.com/zh/wiki/perplexity.jsonld
translations:
  en: https://mimirwiki.com/wiki/perplexity
  ko: https://mimirwiki.com/ko/wiki/perplexity
  ja: https://mimirwiki.com/ja/wiki/perplexity
  es: https://mimirwiki.com/es/wiki/perplexity
---

# Perplexity

> Perplexity 运营基于实时网页检索的 AI 回答引擎以及包含七项服务的开发者 API 平台，涵盖 Agent API（`POST https://api.perplexity.ai/v1/agent`）、Orchestrator API、Search API（每 1,000 次标准请求 5.00 美元，或每 1,000 次 Fast Search 请求 1.00 美元，每次请求最多可包含 5 条查询）、Context API、Monitor API（每 1,000 次运行或抓取 URL 1.00 美元）、Embeddings API 和 Decisions API。在 2026 年 9 月 27 日结束对旧版 Sonar Chat Completions 的支持后，Perplexity 引导开发者迁移至兼容 Open Responses 标准的 Agent API。该接口统一支持 OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA 与 Sonar 模型，并内置网页、金融和人物搜索、代码沙箱以及 MCP 工具。

Perplexity 是一个人工智能研究与回答引擎平台，将实时网页索引与大语言模型相结合，提供附带引用的回答、自主智能体研究以及开发者 API。在 2026 年 9 月 27 日停止对旧版 Sonar Chat Completions 的支持后，Perplexity 的开发者平台（`docs.perplexity.ai`）围绕七项模块化服务构建：多提供商 Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API 和 Decisions API，同时配套提供 `pplx` 命令行界面及官方 Model Context Protocol（MCP）服务器。

**别名:** Perplexity, Agent API, Orchestrator API, Search API, PerplexityBot, 回答引擎

## 关键事实

- **核心 API 平台套件:** Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API、Decisions API [7]
- **Sonar 弃用里程碑:** 2026 年 9 月 27 日（Sonar Chat Completions 停止支持；同步调用自动重构为 Agent API 请求） [5]
- **Agent API 核心能力:** Open Responses 标准、5 级 effort 预设（fast 至 xhigh）、多提供商路由、代码沙箱、Finance Search 与 People Search [5]
- **Search 与 Monitor API 定价:** Search API：每 1,000 次请求 $5.00（Fast Search 为每 1,000 次 $1.00，单次请求最多 5 条查询）；Monitor API：每 1,000 次运行或 URL $1.00 [4]
- **网页爬虫与 IP 列表:** PerplexityBot/1.0（21 个 IPv4 前缀）与 Perplexity-User/1.0（10 个 IPv4 前缀）；两者均不用于基础模型训练 [1]

## 事实摘要

- **平台名称:** Perplexity（Perplexity API Platform & Answer Engine） [7]
- **主要 Agent 端点:** POST https://api.perplexity.ai/v1/agent [6]
- **API 标准兼容性:** Open Responses 标准（Agent API）；OpenAI 与 Anthropic 请求格式（Orchestrator API） [5]
- **支持的模型系列:** Perplexity Sonar、OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA [5]
- **Agent Effort 预设:** fast（默认）、low、medium、high、xhigh [5]
- **Search API 定价:** $5.00 / 1,000 次请求（标准网页搜索）；$1.00 / 1,000 次请求（search_type: "fast"） [4]
- **Monitor API 定价:** 每次成功 Search 运行 $0.001（$1/1K）；每个计费抓取 Page URL $0.001（$1/1K） [4]
- **旧版 Sonar 停服日期:** 2026 年 9 月 27 日（Sonar Chat Completions 停止支持） [5]
- **CLI 与 MCP 集成:** Perplexity CLI（pplx）、Perplexity API MCP Server、Perplexity Computer MCP Server、Decider for Mac [7]
- **官方网页爬虫:** PerplexityBot/1.0（perplexitybot.json）与 Perplexity-User/1.0（perplexity-user.json） [1]

## Perplexity 七大支柱 API 平台架构

截至 2026 年底，Perplexity 已从单一的搜索增强聊天端点演进为模块化的七 API 开发者平台（`docs.perplexity.ai`），并配套提供官方 Python 与 TypeScript SDK（`perplexity` 和 `@perplexity-ai/perplexity_ai`）、`pplx` 命令行界面（Perplexity CLI）、Perplexity API MCP Server 以及 Perplexity Computer MCP Server：[5][6][7]

1. **Agent API（`POST https://api.perplexity.ai/v1/agent`）**：兼容 Open Responses 标准的统一多提供商智能体接口，在内部执行推理与工具调用循环，返回包含结构化 `search_results` 项与带引用 `message` 项的类型化 `output` 数组。[5][6] 2. **Orchestrator API**：多提供商路由网关，允许开发者使用单个 Perplexity API 密钥，以 OpenAI 或 Anthropic 请求格式调用 Anthropic、OpenAI、Google、xAI 及开放权重模型，支持自动模型路由（`perplexity/auto`）、部署故障转移、跨轮次推理状态保留以及提示词缓存。[7] 3. **Search API（`POST /search`）**：纯检索 API，以 JSON 格式返回按相关性排序的网页结果，并在每条结果的 `snippet` 字段中提供提取的页面文本，不调用生成式语言模型，也不收取 Token 费用。[4][7] 4. **Context API**：从已知 URL 中提取整洁的 Markdown、HTML、出站链接、与查询相关的高亮片段以及时效性或自定义标准评分。[7] 5. **Monitor API**：按计划或事件驱动方式运行 Search 监控器与 Page URL 监控器，持续追踪网页内容随时间的变化。[4][7] 6. **Embeddings API**：生成向量表示，涵盖 Standard Embeddings、Contextualized Embeddings 以及 Contextualized Embeddings v2。[4][7] 7. **Decisions API**：为预测与决策类工作负载生成经过校准的概率估计值（配套提供 Decider for Mac 客户端）。[4][7]

## 从 Sonar Chat Completions 向 Agent API 过渡

Perplexity 于 2026 年 9 月 27 日正式停止对旧版 Sonar Chat Completions 端点（`POST https://api.perplexity.ai/v1/sonar`）的支持。[5] 为保障现有生产部署的向后兼容性，同步和流式 Sonar 请求会在后端按模型逐一自动重构为 Agent API 请求以继续运行；而旧版异步 Sonar 请求不再获得重构或支持，必须迁移至 Agent API 的后台模式。[5]

与仅接受 `messages` 数组、局限于 Perplexity 自研 Sonar 模型并返回无类型 `choices` 数组的 Sonar Chat Completions 不同，Agent API 接受 `input` 负载并遵循可移植的 Open Responses 规范。[5] 通过单个 Perplexity API 密钥，开发者可在八大模型系列中自由选择模型：Perplexity 自研 Sonar 模型、OpenAI（例如 `openai/gpt-5.6-luna`）、Anthropic、Google、xAI、Z.AI、Moonshot AI 与 NVIDIA，并可配置模型回退链。[4][5]

Agent API 提供面向研究任务调优的 `effort` 预设（`fast`、`low`、`medium`、`high` 和 `xhigh`）以及可复用、可版本化的 Profiles，用于预先配置循环上限、Token 预算与内置工具：[5][7]

- **Search as Code 与多源检索增强**：内置网页搜索、URL 抓取、Finance Search 和 People Search。[5]
- **代码执行沙箱**：在隔离的容器沙箱中执行生成的代码，在单次 API 请求内完成精确数学计算、数据分析并返回生成的文件。[5][7]
- **MCP 与自定义函数**：原生支持作为客户端连接外部 Model Context Protocol（MCP）服务器，同时支持调用方自定义函数工具。[5]

## Search、Monitor 与 Agent API 定价与计费机制

Perplexity 在所有 API 上均采用按量付费（pay-as-you-go）计费模式，无强制月度订阅。[6] 在 Agent API 与 Orchestrator API 上，Token 费用按公开的各模型单价透明计费，同时另行收取按调用次数或容器运行时长计算的工具费用（例如，代码沙箱按已启动的每 20 分钟容器执行区块加上沙箱内执行的 SDK 网页搜索次数计费，部分内置工具调用按每 1,000 次调用 1.00 美元计费）。[4][6]

对于检索与监控类工作负载，Perplexity 严格按请求或运行单位计费，不收取任何 Token 费用：[4]

| API 服务 | 模式 / 计费单位 | 每 1,000 单位价格 | 单价与计费规则 |
| --- | --- | --- | --- |
| Search API | 标准网页搜索（`POST /search`） | $5.00 / 1K 次请求 | 每次成功请求 $0.005；单次请求可批量提交最多 5 条查询数组（最多 20 条结果），仅计为 1 个计费单位 |
| Search API | Fast Search（`search_type: "fast"`） | $1.00 / 1K 次请求 | 每次成功请求 $0.001（更低延迟的检索；每次请求最多 5 条查询仍计为 1 个计费单位） |
| Monitor API | Search Monitor 运行 | $1.00 / 1K 次运行 | 每次成功的 Search 运行 $0.001，与单次运行内的搜索次数或结果数量无关 |
| Monitor API | Page Monitor 抓取 | $1.00 / 1K 个 URL | 每次成功的 Page 运行中，每个计费抓取 URL $0.001 |

在 Search API 中，无效请求、触发限流（`429`）的请求以及上游错误均不计费；但即便查询匹配到 0 条结果，有效的 HTTP 200 响应仍会按 1 个单位计费。[4] 在 Monitor API 中，失败和跳过的运行均不产生费用。[4]

## Perplexity 爬虫（PerplexityBot 与 Perplexity-User）及 WAF 规则

Perplexity 通过两种不同的 HTTP 用户代理采集并验证网页信息，两者均不用于抓取内容以训练 AI 基础模型：[1]

1. **`PerplexityBot`**：用于在 Perplexity 搜索结果中展示和链接网站的自动索引爬虫。[1] 该爬虫遵守 `robots.txt` 指令（变更大约在 24 小时内生效），发送的用户代理字符串为 `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)`，并在 `https://www.perplexity.ai/perplexitybot.json` 发布官方 IPv4 白名单。[1] 截至 `2026-11-18T16:30:18` 的列表更新，`perplexitybot.json` 共列出了 21 个 `/32` IPv4 前缀，包括 `107.20.236.150/32`、`18.210.92.235/32`、`18.97.1.228/32`、`18.97.9.96/32` 至 `18.97.9.103/32`、`3.222.232.239/32`、`3.224.62.45/32` 以及 `3.41.218.160/32` 至 `3.41.218.167/32`。[2] 2. **`Perplexity-User`**：当用户向 Perplexity 提问并需要访问特定网页以生成回答和引用时触发的实时用户操作抓取器。[1] 由于抓取由用户请求直接发起，`Perplexity-User` 通常会忽略 `robots.txt` 规则，其用户代理标识为 `Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)`，官方 IPv4 白名单发布于 `https://www.perplexity.ai/perplexity-user.json`（截至 `2026-10-28T16:48:51` 共列出 10 个 `/32` IPv4 前缀：`18.97.43.80/32` 至 `18.97.43.87/32`、`34.193.163.52/32` 以及 `44.208.221.197/32`）。[1][3]

对于使用 Cloudflare WAF 或 AWS WAF 等 Web 应用防火墙（WAF）的站点运维人员，Perplexity 建议在高优先级的 `Skip` 或 `Allow` 规则中，将 `http.user_agent` 子串匹配与基于实时 JSON 端点（`perplexitybot.json` 和 `perplexity-user.json`）的源 IP 验证结合使用，并特别指出 Cloudflare 免费版的 Bot Fight Mode 无法通过自定义 WAF 规则绕过，如果保持开启状态，仍可能对 Perplexity 爬虫发起质询拦截。[1]

## 常见问题

### Perplexity 的 Sonar Chat Completions API 发生了什么变化？

Sonar Chat Completions 已于 2026 年 9 月 27 日停止支持，并由 Perplexity Agent API（POST https://api.perplexity.ai/v1/agent）取代。现有的同步和流式 Sonar 请求仍可继续工作，因为 Perplexity 会在后端自动将其重构为 Agent API 调用；但异步 Sonar 请求已不再受支持，必须迁移至 Agent API 的后台模式。 [5]

### Perplexity 的 Search API 如何定价与计费？

Search API 以 JSON 格式返回带提取文本摘要的排序网页结果，不调用大语言模型，也不收取 Token 费用。标准搜索每 1,000 次成功的 POST /search 请求收费 5.00 美元（每次请求 0.005 美元），Fast Search（search_type: "fast"）每 1,000 次成功请求收费 1.00 美元（每次请求 0.001 美元）。单次 POST /search 调用可包含最多五条查询的数组，但仍仅计为一个计费单位。无效、被限流或失败的请求均不计费。 [4]

### Perplexity 的 Agent API 与 Orchestrator API 有什么区别？

Agent API 遵循 Open Responses 规范，运行完整的多步骤智能体循环，内置多种工具（网页搜索、Finance Search、People Search、URL 抓取、20 分钟计费区块的代码执行沙箱以及 MCP 服务器）和预设调优的 effort 级别（fast、low、medium、high、xhigh），最终返回带引用的回答与类型化搜索结果。Orchestrator API 则是多提供商模型网关，支持开发者以标准 OpenAI 或 Anthropic 请求格式调用 Anthropic、OpenAI、Google、xAI 和开放权重模型，并提供 perplexity/auto 路由、部署故障转移和提示词缓存功能。 [7]

### PerplexityBot 与 Perplexity-User 在 robots.txt 方面有什么区别？

PerplexityBot/1.0 是 Perplexity 的自动搜索爬虫，用于索引网站以便其出现在 Perplexity 搜索结果中；它遵守 robots.txt 规则（24 小时内更新生效），并使用发布在 perplexity.ai/perplexitybot.json 中的 IP。Perplexity-User/1.0 则在真实用户向 Perplexity 提问时按需抓取特定页面；由于其代表用户的直接请求，它通常会忽略 robots.txt 规则，并使用 perplexity.ai/perplexity-user.json 中的 IP。两个爬虫均不收集数据用于训练 AI 基础模型。 [1]

## 可引用的句子

- Perplexity 于 2026 年 9 月 27 日停止对旧版 Sonar Chat Completions 的支持，将同步和流式 Sonar 调用自动重构为 Agent API 请求，同时停用异步 Sonar 请求并引导迁移至后台模式。 [5]
- Perplexity API Platform 由七项核心 API 组成：Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API 和 Decisions API，并配套提供 pplx CLI 与 MCP 服务器。 [4][7]
- Agent API（POST https://api.perplexity.ai/v1/agent）遵循 Open Responses 标准，提供五个 effort 级别（fast、low、medium、high、xhigh），可在 Sonar、OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI 和 NVIDIA 模型间路由，并内置网页、金融和人物搜索、代码沙箱及 MCP 集成。 [5][6]
- Perplexity 的 Search API 不收取 Token 费用，每 1,000 次成功标准请求收费 5.00 美元，或每 1,000 次 Fast Search 请求收费 1.00 美元，且包含最多五条查询数组的单次请求仅计为一个计费单位。 [4]
- Perplexity 运营两个网页代理：用于搜索索引的 PerplexityBot/1.0（截至 2026 年 11 月 18 日公开 21 个 IPv4 /32 前缀）和用于用户发起抓取的 Perplexity-User/1.0（截至 2026 年 10 月 28 日公开 10 个 IPv4 /32 前缀），并声明两个爬虫均不抓取内容用于训练 AI 基础模型。 [1][2][3]

## 时间线

- 2026-09-27: Perplexity 正式停止对旧版 Sonar Chat Completions 的支持，引导开发者过渡至基于 Open Responses 的 Agent API。 [5]
- 2026-10-28: Perplexity 更新 Perplexity-User 的公开 IPv4 白名单列表（perplexity-user.json），包含 10 个 /32 前缀。 [3]
- 2026-11-18: Perplexity 更新 PerplexityBot 的公开 IPv4 白名单列表（perplexitybot.json），包含 21 个 /32 前缀。 [2]

## 来源

1. Perplexity Crawlers - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/resources/perplexity-crawlers (访问于 2026-11-23; tier 3: official site)
2. PerplexityBot Published IPv4 Prefixes (perplexitybot.json). Perplexity. 发布于 2026-11-18. https://www.perplexity.ai/perplexitybot.json (访问于 2026-11-23; tier 3: official site)
3. Perplexity-User Published IPv4 Prefixes (perplexity-user.json). Perplexity. 发布于 2026-10-28. https://www.perplexity.ai/perplexity-user.json (访问于 2026-11-23; tier 3: official site)
4. Pricing - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/getting-started/pricing (访问于 2026-11-23; tier 3: official site)
5. Migrate from Sonar to the Agent API - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/migrate-from-sonar/overview (访问于 2026-11-23; tier 3: official site)
6. Agent API Quickstart - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/quickstart (访问于 2026-11-23; tier 3: official site)
7. Perplexity API Documentation Index (llms.txt). Perplexity. https://docs.perplexity.ai/llms.txt (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Perplexity." 版本 fd90e6ee, 2026-11-23. https://mimirwiki.com/zh/wiki/perplexity
