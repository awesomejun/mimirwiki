---
title: "Schema.org"
subtitle: "Shared structured data vocabulary for marking up web pages for search engines and other applications"
canonical_url: https://mimirwiki.com/wiki/schema-org
language: en
page_class: anchor
revision_sha256: 991456cc61cbcf701004643a4420d9c86051b24e9fbb2c185298cfbafe973973
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/schema-org.md
  txt: https://mimirwiki.com/wiki/schema-org.txt
  json: https://mimirwiki.com/wiki/schema-org.json
  jsonld: https://mimirwiki.com/wiki/schema-org.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/schema-org
  ja: https://mimirwiki.com/ja/wiki/schema-org
  zh: https://mimirwiki.com/zh/wiki/schema-org
---

# Schema.org

> Schema.org is a shared structured data vocabulary founded in 2011 by Google, Microsoft, Yahoo, and Yandex for describing entities such as products, recipes, events, and organizations on web pages. Publishers encode it with JSON-LD, Microdata, or RDFa. As of Version 30.1 (2026-09-16), the vocabulary defines 826 types and 1,540 properties under CC BY-SA 3.0.

Schema.org is a collaborative vocabulary of types and properties used to embed structured data in web pages for search engines and other applications. Founded in 2011 by Google, Microsoft, Yahoo, and Yandex, the project maintains a shared multiple-inheritance hierarchy derived from RDF Schema and publishes its canonical machine representation in RDF/Turtle. Web publishers encode Schema.org terms in HTML pages using JSON-LD, Microdata, or RDFa, and as of Version 30.1 (released on 2026-09-16), the vocabulary defines 826 types, 1,540 properties, 19 datatypes, 96 enumerations, and 544 enumeration members. Day-to-day evolution is coordinated through the W3C Schema.org Community Group and its public GitHub repository, while a Steering Group approves formal releases.

**Also known as:** schema.org, Schema.org vocabulary, Schema markup

## Key facts

- **Founded:** 2011 (Google, Microsoft, Yahoo, Yandex) [4]
- **Latest release:** Version 30.1 (2026-09-16) (as of 2026-11-23) [2]
- **Vocabulary size:** 826 types, 1,540 properties, 19 datatypes, 96 enumerations, 544 enumeration members (as of 2026-11-23) [3]
- **Supported encodings:** JSON-LD, Microdata, RDFa [5]
- **Schema license:** Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0) [6]

## Basic facts

- **Type:** Shared structured data vocabulary for the Web [1]
- **Founded:** 2011 [4]
- **Founding companies:** Google, Microsoft, Yahoo, Yandex [1]
- **Governance:** Schema.org Steering Group and W3C Schema.org Community Group [1]
- **Steering Group chair:** R.V. Guha (as of 2026-11-23) [1]
- **Community Group:** W3C Schema.org Community Group (510 participants; launched 2015-03-31) (as of 2026-11-23) [7]
- **Latest release:** Version 30.1 (2026-09-16) (as of 2026-11-23) [2]
- **Vocabulary size:** 826 types, 1,540 properties, 19 datatypes, 96 enumerations, 544 enumeration members (as of 2026-11-23) [3]
- **Canonical representation:** RDF/Turtle [4]
- **Markup formats:** JSON-LD, Microdata, RDFa [5]
- **Licenses:** CC BY-SA 3.0 (schemas, documentation, examples); Apache-2.0 (site software) [6]
- **Repository:** github.com/schemaorg/schemaorg (5,741 commits, 6.3k stars) (as of 2026-11-23) [8]

## What Schema.org is

