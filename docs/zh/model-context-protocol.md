---
title: "模型上下文协议"
subtitle: "将 AI 应用连接到外部工具和数据的开放协议"
canonical_url: https://mimirwiki.com/zh/wiki/model-context-protocol
language: zh
page_class: anchor
revision_sha256: 651eac1551b09726ca552cb355bc151af4299b455a9c9d2d5ebce5ef0755a173
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/model-context-protocol.md
  txt: https://mimirwiki.com/zh/wiki/model-context-protocol.txt
  json: https://mimirwiki.com/zh/wiki/model-context-protocol.json
  jsonld: https://mimirwiki.com/zh/wiki/model-context-protocol.jsonld
translations:
  en: https://mimirwiki.com/wiki/model-context-protocol
  ko: https://mimirwiki.com/ko/wiki/model-context-protocol
  ja: https://mimirwiki.com/ja/wiki/model-context-protocol
  es: https://mimirwiki.com/es/wiki/model-context-protocol
---

# 模型上下文协议

> 模型上下文协议（MCP）是一种开放协议，让 AI 应用通过统一接口连接外部工具和数据源。它使用 JSON-RPC 2.0 消息，经 stdio 或 Streamable HTTP 传输。Anthropic 于 2024 年 11 月 25 日发布 MCP，自 2025 年 12 月起由 Linux 基金会旗下的 Agentic AI Foundation 托管。当前版本为 2026-07-28。

模型上下文协议（Model Context Protocol，MCP）是一种开放协议，用于规范基于大语言模型的应用连接外部数据源和工具的方式。MCP 消息遵循 JSON-RPC 2.0，通过 stdio 和 Streamable HTTP 两种标准传输方式在主机、客户端和服务器之间传递。Anthropic 于 2024 年 11 月 25 日将该协议开源，并在 2025 年 12 月 9 日的公告中将其捐赠给 Linux 基金会旗下新成立的 Agentic AI Foundation。截至 2026 年 11 月 21 日，当前协议版本为 2026-07-28，该修订版使协议变为无状态。

**别名:** MCP, Model Context Protocol

## 关键事实

- **首次发布:** 2024-11-25，Anthropic [8]
- **当前协议版本:** 2026-07-28 (截至 2026-11-21) [2]
- **消息格式:** JSON-RPC 2.0 [1]
- **标准传输方式:** stdio、Streamable HTTP [4]
- **所属基金会:** Agentic AI Foundation（Linux 基金会），2025-12-09 公布 [9]

## 事实摘要

- **类型:** 将 LLM 应用连接到外部数据源和工具的开放协议 [1]
- **最初开发者:** Anthropic [8]
- **首次发布:** 2024-11-25 [8]
- **当前版本:** 2026-07-28 (截至 2026-11-21) [2]
- **版本格式:** 日期字符串（YYYY-MM-DD） [2]
- **消息格式:** JSON-RPC 2.0，UTF-8 编码 [4]
- **标准传输方式:** stdio、Streamable HTTP [4]
- **服务器功能:** 资源、提示、工具 [1]
- **授权:** 可选；基于 HTTP 的传输方式以 OAuth 2.1 为基础 [5]
- **法律实体:** Model Context Protocol a Series of LF Projects, LLC [6]
- **许可证:** Apache License 2.0（代码和规范）；CC BY 4.0（其他文档） [6]
- **官方 SDK:** TypeScript、Python、C#、Go、Rust、Ruby、Java、Swift、PHP、Kotlin (截至 2026-11-21) [7]

## 什么是模型上下文协议

