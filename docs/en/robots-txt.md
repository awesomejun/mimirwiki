---
title: "robots.txt"
subtitle: "Plain-text file under the Robots Exclusion Protocol (RFC 9309) that tells web crawlers which URIs they may access"
canonical_url: https://mimirwiki.com/wiki/robots-txt
language: en
page_class: anchor
revision_sha256: fe74fd318801fd514049a6eccda2cbc6f8e9fc40ca57b799740e0f07df2930ae
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/wiki/robots-txt.md
  txt: https://mimirwiki.com/wiki/robots-txt.txt
  json: https://mimirwiki.com/wiki/robots-txt.json
  jsonld: https://mimirwiki.com/wiki/robots-txt.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/robots-txt
---

# robots.txt

> robots.txt is a plain-text file placed at a website's root path (/robots.txt) under the Robots Exclusion Protocol (RFC 9309) to tell automated crawlers which URIs they may or may not access. Martijn Koster originally defined the convention in 1994, and the IETF standardized it in September 2022. Its rules are advisory and do not provide access authorization.

robots.txt is a UTF-8 plain-text file hosted at the top-level path /robots.txt of a web or FTP service to specify which URIs automated clients, known as crawlers, may or may not access under the Robots Exclusion Protocol (REP). Martijn Koster originally documented the convention in June 1994 following mailing-list consensus, and the Internet Engineering Task Force (IETF) published it as Standards Track RFC 9309 in September 2022. The file organizes User-agent groups paired with Allow and Disallow path rules, alongside optional records such as Sitemap. RFC 9309 defines robots.txt rules as advisory requests that crawlers are asked to honor, and the protocol provides no access authorization or technical enforcement.

**Also known as:** /robots.txt, Robots Exclusion Protocol, REP, RFC 9309, Robots Exclusion Standard

## Key facts

- **Standard:** RFC 9309 (IETF Standards Track, September 2022) [1]
- **Original author and date:** Martijn Koster (1994-06-30 mailing-list consensus) [4]
- **Canonical location:** /robots.txt at service root (UTF-8, text/plain) [1]
- **Core directives:** User-agent, Allow, Disallow (plus optional Sitemap) [1]
- **Google file size limit:** 500 KiB; content past the limit is ignored (as of 2026-11-23) [6]

## Basic facts

- **Protocol name:** Robots Exclusion Protocol (REP) [1]
- **IETF specification:** RFC 9309 (Proposed Standard, September 2022) [3]
- **RFC 9309 authors:** Martijn Koster, Gary Illyes, Henner Zeller, Lizzi Sassman [3]
- **Original consensus date:** 1994-06-30 [4]
- **File path:** /robots.txt (all lowercase, top-level directory) [1]
- **Encoding and media type:** UTF-8, text/plain [1]
- **Standardized directives:** User-agent, Allow, Disallow [1]
- **Special characters:** # (comment), * (wildcard), $ (end of match) [1]
- **Google file size limit:** 500 KiB (as of 2026-11-23) [6]
- **Google default cache duration:** Up to 24 hours (as of 2026-11-23) [6]
- **Reference C++ parser:** github.com/google/robotstxt (Apache-2.0 license) [8]
- **Related IETF working group:** AI Preferences (aipref), active under charter-ietf-aipref-01 (as of 2026-11-23) [2]

## What robots.txt is and how it originated

robots.txt is a plain-text file served at the top-level path of a website or FTP host under the Robots Exclusion Protocol (REP) to state which URIs automated crawlers may access.[1][5] Service owners publish the file so automated clients, such as search engine crawlers that traverse links for indexing, can determine which paths to avoid before requesting site resources.[1][7]

Martijn Koster originally documented the protocol in "A Standard for Robot Exclusion," recording a consensus reached on June 30, 1994 on the `robots` mailing list (`robots-request@nexor.co.uk`) and discussed on the Technical World Wide Web mailing list (`www-talk@info.cern.ch`).[1][4] The document addressed incidents in 1993 and 1994 in which web robots (also called wanderers or spiders) sent rapid requests that overloaded servers, fetched the same files repeatedly, or traversed deep virtual trees, temporary or duplicated content, and CGI scripts with side effects such as voting.[4] A single file at `/robots.txt` was chosen because any existing web server could serve it without extra configuration, crawlers could retrieve the policy in one request, and the filename fit operating-system naming rules with minimal risk of collision.[4]

