---
title: "엔진엑스 (nginx)"
subtitle: "고성능 오픈소스 비동기 이벤트 기반 웹 서버, 리버스 프록시, 로드 밸런서 및 메일 프록시"
canonical_url: https://mimirwiki.com/ko/wiki/nginx
language: ko
page_class: entity
revision_sha256: bc73a157232dbaf61c21a6811f3e57c165e45240766dc19588141df77565df02
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/nginx.md
  txt: https://mimirwiki.com/ko/wiki/nginx.txt
  json: https://mimirwiki.com/ko/wiki/nginx.json
  jsonld: https://mimirwiki.com/ko/wiki/nginx.jsonld
translations:
  en: https://mimirwiki.com/wiki/nginx
  ja: https://mimirwiki.com/ja/wiki/nginx
  zh: https://mimirwiki.com/zh/wiki/nginx
---

# 엔진엑스 (nginx)

> 2026년 11월 23일 기준 최신 오픈소스 릴리스는 메인라인(mainline) 브랜치인 nginx 1.31.10(2026년 11월 23일 출시)과 스테이블(stable) 브랜치인 nginx 1.30.8로, TLS 1.3에서 ssl_early_data 지시어 사용 시 클라이언트가 과도한 CPU 사용을 유발할 수 있는 중위험 취약점(CVE-2026-132779)을 패치했다. 이에 앞서 2026년 11월 18일 출시된 nginx 1.31.9(메인라인)와 1.30.7(스테이블)은 총 10건의 보안 취약점(스테이블 1.30.7은 9건 해당)을 해결했으며, 특히 CVSS v4.0 9.2점(Critical) / CVSS v3.1 8.1점(High)으로 평가된 2건의 미인증 HTTP/2 원격 코드 실행(RCE) 취약점인 CVE-2026-123007(nginx 1.9.5부터 10년간 존재한 HTTP/2 send_window 정수 언더플로 및 힙 버퍼 오버플로)과 CVE-2026-123633(HTTP/2 프록시 worker_connections Use-After-Free)을 패치했다.

엔진엑스(nginx, 대문자 표기 NGINX)는 이고르 시소예프(Igor Sysoev)가 개발하여 2004년 10월 처음 공개한 오픈소스 비동기 이벤트 기반 HTTP 웹 서버, 리버스 프록시(Reverse Proxy), 애플리케이션 로드 밸런서, 콘텐츠 캐시 및 메일 프록시 서버이다. 2조항 BSD 라이선스(2-clause BSD License)로 배포되며 2019년 F5(F5, Inc.)의 인수 이후 F5가 개발을 주도하고 있다. 마스터-워커(Master-Worker) 프로세스 아키텍처를 통해 적은 메모리 점유율로 수만 개의 동시 연결을 처리한다.

**다른 이름:** nginx, NGINX, Engine-X, NGINX Open Source

## 핵심 정보

- **원작자 및 관리 주체:** 이고르 시소예프 (2004년); F5, Inc. (2019년 5월 인수) [1]
- **라이선스:** 2조항 BSD 라이선스 (2-clause BSD License) [1]
- **최신 버전:** 1.31.10 (메인라인, 2026-11-23 출시) 및 1.30.8 (스테이블) (기준 2026-11-23) [2]
- **2026년 11월 보안 업데이트:** 1.31.10 / 1.30.8에서 CVE-2026-132779(ssl_early_data CPU 과점유) 패치; 1.31.9 / 1.30.7(11-18)에서 CVSS 9.2 HTTP/2 RCE 2건 포함 10건 패치 (기준 2026-11-23) [3]

## 기본 정보

