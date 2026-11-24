---
title: "Gemini 4 Neon"
subtitle: "Google DeepMind 于 2026 年 11 月发布的面向编程、科学与企业级工作流的多模态推理模型"
canonical_url: https://mimirwiki.com/zh/wiki/gemini-4-neon
language: zh
page_class: entity
revision_sha256: 5962f24b41d822c78015c9b381ebf0b9f97c0affd23ae224a247d420d2d66cbd
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/zh/wiki/gemini-4-neon.md
  txt: https://mimirwiki.com/zh/wiki/gemini-4-neon.txt
  json: https://mimirwiki.com/zh/wiki/gemini-4-neon.json
  jsonld: https://mimirwiki.com/zh/wiki/gemini-4-neon.jsonld
translations:
  en: https://mimirwiki.com/wiki/gemini-4-neon
  ko: https://mimirwiki.com/ko/wiki/gemini-4-neon
  ja: https://mimirwiki.com/ja/wiki/gemini-4-neon
---

# Gemini 4 Neon

> Gemini 4 Neon（`gemini-4-neon`）是 Google DeepMind 于 2026 年 11 月 18 日发布的多模态推理大语言模型。它基于 Gemini 4 Carbon 适配而来，在统一的 1,000,000 token 上下文窗口内处理文本、图像、音频、视频和 PDF，支持最高 64,000 同步输出 token（通过后台长解码可达 1,000,000 token），知识截止日期为 2026 年 3 月。截至 2026-11-23，其标准 API 定价为每百万输入 token 3.00 美元、每百万缓存输入 token 0.15 美元、每百万输出 token 15.00 美元。

Gemini 4 Neon 是由 Google DeepMind 开发并于 2026 年 11 月 18 日发布的多模态推理大语言模型，与 Gemini 4 Carbon、Gemini 4 Hydrogen 和 Gemini 4 Argon 共同构成第四代 Gemini 4 系列。Gemini 4 Neon（`gemini-4-neon`）基于旗舰模型 Gemini 4 Carbon 适配而来，旨在软件工程、科学研究、网络安全防御和企业级工作流中兼顾前沿分析推理能力与更低的延迟和成本。它在统一的 1,000,000 token 上下文窗口内支持文本、图像、音频、视频和 PDF 输入，默认同步输出最高支持 64,000 token，通过后台长解码最高支持 1,000,000 输出 token。截至 2026-11-23，Gemini 4 Neon 可通过 Google AI Studio 中的 Gemini API、Google Cloud Model Garden、Gemini for business 获取，并面向 Gemini 应用和 Google Antigravity 中的 Google AI Pro 及 Google AI Ultra 付费订阅用户开放。

**别名:** gemini-4-neon, Google Gemini 4 Neon, Gemini 4.0 Neon

## 关键事实

- **发布日期:** 2026-11-18（由 Google DeepMind 的 Koray Kavukcuoglu 宣布） [1]
- **API 模型代码与谱系:** gemini-4-neon（基于 Gemini 4 Carbon 适配） (截至 2026-11-23) [2]
- **上下文窗口与输出:** 100 万统一 token（默认同步输出 64K；后台长解码最高 100 万） (截至 2026-11-23) [2]
- **标准 API 定价:** 每百万 token 输入 $3.00、缓存输入 $0.15（95% 折扣）、输出 $15.00 (截至 2026-11-23) [4]
- **知识截止日期:** 2026 年 3 月 (截至 2026-11-23) [2]

## 事实摘要

- **开发者:** Google DeepMind（Alphabet Inc.） [2]
- **发布日期:** 2026-11-18 [1]
- **API 模型代码:** gemini-4-neon (截至 2026-11-23) [3]
- **基础模型谱系:** 基于 Gemini 4 Carbon 适配（Gemini 4 系列：Carbon、Neon、Hydrogen、Argon） [2]
- **支持模态:** 文本、图像、音频、视频与 PDF 输入；文本输出 (截至 2026-11-23) [3]
- **上下文窗口与输出上限:** 1,000,000 统一上下文 token；默认同步输出最高 64,000 token / 后台长解码最高 1,000,000 token (截至 2026-11-23) [2]
- **知识截止日期:** 2026 年 3 月 (截至 2026-11-23) [2]
- **标准 API 价格（全球）:** 每百万 token 输入 $3.00 / 缓存输入 $0.15 / 输出（含思考 token）$15.00 (截至 2026-11-23) [4]
- **云端 Priority 与 Batch 价格:** 每百万 token Priority 全球：输入 $5.40 / 缓存读取 $0.27 / 输出 $27.00；Batch 全球：输入 $1.50 / 缓存读取 $0.075 / 输出 $7.50 (截至 2026-11-23) [5]
- **分发渠道:** Gemini 应用、Gemini API、Google AI Studio、Gemini for business（Model Garden）、Google Antigravity (截至 2026-11-23) [2]
- **消费者订阅方案:** Google AI Pro（5 TB）与 Google AI Ultra（20 TB 以上；AI Pro 的 5 倍额度） (截至 2026-11-23) [8]

