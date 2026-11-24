---
title: "JSON-LD"
subtitle: "링크드 데이터를 JSON으로 직렬화하는 W3C 표준 형식"
canonical_url: https://mimirwiki.com/ko/wiki/json-ld
language: ko
page_class: anchor
revision_sha256: f2ee60c9ff42bbf13e723ef66c0d2e96d1d60e39ad05f64e81da4e91e99cbc82
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/json-ld.md
  txt: https://mimirwiki.com/ko/wiki/json-ld.txt
  json: https://mimirwiki.com/ko/wiki/json-ld.json
  jsonld: https://mimirwiki.com/ko/wiki/json-ld.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-ld
  ja: https://mimirwiki.com/ja/wiki/json-ld
  zh: https://mimirwiki.com/zh/wiki/json-ld
---

# JSON-LD

> JSON-LD는 링크드 데이터를 유효한 JSON 형식으로 직렬화하는 W3C 표준 권고안이다. 컨텍스트를 통해 JSON 객체의 키를 전역 식별자에 연결하므로 애플리케이션이 여러 웹사이트에 흩어진 데이터를 해석하고 연결할 수 있다. 2014년 1.0 버전으로 표준화된 뒤 2020년 1.1 버전으로 개정됐으며, RDF 그래프 변환, 프로그램 기반 문서 변환, Schema.org 같은 HTML 구조화 데이터 마크업을 지원한다.

JSON-LD(JSON for Linking Data)는 웹에서 링크드 데이터(Linked Data)를 JSON 기반 구문으로 직렬화하기 위해 월드 와이드 웹 컨소시엄(World Wide Web Consortium, W3C)이 제정한 권고안(Recommendation)이다. 모든 JSON-LD 문서는 RFC 8259에 부합하는 유효한 JSON이므로 기존 JSON 파서, 웹 서비스, JSON 기반 저장소에서 그대로 처리할 수 있으며, 여기에 전역 리소스 식별자, 컨텍스트(Context), 언어 태그, 데이터 타입, 방향 그래프 표현 기능을 덧붙인다. W3C는 2014년 1월 16일 JSON-LD 1.0을 발행했고, 2020년 7월 16일 구문, 처리 알고리즘 및 API, 프레이밍(Framing)으로 구성된 JSON-LD 1.1 표준 세트로 이를 대체했다. 애플리케이션은 JSON-LD를 일반 JSON으로 직접 다루거나 자원 기술 프레임워크(Resource Description Framework, RDF) 그래프 및 데이터셋으로 변환해 활용할 수 있으며, Schema.org 같은 구조화 데이터 어휘를 HTML 문서에 삽입하는 데에도 쓴다.

**다른 이름:** JSON for Linked Data, JSON for Linking Data, JSON-LD 1.0, JSON-LD 1.1

## 핵심 정보

- **표준화 기구:** 월드 와이드 웹 컨소시엄(W3C) [1]
- **최초 W3C 권고안:** JSON-LD 1.0(2014-01-16) [4]
- **현재 W3C 권고안:** JSON-LD 1.1(2020-07-16) (기준 2026-11-23) [1]
- **기반 구문:** JSON(RFC 8259) [1]
- **HTML script 유형:** application/ld+json [8]

## 기본 정보

- **유형:** 링크드 데이터를 위한 JSON 기반 직렬화 형식 [1]
- **표준화 기구:** 월드 와이드 웹 컨소시엄(W3C) [1]
- **담당 그룹:** W3C JSON-LD 워킹 그룹(헌장 기간 2028년 1월까지) (기준 2026-11-23) [7]
- **최초 권고안:** JSON-LD 1.0(2014-01-16 발행, 2020-11-03 대체 처리) [4]
- **현재 권고안:** JSON-LD 1.1(2020-07-16) (기준 2026-11-23) [1]
- **함께 발행된 1.1 권고안:** 처리 알고리즘 및 API, 프레이밍 [1]
- **1.1 버전 편집자:** 그레그 켈로그(Gregg Kellogg), 피에르앙투안 샹팽(Pierre-Antoine Champin), 데이브 롱리(Dave Longley) [1]
- **1.0 버전 편집자:** 마누 스포니(Manu Sporny), 그레그 켈로그(Gregg Kellogg), 마르쿠스 란탈러(Markus Lanthaler) [4]
- **기반 형식:** JSON(IETF RFC 8259) [5]
- **데이터 모델 호환성:** RDF 1.1 그래프 및 RDF 데이터셋 [6]
- **명세 저장소:** github.com/w3c/json-ld-syntax [10]