- **원작자:** 이고르 시소예프 (Igor Sysoev) [1]
- **유지보수 주체:** F5, Inc. (NGINX Product Group) [1]
- **최초 공개일:** 2004년 10월 4일 (버전 0.1.0) [1]
- **최신 메인라인 버전:** 1.31.10 (2026년 11월 23일) (기준 2026-11-23) [3]
- **최신 스테이블 버전:** 1.30.8 (1.31.10과 함께 CVE-2026-132779 패치 버전으로 등재) (기준 2026-11-23) [2]
- **프로그래밍 언어:** C [1]
- **라이선스:** 2조항 BSD 라이선스 (2-clause BSD License) [1]
- **지원 프로토콜:** HTTP/1.x, HTTP/2, HTTP/3 (QUIC), TLS/SSL, FastCGI, uwsgi, SCGI, gRPC, IMAP/POP3/SMTP, TCP/UDP [1]

## 개요 및 비동기 이벤트 기반 아키텍처

엔진엑스(nginx)는 단일 서버에서 1만 개 이상의 동시 클라이언트 연결을 처리하는 **C10k 문제(C10k problem)**를 해결하기 위해 2002년 러시아의 소프트웨어 엔지니어 이고르 시소예프(Igor Sysoev)가 설계했으며, 2004년 10월 4일 2조항 BSD 라이선스(2-clause BSD License)로 오픈소스 공개되었다 [1]. 연결마다 별도의 스레드나 프로세스를 생성하는 전통적인 웹 서버와 달리, nginx는 설정 로드와 포트 바인딩 및 워커 관리를 담당하는 단일 특권 **마스터 프로세스(master process)**와 실제 네트워크 I/O를 처리하는 하나 이상의 비특권 단일 스레드 **워커 프로세스(worker processes)**(및 캐시 로더·캐시 매니저 프로세스)로 동작한다 [1].

각 워커 프로세스는 운영체제 커널의 고성능 이벤트 통지 메커니즘(리눅스의 `epoll`, FreeBSD 및 macOS의 `kqueue`, 솔라리스의 event ports)을 기반으로 논블로킹(non-blocking) 비동기 이벤트 루프를 실행한다 [1]. 연결당 컨텍스트 스위칭이나 스레드 스택 할당이 발생하지 않으므로 정적 파일 서빙, TLS 1.3 종료, HTTP/2 및 HTTP/3(QUIC) 멀티플렉싱, gRPC·WebSocket 리버스 프록시, 그리고 업스트림 로드 밸런싱(`http`, `stream`, `mail` 컨텍스트)을 일정하고 낮은 메모리 사용량으로 수행한다 [1]. 2019년 5월에는 애플리케이션 딜리버리 전문 기업 **F5(F5, Inc.)**가 NGINX, Inc.를 인수하여 오픈소스 버전(`nginx.org`)과 상용 배포판인 NGINX Plus를 함께 유지보수하고 있다 [1][2].

## 릴리스 브랜치 체계: 메인라인 1.31.x 및 스테이블 1.30.x

nginx 프로젝트는 `nginx.org`를 통해 두 개의 오픈소스 릴리스 브랜치를 병행 운영한다 [1][2]: - **메인라인 브랜치(Mainline branch)**: 홀수 부 버전 번호를 사용하며(현재 **1.31.x**, 2026년 11월 23일 기준 **1.31.10**), 모든 신규 기능, 프로토콜 개선 사항, 버그 수정 및 보안 패치가 가장 먼저 반영된다 [2][3]. - **스테이블 브랜치(Stable branch)**: 짝수 부 버전 번호를 사용하며(현재 **1.30.x**, 2026년 11월 23일 보안 권고 기준 **1.30.8**), 매년 메인라인에서 분기되어 서드파티 모듈 호환성을 해치지 않는 치명적 버그 수정과 보안 패치만 백포트(backport)된다 [1][2].

