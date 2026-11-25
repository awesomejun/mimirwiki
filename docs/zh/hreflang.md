---
title: "hreflang"
subtitle: "用于指定所链接网页资源语言和目标地区的 HTML 属性与链接参数"
canonical_url: https://mimirwiki.com/zh/wiki/hreflang
language: zh
page_class: anchor
revision_sha256: 8b353b435943852cc32ef716b7cd8d653d88f21cabe5219853153590d5b8511f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/zh/wiki/hreflang.md
  txt: https://mimirwiki.com/zh/wiki/hreflang.txt
  json: https://mimirwiki.com/zh/wiki/hreflang.json
  jsonld: https://mimirwiki.com/zh/wiki/hreflang.jsonld
translations:
  en: https://mimirwiki.com/wiki/hreflang
  ko: https://mimirwiki.com/ko/wiki/hreflang
  ja: https://mimirwiki.com/ja/wiki/hreflang
  es: https://mimirwiki.com/es/wiki/hreflang
---

# hreflang

> hreflang 是一种 HTML 属性和链接参数，使用 RFC 5646 定义的 BCP 47 标签标识所链接资源的语言以及可选的地区。网站通过 HTML link 元素、HTTP Link 标头或 XML 站点地图发布 hreflang 注释，以便 Google 搜索将用户引导至匹配的本地化页面版本。

hreflang 是一种 HTML 属性和链接注释参数，用于指示所链接网页资源的人类语言以及可选的目标地区。它在 WHATWG HTML Living Standard 中被定义为反射属性，并与 IETF RFC 5646 规定的 BCP 47 语言标签配合使用；在锚点元素上不具备浏览器内置行为，而是作为供外部链接处理器使用的元数据。在 Google 搜索中，网站通过 HTML link 元素、RFC 8288 定义的 HTTP Link 标头或 XML 站点地图，将 hreflang 注释与 alternate 链接关系结合发布，以关联同一页面的不同本地化版本。Google 要求所列变体之间建立双向互链，并支持使用 x-default 值指定在没有任何所列语言或地区匹配时的回退页面。

**别名:** hreflang 属性, hreflang 标签, hreflang 注释, rel=alternate hreflang

## 关键事实

- **HTML 规范:** WHATWG HTML Living Standard（更新于 2026-11-22） (截至 2026-11-23) [1]
- **语言标签标准:** IETF BCP 47 / RFC 5646（2009 年 9 月） [2]
- **子标签注册表:** IANA 语言子标签注册表（文件日期 2026-11-18） (截至 2026-11-23) [4]
- **HTTP 标头规范:** IETF RFC 8288（Web Linking，2017 年 10 月） [3]
- **Google 提供方式:** HTML link 元素、HTTP Link 标头和 XML 站点地图 (截至 2026-11-23) [6]

## 事实摘要

- **类型:** 提示所链接 URL 人类语言的 HTML 属性 [9]
- **HTML 规范:** WHATWG HTML Living Standard 第 4.6 节（更新于 2026-11-22） (截至 2026-11-23) [1]
- **DOM API:** HyperlinkElementUtils.hreflang（反射 DOMString） [1]
- **语言标签语法:** IETF BCP 47（RFC 5646，2009 年 9 月；废止 RFC 4646） [2]
- **子标签注册表:** IANA 语言子标签注册表（文件日期 2026-11-18） (截至 2026-11-23) [4]
- **HTTP 标头规范:** IETF RFC 8288（Web Linking，2017 年 10 月；废止 RFC 5988） [3]
- **HTML link 基线支持:** HTML link 元素自 2015 年 7 月起在各主流浏览器中广泛可用 [8]
- **Google 提供方式:** HTML link 元素、HTTP Link 标头和 XML 站点地图 (截至 2026-11-23) [6]
- **回退值:** x-default（Google 搜索中心博客于 2013 年 4 月宣布） [10]
- **确认规则:** Google 搜索要求自引用与双向链接 (截至 2026-11-23) [6]

## 什么是 hreflang

hreflang 是一种 HTML 属性和链接注释参数，用于指示所链接网页资源的人类语言以及可选的目标地区。[6][9] 在 HTML 中，链接是由 `a`、`area`、`form` 和 `link` 元素创建的两个资源之间的概念连接，可分为外部资源链接、超链接和内部资源链接。[1]

