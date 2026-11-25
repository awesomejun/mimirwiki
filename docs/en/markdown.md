---
title: "Markdown"
subtitle: "Lightweight plain-text markup language, text/markdown media type, and standardized specifications including CommonMark and GFM"
canonical_url: https://mimirwiki.com/wiki/markdown
language: en
page_class: anchor
revision_sha256: d047fc09bc881f6bb0bb6b39e8955bb8b655487288ba59afd46b2eac770ff17f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/wiki/markdown.md
  txt: https://mimirwiki.com/wiki/markdown.txt
  json: https://mimirwiki.com/wiki/markdown.json
  jsonld: https://mimirwiki.com/wiki/markdown.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/markdown
  ja: https://mimirwiki.com/ja/wiki/markdown
  zh: https://mimirwiki.com/zh/wiki/markdown
  es: https://mimirwiki.com/es/wiki/markdown
---

# Markdown

> Markdown is a lightweight markup language created in 2004 by John Gruber with contributions from Aaron Swartz to write readable plain text that converts to HTML. Its variants include CommonMark and GitHub Flavored Markdown. The IETF registered the text/markdown media type in RFC 7763 in March 2016, and proposals such as llms.txt use Markdown for AI agents.

Markdown is a lightweight markup language and family of plain-text formatting syntaxes that convert readable text into formal markup languages such as HTML. John Gruber developed Markdown in 2004 with substantial contributions from Aaron Swartz, releasing both a syntax description and a Perl converter named Markdown.pl under a BSD-style open source license. Because the original description left syntactic ambiguities and implementations diverged, the CommonMark specification launched in 2014 to define unambiguous parsing rules, followed by the Internet Engineering Task Force (IETF) registration of the text/markdown media type in RFC 7763 and companion guidance in RFC 7764 in March 2016. Dialects such as GitHub Flavored Markdown (GFM) extend CommonMark with features including tables and task lists, while web conventions such as llms.txt use Markdown to provide structured documentation to large language models and AI agents.

**Also known as:** text/markdown, CommonMark, GFM, GitHub Flavored Markdown

## Key facts

- **Creator:** John Gruber (with contributions from Aaron Swartz) [2]
- **Initial release:** 2004 (Markdown 1.0.1 released 2004-12-17) [3]
- **MIME media type:** text/markdown (RFC 7763, March 2016) [1]
- **Formal core specification:** CommonMark (launched 2014) [5]
- **Major extended dialect:** GitHub Flavored Markdown (GFM), Version 0.29-gfm (2019-04-06) (as of 2026-11-23) [6]

## Basic facts

- **Type:** Lightweight markup language and plain-text formatting syntax [1]
- **Creator:** John Gruber (with substantial contributions from Aaron Swartz) [2]
- **Initial release:** 2004 [2]
- **Original converter:** Markdown.pl 1.0.1 (Perl, 18 KB, 2004-12-17, BSD-style open source license) [3]
- **MIME media type:** text/markdown (required parameter: charset; optional parameter: variant) [1]
- **IETF documents:** RFC 7763 and RFC 7764 (Informational, March 2016, author S. Leonard) [2]
- **Core specification:** CommonMark (launched 2014, written by John MacFarlane) [7]
- **Reference implementations:** cmark (C) and commonmark.js (JavaScript), BSD-licensed [7]
- **CommonMark maintainers:** John MacFarlane, Martin Woodward, Jeff Atwood (as of 2026-11-23) [5]
- **GFM specification:** Version 0.29-gfm (2019-04-06), strict superset of CommonMark (as of 2026-11-23) [6]
- **AI web convention:** Used by the llms.txt proposal (/llms.txt and .md page versions) [8]

## Markdown origins and design philosophy

Markdown was developed in 2004 by John Gruber with substantial contributions from Aaron Swartz.[2][5] Gruber defined Markdown as two things: a plain-text formatting syntax and a Perl software tool (`Markdown.pl`) that converts plain-text formatting into structurally valid HTML.[3] Released as free software under a BSD-style open source license, Markdown 1.0.1 (18 KB) was published on December 17, 2004, which was also the final update to `Markdown.pl`.[3][5]

