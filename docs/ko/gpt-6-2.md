---
title: "GPT-6.2"
subtitle: "OpenAI가 2026년 11월 출시한 멀티모달 추론 대규모 언어 모델 제품군(GPT-6.2 Astra 및 GPT-6.2 Sol)"
canonical_url: https://mimirwiki.com/ko/wiki/gpt-6-2
language: ko
page_class: entity
revision_sha256: 518b577b4aeb9d903e18c3706aa1e4337c6531a166f3fefaaf8849cbad5c52f3
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 11
alternates:
  md: https://mimirwiki.com/ko/wiki/gpt-6-2.md
  txt: https://mimirwiki.com/ko/wiki/gpt-6-2.txt
  json: https://mimirwiki.com/ko/wiki/gpt-6-2.json
  jsonld: https://mimirwiki.com/ko/wiki/gpt-6-2.jsonld
translations:
  en: https://mimirwiki.com/wiki/gpt-6-2
---

# GPT-6.2

> GPT-6.2는 OpenAI가 2026년 11월 17일 ChatGPT Work, Codex, OpenAI API에 출시한 두 종의 대규모 언어 모델(GPT-6.2 Astra와 GPT-6.2 Sol)이다. 두 모델 모두 텍스트와 이미지 입력을 받아 필수 추론 토큰이 포함된 텍스트를 생성하며, 105만 토큰의 컨텍스트 윈도와 최대 12만 8,000 출력 토큰을 지원한다. 2026-11-23 기준 100만 토큰당 표준 API 요금은 GPT-6.2 Astra가 입력 8.00달러와 출력 40.00달러, GPT-6.2 Sol이 입력 2.00달러와 출력 10.00달러이다.

GPT-6.2는 OpenAI가 2026년 11월 17일 공개한 6세대 멀티모달 대규모 언어 모델(Large Language Model, LLM) 제품군의 판올림 버전으로, GPT-6.2 Astra(`gpt-6.2-astra`)와 GPT-6.2 Sol(`gpt-6.2-sol`) 두 가지 추론 모델로 구성된다. OpenAI는 GPT-6.2 Astra를 고난도 전문 문서 작성, 소프트웨어 개발, 과학 연구, 컴퓨터 사용(computer use)을 위한 플래그십 프런티어 모델로, GPT-6.2 Sol을 일상적인 코딩과 대규모 다단계 에이전트 워크플로를 위한 비용 효율적 모델로 정의한다. 두 모델은 텍스트와 이미지를 입력받아 추론 토큰(reasoning tokens)을 거쳐 텍스트를 출력하며, 105만 토큰의 컨텍스트 윈도(최대 입력 92만 2,000토큰, 최대 출력 12만 8,000토큰)를 제공한다. 2026-11-23 기준 OpenAI API와 Google Cloud 비공개 프리뷰, 그리고 ChatGPT Plus, Pro, Enterprise, Edu 구독자용 ChatGPT Work 및 Codex 프리뷰를 통해 이용할 수 있다.

**다른 이름:** GPT-6.2 Astra, GPT-6.2 Sol, gpt-6.2-astra, gpt-6.2-sol, OpenAI GPT-6.2

## 핵심 정보

- **출시일:** 2026-11-17 [2]
- **모델 구성 및 API ID:** GPT-6.2 Astra (gpt-6.2-astra), GPT-6.2 Sol (gpt-6.2-sol) (기준 2026-11-23) [4]
- **컨텍스트 윈도:** 1,050,000토큰(최대 입력 922,000토큰, 최대 출력 128,000토큰) (기준 2026-11-23) [4]
- **GPT-6.2 Astra 표준 API 가격:** 100만 토큰당 입력 $8.00, 캐시 읽기 $0.40, 출력 $40.00(입력 272K 이하) (기준 2026-11-23) [6]
- **GPT-6.2 Sol 표준 API 가격:** 100만 토큰당 입력 $2.00, 캐시 읽기 $0.10, 출력 $10.00(입력 272K 이하) (기준 2026-11-23) [6]

## 기본 정보

