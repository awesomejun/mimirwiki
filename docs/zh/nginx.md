---
title: "nginx"
subtitle: "高性能开源异步 Web 服务器、反向代理、负载均衡器与邮件代理"
canonical_url: https://mimirwiki.com/zh/wiki/nginx
language: zh
page_class: entity
revision_sha256: 625385b5ecf4f5acbf40f64cc24bae8eaed3867f7c40c8d58c86294a9d586a9a
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/nginx.md
  txt: https://mimirwiki.com/zh/wiki/nginx.txt
  json: https://mimirwiki.com/zh/wiki/nginx.json
  jsonld: https://mimirwiki.com/zh/wiki/nginx.jsonld
translations:
  en: https://mimirwiki.com/wiki/nginx
  ko: https://mimirwiki.com/ko/wiki/nginx
  ja: https://mimirwiki.com/ja/wiki/nginx
---

# nginx

> 截至 2026 年 11 月 23 日，nginx 当前的开源发布分支为 nginx 1.31.10（主线版，发布于 2026 年 11 月 23 日）与 nginx 1.30.8（稳定版），这两个版本修复了 CVE-2026-132779（一项中危漏洞，在 TLS 1.3 中使用 ssl_early_data 指令时，客户端可能导致 CPU 占用过高）。此前，nginx 于 2026 年 11 月 18 日发布了 1.31.9（主线版）与 1.30.7（稳定版），共修复 10 个安全漏洞（其中 9 个影响稳定版 1.30.7），其中最严重的是两项 CVSS v4.0 评分 9.2（严重）/ CVSS v3.1 评分 8.1（高危）的未认证 HTTP/2 远程代码执行漏洞：CVE-2026-123007（自 nginx 1.9.5 引入、潜伏达 10 年的 HTTP/2 send_window 整数下溢与堆缓冲区溢出漏洞）与 CVE-2026-123633（HTTP/2 上游代理 worker_connections 释放后使用漏洞）。

nginx（常写作 NGINX，读作“engine-x”）是一款开源、事件驱动的 HTTP Web 服务器、反向代理、应用负载均衡器、内容缓存与邮件代理服务器，最初由伊戈尔·瑟索耶夫（Igor Sysoev）开发并于 2004 年 10 月公开发布。nginx 采用 2 条款 BSD 许可证分发，自 F5, Inc. 于 2019 年收购 NGINX, Inc. 以来由 F5 负责维护。该软件采用异步主从（master-worker）进程架构，旨在以极低的内存开销处理数万个并发连接。

**别名:** NGINX, Engine-X, NGINX Open Source, NGINX Plus

## 关键事实

- **原作者与所有者:** 伊戈尔·瑟索耶夫（2004 年）；F5, Inc.（自 2019 年 5 月起） [1]
- **许可证:** 2 条款 BSD 许可证 [1]
- **最新版本:** 1.31.10（主线版，2026 年 11 月 23 日发布）与 1.30.8（稳定版） (截至 2026-11-23) [2]
- **2026 年 11 月安全更新:** 1.31.10 / 1.30.8 修复 CVE-2026-132779（ssl_early_data 导致 CPU 占用过高）；1.31.9 / 1.30.7（11 月 18 日）修复 10 个 CVE，包括 CVSS 9.2 的 HTTP/2 RCE 漏洞 CVE-2026-123007 与 CVE-2026-123633 (截至 2026-11-23) [3]

## 事实摘要

- **原作者:** 伊戈尔·瑟索耶夫（Igor Sysoev） [1]
- **维护方:** F5, Inc.（NGINX Product Group） [1]
- **首次公开发布:** 2004 年 10 月 4 日（0.1.0 版） [1]
- **主线版本（2026 年 11 月）:** 1.31.10（2026 年 11 月 23 日） (截至 2026-11-23) [3]
- **稳定版本（2026 年 11 月）:** 1.30.8（与 1.31.10 一同列为不受 CVE-2026-132779 影响的版本） (截至 2026-11-23) [2]
- **编程语言:** C [1]
- **许可证:** 2 条款 BSD 许可证 [1]
- **支持协议:** HTTP/1.x、HTTP/2、HTTP/3（QUIC）、TLS/SSL、FastCGI、uwsgi、SCGI、gRPC、IMAP/POP3/SMTP、TCP/UDP [1]

