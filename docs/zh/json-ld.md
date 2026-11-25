---
title: "JSON-LD"
subtitle: "用于在 JSON 中序列化关联数据的 W3C 标准格式"
canonical_url: https://mimirwiki.com/zh/wiki/json-ld
language: zh
page_class: anchor
revision_sha256: ee5045fa88be4ec4a80eeaf535fcd407ad11b0576254b96ec43965a12ce17f4c
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/json-ld.md
  txt: https://mimirwiki.com/zh/wiki/json-ld.txt
  json: https://mimirwiki.com/zh/wiki/json-ld.json
  jsonld: https://mimirwiki.com/zh/wiki/json-ld.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-ld
  ko: https://mimirwiki.com/ko/wiki/json-ld
  ja: https://mimirwiki.com/ja/wiki/json-ld
  es: https://mimirwiki.com/es/wiki/json-ld
---

# JSON-LD

> JSON-LD 是用于在有效 JSON 中序列化关联数据的 W3C 推荐标准。它通过上下文将对象键名映射到全局标识符，使应用程序能够跨网站理解和关联数据。JSON-LD 于 2014 年实现标准化，并于 2020 年更新至 1.1 版本，支持 RDF 图、程序化文档转换以及 Schema.org 等 HTML 结构化数据。

JSON-LD（JSON for Linking Data）是由万维网联盟（W3C）制定的推荐标准，定义了一种用于在 Web 上序列化关联数据（Linked Data）的轻量级 JSON 语法。每份 JSON-LD 文档都是符合 RFC 8259 的有效 JSON，使标准 JSON 解析器、Web 服务和基于 JSON 的存储引擎能够直接处理，同时增加了全局资源标识符、上下文、语言标签、数据类型和有向图结构。W3C 于 2014 年 1 月 16 日发布 JSON-LD 1.0，并于 2020 年 7 月 16 日以涵盖语法、处理算法与 API 以及框架化（Framing）的 JSON-LD 1.1 规范套件将其取代。应用程序既可将 JSON-LD 直接作为 JSON 使用，也可在它与资源描述框架（Resource Description Framework，RDF）图和数据集之间进行转换，或将其嵌入 HTML 文档中以配合 Schema.org 等结构化数据词汇表。

**别名:** JSON for Linked Data, JSON for Linking Data, JSON-LD 1.0, JSON-LD 1.1

## 关键事实

- **标准机构:** 万维网联盟（W3C） [1]
- **首个 W3C 推荐标准:** JSON-LD 1.0（2014-01-16） [4]
- **当前 W3C 推荐标准:** JSON-LD 1.1（2020-07-16） (截至 2026-11-23) [1]
- **基础语法:** JSON（RFC 8259） [1]
- **HTML script 类型:** application/ld+json [8]

## 事实摘要

- **类型:** 基于 JSON 的关联数据序列化格式 [1]
- **标准化组织:** 万维网联盟（W3C） [1]
- **负责工作组:** W3C JSON-LD 工作组（章程有效期至 2028 年 1 月） (截至 2026-11-23) [7]
- **首个推荐标准:** JSON-LD 1.0（2014-01-16 发布；2020-11-03 已被取代） [4]
- **当前推荐标准:** JSON-LD 1.1（2020-07-16） (截至 2026-11-23) [1]
- **配套 1.1 推荐标准:** Processing Algorithms and API；Framing [1]
- **1.1 版编辑:** Gregg Kellogg、Pierre-Antoine Champin、Dave Longley [1]
- **1.0 版编辑:** Manu Sporny、Gregg Kellogg、Markus Lanthaler [4]
- **基础格式:** JSON（IETF RFC 8259） [5]
- **数据模型兼容性:** RDF 1.1 图和 RDF 数据集 [6]
- **规范仓库:** github.com/w3c/json-ld-syntax [10]

## JSON-LD 概述

JSON-LD（JSON for Linking Data）是由万维网联盟（W3C）标准化的轻量级语法，用于在 JSON 中序列化关联数据。[1][7] 关联数据将跨文档与跨网站的机器可读数据连接起来，使应用程序能够沿着嵌入的链接从一个数据集跳转至其他站点托管的相关资源。[1][7] JSON-LD 专为基于 Web 的编程环境、可互操作的 REST Web 服务以及 Apache CouchDB 和 MongoDB 等基于 JSON 的存储引擎而设计。[1][7]

