---
title: "콘텐츠 전송 네트워크"
subtitle: "최종 사용자와 가까운 위치의 캐시 서버에서 웹 콘텐츠를 전달하는 지리적 분산 네트워크"
canonical_url: https://mimirwiki.com/ko/wiki/content-delivery-network
language: ko
page_class: concept
revision_sha256: 598079c47395f99ceed8e3a9b53b76ad16c4a48697f890b33d3d5b6a07a5f38e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/content-delivery-network.md
  txt: https://mimirwiki.com/ko/wiki/content-delivery-network.txt
  json: https://mimirwiki.com/ko/wiki/content-delivery-network.json
  jsonld: https://mimirwiki.com/ko/wiki/content-delivery-network.jsonld
translations:
  en: https://mimirwiki.com/wiki/content-delivery-network
  ja: https://mimirwiki.com/ja/wiki/content-delivery-network
  zh: https://mimirwiki.com/zh/wiki/content-delivery-network
---

# 콘텐츠 전송 네트워크

> 콘텐츠 전송 네트워크(CDN)는 웹 콘텐츠의 사본을 최종 사용자와 가까운 여러 위치에 분산 저장해 전달하는 서버 네트워크이다. 클라이언트와 원본 서버 사이에서 관리형 공유 HTTP 캐시로 동작하며, 응답 지연을 낮추고 원본 서버 부하를 줄이며 가용성을 높인다. 핵심 동작에는 HTTP 캐싱, 대상 지정 캐시 헤더, 애니캐스트 라우팅, CDN 상호 연결 프로토콜이 쓰인다.

콘텐츠 전송 네트워크(Content Delivery Network, CDN)는 웹 객체의 사본을 여러 지역의 서버에 분산 저장하고 최종 사용자와 가까운 위치에서 요청을 처리하는 시스템이다. 클라이언트와 원본 서버(origin server) 사이에서 관리형 공유 HTTP 캐시(managed shared cache)로 동작하며, 응답 지연을 줄이고 원본 서버의 부하를 낮추며 높은 트래픽 상황에서도 전송 안정성을 높인다. 핵심 동작은 HTTP 캐싱(RFC 9111), 대상 지정 캐시 제어(RFC 9213), 애니캐스트 서비스 분산(RFC 4786), CDN 상호 연결(RFC 6707, RFC 7336)을 다루는 국제인터넷표준화기구(IETF) 사양에 기반한다. 상용 CDN은 전 세계의 거점(Point of Presence, PoP)을 통해 정적 자산과 동적 웹 콘텐츠를 모두 전달하는 한편, 캐시 최신성 유지, 보안 노출, 외부 사업자 가용성 의존성 같은 운영상 한계도 수반한다.

**다른 이름:** CDN, Content Delivery Network, Content Distribution Network, 콘텐츠 배포 네트워크, 콘텐츠 전송망

## 핵심 정보

- **캐시 분류:** 관리형 공유 HTTP 캐시 [7]
- **HTTP 캐싱 표준:** RFC 9111(STD 98, 2022년 6월) [1]
- **대상 지정 캐시 헤더:** CDN-Cache-Control(RFC 9213, 2022년 6월) [2]
- **애니캐스트 라우팅 모범 사례:** RFC 4786(BCP 126, 2006년 12월), IGP 또는 BGP 기반 IPv4·IPv6 [5]
- **상호 연결 프레임워크:** CDNI 문제 정의(RFC 6707) 및 프레임워크(RFC 7336) [4]

## 기본 정보

- **분류:** 분산 네트워크 인프라 및 관리형 공유 HTTP 캐시 [7]
- **에지 노드:** 에지 로케이션 또는 거점(PoP)으로 불리는 지리적 분산 데이터 센터 [8]
- **원본 소스:** 권한 있는 HTTP 서버, 웹 서버 또는 오브젝트 스토리지 버킷 [8]
- **HTTP 캐싱 표준:** IETF RFC 9111(STD 98, 2022년 6월), RFC 7234 대체 [1]
- **대상 지정 캐시 제어:** CDN-Cache-Control 응답 헤더(IETF RFC 9213, 2022년 6월) [2]
- **대상 지정 필수 지시어:** max-age, must-revalidate, no-store, no-cache, private [2]
- **애니캐스트 기준 문서:** IETF RFC 4786(BCP 126, 2006년 12월), IPv4 및 IPv6 지원 [5]
- **CDNI 문제 정의:** IETF RFC 6707(Informational, 2012년 9월) [3]
- **CDNI 프레임워크:** IETF RFC 7336(Informational, 2014년 8월), RFC 6707과 함께 RFC 3466 대체 [4]
- **주요 전송 대상:** 정적 자산(HTML, CSS, JavaScript, 이미지, 미디어) 및 동적 웹 콘텐츠 [8]
- **CloudFront 기본 캐시 만료 시간:** 24시간(최소 0초, 고정 상한 없음) (기준 2026-11-23) [8]
- **클라이언트 무결성 보호:** 외부 정적 자산 CDN용 하위 리소스 무결성(SRI) [6]