## JSON-LD의 개요와 설계 목적

JSON-LD(JSON for Linking Data)는 링크드 데이터(Linked Data)를 JSON으로 직렬화하기 위해 월드 와이드 웹 컨소시엄(W3C)이 표준화한 경량 구문이다.[1][7] 링크드 데이터는 서로 다른 문서와 웹사이트에 걸쳐 기계가 해석할 수 있는 데이터를 표준 방식으로 연결해, 애플리케이션이 한 데이터에서 출발해 다른 사이트에 호스팅된 관련 리소스로 링크를 따라가게 한다.[1][7] JSON-LD는 웹 기반 프로그래밍 환경, 상호운용 가능한 REST 웹 서비스, Apache CouchDB나 MongoDB 같은 JSON 기반 저장소에서 링크드 데이터를 다루는 용도에 맞추어 설계됐다.[1][7]

모든 JSON-LD 문서는 IETF RFC 8259(이전 RFC 7159와 RFC 4627을 대체한 표준)가 정의하는 유효한 JSON이므로 기존 JSON 파서와 라이브러리를 그대로 재사용할 수 있다.[1][4][5] JSON-LD 1.0은 원래 RFC 4627을 참조했고, JSON-LD 1.1에서는 기반 JSON 표준 참조를 RFC 8259로 갱신했다.[1][4] JSON-LD는 일반 JSON의 기본 자료형(문자열, 숫자, 불리언, `null`)과 구조 자료형(객체, 배열)에 더해 IRI를 이용한 전역 객체 식별, 컨텍스트(Context)를 통한 키와 IRI의 매핑, 외부 웹 리소스 참조, 문자열 언어 표기, 날짜·시간 같은 값의 데이터 타입 지정, 단일 문서 내 방향 그래프 표현 기능을 제공한다.[1][5]

JSON-LD 1.0 명세는 단순성, 호환성, 표현력, 간결성, 기존 JSON 시스템의 변경 최소화, RDF 활용 가능성이라는 여섯 가지 설계 목표를 제시했다.[4] 기본적인 활용에서는 별도의 전용 처리기 없이도 JSON과 두 키워드(`@context`, `@id`)만 알면 문서를 작성할 수 있다.[4] 이미 운영 중인 JSON API에서는 서버가 HTTP 응답에 링크 관계를 추가해 기존 JSON 문서를 JSON-LD로 해석하도록 지정하는 방식도 지원한다.[1][4]

## JSON-LD 구문, 컨텍스트, 핵심 키워드

JSON-LD는 JSON 객체와 배열 문법을 바탕으로 하되 고유한 구조 규칙과 `@` 기호로 시작하는 예약 키워드를 둔다.[1] JSON-LD에서는 하나의 JSON 객체 안에 들어가는 멤버 이름이 반드시 고유해야 하며, 이는 객체 이름을 고유하게 두도록 권고하는 수준인 RFC 8259보다 엄격하다.[1][5] 일반 JSON에서 배열은 순서를 유지하는 시퀀스이며, JSON-LD에서는 명시적으로 리스트(List)로 정의된 경우를 제외하면 배열을 기본적으로 순서 없는 컬렉션으로 취급한다.[1][5]

JSON-LD의 기본 구문은 웹 규모에서 데이터의 의미를 명확히 구분하기 위한 컨텍스트와 핵심 키워드를 중심으로 동작한다.[1][4]

- `@context`: JSON 문서에서 쓰는 짧은 속성 용어를 전체 IRI에 매핑해 여러 JSON 문서가 같은 키 이름을 쓰더라도 의미가 섞이지 않게 한다. 컨텍스트는 `https://schema.org/`나 `https://json-ld.org/contexts/person.jsonld` 같은 URL로 참조할 수 있으며, 컨텍스트 안에서 용어나 그 `@id`에 `null`을 지정하면 해당 용어와 IRI의 연결을 명시적으로 해제한다.[1][7][8]
- `@id`: 노드 객체(Node Object)에 IRI 형태의 전역 식별자를 부여해 다른 객체나 외부 문서가 같은 리소스를 가리킬 수 있게 한다.[1][4][7]
- `@type`: Schema.org의 `Recipe`나 `Person`처럼 노드 객체의 유형을 지정하거나 값의 데이터 타입을 지정하며, `@set`과 함께 쓸 수도 있다.[1][8]
- `null`: 문서 본문에서 값을 무시하거나 초기화하고 `@context` 내부에서는 용어 매핑을 해제하는 데 쓴다.[1]

