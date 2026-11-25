---
title: "Markdown"
subtitle: "轻量级纯文本标记语言、text/markdown 媒体类型，以及 CommonMark 与 GFM 等标准化规范"
canonical_url: https://mimirwiki.com/zh/wiki/markdown
language: zh
page_class: anchor
revision_sha256: 80dd4d0113e36bd14ab9d1c1b1d6ec4913b12dd3b688ee79c28616d4d716ae89
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/zh/wiki/markdown.md
  txt: https://mimirwiki.com/zh/wiki/markdown.txt
  json: https://mimirwiki.com/zh/wiki/markdown.json
  jsonld: https://mimirwiki.com/zh/wiki/markdown.jsonld
translations:
  en: https://mimirwiki.com/wiki/markdown
  ko: https://mimirwiki.com/ko/wiki/markdown
  ja: https://mimirwiki.com/ja/wiki/markdown
  es: https://mimirwiki.com/es/wiki/markdown
---

# Markdown

> Markdown 是一种轻量级标记语言，于 2004 年由约翰·格鲁伯在亚伦·斯沃茨的贡献下创建，用于编写可读性高且可转换为 HTML 的纯文本。其主要变体包括 CommonMark 和 GitHub Flavored Markdown。IETF 于 2016 年 3 月通过 RFC 7763 注册了 text/markdown 媒体类型，llms.txt 等提案也将 Markdown 用于 AI 智能体。

Markdown 是一种轻量级标记语言及纯文本排版语法族，可将易于阅读的纯文本转换为 HTML 等正式标记语言。约翰·格鲁伯（John Gruber）于 2004 年在亚伦·斯沃茨（Aaron Swartz）的重要贡献下开发了 Markdown，并在类 BSD 开源许可证下发布了语法说明与名为 Markdown.pl 的 Perl 转换器。由于原始说明存在语法歧义且各实现逐渐分化，CommonMark 规范于 2014 年启动以制定无歧义的解析规则；随后，互联网工程任务组（IETF）于 2016 年 3 月通过 RFC 7763 注册了 text/markdown 媒体类型，并发布了配套指南 RFC 7764。GitHub Flavored Markdown（GFM）等方言通过表格和任务列表等功能扩展了 CommonMark，而 llms.txt 等 Web 惯例则使用 Markdown 为大语言模型和 AI 智能体提供结构化文档。

**别名:** text/markdown, CommonMark, GFM, GitHub Flavored Markdown

## 关键事实

- **创建者:** 约翰·格鲁伯（亚伦·斯沃茨贡献） [2]
- **首次发布:** 2004 年（Markdown 1.0.1 发布于 2004-12-17） [3]
- **MIME 媒体类型:** text/markdown（RFC 7763，2016 年 3 月） [1]
- **正式核心规范:** CommonMark（2014 年启动） [5]
- **主要扩展方言:** GitHub Flavored Markdown（GFM），0.29-gfm 版（2019-04-06） (截至 2026-11-23) [6]

## 事实摘要

- **类型:** 轻量级标记语言与纯文本排版语法 [1]
- **创建者:** 约翰·格鲁伯（亚伦·斯沃茨作出重要贡献） [2]
- **首次发布:** 2004 年 [2]
- **原始转换器:** Markdown.pl 1.0.1（Perl，18 KB，2004-12-17，类 BSD 开源许可证） [3]
- **MIME 媒体类型:** text/markdown（必需参数：charset；可选参数：variant） [1]
- **IETF 文档:** RFC 7763 与 RFC 7764（信息类，2016 年 3 月，作者 S. Leonard） [2]
- **核心规范:** CommonMark（2014 年启动，由约翰·麦克法兰撰写） [7]
- **参考实现:** cmark（C）与 commonmark.js（JavaScript），BSD 许可证 [7]
- **CommonMark 维护者:** 约翰·麦克法兰、Martin Woodward、杰夫·阿特伍德 (截至 2026-11-23) [5]
- **GFM 规范:** 0.29-gfm 版（2019-04-06），CommonMark 的严格超集 (截至 2026-11-23) [6]
- **AI Web 惯例:** 用于 llms.txt 提案（/llms.txt 与 .md 页面版本） [8]