`Markdown.pl` required Perl 5.6.0 or later and the standard `Digest::MD5` module.[3] By default it produced XHTML-style tags for empty elements, and authors could configure HTML 4 output with the `--html4tags` command-line option or the `MTMarkdownOptions` container tag in Movable Type.[3] Early supported environments documented by Gruber included Movable Type 2.6 or later (with optional SmartyPants 1.5 or later integration for typographic quotes, dashes, and ellipses), Blosxom 2.0 or later, BBEdit 6.1 or later on Mac OS X (and BBEdit 5.1 or later with MacPerl 5.6.1 on Mac OS 8.6 or later), and Unix command-line execution.[3] Gruber also credited Aaron Swartz for syntax feedback, testing, and the `html2text` utility, acknowledged Nathaniel Irons, Dan Benjamin, Daniel Bogan, and Jason Perkins for feedback, and noted Michel Fortin's PHP port of Markdown.[3]

Readability is the primary design goal of Markdown: a formatted document should be publishable directly as plain text without appearing marked up with formatting instructions.[3][4] While Gruber noted influences from earlier text-to-HTML filters including Setext, atx, Textile, reStructuredText, Grutatext, and EtText, plain-text email served as the largest source of inspiration.[4] Gruber described HTML as a publishing format and Markdown as a writing format whose syntax covers a small subset of HTML tags.[1][4] As documented in RFC 7764, Gruber designed Markdown as an informal format following difficulties with strict XML and XHTML processing in syndicated feeds, referencing Mark Pilgrim's thought experiment in which invalid XHTML in one blog post disrupted other websites via trackbacks.[2] Comparing Postel's Law with the XML 1.0 fatal-error requirement, original Markdown rejects the concept of invalid syntax and operates without a governing standards body.[1][2]

## Markdown syntax and inline HTML

Markdown uses printable punctuation characters chosen to resemble their structural roles, limited to printable US-ASCII characters in the original syntax.[1][4] The syntax separates documents into block elements (paragraphs, headings, blockquotes, lists, code blocks, and horizontal rules or thematic breaks) and span or inline elements (links, emphasis, strong emphasis, code spans, images, automatic links, and backslash escapes).[4][6]

| Element | Original Markdown syntax | CommonMark additions or clarifications |
| --- | --- | --- |
| Paragraphs | One or more consecutive lines separated by blank lines; supports hard-wrapped text | Same rule; blank lines contain only spaces or tabs |
| Hard line breaks | Two or more trailing spaces followed by a line break | Adds a trailing backslash at the end of a line |
| Headings | Setext style (underlining with `=` for H1 or `-` for H2) and ATX style (1 to 6 `#` characters at line start) | Standardized whitespace and block precedence rules |
| Blockquotes | Email-style `>` prefix; supports lazy wrapping, nesting, and embedded blocks | Blank-line-separated `>` blocks remain separate blockquotes |
| Unordered lists | `*`, `+`, or `-` followed by whitespace | Changing the bullet character starts a new list |
| Ordered lists | Numbers followed by `.` (source numbers ignored in HTML output) | Permits `.` or `)` delimiters, preserves start numbers, and starts a new list on delimiter changes |
| Code blocks | Indented lines (four spaces or a tab) | Adds fenced code blocks delimited by backticks or tildes |

For markup outside Markdown's syntax, authors can write raw HTML directly in the document without switching delimiters.[4] In original Markdown, block-level HTML elements (such as `div`, `table`, `pre`, and `p`) must be separated from surrounding text by blank lines without leading indentation, and Markdown syntax inside them is left unprocessed.[4] Span-level HTML elements (such as `span`, `cite`, and `del`) may appear inside paragraphs, list items, or headings, and Markdown syntax inside span-level elements is processed.[4]

