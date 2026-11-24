---
title: "Cursor"
subtitle: "Anysphere, Inc.가 개발하고 The X Subscription에 통합된 AI 코딩 에이전트 및 소프트웨어 개발 환경"
canonical_url: https://mimirwiki.com/ko/wiki/cursor
language: ko
page_class: entity
revision_sha256: 35e1ceeb8fbfe9a66c8a60ac248f570f5586983ed4a22cb467ef3ec33c5e7cd7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ko/wiki/cursor.md
  txt: https://mimirwiki.com/ko/wiki/cursor.txt
  json: https://mimirwiki.com/ko/wiki/cursor.json
  jsonld: https://mimirwiki.com/ko/wiki/cursor.jsonld
translations:
  en: https://mimirwiki.com/wiki/cursor
  ja: https://mimirwiki.com/ja/wiki/cursor
  zh: https://mimirwiki.com/zh/wiki/cursor
---

# Cursor

> Cursor는 2022년 설립된 Anysphere, Inc.가 개발한 AI 코딩 에이전트이자 소프트웨어 개발 환경이다. 2026년 6월 SpaceX는 600억 달러 규모의 주식 거래로 Cursor를 인수하기로 합의했다. 2026-11-23 기준 Cursor는 The X Subscription을 통해 월 0달러부터 200달러까지의 요금제로 판매되며 Agent, Tab 자동 완성, Cloud Agents, Rules, Skills, MCP, CLI와 여러 제공사의 모델을 지원한다.

Cursor는 Anysphere, Inc.가 개발한 AI 코딩 에이전트이자 소프트웨어 개발 환경으로, 코드베이스 이해, 기능 계획과 구현, 버그 수정, 코드 변경 사항 검토에 쓰인다. 2022년 Anysphere로 설립된 이 스타트업은 SpaceX가 xAI와 합병한 데 이어 2026년 6월 600억 달러 규모의 주식 거래로 SpaceX에 인수되기로 합의했다. 2026-11-23 기준 Cursor는 X Subscription Corp.를 통해 The X Subscription의 일부로 제공되며 Free, Plus(월 8달러), Premium(월 30달러), Super(월 100달러), Ultra(월 200달러), Teams(좌석당 월 30달러~200달러), 맞춤형 Enterprise 요금제를 두고 있고, 기존 가입자의 레거시 Cursor 요금제도 유지된다. Cursor는 통합 데스크톱 개발 환경(IDE), 전용 Agents Window, 명령줄 인터페이스(Command-Line Interface, CLI), 웹, iOS에서 동작하며 자체 모델인 Grok 및 Composer와 OpenAI, Anthropic, Google의 서드파티 모델을 지원한다.

**다른 이름:** 커서, Cursor IDE, Cursor 에디터, Anysphere Cursor

## 핵심 정보

- **개발사:** Anysphere, Inc. [9]
- **SpaceX 인수 합의:** 주식 600억 달러 규모, 2026-06-16 보도 [1]
- **개인 요금제 가격:** Free(0달러), Plus(월 8달러), Premium(월 30달러), Super(월 100달러), Ultra(월 200달러) (기준 2026-11-23) [5]
- **Teams 요금제 가격:** 좌석당 월 30달러, 100달러 또는 200달러 (기준 2026-11-23) [5]
- **보안 인증:** SOC 2 Type II, ISO/IEC 27001:2022, ISO/IEC 42001:2023, AIUC-1 (기준 2026-11-23) [8]

## 기본 정보

- **개발사:** Anysphere, Inc. [9]
- **설립 연도:** 2022년(Anysphere로 설립) [1]
- **인수 합의:** SpaceX, 주식 600억 달러 규모(2026-06-16 보도, 2026년 3분기 마무리 예정) [1]
- **구독 판매 법인:** X Subscription Corp.(The X Subscription) (기준 2026-11-23) [4]
- **지원 환경:** 에디터, Agents Window, CLI, Cursor SDK, iOS 앱 (기준 2026-11-23) [6]
- **사용자 지정 기능:** Plugins, Rules, Skills, Subagents, Hooks, MCP (기준 2026-11-23) [3]
- **기본 포함 Cursor 모델:** Grok 4.7, Grok 4.6, Grok 4.5, Composer 2.5 (기준 2026-11-23) [5]
- **개인 요금제:** Free(0달러), Plus(월 8달러), Premium(월 30달러), Super(월 100달러), Ultra(월 200달러) (기준 2026-11-23) [5]
- **Teams 및 Enterprise:** Teams(좌석당 월 30달러, 100달러 또는 200달러), Enterprise(개별 산정) (기준 2026-11-23) [5]
- **보도된 ARR(2025년 6월):** 5억 달러 초과(Bloomberg 및 TechCrunch 보도) (기준 2025-06-05) [2]
- **보안 인증:** AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023, SOC 2 Type II (기준 2026-11-23) [8]
- **공식 웹사이트:** cursor.com [9]

## Cursor 제품 기능, 사용자 지정, 인터페이스

