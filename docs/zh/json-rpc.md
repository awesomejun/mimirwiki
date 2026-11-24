---
title: "JSON-RPC"
subtitle: "采用 JSON 编码的无状态、传输无关远程过程调用协议"
canonical_url: https://mimirwiki.com/zh/wiki/json-rpc
language: zh
page_class: anchor
revision_sha256: 623fa58c120b07bfceab55a810d3c3a1c3f206d0fcf0b5a333eb0c63bedfa8fa
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/json-rpc.md
  txt: https://mimirwiki.com/zh/wiki/json-rpc.txt
  json: https://mimirwiki.com/zh/wiki/json-rpc.json
  jsonld: https://mimirwiki.com/zh/wiki/json-rpc.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-rpc
  ko: https://mimirwiki.com/ko/wiki/json-rpc
  ja: https://mimirwiki.com/ja/wiki/json-rpc
---

# JSON-RPC

> JSON-RPC 是一种无状态、轻量级的远程过程调用（RPC）协议，使用 JSON 对请求、响应、通知、错误和批处理调用进行编码。JSON-RPC 工作组于 2010 年发布并于 2013 年更新的 2.0 版本与传输层无关，可在 HTTP、套接字或单进程内运行，广泛应用于 MCP、LSP 和以太坊客户端的消息交换。

JSON-RPC 是一种无状态、轻量级的远程过程调用（RPC）协议，采用 JavaScript 对象表示法（JSON）对消息进行编码。JSON-RPC 工作组基于 2009-05-24 草案于 2010-03-26 发布了 2.0 版本，并于 2013-01-04 对规范文本进行了最后一次更新；截至 2026-11-23，JSON-RPC 2.0 仍是当前版本。JSON-RPC 规范定义了请求、响应、通知、错误和批处理的数据结构及其处理规则，同时将传输层的选择交由具体实现决定。JSON-RPC 被用作模型上下文协议（MCP）、语言服务器协议（LSP）、以太坊执行客户端 API 以及 Open vSwitch 数据库管理协议（OVSDB）的基础消息格式。

**别名:** JSON-RPC 2.0, JSON-RPC 1.0, JSON 远程过程调用

## 关键事实

- **当前版本:** 2.0（2010-03-26 发布，2013-01-04 更新） (截至 2026-11-23) [1]
- **首个版本:** 1.0（2005 年） [2]
- **制定者:** JSON-RPC 工作组 [1]
- **数据格式:** JSON（RFC 4627） [1]
- **传输层:** 传输无关（进程内、套接字、HTTP 或其他消息通道） [1]

## 事实摘要

- **类型:** 无状态、轻量级远程过程调用（RPC）协议 [1]
- **制定者:** JSON-RPC 工作组（JSON-RPC Working Group） [1]
- **首个版本:** JSON-RPC 1.0（2005 年） [2]
- **当前版本:** JSON-RPC 2.0（2010-03-26 发布，2013-01-04 更新） (截至 2026-11-23) [1]
- **数据格式:** JSON（4 种原始类型与 2 种结构化类型） [1]
- **JSON 标准:** RFC 8259（2017 年 12 月，取代 RFC 7159 和 RFC 4627） (截至 2026-11-23) [4]
- **传输层:** 传输无关（进程内、套接字、HTTP 或其他消息传递方式） [1]
- **消息类型:** 请求、响应、通知、错误与批处理 [1]
- **保留错误码:** -32768 至 -32000（预定义 -32700、-32600 至 -32603，服务器错误 -32000 至 -32099） [1]
- **扩展前缀:** rpc.（保留用于可选系统扩展） [1]
- **接口描述:** OpenRPC 规范（版本 1.4.x，服务发现方法 rpc.discover） (截至 2026-11-23) [10]

## JSON-RPC 概述

JSON-RPC 是一种无状态、轻量级的远程过程调用（RPC）协议，将方法调用与回复编码为 JavaScript 对象表示法（JSON）数据。[1] JSON-RPC 2.0 规范定义了一组精简的数据结构及其处理规则，使协议不依赖于任何特定的网络传输层。[1] 截至 2026-11-23，JSON-RPC 2.0 仍是 JSON-RPC 工作组维护的现行规范；该版本基于 2009-05-24 的草案于 2010-03-26 推出，并于 2013-01-04 完成了最新的文本更新。[1]

