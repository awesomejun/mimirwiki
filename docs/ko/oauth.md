---
title: "OAuth"
subtitle: "접근 토큰을 사용해 HTTP 리소스에 대한 위임 접근을 허용하는 IETF 표준 인가 프레임워크"
canonical_url: https://mimirwiki.com/ko/wiki/oauth
language: ko
page_class: anchor
revision_sha256: 1c6c70acf9b86811587b4dbcb760c8f318fff2ac24825117079f1d2ebfea22d2
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/oauth.md
  txt: https://mimirwiki.com/ko/wiki/oauth.txt
  json: https://mimirwiki.com/ko/wiki/oauth.json
  jsonld: https://mimirwiki.com/ko/wiki/oauth.jsonld
translations:
  en: https://mimirwiki.com/wiki/oauth
  ja: https://mimirwiki.com/ja/wiki/oauth
  zh: https://mimirwiki.com/zh/wiki/oauth
  es: https://mimirwiki.com/es/wiki/oauth
---

# OAuth

> OAuth는 애플리케이션이 리소스 소유자의 자격 증명을 받지 않고 인가 서버가 발급한 접근 토큰으로 HTTP 리소스에 접근할 수 있게 하는 IETF 인가 프레임워크이다. 2012년 10월 RFC 6749로 OAuth 2.0이 발행됐고 2025년 1월 RFC 9700으로 보안 모범 사례가 갱신됐으며, OpenID Connect와 모델 컨텍스트 프로토콜 인가에 쓰인다.

OAuth는 제3자 애플리케이션이 접근 토큰(access token)을 사용해 리소스 소유자(resource owner)를 대신하거나 자체 자격으로 HTTP 보호 리소스에 제한적으로 접근할 수 있게 하는 개방형 인가 프레임워크이다. 2007년 10월 커뮤니티 사양으로 안정화되고 2010년 4월 RFC 5849(OAuth 1.0)로 문서화된 뒤, 2012년 10월 IETF 표준 트랙의 RFC 6749와 RFC 6750으로 발행된 OAuth 2.0으로 대체됐다. 이후 IETF는 코드 교환 증명 키(Proof Key for Code Exchange, PKCE, RFC 7636), 인가 서버 메타데이터(RFC 8414), OAuth 2.0 보안 모범 사례(RFC 9700, BCP 240), 보호 리소스 메타데이터(RFC 9728)를 발행해 OAuth 2.0을 확장했다. 2026-11-23 기준 IETF OAuth 워킹그룹은 OAuth 2.0과 후속 보안 요건을 하나의 사양으로 통합하는 OAuth 2.1(draft-ietf-oauth-v2-1-17)을 개발하고 있다.

**다른 이름:** OAuth 2.0, OAuth 2.1, OAuth 1.0, OAuth 2.0 인가 프레임워크, RFC 6749

## 핵심 정보

- **표준화 기구:** 국제 인터넷 표준화 기구(IETF) OAuth 워킹그룹 [8]
- **핵심 사양:** RFC 6749(OAuth 2.0, 2012년 10월) [1]
- **보안 모범 사례:** RFC 9700 / BCP 240(2025년 1월) [6]
- **역할 구성:** 리소스 소유자, 리소스 서버, 클라이언트, 인가 서버 [1]
- **OAuth 2.1 초안 현황:** draft-ietf-oauth-v2-1-17(활성 인터넷 초안, 2026-10-30 갱신) (기준 2026-11-23) [8]

## 기본 정보

- **유형:** HTTP 인가 프레임워크 [1]
- **표준화 기구:** 국제 인터넷 표준화 기구(IETF) OAuth 워킹그룹 [8]
- **OAuth 1.0:** 2007년 10월 안정화, 2009년 6월 개정판 A, RFC 5849(정보성 문서, 2010년 4월) [4]
- **OAuth 2.0 프레임워크:** RFC 6749(표준 트랙, 2012년 10월, 편집자 D. Hardt) [1]
- **베어러 토큰 사용법:** RFC 6750(표준 트랙, 2012년 10월, TLS 필수) [2]
- **PKCE:** RFC 7636(표준 트랙, 2015년 9월) [3]
- **인가 서버 메타데이터:** RFC 8414(표준 트랙, 2018년 6월) [5]
- **보안 모범 사례(BCP):** RFC 9700 / BCP 240(2025년 1월, RFC 6749·6750·6819 갱신) [6]
- **보호 리소스 메타데이터:** RFC 9728(표준 트랙, 2025년 4월) [7]
- **OAuth 2.1 지위:** 활성 인터넷 초안 draft-ietf-oauth-v2-1-17(2026-10-30 갱신, 2027-05-04 만료) (기준 2026-11-23) [8]
- **OAuth 2.0 역할:** 리소스 소유자, 리소스 서버, 클라이언트, 인가 서버 [1]
- **OAuth 2.0 기반 프로토콜:** OpenID Connect, UMA 2.0, IndieAuth [9]