## nginx 概述与异步事件驱动架构

nginx 由俄罗斯软件工程师伊戈尔·瑟索耶夫于 2002 年设计，旨在解决 **C10k 问题**（在单台服务器上同时处理 10,000 个以上客户端并发连接），并于 2004 年 10 月 4 日以 2 条款 BSD 许可证开源发布。[1] 与传统的每连接一线程或每连接一进程 Web 服务器不同，nginx 采用单个特权 **主进程（master process）**（负责读取配置文件、绑定特权端口以及管理工作进程生命周期）与一个或多个非特权、单线程的 **工作进程（worker processes）**（以及可选的缓存加载进程与缓存管理进程）。[1]

每个工作进程均运行一个基于操作系统原生内核通知机制（Linux 上的 `epoll`、FreeBSD 与 macOS 上的 `kqueue`，以及 Solaris 上的 event ports）的非阻塞异步事件循环。[1] 由于工作进程不会为每个连接创建新的操作系统线程，也不会在磁盘或网络 I/O 上阻塞，nginx 能够以可预测的内存占用提供静态资源服务、终结 TLS 1.3、复用 HTTP/2 与 HTTP/3（QUIC）流、代理 gRPC 与 WebSocket 流量，并在 `http`、`stream` 与 `mail` 上下文中对上游应用服务器执行负载均衡。[1] 2019 年 5 月，应用交付厂商 **F5, Inc.** 收购了 NGINX, Inc.，并继续维护开源版 NGINX Open Source（`nginx.org`）与商业发行版 NGINX Plus。[1][2]

## nginx 发布分支：主线版 1.31.x 与稳定版 1.30.x

nginx 项目在 `nginx.org` 上并行维护两个开源发布分支。[1][2] - **主线分支（Mainline branch）**（奇数次版本号，当前为 **1.31.x**，截至 2026 年 11 月 23 日为 **1.31.10**）：接收所有新功能、协议增强、缺陷修复与安全补丁。[2][3] - **稳定分支（Stable branch）**（偶数次版本号，当前为 **1.30.x**，截至 2026 年 11 月为 **1.30.8**）：每年从主线分支分叉，仅接收关键缺陷修复与安全补丁回移植，不引入破坏模块 API 向后兼容性的变更。[1][2]

**2026 年 11 月 18 日**，nginx 项目发布了 **nginx 1.31.9** 与 **nginx 1.30.7**，集中修复了主线版 1.31.9 中的 10 个 CVE 漏洞（其中 9 个同时影响稳定版 1.30.x），涉及 HTTP/2、HTTP/3、上游代理处理、异步 DNS 解析器、邮件代理模块、`try_files`/`alias` URI 处理以及 `stream` 的 TLS/SNI 处理。[2][3] 五天后的 **2026 年 11 月 23 日**，该项目发布了 **nginx 1.31.10**（`nginx.org` 安全公告页面将 **1.31.10+** 与 **1.30.8+** 列为不受影响版本），修复了 **CVE-2026-132779**（影响 `1.21.4-1.31.9` 版本的中危漏洞，在 TLS 1.3 中使用 `ssl_early_data` 指令时客户端可能导致 CPU 占用过高）以及与后端建立 SSL 连接时 nginx 可能持续占用 CPU 的缺陷。[2][3]

## 2026 年 11 月 nginx 安全公告与 HTTP/2 RCE 漏洞

在 2026 年 11 月 18 日与 11 月 23 日的两次更新中，nginx 项目披露了在 1.31.x 主线分支与 1.30.x 稳定分支中修复的共 11 个安全漏洞。[2][3] 在 11 月 18 日的更新（1.31.9 与 1.30.7）中，云安全研究团队 **Wiz Research** 详细披露了两项严重的未认证 HTTP/2 远程代码执行漏洞：**CVE-2026-123007** 与 **CVE-2026-123633**。两者在 NIST 国家漏洞数据库（NVD）中均获得 **CVSS v4.0 基础评分 9.2（严重）** 与 **CVSS v3.1 基础评分 8.1（高危）**，并在安全社区公告中被称为 **nginx2root** / **nginx2shell**。[4][5][6][8]

