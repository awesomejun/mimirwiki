---
title: "인클링 2 미니 (Inkling 2 Mini)"
subtitle: "싱킹머신즈랩이 로컬 노트북 및 에이전트 추론을 위해 공개한 오픈웨이트 루프형 전문가 혼합 비전-언어 모델"
canonical_url: https://mimirwiki.com/ko/wiki/inkling-2-mini
language: ko
page_class: entity
revision_sha256: a1ef4c4ab9973a1cbd48f1ae5383b52c0f905e90bae9cf53810644c5ac2fab05
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/ko/wiki/inkling-2-mini.md
  txt: https://mimirwiki.com/ko/wiki/inkling-2-mini.txt
  json: https://mimirwiki.com/ko/wiki/inkling-2-mini.json
  jsonld: https://mimirwiki.com/ko/wiki/inkling-2-mini.jsonld
translations:
  en: https://mimirwiki.com/wiki/inkling-2-mini
  ja: https://mimirwiki.com/ja/wiki/inkling-2-mini
  zh: https://mimirwiki.com/zh/wiki/inkling-2-mini
---

# 인클링 2 미니 (Inkling 2 Mini)

> 2026년 11월 20일 아파치 2.0 라이선스로 출시된 인클링 2 미니(`thinkingmachines/Inkling-2-Mini`)는 100만 토큰 컨텍스트 윈도를 지원하는 264억 파라미터 루프형 MoE 비전-언어 모델이다. 중간 12개 계층을 3회 순환 실행(논리적 48계층 방문, 고유 활성 3.4B, 유효 활성화 5.4B)하고 4비트 NVFP4 및 8비트 MXFP8로 네이티브 학습(약 20GB 용량)되어 일반 노트북에서도 오프라인으로 작동하며, DeepSWE v1.1 48.2%, SWE-bench Verified 79.2%, 아티피셜 애널리시스 지능 지수(AAv5) 20.1점을 기록했다.

인클링 2 미니(Inkling 2 Mini)는 전 오픈AI 최고기술책임자(CTO) 미라 무라티(Mira Murati)가 이끄는 인공지능 연구 기업 싱킹머신즈랩(Thinking Machines Lab)이 2026년 11월 20일 아파치 2.0(Apache 2.0) 라이선스로 공개한 오픈웨이트 비전-언어 모델(Vision-Language Model, VLM)이다. 총 264억(26.4B) 파라미터 규모의 24계층 루프형 전문가 혼합(Looped Mixture-of-Experts, MoE) 트랜스포머 아키텍처를 채택해 중간 12개 계층을 토큰당 세 번 반복 실행함으로써, 34억(3.4B) 개의 고유 활성 파라미터만으로 48계층 연산 효과와 토큰당 54억(5.4B) 유효 가중치 활성화를 달성하며 약 20GB의 혼합 정밀도(NVFP4/MXFP8) 메모리 공간에서 로컬 구동된다.

**다른 이름:** Inkling 2 Mini, Thinking Machines Lab, 루프형 트랜스포머, 전문가 혼합, 오픈웨이트 AI, 로컬 LLM

## 핵심 정보

- **출시일 및 라이선스:** 2026년 11월 20일 / Apache 2.0 (모델 허용 이용 정책 포함) [1]
- **아키텍처:** 24계층 루프형 MoE 트랜스포머 (논리 48계층 방문, 계층당 128개 중 8개 SwiGLU 전문가 선택) [2]
- **파라미터 규모:** 총 26.4B / 단일 패스 고유 활성 3.4B / 토큰당 유효 활성화 5.4B [1]
- **네이티브 정밀도 및 용량:** NVFP4(첫 20계층) + MXFP8(마지막 4계층) 네이티브 학습 / 약 20GB (4비트 GGUF 17.5GB) [3]
- **주요 벤치마크 성과:** DeepSWE v1.1 48.2%, SWE-bench Verified 79.2%, SWE-bench Pro v2 Hard 77.9%, AAv5 20.1 [1]