JSON-RPC 采用 JSON 类型系统，该系统包含 4 种原始类型（String、Number、Boolean 和 Null）以及 2 种结构化类型（Object 和 Array）。[1][4] JSON-RPC 2.0 文本将 RFC 4627 作为其 JSON 参考标准。[1] 2017 年 12 月，互联网工程任务组（IETF）发布 RFC 8259 以取代 RFC 7159，而 RFC 7159 此前已取代了 RFC 4627 及其最初注册的 `application/json` 媒体类型。[4] RFC 8259 使 JSON 语法与 ECMA-404 保持一致，并指出仅生成 JSON 对象或数组作为顶层文本的实现可在所有符合标准的解析器之间保持互操作性，这正契合了 JSON-RPC 使用单个对象和批处理数组的设计。[1][4]

在 JSON-RPC 2.0 中，客户端是发起请求对象并处理响应对象的一方，服务器则是处理请求对象并生成响应对象的一方。[1] 单个实现可以针对不同对端或同一对端同时承担这两种角色，而双向会话协调则由规范交予更高层处理。[1] 客户端与服务器之间匹配的所有成员名称均区分大小写，且规范将函数（function）、方法（method）与过程（procedure）视为同义术语。[1]

## JSON-RPC 2.0 消息结构

JSON-RPC 2.0 定义了三种核心消息形式：请求对象（Request）、通知（Notification）和响应对象（Response）。[1] 每个符合规范的请求对象和响应对象都包含一个 `jsonrpc` 成员，其字符串值必须严格为 `"2.0"`。[1]

JSON-RPC 2.0 请求对象用于调用远程方法，最多包含四个成员。[1]

- `jsonrpc`：必填字符串，用于指定协议版本，必须始终为 `"2.0"`。
- `method`：必填字符串，用于指定要调用的过程名称。以 `rpc.`（字母 `rpc` 后跟英文句点 U+002E）开头的方法名保留用于 RPC 内部方法及可选系统扩展。
- `params`：可选结构化值，用于承载调用参数。若包含该成员，参数可通过按服务器预期顺序排列的 JSON 数组按位置传递，或通过成员名称与服务器预期参数名严格区分大小写匹配的 JSON 对象按名称传递。
- `id`：由客户端确定的可选标识符，若存在则必须为字符串、数字或 Null。规范不建议使用 Null 作为请求 `id`，因为无法识别 `id` 时的响应会使用 Null，且 JSON-RPC 1.0 曾用 Null `id` 表示通知；同时，由于二进制浮点格式无法精确表示许多十进制小数，数值型 `id` 也不应包含小数部分。

JSON-RPC 2.0 通知是指省略了 `id` 成员的请求对象。[1] 省略 `id` 表示客户端不期望收到回复，服务器不得针对通知返回响应对象，即使该通知位于批处理数组中也是如此。[1] 由于不会返回任何响应，通知无法得到确认；若通知触发参数无效或内部错误等异常，客户端也不会收到错误报告。[1]

对于除通知以外的每一个请求对象，JSON-RPC 2.0 服务器都必须回复单个 JSON 响应对象。[1] 响应对象始终包含 `"jsonrpc": "2.0"` 以及与请求对象 `id` 匹配的 `id` 成员；若服务器因解析错误或无效请求而无法确定 `id`，则将 `id` 设为 Null。[1] 每个响应对象在成功时必须包含 `result` 成员，在失败时必须包含 `error` 成员，且两个成员不得同时出现在同一个响应对象中。[1]

## JSON-RPC 2.0 错误对象与保留错误码

JSON-RPC 2.0 通过放置在响应对象 `error` 成员中的结构化错误对象来报告方法调用失败。[1] 错误对象包含两个必填成员和一个可选成员：`code`（用于标识错误类型的整数）、`message`（简短的字符串说明，建议限制为一句简洁的话）以及可选的 `data` 成员（承载由服务器定义的任意原始值或结构化值，用于提供附加错误信息）。[1]

