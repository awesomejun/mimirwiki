---
title: "JSON-RPC"
subtitle: "JSON으로 메시지를 인코딩하는 전송 독립적 원격 프로시저 호출 프로토콜"
canonical_url: https://mimirwiki.com/ko/wiki/json-rpc
language: ko
page_class: anchor
revision_sha256: f1db796dbb08c5bd9b02d3544be6d465e10d73fbcd802571f7e52daabbc4eada
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/json-rpc.md
  txt: https://mimirwiki.com/ko/wiki/json-rpc.txt
  json: https://mimirwiki.com/ko/wiki/json-rpc.json
  jsonld: https://mimirwiki.com/ko/wiki/json-rpc.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-rpc
  ja: https://mimirwiki.com/ja/wiki/json-rpc
  zh: https://mimirwiki.com/zh/wiki/json-rpc
---

# JSON-RPC

> JSON-RPC는 요청, 응답, 통지, 오류, 배치 호출을 JSON 형식으로 인코딩하는 무상태 경량 원격 프로시저 호출(RPC) 프로토콜이다. JSON-RPC 워킹 그룹이 2010년 버전 2.0을 공개하고 2013년 갱신했다. 전송 프로토콜에 독립적이어서 HTTP, 소켓, 단일 프로세스 내부에서 동작하며 MCP, LSP, 이더리움 클라이언트의 메시지 교환에 쓰인다.

JSON-RPC는 자바스크립트 객체 표기법(JavaScript Object Notation, JSON)으로 메시지를 인코딩하는 무상태 경량 원격 프로시저 호출(Remote Procedure Call, RPC) 프로토콜이다. JSON-RPC 워킹 그룹(JSON-RPC Working Group)이 2009년 5월 24일 초안을 바탕으로 2010년 3월 26일 버전 2.0을 공개했고 2013년 1월 4일 사양 문서를 마지막으로 갱신했으며, 2026-11-23 기준 버전 2.0이 현행 사양이다. JSON-RPC 사양은 요청(Request), 응답(Response), 통지(Notification), 오류(Error), 배치(Batch) 데이터 구조와 처리 규칙을 규정하며 전송 계층의 선택은 구현체에 맡긴다. JSON-RPC는 모델 컨텍스트 프로토콜(Model Context Protocol, MCP), 언어 서버 프로토콜(Language Server Protocol, LSP), 이더리움(Ethereum) 실행 클라이언트 API, 오픈 v스위치 데이터베이스 관리 프로토콜(Open vSwitch Database Management Protocol, OVSDB)에서 기본 메시지 형식으로 쓰인다.

**다른 이름:** JSON-RPC 2.0, JSON-RPC 1.0, JSON 원격 프로시저 호출

## 핵심 정보

- **현재 버전:** 2.0(2010-03-26 공개, 2013-01-04 갱신) (기준 2026-11-23) [1]
- **최초 버전:** 1.0(2005년) [2]
- **작성 주체:** JSON-RPC 워킹 그룹 [1]
- **데이터 형식:** JSON(RFC 4627) [1]
- **전송 방식:** 전송 독립적(단일 프로세스 내부, 소켓, HTTP, 기타 메시지 채널) [1]

## 기본 정보

- **유형:** 무상태 경량 원격 프로시저 호출(RPC) 프로토콜 [1]
- **작성 주체:** JSON-RPC 워킹 그룹(JSON-RPC Working Group) [1]
- **최초 버전:** JSON-RPC 1.0(2005년) [2]
- **현재 버전:** JSON-RPC 2.0(2010-03-26 공개, 2013-01-04 갱신) (기준 2026-11-23) [1]
- **데이터 형식:** JSON(원시 자료형 4종과 구조화 자료형 2종) [1]
- **JSON 표준:** RFC 8259(2017년 12월, RFC 7159 및 RFC 4627 대체) (기준 2026-11-23) [4]
- **전송 방식:** 전송 독립적(단일 프로세스 내부, 소켓, HTTP, 기타 메시지 전달 환경) [1]
- **메시지 유형:** 요청(Request), 응답(Response), 통지(Notification), 오류(Error), 배치(Batch) [1]
- **예약 오류 코드:** -32768~-32000(사전 정의 -32700, -32600~-32603, 서버 오류 -32000~-32099) [1]
- **확장 접두사:** rpc.(선택적 시스템 확장용 예약 접두사) [1]
- **인터페이스 기술 형식:** OpenRPC 사양(버전 1.4.x, 서비스 탐색 메서드 rpc.discover) (기준 2026-11-23) [10]

