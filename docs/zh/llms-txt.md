---
title: "llms.txt"
subtitle: "引导 AI 代理访问网站核心内容的 Markdown 文件提案"
canonical_url: https://mimirwiki.com/zh/wiki/llms-txt
language: zh
page_class: anchor
revision_sha256: 3610577fc441e4ecd96be7b51c378731ae989d3818f9fa08d26c98d01c35a35c
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/zh/wiki/llms-txt.md
  txt: https://mimirwiki.com/zh/wiki/llms-txt.txt
  json: https://mimirwiki.com/zh/wiki/llms-txt.json
  jsonld: https://mimirwiki.com/zh/wiki/llms-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/llms-txt
  ko: https://mimirwiki.com/ko/wiki/llms-txt
  ja: https://mimirwiki.com/ja/wiki/llms-txt
---

# llms.txt

> llms.txt 是一项 Web 惯例提案，指通常位于 /llms.txt 的 Markdown 文件，用于向 AI 代理提供网站的简明概览以及指向核心页面纯 Markdown 版本的链接。杰里米·霍华德于 2024 年 9 月 3 日发布了该提案，并于 2026 年 8 月发布了第 2 版。该规范属于社区提案，网站可自行选择是否发布。

llms.txt 是一项 Web 惯例提案，建议网站发布一个名为 llms.txt 的 Markdown 文件，为大语言模型（LLM）和 AI 代理提供网站简明概览以及指向更详细、对 LLM 友好内容的链接。杰里米·霍华德（Jeremy Howard）于 2024 年 9 月 3 日在 llmstxt.org 发布了该提案，并于 2026 年 8 月发布了第二版（v2）。该文件可置于网站根目录（/llms.txt）或任意子路径下，并遵循固定的章节顺序，便于常规解析器读取。llmstxt.org 将 llms.txt 定位为持续开放社区意见的提案。

**别名:** /llms.txt, The /llms.txt file, llms.txt 提案

## 关键事实

- **首次发布:** 2024-09-03 [1]
- **当前版本:** v2（2026 年 8 月） (截至 2026-11-21) [2]
- **作者:** 杰里米·霍华德（Jeremy Howard） [1]
- **必需内容:** 一个包含项目或网站名称的 H1 标题 [1]
- **存放位置:** 网站根目录下的 /llms.txt，或任意子路径 [1]

## 事实摘要

- **类型:** 面向 LLM 与 AI 代理的 Markdown 引导文件 Web 惯例提案 [1]
- **作者:** 杰里米·霍华德（Jeremy Howard） [1]
- **首次发布:** 2024-09-03 [1]
- **当前版本:** v2（2026 年 8 月） (截至 2026-11-21) [2]
- **文件名:** llms.txt [1]
- **存放位置:** 网站根目录（/llms.txt）或任意子路径，例如 /docs/llms.txt [1]
- **格式:** 具有固定章节顺序的 Markdown [1]
- **必需内容:** 包含项目或网站名称的 H1 标题 [1]
- **发现机制:** 链接关系 alternate（类型 text/markdown）与 describedby [1]
- **状态:** 提案阶段，开放社区意见 [1]
- **代码仓库:** github.com/AnswerDotAI/llms-txt（Apache-2.0 许可证） [3]
- **参考工具:** 包含 llms_txt2ctx 命令的 llms-txt Python 包 [4]

## 什么是 llms.txt