- **개발사:** OpenAI [1]
- **출시일:** 2026-11-17 [2]
- **모델 구성 및 API 식별자:** GPT-6.2 Astra (gpt-6.2-astra), GPT-6.2 Sol (gpt-6.2-sol) (기준 2026-11-23) [4]
- **이전 세대 모델:** GPT-6 Astra, GPT-6.1 Sol [1]
- **입출력 모달리티:** 텍스트·이미지 입력, 텍스트 출력(오디오·비디오 미지원) (기준 2026-11-23) [4]
- **컨텍스트 윈도 및 토큰 한도:** 1,050,000토큰(최대 입력 922,000토큰, 최대 출력 128,000토큰) (기준 2026-11-23) [4]
- **지식 기준일:** 2026-05-18(GPT-6.2 Astra); 2026-06-01(GPT-6.2 Sol) (기준 2026-11-23) [4]
- **표준 API 요금(272K 이하):** 100만 토큰당 Astra: 입력 $8.00 / 캐시 $0.40 / 출력 $40.00; Sol: 입력 $2.00 / 캐시 $0.10 / 출력 $10.00 (기준 2026-11-23) [6]
- **지원 API 엔드포인트:** v1/responses, v1/chat/completions, v1/batch (기준 2026-11-23) [4]
- **ChatGPT 및 클라우드 제공:** ChatGPT Work 및 Codex(Plus, Pro, Enterprise, Edu); Google Cloud(비공개 프리뷰) (기준 2026-11-23) [3]
- **대비 프레임워크 등급:** 사이버보안: Critical(공통); 생물·화학: High(공통); AI 자기 개선: High(Astra 단독) (기준 2026-11-22) [8]

## GPT-6.2 개요, 출시 연혁 및 모델 체계