JSON-LD 1.1은 JSON-LD 1.0의 상위 집합으로, 별도로 명시된 경우를 제외하면 1.0 문서를 그대로 호환한다.[1] JSON-LD 1.1 명세에는 1.1 처리 모드, 기본 어휘(Default Vocabulary), 기준 IRI(Base IRI), 축약 IRI(Compact IRI), 키워드 별칭, 범위 지정 컨텍스트(Scoped Context), 컨텍스트 전파, 컨텍스트 가져오기(Imported Context), 보호된 용어 정의(Protected Term Definition), JSON 리터럴(JSON Literal), 타입 강제 변환(Type Coercion), 문자열 국제화와 기본 텍스트 방향(Base Direction), 중첩 속성, 역속성(Reverse Property), 포함 노드(Included Node), 다양한 색인 맵(데이터, 속성 기반, 언어, 노드 식별자, 노드 유형 색인), 그래프 컨테이너를 포함한 명명된 그래프(Named Graph) 기능이 수록되어 있다.[1]

## JSON-LD 문서 형태, 처리 API, 프레이밍

JSON-LD는 방향 그래프를 표현하므로 동일한 정보를 여러 형태로 직렬화할 수 있다.[1][3] 프로그램에서 데이터를 일정한 구조로 처리할 수 있도록 JSON-LD 1.1 표준 세트는 확장(Expanded), 압축(Compacted), 평탄화(Flattened), 프레이밍(Framed)이라는 네 가지 문서 형태를 정의한다.[1]

함께 발행된 W3C 권고안인 JSON-LD 1.1 처리 알고리즘 및 API(JSON-LD 1.1 Processing Algorithms and API)는 문서 형태 간 변환 알고리즘과 RDF 변환 알고리즘을 규정하고, Web IDL로 기술된 `JsonLdProcessor` 인터페이스와 `JsonLdOptions` 설정 유형을 정의한다.[2] 주요 처리 기능에는 컨텍스트 처리(용어 정의 생성, 역컨텍스트 생성, 용어 선택), 확장(IRI 및 값 확장), 압축(IRI 및 값 압축), 평탄화(노드 맵 생성·병합 및 공백 노드 식별자 생성), 원격 문서와 컨텍스트 조회, HTML 콘텐츠 처리 알고리즘, 데이터 왕복 변환을 포함한 RDF 직렬화 및 역직렬화가 포함된다.[2]

세 번째 W3C 권고안인 JSON-LD 1.1 프레이밍(JSON-LD 1.1 Framing)은 `JsonLdProcessor`와 `JsonLdOptions`를 확장해 개발자가 예시 기반 질의(query by example)를 수행하고 JSON-LD 그래프에 특정 트리 구조를 강제할 수 있게 한다.[3] 링크드 데이터 그래프는 독립적인 진술(트리플)의 집합이고 애플리케이션은 주로 중첩된 JSON 객체 트리를 다루므로, 프레임(Frame)은 각 주어에 관한 진술을 `{`와 `}` 구분자로 묶고 관련 주어를 애플리케이션이 기대하는 계층으로 중첩하는 방식을 지정한다.[3] 프레이밍 명세는 속성 일치, 와일드카드 일치, 속성 부재 일치, 값 일치, `@id` 일치, 빈 프레임, 기본 콘텐츠, 역프레이밍, 명명된 그래프 프레이밍을 지원하며, 객체 임베드(Object Embed), 명시적 포함(Explicit Inclusion), 기본값 생략(Omit Default), 그래프 생략(Omit Graph), 전체 필수(Require All)라는 다섯 가지 프레이밍 플래그를 정의한다.[3]

## JSON-LD와 RDF 데이터 모델의 관계

