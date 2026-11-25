---
title: "마이크로소프트 코파일럿 (Microsoft Copilot)"
subtitle: "윈도우, 마이크로소프트 365, 애저 전반에 통합된 마이크로소프트의 소비자 및 기업용 생성형 AI 어시스턴트"
canonical_url: https://mimirwiki.com/ko/wiki/microsoft-copilot
language: ko
page_class: entity
revision_sha256: 28a69477beaf32ab813719b30e64f9340de00ad48f7b409e39e3ef4e238be775
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/microsoft-copilot.md
  txt: https://mimirwiki.com/ko/wiki/microsoft-copilot.txt
  json: https://mimirwiki.com/ko/wiki/microsoft-copilot.json
  jsonld: https://mimirwiki.com/ko/wiki/microsoft-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/microsoft-copilot
  ja: https://mimirwiki.com/ja/wiki/microsoft-copilot
  zh: https://mimirwiki.com/zh/wiki/microsoft-copilot
  es: https://mimirwiki.com/es/wiki/microsoft-copilot
---

# 마이크로소프트 코파일럿 (Microsoft Copilot)

> 2026년 11월 기준 마이크로소프트 코파일럿은 웹 기반 무료/기본형인 코파일럿 챗(Copilot Chat, copilot.cloud.microsoft), 유료 좌석 라이선스인 마이크로소프트 365 코파일럿(엔터프라이즈 월 30달러 추가 옵션; 중소기업용 Microsoft Copilot Business 월 18~32달러), 최상위 엔터프라이즈 플랜인 Microsoft 365 E7, 그리고 사용량 기반 요금제가 적용되는 코파일럿 스튜디오 및 코워크(Cowork) 에이전트로 구성된다. 2026년 후반에는 오픈AI 외에도 앤트로픽의 클로드(Claude) 모델을 공식 하위 처리자(Subprocessor)로 통합하여 멀티모델 아키텍처를 확장했다.

마이크로소프트 코파일럿(Microsoft Copilot)은 마이크로소프트(Microsoft Corporation)가 웹 및 모바일 인터페이스, 윈도우 11(Windows 11), 마이크로소프트 365(Microsoft 365) 생산성 제품군, 코파일럿 스튜디오(Copilot Studio) 전반에 걸쳐 제공하는 생성형 인공지능(AI) 어시스턴트 및 에이전트 플랫폼 제품군이다. 오픈AI(OpenAI) 및 앤트로픽(Anthropic)의 프런티어 파운데이션 모델과 마이크로소프트 그래프(Microsoft Graph) 조직 데이터(Work IQ)를 결합하여 대화형 검색, 문서·코드 작성, 다단계 자율 엔터프라이즈 워크플로를 수행한다.

**다른 이름:** Microsoft Copilot, Microsoft 365 Copilot, 마이크로소프트 365 코파일럿, 코파일럿 스튜디오

## 핵심 정보

- **개발사:** 마이크로소프트 (Microsoft Corporation, SEC CIK 0000789019) [1]
- **엔터프라이즈 추가 요금:** 사용자당 월 30달러 (연간 약정 기준) (기준 2026-11-23) [2]
- **중소기업(SMB) 비즈니스 요금:** 단독 추가 옵션 월 18달러; M365 비즈니스 번들 월 23.50~32달러 (기준 2026-11-23) [2]
- **에이전트 턴 실행 한도:** 코파일럿 스튜디오 기준 단일 턴 최대 90분, 턴당 도구 호출 최대 200회 (기준 2026-11-23) [7]

## 기본 정보