For 25 years, REP operated as an informal de facto standard without formal backing from a standards body, documented in the 1994 specification and a 1997 Internet-Draft titled "A Method for Web Robots Control."[4][5][8] The original 1994 format included only `User-agent` and `Disallow` fields and omitted an `Allow` field and wildcard matching.[4][5] In September 2022, the Internet Engineering Task Force (IETF) published RFC 9309 ("Robots Exclusion Protocol") as a Proposed Standard on the Standards Track, authored by Martijn Koster, Gary Illyes, Henner Zeller, and Lizzi Sassman based on the individual draft `draft-koster-rep` with Murray Kucherawy as Responsible Area Director.[1][3] RFC 9309 added a formal protocol grammar, standardized `Allow` and wildcard characters, and specified rules for error handling and caching.[1]

## robots.txt file location, format, and scope

A robots.txt file must be placed at the all-lowercase path `/robots.txt` in the top-level directory of a service, following the URI form `scheme:[//authority]/robots.txt` (such as `https://www.example.com/robots.txt` or `ftp://ftp.example.com/robots.txt`).[1][5] RFC 9309 requires the file to be UTF-8 encoded (RFC 3629) and served with the Internet Media Type `text/plain` (RFC 2046), using CR, LF, or CRLF line endings.[1][6] In Google Search's implementation, supported protocols are HTTP and HTTPS (fetched using a non-conditional HTTP GET request) and FTP (fetched via an anonymous `RETR` command).[6]

Rules inside a robots.txt file apply only to the exact host, protocol, and port number from which the file is fetched.[6] As documented by Google, the scope follows these boundaries:[6]

- **Subdomains and subdirectories**: a file on `https://example.com/robots.txt` does not cover `https://other.example.com/`, and a file placed in a subdirectory such as `/folder/robots.txt` is invalid.
- **Protocols and ports**: rules on `https://example.com/` do not apply to `http://example.com/` or `ftp://example.com/`; standard ports (80 for HTTP, 443 for HTTPS, 21 for FTP) match default hostnames, while non-standard ports such as `:8181` require their own file.
- **IDNs and IP addresses**: Internationalized Domain Names are equivalent to their Punycode forms (RFC 3492), and a file hosted on an IP-address hostname applies only to crawling by that IP address.

As of 2026-11-23, Google enforces a maximum robots.txt file size of 500 kibibytes (KiB) and ignores any content beyond that limit.[6] Google's parser also ignores invalid lines, including a leading Unicode Byte Order Mark (BOM), and applies any valid rules found in the response.[6]

## robots.txt directives, syntax, and matching rules

The robots.txt syntax defined in RFC 9309 uses Augmented Backus-Naur Form (ABNF, RFC 5234) to organize key-value lines into groups consisting of one or more `User-agent` lines followed by `Allow` and `Disallow` rules.[1] Field names are case-insensitive, comments begin with `#`, and crawlers should ignore `Allow` and `Disallow` rules that appear before the first `User-agent` line.[1][4][6]

| Directive or token | Role in RFC 9309 and crawler implementations |
| --- | --- |
| `User-agent` | Identifies the target crawler by product token (ASCII letters, `_`, `-`) or `*` for default rules; matched case-insensitively.[1] |
| `Disallow` | Specifies a URI path prefix starting with `/` that the matched crawler should not access; an empty value imposes no restriction.[1][6] |
| `Allow` | Specifies a URI path prefix starting with `/` that the matched crawler may access, used to permit subpaths inside disallowed directories.[1][6] |
| `Sitemap` | Non-core record permitted by RFC 9309 without terminating a group; supported by Google with the full URL of a sitemap.[1][6] |

Each crawler selects its product token, which should appear as a substring of its HTTP `User-Agent` header (RFC 9110), and combines the rules of all groups matching that token.[1] When no specific group matches, the crawler follows the `User-agent: *` group if present; when neither exists, or when the file is empty, no rules apply.[1][4] Path matching starts at the first octet of the path and should be case-sensitive.[1] Before comparison, non-ASCII octets and RFC 3986 reserved characters must be percent-encoded, while percent-encoded unreserved ASCII characters must be unencoded.[1] RFC 9309 requires support for three special characters: `#` for comments, `*` for zero or more occurrences of any character, and `$` to mark the end of the match pattern, with literal `*` and `$` matched as `%2A` and `%24`.[1]

