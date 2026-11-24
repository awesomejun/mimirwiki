---
title: "자바포셸 (Java4Shell, CVE-2026-114938)"
subtitle: "OpenJDK HotSpot C2 JIT 컴파일러의 x86-64 AVX-512 VBMI Base64 디코더 인트린식에서 발생한 치명적 힙 버퍼 오버플로 취약점"
canonical_url: https://mimirwiki.com/ko/wiki/java4shell
language: ko
page_class: concept
revision_sha256: f651d59eff0c5ce3271f35b34b76df25ccd79edff10ce1daf344838992aec0b3
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/java4shell.md
  txt: https://mimirwiki.com/ko/wiki/java4shell.txt
  json: https://mimirwiki.com/ko/wiki/java4shell.json
  jsonld: https://mimirwiki.com/ko/wiki/java4shell.jsonld
translations:
  en: https://mimirwiki.com/wiki/java4shell
  ja: https://mimirwiki.com/ja/wiki/java4shell
  zh: https://mimirwiki.com/zh/wiki/java4shell
---

# 자바포셸 (Java4Shell, CVE-2026-114938)

> 오라클(Oracle)의 2026년 11월 긴급 보안 패치(CSPU) 권고문에 보안 기업 Calif.io의 연구원 꽝 루옹(Quang Luong, 인간과 AI 에이전트를 결합한 '켄타우로스 해킹' 기법으로 취약점 분석)과 앨버트 양(Albert Yang)이 공동 제보자로 등재되었으며, CVSS v4.0 9.2점(Critical) 및 CVSS v3.1 8.1점(High)이 부여되었다. C2 JIT의 AVX-512 Base64 디코딩 루틴이 64바이트 SIMD 블록을 처리한 뒤 예상치 못한 '=' 패딩 바이트를 만났을 때 잔여 출력 길이 계산이 -1로 언더플로(underflow)되면서 evmovdqub(VMOVDQU8) 명령어의 64비트 쓰기 마스크가 모두 1(0xFFFFFFFFFFFFFFFF)로 설정되어 50바이트 버퍼의 오프셋 48부터 64바이트를 기록(배열 끝을 넘어 62바이트 힙 오버플로)하는 원리이다. 인텔 아이스레이크(Ice Lake) 이상 및 AMD 젠 4(Zen 4) 이상 CPU에서 구동되는 OpenJDK·Oracle JDK 17.0.6+, 21, 25, 27에 영향을 미치며, 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, 27.0.1.0.3 버전에서 패치되었다.

자바포셸(Java4Shell, 공식 식별자 CVE-2026-114938)은 AVX-512 VBMI 명령어 세트를 지원하는 x86-64 프로세서 환경에서 OpenJDK 핫스팟 가상 머신(HotSpot VM)의 C2 적시 컴파일러(Just-In-Time, JIT)가 생성하는 java.util.Base64.Decoder 어셈블리 인트린식(intrinsic)에서 발생하는 치명적인 힙 기반 버퍼 오버플로(Heap-based Buffer Overflow) 취약점이다. 2026년 11월 17일 OpenJDK 긴급 보안 권고와 오라클(Oracle) 긴급 보안 패치를 통해 공개되었으며, 인증되지 않은 원격 공격자가 비정상적인 위치에 패딩 문자('=')를 포함한 Base64 문자열을 전송하는 것만으로 인접한 자바 힙 객체를 덮어써 서비스 거부(DoS), 인증 우회 및 사전 인증 원격 코드 실행(Pre-auth RCE)을 일으킬 수 있다.

**다른 이름:** Java4Shell, CVE-2026-114938, OpenJDK AVX-512 Base64 힙 오버플로, RHSB-2026-018

## 핵심 정보

- **CVE 식별자 및 위험도:** CVE-2026-114938 (CVSS v4.0: 9.2 Critical / CVSS v3.1: 8.1 High) (기준 2026-11-17) [3]
- **취약 컴포넌트:** OpenJDK HotSpot VM C2 JIT x86-64 AVX-512 VBMI Base64.Decoder 인트린식 [1]
- **하드웨어 전제 조건:** AVX-512 VBMI 지원 x86-64 CPU (Intel Ice Lake+ / AMD Zen 4+); ARM64는 영향 없음 [4]
- **패치 완료 버전:** OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, 27.0.1.0.3 (2026-11-17 배포) (기준 2026-11-17) [1]

## 기본 정보

