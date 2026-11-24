---
title: "Microsoft Copilot"
subtitle: "微软面向消费者和企业推出的生成式 AI 助手，深度集成于 Windows、Microsoft 365 和 Azure"
canonical_url: https://mimirwiki.com/zh/wiki/microsoft-copilot
language: zh
page_class: entity
revision_sha256: ac6f2a39336b8dee656bdd1df9e38b202403dd7f9018ebe1da45cf444f44a96e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/zh/wiki/microsoft-copilot.md
  txt: https://mimirwiki.com/zh/wiki/microsoft-copilot.txt
  json: https://mimirwiki.com/zh/wiki/microsoft-copilot.json
  jsonld: https://mimirwiki.com/zh/wiki/microsoft-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/microsoft-copilot
  ko: https://mimirwiki.com/ko/wiki/microsoft-copilot
  ja: https://mimirwiki.com/ja/wiki/microsoft-copilot
---

# Microsoft Copilot

> 截至 2026 年 11 月，Microsoft Copilot 涵盖托管于 copilot.cloud.microsoft 的免费联网版 Copilot Chat、按席位付费的 Microsoft 365 Copilot 许可证（企业版附加组件为每用户每月 30 美元；面向中小企业的 Microsoft Copilot Business 捆绑套餐为每用户每月 18 至 32 美元）、前沿企业级 Microsoft 365 E7 计划，以及按用量计费的 Copilot Studio 与 Cowork 智能体。2026 年底，微软在 OpenAI 之外进一步扩展了模型目录，将 Anthropic 的 Claude 模型作为获批的子处理方集成到平台中。

Microsoft Copilot 是微软公司（Microsoft Corporation）推出的旗舰级生成式人工智能助手与智能体平台产品家族，覆盖消费者网页端与移动端界面、Windows 11、Microsoft 365 生产力套件以及 Copilot Studio。该平台基于 OpenAI 和 Anthropic 的前沿基础模型，并结合 Microsoft Graph 组织数据（Work IQ），提供对话式搜索、文档与代码生成以及多步骤自主企业工作流。

**别名:** Microsoft 365 Copilot, Copilot Chat, Copilot Studio, Bing Chat

## 关键事实

- **开发者:** 微软公司（Microsoft Corporation，SEC CIK 0000789019） [1]
- **企业版附加组件价格:** 每用户每月 30 美元（按年承诺） (截至 2026-11-23) [2]
- **中小企业（SMB）商业定价:** 附加组件每用户每月 18 美元；与 Microsoft 365 Business 捆绑为每用户每月 23.50 至 32 美元 (截至 2026-11-23) [2]
- **智能体轮次限制:** Copilot Studio 中单轮最长运行 90 分钟，每轮最多调用 200 次工具 (截至 2026-11-23) [7]

## 事实摘要

- **开发者:** 微软公司（Microsoft Corporation） [1]
- **主要网页端点:** copilot.microsoft.com（消费者版）/ copilot.cloud.microsoft（企业与教育版） [4]
- **接地架构:** Microsoft Graph / Work IQ 与 Bing 网页索引 [4]
- **基础模型提供商:** OpenAI（Azure OpenAI Service）与 Anthropic（Claude 子处理方） [5]
- **企业许可方案:** Microsoft 365 Copilot 附加组件、Microsoft 365 E7、Microsoft Copilot Business [3]
- **智能体平台:** Microsoft Copilot Studio（按量付费或消息包计费） [7]
- **企业数据保护:** 商业用户的提示词与响应不会用于基础模型训练 [6]
- **母公司 2026 财年营收背景:** 2026 财年（截至 2026 年 6 月 30 日）Form 10-K 中微软总营收为 331,839 百万美元（3,318.4 亿美元） [1]

## Microsoft Copilot 概述与产品架构

Microsoft Copilot 是微软公司面向消费者、商业客户和开发者界面的生成式 AI 助手统一品牌及技术编排框架。[1][4] 该平台最初于 2023 年以 Bing Chat 和 Microsoft 365 Copilot 的名称推出，随后统一整合至 Microsoft Copilot 品牌下，将大语言模型（LLM）与网页搜索索引、操作系统遥测数据及企业组织图谱深度结合。[1][4]

商业版产品的核心架构是 **Work IQ**（原称 Microsoft Graph 接地），它在严格执行现有基于角色的访问控制（RBAC）和 Microsoft Purview 敏感度标签的前提下，将基础模型连接到租户的电子邮件、Microsoft Teams 聊天记录、SharePoint 站点、OneDrive 文档以及日历元数据。[4][6] 当经过身份验证的企业用户在 `copilot.cloud.microsoft` 或 Office 应用内提交提示词时，Copilot 编排器会在用户拥有访问权限的 Microsoft Graph 范围内执行预处理与语义检索，利用检索到的引用信息增强提示词，将负载路由至所选 LLM，并在流式返回响应之前完成合规性、接地验证及负责任的 AI（Responsible AI）后处理检查。[4][6]

## Microsoft Copilot 产品层级、Microsoft 365 E7 与定价

