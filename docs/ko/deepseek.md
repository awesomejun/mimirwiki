---
title: "딥시크 (DeepSeek)"
subtitle: "DeepSeek-V4, DeepSeek-R1, DeepSeek-V3 파운데이션 모델을 개발하는 중국의 인공지능 연구 기업"
canonical_url: https://mimirwiki.com/ko/wiki/deepseek
language: ko
page_class: entity
revision_sha256: 85c36234d09a9973a6c7070a3d890f965c7bb022b80ef2114350ac6aed489c00
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/deepseek.md
  txt: https://mimirwiki.com/ko/wiki/deepseek.txt
  json: https://mimirwiki.com/ko/wiki/deepseek.json
  jsonld: https://mimirwiki.com/ko/wiki/deepseek.jsonld
translations:
  en: https://mimirwiki.com/wiki/deepseek
  ja: https://mimirwiki.com/ja/wiki/deepseek
  zh: https://mimirwiki.com/zh/wiki/deepseek
---

# 딥시크 (DeepSeek)

> 2026년 11월 기준 딥시크 개발자 플랫폼은 100만(1M) 토큰 컨텍스트 윈도우와 최대 38만 4,000(384K) 출력 토큰을 지원하는 두 가지 주력 멀티모달 모델인 deepseek-flash(DeepSeek-V4.1-Flash-1017)와 deepseek-v4-pro(DeepSeek-V4-Pro-0813)를 제공한다. 피크·비피크 시간대별 차등 요금제, 검색(Search)·수집(Fetch)·OCR·음성 인식(Speech) 유틸리티 API, 그리고 2026년 11월 18일 도입된 무료 서버 측 내장 웹 검색 기능을 운영하고 있으며, 앞서 DeepSeek-V3(총 671B / 활성 37B 파라미터)와 MIT 라이선스 기반의 DeepSeek-R1 추론 모델을 공개한 바 있다.

딥시크(DeepSeek, 정식 법인명 항저우 딥시크 인공지능 유한공사 및 베이징 딥시크 인공지능 유한공사)는 2023년 설립되어 중국 저장성 항저우에 본사를 둔 인공지능(AI) 연구 기업이다. 멀티헤드 잠재 어텐션(Multi-head Latent Attention, MLA)과 DeepSeekMoE 아키텍처를 기반으로 DeepSeek-V2, DeepSeek-V3, 강화학습 추론 모델인 DeepSeek-R1, 그리고 멀티모달 모델인 DeepSeek-V4 시리즈 등 오픈웨이트(Open-weight) 및 API 호스팅 거대언어모델(LLM)을 개발한다.

**다른 이름:** DeepSeek, Hangzhou DeepSeek Artificial Intelligence Co., Ltd., 항저우 딥시크 인공지능 유한공사, 深度求索

## 핵심 정보

- **운영 법인:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. / Beijing DeepSeek Artificial Intelligence Co., Ltd. [7]
- **주력 프로덕션 모델:** deepseek-flash (DeepSeek-V4.1-Flash-1017) 및 deepseek-v4-pro (DeepSeek-V4-Pro-0813) (기준 2026-11-23) [1]
- **컨텍스트 및 최대 출력:** 100만(1M) 토큰 컨텍스트 윈도우; 최대 38만 4,000(384K) 출력 토큰 (기준 2026-11-23) [1]
- **주요 오픈웨이트 모델:** DeepSeek-R1 (MIT 라이선스, 2025년 1월) 및 DeepSeek-V3 (671B/37B MoE, 2024년 12월) [4]

## 기본 정보

