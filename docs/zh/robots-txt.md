---
title: "robots.txt"
subtitle: "依据机器人排除协议（RFC 9309）告知网络爬虫可访问哪些 URI 的纯文本文件"
canonical_url: https://mimirwiki.com/zh/wiki/robots-txt
language: zh
page_class: anchor
revision_sha256: b3c3721a0a70a38111ccd1aba7a52e9a345091246f709a163032cfb4147b9c79
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/zh/wiki/robots-txt.md
  txt: https://mimirwiki.com/zh/wiki/robots-txt.txt
  json: https://mimirwiki.com/zh/wiki/robots-txt.json
  jsonld: https://mimirwiki.com/zh/wiki/robots-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/robots-txt
  ko: https://mimirwiki.com/ko/wiki/robots-txt
  ja: https://mimirwiki.com/ja/wiki/robots-txt
  es: https://mimirwiki.com/es/wiki/robots-txt
---

# robots.txt

> robots.txt 是依据机器人排除协议（RFC 9309）放置在网站根路径（/robots.txt）下的纯文本文件，用于告知自动化爬虫可以或不可以访问哪些 URI。Martijn Koster 于 1994 年最初定义了这一惯例，IETF 于 2022 年 9 月将其标准化。其规则仅为建议性质，不提供访问授权功能。

robots.txt 是依据机器人排除协议（Robots Exclusion Protocol，REP）托管在 Web 或 FTP 服务顶层路径 /robots.txt 处的 UTF-8 纯文本文件，用于向称为爬虫的自动化客户端指明可以或不可以访问哪些 URI。Martijn Koster 于 1994 年 6 月根据邮件列表共识最初记录了这一惯例，互联网工程任务组（IETF）于 2022 年 9 月将其发布为标准轨道文档 RFC 9309。该文件将 User-agent 分组与 Allow 和 Disallow 路径规则配对组织，同时支持 Sitemap 等可选记录。RFC 9309 将 robots.txt 规则定义为请求爬虫遵守的建议性声明，该协议本身不提供访问授权或技术强制手段。

**别名:** /robots.txt, 机器人排除协议, Robots Exclusion Protocol, REP, RFC 9309, 机器人排除标准

## 关键事实

- **标准:** RFC 9309（IETF 标准轨道，2022 年 9 月） [1]
- **原作者与日期:** Martijn Koster（1994-06-30 邮件列表共识） [4]
- **规范位置:** 服务根目录下的 /robots.txt（UTF-8，text/plain） [1]
- **核心指令:** User-agent、Allow、Disallow（及可选的 Sitemap） [1]
- **Google 文件大小限制:** 500 KiB；超出限制的内容将被忽略 (截至 2026-11-23) [6]

## 事实摘要

- **协议名称:** 机器人排除协议（Robots Exclusion Protocol，REP） [1]
- **IETF 规范:** RFC 9309（建议标准，2022 年 9 月） [3]
- **RFC 9309 作者:** Martijn Koster、Gary Illyes、Henner Zeller、Lizzi Sassman [3]
- **初始共识日期:** 1994-06-30 [4]
- **文件路径:** /robots.txt（全小写，顶层目录） [1]
- **编码与媒体类型:** UTF-8，text/plain [1]
- **标准化指令:** User-agent、Allow、Disallow [1]
- **特殊字符:** #（注释）、*（通配符）、$（匹配结尾） [1]
- **Google 文件大小限制:** 500 KiB (截至 2026-11-23) [6]
- **Google 默认缓存时长:** 最长 24 小时 (截至 2026-11-23) [6]
- **参考 C++ 解析器:** github.com/google/robotstxt（Apache-2.0 许可证） [8]
- **相关 IETF 工作组:** AI Preferences（aipref），在 charter-ietf-aipref-01 下活跃 (截至 2026-11-23) [2]

## robots.txt 的概念与起源

