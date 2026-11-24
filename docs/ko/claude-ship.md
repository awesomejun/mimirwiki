---
title: "Claude Ship"
subtitle: "GitHub 풀 리퀘스트의 검토, 수정, 정책 기반 승인을 수행하는 Anthropic의 에이전트 도구 모음"
canonical_url: https://mimirwiki.com/ko/wiki/claude-ship
language: ko
page_class: entity
revision_sha256: da6660e4648f7019b54de023f0b75a41996fad01220294f905891606e397d320
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/claude-ship.md
  txt: https://mimirwiki.com/ko/wiki/claude-ship.txt
  json: https://mimirwiki.com/ko/wiki/claude-ship.json
  jsonld: https://mimirwiki.com/ko/wiki/claude-ship.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude-ship
---

# Claude Ship

> Claude Ship은 Anthropic이 2026-11-23 발표한 Claude Team 및 Enterprise 요금제용 GitHub 풀 리퀘스트 에이전트 모음이다. 정식 제공 중인 Code Review와 공개 베타인 PR Steward 및 Claude Approvals로 구성되며, 코드 검토, 수정 커밋, 정책 기반 승인 확인을 자동화하고 병합 통제는 저장소 설정과 GitHub 규칙에 맡긴다.

Claude Ship은 Anthropic이 개발한 GitHub 풀 리퀘스트(pull request, PR) 대상 AI 에이전트 도구 모음으로, 코드 검토, 수정 커밋 푸시, 저장소 정책 기반 승인 여부 평가를 수행한다. 2026-11-23 발표된 Claude Ship은 Code Review(2026-10-15 정식 제공), PR Steward(공개 베타), Claude Approvals(공개 베타) 세 가지 에이전트로 구성된다. Claude Team 및 Enterprise 요금제에서 제공되며, 실제 병합 여부는 저장소 설정과 GitHub 브랜치 보호 규칙 또는 규칙 집합(rulesets)에 따라 결정된다.

**다른 이름:** Claude Ship 에이전트, /ship

## 핵심 정보

- **개발사:** Anthropic [1]
- **발표일:** 2026-11-23 [1]
- **구성 요소 제공 상태:** Code Review: 정식 제공, PR Steward 및 Claude Approvals: 공개 베타 (기준 2026-11-24) [1]
- **지원 요금제:** GitHub 저장소 대상 Claude Team 및 Enterprise 요금제 (기준 2026-11-24) [4]

## 기본 정보

- **개발사:** Anthropic [1]
- **발표일:** 2026-11-23 [1]
- **구성 요소:** Code Review, PR Steward, Claude Approvals [4]
- **Code Review 상태:** 정식 제공(2026-10-15 정식 제공, 2026-03-09 연구용 미리보기) (기준 2026-11-24) [3]
- **PR Steward 상태:** 공개 베타 (기준 2026-11-24) [5]
- **Claude Approvals 상태:** 공개 베타 (기준 2026-11-24) [6]
- **지원 플랫폼:** GitHub(github.com, Code Review와 PR Steward는 GitHub Enterprise Server 지원) (기준 2026-11-24) [5]
- **요금제:** Claude Team 및 Enterprise (기준 2026-11-24) [4]
- **과금 방식:** 토큰 사용량 기준 과금(Claude Approvals는 기본 요금 없음, 정책 분류기 및 유발된 Code Review는 토큰 과금) (기준 2026-11-24) [1]
- **CLI 명령:** Claude Code의 /ship 명령 [4]

## Claude Ship 개요 및 연혁

