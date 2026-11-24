---
title: "SEC EDGAR"
subtitle: "Electronic filing and public disclosure system of the U.S. Securities and Exchange Commission"
canonical_url: https://mimirwiki.com/wiki/sec-edgar
language: en
page_class: anchor
revision_sha256: 819e703b233d7c5b13fa9831b96d28569fd7ea133b8623d39c098d2c64c2e31b
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/sec-edgar.md
  txt: https://mimirwiki.com/wiki/sec-edgar.txt
  json: https://mimirwiki.com/wiki/sec-edgar.json
  jsonld: https://mimirwiki.com/wiki/sec-edgar.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/sec-edgar
  ja: https://mimirwiki.com/ja/wiki/sec-edgar
  zh: https://mimirwiki.com/zh/wiki/sec-edgar
---

# SEC EDGAR

> EDGAR (Electronic Data Gathering, Analysis, and Retrieval) is the U.S. Securities and Exchange Commission's primary system for submitting securities filings such as Forms 10-K, 10-Q and 8-K. Its public database is free to search, and each filer is identified by a Central Index Key (CIK). The data.sec.gov JSON APIs need no API key, with automated access limited to 10 requests per second.

EDGAR (Electronic Data Gathering, Analysis, and Retrieval) is the primary system of the U.S. Securities and Exchange Commission (SEC) through which companies and others submit documents under the Securities Act of 1933, the Securities Exchange Act of 1934, the Trust Indenture Act of 1939 and the Investment Company Act of 1940. Access to EDGAR's public database is free. EDGAR assigns each filer a Central Index Key (CIK) and each accepted submission an accession number. The SEC also publishes filing histories and extracted XBRL financial data as JSON through REST APIs on data.sec.gov, which require no authentication or API key.

**Also known as:** EDGAR, Electronic Data Gathering, Analysis, and Retrieval, SEC EDGAR database, EDGAR filing system, data.sec.gov

## Key facts

- **Operator:** U.S. Securities and Exchange Commission (EDGAR Business Office) [1]
- **Filer identifier:** Central Index Key (CIK), zero-padded to 10 digits in API URLs [2]
- **Request rate limit:** 10 requests per second per user (as of 2026-11-21) [3]
- **API authentication:** None, no API key required (as of 2026-11-21) [2]
- **Full-text search coverage:** Electronic filings since 2001 (as of 2026-11-21) [6]

## Basic facts

- **Full name:** Electronic Data Gathering, Analysis, and Retrieval [1]
- **Operator:** U.S. Securities and Exchange Commission [1]
- **Administered by:** EDGAR Business Office [1]
- **Filer identifier:** Central Index Key (CIK) [3]
- **Submission identifier:** Accession number, for example 0001193125-15-118890 [3]
- **Public access:** Free [1]
- **Data APIs:** data.sec.gov REST APIs returning JSON: submissions, company concept, company facts, frames [2]
- **API authentication:** None required (as of 2026-11-21) [2]
- **Rate limit:** 10 requests per second (as of 2026-11-21) [3]
- **Filing hours:** Business days, 6:00 a.m. to 10:00 p.m. Eastern Time [3]
- **Full-text search coverage:** Electronic filings since 2001 [6]
- **Filer login:** Login.gov individual account credentials with multifactor authentication [7]

## What SEC EDGAR is and who files on it

EDGAR, the Electronic Data Gathering, Analysis, and Retrieval system, is described by the SEC as the primary system for companies and others submitting documents under the Securities Act of 1933, the Securities Exchange Act of 1934, the Trust Indenture Act of 1939 and the Investment Company Act of 1940.[1] An SEC page last reviewed on November 28, 2025 states that the system handles about 4,700 filings a day, delivers 3,000 terabytes of data to the public each year and takes on an average of 40,000 new filers annually.[1] The EDGAR Business Office is the business owner of the system and is responsible for its governance, strategic planning and filer support.[1]

The SEC states that foreign and domestic companies alike must file registration statements, periodic reports and other forms electronically through EDGAR, and that the information can be accessed and downloaded by anyone at no charge.[3] Besides company filings, the public database holds information provided by mutual funds, exchange-traded funds, variable annuities and individuals.[1] EDGAR accepts new filings each business day, Monday through Friday, from 6:00 a.m. to 10:00 p.m. Eastern Time. Some submissions that begin after 5:30 p.m. Eastern Time, or after 10:00 p.m. for ownership Forms 3, 4 and 5, are disseminated on the next business day.[3]