**2026년 11월 18일** nginx 프로젝트는 HTTP/2, HTTP/3, 업스트림 프록시, 비동기 DNS 리졸버, 메일 프록시, `try_files`/`alias` 처리 및 `stream` TLS/SNI 모듈 전반에서 발견된 10건의 보안 취약점(스테이블 1.30.7은 9건 해당)을 일괄 해결하기 위해 **nginx 1.31.9**와 **nginx 1.30.7**을 배포했다 [2][3]. 이어 닷새 뒤인 **2026년 11월 23일**에는 TLS 1.3에서 `ssl_early_data` 지시어를 사용할 때 클라이언트가 과도한 CPU 사용량을 유발할 수 있는 중위험(medium) 취약점인 **CVE-2026-132779**(취약 버전 `1.21.4-1.31.9`)와 백엔드 SSL 연결 시의 CPU 과점유 버그를 수정한 **nginx 1.31.10**(보안 권고 페이지 기준 비해당 버전 `1.31.10+`, `1.30.8+`)을 출시했다 [2][3].

## 2026년 11월 보안 권고 및 HTTP/2 RCE 취약점

2026년 11월 18일 및 11월 23일 두 차례의 업데이트를 통해 nginx 프로젝트는 1.31.x 메인라인 및 1.30.x 스테이블 브랜치에서 총 11건의 CVE를 패치했다 [2][3]. 이 가운데 11월 18일 업데이트(1.31.9 및 1.30.7)에서 클라우드 보안 연구 기관 위즈 리서치(Wiz Research)가 상세 분석을 공개한 2건의 미인증 HTTP/2 원격 코드 실행(RCE) 취약점인 **CVE-2026-123007**과 **CVE-2026-123633**은 미국 국립취약점데이터베이스(NVD)에서 **CVSS v4.0 기준 9.2점(Critical)** 및 **CVSS v3.1 기준 8.1점(High)**을 부여받았으며 보안 커뮤니티에서 **nginx2root** / **nginx2shell**이라는 별칭으로도 불렸다 [4][5][6][8]:

| CVE 식별자 | 영향받는 모듈 및 버전 범위 | 취약점 작동 원리 | 심각도 및 패치 버전 |
| --- | --- | --- | --- |
| **CVE-2026-132779** | TLS 1.3 `ssl_early_data` (nginx 1.21.4 ~ 1.31.9) | `ssl_early_data` 지시어 사용 시 클라이언트가 과도한 CPU 사용(excessive CPU usage)을 유발할 수 있음 [2][3]. | Medium (`nginx.org`); 1.31.10+, 1.30.8+ 패치 |
| **CVE-2026-123007** | `ngx_http_v2_module` (nginx 1.9.5 ~ 1.31.8; 10년 이상 잠복) | 조작된 HTTP/2 `SETTINGS` 및 `WINDOW_UPDATE` 프레임을 통한 `send_window` 흐름 제어 계산 시 정수 언더플로(`CWE-191`) 및 힙 버퍼 오버플로(`CWE-122`) 발생 [2][4][6]. | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High; 1.31.9+, 1.30.7+ 패치 |
| **CVE-2026-123633** | `ngx_http_v2_module` + 업스트림 프록시 (1.19.7 ~ 1.31.8) | HTTP/2 연결이 업스트림 백엔드로 프록시하는 도중 `worker_connections` 한도를 소진할 때 발생하는 해제 후 사용(Use-After-Free, `CWE-416`) [2][5][6]. | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High; 1.31.9+, 1.30.7+ 패치 |
| **CVE-2026-121810** | `ngx_http_v3_module` (1.25.0 ~ 1.31.8) | HTTP/3 QUIC 처리 중 `worker_connections` 소진 시 발생하는 Use-After-Free 취약점 [2][3]. | Medium (`nginx.org`); 1.31.9+, 1.30.7+ 패치 |
| **CVE-2026-123634** | 코어 비동기 DNS `resolver` (0.6.18 ~ 1.31.8) | `resolver` 지시어가 설정된 환경에서 서브요청의 동시 도메인 이름 해석 중 발생하는 Use-After-Free [2][3]. | Medium (`nginx.org`); 1.31.9+, 1.30.7+ 패치 |
| **CVE-2026-113425** | `ngx_mail_module` (0.5.33 ~ 1.31.8) | 메일 프록시 서버 모듈에서 발생하는 Use-After-Free 취약점 [2][3]. | Major (`nginx.org`); 1.31.9+, 1.30.7+ 패치 |