## JSON-RPC란

JSON-RPC는 메서드 호출과 응답을 자바스크립트 객체 표기법(JSON) 데이터로 인코딩하는 무상태 경량 원격 프로시저 호출(RPC) 프로토콜이다.[1] JSON-RPC 2.0 사양은 적은 수의 데이터 구조와 처리 규칙을 정의하며 특정 네트워크 전송 계층에 종속되지 않도록 설계됐다.[1] 2026-11-23 기준 JSON-RPC 2.0은 JSON-RPC 워킹 그룹이 유지하는 현행 사양으로, 2009년 5월 24일 초안을 바탕으로 2010년 3월 26일 제정됐고 2013년 1월 4일 마지막으로 문서가 갱신됐다.[1]

JSON-RPC는 원시 자료형 4종(String, Number, Boolean, Null)과 구조화 자료형 2종(Object, Array)으로 구성된 JSON 자료형 체계를 그대로 사용한다.[1][4] JSON-RPC 2.0 본문은 JSON 참조 문서로 RFC 4627을 인용한다.[1] 국제 인터넷 표준화 기구(IETF)는 2017년 12월 RFC 8259를 발행해 RFC 7159를 대체했으며, 앞서 RFC 7159는 `application/json` 미디어 유형을 처음 등록한 RFC 4627을 대체한 바 있다.[4] RFC 8259는 JSON 문법을 ECMA-404와 일치시키고, 최상위 텍스트로 JSON 객체나 배열만 생성하는 구현체가 모든 호환 파서와 상호 운용된다고 명시하는데 이는 단일 객체와 배치 배열을 쓰는 JSON-RPC의 구조와 맞물린다.[1][4]

JSON-RPC 2.0에서 클라이언트(Client)는 요청(Request) 객체를 보내고 응답(Response) 객체를 처리하는 주체이며, 서버(Server)는 요청 객체를 처리하고 응답 객체를 보내는 주체이다.[1] 하나의 구현체가 다른 피어나 같은 피어를 상대로 두 역할을 동시에 맡을 수 있지만 사양은 양방향 세션 관리 계층을 다루지 않는다.[1] 클라이언트와 서버 사이에서 일치 여부를 따지는 모든 멤버 이름은 대소문자를 구분하며, 사양은 함수(function), 메서드(method), 프로시저(procedure)라는 용어를 같은 뜻으로 취급한다.[1]

## JSON-RPC 2.0 메시지 구조

JSON-RPC 2.0은 요청(Request) 객체, 통지(Notification), 응답(Response) 객체의 세 가지 기본 메시지 형식을 정의한다.[1] 사양을 따르는 모든 요청 객체와 응답 객체에는 문자열 값이 정확히 `"2.0"`인 `jsonrpc` 멤버가 들어가야 한다.[1]

JSON-RPC 2.0 요청 객체는 원격 메서드를 호출할 때 쓰며 최대 네 개의 멤버를 가진다.[1]

