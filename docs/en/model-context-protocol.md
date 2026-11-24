---
title: "Model Context Protocol"
subtitle: "Open protocol that connects AI applications to external tools and data"
canonical_url: https://mimirwiki.com/wiki/model-context-protocol
language: en
page_class: anchor
revision_sha256: 221455ee03b7b587d96839c427e1953bc3b9e1e6967f867dea77878e660302e2
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/model-context-protocol.md
  txt: https://mimirwiki.com/wiki/model-context-protocol.txt
  json: https://mimirwiki.com/wiki/model-context-protocol.json
  jsonld: https://mimirwiki.com/wiki/model-context-protocol.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/model-context-protocol
  ja: https://mimirwiki.com/ja/wiki/model-context-protocol
  zh: https://mimirwiki.com/zh/wiki/model-context-protocol
---

# Model Context Protocol

> The Model Context Protocol (MCP) is an open protocol that lets AI applications connect to external tools and data sources through one common interface. It uses JSON-RPC 2.0 messages over stdio or Streamable HTTP. Anthropic released MCP on 2024-11-25, and the Linux Foundation's Agentic AI Foundation has hosted it since December 2025. The current version is 2026-07-28.

The Model Context Protocol (MCP) is an open protocol that standardizes how applications built on large language models connect to external data sources and tools. MCP messages follow JSON-RPC 2.0 and travel between hosts, clients and servers over two standard transports, stdio and Streamable HTTP. Anthropic released the protocol as open source on 2024-11-25 and contributed it to the Agentic AI Foundation, formed under the Linux Foundation, in an announcement dated 2025-12-09. As of 2026-11-21 the current protocol version is 2026-07-28, the revision that made the protocol stateless.

**Also known as:** MCP

## Key facts

- **First released:** 2024-11-25, by Anthropic [8]
- **Current protocol version:** 2026-07-28 (as of 2026-11-21) [2]
- **Message format:** JSON-RPC 2.0 [1]
- **Standard transports:** stdio and Streamable HTTP [4]
- **Host foundation:** Agentic AI Foundation (Linux Foundation), announced 2025-12-09 [9]

## Basic facts

- **Type:** Open protocol for connecting LLM applications to external data sources and tools [1]
- **Original developer:** Anthropic [8]
- **First released:** 2024-11-25 [8]
- **Current version:** 2026-07-28 (as of 2026-11-21) [2]
- **Version format:** Date string, YYYY-MM-DD [2]
- **Message format:** JSON-RPC 2.0, UTF-8 encoded [4]
- **Standard transports:** stdio, Streamable HTTP [4]
- **Server features:** Resources, prompts, tools [1]
- **Authorization:** Optional; based on OAuth 2.1 for HTTP-based transports [5]
- **Legal entity:** Model Context Protocol a Series of LF Projects, LLC [6]
- **License:** Apache License 2.0 (code and specification); CC BY 4.0 (other documentation) [6]
- **Official SDKs:** TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP, Kotlin (as of 2026-11-21) [7]

## What the Model Context Protocol is