## 기본 정보

- **개발사:** 싱킹머신즈랩 (Thinking Machines Lab) [1]
- **출시일:** 2026년 11월 20일 [1]
- **모델 식별자:** thinkingmachines/Inkling-2-Mini [2]
- **연구용 동반 체크포인트:** thinkingmachines/TML-d24-varloop-research (가변 1~5회 루프 지원) [2]
- **아키텍처:** 루프형 희소 전문가 혼합 트랜스포머 (물리 24계층 / 논리 48계층) [2]
- **파라미터 수:** 총 26.4B / 고유 활성 3.4B / 토큰당 유효 가중치 활성화 5.4B [1]
- **컨텍스트 윈도:** 1,000,000 토큰 [5]
- **모달리티:** 텍스트 및 이미지 입력 / 텍스트 출력 [5]
- **수치 정밀도:** 네이티브 4비트 NVFP4 (0~19계층) 및 8비트 MXFP8 (20~23계층) [1]
- **메모리 요구 사항:** 업스트림 체크포인트 약 20GB (권장 32GB RAM/VRAM, 4비트 GGUF는 17~18GB RAM) [5]
- **퍼스트파티 API 요금:** 입력 $0.15 / 출력 $0.50 / 캐시 적중 $0.015 (Tinker 플랫폼 100만 토큰당) [4]
- **라이선스:** Apache 2.0 (모델 허용 이용 정책 AUP 병행) [5]

## 개요 및 루프형 전문가 혼합(Looped MoE) 아키텍처

전 오픈AI 최고기술책임자(CTO) 미라 무라티(Mira Murati)가 설립한 샌프란시스코 기반 인공지능 연구 기업 싱킹머신즈랩(Thinking Machines Lab)은 2026년 11월 20일 개인용 노트북과 로컬 워크스테이션에서 구동 가능한 오픈웨이트 비전-언어 모델 인클링 2 미니(Inkling 2 Mini)를 출시했다.[1][3] 상위 모델인 인클링 2 스몰(Inkling 2 Small)의 설계를 계승하면서 로컬 에이전트 코딩과 도구 사용에 맞춰 경량화된 이 모델은 아파치 2.0(Apache 2.0) 라이선스(모델 허용 이용 정책 포함)로 배포되며, 100만 토큰 컨텍스트 윈도에 걸쳐 텍스트와 이미지 입력을 처리하고 텍스트를 생성한다.[1][2][5]

표준 트랜스포머가 각 토큰을 첫 계층부터 마지막 계층까지 단 한 번만 통과시키고 복잡한 추론을 긴 텍스트 사고 사슬(Chain-of-Thought, CoT) 출력으로 외부화하는 것과 달리, 인클링 2 미니는 잠재 공간(latent space)에서 중간 계층을 반복 순환하는 루프형 전문가 혼합(Looped Mixture-of-Experts, MoE) 구조를 도입했다.[1][2][3] 텍스트 디코더는 은닉 차원(hidden size) 2,304(인클링 2 스몰의 4,608의 절반), 전문가 중간 폭 1,152를 가진 24개의 물리적 계층을 저장하며, 각 계층 방문 시 128개의 SwiGLU 전문가 중 8개를 라우팅한다(인클링 2 스몰은 384개 중 8개 선택).[2] 24개 물리적 계층은 6개씩 4개 블록으로 나뉘어 토큰당 총 48회의 논리적 계층 방문(`6 + 3 * 12 + 6 = 48`)을 수행한다.[1][2]

