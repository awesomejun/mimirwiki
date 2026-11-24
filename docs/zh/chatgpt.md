---
title: "ChatGPT"
subtitle: "OpenAI 开发的用于聊天、办公任务、网页搜索与软件开发的对话式 AI 应用"
canonical_url: https://mimirwiki.com/zh/wiki/chatgpt
language: zh
page_class: entity
revision_sha256: 4778c55d12356c8ac1c07b92ff77fa8d47f60a508084876d4d12998b846a0c70
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 13
alternates:
  md: https://mimirwiki.com/zh/wiki/chatgpt.md
  txt: https://mimirwiki.com/zh/wiki/chatgpt.txt
  json: https://mimirwiki.com/zh/wiki/chatgpt.json
  jsonld: https://mimirwiki.com/zh/wiki/chatgpt.jsonld
translations:
  en: https://mimirwiki.com/wiki/chatgpt
  ko: https://mimirwiki.com/ko/wiki/chatgpt
  ja: https://mimirwiki.com/ja/wiki/chatgpt
---

# ChatGPT

> ChatGPT 是由 OpenAI 开发并于 2022 年 11 月 30 日推出的对话式 AI 应用。截至 2026-11-23，它在网页端、桌面端和移动端客户端中整合了聊天、网页搜索、用于文档与电子表格处理的 ChatGPT Work 以及 Codex 编程代理。OpenAI 提供 Free、Go、Plus、三档 Pro、Business、Enterprise 和 Edu 订阅方案。

ChatGPT 是由 OpenAI 开发的对话式人工智能软件应用，提供文本对话、网页搜索、语音交互、图像生成、通过 ChatGPT Work 实现的文档创作以及通过 Codex 提供的编程辅助功能。OpenAI 于 2022 年 11 月 30 日推出 ChatGPT，最初是构建在 GPT-3.5 系列模型上的免费研究预览版，该模型在 Azure AI 超级计算基础设施上通过人类反馈强化学习（Reinforcement Learning from Human Feedback，RLHF）训练而成。截至 2026-11-23，ChatGPT 在网页端、macOS、Windows、iOS 和 Android 上提供服务，覆盖个人 Free、Go、Plus 与三档 Pro 订阅方案，以及面向组织的 Business、Enterprise 和 Edu 方案。OpenAI 声明，根据其商业条款和企业隐私政策，ChatGPT Business 中的客户工作区数据不用于模型训练。

**别名:** ChatGPT Work, ChatGPT Search, ChatGPT Business, ChatGPT Enterprise

## 关键事实

- **开发商:** OpenAI [2]
- **首次发布:** 2022-11-30 [2]
- **Pro 按月档位:** Pro 100（100 美元/月）、Pro 200（200 美元/月）、Pro 500（500 美元/月） (截至 2026-11-23) [6]
- **Business Standard 席位:** 按年计费每用户每月 20 美元，按月计费每用户每月 25 美元 (截至 2026-11-23) [7]
- **Business 数据训练政策:** OpenAI 不使用 ChatGPT Business 工作区数据训练模型 (截至 2026-11-23) [7]

## 事实摘要

- **开发商:** OpenAI [2]
- **首次发布:** 2022 年 11 月 30 日 [2]
- **初始基础模型:** GPT-3.5 系列（采用 RLHF 和 PPO 训练） [2]
- **官方网站:** https://chatgpt.com [3]
- **支持平台:** 网页端、macOS 桌面端、Windows 桌面端及移动端 (截至 2026-11-23) [3]
- **个人方案:** Free、Go、Plus 和 Pro（三个按月用量档位） (截至 2026-11-23) [4]
- **Pro 按月定价:** Pro 100（100 美元/月）、Pro 200（200 美元/月）、Pro 500（500 美元/月） (截至 2026-11-23) [6]
- **Business 席位定价:** Standard 年付 20 美元/用户/月（月付 25 美元）；Premium 年付 100 美元/用户/月（月付 125 美元） (截至 2026-11-23) [7]
- **组织方案:** Business、Enterprise、Edu、Health、Gov 及 ChatGPT for Teachers (截至 2026-11-23) [8]
- **ChatGPT Search 发布:** 2024 年 10 月 31 日（自 2025 年 2 月 5 日起支持免注册访问） [10]
- **集成产品:** ChatGPT Work 与 Codex（涵盖 Free 至 Enterprise 全系列方案） (截至 2026-11-23) [9]
- **开放协议采用:** Model Context Protocol（MCP） (截至 2025-12-09) [12]
- **支持地区:** 列表收录 208 个国家和地区（OpenAI 官方支持国家目录） (截至 2026-11-23) [13]