Markdown also performs automatic escaping for the less-than sign and ampersand characters.[4] When an ampersand forms part of an existing HTML entity such as `&copy;`, or when angle brackets delimit an HTML tag, Markdown preserves them; otherwise literal less-than signs and ampersands are converted into HTML entities.[4] Inside Markdown code spans and code blocks, angle brackets and ampersands are always escaped automatically.[4]

## Markdown media type registration (RFC 7763 and RFC 7764)

Markdown content received an official MIME media type, `text/markdown`, when the Internet Engineering Task Force (IETF) published RFC 7763 in March 2016.[1] Authored by S. Leonard of Penango, Inc. as an Informational RFC, RFC 7763 defines `text/markdown` for labeling Markdown works in progress across MIME-capable systems, drawing inspiration from `text/troff` (RFC 4263).[1] RFC 7763 describes split-screen live-preview editors as a central use case and cites interoperability across desktop editors (MarkdownPad, MultiMarkdown Composer), browser tools (Dillinger, Markable), integrated web widgets (Discourse, GitHub), and general-purpose text editors (emacs, vi, Notepad).[1]

Under RFC 7763, the `text/markdown` media type defines one required parameter and one optional parameter.[1] The `charset` parameter is required under Section 4.2.1 of RFC 6838 and has no default value, because original Markdown rules operate on characters and do not mandate a specific encoding.[1] The optional `variant` parameter carries a plain US-ASCII, case-insensitive identifier acting as a hint for the intended Markdown dialect; recipients may apply that variant or ignore the hint, and variant names can be registered in the IANA Markdown Variants registry established by Section 6.1 of RFC 7763.[1]

The companion Informational document RFC 7764, published alongside RFC 7763 in March 2016 by S. Leonard, documents Markdown's design philosophy, local storage strategies, and variant registration templates.[2] RFC 7764 outlines six strategies for preserving media type and parameter metadata locally (mapping to filenames and attributes, storing headers in adjacent files, adding MIME headers to content, creating local batch scripts, pre-processing Markdown in advance, and relying on context), along with specific practices for Subversion and Git.[2] It also provides registration templates for eight common Markdown syntaxes: MultiMarkdown, GitHub-Flavored Markdown, Pandoc, Fountain (Fountain.io), CommonMark, `kramdown-rfc2629` (Markdown for RFCs), `rfc7328` (Pandoc2rfc), and PHP Markdown Extra.[2]

RFC 7763 notes that Markdown displayed solely as plain text carries limited security risk when text editors handle control characters properly, including Unicode characters that alter text directionality.[1] When Markdown is converted to target formats such as HTML, it inherits the security considerations of the target format, including script execution, redirection, remote content downloads, and transmission of personally identifiable information, and may embed islands of raw formal markup that require analysis and sanitization.[1]

## CommonMark specification for Markdown

CommonMark is a formal, unambiguous specification of Markdown syntax launched in 2014 to address parsing divergences across Markdown implementations.[5] Gruber's original syntax description left edge cases unspecified, including sublist indentation, blank lines before blockquotes, headings, or indented code blocks, tight versus loose list rules, mixed list markers, and precedence between block and inline elements.[5][6] Early implementers consulted `Markdown.pl`, which contained bugs and had not been updated since December 17, 2004.[5] Over the following decade, dozens of implementations in multiple programming languages diverged, causing identical documents to render differently across systems such as GitHub wikis and Pandoc without producing syntax errors.[5][6] Earlier testing via MDTest became obsolete, while BabelMark 2 and Babelmark 3 compared outputs across more than 20 implementations.[5][7]

The CommonMark effort was started in 2014 by John MacFarlane (Pandoc), David Greenspan (Meteor), Vicent Marti (GitHub), Neil Williams (Reddit), Benjamin Dumke-von der Ehe (Stack Overflow / Stack Exchange), and Jeff Atwood (Discourse).[5][7] John MacFarlane wrote the specification, drawing on his experience maintaining `pandoc`, `peg-markdown`, and `lunamark`, with contributions from Kārlis Gaņģis on emphasis, links, and images.[7] As of 2026-11-23, `commonmark.org` lists John MacFarlane, Martin Woodward (GitHub), and Jeff Atwood as current maintainers.[5]

