---
title: "robots.txt"
subtitle: "로봇 배제 프로토콜(RFC 9309)에 따라 웹 크롤러의 URI 접근 허용 범위를 지정하는 일반 텍스트 파일"
canonical_url: https://mimirwiki.com/ko/wiki/robots-txt
language: ko
page_class: anchor
revision_sha256: 880ddf5794ca2eec6128668c88a440619a97da055469f4d1c69d0e182459586c
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/ko/wiki/robots-txt.md
  txt: https://mimirwiki.com/ko/wiki/robots-txt.txt
  json: https://mimirwiki.com/ko/wiki/robots-txt.json
  jsonld: https://mimirwiki.com/ko/wiki/robots-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/robots-txt
---

# robots.txt

> robots.txt는 로봇 배제 프로토콜(RFC 9309)에 따라 웹사이트의 루트 경로(/robots.txt)에 두는 일반 텍스트 파일로, 자동화된 크롤러가 어떤 URI에 접근할 수 있는지 알려 준다. Martijn Koster가 1994년 처음 정리했고, IETF가 2022년 9월 표준화했다. 규칙은 권고 성격이며 접근 인가 기능을 제공하지 않는다.

robots.txt는 로봇 배제 프로토콜(Robots Exclusion Protocol, REP)에 따라 웹이나 FTP 서비스의 최상위 경로인 /robots.txt에 두는 UTF-8 일반 텍스트 파일로, 크롤러(crawler)라 불리는 자동화 클라이언트가 어떤 URI에 접근할 수 있는지 지정한다. Martijn Koster가 1994년 6월 메일링 리스트 합의를 바탕으로 이 관례를 처음 문서화했고, 인터넷 국제 표준화 기구(IETF)가 2022년 9월 표준 트랙 문서 RFC 9309로 발행했다. 파일은 User-agent 그룹과 Allow, Disallow 경로 규칙으로 구성되며 Sitemap 같은 선택적 레코드를 함께 둘 수 있다. RFC 9309는 robots.txt 규칙을 크롤러가 따라 주기를 요청하는 권고 규칙으로 규정하며, 이 프로토콜은 접근 인가(access authorization)나 기술적 강제 수단을 제공하지 않는다.

**다른 이름:** /robots.txt, 로봇 배제 프로토콜, Robots Exclusion Protocol, REP, RFC 9309

## 핵심 정보

- **표준 문서:** RFC 9309(IETF 표준 트랙, 2022년 9월) [1]
- **원저자 및 합의일:** Martijn Koster(1994-06-30 메일링 리스트 합의) [4]
- **표준 위치:** 서비스 루트의 /robots.txt(UTF-8, text/plain) [1]
- **핵심 지시어:** User-agent, Allow, Disallow(선택적으로 Sitemap) [1]
- **Google 파일 크기 한도:** 500KiB(한도 이후 내용은 무시) (기준 2026-11-23) [6]

## 기본 정보

- **프로토콜 이름:** 로봇 배제 프로토콜(Robots Exclusion Protocol, REP) [1]
- **IETF 사양:** RFC 9309(표준 제안, 2022년 9월) [3]
- **RFC 9309 저자:** Martijn Koster, Gary Illyes, Henner Zeller, Lizzi Sassman [3]
- **최초 합의일:** 1994-06-30 [4]
- **파일 경로:** /robots.txt(모두 소문자, 최상위 디렉터리) [1]
- **인코딩 및 미디어 유형:** UTF-8, text/plain [1]
- **표준 지시어:** User-agent, Allow, Disallow [1]
- **특수 문자:** #(주석), *(와일드카드), $(일치 끝) [1]
- **Google 파일 크기 한도:** 500KiB (기준 2026-11-23) [6]
- **Google 기본 캐시 기간:** 최대 24시간 (기준 2026-11-23) [6]
- **참조 C++ 파서:** github.com/google/robotstxt(Apache-2.0 라이선스) [8]
- **관련 IETF 워킹 그룹:** AI Preferences(aipref), charter-ietf-aipref-01 하에 활성 상태 (기준 2026-11-23) [2]

## robots.txt의 개념과 기원

