---
title: "站点地图"
subtitle: "用于向搜索引擎爬虫列出网站 URL 与元数据的基于 XML 的协议"
canonical_url: https://mimirwiki.com/zh/wiki/sitemaps
language: zh
page_class: anchor
revision_sha256: 5b53edc2356d19915fd86df8b87944910d34c98dfe0a407604e525383c0027a4
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/sitemaps.md
  txt: https://mimirwiki.com/zh/wiki/sitemaps.txt
  json: https://mimirwiki.com/zh/wiki/sitemaps.json
  jsonld: https://mimirwiki.com/zh/wiki/sitemaps.jsonld
translations:
  en: https://mimirwiki.com/wiki/sitemaps
  ko: https://mimirwiki.com/ko/wiki/sitemaps
  ja: https://mimirwiki.com/ja/wiki/sitemaps
---

# 站点地图

> 站点地图（Sitemaps）是由 Google、Yahoo 和 Microsoft 赞助的 XML 协议，允许网站向搜索引擎列出可抓取的 URL 及其元数据。截至 2026-11-23，0.9 版本将每个站点地图或索引文件限制为最多 50,000 个条目和未压缩 50 MB，同时支持 RSS、Atom 和纯文本文件及各类扩展。列出 URL 有助于发现，但搜索引擎是否将其编入索引仍为可选项。

站点地图（Sitemaps）是一种基于 XML 的网络协议，使网站运营者能够向搜索引擎告知可供抓取的网页、图片、视频和其他文件，以及最后修改日期等元数据。该协议由 Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation 通过 sitemaps.org 赞助，其 0.9 版本定义了单个站点地图文件（urlset）和站点地图索引文件（sitemapindex）的 XML 架构，并同时支持聚合源和纯文本 URL 列表。截至 2026-11-23，每个站点地图文件限制为最多 50,000 个 URL 和未压缩 50 MB（52,428,800 字节），各搜索引擎的 XML 扩展还可支持图片和新闻文章等特定内容。发布站点地图有助于搜索引擎爬虫发现 URL，而各搜索引擎对是否抓取或索引所列条目仍保有完全自主权。

**别名:** Sitemaps, Sitemaps 协议, XML 站点地图, sitemap.xml, Sitemaps 0.9

## 关键事实

- **协议版本:** 0.9（http://www.sitemaps.org/schemas/sitemap/0.9） (截至 2026-11-23) [1]
- **赞助方:** Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation [3]
- **单文件限制:** 50,000 个 URL 及未压缩 50 MB（52,428,800 字节） (截至 2026-11-23) [1]
- **字符编码:** UTF-8 [1]
- **规范许可协议:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]

## 事实摘要

- **类型:** 用于向搜索引擎爬虫告知可抓取 URL 的网络协议 [1]
- **赞助方:** Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation [3]
- **协议版本:** 0.9 (截至 2026-11-23) [1]
- **XML 命名空间:** http://www.sitemaps.org/schemas/sitemap/0.9 (截至 2026-11-23) [1]
- **XML 架构:** sitemap.xsd（站点地图）与 siteindex.xsd（站点地图索引文件） (截至 2026-11-23) [2]
- **支持格式:** XML、RSS 2.0、Atom 0.3 或 1.0 以及 UTF-8 纯文本 (截至 2026-11-23) [1]
- **单文件条目上限:** 每个站点地图 50,000 个 URL；每个站点地图索引 50,000 个站点地图 (截至 2026-11-23) [1]
- **单文件大小上限:** 未压缩 50 MB（52,428,800 字节）；支持 gzip 压缩 (截至 2026-11-23) [1]
- **loc 最大长度:** 少于 2,048 个字符 (截至 2026-11-23) [1]
- **规范许可协议:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]
- **Google Search Console 索引配额:** 每个网站最多 500 个站点地图索引文件 (截至 2025-12-10) [7]

