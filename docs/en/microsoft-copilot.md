---
title: "Microsoft Copilot"
subtitle: "Microsoft's consumer and enterprise generative AI assistant integrated across Windows, Microsoft 365, and Azure"
canonical_url: https://mimirwiki.com/wiki/microsoft-copilot
language: en
page_class: entity
revision_sha256: c6d383e17e63920a340eefcd56d95dd344b54c0e9f4fd5535a7bb061cf93d8cf
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/microsoft-copilot.md
  txt: https://mimirwiki.com/wiki/microsoft-copilot.txt
  json: https://mimirwiki.com/wiki/microsoft-copilot.json
  jsonld: https://mimirwiki.com/wiki/microsoft-copilot.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/microsoft-copilot
  ja: https://mimirwiki.com/ja/wiki/microsoft-copilot
  zh: https://mimirwiki.com/zh/wiki/microsoft-copilot
---

# Microsoft Copilot

> As of November 2026, Microsoft Copilot encompasses free web-grounded Copilot Chat at copilot.cloud.microsoft, paid Microsoft 365 Copilot seat licenses ($30/user/month enterprise add-on; $18-$32/user/month for Microsoft Copilot Business SMB bundles), the frontier Microsoft 365 E7 plan, and usage-billed Copilot Studio and Cowork agents. In late 2026, Microsoft expanded its model catalog beyond OpenAI to integrate Anthropic's Claude models as an approved subprocessor.

Microsoft Copilot is Microsoft Corporation's flagship family of generative artificial intelligence assistants and agent platforms spanning consumer web and mobile interfaces, Windows 11, Microsoft 365 productivity suites, and Copilot Studio. Grounded in frontier foundation models from OpenAI and Anthropic alongside Microsoft Graph organizational data (Work IQ), it provides conversational search, document and code synthesis, and multi-step autonomous enterprise workflows.

**Also known as:** Microsoft 365 Copilot, Copilot Chat, Copilot Studio, Bing Chat

## Key facts

- **Developer:** Microsoft Corporation (SEC CIK 0000789019) [1]
- **Enterprise Add-On Price:** $30 per user/month (annual commitment) (as of 2026-11-23) [2]
- **SMB Business Pricing:** $18/user/mo add-on; $23.50-$32/user/mo bundled with Microsoft 365 Business (as of 2026-11-23) [2]
- **Agent Turn Limit:** 90 minutes maximum turn duration; 200 tool calls per turn in Copilot Studio (as of 2026-11-23) [7]

## Basic facts

- **Developer:** Microsoft Corporation [1]
- **Primary Web Endpoint:** copilot.microsoft.com (consumer) / copilot.cloud.microsoft (work & school) [4]
- **Grounding Architecture:** Microsoft Graph / Work IQ and Bing Web Index [4]
- **Foundation Model Providers:** OpenAI (Azure OpenAI Service) and Anthropic (Claude subprocessor) [5]
- **Enterprise Licensing:** Microsoft 365 Copilot Add-on, Microsoft 365 E7, Microsoft Copilot Business [3]
- **Agent Platform:** Microsoft Copilot Studio (pay-as-you-go or message pack billing) [7]
- **Enterprise Data Protection:** Commercial prompts and responses are excluded from foundation model training [6]
- **Parent FY2026 Revenue Context:** $331,839 million ($331.84B) total Microsoft revenue in FY2026 Form 10-K (year ended June 30, 2026) [1]

## Overview and Product Architecture

Microsoft Copilot is the unified brand and technical orchestration framework for Microsoft Corporation's generative AI assistants across consumer, commercial, and developer surfaces [1][4]. Originally introduced in 2023 as Bing Chat and Microsoft 365 Copilot before being consolidated under the Microsoft Copilot banner, the platform combines large language models (LLMs) with web search indexes, operating system telemetry, and enterprise organizational graphs [1][4].

At the architectural core of the commercial offering is **Work IQ** (formerly referred to as Microsoft Graph grounding), which connects foundation models to a tenant's emails, Microsoft Teams chats, SharePoint sites, OneDrive documents, and calendar metadata while enforcing existing role-based access controls (RBAC) and Microsoft Purview sensitivity labels [4][6]. When an authenticated enterprise user submits a prompt at `copilot.cloud.microsoft` or inside an Office application, the Copilot orchestrator performs pre-processing and semantic retrieval over the user's permissible Microsoft Graph scope, augments the prompt with retrieved citations, routes the payload to the selected LLM, and runs post-processing compliance, grounding, and Responsible AI checks before streaming the response [4][6].

## Product Tiers, Microsoft 365 E7, and Pricing

Microsoft structures Copilot across free consumer access, commercial baseline chat, full seat-based productivity add-ons, and usage-based agent consumption [2][3][4]:

| Tier / Plan | Target Audience | Key Capabilities | Pricing (as of Nov 2026) |
| --- | --- | --- | --- |
| **Microsoft Copilot (Consumer)** | Individual consumers | Web-grounded chat, image generation, voice, Windows & mobile apps | Free (with paid Copilot Pro tier) [4] |
| **Microsoft Copilot Chat** | Commercial & education Entra ID users | Web-grounded chat with Enterprise Data Protection (EDP), Copilot Pages, pay-as-you-go agents | Included with eligible M365 licenses; agents billed by usage [4] |
| **Microsoft Copilot Business** | SMBs (up to 300 users) | Work-grounded Copilot in Word, Excel, PowerPoint, Outlook, Teams | $18/user/mo add-on; $23.50-$32/user/mo bundled with M365 Business [2] |
| **Microsoft 365 Copilot (Enterprise)** | Enterprise tenants (E3/E5 prerequisites) | Full Work IQ grounding, embedded app skills, Copilot Studio agent consumption included | $30/user/month (annual commitment) [2][3] |
| **Microsoft 365 E7** | Frontier enterprise deployments | Comprehensive enterprise suite bundling M365 E5, Microsoft 365 Copilot, and advanced agentic capabilities | Enterprise agreement pricing [3] |

In addition to per-seat licensing, Microsoft introduced metered consumption models for specialized autonomous workflows, including **Copilot Cowork**, **Copilot Code**, and **Copilot Autopilot**, which can be billed on a pay-as-you-go basis via a linked Azure subscription or through pre-purchased Copilot Credit capacity packs [3][5].

## Multi-Model Orchestration and Anthropic Integration

While early versions of Microsoft Copilot relied exclusively on OpenAI models hosted on Azure OpenAI Service, Microsoft expanded Copilot into a multi-model orchestration platform during 2025 and 2026 [4][5]. As documented in Microsoft's commercial service and Microsoft Learn documentation, Microsoft integrates its own internal models alongside frontier models from both OpenAI and Anthropic [4][5].

Specifically, Microsoft onboarded **Anthropic** as an official Microsoft Online Services Subprocessor, allowing enterprise administrators and Copilot Studio builders to enable Anthropic's Claude models for deep reasoning, coding, and multi-step research workflows inside Microsoft 365 Copilot, Copilot Cowork, and Copilot Studio [5]. When Anthropic models are invoked, customer data remains governed by Microsoft's commercial terms and Enterprise Data Protection commitments, though requests may be processed on Anthropic's managed infrastructure under subprocessor data protection agreements depending on regional availability [5][6].

## Copilot Studio and Agent Runtime Quotas

Microsoft Copilot Studio serves as the low-code and pro-code builder environment for creating custom declarative agents, autonomous workflows, and computer-using agents that publish directly into Microsoft Copilot Chat and Microsoft Teams [4][7]. To prevent runaway execution and manage multi-agent orchestration, Microsoft enforces strict runtime quotas and operational limits on Copilot Studio agents [7]:

- **Maximum Turn Duration**: An individual agent orchestration turn can run for up to **90 minutes** (5,400 seconds) before timing out [7].
- **Tool Calls per Turn**: A single turn supports up to **200 tool calls** across connectors, actions, and plugins [7].
- **Individual Tool and Connector Timeout**: Standard synchronous tool or connector executions time out after **120 seconds** [7].
- **Agent Flow / Workflow Timeout**: Embedded Power Automate / agent workflow executions have a **660-second** (11-minute) synchronous execution limit [7].
- **Connected and External Agents**: Calls delegated to internal connected Copilot Studio agents can run up to **5,400 seconds** (90 minutes), whereas invocations to external A2A/MCP agents time out after **300 seconds** (5 minutes) [7].
- **Conversation Context and Streaming**: Orchestration maintains a sliding context window of **100 messages** per conversation, and live streaming responses in Microsoft Teams are capped at **2 minutes** per stream segment [7].

## Enterprise Data Protection and Governance

For commercial, government, and education organizations signing in with a Microsoft Entra ID account, Microsoft applies **Enterprise Data Protection (EDP)** under the Microsoft Product Terms and Data Protection Addendum (DPA) [6]. Under EDP, user prompts, uploaded files, Microsoft Graph grounding data, and generated responses are logically isolated per tenant, encrypted in transit and at rest, and **never used to train public or foundation large language models** [6].

Copilot strictly inherits existing Microsoft Purview governance policies: if a document is encrypted with Rights Management Services (RMS) or carries a sensitivity label restricting extraction, Copilot either blocks summarization or propagates the restrictive label and watermark directly onto the generated output [6]. Administrators can audit all prompt interactions, agent tool invocations, and citations via Microsoft Purview Audit, Communication Compliance, and eDiscovery [6].