在 WHATWG HTML Living Standard（最后更新于 2026-11-22）中，第 4.6.3 节在 `HyperlinkElementUtils` 接口混入上将 `hreflang` 定义为反射 `DOMString` 属性。[1] MDN Web Docs 同时记录了用于指定当前文档与外部资源关系的 HTML `link` 元素，以及用于创建超链接的 HTML `a` 锚点元素，并注明这两个元素自 2015 年 7 月起已在各主流浏览器中广泛可用。[8][9] 关于 `a` 元素，MDN 指出 `hreflang` 仅提示所链接 URL 的人类语言，没有内置浏览器功能，且接受与全局 `lang` 属性相同的语言标签值。[9]

在 Google 搜索中，网站将 `hreflang` 与 `alternate` 链接关系配对使用，以声明跨语言或跨地区的本地化页面版本，使搜索结果能够将用户导向与其语言或地区相匹配的版本。[6]

## hreflang 中使用的 BCP 47 与 RFC 5646 语言标签

hreflang 的取值采用由 2009 年 9 月发布的 IETF RFC 5646（《Tags for Identifying Languages》）规定的 BCP 47 语言标签。[2][5][9] RFC 5646 由 A. Phillips 和 M. Davis 编辑，废止了 RFC 4646（该规范曾取代 RFC 3066 和 RFC 1766），并与 RFC 4647 共同构成 BCP 47。[2][5]

BCP 47 语言标签由一个或多个以连字符（`-`，U+002D）分隔的字母数字子标签组成，按 `language-extlang-script-region-variant-extension-privateuse` 顺序排列。[2][5] 每种类型的子标签均可通过长度、位置和字符内容加以区分，除 RFC 3066 时期注册的一组固定历史遗留标签（grandfathered tags）外，处理器无需本地注册表副本即可识别子标签类别。[2]

| 子标签类型 | 格式 | 来源标准 | 示例 |
| --- | --- | --- | --- |
| 主语言 | 2 至 3 个字母（或 5 至 8 个已注册字母） | ISO 639 | `en`, `es`, `ast`, `mas` |
| 扩展语言 | 宏语言子标签后的 3 个字母 | ISO 639 | `zh-yue`, `ar-afb` |
| 文字 | 4 个字母（引入于 RFC 4646） | ISO 15924 | `zh-Hans`, `az-Latn` |
| 地区 | 2 个字母或 3 位数字 | ISO 3166-1 / UN M.49 | `fr-CA`, `en-GB`, `de-CH`, `es-419` |
| 变体 | 5 至 8 个字母数字，或 1 位数字加 3 个字母数字 | IANA 注册表 | 已注册的方言或正字法子标签 |
| 扩展与私有使用 | 单个字母数字单字符前缀（`x` 保留用于私有使用） | RFC 5646 | 单字符扩展；`x-` 私有使用标签 |

所有有效子标签均维护在单一纯文本文件 IANA 语言子标签注册表中，截至 2026-11-23，其文件日期为 2026-11-18。[4][5] 该注册表为每种语言采用一个 ISO 639 值（有双字母代码时选用双字母代码，否则选用一个三字母代码），并在 RFC 5646 发布时新增了 7,000 多个 ISO 639-3 三字母代码。[5] 注册表记录包含 `Type`、`Subtag`、`Description`、`Added`、`Suppress-Script`、`Scope`、`Deprecated` 和 `Preferred-Value` 等字段。[4][5] 例如，`bh`（比哈尔语）条目带有 2026-06-14 的弃用日期，且其 `Preferred-Value` 为 `bih`。[4]

W3C 指出，语言标签在 HTML 和 XML 中不区分大小写；将语言子标签写作小写、文字子标签首字母大写、字母型地区子标签写作大写仅为书写惯例。[5] W3C 建议尽量保持语言标签简短，在无法提供有效区分时省略地区或文字子标签，并遵循 `Suppress-Script` 条目（例如 `en`、`es` 和 `fr` 对应的 `Latn`）。[4][5] 对于 `zh-yue` 或 `ar-afb` 等历史遗留的“语言加扩展语言”组合，W3C 指出存在等效的独立主语言子标签（`yue` 或 `afb`），并建议尽可能使用独立子标签。[5]

## hreflang 注释的实现方法

