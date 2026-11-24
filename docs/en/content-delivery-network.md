---
title: "Content Delivery Network"
subtitle: "Geographically distributed network of caching servers that delivers web content from locations close to end users"
canonical_url: https://mimirwiki.com/wiki/content-delivery-network
language: en
page_class: concept
revision_sha256: d0585d7842ed5639050fb37f855992e6e278f1d5d61df2ab3d4796fca7388bd7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/wiki/content-delivery-network.md
  txt: https://mimirwiki.com/wiki/content-delivery-network.txt
  json: https://mimirwiki.com/wiki/content-delivery-network.json
  jsonld: https://mimirwiki.com/wiki/content-delivery-network.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/content-delivery-network
  ja: https://mimirwiki.com/ja/wiki/content-delivery-network
  zh: https://mimirwiki.com/zh/wiki/content-delivery-network
---

# Content Delivery Network

> A content delivery network (CDN) is a distributed group of servers that stores copies of web content at locations close to end users. Acting as a managed shared HTTP cache between clients and origin servers, a CDN lowers latency, reduces origin server load, and improves availability. Core mechanisms use HTTP caching, targeted cache headers, anycast routing, and interconnection protocols.

A content delivery network (CDN) is a geographically distributed system of servers that stores copies of web objects and fulfills client requests from locations close to end users. Acting as a managed shared HTTP cache between clients and origin servers, a CDN reduces response latency, lowers origin server load, and improves delivery reliability under high traffic. Core CDN operations are standardized across Internet Engineering Task Force (IETF) specifications covering HTTP caching (RFC 9111), targeted CDN cache control (RFC 9213), anycast service distribution (RFC 4786), and CDN interconnection (RFC 6707 and RFC 7336). Commercial CDN deployments distribute both static assets and dynamic web content through worldwide points of presence (PoPs) while introducing operational trade-offs in cache freshness, security exposure, and third-party availability dependencies.

**Also known as:** CDN, Content Distribution Network, Content Delivery Network (CDN)

## Key facts

- **Cache classification:** Managed shared HTTP cache [7]
- **HTTP caching standard:** RFC 9111 (STD 98, June 2022) [1]
- **Targeted cache header:** CDN-Cache-Control (RFC 9213, June 2022) [2]
- **Anycast routing practice:** RFC 4786 (BCP 126, December 2006), IPv4 and IPv6 via IGP or BGP [5]
- **Interconnection framework:** CDNI Problem Statement (RFC 6707) and Framework (RFC 7336) [4]

## Basic facts

- **Category:** Distributed network infrastructure and managed shared HTTP cache [7]
- **Edge nodes:** Geographically dispersed data centers called edge locations or points of presence (PoPs) [8]
- **Origin sources:** Authoritative HTTP servers, web servers, or object storage buckets [8]
- **HTTP caching specification:** IETF RFC 9111 (STD 98, June 2022), obsoleting RFC 7234 [1]
- **Targeted cache control:** CDN-Cache-Control response header (IETF RFC 9213, June 2022) [2]
- **Required targeted directives:** max-age, must-revalidate, no-store, no-cache, private [2]
- **Anycast standard:** IETF RFC 4786 (BCP 126, December 2006) over IPv4 and IPv6 [5]
- **CDNI problem statement:** IETF RFC 6707 (Informational, September 2012) [3]
- **CDNI framework:** IETF RFC 7336 (Informational, August 2014), obsoleting RFC 3466 with RFC 6707 [4]
- **Primary assets served:** Static assets (HTML, CSS, JavaScript, images, media) and dynamic web content [8]
- **CloudFront default cache expiration:** 24 hours (minimum 0 seconds, no fixed maximum) (as of 2026-11-23) [8]
- **Client-side integrity safeguard:** Subresource Integrity (SRI) for third-party static asset CDNs [6]

## Content delivery network architecture and points of presence

A content delivery network (CDN) operates as a geographically dispersed group of caching servers that stores duplicate copies of web data and fulfills client requests from locations close to end users.[6][8] Origin servers hold the definitive version of web objects such as HTML pages, stylesheets (CSS), JavaScript files, images, and media files, and can be web servers, custom HTTP servers, or object storage services such as Amazon S3 buckets.[6][8] Edge locations, also referred to as points of presence (PoPs), are collections of servers in dispersed data centers where a CDN caches copies of those objects near viewers.[8]

