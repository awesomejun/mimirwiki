---
title: "Google Gemini"
subtitle: "Google 与 Google DeepMind 推出的原生多模态人工智能模型家族、开发者 API 平台及消费级应用生态"
canonical_url: https://mimirwiki.com/zh/wiki/google-gemini
language: zh
page_class: entity
revision_sha256: efe2172438bd8c715ad3939fa97d80b17f0a8bcf32fc82cdcb3ab8ddc185e1bd
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/google-gemini.md
  txt: https://mimirwiki.com/zh/wiki/google-gemini.txt
  json: https://mimirwiki.com/zh/wiki/google-gemini.json
  jsonld: https://mimirwiki.com/zh/wiki/google-gemini.jsonld
translations:
  en: https://mimirwiki.com/wiki/google-gemini
  ko: https://mimirwiki.com/ko/wiki/google-gemini
  ja: https://mimirwiki.com/ja/wiki/google-gemini
---

# Google Gemini

> Google Gemini 由 Google DeepMind 开发，是覆盖消费级订阅服务（Google AI Plus、Pro 与 Ultra）和开发者平台（Google AI Studio 与 Gemini Enterprise Agent Platform）的原生多模态 AI 模型系列与产品生态。截至 2026 年 11 月，旗舰 Gemini 4 家族包含 Gemini 4 Carbon、Gemini 4 Neon、Gemini 4 Argon 与 Gemini 4 Hydrogen，均支持 100 万 token 上下文窗口、最高 64K / 1M 输出 token，以及文本、图像、音频、视频与 PDF 输入；Carbon 与 Argon 在 2026 年 11 月 30 日前适用每百万 token 输入 $2.00 / 输出 $10.00 的付费 API 促销价（2026 年 12 月 1 日起调整为 $4.00 / $20.00）。

Google Gemini 是由 Google DeepMind 与 Alphabet Inc. 开发的旗舰级原生多模态人工智能基础模型家族与助手应用体系。该系列于 2023 年 12 月随 Gemini 1.0 首次推出，历经 Gemini 1.5、2.5、3 以及以化学元素命名的 Gemini 4 世代（`gemini-4-carbon`、`gemini-4-neon`、`gemini-4-argon` 与 `gemini-4-hydrogen`）不断演进，现已为 Google 全部 15 款用户量超过 5 亿的产品（包括 7 款用户量超过 20 亿的产品）提供底层支持，同时驱动 Google AI Studio、Gemini Developer API 以及 Google Cloud 的 Gemini Enterprise Agent Platform。

**别名:** Google Gemini, Google DeepMind, Gemini 4 Carbon, Gemini 4 Neon, 多模态 AI, Google AI Studio

## 关键事实

- **开发者与母公司:** Google DeepMind / Alphabet Inc.（CIK 0001652044；Nasdaq: GOOGL、GOOG） [1]
- **产品集成规模:** 集成于全部 15 款 5 亿以上用户 Google 产品（含 7 款 20 亿以上用户产品） [1]
- **Gemini 4 旗舰阵容:** Gemini 4 Carbon、Gemini 4 Neon、Gemini 4 Argon 与 Gemini 4 Hydrogen（1M 上下文，最高 64K / 1M 输出） [3]
- **专用 Gemini 3 / 4 模型:** Gemini 3.8 Flash / Live / TTS、Nano Banana 2.1（图像）、Gemini Omni Flash（15 秒视频）、Genie 4（24 fps 交互世界） [3]
- **消费级订阅档位:** Google AI Plus（400 GB，Hydrogen）、Google AI Pro（5 TB，Neon）、Google AI Ultra（20 TB 及以上，Carbon） [2]

## 事实摘要

