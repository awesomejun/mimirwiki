---
title: "hreflang"
subtitle: "링크된 웹 리소스의 언어와 대상 지역을 지정하는 HTML 속성이자 링크 매개변수"
canonical_url: https://mimirwiki.com/ko/wiki/hreflang
language: ko
page_class: anchor
revision_sha256: 8f491bbaa1e47c3e8ceb2adaed0f22109f34f35d188e11314a1d248b6312bb08
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/hreflang.md
  txt: https://mimirwiki.com/ko/wiki/hreflang.txt
  json: https://mimirwiki.com/ko/wiki/hreflang.json
  jsonld: https://mimirwiki.com/ko/wiki/hreflang.jsonld
translations:
  en: https://mimirwiki.com/wiki/hreflang
---

# hreflang

> hreflang은 RFC 5646의 BCP 47 언어 태그를 사용해 링크된 리소스의 언어와 선택적으로 지역을 나타내는 HTML 속성이자 링크 매개변수이다. 웹사이트는 HTML link 요소, HTTP Link 헤더, 또는 XML 사이트맵으로 hreflang 주석을 게시해 Google 검색이 사용자에게 맞는 현지화 페이지로 안내하도록 돕는다.

hreflang은 링크된 웹 리소스의 언어와 선택적으로 대상 지역을 나타내는 HTML 속성이자 링크 주석 매개변수이다. WHATWG HTML Living Standard에 반영 속성(reflected attribute)으로 정의되고 IETF RFC 5646이 규정한 BCP 47 언어 태그(language tag)를 값으로 쓰며, 앵커 요소에서는 브라우저 내장 동작 없이 외부 링크 처리기를 위한 메타데이터로 쓰인다. Google 검색에서 사이트는 alternate 링크 관계와 결합한 hreflang 주석을 HTML link 요소, RFC 8288이 정의한 HTTP Link 헤더, 또는 XML 사이트맵(XML sitemap)으로 제공해 한 페이지의 현지화 버전을 서로 연결한다. Google은 나열된 버전 사이의 양방향 링크를 요구하며, 일치하는 언어나 지역이 없을 때 보여 줄 기본 페이지에 x-default 값을 지원한다.

**다른 이름:** hreflang 속성, hreflang 태그, hreflang 주석, rel=alternate hreflang

## 핵심 정보

- **HTML 표준:** WHATWG HTML Living Standard(2026-11-22 갱신) (기준 2026-11-23) [1]
- **언어 태그 표준:** IETF BCP 47 / RFC 5646(2009년 9월) [2]
- **하위 태그 레지스트리:** IANA 언어 하위 태그 레지스트리(파일 날짜 2026-11-18) (기준 2026-11-23) [4]
- **HTTP 헤더 표준:** IETF RFC 8288(Web Linking, 2017년 10월) [3]
- **Google 전달 방식:** HTML link 요소, HTTP Link 헤더, XML 사이트맵 (기준 2026-11-23) [6]

## 기본 정보

- **유형:** 링크된 URL의 언어를 안내하는 HTML 속성 [9]
- **HTML 표준:** WHATWG HTML Living Standard 4.6절(2026-11-22 갱신) (기준 2026-11-23) [1]
- **DOM API:** HyperlinkElementUtils.hreflang(반영 DOMString) [1]
- **언어 태그 문법:** IETF BCP 47(RFC 5646, 2009년 9월, RFC 4646 대체) [2]
- **하위 태그 레지스트리:** IANA 언어 하위 태그 레지스트리(파일 날짜 2026-11-18) (기준 2026-11-23) [4]
- **HTTP 헤더 표준:** IETF RFC 8288(Web Linking, 2017년 10월, RFC 5988 대체) [3]
- **HTML link 지원 기준:** HTML link 요소는 2015년 7월부터 주요 브라우저 전반에서 지원 [8]
- **Google 전달 방식:** HTML link 요소, HTTP Link 헤더, XML 사이트맵 (기준 2026-11-23) [6]
- **기본 대체 값:** x-default(2013년 4월 Google 검색 센터 블로그 발표) [10]
- **확인 규칙:** Google 검색에서 자기 참조와 양방향 링크 필수 (기준 2026-11-23) [6]

## hreflang이란