robots.txt는 로봇 배제 프로토콜(Robots Exclusion Protocol, REP)에 따라 웹사이트나 FTP 호스트의 최상위 경로에 두는 일반 텍스트 파일로, 자동화된 크롤러(crawler)가 어떤 URI에 접근할 수 있는지 밝힌다.[1][5] 서비스 소유자는 색인을 위해 링크를 따라가며 페이지를 수집하는 검색 엔진 크롤러 같은 자동화 클라이언트가 리소스를 요청하기 전에 피해야 할 경로를 알 수 있도록 이 파일을 게시한다.[1][7]

Martijn Koster는 1994년 6월 30일 `robots` 메일링 리스트(`robots-request@nexor.co.uk`)에서 도출되고 월드 와이드 웹 기술 메일링 리스트(`www-talk@info.cern.ch`)에서 논의된 합의를 정리해 "A Standard for Robot Exclusion" 문서로 처음 기록했다.[1][4] 이 문서는 1993년과 1994년에 웹 로봇(방랑자나 스파이더로도 불림)이 짧은 시간에 과도한 요청을 보내 서버에 부하를 주거나, 같은 파일을 반복해서 가져가거나, 깊은 가상 트리, 임시 및 중복 데이터, 투표처럼 부작용이 있는 CGI 스크립트를 탐색하던 사례에 대응하기 위해 마련됐다.[4] `/robots.txt` 단일 파일 방식은 기존 웹 서버에서 별도 설정 없이 쉽게 구현할 수 있고, 크롤러가 문서 한 번의 조회로 접근 정책을 확인할 수 있으며, 주요 운영체제의 파일 이름 규칙에 맞고 기존 파일과 충돌할 가능성이 낮다는 이유로 채택됐다.[4]

이후 25년간 REP는 표준화 기구의 공식 인증 없이 사실상 표준(de facto standard)으로 쓰였으며, 1994년 원문과 1997년 인터넷 초안 "A Method for Web Robots Control"에 문서화돼 있었다.[4][5][8] 1994년 초기 형식은 `User-agent`와 `Disallow` 필드만 정의했고 `Allow` 필드나 와일드카드 일치는 포함하지 않았다.[4][5] 2022년 9월 IETF는 개인 초안 `draft-koster-rep`을 바탕으로 Martijn Koster, Gary Illyes, Henner Zeller, Lizzi Sassman이 작성하고 Murray Kucherawy가 담당 영역 디렉터를 맡은 RFC 9309("Robots Exclusion Protocol")를 표준 트랙의 표준 제안(Proposed Standard)으로 발행했다.[1][3] RFC 9309는 형식 문법을 정립하고 `Allow`와 와일드카드 문자를 표준화했으며, 오류 처리와 캐싱 지침을 추가했다.[1]

## robots.txt의 위치, 형식, 적용 범위

robots.txt 파일은 서비스의 최상위 디렉터리에 모두 소문자인 `/robots.txt` 경로로 배치해야 하며, URI 형식은 `scheme:[//authority]/robots.txt`(예: `https://www.example.com/robots.txt`, `ftp://ftp.example.com/robots.txt`)를 따른다.[1][5] RFC 9309는 파일이 UTF-8(RFC 3629)로 인코딩되고 인터넷 미디어 유형 `text/plain`(RFC 2046)으로 제공되며 CR, LF, CRLF 줄 바꿈을 사용하도록 규정한다.[1][6] Google 검색 구현에서 지원하는 프로토콜은 HTTP와 HTTPS(비조건부 HTTP GET 요청 사용), FTP(익명 `RETR` 명령 사용)이다.[6]

robots.txt 파일에 적힌 규칙은 해당 파일이 호스팅된 정확한 호스트, 프로토콜, 포트 번호에만 적용된다.[6] Google 문서에 정리된 적용 범위는 다음과 같다.[6]

- **하위 도메인과 하위 디렉터리**: `https://example.com/robots.txt`는 `https://other.example.com/`에 적용되지 않으며, `/folder/robots.txt`처럼 하위 디렉터리에 둔 파일은 유효하지 않다.
- **프로토콜과 포트**: `https://example.com/`의 규칙은 `http://example.com/`이나 `ftp://example.com/`에 적용되지 않는다. 기본 포트(HTTP 80, HTTPS 443, FTP 21)는 기본 호스트 이름과 동일하게 취급되지만 `:8181` 같은 비표준 포트에는 별도 파일이 필요하다.
- **IDN과 IP 주소**: 국제화 도메인 이름(IDN)은 퓨니코드(Punycode, RFC 3492) 형식과 동등하게 취급되며, IP 주소를 호스트 이름으로 사용하는 파일은 해당 IP 주소로 크롤링할 때만 유효하다.

