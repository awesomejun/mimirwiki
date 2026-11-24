---
title: "Grok"
subtitle: "由 xAI（SpaceX Super Intelligence LLC）开发的生成式人工智能模型系列、开发者 API 及智能体应用套件"
canonical_url: https://mimirwiki.com/zh/wiki/grok
language: zh
page_class: entity
revision_sha256: 699156320b5852785bd06b2d714109a4c73a1cd7e47b70be0a2d16b6eed0fa38
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/grok.md
  txt: https://mimirwiki.com/zh/wiki/grok.txt
  json: https://mimirwiki.com/zh/wiki/grok.json
  jsonld: https://mimirwiki.com/zh/wiki/grok.jsonld
translations:
  en: https://mimirwiki.com/wiki/grok
  ko: https://mimirwiki.com/ko/wiki/grok
  ja: https://mimirwiki.com/ja/wiki/grok
---

# Grok

> Grok 由 xAI（SpaceX Super Intelligence LLC）开发，从采用 Apache 2.0 许可的 3140 亿参数开源权重混合专家模型 Grok-1 以及 Grok-2（2024 年）演进至 2026 年底的旗舰模型 Grok 4.7（`grok-4.7`）。Grok 4.7 具备 500,000 个 token 的上下文窗口、2026 年 5 月的知识截止日期和可配置的加密推理功能，API 定价为每百万输入 token 2.00 美元、每百万输出 token 6.00 美元。2026 年 10 月 12 日，xAI 推出 The X Subscription（每月 $0 Free、$8 Plus、$30 Premium、$100 Super 和 $200 Ultra），将 Grok、Grok Bot、Cursor 编程智能体和 X Premium 整合至单一的每周共享 AI 用量池中。

Grok 是由 xAI（2026 年在 SpaceX Super Intelligence LLC / SpaceXSI 名义下运营）开发的生成式人工智能模型系列、开发者 API 以及对话与编程应用套件，集成于 `grok.com`、移动应用、X 社交平台以及 Cursor 编程环境中。截至 2026 年底，Grok 以旗舰推理与编程模型 Grok 4.7（`grok-4.7`）为核心，辅以专用的 Voice、Imagine 图像生成和 Imagine 视频生成模型，面向开发者通过 xAI Responses API 提供服务，面向个人消费者和团队则通过统一的 The X Subscription 订阅计划提供。

**别名:** Grok, xAI, SpaceX Super Intelligence, Grok 4.7, The X Subscription, Grok-1

## 关键事实

- **开发者与运营实体:** xAI / SpaceX Super Intelligence LLC（SpaceXSI）；订阅服务由 X Subscription Corp. 销售 [4]
- **2026 年旗舰模型:** Grok 4.7（grok-4.7）：500K token 上下文，2026 年 5 月知识截止日期，每百万输入 / 输出 token 定价 $2.00 / $6.00 [2]
- **多模态与智能体套件:** Grok Chat、Grok Build、Grok Bot、Imagine（Image 2.0 与 Video 1.5）、Voice API（grok-voice-3.0）、Grokipedia [3]
- **The X Subscription（2026 年 10 月 12 日）:** 捆绑 Grok、Grok Bot、Cursor 与 X Premium 的统一订阅计划（Free $0、Plus $8、Premium $30、Super $100、Ultra $200） [4]
- **开源权重版本:** Grok-1（xai-org/grok-1）：314B 参数 8 专家 MoE（每个 token 激活 2 个），64 层，Apache 2.0 许可证 [7]

## 事实摘要

