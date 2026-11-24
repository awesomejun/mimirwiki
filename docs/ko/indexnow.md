---
title: "IndexNow"
subtitle: "웹사이트가 검색 엔진에 URL 추가, 수정, 삭제를 알리는 개방형 HTTP 프로토콜"
canonical_url: https://mimirwiki.com/ko/wiki/indexnow
language: ko
page_class: anchor
revision_sha256: 89a79ce6b6dfd94c9b8547d26b9fbdbe9b8089e179e78ae8fee4e64e9459e64e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/indexnow.md
  txt: https://mimirwiki.com/ko/wiki/indexnow.txt
  json: https://mimirwiki.com/ko/wiki/indexnow.json
  jsonld: https://mimirwiki.com/ko/wiki/indexnow.jsonld
translations:
  en: https://mimirwiki.com/wiki/indexnow
---

# IndexNow

> IndexNow는 웹사이트가 추가, 수정, 삭제된 URL을 검색 엔진에 알리기 위해 Microsoft Bing과 Yandex가 2021년 10월 공개한 개방형 HTTP 프로토콜이다. 사이트는 호스트에 올린 텍스트 키 파일로 소유권을 검증한 뒤, 2026-11-23 기준 GET 요청으로 URL 1건을 보내거나 POST 요청으로 최대 10,000건을 한 번에 제출할 수 있다. 참여 엔드포인트 한 곳에 보낸 제출 내역은 나머지 모든 참여 검색 엔진과 공유된다.

IndexNow는 웹사이트 운영자가 참여 검색 엔진에 호스트의 URL 추가, 수정, 삭제 사실을 알릴 수 있게 하는 개방형 HTTP 알림 프로토콜(protocol)이다. Microsoft Bing과 Yandex가 2021년 10월 18일 이 프로토콜을 공개했으며, IndexNow.org에 게시된 사양은 후원사인 Microsoft Corporation, Yandex N.V., Seznam.cz, a.s.에 의해 크리에이티브 커먼즈 저작자표시-동일조건변경허락 4.0(CC BY-SA 4.0) 라이선스로 제공된다. 사이트는 호스트에 게시한 UTF-8 텍스트 키 파일로 도메인 소유권을 검증하고, 단일 URL을 보내는 HTTP GET 요청이나 최대 10,000개 URL을 묶는 JSON POST 요청을 참여 엔드포인트 한 곳에 전송하면 그 URL이 다른 모든 참여 검색 엔진과 자동으로 공유된다. 2026-11-23 기준 공식 목록인 indexnow.org/searchengines.json에는 Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot의 7개 참여 엔드포인트가 등록되어 있다.

**다른 이름:** IndexNow 프로토콜, IndexNow API, IndexNow.org, 인덱스나우

## 핵심 정보

