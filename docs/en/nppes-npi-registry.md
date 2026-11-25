---
title: "NPPES and the National Provider Identifier (NPI)"
subtitle: "U.S. federal system that assigns 10-digit identifiers to health care providers and publishes them in the NPI Registry"
canonical_url: https://mimirwiki.com/wiki/nppes-npi-registry
language: en
page_class: anchor
revision_sha256: 57c01873ab6f4f967ee752582976f4c4540161d41ae98d1edbb02508fda5bbcb
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/nppes-npi-registry.md
  txt: https://mimirwiki.com/wiki/nppes-npi-registry.txt
  json: https://mimirwiki.com/wiki/nppes-npi-registry.json
  jsonld: https://mimirwiki.com/wiki/nppes-npi-registry.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/nppes-npi-registry
  ja: https://mimirwiki.com/ja/wiki/nppes-npi-registry
  zh: https://mimirwiki.com/zh/wiki/nppes-npi-registry
  es: https://mimirwiki.com/es/wiki/nppes-npi-registry
---

# NPPES and the National Provider Identifier (NPI)

> NPPES is the U.S. Centers for Medicare & Medicaid Services system that assigns National Provider Identifiers (NPIs), the 10-digit HIPAA standard identifiers for health care providers. Its public data can be searched in the NPI Registry, queried through a read-only API and downloaded as monthly and weekly files. An NPI does not confirm that a provider is licensed or credentialed.

The National Plan and Provider Enumeration System (NPPES) is the system through which the U.S. Centers for Medicare & Medicaid Services (CMS) assigns National Provider Identifiers (NPIs) to health care providers. The NPI is the standard unique health identifier for health care providers adopted under the Health Insurance Portability and Accountability Act of 1996 (HIPAA): a 10-position numeric identifier with a check digit in the 10th position and no information about the provider encoded in the number. CMS publishes the publicly disclosable part of each NPPES record through the NPI Registry search site, a read-only API and downloadable files. CMS states that issuance of an NPI does not ensure or validate that a provider is licensed or credentialed.

**Also known as:** NPPES, National Plan and Provider Enumeration System, NPI, National Provider Identifier, NPI Registry, NPPES NPI Registry

## Key facts

- **Identifier format:** 10 numeric digits, the last one a Luhn check digit [4]
- **Operator:** Centers for Medicare & Medicaid Services (CMS) [6]
- **Public API version:** 2.1 (versions 1.0 and 2.0 retired) (as of 2026-11-21) [5]
- **API result limit:** 200 records per request, 1,200 per search using skip (as of 2026-11-21) [5]
- **Bulk file cadence:** Full replacement file monthly, incremental file weekly (as of 2026-11-21) [8]

## Basic facts

- **Full name:** National Plan and Provider Enumeration System [6]
- **Operated by:** Centers for Medicare & Medicaid Services (CMS) [6]
- **Identifier issued:** National Provider Identifier (NPI) [1]
- **Identifier format:** 10-position numeric, check digit in position 10 [3]
- **Check digit algorithm:** Luhn formula (modulus 10 "double-add-double") [4]
- **Legal basis:** HIPAA Administrative Simplification, 45 CFR Part 162 Subpart D [2]
- **Final rule:** 69 FR 3434, published 2004-01-23 [2]
- **Entity types:** Type 1 (individuals), Type 2 (organizations) [10]
- **Public lookup:** NPI Registry, npiregistry.cms.hhs.gov [6]
- **API:** Read-only JSON API, version 2.1 (as of 2026-11-21) [5]
- **Bulk data:** Monthly full replacement file, weekly incremental files, monthly deactivation file, all Version 2 (as of 2026-11-21) [7]
- **Specialty code set:** Health Care Provider Taxonomy, maintained by the National Uniform Claim Committee [11]

## National Provider Identifier format and check digit

The National Provider Identifier (NPI) assigned through NPPES is defined in federal regulation as a numeric identifier of 10 positions, the 10th being a check digit, that carries no intelligence about the health care provider.[3] CMS describes the NPI as intelligence-free: the digits do not encode information such as the state in which a provider lives or the provider's medical specialty.[1]

A CMS requirements document dated January 23, 2004 specifies that the NPI consists of nine numeric digits followed by one check digit, and that NPIs are initially issued with a first digit of 1 or 2 so that they do not collide with other card issuer identifiers.[4] The check digit is computed with the Luhn formula for the modulus 10 "double-add-double" check digit. When an NPI is used as a card issuer identifier on a standard health identification card it is preceded by the prefix 80840, in which 80 indicates health applications and 840 indicates the United States, and the check digit is always calculated as if that prefix were present. For an NPI written without the prefix, this is done by adding the constant 24 to the Luhn sum.[4] In the CMS worked example, the nine-digit identifier 123456789 yields check digit 3 and the NPI 1234567893.[4]