robots.txt 是依据机器人排除协议（Robots Exclusion Protocol，REP）托管在网站或 FTP 主机顶层路径下的纯文本文件，用于声明自动化爬虫可以访问哪些 URI。[1][5] 服务所有者发布该文件，以便为编入索引而遍历链接的搜索引擎爬虫等自动化客户端在请求站点资源之前，能够确定应避开哪些路径。[1][7]

Martijn Koster 最初在《A Standard for Robot Exclusion》中记录了该协议，该文档记载了 1994 年 6 月 30 日在 `robots` 邮件列表（`robots-request@nexor.co.uk`）达成并在 Technical World Wide Web 邮件列表（`www-talk@info.cern.ch`）讨论的共识。[1][4] 该文档旨在应对 1993 年和 1994 年发生的一系列事件：当时网络机器人（亦称漫游者或蜘蛛）因高速发送请求而导致服务器过载、重复抓取相同文件，或遍历深层虚拟目录树、临时或重复内容以及具有投票等副作用的 CGI 脚本。[4] 选择位于 `/robots.txt` 的单一文件，是因为任何现有 Web 服务器无需额外配置即可提供该文件，爬虫可通过一次请求获取策略，且该文件名符合各操作系统的命名规则，命名冲突风险极低。[4]

在长达 25 年的时间里，REP 一直作为未经标准组织正式背书的事实标准运行，仅记载于 1994 年规范以及 1997 年题为《A Method for Web Robots Control》的互联网草案中。[4][5][8] 1994 年的原始格式仅包含 `User-agent` 和 `Disallow` 字段，未包含 `Allow` 字段和通配符匹配。[4][5] 2022 年 9 月，互联网工程任务组（IETF）基于个人草案 `draft-koster-rep` 将 RFC 9309（《Robots Exclusion Protocol》）发布为标准轨道的建议标准，由 Martijn Koster、Gary Illyes、Henner Zeller 和 Lizzi Sassman 撰写，Murray Kucherawy 担任负责领域总监。[1][3] RFC 9309 新增了正式的协议语法，标准化了 `Allow` 与通配符字符，并规定了错误处理与缓存规则。[1]

## robots.txt 的文件位置、格式与适用范围

robots.txt 文件必须以全小写路径 `/robots.txt` 放置在服务的顶层目录中，遵循 `scheme:[//authority]/robots.txt` 的 URI 形式（例如 `https://www.example.com/robots.txt` 或 `ftp://ftp.example.com/robots.txt`）。[1][5] RFC 9309 要求文件采用 UTF-8 编码（RFC 3629），以互联网媒体类型 `text/plain`（RFC 2046）提供，并使用 CR、LF 或 CRLF 作为行尾换行符。[1][6] 在 Google 搜索的实现中，支持的协议包括 HTTP 和 HTTPS（使用非条件 HTTP GET 请求获取）以及 FTP（通过匿名 `RETR` 命令获取）。[6]

robots.txt 文件中的规则仅适用于获取该文件时所对应的确切主机、协议和端口号。[6] 根据 Google 文档的说明，其适用范围遵循以下边界：[6]

- **子域与子目录**：位于 `https://example.com/robots.txt` 的文件不涵盖 `https://other.example.com/`，放置在 `/folder/robots.txt` 等子目录中的文件无效。
- **协议与端口**：`https://example.com/` 上的规则不适用于 `http://example.com/` 或 `ftp://example.com/`；标准端口（HTTP 为 80，HTTPS 为 443，FTP 为 21）与默认主机名等效，而 `:8181` 等非标准端口需要各自的独立文件。
- **IDN 与 IP 地址**：国际化域名（IDN）与其 Punycode 形式（RFC 3492）等效；托管在 IP 地址主机名上的文件仅适用于通过该 IP 地址进行的抓取。

截至 2026-11-23，Google 对 robots.txt 实施 500 KiB 的最大文件大小限制，并忽略超出该限制的任何内容。[6] Google 的解析器还会忽略无效行（包括文件开头的 Unicode 字节顺序标记 BOM），并应用响应中发现的所有有效规则。[6]

## robots.txt 的指令、语法与匹配规则