## 콘텐츠 전송 네트워크 아키텍처와 거점(PoP)

콘텐츠 전송 네트워크(Content Delivery Network, CDN)는 웹 데이터의 복제본을 여러 지역의 서버에 저장하고 최종 사용자와 가까운 위치에서 요청을 처리하는 분산 캐시 서버 집합이다.[6][8] 원본 서버(origin server)는 HTML 문서, 스타일시트(CSS), JavaScript 파일, 이미지, 미디어 파일 같은 웹 객체의 원본을 보관하며, 일반 웹 서버나 사용자 지정 HTTP 서버, Amazon S3 버킷 같은 오브젝트 스토리지 서비스가 원본 역할을 맡는다.[6][8] 에지 로케이션(edge location) 또는 거점(Point of Presence, PoP)은 CDN이 사용자 근처에 객체 사본을 캐시하기 위해 여러 지역의 데이터 센터에 배치한 서버 집합이다.[8]

클라이언트가 CDN으로 제공되는 객체를 요청하면 네트워크는 지연 시간이 낮은 에지 로케이션으로 요청을 보낸다.[8] 요청한 객체의 유효한 사본이 해당 에지 로케이션에 이미 있으면 서버가 원본 서버에 접속하지 않고 즉시 응답을 반환한다.[7][8] 사본이 없으면 에지 서버가 지정된 원본 서버에서 원본 객체를 가져와 전달하고, 이후 요청을 위해 로컬에 사본을 저장한다.[8] 지리적 거리는 지연 시간에 비례해 영향을 미치므로 서버를 사용자 가까이에 둘수록 응답 속도가 빨라진다.[6] Amazon CloudFront 같은 상용 CDN은 자체 백본 네트워크(AWS 백본 네트워크)를 통해 요청을 라우팅해 경유하는 중간 네트워크 수를 줄이고, 첫 바이트 도달 시간(지연)을 낮추며 전송 속도를 높이는 동시에 여러 에지 로케이션에 사본을 유지해 가용성을 확보한다.[8]

HTTP 아키텍처에서 CDN은 서비스 운영자가 명시적으로 배치하는 관리형 공유 캐시(managed shared cache)로 기능하며, 원본 서버의 요청 파싱, 쿠키 기반 세션 복원, 데이터베이스 조회, 템플릿 렌더링 부하를 덜어 준다.[7] RFC 6707은 캐시 가능한 콘텐츠에 CDN을 적용할 때 얻는 주요 효과로 전송 비용 절감, 최종 사용자 체감 품질 향상, 전송 안정성 강화를 든다.[3] CDN은 Bootstrap이나 jQuery 같은 정적 라이브러리, 전체 정적 웹사이트, 동적 웹 콘텐츠 전송에 널리 쓰인다.[6][8] 2026-11-23 기준 Amazon CloudFront는 원본 서버 지정, 로깅, 기본 또는 사용자 지정 도메인, 비공개 콘텐츠용 서명된 URL(signed URL)과 서명된 쿠키(signed cookie) 같은 배포 구성을 모든 에지 로케이션에 전파하고 실제 객체는 요청 시 가져와 캐시하며, 단독 사이트용 표준 배포(standard distribution)와 SaaS 플랫폼용 다중 테넌트 배포(CloudFront SaaS Manager)를 제공한다.[8] 2026-11-23 기준 CloudFront는 에지 로케이션의 기본 캐시 만료 시간을 24시간(최소 0초, 고정 상한 없음)으로 두고, 에지 로케이션에서 나가는 데이터 전송량과 HTTP·HTTPS 요청 수에 과금하며, Amazon S3, Elastic Load Balancing, Amazon API Gateway 같은 AWS 원본에서 CloudFront로 이동하는 데이터 전송에는 요금을 부과하지 않는다.[8]

## 콘텐츠 전송 네트워크의 HTTP 캐싱 동작(RFC 9111)

콘텐츠 전송 네트워크의 캐싱 동작은 국제인터넷표준화기구(IETF)가 2022년 6월 발행한 표준 트랙 문서 RFC 9111(STD 98) HTTP Caching에 기반한다.[1] R. Fielding(Adobe), M. Nottingham(Fastly), J. Reschke(greenbytes)가 편집한 RFC 9111은 기존 RFC 7234를 대체하며, HTTP 캐시를 응답 메시지의 로컬 저장소와 저장·조회·삭제를 제어하는 하위 시스템으로 정의한다.[1]

