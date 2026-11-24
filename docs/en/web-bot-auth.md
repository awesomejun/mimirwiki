---
title: "Web Bot Auth"
subtitle: "Cryptographic authentication protocol for automated HTTP clients and AI agents based on RFC 9421 HTTP Message Signatures"
canonical_url: https://mimirwiki.com/wiki/web-bot-auth
language: en
page_class: anchor
revision_sha256: d18facc66cbffedd50e1fcdc242ba4eced0de2197d41894cccb75782b898b44f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/web-bot-auth.md
  txt: https://mimirwiki.com/wiki/web-bot-auth.txt
  json: https://mimirwiki.com/wiki/web-bot-auth.json
  jsonld: https://mimirwiki.com/wiki/web-bot-auth.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/web-bot-auth
---

# Web Bot Auth

> Web Bot Auth is a cryptographic authentication protocol for automated HTTP clients, including crawlers and AI agents, built on RFC 9421 HTTP Message Signatures. Clients sign outbound requests with a private key and publish public keys in a JWKS directory, typically at /.well-known/http-message-signatures-directory, allowing servers to verify identity. The IETF webbotauth Working Group develops the specification.

Web Bot Auth is a cryptographic authentication protocol that allows automated HTTP clients, such as web crawlers and AI agents, to sign outbound requests using RFC 9421 HTTP Message Signatures so that web servers can verify their identity. Automated clients attach Signature, Signature-Input, and Signature-Agent headers to requests and publish their public signing keys in a JSON Web Key Set (JWKS) directory served over HTTPS, commonly at the well-known URI /.well-known/http-message-signatures-directory. The Internet Engineering Task Force (IETF) Web Bot Auth (webbotauth) Working Group is developing the Standards Track specification in draft-ietf-webbotauth-httpsig-protocol, authored by Thibault Meunier of Cloudflare and Sandor Major of Google. Cloudflare added Web Bot Auth with Ed25519 signing keys to its Verified Bots Program in July 2025.

**Also known as:** webbotauth, HTTP Message Signatures for Automated Traffic, RFC 9421 Web Bot Auth

## Key facts

- **Base standard:** RFC 9421 (HTTP Message Signatures, February 2024) [1]
- **Standards body:** IETF Web Bot Auth (webbotauth) Working Group [2]
- **Active specification:** draft-ietf-webbotauth-httpsig-protocol-01 (2026-10-29) (as of 2026-11-23) [4]
- **Well-known key directory:** /.well-known/http-message-signatures-directory [9]
- **Primary HTTP headers:** Signature, Signature-Input, Signature-Agent [9]

## Basic facts

- **Type:** Cryptographic HTTP authentication protocol for automated clients [5]
- **Base standard:** RFC 9421: HTTP Message Signatures (February 2024) [1]
- **Working group:** IETF Web Bot Auth (webbotauth), Web and Internet Transport area (as of 2026-11-23) [2]
- **Working group chairs:** David Schinazi, Rifaat Shekh-Yusef (as of 2026-11-23) [2]
- **Specification authors:** Thibault Meunier (Cloudflare), Sandor Major (Google) (as of 2026-11-23) [4]
- **Current draft:** draft-ietf-webbotauth-httpsig-protocol-01 (published 2026-10-29) (as of 2026-11-23) [4]
- **Key directory path:** /.well-known/http-message-signatures-directory [9]
- **Directory media type:** application/http-message-signatures-directory+json [4]
- **Cloudflare supported algorithm:** Ed25519 (OKP JSON Web Key) (as of 2026-10-08) [9]
- **Draft status:** Active IETF Internet-Draft (Standards Track intended) (as of 2026-11-23) [4]
- **Reference repository:** github.com/cloudflare/web-bot-auth (Apache-2.0 license) [12]

## What Web Bot Auth is