## OAuth의 기원과 OAuth 1.0에서 OAuth 2.0으로의 전환

OAuth는 제3자 클라이언트의 역할을 리소스 소유자(resource owner)와 분리해, 애플리케이션이 리소스 소유자의 자격 증명을 보유하지 않고 인가 서버(authorization server)가 발급한 접근 토큰(access token)으로 HTTP 리소스에 접근하게 한다.[1] 전통적인 클라이언트-서버 비밀번호 공유 방식에서는 제3자 애플리케이션이 사용자 비밀번호를 평문으로 저장해야 했고, 범위나 유효 기간 제한 없이 과도한 접근 권한을 얻었으며, 비밀번호를 바꾸지 않고는 특정 앱의 권한만 철회할 수 없었고, 제3자 앱이 침해되면 사용자 비밀번호와 그로 보호되는 모든 데이터가 함께 노출됐다.[1]

OAuth 1.0은 보호된 리소스에 대한 위임 접근 문제를 해결하려던 소규모 웹 개발자 커뮤니티에서 만들어졌다.[4] 이 프로토콜은 2007년 10월 버전 1.0으로 안정화됐고, 2009년 6월 `oauth.net/core/1.0a`에 공개된 OAuth Core 1.0 개정판 A(Revision A)로 수정됐다.[4] 원저자들이 변경 통제 권한을 IETF로 이관한 뒤, IETF는 2010년 4월 E. Hammer-Lahav가 편집한 정보성 문서 RFC 5849를 발행해 개정판 A와 보고된 정오 사항을 정리했다.[4] OAuth 1.0은 클라이언트(초기 명칭 Consumer), 서버(초기 명칭 Service Provider), 리소스 소유자(초기 명칭 User)의 세 역할을 두었다.[4] 또한 고유 식별자와 공유 비밀의 쌍으로 구성된 세 가지 자격 증명(클라이언트, 임시, 토큰 자격 증명)을 사용하고, 난스(nonce), 타임스탬프, 서명 방식(`HMAC-SHA1`, `RSA-SHA1`, `PLAINTEXT`)으로 HTTP 요청을 인증했다.[4]

2012년 10월 IETF는 D. Hardt가 편집한 RFC 6749와 M. Jones 및 D. Hardt가 작성한 베어러 토큰 사용법(RFC 6750)을 표준 트랙 문서로 발행하며 OAuth 2.0을 표준화했다.[1][2] RFC 6749는 RFC 5849를 대체하고 폐기한다.[1] OAuth 2.0은 HTTP 환경을 대상으로 설계됐으며 OAuth 1.0과 하위 호환되지 않지만, 두 버전이 네트워크에 공존하거나 구현체가 둘 다 지원할 수 있다.[1] HTTP 이외의 프로토콜에서 OAuth 2.0을 사용하는 것은 RFC 6749의 범위 밖이다.[1]

## OAuth 2.0의 역할, 엔드포인트, 토큰, 인가 유형

OAuth 2.0은 RFC 6749에서 HTTP 리소스에 대한 위임 접근을 위해 네 가지 역할을 정의한다.[1]

| 역할 | RFC 6749의 정의 |
| --- | --- |
| 리소스 소유자(resource owner) | 보호된 리소스에 대한 접근 권한을 부여할 수 있는 주체. 사람인 경우 최종 사용자(end-user)라고 부른다 |
| 리소스 서버(resource server) | 보호된 리소스를 호스팅하며 접근 토큰을 사용한 요청을 받아 응답하는 서버 |
| 클라이언트(client) | 리소스 소유자를 대신해 인가를 받아 보호된 리소스를 요청하는 애플리케이션 |
| 인가 서버(authorization server) | 리소스 소유자를 인증하고 인가를 얻은 뒤 클라이언트에게 접근 토큰을 발급하는 서버 |