- **开发者:** xAI（SpaceX Super Intelligence LLC / SpaceXSI） [4]
- **旗舰模型:** Grok 4.7（grok-4.7） [1]
- **上下文窗口:** 500,000 token（Grok 4.7）；8,192 token（Grok-1 开源权重） [2]
- **知识截止日期:** 2026 年 5 月（Grok 4.7） [2]
- **Grok 4.7 API 定价:** 每百万输入 token $2.00；每百万输出 token $6.00 [1]
- **语音与媒体 API 定价:** STS $0.08/分钟；TTS $15/百万字符；STT $0.10-$0.20/小时；图像 $0.02/张起；视频 $0.02/秒起 [1]
- **API 速率限制等级:** Tier 0（$0）至 Tier 4（自 2026 年 1 月 1 日起累计消费 $5,000 以上）：Grok 4.5-4.7 最高支持 500 RPS 与 100M TPM [3]
- **The X Subscription 档位:** Free（$0）、Plus（$8/月）、Premium（$30/月，4 倍）、Super（$100/月，15 倍）、Ultra（$200/月，50 倍） [6]
- **云合作伙伴平台:** xAI API（api.x.ai/v1）、Google Cloud Vertex AI、Microsoft Foundry [1]
- **开源权重许可证:** Apache 2.0（Grok-1 314B 检查点，托管于 github.com/xai-org/grok-1） [7]

## 从 Grok-1 和 Grok-2 到 SpaceX Super Intelligence 的演进

Grok 由 xAI 创建，旨在提供与 X 社交网络集成的对话推理、编程辅助以及实时信息综合能力。[7][8] 在初代阶段，xAI 以 Apache 2.0 许可证发布了开源权重的 Grok-1 基础检查点（`github.com/xai-org/grok-1` 和 `huggingface.co/xai-org/grok-1`）及参考 JAX 推理代码。[7] Grok-1 是一个拥有 3140 亿参数的混合专家（Mixture-of-Experts，MoE）语言模型，包含 64 层 Transformer，每层 8 个专家且每个 token 激活 2 个专家，嵌入维度为 6,144，配备 48 个查询注意力头和 8 个键/值头、旋转位置编码（RoPE）、131,072 个 token 的 SentencePiece 词表，支持激活分片和 8 位量化，最大序列长度为 8,192 个 token。[7]

2024 年 8 月，xAI 发布了 Grok-2；随后于 2024 年 12 月 12 日推出了速度提升至三倍的升级版 Grok-2（`grok-2-1212` 和 `grok-2-vision-1212`），在 X 平台面向用户免费开放，并同步上线实时网页搜索、内联来源引用、时间线“Grok 按钮”以及自回归照片级图像生成模型 Aurora，同时将 API 定价下调至每百万输入 token 2 美元、每百万输出 token 10 美元。[8]

至 2026 年，xAI 的开发者文档、新闻公告和定价门户均在企业实体 SpaceX Super Intelligence LLC（品牌名为 SpaceXSI，社交账号为 `@SpaceXSI` 和 `@grok`）名下运营，而面向个人消费者与团队的直接自助订阅服务则由 X Subscription Corp. 独家销售。[1][4][5] 其产品组合也从单一对话应用扩展为涵盖 Grok Chat、Grok Build（智能体编程）、Grok Bot（自主 AI 团队成员）、Grok Imagine（图像与视频生成）、Grok Voice 以及 Grokipedia 的完整套件。[3][4]

## Grok 4.7 与多模态模型目录

截至 2026 年 11 月，Grok 4.7（`grok-4.7`）是整个 Grok 平台与 xAI API 的旗舰基础模型，推荐用于所有文本、对话和软件工程工作负载。[1][2] Grok 4.7 具备 500,000 个 token 的上下文窗口、可配置的推理强度、2026 年 5 月的知识截止日期，官方定价为每百万输入 token 2.00 美元、每百万输出 token 6.00 美元（相比 Grok-2 的 $2/$10 定价，输出成本降低了 40%）。[1][2][8]

Grok 4.7 与 Grok 4.x API 系列的关键技术行为包括：[2][3]

