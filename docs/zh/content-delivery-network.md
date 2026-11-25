---
title: "内容分发网络"
subtitle: "在地理上分布式部署的缓存服务器网络，可从靠近终端用户的位置分发网页内容"
canonical_url: https://mimirwiki.com/zh/wiki/content-delivery-network
language: zh
page_class: concept
revision_sha256: 6b8fdf6035a48d7ba52f9b7b34487281e2d6207cb4c5f73a243efef463f023be
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/content-delivery-network.md
  txt: https://mimirwiki.com/zh/wiki/content-delivery-network.txt
  json: https://mimirwiki.com/zh/wiki/content-delivery-network.json
  jsonld: https://mimirwiki.com/zh/wiki/content-delivery-network.jsonld
translations:
  en: https://mimirwiki.com/wiki/content-delivery-network
  ko: https://mimirwiki.com/ko/wiki/content-delivery-network
  ja: https://mimirwiki.com/ja/wiki/content-delivery-network
---

# 内容分发网络

> 内容分发网络（CDN）是一组在靠近终端用户的位置存储网页内容副本的分布式服务器。作为客户端与源站服务器之间的托管共享 HTTP 缓存，CDN 能够降低延迟、减轻源站服务器负载并提升可用性。相关的 IETF 文档涵盖 HTTP 缓存、定向缓存标头、任播服务分发以及 CDN 互联。

内容分发网络（Content Delivery Network，CDN）是一种在地理上分布式部署的服务器系统，用于存储网页对象的副本，并从靠近终端用户的位置处理客户端请求。作为客户端与源站服务器之间的托管共享 HTTP 缓存，CDN 能够缩短响应延迟、降低源站服务器负载，并在高流量下提高分发可靠性。相关的互联网工程任务组（IETF）文档涵盖 HTTP 缓存（RFC 9111）、定向 CDN 缓存控制（RFC 9213）、任播服务分发（RFC 4786）以及 CDN 互联（RFC 6707 与 RFC 7336）。商用 CDN 部署通过遍布全球的接入点（PoP）同时分发静态资源与动态网页内容，同时也会在缓存新鲜度、安全暴露面和第三方可用性依赖方面带来运维权衡。

**别名:** CDN, Content Delivery Network, Content Distribution Network, 内容分发网络（CDN）

## 关键事实

- **缓存分类:** 托管共享 HTTP 缓存 [7]
- **HTTP 缓存标准:** RFC 9111（STD 98，2022 年 6 月） [1]
- **定向缓存标头:** CDN-Cache-Control（RFC 9213，2022 年 6 月） [2]
- **任播路由实践:** RFC 4786（BCP 126，2006 年 12 月），通过 IGP 或 BGP 支持 IPv4 和 IPv6 [5]
- **互联框架:** CDNI 问题陈述（RFC 6707）与框架（RFC 7336） [4]

## 事实摘要

- **类别:** 分布式网络基础设施与托管共享 HTTP 缓存 [7]
- **边缘节点:** 被称为边缘站点或接入点（PoP）的地理分布式数据中心 [8]
- **源站来源:** 权威 HTTP 服务器、Web 服务器或对象存储桶 [8]
- **HTTP 缓存规范:** IETF RFC 9111（STD 98，2022 年 6 月），废止 RFC 7234 [1]
- **定向缓存控制:** CDN-Cache-Control 响应头（IETF RFC 9213，2022 年 6 月） [2]
- **必需的定向指令:** max-age、must-revalidate、no-store、no-cache、private [2]
- **任播运维实践文档:** IETF RFC 4786（BCP 126，2006 年 12 月），支持 IPv4 与 IPv6 [5]
- **CDNI 问题陈述:** IETF RFC 6707（信息性，2012 年 9 月） [3]
- **CDNI 框架:** IETF RFC 7336（信息性，2014 年 8 月），废止 RFC 3466 [4]
- **主要分发资源:** 静态资源（HTML、CSS、JavaScript、图像、媒体）与动态网页内容 [8]
- **CloudFront 默认缓存过期时间:** 24 小时（最小 0 秒，无固定上限） (截至 2026-11-23) [8]
- **客户端完整性保护:** 面向第三方静态资源 CDN 的子资源完整性（SRI） [6]