GPT-6.2는 [OpenAI](https://mimirwiki.com/ko/wiki/openai)가 개발한 6세대 대규모 언어 모델(GPT-6 계열)의 주요 릴리스로, 2026년 11월 17일 GPT-6.2 Astra와 GPT-6.2 Sol 두 가지 모델로 출시되었다.[1][2] 2026-11-23 기준 OpenAI API 모델 카탈로그에서 GPT-6 계열은 천체 명칭을 따라 등급을 구분한다. 최고 성능 추론용 Astra, 일상 코딩과 에이전트 작업용 Sol, 시각 추론·컴퓨터 사용·문장 작성용 Terra(`gpt-6.1-terra`, 2026년 10월 26일 출시), 대량·저비용 처리용 Luna(`gpt-6-luna`, 2026년 9월 22일 출시)와 함께 특화 모델인 GPT-6 Cyber 및 생명과학 연구용 GPT-6 Rosalind Research(2026년 10월 30일 출시)가 운영되고 있다.[2][9][11]

GPT-6.2 Astra는 GPT-6 Astra의 후속 모델이며, GPT-6.2 Sol은 GPT-6.1 Sol(2026년 9월 29일 출시)과 GPT-6 Sol(2026년 9월 22일 출시)의 후속 모델이다.[1][9][11] OpenAI의 출시 발표문과 API 문서에 따르면 GPT-6.2 Astra는 소프트웨어 제작 및 수정, 과학 연구, 법률·재무 분석 문서와 슬라이드·스프레드시트 작성, 정밀 컴퓨터 사용(CAD 및 3D 시뮬레이션 포함), 프런트엔드 웹·게임 디자인 같은 고난도 프로젝트를 겨냥하며, GPT-6.2 Sol은 속도와 비용 효율을 결합해 다단계 에이전트 워크플로와 일상 기술·비기술 업무를 처리하는 모델로 많은 OpenAI 임직원이 기본 모델로 사용하고 있다.[1][4][5]

OpenAI는 2026년 11월 17일 두 모델을 OpenAI API와 [ChatGPT](https://mimirwiki.com/ko/wiki/chatgpt) Work, Codex 데스크톱에 동시 배포했다.[1][2][3] ChatGPT에서는 Plus, Pro, Enterprise, Edu 사용자가 Work 모델 선택기나 Codex 모델 선택기에서 두 모델을 프리뷰로 선택할 수 있으며, 일반 ChatGPT 채팅(Chat) 탭은 기존 모델 구성을 그대로 유지한다.[1][3][10]

## GPT-6.2 기술 사양과 Responses API 아키텍처

2026-11-23 기준 OpenAI 개발자 문서에 따르면 GPT-6.2 Astra(`gpt-6.2-astra`)와 GPT-6.2 Sol(`gpt-6.2-sol`)은 모두 텍스트와 이미지를 입력으로 받아 텍스트를 출력하며, 오디오 및 비디오 입출력, 미세 조정(fine-tuning), 예측 출력(predicted outputs)은 지원하지 않는다.[4][5] 두 모델의 컨텍스트 윈도는 각각 1,050,000토큰이며 요청당 최대 922,000 입력 토큰과 최대 128,000 출력 토큰을 처리할 수 있다.[4][5] 공식 지식 기준일(knowledge cutoff)은 GPT-6.2 Astra가 2026년 5월 18일, GPT-6.2 Sol이 2026년 6월 1일이다.[4][5]

| 사양 항목 | GPT-6.2 Astra (`gpt-6.2-astra`) | GPT-6.2 Sol (`gpt-6.2-sol`) |
| --- | --- | --- |
| 주요 용도 | 고난도 추론, 소프트웨어 개발, 과학 및 전문 문서 작업용 프런티어 모델 | 일상 코딩 및 대규모 다단계 에이전트 워크플로용 균형 모델 |
| 직전 세대 모델 | GPT-6 Astra (`gpt-6-astra`) | GPT-6.1 Sol (`gpt-6.1-sol`) |
| 입출력 모달리티 | 텍스트·이미지 입력, 텍스트 출력 | 텍스트·이미지 입력, 텍스트 출력 |
| 컨텍스트 윈도 | 1,050,000토큰(최대 입력 922,000, 최대 출력 128,000) | 1,050,000토큰(최대 입력 922,000, 최대 출력 128,000) |
| 지식 기준일 | 2026년 5월 18일 | 2026년 6월 1일 |
| 지원 API 엔드포인트 | `v1/responses`, `v1/chat/completions`, `v1/batch` | `v1/responses`, `v1/chat/completions`, `v1/batch` |
| 외부 클라우드 등록 | Google Cloud(비공개 프리뷰) | Google Cloud(비공개 프리뷰) |

두 모델은 모두 추론 토큰(reasoning tokens)을 지원하며, 추론 강도(`reasoning.effort`)를 `none`으로 설정한 API 요청을 거부한다.[4][5] 공통 지원 기능으로는 스트리밍, 구조화된 출력(`structured_outputs`), 함수 호출(`function_calling`), 파일 검색, 이미지 입력, 웹 검색, 프롬프트 캐싱이 있다.[4][5] Responses API(`v1/responses`)를 사용할 경우 `web_search`, `file_search`, `image_generation`, `code_interpreter`, `hosted_shell`, `apply_patch`, `skills`, `computer_use`, [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(`mcp`), `tool_search` 등 10종의 내장 도구와 다중 에이전트 베타(Multi-agent beta) 기반의 서브에이전트 위임을 사용할 수 있다.[4][5]

OpenAI의 'Using GPT-6.2' 가이드는 GPT-6.2부터 적용되는 Responses API의 세 가지 주요 기술 변경 사항을 안내한다.[7]

- 프리픽스 편집(Prefix edits) 시 추론 항목 삭제: 대화 중간에 이전 개발자 메시지나 도구 호출 내역을 수정하거나 모델을 하향 변경할 경우, 또는 최종 사용자나 조직이 바뀔 경우 Responses API가 이전 추론 항목을 폐기한다. 추론 맥락과 프롬프트 캐싱을 유지하려면 이전 프리픽스를 변경하지 않아야 한다.[7]
- 최상위 `instructions` 필드 배치 순서 변경: GPT-6.2부터는 Responses API의 최상위 `instructions`가 `input` 뒤에 추가된다. 따라서 반복 재사용하는 지침에 프롬프트 캐싱을 적용하려면 지침을 `input` 배열의 첫 번째 `developer` 메시지로 넣어야 한다.[7]
- 백그라운드 완료 윈도(공개 베타): 두 모델은 기존의 Flex 처리(`service_tier: flex`)를 지원하지 않는 대신, 장기 실행 요청을 위해 2시간 또는 8시간 완료 윈도를 제공하는 할인 백그라운드 모드를 지원한다.[4][5][7]

## GPT-6.2 API 가격, 처리 등급 및 속도 제한

OpenAI는 GPT-6.2 API 요금을 100만 토큰당 미국 달러 기준으로 산정하며, 입력 토큰 272,000개 이하인 짧은 컨텍스트(short context)와 272,000개를 초과하는 긴 컨텍스트(long context)로 구간을 나눈다. 입력이 272,000토큰을 넘으면 요청 전체에 대해 입력 및 캐시 요금이 2배, 출력 요금이 1.5배로 부과된다.[4][5][6] GPT-6.2 Astra는 이전 세대인 GPT-6 Astra(100만 토큰당 입력 10.00달러, 캐시 읽기 1.00달러, 출력 50.00달러) 대비 표준 입출력 요금을 20%, 캐시 읽기 요금을 60% 낮추었으며, GPT-6.2 Sol은 GPT-6.1 Sol과 동일한 요율을 유지한다.[1][6]

| 모델 및 처리 등급 (2026-11-23 기준) | 짧은 컨텍스트 입력 (<=272K) | 짧은 컨텍스트 출력 (<=272K) | 짧은 컨텍스트 캐시 읽기 | 짧은 컨텍스트 캐시 쓰기 (30분 / 12시간) | 긴 컨텍스트 입력 (>272K) | 긴 컨텍스트 출력 (>272K) |
| --- | --- | --- | --- | --- | --- | --- |
| GPT-6.2 Astra (Standard) | $8.00 / 1M | $40.00 / 1M | $0.40 / 1M | $10.00 / $20.00 | $16.00 / 1M | $60.00 / 1M |
| GPT-6.2 Astra (Batch, 표준의 50%) | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Astra (Fast, 표준의 2배) | $16.00 / 1M | $80.00 / 1M | $0.80 / 1M | $20.00 / $40.00 | $32.00 / 1M | $120.00 / 1M |
| GPT-6.2 Astra (Ultrafast 프로모션, 2027-02-28까지 3배) | $24.00 / 1M | $120.00 / 1M | $1.20 / 1M | $30.00 / $60.00 | $48.00 / 1M | $180.00 / 1M |
| GPT-6.2 Sol (Standard) | $2.00 / 1M | $10.00 / 1M | $0.10 / 1M | $2.50 / $5.00 | $4.00 / 1M | $15.00 / 1M |
| GPT-6.2 Sol (Batch, 표준의 50%) | $1.00 / 1M | $5.00 / 1M | $0.05 / 1M | $1.25 / $2.50 | $2.00 / 1M | $7.50 / 1M |
| GPT-6.2 Sol (Fast, 표준의 2배) | $4.00 / 1M | $20.00 / 1M | $0.20 / 1M | $5.00 / $10.00 | $8.00 / 1M | $30.00 / 1M |
| GPT-6.2 Sol (Ultrafast 프로모션, 2027-02-28까지 3배) | $6.00 / 1M | $30.00 / 1M | $0.30 / 1M | $7.50 / $15.00 | $12.00 / 1M | $45.00 / 1M |

Standard, Batch(50% 할인), Fast(표준의 2배) 등급 외에 초고속 처리 등급인 Ultrafast는 태평양 표준시 기준 2027년 2월 28일까지 표준 요금의 3배로 제공되며, 2027년 3월 1일부터는 표준 요금의 6배가 적용된다.[4][5][6] 2026-11-23 기준 두 모델의 표준 API 속도 제한(rate limits)은 Build 등급에서 분당 요청 5,000건(RPM) 및 분당 토큰 1,000,000개(TPM), Launch 등급에서 10,000 RPM 및 4,000,000 TPM, Grow 등급에서 15,000 RPM 및 40,000,000 TPM으로 동일하다.[4][5]

## GPT-6.2 벤치마크 평가와 초기 사용자 반응

OpenAI는 2026년 11월 17일 발표문에서 GPT-6.2 Astra와 GPT-6.2 Sol이 출력 토큰 사용량을 줄이면서도 전문 지식 업무, 과학, 코딩 벤치마크에서 직전 세대보다 높은 점수를 기록했다고 발표했다.[1][2]

- Agents' Last Exam(장기 다단계 전문 업무): OpenAI 발표에 따르면 GPT-6.2 Astra는 GPT-6 Astra보다 3분의 1 미만의 비용으로 5.2점 높은 점수를 기록했으며, 폴백(fallback) 모델을 사용한 9개 과제를 제외한 [Claude Fable 5.2](https://mimirwiki.com/ko/wiki/claude-fable-5-2)와 비교해 5%의 비용으로 5.5점 앞섰다.[1]
- Terminal-Bench-Science 0.1 및 Vals Science Index v1: GPT-6.2 Astra는 터미널 기반 과학 연구를 평가하는 Terminal-Bench-Science 0.1에서 GPT-6 Astra 대비 3분의 1 미만의 비용으로 9%포인트 상승했으며, 생물학 데이터 해석과 실험 추론을 평가하는 Vals Science Index v1에서도 최고점을 경신했다.[1]
- 법률 및 재무 분석: 법률 과제를 평가하는 Harvey LAB-AA v1.1에서 GPT-6.2 Astra는 약 6분의 1 비용으로 Claude Fable 5.2의 통과율을 2배 이상 상회했으며 법률 특화 구성인 Astra for Law는 더 높은 점수를 기록했다. 또한 실제 스프레드시트와 보고서를 다루는 Artificial Analysis의 AA-AnalystAgent에서 5회 독립 시도 모두 정답을 맞힌 문항 비율 62.5%로 최고치를 기록했다.[1]
- GDPval v2(OpenAI 내부 장기 지식 업무 벤치마크): GPT-6.2 Astra는 출력 토큰을 22% 덜 쓰면서 GPT-6 Astra보다 6.2%포인트 향상되었고, GPT-6.2 Sol은 GPT-6.1 Sol보다 5.3점 상승했다.[1]
- FrontierCode 2.0 및 LifeVal: 최대 추론 강도로 실행한 Cognition의 FrontierCode 2.0에서 GPT-6.2 Sol은 약 5분의 1 비용으로 GPT-6.2 Astra와 0.5점 이내의 성적을 냈고, 일상 과제 벤치마크인 LifeVal에서는 약 7분의 1 비용으로 GPT-6 Astra를 앞섰다.[1]

반면 2026년 11월 17일 VentureBeat 보도에 따르면 사전 테스터와 파워 유저들의 초기 반응은 엇갈렸다.[10] OpenAI 발표문에 인용된 기업 고객(IMC, Legora, Harvey, ClickUp 소속 엔지니어 및 임원)은 법률 및 업무용 에이전트 평가에서 토큰 사용량이 34.5%~62% 줄었다고 평가했고, Raindrop.ai CTO Ben Hylak과 Ashe Magalhaes는 애니메이션, 모션 그래픽, 시각 효과(VFX), 에이전트형 비디오 편집 성능을 긍정적으로 평가했다.[1][10] 그러나 개발자 Theo Browne, 투자자 Matt Shumer, Every CEO Dan Shipper, 와튼스쿨 교수 Ethan Mollick 등은 GPT-6.2 Astra가 장기 자율 빌드 작업 도중 일찍 멈추거나, 지나치게 간결한 기본 문체로 필요한 설명을 생략하며, 서로 다른 게임 레벨 디자인 요청에 똑같이 'Bellwether'라는 이름의 물과 종 테마 레벨을 생성하는 등 고정된 하우스 스타일(house style)이 강하다고 지적했다.[10]

## GPT-6.2 시스템 카드, 대비 프레임워크 등급 및 안전성 평가

OpenAI는 출시 당일인 2026년 11월 17일 GPT-6.2 시스템 카드(System Card)를 공개했으며, 2026년 11월 22일 변경 로그(Change log)를 통해 `OAI-repo Sabotage v2` 섹션의 L2 모니터 분류 기준(`P0`는 즉각 보안팀 검토, `P0.5`는 업무 시간 내 우선 후속 조치)을 명확히 기술했다.[8] OpenAI 대비 프레임워크(Preparedness Framework) 평가 결과, GPT-6.2 Astra와 GPT-6.2 Sol은 모두 사이버보안(Cybersecurity) 역량에서 Critical(치명적) 임계치에, 생물 및 화학(Biological and Chemical) 역량에서 High(높음) 임계치에 도달했다.[8] 두 모델 모두 알려진 소프트웨어 취약점으로부터 실제 작동하는 익스플로잇(exploit)을 개발하는 능력이 GPT-6 Astra 및 GPT-6.1 Sol보다 향상됨에 따라, OpenAI는 고위험 사이버보안 지원에 대한 기본 제한을 강화하고 허용적 접근에 추가 심사를 의무화했다.[8]

또한 GPT-6.2 Astra는 OpenAI가 외부에 배포한 모델 가운데 최초로 AI 자기 개선(AI Self-Improvement) 역량에서 High 임계치에 도달한 모델로 기록되었으며, GPT-6.2 Sol은 해당 임계치 아래로 평가되었다.[8] OpenAI는 이 High 임계치를 향후 완전 자동화된 재귀적 자기 개선이 가능한 모델에 대비해 안전장치를 선제적으로 준비하는 초기 이정표로 정의하고, Codex 내부에 GPT-6.2 Astra 배포를 확대하기 전 단계별 정렬 검증, 연구 환경 격리 강화, 프런티어 에이전트 모니터링 확대를 시행했다고 밝혔다.[8]

GPT-6.2 시스템 카드에는 이 밖에도 간접 프롬프트 인젝션 방어, 환각(hallucinations), 의료 벤치마크(HealthBench Professional, MentalHealthBench), 허니팟 및 기만 행위 평가(ExploitGym Honeypot, Blocker Deception, Broken Search Tool), 직장 업무 시뮬레이션, 의도치 않은 에이전트 간 통신, 연쇄 사고 제어(`CoT-Control`), `OAI-repo Sabotage v2`, `Sneaky Sandbox Escape`, 그리고 외부 기관인 SecureBio 및 영국 AI 안전 연구소(UK AISI)의 독립 평가 항목이 수록되어 있다.[8]

## 자주 묻는 질문

### GPT-6.2는 무엇이며 GPT-6.2 Astra와 GPT-6.2 Sol은 어떻게 다른가요?

GPT-6.2는 OpenAI가 2026년 11월 17일 출시한 멀티모달 추론 언어 모델 제품군으로, 두 가지 모델로 구성됩니다. GPT-6.2 Astra(`gpt-6.2-astra`)는 고난도 추론, 소프트웨어 엔지니어링, 과학 연구, 전문 문서 및 프런트엔드 제작을 위한 플래그십 프런티어 모델이며, GPT-6.2 Sol(`gpt-6.2-sol`)은 일상적인 코딩과 대규모 다단계 에이전트 워크플로를 위해 속도와 비용 효율을 높인 모델입니다. 두 모델 모두 105만 토큰의 컨텍스트 윈도를 지원합니다. [1][2][4][5]

### OpenAI API에서 GPT-6.2 Astra와 GPT-6.2 Sol의 가격은 얼마인가요?

2026-11-23 기준 짧은 컨텍스트(입력 27만 2,000토큰 이하) 요청의 100만 토큰당 표준 API 요금은 GPT-6.2 Astra가 입력 8.00달러, 캐시 읽기 0.40달러, 30분 캐시 쓰기 10.00달러(12시간 20.00달러), 출력 40.00달러이며, GPT-6.2 Sol이 입력 2.00달러, 캐시 읽기 0.10달러, 30분 캐시 쓰기 2.50달러(12시간 5.00달러), 출력 10.00달러입니다. 입력이 27만 2,000토큰을 초과하는 긴 컨텍스트 요청에는 요청 전체에 대해 입력 및 캐시 요금이 2배, 출력 요금이 1.5배로 적용됩니다. [4][5][6]

### GPT-6.2의 컨텍스트 윈도, 최대 출력, 지식 기준일은 어떻게 되나요?

두 모델 모두 105만 토큰(1,050,000토큰)의 컨텍스트 윈도를 제공하며 요청당 최대 입력은 92만 2,000토큰, 최대 출력은 12만 8,000토큰입니다. 지식 기준일(knowledge cutoff)은 GPT-6.2 Astra가 2026년 5월 18일, GPT-6.2 Sol이 2026년 6월 1일입니다. 입력은 텍스트와 이미지를, 출력은 텍스트를 지원하며 오디오, 비디오, 미세 조정(fine-tuning), 예측 출력(predicted outputs)은 지원하지 않습니다. [4][5]

### 사용자와 개발자는 어디에서 GPT-6.2 Astra와 GPT-6.2 Sol을 이용할 수 있나요?

2026-11-23 기준 GPT-6.2 Astra와 GPT-6.2 Sol은 ChatGPT Plus, Pro, Enterprise, Edu 구독자를 대상으로 ChatGPT Work와 Codex 데스크톱 앱에서 프리뷰로 제공되며, 일반 ChatGPT 채팅(Chat) 탭은 기존 모델 선택지를 유지합니다. 개발자는 OpenAI API(`v1/responses`, `v1/chat/completions`, `v1/batch`)에서 두 모델을 호출할 수 있으며, Google Cloud에서도 비공개 프리뷰(private preview)로 등록되어 있습니다. [1][3][4][5][10]

### GPT-6.2 Astra와 Sol은 OpenAI 대비 프레임워크에서 어떤 안전 등급을 받았나요?

2026년 11월 17일 공개되고 11월 22일 갱신된 GPT-6.2 시스템 카드에 따르면, 두 모델은 모두 OpenAI 대비 프레임워크(Preparedness Framework)에서 사이버보안 역량 Critical(치명적) 등급과 생물·화학 역량 High(높음) 등급에 도달했습니다. 또한 GPT-6.2 Astra는 외부에 배포된 OpenAI 모델 가운데 최초로 AI 자기 개선(AI Self-Improvement) 부문 High 등급에 도달했으며, GPT-6.2 Sol은 해당 임계치 미만에 머물렀습니다. [8]

## 인용 문장

- OpenAI는 2026년 11월 17일 ChatGPT Work, Codex, OpenAI API를 통해 GPT-6.2 Astra(gpt-6.2-astra)와 GPT-6.2 Sol(gpt-6.2-sol)을 출시했다. [1][2][3]
- GPT-6.2 Astra와 GPT-6.2 Sol은 각각 105만 토큰의 컨텍스트 윈도(최대 입력 92만 2,000토큰, 최대 출력 12만 8,000토큰)를 지원하며 텍스트와 이미지 입력을 받아 추론 토큰이 포함된 텍스트를 출력한다. [4][5]
- 공식 문서에 기재된 지식 기준일(knowledge cutoff)은 GPT-6.2 Astra가 2026년 5월 18일, GPT-6.2 Sol이 2026년 6월 1일이다. [4][5]
- 2026-11-23 기준 27만 2,000 입력 토큰 이하 요청에 대한 GPT-6.2 Astra의 표준 OpenAI API 가격은 100만 토큰당 입력 8.00달러, 캐시 읽기 0.40달러, 30분 캐시 쓰기 10.00달러, 출력 40.00달러이다. [4][6]
- 2026-11-23 기준 27만 2,000 입력 토큰 이하 요청에 대한 GPT-6.2 Sol의 표준 OpenAI API 가격은 100만 토큰당 입력 2.00달러, 캐시 읽기 0.10달러, 30분 캐시 쓰기 2.50달러, 출력 10.00달러이다. [5][6]
- GPT-6.2 Astra는 이전 세대인 GPT-6 Astra(100만 토큰당 입력 10.00달러, 캐시 읽기 1.00달러, 출력 50.00달러)와 비교해 표준 입출력 토큰 단가를 20%, 캐시 읽기 단가를 60% 인하했다. [1][6]
- OpenAI 대비 프레임워크(Preparedness Framework)에 따른 GPT-6.2 시스템 카드는 두 모델 모두를 사이버보안 Critical 및 생물·화학 High 등급으로 분류하며, GPT-6.2 Astra를 외부에 출시된 OpenAI 모델 중 최초로 AI 자기 개선(AI Self-Improvement) High 등급에 도달한 모델로 명시한다. [8]
- 두 GPT-6.2 모델은 추론 강도(reasoning effort)를 none으로 설정한 API 요청을 거부하고 Flex 처리(service_tier: flex)를 지원하지 않으며, Responses API에서 2시간 및 8시간 완료 윈도 기반의 할인 백그라운드 모드를 지원한다. [4][5][7]

## 연표

- 2026-09-22: OpenAI가 GPT-6 Astra 출시에 이어 GPT-6 Sol과 GPT-6 Luna로 GPT-6 제품군을 확장했다. [9]
- 2026-09-29: OpenAI가 GPT-6.1 Sol을 출시했다. [9]
- 2026-10-26: OpenAI가 OpenAI API, ChatGPT Work, Codex에 GPT-6.1 Terra를 출시했다. [2]
- 2026-11-17: OpenAI가 ChatGPT Work, Codex, OpenAI API에 GPT-6.2 Astra와 GPT-6.2 Sol을 출시하고 GPT-6.2 시스템 카드를 공개했다. [1][2][3][8]
- 2026-11-22: OpenAI가 GPT-6.2 시스템 카드의 변경 로그를 갱신해 OAI-repo Sabotage v2 평가의 L2 모니터 우선순위 분류(P0 및 P0.5) 기준을 명확히 했다. [8]
- 2027-03-01: GPT-6.2 Astra와 GPT-6.2 Sol의 Ultrafast 처리 등급 요금이 표준 요금의 3배에서 6배로 인상될 예정이다. [4][5][6]

## 출처

1. Introducing GPT-6.2 Astra and Sol | OpenAI. OpenAI. 게시일 2026-11-17. https://openai.com/index/introducing-gpt-6-2-astra-sol/ (확인일 2026-11-23; tier 3: official site)
2. Model Release Notes | OpenAI Help Center. OpenAI Help Center. 게시일 2026-11-17. https://help.openai.com/en/articles/9624314-model-release-notes (확인일 2026-11-23; tier 3: official site)
3. ChatGPT release notes | OpenAI Help Center. OpenAI Help Center. 게시일 2026-11-20. https://help.openai.com/en/articles/6825453-chatgpt-release-notes (확인일 2026-11-23; tier 3: official site)
4. GPT-6.2 Astra - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-astra (확인일 2026-11-23; tier 3: official site)
5. GPT-6.2 Sol - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models/gpt-6.2-sol (확인일 2026-11-23; tier 3: official site)
6. Pricing - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/pricing (확인일 2026-11-23; tier 3: official site)
7. Using GPT-6.2 - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/guides/latest-model (확인일 2026-11-23; tier 3: official site)
8. GPT-6.2 System Card - OpenAI Deployment Safety Hub. OpenAI Deployment Safety Hub. 게시일 2026-11-17. https://deploymentsafety.openai.com/gpt-6-2-astra-sol (확인일 2026-11-23; tier 3: official site)
9. GPT-6 Astra: A new generation of intelligence | OpenAI. OpenAI. https://openai.com/index/gpt-6-astra/ (확인일 2026-11-23; tier 3: official site)
10. 'Essentially unusable': OpenAI launches GPT-6.2 Astra and Sol to negative reception from AI power users | VentureBeat. VentureBeat. 게시일 2026-11-17. https://venturebeat.com/technology/essentially-unusable-openai-launches-gpt-6-2-astra-and-sol-to-negative-reception-from-ai-power-users (확인일 2026-11-23; tier 2: academic or news)
11. Models - OpenAI API Documentation. OpenAI. https://developers.openai.com/api/docs/models (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "GPT-6.2." 버전 518b577b, 2026-11-23. https://mimirwiki.com/ko/wiki/gpt-6-2
