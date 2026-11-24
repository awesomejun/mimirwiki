---
title: "OAuth"
subtitle: "由 IETF 标准化的开放授权框架，用于借助访问令牌实现 HTTP 资源的委托访问"
canonical_url: https://mimirwiki.com/zh/wiki/oauth
language: zh
page_class: anchor
revision_sha256: b3da649253c6eb259c685c1e32de3bc7121122ec0ad336252dcdf90164c6fbfb
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/oauth.md
  txt: https://mimirwiki.com/zh/wiki/oauth.txt
  json: https://mimirwiki.com/zh/wiki/oauth.json
  jsonld: https://mimirwiki.com/zh/wiki/oauth.jsonld
translations:
  en: https://mimirwiki.com/wiki/oauth
  ko: https://mimirwiki.com/ko/wiki/oauth
  ja: https://mimirwiki.com/ja/wiki/oauth
---

# OAuth

> OAuth 是 IETF 制定的授权框架，使应用程序能够在不获取资源所有者凭据的情况下，凭授权服务器颁发的访问令牌访问 HTTP 资源。OAuth 2.0 于 2012 年 10 月通过 RFC 6749 发布，并于 2025 年 1 月由 RFC 9700 更新，广泛用于 OpenID Connect 和模型上下文协议的授权机制。

OAuth 是面向 HTTP 服务的开放授权框架，允许第三方应用程序使用访问令牌，代表资源所有者或以其自身名义有限地访问受保护资源。该协议最初于 2007 年 10 月作为社区规范稳定下来，并于 2010 年 4 月在 RFC 5849 中记录为 OAuth 1.0；随后于 2012 年 10 月在 IETF 标准轨道上被 RFC 6749 和 RFC 6750 定义的 OAuth 2.0 取代。此后，IETF 相继发布了代码交换证明密钥（RFC 7636）、授权服务器元数据（RFC 8414）、OAuth 2.0 安全当前最佳实践（RFC 9700，BCP 240）和受保护资源元数据（RFC 9728）等规范以扩展 OAuth 2.0。截至 2026-11-23，IETF OAuth 工作组正在制定 OAuth 2.1（draft-ietf-oauth-v2-1-17），将 OAuth 2.0 及其后续安全要求整合为单一规范。

**别名:** OAuth 2.0, OAuth 2.1, OAuth 1.0, OAuth 2.0 授权框架, RFC 6749

## 关键事实

- **标准组织:** 互联网工程任务组（IETF）OAuth 工作组 [8]
- **核心规范:** RFC 6749（OAuth 2.0，2012 年 10 月） [1]
- **安全 BCP:** RFC 9700 / BCP 240（2025 年 1 月） [6]
- **角色:** 资源所有者、资源服务器、客户端、授权服务器 [1]
- **OAuth 2.1 草案状态:** draft-ietf-oauth-v2-1-17（活跃互联网草案，2026-10-30 更新） (截至 2026-11-23) [8]

## 事实摘要

- **类型:** HTTP 授权框架 [1]
- **标准组织:** 互联网工程任务组（IETF）OAuth 工作组 [8]
- **OAuth 1.0:** 2007 年 10 月稳定；2009 年 6 月 Revision A；RFC 5849（信息性，2010 年 4 月） [4]
- **OAuth 2.0 框架:** RFC 6749（标准轨道，2012 年 10 月；编辑 D. Hardt） [1]
- **持有者令牌用法:** RFC 6750（标准轨道，2012 年 10 月；强制 TLS） [2]
- **PKCE:** RFC 7636（标准轨道，2015 年 9 月） [3]
- **服务器元数据:** RFC 8414（标准轨道，2018 年 6 月） [5]
- **安全 BCP:** RFC 9700 / BCP 240（2025 年 1 月；更新 RFC 6749、6750 和 6819） [6]
- **受保护资源元数据:** RFC 9728（标准轨道，2025 年 4 月） [7]
- **OAuth 2.1 状态:** 活跃互联网草案 draft-ietf-oauth-v2-1-17（2026-10-30 更新，2027-05-04 到期） (截至 2026-11-23) [8]
- **OAuth 2.0 角色:** 资源所有者、资源服务器、客户端、授权服务器 [1]
- **基于 OAuth 2.0 的协议:** OpenID Connect、UMA 2.0、IndieAuth [9]