## 内容分发网络架构与接入点（PoP）

内容分发网络（CDN）作为一组在地理上分散部署的缓存服务器运行，用于存储网页数据的副本，并从靠近终端用户的位置响应客户端请求。[6][8] 源站服务器保存 HTML 页面、样式表（CSS）、JavaScript 文件、图像和媒体文件等网页对象的权威版本，可以是 Web 服务器、自定义 HTTP 服务器，或 Amazon S3 存储桶等对象存储服务。[6][8] 边缘站点（又称接入点，Point of Presence，PoP）是 CDN 部署在各地数据中心的服务器集合，用于在靠近访问者的位置缓存这些对象的副本。[8]

当客户端请求通过 CDN 提供服务的对象时，网络会将请求路由至延迟较低的边缘站点。[8] 若该边缘站点已存有可用副本，服务器会直接返回该副本，而无需将请求转发至源站服务器。[7][8] 若对象不存在，边缘服务器则会从源站服务器获取权威版本，并缓存一份副本以供后续请求使用。[8] 由于地理距离与延迟成正比，将服务器部署在更靠近终端用户的位置能够缩短往返传输时间。[6] Amazon CloudFront 等商业提供商还会通过私有骨干网（AWS 骨干网）路由请求以减少经过的中间网络数量，从而降低首字节时间（Time to First Byte）并提高数据传输速率，同时在多个边缘站点保存副本以保障可用性。[8]

在 HTTP 架构中，CDN 充当由服务运营方显式部署的托管共享缓存，用于将请求解析、基于 Cookie 的会话恢复、数据库查询和模板渲染等工作负载从源站服务器卸载出去。[7] RFC 6707 指出了针对可缓存内容部署 CDN 的三大主要优势：更低的分发成本、更高的终端用户体验质量以及更强的分发健壮性。[3] CDN 被广泛用于分发静态库（例如 Bootstrap 和 jQuery）、完整的静态网站以及动态网页内容。[6][8] 截至 2026-11-23，Amazon CloudFront 会将分配配置（源站服务器、日志记录、分配的或自定义域名，以及面向私有内容的签名 URL 和签名 Cookie 等访问控制）传播至所有边缘站点，并按需拉取对象，同时通过 CloudFront SaaS Manager 提供独立标准分配与多租户分配。[8] 截至 2026-11-23，CloudFront 默认在边缘站点将对象缓存 24 小时（最小 0 秒，无固定上限），按边缘站点的出站数据传输量以及 HTTP 或 HTTPS 请求数计费，且从 AWS 源站（Amazon S3、Elastic Load Balancing 和 Amazon API Gateway）传输至 CloudFront 不收取传输费。[8]

## 内容分发网络中的 HTTP 缓存机制（RFC 9111）

内容分发网络的缓存机制依赖于互联网工程任务组（IETF）于 2022 年 6 月发布的 HTTP 缓存规范 RFC 9111（STD 98），该规范由 R. Fielding（Adobe）、M. Nottingham（Fastly）和 J. Reschke（greenbytes）编辑，废止了 RFC 7234。[1] RFC 9111 将 HTTP 缓存定义为响应消息的本地存储以及控制其存储、检索和删除的子系统，可在后续等效请求中降低响应时间并减少网络带宽消耗。[1]

HTTP 缓存将缓存划分为服务于单个用户的私有缓存（通常位于网页浏览器内部），以及位于客户端与服务器之间、服务于多个用户的共享缓存。[1][7] MDN Web Docs 进一步将共享缓存细分为通常在服务开发者控制之外运行的代理缓存，以及由服务运营方显式部署的托管缓存，包括反向代理、CDN 以及使用 Cache API 的 Service Worker。[7] 随着 HTTPS 加密的普及，路径上的网络代理缓存通常只会透传加密流量而不进行检查或缓存，但在受控企业环境中，使用组织管理的证书颁发机构（CA）解密流量的 TLS 桥接代理属于例外。[7]