The format rules in the CMS document are summarized below.[4]

| Property | Value |
| --- | --- |
| Length | 10 numeric positions |
| Structure | 9-digit identifier followed by 1 check digit |
| First digit at initial issuance | 1 or 2 |
| Check digit algorithm | Luhn formula (modulus 10 "double-add-double") |
| Card issuer prefix | 80840 |
| Constant added when the prefix is absent | 24 |

## Who must obtain and use a National Provider Identifier

The National Provider Identifier must be obtained by every covered health care provider, a term the NPI Final Rule applies to health care providers that transmit any health information in electronic form in connection with a transaction for which the Secretary of Health and Human Services has adopted a standard.[2] Under 45 CFR 162.410 a covered provider must use its NPI to identify itself on standard transactions, disclose the NPI on request to any entity that needs it for a standard transaction, and report changes in its required data within 30 days of the change.[3] Health plans and health care clearinghouses must use the NPI of any provider that has been assigned one on standard transactions, and a health plan may not require a provider that already has an NPI to obtain another.[3]

A health care provider that is not a covered entity may also obtain an NPI.[3] The regulation further requires an organization that is a covered provider to make sure that prescribers who are its members, employees or contractors, and who are not covered entities themselves, obtain an NPI from NPPES.[3] The Final Rule preamble gives registered nurses, dental hygienists and technicians as examples of people who furnish health care without necessarily conducting covered transactions and who are nonetheless eligible for NPIs.[2]

The NPI Final Rule was published on January 23, 2004 and took effect on May 23, 2005, the first day on which providers could apply. Covered providers, health care clearinghouses and health plans other than small health plans had to comply by May 23, 2007, and small health plans by May 23, 2008.[2] The Final Rule preamble describes the NPI as a lasting identifier. For an individual it is intended to be permanent, and for an organization a new NPI is not required after a change of ownership, name, address or taxonomy classification.[2] A deactivated NPI is not assigned to any other provider.[3]

## NPPES entity types: Type 1 and Type 2 NPIs

NPPES assigns every National Provider Identifier under one of two entity types, chosen on the NPI application. Entity Type 1 covers individuals who render health care, such as physicians, dentists, nurses, chiropractors, pharmacists and physical therapists. Entity Type 2 covers organizations that render health care or furnish health care supplies, such as hospitals, home health agencies, ambulance companies, group practices, health maintenance organizations, durable medical equipment suppliers and pharmacies.[10]

The CMS-10114 application form states that a sole proprietorship is an Entity Type 1 individual and may obtain only one NPI, while an incorporated individual may hold a Type 1 NPI personally and a Type 2 NPI for the corporation.[10] An organization may also obtain separate NPIs for subparts, which the form describes as components of an organization provider that may be at a different location or furnish a different type of health care.[3][10] In the NPI Registry API the two types appear as the values `NPI-1` and `NPI-2`.[5]

Health care providers can apply for an NPI in three ways: online through NPPES, through an Electronic File Interchange organization that submits application data in bulk with the provider's permission, or by mailing the paper form CMS-10114 to the NPI Enumerator.[12] A primary Healthcare Provider Taxonomy code is required, and up to 15 taxonomy codes may be reported.[9] The taxonomy code set is maintained by the National Uniform Claim Committee (NUCC), and each code is a ten-character alphanumeric value organized in three levels: provider grouping, classification and area of specialization.[11]

## NPI Registry search and the NPPES API (version 2.1)

The NPI Registry at npiregistry.cms.hhs.gov is described by CMS as a free directory of all active National Provider Identifier records. It shows the parts of an NPI record that CMS treats as having public relevance, including the provider's name, specialty (taxonomy) and practice address.[6] Records can be searched by NPI number, NPI type, taxonomy description, provider or organization name, authorized official name, city, state, country and postal code. The search returns only the first 2,100 matching results. Since June 25, 2024 NPPES has limited the number of Registry queries that can be completed per hour, although the search page does not state the hourly figure, and the same page states that bulk queries must use the data dissemination file.[6]

The NPPES API is a read-only interface that returns Registry data as JSON and retrieves its data from NPPES daily.[5] As of 2026-11-21 the only supported version is 2.1: CMS states that versions 1.0 and 2.0 are retired and that requests without a version flag no longer work, and it lists the planned phase-out date for version 2.1 as "TBD". The endpoint is `https://npiregistry.cms.hhs.gov/api/?version=2.1`.[5] The request limits documented on the API help page are as follows.[5]

| Item | Value as of 2026-11-21 |
| --- | --- |
| Supported version | 2.1 |
| Default `limit` | 10 |
| Maximum `limit` | 200 results per request |
| Maximum `skip` | 1,000 records |
| Maximum records for one set of criteria | 1,200, over six requests |
| Response format | JSON |

