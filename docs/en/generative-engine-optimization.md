---
title: "Generative Engine Optimization"
subtitle: "Methods and metrics for improving web content visibility and citation in generative AI search responses"
canonical_url: https://mimirwiki.com/wiki/generative-engine-optimization
language: en
page_class: concept
revision_sha256: eb2c50d03a2947df566831195ba71258dbc5d5a7c3a585b2a2a412f1b39551dd
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/wiki/generative-engine-optimization.md
  txt: https://mimirwiki.com/wiki/generative-engine-optimization.txt
  json: https://mimirwiki.com/wiki/generative-engine-optimization.json
  jsonld: https://mimirwiki.com/wiki/generative-engine-optimization.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/generative-engine-optimization
  ja: https://mimirwiki.com/ja/wiki/generative-engine-optimization
  zh: https://mimirwiki.com/zh/wiki/generative-engine-optimization
---

# Generative Engine Optimization

> Generative Engine Optimization (GEO) is a set of content and structural methods aimed at increasing the visibility and citation of web sources in answers produced by AI search systems. Coined in November 2023 by Aggarwal et al. with the GEO-bench benchmark, GEO addresses multistage retrieval and generation pipelines, where measured effects depend on retrieval status and domain.

Generative Engine Optimization (GEO) is a web content optimization paradigm designed to increase the presence, citation likelihood, and prominence of source documents in answers synthesized by generative search engines. Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, and Ameet Deshpande formally introduced the term on November 16, 2023 in arXiv:2311.09735, which was accepted to the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD 2024). Conventional search engines return ranked lists of links, whereas generative engines retrieve web documents through search backends and use large language models to produce grounded natural language responses with embedded inline citations. A July 2026 critical survey describes GEO as a stochastic, partially observable pipeline spanning crawling and indexing, retrieval, reranking, citation, and fidelity, while Google Search Central documentation states as of 2026-11-23 that existing Search technical requirements and SEO fundamentals apply to its AI features without separate optimizations.

**Also known as:** GEO, Answer Engine Optimization, Conversational SEO

## Key facts

- **First proposed:** 2023-11-16 (arXiv:2311.09735; accepted to KDD 2024) [1]
- **Originating authors:** Aggarwal, Murahari, Rajpurohit, Kalyan, Narasimhan, and Deshpande [1]
- **Initial benchmark:** GEO-bench (10,000 queries across diverse domains) [2]
- **Foundational benchmark gains:** Up to 40% visibility increase in benchmark tests; up to 37% on Perplexity.ai (as of 2024-06-28) [2]
- **Google Search requirements:** No additional technical requirements or special optimizations beyond the Search technical requirements (as of 2026-11-23) [7]

## Basic facts

- **Type:** Information retrieval and web content optimization paradigm [1]
- **Abbreviation:** GEO [1]
- **First proposed:** 2023-11-16 (arXiv:2311.09735 v1) [1]
- **Conference publication:** 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '24), August 25-29, 2024 [2]
- **Originating authors:** Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, Ameet Deshpande [1]
- **Author affiliations:** Indian Institute of Technology Delhi; Princeton University; independent researchers [2]
- **Initial benchmark:** GEO-bench (10,000 multi-domain user queries) [2]
- **Surveyed literature corpus:** 45 studies from November 2023 through July 2026 (Martinez, 2026) (as of 2026-07-15) [5]
- **Structural optimization result:** 17.3% citation-rate gain and 18.5% subjective-quality gain across six engines (GEO-SFE) (as of 2026-03-31) [4]
- **Google Search guidance:** Standard SEO fundamentals and snippet eligibility apply to AI Overviews and AI Mode (as of 2026-11-23) [7]

## What Generative Engine Optimization is

Generative Engine Optimization (GEO) is a framework for improving how web content appears and receives attribution inside answers synthesized by generative search engines.[1][2] Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, and Ameet Deshpande coined the term in version 1 of their preprint `arXiv:2311.09735` on November 16, 2023, posted revision v3 on June 28, 2024, and published the work in the proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '24), held August 25-29, 2024 in Barcelona.[1][2] The authors were affiliated with the Indian Institute of Technology Delhi, Princeton University, and independent research roles in Seattle.[2]

