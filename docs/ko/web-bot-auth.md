---
title: "Web Bot Auth"
subtitle: "RFC 9421 HTTP 메시지 서명을 기반으로 자동화 클라이언트와 AI 에이전트를 암호화 방식으로 인증하는 프로토콜"
canonical_url: https://mimirwiki.com/ko/wiki/web-bot-auth
language: ko
page_class: anchor
revision_sha256: bc811f6c0c5b1e7ef909f349ff01e1fc6cb3f7cbe8ba162648475fa600578d90
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/web-bot-auth.md
  txt: https://mimirwiki.com/ko/wiki/web-bot-auth.txt
  json: https://mimirwiki.com/ko/wiki/web-bot-auth.json
  jsonld: https://mimirwiki.com/ko/wiki/web-bot-auth.jsonld
translations:
  en: https://mimirwiki.com/wiki/web-bot-auth
  ja: https://mimirwiki.com/ja/wiki/web-bot-auth
  zh: https://mimirwiki.com/zh/wiki/web-bot-auth
  es: https://mimirwiki.com/es/wiki/web-bot-auth
---

# Web Bot Auth

> Web Bot Auth는 RFC 9421 HTTP 메시지 서명(HTTP Message Signatures)을 기반으로 크롤러와 AI 에이전트를 포함한 자동화 HTTP 클라이언트를 인증하는 암호화 프로토콜이다. 클라이언트는 개인 키로 발신 요청에 서명하고 보통 /.well-known/http-message-signatures-directory에 위치한 JWKS 디렉터리에 공개 키를 게시하며, 서버는 이 디렉터리로 신원을 검증한다. IETF webbotauth 워킹그룹이 이 명세를 개발하고 있다.

Web Bot Auth는 웹 크롤러나 AI 에이전트 같은 자동화 HTTP 클라이언트가 RFC 9421 HTTP 메시지 서명(HTTP Message Signatures)으로 발신 요청에 서명해 웹 서버가 신원을 검증할 수 있게 하는 암호화 인증 프로토콜이다. 자동화 클라이언트는 요청에 Signature, Signature-Input, Signature-Agent 헤더를 첨부하고, 보통 웰노운 URI(Well-Known URI)인 /.well-known/http-message-signatures-directory 경로에서 HTTPS로 제공하는 JSON 웹 키 집합(JSON Web Key Set, JWKS) 디렉터리에 공개 서명 키를 게시한다. 국제 인터넷 표준화 기구(IETF)의 Web Bot Auth(webbotauth) 워킹그룹은 Cloudflare의 티보 뫼니에(Thibault Meunier)와 Google의 산도르 메이저(Sandor Major)가 작성한 draft-ietf-webbotauth-httpsig-protocol을 통해 표준 트랙 명세를 개발하고 있다. Cloudflare는 2025년 7월 Ed25519 서명 키 기반의 Web Bot Auth를 검증된 봇 프로그램(Verified Bots Program)에 추가했다.

**다른 이름:** 웹 봇 인증, webbotauth, HTTP Message Signatures for Automated Traffic, RFC 9421 Web Bot Auth

## 핵심 정보

- **기반 표준:** RFC 9421(HTTP 메시지 서명, 2024년 2월) [1]
- **표준화 기구:** IETF Web Bot Auth(webbotauth) 워킹그룹 [2]
- **진행 중인 명세:** draft-ietf-webbotauth-httpsig-protocol-01(2026-10-29) (기준 2026-11-23) [4]
- **웰노운 키 디렉터리:** /.well-known/http-message-signatures-directory [9]
- **주요 HTTP 헤더:** Signature, Signature-Input, Signature-Agent [9]

## 기본 정보