模型上下文协议（Model Context Protocol，MCP）是一种开放协议，用于把基于大语言模型（LLM）的应用连接到外部数据源和工具。[1] 规范列出三项用途：向语言模型共享上下文信息、向 AI 系统开放工具和能力，以及构建可组合的集成与工作流。[1] 规范称其设计借鉴了 [Language Server Protocol](https://mimirwiki.com/zh/wiki/language-server-protocol)。后者在各类开发工具中统一了编程语言支持，MCP 则统一了为 AI 应用接入上下文和工具的方式。[1]

MCP 定义了三种角色。主机（host）是发起连接的 LLM 应用，客户端（client）是主机内部的连接器，服务器（server）是提供上下文和能力的服务。[1] 服务器可以提供资源（上下文和数据）、提示（模板化的消息和工作流）和工具（可由模型执行的函数）。客户端可以提供征询（elicitation）功能，服务器借此向用户索取更多信息。[1]

[Anthropic](https://mimirwiki.com/zh/wiki/anthropic) 于 2024 年 11 月 25 日宣布将 MCP 作为开源标准发布。当时公开的内容包括规范和软件开发工具包（SDK）、Claude Desktop 应用对本地 MCP 服务器的支持，以及一个 MCP 服务器开源仓库。[8] 公告称该协议由 Anthropic 的 David Soria Parra 和 Justin Spahr-Summers 创建。[8]

## 模型上下文协议的消息格式与架构

模型上下文协议的所有消息都采用 [JSON-RPC](https://mimirwiki.com/zh/wiki/json-rpc) 2.0 编码，且必须使用 UTF-8。[1][4] 客户端发送请求和通知，服务器以响应和通知作答。在当前修订版中不存在其他方向：服务器不会发起 JSON-RPC 请求，客户端也不会发送 JSON-RPC 响应。[4]

自 2026-07-28 修订版起，MCP 在协议层面是无状态的。早期修订版中的 `initialize` 握手已被移除，每个请求都在 `_meta` 字段中携带协议版本和客户端能力。[3] 服务器必须实现 `server/discover` 方法，用来报告其支持的协议版本、能力和身份信息。客户端可以先调用该方法，但并非必须。[2][3]

当服务器在处理调用的过程中需要客户端一侧提供信息时，它会返回一个标记为 `input_required` 的结果，其中列出所需内容，客户端随后附上答复并重新发送原请求。规范把这种模式称为多轮往返请求（Multi Round-Trip Requests，MRTR），它取代了早期修订版中由服务器发起的请求。[3] 工具列表变更这类长期存在的变更通知，通过客户端用 `subscriptions/listen` 请求打开的流来传递。[3]

## 模型上下文协议的传输方式与授权

模型上下文协议定义了 stdio 和 Streamable HTTP 两种标准传输方式。使用 stdio 时，客户端把服务器作为子进程启动，双方通过标准输入输出交换以换行分隔的消息。使用 Streamable HTTP 时，每条消息都是发往单一 MCP 端点的 HTTP POST，回复要么是一个 JSON 对象，要么是仅限于该请求的 Server-Sent Events（SSE）流。[4] 两种方式下协议语义完全相同。只要保留 JSON-RPC 消息格式、消息模式和按请求携带元数据的模型，也可以实现自定义传输方式。[4]

在 Streamable HTTP 中，部分元数据会同时写入 HTTP 标头，使中间设备无需解析正文就能路由请求。[4] 协议版本由 `MCP-Protocol-Version` 标头携带，2026-07-28 修订版还要求 POST 请求带有 `Mcp-Method` 和 `Mcp-Name` 标头。[2][3]

在 MCP 中，授权是可选的。对于基于 HTTP 的传输方式，规范以 [OAuth](https://mimirwiki.com/zh/wiki/oauth) 2.1 为基础：受保护的 MCP 服务器充当 OAuth 2.1 资源服务器，MCP 客户端充当 OAuth 2.1 客户端，服务器必须发布 OAuth 2.0 受保护资源元数据（RFC 9728），以便客户端找到授权服务器。[5] 使用 stdio 的实现不应遵循这一流程，而应从环境中获取凭据。[5]

## 模型上下文协议的版本与 2026-07-28 修订版

模型上下文协议的版本是 `YYYY-MM-DD` 格式的日期字符串。版本标识表示最后一次引入不向后兼容变更的日期，保持向后兼容的更新不会改变它。[2] 截至 2026 年 11 月 21 日，当前版本为 2026-07-28。[2] GitHub 上规范仓库的发布页面列出了 2024-11-05、2025-03-26、2025-06-18、2025-11-25 和 2026-07-28 这几个修订版。[10] 客户端和服务器可以同时支持多个版本；如果服务器不支持所请求的版本，会返回 `UnsupportedProtocolVersionError`，并列出它支持的版本。[2]

维护者为 2026-07-28 修订版撰写的发布文章称，这次修订使协议从双向的有状态协议转变为无状态的请求与响应协议，因此负载均衡器后面的任何服务器实例都能处理任意请求。[11] 变更记录列出的主要变化如下。[3]

| 方面 | 2026-07-28 修订版中的变化 |
| --- | --- |
| 会话 | 移除协议层会话和 `Mcp-Session-Id` 标头 |
| 握手 | 移除 `initialize` 握手，版本和能力随每个请求发送 |
| 发现 | 新增 `server/discover`，服务器必须实现 |
| 服务器索取输入 | 以多轮往返请求取代服务器发起的请求 |
| 通知 | 以 `subscriptions/listen` 取代 HTTP GET 端点和资源订阅方法 |
| 任务 | 从实验性核心功能移入 `io.modelcontextprotocol/tasks` 扩展 |
| 弃用 | Roots、Sampling、Logging、HTTP+SSE 传输方式和 OAuth 动态客户端注册 |

被标记为弃用（deprecated）的功能在可被移除之前至少保留在规范中 12 个月，适用加速移除例外时则至少保留 90 天。[2] 2026 年 11 月 11 日，首席维护者宣布改为每六个月发布一次，规范版本一般安排在 3 月和 9 月的最后一个星期二发布。下一次发布的目标日期是 2027 年 3 月 30 日，版本标识预计为 2027-03-30。[12]

## 模型上下文协议的治理与许可

模型上下文协议由 [Linux 基金会](https://mimirwiki.com/zh/wiki/linux-foundation)托管。2025 年 12 月 9 日，Linux 基金会宣布成立 [Agentic AI Foundation](https://mimirwiki.com/zh/wiki/agentic-ai-foundation)（AAIF），三个创始项目分别是 Anthropic 贡献的 MCP、Block 贡献的 goose 和 OpenAI 贡献的 AGENTS.md。[9] 该基金会成立时的白金会员为 Amazon Web Services、Anthropic、Block、Bloomberg、[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare)、Google、Microsoft 和 OpenAI。[9] 项目的治理文件写明其法律形式为 Model Context Protocol a Series of LF Projects, LLC。[6]

MCP 的技术决策遵循维护者层级结构。贡献者（Contributor）提交议题和拉取请求，维护者（Maintainer）负责 SDK、工作组等组成部分，核心维护者（Core Maintainer）把握规范方向，首席维护者（Lead Maintainer）拥有最终决定权。[6] 成员资格属于个人，不为企业保留席位。截至 2026 年 11 月 21 日，治理页面列出的首席维护者为 David Soria Parra 和 Den Delimarsky。[6] 对规范的修改以规范增强提案（Specification Enhancement Proposal，SEP）的形式提出。[6]

代码和规范方面的贡献采用 Apache License 2.0。规范以外的文档以知识共享署名 4.0 国际许可协议发布。[6]

## 模型上下文协议的 SDK、采用情况与局限

模型上下文协议项目维护着十种编程语言的官方 SDK。截至 2026 年 11 月 21 日，其 SDK 页面把 TypeScript、Python、C#、Go、Rust 和 Ruby 列为 Tier 1，Java 列为 Tier 2，Swift、PHP 和 Kotlin 列为 Tier 3。分级依据是功能完整度、协议支持情况和维护承诺。[7] 各 SDK 按各自的进度支持新的修订版。2026-07-28 修订版发布当天，TypeScript、Python、Go 和 C# SDK 已支持该修订版。[7][11]

关于 MCP 采用规模的公开数据来自项目本身及其所属基金会。Linux 基金会在 2025 年 12 月 9 日表示，已发布的 MCP 服务器超过 10,000 个，Claude、Cursor、Microsoft Copilot、Gemini、VS Code 和 ChatGPT 已采用该协议。[9] 维护者在 2026 年 7 月 28 日称，Tier 1 SDK 的月下载量接近 5 亿次，TypeScript 和 Python SDK 的累计下载量均已超过 10 亿次。[11]

MCP 是一份协议规范，有些事项不在它的保证范围之内。规范指出，协议本身无法强制执行其关于用户同意和安全的原则，因此要求主机在调用任何工具之前取得用户的明确同意，并且除非工具描述来自受信任的服务器，否则应视为不可信。[1] 授权是可选的，Tasks 和 MCP Apps 等扩展是核心协议之外需要主动启用的附加功能。[1][5] 无状态指的是协议而不是应用：需要跨调用保存状态的服务器可以签发显式句柄，再由调用方作为普通工具参数传回。[3]

## 常见问题

### 模型上下文协议的当前版本是什么？

截至 2026 年 11 月 21 日，当前协议版本为 2026-07-28。版本是 YYYY-MM-DD 格式的日期字符串，只有出现不向后兼容的变更时才会改变。 [2]

### 模型上下文协议由谁治理？

该项目由 Linux 基金会托管，法律形式为 Model Context Protocol a Series of LF Projects, LLC；Anthropic 将其贡献给了 2025 年 12 月 9 日宣布成立的 Agentic AI Foundation。技术决策由以个人身份参与的维护者作出，首席维护者拥有最终决定权。 [6][9]

### 模型上下文协议使用什么消息格式和传输方式？

MCP 消息采用 UTF-8 编码的 JSON-RPC 2.0。标准传输方式有两种：一是 stdio，服务器作为本地子进程启动；二是 Streamable HTTP，每条消息都是发往单一端点的 HTTP POST。 [1][4]

### 模型上下文协议必须使用 OAuth 吗？

不是。在 MCP 中授权是可选的。在基于 HTTP 的传输方式上使用授权时，规范以 OAuth 2.1 为基础；stdio 实现则从环境中获取凭据。 [5]

### 模型上下文协议 2026-07-28 修订版有哪些变化？

该修订版移除了 initialize 握手和协议层会话，每个请求都是自包含的。它新增了 server/discover 方法和多轮往返请求，并把 Roots、Sampling 和 Logging 标记为弃用。 [3]

### 模型上下文协议有哪些语言的官方 SDK？

截至 2026 年 11 月 21 日，项目列出了 TypeScript、Python、C#、Go、Rust、Ruby、Java、Swift、PHP 和 Kotlin 的官方 SDK，其中前六种被列为 Tier 1。 [7]

## 可引用的句子

- 模型上下文协议使用 JSON-RPC 2.0 消息。 [1]
- 截至 2026 年 11 月 21 日，模型上下文协议的当前版本为 2026-07-28。 [2]
- Anthropic 于 2024 年 11 月 25 日将模型上下文协议开源。 [8]
- Linux 基金会于 2025 年 12 月 9 日宣布，Anthropic 已将模型上下文协议贡献给新成立的 Agentic AI Foundation。 [9]
- 模型上下文协议定义了 stdio 和 Streamable HTTP 两种标准传输方式。 [4]
- 模型上下文协议 2026-07-28 修订版移除了 initialize 握手和协议层会话，使协议变为无状态。 [3]
- 在模型上下文协议中授权是可选的，基于 HTTP 的传输方式以 OAuth 2.1 为基础。 [5]
- 根据维护者 2026 年 11 月 11 日的公告，模型上下文协议下一次规范发布的目标日期是 2027 年 3 月 30 日。 [12]

## 时间线

- 2024-11-25: Anthropic 将模型上下文协议开源。 [8]
- 2025-03-26: 2025-03-26 修订版发布，HTTP+SSE 传输方式自该修订版起被弃用。 [10][3]
- 2025-06-18: 2025-06-18 修订版发布。 [10]
- 2025-11-25: 2025-11-25 修订版发布，实验性地支持任务。 [10][12]
- 2025-12-09: Linux 基金会宣布成立 Agentic AI Foundation，Anthropic 向其贡献模型上下文协议。 [9]
- 2026-07-28: 2026-07-28 修订版发布，协议变为无状态。 [11][3]
- 2026-11-11: 首席维护者宣布每六个月发布一次，并把下一次发布的目标日期定为 2027-03-30。 [12]

## 来源

1. Specification - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28 (访问于 2026-11-21; tier 3: official site)
2. Versioning - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/versioning (访问于 2026-11-21; tier 3: official site)
3. Key Changes - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/changelog (访问于 2026-11-21; tier 3: official site)
4. Overview - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports (访问于 2026-11-21; tier 3: official site)
5. Authorization - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (访问于 2026-11-21; tier 3: official site)
6. Governance and Stewardship - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/community/governance (访问于 2026-11-21; tier 3: official site)
7. SDKs - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/docs/sdk (访问于 2026-11-21; tier 3: official site)
8. Introducing the Model Context Protocol. Anthropic. 发布于 2024-11-25. https://www.anthropic.com/news/model-context-protocol (访问于 2026-11-21; tier 3: official site)
9. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. 发布于 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (访问于 2026-11-21; tier 3: official site)
10. Releases · modelcontextprotocol/modelcontextprotocol · GitHub. Model Context Protocol project (GitHub). https://github.com/modelcontextprotocol/modelcontextprotocol/releases (访问于 2026-11-21; tier 3: official site)
11. The 2026-07-28 Specification. Model Context Protocol Blog. 发布于 2026-07-28. https://blog.modelcontextprotocol.io/posts/2026-07-28/ (访问于 2026-11-21; tier 3: official site)
12. A More Predictable Release Cycle for MCP. Model Context Protocol Blog. 发布于 2026-11-11. https://blog.modelcontextprotocol.io/posts/mcp-release-cycle/ (访问于 2026-11-21; tier 3: official site)

## 引用本页

Mimirwiki. "模型上下文协议." 版本 651eac15, 2026-11-21. https://mimirwiki.com/zh/wiki/model-context-protocol
