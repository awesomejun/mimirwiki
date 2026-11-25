---
title: "Microsoft 365"
subtitle: "Microsoft cloud productivity suite combining Office apps, Exchange Online, and Teams"
canonical_url: https://mimirwiki.com/wiki/microsoft-365
language: en
page_class: entity
revision_sha256: 55c703ec42927320556202ba719f63745b26c169d3a46dcdd5b8e260197cb145
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/microsoft-365.md
  txt: https://mimirwiki.com/wiki/microsoft-365.txt
  json: https://mimirwiki.com/wiki/microsoft-365.json
  jsonld: https://mimirwiki.com/wiki/microsoft-365.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/microsoft-365
---

# Microsoft 365

> Microsoft 365 bundles Office apps with cloud services including Exchange Online and Teams. A public copy of Microsoft's 2026-11-20 Post Incident Report attributes the 2026-11-12 outage (EX1550543/MO1550821) to a latent Windows defect in Exchange Online gateway servers under combined maintenance, shifted Teams traffic, and peak load; service status can be checked in the Microsoft 365 admin center, on Microsoft's public service status page, or via @MSFT365status on X.

Microsoft 365 is Microsoft's cloud productivity suite for organizations and individuals, combining Office on the web, Microsoft Teams, Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft 365 Copilot. On 2026-11-12, a latent Windows defect in Exchange Online network gateway servers triggered a major Microsoft 365 outage, followed by 2026-11-24 Reuters reporting that Microsoft declared an internal 'Code Red' to overhaul incident prevention and recovery.

**Also known as:** M365, Office 365

## Key facts

- **Developer:** Microsoft Corporation [1]
- **Service health channels:** Microsoft 365 admin center (admin.microsoft.com), public service status page, @MSFT365status on X [2]
- **Nov 2026 outage IDs:** EX1550543 / MO1550821 (began 2026-11-12; active impact ended 2026-11-13 at 4:10 PM) (as of 2026-11-25) [4]
- **Reported internal response:** Reuters reported on 2026-11-24 that Microsoft declared a 'Code Red' citing internal memos (as of 2026-11-25) [5]

## Basic facts

- **Product name:** Microsoft 365 [1]
- **Developer:** Microsoft Corporation [1]
- **Core cloud services:** Exchange Online, Microsoft Teams, Office on the web, SharePoint Online, OneDrive for Business, Copilot [2]
- **Messaging backend:** Exchange Online (email, calendar, contacts, tasks; integrated with Microsoft Entra ID) [3]
- **Admin status portal:** https://admin.microsoft.com (Service health page) [2]
- **Nov 2026 Post Incident Report:** EX1550543 / MO1550821 (dated 2026-11-20) [4]

## Microsoft 365 platform overview

Microsoft 365 is a subscription-based cloud solution built by Microsoft to support communication, collaboration, and document productivity across organizations.[1][2] Core services monitored under Microsoft 365 include Office on the web, Microsoft Teams, Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft 365 Copilot.[2][4]

Exchange Online serves as Microsoft 365's hosted messaging service, delivering email, calendar, contacts, and tasks across PCs, web browsers, and mobile devices while integrating with Microsoft Entra ID for identity and policy administration.[3]

## Microsoft 365 November 12, 2026 Exchange Online outage

Microsoft 365 experienced a widespread service disruption starting on November 12, 2026, tracked under incident IDs EX1550543 and MO1550821.[4] According to a publicly hosted copy of Microsoft's November 20, 2026 Post Incident Report, a latent Windows defect specific to an Exchange Online configuration (and not present in standard Windows deployments) caused Microsoft 365 network gateway servers used by Exchange Online to become unresponsive under load.[4]

The report stated that three combined operational conditions exposed the defect: reduced production capacity from planned maintenance, a shift of Microsoft Teams traffic to the Exchange Online gateways, and peak North American traffic.[4] Automatic traffic redistribution then spread load to remaining healthy servers worldwide, disrupting Exchange Online mailbox access and dependent capabilities across Copilot, Teams, SharePoint Online, OneDrive for Business, Defender, Purview, Fabric, Intune, Planner, Power Apps, To Do, Power BI, and Universal Print.[4]

Microsoft extended Exchange Online's email retry delivery window to 48 hours so queued messages would not be returned as undeliverable, confirmed active customer impact ended on November 13 at 4:10 PM, and issued final customer updates on November 14 at 4:15 AM.[4] Planned remediation items in the report target CY26 Q4 and CY27 Q1, including isolating network gateway pools by workload, limiting Teams failover to affected regions, and expanding peak-load testing.[4]

## Microsoft 365 'Code Red' media reports

Microsoft 365 drew renewed attention on November 24 and 25, 2026, after Reuters reported, citing internal memos, that Microsoft declared a 'Code Red' to overhaul how it prevents and responds to major outages.[5][7] According to coverage of the Reuters exclusive by The Next Web and 9to5Mac, M365 Core President Jason Henderson described the outage as the most customer-impacting incident in Exchange Online's history and stated that 'Code Red' made the effort the team's highest priority.[5][6]