截至 2026-11-23，Google 搜索中心文档规定了提供 hreflang 注释的三种等效方法：HTML `link` 元素、HTTP `Link` 标头以及 [XML 站点地图](https://mimirwiki.com/zh/wiki/sitemaps)。[6] Google 对这三种方法一视同仁，在同一组页面上同时使用多种方法会增加维护成本，而不会在搜索中带来额外收益。[6]

| 方法 | 位置与语法 | 典型用例 |
| --- | --- | --- |
| HTML `link` 元素 | 在 `head` 中添加包含 `rel="alternate"`、`hreflang` 和 `href` 的 `link` 元素 | 无法控制站点地图或 HTTP 标头的 HTML 页面 |
| HTTP `Link` 标头 | 在 GET 响应中以逗号分隔的 `Link` 标头条目标注，每个 URL 用尖括号括起并附带 `rel="alternate"` 和 `hreflang` | PDF 等非 HTML 文件 |
| XML 站点地图 | 声明 `xhtml` XML 命名空间，并在每个 `loc` 元素下添加 `xhtml:link` 子条目 | 集中管理多版本 URL 集合 |

在 HTML 文档中，`link` 元素必须位于格式良好的 `head` 元素内，为包括页面自身在内的每个变体各提供一个 `link` 元素。[6][8] 在 XHTML 1.0 下，`link` 等空元素（void element）需要尾随斜杠。[8] Google 规定 `hreflang` 注释必须置于专用的 `link` 元素中，不得在单个 `link` 元素内与 `media` 等其他替代表示属性混用。[6]

在 HTTP 标头方面，IETF RFC 8288（《Web Linking》，2017 年 10 月由 M. Nottingham 发布，废止了 RFC 5988）定义了通用的网页链接模型（链接上下文、链接关系类型、链接目标和可选目标属性），规定了在 HTTP `Link` 标头字段中序列化链接的方式，并纳入了 RFC 5646 的 `Language-Tag` 语法。[3] 包括 `alternate` 在内的已注册链接关系类型维护在 IANA 链接关系注册表中。[3] 在 Google 搜索中，资源的 GET 响应所返回的 `Link` 标头以逗号分隔列出所有本地化版本，每个完全限定 URL 用尖括号括起，后接 `rel="alternate"` 和 `hreflang`，且资源的每个版本都必须返回相同的标头。[6]

在 [XML 站点地图](https://mimirwiki.com/zh/wiki/sitemaps)中，每个本地化版本拥有各自的 `loc` 元素，并在声明 `xhtml` 命名空间的情况下配对子级 `xhtml:link` 条目，列出该页面包括自身在内的所有语言和地区变体。[6] 当一个页面有三个版本时，站点地图包含三个 `loc` 条目，每个条目下都包含三个相同的 `xhtml:link` 子条目。[6]

## hreflang 的相互链接与 URL 规则

Google 搜索在 HTML `link` 元素、HTTP `Link` 标头和 XML 站点地图中强制执行统一的结构规则，以确保本地化分组中的每个 URL 都能相互验证。[6]

- **自引用与完整集合**：页面的每个语言或地区版本都必须列出自身及所有其他变体，从而在分组中的每个版本上形成完全一致的注释集合。[6]
- **双向确认**：如果两个页面没有相互指向对方，Google 将忽略相应的注释。此规则可防止外部网站擅自将自身声明为另一网站页面的替代版本。[6]
- **部分双向链接**：当在所有语言之间维护完整的双向链接不切实际时，部分页面可以省略部分语言。Google 仍会处理相互双向链接的页面对，并建议将新增语言页面与网站的原始语言或主要语言页面进行双向互链。[6]
- **完全限定 URL**：每个替代 URL 都必须包含传输协议方案（`http` 或 `https`），例如 `https://example.com/foo`，不允许使用协议相对 URL（`//example.com/foo`）和相对路径（`/foo`）。[6]
- **跨域名支持**：替代 URL 无需隶属于同一域名。[6]
- **通用语言兜底**：当多个地区 URL 面向同一语言的使用者（例如 `en-IE`、`en-CA` 和 `en-AU`）时，Google 建议为未指定地区的用户提供通用语言条目（`en`），该条目可以复用其中一个地区 URL。[6]

Google 不会根据 URL 中特定语言的子域名（例如 `en`、`en-gb`、`en-us` 或 `de`）推断页面的目标受众，因此每个目标语言或地区都必须通过 `hreflang` 注释显式映射。[6]

## 用于回退页面的 x-default hreflang 值

`x-default` hreflang 值用于为语言或地区与页面上任何显式列出的变体均不匹配的访客指定回退 URL。[6] Google 搜索中心博客于 2013 年 4 月发布公告，推出面向国际着陆页的 `x-default` hreflang，并在之后收录了一篇 2023 年 5 月题为《How x-default can help you》的博客文章。[10]

Google 搜索中心文档特别强调将 `x-default` 用于语言或国家选择页面以及自动重定向访客的主页。[6] 在 Google 的文档示例中，一个同时提供英国英语（`en-GB`）、美国英语（`en-US`）、通用英语（`en`）和德语（`de`）页面的网站，将 `hreflang="x-default"` 分配给包含语言和地区选择器的中性着陆页 `https://www.example.com/`。[6]

`x-default` 值可与标准 BCP 47 语言标签一同在 HTML `link` 元素、HTTP `Link` 标头和 XML 站点地图中使用。[6]

## Google 搜索对 hreflang 与多语言网站的处理

Google 搜索利用 hreflang 注释识别等效内容的本地化版本，并向搜索者呈现与其语言或地区设置相匹配的版本。[6] Google 将多语言网站（提供多种语言内容的网站，例如面向加拿大企业的英语和法语版本）与多地区网站（明确面向不同国家用户的网站，例如加拿大和美国）区分开来，并指出单个网站可以同时具备这两种属性。[7]

Google 搜索不使用 `hreflang`、HTML `lang` 属性或 URL 来检测页面语言。[6][7] Google 通过算法根据页面上的可见内容判断页面语言，并建议每个页面的正文与导航均使用单一语言，避免并排呈现多语翻译。[6][7]

Google 在文档中列举了三种常见的 `hreflang` 应用场景：仅翻译模板（导航和页脚）而主要用户生成内容保持单一语言的页面、同一语言下存在细微地区差异的页面（例如面向美国、英国和爱尔兰的英语页面），以及完全翻译为多种语言的页面。[6] 仅当主要内容未翻译时，页面的本地化版本才会被视为重复内容。[6]

Google 建议为每个语言版本分配独立的 URL，并通过 `hreflang` 注释将其关联。[7] 通过 Cookie 或浏览器设置动态切换内容可能会妨碍 Googlebot 发现所有变体，因为 Googlebot 通常从美国发起抓取，且其 HTTP 请求不包含 `Accept-Language` 标头。[7] Google 还建议避免根据推测的用户语言执行自动重定向，推荐提供超链接让用户手动切换版本，同时支持使用 UTF-8 编码和正确 URL 转义的本地化 URL 词汇及国际化域名（IDN）。[7]

## 常见问题

### 什么是 hreflang？

hreflang 是一种 HTML 属性和链接注释参数，使用 BCP 47 语言标签指示所链接网页资源的人类语言以及可选的目标地区。在 Google 搜索中，网站将 hreflang 与 alternate 链接关系配对使用，以关联同一页面的不同本地化版本。 [2][6][9]

### 有哪些方法可以为 Google 搜索实现 hreflang？

截至 2026-11-23，Google 搜索支持三种等效方法：位于 head 元素内的 HTML link 元素、适用于 PDF 等非 HTML 文件的 HTTP Link 响应标头，以及 XML 站点地图中的 xhtml:link 子条目。同时使用多种方法不会带来额外的搜索收益。 [6]

### 为什么 hreflang 链接必须是双向的？

Google 搜索要求本地化页面集合中的每个页面都引用自身以及所有其他变体，并会忽略未相互指向的页面对。这一确认规则可防止其他网站擅自将自身声明为不受其控制页面的替代版本。 [6]

### hreflang="x-default" 是什么意思？

x-default 值用于为语言或地区与任何显式列出的 hreflang 标签均不匹配的用户指定回退页面。Google 于 2013 年 4 月宣布推出 x-default，并在文档中说明了其用于语言或国家选择页面以及自动重定向主页的用法。 [6][10]

### Google 搜索是否使用 hreflang 检测页面语言？

不是。Google 搜索不使用 hreflang、HTML lang 属性或 URL 来检测页面语言。Google 会通过算法根据页面可见内容判断页面语言，并使用 hreflang 识别同一内容的本地化版本。 [6][7]

### hreflang 的语言和地区代码如何格式化？

语言标签遵循 IETF BCP 47（RFC 5646），将来自 IANA 语言子标签注册表的子标签以连字符组合：以 2 个或 3 个字母的 ISO 639 主语言子标签开头，后面可选接 4 个字母的 ISO 15924 文字子标签，或 2 个字母的 ISO 3166-1 / 3 位数字的 UN M.49 地区子标签。语言标签在 HTML 和 XML 中不区分大小写。 [2][4][5]

## 可引用的句子

- WHATWG HTML Living Standard（最后更新于 2026-11-22）将 hreflang 定义为 HyperlinkElementUtils 接口混入上的反射 DOMString 属性。 [1]
- MDN Web Docs 指出，HTML a 元素上的 hreflang 属性用于提示所链接 URL 的人类语言，没有内置功能，且接受与全局 lang 属性相同的值。 [9]
- IETF RFC 5646 于 2009 年 9 月作为 BCP 47 的一部分发布，规定了以连字符分隔的子标签语言标签语法，并废止了 RFC 4646。 [2]
- 有效的语言、文字和地区子标签维护在 IANA 语言子标签注册表中，截至 2026-11-23，其文件日期为 2026-11-18。 [4][5]
- IETF RFC 8288 发布于 2017 年 10 月，规定了 HTTP Link 标头字段并引用了 RFC 5646 的 Language-Tag 语法。 [3]
- 截至 2026-11-23，Google 搜索中心文档将 HTML link 元素、HTTP Link 标头和 XML 站点地图列为指定 hreflang 注释的三种等效方法。 [6]
- 除非两个页面相互链接，且每个页面都列出了自身及所有替代版本，否则 Google 搜索会忽略这两个页面之间的 hreflang 注释。 [6]
- Google 搜索中心博客于 2013 年 4 月宣布推出面向国际着陆页的 x-default hreflang 值。 [10]

## 时间线

- 2009-09: IETF 作为 BCP 47 的一部分发布 RFC 5646（《Tags for Identifying Languages》），废止了 RFC 4646，并向 IANA 语言子标签注册表新增了 7,000 多个 ISO 639-3 三字母语言代码。 [2][5]
- 2013-04: Google 搜索中心博客发布公告，推出面向国际着陆页的 x-default hreflang。 [10]
- 2015-07: 据 MDN Web Docs 记录，HTML link 和 a 元素达到浏览器基线可用状态。 [8][9]
- 2017-10: IETF 发布 RFC 8288（《Web Linking》），废止了 RFC 5988，并定义了采用 RFC 5646 语言标签语法的 HTTP Link 标头序列化规范。 [3]

## 来源

1. HTML Standard. WHATWG. 发布于 2026-11-22. https://html.spec.whatwg.org/multipage/links.html (访问于 2026-11-23; tier 1: government or public registry)
2. RFC 5646: Tags for Identifying Languages. Internet Engineering Task Force (IETF). 发布于 2009-09. https://www.rfc-editor.org/rfc/rfc5646.txt (访问于 2026-11-23; tier 1: government or public registry)
3. RFC 8288: Web Linking. Internet Engineering Task Force (IETF). 发布于 2017-10. https://www.rfc-editor.org/rfc/rfc8288.txt (访问于 2026-11-23; tier 1: government or public registry)
4. IANA Language Subtag Registry. Internet Assigned Numbers Authority (IANA). 发布于 2026-11-18. https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry (访问于 2026-11-23; tier 1: government or public registry)
5. Language tags in HTML and XML. World Wide Web Consortium (W3C). https://www.w3.org/International/articles/language-tags/ (访问于 2026-11-23; tier 1: government or public registry)
6. Localized Versions of your Pages | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/localized-versions (访问于 2026-11-23; tier 3: official site)
7. Managing Multi-Regional and Multilingual Sites | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (访问于 2026-11-23; tier 3: official site)
8. <link> HTML external resource link element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/link (访问于 2026-11-23; tier 3: official site)
9. <a> HTML anchor element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a (访问于 2026-11-23; tier 3: official site)
10. Introducing "x-default hreflang" for international landing pages | Google Search Central Blog | Google for Developers. Google Search Central Blog. 发布于 2013-04. https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "hreflang." 版本 8b353b43, 2026-11-23. https://mimirwiki.com/zh/wiki/hreflang