- **开发者:** Google DeepMind（Alphabet Inc.） [1]
- **首次发布:** 2023 年 12 月（Gemini 1.0 技术报告于 2023 年 12 月 19 日提交） [7]
- **当前世代:** Gemini 4（Carbon、Neon、Argon、Hydrogen）及专用 Gemini 3.8 / Omni / Genie 4 [3]
- **支持模态:** 输入：文本、图像、音频、视频与 PDF；输出：文本、音频、图像、视频与交互式世界 [3]
- **上下文与最大输出:** 1,000,000 token 上下文窗口；最大输出 64,000 / 1,000,000 token（Gemini 4 家族） [3]
- **Carbon 与 Argon API 定价:** 2026 年 11 月 30 日前每百万 token 输入 $2.00 / 输出 $10.00 / 缓存 $0.10（2026 年 12 月 1 日起为 $4 / $20 / $0.20） [4]
- **API 使用层级:** Free、Tier 1（$250 上限）、Tier 2（$2,000 上限）、Tier 3（$20,000-$100,000+ 上限） [5]
- **滚动消费速率限制:** 每 10 分钟 $10（Tier 1）；每 10 分钟 $200（Tier 2 与 Tier 3） [5]
- **消费级 Google One 方案:** Google AI Plus（400 GB）、Google AI Pro（5 TB）、Google AI Ultra（20 TB+，覆盖 150 多个国家与地区） [2]
- **开发者平台:** Google AI Studio、Gemini Developer API、Gemini Enterprise Agent Platform、Google Antigravity [2]

## 从 Gemini 1.0 到 Gemini 4 的演进与 Alphabet 生态采用规模

Google DeepMind 于 2023 年 12 月推出 Gemini 架构（`arXiv:2312.11805`，提交于 2023 年 12 月 19 日），将其定位为从底层开始跨越图像、音频、视频与文本多模态联合训练的模型家族。[7] 2024 年 3 月，Google DeepMind 发布 Gemini 1.5（`arXiv:2403.05530`，提交于 2024 年 3 月 8 日），实现了覆盖数百万 token 上下文的长上下文多模态理解能力。[8] 随后在 2025 年 7 月，Google DeepMind 推出 Gemini 2.5（`arXiv:2507.06261`，提交于 2025 年 7 月 7 日），集成了思考 token（thinking tokens）、高级推理与新一代智能体能力，并进一步演进至 Alphabet Inc. 2025 财年 Form 10-K（提交于 2026 年 2 月 5 日）中重点提及的 Gemini 3 世代。[1][9]

根据 Alphabet Inc. 向美国证券交易委员会（SEC）提交的 Form 10-K 文件，Gemini 模型已嵌入 Google 全部 15 款服务超过 5 亿用户的产品中，其中包括 7 款用户量超过 20 亿的产品，并支撑 Gemini Enterprise 与 Gemini for Google Workspace 等企业级产品。[1] 截至 2026 年 11 月，Google DeepMind 通过 Gemini 4 家族进一步加快前沿模型发布节奏，从传统的规模分级命名转向化学元素命名体系（`Carbon`、`Neon`、`Argon` 与 `Hydrogen`）。[3][10]

## Gemini 4 与专用 Gemini 3 模型目录

在 Gemini Developer API 与 Google AI Studio 中，当前模型目录由旗舰 Gemini 4 系列（各变体均共享 1,000,000 token 上下文窗口、64,000 / 1,000,000 token 最大输出限制，并原生支持文本、图像、音频、视频与 PDF 模态）以及专用的 Gemini 3.x 和交互式媒体端点组成。[3]

