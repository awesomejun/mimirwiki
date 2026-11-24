---
title: "OAuth"
subtitle: "Open authorization framework standardized by the IETF for delegated HTTP access using access tokens"
canonical_url: https://mimirwiki.com/wiki/oauth
language: en
page_class: anchor
revision_sha256: 0bf8028f29fb0e920c7c79cf02a4172c03752d793fe6e528dd21af7cb2d9ba58
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/oauth.md
  txt: https://mimirwiki.com/wiki/oauth.txt
  json: https://mimirwiki.com/wiki/oauth.json
  jsonld: https://mimirwiki.com/wiki/oauth.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/oauth
  ja: https://mimirwiki.com/ja/wiki/oauth
  zh: https://mimirwiki.com/zh/wiki/oauth
---

# OAuth

> OAuth is an IETF authorization framework that lets an application access HTTP resources with an access token issued by an authorization server without receiving the resource owner's credentials. Published as OAuth 2.0 in RFC 6749 in October 2012 and updated by RFC 9700 in January 2025, OAuth is used by OpenID Connect and Model Context Protocol authorization.

OAuth is an open authorization framework for HTTP services that allows a third-party application to obtain limited access to protected resources on behalf of a resource owner or on its own behalf using an access token. Originally stabilized as a community specification in October 2007 and documented as OAuth 1.0 in RFC 5849 (April 2010), the protocol was replaced on the IETF Standards Track by OAuth 2.0 in RFC 6749 and RFC 6750 in October 2012. Subsequent IETF specifications extended OAuth 2.0 with Proof Key for Code Exchange (RFC 7636), Authorization Server Metadata (RFC 8414), Best Current Practice for OAuth 2.0 Security (RFC 9700, BCP 240), and Protected Resource Metadata (RFC 9728). As of 2026-11-23, the IETF OAuth Working Group is developing OAuth 2.1 (draft-ietf-oauth-v2-1-17) to consolidate OAuth 2.0 and its later security requirements into one specification.

**Also known as:** OAuth 2.0, OAuth 2.1, OAuth 1.0, The OAuth 2.0 Authorization Framework, RFC 6749

## Key facts

- **Standards body:** Internet Engineering Task Force (IETF) OAuth Working Group [8]
- **Core specification:** RFC 6749 (OAuth 2.0, October 2012) [1]
- **Security BCP:** RFC 9700 / BCP 240 (January 2025) [6]
- **Roles:** Resource owner, resource server, client, authorization server [1]
- **OAuth 2.1 draft status:** draft-ietf-oauth-v2-1-17 (Active Internet-Draft, updated 2026-10-30) (as of 2026-11-23) [8]

## Basic facts

- **Type:** HTTP authorization framework [1]
- **Standards body:** Internet Engineering Task Force (IETF) OAuth Working Group [8]
- **OAuth 1.0:** Stabilized October 2007; Revision A June 2009; RFC 5849 (Informational, April 2010) [4]
- **OAuth 2.0 framework:** RFC 6749 (Standards Track, October 2012; editor D. Hardt) [1]
- **Bearer token usage:** RFC 6750 (Standards Track, October 2012; TLS required) [2]
- **PKCE:** RFC 7636 (Standards Track, September 2015) [3]
- **Server metadata:** RFC 8414 (Standards Track, June 2018) [5]
- **Security BCP:** RFC 9700 / BCP 240 (January 2025; updates RFCs 6749, 6750, and 6819) [6]
- **Protected resource metadata:** RFC 9728 (Standards Track, April 2025) [7]
- **OAuth 2.1 status:** Active Internet-Draft draft-ietf-oauth-v2-1-17 (updated 2026-10-30, expires 2027-05-04) (as of 2026-11-23) [8]
- **OAuth 2.0 roles:** Resource owner, resource server, client, authorization server [1]
- **Protocols built on OAuth 2.0:** OpenID Connect, UMA 2.0, IndieAuth [9]

## OAuth origins and transition from OAuth 1.0 to OAuth 2.0

OAuth separates the role of a third-party client from that of a resource owner so an application can access HTTP resources using an access token issued by an authorization server, without holding the resource owner's credentials.[1] Under traditional client-server password sharing, third-party applications had to store user passwords in clear text, received broad access without scope or lifetime limits, could not be revoked individually without changing the password, and exposed the user's password and all protected data upon compromise.[1]

