---
title: "Cloudflare Workers"
subtitle: "由 Cloudflare 推出的无服务器执行平台，通过 V8 隔离实例与 workerd 运行时运行 JavaScript、TypeScript、Python、Rust 和 WebAssembly"
canonical_url: https://mimirwiki.com/zh/wiki/cloudflare-workers
language: zh
page_class: entity
revision_sha256: 4332636d1fb2f82d523849181e5cade056bd516f0a2403a949f6b1a5be5766d0
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/cloudflare-workers.md
  txt: https://mimirwiki.com/zh/wiki/cloudflare-workers.txt
  json: https://mimirwiki.com/zh/wiki/cloudflare-workers.json
  jsonld: https://mimirwiki.com/zh/wiki/cloudflare-workers.jsonld
translations:
  en: https://mimirwiki.com/wiki/cloudflare-workers
  ko: https://mimirwiki.com/ko/wiki/cloudflare-workers
  ja: https://mimirwiki.com/ja/wiki/cloudflare-workers
  es: https://mimirwiki.com/es/wiki/cloudflare-workers
---

# Cloudflare Workers

> Cloudflare Workers 是由 Cloudflare 运营的无服务器计算平台，通过 V8 隔离实例和 workerd 运行时在其全球网络上执行 JavaScript、TypeScript、Python、Rust 和 WebAssembly 代码。该平台于 2017 年发布，提供 Web 标准 API、Node.js 兼容性及存储绑定。截至 2026-11-23，Cloudflare 提供 Workers Free 方案及每月最低 5 美元的 Workers Paid 方案。

Cloudflare Workers 是由 Cloudflare, Inc. 运营的无服务器计算平台，利用 V8 隔离实例（isolate）和开源 workerd 运行时在 Cloudflare 全球网络上执行开发者应用程序。该平台于 2017 年 9 月 29 日发布，依托 Web 平台 API 与原生实现的 Node.js API 子集运行 JavaScript、TypeScript、Python、Rust 及 WebAssembly（Wasm）工作负载。Cloudflare 于 2022 年 9 月 27 日以 Apache-2.0 许可证开源了驱动 Cloudflare Workers 的 JavaScript 与 WebAssembly 服务器运行时 workerd。截至 2026-11-23，Cloudflare 提供每日上限为 100,000 次请求的 Workers Free 方案，以及采用 Standard 用量模式、每月最低 $5 USD 且不收取数据出站或带宽费用的 Workers Paid 方案。

**别名:** Workers, CF Workers, workerd

## 关键事实

- **开发者:** Cloudflare, Inc. [2]
- **执行模型:** 部署于 Cloudflare 全球网络的 V8 隔离实例 [6]
- **开源运行时:** workerd（Apache-2.0 许可证） [10]
- **Workers Free 限额:** 每日 100,000 次请求，每次调用 10 ms CPU 时间 (截至 2026-11-23) [4]
- **Workers Paid 定价:** 每月最低 $5 USD（含 1,000 万次请求及 3,000 万 CPU ms） (截至 2026-11-23) [4]

## 事实摘要

- **开发者:** Cloudflare, Inc.（SEC CIK 0001477333） [2]
- **首次发布日期:** 2017 年 9 月 29 日 [12]
- **执行引擎:** V8 JavaScript 引擎（隔离实例） [6]
- **开源运行时:** workerd（Apache-2.0 许可证，2022 年 9 月 27 日发布测试版） [11]
- **一级支持语言:** JavaScript、TypeScript、Python、Rust (截至 2026-11-23) [7]
- **WebAssembly 支持语言:** 包括 C、C++、Kotlin 和 Go 在内的 WebAssembly（Wasm）目标语言 (截至 2026-11-23) [7]
- **Node.js 兼容性:** 兼容性日期 2026-08-04 及之后默认启用 (截至 2026-11-23) [9]
- **Workers Free 方案:** 每日 100,000 次请求；每次调用 10 ms CPU 时间 (截至 2026-11-23) [4]
- **Workers Paid 方案:** 每月最低 $5 USD；含 1,000 万次请求及 3,000 万 CPU ms；无出站费用 (截至 2026-11-23) [4]
- **单隔离实例内存:** 128 MB（JavaScript 堆与 WebAssembly 内存分配） (截至 2026-11-23) [5]
- **Worker 体积与启动限制:** 64 MiB 未压缩包体；1 秒启动时间上限 (截至 2026-11-23) [5]
- **最大 CPU 时间（Paid）:** 每次 HTTP 请求 5 分钟（默认 30 秒）；间隔 1 小时及以上的 Cron Triggers 为 15 分钟 (截至 2026-11-23) [5]