- **유형:** 자동화 클라이언트를 위한 암호화 기반 HTTP 인증 프로토콜 [5]
- **기반 표준:** RFC 9421: HTTP 메시지 서명(2024년 2월) [1]
- **워킹그룹:** IETF Web Bot Auth(webbotauth), 웹 및 인터넷 전송(wit) 영역 (기준 2026-11-23) [2]
- **워킹그룹 의장:** 데이비드 시나지(David Schinazi), 리파트 셰흐-유세프(Rifaat Shekh-Yusef) (기준 2026-11-23) [2]
- **명세 작성자:** 티보 뫼니에(Thibault Meunier, Cloudflare), 산도르 메이저(Sandor Major, Google) (기준 2026-11-23) [4]
- **현재 초안:** draft-ietf-webbotauth-httpsig-protocol-01(2026-10-29 게시) (기준 2026-11-23) [4]
- **키 디렉터리 경로:** /.well-known/http-message-signatures-directory [9]
- **디렉터리 미디어 유형:** application/http-message-signatures-directory+json [4]
- **Cloudflare 지원 알고리즘:** Ed25519(OKP JSON 웹 키) (기준 2026-10-08) [9]
- **표준화 지위:** 진행 중인 IETF 인터넷 초안(표준 트랙 예정) (기준 2026-11-23) [4]
- **참조 저장소:** github.com/cloudflare/web-bot-auth(Apache-2.0 라이선스) [12]

## Web Bot Auth란

Web Bot Auth는 검색 색인 크롤러, 웹 아카이버, 링크 검사기, AI 학습 크롤러, 최종 사용자를 대리하는 AI 에이전트 같은 자동화 HTTP 클라이언트를 암호화 방식으로 인증하기 위한 프로토콜이다.[2][5] 이 프로토콜은 2024년 2월 발행된 IETF 표준 트랙 명세인 RFC 9421 HTTP 메시지 서명(HTTP Message Signatures)을 기반으로 하며, HTTP 메시지의 선택된 구성 요소에 분리형 디지털 서명(detached digital signature)을 생성하고 검증한다.[1][4] Web Bot Auth는 전송 계층이나 전송 계층 보안(Transport Layer Security, TLS) 스택을 변경하지 않고 HTTP 계층에서만 동작하므로, 역방향 프록시(reverse proxy)나 게이트웨이 같은 HTTP 중개자를 거친 뒤에도 서명을 끝까지 검증할 수 있다.[1][5]

기존의 봇 식별 방식에는 운영 및 보안 측면의 제약이 따른다.[2][5] `User-Agent` 문자열은 임의의 클라이언트가 위조할 수 있으며, Chromium 기반 자동화 브라우저가 정상적인 렌더링을 위해 일반 브라우저 문자열을 보내야 하는 상황에서는 용도가 겹친다.[5] IP 주소 허용 목록은 클라우드 플랫폼의 다층적인 주소 소유 구조 때문에 관리가 복잡하며, 전용 IP 대역을 확보하는 데는 비용과 전문 설정, 기존 평판 이력 확인이 필요하다.[5] OAuth 베어러 토큰(Bearer token) 같은 공유 비밀(shared secret) 방식은 사이트별 사전 등록이 필요하고 대규모 환경에서 키 교체가 어렵다.[5]

`draft-ietf-webbotauth-httpsig-protocol`은 Web Bot Auth의 목표 두 가지와 제약 두 가지를 명시한다.[5] 목표는 요청 전반에 걸친 봇 신뢰의 연속성 확보와 도메인 이름 같은 외부 앵커에 대한 선택적 키 바인딩이다.[5] 제약은 자동화 클라이언트와 웹사이트 양쪽의 운영을 단순하게 유지하는 것과 클라이언트와 원본 서버 사이에 사전 관계가 필요 없도록 하는 것이다.[5] Cloudflare는 2025년 5월 15일 이 방식을 공개 제안했고, 2025년 7월 1일 검증된 봇 프로그램(Verified Bots Program)에 HTTP 메시지 서명을 추가했다.[10][11]

## Web Bot Auth의 HTTP 요청 서명과 검증 방식

Web Bot Auth는 RFC 9421에 정의된 분리형 서명을 사용해 메시지 헤더를 별도 토큰 페이로드에 중복 포함하지 않고 발신 HTTP 요청을 인증한다.[1][5] 자동화 클라이언트는 HTTP 헤더 필드와 파생 구성 요소(derived component)를 선택한 뒤 RFC 9421 규칙에 따라 정규화된 서명 기준 문자열(signature base)을 만들고, 봇 제공자가 보유한 개인 키로 디지털 서명을 계산한다.[1][5] RFC 9421은 SHA-512 기반 RSASSA-PSS, SHA-256 기반 RSASSA-PKCS1-v1_5, SHA-256 기반 HMAC, P-256 및 P-384 곡선 기반 ECDSA, edwards25519 곡선 기반 EdDSA(Ed25519) 알고리즘을 정의한다.[1] `draft-ietf-webbotauth-httpsig-protocol-01`의 테스트 벡터는 SHA-512 기반 RSASSA-PSS와 Ed25519를 다루며, Cloudflare의 프로덕션 구현은 Ed25519를 지원한다.[4][9]