Cursor는 Anysphere, Inc.가 공식 문서에서 소프트웨어 구축용 코딩 에이전트로 설명하는 도구이며 저장소 구조 파악, Plan Mode를 활용한 기능 설계 및 구현, 버그 재현과 수정, 병합 전 변경 사항(diff) 검토와 검사 실행, 외부 개발 도구 연동을 핵심 작업으로 제시한다.[3] 무료(Free) 요금제부터 Cursor 자체 모델을 쓰는 Agent, Chat, Tab 자동 완성 기능을 제한된 사용량으로 이용할 수 있다.[6]

Cursor의 Agent 인터페이스는 데스크톱 통합 개발 환경(IDE), 전용 Agents Window, 웹 클라이언트, iOS용 Cursor, 명령줄 인터페이스(Command-Line Interface, CLI)에 걸쳐 동작한다.[3][6][7] 2026-11-23 기준 Agent 문서에는 Projects, Agent Review, Planning, Prompting, Voice Chat, Debugging, Design Mode, Tools, Security 항목이 수록되어 있으며, CLI 문서에는 Shell Mode, ACP, Headless 및 CI 실행이 포함되어 있다.[3] Cursor는 TypeScript, Python, Bridge 연동을 위한 Cursor SDK도 제공한다.[3]

Cursor는 작업 흐름 사용자 지정 기능을 Plugins, Rules, Skills, Subagents, Hooks, [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(Model Context Protocol, MCP) 서버 여섯 가지로 구분해 문서화한다.[3] Teams 및 Enterprise 요금제에서는 내부 규칙, 스킬, 플러그인을 배포하는 팀 마켓플레이스(team marketplace)를 추가로 제공한다.[4][5]

Cursor 공식 문서는 소스 관리, IDE, 협업 및 이슈 추적 도구와의 연동 목록으로 GitHub, GitLab, Azure DevOps, Bitbucket, JetBrains, Xcode, Slack, Microsoft Teams, Jira, Linear, Notion, Tailscale, Deeplinks를 기재한다.[3]

## Cursor Cloud Agents, Origin, Agent SDK, Voice Chat

Cursor는 Premium 등급부터 Cloud Agents, Automations, Origin 코드 호스팅, Bugbot AI 코드 리뷰 기능을 제공한다.[4][5] 2026-11-23 기준 Cloud Agents 문서에는 환경 설정(Setup), 빌드(Builds), 앱(Apps), 자동화(Automations), Bugbot, 보안 검토(Security Review), 취약점 수정(Vulnerability Remediation), 풀 리퀘스트 라우팅 및 승인(PR Routing & Approval), 롤아웃(Rollouts), 모바일, 자체 호스팅 머신(Self-Hosted Machines), API가 포함되어 있다.[3] Origin은 CLI, GitHub 미러링, CI용 CloneKit, 풀 리퀘스트, Code Tours, 저장소 탐색 및 검색, 접근 정책을 갖춘 코드 호스팅 서비스이다.[3]

2026년 10월과 11월 사이 Cursor는 변경 이력(Changelog)을 통해 네 가지 주요 플랫폼 기능을 공개했다.[7]

- **Origin App Marketplace(2026년 10월 13일)**: 20개가 넘는 연동 앱과 함께 공개 제출을 개시했다. 배포([Cloudflare](https://mimirwiki.com/ko/wiki/cloudflare), Netlify, Render, Spacelift, Vercel), 지속적 통합(Buildkite, CircleCI, CloudBees, Depot, EngFlow, Namespace, RWX), 코드 리뷰(CodeRabbit, Greptile, Tenki), 보안(Artemis Security, Semgrep, Socket Security, Upwind), 모니터링(Sentry), 프로젝트 관리(Linear) 분야의 파트너 앱이 포함된다. Origin 앱은 앱 JWT와 설치 액세스 토큰으로 인증하고 웹훅 이벤트를 수신해 체크 실행, 풀 리퀘스트 댓글, 리뷰를 회신한다.[7]
- **Cloud Agent Canvases 및 Environments API(2026년 10월 16일)**: 클라우드 에이전트가 생성해 링크로 공유할 수 있는 대화형 캔버스(Canvases)와 에이전트 클라우드 환경을 프로그래밍 방식으로 생성하고 관리하는 Environments API 베타를 도입했다. 클라우드 에이전트 환경당 지원 저장소 수는 최대 300개로 늘었고 대규모 환경의 로딩 속도는 5배 빨라졌다.[7]
- **Agent SDK(2026년 10월 20일)**: 정식 출시(GA)되었다. 에이전트를 하나의 코드 폴더로 정의하며 `instructions.md`(프롬프트), `tools/`(타입이 지정된 작업), `skills/`(필요 시 불러오는 절차), `mcp-connections/`(MCP 서버 도구), `channels/`(GitHub, GitLab, Bitbucket, Slack, 웹훅, 크론 일정 트리거)로 구성한다. 로컬 초기화와 플레이그라운드(`npx @cursor/agent-sdk init`, `agent-sdk dev`), 검증(`agent-sdk validate`), 평가 및 풀 리퀘스트 웹훅 재생(`agent-sdk eval`, `agent-sdk github replay`), 보안 리뷰어 및 PR 자동 수정 등 템플릿, Cursor 또는 자체 인프라 배포(`agent-sdk deploy`)를 지원한다.[7]
- **Live Apps(2026년 11월 5일)**: 클라우드 에이전트가 활성화된 모든 유료 요금제에 출시되었다. 클라우드 에이전트가 Cursor Origin 또는 GitHub 저장소에서 웹 애플리케이션을 구성하고, 필요 시 Postgres 데이터베이스를 프로비저닝하며, Cursor 싱글 사인온(Single Sign-On, SSO) 인증을 설정한 뒤 자격 증명 노출 여부 등에 대한 결정론적 및 에이전트 기반 보안 검사를 거쳐 지정된 URL로 배포한다. 팀 관리자는 모든 앱과 시크릿을 조회하고 사용자 지정 보안 규칙을 추가하거나 차단된 게시를 승인하고 앱 게시를 취소할 수 있다. 개인 요금제 사용자는 앱을 공개 공유할 수 있으며 스크립트나 Grok Bot용 Cursor API 키를 발급할 수 있다.[7]

2026년 11월 6일 Cursor는 Agents Window, IDE, 웹, iOS용 Cursor에서 코딩 에이전트와 실시간 음성 통화를 하는 Voice Chat을 출시했고, iOS에서는 `"Hey Siri, call Cursor"` 호출과 잠금 화면 Live Activity 제어를 지원한다.[7] Voice Chat은 [Grok](https://mimirwiki.com/ko/wiki/grok) Voice로 구동되며 Ara, Eve, Leo, Rex, Sal 등의 음성을 선택할 수 있고 Privacy Mode를 켜면 데이터 무보존(zero data retention)으로 동작한다.[7] Voice Chat은 양방향 음성 대화 기능이며, 음성을 채팅 입력창의 텍스트로 바꾸는 받아쓰기 기능(이전 명칭 Voice Mode, IDE 단축키 `Cmd+Shift+Space`)과는 별도이다.[7]

## Cursor 지원 모델과 Cursor Router

Cursor는 SpaceXSI, [OpenAI](https://mimirwiki.com/ko/wiki/openai), [Anthropic](https://mimirwiki.com/ko/wiki/anthropic), Google, Muse의 모델을 지원하며 2026-11-23 기준 구독의 주간 사용량 풀에 포함되는 자체 Cursor 모델과 선불 크레딧에서 API 정가로 과금되는 서드파티 모델로 구분한다.[3][5] 대상 모델에서 지역 데이터 레지던시(regional data residency) 옵션을 선택하면 모델 가격에 10%가 가산된다.[5]

Cursor 자체 모델 풀에는 [Grok](https://mimirwiki.com/ko/wiki/grok) 4.7, Grok 4.6, Grok 4.5, Composer 2.5가 포함된다.[5] 주간 풀을 초과해 추가 사용량을 구매할 때는 2026-11-23 기준 다음의 100만 토큰당 요율이 적용된다.[3][5]

| Cursor 모델 | 기본 / 최대 컨텍스트 | 일반 입력 / 캐시 읽기 / 출력(100만 토큰당) | Fast 모드 입력 / 캐시 읽기 / 출력(100만 토큰당) | 미국 데이터 레지던시 |
| --- | --- | --- | --- | --- |
| Grok 4.7 | 256k / 500k | 2달러 / 0.5달러 / 6달러(500k: 4달러 / 1달러 / 12달러) | 4달러 / 1달러 / 12달러(500k Fast: 6달러 / 1.5달러 / 18달러) | 지원 |
| Grok 4.6 | 256k / - | 2달러 / 0.5달러 / 6달러 | 4달러 / 1달러 / 12달러 | 지원 |
| Grok 4.5 | 256k / - | 2달러 / 0.5달러 / 6달러 | 4달러 / 1달러 / 18달러 | 지원 |
| Composer 2.5 | 200k / - | 0.5달러 / 0.2달러 / 2.5달러 | 3달러 / 0.5달러 / 15달러 | 지원 |

서드파티 모델은 Free와 Plus 요금제에서 사용할 수 없으며 Premium 이상 요금제에서 첫 요청부터 API 정가로 제공된다.[5] 2026-11-23 기준 Cursor 문서에 기재된 [Claude](https://mimirwiki.com/ko/wiki/claude), GPT-5.6, [Google Gemini](https://mimirwiki.com/ko/wiki/google-gemini) 등 서드파티 모델의 100만 토큰당 가격은 다음과 같다.[3][5]

| 서드파티 모델 | 기본 / 최대 컨텍스트 | 입력 | 캐시 쓰기 | 캐시 읽기 | 출력 | 미국 데이터 레지던시 |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 300k / 1M | 8달러 | 10달러 | 0.2달러 | 40달러 | 지원 |
| Claude Opus 5.5 | 300k / 1M | 4달러 | 5달러 | 0.2달러 | 20달러 | 지원 |
| Claude Sonnet 5.5 | 200k / 1M | 2달러 | 2.5달러 | 0.1달러 | 10달러 | 지원 |
| Claude Haiku 5.5 | 300k / 1M | 0.1달러 | 0.125달러 | 0.01달러 | 0.5달러 | 지원 |
| GPT-5.6 Sol | 272k / 1M | 4달러 | 5달러 | 0.4달러 | 20달러 | 지원 |
| GPT-5.6 Terra | 272k / 1M | 2달러 | 2.5달러 | 0.2달러 | 12달러 | 지원 |
| GPT-5.6 Luna | 272k / 1M | 0.2달러 | 0.25달러 | 0.02달러 | 1.2달러 | 지원 |
| Gemini 4 Neon | 200k / 1M | 3달러 | - | 0.15달러 | 15달러 | 지원 |
| Gemini 4 Carbon | 200k / 1M | 2달러 | - | 0.1달러 | 10달러 | 지원 |
| Gemini 4 Argon | 200k / 1M | 2달러 | - | 0.1달러 | 10달러 | 지원 |
| Gemini 4 Hydrogen | 200k / 1M | 1.5달러 | - | 0.075달러 | 7.5달러 | 지원 |
| Gemini 3.1 Pro | 200k / 1M | 2달러 | - | 0.2달러 | 12달러 | 미지원 |
| Gemini 3.8 Flash | 200k / 1M | 0.75달러 | - | 0.075달러 | 3.75달러 | 지원 |
| Muse Wonder | 300k / 1M | 4달러 | - | 0.2달러 | 20달러 | 미지원 |

Cursor의 Auto 기능은 Cursor Router를 통해 Cost, Balance, Intelligence 세 가지 모드로 나뉜다.[5][6] 개인 요금제는 기존 Auto 모드의 후속인 Cost 모드만 지원하며, 어떤 모델이 응답을 처리하든 Cursor 모델 요청으로 계산되어 주간 사용량 풀에서 차감된다.[5][6] Balance와 Intelligence 모드는 Teams 및 Enterprise 요금제를 대상으로 Agents Window, 에디터, CLI, Cursor SDK, iOS 앱에 제공되며 Enterprise 팀은 관리자가 옵트인하기 전까지 기본 비활성 상태이다. Cursor 모델로 라우팅된 요청은 주간 풀에서 차감되고, 서드파티 모델로 라우팅된 요청은 선불 크레딧에서 API 정가와 해당 시 Cursor Token Rate가 함께 과금된다.[5][6]

## Cursor 요금제, The X Subscription, 레거시 요금 체계

Cursor는 Grok, Cursor, X를 하나로 묶은 구독 상품인 The X Subscription의 일부로 제공되며, 공인 리셀러나 제3자 판매처 없이 X Subscription Corp.를 통해 직접 판매된다.[4][5][6] 표시된 모든 구독 가격에는 부가가치세(VAT) 등 적용 세금이 포함되어 있지 않다.[4][5] 2026-11-23 기준 The X Subscription의 Cursor 요금제는 다음과 같다.[4][5][6]

| 요금제 | 월간 가격 | 연간 가격 | 포함 주간 사용량 풀 | 서드파티 모델 |
| --- | --- | --- | --- | --- |
| Free | 0달러 | - | 제한적 | 미지원 |
| Plus | 8달러 | 80달러 | 기본 | 미지원 |
| Premium | 30달러 | 300달러 | Plus의 4배 | 선불 크레딧에서 API 정가 과금 |
| Super | 100달러 | 1,000달러 | Plus의 15배 | 선불 크레딧에서 API 정가 과금 |
| Ultra | 200달러 | 2,000달러 | Plus의 50배 | 선불 크레딧에서 API 정가 과금 |
| Teams | 좌석당 30달러, 100달러 또는 200달러 | - | 좌석 등급과 동일(Plus의 4배~50배) | API 정가 + 대상 모델에 Cursor Token Rate |
| Enterprise | 개별 산정 | 개별 산정 | Grok 및 Cursor 통합 풀 | API 정가 + 대상 모델에 Cursor Token Rate |

각 유료 요금제는 에디터의 Agent, CLI, Cloud Agents, Grok Bot, Grok 앱(Chat, Imagine, Voice, Bot) 전체에서 공유하고 매주 초기화되는 단일 Cursor 모델 사용량 풀을 포함한다. 유료 요금제에는 Grok API 접근 권한이 포함되지만 API 사용량은 표준 모델 요율로 별도 과금된다.[4][5] Plus는 Fast 모드 비활성, 중간 추론 강도(medium effort), Grok 4.7 256k 컨텍스트의 고정 설정으로 Cursor 모델만 제공하며 Auto, Cloud Agents, Automations, Bugbot, Origin, 서드파티 모델, 개인 API 키(BYOK)를 제외한다.[5] Super는 혼잡 시간대 우선 모델 접근을 추가하고 Ultra는 모든 신규 제품과 모델에 대한 최우선 접근을 추가한다.[4][5] 주간 풀을 소진해도 요청 품질이나 속도는 낮아지지 않으며, 사용자는 주간 초기화를 기다리거나 `grok.com/dashboard/billing`에서 선불 크레딧 충전(수동 또는 자동 충전과 월간 추가 사용 한도 설정)을 사용하거나 상위 등급으로 업그레이드할 수 있다.[5] 셀프서브 요금제는 주요 신용카드와 직불카드를 지원하며 갱신 최소 24시간 전까지 언제든 해지할 수 있고, 업그레이드는 즉시 적용되며 다운그레이드는 결제 주기 종료 시 적용된다.[4][6]

Teams 요금제는 한 팀 안에서 Premium, Super, Ultra 좌석 등급을 혼합해 배정할 수 있고(Plus는 팀용 미제공), 중앙 집중식 결제 및 관리, 사용량 분석, 팀 전체 Privacy Mode 강제 적용, 사용자 지정 Chat 데이터 보존 기간, 팀 마켓플레이스, SAML/OIDC SSO를 추가한다.[4][5] Enterprise는 통합 사용량 풀, 청구서 및 발주서(Invoice/PO) 결제와 계좌 이체, SCIM 좌석 관리, 세부 지출 제어, 그룹별 설정과 한도, 감사 로그, 서비스 계정, 고급 네트워크 및 MCP 제어, 우선 지원을 추가한다.[4][5] Teams 및 Enterprise 요금제에서는 대상 서드파티 모델 요청과 개인 API 키(BYOK) 사용 시 입력, 출력, 캐시 토큰 모두에 100만 토큰당 0.25달러의 Cursor Token Rate가 API 정가에 더해진다. 개인 요금제, Cursor 모델, Cost 모드 요청, 그리고 모든 가격 구간에서 캐시 읽기 가격이 100만 토큰당 0.10달러 미만인 서드파티 모델에는 이 요율이 면제된다.[5]

Cursor는 The X Subscription 출시 전에 판매한 레거시 요금제도 기존 가입자를 위해 유지한다.[5][6] 레거시 요금제는 신규 가입이 불가하며, 기존 가입자가 해지하거나 The X Subscription으로 영구 전환(기존 구독은 일할 환불 후 해지)하지 않는 한 유지된다. 결제는 `cursor.com/dashboard/billing`에서 Stripe로 관리되며, Cursor Models와 Other Models 두 개의 월간 사용량 풀을 제공하고 추가 요청에는 종량제(on-demand usage) 과금을 적용한다.[5][6] 과거 요청 기반 레거시 요금제에는 기본 한도를 넘는 컨텍스트 윈도를 모델 API 요율에 20%를 더해 과금하는 Max Mode도 있었다.[5]

| 레거시 Cursor 요금제 | 가격 | The X Subscription 대응 요금제 |
| --- | --- | --- |
| Hobby | 무료 | Free |
| Start(인도 전용) | 월 649루피(세금 포함) | Plus |
| Pro | 월 20달러 | Premium |
| Pro+ | 월 60달러 | Super |
| Ultra | 월 200달러 | Ultra |
| Teams Standard | 사용자당 월 40달러 | Teams(Premium 좌석) |
| Teams Premium | 사용자당 월 120달러 | Teams(Super 좌석) |

## Cursor 보안, 컴플라이언스, 개인정보 보호 제어

Cursor는 `cursor.com/security`(2026년 8월 25일 최종 갱신)에 보안 체계를, `cursor.com/privacy`(2026년 11월 6일 최종 갱신)에 개인정보 처리방침을 게시한다.[8][9] 2026-11-23 기준 Cursor는 AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 인증과 SOC 2 Type II 검증을 보유하고 있으며, 인증서와 감사 보고서, 침투 테스트 요약 보고서, 위탁 처리업체(subprocessor) 목록을 `trust.cursor.com`에서 요청에 따라 제공한다.[4][8][9] Cursor는 신뢰할 수 있는 제3자를 통해 최소 연 1회 침투 테스트를 수행한다고 밝힌다.[8]

Cursor는 모든 위탁 처리업체를 벤더 위험 관리 프로그램에 따라 평가하고 매년 재검토하며, 최소 권한 원칙, 다중 인증(Multi-Factor Authentication, MFA), 시스템 로그 모니터링으로 인프라 접근을 통제하고, 차단 목록(blocklist)에 오른 모델로는 요청을 보내지 않는다고 밝힌다.[8] Cursor는 중국 내에 인프라를 사용하거나 유지하지 않으며 중국에 본사를 둔 기업을 위탁 처리업체로 쓰지 않는다고 명시한다.[8] `security-reports@cursor.com`으로 접수된 보안 취약점 제보는 영업일 기준 5일 이내에 접수 확인을 회신하며, 중대한 보안 사고는 영향을 받는 사용자에게 이메일로 통지한다.[8] Cursor는 자사 코드베이스 보안에도 Bugbot과 Cloud Agent 자동화를 활용한다.[8]

Privacy Mode는 Free, 개인, Teams, Enterprise 요금제 전체에서 제공되며 사용자가 설정에서 켜거나 팀 및 엔터프라이즈 관리자가 조직 전체에 적용할 수 있고, 신규 팀원은 팀의 Privacy Mode 설정을 그대로 승계한다.[4][8] Privacy Mode를 켜면 Cursor와 모델 제공사 모두 사용자 코드 데이터를 모델 학습에 사용하지 않으며, 기술적 통제와 모델 제공사와의 계약상 요건이 적용되고 Voice Chat도 데이터 무보존으로 동작한다.[4][7][8] 개인정보 처리방침은 Anysphere, Inc.의 개인 이용자 계정에 적용되며, 고용주가 지급하는 등 Anysphere가 데이터 처리자(data processor)로 동작하는 상업용 계정은 고객 계약의 적용을 받는다.[9] Anysphere는 입력(Inputs)과 제안(Suggestions)이 보안 검토 대상으로 표시되거나 사용자가 피드백으로 직접 신고하거나 학습 사용에 명시적으로 동의한 경우를 제외하고 모델 학습에 쓰이지 않는다고 밝히며, 유전, 생체, 건강, 종교 정보 같은 민감 정보를 고의로 수집하지 않고 만 18세 미만 이용자를 대상으로 서비스를 제공하지 않는다고 명시한다.[9] 사용자는 설정 대시보드에서 언제든 계정을 삭제할 수 있다.[8]

조직 배포용 보안 제어 기능으로 Cursor는 SAML/OIDC SSO, SCIM 프로비저닝, 컴플라이언스 및 감사 로깅, 서비스 계정, 모바일 기기 관리(MDM) 배포, 데이터 암호화 및 고객 관리 암호화 키(Customer-Managed Encryption Keys, CMEK), 자동 실행·브라우저·네트워크 제어, 그리고 저장소·모델·MCP 서버·Grok Bot 접근 제어를 문서화하고 있다.[4][8]

## Cursor 기업 연혁, 투자 유치, SpaceX 인수 합의

Cursor는 2022년 설립되어 2024년 [OpenAI](https://mimirwiki.com/ko/wiki/openai) 스타트업 액셀러레이터 과정을 거친 Anysphere, Inc.가 개발했다.[1][9] Anysphere는 2024년 말 투자 전 기업가치(pre-money valuation) 25억 달러로 1억 달러를 조달했다.[2] 2025년 초에는 OpenAI를 비롯한 잠재 인수 후보들로부터 인수 제안을 받았으나 이를 거절했다.[2]

TechCrunch 보도에 따르면 Anysphere의 연간 반복 매출(Annualized Recurring Revenue, ARR)은 2025년 4월 중순 3억 달러에 도달했고, Bloomberg와 TechCrunch가 인용한 관계자에 따르면 2025년 6월 5일 기준 5억 달러를 넘어섰다.[2] 2025년 6월 5일 TechCrunch는 Anysphere가 기존 투자자인 Thrive Capital 주도 아래 Andreessen Horowitz, Accel, DST Global이 참여한 시리즈 C 라운드에서 기업가치 99억 달러로 9억 달러를 유치했으며 이는 1년 이내 세 번째 투자 유치였다고 보도했다.[1][2] 당시 Cursor는 2주 무료 체험 후 월 20달러 Pro 요금제와 월 40달러 비즈니스 구독을 제공했고 새로 엔터프라이즈 라이선스를 도입하고 있었다.[2] Anysphere는 2025년 말 23억 달러를 추가로 유치해 기업가치가 약 290억 달러에 이르렀다.[1]

2026년 초 xAI는 Cursor의 시니어 엔지니어링 리더 두 명을 영입했고, 2026년 4월 Business Insider는 xAI가 Cursor에 데이터 센터 용량을 임대하기로 했다고 보도했다.[1] SpaceX가 인수를 제안하기 전 Cursor는 Andreessen Horowitz, Thrive Capital, Nvidia 등이 참여하는 기업가치 500억 달러, 20억 달러 규모 투자 라운드 마무리를 앞두고 있었다.[1] 2026년 4월 SpaceX는 기업공개(IPO)를 앞두고 Cursor와 합의를 발표했는데, SpaceX가 주식 600억 달러로 Cursor를 인수하거나 거래가 무산될 경우 위약금 100억 달러를 지급하는 조건이었다.[1]

2026년 6월 16일 TechCrunch는 SpaceX가 앞서 xAI와 합병하고 주당 135달러에 IPO를 진행한 지 며칠 만에 주식 600억 달러 규모로 Cursor를 인수하기로 합의했으며 SpaceX가 2026년 3분기 거래 마무리를 예상했다고 보도했다.[1] 2026-11-23 기준 Cursor의 공개 웹사이트와 문서는 Cursor가 X Subscription Corp.가 판매하는 The X Subscription 안에서 [Grok](https://mimirwiki.com/ko/wiki/grok) 및 X와 함께 통합 제공되는 것으로 안내하며 SpaceXSI 구독 약관 링크와 모델 제공사 목록의 SpaceXSI를 기재하는 한편, 웹사이트 저작권 표시와 개인정보 처리방침에는 `Anysphere, Inc.`를 유지하고 있다.[4][5][8][9]

## 자주 묻는 질문

### Cursor 요금제는 얼마인가요?

2026-11-23 기준 Cursor는 The X Subscription을 통해 개인용 다섯 등급으로 제공됩니다. 세금 별도로 Free(월 0달러), Plus(월 8달러 또는 연 80달러), Premium(월 30달러 또는 연 300달러), Super(월 100달러 또는 연 1,000달러), Ultra(월 200달러 또는 연 2,000달러)입니다. Teams는 좌석당 월 30달러, 100달러 또는 200달러이며, Enterprise는 개별 산정입니다. Premium 이상 요금제의 서드파티 모델은 선불 크레딧에서 API 정가로 별도 과금됩니다. [4][5]

### Pro와 Pro+ 같은 기존 레거시 Cursor 요금제는 어떻게 되나요?

Hobby(무료), 인도 전용 Start(세금 포함 월 649루피), Pro(월 20달러), Pro+(월 60달러), Ultra(월 200달러), Teams Standard(사용자당 월 40달러), Teams Premium(사용자당 월 120달러) 같은 레거시 요금제는 신규 가입이 중단되었습니다. 기존 가입자는 해지하거나 The X Subscription으로 영구 전환하지 않는 한 기존 요금제와 월간 사용량 풀 두 개, 종량제 추가 과금을 그대로 유지할 수 있습니다. [5][6]

### Cursor는 어떤 AI 모델을 지원하나요?

2026-11-23 기준 유료 요금제는 Cursor 자체 모델인 Grok 4.7, Grok 4.6, Grok 4.5, Composer 2.5에 쓰이는 주간 공유 사용량 풀을 포함합니다. Premium 이상 요금제에서는 Anthropic의 Claude, OpenAI의 GPT-5.6, Google의 Gemini, Muse Wonder 같은 서드파티 모델도 선불 크레딧 기반 API 정가로 사용할 수 있습니다. [3][5]

### Cursor의 Privacy Mode와 보안 인증은 어떻게 되어 있나요?

2026-11-23 기준 Cursor는 AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 인증과 SOC 2 Type II 검증을 보유하고 있으며, 관련 증빙 자료는 trust.cursor.com에서 요청할 수 있습니다. Privacy Mode는 모든 요금제에서 사용할 수 있고 관리자가 팀 전체에 강제 적용할 수 있으며, 활성화 시 사용자 코드 데이터가 모델 학습에 쓰이지 않고 Voice Chat도 데이터 무보존(zero data retention)으로 동작합니다. [7][8][9]

### Cursor에는 어떤 사용자 지정 및 자동화 기능이 있나요?

Cursor 문서는 Plugins, Rules, Skills, Subagents, Hooks, 모델 컨텍스트 프로토콜(MCP) 서버 여섯 가지 사용자 지정 기능을 안내합니다. 이와 함께 명령줄 인터페이스(CLI), Cloud Agents, Automations, Origin 코드 호스팅, Bugbot 코드 리뷰, Live Apps, Voice Chat, 그리고 코드 폴더로 에이전트를 정의하고 배포하는 Agent SDK를 제공합니다. [3][4][7]

### Cursor의 소유 기업은 어디인가요?

Cursor는 2022년 설립된 Anysphere, Inc.가 개발했습니다. 2026년 6월 16일 TechCrunch는 SpaceX가 2026년 3분기 마무리를 예상하며 600억 달러 규모 주식 거래로 Cursor를 인수하기로 합의했다고 보도했습니다. 2026-11-23 기준 Cursor 구독은 X Subscription Corp.를 통해 The X Subscription의 일부로 판매되며, 웹사이트 저작권 표시와 개인정보 처리방침에는 Anysphere, Inc.가 계속 표기되어 있습니다. [1][4][9]

## 인용 문장

- Cursor는 2022년 설립되어 2024년 OpenAI 스타트업 액셀러레이터 과정을 거친 Anysphere가 개발했다. [1]
- 2025년 6월 5일 TechCrunch는 Anysphere가 기업가치 99억 달러에 9억 달러를 투자받고 연간 반복 매출(Annualized Recurring Revenue, ARR) 5억 달러를 넘었다고 보도했다. [2]
- 2026년 6월 16일 TechCrunch는 SpaceX가 2026년 3분기 마무리를 목표로 600억 달러 규모의 주식 거래를 통해 Cursor를 인수하기로 합의했다고 보도했다. [1]
- 2026-11-23 기준 Cursor는 X Subscription Corp.를 통해 The X Subscription의 일부로 직접 판매되며, 개인 월간 요금제는 세금 별도로 Free(0달러), Plus(8달러), Premium(30달러), Super(100달러), Ultra(200달러)이다. [4][5]
- 2026-11-23 기준 Cursor Teams 및 Enterprise 요금제는 대상 서드파티 모델 요청과 개인 API 키(BYOK) 사용에 100만 토큰당 0.25달러의 Cursor Token Rate를 추가로 부과하며, 개인 요금제에는 이 요율이 적용되지 않는다. [5]
- 월 20달러 Pro와 월 60달러 Pro+를 포함한 레거시 Cursor 요금제는 기존 가입자가 해지하거나 The X Subscription으로 영구 전환하지 않는 한 월간 사용량 풀 두 개를 유지한 채 계속 동작한다. [5][6]
- 2026-11-23 기준 Cursor는 AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 인증과 SOC 2 Type II 검증을 보유하며, 중국 내에 인프라를 두지 않는다고 밝힌다. [8]
- Cursor는 2026년 10월 13일 Origin App Marketplace, 10월 20일 Agent SDK, 11월 5일 Live Apps, 11월 6일 Grok Voice 기반 Voice Chat을 차례로 출시했다. [7]

## 연표

- 2022: Cursor의 개발사 Anysphere가 설립됐다. [1]
- 2024: Anysphere가 OpenAI 스타트업 액셀러레이터 과정을 거쳤고, 2024년 말 투자 전 기업가치 25억 달러로 1억 달러를 조달했다. [1][2]
- 2025-04: TechCrunch가 Anysphere의 연간 반복 매출이 3억 달러에 도달했다고 보도했다. [2]
- 2025-06-05: TechCrunch가 Anysphere가 Thrive Capital 주도로 기업가치 99억 달러에 9억 달러 규모 시리즈 C 투자를 유치하고 연간 반복 매출 5억 달러를 넘었다고 보도했다. [1][2]
- 2026-04: xAI가 Cursor에 데이터 센터 용량을 임대한다는 보도와 함께, SpaceX와 Cursor가 주식 600억 달러 인수 또는 위약금 100억 달러 조건의 합의를 발표했다. [1]
- 2026-06-16: TechCrunch가 SpaceX가 2026년 3분기 마무리를 예상하며 주식 600억 달러 규모로 Cursor를 인수하기로 합의했다고 보도했다. [1]
- 2026-08-25: Cursor가 AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 인증과 SOC 2 Type II 검증을 기재한 보안 문서를 갱신했다. [8]
- 2026-10-13: Cursor가 20개 이상의 파트너 연동 앱과 함께 Origin App Marketplace를 출시하고 공개 제출을 열었다. [7]
- 2026-10-16: Cursor가 클라우드 에이전트용 대화형 Canvases, Environments API 베타, 환경당 최대 300개 저장소 지원을 추가했다. [7]
- 2026-10-20: Cursor가 Agent SDK를 정식 출시했다. [7]
- 2026-11-05: Cursor가 유료 요금제에서 클라우드 에이전트로 바로 배포하는 Live Apps를 출시했다. [7]
- 2026-11-06: Cursor가 Grok Voice 기반 Voice Chat을 출시하고 개인정보 처리방침을 갱신했다. [7][9]

## 출처

1. SpaceX to acquire Cursor for $60B in stock, days after blockbuster IPO | TechCrunch. TechCrunch. 게시일 2026-06-16. https://techcrunch.com/2026/06/16/spacex-to-acquire-cursor-for-60b-in-stock-days-after-blockbuster-ipo/ (확인일 2026-11-23; tier 2: academic or news)
2. Cursor's Anysphere nabs $9.9B valuation, soars past $500M ARR | TechCrunch. TechCrunch. 게시일 2025-06-05. https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/ (확인일 2026-11-23; tier 2: academic or news)
3. Cursor Docs - Agent, Rules, MCP, Skills & CLI. Cursor. https://cursor.com/docs (확인일 2026-11-23; tier 3: official site)
4. Cursor · Pricing. Cursor. https://cursor.com/pricing (확인일 2026-11-23; tier 3: official site)
5. Models & Pricing | Cursor Docs. Cursor. https://cursor.com/docs/models-and-pricing (확인일 2026-11-23; tier 3: official site)
6. Pricing and plans | Cursor Docs. Cursor. https://cursor.com/help/account-and-billing/pricing (확인일 2026-11-23; tier 3: official site)
7. What's New in Cursor - Latest Updates & Release Notes. Cursor. https://cursor.com/changelog (확인일 2026-11-23; tier 3: official site)
8. Cursor · Security. Cursor. https://cursor.com/security (확인일 2026-11-23; tier 3: official site)
9. Cursor · Privacy Policy. Cursor. https://cursor.com/privacy (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "Cursor." 버전 35e1ceeb, 2026-11-23. https://mimirwiki.com/ko/wiki/cursor
