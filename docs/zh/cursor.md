---
title: "Cursor"
subtitle: "由 Anysphere, Inc. 创建并整合于 The X Subscription 中的 AI 编程代理与软件开发环境"
canonical_url: https://mimirwiki.com/zh/wiki/cursor
language: zh
page_class: entity
revision_sha256: 4fb2d1dfb753d2312a9b21be55de565d1bebd492712d22a1dd8feda11e09b109
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/zh/wiki/cursor.md
  txt: https://mimirwiki.com/zh/wiki/cursor.txt
  json: https://mimirwiki.com/zh/wiki/cursor.json
  jsonld: https://mimirwiki.com/zh/wiki/cursor.jsonld
translations:
  en: https://mimirwiki.com/wiki/cursor
  ko: https://mimirwiki.com/ko/wiki/cursor
  ja: https://mimirwiki.com/ja/wiki/cursor
---

# Cursor

> Cursor 是由成立于 2022 年的 Anysphere, Inc. 开发的 AI 编程代理与软件开发环境。2026 年 6 月，SpaceX 同意以 600 亿美元股票收购 Cursor。截至 2026-11-23，Cursor 通过 The X Subscription 以每月 0 至 200 美元的价格销售，支持 Agent、Tab 自动补全、Cloud Agents、Rules、Skills、MCP、CLI 以及多家提供商的模型。

Cursor 是由 Anysphere, Inc. 开发的 AI 编程代理与软件开发环境，用于理解代码库、规划与实现功能、调试程序以及审查代码变更。该初创公司于 2022 年以 Anysphere 名义成立，继 SpaceX 此前与 xAI 合并之后，于 2026 年 6 月同意以 600 亿美元的全股票交易被 SpaceX 收购。截至 2026-11-23，Cursor 作为 The X Subscription 的组成部分通过 X Subscription Corp. 分发，提供 Free、Plus（8 美元/月）、Premium（30 美元/月）、Super（100 美元/月）、Ultra（200 美元/月）、Teams（每席位每月 30 至 200 美元）以及定制 Enterprise 方案，同时面向原有订阅用户继续维持旧版 Cursor 方案。Cursor 运行于集成桌面 IDE、专用 Agents Window、命令行界面（CLI）、网页端及 iOS，支持自有 Grok 与 Composer 模型以及来自 OpenAI、Anthropic 和 Google 的第三方模型。

**别名:** Cursor IDE, Cursor 编辑器, Anysphere Cursor

## 关键事实

- **开发商:** Anysphere, Inc. [9]
- **SpaceX 收购协议:** 600 亿美元股票，2026-06-16 报道 [1]
- **个人方案价格:** Free（0 美元）、Plus（8 美元/月）、Premium（30 美元/月）、Super（100 美元/月）、Ultra（200 美元/月） (截至 2026-11-23) [5]
- **Teams 方案价格:** 每席位每月 30、100 或 200 美元 (截至 2026-11-23) [5]
- **安全认证:** SOC 2 Type II、ISO/IEC 27001:2022、ISO/IEC 42001:2023、AIUC-1 (截至 2026-11-23) [8]

## 事实摘要

- **开发商:** Anysphere, Inc. [9]
- **成立时间:** 2022 年（成立时名为 Anysphere） [1]
- **收购协议:** SpaceX，600 亿美元股票（2026-06-16 报道，预计 2026 年第三季度完成） [1]
- **订阅销售主体:** X Subscription Corp.（The X Subscription） (截至 2026-11-23) [4]
- **支持平台:** 编辑器、Agents Window、CLI、Cursor SDK、iOS 应用 (截至 2026-11-23) [6]
- **自定义机制:** Plugins、Rules、Skills、Subagents、Hooks、MCP (截至 2026-11-23) [3]
- **内置 Cursor 模型:** Grok 4.7、Grok 4.6、Grok 4.5、Composer 2.5 (截至 2026-11-23) [5]
- **个人方案:** Free（0 美元）、Plus（8 美元/月）、Premium（30 美元/月）、Super（100 美元/月）、Ultra（200 美元/月） (截至 2026-11-23) [5]
- **Teams 与 Enterprise:** Teams（30、100 或 200 美元/席位/月）；Enterprise（定制报价） (截至 2026-11-23) [5]
- **报道 ARR（2025 年 6 月）:** 超过 5 亿美元（Bloomberg 与 TechCrunch 报道） (截至 2025-06-05) [2]
- **安全认证:** AIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023、SOC 2 Type II (截至 2026-11-23) [8]
- **官方网站:** cursor.com [9]