缓存使用至少由请求方法和目标 URI 组成的缓存键（cache key）来识别已存储的响应，不过许多实际部署的缓存仅存储按 URI 索引的 `GET` 响应。[1] 对于经过内容协商的资源，缓存会将 `Vary` 响应头中指定的请求头纳入缓存键。[1] 大多数缓存条目是针对 `GET` 请求的 `200 (OK)` 响应，但在规则允许时也可存储重定向、`404 (Not Found)` 响应和 `206 (Partial Content)` 响应。[1] 根据 RFC 9111 第 3 节，当响应包含 `no-store`、包含未允许修改后共享存储的 `private`，或者请求包含 `Authorization` 标头且响应未携带明确允许共享缓存的指令时，共享缓存必须避免存储该响应；此外，存储还需要可理解的请求方法、最终状态码，以及 `public`、`Expires`、`max-age`、`s-maxage`、缓存扩展或可启发式缓存的状态码等缓存指示。[1]

已存储的响应处于两种状态之一：新鲜（fresh，无需联系源站即可复用）或过期（stale，除非断开连接的缓存被允许提供过期内容，否则需要向源站验证以重新刷新）。[1][7] 新鲜度采用非负的 `delta-seconds` 值，上限为 `2147483648`（2^31，超过 68 年）以防止整数溢出。[1] 共享缓存通过 `Age` 标头报告已存储的时长；例如，带有 `Cache-Control: max-age=604800`（一周）的响应在共享缓存中存储一天后，将以 `Age: 86400` 返回，为下游客户端留下 518,400 秒的剩余新鲜度。[7] 当省略 `Cache-Control` 时，启发式缓存可能会将带有 `Last-Modified` 标头的响应复用大约自上次修改以来经过时间的 10%。[7] 由于基础 HTTP 缓存未定义显式删除机制，CDN 等托管缓存通过控制台、API 调用或重启提供带外清除（purging），并可执行 Varnish 配置语言（VCL）规则等自定义缓存逻辑。[7]

| 标头或指令 | 适用范围 | 在 HTTP 与 CDN 缓存中的作用 |
| --- | --- | --- |
| `Cache-Control: max-age` | 私有与共享缓存 | 设置自响应生成起的新鲜度生存期（秒）。[1][7] |
| `Cache-Control: s-maxage` | 共享缓存 | 专门为共享缓存设置新鲜度生存期。[1][2] |
| `Cache-Control: private` | 私有缓存 | 将个性化响应的存储限制在单用户缓存内。[1][7] |
| `Cache-Control: no-store` | 所有标准缓存 | 禁止缓存存储该响应。[1] |
| `Cache-Control: no-cache` | 所有标准缓存 | 要求在复用已存储响应前向源站进行验证。[1][2] |
| `Age` | 共享缓存 | 报告自响应生成以来经过的秒数。[1][7] |
| `Expires` | 传统 HTTP/1.0 与 HTTP/1.1 | 以显式时间戳指定缓存过期时间。[1][7] |
| `Vary` | 缓存键构造 | 列出在内容协商中需纳入缓存键的请求头。[1] |

## 定向 HTTP 缓存控制与 CDN-Cache-Control（RFC 9213）

内容分发网络部署通常位于多层缓存拓扑之中，与源站服务器缓存、源站网络缓存及浏览器缓存并存，因此需要向不同类别的缓存下发不同的缓存策略。[2] 虽然 `Cache-Control` 包含面向共享缓存的 `s-maxage`，但它在 `stale-while-revalidate` 等其他指令上缺乏一致的定向能力。[2] 早期 CDN 实现依赖 `Surrogate-Control` 等厂商专用标头，导致不同提供商之间的互操作性较低。[2][7]

