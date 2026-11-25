---
title: "Microsoft 365"
subtitle: "Office 앱과 Exchange Online, Teams를 묶은 Microsoft 클라우드 생산성 제품군"
canonical_url: https://mimirwiki.com/ko/wiki/microsoft-365
language: ko
page_class: entity
revision_sha256: ee0de2bd0e1c70e307209b2501c67693f4a616a3707440545ef6017ef3437813
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/microsoft-365.md
  txt: https://mimirwiki.com/ko/wiki/microsoft-365.txt
  json: https://mimirwiki.com/ko/wiki/microsoft-365.json
  jsonld: https://mimirwiki.com/ko/wiki/microsoft-365.jsonld
translations:
  en: https://mimirwiki.com/wiki/microsoft-365
---

# Microsoft 365

> Microsoft 365는 Office 앱과 Exchange Online, Teams 등 클라우드 서비스를 묶은 제품군이다. 2026년 11월 20일자 사후 보고서 공개 사본(EX1550543/MO1550821)은 11월 12일 장애가 유지보수·Teams 트래픽 전환·피크 부하가 겹치며 드러난 Exchange Online 게이트웨이의 Windows 결함 때문이라고 밝혔으며, 장애 상태는 Microsoft 365 관리 센터, 공개 상태 페이지, X(@MSFT365status)에서 확인할 수 있다.

Microsoft 365는 웹용 Office, Microsoft Teams, Exchange Online, SharePoint Online, OneDrive for Business, Microsoft 365 Copilot 등을 통합 제공하는 Microsoft의 클라우드 생산성 제품군이다. 2026년 11월 12일 Exchange Online 네트워크 게이트웨이 서버의 잠재적 Windows 결함으로 대규모 장애가 발생했으며, 11월 24일 로이터는 내부 메모를 인용해 Microsoft가 'Code Red'를 선포했다고 보도했다.

**다른 이름:** M365, Office 365, 마이크로소프트 365

## 핵심 정보

- **개발사:** Microsoft Corporation [1]
- **상태 확인 경로:** Microsoft 365 관리 센터(admin.microsoft.com), 공개 서비스 상태 페이지, X(@MSFT365status) [2]
- **2026년 11월 장애 ID:** EX1550543 / MO1550821 (11월 12일 발생, 11월 13일 오후 4시 10분 실시간 영향 종료) (기준 2026-11-25) [4]
- **언론 보도 후속 조치:** 2026년 11월 24일 로이터가 내부 메모 근거 'Code Red' 선포 보도 (기준 2026-11-25) [5]

## 기본 정보

- **제품명:** Microsoft 365 [1]
- **개발사:** Microsoft Corporation [1]
- **핵심 클라우드 서비스:** Exchange Online, Microsoft Teams, 웹용 Office, SharePoint Online, OneDrive for Business, Copilot [2]
- **메시징 기반:** Exchange Online (이메일·일정·연락처·작업, Microsoft Entra ID 통합) [3]
- **관리자 상태 포털:** https://admin.microsoft.com (서비스 상태 페이지) [2]
- **2026년 11월 사후 보고서:** EX1550543 / MO1550821 (2026년 11월 20일자) [4]

## Microsoft 365 플랫폼 개요

Microsoft 365는 조직의 협업, 커뮤니케이션, 문서 생산성을 지원하는 구독형 클라우드 제품군이다.[1][2] Microsoft 365 관리 체계에 포함되는 핵심 서비스에는 웹용 Office, Microsoft Teams, Exchange Online, SharePoint Online, OneDrive for Business, Microsoft 365 Copilot 등이 있다.[2][4]

이 가운데 Exchange Online은 PC, 웹, 모바일 기기 전반에서 이메일, 일정, 연락처, 작업을 제공하는 호스팅 메시징 서비스이며, Microsoft Entra ID와 통합되어 관리자가 그룹 정책과 관리 도구를 통해 메시징 환경을 제어할 수 있다.[3]

## Microsoft 365 2026년 11월 12일 Exchange Online 대규모 장애