| 模型名称 | API 端点代码 | 层级与主要工作负载特征 |
| --- | --- | --- |
| Gemini 4 Carbon | `gemini-4-carbon` | 最强前沿推理模型；利用扩展验证循环与思考 token 处理复杂软件工程、网络安全防御、深度数学与科学问题以及 1M token 长文本解码生成 |
| Gemini 4 Neon | `gemini-4-neon` | 前沿级智能模型，针对软件工程、多模态知识工作与科学工作流中的快速端到端任务完成进行了优化 |
| Gemini 4 Argon | `gemini-4-argon` | 高效前沿推理模型，提供 Gemini 4 级智能，同时相比 Carbon 具备更快的响应速度与更低的单轮 token 消耗 |
| Gemini 4 Hydrogen | `gemini-4-hydrogen` | 高速、高性价比的 Gemini 4 模型，面向日常编程、高吞吐任务与智能体工作流设计 |
| Gemini 3.8 Flash | `gemini-3.8-flash` | 面向软件工程与自主企业级工作流的上一代稳定版 Flash 模型 |
| Gemini 3.8 Live & Extended Thinking | `gemini-3.8-live` / `gemini-3.8-live-extended-thinking` | 面向 Live API 的低延迟语音智能体模型（标准版与高强度后台推理版） |
| Gemini 3.8 Flash TTS & Flash-Lite TTS | `gemini-3.8-flash-tts` / `gemini-3.8-flash-lite-tts` | 录音室级与高吞吐文本转语音模型，支持富有表现力的演绎、音色设计与声音复刻 |
| Nano Banana 2.1 / 2 / Pro | `gemini-nano-banana-2.1` / `gemini-3.1-flash-image` / `gemini-3-pro-image` | 针对排版渲染、多轮一致性与大规模视觉创作优化的原生图像生成与编辑模型 |
| Gemini Omni Flash | `gemini-omni-flash` (`gemini-omni-1.2-flash`) | 视频生成与编辑模型，可生成最长 15 秒的原生音频视频，支持关键帧插值、视频续写与角色一致性 |
| Genie 4 | `genie-4` | 实时交互式世界模型，通过 WebRTC 与 WebSockets 流式传输可操控的 24 fps 环境及同步的 48 kHz 立体声音频 |
| Gemini Decision 1 | `gemini-decision-1` | 部署于 Decisions API 的高吞吐决策模型（Tier 3 下最高可达 15,000 RPM 与 10M TPM） |

此外，该目录还保留了 `gemini-3.6-flash`、`gemini-3.5-flash-lite`、`gemini-3.1-flash-lite`、`gemini-3.5-transcribe`（支持话语级语言检测与说话人分离的低延迟语音转文本模型）以及 `gemini-3.5-live-translate-preview`（覆盖 70 多种语言的实时语音同声翻译模型）的稳定端点。[3]

## Gemini Developer API 定价、使用层级与速率限制

在 Gemini Developer API 中，Google 提供免费层级（Free tier，仅适用于部分模型，提交内容可能被用于改进 Google 产品）和付费层级（Paid tier，客户数据不会用于模型训练）。[4] `gemini-4-carbon` 与 `gemini-4-argon` 均不支持免费层级，且这些模型处理的每一个 token 均计入计费，包括内部思考 token 以及在使用 Google 搜索增强检索（Grounding with Google Search，付费层级每月包含 5,000 次免费搜索请求，项目默认配额为每日 1,500 次请求）时产生的工具系统指令或函数声明。[4][5]

针对 `gemini-4-carbon` 与 `gemini-4-argon`，Google 在 2026 年 11 月 30 日前实行首发促销定价，并于 2026 年 12 月 1 日起过渡为标准目录价格。[4]

- **输入价格（付费层级）**：2026 年 11 月 30 日前每百万 token $2.00；2026 年 12 月 1 日起每百万 token $4.00。[4]
- **输出价格（含思考 token）**：2026 年 11 月 30 日前每百万 token $10.00；2026 年 12 月 1 日起每百万 token $20.00。[4]
- **上下文缓存价格（仅限隐式缓存）**：2026 年 11 月 30 日前每百万 token $0.10；2026 年 12 月 1 日起每百万 token $0.20（Carbon 与 Argon 不支持显式缓存）。[4]

Gemini API 的速率限制按 Google Cloud 项目（而非按 API 密钥）执行，每日请求配额（RPD）于太平洋时间午夜重置。[5] 除 RPM、TPM 与 RPD 配额外，Google 还根据项目的 Google Cloud 累计账单历史实施 10 分钟滚动消费速率限制（超限时返回 `429 RESOURCE_EXHAUSTED`）。[5]

