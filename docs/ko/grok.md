---
title: "그록 (Grok)"
subtitle: "xAI(스페이스X 슈퍼 인텔리전스)가 개발한 생성형 인공지능 모델 제품군·개발자 API 및 통합 에이전트 애플리케이션 생태계"
canonical_url: https://mimirwiki.com/ko/wiki/grok
language: ko
page_class: entity
revision_sha256: 52a0d3ef3e2328a3e8636ebfd04d26bb53cdb5524d81fef0eeb751001a7334eb
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ko/wiki/grok.md
  txt: https://mimirwiki.com/ko/wiki/grok.txt
  json: https://mimirwiki.com/ko/wiki/grok.json
  jsonld: https://mimirwiki.com/ko/wiki/grok.jsonld
translations:
  en: https://mimirwiki.com/wiki/grok
  ja: https://mimirwiki.com/ja/wiki/grok
  zh: https://mimirwiki.com/zh/wiki/grok
---

# 그록 (Grok)

> xAI(SpaceX Super Intelligence LLC)가 개발한 그록은 3,140억 파라미터 오픈웨이트 모델 그록-1(Apache 2.0)과 그록-2(2024년)를 거쳐 2026년 말 주력 플래그십 모델인 그록 4.7(`grok-4.7`, 50만 토큰 컨텍스트, 2026년 5월 지식 기준일, 입력 $2.00/출력 $6.00)로 발전했다. 2026년 10월 12일에는 그록, 그록 봇(Grok Bot), 커서(Cursor) 코딩 에이전트, X 프리미엄을 주간 공유 AI 사용량 풀 하나로 묶은 '더 X 서브스크립션'(무료 $0, 플러스 $8, 프리미엄 $30, 슈퍼 $100, 울트라 $200/월)을 출시했다.

그록(Grok)은 xAI(2026년 기준 법인명 SpaceX Super Intelligence LLC, 약칭 SpaceXSI)가 개발한 생성형 인공지능(AI) 파운데이션 모델 제품군이자 대화·코딩·미디어 생성 애플리케이션 및 개발자 API 플랫폼이다. `grok.com`, 모바일 앱, 소셜 네트워크 X(구 트위터), 그리고 AI 코딩 에디터 커서(Cursor)에 통합되어 있으며, 2026년 하반기 기준 주력 추론·코딩 모델인 그록 4.7(`grok-4.7`)과 전용 음성·이미지·비디오 생성 모델을 리스폰스 API(Responses API) 및 통합 구독 요금제인 '더 X 서브스크립션(The X Subscription)'을 통해 제공한다.

**다른 이름:** Grok, xAI, SpaceX Super Intelligence, Grok 4.7, The X Subscription, Grok-1

## 핵심 정보

- **개발사 및 운영 법인:** xAI / SpaceX Super Intelligence LLC (SpaceXSI, 구독 판매 법인: X Subscription Corp.) [4]
- **2026년 주력 모델:** Grok 4.7 (grok-4.7): 50만 토큰 컨텍스트, 2026년 5월 지식 기준일, 입력 $2 / 출력 $6 (100만 토큰당) [2]
- **제품 및 에이전트 제품군:** Grok Chat, Grok Build, Grok Bot, Imagine(Image 2.0·Video 1.5), Voice API(grok-voice-3.0), Grokipedia [3]
- **더 X 서브스크립션 (2026-10-12):** Grok·Grok Bot·Cursor·X Premium 단일 구독 통합 (Free $0, Plus $8, Premium $30, Super $100, Ultra $200) [4]
- **오픈웨이트 공개 모델:** Grok-1 (xai-org/grok-1): 3,140억 파라미터 8전문가 MoE(토큰당 2개 활성), 64계층, Apache 2.0 [7]

## 기본 정보