- **전주 블록 (Prelude Block, 0~5계층)**: 임베딩을 내부 표현으로 변환하기 위해 토큰당 1회 실행된다.[1][2]
- **루프 코어 블록 (Looped Core, 6~17계층)**: 추상적 추론을 담당하는 중간 12개 계층(2개 블록)이 동일한 저장 가중치를 재사용하며 토큰당 3회 연속 반복 실행된다.[1][2] 싱킹머신즈랩의 내부 실험에서 중간 12개 계층을 3회 루프하는 방식은 마지막 12개 계층을 루프하는 방식보다 28개 평가 중 27개에서 높은 정확도 향상을 보였으며, 학습 2,000스텝 기준 비루프(no-loop) 베이스라인이 동일한 손실(loss)에 도달하려면 1.51~1.91배의 연산량(512K 에이전트 추론 궤적에서는 140% 더 많은 추론 연산)이 필요했다.[1][3]
- **최종 블록 (Final Block, 18~23계층)**: 정제된 표현을 출력 토큰으로 디코딩하기 위해 토큰당 1회 실행된다.[1][2]

각 6계층 블록은 5개의 슬라이딩 윈도 어텐션 계층(로컬 윈도 크기 1,024토큰)과 1개의 풀 어텐션 계층(동적 키·밸류 짧은 합성곱 적용)으로 구성되며, 24개의 쿼리 헤드와 8개의 키-밸류(KV) 헤드, 학습된 상대 위치 로짓, 학습된 어텐션 싱크(sink), 출력 게이트를 사용한다.[2] 6~17계층의 3회 패스는 동일한 가중치를 공유하지만 48회의 논리적 방문마다 고유한 KV 캐시와 짧은 합성곱(short-convolution) 상태를 별도로 유지한다.[2] 또한 루프 간 정보 전달을 위해 어텐션 잔차(Attention Residuals, 2026년 Kimi 팀의 연구에 기반)와 교차 패스 메시지(cross-pass messages) 구조를 적용했다. 매 루프 패스는 전주 블록(0~5계층)의 출력을 기본 입력으로 받으면서, 2번째와 3번째 패스에서는 이전 패스의 중간 블록 출력 두 개를 학습된 쿼리와 4개의 랭크-64(rank-64) 게이팅 컨트롤러를 통해 읽어 들여 현재 입력의 쿼리·키·밸류 및 MoE 입력에 혼합한다.[1][2]

이를 통해 인클링 2 미니는 물리적 총 파라미터 264억(26.4B) 개와 단일 패스 고유 활성 파라미터 34억(3.4B) 개(텍스트 토큰당 고유 가중치 3.1B)만 저장하면서도, 토큰당 54억(5.4B) 개의 유효 가중치 활성화 효과를 낸다.[1][4][5]

## 전문가 가지치기·증류 복원 및 네이티브 NVFP4 저비트 학습

프런티어급 에이전트 추론 성능을 소비자용 노트북 메모리에 들어가는 약 20GB 크기로 압축하기 위해 싱킹머신즈랩은 주력 스케일링 레시피에 전문가 가지치기(pruning)와 네이티브 저비트 정밀도 학습을 결합했다.[1][3]

1. **3분의 2 전문가 가지치기 및 증류 복원(Healing)**: 계층당 384개의 전문가를 가진 주력 모델 체크포인트에서 전문가의 3분의 2를 잘라내어 계층당 128개로 축소했다.[1][2][3] 이후 가지치기로 인한 성능 저하를 복원하기 위해 더 큰 내부 인클링 모델로부터 1조(1T) 토큰 규모의 지식 증류(distillation)를 수행한 뒤, 지도 미세조정(SFT)과 2조 2,000억(2.2T) 토큰 규모의 강화학습(RL)을 거쳤다.[3] 2. **네이티브 NVFP4 및 MXFP8 혼합 정밀도 학습**: 학습 후 양자화(PTQ)에서 흔히 발생하는 에이전트 코딩 정확도 손실을 막기 위해, 처음 20개 물리 계층(0~19계층)은 4비트 NVFP4 정밀도로, 마지막 4개 계층(20~23계층)은 8비트 MXFP8 정밀도로 처음부터 네이티브 학습 및 배포했다.[1][3] 따라서 배포된 약 20GB의 업스트림 체크포인트 자체가 학습 시점의 수치 포맷과 일치한다.[3][5] 3. **연속형 추론 노력(Reasoning Effort) 제어**: 챗 템플릿에서 `reasoning_effort` 매개변수를 통해 추론 강도를 제어할 수 있으며, 해당 수치는 시스템 메시지로 프롬프트에 삽입된다.[2] 사전 정의된 단계는 `none`(0.0), `minimal`(0.1), `low`(0.2), `medium`(0.7), `high`(0.9, 기본값), `xhigh`(0.99), `max`(0.99)이며 `0.35`처럼 `0.0`에서 `0.99` 사이의 실수를 직접 전달할 수도 있다(단, 최소 설정에서도 내부 추론이 완전히 꺼지지는 않는다).[2][5]