## OAuth 的起源以及从 OAuth 1.0 到 OAuth 2.0 的演进

OAuth 将第三方客户端的角色与资源所有者分离，使应用程序无需持有资源所有者的凭据，即可使用授权服务器颁发的访问令牌访问 HTTP 资源。[1] 在传统的客户端-服务器密码共享模式下，第三方应用程序必须以明文形式存储用户密码，获得没有范围和有效期限制的广泛访问权限，无法在不更改密码的情况下单独撤销某个应用的权限，而且一旦第三方应用遭到入侵，用户密码及所有受保护数据都会随之泄露。[1]

OAuth 1.0 由一个小型 Web 开发者社区创建，旨在提供受保护资源的委托访问能力。[4] 该规范于 2007 年 10 月在 1.0 版趋于稳定，并于 2009 年 6 月修订为 OAuth Core 1.0 Revision A（`oauth.net/core/1.0a`）。[4] 原作者将变更控制权移交给 IETF 后，IETF 于 2010 年 4 月将涵盖 Revision A 及已报告勘误的文档作为信息性（Informational）规范 RFC 5849（由 E. Hammer-Lahav 编辑）发布。[4] OAuth 1.0 定义了三个角色：客户端（最初称 Consumer）、服务器（最初称 Service Provider）和资源所有者（最初称 User）。[4] 该协议使用三类由标识符和共享密钥组成的凭据（客户端凭据、临时凭据和令牌凭据），并通过随机数（nonce）、时间戳和加密签名（`HMAC-SHA1`、`RSA-SHA1` 或 `PLAINTEXT`）对 HTTP 请求进行认证。[4]

2012 年 10 月，IETF 在标准轨道上发布了 OAuth 2.0 规范 RFC 6749（由 D. Hardt 编辑）以及持有者令牌用法规范 RFC 6750（由 M. Jones 和 D. Hardt 撰写）。[1][2] RFC 6749 取代并废止了 RFC 5849。[1] OAuth 2.0 专为 HTTP 设计且不向后兼容 OAuth 1.0，但两个版本可以在同一网络中共存，实现也可以同时支持两者。[1] 在 HTTP 以外的协议上使用 OAuth 2.0 超出了 RFC 6749 的适用范围。[1]

## OAuth 2.0 的角色、端点、令牌与授权许可类型

OAuth 2.0 在 RFC 6749 中为 HTTP 资源的委托访问定义了四个角色。[1]

| 角色 | RFC 6749 中的定义 |
| --- | --- |
| 资源所有者（Resource owner） | 能够授予受保护资源访问权限的实体；若为自然人，则称为最终用户 |
| 资源服务器（Resource server） | 托管受保护资源的服务器，能够接收并响应携带访问令牌的请求 |
| 客户端（Client） | 经资源所有者授权、代表其发起受保护资源请求的应用程序 |
| 授权服务器（Authorization server） | 在对资源所有者进行认证并获得授权后，向客户端颁发访问令牌的服务器 |

授权服务器与资源服务器可以部署在同一台服务器上，也可以作为独立实体运行；单个授权服务器还可以颁发被多个资源服务器接受的访问令牌。[1] RFC 6749 定义了两个授权服务器端点（授权端点与令牌端点）以及客户端的重定向端点。[1] 在抽象流程中，客户端先从资源所有者处获取授权许可，随后在授权服务器用该许可换取代表特定范围（scope）、有效期和访问属性的访问令牌，并将该访问令牌提交给资源服务器。[1][2] 在部分流程中，客户端无需资源所有者的授权许可，而是直接向授权服务器出示自身凭据以获取访问令牌。[1][2]

RFC 6750 规定了客户端在启用传输层安全协议（TLS）的 HTTP/1.1 上出示持有者访问令牌的方式，并强制要求实现和使用 TLS。[2] 任何持有持有者令牌的一方无需证明其拥有加密密钥材料即可访问对应资源，因此必须在存储和传输过程中防止持有者令牌泄露。[2] RFC 6750 定义了三种传输方式：使用 `Bearer` 方案的 `Authorization` 请求头字段（`Authorization: Bearer <token>`）、表单编码的请求体参数，以及 URI 查询参数，同时禁止客户端在单个请求中同时使用多种方式。[2] 该规范还在 IANA 注册了 `Bearer` 访问令牌类型，以及 `WWW-Authenticate` 错误值 `invalid_request`、`invalid_token` 和 `insufficient_scope`。[2]