HTTP 캐싱 사양은 캐시를 단일 사용자 전용인 비공개 캐시(private cache, 주로 웹 브라우저 내장 캐시)와 여러 사용자가 응답을 공유하도록 중간 경로에 두는 공유 캐시(shared cache)로 나눈다.[1][7] MDN Web Docs는 공유 캐시를 다시 서비스 개발자가 직접 관리하지 않는 프록시 캐시(proxy cache)와 리버스 프록시, CDN, Cache API를 결합한 서비스 워커(service worker) 같은 관리형 캐시(managed cache)로 구분한다.[7] HTTPS 암호화가 보편화되면서 경로상의 일반 프록시 캐시는 대부분 암호화된 트래픽을 터널링할 뿐 응답을 열람하거나 캐시하지 못하며, 조직이 관리하는 인증 기관(CA) 인증서로 트래픽을 복호화하는 기업용 TLS 브리지 프록시 환경에서만 예외적으로 캐싱이 이루어진다.[7]

캐시는 최소한 요청 메서드와 대상 URI로 구성한 캐시 키(cache key)를 사용해 저장된 응답을 찾으며, 실제 운영 환경의 많은 캐시는 `GET` 응답만 URI 기준으로 저장한다.[1] 콘텐츠 협상(content negotiation)이 적용되는 리소스에는 `Vary` 응답 헤더에 지정된 요청 헤더 값을 캐시 키에 함께 넣는다.[1] 캐시에 가장 흔히 저장되는 대상은 `GET` 요청의 `200 (OK)` 응답이지만, 조건을 충족하면 리다이렉트, `404 (Not Found)`, `206 (Partial Content)` 응답도 저장할 수 있다.[1] RFC 9111 제3절에 따르면 공유 캐시는 응답에 `no-store`가 있거나, 수정된 공유 저장을 허용하지 않는 `private` 지시어가 있거나, 공유 캐싱을 명시적으로 허용하는 지시어 없이 요청에 `Authorization` 헤더가 포함된 경우 응답을 저장해서는 안 된다.[1] 응답을 저장하려면 캐시가 요청 메서드와 최종 상태 코드를 인식해야 하며, `public`, `Expires`, `max-age`, `s-maxage`, 캐시 확장 지시어, 또는 휴리스틱 캐싱이 허용된 상태 코드 가운데 하나 이상이 존재해야 한다.[1]

저장된 HTTP 응답은 원본 서버 확인 없이 재사용할 수 있는 최신(fresh) 상태와 유효 기간이 지나 재검증(validation)이 필요한 만료(stale) 상태로 나뉘며, 원본 서버와 연결이 끊긴 캐시는 허용된 조건에서 만료된 응답을 제공할 수 있다.[1][7] 유효 기간을 나타내는 음이 아닌 초 단위 정수(`delta-seconds`)는 31비트 오버플로를 막기 위해 상한을 `2147483648`(2의 31제곱, 약 68년 이상)로 처리한다.[1] 공유 캐시는 응답 생성 이후 경과한 초를 `Age` 헤더로 전달한다. 예를 들어 `Cache-Control: max-age=604800`(1주일) 응답을 공유 캐시가 하루 동안 보관한 뒤 전달하면 `Age: 86400`이 붙어 하위 클라이언트는 남은 518,400초 동안 해당 응답을 최신으로 간주한다.[7] `Cache-Control`이 없을 때는 `Last-Modified` 헤더를 이용한 휴리스틱 캐싱(heuristic caching)이 동작할 수 있으며, 사양은 마지막 수정 이후 경과 시간의 약 10%를 권장한다.[7] 기본 HTTP 캐싱 사양에는 저장된 응답을 명시적으로 삭제하는 절차가 없지만, CDN 같은 관리형 캐시는 대시보드, API 호출, 재시작으로 캐시를 즉시 삭제할 수 있으며 Varnish 설정 언어(VCL) 같은 전용 규칙으로 캐싱 정책을 제어하기도 한다.[7]