2022 年 6 月，IETF 发布了标准跟踪规范 RFC 9213《Targeted HTTP Cache Control》，由 S. Ludin（Akamai）、M. Nottingham（Fastly）和 Y. Wu（[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare)）共同撰写。[2] RFC 9213 确立了定向缓存控制（Targeted Cache-Control）HTTP 响应头的通用约定，并专门针对 CDN 缓存定义了 `CDN-Cache-Control`。[2] 与 CDN 建有缓存失效机制的发布者，可以在 `CDN-Cache-Control` 中设置更长的生存期，同时在 `Cache-Control` 中为浏览器及其他中间节点保留更短的生存期。[2]

定向缓存控制标头定义为 HTTP 字典结构化字段（Dictionary Structured Fields），其中每个字典成员对应一条 HTTP 缓存响应指令（包括扩展指令），其值映射为结构化字段的 Boolean、String、Token、Integer 或 Decimal 类型。[2] 由于错误处理方式与 `Cache-Control` 不同，实现应对定向字段使用结构化字段解析器，并在字段为空或产生解析错误时将其忽略，转而回退至其他缓存控制机制。[2]

每个实现 RFC 9213 的缓存都会维护一个按优先级从高到低排列的标头名称目标列表（target list），例如 `[ExampleCDN-Cache-Control, CDN-Cache-Control]`。[2] 对于收到的每个响应，缓存会选取其目标列表中第一个有效且非空的字段来控制缓存行为，并忽略该响应中的 `Cache-Control` 和 `Expires`。[2] 不在缓存目标列表中的定向字段必须原样透传，且不得改变该缓存的行为。[2] 支持该规范的缓存必须在定向字段中实现五条指令：`max-age`、`must-revalidate`、`no-store`、`no-cache` 和 `private`。[2] 其优先级与 `Cache-Control` 一致，因此 `no-store` 和 `no-cache` 会使 `max-age` 失效，而无法识别的扩展指令会被忽略。[2]

## 任播服务分发（RFC 4786）

任播路由（anycast routing）让一个服务地址可以在两个或多个独立节点上到达，由路由系统把客户端请求送到其中一个节点。该实践记录在 IETF 最佳当前实践 RFC 4786（BCP 126，2006 年 12 月）中，作者为 J. Abley（Afilias Canada）与 K. Lindqvist（Netnod Internet Exchange）。[5] RFC 4786 面向一般的互联网服务，并以 DNS 服务器为主要示例。[5] 部署任播时，运营方将一个稳定的服务地址（IPv4 或 IPv6）关联到两个或多个独立的任播节点，并在路由系统中通告该地址的可达性。[5]

当客户端向任播服务地址发送数据包时，路由系统会根据网络拓扑和请求发起位置，将数据报导向其中一个可用节点。[5] 数据包路由至特定节点的网络拓扑区域称为该节点的覆盖区（catchment）。[5] RFC 4786 区分了两种部署范围：局部范围任播（local-scope anycast），通过内部网关协议（IGP）传播路由，使节点仅在路由系统的子集内可见；以及全局范围任播（global-scope anycast），使用边界网关协议（BGP，RFC 4271）向全球互联网通告可达性。[5] 任播无需服务器转引或轮询 DNS 即可运行，但应用程序在需要时也可将任播与基于名称的分发方式结合使用。[5]

RFC 4786 记录了任播服务分发固有的多项运维约束。[5]

- 事务状态与持续时间：任播对长生命周期事务、服务器端事务状态以及跨节点数据同步施加了限制。[5]
- 负载分布不均：由于路由拓扑决定了覆盖区大小，在任播节点间实现细粒度负载均衡较为困难，尽管任播有助于提升可靠性和粗粒度扩展，但各节点的请求量与流量负载往往仍不均衡。[5]
- 可用性监控：由于观察到的可达性因客户端网络位置而异，且每个节点所服务的客户端群体既非静态也不具备可靠确定性，因此在任播架构下衡量可用性更为复杂。[5]

## 内容分发网络互联标准（RFC 6707 与 RFC 7336）