## Markdown 的起源与设计理念

Markdown 于 2004 年由约翰·格鲁伯（John Gruber）开发，亚伦·斯沃茨（Aaron Swartz）作出了重要贡献。[2][5] 格鲁伯将 Markdown 定义为两部分：一种纯文本排版语法，以及一个将纯文本格式转换为结构有效 HTML 的 Perl 软件工具（`Markdown.pl`）。[3] Markdown 1.0.1（18 KB）于 2004 年 12 月 17 日在类 BSD 开源许可证下作为自由软件发布，这也是 `Markdown.pl` 的最后一个更新版本。[3][5]

`Markdown.pl` 需要 Perl 5.6.0 或更高版本以及标准模块 `Digest::MD5`。[3] 它默认对空元素生成 XHTML 风格标签，作者也可以通过命令行选项 `--html4tags` 或 Movable Type 中的 `MTMarkdownOptions` 容器标签将其配置为输出 HTML 4。[3] 格鲁伯记录的早期支持环境包括 Movable Type 2.6 或更高版本（可选集成 SmartyPants 1.5 或更高版本以处理印刷体引号、破折号和省略号）、Blosxom 2.0 或更高版本、Mac OS X 上的 BBEdit 6.1 或更高版本（以及 Mac OS 8.6 或更高版本上搭配 MacPerl 5.6.1 的 BBEdit 5.1 或更高版本）和 Unix 命令行执行环境。[3] 格鲁伯还致谢了提供语法反馈、测试和 `html2text` 工具的亚伦·斯沃茨，感谢了提供反馈的 Nathaniel Irons、Dan Benjamin、Daniel Bogan 和 Jason Perkins，并提及了 Michel Fortin 开发的 Markdown PHP 移植版。[3]

可读性是 Markdown 的首要设计目标：经过格式化的文档应当可以直接作为纯文本发布，而不显得布满排版指令。[3][4] 尽管格鲁伯指出 Markdown 受到了 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText 等早期纯文本转 HTML 过滤器的影响，但纯文本电子邮件是其最大的灵感来源。[4] 格鲁伯将 HTML 描述为发布格式，而将 Markdown 描述为写作格式，其语法仅覆盖 HTML 标签的一小部分子集。[1][4] 正如 RFC 7764 所记载，格鲁伯是在聚合订阅源（syndicated feeds）遭遇严格 XML 与 XHTML 处理难题后，将 Markdown 设计为一种非正式格式的，并引用了马克·皮尔格林（Mark Pilgrim）的思想实验，即一篇博客文章中无效的 XHTML 可能通过引用通告（trackbacks）破坏其他网站。[2] 在对比波斯特尔法则（Postel's Law）与 XML 1.0 的致命错误要求后，原始 Markdown 摒弃了“无效语法”的概念，且不设管理标准机构。[1][2]

## Markdown 语法与行内 HTML

Markdown 选用在视觉上与其结构作用相似的可打印标点符号，原始语法仅限于可打印的 US-ASCII 字符。[1][4] 该语法将文档划分为块级元素（段落、标题、块引用、列表、代码块以及水平线或主题分隔线）和跨度或行内元素（链接、强调、加粗强调、行内代码、图片、自动链接和反斜杠转义）。[4][6]