| 使用层级 | 准入条件 | 月度计费层级上限 | 10 分钟滚动消费上限 | Gemini Omni Flash（RPM / RPD） | Genie 4（并发会话数 / RPD） | Gemini Decision 1（RPM / TPM / RPD） |
| --- | --- | --- | --- | --- | --- | --- |
| Free | 活跃项目或免费试用 | 不适用 | 不适用 | 不支持 | 不支持 | 200 / 50K / 10,000 |
| Tier 1 | 绑定有效结算账号 | $250 | $10 / 10 分钟 | 8 / 40 | 2 / 50 | 1,500 / 1M / 50,000 |
| Tier 2 | 累计消费 $100 及以上且首次付款满 3 天 | $2,000 | $200 / 10 分钟 | 16 / 200 | 5 / 250 | 5,000 / 4M / 无限制 |
| Tier 3 | 累计消费 $1,000 及以上且首次付款满 30 天 | $20,000 - $100,000+ | $200 / 10 分钟 | 40 / 2,000 | 10 / 1,000 | 15,000 / 10M / 无限制 |

在面向 `genie-4` 的 Interactions API 上，会话内实时控制消息（`user_action` 与会话中 `input` 事件）不消耗单独的 RPM 或 RPD 配额，但 Genie 4 不支持 Batch API、Flex 推理或 Priority 推理。[5] 位于 Google AI Studio 未覆盖地区的开发者可通过 Google Cloud 的 Gemini Enterprise Agent Platform 访问 Gemini 模型。[6]

## Google One AI 订阅方案与 Workspace 集成

面向普通消费者、创作者与独立开发者，Google 通过三档分级订阅方案提供 Gemini 能力与 Google One 云存储空间（所有方案均支持与最多 5 名额外家庭成员共享）。[2]

1. **Google AI Plus（400 GB 存储空间）**：包含 Gemini 4 Hydrogen、Deep Research、Tasks in Gemini、Chrome auto browse、Gemini Notebook、Gmail 校对功能，以及 Android 与 iOS 上的 Gmail Live（仅限美国地区）。[2] 2. **Google AI Pro（5 TB 存储空间）**：将用户的 Gemini 访问额度提升至 4 倍，涵盖 Gemini 应用、Google Antigravity 与 Google AI Studio 中的 Gemini 4 Neon，同时包含每月 200 个 Google Colab 计算单元、通过 Google Developer Program 提供的每月 $10 Google Cloud 抵扣金、Android Studio 中的扩展智能体 AI 辅助、Google Docs 与 Sheets 中的 Gemini 及 Docs Live（仅限美国地区）、Google Flow 视频创作、YouTube Premium Lite（个人版）、Google Health Premium 以及 Google Home Premium Standard（30 天事件历史，价值每月 $10）。[2] 通过验证的学生可免费使用 Google AI Pro 一年，或以每月 $8.99 的价格订阅包含完整版 YouTube Premium 的组合方案。[2] 3. **Google AI Ultra（20 TB 存储空间起，覆盖 150 多个国家与地区）**：提供高于 AI Pro 5 倍的使用上限，并在 Gemini 应用及搜索 AI 模式中解锁 Gemini 4 Carbon，同时包含基于 Project Genie 的实时交互式世界生成、每月 2,000 个 Google Colab 计算单元、每月 $40 Google Cloud 抵扣金、YouTube Premium Family 方案（覆盖 100 多个国家与地区）、Google Health Premium 以及 Google Home Premium Advanced（7×24 小时事件历史与描述，价值每月 $20）。[2]

在整个 Gemini 应用生态中，Deep Research 可实时自主浏览并综合数百个网站，生成多页研究报告；Tasks in Gemini 则可在后台代表用户执行多步骤网页工作流。[2]

## 常见问题

### Gemini 4 Carbon、Neon、Argon 与 Hydrogen 之间有什么区别？

