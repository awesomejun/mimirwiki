---
title: "Gemini 4 Neon"
subtitle: "Google DeepMind가 2026년 11월 출시한 소프트웨어 개발·과학·엔터프라이즈용 멀티모달 추론 언어 모델"
canonical_url: https://mimirwiki.com/ko/wiki/gemini-4-neon
language: ko
page_class: entity
revision_sha256: ab3d57a16bb5315ce17a1bf029a663e94674f542de70f195bfbf37291591ac92
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ko/wiki/gemini-4-neon.md
  txt: https://mimirwiki.com/ko/wiki/gemini-4-neon.txt
  json: https://mimirwiki.com/ko/wiki/gemini-4-neon.json
  jsonld: https://mimirwiki.com/ko/wiki/gemini-4-neon.jsonld
translations:
  en: https://mimirwiki.com/wiki/gemini-4-neon
  ja: https://mimirwiki.com/ja/wiki/gemini-4-neon
  zh: https://mimirwiki.com/zh/wiki/gemini-4-neon
---

# Gemini 4 Neon

> Gemini 4 Neon(`gemini-4-neon`)은 Google DeepMind가 2026년 11월 18일 출시한 멀티모달 추론 대규모 언어 모델이다. Gemini 4 Carbon을 기반으로 조정되었으며 텍스트, 이미지, 오디오, 비디오, PDF를 아우르는 100만 토큰 통합 컨텍스트 윈도와 최대 6만 4,000 동기 출력 토큰(백그라운드 롱 디코드 시 최대 100만 토큰), 2026년 3월 지식 기준 시점을 갖추고 있다. 2026-11-23 기준 표준 API 요금은 100만 토큰당 입력 3.00달러, 캐시 읽기 0.15달러, 출력 15.00달러이다.

Gemini 4 Neon은 Google DeepMind가 개발해 2026년 11월 18일 출시한 4세대 멀티모달 추론 대규모 언어 모델(Large Language Model, LLM)로, Gemini 4 Carbon, Gemini 4 Hydrogen, Gemini 4 Argon과 함께 Gemini 4 제품군을 구성한다. 최상위 모델인 Gemini 4 Carbon을 기반으로 조정(adaptation)된 Gemini 4 Neon(`gemini-4-neon`)은 소프트웨어 엔지니어링, 과학 연구, 사이버보안 방어, 엔터프라이즈 지식 업무 전반에서 프런티어 수준의 추론 깊이와 빠른 종단간(end-to-end) 실행 속도 및 비용 효율을 결합하도록 설계되었다. 텍스트, 이미지, 오디오, 비디오, PDF 입력을 수용하는 100만 토큰 통합 컨텍스트 윈도를 지원하며, 기본 동기 출력으로 최대 6만 4,000토큰, 백그라운드 롱 디코드(background long decode)로 최대 100만 출력 토큰을 생성한다. 2026-11-23 기준 Google AI Studio의 Gemini API, Google Cloud Model Garden, Gemini for business와 함께 Google AI Pro 및 Ultra 구독자용 Gemini 앱과 Google Antigravity에서 제공된다.

**다른 이름:** 제미나이 4 네온, gemini-4-neon, Google Gemini 4 Neon, Gemini 4.0 Neon

## 핵심 정보

- **출시일:** 2026-11-18(Google DeepMind 수석부사장 Koray Kavukcuoglu 발표) [1]
- **API 모델 코드 및 계보:** gemini-4-neon(Gemini 4 Carbon에서 조정) (기준 2026-11-23) [2]
- **컨텍스트 윈도 및 최대 출력:** 통합 100만 토큰(기본 동기 출력 64K 토큰; 백그라운드 롱 디코드 최대 100만 토큰) (기준 2026-11-23) [2]
- **표준 API 가격:** 100만 토큰당 입력 $3.00, 캐시 읽기 $0.15(95% 할인), 출력 $15.00 (기준 2026-11-23) [4]
- **지식 기준 시점:** 2026년 3월 (기준 2026-11-23) [2]

## 기본 정보

