---
title: "IndexNow"
subtitle: "Open HTTP protocol for websites to notify search engines of URL additions, updates, and deletions"
canonical_url: https://mimirwiki.com/wiki/indexnow
language: en
page_class: anchor
revision_sha256: 445adc69b7c7a8f9db4950bab12008abc9aa3da9ddc923241fc4bf07aed987aa
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/indexnow.md
  txt: https://mimirwiki.com/wiki/indexnow.txt
  json: https://mimirwiki.com/wiki/indexnow.json
  jsonld: https://mimirwiki.com/wiki/indexnow.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/indexnow
  ja: https://mimirwiki.com/ja/wiki/indexnow
  zh: https://mimirwiki.com/zh/wiki/indexnow
  es: https://mimirwiki.com/es/wiki/indexnow
---

# IndexNow

> IndexNow is an open HTTP protocol launched by Microsoft Bing and Yandex in October 2021 for notifying search engines of added, updated, or deleted URLs. Sites verify ownership with a hosted text key file and submit one URL via GET or up to 10,000 via POST as of 2026-11-23. Each participating endpoint shares submissions with all others.

IndexNow is an open HTTP notification protocol that lets website owners inform participating search engines when URLs on a host are added, updated, or deleted. Microsoft Bing and Yandex announced the protocol on October 18, 2021, and its specification on IndexNow.org is licensed under Creative Commons Attribution-ShareAlike 4.0 by sponsors Microsoft Corporation, Yandex N.V., and Seznam.cz, a.s. A site verifies domain ownership with a hosted UTF-8 text key file and sends either single-URL HTTP GET requests or JSON POST batches of up to 10,000 URLs to any participating endpoint, which shares submitted URLs with all other participating search engines. As of 2026-11-23, the official registry at indexnow.org/searchengines.json lists seven participating endpoints: Bing, Yandex, Seznam, Naver, Yep, Internet Archive, and Amazonbot.

**Also known as:** IndexNow protocol, IndexNow API, IndexNow.org

## Key facts

- **Launched:** 2021-10-18 [6]
- **Creators:** Microsoft Bing and Yandex [6]
- **Specification license:** Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0) (as of 2026-11-23) [5]
- **Batch submission limit:** Up to 10,000 URLs per HTTP POST request (as of 2026-11-23) [2]
- **Registered endpoints:** 7 in searchengines.json (Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (as of 2026-11-23) [4]

## Basic facts

- **Type:** Open HTTP URL notification protocol [1]
- **Launched:** 2021-10-18 [6]
- **Creators:** Microsoft Bing and Yandex [6]
- **Specification sponsors:** Microsoft Corporation, Yandex N.V., Seznam.cz, a.s. (as of 2026-11-23) [5]
- **License:** Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0) (as of 2026-11-23) [5]
- **Submission methods:** HTTP GET (1 URL) and HTTP POST JSON (up to 10,000 URLs) (as of 2026-11-23) [2]
- **Global endpoint:** https://api.indexnow.org/indexnow (as of 2026-11-23) [3]
- **Verification method:** UTF-8 text key file (8 to 128 characters) hosted on the site (as of 2026-11-23) [2]
- **URI encoding standard:** RFC 3986 [2]
- **Registered search engines:** 7 entries in searchengines.json (Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (as of 2026-11-23) [4]
- **Cost:** Free (as of 2026-11-23) [8]

## What IndexNow is and how it began

IndexNow is a free, open HTTP protocol that allows website owners to notify participating search engines and web crawlers when URLs on a site are added, updated, or deleted.[1][8] Without push notifications, search engines rely on periodic crawling to detect website changes, which can take days or weeks because crawlers do not revisit every URL frequently.[1][6] Sending a notification when content changes lets search engines prioritize crawling those URLs and limit exploratory crawling on unchanged pages, reducing server load.[1][6][8]

Microsoft Bing and Yandex announced IndexNow on October 18, 2021.[6] According to the IndexNow.org Terms of Service read on 2026-11-23, the sponsors of IndexNow.org are Microsoft Corporation, Yandex N.V., and Seznam.cz, a.s.[5] The sponsors license their copyrights in the protocol specification published on IndexNow.org under the Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0) license, with no other intellectual property rights granted, and the Terms of Service are governed by the laws of the State of California.[1][5]