2026-11-23 기준 Google은 robots.txt 파일 크기를 최대 500키비바이트(KiB)로 제한하고 그 이후의 내용은 무시한다.[6] Google 파서는 파일 맨 앞의 유니코드 바이트 순서 표시(Byte Order Mark, BOM)를 포함한 잘못된 줄도 무시하며, 응답에서 유효한 규칙만 추출해 적용한다.[6]

## robots.txt 지시어, 구문, 일치 규칙

RFC 9309에 정의된 robots.txt 구문은 증강 배커스-나우르 표기법(Augmented Backus-Naur Form, ABNF, RFC 5234)을 사용해 하나 이상의 `User-agent` 줄과 그 뒤의 `Allow`, `Disallow` 규칙으로 이루어진 그룹을 구성한다.[1] 필드 이름은 대소문자를 구분하지 않으며, `#`으로 주석을 표시하고, 첫 번째 `User-agent` 줄보다 앞에 놓인 `Allow`나 `Disallow` 규칙은 무시해야 한다.[1][4][6]

| 지시어 | RFC 9309 및 크롤러 구현에서의 역할 |
| --- | --- |
| `User-agent` | 규칙을 적용할 크롤러의 제품 토큰(ASCII 영문자, `_`, `-`) 또는 기본 규칙용 `*`를 지정하며 대소문자를 구분하지 않고 일치시킨다.[1] |
| `Disallow` | 일치한 크롤러가 접근하지 말아야 할 `/`로 시작하는 URI 경로 접두사를 지정하며, 값이 비어 있으면 제한을 두지 않는다.[1][6] |
| `Allow` | 일치한 크롤러가 접근할 수 있는 `/`로 시작하는 URI 경로 접두사를 지정해 비허용 디렉터리 안의 하위 경로를 허용할 때 사용한다.[1][6] |
| `Sitemap` | 그룹을 끊지 않는 범위에서 RFC 9309가 허용하는 비핵심 레코드이며, Google은 사이트맵의 전체 URL 형식으로 지원한다.[1][6] |

각 크롤러는 HTTP `User-Agent` 헤더(RFC 9110)의 부분 문자열이 되는 제품 토큰(product token)을 정하고, 그 토큰과 일치하는 모든 그룹의 규칙을 하나로 합쳐 적용한다.[1] 일치하는 특정 그룹이 없으면 `User-agent: *` 그룹을 따르며, 둘 다 없거나 파일이 비어 있으면 어떤 규칙도 적용되지 않는다.[1][4] 경로 일치는 경로의 첫 번째 옥텟(octet)부터 시작하고 대소문자를 구분한다.[1] 비교에 앞서 비ASCII 옥텟과 RFC 3986 예약 문자는 퍼센트 인코딩(percent-encoding)해야 하며, 퍼센트 인코딩된 비예약 ASCII 문자는 디코딩해야 한다.[1] RFC 9309는 주석용 `#`, 0개 이상의 임의 문자를 뜻하는 `*`, 일치 패턴의 끝을 나타내는 `$` 세 가지 특수 문자 지원을 요구하며, URI의 리터럴 `*`와 `$`는 `%2A`와 `%24`로 일치시킨다.[1]

여러 규칙이 하나의 URI와 일치할 때 크롤러는 옥텟 길이가 가장 긴, 곧 가장 구체적인 규칙을 적용해야 한다.[1] `Allow` 규칙과 `Disallow` 규칙의 구체성이 같으면 `Allow` 규칙을 우선하며, `/robots.txt` URI 자체는 암묵적으로 허용된다.[1] RFC 9309에 따라 크롤러는 그룹 구문 분석에 영향을 주지 않는 선에서 사이트맵(Sitemaps) 같은 추가 레코드를 해석할 수 있다.[1] Google은 `user-agent`, `allow`, `disallow`, `sitemap`을 지원하고 `crawl-delay`는 지원하지 않는다.[6] 사이트맵 프로토콜에서 XML 사이트맵은 `<url>`과 `<loc>` 항목을 담은 UTF-8 `<urlset>` 문서로 파일당 최대 50,000개 URL과 압축 해제 기준 50MB(52,428,800바이트)로 제한되며, 여러 사이트맵은 `<sitemapindex>` 파일로 묶을 수 있다.[10]