The paper formalizes generative engines (GEs) as search systems that combine a search engine backend with multiple large language models (LLMs), citing BingChat, Google's SGE, and [Perplexity](https://mimirwiki.com/wiki/perplexity) (Perplexity.ai) as deployed examples.[2] Formally, a generative engine maps a user query and optional user personalization context to a natural language response through modular steps: a query-reformulation model expands the input query into sub-queries, a search engine retrieves ranked web sources, a summarization model condenses each source, and a response-generation model writes a structured answer with embedded inline citations.[2] Inline attribution gives users a mechanism to verify claims and counteracts LLM hallucination, evaluated in terms of citation recall (whether statements are supported by relevant citations) and citation precision (whether attached citations actually support the statements).[2]

Generative Engine Optimization addresses a structural concern for website owners and content publishers.[1][2] Direct synthesized answers reduce the need for users to click through to source websites, which can lower organic referral traffic, while proprietary generation pipelines limit creator visibility into how pages are ingested and cited.[2] Martinez's 2026 survey searched the literature under term families that included answer engine optimization, conversational SEO, AI search visibility, and citation absorption.[6]

## Generative Engine Optimization framework, metrics, and GEO-bench

Generative Engine Optimization (GEO) was initially formalized by Aggarwal et al. as a black-box optimization framework that takes a source web page as input and outputs a revised version with adjusted presentation, text style, and content to increase visibility in proprietary generative engines.[1][2] In this formulation, a publisher seeks to maximize the visibility or impression function of its citation within a generated response, while the generative engine balances citation impression and query relevance through an opaque internal function.[2]

Visibility in generative engines differs from average rank in conventional search results, where pages appear in a linear list.[2] Generative responses present structured prose that interleaves multiple inline citations with varying passage lengths, placements, and styles.[2] To evaluate attribution across those dimensions, the GEO framework defines customizable visibility metrics that capture relevance and citation influence from both objective and subjective perspectives.[2]