| 헤더 또는 지시어 | 적용 대상 | HTTP 및 CDN 캐싱에서의 역할 |
| --- | --- | --- |
| `Cache-Control: max-age` | 비공개 및 공유 캐시 | 응답 생성 시점 기준의 최신성 유지 시간(초)을 지정한다.[1][7] |
| `Cache-Control: s-maxage` | 공유 캐시 | 공유 캐시에 적용되는 최신성 유지 시간을 지정한다.[1][2] |
| `Cache-Control: private` | 비공개 캐시 | 개인화된 응답을 단일 사용자 캐시에만 저장하도록 제한한다.[1][7] |
| `Cache-Control: no-store` | 모든 표준 캐시 | 캐시가 응답을 저장하지 못하도록 금지한다.[1] |
| `Cache-Control: no-cache` | 모든 표준 캐시 | 저장된 응답을 재사용하기 전에 원본 서버 재검증을 요구한다.[1][2] |
| `Age` | 공유 캐시 | 응답 생성 이후 경과한 시간(초)을 알린다.[1][7] |
| `Expires` | 구 HTTP/1.0 및 HTTP/1.1 | 캐시 만료 시점을 구체적인 시각으로 지정한다.[1][7] |
| `Vary` | 캐시 키 구성 | 콘텐츠 협상 시 캐시 키에 포함할 요청 헤더 목록을 지정한다.[1] |

## 대상 지정 HTTP 캐시 제어와 CDN-Cache-Control(RFC 9213)

콘텐츠 전송 네트워크 환경은 원본 서버 캐시, 원본 네트워크 내부 캐시, 다중 CDN, 브라우저 캐시 등 여러 캐싱 계층이 함께 동작하는 경우가 많아 계층별로 서로 다른 캐싱 정책을 지정할 수단이 필요하다.[2] 표준 `Cache-Control` 헤더에는 공유 캐시용 `s-maxage` 지시어가 있지만, `stale-while-revalidate` 같은 확장 지시어를 포함한 전반적인 캐시 계층별 대상 지정은 일관되게 지원되지 않는다.[2] 기존에는 일부 CDN이 `Surrogate-Control` 같은 사업자별 비표준 헤더를 도입해 상호운용성이 낮았다.[2][7]

2022년 6월 IETF는 Akamai의 S. Ludin, Fastly의 M. Nottingham, [Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare)의 Y. Wu가 작성한 표준 트랙 문서 RFC 9213(Targeted HTTP Cache Control)을 발행했다.[2] RFC 9213은 특정 캐시나 캐시 유형에 지시어를 겨냥하는 대상 지정 캐시 제어(Targeted Cache-Control) 응답 헤더 규약을 정의하고, CDN 캐시 전용 헤더인 `CDN-Cache-Control`을 표준화했다.[2] 계약된 CDN에 대해 능동적인 캐시 무효화 수단을 갖춘 게시자는 `CDN-Cache-Control`로 CDN에 더 긴 캐시 유지 기간을 부여하면서, `Cache-Control`로는 브라우저와 다른 중간 캐시의 저장을 제한할 수 있다.[2]

대상 지정 캐시 제어 헤더는 HTTP 딕셔너리 구조화 필드(Dictionary Structured Fields) 구문을 따르며, 각 항목은 확장 지시어를 포함한 HTTP 캐시 응답 지시어에 해당하고 값은 구조화 필드의 불리언(Boolean), 문자열(String), 토큰(Token), 정수(Integer), 소수(Decimal) 타입으로 대응된다.[2] 오류 처리 방식이 `Cache-Control`과 다르기 때문에 구현체는 대상 지정 필드에 구조화 필드 파서를 적용하며, 필드가 비어 있거나 파싱 오류가 발생하면 해당 필드를 무시하고 다른 캐시 제어 메커니즘으로 전환한다.[2]

RFC 9213을 구현하는 캐시는 우선순위가 높은 순서대로 필드 이름을 나열한 대상 목록(target list, 예: `[ExampleCDN-Cache-Control, CDN-Cache-Control]`)을 유지한다.[2] 캐시는 응답을 받을 때마다 대상 목록에서 처음으로 유효하고 비어 있지 않은 필드를 선택해 캐싱 정책으로 삼고, 그 응답의 `Cache-Control`과 `Expires` 헤더는 무시한다.[2] 대상 목록에 없는 대상 지정 헤더는 해당 캐시의 동작을 바꾸지 않고 그대로 통과시켜야 한다.[2] 대상 지정 필드를 처리하는 캐시는 `max-age`, `must-revalidate`, `no-store`, `no-cache`, `private` 다섯 가지 지시어의 의미를 반드시 구현해야 하며, `no-store`와 `no-cache`가 `max-age`를 무효화하고 알 수 없는 확장 지시어를 무시하는 우선순위 규칙은 `Cache-Control`과 같다.[2]

## 콘텐츠 전송 네트워크의 BGP 애니캐스트 라우팅(RFC 4786)