| 元素 | 原始 Markdown 语法 | CommonMark 的补充或澄清 |
| --- | --- | --- |
| 段落 | 由空行分隔的一行或多行连续文本；支持硬折行文本 | 相同规则；空行仅包含空格或制表符 |
| 硬换行 | 行尾两个或多个空格后接换行符 | 新增行尾反斜杠写法 |
| 标题 | Setext 风格（用 `=` 下划线表示 H1，`-` 表示 H2）与 ATX 风格（行首 1 至 6 个 `#` 字符） | 标准化空白字符与块级优先级规则 |
| 块引用 | 电子邮件风格的 `>` 前缀；支持惰性折行、嵌套及内嵌块 | 由空行分隔的 `>` 块保持为独立的块引用 |
| 无序列表 | `*`、`+` 或 `-` 后接空白字符 | 更换项目符号字符将开始新列表 |
| 有序列表 | 数字后接 `.`（HTML 输出中忽略源数字） | 允许 `.` 或 `)` 分隔符，保留起始编号，更换分隔符时开始新列表 |
| 代码块 | 缩进行（四个空格或一个制表符） | 新增以反引号或波浪号界定的围栏代码块 |

对于 Markdown 语法未涵盖的标记，作者可以直接在文档中编写原始 HTML，而无需切换定界符。[4] 在原始 Markdown 中，块级 HTML 元素（如 `div`、`table`、`pre` 和 `p`）必须通过空行与周围文本分隔且不能有前导缩进，其内部的 Markdown 语法不会被处理。[4] 行内级 HTML 元素（如 `span`、`cite` 和 `del`）可以出现在段落、列表项或标题中，其内部的 Markdown 语法会被正常处理。[4]

Markdown 还会自动转义小于号和与号字符。[4] 当与号属于现有 HTML 实体（如 `&copy;`）的一部分，或尖括号用于界定 HTML 标签时，Markdown 会将其原样保留；否则，字面量小于号和与号会被转换为 HTML 实体。[4] 在 Markdown 的行内代码和代码块内部，尖括号和与号始终会自动转义。[4]

## Markdown 媒体类型注册（RFC 7763 与 RFC 7764）

2016 年 3 月，互联网工程任务组（IETF）发布 RFC 7763，为 Markdown 内容赋予了官方 MIME 媒体类型 `text/markdown`。[1] RFC 7763 由 Penango, Inc. 的 S. Leonard 撰写，属信息类 RFC，受 `text/troff`（RFC 4263）启发，定义了用于在支持 MIME 的系统中标识编辑中 Markdown 文档的 `text/markdown`。[1] RFC 7763 将分屏实时预览编辑器列为核心用例，并提及了桌面编辑器（MarkdownPad、MultiMarkdown Composer）、浏览器工具（Dillinger、Markable）、集成 Web 组件（Discourse、GitHub）以及通用文本编辑器（emacs、vi、Notepad）之间的互操作性。[1]

根据 RFC 7763，`text/markdown` 媒体类型定义了一个必需参数和一个可选参数。[1] 依据 RFC 6838 第 4.2.1 节，`charset` 参数为必需项且没有默认值，因为原始 Markdown 规则基于字符运行，并不强制指定特定编码。[1] 可选的 `variant` 参数携带不区分大小写的纯 US-ASCII 标识符，用作预期 Markdown 方言的提示；接收方可以应用该变体，也可以忽略该提示，变体名称可注册至 RFC 7763 第 6.1 节建立的 IANA Markdown Variants 注册表。[1]

2016 年 3 月与 RFC 7763 同步发布的配套信息类文档 RFC 7764 同样由 S. Leonard 撰写，记录了 Markdown 的设计理念、本地存储策略与变体注册模板。[2] RFC 7764 概述了六种在本地保留媒体类型和参数元数据的策略（映射到文件名和属性、将头部存入相邻文件、向内容添加 MIME 头部、创建本地批处理脚本、预先处理 Markdown 以及依赖上下文），并给出了 Subversion 和 Git 的具体实践。[2] 该文档还提供了八种常见 Markdown 语法的注册模板：MultiMarkdown、GitHub-Flavored Markdown、Pandoc、Fountain（Fountain.io）、CommonMark、`kramdown-rfc2629`（RFC 专用 Markdown）、`rfc7328`（Pandoc2rfc）以及 PHP Markdown Extra。[2]