구현 간 구문 분석 차이를 줄이기 위해 Google은 Googlebot 실제 운영 코드에 기반한 C++ robots.txt 파서 및 매처 라이브러리를 Apache-2.0 라이선스로 `github.com/google/robotstxt`에 오픈소스로 공개했다.[8] 이 저장소에는 로컬 robots.txt 파일에 대해 특정 사용자 에이전트와 RFC 3986 URI의 허용 여부를 검사해 허용 시 종료 코드 0, 비허용 시 1을 반환하는 명령줄 테스트 바이너리(`robots_main`)가 포함되어 있다.[8]

## robots.txt의 HTTP 상태 코드 처리와 캐싱

크롤러는 `/robots.txt` 파일을 가져올 때 서버가 반환하는 HTTP 상태 코드나 네트워크 결과에 따라 robots.txt 규칙의 적용 방식을 정한다.[1][6] RFC 9309는 성공, 리다이렉트, 사용 불가, 도달 불가 상태에 대한 기본 기준을 규정하며, 검색 엔진은 이에 더해 재시도 기간과 캐싱 정책을 문서화한다.[1][6]

| 응답 구분 | RFC 9309 규정 | Google 크롤러 처리 방식(2026-11-23 기준) |
| --- | --- | --- |
| `2xx`(성공) | 파일에서 구문 분석 가능한 규칙을 따른다.[1] | 서버가 제공한 robots.txt 파일을 처리한다.[6] |
| `3xx`(리다이렉트) | 다른 권한(호스트)을 거치더라도 연속 리다이렉트(예: 301, 302)를 최소 5회 따라가며, 가져온 규칙을 최초 호스트에 적용한다. 5회를 넘으면 파일을 사용할 수 없는 것으로 간주할 수 있다.[1] | 리다이렉트를 최소 5단계까지 따라간 뒤 중단하고 404로 처리한다. 프레임, JavaScript, 메타 새로고침 방식의 논리적 리다이렉트는 따라가지 않는다.[6] |
| `4xx`(사용 불가) | HTTP 400-499는 파일이 없거나 사용할 수 없음을 뜻하며 크롤러는 서버의 모든 리소스에 접근할 수 있다.[1] | 429를 제외한 모든 4xx 오류를 유효한 robots.txt가 없는 것으로 처리해 크롤링 제한이 없다고 간주한다. 429 외의 4xx(401, 403 포함)는 크롤링 속도에 영향을 주지 않는다.[6] |
| `5xx` 및 네트워크 오류(도달 불가) | HTTP 500-599나 네트워크 오류는 파일이 정의되지 않은 상태로 보며 크롤러는 전체 비허용을 가정해야 한다.[1] | 처음 12시간 동안 크롤링을 중단하고 계속 재시도한다. 이후 30일간은 마지막으로 유효했던 캐시 사본을 사용하며(캐시가 없으면 제한 없음으로 간주), 30일 뒤에도 오류가 남으면 사이트가 전반적으로 접속 가능한 경우 robots.txt가 없는 것처럼 처리하고 사이트 전반에 장애가 있으면 크롤링을 중단한다.[6] |

Google은 DNS 오류, 타임아웃, 잘못된 응답, 연결 재설정 또는 중단, HTTP 청킹(chunking) 오류를 5xx 서버 오류와 같은 방식으로 처리한다.[6] HTTP 503 응답이 반환되면 Google은 robots.txt 재요청을 더 자주 시도한다.[6]

2026-11-23 기준 Google은 일반적으로 robots.txt 내용을 최대 24시간 동안 캐시하며, 타임아웃이나 5xx 오류로 갱신이 불가능하면 더 오래 유지할 수 있고, 캐시된 응답을 여러 Google 크롤러가 공유할 수 있다.[6] Google은 HTTP `Cache-Control` `max-age` 응답 헤더에 따라 캐시 수명을 늘리거나 줄이기도 한다.[6]