- `jsonrpc`: 프로토콜 버전을 나타내는 필수 문자열로, 항상 `"2.0"`이어야 한다.
- `method`: 호출할 프로시저의 이름을 담은 필수 문자열이다. `rpc.`(`rpc` 뒤에 마침표 U+002E가 붙은 형태)로 시작하는 메서드 이름은 RPC 내부 메서드와 선택적 시스템 확장용으로 예약되어 있어 다른 용도로 쓸 수 없다.
- `params`: 호출에 전달할 매개변수를 담은 선택적 구조화 값이다. 포함할 때는 서버가 기대하는 순서대로 값을 넣은 JSON 배열(위치 기반)이나, 서버가 기대하는 매개변수 이름과 대소문자까지 정확히 일치하는 키를 가진 JSON 객체(이름 기반)로 전달한다.
- `id`: 클라이언트가 정하는 선택적 식별자로, 포함할 때는 문자열, 숫자, Null 가운데 하나여야 한다. 알 수 없는 `id`에 대한 응답이 Null을 사용하고 JSON-RPC 1.0이 통지에 Null `id`를 썼기 때문에 요청 `id`에 Null을 쓰는 일은 피하도록 권고된다. 또한 이진 부동소수점 표현으로 많은 십진 소수를 정확히 나타낼 수 없으므로 숫자 `id`에는 소수부를 넣지 않도록 권고된다.

JSON-RPC 2.0 통지(Notification)는 `id` 멤버를 생략한 요청 객체이다.[1] `id`를 생략하면 클라이언트가 응답을 원하지 않는다는 뜻이 되며, 서버는 배치 안에 포함된 통지를 포함해 어떤 통지에도 응답 객체를 보내지 않아야 한다.[1] 응답이 돌아오지 않으므로 통지는 수신 여부를 확인할 수 없으며, 잘못된 매개변수나 내부 오류가 발생해도 클라이언트는 오류 보고를 받지 못한다.[1]

통지를 제외한 모든 요청 객체에 대해 JSON-RPC 2.0 서버는 단일 JSON 응답 객체로 답해야 한다.[1] 응답 객체에는 항상 `"jsonrpc": "2.0"`과 요청 객체의 `id`와 같은 값을 담은 `id` 멤버가 들어가며, 구문 분석 오류나 잘못된 요청 때문에 `id`를 파악하지 못한 경우에는 `id`를 Null로 설정한다.[1] 응답 객체는 성공 시 `result` 멤버를, 실패 시 `error` 멤버를 반드시 포함해야 하며 두 멤버가 한 응답 객체에 함께 들어가면 안 된다.[1]

## JSON-RPC 2.0 오류 객체와 예약 오류 코드

JSON-RPC 2.0은 메서드 실행 실패를 응답 객체의 `error` 멤버에 담은 구조화된 오류(Error) 객체로 보고한다.[1] 오류 객체는 필수 멤버 두 개와 선택 멤버 하나로 구성된다. `code`는 오류 유형을 나타내는 정수, `message`는 오류를 간결한 한 문장으로 요약한 문자열, 선택 멤버 `data`는 서버가 추가 오류 정보를 담아 보내는 원시 값 또는 구조화 값이다.[1]

JSON-RPC 2.0은 사전 정의된 프로토콜 오류용으로 -32768부터 -32000까지의 정수 범위를 예약하며, XML-RPC 오류 코드 체계와 거의 같은 값을 채택한다.[1] 이 범위 안에서 명시적으로 할당되지 않은 코드는 향후 확장을 위해 예약되어 있고, -32768~-32000 범위 밖의 정수는 애플리케이션이 자체 오류 코드로 사용할 수 있다.[1]

| 코드 | 메시지 | 의미 |
| --- | --- | --- |
| -32700 | Parse error | 서버가 유효하지 않은 JSON을 받았거나 JSON 텍스트 구문 분석 중 오류가 발생했다. |
| -32600 | Invalid Request | 전송된 JSON이 유효한 요청 객체가 아니다. |
| -32601 | Method not found | 요청한 메서드가 존재하지 않거나 사용할 수 없다. |
| -32602 | Invalid params | 메서드 매개변수가 유효하지 않다. |
| -32603 | Internal error | JSON-RPC 내부 오류가 발생했다. |
| -32000 ~ -32099 | Server error | 구현체가 정의하는 서버 오류용으로 예약된 범위이다. |

