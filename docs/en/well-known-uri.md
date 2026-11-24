---
title: "Well-Known URIs"
subtitle: "IETF standard reserving the /.well-known/ path prefix for origin-wide metadata and service discovery"
canonical_url: https://mimirwiki.com/wiki/well-known-uri
language: en
page_class: anchor
revision_sha256: d6008a8353c02484757ec1529f3a051a090d1ca190d9d9bb03db6aa6484ba6b8
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/well-known-uri.md
  txt: https://mimirwiki.com/wiki/well-known-uri.txt
  json: https://mimirwiki.com/wiki/well-known-uri.json
  jsonld: https://mimirwiki.com/wiki/well-known-uri.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/well-known-uri
  ja: https://mimirwiki.com/ja/wiki/well-known-uri
  zh: https://mimirwiki.com/zh/wiki/well-known-uri
---

# Well-Known URIs

> Well-Known URIs are Uniform Resource Identifiers whose path begins with /.well-known/ for origin-wide metadata and service discovery. Specified in IETF RFC 8615 (May 2019), obsoleting RFC 5785, they apply to HTTP, HTTPS, WS, and WSS. IANA maintains the registry under a Specification Required policy for suffixes including security.txt, acme-challenge, and openid-configuration.

Well-Known URIs are Uniform Resource Identifiers whose path component begins with the reserved prefix /.well-known/ on URI schemes explicitly defined to support them, including HTTP, HTTPS, WS, and WSS. Published by the Internet Engineering Task Force (IETF) in May 2019 as RFC 8615, the specification obsoletes RFC 5785 (April 2010) and standardizes a predictable location for origin-wide metadata and protocol discovery while avoiding path collisions. The Internet Assigned Numbers Authority (IANA) maintains the Well-Known URIs registry under a Specification Required policy with Designated Expert review, listing permanent and provisional suffixes such as security.txt, acme-challenge, oauth-authorization-server, oauth-protected-resource, and openid-configuration. Well-known URIs apply only at the top of an origin's path hierarchy, and individual applications define their own metadata format, media types, and scope.

**Also known as:** /.well-known/, Well-Known Uniform Resource Identifiers, RFC 8615, RFC 5785, .well-known

## Key facts

- **Current specification:** RFC 8615 (May 2019, Standards Track) (as of 2026-11-23) [1]
- **Reserved path prefix:** /.well-known/ at the origin root [1]
- **Prior specification:** RFC 5785 (April 2010, obsoleted by RFC 8615) [2]
- **Registry:** IANA Well-Known URIs (created 2010-01-20, updated 2026-10-26) (as of 2026-11-23) [3]
- **Registration policy:** Specification Required with Designated Expert review (RFC 8126) [1]

## Basic facts

- **Type:** Internet standard for a reserved URI path prefix [1]
- **Path prefix:** /.well-known/ [1]
- **Current specification:** RFC 8615 (May 2019, Standards Track) (as of 2026-11-23) [1]
- **Author (RFC 8615):** Mark Nottingham [1]
- **Obsoletes:** RFC 5785 (April 2010, Mark Nottingham and E. Hammer-Lahav) [2]
- **Updates:** RFC 7230 and RFC 7595 [1]
- **Supported URI schemes:** http, https, ws, wss, and other schemes explicitly defined to support them [1]
- **Registry:** IANA Well-Known URIs (iana.org/assignments/well-known-uris) [3]
- **Registry status:** Created 2010-01-20; last updated 2026-10-26 (as of 2026-11-23) [3]
- **Registration policy:** Specification Required [3]
- **Designated Expert:** Mark Nottingham (as of 2026-11-23) [3]
- **Suffix syntax:** RFC 3986 segment-nz (no / character) [1]

## What Well-Known URIs are