인가 서버와 리소스 서버는 같은 서버일 수도 있고 분리된 개체일 수도 있으며, 하나의 인가 서버가 여러 리소스 서버에서 통용되는 접근 토큰을 발급할 수 있다.[1] RFC 6749는 인가 서버의 두 엔드포인트인 인가 엔드포인트(Authorization Endpoint)와 토큰 엔드포인트(Token Endpoint), 그리고 클라이언트의 리디렉션 엔드포인트(Redirection Endpoint)를 정의한다.[1] 추상 프로토콜 흐름에서 클라이언트는 리소스 소유자로부터 인가 부여(authorization grant)를 받은 뒤 인가 서버에서 특정 범위(scope), 수명, 접근 속성을 나타내는 접근 토큰으로 교환하고, 이 토큰을 리소스 서버에 제시한다.[1][2] 일부 흐름에서는 클라이언트가 리소스 소유자의 인가 부여 없이 자체 자격 증명을 인가 서버에 직접 제시해 접근 토큰을 발급받는다.[1][2]

RFC 6750은 전송 계층 보안(Transport Layer Security, TLS)을 적용한 HTTP/1.1 요청에서 베어러 토큰(bearer token)을 사용하는 방법을 규정하며, TLS의 구현과 사용을 의무화한다.[2] 베어러 토큰은 암호화 키 소유를 증명하지 않고 토큰을 소지한 누구나 해당 리소스에 접근할 수 있는 보안 토큰이므로, 저장과 전송 과정에서 노출되지 않도록 보호해야 한다.[2] RFC 6750은 베어러 토큰을 전달하는 세 가지 방법으로 `Authorization` 요청 헤더 필드(`Authorization: Bearer <token>`), 폼 인코딩 본문 매개변수, URI 쿼리 매개변수를 정의하며, 한 요청에서 둘 이상의 방법을 동시에 쓰지 못하게 규정한다.[2] 또한 IANA에 `Bearer` 접근 토큰 유형과 `WWW-Authenticate` 응답 헤더의 오류 값 `invalid_request`, `invalid_token`, `insufficient_scope`를 등록한다.[2]

RFC 6749는 네 가지 인가 유형(grant type)으로 인가 코드(Authorization Code), 암시적(Implicit), 리소스 소유자 비밀번호 자격 증명(Resource Owner Password Credentials), 클라이언트 자격 증명(Client Credentials)을 정의하고, 갱신 토큰(refresh token)과 확장 인가 유형(Extension Grants) 구조를 포함한다.[1] 이후 IETF 사양은 브라우저나 키보드가 없는 장치를 위한 장치 인가 부여(Device Authorization Grant, RFC 8628) 같은 흐름을 추가했다.[9] 후속 보안 지침인 RFC 9700은 보안성이 낮은 동작 방식을 폐지했고, OAuth 커뮤니티 사이트는 암시적 부여와 비밀번호 부여를 레거시(Legacy)로 분류하며, OAuth 2.1은 두 방식을 제외한다.[6][9][10]

## OAuth 2.0 PKCE와 보안 모범 사례(RFC 9700)

인가 코드 부여 방식을 쓰는 OAuth 2.0 공개 클라이언트(public client)는 인가 코드 가로채기 공격에 취약하며, IETF는 이를 완화하기 위해 2015년 9월 RFC 7636(N. Sakimura, J. Bradley, N. Agarwal 작성)에서 코드 교환 증명 키(Proof Key for Code Exchange, PKCE, 발음 "pixy")를 규정했다.[3] 스마트폰 같은 단말에서 악성 앱이 정상 네이티브 OAuth 2.0 앱과 동일한 커스텀 URI 스킴을 등록하면, 운영체제 내부 앱 간 리디렉션 과정에서 인가 코드를 가로채 접근 토큰으로 교환할 수 있다.[3]

PKCE는 클라이언트가 매 인가 요청마다 암호학적으로 무작위한 고유 `code_verifier`를 생성하고, 이를 변환한 `code_challenge`를 인가 엔드포인트에 전달하는 방식으로 가로채기 공격을 막는다.[3] 클라이언트는 토큰 엔드포인트에 인가 코드를 제출할 때 원래의 `code_verifier`를 함께 보내며, 인가 서버는 이를 검증한 뒤 토큰을 발급한다.[3] RFC 7636은 초기 `code_challenge_method` 값으로 `plain`과 `S256`을 정의한다. `plain`은 인가 응답만 관찰하는 공격을 완화하고, `S256`은 운영체제 HTTP 로그 유출 등으로 인가 요청까지 관찰할 수 있는 공격까지 완화한다.[3]