- **정식 법인명:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. (항저우 딥시크 인공지능 유한공사) [7]
- **본사 소재지:** 중국 저장성 항저우시 [7]
- **핵심 아키텍처:** 멀티헤드 잠재 어텐션(MLA), DeepSeekMoE, 다중 토큰 예측(MTP) [5]
- **API 주력 모델 (2026년 11월):** DeepSeek-V4.1-Flash-1017 (deepseek-flash), DeepSeek-V4-Pro-0813 (deepseek-v4-pro) [1]
- **API 컨텍스트 및 출력 한도:** 1,000,000 컨텍스트 토큰 / 최대 384,000 출력 토큰 (기본값 64K) [1]
- **API 동시 요청 한도:** deepseek-flash 2,500건 / deepseek-v4-pro 500건 (user_id 지정 시 사용자당 10건) [2]
- **멀티모달 및 도구 API:** Search API, Fetch API, OCR API, Speech-to-Text API, 서버 측 내장 검색(search_Option) [1]
- **오픈소스 라이선스 (R1):** MIT 라이선스 (DeepSeek-R1 및 증류 모델 가중치·코드) [4]

## 기업 개요 및 아키텍처 기반

딥시크(DeepSeek)는 항저우 딥시크 인공지능 유한공사(Hangzhou DeepSeek Artificial Intelligence Co., Ltd.)와 베이징 딥시크 인공지능 유한공사(Beijing DeepSeek Artificial Intelligence Co., Ltd.)를 통해 프런티어 파운데이션 모델 및 개발자 API를 운영하는 중국의 AI 연구소이다 [1][7]. 2024년과 2025년에 걸쳐 기존 프런티어 모델 대비 현저히 적은 연산 비용으로 학습된 전문가 혼합(Mixture-of-Experts, MoE) 모델과 추론 모델을 오픈웨이트(Open-weight)로 공개하고 상세한 아키텍처 기술 보고서를 발표하며 전 세계적인 주목을 받았다 [4][5][6].

딥시크 파운데이션 모델의 핵심은 **DeepSeek-V2**(2024년 5월, 총 236B / 토큰당 활성 21B 파라미터)에서 도입되어 **DeepSeek-V3**(2024년 12월, 총 671B / 토큰당 활성 37B 파라미터)에서 대규모로 확장된 두 가지 구조적 혁신이다 [5][6]: - **멀티헤드 잠재 어텐션(Multi-head Latent Attention, MLA)**: 추론 시 키-밸류(KV) 캐시 표현을 저차원 잠재 벡터(low-rank latent vector)로 압축하여 장문 컨텍스트 처리 시 메모리 대역폭 병목을 대폭 줄인다 [5][6]. - **보조 손실 없는 부하 분산 기반 DeepSeekMoE(Auxiliary-Loss-Free Load Balancing)**: 세분화된 라우팅 전문가(routed experts)와 공유 전문가(shared experts)를 결합하고, 모델 성능을 저하시키던 기존 보조 손실(auxiliary loss) 대신 동적 편향 조정 라우팅 전략과 다중 토큰 예측(Multi-Token Prediction, MTP) 학습 목표를 적용했다 [5]. DeepSeek-V3는 FP8 혼합 정밀도 학습을 통해 총 278만 8,000 H800 GPU 시간만으로 14조 8,000억(14.8T) 토큰을 사전 학습했다 [5].

## DeepSeek-R1과 강화학습 기반 추론 모델

2025년 1월 딥시크는 **DeepSeek-R1**과 **DeepSeek-R1-Zero**를 오픈소스 MIT 라이선스로 공개하며, 사전 지도 미세조정(SFT) 없이 대규모 순수 강화학습(Reinforcement Learning, RL)만으로도 언어 모델이 자기 검증(self-verification), 성찰(reflection), 장기 사고 사슬(Chain-of-Thought, CoT) 추론 능력을 스스로 학습할 수 있음을 입증했다 [4].

