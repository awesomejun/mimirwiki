---
title: "모델 컨텍스트 프로토콜"
subtitle: "AI 애플리케이션을 외부 도구와 데이터에 연결하는 개방형 프로토콜"
canonical_url: https://mimirwiki.com/ko/wiki/model-context-protocol
language: ko
page_class: anchor
revision_sha256: 16b7e37560d5f70633f7ce24719f4c6abccd28a91c623b1ca2b2b72dd06d492c
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/model-context-protocol.md
  txt: https://mimirwiki.com/ko/wiki/model-context-protocol.txt
  json: https://mimirwiki.com/ko/wiki/model-context-protocol.json
  jsonld: https://mimirwiki.com/ko/wiki/model-context-protocol.jsonld
translations:
  en: https://mimirwiki.com/wiki/model-context-protocol
  ja: https://mimirwiki.com/ja/wiki/model-context-protocol
  zh: https://mimirwiki.com/zh/wiki/model-context-protocol
  es: https://mimirwiki.com/es/wiki/model-context-protocol
---

# 모델 컨텍스트 프로토콜

> 모델 컨텍스트 프로토콜(MCP)은 AI 애플리케이션이 하나의 공통 인터페이스로 외부 도구와 데이터 소스에 연결하도록 하는 개방형 프로토콜이다. JSON-RPC 2.0 메시지를 stdio 또는 Streamable HTTP로 주고받는다. Anthropic이 2024년 11월 25일 공개했고, 2025년 12월부터 리눅스 재단의 에이전틱 AI 재단에 속해 있다. 현재 버전은 2026-07-28이다.

모델 컨텍스트 프로토콜(Model Context Protocol, MCP)은 대규모 언어 모델 기반 애플리케이션이 외부 데이터 소스와 도구에 연결하는 방식을 표준화한 개방형 프로토콜이다. MCP 메시지는 JSON-RPC 2.0을 따르며, 호스트와 클라이언트, 서버 사이를 stdio와 Streamable HTTP라는 두 가지 표준 전송 방식으로 오간다. Anthropic이 2024년 11월 25일 오픈 소스로 공개했고, 2025년 12월 9일 발표를 통해 리눅스 재단 산하에 설립된 에이전틱 AI 재단(Agentic AI Foundation)에 기증했다. 2026년 11월 21일 기준 현재 프로토콜 버전은 2026-07-28이며, 이 개정판에서 프로토콜이 무상태(stateless) 방식으로 바뀌었다.

**다른 이름:** MCP, Model Context Protocol

## 핵심 정보

- **최초 공개:** 2024-11-25, Anthropic [8]
- **현재 프로토콜 버전:** 2026-07-28 (기준 2026-11-21) [2]
- **메시지 형식:** JSON-RPC 2.0 [1]
- **표준 전송 방식:** stdio, Streamable HTTP [4]
- **소속 재단:** 에이전틱 AI 재단(리눅스 재단), 2025-12-09 발표 [9]

## 기본 정보

- **유형:** LLM 애플리케이션을 외부 데이터 소스와 도구에 연결하는 개방형 프로토콜 [1]
- **최초 개발:** Anthropic [8]
- **최초 공개:** 2024-11-25 [8]
- **현재 버전:** 2026-07-28 (기준 2026-11-21) [2]
- **버전 표기:** 날짜 문자열(YYYY-MM-DD) [2]
- **메시지 형식:** JSON-RPC 2.0, UTF-8 인코딩 [4]
- **표준 전송 방식:** stdio, Streamable HTTP [4]
- **서버 기능:** 리소스, 프롬프트, 도구 [1]
- **인가:** 선택 사항. HTTP 기반 전송에서는 OAuth 2.1 기반 [5]
- **법적 실체:** Model Context Protocol a Series of LF Projects, LLC [6]
- **라이선스:** Apache License 2.0(코드와 사양), CC BY 4.0(그 밖의 문서) [6]
- **공식 SDK:** TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP, Kotlin (기준 2026-11-21) [7]