- **개발사:** xAI (SpaceX Super Intelligence LLC / SpaceXSI) [4]
- **플래그십 모델:** 그록 4.7 (Grok 4.7, 모델 ID: grok-4.7) [1]
- **컨텍스트 윈도:** 500,000 토큰 (Grok 4.7) / 8,192 토큰 (Grok-1 오픈웨이트) [2]
- **지식 기준일:** 2026년 5월 (Grok 4.7 기준) [2]
- **Grok 4.7 API 요금:** 입력 $2.00 / 출력 $6.00 (100만 토큰당) [1]
- **음성 및 미디어 API 요금:** STS $0.08/분, TTS $15/100만 자, STT $0.10~$0.20/시간, 이미지 $0.02~/장, 비디오 $0.02~/초 [1]
- **API 속도 제한 등급:** Tier 0($0) ~ Tier 4(2026년 누적 $5,000 이상): Grok 4.5~4.7 기준 최대 500 RPS 및 100M TPM [3]
- **The X Subscription 요금제:** Free($0), Plus($8/월), Premium($30/월, 4배), Super($100/월, 15배), Ultra($200/월, 50배) [6]
- **클라우드 파트너 플랫폼:** xAI API (api.x.ai/v1), Google Cloud Vertex AI, Microsoft Foundry [1]
- **오픈웨이트 라이선스:** Apache 2.0 (Grok-1 314B 체크포인트, github.com/xai-org/grok-1) [7]

## 그록-1·그록-2에서 스페이스X 슈퍼 인텔리전스까지의 발전 과정

그록(Grok)은 소셜 네트워크 X(구 트위터)와의 실시간 데이터 연동, 대화형 추론, 코딩 지원을 목표로 xAI가 개발한 인공지능 시스템이다.[7][8] 초기 세대에서 xAI는 3,140억(314B) 파라미터 규모의 오픈웨이트 기본 모델인 그록-1(`github.com/xai-org/grok-1` 및 `huggingface.co/xai-org/grok-1`)의 가중치와 JAX 예제 코드를 아파치 2.0(Apache 2.0) 라이선스로 공개했다.[7] 그록-1은 64개 트랜스포머 계층과 계층당 8개 전문가 중 토큰당 2개 전문가를 활성화하는 전문가 혼합(Mixture-of-Experts, MoE) 아키텍처로 설계되었으며, 임베딩 크기 6,144, 쿼리 어텐션 헤드 48개 및 키·밸류 헤드 8개, 회전 위치 임베딩(RoPE), 13만 1,072토큰 규모의 센텐스피스(SentencePiece) 토크나이저, 8비트 양자화 및 활성화 샤딩 지원, 최대 시퀀스 길이 8,192토큰 사양을 갖추었다.[7]

2024년 8월 그록-2 출시를 거쳐 2024년 12월 12일에는 추론 속도를 3배 높이고 다국어·지시 이행 성능을 개선한 신형 그록-2(`grok-2-1212` 및 `grok-2-vision-1212`)가 X의 모든 사용자에게 무료로 개방되었으며, 웹 검색·인용 출처 표시·타임라인 '그록 버튼'과 자기회귀형 실사 이미지 생성 모델 오로라(Aurora)가 도입되면서 API 요금이 입력 2달러/출력 10달러(100만 토큰당)로 인하되었다.[8]

2026년 기준 xAI의 공식 개발자 문서와 뉴스룸은 스페이스X 슈퍼 인텔리전스(SpaceX Super Intelligence LLC, 약칭 SpaceXSI, 공식 계정 `@SpaceXSI` 및 `@grok`) 법인 명의로 운영되며, 직접 구독 상품은 X 서브스크립션 코퍼레이션(X Subscription Corp.)을 통해 판매된다.[1][4][5] 제품군 역시 단순 챗봇을 넘어 그록 챗(Chat), 에이전트 코딩 도구 그록 빌드(Grok Build), 자율 AI 팀원 그록 봇(Grok Bot), 이미지·비디오 생성 도구 이매진(Imagine), 실시간 음성(Voice), 그로키피디아(Grokipedia)로 확장되었다.[3][4]

