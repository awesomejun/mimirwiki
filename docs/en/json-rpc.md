---
title: "JSON-RPC"
subtitle: "Stateless, transport-agnostic remote procedure call protocol encoded in JSON"
canonical_url: https://mimirwiki.com/wiki/json-rpc
language: en
page_class: anchor
revision_sha256: 63336d54381a902bfae9467f5c1a6b4590504ac993070a3274d4e186afbb5b2c
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/wiki/json-rpc.md
  txt: https://mimirwiki.com/wiki/json-rpc.txt
  json: https://mimirwiki.com/wiki/json-rpc.json
  jsonld: https://mimirwiki.com/wiki/json-rpc.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/json-rpc
---

# JSON-RPC

> JSON-RPC is a stateless, lightweight remote procedure call (RPC) protocol that encodes requests, responses, notifications, errors, and batch calls in JSON. Published by the JSON-RPC Working Group in 2010 and updated in 2013, version 2.0 is transport-agnostic and works over HTTP, sockets, or within a single process. MCP, LSP, and Ethereum clients use it for message exchange.

JSON-RPC is a stateless, lightweight remote procedure call (RPC) protocol that encodes messages in JavaScript Object Notation (JSON). The JSON-RPC Working Group published version 2.0 on 2010-03-26 (based on a 2009-05-24 draft) and last updated the specification text on 2013-01-04; as of 2026-11-23, JSON-RPC 2.0 remains the current version. The JSON-RPC specification defines request, response, notification, error, and batch data structures along with their processing rules, while leaving the choice of transport layer to implementations. JSON-RPC serves as the base message format in the Model Context Protocol (MCP), the Language Server Protocol (LSP), Ethereum execution client APIs, and the Open vSwitch Database Management Protocol (OVSDB).

**Also known as:** JSON-RPC 2.0, JSON-RPC 1.0, JSON Remote Procedure Call

## Key facts

- **Current version:** 2.0 (originated 2010-03-26, updated 2013-01-04) (as of 2026-11-23) [1]
- **First version:** 1.0 (2005) [2]
- **Author:** JSON-RPC Working Group [1]
- **Data format:** JSON (RFC 4627) [1]
- **Transport:** Transport-agnostic (in-process, sockets, HTTP, or other message channels) [1]

## Basic facts

- **Type:** Stateless, lightweight remote procedure call (RPC) protocol [1]
- **Author:** JSON-RPC Working Group [1]
- **First version:** JSON-RPC 1.0 (2005) [2]
- **Current version:** JSON-RPC 2.0 (originated 2010-03-26, updated 2013-01-04) (as of 2026-11-23) [1]
- **Data format:** JSON (four primitive types and two structured types) [1]
- **JSON standard:** RFC 8259 (December 2017; obsoletes RFC 7159 and RFC 4627) (as of 2026-11-23) [4]
- **Transport:** Transport-agnostic (in-process, sockets, HTTP, or other message passing) [1]
- **Message types:** Request, Response, Notification, Error, and Batch [1]
- **Reserved error codes:** -32768 to -32000 (pre-defined -32700, -32600 to -32603, server -32000 to -32099) [1]
- **Extension prefix:** rpc. (reserved for optional system extensions) [1]
- **Interface description:** OpenRPC Specification (version 1.4.x; discovery method rpc.discover) (as of 2026-11-23) [10]

## What JSON-RPC is

JSON-RPC is a stateless, lightweight remote procedure call (RPC) protocol that encodes method calls and replies as JavaScript Object Notation (JSON) data.[1] The JSON-RPC 2.0 specification defines a small set of data structures and rules for processing them, keeping the protocol independent of any particular network transport.[1] As of 2026-11-23, JSON-RPC 2.0 remains the current specification maintained by the JSON-RPC Working Group, having originated on 2010-03-26 from a 2009-05-24 draft and received its latest text update on 2013-01-04.[1]

JSON-RPC uses the JSON type system, which comprises four primitive types (String, Number, Boolean, and Null) and two structured types (Object and Array).[1][4] The JSON-RPC 2.0 text cites RFC 4627 as its JSON reference.[1] In December 2017, the Internet Engineering Task Force (IETF) published RFC 8259 to replace RFC 7159, which had previously obsoleted RFC 4627 and its original registration of the `application/json` media type.[4] RFC 8259 aligns the JSON grammar with ECMA-404 and notes that implementations producing only JSON objects or arrays as top-level texts remain interoperable across all conforming parsers, matching JSON-RPC's use of single objects and batch arrays.[1][4]

