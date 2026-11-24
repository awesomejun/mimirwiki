---
title: "웰노운 URI"
subtitle: "오리진 단위의 메타데이터와 서비스 탐색을 위해 /.well-known/ 경로 접두사를 예약한 IETF 표준"
canonical_url: https://mimirwiki.com/ko/wiki/well-known-uri
language: ko
page_class: anchor
revision_sha256: 841af16fff92eba8be5b6887304969cc7738ebeb7f1bc3283d2407e288c38249
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/well-known-uri.md
  txt: https://mimirwiki.com/ko/wiki/well-known-uri.txt
  json: https://mimirwiki.com/ko/wiki/well-known-uri.json
  jsonld: https://mimirwiki.com/ko/wiki/well-known-uri.jsonld
translations:
  en: https://mimirwiki.com/wiki/well-known-uri
  ja: https://mimirwiki.com/ja/wiki/well-known-uri
  zh: https://mimirwiki.com/zh/wiki/well-known-uri
---

# 웰노운 URI

> 웰노운 URI(Well-Known URI)는 오리진 단위의 메타데이터와 서비스 탐색 경로를 제공하기 위해 /.well-known/ 접두사로 시작하는 통합 자원 식별자(URI)이다. 2019년 5월 발행된 IETF RFC 8615가 RFC 5785를 대체해 규격화했으며 HTTP, HTTPS, WS, WSS 스킴에 적용된다. IANA가 사양 필수(Specification Required) 정책으로 레지스트리를 관리하며 security.txt, acme-challenge, openid-configuration 등의 접미사가 등록되어 있다.

웰노운 URI(Well-Known URI)는 HTTP, HTTPS, WS, WSS 등 이를 지원하도록 명시적으로 정의된 URI 스킴(URI scheme)에서 경로 구성 요소가 예약 접두사인 /.well-known/으로 시작하는 통합 자원 식별자(Uniform Resource Identifier, URI)이다. 국제 인터넷 표준화 기구(Internet Engineering Task Force, IETF)가 2019년 5월 발행한 표준 트랙(Standards Track) 문서인 RFC 8615가 현행 사양이며, 2010년 4월 발행된 RFC 5785를 대체해 경로 충돌을 피하면서 오리진(origin) 단위의 메타데이터와 프로토콜 탐색 위치를 표준화한다. 국제 인터넷 주소 관리 기구(Internet Assigned Numbers Authority, IANA)는 지정 전문가(Designated Expert) 검토를 거치는 사양 필수(Specification Required) 정책으로 웰노운 URI 레지스트리를 관리하며, security.txt, acme-challenge, oauth-authorization-server, oauth-protected-resource, openid-configuration 같은 영구 및 임시 접미사를 등재한다. 웰노운 URI는 오리진 경로 계층의 최상위에서만 적용되며, 각 애플리케이션 사양이 메타데이터 형식과 미디어 유형, 적용 범위를 직접 정의한다.

**다른 이름:** Well-Known URIs, /.well-known/, Well-Known Uniform Resource Identifiers, RFC 8615, RFC 5785, .well-known

## 핵심 정보

- **현행 사양:** RFC 8615(2019년 5월, 표준 트랙) (기준 2026-11-23) [1]
- **예약 경로 접두사:** 오리진 루트의 /.well-known/ [1]
- **이전 사양:** RFC 5785(2010년 4월, RFC 8615로 대체됨) [2]
- **레지스트리:** IANA 웰노운 URI 레지스트리(2010-01-20 개설, 2026-10-26 갱신) (기준 2026-11-23) [3]
- **등록 정책:** 지정 전문가 검토를 거치는 사양 필수(RFC 8126) [1]

## 기본 정보