| CVE 编号 | 受影响模块与版本 | 漏洞机制 | 严重级别 / 修复版本 |
| --- | --- | --- | --- |
| **CVE-2026-132779** | TLS 1.3 `ssl_early_data`（nginx 1.21.4 - 1.31.9） | 使用 `ssl_early_data` 指令时，客户端可能导致 CPU 占用过高。[2][3] | 中危（`nginx.org`）；已在 1.31.10+、1.30.8+ 中修复 |
| **CVE-2026-123007** | `ngx_http_v2_module`（nginx 1.9.5 - 1.31.8；潜伏 10 年的漏洞） | 通过构造的 `SETTINGS` 与 `WINDOW_UPDATE` 帧在 HTTP/2 `send_window` 流量控制计数中触发整数下溢，导致基于堆的缓冲区溢出（`CWE-191`、`CWE-122`）。[2][4][6] | CVSS v4.0：9.2 严重 / v3.1：8.1 高危；已在 1.31.9+、1.30.7+ 中修复 |
| **CVE-2026-123633** | `ngx_http_v2_module` + 上游代理（1.19.7 - 1.31.8） | 当 `worker_connections` 耗尽且 HTTP/2 客户端连接向上游后端代理时触发释放后使用（`CWE-416`）。[2][5][6] | CVSS v4.0：9.2 严重 / v3.1：8.1 高危；已在 1.31.9+、1.30.7+ 中修复 |
| **CVE-2026-121810** | `ngx_http_v3_module`（1.25.0 - 1.31.8） | 当 `worker_connections` 耗尽时，HTTP/3 QUIC 处理过程中发生释放后使用。[2][3] | 中危（`nginx.org`）；已在 1.31.9+、1.30.7+ 中修复 |
| **CVE-2026-123634** | 核心异步 DNS `resolver`（0.6.18 - 1.31.8） | 配置 `resolver` 后，子请求并发进行域名解析时发生释放后使用。[2][3] | 中危（`nginx.org`）；已在 1.31.9+、1.30.7+ 中修复 |
| **CVE-2026-113425** | `ngx_mail_module`（0.5.33 - 1.31.8） | 邮件代理服务器模块中的释放后使用。[2][3] | 重要（`nginx.org`）；已在 1.31.9+、1.30.7+ 中修复 |

2026 年 11 月 18 日在 nginx 1.31.9 中修复的其余 5 个漏洞（1.30.7 中修复了其中 4 个）包括：**CVE-2026-125283**（组合使用 `try_files` 与 `alias` 指令时的缓冲区溢出）、**CVE-2026-120967**（`stream` 同步 SSL 握手中通过 SNI 绕过 SSL 客户端证书验证）、**CVE-2026-120993**（在 PROXY protocol v2 结合动态 SSL 证书加载时导致工作进程空指针解引用与段错误，影响主线版 1.31.4 - 1.31.8）、**CVE-2026-123640**（`ngx_stream_ssl_preread_module` 对畸形 ClientHello 消息校验不足），以及 **CVE-2026-118899**（通过 SSL/TLS 1.3 读取客户端请求体时导致工作进程死循环）。[2][3]

nginx 变更日志将 CVE-2026-123007 归功于 Xint.io，将 CVE-2026-123633 归功于 Vexera AI 的 Albert。[3]

## nginx 漏洞 CVE-2026-123007 与 CVE-2026-123633 技术分析

在 2026 年 11 月的 nginx 安全公告中，**CVE-2026-123007** 与 **CVE-2026-123633** 因允许攻击者针对标准 HTTP/2 部署实施未认证远程代码执行，引发了互联网安全中心（CIS Advisory `2026-136`）与 Wiz Research 的紧急预警。[6][7][8] - **CVE-2026-123007（潜伏 10 年的 HTTP/2 流量控制堆溢出）**：该漏洞自 2015 年 9 月 nginx 1.9.5 首次引入 `ngx_http_v2_module` 以来即已存在，可在任何启用 `http2` 的 server 块上通过单个 HTTP/2 TCP 连接触发。[4][6][8] 当数据帧处于排队状态时，攻击者通过发送精心构造的 HTTP/2 `SETTINGS`（`SETTINGS_INITIAL_WINDOW_SIZE`）与 `WINDOW_UPDATE` 帧，在 `send_window` 计数中引发整数下溢，从而导致 nginx 工作进程发生基于堆的缓冲区溢出。[4][6] - **CVE-2026-123633（HTTP/2 上游代理释放后使用）**：影响启用 HTTP/2 并将请求代理至上游后端（`proxy_pass`、`fastcgi_pass`、`uwsgi_pass`、`scgi_pass` 或 `grpc_pass`）的服务器，而这正是 Ingress 控制器、API 网关与反向代理的默认架构模式。[5][6] 攻击者通过建立并发连接，在上游连接建立阶段耗尽 `worker_connections`，即可在工作进程堆中触发释放后使用。[5][6]

