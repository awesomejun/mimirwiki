---
title: "JSON-LD"
subtitle: "W3C standard format for serializing Linked Data in JSON"
canonical_url: https://mimirwiki.com/wiki/json-ld
language: en
page_class: anchor
revision_sha256: c41cd7f93abb82ece3a1832d6b68fe678bea1d0d52c3e05f0f68fc13b6e2669e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/json-ld.md
  txt: https://mimirwiki.com/wiki/json-ld.txt
  json: https://mimirwiki.com/wiki/json-ld.json
  jsonld: https://mimirwiki.com/wiki/json-ld.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/json-ld
  ja: https://mimirwiki.com/ja/wiki/json-ld
  zh: https://mimirwiki.com/zh/wiki/json-ld
  es: https://mimirwiki.com/es/wiki/json-ld
---

# JSON-LD

> JSON-LD is a W3C Recommendation for serializing Linked Data in valid JSON. It maps object keys to global identifiers through a context so applications can interpret and connect data across websites. Standardized in 2014 and updated to version 1.1 in 2020, JSON-LD supports RDF graphs, programmatic transformations, and HTML structured data such as Schema.org.

JSON-LD (JSON for Linking Data) is a World Wide Web Consortium (W3C) Recommendation that defines a lightweight JSON-based syntax for serializing Linked Data on the Web. Every JSON-LD document is valid JSON under RFC 8259, allowing standard JSON parsers, Web services, and JSON-based storage engines to process it while adding global resource identifiers, contexts, language tags, datatypes, and directed graphs. The W3C published JSON-LD 1.0 on 2014-01-16 and superseded it with the JSON-LD 1.1 specification suite on 2020-07-16, covering syntax, processing algorithms and API, and framing. Applications use JSON-LD directly as JSON, convert it to and from Resource Description Framework (RDF) graphs and datasets, or embed it in HTML documents for structured data vocabularies such as Schema.org.

**Also known as:** JSON for Linked Data, JSON for Linking Data, JSON-LD 1.0, JSON-LD 1.1

## Key facts

- **Standards body:** World Wide Web Consortium (W3C) [1]
- **First W3C Recommendation:** JSON-LD 1.0 (2014-01-16) [4]
- **Current W3C Recommendation:** JSON-LD 1.1 (2020-07-16) (as of 2026-11-23) [1]
- **Base syntax:** JSON (RFC 8259) [1]
- **HTML script type:** application/ld+json [8]

## Basic facts

- **Type:** JSON-based serialization format for Linked Data [1]
- **Standards organization:** World Wide Web Consortium (W3C) [1]
- **Responsible group:** W3C JSON-LD Working Group (charter through January 2028) (as of 2026-11-23) [7]
- **First Recommendation:** JSON-LD 1.0 (2014-01-16; superseded 2020-11-03) [4]
- **Current Recommendation:** JSON-LD 1.1 (2020-07-16) (as of 2026-11-23) [1]
- **Companion 1.1 Recommendations:** Processing Algorithms and API; Framing [1]
- **Version 1.1 editors:** Gregg Kellogg, Pierre-Antoine Champin, Dave Longley [1]
- **Version 1.0 editors:** Manu Sporny, Gregg Kellogg, Markus Lanthaler [4]
- **Base format:** JSON (IETF RFC 8259) [5]
- **Data model compatibility:** RDF 1.1 graphs and RDF datasets [6]
- **Specification repository:** github.com/w3c/json-ld-syntax [10]

## What JSON-LD is

JSON-LD (JSON for Linking Data) is a lightweight syntax standardized by the World Wide Web Consortium (W3C) for serializing Linked Data in JSON.[1][7] Linked Data connects machine-readable data across documents and websites so that an application can follow embedded links from one dataset to related resources hosted on other sites.[1][7] JSON-LD is designed for Web-based programming environments, interoperable REST Web services, and JSON-based storage engines such as Apache CouchDB and MongoDB.[1][7]

Every JSON-LD document is valid JSON as defined by IETF RFC 8259 (which obsoleted RFC 7159 and earlier RFC 4627), so existing JSON parsers and libraries can parse JSON-LD documents directly.[1][4][5] JSON-LD 1.0 originally referenced RFC 4627, while JSON-LD 1.1 updated the base JSON reference to RFC 8259.[1][4] Beyond standard JSON's primitive types (strings, numbers, booleans, and `null`) and structured types (objects and arrays), JSON-LD adds universal object identifiers via IRIs, term-to-IRI mapping through contexts, cross-site resource references, language annotations for strings, value datatypes such as dates and times, and directed graph representations.[1][5]