`DeepSeek-R1-Zero`는 베이스 모델에 직접 그룹 상대 정책 최적화(Group Relative Policy Optimization, GRPO)를 적용한 모델이며, `DeepSeek-R1`은 여기에 소량의 콜드 스타트(cold-start) CoT 데이터와 거부 샘플링(rejection sampling)을 결합한 다단계 학습을 거쳐 언어 혼용 문제를 해결하고 가독성을 높임으로써 수학, 코드 경진대회, STEM 추론 벤치마크에서 OpenAI-o1-1217에 필적하는 성능을 달성했다 [4]. 또한 딥시크는 DeepSeek-R1의 추론 출력을 기반으로 Qwen 및 Llama 아키텍처에 증류(distillation)한 1.5B~70B 규모의 고밀도(dense) 증류 모델 6종도 함께 공개했다 [4].

## DeepSeek-V4 시리즈, 요금 체계 및 개발자 플랫폼 (2026년)

2026년 후반 기준 딥시크는 프로덕션 API 플랫폼(`api.deepseek.com`)을 멀티모달 **DeepSeek-V4** 아키텍처로 전환하여 일반 대화, 추론(`thinking`), 비전(이미지), 오디오 입력을 **100만(1,000,000) 토큰 컨텍스트 윈도우**와 최대 **38만 4,000(384,000) 출력 토큰**(기본값 64K)을 지원하는 두 개의 주력 모델 엔드포인트로 통합했다 [1]:

| API 모델 별칭 | 기반 모델 버전 | 피크 시간 요금 (08:00-24:00 UTC+8) | 비피크 할인 요금 (00:00-08:00 UTC+8) | 동시 요청 한도 |
| --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` (2026년 10월 20일 출시) | 입력: 캐시 적중 $0.03/M, 미적중(<=256K) $0.30/M, (>256K) $0.50/M; 출력: $1.50~$2.50/M | 입력: 캐시 적중 $0.03/M, 미적중(<=256K) $0.15/M, (>256K) $0.25/M; 출력: $0.75~$1.25/M | 동시 요청 2,500건 [1][2] |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` (2026년 8월 19일 출시) | 입력: 캐시 적중 $0.20/M, 미적중(<=256K) $2.00/M, (>256K) $4.00/M; 출력: $12.00~$18.00/M | 입력: 캐시 적중 $0.20/M, 미적중(<=256K) $1.00/M, (>256K) $2.00/M; 출력: $6.00~$9.00/M | 동시 요청 500건 [1][2] |

두 모델 모두 텍스트, 이미지, 오디오 입력을 받아 텍스트, JSON 모드, 함수 도구 호출(Tool Calls), 추론 과정(Reasoning Content)을 출력한다 [1]. 오디오 토큰 입력 시에는 컨텍스트 구간 및 캐시 적중 여부에 따라 별도의 오디오 입력 요금(`deepseek-flash` 기준 백만 토큰당 $1.00~$4.00, `deepseek-v4-pro` 기준 $7.00~$28.00)이 부과된다 [1]. 기존의 `deepseek-chat` 및 `deepseek-reasoner` 별칭은 자동으로 V4 시리즈 엔드포인트로 매핑된다 [1].

## 내장 웹 검색, 유틸리티 API 및 동시성 제어

2026년 11월 18일 딥시크는 채팅 완성(Chat Completions) 엔드포인트에 `search_Option` 파라미터를 통한 네이티브 서버 측 웹 검색 및 웹페이지 수집 기능을 추가했으며, 프로모션 기간 동안 별도의 검색 쿼리당 추가 비용 없이 내장 검색을 무료로 제공하고 있다 [1][3]. 또한 독립적인 프로그래밍 파이프라인을 위해 다음과 같은 전용 유틸리티 API 엔드포인트도 제공한다 [1]: - **Search API (검색 API)**: 1,000회 쿼리당 $5.00 [1]. - **Fetch API (웹 수집 API)**: 1,000회 URL 수집당 $1.00 [1]. - **OCR API (광학 문자 인식 API)**: 문서 1,000페이지당 $1.00 [1]. - **Speech-to-Text API (음성-텍스트 변환 API)**: 오디오 1시간당 $0.10 [1].