通过对 nginx 内存池分配器（`ngx_pool_t`）进行堆布局操控，攻击者可以覆盖工作进程内存中的函数指针，从而以 nginx 工作进程用户权限执行任意代码。[6][8]

**修复与缓解措施**：管理员应升级至 **nginx 1.31.10+**（主线版）或 **nginx 1.30.8+**（稳定版），这两个版本同时包含 11 月 18 日的补丁（`1.31.9+` / `1.30.7+`）以及 11 月 23 日针对 `CVE-2026-132779` 的补丁。[2][3][7] 若无法立即升级，临时缓解措施包括在不可信监听端口上禁用 `http2`、`http3` 与 `ssl_early_data`，移除未使用的动态 `resolver` 配置块，并确保 nginx 工作进程以非特权账户而非 `root` 身份运行。[2][3][6][7]

## 常见问题

### 截至 2026 年 11 月 23 日，nginx 的最新版本是什么？

截至 2026 年 11 月 23 日，开源版 nginx 的最新版本为主线分支的 1.31.10（在 2026 年 11 月 23 日的 CHANGES 中发布）以及稳定分支的 1.30.8（在安全公告页面上与 1.31.10+ 一同列为不受 CVE-2026-132779 影响）。继 2026 年 11 月 18 日发布 1.31.9 与 1.30.7 修复 10 个 CVE 之后，此次版本修复了 CVE-2026-132779（TLS 1.3 启用 ssl_early_data 时导致 CPU 占用过高）。 [2][3]

### nginx 1.31.10 与 1.30.8 修复的 CVE-2026-132779 是什么漏洞？

CVE-2026-132779 是于 2026 年 11 月 23 日披露的中危漏洞，影响 nginx 1.21.4 至 1.31.9 版本。当启用 TLS 1.3 的 ssl_early_data 指令时，客户端可能借此触发过高的 CPU 占用。该漏洞已在 nginx 1.31.10+ 与 1.30.8+ 中修复。 [2][3]

### nginx 中的 CVE-2026-123007 与 CVE-2026-123633 是什么漏洞？

CVE-2026-123007 与 CVE-2026-123633 是由 Wiz Research 分析、并于 2026 年 11 月 18 日在 nginx 1.31.9 与 1.30.7 中修复的两项严重 HTTP/2 内存破坏漏洞（CVSS v4.0 评分 9.2 / CVSS v3.1 评分 8.1）。其中 CVE-2026-123007 是自 nginx 1.9.5 起潜伏达 10 年的 HTTP/2 send_window 流量控制整数下溢与堆缓冲区溢出漏洞，而 CVE-2026-123633 则是 HTTP/2 上游代理耗尽 worker_connections 时触发的释放后使用漏洞。 [2][4][5][6]

### nginx 的主线分支与稳定分支有什么区别？

nginx 主线分支（奇数次版本号，例如 1.31.x）接收所有新功能、缺陷修复与安全更新，是 nginx 团队推荐用于大多数部署环境的分支。稳定分支（偶数次版本号，例如 1.30.x）仅接收关键缺陷修复与安全补丁回移植，以保持第三方模块的兼容性。 [1][2]

### 如果管理员无法立即升级，如何缓解 2026 年 11 月的 nginx 漏洞？

唯一彻底的修复方式是升级至 nginx 1.31.10+ 或 1.30.8+。作为临时缓解措施，管理员可以在面向公网的监听端口上禁用 HTTP/2、HTTP/3 与 ssl_early_data，并确认 nginx 工作进程未配置为以 root 身份运行。 [2][3][6][7]

## 可引用的句子

