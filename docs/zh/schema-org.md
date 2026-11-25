---
title: "Schema.org"
subtitle: "面向搜索引擎及其他应用程序的网页结构化数据标记共享词汇表"
canonical_url: https://mimirwiki.com/zh/wiki/schema-org
language: zh
page_class: anchor
revision_sha256: 30e936144a6958c753afb7b2c13f69916fbb20506d41212078314edb64582fc9
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/schema-org.md
  txt: https://mimirwiki.com/zh/wiki/schema-org.txt
  json: https://mimirwiki.com/zh/wiki/schema-org.json
  jsonld: https://mimirwiki.com/zh/wiki/schema-org.jsonld
translations:
  en: https://mimirwiki.com/wiki/schema-org
  ko: https://mimirwiki.com/ko/wiki/schema-org
  ja: https://mimirwiki.com/ja/wiki/schema-org
  es: https://mimirwiki.com/es/wiki/schema-org
---

# Schema.org

> Schema.org 是由 Google、Microsoft、Yahoo 和 Yandex 于 2011 年共同创立的共享结构化数据词汇表，用于在网页上描述产品、食谱、活动和组织等实体。发布者可使用 JSON-LD、Microdata 或 RDFa 进行编码。截至 30.1 版（2026-09-16），该词汇表在 CC BY-SA 3.0 协议下定义了 826 个类型和 1,540 个属性。

Schema.org 是一个协作式的类型与属性词汇表，用于向网页嵌入供搜索引擎及其他应用程序使用的结构化数据。该项目由 Google、Microsoft、Yahoo 和 Yandex 于 2011 年共同创立，维护着一套源自 RDF Schema 的多继承层次结构，并以 RDF/Turtle 格式发布其权威机器可读表示。网页发布者可使用 JSON-LD、Microdata 或 RDFa 在 HTML 页面中编码 Schema.org 术语。截至 30.1 版（发布于 2026 年 9 月 16 日），该词汇表共定义了 826 个类型、1,540 个属性、19 个数据类型、96 个枚举和 544 个枚举成员。日常演进工作通过 W3C Schema.org 社区组及其公开 GitHub 仓库协调推进，正式版本由指导委员会（Steering Group）审批发布。

**别名:** schema.org, Schema.org 词汇表, Schema 标记

## 关键事实

- **创立时间:** 2011 年（Google、Microsoft、Yahoo、Yandex） [4]
- **最新版本:** 30.1 版（2026-09-16） (截至 2026-11-23) [2]
- **词汇规模:** 826 个类型、1,540 个属性、19 个数据类型、96 个枚举、544 个枚举成员 (截至 2026-11-23) [3]
- **支持的编码格式:** JSON-LD、Microdata、RDFa [5]
- **模式许可协议:** 知识共享署名-相同方式共享 3.0（CC BY-SA 3.0） [6]

## 事实摘要

- **类型:** 面向万维网的共享结构化数据词汇表 [1]
- **创立年份:** 2011 年 [4]
- **创始企业:** Google、Microsoft、Yahoo、Yandex [1]
- **治理架构:** Schema.org 指导委员会与 W3C Schema.org 社区组 [1]
- **指导委员会主席:** R.V. Guha (截至 2026-11-23) [1]
- **社区组:** W3C Schema.org 社区组（510 名参与者；2015-03-31 成立） (截至 2026-11-23) [7]
- **最新版本:** 30.1 版（2026-09-16） (截至 2026-11-23) [2]
- **词汇规模:** 826 个类型、1,540 个属性、19 个数据类型、96 个枚举、544 个枚举成员 (截至 2026-11-23) [3]
- **权威表示形式:** RDF/Turtle [4]
- **标记格式:** JSON-LD、Microdata、RDFa [5]
- **许可协议:** CC BY-SA 3.0（模式、文档、示例）；Apache-2.0（网站软件） [6]
- **代码仓库:** github.com/schemaorg/schemaorg（5,741 次提交，6.3k 星标） (截至 2026-11-23) [8]

## Schema.org 概述