OAuth 1.0 was created by a small community of web developers to provide delegated access to protected resources.[4] The specification was stabilized at version 1.0 in October 2007 and revised in June 2009 as OAuth Core 1.0 Revision A (`oauth.net/core/1.0a`).[4] The original authors transferred change control to the IETF, which published RFC 5849 (edited by E. Hammer-Lahav) in April 2010 as an Informational document covering Revision A and reported errata.[4] OAuth 1.0 defined three roles: client (originally Consumer), server (originally Service Provider), and resource owner (originally User).[4] It used three classes of identifier-and-shared-secret credentials (client, temporary, and token credentials) and authenticated HTTP requests with nonces, timestamps, and cryptographic signatures (`HMAC-SHA1`, `RSA-SHA1`, or `PLAINTEXT`).[4]

In October 2012, the IETF published OAuth 2.0 on the Standards Track in RFC 6749 (edited by D. Hardt) alongside Bearer Token Usage in RFC 6750 (by M. Jones and D. Hardt).[1][2] RFC 6749 replaces and obsoletes RFC 5849.[1] OAuth 2.0 is designed for HTTP and is not backward compatible with OAuth 1.0, although both versions can coexist on a network and implementations can support both.[1] Use of OAuth 2.0 over protocols other than HTTP is outside the scope of RFC 6749.[1]

## OAuth 2.0 roles, endpoints, tokens, and grant types

OAuth 2.0 defines four roles in RFC 6749 for delegated access to HTTP resources.[1]

| Role | Definition in RFC 6749 |
| --- | --- |
| Resource owner | An entity capable of granting access to a protected resource; referred to as an end-user when a person |
| Resource server | The server hosting protected resources that accepts and responds to requests using access tokens |
| Client | An application making protected resource requests on behalf of the resource owner and with its authorization |
| Authorization server | The server issuing access tokens to the client after authenticating the resource owner and obtaining authorization |

The authorization server and the resource server may run on the same server or as separate entities, and a single authorization server can issue access tokens accepted by multiple resource servers.[1] RFC 6749 defines two authorization server endpoints, the Authorization Endpoint and the Token Endpoint, together with the client's Redirection Endpoint.[1] In the abstract flow, a client obtains an authorization grant from the resource owner, exchanges the grant at the authorization server for an access token representing a specific scope, lifetime, and access attributes, and presents that access token to the resource server.[1][2] In some flows, a client presents its own credentials directly to the authorization server to obtain an access token without a resource owner grant.[1][2]

RFC 6750 specifies how clients present bearer access tokens over HTTP/1.1 with Transport Layer Security (TLS), which is mandatory to implement and use.[2] Any party in possession of a bearer token can use it to access the associated resources without proving possession of cryptographic key material, so bearer tokens require protection from disclosure in storage and transport.[2] RFC 6750 defines three transmission methods: the `Authorization` request header field using the `Bearer` scheme (`Authorization: Bearer <token>`), a form-encoded body parameter, and a URI query parameter, with clients prohibited from using more than one method in a single request.[2] It also registers the `Bearer` access token type and the `WWW-Authenticate` error values `invalid_request`, `invalid_token`, and `insufficient_scope` with IANA.[2]

RFC 6749 defines four authorization grant types: Authorization Code, Implicit, Resource Owner Password Credentials, and Client Credentials, along with Refresh Token issuance and an Extension Grants mechanism.[1] Later IETF specifications added flows such as the Device Authorization Grant (RFC 8628) for devices without a browser or keyboard.[9] Subsequent security guidance in RFC 9700 deprecates less secure operating modes, the OAuth community site lists Implicit and Password grants as legacy, and OAuth 2.1 omits both grants.[6][9][10]

## OAuth 2.0 PKCE and Security Best Current Practice (RFC 9700)

OAuth 2.0 public clients using the Authorization Code Grant are vulnerable to authorization code interception attacks, which the IETF addressed in September 2015 with Proof Key for Code Exchange (PKCE, pronounced "pixy") in RFC 7636 (by N. Sakimura, J. Bradley, and N. Agarwal).[3] In this attack on an end device such as a smartphone, a malicious application registers the same custom URI scheme as a legitimate native OAuth 2.0 application, intercepts the authorization code returned through operating system inter-application redirection, and exchanges that code for an access token.[3]

