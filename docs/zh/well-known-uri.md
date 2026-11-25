---
title: "Well-Known URI"
subtitle: "保留 /.well-known/ 路径前缀用于源级元数据与服务发现的 IETF 标准"
canonical_url: https://mimirwiki.com/zh/wiki/well-known-uri
language: zh
page_class: anchor
revision_sha256: 5aa19c3e4af1e721c39f7c1c3b2137d813eb17a9e2f68c3ea90fa024ae54990d
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/well-known-uri.md
  txt: https://mimirwiki.com/zh/wiki/well-known-uri.txt
  json: https://mimirwiki.com/zh/wiki/well-known-uri.json
  jsonld: https://mimirwiki.com/zh/wiki/well-known-uri.jsonld
translations:
  en: https://mimirwiki.com/wiki/well-known-uri
  ko: https://mimirwiki.com/ko/wiki/well-known-uri
  ja: https://mimirwiki.com/ja/wiki/well-known-uri
  es: https://mimirwiki.com/es/wiki/well-known-uri
---

# Well-Known URI

> Well-Known URI 是路径以 /.well-known/ 开头、用于源级元数据和服务发现的统一资源标识符。该标准由 2019 年 5 月发布的 IETF RFC 8615 规范定义，废止了 RFC 5785，适用于 HTTP、HTTPS、WS 和 WSS。IANA 按“需要规范”（Specification Required）策略维护相关注册表，收录了 security.txt、acme-challenge 和 openid-configuration 等后缀。

Well-Known URI 是在明确定义支持该机制的 URI 方案（包括 HTTP、HTTPS、WS 和 WSS）上，路径组件以保留前缀 /.well-known/ 开头的统一资源标识符（URI）。该规范由互联网工程任务组（IETF）于 2019 年 5 月作为 RFC 8615 发布，废止了 RFC 5785（2010 年 4 月），为源级元数据和协议发现标准化了一个可预测的位置，同时避免路径冲突。互联网号码分配机构（IANA）依据包含指定专家（Designated Expert）评审的“需要规范”（Specification Required）策略维护 Well-Known URIs 注册表，列出了 security.txt、acme-challenge、oauth-authorization-server、oauth-protected-resource 和 openid-configuration 等 permanent 与 provisional 后缀。Well-Known URI 仅适用于源路径层级的顶层，具体应用自行定义其元数据格式、媒体类型和作用域。

**别名:** Well-Known URIs, 知名 URI, /.well-known/, Well-Known Uniform Resource Identifiers, RFC 8615, RFC 5785, .well-known

## 关键事实

- **现行规范:** RFC 8615（2019 年 5 月，标准轨道） (截至 2026-11-23) [1]
- **保留路径前缀:** 位于源根目录的 /.well-known/ [1]
- **先前规范:** RFC 5785（2010 年 4 月，已被 RFC 8615 废止） [2]
- **注册表:** IANA Well-Known URIs（创建于 2010-01-20，更新于 2026-10-26） (截至 2026-11-23) [3]
- **注册策略:** 含指定专家评审的“需要规范”策略（RFC 8126） [1]

## 事实摘要

- **类型:** 关于保留 URI 路径前缀的互联网标准 [1]
- **路径前缀:** /.well-known/ [1]
- **现行规范:** RFC 8615（2019 年 5 月，标准轨道） (截至 2026-11-23) [1]
- **作者（RFC 8615）:** Mark Nottingham [1]
- **废止规范:** RFC 5785（2010 年 4 月，Mark Nottingham 与 E. Hammer-Lahav） [2]
- **更新规范:** RFC 7230 与 RFC 7595 [1]
- **支持的 URI 方案:** http、https、ws、wss 及其他明确定义支持该机制的方案 [1]
- **注册表:** IANA Well-Known URIs（iana.org/assignments/well-known-uris） [3]
- **注册表状态:** 创建于 2010-01-20；最近更新于 2026-10-26 (截至 2026-11-23) [3]
- **注册策略:** 需要规范（Specification Required） [3]
- **指定专家:** Mark Nottingham (截至 2026-11-23) [3]
- **后缀语法:** RFC 3986 segment-nz（不含 / 字符） [1]

## 什么是 Well-Known URI

