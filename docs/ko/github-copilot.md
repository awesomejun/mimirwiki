---
title: "GitHub Copilot"
subtitle: "GitHub이 개발해 코드 편집기, 터미널, 데스크톱 앱, 저장소 환경에서 제공하는 AI 코딩 어시스턴트 및 에이전트 플랫폼"
canonical_url: https://mimirwiki.com/ko/wiki/github-copilot
language: ko
page_class: entity
revision_sha256: 915782d798d76e36829ce498b23a6eb12e965145793332ea97ef466ce8453c33
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ko/wiki/github-copilot.md
  txt: https://mimirwiki.com/ko/wiki/github-copilot.txt
  json: https://mimirwiki.com/ko/wiki/github-copilot.json
  jsonld: https://mimirwiki.com/ko/wiki/github-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/github-copilot
  ja: https://mimirwiki.com/ja/wiki/github-copilot
  zh: https://mimirwiki.com/zh/wiki/github-copilot
---

# GitHub Copilot

> GitHub Copilot은 GitHub이 개발한 AI 코딩 어시스턴트 및 에이전트 플랫폼으로, GitHub의 클라우드 서비스는 Microsoft Corporation의 Intelligent Cloud 부문으로 보고된다. 2021년 6월 29일 기술 미리보기로 공개되었고 2022년 6월 21일 일반 공개되었으며, IDE, 터미널, 데스크톱 앱, github.com에서 동작한다. 2026-11-23 기준으로 다중 제공사 AI 모델과 GitHub AI Credits 과금 체계를 제공한다.

GitHub Copilot은 GitHub이 개발한 인공지능(AI) 코딩 어시스턴트 및 에이전트 플랫폼으로, GitHub의 클라우드 및 온프레미스 제품은 Microsoft Corporation의 Intelligent Cloud 사업 부문으로 보고된다. GitHub은 2021년 6월 29일 OpenAI Codex 기반의 제한적 기술 미리보기(technical preview)로 GitHub Copilot을 공개했고, 2022년 6월 21일 개인 개발자 대상 일반 공개(General Availability, GA)를 시작했으며, 2024년 12월 18일 GitHub Copilot Free 등급을 출시했다. 2026-11-23 기준으로 GitHub Copilot은 코드 편집기, 명령줄 인터페이스(Command-Line Interface, CLI), 데스크톱 앱, github.com, GitHub Mobile, Slack, Microsoft Teams에서 동작하며 OpenAI, Anthropic, Google, Microsoft, xAI, Kimi의 AI 모델과 자체 API 키 연동(Bring Your Own Key, BYOK), 로컬 모델 실행 환경을 지원한다. 2026-11-23 기준으로 GitHub은 개인용 요금제(Free, Student, 월 10달러 Pro, 월 39달러 Pro+, 월 100달러 Max)와 조직 및 기업용 요금제(시트당 월 19달러 Business, 시트당 월 39달러 Enterprise, Copilot access)를 제공하며, 종량제 기능은 1크레딧당 0.01달러인 GitHub AI Credits로 과금한다.

**다른 이름:** Copilot, 깃허브 코파일럿, GitHub Copilot Pro, GitHub Copilot Business, GitHub Copilot Enterprise

## 핵심 정보

- **기술 미리보기 출시:** 2021-06-29 [7]
- **일반 공개:** 2022-06-21 [8]
- **개인용 유료 요금제:** Pro(월 10달러), Pro+(월 39달러), Max(월 100달러) (기준 2026-11-23) [2]
- **조직 및 기업용 요금제:** Business(시트당 월 19달러), Enterprise(시트당 월 39달러), Copilot access(GHEC 0달러 또는 Standalone 사용자당 월 10달러) (기준 2026-11-23) [2]
- **크레딧 과금 단위:** GitHub AI Credit 1단위 = 0.01달러 (기준 2026-11-23) [6]

## 기본 정보

