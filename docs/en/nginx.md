---
title: "nginx"
subtitle: "High-performance open-source asynchronous web server, reverse proxy, load balancer, and mail proxy"
canonical_url: https://mimirwiki.com/wiki/nginx
language: en
page_class: entity
revision_sha256: 83a52c6e1a639b47b7f7c9f5f75a81179c6f0d1b5ea7d2415d63603e3267038a
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/wiki/nginx.md
  txt: https://mimirwiki.com/wiki/nginx.txt
  json: https://mimirwiki.com/wiki/nginx.json
  jsonld: https://mimirwiki.com/wiki/nginx.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/nginx
---

# nginx

> As of November 23, 2026, the current open-source release branches are nginx 1.31.10 (mainline, released November 23, 2026) and nginx 1.30.8 (stable), which patched CVE-2026-132779 (a medium-severity vulnerability where using the ssl_early_data directive in TLS 1.3 could allow a client to cause excessive CPU usage). They followed the November 18, 2026 releases of nginx 1.31.9 (mainline) and 1.30.7 (stable), which patched 10 security vulnerabilities (9 affecting stable 1.30.7) led by two critical unauthenticated HTTP/2 remote code execution flaws rated CVSS v4.0 9.2 (Critical) / CVSS v3.1 8.1 (High): CVE-2026-123007 (a 10-year-old HTTP/2 send_window integer underflow and heap buffer overflow introduced in nginx 1.9.5) and CVE-2026-123633 (an HTTP/2 upstream proxy worker_connections use-after-free).

nginx (stylized as NGINX and pronounced 'engine-x') is an open-source, event-driven HTTP web server, reverse proxy, application load balancer, content cache, and mail proxy server originally created by Igor Sysoev and publicly released in October 2004. Distributed under the 2-clause BSD license and maintained by F5, Inc. since its 2019 acquisition of NGINX, Inc., nginx uses an asynchronous master-worker process architecture designed to handle tens of thousands of concurrent connections with minimal memory overhead.

**Also known as:** NGINX, Engine-X, NGINX Open Source, NGINX Plus

## Key facts

- **Original Author & Owner:** Igor Sysoev (2004); F5, Inc. (since May 2019) [1]
- **License:** 2-clause BSD License [1]
- **Latest Releases:** 1.31.10 (mainline, released Nov 23, 2026) and 1.30.8 (stable) (as of 2026-11-23) [2]
- **Nov 2026 Security Updates:** 1.31.10 / 1.30.8 fix CVE-2026-132779 (ssl_early_data CPU usage); 1.31.9 / 1.30.7 (Nov 18) fixed 10 CVEs including CVSS 9.2 HTTP/2 RCEs CVE-2026-123007 & CVE-2026-123633 (as of 2026-11-23) [3]

## Basic facts

- **Original Author:** Igor Sysoev [1]
- **Maintainer:** F5, Inc. (NGINX Product Group) [1]
- **Initial Public Release:** October 4, 2004 (version 0.1.0) [1]
- **Mainline Release (Nov 2026):** 1.31.10 (November 23, 2026) (as of 2026-11-23) [3]
- **Stable Release (Nov 2026):** 1.30.8 (listed as not vulnerable to CVE-2026-132779 alongside 1.31.10) (as of 2026-11-23) [2]
- **Written In:** C [1]
- **License:** 2-clause BSD License [1]
- **Supported Protocols:** HTTP/1.x, HTTP/2, HTTP/3 (QUIC), TLS/SSL, FastCGI, uwsgi, SCGI, gRPC, IMAP/POP3/SMTP, TCP/UDP [1]

## Overview and Asynchronous Event-Driven Architecture

nginx was engineered in 2002 by Russian software engineer Igor Sysoev to solve the **C10k problem** (handling 10,000+ simultaneous client connections on a single server) and was open-sourced under the 2-clause BSD license on October 4, 2004 [1]. Unlike traditional thread-per-connection or process-per-connection web servers, nginx employs a single privileged **master process** (responsible for reading configuration files, binding privileged ports, and managing worker lifecycles) and one or more unprivileged, single-threaded **worker processes** (plus optional cache loader and cache manager processes) [1].

Each worker process executes a non-blocking, asynchronous event loop backed by operating-system-specific kernel notification mechanisms (`epoll` on Linux, `kqueue` on FreeBSD and macOS, and event ports on Solaris) [1]. Because worker processes do not spawn new OS threads or block on disk or network I/O for each connection, nginx serves static assets, terminates TLS 1.3, multiplexes HTTP/2 and HTTP/3 (QUIC) streams, proxies gRPC and WebSocket traffic, and load-balances upstream application servers (`http`, `stream`, and `mail` contexts) with deterministic memory usage [1]. In May 2019, application delivery vendor **F5, Inc.** acquired NGINX, Inc., continuing development of both NGINX Open Source (`nginx.org`) and the commercial NGINX Plus distribution [1][2].