每份 JSON-LD 文档都是符合 IETF RFC 8259（该标准取代了 RFC 7159 及更早的 RFC 4627）的有效 JSON，因此现有的 JSON 解析器和库可以直接解析 JSON-LD 文档。[1][4][5] JSON-LD 1.0 最初引用 RFC 4627，而 JSON-LD 1.1 将基础 JSON 引用更新至 RFC 8259。[1][4] 在标准 JSON 的原始类型（字符串、数字、布尔值和 `null`）与结构类型（对象和数组）之外，JSON-LD 增加了基于 IRI 的通用对象标识符、通过上下文实现的术语到 IRI 映射、跨站点资源引用、字符串语言标注、日期与时间等值的数据类型，以及有向图表示能力。[1][5]

JSON-LD 1.0 规范列出了六项设计目标：简洁性、兼容性、表达能力、简明性、对现有 JSON 系统的最小改动以及作为 RDF 使用的可行性。[4] 在基础使用场景中，只需熟悉 JSON 以及 `@context` 和 `@id` 两个关键字即可使用 JSON-LD，无需专用的 JSON-LD 处理器。[4] 在已部署的 JSON API 中，服务器还可以通过 HTTP 响应中的链接关系将现有 JSON 文档与 JSON-LD 上下文关联起来，从而以极小改动将现有 JSON 负载解释为 JSON-LD。[1][4]

## JSON-LD 语法、上下文与关键字

JSON-LD 建立在 JSON 对象和数组之上，同时引入了特定的结构规则以及以 `@` 为前缀的保留关键字。[1] 在 JSON-LD 中，JSON 对象内的成员名称必须唯一，而 RFC 8259 仅建议 JSON 对象名称保持唯一。[1][5] 在普通 JSON 中，数组是有序的值序列；而在 JSON-LD 中，除非显式定义为列表，否则数组集合默认按无序处理。[1][5]

JSON-LD 的核心语法围绕上下文与关键字展开，使 JSON 数据在 Web 尺度上具备无歧义的语义。[1][4]

- `@context`：将 JSON 文档中简短的属性术语映射到完整的 IRI，使不同 JSON 文档中共用的键名具有明确且无歧义的定义。上下文可通过 URL 引用（例如 `https://schema.org/` 或 `https://json-ld.org/contexts/person.jsonld`），在上下文中将术语或其 `@id` 赋值为 `null` 可显式解除该术语与 IRI 的关联。[1][7][8]
- `@id`：为节点对象分配以 IRI 表示的通用标识符，使其他对象或外部文档能够引用同一资源。[1][4][7]
- `@type`：指定节点对象的类型（例如 Schema.org 标记中的 `Recipe` 或 `Person`）或为类型化值关联数据类型，也可与 `@set` 结合使用。[1][8]
- `null`：在文档主体中重置或忽略值，并在 `@context` 内部解除术语映射。[1]

JSON-LD 1.1 是 JSON-LD 1.0 的超集，除规范另有说明外，保持了对 1.0 文档的兼容性。[1] 其规范涵盖了 JSON-LD 1.1 处理模式、默认词汇表、基础 IRI、紧凑 IRI、关键字别名、作用域上下文、上下文传播、导入上下文、受保护术语定义、JSON 字面量、类型强制转换、带基础书写方向的字符串国际化、嵌套属性、反向属性、包含节点、多种索引值形式（数据索引、基于属性的索引、语言索引、节点标识符索引和节点类型索引），以及带图容器的命名图。[1]

## JSON-LD 文档形态、处理 API 与框架化

JSON-LD 用于表示有向图，这意味着相同的底层信息可以序列化为多种形态。[1][3] 为了支持确定性的程序化处理，JSON-LD 1.1 规范套件定义了四种文档形态：展开形态（Expanded）、压缩形态（Compacted）、扁平化形态（Flattened）和框架化形态（Framed）。[1]