RFC 9309 定义的 robots.txt 语法采用扩充巴科斯-瑙尔范式（ABNF，RFC 5234），将键值对行组织为由一行或多行 `User-agent` 后接 `Allow` 和 `Disallow` 规则组成的分组。[1] 字段名不区分大小写，注释以 `#` 开头，爬虫应忽略出现在第一行 `User-agent` 之前的 `Allow` 和 `Disallow` 规则。[1][4][6]

| 指令或标记 | 在 RFC 9309 及爬虫实现中的作用 |
| --- | --- |
| `User-agent` | 通过产品标记（ASCII 字母、`_`、`-`）标识目标爬虫，或使用 `*` 表示默认规则；匹配时不区分大小写。[1] |
| `Disallow` | 指定以 `/` 开头、所匹配爬虫不应访问的 URI 路径前缀；值为空时不施加限制。[1][6] |
| `Allow` | 指定以 `/` 开头、所匹配爬虫可以访问的 URI 路径前缀，用于允许被禁止目录中的子路径。[1][6] |
| `Sitemap` | RFC 9309 允许且不会终止分组的非核心记录；Google 支持通过完整 URL 指定站点地图。[1][6] |

每个爬虫选定自身的产品标记（该标记应作为其 HTTP `User-Agent` 标头 RFC 9110 的子串出现），并合并所有与该标记匹配的分组规则。[1] 当没有特定分组匹配时，若存在 `User-agent: *` 分组，爬虫将遵循该分组；若两者均不存在或文件为空，则不适用任何规则。[1][4] 路径匹配从路径的第一个八位字节开始，且应区分大小写。[1] 在比较之前，非 ASCII 八位字节和 RFC 3986 保留字符必须进行百分号编码，而经过百分号编码的非保留 ASCII 字符必须解码。[1] RFC 9309 要求支持三个特殊字符：用于注释的 `#`、匹配零个或多个任意字符的 `*`，以及标记匹配模式结尾的 `$`；字面量 `*` 和 `$` 分别以 `%2A` 和 `%24` 进行匹配。[1]

当多条规则匹配同一个 URI 时，爬虫必须应用最具体的匹配项，即按八位字节数计算的较长模式。[1] 如果某条 `Allow` 规则与某条 `Disallow` 规则的具体程度相同，则应采用 `Allow` 规则；`/robots.txt` URI 本身隐式允许访问。[1] 根据 RFC 9309，只要不干扰分组解析，爬虫可以解释站点地图等其他记录。[1] Google 支持 `user-agent`、`allow`、`disallow` 和 `sitemap`，不支持 `crawl-delay`。[6] 根据站点地图协议，XML 站点地图是包含 `<url>` 和 `<loc>` 条目的 UTF-8 `<urlset>` 文档，单个文件上限为 50,000 个 URL 且未压缩大小不超过 50 MB（52,428,800 字节），多个站点地图可列于 `<sitemapindex>` 文件中。[10]

为减少不同实现之间的解析差异，Google 在 Apache-2.0 许可证下将生产环境使用的 C++ robots.txt 解析器与匹配器库开源至 `github.com/google/robotstxt`。[8] 该仓库包含一个命令行测试程序（`robots_main`），可根据本地 robots.txt 文件评估指定的用户代理与 RFC 3986 URI，允许时返回退出码 0，禁止时返回 1。[8]

## robots.txt 的 HTTP 状态码处理与缓存

爬虫根据获取 `/robots.txt` 时返回的 HTTP 状态码或网络结果来决定如何应用 robots.txt 规则。[1][6] RFC 9309 定义了成功访问、重定向、不可用响应和无法访问错误四类基准情形，而搜索引擎则另行发布了运行超时与缓存策略。[1][6]