Microsoft 365는 2026년 11월 12일부터 사건 번호 EX1550543 및 MO1550821로 분류된 대규모 서비스 장애를 겪었다.[4] 2026년 11월 20일자 Microsoft 사후 보고서(Post Incident Report)의 공개 사본에 따르면, 표준 Windows 배포에는 없는 Exchange Online 전용 구성의 잠재적 Windows 결함이 부하 증가 상황에서 Exchange Online 네트워크 게이트웨이 서버를 무응답 상태로 만들었다.[4]

보고서는 계획된 유지보수로 인한 용량 감소, Teams 트래픽의 Exchange Online 게이트웨이 전환, 북미 피크 시간대 트래픽이라는 세 가지 운영 조건이 겹치며 결함이 촉발됐다고 밝혔다.[4] 이후 자동 트래픽 재분배가 전 세계 정상 서버로 부하를 전파하면서 Exchange Online 메일 접속뿐 아니라 이에 의존하는 Copilot, Teams, SharePoint Online, OneDrive for Business, Defender, Purview, Fabric, Intune, Planner, Power Apps, To Do, Power BI, Universal Print의 기능까지 연쇄 영향을 받았다.[4]

Microsoft는 대기 중인 이메일이 반송되지 않도록 재전송 기간을 48시간으로 연장했으며, 11월 13일 오후 4시 10분 고객의 실시간 영향 종료를 확인한 뒤 11월 14일 오전 4시 15분 최종 공지를 발행했다.[4] 보고서에 포함된 재발 방지 과제는 2026년 4분기(CY26 Q4)와 2027년 1분기(CY27 Q1)를 목표로 워크로드별 게이트웨이 풀 분리, Teams 장애 조치의 지역 한정 적용, 피크 부하 테스트 확대 등을 담고 있다.[4]

## Microsoft 365 'Code Red' 언론 보도

Microsoft 365는 2026년 11월 24일 로이터가 내부 메모를 근거로 Microsoft의 'Code Red' 선포를 단독 보도하면서 다시 주목받았다.[5][7] 로이터 보도를 전한 더 넥스트 웹(The Next Web)과 9to5Mac에 따르면 M365 코어 사장 제이슨 헨더슨은 이번 장애를 Exchange Online 역사상 고객 영향이 가장 큰 사건으로 규정하고, 'Code Red'를 팀의 최우선 과제로 지정했다.[5][6]

같은 보도에서 기업 부사장 아만다 실버는 대응 과정이 '전장의 안개(fog of war)'와 같았으며, 진단 데이터가 분리된 내부 시스템에 흩어져 있어 대응 인력이 11개 Teams 채팅방에서 11,000건 이상의 메시지를 주고받았다고 설명했다.[5] 9to5Mac은 장애 정점에서 게이트웨이 서버의 80% 이상이 응답하지 않았으며 Microsoft가 향후 장애 복구 목표를 1시간 이내로 잡고 있다고 전했다.[6] 다만 내부 메모 원문 전체와 전체 영향 사용자 수는 Microsoft가 공식 공개하지 않았다.[5]

## Microsoft 365 서비스 상태 확인 방법

Microsoft 365 관리자는 Microsoft 365 관리 센터(admin.microsoft.com)의 서비스 상태(Service health) 페이지에서 현재 발생한 문제가 알려진 서비스 장애인지 확인할 수 있다.[2] 공식 문서에 따르면 서비스 지원 관리자(Service Support admin) 또는 기술 지원팀 관리자(Helpdesk admin) 권한이 부여된 계정이 서비스 상태를 조회할 수 있다.[2]

장애로 인해 관리 센터 로그인 자체가 불가능할 경우 Microsoft는 공개 서비스 상태 페이지를 통해 로그인 차단 여부를 확인하고, 특정 이벤트 공지는 X의 @MSFT365status 계정을 통해 확인하도록 안내한다.[2]

## 자주 묻는 질문

### 2026년 11월 12일 장애 때 Outlook과 Teams, Copilot이 한꺼번에 영향을 받은 이유는 무엇인가요?

2026년 11월 20일자 Microsoft 사후 보고서(EX1550543/MO1550821) 공개 사본에 따르면, 유지보수 용량 감소와 Teams 트래픽 전환, 북미 피크 트래픽이 겹치면서 Exchange Online 게이트웨이 서버의 잠재적 Windows 결함이 드러났고, Exchange Online 기능에 의존하는 Teams, Copilot, SharePoint, OneDrive 등 여러 서비스가 연쇄적으로 영향을 받았습니다. [4]