서명된 요청은 세 가지 주요 HTTP 헤더 필드를 포함한다.[1][9] `Signature-Input` 헤더는 서명 대상 구성 요소와 서명 메타데이터 매개변수를 나열하고, `Signature` 헤더는 Base64로 인코딩된 서명 바이트를 담으며, `Signature-Agent` 헤더는 클라이언트의 공개 키 디렉터리를 가져올 HTTPS URL을 가리킨다.[1][4][5][9] RFC 9421 서명은 HTTP 메시지 본문을 직접 포함하지 않으므로 본문 무결성이 필요한 애플리케이션은 콘텐츠의 암호화 해시를 담은 `Content-Digest` 헤더를 함께 사용한다.[1][9] RFC 9421은 수신자가 후속 HTTP 메시지에 서명을 요청할 수 있는 선택적 `Accept-Signature` 헤더도 정의한다.[1]

`Signature-Input`의 표준 메타데이터 매개변수는 서명 범위와 유효 기간을 제한한다.[1][5][9]

| 매개변수 또는 헤더 | Web Bot Auth에서의 역할 |
| --- | --- |
| `Signature-Agent` | 대역 내(in-band) 키 탐색을 위해 클라이언트의 공개 키 디렉터리 HTTPS URL을 전달한다.[4][5] |
| `Signature-Input` | 서명 대상 HTTP 구성 요소(예: `@authority`와 `signature-agent`)와 서명 메타데이터를 나열한다.[1][9] |
| `Signature` | 정규화된 서명 기준 문자열에 대한 분리형 암호화 서명을 담는다.[1][9] |
| `tag` | 애플리케이션 맥락을 식별하며, Cloudflare 구현에서는 봇 요청에 `web-bot-auth`를, 서명된 디렉터리 응답에 `http-message-signatures-directory`를 사용한다.[9] |
| `keyid` | 서명 검증에 사용할 공개 키를 지정하는 Base64URL 인코딩 JSON 웹 키(JSON Web Key, JWK) 썸프린트를 담는다.[5][9] |
| `created` 및 `expires` | 재전송 공격(replay attack) 노출 시간을 제한하기 위해 서명 유효 기간을 유닉스 타임스탬프로 지정한다.[5][9] |
| `nonce` | 재전송 공격 완화를 목적으로 요청마다 부여하는 선택적 값을 제공한다.[9] |

## Web Bot Auth의 키 디렉터리와 신뢰 모델

Web Bot Auth는 HTTPS로 제공되는 JSON 웹 키 집합(JSON Web Key Set, JWKS) 디렉터리에 공개 서명 키를 게시해 검증자가 `Signature-Agent` 헤더로부터 대역 내에서 키를 탐색할 수 있게 한다.[4][5][6] 초기 개인 초안인 `draft-meunier-http-message-signatures-directory`(2026년 3월 2일 개정판 05까지 갱신)는 이 디렉터리 형식을 별도로 규정했으나, 이후 워킹그룹이 키 탐색 메커니즘을 `draft-ietf-webbotauth-httpsig-protocol`로 통합했다.[3][4][6] 이 초안은 미디어 유형 `application/http-message-signatures-directory+json`과 웰노운 URI(Well-Known URI) `/.well-known/http-message-signatures-directory`를 등록한다.[4] RFC 8615에 따라 `/.well-known/` 경로 접두사는 HTTP 및 HTTPS 오리진의 최상위 경로에 예약되므로, 이 경로에 키 디렉터리를 호스팅하면 해당 키 집합이 도메인 운영자와 연결된다.[5][7]