하위 프로토콜은 이 예약 범위를 유지하면서 자체 오류 체계를 덧붙인다.[7] 언어 서버 프로토콜(LSP) 3.17 사양은 JSON-RPC의 핵심 오류 코드 5종(-32700 및 -32600~-32603)을 그대로 사용하고, -32099~-32000 대역을 JSON-RPC 예약 범위로 구분해 하위 호환용 구형 코드인 -32002(ServerNotInitialized)와 -32001(UnknownErrorCode)만 남겼으며, -32803(RequestFailed)과 -32802(ServerCancelled) 같은 LSP 전용 오류는 -32899에서 시작하는 별도 범위에 배치한다.[7]

## JSON-RPC 배치 처리와 전송 독립성

JSON-RPC 2.0에서 클라이언트는 여러 요청 객체를 하나의 JSON 배열(Array)로 묶어 한 번에 전송하는 배치(Batch) 호출을 사용할 수 있다.[1] 서버는 배치 안의 모든 요청을 처리한 뒤 통지를 제외한 각 요청에 대응하는 응답 객체들을 담은 JSON 배열을 반환한다.[1] 서버는 배치 요청을 임의의 순서와 병렬도로 동시 처리할 수 있고 응답 객체도 임의의 순서로 반환할 수 있으므로, 클라이언트는 각 객체의 `id` 멤버를 기준으로 요청과 응답을 대응시킨다.[1]

JSON-RPC 2.0은 배치 호출의 예외 상황 처리 규칙도 구체적으로 정한다.[1] 배치 본문이 잘못된 JSON이거나 빈 배열(`[]`)이면 서버는 배열을 반환하지 않고 오류 코드 -32700(Parse error) 또는 -32600(Invalid Request)과 `"id": null`을 담은 단일 응답 객체 하나를 돌려준다.[1] 비어 있지 않은 배열에 유효하지 않은 항목이 섞여 있으면 서버는 응답 배열 안에 정상 응답과 함께 각 오류 항목에 대한 Invalid Request(-32600) 오류 객체를 담아 반환한다.[1] 배치의 모든 항목이 통지인 경우 서버는 빈 배열을 보내지 않아야 하며 아무런 응답 본문도 반환하지 않는다.[1]

JSON-RPC 2.0은 메시지 프레이밍과 전송 계층 결합 방식을 핵심 사양 밖에 두어, 같은 JSON 구조가 단일 프로세스 내부, 소켓, HTTP, 기타 메시지 전달 환경에서 그대로 동작하게 한다.[1] 초기 개발 과정이던 2008년 1월 15일 제프리 대믹(Jeffrey Damick)과 JSON-RPC 워킹 그룹은 버전 1.2를 대상으로 한 역사적 초안 "JSON-RPC over HTTP"를 작성했다.[3] 이 초안은 HTTP POST를 우선 방식으로 정하고 HTTP GET에는 Base64 및 URL 인코딩한 매개변수를 쓰도록 규정했으며(오래된 클라이언트와 프록시에서 255바이트를 넘는 URI 길이 문제가 생길 수 있음을 적시했다), `Content-Type`과 `Accept` 헤더로 `application/json-rpc`(`application/json` 및 `application/jsonrequest` 허용)와 필수 `Content-Length`를 지정했다.[3] 또한 일반 요청 성공에 200, 통지 성공에 204, -32600에 400, -32601에 404, 그리고 -32700, -32602, -32603 및 서버 오류(-32099~-32000)에 500을 대응시키는 HTTP 상태 코드 매핑을 제안했다.[3] JSON-RPC 2.0을 채택한 프로토콜은 각자 전송 규약을 따로 정의한다. LSP는 HTTP 형식의 ASCII `Content-Length`와 선택적 `Content-Type`(기본값 `application/vscode-jsonrpc; charset=utf-8`) 헤더 뒤에 `\r\n\r\n`을 두어 UTF-8 JSON-RPC 2.0 본문을 구분하며, 이더리움 실행 노드는 일반적으로 `Content-Type: application/json` 헤더를 붙인 HTTP POST 요청을 받는다.[7][8]