CommonMark is written in `spec.txt` as a declarative description of structural elements from the human writer's perspective.[7] Every sequence of Unicode code points constitutes a valid CommonMark document, with `U+0000` replaced by the Unicode replacement character `U+FFFD` for security.[6] Where whitespace defines block structure, tabs behave as 4-character tab stops, while internal tabs remain literal.[6] CommonMark defines a two-phase parsing model in which Phase 1 resolves block structure (leaf blocks such as headings, paragraphs, thematic breaks, code blocks, HTML blocks, and link reference definitions, plus container blocks such as blockquotes and lists) and Phase 2 resolves inline structure, with block structure indicators always taking precedence over inline indicators.[6]

Documented departures from original Markdown in CommonMark include allowing backslash escapes for all ASCII punctuation symbols, adding a trailing backslash for hard line breaks, permitting single-quoted link titles in both inline and reference links, revising HTML block rules to avoid expensive backtracking, keeping blank-line-separated `>` blocks as distinct blockquotes, starting a new list when bullet markers or ordered delimiters change, preserving ordered list start numbers, and supporting fenced code blocks with backticks or tildes.[7] The specification repository (`github.com/commonmark/commonmark-spec`) embeds over 500 side-by-side Markdown and HTML conformance tests runnable via `test/spec_tests.py` and exported as JSON through the `commonmark-spec` npm package, alongside BSD-licensed reference implementations in C (`cmark`) and JavaScript (`commonmark.js`).[7] As of 2026-11-23, `commonmark.org` lists Discourse, GitHub, GitLab, Reddit, Qt, Stack Overflow / Stack Exchange, and Swift among sites and projects that have adopted CommonMark.[5]

## GitHub Flavored Markdown (GFM)

GitHub Flavored Markdown (GFM) is the dialect of Markdown supported for user content on GitHub.com and GitHub Enterprise.[6] As of 2026-11-23, the formal GFM specification is Version 0.29-gfm, dated April 6, 2019, based on John MacFarlane's CommonMark specification.[6] GFM is defined as a strict superset of CommonMark, retaining CommonMark's two-phase block-and-inline parsing model while specifying extensions for GitHub user content.[6]

The GFM specification identifies five formal extensions beyond CommonMark:[6]

- Tables (Section 4.10), adding structured leaf-block table syntax
- Task list items (Section 5.3), extending container list items for checklists
- Strikethrough (Section 6.5), adding inline deleted-text formatting
- Autolinks extension (Section 6.9), expanding automatic link recognition beyond base CommonMark autolinks
- Disallowed Raw HTML (Section 6.11), filtering specific raw HTML tags during rendering

After GFM input is converted to HTML, GitHub.com and GitHub Enterprise perform additional post-processing and sanitization to maintain security and consistent display across the platform.[6] GitHub-Flavored Markdown is also included among the eight variant registration templates documented in RFC 7764.[2]

## Markdown usage in publishing and llms.txt

Markdown is used on major web platforms including Reddit, Stack Overflow, GitHub, GitLab, and Discourse, as well as outside the web for books, articles, slide shows, letters, lecture notes, scholarly writing, screenplays (via Fountain), mathematical formulae, and IETF Internet-Drafts or RFCs (`kramdown-rfc2629` and `rfc7328`).[1][2][5][6]