## 그록 4.7 플래그십 및 멀티모달 모델 카탈로그

2026년 11월 기준 xAI의 최상위 주력 모델은 그록 4.7(`grok-4.7`)로, 코드 작성·디버깅과 일반 텍스트 대화, 에이전트 도구 호출 전 영역에서 기본 모델로 권장된다.[1][2] 그록 4.7은 50만(500K) 토큰 컨텍스트 윈도, 추론 강도 설정(Configurable reasoning), 2026년 5월 지식 기준일(knowledge cut-off)을 갖추고 있으며, API 요금은 입력 100만 토큰당 2.00달러, 출력 100만 토큰당 6.00달러로 책정되어 그록-2 시절($2/$10)보다 출력 요금이 40% 더 낮아졌다.[1][2][8]

그록 4.7 및 4.x 세대 API 모델의 주요 기술적 규칙은 다음과 같다.[2][3]

- **암호화된 추론 콘텐츠 상시 반환**: 리스폰스 API(`POST https://api.x.ai/v1/responses`)에서 `grok-4.7`을 호출하면 요청의 `include` 배열에 명시하지 않아도 항상 `reasoning.encrypted_content` 필드가 응답에 포함되어 반환된다.[2]
- **역할 순서 제약 해제 및 로그 확률 비활성화**: 대화 컨텍스트에서 `system`, `user`, `assistant` 역할을 순서 제한 없이 자유롭게 혼합해 배치할 수 있다.[2] 반면 `grok-4.20` 이후 모델부터는 `logprobs`와 `top_logprobs` 매개변수가 지원되지 않으며 전달 시 오류 없이 무시된다.[2]
- **이미지 시각 입력 사양**: 이미지 입력을 지원하는 모델은 파일당 최대 20MiB 크기의 `jpg`/`jpeg` 또는 `png` 이미지를 개수 제한 없이(컨텍스트 토큰 한도 내에서) 받을 수 있으며 이미지와 텍스트 프롬프트의 배치 순서에도 제약이 없다.[2]
- **실시간 검색 도구 명시적 활성화**: 모델 자체는 2026년 5월 학습 데이터 이후의 실시간 사건을 알지 못하므로, 최신 정보가 필요한 요청에서는 서버 측 검색 도구(Web Search, X Search, Collections RAG, Code Execution, Remote MCP Tools)를 명시적으로 활성화해야 한다.[1][2]

2026년 11월 기준 xAI API가 제공하는 전체 모델 제품군과 요금은 다음과 같다.[1][2][3]

| 모델 / 엔드포인트 분류 | 활성 모델 식별자 (Model ID) | 주요 사양 및 API 과금 기준 |
| --- | --- | --- |
| 주력 언어 및 추론 모델 | `grok-4.7` (최신), `grok-4.6`, `grok-4.5`, `grok-4.3` | 500K 컨텍스트(`grok-4.7`), 입력 $2.00 / 출력 $6.00 (100만 토큰당) |
| 에이전트 코딩·다중 에이전트 | `grok-build-0.1`, `grok-4.20-multi-agent-0309`, `grok-4.20-0309-reasoning`, `grok-4.20-0309-non-reasoning` | Grok Build 기반 에이전트 코딩, 리팩터링, 다중 에이전트 협업 워크플로 구동 |
| 이미지 생성 (Imagine) | `grok-imagine-image-2.0` (Image 2.0), `grok-imagine-image` | 1K / 2K 해상도 생성, 이미지 편집 및 다중 이미지 편집; 장당 $0.02부터 |
| 비디오 생성 (Imagine) | `grok-imagine-video-1.5` (Video 1.5), `grok-imagine-video-1.5-lite`, `grok-imagine-video` | 480p / 720p / 1080p(Super·Ultra에서 최대 15초), 이미지·참조 기반 비디오 생성·편집·연장; 초당 $0.02부터 |
| 음성 및 오디오 (Voice API) | `grok-voice-3.0`, Text to Speech (TTS), Speech to Text (STT) | 음성 대 음성(STS) 분당 $0.08 / TTS 100만 자당 $15.00 / STT 배치 시간당 $0.10 / STT 스트리밍 시간당 $0.20 |