The Model Context Protocol (MCP) is an open protocol that connects applications built on large language models (LLMs) to external data sources and tools.[1] Its specification names three purposes: sharing contextual information with language models, exposing tools and capabilities to AI systems, and building composable integrations and workflows.[1] The specification cites the [Language Server Protocol](https://mimirwiki.com/wiki/language-server-protocol) as an inspiration. That protocol standardized programming-language support across development tools, and MCP applies the same idea to adding context and tools to AI applications.[1]

MCP assigns three roles. A host is the LLM application that initiates connections, a client is a connector inside the host, and a server is a service that provides context and capabilities.[1] Servers can offer resources (context and data), prompts (templated messages and workflows) and tools (functions that a model can execute). Clients can offer elicitation, through which a server asks the user for more information.[1]

[Anthropic](https://mimirwiki.com/wiki/anthropic) announced MCP as an open-source standard on 2024-11-25. The release consisted of the specification and software development kits (SDKs), local MCP server support in the Claude Desktop apps, and an open-source repository of MCP servers.[8] The announcement credited David Soria Parra and Justin Spahr-Summers with creating the protocol at Anthropic.[8]

## Model Context Protocol message format and architecture

The Model Context Protocol encodes every message as [JSON-RPC](https://mimirwiki.com/wiki/json-rpc) 2.0, and messages must be UTF-8 encoded.[1][4] Clients send requests and notifications, and servers reply with responses and notifications. In the current revision no other direction exists: servers do not initiate JSON-RPC requests and clients do not send JSON-RPC responses.[4]

Since revision 2026-07-28 MCP has been stateless at the protocol level. The `initialize` handshake of earlier revisions was removed, and every request now carries its protocol version and the client's capabilities in a `_meta` field.[3] Servers must implement a `server/discover` method that reports their supported protocol versions, capabilities and identity. Clients may call it first, but they are not required to.[2][3]

When a server needs something from the client side in the middle of a call, it returns a result marked `input_required` that lists the information it needs, and the client retries the original request with the answers attached. The specification calls this pattern Multi Round-Trip Requests (MRTR). It replaces the server-initiated requests of earlier revisions.[3] Long-lived change notifications, for example a changed tool list, are delivered on a stream that the client opens with a `subscriptions/listen` request.[3]

## Model Context Protocol transports and authorization

The Model Context Protocol defines two standard transports, stdio and Streamable HTTP. With stdio, the client launches the server as a subprocess and both sides exchange newline-delimited messages over the standard streams. With Streamable HTTP, each message is an HTTP POST to a single MCP endpoint, and the reply arrives either as one JSON object or as a Server-Sent Events (SSE) stream scoped to that request.[4] Protocol semantics are identical on both. Custom transports are allowed if they keep the JSON-RPC message format, the message patterns and the per-request metadata model.[4]

On Streamable HTTP, selected metadata is mirrored into HTTP headers so that intermediaries can route requests without parsing the body.[4] The protocol version is carried in the `MCP-Protocol-Version` header, and revision 2026-07-28 requires `Mcp-Method` and `Mcp-Name` headers on POST requests.[2][3]

Authorization is optional in MCP. For HTTP-based transports the specification builds on [OAuth](https://mimirwiki.com/wiki/oauth) 2.1: a protected MCP server acts as an OAuth 2.1 resource server, the MCP client acts as an OAuth 2.1 client, and servers must publish OAuth 2.0 Protected Resource Metadata (RFC 9728) so that clients can locate the authorization server.[5] Implementations that use stdio are directed not to follow this flow and to read credentials from the environment instead.[5]

## Model Context Protocol versions and the 2026-07-28 revision

Model Context Protocol versions are date strings in the form `YYYY-MM-DD`. Each identifier marks the last date on which backwards-incompatible changes were made, and backwards-compatible updates do not change it.[2] As of 2026-11-21 the current version is 2026-07-28.[2] The releases page of the specification repository on GitHub lists the revisions 2024-11-05, 2025-03-26, 2025-06-18, 2025-11-25 and 2026-07-28.[10] Clients and servers may support several versions at once, and a server that does not support the requested version returns an `UnsupportedProtocolVersionError` that lists the versions it supports.[2]

The maintainers' release post for revision 2026-07-28 describes it as a move from a bidirectional stateful protocol to a stateless request and response protocol, so that any server instance behind a load balancer can handle any request.[11] The changelog lists the following main changes.[3]

| Area | Change in revision 2026-07-28 |
| --- | --- |
| Sessions | Protocol-level sessions and the `Mcp-Session-Id` header removed |
| Handshake | `initialize` handshake removed; version and capabilities sent with every request |
| Discovery | `server/discover` added and required for servers |
| Server-to-client input | Multi Round-Trip Requests replace server-initiated requests |
| Notifications | `subscriptions/listen` replaces the HTTP GET endpoint and the resource subscribe methods |
| Tasks | Moved from the experimental core into the `io.modelcontextprotocol/tasks` extension |
| Deprecated | Roots, Sampling, Logging, the HTTP+SSE transport and OAuth Dynamic Client Registration |

Deprecated features remain in the specification for at least twelve months before they become eligible for removal, apart from an expedited-removal exception of at least ninety days.[2] On 2026-11-11 the lead maintainers announced a six-month release schedule, with specification releases generally planned for the last Tuesday of March and September. The next release is targeted for 2027-03-30 and is expected to carry the version identifier 2027-03-30.[12]

## Model Context Protocol governance and licensing

The Model Context Protocol is hosted by the [Linux Foundation](https://mimirwiki.com/wiki/linux-foundation). On 2025-12-09 the Linux Foundation announced the formation of the [Agentic AI Foundation](https://mimirwiki.com/wiki/agentic-ai-foundation) (AAIF), with three founding project contributions: MCP from Anthropic, goose from Block and AGENTS.md from OpenAI.[9] The foundation's platinum members at launch were Amazon Web Services, Anthropic, Block, Bloomberg, [Cloudflare](https://mimirwiki.com/wiki/cloudflare), Google, Microsoft and OpenAI.[9] The project's governance document gives its legal form as Model Context Protocol a Series of LF Projects, LLC.[6]

Technical decisions in MCP follow a maintainer hierarchy. Contributors file issues and pull requests, Maintainers steward components such as SDKs and working groups, Core Maintainers steer the specification, and Lead Maintainers hold final authority.[6] Membership belongs to individuals, and no seats are reserved for companies. As of 2026-11-21 the governance page lists David Soria Parra and Den Delimarsky as Lead Maintainers.[6] Changes to the specification are proposed as Specification Enhancement Proposals (SEPs).[6]

Code and specification contributions are made under the Apache License 2.0. Documentation other than the specification is published under the Creative Commons Attribution 4.0 International license.[6]

## Model Context Protocol SDKs, adoption and limits

The Model Context Protocol project maintains official SDKs in ten programming languages. As of 2026-11-21 its SDK page classifies TypeScript, Python, C#, Go, Rust and Ruby as Tier 1, Java as Tier 2, and Swift, PHP and Kotlin as Tier 3. Tiers reflect feature completeness, protocol support and maintenance commitment.[7] Each SDK adopts new protocol revisions on its own schedule. On the day revision 2026-07-28 was released, the TypeScript, Python, Go and C# SDKs supported it.[7][11]

Published adoption figures for MCP come from the project and its host foundation. The Linux Foundation stated on 2025-12-09 that more than 10,000 MCP servers had been published and that Claude, Cursor, Microsoft Copilot, Gemini, VS Code and ChatGPT had adopted the protocol.[9] The maintainers reported on 2026-07-28 that the Tier 1 SDKs were downloaded close to half a billion times a month and that the TypeScript and Python SDKs had each passed 1 billion total downloads.[11]

MCP is a protocol specification, and several things lie outside what it guarantees. The specification states that the protocol cannot enforce its own consent and safety principles, so it asks hosts to obtain explicit user consent before invoking any tool and to treat tool descriptions as untrusted unless they come from a trusted server.[1] Authorization is optional, and extensions such as Tasks and MCP Apps are opt-in additions outside the core protocol.[1][5] Statelessness applies to the protocol, not to applications: a server that needs state across calls can issue an explicit handle that is passed back as an ordinary tool argument.[3]

## Frequently asked questions

### What is the current version of the Model Context Protocol?

As of 2026-11-21 the current protocol version is 2026-07-28. Versions are date strings in the form YYYY-MM-DD, and the identifier changes only when backwards-incompatible changes are made. [2]

### Who governs the Model Context Protocol?

The project is hosted by the Linux Foundation as Model Context Protocol a Series of LF Projects, LLC, and Anthropic contributed it to the Agentic AI Foundation announced on 2025-12-09. Technical decisions rest with individual maintainers, and Lead Maintainers hold final authority. [6][9]

### What message format and transports does the Model Context Protocol use?

MCP messages are JSON-RPC 2.0, encoded as UTF-8. The two standard transports are stdio, for a server launched as a local subprocess, and Streamable HTTP, in which each message is an HTTP POST to a single endpoint. [1][4]

### Does the Model Context Protocol require OAuth?

No. Authorization is optional in MCP. When it is used on HTTP-based transports the specification bases it on OAuth 2.1, while stdio implementations take credentials from the environment. [5]

### What changed in Model Context Protocol revision 2026-07-28?

The revision removed the initialize handshake and protocol-level sessions, so each request is self-contained. It added the server/discover method and Multi Round-Trip Requests, and it deprecated Roots, Sampling and Logging. [3]

### Which languages have official Model Context Protocol SDKs?

As of 2026-11-21 the project lists official SDKs for TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP and Kotlin. The first six are classified as Tier 1. [7]

## Quotable sentences

- The Model Context Protocol uses JSON-RPC 2.0 messages. [1]
- The current Model Context Protocol version is 2026-07-28 as of 2026-11-21. [2]
- Anthropic released the Model Context Protocol as open source on 2024-11-25. [8]
- The Linux Foundation announced on 2025-12-09 that Anthropic had contributed the Model Context Protocol to the newly formed Agentic AI Foundation. [9]
- The Model Context Protocol defines two standard transports, stdio and Streamable HTTP. [4]
- Revision 2026-07-28 of the Model Context Protocol removed the initialize handshake and protocol-level sessions, making the protocol stateless. [3]
- Authorization is optional in the Model Context Protocol and is based on OAuth 2.1 for HTTP-based transports. [5]
- The next Model Context Protocol specification release is targeted for 2027-03-30, according to the maintainers' announcement of 2026-11-11. [12]

## Timeline

- 2024-11-25: Anthropic releases the Model Context Protocol as open source. [8]
- 2025-03-26: Revision 2025-03-26 is released; the HTTP+SSE transport is deprecated from this revision. [10][3]
- 2025-06-18: Revision 2025-06-18 is released. [10]
- 2025-11-25: Revision 2025-11-25 is released, with experimental support for tasks. [10][12]
- 2025-12-09: The Linux Foundation announces the Agentic AI Foundation, with the Model Context Protocol contributed by Anthropic. [9]
- 2026-07-28: Revision 2026-07-28 is released and makes the protocol stateless. [11][3]
- 2026-11-11: The lead maintainers announce a six-month release schedule and target 2027-03-30 for the next release. [12]

## Sources

1. Specification - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28 (checked 2026-11-21; tier 3: official site)
2. Versioning - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/versioning (checked 2026-11-21; tier 3: official site)
3. Key Changes - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/changelog (checked 2026-11-21; tier 3: official site)
4. Overview - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports (checked 2026-11-21; tier 3: official site)
5. Authorization - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (checked 2026-11-21; tier 3: official site)
6. Governance and Stewardship - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/community/governance (checked 2026-11-21; tier 3: official site)
7. SDKs - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/docs/sdk (checked 2026-11-21; tier 3: official site)
8. Introducing the Model Context Protocol. Anthropic. published 2024-11-25. https://www.anthropic.com/news/model-context-protocol (checked 2026-11-21; tier 3: official site)
9. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. published 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (checked 2026-11-21; tier 3: official site)
10. Releases · modelcontextprotocol/modelcontextprotocol · GitHub. Model Context Protocol project (GitHub). https://github.com/modelcontextprotocol/modelcontextprotocol/releases (checked 2026-11-21; tier 3: official site)
11. The 2026-07-28 Specification. Model Context Protocol Blog. published 2026-07-28. https://blog.modelcontextprotocol.io/posts/2026-07-28/ (checked 2026-11-21; tier 3: official site)
12. A More Predictable Release Cycle for MCP. Model Context Protocol Blog. published 2026-11-11. https://blog.modelcontextprotocol.io/posts/mcp-release-cycle/ (checked 2026-11-21; tier 3: official site)

## Cite this page

Mimirwiki. "Model Context Protocol." Version 221455ee, 2026-11-21. https://mimirwiki.com/wiki/model-context-protocol