The JSON-LD 1.0 specification listed six design goals: simplicity, compatibility, expressiveness, terseness, minimal edits for existing JSON systems, and usability as RDF.[4] In basic use, JSON-LD requires familiarity with JSON and two keywords, `@context` and `@id`, without requiring dedicated JSON-LD processors.[4] In deployed JSON APIs, servers can also associate existing JSON documents with a JSON-LD context through an HTTP response link relationship so existing JSON payloads can be interpreted as JSON-LD with minimal changes.[1][4]

## JSON-LD syntax, contexts, and keywords

JSON-LD builds on JSON objects and arrays while introducing specific structural rules and reserved keywords prefixed with `@`.[1] In JSON-LD, member names within a JSON object must be unique, whereas RFC 8259 specifies only that JSON object names should be unique.[1][5] In ordinary JSON, arrays are ordered sequences of values; in JSON-LD, array collections are unordered by default unless explicitly defined as lists.[1][5]

Core JSON-LD syntax centers on contexts and keywords that give JSON data unambiguous Web-scale meaning.[1][4]

- `@context`: Maps short property terms in a JSON document to full IRIs so keys shared across different JSON documents carry distinct, unambiguous definitions. A context can be referenced by URL (such as `https://schema.org/` or `https://json-ld.org/contexts/person.jsonld`), and assigning `null` to a term or its `@id` inside a context explicitly decouples that term from an IRI.[1][7][8]
- `@id`: Assigns a universal identifier, expressed as an IRI, to a node object so other objects or external documents can reference the same resource.[1][4][7]
- `@type`: Specifies the type of a node object (such as `Recipe` or `Person` in Schema.org markup) or associates a datatype with a typed value, and can also be combined with `@set`.[1][8]
- `null`: Resets or ignores values in a document body and decouples term mappings inside `@context`.[1]

JSON-LD 1.1 is a superset of JSON-LD 1.0 that maintains compatibility with 1.0 documents except where noted.[1] Its specification documents a JSON-LD 1.1 processing mode, default vocabularies, base IRIs, compact IRIs, keyword aliasing, scoped contexts, context propagation, imported contexts, protected term definitions, JSON literals, type coercion, string internationalization with base direction, nested properties, reverse properties, included nodes, multiple forms of indexed values (data, property-based, language, node identifier, and node type indexing), and named graphs with graph containers.[1]

## JSON-LD document forms, processing API, and framing

JSON-LD represents directed graphs, which means the same underlying information can be serialized in multiple shapes.[1][3] To support deterministic programmatic processing, the JSON-LD 1.1 specification suite defines four document forms: Expanded, Compacted, Flattened, and Framed.[1]

The companion W3C Recommendation, JSON-LD 1.1 Processing Algorithms and API, defines algorithms for transforming documents between forms and converting data to and from RDF, alongside a `JsonLdProcessor` Application Programming Interface (API) and `JsonLdOptions` configuration type described using Web IDL.[2] Its core processing capabilities include context processing (term definition creation, inverse context creation, and term selection), expansion (expanding IRIs and values), compaction (compacting IRIs and values), flattening (generating and merging node maps and assigning blank node identifiers), remote document and context retrieval, HTML content algorithms, and RDF serialization and deserialization with data round-tripping.[2]

A third W3C Recommendation, JSON-LD 1.1 Framing, extends `JsonLdProcessor` and `JsonLdOptions` to allow developers to query by example and enforce a specific tree layout on a JSON-LD graph.[3] Linked Data graphs consist of independent statements (triples), while applications often expect nested JSON object trees; a frame specifies how statements about each subject are bundled inside `{` and `}` delimiters and how related subjects nest.[3] The Framing specification supports matching on properties, wildcards, absent properties, values, and `@id`, as well as empty frames, default content, reverse framing, framing named graphs, and five framing flags: object embed, explicit inclusion, omit default, omit graph, and require all.[3]

## JSON-LD and the RDF data model