2026년 11월 18일 함께 패치된 나머지 5건의 취약점은 **CVE-2026-125283**(`try_files`와 `alias` 지시어를 함께 사용할 때 발생하는 버퍼 오버플로), **CVE-2026-120967**(`stream` 모듈 동기식 SSL 핸드셰이크의 SNI 클라이언트 인증서 검증 우회), **CVE-2026-120993**(동적 SSL 인증서 로딩과 결합된 PROXY 프로토콜 v2 처리 중 NULL 포인터 역참조 및 워커 세그멘테이션 폴트, 메인라인 1.31.4 ~ 1.31.8), **CVE-2026-123640**(`ngx_stream_ssl_preread_module`의 기형적 ClientHello 검증 미흡), 그리고 **CVE-2026-118899**(SSL/TLS 1.3 환경에서 클라이언트 요청 본문을 읽는 중 발생하는 워커 프로세스 무한 루프)이다 [2][3].

nginx 변경 기록은 CVE-2026-123007의 제보자로 Xint.io를, CVE-2026-123633의 제보자로 Vexera AI의 Albert를 적고 있다 [3].

## CVE-2026-123007 및 CVE-2026-123633 심층 분석과 완화 조치

2026년 11월 패치된 취약점 가운데 **CVE-2026-123007**과 **CVE-2026-123633**은 일반적인 HTTP/2 설정만으로 인증 없이 원격 코드 실행이 가능하다는 점에서 인터넷 보안 센터(CIS 권고 `2026-136`)와 위즈 리서치의 집중적인 경고를 받았다 [6][7][8]: - **CVE-2026-123007 (10년 이상 잠복한 HTTP/2 흐름 제어 힙 버퍼 오버플로)**: 2015년 9월 nginx 1.9.5에서 `ngx_http_v2_module`이 처음 도입된 이래 모든 HTTP/2 활성화 서버에 존재해 온 취약점으로, 단일 TCP 연결만으로 트리거된다 [4][6][8]. 공격자가 데이터 프레임이 전송 대기 중인 상태에서 `SETTINGS_INITIAL_WINDOW_SIZE`와 `WINDOW_UPDATE` 프레임을 조작하면 `send_window` 연산에 정수 언더플로가 발생하여 워커 프로세스의 힙 버퍼 오버플로로 이어진다 [4][6]. - **CVE-2026-123633 (HTTP/2 업스트림 프록시 Use-After-Free)**: HTTP/2가 활성화된 서버가 백엔드 업스트림으로 요청을 프록시(`proxy_pass`, `fastcgi_pass`, `uwsgi_pass`, `scgi_pass`, `grpc_pass`)하는 리버스 프록시, 인그레스 컨트롤러, API 게이트웨이 환경에 영향을 미친다 [5][6]. 공격자가 다수의 동시 연결을 열어 업스트림 연결 수립 중 `worker_connections`를 소진시키면 워커 프로세스 힙에서 해제 후 사용(Use-After-Free)이 발생한다 [5][6].

공격자는 nginx 풀 할당자(`ngx_pool_t`) 레이아웃을 정렬(heap grooming)한 뒤 워커 메모리 내 함수 포인터를 변조함으로써 nginx 워커 프로세스 권한으로 임의 코드를 실행할 수 있다 [6][8].

**대응 및 완화 방법**: 시스템 관리자는 11월 18일 패치(`1.31.9+` / `1.30.7+`)와 11월 23일 `CVE-2026-132779` 패치가 모두 반영된 **nginx 1.31.10+** 또는 **nginx 1.30.8+**(또는 각 리눅스 배포판의 백포트 보안 패키지)로 업그레이드해야 한다 [2][3][7]. 즉각적인 업그레이드가 불가능한 환경에서는 임시 완화책으로 외부 리스너에서 `http2`, `http3`, `ssl_early_data`를 비활성화하고, 불필요한 동적 `resolver` 설정을 제거하며, 워커 프로세스가 `root`가 아닌 비특권 계정으로 실행되도록 확인해야 한다 [2][3][6][7].