A core requirement of IndexNow is cross-engine sharing: search engines that adopt the protocol agree that every URL submitted to one participating endpoint is automatically shared with all other participating search engines.[2][3][6] Website owners therefore send each URL notification to a single participating endpoint.[3]

## IndexNow submission methods and HTTP status codes

IndexNow supports two HTTP submission methods for notifying search engines of added, updated, or deleted URLs: single-URL HTTP GET requests and multi-URL HTTP POST JSON requests.[2] Both methods can be issued from any HTTP client, browser, script, or command-line utility such as `curl` or `wget`.[2][3]

To submit one URL via HTTP GET, a site sends a request to `https://<searchengine>/indexnow?url={url-changed}&key={your-key}`, with an optional `keyLocation` parameter when the key file is placed outside the site root.[2][3] Submitted URLs must be URL-escaped and encoded under RFC 3986, such as encoding `:` as `%3A`, `/` as `%2F`, `?` as `%3F`, `=` as `%3D`, and `&` as `%26`.[2][3]

To submit multiple URLs in one request, a site sends an `HTTP POST` to `/indexnow` with the header `Content-Type: application/json; charset=utf-8` and a JSON body containing `host`, `key`, optional `keyLocation`, and `urlList`.[2][3] As of 2026-11-23, each POST request accepts up to 10,000 URLs and may mix `http` and `https` URLs for the same host.[2][3] Exceeding 10,000 URLs in one payload can cause the request to fail or return HTTP 422.[3] Sites can also submit redirected URLs (HTTP 301, HTTP 302, or meta refresh) and deleted URLs returning HTTP 404 or HTTP 410 so search engines update or remove outdated entries.[3]

As of 2026-11-23, IndexNow.org documents six HTTP response codes for submission requests.[2][3][7]

| HTTP code | Status | Documented meaning |
| --- | --- | --- |
| 200 | OK | URL or URL batch submitted successfully; confirms receipt only |
| 202 | Accepted | URL received while key ownership validation is pending (common on an initial request) |
| 400 | Bad Request | Invalid request format |
| 403 | Forbidden | Key invalid (for example, key file missing or key absent from the file) |
| 422 | Unprocessable Entity | URLs do not belong to the host, key fails schema rules, or payload exceeds limits |
| 429 | Too Many Requests | Request rate flagged as excessive or potential spam |

## IndexNow API key rules and domain ownership verification

IndexNow requires website owners who submit URLs manually to prove ownership of the target host by hosting a UTF-8 encoded text key file on that host.[2][3] As of 2026-11-23, the key must be 8 to 128 characters long and contain only lowercase ASCII letters (`a-z`), uppercase ASCII letters (`A-Z`), digits (`0-9`), and hyphens (`-`).[2][3] The IndexNow documentation refers to these as hexadecimal characters while explicitly permitting `a-z`, `A-Z`, `0-9`, and `-`.[2] Keys can be generated with a GUID or UUID generator, command-line tools, or online generators such as the tool in Bing Webmaster Tools.[3][6][7]

IndexNow defines two ways to host the key file for verification.[2]

- Option 1 (root directory): Host a UTF-8 file named `{your-key}.txt` at the root directory of the host, such as `https://www.example.com/{your-key}.txt`, containing only the key string.[2][3] The specification describes Option 1 as the preferred setup, and it covers URLs across the host.[2][3]
- Option 2 (subpath directory): Host one or more UTF-8 text key files in publicly accessible folders on the same host without login requirements, and supply the key file URL in every submission via the `keyLocation` query parameter (GET) or JSON field (POST).[2][3] Under Option 2, the directory of the key file scopes which URLs are valid: for example, a key file at `http://example.com/catalog/key12457EDd.txt` covers URLs starting with `http://example.com/catalog/`, whereas URLs under `http://example.com/help/` or `http://example.com/image/` are invalid for that key.[2]

When a site submits URLs, participating search engines crawl the key file to verify host ownership and continue recognizing the key until the owner changes it.[2] To rotate an API key without service interruption, a site owner replaces the existing key file with a new `{key}.txt` file and starts submitting URLs with the new key, triggering automatic re-verification.[3] Websites using a content management system, hosting provider, or CDN that natively manages IndexNow submissions do not need to create a key file manually.[3]

