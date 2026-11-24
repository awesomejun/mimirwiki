---
title: "Schema.org"
subtitle: "검색 엔진과 여러 애플리케이션을 위해 웹 페이지의 구조화 데이터를 마크업하는 공유 어휘"
canonical_url: https://mimirwiki.com/ko/wiki/schema-org
language: ko
page_class: anchor
revision_sha256: d615078fea7000c9801f0e5a814ddc01e0d51c1708eb773f4b2ea5066b599ca7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ko/wiki/schema-org.md
  txt: https://mimirwiki.com/ko/wiki/schema-org.txt
  json: https://mimirwiki.com/ko/wiki/schema-org.json
  jsonld: https://mimirwiki.com/ko/wiki/schema-org.jsonld
translations:
  en: https://mimirwiki.com/wiki/schema-org
---

# Schema.org

> Schema.org는 웹 페이지의 제품, 레시피, 이벤트, 조직 같은 개체를 기계가 읽을 수 있게 기술하기 위해 2011년 Google, Microsoft, Yahoo, Yandex가 공동 설립한 공유 구조화 데이터(structured data) 어휘다. 게시자는 JSON-LD, Microdata, RDFa 형식으로 이를 작성할 수 있다. 2026년 9월 16일 발표된 버전 30.1(2026-11-23 기준)에는 826개 유형과 1,540개 속성이 정의되어 있으며 CC BY-SA 3.0 라이선스로 제공된다.

Schema.org는 검색 엔진과 여러 애플리케이션이 웹 페이지의 내용을 이해할 수 있도록 구조화 데이터(structured data)를 삽입하는 데 쓰는 공동 어휘다. 2011년 Google, Microsoft, Yahoo, Yandex가 공동 설립했으며, RDF 스키마(RDF Schema)에서 파생된 다중 상속(multiple inheritance) 계층 구조를 유지하고 공식 기계 판독 표현을 RDF/Turtle로 배포한다. 웹 게시자는 JSON-LD, Microdata, RDFa 형식으로 HTML 페이지에 Schema.org 용어를 인코딩할 수 있으며, 2026년 9월 16일 발표된 버전 30.1(2026-11-23 기준)에는 826개 유형, 1,540개 속성, 19개 데이터 유형, 96개 열거형, 544개 열거형 멤버가 포함된다. 일상적인 어휘 발전은 W3C Schema.org 커뮤니티 그룹과 공개 GitHub 저장소에서 조율하며, 정식 릴리스는 운영 위원회(Steering Group)가 승인한다.

**다른 이름:** schema.org, 스키마닷오알지, Schema.org 어휘, 스키마 마크업

## 핵심 정보

- **설립:** 2011년(Google, Microsoft, Yahoo, Yandex) [4]
- **최신 릴리스:** 버전 30.1(2026-09-16) (기준 2026-11-23) [2]
- **어휘 규모:** 유형 826개, 속성 1,540개, 데이터 유형 19개, 열거형 96개, 열거형 멤버 544개 (기준 2026-11-23) [3]
- **지원 인코딩:** JSON-LD, Microdata, RDFa [5]
- **스키마 라이선스:** 크리에이티브 커먼즈 저작자표시-동일조건변경허락 3.0(CC BY-SA 3.0) [6]

## 기본 정보

- **유형:** 웹용 공유 구조화 데이터 어휘 [1]
- **설립 연도:** 2011년 [4]
- **설립 참여사:** Google, Microsoft, Yahoo, Yandex [1]
- **거버넌스:** Schema.org 운영 위원회 및 W3C Schema.org 커뮤니티 그룹 [1]
- **운영 위원회 의장:** R.V. 구하(R.V. Guha) (기준 2026-11-23) [1]
- **커뮤니티 그룹:** W3C Schema.org 커뮤니티 그룹(참여자 510명, 2015-03-31 출범) (기준 2026-11-23) [7]
- **최신 릴리스:** 버전 30.1(2026-09-16) (기준 2026-11-23) [2]
- **어휘 규모:** 유형 826개, 속성 1,540개, 데이터 유형 19개, 열거형 96개, 열거형 멤버 544개 (기준 2026-11-23) [3]
- **공식 기계 표현:** RDF/Turtle [4]
- **마크업 형식:** JSON-LD, Microdata, RDFa [5]
- **라이선스:** CC BY-SA 3.0(스키마, 문서, 예제), Apache-2.0(사이트 소프트웨어) [6]
- **저장소:** github.com/schemaorg/schemaorg(커밋 5,741건, 스타 6.3k) (기준 2026-11-23) [8]