Well-Known URI 是在明确定义支持该机制的 URI 方案中，路径组件以 `/.well-known/` 开头的统一资源标识符。[1] 互联网工程任务组（IETF）于 2019 年 5 月发布了由 Mark Nottingham 撰写的现行标准轨道（Standards Track）规范 RFC 8615。[1] RFC 8615 废止了 Mark Nottingham 与 E. Hammer-Lahav 于 2010 年 4 月发布的 RFC 5785，后者最初确立了 `/.well-known/` 路径前缀及互联网号码分配机构（IANA）注册表。[1][2] RFC 8615 还更新了 RFC 7230 以在 `http` 和 `https` URI 中保留该前缀，并更新了 RFC 7595 以使 IANA URI Schemes 注册表记录支持 Well-Known URI 的方案。[1]

Web 应用程序经常需要在发起请求前发现关于某个源的站点级元数据，例如[机器人排除协议](https://mimirwiki.com/zh/wiki/robots-txt)（Robots Exclusion Protocol）和隐私偏好平台（P3P）。[1][2] 在这些场景下，HTTP 标头字段或 WebDAV PROPFIND 等按资源提供的元数据机制可能会增加客户端感知延迟或带来部署困难。[1][2] HTTP 也常被用作非 Web 协议的传输基础，而这些协议同样需要在主机上定位资源。[1] 在站点根目录指定任意固定路径不仅存在与其他协议位置或源自身所建资源发生冲突的风险，还会侵占源对自身 URI 空间的控制权。[1]

保留单一的 `/.well-known/` 前缀能够隔离协议定义的发现位置，并要求各规范通过 IANA 注册后缀以防止命名冲突。[1][2] 除 `http` 和 `https` 外，RFC 8615 还为经 RFC 8307 更新的 WebSocket（`ws`）和安全 WebSocket（`wss`）URI 保留了 `/.well-known/`，并允许其他 URI 方案在其方案定义明确允许时采用 Well-Known URI。[1] RFC 5785 指出，Well-Known URI 旨在解决多次往返或逐资源检查不切实际的问题，用于直接公开或链接到站点级策略信息与元数据，而通用信息检索与大型 URI 命名空间不在其预期范围内。[2]

## Well-Known URI 语法与作用域规则

Well-Known URI 遵循 RFC 8615 定义的严格语法和结构约束。[1] 对于在 `http://www.example.com/` 上注册了后缀 `example` 的应用程序，其对应的 Well-Known URI 为 `http://www.example.com/.well-known/example`。[1] 每个已注册的后缀都必须符合 RFC 3986 中的 `segment-nz` 产生式，该规则禁止注册名称本身包含 `/` 字符。[1] RFC 8615 建议应用程序选择精确的名称，不鼓励注册通用词汇，并给出了 `example-metadata` 或 `example.com-metadata` 等优于 `metadata` 的推荐示例。[1]

注册项必须引用一份规范，该规范需定义解引用该 URI 所获取资源的格式、关联媒体类型以及适用的 URI 方案。[1] 若注册未明确列出 URI 方案，则默认适用 `http` 和 `https`。[1] 除非规范明确指定替代端口，否则应用程序使用该方案的默认端口。[1] 注册项还可以定义附加路径组件、查询字符串、片段标识符的语法，或 HTTP 方法处理等特定协议行为。[1]

RFC 8615 未定义基础路径 `/.well-known/` 本身的格式和媒体类型，客户端不应假定该位置存在资源。[1] Well-Known URI 严格位于 URI 路径层级的顶层。例如，从根目录开始的 `/.well-known/example` 属于 Well-Known URI，而 `/foo/.well-known/example` 这样的嵌套路径则不属于。[1] RFC 8615 将主机名确定方式以及从 Well-Known URI 获取的元数据作用域留给各应用程序规范自行定义。[1]

## IANA Well-Known URIs 注册表与注册策略

应用程序在 `/.well-known/` 下启用新后缀之前，必须先在 IANA Well-Known URIs 注册表中进行注册。[1] 该注册表由 RFC 5785 建立并于 2010-01-20 创建，由 IANA 负责维护；IANA 根据与 ICANN 签订的合同协调 IETF 协议参数命名空间，以防止分配冲突并支持互操作性。[2][3][8] 截至 2026-11-23，注册表页面记录的最近更新日期为 2026-10-26，指定专家列为 Mark Nottingham，并提供 XML、HTML、TXT 和 CSV 格式下载。[3]

根据 RFC 8615，注册遵循 RFC 8126（BCP 26，2017 年 6 月发布，废止了 RFC 5226）定义的“需要规范”（Specification Required）策略，并需依据一名或多名指定专家（Designated Expert）的建议予以批准。[1][3][8] 申请可通过 IANA 注册表界面或发送电子邮件至 `wellknown-uri-review@ietf.org` 邮件列表提交。[1][3] RFC 5785 最初建立评审流程时，曾为指定专家设定了 14 天的评审目标期限，并允许将超过 21 天仍未解决的申请升级至互联网工程指导组（IESG，邮箱 `iesg@iesg.org`）。[2]

RFC 8615 要求每份注册申请提供四个必填字段以及可选的相关信息。[1]

- **URI suffix**：相对于 `/.well-known/` 的名称
- **Change controller**：标准轨道 RFC 为 `IETF`，其他规范为对应责任方
- **Specification document(s)**：指向定义规范的引用，最好附带可获取的 URI
- **Status**：`permanent` 或 `provisional`
- **Related information**（可选）：其他文档的引用

RFC 8615 在 RFC 5785 最初定义的四字段模板基础上增加了状态区分。[1][2] 由标准轨道 RFC 及其他开放标准（依据 RFC 2026 第 7.1.1 节）定义的值将获得 `permanent` 状态；专家在咨询负责该 URI 方案的社区（通常是相关工作组邮件列表或 `art@ietf.org`）后，也可向已在实际使用中的其他值授予 `permanent` 状态。[1] 其余条目获得 `provisional` 状态，专家随后可根据采用情况将其提升为 `permanent`，或在咨询社区后移除未使用的条目。[1] 只要存在参考规范，专家或其他第三方也可以注册已被广泛部署但尚未注册的后缀。[1] 截至 2026-10-26，IANA 注册表还将已退役的条目标记为 `deprecated`（例如 `privacy-sandbox-attestations.json`、`related-website-set.json` 和 `tpcd`）或 `obsoleted`（例如 `http-opportunistic` 和 `mud`）。[3]

## 主要的已注册 Well-Known URI 后缀

Well-Known URI 在 IETF、W3C、OpenID Foundation、OASIS 和 ETSI 等标准组织中广泛用于支持安全披露、自动证书签发、身份与授权元数据以及协议发现。[3] IANA 注册表中的五个 permanent 后缀涵盖了安全披露、证书自动化以及身份或授权发现。[3]

| URI 后缀 | 定义规范 | 状态 | 变更控制者 | 注册日期 |
| --- | --- | --- | --- | --- |
| `openid-configuration` | OpenID Connect Discovery 1.0 | permanent | OpenID Foundation Artifact Binding Working Group | 2013-08-27 |
| `acme-challenge` | RFC 8555, Section 8.3 | permanent | IETF | 2016-08-18 |
| `oauth-authorization-server` | RFC 8414, Section 3 | permanent | IESG | 2018-03-27 |
| `security.txt` | RFC 9116 | permanent | IETF | 2021-07-13 |
| `oauth-protected-resource` | RFC 9728, Section 3 | permanent | IETF | 2024-10-22 |

`security.txt` 由 E. Foudil 和 Y. Shafranovich 在 RFC 9116（信息类，2022 年 4 月）中规定，定义了一种机器可解析的纯文本文件，供组织向安全研究人员发布漏洞披露规范和报告渠道。[4] 该格式使用按行排列的键值对字段（包括 `Contact`、`Expires`、`Encryption`、`Canonical`、`Policy`、`Acknowledgments`、`Preferred-Languages` 和 `Hiring`），支持 `#` 注释，并建议使用 OpenPGP 明文签名（RFC 4880）配合 `Canonical` 字段来验证文件位置的真实性。[4]

`acme-challenge` 依据 RFC 8555（标准轨道，2019 年 3 月）注册，支持自动证书管理环境（ACME）协议定义的 HTTP 质询。[3][5] ACME 在证书颁发机构与申请者之间实现了域名验证（DV）X.509 证书的域名控制权校验以及证书签发与吊销的自动化，取代了临时性的手动验证步骤。[5]

另有三个相关后缀服务于 [OAuth](https://mimirwiki.com/zh/wiki/oauth) 2.0 和 OpenID Connect 的发现机制。`openid-configuration` 由 OpenID Connect Discovery 1.0（2014 年 2 月定稿，2023-12-15 发布第 2 版勘误）定义，公开包含 OpenID 提供商配置及 OAuth 2.0 端点位置的 JSON 文档，并可选择先通过 WebFinger（RFC 7033）执行签发者发现。[3][9] `oauth-authorization-server` 由 RFC 8414（标准轨道，2018 年 6 月）规定，将该 JSON 元数据格式推广至 OAuth 2.0 授权服务器，通过 HTTPS 或在签名的 JSON Web Token（JWT）内通告 `issuer`、`authorization_endpoint`、`token_endpoint`、`jwks_uri`、`scopes_supported` 和 `response_types_supported` 等字段。[3][6] `oauth-protected-resource` 由 RFC 9728（标准轨道，2025 年 4 月）规定，为 OAuth 2.0 受保护资源提供并行的 JSON 元数据文档（通告 `resource`、`authorization_servers`、`jwks_uri`、`scopes_supported` 和 `bearer_methods_supported`），其路径由各资源标识符确定性推导而来，并允许资源服务器通过 `WWW-Authenticate` 标头通告元数据 URL。[3][7]

截至 2026-10-26，IANA 注册表还包含 `webfinger`（RFC 7033）、`caldav` 与 `carddav`（RFC 6764）、`host-meta` 与 `host-meta.json`（RFC 6415）、`assetlinks.json`（Google Inc.）、`pki-validation`（CA/Browser Forum）、`mta-sts.txt`（RFC 8461）、`jmap`（RFC 8620）、`sbom`（RFC 9472）、`api-catalog`（RFC 9727）、`agent-card.json`（Linux Foundation）和 `webauthn`（W3C）等 permanent 条目，以及 `gpc.json`、`change-password`、`did.json` 和 `tdmrep.json` 等 provisional 条目。[3]

## Well-Known URI 的安全考量

由于 `/.well-known/` 下的资源实际上代表整个源，Well-Known URI 为协议设计者和服务器运维人员都带来了安全考量。[1] RFC 8615 列出了常见威胁，包括敏感数据泄露、拒绝服务攻击、服务器与客户端身份验证失败、DNS 重绑定攻击，以及攻击者利用受限的服务器访问权限篡改 Well-Known URI 响应方式的场景。[1] 服务器运维人员必须通过服务器配置和本地文件系统权限双重途径限制对 Well-Known 位置的写入权限，在多个实体共存的共享源上尤其如此。[1] RFC 8615 还指出，隐藏以点号开头目录的操作系统可能会掩盖 `.well-known` 目录内未经授权的修改，使管理员难以察觉。[1]

对于 `http` 和 `https` URI，Well-Known 资源可被 Web 浏览器访问，并与 Cookie（RFC 6265）、Web Storage 以及从同源其他路径加载的脚本共享同一源安全边界。[1] 在该源其他位置利用跨站脚本（XSS）漏洞的攻击者可以向 Well-Known 资源发起任意请求。[1] RFC 8615 针对浏览器可访问的 Well-Known 端点列出了以下缓解措施与实践建议。[1]

- 加密敏感信息，并对身份验证令牌或密码等敏感值避免压缩，以防止基于浏览器的压缩探测
- 使用灵活的标识符（如 Cookie 名称）以避免与同源上的其他应用程序发生冲突，并设置 `HttpOnly` 和 `Path` Cookie 属性
- 发送 `X-Content-Type-Options: nosniff`，强制使用特定于应用程序的 `Content-Type` 媒体类型，并应用 `Content-Security-Policy` 和 `Referrer-Policy` 标头

应用程序规范必须明确定义发现规则和元数据作用域，以防止跨源边界混淆。[1] RFC 8615 警告称，将来自 `https://example.com/.well-known/example` 的元数据应用于另一主机或端口（如 `https://department.example.com`、`https://www.example.com` 或 `https://www.example.com:8000`）会假定一种可能并不存在的管理关系，从而可能将控制权交给攻击者。[1] 同样，使用某主机名上的 Well-Known HTTPS URI 来引导电子邮件等独立服务，可能会向未实现该 URI 的 Web 服务器发送大量无用 HTTP 请求，形成类似拒绝服务攻击的效应。[1]

## Well-Known URI 的源根目录限制与 llms.txt

根据 RFC 8615，Well-Known URI 严格绑定在源路径层级的根目录，这意味着 `/foo/.well-known/example` 之类的嵌套路径不属于 Well-Known URI。[1] 这种源级约束与 `/robots.txt` 和 `/sitemap.xml`（参见[站点地图](https://mimirwiki.com/zh/wiki/sitemaps)）等全站发现文件保持一致，但对于需要按目录提供元数据或在共享主机上发布的约定而言，却带来了实际限制。[1][10]

由 Jeremy Howard 于 2024-09-03 发布并于 2026-08-10 修订为 v2 的 [llms.txt](https://mimirwiki.com/zh/wiki/llms-txt) 提案体现了这一架构权衡。[10] llms.txt 规定在站点根目录（`/llms.txt`）或任意子路径（例如 `/docs/llms.txt`）放置名为 `llms.txt` 的 Markdown 概览文件，每个文件覆盖其所在目录下的 URL，当存在多个文件时，代理应用路径最具体的那个文件。[10] 在程序化发现方面，llms.txt v2 建议通过 HTML `link` 元素或 HTTP `Link` 标头传递标准链接关系（用于 Markdown 页面版本的 `rel="alternate"` 配合 `type="text/markdown"`，以及指向所属 `llms.txt` 文件的 `rel="describedby"`）。[10]

在讨论现有标准时，llms.txt 规范明确将其子路径模型与 RFC 8615 的 Well-Known URI 进行了对比。[10] 由于 Well-Known URI 仅存在于源根目录，在共享主机（如 GitHub Pages 项目站点）上仅控制子目录的作者虽然可以在自己的目录中发布文件，却无法向主机的 `/.well-known/` 空间添加条目。[10] 通过在任意路径像 `index.html` 一样运作，`llms.txt` 让任何对某路径拥有写权限的发布者都能描述站点的这一特定区域，实现了单一源根目录位置无法表达的按路径作用域。[10]

## 常见问题

### 什么是 Well-Known URI？

Well-Known URI 是在明确定义支持该机制的 URI 方案（例如 HTTP、HTTPS、WS 和 WSS）中，路径以 /.well-known/ 开头的统一资源标识符。它由 IETF RFC 8615 规范定义，为源级元数据和服务的发现提供了标准化位置，同时避免与源自身的 URI 空间发生冲突。 [1]

### RFC 8615 与 RFC 5785 有何区别？

RFC 8615（2019 年 5 月）废止了 RFC 5785（2010 年 4 月），针对 http 和 https 方案更新了 RFC 7230，并更新了 RFC 7595 以使 IANA URI Schemes 注册表能够记录支持 Well-Known URI 的方案。它还新增了 permanent 和 provisional 两种注册状态，明确规定了源根目录路径限制，并扩展了关于浏览器交互、作用域和隐藏目录的安全指南。 [1][2]

### 如何注册新的 Well-Known URI 后缀？

应用程序必须依据 RFC 8126 的“需要规范”（Specification Required）策略，经指定专家评审后在 IANA Well-Known URIs 注册表中注册新后缀。申请通过 IANA 注册表界面或 wellknown-uri-review@ietf.org 邮件列表提交，且必须包含 URI 后缀、变更控制者、定义规范文档以及 permanent 或 provisional 状态。 [1][3][8]

### 有哪些值得关注的已注册 Well-Known URI 后缀？

IANA 注册表中的主要 permanent 后缀包括：用于漏洞披露的 security.txt（RFC 9116）、用于证书签发中自动域名验证的 acme-challenge（RFC 8555）、用于 OAuth 2.0 元数据的 oauth-authorization-server（RFC 8414）和 oauth-protected-resource（RFC 9728），以及用于 OpenID Connect Discovery 1.0 的 openid-configuration。 [3][4][5][6][7][9]

### 能否将 Well-Known URI 放置在 /app/.well-known/ 之类的子目录中？

不可以。根据 RFC 8615，Well-Known URI 严格位于路径层级的顶层，因此 /.well-known/example 属于 Well-Known URI，而 /foo/.well-known/example 这类嵌套路径则不属于。 [1]

### 为什么 llms.txt 提案将文件放在 /.well-known/ 之外？

llms.txt 规范指出，RFC 8615 将 Well-Known URI 限制在源根目录，这使得在 GitHub Pages 等共享主机上仅控制子目录的作者无法在 /.well-known/ 下发布文件。将 llms.txt 置于根目录或任意子路径，可以让每个文件像 index.html 一样描述其所在目录。 [1][10]

## 可引用的句子

- 由 Mark Nottingham 撰写并于 2019 年 5 月发布的 IETF RFC 8615 定义了 /.well-known/ 路径前缀，并废止了 RFC 5785。 [1][2]
- RFC 8615 在 HTTP、HTTPS、WS 和 WSS URI 中保留了 /.well-known/，并更新了 RFC 7230 和 RFC 7595。 [1]
- Well-Known URI 仅限于源路径层级的顶层，且注册后缀必须符合 RFC 3986 的 segment-nz 语法，不得包含斜杠字符。 [1]
- IANA Well-Known URIs 注册表创建于 2010-01-20，依据 RFC 8126 的“需要规范”（Specification Required）策略并结合指定专家评审机制运行。 [1][3][8]
- 截至 2026-11-23，IANA Well-Known URIs 注册表将其最近更新日期列为 2026-10-26，并将 Mark Nottingham 列为指定专家。 [3]
- security.txt 后缀（RFC 9116）于 2021-07-13 注册为 permanent，acme-challenge 后缀（RFC 8555 第 8.3 节）于 2016-08-18 注册为 permanent。 [3][4][5]
- IANA 注册表记录了 openid-configuration（2013-08-27）、oauth-authorization-server（2018-03-27，RFC 8414）和 oauth-protected-resource（2024-10-22，RFC 9728）等 permanent 后缀。 [3][6][7][9]
- llms.txt 提案未采用 /.well-known/ 前缀，因为 Well-Known URI 仅存在于源根目录，在共享主机上仅控制子路径的作者无法发布此类文件。 [1][10]

## 时间线

- 2010-01-20: IANA 创建 Well-Known URIs 注册表。 [3]
- 2010-04: IETF 发布由 Mark Nottingham 和 E. Hammer-Lahav 撰写的 RFC 5785，定义 /.well-known/ 路径前缀和注册流程。 [2]
- 2013-08-27: openid-configuration 后缀在 IANA Well-Known URIs 注册表中注册为 permanent。 [3][9]
- 2016-08-18: 用于 ACME HTTP 域名验证的 acme-challenge 后缀在 IANA 注册表中注册为 permanent。 [3][5]
- 2017-06: IETF 发布 RFC 8126（BCP 26），更新包含“需要规范”策略在内的 IANA 注册表策略框架。 [8]
- 2018-06: 继 2018-03-27 注册 oauth-authorization-server 后，IETF 发布面向 OAuth 2.0 授权服务器元数据的 RFC 8414。 [3][6]
- 2019-03: IETF 发布规定自动证书管理环境（ACME）协议的 RFC 8555。 [5]
- 2019-05: IETF 发布 Mark Nottingham 撰写的 RFC 8615，废止 RFC 5785 并更新 RFC 7230 和 RFC 7595。 [1]
- 2022-04: 继 2021-07-13 注册 security.txt 后，IETF 发布定义 security.txt 漏洞披露格式的 RFC 9116。 [3][4]
- 2025-04: 继 2024-10-22 注册 oauth-protected-resource 后，IETF 发布面向 OAuth 2.0 受保护资源元数据的 RFC 9728。 [3][7]
- 2026-10-26: IANA 记录截至 2026-11-23 的 Well-Known URIs 注册表最近一次更新。 [3]

## 来源

1. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 发布于 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (访问于 2026-11-23; tier 1: government or public registry)
2. RFC 5785: Defining Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 发布于 2010-04. https://www.rfc-editor.org/rfc/rfc5785.txt (访问于 2026-11-23; tier 1: government or public registry)
3. Well-Known URIs. Internet Assigned Numbers Authority (IANA). 发布于 2026-10-26. https://www.iana.org/assignments/well-known-uris (访问于 2026-11-23; tier 1: government or public registry)
4. RFC 9116: A File Format to Aid in Security Vulnerability Disclosure. Internet Engineering Task Force (IETF). 发布于 2022-04. https://www.rfc-editor.org/rfc/rfc9116.txt (访问于 2026-11-23; tier 1: government or public registry)
5. RFC 8555: Automatic Certificate Management Environment (ACME). Internet Engineering Task Force (IETF). 发布于 2019-03. https://www.rfc-editor.org/rfc/rfc8555.txt (访问于 2026-11-23; tier 1: government or public registry)
6. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 发布于 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (访问于 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 发布于 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (访问于 2026-11-23; tier 1: government or public registry)
8. RFC 8126: Guidelines for Writing an IANA Considerations Section in RFCs. Internet Engineering Task Force (IETF). 发布于 2017-06. https://www.rfc-editor.org/rfc/rfc8126.txt (访问于 2026-11-23; tier 1: government or public registry)
9. Final: OpenID Connect Discovery 1.0 incorporating errata set 2. OpenID Foundation. 发布于 2023-12-15. https://openid.net/specs/openid-connect-discovery-1_0.html (访问于 2026-11-23; tier 3: official site)
10. The /llms.txt file, v2 – llms-txt. llmstxt.org. 发布于 2024-09-03. https://llmstxt.org/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Well-Known URI." 版本 5aa19c3e, 2026-11-23. https://mimirwiki.com/zh/wiki/well-known-uri
