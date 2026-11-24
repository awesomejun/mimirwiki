---
title: "Claude"
subtitle: "Anthropic, PBC 开发的 AI 助手及大语言模型系列"
canonical_url: https://mimirwiki.com/zh/wiki/claude
language: zh
page_class: entity
revision_sha256: 70e1c1e060490bc2d45ecf7d2a327c09e9162edc97822c653c67d0569fa7c3ec
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 14
alternates:
  md: https://mimirwiki.com/zh/wiki/claude.md
  txt: https://mimirwiki.com/zh/wiki/claude.txt
  json: https://mimirwiki.com/zh/wiki/claude.json
  jsonld: https://mimirwiki.com/zh/wiki/claude.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude
  ko: https://mimirwiki.com/ko/wiki/claude
  ja: https://mimirwiki.com/ja/wiki/claude
---

# Claude

> Claude 是由 Anthropic, PBC 开发、于 2023 年 3 月 14 日首次发布的 AI 助手及大语言模型系列。截至 2026-11-23，其最新模型包括 Fable 5.2、Opus 5.5、Sonnet 5.5 和 Haiku 5.5，每款模型均支持 100 万 token 上下文窗口。Claude 可通过订阅方案、API、Claude Code 及各大云平台使用。

Claude 是由总部位于美国加利福尼亚州旧金山的特拉华州公益公司（Public Benefit Corporation）Anthropic, PBC 开发的 AI 助手及大语言模型（LLM）系列。Anthropic 于 2023 年 3 月 14 日通过聊天界面和开发者 API 正式推出 Claude，随后将产品线扩展至面向终端与 IDE 软件开发的 Claude Code、面向桌面工作流的 Claude Cowork 以及 Claude Platform API。截至 2026-11-23，当前模型阵容包含 Claude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5 和 Claude Haiku 5.5，每款模型均提供 100 万 token 上下文窗口和最高 128,000 输出 token。Claude 通过 Free、Pro、Max、Ultra、Team、Enterprise 和 Education 方案、Anthropic 第一方 API 以及 Amazon Bedrock、Google Cloud 和 Microsoft Foundry 提供服务。

**别名:** Claude AI, Claude.ai, Claude Platform

## 关键事实

- **开发者:** Anthropic, PBC（加利福尼亚州旧金山） [1]
- **首次公开发布:** 2023-03-14 [3]
- **最新模型:** Claude Fable 5.2、Opus 5.5、Sonnet 5.5 和 Haiku 5.5 (截至 2026-11-23) [4]
- **上下文窗口:** 全部四款最新模型均为 100 万 token（最大输出 128K） (截至 2026-11-23) [4]
- **个人订阅方案:** Free（0 美元）、Pro（按年计费 17 美元/月或按月 20 美元/月）、Max（100 美元/月）、Ultra（200 美元/月） (截至 2026-11-23) [6]

## 事实摘要

- **开发者:** Anthropic, PBC（特拉华州公益公司） [1]
- **首次公开发布:** 2023-03-14（Claude 与 Claude Instant） [3]
- **模型系列:** Haiku、Sonnet、Opus、Fable、Mythos (截至 2026-11-23) [4]
- **最新模型:** Claude Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5 (截至 2026-11-23) [4]
- **上下文窗口与最大输出:** 1,000,000 输入 token；128,000 输出 token（最新模型） (截至 2026-11-23) [4]
- **知识与训练数据截止时间:** 2026 年 6 月（Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5） (截至 2026-11-23) [4]
- **API 基础 token 价格:** 每百万输入/输出 token 从 0.10/0.50 美元（Haiku 5.5）至 8/40 美元（Fable 5.2） (截至 2026-11-23) [5]
- **平台与客户端:** Web、桌面端、iOS、Android、Claude Code 及 Claude Platform API (截至 2026-11-23) [6]
- **云平台:** Amazon Bedrock、Claude Platform on AWS、Google Cloud、Microsoft Foundry (截至 2026-11-23) [4]
- **对齐方法:** Constitutional AI（监督自我修订与 RLAIF） [2]
- **集成协议:** 模型上下文协议（MCP，2024-11-25 开源） [11]
- **支持地区:** 185 个列明国家/地区及其属地（2026-11-12 生效政策） (截至 2026-11-23) [14]