- **개발사:** 마이크로소프트 (Microsoft Corporation) [1]
- **주요 웹 엔드포인트:** copilot.microsoft.com (소비자) / copilot.cloud.microsoft (기업·교육) [4]
- **그라운딩 아키텍처:** 마이크로소프트 그래프 (Microsoft Graph / Work IQ) 및 빙(Bing) 웹 인덱스 [4]
- **기반 모델 공급사:** 오픈AI (Azure OpenAI Service) 및 앤트로픽 (Claude 하위 처리자) [5]
- **엔터프라이즈 라이선스:** Microsoft 365 Copilot 추가 옵션, Microsoft 365 E7, Microsoft Copilot Business [3]
- **에이전트 빌더 플랫폼:** 마이크로소프트 코파일럿 스튜디오 (종량제 또는 메시지 팩 과금) [7]
- **엔터프라이즈 데이터 보호:** 상업용 프롬프트 및 응답은 파운데이션 모델 학습에 사용되지 않음 (EDP) [6]
- **회계연도 공시 기준:** 2026년 6월 30일 종료 회계연도(FY2026) Form 10-K 연차보고서 (연 매출 3,318억 3,900만 달러) [1]

## 개요 및 제품 아키텍처

마이크로소프트 코파일럿(Microsoft Copilot)은 소비자, 기업 및 개발자 환경 전반에 걸쳐 제공되는 마이크로소프트의 생성형 AI 어시스턴트 통합 브랜드이자 오케스트레이션 프레임워크이다 [1][4]. 2023년 빙 챗(Bing Chat)과 마이크로소프트 365 코파일럿으로 처음 출시된 이후 단일 브랜드로 통합되었으며, 거대언어모델(LLM)을 웹 검색 인덱스, 운영체제 텔레메트리, 엔터프라이즈 조직 그래프와 연결한다 [1][4].

기업용 제품의 핵심 아키텍처는 과거 마이크로소프트 그래프 그라운딩(Microsoft Graph grounding)으로 불리던 **워크 IQ(Work IQ)**이다 [4]. 워크 IQ는 기존의 역할 기반 접근 제어(RBAC)와 마이크로소프트 퍼뷰(Microsoft Purview) 민감도 레이블 권한을 엄격히 준수하면서 테넌트 내 이메일, 마이크로소프트 팀즈(Teams) 채팅, 셰어포인트(SharePoint) 사이트, 원드라이브(OneDrive) 문서, 일정 메타데이터를 파운데이션 모델에 연결한다 [4][6]. 인증된 기업 사용자가 `copilot.cloud.microsoft` 또는 오피스 앱 내부에서 프롬프트를 입력하면 코파일럿 오케스트레이터는 사용자에게 허용된 그래프 범위에서 시맨틱 검색을 수행해 프롬프트를 보강하고, 선택된 LLM으로 라우팅한 뒤 규정 준수 및 책임 있는 AI(Responsible AI) 검증을 거쳐 응답을 스트리밍한다 [4][6].

## 제품 티어, Microsoft 365 E7 및 요금 체계

마이크로소프트는 코파일럿을 무료 소비자용, 상업용 기본 챗, 유료 좌석 기반 생산성 애드온, 그리고 사용량 기반 에이전트 과금 체계로 구분하여 운영한다 [2][3][4]:

| 티어 / 플랜 | 대상 고객 | 주요 기능 | 요금 (2026년 11월 기준) |
| --- | --- | --- | --- |
| **Microsoft Copilot (소비자용)** | 개인 소비자 | 웹 그라운딩 채팅, 이미지 생성, 음성 대화, 윈도우·모바일 앱 | 무료 (유료 Copilot Pro 별도) [4] |
| **Microsoft Copilot Chat** | 기업·교육용 Entra ID 계정 | 엔터프라이즈 데이터 보호(EDP)가 적용된 웹 그라운딩 채팅, 코파일럿 페이지, 종량제 에이전트 | 적격 M365 라이선스에 기본 포함 (에이전트는 사용량 과금) [4] |
| **Microsoft Copilot Business** | 중소기업 (최대 300석) | 워드, 엑셀, 파워포인트, 아웃룩, 팀즈 내 업무 데이터 그라운딩 코파일럿 | 단독 추가 옵션 월 18달러; M365 비즈니스 번들 월 23.50~32달러 [2] |
| **Microsoft 365 Copilot (엔터프라이즈)** | 대기업 테넌트 (E3/E5 기반) | 전체 Work IQ 그라운딩, 오피스 앱 내장 기능, 코파일럿 스튜디오 에이전트 사용 포함 | 사용자당 월 30달러 (연간 약정) [2][3] |
| **Microsoft 365 E7** | 프런티어 엔터프라이즈 도입 기업 | M365 E5, Microsoft 365 Copilot 및 고급 에이전트 기능을 통합한 최상위 엔터프라이즈 스위트 | 엔터프라이즈 계약(EA) 요금 [3] |