JSON-LD는 자원 기술 프레임워크(Resource Description Framework, RDF)를 모르는 개발자가 일반 JSON처럼 바로 쓸 수 있게 설계되었으며, 동시에 RDF 기반 시스템에서도 그대로 활용할 수 있다.[1][4] 2014년 2월 25일 발행된 W3C 권고안 RDF 1.1 개념 및 추상 구문(RDF 1.1 Concepts and Abstract Syntax)은 RDF 데이터를 저장하고 교환하는 직렬화 구문으로 Turtle과 함께 JSON-LD를 명시하고, 이를 RDF Schema 및 SPARQL 질의 언어와 연결한다.[6]

RDF 1.1 추상 구문은 정보를 두 가지 핵심 구조로 구성한다. RDF 그래프는 주어-술어-목적어 트리플(Triple)의 집합으로 각 노드는 IRI, 리터럴(데이터 타입이 지정된 값 또는 언어 태그가 붙은 문자열), 공백 노드(Blank Node)가 될 수 있고, RDF 데이터셋은 기본 그래프 하나와 0개 이상의 명명된 그래프로 이루어진다.[6] RDF에서 IRI는 전역 범위를 가지므로 서로 다른 위치에 나타난 같은 IRI는 동일한 리소스를 가리키며 웹에서 역참조(dereference)할 수 있는 출발점 역할을 한다.[6]

JSON-LD 1.1 구문 명세와 처리 알고리즘 및 API 명세는 JSON-LD 문서를 RDF 데이터셋으로 역직렬화하고 RDF 데이터셋을 JSON-LD로 직렬화하는 결정적 알고리즘을 규정해 Turtle이나 TriG와 같은 RDF 구문으로 쓰이게 한다.[1][2] JSON-LD 1.1의 기능을 RDF로 매핑하기 위해 구문 명세는 `rdf:JSON` 데이터 타입, `i18n` 네임스페이스, 그리고 `rdf:language` 및 `rdf:direction` 속성을 갖춘 `rdf:CompoundLiteral` 클래스를 정의한다.[1] 또한 JSON-LD 1.1 명세는 Turtle, RDFa, Microdata 등 다른 링크드 데이터 및 구조화 마크업 형식과의 관계를 설명하며, JSON-LD 1.0 명세는 Microformats와의 비교도 함께 다루었다.[1][4]

## HTML 삽입, Schema.org, 검색 엔진에서의 JSON-LD 활용

JSON-LD 문서는 HTML 페이지 안에 직접 삽입할 수 있으며, 이 기능은 JSON-LD 1.0과 JSON-LD 1.1 명세 모두에 포함되어 있다.[1][4] JSON-LD 1.1 명세는 HTML `script` 요소에 JSON-LD를 삽입하는 규칙, HTML `base` 요소로부터 기준 IRI를 상속받는 방식, JSON-LD `script` 요소 내용의 제약 사항, 특정 JSON-LD `script` 요소를 찾는 방법을 다룬다.[1] W3C 명세에는 IANA 고려 사항(IANA Considerations) 부록이 포함되어 있으며, Google 검색 센터의 구조화 데이터 가이드는 HTML 문서의 `head` 안에 `type="application/ld+json"` 속성을 지정한 `script` 요소로 JSON-LD를 넣는 사례를 보여 준다.[1][4][8]