全部四款 Gemini 4 模型均支持 100 万 token 上下文窗口、64K / 1M 最大输出 token，以及文本、图像、音频、视频与 PDF 输入。Gemini 4 Carbon 是 Google 最强的前沿推理模型，采用扩展验证循环与思考 token，适用于高难度软件工程、网络安全与科学问题。Gemini 4 Neon 提供前沿级智能，针对快速端到端任务完成进行了优化。Gemini 4 Argon 是一款高效前沿推理变体，相比 Carbon 降低了单轮 token 消耗与延迟；而 Gemini 4 Hydrogen 则是面向日常编程与大规模智能体工作流的高速、高性价比模型。 [3]

### Gemini 4 Carbon 与 Gemini 4 Argon 在 Gemini Developer API 上的价格是多少？

Gemini 4 Carbon 与 Gemini 4 Argon 均不提供免费层级。在付费层级下，两款模型在 2026 年 11 月 30 日前共享促销定价：每百万输入 token $2.00、每百万输出 token（含思考 token）$10.00、每百万隐式缓存 token $0.10。自 2026 年 12 月 1 日起，两款模型的标准定价将调整为每百万输入 token $4.00、每百万输出 token $20.00 以及每百万隐式缓存 token $0.20。 [4]

### 哪些 Google One AI 订阅方案包含 Gemini 4 Carbon 与 Gemini 4 Neon？

Google AI Plus（400 GB 存储空间）包含 Gemini 4 Hydrogen。Google AI Pro（5 TB 存储空间）可在 Gemini 应用、Google Antigravity 与 Google AI Studio 中解锁 Gemini 4 Neon，并附带每月 200 个 Colab 计算单元与每月 $10 Google Cloud 抵扣金。Google AI Ultra（20 TB 存储空间起）可在 Gemini 应用与搜索 AI 模式中解锁 Gemini 4 Carbon，提供高于 AI Pro 5 倍的使用上限，以及 Project Genie 交互世界、每月 2,000 个 Colab 计算单元、每月 $40 Google Cloud 抵扣金和 YouTube Premium Family 方案。 [2]

### Gemini API 的使用层级与基于消费额的速率限制是如何运作的？

Gemini API 的速率限制按 Google Cloud 项目维度针对 RPM、TPM 与 RPD（太平洋时间午夜重置）执行，并叠加 10 分钟滚动消费上限。绑定结算账号即可解锁 Tier 1（月度上限 $250，每 10 分钟消费上限 $10）；Google Cloud 累计消费满 $100 且满 3 天可解锁 Tier 2（月度上限 $2,000，每 10 分钟消费上限 $200）；累计消费满 $1,000 且满 30 天可解锁 Tier 3（月度上限 $20,000 至 $100,000+，每 10 分钟消费上限 $200）。 [5]

## 可引用的句子

- 根据 Alphabet Inc. 于 2026 年 2 月提交的 2025 财年 Form 10-K，Gemini 模型已集成到 Google 全部 15 款 5 亿以上用户产品中，其中包括 7 款用户量超过 20 亿的产品。 [1]
- Gemini 4 模型家族由四个主要端点（gemini-4-carbon、gemini-4-neon、gemini-4-argon 与 gemini-4-hydrogen）组成，每个端点均支持 100 万 token 上下文窗口、64K / 1M 最大输出 token，以及文本、图像、音频、视频与 PDF 输入。 [3]
- 在 Gemini Developer API 中，Gemini 4 Carbon 与 Gemini 4 Argon 不支持免费层级；2026 年 11 月 30 日前每百万输入 token 定价 $2.00、输出 token（含思考 token）$10.00、隐式缓存 token $0.10，2026 年 12 月 1 日起翻倍至 $4.00 / $20.00 / $0.20。 [4]
- Google 的专用 API 阵容包括 Genie 4（通过 WebRTC / WebSockets 流式传输含 48 kHz 立体声音频的可操控 24 fps 交互世界）、Gemini Omni Flash（生成与编辑最长 15 秒含原生音频的视频）、Nano Banana 2.1（图像生成）以及 Gemini Decision 1。 [3][5]
- Gemini Developer API 执行 10 分钟滚动消费速率限制：Tier 1（月度上限 $250）为 $10，Tier 2（月度上限 $2,000，需累计消费 $100 及以上）与 Tier 3（月度上限 $20,000-$100,000+，需累计消费 $1,000 及以上且满 30 天）为 $200。 [5]
- 消费级 Google One AI 方案直接对应 Gemini 4 模型层级：Google AI Plus（400 GB）包含 Gemini 4 Hydrogen，Google AI Pro（5 TB、200 个 Colab 计算单元、每月 $10 Cloud 抵扣金）包含 Gemini 4 Neon，Google AI Ultra（20 TB+、2,000 个 Colab 计算单元、每月 $40 Cloud 抵扣金）解锁 Gemini 4 Carbon 与 Project Genie。 [2]

