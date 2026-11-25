---
title: "GPT-6.2"
subtitle: "OpenAI 于 2026 年 11 月发布的多模态推理语言模型（GPT-6.2 Astra 和 GPT-6.2 Sol）"
canonical_url: https://mimirwiki.com/zh/wiki/gpt-6-2
language: zh
page_class: entity
revision_sha256: 6f1cbcf97cdd8b86a12c03ba9e3375b0a37bd4cc2e8f12554a381064c808c4ec
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 11
alternates:
  md: https://mimirwiki.com/zh/wiki/gpt-6-2.md
  txt: https://mimirwiki.com/zh/wiki/gpt-6-2.txt
  json: https://mimirwiki.com/zh/wiki/gpt-6-2.json
  jsonld: https://mimirwiki.com/zh/wiki/gpt-6-2.jsonld
translations:
  en: https://mimirwiki.com/wiki/gpt-6-2
  ko: https://mimirwiki.com/ko/wiki/gpt-6-2
  ja: https://mimirwiki.com/ja/wiki/gpt-6-2
  es: https://mimirwiki.com/es/wiki/gpt-6-2
---

# GPT-6.2

> GPT-6.2 是 OpenAI 于 2026 年 11 月 17 日面向 ChatGPT Work、Codex 和 OpenAI API 发布的一对大语言模型，包括 GPT-6.2 Astra 和 GPT-6.2 Sol。两款模型均接受文本和图像输入，生成包含强制推理 token 的文本输出，并支持 1,050,000 个 token 的上下文窗口及最高 128,000 个输出 token。截至 2026-11-23，每百万 token 的标准 API 定价为 GPT-6.2 Astra 输入 8.00 美元、输出 40.00 美元，GPT-6.2 Sol 输入 2.00 美元、输出 10.00 美元。

GPT-6.2 是 OpenAI 第六代多模态大语言模型系列中的一次版本发布，包含于 2026 年 11 月 17 日推出的两款推理模型：GPT-6.2 Astra（`gpt-6.2-astra`）和 GPT-6.2 Sol（`gpt-6.2-sol`）。OpenAI 将 GPT-6.2 Astra 定位为面向复杂专业成果交付、软件工程、科学研究和计算机操作（computer use）的旗舰前沿模型，将 GPT-6.2 Sol 定位为面向日常编程和多步骤智能体工作流的高性价比模型。两款模型均接受文本和图像输入，生成带有推理 token 的文本输出，并提供 1,050,000 个 token 的上下文窗口（最大输入 922,000 个 token，最大输出 128,000 个 token）。截至 2026-11-23，这两款模型可通过 OpenAI API、Google Cloud 私有预览访问，同时面向 ChatGPT Plus、Pro、Enterprise 和 Edu 订阅用户在 ChatGPT Work 和 Codex 中提供预览。

**别名:** GPT-6.2 Astra, GPT-6.2 Sol, gpt-6.2-astra, gpt-6.2-sol, OpenAI GPT-6.2

## 关键事实

- **发布日期:** 2026-11-17 [2]
- **模型与 API ID:** GPT-6.2 Astra（gpt-6.2-astra）和 GPT-6.2 Sol（gpt-6.2-sol） (截至 2026-11-23) [4]
- **上下文窗口:** 1,050,000 个 token（最大输入 922,000，最大输出 128,000） (截至 2026-11-23) [4]
- **GPT-6.2 Astra 标准 API 价格:** 每百万 token 输入 $8.00、缓存输入 $0.40、输出 $40.00（输入 <=272K） (截至 2026-11-23) [6]
- **GPT-6.2 Sol 标准 API 价格:** 每百万 token 输入 $2.00、缓存输入 $0.10、输出 $10.00（输入 <=272K） (截至 2026-11-23) [6]

## 事实摘要