内容分发网络互联（Content Delivery Network Interconnection，CDNI）使独立的内容分发网络能够相互协作，从而让一个 CDN 代表另一个 CDN 向终端用户分发内容。[3] 不断增长的视频和多媒体流量促使商用 CDN 运营商扩充容量，也推动许多网络服务提供商（NSP）部署了自己的 CDN。[3] 由于单一 CDN 可能无法在每个终端用户的接入网络附近都具备地理覆盖或充足资源，将独立 CDN 互联起来可以整合覆盖范围与容量，实现从内容服务提供商（CSP）到终端用户的端到端分发。[3]

IETF 在 RFC 6707（信息性，2012 年 9 月，作者为 B. Niven-Jenkins、F. Le Faucheur 和 N. Bitar）中定义了该问题域，并在 RFC 7336（信息性，2014 年 8 月，作者为 L. Peterson、B. Davie 和 R. van Brandenburg）中确立了总体架构；RFC 7336 废止了 RFC 3466。[3][4] 在 CDNI 模型中，CSP 与权威上游 CDN（`uCDN`）签约，上游 CDN 既可自行处理请求，也可将分发委派给一个或多个下游 CDN（`dCDN`），例如由 NSP 运营的 CDN；最终向终端用户提供服务的下游 CDN 称为分发 CDN（Delivering CDN）。[3][4]

在互联分发流程中，用户代理首先联系上游 CDN，上游 CDN 可通过 DNS 重定向或 HTTP 重定向将请求转发至更靠近用户的下游 CDN。[3][4] RFC 7336 区分了迭代式 CDNI 请求重定向（上游 CDN 根据本地逻辑将客户端重定向至下游 CDN 的请求路由系统）与递归式 CDNI 请求重定向（上游 CDN 先查询下游 CDN 的重定向接口并整合其响应，从而可能将客户端直接重定向至下游代理服务器）。[4] 若下游 CDN 缺少所请求的对象，它会从上游 CDN 获取该对象，必要时上游 CDN 再从 CSP 获取。[3] CDNI 规则和元数据适用于 `CDN-Domain`（代表一组内容的 FQDN），而 `Distinguished CDN-Domain` 仅用于 CDN 间的获取或重定向，不会出现在客户端请求中。[4]

| CDNI 接口 | 操作时机 | RFC 6707 与 RFC 7336 定义的作用 |
| --- | --- | --- |
| CDNI 控制接口（Control Interface） | 初始配置与触发操作 | 协调管理操作，并包含触发器接口（Trigger Interface），用于在 CSP 操作时预置、重新验证和清除元数据与内容。[3][4] |
| CDNI 请求路由接口（Request Routing Interface） | 同步与异步 | 处理上下游 CDN 之间的 DNS 或 HTTP 请求重定向，并交换动态覆盖范围通告。[3][4] |
| CDNI 元数据接口（Metadata Interface） | 同步或异步 | 在互联 CDN 之间交换限定于 CDN-Domain 范围的分发元数据与分发策略。[3][4] |
| CDNI 日志接口（Logging Interface） | 实时与离线 | 在对等 CDN 之间交换分发日志记录，用于计费和运维可视化。[3][4] |

## 内容分发网络的局限性、缓存过期与安全风险

内容分发网络部署在缓存过期、共享缓存隐私、第三方服务中断以及资源完整性方面存在运维与安全权衡。[1][2][6][7]

由于 HTTP 采用单一的端到端新鲜度模型，在 CDN 上配置比下游缓存更长的新鲜度生存期可能会降低下游缓存的效率。[2] RFC 9213 以带有 `Age: 1800`、`Cache-Control: max-age=600` 和 `CDN-Cache-Control: max-age=3600` 的响应说明了这一交互：经过 30 分钟后，该对象对 CDN 缓存而言依然新鲜，但在受 600 秒上限约束的下游缓存看来已经处于过期状态。[2] 此外，无法连接源站服务器的断连缓存可在允许的条件下提供过期响应。[1]