## IndexNow participating search engines and endpoints

IndexNow publishes a machine-readable JSON registry of participating search engines and crawlers at `https://www.indexnow.org/searchengines.json`.[4] As of 2026-11-23, `searchengines.json` lists seven participants, each mapped to a `meta.json` endpoint.[4] On the same date, the IndexNow.org homepage names five supporting search engines (Microsoft Bing, Naver, Seznam.cz, Yandex, and Yep), while the IndexNow FAQ lists submission endpoints for six named services plus the global endpoint `https://api.indexnow.org/indexnow`.[1][3]

| Registry key (`searchengines.json`) | Metadata URL (`searchengines.json`) | Submission endpoint (`indexnow.org/faq`) |
| --- | --- | --- |
| `bing` | `https://www.bing.com/indexnow/meta.json` | `https://www.bing.com/indexnow` |
| `yandex` | `https://www.yandex.com/indexnow/meta.json` | `https://yandex.com/indexnow` |
| `seznam` | `https://search.seznam.cz/indexnow/meta.json` | `https://search.seznam.cz/indexnow` |
| `naver` | `https://searchadvisor.naver.com/indexnow/meta.json` | `https://searchadvisor.naver.com/indexnow` |
| `yep` | `https://indexnow.yep.com/indexnow/meta.json` | `https://indexnow.yep.com/indexnow` |
| `internetarchive` | `https://web-static.archive.org/indexnow/meta.json` | Not listed in FAQ endpoint list |
| `amazonbot` | `https://indexnow.amazonbot.amazon/indexnow/meta.json` | `https://indexnow.amazonbot.amazon/indexnow` |

On May 19, 2025, Microsoft AI Bing Principal Product Managers Fabrice Canel and Krishna Madhavan announced on the Bing Webmaster Blog that Amazon planned to begin adopting IndexNow in mid-June 2025 to detect web content changes and reduce unnecessary crawling.[9] As of 2026-11-23, Amazon's `amazonbot` endpoint is listed in both `searchengines.json` and the IndexNow FAQ.[3][4]

Under the requirements published on IndexNow.org, a search engine participating in IndexNow must automatically share submitted URLs with all other participating search engines, have a noticeable presence in at least one market or be closely linked to the search market, and make a significant contribution to URL submissions.[2]

## IndexNow CMS, plugin, and Cloudflare Crawler Hints integrations