## Sitemaps 协议概述

站点地图（Sitemaps）协议是一种基于 XML 的规范，允许网站运营者向搜索引擎告知可供抓取的网页、图片、视频和其他文件。[1][5] Sitemaps.org 由 Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation 赞助，各赞助方将其在该规范中的版权依据知识共享署名-相同方式共享 2.5 许可协议（Creative Commons Attribution-ShareAlike License version 2.5）进行授权。[3] 根据 Sitemaps.org 服务条款，任何赞助方均无义务读取、索引或使用已发布的站点地图，且各赞助方均可随时变更或终止对该协议的支持。[3]

除列出 URL 外，站点地图还可传达文件之间的关联及元数据，包括最后修改日期以及网页的[替代语言版本](https://mimirwiki.com/zh/wiki/hreflang)。[5] 尽管 XML 架构是主要格式，Sitemaps 协议与 Google 搜索同样接受聚合源和纯文本 URL 列表。[1][6]

- **XML 站点地图**：可扩展格式，能够承载图片、视频、新闻及本地化网页版本的元数据。许多内容管理系统（CMS）会自动或通过插件生成 XML 站点地图，但在大型或高频变更的网站上维护 XML 映射可能较为复杂。[1][6]
- **RSS、mRSS 和 Atom 源**：Sitemaps.org 支持 RSS 2.0 以及 Atom 0.3 或 1.0，将 `link` 字段读取为 URL，并将可选的 `pubDate`（RSS）或 `updated`（Atom）字段读取为修改日期。[1] 聚合源通常仅列出最近的 URL，应放置在待抓取的最高层级目录中。[1] Google 支持通过 RSS、mRSS 和 Atom 1.0 源提供 HTML、可索引文本内容及视频元数据，而图片与新闻元数据则需使用 XML 扩展。[6]
- **纯文本站点地图**：采用 UTF-8 编码的文本文件，每行包含一个完整限定的 URL，不含页眉、页脚或其他附加元数据，仅限于 HTML 及其他可索引文本网页。[1][6]

WordPress、Wix 和 Blogger 等内容管理系统通常会默认自动生成站点地图。[5] 根据 2025-12-10 更新的 Google 搜索中心文档，站点地图尤其适用于内部链接可能遗漏新网页的大型网站、外部链接较少的新网站，以及包含大量视频、图片或 Google 新闻内容的网站。[5] 相比之下，网页数量约为 500 个或更少、从首页起内部链接覆盖全面且媒体或新闻网页较少的小型网站，可能并不需要站点地图。[5]

## Sitemaps XML 格式与元素

Sitemaps 协议 0.9 在命名空间 `http://www.sitemaps.org/schemas/sitemap/0.9` 下定义了一种采用 UTF-8 编码的 XML 文档格式。[1] 官方提供了两个用于验证的 XML 架构定义文件：用于站点地图文件的 `http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd` 和用于站点地图索引文件的 `http://www.sitemaps.org/schemas/sitemap/0.9/siteindex.xsd`。[2]

包括 URL 在内的所有 XML 值均须遵循 RFC 3986（URI）、RFC 3987（IRI）及 XML 标准，对非 ASCII 字符采用 URL 百分号编码，同时对五个保留字符使用 XML 实体转义码：与号（`&` 转义为 `&amp;`）、单引号（`'` 转义为 `&apos;`）、双引号（`"` 转义为 `&quot;`）、大于号（`>` 转义为 `&gt;`）和小于号（`<` 转义为 `&lt;`）。[1][2] 截至 2026-11-23，Sitemaps 协议 0.9 为站点地图文件定义了六个核心元素。[1]

| 元素 | 要求 | 取值规则与作用 |
| --- | --- | --- |
| `urlset` | 必需 | 封装整个文件并声明协议 0.9 XML 命名空间的根元素。[1] |
| `url` | 必需 | 每个 URL 条目的父元素；其余标签均作为其子元素出现。[1] |
| `loc` | 必需 | 以协议（如 `http` 或 `https`）开头的完整限定网页 URL；若服务器要求则需以尾部斜杠结尾，且长度须短于 2,048 个字符。[1][2] |
| `lastmod` | 可选 | 采用 W3C Datetime 格式（`YYYY-MM-DD` 或带时区的完整 ISO 8601 日期时间）的网页最后修改日期。用于记录网页更新日期，独立于站点地图生成时间，也独立于 HTTP `If-Modified-Since`（304）标头。[1][2] |
| `changefreq` | 可选 | 网页可能发生变化频率的大致估计。有效值包括 `always`（每次访问均变化的文档）、`hourly`、`daily`、`weekly`、`monthly`、`yearly` 和 `never`（归档 URL）。[1] |
| `priority` | 可选 | 该 URL 相对于同一网站其他 URL 的重要程度，取值范围为 `0.0` 到 `1.0`，默认值为 `0.5`。[1] |

协议规范与 Google 搜索文档对所列 URL 还规定了其他细则。由于 `/mypage.html` 等相对路径无效，条目必须为完整的绝对 URL，且 Google 会严格按照所写形式尝试抓取 URL。[2][6] 当同时存在 HTTP 和 HTTPS 版本的 URL 时，网站运营者应仅列出其中一个协议版本；应移除会话 ID 以避免不完整或重复抓取；对于框架网页，则应同时包含框架集和框架内容的 URL。[2] URL 在站点地图中的排列顺序不会影响搜索引擎对其的处理方式。[2] Google 指出，站点地图可能会影响规范 URL 的选择；当存在独立的桌面端和移动端 URL 时，Google 建议仅列出单一版本或对两个版本均进行注释。[6]

## 站点地图索引文件与大小限制

截至 2026-11-23，无论是 XML 格式还是纯文本格式，单个站点地图文件均限制为最多 50,000 个 URL 且未压缩大小不超过 50 MB（52,428,800 字节）。[1][2][6] 为节省带宽，网站运营者可使用 gzip 压缩站点地图文件，但未压缩文件仍须保持在 50 MB 限制以内，且 sitemaps.org 常见问题解答指定采用 gzip 作为压缩格式。[1][2]

当网站的 URL 超过 50,000 个或文件大小超过 50 MB 时，必须将 URL 拆分到多个站点地图文件中，再通过一个或多个站点地图索引文件进行汇总。[1][2][7] 站点地图索引文件采用与单个站点地图相同的 UTF-8 编码及 `http://www.sitemaps.org/schemas/sitemap/0.9` 命名空间。[1][7] 截至 2026-11-23，每个站点地图索引文件最多可列出 50,000 个站点地图，未压缩大小不得超过 50 MB（52,428,800 字节），且支持 gzip 压缩。[1][2][7]

站点地图索引文件使用协议 0.9 定义的四个 XML 元素。[1][7]

- `sitemapindex`（必需）：封装所有所列站点地图条目的根元素。[1][7]
- `sitemap`（必需）：每个独立站点地图的父元素，也是 `sitemapindex` 唯一的直接子元素。[1][7]
- `loc`（必需）：经过实体转义的 URL，用于指明站点地图的位置，目标可为 XML 站点地图、RSS 文件、Atom 文件或纯文本文件。[1][7]
- `lastmod`（可选）：W3C Datetime 时间戳，用于标明所引用站点地图文件本身的修改时间，与该站点地图内部单个网页的修改时间相互独立。[1][7]

在站点地图索引中提供 `lastmod` 可支持增量获取站点地图，使爬虫仅检索近期更新的站点地图。[1][2] 对于拥有数千万 URL 的网站，将频繁变动的 URL 归类到少量站点地图中并在站点地图索引里标记 `lastmod`，有助于搜索引擎快速发现更新。[1][2] 截至 2025-12-10，Google Search Console 允许网站所有者为每个网站最多提交 500 个站点地图索引文件，且分别提交多个站点地图还支持在 Search Console 中按站点地图追踪效果。[6][7]

## 站点地图文件位置、作用范围与发现机制

站点地图文件的存放位置决定了该文件内哪些 URL 有效。[1] 根据协议的路径前缀规则，托管在 `http://example.com/catalog/sitemap.xml` 的站点地图可列出以 `http://example.com/catalog/` 开头的 URL，而同级目录下的 URL（如 `http://example.com/images/`）或不同协议方案的 URL（如 `https://example.com/catalog/page1.php`）则会被视为无效并丢弃。[1] 站点地图中的所有 URL 必须与该站点地图文件具有相同的协议、主机和端口号：`http://www.example.com/sitemap.xml` 不能包含来自 `http://subdomain.example.com` 的 URL，而 `http://www.example.com:100/sitemap.xml` 则要求所列每个 URL 均包含该端口号。[1][2]

由于路径范围适用于站点地图所在目录的后代目录，sitemaps.org 和 Google 建议将站点地图放置在 Web 服务器根目录（`http://example.com/sitemap.xml`），以便通过单一位置覆盖整个网站。[1][2][6] 当组织的安全策略将目录写入权限隔离时，仍允许按目录分别维护站点地图。[1][2] 在 Google 搜索中，通过 Google Search Console 直接提交站点地图可解除父目录范围限制。[6]

站点地图索引文件遵循平行的主机与层级规则：所引用的站点地图必须位于同一主机上，且处于与站点地图索引文件相同的目录或更深层级的子目录中。[1][7] 若要进行跨主机提交（即由单一主机为多个不同主机提供站点地图），必须证明对每个目标主机的所有权。[1][7]

站点地图发布后，sitemaps.org 常见问题解答介绍了三种通知搜索引擎的方法：通过搜索引擎工具直接提交、向搜索引擎发送 ping 通知，以及在 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 中声明站点地图位置。[2] 互联网工程任务组（IETF）于 2022 年 9 月作为 RFC 9309 发布的爬虫排除协议（Robots Exclusion Protocol）规范在第 2.2 节（形式化语法）中指出，`robots.txt` 解析器实现者可定义 Sitemaps 等附加行。[4] 至于 ping 通知，Google 搜索中心博客于 2023 年 6 月发布公告，宣布 Google 的站点地图 ping 端点即将停用。[10]

## 面向图片、新闻及其他内容的站点地图扩展

站点地图 XML 文件支持通过额外的 XML 命名空间针对特定内容类型进行协议扩展。[1][6] Google 搜索中心记录了针对图片、新闻文章、视频以及[本地化网页版本](https://mimirwiki.com/zh/wiki/hreflang)的扩展规范，这些扩展既可放入专用站点地图，也可整合进现有的 XML 站点地图中。[5][6][8][9]

| 扩展 | XML 命名空间 | 必需元素 | 文档规定的限制 |
| --- | --- | --- | --- |
| 核心 Sitemaps 0.9 | `http://www.sitemaps.org/schemas/sitemap/0.9` | `urlset`、`url`、`loc`（或 `sitemapindex`、`sitemap`、`loc`） | 50,000 个 URL 或站点地图；未压缩 50 MB[1][7] |
| Google 图片站点地图 | `http://www.google.com/schemas/sitemap-image/1.1` | `image:image`、`image:loc` | 每个 `url` 最多 1,000 个 `image:image` 标签[8] |
| Google 新闻站点地图 | `http://www.google.com/schemas/sitemap-news/0.9` | `news:news`、`news:publication`、`news:name`、`news:language`、`news:publication_date` | 每个 `url` 1 个 `news:news`；每个站点地图最多 1,000 个 `news:news` 标签；最近 2 天内的文章[9] |

Google 的图片站点地图扩展可帮助 Googlebot 发现容易被遗漏的图片，例如通过 JavaScript 加载的图片。[8] 截至 2025-12-10，每个 `url` 元素最多可包含 1,000 个 `image:image` 子元素，且每个子元素中都必须包含 `image:loc` 图片 URL。[8] 图片 URL 可托管在[内容分发网络](https://mimirwiki.com/zh/wiki/content-delivery-network)等其他域名上，前提是两个域名均已在 Google Search Console 中完成验证，且 `robots.txt` 允许抓取。[8] 继 2022 年 5 月 Google 搜索中心博客发布移除部分站点地图扩展标签的通知后，Google 从其图片站点地图文档中移除了此前记录的四个图片标签（`image:caption`、`image:geo_location`、`image:title` 和 `image:license`）。[8][10]

Google 的新闻站点地图扩展用于供新闻发布商传递文章元数据，发布商既可扩展常规站点地图，也可维护专用的新闻站点地图以便在 Search Console 中单独追踪。[9] 发布商应随新文章发布持续更新现有新闻站点地图，Google 新闻会以与网站其余部分相同的频率抓取新闻站点地图。[9] 条目必须限于最近两天内发布的文章，超过该期限的旧 URL 或其 `news:news` 代码块应予移除；若新闻站点地图暂时为空，Search Console 会显示“空站点地图（Empty Sitemap）”警告以供确认，但不会影响 Google 搜索。[9] 每个 `url` 可接受一个 `news:news` 标签，单个站点地图最多可容纳 1,000 个 `news:news` 标签。[9] 在 `news:publication` 内，`news:name` 必须与 `news.google.com` 上显示的出版物名称完全一致（省略括号内文字）；`news:language` 使用两字母或三字母 ISO 639 代码，其中简体中文使用 `zh-cn`，繁体中文使用 `zh-tw`。[9] `news:publication_date` 标签以 W3C Datetime 格式（`YYYY-MM-DD`、`YYYY-MM-DDThh:mmTZD` 或 `YYYY-MM-DDThh:mm:ssTZD`）记录文章在网站上的原始发布日期。[9]

Google 搜索中心还指出，站点地图视频条目可指定视频时长、评分和年龄适宜性分级，且 RSS、mRSS 和 Atom 1.0 源可在提供 HTML 与可索引文本内容的同时提供视频元数据。[5][6]

## 搜索引擎对站点地图元数据与限制的处理

各搜索引擎对站点地图可选元数据标签的处理方式各不相同，且 Sitemaps 协议并未对爬虫施加读取或索引所列 URL 的义务。[1][3] 在协议 0.9 中，`urlset`、`url` 和 `loc` 为必需元素，而 sitemaps.org 指出对可选元素（`lastmod`、`changefreq` 和 `priority`）的支持因搜索引擎而异，并建议发布商查阅各服务商的官方文档。[1][2]

在协议规范本身中，`changefreq` 被定义为常规的抓取提示。[1] 爬虫访问标记为 `hourly` 的网页时频率可能低于每小时一次，访问标记为 `yearly` 的网页时频率可能高于每年一次，也可能会定期检查标记为 `never` 的 URL 以发现意外变动。[1] 同样，`priority` 以 `0.0` 到 `1.0`（默认 `0.5`）的标度表示单个网站内 URL 之间的相对重要程度，不用于比较不同域名间的网页；将所有 URL 都设为高值无法产生相对区分，且协议规范与常见问题解答均明确表示 `priority` 预期不会影响搜索结果排名。[1][2]

关于 `lastmod`，协议指出该标签独立于服务器的 HTTP `If-Modified-Since`（304）标头，搜索引擎可能以不同方式结合或评估这两项信号。[1] sitemaps.org 常见问题解答指出，为静态文件提供准确的修改时间戳或为动态网页提供基于数据的估计值，有助于爬虫跳过未变更的 URL，从而降低服务器带宽与 CPU 负载。[2] 对于站点地图索引文件，2025-12-10 更新的 Google 搜索中心文档指出，`lastmod` 可能有助于 Google 安排站点地图的抓取计划。[7]

在格式方面，Google 表示其对 XML 站点地图、RSS/mRSS/Atom 1.0 源和纯文本站点地图并无偏好。[6] Google 将站点地图视为 URL 发现辅助手段以及可能影响规范 URL 选择的信号，但同时明确指出，将 URL 列入站点地图并不保证其会被抓取或编入索引。[5][6] 站点地图与依据 RFC 9309 传达爬虫访问权限的 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 协同工作，爬虫必须获得 `robots.txt` 的许可才能访问站点地图中列出的内容。[4][8] 根据 Sitemaps.org 服务条款，Google、Yahoo 和 Microsoft 均保留在任何服务中部分使用该协议或停止支持的权利。[3]

## 常见问题

### 什么是站点地图？

站点地图是一种机器可读文件，网站可通过该文件列出可供抓取的网页、视频、图片和其他文件，并提供最后修改日期和替代语言版本等元数据。搜索引擎通过读取站点地图更高效地发现和抓取 URL。 [1][5]

### 站点地图的 URL 数量和文件大小限制是多少？

截至 2026-11-23，每个 XML 或文本格式的站点地图文件最多可包含 50,000 个 URL，且未压缩大小不得超过 50 MB（52,428,800 字节）。站点地图索引文件在相同的未压缩 50 MB 限制内最多可引用 50,000 个站点地图，并且文件可使用 gzip 压缩。 [1][2][6][7]

### 站点地图和站点地图索引文件中必须包含哪些 XML 元素？

标准 XML 站点地图要求包含声明 0.9 命名空间的 urlset 根元素、作为每个条目父元素的 url，以及保存完整限定 URL 的 loc 子元素。站点地图索引文件要求包含 sitemapindex、sitemap 和 loc 元素，并可使用 lastmod 作为可选子标签。 [1][7]

### priority 标签会影响搜索结果排名吗？

根据 Sitemaps 协议和常见问题解答，priority 用于以 0.0 到 1.0（默认为 0.5）的标度表示某个 URL 相对于同一网站上其他 URL 的重要程度。它不用于比较不同网站之间的网页，且预期不会影响搜索结果排名。 [1][2]

### 搜索引擎如何发现站点地图文件？

sitemaps.org 常见问题解答介绍了向搜索引擎直接提交、向搜索引擎发送 ping 通知以及在 robots.txt 中列出站点地图位置三种方式，RFC 9309 也指出 robots.txt 解析器可支持 Sitemaps 行。2023 年 6 月，Google 搜索中心博客宣布 Google 的站点地图 ping 端点即将停用，而 Google Search Console 仍是直接提交渠道。 [2][4][6][10]

### 每个网站都需要站点地图吗？

根据 2025-12-10 更新的 Google 搜索中心文档，站点地图适用于大型网站、外部链接较少的新网站以及包含大量视频、图片或新闻内容的网站。网页数量在 500 个左右或更少、内部链接完整且不包含大量媒体或新闻网页的小型网站可能不需要站点地图。 [5]

## 可引用的句子

- Sitemaps.org 由 Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation 赞助，其协议规范采用知识共享署名-相同方式共享 2.5 许可协议（Creative Commons Attribution-ShareAlike License version 2.5）授权。 [3]
- 截至 2026-11-23，Sitemaps 协议 0.9 要求采用 UTF-8 编码、XML 命名空间 http://www.sitemaps.org/schemas/sitemap/0.9，以及包含 urlset、url 和 loc 元素，且 loc 的值须短于 2,048 个字符。 [1]
- 截至 2026-11-23，单个站点地图文件最多可包含 50,000 个 URL，且未压缩大小不得超过 50 MB（52,428,800 字节）；站点地图索引文件在相同的未压缩 50 MB 限制内最多可列出 50,000 个站点地图。 [1][2]
- Sitemaps 协议 0.9 提供了用于验证的 XML 架构 sitemap.xsd 和 siteindex.xsd，并支持将 RSS 2.0、Atom 0.3 或 1.0 以及 UTF-8 纯文本文件作为替代格式。 [1][2]
- IETF 于 2022 年 9 月发布的 RFC 9309 在 robots.txt 的 ABNF 形式化语法中指出，解析器实现者可以定义 Sitemaps 等附加行。 [4]
- 截至 2025-12-10，Google Search Console 允许每个网站最多提交 500 个站点地图索引文件，且通过 Search Console 提交站点地图可解除默认的父目录范围限制。 [6][7]
- 截至 2025-12-10，Google 的图片站点地图扩展（http://www.google.com/schemas/sitemap-image/1.1）允许每个 url 元素最多包含 1,000 个 image:image 标签，且 Google 已从其文档中移除了 image:caption、image:geo_location、image:title 和 image:license。 [8]
- Google 的新闻站点地图扩展（http://www.google.com/schemas/sitemap-news/0.9）允许每个站点地图最多包含 1,000 个 news:news 条目，并将条目限制为最近两天内发布的文章。 [9]

## 时间线

- 2008-02-27: Sitemaps.org 更新服务条款，将 Google, Inc.、Yahoo, Inc. 和 Microsoft Corporation 列为赞助方，并规定该规范采用知识共享署名-相同方式共享 2.5 许可协议。 [3]
- 2016-11-21: Sitemaps.org 更新常见问题解答，记录了 50 MB（52,428,800 字节）和 50,000 个 URL 的限制以及 sitemap.xsd 和 siteindex.xsd XML 架构。 [2]
- 2022-05: Google 搜索中心博客发布通知，宣布移除部分站点地图扩展标签。 [8][10]
- 2022-09: IETF 发布 RFC 9309（爬虫排除协议），在其 ABNF 形式化语法中指出 robots.txt 解析器可定义 Sitemaps 等附加行。 [4]
- 2023-06: Google 搜索中心博客发布公告，宣布 Google 的站点地图 ping 端点即将停用。 [10]
- 2025-12-10: Google 搜索中心更新站点地图概述、站点地图索引文件和图片站点地图相关文档。 [5][7][8]

## 来源

1. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (访问于 2026-11-23; tier 3: official site)
2. sitemaps.org - FAQ. sitemaps.org. 发布于 2016-11-21. https://www.sitemaps.org/faq.html (访问于 2026-11-23; tier 3: official site)
3. sitemaps.org - Terms of service. sitemaps.org. 发布于 2008-02-27. https://www.sitemaps.org/terms.html (访问于 2026-11-23; tier 3: official site)
4. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (访问于 2026-11-23; tier 1: government or public registry)
5. What Is a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. 发布于 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview (访问于 2026-11-23; tier 3: official site)
6. Build and Submit a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (访问于 2026-11-23; tier 3: official site)
7. Manage Your Sitemaps With Sitemap Index Files | Google Search Central | Documentation | Google for Developers. Google Search Central. 发布于 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/large-sitemaps (访问于 2026-11-23; tier 3: official site)
8. Image Sitemaps | Google Search Central | Documentation | Google for Developers. Google Search Central. 发布于 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps (访问于 2026-11-23; tier 3: official site)
9. Create a News Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap (访问于 2026-11-23; tier 3: official site)
10. Sitemaps ping endpoint is going away | Google Search Central Blog | Google for Developers. Google Search Central Blog. 发布于 2023-06. https://developers.google.com/search/blog/2023/06/sitemaps-lastmod-ping (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "站点地图." 版本 5b53edc2, 2026-11-23. https://mimirwiki.com/zh/wiki/sitemaps