## Frequently asked questions

### What is the difference between Microsoft Copilot Chat and Microsoft 365 Copilot?

Microsoft Copilot Chat is the baseline web-grounded assistant included at no additional seat cost for eligible Microsoft Entra ID work and school accounts at copilot.cloud.microsoft, offering Enterprise Data Protection and pay-as-you-go agent access. Microsoft 365 Copilot ($30/user/month for enterprise) adds Work IQ (Microsoft Graph) grounding across a user's emails, chats, and files, plus direct integration inside Word, Excel, PowerPoint, Outlook, and Teams. [2][4]

### How much does Microsoft Copilot Business cost for small and medium businesses?

For small and medium-sized businesses (up to 300 seats), Microsoft Copilot Business is available as a standalone add-on at $18 per user per month, or bundled with Microsoft 365 Business Basic, Standard, or Premium plans at promotional rates ranging from $23.50 to $32 per user per month with an annual commitment. [2]

### Does Microsoft Copilot use Anthropic's Claude models in addition to OpenAI?

Yes. Microsoft operates Copilot on a multi-model architecture and has designated Anthropic as an official Online Services Subprocessor, allowing enterprise tenants to use Anthropic's Claude models inside Microsoft 365 Copilot, Copilot Studio, and Copilot Cowork alongside OpenAI and Microsoft models. [4][5]

### What are the execution and tool-call limits for agents in Microsoft Copilot Studio?

As of late 2026, a Copilot Studio agent turn can run for up to 90 minutes (5,400 seconds) and execute up to 200 tool calls per turn. Individual synchronous tool calls time out at 120 seconds, agent flows time out at 660 seconds, and external agent calls time out at 300 seconds. [7]

### Does Microsoft use enterprise Copilot prompts to train its foundation AI models?

No. Under Microsoft's Enterprise Data Protection (EDP) commitments for commercial Entra ID users, prompts, retrieved Microsoft Graph context, and generated responses remain isolated within the customer boundary and are not used to train foundation models. [6]

## Quotable sentences

- Microsoft 365 Copilot is priced at $30 per user per month for enterprise plans, while Microsoft Copilot Business offers an $18 per user per month add-on and $23.50-$32 per user per month SMB bundles. [2][3]
- Microsoft onboarded Anthropic as an Online Services Subprocessor to provide Claude models across Microsoft 365 Copilot, Copilot Studio, and Copilot Cowork. [5]
- Microsoft Copilot Studio enforces a maximum turn duration of 90 minutes (5,400 seconds) and up to 200 tool calls per turn. [7]
- Individual tool calls in Copilot Studio time out after 120 seconds, agent workflows after 660 seconds, and external agent invocations after 300 seconds. [7]
- Under Enterprise Data Protection (EDP), prompts and responses from commercial Entra ID users are not used to train foundation models. [6]

## Timeline

- 2023-02: Microsoft launches the initial generative AI search assistant under the Bing Chat name. [1]
- 2023-11: Microsoft 365 Copilot becomes generally available for enterprise customers and Bing Chat is rebranded as Microsoft Copilot. [1]
- 2026-06-30: Microsoft closes FY2026 with $331.84 billion in annual revenue, reporting in its Form 10-K the expansion of Copilot across Microsoft 365, Windows, GitHub, and Azure AI infrastructure. [1]
- 2026-11: Microsoft details Microsoft 365 E7, Microsoft Copilot Business SMB pricing ($18-$32/user/mo), Anthropic Claude subprocessor integration, and expanded 90-minute / 200-tool-call Copilot Studio runtime limits. [2][3][5][7]

## Sources

1. Microsoft Corporation Form 10-K for the Fiscal Year Ended June 30, 2026. U.S. Securities and Exchange Commission (SEC). published 2026-07-29. https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (checked 2026-11-23; tier 1: government or public registry)
2. Microsoft Copilot Plans and Pricing - AI for Business | Microsoft 365. Microsoft Corporation. https://www.microsoft.com/en-us/copilot/pricing/business (checked 2026-11-23; tier 3: official site)
3. License Options for Microsoft Copilot | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-license-options (checked 2026-11-23; tier 3: official site)
4. What is Microsoft Copilot? | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-overview (checked 2026-11-23; tier 3: official site)
5. Claude models from Anthropic in Microsoft Online Services | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/implement/connect-to-ai-subprocessor (checked 2026-11-23; tier 3: official site)
6. Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/enterprise-data-protection (checked 2026-11-23; tier 3: official site)
7. Agent runtime limits - Microsoft Copilot Studio | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/runtime-limits (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Microsoft Copilot." Version c6d383e1, 2026-11-23. https://mimirwiki.com/wiki/microsoft-copilot