To test GEO strategies systematically, Aggarwal et al. released GEO-bench, a benchmark containing 10,000 user queries drawn from diverse domains and paired with relevant web sources.[1][2] Across GEO-bench evaluations, the authors reported that GEO methods increased source visibility by up to 40%.[1][2] Adding citations, quotations from relevant sources, and statistics produced visibility increases exceeding 40% across varied queries, while strategy effectiveness differed substantially by domain.[1][2] The authors also evaluated their methods on [Perplexity](https://mimirwiki.com/wiki/perplexity) (Perplexity.ai) as a deployed generative engine, reporting visibility gains of up to 37%.[2]

## Empirical studies of Generative Engine Optimization in 2025 and 2026

Generative Engine Optimization research expanded substantially in 2025 and 2026 to cover commercial AI search platforms, document structure, and methodological audits.[3][4][5] Three arXiv papers from September 2025 through July 2026 illustrate the shift from single-benchmark content edits to multi-engine comparisons, structural engineering, and critical synthesis.[3][4][5]

| Study | Date | Scope | Key reported findings |
| --- | --- | --- | --- |
| Aggarwal et al. (arXiv:2311.09735 / KDD '24) | 2023-11-16 (v3: 2024-06-28) | 10,000-query GEO-bench and Perplexity.ai | Up to 40% visibility gain in benchmark tests; over 40% from citations, quotations, and statistics; up to 37% on Perplexity.ai.[1][2] |
| Chen et al. (arXiv:2509.08919) | 2025-09-10 | ChatGPT, Perplexity, Gemini vs. Google Search across verticals, languages, and paraphrases | Systematic bias toward third-party earned media over brand-owned and social sources; large cross-engine differences in diversity, freshness, and phrasing sensitivity.[3] |
| Yu et al. (arXiv:2603.29979) | 2026-03-31 | Structural feature engineering (GEO-SFE) across six generative engines | Macro-, meso-, and micro-structure optimization raised citation rate by 17.3% and subjective quality by 18.5% while preserving semantic integrity.[4] |
| Martinez (arXiv:2607.14035) | 2026-07-15 | Critical scoping review of 45 studies (Nov 2023 to Jul 2026) | Models GEO as a multistage stochastic pipeline; finds evidence concentrated on already-retrieved sources with no stable cross-platform causal effect on organic discoverability or traffic.[5][6] |

In September 2025, Mahe Chen, Xiaoxuan Wang, Kaiwen Chen, and Nick Koudas compared [ChatGPT](https://mimirwiki.com/wiki/chatgpt), [Perplexity](https://mimirwiki.com/wiki/perplexity), and [Google Gemini](https://mimirwiki.com/wiki/google-gemini) against traditional Google web search across multiple verticals, languages, and query paraphrases.[3] Their controlled experiments found that AI search engines exhibit a systematic bias toward earned media (authoritative third-party sources) over brand-owned and social content, contrasting with Google's more balanced source mix.[3] The study also documented significant variation among AI search services in domain diversity, freshness, cross-language stability, and sensitivity to phrasing, leading the authors to propose four practitioner priorities: structuring content for machine scannability and justification, building earned-media presence, tailoring tactics by engine and language, and addressing big-brand bias for niche sites.[3]

In March 2026, Junwei Yu, Mufeng Yang, Yepeng Ding, and Hiroyuki Sato introduced GEO-SFE, a structural feature engineering framework addressing document layout alongside semantic text edits.[4] GEO-SFE decomposes web page structure into three hierarchical levels: macro-structure (document architecture), meso-structure (information chunking), and micro-structure (visual emphasis).[4] Evaluating architecture-aware strategies across six generative engines, the authors reported consistent improvements of 17.3% in citation rate and 18.5% in subjective quality while preserving semantic integrity.[4]

In July 2026, Olivier Martinez published a critical scoping review of 45 GEO studies published or accepted between November 16, 2023 and July 14, 2026, along with one earlier preprint published at EMNLP in December 2023 and related retrieval-augmented generation evaluation literature.[5][6] The survey formalizes GEO as a multistage pipeline spanning search activation, crawling and indexing, retrieval, reranking and context allocation, citation, prominence, factual absorption, fidelity, and user behavior, paired with a visibility vector separating discoverability, citation, absorption, and economic outcomes.[5]

## Generative Engine Optimization and SEO, RAG, robots.txt, and llms.txt

Generative Engine Optimization intersects with search engine optimization (SEO), retrieval-augmented generation (RAG), crawler access controls, and emerging machine-readable publishing conventions.[2][5][7][9] Conventional SEO focuses on improving page rankings in link lists, while GEO targets how language models ingest, summarize, and cite retrieved pages.[2] Because generative search engines depend on underlying search indexes and retrieval models, upstream SEO mechanics remain coupled to downstream citation outcomes.[5][7] Martinez's 2026 review notes that interventions can improve one pipeline stage while impairing another; in particular, rewrites tuned narrowly for citation can degrade upstream retrieval.[5][6]

Crawler access rules govern whether web content enters generative search indexes at all.[7][9] Under the [robots.txt](https://mimirwiki.com/wiki/robots-txt) convention, site owners specify acceptable automated access for search indexing bots and crawlers.[9] Google Search Central specifies that allowing crawling in `robots.txt` and in content delivery network (CDN) or hosting layers remains a basic prerequisite for appearing in AI search features.[7] [OpenAI](https://mimirwiki.com/wiki/openai) maintains separate developer documentation describing its web crawlers.[10] At the network-infrastructure layer, [Cloudflare](https://mimirwiki.com/wiki/cloudflare) announced on July 1, 2026 traffic-management options available to all customers that separate AI traffic controls into three distinct categories: search, agent, and training.[11]

Publishers have also discussed [llms.txt](https://mimirwiki.com/wiki/llms-txt), a web convention proposed by Jeremy Howard on September 3, 2024 and updated to v2 on August 10, 2026.[9] The proposal defines a curated Markdown overview file placed at `/llms.txt` or a subpath such as `/docs/llms.txt`, accompanied by clean `.md` versions of individual pages discovered via HTML `<link>` elements or HTTP `Link` headers using the `alternate` (`type="text/markdown"`) and `describedby` link relations.[9] The proposal distinguishes `llms.txt` from `robots.txt`, which governs crawler permissions, and from sitemaps (`sitemap.xml`), which list all indexable human-readable pages and are typically too large in aggregate for an LLM context window.[9] It also avoids the origin-root `/.well-known/` prefix defined in RFC 8615 so authors on shared hosts can publish path-scoped files.[9] As of August 2026, the v2 specification states that `llms.txt` has been used primarily at inference time, that documentation platforms such as Mintlify and GitBook generate it automatically, and that [OpenAI](https://mimirwiki.com/wiki/openai), [Anthropic](https://mimirwiki.com/wiki/anthropic), and Google's Gemini publish `llms.txt` files for their developer documentation; OpenAI's crawler documentation page itself points to `llms.txt` and `.md` page URLs.[9][10]

## Platform guidance on Generative Engine Optimization

Generative Engine Optimization has drawn explicit platform guidance from Google Search Central regarding AI Overviews and AI Mode in Google Search.[7][8] As of 2026-11-23, Google's official documentation states that foundational SEO practices remain relevant for AI features in Google Search and that site owners face no additional technical requirements or special optimizations to appear in AI Overviews or AI Mode.[7] To be eligible as a supporting link in either feature, a page must be indexed and eligible to appear in Google Search with a snippet under standard Search technical requirements, though compliance does not guarantee crawling, indexing, or serving.[7]

Google describes AI Overviews as summaries intended for queries where an overview adds value beyond classic Search, noting that they often do not trigger, while AI Mode is described as particularly helpful for queries that need further exploration, reasoning, or complex comparisons.[7] Both features may apply a "query fan-out" technique that issues multiple related searches across subtopics and data sources during response generation to identify a wider set of supporting web pages.[7] Because AI Overviews and AI Mode may rely on different models and techniques, the answers and supporting links they display can vary.[7]

Google lists continuing SEO fundamentals applicable to AI search features:[7]

- Allowing crawling in `robots.txt` and in CDN or hosting infrastructure
- Making pages discoverable through internal website links
- Providing a great page experience and keeping important content available in textual form
- Supporting text with high-quality images and videos where applicable
- Ensuring structured data matches the visible text on the page
- Keeping Merchant Center and Business Profile information current

On the Google Search Central Blog, Google published guidance on content performance in its AI search experiences in May 2025, announced a dedicated resource for optimizing for generative AI in Google Search in May 2026, and introduced Search Generative AI performance reports in Search Console in June 2026.[8]

## Methodological limits and evidence boundaries of Generative Engine Optimization

Generative Engine Optimization faces substantial methodological and empirical boundaries documented across 2025 and 2026 audits.[3][5][6] In his July 2026 critical review of 45 studies, Olivier Martinez points out that commercial claims often extrapolate Aggarwal et al.'s up to 40% visibility figure into a general promise of ranking highly in ChatGPT, even though that result measured relative visibility in a simulator where five candidate documents had already been placed inside the model context.[5][6] Across the reviewed literature, evidence shows that modifying an already-retrieved document can causally alter its citation or use inside an answer, whereas no reviewed technique demonstrates a stable, longitudinal, cross-platform causal effect on organic discoverability or downstream user behavior such as traffic and conversions.[5][6]

Empirical findings also show sensitivity to experimental settings and competitive dynamics.[5][6] Across reviewed studies, topical relevance and context position emerge as the most reproducible factors affecting citation, while generic heuristics transfer poorly across domains and models.[5] Multi-actor competition can erode individual optimization gains when multiple publishers apply similar edits, which helps reconcile seemingly conflicting outcomes across single-actor and multi-actor studies such as Puerto et al. (2025).[5][6] Audits of commercial generative engines further report low source overlap across platforms, substantial run-to-run variability, sensitivity to query paraphrases, and persistent fidelity gaps in which a source may be cited without supporting a claim or paraphrased without a link.[3][5][6]

Because legitimate content rewrites, adversarial text sequences, and indirect prompt injections all alter the text consumed by a generative engine, Martinez frames optimization and manipulation as sharing a single technical channel.[6] Under that analysis, distinguishing acceptable GEO practices from manipulation relies on truthfulness, semantic preservation, disclosure, and the absence of hidden instructions.[6] Martinez also notes that the 2023-2026 GEO literature mixes peer-reviewed conference papers, formally accepted forthcoming articles, workshop papers, and preprints, and proposes a reproducible evaluation protocol incorporating repeated measurements, query paraphrases, control conditions, human validation, and multi-actor interference testing.[5][6]

## Frequently asked questions

### What is Generative Engine Optimization (GEO)?

Generative Engine Optimization (GEO) is a black-box optimization framework for adjusting web content presentation, style, and structure to increase visibility and citation in responses produced by generative search engines. Aggarwal et al. introduced the term on 2023-11-16 in arXiv:2311.09735, later accepted to KDD 2024. [1][2]

### How does Generative Engine Optimization differ from traditional SEO?

Traditional search engine optimization (SEO) targets average position in a ranked list of links. Generative Engine Optimization addresses multi-document synthesis, inline citation placement, prominence, and factual attribution across multistage retrieval and generation pipelines. [2][5]

### What did the original GEO-bench study find?

In evaluations on the 10,000-query GEO-bench dataset, Aggarwal et al. reported visibility gains of up to 40% across diverse queries, gains exceeding 40% when adding citations, quotations, and statistics, and gains up to 37% on Perplexity.ai. A July 2026 survey by Olivier Martinez noted that the benchmark gains were measured in a simulator with five documents already placed in context, so they do not establish organic discoverability or durable traffic effects. [2][5][6]

### What do 2025 and 2026 academic studies show about GEO effectiveness?

A September 2025 study by Chen et al. found that ChatGPT, Perplexity, and Gemini favor third-party earned media over brand-owned and social content and vary across engines in diversity, freshness, and phrasing sensitivity. A March 2026 study by Yu et al. reported 17.3% citation-rate gains and 18.5% subjective-quality gains from structural feature engineering across six engines, while Martinez's July 2026 review of 45 studies found that topical relevance and context position are the most reproducible factors. [3][4][5]

### Does Google require special GEO techniques for AI Overviews and AI Mode?

No. As of 2026-11-23, Google Search Central documentation states that pages indexed and eligible for Google Search with a snippet require no extra technical specifications or special optimizations to appear as supporting links in AI Overviews or AI Mode. [7]

### How do robots.txt and llms.txt relate to Generative Engine Optimization?

robots.txt sets automated crawler access rules, and Google requires allowing crawling in robots.txt and hosting infrastructure for AI feature eligibility. Cloudflare also lets site owners separate search, agent, and training AI traffic controls as of July 2026, while llms.txt is a separate proposed Markdown overview file designed for on-demand inference-time use by language models and agents. [7][9][11]

## Quotable sentences

- Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, and Ameet Deshpande introduced the term Generative Engine Optimization on 2023-11-16 in arXiv:2311.09735, which was accepted to KDD 2024. [1][2]
- The GEO-bench benchmark consists of 10,000 queries from diverse domains and web sources adapted to evaluate generative engine visibility methods. [2]
- Aggarwal et al. reported visibility increases of up to 40% across diverse queries in their benchmark evaluation and up to 37% on Perplexity.ai, with citations, quotations from relevant sources, and statistics yielding increases above 40%. [2]
- A September 2025 empirical study by Chen et al. found that ChatGPT, Perplexity, and Gemini display a systematic bias toward third-party earned media over brand-owned and social content compared with Google web search. [3]
- The GEO-SFE structural feature engineering framework reported a 17.3% improvement in citation rate and an 18.5% improvement in subjective quality across six generative engines in March 2026. [4]
- A July 2026 critical survey by Olivier Martinez reviewing 45 studies concluded that already-retrieved content can causally affect citation or use, while no reviewed technique showed a stable, longitudinal, cross-platform causal effect on organic discoverability or downstream user behavior. [5]
- Google Search Central documentation states, as of 2026-11-23, that pages indexed and eligible to appear in Google Search with a snippet face no additional technical requirements or special optimizations for AI Overviews or AI Mode. [7]
- On 2026-07-01, Cloudflare introduced traffic-management options allowing website owners to distinguish and control search, agent, and training AI traffic separately. [11]

## Timeline

- 2023-11-16: Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, and Ameet Deshpande submit version 1 of "GEO: Generative Engine Optimization" to arXiv, introducing the term GEO and the GEO-bench benchmark. [1]
- 2024-06-28: Aggarwal et al. publish revision v3 of the GEO paper on arXiv ahead of its presentation at KDD 2024 (August 25-29, 2024 in Barcelona). [1][2]
- 2024-09-03: Jeremy Howard publishes the /llms.txt proposal for providing curated Markdown site overviews to language models and AI agents. [9]
- 2025-05: Google Search Central Blog publishes guidance on content performance in Google's AI search experiences. [8]
- 2025-09-10: Chen et al. submit a comparative study of ChatGPT, Perplexity, Gemini, and Google Search (arXiv:2509.08919), documenting earned-media bias and cross-engine differences. [3]
- 2026-03-31: Yu et al. submit the GEO-SFE structural feature engineering study (arXiv:2603.29979), reporting citation-rate and subjective-quality improvements across six generative engines. [4]
- 2026-06: Google Search Central Blog announces Search Generative AI performance reports in Search Console, following a May 2026 resource on optimizing for generative AI in Google Search. [8]
- 2026-07-01: Cloudflare introduces AI traffic controls allowing website owners to distinguish and manage search, agent, and training traffic separately. [11]
- 2026-07-15: Olivier Martinez publishes a critical survey of 45 GEO studies from November 2023 through July 2026 (arXiv:2607.14035), formalizing a multistage pipeline model and reproducible evaluation protocol. [5][6]
- 2026-08-10: Jeremy Howard updates the /llms.txt proposal to v2, which describes placing the file at a subpath and discovery through the alternate and describedby link relations. [9]

## Sources

1. [2311.09735] GEO: Generative Engine Optimization. arXiv. published 2023-11-16. https://arxiv.org/abs/2311.09735 (checked 2026-11-23; tier 2: academic or news)
2. GEO: Generative Engine Optimization. arXiv. published 2024-06-28. https://arxiv.org/html/2311.09735v3 (checked 2026-11-23; tier 2: academic or news)
3. [2509.08919] Generative Engine Optimization: How to Dominate AI Search. arXiv. published 2025-09-10. https://arxiv.org/abs/2509.08919 (checked 2026-11-23; tier 2: academic or news)
4. [2603.29979] Structural Feature Engineering for Generative Engine Optimization: How Content Structure Shapes Citation Behavior. arXiv. published 2026-03-31. https://arxiv.org/abs/2603.29979 (checked 2026-11-23; tier 2: academic or news)
5. [2607.14035] Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026). arXiv. published 2026-07-15. https://arxiv.org/abs/2607.14035 (checked 2026-11-23; tier 2: academic or news)
6. Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023–2026). arXiv. published 2026-07-15. https://arxiv.org/html/2607.14035v1 (checked 2026-11-23; tier 2: academic or news)
7. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/ai-features (checked 2026-11-23; tier 3: official site)
8. Top ways to ensure your content performs well in Google's AI experiences on Search | Google Search Central Blog | Google for Developers. Google Search Central Blog. published 2025-05. https://developers.google.com/search/blog/2025/05/succeeding-in-ai-search (checked 2026-11-23; tier 3: official site)
9. The /llms.txt file, v2 – llms-txt. llmstxt.org. published 2024-09-03. https://llmstxt.org/ (checked 2026-11-23; tier 3: official site)
10. Overview of OpenAI Crawlers. OpenAI. https://developers.openai.com/api/docs/bots (checked 2026-11-23; tier 3: official site)
11. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. published 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Generative Engine Optimization." Version eb2c50d0, 2026-11-25. https://mimirwiki.com/wiki/generative-engine-optimization