When a client requests an object served through a CDN, the network routes the request to an edge location providing low latency.[8] If a usable copy is already stored at that edge location, the server returns it directly without forwarding the request to the origin server.[7][8] If the object is absent, the edge server retrieves the definitive version from the origin server and caches a copy for subsequent requests.[8] Because geographical distance affects latency proportionally, placing servers closer to end users shortens round-trip delivery time.[6] Commercial providers such as Amazon CloudFront also route requests over a private backbone network (the AWS backbone network) to reduce the number of intermediate networks traversed, lowering time to first byte and increasing data transfer rates while storing copies across multiple edge locations for availability.[8]

In HTTP architecture, a CDN acts as a managed shared cache deployed explicitly by service operators to offload request parsing, cookie-based session restoration, database queries, and template rendering from origin servers.[7] RFC 6707 identifies three primary benefits of CDN deployment for cacheable content: lower delivery cost, improved quality of experience for end users, and increased delivery robustness.[3] CDNs are widely used to serve static libraries (such as Bootstrap and jQuery), complete static websites, and dynamic web content.[6][8] As of 2026-11-23, Amazon CloudFront propagates distribution configurations (origin servers, logging, assigned or custom domain names, and access controls such as signed URLs and signed cookies for private content) to all edge locations while fetching objects on demand, offering both standalone standard distributions and multi-tenant distributions via CloudFront SaaS Manager.[8] As of 2026-11-23, CloudFront keeps objects cached at edge locations for 24 hours by default (with a 0-second minimum and no fixed maximum), bills for outbound data transfer from edge locations and HTTP or HTTPS requests, and charges no transfer fee from AWS origins (Amazon S3, Elastic Load Balancing, and Amazon API Gateway) to CloudFront.[8]

## HTTP caching mechanics in content delivery networks (RFC 9111)

Content delivery network caching relies on the HTTP Caching specification, published by the Internet Engineering Task Force (IETF) in June 2022 as RFC 9111 (STD 98), edited by R. Fielding (Adobe), M. Nottingham (Fastly), and J. Reschke (greenbytes), which obsoletes RFC 7234.[1] RFC 9111 defines an HTTP cache as a local store of response messages together with the subsystem that controls storage, retrieval, and deletion, reducing response time and network bandwidth consumption on equivalent subsequent requests.[1]

HTTP caching separates caches into private caches, which serve a single user (typically inside a web browser), and shared caches, which sit on intermediaries between clients and servers to serve multiple users.[1][7] MDN Web Docs further subdivides shared caches into proxy caches, usually operated outside the service developer's control, and managed caches explicitly deployed by service operators, including reverse proxies, CDNs, and service workers using the Cache API.[7] With widespread HTTPS encryption, network proxy caches along the path generally tunnel encrypted traffic without inspecting or caching responses, except in controlled enterprise environments where a TLS-bridging proxy decrypts traffic using an organization-managed certificate authority.[7]

A cache identifies stored responses using a cache key composed at minimum of the request method and target URI, although many deployed caches store only `GET` responses keyed by URI.[1] For content-negotiated resources, caches incorporate request headers specified in the `Vary` response header into the cache key.[1] Most cached items are `200 (OK)` responses to `GET` requests, though redirects, `404 (Not Found)` responses, and `206 (Partial Content)` responses can also be stored when rules allow.[1] Under Section 3 of RFC 9111, a shared cache must avoid storing a response when `no-store` is present, when `private` is present without permitting modified shared storage, or when the request contains an `Authorization` header without a response directive explicitly allowing shared caching; storage also requires an understood method, a final status code, and a caching indicator such as `public`, `Expires`, `max-age`, `s-maxage`, a cache extension, or a heuristically cacheable status code.[1]

