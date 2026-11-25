---
title: "사이트맵"
subtitle: "웹사이트의 URL과 메타데이터를 검색엔진 크롤러에 전달하기 위한 XML 기반 프로토콜"
canonical_url: https://mimirwiki.com/ko/wiki/sitemaps
language: ko
page_class: anchor
revision_sha256: 2adc345c61b0802f704997eb6fa86ecb93107fe0d59cc3534aa21c7e8df96252
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/sitemaps.md
  txt: https://mimirwiki.com/ko/wiki/sitemaps.txt
  json: https://mimirwiki.com/ko/wiki/sitemaps.json
  jsonld: https://mimirwiki.com/ko/wiki/sitemaps.jsonld
translations:
  en: https://mimirwiki.com/wiki/sitemaps
  ja: https://mimirwiki.com/ja/wiki/sitemaps
  zh: https://mimirwiki.com/zh/wiki/sitemaps
  es: https://mimirwiki.com/es/wiki/sitemaps
---

# 사이트맵

> 사이트맵(Sitemaps)은 웹사이트가 크롤링 가능한 URL과 메타데이터를 검색엔진에 알리기 위해 사용하는 XML 프로토콜로, Google, Yahoo, Microsoft가 공동 후원한다. 2026-11-23 기준 0.9 버전은 사이트맵과 색인 파일당 최대 50,000개 항목과 압축 해제 기준 50MB를 한도로 정하며, RSS, Atom, 텍스트 파일과 확장을 지원한다. URL 기재는 탐색을 돕지만 색인은 보장되지 않는다.

사이트맵(Sitemaps)은 웹사이트 운영자가 크롤링 가능한 페이지, 이미지, 동영상 및 기타 파일의 목록과 최종 수정일 같은 메타데이터를 검색엔진에 알리기 위해 사용하는 XML 기반 웹 프로토콜이다. Google, Inc., Yahoo, Inc., Microsoft Corporation이 sitemaps.org를 통해 공동 후원하는 프로토콜 0.9 버전은 개별 사이트맵 파일(urlset)과 사이트맵 색인 파일(sitemapindex)의 XML 스키마를 정의하며, 신디케이션 피드와 일반 텍스트 URL 목록도 지원한다. 2026-11-23 기준 단일 사이트맵 파일의 한도는 URL 50,000개와 압축 해제 기준 50MB(52,428,800바이트)이며, 검색엔진별 XML 확장을 통해 이미지와 뉴스 기사 같은 특수 콘텐츠 정보를 추가할 수 있다. 사이트맵 게시는 검색엔진 크롤러(crawler)의 URL 탐색을 돕지만, 기재된 항목을 수집하거나 색인할지 여부는 각 검색엔진의 재량에 따른다.

**다른 이름:** Sitemaps, 사이트맵 프로토콜, XML 사이트맵, sitemap.xml, Sitemaps 0.9

## 핵심 정보

- **프로토콜 버전:** 0.9(http://www.sitemaps.org/schemas/sitemap/0.9) (기준 2026-11-23) [1]
- **후원사:** Google, Inc., Yahoo, Inc., Microsoft Corporation [3]
- **파일당 제한:** URL 50,000개 및 압축 해제 기준 50MB(52,428,800바이트) (기준 2026-11-23) [1]
- **문자 인코딩:** UTF-8 [1]
- **사양 라이선스:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]

## 기본 정보

- **유형:** 크롤링 가능한 URL을 검색엔진 크롤러에 알리는 웹 프로토콜 [1]
- **후원사:** Google, Inc., Yahoo, Inc., Microsoft Corporation [3]
- **프로토콜 버전:** 0.9 (기준 2026-11-23) [1]
- **XML 네임스페이스:** http://www.sitemaps.org/schemas/sitemap/0.9 (기준 2026-11-23) [1]
- **XML 스키마:** sitemap.xsd(사이트맵) 및 siteindex.xsd(사이트맵 색인 파일) (기준 2026-11-23) [2]
- **지원 형식:** XML, RSS 2.0, Atom 0.3 또는 1.0, UTF-8 일반 텍스트 (기준 2026-11-23) [1]
- **파일당 항목 한도:** 사이트맵당 URL 50,000개, 사이트맵 색인당 사이트맵 50,000개 (기준 2026-11-23) [1]
- **파일당 크기 한도:** 압축 해제 기준 50MB(52,428,800바이트), gzip 압축 지원 (기준 2026-11-23) [1]
- **loc 최대 길이:** 2,048자 미만 (기준 2026-11-23) [1]
- **사양 라이선스:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]
- **Google Search Console 색인 한도:** 사이트당 사이트맵 색인 파일 최대 500개 (기준 2025-12-10) [7]