JSON-RPC 2.0 将 -32768 至 -32000（含两端）的整数范围保留用于预定义协议错误，其错误码与 XML-RPC 故障码高度一致。[1] 该范围内未分配的错误码保留供将来使用，而 -32768 至 -32000 范围之外的整数则可供应用程序自定义错误使用。[1]

| 错误码 | 消息 | 含义 |
| --- | --- | --- |
| -32700 | Parse error | 服务器收到无效的 JSON，或在解析 JSON 文本时发生错误。 |
| -32600 | Invalid Request | 发送的 JSON 不是有效的请求对象。 |
| -32601 | Method not found | 请求的方法不存在或不可用。 |
| -32602 | Invalid params | 方法参数无效。 |
| -32603 | Internal error | 发生 JSON-RPC 内部错误。 |
| -32000 至 -32099 | Server error | 保留用于由实现定义的服务器错误。 |

下游协议在保持保留范围不变的基础上扩展了这一错误体系。[7] 在语言服务器协议（LSP）3.17 规范中，保留了五个核心 JSON-RPC 错误码（-32700 以及 -32600 至 -32603），将 -32099 至 -32000 标记为 JSON-RPC 保留范围（仅为向后兼容保留旧错误码 -32002 ServerNotInitialized 与 -32001 UnknownErrorCode），并在自 -32899 起的独立范围内定义了 -32803（RequestFailed）和 -32802（ServerCancelled）等协议特定错误。[7]

## JSON-RPC 批处理与传输无关性

JSON-RPC 2.0 允许客户端将多个请求对象放入单个 JSON 数组中一并发送，这种方式称为批处理（Batch）。[1] 服务器处理完批处理中的所有请求后，返回一个 JSON 数组，其中为每个非通知类请求对象包含一个对应的响应对象。[1] 服务器可以按任意顺序并发执行批处理中的请求，也可以按任意顺序返回响应对象，因此客户端需通过每个对象的 `id` 成员将响应与请求进行匹配。[1]

JSON-RPC 2.0 对批处理中的错误与通知边界情况制定了明确规则。[1] 如果批处理负载为无效 JSON 或空数组（`[]`），服务器将返回单个响应对象，其中包含错误码 -32700（Parse error）或 -32600（Invalid Request）及 `"id": null`。[1] 如果非空数组包含无效元素，服务器返回的响应数组中会同时包含有效条目的正常响应以及每个无效条目对应的 Invalid Request（-32600）错误对象。[1] 如果批处理中的所有条目均为通知，服务器不得返回空数组，而应不返回任何内容。[1]

JSON-RPC 2.0 将消息分帧与传输层绑定排除在核心规范之外，使相同的 JSON 结构能够在同一进程内、套接字、HTTP 或其他消息传递环境中运行。[1] 在协议早期发展阶段，Jeffrey Damick 与 JSON-RPC 工作组于 2008-01-15 发布了面向 JSON-RPC 1.2 的历史性扩展草案“JSON-RPC over HTTP”。[3] 该草案将 HTTP POST 指定为首选方法，并描述了使用 Base64 编码与 URL 编码参数的 HTTP GET（同时指出较旧的客户端和代理可能在 URI 长度超过 255 字节时失败）；它规定 `Content-Type` 和 `Accept` 标头应为 `application/json-rpc`（允许使用 `application/json` 或 `application/jsonrequest`），要求提供 `Content-Length`，并将处理结果映射为相应的 HTTP 状态码：成功请求返回 200，通知返回 204，-32600 返回 400，-32601 返回 404，-32700、-32602、-32603 以及服务器错误（-32099 至 -32000）返回 500。[3] 采用 JSON-RPC 2.0 的各协议会自行定义传输约定：LSP 使用类似 HTTP 的 ASCII `Content-Length` 标头和可选的 `Content-Type` 标头（默认为 `application/vscode-jsonrpc; charset=utf-8`），并以 `\r\n\r\n` 分隔 UTF-8 编码的 JSON-RPC 2.0 负载；以太坊执行节点则通常接受带有 `Content-Type: application/json` 的 HTTP POST 请求。[7][8]

## JSON-RPC 版本演进：从 1.0 到 2.0