hreflang은 링크된 웹 리소스의 언어와 선택적으로 대상 지역을 나타내는 HTML 속성이자 링크 주석 매개변수이다.[6][9] HTML에서 링크는 `a`, `area`, `form`, `link` 요소가 만드는 두 리소스 사이의 개념적 연결이며, 외부 리소스 링크, 하이퍼링크(hyperlink), 내부 리소스 링크의 세 종류로 나뉜다.[1]

2026년 11월 22일 갱신된 WHATWG HTML Living Standard 4.6.3절은 `HyperlinkElementUtils` 인터페이스 믹스인에 `hreflang`을 반영 `DOMString` 속성으로 정의한다.[1] MDN Web Docs는 현재 문서와 외부 리소스의 관계를 지정하는 HTML `link` 요소와 하이퍼링크를 생성하는 HTML `a` 앵커 요소를 문서화하며, 두 요소 모두 2015년 7월부터 주요 브라우저 전반에서 지원됐다고 기록한다.[8][9] MDN은 `a` 요소의 `hreflang` 속성이 링크된 URL의 언어를 안내하고 브라우저 내장 동작이 없으며 전역 `lang` 속성과 같은 언어 태그 값을 허용한다고 설명한다.[9]

Google 검색에서 웹사이트는 `alternate` 링크 관계와 `hreflang`을 함께 지정해 여러 언어나 지역별 페이지 버전을 알리고, 검색 결과가 사용자의 언어나 지역에 맞는 버전으로 연결되도록 한다.[6]

## hreflang에 쓰이는 BCP 47과 RFC 5646 언어 태그

hreflang 값은 2009년 9월 발행된 IETF RFC 5646("Tags for Identifying Languages")이 규정하는 BCP 47 언어 태그(language tag)를 따른다.[2][5][9] A. 필립스(A. Phillips)와 M. 데이비스(M. Davis)가 편집한 RFC 5646은 RFC 4646(이전 RFC 3066과 RFC 1766을 대체)을 대체하며, RFC 4647과 함께 BCP 47을 이룬다.[2][5]

BCP 47 언어 태그는 하이픈(`-`, U+002D)으로 구분된 하나 이상의 영숫자 하위 태그(subtag)로 이루어지며, `language-extlang-script-region-variant-extension-privateuse` 순서를 따른다.[2][5] 각 하위 태그의 유형은 길이, 위치, 문자 구성만으로 구별되므로 RFC 3066 시기에 등록된 고정 구버전 태그(grandfathered tag)를 제외하면 레지스트리 사본 없이도 하위 태그 종류를 판별할 수 있다.[2]

| 하위 태그 유형 | 형식 | 근거 표준 | 예시 |
| --- | --- | --- | --- |
| 기본 언어(primary language) | 영문자 2~3자(또는 등록된 5~8자) | ISO 639 | `en`, `es`, `ast`, `mas` |
| 확장 언어(extended language) | 거시언어 하위 태그 뒤 영문자 3자 | ISO 639 | `zh-yue`, `ar-afb` |
| 문자 체계(script) | 영문자 4자(RFC 4646에서 도입) | ISO 15924 | `zh-Hans`, `az-Latn` |
| 지역(region) | 영문자 2자 또는 숫자 3자리 | ISO 3166-1 / UN M.49 | `fr-CA`, `en-GB`, `de-CH`, `es-419` |
| 변이형(variant) | 영숫자 5~8자, 또는 숫자 1자리와 영숫자 3자 | IANA 레지스트리 | 등록된 방언 및 정서법 하위 태그 |
| 확장 및 사설 사용(extension / private use) | 단일 영숫자 접두어(`x`는 사설 사용 예약) | RFC 5646 | 단일 문자 확장, `x-` 사설 사용 태그 |

유효한 모든 하위 태그는 단일 일반 텍스트 파일인 IANA 언어 하위 태그 레지스트리(IANA Language Subtag Registry)에서 관리되며, 2026-11-23 기준 파일 날짜는 2026-11-18이다.[4][5] 레지스트리는 언어당 하나의 ISO 639 값을 채택해 2자리 코드가 있으면 이를 쓰고 없으면 3자리 코드 하나를 수록하며, RFC 5646 발행 당시 7,000개 이상의 ISO 639-3 3자리 코드가 추가됐다.[5] 레지스트리 항목에는 `Type`, `Subtag`, `Description`, `Added`, `Suppress-Script`, `Scope`, `Deprecated`, `Preferred-Value` 같은 필드가 포함된다.[4][5] 예를 들어 `bh`(Bihari languages) 항목은 2026-06-14에 폐기 표시됐으며 `Preferred-Value`로 `bih`가 지정되어 있다.[4]