The SEC began developing an electronic disclosure system in 1983 and made the operational EDGAR system available to volunteer filers on July 15, 1992. Rules issued on February 23, 1993 required electronic filing, with a phase-in that began on April 26, 1993, and rules requiring foreign issuers to file through EDGAR took effect on November 4, 2002.[9] The SEC's data access page states that EDGAR started in 1994/1995 and that its index files list all public filings from the third quarter of 1994 onward.[3]

## EDGAR identifiers: CIK and accession numbers

EDGAR assigns each filer a unique numerical identifier, the Central Index Key (CIK), when the filer signs up to make filings with the SEC. CIK numbers remain unique to the filer and are not recycled.[3] Filers include companies, funds and individuals, and a single CIK can be associated with more than one name when a company or fund has changed its name.[3] In data.sec.gov API URLs the CIK is written as 10 digits, padded with zeros at the front.[2]

Each accepted submission receives an accession number, a unique identifier assigned automatically by EDGAR. In the SEC's example, 0001193125-15-118890, the first ten digits are the CIK of the entity that submitted the filing, which may be the company or a third-party filer agent, the next two digits are the year, and the final group is a sequential count of submissions from that CIK. The count is usually, but not always, reset at the start of each calendar year.[3] The two identifier formats are summarized below.[2][3]

| Identifier | Written form in SEC documentation | Identifies |
| --- | --- | --- |
| Central Index Key (CIK) | `CIK##########` in API URLs, zero-padded to 10 digits | A filer: company, fund or individual |
| Accession number | `0001193125-15-118890`: submitter CIK, two-digit year, sequence count | One accepted submission |

Filing documents are stored under paths built from both identifiers. In the SEC's example path `/Archives/edgar/data/1122304/000119312515118890/`, the first directory is the CIK directory and the second is the accession number without dashes, a form available for filings made after May 26, 2000. Directory browsing is allowed for CIK and accession number directories, but the parent `/Archives/edgar/data/` directory is not browsable.[3] The SEC also publishes `company_tickers.json`, a file associating tickers, CIKs and company names, which it updates periodically without guaranteeing accuracy or scope.[3]

## Common EDGAR form types

EDGAR identifies each filing by a form type, and a form type with "/A" appended, such as 10-K/A, marks an amendment.[5] The form types below are among those the SEC describes in its guidance on researching filings and on Form D.[5][11]

| Form type | Description |
| --- | --- |
| 10-K | Annual report with audited annual financial statements |
| 10-Q | Quarterly report with unaudited quarterly financial statements |
| 8-K | Current report on material events or information, made public before the next periodic report |
| S-1 | Registration statement for the offer and sale of securities to the public, often for an initial public offering |
| 4 | Statement of changes in beneficial ownership by a corporate insider, due within two business days of the transaction |
| 20-F | Annual report or registration statement of a foreign private issuer |
| D | Notice of an exempt offering of securities under Regulation D |

Form D on EDGAR is a notice of an exempt offering that Regulation D requires to be filed with the SEC, and it must be filed within 15 days after the first sale of securities. According to an SEC page last reviewed on April 24, 2026, the SEC does not charge fees to open or maintain an EDGAR account or to file a Form D notice or amendment.[11] A company needs an EDGAR account, and with it a CIK, before it can file a Form D.[11]

Financial statements in several EDGAR form types are also available as structured data. The data.sec.gov XBRL APIs cover Forms 10-Q, 10-K, 8-K, 20-F, 40-F and 6-K and their variants, and the SEC states that it first required XBRL in 2009.[2] The SEC describes XBRL as an XML-based format for reporting financial statements, filed either as a separate XML file or embedded in HTML reports as inline XBRL.[2]

## data.sec.gov APIs, XBRL frames and SEC fair access rules

The SEC hosts RESTful APIs on data.sec.gov that deliver EDGAR data as JSON. As of 2026-11-21 these APIs require no authentication or API key, and they cover each filer's submission history and the XBRL data from financial statements.[2] The documented endpoints are listed below.[2]

| Endpoint | Returns |
| --- | --- |
| `https://data.sec.gov/submissions/CIK##########.json` | Filing history of one entity, with metadata such as current name, former names, exchanges and ticker symbols |
| `https://data.sec.gov/api/xbrl/companyconcept/CIK##########/us-gaap/AccountsPayableCurrent.json` | All XBRL disclosures of one concept by one company |
| `https://data.sec.gov/api/xbrl/companyfacts/CIK##########.json` | All company concept data for one company in a single call |
| `https://data.sec.gov/api/xbrl/frames/us-gaap/AccountsPayableCurrent/USD/CY2019Q1I.json` | One fact per reporting entity for the requested calendar period |