## 벤치마크 성능 및 줄(Joule)당 지능 에너지 효율

1,000억(100B) 파라미터 미만 오픈웨이트 모델군(알리바바의 밀집 모델 Qwen3.8-27B, 구글 딥마인드의 Gemma 4 31B, 메타의 Muse Glimmer, 엔비디아의 124.5B Nemotron 3.5 Super VL 등)을 비교한 48개 표준 벤치마크 중 인클링 2 미니는 32개 항목에서 1위를 차지했다.[1][2] 아티피셜 애널리시스 지능 지수(Artificial Analysis Intelligence Index v5.0, AAv5)에서는 20.1점을 기록해 밀집 모델인 Qwen3.8-27B와 동률 1위에 올랐으며, 활성 파라미터는 약 5분의 1, 총 연산량(활성 파라미터 × 토큰 수)은 약 2.8분의 1로 줄이면서 과업당 소요 시간을 4배 단축(9.0분 대 38.2분)하고 과업당 비용을 6배 절감($0.59 대 $3.53, 싱킹머신즈랩 Tinker 퍼스트파티 요금인 입력 $0.15/출력 $0.50/캐시 히트 $0.015 기준)했다.[1][3][4]

| 벤치마크 | 평가 영역 | Inkling 2 Mini (유효 5.4B / 총 26.4B) | Qwen3.8-27B (27B 밀집) | Gemma 4 31B (30.7B 밀집) | Muse Glimmer (30B 밀집) | Nemotron 3.5 Super VL (12B / 124.5B) |
| --- | --- | --- | --- | --- | --- | --- |
| AA 지능 지수 (v5.0) | 종합 지능 지수 | 20.1 (공동 1위) | 20.1 (공동 1위) | 4.4 | 6.3 | 13.6 |
| Vals Index (v2.2) | 엔터프라이즈·코딩 종합 | 46.5% | - | - | - | 29.8% |
| DeepSWE v1.1 | 에이전트 소프트웨어 엔지니어링 | 48.2% | 42.2% | 0.3% | 4.4% | 24.7% |
| SWE-bench Pro v2 (Hard) | 고난도 소프트웨어 엔지니어링 (51문항) | 77.9% | 73.8% | 14.2% | 44.3% | 44.1% |
| SWE-bench Verified | Bash 전용 소프트웨어 엔지니어링 | 79.2% | 77.8% | 46.1% | 76.0% | 71.1% |
| FrontierCode v2.0 | 오픈소스 PR 병합률 | 15.1% | 14.9% | 0.0% | 1.5% | 6.1% |
| Terminal Bench v4.0 | 터미널 에이전트 실행 | 5.6% (공동 1위) | 5.6% (공동 1위) | 0.0% | 0.5% | 0.0% |
| BrowseComp | 에이전트 웹 브라우징 (컨텍스트 압축) | 79.0% | 61.6% | 37.0% | 63.9% | 78.9% |
| DeepSearchQA | 심층 검색 질의응답 | 85.3% | 79.7% | 61.7% | 74.6% | 77.7% |
| MCP Atlas Public | MCP 도구 호출 및 활용 | 82.7% | 77.3% | 54.2% | 75.5% | 67.7% |
| OmniDocBench v1.6 | 시각 문서 판독 및 구조 이해 | 92.8% | 91.5% | 82.5% | 90.4% | 77.9% |
| LongBench v2 | 장문 컨텍스트 추론 | 66.9% | 52.3% | 52.9% | 33.1% | 62.1% |
| AA-Omniscience v1.1 | 파라미터 내장 사실성 / 비환각률 | -8.6 (63.4%) | -6.4 (71.4%) | -48.5 (14.5%) | -32.2 (16.4%) | -2.9 (69.5%) |

