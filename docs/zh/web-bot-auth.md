---
title: "Web Bot Auth"
subtitle: "基于 RFC 9421 HTTP 消息签名的自动化 HTTP 客户端与 AI 代理密码学认证协议"
canonical_url: https://mimirwiki.com/zh/wiki/web-bot-auth
language: zh
page_class: anchor
revision_sha256: 5fc6a0530bda162b1ce8498d0097cfee2c76b8ab893522078982f134be9232ca
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/web-bot-auth.md
  txt: https://mimirwiki.com/zh/wiki/web-bot-auth.txt
  json: https://mimirwiki.com/zh/wiki/web-bot-auth.json
  jsonld: https://mimirwiki.com/zh/wiki/web-bot-auth.jsonld
translations:
  en: https://mimirwiki.com/wiki/web-bot-auth
  ko: https://mimirwiki.com/ko/wiki/web-bot-auth
  ja: https://mimirwiki.com/ja/wiki/web-bot-auth
---

# Web Bot Auth

> Web Bot Auth 是一种基于 RFC 9421 HTTP 消息签名构建的密码学认证协议，面向网络爬虫和 AI 代理等自动化 HTTP 客户端。客户端使用私钥对出站请求签名，并将公钥发布在通常位于 /.well-known/http-message-signatures-directory 的 JWKS 目录中，使服务器能够验证其身份。该规范由 IETF webbotauth 工作组制定。

Web Bot Auth 是一种密码学认证协议，允许网络爬虫和 AI 代理等自动化 HTTP 客户端使用 RFC 9421 HTTP 消息签名对出站请求进行签名，从而使 Web 服务器能够验证其身份。自动化客户端会在请求中附加 Signature、Signature-Input 和 Signature-Agent 请求头，并通过 HTTPS 在 JSON Web Key Set（JWKS）目录中发布其公钥签名密钥，该目录通常托管于知名 URI /.well-known/http-message-signatures-directory。互联网工程任务组（IETF）的 Web Bot Auth（webbotauth）工作组正在通过由 Cloudflare 的 Thibault Meunier 和 Google 的 Sandor Major 编写的 draft-ietf-webbotauth-httpsig-protocol 制定标准轨道规范。Cloudflare 已于 2025 年 7 月将基于 Ed25519 签名密钥的 Web Bot Auth 纳入其 Verified Bots Program。

**别名:** webbotauth, HTTP Message Signatures for Automated Traffic, RFC 9421 Web Bot Auth

## 关键事实

- **基础标准:** RFC 9421（HTTP 消息签名，2024 年 2 月） [1]
- **标准组织:** IETF Web Bot Auth（webbotauth）工作组 [2]
- **当前活跃规范:** draft-ietf-webbotauth-httpsig-protocol-01（2026-10-29） (截至 2026-11-23) [4]
- **知名密钥目录:** /.well-known/http-message-signatures-directory [9]
- **主要 HTTP 请求头:** Signature、Signature-Input、Signature-Agent [9]

## 事实摘要

- **类型:** 面向自动化客户端的密码学 HTTP 认证协议 [5]
- **基础标准:** RFC 9421：HTTP 消息签名（2024 年 2 月） [1]
- **工作组:** IETF Web Bot Auth（webbotauth），Web 与互联网传输领域 (截至 2026-11-23) [2]
- **工作组主席:** David Schinazi、Rifaat Shekh-Yusef (截至 2026-11-23) [2]
- **规范作者:** Thibault Meunier（Cloudflare）、Sandor Major（Google） (截至 2026-11-23) [4]
- **当前草案:** draft-ietf-webbotauth-httpsig-protocol-01（发布于 2026-10-29） (截至 2026-11-23) [4]
- **密钥目录路径:** /.well-known/http-message-signatures-directory [9]
- **目录媒体类型:** application/http-message-signatures-directory+json [4]
- **Cloudflare 支持算法:** Ed25519（OKP JSON Web Key） (截至 2026-10-08) [9]
- **草案状态:** 活跃 IETF 互联网草案（拟定标准轨道） (截至 2026-11-23) [4]
- **参考代码库:** github.com/cloudflare/web-bot-auth（Apache-2.0 许可证） [12]