콘텐츠 전송 네트워크 운영자와 분산 인터넷 서비스는 하나의 IP 주소를 여러 독립 위치의 서버에 공유해 클라이언트 트래픽을 가까운 노드로 전달하는 애니캐스트(anycast) 라우팅을 활용하며, 그 운영 모범 사례는 2006년 12월 IETF의 J. Abley(Afilias Canada)와 K. Lindqvist(Netnod Internet Exchange)가 발행한 RFC 4786(BCP 126)에 정리되어 있다.[5] 애니캐스트는 고정된 서비스 주소(Service Address, IPv4 또는 IPv6)를 둘 이상의 독립된 애니캐스트 노드(Anycast Node)에 할당하고 라우팅 시스템에 해당 주소의 도달 가능성을 광고하는 방식으로 동작한다.[5]

클라이언트가 애니캐스트 서비스 주소로 패킷을 보내면 라우팅 시스템은 네트워크 위상과 요청 출발 지점에 따라 가용 노드 가운데 하나로 데이터그램을 전달한다.[5] 특정 애니캐스트 노드로 패킷이 도달하는 네트워크의 위상적 영역을 집수 영역(catchment)이라고 부른다.[5] RFC 4786은 애니캐스트를 내부 게이트웨이 프로토콜(Interior Gateway Protocol, IGP) 안에서 일부 구간에만 노드를 노출하는 지역 범위 애니캐스트(local-scope anycast)와 경계 경로 프로토콜(Border Gateway Protocol, BGP, RFC 4271)을 통해 전 세계 인터넷에 도달 가능성을 광고하는 전역 범위 애니캐스트(global-scope anycast)로 구분한다.[5] 애니캐스트는 별도의 서버 리디렉션이나 라운드 로빈 DNS 없이도 트래픽을 분산할 수 있으며, 애플리케이션 요구에 따라 이름 기반 분산 방식과 결합해 쓸 수도 있다.[5]

RFC 4786은 애니캐스트 기반 서비스 분산이 수반하는 운영상 제약도 함께 제시한다.[5]

- 트랜잭션 지속 시간과 상태 관리: 애니캐스트는 장시간 유지되는 트랜잭션, 서버 측 트랜잭션 상태 보관, 노드 간 데이터 동기화에 제약을 가한다.[5]
- 부하 분산 불균형: 노드 선택이 라우팅 위상에 좌우되므로 애니캐스트 노드 간 정밀한 부하 분산은 달성하기 어렵고 요청 및 트래픽 부하가 불균형하게 분포하는 경향이 있으며, 주로 가용성 확보와 거친 단위의 확장에 적합하다.[5]
- 가용성 모니터링 복잡성: 클라이언트의 네트워크 위치에 따라 관측되는 서비스 가용성이 달라지고, 개별 노드가 담당하는 클라이언트 집단 역시 고정되거나 결정론적이지 않아 상태 감시가 까다로워진다.[5]

## 콘텐츠 전송 네트워크 상호 연결 표준(RFC 6707, RFC 7336)

콘텐츠 전송 네트워크 상호 연결(Content Distribution Network Interconnection, CDNI)은 서로 독립된 CDN들이 연동해 한 CDN이 다른 CDN을 대신해 최종 사용자에게 콘텐츠를 전달할 수 있도록 하는 구조이다.[3] 동영상과 멀티미디어 트래픽이 증가하면서 기존 CDN 사업자들이 인프라를 확장했고 다수의 네트워크 서비스 사업자(Network Service Provider, NSP)도 자체 CDN을 구축했다.[3] 단일 CDN만으로는 모든 최종 사용자의 접속 네트워크 가까이에 충분한 거점과 자원을 갖추기 어려워, 여러 CDN을 상호 연결해 콘텐츠 서비스 제공자(Content Service Provider, CSP)에서 최종 사용자까지의 종단 간 전송 범위를 넓히려는 요구가 생겼다.[3]

IETF는 2012년 9월 B. Niven-Jenkins, F. Le Faucheur, N. Bitar가 작성한 RFC 6707(Informational)로 CDNI 문제 영역을 정의했고, 2014년 8월 L. Peterson, B. Davie, R. van Brandenburg가 작성한 RFC 7336(Informational)으로 전체 프레임워크를 제시했으며, 두 문서는 기존 RFC 3466을 대체한다.[3][4] CDNI 모델에서는 CSP와 직접 계약을 맺은 권한 있는 상위 CDN(`uCDN`)이 요청을 직접 처리하거나 NSP가 운영하는 CDN 같은 하나 이상의 하위 CDN(`dCDN`)에 전송을 위임하며, 연쇄적인 하위 CDN 가운데 최종 사용자에게 콘텐츠를 실제로 전달하는 마지막 CDN을 전달 CDN(Delivering CDN)이라 부른다.[3][4]