## JSON-RPC 버전 이력: 1.0에서 2.0까지

JSON-RPC 1.0은 2005년 공개된 피어 투 피어(peer-to-peer) 원격 프로시저 호출 프로토콜로, 연결된 두 피어가 바이트 스트림 연결(TCP/IP 소켓 권장)이나 여러 번의 HTTP POST 요청을 통해 서로의 메서드를 호출하는 구조였다.[2] JSON-RPC 1.0 요청 객체는 `method`, 위치 기반 배열 전용인 `params`, 임의 JSON 자료형의 `id` 세 속성으로 이루어졌다.[2] 통지는 `id` 값을 `null`로 지정해 구분했고, 응답 객체는 항상 `result`와 `error` 속성을 모두 포함하되 쓰지 않는 쪽을 `null`로 채웠다.[2] 버전 1.0에는 기본 JSON 자료형 외의 객체를 생성자로 복원하기 위한 `__jsonclass__` 클래스 힌팅 속성도 포함되어 있었다.[2]

2009년 5월 24일 초안을 바탕으로 2010년 3월 26일 제정되고 2013년 1월 4일 갱신된 JSON-RPC 2.0은 프로토콜을 무상태 클라이언트-서버 메시지 사양으로 단순화하면서 버전 1.0과 직접 호환되지 않는 변경을 도입했다.[1] 모든 JSON-RPC 2.0 요청과 응답 객체에는 `"jsonrpc": "2.0"` 멤버가 포함되고 버전 1.0 객체에는 이 멤버가 없으므로 구현체는 두 버전을 쉽게 구분할 수 있다.[1]

| 항목 | JSON-RPC 1.0(2005년) | JSON-RPC 2.0(2010년, 2013년 갱신) |
| --- | --- | --- |
| 버전 식별자 | 없음 | `"jsonrpc": "2.0"` 멤버 필수 |
| 매개변수(`params`) | 배열만 허용(위치 기반) | 선택 사항, 배열(위치 기반) 또는 객체(이름 기반) |
| 통지 표현 | `"id": null` | `id` 멤버 생략 |
| 응답 `result` 및 `error` | 둘 다 포함, 미사용 필드는 `null` | 상호 배타적, 둘 중 하나만 존재 가능 |
| 배치 요청 | 미정의 | 요청 객체의 JSON 배열 |
| 클래스 힌팅(`__jsonclass__`) | 사양에 정의 | 사양에서 제외 |
| 통신 모델 | 스트림 또는 HTTP 기반 피어 투 피어 | 무상태 클라이언트-서버 역할, 전송 독립적 |

JSON-RPC 2.0 사양은 버전 1.0의 피어 투 피어 및 클래스 힌팅 기능까지 구현하지 않더라도 가능한 경우 1.0 객체 처리를 고려하도록 권고한다.[1] JSON-RPC 1.0은 버전 2.0 공개 이후에도 네트워크 표준에 채택됐다. 2013년 12월 IETF는 정보용(Informational) RFC 7047을 통해 오픈 v스위치 데이터베이스 관리 프로토콜(OVSDB)을 발행했으며, OVSDB는 JSON 기반 JSON-RPC 1.0을 유선 프로토콜로 사용해 가상 스위치의 브리지, 포트, 터널 인터페이스, 큐, 서비스 품질(QoS) 정책을 관리한다.[5]

## JSON-RPC 채택 사례와 OpenRPC 도구

