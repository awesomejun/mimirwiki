---
title: "Claude"
subtitle: "Anthropic, PBC가 개발한 AI 어시스턴트 및 대규모 언어 모델 제품군"
canonical_url: https://mimirwiki.com/ko/wiki/claude
language: ko
page_class: entity
revision_sha256: 9bc04e23822c9466438dcb73062fd1630c8e03c9c78c2bd5c51115227b1da4fb
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 14
alternates:
  md: https://mimirwiki.com/ko/wiki/claude.md
  txt: https://mimirwiki.com/ko/wiki/claude.txt
  json: https://mimirwiki.com/ko/wiki/claude.json
  jsonld: https://mimirwiki.com/ko/wiki/claude.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude
  ja: https://mimirwiki.com/ja/wiki/claude
  zh: https://mimirwiki.com/zh/wiki/claude
---

# Claude

> Claude는 Anthropic, PBC가 개발해 2023년 3월 14일 공개 출시한 AI 어시스턴트이자 대규모 언어 모델 제품군이다. 2026-11-23 기준 최신 모델은 Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5이며 각 모델은 100만 토큰 컨텍스트 윈도를 지원한다. 구독 요금제, API, Claude Code, 주요 클라우드 플랫폼을 통해 이용할 수 있다.

Claude는 미국 캘리포니아주 샌프란시스코에 본사를 둔 델라웨어주 공익법인(Public Benefit Corporation) Anthropic, PBC가 개발한 AI 어시스턴트이자 대규모 언어 모델(Large Language Model, LLM) 제품군이다. Anthropic은 2023년 3월 14일 채팅 인터페이스와 개발자 API를 통해 Claude를 공개 출시했으며, 이후 터미널과 통합 개발 환경(IDE)용 코딩 에이전트인 Claude Code, 데스크톱 업무용 Claude Cowork, Claude Platform API로 제품군을 확장했다. 2026-11-23 기준 최신 모델은 Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, Claude Haiku 5.5의 4종이며, 모두 100만 토큰 컨텍스트 윈도(context window)와 최대 12만 8,000 출력 토큰을 지원한다. Claude는 Free, Pro, Max, Ultra, Team, Enterprise, Education 요금제와 Anthropic 자체 API 외에도 Amazon Bedrock, Google Cloud, Microsoft Foundry에서 제공된다.

**다른 이름:** 클로드, Claude AI, Claude.ai, Claude Platform

## 핵심 정보

- **개발사:** Anthropic, PBC(미국 캘리포니아주 샌프란시스코) [1]
- **최초 공개 출시:** 2023-03-14 [3]
- **최신 모델:** Claude Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5 (기준 2026-11-23) [4]
- **컨텍스트 윈도:** 최신 모델 4종 모두 100만 토큰(최대 출력 128K 토큰) (기준 2026-11-23) [4]
- **개인 구독 요금제:** Free(0달러), Pro(연간 결제 시 월 17달러, 월간 결제 시 월 20달러), Max(월 100달러), Ultra(월 200달러) (기준 2026-11-23) [6]

## 기본 정보

- **개발사:** Anthropic, PBC(미국 델라웨어주 공익법인) [1]
- **최초 공개 출시:** 2023-03-14(Claude 및 Claude Instant) [3]
- **모델 계열:** Haiku, Sonnet, Opus, Fable, Mythos (기준 2026-11-23) [4]
- **최신 모델:** Claude Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5 (기준 2026-11-23) [4]
- **컨텍스트 윈도 및 최대 출력:** 입력 1,000,000토큰, 출력 최대 128,000토큰(최신 모델 기준) (기준 2026-11-23) [4]
- **지식 및 학습 데이터 기준 시점:** 2026년 6월(Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5) (기준 2026-11-23) [4]
- **API 기본 토큰 가격:** 100만 입력/출력 토큰당 0.10/0.50달러(Haiku 5.5)부터 8/40달러(Fable 5.2)까지 (기준 2026-11-23) [5]
- **플랫폼 및 클라이언트:** 웹, 데스크톱, iOS, Android, Claude Code, Claude Platform API (기준 2026-11-23) [6]
- **클라우드 제공처:** Amazon Bedrock, Claude Platform on AWS, Google Cloud, Microsoft Foundry (기준 2026-11-23) [4]
- **정렬 방식:** Constitutional AI(지도 자가 수정 및 RLAIF) [2]
- **연동 프로토콜:** 모델 컨텍스트 프로토콜(MCP, 2024-11-25 오픈소스 공개) [11]
- **지원 지역:** 목록 등재 185개 국가·지역 및 속령(2026-11-12 발효 정책) (기준 2026-11-23) [14]

## Claude 개요, 출시 연혁, 제품 구성

