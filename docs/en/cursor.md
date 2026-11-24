---
title: "Cursor"
subtitle: "AI coding agent and software development environment created by Anysphere, Inc. and bundled in The X Subscription"
canonical_url: https://mimirwiki.com/wiki/cursor
language: en
page_class: entity
revision_sha256: bfb78c2666051b80291f9e127c31cd4c33433295345b2142ffb6d23c1e1949af
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/wiki/cursor.md
  txt: https://mimirwiki.com/wiki/cursor.txt
  json: https://mimirwiki.com/wiki/cursor.json
  jsonld: https://mimirwiki.com/wiki/cursor.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/cursor
  ja: https://mimirwiki.com/ja/wiki/cursor
  zh: https://mimirwiki.com/zh/wiki/cursor
---

# Cursor

> Cursor is an AI coding agent and development environment developed by Anysphere, Inc., founded in 2022. In June 2026, SpaceX agreed to acquire Cursor for $60 billion in stock. As of 2026-11-23, Cursor is sold through The X Subscription at $0 to $200 per month, supporting Agent, Tab completions, Cloud Agents, Rules, Skills, MCP, CLI, and multiple model providers.

Cursor is an AI coding agent and software development environment developed by Anysphere, Inc. for understanding codebases, planning and building features, debugging, and reviewing code changes. Founded in 2022 as Anysphere, the startup agreed in June 2026 to be acquired by SpaceX in a $60 billion stock transaction, following SpaceX's earlier merger with xAI. As of 2026-11-23, Cursor is distributed as part of The X Subscription through X Subscription Corp. across Free, Plus ($8/month), Premium ($30/month), Super ($100/month), Ultra ($200/month), Teams ($30 to $200 per seat/month), and custom Enterprise plans, while existing legacy Cursor plans remain active for prior subscribers. Cursor runs across an integrated desktop IDE, a dedicated Agents Window, a command-line interface (CLI), web, and iOS, and supports first-party Grok and Composer models alongside third-party models from OpenAI, Anthropic, and Google.

**Also known as:** Cursor IDE, Cursor Editor, Anysphere Cursor

## Key facts

- **Developer:** Anysphere, Inc. [9]
- **SpaceX acquisition agreement:** $60 billion in stock, reported 2026-06-16 [1]
- **Individual plan prices:** Free ($0), Plus ($8/mo), Premium ($30/mo), Super ($100/mo), Ultra ($200/mo) (as of 2026-11-23) [5]
- **Teams plan prices:** $30, $100, or $200 per seat/month (as of 2026-11-23) [5]
- **Security certifications:** SOC 2 Type II, ISO/IEC 27001:2022, ISO/IEC 42001:2023, AIUC-1 (as of 2026-11-23) [8]

## Basic facts

- **Developer:** Anysphere, Inc. [9]
- **Founded:** 2022 (as Anysphere) [1]
- **Acquisition agreement:** SpaceX, $60 billion in stock (reported 2026-06-16, expected to close Q3 2026) [1]
- **Subscription distributor:** X Subscription Corp. (The X Subscription) (as of 2026-11-23) [4]
- **Supported surfaces:** Editor, Agents Window, CLI, Cursor SDK, iOS app (as of 2026-11-23) [6]
- **Customization:** Plugins, Rules, Skills, Subagents, Hooks, MCP (as of 2026-11-23) [3]
- **Included Cursor models:** Grok 4.7, Grok 4.6, Grok 4.5, Composer 2.5 (as of 2026-11-23) [5]
- **Individual plans:** Free ($0), Plus ($8/mo), Premium ($30/mo), Super ($100/mo), Ultra ($200/mo) (as of 2026-11-23) [5]
- **Teams and Enterprise:** Teams ($30, $100, or $200/seat/mo); Enterprise (custom) (as of 2026-11-23) [5]
- **Reported ARR (June 2025):** Over $500 million (Bloomberg and TechCrunch report) (as of 2025-06-05) [2]
- **Security certifications:** AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023, SOC 2 Type II (as of 2026-11-23) [8]
- **Official website:** cursor.com [9]

## Cursor product features, customization, and interfaces