Web Bot Auth is a protocol for cryptographically authenticating automated HTTP clients, including search index crawlers, web archivers, link checkers, AI training crawlers, and AI agents acting on behalf of end users.[2][5] The protocol builds on RFC 9421, the IETF Standards Track specification for HTTP Message Signatures published in February 2024, which enables detached digital signatures over selected components of an HTTP message.[1][4] Web Bot Auth operates solely at the HTTP layer, leaving the transport layer and TLS stack unchanged so signatures remain verifiable across reverse proxies, gateways, and other HTTP intermediaries.[1][5]

Conventional bot identification mechanisms carry operational and security drawbacks.[2][5] `User-Agent` strings can be spoofed by arbitrary clients and are overloaded when an automated browser such as Chromium sends a standard browser string to ensure proper page rendering.[5] IP address allowlists require maintaining lists across cloud platforms with layered address ownership, while dedicated IP blocks incur acquisition costs, specialist setup, and prior reputation history.[5] Shared secrets such as OAuth Bearer tokens require per-site onboarding and complicate key rotation at web scale.[5]

Web Bot Auth addresses these requirements under two stated objectives and two constraints in `draft-ietf-webbotauth-httpsig-protocol`.[5] Its objectives are continuity of bot trust across requests and optional binding of signing keys to an external anchor such as a domain name.[5] Its constraints are preserving operational simplicity for both automated clients and websites and requiring no pre-established relationship between the client and the origin server.[5] Cloudflare publicly proposed this approach on May 15, 2025, and added HTTP Message Signatures to its Verified Bots Program on July 1, 2025.[10][11]

## How Web Bot Auth signs and verifies HTTP requests

Web Bot Auth uses detached signatures defined by RFC 9421 to authenticate outbound HTTP requests without duplicating message headers inside a separate token payload.[1][5] An automated client selects HTTP header fields and derived components, serializes them into a canonical signature base according to RFC 9421 rules, and computes a digital signature with a private key held by the bot provider.[1][5] RFC 9421 defines algorithms including RSASSA-PSS with SHA-512, RSASSA-PKCS1-v1_5 with SHA-256, HMAC with SHA-256, ECDSA with curves P-256 and P-384, and EdDSA using curve edwards25519 (Ed25519).[1] Test vectors in `draft-ietf-webbotauth-httpsig-protocol-01` cover RSASSA-PSS with SHA-512 and Ed25519, while Cloudflare's production implementation supports Ed25519.[4][9]

Signed requests carry three primary HTTP header fields.[1][9] The `Signature-Input` header lists the covered message components and signature metadata parameters, the `Signature` header carries the base64-encoded signature bytes, and the `Signature-Agent` header identifies the HTTPS URL where the client's public key directory can be fetched.[1][4][5][9] Because RFC 9421 signatures do not directly cover HTTP message bodies, applications that need body integrity rely on a `Content-Digest` header containing a cryptographic hash of the content.[1][9] RFC 9421 also defines an optional `Accept-Signature` header through which a recipient can request that subsequent HTTP messages carry signatures.[1]

Standard metadata parameters in `Signature-Input` bound signature scope and lifetime.[1][5][9]

| Parameter or header | Role in Web Bot Auth |
| --- | --- |
| `Signature-Agent` | Carries the HTTPS URL of the client's public key directory for in-band discovery.[4][5] |
| `Signature-Input` | Lists covered HTTP components (such as `@authority` and `signature-agent`) and signature metadata.[1][9] |
| `Signature` | Contains the detached cryptographic signature over the canonicalized signature base.[1][9] |
| `tag` | Identifies the application context, using `web-bot-auth` for bot requests and `http-message-signatures-directory` for signed directory responses in Cloudflare's implementation.[9] |
| `keyid` | Holds the base64url-encoded JSON Web Key (JWK) thumbprint identifying which public key verifies the signature.[5][9] |
| `created` and `expires` | Specify Unix timestamps that bound the signature validity window to limit replay exposure.[5][9] |
| `nonce` | Supplies an optional per-request value intended to mitigate replay attacks.[9] |

## Web Bot Auth key directories and trust model