JSON-RPC 1.0 于 2005 年发布，最初是一种对等（peer-to-peer）远程过程调用协议，相互连接的两个对等端可通过字节流（推荐使用 TCP/IP 套接字）或多次 HTTP POST 请求彼此调用方法。[2] JSON-RPC 1.0 请求对象包含三个属性：`method`、`params`（严格限定为位置数组）以及 `id`（任意 JSON 类型）。[2] 通知使用值为 `null` 的 `id`，而响应对象始终同时包含 `result` 和 `error` 属性，并将未使用的属性设为 `null`。[2] 1.0 版本还包含用于类提示（class hinting）的 `__jsonclass__` 属性，以便对等端实例化超出标准 JSON 类型的带类型对象。[2]

基于 2009-05-24 草案于 2010-03-26 推出并在 2013-01-04 更新的 JSON-RPC 2.0，将协议简化为无状态的客户端-服务器消息规范，并引入了破坏与 1.0 版本线路兼容性的变更。[1] 由于每个 JSON-RPC 2.0 请求和响应对象都带有 `"jsonrpc": "2.0"`，而 1.0 版本对象省略了该成员，各实现可以轻松区分两个版本。[1]

| 特性 | JSON-RPC 1.0（2005 年） | JSON-RPC 2.0（2010 年，2013 年更新） |
| --- | --- | --- |
| 版本标识符 | 省略 | 必填 `"jsonrpc": "2.0"` 成员 |
| 参数（`params`） | 仅限数组（按位置） | 可选数组（按位置）或对象（按名称） |
| 通知格式 | `"id": null` | 省略 `id` 成员 |
| 响应 `result` 与 `error` | 两者均存在，未使用字段设为 `null` | 互斥，仅允许存在其一 |
| 批处理请求 | 未定义 | 请求对象组成的 JSON 数组 |
| 类提示（`__jsonclass__`） | 规范中定义 | 从规范中移除 |
| 通信模型 | 基于流或 HTTP 的对等通信 | 无状态客户端与服务器角色，传输无关 |

JSON-RPC 2.0 建议各实现在切实可行的情况下考虑处理 1.0 版本对象，即使不支持 1.0 版本的对等通信与类提示特性也是如此。[1] 在 2.0 版本发布后，JSON-RPC 1.0 仍继续出现在网络规范中：2013 年 12 月，IETF 发布了信息性文档 RFC 7047，定义了 Open vSwitch 数据库管理协议（OVSDB），该协议以基于 JSON 的 JSON-RPC 1.0 作为线路协议，用于配置虚拟交换机的网桥、端口、隧道接口、队列和服务质量（QoS）策略。[5]

## JSON-RPC 生态应用与 OpenRPC 工具