Stored responses exist in one of two states: fresh (reusable without contacting the origin) or stale (requiring origin validation to freshen, unless a disconnected cache is permitted to serve stale content).[1][7] Freshness uses non-negative `delta-seconds` values capped at `2147483648` (2^31, over 68 years) to prevent integer overflow.[1] Shared caches report elapsed storage time with the `Age` header; for example, a response carrying `Cache-Control: max-age=604800` (one week) stored by a shared cache for one day is served with `Age: 86400`, leaving 518,400 seconds of remaining freshness for downstream clients.[7] When `Cache-Control` is omitted, heuristic caching may reuse responses with a `Last-Modified` header for roughly 10% of the elapsed time since last modification.[7] Because base HTTP caching defines no mechanism for explicit deletion, managed caches such as CDNs provide out-of-band purging via dashboards, API calls, or restarts, and can execute custom caching logic such as Varnish Configuration Language (VCL) rules.[7]

| Header or directive | Scope | Function in HTTP and CDN caching |
| --- | --- | --- |
| `Cache-Control: max-age` | Private and shared caches | Sets freshness lifetime in seconds from response generation.[1][7] |
| `Cache-Control: s-maxage` | Shared caches | Sets freshness lifetime specifically for shared caches.[1][2] |
| `Cache-Control: private` | Private caches | Restricts personalized response storage to single-user caches.[1][7] |
| `Cache-Control: no-store` | All standard caches | Prevents caches from storing the response.[1] |
| `Cache-Control: no-cache` | All standard caches | Requires origin validation before reusing a stored response.[1][2] |
| `Age` | Shared caches | Reports seconds elapsed since the response was generated.[1][7] |
| `Expires` | Legacy HTTP/1.0 and HTTP/1.1 | Specifies cache expiration as an explicit timestamp.[1][7] |
| `Vary` | Cache key construction | Lists request headers incorporated into the cache key for content negotiation.[1] |

## Targeted HTTP cache control and CDN-Cache-Control (RFC 9213)

Content delivery network deployments often sit inside multi-layer caching topologies alongside origin-server caches, origin-network caches, and browser caches, creating a need to direct different caching policies to each class of cache.[2] While `Cache-Control` includes `s-maxage` for shared caches, it lacks consistent targeting across other directives such as `stale-while-revalidate`.[2] Earlier CDN implementations relied on vendor-specific headers such as `Surrogate-Control`, resulting in low interoperability across providers.[2][7]