The submissions endpoint returns at least one year of filings or the 1,000 most recent filings, whichever is more, and points to additional files for older filings. The frames endpoint takes a period written as `CY####` for annual data, `CY####Q#` for quarterly data or `CY####Q#I` for instantaneous data, and returns the fact from each entity that most closely fits that calendar period. The XBRL endpoints aggregate only facts that use a non-custom taxonomy, such as us-gaap, ifrs-full, dei or srt, and that apply to the entire filing entity.[2] The APIs are updated in real time as filings are disseminated, with a typical processing delay of less than a second for submissions and under a minute for XBRL data, and bulk archives of both data sets (`submissions.zip` and `companyfacts.zip`) are republished nightly at about 3:00 a.m. Eastern Time.[2]

Automated access to EDGAR is subject to the SEC's fair access rules. As of 2026-11-21 the maximum request rate is 10 requests per second, and the SEC asks automated clients to declare a user agent in their request headers. Its sample `User-Agent` value consists of a company name followed by an administrative contact email address.[3] The limit applies to each user regardless of the number of machines used, and the SEC reserves the right to block IP addresses that submit excessive requests.[4] data.sec.gov does not support CORS, and the SEC states that it cannot provide technical support for developing or debugging scripted downloading processes.[2]

## EDGAR Next filer access and account management changes

EDGAR Next is the SEC's name for rule and form amendments on EDGAR filer access and account management that the Commission adopted on September 27, 2024.[8] The amendments require filers to authorize identified individuals to manage their EDGAR accounts, and require individuals acting for a filer to present individual account credentials obtained from Login.gov. They also modernized Form ID, the application for EDGAR access, and introduced optional APIs through which filers can make submissions, retrieve information and perform account management tasks.[8] Compliance with the amended Form ID was required on March 24, 2025, the date on which all the amendments became effective, and compliance with all the amendments was required by September 15, 2025.[8]

The SEC's EDGAR Next page, last reviewed on December 22, 2025, states that compliance with EDGAR Next is required to file on EDGAR and that enrollment has closed. A filer must either have enrolled in EDGAR Next or have had a Form ID application granted on or after March 24, 2025, and a filer without access applies by submitting Form ID on the EDGAR Filer Management website.[7] Logging in to any of the three EDGAR websites (EDGAR Filer Management, EDGAR Online Forms and EDGAR Filing) requires Login.gov individual account credentials and multifactor authentication, and legacy login methods have been discontinued.[7] The filer-side APIs are documented separately from the public data.sec.gov APIs, in guides that cover filer and user API tokens.[2]

## What an EDGAR filing does not establish

The presence of a filing on SEC EDGAR does not mean that the SEC has verified its contents. The SEC's Division of Corporation Finance reviews filings selectively, and it states that its review process "is not a guarantee that the disclosure is complete and accurate": responsibility for complete and accurate disclosure lies with the company and others involved in preparing its filings.[10] Under the Sarbanes-Oxley Act of 2002, each reporting company receives some level of Division review at least once every three years. The Division adds that it neither assesses the merits of a transaction nor decides whether an investment suits a particular investor.[10]

An EDGAR filing is also not evidence of registration or approval. The SEC's investor education site, Investor.gov, states that making a filing with the SEC does not make an individual or firm registered with the SEC, and that the SEC does not issue registration certificates.[12] The same page notes that a Form D filing says nothing about whether an individual or firm is registered or licensed with the SEC.[12]

EDGAR's public tools also have coverage limits. Full-text search covers only filings submitted electronically since 2001, including attachments such as exhibits.[6] Some filings are still submitted on paper and are not accessible through EDGAR, and SEC staff may remove or correct a filing after acceptance at the filer's request, for example when a document was submitted for the wrong filer or duplicated an earlier one.[3]

## Frequently asked questions

### What is a CIK number?

A Central Index Key (CIK) is the unique numerical identifier that EDGAR assigns to a filer when it signs up to make filings with the SEC. CIK numbers are not recycled, and the data.sec.gov APIs write them zero-padded to 10 digits. [3][2]

### Do the SEC EDGAR APIs require an API key?

No. As of 2026-11-21 the SEC states that the data.sec.gov APIs require no authentication or API keys. Automated requests are limited to 10 requests per second, and the SEC asks clients to declare a user agent in the request headers. [2][3]

### Does the SEC verify the accuracy of filings on EDGAR?

The SEC's Division of Corporation Finance reviews filings selectively and states that its review process is not a guarantee that disclosure is complete and accurate. Responsibility for complete and accurate disclosure lies with the company and others involved in preparing its filings. [10]

### How far back do EDGAR filings go?

The SEC states that EDGAR started in 1994/1995, and its index files list public filings from the third quarter of 1994 onward. Full-text search covers electronic filings submitted since 2001. [3][6]

### What is EDGAR Next?

