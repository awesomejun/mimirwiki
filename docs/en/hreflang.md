---
title: "hreflang"
subtitle: "HTML attribute and link parameter specifying the language and target region of linked web resources"
canonical_url: https://mimirwiki.com/wiki/hreflang
language: en
page_class: anchor
revision_sha256: acccab62ba979d67ffcdb99a13f735f57a3e0ca3249828271c46167d34f3edca
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/hreflang.md
  txt: https://mimirwiki.com/wiki/hreflang.txt
  json: https://mimirwiki.com/wiki/hreflang.json
  jsonld: https://mimirwiki.com/wiki/hreflang.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/hreflang
---

# hreflang

> hreflang is an HTML attribute and link parameter that identifies the language, and optionally the region, of a linked resource using BCP 47 tags from RFC 5646. Websites publish hreflang annotations through HTML link elements, HTTP Link headers, or XML sitemaps so Google Search can direct users to the matching localized version of a page.

hreflang is an HTML attribute and link annotation parameter that indicates the human language, and optionally the target region, of a linked web resource. Defined as a reflected attribute in the WHATWG HTML Living Standard and paired with BCP 47 language tags specified by IETF RFC 5646, hreflang carries no built-in browser behavior on anchor elements and serves as metadata for external link processors. In Google Search, sites publish hreflang annotations with the alternate link relation through HTML link elements, HTTP Link headers defined by RFC 8288, or XML sitemaps to connect localized versions of a page. Google requires reciprocal links across listed variants and supports the x-default value for fallback pages when no listed language or region matches.

**Also known as:** hreflang attribute, hreflang tag, hreflang annotation, rel=alternate hreflang

## Key facts

- **HTML specification:** WHATWG HTML Living Standard (updated 2026-11-22) (as of 2026-11-23) [1]
- **Language tag standard:** IETF BCP 47 / RFC 5646 (September 2009) [2]
- **Subtag registry:** IANA Language Subtag Registry (file date 2026-11-18) (as of 2026-11-23) [4]
- **HTTP header specification:** IETF RFC 8288 (Web Linking, October 2017) [3]
- **Google delivery methods:** HTML link elements, HTTP Link headers, and XML sitemaps (as of 2026-11-23) [6]

## Basic facts

- **Type:** HTML attribute hinting at the human language of a linked URL [9]
- **HTML specification:** WHATWG HTML Living Standard, Section 4.6 (updated 2026-11-22) (as of 2026-11-23) [1]
- **DOM API:** HyperlinkElementUtils.hreflang (reflected DOMString) [1]
- **Language tag syntax:** IETF BCP 47 (RFC 5646, September 2009; obsoletes RFC 4646) [2]
- **Subtag registry:** IANA Language Subtag Registry (file date 2026-11-18) (as of 2026-11-23) [4]
- **HTTP header specification:** IETF RFC 8288 (Web Linking, October 2017; obsoletes RFC 5988) [3]
- **HTML link baseline:** HTML link element widely available across browsers since July 2015 [8]
- **Google delivery methods:** HTML link elements, HTTP Link headers, and XML sitemaps (as of 2026-11-23) [6]
- **Fallback value:** x-default (announced by Google Search Central Blog in April 2013) [10]
- **Confirmation rule:** Self-referencing and bidirectional links required in Google Search (as of 2026-11-23) [6]

## What hreflang is

hreflang is an HTML attribute and link annotation parameter that indicates the human language, and optionally the target region, of a linked web resource.[6][9] In HTML, links are conceptual connections between two resources created by `a`, `area`, `form`, and `link` elements, grouped into links to external resources, hyperlinks, and internal resource links.[1]

In the WHATWG HTML Living Standard (last updated 2026-11-22), Section 4.6.3 defines `hreflang` on the `HyperlinkElementUtils` interface mixin as a reflected `DOMString` attribute.[1] MDN Web Docs documents both the HTML `link` element (which specifies relationships between the current document and an external resource) and the HTML `a` anchor element (which creates hyperlinks), recording both elements as widely available across browsers since July 2015.[8][9] On the `a` element, MDN notes that `hreflang` hints at the human language of the linked URL, carries no built-in browser functionality, and accepts the same language tag values as the global `lang` attribute.[9]

In Google Search, websites pair `hreflang` with the `alternate` link relation to declare localized versions of a page across languages or regions so that search results point users to the version matching their language or region.[6]

## BCP 47 and RFC 5646 language tags used in hreflang

hreflang values use BCP 47 language tags specified by IETF RFC 5646 ("Tags for Identifying Languages"), published in September 2009.[2][5][9] Edited by A. Phillips and M. Davis, RFC 5646 obsoleted RFC 4646 (which replaced RFC 3066 and RFC 1766) and combines with RFC 4647 to comprise BCP 47.[2][5]