JSON-LD is designed both for developers working directly with JSON without knowledge of the Resource Description Framework (RDF) and for systems operating on RDF data.[1][4] The W3C Recommendation RDF 1.1 Concepts and Abstract Syntax, published on 2014-02-25, explicitly lists JSON-LD alongside Turtle as a serialization syntax for storing and exchanging RDF data, linking it with RDF Schema and the SPARQL query language.[6]

In the RDF 1.1 abstract syntax, information is organized into RDF graphs, which are sets of subject-predicate-object triples whose nodes may be IRIs, literals (datatyped values or language-tagged strings), or blank nodes, and RDF datasets, which group a default graph together with zero or more named graphs.[6] IRIs have global scope in RDF, meaning separate occurrences of the same IRI denote the same resource and can serve as dereferenceable starting points on the Web.[6]

JSON-LD 1.1 and its Processing Algorithms and API specification define deterministic algorithms for deserializing JSON-LD documents into RDF datasets and serializing RDF datasets back into JSON-LD, functioning alongside formats such as Turtle and TriG.[1][2] To support JSON-LD 1.1 features within RDF, the syntax specification defines the `rdf:JSON` datatype, the `i18n` namespace, and the `rdf:CompoundLiteral` class together with `rdf:language` and `rdf:direction` properties.[1] The JSON-LD 1.1 specification also documents how JSON-LD relates to other Linked Data and structured markup formats, including Turtle, RDFa, and Microdata, and JSON-LD 1.0 additionally compared it with Microformats.[1][4]

## JSON-LD in HTML, Schema.org, and search engines

JSON-LD documents can be embedded directly inside HTML pages, a feature defined in both JSON-LD 1.0 and JSON-LD 1.1.[1][4] The JSON-LD 1.1 specification addresses embedding JSON-LD in HTML `script` elements, inheriting the base IRI from an HTML document's `base` element, content restrictions for JSON-LD `script` elements, and locating a specific JSON-LD `script` element.[1] The specifications also include IANA Considerations appendices, and Google Search Central's structured data guide demonstrates HTML embedding using a `script` element with `type="application/ld+json"` placed in the document `head`.[1][4][8]