## ChatGPT 发布、训练背景与核心产品支柱

ChatGPT 由 [OpenAI](https://mimirwiki.com/zh/wiki/openai) 于 2022 年 11 月 30 日推出，最初是面向对话交互打造的免费研究预览版。[2] OpenAI 将其初始版本描述为 InstructGPT 的姊妹模型，基于 2022 年初在 Azure AI 超级计算基础设施上完成训练的 GPT-3.5 系列模型微调而成。[2] 微软在以 CIK 0000789019 提交至 [SEC EDGAR](https://mimirwiki.com/zh/wiki/sec-edgar) 的截至 2026 年 6 月 30 日财年 Form 10-K 报告中，披露了其与 OpenAI 的长期战略合作伙伴关系。[1]

OpenAI 采用人类反馈强化学习（RLHF）训练初始 ChatGPT 模型。[2] 人类 AI 训练师首先同时扮演用户和助手撰写对话，生成监督微调数据，OpenAI 将其与转换为对话格式的 InstructGPT 数据集合并。[2] 随后，OpenAI 收集对多个模型备选回复的排序比较数据以训练奖励模型，并使用近端策略优化（PPO）进行迭代微调。[2] 发布之初，OpenAI 指出了五项局限：生成看似合理实则错误或无意义的答案、对提示词措辞敏感、回复冗长并反复出现套话、面对模糊输入时自行猜测意图，以及即便通过 Moderation API 监测仍偶尔出现不安全或有偏见的输出。[2]

截至 2026-11-23，OpenAI 围绕三大核心产品领域组织 ChatGPT：用于日常问答、写作、网页搜索、语音对话和图像生成的 Chat；结合 Gmail 与 Slack 等已连接工具创建和编辑文档、幻灯片、电子表格、图表及 PDF 的 ChatGPT Work；以及覆盖规划、编码、测试、审查与发布全流程的软件工程工具 Codex。[3] ChatGPT 支持网页端、iOS 和 Android，其中整合了 Chat、Work 与 Codex 的体验在 macOS 和 Windows 桌面端面向所有方案开放，在网页端和移动端面向 Plus、Pro、Business、Enterprise 和 Edu 方案开放。[3][4][9] 截至 2026-11-23，ChatGPT 概览页面还列出了 Deep Research、Voice、Study Mode、Plugins、Sites、Space、Dots、Health 和 Finance 等其他产品领域。[3]

## ChatGPT 个人方案、模型与定价

截至 2026-11-23，ChatGPT 提供四个个人订阅档位：Free、Go、Plus 和 Pro，其中 Pro 按月度用量进一步划分为三个档位。[4][6] OpenAI 于 2025 年 8 月在印度率先推出 ChatGPT Go，随后扩展至另外 170 个国家，并于 2026 年 1 月 16 日在全球发布。[5] 在 2026 年 1 月 16 日的公告中，OpenAI 公布美国地区定价为 ChatGPT Go 每月 8 美元（部分市场采用本地化定价）、ChatGPT Plus 每月 20 美元、ChatGPT Pro 每月 200 美元。[5] 在同一公告中，OpenAI 表示计划在美国的 Free 档位和 ChatGPT Go 中开始测试广告，同时保持 Plus、Pro、Business 和 Enterprise 无广告。[5] 截至 2026-11-23，ChatGPT 定价页面在 Go 方案中显示有广告提示。[4]

截至 2026-11-23，OpenAI 以三个仅支持按月计费、无按年计费选项的档位提供 ChatGPT Pro：每月 100 美元的 Pro 100、每月 200 美元的 Pro 200 和每月 500 美元的 Pro 500。[6] Pro 200 包含的用量高于 Pro 100，而 Pro 500 提供最高的包含额度，且是唯一支持 GPT-6 Astra 与 GPT-6.1 Sol 的 Ultrafast 模式的 Pro 档位。[6] 与同一模型的 Standard 模式相比，Fast 模式以 2.5 倍速率消耗包含额度，Ultrafast 模式以 8 倍速率消耗包含额度，超出后按 Standard 额度费率的 6 倍从已购买额度中扣除。[6] Pro 订阅者可在包含额度之外购买额度，用于 Codex、ChatGPT Work、ChatGPT for Word、ChatGPT for Excel 和 ChatGPT for PowerPoint 中符合条件的用量。[6]

| 方案 | 公布美国价格 | GPT Instant 上下文窗口（约最大输入） | GPT Reasoning 上下文窗口（约最大输入） | 模型与功能访问权限（截至 2026-11-23） |
| --- | --- | --- | --- | --- |
| Free | 每月 0 美元 | 27K token（约 12 页） | 动态变化 | 使用 GPT-6 进行无限制日常文本对话（受防滥用护栏约束）、GPT-6 Luna、GPT-5 Thinking Mini、Search、Voice、Projects、Plugins、受限文件上传、受限桌面端 Work 与 Codex |
| Go | 每月 8 美元（2026-01-16 公布，部分市场本地化定价） | 54K token（约 40 页） | 256K token（约 320 页） | 包含 Free 全部功能，并提供更高的消息、上传和图像额度、更长记忆、支持视频的 Voice、定时任务；可能包含广告 |
| Plus | 每月 20 美元（2026-01-16 公布） | 54K token（约 40 页） | 256K token（约 320 页） | 无广告的 Go 功能，外加 GPT-6.1 Sol、GPT-6 Astra、GPT-6 Sol、GPT-5.6 模型、旧版模型、Fast 响应速度、Sites、扩展版 Codex，以及桌面端、网页端和移动端 Work |
| Pro（Pro 100 / Pro 200 / Pro 500） | 每月 100、200 或 500 美元（仅按月计费，截至 2026-11-23） | 128K token（约 250 页） | 400K token（约 680 页） | 包含 Plus 全部功能，外加 GPT-5.6 Sol Pro、扩展的 GPT-6 系列访问权限、Dots、ChatGPT Space、月度 API 额度，以及 Pro 500 专属的 Ultrafast 模式 |

在所有个人方案中，OpenAI 均声明无限制访问受防滥用护栏约束；ChatGPT Pro 文档同时明确，根据使用条款，禁止共享账号凭据、转售访问权限以及自动提取数据。[4][6] 截至 2026-11-23，ChatGPT 定价页面还列出了面向生命科学研究的 Rosalind Academic Plan。[4]

## ChatGPT Business、Enterprise、Edu 与基于额度的定价体系

ChatGPT Business 是 OpenAI 面向组织的自助式共享工作区方案，于 2025 年 8 月 29 日由 ChatGPT Team 更名而来。[7] 组织可从 1 个付费席位开始创建 ChatGPT Business 工作区，通过 Workspace settings 或 Admin Console 管理成员与角色，并在用户间分配或重新分配席位容量。[7] 截至 2026-11-23，ChatGPT Business 提供 Standard 席位和 Premium 席位，允许工作区混合配置两种席位，并支持购买工作区额度以突破包含的速率上限。[7] 2026 年 6 月 24 日之前创建的工作区还曾可使用旧版 Codex 席位类型。[7]

| 席位类型 | 按月计费（USD） | 按年计费（USD） | 包含权限（截至 2026-11-23） |
| --- | --- | --- | --- |
| Standard 席位 | 每用户每月 25 美元 | 每用户每月 20 美元 | ChatGPT、ChatGPT Work、Codex、GPTs、Projects、Apps、Company Knowledge、ChatGPT Agent 与 Deep Research |
| Premium 席位 | 每用户每月 125 美元 | 每用户每月 100 美元 | 包含 Standard 席位权限，并提供更高的 ChatGPT Work 和 Codex 用量上限，且无 5 小时用量限制 |

ChatGPT Enterprise、ChatGPT Edu、Health、Gov 和 ChatGPT for Teachers 服务于更大规模或特定领域的部署，其中 Enterprise 作为由销售团队主导的合同制方案，面向需要发票结算、采购订单、电汇或 ACH 转账、账期付款条件、零数据保留（Zero Data Retention）或商业伙伴协议（BAA）的组织。[7][8] ChatGPT 订阅独立于 OpenAI API 平台，API 用量单独计费。[7][8]

针对采用基于额度的灵活定价（credit-based flexible pricing）的 ChatGPT Business、Enterprise、Edu、Health、Gov 和 ChatGPT for Teachers 工作区，OpenAI 发布了额度费率表，涵盖按单位固定计费的 Chat 项目以及按 token 计费的 Work 和 Codex 项目。[8] 采用基于额度灵活定价的 Enterprise 和 Edu 工作区可通过额度扩展用量而无固定速率限制，且 ChatGPT Edu 在消耗额度之前包含每日图像用量预算及每滚动 24 小时 5 次 Deep Research 查询。[8] 截至 2026-11-23，额度费率表列出的单次 Chat 与功能费率如下：Instant 消息在防滥用护栏约束下不限次数；GPT-6（GPT-6 Sol）和 GPT-5.6 Sol 为每条消息 10 额度；面向部分 Enterprise 方案的 GPT-5.5 Rosalind Research 与 Discovery 为每条消息 20 额度；GPT-6 Pro（由 GPT-6 Astra 驱动）和 GPT-5.6 Sol Pro 为每条消息 50 额度；Agent 模式为每条消息 30 额度；Deep Research 为每项任务 50 额度；Voice 为每分钟 1.25 额度。[8]

## ChatGPT Search 与出版商合作

ChatGPT Search 是内置于 ChatGPT 的网页搜索功能，继 2024 年 7 月 25 日公布 SearchGPT 原型后，由 OpenAI 于 2024 年 10 月 31 日正式推出。[10] 在 2024 年 10 月 31 日上线时，OpenAI 在 `chatgpt.com` 及桌面端和移动端应用中面向 ChatGPT Plus、Team 和 SearchGPT 候补名单用户推出搜索功能，同时发布了一款支持从浏览器地址栏直接搜索的 Chrome 扩展程序。[10] OpenAI 于 2024 年 12 月 16 日将 ChatGPT Search 扩展至受支持地区的所有登录用户，并于 2025 年 2 月 5 日在受支持地区向所有人免注册开放。[10] 截至 2026-11-23，Search 功能已包含在 Free、Go、Plus 和 Pro 方案中。[4]

ChatGPT 会根据用户问题自动决定是否执行网页搜索，用户也可点击网页搜索图标手动触发搜索。[10] 搜索回复中包含指向新闻报道和博客文章等来源的内联链接，点击 Sources 按钮可在侧边栏查看引用的网页列表。[10] OpenAI 还与新闻及数据提供商合作，为天气、股票、体育、新闻和地图打造了结构化的可视化布局。[10]

OpenAI 表示，初始 ChatGPT Search 模型是 GPT-4o 的微调版本，采用包括从 OpenAI o1-preview 蒸馏输出在内的合成数据生成技术进行后训练，并结合第三方搜索提供商与合作伙伴直接提供的内容。[10] 上线时，OpenAI 公布了 14 家全球出版商合作伙伴：Associated Press、Axel Springer、Condé Nast、Dotdash Meredith、Financial Times、GEDI、Hearst、Le Monde、News Corp、Prisa（El País）、Reuters、The Atlantic、Time 和 Vox Media，同时说明任何网站或出版商均可自行选择是否出现在 ChatGPT Search 中。[10]

## ChatGPT Work、Codex 集成与开放代理协议

ChatGPT 在 Free、Go、Plus、Pro、Business、Edu 和 Enterprise 方案中均包含 ChatGPT Work 与 Codex 编程代理，两款产品在 ChatGPT 订阅下共享定价、额度和用量上限。[9] 在 ChatGPT 生态中，Codex 运行于 ChatGPT 桌面端应用、Codex CLI、Codex IDE 扩展和 Codex Cloud，覆盖本地任务、云端任务、定时自动化、代码审查与委派工作进程（delegated workers）。[8][9] ChatGPT Work 用于生成和编辑文档、幻灯片、电子表格、图表及 PDF 等交付物，并与 Gmail 和 Slack 等外部办公工具连接。[3]

在 Business、Enterprise 和 Edu 工作区的基于额度灵活定价下，ChatGPT Work 和 Codex 的用量按每 100 万输入 token、缓存输入 token 和输出 token 计算，缓存写入不收费，Fast 模式按 2 倍额度费率计费。[8] OpenAI 说明，GPT-6.2 Astra、GPT-6.2 Sol、GPT-6.1 Terra、GPT-6.1 Sol 和 GPT-6 Luna 仅在 ChatGPT Work 和 Codex 中可用而不包含在常规 Chat 中，使用 GPT-6.2 Sol 的典型 Codex 任务消耗 2 至 15 额度，且使用 ChatGPT 登录的 Enterprise Codex 用量不设 272K 输入 token 分档加价门槛。[8] 截至 2026-11-23，Standard 模式额度费率表针对 Work 和 Codex 列出的 token 费率如下。[8]

| 模型 | 输入 token（每 100 万额度） | 缓存输入 token（每 100 万额度） | 输出 token（每 100 万额度） |
| --- | --- | --- | --- |
| GPT-6.2 Astra | 200 | 10 | 1,000 |
| GPT-6.2 Sol / GPT-6.1 Sol | 50 | 2.5 | 250 |
| GPT-6.1 Terra | 25 | 1.25 | 125 |
| GPT-6 Astra | 250 | 25 | 1,250 |
| GPT-6 Sol | 50 | 5 | 250 |
| GPT-6 Luna | 2.5 | 0.25 | 12.5 |
| GPT-5.6 Sol | 100 | 10 | 500 |
| GPT-5.6 Terra | 50 | 5 | 300 |
| GPT-5.6 Luna | 5 | 0.5 | 30 |

ChatGPT 和 Codex 也参与由 Linux Foundation 托管的开放代理标准体系。[12] 2025 年 12 月 9 日，Linux Foundation 宣布成立 Agentic AI Foundation（AAIF），OpenAI 与 Amazon Web Services、Anthropic、Block、Bloomberg、Cloudflare、Google 和 Microsoft 共同担任白金成员。[12] 公告指出，ChatGPT 采用了 Anthropic 推出的用于连接模型与工具、数据及应用的 [Model Context Protocol](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP），而 OpenAI 贡献了其基于 Markdown 的 `AGENTS.md` 规范（于 2025 年 8 月发布，已被包括 Codex 在内的逾 60,000 个开源项目和代理框架采用），以及 ACP、Codex CLI、Agents SDK 和 Apps SDK。[12]

## ChatGPT 数据训练政策、安全控制与开发者平台文档

ChatGPT 对组织工作区与个人账号适用不同的数据治理条款。[7][3] 在 ChatGPT Business 概览文档中，OpenAI 声明 ChatGPT Business 遵循其商业条款和企业隐私政策，且 OpenAI 不会使用客户工作区数据训练模型。[7] 需要零数据保留（Zero Data Retention）或商业伙伴协议（BAA）的组织使用 ChatGPT Enterprise 等合同制方案。[7] 针对专业领域，OpenAI 费率表还列出了 Trusted Access 审批项目，包括面向法律领域的 Astra for Law、面向生命科学领域的 GPT-6 Rosalind Research，以及面向网络安全模型的 Daybreak（Trusted Access for Cyber）。[8]

对于个人用户，ChatGPT 概览页面指出，账号持有人可自主管理关于其数据使用方式的隐私设置，并提供家长控制（Parental Controls）功能以便家长为青少年用户配置安全防护措施。[3]

OpenAI 还在 `developers.openai.com` 和 `learn.chatgpt.com` 上维护与 ChatGPT 相关的开发者与网络生态文档。[9][11] 截至 2026-11-23，OpenAI 的 ChatGPT 开发者文档涵盖基于 MCP 服务器构建的 Plugins、Sign in with ChatGPT、Commerce 集成、广告效果衡量与 Advertiser API、Workspace Agents、允许网站放行经验证 ChatGPT 浏览器访问的 Agent Access，以及 Overview of OpenAI Crawlers 参考页面。[11] `learn.chatgpt.com` 与 `developers.openai.com` 均发布 [llms.txt](https://mimirwiki.com/zh/wiki/llms-txt) 文档索引，并在页面 URL 末尾附加 `.md` 时提供文档的 Markdown 版本。[9][11]

截至 2026-11-23，OpenAI 官方支持国家和地区目录收录了 208 个可使用 OpenAI 服务的国家和地区，并声明从列表之外的地区访问或提供访问可能导致账号被封禁或暂停。[13]

## 常见问题

### ChatGPT 何时发布？其首个版本是如何训练的？

OpenAI 于 2022 年 11 月 30 日推出 ChatGPT，作为在 Azure AI 超级计算基础设施上基于 GPT-3.5 系列模型微调而成的免费研究预览版。OpenAI 采用人类反馈强化学习（RLHF）对其进行训练，将基于人类训练师对话的监督微调与奖励建模及近端策略优化（PPO）相结合。 [2]

### ChatGPT 提供哪些个人订阅方案和 Pro 档位？

截至 2026-11-23，ChatGPT 提供四个个人订阅档位：Free、Go、Plus 和 Pro。OpenAI 于 2026 年 1 月 16 日公布美国地区 Go 月费为 8 美元、Plus 月费为 20 美元；截至 2026-11-23，Pro 以按月计费的三个档位提供，分别为每月 100 美元的 Pro 100、每月 200 美元的 Pro 200 和每月 500 美元的 Pro 500，其中 Pro 500 包含 Ultrafast 模式。 [4][5][6]

### ChatGPT Business 每个席位的价格是多少？

截至 2026-11-23，ChatGPT Business 的 Standard 席位按年计费为每用户每月 20 美元，按月计费为每用户每月 25 美元；Premium 席位按年计费为每用户每月 100 美元，按月计费为每用户每月 125 美元。工作区可从单个付费席位起步，支持混合配置 Standard 与 Premium 席位，并可购买工作区额度以扩展用量。 [7]

### OpenAI 会使用 ChatGPT Business 工作区数据训练模型吗？

不会。截至 2026-11-23，OpenAI 的 ChatGPT Business 概览文档明确指出，ChatGPT Business 遵循 OpenAI 的商业条款和企业隐私政策，OpenAI 不会使用客户工作区数据训练模型。需要零数据保留（Zero Data Retention）或商业伙伴协议（BAA）的组织可使用 ChatGPT Enterprise 等合同制方案。 [7]

### ChatGPT Search 可以不注册账号免费使用吗？

可以。OpenAI 于 2024 年 10 月 31 日面向付费用户和候补名单用户推出 ChatGPT Search，于 2024 年 12 月 16 日向所有登录用户开放，并于 2025 年 2 月 5 日起在 ChatGPT 可用地区向所有人免注册免费开放。 [10]

### ChatGPT Work 和 Codex 是如何包含在 ChatGPT 方案中的？

截至 2026-11-23，OpenAI 在 Free、Go、Plus、Pro、Business、Edu 和 Enterprise 方案中均包含 ChatGPT Work 和 Codex，两款产品共享定价、额度与用量上限。Free 和 Go 方案提供受限的桌面端访问，而 Plus、Pro、Business、Enterprise 和 Edu 方案在桌面端、网页端和移动端提供扩展访问，并支持在包含额度之外按需购买额度用于符合条件的用量。 [3][4][9]

## 可引用的句子

- OpenAI 于 2022 年 11 月 30 日推出 ChatGPT，作为基于 GPT-3.5 系列模型并通过人类反馈强化学习（RLHF）微调而成的免费研究预览版。 [2]
- OpenAI 于 2024 年 10 月 31 日推出 ChatGPT Search，并于 2025 年 2 月 5 日在受支持地区免注册开放。 [10]
- OpenAI 于 2025 年 8 月 29 日将 ChatGPT Team 更名为 ChatGPT Business。 [7]
- 2026 年 1 月 16 日，OpenAI 在全球范围内推出 ChatGPT Go，美国地区定价为每月 8 美元，同时列明 ChatGPT Plus 为每月 20 美元。 [5]
- 截至 2026-11-23，OpenAI 以按月计费的三个档位提供 ChatGPT Pro：每月 100 美元的 Pro 100、每月 200 美元的 Pro 200 和每月 500 美元的 Pro 500。 [6]
- 截至 2026-11-23，ChatGPT Business 的 Standard 席位按年计费为每用户每月 20 美元（按月计费为每用户每月 25 美元），Premium 席位按年计费为每用户每月 100 美元（按月计费为每用户每月 125 美元）。 [7]
- 截至 2026-11-23，OpenAI 声明不会使用 ChatGPT Business 工作区数据来训练模型。 [7]
- 2025 年 12 月 9 日，Linux Foundation 在成立 Agentic AI Foundation 的公告中表示，ChatGPT 已采用模型上下文协议（MCP）。 [12]

## 时间线

- 2022-11-30: OpenAI 推出 ChatGPT，作为基于 GPT-3.5 系列模型并采用 RLHF 微调而成的免费研究预览版。 [2]
- 2024-07-25: OpenAI 发布后来集成到 ChatGPT 中的 AI 网页搜索原型 SearchGPT。 [10]
- 2024-10-31: OpenAI 携手 14 家公布名单的出版商合作伙伴，面向 Plus、Team 及 SearchGPT 候补名单用户推出 ChatGPT Search。 [10]
- 2024-12-16: OpenAI 将 ChatGPT Search 扩展至 ChatGPT 可用地区的所有登录用户。 [10]
- 2025-02-05: OpenAI 在受支持地区向所有用户免注册开放 ChatGPT Search。 [10]
- 2025-08: OpenAI 在印度推出 ChatGPT Go，并发布编程代理规范 AGENTS.md。 [5][12]
- 2025-08-29: OpenAI 将 ChatGPT Team 更名为 ChatGPT Business。 [7]
- 2025-12-09: Linux Foundation 宣布成立以 OpenAI 为白金成员的 Agentic AI Foundation（AAIF），并指出 ChatGPT 已采用模型上下文协议（MCP）。 [12]
- 2026-01-16: OpenAI 以美国地区每月 8 美元的价格在全球推出 ChatGPT Go，并宣布计划在 Free 和 Go 档位中测试广告。 [5]
- 2026-06-24: OpenAI 停止向新创建的 ChatGPT Business 工作区提供旧版 Codex 席位类型。 [7]

## 来源

1. Microsoft Form 10-K for the fiscal year ended June 30, 2026. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (访问于 2026-11-23; tier 1: government or public registry)
2. Introducing ChatGPT | OpenAI. OpenAI. 发布于 2022-11-30. https://openai.com/index/chatgpt/ (访问于 2026-11-23; tier 3: official site)
3. Overview | ChatGPT. OpenAI. https://chatgpt.com/overview/ (访问于 2026-11-23; tier 3: official site)
4. Plans and Pricing | ChatGPT. OpenAI. https://chatgpt.com/pricing/ (访问于 2026-11-23; tier 3: official site)
5. Introducing ChatGPT Go, now available worldwide | OpenAI. OpenAI. 发布于 2026-01-16. https://openai.com/index/introducing-chatgpt-go/ (访问于 2026-11-23; tier 3: official site)
6. About ChatGPT Pro tiers | OpenAI Help Center. OpenAI Help Center. https://help.openai.com/en/articles/9793128-about-chatgpt-pro-tiers (访问于 2026-11-23; tier 3: official site)
7. ChatGPT Business overview | OpenAI Help Center. OpenAI Help Center. https://help.openai.com/en/articles/8792828-chatgpt-business-overview (访问于 2026-11-23; tier 3: official site)
8. ChatGPT Rate Card (Business, Enterprise/Edu credit-based pricing) | OpenAI Help Center. OpenAI Help Center. https://help.openai.com/en/articles/11481834-chatgpt-rate-card-business-enterpriseedu-credit-based-pricing (访问于 2026-11-23; tier 3: official site)
9. Pricing | ChatGPT Learn. OpenAI. https://learn.chatgpt.com/docs/pricing (访问于 2026-11-23; tier 3: official site)
10. Introducing ChatGPT search | OpenAI. OpenAI. 发布于 2024-10-31. https://openai.com/index/introducing-chatgpt-search/ (访问于 2026-11-23; tier 3: official site)
11. Overview of OpenAI Crawlers. OpenAI. https://developers.openai.com/api/docs/bots (访问于 2026-11-23; tier 3: official site)
12. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. 发布于 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (访问于 2026-11-23; tier 3: official site)
13. Supported countries and territories | OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/supported-countries (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "ChatGPT." 版本 4778c55d, 2026-11-23. https://mimirwiki.com/zh/wiki/chatgpt
