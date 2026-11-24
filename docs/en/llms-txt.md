---
title: "llms.txt"
subtitle: "Proposed Markdown file that guides AI agents to a website's key content"
canonical_url: https://mimirwiki.com/wiki/llms-txt
language: en
page_class: anchor
revision_sha256: 10f01c6750d5a86dc7c0a3fcf532d60176e7297333174d0d37e2ec3a8bef3ea7
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/wiki/llms-txt.md
  txt: https://mimirwiki.com/wiki/llms-txt.txt
  json: https://mimirwiki.com/wiki/llms-txt.json
  jsonld: https://mimirwiki.com/wiki/llms-txt.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/llms-txt
  ja: https://mimirwiki.com/ja/wiki/llms-txt
  zh: https://mimirwiki.com/zh/wiki/llms-txt
---

# llms.txt

> llms.txt is a proposed web convention: a Markdown file, usually at /llms.txt, that gives AI agents a short overview of a website and links to clean Markdown versions of its key pages. Jeremy Howard published the proposal on 2024-09-03 and released version 2 in August 2026. It is a community proposal, and publishing the file is optional.

llms.txt is a proposed web convention in which a site publishes a Markdown file named llms.txt that gives large language models and AI agents a short overview of the site and links to more detailed, LLM-friendly content. Jeremy Howard published the proposal on 2024-09-03 at llmstxt.org and released a second version, v2, in August 2026. The file can sit at the site root (/llms.txt) or at any subpath, and it follows a fixed section order that ordinary parsers can read. llmstxt.org presents llms.txt as a proposal that remains open for community input.

**Also known as:** /llms.txt, The /llms.txt file, llms.txt proposal

## Key facts

- **First published:** 2024-09-03 [1]
- **Current version:** v2 (August 2026) (as of 2026-11-21) [2]
- **Author:** Jeremy Howard [1]
- **Required content:** One H1 heading with the project or site name [1]
- **Location:** /llms.txt at the site root, or any subpath [1]

## Basic facts

- **Type:** Proposed web convention for a Markdown guide file aimed at LLMs and AI agents [1]
- **Author:** Jeremy Howard [1]
- **First published:** 2024-09-03 [1]
- **Current version:** v2 (August 2026) (as of 2026-11-21) [2]
- **File name:** llms.txt [1]
- **Location:** Site root (/llms.txt) or any subpath, for example /docs/llms.txt [1]
- **Format:** Markdown with a fixed section order [1]
- **Required content:** An H1 heading with the project or site name [1]
- **Discovery:** Link relations alternate (type text/markdown) and describedby [1]
- **Status:** Proposal, open for community input [1]
- **Repository:** github.com/AnswerDotAI/llms-txt (Apache-2.0 license) [3]
- **Reference tooling:** llms-txt Python package with the llms_txt2ctx command [4]

## What llms.txt is