## Cursor 产品功能、自定义机制与界面

在 Anysphere, Inc. 的官方文档中，Cursor 被定位为面向软件开发的编程代理，覆盖五项核心工作流：追踪与理解代码仓库、使用 Plan Mode 界定范围并实现功能、复现与修复缺陷、在合并前检查差异并运行检测，以及与外部开发工具集成。[3] 从 Free 档位起，Cursor 即提供基于自有模型的 Agent、Chat 和 Tab 补全的有限访问权限。[6]

Cursor 的 Agent 界面横跨桌面 IDE、专用 Agents Window、网页客户端、Cursor for iOS 以及命令行界面（CLI）。[3][6][7] 截至 2026-11-23，Agent 文档涵盖 Projects、Agent Review、Planning、Prompting、Voice Chat、Debugging、Design Mode、Tools 和 Security，而 CLI 文档涵盖 Shell Mode、ACP 以及无头（Headless）或 CI 执行。[3] Cursor 还发布了面向 TypeScript、Python 和 Bridge 集成的 Cursor SDK。[3]

Cursor 将工作流自定义归纳为六种文档化机制：Plugins、Rules、Skills、Subagents、Hooks 和[模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP）服务器。[3] 在 Teams 和 Enterprise 方案中，组织还会获得用于分发内部规则、技能和插件的团队市场（team marketplace）。[4][5]

Cursor 列出的原生集成涵盖源代码管理、IDE、通信和问题跟踪平台，包括 GitHub、GitLab、Azure DevOps、Bitbucket、JetBrains、Xcode、Slack、Microsoft Teams、Jira、Linear、Notion、Tailscale 和 Deeplinks。[3]

## Cursor Cloud Agents、Origin、Agent SDK 与 Voice Chat

Cursor 从 Premium 订阅档位起提供 Cloud Agents、Automations、Origin 代码托管和 Bugbot AI 代码审查。[4][5] 截至 2026-11-23，Cloud Agents 文档涵盖环境配置、构建、应用、自动化、Bugbot、安全审查、漏洞修复、拉取请求路由与审批、灰度发布、移动端访问、自托管机器以及 API。[3] Origin 提供代码仓库托管服务，支持 CLI、GitHub 镜像、CI 中的 CloneKit、拉取请求、Code Tours、仓库浏览与搜索以及访问策略。[3]

2026 年 10 月至 11 月期间，Cursor 在更新日志中发布了四项重要平台新增功能。[7]

- **Origin App Marketplace（2026 年 10 月 13 日）**：上线时即包含 20 多项集成并开放公开应用提交，涵盖部署（[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare)、Netlify、Render、Spacelift、Vercel）、CI（Buildkite、CircleCI、CloudBees、Depot、EngFlow、Namespace、RWX）、代码审查（CodeRabbit、Greptile、Tenki）、安全（Artemis Security、Semgrep、Socket Security、Upwind）、监控（Sentry）以及项目管理（Linear）。Origin 应用通过应用 JWT 和安装访问令牌进行身份验证，接收 Webhook 事件，并回写检查运行、拉取请求评论和审查结果。[7]
- **Cloud Agent Canvases 与 Environments API（2026 年 10 月 16 日）**：新增由云端代理构建的可共享交互式 Canvases，推出用于以编程方式管理代理云端环境的测试版 Environments API，将单个环境的容量扩展至最多 300 个代码仓库，并将大型环境的加载速度提升至原来的 5 倍。[7]
- **Agent SDK（2026 年 10 月 20 日）**：正式发布（GA），支持以代码文件夹形式定义代理，其中包含用于提示词的 `instructions.md`、用于类型化操作的 `tools/`、用于按需流程的 `skills/`、用于 MCP 服务器工具的 `mcp-connections/`，以及用于来自 GitHub、GitLab、Bitbucket、Slack、Webhook 和定时任务触发器的 `channels/`。该 SDK 提供本地初始化与演练场（`npx @cursor/agent-sdk init`、`agent-sdk dev`）、校验（`agent-sdk validate`）、评估与拉取请求 Webhook 回放（`agent-sdk eval`、`agent-sdk github replay`）、模板（安全审查器、所有者策略审批器、PR 自动修复器、Linear 或 Jira 分类器），以及部署至 Cursor 或自托管基础设施的功能（`agent-sdk deploy`）。[7]
- **Live Apps（2026 年 11 月 5 日）**：面向所有启用云端代理的付费方案发布。云端代理可基于新建或现有的 Cursor Origin 或 GitHub 仓库搭建 Web 应用，按需配置 Postgres 数据库，将身份验证置于 Cursor SSO 之后，运行确定性与代理式安全检查以排查凭证泄露等问题，并部署至指定 URL。团队管理员可以检查所有应用与密钥、添加自定义安全规则、批准被拦截的发布或取消发布应用；个人用户可以公开分享应用，并为脚本或 Grok Bot 签发 Cursor API 密钥。[7]

2026 年 11 月 6 日，Cursor 在 Agents Window、IDE、网页端和 Cursor for iOS 中上线了与编程代理进行语音交流的 Voice Chat，支持 Siri 唤醒（`"Hey Siri, call Cursor"`）和 iOS 锁屏实时活动（Live Activity）控制。[7] Voice Chat 基于 [Grok](https://mimirwiki.com/zh/wiki/grok) Voice 运行，提供 Ara、Eve、Leo、Rex 和 Sal 等可选音色，并在启用 Privacy Mode 时以零数据留存模式运行。[7] Voice Chat 提供双向语音对话，与语音转文本听写功能（原名 Voice Mode，在 IDE 中通过 `Cmd+Shift+Space` 切换）相互独立。[7]

## Cursor 支持的模型与 Cursor Router

Cursor 支持来自 SpaceXSI、[OpenAI](https://mimirwiki.com/zh/wiki/openai)、[Anthropic](https://mimirwiki.com/zh/wiki/anthropic)、Google 和 Muse 的模型；截至 2026-11-23，这些模型被划分为纳入订阅每周用量池的自有 Cursor 模型，以及按 API 标价从预付额度中计费的第三方模型。[3][5] 对符合条件的模型启用区域数据驻留（regional data residency）会在模型价格基础上加收 10%。[5]

Cursor 自有模型池涵盖 [Grok](https://mimirwiki.com/zh/wiki/grok) 4.7、Grok 4.6、Grok 4.5 和 Composer 2.5。[5] 当用量超出每周用量池时，截至 2026-11-23 适用以下每百万 token 费率。[3][5]

| Cursor 模型 | 默认 / 最大上下文 | 标准输入 / 缓存读取 / 输出（每百万 token） | Fast 模式输入 / 缓存读取 / 输出（每百万 token） | 美国数据驻留 |
| --- | --- | --- | --- | --- |
| Grok 4.7 | 256k / 500k | $2 / $0.5 / $6（500k：$4 / $1 / $12） | $4 / $1 / $12（500k Fast：$6 / $1.5 / $18） | 支持 |
| Grok 4.6 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $12 | 支持 |
| Grok 4.5 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $18 | 支持 |
| Composer 2.5 | 200k / - | $0.5 / $0.2 / $2.5 | $3 / $0.5 / $15 | 支持 |

第三方模型在 Free 和 Plus 方案中不可用，从 Premium 方案起在首次请求即按 API 标价计费。[5] 截至 2026-11-23，Cursor 文档列出了以下第三方模型，包括 [Claude](https://mimirwiki.com/zh/wiki/claude)、GPT-5.6 和 [Google Gemini](https://mimirwiki.com/zh/wiki/google-gemini) 模型，价格按每百万 token 计。[3][5]

| 第三方模型 | 默认 / 最大上下文 | 输入 | 缓存写入 | 缓存读取 | 输出 | 美国数据驻留 |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 300k / 1M | $8 | $10 | $0.2 | $40 | 支持 |
| Claude Opus 5.5 | 300k / 1M | $4 | $5 | $0.2 | $20 | 支持 |
| Claude Sonnet 5.5 | 200k / 1M | $2 | $2.5 | $0.1 | $10 | 支持 |
| Claude Haiku 5.5 | 300k / 1M | $0.1 | $0.125 | $0.01 | $0.5 | 支持 |
| GPT-5.6 Sol | 272k / 1M | $4 | $5 | $0.4 | $20 | 支持 |
| GPT-5.6 Terra | 272k / 1M | $2 | $2.5 | $0.2 | $12 | 支持 |
| GPT-5.6 Luna | 272k / 1M | $0.2 | $0.25 | $0.02 | $1.2 | 支持 |
| Gemini 4 Neon | 200k / 1M | $3 | - | $0.15 | $15 | 支持 |
| Gemini 4 Carbon | 200k / 1M | $2 | - | $0.1 | $10 | 支持 |
| Gemini 4 Argon | 200k / 1M | $2 | - | $0.1 | $10 | 支持 |
| Gemini 4 Hydrogen | 200k / 1M | $1.5 | - | $0.075 | $7.5 | 支持 |
| Gemini 3.1 Pro | 200k / 1M | $2 | - | $0.2 | $12 | 不支持 |
| Gemini 3.8 Flash | 200k / 1M | $0.75 | - | $0.075 | $3.75 | 支持 |
| Muse Wonder | 300k / 1M | $4 | - | $0.2 | $20 | 不支持 |

Cursor 的 Auto 功能通过 Cursor Router 将模型选择划分为三种模式：Cost、Balance 和 Intelligence。[5][6] 个人方案支持 Cost 模式（原 Auto 模式的继任者），无论实际由哪个模型响应，均作为 Cursor 模型请求从每周用量池中扣减。[5][6] Balance 和 Intelligence 模式面向 Teams 和 Enterprise 方案在 Agents Window、编辑器、CLI、Cursor SDK 和 iOS 应用中推出，Enterprise 团队默认未启用，需由管理员主动开启；路由至 Cursor 模型的请求从每周用量池扣减，而路由至第三方模型的请求则从预付额度按 API 标价计费，并在适用时加收 Cursor Token Rate。[5][6]

## Cursor 订阅方案、The X Subscription 与旧版定价

Cursor 作为 The X Subscription 的组成部分销售；The X Subscription 是整合 Grok、Cursor 和 X 的单一订阅产品，通过 X Subscription Corp. 直接分发，没有授权经销商或第三方卖家。[4][5][6] 所有公布订阅价格均不含增值税（VAT）等适用税费。[4][5] 截至 2026-11-23，Cursor 在 The X Subscription 下提供以下方案。[4][5][6]

| 方案 | 月付价格 | 年付价格 | 包含每周用量池 | 第三方模型 |
| --- | --- | --- | --- | --- |
| Free | $0 | - | 有限 | 不可用 |
| Plus | $8 | $80 | 基础（Base） | 不可用 |
| Premium | $30 | $300 | Plus 的 4 倍 | 按 API 标价从预付额度计费 |
| Super | $100 | $1,000 | Plus 的 15 倍 | 按 API 标价从预付额度计费 |
| Ultra | $200 | $2,000 | Plus 的 50 倍 | 按 API 标价从预付额度计费 |
| Teams | 每席位 $30、$100 或 $200 | - | 对应席位档位（Plus 的 4 倍至 50 倍） | API 标价，符合条件模型另加 Cursor Token Rate |
| Enterprise | 定制报价 | 定制报价 | Grok 与 Cursor 共享池 | API 标价，符合条件模型另加 Cursor Token Rate |

每个付费方案提供一个每周刷新的 Cursor 模型用量池，可在编辑器内的 Agent、CLI、Cloud Agents、Grok Bot 以及 Grok 应用（Chat、Imagine、Voice 和 Bot）之间共享；付费方案包含 Grok API 访问权限，但 API 用量按标准模型费率单独计费。[4][5] Plus 以固定配置运行 Cursor 模型（关闭 Fast 模式、中等推理强度，以及 Grok 4.7 的 256k 上下文窗口），且不包含 Auto、Cloud Agents、Automations、Bugbot、Origin、第三方模型及自带 API 密钥（BYOK）。[5] Super 增加高峰时段优先模型访问权限，Ultra 增加对新产品与新模型的最早访问权限。[4][5] 用完每周用量池后，Cursor 不会降低请求质量或速度；用户可等待每周重置、购买预付额度充值（手动充值或在 `grok.com/dashboard/billing` 管理带月度消费上限的自动充值），或升级档位。[5] 自助订阅方案支持主流信用卡与借记卡，允许在续费前最晚 24 小时取消，升级即时生效，降级在当前计费周期结束时生效。[4][6]

Teams 方案允许在同一团队中混合配置 Premium、Super 和 Ultra 席位档位（团队不支持 Plus），并增加集中计费、用量分析、团队范围强制 Privacy Mode、自定义 Chat 数据留存、团队市场以及 SAML/OIDC SSO。[4][5] Enterprise 方案进一步增加共享用量池、发票或采购订单结算及电汇付款、SCIM 席位管理、精细化支出控制、分组限额、审计日志、服务账号、高级网络与 MCP 控制以及优先支持。[4][5] 在 Teams 和 Enterprise 方案中，符合条件的第三方模型请求和 BYOK 用量对输入、输出和缓存 token 均收取每百万 token 0.25 美元的 Cursor Token Rate；个人方案、Cursor 模型、Cost 模式请求，以及在所有价格档位中缓存读取价格均严格低于每百万 token 0.10 美元的第三方模型免收该费用。[5]

Cursor 同时面向现有订阅用户保留在 The X Subscription 之前销售的旧版方案。[5][6] 旧版方案已停止向新客户开放，除非用户取消订阅或永久切换至 The X Subscription（切换时旧版订阅将按比例退款并取消），否则继续有效；计费在 `cursor.com/dashboard/billing` 通过 Stripe 管理，并提供两个月度用量池（Cursor Models 与 Other Models）以及超额请求的按需计费。[5][6] 旧版按请求计费方案还曾包含用于扩展上下文窗口的 Max Mode，按模型 API 费率加收 20% 计费。[5]

| 旧版 Cursor 方案 | 价格 | The X Subscription 对应方案 |
| --- | --- | --- |
| Hobby | 免费 | Free |
| Start（仅限印度） | ₹649/月（含税） | Plus |
| Pro | $20/月 | Premium |
| Pro+ | $60/月 | Super |
| Ultra | $200/月 | Ultra |
| Teams Standard | $40/用户/月 | Teams（Premium 席位） |
| Teams Premium | $120/用户/月 | Teams（Super 席位） |

## Cursor 安全、合规与隐私控制

Cursor 在 `cursor.com/security`（最后更新于 2026 年 8 月 25 日）公布其安全架构，在 `cursor.com/privacy`（最后更新于 2026 年 11 月 6 日）公布其隐私政策。[8][9] 截至 2026-11-23，Cursor 持有 AIUC-1、ISO/IEC 27001:2022 和 ISO/IEC 42001:2023 认证以及 SOC 2 Type II 鉴证报告，并可通过 `trust.cursor.com` 按需提供证书、审计报告、渗透测试执行摘要及次级处理方（subprocessor）列表。[4][8][9] Cursor 承诺至少每年进行一次第三方渗透测试。[8]

Cursor 声明每位次级处理方均接受供应商风险评估与年度复审，基础设施访问遵循最小权限原则并配合多因素认证（MFA）与日志监控，同时严格执行模型黑名单以确保请求绝不会路由至被禁用的模型。[8] Cursor 声明不在中国使用或维护基础设施，也不聘用总部位于中国的公司担任次级处理方。[8] 向 `security-reports@cursor.com` 报告的安全漏洞会在五个工作日内予以确认回复，重大安全事件将通过电子邮件通知受影响用户。[8] Cursor 亦使用 Bugbot 和 Cloud Agent 自动化来监控自身代码库。[8]

Privacy Mode 适用于 Free、个人、Teams 和 Enterprise 全部方案，用户可在设置中自行开启，管理员也可在组织范围内强制实施，新加入的团队成员会自动继承团队设置。[4][8] Cursor 声明在开启 Privacy Mode 后，依托技术控制和提供商合同条款，用户代码数据不会被 Cursor 或其模型提供商用于训练，且 Voice Chat 以零数据留存方式运行。[4][7][8] 根据隐私政策，Anysphere, Inc. 负责个人账户，而由雇主配发、Anysphere 担任数据处理方的商业账户则受客户协议约束。[9] Anysphere 声明除非被标记用于安全审查、由用户明确作为反馈报告或经用户明确批准，否则输入（Inputs）和建议（Suggestions）不会用于训练模型；同时声明不会故意收集基因、生物特征、健康或宗教数据，也不向 18 岁以下用户提供服务。[9] 用户可直接从设置仪表板删除账户。[8]

面向组织级部署，Cursor 在文档中列出了 SAML/OIDC SSO、SCIM 置备、合规与审计日志、服务账号、移动设备管理（MDM）部署、数据加密与客户托管加密密钥（CMEK）、自动运行与浏览器及网络控制，以及针对代码仓库、模型、MCP 服务器和 Grok Bot 的访问控制。[4][8]

## Cursor 企业沿革、融资历程与 SpaceX 收购协议

Cursor 由 Anysphere, Inc. 创建，该公司成立于 2022 年，并于 2024 年参加了 [OpenAI](https://mimirwiki.com/zh/wiki/openai) 的创业加速器项目。[1][9] 2024 年底，Anysphere 以 25 亿美元投前估值融资 1 亿美元。[2] 2025 年初，OpenAI 及其他潜在买家曾就收购事宜接洽 Anysphere，Anysphere 拒绝了这些要约。[2]

据 TechCrunch 报道，Anysphere 的年化经常性收入（ARR）于 2025 年 4 月中旬达到 3 亿美元，据 Bloomberg 和 TechCrunch 引述的消息人士称，到 2025 年 6 月 5 日已突破 5 亿美元。[2] 2025 年 6 月 5 日，TechCrunch 报道称 Anysphere 以 99 亿美元估值完成了 9 亿美元 C 轮融资（一年内的第三次融资），由老股东 Thrive Capital 领投，Andreessen Horowitz、Accel 和 DST Global 参投。[1][2] 当时，Cursor 提供两周免费试用，试用后可转为每月 20 美元的 Pro 或每月 40 美元的商业订阅，并同步推出了企业版许可。[2] 2025 年底，Anysphere 又追加融资 23 亿美元，估值达到约 290 亿美元。[1]

2026 年初，xAI 聘用了 Cursor 的两名资深工程负责人，2026 年 4 月 Business Insider 报道称 xAI 同意向 Cursor 出租数据中心算力容量。[1] 在 SpaceX 提出收购要约之前，Cursor 原本接近完成一轮由 Andreessen Horowitz、Thrive Capital 和 Nvidia 等投资者参与、估值 500 亿美元的 20 亿美元融资。[1] 2026 年 4 月，在 SpaceX 首次公开募股（IPO）前夕，SpaceX 与 Cursor 宣布达成协议：SpaceX 要么以 600 亿美元股票收购 Cursor，要么在交易未能推进时支付 100 亿美元分手费。[1]

2026 年 6 月 16 日，在 SpaceX 以每股 135 美元完成 IPO 数日后，且继 SpaceX 此前于 2026 年与 xAI 合并之后，TechCrunch 报道称 SpaceX 已同意以 600 亿美元股票收购 Cursor，SpaceX 表示交易预计于 2026 年第三季度完成。[1] 截至 2026-11-23，Cursor 的公开网站和文档显示其已与 [Grok](https://mimirwiki.com/zh/wiki/grok) 和 X 一同整合至由 X Subscription Corp. 销售的 The X Subscription 中，链接至 SpaceXSI Subscription Terms 并将 SpaceXSI 列为受支持的模型提供商，同时在网站版权声明和隐私政策中仍保留 `Anysphere, Inc.`。[4][5][8][9]

## 常见问题

### Cursor 的价格是多少？

截至 2026-11-23，Cursor 通过 The X Subscription 提供五个个人订阅档位（均不含税）：Free（0 美元/月）、Plus（8 美元/月或 80 美元/年）、Premium（30 美元/月或 300 美元/年）、Super（100 美元/月或 1,000 美元/年）和 Ultra（200 美元/月或 2,000 美元/年）。Teams 席位价格为每席位每月 30 美元、100 美元或 200 美元，Enterprise 方案采用定制报价。Premium 及以上方案中的第三方模型按 API 标价从预付额度中单独计费。 [4][5]

### Pro 和 Pro+ 等旧版 Cursor 方案现况如何？

包括 Hobby（免费）、印度专属 Start（含税 649 卢比/月）、Pro（20 美元/月）、Pro+（60 美元/月）、Ultra（200 美元/月）、Teams Standard（40 美元/用户/月）和 Teams Premium（120 美元/用户/月）在内的旧版 Cursor 方案已停止向新客户开放。现有订阅用户只要不取消订阅或不选择永久切换至 The X Subscription，即可继续保留旧版方案、两个月度用量池及按需计费。 [5][6]

### Cursor 支持哪些 AI 模型？

截至 2026-11-23，付费方案包含一个用于 Cursor 自有模型的共享每周用量池，涵盖 Grok 4.7、Grok 4.6、Grok 4.5 和 Composer 2.5。在 Premium 及以上方案中，Cursor 还支持第三方模型，包括 Claude（Anthropic）、GPT-5.6（OpenAI）、Gemini（Google）和 Muse Wonder，按 API 标价从预付额度中计费。 [3][5]

### Cursor 的 Privacy Mode 和安全认证如何运作？

截至 2026-11-23，Cursor 持有 AIUC-1、ISO/IEC 27001:2022 和 ISO/IEC 42001:2023 认证以及 SOC 2 Type II 鉴证报告，相关证明文件可在 trust.cursor.com 申请获取。所有方案均提供 Privacy Mode，管理员可在团队范围内强制启用；开启后不会将用户代码数据用于模型训练，且 Voice Chat 以零数据留存方式运行。 [7][8][9]

### Cursor 包含哪些自定义与自动化功能？

Cursor 文档列出了六种自定义机制：Plugins、Rules、Skills、Subagents、Hooks 以及模型上下文协议（MCP）服务器。Cursor 还提供命令行界面（CLI）、Cloud Agents、Automations、Origin 代码托管、Bugbot 代码审查、Live Apps、Voice Chat，以及用于构建和部署代码定义代理的 Agent SDK。 [3][4][7]

### Cursor 归哪家公司所有？

Cursor 由成立于 2022 年的 Anysphere, Inc. 开发。2026 年 6 月 16 日，TechCrunch 报道称 SpaceX 同意以 600 亿美元股票交易收购 Cursor，预计于 2026 年第三季度完成交割。截至 2026-11-23，Cursor 订阅作为 The X Subscription 的一部分通过 X Subscription Corp. 销售，而 Cursor 的隐私政策和网站版权声明中仍列明 Anysphere, Inc.。 [1][4][9]

## 可引用的句子

- Cursor 由 Anysphere 开发，该公司成立于 2022 年，并于 2024 年参加了 OpenAI 的创业加速器项目。 [1]
- 2025 年 6 月 5 日，TechCrunch 报道称 Anysphere 以 99 亿美元估值融资 9 亿美元，年化经常性收入（ARR）突破 5 亿美元。 [2]
- 2026 年 6 月 16 日，TechCrunch 报道称 SpaceX 同意以 600 亿美元的全股票交易收购 Cursor，交易预计于 2026 年第三季度完成。 [1]
- 截至 2026-11-23，Cursor 作为 The X Subscription 的组成部分由 X Subscription Corp. 直接销售，个人月付方案不含税价格为 0 美元（Free）、8 美元（Plus）、30 美元（Premium）、100 美元（Super）和 200 美元（Ultra）。 [4][5]
- 截至 2026-11-23，Cursor 的 Teams 和 Enterprise 方案对符合条件的第三方模型请求以及自带 API 密钥（BYOK）用量加收每百万 token 0.25 美元的 Cursor Token Rate，个人方案不收取该费用。 [5]
- 包括每月 20 美元的 Pro 和每月 60 美元的 Pro+ 在内的旧版 Cursor 方案仍对现有订阅用户保持有效，并保留两个月度用量池，除非用户取消订阅或永久切换至 The X Subscription。 [5][6]
- 截至 2026-11-23，Cursor 持有 AIUC-1、ISO/IEC 27001:2022 和 ISO/IEC 42001:2023 认证以及 SOC 2 Type II 鉴证报告，并声明在中国不维护任何基础设施。 [8]
- 2026 年 10 月至 11 月期间，Cursor 于 10 月 13 日上线 Origin App Marketplace，于 10 月 20 日发布 Agent SDK，于 11 月 5 日推出 Live Apps，并于 11 月 6 日推出由 Grok Voice 驱动的 Voice Chat。 [7]

## 时间线

- 2022: Cursor 的开发商 Anysphere 成立。 [1]
- 2024: Anysphere 参加 OpenAI 创业加速器项目，并于 2024 年底以 25 亿美元投前估值融资 1 亿美元。 [1][2]
- 2025-04: TechCrunch 报道称 Anysphere 年化经常性收入达到 3 亿美元。 [2]
- 2025-06-05: TechCrunch 报道称 Anysphere 完成由 Thrive Capital 领投、估值 99 亿美元的 9 亿美元 C 轮融资，年化经常性收入突破 5 亿美元。 [1][2]
- 2026-04: SpaceX 与 Cursor 宣布达成 600 亿美元股票收购或 100 亿美元分手费协议，同期有报道称 xAI 向 Cursor 出租数据中心容量。 [1]
- 2026-06-16: TechCrunch 报道称 SpaceX 同意以 600 亿美元股票收购 Cursor，预计于 2026 年第三季度完成交割。 [1]
- 2026-08-25: Cursor 更新安全文档，列明 AIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023 认证以及 SOC 2 Type II 鉴证报告。 [8]
- 2026-10-13: Cursor 上线包含 20 多项合作伙伴集成的 Origin App Marketplace，并开放公开提交。 [7]
- 2026-10-16: Cursor 为云端代理新增可共享交互式 Canvases、测试版 Environments API，并支持每个云端环境最多 300 个代码仓库。 [7]
- 2026-10-20: Cursor 正式发布（GA）Agent SDK。 [7]
- 2026-11-05: Cursor 在付费方案中上线通过云端代理部署的 Live Apps。 [7]
- 2026-11-06: Cursor 上线由 Grok Voice 驱动的编程代理 Voice Chat，并更新隐私政策。 [7][9]

## 来源

1. SpaceX to acquire Cursor for $60B in stock, days after blockbuster IPO | TechCrunch. TechCrunch. 发布于 2026-06-16. https://techcrunch.com/2026/06/16/spacex-to-acquire-cursor-for-60b-in-stock-days-after-blockbuster-ipo/ (访问于 2026-11-23; tier 2: academic or news)
2. Cursor's Anysphere nabs $9.9B valuation, soars past $500M ARR | TechCrunch. TechCrunch. 发布于 2025-06-05. https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/ (访问于 2026-11-23; tier 2: academic or news)
3. Cursor Docs - Agent, Rules, MCP, Skills & CLI. Cursor. https://cursor.com/docs (访问于 2026-11-23; tier 3: official site)
4. Cursor · Pricing. Cursor. https://cursor.com/pricing (访问于 2026-11-23; tier 3: official site)
5. Models & Pricing | Cursor Docs. Cursor. https://cursor.com/docs/models-and-pricing (访问于 2026-11-23; tier 3: official site)
6. Pricing and plans | Cursor Docs. Cursor. https://cursor.com/help/account-and-billing/pricing (访问于 2026-11-23; tier 3: official site)
7. What's New in Cursor - Latest Updates & Release Notes. Cursor. https://cursor.com/changelog (访问于 2026-11-23; tier 3: official site)
8. Cursor · Security. Cursor. https://cursor.com/security (访问于 2026-11-23; tier 3: official site)
9. Cursor · Privacy Policy. Cursor. https://cursor.com/privacy (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Cursor." 版本 4fb2d1df, 2026-11-23. https://mimirwiki.com/zh/wiki/cursor