- **加密推理内容**：在 xAI Responses API（`POST https://api.x.ai/v1/responses`）上，即使请求的 `include` 参数未明确要求，`grok-4.7` 也会始终在响应载荷中返回 `reasoning.encrypted_content`。[2]
- **灵活的角色排序与参数规则**：对话模型支持在对话上下文中以任意顺序排列 `system`、`user` 和 `assistant` 角色。[2] 对于 `grok-4.20` 及所有更新模型，系统不支持 `logprobs` 和 `top_logprobs` 参数，传入时会被静默忽略。[2]
- **视觉输入限制**：支持图像的 Grok 模型接受单个文件最大 20 MiB 的 `jpg`/`jpeg` 和 `png` 文件，在 token 上下文窗口范围内不限制单次请求的图像数量，并支持以任意顺序交错输入图像和文本提示词。[2]
- **显式实时联网检索**：默认情况下，Grok API 模型无法获取 2026 年 5 月训练截止日期之后的实时事件，除非调用方启用服务器端搜索工具（Web Search、X Search、Collections RAG、Code Execution 或 Remote MCP Tools）。[1][2]

在更广泛的 xAI API 目录中（详见 2026 年 11 月的速率限制与定价规范），xAI 提供以下多个模型系列：[1][2][3]

| 模型 / 端点系列 | 活跃模型标识符 | 定价 / 关键规格 |
| --- | --- | --- |
| 旗舰语言与推理 | `grok-4.7`（最新）、`grok-4.6`、`grok-4.5`、`grok-4.3` | 500K 上下文（`grok-4.7`）；输入 $2.00 / 百万 token，输出 $6.00 / 百万 token |
| 专用智能体与编程 | `grok-build-0.1`、`grok-4.20-multi-agent-0309`、`grok-4.20-0309-reasoning`、`grok-4.20-0309-non-reasoning` | 驱动 Grok Build 智能体编程、重构与多智能体工作流 |
| 图像生成（Imagine） | `grok-imagine-image-2.0`（Image 2.0）、`grok-imagine-image` | 1K / 2K 图像生成、编辑及多图编辑，$0.02 / 张起 |
| 视频生成（Imagine） | `grok-imagine-video-1.5`（Video 1.5）、`grok-imagine-video-1.5-lite`、`grok-imagine-video` | 480p / 720p / 1080p（Super/Ultra 最高支持 15 秒 1080p）、图生视频、参考图生视频、编辑与延长，$0.02 / 秒起 |
| 语音与音频 API | `grok-voice-3.0`、文本转语音（TTS）、语音转文本（STT） | 语音到语音（STS）：$0.08/分钟；TTS：$15.00/百万字符；STT 批处理：$0.10/小时；STT 流式：$0.20/小时 |

## xAI API 架构、云集成与速率限制等级

xAI 开发者平台提供现代化的 Responses API（`https://api.x.ai/v1/responses`）、OpenAI 兼容 REST 接口、基于原生 gRPC 的 `xai_sdk` Python 包，以及与 Vercel AI SDK（`@ai-sdk/xai`）、Google Cloud Vertex AI 和 Microsoft Foundry 的官方集成。[1][3] 企业级高级 API 功能涵盖提示词缓存（Prompt Caching）、上下文压缩（Context Compaction）、优先处理（Priority Processing）、自定义内容审核控制、批处理 API（Batch API）、延迟补全（Deferred Completions）、异步请求、WebSocket 模式、mTLS 认证、区域端点以及输出水印（Output Watermarking）。[1][3]

每个 xAI API 团队均按模型受限于两个维度的速率限制：语言模型按每秒请求数（RPS）和每分钟 token 数（TPM）计费限流，语音端点则按并发会话数（CST）和 RPS 限流。[3] 为防止单秒突发流量耗尽配额，团队的每秒请求上限由其每分钟预算推导得出（`RPM / 48`，最低 2 RPS）。[3] 所有提示词 token（文本、图像、音频）、补全 token、推理 token 以及缓存命中的提示词 token 均计入对应模型的 TPM 上限。[3] 速率限制等级根据自 2026 年 1 月 1 日以来的累计 API 消费额自动且永久解锁，不会降级：[3]