2025년 1월 IETF는 OAuth 2.0 보안 모범 사례인 RFC 9700(BCP 240, T. Lodderstedt, J. Bradley, A. Labunets, D. Fett 작성)을 발행해 RFC 6749, RFC 6750, RFC 6819를 갱신했다.[6] RFC 9700은 실제 구현 취약점, 높은 보안이 요구되는 환경(오픈 뱅킹, eHealth, 전자정부, 전자서명), 동적 클라이언트-서버 구성, 리디렉션 시 URL 프래그먼트 처리에 관한 브라우저 동작 변화를 반영한다.[6] 주요 요구 사항은 다음과 같다.[6]

- 클라이언트 리디렉션 URI를 사전 등록된 URI와 대조할 때 네이티브 앱의 localhost 리디렉션 URI 포트 번호를 제외하고 정확 문자열 일치(exact string matching) 검증 의무화
- 클라이언트와 인가 서버에서 쿼리 매개변수의 임의 URI로 브라우저를 전달하는 오픈 리다이렉터(open redirector) 노출 금지
- 인가 서버 지원이 확인된 PKCE, OpenID Connect의 `nonce` 매개변수, 또는 사용자 에이전트에 안전하게 결합된 `state` 내 일회용 토큰을 이용한 교차 사이트 요청 위조(Cross-Site Request Forgery, CSRF) 방어 의무화
- 클라이언트가 둘 이상의 인가 서버와 통신할 때 RFC 9207의 `iss` 매개변수, ID 토큰이나 JARM 응답의 `iss` 클레임, 또는 별도 리디렉션 URI를 이용한 혼동 공격(mix-up attack) 방어 의무화
- 인가 코드 부여 방식에서 공개 클라이언트의 PKCE 사용 의무화, 기밀 클라이언트(confidential client)의 PKCE 사용 권장, 그리고 추가 조치를 전제로 한 기밀 OpenID Connect 클라이언트의 `nonce` 대안 허용
- 보안성이 낮거나 안전하지 않은 동작 방식의 폐지, 그리고 발신자 제한 접근 토큰(sender-constrained access token), 대상 제한 접근 토큰(audience-restricted access token), 갱신 토큰 보호에 관한 지침 제시

IETF OAuth 워킹그룹은 이 밖에도 푸시 인가 요청(PAR, RFC 9126), 소유 증명 시연(DPoP, RFC 9449), 상호 TLS(Mutual TLS, RFC 8705), 접근 토큰용 JWT 프로파일(RFC 9068), 토큰 검사(Token Introspection, RFC 7662), 토큰 철회(Token Revocation, RFC 7009), 토큰 교환(Token Exchange, RFC 8693), 리치 인가 요청(RAR, RFC 9396), 단계적 인증 챌린지(Step-up Authentication Challenge, RFC 9470), 기기 간 흐름 보안(RFC 10027) 등의 확장 사양을 발행했다.[9]

## OAuth 2.0 메타데이터와 탐색 사양