Web Bot Auth publishes public signing keys in a JSON Web Key Set (JWKS) directory served over HTTPS, enabling verifiers to discover keys in-band from the `Signature-Agent` header.[4][5][6] Earlier individual drafts (`draft-meunier-http-message-signatures-directory`, updated through revision 05 on March 2, 2026) specified this directory format separately before the working group consolidated key discovery into `draft-ietf-webbotauth-httpsig-protocol`.[3][4][6] The draft registers the media type `application/http-message-signatures-directory+json` and the well-known URI `/.well-known/http-message-signatures-directory`.[4] Under RFC 8615, the `/.well-known/` path prefix is reserved at the root of an HTTP or HTTPS origin, so hosting the key directory at that path binds the key set to the domain operator.[5][7]

In the trust model defined by `draft-ietf-webbotauth-httpsig-protocol-01`, the verified `Signature-Agent` HTTPS URL serves as the agent's persistent identifier.[5] An unresolved `Signature-Agent` header is an unverified claim, and verifiers must hold off applying access policy until they resolve the URL over TLS and verify the request signature against a key returned by that directory.[5] Because identity attaches to the URL while `keyid` selects an individual key, an operator can rotate keys without breaking continuity by publishing a new key alongside the existing key and later removing the old key.[5] When a verifier holds a key directly without a resolved URL, attribution falls back to the `keyid` thumbprint, which has no continuity across key rotations.[5]

Resolving a key directory over TLS establishes that the host named in the URL served that key set at fetch time, and a valid request signature proves that the holder of one of those keys signed the covered components.[5] To prevent third parties from mirroring another operator's directory and claiming those keys, directory responses can carry HTTP message signatures proving possession of each listed private key.[4][9] When a verifier obtains directory records from multiple sources, the newer record takes precedence based on the directory signature's `created` timestamp or the verifier's own fetch time.[5] Verification proves cryptographic continuity and key possession, while determining whether an operator is trustworthy or authorized to access a site remains the origin server's policy decision.[5]

## IETF Web Bot Auth standardization

Web Bot Auth is standardized through the Internet Engineering Task Force (IETF) Web Bot Auth (`webbotauth`) Working Group in the Web and Internet Transport (`wit`) area.[2] As of 2026-11-23, the working group is active under approved charter `charter-ietf-webbotauth-01`, chaired by David Schinazi and Rifaat Shekh-Yusef with Mike Bishop as Area Director.[2] Its charter defines three deliverable categories: Standards Track specifications for authenticating automated clients to websites aimed at human users, Standards Track specifications for conveying additional metadata about requesting bots via widely used identifiers such as domain names or URLs, and Best Current Practice or Informational documents covering operational lifecycle, key management, deployment considerations, and effects on web openness.[2] The working group coordinates with the AIPREF, HTTPBIS, OAUTH, TLS, and WIMSE working groups.[2]