| 速率限制等级 | 累计消费门槛（自 2026 年 1 月 1 日起） | `grok-4.7` / `4.6` / `4.5`（RPS / TPM） | `grok-4.3` / `grok-build-0.1` / `4.20`（RPS / TPM） | `grok-4.20-multi-agent`（RPS / TPM） | `grok-imagine-image-2.0`（RPS） | `grok-imagine-video-1.5`（RPS） | `grok-voice-3.0`（CST） |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Tier 0 | $0（默认） | 150 RPS / 50M TPM | 37 RPS / 10M TPM | 9 RPS / 2.5M TPM | 6 RPS | 10 RPS | 10 CST |
| Tier 1 | $50 | 172 RPS / 53M TPM | 50 RPS / 15M TPM | 12 RPS / 3.7M TPM | 12 RPS | 20 RPS | 20 CST |
| Tier 2 | $250 | 208 RPS / 60M TPM | 75 RPS / 25M TPM | 18 RPS / 6.2M TPM | 25 RPS | 39 RPS | 50 CST |
| Tier 3 | $1,000 | 312 RPS / 74M TPM | 125 RPS / 45M TPM | 31 RPS / 11M TPM | 50 RPS | 79 RPS | 100 CST |
| Tier 4 | $5,000 | 500 RPS / 100M TPM | 208 RPS / 85M TPM | 56 RPS / 21M TPM | 100 RPS | 158 RPS | 200 CST |
| Enterprise | 定制（通过 sales@x.ai） | 定制 | 定制 | 定制 | 定制 | 定制 | 定制 |

## The X Subscription：Grok、Grok Bot、Cursor 与 X Premium 的统一整合

2026 年 10 月 12 日，xAI 推出了全球统一的订阅计划 The X Subscription，将四款产品整合至单一账单账户和每周共享 AI 用量池中：Grok（Chat、Voice、Imagine 与 Build）、Grok Bot（自主 AI 团队成员）、Cursor IDE 及云端编程智能体（包括通过 Origin 提供的代码托管和通过 Bugbot 提供的 AI 代码审查），以及 X Premium 社交网络权益。[4][5][6]

每个付费档位均提供一个每周刷新的 Grok 模型用量池，可在 Grok 网页/移动应用、X 平台上的 Grok 标签页、Grok Bot 和 Cursor 之间共享，其 Grok 模型编程用量至少为同级别旧版独立 Cursor 计划的两倍（Team 计划的编程用量则是旧版 Cursor Teams 的三倍）。[4][5] 现有的独立 SuperGrok、Cursor 和 X Premium 订阅用户可选择保留原有计划，或切换至 The X Subscription 并自动获得未使用时长的按比例退款（通过 Apple App Store 购买的 Cursor 订阅除外，需直接在 Apple 端取消）。[4][6]

| 订阅档位 | 月付价格 | 年付价格 | 每周共享 AI 用量池 | Grok、Cursor 与 X 包含的核心功能 |
| --- | --- | --- | --- | --- |
| Free | $0 / 月 | $0 / 年 | 有限额度 | 每日 Grok 访问、入门级 Cursor 编程智能体额度、标准 X 功能、6.00% X Money 年化收益率（APY）及 3% 返现（需启用 Direct Deposit） |
| Plus | $8 / 月 | $80 / 年（$7/月） | 基础（1 倍） | Grok + Cursor 共享池、Grok Chat/Voice/Imagine/Build、Grok API 访问、X Premium 认证徽章、减少时间线广告、创作者工具（不含 Grok Bot；不适用于 Teams） |
| Premium | $30 / 月 | $300 / 年（$25/月） | Plus 的 4 倍 | 解锁 Grok Bot、最新 Grok 模型、Cursor Cloud 智能体与自动化、Origin 代码托管、Bugbot AI 代码审查、X 大多数页面免广告浏览、6.00% X Money APY（替代原合计 $90/月的 SuperGrok + Cursor Pro + X Premium+） |
| Super | $100 / 月 | $1,000 / 年（$84/月） | Plus 的 15 倍 | 包含 Premium 全部权益，外加 1080p 15 秒视频生成、极速响应及高峰期优先访问权 |
| Ultra | $200 / 月 | $2,000 / 年（$167/月） | Plus 的 50 倍 | 包含 Super 全部权益，面向重度用户提供 Plus 50 倍的每周 AI 用量额度 |
| Teams | $30 - $200 / 席位 / 月 | $300 - $2,000 / 席位 / 年 | 每席位 Plus 的 4 倍至 50 倍 | 支持 Premium/Super/Ultra 席位混搭、集中账单管理、用量分析、SAML/OIDC 单点登录（SSO）、SOC 2 合规、面向内部规则/技能/插件的团队应用市场 |