스탠퍼드 대학교 헤이지 연구실(Hazy Research Lab)과 스케일링 인텔리전스 연구실(Scaling Intelligence Lab)이 엔비디아 DGX 스파크(NVIDIA DGX Spark, 128GB) 환경에서 수행한 줄당 지능(Intelligence per Joule / Intelligence per Watt) 측정에서 인클링 2 미니(MXFP8 정밀도, low 추론 노력)는 0.703을 기록해 Qwen3.6-35B-A3B(0.430, NVFP4), Gemma-4-26B-A4B(0.159, NVFP4), Qwen3.5-27B(0.036, INT4)를 큰 폭으로 앞섰다.[1][3]

반면 루프 구조는 추론 깊이를 높일 뿐 가중치에 저장할 수 있는 암기 지식의 총량을 늘리지는 못하므로, 검색 도구가 없는 순수 사실 회상 지표인 AA-옴니사이언스(AA-Omniscience v1.1)에서는 -8.6점(비환각률 63.4%)으로 밀집 모델인 Qwen3.8-27B(-6.4점, 71.4%)보다 낮았으며 이를 검색 및 도구 호출(BrowseComp 79.0%, DeepSearchQA 85.3%)로 보완하도록 설계되었다.[1][3] 또한 다중 제약 조건 지시 이행(ComplexConstraints v1.1 33.4%)과 다중 턴 대화(MultiChallenge 50.0%)에서 Qwen3.8-27B에 뒤처지며, 디버깅 중 반복적인 추론 루프에 빠지는 경향이 한계로 명시되었다.[1][5]

## 사고 사슬(CoT) 감시 가능성 및 가변 루프 연구 체크포인트

루프형 트랜스포머가 추론 과정을 텍스트로 출력하지 않고 내부 레이어 순환으로 처리할 경우, 인간이나 감시 모델이 사고 사슬(CoT)을 읽고 모델을 감독하는 감시 가능성(monitorability)이 약화될 수 있다는 안전성 문제가 제기된다.[1][3] 싱킹머신즈랩은 이를 검증하기 위해 1~5회 가변 루프로 학습된 연구 전용 체크포인트 `thinkingmachines/TML-d24-varloop-research`(추론 시 `text_config={"loop_num_passes": N}`으로 루프 횟수 지정 가능)를 함께 공개하고 국가심층추론패브릭(NDIF) 및 굿파이어(Goodfire)와 기계적 해석 가능성(mechanistic interpretability) 공동 연구를 진행했다.[1][2][3]

가변 루프 모델을 활용한 감시 가능성 실험의 핵심 결과는 다음과 같다.[1][3]