- **开发商:** OpenAI [1]
- **发布日期:** 2026-11-17 [2]
- **模型变体与 API ID:** GPT-6.2 Astra（gpt-6.2-astra）和 GPT-6.2 Sol（gpt-6.2-sol） (截至 2026-11-23) [4]
- **前代模型:** GPT-6 Astra 和 GPT-6.1 Sol [1]
- **模态:** 文本与图像输入；文本输出（不支持音频和视频） (截至 2026-11-23) [4]
- **上下文窗口与上限:** 1,050,000 个 token（最大输入 922,000，最大输出 128,000） (截至 2026-11-23) [4]
- **知识截止日期:** 2026-05-18（GPT-6.2 Astra）；2026-06-01（GPT-6.2 Sol） (截至 2026-11-23) [4]
- **标准 API 定价（<=272K）:** Astra：每百万 token 输入 $8.00 / 缓存 $0.40 / 输出 $40.00；Sol：每百万 token 输入 $2.00 / 缓存 $0.10 / 输出 $10.00 (截至 2026-11-23) [6]
- **支持的 API 端点:** v1/responses, v1/chat/completions, v1/batch (截至 2026-11-23) [4]
- **ChatGPT 与云平台可用性:** ChatGPT Work 和 Codex（Plus、Pro、Enterprise、Edu）；Google Cloud（私有预览） (截至 2026-11-23) [3]
- **准备框架评级:** 网络安全：Critical（两款）；生物与化学：High（两款）；AI 自我改进：High（仅 Astra） (截至 2026-11-22) [8]

## GPT-6.2 概述、发布历史与模型阵容