Schema.org is a collaborative, community activity that creates, maintains, and promotes schemas for structured data on the Internet.[1] Google, Microsoft, Yahoo, and Yandex founded Schema.org in 2011 as a joint effort in the spirit of [sitemaps](https://mimirwiki.com/wiki/sitemaps) (`sitemaps.org`) so that webmasters could adopt one shared markup vocabulary understood across major search engines.[4][6] The domain name `schema.org` was contributed by the OpenDomain project.[6]

Standard HTML elements tell browsers how to render page content, such as formatting a heading with an `h1` element, while leaving the underlying entity type ambiguous.[5] Schema.org adds explicit machine-readable labels for entities such as movies, people, organizations, products, and events so search engines and other software can interpret page content consistently across sites, reducing reliance on error-prone automated extraction.[5][6] Many early terms drew inspiration from prior efforts including Microformats, FOAF, and OpenCyc.[6]

Schema.org operates as a collaborative initiative documenting schemas supported by participating search engines, separate from formal standards bodies such as the W3C or IETF.[6] Web pages written in any human language can include Schema.org markup, while the vocabulary terms themselves and the Schema.org site documentation are written in English.[6] Alongside protocols such as Facebook Open Graph, Schema.org provides granular markup for describing multiple distinct entities and components on a single web page.[6]

## Schema.org data model and vocabulary structure

Schema.org uses a generic data model derived from RDF Schema, which itself derives from CycL.[4] Its schemas are organized as a multiple-inheritance hierarchy of types in which each type can inherit properties from multiple parent types.[4] The broadest root type is `Thing`, which provides core properties such as `name`, `description`, `url`, and `image`, while more specific types inherit from broader parents; for example, `LocalBusiness` is a subtype of both `Place` and `Organization`.[5]

Properties in Schema.org can have multiple domains (`domainIncludes`) and multiple ranges (`rangeIncludes`), a pragmatic design choice that avoids creating artificial intermediate types solely to group properties.[4] Through meta-level types such as `Class` and `Property`, the schema supports reflection and can represent its own definitions.[4] The canonical machine-readable representation of Schema.org is published in RDF/Turtle, with additional machine-readable formats such as RDF and [JSON-LD](https://mimirwiki.com/wiki/json-ld) available on the developer documentation page.[3][4]

As of Version 30.1, released on 2026-09-16 (accessed 2026-11-23), Schema.org defines the following vocabulary components.[2][3]

| Component | Count (Version 30.1, as of 2026-11-23) |
| --- | --- |
| Types | 826 |
| Properties | 1,540 |
| Datatypes | 19 |
| Enumerations | 96 |
| Enumeration members | 544 |

Commonly used Schema.org type groups include creative works (`CreativeWork`, `Book`, `Movie`, `MusicRecording`, `Recipe`, `TVSeries`), embedded media objects (`AudioObject`, `ImageObject`, `VideoObject`), `Event`, health and medical entities (`MedicalEntity`), `Organization`, `Person`, `Place` (`LocalBusiness`, `Restaurant`), `Product` and `Offer` (`AggregateOffer`), `Review` and `AggregateRating`, and `Action`, alongside primitive datatypes for values such as text and numbers.[3] General linking properties include `mainEntity` and `mainEntityOfPage`, which identify the primary entity described by a page, alongside `url`, `sameAs`, and `about`.[4]

Schema.org follows a pragmatic conformance model grounded in Postel's Law, treating type and property associations as guidelines.[4] A single entity description may combine properties from multiple independent types, such as `Book` and `Product`, and publishers often supply plain text strings or URLs where structured entity types are expected; types such as `Role` and `URL` can be used with any property.[4][5] Any property may carry multiple values, which represent an unordered set by default under RDF triples.[4] When ordering or collection semantics are needed, publishers can use RDF Lists (`rdf:List`, expressed with `@list` in JSON-LD) or RDF Containers (`rdf:Seq`, `rdf:Bag`, `rdf:Alt`), with the property's expected range applying to individual collection elements for parsers that support them.[4]

Schema.org groups specialized areas into hosted sections (`auto`, `bib`, `health-lifesci`, `meta`, and `pending`) that serve as views into a single collection of definitions.[3] Terms under active discussion live in `pending` and may change before reaching consensus, `meta` holds internal vocabulary for technical definitions and site functionality, and `attic` archives deprecated or unaccepted terms that publishers are cautioned against using.[3] Unlike core terms, `pending`, `meta`, and `attic` can be updated without a full release.[3] Independent external extensions, such as the GS1 Web Vocabulary and Croissant (a community metadata vocabulary for machine learning datasets), extend Schema.org without official approval from the Steering Group.[3]

## Schema.org encodings and term identifiers

Schema.org terms can be embedded in web pages using three primary serialization formats: [JSON-LD](https://mimirwiki.com/wiki/json-ld), Microdata, and RDFa.[4][5][6] Schema.org initially emphasized Microdata as a pragmatic choice when the project launched, then expanded documentation and examples across RDFa and JSON-LD, noting that tasks such as mixing vocabularies or inverting property relationships are harder in Microdata.[6]

| Format | Encoding mechanism | Specification and notes |
| --- | --- | --- |
| JSON-LD | JSON object embedded in HTML `script` elements with `type="application/ld+json"`, using `@context` and `@type` | W3C Recommendation (`JSON-LD 1.1` published 2020-07-16, superseding `JSON-LD 1.0` from 2014-01-16); 100% compatible with JSON (RFC 8259) and interoperable with RDF graphs |
| Microdata | Inline HTML5 attributes `itemscope`, `itemtype`, and `itemprop` on content elements, nesting new `itemscope` blocks for embedded items | Introduced with HTML5; item types are given as Schema.org URLs such as `https://schema.org/Movie` |
| RDFa (RDFa Lite) | Inline HTML attributes `vocab="https://schema.org/"`, `typeof`, and `property` on content elements | Maps almost isomorphically to Microdata (`itemprop` becomes `property`, `itemtype` becomes `typeof`, and `itemscope` is omitted) |

The table above summarizes encoding details documented across Schema.org, Google Search Central, and W3C specifications.[4][5][9][10] In HTML markup, Schema.org also documents machine-readable disambiguation patterns: HTML `time` elements with `datetime` attributes formatted as `YYYY-MM-DD` (optionally followed by `T` and `hh:mm` or `hh:mm:ss`) for dates and times, HTML `link` elements with `href` for enumerations and canonical references, and HTML `meta` elements with `content` for implicit values.[5]

Schema.org launched on an `http:` website with RDF term identifiers using `http://schema.org/` URLs before later migrating its public website and preferred documentation examples to `https://schema.org/`.[7] Schema.org documentation states that both `https://schema.org` and `http://schema.org` remain valid and widely understood in structured data markup.[7] After transitioning to static file hosting, Schema.org replaced HTTP content negotiation for its remote JSON-LD context with an HTTP `Link` header pointing to `/docs/jsonldcontext.jsonld` with `rel="alternate"` and `type="application/ld+json"`.[7] Because that context document retains `http:` as its base URL so existing RDF parsers worldwide do not silently change emitted triples, Dan Brickley noted on 2026-10-30 that JSON-LD parsers continue to emit `http://` triples even when markup references `https://schema.org`, and advised data consumers to canonicalize identifiers when aggregating Schema.org data.[7]

## Schema.org governance, repository, and licensing

Schema.org is governed through a two-tier structure consisting of a Steering Group and the W3C Schema.org Community Group.[1] The Steering Group provides high-level oversight, manages operational decisions, and approves formal releases.[1] Co-founder R.V. Guha, who initiated Schema.org at Google, chairs the Steering Group in an individual capacity (as of 2026-11-23), alongside representatives from founding companies Google, Microsoft, Yahoo, and Yandex, a W3C representative, and substantial community contributors.[1] In April 2015, the Steering Group unanimously expanded its membership to add Stéphane Corlosquet, Martin Hepp (author of GoodRelations), and a seat for the W3C.[1] Steering Group discussions are public, with meeting notes posted on GitHub and linked from issue #1.[1]

The W3C Schema.org Community Group was proposed by Dan Brickley and launched on 2015-03-31, becoming the main public forum for day-to-day schema discussion, proposal preparation, and extension review in April 2015.[1][7] Participation is open to anyone with a W3C account who signs the W3C Community Contributor License Agreement, and W3C notes that its hosting of the group does not imply endorsement by W3C Membership or staff.[1][7] As of 2026-11-23, the Community Group has 510 participants and six listed chairs: Dan Brickley, Dan Scott, Stéphane Corlosquet, Phil Barker, Phil Archer, and Ryan Levering.[7] Dan Brickley also runs daily operations and serves as project webmaster, chairing the Community Group on behalf of Schema.org independently of his role as Google's representative on the Steering Group.[1] Discussions take place on the `public-schemaorg@w3.org` mailing list and on GitHub, with related W3C Community Groups coordinating domain work in areas including health and medicine, sports, archives, bibliography, and automotive.[1][7]

Schema.org maintains its schemas (`data`), documentation (`docs`), templates, `versions.json`, and site software (`software`, partly imported from the `sdopythonapp` submodule) in the public GitHub repository `github.com/schemaorg/schemaorg`.[8] As of 2026-11-23, the repository records 5,741 commits, 6.3k stars, 975 forks, 388 watchers, 301 open issues, and 14 open pull requests.[8] Issue #1 acts as the release planning index, issues #2 and #3 organize vocabulary and tooling work, continuous integration tests check pull requests, and draft releases are staged at `staging.schema.org`.[1][2][8] The project's contribution guidelines prioritize incremental fixes and additions backed by real consuming applications, including web analytics, browser add-ons, and cloud tools alongside search engines, emphasizing local usability and alignment with external standards such as GoodRelations, GS1, IPTC rNews, MARC, BibFrame, FRBR, BBC, the European Broadcasting Union, Music Ontology, and MusicBrainz.[8]

Schema.org publishes its schema definitions, site documentation, blog content, and markup examples under the Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0) license.[6] The supporting software used to run the Schema.org site is released under the Apache-2.0 open-source license.[6][8]

## Schema.org release history

Schema.org publishes versioned formal releases after review by the Steering Group and the wider community, with a summary of the current release hosted at `https://schema.org/version/latest`.[2][8] As of 2026-11-23, the latest published release is Version 30.1, issued on 2026-09-16.[2]

Version 30.1 (2026-09-16) introduced vocabulary supporting discovery of EU Digital Product Passports, adding the `DigitalProductPassport` class, `hasDigitalProductPassport`, `EnvironmentalProductDeclaration` and `DeclarationOfConformity` (as subtypes of `Certification`), and product properties `authorizedRepresentative`, `importer`, `recycledContentPercentage`, and `substanceOfConcern`.[2] The same release added retail feed properties including `consumerNotice`, `isOftenBoughtWith`, `specification`, `valueGroup`, `itemPopularity`, `minimumOrderValue`, and the `MaximumRetailPrice` enumeration value, documented explicit support for ordered lists, updated term usage statistics, added `Ophthalmology` and `Audiology` to `MedicalSpecialty`, and promoted adopted `pending` terms to general availability.[2]

Major recent releases prior to Version 30.1 include the following milestones.[2]

| Version | Release date | Notable additions and changes |
| --- | --- | --- |
| 30.1 | 2026-09-16 | EU Digital Product Passport types and properties, retail feed vocabulary, ordered-list documentation, pending-to-GA promotions |
| 30.0 | 2026-03-19 | GS1, Dublin Core, and Open Graph equivalence annotations and exports; EU Digital Product Passport examples aligned with UN/CEFACT; `Credential` and `Error` classes; `Quantity` moved to inherit from `DataType` |
| 29.4 | 2025-12-08 | `ConferenceEvent`, `PerformingArtsEvent`, `InstantaneousEvent`, authentication actions (`AuthenticateAction`, `LoginAction`, `ResetPasswordAction`), `OperatingSystem`, `RuntimePlatform`, `SequentialArt` (deprecating `GraphicNovel`), OWL equivalences for UN/CEFACT, OWL, OMG, and GS1 |
| 29.3 | 2025-09-04 | Expanded range of `recipeIngredient`; added `OnlineMarketplace` and `hasStore` / `isStoreOn` |
| 29.0 | 2025-03-24 | `FinancialIncentive` vocabulary, European Legislation Identifier (ELI) properties on `Legislation`, revised shipping types (`ShippingConditions`, `ShippingService`, deprecating `DeliveryTimeSettings`) |
| 28.0 | 2024-09-17 | Loyalty and membership program types (`MemberProgram`, `MemberProgramTier`, `TierBenefitEnumeration`) |
| 27.02 | 2024-07-01 | Migrated editorial staging site from `webschemas.org` to `staging.schema.org` |
| 27.01 | 2024-06-24 | Schema.org site redesign |
| 27.0 | 2024-05-20 | Added `hasGS1DigitalLink` and `certificationRating` |

Patch releases Version 29.1 (2025-04-25) and Version 29.2 (2025-05-13) corrected regressions introduced in Version 29.0 and added properties and types such as `pronouns`, `companyRegistration`, `Cooperative`, and `referee`.[2] Terms in `pending`, `meta`, and `attic` may also be updated between full releases.[3]

## Schema.org search engine usage and limits

Schema.org markup is used by search engines including Google, Microsoft, Yahoo, and Yandex to interpret page entities and power rich search results.[5][6][9] Google Search Central documents structured data features covering content types such as Article, Breadcrumb, Course list, Dataset, Discussion forum, Event, Fact check, Image metadata, Job posting, Local business, Organization, Product snippet, Merchant listing, Profile page, Q&A, Recipe, Review snippet, Software app, Speakable, Subscription and paywalled content, Vacation rental, and Video.[9] For recipe pages, for example, structured data labels ingredients, calories, and cooking times so Google Search can display rich results and support attribute-level filtering.[9] Content management systems such as Wix, WordPress, and Shopify provide built-in settings or plugins for adding structured data without editing HTML directly.[9]

Publishers can verify syntax and structure with two primary validation tools documented in the sources: the Schema.org Markup Validator, which checks Schema.org structures and marks RDF collections (`List`, `Bag`, `Seq`, `Alt`), and Google's Rich Results Test, which validates structured data and previews eligible Google Search features.[4][9]

Schema.org and search engine documentation identify several practical boundaries and limits on structured data usage:

- **Selective feature display**: The Schema.org FAQ states that search engines do not surface every type of information defined in Schema.org, and publishers need to consult each search engine's documentation for specific supported features.[6]
- **Visible-content requirement**: Both Schema.org guidelines and Google Search Central instruct publishers to mark up only content visible to users on the page, avoiding blank pages created solely to hold structured data and avoiding hidden markup even when the underlying data is accurate.[5][6][9]
- **Optional and partial markup**: Marking up every property of an item is optional; when no exact subtype exists, publishers can leave content unmarked, use a broader parent type such as `Person`, or define an extension.[6]
- **Bounded ontological scope**: Schema.org simplifies web content for practical publishing and leaves comprehensive domain ontologies to independent vocabularies and external extensions.[4][8]
- **Parser and identifier heterogeneity**: Schema.org does not require all parsers to implement RDF collections or containers, and the Web corpus mixes `http://` and `https://` identifiers across Microdata, RDFa, and JSON-LD, requiring data consumers to handle canonicalization and shortcut string values.[4][7]

## Frequently asked questions

### What is Schema.org?

Schema.org is a collaborative vocabulary of types and properties used to add machine-readable structured data to web pages. Google, Microsoft, Yahoo, and Yandex founded the initiative in 2011 so websites could use one shared markup vocabulary across major search engines and other applications. [1][4]

### Is Schema.org a formal standards body like the W3C?

No. Schema.org describes itself as a collaborative effort documenting schemas supported by major search engines, separate from formal standards bodies such as the W3C or IETF. The W3C hosts the Schema.org Community Group as a public discussion forum, and W3C hosting does not imply endorsement by W3C Membership or staff. [6][7]

### Which markup formats can be used with Schema.org?

Publishers can encode Schema.org terms in web pages using JSON-LD, Microdata, or RDFa (including RDFa Lite). The canonical machine-readable representation of the Schema.org vocabulary itself is published in RDF/Turtle. [4][5][6]

### How large is the Schema.org vocabulary?

As of Version 30.1, released on 2026-09-16 (accessed 2026-11-23), the Schema.org vocabulary contains 826 types, 1,540 properties, 19 datatypes, 96 enumerations, and 544 enumeration members. It also includes hosted sections such as pending for terms under review and an attic archive for deprecated terms. [2][3]

### Under what licenses are Schema.org vocabularies and software released?

Schema.org schemas, site documentation, blog content, and markup examples are released under the Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0) license. The supporting software used to publish the site is released under the Apache-2.0 open-source license. [6][8]

### Is every Schema.org type shown in search engine results?

No. According to the Schema.org FAQ, search engines do not surface every type of information defined in the vocabulary, and each search engine documents which features and types it supports. Google Search Central also states that structured data on a page must describe content visible to visitors on that page. [6][9]

## Quotable sentences

- Schema.org was founded in 2011 by Google, Microsoft, Yahoo, and Yandex to provide a shared structured data vocabulary for web pages. [1][4]
- The W3C Schema.org Community Group was proposed and launched on 2015-03-31 as a public forum for discussing changes and extensions to Schema.org. [7]
- As of 2026-11-23, the latest published release of Schema.org is Version 30.1, released on 2026-09-16. [2]
- As of 2026-11-23, the Schema.org vocabulary consists of 826 types, 1,540 properties, 19 datatypes, 96 enumerations, and 544 enumeration members. [3]
- Schema.org markup can be encoded in web pages using JSON-LD, Microdata, or RDFa, while the canonical machine representation of the schema is in RDF/Turtle. [4][5]
- Schema.org schemas, site documentation, blog content, and markup examples are licensed under Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0), while the supporting site software uses the Apache-2.0 license. [6][8]
- JSON-LD 1.1 was published as a W3C Recommendation on 2020-07-16, superseding the JSON-LD 1.0 Recommendation from 2014-01-16. [10]
- Google Search Central documentation states that structured data on a page must describe content visible to users on that page. [9]