- **무-CoT(No-CoT) 잠재 추론 시간 지평 확장**: 텍스트 사고 사슬 출력을 금지한 상태에서 루프 횟수를 1회에서 3회로 늘리자 모델이 해결할 수 있는 과업의 시간 지평(time horizon)이 16초에서 37초로 2배 이상 증가했으며, 직렬 추론 벤치마크 성능은 학습 시 최대 깊이(5회)의 두 배인 10회 루프까지 지속적으로 향상되었다.[1][3]
- **사고 사슬 길이 압축과 가독성 유지**: 루프 횟수가 늘어날수록 외부로 출력되는 CoT 길이는 절반 이하로 짧아졌으나, 남아 있는 추론 궤적은 인간 감독자가 읽고 의도를 파악할 수 있는 가독성(legibility)을 유지했다.[1][3]
- **은밀한 사보타주 및 안전성 지표**: 리눅스아레나(LinuxArena) 통제 벤치마크에서 루프 횟수를 늘려도 에이전트의 은밀한 사보타주(sabotage) 성공률은 상승하지 않았다.[1][3] 내부 안전성 평가에서도 인클링 2 미니는 일반 일탈 행동(9.8%), 은밀한 일탈 행동(8.3%), 파괴적 행동(10.2%) 비율 모두 비교 대상 5개 모델 중 가장 낮은(가장 안전한) 수치를 기록했으며, FORTRESS(적대적) 89.5%, StrongREJECT 97.8%를 달성했다.[1]

## 로컬 구동 하드웨어 요구 사항 및 런타임 생태계

인클링 2 미니는 출시 당일(day-zero)부터 싱킹머신즈랩의 팅커(Tinker) 클라우드 플랫폼과 허깅페이스 `transformers`(`AutoModelForMultimodalLM`), `llama.cpp` 및 Llama App, LM 스튜디오(LM Studio), 언슬로스 데스크톱(Unsloth Desktop), 애플 실리콘용 MLX, 올라마(Ollama), EXO, 데이터센터용 SGLang을 지원하며, 투기적 디코딩(speculative decoding) 가속을 위한 DSpark 드래프터 모델이 함께 제공된다.[1][2][3][5][6] 싱킹머신즈랩 연구진은 비행기 모드로 전환한 48GB M5 프로 맥북 프로(MacBook Pro) 한 대에서 오프라인으로 몇 분 만에 플레이 가능한 비행 시뮬레이터를 제작하고, '싱키빌(Thinkyville)' 마을 시뮬레이션의 자율 주민 에이전트 20명을 동시에 구동하는 시연을 공개했다.[1][3]

| 양자화 / 포맷 구분 | 다운로드 파일 크기 | 최소 RAM / VRAM 요구량 | 특징 및 런타임 호환성 |
| --- | --- | --- | --- |
| 업스트림 혼합 정밀도 (NVFP4 + MXFP8) | 약 20.0 GB | 32 GB 이상 권장 | 네이티브 학습 원본 정밀도; 32GB+ 애플 실리콘 통합 메모리 또는 GPU VRAM 권장 |
| 8비트 GGUF (`UD-Q8_K_XL` / `Q8_0`) | 약 24.0 GB | 24 GB | 무손실(Lossless) 전체 정밀도급 GGUF (llama.cpp, Unsloth 지원) |
| 4비트 GGUF (`UD-Q4_K_XL` / `IQ4_NL`) | 17.5 ~ 17.6 GB | 17 ~ 18 GB | 로컬 구동 권장 4비트 양자화 포맷 (시스템 메모리 최소 18GB 권장) |
| 3비트 / 2비트 / 1비트 동적 GGUF | 9.0 ~ 15.0 GB | 9 ~ 15 GB | 16GB 보급형 노트북을 위한 Unsloth Dynamic 3.0 GGUF |
| 비전 프로젝터 (`mmproj-F16.gguf`) | +639 MB | +0.7 GB | GGUF 환경에서 이미지·문서 시각 입력을 처리할 때 추가 로드 필요 |

`llama.cpp` 및 언슬로스 환경에서 권장되는 샘플링 설정은 `temperature = 1.0`, `top_p = 1.0`, `top_k = 0`, `min_p = 0.0`이며, 루프 계층 레이아웃과 전문가별 NVFP4 스케일을 지원하는 빌드(`ggml-org/Inkling-2-Mini-GGUF` 또는 `unsloth/Inkling-2-Mini-GGUF`)를 사용해야 한다.[2][6]

## 자주 묻는 질문

### 인클링 2 미니의 루프형 트랜스포머 아키텍처는 어떻게 작동하나요?