`draft-ietf-webbotauth-httpsig-protocol-01`이 정의한 신뢰 모델에서는 검증된 `Signature-Agent` HTTPS URL이 에이전트의 지속적 식별자 역할을 한다.[5] 아직 조회되지 않은 `Signature-Agent` 헤더는 확인되지 않은 주장이므로, 검증자는 TLS를 통해 해당 URL을 조회하고 반환된 키로 요청 서명을 검증한 뒤에만 접근 정책을 적용해야 한다.[5] 식별자가 URL에 연결되고 `keyid`는 개별 키를 선택하는 역할을 맡기 때문에, 운영자는 기존 키와 함께 새 키를 게시한 뒤 나중에 기존 키를 제거하는 방식으로 식별 연속성을 유지하며 키를 교체할 수 있다.[5] 조회된 URL 없이 검증자가 키를 직접 보유한 경우에는 `keyid` 썸프린트까지만 귀속이 가능하며, 이 방식에서는 키 교체 간 연속성이 유지되지 않는다.[5]

TLS를 통해 키 디렉터리를 조회하면 해당 URL의 호스트가 조회 시점에 그 키 집합을 제공했다는 사실이 확인되며, 유효한 요청 서명은 그 키 중 하나를 보유한 주체가 서명 대상 구성 요소에 서명했음을 증명한다.[5] 제3자가 다른 운영자의 디렉터리를 복제해 키를 도용 등록하는 행위를 막기 위해, 디렉터리 응답 자체에도 목록의 각 개인 키 소유를 증명하는 HTTP 메시지 서명을 첨부할 수 있다.[4][9] 검증자가 여러 출처에서 동일한 디렉터리 쌍을 얻은 경우에는 디렉터리 응답 서명의 `created` 타임스탬프나 검증자의 직접 조회 시각을 기준으로 더 최신인 정보가 우선한다.[5] 서명 검증은 암호화 연속성과 키 소유를 증명하며, 운영자의 신뢰 여부나 요청의 인가 여부는 원본 서버의 정책 판단으로 남는다.[5]

## IETF Web Bot Auth 표준화 현황

Web Bot Auth는 국제 인터넷 표준화 기구(IETF) 웹 및 인터넷 전송(Web and Internet Transport, wit) 영역 산하의 Web Bot Auth(`webbotauth`) 워킹그룹에서 표준화가 진행되고 있다.[2] 2026-11-23 기준 이 워킹그룹은 승인된 헌장 `charter-ietf-webbotauth-01` 아래 활동 중이며, 데이비드 시나지(David Schinazi)와 리파트 셰흐-유세프(Rifaat Shekh-Yusef)가 의장을, 마이크 비숍(Mike Bishop)이 영역 이사(Area Director)를 맡고 있다.[2] 헌장은 세 가지 산출물 범주를 정하고 있다. 사람용 웹사이트에 대한 자동화 클라이언트 인증 표준 트랙 문서, 도메인 이름이나 URL 같은 기존 식별자를 통해 요청 봇의 추가 정보를 전달하는 표준 트랙 문서, 그리고 수명 주기 관리와 키 관리, 배포 고려사항 및 웹 개방성에 미치는 영향을 다루는 최선 운영 관행(Best Current Practice) 또는 정보성(Informational) 문서다.[2] 워킹그룹은 AIPREF, HTTPBIS, OAUTH, TLS, WIMSE 워킹그룹과 협력한다.[2]

2026-11-23 기준 워킹그룹이 채택한 공식 워킹그룹 인터넷 초안은 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)의 티보 뫼니에와 Google의 산도르 메이저가 작성한 `draft-ietf-webbotauth-httpsig-protocol-01`("HTTP Message Signatures for automated traffic") 한 건이다.[3][4][5] 2026년 10월 29일 게시되고 2027년 5월 2일 만료 예정인 44쪽 분량의 개정판 `-01`은 초기 개인 초안 시리즈인 `draft-meunier-webbotauth-httpsig-protocol`을 대체하며, 그 이전에는 2026년 3월 2일 갱신된 `draft-meunier-web-bot-auth-architecture-05`가 사용됐다.[3][4][5] 헌장 마일스톤은 인증 기법 및 봇 추가 정보 전달용 표준 트랙 명세의 IESG 제출 시한을 2026년 4월로, 최선 운영 관행 운영 명세의 제출 시한을 2026년 8월로 기재하고 있다.[2]