On the public Web, JSON-LD is paired with [Schema.org](https://mimirwiki.com/wiki/schema-org), a shared vocabulary for marking up web page entities so that major search engines (Google, Microsoft, Yandex, and Yahoo!) can interpret page meaning.[9] Schema.org supports three markup formats, namely Microdata, RDFa, and JSON-LD, and publishes most of its site examples across all three formats.[9] Its type hierarchy starts at `Thing` (with properties `name`, `description`, `url`, and `image`) and branches into subtypes such as `CreativeWork` (including `Book`, `Movie`, `MusicRecording`, `Recipe`, and `TVSeries`), `Event`, `Organization`, `Person`, `Place`, `LocalBusiness`, `Product`, and `Review`.[9]

Google Search Central documents how Google Search reads in-page JSON-LD structured data, such as a Schema.org `Recipe` object referencing a nested `Person` author, to classify page content, gather entity information about people, books, or companies, and display rich results.[8] Both Schema.org and Google Search Central specify that structured data should describe content visible to users on that page, advising against empty pages created solely to hold markup or markup for hidden content.[8][9] Site owners using content management systems such as Wix, WordPress, or Shopify can configure structured data through platform settings or plugins, and developers can validate markup and preview eligible search features using Google's Rich Results Test.[8]

## JSON-LD versions, governance, and implementations

JSON-LD originated in the JSON for Linking Data Community Group before transferring to the W3C RDF Working Group, which published JSON-LD 1.0 and JSON-LD 1.0 Processing Algorithms and API as W3C Recommendations on 2014-01-16 (edited by Manu Sporny, Gregg Kellogg, and Markus Lanthaler, with Dave Longley and Niklas Lindström as co-authors).[2][4] Work on JSON-LD 1.1 then moved to the W3C JSON-LD Working Group, building on the JSON-LD Community Group's Final Report.[1] Following Candidate Releases on 2019-12-12 and Proposed Recommendations on 2020-05-07, the Working Group published three W3C Recommendations on 2020-07-16, edited by Gregg Kellogg, Pierre-Antoine Champin, and Dave Longley.[1][2][3] W3C formally marked JSON-LD 1.0 as a Superseded Recommendation on 2020-11-03, directing new implementations to JSON-LD 1.1 while retaining W3C Patent Policy licensing commitments for the 1.0 specification.[4]

| Specification | Publication date | Scope | Repository |
| --- | --- | --- | --- |
| JSON-LD 1.1 | 2020-07-16 | Linked Data syntax, contexts, keywords, HTML embedding, RDF mapping | `w3c/json-ld-syntax` |
| JSON-LD 1.1 Processing Algorithms and API | 2020-07-16 | Expansion, compaction, flattening, RDF conversion, `JsonLdProcessor` API | `w3c/json-ld-api` |
| JSON-LD 1.1 Framing | 2020-07-16 | Query-by-example graph matching and deterministic tree layout | `w3c/json-ld-framing` |

All three specifications form the official JSON-LD 1.1 Recommendation suite produced by the W3C JSON-LD Working Group.[1][2][3][10]

As of 2026-11-23, the W3C JSON-LD Working Group maintains formal specification governance under a charter running through January 2028, while the open JSON-LD Community Group coordinates community drafts, discussion calls, and mailing lists.[7] In the public `w3c/json-ld-syntax` repository on GitHub, the Working Group notes that JSON-LD 1.1 drafts are feature frozen, limiting repository issues to bug reports, clarifications of existing features, and editorial corrections.[10]

As of 2026-11-23, json-ld.org hosts the web-based JSON-LD Playground for debugging and visualizing markup, tracks conformance through official test suites and an implementation report, and lists conforming JSON-LD 1.1 libraries across JavaScript (`json-ld.js`, `jsonld-streaming-parser.js`, `jsonld-streaming-serializer.js`, `rdf-parse.js`), Python (`PyLD`, `RDFLib`, `TRLD`), Ruby (`JSON-LD for RDF.rb`), Go (`JSON-goLD`), Java (`Titanium`), C# (`dotNetRDF`), Erlang and Elixir (`JSON-LD.ex`), Rust (`sophia`, `oxjsonld`), and command-line tools (`jsonld-cli`, `ld-cli`), alongside JSON-LD 1.0 implementations in PHP (`php-json-ld`, `JsonLD`), Java (`JSONLD-JAVA`), and C# (`json-ld.net`).[7] Community drafts extend the JSON-LD data model to related specifications, including YAML-LD for human-writable YAML authoring, CBOR-LD for compressed binary serialization in space-constrained uses such as QR codes, PDF417 barcodes, and NFC tags, as well as Streaming and JSON-LD-star drafts.[7]

## Frequently asked questions

### What is JSON-LD?

JSON-LD (JSON for Linking Data) is a W3C Recommendation that defines a lightweight JSON-based syntax for serializing Linked Data on the Web. Every JSON-LD document is valid JSON under RFC 8259 while adding contexts, global IRI identifiers, datatypes, language annotations, and directed graph structures. [1][5][7]

### What do @context, @id, and @type do in JSON-LD?

In JSON-LD, @context maps short JSON property names to full IRIs so keys carry unambiguous meanings across documents. The @id keyword assigns a global IRI identifier to a node object, and @type specifies the type of a node object or the datatype of a value. [1][4][8]

### How did JSON-LD 1.1 update JSON-LD 1.0?

Published as three W3C Recommendations on 2020-07-16, JSON-LD 1.1 superseded the 2014 JSON-LD 1.0 specification while preserving compatibility with 1.0 documents except where noted. It updated the base JSON reference to RFC 8259, standardized JSON-LD Framing as a W3C Recommendation, and added features such as scoped contexts, JSON literals, base direction for strings, and additional indexing modes. [1][2][3][4]

### Does JSON-LD require knowledge of RDF?

No. The W3C specifications state that JSON-LD can be used directly as ordinary JSON without knowledge of RDF, while also serving as a standard RDF serialization syntax that converts to and from RDF 1.1 graphs and datasets for tools such as SPARQL. [1][4][6]

### What are the JSON-LD Processing API and Framing specifications?

JSON-LD 1.1 Processing Algorithms and API defines the JsonLdProcessor interface and algorithms for expansion, compaction, flattening, and RDF conversion. JSON-LD 1.1 Framing extends that API so developers can query by example and enforce a deterministic nested tree layout on a directed graph. [2][3]

### How is JSON-LD embedded in HTML pages for search engines?

JSON-LD can be placed inside an HTML script element with the type attribute set to application/ld+json, often in the document head, using vocabularies such as Schema.org. Google Search reads in-page JSON-LD describing visible page content to understand entities and display rich results, and provides the Rich Results Test for validation. [1][8][9]

## Quotable sentences

- The W3C RDF Working Group published JSON-LD 1.0 as a W3C Recommendation on 2014-01-16. [4]
- The W3C JSON-LD Working Group published JSON-LD 1.1, JSON-LD 1.1 Processing Algorithms and API, and JSON-LD 1.1 Framing as W3C Recommendations on 2020-07-16. [1][2][3]
- W3C marked JSON-LD 1.0 as a Superseded Recommendation on 2020-11-03 in favor of JSON-LD 1.1. [4]
- Every JSON-LD 1.1 document is valid JSON under IETF RFC 8259, with unique object member names and arrays treated as unordered by default. [1][5]
- RDF 1.1 Concepts and Abstract Syntax names JSON-LD alongside Turtle as a serialization syntax for storing and exchanging RDF data. [6]
- JSON-LD 1.1 Framing allows developers to query by example and enforce a deterministic tree layout on a JSON-LD graph. [3]
- Schema.org supports JSON-LD alongside Microdata and RDFa as markup formats understood by Google, Microsoft, Yandex, and Yahoo!. [9]
- As of 2026-11-23, the W3C JSON-LD Working Group charter runs through January 2028, and the w3c/json-ld-syntax GitHub repository marks JSON-LD 1.1 drafts as feature frozen. [7][10]

## Timeline

- 2014-01-16: W3C RDF Working Group publishes JSON-LD 1.0 and JSON-LD 1.0 Processing Algorithms and API as W3C Recommendations. [2][4]
- 2014-02-25: W3C RDF Working Group publishes RDF 1.1 Concepts and Abstract Syntax as a W3C Recommendation, citing JSON-LD as an RDF serialization syntax. [6]
- 2017-12: IETF publishes RFC 8259 defining the JSON data interchange format referenced by JSON-LD 1.1. [1][5]
- 2019-12-12: W3C JSON-LD Working Group publishes Candidate Releases for JSON-LD 1.1, Processing Algorithms and API, and Framing. [1][2][3]
- 2020-07-16: W3C JSON-LD Working Group publishes JSON-LD 1.1, JSON-LD 1.1 Processing Algorithms and API, and JSON-LD 1.1 Framing as W3C Recommendations. [1][2][3]
- 2020-11-03: W3C marks JSON-LD 1.0 as a Superseded Recommendation in favor of JSON-LD 1.1. [4]

## Sources

1. JSON-LD 1.1. World Wide Web Consortium (W3C). published 2020-07-16. https://www.w3.org/TR/json-ld11/ (checked 2026-11-23; tier 1: government or public registry)
2. JSON-LD 1.1 Processing Algorithms and API. World Wide Web Consortium (W3C). published 2020-07-16. https://www.w3.org/TR/json-ld11-api/ (checked 2026-11-23; tier 1: government or public registry)
3. JSON-LD 1.1 Framing. World Wide Web Consortium (W3C). published 2020-07-16. https://www.w3.org/TR/json-ld11-framing/ (checked 2026-11-23; tier 1: government or public registry)
4. JSON-LD 1.0. World Wide Web Consortium (W3C). published 2014-01-16. https://www.w3.org/TR/2014/REC-json-ld-20140116/ (checked 2026-11-23; tier 1: government or public registry)
5. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). published 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (checked 2026-11-23; tier 1: government or public registry)
6. RDF 1.1 Concepts and Abstract Syntax. World Wide Web Consortium (W3C). published 2014-02-25. https://www.w3.org/TR/rdf11-concepts/ (checked 2026-11-23; tier 1: government or public registry)
7. JSON-LD - JSON for Linked Data. JSON-LD Community Group. https://json-ld.org/ (checked 2026-11-23; tier 3: official site)
8. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (checked 2026-11-23; tier 3: official site)
9. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (checked 2026-11-23; tier 3: official site)
10. GitHub - w3c/json-ld-syntax: JSON-LD 1.1 Specification · GitHub. W3C (GitHub). https://github.com/w3c/json-ld-syntax (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "JSON-LD." Version c41cd7f9, 2026-11-23. https://mimirwiki.com/wiki/json-ld
