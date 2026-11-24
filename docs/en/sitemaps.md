---
title: "Sitemaps"
subtitle: "XML-based protocol for listing website URLs and metadata for search engine crawlers"
canonical_url: https://mimirwiki.com/wiki/sitemaps
language: en
page_class: anchor
revision_sha256: 0459330a861863dedb712d79cdd4816eadff75cac904ac5e344fc85e75cb5f3f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/sitemaps.md
  txt: https://mimirwiki.com/wiki/sitemaps.txt
  json: https://mimirwiki.com/wiki/sitemaps.json
  jsonld: https://mimirwiki.com/wiki/sitemaps.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/sitemaps
  ja: https://mimirwiki.com/ja/wiki/sitemaps
  zh: https://mimirwiki.com/zh/wiki/sitemaps
---

# Sitemaps

> Sitemaps is an XML protocol sponsored by Google, Yahoo, and Microsoft that lets websites list crawlable URLs and metadata for search engines. As of 2026-11-23, version 0.9 limits each sitemap or index file to 50,000 entries and 50 MB uncompressed, supports RSS, Atom, and text files, and permits extensions. Listing URLs helps discovery, while indexing remains optional.

Sitemaps is an XML-based web protocol that enables website operators to inform search engines about pages, images, videos, and other files available for crawling, along with metadata such as last modification dates. Sponsored by Google, Inc., Yahoo, Inc., and Microsoft Corporation through sitemaps.org, protocol version 0.9 defines XML schemas for individual sitemap files (urlset) and sitemap index files (sitemapindex), alongside support for syndication feeds and plain text URL lists. As of 2026-11-23, each sitemap file is limited to 50,000 URLs and 50 MB (52,428,800 bytes) uncompressed, and search engine XML extensions support specialized content such as images and news articles. Publishing a sitemap assists search engine crawlers in discovering URLs, while each search engine retains full discretion over whether to crawl or index listed entries.

**Also known as:** Sitemaps protocol, XML Sitemap, sitemap.xml, Sitemaps 0.9

## Key facts

- **Protocol version:** 0.9 (http://www.sitemaps.org/schemas/sitemap/0.9) (as of 2026-11-23) [1]
- **Sponsors:** Google, Inc., Yahoo, Inc., and Microsoft Corporation [3]
- **Per-file limits:** 50,000 URLs and 50 MB (52,428,800 bytes) uncompressed (as of 2026-11-23) [1]
- **Character encoding:** UTF-8 [1]
- **Specification license:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]

## Basic facts

- **Type:** Web protocol for informing search engine crawlers about crawlable URLs [1]
- **Sponsors:** Google, Inc., Yahoo, Inc., and Microsoft Corporation [3]
- **Protocol version:** 0.9 (as of 2026-11-23) [1]
- **XML namespace:** http://www.sitemaps.org/schemas/sitemap/0.9 (as of 2026-11-23) [1]
- **XML schemas:** sitemap.xsd (sitemaps) and siteindex.xsd (sitemap index files) (as of 2026-11-23) [2]
- **Supported formats:** XML, RSS 2.0, Atom 0.3 or 1.0, and UTF-8 plain text (as of 2026-11-23) [1]
- **Per-file entry limit:** 50,000 URLs per sitemap; 50,000 sitemaps per sitemap index (as of 2026-11-23) [1]
- **Per-file size limit:** 50 MB (52,428,800 bytes) uncompressed; gzip compression supported (as of 2026-11-23) [1]
- **Maximum loc length:** Less than 2,048 characters (as of 2026-11-23) [1]
- **Specification license:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]
- **Google Search Console index quota:** Up to 500 sitemap index files per site (as of 2025-12-10) [7]

## Overview of the Sitemaps protocol

The Sitemaps protocol is an XML-based specification that lets website operators inform search engines about pages, images, videos, and other files available for crawling.[1][5] Sitemaps.org is sponsored by Google, Inc., Yahoo, Inc., and Microsoft Corporation, and the sponsors license their copyrights in the specification under the Creative Commons Attribution-ShareAlike License (version 2.5).[3] Under the Sitemaps.org Terms of Service, no sponsor is obligated to read, index, or use any published sitemap, and each sponsor may alter or discontinue its support for the protocol at any time.[3]

