---
title: "GPTBot"
subtitle: "OpenAI 用于采集生成式 AI 基础模型训练数据的自动化网络爬虫"
canonical_url: https://mimirwiki.com/zh/wiki/gptbot
language: zh
page_class: entity
revision_sha256: 1702107d37c007b456552a9998b4cb78a5b2659848638875bf3483d1513c38d9
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/gptbot.md
  txt: https://mimirwiki.com/zh/wiki/gptbot.txt
  json: https://mimirwiki.com/zh/wiki/gptbot.json
  jsonld: https://mimirwiki.com/zh/wiki/gptbot.jsonld
translations:
  en: https://mimirwiki.com/wiki/gptbot
  ko: https://mimirwiki.com/ko/wiki/gptbot
  ja: https://mimirwiki.com/ja/wiki/gptbot
  es: https://mimirwiki.com/es/wiki/gptbot
---

# GPTBot

> 截至 2026 年底，GPTBot 通过 User-Agent 标识 GPTBot/1.4 (+https://openai.com/gptbot) 表明身份，并在 openai.com/gptbot.json 中公开可验证的出口 IPv4 前缀（截至 2026 年 9 月 22 日共 18 个 CIDR 地址块）。网站运营者可通过 robots.txt（RFC 9309）独立禁止 GPTBot 以阻止模型训练抓取，同时允许 OAI-SearchBot（39 个 IPv4 地址块）以保持在 ChatGPT 搜索结果中的可见性，并可配合新兴的 IETF AI Preferences（aipref）与 Web Bot Auth 加密签名标准进行管理。

GPTBot 是由 OpenAI 运营的主要自动化网络爬虫，用于发现并抓取可能用于训练生成式人工智能基础模型的公开网页内容。它与另外三个承担不同功能角色的 OpenAI 用户代理并行运行：OAI-SearchBot（用于 ChatGPT 搜索索引）、OAI-AdsBot（用于广告落地页验证）以及 ChatGPT-User（用于用户实时触发的网页浏览与自定义 GPT 操作）。

**别名:** GPTBot/1.4, OAI-SearchBot, OAI-AdsBot, ChatGPT-User

## 关键事实

- **运营方:** OpenAI（OpenAI OpCo, LLC） [1]
- **当前 User-Agent 标识:** GPTBot/1.4 (+https://openai.com/gptbot) (截至 2026-11-23) [1]
- **公开 IP 范围:** openai.com/gptbot.json 中的 18 个 IPv4 CIDR 前缀（更新于 2026-09-22） (截至 2026-11-23) [2]
- **配套 OpenAI 代理:** OAI-SearchBot/1.4（搜索）、OAI-AdsBot/1.0（广告）、ChatGPT-User/1.0（用户操作） (截至 2026-11-23) [1]

## 事实摘要

- **运营方:** OpenAI [1]
- **主要功能:** 抓取公开网页内容用于生成式 AI 基础模型训练 [1]
- **User-Agent 字符串:** Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot) [1]
- **IP 验证清单:** https://openai.com/gptbot.json（截至 2026-09-22 共 18 个 IPv4 前缀） [2]
- **搜索配套爬虫:** OAI-SearchBot/1.4（https://openai.com/searchbot.json，39 个 IPv4 前缀） [1]
- **排除协议:** 机器人排除协议（IETF RFC 9309 / robots.txt） [5]
- **新兴标准:** IETF AI Preferences（aipref）与 IETF Web Bot Auth（webbotauth） [6]

## GPTBot 概述与 OpenAI 爬虫分类体系

**GPTBot** 由 OpenAI 于 2023 年 8 月推出并在 2026 年迭代至 1.4 版本，是 OpenAI 专门用于采集公开互联网文本与媒体内容以训练和改进生成式 AI 基础模型的网络爬虫。[1] 由于网站发布者通常希望将训练数据采集、搜索引擎索引、广告合规检查以及实时用户触发的页面抓取区分开来，OpenAI 将其自动化 HTTP 流量划分为以下四个具有独立 `robots.txt` 控制规则和 IP 清单的用户代理。[1]

| User-Agent 标识 | 当前版本 | 用途与模型训练政策 | IP 清单 URL |
| --- | --- | --- | --- |
| `GPTBot` | `GPTBot/1.4` | 抓取可能用于训练 OpenAI 生成式 AI 基础模型的内容。会避开付费墙、包含大量个人身份信息（PII）的来源以及违反政策的内容。[1] | `https://openai.com/gptbot.json`（截至 2026-09-22 共 18 个 IPv4 前缀）[2] |
| `OAI-SearchBot` | `OAI-SearchBot/1.4` | 索引网站以在 ChatGPT 搜索功能中展示链接和摘要。**不**用于训练 OpenAI 基础模型。[1] | `https://openai.com/searchbot.json`（截至 2026-01-02 共 39 个 IPv4 前缀）[3] |
| `OAI-AdsBot` | `OAI-AdsBot/1.0` | 检查广告主落地页的质量、安全性与政策合规性。**不**用于训练基础模型。[1] | 通过 OpenAI 爬虫文档发布[1] |
| `ChatGPT-User` | `ChatGPT-User/1.0` | 在真实用户要求 ChatGPT 或自定义 GPT 抓取特定网页时代表用户触发。**不**用于被动式基础模型训练。[1] | `https://openai.com/chatgpt-user.json`（更新于 2026-11-06）[4] |

截至 2026 年底，GPTBot 发送的完整 HTTP `User-Agent` 请求头为 `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot)`。[1]

## Robots.txt 退出机制与细粒度访问控制

GPTBot 遵循在 **IETF RFC 9309** 中标准化的机器人排除协议（Robots Exclusion Protocol）。[1][5] 网站管理员可在站点的 `/robots.txt` 文件中添加 `User-agent: GPTBot` 规则，从而禁止 GPTBot 抓取整个域名，或将其访问限制在特定目录路径内。[1][5]

由于 OpenAI 将训练抓取与搜索索引分离，希望退出 AI 模型训练但仍希望作为引用链接出现在 ChatGPT Search 中的发布者，可以按如下方式禁止 `GPTBot` 并明确允许 `OAI-SearchBot`。[1]

```text User-agent: GPTBot Disallow: /

User-agent: OAI-SearchBot Allow: / ```

OpenAI 指出，网站更新其 `robots.txt` 规则后，OpenAI 的分布式爬虫集群可能需要约 24 小时才能刷新缓存的 `robots.txt` 策略并停止请求。[1]

## IP 验证与加密 Web Bot 身份认证

由于第三方抓取工具经常在 HTTP 请求头中伪造 `GPTBot` User-Agent 字符串，仅依赖 `User-Agent` 请求头不足以用于防火墙策略执行或流量分析。[1][8] 为此，OpenAI 发布了机器可读的 JSON 前缀清单，以便网络运营者和内容分发网络（CDN）在 IP 层验证真实流量。[1][2][3][4] - **`gptbot.json`**：截至 `2026-09-22T00:00:00Z` 创建时间戳，包含 18 个 IPv4 CIDR 地址块（例如 `20.171.206.0/24`、`52.230.152.0/24`、`20.168.17.192/28`、`172.182.202.0/25`、`172.182.204.0/24` 和 `172.182.214.0/24`）。[2] - **`searchbot.json`**：截至 `2026-01-02T07:01:00.000000Z` 包含 39 个 IPv4 CIDR 地址块。[3] - **`chatgpt-user.json`**：截至 `2026-11-06T00:00:00Z` 更新，包含数十个按区域划分的出口 IPv4 CIDR 地址块。[4]

除 IP 白名单之外，Cloudflare 等边缘安全提供商与 **IETF Web Bot Auth（`webbotauth`）工作组** 推出了面向自动化代理的加密 HTTP 消息签名（基于 RFC 9421）。[7][8] 借助加密机器人身份认证，经过验证的爬虫和 AI 代理会附带使用公开 Ed25519 或 RSA 密钥目录签名的 `Signature` 和 `Signature-Input` 请求头，使源站服务器和 WAF 无需依赖易失效的 IP 地址段查询，即可从数学上验证机器人身份。[7][8]

## IETF AI Preferences（aipref）与网络生态影响

AI 训练爬虫的迅速扩张引发了广泛讨论：最初于 1994 年设计、旨在防止搜索爬虫令服务器过载并换取互惠搜索流量的 `robots.txt`，是否足以表达版权与机器学习使用政策。[5][6]

为弥补这一缺口，**IETF AI Preferences（`aipref`）工作组** 正式成立，负责制定机器可读的词汇表和附着机制，以表达数字内容是否以及如何可被 AI 系统使用。[6] 该工作组的活跃规范包括 `draft-ietf-aipref-vocab`（用于表达 AI 使用偏好的词汇表）和 `draft-ietf-aipref-attach`（通过 `robots.txt` 扩展和 HTTP `Content-Usage` 请求头附着偏好的机制），能够明确区分通用自动化处理、基础模型训练（`train-ai` / `ai`）以及搜索或推理检索增强。[6] 与此同时，来自 Cloudflare AI 流量报告的网络遥测数据显示，`GPTBot` 与 Bytespider、ClaudeBot 和 Google-Extended 长期位居全球流量最高的 AI 爬虫之列，推动了托管式 AI 抓取控制及按次抓取付费（pay-per-crawl）架构的广泛采用。[8]

## 常见问题

### GPTBot 与 OAI-SearchBot 有什么区别？

GPTBot（GPTBot/1.4）抓取公开网页以收集 OpenAI 生成式 AI 基础模型的训练数据。OAI-SearchBot（OAI-SearchBot/1.4）仅用于索引网站并在 ChatGPT 搜索功能中提供链接，不用于训练 OpenAI 的基础模型。 [1]

### 网站如何在阻止 GPTBot 的同时不失去在 ChatGPT Search 中的可见性？

网站管理员可以在根目录的 /robots.txt 文件中添加“User-agent: GPTBot”和“Disallow: /”，同时添加“User-agent: OAI-SearchBot”和“Allow: /”。这可防止 OpenAI 抓取网站用于模型训练，同时允许页面在 ChatGPT 搜索回答中被索引和引用。 [1][5]

### 服务器管理员如何验证 GPTBot 请求确实来自 OpenAI？

管理员应将请求的源 IP 地址与 OpenAI 在 https://openai.com/gptbot.json 发布的官方 CIDR 地址块（截至 2026 年 9 月列出 18 个 IPv4 前缀）进行比对，或使用 CDN 的已验证机器人（Verified Bot）检查以及 IETF Web Bot Auth 框架下标准化的 HTTP 消息签名。 [1][2][7][8]

### 什么是 ChatGPT-User？它为何与 GPTBot 的行为不同？

ChatGPT-User（ChatGPT-User/1.0）是在真实用户主动要求 ChatGPT 或自定义 GPT 操作实时访问特定 URL 时调用的。其出口 IP 单独发布在 https://openai.com/chatgpt-user.json，且其请求不用于被动式基础模型训练。 [1][4]

### 有哪些 IETF 标准规范像 GPTBot 这样的 AI 网络爬虫？

GPTBot 对 robots.txt 的遵循受 IETF RFC 9309（机器人排除协议）规范。此外，IETF AI Preferences（aipref）工作组正在制定用于表达 AI 训练退出的标准化词汇表（draft-ietf-aipref-vocab）及 HTTP/robots 附着规则，而 IETF Web Bot Auth（webbotauth）工作组则负责标准化加密机器人身份认证。 [5][6][7]

## 可引用的句子

- OpenAI 将其网络流量划分为四个独立的用户代理：GPTBot/1.4（模型训练）、OAI-SearchBot/1.4（搜索索引）、OAI-AdsBot/1.0（广告落地页验证）以及 ChatGPT-User/1.0（用户触发请求）。 [1]
- 截至 2026 年 9 月 22 日更新，OpenAI 的 GPTBot 官方 IP 清单（https://openai.com/gptbot.json）共列出 18 个 IPv4 CIDR 前缀。 [2]
- 截至 2026 年 1 月 2 日更新，OpenAI 的 OAI-SearchBot 官方 IP 清单（https://openai.com/searchbot.json）共列出 39 个 IPv4 CIDR 前缀。 [3]
- 在 robots.txt 中禁止 GPTBot 可阻止 OpenAI 抓取网站用于基础模型训练，同时允许 OAI-SearchBot 可保留在 ChatGPT 搜索结果中的索引。 [1][5]
- IETF AI Preferences（aipref）工作组正在制定 draft-ietf-aipref-vocab 和 draft-ietf-aipref-attach，以标准化机器可读的 AI 训练与使用偏好。 [6]

## 时间线

- 2022-09: IETF 发布 RFC 9309，正式将机器人排除协议（robots.txt）标准化。 [5]
- 2023-08: OpenAI 推出 GPTBot，并提供 robots.txt 退出控制及公开出口 IP 范围。 [1]
- 2024-07: OpenAI 推出 OAI-SearchBot，将搜索索引与 GPTBot 基础模型训练抓取分离开来。 [1]
- 2026-01-02: OpenAI 将面向 OAI-SearchBot 的 searchbot.json 更新至 39 个 IPv4 CIDR 地址块。 [3]
- 2026-09-22: 随着 GPTBot 升级至用户代理版本 GPTBot/1.4，OpenAI 将 gptbot.json 更新至 18 个 IPv4 CIDR 前缀。 [1][2]
- 2026-11-06: OpenAI 更新面向用户实时发起的 ChatGPT 浏览操作的 chatgpt-user.json 出口 IPv4 地址范围。 [4]

## 来源

1. Overview of OpenAI Crawlers (GPTBot/1.4, OAI-SearchBot/1.4, OAI-AdsBot/1.0, ChatGPT-User/1.0). OpenAI Platform Documentation. https://platform.openai.com/docs/bots (访问于 2026-11-23; tier 3: official site)
2. OpenAI GPTBot Official IPv4 CIDR Prefix Manifest (gptbot.json). OpenAI. 发布于 2026-09-22. https://openai.com/gptbot.json (访问于 2026-11-23; tier 3: official site)
3. OpenAI OAI-SearchBot Official IPv4 CIDR Prefix Manifest (searchbot.json). OpenAI. 发布于 2026-01-02. https://openai.com/searchbot.json (访问于 2026-11-23; tier 3: official site)
4. OpenAI ChatGPT-User Official IPv4 CIDR Prefix Manifest (chatgpt-user.json). OpenAI. 发布于 2026-11-06. https://openai.com/chatgpt-user.json (访问于 2026-11-23; tier 3: official site)
5. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309 (访问于 2026-11-23; tier 1: government or public registry)
6. IETF AI Preferences (aipref) Working Group Charter and Active Drafts (draft-ietf-aipref-vocab, draft-ietf-aipref-attach). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (访问于 2026-11-23; tier 1: government or public registry)
7. IETF Web Bot Auth (webbotauth) Working Group Charter. Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (访问于 2026-11-23; tier 1: government or public registry)
8. From Googlebot to GPTBot: Who's Crawling Your Site and Cryptographic Bot Verification. Cloudflare. 发布于 2025-05. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "GPTBot." 版本 1702107d, 2026-11-24. https://mimirwiki.com/zh/wiki/gptbot