Cursor is documented by Anysphere, Inc. as a coding agent for building software across five core workflows: tracing and understanding repositories, scoping and implementing features with Plan Mode, reproducing and fixing bugs, inspecting diffs and running checks before merging, and connecting with external development tools.[3] Starting on the Free tier, Cursor provides limited access to Agent, Chat, and Tab completions using Cursor's own models.[6]

Cursor's Agent interface spans a desktop IDE, a dedicated Agents Window, a web client, Cursor for iOS, and a command-line interface (CLI).[3][6][7] As of 2026-11-23, the Agent documentation covers Projects, Agent Review, Planning, Prompting, Voice Chat, Debugging, Design Mode, Tools, and Security, while the CLI documentation covers Shell Mode, ACP, and Headless or CI execution.[3] Cursor also publishes a Cursor SDK for TypeScript, Python, and Bridge integrations.[3]

Cursor organizes workflow customization under six documented mechanisms: Plugins, Rules, Skills, Subagents, Hooks, and [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (MCP) servers.[3] On Teams and Enterprise plans, organizations also receive a team marketplace for distributing internal rules, skills, and plugins.[4][5]

Cursor lists native integrations with source-control, IDE, communication, and issue-tracking platforms: GitHub, GitLab, Azure DevOps, Bitbucket, JetBrains, Xcode, Slack, Microsoft Teams, Jira, Linear, Notion, Tailscale, and Deeplinks.[3]

## Cursor Cloud Agents, Origin, Agent SDK, and Voice Chat

Cursor includes Cloud Agents, Automations, Origin code hosting, and Bugbot AI code reviews starting on the Premium subscription tier.[4][5] As of 2026-11-23, Cloud Agents documentation covers environment setup, builds, apps, automations, Bugbot, security review, vulnerability remediation, pull request routing and approval, rollouts, mobile access, self-hosted machines, and an API.[3] Origin provides repository hosting with a CLI, GitHub mirroring, CloneKit in CI, pull requests, Code Tours, repository browse and search, and access policies.[3]

Between October and November 2026, Cursor published four major platform additions in its changelog.[7]

- **Origin App Marketplace (October 13, 2026)**: Opened with more than 20 integrations and public app submissions across deployments ([Cloudflare](https://mimirwiki.com/wiki/cloudflare), Netlify, Render, Spacelift, Vercel), CI (Buildkite, CircleCI, CloudBees, Depot, EngFlow, Namespace, RWX), code review (CodeRabbit, Greptile, Tenki), security (Artemis Security, Semgrep, Socket Security, Upwind), monitoring (Sentry), and project management (Linear). Origin apps authenticate with an app JWT and installation access tokens, receive webhook events, and write back check runs, pull request comments, and reviews.[7]
- **Cloud Agent Canvases and Environments API (October 16, 2026)**: Added shareable interactive Canvases built by cloud agents, launched the beta Environments API for programmatic management of agent cloud environments, expanded environment capacity to up to 300 repositories, and increased load speed for large environments by 5x.[7]
- **Agent SDK (October 20, 2026)**: Reached general availability for defining agents as code folders containing `instructions.md` for prompts, `tools/` for typed actions, `skills/` for on-demand procedures, `mcp-connections/` for MCP server tools, and `channels/` for triggers from GitHub, GitLab, Bitbucket, Slack, webhooks, and cron schedules. The SDK provides local setup and playgrounds (`npx @cursor/agent-sdk init`, `agent-sdk dev`), validation (`agent-sdk validate`), evaluation and pull request webhook replay (`agent-sdk eval`, `agent-sdk github replay`), templates (security reviewer, owners-policy approver, PR autofixer, Linear or Jira triager), and deployment (`agent-sdk deploy`) to Cursor or self-hosted infrastructure.[7]
- **Live Apps (November 5, 2026)**: Released on all paid plans with cloud agents enabled. A cloud agent scaffolds a web application from a new or existing Cursor Origin or GitHub repository, provisions a Postgres database when needed, places authentication behind Cursor SSO, runs deterministic and agentic security checks for issues such as exposed credentials, and deploys to a chosen URL. Team administrators can inspect all apps and secrets, add custom security rules, approve blocked publishes, or unpublish apps; individual users can share apps publicly and provision Cursor API keys for scripts or Grok Bot.[7]

On November 6, 2026, Cursor added Voice Chat with coding agents across the Agents Window, IDE, web, and Cursor for iOS, including Siri activation (`"Hey Siri, call Cursor"`) and iOS Lock Screen Live Activity controls.[7] Voice Chat runs on [Grok](https://mimirwiki.com/wiki/grok) Voice with selectable voices including Ara, Eve, Leo, Rex, and Sal, and operates with zero data retention when Privacy Mode is enabled.[7] Voice Chat provides two-way spoken conversation and is separate from speech-to-text dictation (formerly Voice Mode, toggled in the IDE with `Cmd+Shift+Space`).[7]

## Cursor supported models and Cursor Router

Cursor supports models from SpaceXSI, [OpenAI](https://mimirwiki.com/wiki/openai), [Anthropic](https://mimirwiki.com/wiki/anthropic), Google, and Muse, divided as of 2026-11-23 into first-party Cursor models covered by a subscription's weekly usage pool and third-party models billed at API list price from prepaid credit.[3][5] Opting in to regional data residency adds a 10% uplift to model pricing for eligible models.[5]

Cursor's first-party pool covers [Grok](https://mimirwiki.com/wiki/grok) 4.7, Grok 4.6, Grok 4.5, and Composer 2.5.[5] When usage exceeds the weekly pool, the following per-million-token rates apply as of 2026-11-23.[3][5]

| Cursor model | Default / max context | Standard input / cache read / output (per 1M tokens) | Fast mode input / cache read / output (per 1M tokens) | US Data Residency |
| --- | --- | --- | --- | --- |
| Grok 4.7 | 256k / 500k | $2 / $0.5 / $6 (500k: $4 / $1 / $12) | $4 / $1 / $12 (500k Fast: $6 / $1.5 / $18) | Yes |
| Grok 4.6 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $12 | Yes |
| Grok 4.5 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $18 | Yes |
| Composer 2.5 | 200k / - | $0.5 / $0.2 / $2.5 | $3 / $0.5 / $15 | Yes |

Third-party models are unavailable on Free and Plus plans and are available starting on Premium at API list price from the first request.[5] As of 2026-11-23, Cursor documentation lists the following third-party models, including [Claude](https://mimirwiki.com/wiki/claude), GPT-5.6, and [Google Gemini](https://mimirwiki.com/wiki/google-gemini) models, with prices per million tokens.[3][5]

| Third-party model | Default / max context | Input | Cache write | Cache read | Output | US Data Residency |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 300k / 1M | $8 | $10 | $0.2 | $40 | Yes |
| Claude Opus 5.5 | 300k / 1M | $4 | $5 | $0.2 | $20 | Yes |
| Claude Sonnet 5.5 | 200k / 1M | $2 | $2.5 | $0.1 | $10 | Yes |
| Claude Haiku 5.5 | 300k / 1M | $0.1 | $0.125 | $0.01 | $0.5 | Yes |
| GPT-5.6 Sol | 272k / 1M | $4 | $5 | $0.4 | $20 | Yes |
| GPT-5.6 Terra | 272k / 1M | $2 | $2.5 | $0.2 | $12 | Yes |
| GPT-5.6 Luna | 272k / 1M | $0.2 | $0.25 | $0.02 | $1.2 | Yes |
| Gemini 4 Neon | 200k / 1M | $3 | - | $0.15 | $15 | Yes |
| Gemini 4 Carbon | 200k / 1M | $2 | - | $0.1 | $10 | Yes |
| Gemini 4 Argon | 200k / 1M | $2 | - | $0.1 | $10 | Yes |
| Gemini 4 Hydrogen | 200k / 1M | $1.5 | - | $0.075 | $7.5 | Yes |
| Gemini 3.1 Pro | 200k / 1M | $2 | - | $0.2 | $12 | No |
| Gemini 3.8 Flash | 200k / 1M | $0.75 | - | $0.075 | $3.75 | Yes |
| Muse Wonder | 300k / 1M | $4 | - | $0.2 | $20 | No |

Cursor's Auto feature splits model selection into three modes through Cursor Router: Cost, Balance, and Intelligence.[5][6] Individual plans support Cost mode (the successor to earlier Auto mode), which bills as a Cursor-model request against the weekly pool regardless of which model serves the request.[5][6] Balance and Intelligence modes launch for Teams and Enterprise plans across the Agents Window, editor, CLI, Cursor SDK, and iOS app, with Enterprise teams opted out by default until an administrator opts in; routes to Cursor models draw from the weekly pool, while routes to third-party models bill at API list price from prepaid credit plus the Cursor Token Rate when applicable.[5][6]

## Cursor plans, The X Subscription, and legacy pricing

Cursor is sold as part of The X Subscription, a single subscription combining Grok, Cursor, and X, distributed directly through X Subscription Corp. with no authorized resellers or third-party sellers.[4][5][6] All published subscription prices exclude applicable taxes such as VAT.[4][5] As of 2026-11-23, Cursor lists the following plans on The X Subscription.[4][5][6]

| Plan | Monthly price | Annual price | Included weekly pool | Third-party models |
| --- | --- | --- | --- | --- |
| Free | $0 | - | Limited | Not available |
| Plus | $8 | $80 | Base | Not available |
| Premium | $30 | $300 | 4x Plus | API list price from prepaid credit |
| Super | $100 | $1,000 | 15x Plus | API list price from prepaid credit |
| Ultra | $200 | $2,000 | 50x Plus | API list price from prepaid credit |
| Teams | $30, $100, or $200 per seat | - | Matches seat tier (4x to 50x Plus) | API list price plus Cursor Token Rate on eligible models |
| Enterprise | Custom | Custom | Pooled across Grok and Cursor | API list price plus Cursor Token Rate on eligible models |

Each paid plan provides one weekly-refreshing pool for Cursor models shared across Agent in the editor, CLI, Cloud Agents, Grok Bot, and Grok applications (Chat, Imagine, Voice, and Bot); Grok API access is included on paid plans but billed separately at standard model rates.[4][5] Plus runs Cursor models at fixed settings (Fast mode off, medium effort, and Grok 4.7 at the 256k context window) and excludes Auto, Cloud Agents, Automations, Bugbot, Origin, third-party models, and bring-your-own API keys (BYOK).[5] Super adds priority model access at peak times, and Ultra adds earliest access to new products and models.[4][5] When a user exhausts the weekly pool, Cursor does not downgrade request quality or speed; users can wait for the weekly reset, purchase prepaid credit top-ups (manual or Auto Top-up with a monthly spending cap managed at `grok.com/dashboard/billing`), or upgrade tiers.[5] Self-serve plans accept major credit and debit cards and allow cancellation up to 24 hours before renewal, with upgrades taking effect immediately and downgrades taking effect at the end of the billing period.[4][6]

Teams plans allow mixing Premium, Super, and Ultra seat tiers on one team (Plus is unavailable for teams) and add centralized billing, usage analytics, team-wide Privacy Mode enforcement, custom Chat data retention, a team marketplace, and SAML/OIDC SSO.[4][5] Enterprise adds pooled usage, invoice or purchase-order billing and wire transfers, SCIM seat management, granular spend controls, group-level limits, audit logs, service accounts, advanced network and MCP controls, and priority support.[4][5] On Teams and Enterprise plans, eligible third-party model requests and BYOK usage incur a Cursor Token Rate of $0.25 per million tokens across input, output, and cached tokens; individual plans, Cursor models, Cost mode requests, and third-party models whose cache-read price is strictly below $0.10 per million tokens across every pricing tier are exempt.[5]

Cursor also maintains legacy plans sold prior to The X Subscription for existing subscribers.[5][6] Legacy plans are closed to new customers, continue unless cancelled or permanently switched to The X Subscription (which cancels the legacy subscription with a prorated refund), are managed via Stripe at `cursor.com/dashboard/billing`, and provide two monthly usage pools (Cursor Models and Other Models) with on-demand billing for extra requests.[5][6] Legacy request-based plans also included Max Mode for extended context windows billed at the model's API rate plus 20%.[5]

| Legacy Cursor plan | Price | Comparable plan on The X Subscription |
| --- | --- | --- |
| Hobby | Free | Free |
| Start (India only) | ₹649/month (tax inclusive) | Plus |
| Pro | $20/month | Premium |
| Pro+ | $60/month | Super |
| Ultra | $200/month | Ultra |
| Teams Standard | $40/user/month | Teams (Premium seat) |
| Teams Premium | $120/user/month | Teams (Super seat) |

## Cursor security, compliance, and privacy controls

Cursor publishes its security architecture on `cursor.com/security` (last updated August 25, 2026) and its Privacy Policy on `cursor.com/privacy` (last updated November 6, 2026).[8][9] As of 2026-11-23, Cursor holds AIUC-1, ISO/IEC 27001:2022, and ISO/IEC 42001:2023 certifications along with a SOC 2 Type II attestation, and makes certificates, audit reports, penetration test executive summaries, and its subprocessor list available on request through `trust.cursor.com`.[4][8][9] Cursor commits to at least annual third-party penetration testing.[8]

Cursor states that each subprocessor undergoes vendor risk evaluation and annual re-review, that infrastructure access follows the principle of least privilege with multi-factor authentication (MFA) and log monitoring, and that model blocklists are enforced so requests are never routed to blocked models.[8] Cursor states that it does not use or maintain infrastructure in China and does not engage China-headquartered companies as subprocessors.[8] Security vulnerabilities reported to `security-reports@cursor.com` are acknowledged within five business days, and critical security incidents are communicated to affected users by email.[8] Cursor also uses Bugbot and Cloud Agent automations to monitor its own codebase.[8]

Privacy Mode is available across Free, individual, Teams, and Enterprise plans and can be enabled by users in settings or enforced across an organization by administrators, with new team members inheriting the team setting.[4][8] When Privacy Mode is active, Cursor states that user code data is not used for training by Cursor or its model providers, supported by technical controls and contractual provider terms, and Voice Chat runs with zero data retention.[4][7][8] Under the Privacy Policy, Anysphere, Inc. covers individual accounts while employer-provisioned commercial accounts where Anysphere acts as a data processor are governed by customer agreements.[9] Anysphere states that Inputs and Suggestions are not used to train models unless flagged for security review, explicitly reported as feedback, or explicitly approved by the user, and states that it does not knowingly collect genetic, biometric, health, or religious data or direct services to users under age 18.[9] Users can delete their accounts directly from the Settings dashboard.[8]

For organizational deployments, Cursor documents SAML/OIDC SSO, SCIM provisioning, compliance and audit logging, service accounts, mobile device management (MDM) deployment, data encryption and customer-managed encryption keys (CMEK), auto-run, browser, and network controls, and access controls for repositories, models, MCP servers, and Grok Bot.[4][8]

## Cursor corporate history, funding, and SpaceX acquisition agreement

Cursor was created by Anysphere, Inc., which was founded in 2022 and went through [OpenAI](https://mimirwiki.com/wiki/openai)'s startup accelerator in 2024.[1][9] In late 2024, Anysphere raised $100 million at a pre-money valuation of $2.5 billion.[2] Earlier in 2025, OpenAI and other prospective buyers approached Anysphere regarding an acquisition, and Anysphere declined those offers.[2]

Anysphere's annualized recurring revenue (ARR) was reported by TechCrunch at $300 million in mid-April 2025 and surpassed $500 million by June 5, 2025, according to sources cited by Bloomberg and TechCrunch.[2] On June 5, 2025, TechCrunch reported that Anysphere closed a $900 million Series C round (its third funding round within a year) at a $9.9 billion valuation, led by returning investor Thrive Capital with participation from Andreessen Horowitz, Accel, and DST Global.[1][2] At that time, Cursor offered a two-week free trial converting into $20 monthly Pro or $40 monthly business subscriptions, alongside newly introduced enterprise licenses.[2] In late 2025, Anysphere raised an additional $2.3 billion, reaching a valuation of approximately $29 billion.[1]

In early 2026, xAI hired two senior Cursor engineering leaders, and in April 2026 Business Insider reported that xAI had agreed to rent data center capacity to Cursor.[1] Prior to SpaceX's acquisition offer, Cursor had been nearing a $2 billion funding round at a $50 billion valuation from investors including Andreessen Horowitz, Thrive Capital, and Nvidia.[1] In April 2026, ahead of SpaceX's initial public offering, SpaceX and Cursor announced an agreement under which SpaceX would either acquire Cursor for $60 billion in stock or pay a $10 billion break-up fee if the transaction did not proceed.[1]

On June 16, 2026, days after SpaceX's IPO at $135 per share and following SpaceX's earlier 2026 merger with xAI, TechCrunch reported that SpaceX had agreed to acquire Cursor for $60 billion in stock, with SpaceX stating the transaction was expected to close in the third quarter of 2026.[1] As of 2026-11-23, Cursor's public website and documentation present Cursor as integrated into The X Subscription sold by X Subscription Corp. alongside [Grok](https://mimirwiki.com/wiki/grok) and X, linking to SpaceXSI Subscription Terms and listing SpaceXSI among supported model providers, while retaining `Anysphere, Inc.` on its website copyright notice and Privacy Policy.[4][5][8][9]

## Frequently asked questions

### How much does Cursor cost?

As of 2026-11-23, Cursor is sold through The X Subscription with five individual tiers: Free ($0/month), Plus ($8/month or $80/year), Premium ($30/month or $300/year), Super ($100/month or $1,000/year), and Ultra ($200/month or $2,000/year), excluding taxes. Teams seats are priced at $30, $100, or $200 per seat per month, and Enterprise plans use custom pricing. Third-party models on Premium and higher plans are billed separately at API list price from prepaid credit. [4][5]

### What happened to legacy Cursor plans such as Pro and Pro+?

Legacy Cursor plans, including Hobby (Free), Start in India (₹649/month tax inclusive), Pro ($20/month), Pro+ ($60/month), Ultra ($200/month), Teams Standard ($40/user/month), and Teams Premium ($120/user/month), are closed to new customers. Existing subscribers retain their legacy plans, two monthly usage pools, and on-demand billing unless they cancel or choose a permanent switch to The X Subscription. [5][6]

### Which AI models does Cursor support?

As of 2026-11-23, paid plans include a shared weekly pool for Cursor's own models: Grok 4.7, Grok 4.6, Grok 4.5, and Composer 2.5. On Premium and higher plans, Cursor also supports third-party models including Claude (Anthropic), GPT-5.6 (OpenAI), Gemini (Google), and Muse Wonder, billed at API list price from prepaid credit. [3][5]

### How do Cursor's Privacy Mode and security certifications work?

As of 2026-11-23, Cursor holds AIUC-1, ISO/IEC 27001:2022, and ISO/IEC 42001:2023 certifications and a SOC 2 Type II attestation, with supporting documents available on request at trust.cursor.com. Privacy Mode is available on all plans, can be enforced team-wide by administrators, prevents model training on user code data, and runs Voice Chat with zero data retention. [7][8][9]

### What customization and automation features does Cursor include?

Cursor documentation lists six customization mechanisms: Plugins, Rules, Skills, Subagents, Hooks, and Model Context Protocol (MCP) servers. Cursor also includes a command-line interface (CLI), Cloud Agents, Automations, Origin code hosting, Bugbot code reviews, Live Apps, Voice Chat, and the Agent SDK for building and deploying code-defined agents. [3][4][7]

### Who owns Cursor?

Cursor was developed by Anysphere, Inc., which was founded in 2022. On June 16, 2026, TechCrunch reported that SpaceX agreed to acquire Cursor in a $60 billion stock deal expected to close in the third quarter of 2026. As of 2026-11-23, Cursor subscriptions are sold through X Subscription Corp. as part of The X Subscription, while Anysphere, Inc. remains listed on Cursor's Privacy Policy and website copyright notices. [1][4][9]

## Quotable sentences

- Cursor was developed by Anysphere, which was founded in 2022 and participated in OpenAI's startup accelerator in 2024. [1]
- On June 5, 2025, TechCrunch reported that Anysphere raised $900 million at a $9.9 billion valuation and surpassed $500 million in annualized recurring revenue. [2]
- On June 16, 2026, TechCrunch reported that SpaceX agreed to acquire Cursor in a $60 billion stock transaction expected to close in the third quarter of 2026. [1]
- As of 2026-11-23, Cursor is sold directly through X Subscription Corp. as part of The X Subscription with individual monthly tiers at $0 (Free), $8 (Plus), $30 (Premium), $100 (Super), and $200 (Ultra), excluding taxes. [4][5]
- As of 2026-11-23, Cursor Teams and Enterprise plans add a $0.25 per million tokens Cursor Token Rate on eligible third-party model requests and bring-your-own-key usage, while individual plans do not pay this rate. [5]
- Legacy Cursor plans, including Pro at $20 per month and Pro+ at $60 per month, remain active for existing subscribers with two monthly usage pools unless they cancel or permanently switch to The X Subscription. [5][6]
- As of 2026-11-23, Cursor holds AIUC-1, ISO/IEC 27001:2022, and ISO/IEC 42001:2023 certifications and a SOC 2 Type II attestation, and states that it maintains no infrastructure in China. [8]
- Between October and November 2026, Cursor launched the Origin App Marketplace on October 13, released the Agent SDK on October 20, introduced Live Apps on November 5, and launched Voice Chat powered by Grok Voice on November 6. [7]

## Timeline

- 2022: Anysphere, the developer of Cursor, is founded. [1]
- 2024: Anysphere participates in OpenAI's startup accelerator and raises $100 million at a $2.5 billion pre-money valuation in late 2024. [1][2]
- 2025-04: TechCrunch reports that Anysphere reaches $300 million in annualized recurring revenue. [2]
- 2025-06-05: TechCrunch reports that Anysphere raises a $900 million Series C round at a $9.9 billion valuation led by Thrive Capital, with annualized recurring revenue exceeding $500 million. [1][2]
- 2026-04: SpaceX and Cursor announce an agreement for either a $60 billion stock acquisition or a $10 billion break-up fee, alongside reports that xAI rented data center capacity to Cursor. [1]
- 2026-06-16: TechCrunch reports that SpaceX agrees to acquire Cursor for $60 billion in stock, with closing expected in the third quarter of 2026. [1]
- 2026-08-25: Cursor updates its security documentation listing AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 certifications, and SOC 2 Type II attestation. [8]
- 2026-10-13: Cursor launches the Origin App Marketplace with more than 20 partner integrations and opens it to public submissions. [7]
- 2026-10-16: Cursor adds shareable interactive Canvases for cloud agents, the beta Environments API, and support for up to 300 repositories per cloud environment. [7]
- 2026-10-20: Cursor releases the Agent SDK to general availability. [7]
- 2026-11-05: Cursor launches Live Apps deployment from cloud agents on paid plans. [7]
- 2026-11-06: Cursor launches Voice Chat with coding agents powered by Grok Voice and updates its Privacy Policy. [7][9]

## Sources

1. SpaceX to acquire Cursor for $60B in stock, days after blockbuster IPO | TechCrunch. TechCrunch. published 2026-06-16. https://techcrunch.com/2026/06/16/spacex-to-acquire-cursor-for-60b-in-stock-days-after-blockbuster-ipo/ (checked 2026-11-23; tier 2: academic or news)
2. Cursor's Anysphere nabs $9.9B valuation, soars past $500M ARR | TechCrunch. TechCrunch. published 2025-06-05. https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/ (checked 2026-11-23; tier 2: academic or news)
3. Cursor Docs - Agent, Rules, MCP, Skills & CLI. Cursor. https://cursor.com/docs (checked 2026-11-23; tier 3: official site)
4. Cursor · Pricing. Cursor. https://cursor.com/pricing (checked 2026-11-23; tier 3: official site)
5. Models & Pricing | Cursor Docs. Cursor. https://cursor.com/docs/models-and-pricing (checked 2026-11-23; tier 3: official site)
6. Pricing and plans | Cursor Docs. Cursor. https://cursor.com/help/account-and-billing/pricing (checked 2026-11-23; tier 3: official site)
7. What's New in Cursor - Latest Updates & Release Notes. Cursor. https://cursor.com/changelog (checked 2026-11-23; tier 3: official site)
8. Cursor · Security. Cursor. https://cursor.com/security (checked 2026-11-23; tier 3: official site)
9. Cursor · Privacy Policy. Cursor. https://cursor.com/privacy (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Cursor." Version bfb78c26, 2026-11-23. https://mimirwiki.com/wiki/cursor