配套的 W3C 推荐标准 JSON-LD 1.1 Processing Algorithms and API 定义了在各文档形态之间转换以及与 RDF 相互转换的算法，同时使用 Web IDL 描述了 `JsonLdProcessor` 应用程序编程接口（API）和 `JsonLdOptions` 配置类型。[2] 其核心处理能力包括上下文处理（创建术语定义、创建反向上下文与术语选择）、展开（展开 IRI 与值）、压缩（压缩 IRI 与值）、扁平化（生成和合并节点映射并分配空白节点标识符）、远程文档与上下文获取、HTML 内容处理算法，以及支持数据往返转换的 RDF 序列化与反序列化。[2]

第三项 W3C 推荐标准 JSON-LD 1.1 Framing 扩展了 `JsonLdProcessor` 和 `JsonLdOptions`，使开发者能够按示例查询，并在 JSON-LD 图上强制应用特定的树状布局。[3] 关联数据图由相互独立的陈述（三元组）构成，而应用程序通常期望嵌套的 JSON 对象树；框架（Frame）规定了如何将关于每个主语的陈述归组到 `{` 与 `}` 定界符内，以及相关主语如何嵌套。[3] Framing 规范支持按属性、通配符、缺失属性、值和 `@id` 进行匹配，也支持空框架、默认内容、反向框架化、命名图框架化，以及五项框架化标志：对象嵌入（object embed）、显式包含（explicit inclusion）、省略默认值（omit default）、省略图（omit graph）和全部必需（require all）。[3]

## JSON-LD 与 RDF 数据模型

JSON-LD 既面向无需了解资源描述框架（RDF）即可直接使用 JSON 的开发者，也面向处理 RDF 数据的系统。[1][4] 发布于 2014 年 2 月 25 日的 W3C 推荐标准《RDF 1.1 Concepts and Abstract Syntax》明确将 JSON-LD 与 Turtle 并列为用于存储和交换 RDF 数据的序列化语法，并将其与 RDF Schema 及 SPARQL 查询语言联系起来。[6]

在 RDF 1.1 抽象语法中，信息被组织为 RDF 图与 RDF 数据集：RDF 图是由主语-谓语-宾语三元组组成的集合，其节点可以是 IRI、字面量（带数据类型的值或带语言标签的字符串）或空白节点；RDF 数据集则将一个默认图与零个或多个命名图组合在一起。[6] IRI 在 RDF 中具有全局作用域，意味着不同位置出现的同一 IRI 指向同一个资源，并可作为 Web 上可解引用的起点。[6]

JSON-LD 1.1 及其 Processing Algorithms and API 规范定义了将 JSON-LD 文档反序列化为 RDF 数据集以及将 RDF 数据集序列化回 JSON-LD 的确定性算法，与 Turtle 和 TriG 等格式并行使用。[1][2] 为在 RDF 中支持 JSON-LD 1.1 的特性，语法规范定义了 `rdf:JSON` 数据类型、`i18n` 命名空间，以及带有 `rdf:language` 和 `rdf:direction` 属性的 `rdf:CompoundLiteral` 类。[1] JSON-LD 1.1 规范还阐述了 JSON-LD 与 Turtle、RDFa、Microdata 等其他关联数据及结构化标记格式之间的关系，而 JSON-LD 1.0 还曾将其与 Microformats 进行比较。[1][4]

## HTML、Schema.org 与搜索引擎中的 JSON-LD

JSON-LD 文档可直接嵌入 HTML 页面中，该特性在 JSON-LD 1.0 和 JSON-LD 1.1 中均有定义。[1][4] JSON-LD 1.1 规范涉及在 HTML `script` 元素中嵌入 JSON-LD、从 HTML 文档的 `base` 元素继承基础 IRI、JSON-LD `script` 元素的内容限制，以及定位特定的 JSON-LD `script` 元素。[1] 相关规范还包含 IANA Considerations 附录，Google 搜索中心的结构化数据指南则演示了在文档 `head` 中使用带有 `type="application/ld+json"` 的 `script` 元素进行 HTML 嵌入的方式。[1][4][8]