## xAI API 인프라·클라우드 파트너십 및 속도 제한 등급(Tier 0~4)

xAI API는 리스폰스 API(`https://api.x.ai/v1/responses`), 오픈AI 호환 REST 인터페이스, gRPC 기반 네이티브 파이썬 SDK(`xai_sdk`), 버셀 AI SDK(`@ai-sdk/xai`)를 지원하며, 구글 클라우드 버텍스 AI(Google Cloud Vertex AI)와 마이크로소프트 파운드리(Microsoft Foundry)에서도 파트너 모델로 제공된다.[1][3] 엔터프라이즈 기능으로는 프롬프트 캐싱, 컨텍스트 압축(Context Compaction), 우선순위 처리(Priority Processing), 맞춤형 모더레이션 제어, 배치 API, 지연 완료(Deferred Completions), 비동기 요청, 웹소켓 모드, mTLS 인증, 리전별 엔드포인트, 출력 워터마킹이 지원된다.[1][3]

모든 API 팀에는 모델별로 초당 요청 수(RPS)와 분당 토큰 수(TPM, 음성 모델은 동시 세션 수 CST)의 두 가지 속도 제한이 적용된다.[3] 갑작스러운 트래픽 폭주를 막기 위해 초당 요청 한도는 분당 요청 예산에서 파생(`RPM / 48`, 최소 2 RPS)되며, 프롬프트 토큰(텍스트·이미지·오디오), 완료 토큰, 추론 토큰, 그리고 할인 과금되는 캐시 적중 프롬프트 토큰까지 모두 해당 모델의 TPM 한도에 합산된다.[3] 속도 제한 등급은 2026년 1월 1일 이후의 누적 API 결제액(선불 크레딧 구매 또는 정산 완료된 청구서 기준)에 따라 자동 승급되며 한 번 달성한 등급은 영구히 유지(강등 없음)된다.[3]

| 속도 제한 등급 | 2026년 1월 1일 이후 누적 지출 요건 | `grok-4.7` / `4.6` / `4.5` (RPS / TPM) | `grok-4.3` / `grok-build-0.1` / `4.20` (RPS / TPM) | `grok-4.20-multi-agent` (RPS / TPM) | `grok-imagine-image-2.0` (RPS) | `grok-imagine-video-1.5` (RPS) | `grok-voice-3.0` (동시 세션 CST) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Tier 0 | $0 (기본값) | 150 RPS / 50M TPM | 37 RPS / 10M TPM | 9 RPS / 2.5M TPM | 6 RPS | 10 RPS | 10 CST |
| Tier 1 | $50 | 172 RPS / 53M TPM | 50 RPS / 15M TPM | 12 RPS / 3.7M TPM | 12 RPS | 20 RPS | 20 CST |
| Tier 2 | $250 | 208 RPS / 60M TPM | 75 RPS / 25M TPM | 18 RPS / 6.2M TPM | 25 RPS | 39 RPS | 50 CST |
| Tier 3 | $1,000 | 312 RPS / 74M TPM | 125 RPS / 45M TPM | 31 RPS / 11M TPM | 50 RPS | 79 RPS | 100 CST |
| Tier 4 | $5,000 | 500 RPS / 100M TPM | 208 RPS / 85M TPM | 56 RPS / 21M TPM | 100 RPS | 158 RPS | 200 CST |
| Enterprise | 별도 문의 (`sales@x.ai`) | 맞춤형 | 맞춤형 | 맞춤형 | 맞춤형 | 맞춤형 | 맞춤형 |

## 더 X 서브스크립션(The X Subscription): 그록·그록 봇·커서·X 프리미엄 통합