OAuth 2.0은 초기에는 배포 시점에 클라이언트가 서버 URL을 미리 아는 정적 관계를 전제했으며, 이후 IETF 사양은 동적 환경을 위해 [웰노운 URI](https://mimirwiki.com/ko/wiki/well-known-uri)에서 JSON 메타데이터를 탐색하는 방식을 추가했다.[5][6][7]

2018년 6월 표준 트랙으로 발행된 OAuth 2.0 인가 서버 메타데이터(RFC 8414, M. Jones, N. Sakimura, J. Bradley 작성)는 OpenID Connect Discovery 1.0의 메타데이터 형식을 호환 가능하게 일반화해 폭넓은 OAuth 2.0 사례에 적용한다.[5] 클라이언트는 쿼리나 프래그먼트가 없는 `https` 스킴의 `issuer` URL에서 도출한 `.well-known` 위치(RFC 5785 기준)로부터 JSON 문서를 조회하며, `issuer` 식별자는 인가 서버 혼동 공격을 막는 데도 쓰인다.[5] 메타데이터는 HTTPS를 통한 자체 선언 JSON 형태나 JSON Web Token(JWT) 클레임으로 서명된 형태로 전달할 수 있다.[5] 등록된 주요 필드에는 `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `registration_endpoint`(RFC 7591), `scopes_supported`, `response_types_supported`, `response_modes_supported`(생략 시 기본값 `query`와 `fragment`, `form_post`도 정의), `grant_types_supported`가 있다.[5]

2025년 4월 표준 트랙으로 발행된 OAuth 2.0 보호 리소스 메타데이터(RFC 9728, M.B. Jones, P. Hunt, A. Parecki 작성)는 클라이언트와 인가 서버가 보호된 리소스와 상호작용하는 데 필요한 정보를 얻도록 RFC 8414와 대칭적인 JSON 메타데이터 형식을 정의한다.[7] 각 보호 리소스는 자신의 `https` 리소스 식별자에서 결정론적으로 도출된 `.well-known` 위치(RFC 8615 기준)에 자체 선언 방식이나 JWT 서명 방식으로 메타데이터 문서를 게시한다.[7] IANA에 등록된 주요 매개변수에는 `resource`(필수), `authorization_servers`(RFC 8414 발급자 식별자 목록), `jwks_uri`, `scopes_supported`, `bearer_methods_supported`(`header`, `body`, `query`)가 포함된다.[7] RFC 9728은 보호 리소스가 `WWW-Authenticate` HTTP 응답 헤더로 클라이언트에게 보호 리소스 메타데이터 URL을 동적으로 알리는 방법도 규정한다.[7]

프로그래밍 방식의 클라이언트 등록을 위해 RFC 7591은 OAuth 2.0 동적 클라이언트 등록 프로토콜(Dynamic Client Registration Protocol)을, RFC 7592는 실험적 등록 관리를 정의한다.[5][9] 2026-11-23 기준 OAuth 워킹그룹은 클라이언트 ID 메타데이터 문서(`draft-ietf-oauth-client-id-metadata-document-00`)와 Cross-App Access(XAA) 같은 초안 사양도 함께 개발하고 있다.[9][12]

## OAuth 2.1 통합 작업과 IETF 초안 현황

OAuth 2.1은 OAuth 2.0(RFC 6749), 베어러 토큰 사용법(RFC 6750), 그리고 이후 발행된 주요 사양을 단일 문서로 통합하려는 IETF OAuth 워킹그룹의 작업이다.[8][10] 이 사양은 PKCE(RFC 7636), 네이티브 앱용 OAuth 2.0(RFC 8252), 브라우저 기반 앱용 OAuth(RFC 10017), OAuth 2.0 보안 모범 사례(RFC 9700)의 변경 사항을 하나로 모은다.[6][10]

2026-11-23 기준 `draft-ietf-oauth-v2-1-17`(Dick Hardt, 편집자 Aaron Parecki, Torsten Lodderstedt 작성, `draft-parecki-oauth-v2-1` 대체)은 표준 트랙을 목표로 하는 활성 인터넷 초안이며, 승인될 경우 RFC 6749와 RFC 6750을 대체한다.[8] IETF Datatracker는 개정판 17의 마지막 갱신일을 2026-10-30(문서 표기일 2026-10-31), 만료일을 2027-05-04로 기록하고 있으며, 2026년 12월 IESG 제출을 OAuth 워킹그룹 마일스톤으로 둔다.[8] IETF는 인터넷 초안을 진행 중인 작업으로 분류하며, 이 문서는 아직 최종 RFC로 발행되지 않았다.[8] 초안 소스와 이슈 트래커는 `github.com/oauth-wg/oauth-v2-1`에서 관리된다.[8]

OAuth 커뮤니티의 OAuth 2.1 문서는 OAuth 2.0과의 주요 차이점 일곱 가지를 정리하며, 이 내용은 2026-11-23 기준 `draft-ietf-oauth-v2-1-17`의 구성에도 반영되어 있다.[8][10]

| 항목 | OAuth 2.1 규정(draft-ietf-oauth-v2-1-17) |
| --- | --- |
| PKCE | 인가 코드 흐름을 사용하는 모든 OAuth 클라이언트에 의무화 |
| 리디렉션 URI | 정확 문자열 일치(exact string matching)로 비교 |
| 암시적 부여 | 사양에서 제외(`response_type=token` 제거) |
| 리소스 소유자 비밀번호 자격 증명 부여 | 사양에서 제외 |
| URI 쿼리 문자열의 베어러 토큰 | 제외. 리소스 요청은 Authorization 헤더 필드 또는 폼 인코딩 본문 매개변수 사용 |
| 공개 클라이언트 갱신 토큰 | 발신자 제한 방식 적용 또는 토큰 순환(rotation) 의무화 |
| 클라이언트 유형 정의 | 공개 클라이언트와 기밀 클라이언트의 구분을 자격 증명 보유 여부로 단순화 |

`draft-ietf-oauth-v2-1-17`은 베어러 토큰 외에 발신자 제한 접근 토큰 절을 별도로 두고, 핵심 인가 유형을 인가 코드, 클라이언트 자격 증명, 갱신 토큰, 확장 인가 유형으로 한정한다.[8]

## OpenID Connect와 모델 컨텍스트 프로토콜 인가에서의 OAuth

OAuth 2.0은 OpenID Connect(OpenID Foundation), UMA 2.0(Kantara), IndieAuth(W3C), 그리고 [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(Model Context Protocol, MCP)의 전송 계층 인가 등 여러 프로토콜의 기반이 된다.[9][11][12]

OpenID Connect는 RFC 6749와 RFC 6750 위에 구축된 상호 운용 가능한 인증 프로토콜로, 애플리케이션이 OpenID 제공자(OpenID Provider, OP 또는 Identity Provider, IDP)로 불리는 인가 서버의 인증 결과를 바탕으로 사용자 신원을 확인하고 REST 방식의 UserInfo 엔드포인트에서 사용자 프로필 클레임을 얻게 한다.[11] 사용자 인증을 OP에 위임하는 애플리케이션과 웹사이트는 신뢰 당사자(Relying Party, RP)라고 부른다.[11] OpenID Connect 흐름에서 RP가 OP에 요청을 보내면 OP가 사용자를 인증하고 인가를 얻은 뒤, 최소한 사용자 식별자(`sub` 클레임)와 인증 시점·방식 정보를 담은 신원 토큰(Identity Token)을 보통 접근 토큰과 함께 반환한다.[11] OpenID Connect는 전송 암호화에 HTTPS/TLS를, 서명이 필요한 경우 JSON Web Token(JWT) 구조를 사용하며 웹, 모바일, 자바스크립트 클라이언트를 지원하고 신원 데이터 암호화, 제공자 탐색, 세션 로그아웃 같은 선택 기능을 제공한다.[11] OpenID Foundation은 이러한 JSON·REST 기반 구조를 XML 기반인 OpenID 2.0 및 SAML과 대비해 설명한다.[11]

모델 컨텍스트 프로토콜 사양(버전 2026-07-28)은 HTTP 기반 전송을 위한 선택적 전송 계층 인가를 정의하며, STDIO 전송을 쓰는 구현체는 이 사양을 따르지 않고 환경에서 자격 증명을 가져온다.[12] MCP 인가에서 보호된 MCP 서버는 OAuth 2.1 리소스 서버 역할을, MCP 클라이언트는 리소스 소유자를 대신해 요청을 보내는 OAuth 2.1 클라이언트 역할을 맡고, 인가 서버가 사용자와 상호작용해 접근 토큰을 발급한다.[12] 2026-11-23 기준 MCP 버전 2026-07-28이 준수 대상으로 명시하는 OAuth 및 OpenID Connect 사양 구성은 다음과 같다.[12]

- 핵심 흐름과 토큰: OAuth 2.1 IETF 초안(`draft-ietf-oauth-v2-1-13`)과 베어러 토큰 사용법(RFC 6750)
- 보호 리소스 탐색: MCP 서버와 클라이언트에 OAuth 2.0 보호 리소스 메타데이터(RFC 9728) 구현 의무화. MCP 서버는 HTTP 401 응답의 `WWW-Authenticate: Bearer` 헤더에 `resource_metadata`(예: `/.well-known/oauth-protected-resource`)와 최소 권한·단계적 인가를 위한 선택적 `scope` 안내를 포함한다
- 인가 서버 탐색: 인가 서버는 OAuth 2.0 인가 서버 메타데이터(RFC 8414)와 OpenID Connect Discovery 1.0 가운데 하나 이상을 제공해야 하며, MCP 클라이언트는 두 방식을 모두 지원해야 한다
- 리소스 및 발급자 결합: OAuth 2.0 리소스 지시자(RFC 8707) 구현 의무화로 인가 요청과 토큰 요청 모두에 MCP 서버의 정규 URI를 `resource` 매개변수로 포함하고, 토큰 엔드포인트에 인가 코드를 보내기 전 RFC 9207의 `iss` 매개변수를 기록된 발급자와 대조 검증한다
- 클라이언트 등록: OAuth 클라이언트 ID 메타데이터 문서(`draft-ietf-oauth-client-id-metadata-document-00`), 사전 등록, 또는 동적 클라이언트 등록(RFC 7591 및 OpenID Connect Dynamic Client Registration 1.0) 중 하나를 사용하며, MCP에서는 RFC 7591을 폐지 대상으로 표시하고 하위 호환용으로 유지한다

## 자주 묻는 질문

### OAuth란 무엇인가요?

OAuth는 제3자 애플리케이션이 리소스 소유자의 자격 증명을 받지 않고 인가 서버가 발급한 접근 토큰을 사용해 HTTP 보호 리소스에 제한적으로 접근할 수 있게 하는 IETF 인가 프레임워크입니다. OAuth 2.0은 2012년 10월 IETF 표준 트랙 문서인 RFC 6749와 RFC 6750으로 발행됐습니다. [1][2]

### OAuth 2.0의 네 가지 역할은 무엇인가요?

RFC 6749는 네 가지 역할을 정의합니다. 보호된 리소스에 대한 접근 권한을 부여하는 리소스 소유자(사람인 경우 최종 사용자), 보호된 리소스를 호스팅하는 리소스 서버, 인가를 받아 보호된 리소스를 요청하는 클라이언트, 그리고 리소스 소유자를 인증하고 접근 토큰을 발급하는 인가 서버입니다. [1]

### PKCE란 무엇이며 OAuth 2.0에서 왜 사용하나요?

2015년 9월 RFC 7636으로 규정된 코드 교환 증명 키(PKCE)는 동적으로 생성한 무작위 코드 검증자와 이를 변환한 코드 챌린지로 인가 요청과 토큰 요청을 연결해 인가 코드 부여 방식의 인가 코드 가로채기 및 주입 공격을 완화합니다. RFC 9700은 공개 클라이언트에 PKCE 사용을 의무화하고 기밀 클라이언트에도 사용을 권장합니다. [3][6]

### OAuth 2.0 보안 모범 사례인 RFC 9700에서는 무엇이 달라졌나요?

2025년 1월 BCP 240으로 발행된 RFC 9700은 RFC 6749, RFC 6750, RFC 6819를 갱신합니다. 네이티브 앱의 localhost 포트 번호를 제외한 리디렉션 URI 정확 일치 검증, 오픈 리다이렉터 금지, CSRF 방어 및 RFC 9207 iss 매개변수 등을 통한 혼동 공격 방어, 공개 클라이언트의 PKCE 의무화, 보안성이 낮은 동작 방식의 폐지 등을 규정합니다. [6]

### OAuth 2.1은 확정된 표준인가요?

2026-11-23 기준 OAuth 2.1은 IETF OAuth 워킹그룹의 활성 인터넷 초안(draft-ietf-oauth-v2-1-17, 2026-10-30 갱신, 2027-05-04 만료)이며 2026년 12월 IESG 제출을 워킹그룹 마일스톤으로 두고 있습니다. OAuth 2.0과 이후 RFC를 통합하면서 암시적 부여와 리소스 소유자 비밀번호 자격 증명 부여, URI 쿼리 문자열의 베어러 토큰 전달을 제외하고 모든 인가 코드 클라이언트에 PKCE를 의무화합니다. [8][10]

### OpenID Connect와 모델 컨텍스트 프로토콜은 OAuth를 어떻게 활용하나요?

OpenID Connect는 OAuth 2.0(RFC 6749, RFC 6750) 위에 구축된 인증 프로토콜로, OpenID 제공자가 신원 토큰을 반환하고 UserInfo 엔드포인트가 사용자 프로필 클레임을 제공합니다. 모델 컨텍스트 프로토콜 버전 2026-07-28은 선택적 HTTP 전송 인가에 OAuth 2.1, RFC 6750, RFC 8414, RFC 9728, RFC 8707, RFC 9207을 적용하며 보호된 MCP 서버를 OAuth 2.1 리소스 서버로 다룹니다. [11][12]

## 인용 문장

- OAuth 1.0은 2007년 10월 안정화됐고 2009년 6월 개정판 A로 수정된 뒤 2010년 4월 정보성 문서인 RFC 5849로 발행됐다. [4]
- 2012년 10월 IETF 표준 트랙으로 발행된 RFC 6749는 OAuth 2.0 인가 프레임워크를 정의하고 RFC 5849를 대체한다. [1]
- RFC 6750은 OAuth 2.0 보호 리소스에 대한 HTTP 베어러 토큰 사용법을 정의하며 전송 계층 보안(TLS) 사용을 의무화한다. [2]
- 2015년 9월 발행된 RFC 7636은 OAuth 2.0 공개 클라이언트에 대한 인가 코드 가로채기 공격을 완화하기 위해 코드 교환 증명 키(PKCE)를 규정한다. [3]
- RFC 8414(2018년 6월)와 RFC 9728(2025년 4월)은 OAuth 2.0 인가 서버와 보호 리소스를 위해 .well-known URI에서 제공하는 JSON 메타데이터 형식을 정의한다. [5][7]
- 2025년 1월 발행된 RFC 9700(BCP 240)은 OAuth 2.0 보안 모범 사례를 담아 RFC 6749, RFC 6750, RFC 6819를 갱신한다. [6]
- 2026-11-23 기준 OAuth 2.1은 승인 시 RFC 6749와 RFC 6750을 대체할 예정인 활성 IETF 인터넷 초안(draft-ietf-oauth-v2-1-17, 2026-10-30 갱신)이다. [8]
- 모델 컨텍스트 프로토콜 사양 버전 2026-07-28은 HTTP 인가를 쓰는 보호된 MCP 서버에 RFC 9728 구현을 요구하고 MCP 클라이언트에 RFC 8707 resource 매개변수 전송을 요구한다. [12]

## 연표

- 2007-10: 웹 개발자 커뮤니티가 OAuth 1.0 프로토콜을 안정화한다. [4]
- 2009-06: OAuth Core 1.0 개정판 A가 oauth.net/core/1.0a에 공개된다. [4]
- 2010-04: IETF가 OAuth 1.0 프로토콜을 정보성 문서인 RFC 5849로 발행한다. [4]
- 2012-10: IETF가 RFC 6749(OAuth 2.0 인가 프레임워크)와 RFC 6750(베어러 토큰 사용법)을 표준 트랙으로 발행해 RFC 5849를 대체한다. [1][2]
- 2015-09: IETF가 OAuth 공개 클라이언트를 위한 코드 교환 증명 키(PKCE)를 규정한 RFC 7636을 발행한다. [3]
- 2018-06: IETF가 OAuth 2.0 인가 서버 메타데이터를 정의한 RFC 8414를 발행한다. [5]
- 2025-01: IETF가 OAuth 2.0 보안 모범 사례인 RFC 9700(BCP 240)을 발행해 RFC 6749, RFC 6750, RFC 6819를 갱신한다. [6]
- 2025-04: IETF가 OAuth 2.0 보호 리소스 메타데이터를 정의한 RFC 9728을 발행한다. [7]
- 2026-07-28: 모델 컨텍스트 프로토콜 사양 버전 2026-07-28이 HTTP 기반 전송 인가에 OAuth 2.1, RFC 9728, RFC 8414, RFC 8707, RFC 9207을 명시한다. [12]
- 2026-10-30: IETF Datatracker에 OAuth 2.1 인터넷 초안 개정판 17(draft-ietf-oauth-v2-1-17)이 갱신 기록되며, 만료일은 2027-05-04이고 IESG 제출 워킹그룹 마일스톤은 2026년 12월이다. [8]

## 출처

1. RFC 6749: The OAuth 2.0 Authorization Framework. Internet Engineering Task Force (IETF). 게시일 2012-10. https://www.rfc-editor.org/rfc/rfc6749.txt (확인일 2026-11-23; tier 1: government or public registry)
2. RFC 6750: The OAuth 2.0 Authorization Framework: Bearer Token Usage. Internet Engineering Task Force (IETF). 게시일 2012-10. https://www.rfc-editor.org/rfc/rfc6750.txt (확인일 2026-11-23; tier 1: government or public registry)
3. RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Internet Engineering Task Force (IETF). 게시일 2015-09. https://www.rfc-editor.org/rfc/rfc7636.txt (확인일 2026-11-23; tier 1: government or public registry)
4. RFC 5849: The OAuth 1.0 Protocol. Internet Engineering Task Force (IETF). 게시일 2010-04. https://www.rfc-editor.org/rfc/rfc5849.txt (확인일 2026-11-23; tier 1: government or public registry)
5. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 게시일 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (확인일 2026-11-23; tier 1: government or public registry)
6. RFC 9700: Best Current Practice for OAuth 2.0 Security. Internet Engineering Task Force (IETF). 게시일 2025-01. https://www.rfc-editor.org/rfc/rfc9700.txt (확인일 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 게시일 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (확인일 2026-11-23; tier 1: government or public registry)
8. draft-ietf-oauth-v2-1-17 - The OAuth 2.1 Authorization Framework. Internet Engineering Task Force (IETF). 게시일 2026-10-30. https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ (확인일 2026-11-23; tier 1: government or public registry)
9. OAuth 2.0 - OAuth. OAuth Community Site. https://oauth.net/2/ (확인일 2026-11-23; tier 3: official site)
10. OAuth 2.1. OAuth Community Site. https://oauth.net/2.1/ (확인일 2026-11-23; tier 3: official site)
11. How OpenID Connect Works - OpenID Foundation. OpenID Foundation. 게시일 2023-02-14. https://openid.net/developers/how-connect-works/ (확인일 2026-11-23; tier 3: official site)
12. Authorization - Model Context Protocol. Model Context Protocol project. 게시일 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "OAuth." 버전 1c6c70ac, 2026-11-23. https://mimirwiki.com/ko/wiki/oauth