A BCP 47 language tag consists of one or more alphanumeric subtags separated by hyphens (`-`, U+002D), ordered as `language-extlang-script-region-variant-extension-privateuse`.[2][5] Each subtag type is distinguished by length, position, and character content, enabling processors to identify subtag categories without a local registry copy, except for a fixed set of grandfathered tags registered during the RFC 3066 era.[2]

| Subtag type | Format | Source standard | Examples |
| --- | --- | --- | --- |
| Primary language | 2 to 3 letters (or 5 to 8 registered letters) | ISO 639 | `en`, `es`, `ast`, `mas` |
| Extended language | 3 letters after a macrolanguage subtag | ISO 639 | `zh-yue`, `ar-afb` |
| Script | 4 letters (introduced in RFC 4646) | ISO 15924 | `zh-Hans`, `az-Latn` |
| Region | 2 letters or 3 digits | ISO 3166-1 / UN M.49 | `fr-CA`, `en-GB`, `de-CH`, `es-419` |
| Variant | 5 to 8 alphanumerics, or 1 digit plus 3 alphanumerics | IANA registry | Registered dialect or orthography subtags |
| Extension and private use | Single alphanumeric singleton (`x` reserved for private use) | RFC 5646 | Single-character extensions; `x-` private-use tags |

All valid subtags are maintained in a single plain-text file, the IANA Language Subtag Registry, which had a file date of 2026-11-18 as of 2026-11-23.[4][5] The registry adopts one ISO 639 value per language (selecting a two-letter code when available and otherwise one three-letter code) and added over 7,000 ISO 639-3 three-letter codes upon the publication of RFC 5646.[5] Registry records contain fields such as `Type`, `Subtag`, `Description`, `Added`, `Suppress-Script`, `Scope`, `Deprecated`, and `Preferred-Value`.[4][5] For example, the `bh` (Bihari languages) entry carries a deprecation date of 2026-06-14 with `Preferred-Value: bih`.[4]

W3C states that language tags are case-insensitive in HTML and XML; writing language subtags in lowercase, script subtags with an initial capital, and alphabetic region subtags in uppercase is a convention only.[5] W3C advises keeping language tags as short as possible, omitting region or script subtags when they add no useful distinction, and following `Suppress-Script` entries such as `Latn` for `en`, `es`, and `fr`.[4][5] For legacy language-plus-extlang combinations such as `zh-yue` or `ar-afb`, W3C notes that an equivalent standalone primary language subtag (`yue` or `afb`) exists and advises using the standalone subtag when possible.[5]

## Implementation methods for hreflang annotations