2026년 10월 12일 xAI는 기존의 개별 구독 상품이었던 슈퍼그록(SuperGrok), 커서(Cursor), X 프리미엄(X Premium)을 단일 요금제와 단일 주간 공유 사용량 풀(shared weekly usage pool)로 통합한 '더 X 서브스크립션(The X Subscription)'을 전 세계에 출시했다.[4][5][6] 이 요금제는 그록(Chat, Voice, Imagine, Build), AI 팀원 그록 봇(Grok Bot), 로컬 및 클라우드 코딩 에이전트 커서(Origin 코드 호스팅 및 Bugbot AI 코드 리뷰 포함), 그리고 X 소셜 네트워크 혜택을 하나로 묶어 제공한다.[4][5]

유료 요금제의 공유 사용량 풀은 매주 갱신(weekly refresh)되어 하루 사용량이 많더라도 월간 한도가 한꺼번에 소진되지 않으며, 동급의 기존 커서 단독 요금제 대비 그록 모델 코딩 사용량을 최소 2배 이상(팀 요금제는 구형 Cursor Teams 대비 좌석당 더 낮은 가격에 3배 이상의 코딩 사용량) 제공한다.[4][5] 기존 슈퍼그록·커서·X 프리미엄 가입자는 기존 요금제를 그대로 유지하거나 잔여 기간에 대한 일할 환불(prorated refund, 단 애플 앱스토어 결제 커서 구독은 애플 설정에서 직접 해지 필요)을 받고 더 X 서브스크립션으로 전환할 수 있다.[4][6]

| 요금제 등급 | 월간 요금 | 연간 요금 | 주간 공유 AI 사용량 풀 | 그록·커서·X 주요 포함 혜택 |
| --- | --- | --- | --- | --- |
| Free | $0 / 월 | $0 / 년 | 제한적 (Limited) | 일일 그록 기본 접근, 커서 코딩 에이전트 입문용 한도, 표준 X 기능, 직접 입금(Direct Deposit) 시 X 머니 연 6.00% 이자(APY) 및 3% 캐시백 |
| Plus | $8 / 월 | $80 / 년 ($7/월) | 기본 풀 (Base, 1x) | 그록+커서 공유 풀, 그록 Chat/Voice/Imagine/Build, 그록 API 콘솔 접근, X 인증 체크마크, 타임라인 광고 감소, 크리에이터 도구 (그록 봇 미포함, 팀 요금제 미지원) |
| Premium | $30 / 월 | $300 / 년 ($25/월) | Plus의 4배 (4x) | 그록 봇(Grok Bot) 포함, 최신 그록 모델, 커서 클라우드 에이전트·자동화, Origin 코드 호스팅, Bugbot AI 코드 리뷰, X 대부분 영역 광고 제거, X 머니 6.00% APY (기존 SuperGrok+Cursor Pro+X Premium+ 합산 $90/월 대체) |
| Super | $100 / 월 | $1,000 / 년 ($84/월) | Plus의 15배 (15x) | Premium의 모든 혜택 + 1080p 15초 비디오 생성, 초고속 응답, 피크 시간대 우선 접속권 |
| Ultra | $200 / 월 | $2,000 / 년 ($167/월) | Plus의 50배 (50x) | Super의 모든 혜택 + 파워 유저를 위한 Plus 대비 50배 주간 공유 사용량 |
| Teams | 좌석당 $30~$200 / 월 | 좌석당 $300~$2,000 / 년 | 좌석별 4x ~ 50x | 팀 내 Premium·Super·Ultra 좌석 혼합 구성 가능, 통합 청구·관리, 사용량 분석, SAML/OIDC SSO, SOC 2 준수, 사내 규칙·스킬·플러그인용 팀 마켓플레이스 |