## robots.txt의 권고적 한계, 보안, 색인 제어

RFC 9309는 robots.txt 규칙이 접근 인가(access authorization) 수단이 아니라고 명시하며, 규칙 준수는 각 크롤러의 선택에 달려 있다.[1][7] 1994년 원문 역시 규칙을 강제하는 주체가 없으며 현재와 미래의 모든 로봇이 이를 따르리라는 보장이 없다고 밝혔다.[4] 보안 취약점을 스캔하는 악성 봇이나 스팸 발송용 이메일 주소 수집기 같은 비준수 클라이언트는 robots.txt를 무시한다.[5]

`/robots.txt`는 누구나 읽을 수 있는 공개 파일이므로, 이 파일에 경로를 적으면 관리자가 크롤러의 접근을 막고 싶어 하는 서버 영역이 외부에 그대로 드러난다.[5] robotstxt.org와 Google 문서는 모두 비공개 정보를 숨기는 용도로 robots.txt를 사용할 수 없으며, 비밀번호 보호 같은 별도 접근 통제가 필요하다고 설명한다.[5][7] 또한 Google 문서는 피드 구독 같은 사용자 제어 페처(user-triggered fetcher)나 악성코드 분석처럼 사용자 안전을 높이기 위한 크롤러에는 REP가 적용되지 않는다고 밝힌다.[6]

검색 엔진에서 robots.txt는 크롤링 트래픽과 대역폭 소모를 관리하는 수단이며, 색인 여부는 파일 유형과 별도 지시어에 따라 달라진다.[7][9] HTML 페이지나 PDF 같은 텍스트 기반 문서를 robots.txt로 차단하면 Google이 페이지를 크롤링하지는 않지만, 다른 페이지가 설명 텍스트와 함께 해당 URL로 링크하면 Google이 페이지를 방문하지 않고도 URL을 색인해 설명 문구 없는 검색 결과로 표시할 수 있다.[7] 크롤링 가능한 페이지를 검색 결과에서 제외하려면 HTML `<meta name="robots">` 요소(예: `noindex`)나 `X-Robots-Tag` HTTP 응답 헤더 같은 페이지 단위 지시어를 쓰거나 비밀번호로 접근을 제한해야 한다.[7][9] 이미지, 동영상, 오디오 같은 미디어 파일은 robots.txt로 Google 검색 결과 노출을 막을 수 있으며, 페이지 렌더링에 필요한 스타일시트나 스크립트 리소스 파일을 차단하면 Google이 해당 페이지를 정확히 분석하기 어려워질 수 있다.[7]

## robots.txt와 IETF AIPREF, AI 크롤러 선호 신호

robots.txt는 검색 엔진 크롤링에 더해 인공지능(AI) 모델의 개발, 배포, 사용을 위한 콘텐츠 수집 선호도를 표현하는 표준화 작업에서도 참조된다.[2] 2026-11-23 기준 IETF의 AI Preferences(`aipref`) 워킹 그룹은 웹 및 인터넷 전송(`wit`) 영역에서 승인된 헌장 `charter-ietf-aipref-01` 하에 활동 중이며, Mark Nottingham과 Suresh Krishnan이 공동 의장을, Mike Bishop이 영역 디렉터를 맡고 있다.[2]

`aipref` 헌장은 세 가지 산출물을 규정한다. 첫째는 콘텐츠와의 연결 방식에 독립적인 AI 선호 표현 어휘 표준 트랙 문서(`draft-ietf-aipref-vocab`)이고, 둘째는 IETF 프로토콜과 형식에서 해당 선호도를 콘텐츠에 연결하는 표준 트랙 사양(`draft-ietf-aipref-attach`)이며, 셋째는 여러 선호 표현이 충돌할 때 이를 조정하는 표준 방법이다.[2] 2026-11-23 기준 IETF Datatracker에는 두 초안 문서의 IESG 발행 목표 시점이 2026년 8월로 기재되어 있다.[2] 헌장은 연결 수단으로 로봇 배제 프로토콜(RFC 9309) 같은 웰노운 URI(RFC 8615)와 HTTP 응답 헤더 필드를 명시하고, 국제언론통신위원회(IPTC), PLUS Coalition, WHATWG, W3C와 협력하도록 정하고 있다.[2]