依赖外部 CDN 会引入第三方可用性依赖。[6] MDN Web Docs 指出，如果第三方 CDN 发生故障、在特定地区被封锁或永久关闭，依赖它的网站将出现功能异常。[6] 在某些场景下，从外部 CDN 域名加载 Bootstrap 或 jQuery 等第三方库也可能降低性能：浏览器必须针对第三方主机执行额外的 DNS 查询与连接建立，而且现代浏览器会按来源对 HTTP 缓存进行分区（使用包含引用站点标识的双重键机制，以缓解隐私与时序攻击风险），因此同一第三方库仍须在每个站点上单独下载。[1][6]

共享 CDN 缓存同样带来安全与数据隔离风险。[1][6][7] 第三方 CDN 一旦遭到入侵，攻击者便可向依赖站点的访问者分发恶意内容，因此对第三方静态资源必须采取子资源完整性（Subresource Integrity，SRI）等客户端防护措施。[6] 若在共享缓存中存储个性化响应时未标记 `Cache-Control: private`，就可能将某位用户的数据暴露给其他用户，且仅存在 Cookie 并不会将 HTTP 响应标记为私有。[7] RFC 9111 进一步将缓存投毒、时序攻击以及敏感信息缓存列为 HTTP 缓存系统的核心安全考量。[1]

## 常见问题

### 什么是内容分发网络（CDN）？

内容分发网络（CDN）是一组在地理上分布式部署的服务器，用于存储网页内容的副本，并从靠近终端用户的边缘位置响应请求。作为客户端与源站服务器之间的托管共享 HTTP 缓存，CDN 可以降低延迟、减轻源站服务器负载并提高可用性。 [6][7][8]

### CDN-Cache-Control 与标准 Cache-Control 有何区别？

RFC 9111 中定义的标准 Cache-Control 指令广泛适用于浏览器和共享缓存，按层级定向控制的能力有限。2022 年 6 月在 RFC 9213 中标准化的 CDN-Cache-Control 是一种专门针对 CDN 缓存的字典结构化字段（Dictionary Structured Field），使发布者能够设定独立的 CDN 缓存策略，同时 CDN 会对该响应忽略 Cache-Control 和 Expires。 [2][7]

### RFC 4786 中的 BGP 任播路由是什么？

RFC 4786（BCP 126）中记录的全局范围 BGP 任播从多个独立位置通告同一个 IP 服务地址，由路由系统根据自身拓扑和请求发起的位置决定由哪个节点处理请求。它无需轮询 DNS 转引即可支持服务可靠性和粗粒度扩展，但各节点间的流量负载通常仍会保持不均衡。 [5]

### 什么是 CDN 互联（CDNI）？

RFC 6707 概述并在 RFC 7336 中构建框架的 CDN 互联（CDNI），是独立 CDN 之间的一种协作关系，允许具有权威性的上游 CDN 将内容分发委派给更靠近终端用户的下游 CDN。它通过四个接口领域协调分发：控制（包括触发器接口）、请求路由、元数据和日志记录。 [3][4]

### CDN 会暴露个性化用户数据或提供过期内容吗？

是的。由于 CDN 作为共享缓存运行，在未标记 Cache-Control: private 指令的情况下存储个性化响应可能会将一名用户的内容暴露给其他用户，且仅存在 Cookie 并不会将响应标记为私有。此外，为 CDN 配置比下游缓存更长的新鲜度生存期，可能导致响应到达下游缓存时已经过期。 [2][7]

### 从第三方 CDN 加载静态库有哪些风险？

MDN Web Docs 列出了与自托管静态资源相比的三项缺点：第三方服务中断、地区封锁或永久关闭可能导致依赖该 CDN 的网站失效；若缺乏子资源完整性（SRI）等防护措施，遭入侵的 CDN 可能分发恶意文件；此外，独立来源会增加 DNS 查询和连接开销，而浏览器缓存分区也会阻止跨站点的资源复用。 [6]

## 可引用的句子