In JSON-RPC 2.0, the Client is the party that originates Request objects and handles Response objects, and the Server is the party that handles Request objects and originates Response objects.[1] A single implementation can fill both roles at the same time toward different peers or the same peer, while the specification leaves bidirectional session coordination to higher layers.[1] All member names matched between Client and Server are case-sensitive, and the specification treats the terms function, method, and procedure as interchangeable.[1]

## JSON-RPC 2.0 message structure

JSON-RPC 2.0 defines three core message forms: the Request object, the Notification, and the Response object.[1] Every conforming Request and Response object includes a `jsonrpc` member whose String value must be exactly `"2.0"`.[1]

A JSON-RPC 2.0 Request object invokes a remote method and contains up to four members.[1]

- `jsonrpc`: Required String specifying the protocol version, always `"2.0"`.
- `method`: Required String naming the procedure to invoke. Method names starting with `rpc.` (the letters `rpc` followed by a period, U+002E) are reserved for RPC-internal methods and optional system extensions.
- `params`: Optional Structured value holding arguments for the invocation. When included, parameters are supplied either by position as a JSON Array in server-expected order, or by name as a JSON Object whose member names match the server's expected parameter names with exact case sensitivity.
- `id`: Optional Client-established identifier that must be a String, Number, or Null when present. Using Null as a request `id` is discouraged because responses with an unknown `id` use Null and JSON-RPC 1.0 used a Null `id` for notifications; numeric `id` values should also omit fractional parts because binary floating-point formats cannot represent many decimal fractions exactly.

A JSON-RPC 2.0 Notification is a Request object that omits the `id` member.[1] Omitting `id` signals that the Client does not expect a reply, and the Server must not return a Response object for a Notification, including Notifications sent inside a batch.[1] Because no response is returned, Notifications are unconfirmable, and the Client receives no report if a Notification encounters errors such as invalid parameters or an internal error.[1]

For every Request object other than a Notification, a JSON-RPC 2.0 Server must reply with a single JSON Response object.[1] A Response object always includes `"jsonrpc": "2.0"` and an `id` member matching the Request object's `id`, or Null if the Server could not determine the `id` due to a parse error or invalid request.[1] Each Response object must include either a `result` member on success or an `error` member on failure, and both members must not appear together in the same Response object.[1]

## JSON-RPC 2.0 error object and reserved codes

JSON-RPC 2.0 reports method failures through a structured Error object placed in the Response object's `error` member.[1] The Error object contains two required members and one optional member: `code` (an integer identifying the error type), `message` (a short String description, preferably limited to one concise sentence), and an optional `data` member holding any server-defined primitive or structured value with additional error information.[1]

JSON-RPC 2.0 reserves the integer range from -32768 to -32000 inclusive for pre-defined protocol errors, using codes closely aligned with XML-RPC fault codes.[1] Unassigned codes within that range remain reserved for future use, while integers outside -32768 to -32000 are available for application-defined errors.[1]

| Code | Message | Meaning |
| --- | --- | --- |
| -32700 | Parse error | Invalid JSON was received by the server, or an error occurred while parsing the JSON text. |
| -32600 | Invalid Request | The JSON sent is not a valid Request object. |
| -32601 | Method not found | The requested method does not exist or is unavailable. |
| -32602 | Invalid params | The method parameters are invalid. |
| -32603 | Internal error | An internal JSON-RPC error occurred. |
| -32000 to -32099 | Server error | Reserved for implementation-defined server errors. |

Downstream protocols build on this error scheme while keeping the reserved range intact.[7] In the Language Server Protocol (LSP) 3.17 specification, the five core JSON-RPC error codes (-32700 and -32600 through -32603) are retained, the -32099 to -32000 range is marked as JSON-RPC reserved (retaining only legacy codes -32002 ServerNotInitialized and -32001 UnknownErrorCode for backwards compatibility), and protocol-specific errors such as -32803 (RequestFailed) and -32802 (ServerCancelled) are defined in a separate range starting at -32899.[7]

## JSON-RPC batch processing and transport independence

JSON-RPC 2.0 allows a Client to transmit multiple Request objects in a single message by placing them in a JSON Array, known as a Batch.[1] After processing all requests in the Batch, the Server returns a JSON Array containing one Response object for each non-notification Request object.[1] The Server may execute batched requests concurrently in any order and return Response objects in any order, so the Client matches responses to requests by the `id` member of each object.[1]