Schema.org 是一项旨在创建、维护和推广互联网结构化数据模式的协作式社区活动。[1] 2011 年，Google、Microsoft、Yahoo 和 Yandex 秉持与[站点地图](https://mimirwiki.com/zh/wiki/sitemaps)（`sitemaps.org`）相同的协作精神共同创立了 Schema.org，使网站管理员能够采用一套为各大搜索引擎共同理解的共享标记词汇表。[4][6] `schema.org` 域名由 OpenDomain 项目捐赠。[6]

标准 HTML 元素仅告知浏览器如何渲染页面内容（例如使用 `h1` 元素排版标题），却无法明确表达背后实体的具体类型。[5] Schema.org 为电影、人物、组织、产品和活动等实体添加了显式的机器可读标签，使搜索引擎和其他软件能够跨站点一致地理解页面内容，从而减少对容易出错的自动提取技术的依赖。[5][6] 许多早期术语借鉴了 Microformats、FOAF 和 OpenCyc 等先驱项目的成果。[6]

Schema.org 作为一项记录参与搜索引擎所支持模式的协作计划运作，独立于 W3C 或 IETF 等正式标准制定机构。[6] 任何自然语言编写的网页均可嵌入 Schema.org 标记，而词汇表术语本身及 Schema.org 网站文档均使用英语编写。[6] 在与 Facebook Open Graph 等协议并存的同时，Schema.org 提供了更为精细的标记方式，用于在单个网页中描述多个不同实体及其组成部分。[6]

## Schema.org 数据模型与词汇表结构

Schema.org 采用源自 RDF Schema 的通用数据模型，而 RDF Schema 本身衍生自 CycL。[4] 其模式组织为多继承类型层次结构，每个类型均可从多个父类型继承属性。[4] 最宽泛的根类型为 `Thing`，提供 `name`、`description`、`url` 和 `image` 等核心属性，而更具体的类型则继承自更宽泛的父类型；例如，`LocalBusiness` 同时是 `Place` 和 `Organization` 的子类型。[5]

Schema.org 中的属性可拥有多个定义域（`domainIncludes`）和多个值域（`rangeIncludes`），这一务实设计避免了仅为归组属性而人为创建大量中间类型。[4] 借助 `Class` 和 `Property` 等元级类型，该模式支持反射机制，能够表达自身定义。[4] Schema.org 的权威机器可读表示形式以 RDF/Turtle 发布，开发者文档页面同时提供 RDF 和 [JSON-LD](https://mimirwiki.com/zh/wiki/json-ld) 等其他机器可读格式。[3][4]

截至 2026 年 9 月 16 日发布的 30.1 版（访问日期 2026-11-23），Schema.org 定义了以下词汇表组件。[2][3]

| 组件 | 数量（30.1 版，截至 2026-11-23） |
| --- | --- |
| 类型（Types） | 826 |
| 属性（Properties） | 1,540 |
| 数据类型（Datatypes） | 19 |
| 枚举（Enumerations） | 96 |
| 枚举成员（Enumeration members） | 544 |

常用的 Schema.org 类型组包括创意作品（`CreativeWork`、`Book`、`Movie`、`MusicRecording`、`Recipe`、`TVSeries`）、嵌入式媒体对象（`AudioObject`、`ImageObject`、`VideoObject`）、`Event`、健康与医疗实体（`MedicalEntity`）、`Organization`、`Person`、`Place`（`LocalBusiness`、`Restaurant`）、`Product` 与 `Offer`（`AggregateOffer`）、`Review` 与 `AggregateRating` 以及 `Action`，同时还定义了文本和数字等基本数据类型。[3] 通用关联属性包括用于标识页面所描述主要实体的 `mainEntity` 和 `mainEntityOfPage`，以及 `url`、`sameAs` 和 `about`。[4]

Schema.org 遵循基于波斯特尔法则（Postel's Law）的务实一致性模型，将类型与属性的关联视为指导原则。[4] 单个实体描述可以组合来自多个独立类型（例如 `Book` 和 `Product`）的属性，发布者在预期为结构化实体类型的位置也常提供纯文本字符串或 URL；`Role` 和 `URL` 等类型可用于任意属性。[4][5] 任意属性均可携带多个值，在 RDF 三元组模型下默认表示为无序集合。[4] 当需要顺序或集合语义时，发布者可使用 RDF 列表（`rdf:List`，在 JSON-LD 中以 `@list` 表示）或 RDF 容器（`rdf:Seq`、`rdf:Bag`、`rdf:Alt`），在支持此类结构的解析器中，属性的预期值域将适用于集合中的各个元素。[4]

Schema.org 将专业领域划分为多个托管分区（`auto`、`bib`、`health-lifesci`、`meta` 和 `pending`），作为统一定义集合的不同视图。[3] 正在积极讨论中的术语位于 `pending` 分区，在达成共识前可能发生变化；`meta` 存放用于技术定义和网站功能的内部词汇；`attic` 则归档已弃用或未被采纳的术语，并提示发布者避免使用。[3] 与核心术语不同，`pending`、`meta` 和 `attic` 无需完整版本发布即可更新。[3] 独立的外部扩展（例如 GS1 Web Vocabulary 和面向机器学习数据集的社区元数据词汇表 Croissant）无需指导委员会正式批准即可扩展 Schema.org。[3]

## Schema.org 编码格式与术语标识符

Schema.org 术语可通过三种主要序列化格式嵌入网页：[JSON-LD](https://mimirwiki.com/zh/wiki/json-ld)、Microdata 和 RDFa。[4][5][6] Schema.org 在创立初期出于务实考量侧重于 Microdata，随后在认识到混合词汇表或反转属性关系等任务在 Microdata 中较为困难后，将文档与示例扩展至 RDFa 和 JSON-LD。[6]

| 格式 | 编码机制 | 规范与说明 |
| --- | --- | --- |
| JSON-LD | 将包含 `@context` 和 `@type` 的 JSON 对象嵌入带有 `type="application/ld+json"` 的 HTML `script` 元素中 | W3C 推荐标准（`JSON-LD 1.1` 发布于 2020-07-16，取代 2014-01-16 的 `JSON-LD 1.0`）；与 JSON（RFC 8259）100% 兼容，并可与 RDF 图互操作 |
| Microdata | 在内容元素上使用内联 HTML5 属性 `itemscope`、`itemtype` 和 `itemprop`，通过嵌套新的 `itemscope` 块表示嵌套项 | 随 HTML5 引入；项目类型以 Schema.org URL 形式给出，例如 `https://schema.org/Movie` |
| RDFa（RDFa Lite） | 在内容元素上使用内联 HTML 属性 `vocab="https://schema.org/"`、`typeof` 和 `property` | 与 Microdata 几乎同构映射（`itemprop` 对应 `property`，`itemtype` 对应 `typeof`，并省略 `itemscope`） |

上表汇总了 Schema.org、Google 搜索中心和 W3C 规范中记录的编码细节。[4][5][9][10] 在 HTML 标记中，Schema.org 还规定了机器可读的消歧模式：使用带 `datetime` 属性的 HTML `time` 元素表示日期和时间，格式为 `YYYY-MM-DD`（可选后接 `T` 及 `hh:mm` 或 `hh:mm:ss`）；使用带 `href` 属性的 HTML `link` 元素表示枚举与规范引用；使用带 `content` 属性的 HTML `meta` 元素表示隐式值。[5]

Schema.org 最初部署在 `http:` 网站上，使用 `http://schema.org/` URL 作为 RDF 术语标识符，后来将其公开网站和推荐文档示例迁移至 `https://schema.org/`。[7] Schema.org 文档说明，在结构化数据标记中，`https://schema.org` 和 `http://schema.org` 均有效且被广泛识别。[7] 过渡到静态文件托管后，Schema.org 取消了远程 JSON-LD 上下文的 HTTP 内容协商，改用指向 `/docs/jsonldcontext.jsonld` 且带有 `rel="alternate"` 和 `type="application/ld+json"` 的 HTTP `Link` 响应头。[7] 为避免全球现有的 RDF 解析器在无预警情况下改变输出的三元组，该上下文文档仍保留 `http:` 作为基础 URL；Dan Brickley 于 2026 年 10 月 30 日指出，即便标记引用了 `https://schema.org`，JSON-LD 解析器仍会输出 `http://` 三元组，并建议数据使用方在聚合 Schema.org 数据时对标识符进行规范化（canonicalization）处理。[7]

## Schema.org 治理架构、代码仓库与许可协议

Schema.org 采用由指导委员会（Steering Group）与 W3C Schema.org 社区组构成的双层治理结构。[1] 指导委员会负责高层监督、管理运营决策并批准正式版本发布。[1] 在 Google 发起 Schema.org 的联合创始人 R.V. Guha 以个人身份担任指导委员会主席（截至 2026 年 11 月 23 日），成员还包括创始企业 Google、Microsoft、Yahoo 和 Yandex 的代表、一名 W3C 代表以及重要社区贡献者。[1] 2015 年 4 月，指导委员会一致同意扩大成员规模，增补了 Stéphane Corlosquet、Martin Hepp（GoodRelations 的作者）以及一个 W3C 席位。[1] 指导委员会的讨论全部公开，会议纪要发布在 GitHub 上并链接至议题 #1。[1]

W3C Schema.org 社区组由 Dan Brickley 提议并于 2015 年 3 月 31 日成立，自 2015 年 4 月起成为日常模式讨论、提案起草和扩展评审的主要公开论坛。[1][7] 任何拥有 W3C 账号并签署《W3C 社区贡献者许可协议》（W3C Community Contributor License Agreement）的人士均可参与，W3C 同时声明其托管该小组并不意味着获得 W3C 会员或工作人员的官方背书。[1][7] 截至 2026 年 11 月 23 日，该社区组共有 510 名参与者及六位列名主席：Dan Brickley、Dan Scott、Stéphane Corlosquet、Phil Barker、Phil Archer 和 Ryan Levering。[7] Dan Brickley 还负责日常运营并担任项目网站管理员，独立于其在指导委员会中作为 Google 代表的身份，代表 Schema.org 主持社区组工作。[1] 相关讨论在 `public-schemaorg@w3.org` 邮件列表及 GitHub 上开展，其他相关 W3C 社区组则负责协调健康医疗、体育、档案、书目和汽车等领域的专业工作。[1][7]

Schema.org 在公开 GitHub 仓库 `github.com/schemaorg/schemaorg` 中维护其模式（`data`）、文档（`docs`）、模板、`versions.json` 以及网站软件（`software`，部分导入自 `sdopythonapp` 子模块）。[8] 截至 2026 年 11 月 23 日，该仓库记录有 5,741 次提交、6.3k 星标、975 次复刻、388 名关注者、301 个未关闭议题以及 14 个未关闭拉取请求。[8] 议题 #1 用作版本发布规划索引，议题 #2 和 #3 分别组织词汇表与工具开发工作，持续集成测试用于检查拉取请求，草稿版本则在 `staging.schema.org` 进行预发布。[1][2][8] 该项目的贡献指南优先考虑具有实际消费应用（除搜索引擎外，还包括网站分析、浏览器插件和云端工具）支撑的渐进式修复与增补，强调本地可用性以及与 GoodRelations、GS1、IPTC rNews、MARC、BibFrame、FRBR、BBC、欧洲广播联盟（European Broadcasting Union）、Music Ontology 和 MusicBrainz 等外部标准的对齐。[8]

Schema.org 的模式定义、网站文档、博客内容和标记示例均依据知识共享署名-相同方式共享 3.0（CC BY-SA 3.0）许可协议发布。[6] 用于运行 Schema.org 网站的支撑软件则采用 Apache-2.0 开源许可协议发布。[6][8]

## Schema.org 版本发布历史

Schema.org 在经过指导委员会和广大社区评审后发布带版本号的正式版本，当前版本摘要托管于 `https://schema.org/version/latest`。[2][8] 截至 2026 年 11 月 23 日，最新发布的正式版本为 2026 年 9 月 16 日推出的 30.1 版。[2]

30.1 版（2026-09-16）引入了支持欧盟数字产品护照（EU Digital Product Passports）发现的词汇，新增 `DigitalProductPassport` 类、`hasDigitalProductPassport`、`EnvironmentalProductDeclaration` 和 `DeclarationOfConformity`（作为 `Certification` 的子类型），以及产品属性 `authorizedRepresentative`、`importer`、`recycledContentPercentage` 和 `substanceOfConcern`。[2] 同一版本还新增了零售数据源属性，包括 `consumerNotice`、`isOftenBoughtWith`、`specification`、`valueGroup`、`itemPopularity`、`minimumOrderValue` 和枚举值 `MaximumRetailPrice`，并正式记录了对有序列表的显式支持，更新了术语使用统计数据，向 `MedicalSpecialty` 添加了 `Ophthalmology` 和 `Audiology`，同时将已采纳的 `pending` 术语晋升为正式可用（GA）。[2]

30.1 版之前的主要近期版本里程碑如下。[2]

| 版本 | 发布日期 | 主要新增与变更 |
| --- | --- | --- |
| 30.1 | 2026-09-16 | 欧盟数字产品护照类型与属性、零售数据源词汇、有序列表文档化、`pending` 术语晋升正式版 |
| 30.0 | 2026-03-19 | GS1、Dublin Core 和 Open Graph 等价性注解及导出；与 UN/CEFACT 对齐的欧盟数字产品护照示例；`Credential` 和 `Error` 类；`Quantity` 改为继承自 `DataType` |
| 29.4 | 2025-12-08 | `ConferenceEvent`、`PerformingArtsEvent`、`InstantaneousEvent`、身份验证动作（`AuthenticateAction`、`LoginAction`、`ResetPasswordAction`）、`OperatingSystem`、`RuntimePlatform`、`SequentialArt`（弃用 `GraphicNovel`），以及面向 UN/CEFACT、OWL、OMG 和 GS1 的 OWL 等价关系 |
| 29.3 | 2025-09-04 | 扩展 `recipeIngredient` 值域；新增 `OnlineMarketplace` 及 `hasStore` / `isStoreOn` |
| 29.0 | 2025-03-24 | `FinancialIncentive` 词汇、`Legislation` 上的欧洲立法标识符（ELI）属性、修订配送类型（`ShippingConditions`、`ShippingService`，弃用 `DeliveryTimeSettings`） |
| 28.0 | 2024-09-17 | 忠诚度与会员计划类型（`MemberProgram`、`MemberProgramTier`、`TierBenefitEnumeration`） |
| 27.02 | 2024-07-01 | 将编辑预发布站点从 `webschemas.org` 迁移至 `staging.schema.org` |
| 27.01 | 2024-06-24 | Schema.org 网站改版 |
| 27.0 | 2024-05-20 | 新增 `hasGS1DigitalLink` 和 `certificationRating` |

补丁版本 29.1 版（2025-04-25）和 29.2 版（2025-05-13）修复了 29.0 版引入的回归问题，并新增了 `pronouns`、`companyRegistration`、`Cooperative` 和 `referee` 等属性和类型。[2] `pending`、`meta` 和 `attic` 分区中的术语也可在完整版本发布间隙进行更新。[3]

## Schema.org 的搜索引擎应用与限制

Schema.org 标记被 Google、Microsoft、Yahoo 和 Yandex 等搜索引擎用于解析页面实体并驱动富媒体搜索结果。[5][6][9] Google 搜索中心记录的结构化数据功能涵盖多种内容类型，包括 Article（文章）、Breadcrumb（面包屑导航）、Course list（课程列表）、Dataset（数据集）、Discussion forum（讨论论坛）、Event（活动）、Fact check（事实核查）、Image metadata（图片元数据）、Job posting（招聘信息）、Local business（本地商家）、Organization（组织）、Product snippet（商品摘要）、Merchant listing（商家商品详情）、Profile page（个人资料页）、Q&A（问答）、Recipe（食谱）、Review snippet（评价摘要）、Software app（软件应用）、Speakable（可朗读内容）、Subscription and paywalled content（订阅和付费墙内容）、Vacation rental（度假租赁）和 Video（视频）。[9] 例如，对于食谱页面，结构化数据可标注食材、热量和烹饪时间，使 Google 搜索能够展示富媒体结果并支持属性级筛选。[9] Wix、WordPress 和 Shopify 等内容管理系统（CMS）提供内置设置或插件，无需直接编辑 HTML 即可添加结构化数据。[9]

发布者可使用官方资料中介绍的两种主要验证工具检查语法与结构：Schema.org 标记验证器（Schema.org Markup Validator）用于检查 Schema.org 结构并标示 RDF 集合（`List`、`Bag`、`Seq`、`Alt`）；Google 的富媒体搜索结果测试（Rich Results Test）则用于验证结构化数据并预览符合条件的 Google 搜索功能。[4][9]

Schema.org 与搜索引擎文档指出了结构化数据使用中的若干实际边界与限制：

- **选择性功能展示**：Schema.org 常见问题解答指出，搜索引擎不会呈现 Schema.org 中定义的每一种信息类型，发布者需要查阅各家搜索引擎的文档以了解其支持的具体功能。[6]
- **可见内容要求**：Schema.org 指南和 Google 搜索中心均要求发布者仅标记页面上对用户可见的内容，避免创建仅用于承载结构化数据的空白页面，也不要添加隐藏标记（即便底层数据准确无误）。[5][6][9]
- **可选与部分标记**：并非必须标记项目的每一个属性；若不存在精确子类型，发布者可不作标记、使用 `Person` 等更宽泛的父类型，或自定义扩展。[6]
- **有限的本体范围**：Schema.org 为便于实际网页发布而简化了网页内容建模，将全面详尽的领域本体交由独立词汇表和外部扩展处理。[4][8]
- **解析器与标识符异构性**：Schema.org 不强制所有解析器实现 RDF 集合或容器，且全网语料在 Microdata、RDFa 和 JSON-LD 中混用 `http://` 与 `https://` 标识符，要求数据使用方自行处理标识符规范化以及简写字符串值。[4][7]

## 常见问题

### 什么是 Schema.org？

Schema.org 是一个用于向网页添加机器可读结构化数据的协作式类型和属性词汇表。Google、Microsoft、Yahoo 和 Yandex 于 2011 年共同发起了这一项目，使网站能够在各大搜索引擎和其他应用程序之间使用一套统一的共享标记词汇表。 [1][4]

### Schema.org 是像 W3C 那样的正式标准机构吗？

不是。Schema.org 将自身定位为一项记录各大搜索引擎所支持模式的协作计划，与 W3C 或 IETF 等正式标准制定机构相区分。W3C 托管 Schema.org 社区组作为公开讨论论坛，但 W3C 的托管并不意味着获得 W3C 会员或工作人员的官方背书。 [6][7]

### Schema.org 可以使用哪些标记格式？

发布者可以使用 JSON-LD、Microdata 或 RDFa（包括 RDFa Lite）在网页中编码 Schema.org 术语。Schema.org 词汇表本身的权威机器可读表示形式以 RDF/Turtle 格式发布。 [4][5][6]

### Schema.org 词汇表的规模有多大？

截至 2026 年 9 月 16 日发布的 30.1 版（访问日期 2026-11-23），Schema.org 词汇表包含 826 个类型、1,540 个属性、19 个数据类型、96 个枚举和 544 个枚举成员。此外，它还设有托管分区，例如用于存放待评审术语的 pending 分区以及用于归档已弃用术语的 attic 分区。 [2][3]

### Schema.org 的词汇表和软件采用什么许可协议发布？

Schema.org 的模式定义、网站文档、博客内容和标记示例采用知识共享署名-相同方式共享 3.0（CC BY-SA 3.0）许可协议发布。用于发布网站的支撑软件则采用 Apache-2.0 开源许可协议发布。 [6][8]

### Schema.org 中的每个类型都会在搜索引擎结果中显示吗？

不会。根据 Schema.org 常见问题解答，搜索引擎并不会展示词汇表中定义的每一种信息类型，各家搜索引擎会分别说明其支持的功能与类型。Google 搜索中心也规定，页面上的结构化数据必须描述该页面上对访问者可见的内容。 [6][9]

## 可引用的句子

- Schema.org 由 Google、Microsoft、Yahoo 和 Yandex 于 2011 年联合创立，旨在为网页提供共享的结构化数据词汇表。 [1][4]
- W3C Schema.org 社区组于 2015 年 3 月 31 日发起并成立，作为讨论 Schema.org 变更与扩展的公开论坛。 [7]
- 截至 2026 年 11 月 23 日，Schema.org 最新发布的版本为 2026 年 9 月 16 日推出的 30.1 版。 [2]
- 截至 2026 年 11 月 23 日，Schema.org 词汇表包含 826 个类型、1,540 个属性、19 个数据类型、96 个枚举和 544 个枚举成员。 [3]
- Schema.org 标记可使用 JSON-LD、Microdata 或 RDFa 编码嵌入网页，而该模式规范的权威机器可读表示形式为 RDF/Turtle。 [4][5]
- Schema.org 的模式定义、网站文档、博客内容和标记示例采用知识共享署名-相同方式共享 3.0（CC BY-SA 3.0）许可协议，而支撑网站运行的软件采用 Apache-2.0 许可协议。 [6][8]
- JSON-LD 1.1 于 2020 年 7 月 16 日作为 W3C 推荐标准发布，取代了 2014 年 1 月 16 日发布的 JSON-LD 1.0 推荐标准。 [10]
- Google 搜索中心文档明确指出，网页上的结构化数据必须描述该页面上对用户可见的内容。 [9]

## 时间线

- 2011: Google、Microsoft、Yahoo 和 Yandex 共同推出 Schema.org，为网页提供共享的结构化数据词汇表。 [4][8]
- 2014-01-16: W3C 将 JSON-LD 1.0 作为 W3C 推荐标准发布。 [10]
- 2015-03-31: Dan Brickley 提议并成立 W3C Schema.org 社区组。 [7]
- 2015-04: Schema.org 指导委员会扩大成员，吸纳社区贡献者 Stéphane Corlosquet 和 Martin Hepp 以及一名 W3C 代表，W3C 社区组成为主要协作论坛。 [1]
- 2020-07-16: W3C 将 JSON-LD 1.1 作为 W3C 推荐标准发布，取代 JSON-LD 1.0。 [10]
- 2024-07-01: Schema.org 发布 27.02 版，将其编辑预发布站点从 webschemas.org 迁移至 staging.schema.org。 [2]
- 2025-03-24: Schema.org 发布 29.0 版，新增金融激励词汇、欧洲立法标识符（ELI）属性及修订后的配送模式。 [2]
- 2026-03-19: Schema.org 发布 30.0 版，新增 GS1、Dublin Core 和 Open Graph 等价性注解以及欧盟数字产品护照示例。 [2]
- 2026-09-16: Schema.org 发布 30.1 版，新增欧盟数字产品护照类型、零售数据源属性以及有序列表的显式文档。 [2]

## 来源

1. About - Schema.org. Schema.org. https://schema.org/docs/about.html (访问于 2026-11-23; tier 3: official site)
2. Release listing - schema.org. Schema.org. 发布于 2026-09-16. https://schema.org/docs/releases.html (访问于 2026-11-23; tier 3: official site)
3. Schemas - Schema.org. Schema.org. https://schema.org/docs/schemas.html (访问于 2026-11-23; tier 3: official site)
4. Data model - Schema.org. Schema.org. https://schema.org/docs/datamodel.html (访问于 2026-11-23; tier 3: official site)
5. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (访问于 2026-11-23; tier 3: official site)
6. FAQ - schema.org. Schema.org. https://schema.org/docs/faq.html (访问于 2026-11-23; tier 3: official site)
7. Schema.org Community Group. World Wide Web Consortium (W3C). https://www.w3.org/community/schemaorg/ (访问于 2026-11-23; tier 1: government or public registry)
8. GitHub - schemaorg/schemaorg: Schema.org - schemas and supporting software · GitHub. Schema.org (GitHub). https://github.com/schemaorg/schemaorg (访问于 2026-11-23; tier 3: official site)
9. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (访问于 2026-11-23; tier 3: official site)
10. JSON-LD 1.1. World Wide Web Consortium (W3C). 发布于 2020-07-16. https://www.w3.org/TR/json-ld11/ (访问于 2026-11-23; tier 1: government or public registry)

## 引用本页

Mimirwiki. "Schema.org." 版本 30e93614, 2026-11-24. https://mimirwiki.com/zh/wiki/schema-org