## Release Branches: Mainline 1.31.x and Stable 1.30.x

The nginx project maintains two concurrent open-source release branches on `nginx.org` [1][2]: - **Mainline branch** (odd minor version numbers, currently **1.31.x**, at **1.31.10** as of November 23, 2026): Receives all new features, protocol enhancements, bug fixes, and security patches [2][3]. - **Stable branch** (even minor version numbers, currently **1.30.x**, at **1.30.8** as of November 2026): Forked annually from the mainline branch; receives critical bug fixes and security backports without introducing backward-incompatible module API changes [1][2].

On **November 18, 2026**, the project released **nginx 1.31.9** and **nginx 1.30.7** to remediate a coordinated batch of 10 Common Vulnerabilities and Exposures (CVEs) in mainline 1.31.9 (9 of which also affected stable 1.30.x) spanning HTTP/2, HTTP/3, upstream proxy handling, the asynchronous DNS resolver, the mail proxy module, `try_files`/`alias` URI handling, and `stream` TLS/SNI processing [2][3]. Five days later, on **November 23, 2026**, the project released **nginx 1.31.10** (with the `nginx.org` security advisories page listing **1.31.10+** and **1.30.8+** as not vulnerable) to patch **CVE-2026-132779** (a medium-severity flaw affecting versions `1.21.4-1.31.9` where using the `ssl_early_data` directive in TLS 1.3 could allow a client to cause excessive CPU usage) and a bug where nginx might hog CPU if SSL connections to backends were used [2][3].

## November 2026 Security Advisories and HTTP/2 RCE Flaws

Across the November 18 and November 23, 2026 updates, the nginx project disclosed 11 vulnerabilities patched across the 1.31.x mainline and 1.30.x stable branches [2][3]. In the November 18 update (1.31.9 and 1.30.7), cloud security researchers at **Wiz Research** detailed two critical unauthenticated HTTP/2 remote code execution vulnerabilities - **CVE-2026-123007** and **CVE-2026-123633**, both assigned a **CVSS v4.0 base score of 9.2 (Critical)** and **CVSS v3.1 base score of 8.1 (High)** in the NIST National Vulnerability Database (NVD) and referred to in community advisories under the nicknames **nginx2root** / **nginx2shell** [4][5][6][8]:

| CVE Identifier | Affected Module & Versions | Vulnerability Mechanism | Severity / Patched In |
| --- | --- | --- | --- |
| **CVE-2026-132779** | TLS 1.3 `ssl_early_data` (nginx 1.21.4 - 1.31.9) | When using the `ssl_early_data` directive, a client might cause excessive CPU usage [2][3]. | Medium (`nginx.org`); fixed in 1.31.10+, 1.30.8+ |
| **CVE-2026-123007** | `ngx_http_v2_module` (nginx 1.9.5 - 1.31.8; 10-year-old flaw) | Integer underflow in HTTP/2 `send_window` flow-control accounting via crafted `SETTINGS` and `WINDOW_UPDATE` frames leads to heap-based buffer overflow (`CWE-191`, `CWE-122`) [2][4][6]. | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High; fixed in 1.31.9+, 1.30.7+ |
| **CVE-2026-123633** | `ngx_http_v2_module` + upstream proxy (1.19.7 - 1.31.8) | Use-after-free (`CWE-416`) triggered when an HTTP/2 client connection proxies to an upstream backend while `worker_connections` is exhausted [2][5][6]. | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High; fixed in 1.31.9+, 1.30.7+ |
| **CVE-2026-121810** | `ngx_http_v3_module` (1.25.0 - 1.31.8) | Use-after-free in HTTP/3 QUIC processing when `worker_connections` is exhausted [2][3]. | Medium (`nginx.org`); fixed in 1.31.9+, 1.30.7+ |
| **CVE-2026-123634** | Core asynchronous DNS `resolver` (0.6.18 - 1.31.8) | Use-after-free during simultaneous name resolution in subrequests when `resolver` is configured [2][3]. | Medium (`nginx.org`); fixed in 1.31.9+, 1.30.7+ |
| **CVE-2026-113425** | `ngx_mail_module` (0.5.33 - 1.31.8) | Use-after-free in the mail proxy server module [2][3]. | Major (`nginx.org`); fixed in 1.31.9+, 1.30.7+ |