| 响应类别 | RFC 9309 规范 | Google 爬虫处理方式（截至 2026-11-23） |
| --- | --- | --- |
| `2xx`（成功） | 解析并遵循文件中的有效规则。[1] | 按服务器提供的内容处理 robots.txt 文件。[6] |
| `3xx`（重定向） | 至少跟踪五次连续重定向（如 301 或 302），即使跨授权域亦然，并将获取的规则应用于初始授权域；超过五次后，爬虫可将文件视为不可用。[1] | 至少跟踪五次重定向跳转，随后停止并将响应视为 404；不跟踪通过框架、JavaScript 或 meta refresh 实现的逻辑重定向。[6] |
| `4xx`（不可用） | HTTP 400-499 表示文件不可用；爬虫可以访问服务器上的任意资源。[1] | 除 429 之外的所有 4xx 错误均视为无 robots.txt（无抓取限制）；除 429 外的 4xx 状态码（包括 401 和 403）不会降低抓取速率。[6] |
| `5xx` 与网络错误（无法访问） | HTTP 500-599 或网络错误导致文件处于未定义状态；爬虫必须假定完全禁止抓取。[1] | 停止抓取 12 小时并持续重试；在随后的 30 天内使用最后一次有效的缓存副本（若无缓存则假定无限制）；30 天后，若站点整体可访问则视为无限制，若站点存在普遍可用性问题则停止抓取。[6] |

Google 将 DNS 错误、超时、无效响应、连接重置或中断以及 HTTP 分块错误与 5xx 服务器错误归为同类处理。[6] 遇到 HTTP 503 响应时，Google 会以更高频率重试获取 robots.txt。[6]

截至 2026-11-23，Google 通常会将 robots.txt 文件的内容缓存最长 24 小时；当刷新尝试因超时或 5xx 错误失败时，可能会更长时间保留缓存版本，并且不同的 Google 爬虫之间可能会共享缓存规则。[6] Google 也可能依据 HTTP `Cache-Control` `max-age` 响应标头延长或缩短缓存有效期。[6]

## robots.txt 的建议性局限、安全性与索引控制

RFC 9309 明确指出，robots.txt 规则并非访问授权机制，是否遵守完全取决于各个爬虫自身的选择。[1][7] 1994 年的原始规范同样指出，没有任何一方强制执行这些规则，也无法保证当前或未来的所有机器人都会遵守。[4] 恶意自动化客户端（包括漏洞扫描器以及垃圾邮件发送者使用的电子邮件地址采集器）通常会直接忽略 robots.txt。[5]

由于 `/robots.txt` 对任何客户端均公开可访问，在其中列出路径会暴露管理员希望爬虫跳过的服务器目录。[5] robotstxt.org 和 Google 均在文档中说明，robots.txt 无法隐藏机密信息，保护私密文件必须依赖密码保护等访问控制机制。[5][7] 此外，Google 文档指出，REP 不适用于由用户触发的抓取工具（例如订阅源抓取），也不适用于为保护用户安全而运行的爬虫（例如恶意软件分析）。[6]

对于搜索引擎而言，robots.txt 用于管理抓取流量和带宽消耗，而索引行为则取决于文件类型及单独的指令。[7][9] 在 robots.txt 中屏蔽 HTML 页面、PDF 或其他文本类文档可以阻止 Google 抓取该页面，但如果外部页面使用描述性锚文本链接到该 URL，Google 仍可在不访问该页面的情况下将其编入索引，并在搜索结果中显示不含摘要描述的条目。[7] 要阻止可抓取的页面出现在搜索结果中，需要使用页面级指令，例如 HTML `<meta name="robots">` 元素（如 `noindex`）或 `X-Robots-Tag` HTTP 响应标头，或者通过身份验证限制访问。[7][9] 对于图片、视频和音频等媒体文件，Google 文档指出 robots.txt 可阻止这些文件出现在 Google 搜索结果中；而屏蔽关键的样式表或脚本资源文件则可能导致 Google 无法准确渲染和分析依赖它们的页面。[7]

## robots.txt、IETF AIPREF 与 AI 爬虫偏好信号

除搜索引擎抓取外，robots.txt 也被纳入面向人工智能（AI）模型开发、部署与使用的内容偏好表达标准化工作中。[2] 截至 2026-11-23，IETF 的 AI Preferences（`aipref`）工作组在获批章程 `charter-ietf-aipref-01` 下活跃于 Web 与互联网传输（`wit`）领域，由 Mark Nottingham 和 Suresh Krishnan 担任主席，Mike Bishop 担任领域总监。[2]

