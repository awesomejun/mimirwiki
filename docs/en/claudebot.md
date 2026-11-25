---
title: "ClaudeBot"
subtitle: "Web crawler operated by Anthropic to collect public web content for AI model training"
canonical_url: https://mimirwiki.com/wiki/claudebot
language: en
page_class: entity
revision_sha256: 4a0a87250a74179b0e86a7ab552c43970d5dd7724a5d8e912840e606f100ffab
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/claudebot.md
  txt: https://mimirwiki.com/wiki/claudebot.txt
  json: https://mimirwiki.com/wiki/claudebot.json
  jsonld: https://mimirwiki.com/wiki/claudebot.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/claudebot
  ja: https://mimirwiki.com/ja/wiki/claudebot
  zh: https://mimirwiki.com/zh/wiki/claudebot
  es: https://mimirwiki.com/es/wiki/claudebot
---

# ClaudeBot

> ClaudeBot is the training web crawler operated by Anthropic to collect public web content for generative AI models. Anthropic separates it from Claude-SearchBot for search indexing and Claude-User for user-initiated requests. Site owners can block or throttle ClaudeBot via robots.txt, and as of October 30, 2026 Anthropic also recognizes a draft IETF aipref training preference signal.

ClaudeBot is an automated web crawler operated by Anthropic to collect publicly available web content that may contribute to training its generative AI models, including Claude. Anthropic documents ClaudeBot alongside two separate web robots: Claude-SearchBot for search indexing and Claude-User for retrieving pages in response to user-initiated queries. Website owners can restrict or rate-limit ClaudeBot through robots.txt directives defined under RFC 9309, including the non-standard Crawl-delay extension, and as of October 30, 2026 Anthropic began recognizing a machine-readable no-AI-training preference signal based on draft IETF aipref work. Website operators reported heavy request volumes from ClaudeBot in 2024, and Anthropic's November 17, 2026 Form S-1/A-3 filing discloses ongoing litigation over its web crawling practices.

**Also known as:** Anthropic web crawler, ClaudeBot crawler

## Key facts

- **Operator:** Anthropic (as of 2026-11-23) [4]
- **Product token:** ClaudeBot (as of 2026-11-23) [4]
- **Stated purpose:** Collecting public web content for generative AI model training (as of 2026-11-23) [4]
- **Companion bots:** Claude-SearchBot (search indexing) and Claude-User (user-initiated page fetches) (as of 2026-11-23) [4]
- **Opt-out controls:** robots.txt directives, Crawl-delay extension, and draft IETF aipref preference signal (since 2026-10-30) (as of 2026-11-23) [4]

## Basic facts

- **Name:** ClaudeBot [4]
- **Type:** Automated web crawler (training crawler) [4]
- **Operator:** Anthropic (as of 2026-11-23) [4]
- **Operator legal entity:** Anthropic, PBC (Delaware public benefit corporation, San Francisco, California) (as of 2026-11-17) [2]
- **Product token:** ClaudeBot (as of 2026-11-23) [4]
- **Stated purpose:** Collecting publicly available web content for AI model training (as of 2026-11-23) [4]
- **Companion Anthropic bots:** Claude-SearchBot (search indexing), Claude-User (user-directed retrieval) (as of 2026-11-23) [4]
- **Exclusion protocol:** Robots Exclusion Protocol (robots.txt, IETF RFC 9309) [1]
- **Rate-limit directive:** Crawl-delay (non-standard robots.txt extension) (as of 2026-11-23) [4]
- **Training preference signal:** Draft IETF aipref no-AI-training signal (recognized since 2026-10-30) (as of 2026-11-23) [4]
- **Anti-circumvention policy:** Does not attempt to bypass CAPTCHAs on crawled sites (as of 2026-11-23) [4]
- **Privacy documentation:** Anthropic Privacy Policy (effective 2026-09-10) and separate Non-User Privacy Policy (as of 2026-09-10) [5]
- **Published IP list URL:** https://claude.com/crawling/bots.json (14 IPv4 prefixes, creationTime 2026-10-20T00:00:00Z) (as of 2026-11-23) [10]

## ClaudeBot and Anthropic's web robot suite