RFC 9309의 권고적 성격과 마찬가지로 `aipref` 헌장은 네 가지 영역을 범위에서 명시적으로 제외한다. 제외 항목은 선호도의 기술적 강제, 클라이언트나 크롤러 인증 및 인가를 위한 애플리케이션 계층 프로토콜, 콘텐츠 선호도 레지스트리 구축, AI 학습에 대한 감사 및 투명성 조치이다.[2] 표준화 기구 밖에서도 검색 노출과 AI 학습을 분리하려는 인프라 제어가 도입되고 있으며, 2026년 9월 15일 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)는 사이트 소유자가 검색 가능성을 유지하면서 AI 학습을 비허용할 수 있도록 Apple, Google, Microsoft와 공유 모델을 이루는 제어 기능과 Accountable 지정을 발표했다.[11]

## 자주 묻는 질문

### robots.txt 파일은 무엇인가요?

robots.txt 파일은 로봇 배제 프로토콜(RFC 9309)에 따라 웹이나 FTP 호스트의 루트 디렉터리(/robots.txt)에 두는 UTF-8 일반 텍스트 파일입니다. 자동화된 크롤러에게 해당 호스트에서 접근할 수 있는 URI 경로와 접근하지 말아야 할 경로를 알려 줍니다. Martijn Koster가 1994년 6월 처음 문서화했고, IETF가 2022년 9월 RFC 9309로 발행했습니다. [1][4]

### RFC 9309 기준으로 robots.txt는 어떤 지시어를 지원하나요?

RFC 9309는 User-agent, Allow, Disallow 세 가지 핵심 지시어와 주석용 #, 와일드카드 *, 경로 끝 표시 $ 특수 문자를 표준화했습니다. 크롤러는 그룹 구문 분석을 방해하지 않는 범위에서 Sitemap 같은 추가 레코드도 해석할 수 있습니다. 2026-11-23 기준 Google은 User-agent, Allow, Disallow, Sitemap을 지원하며 crawl-delay는 지원하지 않습니다. [1][6]

### 크롤러는 robots.txt의 HTTP 4xx와 5xx 오류를 어떻게 처리하나요?

RFC 9309에서 HTTP 400-499 응답은 robots.txt를 사용할 수 없음을 뜻하므로 크롤러가 서버의 모든 리소스에 접근할 수 있고, HTTP 500-599 응답은 파일에 도달할 수 없음을 뜻하므로 전체 비허용을 가정해야 합니다. 2026-11-23 기준 Google은 429를 제외한 4xx 오류를 크롤링 제한 없음으로 처리하고, 5xx 오류에서는 12시간 동안 크롤링을 중단한 뒤 최대 30일간 마지막으로 유효했던 캐시 사본을 사용합니다. [1][6]

### Google의 robots.txt 파일 크기 한도는 얼마인가요?

2026-11-23 기준 Google은 robots.txt의 최대 파일 크기를 500키비바이트(KiB)로 제한합니다. 500KiB를 초과한 뒤의 내용은 Google 파서가 무시합니다. [6]

### robots.txt로 웹 페이지의 검색 결과 노출을 막거나 비공개 파일을 보호할 수 있나요?

아니요. RFC 9309는 robots.txt 규칙이 접근 인가 수단이 아니라고 명시하며, 규칙을 따르지 않는 크롤러는 파일을 무시할 수 있습니다. 웹 페이지의 경우 다른 페이지가 해당 URL로 링크하면 Google이 페이지를 방문하지 않고도 색인할 수 있으므로, 검색 결과 제외나 비공개 파일 보호에는 HTML meta robots 요소, X-Robots-Tag HTTP 헤더, 비밀번호 보호 같은 수단이 필요합니다. [1][7][9]

### IETF AIPREF 워킹 그룹은 robots.txt와 어떤 관련이 있나요?

2026-11-23 기준 활성 상태인 IETF AI Preferences(aipref) 워킹 그룹은 AI 시스템을 위한 콘텐츠 수집 및 처리 선호도를 표현하는 어휘와 프로토콜 결합 방식을 표준화하는 헌장을 맡고 있습니다. 승인된 헌장에는 로봇 배제 프로토콜(RFC 9309) 같은 웰노운 URI(RFC 8615)와 HTTP 응답 헤더 필드를 통해 선호도를 연결하는 방안이 명시되어 있습니다. [2]