The same reporting cited a memo from Corporate Vice President Amanda Silver describing a 'fog of war' during incident response, with responders exchanging more than 11,000 messages across 11 Teams chats while diagnostic data sat in separate internal tracking systems.[5] 9to5Mac also reported that more than 80 percent of gateway servers were unresponsive at peak and that Microsoft is working toward resolving future incidents in under an hour.[6] Microsoft has not publicly released the full internal memos or a total count of affected users.[5]

## Microsoft 365 service health monitoring

Microsoft 365 administrators can check whether an issue is a known service incident on the Service health page inside the Microsoft 365 admin center at admin.microsoft.com.[2] Microsoft documentation notes that accounts assigned the Service Support admin or Helpdesk admin role can view service health updates directly in the admin center.[2]

If users or administrators cannot sign in to the Microsoft 365 admin center during an outage, Microsoft directs them to check the public Microsoft service status page for known sign-in issues and to follow @MSFT365status on X for updates on selected events.[2]

## Frequently asked questions

### Why were Outlook, Teams, and Copilot affected at the same time during the November 12, 2026 Microsoft 365 outage?

According to a public copy of Microsoft's November 20, 2026 Post Incident Report (EX1550543/MO1550821), a latent Windows defect caused Exchange Online network gateway servers to fail under combined maintenance, shifted Teams traffic, and peak North American load, which disrupted Exchange Online and dependent features in Teams, Copilot, SharePoint, OneDrive, and other Microsoft 365 services. [4]

### Where can users and admins check Microsoft 365 outage status?

Administrators can view the Service health page in the Microsoft 365 admin center (admin.microsoft.com). If sign-in to the admin center is unavailable, Microsoft recommends checking its public service status page or @MSFT365status on X. [2]

### What is the Microsoft 365 'Code Red' reported in November 2026?

Reuters reported on November 24, 2026, citing internal memos, that Microsoft declared a 'Code Red' highest-priority engineering effort to improve outage prevention, diagnostics, and recovery speed after the November 12-13 Exchange Online outage. The full internal memos have not been publicly released. [5][6][7]

### What long-term fixes are listed in Microsoft's November 20, 2026 Post Incident Report?

The public copy of the report lists CY26 Q4 and CY27 Q1 engineering actions including isolating network gateway capacity pools by workload, limiting Teams failover to affected regions, fixing cross-region traffic cascade, and expanding peak-load testing. [4]

## Quotable sentences

- A publicly hosted copy of Microsoft's 2026-11-20 Post Incident Report (EX1550543/MO1550821) states that a latent Windows defect in Exchange Online gateway servers triggered the 2026-11-12 outage affecting Exchange Online and dependent Microsoft 365 services. [4]
- Microsoft confirmed active customer impact ended on 2026-11-13 at 4:10 PM and issued final incident updates on 2026-11-14 at 4:15 AM. [4]
- Reuters reported on 2026-11-24, citing internal memos, that Microsoft declared a 'Code Red' after the outage; full internal memos and total affected user counts have not been published by Microsoft. [5][6][7]
- Microsoft 365 administrators can monitor known service incidents via the Service health page in the Microsoft 365 admin center (admin.microsoft.com), the public service status page, or @MSFT365status on X. [2]

## Sources

1. Microsoft 365 for enterprise overview. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide (checked 2026-11-25; tier 3: official site)
2. How to check Microsoft 365 service health. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-365/enterprise/view-service-health?view=o365-worldwide (checked 2026-11-25; tier 3: official site)
3. Exchange Online service description. Microsoft Learn. https://learn.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description (checked 2026-11-25; tier 3: official site)
4. Post Incident Report for Microsoft 365 (EX1550543 / MO1550821, Public Copy). Microsoft Corporation (hosted by 365fanatic.com). published 2026-11-20. https://www.365fanatic.com/wp-content/uploads/2026/11/postincidentreport-mo1550821.pdf (checked 2026-11-25; tier 2: academic or news)
5. Microsoft declares 'Code Red' after its worst email outage, Reuters reports. The Next Web. published 2026-11-24. https://thenextweb.com/news/microsoft-code-red-exchange-online-outage-memos-reuters (checked 2026-11-25; tier 2: academic or news)
6. Microsoft declares a Code Red in response to worst ever outage. 9to5Mac. published 2026-11-25. https://9to5mac.com/2026/11/25/microsoft-declares-a-code-red-in-response-to-worst-ever-outage/ (checked 2026-11-25; tier 2: academic or news)
7. Microsoft declares 'Code Red' after historic outage, internal memos show: Reuters exclusive. CTV News (Reuters). published 2026-11-24. https://www.ctvnews.ca/sci-tech/article/microsoft-declares-code-red-after-historic-outage-internal-memos-show-reuters-exclusive/ (checked 2026-11-25; tier 2: academic or news)

## Cite this page

Mimirwiki. "Microsoft 365." Version 55c703ec, 2026-11-25. https://mimirwiki.com/wiki/microsoft-365