- **CVE ID:** CVE-2026-114938 [3]
- **통칭:** Java4Shell (자바포셸) [4]
- **공식 공개일:** 2026년 11월 17일 [1]
- **발견자:** 꽝 루옹 (Quang Luong, Calif.io) 및 앨버트 양 (Albert Yang) - 오라클 권고문 등재 제보자 [2]
- **CVSS 점수:** CVSS v4.0: 9.2 (Critical) / CVSS v3.1: 8.1 (High) [3]
- **취약점 유형:** CWE-122 (힙 기반 버퍼 오버플로) / SIMD 쓰기 마스크 정수 언더플로 [3]
- **영향받는 자바 버전:** OpenJDK / Oracle JDK 17 (17.0.6 이상), 21, 25, 27; Oracle JDK 8u511b33-perf [2]
- **JVM 플래그 우회 조치:** -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics (또는 -XX:UseAVX=2) [5]

## 개요 및 '켄타우로스 해킹'을 통한 발견 경위

**자바포셸(Java4Shell, `CVE-2026-114938`)**은 자바 가상 머신(JVM)의 하드웨어 가속 Base64 디코딩 루틴에서 발견된 치명적인 메모리 안전성 붕괴 취약점이다 [1][3][4]. 자바(Java)는 가비지 컬렉션과 배열 경계 검사를 제공하는 메모리 안전(memory-safe) 언어이기 때문에, 대부분의 웹 애플리케이션은 HTTP 헤더(`Authorization: Basic` 또는 `Bearer` JWT 토큰), 쿠키, SAML 어설션, JSON 페이로드 등 외부에서 입력된 비신뢰 문자열을 인증 전 단계에서 표준 라이브러리인 `java.util.Base64.getDecoder().decode()`에 직접 전달한다 [4][5]. 그러나 특정 메서드가 반복 호출되어 핫스팟(HotSpot) C2 적시 컴파일러(JIT)에 의해 네이티브 코드로 컴파일되면, JVM은 자바 바이트코드 대신 호스트 CPU 명령어에 맞춰 수작업으로 작성된 어셈블리 인트린식(intrinsic)인 `Base64.Decoder.decodeBlock`을 실행한다 [1][4].

오라클(Oracle)의 2026년 11월 긴급 보안 패치(Critical Security Patch Update, CSPU) 권고문은 이 취약점(`CVE-2026-114938`)의 제보자로 보안 리서치 기업 **Calif.io**의 **꽝 루옹(Quang Luong)**과 **앨버트 양(Albert Yang)** 두 사람을 명시하고 있으며, 오라클 및 OpenJDK 보안 그룹과의 조율을 거쳐 **2026년 11월 17일** 공식 공개되었다 [1][2][4][7]. 루옹은 Calif.io의 기술 보고서에서 인간 연구원의 역공학 가설 수립과 거대언어모델(LLM) 에이전트의 어셈블리 상태 공간 탐색을 결합한 이른바 **'켄타우로스 해킹(centaur hacking)'** 워크플로를 통해 OpenJDK의 `stubGenerator_x86_64.cpp` 내 복잡한 x86-64 SIMD 어셈블리 생성 코드를 감사하던 중 해당 버그를 찾아냈다고 밝혔다 [4].

## 기술적 작동 원리: AVX-512 VBMI 쓰기 마스크 언더플로

`CVE-2026-114938`의 근본 원인은 OpenJDK C2 JIT의 Base64 디코더 인트린식(`decodeBlock`) 내 x86-64 **AVX-512 VBMI**(Vector Byte Manipulation Instructions) 고속 처리 경로에 존재한다 [1][4]. 표준 Base64 디코딩에서는 인코딩된 ASCII 4바이트마다 3바이트의 디코딩된 출력이 생성되므로, 64바이트 크기의 AVX-512 레지스터(`ZMM`) 하나를 처리하면 최대 48바이트의 디코딩 결과가 만들어진다 [4]. 인트린식 루프가 64바이트 SIMD 블록 내부에서 유효하지 않은 문자나 패딩 문자 `'='`(`0x3d`)를 감지하면, 벡터 루프를 종료하고 남은 꼬리(tail) 바이트를 일반 스칼라 자바 루프로 넘기도록 설계되어 있었다 [4].

그러나 마지막 마스크 기반 SIMD 메모리 저장 명령어인 `evmovdqub`(`VMOVDQU8`, 마스크 레지스터 `k` 사용)를 실행하기 직전 남은 출력 길이(`output_len`)를 계산하는 과정에서 부호 있는 정수의 언더플로(Underflow) 버그가 발생한다 [4]. 특정 오프셋에 패딩 문자 `'='`가 위치할 경우 남은 바이트 수 계산값이 `-1`(64비트 2의 보수 표현으로 `0xFFFFFFFFFFFFFFFF`)이 되며, 이 값이 64비트 AVX-512 마스크 레지스터에 로드되면서 쓰기 마스크 전체 비트가 `1`(`-1u64`)로 채워진다 [4]. 그 결과 CPU의 `evmovdqub` 명령어는 대상 자바 `byte[]` 배열에 레지스터 전체 크기인 **64바이트**를 그대로 덮어쓰게 된다 [4].

