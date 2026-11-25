---
title: "Cloudflare Workers"
subtitle: "Serverless execution platform by Cloudflare running JavaScript, TypeScript, Python, Rust, and WebAssembly across V8 isolates and the workerd runtime"
canonical_url: https://mimirwiki.com/wiki/cloudflare-workers
language: en
page_class: entity
revision_sha256: dd2857af9d2a20ab92975f08382047ab34d13f8fd285aaaea1e17fdb2cf03539
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/cloudflare-workers.md
  txt: https://mimirwiki.com/wiki/cloudflare-workers.txt
  json: https://mimirwiki.com/wiki/cloudflare-workers.json
  jsonld: https://mimirwiki.com/wiki/cloudflare-workers.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/cloudflare-workers
  ja: https://mimirwiki.com/ja/wiki/cloudflare-workers
  zh: https://mimirwiki.com/zh/wiki/cloudflare-workers
  es: https://mimirwiki.com/es/wiki/cloudflare-workers
---

# Cloudflare Workers

> Cloudflare Workers is a serverless compute platform by Cloudflare that executes JavaScript, TypeScript, Python, Rust, and WebAssembly across its global network using V8 isolates and the workerd runtime. Announced in 2017, it provides web standard APIs, Node.js compatibility, and storage bindings. As of 2026-11-23, Cloudflare offers Workers Free and Workers Paid starting at $5 per month.

Cloudflare Workers is a serverless compute platform operated by Cloudflare, Inc. that executes developer applications across Cloudflare's global network using V8 isolates and the open-source workerd runtime. Announced on September 29, 2017, the platform runs JavaScript, TypeScript, Python, Rust, and WebAssembly (Wasm) workloads with web platform APIs and a natively implemented subset of Node.js APIs. Cloudflare released workerd, the JavaScript and WebAssembly server runtime behind Cloudflare Workers, under the Apache-2.0 license on September 27, 2022. As of 2026-11-23, Cloudflare offers a Workers Free plan capped at 100,000 requests per day and a Workers Paid plan starting at $5 USD per month under the Standard usage model with no egress or bandwidth fees.

**Also known as:** Workers, CF Workers, workerd

## Key facts

- **Developer:** Cloudflare, Inc. [2]
- **Execution model:** V8 isolates across Cloudflare's global network [6]
- **Open-source runtime:** workerd (Apache-2.0 license) [10]
- **Workers Free limit:** 100,000 requests per day, 10 ms CPU time per invocation (as of 2026-11-23) [4]
- **Workers Paid pricing:** $5 USD per month minimum (10M requests and 30M CPU ms included) (as of 2026-11-23) [4]

## Basic facts

- **Developer:** Cloudflare, Inc. (SEC CIK 0001477333) [2]
- **Initial announcement:** September 29, 2017 [12]
- **Execution engine:** V8 JavaScript engine (isolates) [6]
- **Open-source runtime:** workerd (Apache-2.0 license, beta announced September 27, 2022) [11]
- **First-class languages:** JavaScript, TypeScript, Python, Rust (as of 2026-11-23) [7]
- **WebAssembly languages:** WebAssembly (Wasm) targets including C, C++, Kotlin, and Go (as of 2026-11-23) [7]
- **Node.js compatibility:** Enabled by default for compatibility dates on or after 2026-08-04 (as of 2026-11-23) [9]
- **Workers Free plan:** 100,000 requests per day; 10 ms CPU time per invocation (as of 2026-11-23) [4]
- **Workers Paid plan:** $5 USD per month minimum; 10 million requests and 30 million CPU ms included; no egress fees (as of 2026-11-23) [4]
- **Memory per isolate:** 128 MB (JavaScript heap and WebAssembly allocations) (as of 2026-11-23) [5]
- **Worker size and startup:** 64 MiB uncompressed bundle; 1-second startup time limit (as of 2026-11-23) [5]
- **Maximum CPU time (Paid):** 5 minutes per HTTP request (30 seconds default); 15 minutes for hourly or longer Cron Triggers (as of 2026-11-23) [5]

## Cloudflare Workers V8 isolate architecture and workerd runtime