좌석당 정액 라이선스 외에도 마이크로소프트는 **코파일럿 코워크(Copilot Cowork)**, **코파일럿 코드(Copilot Code)**, **코파일럿 오토파일럿(Copilot Autopilot)** 등 장기 실행 자율 워크플로를 위해 애저(Azure) 구독 연동 종량제(Pay-as-you-go) 또는 사전 구매 크레딧(Copilot Credit) 용량 팩 기반 과금 모델을 함께 제공한다 [3][5].

## 멀티모델 오케스트레이션 및 앤트로픽(Anthropic) 통합

초기 마이크로소프트 코파일럿은 애저 오픈AI 서비스(Azure OpenAI Service)에서 호스팅되는 오픈AI 모델에만 의존했으나, 2025년과 2026년을 거치며 멀티모델 오케스트레이션 플랫폼으로 확장되었다 [4][5]. 마이크로소프트의 공식 기술 문서에 따르면 코파일럿은 자체 내부 모델과 더불어 오픈AI 및 앤트로픽(Anthropic)의 프런티어 모델을 함께 활용한다 [4][5].

특히 마이크로소프트는 앤트로픽을 공식 온라인 서비스 하위 처리자(Microsoft Online Services Subprocessor)로 지정하여, 기업 관리자와 코파일럿 스튜디오 개발자가 마이크로소프트 365 코파일럿, 코파일럿 코워크, 코파일럿 스튜디오 내에서 심층 추론, 코딩, 다단계 리서치 작업에 앤트로픽의 클로드(Claude) 모델을 활성화할 수 있도록 지원한다 [5]. 클로드 모델 호출 시에도 고객 데이터는 마이크로소프트의 상업용 약관 및 엔터프라이즈 데이터 보호(EDP) 약정의 적용을 받으며, 리전 가용성에 따라 하위 처리자 데이터 보호 계약 하에 앤트로픽의 관리형 인프라에서 요청이 처리될 수 있다 [5][6].

## 코파일럿 스튜디오 및 에이전트 런타임 쿼터

마이크로소프트 코파일럿 스튜디오(Microsoft Copilot Studio)는 코파일럿 챗과 마이크로소프트 팀즈에 직접 배포되는 선언형 에이전트(declarative agents), 자율 워크플로, 컴퓨터 사용 에이전트를 제작하는 로우코드·프로코드 빌더 환경이다 [4][7]. 마이크로소프트는 무한 루프 방지와 멀티에이전트 오케스트레이션 안정성을 위해 코파일럿 스튜디오 에이전트에 다음과 같은 엄격한 런타임 쿼터와 실행 한도를 적용한다 [7]:

- **최대 턴 지속 시간(Maximum Turn Duration)**: 단일 에이전트 오케스트레이션 턴은 타임아웃 전까지 최대 **90분**(5,400초) 동안 실행될 수 있다 [7].
- **턴당 도구 호출 횟수(Tool Calls per Turn)**: 단일 턴 내에서 커넥터, 액션, 플러그인을 통틀어 최대 **200회**의 도구 호출을 지원한다 [7].
- **개별 도구 및 커넥터 타임아웃**: 표준 동기식 도구 또는 커넥터 실행은 **120초** 후 타임아웃된다 [7].
- **에이전트 플로/워크플로 타임아웃**: 내장된 파워 오토메이트(Power Automate) 및 에이전트 워크플로의 동기 실행 한도는 **660초**(11분)이다 [7].
- **연결된 에이전트 및 외부 에이전트 타임아웃**: 내부 연결된 코파일럿 스튜디오 에이전트 호출은 최대 **5,400초**(90분)까지 실행 가능하며, 외부 A2A/MCP 에이전트 호출은 **300초**(5분) 후 타임아웃된다 [7].
- **대화 컨텍스트 및 스트리밍**: 오케스트레이션은 대화당 최근 **100개 메시지**의 슬라이딩 컨텍스트 윈도우를 유지하며, 팀즈 내 실시간 스트리밍 응답은 세그먼트당 **2분**으로 제한된다 [7].

