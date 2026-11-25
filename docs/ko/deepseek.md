---
title: "딥시크 (DeepSeek)"
subtitle: "DeepSeek-V4, DeepSeek-R1, DeepSeek-V3 파운데이션 모델을 개발하는 중국의 인공지능 연구 기업"
canonical_url: https://mimirwiki.com/ko/wiki/deepseek
language: ko
page_class: entity
revision_sha256: 722ff3140e3af838bf5e1a65ad37d77765ead7c4c7a1937a8563f55a6c5e4d06
date_modified: 2026-11-25
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
  es: https://mimirwiki.com/es/wiki/deepseek
---

# 딥시크 (DeepSeek)

> 2026년 11월 기준 딥시크 API에는 컨텍스트 길이 1M, 최대 출력 384K인 두 모델 deepseek-flash(DeepSeek-V4.1-Flash-1017)와 deepseek-v4-pro(DeepSeek-V4-Pro-0813)가 있다. 비피크 요금은 피크 요금의 절반이며, Search, Fetch, OCR, 음성 API를 따로 제공한다. 2026년 11월 18일 12시(베이징 시간)부터 모델 호출 중에 실행되는 서버 측 검색과 웹 가져오기 도구 호출에는 요금을 받지 않는다. 이전 모델로는 DeepSeek-V3(전체 671B, 활성 37B 파라미터)와 추론 모델 DeepSeek-R1이 있다.

딥시크(DeepSeek)는 중국의 인공지능(AI) 기업으로, 서비스는 중국에 등록 주소를 둔 Hangzhou DeepSeek Artificial Intelligence Co., Ltd.(항저우 딥시크 인공지능 유한공사)가 제공한다. 멀티헤드 잠재 어텐션(Multi-head Latent Attention, MLA)과 DeepSeekMoE 아키텍처를 기반으로 DeepSeek-V2, DeepSeek-V3, 강화학습 추론 모델 DeepSeek-R1, API로 제공하는 DeepSeek-V4 시리즈 등 대규모 언어 모델을 개발한다.

**다른 이름:** DeepSeek, Hangzhou DeepSeek Artificial Intelligence Co., Ltd., 항저우 딥시크 인공지능 유한공사, 深度求索

## 핵심 정보

- **운영 법인:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **주력 프로덕션 모델:** deepseek-flash (DeepSeek-V4.1-Flash-1017) 및 deepseek-v4-pro (DeepSeek-V4-Pro-0813) (기준 2026-11-25) [1]
- **컨텍스트 및 최대 출력:** 100만(1M) 토큰 컨텍스트 윈도우; 최대 38만 4,000(384K) 출력 토큰 (기준 2026-11-25) [1]
- **주요 오픈웨이트 모델:** DeepSeek-R1 (MIT 라이선스, 2025년 1월) 및 DeepSeek-V3 (671B/37B MoE, 2024년 12월) [4]

## 기본 정보

- **정식 법인명:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **등록 주소:** 중국 [7]
- **핵심 아키텍처:** 멀티헤드 잠재 어텐션(MLA), DeepSeekMoE, 다중 토큰 예측(MTP) [5]
- **API 주력 모델 (2026년 11월):** DeepSeek-V4.1-Flash-1017 (deepseek-flash), DeepSeek-V4-Pro-0813 (deepseek-v4-pro) [1]
- **API 컨텍스트 및 출력 한도:** 컨텍스트 길이 1M / 최대 출력 384K [1]
- **API 동시 요청 한도:** deepseek-flash 2,500건 / deepseek-v4-pro 500건 (user_id 지정 시 사용자당 10건) [2]
- **멀티모달 및 도구 API:** Search API, Fetch API, 파일 파싱·OCR API, 음성 인식(ASR), 음성 합성(TTS) [1]
- **오픈소스 라이선스 (R1):** MIT 라이선스 (DeepSeek-R1 및 증류 모델 가중치·코드) [4]

## 기업 개요 및 아키텍처 기반

딥시크의 서비스는 Hangzhou DeepSeek Artificial Intelligence Co., Ltd.가 제공한다 [7]. 이 회사는 모델 아키텍처에 관한 기술 보고서를 공개했고, 전문가 혼합(Mixture-of-Experts, MoE) 모델과 추론 모델을 내놓았다 [4][5][6].