When multiple rules match a URI, crawlers must apply the most specific match, defined as the pattern with the most octets.[1] If an `Allow` rule and a `Disallow` rule are equivalent in specificity, the `Allow` rule should be used; the `/robots.txt` URI itself is implicitly allowed.[1] Under RFC 9309, crawlers may interpret other records such as Sitemaps as long as they do not interfere with group parsing.[1] Google supports `user-agent`, `allow`, `disallow`, and `sitemap`, and does not support `crawl-delay`.[6] Under the Sitemaps protocol, an XML sitemap is a UTF-8 `<urlset>` document containing `<url>` and `<loc>` entries, capped at 50,000 URLs and 50 MB (52,428,800 bytes) uncompressed per file, and multiple sitemaps can be listed in a `<sitemapindex>` file.[10]

To reduce parsing differences across implementations, Google open-sourced its production C++ robots.txt parser and matcher library in `github.com/google/robotstxt` under the Apache-2.0 license.[8] The repository includes a command-line testing binary (`robots_main`) that evaluates a user-agent and an RFC 3986 URI against a local robots.txt file, returning exit code 0 for allowed and 1 for disallowed.[8]

## robots.txt HTTP status code handling and caching

Crawlers determine how to apply robots.txt rules based on the HTTP status code or network result returned when fetching `/robots.txt`.[1][6] RFC 9309 defines baseline categories for successful access, redirects, unavailable responses, and unreachable errors, while search engines publish additional operational timeouts and caching policies.[1][6]

| Response class | RFC 9309 specification | Google crawler handling (as of 2026-11-23) |
| --- | --- | --- |
| `2xx` (Success) | Parse and follow valid rules in the file.[1] | Process the robots.txt file as provided.[6] |
| `3xx` (Redirect) | Follow at least five consecutive redirects (such as 301 or 302), even across authorities, applying retrieved rules to the initial authority; after more than five, crawlers may treat the file as unavailable.[1] | Follow at least five redirect hops, then stop and treat the response as 404; logical redirects via frames, JavaScript, or meta refresh are not followed.[6] |
| `4xx` (Unavailable) | HTTP 400-499 indicates the file is unavailable; crawlers may access any resource on the server.[1] | All 4xx errors except 429 are treated as no robots.txt (no crawl restrictions); 4xx codes other than 429 (including 401 and 403) do not reduce crawl rate.[6] |
| `5xx` and network errors (Unreachable) | HTTP 500-599 or network errors leave the file undefined; crawlers must assume complete disallow.[1] | Stop crawling for 12 hours while retrying; for the next 30 days use the last valid cached copy (or assume no restrictions if no cache exists); after 30 days, treat a generally available site as unrestricted or halt crawling if the site has general availability problems.[6] |

Google classifies DNS errors, timeouts, invalid responses, reset or interrupted connections, and HTTP chunking errors alongside 5xx server errors.[6] On HTTP 503 responses, Google retries fetching robots.txt at higher frequency.[6]

As of 2026-11-23, Google generally caches the contents of a robots.txt file for up to 24 hours, may retain the cached version longer when refresh attempts fail due to timeouts or 5xx errors, and may share cached rules across different Google crawlers.[6] Google may also increase or decrease the cache lifetime based on HTTP `Cache-Control` `max-age` response headers.[6]

## robots.txt advisory limits, security, and indexing

RFC 9309 states that robots.txt rules are not a form of access authorization, and compliance depends on each crawler choosing to follow the protocol.[1][7] The original 1994 specification noted that no party enforces the rules and no guarantee exists that all current or future robots will honor them.[4] Malicious automated clients, including vulnerability scanners and email address harvesters used by spammers, routinely ignore robots.txt.[5]

Because `/robots.txt` is publicly accessible to any client, listing paths inside it reveals which server directories an administrator wants crawlers to skip.[5] Both robotstxt.org and Google document that robots.txt cannot keep confidential material hidden and that protecting private files requires access controls such as password protection.[5][7] In addition, Google documents that REP does not apply to user-triggered fetchers, such as feed subscriptions, or crawlers operated to protect user safety, such as malware analysis.[6]