## Timeline

- 2011: Google, Microsoft, Yahoo, and Yandex launch Schema.org to provide a shared structured data vocabulary for web pages. [4][8]
- 2014-01-16: The W3C publishes JSON-LD 1.0 as a W3C Recommendation. [10]
- 2015-03-31: Dan Brickley proposes and launches the W3C Schema.org Community Group. [7]
- 2015-04: The Schema.org Steering Group expands to include community contributors Stéphane Corlosquet and Martin Hepp plus a W3C representative, and the W3C Community Group becomes the main collaboration forum. [1]
- 2020-07-16: The W3C publishes JSON-LD 1.1 as a W3C Recommendation, superseding JSON-LD 1.0. [10]
- 2024-07-01: Schema.org releases Version 27.02, migrating its editorial staging site from webschemas.org to staging.schema.org. [2]
- 2025-03-24: Schema.org releases Version 29.0 with new vocabulary for financial incentives, European Legislation Identifier (ELI) properties, and revised shipping schemas. [2]
- 2026-03-19: Schema.org releases Version 30.0, adding equivalence annotations for GS1, Dublin Core, and Open Graph along with EU Digital Product Passport examples. [2]
- 2026-09-16: Schema.org releases Version 30.1, adding EU Digital Product Passport types, retail feed properties, and explicit documentation for ordered lists. [2]