유료 요금제에는 그록 API 접근 권한이 포함되지만, 실제 API 토큰 호출 비용은 구독의 주간 사용량 풀에서 차감되지 않고 표준 API 요율에 따라 별도 과금된다.[5] 또한 커서 내부에서 오픈AI나 앤스로픽 등 서드파티(제3자) 모델을 사용하는 기능은 Premium 이상 등급에서 계속 지원되나, 기본 포함 사용량 풀에 해당하지 않으므로 첫 사용부터 선불 충전(top-ups) 기반의 추가 사용 크레딧(Additional Usage credits)을 통해 API 정가로 별도 과금된다.[4][5][6]

## 자주 묻는 질문

### 그록 4.7(Grok 4.7)의 주요 사양과 API 요금은 어떻게 되나요?

그록 4.7(grok-4.7)은 2026년 하반기 xAI의 최상위 언어·코딩·추론 모델입니다. 50만(500K) 토큰 컨텍스트 윈도, 2026년 5월 지식 기준일, 추론 강도 조절 및 암호화된 추론 콘텐츠(reasoning.encrypted_content) 반환, 파일당 최대 20MiB의 무제한 이미지(JPEG/PNG) 입력을 지원하며, API 요금은 입력 100만 토큰당 2.00달러, 출력 100만 토큰당 6.00달러입니다. [2]

### 2026년 10월 출시된 더 X 서브스크립션(The X Subscription)은 어떤 서비스인가요?

2026년 10월 12일 발표된 더 X 서브스크립션은 그록(Chat, Voice, Imagine 이미지·비디오, Grok Build), AI 팀원 그록 봇(Grok Bot), 코딩 에디터 커서(Cursor, Origin 코드 호스팅 및 Bugbot 코드 리뷰 포함), 그리고 X 프리미엄을 하나의 요금제와 주간 갱신 공유 사용량 풀로 묶은 통합 구독 상품입니다. Free($0), Plus($8/월 또는 $80/년), Premium($30/월 또는 $300/년, Plus의 4배 사용량으로 기존 합산 월 $90 상당의 SuperGrok+Cursor Pro+X Premium+ 대체), Super($100/월, 15배), Ultra($200/월, 50배)로 구성됩니다. [4]

### 더 X 서브스크립션의 공유 사용량 풀로 커서(Cursor) 내의 타사 모델이나 그록 API 토큰 요금도 결제되나요?

아니요. 주간 공유 사용량 풀은 그록 앱, X의 그록 탭, 그록 봇(Premium 이상), 그리고 커서에서 '그록 모델'을 사용할 때만 적용됩니다. Premium·Super·Ultra 요금제 사용자는 커서에서 제3자(서드파티) 모델을 계속 선택할 수 있지만, 첫 사용부터 선불 충전(top-ups) 크레딧을 통해 각 모델의 API 정가로 별도 과금됩니다. 마찬가지로 그록 API 직접 호출 비용도 표준 토큰 요율로 별도 청구됩니다. [6]

### xAI API의 속도 제한 등급(Tier 0~4)은 어떻게 결정되나요?

xAI API는 모델별로 초당 요청 수(RPS, 분당 예산 RPM/48로 산출, 최소 2)와 분당 토큰 수(TPM, 프롬프트·완료·추론·캐시 토큰 모두 합산)를 제한합니다. 등급은 2026년 1월 1일 이후 누적 API 결제액에 따라 Tier 0($0), Tier 1($50), Tier 2($250), Tier 3($1,000), Tier 4($5,000)로 자동 승급되며 한 번 오른 등급은 강등되지 않습니다. 그록 4.7 기준 Tier 0에서는 150 RPS / 5,000만 TPM, Tier 4에서는 500 RPS / 1억 TPM이 제공됩니다. [3]

## 인용 문장