`aipref` 章程定义了三项交付成果：独立于传输机制、用于描述 AI 相关内容偏好的标准轨道词汇表文档（`draft-ietf-aipref-vocab`）；在 IETF 协议和格式中将这些偏好与内容关联的标准轨道附加规范（`draft-ietf-aipref-attach`）；以及协调多种偏好表达的标准方法。[2] 截至 2026-11-23，这两份草案交付物在 IETF Datatracker 上列出的里程碑时间均为 2026 年 8 月。[2] 章程明确将知名 URI（RFC 8615，例如机器人排除协议 RFC 9309）与 HTTP 响应标头字段并列为附加机制，并指示该工作组与国际新闻电信理事会（IPTC）、PLUS Coalition、WHATWG 及 W3C 保持联络。[2]

与 RFC 9309 的建议性边界一致，`aipref` 章程将四个领域排除在工作范围之外：偏好的技术强制执行、用于客户端或爬虫身份验证与授权的应用层协议、内容偏好注册表，以及针对 AI 训练的审计或透明度措施。[2] 在标准组织之外，基础设施提供商也推出了将搜索发现与 AI 训练分离的控制机制：2026 年 9 月 15 日，[Cloudflare](https://mimirwiki.com/zh/wiki/cloudflare) 宣布推出与 Apple、Google 和 Microsoft 共同构建共享模型的控制功能及 Accountable 标识，使站点所有者能够在保持搜索可发现性的同时禁止 AI 训练。[11]

## 常见问题

### 什么是 robots.txt 文件？

robots.txt 文件是依据机器人排除协议（RFC 9309）放置在 Web 或 FTP 主机根目录 /robots.txt 处的 UTF-8 纯文本文件。它用于告知自动化爬虫可以或不可以访问该主机上的哪些 URI 路径。Martijn Koster 于 1994 年 6 月最初记录了这一惯例，IETF 则于 2022 年 9 月发布了 RFC 9309。 [1][4]

### 根据 RFC 9309，robots.txt 支持哪些指令？

RFC 9309 标准化了三条核心指令：User-agent、Allow 和 Disallow，以及三个特殊字符：用于注释的 #、用于通配符序列的 * 和用于路径末尾匹配的 $。在不中断分组解析的前提下，爬虫还可以解释 Sitemap 等附加记录。截至 2026-11-23，Google 支持 User-agent、Allow、Disallow 和 Sitemap，不支持 crawl-delay。 [1][6]

### 爬虫如何处理针对 robots.txt 的 HTTP 4xx 和 5xx 错误？

根据 RFC 9309，HTTP 400-499 响应表示 robots.txt 不可用，因此爬虫可以访问服务器上的任意资源；而 HTTP 500-599 响应表示文件无法访问，爬虫必须假定完全禁止抓取。截至 2026-11-23，Google 将除 429 之外的 4xx 错误视为无抓取限制，遇到 5xx 错误时会停止抓取 12 小时，之后最多 30 天内回退使用最后一次缓存的副本。 [1][6]

### Google 对 robots.txt 的文件大小限制是多少？

截至 2026-11-23，Google 对 robots.txt 实施的最大文件大小限制为 500 KiB。超出 500 KiB 上限的任何内容都会被 Google 的解析器忽略。 [6]

### robots.txt 能否阻止网页出现在搜索结果中或保护私密文件？

不能。RFC 9309 明确指出 robots.txt 规则并非访问授权机制，不遵守协议的爬虫可以忽略该文件。对于网页而言，如果其他页面链接到被禁止的 URL，Google 仍可在不访问该页面的情况下将其编入索引；因此，要从搜索结果中排除页面或保护私密文件，需要使用 HTML meta robots 元素、X-Robots-Tag HTTP 标头或密码保护等机制。 [1][7][9]

### IETF AIPREF 工作组与 robots.txt 有何关联？

截至 2026-11-23，处于活跃状态的 IETF AI Preferences（aipref）工作组依据章程，负责标准化一套词汇表及协议附加方法，用于表达面向 AI 系统的内容收集与处理偏好。其获批章程明确涵盖通过知名 URI（RFC 8615，例如机器人排除协议 RFC 9309）以及 HTTP 响应标头字段附加这些偏好。 [2]

## 可引用的句子

- Martijn Koster 根据 1994 年 6 月 30 日邮件列表达成的共识，最初记录了机器人排除协议。 [1][4]
- IETF 于 2022 年 9 月将机器人排除协议发布为标准轨道文档 RFC 9309。 [1][3]
- RFC 9309 要求 robots.txt 文件采用 UTF-8 编码、媒体类型为 text/plain，并在全小写的路径 /robots.txt 下提供。 [1]
- 根据 RFC 9309，爬虫应按八位字节长度应用最具体的路径匹配规则；当 Allow 规则与 Disallow 规则等效时，Allow 规则优先。 [1]
- 根据 RFC 9309，针对 robots.txt 的 HTTP 400-499 响应允许访问服务器上的任意资源，而 HTTP 500-599 响应则要求假定完全禁止访问。 [1]
- 截至 2026-11-23，Google 对 robots.txt 实施 500 KiB 的文件大小上限，并忽略超出该上限的内容。 [6]
- Google 文档说明，即使在 robots.txt 中屏蔽了某个网页，只要其他页面链接到该 URL，该 URL 仍可能出现在 Google 搜索结果中。 [7]
- 截至 2026-11-23，处于活跃状态的 IETF AI Preferences（aipref）工作组依据章程，负责制定使用包括 RFC 9309 和 HTTP 响应标头字段在内的 IETF 协议附加 AI 内容偏好的规范。 [2]

## 时间线

- 1994-06-30: 邮件列表就 Martijn Koster 撰写的《A Standard for Robot Exclusion》达成共识。 [4]
- 1997: 互联网草案《A Method for Web Robots Control》记录了 robots.txt 排除机制。 [5]
- 2022-09: IETF 将 RFC 9309（《Robots Exclusion Protocol》）发布为标准轨道的建议标准。 [1][3]
- 2026-09-15: Cloudflare 与 Apple、Google 和 Microsoft 宣布推出控制功能与 Accountable 标识，以在保持站点搜索可发现性的同时禁止 AI 训练。 [11]

## 来源

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (访问于 2026-11-23; tier 1: government or public registry)
2. AI Preferences (aipref). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (访问于 2026-11-23; tier 1: government or public registry)
3. RFC 9309 - Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://datatracker.ietf.org/doc/rfc9309/ (访问于 2026-11-23; tier 1: government or public registry)
4. A Standard for Robot Exclusion - The Web Robots Pages. robotstxt.org. 发布于 1994-06-30. https://www.robotstxt.org/orig.html (访问于 2026-11-23; tier 3: official site)
5. About /robots.txt - The Web Robots Pages. robotstxt.org. https://www.robotstxt.org/robotstxt.html (访问于 2026-11-23; tier 3: official site)
6. How Google Interprets the robots.txt Specification | Google Crawling Infrastructure | Crawling infrastructure | Google for Developers. Google Search Central. https://developers.google.com/crawling/docs/robots-txt/robots-txt-spec (访问于 2026-11-23; tier 3: official site)
7. Robots.txt Introduction and Guide | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/robots/intro (访问于 2026-11-23; tier 3: official site)
8. GitHub - google/robotstxt: The repository contains Google's robots.txt parser and matcher as a C++ library (compliant to C++11).. Google (GitHub). https://github.com/google/robotstxt (访问于 2026-11-23; tier 3: official site)
9. Robots.txt - Glossary | MDN. MDN Web Docs. 发布于 2025-11-26. https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt (访问于 2026-11-23; tier 3: official site)
10. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (访问于 2026-11-23; tier 3: official site)
11. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 发布于 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "robots.txt." 版本 b3c3721a, 2026-11-23. https://mimirwiki.com/zh/wiki/robots-txt