虽然付费计划包含 Grok API 控制台的访问权限，但直接调用 API 所消耗的 token 会按标准 API 费率单独计费，不会从订阅的每周用量池中扣除。[5] 同样，Premium、Super 和 Ultra 计划用户仍可在 Cursor 内选择非 Grok 的第三方模型，但相关费用不计入订阅包含的 Grok 用量池，而是通过预付充值和 Additional Usage 额度按 API 官方标价单独计费。[4][5][6]

## 常见问题

### Grok 4.7 的技术规格和 API 定价是多少？

Grok 4.7（grok-4.7）是 xAI 截至 2026 年底的旗舰语言、编程与推理模型。它支持 500,000 个 token 的上下文窗口、可配置的推理强度（在 Responses API 上始终返回 reasoning.encrypted_content）、2026 年 5 月的知识截止日期，以及单张不超过 20 MiB 的 JPEG/PNG 图像不限数量输入。标准 API 定价为每百万输入 token 2.00 美元、每百万输出 token 6.00 美元。 [2]

### 2026 年 10 月发布的 The X Subscription 包含哪些内容？

The X Subscription 于 2026 年 10 月 12 日推出，将 Grok（Chat、Voice、Imagine 图像/视频生成以及 Grok Build）、Grok Bot AI 团队成员、Cursor 代码编辑器及云端智能体（包括 Origin 代码托管和 Bugbot AI 代码审查）以及 X Premium 整合为一个拥有每周共享 AI 用量池的统一订阅计划。其档位包括 Free（$0）、Plus（$8/月或 $80/年）、Premium（$30/月或 $300/年，Plus 4 倍用量，替代原先合计 $90/月的独立 SuperGrok、Cursor Pro 和 X Premium+ 计划）、Super（$100/月或 $1,000/年，Plus 15 倍用量）以及 Ultra（$200/月或 $2,000/年，Plus 50 倍用量）。 [4]

### The X Subscription 是否涵盖 Cursor 中的第三方模型或直接调用 Grok API 的 token 费用？

不涵盖。The X Subscription 的每周共享用量池仅适用于在 Grok 应用、X、Grok Bot（Premium 及以上）和 Cursor 中使用 Grok 模型。Premium、Super 和 Ultra 计划用户仍可在 Cursor 中使用第三方模型，但自第一个 token 起即通过预付充值按 API 官方标价单独计费。同样，直接调用 Grok API 也会按标准每 token API 费率单独计费。 [6]

### xAI API 的速率限制等级是如何运作的？

xAI API 按模型对每秒请求数（RPS，按 RPM / 48 计算，最低为 2）和每分钟 token 数（TPM，计入提示词、补全、推理和缓存 token）实施速率限制。等级根据自 2026 年 1 月 1 日起的累计消费额自动且永久解锁：Tier 0（$0）、Tier 1（$50）、Tier 2（$250）、Tier 3（$1,000）和 Tier 4（$5,000）。对于 Grok 4.5、4.6 和 4.7，限额从 Tier 0 的 150 RPS 和 50M TPM 提升至 Tier 4 的 500 RPS 和 100M TPM。 [3]

## 可引用的句子