Claude는 미국 캘리포니아주 샌프란시스코 548 Market Street(PMB 90375, 우편번호 94104)에 본사를 둔 델라웨어주 공익법인 [Anthropic](https://mimirwiki.com/ko/wiki/anthropic), PBC가 개발한다.[1] 2026년 11월 17일 [SEC EDGAR](https://mimirwiki.com/ko/wiki/sec-edgar)에 제출된 Form S-1 수정안 제3호(S-1/A-3)에 따르면, Anthropic은 공동 창립자인 Dario Amodei(최고경영자)와 Daniela Amodei(사장)가 이끌고 있다.[1] Anthropic은 Notion, Quora(Poe 경유), DuckDuckGo(DuckAssist용)를 비롯해 Juni Learning, Robin AI, AssemblyAI 등 초기 파트너와 비공개 알파 테스트를 진행한 뒤 2023년 3월 14일 Claude를 공개 출시했다.[3]

2023년 3월 출시 당시 Claude는 채팅 인터페이스와 개발자 콘솔 API를 통해 Claude와 더 가볍고 비용이 낮은 Claude Instant의 두 가지 버전으로 제공되었다.[3] Anthropic은 초기 출시 버전이 요약, 검색, 협업 글쓰기, 질의응답, 코딩 등의 작업을 지원한다고 밝혔다.[3]

2026-11-23 기준 Anthropic의 제품 개요 페이지는 Claude 모델을 중심으로 웹, 데스크톱, iOS, Android용 Claude 채팅 앱, Claude Code, Claude Cowork, 대기자 명단을 받는 리서치 프리뷰 앱인 Claude Duet, Claude Platform, Claude Tag, 그리고 특화 제품인 Claude Security와 Claude Science를 함께 소개한다.[6][7] Claude 애플리케이션 전반에 명시된 기능으로는 Artifacts, Design, Docs, Slides, Data, Sheets 및 Whiteboards(베타), Connectors, Plugins, Skills, Extensions, 음성 모드(Voice mode), 웹 검색, Research, 작업 예약, Claude in Chrome, Claude for Google Workspace, Claude for Microsoft 365가 있다.[6][7] 2026년 9월 Anthropic은 사용자가 한 대화 안에서 일반 질의와 다단계 데스크톱 작업을 오갈 수 있도록 Claude Cowork와 Claude.ai를 단일 애플리케이션으로 통합하기 시작했다.[1]

## Claude 모델 구성과 사양

Claude 모델은 Models API(`GET /v1/models`)의 `line` 필드에 보고되는 `haiku`, `sonnet`, `opus`, `fable`, `mythos`의 다섯 계열로 구분된다.[4] 2026-11-23 기준 Claude Platform Docs에는 Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, Claude Haiku 5.5의 4종이 최신 모델로 등재되어 있다.[4] 이 4종은 모두 텍스트와 이미지 입력, 텍스트 출력을 처리하며 다국어 기능, 비전(vision), 도구 사용(tool use), 적응형 추론(adaptive thinking)을 지원한다.[4]

| 모델 | Claude API ID | 컨텍스트 윈도 | 최대 출력 | 추론 모드 및 기본 노력 수준 | 지식 기준 시점 | 최단 지원 종료 예정일 |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | `claude-fable-5-2` | 1M 토큰 | 128K 토큰 | 적응형(상시 활성), high | 2026년 6월 | 2027-11-09 |
| Claude Opus 5.5 | `claude-opus-5-5` | 1M 토큰 | 128K 토큰 | 적응형(상시 활성), medium | 2026년 6월 | 2027-09-22 |
| Claude Sonnet 5.5 | `claude-sonnet-5-5` | 1M 토큰 | 128K 토큰 | 적응형, high | 2026년 6월 | 2027-09-28 |
| Claude Haiku 5.5 | `claude-haiku-5-5` | 1M 토큰 | 128K 토큰 | 적응형, medium | 2026년 6월 | 2027-10-07 |

Claude Platform Docs는 Claude Fable 5.2를 고난도 추론과 장기 에이전트 작업용, Claude Opus 5.5를 일반 워크로드 및 장기 에이전트 코딩과 지식 업무용, Claude Sonnet 5.5를 속도와 성능의 균형용, Claude Haiku 5.5를 분류, 추출, 라우팅 같은 대량·저지연 작업용으로 구분한다.[4] 4종 모두 신뢰 가능한 지식 기준 시점(reliable knowledge cutoff)과 학습 데이터 기준 시점이 2026년 6월로 기재되어 있다.[4]

2026-11-23 기준 Claude Platform Docs는 최신 4종 외의 추가 및 이전 모델로 Claude Mythos 5.2, Claude Fable 5.1 및 5, Claude Mythos 5.1 및 5, Claude Opus 5, 4.8, 4.7, 4.6, 4.5, 4.1, 4, Claude Sonnet 5, 4.6, 4.5, 4, Claude Haiku 4.5도 함께 안내한다.[4] 이전 세대 가운데 Claude Opus 4.5, Claude Sonnet 4.5, Claude Sonnet 4, Claude Haiku 4.5는 20만 토큰 컨텍스트 윈도와 최대 6만 4,000 출력 토큰을 지원하며, Claude Opus 4.1과 Claude Opus 4는 20만 토큰 컨텍스트 윈도와 최대 3만 2,000 출력 토큰을 지원한다.[4]

개발자는 `GET /v1/models` 엔드포인트로 모델 사양을 프로그래밍 방식으로 조회할 수 있으며, 생명주기 단계(`active`, `deprecated`, `retired`)별 필터링과 함께 `max_input_tokens`, `max_tokens`, `line`, 그리고 `thinking.types.disabled`, `thinking.types.between_tools`, `server_tools`(웹 검색 및 코드 실행), 프로그래밍 방식 도구 호출 지원 여부를 담은 `capabilities` 객체를 받을 수 있다.[4] Anthropic의 Form S-1/A-3에는 그래픽 사용자 인터페이스를 관찰하고 클릭, 입력, 앱 탐색을 수행하는 컴퓨터 사용(computer use) 기능과 단일 응답 안의 연속된 도구 호출 사이에 개별 추론 단계를 배치하는 교차 추론(interleaved thinking) 기능도 정의되어 있다.[1]

## Claude Platform API 가격과 개발자 기능

Claude Platform의 Claude API 사용량은 미국 달러 기준 100만 토큰(MTok) 단위로 기본 입력, 기본 출력, 프롬프트 캐싱(prompt caching), 배치 처리(batch processing) 요율에 따라 과금된다.[5] 2026-11-23 기준 Claude Platform Docs에 게시된 최신 모델 4종의 API 요금은 다음과 같다.[5]

| 모델 | 기본 입력 | 기본 출력 | 캐시 쓰기(5분 / 1시간) | 캐시 읽기 | 배치 입력 / 출력 |
| --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 8달러 / MTok | 40달러 / MTok | 10달러 / 16달러 / MTok | 0.20달러 / MTok | 4달러 / 20달러 / MTok |
| Claude Opus 5.5 | 4달러 / MTok | 20달러 / MTok | 5달러 / 8달러 / MTok | 0.20달러 / MTok | 2달러 / 10달러 / MTok |
| Claude Sonnet 5.5 | 2달러 / MTok | 10달러 / MTok | 2.50달러 / 4달러 / MTok | 0.10달러 / MTok | 1달러 / 5달러 / MTok |
| Claude Haiku 5.5(10만 토큰 이하 프롬프트) | 0.10달러 / MTok | 0.50달러 / MTok | 0.125달러 / 0.20달러 / MTok | 0.01달러 / MTok | 0.05달러 / 0.25달러 / MTok |
| Claude Haiku 5.5(10만 토큰 초과 프롬프트) | 0.50달러 / MTok | 2.50달러 / MTok | 0.625달러 / 1달러 / MTok | 0.05달러 / MTok | 0.25달러 / 1.25달러 / MTok |

프롬프트 캐싱은 기본 입력 단가에 고정 배수를 적용하는데, 5분 캐시 쓰기는 1.25배, 1시간 캐시 쓰기는 2배이며, 캐시 읽기는 Fable 5.2, Mythos 5.2, Fable 5.1, Mythos 5.1에서 0.025배, Opus 5.5와 Sonnet 5.5에서 0.05배, 나머지 모델에서 0.1배이다.[5] Batch API는 비동기 요청의 입력과 출력 토큰에 50% 할인을 제공한다.[5] 고속 모드(Fast mode)는 지원 모델에서 초당 출력 토큰 속도를 최대 2.5배 높이는 대신 기본 요금의 2배를 부과하며(Fable 5.2 및 Mythos 5.2는 입력 16달러, 출력 80달러/MTok, Opus 5.5는 8달러, 40달러/MTok, Opus 5 및 Opus 4.8은 10달러, 50달러/MTok), Batch API와 함께 사용할 수 없다.[5]

Claude 4.6 이후 모델에서 `inference_geo: "us"` 매개변수로 미국 전용 추론을 지정하면 자체 API, Claude Platform on AWS, Anthropic 관리형 Google Cloud 배포, Microsoft Foundry의 Azure US Data Zone Standard 배포에서 모든 토큰 과금 항목에 1.1배 배수가 적용된다.[5] Anthropic 문서는 Claude 4.7 이후 모델과 Claude Mythos Preview가 새로운 토크나이저(tokenizer)를 사용하며, Claude Sonnet 4.6 이하 모델과 비교해 같은 텍스트에서 약 30% 더 많은 토큰을 생성한다고 안내한다.[5] 2026-11-23 기준 추가 모델의 100만 입력 및 출력 토큰당 기본 가격은 Claude Mythos 5.2가 8달러와 40달러, Fable 5.1, Fable 5, Mythos 5.1, Mythos 5가 10달러와 50달러, Opus 5부터 Opus 4.5까지가 5달러와 25달러, Opus 4.1과 Opus 4가 15달러와 75달러, Sonnet 5가 2달러와 10달러, Sonnet 4.6부터 Sonnet 4까지가 3달러와 15달러, Haiku 4.5가 1달러와 5달러이다.[5]

토큰 요금 외에 `claude.com/pricing`은 2026-11-23 기준 Claude Platform 기능 3종의 별도 요금도 제시한다. Managed Agents는 활성 실행 시간당 0.08달러(기본 토큰 요금 별도), 웹 검색(Web search)은 검색 1,000건당 10달러(토큰 비용 제외), 샌드박스 Python 코드 실행(Code execution)은 조직당 매일 50시간 무료 제공 후 컨테이너 시간당 0.05달러이다.[6]

2026-11-23 기준 Claude API는 조직 단위로 월간 지출 한도(spend limit)와 분당 요청 수(RPM), 분당 입력 토큰 수(ITPM), 분당 출력 토큰 수(OTPM) 속도 제한(rate limit)을 적용하며, 한도를 넘으면 HTTP 429 응답을 반환한다.[12] 표준 사용 등급별 월간 지출 상한은 Start 500달러, Build 1,000달러, Scale 200,000달러이며 신규 계정은 Evaluation 등급에서 시작할 수 있다. 기본 ITPM 한도는 캐시되지 않은 `input_tokens`와 `cache_creation_input_tokens`만 산입하고 `cache_read_input_tokens`는 제외하며, Managed Agents는 생성 엔드포인트 분당 300건, 조회 엔드포인트 분당 1,200건의 제한을 둔다.[12] 방화벽 허용 목록을 위해 Anthropic은 2026-11-23 기준 고정 인바운드 IP 대역으로 IPv4 `160.79.104.0/23`, `153.61.224.0/22`와 IPv6 `2607:6bc0::/48`을, MCP 도구 호출과 웹 검색·웹 가져오기 등에 쓰는 아웃바운드 IPv4 대역으로 `160.79.104.0/21`과 `153.61.208.0/20`을 게시한다.[13]

## Claude 개인, 팀, 엔터프라이즈, 교육 요금제

Claude는 `claude.com/pricing`에 공개된 단계별 구독 요금제를 통해 개인 사용자, 팀, 대기업, 대학 기관에 제공된다.[6] 2026-11-23 기준 가격 페이지에는 개인용 4단계(Free, Pro, Max, Ultra), Standard와 Premium 좌석을 둔 Team 요금제, 셀프서비스와 영업 지원 방식을 제공하는 Enterprise 요금제, 대학 전체를 대상으로 하는 Education 요금제가 올라와 있다.[6]

| 요금제 | 표시 가격(USD) | 결제 조건 | 명시된 제공량 및 주요 기능 |
| --- | --- | --- | --- |
| Free | 0달러 | 무료 | 5시간 및 주간 제한 사용량, Sonnet 및 Haiku 모델, 웹·데스크톱·iOS·Android 채팅, Artifacts, Design, Slides, Docs, 웹 검색, 코드 실행, 음성 모드, Projects 최대 5개 |
| Pro | 연간 결제 시 월 17달러(연 200달러 선결제) 또는 월간 20달러 | 월간 또는 연간 | 기준(1배) 5시간 및 주간 사용량, Opus 접근, 사용량 크레딧 기반 Fable, Claude Code, Claude Science, Claude Data, Sheets 및 Whiteboards(베타), Research, 작업 예약, Claude in Chrome, Microsoft 365 및 Outlook 추가 |
| Max | 월 100달러 | 월간 | Pro 대비 5배의 5시간 및 주간 사용량, 주간 한도의 최대 50%까지 Fable 포함, 월 100달러 API 크레딧, 신규 기능 조기 접근, 혼잡 시간대 우선 접근 |
| Ultra | 월 200달러 | 월간 | 인증 계정 대상 5시간 한도 없음, Pro 대비 10배 주간 사용량, 주간 한도의 최대 50%까지 Fable 포함, 월 200달러 API 크레딧, 신규 기능 조기 접근, 혼잡 시간대 우선 접근 |
| Team | Standard: 연간 결제 시 좌석당 월 20달러(월간 25달러), Premium: 연간 결제 시 좌석당 월 100달러(월간 125달러) | 월간 또는 연간(2명~150명) | 좌석 유형 혼합 가능, Premium은 Standard 대비 5배 사용량과 주간 한도 최대 50% Fable 제공, Claude Cowork, Claude Tag, 엔터프라이즈 검색, 프로젝트 공유, SSO, 도메인 인증, 중앙 결제, 사용 분석, 월 최대 500달러 공동 API 크레딧 |
| Enterprise | 좌석당 월 20달러 기본료 + API 요율 기준 사용량 | 연간(최소 20좌석) | 조직 및 사용자 지출 한도, 역할 기반 접근 제어, SCIM, 감사 로그, Compliance API, 사용자 지정 데이터 보존 제어, 도메인 캡처, 네트워크 수준 접근 제어, IP 허용 목록, HIPAA 대응 옵션, 추론 훅(inference hooks), Claude Security(베타) 추가 |

개인 요금제(Free, Pro, Max, Ultra)에서는 모델 학습이 수신 거부(opt-out) 방식이며, Team과 Enterprise 요금제에서는 고객 콘텐츠가 기본적으로 모델 학습에 사용되지 않는다.[6] 모든 요금제는 모델에 따라 최대 100만 토큰 컨텍스트 윈도를 지원한다고 기재하며, 사용 한도 도달 속도는 선택한 모델, 대화 길이, 파일 크기에 따라 달라진다.[6]

영업 지원(sales-assisted) Enterprise 계약에는 셀프서비스 Enterprise에 없는 AWS Marketplace 구매, 컨설팅, 약정 지출 구간별 할인, 평가판(trials), 일정 지출 기준 이상에서의 고객 성공 지원, 청구서 발행 및 후불 결제 조건(net terms)이 포함된다.[6] Anthropic은 대학의 학생, 교수진, 교직원을 대상으로 할인 요율, 학술 연구 및 학습 모드, 전용 API 크레딧을 제공하는 Education 요금제도 운영하지만 공개 가격은 기재하지 않는다.[6]

2026년 11월 12일 발효된 Anthropic의 지원 지역 정책(Supported Regions Policy)에 따라 Claude.ai, Claude Code, Cowork를 포함한 애플리케이션과 Claude API, 클라우드 플랫폼 및 공인 리셀러를 통한 Claude 모델은 목록에 등재된 185개 국가·지역과 그 속령에서만 이용할 수 있다.[14] 목록에 없는 지역에 물리적으로 체류 중인 개인은 물론, 미지원 지역에 설립되거나 본사를 두었거나 지분 과반을 보유·지배받는 법인의 이용도 제한된다.[14]

## Claude Code, Claude Cowork 및 클라우드 플랫폼 제공 현황

Claude Code는 2025년 2월 리서치 프리뷰로 처음 공개된 Anthropic의 에이전트형 소프트웨어 개발 도구이다.[1][8] Anthropic의 Form S-1/A-3과 공식 GitHub 저장소(`anthropics/claude-code`)에 따르면 Claude Code는 터미널, IDE, 또는 GitHub의 `@claude` 멘션을 통해 동작하며, 로컬 머신이나 샌드박스 클라우드 실행 환경에서 상태를 유지하면서 자연어 명령으로 코드베이스 분석, 계획, 작성, 테스트, 디버깅, Git 워크플로 처리를 수행한다.[1][8] Form S-1/A-3은 NASA 엔지니어들이 화성 탐사 로버 Perseverance의 주행 명령을 계획하고 작성하는 데 Claude Code를 활용했다고 기재한다.[1]

2026-11-23 기준 공개 GitHub 저장소 `anthropics/claude-code`는 스타 15만 6,800개(156.8k), 포크 2만 5,100개(25.1k), 커밋 1,110건을 기록했다.[8] 2026-11-23 기준 저장소 README에 안내된 설치 방법은 macOS 및 Linux의 셸 스크립트(`curl -fsSL https://claude.ai/install.sh | bash`)와 Homebrew 캐스크(`brew install --cask claude-code`), Windows의 PowerShell 스크립트(`irm https://claude.ai/install.ps1 | iex`)와 WinGet(`winget install Anthropic.ClaudeCode`)이며, npm 패키지(`@anthropic-ai/claude-code`)를 통한 설치는 지원 중단 예정(deprecated)으로 표시되어 있다.[8] Anthropic은 같은 에이전트 아키텍처를 일반 데스크톱 지식 업무로 확장해 2026년 1월 파일 읽기, 애플리케이션 조작, 다단계 워크플로 실행을 수행하는 Claude Cowork를 리서치 프리뷰로 공개했고, 2026년 9월부터 Claude.ai와 통합하기 시작했다.[1]

Claude 모델은 Anthropic 자체 API 외에도 주요 클라우드 플랫폼에서 제공된다.[4][5] Amazon Web Services에서는 Amazon Bedrock(Claude Fable 5.2, Opus 5.5, Sonnet 5.5, Haiku 5.5 등 최신 모델을 제공하며 최대 8시간 자율 실행 에이전트를 지원하는 Amazon Bedrock AgentCore와 연동)과 Claude Platform on AWS를 통해 이용할 수 있다.[4][5][9] Google Cloud에서는 Gemini Enterprise Agent Platform의 Model Garden을 통해 Google 관리형 및 Anthropic 관리형 배포로 제공되며, 2026-11-23 기준 Fable 5~5.2, Opus 4.5~5.5, Sonnet 4.5~5.5, Haiku 4.5 및 5.5 모델을 지원한다.[4][5][10] Azure에서는 Microsoft Foundry를 통해 제공된다.[4][5]

2026-11-23 기준 클라우드 과금 방식은 제공 경로에 따라 다르다.[5] 파트너가 운영하는 플랫폼(Amazon Bedrock 및 Google 관리형 Google Cloud)에서는 클라우드 사업자가 직접 청구하며, Claude 4.5 이후 모델의 리전 또는 멀티리전 엔드포인트에는 글로벌 엔드포인트 대비 10%의 추가 요율이 적용된다.[5] Anthropic이 마켓플레이스를 통해 운영하는 플랫폼(AWS Marketplace 기반 Claude Platform on AWS 및 Azure Marketplace 기반 Microsoft Foundry의 Claude)에서는 Anthropic이 표준 단가로 토큰 사용량을 달러로 산정한 뒤 1 CCU당 0.01달러 비율로 Claude Consumption Units(CCU)로 환산해 매시간 보고하고 월말 후불 청구한다.[5]

## Claude의 Constitutional AI 학습 방식과 모델 컨텍스트 프로토콜 지원

Claude 모델은 2022년 12월 15일 Anthropic의 Yuntao Bai 외 50명의 공동 저자가 arXiv에 발표한 논문 "Constitutional AI: Harmlessness from AI Feedback"에서 제시한 Constitutional AI 방식으로 정렬(alignment)된다.[2][9] 이 방식은 명문화된 규칙이나 원칙 목록을 통해 인간 감독을 제공하며 두 단계로 학습을 진행한다.[2] 지도 학습(supervised learning) 단계에서는 초기 모델이 응답을 생성한 뒤 명문화된 원칙에 따라 스스로 비평하고 수정하며, 원본 모델을 이 수정 데이터셋으로 미세 조정(fine-tuning)한다.[2] 이어지는 강화학습 단계인 AI 피드백 기반 강화학습(Reinforcement Learning from AI Feedback, RLAIF)에서는 AI 모델이 두 개의 샘플 응답 중 원칙에 더 부합하는 쪽을 평가해 선호도 데이터셋을 만들고, 이를 바탕으로 학습한 선호도 모델(preference model)을 강화학습의 보상 신호로 사용한다.[2] 두 단계 모두 연쇄 사고(chain-of-thought) 추론을 활용할 수 있으며, 유해한 요청을 거부할 때 그 이유를 설명하도록 학습한다.[2]

2026년 11월 17일 제출된 Anthropic의 Form S-1/A-3은 Constitutional AI를 Claude의 헌법(Claude's constitution)이라 부르는 명문화된 원칙에 따라 모델을 학습시키는 방법으로 정의하며, 이 원칙이 광범위한 안전성(broadly safe), 광범위한 윤리성(broadly ethical), Anthropic 지침 준수, 실질적 유용성(genuinely helpful)의 네 가지 우선순위로 구성된다고 밝힌다.[1] 이 과정을 통해 모델은 감사 가능한 명문화된 원칙에 비추어 자신의 응답을 평가하고 비평하며 수정한다.[1]

Claude는 Anthropic의 David Soria Parra와 Justin Spahr-Summers가 설계해 2024년 11월 25일 오픈소스로 공개한 [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(Model Context Protocol, MCP)을 통해 외부 도구 및 데이터 시스템과 연동된다.[11] MCP는 데이터 소스가 MCP 서버로 기능을 노출하고 AI 애플리케이션이 MCP 클라이언트로 접속해 양방향 연결을 유지하는 개방형 클라이언트-서버 표준이다.[11] 공개 당시 Anthropic은 MCP 사양과 SDK, 모든 Claude.ai 요금제용 Claude Desktop 앱의 로컬 MCP 서버 지원, 그리고 Google Drive, Slack, GitHub, Git, Postgres, Puppeteer용 오픈소스 사전 구축 MCP 서버를 함께 발표했다.[11] Anthropic 발표문은 MCP 초기 도입 사례로 Block과 Apollo를, 프로토콜 연동 작업을 진행한 개발 도구 기업으로 Zed, Replit, Codeium, Sourcegraph를 들었다.[11]

## 자주 묻는 질문

### 2026-11-23 기준 최신 Claude 모델은 무엇인가요?

2026-11-23 기준 Claude Platform Docs에는 Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, Claude Haiku 5.5의 4종이 최신 모델로 올라와 있습니다. 4종 모두 100만 토큰 컨텍스트 윈도, 최대 12만 8,000 출력 토큰, 적응형 추론(adaptive thinking), 비전, 도구 사용, 2026년 6월 지식 기준 시점을 지원합니다. [4]

### Claude 구독 요금제 가격은 얼마인가요?

2026-11-23 기준 개인 요금제는 Free(0달러), Pro(연간 결제 시 월 17달러, 연 200달러 선결제, 월간 결제 시 월 20달러), Max(월 100달러), Ultra(월 200달러)의 4단계로 구성되어 있습니다. 2명에서 150명 규모의 Team 요금제는 Standard 좌석이 연간 결제 기준 월 20달러(월간 25달러), Premium 좌석이 연간 결제 기준 월 100달러(월간 125달러)이며, Enterprise 요금제는 최소 20좌석 기준 연간 결제 좌석당 월 20달러에 API 요율 기준 사용량이 별도 부과됩니다. [6]

### Claude API 토큰 가격은 어떻게 되나요?

2026-11-23 기준 100만 입력 및 출력 토큰당 기본 API 가격은 Claude Fable 5.2가 8달러와 40달러, Claude Opus 5.5가 4달러와 20달러, Claude Sonnet 5.5가 2달러와 10달러입니다. Claude Haiku 5.5는 10만 토큰 이하 프롬프트에 입력 0.10달러와 출력 0.50달러, 10만 토큰 초과 프롬프트에 입력 0.50달러와 출력 2.50달러가 적용됩니다. 비동기 Batch API를 사용하면 입력과 출력 토큰 요금이 50% 할인됩니다. [5]

### Claude Code란 무엇이며 어떤 요금제에 포함되나요?

Claude Code는 2025년 2월 리서치 프리뷰로 공개된 Anthropic의 에이전트형 코딩 도구로, 터미널이나 IDE, GitHub의 @claude 멘션을 통해 코드 계획, 작성, 테스트, 디버깅과 Git 워크플로를 수행합니다. 2026-11-23 기준 Claude Code는 Pro, Max, Ultra, Team, Enterprise 요금제에 포함되어 있으며 Free 요금제에는 포함되지 않습니다. [1][6][8]

### 어떤 클라우드 플랫폼에서 Claude 모델을 사용할 수 있나요?

2026-11-23 기준 Claude 모델은 AWS의 Amazon Bedrock과 Claude Platform on AWS, Google Cloud의 Gemini Enterprise Agent Platform 내 Model Garden(Google 관리형 및 Anthropic 관리형), 그리고 Azure의 Microsoft Foundry에서 제공됩니다. 파트너 운영 플랫폼인 Amazon Bedrock과 Google 관리형 Google Cloud에서 Claude 4.5 이후 모델의 리전 또는 멀티리전 엔드포인트를 사용하면 글로벌 엔드포인트 대비 10%의 추가 요율이 적용됩니다. [4][5][9][10]

### Constitutional AI와 모델 컨텍스트 프로토콜(MCP)은 Claude와 어떤 관계가 있나요?

Constitutional AI는 Anthropic 연구진이 2022년 12월 발표한 학습 방식으로, 지도 학습과 AI 피드백 기반 강화학습(RLAIF)을 통해 Claude 모델이 명문화된 원칙에 따라 자신의 응답을 평가하고 수정하도록 학습합니다. 2024년 11월 25일 Anthropic이 오픈소스로 공개한 모델 컨텍스트 프로토콜(MCP)은 Claude Desktop을 포함한 Claude 애플리케이션을 외부 데이터 소스와 도구에 연결하는 개방형 클라이언트-서버 표준입니다. [1][2][11]

## 인용 문장

- Anthropic, PBC는 2023년 3월 14일 채팅 인터페이스와 개발자 API를 통해 Claude와 Claude Instant를 공개 출시했다. [3]
- 2026-11-23 기준 최신 Claude 모델은 Claude Fable 5.2, Claude Opus 5.5, Claude Sonnet 5.5, Claude Haiku 5.5의 4종이며 각 모델은 100만 토큰 컨텍스트 윈도와 최대 12만 8,000 출력 토큰을 지원한다. [4]
- 2026-11-23 기준 Claude 기본 API 요금은 100만 입력 및 출력 토큰당 Fable 5.2가 8달러와 40달러, Opus 5.5가 4달러와 20달러, Sonnet 5.5가 2달러와 10달러이며, Haiku 5.5는 10만 토큰 이하 프롬프트에 0.10달러와 0.50달러가 적용된다. [5]
- 2026-11-23 기준 Claude 개인 구독 요금제는 Free가 0달러, Pro가 연간 결제 시 월 17달러(월간 20달러), Max가 월 100달러, Ultra가 월 200달러이다. [6]
- Anthropic은 2025년 2월 Claude Code를, 2026년 1월 Claude Cowork를 각각 리서치 프리뷰로 공개했다. [1]
- 2026-11-23 기준 Claude 모델은 Amazon Bedrock, Claude Platform on AWS, Google Cloud, Microsoft Foundry에서 제공된다. [4][5][9][10]
- Anthropic 연구진은 2022년 12월 15일 지도 자가 수정과 AI 피드백 기반 강화학습(RLAIF)을 다룬 Constitutional AI 논문을 arXiv에 제출했다. [2]
- Anthropic은 2024년 11월 25일 모델 컨텍스트 프로토콜(MCP) 사양, SDK, Claude Desktop용 로컬 서버 지원을 오픈소스로 공개했다. [11]

## 연표

- 2022-12-15: Anthropic의 Yuntao Bai 외 50명의 공동 저자가 "Constitutional AI: Harmlessness from AI Feedback" 논문을 arXiv에 제출했다. [2]
- 2023-03-14: Anthropic이 초기 파트너와의 비공개 알파 테스트를 거쳐 채팅 인터페이스와 개발자 API로 Claude 및 Claude Instant를 공개 출시했다. [3]
- 2024-11-25: Anthropic이 모델 컨텍스트 프로토콜(MCP)의 사양, SDK, 사전 구축 서버, Claude Desktop 로컬 지원을 오픈소스로 공개했다. [11]
- 2025-02: Anthropic이 코딩 에이전트 Claude Code를 리서치 프리뷰로 공개했다. [1]
- 2026-01: Anthropic이 다단계 데스크톱 업무용 Claude Cowork를 리서치 프리뷰로 공개했다. [1]
- 2026-09: Anthropic이 Claude Cowork와 Claude.ai를 단일 애플리케이션으로 통합하기 시작했다. [1]
- 2026-11-17: Anthropic, PBC가 미국 증권거래위원회(SEC)에 Form S-1 증권신고서 수정안 제3호(S-1/A-3)를 제출했다. [1]

## 출처

1. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 게시일 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (확인일 2026-11-23; tier 1: government or public registry)
2. [2212.08073] Constitutional AI: Harmlessness from AI Feedback. arXiv (Bai et al., Anthropic). 게시일 2022-12-15. https://arxiv.org/abs/2212.08073 (확인일 2026-11-23; tier 2: academic or news)
3. Introducing Claude \ Anthropic. Anthropic. 게시일 2023-03-14. https://www.anthropic.com/news/introducing-claude (확인일 2026-11-23; tier 3: official site)
4. Models overview - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/models/overview (확인일 2026-11-23; tier 3: official site)
5. Pricing - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/about-claude/pricing (확인일 2026-11-23; tier 3: official site)
6. Plans & pricing | Claude by Anthropic. Anthropic. https://claude.com/pricing (확인일 2026-11-23; tier 3: official site)
7. Claude | The AI assistant for work. Anthropic. https://claude.com/product/overview (확인일 2026-11-23; tier 3: official site)
8. GitHub - anthropics/claude-code: Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands. · GitHub. Anthropic (GitHub). https://github.com/anthropics/claude-code (확인일 2026-11-23; tier 3: official site)
9. Claude by Anthropic - Models in Amazon Bedrock - AWS. Amazon Web Services. https://aws.amazon.com/bedrock/anthropic/ (확인일 2026-11-23; tier 3: official site)
10. Anthropic's Claude on Google Cloud models | Gemini Enterprise Agent Platform | Google Cloud Documentation. Google Cloud. https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/partner-models/claude (확인일 2026-11-23; tier 3: official site)
11. Introducing the Model Context Protocol \ Anthropic. Anthropic. 게시일 2024-11-25. https://www.anthropic.com/news/model-context-protocol (확인일 2026-11-23; tier 3: official site)
12. Rate limits - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/rate-limits (확인일 2026-11-23; tier 3: official site)
13. IP addresses - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/ip-addresses (확인일 2026-11-23; tier 3: official site)
14. Supported Regions Policy \ Anthropic. Anthropic. 게시일 2026-11-12. https://www.anthropic.com/supported-countries (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "Claude." 버전 9bc04e23, 2026-11-23. https://mimirwiki.com/ko/wiki/claude