微软将 Microsoft Copilot 划分为免费消费者版、商业基础聊天版、按席位付费的生产力附加组件以及按用量计费的智能体消费模式。[2][3][4]

| 层级 / 计划 | 目标受众 | 核心能力 | 定价（截至 2026 年 11 月） |
| --- | --- | --- | --- |
| **Microsoft Copilot（消费者版）** | 个人消费者 | 联网对话、图像生成、语音交互、Windows 与移动应用 | 免费（提供付费 Copilot Pro 层级） [4] |
| **Microsoft Copilot Chat** | 商业及教育版 Entra ID 用户 | 支持企业数据保护（EDP）的联网对话、Copilot Pages、按量付费智能体 | 包含在符合条件的 M365 许可证中；智能体按用量计费 [4] |
| **Microsoft Copilot Business** | 中小企业（最多 300 名用户） | 在 Word、Excel、PowerPoint、Outlook、Teams 中提供基于工作数据的 Copilot | 附加组件每用户每月 18 美元；与 M365 Business 捆绑为每用户每月 23.50 至 32 美元 [2] |
| **Microsoft 365 Copilot（企业版）** | 企业租户（需具备 E3/E5 前置许可） | 完整 Work IQ 接地、嵌入式应用技能，并包含 Copilot Studio 智能体额度 | 每用户每月 30 美元（按年承诺） [2][3] |
| **Microsoft 365 E7** | 前沿企业级部署 | 整合 M365 E5、Microsoft 365 Copilot 与高级智能体能力的综合企业套件 | 企业协议（EA）定价 [3] |

除按席位许可外，微软还针对 **Copilot Cowork**、**Copilot Code** 和 **Copilot Autopilot** 等专用自主工作流推出了计量消费模式，可通过关联的 Azure 订阅按量付费，或通过预购 Copilot Credit 容量包进行结算。[3][5]

## Microsoft Copilot 多模型编排与 Anthropic 集成

早期版本的 Microsoft Copilot 仅依赖托管在 Azure OpenAI Service 上的 OpenAI 模型，但微软在 2025 年和 2026 年期间将 Copilot 扩展为多模型编排平台。[4][5] 根据微软商业服务文档和 Microsoft Learn 技术文档的说明，微软在集成自研内部模型的同时，也接入了来自 OpenAI 和 Anthropic 的前沿模型。[4][5]

具体而言，微软已将 **Anthropic** 纳入官方 Microsoft 在线服务子处理方（Microsoft Online Services Subprocessor）名单，允许企业管理员和 Copilot Studio 构建者在 Microsoft 365 Copilot、Copilot Cowork 和 Copilot Studio 中启用 Anthropic 的 Claude 模型，以执行深度推理、编程和多步骤研究工作流。[5] 调用 Anthropic 模型时，客户数据仍受微软商业条款和企业数据保护承诺的约束，但根据区域可用性，相关请求可能会在子处理方数据保护协议下由 Anthropic 的托管基础设施处理。[5][6]

## Copilot Studio 与智能体运行时配额

Microsoft Copilot Studio 是面向低代码和专业代码开发者的构建环境，用于创建自定义声明式智能体、自主工作流以及计算机操作智能体，并可直接发布至 Microsoft Copilot Chat 和 Microsoft Teams。[4][7] 为防止失控执行并规范多智能体编排，微软对 Copilot Studio 智能体实施了严格的运行时配额与操作限制。[7]

- **单轮最长运行时间**：单个智能体编排轮次在超时前最多可运行 **90 分钟**（5,400 秒）。[7]
- **每轮工具调用次数**：单轮对话在连接器、操作和插件范围内最多支持 **200 次工具调用**。[7]
- **单个工具与连接器超时**：标准同步工具或连接器执行在 **120 秒**后超时。[7]
- **智能体流 / 工作流超时**：嵌入式 Power Automate 及智能体工作流的同步执行上限为 **660 秒**（11 分钟）。[7]
- **已连接智能体与外部智能体**：委派给内部已连接 Copilot Studio 智能体的调用最长可运行 **5,400 秒**（90 分钟），而调用外部 A2A/MCP 智能体则在 **300 秒**（5 分钟）后超时。[7]
- **对话上下文与流式输出**：编排器为每次对话维护 **100 条消息**的滑动上下文窗口，Microsoft Teams 中的实时流式响应每个流式分段上限为 **2 分钟**。[7]

## Microsoft Copilot 企业数据保护与治理

对于使用 Microsoft Entra ID 账户登录的商业、政府和教育机构组织，微软依据《Microsoft 产品条款》和《数据处理附录》（DPA）提供**企业数据保护（EDP）**。[6] 在 EDP 框架下，用户提示词、上传文件、Microsoft Graph 接地数据及生成的响应均按租户进行逻辑隔离，在传输和静态存储过程中全程加密，且**绝不用于训练公共或基础大语言模型**。[6]

Copilot 严格继承现有的 Microsoft Purview 治理策略：如果文档采用权限管理服务（RMS）加密或带有禁止提取的敏感度标签，Copilot 会阻止摘要生成，或将受限标签与水印直接延续至生成的内容中。[6] 管理员可通过 Microsoft Purview Audit、Communication Compliance 以及 eDiscovery 审计所有提示词交互、智能体工具调用和引用记录。[6]