채택된 프로토콜 초안과 함께 2026-11-23 기준 `webbotauth` 문서 페이지에는 14건의 관련 개인 인터넷 초안이 등재되어 있다.[3] 이 제안들은 봇 레지스트리와 서명 에이전트 카드(`draft-meunier-webbotauth-registry-04`), 서명된 에이전트 메타데이터 헤더(`draft-vilgalys-webbotauth-signed-agent-metadata-00`), 호스팅 키 디렉터리(`draft-singh-webbotauth-hosted-directories-00`), 익명 봇 인증(`draft-rescorla-anonymous-webbotauth-01`), 검증 결과 보고(`draft-suresh-webbotauth-verification-outcome-00`), 크롤러 모범 사례(`draft-illyes-webbotauth-cbcp-01`), JSON 기반 IP 대역 게시(`draft-illyes-webbotauth-jafar-01`) 같은 보완 메커니즘을 다룬다.[3] 이 문서들은 모두 작업 중인 인터넷 초안이며 아직 공식 IETF RFC 지위를 갖지 않는다.[5][6]

## Cloudflare의 Web Bot Auth 구현과 도구

Web Bot Auth는 2025년 7월 1일 HTTP 메시지 서명을 도입한 Cloudflare의 검증된 봇 프로그램에서 프로덕션 환경에 적용되어 있다.[9][10] 2026년 10월 8일 갱신된 Cloudflare 개발자 문서에 따르면 등록 절차는 네 단계로 구성된다. Ed25519 키 쌍을 생성해 공개 키를 JWK(`kty: "OKP"`, `crv: "Ed25519"`, 패딩 없는 Base64URL 인코딩 `x`)로 변환하고, `/.well-known/http-message-signatures-directory` 경로에서 HTTPS로 서명된 JWKS 디렉터리를 호스팅하며, Cloudflare 대시보드에서 검증 방식으로 `Request Signature`를 선택해 봇과 디렉터리 URL을 등록한 뒤, 발신 요청에 서명을 첨부하는 순서다.[9] 디렉터리 응답은 `Content-Type: application/http-message-signatures-directory+json` 헤더를 설정하고, `@authority;req`와 `tag="http-message-signatures-directory"`, `keyid`, `created`, `expires`를 포함하는 HTTP 메시지 서명을 Ed25519 키마다 하나씩 첨부해야 한다.[9]

2026년 10월 8일 기준 Cloudflare의 요청 검증은 이전 초안 버전(`draft-meunier-web-bot-auth-architecture-02` 및 `draft-meunier-http-message-signatures-directory-03`)을 따르며 몇 가지 구현 제약이 있다.[9] 발신 요청은 `https://` URI를 큰따옴표로 감싼 구조화 문자열 형식의 `Signature-Agent` 헤더를 포함해야 하고, `Signature-Input`에 `signature-agent`와 최소한 `@authority`를 넣어야 하며, ASCII 값만 사용하는 구성 요소와 `tag="web-bot-auth"`를 지정해야 한다.[9] Cloudflare는 이후 초안에 도입된 딕셔너리 형식의 `Signature-Agent` 구문을 거부하며, `@query-params`와 `@status`를 지원하지 않고, `Signature-Input`에 RFC 9421 구성 요소 매개변수인 `sf`, `bs`, `key`, `req`, `name`이 포함되면 검증에 실패한다.[9] Cloudflare는 `nonce` 포함을 권장하지만 2026년 10월 8일 기준 수신된 논스를 검증하거나 데이터베이스에 저장해 재전송을 차단하지 않으며, 재전송 노출 기간을 줄이기 위해 1분 정도의 짧은 `expires` 간격 사용을 권장한다.[9] 운영자는 `https://crawltest.com/cdn-cgi/web-bot-auth` 테스트 엔드포인트에서 요청 형식과 검증 결과를 확인할 수 있으며, 알려진 키로 서명 검증에 성공하면 HTTP 200을, 키가 등록되지 않았거나 검증에 실패하면 HTTP 401을, 형식이 잘못되면 HTTP 400을 반환받는다.[9]