JSON-RPC 2.0 defines specific rules for batch error and notification edge cases.[1] If a batch payload is invalid JSON or an empty Array (`[]`), the Server returns a single Response object with error code -32700 (Parse error) or -32600 (Invalid Request) and `"id": null`.[1] If a non-empty Array contains invalid elements, the Server returns a Response Array containing an Invalid Request (-32600) error object for each invalid entry alongside responses for valid entries.[1] If every item in a Batch is a Notification, the Server must not return an empty Array and should return nothing at all.[1]

JSON-RPC 2.0 leaves message framing and transport bindings outside the core specification, allowing the same JSON structures to run within the same process, over sockets, over HTTP, or across other message-passing environments.[1] Earlier in the protocol's development, on 2008-01-15, Jeffrey Damick and the JSON-RPC Working Group published a historical "JSON-RPC over HTTP" extension draft targeting JSON-RPC 1.2.[3] That draft designated HTTP POST as the preferred method and also described HTTP GET with Base64-encoded and URL-encoded parameters (noting that older clients and proxies could fail on URI lengths over 255 bytes); it specified `Content-Type` and `Accept` headers of `application/json-rpc` (with `application/json` or `application/jsonrequest` permitted), required `Content-Length`, and mapped HTTP status codes to outcomes: 200 for successful requests, 204 for notifications, 400 for -32600, 404 for -32601, and 500 for -32700, -32602, -32603, and server errors (-32099 to -32000).[3] Adopting protocols define their own transport conventions: LSP frames UTF-8 JSON-RPC 2.0 payloads with HTTP-style ASCII `Content-Length` and optional `Content-Type` headers (defaulting to `application/vscode-jsonrpc; charset=utf-8`) separated by `\r\n\r\n`, while Ethereum execution nodes commonly accept HTTP POST requests with `Content-Type: application/json`.[7][8]

## JSON-RPC version history: 1.0 to 2.0

JSON-RPC 1.0 was published in 2005 as a peer-to-peer remote procedure call protocol in which two connected peers could invoke methods on each other over a byte stream (with TCP/IP sockets encouraged) or over multiple HTTP POST requests.[2] A JSON-RPC 1.0 Request object contained three properties: `method`, `params` (strictly a positional Array), and `id` (of any JSON type).[2] Notifications used an `id` value of `null`, and Response objects always contained both `result` and `error` properties, setting the unused property to `null`.[2] Version 1.0 also included a `__jsonclass__` property for class hinting so peers could instantiate typed objects beyond standard JSON types.[2]

JSON-RPC 2.0, originated on 2010-03-26 from a 2009-05-24 draft and updated on 2013-01-04, simplified the protocol into a stateless client-server message specification and introduced changes that break wire compatibility with version 1.0.[1] Implementations can distinguish the two versions because every JSON-RPC 2.0 Request and Response object carries `"jsonrpc": "2.0"`, whereas version 1.0 objects omit that member.[1]

| Feature | JSON-RPC 1.0 (2005) | JSON-RPC 2.0 (2010, updated 2013) |
| --- | --- | --- |
| Version identifier | Omitted | Required `"jsonrpc": "2.0"` member |
| Parameters (`params`) | Array only (positional) | Optional Array (positional) or Object (named) |
| Notification format | `"id": null` | `id` member omitted |
| Response `result` and `error` | Both present; unused field set to `null` | Mutually exclusive; only one may exist |
| Batch requests | Not defined | JSON Array of Request objects |
| Class hinting (`__jsonclass__`) | Defined in specification | Omitted from specification |
| Communication model | Peer-to-peer over stream or HTTP | Stateless Client and Server roles; transport-agnostic |

JSON-RPC 2.0 advises implementations to consider handling version 1.0 objects where practical, even without version 1.0's peer-to-peer and class-hinting features.[1] JSON-RPC 1.0 continued to appear in networking specifications after 2.0 was published: in December 2013, the IETF issued Informational RFC 7047 defining the Open vSwitch Database Management Protocol (OVSDB), which uses JSON-RPC 1.0 over JSON as its wire protocol for configuring virtual switch bridges, ports, tunnel interfaces, queues, and quality-of-service policies.[5]

## JSON-RPC adoption and OpenRPC tooling