딥시크의 모델은 **DeepSeek-V2**(2024년 5월, 전체 236B 파라미터 중 토큰당 21B 활성)에서 도입하고 **DeepSeek-V3**(2024년 12월, 전체 671B 파라미터 중 토큰당 37B 활성)에서도 채택한 두 가지 아키텍처를 쓴다 [5][6]: - **멀티헤드 잠재 어텐션(MLA)**: 키-값(KV) 캐시를 잠재 벡터로 압축해 추론 효율을 높인다 [5][6]. - **DeepSeekMoE**: 라우팅 전문가와 공유 전문가를 쓰는 희소 연산 구조다. DeepSeek-V3는 여기에 보조 손실 없는 부하 분산 방식과 다중 토큰 예측(MTP) 학습 목표를 더했다 [5][6]. DeepSeek-V3는 FP8 혼합 정밀도 학습으로 14.8조 토큰을 사전 학습했으며, 기술 보고서는 전체 학습에 H800 GPU 278만 8,000시간이 들었다고 밝혔다 [5].

## DeepSeek-R1과 강화학습 기반 추론 모델

2025년 1월 22일 arXiv에 제출된 DeepSeek-R1 논문은 **DeepSeek-R1**과 **DeepSeek-R1-Zero**를 소개한다. 논문은 사람이 라벨을 붙인 추론 과정 없이 순수 강화학습(RL)만으로 대규모 언어 모델의 추론 능력을 끌어낼 수 있으며, 학습 중에 자기 성찰과 검증 같은 행동이 나타났다고 보고했다 [4].

`DeepSeek-R1-Zero`는 강화학습 전의 지도 미세조정 단계 없이 그룹 상대 정책 최적화(GRPO)로 학습했다. 이 모델은 가독성이 낮고 언어가 섞이는 문제가 있어, `DeepSeek-R1`은 콜드 스타트 사고 사슬 데이터, 거부 샘플링, 강화학습, 지도 미세조정을 결합한 다단계 학습을 거쳤다 [4]. 논문은 수학 과제에서 OpenAI-o1-1217과 비슷한 성능을 보였고, 엔지니어링 중심 코딩 과제에서는 OpenAI-o1-1217이 DeepSeek-R1보다 높았다고 보고했다 [4]. 딥시크는 Qwen과 Llama 모델을 기반으로 한 1.5B~70B 파라미터의 증류 모델 6종도 공개했다 [4].

## DeepSeek-V4 시리즈, 요금 체계 및 개발자 플랫폼 (2026년)

딥시크 API(`api.deepseek.com`)는 2026년 4월 24일 DeepSeek-V4-Pro와 DeepSeek-V4-Flash를 추가했다 [3]. 2026년 11월 기준 요금 문서에는 두 모델이 있으며, 둘 다 **컨텍스트 길이 1M**, **최대 출력 384K**다 [1]:

| 모델 이름 | 모델 버전 | 입력, 캐시 적중 (피크 / 비피크) | 입력, 캐시 미적중 (피크 / 비피크) | 출력 (피크 / 비피크) | 동시 요청 한도 |
| --- | --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` | $0.006 / $0.003 | $0.30 / $0.15 | $1.20 / $0.60 | 2,500 |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` | $0.044 / $0.022 | $1.32 / $0.66 | $3.96 / $1.98 | 500 |

요금은 100만 토큰당 가격이다 [1][2]. 비피크 요금은 피크 요금의 절반이다. 피크 시간은 중국 공휴일을 제외한 월요일~금요일 01:00~04:00과 06:00~10:00(UTC)이다 [1]. 두 모델 모두 사고 모드와 비사고 모드, JSON 출력, 도구 호출, Responses API, Anthropic 형식 API를 지원한다. 비전은 `deepseek-flash`만 지원하고 `deepseek-v4-pro`는 지원하지 않는다 [1]. 이전 모델 이름인 `deepseek-v4-flash`와 `deepseek-v4-flash-vision-exp`로 보낸 요청은 DeepSeek-V4.1-Flash-1017이 처리한다 [1].

변경 기록에 따르면 DeepSeek-V4-Pro 정식(GA) 버전은 2026년 8월 13일에 적용됐고, DeepSeek-V4.1-Flash는 2026년 9월 10일에 출시됐으며, 2026년 10월 17일에 DeepSeek-V4.1-Flash-1017로 업그레이드됐다 [3].

## 내장 웹 검색, 유틸리티 API 및 동시성 제어