Cloudflare는 중개자를 거치는 환경에서 봇 운영자 신원과 콘텐츠 사용 목적을 전달하기 위해 RFC 7239 `Forwarded` 헤더(문서 예시 구문: `Forwarded: for="openai";use="reference"`)를 활용하는 실험적 전이 신뢰(transitive trust) 기능도 문서화하고 있으며, 이 기능은 변경될 수 있다고 명시한다.[9] 원본 서버에서 직접 서명을 검증하고자 하는 사이트 소유자는 Cloudflare 지원팀에 해당 영역(zone)의 Cloudflare 측 검증 비활성화를 요청해 `cf.bot_management.verified_bot` 필드가 채워지지 않도록 할 수 있으며, 이 경우 검증된 봇은 역방향 DNS 조회 같은 기존 방식으로 전환된다.[9]

Cloudflare는 Apache-2.0 라이선스의 공개 저장소 `github.com/cloudflare/web-bot-auth`에서 TypeScript 패키지(`http-message-sig`, `jsonwebkey-thumbprint`, `web-bot-auth`)와 Rust 크레이트(`web-bot-auth`, `http-signature-directory`)를 관리하며, 2026-11-23 기준 이 저장소는 스타 188개와 포크 52개를 기록하고 있다.[12] 저장소에는 브라우저 확장 프로그램, Rust, Caddy 플러그인, Cloudflare Workers용 서명 및 검증 예제가 포함되어 있으며, Cloudflare Research는 `http-message-signatures-example.research.cloudflare.com`에서 실시간 테스트 환경을 운영한다.[12] 저장소 문서는 이 소프트웨어가 보안 감사를 받지 않았다고 안내한다.[12]

## Web Bot Auth의 적용 범위, 보안 고려사항과 한계