- **개발사:** GitHub [7]
- **모기업 보고 부문:** Microsoft Corporation, Intelligent Cloud 부문 (기준 2026-06-30) [1]
- **기술 미리보기 출시:** 2021-06-29 [7]
- **일반 공개:** 2022-06-21 [8]
- **무료 요금제 출시:** 2024-12-18 [9]
- **개인용 요금제:** Free(0달러), Student(인증 학생 0달러), Pro(월 10달러), Pro+(월 39달러), Max(월 100달러) (기준 2026-11-23) [2]
- **조직 및 기업용 요금제:** Business(시트당 월 19달러), Enterprise(시트당 월 39달러), Copilot access(GHEC 라이선스 0달러 또는 Standalone 사용자당 월 10달러) (기준 2026-11-23) [2]
- **종량제 과금 단위:** GitHub AI Credits(1크레딧 = 0.01달러) (기준 2026-11-23) [6]
- **지원 환경:** VS Code, Visual Studio, JetBrains IDE, Xcode, Vim, Neovim, Zed, Eclipse, Raycast, SQL Server Management Studio, CLI, 데스크톱 앱, github.com, GitHub Mobile, Slack, Teams (기준 2026-11-23) [5]
- **지원 AI 모델 제공사:** OpenAI, Anthropic, Google, Microsoft, xAI, Kimi (기준 2026-11-23) [5]

## GitHub Copilot 출시 연혁과 Microsoft 공시 맥락