## 자주 묻는 질문

### 2026년 11월 23일 기준 엔진엑스(nginx)의 최신 버전은 무엇인가요?

2026년 11월 23일 기준 최신 버전은 메인라인 브랜치 nginx 1.31.10(2026년 11월 23일 출시)과 스테이블 브랜치 nginx 1.30.8(보안 권고 페이지에서 1.31.10+와 함께 CVE-2026-132779 비해당 버전으로 등재)입니다. 해당 버전은 TLS 1.3의 ssl_early_data 사용 시 과도한 CPU 사용을 유발하는 CVE-2026-132779를 패치했으며, 앞서 11월 18일 출시된 1.31.9 및 1.30.7에서 10건의 CVE를 패치한 바 있습니다. [2][3]

### nginx 1.31.10 및 1.30.8에서 패치된 CVE-2026-132779는 어떤 취약점인가요?

CVE-2026-132779는 2026년 11월 23일 공개된 중위험(medium) 취약점으로, nginx 1.21.4부터 1.31.9까지의 버전에서 TLS 1.3의 ssl_early_data 지시어를 사용할 때 클라이언트가 과도한 CPU 사용량을 유발할 수 있는 문제입니다. nginx 1.31.10 이상 및 1.30.8 이상에서 해결되었습니다. [2][3]

### CVE-2026-123007과 CVE-2026-123633은 어떤 취약점인가요?

CVE-2026-123007과 CVE-2026-123633은 위즈 리서치(Wiz Research)가 분석하고 2026년 11월 18일 nginx 1.31.9 및 1.30.7에서 패치된 CVSS v4.0 9.2점(Critical) / CVSS v3.1 8.1점(High) 등급의 HTTP/2 원격 코드 실행 취약점입니다. CVE-2026-123007은 nginx 1.9.5(2015년)부터 10년 넘게 존재해 온 HTTP/2 send_window 정수 언더플로 및 힙 버퍼 오버플로 취약점이며, CVE-2026-123633은 HTTP/2 업스트림 프록시 연결 중 worker_connections 한도가 소진될 때 발생하는 Use-After-Free 취약점입니다. [2][4][5][6]

### nginx의 메인라인(Mainline) 브랜치와 스테이블(Stable) 브랜치는 어떻게 다른가요?

홀수 부 버전(예: 1.31.x)을 사용하는 메인라인 브랜치는 모든 신규 기능과 버그 수정, 보안 패치가 즉시 적용되는 권장 브랜치입니다. 짝수 부 버전(예: 1.30.x)을 사용하는 스테이블 브랜치는 서드파티 모듈의 API 호환성을 유지하기 위해 신규 기능 추가 없이 치명적 버그와 보안 패치만 백포트합니다. [1][2]

### 즉시 nginx를 업그레이드할 수 없는 경우 2026년 11월 취약점들을 어떻게 임시 완화할 수 있나요?

근본적인 해결책은 nginx 1.31.10 이상 또는 1.30.8 이상으로 업그레이드하는 것입니다. 패치 전 임시 조치가 필요한 경우 공개 리스너에서 http2, http3 및 ssl_early_data 지시어를 비활성화하고, 불필요한 동적 resolver 설정을 제거하며, 워커 프로세스가 root 권한으로 실행되지 않도록 설정해야 합니다. [2][3][6][7]

## 인용 문장