Calif.io가 공개한 JDK 버전별 최소 재현 페이로드(PoC)는 다음과 같다 [4]: - **OpenJDK 21, 25, 27**: 65바이트 문자열 `'A' * 64 + '='`를 디코딩하면 JVM은 50바이트 크기의 대상 `byte[]` 배열을 할당한다(16바이트 배열 헤더와 8바이트 정렬 패딩을 포함해 힙에서 72바이트 차지) [4]. 처음 64자의 디코딩으로 48바이트가 채워진 뒤, 마스크가 `-1`로 풀린 `evmovdqub`가 50바이트 버퍼의 오프셋 48부터 64바이트를 기록하면서(쓰기 데이터의 48..63바이트는 항상 `0x9a`) **배열 끝을 넘어 인접한 다음 자바 힙 객체의 헤더와 필드를 62바이트만큼 침범하여 덮어쓴다** [4]. - **OpenJDK 17 (17.0.6 ~ 17.0.21)**: JDK 17에서는 AVX-512 루프 진입 전 최소 버퍼 크기 조건이 더 크게 설정되어 있어 129바이트 문자열인 `'A' * 128 + '='`를 입력할 때 동일한 힙 오버플로가 트리거된다 [4].

## 영향받는 자바 버전, CPU 아키텍처 및 엔터프라이즈 파급력

`CVE-2026-114938`이 실제로 발현되려면 취약한 JVM 버전과 **AVX-512 VBMI** 명령어를 지원하는 x86-64 CPU라는 두 가지 조건이 동시에 충족되어야 한다 [1][2][4]:

| 구분 | 취약한 환경 (영향 받음) | 안전한 환경 (영향 없음) |
| --- | --- | --- |
| **Java / OpenJDK 버전** | OpenJDK 및 Oracle Java SE **17.0.6 ~ 17.0.21**, **21.0.0 ~ 21.0.13**, **25.0.0 ~ 25.0.5**, **27.0.0 ~ 27.0.1**; Oracle GraalVM / JDK **8u511b33-perf** [1][2] | 표준 OpenJDK 8 및 OpenJDK 11 (AVX-512 VBMI Base64 인트린식 미포함); OpenJDK 17.0.1 ~ 17.0.5 [1][4][5] |
| **CPU 아키텍처** | **AVX-512 VBMI 지원 x86-64**: 인텔 아이스레이크(Ice Lake), 타이거레이크, 사파이어 래피즈(Sapphire Rapids), 에메랄드 래피즈, 그래나이트 래피즈; AMD 젠 4(Zen 4, EPYC Genoa/Bergamo) 및 젠 5(Zen 5, EPYC Turin) [4][5] | **ARM64 / AArch64** (AWS Graviton, Apple Silicon, Ampere); AVX-512 VBMI가 없는 구형 x86-64 CPU (인텔 스카이레이크-SP, AMD Zen 2/Zen 3 등) [4][5] |

스레드 로컬 할당 버퍼(TLAB) 내에서 발생한 62바이트 힙 오버플로는 바로 뒤에 할당된 객체의 마크 워드(mark word), 압축 클래스 포인터(`_klass`), 배열 길이 필드 또는 불리언(boolean)·참조 필드를 변조할 수 있다 [4]. 공격자는 이를 이용해 인접한 인증 객체의 권한 플래그를 덮어쓰거나 인접한 `byte[]` 배열의 길이를 비정상적으로 늘려 JVM 프로세스 전체 메모리에 대한 임의 읽기·쓰기(arbitrary R/W) 및 원격 코드 실행(RCE)을 달성할 수 있다 [4]. Calif.io와 보안 업계는 **키클록(Keycloak)**, **아틀라시안 지라(Jira) 및 컨플루언스(Confluence)**, **JFrog 아티팩토리(Artifactory)**, **젠킨스(Jenkins)**, **핑페더레이트(PingFederate)** 등 다수의 엔터프라이즈 자바 솔루션에서 사전 인증(Pre-auth) 공격이 가능함을 입증했다 [4][7].

## 패치 릴리스, JVM 플래그 우회 조치 및 CISA 권고

