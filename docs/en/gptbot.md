---
title: "GPTBot"
subtitle: "OpenAI's automated web crawler used to collect training data for generative AI foundation models"
canonical_url: https://mimirwiki.com/wiki/gptbot
language: en
page_class: entity
revision_sha256: 103a9e90b01bc37f0f58970c706356df5ac7f39009e522fa9935a1685cf0213f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/wiki/gptbot.md
  txt: https://mimirwiki.com/wiki/gptbot.txt
  json: https://mimirwiki.com/wiki/gptbot.json
  jsonld: https://mimirwiki.com/wiki/gptbot.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/gptbot
---

# GPTBot

> As of late 2026, GPTBot identifies itself via the User-Agent token GPTBot/1.4 (+https://openai.com/gptbot) and publishes its verifiable egress IPv4 prefixes at openai.com/gptbot.json (18 CIDR blocks as of September 22, 2026). Website operators can independently block model-training scraping via robots.txt (RFC 9309) by disallowing GPTBot while allowing OAI-SearchBot (39 IPv4 blocks) to remain visible in ChatGPT search results, alongside emerging IETF AI Preferences (aipref) and Web Bot Auth cryptographic signature standards.

GPTBot is the primary automated web crawler operated by OpenAI to discover and fetch public web content that may be used to train generative artificial intelligence foundation models. It operates alongside three distinct OpenAI user agents with separate functional roles: OAI-SearchBot (for ChatGPT search indexing), OAI-AdsBot (for advertising landing-page verification), and ChatGPT-User (for real-time user-initiated browsing and custom GPT actions).

**Also known as:** GPTBot/1.4, OAI-SearchBot, OAI-AdsBot, ChatGPT-User

## Key facts

- **Operator:** OpenAI (OpenAI OpCo, LLC) [1]
- **Current User-Agent Token:** GPTBot/1.4 (+https://openai.com/gptbot) (as of 2026-11-23) [1]
- **Published IP Ranges:** 18 IPv4 CIDR prefixes in openai.com/gptbot.json (updated 2026-09-22) (as of 2026-11-23) [2]
- **Companion OpenAI Agents:** OAI-SearchBot/1.4 (search), OAI-AdsBot/1.0 (ads), ChatGPT-User/1.0 (user actions) (as of 2026-11-23) [1]

## Basic facts

- **Operator:** OpenAI [1]
- **Primary Function:** Crawling public web content for generative AI foundation model training [1]
- **User-Agent String:** Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot) [1]
- **IP Verification Manifest:** https://openai.com/gptbot.json (18 IPv4 prefixes as of 2026-09-22) [2]
- **Search Companion Crawler:** OAI-SearchBot/1.4 (https://openai.com/searchbot.json, 39 IPv4 prefixes) [1]
- **Exclusion Protocol:** Robots Exclusion Protocol (IETF RFC 9309 / robots.txt) [5]
- **Emerging Standards:** IETF AI Preferences (aipref) and IETF Web Bot Auth (webbotauth) [6]

## Overview and OpenAI Crawler Taxonomy

Introduced by OpenAI in August 2023 and iterated through version 1.4 in 2026, **GPTBot** is OpenAI's dedicated web crawler for collecting public internet text and media used to train and improve generative AI foundation models [1]. Because website publishers frequently wish to distinguish between training-data ingestion, search-engine indexing, advertising compliance checks, and live user-triggered page fetches, OpenAI separates its automated HTTP traffic into four distinct user agents with independent `robots.txt` controls and IP manifests [1]:

| User-Agent Token | Current Version | Purpose & Model Training Policy | IP Manifest URL |
| --- | --- | --- | --- |
| `GPTBot` | `GPTBot/1.4` | Crawls content potentially used to train OpenAI generative AI foundation models. Avoids paywalls, PII-heavy sources, and policy-violating content [1]. | `https://openai.com/gptbot.json` (18 IPv4 prefixes as of 2026-09-22) [2] |
| `OAI-SearchBot` | `OAI-SearchBot/1.4` | Indexes websites to surface links and summaries in ChatGPT search features. **Not** used to train OpenAI foundation models [1]. | `https://openai.com/searchbot.json` (39 IPv4 prefixes as of 2026-01-02) [3] |
| `OAI-AdsBot` | `OAI-AdsBot/1.0` | Inspects advertiser landing pages for quality, safety, and policy verification. **Not** used to train foundation models [1]. | Published via OpenAI crawler documentation [1] |
| `ChatGPT-User` | `ChatGPT-User/1.0` | Triggered on behalf of a live human user asking ChatGPT or a Custom GPT to fetch a specific webpage. **Not** used for passive foundation model training [1]. | `https://openai.com/chatgpt-user.json` (updated 2026-11-06) [4] |

The full HTTP `User-Agent` header sent by GPTBot in late 2026 is `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot)` [1].

## Robots.txt Opt-Out and Granular Access Control

GPTBot adheres to the Robots Exclusion Protocol standardized in **IETF RFC 9309** [1][5]. Site administrators can block GPTBot from scraping an entire domain - or restrict it to specific directory paths - by adding `User-agent: GPTBot` rules to their site's `/robots.txt` file [1][5].

Because OpenAI decouples training crawls from search indexing, a publisher that wants to opt out of AI model training while still appearing as a cited link in ChatGPT Search can disallow `GPTBot` while explicitly allowing `OAI-SearchBot` [1]:

```text User-agent: GPTBot Disallow: /

User-agent: OAI-SearchBot Allow: / ```

OpenAI notes that after a site updates its `robots.txt` rules, it may take approximately 24 hours for OpenAI's distributed crawler fleet to refresh its cached `robots.txt` policy and cease requests [1].

## IP Verification and Cryptographic Web Bot Authentication

Because third-party scrapers routinely spoof the `GPTBot` User-Agent string in HTTP headers, relying solely on the `User-Agent` header is insufficient for firewall enforcement or analytics [1][8]. OpenAI publishes machine-readable JSON prefix manifests so network operators and content delivery networks (CDNs) can verify authentic traffic at the IP layer [1][2][3][4]: - **`gptbot.json`**: Contains 18 IPv4 CIDR blocks (such as `20.171.206.0/24`, `52.230.152.0/24`, `20.168.17.192/28`, `172.182.202.0/25`, `172.182.204.0/24`, and `172.182.214.0/24`) as of the `2026-09-22T00:00:00Z` creation timestamp [2]. - **`searchbot.json`**: Contains 39 IPv4 CIDR blocks as of `2026-01-02T07:01:00.000000Z` [3]. - **`chatgpt-user.json`**: Contains dozens of regional egress IPv4 CIDR blocks updated as of `2026-11-06T00:00:00Z` [4].

Beyond IP allowlisting, edge security providers such as Cloudflare and the **IETF Web Bot Auth (`webbotauth`) Working Group** have introduced cryptographic HTTP Message Signatures (based on RFC 9421) for automated agents [7][8]. Through cryptographic bot authentication, verified crawlers and AI agents attach a `Signature` and `Signature-Input` header signed with a published Ed25519 or RSA key directory, allowing origin servers and WAFs to mathematically verify bot identity without fragile IP range lookups [7][8].

## IETF AI Preferences (aipref) and Web Ecosystem Impact

The rapid expansion of AI training crawlers led to significant debate over whether `robots.txt` - originally designed in 1994 to prevent search crawlers from overloading servers while conferring reciprocal search traffic - is adequate for expressing copyright and machine-learning usage policies [5][6].

To address this gap, the **IETF AI Preferences (`aipref`) Working Group** was chartered to standardize machine-readable vocabulary and attachment mechanisms for expressing how digital content may or may not be used by AI systems [6]. The working group's active specifications, including `draft-ietf-aipref-vocab` (A Vocabulary For Expressing AI Usage Preferences) and `draft-ietf-aipref-attach` (mechanisms for attaching preferences via `robots.txt` extensions and HTTP `Content-Usage` headers), distinguish between general automated processing, foundation model training (`train-ai` / `ai`), and search or inference grounding [6]. Meanwhile, network telemetry from Cloudflare's AI traffic reports indicates that `GPTBot` consistently ranks among the highest-volume AI crawlers globally alongside bytespider, ClaudeBot, and Google-Extended, driving widespread adoption of managed AI crawl controls and pay-per-crawl architectures [8].

## Frequently asked questions

### What is the difference between GPTBot and OAI-SearchBot?

GPTBot (GPTBot/1.4) crawls public web pages to collect training data for OpenAI's generative AI foundation models. OAI-SearchBot (OAI-SearchBot/1.4) crawls websites solely to index and link to them inside ChatGPT's search features and is not used to train OpenAI's foundation models. [1]

### How can a website block GPTBot without losing visibility in ChatGPT Search?

A site administrator can add 'User-agent: GPTBot' followed by 'Disallow: /' in the root /robots.txt file while adding 'User-agent: OAI-SearchBot' followed by 'Allow: /'. This prevents OpenAI from scraping the site for model training while allowing pages to be indexed and cited in ChatGPT search responses. [1][5]

### How can server administrators verify that a GPTBot request is genuinely from OpenAI?

Administrators should match the request's source IP address against the official CIDR blocks published by OpenAI at https://openai.com/gptbot.json (which lists 18 IPv4 prefixes as of September 2026), or use CDN Verified Bot checks and HTTP Message Signatures standardized under the IETF Web Bot Auth framework. [1][2][7][8]

### What is ChatGPT-User and why does it behave differently from GPTBot?

ChatGPT-User (ChatGPT-User/1.0) is invoked when a human user actively asks ChatGPT or a Custom GPT action to visit a specific URL in real time. Its egress IPs are published separately at https://openai.com/chatgpt-user.json and its requests are not used for passive foundation model training. [1][4]

### What IETF standards govern AI web crawlers like GPTBot?

GPTBot's robots.txt compliance is governed by IETF RFC 9309 (Robots Exclusion Protocol). In addition, the IETF AI Preferences (aipref) Working Group develops standardized vocabularies (draft-ietf-aipref-vocab) and HTTP/robots attachment rules for expressing AI training opt-outs, while the IETF Web Bot Auth (webbotauth) Working Group standardizes cryptographic bot authentication. [5][6][7]

## Quotable sentences

- OpenAI separates its web traffic across four distinct user agents: GPTBot/1.4 (model training), OAI-SearchBot/1.4 (search indexing), OAI-AdsBot/1.0 (ad landing page verification), and ChatGPT-User/1.0 (user-triggered requests). [1]
- OpenAI's official IP manifest for GPTBot (https://openai.com/gptbot.json) lists 18 IPv4 CIDR prefixes as of its September 22, 2026 update. [2]
- OpenAI's official IP manifest for OAI-SearchBot (https://openai.com/searchbot.json) lists 39 IPv4 CIDR prefixes as of its January 2, 2026 update. [3]
- Disallowing GPTBot in robots.txt prevents OpenAI from crawling a site for foundation model training while allowing OAI-SearchBot preserves indexing in ChatGPT search results. [1][5]
- The IETF AI Preferences (aipref) Working Group develops draft-ietf-aipref-vocab and draft-ietf-aipref-attach to standardize machine-readable AI training and usage preferences. [6]

## Timeline

- 2022-09: IETF publishes RFC 9309, formally standardizing the Robots Exclusion Protocol (robots.txt). [5]
- 2023-08: OpenAI launches GPTBot with robots.txt opt-out controls and published egress IP ranges. [1]
- 2024-07: OpenAI introduces OAI-SearchBot to separate search indexing from GPTBot foundation model training crawls. [1]
- 2026-01-02: OpenAI updates searchbot.json to 39 IPv4 CIDR blocks for OAI-SearchBot. [3]
- 2026-09-22: OpenAI updates gptbot.json to 18 IPv4 CIDR prefixes as GPTBot advances to user-agent version GPTBot/1.4. [1][2]
- 2026-11-06: OpenAI updates chatgpt-user.json egress IPv4 ranges for live user-initiated ChatGPT browsing actions. [4]

## Sources

1. Overview of OpenAI Crawlers (GPTBot/1.4, OAI-SearchBot/1.4, OAI-AdsBot/1.0, ChatGPT-User/1.0). OpenAI Platform Documentation. https://platform.openai.com/docs/bots (checked 2026-11-23; tier 3: official site)
2. OpenAI GPTBot Official IPv4 CIDR Prefix Manifest (gptbot.json). OpenAI. published 2026-09-22. https://openai.com/gptbot.json (checked 2026-11-23; tier 3: official site)
3. OpenAI OAI-SearchBot Official IPv4 CIDR Prefix Manifest (searchbot.json). OpenAI. published 2026-01-02. https://openai.com/searchbot.json (checked 2026-11-23; tier 3: official site)
4. OpenAI ChatGPT-User Official IPv4 CIDR Prefix Manifest (chatgpt-user.json). OpenAI. published 2026-11-06. https://openai.com/chatgpt-user.json (checked 2026-11-23; tier 3: official site)
5. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309 (checked 2026-11-23; tier 1: government or public registry)
6. IETF AI Preferences (aipref) Working Group Charter and Active Drafts (draft-ietf-aipref-vocab, draft-ietf-aipref-attach). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (checked 2026-11-23; tier 1: government or public registry)
7. IETF Web Bot Auth (webbotauth) Working Group Charter. Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (checked 2026-11-23; tier 1: government or public registry)
8. From Googlebot to GPTBot: Who's Crawling Your Site and Cryptographic Bot Verification. Cloudflare. published 2025-05. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "GPTBot." Version 103a9e90, 2026-11-23. https://mimirwiki.com/wiki/gptbot