Web Bot Auth는 주로 사람을 대상으로 하는 웹 콘텐츠에 접근하는 자동화 HTTP 클라이언트의 암호화 인증을 다루며, IETF `webbotauth` 워킹그룹 헌장은 여러 인접 영역을 범위 밖으로 명시한다.[2] 범위 밖 항목에는 기계용 HTTP API나 에이전트 간 인터페이스 접근 인증, 에이전트 뒤의 최종 사용자 인증, HTTP 이외의 애플리케이션 프로토콜 인증, 비암호화 식별 방식, 봇 의도 어휘 정의, 특정 봇에 대한 평판 추적 및 부여, 참여하지 않는 봇과 비봇 클라이언트 구분 기법이 포함된다.[2] 또한 Web Bot Auth는 2022년 9월 RFC 9309로 표준화된 로봇 배제 프로토콜([robots.txt](https://mimirwiki.com/ko/wiki/robots-txt))과 목적이 다르며, RFC 9309는 `user-agent` 토큰별 자발적 크롤링 규칙을 정의하면서 해당 규칙이 접근 인가 수단이 아님을 명시하고 있다.[8]

Web Bot Auth의 암호화 검증에는 명확한 보안 경계가 존재한다.[5] 유효한 서명은 조회된 `Signature-Agent` URL에 게시된 키로 요청이 서명됐다는 사실만을 확인하며, 운영자가 선의인지 또는 해당 요청이 인가됐는지까지는 보증하지 않는다.[5] 프로토콜은 클라이언트가 기존 URL을 버리고 새 URL을 생성하는 행위를 막지 않으며, 여러 요청에 걸쳐 지속적으로 식별되기를 원하는 운영자를 대상으로 설계됐다.[5] 또한 서명된 요청은 유효 기간 내에서 재전송될 수 있으므로, 운영자는 서명 대상 구성 요소 선택과 짧은 `created` 및 `expires` 간격으로 재전송 범위와 기간을 제한한다.[5][9]

대역 내 키 탐색의 도입은 `draft-ietf-webbotauth-httpsig-protocol-01`의 보안 및 개인정보 고려사항에서 다루는 운영 위험을 수반한다.[4] 검증자가 수신 요청에 적힌 임의의 `Signature-Agent` HTTPS URL을 조회하므로, 서버는 서버 측 요청 위조(Server-Side Request Forgery, SSRF)를 방지하고 디렉터리 조회 자원과 캐싱 동작에 상한을 두어야 한다.[4] 명세는 TLS 사용, 키 유출 대응, 공유 비밀 및 키 재사용 지양, 테스트 키와 정적 서명 처리, 역방향 프록시 고려사항, 그리고 클라이언트 식별 및 상관관계 분석과 디렉터리 접근 패턴에 따른 개인정보 영향도 다룬다.[4] 아울러 `webbotauth` 헌장은 봇 클라이언트와 웹사이트에 추가되는 운영 부담을 고려하고 구조적 병목이 생기지 않도록 주의할 것을 요구한다.[2]

## 자주 묻는 질문

### Web Bot Auth란 무엇인가요?

Web Bot Auth는 웹 크롤러나 AI 에이전트 같은 자동화 클라이언트가 RFC 9421 HTTP 메시지 서명을 사용해 발신 요청에 암호화 서명을 붙이는 HTTP 계층 인증 프로토콜입니다. 서버는 JSON 웹 키 집합 디렉터리에 게시된 공개 키로 이 서명을 검증합니다. [1][4][5]

### Web Bot Auth에서 서버는 봇의 공개 키를 어떻게 찾나요?

서명된 요청에는 봇의 키 디렉터리 HTTPS URL을 담은 Signature-Agent 헤더가 포함됩니다. 서버는 보통 /.well-known/http-message-signatures-directory에 호스팅된 해당 URL에서 JSON 웹 키 집합을 가져오고, keyid 썸프린트 매개변수로 일치하는 키를 선택합니다. [4][5][9]

### Web Bot Auth는 공식 IETF RFC 표준인가요?

2026-11-23 기준 Web Bot Auth는 IETF Web Bot Auth(webbotauth) 워킹그룹에서 표준화가 진행 중인 프로토콜입니다. 핵심 명세인 draft-ietf-webbotauth-httpsig-protocol-01은 2026년 10월 29일 게시된 표준 트랙 인터넷 초안이며 아직 RFC로 발행되지 않았습니다. [2][4][5]

### Cloudflare는 Web Bot Auth에서 어떤 암호화 키를 지원하나요?

2026년 10월 8일 기준 Cloudflare의 Web Bot Auth 연동은 /.well-known/http-message-signatures-directory에 OKP JSON 웹 키 형식으로 게시된 Ed25519 서명 키를 지원합니다. 디렉터리 응답에는 각 Ed25519 키의 소유를 증명하는 HTTP 메시지 서명이 포함되어야 합니다. [9]

### Web Bot Auth는 봇 식별자를 유지하면서 어떻게 키를 교체하나요?

draft-ietf-webbotauth-httpsig-protocol-01에서는 검증된 Signature-Agent HTTPS URL이 에이전트의 식별자 역할을 하고 keyid가 개별 키를 선택합니다. 운영자는 디렉터리에 새 공개 키를 기존 키와 함께 게시한 뒤 나중에 기존 키를 제거함으로써 동일한 URL 아래에서 식별 연속성을 유지합니다. [5]

### Web Bot Auth가 robots.txt를 대체하거나 최종 사용자를 인증하나요?

아닙니다. 로봇 배제 프로토콜(RFC 9309)은 자발적인 크롤러 접근 규칙을 정의하고, Web Bot Auth는 자동화 클라이언트의 신원을 암호화 방식으로 검증합니다. 또한 IETF webbotauth 워킹그룹 헌장은 클라이언트나 에이전트의 최종 사용자 인증을 범위 밖으로 명시하고 있습니다. [2][8]

## 인용 문장

- Web Bot Auth는 2024년 2월 발행된 RFC 9421(HTTP 메시지 서명)에 정의된 분리형 디지털 서명을 사용해 자동화 HTTP 요청을 인증한다. [1][4]
- 2026-11-23 기준 IETF Web Bot Auth(webbotauth) 워킹그룹은 승인된 헌장 charter-ietf-webbotauth-01 아래 웹 및 인터넷 전송(wit) 영역에서 활동하고 있다. [2]
- 채택된 워킹그룹 초안 draft-ietf-webbotauth-httpsig-protocol-01은 Cloudflare의 티보 뫼니에(Thibault Meunier)와 Google의 산도르 메이저(Sandor Major)가 작성해 2026년 10월 29일 게시했다. [4][5]
- draft-ietf-webbotauth-httpsig-protocol-01에서는 검증된 Signature-Agent HTTPS URL이 에이전트의 식별자 역할을 하며, 식별 연속성을 유지한 채 키를 교체할 수 있게 한다. [5]
- draft-ietf-webbotauth-httpsig-protocol-01은 JWKS 키 디렉터리 게시를 위해 웰노운 URI /.well-known/http-message-signatures-directory와 미디어 유형 application/http-message-signatures-directory+json을 정의한다. [4][7]
- Cloudflare는 2025년 7월 1일 검증된 봇 프로그램(Verified Bots Program)에 HTTP 메시지 서명(Web Bot Auth)을 추가했다. [10]
- 2026년 10월 8일 기준 Cloudflare의 Web Bot Auth 구현은 Ed25519 키를 지원하며 /.well-known/http-message-signatures-directory 경로에서 HTTPS로 서명된 디렉터리 응답을 제공할 것을 요구한다. [9]
- Cloudflare는 Apache-2.0 라이선스의 github.com/cloudflare/web-bot-auth 저장소에서 TypeScript 및 Rust용 Web Bot Auth 라이브러리와 예제를 관리한다. [12]

## 연표

- 2024-02: IETF가 RFC 9421(HTTP 메시지 서명)을 표준 트랙 명세로 발행한다. [1]
- 2025-05-15: Cloudflare가 티보 뫼니에와 마리 갈리세르(Mari Galicer) 명의로 암호화 HTTP 서명을 이용한 봇 및 AI 에이전트 트래픽 검증 제안을 공개한다. [11]
- 2025-07-01: Cloudflare가 검증된 봇 프로그램에 HTTP 메시지 서명을 추가한다. [10]
- 2026-03-02: 티보 뫼니에와 산도르 메이저가 draft-meunier-web-bot-auth-architecture와 draft-meunier-http-message-signatures-directory의 개정판 05를 게시하며, 두 문서는 이후 webbotauth 프로토콜 및 디렉터리 초안으로 대체된다. [3][6]
- 2026-10-08: Cloudflare가 Ed25519 키 디렉터리, 요청 서명, 실험적 RFC 7239 Forwarded 헤더 지원을 담은 Web Bot Auth 개발자 문서를 갱신한다. [9]
- 2026-10-29: IETF webbotauth 워킹그룹이 draft-ietf-webbotauth-httpsig-protocol-01(자동화 트래픽용 HTTP 메시지 서명)을 게시한다. [3][4][5]

## 출처

1. RFC 9421: HTTP Message Signatures. Internet Engineering Task Force (IETF). 게시일 2024-02. https://www.rfc-editor.org/rfc/rfc9421.txt (확인일 2026-11-23; tier 1: government or public registry)
2. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (확인일 2026-11-23; tier 1: government or public registry)
3. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/documents/ (확인일 2026-11-23; tier 1: government or public registry)
4. draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic. Internet Engineering Task Force (IETF). 게시일 2026-10-29. https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/ (확인일 2026-11-23; tier 1: government or public registry)
5. draft-ietf-webbotauth-httpsig-protocol-01. Internet Engineering Task Force (IETF). 게시일 2026-10-29. https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol (확인일 2026-11-23; tier 1: government or public registry)
6. draft-meunier-http-message-signatures-directory-05 - HTTP Message Signatures Directory. Internet Engineering Task Force (IETF). 게시일 2026-03-02. https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/ (확인일 2026-11-23; tier 1: government or public registry)
7. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 게시일 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (확인일 2026-11-23; tier 1: government or public registry)
8. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (확인일 2026-11-23; tier 1: government or public registry)
9. Web Bot Auth · Cloudflare bot solutions docs. Cloudflare. 게시일 2026-10-08. https://developers.cloudflare.com/bots/reference/bot-verification/web-bot-auth/ (확인일 2026-11-23; tier 3: official site)
10. Message Signatures are now part of our Verified Bots Program, simplifying bot authentication | Cloudflare Blog. The Cloudflare Blog. 게시일 2025-07-01. https://blog.cloudflare.com/verified-bots-with-cryptography/ (확인일 2026-11-23; tier 3: official site)
11. Forget IPs: using cryptography to verify bot and agent traffic | Cloudflare Blog. The Cloudflare Blog. 게시일 2025-05-15. https://blog.cloudflare.com/web-bot-auth/ (확인일 2026-11-23; tier 3: official site)
12. GitHub - cloudflare/web-bot-auth: Sign and verify orchestrated HTTP requests · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/web-bot-auth (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "Web Bot Auth." 버전 bc811f6c, 2026-11-23. https://mimirwiki.com/ko/wiki/web-bot-auth