### Microsoft 365 장애 상태는 어디서 확인할 수 있나요?

관리자는 Microsoft 365 관리 센터(admin.microsoft.com)의 서비스 상태 페이지에서 확인할 수 있으며, 관리 센터 로그인이 불가한 경우 공개 서비스 상태 페이지나 X의 @MSFT365status 계정을 통해 공지를 확인할 수 있습니다. [2]

### 2026년 11월 보도된 Microsoft 365 'Code Red'는 무엇인가요?

2026년 11월 24일 로이터가 내부 메모를 인용해 보도한 내용으로, 대규모 Exchange Online 장애 이후 장애 예방, 진단 통합, 복구 속도 개선을 최우선 과제로 삼은 내부 대응 체계를 뜻합니다. 내부 메모 원문 전체는 공개되지 않았습니다. [5][6][7]

### 2026년 11월 20일자 Microsoft 사후 보고서에 담긴 장기 재발 방지 대책은 무엇인가요?

사후 보고서 공개 사본에는 2026년 4분기와 2027년 1분기를 목표로 워크로드별 네트워크 게이트웨이 풀 분리, Teams 장애 조치의 지역 한정 적용, 지역 간 연쇄 장애 방지, 피크 부하 테스트 확대 등이 포함돼 있습니다. [4]

## 인용 문장

- 2026년 11월 20일자 Microsoft 사후 보고서 공개 사본(EX1550543/MO1550821)은 11월 12일 장애가 Exchange Online 게이트웨이 서버의 잠재적 Windows 결함으로 발생해 Exchange Online과 의존 서비스에 영향을 주었다고 밝혔다. [4]
- Microsoft는 11월 13일 오후 4시 10분 고객의 실시간 영향 종료를 확인하고 11월 14일 오전 4시 15분 최종 공지를 발행했다. [4]
- 2026년 11월 24일 로이터는 내부 메모를 인용해 Microsoft가 'Code Red'를 선포했다고 보도했으며, 내부 메모 원문과 전체 영향 사용자 수는 공식 공개되지 않았다. [5][6][7]
- Microsoft 365 관리자는 Microsoft 365 관리 센터(admin.microsoft.com)의 서비스 상태 페이지, 공개 서비스 상태 페이지, 또는 X의 @MSFT365status 계정을 통해 서비스 장애 여부를 확인할 수 있다. [2]

## 출처

1. Microsoft 365 for enterprise overview. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide (확인일 2026-11-25; tier 3: official site)
2. How to check Microsoft 365 service health. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-365/enterprise/view-service-health?view=o365-worldwide (확인일 2026-11-25; tier 3: official site)
3. Exchange Online service description. Microsoft Learn. https://learn.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description (확인일 2026-11-25; tier 3: official site)
4. Post Incident Report for Microsoft 365 (EX1550543 / MO1550821, Public Copy). Microsoft Corporation (hosted by 365fanatic.com). 게시일 2026-11-20. https://www.365fanatic.com/wp-content/uploads/2026/11/postincidentreport-mo1550821.pdf (확인일 2026-11-25; tier 2: academic or news)
5. Microsoft declares 'Code Red' after its worst email outage, Reuters reports. The Next Web. 게시일 2026-11-24. https://thenextweb.com/news/microsoft-code-red-exchange-online-outage-memos-reuters (확인일 2026-11-25; tier 2: academic or news)
6. Microsoft declares a Code Red in response to worst ever outage. 9to5Mac. 게시일 2026-11-25. https://9to5mac.com/2026/11/25/microsoft-declares-a-code-red-in-response-to-worst-ever-outage/ (확인일 2026-11-25; tier 2: academic or news)
7. Microsoft declares 'Code Red' after historic outage, internal memos show: Reuters exclusive. CTV News (Reuters). 게시일 2026-11-24. https://www.ctvnews.ca/sci-tech/article/microsoft-declares-code-red-after-historic-outage-internal-memos-show-reuters-exclusive/ (확인일 2026-11-25; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "Microsoft 365." 버전 ee0de2bd, 2026-11-25. https://mimirwiki.com/ko/wiki/microsoft-365