RFC 7763 指出，当文本编辑器正确处理控制字符（包括改变文本方向的 Unicode 字符）时，仅以纯文本显示 Markdown 所带来的安全风险有限。[1] 当 Markdown 被转换为 HTML 等目标格式时，它会继承目标格式的安全风险，包括脚本执行、重定向、远程内容下载和个人身份信息传输，并且可能嵌入需要分析与净化的原始正式标记片段。[1]

## 面向 Markdown 的 CommonMark 规范

CommonMark 是一项于 2014 年启动的正式且无歧义的 Markdown 语法规范，旨在解决不同 Markdown 实现之间的解析差异。[5] 格鲁伯的原始语法说明未对多种边界情况作出明确规定，包括子列表缩进、块引用或标题及缩进代码块之前的空行、紧凑列表与宽松列表规则、混合列表标记，以及块级元素与行内元素之间的优先级。[5][6] 早期实现者曾参考 `Markdown.pl`，但该脚本存在缺陷且自 2004 年 12 月 17 日起未再更新。[5] 在随后的十年里，多种编程语言中的数十种实现不断分化，导致同一文档在 GitHub Wiki 与 Pandoc 等系统中呈现不同效果，却不会产生语法错误。[5][6] 早期的 MDTest 测试工具逐渐过时，而 BabelMark 2 与 Babelmark 3 被用来对比 20 多种实现的输出结果。[5][7]

CommonMark 工作由约翰·麦克法兰（John MacFarlane，Pandoc）、David Greenspan（Meteor）、Vicent Marti（GitHub）、Neil Williams（Reddit）、Benjamin Dumke-von der Ehe（Stack Overflow / Stack Exchange）和杰夫·阿特伍德（Jeff Atwood，Discourse）于 2014 年发起。[5][7] 规范由约翰·麦克法兰结合其维护 `pandoc`、`peg-markdown` 和 `lunamark` 的经验执笔，Kārlis Gaņģis 在强调、链接和图片方面作出了贡献。[7] 截至 2026-11-23，`commonmark.org` 列出的现任维护者为约翰·麦克法兰、Martin Woodward（GitHub）和杰夫·阿特伍德。[5]

CommonMark 以 `spec.txt` 形式编写，从人类作者的视角对结构元素进行声明式描述。[7] 任意 Unicode 码位序列均构成有效的 CommonMark 文档，出于安全考虑，`U+0000` 会被替换为 Unicode 替换字符 `U+FFFD`。[6] 在空白字符决定块结构的场景下，制表符按 4 字符制表位处理，内部制表符则保持字面值。[6] CommonMark 定义了两阶段解析模型：第一阶段解析块结构（包括标题、段落、主题分隔线、代码块、HTML 块和链接引用定义等叶块，以及块引用和列表等容器块），第二阶段解析行内结构，且块结构指示符始终优先于行内指示符。[6]

CommonMark 文档记录的相对原始 Markdown 的变更包括：允许对所有 ASCII 标点符号进行反斜杠转义、新增行尾反斜杠硬换行、在行内链接和引用链接中均允许单引号包裹链接标题、修订 HTML 块规则以避免高开销回溯、将空行分隔的 `>` 块保留为独立块引用、在项目符号或有序列表分隔符变更时开启新列表、保留有序列表的起始编号，以及支持使用反引号或波浪号的围栏代码块。[7] 规范仓库（`github.com/commonmark/commonmark-spec`）内置 500 多个 Markdown 与 HTML 对照一致性测试，可通过 `test/spec_tests.py` 运行并经由 `commonmark-spec` npm 包导出为 JSON，同时配套提供基于 BSD 许可证的 C（`cmark`）与 JavaScript（`commonmark.js`）参考实现。[7] 截至 2026-11-23，`commonmark.org` 列出的 CommonMark 采用站点与项目包括 Discourse、GitHub、GitLab、Reddit、Qt、Stack Overflow / Stack Exchange 和 Swift。[5]