- **개발사:** Google DeepMind (Alphabet Inc.) [2]
- **출시일:** 2026-11-18 [1]
- **API 모델 코드:** gemini-4-neon (기준 2026-11-23) [3]
- **기반 모델 및 계열:** Gemini 4 Carbon에서 조정(Gemini 4 계열: Carbon, Neon, Hydrogen, Argon) [2]
- **지원 모달리티:** 텍스트, 이미지, 오디오, 비디오, PDF 입력; 텍스트 출력 (기준 2026-11-23) [3]
- **컨텍스트 윈도 및 최대 출력:** 통합 1,000,000토큰; 동기 출력 최대 64,000토큰 / 백그라운드 롱 디코드 최대 1,000,000토큰 (기준 2026-11-23) [2]
- **지식 기준 시점:** 2026년 3월 (기준 2026-11-23) [2]
- **표준 API 가격(글로벌):** 100만 토큰당 입력 $3.00 / 캐시 읽기 $0.15 / 출력(추론 토큰 포함) $15.00 (기준 2026-11-23) [4]
- **클라우드 Priority 및 Batch 가격:** 100만 토큰당 Priority 글로벌: 입력 $5.40 / 캐시 $0.27 / 출력 $27.00; Batch 글로벌: 입력 $1.50 / 캐시 $0.075 / 출력 $7.50 (기준 2026-11-23) [5]
- **제공 채널:** Gemini 앱, Gemini API, Google AI Studio, Gemini for business(Model Garden), Google Antigravity (기준 2026-11-23) [2]
- **포함된 소비자 요금제:** Google AI Pro(5 TB) 및 Google AI Ultra(20 TB 이상, AI Pro 대비 5배 한도) (기준 2026-11-23) [8]

## Gemini 4 Neon 개요, 출시 배경 및 Gemini 4 제품군 내 위치