Well-Known URIs are Uniform Resource Identifiers whose path component begins with `/.well-known/` on URI schemes explicitly defined to support well-known locations.[1] The Internet Engineering Task Force (IETF) published the current Standards Track specification, RFC 8615, in May 2019, authored by Mark Nottingham.[1] RFC 8615 obsoletes RFC 5785, which Mark Nottingham and E. Hammer-Lahav published in April 2010 to establish the `/.well-known/` path prefix and the Internet Assigned Numbers Authority (IANA) registry.[1][2] RFC 8615 also updates RFC 7230 to reserve the prefix in `http` and `https` URIs and updates RFC 7595 so the IANA URI Schemes registry records which schemes support well-known URIs.[1]

Web applications frequently need to discover site-wide metadata about an origin before making a request, as seen in the [Robots Exclusion Protocol](https://mimirwiki.com/wiki/robots-txt) and the Platform for Privacy Preferences (P3P).[1][2] Per-resource metadata mechanisms such as HTTP header fields or WebDAV PROPFIND can introduce client-perceived latency or deployment difficulties in those scenarios.[1][2] HTTP is also used as a substrate for non-Web protocols that need to locate resources on a host.[1] Designating arbitrary fixed paths at the site root risks collisions with other protocol locations and with resources created by the origin, while encroaching on an origin's control over its own URI space.[1]

Reserving the single `/.well-known/` prefix isolates protocol-defined discovery locations and requires specifications to register suffixes through IANA to prevent naming collisions.[1][2] In addition to `http` and `https`, RFC 8615 reserves `/.well-known/` for WebSocket (`ws`) and Secure WebSocket (`wss`) URIs, updated via RFC 8307, and permits other URI schemes to adopt well-known URIs when their scheme definitions explicitly allow it.[1] RFC 5785 noted that well-known URIs were created to expose site-wide policy information and metadata directly or by linking to other URIs when multiple round-trips or per-resource checks are impractical, leaving general information retrieval and large URI namespaces outside their intended scope.[2]

## Well-Known URI syntax and scoping rules

Well-Known URIs follow strict syntax and structural constraints defined in RFC 8615.[1] For an application registering the suffix `example` on `http://www.example.com/`, the corresponding well-known URI is `http://www.example.com/.well-known/example`.[1] Every registered suffix must conform to the `segment-nz` production in RFC 3986, which prohibits the `/` character within the registered name itself.[1] RFC 8615 advises applications to choose precise names and discourages registering generic terms, giving `example-metadata` or `example.com-metadata` as preferred examples over `metadata`.[1]

A registration must reference a specification that defines the format, associated media types, and applicable URI schemes for the resource obtained by dereferencing the URI.[1] When a registration omits explicit URI schemes, `http` and `https` are assumed.[1] Applications use the default port for the scheme unless the specification explicitly designates an alternative port.[1] Registrations may also define syntax for additional path components, query strings, fragment identifiers, or protocol-specific behavior such as HTTP method handling.[1]

RFC 8615 leaves the format and media type of the base `/.well-known/` path undefined, and clients should not expect a resource to exist at that location.[1] Well-known URIs are rooted strictly at the top of a URI's path hierarchy. For example, a path starting at the root such as `/.well-known/example` qualifies as a well-known URI, while a nested path such as `/foo/.well-known/example` does not.[1] RFC 8615 leaves both hostname determination and the scope of metadata retrieved from a well-known URI to each individual application specification.[1]

## IANA Well-Known URIs registry and registration policy

Well-Known URIs must be registered in the IANA Well-Known URIs registry before applications mint new suffixes under `/.well-known/`.[1] Established by RFC 5785 and created on 2010-01-20, the registry is maintained by IANA, which coordinates IETF protocol parameter namespaces under contract with ICANN to prevent conflicting assignments and support interoperability.[2][3][8] As of 2026-11-23, the registry page records its last update on 2026-10-26, lists Mark Nottingham as Designated Expert, and provides downloads in XML, HTML, TXT, and CSV formats.[3]

Under RFC 8615, registrations follow the Specification Required policy defined in RFC 8126 (BCP 26, June 2017, which obsoleted RFC 5226) and require approval on the advice of one or more Designated Experts.[1][3][8] Requests are submitted through the IANA registry interface or by email to the `wellknown-uri-review@ietf.org` mailing list.[1][3] When RFC 5785 originally established the review workflow, it set a 14-day review target for Designated Experts and allowed unresolved requests to be escalated to the Internet Engineering Steering Group (IESG) at `iesg@iesg.org` after 21 days.[2]

RFC 8615 requires each registration request to provide four mandatory fields plus optional related information:[1]

- **URI suffix**: the name relative to `/.well-known/`
- **Change controller**: `IETF` for Standards Track RFCs, or the responsible party for other specifications
- **Specification document(s)**: a reference, preferably with a retrievable URI, to the defining specification
- **Status**: either `permanent` or `provisional`
- **Related information** (optional): citations to additional documents

RFC 8615 added the status distinction to the four-field template originally defined in RFC 5785.[1][2] Values defined by Standards Track RFCs and other open standards (under RFC 2026 Section 7.1.1) receive `permanent` status, and experts may also grant `permanent` status to other values found to be in use after consulting the community responsible for the URI scheme (typically on the relevant working group mailing list or `art@ietf.org`).[1] Other entries receive `provisional` status, which experts may later promote to `permanent` based on adoption or remove in consultation with the community if unused.[1] Experts or other third parties may also register widely deployed unregistered suffixes if a reference specification exists.[1] As of 2026-10-26, the IANA registry table also marks retired entries as `deprecated` (such as `privacy-sandbox-attestations.json`, `related-website-set.json`, and `tpcd`) or `obsoleted` (such as `http-opportunistic` and `mud`).[3]

## Notable registered Well-Known URI suffixes

Well-Known URIs support security disclosure, automated certificate issuance, identity and authorization metadata, and protocol discovery across standards bodies including the IETF, the W3C, the OpenID Foundation, OASIS, and ETSI.[3] Five permanent suffixes in the IANA registry cover security disclosure, certificate automation, and identity or authorization discovery:[3]

| URI Suffix | Defining Specification | Status | Change Controller | Date Registered |
| --- | --- | --- | --- | --- |
| `openid-configuration` | OpenID Connect Discovery 1.0 | permanent | OpenID Foundation Artifact Binding Working Group | 2013-08-27 |
| `acme-challenge` | RFC 8555, Section 8.3 | permanent | IETF | 2016-08-18 |
| `oauth-authorization-server` | RFC 8414, Section 3 | permanent | IESG | 2018-03-27 |
| `security.txt` | RFC 9116 | permanent | IETF | 2021-07-13 |
| `oauth-protected-resource` | RFC 9728, Section 3 | permanent | IETF | 2024-10-22 |

`security.txt`, specified in RFC 9116 (Informational, April 2022) by E. Foudil and Y. Shafranovich, defines a machine-parsable plain-text file where organizations publish vulnerability disclosure practices and reporting channels for security researchers.[4] The format uses line-based key-value fields (including `Contact`, `Expires`, `Encryption`, `Canonical`, `Policy`, `Acknowledgments`, `Preferred-Languages`, and `Hiring`), supports `#` comments, and recommends OpenPGP cleartext signatures (RFC 4880) paired with the `Canonical` field to authenticate the file's location.[4]

`acme-challenge`, registered under RFC 8555 (Standards Track, March 2019), supports the HTTP challenge defined by the Automatic Certificate Management Environment (ACME) protocol.[3][5] ACME automates domain-control verification for Domain Validation (DV) X.509 certificates as well as certificate issuance and revocation between certification authorities and applicants, replacing ad hoc manual verification steps.[5]

Three related suffixes serve [OAuth](https://mimirwiki.com/wiki/oauth) 2.0 and OpenID Connect discovery. `openid-configuration`, defined by OpenID Connect Discovery 1.0 (finalized in February 2014, with errata set 2 published on 2023-12-15), exposes a JSON document containing an OpenID Provider's configuration and OAuth 2.0 endpoint locations, optionally following issuer discovery via WebFinger (RFC 7033).[3][9] `oauth-authorization-server`, specified in RFC 8414 (Standards Track, June 2018), generalizes that JSON metadata format for OAuth 2.0 authorization servers, advertising fields such as `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `scopes_supported`, and `response_types_supported` either over HTTPS or inside a signed JSON Web Token (JWT).[3][6] `oauth-protected-resource`, specified in RFC 9728 (Standards Track, April 2025), provides a parallel JSON metadata document for OAuth 2.0 protected resources (advertising `resource`, `authorization_servers`, `jwks_uri`, `scopes_supported`, and `bearer_methods_supported`) derived deterministically from each resource identifier, and lets resource servers announce metadata URLs through the `WWW-Authenticate` header.[3][7]

As of 2026-10-26, the IANA registry also includes permanent entries such as `webfinger` (RFC 7033), `caldav` and `carddav` (RFC 6764), `host-meta` and `host-meta.json` (RFC 6415), `assetlinks.json` (Google Inc.), `pki-validation` (CA/Browser Forum), `mta-sts.txt` (RFC 8461), `jmap` (RFC 8620), `sbom` (RFC 9472), `api-catalog` (RFC 9727), `agent-card.json` (Linux Foundation), and `webauthn` (W3C), alongside provisional entries including `gpc.json`, `change-password`, `did.json`, and `tdmrep.json`.[3]

## Well-Known URI security considerations

Well-Known URIs introduce security considerations for both protocol designers and server operators because resources under `/.well-known/` effectively represent an entire origin.[1] RFC 8615 highlights general threats including exposure of sensitive data, denial-of-service attacks, server and client authentication failures, DNS rebinding attacks, and scenarios where limited server access allows an attacker to alter how well-known URIs are served.[1] Server operators must restrict write access to well-known locations through both server configuration and local filesystem permissions, particularly on shared origins where multiple entities are co-located.[1] RFC 8615 also notes that operating systems hiding dot-prefixed directories can conceal unauthorized modifications inside a `.well-known` directory from administrators.[1]

For `http` and `https` URIs, well-known resources are accessible to web browsers and share the origin security boundary with cookies (RFC 6265), Web Storage, and scripts loaded from other paths on the same origin.[1] An attacker who exploits a Cross-Site Scripting (XSS) vulnerability elsewhere on the origin can issue arbitrary requests to well-known resources.[1] RFC 8615 lists mitigations and practices for browser-accessible well-known endpoints:[1]

- Encrypting sensitive information and avoiding compression on sensitive values such as authentication tokens or passwords to prevent browser-based compression probing
- Using flexible identifiers such as cookie names to prevent collisions with other applications on the same origin, and setting `HttpOnly` and `Path` cookie attributes
- Sending `X-Content-Type-Options: nosniff`, enforcing an application-specific `Content-Type` media type, and applying `Content-Security-Policy` and `Referrer-Policy` headers

Application specifications must explicitly define both discovery rules and metadata scope to prevent boundary confusion across origins.[1] RFC 8615 warns that applying metadata from `https://example.com/.well-known/example` to another host or port, such as `https://department.example.com`, `https://www.example.com`, or `https://www.example.com:8000`, assumes an administrative relationship that might not exist and can grant control to an attacker.[1] Similarly, using a well-known HTTPS URI on a hostname to bootstrap a separate service such as email can generate large volumes of undesired HTTP requests to web servers that do not implement the URI, resembling a denial-of-service attack.[1]

## Well-Known URI origin-root limitation and llms.txt

Well-Known URIs are bound strictly to the root of an origin's path hierarchy under RFC 8615, meaning nested paths such as `/foo/.well-known/example` do not qualify as well-known URIs.[1] This origin-level constraint aligns with site-wide discovery files such as `/robots.txt` and `/sitemap.xml` (see [Sitemaps](https://mimirwiki.com/wiki/sitemaps)), yet creates practical constraints for conventions that need per-directory metadata or shared-host publishing.[1][10]

The [llms.txt](https://mimirwiki.com/wiki/llms-txt) proposal, published by Jeremy Howard on 2024-09-03 and revised as v2 on 2026-08-10, illustrates this architectural trade-off.[10] llms.txt specifies placing a Markdown overview file named `llms.txt` at the site root (`/llms.txt`) or at any subpath (such as `/docs/llms.txt`), where each file covers the URLs under its own directory and agents apply the most specific file when multiple files exist.[10] For programmatic discovery, llms.txt v2 recommends standard link relations (`rel="alternate"` with `type="text/markdown"` for Markdown page versions and `rel="describedby"` for the governing `llms.txt` file) delivered via HTML `link` elements or HTTP `Link` headers.[10]

In discussing existing standards, the llms.txt specification explicitly contrasts its subpath model with RFC 8615 well-known URIs.[10] Because well-known URIs exist solely at the origin root, authors who control only a subdirectory on a shared host (such as a GitHub Pages project site) can publish files in their own directory yet cannot add entries to the host's `/.well-known/` space.[10] By functioning like `index.html` at any path, `llms.txt` allows any publisher with write access to a path to describe that specific section of a site, a per-path scope that a single origin-root location cannot express.[10]

## Frequently asked questions

### What are Well-Known URIs?

Well-Known URIs are Uniform Resource Identifiers whose path begins with /.well-known/ on URI schemes explicitly defined to support them, such as HTTP, HTTPS, WS, and WSS. Specified in IETF RFC 8615, they provide a standardized location for origin-wide metadata and service discovery while avoiding collisions with an origin's own URI space. [1]

### How does RFC 8615 differ from RFC 5785?

RFC 8615 (May 2019) obsoletes RFC 5785 (April 2010), updates RFC 7230 for the http and https schemes, and updates RFC 7595 so the IANA URI Schemes registry tracks schemes that support well-known URIs. It also adds permanent and provisional registration statuses, explicitly states the origin-root path restriction, and expands security guidance for browser interaction, scoping, and hidden directories. [1][2]

### How are new Well-Known URI suffixes registered?

Applications must register new suffixes in the IANA Well-Known URIs registry under the Specification Required policy from RFC 8126, subject to Designated Expert review. Requests are submitted via the IANA registry interface or the wellknown-uri-review@ietf.org mailing list and must include the URI suffix, change controller, defining specification document, and permanent or provisional status. [1][3][8]

### What are some notable registered Well-Known URI suffixes?

Permanent suffixes in the IANA registry include security.txt (RFC 9116) for vulnerability disclosure, acme-challenge (RFC 8555) for automated domain validation in certificate issuance, oauth-authorization-server (RFC 8414) and oauth-protected-resource (RFC 9728) for OAuth 2.0 metadata, and openid-configuration for OpenID Connect Discovery 1.0. [3][4][5][6][7][9]

### Can a Well-Known URI be placed in a subdirectory such as /app/.well-known/?

No. Under RFC 8615, well-known URIs are rooted strictly at the top of the path hierarchy, so /.well-known/example qualifies as a well-known URI while a nested path such as /foo/.well-known/example does not. [1]

### Why does the llms.txt proposal place files outside /.well-known/?

The llms.txt specification notes that RFC 8615 restricts well-known URIs to the origin root, which prevents authors who control only a subdirectory on a shared host such as GitHub Pages from publishing under /.well-known/. Placing llms.txt at the root or any subpath lets each file describe its own directory, similar to index.html. [1][10]

## Quotable sentences

- IETF RFC 8615, published in May 2019 by Mark Nottingham, defines the /.well-known/ path prefix and obsoletes RFC 5785. [1][2]
- RFC 8615 reserves /.well-known/ in HTTP, HTTPS, WS, and WSS URIs and updates RFC 7230 and RFC 7595. [1]
- Well-known URIs are restricted to the top of an origin's path hierarchy, and registered suffixes must conform to the RFC 3986 segment-nz syntax without a slash character. [1]
- The IANA Well-Known URIs registry was created on 2010-01-20 and operates under the Specification Required policy from RFC 8126 with Designated Expert review. [1][3][8]
- As of 2026-11-23, the IANA Well-Known URIs registry lists its last update as 2026-10-26 and names Mark Nottingham as Designated Expert. [3]
- The security.txt suffix (RFC 9116) was registered as permanent on 2021-07-13, and the acme-challenge suffix (RFC 8555, Section 8.3) was registered as permanent on 2016-08-18. [3][4][5]
- The IANA registry records permanent suffixes for openid-configuration (2013-08-27), oauth-authorization-server (2018-03-27, RFC 8414), and oauth-protected-resource (2024-10-22, RFC 9728). [3][6][7][9]
- The llms.txt proposal omits the /.well-known/ prefix because well-known URIs exist only at the origin root and cannot be published by authors who control only a subpath on a shared host. [1][10]

## Timeline

- 2010-01-20: IANA creates the Well-Known URIs registry. [3]
- 2010-04: The IETF publishes RFC 5785, authored by Mark Nottingham and E. Hammer-Lahav, defining the /.well-known/ path prefix and registration procedure. [2]
- 2013-08-27: The openid-configuration suffix is registered as permanent in the IANA Well-Known URIs registry. [3][9]
- 2016-08-18: The acme-challenge suffix for ACME HTTP domain validation is registered as permanent in the IANA registry. [3][5]
- 2017-06: The IETF publishes RFC 8126 (BCP 26), updating the IANA registry policy framework including Specification Required. [8]
- 2018-06: The IETF publishes RFC 8414 for OAuth 2.0 Authorization Server Metadata, following registration of oauth-authorization-server on 2018-03-27. [3][6]
- 2019-03: The IETF publishes RFC 8555 specifying the Automatic Certificate Management Environment (ACME) protocol. [5]
- 2019-05: The IETF publishes RFC 8615 by Mark Nottingham, obsoleting RFC 5785 and updating RFC 7230 and RFC 7595. [1]
- 2022-04: The IETF publishes RFC 9116 defining the security.txt vulnerability disclosure format, following registration of security.txt on 2021-07-13. [3][4]
- 2025-04: The IETF publishes RFC 9728 for OAuth 2.0 Protected Resource Metadata, following registration of oauth-protected-resource on 2024-10-22. [3][7]
- 2026-10-26: IANA records the latest update to the Well-Known URIs registry as of 2026-11-23. [3]

## Sources

1. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). published 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (checked 2026-11-23; tier 1: government or public registry)
2. RFC 5785: Defining Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). published 2010-04. https://www.rfc-editor.org/rfc/rfc5785.txt (checked 2026-11-23; tier 1: government or public registry)
3. Well-Known URIs. Internet Assigned Numbers Authority (IANA). published 2026-10-26. https://www.iana.org/assignments/well-known-uris (checked 2026-11-23; tier 1: government or public registry)
4. RFC 9116: A File Format to Aid in Security Vulnerability Disclosure. Internet Engineering Task Force (IETF). published 2022-04. https://www.rfc-editor.org/rfc/rfc9116.txt (checked 2026-11-23; tier 1: government or public registry)
5. RFC 8555: Automatic Certificate Management Environment (ACME). Internet Engineering Task Force (IETF). published 2019-03. https://www.rfc-editor.org/rfc/rfc8555.txt (checked 2026-11-23; tier 1: government or public registry)
6. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). published 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (checked 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). published 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (checked 2026-11-23; tier 1: government or public registry)
8. RFC 8126: Guidelines for Writing an IANA Considerations Section in RFCs. Internet Engineering Task Force (IETF). published 2017-06. https://www.rfc-editor.org/rfc/rfc8126.txt (checked 2026-11-23; tier 1: government or public registry)
9. Final: OpenID Connect Discovery 1.0 incorporating errata set 2. OpenID Foundation. published 2023-12-15. https://openid.net/specs/openid-connect-discovery-1_0.html (checked 2026-11-23; tier 3: official site)
10. The /llms.txt file, v2 – llms-txt. llmstxt.org. published 2024-09-03. https://llmstxt.org/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Well-Known URIs." Version d6008a83, 2026-11-23. https://mimirwiki.com/wiki/well-known-uri