## 사이트맵 프로토콜 개요

사이트맵(Sitemaps) 프로토콜은 웹사이트 운영자가 크롤링 가능한 페이지, 이미지, 동영상 및 기타 파일의 목록을 검색엔진에 알리기 위해 사용하는 XML 기반 사양이다.[1][5] sitemaps.org는 Google, Inc., Yahoo, Inc., Microsoft Corporation이 후원하며, 후원사들은 사양에 대한 저작권을 크리에이티브 커먼즈 저작자표시-동일조건변경허락 2.5 라이선스(Creative Commons Attribution-ShareAlike License version 2.5)로 배포한다.[3] sitemaps.org 이용약관에 따라 후원사는 게시된 사이트맵을 읽거나 색인하거나 활용할 의무를 지지 않으며, 각 후원사는 언제든 프로토콜 지원을 변경하거나 중단할 수 있다.[3]

사이트맵은 URL 목록에 더해 파일 간 관계와 최종 수정일, 페이지의 [다국어 대체 버전](https://mimirwiki.com/ko/wiki/hreflang) 같은 메타데이터를 전달할 수 있다.[5] XML 스키마가 기본 형식이지만, 사이트맵 프로토콜과 Google 검색은 신디케이션 피드(syndication feed)와 일반 텍스트 URL 목록도 지원한다.[1][6]

- **XML 사이트맵**: 확장이 가능해 이미지, 동영상, 뉴스, 지역화 버전 페이지의 추가 정보를 함께 제공할 수 있다. 대다수 콘텐츠 관리 시스템(CMS)이 XML 사이트맵을 자동 생성하거나 플러그인을 제공하지만, 규모가 크거나 URL이 자주 바뀌는 사이트에서는 매핑 유지가 복잡해질 수 있다.[1][6]
- **RSS, mRSS, Atom 피드**: sitemaps.org는 RSS 2.0과 Atom 0.3 또는 1.0을 지원하며, `link` 필드에서 URL을, 선택 항목인 `pubDate`(RSS) 또는 `updated`(Atom) 필드에서 수정일을 읽는다.[1] 피드는 최근 URL만 포함하는 경우가 많으며 크롤링 대상의 최상위 디렉터리에 두어야 한다.[1] Google은 RSS, mRSS, Atom 1.0 피드를 통해 HTML, 색인 가능한 텍스트 콘텐츠, 동영상 정보를 받을 수 있지만, 이미지와 뉴스 정보에는 XML 확장이 필요하다.[6]
- **텍스트 사이트맵**: 헤더, 푸터, 기타 부가 정보 없이 한 줄에 완전한 URL 하나씩만 적는 UTF-8 텍스트 파일로, HTML 및 색인 가능한 텍스트 페이지에 한정해 사용할 수 있다.[1][6]

WordPress, Wix, Blogger 같은 콘텐츠 관리 시스템은 사이트맵을 자동으로 생성해 두는 경우가 많다.[5] 2025-12-10에 갱신된 Google 검색 센터 문서는 내부 링크로 모든 페이지를 연결하기 어려운 대형 사이트, 외부 링크가 적은 신규 사이트, 동영상이나 이미지 또는 Google 뉴스 콘텐츠 비중이 큰 사이트에서 사이트맵이 유용하다고 설명한다.[5] 반면 검색 결과에 노출할 페이지가 약 500개 이하이고 홈 페이지에서 출발하는 내부 링크로 주요 페이지가 모두 연결되어 있으며 미디어와 뉴스 파일이 많지 않은 소규모 사이트는 사이트맵이 필요하지 않을 수 있다.[5]

## 사이트맵 XML 형식과 요소

사이트맵 프로토콜 0.9는 `http://www.sitemaps.org/schemas/sitemap/0.9` 네임스페이스 아래 UTF-8로 인코딩된 XML 문서 형식을 정의한다.[1] 유효성 검증을 위해 사이트맵 파일용 `http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd`와 사이트맵 색인 파일용 `http://www.sitemaps.org/schemas/sitemap/0.9/siteindex.xsd` 두 가지 공식 XML 스키마가 제공된다.[2]

URL을 포함한 모든 XML 데이터 값은 RFC 3986(URI), RFC 3987(IRI) 및 XML 표준을 따라야 하며, 비ASCII 문자에 대한 URL 퍼센트 인코딩과 함께 5개 예약 문자의 XML 엔티티 이스케이프(entity escaping)를 적용해야 한다. 대상 문자는 앰퍼샌드(`&`를 `&amp;`로), 작은따옴표(`'`를 `&apos;`로), 큰따옴표(`"`를 `&quot;`로), 부등호(`>`를 `&gt;`로, `<`를 `&lt;`로)이다.[1][2] 2026-11-23 기준 사이트맵 프로토콜 0.9는 사이트맵 파일에 6가지 핵심 요소를 규정한다.[1]

| 요소 | 필수 여부 | 값 규칙 및 역할 |
| --- | --- | --- |
| `urlset` | 필수 | 파일 전체를 감싸고 프로토콜 0.9 XML 네임스페이스를 선언하는 루트 요소.[1] |
| `url` | 필수 | 개별 URL 항목의 부모 요소로, 나머지 태그를 하위 요소로 포함한다.[1] |
| `loc` | 필수 | 프로토콜(`http` 또는 `https` 등)으로 시작하고 서버 요구 시 후행 슬래시를 포함하는 완전한 절대 URL. 길이는 2,048자 미만이어야 한다.[1][2] |
| `lastmod` | 선택 | W3C Datetime 형식(`YYYY-MM-DD` 또는 시간대를 포함한 ISO 8601 전체 일시)으로 적는 페이지 최종 수정일. 사이트맵 생성 시각과 구분해 연결된 페이지의 수정 날짜를 기록하며, HTTP `If-Modified-Since`(304) 헤더와 별개로 다뤄진다.[1][2] |
| `changefreq` | 선택 | 페이지 변경 빈도에 대한 개략적 추정값. 허용값은 `always`(접근할 때마다 변경되는 문서), `hourly`, `daily`, `weekly`, `monthly`, `yearly`, `never`(보관된 URL)이다.[1] |
| `priority` | 선택 | 같은 사이트 내 다른 URL과 비교한 상대적 중요도로 `0.0`에서 `1.0` 사이의 값을 쓰며 기본값은 `0.5`이다.[1] |

프로토콜 사양과 Google 검색 문서는 기재할 URL에 관한 세부 규칙도 둔다. `/mypage.html` 같은 상대 경로는 유효하지 않으므로 완전한 절대 URL을 적어야 하며, Google은 기재된 그대로 URL을 크롤링하려 시도한다.[2][6] HTTP와 HTTPS 버전이 모두 존재할 때는 한 가지 버전만 기재해야 하며, 불완전하거나 중복된 크롤링을 막기 위해 세션 ID(session ID)는 제거해야 한다.[2] 프레임을 사용하는 페이지에서는 프레임셋(frameset) URL과 프레임 콘텐츠 URL을 모두 포함한다.[2] 사이트맵 내부에서 URL이 나열된 순서는 검색엔진 처리에 영향을 주지 않는다.[2] Google은 사이트맵이 정규 URL(canonical URL) 선택에 영향을 줄 수 있다고 설명하며, 데스크톱과 모바일 URL이 분리된 경우 한 버전만 적거나 두 버전에 각각 주석을 달아 구분하도록 안내한다.[6]

## 사이트맵 색인 파일과 크기 제한

2026-11-23 기준 단일 사이트맵 파일은 XML과 일반 텍스트 형식을 모두 포함해 최대 50,000개의 URL과 압축 해제 기준 50MB(52,428,800바이트) 크기로 제한된다.[1][2][6] 대역폭 부담을 줄이기 위해 사이트맵 파일을 gzip으로 압축할 수 있으며, 압축을 해제한 상태의 크기가 50MB를 넘지 않아야 한다. sitemaps.org FAQ는 압축 형식으로 gzip을 지정한다.[1][2]

웹사이트의 URL 수가 50,000개를 초과하거나 파일 크기가 50MB를 넘으면 목록을 여러 사이트맵 파일로 분할하고, 이를 하나 이상의 사이트맵 색인(sitemap index) 파일로 묶어야 한다.[1][2][7] 사이트맵 색인 파일 역시 개별 사이트맵과 동일한 UTF-8 인코딩과 `http://www.sitemaps.org/schemas/sitemap/0.9` 네임스페이스를 사용한다.[1][7] 2026-11-23 기준 사이트맵 색인 파일 하나는 최대 50,000개의 사이트맵을 목록에 넣을 수 있고, 압축 해제 기준 50MB(52,428,800바이트) 이하를 유지해야 하며, gzip 압축을 지원한다.[1][2][7]

사이트맵 색인 파일은 프로토콜 0.9에서 정의된 4가지 XML 요소를 사용한다.[1][7]

- `sitemapindex`(필수): 파일에 포함된 모든 사이트맵 항목을 감싸는 루트 요소.[1][7]
- `sitemap`(필수): 개별 사이트맵을 감싸는 부모 요소로 `sitemapindex`의 유일한 직속 하위 태그이다.[1][7]
- `loc`(필수): XML 사이트맵, RSS 파일, Atom 파일, 일반 텍스트 파일의 위치를 나타내는 엔티티 이스케이프 처리된 URL.[1][7]
- `lastmod`(선택): 해당 사이트맵 파일에 나열된 개별 페이지의 수정 시점과 무관하게 그 사이트맵 파일 자체가 변경된 시각을 W3C Datetime 형식으로 기록하는 요소.[1][7]

사이트맵 색인 파일에 `lastmod`를 제공하면 크롤러가 특정 시점 이후 변경된 사이트맵만 선별적으로 가져오는 증분 수집(incremental fetching)이 가능해진다.[1][2] 수천만 개의 URL을 보유한 대형 사이트는 자주 바뀌는 URL을 소수의 사이트맵에 모아 두고 색인 파일의 `lastmod`를 갱신해 신규 및 변경 URL의 탐색 속도를 높일 수 있다.[1][2] 2025-12-10 기준 Google Search Console은 사이트당 최대 500개의 사이트맵 색인 파일 제출을 허용하며, 여러 사이트맵을 나누어 제출하면 Search Console에서 사이트맵별 검색 성과를 따로 추적할 수 있다.[6][7]

## 사이트맵 파일 위치, 적용 범위 및 탐색

사이트맵 파일의 저장 위치는 해당 파일에 포함할 수 있는 유효 URL의 범위를 결정한다.[1] 프로토콜의 경로 접두사 규칙에 따라 `http://example.com/catalog/sitemap.xml`에 둔 사이트맵은 `http://example.com/catalog/`로 시작하는 URL만 포함할 수 있으며, `http://example.com/images/` 같은 다른 경로의 URL이나 `https://example.com/catalog/page1.php`처럼 스킴이 다른 URL은 무효 처리되어 제외된다.[1] 사이트맵에 적는 모든 URL은 사이트맵 파일과 동일한 프로토콜, 호스트, 포트 번호를 사용해야 한다. 예를 들어 `http://www.example.com/sitemap.xml`에는 `http://subdomain.example.com`의 URL을 넣을 수 없으며, `http://www.example.com:100/sitemap.xml`에 나열되는 URL은 모두 `http://www.example.com:100`으로 시작해야 한다.[1][2]

경로 범위가 하위 디렉터리에만 적용되므로 sitemaps.org와 Google은 사이트 전체 파일을 포괄할 수 있도록 웹 서버 루트 디렉터리(`http://example.com/sitemap.xml`)에 사이트맵을 두도록 안내한다.[1][2][6] 조직 내 보안 정책상 디렉터리별 쓰기 권한이 분리되어 있다면 경로별로 별도 사이트맵을 생성할 수 있다.[1][2] Google 검색에서는 Google Search Console을 통해 사이트맵을 제출하면 상위 디렉터리 범위 제한이 해제된다.[6]

사이트맵 색인 파일에도 같은 호스트 및 계층 규칙이 적용되어, 색인 파일은 동일한 호스트의 같은 디렉터리 또는 하위 디렉터리에 있는 사이트맵만 참조할 수 있다.[1][7] 하나의 호스트에서 여러 호스트의 사이트맵을 함께 제출하는 교차 제출(cross-submit)을 사용하려면 각 대상 호스트의 소유권을 입증해야 한다.[1][7]

사이트맵을 생성한 뒤 검색엔진에 알리는 방법으로 sitemaps.org FAQ는 검색엔진에 직접 제출하기, 핑(ping) 전송하기, [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt) 파일에 사이트맵 위치를 추가하기의 세 가지를 든다.[2] 국제 인터넷 표준화 기구(IETF)가 2022년 9월 발행한 로봇 배제 프로토콜(Robots Exclusion Protocol) 표준 RFC 9309는 2.2절 형식 구문(ABNF)에서 `robots.txt` 파서 구현자가 사이트맵 같은 추가 행을 정의할 수 있다고 명시한다.[4] 한편 핑 알림과 관련해 Google 검색 센터 블로그는 2023년 6월 Google의 사이트맵 핑 엔드포인트가 종료될 예정이라고 공지했다.[10]

## 사이트맵의 이미지, 뉴스 및 기타 콘텐츠 확장

사이트맵 XML 파일은 추가 XML 네임스페이스를 통해 특수 콘텐츠 유형을 기술하는 프로토콜 확장을 지원한다.[1][6] Google 검색 센터는 이미지, 뉴스 기사, 동영상 및 [지역화 페이지 버전](https://mimirwiki.com/ko/wiki/hreflang)에 관한 확장을 문서화하고 있으며, 운영자는 전용 사이트맵을 따로 만들거나 기존 XML 사이트맵에 확장 태그를 결합할 수 있다.[5][6][8][9]

| 확장 | XML 네임스페이스 | 필수 요소 | 문서화된 제한 |
| --- | --- | --- | --- |
| 기본 사이트맵 0.9 | `http://www.sitemaps.org/schemas/sitemap/0.9` | `urlset`, `url`, `loc`(또는 `sitemapindex`, `sitemap`, `loc`) | URL 또는 사이트맵 50,000개, 압축 해제 기준 50MB[1][7] |
| Google 이미지 사이트맵 | `http://www.google.com/schemas/sitemap-image/1.1` | `image:image`, `image:loc` | `url`당 `image:image` 태그 최대 1,000개[8] |
| Google 뉴스 사이트맵 | `http://www.google.com/schemas/sitemap-news/0.9` | `news:news`, `news:publication`, `news:name`, `news:language`, `news:publication_date` | `url`당 `news:news` 1개, 사이트맵당 최대 1,000개, 최근 2일 이내 기사[9] |

Google의 이미지 사이트맵 확장은 JavaScript 코드로 불러오는 이미지처럼 크롤러가 놓치기 쉬운 이미지를 Googlebot에 알리는 데 쓰인다.[8] 2025-12-10 기준 각 `url` 요소에는 최대 1,000개의 `image:image` 하위 태그를 넣을 수 있으며, 각 태그 안에 이미지 URL을 담는 `image:loc`가 필수적으로 들어간다.[8] 이미지는 [콘텐츠 전송 네트워크](https://mimirwiki.com/ko/wiki/content-delivery-network)(Content Delivery Network, CDN) 같은 다른 도메인에 호스팅할 수 있으며, 이 경우 두 도메인을 모두 Search Console에서 인증하고 `robots.txt`에서 크롤링을 차단하지 않아야 한다.[8] Google은 2022년 5월 검색 센터 블로그에서 일부 사이트맵 확장 태그의 종료를 알린 데 이어, 이미지 사이트맵 문서에서 `image:caption`, `image:geo_location`, `image:title`, `image:license` 태그를 제거했다.[8][10]

Google의 뉴스 사이트맵 확장은 뉴스 발행사가 기사 메타데이터를 전달하는 데 사용하며, 기존 사이트맵을 확장하거나 Search Console 추적을 위해 뉴스 전용 사이트맵을 별도로 운영할 수 있다.[9] 발행사는 새 기사가 나올 때마다 기존 뉴스 사이트맵 파일을 갱신하며, Google 뉴스는 사이트의 나머지 부분과 같은 빈도로 뉴스 사이트맵을 크롤링한다.[9] 최근 2일 이내에 발행된 기사 URL만 포함해야 하며, 이틀이 지난 기사는 URL을 제거하거나 `news:news` 메타데이터를 삭제한다. 최근 발행 기사가 없어 뉴스 사이트맵이 일시적으로 비어 있을 때 Search Console에 빈 사이트맵 경고가 표시될 수 있으나, 이는 의도된 상태인지 확인하는 알림이며 Google 검색에 문제를 일으키지 않는다.[9] 각 `url`에는 하나의 `news:news` 태그만 허용되고 파일당 `news:news` 태그는 최대 1,000개까지 넣을 수 있다.[9] `news:publication` 내부의 `news:name`은 `news.google.com`에 표시되는 매체 이름에서 괄호 안 문구를 뺀 형태와 정확히 일치해야 하며, `news:language`는 2자리 또는 3자리 ISO 639 언어 코드를 쓰되 중국어 간체는 `zh-cn`, 번체는 `zh-tw`를 사용한다.[9] `news:publication_date`에는 기사가 사이트맵에 추가된 시각과 별도로 사이트에 최초 발행된 일시를 W3C Datetime 형식(`YYYY-MM-DD`, `YYYY-MM-DDThh:mmTZD`, `YYYY-MM-DDThh:mm:ssTZD`)으로 기록한다.[9]

Google 검색 센터는 동영상 사이트맵 항목에 재생 시간, 평점, 연령 적합성 등급을 적을 수 있으며, RSS, mRSS, Atom 1.0 피드를 통해 HTML과 텍스트 콘텐츠 외에 동영상 정보도 제공할 수 있다고 설명한다.[5][6]

## 검색엔진의 사이트맵 메타데이터 처리와 한계

검색엔진은 사이트맵의 선택적 메타데이터 태그를 서로 다르게 처리하며, 사이트맵 프로토콜은 크롤러에 기재된 URL을 읽거나 색인할 의무를 부과하지 않는다.[1][3] 프로토콜 0.9에서 `urlset`, `url`, `loc`는 필수이지만, sitemaps.org는 선택 태그(`lastmod`, `changefreq`, `priority`)의 지원 여부가 검색엔진마다 다르므로 각 검색엔진의 문서를 확인하라고 안내한다.[1][2]

프로토콜 사양에서 `changefreq`는 크롤링 참고 정보로 정의된다.[1] 크롤러는 `hourly`로 표시된 페이지를 한 시간보다 긴 간격으로 수집하거나, `yearly`로 표시된 페이지를 1년보다 자주 수집할 수 있으며, `never`로 표시된 URL도 예상치 못한 변경을 확인하려고 주기적으로 방문할 수 있다.[1] `priority` 역시 같은 사이트 내 URL 사이의 상대적 중요도를 `0.0`에서 `1.0` 사이(기본값 `0.5`)로 표시하는 값이다. 다른 도메인의 페이지와 비교하는 데 쓰이지 않으며, 모든 URL에 높은 값을 지정해도 상대적 구분이 사라지고, 사양과 FAQ는 `priority`가 검색 결과 순위에 영향을 주지 않는다고 설명한다.[1][2]

`lastmod` 태그는 서버가 반환하는 HTTP `If-Modified-Since`(304) 헤더와 별개이며, 검색엔진은 두 정보를 서로 다른 방식으로 활용할 수 있다.[1] sitemaps.org FAQ는 정적 파일의 실제 수정 시각이나 동적 URL의 데이터 변경 기준 추정치를 `lastmod`로 제공하면 크롤러가 변경되지 않은 URL을 다시 수집하지 않도록 도와 웹 서버의 대역폭과 CPU 사용량을 줄일 수 있다고 설명한다.[2] 2025-12-10에 갱신된 Google 검색 센터 문서는 사이트맵 색인 파일의 `lastmod`가 Google의 사이트맵 크롤링 일정 수립에 도움이 될 수 있다고 밝힌다.[7]

형식 측면에서 Google은 XML 사이트맵, RSS/mRSS/Atom 1.0 피드, 일반 텍스트 사이트맵 사이에 선호를 두지 않는다.[6] Google은 사이트맵을 URL 탐색 보조 수단이자 정규 URL 선택에 영향을 줄 수 있는 신호로 활용하지만, 사이트맵에 URL을 넣더라도 크롤링과 색인이 보장되지는 않는다고 명시한다.[5][6] 사이트맵은 RFC 9309에 따라 크롤러 접근 권한을 정의하는 [robots.txt](https://mimirwiki.com/ko/wiki/robots-txt)와 함께 운용되며, 사이트맵에 기재된 콘텐츠를 색인하려면 `robots.txt`에서 해당 크롤링을 허용해야 한다.[4][8] sitemaps.org 이용약관에 따라 Google, Yahoo, Microsoft는 각자 자사 제품과 서비스에서 프로토콜을 일부만 사용하거나 사용을 중단할 권한을 유지한다.[3]

## 자주 묻는 질문

### 사이트맵이란 무엇인가요?

사이트맵은 웹사이트가 크롤링할 수 있는 페이지, 동영상, 이미지 및 기타 파일의 목록과 최종 수정일, 다국어 대체 버전 같은 메타데이터를 검색엔진에 제공하는 기계 판독용 파일입니다. 검색엔진은 이 파일을 읽어 사이트의 URL을 더 효율적으로 탐색하고 수집합니다. [1][5]

### 사이트맵 파일의 URL 수와 크기 제한은 얼마인가요?

2026-11-23 기준 XML 또는 텍스트 형식의 단일 사이트맵 파일은 최대 50,000개의 URL을 담을 수 있으며 압축을 풀었을 때 크기가 50MB(52,428,800바이트) 이하여야 합니다. 사이트맵 색인 파일 역시 압축 해제 기준 50MB 한도 내에서 최대 50,000개의 사이트맵을 목록에 넣을 수 있으며, gzip 압축을 사용할 수 있습니다. [1][2][6][7]

### 사이트맵과 사이트맵 색인 파일에 필수적으로 들어가야 하는 XML 요소는 무엇인가요?

표준 XML 사이트맵에서는 0.9 네임스페이스를 선언하는 urlset 루트 요소, 각 항목을 감싸는 url 부모 요소, 전체 URL을 적는 loc 하위 요소가 필수입니다. 사이트맵 색인 파일에서는 sitemapindex, sitemap, loc 요소가 필수이며, lastmod를 선택 하위 태그로 사용할 수 있습니다. [1][7]

### priority 태그는 검색 결과 순위에 영향을 주나요?

사이트맵 프로토콜과 FAQ에 따르면 priority는 같은 사이트 내 다른 URL과 비교한 상대적 중요도를 0.0에서 1.0 사이(기본값 0.5)로 표시하는 값입니다. 다른 사이트의 페이지와 비교하는 데 쓰이지 않으며, 검색 결과 순위에 영향을 주지 않는 것으로 설명됩니다. [1][2]

### 검색엔진은 사이트맵 파일을 어떻게 찾나요?

sitemaps.org FAQ는 검색엔진에 직접 제출하기, 핑(ping) 보내기, robots.txt에 사이트맵 위치 적기의 세 가지 방법을 안내하며, RFC 9309도 robots.txt 파서가 사이트맵 행을 지원할 수 있다고 언급합니다. Google 검색 센터 블로그는 2023년 6월 Google의 사이트맵 핑 엔드포인트가 종료될 예정이라고 공지했으며, Google Search Console을 통한 직접 제출은 계속 지원됩니다. [2][4][6][10]

### 모든 웹사이트에 사이트맵이 필요한가요?

2025-12-10에 갱신된 Google 검색 센터 문서에 따르면 페이지 수가 많은 대형 사이트, 외부 링크가 적은 신규 사이트, 동영상이나 이미지 또는 Google 뉴스 콘텐츠가 많은 사이트에서 사이트맵이 유용합니다. 반면 검색 결과에 노출할 페이지가 약 500개 이하이고 내부 링크가 빠짐없이 연결되어 있으며 미디어와 뉴스 비중이 작은 사이트는 사이트맵이 필요하지 않을 수 있습니다. [5]

## 인용 문장

- Sitemaps.org는 Google, Inc., Yahoo, Inc., Microsoft Corporation이 후원하며, 프로토콜 사양의 저작권은 크리에이티브 커먼즈 저작자표시-동일조건변경허락 2.5 라이선스(Creative Commons Attribution-ShareAlike License version 2.5)로 배포된다. [3]
- 2026-11-23 기준 사이트맵 프로토콜 0.9는 UTF-8 인코딩, http://www.sitemaps.org/schemas/sitemap/0.9 XML 네임스페이스, 그리고 2,048자 미만의 loc 값을 포함하는 urlset, url, loc 요소를 필수로 규정한다. [1]
- 2026-11-23 기준 단일 사이트맵 파일은 최대 50,000개의 URL과 압축 해제 기준 50MB(52,428,800바이트) 이하로 제한되며, 사이트맵 색인 파일도 같은 50MB 한도 내에서 최대 50,000개의 사이트맵을 포함할 수 있다. [1][2]
- 사이트맵 프로토콜 0.9는 검증용 XML 스키마인 sitemap.xsd와 siteindex.xsd를 제공하며, XML 외에 RSS 2.0, Atom 0.3 또는 1.0, UTF-8 일반 텍스트 형식을 지원한다. [1][2]
- 2022년 9월 IETF가 발행한 RFC 9309는 robots.txt의 ABNF 형식 구문에서 파서 구현자가 사이트맵 같은 추가 행을 정의할 수 있다고 명시한다. [4]
- 2025-12-10 기준 Google Search Console은 사이트당 최대 500개의 사이트맵 색인 파일 제출을 허용하며, Search Console을 통해 제출한 사이트맵에는 기본 상위 디렉터리 범위 제한이 적용되지 않는다. [6][7]
- 2025-12-10 기준 Google의 이미지 사이트맵 확장(http://www.google.com/schemas/sitemap-image/1.1)은 url 요소당 최대 1,000개의 image:image 태그를 허용하며, Google은 문서에서 image:caption, image:geo_location, image:title, image:license 태그를 제거했다. [8]
- Google의 뉴스 사이트맵 확장(http://www.google.com/schemas/sitemap-news/0.9)은 사이트맵당 최대 1,000개의 news:news 항목을 허용하며, 최근 2일 이내에 발행된 기사만 포함하도록 규정한다. [9]

## 연표

- 2008-02-27: sitemaps.org가 Google, Inc., Yahoo, Inc., Microsoft Corporation을 후원사로 명시하고 크리에이티브 커먼즈 저작자표시-동일조건변경허락 2.5 라이선스를 규정한 이용약관을 갱신한다. [3]
- 2016-11-21: sitemaps.org가 50MB(52,428,800바이트) 및 50,000 URL 제한과 sitemap.xsd, siteindex.xsd XML 스키마를 문서화한 FAQ를 갱신한다. [2]
- 2022-05: Google 검색 센터 블로그가 일부 사이트맵 확장 태그의 종료를 알리는 공지를 게시한다. [8][10]
- 2022-09: IETF가 robots.txt 파서 구현자가 사이트맵 같은 추가 행을 정의할 수 있다고 ABNF 형식 구문에 명시한 RFC 9309(로봇 배제 프로토콜)를 발행한다. [4]
- 2023-06: Google 검색 센터 블로그가 Google의 사이트맵 핑 엔드포인트가 종료될 예정임을 공지한다. [10]
- 2025-12-10: Google 검색 센터가 사이트맵 개요, 사이트맵 색인 파일, 이미지 사이트맵 문서를 갱신한다. [5][7][8]

## 출처

1. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (확인일 2026-11-23; tier 3: official site)
2. sitemaps.org - FAQ. sitemaps.org. 게시일 2016-11-21. https://www.sitemaps.org/faq.html (확인일 2026-11-23; tier 3: official site)
3. sitemaps.org - Terms of service. sitemaps.org. 게시일 2008-02-27. https://www.sitemaps.org/terms.html (확인일 2026-11-23; tier 3: official site)
4. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 게시일 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (확인일 2026-11-23; tier 1: government or public registry)
5. What Is a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. 게시일 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview (확인일 2026-11-23; tier 3: official site)
6. Build and Submit a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (확인일 2026-11-23; tier 3: official site)
7. Manage Your Sitemaps With Sitemap Index Files | Google Search Central | Documentation | Google for Developers. Google Search Central. 게시일 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/large-sitemaps (확인일 2026-11-23; tier 3: official site)
8. Image Sitemaps | Google Search Central | Documentation | Google for Developers. Google Search Central. 게시일 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps (확인일 2026-11-23; tier 3: official site)
9. Create a News Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap (확인일 2026-11-23; tier 3: official site)
10. Sitemaps ping endpoint is going away | Google Search Central Blog | Google for Developers. Google Search Central Blog. 게시일 2023-06. https://developers.google.com/search/blog/2023/06/sitemaps-lastmod-ping (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "사이트맵." 버전 2adc345c, 2026-11-23. https://mimirwiki.com/ko/wiki/sitemaps