- **공개일:** 2021-10-18 [6]
- **개발 주체:** Microsoft Bing, Yandex [6]
- **사양 라이선스:** 크리에이티브 커먼즈 저작자표시-동일조건변경허락 4.0(CC BY-SA 4.0) (기준 2026-11-23) [5]
- **일괄 제출 한도:** HTTP POST 요청당 최대 10,000개 URL (기준 2026-11-23) [2]
- **등록된 엔드포인트:** searchengines.json 기준 7개(Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (기준 2026-11-23) [4]

## 기본 정보

- **유형:** 개방형 HTTP URL 알림 프로토콜 [1]
- **공개일:** 2021-10-18 [6]
- **개발 주체:** Microsoft Bing, Yandex [6]
- **사양 후원사:** Microsoft Corporation, Yandex N.V., Seznam.cz, a.s. (기준 2026-11-23) [5]
- **라이선스:** 크리에이티브 커먼즈 저작자표시-동일조건변경허락 4.0(CC BY-SA 4.0) (기준 2026-11-23) [5]
- **제출 방식:** HTTP GET(URL 1건) 및 HTTP POST JSON(최대 10,000건) (기준 2026-11-23) [2]
- **전역 엔드포인트:** https://api.indexnow.org/indexnow (기준 2026-11-23) [3]
- **소유권 검증 방식:** 호스트에 게시한 UTF-8 텍스트 키 파일(8~128자) (기준 2026-11-23) [2]
- **URI 인코딩 표준:** RFC 3986 [2]
- **등록된 검색 엔진:** searchengines.json 기준 7개(Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (기준 2026-11-23) [4]
- **이용 비용:** 무료 (기준 2026-11-23) [8]

## IndexNow의 개요와 출범 배경

IndexNow는 웹사이트 운영자가 사이트의 URL 추가, 수정, 삭제를 참여 검색 엔진과 웹 크롤러(crawler)에 알릴 수 있게 하는 무료 개방형 HTTP 프로토콜이다.[1][8] 푸시 알림을 쓰지 않을 때 검색 엔진은 주기적인 크롤링으로 웹사이트 변경 사항을 찾는데, 크롤러가 모든 URL을 자주 방문하지는 않으므로 변경이 반영되기까지 며칠에서 몇 주가 걸릴 수 있다.[1][6] 콘텐츠가 바뀔 때 HTTP 알림을 보내면 검색 엔진이 해당 URL의 크롤링 우선순위를 높이고 변경되지 않은 페이지를 확인하기 위한 탐색성 크롤링을 줄여 서버 부하를 낮출 수 있다.[1][6][8]

Microsoft Bing과 Yandex는 2021년 10월 18일 IndexNow를 공개했다.[6] 2026-11-23에 확인한 IndexNow.org 이용약관에 따르면 IndexNow.org의 후원사는 Microsoft Corporation, Yandex N.V., Seznam.cz, a.s.이다.[5] 후원사는 IndexNow.org에 게시된 프로토콜 사양의 저작권을 크리에이티브 커먼즈 저작자표시-동일조건변경허락 4.0(CC BY-SA 4.0) 라이선스로 제공하며 그 밖의 지식재산권은 부여하지 않는다. 이 이용약관은 미국 캘리포니아주 법의 적용을 받는다.[1][5]

IndexNow의 핵심 조건은 검색 엔진 간 자동 공유다. 프로토콜을 채택한 검색 엔진은 참여 엔드포인트 한 곳에 제출된 모든 URL을 다른 모든 참여 검색 엔진과 자동으로 공유하기로 합의한다.[2][3][6] 이에 따라 웹사이트 운영자는 URL 변경 알림을 참여 엔드포인트 한 곳에만 보내면 된다.[3]

## IndexNow 제출 방식과 HTTP 상태 코드

IndexNow는 추가, 수정, 삭제된 URL을 검색 엔진에 알리기 위해 단일 URL을 보내는 HTTP GET 요청과 여러 URL을 묶어 보내는 HTTP POST JSON 요청의 두 가지 제출 방식을 지원한다.[2] 두 방식 모두 웹 브라우저, 스크립트, `curl`, `wget` 같은 일반 HTTP 클라이언트로 호출할 수 있다.[2][3]

HTTP GET으로 URL 1건을 제출할 때는 `https://<searchengine>/indexnow?url={url-changed}&key={your-key}` 형식으로 요청하며, 키 파일이 사이트 루트 외의 경로에 있을 때는 `keyLocation` 매개변수를 함께 전달한다.[2][3] 제출하는 URL은 RFC 3986 표준에 따라 URL 이스케이프 및 인코딩을 거쳐야 하며, 예를 들어 `:`는 `%3A`, `/`는 `%2F`, `?`는 `%3F`, `=`는 `%3D`, `&`는 `%26`으로 변환한다.[2][3]

여러 URL을 한 번에 제출할 때는 `/indexnow` 경로로 `Content-Type: application/json; charset=utf-8` 헤더를 붙여 HTTP POST 요청을 보내고, JSON 본문에 `host`, `key`, 선택 항목인 `keyLocation`, `urlList`를 담는다.[2][3] 2026-11-23 기준 POST 요청 1건당 최대 10,000개의 URL을 제출할 수 있으며, 같은 호스트의 `http` URL과 `https` URL을 섞어 넣을 수 있다.[2][3] 한 요청에 10,000개를 초과해 담으면 요청이 실패하거나 HTTP 422 응답이 반환될 수 있다.[3] 리디렉션된 URL(HTTP 301, HTTP 302, meta refresh)이나 삭제되어 HTTP 404 또는 HTTP 410을 반환하는 URL도 제출할 수 있어, 검색 엔진이 오래된 항목을 갱신하거나 제거하게 할 수 있다.[3]

2026-11-23 기준 IndexNow.org 문서가 규정하는 제출 요청의 HTTP 응답 코드는 6가지다.[2][3][7]

| HTTP 코드 | 상태 | 문서에 명시된 의미 |
| --- | --- | --- |
| 200 | OK | URL 또는 URL 목록 제출 완료(수신 확인만을 의미) |
| 202 | Accepted | URL 수신 완료, 키 소유권 검증 대기 중(최초 요청 시 흔히 발생) |
| 400 | Bad Request | 잘못된 요청 형식 |
| 403 | Forbidden | 유효하지 않은 키(키 파일 미존재 또는 파일 내 키 불일치 등) |
| 422 | Unprocessable Entity | 호스트에 속하지 않는 URL, 프로토콜 스키마에 맞지 않는 키, 또는 제출 한도 초과 |
| 429 | Too Many Requests | 과도한 요청 또는 스팸 의심에 따른 요청 제한 |

## IndexNow API 키 규칙과 도메인 소유권 검증

IndexNow는 URL을 수동으로 제출하는 웹사이트 운영자가 대상 호스트에 UTF-8 인코딩 텍스트 키 파일을 게시해 도메인 소유권을 증명하도록 요구한다.[2][3] 2026-11-23 기준 API 키는 8자 이상 128자 이하의 문자열이어야 하며, 영문 소문자(`a-z`), 영문 대문자(`A-Z`), 숫자(`0-9`), 하이픈(`-`)만 사용할 수 있다.[2][3] IndexNow 기술 문서는 키 문자열을 16진수 문자라고 부르면서도 허용 문자 집합을 `a-z`, `A-Z`, `0-9`, `-`로 명시한다.[2] 키는 GUID 또는 UUID 생성기, 명령줄 도구, Bing Webmaster Tools의 키 생성 도구 등으로 만들 수 있다.[3][6][7]

IndexNow는 키 파일을 호스팅하는 소유권 검증 방식을 두 가지로 정의한다.[2]

- Option 1(루트 디렉터리): 웹사이트 루트 디렉터리에 키 문자열만 담은 UTF-8 파일 `{your-key}.txt`(예: `https://www.example.com/{your-key}.txt`)를 게시한다.[2][3] 사양은 Option 1을 기본 권장 방식으로 제시하며, 이 파일은 해당 호스트의 URL 전반에 적용된다.[2][3]
- Option 2(하위 경로 디렉터리): 같은 호스트에서 로그인 없이 공개 접근할 수 있는 다른 폴더에 하나 이상의 UTF-8 텍스트 키 파일을 게시하고, 모든 제출 요청마다 GET의 `keyLocation` 쿼리 매개변수나 POST의 JSON `keyLocation` 필드로 키 파일 URL을 지정한다.[2][3] Option 2에서는 키 파일이 놓인 디렉터리에 따라 유효한 URL 범위가 제한된다. 예를 들어 `http://example.com/catalog/key12457EDd.txt`에 둔 키 파일은 `http://example.com/catalog/`로 시작하는 URL에는 유효하지만, `http://example.com/help/`나 `http://example.com/image/` 아래의 URL에는 유효하지 않다.[2]

웹사이트가 URL을 제출하면 참여 검색 엔진은 키 파일을 크롤링해 호스트 소유권을 확인하고, 운영자가 키를 바꿀 때까지 해당 키를 계속 사용한다.[2] 서비스 중단 없이 API 키를 교체하려면 기존 키 파일을 새 `{key}.txt` 파일로 바꾼 뒤 새 키로 URL 제출을 시작하면 되며, 검색 엔진은 다음 제출 시 새 키를 자동으로 재검증한다.[3] IndexNow를 자체 관리하는 콘텐츠 관리 시스템(Content Management System, CMS), 호스팅 서비스, CDN을 쓰는 경우에는 키 파일을 수동으로 만들 필요가 없다.[3]

## IndexNow 참여 검색 엔진과 엔드포인트

IndexNow는 참여 검색 엔진과 크롤러의 기계 판독용 JSON 목록을 `https://www.indexnow.org/searchengines.json`에 게시한다.[4] 2026-11-23 기준 `searchengines.json`에는 각 참여자의 `meta.json` 주소를 연결한 7개 항목이 등록되어 있다.[4] 같은 시점에 IndexNow.org 첫 화면은 지원 검색 엔진으로 5곳(Microsoft Bing, Naver, Seznam.cz, Yandex, Yep)을 적고 있으며, IndexNow FAQ는 전역 엔드포인트 `https://api.indexnow.org/indexnow`와 함께 6개 개별 서비스의 제출 엔드포인트를 안내한다.[1][3]

| 등록 키(`searchengines.json`) | 메타데이터 URL(`searchengines.json`) | 제출 엔드포인트(`indexnow.org/faq`) |
| --- | --- | --- |
| `bing` | `https://www.bing.com/indexnow/meta.json` | `https://www.bing.com/indexnow` |
| `yandex` | `https://www.yandex.com/indexnow/meta.json` | `https://yandex.com/indexnow` |
| `seznam` | `https://search.seznam.cz/indexnow/meta.json` | `https://search.seznam.cz/indexnow` |
| `naver` | `https://searchadvisor.naver.com/indexnow/meta.json` | `https://searchadvisor.naver.com/indexnow` |
| `yep` | `https://indexnow.yep.com/indexnow/meta.json` | `https://indexnow.yep.com/indexnow` |
| `internetarchive` | `https://web-static.archive.org/indexnow/meta.json` | FAQ 엔드포인트 목록에 미기재 |
| `amazonbot` | `https://indexnow.amazonbot.amazon/indexnow/meta.json` | `https://indexnow.amazonbot.amazon/indexnow` |

2025년 5월 19일 Microsoft AI Bing의 수석 프로덕트 매니저인 파브리스 카넬(Fabrice Canel)과 크리슈나 마다반(Krishna Madhavan)은 Bing Webmaster Blog를 통해 Amazon이 웹 콘텐츠 변경을 탐지하고 불필요한 크롤링을 줄이기 위해 2025년 6월 중순부터 IndexNow 도입을 시작할 예정이라고 발표했다.[9] 2026-11-23 기준 Amazon의 `amazonbot` 엔드포인트는 `searchengines.json`과 IndexNow FAQ 양쪽에 모두 등재되어 있다.[3][4]

IndexNow.org 문서가 명시한 참여 요건에 따르면, IndexNow에 참여하려는 검색 엔진은 제출된 URL을 다른 모든 참여 검색 엔진과 자동 공유하기로 합의해야 하며, 최소 하나 이상의 시장에서 뚜렷한 입지를 가지거나 검색 시장과 밀접하게 연관되어 있으면서 URL 제출량에 상당한 기여를 해야 한다.[2]

## IndexNow의 CMS, 플러그인, Cloudflare Crawler Hints 연동

IndexNow는 웹사이트가 별도 코드를 작성하지 않고도 URL 변경 알림을 보낼 수 있도록 콘텐츠 관리 시스템(CMS), 서드파티 SEO 플러그인, [콘텐츠 전송 네트워크](https://mimirwiki.com/ko/wiki/content-delivery-network)(Content Delivery Network, CDN)에 연동되어 있다.[3][7]

2021년 11월 30일 [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)는 Microsoft Bing 및 Yandex와 협력해 Crawler Hints 서비스에 IndexNow 지원을 추가하고, Crawler Hints를 모든 Cloudflare 고객에게 무료로 일반 공개했다.[10] Cloudflare 고객은 대시보드 Cache 탭의 Configuration 항목에서 설정을 한 번 켜는 것만으로 이 기능을 활성화할 수 있으며, 이후 콘텐츠가 변경되면 Cloudflare가 IndexNow 신호를 자동으로 전송한다.[10] Cloudflare는 2021년 11월 30일 발표에서 전체 인터넷 트래픽의 약 45%가 웹 크롤러와 봇에서 발생하며, 주요 검색 크롤러 트래픽을 1년간 조사한 결과 크롤러 방문의 53%가 이전 방문 이후 바뀌지 않은 페이지에 대한 요청이었다고 밝혔다.[10] 같은 시점까지 60,000개가 넘는 고유 Cloudflare 웹사이트가 Crawler Hints에 참여해 Bing에 약 10억 건의 변경 힌트를 전송했다.[10] 2026-11-23 기준 IndexNow.org와 Bing Webmaster Tools는 Cloudflare Crawler Hints를 기본 CDN 연동 사례로 안내하고 있으며, 2021년 10월 공개 글에서는 Akamai도 IndexNow 연동을 계획 중이라고 언급했다.[3][6][7]

2026-11-23 기준 IndexNow.org와 Bing Webmaster Tools는 기본 지원 또는 플러그인·확장 기능으로 IndexNow를 지원하는 16개 CMS 플랫폼을 나열한다. 해당 플랫폼은 WordPress, Shopify, Wix, GoDaddy, Duda, XenForo, Milestone, Joomla!, Drupal, Bitrix24, PrestaShop, MODX, Shopware, OpenCart, Typo3, Umbraco다.[3][7] Bing Webmaster Tools에 구체적으로 적힌 서드파티 플러그인으로는 WordPress용 IndexNow plugin, Yoast, RankMath, AIOSEO, SEOPress, Shopify용 InstaIndex, Joomla!용 Aimy Sitemap PRO, JSitemap, Bitrix24용 ReIndex, TurboIndex가 있다.[7]

2021년 10월 공개 당시 Microsoft Bing은 WordPress와 다른 CMS의 도입을 돕기 위해 오픈소스 코드를 제공했고, Wix, Duda, Botify, Oncrawl, Onely, Yext의 연동 계획과 함께 Bing Webmaster URL 제출 API를 쓰던 eBay, LinkedIn, MSN, GitHub, Bizapedia 등 대형 사이트의 IndexNow 전환 계획을 밝혔다.[6] 2025년 5월 19일 Microsoft Bing은 Shopify와 디지털 마케팅·CMS 제공 업체 Milestone Inc.가 IndexNow를 연동했다고 발표했다.[9] 웹사이트 운영자는 제출된 URL의 수신 여부를 Bing Webmaster Tools 포털에서 확인할 수 있다.[7]

## IndexNow 프로토콜의 한계, 미참여 범위, 사이트맵과의 관계

IndexNow는 자발적인 URL 변경 알림 신호로 작동하며, 실제 적용 범위는 검색 엔진의 참여 여부, 크롤링 할당량(crawl quota), 제출 한도, 후원사 약관의 제약을 받는다.[2][3][4][5][7]

IndexNow의 도달 범위는 프로토콜에 등록된 서비스로 한정된다. 2026-11-23 기준 `indexnow.org/searchengines.json`에는 Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot의 7개 참여 엔드포인트가 등록되어 있다.[4] URL 자동 공유는 참여 검색 엔진 사이에서만 이루어지므로, 이 목록에 없는 검색 엔진은 프로토콜을 통해 IndexNow 알림을 받지 않는다.[2][4] 또한 IndexNow.org 이용약관에 따라 각 후원사는 사전 통지 없이 사양을 변경하거나 자사 제품·서비스에서 IndexNow 지원을 중단할 권한을 보유하며, 제출된 URL을 읽거나 색인할 의무를 지지 않는다.[5]

IndexNow 엔드포인트에서 HTTP `200` 응답을 받더라도 해당 엔드포인트가 URL 또는 URL 목록을 수신했다는 사실만 확인된다.[2] IndexNow FAQ와 Bing Webmaster Tools는 모두 URL 제출이 크롤링이나 색인을 보장하지 않는다고 명시한다.[3][7] 검색 엔진은 자체 크롤링 할당량, 스케줄링 로직, 품질 신호를 기준으로 크롤링 여부를 결정하며, IndexNow를 통해 발생한 크롤링도 웹사이트의 크롤링 할당량에 합산된다.[3][7]

IndexNow는 일괄 제출 규모와 요청 빈도에도 제한을 둔다. 2026-11-23 기준 POST 요청 1건당 상한은 10,000개 URL이며, 과도하거나 반복적인 제출에는 HTTP `429` 요청 제한이 적용될 수 있다.[2][3] IndexNow FAQ는 실질적인 콘텐츠 변경이 있을 때만 제출하고, 같은 URL을 다시 제출하기 전에 최소 5분 이상 기다리며, 리뷰·댓글·게시판 글 같은 사용자 생성 콘텐츠는 단계적으로 묶어 제출하도록 안내한다(예: 1~20건은 매 건마다, 100건까지는 5건마다, 1,000건까지는 10건마다 제출).[3]

IndexNow는 [XML 사이트맵](https://mimirwiki.com/ko/wiki/sitemaps)(sitemap)과 함께 쓰도록 설계되었으며, 프로토콜 도입 이후 새로 추가, 수정, 삭제된 URL을 알리는 용도에 맞춰져 있다.[3][7] IndexNow FAQ는 도입 이전의 과거 변경 내역을 소급 제출하거나 사이트 이전·개편 같은 대규모 변경 외에 전체 사이트 URL을 한꺼번에 제출하는 일을 피하고, 전체 URL 목록 제공과 변경 빈도가 낮은 페이지 탐색을 위해 정확한 `lastmod` 값을 담은 XML 사이트맵을 계속 유지하도록 안내한다.[3]

## 자주 묻는 질문

### IndexNow란 무엇인가요?

IndexNow는 웹사이트 운영자가 URL의 추가, 수정, 삭제를 참여 검색 엔진에 알릴 수 있도록 Microsoft Bing과 Yandex가 2021년 10월 18일 공개한 무료 개방형 HTTP 프로토콜입니다. 참여 엔드포인트 한 곳에 URL을 제출하면 해당 알림이 다른 모든 참여 검색 엔진과 자동으로 공유됩니다. [1][2][6][8]

### 어떤 검색 엔진이 IndexNow에 참여하고 있나요?

2026-11-23 기준 공식 목록인 indexnow.org/searchengines.json에는 Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot의 7개 참여 엔드포인트가 등록되어 있습니다. 이 목록에 없는 검색 엔진은 IndexNow를 통해 URL 알림을 받지 않습니다. [2][4]

### IndexNow 요청 한 번에 몇 개의 URL을 제출할 수 있나요?

2026-11-23 기준 IndexNow는 HTTP GET 요청당 URL 1건, UTF-8 JSON 형식의 HTTP POST 요청당 최대 10,000건의 URL 제출을 지원합니다. POST 요청 한 번에 10,000건을 초과해 제출하면 요청이 실패하거나 HTTP 422(Unprocessable Entity) 응답이 반환될 수 있습니다. [2][3]

### IndexNow는 웹사이트 소유권을 어떻게 검증하나요?

수동으로 설정할 때 사이트 운영자는 8자에서 128자 길이(a-z, A-Z, 0-9, 하이픈)의 API 키를 만들어 사이트 루트에 {your-key}.txt라는 UTF-8 텍스트 파일로 호스팅합니다. 공개 접근이 가능한 하위 폴더에 키 파일을 두고 제출 시 keyLocation 매개변수로 파일 URL을 지정할 수도 있으며, 이 경우 해당 디렉터리 아래의 URL만 유효한 제출 대상으로 인정됩니다. [2][3]

### IndexNow에서 HTTP 200 응답을 받으면 크롤링이나 색인이 보장되나요?

아닙니다. HTTP 200 응답은 검색 엔진이 제출된 URL 또는 URL 목록을 정상적으로 수신했다는 사실만 확인해 줍니다. 검색 엔진은 자체 크롤링 할당량, 스케줄링 로직, 품질 신호에 따라 크롤링 여부를 판단하며, 이 과정에서 발생하는 크롤링도 사이트의 크롤링 할당량에 포함됩니다. [2][3][7]

### IndexNow가 XML 사이트맵을 대체하나요?

아닙니다. IndexNow 문서는 웹사이트가 IndexNow와 XML 사이트맵을 함께 사용하도록 안내합니다. IndexNow는 최근에 추가, 수정, 삭제된 URL을 알리는 데 쓰이고, lastmod 값이 담긴 XML 사이트맵은 사이트의 전체 URL 목록을 제공하며 변경 빈도가 낮거나 이전에 바뀐 페이지를 탐색하게 합니다. [3]

## 인용 문장

- Microsoft Bing과 Yandex는 2021년 10월 18일 IndexNow 프로토콜을 공개했다. [6]
- IndexNow.org에 게시된 IndexNow 프로토콜 사양은 후원사인 Microsoft Corporation, Yandex N.V., Seznam.cz, a.s.에 의해 크리에이티브 커먼즈 저작자표시-동일조건변경허락 4.0 라이선스로 제공된다. [5]
- 2026-11-23 기준 IndexNow는 HTTP POST JSON 요청 한 번에 최대 10,000개의 URL을 허용한다. [2][3]
- 2026-11-23 기준 IndexNow API 키는 영문 소문자, 영문 대문자, 숫자, 하이픈으로 구성된 8자 이상 128자 이하의 문자열이어야 한다. [2][3]
- 2026-11-23 기준 indexnow.org/searchengines.json에는 Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot의 7개 참여 엔드포인트가 등록되어 있다. [4]
- 2021년 11월 30일 Cloudflare는 Crawler Hints에 IndexNow 지원을 추가하고 이 기능을 Cloudflare 고객에게 무료로 일반 공개했다. [10]
- IndexNow 엔드포인트가 반환하는 HTTP 200 응답은 제출된 URL의 수신 확인만을 뜻하며 크롤링이나 색인을 보장하지 않는다. [2][3][7]

## 연표

- 2021-10-18: Microsoft Bing과 Yandex가 IndexNow URL 알림 프로토콜을 공개한다. [6]
- 2021-11-30: Cloudflare가 Crawler Hints에 IndexNow 지원을 추가하고 모든 Cloudflare 고객에게 무료로 일반 공개한다. [10]
- 2025-05-19: Microsoft Bing이 Shopify와 Milestone Inc.의 IndexNow 지원을 전하고, Amazon이 2025년 6월 중순 IndexNow 도입을 시작할 예정이라고 발표한다. [9]

## 출처

1. Home | IndexNow.org. IndexNow. https://www.indexnow.org/ (확인일 2026-11-23; tier 3: official site)
2. Documentation | IndexNow.org. IndexNow. https://www.indexnow.org/documentation (확인일 2026-11-23; tier 3: official site)
3. FAQ | IndexNow.org. IndexNow. https://www.indexnow.org/faq (확인일 2026-11-23; tier 3: official site)
4. IndexNow Participating Search Engines JSON. IndexNow. https://www.indexnow.org/searchengines.json (확인일 2026-11-23; tier 3: official site)
5. Terms | IndexNow.org. IndexNow. https://www.indexnow.org/terms (확인일 2026-11-23; tier 3: official site)
6. IndexNow – Instantly Index your web content in Search Engines |.... Microsoft Bing Webmaster Blog. 게시일 2021-10-18. https://blogs.bing.com/webmaster/2021/10/IndexNow-Instantly-Index-your-web-content-in-Search-Engines/ (확인일 2026-11-23; tier 3: official site)
7. How to add IndexNow to your website | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow/getstarted (확인일 2026-11-23; tier 3: official site)
8. Why IndexNow | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow (확인일 2026-11-23; tier 3: official site)
9. IndexNow Drives Smarter and Faster Content Discovery | Bing.... Microsoft Bing Webmaster Blog. 게시일 2025-05-19. https://blogs.bing.com/webmaster/2025/5/IndexNow-Drives-Smarter-and-Faster-Content-Discovery/ (확인일 2026-11-23; tier 3: official site)
10. Cloudflare Supports IndexNow via one-click Integration | Bing.... Microsoft Bing Webmaster Blog. 게시일 2021-11-30. https://blogs.bing.com/webmaster/2021/11/Cloudflare-Supports-IndexNow-via-one-click-Integration/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "IndexNow." 버전 89a79ce6, 2026-11-23. https://mimirwiki.com/ko/wiki/indexnow