## 时间线

- 2023-12-19: Google DeepMind 提交 Gemini 1.0 技术报告（arXiv:2312.11805），推出其原生多模态模型家族。 [7]
- 2024-03-08: Google DeepMind 提交 Gemini 1.5 技术报告（arXiv:2403.05530），展示了跨数百万上下文 token 的多模态理解能力。 [8]
- 2025-07-07: Google DeepMind 提交 Gemini 2.5 技术报告（arXiv:2507.06261），推进了思考 token 与智能体推理能力。 [9]
- 2026-02-05: Alphabet Inc. 在 2025 财年 Form 10-K 中披露，Gemini 已驱动 Google 全部 15 款 5 亿以上用户产品，其中包括 7 款 20 亿以上用户产品。 [1]
- 2026-11-18: Google DeepMind 在 Google AI Studio 与 Google Antigravity 中发布 Gemini 4 Neon，并同步推出 Gemini 4 Carbon、Argon 与 Hydrogen 阵容。 [10]

## 来源

1. Alphabet Inc. Form 10-K for the Fiscal Year Ended December 31, 2025 (CIK 0001652044). U.S. Securities and Exchange Commission (EDGAR). 发布于 2026-02-05. https://www.sec.gov/Archives/edgar/data/1652044/000165204426000018/goog-20251231.htm (访问于 2026-11-23; tier 1: government or public registry)
2. Google AI plans with Cloud Storage - Google One. Google. https://one.google.com/about/google-ai-plans/ (访问于 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/models?auto_signin=false (访问于 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/pricing?auto_signin=false (访问于 2026-11-23; tier 3: official site)
5. Rate limits - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/rate-limits?auto_signin=false (访问于 2026-11-23; tier 3: official site)
6. Available regions for Google AI Studio and Gemini API. Google. https://aistudio.google.com/docs/available-regions?auto_signin=false (访问于 2026-11-23; tier 3: official site)
7. Gemini: A Family of Highly Capable Multimodal Models (arXiv:2312.11805). arXiv / Gemini Team Google. 发布于 2023-12-19. https://arxiv.org/abs/2312.11805 (访问于 2026-11-23; tier 2: academic or news)
8. Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context (arXiv:2403.05530). arXiv / Gemini Team Google. 发布于 2024-03-08. https://arxiv.org/abs/2403.05530 (访问于 2026-11-23; tier 2: academic or news)
9. Gemini 2.5: Pushing the Frontier with Advanced Reasoning, Multimodality, Long Context, and Next Generation Agentic Capabilities (arXiv:2507.06261). arXiv / Google DeepMind. 发布于 2025-07-07. https://arxiv.org/abs/2507.06261 (访问于 2026-11-23; tier 2: academic or news)
10. Introducing Gemini 4 Neon. Google. 发布于 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Google Gemini." 版本 efe21724, 2026-11-23. https://mimirwiki.com/zh/wiki/google-gemini