Google Search Central documentation, as of 2026-11-23, specifies three equivalent methods for delivering hreflang annotations: HTML `link` elements, HTTP `Link` headers, and [XML sitemaps](https://mimirwiki.com/wiki/sitemaps).[6] Google treats all three methods equally, and using more than one method on the same pages increases maintenance work without providing an additional benefit in Search.[6]

| Method | Placement and syntax | Typical use case |
| --- | --- | --- |
| HTML `link` elements | `link` elements in `head` with `rel="alternate"`, `hreflang`, and `href` | HTML pages without sitemap or HTTP header control |
| HTTP `Link` headers | Comma-separated `Link` header entries in GET responses with each URL in angle brackets, `rel="alternate"`, and `hreflang` | Non-HTML files such as PDFs |
| XML sitemap | `xhtml:link` child entries under each `loc` element with the `xhtml` XML namespace declared | Centralized management of multi-version URL sets |

In HTML documents, `link` elements must appear inside a well-formed `head` element, with one `link` element for every variant including the page itself.[6][8] Under XHTML 1.0, void elements such as `link` require a trailing slash.[8] Google specifies that `hreflang` annotations must be placed in dedicated `link` elements and must not be combined with other alternate-representation attributes such as `media` in a single `link` element.[6]

For HTTP headers, IETF RFC 8288 ("Web Linking", October 2017, by M. Nottingham, obsoleting RFC 5988) defines a general web linking model (link context, link relation type, link target, and optional target attributes), serializes links in the HTTP `Link` header field, and incorporates `Language-Tag` syntax from RFC 5646.[3] Registered link relation types, including `alternate`, are maintained in the IANA Link Relations registry.[3] In Google Search, the `Link` header returned in a resource's GET response lists every localized version separated by commas, enclosing each fully-qualified URL in angle brackets followed by `rel="alternate"` and `hreflang`; every version of the resource returns the identical header.[6]

In an [XML sitemap](https://mimirwiki.com/wiki/sitemaps), each localized version has its own `loc` element paired with child `xhtml:link` entries listing every language and region variant of that page, including itself, with the `xhtml` namespace declared.[6] When a page has three versions, the sitemap contains three `loc` entries and each entry holds three identical `xhtml:link` child entries.[6]

## Reciprocal linking and URL rules for hreflang

Google Search enforces shared structural rules across HTML `link` elements, HTTP `Link` headers, and XML sitemaps so that every URL in a localized group verifies the others.[6]

- **Self-referencing and complete sets**: Each language or regional version of a page must list itself together with all other variants, producing an identical annotation set on every version in the group.[6]
- **Bidirectional confirmation**: If two pages do not both point to each other, Google ignores the annotations. This rule prevents an external website from arbitrarily naming itself as an alternate version of another site's page.[6]
- **Partial bidirectional linking**: When maintaining complete bidirectional links across every language becomes impractical, some languages may be omitted on some pages. Google still processes pairs that link bidirectionally and advises linking newly added language pages bidirectionally to the site's originating or dominant languages.[6]
- **Fully-qualified URLs**: Every alternate URL must include its transport scheme (`http` or `https`), such as `https://example.com/foo`, excluding protocol-relative URLs (`//example.com/foo`) and relative paths (`/foo`).[6]
- **Cross-domain support**: Alternate URLs do not need to belong to the same domain.[6]
- **Generic language catchall**: When multiple regional URLs target speakers of one language (such as `en-IE`, `en-CA`, and `en-AU`), Google advises providing a generic language entry (`en`) for users in unspecified regions, which may reuse one of the regional URLs.[6]

Google does not use language-specific subdomains in URLs (such as `en`, `en-gb`, `en-us`, or `de`) to infer a page's target audience, so each target language or region must be mapped explicitly through `hreflang` annotations.[6]

## The x-default hreflang value for fallback pages

The `x-default` hreflang value designates a fallback URL for visitors whose language or region matches none of the explicitly listed variants on a page.[6] Google Search Central Blog published an announcement introducing `x-default` hreflang for international landing pages in April 2013, and later listed a May 2023 blog post titled "How x-default can help you".[10]

Google Search Central documentation highlights `x-default` especially for language or country selector pages and for home pages that redirect visitors automatically.[6] In Google's documented example, a website serving UK English (`en-GB`), US English (`en-US`), generic English (`en`), and German (`de`) pages assigns `hreflang="x-default"` to `https://www.example.com/`, a neutral landing page containing language and region selectors.[6]

The `x-default` value is supported in HTML `link` elements, HTTP `Link` headers, and XML sitemaps alongside standard BCP 47 language tags.[6]

## Google Search handling of hreflang and multilingual sites

Google Search uses hreflang annotations to recognize localized variations of equivalent content and present the version matching a searcher's language or regional settings.[6] Google distinguishes multilingual websites (sites offering content in more than one language, such as English and French versions for a Canadian business) from multi-regional websites (sites explicitly targeting users in different countries, such as Canada and the United States), noting that a single site can be both.[7]

Google Search does not use `hreflang`, the HTML `lang` attribute, or URLs to detect the language of a page.[6][7] Google determines page language algorithmically from the visible content on the page and advises using a single language for both content and navigation per page while avoiding side-by-side translations.[6][7]

Google documents three common scenarios for `hreflang`: pages where only the template (navigation and footer) is translated while the main user-generated content stays in one language, pages with small regional variations in a single language (such as English targeted to the US, UK, and Ireland), and pages fully translated into multiple languages.[6] Localized versions of a page are treated as duplicates only when the main content remains untranslated.[6]

Google advises assigning distinct URLs to each language version and linking them with `hreflang` annotations.[7] Dynamically changing content through cookies or browser settings can prevent Googlebot from discovering all variations, because Googlebot usually crawls from the United States and sends HTTP requests without an `Accept-Language` header.[7] Google also advises against automatic redirection based on assumed user language, favoring hyperlinks that let users select versions manually, and supports localized words in URLs and Internationalized Domain Names (IDNs) using UTF-8 encoding and proper URL escaping.[7]

## Frequently asked questions

### What is hreflang?

hreflang is an HTML attribute and link annotation parameter that indicates the human language, and optionally the target region, of a linked web resource using BCP 47 language tags. In Google Search, websites pair hreflang with the alternate link relation to connect localized versions of a page. [2][6][9]

### Which methods can be used to implement hreflang for Google Search?

As of 2026-11-23, Google Search supports three equivalent methods: HTML link elements inside the head element, HTTP Link response headers (useful for non-HTML files such as PDFs), and xhtml:link child entries in XML sitemaps. Using more than one method at the same time provides no additional search benefit. [6]

### Why do hreflang links need to be bidirectional?

Google Search requires every page in a localized set to reference itself and every other variant, and ignores pairs that do not point back to each other. This confirmation rule prevents another website from arbitrarily naming itself as an alternate version of a page it does not control. [6]

### What does hreflang="x-default" mean?

The x-default value identifies a fallback page for users whose language or region does not match any explicitly listed hreflang tag. Google announced x-default in April 2013 and documents its use for language or country selector pages and auto-redirecting home pages. [6][10]

### Does Google Search use hreflang to detect the language of a page?

No. Google Search does not use hreflang, the HTML lang attribute, or URLs to detect the language of a page. Google determines page language algorithmically from visible page content and uses hreflang to identify localized variations of the same content. [6][7]

### How are hreflang language and region codes formatted?

Language tags follow IETF BCP 47 (RFC 5646) and combine hyphen-separated subtags from the IANA Language Subtag Registry, beginning with a two- or three-letter ISO 639 primary language subtag optionally followed by a four-letter ISO 15924 script subtag or a two-letter ISO 3166-1 or three-digit UN M.49 region subtag. Language tags are case-insensitive in HTML and XML. [2][4][5]

## Quotable sentences

- The WHATWG HTML Living Standard (last updated 2026-11-22) defines hreflang as a reflected DOMString attribute on the HyperlinkElementUtils interface mixin. [1]
- MDN Web Docs states that the hreflang attribute on the HTML a element hints at the human language of the linked URL, has no built-in functionality, and takes the same values as the global lang attribute. [9]
- IETF RFC 5646, published in September 2009 as part of BCP 47, specifies the hyphen-separated subtag syntax for language tags and obsoletes RFC 4646. [2]
- Valid language, script, and region subtags are maintained in the IANA Language Subtag Registry, which had a file date of 2026-11-18 as of 2026-11-23. [4][5]
- IETF RFC 8288, published in October 2017, specifies the HTTP Link header field and references RFC 5646 Language-Tag syntax. [3]
- As of 2026-11-23, Google Search Central documentation lists HTML link elements, HTTP Link headers, and XML sitemaps as three equivalent methods for specifying hreflang annotations. [6]
- Google Search ignores hreflang annotations between two pages unless both pages link to each other and each page lists itself along with all alternate versions. [6]
- Google Search Central Blog announced the x-default hreflang value for international landing pages in April 2013. [10]

## Timeline

- 2009-09: The IETF publishes RFC 5646 (Tags for Identifying Languages) as part of BCP 47, obsoleting RFC 4646 and adding over 7,000 ISO 639-3 three-letter language codes to the IANA Language Subtag Registry. [2][5]
- 2013-04: Google Search Central Blog publishes an announcement introducing x-default hreflang for international landing pages. [10]
- 2015-07: The HTML link and a elements reach baseline browser availability, as tracked by MDN Web Docs. [8][9]
- 2017-10: The IETF publishes RFC 8288 (Web Linking), obsoleting RFC 5988 and defining HTTP Link header serialization with RFC 5646 language tag syntax. [3]

## Sources

1. HTML Standard. WHATWG. published 2026-11-22. https://html.spec.whatwg.org/multipage/links.html (checked 2026-11-23; tier 1: government or public registry)
2. RFC 5646: Tags for Identifying Languages. Internet Engineering Task Force (IETF). published 2009-09. https://www.rfc-editor.org/rfc/rfc5646.txt (checked 2026-11-23; tier 1: government or public registry)
3. RFC 8288: Web Linking. Internet Engineering Task Force (IETF). published 2017-10. https://www.rfc-editor.org/rfc/rfc8288.txt (checked 2026-11-23; tier 1: government or public registry)
4. IANA Language Subtag Registry. Internet Assigned Numbers Authority (IANA). published 2026-11-18. https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry (checked 2026-11-23; tier 1: government or public registry)
5. Language tags in HTML and XML. World Wide Web Consortium (W3C). https://www.w3.org/International/articles/language-tags/ (checked 2026-11-23; tier 1: government or public registry)
6. Localized Versions of your Pages | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/localized-versions (checked 2026-11-23; tier 3: official site)
7. Managing Multi-Regional and Multilingual Sites | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (checked 2026-11-23; tier 3: official site)
8. <link> HTML external resource link element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/link (checked 2026-11-23; tier 3: official site)
9. <a> HTML anchor element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a (checked 2026-11-23; tier 3: official site)
10. Introducing "x-default hreflang" for international landing pages | Google Search Central Blog | Google for Developers. Google Search Central Blog. published 2013-04. https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "hreflang." Version acccab62, 2026-11-23. https://mimirwiki.com/wiki/hreflang