## Web Bot Auth 概述

Web Bot Auth 是一种用于对自动化 HTTP 客户端进行密码学认证的协议，涵盖搜索索引爬虫、网页归档工具、链接检查器、AI 训练爬虫以及代表终端用户执行操作的 AI 代理。[2][5] 该协议构建于 2024 年 2 月发布的 IETF 标准轨道规范 RFC 9421（HTTP 消息签名）之上，支持对 HTTP 消息中的选定组件生成分离式数字签名。[1][4] Web Bot Auth 仅在 HTTP 层运行，不改变传输层与 TLS 协议栈，因此签名在经过反向代理、网关及其他 HTTP 中间件后仍可验证。[1][5]

传统的机器人识别机制存在运维与安全方面的缺陷。[2][5] `User-Agent` 字符串容易被任意客户端伪造，而且当 Chromium 等自动化浏览器为了确保页面正常渲染而发送标准浏览器字符串时，该字段的语义会发生过载。[5] IP 地址允许列表需要在地址所有权分层复杂的云平台上持续维护清单，而专用 IP 地址段则伴随着采购成本、专业配置需求以及既有信誉历史负担。[5] OAuth Bearer 令牌等共享密钥机制要求逐站点接入，在 Web 规模下会显著增加密钥轮换的复杂度。[5]

Web Bot Auth 在 `draft-ietf-webbotauth-httpsig-protocol` 提出的两个目标与两个约束条件下应对上述需求。[5] 其目标是跨请求保持机器人信任的连续性，并支持将签名密钥可选地绑定至域名等外部信任锚。[5] 其约束条件是同时保持自动化客户端与网站双方的运维简洁性，且不要求客户端与源站服务器之间存在预先建立的关系。[5] Cloudflare 于 2025 年 5 月 15 日公开提出该方案，并于 2025 年 7 月 1 日将 HTTP 消息签名加入其 Verified Bots Program。[10][11]

## Web Bot Auth 如何签名与验证 HTTP 请求

Web Bot Auth 采用 RFC 9421 定义的分离式签名来认证出站 HTTP 请求，无需将消息头重复封装在独立的令牌载荷中。[1][5] 自动化客户端选择 HTTP 头部字段和派生组件，依照 RFC 9421 规则将其序列化为规范签名基串（signature base），随后使用机器人提供方持有的私钥计算数字签名。[1][5] RFC 9421 定义的算法包括基于 SHA-512 的 RSASSA-PSS、基于 SHA-256 的 RSASSA-PKCS1-v1_5、基于 SHA-256 的 HMAC、基于 P-256 和 P-384 曲线的 ECDSA，以及基于 edwards25519 曲线的 EdDSA（Ed25519）。[1] `draft-ietf-webbotauth-httpsig-protocol-01` 中的测试向量涵盖基于 SHA-512 的 RSASSA-PSS 和 Ed25519，而 Cloudflare 的生产实现支持 Ed25519。[4][9]

带签名的请求携带三个主要的 HTTP 头部字段。[1][9] `Signature-Input` 头部列出受签名覆盖的消息组件与签名元数据参数，`Signature` 头部承载经 Base64 编码的签名字节，`Signature-Agent` 头部则指明用于获取客户端公钥目录的 HTTPS URL。[1][4][5][9] 由于 RFC 9421 签名并不直接覆盖 HTTP 消息正文，需要正文完整性的应用依赖包含内容加密哈希值的 `Content-Digest` 头部。[1][9] RFC 9421 还定义了一个可选的 `Accept-Signature` 头部，接收方可通过它要求后续 HTTP 消息携带签名。[1]

`Signature-Input` 中的标准元数据参数用于限定签名的作用范围与生命周期。[1][5][9]