JSON-RPC 2.0은 주요 개발 도구, AI 연동, 블록체인 프로토콜의 메시지 계층으로 쓰인다.[6][7][8] [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(MCP)은 2026-11-23 기준 최신 사양인 버전 2026-07-28에서 LLM 호스트 애플리케이션, 내부 클라이언트, 그리고 리소스(Resources)·프롬프트(Prompts)·도구(Tools)·사용자 입력 요청(Elicitation)을 제공하는 서버 사이의 통신에 JSON-RPC 2.0 메시지를 사용한다.[6] MCP는 마이크로소프트(Microsoft)가 관리하는 언어 서버 프로토콜(LSP, 2026-11-23 기준 3.17 보관, 3.18 현행, 3.19 예정)에서 영감을 받았으며, LSP 역시 코드 편집기와 언어 서버 사이에서 자동 완성, 진단, 서식 지정, 심볼 탐색 메시지를 주고받을 때 JSON-RPC 2.0을 사용한다.[6][7]

JSON-RPC 2.0은 이더리움(Ethereum) 실행 노드의 표준 클라이언트 인터페이스이기도 하다.[8][9] 모든 이더리움 실행 클라이언트는 동일한 JSON-RPC API를 제공해, 애플리케이션이 노드 구현체 종류와 관계없이 블록체인 상태를 조회하고 과거 블록과 거래 영수증을 가져오며 트랜잭션을 전송할 수 있게 한다.[8][9] 이더리움 문서는 핵심 메서드를 가십(`eth_blockNumber`, `eth_sendRawTransaction`), 상태(`eth_getBalance`, `eth_getStorageAt`, `eth_getTransactionCount`, `eth_getCode`, `eth_call`, `eth_estimateGas`), 이력(`eth_getBlockByNumber`, `eth_getTransactionReceipt`)으로 분류하며, 수량(정수)은 앞자리 0을 뺀 `"0x"` 접두사 16진수 문자열(0은 `"0x0"`)로, 비정형 바이트 배열은 1바이트당 16진수 두 자리의 짝수 길이 `"0x"` 접두사 문자열로 인코딩한다.[8] 이더리움 실행 API의 공식 사양은 CC0-1.0 라이선스의 `ethereum/execution-apis` GitHub 저장소에서 관리되며 `speccheck`과 `hive` 시뮬레이터의 `rpc-compat` 테스트 모음으로 클라이언트 준수 여부를 검증한다.[9] 이더리움 합의 클라이언트는 별도의 비콘 API(Beacon API)를 노출하고, 합의 클라이언트와 실행 클라이언트 사이의 노드 내부 통신에는 엔진 API(Engine API)가 쓰인다.[8]

JSON-RPC 2.0 인터페이스를 기계가 읽을 수 있는 형태로 기술하고 검증하기 위해 OpenRPC 사양(2026-11-23 기준 버전 1.4.x, Apache-2.0 라이선스)은 JSON-RPC 2.0 API 전용의 언어 독립적 JSON 인터페이스 기술 형식을 정의한다.[10] 관례적으로 `openrpc.json`이라는 이름을 쓰는 OpenRPC 문서에는 `openrpc`, `info`, `methods` 필드가 필수로 들어가며, 입출력 스키마 정의에는 JSON Schema Draft 07을, 설명 필드에는 GitHub Flavored [마크다운](https://mimirwiki.com/ko/wiki/markdown)(Markdown)을 지원한다.[10] OpenRPC는 JSON-RPC 2.0의 예약 접두사 `rpc.`를 활용한 서비스 탐색 메서드 `rpc.discover`도 규정해 실행 시점에 API의 OpenRPC 스키마를 반환할 수 있게 한다.[1][10] `ethereum/execution-apis` 프로젝트는 여러 OpenRPC YAML 파일로 JSON-RPC 메서드를 작성한 뒤 검증된 단일 `openrpc.json` 문서로 컴파일한다.[9]

## 자주 묻는 질문

### JSON-RPC란 무엇인가요?

JSON-RPC는 요청, 응답, 통지, 오류 객체를 JSON으로 인코딩하는 무상태 경량 원격 프로시저 호출(RPC) 프로토콜입니다. JSON-RPC 워킹 그룹이 2010년 3월 26일 버전 2.0을 공개했고 2013년 1월 4일 문서를 마지막으로 갱신했습니다. [1]

### JSON-RPC 2.0의 통지는 일반 요청과 어떻게 다른가요?

JSON-RPC 2.0의 일반 요청에는 서버가 응답 객체를 호출과 짝지을 수 있도록 id 멤버가 들어갑니다. 통지(Notification)는 id 멤버를 생략한 요청 객체이며, 배치 안에 포함된 경우에도 서버는 통지에 응답을 보내지 않아야 합니다. [1]

### JSON-RPC 2.0의 예약 오류 코드는 무엇인가요?

JSON-RPC 2.0은 사전 정의된 프로토콜 오류용으로 -32768부터 -32000까지의 정수 코드를 예약합니다. 구체적으로 -32700은 Parse error, -32600은 Invalid Request, -32601은 Method not found, -32602는 Invalid params, -32603은 Internal error이며, -32000부터 -32099까지는 구현체가 정의하는 서버 오류용입니다. [1]

### JSON-RPC 2.0을 쓰려면 반드시 HTTP를 사용해야 하나요?

아닙니다. JSON-RPC 2.0은 전송 프로토콜에 독립적이며 JSON 데이터 구조와 처리 규칙만 정의하므로 HTTP, 소켓, 단일 프로세스 내부, 기타 메시지 전달 환경에서 동작합니다. [1]

### JSON-RPC 1.0과 JSON-RPC 2.0은 무엇이 달라졌나요?

JSON-RPC 2.0은 필수 "jsonrpc": "2.0" 버전 필드, JSON 객체를 이용한 이름 기반 매개변수, 배치 요청 배열, 서로 배타적인 result와 error 응답 필드를 도입했습니다. 또한 통지 표시 방식을 "id": null에서 id 생략으로 바꾸고 버전 1.0의 __jsonclass__ 클래스 힌팅을 제외했습니다. [1][2]

### 어떤 주요 프로토콜과 사양이 JSON-RPC를 사용하나요?

모델 컨텍스트 프로토콜(MCP), 언어 서버 프로토콜(LSP), 이더리움 실행 클라이언트 API가 JSON-RPC 2.0을 사용하며, 오픈 v스위치 데이터베이스 관리 프로토콜(RFC 7047)은 JSON-RPC 1.0을 사용합니다. OpenRPC는 JSON-RPC 2.0 API 전용의 기계 판독용 인터페이스 기술 형식을 제공합니다. [5][6][7][8][10]

## 인용 문장

- JSON-RPC 2.0은 2009년 5월 24일 초안을 바탕으로 2010년 3월 26일 공개됐고 2013년 1월 4일 마지막으로 갱신됐다. [1]
- 모든 JSON-RPC 2.0 요청 객체와 응답 객체에는 값이 정확히 "2.0"인 문자열 멤버 "jsonrpc"가 반드시 들어가야 한다. [1]
- JSON-RPC 2.0 응답 객체는 "result" 멤버와 "error" 멤버 가운데 하나를 반드시 포함해야 하며 둘을 함께 포함할 수 없다. [1]
- JSON-RPC 2.0은 사전 정의된 프로토콜 오류용으로 정수 코드 -32768부터 -32000까지를 예약하고, 이 가운데 -32000부터 -32099까지를 구현체 정의 서버 오류용으로 배정한다. [1]
- JSON-RPC 2.0에서 "rpc."로 시작하는 메서드 이름은 선택적 시스템 확장용으로 예약되어 있으며 OpenRPC의 서비스 탐색 메서드 "rpc.discover"가 이를 사용한다. [1][10]
- IETF는 2017년 12월 RFC 8259를 발행해 RFC 7159와 RFC 4627을 대체하는 JSON 데이터 교환 형식 표준을 확정했다. [4]
- 모델 컨텍스트 프로토콜(버전 2026-07-28)과 언어 서버 프로토콜(버전 3.17)은 모두 JSON-RPC 2.0을 기본 메시지 형식으로 사용한다. [6][7]
- 이더리움 실행 클라이언트는 CC0-1.0 라이선스의 ethereum/execution-apis 저장소에 OpenRPC 형식으로 기술된 표준 JSON-RPC 2.0 API를 구현한다. [8][9]

## 연표

- 2005: JSON-RPC.ORG가 스트림 연결과 HTTP 기반의 피어 투 피어 원격 프로시저 호출을 정의한 JSON-RPC 1.0 사양을 공개한다. [2]
- 2008-01-15: 제프리 대믹과 JSON-RPC 워킹 그룹이 버전 1.2용 역사적 초안인 JSON-RPC over HTTP 확장을 작성한다. [3]
- 2009-05-24: JSON-RPC 워킹 그룹이 이후 JSON-RPC 2.0의 토대가 된 초안 버전을 만든다. [1]
- 2010-03-26: JSON-RPC 워킹 그룹이 JSON-RPC 2.0 사양을 공개한다. [1]
- 2013-01-04: JSON-RPC 워킹 그룹이 JSON-RPC 2.0 사양 문서의 마지막 기록 갱신을 발표한다. [1]
- 2013-12: IETF가 JSON-RPC 1.0 기반의 오픈 v스위치 데이터베이스 관리 프로토콜(OVSDB)을 정의한 정보용 RFC 7047을 발행한다. [5]
- 2017-12: IETF가 RFC 7159와 RFC 4627을 대체하는 표준 트랙 JSON 사양 RFC 8259를 발행한다. [4]
- 2026-07-28: 모델 컨텍스트 프로토콜 프로젝트가 JSON-RPC 2.0 메시지를 사용하는 사양 버전 2026-07-28을 공개한다. [6]

## 출처

1. JSON-RPC 2.0 Specification. JSON-RPC Working Group. 게시일 2010-03-26. https://www.jsonrpc.org/specification (확인일 2026-11-23; tier 3: official site)
2. JSON-RPC 1.0 Specification (2005). JSON-RPC Working Group. 게시일 2005. https://www.jsonrpc.org/specification_v1 (확인일 2026-11-23; tier 3: official site)
3. JSON-RPC over HTTP. JSON-RPC Working Group. 게시일 2008-01-15. https://www.jsonrpc.org/historical/json-rpc-over-http.html (확인일 2026-11-23; tier 3: official site)
4. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 게시일 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (확인일 2026-11-23; tier 1: government or public registry)
5. RFC 7047: The Open vSwitch Database Management Protocol. Internet Engineering Task Force (IETF). 게시일 2013-12. https://www.rfc-editor.org/rfc/rfc7047.txt (확인일 2026-11-23; tier 1: government or public registry)
6. Specification - Model Context Protocol. Model Context Protocol project. 게시일 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28 (확인일 2026-11-23; tier 3: official site)
7. Language Server Protocol Specification - 3.17. Microsoft (LSP). https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/ (확인일 2026-11-23; tier 3: official site)
8. JSON-RPC API | ethereum.org. ethereum.org. https://ethereum.org/developers/docs/apis/json-rpc/ (확인일 2026-11-23; tier 3: official site)
9. GitHub - ethereum/execution-apis: Collection of APIs provided by Ethereum execution layer clients · GitHub. Ethereum (GitHub). https://github.com/ethereum/execution-apis (확인일 2026-11-23; tier 3: official site)
10. OpenRPC Specification | spec. OpenRPC. https://spec.open-rpc.org/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "JSON-RPC." 버전 f1db796d, 2026-11-23. https://mimirwiki.com/ko/wiki/json-rpc