## 常见问题

### Microsoft Copilot Chat 与 Microsoft 365 Copilot 有什么区别？

Microsoft Copilot Chat 是托管于 copilot.cloud.microsoft 的基础联网助手，面向符合条件的 Microsoft Entra ID 工作和学校账户免费包含（无额外席位费用），提供企业数据保护和按量付费的智能体访问能力。Microsoft 365 Copilot（企业版每用户每月 30 美元）则在此基础上增加了覆盖用户邮件、聊天和文件的 Work IQ（Microsoft Graph）接地能力，以及 Word、Excel、PowerPoint、Outlook 和 Teams 应用内的直接集成。 [2][4]

### 面向中小企业的 Microsoft Copilot Business 费用是多少？

对于中小企业（最多 300 个席位），Microsoft Copilot Business 可作为独立附加组件以每用户每月 18 美元的价格购买，也可按年承诺与 Microsoft 365 Business Basic、Standard 或 Premium 计划捆绑，促销价格为每用户每月 23.50 至 32 美元。 [2]

### Microsoft Copilot 除了 OpenAI 模型外，还使用 Anthropic 的 Claude 模型吗？

是的。微软采用多模型架构运行 Copilot，并已将 Anthropic 指定为官方在线服务子处理方，允许企业租户在 Microsoft 365 Copilot、Copilot Studio 和 Copilot Cowork 中与 OpenAI 及微软自研模型一同使用 Anthropic 的 Claude 模型。 [4][5]

### Microsoft Copilot Studio 中智能体的运行时间和工具调用限制是多少？

截至 2026 年底，Copilot Studio 智能体单轮最长可运行 90 分钟（5,400 秒），每轮最多可执行 200 次工具调用。单个同步工具调用超时时间为 120 秒，智能体流超时时间为 660 秒，外部智能体调用超时时间为 300 秒。 [7]

### 微软是否会使用企业版 Copilot 的提示词来训练基础 AI 模型？

不会。根据微软面向商业 Entra ID 用户的企业数据保护（EDP）承诺，提示词、检索到的 Microsoft Graph 上下文以及生成的响应均隔离在客户边界内，不会用于训练基础模型。 [6]

## 可引用的句子

- Microsoft 365 Copilot 企业版定价为每用户每月 30 美元，Microsoft Copilot Business 提供每用户每月 18 美元的附加组件以及每用户每月 23.50 至 32 美元的中小企业捆绑套餐。 [2][3]
- 微软已将 Anthropic 纳入在线服务子处理方名单，在 Microsoft 365 Copilot、Copilot Studio 和 Copilot Cowork 中提供 Claude 模型。 [5]
- Microsoft Copilot Studio 强制执行单轮最长 90 分钟（5,400 秒）以及每轮最多 200 次工具调用的限制。 [7]
- Copilot Studio 中单个工具调用在 120 秒后超时，智能体工作流在 660 秒后超时，外部智能体调用在 300 秒后超时。 [7]
- 在企业数据保护（EDP）框架下，商业 Entra ID 用户的提示词与响应不会用于训练基础模型。 [6]

## 时间线

- 2023-02: 微软以 Bing Chat 的名称推出首个生成式 AI 搜索助手。 [1]
- 2023-11: Microsoft 365 Copilot 面向企业客户正式全面上市，Bing Chat 更名为 Microsoft Copilot。 [1]
- 2026-06-30: 微软以 3,318.4 亿美元的年营收结束 2026 财年，并在 Form 10-K 中披露了 Copilot 在 Microsoft 365、Windows、GitHub 及 Azure AI 基础设施中的扩展。 [1]
- 2026-11: 微软公布了 Microsoft 365 E7、Microsoft Copilot Business 中小企业定价（每用户每月 18 至 32 美元）、Anthropic Claude 子处理方集成，以及扩展至 90 分钟与 200 次工具调用的 Copilot Studio 运行时限制。 [2][3][5][7]

## 来源

1. Microsoft Corporation Form 10-K for the Fiscal Year Ended June 30, 2026. U.S. Securities and Exchange Commission (SEC). 发布于 2026-07-29. https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (访问于 2026-11-23; tier 1: government or public registry)
2. Microsoft Copilot Plans and Pricing - AI for Business | Microsoft 365. Microsoft Corporation. https://www.microsoft.com/en-us/copilot/pricing/business (访问于 2026-11-23; tier 3: official site)
3. License Options for Microsoft Copilot | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-license-options (访问于 2026-11-23; tier 3: official site)
4. What is Microsoft Copilot? | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-overview (访问于 2026-11-23; tier 3: official site)
5. Claude models from Anthropic in Microsoft Online Services | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/implement/connect-to-ai-subprocessor (访问于 2026-11-23; tier 3: official site)
6. Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/enterprise-data-protection (访问于 2026-11-23; tier 3: official site)
7. Agent runtime limits - Microsoft Copilot Studio | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/runtime-limits (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Microsoft Copilot." 版本 ac6f2a39, 2026-11-23. https://mimirwiki.com/zh/wiki/microsoft-copilot