결제 등급별로 분당 토큰 수(TPM)나 분당 요청 수(RPM) 상한을 엄격히 제한하는 타사와 달리, 딥시크는 현재 처리 중인 동시 요청 수(In-flight Concurrency: `deepseek-flash` 2,500건, `deepseek-v4-pro` 500건)를 기준으로 처리량을 제어한다 [2]. 특히 멀티테넌트 애플리케이션에서 특정 최종 사용자가 전체 쿼터를 독점하는 것을 방지하기 위해 API 요청에 `user_id` 파라미터를 전달하면 해당 개별 `user_id`의 동시 요청을 **최대 10건**으로 자동 격리 제한하며, 초과 시 전체 조직 계정이 아닌 해당 `user_id` 요청에만 HTTP `429 Too Many Requests`를 반환한다 [2].

## 데이터 거버넌스 및 개인정보 처리방침

딥시크의 개인정보 처리방침(Privacy Policy)에 따르면 소비자용 웹, 모바일 앱 및 호스팅 플랫폼 서비스는 항저우 딥시크 인공지능 유한공사와 베이징 딥시크 인공지능 유한공사가 운영한다 [7]. 호스팅 서비스를 통해 수집된 사용자 프롬프트, 업로드 파일, 대화 기록 및 상호작용 로그는 **중화인민공화국(중국)** 내 서버에 저장되며 중국의 데이터 보호 및 사이버보안 법률의 적용을 받는다 [7]. 반면 외부 데이터 전송이 불가능한 기업 및 기관은 MIT 라이선스 등으로 공개된 DeepSeek-V2, DeepSeek-V3, DeepSeek-R1 오픈웨이트 모델 가중치를 자체 프라이빗 인프라에 직접 구축(Self-hosting)하여 외부 텔레메트리 없이 운영할 수 있다 [4][5][7].

## 자주 묻는 질문

### 2026년 11월 기준 딥시크(DeepSeek)의 주력 API 모델은 무엇인가요?

딥시크는 고속 멀티모달 추론 및 코딩을 위한 deepseek-flash(기반 모델 DeepSeek-V4.1-Flash-1017)와 고난도 심층 추론을 위한 deepseek-v4-pro(기반 모델 DeepSeek-V4-Pro-0813) 두 가지 주력 API 모델을 제공합니다. 두 모델 모두 100만(1M) 토큰 컨텍스트 윈도우와 최대 38만 4,000(384K) 출력 토큰을 지원합니다. [1][3]

### 딥시크 API의 피크 및 비피크 시간대 할인 요금제는 어떻게 운영되나요?

딥시크는 베이징 시간(UTC+8) 기준 매일 00:00부터 08:00까지(한국 시간 01:00~09:00, UTC 기준 16:00~00:00)의 비피크 시간대에 캐시 미적중(Cache Miss) 입력 및 출력 토큰 요금을 50% 할인합니다. 예를 들어 deepseek-flash의 256K 이하 입력 요금은 피크 시간 백만 토큰당 0.30달러에서 비피크 시간 0.15달러로, 출력 요금은 1.50달러에서 0.75달러로 인하됩니다. [1]

### 딥시크 API의 동시 요청 한도와 user_id 격리 기능은 어떻게 작동하나요?

딥시크는 계정 단위로 deepseek-flash는 최대 2,500건, deepseek-v4-pro는 최대 500건의 동시 진행 요청(Concurrency)을 허용합니다. 개발자가 API 호출 시 user_id 필드에 최종 사용자 식별자를 포함하면, 해당 user_id당 동시 요청을 최대 10건으로 제한하여 특정 사용자가 전체 서비스 쿼터를 고갈시키는 것을 방지합니다. [2]

### DeepSeek-V3와 DeepSeek-R1이 기술적으로 주목받은 이유는 무엇인가요?