## Sources

1. About - Schema.org. Schema.org. https://schema.org/docs/about.html (checked 2026-11-23; tier 3: official site)
2. Release listing - schema.org. Schema.org. published 2026-09-16. https://schema.org/docs/releases.html (checked 2026-11-23; tier 3: official site)
3. Schemas - Schema.org. Schema.org. https://schema.org/docs/schemas.html (checked 2026-11-23; tier 3: official site)
4. Data model - Schema.org. Schema.org. https://schema.org/docs/datamodel.html (checked 2026-11-23; tier 3: official site)
5. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (checked 2026-11-23; tier 3: official site)
6. FAQ - schema.org. Schema.org. https://schema.org/docs/faq.html (checked 2026-11-23; tier 3: official site)
7. Schema.org Community Group. World Wide Web Consortium (W3C). https://www.w3.org/community/schemaorg/ (checked 2026-11-23; tier 1: government or public registry)
8. GitHub - schemaorg/schemaorg: Schema.org - schemas and supporting software · GitHub. Schema.org (GitHub). https://github.com/schemaorg/schemaorg (checked 2026-11-23; tier 3: official site)
9. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (checked 2026-11-23; tier 3: official site)
10. JSON-LD 1.1. World Wide Web Consortium (W3C). published 2020-07-16. https://www.w3.org/TR/json-ld11/ (checked 2026-11-23; tier 1: government or public registry)

## Cite this page

Mimirwiki. "Schema.org." Version 991456cc, 2026-11-24. https://mimirwiki.com/wiki/schema-org