상호 연결된 전송 흐름에서 사용자 에이전트의 초기 요청은 먼저 상위 CDN에 도착하며, 상위 CDN은 DNS 리디렉션이나 HTTP 리디렉션을 통해 사용자와 더 가까운 하위 CDN으로 요청을 넘길 수 있다.[3][4] RFC 7336은 상위 CDN이 자체 판단만으로 하위 CDN의 요청 라우팅 시스템에 요청을 넘기는 반복적 요청 리디렉션(Iterative CDNI Request Redirection)과, 상위 CDN이 먼저 하위 CDN의 리디렉션 인터페이스에 질의해 응답을 반영함으로써 사용자 에이전트를 하위 CDN 내부 서버로 직접 안내할 수 있는 재귀적 요청 리디렉션(Recursive CDNI Request Redirection)을 구분한다.[4] 하위 CDN에 해당 콘텐츠가 없으면 상위 CDN에서 객체를 가져오고, 필요한 경우 상위 CDN이 CSP에서 원본을 확보한다.[3] CDNI 메타데이터와 정책은 특정 콘텐츠 집합을 식별하는 `CDN-Domain`(FQDN) 단위로 적용되며, 클라이언트 요청에 노출되지 않는 `Distinguished CDN-Domain`은 CDN 간 콘텐츠 수집이나 리디렉션 대상 식별에 쓰인다.[4]

| CDNI 인터페이스 | 동작 시점 | RFC 6707 및 RFC 7336에 정의된 역할 |
| --- | --- | --- |
| CDNI 제어 인터페이스(Control Interface) | 비동기 | 관리 작업을 조율하며, CSP 요청에 따라 메타데이터와 콘텐츠를 사전 배치·재검증·삭제하는 트리거 인터페이스(Trigger Interface)를 포함한다.[3][4] |
| CDNI 요청 라우팅 인터페이스(Request Routing Interface) | 동기 및 비동기 | 상위·하위 CDN 간 DNS 및 HTTP 요청 리디렉션과 동적 거점(footprint) 정보 광고를 처리한다.[3][4] |
| CDNI 메타데이터 인터페이스(Metadata Interface) | 동기 또는 비동기 | CDN-Domain 단위의 배포 메타데이터와 전송 정책을 상호 연결된 CDN 간에 교환한다.[3][4] |
| CDNI 로깅 인터페이스(Logging Interface) | 비동기 | 상호 연결된 CDN 간에 콘텐츠 전송 로그 정보를 교환한다.[3][4] |

## 콘텐츠 전송 네트워크의 한계, 캐시 만료 문제, 보안 위험

콘텐츠 전송 네트워크 아키텍처는 캐시 최신성 불일치, 공유 캐시 개인정보 보호, 외부 사업자 장애 의존성, 자산 무결성 측면에서 운영상 한계와 보안 위험을 안고 있다.[1][2][6][7]

HTTP 캐싱은 단일한 종단 간 최신성 모델을 따르기 때문에 CDN 캐시에 하위 캐시보다 긴 유효 기간을 부여하면 하위 캐시의 효율이 떨어질 수 있다.[2] RFC 9213은 `Age: 1800`, `Cache-Control: max-age=600`, `CDN-Cache-Control: max-age=3600` 헤더가 함께 전송되는 사례를 든다. 이 응답은 30분이 지난 시점에 CDN 기준으로는 여전히 최신 상태이지만, 600초 제한을 따르는 하위 캐시에는 도착과 동시에 만료된 응답으로 판정된다.[2] 또한 원본 서버에 접속할 수 없는 단절 상태(disconnected)의 캐시는 허용된 조건에서 만료된 응답을 그대로 제공할 수 있다.[1]

외부 CDN을 도입하면 제3자 서비스에 대한 가용성 의존성이 생긴다.[6] MDN Web Docs는 외부 CDN에 장애가 발생하거나 특정 지역에서 차단되거나 서비스가 영구 종료될 경우 그 CDN에 의존하는 웹사이트가 정상 동작하지 않는다고 지적한다.[6] Bootstrap이나 jQuery 같은 정적 라이브러리를 외부 CDN 도메인에서 불러오는 구성은 상황에 따라 오히려 성능을 떨어뜨릴 수도 있다. 브라우저는 외부 오리진과 연결하기 위해 추가 DNS 조회와 연결 협상을 거쳐야 하고, 최신 브라우저는 개인정보 보호와 타이밍 공격 완화를 위해 참조 사이트 식별자를 포함하는 이중 키(double keying) 방식으로 오리진별 HTTP 캐시를 격리하므로 동일한 외부 라이브러리도 사이트마다 새로 내려받아야 한다.[1][6]