W3C는 HTML과 XML에서 언어 태그가 대소문자를 구분하지 않으며 언어는 소문자, 문자 체계는 첫 글자 대문자, 영문 지역 코드는 대문자로 적는 방식이 관례일 뿐이라고 설명한다.[5] W3C는 태그를 가능한 한 짧게 유지하고 구별에 필요할 때만 지역이나 문자 체계 하위 태그를 붙이며, `en`, `es`, `fr`의 `Latn`처럼 `Suppress-Script`가 지정된 기본 문자 체계는 생략하도록 안내한다.[4][5] `zh-yue`나 `ar-afb` 같은 기존 확장 언어 조합에는 대응하는 단독 기본 언어 하위 태그(`yue`, `afb`)가 존재하며, W3C는 가능한 경우 단독 기본 언어 하위 태그를 쓰도록 안내한다.[5]

## hreflang 주석의 구현 방식

2026-11-23 기준 Google 검색 센터 문서는 hreflang 주석을 전달하는 동등한 세 가지 방법으로 HTML `link` 요소, HTTP `Link` 헤더, [XML 사이트맵](https://mimirwiki.com/ko/wiki/sitemaps)(XML sitemap)을 제시한다.[6] Google은 세 방식을 동등하게 취급하며, 같은 페이지에 여러 방식을 함께 적용해도 검색상 추가 이점 없이 관리 부담만 커진다.[6]

| 방식 | 위치와 구문 | 주요 활용 사례 |
| --- | --- | --- |
| HTML `link` 요소 | `head` 요소 안에 `rel="alternate"`, `hreflang`, `href` 속성을 지정한 `link` 요소 | 사이트맵이나 HTTP 헤더를 제어하기 어려운 HTML 페이지 |
| HTTP `Link` 헤더 | GET 응답에 각 URL을 꺾쇠괄호로 감싸고 `rel="alternate"`와 `hreflang`을 쉼표로 구분해 나열한 `Link` 헤더 | PDF 같은 비 HTML 파일 |
| XML 사이트맵 | `xhtml` XML 네임스페이스를 선언하고 각 `loc` 요소 아래에 `xhtml:link` 하위 항목 나열 | 다국어 URL 집합의 중앙 집중식 관리 |

HTML 방식에서는 올바르게 구성된 `head` 요소 안에 페이지 자신을 포함한 모든 버전별 `link` 요소를 넣어야 한다.[6][8] XHTML 1.0에서는 `link` 같은 빈 요소(void element) 끝에 슬래시가 필요하다.[8] Google은 `hreflang` 주석을 독립된 `link` 요소에 두고, 단일 `link` 요소 안에서 `media` 같은 다른 대체 표현 속성과 결합하지 않도록 규정한다.[6]

HTTP 헤더 방식은 2017년 10월 M. 노팅엄(M. Nottingham)이 작성하고 RFC 5988을 대체한 IETF RFC 8288("Web Linking")에 바탕을 둔다.[3] RFC 8288은 링크 컨텍스트, 링크 관계 유형, 링크 대상, 선택적 대상 속성으로 구성된 웹 링크 모델과 HTTP `Link` 헤더 직렬화를 정의하며 RFC 5646의 `Language-Tag` 문법을 포함한다.[3] `alternate` 같은 등록 링크 관계 유형은 IANA 링크 관계 레지스트리(IANA Link Relations registry)에서 관리된다.[3] Google 검색에서 GET 응답에 포함하는 `Link` 헤더는 각 버전의 완전한 URL을 꺾쇠괄호로 감싸고 `rel="alternate"`와 `hreflang`을 붙여 쉼표로 구분하며, 한 리소스의 모든 버전이 동일한 헤더를 반환해야 한다.[6]

[XML 사이트맵](https://mimirwiki.com/ko/wiki/sitemaps) 방식에서는 각 현지화 버전마다 `loc` 요소를 두고, 그 아래에 자기 자신을 포함한 모든 언어 및 지역 버전을 나열한 `xhtml:link` 하위 항목을 추가하며 `xhtml` 네임스페이스를 선언한다.[6] 한 페이지에 세 가지 버전이 있으면 사이트맵에 세 개의 `loc` 항목이 들어가고 각 항목마다 동일한 세 개의 `xhtml:link` 하위 항목이 포함된다.[6]

## hreflang의 상호 링크와 URL 규칙

Google 검색은 현지화 페이지 집합에 속한 모든 URL이 서로를 검증할 수 있도록 HTML `link` 요소, HTTP `Link` 헤더, XML 사이트맵 세 방식 모두에 공통 구조 규칙을 적용한다.[6]

- **자기 참조와 전체 목록 기재**: 페이지의 각 언어 및 지역 버전은 자기 자신과 다른 모든 버전을 함께 나열해야 하며, 집합 내 모든 페이지의 주석 목록이 동일해야 한다.[6]
- **양방향 확인(bidirectional confirmation)**: 두 페이지가 서로를 가리키지 않으면 Google은 해당 주석을 무시한다. 이 규칙은 외부 사이트가 다른 사이트 페이지의 대체 버전으로 임의 등록하는 행위를 막는다.[6]
- **부분 양방향 링크**: 모든 언어 사이에 완전한 양방향 링크를 유지하기 어려운 경우 일부 페이지에서 일부 언어를 생략할 수 있다. Google은 서로 가리키는 쌍을 계속 처리하며, 새로 추가한 언어 페이지는 사이트의 원래 언어나 주력 언어 페이지와 양방향으로 연결하도록 안내한다.[6]
- **완전한 URL(fully-qualified URL)**: 모든 대체 URL에는 `https://example.com/foo`처럼 전송 방식(`http` 또는 `https`)을 포함해야 하며, 프로토콜 생략 URL(`//example.com/foo`)이나 상대 경로(`/foo`)는 허용되지 않는다.[6]
- **도메인 간 연결**: 대체 URL이 같은 도메인에 있을 필요는 없다.[6]
- **일반 언어 포괄 URL**: `en-IE`, `en-CA`, `en-AU`처럼 같은 언어의 여러 지역 URL을 운영할 때 Google은 지역이 지정되지 않은 사용자를 위한 일반 언어 항목(`en`)도 함께 제공하도록 안내하며, 이 항목에 기존 지역 URL 중 하나를 쓸 수 있다.[6]

Google은 URL에 포함된 언어별 하위 도메인(`en`, `en-gb`, `en-us`, `de` 등)으로 페이지의 대상 사용자를 추정하지 않으므로, 모든 대상 언어와 지역을 `hreflang` 주석으로 명시해야 한다.[6]

## 대체 기본 페이지를 지정하는 x-default hreflang 값

`x-default` hreflang 값은 페이지에 명시된 어떤 언어나 지역 버전과도 일치하지 않는 방문자를 위한 기본 대체 URL을 지정한다.[6] Google 검색 센터 블로그는 2013년 4월 국제 랜딩 페이지를 위한 `x-default` hreflang 도입을 발표했고, 이후 2023년 5월 "How x-default can help you"라는 제목의 게시물을 아카이브에 등재했다.[10]

Google 검색 센터 문서는 특히 언어 및 국가 선택 페이지나 방문자를 자동으로 리디렉션하는 홈 페이지에 `x-default`를 지정하도록 안내한다.[6] Google의 문서 예시는 영국 영어(`en-GB`), 미국 영어(`en-US`), 일반 영어(`en`), 독일어(`de`) 페이지를 운영하는 사이트가 언어와 지역 선택기를 갖춘 기본 페이지 `https://www.example.com/`에 `hreflang="x-default"`를 지정하는 구성을 보여 준다.[6]

`x-default` 값은 HTML `link` 요소, HTTP `Link` 헤더, XML 사이트맵에서 표준 BCP 47 언어 태그와 함께 사용할 수 있다.[6]

## Google 검색의 hreflang과 다국어 사이트 처리

Google 검색은 hreflang 주석을 사용해 같은 콘텐츠의 현지화 버전을 파악하고 검색자의 언어나 지역 설정에 맞는 버전을 제시한다.[6] Google은 둘 이상의 언어로 콘텐츠를 제공하는 다국어 웹사이트(예: 영어와 프랑스어 버전을 제공하는 캐나다 기업)와 서로 다른 국가 사용자를 겨냥하는 다지역 웹사이트(예: 캐나다와 미국에 배송하는 제조사)를 구분하며, 한 사이트가 둘 다에 해당할 수 있다고 설명한다.[7]

Google 검색은 페이지의 언어를 감지할 때 `hreflang`, HTML `lang` 속성, URL을 사용하지 않는다.[6][7] Google은 페이지에 표시된 콘텐츠를 알고리즘으로 분석해 언어를 판별하며, 각 페이지의 본문과 내비게이션을 단일 언어로 유지하고 병렬 번역 배치를 피하도록 안내한다.[6][7]

Google은 `hreflang`을 적용하는 주요 사례 세 가지를 제시한다. 포럼처럼 사용자 생성 콘텐츠 본문은 한 언어로 두고 내비게이션과 바닥글 템플릿만 번역한 경우, 미국과 영국 및 아일랜드 영어처럼 한 언어 안에서 작은 지역 차이가 있는 경우, 그리고 사이트 콘텐츠 전체를 여러 언어로 번역한 경우이다.[6] 페이지의 현지화 버전은 주요 본문이 번역되지 않은 채 남아 있을 때만 중복 콘텐츠로 간주된다.[6]

Google은 각 언어 버전에 별도의 URL을 부여하고 `hreflang` 주석으로 연결하도록 안내한다.[7] 쿠키나 브라우저 설정으로 콘텐츠 언어를 동적으로 바꾸면 Googlebot이 모든 변형을 발견하지 못할 수 있는데, Googlebot이 주로 미국에서 크롤링하고 HTTP 요청에 `Accept-Language` 헤더를 포함하지 않기 때문이다.[7] Google은 추정된 사용자 언어에 따른 자동 리디렉션을 피하고 사용자가 직접 버전을 전환할 수 있는 하이퍼링크를 제공하도록 안내하며, UTF-8 인코딩과 적절한 URL 이스케이프 처리를 전제로 현지화된 URL 단어와 국제화 도메인 이름(Internationalized Domain Name, IDN)을 지원한다.[7]

## 자주 묻는 질문

### hreflang이란 무엇인가요?

hreflang은 BCP 47 언어 태그를 사용해 링크된 웹 리소스의 언어와 선택적으로 대상 지역을 나타내는 HTML 속성이자 링크 주석 매개변수입니다. Google 검색에서 웹사이트는 alternate 링크 관계와 hreflang을 함께 사용해 한 페이지의 현지화 버전을 연결합니다. [2][6][9]

### Google 검색에서 hreflang을 구현하는 방법에는 무엇이 있나요?

2026-11-23 기준 Google 검색은 head 요소 안의 HTML link 요소, PDF 같은 비 HTML 파일에 유용한 HTTP Link 응답 헤더, XML 사이트맵의 xhtml:link 하위 항목 등 동등한 세 가지 방법을 지원합니다. 둘 이상의 방법을 동시에 써도 검색상 추가 이점은 없습니다. [6]

### hreflang 링크가 양방향이어야 하는 이유는 무엇인가요?

Google 검색은 현지화 페이지 집합의 모든 페이지가 자기 자신과 다른 모든 버전을 가리키도록 요구하며, 서로를 가리키지 않는 쌍은 무시합니다. 이 확인 규칙은 다른 웹사이트가 통제권이 없는 페이지의 대체 버전으로 임의 등록하는 일을 막기 위한 것입니다. [6]

### hreflang="x-default"는 무엇을 의미하나요?

x-default 값은 명시된 어떤 hreflang 태그와도 언어나 지역이 일치하지 않는 사용자를 위한 기본 페이지를 지정합니다. Google은 2013년 4월 x-default를 발표했으며, 언어 및 국가 선택 페이지나 자동 리디렉션 홈 페이지에 쓰는 사례를 문서화하고 있습니다. [6][10]

### Google 검색은 페이지의 언어를 감지할 때 hreflang을 사용하나요?

아닙니다. Google 검색은 페이지 언어를 감지할 때 hreflang, HTML lang 속성, URL을 사용하지 않습니다. Google은 페이지에 표시된 콘텐츠를 알고리즘으로 분석해 언어를 판별하며, hreflang은 같은 콘텐츠의 현지화 버전을 연결하는 용도로 사용합니다. [6][7]

### hreflang의 언어와 지역 코드는 어떤 형식을 따르나요?

언어 태그는 IETF BCP 47(RFC 5646)을 따르며 IANA 언어 하위 태그 레지스트리의 하위 태그를 하이픈으로 연결해 구성합니다. 보통 2자리 또는 3자리 ISO 639 기본 언어 하위 태그로 시작하고, 필요에 따라 4자리 ISO 15924 문자 체계 하위 태그나 2자리 ISO 3166-1 또는 3자리 UN M.49 지역 하위 태그를 붙이며, HTML과 XML에서 대소문자를 구분하지 않습니다. [2][4][5]

## 인용 문장

- 2026년 11월 22일 갱신된 WHATWG HTML Living Standard는 hreflang을 HyperlinkElementUtils 인터페이스 믹스인의 반영 DOMString 속성으로 정의한다. [1]
- MDN Web Docs는 HTML a 요소의 hreflang 속성이 링크된 URL의 언어를 안내하며 내장 동작이 없고 전역 lang 속성과 같은 값을 허용한다고 밝힌다. [9]
- 2009년 9월 BCP 47의 일부로 발행된 IETF RFC 5646은 하이픈으로 구분하는 언어 태그 하위 태그 문법을 규정하며 RFC 4646을 대체한다. [2]
- 유효한 언어, 문자 체계, 지역 하위 태그는 IANA 언어 하위 태그 레지스트리에서 관리되며, 2026-11-23 기준 파일 날짜는 2026-11-18이다. [4][5]
- 2017년 10월 발행된 IETF RFC 8288은 HTTP Link 헤더 필드를 규정하며 RFC 5646의 Language-Tag 문법을 참조한다. [3]
- 2026-11-23 기준 Google 검색 센터 문서는 hreflang 주석을 지정하는 동등한 세 가지 방법으로 HTML link 요소, HTTP Link 헤더, XML 사이트맵을 제시한다. [6]
- Google 검색은 두 페이지가 서로를 가리키고 각 페이지가 자기 자신과 모든 대체 버전을 나열하지 않으면 두 페이지 사이의 hreflang 주석을 무시한다. [6]
- Google 검색 센터 블로그는 2013년 4월 국제 랜딩 페이지를 위한 x-default hreflang 값을 발표했다. [10]

## 연표

- 2009-09: IETF가 BCP 47의 일부로 RFC 5646(Tags for Identifying Languages)을 발행해 RFC 4646을 대체하고, 7,000개 이상의 ISO 639-3 3자리 언어 코드를 IANA 언어 하위 태그 레지스트리에 추가한다. [2][5]
- 2013-04: Google 검색 센터 블로그가 국제 랜딩 페이지를 위한 x-default hreflang 도입을 발표한다. [10]
- 2015-07: MDN Web Docs 기준 HTML link 요소와 a 요소가 주요 브라우저 전반의 기본 지원 상태에 도달한다. [8][9]
- 2017-10: IETF가 RFC 5988을 대체하는 RFC 8288(Web Linking)을 발행해 RFC 5646 언어 태그 문법을 포함하는 HTTP Link 헤더 직렬화를 규정한다. [3]

## 출처

1. HTML Standard. WHATWG. 게시일 2026-11-22. https://html.spec.whatwg.org/multipage/links.html (확인일 2026-11-23; tier 1: government or public registry)
2. RFC 5646: Tags for Identifying Languages. Internet Engineering Task Force (IETF). 게시일 2009-09. https://www.rfc-editor.org/rfc/rfc5646.txt (확인일 2026-11-23; tier 1: government or public registry)
3. RFC 8288: Web Linking. Internet Engineering Task Force (IETF). 게시일 2017-10. https://www.rfc-editor.org/rfc/rfc8288.txt (확인일 2026-11-23; tier 1: government or public registry)
4. IANA Language Subtag Registry. Internet Assigned Numbers Authority (IANA). 게시일 2026-11-18. https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry (확인일 2026-11-23; tier 1: government or public registry)
5. Language tags in HTML and XML. World Wide Web Consortium (W3C). https://www.w3.org/International/articles/language-tags/ (확인일 2026-11-23; tier 1: government or public registry)
6. Localized Versions of your Pages | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/localized-versions (확인일 2026-11-23; tier 3: official site)
7. Managing Multi-Regional and Multilingual Sites | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (확인일 2026-11-23; tier 3: official site)
8. <link> HTML external resource link element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/link (확인일 2026-11-23; tier 3: official site)
9. <a> HTML anchor element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a (확인일 2026-11-23; tier 3: official site)
10. Introducing "x-default hreflang" for international landing pages | Google Search Central Blog | Google for Developers. Google Search Central Blog. 게시일 2013-04. https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "hreflang." 버전 8f491bba, 2026-11-23. https://mimirwiki.com/ko/wiki/hreflang