## Claude 概述、发布历史与产品阵容

Claude 由特拉华州公益公司 [Anthropic](https://mimirwiki.com/zh/wiki/anthropic), PBC 开发，其主要行政办公地址位于加利福尼亚州旧金山 548 Market Street, PMB 90375, San Francisco, California 94104。[1] 根据 2026 年 11 月 17 日向 [SEC EDGAR](https://mimirwiki.com/zh/wiki/sec-edgar) 提交的 Form S-1 第 3 号修正案（Amendment No. 3），Anthropic 由联合创始人 Dario Amodei（首席执行官）和 Daniela Amodei（总裁）领导。[1] 在与 Notion、Quora（通过 Poe）、DuckDuckGo（用于 DuckAssist）以及 Juni Learning、Robin AI 和 AssemblyAI 等早期合作伙伴完成封闭测试后，Anthropic 于 2023 年 3 月 14 日公开发布了 Claude。[3]

在 2023 年 3 月发布时，Claude 通过聊天界面和开发者控制台 API 提供两个版本：Claude 以及更轻量、成本更低的 Claude Instant。[3] Anthropic 表示，首发版本可处理摘要、搜索、协作写作、问答和编程等任务。[3]

截至 2026-11-23，Anthropic 的产品概览列出了围绕 Claude 模型构建的更广泛产品套件，包括面向 Web、桌面端、iOS 和 Android 的 Claude 聊天应用、Claude Code、Claude Cowork、处于研究预览阶段并开放候补名单的 Claude Duet、Claude Platform、Claude Tag，以及专用产品 Claude Security 和 Claude Science。[6][7] 各类 Claude 应用的已记录功能涵盖 Artifacts、Design、Docs、Slides、Data、Sheets 与 Whiteboards（测试版）、Connectors、Plugins、Skills、Extensions、语音模式（Voice mode）、网页搜索、Research、任务定时调度、Claude in Chrome、Claude for Google Workspace 和 Claude for Microsoft 365。[6][7] 2026 年 9 月，Anthropic 开始将 Claude Cowork 与 Claude.ai 合并为单一应用，使用户能够在同一对话中自由切换聊天问答与多步骤桌面任务。[1]

## Claude 模型阵容与规格

Anthropic 将 Claude 模型划分为五个模型系列，在 Models API（`GET /v1/models`）的 `line` 字段中分别报告为 `haiku`、`sonnet`、`opus`、`fable` 和 `mythos`。[4] 截至 2026-11-23，Claude Platform Docs 列出了当前阵容中的四款模型：Claude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5 和 Claude Haiku 5.5。[4] 这四款模型均支持文本和图像输入、文本输出，并具备多语言处理、视觉理解、工具使用和自适应思考（adaptive thinking）能力。[4]

| 模型 | Claude API ID | 上下文窗口 | 最大输出 | 思考模式与默认推理力度 | 知识截止日期 | 最早退役日期 |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | `claude-fable-5-2` | 1M token | 128K token | 自适应（始终开启），high | 2026 年 6 月 | 2027 年 11 月 9 日 |
| Claude Opus 5.5 | `claude-opus-5-5` | 1M token | 128K token | 自适应（始终开启），medium | 2026 年 6 月 | 2027 年 9 月 22 日 |
| Claude Sonnet 5.5 | `claude-sonnet-5-5` | 1M token | 128K token | 自适应，high | 2026 年 6 月 | 2027 年 9 月 28 日 |
| Claude Haiku 5.5 | `claude-haiku-5-5` | 1M token | 128K token | 自适应，medium | 2026 年 6 月 | 2027 年 10 月 7 日 |

在 Claude Platform Docs 中，Anthropic 将 Claude Fable 5.2 定位为面向高难度推理与长周期智能体任务，Claude Opus 5.5 面向通用工作负载及长时间运行的智能体编程与知识工作，Claude Sonnet 5.5 面向兼顾速度与能力的场景，Claude Haiku 5.5 面向分类、提取与路由等高吞吐、低延迟敏感型任务。[4] 这四款模型的可靠知识截止时间与训练数据截止时间均列为 2026 年 6 月。[4]

截至 2026-11-23，Claude Platform Docs 还在当前四款模型之外列出了其他及早期模型，包括 Claude Mythos 5.2、Claude Fable 5.1 和 5、Claude Mythos 5.1 和 5、Claude Opus 5、4.8、4.7、4.6、4.5、4.1 和 4、Claude Sonnet 5、4.6、4.5 和 4，以及 Claude Haiku 4.5。[4] 在早期模型中，Claude Opus 4.5、Claude Sonnet 4.5、Claude Sonnet 4 和 Claude Haiku 4.5 配备 200,000 token 上下文窗口和 64,000 token 最大输出，而 Claude Opus 4.1 和 Claude Opus 4 配备 200,000 token 上下文窗口和 32,000 token 最大输出。[4]

开发者可通过 `GET /v1/models` 端点以编程方式查询模型规格，该端点支持按生命周期阶段（`active`、`deprecated` 或 `retired`）筛选，并返回 `max_input_tokens`、`max_tokens`、`line` 以及涵盖 `thinking.types.disabled`、`thinking.types.between_tools`、`server_tools`（网页搜索与代码执行）和编程式工具调用等配置的 `capabilities` 对象。[4] Anthropic 的 Form S-1/A-3 还定义了 Claude 的其他能力，包括计算机使用（computer use，通过点击、输入和导航应用程序来观察并与图形用户界面交互）以及交错思考（interleaved thinking，在单次响应中连续工具调用之间插入独立的推理步骤）。[1]

## Claude Platform API 定价与开发者功能

Claude Platform 上的 Claude API 用量以美元按每百万 token（MTok）计费，涵盖基础输入、基础输出、提示词缓存和批处理费率。[5] 截至 2026-11-23，Claude Platform Docs 公布了当前四款模型的以下费率。[5]

| 模型 | 基础输入 | 基础输出 | 缓存写入（5 分钟 / 1 小时） | 缓存命中 | 批处理输入 / 输出 |
| --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | $8 / MTok | $40 / MTok | $10 / $16 per MTok | $0.20 / MTok | $4 / $20 per MTok |
| Claude Opus 5.5 | $4 / MTok | $20 / MTok | $5 / $8 per MTok | $0.20 / MTok | $2 / $10 per MTok |
| Claude Sonnet 5.5 | $2 / MTok | $10 / MTok | $2.50 / $4 per MTok | $0.10 / MTok | $1 / $5 per MTok |
| Claude Haiku 5.5（不超过 100K token 的提示词） | $0.10 / MTok | $0.50 / MTok | $0.125 / $0.20 per MTok | $0.01 / MTok | $0.05 / $0.25 per MTok |
| Claude Haiku 5.5（超过 100K token 的提示词） | $0.50 / MTok | $2.50 / MTok | $0.625 / $1 per MTok | $0.05 / MTok | $0.25 / $1.25 per MTok |

提示词缓存在基础输入价格上采用固定倍率：5 分钟缓存写入为 1.25 倍，1 小时缓存写入为 2 倍；缓存读取倍率在 Fable 5.2、Mythos 5.2、Fable 5.1 和 Mythos 5.1 上为 0.025 倍，在 Opus 5.5 和 Sonnet 5.5 上为 0.05 倍，在其他所有模型上为 0.1 倍。[5] Batch API 为异步请求的输入和输出 token 提供 50% 折扣。[5] 快速模式（Fast mode）在支持的模型上以两倍标准价格提供最高 2.5 倍的每秒输出 token 速度（Fable 5.2 与 Mythos 5.2 为 $16/$80 per MTok，Opus 5.5 为 $8/$40 per MTok，Opus 5 与 Opus 4.8 为 $10/$50 per MTok），且不可与 Batch API 叠加使用。[5]

对于 Claude 4.6 及更新模型，通过 `inference_geo: "us"` 参数选择仅限美国地区推理时，第一方 API、Claude Platform on AWS、Anthropic 托管的 Google Cloud 部署以及 Microsoft Foundry 中的 Azure US Data Zone Standard 部署的所有 token 计费类别均适用 1.1 倍倍率。[5] Anthropic 文档指出，Claude 4.7 及更新模型（以及 Claude Mythos Preview）使用新版分词器，处理相同文本时生成的 token 数量比 Claude Sonnet 4.6 及更早模型多约 30%。[5] 在 2026-11-23 列出的其他模型中，每 MTok 的基础输入和输出价格为：Claude Mythos 5.2 为 $8/$40，Fable 5.1、Fable 5、Mythos 5.1 和 Mythos 5 为 $10/$50，Opus 5 至 Opus 4.5 为 $5/$25，Opus 4.1 和 Opus 4 为 $15/$75，Sonnet 5 为 $2/$10，Sonnet 4.6 至 Sonnet 4 为 $3/$15，Haiku 4.5 为 $1/$5。[5]

除 token 费率外，`claude.com/pricing` 截至 2026-11-23 还列出了三项 Claude Platform 功能的单独收费：Managed Agents 按每会话活跃运行小时 0.08 美元计费（另加标准 token 费用），网页搜索（Web search）按每 1,000 次搜索 10 美元计费（不含 token 用量），沙箱化 Python 代码执行（Code execution）为每个组织每日免费 50 小时，超出后按每容器每小时 0.05 美元计费。[6]

截至 2026-11-23，Claude API 执行组织级支出限额以及按每分钟请求数（RPM）、每分钟输入 token 数（ITPM）和每分钟输出 token 数（OTPM）衡量的速率限制，超出限额时返回 HTTP 429 响应。[12] 标准使用层级的月度支出上限为 Start 层级 500 美元、Build 层级 1,000 美元、Scale 层级 200,000 美元，新账户可从 Evaluation 层级起步；默认 ITPM 限额仅计算未缓存的 `input_tokens` 和 `cache_creation_input_tokens`，不计入 `cache_read_input_tokens`；Managed Agents 对创建类端点执行 300 RPM 限制，对读取类端点执行 1,200 RPM 限制。[12] 针对防火墙白名单配置，Anthropic 截至 2026-11-23 公布的固定入站 IP 网段为 `160.79.104.0/23`、`153.61.224.0/22` 及 IPv6 `2607:6bc0::/48`，用于 MCP 工具调用、网页搜索和网页抓取等出站请求的出站 IPv4 网段为 `160.79.104.0/21` 和 `153.61.208.0/20`。[13]

## Claude 个人、团队、企业与教育方案

Claude 通过 `claude.com/pricing` 公布的订阅方案面向个人用户、团队、大型企业和高校提供服务。[6] 截至 2026-11-23，定价页面列出了四个个人层级（Free、Pro、Max 和 Ultra）、包含 Standard 和 Premium 席位的 Team 层级、提供自助购买与销售协助选项的 Enterprise 层级，以及面向全校的 Education 方案。[6]

| 方案 | 公布价格（USD） | 计费方式 | 已记录配额与功能 |
| --- | --- | --- | --- |
| Free | $0 | 免费 | 受限的 5 小时及每周用量；Sonnet 与 Haiku 模型；Web、桌面端、iOS 和 Android 聊天；Artifacts、Design、Slides、Docs、网页搜索、代码执行、语音模式，最多 5 个 Projects |
| Pro | 按年计费 $17/月（年付 $200）或按月 $20/月 | 按月或按年 | 1 倍基准 5 小时及每周用量；增加 Opus 访问权限、通过用量额度使用 Fable、Claude Code、Claude Science、Claude Data、Sheets 与 Whiteboards（测试版）、Research、任务定时调度、Claude in Chrome、Microsoft 365 与 Outlook |
| Max | $100/月 | 按月 | Pro 的 5 倍 5 小时及每周用量；Fable 最高占每周限额的 50%；每月 $100 API 额度；新功能抢先体验及高流量时段优先访问 |
| Ultra | $200/月 | 按月 | 已验证账户无 5 小时限制；Pro 的 10 倍每周用量；Fable 最高占每周限额的 50%；每月 $200 API 额度；新功能抢先体验及高流量时段优先访问 |
| Team | Standard：按年 $20/席位/月（按月 $25）；Premium：按年 $100/席位/月（按月 $125） | 按月或按年（2 至 150 个席位） | 支持混合搭配席位；Premium 提供 Standard 的 5 倍用量且 Fable 最高占每周限额的 50%；增加 Claude Cowork、Claude Tag、企业搜索、项目共享、SSO、域名验证、集中计费、用量分析及每月最高 $500 共享 API 额度 |
| Enterprise | $20/席位/月基础费 + 按 API 费率计收用量 | 按年（最低 20 个席位） | 增加组织与用户支出限额、基于角色的访问控制、SCIM、审计日志、Compliance API、自定义数据保留策略、域名捕获、网络级访问控制、IP 白名单、HIPAA 就绪方案、推理钩子（inference hooks）及 Claude Security（测试版） |

在个人方案（Free、Pro、Max 和 Ultra）中，Anthropic 将模型训练列为可选择退出（opt-out），而在 Team 和 Enterprise 方案中，客户内容默认不用于模型训练。[6] 所有层级均标明根据模型不同最高支持 100 万 token 上下文窗口，用量限额则取决于所选模型、对话长度和文件大小。[6]

销售协助型 Enterprise 方案增加了自助型 Enterprise 所不具备的选项，包括 AWS Marketplace 采购渠道、咨询服务、承诺消费额阶梯激励、试用、达到相应消费门槛后的客户成功支持，以及带账期条件（net terms）的发票结算。[6] Anthropic 还面向高校提供涵盖学生、教职员工的 Education 方案，提供折扣费率、学术研究与学习模式以及专属 API 额度，其具体价格未公开列出。[6]

根据 2026 年 11 月 12 日生效的 Anthropic《支持地区政策》（Supported Regions Policy），Claude 应用（Claude.ai、Claude Code 和 Cowork）、Claude API 以及通过云平台和授权经销商提供的 Claude 模型，仅在 185 个列明国家/地区及其属地和附属领土内可用。[14] 该政策排除了身处未列明地区的个人访问，也排除了在未列明地区注册成立、设有总部或由其控股或控制的实体访问。[14]

## Claude Code、Claude Cowork 与云平台可用性

Claude Code 是 Anthropic 的智能体编程工具，最早于 2025 年 2 月以研究预览版形式推出。[1][8] 根据 Anthropic 的 Form S-1/A-3 和官方 GitHub 仓库（`anthropics/claude-code`），Claude Code 可在终端、IDE 中或通过 GitHub 上的 `@claude` 提及运行，在持久化本地环境或沙箱化云端执行环境中通过自然语言命令检查代码库，执行代码规划、编写、测试和调试，并管理 Git 工作流。[1][8] Anthropic 的 Form S-1/A-3 提到，NASA 工程师曾使用 Claude Code 为火星探测器毅力号（Perseverance）规划并编写导航指令。[1]

截至 2026-11-23，GitHub 公开仓库 `anthropics/claude-code` 累计获得 156.8k 星标、25.1k 派生分支及 1,110 次提交。[8] 截至 2026-11-23，该仓库 README 列出的安装方式包括 macOS 和 Linux 上的 Shell 脚本（`curl -fsSL https://claude.ai/install.sh | bash`）与 Homebrew cask（`brew install --cask claude-code`），以及 Windows 上的 PowerShell 脚本（`irm https://claude.ai/install.ps1 | iex`）与 WinGet（`winget install Anthropic.ClaudeCode`），而通过 npm（`@anthropic-ai/claude-code`）安装已被标记为弃用（deprecated）。[8] 为将这一智能体架构延伸至桌面知识工作，Anthropic 于 2026 年 1 月以研究预览版发布了用于读取文件、操作应用程序并在用户桌面执行多步骤工作流的 Claude Cowork，并于 2026 年 9 月开始将 Claude Cowork 与 Claude.ai 合并。[1]

除 Anthropic 第一方 API 外，Claude 模型还通过主要云平台分发。[4][5] 在 Amazon Web Services 上，Claude 模型通过 Amazon Bedrock（列出包括 Claude Fable 5.2、Opus 5.5、Sonnet 5.5 和 Haiku 5.5 在内的当前版本，并与支持自主智能体连续运行长达 8 小时的 Amazon Bedrock AgentCore 集成）以及 Claude Platform on AWS 提供。[4][5][9] 在 Google Cloud 上，Claude 模型通过 Gemini Enterprise Agent Platform 中的 Model Garden 以 Google 托管和 Anthropic 托管两种部署方式提供，截至 2026-11-23 覆盖 Fable 5 至 5.2、Opus 4.5 至 5.5、Sonnet 4.5 至 5.5 以及 Haiku 4.5 和 5.5。[4][5][10] Claude 模型同时也在 Azure 上通过 Microsoft Foundry 提供。[4][5]

截至 2026-11-23，云端计费模式因渠道而异。[5] 在合作伙伴运营的平台（Amazon Bedrock 和 Google Cloud 上 Google 托管的 Claude Models）上，由云服务商直接向客户开票，且 Claude 4.5 及更新模型的区域或多区域端点相比全球端点加收 10% 溢价。[5] 在 Anthropic 运营的云市场平台（通过 AWS Marketplace 提供的 Claude Platform on AWS 以及通过 Azure Marketplace 提供的 Microsoft Foundry 上的 Claude）上，Anthropic 按标准费率以美元计算 token 用量，以每 1 CCU 折合 0.01 美元换算为 Claude Consumption Units（CCU），按小时上报 CCU 并按月后付结算。[5]

## Claude 的 Constitutional AI 训练与模型上下文协议支持

Claude 模型采用 Constitutional AI 进行对齐，该训练方法由 Anthropic 的 Yuntao Bai 及 50 位合著者在 2022 年 12 月 15 日提交至 arXiv 的论文《Constitutional AI: Harmlessness from AI Feedback》中提出。[2][9] 在该方法下，人类监督通过一套成文规则或原则列表提供，训练分为两个阶段进行。[2] 在监督学习阶段，初始模型生成输出，依据成文原则对输出进行自我批评和修订，并利用修订后的响应进行微调。[2] 在强化学习阶段，即基于 AI 反馈的强化学习（Reinforcement Learning from AI Feedback，RLAIF），由 AI 模型对采样响应对进行评估以构建偏好数据集，随后在该数据集上训练偏好模型，并在强化学习中将该偏好模型用作奖励信号。[2] 两个阶段均可采用思维链（chain-of-thought）推理，使助手在回应有害请求时能够解释其拒绝理由。[2]

在 Anthropic 于 2026 年 11 月 17 日提交的 Form S-1/A-3 中，Constitutional AI 被定义为依据一套被称为“Claude 宪法”（Claude's constitution）的成文原则来训练模型，这些原则围绕四项优先目标组织：广泛安全（broadly safe）、广泛合乎伦理（broadly ethical）、遵守 Anthropic 准则以及真正有帮助（genuinely helpful）。[1] 借由这一过程，模型依据可审计的成文原则对自身响应进行评估、批评与修订。[1]

Claude 还通过[模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP）连接外部工具与数据系统，该开放标准由 Anthropic 的 David Soria Parra 和 Justin Spahr-Summers 创建，并于 2024 年 11 月 25 日开源。[11] MCP 定义了一种客户端-服务器架构：数据源通过 MCP 服务器对外暴露访问能力，而 AI 应用作为 MCP 客户端与其维持双向连接。[11] 发布时，Anthropic 公开了 MCP 规范与 SDK，为覆盖全部 Claude.ai 方案的 Claude Desktop 应用添加了本地 MCP 服务器支持，并发布了针对 Google Drive、Slack、GitHub、Git、Postgres 和 Puppeteer 等系统的开源预构建 MCP 服务器。[11] Anthropic 的发布公告将 Block 和 Apollo 列为集成 MCP 的早期采用者，并提到 Zed、Replit、Codeium 和 Sourcegraph 等开发者工具公司正围绕该协议开展合作。[11]

## 常见问题

### 截至 2026-11-23，最新的 Claude 模型有哪些？

截至 2026-11-23，Claude Platform Docs 列出了当前阵容中的四款模型：Claude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5 和 Claude Haiku 5.5。这四款模型均支持 100 万 token 上下文窗口、最高 128,000 输出 token、自适应思考（adaptive thinking）、视觉理解、工具使用，且知识截止日期均为 2026 年 6 月。 [4]

### Claude 订阅方案的价格是多少？

截至 2026-11-23，Claude 提供四个个人层级：Free（0 美元）、Pro（按年预付 200 美元折合每月 17 美元，或按月计费每月 20 美元）、Max（每月 100 美元）和 Ultra（每月 200 美元）。面向 2 至 150 个席位的 Team 方案列出 Standard 席位按年计费每席位每月 20 美元（按月计费 25 美元），Premium 席位按年计费每席位每月 100 美元（按月计费 125 美元）；Enterprise 方案最低 20 个席位，按年计费每席位每月 20 美元起，另按 API 费率计收使用量费用。 [6]

### Claude API 的 token 价格是多少？

截至 2026-11-23，Claude API 每百万输入和输出 token 的基础价格分别为：Claude Fable 5.2 为 8 美元和 40 美元，Claude Opus 5.5 为 4 美元和 20 美元，Claude Sonnet 5.5 为 2 美元和 10 美元。Claude Haiku 5.5 针对不超过 100,000 token 的提示词定价为每百万 token 输入 0.10 美元、输出 0.50 美元，超过 100,000 token 的提示词为输入 0.50 美元、输出 2.50 美元。Batch API 对输入和输出 token 费率提供 50% 折扣。 [5]

### 什么是 Claude Code？哪些方案包含该工具？

Claude Code 是 Anthropic 于 2025 年 2 月以研究预览版形式发布的智能体编程工具，可在终端、IDE 中运行或通过 GitHub 上的 @claude 提及触发，用于规划、编写、测试和调试代码并管理 Git 工作流。截至 2026-11-23，Claude Code 包含在 Pro、Max、Ultra、Team 和 Enterprise 方案中，不包含在 Free 方案内。 [1][6][8]

### 哪些云平台提供 Claude 模型？

截至 2026-11-23，Claude 模型在 Amazon Web Services 上通过 Amazon Bedrock 和 Claude Platform on AWS 提供，在 Google Cloud 上通过 Gemini Enterprise Agent Platform 中的 Model Garden 以 Google 托管和 Anthropic 托管两种部署方式提供，在 Azure 上则通过 Microsoft Foundry 提供。在 Amazon Bedrock 和 Google 托管的 Google Cloud 部署中，Claude 4.5 及更新模型的区域或多区域端点相比全球端点收取 10% 溢价。 [4][5][9][10]

### Constitutional AI 和模型上下文协议（MCP）与 Claude 有何关系？

Constitutional AI 由 Anthropic 研究人员于 2022 年 12 月提出，通过监督学习和基于 AI 反馈的强化学习（RLAIF），训练 Claude 模型依据一套成文原则对自身输出进行评估、批评和修订。模型上下文协议（MCP）是 Anthropic 于 2024 年 11 月 25 日开源的开放客户端-服务器标准，用于将包括 Claude Desktop 在内的 Claude 应用连接到外部数据源与工具。 [1][2][11]

## 可引用的句子

- Anthropic, PBC 于 2023 年 3 月 14 日通过聊天界面和开发者 API 正式公开发布了 Claude 与 Claude Instant。 [3]
- 截至 2026-11-23，最新的 Claude 模型阵容包括 Claude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5 和 Claude Haiku 5.5，每款模型均配备 100 万 token 上下文窗口与最高 128,000 输出 token。 [4]
- 截至 2026-11-23，Claude API 每百万输入和输出 token 的标准定价分别为：Fable 5.2 为 8 美元和 40 美元，Opus 5.5 为 4 美元和 20 美元，Sonnet 5.5 为 2 美元和 10 美元，Haiku 5.5（不超过 100,000 token 的提示词）为 0.10 美元和 0.50 美元。 [5]
- 截至 2026-11-23，Claude 个人订阅方案的定价为：Free 免费（0 美元），Pro 按年计费每月 17 美元（按月计费 20 美元），Max 每月 100 美元，Ultra 每月 200 美元。 [6]
- Anthropic 分别于 2025 年 2 月和 2026 年 1 月以研究预览版形式发布了 Claude Code 与 Claude Cowork。 [1]
- 截至 2026-11-23，Claude 模型已在 Amazon Bedrock、Claude Platform on AWS、Google Cloud 和 Microsoft Foundry 上提供。 [4][5][9][10]
- Anthropic 研究人员于 2022 年 12 月 15 日向 arXiv 提交了 Constitutional AI 论文，阐述了监督自我修订和基于 AI 反馈的强化学习（RLAIF）。 [2]
- Anthropic 于 2024 年 11 月 25 日开源了模型上下文协议（MCP）规范、SDK 及 Claude Desktop 的本地服务器支持。 [11]

## 时间线

- 2022-12-15: Anthropic 的 Yuntao Bai 及 50 位合著者向 arXiv 提交论文《Constitutional AI: Harmlessness from AI Feedback》。 [2]
- 2023-03-14: Anthropic 在与早期合作伙伴完成封闭测试后，通过聊天界面和开发者 API 公开发布 Claude 与 Claude Instant。 [3]
- 2024-11-25: Anthropic 开源模型上下文协议（MCP），发布规范、SDK、预构建服务器以及 Claude Desktop 中的本地 MCP 支持。 [11]
- 2025-02: Anthropic 以研究预览版形式发布编程智能体 Claude Code。 [1]
- 2026-01: Anthropic 以研究预览版形式发布面向多步骤桌面工作流的 Claude Cowork。 [1]
- 2026-09: Anthropic 开始将 Claude Cowork 与 Claude.ai 合并为统一应用。 [1]
- 2026-11-17: Anthropic, PBC 向美国证券交易委员会（SEC）提交 Form S-1 注册声明第 3 号修正案。 [1]

## 来源

1. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 发布于 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (访问于 2026-11-23; tier 1: government or public registry)
2. [2212.08073] Constitutional AI: Harmlessness from AI Feedback. arXiv (Bai et al., Anthropic). 发布于 2022-12-15. https://arxiv.org/abs/2212.08073 (访问于 2026-11-23; tier 2: academic or news)
3. Introducing Claude \ Anthropic. Anthropic. 发布于 2023-03-14. https://www.anthropic.com/news/introducing-claude (访问于 2026-11-23; tier 3: official site)
4. Models overview - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/models/overview (访问于 2026-11-23; tier 3: official site)
5. Pricing - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/about-claude/pricing (访问于 2026-11-23; tier 3: official site)
6. Plans & pricing | Claude by Anthropic. Anthropic. https://claude.com/pricing (访问于 2026-11-23; tier 3: official site)
7. Claude | The AI assistant for work. Anthropic. https://claude.com/product/overview (访问于 2026-11-23; tier 3: official site)
8. GitHub - anthropics/claude-code: Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands. · GitHub. Anthropic (GitHub). https://github.com/anthropics/claude-code (访问于 2026-11-23; tier 3: official site)
9. Claude by Anthropic - Models in Amazon Bedrock - AWS. Amazon Web Services. https://aws.amazon.com/bedrock/anthropic/ (访问于 2026-11-23; tier 3: official site)
10. Anthropic's Claude on Google Cloud models | Gemini Enterprise Agent Platform | Google Cloud Documentation. Google Cloud. https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/partner-models/claude (访问于 2026-11-23; tier 3: official site)
11. Introducing the Model Context Protocol \ Anthropic. Anthropic. 发布于 2024-11-25. https://www.anthropic.com/news/model-context-protocol (访问于 2026-11-23; tier 3: official site)
12. Rate limits - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/rate-limits (访问于 2026-11-23; tier 3: official site)
13. IP addresses - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/ip-addresses (访问于 2026-11-23; tier 3: official site)
14. Supported Regions Policy \ Anthropic. Anthropic. 发布于 2026-11-12. https://www.anthropic.com/supported-countries (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Claude." 版本 70e1c1e0, 2026-11-23. https://mimirwiki.com/zh/wiki/claude