- nginx는 2026년 11월 23일 메인라인 1.31.10을 출시(보안 권고 페이지에 1.31.10+ 및 스테이블 1.30.8+를 비해당 버전으로 등재)하여 TLS 1.3에서 ssl_early_data 사용 시 과도한 CPU 사용을 유발하는 CVE-2026-132779(1.21.4~1.31.9 영향)를 패치했다. [2][3]
- nginx는 2026년 11월 18일 메인라인 1.31.9와 스테이블 1.30.7을 출시하여 총 10건의 보안 취약점(1.30.7은 9건)을 패치했다. [2][3]
- HTTP/2 취약점인 CVE-2026-123007과 CVE-2026-123633은 NVD에서 CVSS v4.0 9.2점(Critical) 및 CVSS v3.1 8.1점(High)을 부여받았으며 미인증 원격 코드 실행을 유발할 수 있다. [4][5][6]
- CVE-2026-123007은 ngx_http_v2_module의 send_window 계산 시 발생하는 정수 언더플로 및 힙 버퍼 오버플로 취약점으로 nginx 1.9.5부터 1.31.8 및 1.30.6까지 영향을 미쳤다. [2][4][6]
- nginx는 이고르 시소예프가 2004년 10월 4일 2조항 BSD 라이선스로 최초 공개했으며 2019년 5월부터 F5, Inc.가 유지보수하고 있다. [1]

## 연표

- 2004-10-04: 이고르 시소예프가 2조항 BSD 라이선스로 nginx 0.1.0을 최초 공개. [1]
- 2015-09: nginx 1.9.5에서 HTTP/2 지원을 위한 ngx_http_v2_module 도입 (훗날 CVE-2026-123007로 확인된 send_window 로직 포함). [2][6]
- 2019-05: F5, Inc.가 NGINX, Inc. 인수를 완료함. [1]
- 2026-11-18: CVSS 9.2점 등급의 HTTP/2 RCE 취약점 2건(CVE-2026-123007, CVE-2026-123633)을 포함한 총 10건의 CVE를 패치한 nginx 1.31.9(메인라인) 및 1.30.7(스테이블) 릴리스. [2][3][6]
- 2026-11-23: TLS 1.3에서 ssl_early_data 사용 시 과도한 CPU 사용을 유발하는 CVE-2026-132779 및 백엔드 SSL 연결 CPU 과점유 버그를 패치한 nginx 1.31.10(메인라인) 출시(보안 권고 페이지에 1.31.10+ 및 스테이블 1.30.8+ 등재). [2][3]

## 출처

1. nginx news and official project documentation. nginx.org / F5, Inc.. https://nginx.org/en/ (확인일 2026-11-23; tier 3: official site)
2. nginx security advisories. nginx.org. 게시일 2026-11-23. https://nginx.org/en/security_advisories.html (확인일 2026-11-23; tier 3: official site)
3. Changes with nginx 1.31.10 (23 Nov 2026) and 1.31.9 (18 Nov 2026). nginx.org. 게시일 2026-11-23. https://nginx.org/en/CHANGES (확인일 2026-11-23; tier 3: official site)
4. NVD - CVE-2026-123007 Detail (nginx HTTP/2 send_window integer underflow and heap-based buffer overflow). National Vulnerability Database (NIST). 게시일 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123007 (확인일 2026-11-23; tier 1: government or public registry)
5. NVD - CVE-2026-123633 Detail (nginx HTTP/2 upstream proxy worker_connections use-after-free). National Vulnerability Database (NIST). 게시일 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123633 (확인일 2026-11-23; tier 1: government or public registry)
6. Unauthenticated Remote Code Execution in NGINX: CVE-2026-123633 and CVE-2026-123007 | Wiz Blog. Wiz Research. 게시일 2026-11-18. https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities (확인일 2026-11-23; tier 3: official site)
7. Multiple Vulnerabilities in NGINX Could Allow for Remote Code Execution (CIS Advisory 2026-136). Center for Internet Security (CIS). 게시일 2026-11-19. https://www.cisecurity.org/advisory/multiple-vulnerabilities-in-nginx-could-allow-for-remote-code-execution_2026-136 (확인일 2026-11-23; tier 2: academic or news)
8. 10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers Execute Code on Servers. The Hacker News. 게시일 2026-11-19. https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "엔진엑스 (nginx)." 버전 bc73a157, 2026-11-23. https://mimirwiki.com/ko/wiki/nginx