ClaudeBot is the training web crawler operated by [Anthropic](https://mimirwiki.com/wiki/anthropic) as part of a three-robot system for gathering web content, indexing search results, and fetching pages for [Claude](https://mimirwiki.com/wiki/claude) users.[4] As of 2026-11-23, Anthropic's crawler documentation separates automated access into three named robots so website owners can set distinct access policies for model training, search indexing, and user-initiated retrieval.[4]

| Bot | Stated function | Effect of disabling via robots.txt |
| --- | --- | --- |
| ClaudeBot | Collects web content that may contribute to training generative AI models | Signals that future materials from the site should be excluded from Anthropic AI model training datasets |
| Claude-SearchBot | Navigates and analyzes web content to improve search result relevance and accuracy | Prevents indexing of site content for search optimization, which may reduce visibility and accuracy in user search results |
| Claude-User | Accesses websites in response to questions asked by Claude users | Prevents retrieval of site content in response to user queries, which may reduce visibility for user-directed web search |

Anthropic distinguishes these three crawlers and fetchers from Anthropic-hosted browsers that Claude uses to complete tasks on a user's behalf, including Claude-Agent in Claude Duet, which are documented separately.[4]

As of 2026-11-23, Anthropic lists four operational principles for its web robots.[4]

- Transparent identification through the three documented bot names
- Non-intrusive crawl pacing on individual domains, including respecting `Crawl-delay` where appropriate
- Honoring do-not-crawl directives published in `robots.txt`
- Respecting anti-circumvention technologies, including refraining from bypassing CAPTCHAs on crawled sites

## ClaudeBot controls under robots.txt and IETF aipref

ClaudeBot follows site-level access directives published in [robots.txt](https://mimirwiki.com/wiki/robots-txt), the text file standardized by the Internet Engineering Task Force (IETF) in RFC 9309.[1][4] Published in September 2022, RFC 9309 specifies and extends the Robots Exclusion Protocol originally defined by Martijn Koster in 1994.[1] Under RFC 9309, a `robots.txt` file organizes `allow` and `disallow` rules into groups headed by `user-agent` product tokens containing only ASCII letters, underscores, and hyphens, which crawlers match case-insensitively before falling back to the wildcard group `user-agent: *` if no specific group matches.[1] Path matching starts from the first octet of the URI path, should be case-sensitive, and applies the longest matching rule; RFC 9309 also notes explicitly that `robots.txt` rules are not a form of access authorization.[1]

To exclude ClaudeBot from an entire website, Anthropic's documentation as of 2026-11-23 instructs site owners to add `User-agent: ClaudeBot` and `Disallow: /` to the `robots.txt` file in the site's top-level directory and repeat the configuration on every subdomain they want to opt out.[4] To limit request frequency, Anthropic supports the non-standard `Crawl-delay` extension to `robots.txt` (for example, `User-agent: ClaudeBot` followed by `Crawl-delay: 1`).[1][4]

Anthropic states as of 2026-11-23 that opting out of crawling requires updating `robots.txt`.[4] Blocking the source IP addresses from which Anthropic bots operate can prevent the crawlers from reading a site's `robots.txt` file, so Anthropic notes that IP blocking may not work reliably or persistently guarantee an opt-out.[4] Anthropic publishes its crawler IP prefixes in JSON format at `https://claude.com/crawling/bots.json`; as of 2026-11-23, the file carries `creationTime` `2026-10-20T00:00:00Z` and lists 14 IPv4 prefixes, comprising `216.73.216.0/22` and 13 single-host `/32` addresses.[4][10]

On October 30, 2026, Anthropic began recognizing a machine-readable preference signal allowing website owners to express a "no AI training" setting.[4] The signal is based on draft work from the IETF `aipref` working group, and Anthropic states it is rolling out support globally across its services over time while noting that its interpretation may evolve alongside the draft standard.[4] For any given path, `robots.txt` rules that explicitly name `ClaudeBot` take precedence over the general preference signal, even if the general signal specifies a different setting; when `robots.txt` does not mention `ClaudeBot`, Anthropic applies the general preference setting.[4]

## ClaudeBot in Anthropic's training data and privacy policies

ClaudeBot collects publicly available web content that represents one category of training data described in Anthropic's Privacy Policy and securities filings.[2][4][5] Anthropic's Privacy Policy, effective September 10, 2026, enumerates six sources of data collected or received to train Anthropic models.[5]

- Publicly available information via the Internet
- Datasets obtained through commercial agreements with third-party businesses
- Data provided by users or crowd workers, including Inputs and Outputs from Anthropic Services unless users opt out through account settings
- Feedback explicitly provided by users about Anthropic Services
- Materials flagged for safety, security, or policy review
- Data generated internally by Anthropic

Anthropic's Privacy Policy states that it does not apply to content processed on behalf of business customers such as Enterprise accounts, which is governed by customer agreements, and directs readers to a separate Non-User Privacy Policy for information on how large language models are trained using third-party personal data and what choices apply to non-users.[5] Even when a consumer user opts out of model training through account settings, Anthropic states that Inputs and Outputs may still be used for model improvement if conversations are flagged for safety review or explicitly reported through feedback mechanisms.[5]

In Amendment No. 3 to Form S-1 filed with [SEC EDGAR](https://mimirwiki.com/wiki/sec-edgar) on November 17, 2026 (Registration No. 333-299633), Anthropic, PBC states that it uses publicly available internet information, licensed or commissioned third-party datasets, and synthetic data generated by its own models across both pre-training and post-training stages of model development.[2] The filing identifies web scraping or web crawling techniques, book scanning, and other methods as ways Anthropic collects publicly available information.[2] Anthropic states in the same filing that while it takes steps designed to comply with applicable law, `robots.txt` notices, and technical measures such as paywalls or logins, those efforts may not always succeed, and Anthropic may be unable to verify whether collected material is protected under privacy, copyright, or other intellectual property laws.[2]

## ClaudeBot and Cloudflare AI crawler controls

ClaudeBot operates within a broader web infrastructure environment where network providers such as [Cloudflare](https://mimirwiki.com/wiki/cloudflare) classify automated traffic and offer site owners granular controls over AI crawlers.[6][7] In a July 1, 2025 traffic analysis covering May 2024 to May 2025, Cloudflare reported that AI and search crawler traffic increased 18%, with [OpenAI](https://mimirwiki.com/wiki/openai)'s [GPTBot](https://mimirwiki.com/wiki/gptbot) growing 305% and Googlebot growing 96%.[9]

On July 1, 2026, Cloudflare introduced AI traffic options across all customer plans so website owners can distinguish and manage Search, Agent, and Training traffic separately.[7] On the same date, Cloudflare updated its BotBase taxonomy so that every tracked bot is classified by behavior and by operator access type, replacing the prior separation between Verified bots and signed agents with a `Direct` versus `Intermediary` access field.[6]

| BotBase classification dimension | Category | Cloudflare definition (documentation updated 2026-11-12) |
| --- | --- | --- |
| Behavior (managed AI preset) | Training | Crawling to train or fine-tune models |
| Behavior (managed AI preset) | Search | Crawling to build search indexes or RAG databases |
| Behavior (managed AI preset) | Agent | User-directed agents visiting a page on behalf of a human |
| Operator access label | Direct | Operated by a single, narrow operator, usually on its own infrastructure |
| Operator access label | Intermediary | Agentic service driven by many end users, introducing transitive trust |

Under Cloudflare's Verified bots documentation (last updated November 12, 2026), Verified status requires deterministic self-identification through cryptographic [Web Bot Auth](https://mimirwiki.com/wiki/web-bot-auth) signatures, a published IP list with a stable user-agent, or reverse DNS, paired with non-abusive behavior that honors `robots.txt` and crawl directives at reasonable request rates.[6] Legacy WAF categories such as `AI Crawler`, `AI Search`, and `AI Assistant` remain available for backward compatibility alongside the updated taxonomy.[6] Cloudflare lists failing to respect the `crawl-delay` directive in `robots.txt` as a policy breach that can remove an AI crawler from its global allowlist, and notes that repeated violations or inconsistent compliance across an organization's bots can result in revoking Verified status for all bots operated by that organization.[6]

On September 15, 2026, Cloudflare also announced a Disallow AI Training setting and an Accountable designation that let website owners stay indexed for search while disallowing AI training, and stated that Apple, Google, and Microsoft honor or have committed to honor the setting.[8]

## ClaudeBot publisher reports and scraping litigation

ClaudeBot has drawn public operational reports from website administrators regarding high request volumes, while Anthropic's broader web crawling practices have become the subject of legal proceedings.[2][3] On July 25, 2024, *The Verge* reported that iFixit CEO Kyle Wiens stated ClaudeBot had sent nearly one million requests to iFixit's servers within a 24-hour period, triggering operational alarms and requiring intervention from iFixit's DevOps team.[3]

iFixit's Terms of Use prohibited reproducing, copying, or distributing site content without express prior written permission, specifically including machine learning or AI model training.[3] When questioned by 404 Media, Anthropic linked to its FAQ page indicating its crawler is blocked through `robots.txt`.[3] After iFixit added a `crawl-delay` rule to its `robots.txt` file, Wiens told *The Verge* that server logs showed ClaudeBot had stopped, and Anthropic spokesperson Jennifer Martinez stated that Anthropic respects `robots.txt` and that its crawler honored the signal once iFixit implemented it.[3]

In the same July 2024 discussion thread started by Wiens on X, Read the Docs co-founder Eric Holscher and Freelancer.com CEO Matt Barrie stated that their websites had also experienced heavy scraping from Anthropic's crawler.[3] *The Verge* also noted that in April 2024, the Linux Mint web forum attributed a site outage to server strain caused by ClaudeBot's scraping activity.[3]

In Amendment No. 3 to Form S-1 filed on November 17, 2026, Anthropic, PBC disclosed that its scraping, web crawling, and data collection activities have resulted in and remain the subject of litigation alleging violations of law.[2] Specifically, the filing cites `Reddit, Inc. v. Anthropic PBC`, in which Reddit alleged Anthropic improperly accessed posts stored on Reddit's platform in violation of Reddit's legal rights.[2] Anthropic filed a notice of removal to federal court on July 3, 2025, the case was remanded to state court on March 30, 2026, and the lawsuit remained pending as of November 17, 2026.[2] Anthropic also disclosed as a business risk that an unfavorable settlement or judgment in crawling litigation could require discontinuing certain scraping or crawling techniques, developing alternative data collection methods, or paying substantial sums.[2]

## Frequently asked questions

### What is ClaudeBot used for?

As of 2026-11-23, Anthropic uses ClaudeBot to collect publicly available web content that may contribute to training its generative AI models. Anthropic operates Claude-SearchBot separately for search indexing and Claude-User for fetching web pages in response to user queries. [4]

### How can website owners block or rate-limit ClaudeBot?

Website owners can block ClaudeBot by adding User-agent: ClaudeBot and Disallow: / to the top-level robots.txt file on each domain and subdomain they want to exclude. Site owners can also throttle crawl frequency with the non-standard Crawl-delay extension, and as of October 30, 2026 Anthropic recognizes a draft IETF aipref no-AI-training preference signal. [1][4]

### Does blocking ClaudeBot stop Claude from fetching pages during a user conversation?

No. Restricting ClaudeBot signals that future site content should be excluded from Anthropic's AI model training datasets. User-initiated page retrieval uses Claude-User and search indexing uses Claude-SearchBot, allowing site owners to configure separate robots.txt rules for each bot. [4]

### Why does Anthropic advise against blocking ClaudeBot by IP address alone?

As of 2026-11-23, Anthropic's crawler documentation states that blocking the IP addresses used by its bots impedes the crawlers from reading a site's robots.txt file, so IP blocking may not work reliably or persistently guarantee an opt-out. Anthropic publishes a list of source IP addresses so administrators can verify whether a crawler comes from Anthropic. [4]

### How does Cloudflare categorize training crawlers such as ClaudeBot?

Under the BotBase taxonomy introduced on July 1, 2026, Cloudflare classifies bots by behaviors including Training for model training or fine-tuning, Search for search indexes or RAG databases, and Agent for user-directed browsing, with managed presets across all plans. Cloudflare also requires Verified bots to identify themselves deterministically and honor robots.txt directives, including crawl-delay. [6][7]

### What web crawling litigation has Anthropic disclosed in SEC filings?

In Amendment No. 3 to Form S-1 filed with the SEC on November 17, 2026, Anthropic, PBC disclosed pending litigation in Reddit, Inc. v. Anthropic PBC alleging improper access to posts stored on Reddit's platform. Anthropic filed a notice of removal to federal court on July 3, 2025, and the case was remanded to state court on March 30, 2026. [2]

## Quotable sentences

- As of 2026-11-23, Anthropic documents three web robots: ClaudeBot for AI model training data collection, Claude-SearchBot for search indexing, and Claude-User for user-initiated page fetches. [4]
- As of 2026-11-23, Anthropic states that its web bots honor robots.txt directives, support the non-standard Crawl-delay extension, and do not attempt to bypass CAPTCHAs. [4]
- As of October 30, 2026, Anthropic began recognizing a machine-readable no-AI-training preference signal based on draft work by the IETF aipref working group, with explicit ClaudeBot robots.txt rules taking priority. [4]
- RFC 9309, published by the IETF in September 2022, specifies the Robots Exclusion Protocol and states that robots.txt rules are not a form of access authorization. [1]
- In July 2024, iFixit CEO Kyle Wiens reported that ClaudeBot sent almost one million requests to iFixit servers within 24 hours and stopped after iFixit added a crawl-delay directive to robots.txt. [3]
- Anthropic's Privacy Policy, effective September 10, 2026, lists publicly available internet information among six data sources used to train Anthropic models. [5]
- In Amendment No. 3 to Form S-1 filed with the SEC on November 17, 2026, Anthropic, PBC disclosed that Reddit, Inc. v. Anthropic PBC remained pending after being remanded to state court on March 30, 2026. [2]
- Cloudflare's July 1, 2025 crawler analysis reported that AI and search crawler traffic increased 18% between May 2024 and May 2025, with GPTBot traffic rising 305% and Googlebot traffic rising 96%. [9]

## Timeline

- 2022-09: The IETF publishes RFC 9309, standardizing the Robots Exclusion Protocol (robots.txt). [1]
- 2024-04: The Linux Mint web forum attributes a site outage to server strain from ClaudeBot scraping activity. [3]
- 2024-07-25: The Verge reports that ClaudeBot sent almost one million requests to iFixit within 24 hours and stopped after iFixit added a crawl-delay directive to robots.txt. [3]
- 2025-07-01: Cloudflare publishes a crawler traffic analysis reporting an 18% rise in AI and search crawler traffic between May 2024 and May 2025, with GPTBot up 305% and Googlebot up 96%. [9]
- 2025-07-03: Anthropic files a notice of removal to federal court in Reddit, Inc. v. Anthropic PBC, a lawsuit alleging improper access to Reddit posts. [2]
- 2026-03-30: Reddit, Inc. v. Anthropic PBC is remanded from federal court to state court. [2]
- 2026-07-01: Cloudflare introduces separate Search, Agent, and Training traffic options for all customers and adds Direct versus Intermediary access labels in BotBase. [6][7]
- 2026-09-10: Anthropic's updated Privacy Policy takes effect, listing publicly available internet information among six sources of model training data. [5]
- 2026-09-15: Cloudflare announces a Disallow AI Training setting and an Accountable designation for staying indexed for search while disallowing AI training, and states that Apple, Google, and Microsoft honor or have committed to honor the setting. [8]
- 2026-10-30: Anthropic begins recognizing a machine-readable no-AI-training preference signal based on draft work by the IETF aipref working group. [4]
- 2026-11-17: Anthropic, PBC files Amendment No. 3 to Form S-1 with the SEC, disclosing web crawling methods, robots.txt compliance limitations, and pending crawling litigation. [2]

## Sources

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (checked 2026-11-23; tier 1: government or public registry)
2. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). published 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (checked 2026-11-23; tier 1: government or public registry)
3. Anthropic’s crawler is ignoring websites’ anti-AI scraping policies | The Verge. The Verge. published 2024-07-25. https://www.theverge.com/2024/7/25/24205943/anthropic-ai-web-crawler-claudebot-ifixit-scraping-training-data (checked 2026-11-23; tier 2: academic or news)
4. Does Anthropic crawl data from the web, and how can site owners block the crawler? | Claude Help Center. Anthropic. https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler (checked 2026-11-23; tier 3: official site)
5. Privacy Policy \ Anthropic. Anthropic. published 2026-09-10. https://www.anthropic.com/legal/privacy (checked 2026-11-23; tier 3: official site)
6. Verified bots · Cloudflare bot solutions docs. Cloudflare. published 2026-11-12. https://developers.cloudflare.com/bots/concepts/bot/verified-bots/ (checked 2026-11-23; tier 3: official site)
7. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. published 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (checked 2026-11-23; tier 3: official site)
8. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. published 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (checked 2026-11-23; tier 3: official site)
9. From Googlebot to GPTBot: Who’s crawling your site in 2025 | Cloudflare Blog. The Cloudflare Blog. published 2025-07-01. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (checked 2026-11-23; tier 3: official site)
10. Anthropic Crawler IP Prefixes (bots.json). Anthropic. published 2026-10-20. https://claude.com/crawling/bots.json (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "ClaudeBot." Version 4a0a8725, 2026-11-25. https://mimirwiki.com/wiki/claudebot