IndexNow is integrated into content management systems (CMS), third-party SEO plugins, and [content delivery networks](https://mimirwiki.com/wiki/content-delivery-network) (CDNs) so websites can issue URL change notifications automatically.[3][7]

On November 30, 2021, [Cloudflare](https://mimirwiki.com/wiki/cloudflare) partnered with Microsoft Bing and Yandex to add IndexNow support to Cloudflare Crawler Hints and made Crawler Hints generally available free of charge to all Cloudflare customers.[10] Cloudflare customers enable the integration from a single setting in the Configuration section under the Cache tab of the Cloudflare dashboard, after which Cloudflare sends IndexNow signals automatically when site content changes.[10] In the November 30, 2021 announcement, Cloudflare reported that approximately 45% of Internet traffic originated from web crawlers and bots and that a year-long study of major search crawler traffic found 53% of crawler visits requested pages unchanged since the previous visit.[10] By that date, more than 60,000 unique Cloudflare websites had opted in to Crawler Hints and sent Bing about one billion change hints.[10] As of 2026-11-23, both IndexNow.org and Bing Webmaster Tools list Cloudflare Crawler Hints as a native CDN integration, and the October 2021 launch post also noted that Akamai planned to integrate IndexNow.[3][6][7]

As of 2026-11-23, IndexNow.org and Bing Webmaster Tools list 16 CMS platforms that provide native IndexNow integration or support through plugins and extensions: WordPress, Shopify, Wix, GoDaddy, Duda, XenForo, Milestone, Joomla!, Drupal, Bitrix24, PrestaShop, MODX, Shopware, OpenCart, Typo3, and Umbraco.[3][7] Bing Webmaster Tools lists specific third-party plugins including the IndexNow plugin, Yoast, RankMath, AIOSEO, and SEOPress for WordPress; InstaIndex for Shopify; Aimy Sitemap PRO and JSitemap for Joomla!; and ReIndex and TurboIndex for Bitrix24.[7]

At launch in October 2021, Microsoft Bing published open-source code to help WordPress and other CMS platforms adopt IndexNow, reported planned integrations by Wix, Duda, Botify, Oncrawl, Onely, and Yext, and stated that large websites using the Bing Webmaster URL submission API, including eBay, LinkedIn, MSN, GitHub, and Bizapedia, planned to migrate to IndexNow.[6] On May 19, 2025, Microsoft Bing reported that Shopify and digital marketing and CMS provider Milestone Inc. had integrated IndexNow.[9] Website owners can check receipt of submitted URLs through the Bing Webmaster Tools portal.[7]

## IndexNow protocol limits, non-participation, and relationship to sitemaps

IndexNow operates as a voluntary URL notification signal whose practical scope is bounded by search engine participation, crawl quotas, submission limits, and sponsor terms.[2][3][4][5][7]

Participation in IndexNow is limited to the services registered in the protocol. As of 2026-11-23, `indexnow.org/searchengines.json` lists seven participating endpoints: Bing, Yandex, Seznam, Naver, Yep, Internet Archive, and Amazonbot.[4] Because automatic URL sharing applies only among participating search engines, search engines absent from that registry do not receive IndexNow notifications through the protocol.[2][4] Under the IndexNow.org Terms of Service, each sponsor reserves the right to change the specification without notice, to use or discontinue IndexNow on any product or service at any time, and bears no obligation to read or index submitted URLs.[5]

Receiving an HTTP `200` response from an IndexNow endpoint confirms only that the endpoint received the submitted URL or URL list.[2] Both the IndexNow FAQ and Bing Webmaster Tools state that submitting a URL does not guarantee crawling or indexing.[3][7] Search engines evaluate each submitted URL using their own crawl quotas, scheduling logic, and quality signals, and every crawl triggered through IndexNow counts toward the website's crawl quota.[3][7]

IndexNow also enforces batch and rate constraints. A single POST request is capped at 10,000 URLs as of 2026-11-23, and excessive or repetitive submissions can trigger HTTP `429` rate limiting.[2][3] The IndexNow FAQ advises submitting only meaningful content changes, waiting at least 5 minutes before resubmitting the same URL, and submitting user-generated content such as reviews, comments, or forum posts incrementally (for example, each review from 1 to 20, every 5th up to 100, and every 10th up to 1,000).[3]

IndexNow is designed to complement [XML sitemaps](https://mimirwiki.com/wiki/sitemaps) and is intended for URLs added, updated, or deleted after a site enables the protocol.[3][7] The IndexNow FAQ states that sites should avoid retroactive submission of older changes or submitting an entire site at once outside major events such as a migration or redesign, and should continue maintaining XML sitemaps with accurate `lastmod` timestamps to provide a complete URL inventory and support discovery of infrequently updated pages.[3]

## Frequently asked questions

### What is IndexNow?

IndexNow is a free, open HTTP protocol launched by Microsoft Bing and Yandex on October 18, 2021 that lets website owners notify participating search engines when URLs are added, updated, or deleted. Submitting a URL to one participating endpoint automatically shares that notification with all other participating search engines. [1][2][6][8]

### Which search engines participate in IndexNow?

As of 2026-11-23, the official registry at indexnow.org/searchengines.json lists seven participating endpoints: Bing, Yandex, Seznam, Naver, Yep, Internet Archive, and Amazonbot. Search engines outside this registry do not receive URL notifications through IndexNow. [2][4]

### How many URLs can be submitted in one IndexNow request?

As of 2026-11-23, IndexNow supports submitting one URL per HTTP GET request or up to 10,000 URLs in a single UTF-8 JSON HTTP POST request. Submitting more than 10,000 URLs in one POST payload can cause the request to fail or return HTTP 422 (Unprocessable Entity). [2][3]

### How does IndexNow verify website ownership?

For manual setup, a site owner creates an API key of 8 to 128 characters (a-z, A-Z, 0-9, and hyphens) and hosts it in a UTF-8 text file named {your-key}.txt at the site root. Alternatively, the key file can be hosted in a publicly accessible subfolder if its URL is supplied in the keyLocation parameter, which limits valid submissions to URLs under that directory. [2][3]

### Does an HTTP 200 response from IndexNow guarantee crawling or indexing?

No. An HTTP 200 response confirms only that the search engine received the submitted URL or batch. Search engines still apply their own crawl quotas, scheduling logic, and quality signals, and every resulting crawl counts toward the site's crawl quota. [2][3][7]

### Does IndexNow replace XML sitemaps?

No. IndexNow documentation states that websites should use IndexNow alongside XML sitemaps. IndexNow notifies search engines of recent URL additions, updates, and deletions, while XML sitemaps with lastmod values provide a complete site inventory and surface older or infrequently changing pages. [3]

## Quotable sentences

- Microsoft Bing and Yandex announced the IndexNow protocol on October 18, 2021. [6]
- The IndexNow protocol specification on IndexNow.org is licensed under Creative Commons Attribution-ShareAlike 4.0 by sponsors Microsoft Corporation, Yandex N.V., and Seznam.cz, a.s. [5]
- As of 2026-11-23, IndexNow accepts up to 10,000 URLs in a single HTTP POST JSON request. [2][3]
- As of 2026-11-23, an IndexNow API key must be between 8 and 128 characters long using lowercase letters, uppercase letters, digits, and hyphens. [2][3]
- As of 2026-11-23, indexnow.org/searchengines.json lists seven participating endpoints: Bing, Yandex, Seznam, Naver, Yep, Internet Archive, and Amazonbot. [4]
- On November 30, 2021, Cloudflare announced IndexNow support in Crawler Hints and made Crawler Hints generally available free of charge to Cloudflare customers. [10]
- An HTTP 200 response from an IndexNow endpoint confirms receipt of the submitted URLs only and does not guarantee crawling or indexing. [2][3][7]

## Timeline

- 2021-10-18: Microsoft Bing and Yandex announce the IndexNow URL notification protocol. [6]
- 2021-11-30: Cloudflare adds IndexNow support to Crawler Hints and makes Crawler Hints generally available free of charge to all Cloudflare customers. [10]
- 2025-05-19: Microsoft Bing reports IndexNow support on Shopify and Milestone Inc. and announces that Amazon plans to begin adopting IndexNow in mid-June 2025. [9]

## Sources

1. Home | IndexNow.org. IndexNow. https://www.indexnow.org/ (checked 2026-11-23; tier 3: official site)
2. Documentation | IndexNow.org. IndexNow. https://www.indexnow.org/documentation (checked 2026-11-23; tier 3: official site)
3. FAQ | IndexNow.org. IndexNow. https://www.indexnow.org/faq (checked 2026-11-23; tier 3: official site)
4. IndexNow Participating Search Engines JSON. IndexNow. https://www.indexnow.org/searchengines.json (checked 2026-11-23; tier 3: official site)
5. Terms | IndexNow.org. IndexNow. https://www.indexnow.org/terms (checked 2026-11-23; tier 3: official site)
6. IndexNow – Instantly Index your web content in Search Engines |.... Microsoft Bing Webmaster Blog. published 2021-10-18. https://blogs.bing.com/webmaster/2021/10/IndexNow-Instantly-Index-your-web-content-in-Search-Engines/ (checked 2026-11-23; tier 3: official site)
7. How to add IndexNow to your website | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow/getstarted (checked 2026-11-23; tier 3: official site)
8. Why IndexNow | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow (checked 2026-11-23; tier 3: official site)
9. IndexNow Drives Smarter and Faster Content Discovery | Bing.... Microsoft Bing Webmaster Blog. published 2025-05-19. https://blogs.bing.com/webmaster/2025/5/IndexNow-Drives-Smarter-and-Faster-Content-Discovery/ (checked 2026-11-23; tier 3: official site)
10. Cloudflare Supports IndexNow via one-click Integration | Bing.... Microsoft Bing Webmaster Blog. published 2021-11-30. https://blogs.bing.com/webmaster/2021/11/Cloudflare-Supports-IndexNow-via-one-click-Integration/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "IndexNow." Version 445adc69, 2026-11-23. https://mimirwiki.com/wiki/indexnow