GitHub Copilot은 2021년 6월 29일 GitHub이 [OpenAI](https://mimirwiki.com/ko/wiki/openai)와 협력해 [OpenAI Codex](https://mimirwiki.com/ko/wiki/openai-codex)를 기반으로 제한적 기술 미리보기로 출시했다.[7] 출시 당시 GitHub은 Copilot을 작업 중인 코드 문맥을 읽어 한 줄 전체나 함수 전체를 제안하는 AI 페어 프로그래머(AI pair programmer)로 소개했으며, 공개 소스 코드 비중이 높은 데이터셋으로 학습되어 여러 언어에서 동작하고 특히 Python, JavaScript, TypeScript, Ruby, Go에서 잘 작동한다고 설명했다.[7]

2022년 6월 21일 GitHub은 편집기 확장 프로그램 형태의 GitHub Copilot을 모든 개인 개발자에게 일반 공개(General Availability, GA)했으며, 요금을 월 10달러 또는 연 100달러로 책정하고 무료 체험과 함께 인증된 학생 및 주요 오픈소스 프로젝트 관리자(maintainer) 대상 무료 이용을 제공했다.[8] 2024년 12월 18일에는 2021년부터 2025년까지 GitHub 최고경영자(CEO)를 지낸 Thomas Dohmke가 GitHub 개발자 수 1억 5,000만 명 돌파와 함께 Visual Studio Code 및 GitHub 대시보드에 통합된 GitHub Copilot Free 출시를 발표했다.[9] 출시 당시 Copilot Free는 월 2,000회의 코드 자동 완성과 50회의 채팅 메시지를 제공하고 [Anthropic](https://mimirwiki.com/ko/wiki/anthropic)의 [Claude](https://mimirwiki.com/ko/wiki/claude) 3.5 Sonnet과 OpenAI의 GPT-4o 선택, 다중 파일 편집, 서드파티 에이전트를 지원했으며, 학생과 교육자 및 오픈소스 관리자의 무제한 Copilot Pro 무료 이용 조건은 그대로 유지되었다.[9]

[SEC EDGAR](https://mimirwiki.com/ko/wiki/sec-edgar)에 제출된 Microsoft Corporation(CIK 0000789019)의 2026년 6월 30일 종료 회계연도 Form 10-K는 GitHub이 클라우드 및 온프레미스 제품을 함께 제공하며 개발자가 코드를 관리하고 소프트웨어 개발 수명 주기 전반에 AI 및 에이전트 기반 도구를 통합하는 협업 플랫폼이라고 기술한다.[1] Microsoft는 GitHub 클라우드 서비스를 Intelligent Cloud 부문의 서버 제품 및 클라우드 서비스 항목에 포함하고, Azure 및 기타 클라우드 서비스 매출 성장 지표에 합산해 보고하며 해당 발췌 공시에서 GitHub Copilot의 단독 매출은 따로 구분하지 않는다.[1] 2026년 6월 30일 종료 회계연도 Form 10-K에 기재된 Microsoft의 연결 재무 실적은 다음과 같다.[1]

| Microsoft Corporation 연결 지표 | 2026 회계연도 | 2025 회계연도 | 증감률 |
| --- | --- | --- | --- |
| 매출 | 3,318억 3,900만 달러 | 2,817억 2,400만 달러 | 18% |
| 매출총이익 | 2,254억 6,500만 달러 | 1,938억 9,300만 달러 | 16% |
| 영업이익 | 1,552억 3,700만 달러 | 1,285억 2,800만 달러 | 21% |
| 순이익 | 1,337억 4,900만 달러 | 1,018억 3,200만 달러 | 31% |
| 희석 주당순이익(EPS) | 17.95달러 | 발췌본 미기재 | 발췌본 미기재 |

## GitHub Copilot 요금제와 가격

GitHub Copilot은 2026-11-23 기준으로 개인용 요금제 5종과 조직 및 기업용 요금제 3종으로 제공된다.[2][5] GitHub 문서는 모든 요금제에 Copilot CLI와 Copilot 앱이 포함되며, GitHub Enterprise Server에서는 현재 Copilot을 지원하지 않는다고 밝힌다.[2] 조직 및 기업용 요금제는 GitHub Free나 GitHub Team 조직, 그리고 GitHub Enterprise Cloud를 쓰는 조직 및 기업이 이용할 수 있으며 Copilot Enterprise는 GitHub Enterprise Cloud 환경 전용이다.[2][3]

아래 표는 2026-11-23 기준 GitHub 문서와 GitHub Copilot 요금제 페이지에 게시된 가격, 월간 크레딧 제공량, 모델 등급을 정리한 것이다.[2][3][5]

| 요금제 | 대상 | 게시 가격 | 월간 GitHub AI Credits 제공량 | 모델 접근 및 주요 구분 |
| --- | --- | --- | --- | --- |
| Copilot Free | 개인 | 0달러 | 제한된 크레딧(월 2,000회 인라인 자동 완성) | 자동 모델 선택 전용(문서 기준), Fusion Standard, 커뮤니티 지원 |
| Copilot Student | 개인(인증 학생) | 0달러 | 제한된 크레딧 | 자동 모델 선택 전용(문서 기준), 서드파티 에이전트 제외 |
| Copilot Pro | 개인 | 월 10달러(일부 사용자 무료) | 기본 1,000크레딧(기본 10달러 + 유연 할당 5달러, 총 15달러) | 무제한 자동 완성 및 다음 편집 제안, 모델 선택, 클라우드용 Copilot, 코드 리뷰 |
| Copilot Pro+ | 개인 | 월 39달러 | 기본 3,900크레딧(기본 39달러 + 유연 할당 31달러, 총 70달러) | Opus 포함 프리미엄 모델, Fusion Standard/High/Max, 감사 로그 |
| Copilot Max | 개인 | 월 100달러 | 기본 10,000크레딧(기본 100달러 + 유연 할당 100달러, 총 200달러) | 신규 모델 및 기능 우선 접근, 개인 요금제 최대 제공량 |
| Copilot Business | 조직 및 기업 | 부여 시트당 월 19달러 | 사용자당 월 1,900크레딧(공용 풀) | 광범위한 모델 카탈로그 및 프리미엄 모델, 중앙 관리 및 정책 제어 |
| Copilot Enterprise | 기업(GitHub Enterprise Cloud) | 부여 시트당 월 39달러 | 사용자당 월 3,900크레딧(공용 풀) | 신규 모델 및 기능 우선 접근, Copilot Business 전체 기능 포함 |
| Copilot access | 자격 요건 충족 기업 | 0달러(GitHub Enterprise Cloud 라이선스 사용자) 또는 사용자당 월 10달러(Copilot Standalone) | 기본 제공량 없음(첫 사용부터 종량 과금) | Copilot Enterprise와 동일한 기능 및 모델 자격 |

2026-11-23 기준 개인용 요금제 비교표에서 GitHub은 공용 크레딧 풀, 엔터프라이즈급 보안, 지식재산권 면책(IP indemnity), github.com 사용자 관리, 사용량 지표(usage metrics), SAML 단일 로그인(SAML SSO) 인증을 Free, Pro, Pro+, Max에서 제외된 항목으로 표시한다.[5] 같은 페이지에서 Pro 요약 카드는 서드파티 에이전트(Claude Code 및 Codex)를 Pro부터 포함하는 것으로 적고 있으며, 하단의 클라우드용 Copilot 기능 비교표는 Claude by Anthropic 및 OpenAI Codex 등 서드파티 코딩 에이전트로의 클라우드 작업 위임(Preview)을 Pro+와 Max에 포함된 항목으로 기재한다.[5]

## GitHub Copilot AI Credits와 과금 구조

GitHub Copilot은 2026-11-23 기준으로 대화형 및 에이전트 AI 사용량을 GitHub AI Credits 단위로 계량하며, 1 AI 크레딧은 0.01달러에 해당한다.[6] 채팅, 에이전트 모드, 코드 리뷰, 클라우드용 Copilot, Copilot CLI, Copilot 앱은 AI 크레딧을 소모하며, 상호작용당 소모량은 선택한 모델과 작업 복잡도에 따라 달라진다.[5][6] 인라인 코드 자동 완성(inline code completion)과 다음 편집 제안(next edit suggestions)은 AI 크레딧을 소모하지 않으며, 유료 요금제에서는 사용자의 예산이 0달러이거나 지출 한도에 도달한 경우에도 무제한으로 유지된다.[3][6]

2026-11-23 기준 개인용 유료 요금제의 월간 총 크레딧은 월 구독료와 동일한 기본 크레딧(Pro 10달러, Pro+ 39달러, Max 100달러)에 시기에 따라 변동될 수 있는 유연 할당량(flex allotment, Pro 5달러, Pro+ 31달러, Max 100달러)을 더한 값으로 구성된다.[5] 월간 제공량을 모두 소모한 사용자는 다음 월간 초기화 시점까지 기다리거나, 상호작용당 크레딧 소모가 적은 경량 모델로 전환하거나, 크레딧당 0.01달러(예산 10달러당 1,000크레딧)로 추가 종량제 예산을 설정해 작업을 이어갈 수 있으며, 추가 크레딧 구매는 Free 요금제에서 제외된다.[5][6] Copilot 설정의 예산 추적 기능은 설정한 예산의 75%, 90%, 100%에 도달하면 알림을 보낸다.[6]

조직 및 기업 환경에서는 Copilot Business와 Copilot Enterprise의 각 시트가 월간 크레딧을 조직 전체 공용 풀에 합산하며, 관리자가 추가 유료 사용을 허용하면 풀 초과분이 별도로 청구된다.[3][5][6] 관리자가 추가 유료 사용을 허용하지 않으면 다음 결제 주기까지 Copilot 이용이 일시 중지된다.[6] Copilot access 요금제는 기본 제공량 없이 첫 사용 시점부터 종량제로 청구된다.[3] Copilot 시트는 사용자 1명당 라이선스이며 추가 비용이 0달러인 경우에도 시트 할당이 필요하고, Copilot access와 Copilot Business에서는 기업 관리자가 개인 또는 엔터프라이즈 팀 단위로 시트를 직접 배정해 팀 구성원 전원에게 시트를 부여할 수 있다.[3] 데이터 상주(data residency) 및 FedRAMP 준수 Copilot 요청에는 10%의 모델 승수(multiplier) 가산이 적용된다.[3]

## GitHub Copilot 지원 AI 모델과 Copilot Fusion

GitHub Copilot은 2026-11-23 기준으로 6개 제공사의 다중 AI 모델을 지원하며, 사용 가능한 모델은 구독 요금제, 기능, 클라이언트 환경에 따라 달라진다.[2][4][5] GitHub 문서는 모델 제공 여부가 변경될 수 있고 일부 모델이 시간이 지나면서 업데이트되거나 교체될 수 있다고 안내한다.[4] 아래 표는 2026-11-23 기준 GitHub 문서(지원 모델 표에 일반 공개(GA)로 표시된 모델)와 GitHub Copilot 요금제 페이지에 등재된 모델을 제공사별로 정리한 것이다.[4][5]

| 제공사 | 등재 모델(2026-11-23 기준) |
| --- | --- |
| [OpenAI](https://mimirwiki.com/ko/wiki/openai) | GPT-5 mini, GPT-5.2, GPT-5.2-Codex, GPT-5.3-Codex, GPT-5.4, GPT-5.4 mini, GPT-5.4 nano, GPT-5.5, GPT-5.6 Luna, GPT-5.6 Sol, GPT-6 Astra, GPT-6 Luna, GPT-6 Sol, GPT-6.1 Sol, GPT-6.1 Terra, GPT-6.2 Astra, GPT-6.2 Sol |
| [Anthropic](https://mimirwiki.com/ko/wiki/anthropic) | [Claude](https://mimirwiki.com/ko/wiki/claude) Fable 5, Claude Fable 5.1, Claude Fable 5.2, Claude Haiku 4.5, Claude Haiku 5.5, Claude Sonnet 4, Claude Sonnet 4.6, Claude Sonnet 5, Claude Sonnet 5.5, Claude Opus 4.8, Claude Opus 4.8 (fast mode) (preview), Claude Opus 5.5 |
| Google | [Gemini](https://mimirwiki.com/ko/wiki/google-gemini) 3.7 Flash, Gemini 3.8 Flash, Gemini 4 Argon, Gemini 4 Carbon, Gemini 4 Hydrogen, Gemini 4 Neon |
| Microsoft | MAI-Code-1.1-Flash, MAI Code 2, MAI Code 2 Flash |
| xAI | [Grok](https://mimirwiki.com/ko/wiki/grok) 4.5, Grok 4.6, Grok 4.7 |
| Kimi | Kimi K3 |

수동 모델 선택과 함께 GitHub Copilot은 2026-11-23 기준 자동 모델 라우팅 기능인 Copilot Fusion을 제공한다.[5][6] Fusion Standard(Free, Pro, Pro+, Max 포함)는 일상 작업마다 모델 하나를 선택하며, Fusion Fast(Free, Pro, Pro+, Max 포함)는 Visual Studio Code 인라인 채팅에서만 동작하고 사용자가 직접 선택할 수 없다.[5] Fusion High(Pro+, Max 포함)는 복합 버그 수정이나 다중 파일 변경처럼 추가 모델 호출이 필요한 작업에 쓰이고, Fusion Max(Pro+, Max 포함)는 더 깊은 추론과 분석이 필요한 작업에 쓰인다.[5]

GitHub Copilot은 사용자가 자체 API 키를 입력해 외부 클라우드 모델 제공자를 연결하는 자체 API 키 연동(Bring Your Own Key, BYOK)과 Ollama 및 Foundry Local을 통한 로컬 모델 실행도 지원한다.[6]

## GitHub Copilot 지원 환경, IDE 통합, 에이전트 기능

GitHub Copilot은 2026-11-23 기준으로 코드 편집기, 터미널, 데스크톱 소프트웨어, 웹 인터페이스, 메시징 애플리케이션 전반에서 동작하며 한 환경에서 시작한 세션을 다른 환경에서 이어서 진행할 수 있다.[5][6] GitHub이 명시한 지원 편집기 및 통합 개발 환경(Integrated Development Environment, IDE)은 Visual Studio Code, Visual Studio, JetBrains IDE, Xcode, Vim, Neovim, Zed, Eclipse, Raycast, SQL Server Management Studio이다.[5][6] 편집기 외에는 터미널용 Copilot CLI, GitHub Copilot 데스크톱 앱(macOS Apple Silicon 설치 버전 포함), github.com, GitHub Mobile, Slack, Microsoft Teams에서 이용할 수 있다.[5][6]

2026-11-23 기준 GitHub이 안내하는 핵심 코딩 및 에이전트 기능은 다음과 같다.[5][6]

- **인라인 코드 제안과 다음 편집 제안**: 공개 저장소에 등장하는 언어를 기반으로 실시간 코드 자동 완성을 제공하며, Free 요금제에서는 월 2,000회로 제한되고 유료 요금제에서는 무제한이다.[5][6]
- **IDE 에이전트 모드**: Free, Pro, Pro+, Max 요금제에서 Visual Studio Code, Visual Studio, JetBrains IDE, Eclipse, Xcode 환경에 제공된다.[5]
- **클라우드용 Copilot(Copilot in the cloud)**: 유료 요금제에서 풀 리퀘스트(pull request) 생성 여부를 선택해 조사, 계획, 코드 작성을 수행하고 이슈, 풀 리퀘스트, 코드 편집기, 에이전트 패널, 외부 프로젝트 관리 도구에서 작업을 시작하고 병렬 세션을 추적한다.[5][6]
- **Copilot CLI**: 모든 요금제에 포함되어 터미널에서 작업하고 코딩 에이전트에 작업을 위임하며, 로컬 또는 GitHub에서 코드 변경 및 커밋을 수행하고 프로그래밍 모드(programmatic mode)를 실행한다.[2][5]
- **코드 리뷰 및 앱 현대화**: Pro 이상 요금제에서 GitHub 풀 리퀘스트 리뷰, 편집기 내 로컬 파일 차이(diff) 리뷰, `instructions.md` 기반 사용자 지정 지침, Java 및 .NET 애플리케이션 현대화를 제공한다.[5][6]
- **자동화 및 서드파티 에이전트**: 재사용 가능한 에이전트 작업을 수동 실행, 예약 실행 또는 지원 트리거로 실행할 수 있으며, 지원 요금제에서는 Claude by Anthropic과 [OpenAI Codex](https://mimirwiki.com/ko/wiki/openai-codex) 같은 서드파티 코딩 에이전트에 작업을 위임할 수 있다.[5][6]

사용자 지정 및 외부 도구 연동을 위해 GitHub Copilot은 사용자 지정 지침(custom instructions), 사용자 지정 에이전트, 에이전트 스킬(agent skills), Copilot Spaces, Copilot Connectors, 플러그인, 그리고 IDE 에이전트 모드와 클라우드용 Copilot 양쪽의 [Model Context Protocol](https://mimirwiki.com/ko/wiki/model-context-protocol)(MCP) 서버 연동을 지원한다.[5][6]

## GitHub Copilot 콘텐츠 필터링, 개인정보 처리, 엔터프라이즈 거버넌스

GitHub Copilot은 2026-11-23 기준으로 모든 기본 AI 모델의 입력 프롬프트와 출력 자동 완성 결과에 유해하거나 공격적이거나 주제에서 벗어난 내용을 걸러내는 콘텐츠 필터를 적용한다.[4] 사용자가 활성화한 경우 공개 코드 일치 여부(public code matching)와 코드 참조(code referencing) 필터도 함께 작동하며, 이 기능은 Free, Pro, Pro+, Max 요금제에 모두 포함된다.[4][5]

2026-11-23 기준 제품 개인정보 FAQ에서 GitHub은 GitHub Copilot이 이용 환경과 기능에 따라 다음 네 가지 범주의 개인정보를 처리한다고 밝힌다.[6]

- **사용자 참여 데이터(User Engagement Data)**: 수락하거나 거절한 자동 완성 내역, 오류 메시지, 시스템 로그, 제품 사용량 지표 등 상호작용 과정에서 수집되는 가명 식별자 데이터이다.[6]
- **프롬프트(Prompts)**: 제안을 생성하기 위해 Copilot AI로 전송되는 채팅 또는 코드 입력과 관련 문맥이다.[6]
- **제안(Suggestions)**: 프롬프트를 바탕으로 반환되는 AI 생성 코드 또는 채팅 응답이다.[6]
- **피드백 데이터(Feedback Data)**: 좋아요 또는 싫어요 반응, 선택적 의견, 지원 티켓 피드백 등 실시간 사용자 피드백이다.[6]

조직과 기업을 위해 Copilot Business와 Copilot Enterprise는 중앙 시트 관리, Copilot 정책 제어, 공용 크레딧 풀, 그리고 초과 사용 허용 여부를 정하는 관리자 지출 한도 설정을 제공한다.[2][3][6] 기업용 요금제는 개인용 요금제에서 제외되는 SAML SSO 인증, github.com 사용자 관리, 사용량 지표, 엔터프라이즈급 보안, 지식재산권 면책(IP indemnity)을 포괄하며, 감사 로그(audit logs)는 개인용 Pro+ 이상부터 제공 목록에 기재되어 있다.[5] 데이터 상주 또는 FedRAMP 준수 환경으로 라우팅되는 Copilot 요청에는 10%의 모델 승수 가산이 적용된다.[3]

## 자주 묻는 질문

### GitHub Copilot의 요금제와 가격은 어떻게 되나요?

2026-11-23 기준 개인용 요금제는 Free(0달러), Student(인증 학생 대상 0달러), Pro(월 10달러), Pro+(월 39달러), Max(월 100달러) 다섯 가지입니다. 조직 및 기업용 요금제는 Copilot Business(시트당 월 19달러), Copilot Enterprise(시트당 월 39달러), 그리고 Copilot access(GitHub Enterprise Cloud 라이선스 사용자 0달러 또는 Copilot Standalone 사용자당 월 10달러, 종량제 별도 과금)로 구성됩니다. [2][3][5]

### GitHub Copilot에서 GitHub AI Credits는 어떻게 작동하나요?

2026-11-23 기준 GitHub AI Credit 1단위는 0.01달러이며, 채팅, 에이전트 모드, 코드 리뷰, 클라우드용 Copilot, Copilot CLI, Copilot 앱 사용량이 선택한 모델과 작업 복잡도에 따라 크레딧으로 차감됩니다. 인라인 코드 자동 완성과 다음 편집 제안은 크레딧을 소모하지 않고 유료 요금제에서 무제한으로 제공됩니다. Business와 Enterprise 시트는 크레딧을 조직 공용 풀에 합산하며, 추가 종량제 예산을 설정하면 75%, 90%, 100% 시점에 알림이 발송됩니다. [3][5][6]

### GitHub Copilot은 어떤 AI 모델을 지원하나요?

2026-11-23 기준 GitHub Copilot은 OpenAI(GPT-5 및 GPT-6 시리즈), Anthropic(Claude Fable, Haiku, Sonnet, Opus 시리즈), Google(Gemini 3.7, 3.8 및 Gemini 4 시리즈), Microsoft(MAI Code 시리즈), xAI(Grok 4.5~4.7), Kimi(Kimi K3) 모델을 지원합니다. 사용자는 Copilot Fusion으로 자동 라우팅을 쓰거나 특정 모델을 직접 선택할 수 있으며, 자체 API 키로 외부 클라우드 제공자를 연결하거나 Ollama와 Foundry Local로 로컬 모델을 실행할 수도 있습니다. [4][5][6]

### GitHub Copilot Free에는 어떤 기능이 포함되나요?

2026-11-23 기준 GitHub Copilot Free는 신용카드 등록 없이 무료로 이용할 수 있으며 월 2,000회 인라인 코드 자동 완성, 제한된 채팅 및 에이전트 사용량, Copilot CLI, Copilot 앱, Copilot Spaces, 에이전트 모드의 Model Context Protocol 서버 연동, Copilot Fusion Standard, 커뮤니티 지원을 포함합니다. 코드 리뷰, 클라우드용 Copilot, 에이전트 작업 할당을 통한 풀 리퀘스트 생성, 추가 크레딧 구매는 포함되지 않습니다. [2][5][6][9]

### GitHub Copilot은 어떤 IDE와 플랫폼을 지원하나요?

2026-11-23 기준 GitHub Copilot은 Visual Studio Code, Visual Studio, JetBrains IDE, Xcode, Vim, Neovim, Zed, Eclipse, Raycast, SQL Server Management Studio를 지원합니다. 또한 Copilot CLI 터미널, GitHub Copilot 데스크톱 앱, github.com, GitHub Mobile, Slack, Microsoft Teams에서도 사용할 수 있으며 GitHub Enterprise Server에서는 지원되지 않습니다. [2][5][6]

### Microsoft는 SEC Form 10-K에서 GitHub Copilot을 어떻게 보고하나요?

Microsoft Corporation의 2026년 6월 30일 종료 회계연도 Form 10-K에서 GitHub 클라우드 서비스는 Intelligent Cloud 부문의 서버 제품 및 클라우드 서비스 항목과 Azure 및 기타 클라우드 서비스 매출 성장 지표에 포함되어 보고됩니다. 해당 공시는 GitHub을 소프트웨어 개발 수명 주기 전반에 AI와 에이전트 기반 도구를 통합하는 클라우드 및 온프레미스 협업 플랫폼으로 설명하며, GitHub Copilot의 단독 매출은 별도로 구분해 기재하지 않았습니다. [1]

## 인용 문장

- GitHub은 2021년 6월 29일 OpenAI Codex를 기반으로 한 GitHub Copilot 기술 미리보기를 출시했다. [7]
- GitHub은 2022년 6월 21일 월 10달러 또는 연 100달러 가격으로 개인 개발자 대상 GitHub Copilot 일반 공개를 시작했다. [8]
- GitHub은 2024년 12월 18일 월 2,000회 코드 자동 완성과 50회 채팅 메시지를 제공하는 GitHub Copilot Free를 Visual Studio Code에 통합해 출시했다. [9]
- 2026-11-23 기준 GitHub은 개인용 유료 Copilot 요금제를 Pro 월 10달러, Pro+ 월 39달러, Max 월 100달러로 게시하고 있다. [2][5]
- 2026-11-23 기준 GitHub은 Copilot Business를 부여 시트당 월 19달러, Copilot Enterprise를 부여 시트당 월 39달러로 책정하고 있다. [2][3]
- 2026-11-23 기준 GitHub AI Credit 1단위는 0.01달러이며, 유료 요금제에서 인라인 코드 자동 완성과 다음 편집 제안은 크레딧을 소모하지 않는다. [3][6]
- 2026-11-23 기준 GitHub Copilot은 OpenAI, Anthropic, Google, Microsoft, xAI, Kimi의 모델을 지원하며 자체 API 키 클라우드 모델 연동과 Ollama 및 Foundry Local 기반 로컬 모델 실행을 지원한다. [4][5][6]
- Microsoft Corporation의 2026년 6월 30일 종료 회계연도 Form 10-K는 GitHub 클라우드 서비스를 Intelligent Cloud 부문의 서버 제품 및 클라우드 서비스 항목에 포함한다. [1]

## 연표

- 2021-06-29: GitHub이 OpenAI와 협력해 OpenAI Codex 기반의 GitHub Copilot 제한적 기술 미리보기를 출시했다. [7]
- 2022-06-21: GitHub이 월 10달러 또는 연 100달러 가격으로 모든 개인 개발자 대상 GitHub Copilot 일반 공개를 시작하고, 인증 학생과 주요 오픈소스 프로젝트 관리자에게 무료 이용을 제공했다. [8]
- 2024-12-18: GitHub이 플랫폼 개발자 수 1억 5,000만 명 돌파와 함께 Visual Studio Code 및 GitHub 대시보드에 통합된 GitHub Copilot Free를 출시했다. [9]
- 2026-06-30: Microsoft Corporation의 2026 회계연도가 종료되었으며, Form 10-K에서 GitHub 클라우드 서비스를 Intelligent Cloud 부문으로 보고했다. [1]

## 출처

1. Microsoft Corporation Form 10-K for the fiscal year ended June 30, 2026. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (확인일 2026-11-23; tier 1: government or public registry)
2. Plans for GitHub Copilot - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/get-started/plans (확인일 2026-11-23; tier 3: official site)
3. GitHub Copilot seats and billing cycles for organizations and enterprises - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/concepts/billing-and-usage/organizations-and-enterprises/seats-and-billing-cycles (확인일 2026-11-23; tier 3: official site)
4. Supported AI models in GitHub Copilot - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/reference/ai-models/supported-models (확인일 2026-11-23; tier 3: official site)
5. GitHub Copilot · Plans & pricing for every developer & team · GitHub. GitHub. https://github.com/features/copilot/plans (확인일 2026-11-23; tier 3: official site)
6. GitHub Copilot · Your AI coding agent · GitHub. GitHub. https://github.com/features/copilot (확인일 2026-11-23; tier 3: official site)
7. Introducing GitHub Copilot: your AI pair programmer - The GitHub Blog. The GitHub Blog. 게시일 2021-06-29. https://github.blog/news-insights/product-news/introducing-github-copilot-ai-pair-programmer/ (확인일 2026-11-23; tier 3: official site)
8. GitHub Copilot is generally available to all developers - The GitHub Blog. The GitHub Blog. 게시일 2022-06-21. https://github.blog/news-insights/product-news/github-copilot-is-generally-available-to-all-developers/ (확인일 2026-11-23; tier 3: official site)
9. Announcing 150M developers and a new free tier for GitHub Copilot in VS Code - The GitHub Blog. The GitHub Blog. 게시일 2024-12-18. https://github.blog/news-insights/product-news/github-copilot-in-vscode-free/ (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "GitHub Copilot." 버전 915782d7, 2026-11-23. https://mimirwiki.com/ko/wiki/github-copilot