공유 CDN 캐시는 보안과 데이터 격리 위험도 동반한다.[1][6][7] 공격자가 외부 CDN을 침해하면 의존 웹사이트 사용자에게 악성 콘텐츠를 배포할 수 있으므로 정적 자산 검증을 위해 하위 리소스 무결성(Subresource Integrity, SRI) 같은 대응 수단이 필요하다.[6] 공유 캐시에 개인화된 응답을 저장하면서 `Cache-Control: private` 지시어를 지정하지 않으면 한 사용자의 정보가 다른 사용자에게 노출될 수 있으며, 요청이나 응답에 쿠키가 존재한다는 사실만으로 HTTP 응답이 비공개 처리되지 않는다.[7] RFC 9111 역시 HTTP 캐싱 시스템의 핵심 보안 고려 사항으로 캐시 오염(cache poisoning), 타이밍 공격(timing attacks), 민감 정보 캐싱을 명시한다.[1]

## 자주 묻는 질문

### 콘텐츠 전송 네트워크(CDN)란 무엇인가요?

콘텐츠 전송 네트워크(CDN)는 웹 콘텐츠의 사본을 여러 지역에 분산된 서버에 저장하고 최종 사용자와 가까운 에지 위치에서 요청을 처리하는 네트워크입니다. 클라이언트와 원본 서버 사이에서 관리형 공유 HTTP 캐시로 동작하며, 응답 지연을 줄이고 원본 서버 부하를 낮추며 가용성을 높입니다. [6][7][8]

### CDN-Cache-Control 헤더는 일반 Cache-Control 헤더와 어떻게 다른가요?

RFC 9111에 정의된 일반 Cache-Control 지시어는 브라우저와 공유 캐시 전반에 폭넓게 적용되어 계층별 세밀한 대상 지정이 제한됩니다. 2022년 6월 RFC 9213으로 표준화된 CDN-Cache-Control은 CDN 캐시만을 대상으로 하는 딕셔너리 구조화 필드이며, 이를 지원하는 CDN은 해당 응답에서 Cache-Control과 Expires를 무시하고 별도의 캐싱 정책을 적용합니다. [2][7]

### CDN에서 BGP 애니캐스트 라우팅을 사용하는 이유는 무엇인가요?

RFC 4786(BCP 126)에 정리된 전역 범위 BGP 애니캐스트는 동일한 IP 서비스 주소를 여러 독립 위치에서 광고하여 인터넷 라우팅이 클라이언트 패킷을 위상적으로 가까운 노드로 전달하게 합니다. 라운드 로빈 DNS 없이도 서비스 안정성과 거친 단위의 확장을 지원하지만, 노드 간 트래픽 부하가 고르게 분산되기는 어렵습니다. [5]

### CDN 상호 연결(CDNI)이란 무엇인가요?

RFC 6707에서 문제를 정의하고 RFC 7336에서 프레임워크를 제시한 CDN 상호 연결(CDNI)은 독립된 CDN들이 협력해 상위 CDN이 최종 사용자와 더 가까운 하위 CDN에 콘텐츠 전송을 위임하는 구조입니다. 제어(트리거 인터페이스 포함), 요청 라우팅, 메타데이터, 로깅의 네 가지 인터페이스 영역을 통해 전송을 조율합니다. [3][4]

### CDN에서 개인화된 사용자 데이터가 노출되거나 만료된 콘텐츠가 전달될 수 있나요?

네, 그럴 수 있습니다. CDN은 공유 캐시로 동작하므로 개인화된 응답에 Cache-Control: private 지시어를 지정하지 않으면 다른 사용자에게 데이터가 노출될 수 있으며, 쿠키가 있다는 사실만으로 응답이 비공개 처리되지 않습니다. 또한 CDN의 캐시 유효 기간을 하위 캐시보다 길게 설정하면 응답이 하위 캐시에 도착했을 때 이미 만료된 상태가 될 수 있습니다. [2][7]

### 외부 CDN에서 정적 라이브러리를 불러올 때 어떤 위험이 있나요?

MDN Web Docs는 자체 호스팅과 비교해 세 가지 단점을 지적합니다. 외부 CDN의 장애, 지역 차단, 서비스 종료가 의존 웹사이트의 오작동으로 이어질 수 있고, 침해된 CDN이 악성 파일을 배포할 위험이 있어 하위 리소스 무결성(SRI) 같은 대응이 필요합니다. 또한 별도 오리진 연결에 따른 DNS 조회와 연결 비용이 늘어나며, 최신 브라우저의 오리진별 캐시 격리 때문에 사이트 간 자산 캐시 재사용도 일어나지 않습니다. [6]