Gemini 4 Neon은 Google DeepMind가 개발해 2026년 11월 18일 공개한 멀티모달 추론 대규모 언어 모델로, Google DeepMind 수석부사장(SVP) 겸 Google 수석 AI 아키텍트인 Koray Kavukcuoglu가 공식 출시를 발표했다.[1][2] 2026-11-23 기준 Google AI Studio 문서에 등재된 [Google Gemini](https://mimirwiki.com/ko/wiki/google-gemini) 4세대(Gemini 4) 모델 라인업은 원소 이름을 딴 네 가지 모델인 Gemini 4 Carbon(`gemini-4-carbon`), Gemini 4 Neon(`gemini-4-neon`), Gemini 4 Hydrogen(`gemini-4-hydrogen`), Gemini 4 Argon(`gemini-4-argon`)으로 구성된다.[3]

2026년 11월 18일 발행된 Google DeepMind 모델 카드에 따르면 Gemini 4 Neon은 플래그십 모델인 Gemini 4 Carbon으로부터 조정(adapted)되었으며, 모델 아키텍처, 학습 데이터셋, 데이터 전처리 과정, 하드웨어 및 소프트웨어 인프라를 Carbon과 공유한다.[2] Google은 가장 복잡하고 호흡이 긴 프로젝트에는 Gemini 4 Carbon을, 빠른 일상 실행에는 Gemini 4 Hydrogen을 배치하는 한편, Gemini 4 Neon을 프런티어급 추론 깊이와 빠른 종단간(end-to-end) 실행 속도 및 비용 효율을 겸비한 중간 프런티어 계층으로 정의한다. 이에 따라 Gemini 4 Neon은 단독 에이전트로 동작하거나 Google Antigravity 내에서 병렬 실행되는 여러 Hydrogen 서브에이전트를 지휘하는 오케스트레이터(Orchestrator)로 활용된다.[1][2]

2026-11-23 기준 Gemini 4 Neon은 Gemini 앱, Gemini Developer API, Google AI Studio, Gemini for business(Google Cloud Model Garden 포함), 에이전트형 개발 플랫폼인 Google Antigravity의 5개 공식 채널을 통해 배포된다.[1][2] 일반 및 전문가용 구독 서비스인 Google One에서는 Google AI Pro 요금제(5 TB 클라우드 스토리지, 월 200 Google Colab 컴퓨트 유닛, 월 10달러 Google Cloud 크레딧 포함)와 Google AI Ultra 요금제(20 TB 이상 스토리지, Gemini 4 Carbon 추가, AI Pro 대비 5배 높은 Gemini 사용 한도, 월 2,000 Colab 컴퓨트 유닛 및 월 40달러 Google Cloud 크레딧 포함) 가입자에게 Gemini 앱, Google Antigravity, Google AI Studio 내 Gemini 4 Neon 접근 권한을 제공하며, 기본 유료 등급인 Google AI Plus(400 GB 스토리지)에는 Gemini 4 Hydrogen이 포함된다.[8]

## Gemini 4 Neon 기술 사양, 멀티모달 입출력 및 롱 디코드 아키텍처

2026-11-23 기준 Gemini API 문서와 Google DeepMind 모델 카드에 따르면 Gemini 4 Neon(`gemini-4-neon`)은 텍스트 문자열, 이미지, 오디오, 비디오 파일, PDF 문서를 기본 입력으로 받아들이며 입출력을 합쳐 최대 100만 토큰(1,000,000토큰)의 통합 컨텍스트 윈도를 제공한다.[1][2][3] 출력의 경우 기본 동기(synchronous) 호출에서 최대 6만 4,000토큰을 생성할 수 있고, 백그라운드 롱 디코드(background long decode) 모드를 사용하면 최대 100만 토큰까지 연속 생성이 가능하다.[2][3][4] 모델 카드에 기재된 지식 기준 시점(knowledge cutoff)은 2026년 3월이다.[2]

| 사양 항목 | Gemini 4 Neon (`gemini-4-neon`) |
| --- | --- |
| 개발사 | Google DeepMind (Alphabet Inc.) |
| 출시일 | 2026년 11월 18일 |
| 기반 아키텍처 및 계보 | Gemini 4 Carbon (`gemini-4-carbon`)에서 조정 |
| 입력 모달리티 | 텍스트, 이미지, 오디오, 비디오, PDF |
| 출력 모달리티 | 텍스트(추론 및 사고 토큰 포함) |
| 컨텍스트 윈도 | 입출력 통합 1,000,000토큰 |
| 최대 출력 토큰 | 기본 동기 출력 64,000토큰 / 백그라운드 롱 디코드 최대 1,000,000토큰 |
| 지식 기준 시점 | 2026년 3월 |
| Gemini API 캐싱 지원 | 암시적 컨텍스트 캐싱(implicit caching, 100만 토큰당 $0.15; 명시적 캐싱 미지원) |

Gemini 4 Neon은 추론 수준(기본값 `high` 및 `xhigh` 등) 조정, 장기 에이전트 세션에서의 컨텍스트 압축(context compaction), [모델 컨텍스트 프로토콜](https://mimirwiki.com/ko/wiki/model-context-protocol)(MCP) 연동 및 Google Antigravity의 `/swarm` 다중 에이전트 오케스트레이션을 지원한다.[1] Google은 출시 발표문에서 Google Antigravity와 Gemini 4 Neon을 결합한 네 가지 시연 사례를 공개했다. 첫째는 Blender MCP와 `/swarm`을 구동해 Carbon과 Hydrogen을 분젠 버너 불꽃으로, Argon과 Neon을 고전압 가스 방전관으로 시각화한 3D 실험대 렌더링이며, 둘째는 사전 제작 에셋 없이 10,200줄의 커스텀 셰이더와 120 Hz 물리 엔진, 공간 웹 오디오만으로 몽블랑·샤모니 실제 지형 위에 구현한 1인칭 WebGL2 프리라이드 스키 시뮬레이터이다. 셋째는 케임브리지 대학교 킹스 칼리지의 아카이브 사진을 바탕으로 외부 예배당부터 1936년 앨런 튜링의 서재(X.8호실)와 책상 위에서 작동하는 보편 튜링 기계까지 구현한 대화형 3D 공간이며, 넷째는 삽입 이미지나 Apps Script 없이 50만 개 이상의 실시간 스프레드시트 수식만으로 단일 사진을 윤곽선 검출·3D 깊이 매핑·6가지 조명 모드를 갖춘 10만 셀 규모의 Google Sheets로 변환한 에이전트 스웜 작업이다.[1]

## Gemini 4 Neon API 및 Google Cloud 요금, 캐싱, 속도 제한

Gemini 4 Neon은 Gemini Developer API의 유료 등급(Paid tier, 무료 등급인 Free tier에서는 미제공)과 Google Cloud Model Garden을 통해 과금된다.[4][5] 모델이 처리하는 모든 토큰은 과금 대상에 포함되며, 여기에는 모델의 내부 사고 토큰(thinking tokens)과 그라운딩(grounding) 사용 시 투입되는 내부 도구 시스템 지침 및 함수 선언 토큰이 모두 산입된다.[4] Gemini Developer API에서 컨텍스트 캐싱은 암시적 캐싱(implicit caching)만 지원하며 기본 입력 단가(3.00달러)에서 95% 할인된 100만 토큰당 0.15달러가 부과된다. Google 검색 그라운딩(Grounding with Google Search)은 Gemini 3 이후 모델 전체에서 합산해 월 5,000건까지 무료로 제공된 뒤 1,000건당 14.00달러(일일 기본 상한 1,500건)가 부과된다.[1][4][6]

Google Cloud Model Garden(Agent Platform)에서는 2026-11-23 기준 처리 모드(Standard, Priority, Batch)와 엔드포인트 리전(글로벌 대 비글로벌)에 따라 차등 요율이 적용되며, 캐시 쓰기(cache write) 요금은 2027년 1월 12일부터 부과될 예정이다.[5]

| 플랫폼 및 서비스 등급 (2026-11-23 기준) | 엔드포인트 리전 | 입력 (텍스트, 이미지, 비디오, 오디오) | 캐시 읽기 | 캐시 쓰기 (2027-01-12 발효) | 텍스트 출력 (응답 및 추론) |
| --- | --- | --- | --- | --- | --- |
| Gemini Developer API (유료 등급) | 글로벌 | $3.00 / 1M | $0.15 / 1M (암시적) | 미지원 | $15.00 / 1M |
| Google Cloud Model Garden - Standard | 글로벌 | $3.00 / 1M | $0.15 / 1M | $3.75 / 1M | $15.00 / 1M |
| Google Cloud Model Garden - Standard | 비글로벌(리전) | $3.30 / 1M | $0.165 / 1M | $4.125 / 1M | $16.50 / 1M |
| Google Cloud Model Garden - Priority | 글로벌 | $5.40 / 1M | $0.27 / 1M | $6.75 / 1M | $27.00 / 1M |
| Google Cloud Model Garden - Priority | 비글로벌(리전) | $5.94 / 1M | $0.297 / 1M | $7.425 / 1M | $29.70 / 1M |
| Google Cloud Model Garden - Batch | 글로벌 | $1.50 / 1M | $0.075 / 1M | $1.875 / 1M | $7.50 / 1M |
| Google Cloud Model Garden - Batch | 비글로벌(리전) | $1.65 / 1M | $0.0825 / 1M | $2.0625 / 1M | $8.25 / 1M |

Google Cloud에서는 HTTP 200 응답 코드를 반환한 요청에 대해서만 요금이 청구되며 4xx 및 5xx 오류 응답에는 입출력 요금이 부과되지 않는다.[5] Gemini Developer API에서는 API 키가 아닌 프로젝트 단위로 속도 제한(RPM, TPM, RPD)과 10분 이동 윈도 기준 지출 속도 제한(spend rate limit)이 적용된다. 사용 등급은 Tier 1(결제 계정 연결, 월 한도 250달러, 10분당 지출 제한 10달러), Tier 2(누적 지출 100달러 및 첫 결제 후 3일 경과, 월 한도 2,000달러, 10분당 200달러), Tier 3(누적 지출 1,000달러 및 30일 경과, 월 한도 2만~10만 달러 이상, 10분당 200달러)으로 나뉘며 한도 초과 시 `429 RESOURCE_EXHAUSTED` 오류를 반환한다.[6]

## Gemini 4 Neon 벤치마크 성능 평가

2026년 11월 18일 발행된 Gemini 4 Neon 모델 카드와 출시 발표문에서 Google DeepMind는 종합 역량 지수, 에이전트형 코딩, 엔터프라이즈 지식 업무, 과학 및 수학, 추론, 멀티모달 이해, 장문 컨텍스트, 사이버보안의 8개 영역에 걸쳐 Gemini 4 Neon을 Anthropic의 [Claude](https://mimirwiki.com/ko/wiki/claude) Opus 5.5 및 OpenAI의 [GPT-6.2](https://mimirwiki.com/ko/wiki/gpt-6-2) Sol과 비교한 벤치마크 결과를 공개했다.[1][2]

| 평가 영역 | 벤치마크 | Gemini 4 Neon | Claude Opus 5.5 | GPT-6.2 Sol |
| --- | --- | --- | --- | --- |
| 종합 역량 지수 | Artificial Analysis Intelligence Index v5.0.1 | 61 | 59 | 57 |
| 종합 역량 지수 | Vals Index v2.2 | 70.9% | 70.1% | 66.1% |
| 에이전트형 코딩 | CursorBench 4.1 | 65.4% | 58.1% | 미기재 |
| 에이전트형 코딩 | Terminal-Bench 4.1 (부정행위 보정 정확도) | 65.2% | 65.8% | 61.5% |
| 에이전트형 코딩 | FrontierCode 2.0 (메인 점수) | 46.2% | 47.3% | 43.8% |
| 에이전트형 코딩 | SWE-sweep (제공사 하니스 / mini-SWE 하니스) | 39.0% / 12.8% | 10.1% / 3.6% | 8.3% / 11.6% |
| 지식 업무 | Zapier AutomationBench | 56.3% | 42.5% | 41.3% |
| 지식 업무 | Agents' Last Exam v1.1 | 75.8% | 71.6% | 73.0% |
| 과학 및 수학 | RiemannBench | 84.0% | 80.0% | 80.0% |
| 과학 및 수학 | Terminal-Bench-Science 0.1 | 70.5% | 63.3% | 68.0% |
| 고난도 추론 | HLE-Diamond | 71.3% | 67.9% | 64.0% |
| 멀티모달 이해 | MKA Climb WSR / Chartography / LVBench | 56.5% / 73.5% / 89.0% | 53.0% / 66.3% / 83.7% | 52.7% / 75.1% / 87.6% |
| 장문 컨텍스트 | GraphWalks (256K~1M, BFS F1) | 95.2% | 66.8% | 80.1% |
| 사이버보안 | CWE-Bench v2 / SEC-bench Pro / WebExploitBench v1.2 | 70.7% / 90.5% / 51.3% | 67.1% / 미기재 / 37.1% | 66.0% / 88.3% / 미기재 |

모델 카드 표 외에도 Google은 Gemini 4 Neon이 Artificial Analysis Coding Agent Index에서 58.6점으로 전체 1위, Legal Research Bench 및 Tax Agent Bench에서 1위, 장기 경영 시뮬레이션인 Andon Labs의 Vending-Bench 2에서 16,843달러로 전체 1위를 차지했으며, 4,200건 이상의 실제 에이전트 세션을 평가한 Arena의 Agent Arena Index에서 1336점으로 세계 2위(작업 중 사용자의 수정 지시에 적응하는 조향성[steerability] 부문 2위)로 진입했다고 밝혔다.[1] 독립 평가 기관인 Artificial Analysis 역시 2026년 11월 18일 분석 기사에서 Gemini 4 Neon이 Gemini 4 Carbon 대비 과제당 비용을 약 17% 낮추면서 소폭 높은 지능 지수를 달성했다고 보고했다.[9]

## Gemini 4 Neon 안전성 평가, 한계점 및 지원 지역

Gemini 4 Neon 모델 카드는 이 모델의 주요 권장 용도로 장기 실행 에이전트 워크플로, 다중 파일 저장소 디버깅 및 리팩터링, 멀티모달 지식 업무, 그리고 보안 코드 생성·모의 침투 테스트·취약점 탐지 및 검증·패치 적용을 포함한 방어적 사이버보안 업무를 제시한다.[2] Google은 Google Antigravity 내부 테스트에서 Gemini 4 Neon이 역대 Gemini 모델 중 가장 낮은 허위 사실 날조율(fabrication rate)을 기록했다고 밝혔다.[1]

개발 단계에서 수행된 자동화 안전성 내부 평가에서 Gemini 4 Neon은 텍스트 대 텍스트 안전성(Gemini 4 Hydrogen 대비 0.00%포인트 차이), 다국어 안전성, 이미지 대 텍스트 안전성 항목 모두에서 Gemini 4 Hydrogen과 신뢰구간 내의 동등한 안전 성능을 보였다.[2] 또한 거절 응답의 어조는 Gemini 4 Hydrogen과 유사하게 유지하면서 특히 멀티모달 프롬프트에서의 불필요한 과잉 거절(unjustified refusals)을 줄였다.[2]

모델 카드에 명시된 한계점으로는 일반적인 환각(hallucinations) 가능성과 2026년 3월로 설정된 지식 기준 시점이 있으며, 프런티어 안전(Frontier Safety) 및 탈옥(jailbreak) 방어 정책은 기반 모델인 Gemini 4 Carbon의 안전·보안 보고서 체계를 따른다.[2] 2026-11-23 기준 Google AI Studio 및 Gemini Developer API 지원 지역 문서에는 한국과 미국을 포함한 215개 이상의 국가 및 속령이 등재되어 있으며, 미지원 지역 사용자는 Google Cloud의 Gemini Enterprise Agent Platform을 통해 접근할 수 있다.[7]

## 자주 묻는 질문

### Gemini 4 Neon은 어떤 모델이며 Gemini 4 제품군에서 어떤 위치에 있나요?

Gemini 4 Neon(`gemini-4-neon`)은 Google과 Google DeepMind가 2026년 11월 18일 출시한 멀티모달 추론 대규모 언어 모델입니다. 최상위 플래그십 모델인 Gemini 4 Carbon을 기반으로 조정(adaptation)된 모델로, 최고 난도 장기 프로젝트를 담당하는 Carbon과 빠른 일상 실행을 담당하는 Gemini 4 Hydrogen 사이에 위치해 프런티어급 분석 추론과 빠른 작업 완료 속도, 비용 효율의 균형을 맞추도록 설계되었습니다. [1][2][3]

### Gemini 4 Neon의 컨텍스트 윈도, 지원 모달리티, 지식 기준 시점은 어떻게 되나요?

Gemini 4 Neon은 텍스트, 이미지, 오디오, 비디오, PDF 파일을 입력으로 받으며 입출력 통합 최대 100만 토큰(1,000,000토큰)의 컨텍스트 윈도를 지원합니다. 출력은 기본 동기 호출에서 최대 6만 4,000토큰, 백그라운드 롱 디코드(background long decode) 사용 시 최대 100만 토큰까지 생성할 수 있으며, 2026년 11월 18일 발행된 모델 카드 기준 지식 기준 시점은 2026년 3월입니다. [2][3][4]

### Gemini API와 Google Cloud에서 Gemini 4 Neon의 요금은 얼마인가요?

2026-11-23 기준 Gemini Developer API(유료 등급 전용, 무료 등급 미제공)와 Google Cloud Model Garden 글로벌 엔드포인트의 표준 요금은 100만 토큰당 입력 3.00달러, 캐시 읽기 0.15달러(95% 할인), 출력(추론 토큰 포함) 15.00달러입니다. Google Cloud Model Garden에서는 글로벌 엔드포인트 기준 Priority 등급이 입력 5.40달러, 캐시 읽기 0.27달러, 출력 27.00달러이고 Batch 등급이 입력 1.50달러, 캐시 읽기 0.075달러, 출력 7.50달러이며, 비글로벌 리전 엔드포인트에는 10% 추가 요율이 적용됩니다. [1][4][5]

### 어떤 Google 구독 요금제와 개발자 플랫폼에서 Gemini 4 Neon을 사용할 수 있나요?

2026-11-23 기준 개발자는 Google AI Studio의 Gemini API 유료 등급과 Google Cloud의 Gemini for business 및 Model Garden에서 이용할 수 있습니다. 일반 및 전문가 구독자의 경우 Google One의 Google AI Pro 요금제(클라우드 스토리지 5 TB 포함)와 Google AI Ultra 요금제(스토리지 20 TB 이상, AI Pro 대비 5배 높은 사용 한도 제공)에 포함되어 Gemini 앱, Google Antigravity, Google AI Studio에서 사용할 수 있습니다. [1][2][4][8]

### 코딩, 과학, 엔터프라이즈 벤치마크에서 Gemini 4 Neon의 성능은 어떠한가요?

2026년 11월 18일 공개된 Google DeepMind 발표문과 모델 카드에 따르면 Gemini 4 Neon은 Artificial Analysis Intelligence Index v5.0.1에서 61점(xhigh 추론 기준 전체 3위), Artificial Analysis Coding Agent Index에서 58.6점(전체 1위), Vals Index v2.2에서 70.9%(전체 2위), Zapier AutomationBench에서 56.3%(전체 1위), Andon Labs Vending-Bench 2에서 16,843달러(전체 1위), RiemannBench에서 84.0%, Terminal-Bench-Science 0.1에서 70.5%, HLE-Diamond에서 71.3%, GraphWalks(256K~1M BFS)에서 95.2%, 그리고 Google Antigravity 하니스 기반 SWE-sweep에서 39.0%를 기록했습니다. [1][2]

## 인용 문장

- Google DeepMind는 2026년 11월 18일 Gemini 4 Carbon을 기반으로 조정(adaptation)한 멀티모달 추론 모델 Gemini 4 Neon을 출시했다. [1][2]
- Gemini 4 Neon(API 모델 코드 gemini-4-neon)은 텍스트, 이미지, 오디오, 비디오, PDF 입력을 수용하는 100만 토큰 통합 컨텍스트 윈도를 갖추고 있으며 기본 동기 출력 최대 6만 4,000토큰, 백그라운드 롱 디코드(long decode)를 통해 최대 100만 출력 토큰을 지원한다. [2][3]
- 2026-11-23 기준 Gemini Developer API와 Google Cloud Model Garden(글로벌 엔드포인트)에서 Gemini 4 Neon의 표준 요금은 100만 토큰당 입력 3.00달러, 캐시 읽기 0.15달러, 출력(추론 토큰 포함) 15.00달러이다. [1][4][5]
- 2026-11-23 기준 Google Cloud Model Garden의 글로벌 엔드포인트 요금은 100만 토큰당 Priority 등급이 입력 5.40달러, 캐시 읽기 0.27달러, 출력 27.00달러이고 Batch 등급이 입력 1.50달러, 캐시 읽기 0.075달러, 출력 7.50달러이며, 비글로벌(리전) 엔드포인트에는 10% 할증이 적용된다. [5]
- Google DeepMind의 Gemini 4 Neon 모델 카드에 명시된 지식 기준 시점(knowledge cutoff)은 2026년 3월이다. [2]
- Google DeepMind가 발표한 2026년 11월 벤치마크에서 Gemini 4 Neon은 Artificial Analysis Intelligence Index v5.0.1 61점, Artificial Analysis Coding Agent Index 58.6점(전체 1위), Vals Index v2.2 70.9%, AutomationBench 56.3%, RiemannBench 84.0%, Google Antigravity 하니스 기준 SWE-sweep 39.0%를 기록했다. [1][2]
- 2026-11-23 기준 Gemini 4 Neon은 Google AI Studio의 Gemini API(유료 등급 전용), Google Cloud Model Garden 및 Gemini for business, 그리고 Google AI Pro 및 Ultra 구독자용 Gemini 앱과 Google Antigravity를 통해 제공된다. [1][2][8]

## 연표

- 2026-03: Google DeepMind 모델 카드에 기재된 Gemini 4 Neon의 지식 기준 시점(knowledge cutoff)이다. [2]
- 2026-11-18: Google DeepMind가 Gemini 앱, Gemini API, Google AI Studio, Gemini for business, Google Antigravity에 Gemini 4 Neon(gemini-4-neon)을 출시하고 모델 카드를 공개했다. [1][2][9]
- 2027-01-12: Google Cloud Model Garden에서 Gemini 4 Neon의 캐시 쓰기(cache write) 요금($3.75/1M 표준 글로벌, $6.75/1M Priority 글로벌, $1.875/1M Batch 글로벌)이 발효될 예정이다. [5]

## 출처

1. Introducing Gemini 4 Neon. Google (The Keyword). 게시일 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (확인일 2026-11-23; tier 3: official site)
2. Gemini 4 Neon - Model Card - Google DeepMind. Google DeepMind. 게시일 2026-11-18. https://deepmind.google/models/model-cards/gemini-4-neon/ (확인일 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/models?auto_signin=false (확인일 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/pricing?auto_signin=false (확인일 2026-11-23; tier 3: official site)
5. Agent Platform Pricing | Google Cloud. Google Cloud. https://cloud.google.com/model-garden/pricing (확인일 2026-11-23; tier 3: official site)
6. Rate limits - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/rate-limits?auto_signin=false (확인일 2026-11-23; tier 3: official site)
7. Available regions for Google AI Studio and Gemini API - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/available-regions?auto_signin=false (확인일 2026-11-23; tier 3: official site)
8. Google AI plans with Cloud Storage - Google One. Google One. https://one.google.com/about/google-ai-plans/ (확인일 2026-11-23; tier 3: official site)
9. Google continues to accelerate its release cadence with Gemini 4 Neon | Artificial Analysis. Artificial Analysis. 게시일 2026-11-18. https://artificialanalysis.ai/articles/gemini-4-neon-intelligence-gain (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "Gemini 4 Neon." 버전 ab3d57a1, 2026-11-23. https://mimirwiki.com/ko/wiki/gemini-4-neon