JSON-RPC 2.0 被用作多项主流开发者工具、AI 及区块链协议的消息层。[6][7][8] [模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP，截至 2026-11-23 最新规范版本为 2026-07-28）使用 JSON-RPC 2.0 消息连接 LLM 宿主应用程序、内部客户端以及暴露资源、提示词、工具和客户端信息征集（elicitation）流程的服务器。[6] MCP 受到微软维护的语言服务器协议（LSP，截至 2026-11-23，规范 3.17 已归档，3.18 列为当前版本，3.19 列为即将发布版本）的启发，而 LSP 同样在代码编辑器与语言服务器之间通过 JSON-RPC 2.0 消息传输补全、诊断、格式化和符号导航等操作。[6][7]

JSON-RPC 2.0 同时也是以太坊执行节点的标准客户端接口。[8][9] 每个以太坊执行客户端都暴露统一的 JSON-RPC API，使软件应用能够在可互换的节点实现之间查询区块链状态、获取历史区块和交易收据以及提交交易。[8][9] 以太坊文档将核心方法划分为三类：广播类（`eth_blockNumber`、`eth_sendRawTransaction`）、状态类（`eth_getBalance`、`eth_getStorageAt`、`eth_getTransactionCount`、`eth_getCode`、`eth_call`、`eth_estimateGas`）和历史类（`eth_getBlockByNumber`、`eth_getTransactionReceipt`），其中整数数量编码为紧凑的 `"0x"` 前缀十六进制字符串（零表示为 `"0x0"`），未格式化字节数组编码为偶数长度的 `"0x"` 前缀十六进制字符串。[8] 以太坊执行 API 的权威规范以 CC0-1.0 许可维护于 GitHub 上的 `ethereum/execution-apis` 仓库中，并通过 `speccheck` 以及 `hive` 模拟器的 `rpc-compat` 测试套件针对各客户端进行验证。[9] 以太坊共识客户端则另行暴露 Beacon API，而共识客户端与执行客户端之间通过 Engine API 交换节点内部消息。[8]

为以机器可读形式描述和验证 JSON-RPC 2.0 接口，OpenRPC 规范（截至 2026-11-23 版本为 1.4.x，采用 Apache-2.0 许可）专门面向 JSON-RPC 2.0 API 定义了一种与语言无关的 JSON 接口描述格式。[10] OpenRPC 文档惯例命名为 `openrpc.json`，要求包含 `openrpc`、`info` 和 `methods` 字段，使用 Draft 07 JSON Schema 定义参数与结果，并在描述字段中支持 GitHub Flavored [Markdown](https://mimirwiki.com/zh/wiki/markdown)。[10] OpenRPC 还利用 JSON-RPC 2.0 保留的 `rpc.` 扩展前缀定义了服务发现方法 `rpc.discover`，以便在运行时返回 API 的 OpenRPC 模式。[1][10] 包括 `ethereum/execution-apis` 在内的项目采用 OpenRPC YAML 文件编写其 JSON-RPC 方法，并将其编译为经过验证的 `openrpc.json` 文档。[9]

## 常见问题

### 什么是 JSON-RPC？

JSON-RPC 是一种无状态、轻量级的远程过程调用（RPC）协议，使用 JSON 对请求、响应、通知和错误对象进行编码。2.0 版本由 JSON-RPC 工作组于 2010-03-26 发布，并于 2013-01-04 进行了最后一次更新。 [1]

### JSON-RPC 2.0 通知与常规请求有何区别？

JSON-RPC 2.0 请求包含一个 id 成员，以便服务器将响应对象与对应调用进行匹配。通知则省略了 id 成员，服务器不得对其返回任何响应，即使该通知包含在批处理请求中也是如此。 [1]

### JSON-RPC 2.0 中有哪些保留错误码？

JSON-RPC 2.0 将 -32768 至 -32000 的整数错误码保留用于预定义协议错误。具体而言，-32700 为 Parse error（解析错误），-32600 为 Invalid Request（无效请求），-32601 为 Method not found（未找到方法），-32602 为 Invalid params（无效参数），-32603 为 Internal error（内部错误），而 -32000 至 -32099 保留用于由实现定义的服务器错误。 [1]

### JSON-RPC 2.0 是否必须使用 HTTP 作为传输协议？

不需要。JSON-RPC 2.0 与传输层无关，仅定义 JSON 数据结构与处理规则，因此各实现可在 HTTP、套接字、同一进程内或其他消息传递通道上运行。 [1]

### JSON-RPC 1.0 与 JSON-RPC 2.0 之间有哪些变化？

JSON-RPC 2.0 新增了必填的 "jsonrpc": "2.0" 版本字段、基于 JSON 对象的命名参数、批处理请求数组，以及互斥的 result 与 error 响应字段。此外，它还将通知的表示方式从 "id": null 改为省略 id，并移除了 1.0 版本的 __jsonclass__ 类提示机制。 [1][2]

### 哪些主要协议和规范使用了 JSON-RPC？

模型上下文协议（MCP）、语言服务器协议（LSP）以及以太坊执行客户端 API 使用 JSON-RPC 2.0，而 Open vSwitch 数据库管理协议（RFC 7047）使用 JSON-RPC 1.0。OpenRPC 则专门为 JSON-RPC 2.0 API 定义了标准的机器可读接口描述格式。 [5][6][7][8][10]

## 可引用的句子

- JSON-RPC 2.0 基于 2009-05-24 草案于 2010-03-26 发布，其有记录的最新更新时间为 2013-01-04。 [1]
- 每个 JSON-RPC 2.0 请求对象和响应对象都必须包含一个 "jsonrpc" 成员，且其字符串值必须严格为 "2.0"。 [1]
- JSON-RPC 2.0 响应对象必须包含 "result" 成员或 "error" 成员之一，且不得同时包含两者。 [1]
- JSON-RPC 2.0 将整数错误码 -32768 至 -32000 保留用于预定义协议错误，其中 -32000 至 -32099 指定用于由具体实现定义的服务器错误。 [1]
- 在 JSON-RPC 2.0 中，以 "rpc." 开头的方法名保留用于可选系统扩展，例如 OpenRPC 的服务发现方法 "rpc.discover"。 [1][10]
- IETF 于 2017 年 12 月发布 RFC 8259 以标准化 JSON 数据交换格式，取代了 RFC 7159 和 RFC 4627。 [4]
- 模型上下文协议（版本 2026-07-28）和语言服务器协议（版本 3.17）均以 JSON-RPC 2.0 作为基础消息格式。 [6][7]
- 以太坊执行客户端实现了在采用 CC0-1.0 许可的 ethereum/execution-apis 仓库中以 OpenRPC 格式定义的标准 JSON-RPC 2.0 API。 [8][9]

## 时间线

- 2005: JSON-RPC.ORG 发布 JSON-RPC 1.0 规范，支持基于流连接与 HTTP 的对等远程过程调用。 [2]
- 2008-01-15: Jeffrey Damick 与 JSON-RPC 工作组起草面向 1.2 版本的历史性扩展草案 JSON-RPC over HTTP。 [3]
- 2009-05-24: JSON-RPC 工作组形成后来用于构建 JSON-RPC 2.0 的基础草案版本。 [1]
- 2010-03-26: JSON-RPC 工作组发布 JSON-RPC 2.0 规范。 [1]
- 2013-01-04: JSON-RPC 工作组发布 JSON-RPC 2.0 规范文本有记录的最后一次更新。 [1]
- 2013-12: IETF 发布信息性 RFC 7047，基于 JSON-RPC 1.0 定义了 Open vSwitch 数据库管理协议（OVSDB）。 [5]
- 2017-12: IETF 发布 RFC 8259，取代 RFC 7159 和 RFC 4627 成为标准跟踪（Standards Track）JSON 规范。 [4]
- 2026-07-28: 模型上下文协议项目发布采用 JSON-RPC 2.0 消息的 2026-07-28 版规范。 [6]

## 来源

1. JSON-RPC 2.0 Specification. JSON-RPC Working Group. 发布于 2010-03-26. https://www.jsonrpc.org/specification (访问于 2026-11-23; tier 3: official site)
2. JSON-RPC 1.0 Specification (2005). JSON-RPC Working Group. 发布于 2005. https://www.jsonrpc.org/specification_v1 (访问于 2026-11-23; tier 3: official site)
3. JSON-RPC over HTTP. JSON-RPC Working Group. 发布于 2008-01-15. https://www.jsonrpc.org/historical/json-rpc-over-http.html (访问于 2026-11-23; tier 3: official site)
4. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 发布于 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (访问于 2026-11-23; tier 1: government or public registry)
5. RFC 7047: The Open vSwitch Database Management Protocol. Internet Engineering Task Force (IETF). 发布于 2013-12. https://www.rfc-editor.org/rfc/rfc7047.txt (访问于 2026-11-23; tier 1: government or public registry)
6. Specification - Model Context Protocol. Model Context Protocol project. 发布于 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28 (访问于 2026-11-23; tier 3: official site)
7. Language Server Protocol Specification - 3.17. Microsoft (LSP). https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/ (访问于 2026-11-23; tier 3: official site)
8. JSON-RPC API | ethereum.org. ethereum.org. https://ethereum.org/developers/docs/apis/json-rpc/ (访问于 2026-11-23; tier 3: official site)
9. GitHub - ethereum/execution-apis: Collection of APIs provided by Ethereum execution layer clients · GitHub. Ethereum (GitHub). https://github.com/ethereum/execution-apis (访问于 2026-11-23; tier 3: official site)
10. OpenRPC Specification | spec. OpenRPC. https://spec.open-rpc.org/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "JSON-RPC." 版本 623fa58c, 2026-11-23. https://mimirwiki.com/zh/wiki/json-rpc