공개 웹에서 JSON-LD는 [Schema.org](https://mimirwiki.com/ko/wiki/schema-org)와 함께 쓰인다. Schema.org는 Google, Microsoft, Yandex, Yahoo! 같은 주요 검색 엔진이 웹 페이지의 의미를 해석할 수 있도록 공유 어휘를 제공한다.[9] Schema.org 어휘는 Microdata, RDFa, JSON-LD 세 가지 형식으로 작성할 수 있으며, Schema.org 사이트의 대부분 예제는 세 형식을 함께 제시한다.[9] Schema.org의 유형 계층은 `name`, `description`, `url`, `image` 속성을 지닌 최상위 유형 `Thing`에서 시작해 `CreativeWork`(`Book`, `Movie`, `MusicRecording`, `Recipe`, `TVSeries` 등), `Event`, `Organization`, `Person`, `Place`, `LocalBusiness`, `Product`, `Review` 같은 하위 유형으로 분화한다.[9]

Google 검색 센터 문서는 Google 검색이 페이지에 포함된 JSON-LD 구조화 데이터(예: 중첩된 `Person` 작성자 객체를 포함하는 Schema.org `Recipe` 데이터)를 읽어 페이지 콘텐츠를 분류하고 사람·책·기업에 관한 정보를 파악하며 리치 결과(Rich Results)를 표시하는 방식을 설명한다.[8] Schema.org와 Google 검색 센터는 모두 구조화 데이터가 해당 페이지에서 사용자에게 보이는 콘텐츠를 설명해야 한다고 명시하며, 마크업만 담는 빈 페이지를 만들거나 숨겨진 요소에 마크업을 넣지 않도록 안내한다.[8][9] Wix, WordPress, Shopify 같은 콘텐츠 관리 시스템(CMS)을 쓰는 사이트 운영자는 각 플랫폼의 설정 화면이나 플러그인으로 구조화 데이터를 구성할 수 있으며, Google의 리치 결과 테스트(Rich Results Test) 도구로 마크업 유효성을 검사하고 지원 기능을 미리 확인할 수 있다.[8]

## JSON-LD 버전 이력, 거버넌스, 구현 생태계

JSON-LD는 JSON for Linking Data 커뮤니티 그룹에서 출발해 W3C RDF 워킹 그룹으로 이관됐으며, 2014년 1월 16일 JSON-LD 1.0과 JSON-LD 1.0 처리 알고리즘 및 API가 W3C 권고안으로 발행됐다(편집자 마누 스포니, 그레그 켈로그, 마르쿠스 란탈러, 공동 저자 데이브 롱리, 니클라스 린드스트룀).[2][4] 이후 JSON-LD 1.1 작업은 JSON-LD 커뮤니티 그룹 최종 보고서를 바탕으로 W3C JSON-LD 워킹 그룹이 맡았다.[1] 워킹 그룹은 2019년 12월 12일 후보 권고안(Candidate Release), 2020년 5월 7일 권고 제안(Proposed Recommendation)을 거쳐 2020년 7월 16일 세 편의 JSON-LD 1.1 W3C 권고안을 발행했다(편집자 그레그 켈로그, 피에르앙투안 샹팽, 데이브 롱리).[1][2][3] W3C는 2020년 11월 3일 JSON-LD 1.0을 대체된 권고안(Superseded Recommendation)으로 지정해 신규 구현이 JSON-LD 1.1을 따르도록 안내하는 한편, 1.0 명세에 대한 W3C 특허 정책 라이선스 약정은 유지했다.[4]

| 명세 | 발행일 | 범위 | 저장소 |
| --- | --- | --- | --- |
| JSON-LD 1.1 | 2020-07-16 | 링크드 데이터 구문, 컨텍스트, 키워드, HTML 삽입, RDF 매핑 | `w3c/json-ld-syntax` |
| JSON-LD 1.1 Processing Algorithms and API | 2020-07-16 | 확장, 압축, 평탄화, RDF 변환, `JsonLdProcessor` API | `w3c/json-ld-api` |
| JSON-LD 1.1 Framing | 2020-07-16 | 예시 기반 그래프 일치 및 결정적 트리 구조 생성 | `w3c/json-ld-framing` |

세 명세는 모두 W3C JSON-LD 워킹 그룹의 공식 권고안 세트를 이룬다.[1][2][3][10]

2026-11-23 기준 W3C JSON-LD 워킹 그룹은 2028년 1월까지 이어지는 헌장 아래 공식 명세 거버넌스를 담당하고 있으며, 누구나 참여할 수 있는 JSON-LD 커뮤니티 그룹이 커뮤니티 초안, 논의 회의, 메일링 리스트를 운영한다.[7] GitHub의 공개 `w3c/json-ld-syntax` 저장소는 JSON-LD 1.1 초안이 기능 동결(Feature Frozen) 상태임을 명시해 이슈 접수를 버그 수정, 기존 기능 명확화, 편집상 개선으로 제한하고 있다.[10]

2026-11-23 기준 json-ld.org는 마크업을 디버깅하고 시각화하는 웹 기반 JSON-LD 플레이그라운드(JSON-LD Playground)를 제공하며, 공식 테스트 스위트와 구현 보고서를 통해 처리기 적합성을 추적한다.[7] 같은 사이트는 JavaScript(`json-ld.js`, `jsonld-streaming-parser.js`, `jsonld-streaming-serializer.js`, `rdf-parse.js`), Python(`PyLD`, `RDFLib`, `TRLD`), Ruby(`JSON-LD for RDF.rb`), Go(`JSON-goLD`), Java(`Titanium`), C#(`dotNetRDF`), Erlang·Elixir(`JSON-LD.ex`), Rust(`sophia`, `oxjsonld`), 명령줄 도구(`jsonld-cli`, `ld-cli`)의 JSON-LD 1.1 적합 구현체와 함께 PHP(`php-json-ld`, `JsonLD`), Java(`JSONLD-JAVA`), C#(`json-ld.net`)의 1.0 구현체를 목록으로 안내한다.[7] 또한 커뮤니티 초안들은 JSON-LD 데이터 모델을 확장해 사람이 작성하기 쉬운 YAML-LD, QR 코드·PDF417 바코드·NFC 태그 같은 공간 제약 환경을 위한 압축 이진 형식 CBOR-LD, 스트리밍(Streaming), JSON-LD-star 같은 관련 명세를 다루고 있다.[7]

## 자주 묻는 질문

### JSON-LD란 무엇인가요?

JSON-LD(JSON for Linking Data)는 웹에서 링크드 데이터를 JSON 기반 구문으로 직렬화하기 위해 W3C가 제정한 권고안입니다. 모든 JSON-LD 문서는 RFC 8259에 부합하는 유효한 JSON이면서 컨텍스트, 전역 IRI 식별자, 데이터 타입, 언어 표기, 방향 그래프 구조를 지원합니다. [1][5][7]

### JSON-LD에서 @context, @id, @type 키워드는 어떤 역할을 하나요?

@context는 짧은 JSON 속성 이름을 전체 IRI에 매핑해 서로 다른 문서 사이에서도 키의 의미가 명확하게 구분되도록 합니다. @id는 노드 객체에 전역 IRI 식별자를 부여하고, @type은 노드 객체의 유형이나 값의 데이터 타입을 지정합니다. [1][4][8]

### JSON-LD 1.1에서는 JSON-LD 1.0과 비교해 무엇이 달라졌나요?

2020년 7월 16일 세 편의 W3C 권고안으로 발행된 JSON-LD 1.1은 2014년 JSON-LD 1.0을 대체하면서도 별도 명시된 경우를 제외하면 1.0 문서와의 호환성을 유지합니다. 기반 JSON 표준 참조를 RFC 8259로 갱신하고 JSON-LD 프레이밍을 W3C 권고안으로 표준화했으며, 범위 지정 컨텍스트, JSON 리터럴, 문자열 기본 텍스트 방향, 확장된 색인 방식을 추가했습니다. [1][2][3][4]

### JSON-LD를 쓰려면 RDF를 알아야 하나요?

아닙니다. W3C 명세에 따르면 JSON-LD는 RDF에 관한 지식 없이 일반 JSON으로 직접 사용할 수 있습니다. 동시에 표준 RDF 직렬화 구문으로도 동작해 SPARQL 같은 도구에서 쓰이는 RDF 1.1 그래프 및 데이터셋과 상호 변환할 수 있습니다. [1][4][6]

### JSON-LD 처리 알고리즘 및 API와 프레이밍 명세는 무엇을 정의하나요?

JSON-LD 1.1 처리 알고리즘 및 API는 확장, 압축, 평탄화, RDF 변환 알고리즘과 JsonLdProcessor 인터페이스를 규정합니다. JSON-LD 1.1 프레이밍은 이 API를 확장해 개발자가 예시 기반 질의로 데이터를 선택하고 방향 그래프에 일정한 중첩 트리 구조를 적용할 수 있게 합니다. [2][3]

### 검색 엔진을 위해 JSON-LD를 HTML 페이지에 어떻게 넣나요?

HTML 문서의 head 등에 type 속성을 application/ld+json으로 지정한 script 요소를 두고 Schema.org 같은 어휘로 작성한 JSON-LD를 삽입합니다. Google 검색은 사용자에게 보이는 페이지 콘텐츠를 설명하는 인페이지 JSON-LD를 읽어 엔티티를 이해하고 리치 결과를 표시하며, 리치 결과 테스트 도구로 검증을 지원합니다. [1][8][9]

## 인용 문장

- W3C RDF 워킹 그룹은 2014년 1월 16일 JSON-LD 1.0을 W3C 권고안으로 발행했다. [4]
- W3C JSON-LD 워킹 그룹은 2020년 7월 16일 JSON-LD 1.1, JSON-LD 1.1 처리 알고리즘 및 API, JSON-LD 1.1 프레이밍을 W3C 권고안으로 발행했다. [1][2][3]
- W3C는 2020년 11월 3일 JSON-LD 1.0을 JSON-LD 1.1로 대체된 권고안으로 지정했다. [4]
- 모든 JSON-LD 1.1 문서는 IETF RFC 8259에 부합하는 유효한 JSON이며, 객체 멤버 이름이 고유하고 배열은 기본적으로 순서가 없는 컬렉션으로 취급된다. [1][5]
- RDF 1.1 개념 및 추상 구문 권고안은 RDF 데이터를 저장하고 교환하는 직렬화 구문으로 Turtle과 함께 JSON-LD를 명시한다. [6]
- JSON-LD 1.1 프레이밍은 예시 기반 질의와 방향 그래프에 대한 결정적 트리 구조 적용을 지원한다. [3]
- Schema.org는 Google, Microsoft, Yandex, Yahoo!가 이해하는 마크업 형식으로 Microdata, RDFa와 함께 JSON-LD를 지원한다. [9]
- 2026-11-23 기준 W3C JSON-LD 워킹 그룹의 헌장은 2028년 1월까지이며, w3c/json-ld-syntax GitHub 저장소는 JSON-LD 1.1 초안을 기능 동결 상태로 명시하고 있다. [7][10]

## 연표

- 2014-01-16: W3C RDF 워킹 그룹이 JSON-LD 1.0과 JSON-LD 1.0 처리 알고리즘 및 API를 W3C 권고안으로 발행한다. [2][4]
- 2014-02-25: W3C RDF 워킹 그룹이 JSON-LD를 RDF 직렬화 구문으로 명시한 RDF 1.1 개념 및 추상 구문을 W3C 권고안으로 발행한다. [6]
- 2017-12: IETF가 JSON-LD 1.1에서 참조하는 JSON 데이터 교환 형식 표준인 RFC 8259를 발행한다. [1][5]
- 2019-12-12: W3C JSON-LD 워킹 그룹이 JSON-LD 1.1, 처리 알고리즘 및 API, 프레이밍의 후보 권고안을 발행한다. [1][2][3]
- 2020-07-16: W3C JSON-LD 워킹 그룹이 JSON-LD 1.1, JSON-LD 1.1 처리 알고리즘 및 API, JSON-LD 1.1 프레이밍을 W3C 권고안으로 발행한다. [1][2][3]
- 2020-11-03: W3C가 JSON-LD 1.0을 JSON-LD 1.1로 대체된 권고안으로 지정한다. [4]

## 출처

1. JSON-LD 1.1. World Wide Web Consortium (W3C). 게시일 2020-07-16. https://www.w3.org/TR/json-ld11/ (확인일 2026-11-23; tier 1: government or public registry)
2. JSON-LD 1.1 Processing Algorithms and API. World Wide Web Consortium (W3C). 게시일 2020-07-16. https://www.w3.org/TR/json-ld11-api/ (확인일 2026-11-23; tier 1: government or public registry)
3. JSON-LD 1.1 Framing. World Wide Web Consortium (W3C). 게시일 2020-07-16. https://www.w3.org/TR/json-ld11-framing/ (확인일 2026-11-23; tier 1: government or public registry)
4. JSON-LD 1.0. World Wide Web Consortium (W3C). 게시일 2014-01-16. https://www.w3.org/TR/2014/REC-json-ld-20140116/ (확인일 2026-11-23; tier 1: government or public registry)
5. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 게시일 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (확인일 2026-11-23; tier 1: government or public registry)
6. RDF 1.1 Concepts and Abstract Syntax. World Wide Web Consortium (W3C). 게시일 2014-02-25. https://www.w3.org/TR/rdf11-concepts/ (확인일 2026-11-23; tier 1: government or public registry)
7. JSON-LD - JSON for Linked Data. JSON-LD Community Group. https://json-ld.org/ (확인일 2026-11-23; tier 3: official site)
8. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (확인일 2026-11-23; tier 3: official site)
9. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (확인일 2026-11-23; tier 3: official site)
10. GitHub - w3c/json-ld-syntax: JSON-LD 1.1 Specification · GitHub. W3C (GitHub). https://github.com/w3c/json-ld-syntax (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "JSON-LD." 버전 f2ee60c9, 2026-11-23. https://mimirwiki.com/ko/wiki/json-ld