DeepSeek-V3(총 671B, 활성 37B 파라미터)는 KV 캐시 메모리를 대폭 줄이는 멀티헤드 잠재 어텐션(MLA)과 보조 손실 없는 DeepSeekMoE 라우터 및 FP8 학습을 결합해 학습 효율을 극대화했습니다. 이어 출시된 DeepSeek-R1은 대규모 순수 강화학습(GRPO)과 다단계 콜드 스타트 학습을 통해 프런티어급 추론 성능을 달성하고 이를 오픈소스 MIT 라이선스로 공개했습니다. [4][5]

### 딥시크의 호스팅 웹 앱과 API로 전송된 데이터는 어디에 저장되나요?

딥시크 개인정보 처리방침에 따라 호스팅 서비스로 전송된 프롬프트와 파일 데이터는 중국(중화인민공화국) 내 서버에 저장되며 항저우 딥시크 인공지능 유한공사가 관리합니다. 자체 데이터 레지던시가 필요한 조직은 오픈웨이트로 공개된 모델 가중치를 자체 서버에 독립적으로 구축하여 사용할 수 있습니다. [4][7]

## 인용 문장

- 딥시크의 프로덕션 API 모델인 deepseek-flash(DeepSeek-V4.1-Flash-1017)와 deepseek-v4-pro(DeepSeek-V4-Pro-0813)는 모두 100만 토큰 컨텍스트 윈도우와 최대 38만 4,000 출력 토큰을 지원한다. [1][3]
- 딥시크는 베이징 시간 00:00~08:00(UTC 16:00~00:00) 비피크 시간대에 캐시 미적중 입력 및 출력 토큰 요금을 50% 할인한다. [1]
- 딥시크 API의 동시 요청 한도는 deepseek-flash 2,500건, deepseek-v4-pro 500건이며, user_id 파라미터 사용 시 개별 사용자당 동시 요청을 10건으로 제한한다. [2]
- 2026년 11월 18일 딥시크는 채팅 완성 API 내에 추가 검색 쿼리 비용 없이 사용할 수 있는 서버 측 내장 웹 검색 및 웹페이지 수집 기능을 도입했다. [1][3]
- DeepSeek-V3는 토큰당 37B가 활성화되는 총 671B 규모의 MoE 모델이며, DeepSeek-R1은 2025년 1월 오픈소스 MIT 라이선스로 공개되었다. [4][5]

## 연표

- 2024-05: 멀티헤드 잠재 어텐션(MLA)과 236B/21B MoE 아키텍처를 도입한 DeepSeek-V2 기술 보고서 발표. [6]
- 2024-12: FP8 정밀도로 14.8조 토큰을 사전 학습한 671B(활성 37B) 규모의 전문가 혼합 모델 DeepSeek-V3 공개. [5]
- 2025-01: 강화학습 기반 추론 모델 DeepSeek-R1, DeepSeek-R1-Zero 및 6종의 증류 모델을 MIT 라이선스로 공개. [4]
- 2026-08-19: 100만 토큰 컨텍스트와 텍스트·이미지·오디오 멀티모달 입력을 지원하는 DeepSeek-V4-Pro-0813(deepseek-v4-pro) API 출시. [1][3]
- 2026-10-20: 고속 추론 엔드포인트인 deepseek-flash의 기반 모델로 DeepSeek-V4.1-Flash-1017 배포. [1][3]
- 2026-11-18: 채팅 완성 API에서 별도 검색 쿼리 요금 없이 서버 측 웹 검색 및 페이지 수집 기능 기본 지원 시작. [1][3]

## 출처

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (확인일 2026-11-23; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (확인일 2026-11-23; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 게시일 2026-11-18. https://api-docs.deepseek.com/updates (확인일 2026-11-23; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 게시일 2025-01-22. https://arxiv.org/abs/2501.12948 (확인일 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 게시일 2024-12-27. https://arxiv.org/abs/2412.19437 (확인일 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 게시일 2024-05-07. https://arxiv.org/abs/2405.04434 (확인일 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (확인일 2026-11-23; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "딥시크 (DeepSeek)." 버전 85c36234, 2026-11-23. https://mimirwiki.com/ko/wiki/deepseek