For search engines, robots.txt manages crawling traffic and bandwidth consumption, while indexing behavior depends on file type and separate directives.[7][9] Blocking an HTML page, PDF, or other text-based document in robots.txt prevents Google from crawling the page, yet Google can still index the URL without visiting it if external pages link to that URL with descriptive anchor text, displaying a search result without a description.[7] Preventing a crawlable page from appearing in search results requires page-level directives such as the HTML `<meta name="robots">` element (for example `noindex`) or the `X-Robots-Tag` HTTP response header, or restricting access via authentication.[7][9] For media files such as images, videos, and audio, Google documents that robots.txt prevents those files from appearing in Google Search results, while blocking essential stylesheet or script resource files can prevent Google from rendering and analyzing dependent pages accurately.[7]

## robots.txt, IETF AIPREF, and AI crawler preference signaling

In addition to search engine crawling, robots.txt is referenced in standards work on expressing content preferences for Artificial Intelligence (AI) model development, deployment, and use.[2] As of 2026-11-23, the IETF AI Preferences (`aipref`) working group is active in the Web and Internet Transport (`wit`) area under approved charter `charter-ietf-aipref-01`, chaired by Mark Nottingham and Suresh Krishnan with Mike Bishop as Area Director.[2]

The `aipref` charter defines three deliverables: a standards-track vocabulary document (`draft-ietf-aipref-vocab`) describing AI-related content preferences independently of delivery mechanism, standards-track attachment specifications (`draft-ietf-aipref-attach`) associating those preferences with content in IETF protocols and formats, and a standard method for reconciling multiple expressions of preferences.[2] Both draft deliverables are listed on the IETF Datatracker with August 2026 milestones as of 2026-11-23.[2] The charter explicitly identifies Well-Known URIs (RFC 8615), such as the Robots Exclusion Protocol (RFC 9309), alongside HTTP response header fields as attachment mechanisms, and directs the group to liaise with the International Press Telecommunications Council (IPTC), the PLUS Coalition, WHATWG, and W3C.[2]