## Gemini 4 Neon 概述、发布及在 Gemini 4 系列中的定位

Gemini 4 Neon 是由 Google DeepMind 开发的多模态推理大语言模型，于 2026 年 11 月 18 日由 Google DeepMind 高级副总裁兼 Google 首席 AI 架构师 Koray Kavukcuoglu 署名发布。[1][2] 截至 2026-11-23，根据 Google AI Studio 文档中列出的 [Google Gemini](https://mimirwiki.com/zh/wiki/google-gemini) 4 模型目录，Google 提供四款以化学元素命名的模型：Gemini 4 Carbon（`gemini-4-carbon`）、Gemini 4 Neon（`gemini-4-neon`）、Gemini 4 Hydrogen（`gemini-4-hydrogen`）和 Gemini 4 Argon（`gemini-4-argon`）。[3]

根据 Google DeepMind 于 2026 年 11 月 18 日发布的模型卡，Gemini 4 Neon 基于 Gemini 4 Carbon 适配而来，并与 Carbon 共享底层架构、训练数据集、数据处理流水线以及硬件和软件基础设施。[2] Google 将 Gemini 4 Carbon 定位于最具挑战性的长周期项目，将 Gemini 4 Hydrogen 定位于高速日常任务，而将 Gemini 4 Neon 设计为中档前沿层级，将分析深度与更快的端到端执行速度及更低的单任务成本相结合；它既可独立运行，也可在 Google Antigravity 中作为编排器调度并行运行的 Gemini 4 Hydrogen 子智能体。[1][2]

截至 2026-11-23，Gemini 4 Neon 通过五个官方渠道分发：Gemini 应用、Gemini Developer API、Google AI Studio、Gemini for business（含 Google Cloud Model Garden）以及智能体开发平台 Google Antigravity。[1][2] 在消费者和专业用户侧，Google One 将 Gemini 4 Neon 的访问权限打包进 Google AI Pro 方案（包含 5 TB 存储空间、每月 200 个 Google Colab 计算单元及每月 10 美元 Google Cloud 赠金）和 Google AI Ultra 方案（20 TB 存储空间起，额外包含 Gemini 4 Carbon，提供 AI Pro 5 倍的 Gemini 使用额度，并包含每月 2,000 个 Colab 计算单元和每月 40 美元 Google Cloud 赠金），而入门级的 Google AI Plus 方案（400 GB 存储空间）则包含 Gemini 4 Hydrogen。[8]

## Gemini 4 Neon 技术规格、模态与长解码架构

根据截至 2026-11-23 的 Gemini API 文档与 Google DeepMind 模型卡，Gemini 4 Neon（`gemini-4-neon`）在最高 1,000,000 token 的统一输入输出上下文窗口内原生支持文本字符串、图像、音频、视频文件和 PDF 文档输入。[1][2][3] 在生成方面，该模型默认同步输出最高支持 64,000 token，使用后台长解码时最高支持 1,000,000 输出 token。[2][3][4] 模型卡标明 Gemini 4 Neon 的知识截止日期为 2026 年 3 月。[2]

| 规格项目 | Gemini 4 Neon（`gemini-4-neon`） |
| --- | --- |
| 开发者 | Google DeepMind（Alphabet Inc.） |
| 发布日期 | 2026 年 11 月 18 日 |
| 基础架构与谱系 | 基于 Gemini 4 Carbon（`gemini-4-carbon`）适配 |
| 输入模态 | 文本、图像、音频、视频、PDF |
| 输出模态 | 文本（含推理 / 思考 token） |
| 上下文窗口 | 1,000,000 统一输入输出 token |
| 最大输出 token | 默认同步 64,000 / 后台长解码最高 1,000,000 |
| 知识截止日期 | 2026 年 3 月 |
| Gemini API 缓存支持 | 隐式上下文缓存 $0.15 / 1M token（不支持显式缓存） |

Gemini 4 Neon 支持可配置的思考级别（包括默认的 `high` 与 `xhigh`）、长周期多轮智能体会话中的上下文压缩（context compaction），以及包括 [模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP）服务器和 Google Antigravity 中 `/swarm` 多智能体执行在内的工具编排能力。[1] 在发布博文中，Google 通过四项参考构建展示了 Gemini 4 Neon 在 Google Antigravity 中的长解码与智能体集群能力：驱动 Blender MCP 渲染带有 Carbon 与 Hydrogen 本生灯火焰及 Argon 与 Neon 气体放电管的 3D 实验台；在不使用任何预制素材的情况下，基于勃朗峰和霞慕尼高程数据编写 10,200 行自定义着色器的 WebGL2 自由式滑雪模拟器并实现 120 Hz 物理引擎；以交互式 3D 形式重建 1936 年艾伦·图灵位于剑桥大学国王学院的书房（X.8 室）并配备可运行的通用图灵机；以及在不嵌入图像或使用 Apps Script 的前提下，通过超过 500,000 条实时电子表格公式将单张照片转换为包含 100,000 个单元格的 Google 表格，实现边缘检测、3D 深度映射与场景重打光。[1]

## Gemini 4 Neon API 与 Google Cloud 定价、缓存及速率限制

Gemini 4 Neon 仅通过 Gemini Developer API 的付费层级（免费层级不提供）以及 Google Cloud Model Garden 提供。[4][5] 模型处理的每一个 token 均会被计量和计费，包括内部思考 token，以及启用接地（grounding）时的工具系统指令或函数声明。[4] 在 Gemini Developer API 上，Gemini 4 Neon 的上下文缓存仅支持隐式缓存，定价为每百万缓存输入 token 0.15 美元（较 3.00 美元基础输入单价优惠 95%）；Google 搜索接地（Grounding with Google Search）在 Gemini 3 及更新模型之间共享每月 5,000 次免费搜索请求，超出后按每 1,000 次请求 14.00 美元计费（默认每日上限为 1,500 次请求）。[1][4][6]

在 Google Cloud Model Garden（Agent Platform）上，截至 2026-11-23 的定价依据 Standard、Priority 和 Batch 三种处理模式以及全球端点与非全球（区域）端点而有所不同，显式缓存写入计费计划于 2027 年 1 月 12 日生效。[5]

| 平台与服务层级（截至 2026-11-23） | 端点区域 | 输入（文本、图像、视频、音频） | 缓存读取 | 缓存写入（2027-01-12 生效） | 文本输出（响应与推理） |
| --- | --- | --- | --- | --- | --- |
| Gemini Developer API（付费层级） | 全球 | $3.00 / 1M | $0.15 / 1M（隐式） | 不支持 | $15.00 / 1M |
| Google Cloud Model Garden - Standard | 全球 | $3.00 / 1M | $0.15 / 1M | $3.75 / 1M | $15.00 / 1M |
| Google Cloud Model Garden - Standard | 非全球 | $3.30 / 1M | $0.165 / 1M | $4.125 / 1M | $16.50 / 1M |
| Google Cloud Model Garden - Priority | 全球 | $5.40 / 1M | $0.27 / 1M | $6.75 / 1M | $27.00 / 1M |
| Google Cloud Model Garden - Priority | 非全球 | $5.94 / 1M | $0.297 / 1M | $7.425 / 1M | $29.70 / 1M |
| Google Cloud Model Garden - Batch | 全球 | $1.50 / 1M | $0.075 / 1M | $1.875 / 1M | $7.50 / 1M |
| Google Cloud Model Garden - Batch | 非全球 | $1.65 / 1M | $0.0825 / 1M | $2.0625 / 1M | $8.25 / 1M |

在 Google Cloud 上，客户仅需为返回 HTTP 200 状态码的请求付费，4xx 和 5xx 响应不产生 token 费用。[5] 在 Gemini Developer API 上，各使用层级适用项目级速率限制和基于支出的速率限制：Tier 1（关联有效结算账号，月结算上限 250 美元，每 10 分钟滚动窗口支出上限 10 美元）、Tier 2（累计支出 100 美元且满 3 天，结算上限 2,000 美元，每 10 分钟窗口上限 200 美元）和 Tier 3（累计支出 1,000 美元且满 30 天，结算上限 20,000 美元至 100,000 美元以上，每 10 分钟窗口上限 200 美元），超出限制时返回 `429 RESOURCE_EXHAUSTED`。[6]

## Gemini 4 Neon 基准评测

在 2026 年 11 月 18 日发布的 Gemini 4 Neon 模型卡与发布公告中，Google DeepMind 公布了在能力指数、智能体编程、企业知识工作、科学与数学推理、多模态理解、长上下文检索以及网络安全等维度上，将 Gemini 4 Neon 与 [Claude](https://mimirwiki.com/zh/wiki/claude) Opus 5.5 及 OpenAI 的 [GPT-6.2](https://mimirwiki.com/zh/wiki/gpt-6-2) Sol 进行对比的基准评测结果。[1][2]

| 类别 | 基准测试 | Gemini 4 Neon | Claude Opus 5.5 | GPT-6.2 Sol |
| --- | --- | --- | --- | --- |
| 能力指数 | Artificial Analysis Intelligence Index v5.0.1 | 61 | 59 | 57 |
| 能力指数 | Vals Index v2.2 | 70.9% | 70.1% | 66.1% |
| 智能体编程 | CursorBench 4.1 | 65.4% | 58.1% | 未报告 |
| 智能体编程 | Terminal-Bench 4.1（作弊校正后） | 65.2% | 65.8% | 61.5% |
| 智能体编程 | FrontierCode 2.0（主分数） | 46.2% | 47.3% | 43.8% |
| 智能体编程 | SWE-sweep（提供商框架 / mini-SWE 框架） | 39.0% / 12.8% | 10.1% / 3.6% | 8.3% / 11.6% |
| 知识工作 | Zapier AutomationBench | 56.3% | 42.5% | 41.3% |
| 知识工作 | Agents' Last Exam v1.1 | 75.8% | 71.6% | 73.0% |
| 科学与数学 | RiemannBench | 84.0% | 80.0% | 80.0% |
| 科学与数学 | Terminal-Bench-Science 0.1 | 70.5% | 63.3% | 68.0% |
| 推理 | HLE-Diamond | 71.3% | 67.9% | 64.0% |
| 多模态 | MKA Climb WSR / Chartography / LVBench | 56.5% / 73.5% / 89.0% | 53.0% / 66.3% / 83.7% | 52.7% / 75.1% / 87.6% |
| 长上下文 | GraphWalks（256K 至 1M，BFS F1） | 95.2% | 66.8% | 80.1% |
| 网络安全 | CWE-Bench v2 / SEC-bench Pro / WebExploitBench v1.2 | 70.7% / 90.5% / 51.3% | 67.1% / 未报告 / 37.1% | 66.0% / 88.3% / 未报告 |

除模型卡表格外，Google 还报告称，Gemini 4 Neon 在 Artificial Analysis Coding Agent Index 中位列总排名第 1（58.6 分），在 Legal Research Bench 和 Tax Agent Bench 中位列第 1，在 Andon Labs 的 Vending-Bench 2 中位列第 1（模拟企业净资产 16,843 美元），并在涵盖超过 4,200 次真实世界智能体会话的 Arena Agent Arena Index 中位列全球第 2（1336 Elo，可控性排名第 2）。[1] Artificial Analysis 也于 2026 年 11 月 18 日指出，Gemini 4 Neon 在单任务成本降低约 17% 的同时，相比 Gemini 4 Carbon 实现了小幅智能提升。[9]

## Gemini 4 Neon 安全性评测、局限性与区域可用性

根据 Gemini 4 Neon 模型卡，该模型面向长时间运行的智能体工作流、迭代式代码仓库编程与调试、多模态知识工作以及防御性网络安全运营，包括安全代码生成、渗透测试以及漏洞发现、验证与修补。[2] Google 报告称，在内部 Google Antigravity 测试中，Gemini 4 Neon 录得了迄今为止所有受测 Gemini 模型中最低的虚构率（fabrication rate）。[1]

在将 Gemini 4 Neon 与 Gemini 4 Hydrogen 进行对比的内部自动化开发安全评测中，Google DeepMind 报告称，Gemini 4 Neon 在文本到文本内容安全（差距为 0.00 个百分点）、多语言安全和图像到文本安全方面均表现相当，所有差异均落在统计置信区间内。[2] 其拒绝语气与 Gemini 4 Hydrogen 保持相近，同时对良性多模态提示词的不合理拒绝有所减少。[2]

模型卡中记录的局限性包括开放式问题或超出知识截止日期查询中的潜在幻觉、2026 年 3 月的知识截止日期，以及在 Gemini 4 Carbon 安全与安保框架下持续推进的前沿安全与抗越狱缓解措施。[2] 截至 2026-11-23，Google 的可用区域文档列出了超过 215 个支持 Google AI Studio 和 Gemini Developer API 的国家和地区，而位于这些区域之外的用户则被引导使用 Google Cloud 上的 Gemini Enterprise Agent Platform。[7]

## 常见问题

### 什么是 Gemini 4 Neon，它在 Gemini 4 模型系列中处于什么定位？

Gemini 4 Neon（`gemini-4-neon`）是 Google 与 Google DeepMind 于 2026 年 11 月 18 日发布的多模态推理大语言模型。该模型基于规模更大的旗舰模型 Gemini 4 Carbon 适配而来，定位介于面向最高难度长周期推理的 Gemini 4 Carbon 与面向日常高速执行的 Gemini 4 Hydrogen 之间，在前沿推理深度、更快的任务完成速度与更低的单任务成本之间取得平衡。 [1][2][3]

### Gemini 4 Neon 的上下文窗口、支持模态和知识截止日期是什么？

Gemini 4 Neon 在统一的 1,000,000 token 输入输出上下文窗口内支持文本、图像、音频、视频和 PDF 文件输入，文本输出在默认同步模式下最高可达 64,000 token，通过后台长解码最高可达 1,000,000 token。根据 Google DeepMind 于 2026 年 11 月 18 日发布的模型卡，该模型的知识截止日期为 2026 年 3 月。 [2][3][4]

### Gemini 4 Neon 在 Gemini API 和 Google Cloud 上的价格是多少？

截至 2026-11-23，Gemini Developer API（仅限付费层级，免费层级不提供）和 Google Cloud Model Garden 全球端点的标准定价为每百万输入 token 3.00 美元、每百万缓存输入 token 0.15 美元（95% 折扣）、每百万输出 token（含思考 token）15.00 美元。在 Google Cloud Model Garden 上，全球端点的 Priority 定价为每百万 token 输入 5.40 美元、缓存读取 0.27 美元、输出 27.00 美元；Batch 定价为每百万 token 输入 1.50 美元、缓存读取 0.075 美元、输出 7.50 美元；非全球区域端点需加收 10% 溢价。 [1][4][5]

### 哪些 Google 订阅方案和开发者平台包含 Gemini 4 Neon？

截至 2026-11-23，开发者可通过 Google AI Studio 中的 Gemini API 付费层级以及 Google Cloud 上的 Gemini for business 和 Model Garden 使用 Gemini 4 Neon。对于个人及专业消费者订阅用户，Gemini 4 Neon 包含在 Google AI Pro 方案（含 5 TB 存储空间）和 Google AI Ultra 方案（20 TB 存储空间起，提供 AI Pro 5 倍的 Gemini 使用额度）中，可在 Gemini 应用、Google Antigravity 和 Google AI Studio 中使用。 [1][2][4][8]

### Gemini 4 Neon 在编程、科学和企业级基准测试中的表现如何？

根据 Google DeepMind 于 2026 年 11 月 18 日发布的公告和模型卡，Gemini 4 Neon 在 Artificial Analysis Intelligence Index v5.0.1 中获得 61 分（xhigh 思考设置下总排名第 3），在 Artificial Analysis Coding Agent Index 中获得 58.6 分（总排名第 1），在 Vals Index v2.2 中获得 70.9%（总排名第 2），在 Zapier 的 AutomationBench 中获得 56.3%（总排名第 1），在 Andon Labs 的 Vending-Bench 2 中获得 16,843 美元（总排名第 1），在 RiemannBench 中获得 84.0%，在 Terminal-Bench-Science 0.1 中获得 70.5%，在 HLE-Diamond 中获得 71.3%，在 GraphWalks（256K-1M BFS）中获得 95.2%，并在 Google Antigravity 提供商评测框架下的 SWE-sweep 中获得 39.0%。 [1][2]

## 可引用的句子

- Google DeepMind 于 2026 年 11 月 18 日发布了 Gemini 4 Neon，作为基于 Gemini 4 Carbon 适配的中档多模态推理模型。 [1][2]
- Gemini 4 Neon（API 模型代码为 gemini-4-neon）在统一的 1,000,000 token 上下文窗口内支持文本、图像、音频、视频和 PDF 输入，默认同步输出最高支持 64,000 token，通过后台长解码（background long decode）最高支持 1,000,000 输出 token。 [2][3]
- 截至 2026-11-23，Gemini 4 Neon 在 Gemini Developer API 和 Google Cloud Model Garden（全球端点）上的标准定价为每百万输入 token 3.00 美元、每百万缓存输入 token 0.15 美元、每百万输出 token（含思考 token）15.00 美元。 [1][4][5]
- 截至 2026-11-23，Google Cloud Model Garden 对 Gemini 4 Neon 的全球推理定价为：Priority 模式每百万 token 输入 5.40 美元 / 缓存读取 0.27 美元 / 输出 27.00 美元，Batch 模式每百万 token 输入 1.50 美元 / 缓存读取 0.075 美元 / 输出 7.50 美元，非全球区域端点需加收 10% 溢价。 [5]
- Google DeepMind 发布的 Gemini 4 Neon 模型卡标明其知识截止日期为 2026 年 3 月。 [2]
- 在 Google DeepMind 于 2026 年 11 月公布的基准评测中，Gemini 4 Neon 在 Artificial Analysis Intelligence Index v5.0.1 获得 61 分，在 Artificial Analysis Coding Agent Index 获得 58.6 分（总排名第 1），在 Vals Index v2.2 获得 70.9%，在 AutomationBench 获得 56.3%，在 RiemannBench 获得 84.0%，在 Google Antigravity 框架下的 SWE-sweep 获得 39.0%。 [1][2]
- 截至 2026-11-23，Gemini 4 Neon 通过 Google AI Studio 中的 Gemini API（仅限付费层级）、Google Cloud Model Garden 与 Gemini for business 提供，并向 Gemini 应用及 Google Antigravity 中的 Google AI Pro 和 Google AI Ultra 订阅用户开放。 [1][2][8]

## 时间线

- 2026-03: Google DeepMind 发布的 Gemini 4 Neon 模型卡中记录的知识截止日期。 [2]
- 2026-11-18: Google DeepMind 在 Gemini 应用、Gemini API、Google AI Studio、Gemini for business 和 Google Antigravity 上发布 Gemini 4 Neon（gemini-4-neon），并公布 Gemini 4 Neon 模型卡。 [1][2][9]
- 2027-01-12: Google Cloud Model Garden 针对 Gemini 4 Neon 的缓存写入计费（Standard 全球 $3.75/1M、Priority 全球 $6.75/1M、Batch 全球 $1.875/1M）计划生效日期。 [5]

## 来源

1. Introducing Gemini 4 Neon. Google (The Keyword). 发布于 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (访问于 2026-11-23; tier 3: official site)
2. Gemini 4 Neon - Model Card - Google DeepMind. Google DeepMind. 发布于 2026-11-18. https://deepmind.google/models/model-cards/gemini-4-neon/ (访问于 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/models?auto_signin=false (访问于 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/pricing?auto_signin=false (访问于 2026-11-23; tier 3: official site)
5. Agent Platform Pricing | Google Cloud. Google Cloud. https://cloud.google.com/model-garden/pricing (访问于 2026-11-23; tier 3: official site)
6. Rate limits - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/rate-limits?auto_signin=false (访问于 2026-11-23; tier 3: official site)
7. Available regions for Google AI Studio and Gemini API - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/available-regions?auto_signin=false (访问于 2026-11-23; tier 3: official site)
8. Google AI plans with Cloud Storage - Google One. Google One. https://one.google.com/about/google-ai-plans/ (访问于 2026-11-23; tier 3: official site)
9. Google continues to accelerate its release cadence with Gemini 4 Neon | Artificial Analysis. Artificial Analysis. 发布于 2026-11-18. https://artificialanalysis.ai/articles/gemini-4-neon-intelligence-gain (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "Gemini 4 Neon." 版本 5962f24b, 2026-11-23. https://mimirwiki.com/zh/wiki/gemini-4-neon