EDGAR Next is the set of rule and form amendments on filer access and account management that the SEC adopted on September 27, 2024. The amendments became effective on March 24, 2025, with compliance required by September 15, 2025, and logging in to EDGAR now requires Login.gov individual account credentials with multifactor authentication. [8][7]

### What is the difference between Forms 10-K, 10-Q and 8-K?

Form 10-K is the annual report with audited financial statements, and Form 10-Q is the quarterly report with unaudited financial statements. Form 8-K is a current report that discloses material events or information before the next scheduled quarterly or annual report. [5]

## Quotable sentences

- EDGAR stands for Electronic Data Gathering, Analysis, and Retrieval. [1]
- CIK numbers assigned by EDGAR remain unique to the filer and are not recycled. [3]
- As of 2026-11-21, the SEC's data.sec.gov APIs require no authentication or API keys. [2]
- As of 2026-11-21, the SEC's maximum request rate for automated access to EDGAR is 10 requests per second. [3]
- EDGAR full-text search covers filings submitted electronically since 2001. [6]
- The SEC adopted the EDGAR Next rule and form amendments on September 27, 2024. [8]
- The SEC's Division of Corporation Finance states that its filing review process is not a guarantee that disclosure is complete and accurate. [10]
- A Form D must be filed within 15 days after the first sale of securities. [11]

## Timeline

- 1992-07-15: The operational EDGAR system becomes available to filers on a voluntary basis. [9]
- 1993-02-23: The SEC issues releases adopting interim rules that require electronic filing. [9]
- 1993-04-26: The phase-in of filers onto the EDGAR system begins. [9]
- 1994-12-19: SEC Release No. 33-7122 makes the interim EDGAR rules final and applicable to all domestic registrants. [9]
- 1999-06-28: EDGAR begins accepting live filings submitted in HTML. [9]
- 2002-11-04: Rules requiring foreign issuers to make their SEC filings through EDGAR take effect. [9]
- 2024-09-27: The SEC adopts the EDGAR Next rule and form amendments on filer access and account management. [8]
- 2025-03-24: The EDGAR Next amendments become effective and compliance with the amended Form ID is required. [8]
- 2025-09-15: Compliance with all EDGAR Next rule and form amendments is required. [8]

## Sources

1. SEC.gov | About EDGAR. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/about-edgar (checked 2026-11-21; tier 1: government or public registry)
2. SEC.gov | EDGAR Application Programming Interfaces (APIs). U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-application-programming-interfaces (checked 2026-11-21; tier 1: government or public registry)
3. SEC.gov | Accessing EDGAR Data. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data (checked 2026-11-21; tier 1: government or public registry)
4. SEC.gov | Developer Resources. U.S. Securities and Exchange Commission. https://www.sec.gov/about/developer-resources (checked 2026-11-21; tier 1: government or public registry)
5. SEC.gov | Using EDGAR to Research Investments. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/using-edgar-research-investments (checked 2026-11-21; tier 1: government or public registry)
6. SEC.gov | EDGAR Full Text Search FAQ. U.S. Securities and Exchange Commission. https://www.sec.gov/edgar/search/efts-faq.html (checked 2026-11-21; tier 1: government or public registry)
7. SEC.gov | EDGAR Next: Improving Filer Access and Account Management. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/improving-edgar/edgar-next-improving-filer-access-account-management (checked 2026-11-21; tier 1: government or public registry)
8. SEC.gov | SEC Adopts Improvements to EDGAR System to Enhance Security, Filer Access, and Account Management. U.S. Securities and Exchange Commission. published 2024-09-27. https://www.sec.gov/newsroom/press-releases/2024-155 (checked 2026-11-21; tier 1: government or public registry)
9. Electronic Filing and EDGAR (October 2006). U.S. Securities and Exchange Commission. published 2006-10-03. https://www.sec.gov/info/edgar/regoverview.htm (checked 2026-11-21; tier 1: government or public registry)
10. SEC.gov | Filing Review Process. U.S. Securities and Exchange Commission. https://www.sec.gov/divisions/corpfin/cffilingreview.htm (checked 2026-11-21; tier 1: government or public registry)
11. SEC.gov | What is Form D?. U.S. Securities and Exchange Commission. https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/what-form-d (checked 2026-11-21; tier 1: government or public registry)
12. False Claims of SEC Registration | Investor.gov. U.S. Securities and Exchange Commission, Investor.gov. https://www.investor.gov/protect-your-investments/fraud/types-fraud/false-claims-sec-registration (checked 2026-11-21; tier 1: government or public registry)

## Cite this page

Mimirwiki. "SEC EDGAR." Version 819e703b, 2026-11-21. https://mimirwiki.com/wiki/sec-edgar