## 모델 컨텍스트 프로토콜이란

모델 컨텍스트 프로토콜(Model Context Protocol, MCP)은 대규모 언어 모델(LLM)로 만든 애플리케이션을 외부 데이터 소스와 도구에 연결하는 개방형 프로토콜이다.[1] 사양은 목적을 세 가지로 든다. 언어 모델에 맥락 정보를 전달하는 것, AI 시스템에 도구와 기능을 노출하는 것, 조합할 수 있는 통합과 워크플로를 구성하는 것이다.[1] 사양은 [언어 서버 프로토콜](https://mimirwiki.com/ko/wiki/language-server-protocol)(Language Server Protocol)에서 착안했다고 밝힌다. 언어 서버 프로토콜이 여러 개발 도구의 프로그래밍 언어 지원을 표준화했듯이, MCP는 AI 애플리케이션에 맥락과 도구를 붙이는 방식을 표준화한다.[1]

MCP에는 세 가지 역할이 있다. 호스트(host)는 연결을 시작하는 LLM 애플리케이션이고, 클라이언트(client)는 호스트 안에서 동작하는 커넥터이며, 서버(server)는 맥락과 기능을 제공하는 서비스다.[1] 서버는 리소스(맥락과 데이터), 프롬프트(템플릿 형태의 메시지와 워크플로), 도구(모델이 실행할 수 있는 함수)를 제공할 수 있다. 클라이언트는 서버가 사용자에게 추가 정보를 요청하는 통로인 엘리시테이션(elicitation)을 제공할 수 있다.[1]

[Anthropic](https://mimirwiki.com/ko/wiki/anthropic)은 2024년 11월 25일 MCP를 오픈 소스 표준으로 발표했다. 이때 사양과 소프트웨어 개발 키트(SDK), Claude Desktop 앱의 로컬 MCP 서버 지원, MCP 서버를 모은 오픈 소스 저장소가 함께 공개됐다.[8] 발표문은 Anthropic의 David Soria Parra와 Justin Spahr-Summers가 이 프로토콜을 만들었다고 밝혔다.[8]

## 모델 컨텍스트 프로토콜의 메시지 형식과 구조

모델 컨텍스트 프로토콜은 모든 메시지를 [JSON-RPC](https://mimirwiki.com/ko/wiki/json-rpc) 2.0으로 표현하며, 메시지는 UTF-8로 인코딩해야 한다.[1][4] 클라이언트는 요청과 알림을 보내고, 서버는 응답과 알림으로 답한다. 현행 개정판에는 이 밖의 방향이 없다. 서버가 JSON-RPC 요청을 먼저 보내지 않고, 클라이언트가 JSON-RPC 응답을 보내지도 않는다.[4]

2026-07-28 개정판부터 MCP는 프로토콜 수준에서 무상태(stateless)다. 이전 개정판의 `initialize` 핸드셰이크가 없어졌고, 요청마다 프로토콜 버전과 클라이언트의 기능 목록을 `_meta` 필드에 담아 보낸다.[3] 서버는 자신이 지원하는 프로토콜 버전과 기능, 식별 정보를 알려 주는 `server/discover` 메서드를 반드시 구현해야 한다. 클라이언트는 이 메서드를 가장 먼저 호출할 수 있지만 의무는 아니다.[2][3]

호출을 처리하던 서버가 클라이언트 쪽 정보를 필요로 하면, 필요한 내용을 나열한 `input_required` 결과를 돌려준다. 클라이언트는 답을 덧붙여 원래 요청을 다시 보낸다. 사양은 이 방식을 다중 왕복 요청(Multi Round-Trip Requests, MRTR)이라 부르며, 이전 개정판에서 서버가 먼저 보내던 요청을 이것이 대체한다.[3] 도구 목록 변경처럼 오래 이어지는 변경 알림은 클라이언트가 `subscriptions/listen` 요청으로 연 스트림을 통해 전달된다.[3]

## 모델 컨텍스트 프로토콜의 전송 방식과 인가

모델 컨텍스트 프로토콜은 stdio와 Streamable HTTP라는 두 가지 표준 전송 방식을 정의한다. stdio에서는 클라이언트가 서버를 하위 프로세스로 실행하고, 양쪽이 표준 입출력으로 줄바꿈 단위의 메시지를 주고받는다. Streamable HTTP에서는 메시지 하나하나가 단일 MCP 엔드포인트로 보내는 HTTP POST이며, 응답은 JSON 객체 하나 또는 해당 요청에 한정된 서버 전송 이벤트(Server-Sent Events, SSE) 스트림으로 돌아온다.[4] 프로토콜의 의미는 두 방식에서 동일하다. JSON-RPC 메시지 형식과 메시지 패턴, 요청별 메타데이터 모델을 유지하면 사용자 정의 전송 방식도 쓸 수 있다.[4]

Streamable HTTP에서는 중간 장비가 본문을 해석하지 않고도 요청을 라우팅할 수 있도록 일부 메타데이터를 HTTP 헤더에도 싣는다.[4] 프로토콜 버전은 `MCP-Protocol-Version` 헤더에 담기고, 2026-07-28 개정판은 POST 요청에 `Mcp-Method`와 `Mcp-Name` 헤더를 요구한다.[2][3]

MCP에서 인가(authorization)는 선택 사항이다. HTTP 기반 전송에서는 사양이 [OAuth](https://mimirwiki.com/ko/wiki/oauth) 2.1을 바탕으로 삼는다. 보호되는 MCP 서버는 OAuth 2.1 리소스 서버로, MCP 클라이언트는 OAuth 2.1 클라이언트로 동작하며, 서버는 클라이언트가 인가 서버를 찾을 수 있도록 OAuth 2.0 보호 리소스 메타데이터(RFC 9728)를 제공해야 한다.[5] stdio를 쓰는 구현은 이 절차를 따르지 않고 환경에서 자격 증명을 가져오도록 되어 있다.[5]

## 모델 컨텍스트 프로토콜의 버전과 2026-07-28 개정판

모델 컨텍스트 프로토콜의 버전은 `YYYY-MM-DD` 형식의 날짜 문자열이다. 버전 식별자는 하위 호환이 깨지는 변경이 마지막으로 이루어진 날짜를 뜻하며, 하위 호환이 유지되는 갱신으로는 바뀌지 않는다.[2] 2026년 11월 21일 기준 현재 버전은 2026-07-28이다.[2] GitHub의 사양 저장소 릴리스 페이지에는 2024-11-05, 2025-03-26, 2025-06-18, 2025-11-25, 2026-07-28 개정판이 올라 있다.[10] 클라이언트와 서버는 여러 버전을 동시에 지원할 수 있고, 요청받은 버전을 지원하지 않는 서버는 자신이 지원하는 버전 목록을 담은 `UnsupportedProtocolVersionError`를 돌려준다.[2]

유지보수자들이 쓴 2026-07-28 개정판 공개 글은 이 개정을 양방향 상태 유지 프로토콜에서 무상태 요청·응답 프로토콜로 옮겨 간 변화로 설명한다. 그 결과 로드 밸런서 뒤의 어느 서버 인스턴스든 어떤 요청이든 처리할 수 있다.[11] 변경 내역 문서가 꼽는 주요 변경은 다음과 같다.[3]

| 영역 | 2026-07-28 개정판의 변경 |
| --- | --- |
| 세션 | 프로토콜 수준 세션과 `Mcp-Session-Id` 헤더 삭제 |
| 핸드셰이크 | `initialize` 핸드셰이크 삭제, 버전과 기능 목록을 요청마다 전송 |
| 탐색 | `server/discover` 추가, 서버 구현 필수 |
| 서버의 입력 요청 | 서버가 먼저 보내던 요청을 다중 왕복 요청으로 대체 |
| 알림 | HTTP GET 엔드포인트와 리소스 구독 메서드를 `subscriptions/listen`으로 대체 |
| 태스크 | 실험적 코어 기능에서 `io.modelcontextprotocol/tasks` 확장으로 이동 |
| 폐기 예정 | Roots, Sampling, Logging, HTTP+SSE 전송, OAuth 동적 클라이언트 등록 |

폐기 예정(deprecated)으로 지정된 기능은 삭제 대상이 되기 전까지 최소 12개월 동안 사양에 남는다. 다만 신속 삭제 예외에 해당하면 이 기간은 최소 90일이다.[2] 2026년 11월 11일 리드 유지보수자들은 릴리스 주기를 6개월로 정하고, 사양 릴리스를 대체로 3월과 9월의 마지막 화요일에 내겠다고 발표했다. 다음 릴리스의 목표일은 2027년 3월 30일이며 버전 식별자는 2027-03-30이 될 예정이다.[12]

## 모델 컨텍스트 프로토콜의 거버넌스와 라이선스

모델 컨텍스트 프로토콜은 [리눅스 재단](https://mimirwiki.com/ko/wiki/linux-foundation)(Linux Foundation) 산하 프로젝트다. 리눅스 재단은 2025년 12월 9일 [에이전틱 AI 재단](https://mimirwiki.com/ko/wiki/agentic-ai-foundation)(Agentic AI Foundation, AAIF)의 설립을 발표했고, 창립 프로젝트로 Anthropic의 MCP, Block의 goose, OpenAI의 AGENTS.md 세 가지가 기증됐다.[9] 출범 당시 플래티넘 회원은 Amazon Web Services, Anthropic, Block, Bloomberg, [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare), Google, Microsoft, OpenAI였다.[9] 프로젝트의 거버넌스 문서는 법적 형태를 Model Context Protocol a Series of LF Projects, LLC로 밝힌다.[6]

MCP의 기술적 결정은 유지보수자 계층 구조를 따른다. 기여자(Contributor)는 이슈와 풀 리퀘스트를 올리고, 유지보수자(Maintainer)는 SDK나 워킹 그룹 같은 구성 요소를 맡으며, 코어 유지보수자(Core Maintainer)는 사양의 방향을 이끌고, 리드 유지보수자(Lead Maintainer)가 최종 결정 권한을 가진다.[6] 자격은 개인에게 주어지며 기업 몫으로 배정된 자리는 없다. 2026년 11월 21일 기준 거버넌스 페이지에는 David Soria Parra와 Den Delimarsky가 리드 유지보수자로 올라 있다.[6] 사양 변경은 사양 개선 제안(Specification Enhancement Proposal, SEP)으로 제출한다.[6]

코드와 사양에 대한 기여에는 Apache License 2.0이 적용된다. 사양을 제외한 문서는 크리에이티브 커먼즈 저작자표시 4.0 국제 라이선스로 공개된다.[6]

## 모델 컨텍스트 프로토콜의 SDK, 채택 현황, 한계

모델 컨텍스트 프로토콜 프로젝트는 열 가지 프로그래밍 언어의 공식 SDK를 관리한다. 2026년 11월 21일 기준 SDK 페이지는 TypeScript, Python, C#, Go, Rust, Ruby를 1등급(Tier 1), Java를 2등급, Swift, PHP, Kotlin을 3등급으로 분류한다. 등급은 기능 완성도, 프로토콜 지원 범위, 유지보수 약속 수준을 반영한다.[7] 새 개정판을 받아들이는 시점은 SDK마다 다르다. 2026-07-28 개정판이 공개된 날에는 TypeScript, Python, Go, C# SDK가 이 개정판을 지원했다.[7][11]

MCP 채택 규모에 관해 공개된 수치는 프로젝트와 소속 재단이 발표한 것이다. 리눅스 재단은 2025년 12월 9일, 공개된 MCP 서버가 1만 개를 넘고 Claude, Cursor, Microsoft Copilot, Gemini, VS Code, ChatGPT가 이 프로토콜을 채택했다고 밝혔다.[9] 유지보수자들은 2026년 7월 28일, 1등급 SDK의 월간 다운로드가 5억 회에 가깝고 TypeScript SDK와 Python SDK의 누적 다운로드가 각각 10억 회를 넘었다고 밝혔다.[11]

MCP는 프로토콜 사양이므로 사양이 보장하지 않는 영역이 있다. 사양은 프로토콜만으로는 동의와 안전에 관한 원칙을 강제할 수 없다고 밝히고, 호스트가 도구를 호출하기 전에 사용자의 명시적 동의를 받을 것과 신뢰할 수 있는 서버에서 받은 것이 아니면 도구 설명을 신뢰하지 않을 것을 요구한다.[1] 인가는 선택 사항이고, Tasks나 MCP Apps 같은 확장은 코어 프로토콜 밖에서 선택적으로 쓰는 기능이다.[1][5] 무상태라는 성질은 프로토콜에 해당하며 애플리케이션까지 무상태가 되는 것은 아니다. 호출 사이에 상태가 필요한 서버는 명시적 핸들을 발급하고, 이 핸들을 일반 도구 인자로 다시 전달받는다.[3]

## 자주 묻는 질문

### 모델 컨텍스트 프로토콜의 현재 버전은 무엇인가요?

2026년 11월 21일 기준 현재 프로토콜 버전은 2026-07-28입니다. 버전은 YYYY-MM-DD 형식의 날짜 문자열이며, 하위 호환이 깨지는 변경이 있을 때만 바뀝니다. [2]

### 모델 컨텍스트 프로토콜은 누가 관리하나요?

리눅스 재단 산하에서 Model Context Protocol a Series of LF Projects, LLC라는 형태로 운영되며, Anthropic이 2025년 12월 9일 발표된 에이전틱 AI 재단에 기증했습니다. 기술적 결정은 개인 자격의 유지보수자들이 내리고, 최종 권한은 리드 유지보수자에게 있습니다. [6][9]

### 모델 컨텍스트 프로토콜은 어떤 메시지 형식과 전송 방식을 쓰나요?

메시지는 UTF-8로 인코딩한 JSON-RPC 2.0입니다. 표준 전송 방식은 두 가지로, 서버를 로컬 하위 프로세스로 실행하는 stdio와 메시지마다 단일 엔드포인트에 HTTP POST를 보내는 Streamable HTTP가 있습니다. [1][4]

### 모델 컨텍스트 프로토콜을 쓰려면 OAuth가 꼭 필요한가요?

아닙니다. MCP에서 인가는 선택 사항입니다. HTTP 기반 전송에서 인가를 쓸 때는 사양이 OAuth 2.1을 바탕으로 하고, stdio 구현은 환경에서 자격 증명을 가져옵니다. [5]

### 모델 컨텍스트 프로토콜 2026-07-28 개정판에서 무엇이 바뀌었나요?

initialize 핸드셰이크와 프로토콜 수준 세션이 없어져 요청 하나하나가 독립적으로 처리됩니다. server/discover 메서드와 다중 왕복 요청이 추가됐고, Roots, Sampling, Logging은 폐기 예정으로 지정됐습니다. [3]

### 모델 컨텍스트 프로토콜의 공식 SDK는 어떤 언어로 제공되나요?

2026년 11월 21일 기준 TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP, Kotlin용 공식 SDK가 있습니다. 앞의 여섯 개는 1등급(Tier 1)으로 분류됩니다. [7]

## 인용 문장

- 모델 컨텍스트 프로토콜은 JSON-RPC 2.0 메시지를 사용한다. [1]
- 2026년 11월 21일 기준 모델 컨텍스트 프로토콜의 현재 버전은 2026-07-28이다. [2]
- Anthropic은 2024년 11월 25일 모델 컨텍스트 프로토콜을 오픈 소스로 공개했다. [8]
- 리눅스 재단은 2025년 12월 9일 Anthropic이 모델 컨텍스트 프로토콜을 새로 설립된 에이전틱 AI 재단에 기증했다고 발표했다. [9]
- 모델 컨텍스트 프로토콜은 stdio와 Streamable HTTP라는 두 가지 표준 전송 방식을 정의한다. [4]
- 모델 컨텍스트 프로토콜 2026-07-28 개정판은 initialize 핸드셰이크와 프로토콜 수준 세션을 없애 프로토콜을 무상태로 만들었다. [3]
- 모델 컨텍스트 프로토콜에서 인가는 선택 사항이며, HTTP 기반 전송에서는 OAuth 2.1을 바탕으로 한다. [5]
- 유지보수자들의 2026년 11월 11일 발표에 따르면 모델 컨텍스트 프로토콜의 다음 사양 릴리스 목표일은 2027년 3월 30일이다. [12]

## 연표

- 2024-11-25: Anthropic이 모델 컨텍스트 프로토콜을 오픈 소스로 공개한다. [8]
- 2025-03-26: 2025-03-26 개정판이 공개된다. HTTP+SSE 전송은 이 개정판부터 폐기 예정으로 취급된다. [10][3]
- 2025-06-18: 2025-06-18 개정판이 공개된다. [10]
- 2025-11-25: 태스크를 실험적으로 지원하는 2025-11-25 개정판이 공개된다. [10][12]
- 2025-12-09: 리눅스 재단이 에이전틱 AI 재단 설립을 발표하고, Anthropic이 모델 컨텍스트 프로토콜을 기증한다. [9]
- 2026-07-28: 2026-07-28 개정판이 공개되어 프로토콜이 무상태 방식으로 바뀐다. [11][3]
- 2026-11-11: 리드 유지보수자들이 6개월 릴리스 주기를 발표하고 다음 릴리스 목표일을 2027-03-30으로 정한다. [12]

## 출처

1. Specification - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28 (확인일 2026-11-21; tier 3: official site)
2. Versioning - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/versioning (확인일 2026-11-21; tier 3: official site)
3. Key Changes - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/changelog (확인일 2026-11-21; tier 3: official site)
4. Overview - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports (확인일 2026-11-21; tier 3: official site)
5. Authorization - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (확인일 2026-11-21; tier 3: official site)
6. Governance and Stewardship - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/community/governance (확인일 2026-11-21; tier 3: official site)
7. SDKs - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/docs/sdk (확인일 2026-11-21; tier 3: official site)
8. Introducing the Model Context Protocol. Anthropic. 게시일 2024-11-25. https://www.anthropic.com/news/model-context-protocol (확인일 2026-11-21; tier 3: official site)
9. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. 게시일 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (확인일 2026-11-21; tier 3: official site)
10. Releases · modelcontextprotocol/modelcontextprotocol · GitHub. Model Context Protocol project (GitHub). https://github.com/modelcontextprotocol/modelcontextprotocol/releases (확인일 2026-11-21; tier 3: official site)
11. The 2026-07-28 Specification. Model Context Protocol Blog. 게시일 2026-07-28. https://blog.modelcontextprotocol.io/posts/2026-07-28/ (확인일 2026-11-21; tier 3: official site)
12. A More Predictable Release Cycle for MCP. Model Context Protocol Blog. 게시일 2026-11-11. https://blog.modelcontextprotocol.io/posts/mcp-release-cycle/ (확인일 2026-11-21; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "모델 컨텍스트 프로토콜." 버전 16b7e375, 2026-11-21. https://mimirwiki.com/ko/wiki/model-context-protocol