llms.txt is a proposal for a [Markdown](https://mimirwiki.com/wiki/markdown) file that a website publishes to give large language models (LLMs) and AI agents a concise guide to its content.[1] The proposal argues that web pages are designed for human readers: navigation, advertising and scripts surround the information on an HTML page, and most websites are too large to fit in a model's context window.[1] An llms.txt file therefore gathers brief background, guidance and links to more detailed Markdown files in one place.[1]

The llms.txt proposal has two parts. The first is the `llms.txt` file itself. The second is a clean Markdown version of each page that an agent might need, served at the same URL as the original page with a `.md` extension.[1] Agents are expected to read or search the llms.txt file, find what they need and then follow the relevant links, so that detail is fetched only on demand.[1]

Jeremy Howard published the llms.txt proposal on 2024-09-03 and released a revised text, labelled v2, in August 2026.[1][2] The proposal is maintained in the AnswerDotAI/llms-txt repository on GitHub under the Apache-2.0 license.[3] According to the proposal, llms.txt files are used most heavily for software documentation.[1]

## llms.txt file format

An llms.txt file is written in Markdown and contains the following parts in a fixed order.[1]

- An optional byte-order mark (BOM)
- An H1 heading with the name of the project or site, which is the only required part
- A blockquote with a short summary of the project
- Zero or more Markdown sections of any type except headings, holding more detailed information
- Zero or more sections introduced by H2 headings, each holding a list of links to further detail

Each entry in an llms.txt link list is a Markdown hyperlink in the form `[name](url)`, optionally followed by a colon and notes about the linked file.[1] A section titled Optional holds secondary links that an agent can skip when a shorter context is needed. In v2 this is a convention only, because the tooling that gave the section a mechanical meaning is no longer part of the proposal.[1][2]

The proposal uses Markdown instead of a structured format such as XML because the files are expected to be read by language models and agents. The fixed layout still allows processing with conventional parsers and regular expressions.[1]

## llms.txt location and discovery

An llms.txt file can be placed at the root path of a website, `/llms.txt`, or at any subpath such as `/docs/llms.txt`. A file covers the URLs under its path, and where more than one file applies, agents are expected to use the most specific one.[1] The first version of the proposal allowed subpaths without defining what they meant, and v2 added this rule.[2]

For individual pages, the llms.txt proposal asks for a Markdown version at the same URL, either with `.md` appended (`page.html.md`) or with the extension replaced (`page.md`). URLs without a file name use `index.html.md` or `index.md`.[1] The first version specified only the appended form.[2]

Version 2 added discovery through standard link relations. A link with `rel="alternate"` and `type="text/markdown"` points to the Markdown version of a page, and `rel="describedby"` points to the llms.txt file that covers it. Both can be given as HTML `link` elements or in an HTTP `Link` header.[1][2] The relation types `alternate` and `describedby` are registered in the IANA Link Relations registry.[9] The proposal does not use the `/.well-known/` path prefix defined by RFC 8615, on the grounds that well-known URIs exist only at the origin root while many authors control only a path on a shared host.[1][8]

## How llms.txt differs from robots.txt and sitemap.xml

llms.txt and [robots.txt](https://mimirwiki.com/wiki/robots-txt) serve different purposes. The Robots Exclusion Protocol, published by the IETF as RFC 9309 in September 2022, lets service owners control how crawlers may access their content.[7] The llms.txt proposal leaves access control to robots.txt and describes its own content as information used on demand, when an agent needs to know about a topic while assisting a user.[1]

llms.txt is also distinct from a [sitemap](https://mimirwiki.com/wiki/sitemaps), which lists all indexable human-readable pages of a site. The proposal gives three reasons why a sitemap is not a substitute: it often does not list LLM-readable versions of pages, it does not include URLs on external sites, and the documents it covers are usually too large in aggregate for a context window.[1] llms.txt is described instead as a curated overview.[1]

The author's stated expectation was that llms.txt would mainly be useful for inference, meaning use at the time a question is answered, and not for model training. The v2 text reports that this is how the file has been used.[1]

## llms.txt adoption and tooling

The v2 text of the llms.txt proposal, written by its author, states that thousands of sites publish an llms.txt file and that OpenAI, Anthropic and Google's Gemini API publish one for their developer documentation.[1] It lists Mintlify, GitBook, Yoast SEO, AIOSEO and Wix among the platforms and plugins that can generate the file automatically.[1]

Mintlify's documentation states that it hosts an llms.txt file at the root of every documentation project and also generates a file named `llms-full.txt`.[10] The name `llms-full.txt` comes from such platforms and does not appear in the llmstxt.org proposal.[1][10] One published example is the [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) documentation site, which serves an index of its pages at `modelcontextprotocol.io/llms.txt`.[11]

The llmstxt.org site documents a Python package, `llms-txt`, with a command-line tool named `llms_txt2ctx` that parses an llms.txt file and builds an XML context file from it.[4] The first version of the proposal described this tool. In v2, context expansion is no longer part of the proposal itself.[2]

## llms.txt status and limits

llms.txt is a proposal. llmstxt.org describes the specification as open for community input and keeps an informal overview of it in a public GitHub repository.[1] Chrome's Lighthouse documentation, last updated 2026-05-05, calls llms.txt an emerging convention. Lighthouse marks its llms.txt audit as not applicable when a site returns a 404 for the file, because providing the file is optional, and flags a page only when a server error occurs during retrieval.[5]

Publishing llms.txt is not a requirement for Google's AI search features. Google's Search Central documentation, last updated 2025-12-10, states that site owners do not need to create new machine-readable files or AI text files to appear in AI Overviews or AI Mode.[6]

llms.txt does not replace other web conventions. It does not set crawler permissions, which remain the role of robots.txt, and it is not an exhaustive page index in the way a sitemap is.[1][7] The proposal notes that an llms.txt file can refer to structured data markup used on a site, to help models interpret that markup in context.[1]

## Frequently asked questions

### What is llms.txt?

llms.txt is a proposed Markdown file that a website publishes to give AI agents a short overview of the site and links to more detailed content. Jeremy Howard published the proposal on 2024-09-03. [1]

### Where is an llms.txt file placed?

At the root path /llms.txt or at any subpath such as /docs/llms.txt. A file covers the URLs under its path, and the most specific file applies when several exist. [1]

### Is llms.txt an official web standard?

llmstxt.org describes llms.txt as a proposal that is open for community input. Chrome's Lighthouse documentation, last updated 2026-05-05, calls it an emerging convention and treats the file as optional. [1][5]

### How does llms.txt differ from robots.txt?

robots.txt, specified in RFC 9309, tells crawlers what access to a site is acceptable. llms.txt does not set permissions. It is a curated overview that an agent reads on demand to find a site's key content. [1][7]

### Does Google require llms.txt for AI Overviews or AI Mode?

No. Google's Search Central documentation, last updated 2025-12-10, says that no new machine-readable files or AI text files are needed to appear in these features. [6]

### What changed in llms.txt v2?

Version 2, published in August 2026, added discovery through the alternate and describedby link relations, allowed two URL forms for Markdown page versions, defined what a file in a subpath covers, and removed context-expansion tooling from the proposal. [2]

## Quotable sentences

- The llms.txt proposal was published by Jeremy Howard on 2024-09-03. [1]
- Version 2 of the llms.txt proposal was published in August 2026. [2]
- The only required part of an llms.txt file is an H1 heading with the name of the project or site. [1]
- An llms.txt file can be placed at a website's root or at any subpath, and it covers the URLs under its path. [1]
- Version 2 of the llms.txt proposal recommends the link relations alternate, with type text/markdown, and describedby for discovery. [1]
- Chrome's Lighthouse documentation, last updated 2026-05-05, describes providing an llms.txt file as optional. [5]
- Google's Search Central documentation states that no new machine-readable files or AI text files are needed to appear in AI Overviews or AI Mode. [6]
- The llms.txt proposal is maintained in the AnswerDotAI/llms-txt repository on GitHub under the Apache-2.0 license. [3]

## Timeline

- 2024-09-03: Jeremy Howard publishes the llms.txt proposal. [1]
- 2026-08: Version 2 of the llms.txt proposal is published. [2]

## Sources

1. The /llms.txt file, v2 – llms-txt. llmstxt.org. published 2024-09-03. https://llmstxt.org/ (checked 2026-11-21; tier 3: official site)
2. Changes – llms-txt. llmstxt.org. published 2026-08. https://llmstxt.org/changes.html (checked 2026-11-21; tier 3: official site)
3. GitHub - AnswerDotAI/llms-txt: The /llms.txt file, helping language models use your website. AnswerDotAI (GitHub). https://github.com/AnswerDotAI/llms-txt (checked 2026-11-21; tier 3: official site)
4. Python module & CLI – llms-txt. llmstxt.org. https://llmstxt.org/intro.html (checked 2026-11-21; tier 3: official site)
5. llms.txt | Lighthouse | Chrome for Developers. Google (Chrome for Developers). published 2026-05-05. https://developer.chrome.com/docs/lighthouse/agentic-browsing/llms-txt (checked 2026-11-21; tier 3: official site)
6. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. published 2025-12-10. https://developers.google.com/search/docs/appearance/ai-features (checked 2026-11-21; tier 3: official site)
7. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (checked 2026-11-21; tier 1: government or public registry)
8. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). published 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (checked 2026-11-21; tier 1: government or public registry)
9. Link Relations. Internet Assigned Numbers Authority (IANA). published 2026-06-12. https://www.iana.org/assignments/link-relations/link-relations.xhtml (checked 2026-11-21; tier 1: government or public registry)
10. llms.txt - Mintlify. Mintlify. https://www.mintlify.com/docs/ai/llmstxt (checked 2026-11-21; tier 3: official site)
11. Model Context Protocol (llms.txt documentation index). Model Context Protocol project. https://modelcontextprotocol.io/llms.txt (checked 2026-11-21; tier 3: official site)

## Cite this page

Mimirwiki. "llms.txt." Version 10f01c67, 2026-11-21. https://mimirwiki.com/wiki/llms-txt