## GitHub Flavored Markdown（GFM）

GitHub Flavored Markdown（GFM）是 GitHub.com 和 GitHub Enterprise 上面向用户内容支持的 Markdown 方言。[6] 截至 2026-11-23，正式的 GFM 规范为发布于 2019 年 4 月 6 日的 0.29-gfm 版，基于约翰·麦克法兰的 CommonMark 规范构建。[6] GFM 被定义为 CommonMark 的严格超集，保留了 CommonMark 的两阶段块级与行内解析模型，同时为 GitHub 用户内容规定了相应扩展。[6]

GFM 规范在 CommonMark 之上明确了五项正式扩展：[6]

- 表格（第 4.10 节），新增结构化叶块表格语法
- 任务列表项（第 5.3 节），扩展容器列表项以支持复选框清单
- 删除线（第 6.5 节），新增行内删除文本格式
- 自动链接扩展（第 6.9 节），在基础 CommonMark 自动链接之外扩展自动链接识别
- 禁用原始 HTML（第 6.11 节），在渲染期间过滤特定的原始 HTML 标签

在将 GFM 输入转换为 HTML 后，GitHub.com 和 GitHub Enterprise 会执行额外的后处理与净化，以维护全平台的安全性和显示一致性。[6] GitHub-Flavored Markdown 也被收录在 RFC 7764 所记录的八种变体注册模板之中。[2]

## Markdown 在出版与 llms.txt 中的应用

Markdown 广泛应用于 Reddit、Stack Overflow、GitHub、GitLab 和 Discourse 等主流 Web 平台，在 Web 之外也用于书籍、文章、幻灯片、信件、讲义、学术写作、剧本（通过 Fountain）、数学公式以及 IETF 互联网草案或 RFC（`kramdown-rfc2629` 与 `rfc7328`）。[1][2][5][6]