In June 2022, the IETF published RFC 9213 (Standards Track), Targeted HTTP Cache Control, authored by S. Ludin (Akamai), M. Nottingham (Fastly), and Y. Wu ([Cloudflare](https://mimirwiki.com/wiki/cloudflare)).[2] RFC 9213 establishes a general convention for Targeted Cache-Control HTTP response headers and defines `CDN-Cache-Control` specifically for CDN caches.[2] Publishers with an invalidation relationship with their CDN can assign longer lifetimes in `CDN-Cache-Control` while retaining shorter lifetimes in `Cache-Control` for browsers and other intermediaries.[2]

Targeted cache-control headers are defined as HTTP Dictionary Structured Fields in which each dictionary member is an HTTP cache response directive (including extension directives), with values mapped to Structured Fields Boolean, String, Token, Integer, or Decimal types.[2] Because error handling differs from `Cache-Control`, implementations use a Structured Fields parser for targeted fields and ignore any field that is empty or produces a parsing error, falling back to other cache-control mechanisms.[2]

Each cache implementing RFC 9213 maintains an ordered target list of header names from highest to lowest priority, such as `[ExampleCDN-Cache-Control, CDN-Cache-Control]`.[2] For each received response, the cache selects the first valid, non-empty field on its target list to govern caching behavior and ignores `Cache-Control` and `Expires` on that response.[2] Targeted fields absent from a cache's target list must be passed through without altering that cache's behavior.[2] Supporting caches must implement five directives inside targeted fields: `max-age`, `must-revalidate`, `no-store`, `no-cache`, and `private`.[2] Precedence matches `Cache-Control`, so `no-store` and `no-cache` make `max-age` inoperative, and unrecognized extension directives are ignored.[2]

## BGP anycast routing for content delivery networks (RFC 4786)

Content delivery network infrastructures and other distributed Internet services use anycast routing, documented in IETF Best Current Practice RFC 4786 (BCP 126, December 2006) by J. Abley (Afilias Canada) and K. Lindqvist (Netnod Internet Exchange), to route client requests to one of several autonomous server sites sharing a single IP address.[5] To deploy anycast, an operator associates a stable Service Address (IPv4 or IPv6) with two or more discrete Anycast Nodes and advertises reachability to that address inside a routing system.[5]

When a client sends packets to an anycast Service Address, the routing system directs datagrams to one of the available nodes based on network topology and the origin point of the request.[5] The topological region of a network whose packets reach a particular node is termed its catchment.[5] RFC 4786 distinguishes two deployment scopes: local-scope anycast, which propagates routes through an Interior Gateway Protocol (IGP) so a node is visible only within a subset of the routing system, and global-scope anycast, which advertises reachability across the global Internet using the Border Gateway Protocol (BGP, RFC 4271).[5] Anycast operates without requiring server referrals or round-robin DNS, though applications may combine anycast with name-based distribution when needed.[5]

RFC 4786 documents several operational constraints inherent to anycast service distribution.[5]

- Transaction state and longevity: Anycast imposes constraints on long-lived transactions, server-side transaction state, and cross-node data synchronization.[5]
- Uneven load distribution: Fine-grained load balancing across anycast nodes is difficult to achieve because routing topology dictates catchment size, leaving request and traffic loads generally unbalanced across nodes even though anycast supports reliability and coarse-grained scaling.[5]
- Availability monitoring: Measuring availability is more complex under anycast because observed reachability varies by client network location, and the client population served by each node is neither static nor reliably deterministic.[5]

## Content delivery network interconnection standards (RFC 6707 and RFC 7336)

Content Delivery Network Interconnection (CDNI) enables standalone content delivery networks to interoperate so that one CDN can deliver content to end users on behalf of another CDN.[3] Growing video and multimedia traffic prompted commercial CDN operators to expand capacity and led many Network Service Providers (NSPs) to deploy their own CDNs.[3] Because a single CDN may lack geographic presence or sufficient resources close to every end user's attachment network, interconnecting separate CDNs pools footprints and capacity for end-to-end delivery from Content Service Providers (CSPs) to end users.[3]

The IETF defined this problem space in RFC 6707 (Informational, September 2012, by B. Niven-Jenkins, F. Le Faucheur, and N. Bitar) and established the overall architecture in RFC 7336 (Informational, August 2014, by L. Peterson, B. Davie, and R. van Brandenburg), which together obsolete RFC 3466.[3][4] In the CDNI model, a CSP contracts with an authoritative or upstream CDN (`uCDN`), which may serve requests itself or delegate delivery to one or more downstream CDNs (`dCDN`), such as an NSP-operated CDN; the final downstream CDN that serves the end user is the Delivering CDN.[3][4]

During an interconnected delivery flow, a user agent first contacts the upstream CDN, which can redirect the request via DNS redirection or HTTP redirection to a downstream CDN closer to the user.[3][4] RFC 7336 distinguishes iterative CDNI request redirection (where the upstream CDN redirects the client to the downstream CDN's request routing system based on local logic) from recursive CDNI request redirection (where the upstream CDN queries the downstream CDN's redirection interface first and incorporates that answer, potentially redirecting the client directly to a downstream surrogate).[4] If the downstream CDN lacks the requested item, it acquires the object from the upstream CDN, which in turn acquires it from the CSP when necessary.[3] CDNI rules and metadata apply to a `CDN-Domain` (an FQDN representing a content set), while a `Distinguished CDN-Domain` is allocated strictly for inter-CDN acquisition or redirection and never appears in client requests.[4]

| CDNI interface | Operation timing | Role defined in RFC 6707 and RFC 7336 |
| --- | --- | --- |
| CDNI Control Interface | Asynchronous | Coordinates administrative actions and includes the Trigger Interface to pre-position, revalidate, and purge metadata and content upon CSP actions.[3][4] |
| CDNI Request Routing Interface | Synchronous and asynchronous | Handles DNS or HTTP request redirection between upstream and downstream CDNs and exchanges dynamic footprint advertisements.[3][4] |
| CDNI Metadata Interface | Synchronous or asynchronous | Exchanges distribution metadata and delivery policies scoped to CDN-Domains across interconnected CDNs.[3][4] |
| CDNI Logging Interface | Asynchronous | Exchanges delivery logging records between peer CDNs for accounting and operational visibility.[3][4] |

## Content delivery network limitations, staleness, and security risks

Content delivery network deployments carry operational and security trade-offs involving cache staleness, shared-cache privacy, third-party outages, and asset integrity.[1][2][6][7]

Because HTTP uses a single end-to-end freshness model, configuring longer freshness lifetimes on a CDN than on downstream caches can reduce downstream cache efficiency.[2] RFC 9213 illustrates this interaction with a response served with `Age: 1800`, `Cache-Control: max-age=600`, and `CDN-Cache-Control: max-age=3600`: after 30 minutes, the object remains fresh for the CDN cache while appearing already stale to downstream caches governed by the 600-second limit.[2] Additionally, a disconnected cache that cannot reach an origin server may serve stale responses under allowed conditions.[1]

Depending on an external CDN introduces a third-party availability dependency.[6] MDN Web Docs notes that if a third-party CDN suffers an outage, is blocked in a region, or permanently shuts down, websites relying on it malfunction.[6] Loading third-party libraries such as Bootstrap or jQuery from an external CDN domain can also degrade performance in some scenarios: browsers must perform extra DNS lookups and connection setup to the third-party host, and modern browsers partition HTTP caches by origin (using double keying with the referring site's identity to mitigate privacy and timing-attack risks), so the same third-party library must still be downloaded separately for each site.[1][6]

Shared CDN caches also present security and data-isolation risks.[1][6][7] Compromising a third-party CDN allows attackers to serve malicious content to visitors of dependent sites, making client-side safeguards such as Subresource Integrity (SRI) necessary for third-party static assets.[6] Storing personalized responses in a shared cache without marking them `Cache-Control: private` can expose one user's data to other users, and the presence of a cookie alone does not mark an HTTP response as private.[7] RFC 9111 further identifies cache poisoning, timing attacks, and caching of sensitive information as core security considerations for HTTP caching systems.[1]

## Frequently asked questions

### What is a content delivery network (CDN)?

A content delivery network (CDN) is a geographically distributed group of servers that stores copies of web content and fulfills requests from edge locations close to end users. Acting as a managed shared HTTP cache between clients and origin servers, a CDN lowers latency, reduces origin server load, and improves availability. [6][7][8]

### How does CDN-Cache-Control differ from standard Cache-Control?

Standard Cache-Control directives defined in RFC 9111 apply broadly across browsers and shared caches, with limited per-layer targeting. CDN-Cache-Control, standardized in RFC 9213 in June 2022, is a Dictionary Structured Field targeted specifically at CDN caches so publishers can set separate CDN caching policies while the CDN ignores Cache-Control and Expires for that response. [2][7]

### Why do CDNs use BGP anycast routing?

Global-scope BGP anycast, documented in RFC 4786 (BCP 126), advertises the same IP service address from multiple discrete locations so Internet routing delivers client packets to a topologically near node. It supports service reliability and coarse-grained scaling without requiring round-robin DNS referrals, although traffic load across nodes tends to remain uneven. [5]

### What is CDN Interconnection (CDNI)?

CDN Interconnection (CDNI), outlined in RFC 6707 and framed in RFC 7336, is a relationship between separate CDNs that lets an authoritative upstream CDN delegate content delivery to a downstream CDN closer to end users. It coordinates delivery across four interface areas: Control (including a Trigger Interface), Request Routing, Metadata, and Logging. [3][4]

### Can a CDN expose personalized user data or serve stale content?

Yes. Because a CDN operates as a shared cache, storing personalized responses without the Cache-Control: private directive can expose one user's content to other users, and cookies alone do not mark a response as private. In addition, giving a CDN a longer freshness lifetime than downstream caches can cause responses to arrive already stale at downstream caches. [2][7]

### What risks come with loading static libraries from a third-party CDN?

MDN Web Docs lists three downsides compared to self-hosting static assets: a third-party outage, regional block, or shutdown can break dependent websites; a compromised CDN can serve malicious files unless mitigated with controls such as Subresource Integrity (SRI); and separate origins add DNS lookup and connection overhead while browser cache partitioning prevents cross-site asset reuse. [6]

## Quotable sentences

- The IETF published RFC 9111 (STD 98) in June 2022 as the Standards Track HTTP Caching specification, obsoleting RFC 7234. [1]
- RFC 9213, published in June 2022 by authors from Akamai, Fastly, and Cloudflare, defines the CDN-Cache-Control HTTP response header for CDN caches. [2]
- Under RFC 9213, caches implementing a targeted cache-control field must support the max-age, must-revalidate, no-store, no-cache, and private directives. [2]
- RFC 4786 (BCP 126), published in December 2006, documents operational practices for distributing services across multiple locations using IPv4 and IPv6 anycast over IGP or BGP. [5]
- RFC 6707 (September 2012) and RFC 7336 (August 2014) define the problem statement and framework for Content Distribution Network Interconnection (CDNI), obsoleting RFC 3466. [3][4]
- Modern browsers partition HTTP caches by origin for privacy reasons, requiring separate downloads of third-party CDN libraries on each website. [6]
- Managed caches such as CDNs allow explicit deletion of stored responses through dashboards, API calls, or restarts, a capability outside the base HTTP caching specification. [7]
- As of 2026-11-23, Amazon CloudFront caches objects at edge locations for 24 hours by default, with a 0-second minimum expiration time and no fixed maximum. [8]

## Timeline

- 2006-12: The IETF publishes RFC 4786 (BCP 126), Operation of Anycast Services, documenting local-scope IGP and global-scope BGP anycast practices. [5]
- 2012-09: The IETF publishes RFC 6707, Content Distribution Network Interconnection (CDNI) Problem Statement, scoping four CDNI interfaces. [3]
- 2014-08: The IETF publishes RFC 7336, Framework for Content Distribution Network Interconnection (CDNI), obsoleting RFC 3466 in combination with RFC 6707. [4]
- 2022-06: The IETF publishes RFC 9111 (STD 98), HTTP Caching, obsoleting RFC 7234, alongside RFC 9213, Targeted HTTP Cache Control, standardizing the CDN-Cache-Control response header. [1][2]

## Sources

1. RFC 9111: HTTP Caching. Internet Engineering Task Force (IETF). published 2022-06. https://www.rfc-editor.org/rfc/rfc9111.txt (checked 2026-11-23; tier 1: government or public registry)
2. RFC 9213: Targeted HTTP Cache Control. Internet Engineering Task Force (IETF). published 2022-06. https://www.rfc-editor.org/rfc/rfc9213.txt (checked 2026-11-23; tier 1: government or public registry)
3. RFC 6707: Content Distribution Network Interconnection (CDNI) Problem Statement. Internet Engineering Task Force (IETF). published 2012-09. https://www.rfc-editor.org/rfc/rfc6707.txt (checked 2026-11-23; tier 1: government or public registry)
4. RFC 7336: Framework for Content Distribution Network Interconnection (CDNI). Internet Engineering Task Force (IETF). published 2014-08. https://www.rfc-editor.org/rfc/rfc7336.txt (checked 2026-11-23; tier 1: government or public registry)
5. RFC 4786: Operation of Anycast Services. Internet Engineering Task Force (IETF). published 2006-12. https://www.rfc-editor.org/rfc/rfc4786.txt (checked 2026-11-23; tier 1: government or public registry)
6. CDN - Glossary | MDN. MDN Web Docs. published 2025-07-11. https://developer.mozilla.org/en-US/docs/Glossary/CDN (checked 2026-11-23; tier 3: official site)
7. HTTP caching - HTTP | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching (checked 2026-11-23; tier 3: official site)
8. What is Amazon CloudFront? - Amazon CloudFront. Amazon Web Services. https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "Content Delivery Network." Version d0585d78, 2026-11-23. https://mimirwiki.com/wiki/content-delivery-network