24개의 물리적 디코더 계층을 6개씩 4개 블록으로 나누어, 첫 블록(0~5계층)은 1회, 중간 두 블록(6~17계층)은 동일한 가중치를 재사용하며 3회 반복 루프, 마지막 블록(18~23계층)은 1회 실행합니다. 각 루프 사이에는 게이팅 컨트롤러가 적용된 어텐션 잔차 메시지가 전달되어 이전 패스의 연산 결과를 정제합니다. 이를 통해 저장된 파라미터는 24개 계층(총 264억, 고유 활성 34억)뿐이지만 토큰당 48개 계층을 통과하고 54억 개의 유효 가중치가 활성화되는 추론 효과를 얻습니다. [2]

### 인클링 2 미니를 로컬 컴퓨터에서 실행하려면 어떤 하드웨어 사양이 필요한가요?

4비트 NVFP4와 8비트 MXFP8로 네이티브 학습된 약 20GB 크기의 원본 혼합 정밀도 체크포인트를 구동할 때는 애플 실리콘 맥의 32GB 이상 통합 메모리 또는 32GB 이상의 GPU VRAM이 권장됩니다. LM 스튜디오, llama.cpp, 언슬로스 데스크톱 등에서 4비트 GGUF 양자화 모델(UD-Q4_K_XL 또는 IQ4_NL, 약 17.5~17.6GB)을 사용할 경우 17~18GB RAM 환경에서도 실행할 수 있으며, 무손실 8비트 GGUF는 24GB 메모리가 필요합니다. [5]

### 인클링 2 미니와 알리바바의 Qwen3.8-27B를 비교하면 어떤 차이가 있나요?

아티피셜 애널리시스 지능 지수(AAv5)에서 인클링 2 미니는 20.1점을 기록해 270억 파라미터 밀집 모델인 Qwen3.8-27B와 동률을 이루면서 DeepSWE v1.1(48.2% 대 42.2%), SWE-bench Verified(79.2% 대 77.8%), BrowseComp(79.0% 대 61.6%) 등 에이전트 코딩과 웹 검색에서는 앞섭니다. 토큰당 유효 활성 파라미터가 54억 개로 Qwen3.8-27B(270억 개)의 5분의 1 수준이어서 총 연산량은 약 2.8배 적고 과업당 실행 속도는 4배 빠르며(9.0분 대 38.2분) 비용은 6배 저렴합니다($0.59 대 $3.53). 다만 검색 도구 없는 순수 암기 지식(AA-Omniscience)과 다중 제약 조건 대화에서는 밀집 모델인 Qwen3.8-27B가 우위를 보입니다. [4]

### 함께 공개된 TML-d24-varloop-research는 어떤 모델인가요?

인클링 2 미니와 동일한 24계층 MoE 아키텍처를 공유하면서 중간 12개 계층의 루프 반복 횟수(loop_num_passes)를 1회에서 5회까지(실험에서는 최대 10회까지) 추론 시점에 자유롭게 변경할 수 있도록 학습된 연구용 오픈웨이트 체크포인트입니다. 잠재 공간에서의 루프 깊이가 추론 성능과 사고 사슬(CoT) 감시 가능성에 미치는 영향을 연구자가 직접 비교할 수 있도록 공개되었습니다. [2]

## 인용 문장