- **유형:** 예약 URI 경로 접두사에 관한 인터넷 표준 [1]
- **경로 접두사:** /.well-known/ [1]
- **현행 사양:** RFC 8615(2019년 5월, 표준 트랙) (기준 2026-11-23) [1]
- **작성자(RFC 8615):** 마크 노팅엄(Mark Nottingham) [1]
- **대체한 사양:** RFC 5785(2010년 4월, 마크 노팅엄·E. Hammer-Lahav) [2]
- **갱신한 사양:** RFC 7230, RFC 7595 [1]
- **지원 URI 스킴:** http, https, ws, wss 및 지원을 명시적으로 정의한 기타 스킴 [1]
- **레지스트리:** IANA Well-Known URIs(iana.org/assignments/well-known-uris) [3]
- **레지스트리 현황:** 2010-01-20 개설, 2026-10-26 마지막 갱신 (기준 2026-11-23) [3]
- **등록 정책:** 사양 필수(Specification Required) [3]
- **지정 전문가:** 마크 노팅엄(Mark Nottingham) (기준 2026-11-23) [3]
- **접미사 구문:** RFC 3986 segment-nz 규칙(/ 문자 불가) [1]

## 웰노운 URI란

웰노운 URI(Well-Known URI)는 이를 지원하도록 명시적으로 정의된 URI 스킴에서 경로 구성 요소가 `/.well-known/`으로 시작하는 통합 자원 식별자(URI)이다.[1] 국제 인터넷 표준화 기구(IETF)는 2019년 5월 마크 노팅엄(Mark Nottingham)이 작성한 표준 트랙(Standards Track) 사양인 RFC 8615를 발행했다.[1] RFC 8615는 2010년 4월 마크 노팅엄과 E. Hammer-Lahav가 `/.well-known/` 경로 접두사와 국제 인터넷 주소 관리 기구(IANA) 레지스트리를 처음 도입한 RFC 5785를 대체한다.[1][2] 또한 RFC 7230을 갱신해 `http`와 `https` URI에서 해당 접두사를 예약하고, RFC 7595를 갱신해 IANA URI 스킴 레지스트리가 웰노운 URI를 지원하는 스킴을 추적하도록 했다.[1]