In addition to listing URLs, a sitemap can communicate relationships and file metadata, including last modification dates and [alternate language versions](https://mimirwiki.com/wiki/hreflang) of pages.[5] Although the XML schema is the primary format, the Sitemaps protocol and Google Search also accept syndication feeds and plain text URL lists.[1][6]

- **XML sitemap**: Extensible format capable of carrying metadata for images, video, news, and localized page versions. Many content management systems (CMS) generate XML sitemaps automatically or through plugins, though maintaining XML mappings on large or rapidly changing sites can be complex.[1][6]
- **RSS, mRSS, and Atom feeds**: Sitemaps.org supports RSS 2.0 and Atom 0.3 or 1.0, reading the `link` field as the URL and the optional `pubDate` (RSS) or `updated` (Atom) field as the modification date.[1] Feeds often list only recent URLs and should be placed in the highest-level directory to be crawled.[1] Google supports RSS, mRSS, and Atom 1.0 feeds for HTML, indexable textual content, and video metadata, while image and news metadata require XML extensions.[6]
- **Plain text sitemap**: A UTF-8 text file containing one fully-qualified URL per line with no header, footer, or additional metadata, limited to HTML and other indexable textual pages.[1][6]

Content management systems such as WordPress, Wix, and Blogger commonly generate a sitemap automatically.[5] According to Google Search Central documentation updated on 2025-12-10, sitemaps are particularly useful for large sites where internal linking may miss new pages, new sites with few external links, and sites with substantial video, image, or Google News content.[5] By contrast, small sites with roughly 500 pages or fewer that are comprehensively linked from the home page and have few media or news pages may not need a sitemap.[5]

## Sitemaps XML format and elements

Sitemaps protocol 0.9 defines an XML document format encoded in UTF-8 under the namespace `http://www.sitemaps.org/schemas/sitemap/0.9`.[1] Two official XML Schema Definition files are provided for validation: `http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd` for sitemap files and `http://www.sitemaps.org/schemas/sitemap/0.9/siteindex.xsd` for sitemap index files.[2]

All XML values, including URLs, must follow RFC 3986 (URIs), RFC 3987 (IRIs), and the XML standard, using both URL percent-encoding for non-ASCII characters and XML entity escape codes for five reserved characters: ampersand (`&` as `&amp;`), single quote (`'` as `&apos;`), double quote (`"` as `&quot;`), greater-than (`>` as `&gt;`), and less-than (`<` as `&lt;`).[1][2] As of 2026-11-23, Sitemaps protocol 0.9 defines six core elements for a sitemap file.[1]

| Element | Requirement | Value rules and role |
| --- | --- | --- |
| `urlset` | Required | Root element encapsulating the file and declaring the protocol 0.9 XML namespace.[1] |
| `url` | Required | Parent element for each URL entry; all remaining tags appear as its children.[1] |
| `loc` | Required | Fully-qualified page URL starting with the protocol (such as `http` or `https`), ending with a trailing slash if required by the server, and shorter than 2,048 characters.[1][2] |
| `lastmod` | Optional | Date of last page modification in W3C Datetime format (`YYYY-MM-DD` or full ISO 8601 date and time with time zone). Records the page update date, separate from sitemap generation time and separate from HTTP `If-Modified-Since` (304) headers.[1][2] |
| `changefreq` | Optional | General estimate of how often the page is likely to change. Valid values are `always` (documents changing on every access), `hourly`, `daily`, `weekly`, `monthly`, `yearly`, and `never` (archived URLs).[1] |
| `priority` | Optional | Relative importance of the URL compared to other URLs on the same site, from `0.0` to `1.0` with a default of `0.5`.[1] |

The specification and Google Search documentation set additional rules for listed URLs. Entries must be complete, absolute URLs because relative paths such as `/mypage.html` are invalid, and Google attempts to crawl URLs exactly as written.[2][6] Site operators should list only one protocol version when both HTTP and HTTPS URLs exist, remove session IDs to avoid incomplete and redundant crawling, and include both frameset and frame content URLs for framed pages.[2] The order of URLs inside a sitemap does not influence how search engines process them.[2] Google notes that sitemaps can influence canonical URL selection, and where separate desktop and mobile URLs exist, Google advises listing either a single version or annotating both versions.[6]

## Sitemaps index files and size limits

Sitemaps files are limited as of 2026-11-23 to 50,000 URLs and 50 MB (52,428,800 bytes) uncompressed per file across XML and plain text formats.[1][2][6] To reduce bandwidth, site operators may compress sitemap files using gzip; the uncompressed file must remain within the 50 MB limit, and the sitemaps.org FAQ specifies gzip for compressed sitemaps.[1][2]

When a site exceeds 50,000 URLs or 50 MB, the URLs must be split across multiple sitemap files, which can then be grouped inside one or more sitemap index files.[1][2][7] A sitemap index file uses the same UTF-8 encoding and `http://www.sitemaps.org/schemas/sitemap/0.9` namespace as an individual sitemap.[1][7] As of 2026-11-23, each sitemap index file may list up to 50,000 sitemaps, must not exceed 50 MB (52,428,800 bytes) uncompressed, and supports gzip compression.[1][2][7]

A sitemap index file uses four XML elements defined in protocol 0.9.[1][7]

- `sitemapindex` (required): Root element enclosing all listed sitemap entries.[1][7]
- `sitemap` (required): Parent element for each individual sitemap and the sole direct child of `sitemapindex`.[1][7]
- `loc` (required): Entity-escaped URL identifying the location of a sitemap, which may be an XML sitemap, RSS file, Atom file, or plain text file.[1][7]
- `lastmod` (optional): W3C Datetime timestamp indicating when the referenced sitemap file itself was modified, independent of when individual pages listed inside that sitemap changed.[1][7]

Supplying `lastmod` inside a sitemap index enables incremental sitemap fetching, allowing crawlers to retrieve only recently updated sitemaps.[1][2] For sites with tens of millions of URLs, grouping frequently changing URLs into a small set of sitemaps and marking them with `lastmod` in the sitemap index helps search engines discover updates rapidly.[1][2] As of 2025-12-10, Google Search Console permits site owners to submit up to 500 sitemap index files per site, and submitting separate sitemaps also supports per-sitemap performance tracking in Search Console.[6][7]

## Sitemaps file location, scoping, and discovery

Sitemaps file placement determines which URLs are valid inside a given sitemap file.[1] Under the protocol's path-prefix rule, a sitemap hosted at `http://example.com/catalog/sitemap.xml` may list URLs beginning with `http://example.com/catalog/`, whereas URLs under sibling directories such as `http://example.com/images/` or under a different scheme such as `https://example.com/catalog/page1.php` are treated as invalid and dropped.[1] All URLs in a sitemap must share the same protocol, host, and port number as the sitemap file; a sitemap at `http://www.example.com/sitemap.xml` cannot include URLs from `http://subdomain.example.com`, and a sitemap at `http://www.example.com:100/sitemap.xml` requires that port number on every listed URL.[1][2]

Because path scoping applies to descendants of the sitemap directory, sitemaps.org and Google advise placing sitemaps at the web server root directory (`http://example.com/sitemap.xml`) so that a single location covers the entire site.[1][2][6] Separate directory-level sitemaps remain permitted when organizational security policies compartmentalize directory write access.[1][2] In Google Search, submitting a sitemap directly through Google Search Console lifts the parent-directory restriction.[6]

Sitemap index files follow parallel host and hierarchy rules: referenced sitemaps must reside on the same host and in the same directory as the sitemap index file or a deeper subdirectory.[1][7] Cross-host submission, in which a single host serves sitemaps for multiple distinct hosts, requires proving ownership of each target host.[1][7]

Once a sitemap is published, the sitemaps.org FAQ describes three methods for notifying search engines: direct submission through search engine tools, pinging search engines, and declaring the sitemap location in [robots.txt](https://mimirwiki.com/wiki/robots-txt).[2] The Robots Exclusion Protocol specification, published by the Internet Engineering Task Force (IETF) as RFC 9309 in September 2022, notes in Section 2.2 (Formal Syntax) that `robots.txt` parser implementors may define additional lines such as Sitemaps.[4] Regarding ping notifications, the Google Search Central Blog published an announcement in June 2023 stating that Google's sitemap ping endpoint was going away.[10]

## Sitemaps extensions for images, news, and other content

Sitemaps XML files support protocol extensions through additional XML namespaces for specialized content types.[1][6] Google Search Central documents extensions for images, news articles, videos, and [localized page versions](https://mimirwiki.com/wiki/hreflang), which can be placed in dedicated sitemaps or combined inside an existing XML sitemap.[5][6][8][9]

| Extension | XML namespace | Required elements | Documented limits |
| --- | --- | --- | --- |
| Core Sitemaps 0.9 | `http://www.sitemaps.org/schemas/sitemap/0.9` | `urlset`, `url`, `loc` (or `sitemapindex`, `sitemap`, `loc`) | 50,000 URLs or sitemaps; 50 MB uncompressed[1][7] |
| Google Image Sitemaps | `http://www.google.com/schemas/sitemap-image/1.1` | `image:image`, `image:loc` | Up to 1,000 `image:image` tags per `url`[8] |
| Google News Sitemaps | `http://www.google.com/schemas/sitemap-news/0.9` | `news:news`, `news:publication`, `news:name`, `news:language`, `news:publication_date` | 1 `news:news` per `url`; up to 1,000 `news:news` tags per sitemap; articles from the last 2 days[9] |

Google's image sitemap extension helps Googlebot discover images that might otherwise be missed, such as images loaded through JavaScript.[8] As of 2025-12-10, each `url` element may contain up to 1,000 `image:image` child elements, each enclosing a required `image:loc` URL.[8] Image URLs may be hosted on a separate domain, such as a [content delivery network](https://mimirwiki.com/wiki/content-delivery-network), provided both domains are verified in Google Search Console and `robots.txt` allows crawling.[8] Google removed four previously documented image tags (`image:caption`, `image:geo_location`, `image:title`, and `image:license`) from its image sitemap documentation, following a May 2022 Google Search Central Blog notice announcing the removal of selected sitemap extension tags.[8][10]

Google's news sitemap extension carries article metadata for news publishers, who may extend a general sitemap or maintain a dedicated news sitemap for separate Search Console tracking.[9] Publishers update their existing news sitemap as fresh articles are published, and Google News crawls news sitemaps at the same frequency as the rest of the site.[9] Entries must be limited to articles published within the last two days, after which older URLs or their `news:news` blocks are removed; if a news sitemap temporarily becomes empty, Search Console displays an Empty Sitemap warning for confirmation without affecting Google Search.[9] Each `url` accepts one `news:news` tag, and a single sitemap can hold up to 1,000 `news:news` tags.[9] Within `news:publication`, `news:name` must match the publication name on `news.google.com` omitting parenthetical text, and `news:language` uses a two- or three-letter ISO 639 code, with `zh-cn` for Simplified Chinese and `zh-tw` for Traditional Chinese.[9] The `news:publication_date` tag records the original W3C Datetime publication date on the site (`YYYY-MM-DD`, `YYYY-MM-DDThh:mmTZD`, or `YYYY-MM-DDThh:mm:ssTZD`).[9]

Google Search Central also notes that sitemap video entries can specify video running time, rating, and age-appropriateness rating, and that RSS, mRSS, and Atom 1.0 feeds can supply video metadata alongside HTML and indexable textual content.[5][6]

## Search engine handling of Sitemaps metadata and limits

Search engines handle optional Sitemaps metadata tags differently, and the Sitemaps protocol places no obligation on crawlers to read or index listed URLs.[1][3] While `urlset`, `url`, and `loc` are mandatory in protocol 0.9, sitemaps.org states that support for optional elements (`lastmod`, `changefreq`, and `priority`) varies by search engine and refers publishers to each provider's documentation.[1][2]

Within the protocol specification itself, `changefreq` is defined as a general crawling hint.[1] Crawlers may visit pages labeled `hourly` less frequently than once per hour, visit pages labeled `yearly` more frequently than once per year, and periodically check URLs labeled `never` for unexpected changes.[1] Similarly, `priority` expresses the relative importance of URLs within a single site on a `0.0` to `1.0` scale (default `0.5`); it does not compare pages across different domains, assigning high values to all URLs offers no relative differentiation, and the specification and FAQ state that `priority` is not expected to affect search result rankings.[1][2]

For `lastmod`, the protocol notes that the tag is independent of HTTP `If-Modified-Since` (304) server headers and that search engines may combine or evaluate both signals differently.[1] The sitemaps.org FAQ notes that supplying accurate modification timestamps for static files or data-derived estimates for dynamic pages helps crawlers skip unchanged URLs, lowering server bandwidth and CPU load.[2] In sitemap index files, Google Search Central documentation updated on 2025-12-10 states that `lastmod` may help Google schedule sitemaps for crawling.[7]

Across formats, Google states that it has no preference among XML sitemaps, RSS/mRSS/Atom 1.0 feeds, and plain text sitemaps.[6] Google treats sitemaps as a URL discovery aid and a signal that can influence canonical URL selection, while explicitly noting that listing a URL in a sitemap does not guarantee crawling or indexing.[5][6] Sitemaps function alongside [robots.txt](https://mimirwiki.com/wiki/robots-txt), which communicates crawler access permissions under RFC 9309, and crawlers must be permitted by `robots.txt` to access content listed in sitemaps.[4][8] Under the Sitemaps.org Terms of Service, Google, Yahoo, and Microsoft each reserve the right to use the protocol partially or discontinue support on any service.[3]

## Frequently asked questions

### What is a sitemap?

A sitemap is a machine-readable file in which a website lists pages, videos, images, and other files available for crawling, along with metadata such as last modification dates and alternate language versions. Search engines read sitemaps to discover and crawl URLs more efficiently. [1][5]

### What are the URL and file size limits for a sitemap?

As of 2026-11-23, each XML or text sitemap file can include up to 50,000 URLs and must be no larger than 50 MB (52,428,800 bytes) uncompressed. A sitemap index file can reference up to 50,000 sitemaps within the same 50 MB uncompressed limit, and files may be compressed with gzip. [1][2][6][7]

### Which XML elements are required in a sitemap and a sitemap index file?

A standard XML sitemap requires the urlset root element declaring the 0.9 namespace, a url parent element for each entry, and a loc child element holding the fully-qualified URL. A sitemap index file requires sitemapindex, sitemap, and loc elements, with lastmod available as an optional child tag. [1][7]

### Does the priority tag change search result rankings?

According to the Sitemaps protocol and FAQ, priority indicates the importance of a URL relative to other URLs on the same site on a scale from 0.0 to 1.0 (default 0.5). It does not compare pages across different sites and is not expected to change search result rankings. [1][2]

### How do search engines discover a sitemap file?

The sitemaps.org FAQ describes direct submission to search engines, pinging search engines, and listing the sitemap location in robots.txt, and RFC 9309 notes that robots.txt parsers can support Sitemaps lines. In June 2023, the Google Search Central Blog announced that Google's sitemap ping endpoint was going away, while Google Search Console remains a direct submission channel. [2][4][6][10]

### Does every website need a sitemap?

According to Google Search Central documentation updated on 2025-12-10, sitemaps are useful for large sites, new sites with few external links, and sites with extensive video, image, or news content. Small sites of roughly 500 pages or fewer that are comprehensively linked internally and lack extensive media or news pages may not need a sitemap. [5]

## Quotable sentences

- Sitemaps.org is sponsored by Google, Inc., Yahoo, Inc., and Microsoft Corporation, and its protocol specification is licensed under the Creative Commons Attribution-ShareAlike License (version 2.5). [3]
- As of 2026-11-23, Sitemaps protocol 0.9 requires UTF-8 encoding, the XML namespace http://www.sitemaps.org/schemas/sitemap/0.9, and urlset, url, and loc elements with loc values shorter than 2,048 characters. [1]
- As of 2026-11-23, a single sitemap file can contain at most 50,000 URLs and must be no larger than 50 MB (52,428,800 bytes) uncompressed, and a sitemap index file can list at most 50,000 sitemaps within the same 50 MB uncompressed limit. [1][2]
- Sitemaps protocol 0.9 provides XML validation schemas at sitemap.xsd and siteindex.xsd and supports RSS 2.0, Atom 0.3 or 1.0, and UTF-8 plain text files as alternative formats. [1][2]
- RFC 9309, published by the IETF in September 2022, notes in its ABNF formal syntax for robots.txt that parser implementors may define additional lines such as Sitemaps. [4]
- As of 2025-12-10, Google Search Console allows up to 500 sitemap index files per site, and submitting a sitemap through Search Console lifts the default parent-directory scope restriction. [6][7]
- As of 2025-12-10, Google's image sitemap extension (http://www.google.com/schemas/sitemap-image/1.1) permits up to 1,000 image:image tags per url element, and Google has removed image:caption, image:geo_location, image:title, and image:license from its documentation. [8]
- Google's news sitemap extension (http://www.google.com/schemas/sitemap-news/0.9) permits up to 1,000 news:news entries per sitemap and restricts entries to articles published within the last two days. [9]

## Timeline

- 2008-02-27: Sitemaps.org updates its Terms of Service naming Google, Inc., Yahoo, Inc., and Microsoft Corporation as sponsors and specifying Creative Commons Attribution-ShareAlike 2.5 licensing for the specification. [3]
- 2016-11-21: Sitemaps.org updates its FAQ documenting the 50 MB (52,428,800 bytes) and 50,000-URL limits along with the sitemap.xsd and siteindex.xsd XML schemas. [2]
- 2022-05: Google Search Central Blog publishes a notice announcing the removal of selected sitemap extension tags. [8][10]
- 2022-09: The IETF publishes RFC 9309 (Robots Exclusion Protocol), noting in its ABNF formal syntax that robots.txt parsers may define additional lines such as Sitemaps. [4]
- 2023-06: Google Search Central Blog publishes an announcement that Google's sitemaps ping endpoint is going away. [10]
- 2025-12-10: Google Search Central updates its documentation for Sitemaps overview, sitemap index files, and image sitemaps. [5][7][8]

## Sources

1. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (checked 2026-11-23; tier 3: official site)
2. sitemaps.org - FAQ. sitemaps.org. published 2016-11-21. https://www.sitemaps.org/faq.html (checked 2026-11-23; tier 3: official site)
3. sitemaps.org - Terms of service. sitemaps.org. published 2008-02-27. https://www.sitemaps.org/terms.html (checked 2026-11-23; tier 3: official site)
4. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (checked 2026-11-23; tier 1: government or public registry)
5. What Is a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. published 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview (checked 2026-11-23; tier 3: official site)
6. Build and Submit a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (checked 2026-11-23; tier 3: official site)
7. Manage Your Sitemaps With Sitemap Index Files | Google Search Central | Documentation | Google for Developers. Google Search Central. published 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/large-sitemaps (checked 2026-11-23; tier 3: official site)
8. Image Sitemaps | Google Search Central | Documentation | Google for Developers. Google Search Central. published 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps (checked 2026-11-23; tier 3: official site)
9. Create a News Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap (checked 2026-11-23; tier 3: official site)
10. Sitemaps ping endpoint is going away | Google Search Central Blog | Google for Developers. Google Search Central Blog. published 2023-06. https://developers.google.com/search/blog/2023/06/sitemaps-lastmod-ping (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Sitemaps." Version 0459330a, 2026-11-23. https://mimirwiki.com/wiki/sitemaps