- IETF 于 2022 年 6 月发布标准跟踪（Standards Track）HTTP 缓存规范 RFC 9111（STD 98），废止了 RFC 7234。 [1]
- 由 Akamai、Fastly 和 Cloudflare 的作者于 2022 年 6 月发布的 RFC 9213，为 CDN 缓存定义了 CDN-Cache-Control HTTP 响应头。 [2]
- 根据 RFC 9213，实现定向缓存控制字段的缓存必须支持 max-age、must-revalidate、no-store、no-cache 和 private 指令。 [2]
- 2006 年 12 月发布的 RFC 4786（BCP 126）记录了通过 IGP 或 BGP 上的 IPv4 和 IPv6 任播将服务分布到多个位置的运维实践。 [5]
- RFC 6707（2012 年 9 月）和 RFC 7336（2014 年 8 月）定义了内容分发网络互联（CDNI）的问题陈述和框架；废止 RFC 3466 的是 RFC 7336。 [3][4]
- 现代浏览器出于隐私原因按来源（origin）对 HTTP 缓存进行分区，导致每个网站都必须单独下载第三方 CDN 上的库文件。 [6]
- CDN 等托管缓存允许通过控制台、API 调用或重启显式删除已存储的响应，这一能力不在基础 HTTP 缓存规范的范围内。 [7]
- 截至 2026-11-23，Amazon CloudFront 默认在边缘站点将对象缓存 24 小时，最小过期时间为 0 秒，且没有固定的最大过期时间。 [8]

## 时间线

- 2006-12: IETF 发布 RFC 4786（BCP 126）《Operation of Anycast Services》，记录了局部范围 IGP 与全局范围 BGP 任播实践。 [5]
- 2012-09: IETF 发布 RFC 6707《Content Distribution Network Interconnection (CDNI) Problem Statement》，界定了四类 CDNI 接口的范围。 [3]
- 2014-08: IETF 发布 RFC 7336《Framework for Content Distribution Network Interconnection (CDNI)》，废止了 RFC 3466。 [4]
- 2022-06: IETF 发布废止 RFC 7234 的 RFC 9111（STD 98）《HTTP Caching》，并同步发布标准化 CDN-Cache-Control 响应头的 RFC 9213《Targeted HTTP Cache Control》。 [1][2]

## 来源

1. RFC 9111: HTTP Caching. Internet Engineering Task Force (IETF). 发布于 2022-06. https://www.rfc-editor.org/rfc/rfc9111.txt (访问于 2026-11-23; tier 1: government or public registry)
2. RFC 9213: Targeted HTTP Cache Control. Internet Engineering Task Force (IETF). 发布于 2022-06. https://www.rfc-editor.org/rfc/rfc9213.txt (访问于 2026-11-23; tier 1: government or public registry)
3. RFC 6707: Content Distribution Network Interconnection (CDNI) Problem Statement. Internet Engineering Task Force (IETF). 发布于 2012-09. https://www.rfc-editor.org/rfc/rfc6707.txt (访问于 2026-11-23; tier 1: government or public registry)
4. RFC 7336: Framework for Content Distribution Network Interconnection (CDNI). Internet Engineering Task Force (IETF). 发布于 2014-08. https://www.rfc-editor.org/rfc/rfc7336.txt (访问于 2026-11-23; tier 1: government or public registry)
5. RFC 4786: Operation of Anycast Services. Internet Engineering Task Force (IETF). 发布于 2006-12. https://www.rfc-editor.org/rfc/rfc4786.txt (访问于 2026-11-23; tier 1: government or public registry)
6. CDN - Glossary | MDN. MDN Web Docs. 发布于 2025-07-11. https://developer.mozilla.org/en-US/docs/Glossary/CDN (访问于 2026-11-23; tier 3: official site)
7. HTTP caching - HTTP | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching (访问于 2026-11-23; tier 3: official site)
8. What is Amazon CloudFront? - Amazon CloudFront. Amazon Web Services. https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "内容分发网络." 版本 6b8fdf60, 2026-11-25. https://mimirwiki.com/zh/wiki/content-delivery-network