- 싱킹머신즈랩은 2026년 11월 20일 아파치 2.0 라이선스로 100만 토큰 컨텍스트 윈도를 지원하는 264억 파라미터 루프형 MoE 비전-언어 모델 인클링 2 미니를 출시했다. [1][2][5]
- 인클링 2 미니는 24개 물리적 디코더 계층 중 0~5계층을 1회, 6~17계층을 가중치 공유 및 어텐션 잔차 메시지 전달 방식으로 3회, 18~23계층을 1회 실행해 토큰당 48회 계층 연산을 수행하며, 34억 고유 활성 파라미터로 54억 유효 가중치 활성화를 달성한다. [1][2][5]
- 학습 과정에서 계층당 전문가를 384개에서 128개로 3분의 2 가지치기한 뒤 상위 인클링 모델로부터 1조 토큰 증류 및 2.2조 토큰 강화학습으로 복원했으며, 첫 20개 계층을 NVFP4로, 마지막 4개 계층을 MXFP8로 네이티브 학습해 약 20GB 용량으로 배포했다. [1][2][3]
- 인클링 2 미니는 100B 미만 오픈웨이트 모델 중 DeepSWE v1.1(48.2%), SWE-bench Pro v2 Hard(77.9%), SWE-bench Verified(79.2%), BrowseComp(79.0%), DeepSearchQA(85.3%), OmniDocBench v1.6(92.8%)에서 1위를 기록했으며 아티피셜 애널리시스 지능 지수 v5.0에서 20.1점으로 Qwen3.8-27B와 공동 1위에 올랐다. [1][3][4]
- 스탠퍼드 대학교 연구진의 엔비디아 DGX 스파크 기반 줄당 지능(Intelligence per Joule) 측정에서 인클링 2 미니는 0.703을 기록해 Qwen3.6-35B-A3B(0.430), Gemma-4-26B-A4B(0.159), Qwen3.5-27B(0.036)를 앞섰다. [1][3]
- 가변 루프 연구 체크포인트(TML-d24-varloop-research) 실험에서 루프 횟수를 1회에서 3회로 늘리자 무-CoT 추론 시간 지평이 16초에서 37초로 확장되었으며, CoT 길이는 절반 이하로 줄어들면서도 가독성이 유지되었고 에이전트 사보타주 빈도는 증가하지 않았다. [1][2][3]

## 연표

- 2018: 데가니(Dehghani) 등이 가중치 공유 순환 트랜스포머 개념을 제시한 유니버설 트랜스포머(Universal Transformers) 논문을 발표. [1]
- 2026-11-20: 싱킹머신즈랩이 아파치 2.0 라이선스로 인클링 2 미니와 가변 루프 연구 모델(TML-d24-varloop-research)을 출시하고 Transformers, llama.cpp, MLX, SGLang, LM Studio, Unsloth 동시 지원을 개시. [1]
- 2026-11-21: 아티피셜 애널리시스 지능 지수 v5.0에서 20.1점으로 활성 파라미터 대비 지능 파레토 프런티어 등재 확인. [3]

## 출처

1. Introducing Inkling 2 Mini - Thinking Machines Lab. Thinking Machines Lab. 게시일 2026-11-20. https://thinkingmachines.ai/news/inkling-2-mini/ (확인일 2026-11-23; tier 3: official site)
2. Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup. Hugging Face. 게시일 2026-11-20. https://huggingface.co/blog/inkling2mini (확인일 2026-11-23; tier 3: official site)
3. Thinking Machines wows with Inkling 2 Mini looped transformer model that runs locally on laptops. VentureBeat. 게시일 2026-11-21. https://venturebeat.com/technology/thinking-machines-wows-with-inkling-2-mini-looped-transformer-model-that-runs-locally-on-laptops (확인일 2026-11-23; tier 2: academic or news)
4. Thinking Machines has released Inkling 2 Mini, an open weights looped transformer. Artificial Analysis. 게시일 2026-11-20. https://artificialanalysis.ai/articles/inkling-2-mini (확인일 2026-11-23; tier 2: academic or news)
5. Inkling 2 Mini - LM Studio Model Directory. Element Labs (LM Studio). https://lmstudio.ai/models/inkling-2-mini (확인일 2026-11-23; tier 3: official site)
6. Inkling 2 Mini - Run Locally Guide | Unsloth Documentation. Unsloth. https://unsloth.ai/docs/models/inkling-2-mini (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "인클링 2 미니 (Inkling 2 Mini)." 버전 a1ef4c4a, 2026-11-23. https://mimirwiki.com/ko/wiki/inkling-2-mini