The remaining five vulnerabilities patched on November 18, 2026 in nginx 1.31.9 (four in 1.30.7) are **CVE-2026-125283** (a buffer overflow when combining `try_files` and `alias` directives), **CVE-2026-120967** (SSL client certificate verification bypass via SNI in `stream` synchronous SSL handshakes), **CVE-2026-120993** (a worker NULL pointer dereference / segmentation fault in PROXY protocol v2 with dynamic SSL certificate loading, affecting mainline 1.31.4 - 1.31.8), **CVE-2026-123640** (insufficient validation of malformed ClientHello messages in `ngx_stream_ssl_preread_module`), and **CVE-2026-118899** (an endless worker process loop when reading client request bodies over SSL/TLS 1.3) [2][3].

The nginx change log credits CVE-2026-123007 to Xint.io and CVE-2026-123633 to Albert of Vexera AI [3].

## Technical Analysis of CVE-2026-123007 and CVE-2026-123633

Among the November 2026 advisories, **CVE-2026-123007** and **CVE-2026-123633** drew urgent warnings from the Center for Internet Security (CIS Advisory `2026-136`) and Wiz Research because they enable unauthenticated remote code execution against standard HTTP/2 deployments [6][7][8]: - **CVE-2026-123007 (10-Year-Old HTTP/2 Flow-Control Heap Overflow)**: Present since `ngx_http_v2_module` debuted in nginx 1.9.5 (September 2015), this flaw is triggered over a single HTTP/2 TCP connection on any server block with `http2` enabled [4][6][8]. By sending crafted HTTP/2 `SETTINGS` (`SETTINGS_INITIAL_WINDOW_SIZE`) and `WINDOW_UPDATE` frames while data frames are queued, an attacker causes an integer underflow in `send_window` accounting, leading to a heap-based buffer overflow in the nginx worker process [4][6]. - **CVE-2026-123633 (HTTP/2 Upstream Proxy Use-After-Free)**: Affects servers with HTTP/2 enabled that proxy requests to an upstream backend (`proxy_pass`, `fastcgi_pass`, `uwsgi_pass`, `scgi_pass`, or `grpc_pass`), a default pattern for ingress controllers, API gateways, and reverse proxies [5][6]. By opening concurrent connections to exhaust `worker_connections` during upstream connection setup, an attacker triggers a use-after-free in the worker process heap [5][6].

By grooming the nginx pool allocator (`ngx_pool_t`), an attacker can overwrite function pointers inside worker memory to execute arbitrary code with the privileges of the nginx worker user [6][8].

**Remediation**: Administrators should upgrade to **nginx 1.31.10+** (mainline) or **nginx 1.30.8+** (stable), which include both the November 18 fixes (`1.31.9+` / `1.30.7+`) and the November 23 `CVE-2026-132779` fix [2][3][7]. Where immediate upgrades are impossible, temporary workarounds include disabling `http2`, `http3`, and `ssl_early_data` on untrusted listeners, removing dynamic `resolver` blocks where unused, and ensuring nginx worker processes run under an unprivileged account rather than `root` [2][3][6][7].

## Frequently asked questions

### What are the latest versions of nginx as of November 23, 2026?

As of November 23, 2026, the latest open-source versions of nginx are 1.31.10 on the mainline branch (released November 23, 2026 in CHANGES) and 1.30.8 on the stable branch (listed as not vulnerable to CVE-2026-132779 alongside 1.31.10+ on the security advisories page). They patch CVE-2026-132779 (excessive CPU usage in TLS 1.3 with ssl_early_data) following the November 18, 2026 1.31.9 and 1.30.7 releases that fixed 10 CVEs. [2][3]

### What is CVE-2026-132779 in nginx 1.31.10 and 1.30.8?

CVE-2026-132779 is a medium-severity vulnerability disclosed on November 23, 2026 affecting nginx 1.21.4 through 1.31.9 where enabling the TLS 1.3 ssl_early_data directive could allow a client to trigger excessive CPU usage. It is resolved in nginx 1.31.10+ and 1.30.8+. [2][3]

### What are CVE-2026-123007 and CVE-2026-123633 in nginx?

CVE-2026-123007 and CVE-2026-123633 are two critical HTTP/2 memory-corruption vulnerabilities (CVSS v4.0 score 9.2 / CVSS v3.1 score 8.1) analyzed by Wiz Research and patched in nginx 1.31.9 and 1.30.7 on November 18, 2026. CVE-2026-123007 is a 10-year-old integer underflow and heap buffer overflow in HTTP/2 send_window flow-control handling (present since nginx 1.9.5), while CVE-2026-123633 is a use-after-free triggered when HTTP/2 upstream proxying exhausts worker_connections. [2][4][5][6]

### What is the difference between the nginx mainline and stable branches?