- 2026년 11월 기준 xAI의 플래그십 언어 모델은 그록 4.7(grok-4.7)로, 50만 토큰 컨텍스트 윈도와 2026년 5월 지식 기준일, 리스폰스 API에서의 암호화된 추론 콘텐츠 상시 반환 기능을 갖추었으며 입력 100만 토큰당 2.00달러, 출력 100만 토큰당 6.00달러에 제공된다. [1][2]
- xAI가 아파치 2.0 라이선스로 공개한 오픈웨이트 그록-1(xai-org/grok-1)은 64계층, 계층당 8개 전문가(토큰당 2개 활성), 임베딩 크기 6,144, 최대 시퀀스 길이 8,192토큰 사양의 3,140억 파라미터 MoE 모델이다. [7]
- 2026년 10월 12일 출시된 '더 X 서브스크립션(The X Subscription)'은 그록, 그록 봇, 커서(Cursor), X 프리미엄을 단일 주간 공유 사용량 풀로 통합하여 Free($0), Plus($8/월), Premium($30/월, 4배), Super($100/월, 15배), Ultra($200/월, 50배)의 5단계로 제공한다. [4][5][6]
- xAI API 속도 제한 등급은 2026년 1월 1일 이후 누적 결제액에 따라 영구 승급되며, 그록 4.5·4.6·4.7 기준 Tier 0($0 기본값)의 150 RPS·5,000만 TPM에서 Tier 4($5,000 이상)의 500 RPS·1억 TPM까지 확장된다. [3]
- xAI 멀티모달 API는 실시간 음성 대화(STS 분당 $0.08, TTS 100만 자당 $15.00, STT 배치 시간당 $0.10 및 스트리밍 $0.20), 이매진 이미지 2.0(장당 $0.02부터), 이매진 비디오 1.5(480p·720p·1080p 초당 $0.02부터)를 제공한다. [1][2][3]

## 연표

- 2024-03: xAI가 3,140억 파라미터 오픈웨이트 MoE 모델 그록-1(xai-org/grok-1) 가중치와 JAX 코드를 아파치 2.0 라이선스로 공개. [7]
- 2024-12-12: xAI가 3배 빨라진 그록-2(grok-2-1212)를 X 전체 사용자에게 무료 개방하고 오로라(Aurora) 이미지 모델 출시 및 API 요금($2/$10) 인하를 단행. [8]
- 2026-05: 플래그십 모델 그록 4.7(grok-4.7)의 학습 지식 기준일. [2]
- 2026-10-12: xAI(SpaceX Super Intelligence LLC)가 그록, 그록 봇, 커서, X 프리미엄을 통합한 '더 X 서브스크립션'을 출시. [4]
- 2026-11-13: 그록 4.7, 그록 빌드 0.1, 이매진 이미지 2.0, 이매진 비디오 1.5, 그록 보이스 3.0을 포함한 신규 API 속도 제한 정책을 갱신. [3]

## 출처

1. Grok API Documentation Overview | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). https://docs.x.ai/overview (확인일 2026-11-23; tier 3: official site)
2. Grok Models & Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 게시일 2026-09-21. https://docs.x.ai/developers/models (확인일 2026-11-23; tier 3: official site)
3. Rate Limits | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 게시일 2026-11-13. https://docs.x.ai/developers/rate-limits (확인일 2026-11-23; tier 3: official site)
4. Introducing The X Subscription | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 게시일 2026-10-12. https://x.ai/news/x-subscription (확인일 2026-11-23; tier 3: official site)
5. Pricing: Compare Plans | SpaceXSI. xAI (SpaceX Super Intelligence LLC). https://x.ai/pricing (확인일 2026-11-23; tier 3: official site)
6. The X Subscription Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 게시일 2026-10-11. https://docs.x.ai/x-subscription/pricing (확인일 2026-11-23; tier 3: official site)
7. Grok-1 Open Release Repository and Model Specifications (xai-org/grok-1). xAI. https://raw.githubusercontent.com/xai-org/grok-1/main/README.md (확인일 2026-11-23; tier 3: official site)
8. Bringing Grok to Everyone | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 게시일 2024-12-12. https://x.ai/news/grok-1212 (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "그록 (Grok)." 버전 52a0d3ef, 2026-11-23. https://mimirwiki.com/ko/wiki/grok