## 엔터프라이즈 데이터 보호(EDP) 및 거버넌스

마이크로소프트 엔트라 ID(Microsoft Entra ID) 계정으로 로그인하는 상업용, 정부 및 교육 기관 조직에는 마이크로소프트 제품 약관(Product Terms) 및 데이터 보호 부록(DPA)에 따른 **엔터프라이즈 데이터 보호(Enterprise Data Protection, EDP)**가 기본 적용된다 [6]. EDP 체계 하에서 사용자 프롬프트, 업로드 파일, 마이크로소프트 그래프 그라운딩 데이터 및 생성된 응답은 테넌트별로 논리적으로 격리되고 전송 및 저장 시 암호화되며, **공용 또는 파운데이션 거대언어모델을 학습시키는 데 절대 사용되지 않는다** [6].

또한 코파일럿은 기존 마이크로소프트 퍼뷰(Microsoft Purview) 거버넌스 정책을 그대로 상속한다 [6]. 문서가 권한 관리 서비스(RMS)로 암호화되어 있거나 추출을 제한하는 민감도 레이블을 보유한 경우 코파일럿은 요약을 차단하거나 생성된 결과물에 동일한 제한 레이블과 워터마크를 자동으로 전파한다 [6]. 관리자는 퍼뷰 감사(Audit), 커뮤니케이션 규정 준수(Communication Compliance), eDiscovery를 통해 모든 프롬프트 상호작용과 에이전트 도구 호출 내역을 감사할 수 있다 [6].

## 자주 묻는 질문

### 마이크로소프트 코파일럿 챗(Copilot Chat)과 마이크로소프트 365 코파일럿의 차이점은 무엇인가요?

마이크로소프트 코파일럿 챗은 적격 엔트라 ID(Entra ID) 기업·교육 계정에 추가 좌석 비용 없이 기본 제공되는 웹 그라운딩 어시스턴트(copilot.cloud.microsoft)로, 엔터프라이즈 데이터 보호(EDP)와 종량제 에이전트 접근을 제공합니다. 반면 마이크로소프트 365 코파일럿(엔터프라이즈 기준 월 30달러)은 이메일, 채팅, 파일을 아우르는 워크 IQ(마이크로소프트 그래프) 그라운딩과 워드, 엑셀, 파워포인트, 아웃룩, 팀즈 앱 내 통합 기능을 추가로 제공합니다. [2][4]

### 중소기업용 마이크로소프트 코파일럿 비즈니스(Microsoft Copilot Business)의 가격은 얼마인가요?

최대 300석 규모의 중소기업(SMB)을 위한 Microsoft Copilot Business는 연간 약정 기준 사용자당 월 18달러의 단독 추가 옵션(Add-on)으로 제공되며, Microsoft 365 Business Basic, Standard, Premium과 결합된 번들 플랜은 사용자당 월 23.50달러에서 32달러 사이의 프로모션 요금으로 제공됩니다. [2]

### 마이크로소프트 코파일럿은 오픈AI 외에 앤트로픽의 클로드(Claude) 모델도 사용하나요?

네, 그렇습니다. 마이크로소프트는 코파일럿을 멀티모델 아키텍처로 운영하고 있으며 앤트로픽(Anthropic)을 공식 온라인 서비스 하위 처리자(Subprocessor)로 등록하여, 기업 테넌트가 마이크로소프트 365 코파일럿, 코파일럿 스튜디오, 코파일럿 코워크에서 오픈AI 모델과 함께 클로드 모델을 사용할 수 있도록 지원합니다. [4][5]

### 마이크로소프트 코파일럿 스튜디오 에이전트의 실행 시간 및 도구 호출 한도는 어떻게 되나요?