| 参数或请求头 | 在 Web Bot Auth 中的作用 |
| --- | --- |
| `Signature-Agent` | 携带客户端公钥目录的 HTTPS URL，用于带内（in-band）密钥发现。[4][5] |
| `Signature-Input` | 列出受签名覆盖的 HTTP 组件（如 `@authority` 和 `signature-agent`）以及签名元数据。[1][9] |
| `Signature` | 承载针对规范化签名基串生成的分离式密码学签名。[1][9] |
| `tag` | 标识应用上下文，在 Cloudflare 实现中机器人请求使用 `web-bot-auth`，带签名的目录响应使用 `http-message-signatures-directory`。[9] |
| `keyid` | 保存经 Base64URL 编码的 JSON Web Key（JWK）指纹，用于指明验证签名所需的公钥。[5][9] |
| `created` 与 `expires` | 以 Unix 时间戳形式规定签名有效期窗口，以限制重放攻击风险。[5][9] |
| `nonce` | 提供可选的按请求生成的随机值，用于缓解重放攻击。[9] |

## Web Bot Auth 密钥目录与信任模型

Web Bot Auth 在通过 HTTPS 提供的 JSON Web Key Set（JWKS）目录中发布公钥签名密钥，使验证方能够通过 `Signature-Agent` 请求头在带内发现密钥。[4][5][6] 早期的个人草案（`draft-meunier-http-message-signatures-directory`，于 2026 年 3 月 2 日更新至第 05 版）曾单独规定该目录格式，之后工作组将密钥发现机制整合进 `draft-ietf-webbotauth-httpsig-protocol`。[3][4][6] 该草案注册了媒体类型 `application/http-message-signatures-directory+json` 以及知名 URI `/.well-known/http-message-signatures-directory`。[4] 根据 RFC 8615，`/.well-known/` 路径前缀保留在 HTTP 或 HTTPS 源站的根目录处，因此将密钥目录托管在该路径下即可把密钥集与域名运营方绑定起来。[5][7]

在 `draft-ietf-webbotauth-httpsig-protocol-01` 定义的信任模型中，经过验证的 `Signature-Agent` HTTPS URL 作为代理的持久标识符。[5] 未经解析的 `Signature-Agent` 请求头仅属于未验证声明，验证方必须暂缓应用访问策略，直至通过 TLS 解析该 URL 并使用该目录返回的密钥完成请求签名验证。[5] 由于身份绑定在 URL 上而 `keyid` 负责选择具体密钥，运营方可以通过在目录中同时发布新密钥与现有密钥、之后再移除旧密钥的方式完成密钥轮换，而不中断身份连续性。[5] 当验证方直接持有密钥而未关联已解析的 URL 时，归属只能回退至 `keyid` 指纹，该方式在密钥轮换后无法保持连续性。[5]

通过 TLS 解析密钥目录能够确认 URL 所指主机在拉取时刻提供了该密钥集，而有效的请求签名则证明持有其中某一密钥的主体对受覆盖组件进行了签名。[5] 为防止第三方镜像其他运营方的目录并冒领这些密钥，目录响应本身可以附带 HTTP 消息签名，以证明对所列每个私钥的所有权。[4][9] 当验证方从多个来源获取目录记录时，应依据目录签名的 `created` 时间戳或验证方自身的拉取时间，优先采用更新的记录。[5] 签名验证证明的是密码学连续性与密钥所有权，而判断运营方是否可信或是否获准访问站点仍属于源站服务器的策略决策。[5]

## IETF Web Bot Auth 标准化进展