2026년 11월 17일 OpenJDK 프로젝트, 오라클, 레드햇(`RHSB-2026-018`), 아마존 코레토(Corretto), 이클립스 테무린(Temurin), 아줄(Azul) 등은 AVX-512 VBMI 마스크 연산 오류를 수정한 긴급 대역 외(Out-of-band) 패치 빌드를 일제히 배포했다 [1][2][5]: - **OpenJDK 17.0.21.0.3** - **OpenJDK 21.0.13.0.3** - **OpenJDK 25.0.5.0.3** - **OpenJDK 27.0.1.0.3**

**JVM 실행 플래그를 통한 즉각적 우회(Workaround)**: 운영 중인 프로덕션 환경에서 JDK 바이너리를 즉시 업그레이드하기 어려운 경우, `JAVA_OPTS` 등 JVM 실행 인자에 아래 플래그 중 하나를 추가하고 프로세스를 재시작하면 취약한 Base64 어셈블리 인트린식을 완전히 비활성화할 수 있다 [4][5]: ```text -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics ``` 또는 JVM의 AVX 사용 수준을 AVX2 이하로 제한할 수도 있다: ```text -XX:UseAVX=2 ```

**CISA 경보 및 경계 완화 조치**: 2026년 11월 17일 미국 사이버보안 및 인프라 보안국(CISA)은 캐나다 사이버보안센터(Canadian Centre for Cyber Security)의 협력을 받아 경보를 발표하고, 서드파티 애플리케이션·컨테이너 이미지·어플라이언스에 내장된 버전을 포함한 모든 JDK 및 자바 런타임 자산을 점검한 뒤 인터넷 노출 시스템부터 우선 패치할 것을 권고했다 [6]. 즉각적인 패치가 어려운 경우 애플리케이션 경계에서의 Base64 입력 제한·검증, 입력 크기 제한, 비인증 접근 제한 등 임시 보완 통제를 적용하고, 비인가 런타임·예기치 않은 JVM 충돌·의심스러운 자바 프로세스 여부를 모니터링할 것을 당부했다 [6].

## 자주 묻는 질문

### 자바포셸(Java4Shell, CVE-2026-114938)이란 무엇인가요?

자바포셸(CVE-2026-114938)은 OpenJDK 핫스팟 가상 머신(HotSpot VM)의 C2 JIT 컴파일러가 x86-64 AVX-512 VBMI 프로세서에서 사용하는 java.util.Base64.Decoder 어셈블리 인트린식에서 발생한 치명적인 힙 버퍼 오버플로 취약점(CVSS v4.0 9.2점 / CVSS v3.1 8.1점)입니다. 2026년 11월 17일 공개되었으며, 비정상적인 위치에 '=' 패딩 문자가 포함된 Base64 문자열만으로 자바 힙 메모리를 오염시켜 원격 코드 실행(RCE)을 유발할 수 있습니다. [1][3][4]

### 어떤 자바 버전과 CPU 환경이 CVE-2026-114938에 취약한가요?

OpenJDK 및 Oracle Java SE 17(17.0.6~17.0.21), 21(21.0.13 이하), 25(25.0.5 이하), 27(27.0.1 이하) 및 Oracle JDK 8u511b33-perf 버전이 AVX-512 VBMI를 지원하는 x86-64 CPU(인텔 아이스레이크 이상, AMD 젠 4 이상)에서 실행될 때만 취약합니다. ARM64(AWS Graviton, Apple Silicon 등) 서버나 표준 OpenJDK 8 및 11 환경은 영향을 받지 않습니다. [1][2][4][5]

### 단 65바이트의 Base64 문자열이 어떻게 자바에서 힙 버퍼 오버플로를 일으키나요?

AVX-512 VBMI Base64 디코딩 인트린식이 첫 64바이트 SIMD 블록을 처리해 48바이트를 디코딩한 뒤 예상치 못한 위치에서 '=' 패딩 바이트(예: 'A' 64개 뒤에 '=' 1개)를 만나면 남은 길이 계산이 -1로 언더플로됩니다. 이로 인해 64비트 쓰기 마스크가 모두 1(0xFFFFFFFFFFFFFFFF)로 설정되면서 evmovdqub 명령어가 50바이트 크기의 대상 배열 버퍼의 오프셋 48부터 64바이트를 강제로 기록하여 배열 끝을 넘어 인접한 힙 객체를 62바이트 덮어쓰게 됩니다. [4]

### Java4Shell을 해결하기 위해 어떤 OpenJDK 버전으로 업그레이드해야 하나요?

2026년 11월 17일 긴급 배포된 OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, 27.0.1.0.3 버전 또는 동일한 패치가 반영된 2026년 11월 오라클 긴급 보안 패치(CPU) 및 레드햇 OpenJDK 패키지로 업그레이드하면 해결됩니다. [1][2][5]