llms.txt 是一项关于 [Markdown](https://mimirwiki.com/zh/wiki/markdown) 文件的提案，网站通过发布该文件，为大语言模型（LLM）和 AI 代理提供站点内容的简明指南。[1] 该提案指出，网页原本面向人类读者设计，HTML 页面中的正文信息被导航栏、广告和脚本包围，且大多数网站的体量远超模型的上下文窗口容量。[1] 因此，llms.txt 文件将简短的背景介绍、使用指引以及指向更详细 Markdown 文件的链接汇集于一处。[1]

llms.txt 提案包含两部分：第一部分是 `llms.txt` 文件本身；第二部分是代理可能需要的各页面精简 Markdown 版本，以原页面相同 URL 加上 `.md` 扩展名的形式提供。[1] 代理可通过读取或检索 llms.txt 文件定位所需内容，再按需访问相应链接获取详细信息。[1]

杰里米·霍华德（Jeremy Howard）于 2024 年 9 月 3 日发布了 llms.txt 提案，并于 2026 年 8 月发布了标记为 v2 的修订版。[1][2] 该提案在 GitHub 的 AnswerDotAI/llms-txt 仓库中以 Apache-2.0 许可证进行维护。[3] 根据提案说明，llms.txt 文件目前最常用于软件文档。[1]

## llms.txt 文件格式

llms.txt 文件采用 Markdown 编写，并按固定顺序包含以下部分。[1]

- 可选的字节顺序标记（BOM）
- 包含项目或网站名称的 H1 标题，这是唯一必需的部分
- 包含项目简短摘要的引用块（blockquote）
- 零个或多个不含标题的任意类型 Markdown 段落，用于承载更详细的信息
- 零个或多个以 H2 标题引导的章节，每个章节包含指向进一步详情的链接列表

llms.txt 链接列表中的每个条目均为 `[name](url)` 形式的 Markdown 超链接，其后可选择性附加冒号及关于所链接文件的说明文字。[1] 标题为 Optional 的章节用于存放次要链接，当代理需要更短的上下文时可以跳过这些链接。在 v2 中，由于赋予该章节机械含义的工具已不再属于提案内容，此做法仅作为一项惯例保留。[1][2]

该提案选择 Markdown 而非 XML 等结构化格式，是因为文件主要面向语言模型和代理阅读；同时，固定的版式依然允许使用常规解析器和正则表达式进行处理。[1]

## llms.txt 的存放位置与发现机制

llms.txt 文件可以放置在网站根路径 `/llms.txt`，也可以放置在诸如 `/docs/llms.txt` 的任意子路径下。每个文件覆盖其所在路径下的 URL；当多个文件同时适用时，代理应使用路径最具体的文件。[1] 提案第一版虽然允许使用子路径，但未界定其含义，v2 补充了这一规则。[2]

对于单个页面，llms.txt 提案要求在相同 URL 下提供 Markdown 版本，既可在原路径后追加 `.md`（`page.html.md`），也可替换原扩展名（`page.md`）。不含文件名的 URL 则使用 `index.html.md` 或 `index.md`。[1] 第一版此前仅规定了追加形式。[2]

第 2 版新增了基于标准链接关系的发现机制：带有 `rel="alternate"` 和 `type="text/markdown"` 的链接指向页面的 Markdown 版本，`rel="describedby"` 则指向覆盖该页面的 llms.txt 文件，两者均可通过 HTML `link` 元素或 HTTP `Link` 响应头提供。[1][2] 关系类型 `alternate` 和 `describedby` 均已在 IANA 链接关系注册表（IANA Link Relations registry）中注册。[9] 该提案未采用 RFC 8615 定义的 `/.well-known/` 路径前缀，理由是知名 URI（well-known URI）仅能存在于源站根目录，而许多作者在共享主机上仅控制特定子路径。[1][8]

## llms.txt 与 robots.txt 及 sitemap.xml 的区别

llms.txt 与 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 的用途各不相同。IETF 于 2022 年 9 月以 RFC 9309 发布的机器人排除协议（Robots Exclusion Protocol）允许服务所有者控制爬虫访问其内容的方式。[7] llms.txt 提案将访问控制交由 robots.txt 处理，并将自身内容定位为代理在协助用户时按需查阅的主题信息。[1]

llms.txt 也不同于列出站点所有可索引人类可读页面的[站点地图](https://mimirwiki.com/zh/wiki/sitemaps)（sitemap）。提案给出了站点地图无法替代 llms.txt 的三点理由：站点地图通常不包含适合 LLM 阅读的页面版本、不收录外部网站的 URL，且其涵盖的全部文档总和往往超出上下文窗口容量。[1] 相比之下，llms.txt 被定位为经过筛选的站点概览。[1]

作者曾明确表示，预期 llms.txt 主要服务于推理阶段（即回答问题时的即时调用），而非模型训练；v2 文本指出，该文件的实际应用情况正符合这一预期。[1]

## llms.txt 的采用情况与工具生态

由提案作者撰写的 llms.txt v2 文本称，已有数千个网站发布了 llms.txt 文件，OpenAI、Anthropic 以及 Google 的 Gemini API 均已为其开发者文档提供了 llms.txt。[1] 文本列举了 Mintlify、GitBook、Yoast SEO、AIOSEO 和 Wix 等能够自动生成该文件的平台与插件。[1]

Mintlify 的文档显示，其会在每个文档项目的根目录托管一个 llms.txt 文件，同时还会生成名为 `llms-full.txt` 的文件。[10] `llms-full.txt` 这一名称源自此类平台，并未出现在 llmstxt.org 的提案中。[1][10] 一个公开实例是 [Model Context Protocol](https://mimirwiki.com/zh/wiki/model-context-protocol) 文档网站，该站点在 `modelcontextprotocol.io/llms.txt` 提供了页面索引。[11]

llmstxt.org 网站记录了一个名为 `llms-txt` 的 Python 包，其中包含命令行工具 `llms_txt2ctx`，可解析 llms.txt 文件并据此构建 XML 上下文文件。[4] 提案第一版曾介绍该工具，但在 v2 中，上下文展开功能已不再属于提案本身。[2]

## llms.txt 的当前状态与局限

llms.txt 目前仍处于提案阶段。llmstxt.org 将该规范描述为持续接受社区意见，并在公开 GitHub 仓库中维护了一份非正式概览。[1] 最近更新于 2026 年 5 月 5 日的 Chrome Lighthouse 文档将 llms.txt 称为一项新兴惯例。由于提供该文件属于可选项，当网站对该文件返回 404 时，Lighthouse 会将 llms.txt 审计项标记为“不适用”，仅在获取过程中发生服务器错误时才标记页面问题。[5]

发布 llms.txt 并非接入 Google AI 搜索功能的必要条件。最近更新于 2025 年 12 月 10 日的 Google 搜索中心文档指出，网站所有者无需创建新的机器可读文件或 AI 文本文件即可出现在 AI 概览（AI Overviews）或 AI 模式（AI Mode）中。[6]

llms.txt 并不替代其他 Web 惯例：设置爬虫权限仍由 robots.txt 负责，且 llms.txt 也不像站点地图那样提供穷尽式的页面索引。[1][7] 提案同时提到，llms.txt 文件可以引用网站所使用的结构化数据标记，以帮助模型结合上下文理解这些标记。[1]

## 常见问题

### 什么是 llms.txt？

llms.txt 是一项 Markdown 文件提案，网站可通过发布该文件向 AI 代理提供站点简明概览及指向更详细内容的链接。杰里米·霍华德于 2024 年 9 月 3 日发布了该提案。 [1]

### llms.txt 文件应放置在何处？

应放置在根路径 /llms.txt 或诸如 /docs/llms.txt 的任意子路径下。文件覆盖其路径下的所有 URL，当存在多个文件时，适用路径最具体的文件。 [1]

### llms.txt 是官方 Web 标准吗？

llmstxt.org 将 llms.txt 描述为开放社区意见的提案。最近更新于 2026 年 5 月 5 日的 Chrome Lighthouse 文档将其称为新兴惯例，并将提供该文件视为可选项。 [1][5]

### llms.txt 与 robots.txt 有何区别？

由 RFC 9309 规范的 robots.txt 用于告知爬虫网站允许哪些访问行为；llms.txt 不设置访问权限，而是供代理按需阅读、用于定位网站核心内容的精选概览。 [1][7]

### Google 的 AI 概览或 AI 模式是否要求使用 llms.txt？

不要求。最近更新于 2025 年 12 月 10 日的 Google 搜索中心文档表示，网站无需创建任何新的机器可读文件或 AI 文本文件即可出现在这些功能中。 [6]

### llms.txt v2 有哪些变化？

2026 年 8 月发布的第 2 版新增了通过 alternate 和 describedby 链接关系进行发现的机制，允许 Markdown 页面版本采用两种 URL 形式，明确了子路径文件的覆盖范围，并将上下文展开工具移出了提案范围。 [2]

## 可引用的句子

- llms.txt 提案由杰里米·霍华德于 2024 年 9 月 3 日发布。 [1]
- llms.txt 提案第 2 版于 2026 年 8 月发布。 [2]
- llms.txt 文件中唯一必需的部分是包含项目或网站名称的 H1 标题。 [1]
- llms.txt 文件可放置在网站根目录或任意子路径下，并覆盖其路径下的 URL。 [1]
- llms.txt 提案第 2 版推荐使用类型为 text/markdown 的 alternate 链接关系以及 describedby 链接关系进行发现。 [1]
- 最近更新于 2026 年 5 月 5 日的 Chrome Lighthouse 文档将提供 llms.txt 文件描述为可选项。 [5]
- Google 搜索中心文档指出，网站无需创建新的机器可读文件或 AI 文本文件即可出现在 AI 概览或 AI 模式中。 [6]
- llms.txt 提案在 GitHub 的 AnswerDotAI/llms-txt 仓库中以 Apache-2.0 许可证进行维护。 [3]

## 时间线

- 2024-09-03: 杰里米·霍华德发布 llms.txt 提案。 [1]
- 2026-08: llms.txt 提案第 2 版发布。 [2]

## 来源

1. The /llms.txt file, v2 – llms-txt. llmstxt.org. 发布于 2024-09-03. https://llmstxt.org/ (访问于 2026-11-21; tier 3: official site)
2. Changes – llms-txt. llmstxt.org. 发布于 2026-08. https://llmstxt.org/changes.html (访问于 2026-11-21; tier 3: official site)
3. GitHub - AnswerDotAI/llms-txt: The /llms.txt file, helping language models use your website. AnswerDotAI (GitHub). https://github.com/AnswerDotAI/llms-txt (访问于 2026-11-21; tier 3: official site)
4. Python module & CLI – llms-txt. llmstxt.org. https://llmstxt.org/intro.html (访问于 2026-11-21; tier 3: official site)
5. llms.txt | Lighthouse | Chrome for Developers. Google (Chrome for Developers). 发布于 2026-05-05. https://developer.chrome.com/docs/lighthouse/agentic-browsing/llms-txt (访问于 2026-11-21; tier 3: official site)
6. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. 发布于 2025-12-10. https://developers.google.com/search/docs/appearance/ai-features (访问于 2026-11-21; tier 3: official site)
7. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 发布于 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (访问于 2026-11-21; tier 1: government or public registry)
8. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 发布于 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (访问于 2026-11-21; tier 1: government or public registry)
9. Link Relations. Internet Assigned Numbers Authority (IANA). 发布于 2026-06-12. https://www.iana.org/assignments/link-relations/link-relations.xhtml (访问于 2026-11-21; tier 1: government or public registry)
10. llms.txt - Mintlify. Mintlify. https://www.mintlify.com/docs/ai/llmstxt (访问于 2026-11-21; tier 3: official site)
11. Model Context Protocol (llms.txt documentation index). Model Context Protocol project. https://modelcontextprotocol.io/llms.txt (访问于 2026-11-21; tier 3: official site)

## 引用本页

Mimirwiki. "llms.txt." 版本 3610577f, 2026-11-21. https://mimirwiki.com/zh/wiki/llms-txt