2026년 후반 기준 코파일럿 스튜디오 에이전트는 단일 턴당 최대 90분(5,400초) 동안 실행될 수 있으며 턴당 최대 200회의 도구 호출을 수행할 수 있습니다. 개별 동기식 도구 호출은 120초, 에이전트 워크플로는 660초, 외부 에이전트 호출은 300초 후에 타임아웃됩니다. [7]

### 기업 사용자가 입력한 코파일럿 프롬프트가 파운데이션 AI 모델 학습에 사용되나요?

사용되지 않습니다. 상업용 엔트라 ID 사용자에게 적용되는 엔터프라이즈 데이터 보호(EDP) 약정에 따라 프롬프트, 마이크로소프트 그래프 컨텍스트 및 생성된 응답은 고객 테넌트 경계 내에 격리되며 파운데이션 모델 학습에 활용되지 않습니다. [6]

## 인용 문장

- 마이크로소프트 365 코파일럿 엔터프라이즈 추가 옵션은 사용자당 월 30달러이며, 중소기업용 Microsoft Copilot Business는 월 18달러 추가 옵션 및 월 23.50~32달러 번들 요금으로 제공된다. [2][3]
- 마이크로소프트는 앤트로픽(Anthropic)을 공식 온라인 서비스 하위 처리자로 등록하여 마이크로소프트 365 코파일럿, 코파일럿 스튜디오, 코파일럿 코워크에 클로드(Claude) 모델을 통합했다. [5]
- 마이크로소프트 코파일럿 스튜디오는 단일 턴 최대 실행 시간 90분(5,400초)과 턴당 최대 200회의 도구 호출 한도를 적용한다. [7]
- 코파일럿 스튜디오의 개별 도구 호출 타임아웃은 120초, 에이전트 워크플로 타임아웃은 660초, 외부 에이전트 호출 타임아웃은 300초이다. [7]
- 엔터프라이즈 데이터 보호(EDP) 약정에 따라 상업용 엔트라 ID 사용자의 프롬프트와 응답은 파운데이션 모델 학습에 사용되지 않는다. [6]

## 연표

- 2023-02: 마이크로소프트가 빙 챗(Bing Chat)이라는 명칭으로 최초의 생성형 AI 검색 어시스턴트를 출시함. [1]
- 2023-11: 기업 고객을 대상으로 마이크로소프트 365 코파일럿 정식 출시(GA) 및 빙 챗의 마이크로소프트 코파일럿 브랜드 통합. [1]
- 2026-06-30: 마이크로소프트가 연 매출 3,318억 4,000만 달러로 FY2026을 마감하며 Form 10-K 보고서에 마이크로소프트 365, 윈도우, 깃허브 전반의 코파일럿 확장을 공시함. [1]
- 2026-11: Microsoft 365 E7, 중소기업용 Microsoft Copilot Business 요금(월 18~32달러), 앤트로픽 클로드 하위 처리자 통합, 코파일럿 스튜디오 90분/200회 도구 호출 한도 문서화. [2][3][5][7]

## 출처

1. Microsoft Corporation Form 10-K for the Fiscal Year Ended June 30, 2026. U.S. Securities and Exchange Commission (SEC). 게시일 2026-07-29. https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (확인일 2026-11-23; tier 1: government or public registry)
2. Microsoft Copilot Plans and Pricing - AI for Business | Microsoft 365. Microsoft Corporation. https://www.microsoft.com/en-us/copilot/pricing/business (확인일 2026-11-23; tier 3: official site)
3. License Options for Microsoft Copilot | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-license-options (확인일 2026-11-23; tier 3: official site)
4. What is Microsoft Copilot? | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-overview (확인일 2026-11-23; tier 3: official site)
5. Claude models from Anthropic in Microsoft Online Services | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/implement/connect-to-ai-subprocessor (확인일 2026-11-23; tier 3: official site)
6. Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/enterprise-data-protection (확인일 2026-11-23; tier 3: official site)
7. Agent runtime limits - Microsoft Copilot Studio | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/runtime-limits (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "마이크로소프트 코파일럿 (Microsoft Copilot)." 버전 28a69477, 2026-11-23. https://mimirwiki.com/ko/wiki/microsoft-copilot