RFC 6749 定义了四种授权许可类型：授权码（Authorization Code）、隐式（Implicit）、资源所有者密码凭据（Resource Owner Password Credentials）和客户端凭据（Client Credentials），同时包含刷新令牌（Refresh Token）颁发机制和扩展许可（Extension Grants）机制。[1] 后续 IETF 规范还补充了面向无浏览器或无键盘设备的设备授权许可（Device Authorization Grant，RFC 8628）等流程。[9] 随后的安全指南 RFC 9700 弃用了安全性较低的运行模式，OAuth 社区站点将隐式许可与密码许可列为遗留模式，而 OAuth 2.1 则彻底移除了这两种许可。[6][9][10]

## OAuth 2.0 PKCE 与安全当前最佳实践（RFC 9700）

使用授权码许可的 OAuth 2.0 公共客户端容易受到授权码拦截攻击，为此 IETF 于 2015 年 9 月在 RFC 7636（由 N. Sakimura、J. Bradley 和 N. Agarwal 撰写）中制定了代码交换证明密钥（PKCE，读作“pixy”）。[3] 在智能手机等终端设备上实施该攻击时，恶意应用程序会注册与合法原生 OAuth 2.0 应用相同的自定义 URI 方案，在操作系统执行应用间重定向时拦截返回的授权码，并用该授权码换取访问令牌。[3]

PKCE 要求客户端为每次授权请求生成一个唯一的、密码学随机的 `code_verifier`，并将变换后的值 `code_challenge` 发送至授权端点，从而缓解拦截攻击。[3] 客户端在向令牌端点提交授权码时必须附带原始的 `code_verifier`，以便授权服务器在颁发令牌前验证两者的绑定关系。[3] RFC 7636 定义了两种初始的 `code_challenge_method` 值：`plain` 仅用于缓解授权响应被窃听的场景，而 `S256` 还能缓解攻击者能够读取授权请求的场景（例如操作系统 HTTP 日志泄露）。[3]

2025 年 1 月，IETF 发布了 OAuth 2.0 安全当前最佳实践 RFC 9700（BCP 240，由 T. Lodderstedt、J. Bradley、A. Labunets 和 D. Fett 撰写），更新了 RFC 6749、RFC 6750 和 RFC 6819。[6] RFC 9700 针对实际部署中的实现缺陷、高安全要求场景（包括开放银行、电子健康、电子政务和电子签名）、动态客户端-服务器关系以及重定向时影响 URL 片段处理的浏览器行为变化做出了规定。[6] 其核心要求包括以下措施。[6]

- 将客户端重定向 URI 与预注册 URI 比对时必须采用精确字符串匹配，原生应用的 localhost 重定向 URI 中的端口号除外
- 禁止客户端和授权服务器暴露开放重定向器
- 强制实施跨站请求伪造（CSRF）防护，采用已确认授权服务器支持的 PKCE、OpenID Connect 的 `nonce` 参数，或与用户代理绑定的 `state` 一次性 CSRF 令牌
- 当客户端与多个授权服务器交互时，强制实施混淆攻击防御，使用 RFC 9207 的 `iss` 参数、ID 令牌或 JARM 响应中的 `iss` 声明，或使用相互独立的重定向 URI
- 在授权码许可中强制要求公共客户端使用 PKCE，建议机密客户端使用 PKCE，并允许机密 OpenID Connect 客户端在满足条件时使用 `nonce`
- 弃用安全性较低或不安全的运行模式，并就发送方受限访问令牌、受众受限访问令牌和刷新令牌保护提供指导

IETF OAuth 工作组还制定了多项补充规范以支持更高安全级别与令牌生命周期管理需求，包括推送授权请求（PAR，RFC 9126）、持有证明演示（DPoP，RFC 9449）、双向 TLS（Mutual TLS，RFC 8705）、访问令牌 JWT 配置文件（RFC 9068）、令牌自省（Token Introspection，RFC 7662）、令牌撤销（Token Revocation，RFC 7009）、令牌交换（Token Exchange，RFC 8693）、富授权请求（RAR，RFC 9396）、分步认证质询（Step-up Authentication Challenge，RFC 9470）以及跨设备流程安全（RFC 10027）。[9]

## OAuth 2.0 元数据与发现规范