## Schema.org란

Schema.org는 인터넷상의 구조화 데이터(structured data) 스키마를 만들고 유지하며 보급하는 공동 커뮤니티 활동이다.[1] Google, Microsoft, Yahoo, Yandex가 웹마스터에게 주요 검색 엔진 전반에서 통용되는 단일 마크업 어휘를 제공하기 위해 [사이트맵](https://mimirwiki.com/ko/wiki/sitemaps)(`sitemaps.org`)의 취지를 따라 2011년 공동 설립했다.[4][6] `schema.org` 도메인 이름은 OpenDomain 프로젝트에서 기증받았다.[6]

기본 HTML 요소는 `h1` 제목 표시처럼 브라우저가 화면에 텍스트를 그리는 방식만 알려 줄 뿐 해당 문자열이 영화인지 다른 대상인지 뜻까지 전달하지는 못한다.[5] Schema.org는 영화, 인물, 조직, 제품, 이벤트 같은 개체에 명시적인 기계 판독 라벨을 붙여 검색 엔진과 다른 소프트웨어가 다양한 사이트 구조 속에서도 페이지 내용을 일관되게 해석하도록 돕고, 오류가 잦은 자동 추출 의존도를 낮춘다.[5][6] 초기 어휘의 상당 부분은 Microformats, FOAF, OpenCyc 등 선행 작업에서 영향을 받았다.[6]

Schema.org는 참여 검색 엔진이 지원하는 스키마를 문서화하는 협력 활동이며, W3C나 IETF 같은 공식 표준 기구와는 구별된다.[6] Schema.org 마크업은 어떤 언어로 작성된 웹 페이지에서도 쓸 수 있으며, 어휘 용어 자체와 사이트 문서는 영어로 제공된다.[6] Facebook Open Graph 같은 프로토콜과 함께 쓰더라도 Schema.org는 한 페이지에 등장하는 여러 개체와 구성 요소를 세밀하게 기술하는 수단을 제공한다.[6]

## Schema.org의 데이터 모델과 어휘 구조

Schema.org는 CycL에서 유래한 RDF 스키마(RDF Schema)를 바탕으로 만든 범용 데이터 모델을 사용한다.[4] 스키마는 하나의 유형이 둘 이상의 상위 유형으로부터 속성을 물려받을 수 있는 다중 상속(multiple inheritance) 계층 구조로 구성된다.[4] 최상위 유형은 `name`, `description`, `url`, `image` 같은 기본 속성을 지닌 `Thing`이며, 하위 유형은 상위 유형의 속성을 상속받는다. 예를 들어 `LocalBusiness`는 `Place`와 `Organization`의 하위 유형으로서 두 상위 유형의 속성을 모두 물려받는다.[5]

Schema.org의 각 속성은 여러 도메인(`domainIncludes`)과 여러 범위(`rangeIncludes`)를 가질 수 있다. 이 설계는 속성 묶음만을 위해 인위적인 중간 유형을 대량으로 만드는 상황을 피하려는 실용적 결정이다.[4] 또한 `Class`와 `Property` 같은 메타 유형을 통해 스키마가 자기 자신의 정의를 표현하는 반영(reflection)을 지원한다.[4] Schema.org의 공식 기계 판독 표현은 RDF/Turtle 형식이며, 개발자 문서 페이지에서 RDF와 [JSON-LD](https://mimirwiki.com/ko/wiki/json-ld) 등 기계 판독용 파일을 내려받을 수 있다.[3][4]

2026년 9월 16일 발표된 버전 30.1(2026-11-23 기준)에서 Schema.org 어휘의 구성 요소 수는 다음과 같다.[2][3]

| 구성 요소 | 수량(버전 30.1, 2026-11-23 기준) |
| --- | --- |
| 유형(Types) | 826 |
| 속성(Properties) | 1,540 |
| 데이터 유형(Datatypes) | 19 |
| 열거형(Enumerations) | 96 |
| 열거형 멤버(Enumeration members) | 544 |

자주 쓰이는 Schema.org 유형군에는 창작물(`CreativeWork`, `Book`, `Movie`, `MusicRecording`, `Recipe`, `TVSeries`), 내장 미디어 객체(`AudioObject`, `ImageObject`, `VideoObject`), `Event`, 보건 및 의료 개체(`MedicalEntity`), `Organization`, `Person`, `Place`(`LocalBusiness`, `Restaurant`), `Product` 및 `Offer`(`AggregateOffer`), `Review` 및 `AggregateRating`, `Action`이 있으며, 텍스트와 숫자 등을 위한 기본 데이터 유형도 함께 정의된다.[3] 페이지와 주 개체의 관계를 나타내는 일반 속성으로는 해당 페이지의 핵심 대상을 가리키는 `mainEntity`와 `mainEntityOfPage`가 있으며, `url`, `sameAs`, `about`과 구분해 쓰인다.[4]

Schema.org는 포스텔의 법칙(Postel's Law)에 따른 실용적 적합성 원칙을 채택해 유형과 속성의 연결을 엄격한 형식 규칙에 가까운 강제 사항보다 지침으로 다룬다.[4] 하나의 개체 설명에 `Book`과 `Product`처럼 서로 독립된 여러 유형의 속성을 함께 넣을 수 있으며, 구조화된 개체 유형이 기대되는 속성에도 일반 텍스트 문자열이나 URL을 넣는 경우가 흔히 허용된다. `Role`과 `URL` 유형은 모든 속성에 사용할 수 있다.[4][5] 모든 속성은 기본적으로 여러 값을 가질 수 있고, 기반이 되는 RDF 트리플(triple) 모델에 따라 기본 다중 값은 순서가 없는 집합으로 취급된다.[4] 순서나 컬렉션 의미가 필요한 경우에는 RDF 리스트(`rdf:List`, JSON-LD에서는 `@list`로 표현)나 RDF 컨테이너(`rdf:Seq`, `rdf:Bag`, `rdf:Alt`)를 사용할 수 있으며, 이를 지원하는 파서에서는 속성의 선언된 범위가 컬렉션 내부의 개별 요소에 적용된다.[4]

Schema.org는 특수 분야를 `auto`, `bib`, `health-lifesci`, `meta`, `pending` 같은 호스팅 구획(hosted sections)으로 묶어 단일 어휘 집합의 뷰로 제공한다.[3] 논의와 검토가 진행 중인 신규 용어는 `pending` 구획에 배치되어 합의 전 변경될 수 있고, `meta` 구획은 기술 정의와 사이트 기능에 쓰이는 내부 어휘를 담으며, `attic` 영역은 핵심 어휘나 다른 구획에서 폐기되었거나 정식 채택되지 않은 용어를 보관하므로 게시자는 사용하지 않도록 안내된다.[3] 핵심 어휘와 달리 `pending`, `meta`, `attic` 영역은 정식 릴리스 없이도 수시로 갱신될 수 있다.[3] GS1 웹 어휘(GS1 Web Vocabulary)와 머신러닝 데이터셋용 메타데이터 어휘인 크루아상(Croissant) 같은 외부 확장(external extensions)은 운영 위원회의 공식 승인 없이 독립적으로 Schema.org를 확장한다.[3]

## Schema.org 인코딩 형식과 용어 식별자

Schema.org 용어는 [JSON-LD](https://mimirwiki.com/ko/wiki/json-ld), Microdata, RDFa의 세 가지 주요 직렬화 형식으로 웹 페이지에 삽입할 수 있다.[4][5][6] Schema.org는 초기 출범 당시 실용적 선택으로 Microdata에 초점을 맞췄으나, 이후 어휘 혼합이나 속성 관계 반전이 Microdata에서 까다롭다는 점을 고려해 RDFa와 JSON-LD까지 아우르도록 문서와 예제를 확장했다.[6]

| 형식 | 인코딩 방식 | 사양 및 특징 |
| --- | --- | --- |
| JSON-LD | HTML `script` 요소(`type="application/ld+json"`) 안에 `@context`와 `@type`을 포함한 JSON 객체로 삽입 | W3C 권고안(`JSON-LD 1.1`은 2020-07-16 발행, 2014-01-16의 `JSON-LD 1.0` 대체). JSON(RFC 8259)과 100% 호환되며 RDF 그래프와 상호 운용 가능 |
| Microdata | 콘텐츠 HTML 요소에 `itemscope`, `itemtype`, `itemprop` 속성을 직접 표기하고, 중첩 개체는 새 `itemscope` 블록으로 시작 | HTML5와 함께 도입. 항목 유형은 `https://schema.org/Movie` 같은 Schema.org URL로 지정 |
| RDFa(RDFa Lite) | 콘텐츠 HTML 요소에 `vocab="https://schema.org/"`, `typeof`, `property` 속성을 표기 | Microdata와 거의 일대일로 대응(`itemprop`은 `property`, `itemtype`은 `typeof`로 바꾸고 `itemscope`는 생략) |

위 표는 Schema.org, Google 검색 센터, W3C 사양 문서에 기술된 인코딩 방식을 정리한 것이다.[4][5][9][10] HTML 마크업에서 기계가 값을 명확히 해석하도록 돕기 위해 Schema.org는 날짜와 시간에 `YYYY-MM-DD` 형식(선택적으로 `T`와 `hh:mm` 또는 `hh:mm:ss` 결합)의 `datetime` 속성을 가진 HTML `time` 요소, 열거형과 표준 참조에 `href` 속성을 가진 HTML `link` 요소, 암시적 정보 표기에 `content` 속성을 가진 HTML `meta` 요소 사용법을 문서화한다.[5]

Schema.org는 출범 당시 `http:` 기반 웹사이트로 운영되며 RDF 용어 식별자에도 `http://schema.org/` URL을 사용했고, 이후 공개 웹사이트와 권장 예제를 `https://schema.org/`로 전환했다.[7] Schema.org 문서는 구조화 데이터 마크업에서 `https://schema.org`와 `http://schema.org`가 모두 유효하며 폭넓게 인식된다고 안내한다.[7] 정적 파일 호스팅으로 전환하면서 원격 JSON-LD 컨텍스트 제공 방식은 HTTP 콘텐츠 협상에서 `/docs/jsonldcontext.jsonld`를 가리키는 HTTP `Link` 헤더(`rel="alternate"`, `type="application/ld+json"`)로 바뀌었다.[7] 기존 파서들이 생성하는 RDF 트리플이 예기치 않게 달라지는 일을 막기 위해 이 컨텍스트 파일의 기준 URL은 계속 `http:`로 유지된다. 댄 브릭리(Dan Brickley)는 2026년 10월 30일 게시물에서 마크업이 `https://schema.org`를 참조하더라도 JSON-LD 파서가 여전히 `http://` 기반 트리플을 출력한다는 점을 짚으며, 데이터를 수집하는 측에서 식별자를 정규화(canonicalization)할 것을 권고했다.[7]

## Schema.org의 거버넌스, 저장소, 라이선스

Schema.org는 운영 위원회(Steering Group)와 W3C Schema.org 커뮤니티 그룹(Community Group)의 이원 거버넌스 구조로 운영된다.[1] 운영 위원회는 프로젝트 전반의 감독, 일상 운영 결정, 정식 릴리스 승인을 맡는다.[1] Google에서 Schema.org를 발의한 공동 설립자 R.V. 구하(R.V. Guha)가 개인 자격으로 운영 위원회 의장을 맡고 있으며(2026-11-23 기준), 설립 참여사인 Google, Microsoft, Yahoo, Yandex 대표와 W3C 대표, 주요 커뮤니티 기여자가 참여한다.[1] 2015년 4월 운영 위원회는 만장일치로 구성을 확대해 스테판 코를로스케(Stéphane Corlosquet), GoodRelations 작성자인 마르틴 헤프(Martin Hepp, 2014년부터 2017년까지 재임), W3C 대표 자리를 추가했다.[1] 운영 위원회의 논의는 공개되며, 회의록은 GitHub에 게시되어 이슈 #1에 연결된다.[1]

W3C Schema.org 커뮤니티 그룹은 댄 브릭리가 제안해 2015년 3월 31일 출범했으며, 2015년 4월부터 일상적인 스키마 논의, 제안 작성, 확장 검토의 주된 공개 포럼 역할을 맡고 있다.[1][7] W3C 계정을 갖고 W3C 커뮤니티 기여자 라이선스 계약(W3C Community Contributor License Agreement)에 동의하면 누구나 참여할 수 있으며, W3C는 그룹 호스팅이 W3C 회원사나 직원의 공식 승인을 뜻하지 않는다고 명시한다.[1][7] 2026-11-23 기준 커뮤니티 그룹 참여자는 510명이고, 의장은 댄 브릭리, 댄 스콧(Dan Scott), 스테판 코를로스케, 필 바커(Phil Barker), 필 아처(Phil Archer), 라이언 레버링(Ryan Levering) 등 6명이다.[7] 댄 브릭리는 일상 운영과 프로젝트 웹마스터 역할도 수행하며, 운영 위원회의 Google 대표 자격과는 별개로 Schema.org 프로젝트 측 의장으로 커뮤니티 그룹을 이끈다.[1] 논의는 `public-schemaorg@w3.org` 메일링 리스트와 GitHub에서 이루어지며, 보건 및 의료, 스포츠, 아카이브, 서지, 자동차 분야의 관련 W3C 커뮤니티 그룹들도 메인 커뮤니티 그룹과 GitHub 저장소를 통해 조율한다.[1][7]

Schema.org의 스키마(`data`), 문서(`docs`), 템플릿, `versions.json`, 사이트 소프트웨어(`software`, 상당 부분은 `sdopythonapp` 서브모듈에서 가져옴)는 공개 GitHub 저장소 `github.com/schemaorg/schemaorg`에서 관리된다.[8] 2026-11-23 기준 이 저장소에는 커밋 5,741건, 스타 6.3k, 포크 975건, 워처 388명, 열린 이슈 301건, 열린 풀 리퀘스트 14건이 기록되어 있다.[8] 이슈 #1은 릴리스 계획 색인으로, 이슈 #2와 #3은 어휘 변경과 도구 작업 분류에 쓰이며, 풀 리퀘스트는 지속적 통합(continuous integration) 테스트를 거치고 차기 릴리스 초안은 `staging.schema.org`에서 공개 검토된다.[1][2][8] 기여 지침은 검색 엔진을 포함해 웹 분석, 브라우저 부가 기능, 클라우드 도구 등 실제 데이터 소비 애플리케이션이 활용할 근거가 있는 점진적 개선과 추가를 우선하며, GoodRelations, GS1, IPTC rNews, MARC, BibFrame, FRBR, BBC, 유럽방송연맹(European Broadcasting Union), Music Ontology, MusicBrainz 같은 외부 표준 및 커뮤니티 설계와의 정합성을 중시한다.[8]

Schema.org의 스키마 정의, 사이트 문서, 블로그 글, 마크업 예제는 크리에이티브 커먼즈 저작자표시-동일조건변경허락 3.0(CC BY-SA 3.0) 라이선스로 배포된다.[6] 사이트 운영과 발행에 쓰이는 지원 소프트웨어에는 Apache-2.0 오픈소스 라이선스가 적용된다.[6][8]

## Schema.org 릴리스 이력

Schema.org는 운영 위원회와 커뮤니티의 최종 검토를 거쳐 버전이 붙은 정식 릴리스를 발표하며, 최신 공개 버전의 요약은 `https://schema.org/version/latest`에서 확인할 수 있다.[2][8] 2026-11-23 기준 최신 정식 릴리스는 2026년 9월 16일 발표된 버전 30.1이다.[2]

버전 30.1(2026-09-16)은 EU 디지털 제품 여권(EU Digital Product Passports) 탐색을 지원하는 어휘를 도입해 `DigitalProductPassport` 클래스, `hasDigitalProductPassport` 속성, `Certification`의 하위 유형인 `EnvironmentalProductDeclaration`과 `DeclarationOfConformity`, 제품 속성 `authorizedRepresentative`, `importer`, `recycledContentPercentage`, `substanceOfConcern`을 추가했다.[2] 같은 릴리스에는 `consumerNotice`, `isOftenBoughtWith`, `specification`, `valueGroup`, `itemPopularity`, `minimumOrderValue`, 열거형 값 `MaximumRetailPrice` 등 소매 제품 피드 어휘가 포함됐으며, 순서가 있는 목록에 대한 명시적 지원 문서화, 용어 사용 통계 갱신, `MedicalSpecialty`에 `Ophthalmology`와 `Audiology` 추가, 채택된 `pending` 용어의 정식 승격도 이루어졌다.[2]

버전 30.1을 포함한 최근 주요 릴리스 내역은 다음과 같다.[2]

| 버전 | 발표일 | 주요 추가 및 변경 사항 |
| --- | --- | --- |
| 30.1 | 2026-09-16 | EU 디지털 제품 여권 유형 및 속성, 소매 피드 어휘, 순서 있는 목록 문서화, pending 용어 정식 승격 |
| 30.0 | 2026-03-19 | GS1, Dublin Core, Open Graph 동등성 주석 및 내보내기, UN/CEFACT 코드에 맞춘 EU 디지털 제품 여권 예제, `Credential`과 `Error` 클래스, `Quantity`의 상위 유형을 `DataType`으로 변경 |
| 29.4 | 2025-12-08 | `ConferenceEvent`, `PerformingArtsEvent`, `InstantaneousEvent`, 인증 동작(`AuthenticateAction`, `LoginAction`, `ResetPasswordAction`), `OperatingSystem`, `RuntimePlatform`, `SequentialArt`(`GraphicNovel` 폐기), UN/CEFACT, OWL, OMG, GS1 온톨로지 OWL 동등성 |
| 29.3 | 2025-09-04 | `recipeIngredient` 범위 확장, `OnlineMarketplace` 및 `hasStore` / `isStoreOn` 추가 |
| 29.0 | 2025-03-24 | `FinancialIncentive` 어휘, `Legislation`의 유럽 입법 식별자(ELI) 속성, 배송 스키마 개편(`ShippingConditions`, `ShippingService`, `DeliveryTimeSettings` 폐기) |
| 28.0 | 2024-09-17 | 멤버십 및 로열티 프로그램 유형(`MemberProgram`, `MemberProgramTier`, `TierBenefitEnumeration`) |
| 27.02 | 2024-07-01 | 편집 스테이징 사이트를 `webschemas.org`에서 `staging.schema.org`로 이전 |
| 27.01 | 2024-06-24 | Schema.org 웹사이트 디자인 개편 |
| 27.0 | 2024-05-20 | `hasGS1DigitalLink` 및 `certificationRating` 추가 |

버전 29.1(2025-04-25)과 버전 29.2(2025-05-13) 패치 릴리스는 버전 29.0에서 발생한 오류를 수정하면서 `pronouns`, `companyRegistration`, `Cooperative`, `referee` 같은 속성과 유형을 추가했다.[2] `pending`, `meta`, `attic` 구획의 용어는 정식 릴리스 사이에도 갱신될 수 있다.[3]

## Schema.org의 검색 엔진 활용과 한계

Schema.org 마크업은 Google, Microsoft, Yahoo, Yandex 등 검색 엔진이 페이지의 개체를 이해하고 리치 결과(rich results)를 구성하는 데 활용된다.[5][6][9] Google 검색 센터 문서는 Article, Breadcrumb, Course list, Dataset, Discussion forum, Event, Fact check, Image metadata, Job posting, Local business, Organization, Product snippet, Merchant listing, Profile page, Q&A, Recipe, Review snippet, Software app, Speakable, Subscription and paywalled content, Vacation rental, Video 등의 구조화 데이터 기능을 안내한다.[9] 예를 들어 레시피 페이지에서 재료, 열량, 조리 시간을 구조화 데이터로 표기하면 Google 검색이 리치 결과를 표시하고 항목별 검색을 지원할 수 있다.[9] Wix, WordPress, Shopify 같은 콘텐츠 관리 시스템(CMS)은 HTML을 직접 편집하지 않고도 구조화 데이터를 설정할 수 있는 내장 설정이나 플러그인을 제공한다.[9]

게시자는 출처 문서에 안내된 두 가지 주요 검증 도구로 마크업을 점검할 수 있다. Schema.org 마크업 검증기(Schema.org Markup Validator)는 Schema.org 구조를 검사하고 RDF 컬렉션 표식(`List`, `Bag`, `Seq`, `Alt`)을 표시하며, Google의 리치 결과 테스트(Rich Results Test)는 구조화 데이터를 검증하고 Google 검색 기능 미리 보기를 제공한다.[4][9]

Schema.org와 검색 엔진 문서에는 구조화 데이터 활용과 관련한 몇 가지 경계와 한계가 명시되어 있다.

- **선별적 기능 지원**: Schema.org FAQ는 어휘에 정의된 모든 정보 유형이 검색 결과에 표시되지는 않는다고 밝히며, 각 검색 엔진의 공식 문서에서 지원하는 구체적 기능을 확인해야 한다고 안내한다.[6]
- **가시 콘텐츠 원칙**: Schema.org 지침과 Google 검색 센터 문서는 모두 페이지 방문자에게 실제로 보이는 콘텐츠만 마크업하도록 규정하며, 구조화 데이터만 담는 빈 페이지를 만들거나 정확한 정보라도 숨겨진 내용을 마크업하는 행위를 금지한다.[5][6][9]
- **선택적 및 부분적 마크업**: 한 항목의 모든 속성을 빠짐없이 표기할 의무는 없으며, 적합한 세부 유형이 없을 때는 마크업을 생략하거나 `Person` 같은 상위 유형을 쓰거나 확장을 정의할 수 있다.[6]
- **제한된 온톨로지 범위**: Schema.org는 실용적인 웹 게시를 위해 웹 콘텐츠를 단순화해 다루며, 포괄적인 도메인 온톨로지 모델링은 독립 어휘와 외부 확장의 몫으로 둔다.[4][8]
- **파서와 식별자의 이질성**: Schema.org는 모든 파서에 RDF 컬렉션이나 컨테이너 지원을 의무화하지 않으며, 웹 전반에 Microdata, RDFa, JSON-LD와 `http://` 및 `https://` 식별자가 혼재하므로 데이터 소비 측에서 식별자 정규화와 축약 문자열 처리가 필요하다.[4][7]

## 자주 묻는 질문

### Schema.org란 무엇인가요?

Schema.org는 웹 페이지에 기계가 읽을 수 있는 구조화 데이터를 추가하는 데 쓰는 유형과 속성의 공동 어휘입니다. 웹사이트가 주요 검색 엔진과 여러 애플리케이션 전반에서 공통 마크업 어휘를 사용할 수 있도록 2011년 Google, Microsoft, Yahoo, Yandex가 공동 설립했습니다. [1][4]

### Schema.org는 W3C 같은 공식 표준 기구인가요?

아닙니다. Schema.org는 주요 검색 엔진이 지원하는 스키마를 문서화하는 협력 활동이며, W3C나 IETF 같은 공식 표준 기구와는 구별됩니다. W3C는 공개 논의 공간으로 Schema.org 커뮤니티 그룹을 호스팅하지만, 그룹 활동이 W3C 회원사나 직원의 공식 승인을 뜻하지는 않습니다. [6][7]

### Schema.org는 어떤 마크업 형식으로 작성할 수 있나요?

게시자는 JSON-LD, Microdata, RDFa(RDFa Lite 포함) 형식으로 웹 페이지에 Schema.org 용어를 인코딩할 수 있습니다. Schema.org 어휘 자체의 공식 기계 판독 표현은 RDF/Turtle 형식으로 배포됩니다. [4][5][6]

### Schema.org 어휘의 규모는 어느 정도인가요?

2026년 9월 16일 발표된 버전 30.1(2026-11-23 기준)에서 Schema.org 어휘는 826개 유형, 1,540개 속성, 19개 데이터 유형, 96개 열거형, 544개 열거형 멤버로 구성됩니다. 이 밖에 검토 중인 용어를 두는 pending 구획과 폐기된 용어를 보관하는 attic 영역도 운영합니다. [2][3]

### Schema.org의 어휘와 소프트웨어에는 어떤 라이선스가 적용되나요?

Schema.org의 스키마, 사이트 문서, 블로그 글, 마크업 예제는 크리에이티브 커먼즈 저작자표시-동일조건변경허락 3.0(CC BY-SA 3.0) 라이선스로 공개됩니다. 사이트 발행에 쓰이는 지원 소프트웨어에는 Apache-2.0 오픈소스 라이선스가 적용됩니다. [6][8]

### Schema.org에 정의된 모든 유형이 검색 결과에 표시되나요?

아닙니다. Schema.org FAQ에 따르면 검색 엔진은 어휘에 정의된 모든 정보 유형을 검색 결과에 노출하지 않으며, 각 검색 엔진이 지원하는 기능과 유형을 별도 문서로 안내합니다. Google 검색 센터 문서 역시 페이지의 구조화 데이터가 해당 페이지에서 방문자에게 보이는 콘텐츠를 설명해야 한다고 규정합니다. [6][9]

## 인용 문장

- Schema.org는 웹 페이지용 공유 구조화 데이터 어휘를 제공하기 위해 2011년 Google, Microsoft, Yahoo, Yandex가 공동 설립했다. [1][4]
- W3C Schema.org 커뮤니티 그룹은 Schema.org의 변경 사항과 확장을 논의하는 공개 포럼으로 2015년 3월 31일 제안 및 출범했다. [7]
- 2026-11-23 기준 Schema.org의 최신 공개 릴리스는 2026년 9월 16일 발표된 버전 30.1이다. [2]
- 2026-11-23 기준 Schema.org 어휘는 826개 유형, 1,540개 속성, 19개 데이터 유형, 96개 열거형, 544개 열거형 멤버로 구성된다. [3]
- Schema.org 마크업은 JSON-LD, Microdata, RDFa 형식으로 웹 페이지에 작성할 수 있으며, 스키마의 공식 기계 판독 표현은 RDF/Turtle이다. [4][5]
- Schema.org의 스키마, 사이트 문서, 블로그 글, 마크업 예제는 크리에이티브 커먼즈 저작자표시-동일조건변경허락 3.0(CC BY-SA 3.0) 라이선스로 제공되며, 사이트 지원 소프트웨어에는 Apache-2.0 라이선스가 적용된다. [6][8]
- JSON-LD 1.1은 2014년 1월 16일의 JSON-LD 1.0 권고안을 대체하는 W3C 권고안으로 2020년 7월 16일 발행됐다. [10]
- Google 검색 센터 문서는 페이지의 구조화 데이터가 해당 페이지에서 사용자에게 보이는 콘텐츠를 설명해야 한다고 명시한다. [9]

## 연표

- 2011: Google, Microsoft, Yahoo, Yandex가 웹 페이지용 공유 구조화 데이터 어휘인 Schema.org를 출범한다. [4][8]
- 2014-01-16: W3C가 JSON-LD 1.0을 W3C 권고안으로 발행한다. [10]
- 2015-03-31: 댄 브릭리(Dan Brickley)가 W3C Schema.org 커뮤니티 그룹을 제안하고 출범한다. [7]
- 2015-04: Schema.org 운영 위원회가 커뮤니티 기여자인 스테판 코를로스케(Stéphane Corlosquet), 마르틴 헤프(Martin Hepp)와 W3C 대표를 포함하도록 확대되고, W3C 커뮤니티 그룹이 주요 협업 포럼이 된다. [1]
- 2020-07-16: W3C가 JSON-LD 1.0을 대체하는 JSON-LD 1.1을 W3C 권고안으로 발행한다. [10]
- 2024-07-01: Schema.org가 버전 27.02를 발표해 편집 스테이징 사이트를 webschemas.org에서 staging.schema.org로 이전한다. [2]
- 2025-03-24: Schema.org가 금융 인센티브, 유럽 입법 식별자(ELI) 속성, 개편된 배송 스키마를 담은 버전 29.0을 발표한다. [2]
- 2026-03-19: Schema.org가 GS1, Dublin Core, Open Graph 동등성 주석과 EU 디지털 제품 여권 예제를 추가한 버전 30.0을 발표한다. [2]
- 2026-09-16: Schema.org가 EU 디지털 제품 여권 유형, 소매 피드 속성, 순서가 있는 목록에 대한 명시적 문서를 추가한 버전 30.1을 발표한다. [2]

## 출처

1. About - Schema.org. Schema.org. https://schema.org/docs/about.html (확인일 2026-11-23; tier 3: official site)
2. Release listing - schema.org. Schema.org. 게시일 2026-09-16. https://schema.org/docs/releases.html (확인일 2026-11-23; tier 3: official site)
3. Schemas - Schema.org. Schema.org. https://schema.org/docs/schemas.html (확인일 2026-11-23; tier 3: official site)
4. Data model - Schema.org. Schema.org. https://schema.org/docs/datamodel.html (확인일 2026-11-23; tier 3: official site)
5. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (확인일 2026-11-23; tier 3: official site)
6. FAQ - schema.org. Schema.org. https://schema.org/docs/faq.html (확인일 2026-11-23; tier 3: official site)
7. Schema.org Community Group. World Wide Web Consortium (W3C). https://www.w3.org/community/schemaorg/ (확인일 2026-11-23; tier 1: government or public registry)
8. GitHub - schemaorg/schemaorg: Schema.org - schemas and supporting software · GitHub. Schema.org (GitHub). https://github.com/schemaorg/schemaorg (확인일 2026-11-23; tier 3: official site)
9. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (확인일 2026-11-23; tier 3: official site)
10. JSON-LD 1.1. World Wide Web Consortium (W3C). 게시일 2020-07-16. https://www.w3.org/TR/json-ld11/ (확인일 2026-11-23; tier 1: government or public registry)

## 이 문서 인용하기

Mimirwiki. "Schema.org." 버전 d615078f, 2026-11-23. https://mimirwiki.com/ko/wiki/schema-org