GPT-6.2 是由 [OpenAI](https://mimirwiki.com/zh/wiki/openai) 开发的 GPT-6 代大语言模型版本，于 2026 年 11 月 17 日推出，包含 GPT-6.2 Astra 和 GPT-6.2 Sol 两个变体。[1][2] 截至 2026-11-23，在 OpenAI 的模型目录中，GPT-6 系列采用天体名称划分层级：Astra 面向前沿推理，Sol 面向均衡的日常编程和智能体工作负载，Terra（`gpt-6.1-terra`，2026 年 10 月 26 日发布）面向视觉推理和写作，Luna（`gpt-6-luna`，2026 年 9 月 22 日发布）面向高吞吐低成本任务，此外还有专用变体 GPT-6 Cyber 和 GPT-6 Rosalind Research（2026 年 10 月 30 日发布）。[2][9][11]

GPT-6.2 Astra 是 GPT-6 Astra 的继任模型，而 GPT-6.2 Sol 是 GPT-6.1 Sol（2026 年 9 月 29 日发布）和 GPT-6 Sol（2026 年 9 月 22 日发布）的继任模型。[1][9][11] 根据 OpenAI 的发布公告和 API 文档，GPT-6.2 Astra 专为涵盖软件工程、科学研究、法律与财务分析、计算机操作以及 3D 或前端设计的复杂端到端项目而打造；GPT-6.2 Sol 则针对低延迟的日常编程、写作以及大规模多步骤智能体工作流进行了优化，并作为许多 OpenAI 员工的默认内部模型使用。[1][4][5]

2026 年 11 月 17 日，OpenAI 在 OpenAI API、[ChatGPT](https://mimirwiki.com/zh/wiki/chatgpt) Work 和 Codex 桌面端同步上线了两款模型。[1][2][3] 在 ChatGPT 中，Plus、Pro、Enterprise 和 Edu 用户可通过 Work 模型选择器和 Codex 模型选择器获得 GPT-6.2 Astra 和 GPT-6.2 Sol 的预览访问权限，而标准的 ChatGPT 聊天（Chat）标签页保留了现有的模型选项。[1][3][10]

## GPT-6.2 技术规格与 Responses API 架构

根据截至 2026-11-23 的 OpenAI 开发者文档，GPT-6.2 Astra（`gpt-6.2-astra`）和 GPT-6.2 Sol（`gpt-6.2-sol`）均接受文本和图像输入并返回文本输出，但不支持音频和视频模态、微调及预测输出。[4][5] 每款模型均提供 1,050,000 个 token 的上下文窗口，单次请求最高支持 922,000 个输入 token 和 128,000 个输出 token。[4][5] 文档记录的知识截止日期为 GPT-6.2 Astra 2026 年 5 月 18 日，GPT-6.2 Sol 2026 年 6 月 1 日。[4][5]

| 规格项 | GPT-6.2 Astra（`gpt-6.2-astra`） | GPT-6.2 Sol（`gpt-6.2-sol`） |
| --- | --- | --- |
| 主要定位 | 面向复杂推理、编程和专业工作的前沿模型 | 面向日常编程和大规模多步骤智能体的均衡模型 |
| 前代模型 | GPT-6 Astra（`gpt-6-astra`） | GPT-6.1 Sol（`gpt-6.1-sol`） |
| 输入 / 输出模态 | 文本和图像输入；文本输出 | 文本和图像输入；文本输出 |
| 上下文窗口 | 1,050,000 个 token（最大输入 922,000，最大输出 128,000） | 1,050,000 个 token（最大输入 922,000，最大输出 128,000） |
| 知识截止日期 | 2026 年 5 月 18 日 | 2026 年 6 月 1 日 |
| 支持的 API 端点 | `v1/responses`、`v1/chat/completions`、`v1/batch` | `v1/responses`、`v1/chat/completions`、`v1/batch` |
| 云合作伙伴上线情况 | Google Cloud（私有预览） | Google Cloud（私有预览） |

两款模型均会生成推理 token，并拒绝将 `reasoning.effort` 设为 `none` 的 API 请求。[4][5] 两款模型支持的 API 功能包括流式传输（streaming）、结构化输出（structured outputs）、函数调用（function calling）、文件搜索、图像输入、网页搜索和提示缓存（prompt caching）。[4][5] 通过 Responses API（`v1/responses`）调用时，两款模型均支持 `web_search`、`file_search`、`image_generation`、`code_interpreter`、`hosted_shell`、`apply_patch`、`skills`、`computer_use`、[模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（`mcp`）和 `tool_search` 等内置工具，并支持通过 Multi-agent 测试版进行子智能体委派。[4][5]

OpenAI 的“Using GPT-6.2”迁移指南重点列出了从 GPT-6.2 开始在 Responses API 中引入的三项行为变更：[7]

- 前缀编辑（Prefix edits）：在对话中途修改早期历史记录（例如更改先前的 developer 消息或工具调用）、降级模型或更改用户/组织后，Responses API 会丢弃先前的推理项，因此必须保持前缀不变以保留推理状态和提示缓存。[7]
- 顶层 `instructions` 顺序：GPT-6.2 会将顶层 `instructions` 参数追加到 `input` 之后而非之前，因此开发者必须将可复用的指令放在 `input` 开头的 `developer` 消息中，才能利用提示缓存。[7]
- 后台完成窗口：两款 GPT-6.2 模型均不支持 Flex 处理（`service_tier: flex`），作为替代，长时间运行的 Responses API 请求可使用公测版折扣后台模式，提供 2 小时或 8 小时的完成窗口。[4][5][7]

## GPT-6.2 API 定价、处理层级与速率限制

OpenAI 按每百万 token 以美元计量 GPT-6.2 的 API 用量，并区分短上下文请求（不超过 272,000 个输入 token）和长上下文请求（超过 272,000 个输入 token）；在长上下文请求中，整个请求的输入和缓存费率翻倍，输出费率提高至 1.5 倍。[4][5][6] 与 GPT-6 Astra（每百万 token 输入 10.00 美元、缓存输入 1.00 美元、输出 50.00 美元）相比，GPT-6.2 Astra 将标准输入和输出价格降低了 20%，将缓存输入价格降低了 60%，而 GPT-6.2 Sol 则保留了 GPT-6.1 Sol 的定价。[1][6]

| 模型与处理层级（截至 2026-11-23） | 短上下文输入（<=272K） | 短上下文输出（<=272K） | 短上下文缓存输入 | 短上下文缓存写入（30 分钟 / 12 小时） | 长上下文输入（>272K） | 长上下文输出（>272K） |
| --- | --- | --- | --- | --- | --- | --- |
| GPT-6.2 Astra（Standard） | $8.00 / 1M | $40.00 / 1M | $0.40 / 1M | $10.00 / $20.00 | $16.00 / 1M | $60.00 / 1M |
| GPT-6.2 Astra（Batch，Standard 的 50%） | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Astra（Fast，Standard 的 2 倍） | $16.00 / 1M | $80.00 / 1M | $0.80 / 1M | $20.00 / $40.00 | $32.00 / 1M | $120.00 / 1M |
| GPT-6.2 Astra（Ultrafast 促销，至 2027-02-28 为 Standard 的 3 倍） | $24.00 / 1M | $120.00 / 1M | $1.20 / 1M | $30.00 / $60.00 | $48.00 / 1M | $180.00 / 1M |
| GPT-6.2 Sol（Standard） | $2.00 / 1M | $10.00 / 1M | $0.10 / 1M | $2.50 / $5.00 | $4.00 / 1M | $15.00 / 1M |
| GPT-6.2 Sol（Batch，Standard 的 50%） | $1.00 / 1M | $5.00 / 1M | $0.05 / 1M | $1.25 / $2.50 | $2.00 / 1M | $7.50 / 1M |
| GPT-6.2 Sol（Fast，Standard 的 2 倍） | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Sol（Ultrafast 促销，至 2027-02-28 为 Standard 的 3 倍） | $6.00 / 1M | $30.00 / 1M | $0.30 / 1M | $7.50 / $15.00 | $12.00 / 1M | $45.00 / 1M |

除 Standard、Batch（50% 折扣）和 Fast（Standard 的 2 倍）层级外，OpenAI 还提供 Ultrafast 层级，在太平洋时间 2027 年 2 月 28 日之前按 Standard 费率的 3 倍计价，自 2027 年 3 月 1 日起按 Standard 费率的 6 倍计价。[4][5][6] 截至 2026-11-23，两款模型的标准速率限制均为：Build 层级每分钟 5,000 次请求（RPM）和每分钟 1,000,000 个 token（TPM），Launch 层级 10,000 RPM 和 4,000,000 TPM，Grow 层级 15,000 RPM 和 40,000,000 TPM。[4][5]

## GPT-6.2 基准评估与早期反响

在 2026 年 11 月 17 日的发布公告中，OpenAI 报告称 GPT-6.2 Astra 和 GPT-6.2 Sol 在减少输出 token 生成量的同时，在长周期专业、科学和编程基准测试中均优于其前代模型。[1][2]

- Agents' Last Exam（长周期多步骤专业工作）：OpenAI 报告称，GPT-6.2 Astra 以不到三分之一的成本比 GPT-6 Astra 高出 5.2 分，并以 5% 的成本领先 [Claude Fable 5.2](https://mimirwiki.com/zh/wiki/claude-fable-5-2)（排除 9 项使用回退模型的任务）5.5 分。[1]
- Terminal-Bench-Science 0.1 与 Vals Science Index v1：OpenAI 表示，GPT-6.2 Astra 在 Terminal-Bench-Science 0.1 上以不到三分之一的成本比 GPT-6 Astra 高出 9 个百分点，并在 Vals Science Index v1 上创下新高。[1]
- 法律与财务工作流：在 Harvey LAB-AA v1.1 上，OpenAI 报告 GPT-6.2 Astra 以约六分之一的成本取得了超过 Claude Fable 5.2 两倍的通过率，而名为 Astra for Law 的法律专用配置得分更高；在 Artificial Analysis 的 AA-AnalystAgent 电子表格与报告基准测试中，GPT-6.2 Astra 在全部五次独立尝试中答对了 62.5% 的问题。[1]
- GDPval v2（OpenAI 内部知识工作评估）：GPT-6.2 Astra 在输出 token 减少 22% 的情况下比 GPT-6 Astra 提升了 6.2 个百分点，GPT-6.2 Sol 比 GPT-6.1 Sol 提升了 5.3 分。[1]
- FrontierCode 2.0 与 LifeVal：在最大推理强度下的 Cognition FrontierCode 2.0 中，GPT-6.2 Sol 以约五分之一的成本与 GPT-6.2 Astra 保持在 0.5 分以内；在 OpenAI 的 LifeVal 日常任务评估中，GPT-6.2 Sol 以约七分之一的成本超越了 GPT-6 Astra。[1]

发布后，VentureBeat 于 2026 年 11 月 17 日报道称，外部 AI 资深用户对发布前及发布当日的反馈出现分化。[10] OpenAI 引用的早期企业评估者（包括 IMC、Legora、Harvey 和 ClickUp 的工程师及高管）报告在法律和工作区基准测试中 token 使用量减少了 34.5% 至 62%，测试者 Ben Hylak（Raindrop.ai CTO）和 Ashe Magalhaes 也称赞了 GPT-6.2 Astra 的动态图形、视觉特效和视频编辑能力。[1][10] 相比之下，开发者 Theo Browne、投资人 Matt Shumer、Every CEO Dan Shipper 和沃顿商学院教授 Ethan Mollick 批评 GPT-6.2 Astra 在长时间自主构建任务中容易提前停止、表现出重复的固定风格（例如在不同游戏提示下都生成同样名为“Bellwether”的水域关卡），或因默认行文过于简略而遗漏上下文。[10]

## GPT-6.2 系统卡、准备框架评级与安全性评估

OpenAI 于 2026 年 11 月 17 日发布了 GPT-6.2 系统卡，并于 2026 年 11 月 22 日更新了变更日志，以明确 OAI-repo Sabotage v2 评估中的 L2 监控优先级分类（`P0` 表示立即交由安全团队审查，`P0.5` 表示在工作时间内高优先级跟进）。[8] 根据 OpenAI 准备框架（Preparedness Framework），GPT-6.2 Astra 和 GPT-6.2 Sol 在网络安全能力方面均达到 Critical 阈值，在生物与化学能力方面均达到 High 阈值。[8] 两款模型在利用已知软件漏洞开发可用漏洞利用程序方面的表现均超过 GPT-6 Astra 和 GPT-6.1 Sol，促使 OpenAI 收紧了对高风险网络安全查询的默认限制，并要求对更宽松的网络安全访问权限进行额外审查。[8]

GPT-6.2 Astra 也是 OpenAI 首个在 AI 自我改进（AI Self-Improvement）能力方面达到 High 阈值的外部部署模型，OpenAI 将该阈值定义为在具备完全自动化递归自我改进能力的模型出现之前准备安全保障的早期里程碑，而 GPT-6.2 Sol 仍低于该阈值。[8] 在 Codex 内扩大 GPT-6.2 Astra 的内部部署之前，OpenAI 验证了分阶段门控的对齐安全措施，加强了研究环境的隔离，并扩大了对前沿智能体的监控范围。[8]

GPT-6.2 系统卡记录了涵盖提示注入防护、幻觉、HealthBench Professional、MentalHealthBench、ExploitGym Honeypot、Blocker Deception、Broken Search Tool、职场任务模拟、非预期智能体间通信、思维链控制（`CoT-Control`）、`OAI-repo Sabotage v2`、`Sneaky Sandbox Escape` 的全面对齐与可监控性测试，以及由 SecureBio 和英国 AI 安全研究所（UK AISI）进行的外部评估。[8]

## 常见问题

### 什么是 GPT-6.2？GPT-6.2 Astra 和 GPT-6.2 Sol 有何区别？

GPT-6.2 是 OpenAI 于 2026 年 11 月 17 日发布的语言模型版本，包含两款模型：GPT-6.2 Astra（`gpt-6.2-astra`）定位为面向复杂推理、软件工程、科学研究和专业成果交付的旗舰前沿模型；GPT-6.2 Sol（`gpt-6.2-sol`）定位为面向日常编程和多步骤智能体工作流的更快速、更低成本模型。两款模型均具备 1,050,000 个 token 的上下文窗口，并接受文本和图像输入。 [1][2][4][5]

### GPT-6.2 Astra 和 GPT-6.2 Sol 在 OpenAI API 中的价格是多少？

截至 2026-11-23，短上下文请求（输入不超过 272,000 个 token）每百万 token 的标准 API 价格为：GPT-6.2 Astra 输入 8.00 美元、缓存输入 0.40 美元、30 分钟缓存写入 10.00 美元（12 小时为 20.00 美元）、输出 40.00 美元；GPT-6.2 Sol 输入 2.00 美元、缓存输入 0.10 美元、30 分钟缓存写入 2.50 美元（12 小时为 5.00 美元）、输出 10.00 美元。对于超过 272,000 个输入 token 的长上下文请求，整个请求的输入和缓存费率翻倍，输出费率提高至 1.5 倍。 [4][5][6]

### GPT-6.2 的上下文窗口、输出上限和知识截止日期分别是多少？

每款 GPT-6.2 模型均提供 1,050,000 个 token 的上下文窗口，最多支持 922,000 个输入 token 和 128,000 个输出 token。知识截止日期方面，GPT-6.2 Astra 为 2026 年 5 月 18 日，GPT-6.2 Sol 为 2026 年 6 月 1 日。两款模型均支持文本和图像输入以及文本输出，但不支持音频、视频、微调（fine-tuning）和预测输出（predicted outputs）。 [4][5]

### 用户和开发者可以在哪里访问 GPT-6.2 Astra 和 GPT-6.2 Sol？

截至 2026-11-23，ChatGPT Plus、Pro、Enterprise 和 Edu 用户可在 ChatGPT Work 和 Codex 桌面端以预览版形式使用 GPT-6.2 Astra 和 GPT-6.2 Sol，而常规 ChatGPT 聊天（Chat）标签页仍保留原有模型选项。开发者可通过 OpenAI API（`v1/responses`、`v1/chat/completions` 和 `v1/batch`）调用这两款模型，此外两款模型也已在 Google Cloud 上线私有预览。 [1][3][4][5][10]

### GPT-6.2 Astra 和 Sol 在 OpenAI 准备框架中达到了哪些阈值？

在 2026 年 11 月 17 日发布（2026 年 11 月 22 日更新）的 GPT-6.2 系统卡中，OpenAI 表示根据 OpenAI 准备框架（Preparedness Framework），GPT-6.2 Astra 和 GPT-6.2 Sol 在网络安全（Cybersecurity）能力上均达到 Critical 阈值，在生物与化学（Biological and Chemical）能力上均达到 High 阈值。此外，GPT-6.2 Astra 是 OpenAI 首个在 AI 自我改进（AI Self-Improvement）能力上达到 High 阈值的外部部署模型，而 GPT-6.2 Sol 仍低于该阈值。 [8]

## 可引用的句子

- OpenAI 于 2026 年 11 月 17 日在 ChatGPT Work、Codex 和 OpenAI API 中发布了 GPT-6.2 Astra 和 GPT-6.2 Sol，模型标识符分别为 gpt-6.2-astra 和 gpt-6.2-sol。 [1][2][3]
- GPT-6.2 Astra 和 GPT-6.2 Sol 均支持 1,050,000 个 token 的上下文窗口（最大输入 922,000 个 token，最大输出 128,000 个 token），接受文本和图像输入，并生成包含推理 token 的文本输出。 [4][5]
- 官方文档记载的知识截止日期为 GPT-6.2 Astra 2026 年 5 月 18 日、GPT-6.2 Sol 2026 年 6 月 1 日。 [4][5]
- 截至 2026-11-23，对于不超过 272,000 个输入 token 的提示，GPT-6.2 Astra 的标准 OpenAI API 定价为每百万输入 token 8.00 美元、每百万缓存输入 token 0.40 美元、每百万 30 分钟缓存写入 token 10.00 美元、每百万输出 token 40.00 美元。 [4][6]
- 截至 2026-11-23，对于不超过 272,000 个输入 token 的提示，GPT-6.2 Sol 的标准 OpenAI API 定价为每百万输入 token 2.00 美元、每百万缓存输入 token 0.10 美元、每百万 30 分钟缓存写入 token 2.50 美元、每百万输出 token 10.00 美元。 [5][6]
- 与其前代模型 GPT-6 Astra（每百万 token 输入 10.00 美元、缓存输入 1.00 美元、输出 50.00 美元）相比，GPT-6.2 Astra 将标准输入和输出 token 价格降低了 20%，将缓存输入价格降低了 60%。 [1][6]
- 根据 OpenAI 准备框架（Preparedness Framework），GPT-6.2 系统卡将 GPT-6.2 Astra 和 GPT-6.2 Sol 在网络安全能力方面均划为 Critical 阈值、在生物与化学能力方面均划为 High 阈值，而 GPT-6.2 Astra 是 OpenAI 首个在 AI 自我改进（AI Self-Improvement）能力方面达到 High 阈值的外部部署模型。 [8]
- 两款 GPT-6.2 模型均会拒绝将推理强度（reasoning effort）设为 none 的 API 请求，不支持 Flex 处理（service_tier: flex），但支持在 Responses API 中使用带折扣的后台完成窗口（2 小时或 8 小时）。 [4][5][7]

## 时间线

- 2026-09-22: 继 GPT-6 Astra 发布后，OpenAI 推出 GPT-6 Sol 和 GPT-6 Luna，扩展了 GPT-6 模型系列。 [9]
- 2026-09-29: OpenAI 在 GPT-6 系列中发布了 GPT-6.1 Sol。 [9]
- 2026-10-26: OpenAI 在 OpenAI API、ChatGPT Work 和 Codex 中上线了 GPT-6.1 Terra。 [2]
- 2026-11-17: OpenAI 在 ChatGPT Work、Codex 和 OpenAI API 中发布了 GPT-6.2 Astra 和 GPT-6.2 Sol，并公开了 GPT-6.2 系统卡。 [1][2][3][8]
- 2026-11-22: OpenAI 更新了 GPT-6.2 系统卡的变更日志，以明确 OAI-repo Sabotage v2 部分中的 L2 监控优先级分类。 [8]
- 2027-03-01: GPT-6.2 Astra 和 GPT-6.2 Sol 的 Ultrafast API 定价计划从 Standard 费率的 3 倍上调至 6 倍。 [4][5][6]

## 来源

1. Introducing GPT-6.2 Astra and Sol | OpenAI. OpenAI. 发布于 2026-11-17. https://openai.com/index/introducing-gpt-6-2-astra-sol/ (访问于 2026-11-23; tier 3: official site)
2. Model Release Notes | OpenAI Help Center. OpenAI Help Center. 发布于 2026-11-17. https://help.openai.com/en/articles/9624314-model-release-notes (访问于 2026-11-23; tier 3: official site)
3. ChatGPT release notes | OpenAI Help Center. OpenAI Help Center. 发布于 2026-11-20. https://help.openai.com/en/articles/6825453-chatgpt-release-notes (访问于 2026-11-23; tier 3: official site)
4. GPT-6.2 Astra - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-astra (访问于 2026-11-23; tier 3: official site)
5. GPT-6.2 Sol - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-sol (访问于 2026-11-23; tier 3: official site)
6. Pricing - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/pricing (访问于 2026-11-23; tier 3: official site)
7. Using GPT-6.2 - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/guides/latest-model (访问于 2026-11-23; tier 3: official site)
8. GPT-6.2 System Card - OpenAI Deployment Safety Hub. OpenAI Deployment Safety Hub. 发布于 2026-11-17. https://deploymentsafety.openai.com/gpt-6-2-astra-sol (访问于 2026-11-23; tier 3: official site)
9. GPT-6 Astra: A new generation of intelligence | OpenAI. OpenAI. https://openai.com/index/gpt-6-astra/ (访问于 2026-11-23; tier 3: official site)
10. 'Essentially unusable': OpenAI launches GPT-6.2 Astra and Sol to negative reception from AI power users | VentureBeat. VentureBeat. 发布于 2026-11-17. https://venturebeat.com/technology/essentially-unusable-openai-launches-gpt-6-2-astra-and-sol-to-negative-reception-from-ai-power-users (访问于 2026-11-23; tier 2: academic or news)
11. Models - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "GPT-6.2." 版本 6f1cbcf9, 2026-11-23. https://mimirwiki.com/zh/wiki/gpt-6-2