## 인용 문장

- Martijn Koster는 1994년 6월 30일 메일링 리스트 합의를 바탕으로 로봇 배제 프로토콜을 처음 문서화했다. [1][4]
- IETF는 2022년 9월 로봇 배제 프로토콜을 표준 트랙 문서 RFC 9309로 발행했다. [1][3]
- RFC 9309는 robots.txt 파일이 UTF-8 인코딩과 text/plain 미디어 유형을 따르며 모두 소문자인 /robots.txt 경로에서 제공되도록 규정한다. [1]
- RFC 9309에서 크롤러는 옥텟 길이가 가장 긴 경로 일치 규칙을 적용하며, Allow 규칙과 Disallow 규칙이 동등하면 Allow 규칙을 우선한다. [1]
- RFC 9309에서 robots.txt에 대한 HTTP 400-499 응답은 서버의 모든 리소스 접근을 허용하며, HTTP 500-599 응답은 전체 비허용을 가정하도록 요구한다. [1]
- 2026-11-23 기준 Google은 robots.txt에 500KiB 파일 크기 한도를 적용하고 한도 이후의 내용은 무시한다. [6]
- Google 문서는 robots.txt로 웹 페이지를 차단하더라도 다른 페이지가 해당 URL로 링크하면 Google 검색 결과에 나타날 수 있다고 밝힌다. [7]
- 2026-11-23 기준 활성 상태인 IETF AI Preferences(aipref) 워킹 그룹은 RFC 9309와 HTTP 응답 헤더 필드를 포함한 IETF 프로토콜로 AI 콘텐츠 선호도를 연결하는 사양을 제정하는 헌장을 맡고 있다. [2]

## 연표

- 1994-06-30: Martijn Koster가 작성한 "A Standard for Robot Exclusion"에 대해 메일링 리스트 합의가 도출됐다. [4]
- 1997: 인터넷 초안 "A Method for Web Robots Control"이 robots.txt 배제 메커니즘을 문서화했다. [5]
- 2022-09: IETF가 RFC 9309("Robots Exclusion Protocol")를 표준 트랙의 표준 제안으로 발행했다. [1][3]
- 2026-09-15: Cloudflare가 검색 가능성을 유지하면서 AI 학습을 비허용하는 제어 기능과 Accountable 지정을 Apple, Google, Microsoft와 함께 발표했다. [11]

## 출처

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (확인일 2026-11-23; tier 1: government or public registry)
2. AI Preferences (aipref). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (확인일 2026-11-23; tier 1: government or public registry)
3. RFC 9309 - Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://datatracker.ietf.org/doc/rfc9309/ (확인일 2026-11-23; tier 1: government or public registry)
4. A Standard for Robot Exclusion - The Web Robots Pages. robotstxt.org. 게시일 1994-06-30. https://www.robotstxt.org/orig.html (확인일 2026-11-23; tier 3: official site)
5. About /robots.txt - The Web Robots Pages. robotstxt.org. https://www.robotstxt.org/robotstxt.html (확인일 2026-11-23; tier 3: official site)
6. How Google Interprets the robots.txt Specification | Google Crawling Infrastructure | Crawling infrastructure | Google for Developers. Google Search Central. https://developers.google.com/crawling/docs/robots-txt/robots-txt-spec (확인일 2026-11-23; tier 3: official site)
7. Robots.txt Introduction and Guide | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/robots/intro (확인일 2026-11-23; tier 3: official site)
8. GitHub - google/robotstxt: The repository contains Google's robots.txt parser and matcher as a C++ library (compliant to C++11).. Google (GitHub). https://github.com/google/robotstxt (확인일 2026-11-23; tier 3: official site)
9. Robots.txt - Glossary | MDN. MDN Web Docs. 게시일 2025-11-26. https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt (확인일 2026-11-23; tier 3: official site)
10. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (확인일 2026-11-23; tier 3: official site)
11. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 게시일 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "robots.txt." 버전 880ddf57, 2026-11-23. https://mimirwiki.com/ko/wiki/robots-txt