- 截至 2026 年 11 月，xAI 的旗舰语言模型为 Grok 4.7（grok-4.7），具备 500,000 token 上下文窗口、2026 年 5 月知识截止日期、Responses API 强制返回加密推理内容，定价为每百万输入 token 2.00 美元、每百万输出 token 6.00 美元。 [1][2]
- xAI 发布的开源权重模型 Grok-1（xai-org/grok-1）采用 Apache 2.0 许可证，是一款 3140 亿参数的混合专家模型，包含 64 层、每层 8 个专家（每个 token 使用 2 个）、6,144 嵌入维度以及 8,192 token 上下文窗口。 [7]
- 2026 年 10 月 12 日，xAI（SpaceX Super Intelligence LLC）推出 The X Subscription，将 Grok、Grok Bot、Cursor 和 X Premium 整合至单一订阅与每周共享 AI 用量池中，包含五个档位：Free（$0）、Plus（$8/月）、Premium（$30/月，Plus 的 4 倍）、Super（$100/月，Plus 的 15 倍）和 Ultra（$200/月，Plus 的 50 倍）。 [4][5][6]
- 在 xAI API 中，速率限制等级根据自 2026 年 1 月 1 日起的累计消费额永久提升，从 Tier 0（$0 默认：Grok 4.5/4.6/4.7 为 150 RPS 和 50M TPM）扩展至 Tier 4（累计消费 $5,000 以上：Grok 4.5/4.6/4.7 为 500 RPS 和 100M TPM）。 [3]
- xAI 的多模态 API 套件包括 Grok Voice API（语音到语音 $0.08/分钟，TTS $15.00/百万字符，STT 批处理 $0.10/小时与流式 $0.20/小时）、Imagine Image 2.0（$0.02/张起）以及 Imagine Video 1.5（支持 480p、720p 与 1080p，$0.02/秒起）。 [1][2][3]

## 时间线

- 2024-03: xAI 以 Apache 2.0 许可证发布 3140 亿参数的开源权重混合专家模型 Grok-1 检查点及 JAX 代码。 [7]
- 2024-12-12: xAI 向所有 X 用户免费推出速度更快的 Grok-2（grok-2-1212 和 grok-2-vision-1212），发布 Aurora 图像生成模型，并将 API 定价下调至每百万 token $2/$10。 [8]
- 2026-05: 旗舰模型 Grok 4.7 的知识截止日期。 [2]
- 2026-10-12: xAI（SpaceX Super Intelligence LLC）推出 The X Subscription，将 Grok、Grok Bot、Cursor 与 X Premium 整合至单一计划和共享用量池。 [4]
- 2026-11-13: xAI 更新其 API 速率限制表，涵盖 Grok 4.7、Grok Build 0.1、Imagine Image 2.0、Imagine Video 1.5 和 Grok Voice 3.0。 [3]

## 来源

1. Grok API Documentation Overview | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). https://docs.x.ai/overview (访问于 2026-11-23; tier 3: official site)
2. Grok Models & Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 发布于 2026-09-21. https://docs.x.ai/developers/models (访问于 2026-11-23; tier 3: official site)
3. Rate Limits | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 发布于 2026-11-13. https://docs.x.ai/developers/rate-limits (访问于 2026-11-23; tier 3: official site)
4. Introducing The X Subscription | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 发布于 2026-10-12. https://x.ai/news/x-subscription (访问于 2026-11-23; tier 3: official site)
5. Pricing: Compare Plans | SpaceXSI. xAI (SpaceX Super Intelligence LLC). https://x.ai/pricing (访问于 2026-11-23; tier 3: official site)
6. The X Subscription Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 发布于 2026-10-11. https://docs.x.ai/x-subscription/pricing (访问于 2026-11-23; tier 3: official site)
7. Grok-1 Open Release Repository and Model Specifications (xai-org/grok-1). xAI. https://raw.githubusercontent.com/xai-org/grok-1/main/README.md (访问于 2026-11-23; tier 3: official site)
8. Bringing Grok to Everyone | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 发布于 2024-12-12. https://x.ai/news/grok-1212 (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Grok." 版本 69915632, 2026-11-23. https://mimirwiki.com/zh/wiki/grok