### JDK를 즉시 업그레이드할 수 없을 때 JVM 옵션으로 취약점을 차단하는 방법은 무엇인가요?

JVM 시작 옵션에 '-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics' (또는 '-XX:UseAVX=2') 플래그를 추가하고 자바 애플리케이션을 재시작하면 취약한 AVX-512 Base64 인트린식이 비활성화되어 공격을 완전히 차단할 수 있습니다. [4][5]

## 인용 문장

- CVE-2026-114938(Java4Shell)은 2026년 11월 17일 공개되었으며 CVSS v4.0 9.2점(Critical) 및 CVSS v3.1 8.1점(High)을 부여받았다. [1][2][3]
- CVE-2026-114938은 OpenJDK C2 JIT의 Base64.Decoder 인트린식 내 AVX-512 VBMI evmovdqub 명령어의 쓰기 마스크가 -1로 언더플로되면서 50바이트 버퍼의 오프셋 48부터 64바이트를 기록(62바이트 힙 오버플로)하여 발생한다. [4]
- 오라클의 2026년 11월 긴급 보안 패치(CSPU) 권고문은 CVE-2026-114938의 제보자로 Calif.io의 꽝 루옹(Quang Luong)과 앨버트 양(Albert Yang)을 등재하고 있으며, 이 취약점은 AVX-512 VBMI를 지원하는 x86-64 CPU 상의 OpenJDK 17.0.6+, 21, 25, 27에 영향을 미치고 ARM64 및 표준 OpenJDK 8/11에는 영향을 미치지 않는다. [1][2][4][5][7]
- OpenJDK는 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, 27.0.1.0.3 버전에서 CVE-2026-114938을 패치했으며, -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics 플래그로 임시 완화할 수 있다. [1][5]

## 연표

- 2023-01: OpenJDK 17.0.6에 AVX-512 VBMI Base64 디코더 C2 JIT 인트린식이 백포트되며 잠재적 마스크 언더플로 버그가 포함됨. [1][4]
- 2026-11-17: OpenJDK가 2026/11/17 보안 권고문을 발행하고 오라클이 긴급 보안 패치 업데이트(CSPU)를 배포했으며 CISA가 즉각적인 패치를 촉구하는 경보를 발표함. OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3, 27.0.1.0.3이 출시됨. [1][2][6]
- 2026-11-18: Calif.io의 꽝 루옹이 상세 기술 분석('Java4Shell')을 공개하고 레드햇이 보안 게시판 RHSB-2026-018을 발행함. [4][5]

## 출처

1. OpenJDK Vulnerability Advisory: 2026/11/17 (CVE-2026-114938 in Hotspot Base64 Intrinsic). OpenJDK Vulnerability Group. 게시일 2026-11-17. https://openjdk.org/groups/vulnerability/advisories/2026-11-17 (확인일 2026-11-23; tier 3: official site)
2. Oracle Critical Security Patch Update Advisory - November 2026. Oracle Corporation. 게시일 2026-11-17. https://www.oracle.com/security-alerts/cspunov2026.html (확인일 2026-11-23; tier 3: official site)
3. NVD Detail for CVE-2026-114938: OpenJDK HotSpot VM AVX-512 Base64 Decoder Heap-Based Buffer Overflow. National Vulnerability Database (NIST). 게시일 2026-11-17. https://nvd.nist.gov/vuln/detail/CVE-2026-114938 (확인일 2026-11-23; tier 1: government or public registry)
4. Java4Shell: Write once, RCE everywhere. Calif.io (Quang Luong). 게시일 2026-11-18. https://calif.io/java4shell (확인일 2026-11-23; tier 3: official site)
5. Red Hat Security Bulletin RHSB-2026-018: OpenJDK AVX-512 Base64 Heap Overflow (CVE-2026-114938). Red Hat, Inc.. 게시일 2026-11-18. https://access.redhat.com/security/vulnerabilities/RHSB-2026-018 (확인일 2026-11-23; tier 3: official site)
6. Critical Java Vulnerability Requires Immediate Patching | CISA. Cybersecurity and Infrastructure Security Agency (CISA). 게시일 2026-11-17. https://www.cisa.gov/news-events/alerts/2026/11/17/critical-java-vulnerability-requires-immediate-patching (확인일 2026-11-24; tier 1: government or public registry)
7. Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ. Tenable Research. 게시일 2026-11-17. https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "자바포셸 (Java4Shell, CVE-2026-114938)." 버전 f651d59e, 2026-11-24. https://mimirwiki.com/ko/wiki/java4shell