The nginx mainline branch (odd minor versions, such as 1.31.x) receives all new features, bug fixes, and security updates and is recommended by the nginx team for most deployments. The stable branch (even minor versions, such as 1.30.x) only receives critical bug fixes and security backports to preserve third-party module compatibility. [1][2]

### How can administrators mitigate the November 2026 nginx vulnerabilities if they cannot upgrade immediately?

The only complete fix is upgrading to nginx 1.31.10+ or 1.30.8+. As a temporary workaround, administrators can disable HTTP/2, HTTP/3, and ssl_early_data on public-facing listeners and verify that nginx worker processes are not configured to run as root. [2][3][6][7]

## Quotable sentences

- On November 23, 2026, nginx released mainline version 1.31.10 (with security_advisories.html listing 1.31.10+ and 1.30.8+ as not vulnerable) to fix CVE-2026-132779, a medium-severity excessive CPU usage flaw when using ssl_early_data in TLS 1.3 (affecting 1.21.4-1.31.9). [2][3]
- nginx released mainline version 1.31.9 and stable version 1.30.7 on November 18, 2026, patching 10 security vulnerabilities in 1.31.9 (9 in 1.30.7). [2][3]
- CVE-2026-123007 and CVE-2026-123633 are HTTP/2 vulnerabilities that carry a CVSS v4.0 base score of 9.2 (Critical) and CVSS v3.1 score of 8.1 (High) in NVD and allow unauthenticated remote code execution. [4][5][6]
- CVE-2026-123007 is an integer underflow and heap buffer overflow in ngx_http_v2_module send_window handling that affected nginx versions 1.9.5 through 1.31.8 and 1.30.6. [2][4][6]
- nginx was originally released by Igor Sysoev on October 4, 2004 under the 2-clause BSD license and has been maintained by F5, Inc. since May 2019. [1]

## Timeline

- 2004-10-04: Igor Sysoev releases nginx 0.1.0 publicly under the 2-clause BSD license. [1]
- 2015-09: nginx 1.9.5 introduces ngx_http_v2_module for HTTP/2 support, containing the latent send_window logic later identified as CVE-2026-123007. [2][6]
- 2019-05: F5, Inc. completes the acquisition of NGINX, Inc. [1]
- 2026-11-18: nginx releases 1.31.9 (mainline) and 1.30.7 (stable), patching 10 CVEs including the CVSS 9.2 HTTP/2 RCE flaws CVE-2026-123007 and CVE-2026-123633 alongside CVE-2026-121810, CVE-2026-123634, CVE-2026-113425, and CVE-2026-125283. [2][3][6]
- 2026-11-23: nginx releases mainline version 1.31.10 (and lists 1.31.10+ and stable 1.30.8+ as not vulnerable on security_advisories.html), patching CVE-2026-132779 (excessive CPU usage in TLS 1.3 when using ssl_early_data) and a backend SSL connection CPU usage bug. [2][3]

## Sources

1. nginx news and official project documentation. nginx.org / F5, Inc.. https://nginx.org/en/ (checked 2026-11-23; tier 3: official site)
2. nginx security advisories. nginx.org. published 2026-11-23. https://nginx.org/en/security_advisories.html (checked 2026-11-23; tier 3: official site)
3. Changes with nginx 1.31.10 (23 Nov 2026) and 1.31.9 (18 Nov 2026). nginx.org. published 2026-11-23. https://nginx.org/en/CHANGES (checked 2026-11-23; tier 3: official site)
4. NVD - CVE-2026-123007 Detail (nginx HTTP/2 send_window integer underflow and heap-based buffer overflow). National Vulnerability Database (NIST). published 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123007 (checked 2026-11-23; tier 1: government or public registry)
5. NVD - CVE-2026-123633 Detail (nginx HTTP/2 upstream proxy worker_connections use-after-free). National Vulnerability Database (NIST). published 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123633 (checked 2026-11-23; tier 1: government or public registry)
6. Unauthenticated Remote Code Execution in NGINX: CVE-2026-123633 and CVE-2026-123007 | Wiz Blog. Wiz Research. published 2026-11-18. https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities (checked 2026-11-23; tier 3: official site)
7. Multiple Vulnerabilities in NGINX Could Allow for Remote Code Execution (CIS Advisory 2026-136). Center for Internet Security (CIS). published 2026-11-19. https://www.cisecurity.org/advisory/multiple-vulnerabilities-in-nginx-could-allow-for-remote-code-execution_2026-136 (checked 2026-11-23; tier 2: academic or news)
8. 10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers Execute Code on Servers. The Hacker News. published 2026-11-19. https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "nginx." Version 83a52c6e, 2026-11-23. https://mimirwiki.com/wiki/nginx