Web Bot Auth 的标准化工作由互联网工程任务组（IETF）Web 与互联网传输（`wit`）领域下的 Web Bot Auth（`webbotauth`）工作组推进。[2] 截至 2026-11-23，该工作组在已批准的章程 `charter-ietf-webbotauth-01` 下运行，由 David Schinazi 和 Rifaat Shekh-Yusef 担任工作组主席，Mike Bishop 担任领域总监（Area Director）。[2] 其章程定义了三类交付成果：面向人类用户网站的自动化客户端认证标准轨道规范、借助域名或 URL 等常用标识符传递请求机器人附加元数据的标准轨道规范，以及涵盖运维生命周期、密钥管理、部署考量和对 Web 开放性影响的当前最佳实践（Best Current Practice）或信息性（Informational）文档。[2] 该工作组与 AIPREF、HTTPBIS、OAUTH、TLS 及 WIMSE 等工作组保持协作。[2]

截至 2026-11-23，该工作组已采纳一份工作组互联网草案，即由 [Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 的 Thibault Meunier 和 Google 的 Sandor Major 编写的 `draft-ietf-webbotauth-httpsig-protocol-01`（“HTTP Message Signatures for automated traffic”）。[3][4][5] 修订版 `-01` 全文共 44 页，发布于 2026 年 10 月 29 日，计划于 2027 年 5 月 2 日到期；它取代了先前的个人草案系列 `draft-meunier-webbotauth-httpsig-protocol`，而后者又于 2026 年 3 月 2 日之后取代了 `draft-meunier-web-bot-auth-architecture-05`。[3][4][5] 工作组章程列出的目标里程碑为：2026 年 4 月向 IESG 提交标准轨道认证与机器人信息规范，2026 年 8 月提交当前最佳实践运维文档。[2]

除已采纳的协议草案外，截至 2026-11-23，`webbotauth` 文档页面还列出了 14 份相关的个人互联网草案。[3] 这些提案探索了多种互补机制，包括机器人注册表与 Signature Agent Cards（`draft-meunier-webbotauth-registry-04`）、带签名的代理元数据头部（`draft-vilgalys-webbotauth-signed-agent-metadata-00`）、托管密钥目录（`draft-singh-webbotauth-hosted-directories-00`）、匿名机器人认证（`draft-rescorla-anonymous-webbotauth-01`）、验证结果上报（`draft-suresh-webbotauth-verification-outcome-00`）、爬虫最佳实践（`draft-illyes-webbotauth-cbcp-01`）以及基于 JSON 的 IP 地址段发布（`draft-illyes-webbotauth-jafar-01`）。[3] 作为互联网草案，这些文档均仍处于推进中的工作状态，尚未具备正式的 IETF RFC 地位。[5][6]

## Cloudflare 的 Web Bot Auth 实现与工具

Web Bot Auth 已在 Cloudflare 的 Verified Bots Program 中投入生产部署，该项目于 2025 年 7 月 1 日加入了 HTTP 消息签名支持。[9][10] 根据 2026 年 10 月 8 日更新的 Cloudflare 开发者参考文档，接入流程包含四个步骤：生成 Ed25519 密钥对并将公钥转换为 JWK（`kty: "OKP"`、`crv: "Ed25519"`、无填充 Base64URL 编码的 `x`）；在 `/.well-known/http-message-signatures-directory` 上通过 HTTPS 托管带签名的 JWKS 目录；在 Cloudflare 控制台中使用 `Request Signature` 验证方式注册机器人及目录 URL；以及对出站请求进行签名。[9] 目录响应必须设置 `Content-Type: application/http-message-signatures-directory+json`，并为每个 Ed25519 密钥附带一条覆盖 `@authority;req` 且包含 `tag="http-message-signatures-directory"`、`keyid`、`created` 和 `expires` 的 HTTP 消息签名。[9]

截至 2026 年 10 月 8 日，Cloudflare 的请求验证遵循早期草案版本（`draft-meunier-web-bot-auth-architecture-02` 和 `draft-meunier-http-message-signatures-directory-03`），并施加了特定限制。[9] 出站请求必须将 `Signature-Agent` 作为带双引号的结构化字符串发送且其中包含 `https://` URI，在 `Signature-Input` 中包含 `signature-agent` 以及至少 `@authority`，使用纯 ASCII 组件值，并将 `tag` 设为 `tag="web-bot-auth"`。[9] Cloudflare 拒绝后续草案引入的 `Signature-Agent` 字典语法，不支持 `@query-params` 或 `@status`，并且当 `Signature-Input` 使用 RFC 9421 组件参数 `sf`、`bs`、`key`、`req` 或 `name` 时会判定验证失败。[9] 尽管 Cloudflare 建议发送 `nonce`，但截至 2026 年 10 月 8 日其验证器既不校验 nonce 也不在数据库中存储已见 nonce，因此建议使用较短的 `expires` 间隔（例如一分钟）来限制重放窗口。[9] 运营方可通过 `https://crawltest.com/cdn-cgi/web-bot-auth` 测试请求格式与验证结果：已验证的已知密钥返回 HTTP 200，未知密钥或验证失败返回 HTTP 401，格式错误的消息返回 HTTP 400。[9]

Cloudflare 还记录了一种实验性的传递信任（transitive trust）机制，利用 RFC 7239 `Forwarded` 请求头（示例语法如 `Forwarded: for="openai";use="reference"`）在中间件之间传递机器人运营方身份与内容使用承诺，并注明该特性可能会发生变化。[9] 希望在源站自行验证签名的站点所有者可以联系 Cloudflare Support 在其区域（zone）中禁用 Cloudflare 的验证，使其不再填充 `cf.bot_management.verified_bot`，从而让已验证机器人回退至反向 DNS 验证等方式。[9]

Cloudflare 在 `github.com/cloudflare/web-bot-auth` 维护了一个采用 Apache-2.0 许可证的开源代码库，包含 TypeScript 包（`http-message-sig`、`jsonwebkey-thumbprint`、`web-bot-auth`）和 Rust crate（`web-bot-auth`、`http-signature-directory`）；截至 2026-11-23，该代码库拥有 188 个 Star 和 52 个 Fork。[12] 代码库提供面向浏览器扩展、Rust、Caddy 插件和 Cloudflare Workers 的签名与验证示例，同时 Cloudflare Research 在 `http-message-signatures-example.research.cloudflare.com` 提供了一个测试端点。[12] 代码库文档指出该软件尚未经过安全审计。[12]

## Web Bot Auth 的适用范围、安全性与局限性

Web Bot Auth 面向访问以人类用户为主的 Web 内容的自动化 HTTP 客户端密码学认证，IETF `webbotauth` 章程明确将若干相邻问题划归范围之外。[2] 范围之外的事项包括：面向机器的 HTTP API 或代理间接口访问认证、代理背后的终端用户认证、非 HTTP 协议、非密码学识别方式、定义机器人意图词汇表、跟踪或评定机器人信誉，以及检测选择保持未认证状态的机器人。[2] Web Bot Auth 也不同于 2022 年 9 月在 RFC 9309 中标准化的机器人排除协议（[robots.txt](https://mimirwiki.com/zh/wiki/robots-txt)），后者按 `user-agent` 标记表达自愿性抓取规则，并明确声明这些规则不构成访问授权。[8]

Web Bot Auth 下的密码学验证具有明确的安全边界。[5] 有效签名仅确认请求由已解析 `Signature-Agent` URL 上发布的密钥签署，并不证明运营方出于善意，也不代表特定请求已获授权。[5] 协议本身无法阻止客户端弃用原有 URL 并启用新 URL，因为该机制针对的是希望在跨请求场景中获得持续识别的运营方。[5] 带签名的请求在其有效期内仍存在被重放的风险，运营方需要通过合理选择受覆盖组件并设置较短的 `created` 至 `expires` 间隔来加以约束。[5][9]

部署带内密钥发现会引入 `draft-ietf-webbotauth-httpsig-protocol-01` 安全与隐私考量章节所论述的运维风险。[4] 由于验证方会拉取入站请求提供的任意 `Signature-Agent` HTTPS URL，服务器必须防范服务器端请求伪造（SSRF），并对目录拉取的资源消耗和缓存行为加以限制。[4] 该规范还强调了 TLS 要求、密钥泄露应急响应、避免共享密钥与密钥复用、测试或静态签名的处理、反向代理交互，以及客户端识别、关联分析和目录访问模式带来的隐私影响。[4] 此外，`webbotauth` 章程要求工作组兼顾机器人客户端与网站的运维开销，并避免引入架构瓶颈。[2]

## 常见问题

### 什么是 Web Bot Auth？

Web Bot Auth 是一种 HTTP 层认证协议，允许网络爬虫和 AI 代理等自动化客户端使用 RFC 9421 HTTP 消息签名对出站请求进行加密签名。服务器依据发布在 JSON Web Key Set 目录中的公钥验证这些签名。 [1][4][5]

### 在 Web Bot Auth 中，服务器如何查找机器人的公钥？

带签名的请求会携带包含机器人密钥目录 HTTPS URL 的 Signature-Agent 请求头。服务器从该 URL（通常托管于 /.well-known/http-message-signatures-directory）获取 JSON Web Key Set，并使用 keyid 指纹参数选择匹配的公钥。 [4][5][9]

### Web Bot Auth 是正式的 IETF RFC 标准吗？

截至 2026-11-23，Web Bot Auth 仍是 IETF Web Bot Auth（webbotauth）工作组正在推进的草案工作。其核心规范 draft-ietf-webbotauth-httpsig-protocol-01 是一份发布于 2026 年 10 月 29 日的标准轨道（Standards Track）互联网草案，尚未作为 RFC 正式发布。 [2][4][5]

### Cloudflare 的 Web Bot Auth 支持哪些加密密钥？

截至 2026 年 10 月 8 日，Cloudflare 的 Web Bot Auth 集成支持在 /.well-known/http-message-signatures-directory 处以 OKP JSON Web Key 形式发布的 Ed25519 签名密钥。目录响应必须为每个 Ed25519 密钥附加一条 HTTP 消息签名，以证明密钥所有权。 [9]

### Web Bot Auth 如何在不丢失机器人身份的情况下进行密钥轮换？

在 draft-ietf-webbotauth-httpsig-protocol-01 中，经过验证的 Signature-Agent HTTPS URL 充当代理的标识符，而 keyid 用于选择单个密钥。运营方可以通过在目录中同时发布新公钥与现有公钥，随后再移除旧公钥的方式完成密钥轮换，从而在同一 URL 下保持身份连续性。 [5]

### Web Bot Auth 会取代 robots.txt 或用于认证终端用户吗？

不会。机器人排除协议（RFC 9309）定义的是自愿遵守的爬虫访问规则，而 Web Bot Auth 用于以密码学方式验证自动化客户端的身份。IETF webbotauth 工作组章程明确将终端用户认证排除在工作范围之外。 [2][8]

## 可引用的句子

- Web Bot Auth 使用由 RFC 9421（HTTP 消息签名，发布于 2024 年 2 月）定义的分离式数字签名来认证自动化 HTTP 请求。 [1][4]
- 截至 2026-11-23，IETF Web Bot Auth（webbotauth）工作组在已批准的章程 charter-ietf-webbotauth-01 下，隶属于 Web 与互联网传输（Web and Internet Transport）领域开展工作。 [2]
- 工作组采纳的草案 draft-ietf-webbotauth-httpsig-protocol-01 由 Cloudflare 的 Thibault Meunier 和 Google 的 Sandor Major 编写，并于 2026 年 10 月 29 日发布。 [4][5]
- 在 draft-ietf-webbotauth-httpsig-protocol-01 中，经过验证的 Signature-Agent HTTPS URL 用作代理的标识符，可在不破坏身份连续性的前提下实现密钥轮换。 [5]
- draft-ietf-webbotauth-httpsig-protocol-01 定义了用于发布 JWKS 密钥目录的知名 URI /.well-known/http-message-signatures-directory 以及媒体类型 application/http-message-signatures-directory+json。 [4][7]
- Cloudflare 于 2025 年 7 月 1 日将 HTTP 消息签名（Web Bot Auth）纳入其 Verified Bots Program。 [10]
- 截至 2026 年 10 月 8 日，Cloudflare 的 Web Bot Auth 实现支持 Ed25519 密钥，并要求在 /.well-known/http-message-signatures-directory 路径上通过 HTTPS 提供带签名的目录响应。 [9]
- Cloudflare 在 Apache-2.0 许可证下，于 github.com/cloudflare/web-bot-auth 维护开源的 TypeScript 和 Rust 版 Web Bot Auth 库及示例。 [12]

## 时间线

- 2024-02: IETF 将 RFC 9421（HTTP 消息签名）作为标准轨道规范发布。 [1]
- 2025-05-15: Cloudflare 发布由 Thibault Meunier 和 Mari Galicer 提出的初始方案，主张使用密码学 HTTP 签名验证机器人与 AI 代理流量。 [11]
- 2025-07-01: Cloudflare 将 HTTP 消息签名纳入其 Verified Bots Program。 [10]
- 2026-03-02: Thibault Meunier 和 Sandor Major 发布 draft-meunier-web-bot-auth-architecture 与 draft-meunier-http-message-signatures-directory 的第 05 版，这两份文档随后被 webbotauth 协议和目录草案取代。 [3][6]
- 2026-10-08: Cloudflare 更新其 Web Bot Auth 开发者文档，涵盖 Ed25519 密钥目录、请求签名以及实验性的 RFC 7239 Forwarded 请求头支持。 [9]
- 2026-10-29: IETF webbotauth 工作组发布 draft-ietf-webbotauth-httpsig-protocol-01（HTTP Message Signatures for automated traffic）。 [3][4][5]

## 来源

1. RFC 9421: HTTP Message Signatures. Internet Engineering Task Force (IETF). 发布于 2024-02. https://www.rfc-editor.org/rfc/rfc9421.txt (访问于 2026-11-23; tier 1: government or public registry)
2. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (访问于 2026-11-23; tier 1: government or public registry)
3. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/documents/ (访问于 2026-11-23; tier 1: government or public registry)
4. draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic. Internet Engineering Task Force (IETF). 发布于 2026-10-29. https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/ (访问于 2026-11-23; tier 1: government or public registry)
5. draft-ietf-webbotauth-httpsig-protocol-01. Internet Engineering Task Force (IETF). 发布于 2026-10-29. https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol (访问于 2026-11-23; tier 1: government or public registry)
6. draft-meunier-http-message-signatures-directory-05 - HTTP Message Signatures Directory. Internet Engineering Task Force (IETF). 发布于 2026-03-02. https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/ (访问于 2026-11-23; tier 1: government or public registry)
7. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 发布于 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (访问于 2026-11-23; tier 1: government or public registry)
8. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (访问于 2026-11-23; tier 1: government or public registry)
9. Web Bot Auth · Cloudflare bot solutions docs. Cloudflare. 发布于 2026-10-08. https://developers.cloudflare.com/bots/reference/bot-verification/web-bot-auth/ (访问于 2026-11-23; tier 3: official site)
10. Message Signatures are now part of our Verified Bots Program, simplifying bot authentication | Cloudflare Blog. The Cloudflare Blog. 发布于 2025-07-01. https://blog.cloudflare.com/verified-bots-with-cryptography/ (访问于 2026-11-23; tier 3: official site)
11. Forget IPs: using cryptography to verify bot and agent traffic | Cloudflare Blog. The Cloudflare Blog. 发布于 2025-05-15. https://blog.cloudflare.com/web-bot-auth/ (访问于 2026-11-23; tier 3: official site)
12. GitHub - cloudflare/web-bot-auth: Sign and verify orchestrated HTTP requests · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/web-bot-auth (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Web Bot Auth." 版本 5fc6a053, 2026-11-23. https://mimirwiki.com/zh/wiki/web-bot-auth