Consistent with the advisory boundary of RFC 9309, the `aipref` charter excludes four areas from its scope: technical enforcement of preferences, application-layer protocols for authenticating or authorizing clients or crawlers, registries of content preferences, and auditing or transparency measures for AI training.[2] Outside standards bodies, infrastructure providers have also introduced controls separating search discovery from AI training: on September 15, 2026, [Cloudflare](https://mimirwiki.com/wiki/cloudflare) announced controls and an Accountable designation forming a shared model with Apple, Google, and Microsoft to let site owners stay discoverable in search while disallowing AI training.[11]

## Frequently asked questions

### What is a robots.txt file?

A robots.txt file is a UTF-8 plain-text file placed at /robots.txt in the root directory of a web or FTP host under the Robots Exclusion Protocol (RFC 9309). It tells automated crawlers which URI paths on that host they may or may not access. Martijn Koster originally documented the convention in June 1994, and the IETF published RFC 9309 in September 2022. [1][4]

### Which directives does robots.txt support under RFC 9309?

RFC 9309 standardizes three core directives: User-agent, Allow, and Disallow, along with the special characters # for comments, * for wildcard sequences, and $ for end-of-path matching. Crawlers may also interpret additional records such as Sitemap without interrupting group parsing. As of 2026-11-23, Google supports User-agent, Allow, Disallow, and Sitemap, and does not support crawl-delay. [1][6]

### How do crawlers handle HTTP 4xx and 5xx errors for robots.txt?

Under RFC 9309, HTTP 400-499 responses indicate that robots.txt is unavailable, so crawlers may access any resource on the server, while HTTP 500-599 responses indicate an unreachable file and require assuming complete disallow. As of 2026-11-23, Google treats 4xx errors other than 429 as no crawl restrictions, and on 5xx errors stops crawling for 12 hours before falling back to its last cached copy for up to 30 days. [1][6]

### What is Google's file size limit for robots.txt?

As of 2026-11-23, Google enforces a maximum file size of 500 kibibytes (KiB) for robots.txt. Any content after the 500 KiB limit is ignored by Google's parser. [6]

### Does robots.txt prevent a web page from appearing in search results or secure private files?

No. RFC 9309 explicitly states that robots.txt rules are not a form of access authorization, and non-compliant crawlers can ignore the file. For web pages, Google can still index a disallowed URL without visiting it if other pages link to it, so excluding a page from search results or protecting private files requires mechanisms such as the HTML meta robots element, X-Robots-Tag HTTP headers, or password protection. [1][7][9]

### How does the IETF AIPREF working group relate to robots.txt?

As of 2026-11-23, the active IETF AI Preferences (aipref) working group is chartered to standardize a vocabulary and protocol attachment methods for expressing preferences about collecting and processing content for AI systems. Its approved charter explicitly includes attaching those preferences through Well-Known URIs (RFC 8615) such as the Robots Exclusion Protocol (RFC 9309), as well as HTTP response header fields. [2]

## Quotable sentences

- Martijn Koster originally documented the Robots Exclusion Protocol following mailing-list consensus on June 30, 1994. [1][4]
- The IETF published the Robots Exclusion Protocol as Standards Track RFC 9309 in September 2022. [1][3]
- RFC 9309 requires a robots.txt file to be UTF-8 encoded with media type text/plain and served at the all-lowercase path /robots.txt. [1]
- Under RFC 9309, crawlers apply the most specific path match by octet length, and an Allow rule takes precedence when an Allow rule and a Disallow rule are equivalent. [1]
- Under RFC 9309, HTTP 400-499 responses for robots.txt permit accessing any server resource, whereas HTTP 500-599 responses require assuming complete disallow. [1]
- As of 2026-11-23, Google enforces a 500 KiB file size limit for robots.txt and ignores content beyond that limit. [6]
- Google documents that blocking a web page in robots.txt does not prevent its URL from appearing in Google Search results if other pages link to it. [7]
- As of 2026-11-23, the active IETF AI Preferences (aipref) working group is chartered to specify attaching AI content preferences using IETF protocols including RFC 9309 and HTTP response header fields. [2]

## Timeline

- 1994-06-30: Mailing-list consensus is reached on "A Standard for Robot Exclusion," authored by Martijn Koster. [4]
- 1997: The Internet-Draft "A Method for Web Robots Control" documents the robots.txt exclusion mechanism. [5]
- 2022-09: The IETF publishes RFC 9309 ("Robots Exclusion Protocol") as a Proposed Standard on the Standards Track. [1][3]
- 2026-09-15: Cloudflare announces controls and an Accountable designation with Apple, Google, and Microsoft for keeping sites discoverable in search while disallowing AI training. [11]

## Sources

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (checked 2026-11-23; tier 1: government or public registry)
2. AI Preferences (aipref). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (checked 2026-11-23; tier 1: government or public registry)
3. RFC 9309 - Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://datatracker.ietf.org/doc/rfc9309/ (checked 2026-11-23; tier 1: government or public registry)
4. A Standard for Robot Exclusion - The Web Robots Pages. robotstxt.org. published 1994-06-30. https://www.robotstxt.org/orig.html (checked 2026-11-23; tier 3: official site)
5. About /robots.txt - The Web Robots Pages. robotstxt.org. https://www.robotstxt.org/robotstxt.html (checked 2026-11-23; tier 3: official site)
6. How Google Interprets the robots.txt Specification | Google Crawling Infrastructure | Crawling infrastructure | Google for Developers. Google Search Central. https://developers.google.com/crawling/docs/robots-txt/robots-txt-spec (checked 2026-11-23; tier 3: official site)
7. Robots.txt Introduction and Guide | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/robots/intro (checked 2026-11-23; tier 3: official site)
8. GitHub - google/robotstxt: The repository contains Google's robots.txt parser and matcher as a C++ library (compliant to C++11).. Google (GitHub). https://github.com/google/robotstxt (checked 2026-11-23; tier 3: official site)
9. Robots.txt - Glossary | MDN. MDN Web Docs. published 2025-11-26. https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt (checked 2026-11-23; tier 3: official site)
10. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (checked 2026-11-23; tier 3: official site)
11. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. published 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "robots.txt." Version fe74fd31, 2026-11-23. https://mimirwiki.com/wiki/robots-txt