## Cloudflare Workers 的 V8 隔离实例架构与 workerd 运行时

Cloudflare Workers 在 [Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 遍布全球的分布式服务器网络上通过 V8 JavaScript 引擎执行用户应用程序。[6] 每台服务器运行多个 Workers 运行时实例，每个运行时实例托管数百至数千个 V8 隔离实例（isolate），即具有独立内存沙箱的轻量级执行上下文。[6] 与基于容器的无服务器架构为每个函数启动独立的语言运行时进程或虚拟机不同，Workers 运行时在每个容器中仅初始化单个 V8 宿主进程，并在该进程内的隔离实例中运行用户脚本。[6] Cloudflare 文档指出，与容器或虚拟机中的 Node.js 进程相比，V8 隔离实例的启动速度快约一百倍，启动时的内存消耗低一个数量级。[6]

路由至 `*.workers.dev` 子域名或 Cloudflare 托管域名的请求，会调用 Worker 以 ES 模块语法导出的 `fetch(request, env, ctx)` 处理函数并接收 `Response` 对象。[6] 每个 Worker 实例在单线程事件循环上处理请求，包括等待异步 I/O 的并发请求。[6] 当宿主机资源紧张、Worker 触及资源限制或代码表现出可疑的沙箱逃逸行为时，隔离实例可能会被驱逐（evict）。[6] 由于无法保证任意两个请求会到达 Worker 的同一个实例，Cloudflare 建议不要在全局作用域中存储可变状态。[6]

驱动 Cloudflare Workers 的开源服务器运行时为 `workerd`（发音为“worker-dee”），以 Apache-2.0 许可证发布于 GitHub。[10][11] 开发者可使用 `workerd` 自托管兼容 Workers 的应用程序、运行本地开发与测试环境，或部署可编程的正向或反向 HTTP 代理。[10] Cloudflare 为 `workerd` 制定了六项设计原则。[10]

- 服务器优先设计：专门面向服务器工作负载，不包含 CLI 和 GUI 环境。[10]
- 基于标准的内置 API：与 `fetch()` 等 Web 平台规范保持一致。[10]
- 纳米服务（Nanoservices）：允许独立部署的组件在同一线程和进程内相互调用。[10]
- 同构部署（Homogeneous deployment）：在集群各机器上保持一致的部署形态，以简化负载均衡。[10]
- 能力绑定（Capability bindings）：通过显式引用连接服务与外部资源，降低服务器端请求伪造（SSRF）风险。[10]
- 基于日期的向后兼容性：每个 `workerd` 版本标识对应其支持的最大兼容性日期，从而为较早的兼容性日期保留历史 API 行为。[10]

`workerd` 使用 Bazel 构建，并在 Linux 和 macOS（`x86-64` 与 `arm64`）以及 Windows（`x86-64`）上进行测试。[10] 其原生配置采用 Cap'n Proto 文本格式，同时 `workerd serve wrangler.jsonc` 也可加载经 `esbuild` 打包的 Wrangler 配置。[10] 截至 2026-11-25，`cloudflare/workerd` GitHub 仓库记录了 9.3k 个 star、846 个 fork 和 14,147 次提交。[10] Cloudflare 提醒，独立运行的 `workerd` 不适合作为抵御实现缺陷的唯一加固沙箱，运行不受信任的代码时需要外层虚拟机或沙箱，而托管型 Cloudflare Workers 服务则应用了额外的纵深防御层。[10]

## Cloudflare Workers 运行时 API、Web 标准与 Node.js 兼容性

Cloudflare Workers 实现了 Web 平台 API，使应用代码能够在浏览器和服务器运行时之间遵循 JavaScript Web 标准。[8] 其内置运行时 API 涵盖 Fetch、Request、Response、Headers、Cache、Streams（`ReadableStream`、`WritableStream` 和 `TransformStream`）、Web Crypto、WebSockets、TCP 套接字、Encoding、EventSource、MessageChannel、Performance 与定时器、Scheduler、HTMLRewriter、远程过程调用（RPC）、Context（`ctx`）、Bindings（`env`），以及覆盖 Fetch、Scheduled、Queue、Email、Alarm、Tail 和 Connect 事件的事件处理程序。[8]

Cloudflare 运行时 API 文档指出，Workers 复用 Web 平台 API 以实现 WinterCG JavaScript 运行时之间的互操作性。[8] 在更广泛的标准生态中，被称为 WinterTC（Web 可互操作服务器运行时技术委员会，Technical Committee on Web-interoperable Server Runtimes）的 Ecma International 第 55 技术委员会负责为服务器端 JavaScript 运行时制定与 Web 共享的最小公共 API 标准，与 WHATWG 和 W3C 就 Web API 规范展开协作，并发布可互操作服务器端 API 的标准。[1]

为了运行依赖 Node.js 库的 npm 软件包，Cloudflare Workers 通过两种机制提供 Node.js API 子集：面向 Node.js Current 发布版本的原生内置实现，以及由 Wrangler 通过 `unenv` 注入的 polyfill 垫片（其中未实现的方法会执行空操作或抛出错误）。[9] 运行时行为由 Worker 的兼容性日期和兼容性标志控制。[8][9] 对于 2026-08-04 及之后的兼容性日期，Cloudflare Workers 默认同时启用 `nodejs_compat` 和 `nodejs_compat_v2`，选择停用的项目需添加 `no_nodejs_compat` 和 `no_nodejs_compat_v2`。[9] 2024-09-23 至 2026-08-03 之间的兼容性日期可通过 `nodejs_compat` 标志选择启用，该标志同时开启自动 `unenv` polyfill 注入；若仅需 `AsyncLocalStorage`，则可单独使用 `nodejs_als` 标志。[9]

截至 2026-11-23，Cloudflare 文档列出的 Node.js 运行时兼容性覆盖范围如下。[9]

- 原生支持模块：`assert`、`AsyncLocalStorage`、`Buffer`、`crypto`、Debugger（通过 Chrome DevTools 集成）、Diagnostics Channel、Errors、`EventEmitter`、`fs`、Globals、`http`、`https`、`net`、`path`、`process`、Punycode（已弃用）、Query strings、`stream`、`StringDecoder`、`timers`、`url`、`util`、Web Crypto API、Web Streams API 和 `zlib`。[9]
- 部分支持模块：Console、`dns`、Module、OS、Performance hooks、Test runner 和 `tls`（TLS/SSL）。[9]
- 按兼容性日期随 `nodejs_compat` 启用的仅导入非功能性存根（stub）模块：`node:http2`（2025-09-01）；`node:vm`（2025-10-01）；`node:cluster`、`node:domain`、`node:trace_events` 和 `node:wasi`（2025-12-04）；`node:_stream_wrap`、`node:dgram`、`node:inspector` 和 `node:sqlite`（2026-01-29）；以及 `node:child_process`、`node:readline`、`node:repl`、`node:tty`、`node:v8` 和 `node:worker_threads`（2026-03-17）。[9]

## Cloudflare Workers 支持语言、开发工具与平台绑定

Cloudflare Workers 支持多种编程语言、本地开发工具、Web 框架以及与 Cloudflare 平台服务的直接绑定。[3][7] 截至 2026-11-23，该平台列出四种一级支持语言：JavaScript、TypeScript、Python（通过 Python Workers）和 Rust（在文档导航中标注为 Beta）。[3][7] 借助 WebAssembly（Wasm）二进制支持，开发者还可部署使用可编译为 Wasm 的语言（包括 C、C++、Kotlin 和 Go）编写的 Worker。[7]

开发者使用 Wrangler CLI、Cloudflare Vite Plugin、Miniflare、Vitest 集成以及通过 Workers Builds（支持 GitHub 和 GitLab 集成）实现的内置 CI/CD，或 GitHub Actions、GitLab CI/CD 等外部流水线来构建、测试和部署 Worker。[3] Cloudflare 发布了面向多种 Web 和 API 框架的指南，涵盖 React、Vue、SvelteKit、Next.js（使用 OpenNext 适配器）、Astro、React Router、Remix 3、Nuxt、Angular、Hono、TanStack Start、Qwik、Solid、FastAPI 和 Flask。[3] 静态前端资源可通过 Cloudflare 的[内容分发网络](https://mimirwiki.com/zh/wiki/content-delivery-network)与缓存随 Worker 逻辑一并直接提供服务，Smart Placement 则面向外部数据存储优化后端请求路由。[3] 截至 2026-11-23，Cloudflare Workers 文档还发布了 [llms.txt](https://mimirwiki.com/zh/wiki/llms-txt) 索引、`llms-full.txt`、逐页 [Markdown](https://mimirwiki.com/zh/wiki/markdown) 视图，以及指向 Cloudflare [Model Context Protocol](https://mimirwiki.com/zh/wiki/model-context-protocol) 服务器的链接。[3]

在 Cloudflare 提交至 [SEC EDGAR](https://mimirwiki.com/zh/wiki/sec-edgar) 的 2025 财年申报文件中，Cloudflare 将 Cloudflare Workers、Cloudflare Workers for Platforms（供平台客户运行终端用户代码的多租户托管执行环境）和 Cloudflare Pages 归类为其计算（Compute）开发者解决方案。[2] Workers 通过显式 `env` 绑定连接存储、计算、AI 和媒体服务。[2][3]

- 存储与数据库：Durable Objects（有状态实时协调）、D1（无服务器 SQL 数据库）、Workers KV（支持边缘缓存读取的全球分布式键值存储）、Queues（无出站费用的异步消息队列）、Hyperdrive（面向外部数据库的连接池、路由优化与查询缓存）以及 R2（无出站费用的对象存储）。[2][3]
- 计算与 AI：Workers AI（无服务器 GPU 上的机器学习推理）、Workflows（支持自动重试的持久化多步骤执行）、Vectorize（用于嵌入向量与语义搜索的向量数据库）、Browser Run（可编程无服务器浏览器实例）、Service 绑定（Worker 之间的 HTTP 与 `WorkerEntrypoint` RPC 调用）、Dynamic Worker Loaders 以及 Workers for Platforms Dispatcher。[2][3]
- 媒体与运维绑定：Cache、Images、Stream、Media Transformations、Assets、Analytics Engine、Rate Limiting、Secrets、Secrets Store（Beta）、mTLS 证书和环境变量。[3]

## Cloudflare Workers 方案与定价

Cloudflare Workers 提供 Workers Free 方案、每月最低 $5 USD 的 Workers Paid 方案以及基于合同的 Workers Enterprise 账户。[4] 账户默认使用 Workers Free，包含 Workers、Pages Functions、Workers KV 和 Hyperdrive 的每日用量额度。[4] Workers Paid 采用 Standard 用量模式，提供覆盖 Workers、Pages Functions、Workers KV、Hyperdrive 和 Durable Objects 的月度额度，且不对数据传输（出站）或带宽收取额外费用。[4] 所有 Pages Functions 均遵循与 Workers 相同的计费规则。[4] 部分较早的配置仍保留旧版用量模式（Workers Unbound 和 Workers Bundled），Cloudflare 已于 2024 年 3 月 1 日将 Bundled Workers 迁移至 Standard 定价模式，并自动应用 50 毫秒 CPU 时间上限。[4]

截至 2026-11-23，Cloudflare 公布的 Free 和 Paid（Standard）层级 Workers 计算定价如下。[4]

| 指标 | Workers Free | Workers Paid（Standard） |
| --- | --- | --- |
| 基础订阅费 | $0 | 每月最低 $5 USD |
| 入站请求 | 每日 100,000 次 | 每月含 1,000 万次，超出后每百万次 $0.30 |
| 持续时间（挂钟时间） | 不收费 | 不收费且无限制 |
| CPU 时间 | 每次调用 10 ms | 每月含 3,000 万 CPU ms，超出后每百万 CPU ms $0.02 |
| 每次调用最大 CPU 时间 | 10 ms | HTTP 5 分钟（默认 30 秒）；间隔 1 小时及以上的 Cron Triggers 15 分钟 |
| 静态资源请求 | 免费且不限量 | 免费且不限量 |

Cloudflare 不对 Worker 发起的出站子请求计费。[4] WebSocket 连接在初始 Upgrade 握手时计为单次请求，后续路由的消息不收取按消息计费的请求费用。[4] 启用 Workers Caching 时，缓存命中按每次请求费率计费（包括静态资源及 Worker 间调用），而 CPU 时间仅在缓存未命中或绕过缓存导致 Worker 执行时计费。[4] 账户所有者可设置 Workers 支出上限，在超出免费额度后的请求与 CPU 费用（不含 $5 订阅费）达到设定阈值时阻止新调用，也可配置不阻止执行的电子邮件告警。[4]

Cloudflare 的 Workers 定价页面还列出了截至 2026-11-23 的相关开发者服务额度与超额费率。[4]

| 服务与指标 | Workers Free | Workers Paid |
| --- | --- | --- |
| Workers Logs 写入事件 | 每日 200,000 条（保留 3 天） | 每月含 2,000 万条，超出后每百万条 $0.60（保留 7 天） |
| Workers Trace Events Logpush | 不可用 | 每月含 1,000 万次请求，超出后每百万次 $0.05 |
| Workers KV 键读取 | 每日 100,000 次 | 每月含 1,000 万次，超出后每百万次 $0.50 |
| Workers KV 键写入、删除或列举 | 各项每日 1,000 次 | 各项每月含 100 万次，超出后各项每百万次 $5.00 |
| Workers KV 存储与命名空间 | 1 GB；1,000 个命名空间 | 1 GB（+$0.50/GB-月）；含前 1,000 个命名空间（每增加 1 个 +$0.10/月） |
| Hyperdrive 数据库查询 | 每日 100,000 次 | 不限量 |
| Queues 标准操作（每 64 KB 消息分块） | 每日 10,000 次（保留 24 小时；10,000 个队列） | 每月 100 万次（+$0.40/百万次；默认保留 4 天，最长 14 天；含前 10,000 个队列，每增加 1 个 +$0.10/月） |
| Workflows 步骤与存储 | 每日 3,000 步；1 GB-月（请求与 Workers 共享） | 每月 500,000 步（每 100,000 步 +$0.80）；1 GB-月（+$0.20/GB-月） |
| D1 读取行数 | 每日 500 万行 | 每月含 250 亿行，超出后每百万行 $0.001 |
| D1 写入行数 | 每日 100,000 行 | 每月含 5,000 万行，超出后每百万行 $1.00 |
| D1 存储与数据库 | 总计 5 GB；10 个数据库 | 5 GB（+$0.75/GB-月）；100,000 个数据库（每增加 1 个 +$0.10/月） |

Cloudflare 说明，Workers Logs 将自 2026 年 12 月 1 日起过渡至 Cloudflare Observability 定价体系，而 Workflows 步骤与存储计费将自 Workflows 计费变更日志公布的日期起生效。[4] Queues 按每条消息的 64 KB 分块计量操作（1 KB 定义为 1,000 字节，含约 100 字节内部元数据），因此典型消息投递消耗三次操作（写入、读取和删除），且无出站费用。[4]

## Cloudflare Workers 运维与资源限制

Cloudflare Workers 在 Workers Free 和 Workers Paid 方案中均实施账户、执行、网络及部署限制。[5] 截至 2026-11-23，Cloudflare 列出的核心账户与平台限制如下。[5]

| 限制项 | Workers Free | Workers Paid |
| --- | --- | --- |
| 每日请求数 | 每日 100,000 次（00:00 UTC 重置） | 无限制 |
| 每次 HTTP 请求 CPU 时间 | 10 ms | 5 分钟（默认 30 秒） |
| 每次 Cron Trigger CPU 时间 | 10 ms | 5 分钟（间隔不足 1 小时）；15 分钟（间隔 1 小时及以上） |
| 单隔离实例内存 | 128 MB | 128 MB |
| 每次调用子请求数 | 50 次（内部服务 1,000 次） | 10,000 次（最高可配置至 1,000 万次） |
| 同时等待响应头的出站连接数 | 6 | 6 |
| 每个 Worker 的环境变量（机密与文本） | 64 个（每个 5 KB） | 128 个（每个 5 KB） |
| Worker 包体大小（未压缩） | 64 MiB | 64 MiB |
| Worker 启动时间（全局作用域） | 1 秒 | 1 秒 |
| 每个账户的 Worker 数量 | 100 | 500 |
| 版本保留期 | 30 天（保留最近 100 个版本） | 30 天（保留最近 100 个版本） |
| 每个账户的 Cron Triggers 数量 | 5 | 1,000 |
| 每个 Worker 版本的静态资源文件数 | 20,000 个（单文件 25 MiB） | 100,000 个（单文件 25 MiB） |

CPU 时间仅计算脚本主动执行时间，不包括等待 `fetch()`、KV 读取或数据库查询等网络 I/O 的时间。[5] Cloudflare 报告称，普通 Worker 每次请求平均消耗约 2.2 ms 的 CPU 时间，而处理身份验证、服务器端渲染或大型负载解析等较重工作负载通常消耗 10-20 ms。[5] 超出 Workers Free 每日请求上限将触发 Error 1027（路由可配置为 fail open 以绕过 Worker，或配置为 fail closed 以返回错误页面）。[5] 超出 CPU 或内存限制将返回 Error 1102（在分析与 Logpush 中记录为 `exceededCpu` 或 `exceededMemory`），超出 1 秒全局作用域启动上限则会导致部署被拒绝并返回错误代码 10021。[5]

128 MB 内存上限同时覆盖整个隔离实例的 JavaScript 堆和 WebAssembly 分配，单个隔离实例可能同时处理多个并发请求。[5] 当隔离实例超过 128 MB 时，运行时会允许正在处理的请求完成，并将新请求路由至新的隔离实例，仅在极端负载下才会取消传入请求。[5] 在客户端保持连接期间，HTTP 触发的 Worker 没有硬性挂钟持续时间上限，且 `ctx.waitUntil()` 可在响应完成或客户端断开连接后将执行延长最多 30 秒；Cron Triggers、Durable Object Alarms 和 Queue Consumers 的挂钟持续时间上限为 15 分钟。[5] 在常规运行时更新期间，旧版本运行时上的进程最多允许 20 分钟以平滑排空现有流式 HTTP 响应和 WebSockets。[5]

每个顶层请求（包括通过 Service 绑定调用的 Worker）在 `fetch()`、KV、Cache、R2、Queues、TCP `connect()` 和出站 WebSockets 中最多允许六个同时等待响应头的出站连接，额外连接将排队直至响应头返回。[5] 请求与响应限制将 URL 上限设为 16 KB，请求头和响应头总大小各限制为 128 KB，响应体大小不设强制上限（但受 CDN 缓存限制约束：Free、Pro 和 Business 方案为 512 MB，Enterprise 方案为 5 GB）。[5] 入站请求体上限由域名所属的 Cloudflare 方案决定：Free 和 Pro 为 100 MB，Business 为 200 MB，Enterprise 自助服务最高 5 GB（超出返回 HTTP 413），而从 Durable Objects 或 Containers 发出的出站 HTTP 请求体默认上限为 100 MiB。[5] 路由限制为每个区域（zone）1,000 条路由（`wrangler dev --remote` 或 Quick Editor 会话期间为 50 条）、每个区域 100 个自定义域名，以及每个 Worker 1,000 个路由区域。[5] 需要超过 500 个 Worker 的多租户平台可使用 Workers for Platforms，该服务支持无限数量的用户 Worker。[5]

## Cloudflare Workers 发展历程与运维披露

Cloudflare Workers 于 2017 年 9 月 29 日 Birthday Week 期间在 Cloudflare Blog 上发布，作为在 Cloudflare 网络边缘运行 JavaScript Service Workers 的方式推出。[12] 随后，该发布文章追加了一条日期为 2018 年 3 月 13 日的更新，记录了该平台的可用性。[12] 在首次发布五年后的 2022 年 9 月 27 日，Cloudflare 宣布推出 `workerd` 的首个测试版，以 Apache-2.0 开源许可证公开了驱动 Cloudflare Workers 的 JavaScript 与 WebAssembly 运行时代码。[11]

2024 年 3 月 1 日，Cloudflare 将采用旧版 Bundled 定价的账户迁移至 Standard 用量模式。[4] 自兼容性日期 2024-09-23 起，启用 `nodejs_compat` 会指示 Wrangler 自动注入 `unenv` polyfill。[9] `node:http2`、`node:vm`、`node:sqlite`、`node:child_process` 和 `node:worker_threads` 等 Node.js 模块的仅导入存根，在兼容性日期 2025-09-01 至 2026-03-17 之间的各个日期起随 `nodejs_compat` 启用；兼容性日期为 2026-08-04 或之后时，`nodejs_compat` 和 `nodejs_compat_v2` 默认启用。[9] 此外，Cloudflare 还计划于 2026 年 12 月 1 日起使 Workers Logs 采用 Cloudflare Observability 定价体系。[4]

在 [Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 提交至 [SEC EDGAR](https://mimirwiki.com/zh/wiki/sec-edgar) 的 2025 财年申报文件中，该公司表示，客户使用包括 Cloudflare Workers 在内的开发者解决方案，为其打开了存储与计算这一新市场，并表示认为自己在存储与计算工作负载上与公有云厂商的竞争日益增多。[2] 在同一份申报文件的风险披露部分，Cloudflare 报告了一起发生于 2025 年 6 月的运维事件：Workers KV 服务所使用的底层第三方存储基础设施发生故障，导致持续数小时的服务中断，影响了 Cloudflare 的部分服务与客户。[2] Cloudflare 表示，2025 年 6 月的此次中断未对其业务、经营业绩或财务状况产生重大影响。[2]

## 常见问题

### Cloudflare Workers 如何使用 V8 隔离实例执行代码？

Cloudflare Workers 在共享操作系统进程中运行 V8 JavaScript 引擎，并为每个用户应用程序分配具有隔离内存的轻量级 V8 隔离实例（isolate）。单个运行时实例可运行并切换数百至数千个隔离实例，因此每个容器只需承担一次运行时进程启动开销。Cloudflare 官方文档指出，与容器或虚拟机中的 Node.js 进程相比，隔离实例的启动速度快约一百倍，且启动时的内存消耗低一个数量级。 [6]

### 什么是 workerd，它采用什么许可证分发？

workerd（发音为“worker-dee”）是基于驱动 Cloudflare Workers 的同一套代码构建的开源 JavaScript 与 WebAssembly 服务器运行时，采用 Apache-2.0 许可证分发。Cloudflare 于 2022 年 9 月 27 日发布其首个测试版，用于本地开发、自托管 Workers 应用以及构建可编程 HTTP 代理。Cloudflare 指出，在运行不受信任的代码时，独立部署的 workerd 需要配合虚拟机等外部沙箱使用。 [10][11]

### Cloudflare Workers 的定价是多少？

截至 2026-11-23，Cloudflare 提供免费的 Workers Free 方案（每日 100,000 次请求及每次调用 10 毫秒 CPU 时间）以及账户每月最低 5 美元（$5 USD）的 Workers Paid 方案。在 Standard 用量模式下，Workers Paid 每月包含 1,000 万次请求和 3,000 万 CPU 毫秒，超出部分按每百万次请求 $0.30 和每百万 CPU 毫秒 $0.02 计费，不收取持续时间或出站带宽费用。静态资源请求以及由 Worker 发起的子请求均免费。 [4]

### Cloudflare Workers Free 和 Paid 方案的主要资源限制有哪些？

截至 2026-11-23，Workers Free 和 Workers Paid 方案均执行每个隔离实例 128 MB 内存、64 MiB 未压缩 Worker 包体积、1 秒启动时间以及 6 个同时等待响应头的出站连接上限。Workers Free 将每日流量限制为 100,000 次请求、HTTP CPU 时间 10 ms、每次请求 50 个子请求、每个账户 100 个 Worker 及 5 个 Cron Triggers。Workers Paid 取消了每日请求上限，并将限额提升至 5 分钟 HTTP CPU 时间（默认 30 秒）、每次请求 10,000 个子请求（最高可配置至 1,000 万）、500 个 Worker 及 1,000 个 Cron Triggers。 [5]

### Cloudflare Workers 支持哪些编程语言？

截至 2026-11-23，Cloudflare Workers 为 JavaScript、TypeScript、Python（通过 Python Workers）和 Rust 提供一级支持。由于运行时还可执行 WebAssembly（Wasm），开发者也可以将 C、C++、Kotlin 和 Go 等其他语言编译为 Wasm 后在 Workers 上运行。 [7]

### Cloudflare Workers 支持 Node.js API 吗？

支持。截至 2026-11-23，Cloudflare Workers 在运行时中原生实现了部分 Node.js API，包括 Buffer、crypto、fs、http、https、net、path、process、stream、timers、url、util、zlib 和 AsyncLocalStorage，并由 Wrangler 的 unenv polyfill 及仅支持导入的存根（stub）模块加以补充。对于 2026-08-04 及之后的兼容性日期，无需额外标志即可默认同时启用 nodejs_compat 和 nodejs_compat_v2。 [9]

## 可引用的句子

- Cloudflare 于 2017 年 9 月 29 日在 Cloudflare Blog 上发布了 Cloudflare Workers。 [12]
- Cloudflare Workers 在 Cloudflare 全球网络上的共享运行时进程内部托管的 V8 隔离实例（isolate）中执行用户代码。 [6]
- Cloudflare 于 2022 年 9 月 27 日以 Apache-2.0 许可证发布了驱动 Cloudflare Workers 的 JavaScript 与 WebAssembly 运行时 workerd 的首个测试版。 [10][11]
- 截至 2026-11-23，Cloudflare Workers 为 JavaScript、TypeScript、Python 和 Rust 提供一级支持，同时支持包括 C、C++、Kotlin 和 Go 在内的 WebAssembly（Wasm）编译目标。 [7]
- 对于 2026-08-04 及之后的兼容性日期（compatibility date），Cloudflare Workers 默认同时启用 nodejs_compat 和 nodejs_compat_v2。 [9]
- 截至 2026-11-23，Workers Free 方案每日允许 100,000 次请求及每次调用 10 毫秒 CPU 时间，而 Workers Paid 方案每月最低收费 5 美元（$5 USD），包含每月 1,000 万次请求和 3,000 万 CPU 毫秒，且不收取数据出站（egress）费用。 [4]
- 截至 2026-11-23，Cloudflare Workers 在 Free 和 Paid 方案中均执行每个隔离实例 128 MB 内存上限、64 MiB 未压缩 Worker 体积上限以及 1 秒启动时间上限。 [5]
- Cloudflare 的 2025 财年 SEC 申报文件披露，2025 年 6 月 Workers KV 所依赖的第三方存储基础设施发生故障，导致持续数小时的服务中断，但未造成重大财务影响。 [2]

## 时间线

- 2017-09-29: Cloudflare 在 Cloudflare Blog 上发布 Cloudflare Workers，推出在 Cloudflare 边缘执行的 JavaScript Service Workers。 [12]
- 2018-03-13: Cloudflare 在 2017 年 9 月的 Cloudflare Workers 发布博客文章中追加更新，记录了该服务的可用性。 [12]
- 2022-09-27: Cloudflare 发布 workerd 首个测试版，以 Apache-2.0 许可证开源 Cloudflare Workers 的 JavaScript 与 WebAssembly 运行时。 [11]
- 2024-03-01: Cloudflare 将旧版 Bundled Workers 账户迁移至 Standard 用量模式，并为迁移后的 Bundled Workers 自动应用 50 毫秒 CPU 时间上限。 [4]
- 2024-09-23: Cloudflare Workers 开始在达到或晚于该兼容性日期且启用 nodejs_compat 时自动注入 Wrangler unenv polyfill。 [9]
- 2025-06: Workers KV 所使用的底层第三方存储基础设施发生故障，造成持续数小时的服务中断，该事件披露于 Cloudflare 的 2025 财年 SEC 申报文件中。 [2]
- 2026-08-04: Cloudflare Workers 为配置为该兼容性日期及之后的 Worker 默认同时启用 nodejs_compat 和 nodejs_compat_v2。 [9]

## 来源

1. WinterTC. Ecma International (WinterTC). https://wintertc.org/ (访问于 2026-11-23; tier 1: government or public registry)
2. cloud-20251231. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/1477333/000147733326000016/cloud-20251231.htm (访问于 2026-11-23; tier 1: government or public registry)
3. Overview · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/ (访问于 2026-11-23; tier 3: official site)
4. Pricing · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/pricing/ (访问于 2026-11-23; tier 3: official site)
5. Limits · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/limits/ (访问于 2026-11-23; tier 3: official site)
6. How Workers works · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/reference/how-workers-works/ (访问于 2026-11-23; tier 3: official site)
7. Languages · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/languages/ (访问于 2026-11-23; tier 3: official site)
8. Runtime APIs · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/ (访问于 2026-11-23; tier 3: official site)
9. Node.js compatibility · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/nodejs/ (访问于 2026-11-23; tier 3: official site)
10. GitHub - cloudflare/workerd: The JavaScript / Wasm runtime that powers Cloudflare Workers · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/workerd (访问于 2026-11-23; tier 3: official site)
11. Introducing workerd: the Open Source Workers runtime | Cloudflare Blog. The Cloudflare Blog. 发布于 2022-09-27. https://blog.cloudflare.com/workerd-open-source-workers-runtime/ (访问于 2026-11-23; tier 3: official site)
12. Introducing Cloudflare Workers: Run JavaScript Service Workers at the Edge | Cloudflare Blog. The Cloudflare Blog. 发布于 2017-09-29. https://blog.cloudflare.com/introducing-cloudflare-workers/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Cloudflare Workers." 版本 4332636d, 2026-11-25. https://mimirwiki.com/zh/wiki/cloudflare-workers