2026년 11월 13일 딥시크는 `deepseek-flash` 모델의 Messages, Responses, Chat Completions API에서 웹 검색, 파일 입력, URL 읽기, 모델 안전 기능을 개발자에게 열었고, Search와 Fetch, OCR, ASR, TTS를 독립 API로도 제공했다 [3]. 요금 문서의 가격은 다음과 같다 [1]: - **Search API(텍스트)**: 성공한 요청 1,000건당 $0.75 [1]. - **Fetch API**: 성공한 요청 1,000건당 $0.75 [1]. - **파일 파싱·OCR API**: 1,000쪽당 $0.225 [1]. - **음성 인식(ASR)**: 오디오 1시간당 정가 $0.116, 기간 한정 가격 $0.058 [1]. - **음성 합성(TTS)**: 1만 자당 정가 $0.45, 기간 한정 가격 $0.225 [1].

2026년 11월 18일 12시(베이징 시간, UTC+8)부터 모델 호출 중에 실행되는 서버 측 검색과 웹 가져오기 도구 호출에는 요금을 받지 않는다. 반환된 결과는 모델 컨텍스트에 추가되어 모델 토큰 사용량으로 과금된다 [1].

동시 요청 한도는 계정 단위로 계산하며 `deepseek-flash`는 2,500, `deepseek-v4-pro`는 500이다. 한도를 넘는 요청은 HTTP 429 오류를 받는다 [2]. 개발자는 `user_id` 파라미터를 보낼 수 있고, 딥시크는 이를 콘텐츠 안전 격리, KVCache 격리, 스케줄링 격리에 쓴다. 일반 API 사용자는 모든 `user_id`를 합쳐 한도를 계산한다. 동시 요청 한도를 늘린 계정은 `user_id`마다 `deepseek-flash` 2,500, `deepseek-v4-pro` 500의 한도도 함께 적용된다 [2].

## 데이터 거버넌스 및 개인정보 처리방침

딥시크 개인정보 처리방침(2026년 2월 10일 최종 수정)에 따르면 서비스는 중국에 등록 주소를 둔 Hangzhou DeepSeek Artificial Intelligence Co., Ltd.가 제공하고 관리한다 [7]. 방침은 딥시크가 개인정보를 **중화인민공화국**에서 수집, 처리, 저장한다고 밝힌다 [7]. 모델 학습이나 기술 최적화에 개인정보를 쓰는 것을 거부할 권리도 적혀 있다 [7]. 개발자가 딥시크 오픈 플랫폼으로 만든 애플리케이션의 최종 사용자 개인정보에는 이 방침이 적용되지 않으며, 그 경우 애플리케이션을 운영하는 개발자가 개인정보 처리의 관리자라고 방침은 설명한다 [7]. 딥시크는 DeepSeek-R1 증류 모델도 공개했다 [4].

## 자주 묻는 질문

### 2026년 11월 기준 딥시크(DeepSeek)의 주력 API 모델은 무엇인가요?

딥시크 API에는 deepseek-flash(모델 버전 DeepSeek-V4.1-Flash-1017)와 deepseek-v4-pro(모델 버전 DeepSeek-V4-Pro-0813) 두 모델이 있습니다. 둘 다 컨텍스트 길이는 1M, 최대 출력은 384K입니다. [1][3]

### 딥시크 API의 피크 및 비피크 시간대 할인 요금제는 어떻게 운영되나요?

비피크 요금은 피크 요금의 절반입니다. 피크 시간은 중국 공휴일을 제외한 월요일~금요일 01:00~04:00과 06:00~10:00(UTC)이고, 그 밖의 시간은 모두 비피크입니다. 예를 들어 deepseek-flash의 캐시 미적중 입력은 100만 토큰당 피크 $0.30, 비피크 $0.15이고, 출력은 피크 $1.20, 비피크 $0.60입니다. [1]

### 딥시크 API의 동시 요청 한도와 user_id 격리 기능은 어떻게 작동하나요?

동시 요청 한도는 계정 단위로 계산하며 deepseek-flash는 2,500, deepseek-v4-pro는 500입니다. 한도를 넘는 요청은 HTTP 429 오류를 받습니다. 일반 API 사용자는 모든 user_id를 합쳐 한도를 계산합니다. 동시 요청 한도를 늘린 계정은 user_id마다 deepseek-flash 2,500, deepseek-v4-pro 500의 한도도 함께 적용됩니다. [2]