OAuth 2.0 最初假设客户端在部署时即已知晓服务器 URL 的静态关系，随后的 IETF 规范面向动态环境增加了基于[知名 URI](https://mimirwiki.com/zh/wiki/well-known-uri)的 JSON 元数据发现机制。[5][6][7]

2018 年 6 月在标准轨道上发布的 OAuth 2.0 授权服务器元数据（RFC 8414，由 M. Jones、N. Sakimura 和 J. Bradley 撰写）以兼容格式将 OpenID Connect Discovery 1.0 泛化，适用于更广泛的 OAuth 2.0 部署。[5] 客户端从授权服务器 `issuer` URL 推导出的 `.well-known` 位置（依据 RFC 5785）获取 JSON 文档；该 `issuer` URL 采用 `https` 方案且不含查询或片段部分，同时有助于防范混淆攻击。[5] 元数据既可通过 HTTPS 以自声明 JSON 形式提供，也可作为 JSON Web Token（JWT）中的签名声明传递。[5] 已注册的元数据参数包括 `issuer`、`authorization_endpoint`、`token_endpoint`、`jwks_uri`、`registration_endpoint`（RFC 7591）、`scopes_supported`、`response_types_supported`、`response_modes_supported`（默认为 `query` 和 `fragment`，并定义了 `form_post`）以及 `grant_types_supported`。[5]

2025 年 4 月在标准轨道上发布的 OAuth 2.0 受保护资源元数据（RFC 9728，由 M.B. Jones、P. Hunt 和 A. Parecki 撰写）定义了相对应的 JSON 元数据格式，使客户端和授权服务器能够发现与 OAuth 2.0 受保护资源交互的方式。[7] 每个受保护资源都在由其 `https` 资源标识符确定性推导出的 `.well-known` 位置（依据 RFC 8615）发布元数据，形式可为自声明 JSON 或 JWT 签名声明。[7] 已注册的参数包括 `resource`（必需）、`authorization_servers`（RFC 8414 颁发者标识符列表）、`jwks_uri`、`scopes_supported` 以及 `bearer_methods_supported`（`header`、`body` 和 `query`）。[7] RFC 9728 还规定了受保护资源如何通过 `WWW-Authenticate` HTTP 响应头向客户端动态告知受保护资源元数据 URL。[7]

在程序化客户端注册方面，RFC 7591 规定了 OAuth 2.0 动态客户端注册协议，RFC 7592 定义了实验性的注册管理规范。[5][9] 截至 2026-11-23，OAuth 工作组还在推进客户端 ID 元数据文档（`draft-ietf-oauth-client-id-metadata-document-00`）以及跨应用访问（Cross-App Access，XAA）等其他工作组草案。[9][12]

## OAuth 2.1 整合与 IETF 草案状态

OAuth 2.1 是 IETF OAuth 工作组正在推进的一项规范整合工作，旨在将 OAuth 2.0（RFC 6749）、持有者令牌用法（RFC 6750）及后续规范合并为单一文档。[8][10] 它吸收了 RFC 7636（PKCE）、RFC 8252（原生应用 OAuth 2.0）、RFC 10017（基于浏览器应用的 OAuth）以及 RFC 9700（OAuth 2.0 安全当前最佳实践）中的修订内容。[6][10]

截至 2026-11-23，`draft-ietf-oauth-v2-1-17`（作者为 Dick Hardt、编辑 Aaron Parecki 以及 Torsten Lodderstedt，取代了 `draft-parecki-oauth-v2-1`）是拟走标准轨道的活跃互联网草案，若获批准将废止 RFC 6749 和 RFC 6750。[8] IETF Datatracker 记录显示，第 17 版最后更新于 2026-10-30（草案标明日期为 2026-10-31），到期日为 2027-05-04，OAuth 工作组设定的提交 IESG 里程碑为 2026 年 12 月。[8] IETF 将互联网草案归类为进行中的工作，该文档尚未作为最终 RFC 发布。[8] 其草案源码与问题追踪库维护于 `github.com/oauth-wg/oauth-v2-1`。[8]

OAuth 社区的 OAuth 2.1 文档列出了与 OAuth 2.0 相比的七项主要差异，这些差异在截至 2026-11-23 的 `draft-ietf-oauth-v2-1-17` 结构中均有所体现。[8][10]

| 领域 | OAuth 2.1 规则（draft-ietf-oauth-v2-1-17） |
| --- | --- |
| PKCE | 所有使用授权码流程的 OAuth 客户端均必须使用 |
| 重定向 URI | 必须使用精确字符串匹配进行比较 |
| 隐式许可 | 移除（删除 `response_type=token`） |
| 资源所有者密码凭据许可 | 移除 |
| URI 查询字符串中的持有者令牌 | 移除；资源请求须使用 Authorization 请求头字段或表单编码的内容参数 |
| 公共客户端刷新令牌 | 必须为发送方受限或实行令牌轮换 |
| 客户端类型定义 | 将公共客户端与机密客户端的定义简化为客户端是否持有凭据 |

除持有者令牌外，`draft-ietf-oauth-v2-1-17` 还设有专门章节阐述发送方受限访问令牌，并将核心授权许可类型限定为授权码、客户端凭据、刷新令牌和扩展许可。[8]

## OpenID Connect 与模型上下文协议授权中的 OAuth

OAuth 2.0 构成了多项协议的基础授权层，包括 OpenID Connect（OpenID Foundation）、UMA 2.0（Kantara）、IndieAuth（W3C），以及[模型上下文协议](https://mimirwiki.com/zh/wiki/model-context-protocol)（MCP）中的传输层授权。[9][11][12]

OpenID Connect 是构建在 RFC 6749 和 RFC 6750 之上的可互操作认证协议，使应用程序能够根据授权服务器（称为 OpenID 提供方，OP，或身份提供方，IDP）完成的认证来验证最终用户身份，并从类 REST 风格的 UserInfo 端点获取用户资料声明。[11] 将用户认证委托给 OP 的应用程序称为依赖方（Relying Party，RP）。[11] 在 OpenID Connect 流程中，RP 向 OP 发送认证请求，OP 对最终用户进行认证并获得授权后，返回一个至少包含 `sub`（主体）声明及认证元数据的身份令牌，通常同时附带访问令牌。[11] OpenID Connect 依赖 HTTPS/TLS 进行传输加密，并在跨 Web、移动端和 JavaScript 客户端需要签名时采用 JSON Web Token（JWT）结构，同时支持身份数据加密、提供方发现和会话注销等可选特性。[11] OpenID Foundation 将这种基于 JSON 与 REST 的设计同 OpenID 2.0 和 SAML 等基于 XML 的身份协议进行了对比。[11]

模型上下文协议规范（2026-07-28 版）为基于 HTTP 的传输定义了可选的传输层授权，而使用 STDIO 传输的实现则从运行环境中获取凭据。[12] 在 MCP 授权中，受保护的 MCP 服务器充当 OAuth 2.1 资源服务器，MCP 客户端充当代表资源所有者发起请求的 OAuth 2.1 客户端，授权服务器则与用户交互并颁发访问令牌。[12] 截至 2026-11-23，2026-07-28 版规范指定了 OAuth 与 OpenID Connect 标准的以下子集。[12]

- 核心流程与令牌：OAuth 2.1 IETF 草案（`draft-ietf-oauth-v2-1-13`）及持有者令牌用法（RFC 6750）
- 受保护资源发现：强制要求 MCP 服务器和客户端支持 OAuth 2.0 受保护资源元数据（RFC 9728）；MCP 服务器返回携带 `resource_metadata`（例如 `/.well-known/oauth-protected-resource`）及可选 `scope` 提示的 HTTP 401 `WWW-Authenticate: Bearer` 响应头，以支持最小权限和分步授权
- 授权服务器发现：授权服务器必须提供 OAuth 2.0 授权服务器元数据（RFC 8414）或 OpenID Connect Discovery 1.0，MCP 客户端必须同时支持两者
- 资源与颁发者绑定：强制要求支持 OAuth 2.0 资源指示器（RFC 8707），在授权请求和令牌请求中均须通过 `resource` 参数携带 MCP 服务器的规范 URI，并在向令牌端点发送授权码前依据已记录的颁发者校验 RFC 9207 的 `iss` 参数
- 客户端注册：支持 OAuth 客户端 ID 元数据文档（`draft-ietf-oauth-client-id-metadata-document-00`）、预注册或动态客户端注册（RFC 7591 及 OpenID Connect Dynamic Client Registration 1.0），其中 RFC 7591 在 MCP 中已被弃用，仅出于向后兼容而保留

## 常见问题

### 什么是 OAuth？

OAuth 是 IETF 制定的 HTTP 服务授权框架，允许第三方应用程序在不获取资源所有者凭据的情况下，使用授权服务器颁发的访问令牌有限地访问受保护资源。OAuth 2.0 于 2012 年 10 月在 IETF 标准轨道上通过 RFC 6749 和 RFC 6750 发布。 [1][2]

### OAuth 2.0 中的四个角色是什么？

RFC 6749 定义了四个角色：资源所有者（能够授予受保护资源访问权限的实体，若为自然人则称为最终用户）、资源服务器（托管受保护资源的服务器）、客户端（经授权代表资源所有者请求受保护资源的应用程序），以及授权服务器（对资源所有者进行认证并颁发访问令牌的服务器）。 [1]

### 什么是 PKCE，为什么在 OAuth 2.0 中使用它？

代码交换证明密钥（PKCE）于 2015 年 9 月在 RFC 7636 中规定，通过动态生成的随机代码验证器（code verifier）及其变换后的代码质询（code challenge）将授权请求与令牌请求绑定，从而缓解授权码许可中的授权码拦截与注入攻击。RFC 9700 要求公共客户端必须使用 PKCE，并建议机密客户端也使用 PKCE。 [3][6]

### OAuth 2.0 安全当前最佳实践 RFC 9700 有哪些变化？

RFC 9700 于 2025 年 1 月作为 BCP 240 发布，更新了 RFC 6749、RFC 6750 和 RFC 6819。其主要变化包括：要求对重定向 URI 进行精确字符串匹配（原生应用的 localhost 重定向 URI 中的端口号除外）、禁止暴露开放重定向器、强制要求 CSRF 防护及基于 RFC 9207 iss 参数等机制的混淆攻击防御、强制公共客户端使用 PKCE，以及弃用安全性较低的运行模式。 [6]

### OAuth 2.1 是已定稿的标准吗？

截至 2026-11-23，OAuth 2.1 是 IETF OAuth 工作组的活跃互联网草案（draft-ietf-oauth-v2-1-17，2026-10-30 最后更新，2027-05-04 到期），工作组提交 IESG 的里程碑为 2026 年 12 月。该草案整合了 OAuth 2.0 及后续 RFC，移除了隐式许可、资源所有者密码凭据许可以及 URI 查询字符串中的持有者令牌，并要求所有使用授权码流程的客户端均采用 PKCE。 [8][10]

### OpenID Connect 和模型上下文协议如何使用 OAuth？

OpenID Connect 是构建在 OAuth 2.0（RFC 6749 和 RFC 6750）之上的认证协议，由 OpenID 提供方返回身份令牌，并通过 UserInfo 端点提供用户资料声明。模型上下文协议规范 2026-07-28 版将 OAuth 2.1、RFC 6750、RFC 8414、RFC 9728、RFC 8707 和 RFC 9207 用于可选的 HTTP 传输授权，并将受保护的 MCP 服务器视为 OAuth 2.1 资源服务器。 [11][12]

## 可引用的句子

- OAuth 1.0 于 2007 年 10 月趋于稳定，于 2009 年 6 月修订为 Revision A，并于 2010 年 4 月作为信息性（Informational）文档 RFC 5849 发布。 [4]
- 2012 年 10 月在 IETF 标准轨道上发布的 RFC 6749 定义了 OAuth 2.0 授权框架，并废止了 RFC 5849。 [1]
- RFC 6750 定义了面向 OAuth 2.0 受保护资源的 HTTP 持有者令牌（Bearer Token）用法，并要求使用传输层安全协议（TLS）。 [2]
- 2015 年 9 月发布的 RFC 7636 规定了代码交换证明密钥（PKCE），用于缓解针对 OAuth 2.0 公共客户端的授权码拦截攻击。 [3]
- RFC 8414（2018 年 6 月）和 RFC 9728（2025 年 4 月）为 OAuth 2.0 授权服务器和受保护资源定义了通过 .well-known URI 提供的 JSON 元数据文档。 [5][7]
- 2025 年 1 月发布的 RFC 9700（BCP 240）以 OAuth 2.0 安全当前最佳实践更新了 RFC 6749、RFC 6750 和 RFC 6819。 [6]
- 截至 2026-11-23，OAuth 2.1 仍为活跃的 IETF 互联网草案（draft-ietf-oauth-v2-1-17，2026-10-30 更新），若获批准将废止 RFC 6749 和 RFC 6750。 [8]
- 模型上下文协议（MCP）规范 2026-07-28 版要求使用 HTTP 授权的受保护 MCP 服务器实现 RFC 9728，并要求 MCP 客户端发送 RFC 8707 的 resource 参数。 [12]

## 时间线

- 2007-10: Web 开发者社区将 OAuth 1.0 协议定型为稳定版本。 [4]
- 2009-06: OAuth Core 1.0 Revision A 在 oauth.net/core/1.0a 发布。 [4]
- 2010-04: IETF 将 RFC 5849（The OAuth 1.0 Protocol）作为信息性 RFC 发布。 [4]
- 2012-10: IETF 在标准轨道上发布 RFC 6749（The OAuth 2.0 Authorization Framework）和 RFC 6750（Bearer Token Usage），并废止 RFC 5849。 [1][2]
- 2015-09: IETF 发布 RFC 7636，为 OAuth 公共客户端规定了代码交换证明密钥（PKCE）。 [3]
- 2018-06: IETF 发布 RFC 8414，定义 OAuth 2.0 授权服务器元数据。 [5]
- 2025-01: IETF 发布 RFC 9700（BCP 240），确立 OAuth 2.0 安全当前最佳实践，并更新 RFC 6749、RFC 6750 和 RFC 6819。 [6]
- 2025-04: IETF 发布 RFC 9728，定义 OAuth 2.0 受保护资源元数据。 [7]
- 2026-07-28: 模型上下文协议规范 2026-07-28 版指定将 OAuth 2.1、RFC 9728、RFC 8414、RFC 8707 和 RFC 9207 用于基于 HTTP 的传输层授权。 [12]
- 2026-10-30: IETF Datatracker 记录了 OAuth 2.1 互联网草案第 17 版（draft-ietf-oauth-v2-1-17），到期日为 2027-05-04，提交 IESG 的工作组里程碑为 2026 年 12 月。 [8]

## 来源

1. RFC 6749: The OAuth 2.0 Authorization Framework. Internet Engineering Task Force (IETF). 发布于 2012-10. https://www.rfc-editor.org/rfc/rfc6749.txt (访问于 2026-11-23; tier 1: government or public registry)
2. RFC 6750: The OAuth 2.0 Authorization Framework: Bearer Token Usage. Internet Engineering Task Force (IETF). 发布于 2012-10. https://www.rfc-editor.org/rfc/rfc6750.txt (访问于 2026-11-23; tier 1: government or public registry)
3. RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Internet Engineering Task Force (IETF). 发布于 2015-09. https://www.rfc-editor.org/rfc/rfc7636.txt (访问于 2026-11-23; tier 1: government or public registry)
4. RFC 5849: The OAuth 1.0 Protocol. Internet Engineering Task Force (IETF). 发布于 2010-04. https://www.rfc-editor.org/rfc/rfc5849.txt (访问于 2026-11-23; tier 1: government or public registry)
5. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 发布于 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (访问于 2026-11-23; tier 1: government or public registry)
6. RFC 9700: Best Current Practice for OAuth 2.0 Security. Internet Engineering Task Force (IETF). 发布于 2025-01. https://www.rfc-editor.org/rfc/rfc9700.txt (访问于 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 发布于 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (访问于 2026-11-23; tier 1: government or public registry)
8. draft-ietf-oauth-v2-1-17 - The OAuth 2.1 Authorization Framework. Internet Engineering Task Force (IETF). 发布于 2026-10-30. https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ (访问于 2026-11-23; tier 1: government or public registry)
9. OAuth 2.0 - OAuth. OAuth Community Site. https://oauth.net/2/ (访问于 2026-11-23; tier 3: official site)
10. OAuth 2.1. OAuth Community Site. https://oauth.net/2.1/ (访问于 2026-11-23; tier 3: official site)
11. How OpenID Connect Works - OpenID Foundation. OpenID Foundation. 发布于 2023-02-14. https://openid.net/developers/how-connect-works/ (访问于 2026-11-23; tier 3: official site)
12. Authorization - Model Context Protocol. Model Context Protocol project. 发布于 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "OAuth." 版本 b3da6492, 2026-11-23. https://mimirwiki.com/zh/wiki/oauth