PKCE mitigates interception by requiring the client to generate a unique, cryptographically random `code_verifier` for each authorization request and send a transformed value called a `code_challenge` to the authorization endpoint.[3] When submitting the authorization code to the token endpoint, the client includes the original `code_verifier` so the authorization server can verify the binding before issuing tokens.[3] RFC 7636 defines two initial `code_challenge_method` values: `plain`, which mitigates observation of authorization responses alone, and `S256`, which also mitigates scenarios where an attacker can read authorization requests, such as through leaked operating system HTTP logs.[3]

In January 2025, the IETF published Best Current Practice for OAuth 2.0 Security as RFC 9700 (BCP 240, by T. Lodderstedt, J. Bradley, A. Labunets, and D. Fett), updating RFCs 6749, 6750, and 6819.[6] RFC 9700 addresses real-world implementation weaknesses, high-security deployments (including open banking, eHealth, eGovernment, and electronic signatures), dynamic client-server relationships, and browser changes affecting URL fragment handling during redirects.[6] Its core requirements include the following measures.[6]

- Exact string matching when comparing client redirection URIs against pre-registered URIs, except for port numbers in localhost redirection URIs of native applications
- Prohibition on exposing open redirectors on clients and authorization servers
- Mandatory Cross-Site Request Forgery (CSRF) protection via PKCE (when authorization server support is verified), the OpenID Connect `nonce` parameter, or one-time CSRF tokens in `state` bound to the user agent
- Mandatory mix-up attack defenses when a client interacts with more than one authorization server, using the `iss` parameter (RFC 9207), an `iss` claim in an ID Token or JARM response, or distinct redirection URIs
- Mandatory PKCE for public clients in the Authorization Code Grant, recommended PKCE for confidential clients, and conditional use of `nonce` by confidential OpenID Connect clients
- Deprecation of less secure or insecure operating modes, paired with guidance on sender-constrained access tokens, audience-restricted access tokens, and refresh token protection

Additional IETF OAuth Working Group specifications support higher-security and token lifecycle requirements, including Pushed Authorization Requests (PAR, RFC 9126), Demonstration of Proof of Possession (DPoP, RFC 9449), Mutual TLS (RFC 8705), JWT Profile for Access Tokens (RFC 9068), Token Introspection (RFC 7662), Token Revocation (RFC 7009), Token Exchange (RFC 8693), Rich Authorization Requests (RAR, RFC 9396), Step-up Authentication Challenge (RFC 9470), and Security of Cross-Device Flows (RFC 10027).[9]

## OAuth 2.0 metadata and discovery specifications