웹 애플리케이션은 요청을 보내기 전에 오리진(origin) 전체에 적용되는 메타데이터를 먼저 확인해야 하는 경우가 많다. [로봇 배제 프로토콜](https://mimirwiki.com/ko/wiki/robots-txt)(Robots Exclusion Protocol)과 개인정보 보호 환경설정 플랫폼(Platform for Privacy Preferences, P3P)이 대표적인 예이다.[1][2] HTTP 헤더 필드나 WebDAV PROPFIND 같은 리소스별 메타데이터 방식은 이런 상황에서 클라이언트 지연 시간이나 배포 부담을 키울 수 있다.[1][2] 비웹(non-Web) 프로토콜의 전달 기반으로 HTTP를 사용하면서 특정 호스트의 리소스를 찾아야 하는 경우도 늘었다.[1] 이때 사이트 루트에 임의의 고정 경로를 지정하면 다른 프로토콜 경로 또는 오리진이 직접 만든 리소스와 충돌할 위험이 생기고, 오리진이 자기 URI 공간을 통제할 권한도 침해된다.[1]

`/.well-known/`이라는 단일 접두사를 예약하면 프로토콜별 탐색 위치를 한곳에 분리하고, IANA 등록 절차를 통해 이름 충돌을 막을 수 있다.[1][2] RFC 8615는 `http`와 `https` 외에도 RFC 8307을 통해 갱신된 웹소켓(`ws`)과 보안 웹소켓(`wss`) URI에 `/.well-known/` 접두사를 예약하며, 다른 URI 스킴도 스킴 정의에서 명시적으로 허용하면 웰노운 URI를 사용할 수 있다.[1] RFC 5785는 웰노운 URI가 여러 차례 왕복 통신이나 리소스별 확인이 비현실적인 상황에서 사이트 단위 정책 정보와 메타데이터를 직접 제공하거나 다른 URI로 안내하는 용도로 설계되었으며, 일반적인 정보 검색이나 대규모 URI 네임스페이스 구축은 의도된 범위 밖에 둔다고 밝혔다.[2]

## 웰노운 URI의 구문과 적용 범위 규칙

웰노운 URI는 RFC 8615가 정한 구문과 계층 규칙을 따른다.[1] 예를 들어 애플리케이션이 `example`이라는 접미사를 등록하면 `http://www.example.com/`에서의 웰노운 URI는 `http://www.example.com/.well-known/example`이 된다.[1] 등록하는 모든 접미사는 RFC 3986의 `segment-nz` 구문 규칙을 만족해야 하므로 등록 이름 자체에 `/` 문자를 넣을 수 없다.[1] RFC 8615는 애플리케이션이 구체적인 이름을 택하도록 권고하며, 일반 명사를 선점하는 행위를 지양하고 `example-metadata`나 `example.com-metadata` 같은 이름을 예로 든다.[1]

등록 요청은 해당 URI를 역참조했을 때 반환되는 형식, 관련 미디어 유형(media type), 사용할 URI 스킴을 정의한 사양을 참조해야 한다.[1] URI 스킴을 별도로 적지 않으면 `http`와 `https`가 기본으로 적용된다.[1] 포트는 해당 스킴의 기본 포트를 사용하며, 다른 포트를 쓰려면 애플리케이션 사양에 명시해야 한다.[1] 등록 항목에는 추가 하위 경로, 쿼리 문자열, 프래그먼트 식별자의 구문이나 HTTP 메서드 처리 같은 프로토콜 세부 규칙도 함께 넣을 수 있다.[1]

RFC 8615는 기본 경로인 `/.well-known/` 자체의 형식이나 미디어 유형을 정하지 않으며, 클라이언트가 해당 위치에 리소스가 있다고 가정해서는 안 된다.[1] 웰노운 URI는 URI 경로 계층의 최상위에만 놓인다. `/.well-known/example`은 웰노운 URI에 해당하고, `/foo/.well-known/example`처럼 경로 중간에 위치한 주소는 웰노운 URI에 해당하지 않는다.[1] 또한 특정 애플리케이션에서 어떤 호스트 이름을 조회할지와 웰노운 URI에서 얻은 메타데이터의 적용 범위는 각 애플리케이션 사양이 직접 정의해야 한다.[1]

## IANA 웰노운 URI 레지스트리와 등록 정책

웰노운 URI의 새 접미사를 도입하려는 애플리케이션은 `/.well-known/` 아래에 경로를 만들기 전에 IANA 웰노운 URI 레지스트리에 등록해야 한다.[1] RFC 5785에 따라 2010년 1월 20일 개설된 이 레지스트리는 IANA가 관리한다. IANA는 ICANN과의 계약을 통해 IETF 프로토콜 매개변수 네임스페이스를 중앙에서 조정하며, 할당 충돌을 방지하고 상호 운용성을 유지한다.[2][3][8] 2026-11-23 기준 IANA 레지스트리 페이지는 마지막 갱신일을 2026년 10월 26일로 표기하고 있으며, 지정 전문가로 마크 노팅엄을 등재하고 XML, HTML, TXT, CSV 형식 내려받기를 제공한다.[3]

RFC 8615에 따라 등록 절차는 RFC 8126(BCP 26, 2017년 6월 발행, RFC 5226 대체)이 정의한 사양 필수(Specification Required) 정책을 따르며, 한 명 이상의 지정 전문가 자문을 거쳐 승인된다.[1][3][8] 등록 및 변경 요청은 IANA 레지스트리 인터페이스나 `wellknown-uri-review@ietf.org` 메일링 리스트로 제출할 수 있다.[1][3] 앞서 RFC 5785가 최초 검토 절차를 정할 당시에는 지정 전문가가 14일 이내에 승인 또는 거부를 회신하고, 21일이 넘도록 결정되지 않은 요청은 `iesg@iesg.org`를 통해 인터넷 엔지니어링 운영 그룹(IESG)에 상정할 수 있도록 규정했다.[2]

RFC 8615는 등록 요청에 네 가지 필수 항목과 선택 항목 하나를 포함하도록 요구한다.[1]

- **URI 접미사(URI suffix)**: `/.well-known/` 뒤에 붙는 이름
- **변경 관리자(Change controller)**: 표준 트랙 RFC는 `IETF`, 그 외 사양은 책임 주체의 이름
- **사양 문서(Specification document(s))**: 항목을 정의한 문서 참조(가급적 문서를 내려받을 수 있는 URI 포함)
- **상태(Status)**: `permanent`(영구) 또는 `provisional`(임시)
- **관련 정보(Related information, 선택)**: 추가 참고 문서 인용

RFC 8615는 기존 RFC 5785의 네 항목 템플릿에 상태(Status) 구분을 추가했다.[1][2] 표준 트랙 RFC와 RFC 2026 제7.1.1절 기준의 개방형 표준에 정의된 값은 `permanent` 상태를 받으며, 그 외 값도 전문가가 해당 URI 스킴 커뮤니티(관련 워킹 그룹 메일링 리스트 또는 `art@ietf.org`)와 협의해 실제 사용 사실을 확인하면 `permanent`로 등록될 수 있다.[1] 나머지 항목은 `provisional` 상태로 등록되며, 전문가는 커뮤니티 협의를 거쳐 미사용 항목을 삭제하거나 사용이 확산된 항목을 `permanent`로 승격할 수 있다.[1] 널리 배포되었으나 미등록 상태인 웰노운 URI는 사양 문서 참조 요건을 충족하는 조건에서 전문가나 제3자가 등록할 수도 있다.[1] 2026년 10월 26일 기준 IANA 레지스트리 표에는 더 이상 쓰이지 않는 항목을 표시하는 `deprecated`(`privacy-sandbox-attestations.json`, `related-website-set.json`, `tpcd` 등)와 `obsoleted`(`http-opportunistic`, `mud` 등) 상태도 함께 등재되어 있다.[3]

## 주요 등록 웰노운 URI 접미사

웰노운 URI는 IETF, W3C, OpenID Foundation, OASIS, ETSI 등 여러 표준화 기구에서 보안 취약점 제보, 인증서 자동 발급, 인증 및 권한 부여 메타데이터, 프로토콜 탐색 용도로 쓰인다.[3] 보안 제보, 인증서 자동화, 인증 및 권한 부여 탐색에 쓰이는 영구 접미사 다섯 가지는 다음과 같다.[3]

| URI 접미사 | 정의 사양 | 상태 | 변경 관리자 | 등록일 |
| --- | --- | --- | --- | --- |
| `openid-configuration` | OpenID Connect Discovery 1.0 | permanent | OpenID Foundation Artifact Binding Working Group | 2013-08-27 |
| `acme-challenge` | RFC 8555, Section 8.3 | permanent | IETF | 2016-08-18 |
| `oauth-authorization-server` | RFC 8414, Section 3 | permanent | IESG | 2018-03-27 |
| `security.txt` | RFC 9116 | permanent | IETF | 2021-07-13 |
| `oauth-protected-resource` | RFC 9728, Section 3 | permanent | IETF | 2024-10-22 |

`security.txt`는 E. Foudil과 Y. Shafranovich가 2022년 4월 정보성(Informational) RFC 9116으로 정의한 기계 판독형 텍스트 파일이다. 조직이 보안 취약점 공개 정책과 신고 연락처를 게시해 보안 연구자가 취약점을 제보할 수 있게 돕는다.[4] 줄 단위 키-값 필드(`Contact`, `Expires`, `Encryption`, `Canonical`, `Policy`, `Acknowledgments`, `Preferred-Languages`, `Hiring` 등)와 `#` 주석을 지원하며, 파일 위치의 진위를 검증하기 위해 `Canonical` 필드와 함께 OpenPGP 평문 서명(RFC 4880)을 적용하도록 권고한다.[4]

`acme-challenge`는 2019년 3월 발행된 표준 트랙 사양 RFC 8555의 자동 인증서 관리 환경(Automatic Certificate Management Environment, ACME) 프로토콜에서 HTTP 검증 챌린지(HTTP Challenge)에 쓰이는 접미사이다.[3][5] ACME는 인증 기관(CA)과 신청자 사이에서 도메인 검증(Domain Validation, DV) X.509 인증서를 위한 도메인 제어 확인, 인증서 발급, 폐기 절차를 자동화해 기존의 수동 검증 방식을 대체한다.[5]

세 가지 접미사는 [OAuth](https://mimirwiki.com/ko/wiki/oauth) 2.0과 OpenID Connect 탐색을 담당한다. `openid-configuration`은 OpenID Connect Discovery 1.0(2014년 2월 최종본 확정, 2023년 12월 15일 정오표 2차 반영본 발행)이 정의하며, 선택적으로 WebFinger(RFC 7033)로 발급자를 찾은 뒤 OpenID 제공자(OpenID Provider)의 구성과 OAuth 2.0 엔드포인트 위치를 JSON 문서로 조회하게 한다.[3][9] `oauth-authorization-server`는 2018년 6월 발행된 표준 트랙 사양 RFC 8414가 이 JSON 메타데이터 형식을 일반 OAuth 2.0 권한 부여 서버(Authorization Server)로 확장한 것으로, `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `scopes_supported`, `response_types_supported` 등의 항목을 HTTPS 응답이나 서명된 JSON 웹 토큰(JWT)으로 전달한다.[3][6] `oauth-protected-resource`는 2025년 4월 발행된 표준 트랙 사양 RFC 9728이 정의하며, OAuth 2.0 보호 리소스(Protected Resource)의 식별자에서 결정론적으로 도출된 위치에 `resource`, `authorization_servers`, `jwks_uri`, `scopes_supported`, `bearer_methods_supported` 같은 JSON 메타데이터를 게시하고 `WWW-Authenticate` 헤더로 메타데이터 URL을 알릴 수 있게 한다.[3][7]

2026년 10월 26일 기준 IANA 레지스트리에는 이 밖에도 `webfinger`(RFC 7033), `caldav`와 `carddav`(RFC 6764), `host-meta`와 `host-meta.json`(RFC 6415), `assetlinks.json`(Google Inc.), `pki-validation`(CA/Browser Forum), `mta-sts.txt`(RFC 8461), `jmap`(RFC 8620), `sbom`(RFC 9472), `api-catalog`(RFC 9727), `agent-card.json`(Linux Foundation), `webauthn`(W3C) 같은 영구 항목과 `gpc.json`, `change-password`, `did.json`, `tdmrep.json` 같은 임시 항목이 등록되어 있다.[3]

## 웰노운 URI의 보안 고려 사항

웰노운 URI는 `/.well-known/` 아래의 리소스가 오리진 전체를 대표하는 성격을 띠므로 프로토콜 설계자와 서버 운영자 모두 보안 위험을 관리해야 한다.[1] RFC 8615는 민감 정보 노출, 서비스 거부(DoS) 공격, 서버 및 클라이언트 인증 문제, DNS 리바인딩(DNS rebinding) 공격, 제한된 서버 접근 권한을 악용해 웰노운 URI 응답을 변조하는 공격을 주요 위험으로 열거한다.[1] 서버 운영자는 여러 주체가 하나의 오리진을 공유하는 환경을 포함해 서버 설정과 로컬 파일 시스템 권한 양쪽에서 웰노운 경로의 쓰기 권한을 엄격하게 통제해야 한다.[1] 또한 점(`.`)으로 시작하는 디렉터리를 숨기는 운영체제에서는 관리자가 `.well-known` 디렉터리의 존재나 변조 사실을 알아차리지 못할 위험도 RFC 8615에 명시되어 있다.[1]

`http`와 `https` 스킴의 웰노운 리소스는 웹 브라우저에서 접근할 수 있으며, 쿠키(RFC 6265), 웹 스토리지(Web Storage), 같은 오리진의 다른 경로에서 불러온 스크립트와 동일한 오리진 보안 경계를 공유한다.[1] 따라서 오리진 내 다른 경로에 교차 사이트 스크립팅(Cross-Site Scripting, XSS) 취약점이 있으면 공격자가 웰노운 리소스에 임의의 요청을 보낼 수 있다.[1] RFC 8615는 브라우저와 상호 작용하는 웰노운 엔드포인트에 대해 다음과 같은 완화 조치와 모범 사례를 제시한다.[1]

- 민감한 정보를 암호화하고, 인증 토큰이나 비밀번호 같은 민감 데이터에는 브라우저 스크립트 환경의 압축 공간 탐색 공격을 막기 위해 압축을 적용하지 않는다
- 같은 오리진의 다른 애플리케이션과 충돌하지 않도록 쿠키 이름 같은 식별자를 유연하게 설계하고, 쿠키에 `HttpOnly` 플래그와 `Path` 매개변수를 지정한다
- `X-Content-Type-Options: nosniff` 헤더를 전송하고, 애플리케이션 전용 `Content-Type` 미디어 유형을 검증하며, `Content-Security-Policy`와 `Referrer-Policy` 헤더를 적용한다

개별 애플리케이션 사양은 오리진 간 경계 혼동을 막기 위해 탐색 방법과 메타데이터 적용 범위를 명시해야 한다.[1] RFC 8615는 `https://example.com/.well-known/example`에서 얻은 정책을 `https://department.example.com`, `https://www.example.com`, `https://www.example.com:8000` 같은 다른 호스트나 포트에 적용하면 실제 존재하지 않을 수 있는 관리 관계를 가정하게 되어 보안 문제가 생긴다고 경고한다.[1] 또한 이메일 같은 별도 서비스의 정책을 찾기 위해 특정 호스트 이름의 웰노운 HTTPS URI를 부트스트랩 용도로 지정하면, 해당 URI를 구현하지 않은 웹 서버에도 대량의 불필요한 요청이 몰려 서비스 거부 공격과 유사한 부하가 발생할 수 있다.[1]

## 웰노운 URI의 오리진 루트 제약과 llms.txt와의 비교

웰노운 URI는 RFC 8615에 따라 오리진 경로 계층의 최상위에만 놓이므로 `/foo/.well-known/example` 같은 하위 경로는 웰노운 URI로 인정되지 않는다.[1] 이러한 오리진 루트 단위 구조는 `/robots.txt`나 `/sitemap.xml`(참조: [사이트맵](https://mimirwiki.com/ko/wiki/sitemaps)) 같은 사이트 전체 대상 파일과 유사하지만, 디렉터리별 메타데이터를 두거나 공유 호스트에서 특정 하위 경로만 운영하는 환경에서는 제약이 된다.[1][10]

제러미 하워드(Jeremy Howard)가 2024년 9월 3일 공개하고 2026년 8월 10일 v2로 개정한 [llms.txt](https://mimirwiki.com/ko/wiki/llms-txt) 제안은 이 구조적 차이를 보여 준다.[10] llms.txt는 마크다운(Markdown) 개요 파일인 `llms.txt`를 사이트 루트(`/llms.txt`)나 `/docs/llms.txt` 같은 임의의 하위 경로에 두도록 규정한다. 각 파일은 자기 경로 아래의 URL을 담당하며, 둘 이상의 파일이 해당할 때 에이전트는 가장 구체적인 경로의 파일을 적용한다.[10] 탐색 수단으로 llms.txt v2는 HTML `link` 요소나 HTTP `Link` 헤더에 표준 링크 관계(`text/markdown` 유형의 `rel="alternate"`와 `rel="describedby"`)를 싣는 방식을 권고한다.[10]

llms.txt 사양은 기존 표준과의 관계를 설명하면서 RFC 8615 웰노운 URI와의 차이를 명시한다.[10] 웰노운 URI는 오리진 루트에만 존재하기 때문에 GitHub Pages 프로젝트 사이트처럼 공유 호스트에서 자기 디렉터리만 관리하는 작성자는 해당 디렉터리에 파일을 게시할 수 있어도 호스트의 `/.well-known/` 경로에는 파일을 추가할 수 없다.[10] `llms.txt`는 `index.html`처럼 임의의 경로에 놓여 해당 경로의 내용을 설명하므로, 특정 경로에 콘텐츠를 게시할 권한이 있는 작성자라면 누구나 자기 영역의 개요 파일을 제공할 수 있다.[10]

## 자주 묻는 질문

### 웰노운 URI란 무엇인가요?

웰노운 URI(Well-Known URI)는 HTTP, HTTPS, WS, WSS처럼 지원을 명시적으로 정의한 URI 스킴에서 경로가 /.well-known/으로 시작하는 통합 자원 식별자입니다. IETF RFC 8615에 규정되어 있으며, 오리진의 고유 URI 공간과 충돌하지 않으면서 오리진 단위의 메타데이터와 서비스 탐색 경로를 제공합니다. [1]

### RFC 8615는 RFC 5785와 어떻게 다른가요?

2019년 5월 발행된 RFC 8615는 2010년 4월의 RFC 5785를 대체하며, http와 https 스킴을 위해 RFC 7230을 갱신하고 IANA URI 스킴 레지스트리가 웰노운 URI 지원 여부를 기록하도록 RFC 7595를 갱신했습니다. 또한 permanent와 provisional 등록 상태를 추가하고, 오리진 루트 경로 제한을 명시했으며, 웹 브라우저 상호 작용과 적용 범위 및 숨김 디렉터리에 관한 보안 지침을 확장했습니다. [1][2]

### 새 웰노운 URI 접미사는 어떻게 등록하나요?

애플리케이션은 RFC 8126의 사양 필수(Specification Required) 정책과 지정 전문가 검토 절차에 따라 IANA 웰노운 URI 레지스트리에 새 접미사를 등록해야 합니다. 등록 요청은 IANA 레지스트리 인터페이스나 wellknown-uri-review@ietf.org 메일링 리스트로 제출하며, URI 접미사, 변경 관리자, 사양 문서, permanent 또는 provisional 상태를 포함해야 합니다. [1][3][8]

### 주요 등록 웰노운 URI 접미사에는 어떤 것이 있나요?

IANA 레지스트리에 영구 등록된 주요 접미사로는 취약점 공개용 security.txt(RFC 9116), 인증서 발급 시 도메인 자동 검증용 acme-challenge(RFC 8555), OAuth 2.0 메타데이터용 oauth-authorization-server(RFC 8414)와 oauth-protected-resource(RFC 9728), OpenID Connect Discovery 1.0용 openid-configuration이 있습니다. [3][4][5][6][7][9]

### 웰노운 URI를 /app/.well-known/ 같은 하위 디렉터리에 둘 수 있나요?

아닙니다. RFC 8615에서 웰노운 URI는 경로 계층의 최상위에만 위치하므로 /.well-known/example은 웰노운 URI에 해당하지만 /foo/.well-known/example 같은 중첩 경로는 웰노운 URI로 인정되지 않습니다. [1]

### llms.txt 제안은 왜 /.well-known/ 밖에 파일을 두나요?

llms.txt 사양은 RFC 8615가 웰노운 URI를 오리진 루트로 제한하기 때문에 GitHub Pages 같은 공유 호스트에서 하위 디렉터리만 관리하는 작성자가 /.well-known/ 아래에 파일을 올릴 수 없다고 설명합니다. 루트나 임의의 하위 경로에 llms.txt를 두면 index.html처럼 각 파일이 자기 디렉터리를 설명할 수 있습니다. [1][10]

## 인용 문장

- 마크 노팅엄이 작성해 2019년 5월 발행된 IETF RFC 8615는 /.well-known/ 경로 접두사를 정의하고 RFC 5785를 대체한다. [1][2]
- RFC 8615는 HTTP, HTTPS, WS, WSS URI에서 /.well-known/을 예약하며 RFC 7230과 RFC 7595를 갱신한다. [1]
- 웰노운 URI는 오리진 경로 계층의 최상위로 제한되며, 등록 접미사는 슬래시 문자 없이 RFC 3986의 segment-nz 구문을 따라야 한다. [1]
- IANA 웰노운 URI 레지스트리는 2010년 1월 20일 개설되었으며 RFC 8126의 사양 필수 정책과 지정 전문가 검토 절차로 운영된다. [1][3][8]
- 2026-11-23 기준 IANA 웰노운 URI 레지스트리는 마지막 갱신일을 2026년 10월 26일로 기록하고 지정 전문가로 마크 노팅엄을 등재한다. [3]
- security.txt 접미사(RFC 9116)는 2021년 7월 13일 영구 등록되었고, acme-challenge 접미사(RFC 8555, Section 8.3)는 2016년 8월 18일 영구 등록되었다. [3][4][5]
- IANA 레지스트리에는 openid-configuration(2013-08-27), oauth-authorization-server(2018-03-27, RFC 8414), oauth-protected-resource(2024-10-22, RFC 9728)가 영구 접미사로 등재되어 있다. [3][6][7][9]
- llms.txt 제안은 웰노운 URI가 오리진 루트에만 존재해 공유 호스트의 하위 경로 작성자가 게시할 수 없다는 이유로 /.well-known/ 접두사를 채택하지 않는다. [1][10]

## 연표

- 2010-01-20: IANA가 웰노운 URI 레지스트리를 개설한다. [3]
- 2010-04: IETF가 마크 노팅엄과 E. Hammer-Lahav가 작성한 RFC 5785를 발행해 /.well-known/ 경로 접두사와 등록 절차를 정의한다. [2]
- 2013-08-27: openid-configuration 접미사가 IANA 웰노운 URI 레지스트리에 영구 등록된다. [3][9]
- 2016-08-18: ACME HTTP 도메인 검증용 acme-challenge 접미사가 IANA 레지스트리에 영구 등록된다. [3][5]
- 2017-06: IETF가 사양 필수 정책을 포함한 IANA 레지스트리 정책 체계인 RFC 8126(BCP 26)을 발행한다. [8]
- 2018-06: 2018년 3월 27일 oauth-authorization-server 등록에 이어 IETF가 OAuth 2.0 권한 부여 서버 메타데이터 사양인 RFC 8414를 발행한다. [3][6]
- 2019-03: IETF가 자동 인증서 관리 환경(ACME) 프로토콜 사양인 RFC 8555를 발행한다. [5]
- 2019-05: IETF가 마크 노팅엄이 작성한 RFC 8615를 발행해 RFC 5785를 대체하고 RFC 7230과 RFC 7595를 갱신한다. [1]
- 2022-04: 2021년 7월 13일 security.txt 등록에 이어 IETF가 보안 취약점 공개 파일 형식인 RFC 9116을 발행한다. [3][4]
- 2025-04: 2024년 10월 22일 oauth-protected-resource 등록에 이어 IETF가 OAuth 2.0 보호 리소스 메타데이터 사양인 RFC 9728을 발행한다. [3][7]
- 2026-10-26: IANA가 2026-11-23 기준 가장 최근의 웰노운 URI 레지스트리 갱신을 기록한다. [3]

## 출처

1. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 게시일 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (확인일 2026-11-23; tier 1: government or public registry)
2. RFC 5785: Defining Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 게시일 2010-04. https://www.rfc-editor.org/rfc/rfc5785.txt (확인일 2026-11-23; tier 1: government or public registry)
3. Well-Known URIs. Internet Assigned Numbers Authority (IANA). 게시일 2026-10-26. https://www.iana.org/assignments/well-known-uris (확인일 2026-11-23; tier 1: government or public registry)
4. RFC 9116: A File Format to Aid in Security Vulnerability Disclosure. Internet Engineering Task Force (IETF). 게시일 2022-04. https://www.rfc-editor.org/rfc/rfc9116.txt (확인일 2026-11-23; tier 1: government or public registry)
5. RFC 8555: Automatic Certificate Management Environment (ACME). Internet Engineering Task Force (IETF). 게시일 2019-03. https://www.rfc-editor.org/rfc/rfc8555.txt (확인일 2026-11-23; tier 1: government or public registry)
6. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 게시일 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (확인일 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 게시일 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (확인일 2026-11-23; tier 1: government or public registry)
8. RFC 8126: Guidelines for Writing an IANA Considerations Section in RFCs. Internet Engineering Task Force (IETF). 게시일 2017-06. https://www.rfc-editor.org/rfc/rfc8126.txt (확인일 2026-11-23; tier 1: government or public registry)
9. Final: OpenID Connect Discovery 1.0 incorporating errata set 2. OpenID Foundation. 게시일 2023-12-15. https://openid.net/specs/openid-connect-discovery-1_0.html (확인일 2026-11-23; tier 3: official site)
10. The /llms.txt file, v2 – llms-txt. llmstxt.org. 게시일 2024-09-03. https://llmstxt.org/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "웰노운 URI." 버전 841af16f, 2026-11-23. https://mimirwiki.com/ko/wiki/well-known-uri