在公开 Web 上，JSON-LD 常与 [Schema.org](https://mimirwiki.com/zh/wiki/schema-org) 配合使用。Schema.org 是一套用于标记网页实体的共享词汇表，帮助主流搜索引擎（Google、Microsoft、Yandex 和 Yahoo!）理解页面语义。[9] Schema.org 支持 Microdata、RDFa 和 JSON-LD 三种标记格式，并在网站上以这三种格式发布了绝大多数示例。[9] 其类型层次以 `Thing`（包含 `name`、`description`、`url` 和 `image` 属性）为起点，衍生出 `CreativeWork`（包括 `Book`、`Movie`、`MusicRecording`、`Recipe` 和 `TVSeries`）、`Event`、`Organization`、`Person`、`Place`、`LocalBusiness`、`Product` 和 `Review` 等子类型。[9]

Google 搜索中心文档说明了 Google 搜索如何读取页内 JSON-LD 结构化数据（例如引用嵌套 `Person` 作者对象的 Schema.org `Recipe` 对象），以对页面内容进行分类、收集人物、书籍或公司等实体信息，并展示富媒体搜索结果。[8] Schema.org 与 Google 搜索中心均指出，结构化数据应描述该页面上对用户可见的内容，不建议创建仅用于放置标记的空白页面或为隐藏内容添加标记。[8][9] 使用 Wix、WordPress 或 Shopify 等内容管理系统的站点所有者可通过平台设置或插件配置结构化数据，开发者则可使用 Google 的富媒体搜索结果测试工具验证标记并预览符合条件的搜索功能。[8]

## JSON-LD 版本、治理与实现生态

JSON-LD 起源于 JSON for Linking Data 社区组，随后移交至 W3C RDF 工作组。该工作组于 2014 年 1 月 16 日将 JSON-LD 1.0 和 JSON-LD 1.0 Processing Algorithms and API 发布为 W3C 推荐标准（由 Manu Sporny、Gregg Kellogg 和 Markus Lanthaler 编辑，Dave Longley 与 Niklas Lindström 担任合著者）。[2][4] 此后，JSON-LD 1.1 的制定工作在 JSON-LD 社区组最终报告的基础上转由 W3C JSON-LD 工作组负责。[1] 继 2019 年 12 月 12 日发布候选发布版（Candidate Release）和 2020 年 5 月 7 日发布提案推荐标准（Proposed Recommendation）之后，工作组于 2020 年 7 月 16 日发布了三项 W3C 推荐标准，由 Gregg Kellogg、Pierre-Antoine Champin 和 Dave Longley 编辑。[1][2][3] W3C 于 2020 年 11 月 3 日正式将 JSON-LD 1.0 标记为已被取代的推荐标准（Superseded Recommendation），引导新实现采用 JSON-LD 1.1，同时保留对 1.0 规范的 W3C 专利政策许可承诺。[4]

| 规范 | 发布日期 | 范围 | 仓库 |
| --- | --- | --- | --- |
| JSON-LD 1.1 | 2020-07-16 | 关联数据语法、上下文、关键字、HTML 嵌入、RDF 映射 | `w3c/json-ld-syntax` |
| JSON-LD 1.1 Processing Algorithms and API | 2020-07-16 | 展开、压缩、扁平化、RDF 转换、`JsonLdProcessor` API | `w3c/json-ld-api` |
| JSON-LD 1.1 Framing | 2020-07-16 | 按示例图匹配与确定性树状布局 | `w3c/json-ld-framing` |

上述三项规范共同构成 W3C JSON-LD 工作组制定的官方 JSON-LD 1.1 推荐标准套件。[1][2][3][10]

截至 2026 年 11 月 23 日，W3C JSON-LD 工作组在持续至 2028 年 1 月的章程框架下负责正式规范治理，而开放的 JSON-LD 社区组则协调社区草案、讨论会议和邮件列表。[7] 在 GitHub 公开仓库 `w3c/json-ld-syntax` 中，工作组注明 JSON-LD 1.1 草案处于功能冻结（feature frozen）状态，仓库议题仅限于错误报告、现有特性澄清以及编辑性勘误。[10]

截至 2026 年 11 月 23 日，json-ld.org 托管了用于调试和可视化标记的 Web 工具 JSON-LD Playground，通过官方测试套件与实现报告跟踪一致性，并列出了涵盖 JavaScript（`json-ld.js`、`jsonld-streaming-parser.js`、`jsonld-streaming-serializer.js`、`rdf-parse.js`）、Python（`PyLD`、`RDFLib`、`TRLD`）、Ruby（`JSON-LD for RDF.rb`）、Go（`JSON-goLD`）、Java（`Titanium`）、C#（`dotNetRDF`）、Erlang 与 Elixir（`JSON-LD.ex`）、Rust（`sophia`、`oxjsonld`）以及命令行工具（`jsonld-cli`、`ld-cli`）的 JSON-LD 1.1 合规库，同时列出了 PHP（`php-json-ld`、`JsonLD`）、Java（`JSONLD-JAVA`）和 C#（`json-ld.net`）中的 JSON-LD 1.0 实现。[7] 社区草案还将 JSON-LD 数据模型扩展至相关规范，包括面向人工编写 YAML 的 YAML-LD、面向二维码、PDF417 条码和 NFC 标签等空间受限场景的压缩二进制序列化格式 CBOR-LD，以及 Streaming 和 JSON-LD-star 草案。[7]

## 常见问题

### 什么是 JSON-LD？

JSON-LD（JSON for Linking Data）是一项 W3C 推荐标准，定义了一种用于在 Web 上序列化关联数据的轻量级 JSON 语法。每份 JSON-LD 文档都是符合 RFC 8259 的有效 JSON，同时增加了上下文、全局 IRI 标识符、数据类型、语言标注以及有向图结构。 [1][5][7]

### JSON-LD 中的 @context、@id 和 @type 有什么作用？

在 JSON-LD 中，@context 将简短的 JSON 属性名映射到完整的 IRI，使键名在不同文档之间具有无歧义的含义。@id 关键字为节点对象分配全局 IRI 标识符，@type 用于指定节点对象的类型或值的数据类型。 [1][4][8]

### JSON-LD 1.1 对 JSON-LD 1.0 做了哪些更新？

JSON-LD 1.1 于 2020 年 7 月 16 日作为三项 W3C 推荐标准发布，取代了 2014 年的 JSON-LD 1.0 规范，除特别注明之处外保持了与 1.0 文档的兼容性。它将基础 JSON 引用更新至 RFC 8259，将 JSON-LD Framing 标准化为 W3C 推荐标准，并新增了作用域上下文、JSON 字面量、字符串基础书写方向以及更多索引模式等特性。 [1][2][3][4]

### 使用 JSON-LD 需要了解 RDF 吗？

不需要。W3C 规范指出，无需了解 RDF 即可将 JSON-LD 直接作为普通 JSON 使用；同时它也作为标准的 RDF 序列化语法，能够与用于 SPARQL 等工具的 RDF 1.1 图和数据集进行双向转换。 [1][4][6]

### 什么是 JSON-LD 处理 API 和 Framing 规范？

JSON-LD 1.1 Processing Algorithms and API 定义了 JsonLdProcessor 接口以及用于展开、压缩、扁平化和 RDF 转换的算法。JSON-LD 1.1 Framing 扩展了该 API，使开发者能够按示例查询，并对有向图强制应用确定性的嵌套树状布局。 [2][3]

### 如何将 JSON-LD 嵌入 HTML 页面以供搜索引擎使用？

可将 JSON-LD 放入 type 属性设为 application/ld+json 的 HTML script 元素中（通常位于文档的 head 内），并结合 Schema.org 等词汇表使用。Google 搜索会读取描述页面可见内容的页内 JSON-LD 以理解实体并展示富媒体搜索结果，同时提供富媒体搜索结果测试工具用于验证。 [1][8][9]

## 可引用的句子

- W3C RDF 工作组于 2014 年 1 月 16 日将 JSON-LD 1.0 发布为 W3C 推荐标准。 [4]
- W3C JSON-LD 工作组于 2020 年 7 月 16 日将 JSON-LD 1.1、JSON-LD 1.1 Processing Algorithms and API 以及 JSON-LD 1.1 Framing 发布为 W3C 推荐标准。 [1][2][3]
- W3C 于 2020 年 11 月 3 日将 JSON-LD 1.0 标记为已被取代的推荐标准，以 JSON-LD 1.1 作为替代。 [4]
- 每份 JSON-LD 1.1 文档均符合 IETF RFC 8259 定义的有效 JSON 规范，其对象成员名称必须唯一，数组默认按无序集合处理。 [1][5]
- 《RDF 1.1 Concepts and Abstract Syntax》将 JSON-LD 与 Turtle 并列为用于存储和交换 RDF 数据的序列化语法。 [6]
- JSON-LD 1.1 Framing 允许开发者按示例查询，并在 JSON-LD 图上强制生成确定性的树状布局。 [3]
- Schema.org 将 JSON-LD 与 Microdata 和 RDFa 一并作为 Google、Microsoft、Yandex 和 Yahoo! 可理解的标记格式予以支持。 [9]
- 截至 2026 年 11 月 23 日，W3C JSON-LD 工作组的章程有效期持续至 2028 年 1 月，GitHub 上的 w3c/json-ld-syntax 仓库将 JSON-LD 1.1 草案标记为功能冻结状态。 [7][10]

## 时间线

- 2014-01-16: W3C RDF 工作组将 JSON-LD 1.0 和 JSON-LD 1.0 Processing Algorithms and API 发布为 W3C 推荐标准。 [2][4]
- 2014-02-25: W3C RDF 工作组将《RDF 1.1 Concepts and Abstract Syntax》发布为 W3C 推荐标准，并将 JSON-LD 列为 RDF 序列化语法。 [6]
- 2017-12: IETF 发布定义 JSON 数据交换格式的 RFC 8259，该标准被 JSON-LD 1.1 引用。 [1][5]
- 2019-12-12: W3C JSON-LD 工作组发布 JSON-LD 1.1、Processing Algorithms and API 以及 Framing 的候选发布版。 [1][2][3]
- 2020-07-16: W3C JSON-LD 工作组将 JSON-LD 1.1、JSON-LD 1.1 Processing Algorithms and API 以及 JSON-LD 1.1 Framing 发布为 W3C 推荐标准。 [1][2][3]
- 2020-11-03: W3C 将 JSON-LD 1.0 标记为已被取代的推荐标准，以 JSON-LD 1.1 作为替代。 [4]

## 来源

1. JSON-LD 1.1. World Wide Web Consortium (W3C). 发布于 2020-07-16. https://www.w3.org/TR/json-ld11/ (访问于 2026-11-23; tier 1: government or public registry)
2. JSON-LD 1.1 Processing Algorithms and API. World Wide Web Consortium (W3C). 发布于 2020-07-16. https://www.w3.org/TR/json-ld11-api/ (访问于 2026-11-23; tier 1: government or public registry)
3. JSON-LD 1.1 Framing. World Wide Web Consortium (W3C). 发布于 2020-07-16. https://www.w3.org/TR/json-ld11-framing/ (访问于 2026-11-23; tier 1: government or public registry)
4. JSON-LD 1.0. World Wide Web Consortium (W3C). 发布于 2014-01-16. https://www.w3.org/TR/2014/REC-json-ld-20140116/ (访问于 2026-11-23; tier 1: government or public registry)
5. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 发布于 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (访问于 2026-11-23; tier 1: government or public registry)
6. RDF 1.1 Concepts and Abstract Syntax. World Wide Web Consortium (W3C). 发布于 2014-02-25. https://www.w3.org/TR/rdf11-concepts/ (访问于 2026-11-23; tier 1: government or public registry)
7. JSON-LD - JSON for Linked Data. JSON-LD Community Group. https://json-ld.org/ (访问于 2026-11-23; tier 3: official site)
8. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (访问于 2026-11-23; tier 3: official site)
9. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (访问于 2026-11-23; tier 3: official site)
10. GitHub - w3c/json-ld-syntax: JSON-LD 1.1 Specification · GitHub. W3C (GitHub). https://github.com/w3c/json-ld-syntax (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "JSON-LD." 版本 ee5045fa, 2026-11-23. https://mimirwiki.com/zh/wiki/json-ld