JSON-RPC 2.0 serves as the message layer for several major developer, AI, and blockchain protocols.[6][7][8] The [Model Context Protocol](https://mimirwiki.com/wiki/model-context-protocol) (MCP), whose specification version 2026-07-28 is the latest release as of 2026-11-23, uses JSON-RPC 2.0 messages to connect LLM host applications, internal clients, and servers that expose resources, prompts, tools, and client elicitation flows.[6] MCP draws inspiration from the Language Server Protocol (LSP), maintained by Microsoft (with specification version 3.17 archived, 3.18 listed as current, and 3.19 as upcoming as of 2026-11-23), which carries JSON-RPC 2.0 messages between code editors and language servers for operations such as completion, diagnostics, formatting, and symbol navigation.[6][7]

JSON-RPC 2.0 is also the standard client interface for Ethereum execution nodes.[8][9] Every Ethereum execution client exposes a uniform JSON-RPC API so software applications can query blockchain state, retrieve historical blocks and transaction receipts, and submit transactions across interchangeable node implementations.[8][9] Ethereum documentation organizes core methods into gossip (`eth_blockNumber`, `eth_sendRawTransaction`), state (`eth_getBalance`, `eth_getStorageAt`, `eth_getTransactionCount`, `eth_getCode`, `eth_call`, `eth_estimateGas`), and history (`eth_getBlockByNumber`, `eth_getTransactionReceipt`), encoding integer quantities as compact `"0x"`-prefixed hexadecimal strings (`"0x0"` for zero) and unformatted byte arrays as even-length `"0x"`-prefixed hex strings.[8] The canonical Ethereum execution API specification is maintained under the CC0-1.0 license in the `ethereum/execution-apis` GitHub repository and validated against clients with `speccheck` and the `hive` simulator's `rpc-compat` test suite.[9] Ethereum consensus clients expose a separate Beacon API, and consensus and execution clients exchange internal node messages through the Engine API.[8]

To describe and validate JSON-RPC 2.0 interfaces in a machine-readable form, the OpenRPC Specification (version 1.4.x as of 2026-11-23, Apache-2.0 license) defines a language-agnostic JSON interface description format exclusively for JSON-RPC 2.0 APIs.[10] An OpenRPC document, conventionally named `openrpc.json`, requires `openrpc`, `info`, and `methods` fields, uses Draft 07 JSON Schema for parameter and result definitions, and supports GitHub Flavored [Markdown](https://mimirwiki.com/wiki/markdown) in description fields.[10] OpenRPC also defines a service discovery method named `rpc.discover` using JSON-RPC 2.0's reserved `rpc.` extension prefix to return an API's OpenRPC schema at runtime.[1][10] Projects including `ethereum/execution-apis` author their JSON-RPC methods in OpenRPC YAML files and compile them into a validated `openrpc.json` document.[9]

## Frequently asked questions

### What is JSON-RPC?

JSON-RPC is a stateless, lightweight remote procedure call (RPC) protocol that encodes requests, responses, notifications, and error objects in JSON. Version 2.0 was originated by the JSON-RPC Working Group on 2010-03-26 and last updated on 2013-01-04. [1]

### How does a JSON-RPC 2.0 Notification differ from a regular Request?

A JSON-RPC 2.0 Request includes an id member so the server can match its Response object to the call. A Notification omits the id member, and the server must not return any response to it, including when it appears inside a batch. [1]

### What are the reserved error codes in JSON-RPC 2.0?

JSON-RPC 2.0 reserves integer error codes from -32768 to -32000 for pre-defined protocol errors. Specifically, -32700 is Parse error, -32600 is Invalid Request, -32601 is Method not found, -32602 is Invalid params, -32603 is Internal error, and -32000 to -32099 are reserved for implementation-defined server errors. [1]

### Does JSON-RPC 2.0 require HTTP as its transport protocol?

No. JSON-RPC 2.0 is transport-agnostic and defines only JSON data structures and processing rules, allowing implementations to operate over HTTP, sockets, within the same process, or across other message-passing channels. [1]

### What changed between JSON-RPC 1.0 and JSON-RPC 2.0?

JSON-RPC 2.0 added the required "jsonrpc": "2.0" version field, named parameters via JSON Objects, batch request arrays, and mutually exclusive result and error response fields. It also changed notifications from "id": null to an omitted id and dropped version 1.0's __jsonclass__ class hinting. [1][2]

### Which major protocols and specifications use JSON-RPC?

The Model Context Protocol (MCP), the Language Server Protocol (LSP), and Ethereum execution client APIs use JSON-RPC 2.0, while the Open vSwitch Database Management Protocol (RFC 7047) uses JSON-RPC 1.0. OpenRPC defines a standard machine-readable interface description format specifically for JSON-RPC 2.0 APIs. [5][6][7][8][10]

## Quotable sentences

- JSON-RPC 2.0 originated on 2010-03-26 from a 2009-05-24 draft and received its latest documented update on 2013-01-04. [1]
- Every JSON-RPC 2.0 Request and Response object must include a "jsonrpc" member with the exact String value "2.0". [1]
- A JSON-RPC 2.0 Response object must include either a "result" member or an "error" member, and must not include both. [1]
- JSON-RPC 2.0 reserves integer error codes -32768 through -32000 for pre-defined protocol errors, with -32000 through -32099 designated for implementation-defined server errors. [1]
- Method names beginning with "rpc." are reserved in JSON-RPC 2.0 for optional system extensions, such as OpenRPC's "rpc.discover" service discovery method. [1][10]
- The IETF published RFC 8259 in December 2017 to standardize the JSON data interchange format, replacing RFC 7159 and RFC 4627. [4]
- The Model Context Protocol (version 2026-07-28) and the Language Server Protocol (version 3.17) both use JSON-RPC 2.0 as their base message format. [6][7]
- Ethereum execution clients implement a standard JSON-RPC 2.0 API specified in OpenRPC format in the CC0-1.0 licensed ethereum/execution-apis repository. [8][9]

## Timeline

- 2005: JSON-RPC.ORG publishes the JSON-RPC 1.0 specification for peer-to-peer remote procedure calls over stream connections and HTTP. [2]
- 2008-01-15: Jeffrey Damick and the JSON-RPC Working Group draft the historical JSON-RPC over HTTP extension for version 1.2. [3]
- 2009-05-24: The JSON-RPC Working Group produces the base draft version later used to form JSON-RPC 2.0. [1]
- 2010-03-26: The JSON-RPC Working Group publishes the JSON-RPC 2.0 specification. [1]
- 2013-01-04: The JSON-RPC Working Group publishes the latest documented update to the JSON-RPC 2.0 specification text. [1]
- 2013-12: The IETF publishes Informational RFC 7047, defining the Open vSwitch Database Management Protocol (OVSDB) on top of JSON-RPC 1.0. [5]
- 2017-12: The IETF publishes RFC 8259, replacing RFC 7159 and RFC 4627 as the Standards Track JSON specification. [4]
- 2026-07-28: The Model Context Protocol project publishes specification version 2026-07-28 using JSON-RPC 2.0 messages. [6]

## Sources

1. JSON-RPC 2.0 Specification. JSON-RPC Working Group. published 2010-03-26. https://www.jsonrpc.org/specification (checked 2026-11-23; tier 3: official site)
2. JSON-RPC 1.0 Specification (2005). JSON-RPC Working Group. published 2005. https://www.jsonrpc.org/specification_v1 (checked 2026-11-23; tier 3: official site)
3. JSON-RPC over HTTP. JSON-RPC Working Group. published 2008-01-15. https://www.jsonrpc.org/historical/json-rpc-over-http.html (checked 2026-11-23; tier 3: official site)
4. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). published 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (checked 2026-11-23; tier 1: government or public registry)
5. RFC 7047: The Open vSwitch Database Management Protocol. Internet Engineering Task Force (IETF). published 2013-12. https://www.rfc-editor.org/rfc/rfc7047.txt (checked 2026-11-23; tier 1: government or public registry)
6. Specification - Model Context Protocol. Model Context Protocol project. published 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28 (checked 2026-11-23; tier 3: official site)
7. Language Server Protocol Specification - 3.17. Microsoft (LSP). https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/ (checked 2026-11-23; tier 3: official site)
8. JSON-RPC API | ethereum.org. ethereum.org. https://ethereum.org/developers/docs/apis/json-rpc/ (checked 2026-11-23; tier 3: official site)
9. GitHub - ethereum/execution-apis: Collection of APIs provided by Ethereum execution layer clients · GitHub. Ethereum (GitHub). https://github.com/ethereum/execution-apis (checked 2026-11-23; tier 3: official site)
10. OpenRPC Specification | spec. OpenRPC. https://spec.open-rpc.org/ (checked 2026-11-23; tier 3: official site)

## Cite this page

Mimirwiki. "JSON-RPC." Version 63336d54, 2026-11-23. https://mimirwiki.com/wiki/json-rpc