In AI and web documentation workflows, Markdown forms the format for the [llms.txt](https://mimirwiki.com/wiki/llms-txt) proposal, published by Jeremy Howard on September 3, 2024 and updated to version 2 on August 10, 2026.[8] Because standard HTML pages surround core information with navigation, advertising, and JavaScript, `llms.txt` proposes placing a Markdown guide file at `/llms.txt` or a subpath such as `/docs/llms.txt` to give large language models (LLMs) and AI agents concise background information and curated links.[8] An `llms.txt` file follows a fixed Markdown section order (an optional byte-order mark, a required H1 site or project title, an optional blockquote summary, optional body sections, and H2 sections containing Markdown link lists), allowing both language models and conventional parsers or regular expressions to process it.[8]

The `llms.txt` proposal also recommends serving clean Markdown versions of individual pages at the same URL with `.md` appended (`page.html.md`) or replacing the extension (`page.md`), or using `index.html.md` or `index.md` for directory URLs.[8] To aid automated discovery, `llms.txt` v2 recommends HTML `link` elements or HTTP `Link` response headers using `rel="alternate"` with `type="text/markdown"` (the RFC 7763 media type) for page Markdown copies and `rel="describedby"` for the covering `llms.txt` file.[1][8] According to the `llms.txt` v2 text as of August 2026, thousands of websites publish `llms.txt` files, documentation platforms including Mintlify and GitBook generate them automatically, `nbdev` software documentation projects produce `.md` versions of pages by default (including Answer.AI, fast.ai, and FastHTML docs), Chrome's Lighthouse includes `llms.txt` in its agentic browsing audits, and AI providers including [OpenAI](https://mimirwiki.com/wiki/openai), [Anthropic](https://mimirwiki.com/wiki/anthropic), and [Google Gemini](https://mimirwiki.com/wiki/google-gemini) publish `llms.txt` files for their developer documentation alongside existing web conventions such as [robots.txt](https://mimirwiki.com/wiki/robots-txt) and [sitemaps](https://mimirwiki.com/wiki/sitemaps).[8]

## Frequently asked questions

### What is Markdown?

Markdown is a lightweight markup language and plain-text formatting syntax designed to remain readable as plain text while converting to formal markup languages such as HTML. Its syntax uses punctuation characters inspired primarily by plain-text email conventions and allows raw HTML inline. [1][3][4]

### Who created Markdown and when was it released?

John Gruber developed Markdown in 2004 with substantial contributions from Aaron Swartz. Gruber released Markdown 1.0.1, the final update to the original Perl converter Markdown.pl, on December 17, 2004 under a BSD-style open source license. [2][3][5]

### What is the official MIME media type for Markdown?

The official MIME media type for Markdown is text/markdown, registered by the IETF in March 2016 through Informational RFC 7763. It requires a charset parameter with no default value and accepts an optional case-insensitive US-ASCII variant parameter, with companion guidance provided in RFC 7764. [1][2]

### How does CommonMark relate to original Markdown?

CommonMark is an unambiguous specification of Markdown syntax launched in 2014 to resolve parsing ambiguities and implementation divergences that arose after John Gruber's original description and Markdown.pl. It preserves core Markdown elements while adding fenced code blocks, a trailing-backslash hard line break syntax, and over 500 conformance test examples. [5][7]

### What extensions does GitHub Flavored Markdown add to CommonMark?

GitHub Flavored Markdown (GFM), specified in Version 0.29-gfm (2019-04-06) as a strict superset of CommonMark, adds five extensions: tables, task list items, strikethrough, extended autolinks, and disallowed raw HTML. GitHub.com and GitHub Enterprise also apply post-processing and sanitization after converting GFM to HTML. [6]

### How is Markdown used in the llms.txt proposal for AI agents?

The llms.txt proposal uses a Markdown file placed at /llms.txt or a subpath such as /docs/llms.txt with a fixed section order so language models and AI agents can read a site overview and follow links to detailed documentation. It also proposes serving clean Markdown versions of individual pages with .md URLs discovered through rel="alternate" and type="text/markdown" links. [8]

## Quotable sentences

- Markdown was developed in 2004 by John Gruber with substantial contributions from Aaron Swartz. [2][5]
- John Gruber released Markdown 1.0.1 as an 18 KB Perl script under a BSD-style open source license on December 17, 2004. [3]
- Original Markdown supports inline raw HTML, automatically escapes literal less-than signs and ampersands while preserving HTML entities, and draws its primary syntax inspiration from plain-text email. [4]
- RFC 7763, published by the Internet Engineering Task Force in March 2016, registers the text/markdown media type with a required charset parameter and an optional variant parameter. [1]
- RFC 7764, published in March 2016 as an informational companion to RFC 7763, supplies registration templates for eight Markdown variants including MultiMarkdown, GitHub-Flavored Markdown, Pandoc, and CommonMark. [2]
- The CommonMark specification effort started in 2014 and provides over 500 embedded conformance test examples along with BSD-licensed reference implementations in C (cmark) and JavaScript (commonmark.js). [5][7]
- GitHub Flavored Markdown (GFM) Version 0.29-gfm, dated April 6, 2019, is a strict superset of CommonMark that specifies five extensions: tables, task list items, strikethrough, extended autolinks, and disallowed raw HTML. [6]
- The llms.txt proposal, published by Jeremy Howard on September 3, 2024 and updated to v2 on August 10, 2026, uses Markdown files at /llms.txt and .md page versions discovered via type="text/markdown" link relations for language models and AI agents. [8]

## Timeline

- 2004: John Gruber develops Markdown with substantial contributions from Aaron Swartz, publishing a plain-text formatting syntax and the Perl converter Markdown.pl. [2][3][5]
- 2004-12-17: John Gruber releases Markdown 1.0.1, the final update to the original Markdown.pl script. [3][5]
- 2014: John MacFarlane, David Greenspan, Vicent Marti, Neil Williams, Benjamin Dumke-von der Ehe, and Jeff Atwood launch the CommonMark specification effort. [5][7]
- 2016-03: The IETF publishes Informational RFC 7763, registering the text/markdown media type, alongside companion guidance in RFC 7764. [1][2]
- 2019-04-06: GitHub publishes Version 0.29-gfm of the GitHub Flavored Markdown specification based on CommonMark. [6]
- 2024-09-03: Jeremy Howard publishes the llms.txt proposal using Markdown files to guide language models and AI agents through websites. [8]
- 2026-08-10: Version 2 of the llms.txt proposal is updated at llmstxt.org, describing Markdown overview files, .md page versions, and type="text/markdown" link-relation discovery. [8]

## Sources

1. RFC 7763: The text/markdown Media Type. Internet Engineering Task Force (IETF). published 2016-03. https://www.rfc-editor.org/rfc/rfc7763.txt (checked 2026-11-23; tier 1: government or public registry)
2. RFC 7764: Guidance on Markdown: Design Philosophies, Stability Strategies, and Select Registrations. Internet Engineering Task Force (IETF). published 2016-03. https://www.rfc-editor.org/rfc/rfc7764.txt (checked 2026-11-23; tier 1: government or public registry)
3. Daring Fireball: Markdown. Daring Fireball. https://daringfireball.net/projects/markdown/ (checked 2026-11-23; tier 3: official site)
4. Daring Fireball: Markdown Syntax Documentation. Daring Fireball. https://daringfireball.net/projects/markdown/syntax (checked 2026-11-23; tier 3: official site)
5. CommonMark. CommonMark. https://commonmark.org/ (checked 2026-11-23; tier 3: official site)
6. GitHub Flavored Markdown Spec. GitHub. published 2019-04-06. https://github.github.com/gfm/ (checked 2026-11-23; tier 3: official site)
7. GitHub - commonmark/commonmark-spec: CommonMark spec, with reference implementations in C and JavaScript · GitHub. CommonMark (GitHub). https://github.com/commonmark/commonmark-spec (checked 2026-11-23; tier 3: official site)
8. The /llms.txt file, v2 – llms-txt. llmstxt.org. published 2024-09-03. https://llmstxt.org/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Markdown." Version d047fc09, 2026-11-23. https://mimirwiki.com/wiki/markdown