### DeepSeek-V3와 DeepSeek-R1이 기술적으로 주목받은 이유는 무엇인가요?

DeepSeek-V3(총 671B, 활성 37B 파라미터)는 KV 캐시 메모리를 대폭 줄이는 멀티헤드 잠재 어텐션(MLA)과 보조 손실 없는 DeepSeekMoE 라우터 및 FP8 학습을 결합해 학습 효율을 극대화했습니다. 이어 출시된 DeepSeek-R1은 대규모 순수 강화학습(GRPO)과 다단계 콜드 스타트 학습을 통해 프런티어급 추론 성능을 달성하고 이를 오픈소스 MIT 라이선스로 공개했습니다. [4][5]

### 딥시크의 호스팅 웹 앱과 API로 전송된 데이터는 어디에 저장되나요?

딥시크 개인정보 처리방침은 개인정보를 중화인민공화국에서 수집, 처리, 저장하며, 서비스는 Hangzhou DeepSeek Artificial Intelligence Co., Ltd.가 제공하고 관리한다고 밝힙니다. 개발자가 딥시크 오픈 플랫폼으로 만든 애플리케이션의 최종 사용자에게는 이 방침이 적용되지 않습니다. [4][7]

## 인용 문장

- 딥시크의 프로덕션 API 모델인 deepseek-flash(DeepSeek-V4.1-Flash-1017)와 deepseek-v4-pro(DeepSeek-V4-Pro-0813)는 모두 100만 토큰 컨텍스트 윈도우와 최대 38만 4,000 출력 토큰을 지원한다. [1][3]
- 딥시크 API의 비피크 요금은 피크 요금의 절반이며, 피크 시간은 중국 공휴일을 제외한 월요일~금요일 01:00~04:00과 06:00~10:00(UTC)이다. [1]
- 딥시크 API의 계정 단위 동시 요청 한도는 deepseek-flash 2,500, deepseek-v4-pro 500이며, 한도를 늘린 계정은 user_id마다 같은 한도가 함께 적용된다. [2]
- 2026년 11월 18일 12시(베이징 시간)부터 딥시크 모델 호출 중에 실행되는 서버 측 검색과 웹 가져오기 도구 호출에는 요금을 받지 않으며, 반환된 결과는 모델 토큰 사용량으로 과금된다. [1]
- DeepSeek-V3는 토큰당 37B가 활성화되는 총 671B 규모의 MoE 모델이며, DeepSeek-R1은 2025년 1월 오픈소스 MIT 라이선스로 공개되었다. [4][5]

## 연표

- 2024-05: 멀티헤드 잠재 어텐션(MLA)과 236B/21B MoE 아키텍처를 도입한 DeepSeek-V2 기술 보고서 발표. [6]
- 2024-12: FP8 정밀도로 14.8조 토큰을 사전 학습한 671B(활성 37B) 규모의 전문가 혼합 모델 DeepSeek-V3 공개. [5]
- 2025-01: 강화학습 기반 추론 모델 DeepSeek-R1, DeepSeek-R1-Zero 및 6종의 증류 모델을 MIT 라이선스로 공개. [4]
- 2026-08-13: DeepSeek-V4-Pro 정식(GA) 버전이 앱, 웹, API에 적용됨(모델 이름 deepseek-v4-pro). [1][3]
- 2026-10-17: DeepSeek V4.1 Flash가 DeepSeek-V4.1-Flash-1017로 업그레이드됨(모델 이름 deepseek-flash). [1][3]
- 2026-11-18: 베이징 시간 12시부터 모델 호출 중에 실행되는 서버 측 검색과 웹 가져오기 도구 호출에 요금을 받지 않음. [1]

## 출처

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (확인일 2026-11-25; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (확인일 2026-11-25; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 게시일 2026-11-13. https://api-docs.deepseek.com/updates (확인일 2026-11-25; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 게시일 2025-01-22. https://arxiv.org/abs/2501.12948 (확인일 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 게시일 2024-12-27. https://arxiv.org/abs/2412.19437 (확인일 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 게시일 2024-05-07. https://arxiv.org/abs/2405.04434 (확인일 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (확인일 2026-11-25; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "딥시크 (DeepSeek)." 버전 722ff314, 2026-11-25. https://mimirwiki.com/ko/wiki/deepseek
