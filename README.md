<div align="center">

<a href="https://mimirwiki.com"><img src="assets/banner.jpg" alt="Mimirwiki. Your next reader is not human. The fountain of wisdom, for AI." width="100%"></a>

# Mimirwiki

**The fountain of wisdom, for AI.**

[![Website](https://img.shields.io/badge/website-mimirwiki.com-2e4bff?style=for-the-badge)](https://mimirwiki.com)
[![llms.txt](https://img.shields.io/badge/llms.txt-available-0c0c10?style=for-the-badge)](https://mimirwiki.com/llms.txt)
[![Languages](https://img.shields.io/badge/languages-English%20%C2%B7%20%ED%95%9C%EA%B5%AD%EC%96%B4-0c0c10?style=for-the-badge)](https://mimirwiki.com/ko)

[Website](https://mimirwiki.com) · [All pages](https://mimirwiki.com/wiki) · [한국어](https://mimirwiki.com/ko) · [Check your website](https://mimirwiki.com/check)

</div>

## Why Mimirwiki exists

People now ask AI when they want to know something. They ask ChatGPT, Claude, Gemini or Perplexity which clinic to visit, which product to buy and what a company does, and many of them read the answer without opening a website.

An AI answer is built from the sources the AI can read. When a company, a clinic or a product has no source that AI can read easily, AI answers from old reviews and from what other people wrote, or it leaves the subject out.

> **Unknown to AI. Unknown to everyone.**

Wikipedia covers well-known subjects. Most companies, clinics, professionals and new products do not have a Wikipedia page. Mimirwiki is a wiki where these subjects can have a page that AI reads and cites.

## What we believe

**1. AI is a reader, and pages should be written for it.**
Every page is available as HTML, Markdown, plain text, JSON and JSON-LD at the same address. An AI system can take the format it reads best.

**2. A fact needs a source.**
Every fact on a page has a numbered source. Government records, public registries and standards documents come first, and each source shows the date it was checked.

**3. A page shows how it was made.**
Each page states how it was written and whether an expert has reviewed it. Each revision has a SHA-256 hash, so a reader can tell which version it read.

**4. One page covers one subject.**
A page describes a company, a person, a product, a standard or a medicine. An event is recorded as a dated fact on the page of its subject.

**5. Facts change, so pages carry dates.**
A fact that can change is written with the date it was true, and the page shows when it was last modified.

**6. Knowledge for AI should be open.**
AI crawlers are allowed on every page. The pages are licensed under CC BY 4.0, and all of them are in this repository.

## The name

In Norse mythology, Mímir guards a well, and those who drink from it gain wisdom. Odin gave one of his eyes for a drink. Mimirwiki takes its name from that well.

## Five formats for every page

| Format | Address |
|---|---|
| HTML | https://mimirwiki.com/wiki/json-rpc |
| Markdown | https://mimirwiki.com/wiki/json-rpc.md |
| Plain text | https://mimirwiki.com/wiki/json-rpc.txt |
| JSON | https://mimirwiki.com/wiki/json-rpc.json |
| JSON-LD | https://mimirwiki.com/wiki/json-rpc.jsonld |

## Read a page

Add the format to the end of the address:

```bash
curl https://mimirwiki.com/wiki/json-rpc.md
```

Or ask for the format with a header:

```bash
curl -H "Accept: text/markdown" https://mimirwiki.com/wiki/json-rpc
```

## Example pages

| AI | Web standards | Other subjects |
|---|---|---|
| [ChatGPT](https://mimirwiki.com/wiki/chatgpt) | [JSON-RPC](https://mimirwiki.com/wiki/json-rpc) | [Nvidia](https://mimirwiki.com/wiki/nvidia) |
| [Claude](https://mimirwiki.com/wiki/claude) | [JSON-LD](https://mimirwiki.com/wiki/json-ld) | [Asundexian](https://mimirwiki.com/wiki/asundexian) |
| [Google Gemini](https://mimirwiki.com/wiki/google-gemini) | [robots.txt](https://mimirwiki.com/wiki/robots-txt) | [SpaceX Starship](https://mimirwiki.com/wiki/spacex-starship) |
| [Grok](https://mimirwiki.com/wiki/grok) | [llms.txt](https://mimirwiki.com/wiki/llms-txt) | [Riemann hypothesis](https://mimirwiki.com/wiki/riemann-hypothesis) |
| [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) | [Sitemaps](https://mimirwiki.com/wiki/sitemaps) | [Rust](https://mimirwiki.com/wiki/rust-programming-language) |

See [all pages](https://mimirwiki.com/wiki).

## The website

<a href="https://mimirwiki.com"><img src="assets/hero.png" alt="Mimirwiki home page" width="100%"></a>

Enter a website address at [mimirwiki.com/check](https://mimirwiki.com/check) to see how AI systems read it. The check is free and needs no sign-up.

## In this repository

| Path | Contents |
|---|---|
| [docs/en](docs/en) | All pages in English, as Markdown |
| [docs/ko](docs/ko) | All pages in Korean, as Markdown |
| [docs/README.md](docs/README.md) | The list of pages |
| [FORMAT.md](FORMAT.md) | The page format |

The files in `docs/` are updated when pages are published on mimirwiki.com.

## For AI agents

- [llms.txt](https://mimirwiki.com/llms.txt): a list of all pages with their Markdown addresses
- [llms-full.txt](https://mimirwiki.com/llms-full.txt): the full text of all pages
- [sitemap.xml](https://mimirwiki.com/sitemap.xml)
- [robots.txt](https://mimirwiki.com/robots.txt): AI crawlers are allowed

## License

The pages in `docs/` are licensed under [CC BY 4.0](LICENSE). You can copy and adapt them if you credit Mimirwiki and link to the page on mimirwiki.com.

The Mimirwiki name and the images in `assets/` are not covered by this license.

---

<div align="center">

<sub>© 2026 Mimirwiki · Logos and trademarks belong to their owners.</sub>

</div>