Cloudflare Workers executes user applications on the V8 JavaScript engine across [Cloudflare](https://mimirwiki.com/wiki/cloudflare)'s global network of distributed servers.[6] Each server runs instances of the Workers runtime, and each runtime instance hosts hundreds or thousands of V8 isolates, which are lightweight execution contexts with separate memory sandboxes.[6] The runtime initializes a single V8 host process per container and runs user scripts inside isolates within that process, whereas container-based serverless architectures start a separate language runtime process or virtual machine per function.[6] Cloudflare's documentation states that a V8 isolate starts roughly one hundred times faster and consumes an order of magnitude less memory on startup than a Node.js process in a container or virtual machine.[6]

Requests routed to a `*.workers.dev` subdomain or a Cloudflare-managed domain invoke a Worker's exported `fetch(request, env, ctx)` handler in ES modules syntax and receive a `Response` object.[6] Each Worker instance processes requests, including concurrent requests awaiting asynchronous I/O, on a single-threaded event loop.[6] Isolates can be evicted when host resources become constrained, when a Worker hits resource limits, or when code exhibits suspicious sandbox-escape behavior.[6] Because there is no guarantee that any two requests reach the same instance of a Worker, Cloudflare advises against storing mutable state in global scope.[6]

The open-source server runtime powering Cloudflare Workers is `workerd` (pronounced "worker-dee"), published on GitHub under the Apache-2.0 license.[10][11] Developers use `workerd` to self-host Workers-compatible applications, run local development and test environments, or operate a programmable forward or reverse HTTP proxy.[10] Cloudflare documents six design principles for `workerd`:[10]

- Server-first design targeting server workloads specifically, excluding CLI and GUI environments.[10]
- Standard-based built-in APIs aligned with web platform specifications such as `fetch()`.[10]
- Nanoservices allowing independently deployable components to invoke one another inside the same thread and process.[10]
- Homogeneous deployment across cluster machines to simplify load balancing.[10]
- Capability bindings linking services and external resources through explicit references to reduce server-side request forgery (SSRF) exposure.[10]
- Date-based backwards compatibility in which each `workerd` version identifier corresponds to the maximum compatibility date it supports, preserving historical API behavior for older compatibility dates.[10]

`workerd` builds with Bazel and is tested on Linux and macOS (`x86-64` and `arm64`) as well as Windows (`x86-64`).[10] Its native configuration uses Cap'n Proto text format, and `workerd serve wrangler.jsonc` also loads Wrangler configurations bundled via `esbuild`.[10] As of 2026-11-25, the `cloudflare/workerd` GitHub repository recorded 9.3k stars, 846 forks, and 14,147 commits.[10] Cloudflare warns that standalone `workerd` is unsuitable as a sole hardened sandbox against implementation bugs and requires an outer virtual machine or sandbox for untrusted code, while the hosted Cloudflare Workers service applies additional defense-in-depth layers.[10]

## Cloudflare Workers runtime APIs, web standards, and Node.js compatibility

Cloudflare Workers implements web platform APIs so application code can follow JavaScript web standards across browsers and server runtimes.[8] Its built-in runtime APIs include Fetch, Request, Response, Headers, Cache, Streams (`ReadableStream`, `WritableStream`, and `TransformStream`), Web Crypto, WebSockets, TCP sockets, Encoding, EventSource, MessageChannel, Performance and timers, Scheduler, HTMLRewriter, Remote-procedure call (RPC), Context (`ctx`), Bindings (`env`), and event handlers covering Fetch, Scheduled, Queue, Email, Alarm, Tail, and Connect events.[8]

Cloudflare's runtime API documentation states that Workers reuses web platform APIs for interoperability across WinterCG JavaScript runtimes.[8] In the broader standards ecosystem, Ecma International's Technical Committee 55, known as WinterTC (Technical Committee on Web-interoperable Server Runtimes), standardizes a minimum common API shared with the web for server-side JavaScript runtimes, collaborates with WHATWG and W3C on web API specifications, and publishes standards for interoperable server-side APIs.[1]

To run npm packages that depend on Node.js libraries, Cloudflare Workers provides a subset of Node.js APIs through two mechanisms: native built-in implementations targeting the Current release of Node.js, and polyfill shims injected by Wrangler via `unenv` whose unimplemented methods either no-op or throw errors.[9] Runtime behavior is controlled by a Worker's compatibility date and compatibility flags.[8][9] For compatibility dates on or after 2026-08-04, Cloudflare Workers enables both `nodejs_compat` and `nodejs_compat_v2` by default, while projects opting out add `no_nodejs_compat` and `no_nodejs_compat_v2`.[9] Compatibility dates from 2024-09-23 through 2026-08-03 opt in through the `nodejs_compat` flag, which also enables automatic `unenv` polyfill injection; a separate `nodejs_als` flag enables `AsyncLocalStorage` alone.[9]

As of 2026-11-23, Cloudflare documents the following Node.js runtime compatibility coverage:[9]

- Natively supported modules: `assert`, `AsyncLocalStorage`, `Buffer`, `crypto`, Debugger (via Chrome DevTools integration), Diagnostics Channel, Errors, `EventEmitter`, `fs`, Globals, `http`, `https`, `net`, `path`, `process`, Punycode (deprecated), Query strings, `stream`, `StringDecoder`, `timers`, `url`, `util`, Web Crypto API, Web Streams API, and `zlib`.[9]
- Partially supported modules: Console, `dns`, Module, OS, Performance hooks, Test runner, and `tls` (TLS/SSL).[9]
- Non-functional import-only stub modules enabled with `nodejs_compat` by compatibility date: `node:http2` (2025-09-01), `node:vm` (2025-10-01), `node:cluster`, `node:domain`, `node:trace_events`, and `node:wasi` (2025-12-04), `node:_stream_wrap`, `node:dgram`, `node:inspector`, and `node:sqlite` (2026-01-29), and `node:child_process`, `node:readline`, `node:repl`, `node:tty`, `node:v8`, and `node:worker_threads` (2026-03-17).[9]

## Cloudflare Workers languages, developer tooling, and platform bindings

Cloudflare Workers supports multiple programming languages, local development tools, web frameworks, and direct bindings to Cloudflare platform services.[3][7] As of 2026-11-23, the platform lists first-class support for four languages: JavaScript, TypeScript, Python (via Python Workers), and Rust (labeled Beta in the documentation navigation).[3][7] Through WebAssembly (Wasm) binary support, developers can also deploy Workers written in languages compiled to Wasm, including C, C++, Kotlin, and Go.[7]

Developers build, test, and deploy Workers using the Wrangler CLI, the Cloudflare Vite Plugin, Miniflare, Vitest integration, and built-in CI/CD via Workers Builds (with GitHub and GitLab integrations) or external pipelines such as GitHub Actions and GitLab CI/CD.[3] Cloudflare publishes framework guides for web and API frameworks including React, Vue, SvelteKit, Next.js (using the OpenNext adapter), Astro, React Router, Remix 3, Nuxt, Angular, Hono, TanStack Start, Qwik, Solid, FastAPI, and Flask.[3] Static front-end assets can be served directly through Cloudflare's [content delivery network](https://mimirwiki.com/wiki/content-delivery-network) and cache alongside Worker logic, and Smart Placement optimizes back-end request routing toward external data stores.[3] As of 2026-11-23, Cloudflare Workers documentation also publishes an [llms.txt](https://mimirwiki.com/wiki/llms-txt) index, `llms-full.txt`, per-page [Markdown](https://mimirwiki.com/wiki/markdown) views, and links to Cloudflare's [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) servers.[3]

In Cloudflare's fiscal year 2025 filing on [SEC EDGAR](https://mimirwiki.com/wiki/sec-edgar), Cloudflare categorizes Cloudflare Workers, Cloudflare Workers for Platforms (a multi-tenant managed execution environment where platform customers run end-user code), and Cloudflare Pages under its Compute developer solutions.[2] Workers connect to storage, compute, AI, and media services through explicit `env` bindings:[2][3]

- Storage and databases: Durable Objects (stateful real-time coordination), D1 (serverless SQL database), Workers KV (globally distributed key-value storage with edge-cached reads), Queues (asynchronous message queues without egress charges), Hyperdrive (connection pooling, routing optimization, and query caching for external databases), and R2 (object storage without egress fees).[2][3]
- Compute and AI: Workers AI (machine learning inference on serverless GPUs), Workflows (durable multi-step execution with automatic retries), Vectorize (vector database for embeddings and semantic search), Browser Run (programmatic serverless browser instances), Service bindings (HTTP and `WorkerEntrypoint` RPC calls between Workers), Dynamic Worker Loaders, and the Workers for Platforms Dispatcher.[2][3]
- Media and operational bindings: Cache, Images, Stream, Media Transformations, Assets, Analytics Engine, Rate Limiting, Secrets, Secrets Store (Beta), mTLS certificates, and environment variables.[3]

## Cloudflare Workers plans and pricing

Cloudflare Workers is offered on a Workers Free plan, a Workers Paid plan with a $5 USD monthly account minimum, and contract-based Workers Enterprise accounts.[4] Accounts default to Workers Free, which provides daily usage allowances for Workers, Pages Functions, Workers KV, and Hyperdrive.[4] Workers Paid uses the Standard usage model, grants monthly allotments covering Workers, Pages Functions, Workers KV, Hyperdrive, and Durable Objects, and applies no additional fees for data transfer (egress) or bandwidth.[4] All Pages Functions follow the same billing rules as Workers.[4] Legacy usage models (Workers Unbound and Workers Bundled) remain in some older configurations, while Cloudflare migrated Bundled Workers to Standard pricing on March 1, 2024 with an automatic 50-millisecond CPU limit.[4]

As of 2026-11-23, Cloudflare publishes the following Workers compute pricing under the Free and Paid (Standard) tiers:[4]

| Metric | Workers Free | Workers Paid (Standard) |
| --- | --- | --- |
| Base subscription | $0 | $5 USD per month minimum |
| Inbound requests | 100,000 per day | 10 million per month included, then $0.30 per additional million |
| Duration (wall-clock time) | No charge | No charge and no limit |
| CPU time | 10 ms per invocation | 30 million CPU ms per month included, then $0.02 per additional million CPU ms |
| Maximum CPU time per invocation | 10 ms | 5 minutes HTTP (30 seconds default); 15 minutes for hourly or longer Cron Triggers |
| Static asset requests | Free and unlimited | Free and unlimited |

Cloudflare does not bill for outbound subrequests initiated by a Worker.[4] WebSocket connections count as a single request upon the initial Upgrade handshake, while routed messages incur no per-message request fees.[4] When Workers Caching is enabled, cache hits are billed at the per-request rate (including static assets and Worker-to-Worker calls), and CPU time is billed only when the Worker executes on a cache miss or bypass.[4] Account owners can configure a Workers spending limit to block new invocations once post-allowance request and CPU charges cross a chosen threshold (excluding the $5 subscription fee), or configure non-blocking email alerts.[4]

Cloudflare's Workers pricing page also lists allowances and overage rates for adjacent developer services as of 2026-11-23:[4]

| Service and metric | Workers Free | Workers Paid |
| --- | --- | --- |
| Workers Logs events written | 200,000 per day (3-day retention) | 20 million per month included, then $0.60 per million (7-day retention) |
| Workers Trace Events Logpush | Unavailable | 10 million requests per month included, then $0.05 per million |
| Workers KV keys read | 100,000 per day | 10 million per month included, then $0.50 per million |
| Workers KV keys written, deleted, or listed | 1,000 per day each | 1 million per month included, then $5.00 per million each |
| Workers KV storage and namespaces | 1 GB; 1,000 namespaces | 1 GB (+$0.50/GB-month); first 1,000 namespaces (+$0.10/additional namespace/month) |
| Hyperdrive database queries | 100,000 per day | Unlimited |
| Queues standard operations (per 64 KB message chunk) | 10,000 per day (24-hour retention; 10,000 queues) | 1 million per month (+$0.40/million; 4-day default up to 14-day retention; first 10,000 queues included, +$0.10/additional queue/month) |
| Workflows steps and storage | 3,000 steps per day; 1 GB-month (requests shared with Workers) | 500,000 steps per month (+$0.80 per 100,000); 1 GB-month (+$0.20/GB-month) |
| D1 rows read | 5 million per day | 25 billion per month included, then $0.001 per million |
| D1 rows written | 100,000 per day | 50 million per month included, then $1.00 per million |
| D1 storage and databases | 5 GB total; 10 databases | 5 GB (+$0.75/GB-month); 100,000 databases (+$0.10/additional database/month) |

Cloudflare notes that Workers Logs will transition to Cloudflare Observability pricing beginning December 1, 2026, and that Workflows step and storage billing begins on the date announced in the Workflows billing changelog.[4] Queues meters operations on each individual message per 64 KB chunk (1 KB defined as 1,000 bytes, with roughly 100 bytes of internal metadata), so typical delivery consumes three operations (write, read, and delete) with no egress fees.[4]

## Cloudflare Workers operational and resource limits

Cloudflare Workers enforces account, execution, network, and deployment limits across both the Workers Free and Workers Paid plans.[5] As of 2026-11-23, Cloudflare lists the following core account and platform limits:[5]

| Limit | Workers Free | Workers Paid |
| --- | --- | --- |
| Daily requests | 100,000 per day (resets 00:00 UTC) | No limit |
| CPU time per HTTP request | 10 ms | 5 minutes (30 seconds default) |
| CPU time per Cron Trigger | 10 ms | 5 minutes (under 1-hour interval); 15 minutes (1-hour or longer interval) |
| Memory per isolate | 128 MB | 128 MB |
| Subrequests per invocation | 50 (1,000 to internal services) | 10,000 (configurable up to 10 million) |
| Simultaneous outgoing connections waiting for headers | 6 | 6 |
| Environment variables per Worker (secrets and text) | 64 (5 KB each) | 128 (5 KB each) |
| Worker bundle size (uncompressed) | 64 MiB | 64 MiB |
| Worker startup time (global scope) | 1 second | 1 second |
| Workers per account | 100 | 500 |
| Version retention | 30 days (100 most recent kept) | 30 days (100 most recent kept) |
| Cron Triggers per account | 5 | 1,000 |
| Static asset files per Worker version | 20,000 (25 MiB per file) | 100,000 (25 MiB per file) |

CPU time counts only active script execution and excludes time spent waiting on network I/O such as `fetch()`, KV reads, or database queries.[5] Cloudflare reports that an average Worker consumes approximately 2.2 ms of CPU time per request, while heavier workloads handling authentication, server-side rendering, or large payload parsing typically use 10-20 ms.[5] Exceeding the Workers Free daily request limit triggers Error 1027 (with routes configurable as fail open to bypass the Worker or fail closed to return the error page).[5] Exceeding CPU or memory limits returns Error 1102 (`exceededCpu` or `exceededMemory` in analytics and Logpush), and exceeding the 1-second global-scope startup limit rejects deployment with error code 10021.[5]

The 128 MB memory cap covers both the JavaScript heap and WebAssembly allocations across an entire isolate, which may handle multiple concurrent requests.[5] When an isolate exceeds 128 MB, the runtime allows in-flight requests to complete and routes new requests to a fresh isolate, canceling incoming requests only under extreme load.[5] HTTP-triggered Workers have no hard wall-clock duration limit while the client remains connected, and `ctx.waitUntil()` can extend execution up to 30 seconds after a response finishes or a client disconnects; Cron Triggers, Durable Object Alarms, and Queue Consumers are capped at 15 minutes of wall-clock duration.[5] During routine runtime updates, processes on the previous runtime version allow up to 20 minutes to drain existing streaming HTTP responses and WebSockets.[5]

Each top-level request (including Workers invoked via Service bindings) permits up to six simultaneous outbound connections waiting for response headers across `fetch()`, KV, Cache, R2, Queues, TCP `connect()`, and outbound WebSockets, queueing additional connections until headers arrive.[5] Request and response limits cap URLs at 16 KB and total request or response headers at 128 KB each, with no enforced response body size limit (subject to CDN cache caps of 512 MB on Free, Pro, and Business plans and 5 GB on Enterprise).[5] Incoming request body limits are governed by the domain's Cloudflare plan: 100 MB on Free and Pro, 200 MB on Business, and up to 5 GB self-serve on Enterprise (returning HTTP 413 if exceeded), while outbound HTTP bodies sent from Durable Objects or Containers default to 100 MiB.[5] Routing limits allow 1,000 routes per zone (50 during `wrangler dev --remote` or Quick Editor sessions), 100 custom domains per zone, and 1,000 routed zones per Worker.[5] Multi-tenant platforms needing more than 500 Workers can use Workers for Platforms, which supports an unlimited number of user Workers.[5]

## Cloudflare Workers history and operational disclosures

Cloudflare Workers was introduced on September 29, 2017 on the Cloudflare Blog during Birthday Week as a way to run JavaScript Service Workers at Cloudflare's network edge.[12] An update dated March 13, 2018 was later appended to that launch announcement recording availability of the platform.[12] Five years after the initial launch, on September 27, 2022, Cloudflare announced the first beta release of `workerd`, releasing the JavaScript and WebAssembly runtime code behind Cloudflare Workers as open-source software under the Apache-2.0 license.[11]

On March 1, 2024, Cloudflare migrated accounts from legacy Bundled pricing to the Standard usage model.[4] Beginning with compatibility date 2024-09-23, enabling `nodejs_compat` instructed Wrangler to inject `unenv` polyfills automatically.[9] Import-only stubs for Node.js modules such as `node:http2`, `node:vm`, `node:sqlite`, `node:child_process`, and `node:worker_threads` are enabled with `nodejs_compat` on compatibility dates from 2025-09-01 through 2026-03-17, and for compatibility dates of 2026-08-04 or later Workers enables `nodejs_compat` and `nodejs_compat_v2` by default.[9] Cloudflare has also scheduled Workers Logs to adopt Cloudflare Observability pricing on December 1, 2026.[4]

In [Cloudflare](https://mimirwiki.com/wiki/cloudflare)'s fiscal year 2025 filing on [SEC EDGAR](https://mimirwiki.com/wiki/sec-edgar), the company states that customers' use of its developer solutions, including Cloudflare Workers, opened a new market for it in storage and compute, and that it believes it is increasingly competing with public cloud vendors for storage and compute workloads.[2] In the same filing's risk disclosures, Cloudflare reported an operational incident in June 2025 in which underlying third-party storage infrastructure used by the Workers KV service failed, causing a service outage lasting several hours that affected a portion of Cloudflare's services and customers.[2] Cloudflare stated that the June 2025 outage had no material impact on its business, results of operations, or financial condition.[2]

## Frequently asked questions

### How does Cloudflare Workers execute code using V8 isolates?

Cloudflare Workers runs the V8 JavaScript engine inside shared operating system processes and allocates a lightweight V8 isolate with isolated memory for each user application. A single runtime instance runs hundreds or thousands of isolates and switches between them, paying the runtime process startup cost once per container. Cloudflare's documentation reports that isolates start roughly one hundred times faster and consume an order of magnitude less startup memory than a Node.js process in a container or virtual machine. [6]

### What is workerd and under what license is it distributed?

workerd (pronounced "worker-dee") is the open-source JavaScript and WebAssembly server runtime based on the same code that powers Cloudflare Workers, distributed under the Apache-2.0 license. Cloudflare announced its first beta release on September 27, 2022 for local development, self-hosting Workers applications, and programmable HTTP proxying. Cloudflare notes that standalone workerd requires an external sandbox such as a virtual machine when running untrusted code. [10][11]

### How much does Cloudflare Workers cost?

As of 2026-11-23, Cloudflare offers a Workers Free plan at no charge with 100,000 requests per day and 10 milliseconds of CPU time per invocation, plus a Workers Paid plan with a $5 USD monthly account minimum. Under the Standard usage model, Workers Paid includes 10 million requests and 30 million CPU milliseconds per month, charges $0.30 per additional million requests and $0.02 per additional million CPU milliseconds, and applies no duration or egress bandwidth charges. Static asset requests and Worker-initiated subrequests are free. [4]

### What are the main resource limits on Cloudflare Workers Free and Paid plans?

As of 2026-11-23, both Workers Free and Workers Paid plans enforce 128 MB of memory per isolate, a 64 MiB uncompressed Worker bundle size, a 1-second startup time limit, and 6 simultaneous outgoing connections waiting for response headers. Workers Free caps daily traffic at 100,000 requests, HTTP CPU time at 10 ms, subrequests at 50 per request, and account counts at 100 Workers and 5 Cron Triggers. Workers Paid removes the daily request cap and raises limits to 5 minutes of HTTP CPU time (30 seconds default), 10,000 subrequests per request (configurable up to 10 million), 500 Workers, and 1,000 Cron Triggers. [5]

### Which programming languages does Cloudflare Workers support?

As of 2026-11-23, Cloudflare Workers provides first-class support for JavaScript, TypeScript, Python (via Python Workers), and Rust. Because the runtime also executes WebAssembly (Wasm), developers can compile additional languages including C, C++, Kotlin, and Go to run on Workers. [7]

### Does Cloudflare Workers support Node.js APIs?

Yes. As of 2026-11-23, Cloudflare Workers implements a subset of Node.js APIs natively in the runtime, including Buffer, crypto, fs, http, https, net, path, process, stream, timers, url, util, zlib, and AsyncLocalStorage, supplemented by Wrangler unenv polyfills and import-only stub modules. For compatibility dates on or after 2026-08-04, both nodejs_compat and nodejs_compat_v2 are enabled by default without extra flags. [9]

## Quotable sentences

- Cloudflare announced Cloudflare Workers on September 29, 2017 on the Cloudflare Blog. [12]
- Cloudflare Workers executes user code inside V8 isolates hosted within shared runtime processes across Cloudflare's global network. [6]
- Cloudflare introduced the first beta release of workerd, the JavaScript and WebAssembly runtime that powers Cloudflare Workers, under the Apache-2.0 license on September 27, 2022. [10][11]
- As of 2026-11-23, Cloudflare Workers provides first-class support for JavaScript, TypeScript, Python, and Rust, alongside WebAssembly (Wasm) compilation targets including C, C++, Kotlin, and Go. [7]
- For compatibility dates on or after 2026-08-04, Cloudflare Workers enables both nodejs_compat and nodejs_compat_v2 by default. [9]
- As of 2026-11-23, the Workers Free plan allows 100,000 requests per day and 10 milliseconds of CPU time per invocation, while the Workers Paid plan has a $5 USD monthly minimum and includes 10 million requests and 30 million CPU milliseconds per month with no egress charges. [4]
- As of 2026-11-23, Cloudflare Workers enforces a 128 MB memory limit per isolate, a 64 MiB uncompressed Worker size limit, and a 1-second startup time limit on both Free and Paid plans. [5]
- Cloudflare's fiscal year 2025 SEC filing discloses that a June 2025 failure in third-party storage infrastructure used by Workers KV caused a multi-hour service outage without a material financial impact. [2]

## Timeline

- 2017-09-29: Cloudflare announces Cloudflare Workers on the Cloudflare Blog, introducing JavaScript Service Workers executed at Cloudflare's edge. [12]
- 2018-03-13: Cloudflare appends an update to the September 2017 Cloudflare Workers launch blog post recording availability of the service. [12]
- 2022-09-27: Cloudflare announces the first beta release of workerd, open-sourcing the Cloudflare Workers JavaScript and WebAssembly runtime under the Apache-2.0 license. [11]
- 2024-03-01: Cloudflare migrates legacy Bundled Workers accounts to the Standard usage model and applies an automatic 50-millisecond CPU limit to migrated Bundled Workers. [4]
- 2024-09-23: Cloudflare Workers begins automatically injecting Wrangler unenv polyfills when nodejs_compat is enabled on or after this compatibility date. [9]
- 2025-06: A failure in underlying third-party storage infrastructure used by Workers KV causes a multi-hour service outage disclosed in Cloudflare's fiscal year 2025 SEC filing. [2]
- 2026-08-04: Cloudflare Workers enables both nodejs_compat and nodejs_compat_v2 by default for Workers configured with this compatibility date or later. [9]

## Sources

1. WinterTC. Ecma International (WinterTC). https://wintertc.org/ (checked 2026-11-23; tier 1: government or public registry)
2. cloud-20251231. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/1477333/000147733326000016/cloud-20251231.htm (checked 2026-11-23; tier 1: government or public registry)
3. Overview · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/ (checked 2026-11-23; tier 3: official site)
4. Pricing · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/pricing/ (checked 2026-11-23; tier 3: official site)
5. Limits · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/limits/ (checked 2026-11-23; tier 3: official site)
6. How Workers works · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/reference/how-workers-works/ (checked 2026-11-23; tier 3: official site)
7. Languages · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/languages/ (checked 2026-11-23; tier 3: official site)
8. Runtime APIs · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/ (checked 2026-11-23; tier 3: official site)
9. Node.js compatibility · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/nodejs/ (checked 2026-11-23; tier 3: official site)
10. GitHub - cloudflare/workerd: The JavaScript / Wasm runtime that powers Cloudflare Workers · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/workerd (checked 2026-11-23; tier 3: official site)
11. Introducing workerd: the Open Source Workers runtime | Cloudflare Blog. The Cloudflare Blog. published 2022-09-27. https://blog.cloudflare.com/workerd-open-source-workers-runtime/ (checked 2026-11-23; tier 3: official site)
12. Introducing Cloudflare Workers: Run JavaScript Service Workers at the Edge | Cloudflare Blog. The Cloudflare Blog. published 2017-09-29. https://blog.cloudflare.com/introducing-cloudflare-workers/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Cloudflare Workers." Version dd2857af, 2026-11-25. https://mimirwiki.com/wiki/cloudflare-workers