As of 2026-11-23, the working group holds one adopted Working Group Internet-Draft: `draft-ietf-webbotauth-httpsig-protocol-01` ("HTTP Message Signatures for automated traffic"), authored by Thibault Meunier of [Cloudflare](https://mimirwiki.com/wiki/cloudflare) and Sandor Major of Google.[3][4][5] Revision `-01`, a 44-page document published on October 29, 2026 and set to expire on May 2, 2027, replaces the earlier individual series `draft-meunier-webbotauth-httpsig-protocol`, which replaced `draft-meunier-web-bot-auth-architecture-05` after March 2, 2026.[3][4][5] The charter lists target milestones of April 2026 for submitting Standards Track authentication and bot-information specifications to the IESG and August 2026 for submitting the Best Current Practice operational document.[2]

Alongside the adopted protocol draft, 14 related individual Internet-Drafts were listed on the `webbotauth` documents page as of 2026-11-23.[3] These proposals explore complementary mechanisms including bot registries and Signature Agent Cards (`draft-meunier-webbotauth-registry-04`), signed agent metadata headers (`draft-vilgalys-webbotauth-signed-agent-metadata-00`), hosted key directories (`draft-singh-webbotauth-hosted-directories-00`), anonymous bot authentication (`draft-rescorla-anonymous-webbotauth-01`), verification outcome reporting (`draft-suresh-webbotauth-verification-outcome-00`), crawler best practices (`draft-illyes-webbotauth-cbcp-01`), and JSON-based IP range publishing (`draft-illyes-webbotauth-jafar-01`).[3] As Internet-Drafts, these documents remain works in progress without formal IETF RFC status.[5][6]

## Cloudflare Web Bot Auth implementation and tooling

Web Bot Auth is deployed in production within Cloudflare's Verified Bots Program, which added HTTP Message Signatures on July 1, 2025.[9][10] As documented in Cloudflare's developer reference updated on October 8, 2026, onboarding follows four steps: generating an Ed25519 key pair and converting the public key to a JWK (`kty: "OKP"`, `crv: "Ed25519"`, unpadded base64url `x`), hosting a signed JWKS directory over HTTPS at `/.well-known/http-message-signatures-directory`, registering the bot and directory URL in the Cloudflare dashboard under the `Request Signature` verification method, and signing outbound requests.[9] Directory responses must set `Content-Type: application/http-message-signatures-directory+json` and attach one HTTP message signature per Ed25519 key covering `@authority;req` with `tag="http-message-signatures-directory"`, `keyid`, `created`, and `expires`.[9]

As of October 8, 2026, Cloudflare's request verification follows earlier draft versions (`draft-meunier-web-bot-auth-architecture-02` and `draft-meunier-http-message-signatures-directory-03`) and enforces specific constraints.[9] Outbound requests must include `Signature-Agent` as a double-quoted structured string containing an `https://` URI, include `signature-agent` and at least `@authority` in `Signature-Input`, use ASCII-only component values, and set `tag="web-bot-auth"`.[9] Cloudflare rejects the dictionary syntax for `Signature-Agent` introduced in later drafts, does not support `@query-params` or `@status`, and fails validation if `Signature-Input` uses the RFC 9421 component parameters `sf`, `bs`, `key`, `req`, or `name`.[9] Although Cloudflare recommends sending a `nonce`, as of October 8, 2026 its verifier does not validate nonces or store seen nonces in a database; it recommends short `expires` intervals, such as one minute, to limit replay windows.[9] Operators can test request formatting and verification against `https://crawltest.com/cdn-cgi/web-bot-auth`, which returns HTTP 200 for verified known keys, HTTP 401 for unknown keys or failed verification, and HTTP 400 for malformed messages.[9]

Cloudflare also documents an experimental transitive trust mechanism using the RFC 7239 `Forwarded` header (such as `Forwarded: for="openai";use="reference"` as an illustrative syntax example) to convey bot operator identity and content-use commitments across intermediaries, noting that this feature may change.[9] Site owners who want to perform origin-side signature validation can ask Cloudflare Support to disable Cloudflare's verification on their zone so it does not populate `cf.bot_management.verified_bot`, causing verified bots to fall back to methods such as reverse DNS validation.[9]

Cloudflare maintains an Apache-2.0 open-source repository at `github.com/cloudflare/web-bot-auth` containing TypeScript packages (`http-message-sig`, `jsonwebkey-thumbprint`, `web-bot-auth`) and Rust crates (`web-bot-auth`, `http-signature-directory`), which had 188 stars and 52 forks as of 2026-11-23.[12] The repository includes signing and verification examples for browser extensions, Rust, a Caddy plugin, and Cloudflare Workers, alongside a Cloudflare Research test endpoint at `http-message-signatures-example.research.cloudflare.com`.[12] The repository documentation notes that the software has not been audited.[12]

## Web Bot Auth scope, security, and limitations

Web Bot Auth addresses cryptographic authentication of automated HTTP clients accessing web content intended primarily for human users, and the IETF `webbotauth` charter explicitly places several adjacent problems out of scope.[2] Out-of-scope items include authenticating access to machine-oriented HTTP APIs or agent-to-agent interfaces, authenticating the end user behind an agent, non-HTTP protocols, non-cryptographic identification, defining a vocabulary of bot intents, tracking or assigning bot reputation, and detecting bots that choose to remain unauthenticated.[2] Web Bot Auth is also distinct from the Robots Exclusion Protocol ([robots.txt](https://mimirwiki.com/wiki/robots-txt)), standardized in RFC 9309 in September 2022, which expresses voluntary crawl rules per `user-agent` token and explicitly states that those rules do not constitute access authorization.[8]

Cryptographic verification under Web Bot Auth carries defined security boundaries.[5] A valid signature confirms only that a request was signed by a key published at the resolved `Signature-Agent` URL, without certifying that the operator is benign or that a given request is authorized.[5] Nothing in the protocol prevents a client from abandoning one URL and standing up another, because the mechanism is designed for operators that want continuous recognition across requests.[5] Signed requests remain vulnerable to replay within their validity window, which operators bound through covered components and short `created` to `expires` intervals.[5][9]

Deploying in-band key discovery introduces operational risks addressed in the security and privacy considerations of `draft-ietf-webbotauth-httpsig-protocol-01`.[4] Because verifiers fetch arbitrary `Signature-Agent` HTTPS URLs presented by incoming requests, servers must guard against Server-Side Request Forgery (SSRF) and bound directory fetch resources and caching behavior.[4] The specification also highlights TLS requirements, key compromise response, avoidance of shared secrets and key reuse, handling of test or static signatures, reverse proxy interactions, and privacy implications of client identification, correlation, and directory access patterns.[4] In addition, the `webbotauth` charter directs the working group to account for operational overhead on bot clients and websites and to avoid introducing architectural bottlenecks.[2]

## Frequently asked questions

### What is Web Bot Auth?

Web Bot Auth is an HTTP-layer authentication protocol that lets automated clients, such as web crawlers and AI agents, cryptographically sign outbound requests using RFC 9421 HTTP Message Signatures. Servers verify those signatures against public keys published in a JSON Web Key Set directory. [1][4][5]

### How does a server find a bot's public keys in Web Bot Auth?

A signed request carries a Signature-Agent header containing an HTTPS URL for the bot's key directory. Servers fetch the JSON Web Key Set from that URL, commonly hosted at /.well-known/http-message-signatures-directory, and select the matching key using the keyid thumbprint parameter. [4][5][9]

### Is Web Bot Auth an official IETF RFC standard?

As of 2026-11-23, Web Bot Auth is an active work in progress at the IETF Web Bot Auth (webbotauth) Working Group. Its main specification, draft-ietf-webbotauth-httpsig-protocol-01, is a Standards Track Internet-Draft published on October 29, 2026, and has not been published as an RFC. [2][4][5]

### What cryptographic keys does Cloudflare support for Web Bot Auth?

As of October 8, 2026, Cloudflare's Web Bot Auth integration supports Ed25519 signing keys published as OKP JSON Web Keys at /.well-known/http-message-signatures-directory. Directory responses must include an HTTP message signature for each Ed25519 key to prove key possession. [9]

### How does Web Bot Auth handle key rotation without losing bot identity?

In draft-ietf-webbotauth-httpsig-protocol-01, the verified Signature-Agent HTTPS URL serves as the agent's identifier while keyid selects the individual key. An operator rotates keys by publishing the new public key alongside the existing one in the directory and removing the old key afterward, preserving continuity under the same URL. [5]

### Does Web Bot Auth replace robots.txt or authenticate end users?

No. The Robots Exclusion Protocol (RFC 9309) defines voluntary crawler access rules, and Web Bot Auth verifies automated client identity cryptographically. The IETF webbotauth Working Group charter explicitly places end-user authentication out of scope. [2][8]

## Quotable sentences

- Web Bot Auth uses detached digital signatures defined by RFC 9421 (HTTP Message Signatures, published February 2024) to authenticate automated HTTP requests. [1][4]
- As of 2026-11-23, the IETF Web Bot Auth (webbotauth) Working Group operates in the Web and Internet Transport area under approved charter charter-ietf-webbotauth-01. [2]
- The adopted working group draft draft-ietf-webbotauth-httpsig-protocol-01 was published on October 29, 2026 by Thibault Meunier of Cloudflare and Sandor Major of Google. [4][5]
- In draft-ietf-webbotauth-httpsig-protocol-01, the verified Signature-Agent HTTPS URL serves as the agent's identifier and enables key rotation without breaking identity continuity. [5]
- draft-ietf-webbotauth-httpsig-protocol-01 defines the well-known URI /.well-known/http-message-signatures-directory and the media type application/http-message-signatures-directory+json for publishing JWKS key directories. [4][7]
- Cloudflare added HTTP Message Signatures (Web Bot Auth) to its Verified Bots Program on July 1, 2025. [10]
- As of October 8, 2026, Cloudflare's Web Bot Auth implementation supports Ed25519 keys and requires signed directory responses over HTTPS at /.well-known/http-message-signatures-directory. [9]
- Cloudflare maintains open-source TypeScript and Rust Web Bot Auth libraries and examples in github.com/cloudflare/web-bot-auth under the Apache-2.0 license. [12]

## Timeline

- 2024-02: The IETF publishes RFC 9421 (HTTP Message Signatures) as a Standards Track specification. [1]
- 2025-05-15: Cloudflare publishes an initial proposal by Thibault Meunier and Mari Galicer for verifying bot and AI agent traffic with cryptographic HTTP signatures. [11]
- 2025-07-01: Cloudflare adds HTTP Message Signatures to its Verified Bots Program. [10]
- 2026-03-02: Thibault Meunier and Sandor Major publish revision 05 of draft-meunier-web-bot-auth-architecture and draft-meunier-http-message-signatures-directory, which are subsequently replaced by the webbotauth protocol and directory drafts. [3][6]
- 2026-10-08: Cloudflare updates its Web Bot Auth developer documentation covering Ed25519 key directories, request signing, and experimental RFC 7239 Forwarded header support. [9]
- 2026-10-29: The IETF webbotauth Working Group publishes draft-ietf-webbotauth-httpsig-protocol-01 (HTTP Message Signatures for automated traffic). [3][4][5]

## Sources

1. RFC 9421: HTTP Message Signatures. Internet Engineering Task Force (IETF). published 2024-02. https://www.rfc-editor.org/rfc/rfc9421.txt (checked 2026-11-23; tier 1: government or public registry)
2. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (checked 2026-11-23; tier 1: government or public registry)
3. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/documents/ (checked 2026-11-23; tier 1: government or public registry)
4. draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic. Internet Engineering Task Force (IETF). published 2026-10-29. https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/ (checked 2026-11-23; tier 1: government or public registry)
5. draft-ietf-webbotauth-httpsig-protocol-01. Internet Engineering Task Force (IETF). published 2026-10-29. https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol (checked 2026-11-23; tier 1: government or public registry)
6. draft-meunier-http-message-signatures-directory-05 - HTTP Message Signatures Directory. Internet Engineering Task Force (IETF). published 2026-03-02. https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/ (checked 2026-11-23; tier 1: government or public registry)
7. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). published 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (checked 2026-11-23; tier 1: government or public registry)
8. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). published 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (checked 2026-11-23; tier 1: government or public registry)
9. Web Bot Auth · Cloudflare bot solutions docs. Cloudflare. published 2026-10-08. https://developers.cloudflare.com/bots/reference/bot-verification/web-bot-auth/ (checked 2026-11-23; tier 3: official site)
10. Message Signatures are now part of our Verified Bots Program, simplifying bot authentication | Cloudflare Blog. The Cloudflare Blog. published 2025-07-01. https://blog.cloudflare.com/verified-bots-with-cryptography/ (checked 2026-11-23; tier 3: official site)
11. Forget IPs: using cryptography to verify bot and agent traffic | Cloudflare Blog. The Cloudflare Blog. published 2025-05-15. https://blog.cloudflare.com/web-bot-auth/ (checked 2026-11-23; tier 3: official site)
12. GitHub - cloudflare/web-bot-auth: Sign and verify orchestrated HTTP requests · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/web-bot-auth (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Web Bot Auth." Version d18facc6, 2026-11-23. https://mimirwiki.com/wiki/web-bot-auth