Search parameters documented for version 2.1 include `number`, `enumeration_type`, `taxonomy_description`, `first_name`, `last_name`, `organization_name`, `city`, `state`, `postal_code`, `country_code`, `limit` and `skip`, and the documented list contains no API key or authentication parameter. Name and postal code fields accept a trailing wildcard after at least two characters.[5] The JSON response contains an addresses array whose first entry is the primary practice location and whose second entry is the mailing address, a taxonomies array of up to 15 entries, an other identifiers array of up to 50 entries, and arrays for other names, endpoints and additional practice locations.[5]

## NPPES downloadable data dissemination files

NPPES data are also published as downloadable files. CMS began disclosing NPPES provider data that are disclosable under the Freedom of Information Act (FOIA) in September 2007, in two forms: the NPI Registry, a query-only database updated daily, and the downloadable file. CMS charges nothing to view or download the data.[8] Three kinds of file are produced: a full replacement monthly NPI file, a weekly incremental NPI file and a full replacement NPI deactivation file. The weekly file contains only the data for a given week, including newly assigned NPIs, updates and newly deactivated NPIs, and is meant to be used together with the latest monthly file.[8]

The monthly download is a ZIP archive containing a readme document, a code value document, a header file and a comma-separated data file in which every value is enclosed in double quotes. CMS notes that the data file exceeds 4 GB and that no help desk or technical support is offered for downloading or using it.[8] Since June 18, 2018 each archive has also included three reference files: Other Name, Practice Location and Endpoint.[8] For a deactivated NPI, the files disclose only the NPI and its date of deactivation.[8]

As of 2026-11-21 the NPI Files page offers Version 2 files only. NPPES ended support for Version 1 of the monthly and weekly files effective March 3, 2026, and Version 2 has extended character limits for the First Name and Legal Business Name fields.[7] On 2026-11-21 the page listed a monthly file dated November 9, 2026 (a 1,079.11 MB ZIP), a monthly deactivation update of the same date, and weekly updates covering November 2 to 8 and November 9 to 15, 2026.[7]

## What NPPES and the NPI Registry do not verify

NPPES and the NPI Registry do not verify a provider's license or credentials. The Registry search page, the API help page and the NPI Files page all carry the same CMS notice: "Issuance of an NPI does not ensure or validate that the Health Care Provider is Licensed or Credentialed."[5][6][7] The data in the Registry and in the downloadable files are those reported to NPPES by the provider, by someone acting on the provider's behalf or by an organization's authorized official, and CMS asks providers to correct information that is wrong.[8]

Several NPPES fields that resemble credentials are supplied by providers themselves. The data elements disclosed for individual providers include a license number and a license state code.[9] Taxonomy codes are self-selected by the provider, and NUCC states that scope of licensure is not within the purview of the taxonomy code set.[11] The NPI itself carries no information about specialty or location.[1]

Some NPPES data are never published. Social Security numbers, IRS Individual Taxpayer Identification Numbers and dates of birth were determined not to be disclosable under FOIA and are not released.[9] In the other direction, a provider with an active NPI cannot opt out of disclosure or suppress its record.[8] The 2004 Final Rule preamble also stated that links among the various NPI types would not be maintained in the enumeration system, and that ownership and incorporation information would not be contained in it.[2]

## Frequently asked questions

### What is an NPI number?

A National Provider Identifier (NPI) is the HIPAA standard unique identifier for health care providers in the United States. It is a 10-digit number with a check digit in the last position and no encoded information about the provider, and it is assigned through NPPES, the enumeration system of the Centers for Medicare & Medicaid Services. [1][3][6]

### Does having an NPI mean a provider is licensed?

No. CMS states on the NPI Registry that issuance of an NPI does not ensure or validate that a health care provider is licensed or credentialed. NPPES data are reported by providers themselves, and taxonomy codes are self-selected. [6][8][11]

### How is the NPI check digit calculated?

The tenth digit is a Luhn (modulus 10 "double-add-double") check digit calculated as if the prefix 80840 preceded the number. When the prefix is not written, the constant 24 is added to the Luhn sum. In the CMS example, 123456789 produces check digit 3, giving the NPI 1234567893. [4]

### What is the difference between a Type 1 and a Type 2 NPI?

Entity Type 1 NPIs are issued to individuals who render health care, including sole proprietors, who may obtain only one NPI. Entity Type 2 NPIs are issued to organizations such as hospitals, group practices and pharmacies, and to their subparts. [10]

### What are the limits of the NPI Registry API?

As of 2026-11-21 the API supports only version 2.1, returns at most 200 results per request and lets the skip parameter pass over up to 1,000 records, for a maximum of 1,200 records per set of search criteria. CMS directs bulk users to the downloadable data dissemination file. [5][6]