## 인용 문장

- IETF는 2022년 6월 RFC 7234를 대체하는 표준 트랙 HTTP 캐싱 사양으로 RFC 9111(STD 98)을 발행했다. [1]
- 2022년 6월 Akamai, Fastly, Cloudflare 소속 저자들이 발행한 RFC 9213은 CDN 캐시 전용 HTTP 응답 헤더인 CDN-Cache-Control을 정의한다. [2]
- RFC 9213에 따라 대상 지정 캐시 제어 필드를 구현하는 캐시는 max-age, must-revalidate, no-store, no-cache, private 지시어를 반드시 지원해야 한다. [2]
- 2006년 12월 발행된 RFC 4786(BCP 126)은 IGP 또는 BGP 기반의 IPv4 및 IPv6 애니캐스트로 여러 위치에 서비스를 분산 운영하는 모범 사례를 기술한다. [5]
- RFC 6707(2012년 9월)과 RFC 7336(2014년 8월)은 콘텐츠 전송 네트워크 상호 연결(CDNI)의 문제 정의와 프레임워크를 규정하며 RFC 3466을 대체한다. [3][4]
- 최신 브라우저는 개인정보 보호를 위해 오리진별로 HTTP 캐시를 격리하므로 외부 CDN의 동일 라이브러리도 웹사이트마다 별도로 내려받아야 한다. [6]
- CDN 같은 관리형 캐시는 기본 HTTP 캐싱 사양에 정의되지 않은 명시적 삭제 기능을 대시보드, API 호출, 재시작을 통해 제공한다. [7]
- 2026-11-23 기준 Amazon CloudFront는 기본적으로 객체를 에지 로케이션에 24시간 동안 캐시하며, 최소 만료 시간은 0초이고 고정된 최대 만료 시간은 없다. [8]

## 연표

- 2006-12: IETF가 지역 범위 IGP와 전역 범위 BGP 애니캐스트 운영 사례를 정리한 RFC 4786(BCP 126) 'Operation of Anycast Services'를 발행한다. [5]
- 2012-09: IETF가 네 가지 CDNI 인터페이스의 범위를 정의한 RFC 6707 'Content Distribution Network Interconnection (CDNI) Problem Statement'를 발행한다. [3]
- 2014-08: IETF가 RFC 6707과 함께 RFC 3466을 대체하는 RFC 7336 'Framework for Content Distribution Network Interconnection (CDNI)'를 발행한다. [4]
- 2022-06: IETF가 RFC 7234를 대체하는 RFC 9111(STD 98) 'HTTP Caching'과 CDN-Cache-Control 응답 헤더를 표준화한 RFC 9213 'Targeted HTTP Cache Control'을 함께 발행한다. [1][2]

## 출처

1. RFC 9111: HTTP Caching. Internet Engineering Task Force (IETF). 게시일 2022-06. https://www.rfc-editor.org/rfc/rfc9111.txt (확인일 2026-11-23; tier 1: government or public registry)
2. RFC 9213: Targeted HTTP Cache Control. Internet Engineering Task Force (IETF). 게시일 2022-06. https://www.rfc-editor.org/rfc/rfc9213.txt (확인일 2026-11-23; tier 1: government or public registry)
3. RFC 6707: Content Distribution Network Interconnection (CDNI) Problem Statement. Internet Engineering Task Force (IETF). 게시일 2012-09. https://www.rfc-editor.org/rfc/rfc6707.txt (확인일 2026-11-23; tier 1: government or public registry)
4. RFC 7336: Framework for Content Distribution Network Interconnection (CDNI). Internet Engineering Task Force (IETF). 게시일 2014-08. https://www.rfc-editor.org/rfc/rfc7336.txt (확인일 2026-11-23; tier 1: government or public registry)
5. RFC 4786: Operation of Anycast Services. Internet Engineering Task Force (IETF). 게시일 2006-12. https://www.rfc-editor.org/rfc/rfc4786.txt (확인일 2026-11-23; tier 1: government or public registry)
6. CDN - Glossary | MDN. MDN Web Docs. 게시일 2025-07-11. https://developer.mozilla.org/en-US/docs/Glossary/CDN (확인일 2026-11-23; tier 3: official site)
7. HTTP caching - HTTP | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching (확인일 2026-11-23; tier 3: official site)
8. What is Amazon CloudFront? - Amazon CloudFront. Amazon Web Services. https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "콘텐츠 전송 네트워크." 버전 598079c4, 2026-11-23. https://mimirwiki.com/ko/wiki/content-delivery-network