OAuth 2.0 originally assumed static relationships in which server URLs were known to clients at deployment time, and subsequent IETF specifications added JSON metadata discovery at [well-known URIs](https://mimirwiki.com/wiki/well-known-uri) for dynamic environments.[5][6][7]

OAuth 2.0 Authorization Server Metadata, published on the Standards Track as RFC 8414 in June 2018 (by M. Jones, N. Sakimura, and J. Bradley), generalizes OpenID Connect Discovery 1.0 in a compatible format for broader OAuth 2.0 deployments.[5] Clients retrieve a JSON document from a `.well-known` location (per RFC 5785) derived from the authorization server's `issuer` URL, which uses the `https` scheme with no query or fragment components and also assists in preventing mix-up attacks.[5] Metadata can be delivered as self-asserted JSON over HTTPS or as signed claims in a JSON Web Token (JWT).[5] Registered metadata parameters include `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `registration_endpoint` (RFC 7591), `scopes_supported`, `response_types_supported`, `response_modes_supported` (defaulting to `query` and `fragment`, with `form_post` also defined), and `grant_types_supported`.[5]

OAuth 2.0 Protected Resource Metadata, published on the Standards Track as RFC 9728 in April 2025 (by M.B. Jones, P. Hunt, and A. Parecki), defines a parallel JSON metadata format enabling clients and authorization servers to discover how to interact with an OAuth 2.0 protected resource.[7] Each protected resource publishes its metadata at a `.well-known` location (per RFC 8615) deterministically derived from its `https` resource identifier, either self-asserted or signed as JWT claims.[7] Registered parameters include `resource` (required), `authorization_servers` (a list of RFC 8414 issuer identifiers), `jwks_uri`, `scopes_supported`, and `bearer_methods_supported` (`header`, `body`, and `query`).[7] RFC 9728 also defines how protected resources use the `WWW-Authenticate` HTTP header to dynamically inform clients of the protected resource metadata URL.[7]

For programmatic client onboarding, RFC 7591 specifies the OAuth 2.0 Dynamic Client Registration Protocol and RFC 7592 defines experimental registration management.[5][9] As of 2026-11-23, the OAuth Working Group is also developing Client ID Metadata Documents (`draft-ietf-oauth-client-id-metadata-document-00`) alongside other working group drafts such as Cross-App Access (XAA).[9][12]

## OAuth 2.1 consolidation and IETF draft status

OAuth 2.1 is an active IETF OAuth Working Group specification effort to consolidate OAuth 2.0 (RFC 6749), Bearer Token Usage (RFC 6750), and subsequent specifications into a single document.[8][10] It incorporates changes from RFC 7636 (PKCE), RFC 8252 (OAuth 2.0 for Native Apps), RFC 10017 (OAuth for Browser-Based Apps), and RFC 9700 (OAuth 2.0 Security Best Current Practice).[6][10]

As of 2026-11-23, `draft-ietf-oauth-v2-1-17` (authored by Dick Hardt, Aaron Parecki as editor, and Torsten Lodderstedt, replacing `draft-parecki-oauth-v2-1`) is an Active Internet-Draft on the intended Standards Track that would obsolete RFC 6749 and RFC 6750 if approved.[8] IETF Datatracker lists revision 17 as last updated on 2026-10-30 (with draft date 2026-10-31) and expiring on 2027-05-04, with an OAuth Working Group milestone of December 2026 to submit the draft to the IESG.[8] The IETF classifies an Internet-Draft as work in progress, and the document has not been published as a finalized RFC.[8] Its draft source and issue tracker are maintained at `github.com/oauth-wg/oauth-v2-1`.[8]

The OAuth community documentation for OAuth 2.1 lists seven major differences from OAuth 2.0, reflected in the structure of `draft-ietf-oauth-v2-1-17` as of 2026-11-23.[8][10]

| Area | OAuth 2.1 rule (draft-ietf-oauth-v2-1-17) |
| --- | --- |
| PKCE | Required for all OAuth clients using the authorization code flow |
| Redirect URIs | Must be compared using exact string matching |
| Implicit grant | Omitted (`response_type=token` removed) |
| Resource Owner Password Credentials grant | Omitted |
| Bearer tokens in URI query strings | Omitted; resource requests use the Authorization header field or form-encoded content parameter |
| Public-client refresh tokens | Must be either sender-constrained or rotated |
| Client type definitions | Public and confidential client definitions simplified to whether the client has credentials |

In addition to bearer tokens, `draft-ietf-oauth-v2-1-17` includes a dedicated section on sender-constrained access tokens and limits core grant types to Authorization Code, Client Credentials, Refresh Token, and Extension Grants.[8]

## OAuth in OpenID Connect and Model Context Protocol authorization

OAuth 2.0 forms the base authorization layer for protocols including OpenID Connect (OpenID Foundation), UMA 2.0 (Kantara), IndieAuth (W3C), and transport authorization in the [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (MCP).[9][11][12]

OpenID Connect is an interoperable authentication protocol built on RFC 6749 and RFC 6750 that lets applications verify end-user identity based on authentication performed by an authorization server, called an OpenID Provider (OP) or Identity Provider (IDP), and retrieve user profile claims from a REST-like UserInfo Endpoint.[11] Applications that delegate user authentication to an OP are called Relying Parties (RPs).[11] In an OpenID Connect flow, the RP sends an authentication request to the OP, the OP authenticates the end-user and obtains authorization, and the OP responds with an Identity Token containing at minimum a `sub` (subject) claim and authentication metadata, usually together with an access token.[11] OpenID Connect relies on HTTPS/TLS for transport encryption and JSON Web Token (JWT) structures when signatures are required across web, mobile, and JavaScript clients, supporting optional features such as identity data encryption, provider discovery, and session logout.[11] The OpenID Foundation contrasts this JSON and REST design with XML-based identity protocols such as OpenID 2.0 and SAML.[11]

The Model Context Protocol specification (version 2026-07-28) defines optional transport-level authorization for HTTP-based transports, while implementations using STDIO transports retrieve credentials from the environment.[12] In MCP authorization, a protected MCP server acts as an OAuth 2.1 resource server, an MCP client acts as an OAuth 2.1 client making requests on behalf of a resource owner, and an authorization server interacts with the user and issues access tokens.[12] Version 2026-07-28 specifies a subset of OAuth and OpenID Connect standards as of 2026-11-23.[12]

- Core flow and tokens: OAuth 2.1 IETF Draft (`draft-ietf-oauth-v2-1-13`) and Bearer Token Usage (RFC 6750)
- Protected resource discovery: Mandatory OAuth 2.0 Protected Resource Metadata (RFC 9728) on MCP servers and clients; MCP servers return HTTP 401 `WWW-Authenticate: Bearer` headers carrying `resource_metadata` (such as `/.well-known/oauth-protected-resource`) and optional `scope` guidance for least-privilege and step-up authorization
- Authorization server discovery: Authorization servers must provide OAuth 2.0 Authorization Server Metadata (RFC 8414) or OpenID Connect Discovery 1.0, and MCP clients must support both
- Resource and issuer binding: Mandatory Resource Indicators for OAuth 2.0 (RFC 8707), requiring a `resource` parameter with the MCP server's canonical URI in both authorization and token requests, and RFC 9207 `iss` parameter validation against the recorded issuer before sending an authorization code to a token endpoint
- Client registration: OAuth Client ID Metadata Documents (`draft-ietf-oauth-client-id-metadata-document-00`), pre-registration, or Dynamic Client Registration (RFC 7591 and OpenID Connect Dynamic Client Registration 1.0), with RFC 7591 deprecated in MCP and retained for backward compatibility

## Frequently asked questions

### What is OAuth?

OAuth is an IETF authorization framework for HTTP services that allows a third-party application to obtain limited access to protected resources using an access token issued by an authorization server, without receiving the resource owner's credentials. OAuth 2.0 was published on the IETF Standards Track in RFC 6749 and RFC 6750 in October 2012. [1][2]

### What are the four roles in OAuth 2.0?

RFC 6749 defines four roles: the resource owner (an entity capable of granting access to a protected resource, referred to as an end-user when a person), the resource server (the server hosting protected resources), the client (the application making protected resource requests with authorization), and the authorization server (the server that authenticates the resource owner and issues access tokens). [1]

### What is PKCE and why is it used in OAuth 2.0?

Proof Key for Code Exchange (PKCE), specified in RFC 7636 in September 2015, mitigates authorization code interception and injection attacks in the Authorization Code Grant by binding the authorization request to the token request with a dynamically created random code verifier and its transformed code challenge. RFC 9700 requires PKCE for public clients and recommends it for confidential clients. [3][6]

### What changed in RFC 9700, the OAuth 2.0 Security Best Current Practice?

Published in January 2025 as BCP 240, RFC 9700 updates RFCs 6749, 6750, and 6819 by requiring exact string matching for redirection URIs (except port numbers in localhost redirection URIs of native apps), prohibiting open redirectors, requiring CSRF protection and mix-up attack defenses such as the RFC 9207 iss parameter, requiring PKCE for public clients, and deprecating less secure modes of operation. [6]

### Is OAuth 2.1 a finalized standard?

As of 2026-11-23, OAuth 2.1 is an active IETF OAuth Working Group Internet-Draft (draft-ietf-oauth-v2-1-17, last updated 2026-10-30, expiring 2027-05-04) with a working group milestone of December 2026 for IESG submission. The draft consolidates OAuth 2.0 and subsequent RFCs, omits the Implicit and Resource Owner Password Credentials grants and URI query-string bearer tokens, and requires PKCE for all clients using the authorization code flow. [8][10]

### How do OpenID Connect and the Model Context Protocol use OAuth?

OpenID Connect is an authentication protocol built on OAuth 2.0 (RFC 6749 and RFC 6750) in which an OpenID Provider returns an Identity Token and a UserInfo Endpoint supplies user profile claims. Model Context Protocol specification version 2026-07-28 uses OAuth 2.1, RFC 6750, RFC 8414, RFC 9728, RFC 8707, and RFC 9207 for optional HTTP transport authorization, treating a protected MCP server as an OAuth 2.1 resource server. [11][12]

## Quotable sentences

- OAuth 1.0 was stabilized in October 2007, revised as Revision A in June 2009, and published as Informational RFC 5849 in April 2010. [4]
- RFC 6749, published on the IETF Standards Track in October 2012, defines the OAuth 2.0 authorization framework and obsoletes RFC 5849. [1]
- RFC 6750 defines HTTP Bearer Token usage for OAuth 2.0 protected resources and requires Transport Layer Security (TLS). [2]
- RFC 7636, published in September 2015, specifies Proof Key for Code Exchange (PKCE) to mitigate authorization code interception attacks against OAuth 2.0 public clients. [3]
- RFC 8414 (June 2018) and RFC 9728 (April 2025) define JSON metadata documents served from .well-known URIs for OAuth 2.0 authorization servers and protected resources. [5][7]
- RFC 9700 (BCP 240), published in January 2025, updates RFCs 6749, 6750, and 6819 with best current security practices for OAuth 2.0. [6]
- As of 2026-11-23, OAuth 2.1 is an active IETF Internet-Draft (draft-ietf-oauth-v2-1-17, updated 2026-10-30) intended to obsolete RFC 6749 and RFC 6750 if approved. [8]
- Model Context Protocol specification version 2026-07-28 requires protected MCP servers using HTTP authorization to implement RFC 9728 and requires MCP clients to send the RFC 8707 resource parameter. [12]

## Timeline

- 2007-10: Web developers stabilize the OAuth 1.0 protocol. [4]
- 2009-06: OAuth Core 1.0 Revision A is published at oauth.net/core/1.0a. [4]
- 2010-04: The IETF publishes RFC 5849 (The OAuth 1.0 Protocol) as an Informational RFC. [4]
- 2012-10: The IETF publishes RFC 6749 (The OAuth 2.0 Authorization Framework) and RFC 6750 (Bearer Token Usage) on the Standards Track, obsoleting RFC 5849. [1][2]
- 2015-09: The IETF publishes RFC 7636, specifying Proof Key for Code Exchange (PKCE) for OAuth public clients. [3]
- 2018-06: The IETF publishes RFC 8414, defining OAuth 2.0 Authorization Server Metadata. [5]
- 2025-01: The IETF publishes RFC 9700 (BCP 240), establishing Best Current Practice for OAuth 2.0 Security and updating RFCs 6749, 6750, and 6819. [6]
- 2025-04: The IETF publishes RFC 9728, defining OAuth 2.0 Protected Resource Metadata. [7]
- 2026-07-28: Model Context Protocol specification version 2026-07-28 specifies OAuth 2.1, RFC 9728, RFC 8414, RFC 8707, and RFC 9207 for HTTP-based transport authorization. [12]
- 2026-10-30: IETF Datatracker records revision 17 of the OAuth 2.1 Internet-Draft (draft-ietf-oauth-v2-1-17), with an expiration date of 2027-05-04 and a working group milestone of December 2026 for IESG submission. [8]

## Sources

1. RFC 6749: The OAuth 2.0 Authorization Framework. Internet Engineering Task Force (IETF). published 2012-10. https://www.rfc-editor.org/rfc/rfc6749.txt (checked 2026-11-23; tier 1: government or public registry)
2. RFC 6750: The OAuth 2.0 Authorization Framework: Bearer Token Usage. Internet Engineering Task Force (IETF). published 2012-10. https://www.rfc-editor.org/rfc/rfc6750.txt (checked 2026-11-23; tier 1: government or public registry)
3. RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Internet Engineering Task Force (IETF). published 2015-09. https://www.rfc-editor.org/rfc/rfc7636.txt (checked 2026-11-23; tier 1: government or public registry)
4. RFC 5849: The OAuth 1.0 Protocol. Internet Engineering Task Force (IETF). published 2010-04. https://www.rfc-editor.org/rfc/rfc5849.txt (checked 2026-11-23; tier 1: government or public registry)
5. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). published 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (checked 2026-11-23; tier 1: government or public registry)
6. RFC 9700: Best Current Practice for OAuth 2.0 Security. Internet Engineering Task Force (IETF). published 2025-01. https://www.rfc-editor.org/rfc/rfc9700.txt (checked 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). published 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (checked 2026-11-23; tier 1: government or public registry)
8. draft-ietf-oauth-v2-1-17 - The OAuth 2.1 Authorization Framework. Internet Engineering Task Force (IETF). published 2026-10-30. https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ (checked 2026-11-23; tier 1: government or public registry)
9. OAuth 2.0 - OAuth. OAuth Community Site. https://oauth.net/2/ (checked 2026-11-23; tier 3: official site)
10. OAuth 2.1. OAuth Community Site. https://oauth.net/2.1/ (checked 2026-11-23; tier 3: official site)
11. How OpenID Connect Works - OpenID Foundation. OpenID Foundation. published 2023-02-14. https://openid.net/developers/how-connect-works/ (checked 2026-11-23; tier 3: official site)
12. Authorization - Model Context Protocol. Model Context Protocol project. published 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "OAuth." Version 0bf8028f, 2026-11-23. https://mimirwiki.com/wiki/oauth