### How often is NPPES public data updated?

CMS describes the NPI Registry as updated daily, and the API retrieves data from NPPES daily. The full replacement downloadable file is issued monthly and incremental files are issued weekly. [5][8]

## Quotable sentences

- The National Provider Identifier is a 10-position numeric identifier with a check digit in the 10th position. [3]
- The NPI check digit is calculated with the Luhn formula as if the prefix 80840 preceded the number. [4]
- CMS states that issuance of an NPI does not ensure or validate that a health care provider is licensed or credentialed. [6]
- As of 2026-11-21, the NPPES NPI Registry API supports only version 2.1. [5]
- As of 2026-11-21, an NPPES NPI Registry API query returns a maximum of 200 results per request. [5]
- NPPES publishes a full replacement NPI file monthly and an incremental NPI file weekly. [8]
- The NPI Final Rule was published in the Federal Register on January 23, 2004 at 69 FR 3434. [2]
- Social Security numbers, IRS Individual Taxpayer Identification Numbers and dates of birth held in NPPES are not released to the public. [9]

## Timeline

- 2004-01-23: The Department of Health and Human Services publishes the NPI Final Rule (69 FR 3434), adopting the National Provider Identifier as the standard unique health identifier for health care providers. [2]
- 2005-05-23: The NPI Final Rule takes effect and health care providers may begin applying for NPIs. [2]
- 2006-05-01: The Electronic File Interchange process for bulk enumeration becomes available. [9]
- 2007-05-23: Compliance date for covered health care providers, health care clearinghouses and health plans other than small health plans. [2]
- 2007-05-30: CMS publishes the NPPES Data Dissemination Notice (CMS-6060-N) in the Federal Register. [9]
- 2008-05-23: Compliance date for small health plans. [2]
- 2018-06-18: The zipped NPPES downloadable file begins to include the Other Name, Practice Location and Endpoint reference files. [8]
- 2024-06-25: NPPES begins limiting the number of NPI Registry queries that can be completed per hour. [6]
- 2026-03-03: NPPES ends support for Version 1 of the monthly and weekly downloadable files. [7]

## Sources

1. National Provider Identifier Standard (NPI) | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/regulations-and-guidance/administrative-simplification/nationalprovidentstand (checked 2026-11-21; tier 1: government or public registry)
2. HIPAA Administrative Simplification: Standard Unique Health Identifier for Health Care Providers. Federal Register, Department of Health and Human Services. published 2004-01-23. https://www.federalregister.gov/documents/2004/01/23/04-1149/hipaa-administrative-simplification-standard-unique-health-identifier-for-health-care-providers (checked 2026-11-21; tier 1: government or public registry)
3. 45 CFR Part 162 Subpart D: Standard Unique Health Identifier for Health Care Providers. Electronic Code of Federal Regulations (eCFR). https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-162/subpart-D (checked 2026-11-21; tier 1: government or public registry)
4. Requirements for National Provider Identifier (NPI) and NPI Check Digit. Centers for Medicare & Medicaid Services. published 2004-01-23. https://www.cms.gov/Regulations-and-Guidance/Administrative-Simplification/NationalProvIdentStand/Downloads/NPIcheckdigit.pdf (checked 2026-11-21; tier 1: government or public registry)
5. NPPES NPI Registry: NPPES API Help. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/api-page (checked 2026-11-21; tier 1: government or public registry)
6. NPPES NPI Registry: Search NPI Records. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/search (checked 2026-11-21; tier 1: government or public registry)
7. NPI Files. Centers for Medicare & Medicaid Services. https://download.cms.gov/nppes/NPI_Files.html (checked 2026-11-21; tier 1: government or public registry)
8. Data Dissemination | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination (checked 2026-11-21; tier 1: government or public registry)
9. HIPAA Administrative Simplification: National Plan and Provider Enumeration System Data Dissemination. Federal Register, Centers for Medicare & Medicaid Services. published 2007-05-30. https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination (checked 2026-11-21; tier 1: government or public registry)
10. CMS-10114 National Provider Identifier (NPI) Application/Update Form. Centers for Medicare & Medicaid Services. https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/downloads/CMS10114.pdf (checked 2026-11-21; tier 1: government or public registry)
11. National Uniform Claim Committee - Provider Taxonomy. National Uniform Claim Committee. https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40 (checked 2026-11-21; tier 3: official site)
12. How to Apply | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/how-apply (checked 2026-11-21; tier 1: government or public registry)

## Cite this page

Mimirwiki. "NPPES and the National Provider Identifier (NPI)." Version 57c01873, 2026-11-24. https://mimirwiki.com/wiki/nppes-npi-registry