Claude Ship은 [Anthropic](https://mimirwiki.com/ko/wiki/anthropic)이 GitHub 풀 리퀘스트(pull request, PR)의 검토, 수정, 정책 기반 승인 확인을 처리하기 위해 제공하는 에이전트 모음이다.[1][4] Anthropic은 2026-11-23 기존 Code Review 제품과 새 공개 베타 에이전트 2종(PR Steward, Claude Approvals)을 묶어 Claude Ship을 발표했다.[1] 같은 날 기술 매체 TechCrunch와 The Verge도 출시 소식을 보도했다.[11][12]

Code Review는 Claude Ship 통합 발표 이전에 먼저 출시되었다. Anthropic은 2026-03-09 Team 및 Enterprise 조직 대상으로 Code Review 연구용 미리보기(research preview)를 공개했고, 2026-10-15 정식 제공(generally available)을 발표했다.[2][3] 2026-11-24 기준 Code Review는 정식 제공 상태이며, PR Steward와 Claude Approvals는 공개 베타 상태이고 정식 출시일은 공개되지 않았다.[1][5][6] 개발자는 개별 PR에 대해 Claude Code에서 `/ship` 명령을 실행해 변경 사항 푸시, PR 생성, 검토, 피드백 및 실패한 검사 수정 작업을 진행할 수도 있다.[1][4]

## Claude Ship 구성 에이전트 및 작동 방식

Claude Ship은 저장소 단위로 자동 실행할 수 있는 세 가지 에이전트로 PR 처리 단계를 나눈다.[1][4]

- **Code Review**는 여러 에이전트를 병렬로 투입해 주변 코드베이스와 함께 PR을 검토하고, 오탐(false positive)을 걸러내기 위한 검증을 거친 뒤 심각도 순으로 정리한 요약 댓글과 해당 코드 줄의 인라인 댓글을 남긴다.[2][4] 관리자는 저장소별로 `Quick`, `Standard`(기본값), `Deep` 세 가지 검토 수준을 선택할 수 있다.[3] Anthropic은 정식 제공 시점에 대부분의 검토가 6~10분 내에 완료되며, 연구용 미리보기 당시 평균 약 20분보다 빨라졌다고 밝혔다.[2][3] 또한 Anthropic은 Claude Code 팀 내부에서 2026년 6월부터 9월 사이 병합된 PR 수가 두 배 이상 증가했고 되돌려진(reverted) 비율은 40% 이상 감소했다고 발표했다.[1]
- **PR Steward**는 열려 있는 PR을 클라우드 세션에서 추적하며, PR이 수정한 코드에서 발생한 지속적 통합(CI) 검사 실패, 병합 충돌(merge conflict), 사람이나 Code Review 등 검토 도구의 피드백, Claude Approvals 검사 결과를 해결하기 위해 수정 커밋을 푸시한다.[1][5] 푸시할 때마다 변경 내용과 되돌리는 방법을 댓글로 남긴다.[1] 개발자는 `@claude` 댓글로 작업을 지시하거나, `@claude stop` 댓글 또는 `claude-pr-steward-watching` 라벨 제거로 동작을 멈출 수 있다.[1][5] 기본 설정에서는 초안(draft) PR, 포크(fork)에서 열린 PR, 봇이 연 PR, 저장소 쓰기 권한이 없는 작성자의 PR을 건너뛴다.[5] 제품 문서에 따르면 PR Steward는 풀 리퀘스트를 승인하거나 병합하지 않도록 설계되었다.[4][5]
- **Claude Approvals**는 저장소의 `.claude/approvals.yml` 정책 파일에 따라 PR을 평가하고, 누가 추가로 승인해야 하는지 표시하는 `Claude Approvals` 상태 검사를 추가한다.[6] 정책 규칙에는 경로 패턴, 필요한 사람 승인 수(seats), Claude가 댓글만 남길지 승인 리뷰를 게시할 수 있는지 여부, 그리고 PR 속성이나 자연어 분류기(classifier)에 기반한 조건을 지정할 수 있다.[1][6] 규칙 조건은 CI 결과를 읽을 수 없으므로 CI 검사는 GitHub에서 별도의 필수 검사로 유지해야 한다.[6] Anthropic은 병합을 차단하지 않고 정책 판단 결과만 표시하는 관찰 모드(`observe` mode)로 먼저 운영할 것을 권장한다.[1][6]

## Claude Ship과 GitHub 병합 통제

Claude Ship 환경에서 실제 병합 가능 여부는 저장소 설정과 GitHub의 병합 통제 규칙에 따라 결정된다.[4] Anthropic은 제품 문서에서 Claude Ship이 AI를 사용하므로 버그나 보안 취약점 또는 기타 문제를 놓칠 수 있다고 명시하고, 병합 전 원하는 승인을 요구하려면 브랜치 보호(branch protection)를 사용하라고 안내한다.[4]

Claude Approvals 검사는 GitHub에서 필수 검사(required check)로 지정된 경우에만 병합을 차단하며, 관찰 모드에서는 보통 차단하지 않는다.[4][6] 문서는 또한 필수 검사로 지정되지 않은 경우, 정책에서 작성자 본인이 유일한 승인 좌석을 채울 수 있게(`seats: 1`) 설정하거나 `seats: 0`으로 둔 경우, GitHub 브랜치 규칙이 1개의 승인만 요구할 때 Claude의 승인 리뷰가 그 승인으로 계산되는 경우, 또는 Code Review 통과 조건 없이 `claude: approves`를 허용한 경우 다른 사람의 검토 없이 PR이 병합될 수 있다고 주의사항을 명시한다.[6] 아울러 `.claude/approvals.yml` 정책 파일을 추가하면 해당 파일 범위에 대한 자동 Code Review가 중단되므로, 자동 검토를 유지하려면 규칙에 `claude/code_review`를 명시해야 한다.[6]

GitHub 측 병합 통제는 2023-07-12 정식 제공된 풀 리퀘스트 병합 대기열(merge queue), 2026-02-17 정식 제공되어 팀 단위 승인 요구와 `!` 제외 패턴을 지원하는 저장소 규칙 집합의 필수 검토자 규칙(required reviewer rule), 그리고 2026-08-11 공개된 기존 브랜치 보호 규칙의 저장소 규칙 집합 자동 이전 기능을 통해 동작한다.[8][9][10]

## Claude Ship 제공 범위, 설정 및 과금

Claude Ship은 2026-11-24 기준 GitHub 저장소를 사용하는 Claude Team 및 Enterprise 요금제 조직에 제공된다.[1][4] Claude 조직의 소유자(Owner)가 claude.ai의 `Organization settings > Claude Ship`에서 Code Review와 PR Steward를 켜고 GitHub 계정을 연결한 뒤, GitHub 조직 소유자가 설치한 Claude GitHub App을 연동하면 된다. 검토는 Anthropic 인프라에서 실행되므로 저장소에 별도 워크플로 파일을 추가하지 않는다.[5][7] Claude Approvals는 사전 조건이 충족된 저장소의 기본 브랜치에 병합 권한이 있는 사용자가 `.claude/approvals.yml` 파일을 추가하면 동작하며, Claude 조직 소유자는 조직 전체에서 Approvals를 끌 수 있다.[1][6]

| 에이전트 | 제공 상태(2026-11-24 기준) | 지원 GitHub 환경 | 규정 준수 제한 |
| --- | --- | --- | --- |
| Code Review | 정식 제공 | github.com 및 GitHub Enterprise Server | Zero Data Retention, HIPAA 구성, CMEK 미지원 |
| PR Steward | 공개 베타 | github.com 및 GitHub Enterprise Server(포트 443) | Zero Data Retention, HIPAA 구성, CMEK 미지원 |
| Claude Approvals | 공개 베타 | github.com(GitHub Enterprise Cloud 포함) | Zero Data Retention, HIPAA 구성, CMEK 미지원, FERPA 또는 Access Transparency 설정 시 시작 불가 |

Code Review와 PR Steward 사용량은 토큰 기준으로 과금되며, 관리자는 월간 지출 한도를 설정할 수 있다.[1][5] Claude Approvals 자체에는 기본 요금이 없으나, 정책에 포함된 분류기 실행과 정책이 유발하는 Code Review는 관찰 모드를 포함해 토큰 기준으로 과금된다.[1][6] Claude Code에서 `/ship`을 실행하는 작업은 일반 Claude Code 사용량으로 집계된다.[1] Anthropic은 2026-11-23 발표에서 자격을 갖춘 Claude Enterprise 조직이 2027-01-15까지 최소 10,000달러의 Claude Ship 크레딧을 신청해 수령 후 30일간 사용할 수 있다고 밝혔다.[1]

## 자주 묻는 질문

### Claude Ship을 구성하는 세 가지 에이전트는 무엇인가요?

Claude Ship은 정식 제공 중인 Code Review와 공개 베타인 PR Steward, Claude Approvals로 구성됩니다. Code Review는 심각도 순으로 문제점을 보고하고, PR Steward는 실패한 검사·병합 충돌·검토 피드백에 대한 수정 커밋을 올리며, Claude Approvals는 저장소 정책 파일에 따라 승인 여부를 평가합니다. [1][4]

### PR Steward가 GitHub 풀 리퀘스트를 직접 승인하거나 병합할 수 있나요?

아닙니다. Anthropic 제품 문서에 따르면 PR Steward는 풀 리퀘스트를 승인하거나 병합하지 않도록 설계되었으며, 병합 전 필요한 승인을 강제하려면 GitHub 브랜치 보호 규칙이나 규칙 집합을 사용해야 합니다. [4][5]

### Claude Approvals의 관찰 모드는 어떻게 작동하나요?

관찰 모드(observe mode)에서는 병합을 차단하지 않으면서 `.claude/approvals.yml` 정책이 어떤 결정을 내릴지 상태 검사로 보여 줍니다. 다만 관찰 모드에서도 정책이 실행하는 분류기와 Code Review에는 토큰 과금이 적용됩니다. [1][6]

### Claude Ship을 사용할 수 없는 조직 조건이 있나요?

2026-11-24 기준 Zero Data Retention이 활성화되었거나 HIPAA 구성 또는 고객 관리 암호화 키(CMEK)를 적용한 조직은 Claude Ship을 사용할 수 없습니다. 또한 Claude Approvals는 FERPA 또는 Access Transparency 설정이 있는 조직에서 시작할 수 없습니다. [1][6]

## 인용 문장

- Anthropic은 2026-11-23 GitHub 저장소를 사용하는 Claude Team 및 Enterprise 요금제 대상으로 Claude Ship을 발표했다. [1]
- Code Review는 2026-03-09 연구용 미리보기로 공개되었고 2026-10-15 정식 제공으로 전환되었다. [2][3]
- 2026-11-24 기준 PR Steward와 Claude Approvals는 공개 베타 상태이다. [5][6]
- PR Steward는 풀 리퀘스트를 승인하거나 병합하지 않도록 설계되었다. [4][5]
- Claude Approvals는 저장소의 .claude/approvals.yml 정책 파일을 읽으며, 규칙 조건에서 CI 결과를 읽을 수 없다. [6]
- Claude Ship 사용량은 토큰 기준으로 과금되며, 관찰 모드에서 정책이 실행하는 분류기와 Code Review에도 과금이 적용된다. [1][6]

## 연표

- 2026-03-09: Anthropic이 Team 및 Enterprise 조직 대상으로 Claude Code용 Code Review 연구용 미리보기를 공개했다. [2]
- 2026-10-15: Anthropic이 저장소별 Quick·Standard·Deep 검토 수준을 포함한 Code Review 정식 제공을 발표했다. [3]
- 2026-11-23: Anthropic이 정식 제공 중인 Code Review와 공개 베타인 PR Steward, Claude Approvals를 묶은 Claude Ship을 발표했다. [1]

## 출처

1. Introducing Claude Ship. Anthropic. 게시일 2026-11-23. https://claude.com/resources/articles/introducing-claude-ship (확인일 2026-11-24; tier 3: official site)
2. Bringing Code Review to Claude Code. Anthropic. 게시일 2026-03-09. https://claude.com/resources/articles/code-review (확인일 2026-11-24; tier 3: official site)
3. Code Review is now generally available. Anthropic. 게시일 2026-10-15. https://claude.com/resources/articles/code-review-is-now-generally-available (확인일 2026-11-24; tier 3: official site)
4. Claude Ship - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/claude-ship (확인일 2026-11-24; tier 3: official site)
5. PR Steward - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/pr-steward (확인일 2026-11-24; tier 3: official site)
6. Claude Approvals - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/approvals (확인일 2026-11-24; tier 3: official site)
7. Set up Code Review - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/code-review-setup (확인일 2026-11-24; tier 3: official site)
8. Required reviewer rule is now generally available. GitHub. 게시일 2026-02-17. https://github.blog/changelog/2026-02-17-required-reviewer-rule-is-now-generally-available/ (확인일 2026-11-24; tier 3: official site)
9. Automatically migrate branch protection rules to repository rulesets. GitHub. 게시일 2026-08-11. https://github.blog/changelog/2026-08-11-automatically-migrate-branch-protection-rules-to-repository-rulesets/ (확인일 2026-11-24; tier 3: official site)
10. Pull request merge queue is now generally available!. GitHub. 게시일 2023-07-12. https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/ (확인일 2026-11-24; tier 3: official site)
11. Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes. TechCrunch. 게시일 2026-11-23. https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/ (확인일 2026-11-24; tier 2: academic or news)
12. Claude AI can review pull requests and ship fixes on its own now. The Verge. 게시일 2026-11-23. https://www.theverge.com/ai-artificial-intelligence/1040134/anthropic-claude-ship-ai-pull-requests (확인일 2026-11-24; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "Claude Ship." 버전 da6660e4, 2026-11-24. https://mimirwiki.com/ko/wiki/claude-ship