在 AI 与 Web 文档工作流中，Markdown 是 [llms.txt](https://mimirwiki.com/zh/wiki/llms-txt) 提案所采用的格式，该提案由杰里米·霍华德（Jeremy Howard）于 2024 年 9 月 3 日发布，并于 2026 年 8 月 10 日更新至第 2 版。[8] 由于标准 HTML 页面在核心信息周围夹杂导航、广告和 JavaScript，`llms.txt` 建议在 `/llms.txt` 或 `/docs/llms.txt` 等子路径下放置一份 Markdown 指南文件，为大语言模型（LLM）和 AI 智能体提供精简的背景信息与精选链接。[8] `llms.txt` 文件遵循固定的 Markdown 章节顺序（可选的字节顺序标记、必需的 H1 站点或项目标题、可选的块引用摘要、可选的正文章节以及包含 Markdown 链接列表的 H2 章节），从而既能由语言模型读取，也能被常规解析器或正则表达式处理。[8]

`llms.txt` 提案还建议在相同 URL 后附加 `.md`（`page.html.md`）或替换扩展名（`page.md`）来提供单个页面的简洁 Markdown 版本，目录 URL 则使用 `index.html.md` 或 `index.md`。[8] 为便于自动发现，`llms.txt` v2 建议使用 HTML `link` 元素或 HTTP `Link` 响应头，通过 `rel="alternate"` 搭配 `type="text/markdown"`（即 RFC 7763 媒体类型）指向页面的 Markdown 副本，并通过 `rel="describedby"` 指向涵盖该页面的 `llms.txt` 文件。[1][8] 根据截至 2026 年 8 月的 `llms.txt` v2 文本，已有数千个网站发布了 `llms.txt` 文件，Mintlify 和 GitBook 等文档平台会自动生成该文件，`nbdev` 软件文档项目（包括 Answer.AI、fast.ai 和 FastHTML 文档）默认生成页面的 `.md` 版本，Chrome 的 Lighthouse 在其智能体浏览审计中纳入了 `llms.txt`，[OpenAI](https://mimirwiki.com/zh/wiki/openai)、[Anthropic](https://mimirwiki.com/zh/wiki/anthropic) 和 [Google Gemini](https://mimirwiki.com/zh/wiki/google-gemini) 等 AI 提供商也在 [robots.txt](https://mimirwiki.com/zh/wiki/robots-txt) 和 [站点地图](https://mimirwiki.com/zh/wiki/sitemaps) 等现有 Web 惯例之外，为其开发者文档发布了 `llms.txt` 文件。[8]

## 常见问题

### 什么是 Markdown？

Markdown 是一种轻量级标记语言和纯文本排版语法，旨在保持纯文本状态下的可读性，同时可转换为 HTML 等正式标记语言。其语法使用主要受纯文本电子邮件惯例启发的标点符号，并允许直接嵌入原始 HTML。 [1][3][4]

### Markdown 是谁在何时创建的？

Markdown 于 2004 年由约翰·格鲁伯（John Gruber）开发，亚伦·斯沃茨（Aaron Swartz）作出了重要贡献。格鲁伯于 2004 年 12 月 17 日在类 BSD 开源许可证下发布了原始 Perl 转换器 Markdown.pl 的最后一个更新版本 Markdown 1.0.1。 [2][3][5]

### Markdown 的官方 MIME 媒体类型是什么？

Markdown 的官方 MIME 媒体类型是 text/markdown，由 IETF 于 2016 年 3 月通过信息类文档 RFC 7763 注册。它要求提供无默认值的 charset 参数，并接受可选的不区分大小写的 US-ASCII variant 参数，配套指导文档为 RFC 7764。 [1][2]

### CommonMark 与原始 Markdown 有什么关系？

CommonMark 是一项始于 2014 年的明确 Markdown 语法规范，旨在解决约翰·格鲁伯的原始说明与 Markdown.pl 之后出现的解析歧义和实现差异。它保留了核心 Markdown 元素，同时增加了围栏代码块、行尾反斜杠硬换行语法以及 500 多个一致性测试示例。 [5][7]

### GitHub Flavored Markdown 在 CommonMark 基础上增加了哪些扩展？

GitHub Flavored Markdown（GFM）在 0.29-gfm 版（2019-04-06）中被定义为 CommonMark 的严格超集，增加了五项扩展：表格、任务列表项、删除线、扩展自动链接和禁用原始 HTML。GitHub.com 和 GitHub Enterprise 在将 GFM 转换为 HTML 后还会执行额外的后处理和净化（sanitization）。 [6]

### 面向 AI 智能体的 llms.txt 提案如何使用 Markdown？

llms.txt 提案在 /llms.txt 或 /docs/llms.txt 等子路径下放置具有固定章节顺序的 Markdown 文件，使语言模型和 AI 智能体能够读取站点概览并沿链接访问详细文档。该提案还建议为单个页面提供简洁的 .md 版本，并通过 rel="alternate" 和 type="text/markdown" 链接实现发现。 [8]

## 可引用的句子

- Markdown 于 2004 年由约翰·格鲁伯（John Gruber）开发，亚伦·斯沃茨（Aaron Swartz）作出了重要贡献。 [2][5]
- 约翰·格鲁伯于 2004 年 12 月 17 日在类 BSD 开源许可证下发布了 18 KB 的 Perl 脚本 Markdown 1.0.1。 [3]
- 原始 Markdown 支持行内原始 HTML，在保留 HTML 实体的同时自动转义字面量小于号和与号，其主要语法灵感来源于纯文本电子邮件。 [4]
- 互联网工程任务组（IETF）于 2016 年 3 月发布的 RFC 7763 注册了 text/markdown 媒体类型，包含必需的 charset 参数和可选的 variant 参数。 [1]
- 作为 RFC 7763 的信息类配套文档，RFC 7764 于 2016 年 3 月发布，提供了 MultiMarkdown、GitHub-Flavored Markdown、Pandoc 和 CommonMark 等八种 Markdown 变体的注册模板。 [2]
- CommonMark 规范项目始于 2014 年，提供超过 500 个内置一致性测试示例，以及基于 BSD 许可证的 C（cmark）和 JavaScript（commonmark.js）参考实现。 [5][7]
- 发布于 2019 年 4 月 6 日的 GitHub Flavored Markdown（GFM）0.29-gfm 版是 CommonMark 的严格超集，规定了五项扩展：表格、任务列表项、删除线、扩展自动链接和禁用原始 HTML。 [6]
- 杰里米·霍华德（Jeremy Howard）于 2024 年 9 月 3 日发布并于 2026 年 8 月 10 日更新至 v2 的 llms.txt 提案，面向语言模型和 AI 智能体使用位于 /llms.txt 的 Markdown 文件以及通过 type="text/markdown" 链接关系发现的 .md 页面版本。 [8]

## 时间线

- 2004: 约翰·格鲁伯在亚伦·斯沃茨的重要贡献下开发 Markdown，发布纯文本排版语法与 Perl 转换器 Markdown.pl。 [2][3][5]
- 2004-12-17: 约翰·格鲁伯发布原始 Markdown.pl 脚本的最后一个更新版本 Markdown 1.0.1。 [3][5]
- 2014: 约翰·麦克法兰、David Greenspan、Vicent Marti、Neil Williams、Benjamin Dumke-von der Ehe 和杰夫·阿特伍德启动 CommonMark 规范项目。 [5][7]
- 2016-03: IETF 发布信息类文档 RFC 7763 注册 text/markdown 媒体类型，并同步发布配套指南 RFC 7764。 [1][2]
- 2019-04-06: GitHub 发布基于 CommonMark 的 GitHub Flavored Markdown 规范 0.29-gfm 版。 [6]
- 2024-09-03: 杰里米·霍华德发布 llms.txt 提案，利用 Markdown 文件引导语言模型和 AI 智能体浏览网站。 [8]
- 2026-08-10: llms.txt 提案第 2 版在 llmstxt.org 更新，描述了 Markdown 概览文件、.md 页面版本以及 type="text/markdown" 链接关系发现机制。 [8]

## 来源

1. RFC 7763: The text/markdown Media Type. Internet Engineering Task Force (IETF). 发布于 2016-03. https://www.rfc-editor.org/rfc/rfc7763.txt (访问于 2026-11-23; tier 1: government or public registry)
2. RFC 7764: Guidance on Markdown: Design Philosophies, Stability Strategies, and Select Registrations. Internet Engineering Task Force (IETF). 发布于 2016-03. https://www.rfc-editor.org/rfc/rfc7764.txt (访问于 2026-11-23; tier 1: government or public registry)
3. Daring Fireball: Markdown. Daring Fireball. https://daringfireball.net/projects/markdown/ (访问于 2026-11-23; tier 3: official site)
4. Daring Fireball: Markdown Syntax Documentation. Daring Fireball. https://daringfireball.net/projects/markdown/syntax (访问于 2026-11-23; tier 3: official site)
5. CommonMark. CommonMark. https://commonmark.org/ (访问于 2026-11-23; tier 3: official site)
6. GitHub Flavored Markdown Spec. GitHub. 发布于 2019-04-06. https://github.github.com/gfm/ (访问于 2026-11-23; tier 3: official site)
7. GitHub - commonmark/commonmark-spec: CommonMark spec, with reference implementations in C and JavaScript · GitHub. CommonMark (GitHub). https://github.com/commonmark/commonmark-spec (访问于 2026-11-23; tier 3: official site)
8. The /llms.txt file, v2 – llms-txt. llmstxt.org. 发布于 2024-09-03. https://llmstxt.org/ (访问于 2026-11-23; tier 3: official site)

## 引用本页

Mimirwiki. "Markdown." 版本 80dd4d01, 2026-11-23. https://mimirwiki.com/zh/wiki/markdown