- 2026 年 11 月 23 日，nginx 发布主线版本 1.31.10（security_advisories.html 将 1.31.10+ 与 1.30.8+ 列为不受影响版本），以修复在 TLS 1.3 中使用 ssl_early_data 时导致 CPU 占用过高的中危漏洞 CVE-2026-132779（影响 1.21.4-1.31.9）。 [2][3]
- nginx 于 2026 年 11 月 18 日发布主线版本 1.31.9 与稳定版本 1.30.7，在 1.31.9 中修复了 10 个安全漏洞（1.30.7 中修复了 9 个）。 [2][3]
- CVE-2026-123007 与 CVE-2026-123633 均为 HTTP/2 漏洞，在 NVD 中获得 CVSS v4.0 基础评分 9.2（严重）与 CVSS v3.1 评分 8.1（高危），并允许未认证远程代码执行。 [4][5][6]
- CVE-2026-123007 是 ngx_http_v2_module 中 send_window 处理逻辑的整数下溢与堆缓冲区溢出漏洞，影响 nginx 1.9.5 至 1.31.8 及 1.30.6 版本。 [2][4][6]
- nginx 最初由伊戈尔·瑟索耶夫于 2004 年 10 月 4 日以 2 条款 BSD 许可证发布，并自 2019 年 5 月起由 F5, Inc. 维护。 [1]

## 时间线

- 2004-10-04: 伊戈尔·瑟索耶夫以 2 条款 BSD 许可证公开发布 nginx 0.1.0。 [1]
- 2015-09: nginx 1.9.5 引入支持 HTTP/2 的 ngx_http_v2_module，其中包含后来被识别为 CVE-2026-123007 的潜在 send_window 逻辑。 [2][6]
- 2019-05: F5, Inc. 完成对 NGINX, Inc. 的收购。 [1]
- 2026-11-18: nginx 发布 1.31.9（主线版）与 1.30.7（稳定版），修复了包括 CVSS 9.2 的 HTTP/2 RCE 漏洞 CVE-2026-123007 与 CVE-2026-123633，以及 CVE-2026-121810、CVE-2026-123634、CVE-2026-113425 与 CVE-2026-125283 在内的 10 个 CVE。 [2][3][6]
- 2026-11-23: nginx 发布主线版本 1.31.10（并在 security_advisories.html 中将 1.31.10+ 与稳定版 1.30.8+ 列为不受影响），修复了 CVE-2026-132779（TLS 1.3 使用 ssl_early_data 时 CPU 占用过高）以及后端 SSL 连接 CPU 占用缺陷。 [2][3]

## 来源

1. nginx news and official project documentation. nginx.org / F5, Inc.. https://nginx.org/en/ (访问于 2026-11-23; tier 3: official site)
2. nginx security advisories. nginx.org. 发布于 2026-11-23. https://nginx.org/en/security_advisories.html (访问于 2026-11-23; tier 3: official site)
3. Changes with nginx 1.31.10 (23 Nov 2026) and 1.31.9 (18 Nov 2026). nginx.org. 发布于 2026-11-23. https://nginx.org/en/CHANGES (访问于 2026-11-23; tier 3: official site)
4. NVD - CVE-2026-123007 Detail (nginx HTTP/2 send_window integer underflow and heap-based buffer overflow). National Vulnerability Database (NIST). 发布于 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123007 (访问于 2026-11-23; tier 1: government or public registry)
5. NVD - CVE-2026-123633 Detail (nginx HTTP/2 upstream proxy worker_connections use-after-free). National Vulnerability Database (NIST). 发布于 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123633 (访问于 2026-11-23; tier 1: government or public registry)
6. Unauthenticated Remote Code Execution in NGINX: CVE-2026-123633 and CVE-2026-123007 | Wiz Blog. Wiz Research. 发布于 2026-11-18. https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities (访问于 2026-11-23; tier 3: official site)
7. Multiple Vulnerabilities in NGINX Could Allow for Remote Code Execution (CIS Advisory 2026-136). Center for Internet Security (CIS). 发布于 2026-11-19. https://www.cisecurity.org/advisory/multiple-vulnerabilities-in-nginx-could-allow-for-remote-code-execution_2026-136 (访问于 2026-11-23; tier 2: academic or news)
8. 10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers Execute Code on Servers. The Hacker News. 发布于 2026-11-19. https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "nginx." 版本 625385b5, 2026-11-23. https://mimirwiki.com/zh/wiki/nginx
