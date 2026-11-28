---
title: "llama.cpp (라마닷시피피)"
subtitle: "ggml-org가 유지·관리하는 로컬 대형언어모델(LLM) 실행용 오픈소스 C/C++ 추론 엔진"
canonical_url: https://mimirwiki.com/ko/wiki/llama-cpp
language: ko
page_class: entity
revision_sha256: a99e7586abb2c4f75e06f7a83d9fda36ae9be12484a4b29e2c5960cf74d1fa98
date_modified: 2026-11-28
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/ko/wiki/llama-cpp.md
  txt: https://mimirwiki.com/ko/wiki/llama-cpp.txt
  json: https://mimirwiki.com/ko/wiki/llama-cpp.json
  jsonld: https://mimirwiki.com/ko/wiki/llama-cpp.jsonld
translations:
  en: https://mimirwiki.com/wiki/llama-cpp
---

# llama.cpp (라마닷시피피)

> llama.cpp는 ggml-org가 관리하는 로컬 대형언어모델 실행용 오픈소스 C/C++ 추론 엔진이다. 2026년 11월 26일 공개된 AMD 라이젠·라데온 벤치마크 대시보드는 문맥 깊이 0에서 입력 512토큰 처리(PP512)와 출력 128토큰 생성(TG128) 속도를 모델·빌드·양자화별로 나누어 측정한다.

llama.cpp(라마닷시피피)는 ggml-org가 개발·유지하는 오픈소스 C/C++ 추론 엔진으로, 개인용 컴퓨터와 워크스테이션의 CPU·GPU에서 대형언어모델(LLM)을 로컬 실행할 수 있게 한다. 표준 성능 측정 도구인 `llama-bench`를 포함하며, 사전 빌드 배포 프로젝트 `llama-install.sh`와 별도 데스크톱 제품인 Llama 앱의 기반을 이룬다. 2026년 11월 26일 ggml-org는 허깅페이스(Hugging Face)에 AMD 라이젠(Ryzen)·라데온(Radeon)용 벤치마크 대시보드를 공개해 프롬프트 처리(PP512)와 토큰 생성(TG128) 속도를 모델·빌드·양자화별로 분리 비교할 수 있게 했다.

**다른 이름:** llama.cpp, 라마닷시피피

## 핵심 정보

- **개발·관리 주체:** ggml-org (github.com/ggml-org/llama.cpp) (기준 2026-11-28) [3]
- **구현 언어:** C / C++ (기준 2026-11-28) [3]
- **AMD 벤치마크 대시보드 공개:** 2026년 11월 26일 (Radeon 8060S gfx1151, Radeon AI Pro R9700S gfx1201) (기준 2026-11-26) [1]
- **핵심 측정 지표:** PP512(입력 512토큰 처리) 및 TG128(출력 128토큰 생성), 문맥 깊이 0 기준 (기준 2026-11-26) [1]

## 기본 정보

- **소프트웨어 유형:** 오픈소스 로컬 LLM 추론 엔진 [3]
- **개발 조직:** ggml-org [3]
- **개발 언어:** C, C++ [3]
- **벤치마크 도구:** llama-bench [4]
- **AMD 대시보드 초기 장비 (2026-11):** Radeon 8060S (gfx1151), Radeon AI Pro R9700S (gfx1201) [1]
- **연관 데스크톱 앱:** Llama 앱 (llama-install.sh 기반 배포) [6]

## llama.cpp 구조와 로컬 추론 생태계

llama.cpp는 `ggml-org`가 C/C++로 개발하는 오픈소스 추론 엔진으로, 클라우드 API 없이 로컬 장비에서 대형언어모델을 실행할 수 있게 한다.[3] 저장소에는 다양한 양자화 형식과 백엔드의 처리량을 재현 가능하게 측정하는 `llama-bench` 도구가 포함되어 있으며, 사전 빌드 바이너리를 배포하는 `llama-install.sh`는 별도 데스크톱 앱인 `llama.app`의 설치 기반으로도 쓰인다.[1][4][6]

## 프롬프트 처리(PP512)와 답변 생성(TG128) 속도의 분리 측정 방식

2026년 11월 26일 ggml-org는 허깅페이스 스페이스(Hugging Face Spaces)에 AMD 라이젠·라데온용 벤치마크 대시보드를 공개했다. 초기 선택 장비는 Radeon 8060S(`gfx1151`)와 Radeon AI Pro R9700S(`gfx1201`)이다.[1][2] 대시보드는 추론 성능을 단일 점수로 묶지 않고, 문맥 깊이 0(`n_depth=0`)에서 시작하는 두 가지 초당 토큰 처리량(평균 `avg_ts`)으로 나누어 표시한다.[1]

| 측정 항목 | 측정 작업 | 시작 문맥 깊이 | 의미 |
| --- | --- | --- | --- |
| PP512 | 생성 없이 입력 512토큰 처리 | 0 (`n_depth=0`) | 프롬프트 입력·사전처리(prefill) 속도 |
| TG128 | 기존 문맥 없이 출력 128토큰 생성 | 0 (`n_depth=0`) | 순수 답변 토큰 생성(decoding) 속도 |
| Context scaling 탭 | 문맥 길이가 늘어날 때의 토큰 생성 속도 | 증가하는 문맥 | 긴 문맥에서의 메모리 대역폭 영향 |

이용자는 대시보드 사이드바에서 하드웨어, 모델, llama.cpp 빌드, 양자화 설정을 골라 시간에 따른 성능 변화를 비교할 수 있다.[1][2]

## 공개 주간 자동 측정 워크플로

ggml-org는 벤치마크 원시 결과뿐 아니라 `llama-install.sh` 저장소의 `bench-gfx1151.yml` 같은 공개 GitHub Actions 워크플로를 통해 매주 사전 빌드 바이너리를 `llama-bench`로 측정한다.[1][5] 이를 통해 커널·빌드·모델 변경이 AMD 로컬 추론 속도에 미치는 영향을 누구나 투명하게 확인할 수 있다.[1]

## 2026년 11월 기준 벤치마크 해석 한계 및 미확인 사항

2026년 11월 28일 기준 AMD 대시보드 수치는 특정 기준 장비와 빈 문맥·표준 설정에서 측정된 참고값이며, 개별 독자의 PC나 실제 앱 환경에서의 체감 속도와 다를 수 있다.[1] 또한 초당 토큰 처리량은 연산 속도만 보여줄 뿐 모델 답변의 정확도나 품질을 판단하는 지표가 아니다.[1][4]

## 자주 묻는 질문

### llama.cpp는 무엇인가요?

ggml-org가 유지·관리하는 오픈소스 C/C++ 추론 엔진으로, 개인용 PC와 워크스테이션의 CPU·GPU에서 대형언어모델(LLM)을 로컬 실행할 때 쓰입니다. [3]

### 프롬프트 처리와 답변 생성 속도는 어떻게 다르게 측정하나요?

2026년 11월 26일 공개된 AMD 벤치마크 대시보드에서 PP512는 생성 없이 입력 512토큰을 처리하는 속도를, TG128은 기존 문맥 없이 출력 128토큰을 생성하는 속도를 각각 초당 토큰 수로 측정합니다. 두 테스트 모두 문맥 깊이 0에서 시작하며, 문맥 길이에 따른 변화는 별도 Context scaling 탭에서 확인합니다. [1][2]

### AMD 벤치마크 대시보드의 초기 지원 장비는 무엇인가요?

초기 선택지는 AMD Radeon 8060S(gfx1151)와 Radeon AI Pro R9700S(gfx1201)이며, 공개 GitHub 워크플로를 통해 매주 자동 측정됩니다. [1][5]

### 토큰 처리량이 높으면 답변 품질도 더 좋은가요?

아닙니다. PP512와 TG128은 특정 하드웨어·빌드·양자화 조건에서의 실행 속도만 측정하며, 모델 답변의 정확성이나 품질을 나타내지 않습니다. [1][4]

## 인용 문장

- 2026년 11월 26일 ggml-org는 Radeon 8060S(gfx1151)와 Radeon AI Pro R9700S(gfx1201)를 초기 대상으로 하는 llama.cpp x AMD 벤치마크 대시보드를 허깅페이스에 공개했다. [1][2]
- 대시보드는 문맥 깊이 0에서 입력 512토큰 처리(PP512)와 출력 128토큰 생성(TG128)을 각각 초당 평균 토큰 수로 분리 측정한다. [1]
- ggml-org는 llama.app의 기반인 llama-install.sh의 사전 빌드 바이너리를 공개 GitHub 워크플로로 매주 자동 벤치마크한다. [1][5][6]
- llama.cpp는 C/C++로 구현된 오픈소스 엔진이며 자체 측정 도구 llama-bench를 제공한다. [3][4]

## 연표

- 2026-11-26: ggml-org가 허깅페이스에 AMD 라이젠·라데온용 llama.cpp 공개 벤치마크 대시보드를 발표한다. [1][2]

## 출처

1. Introducing the llama.cpp benchmark dashboard for AMD Ryzen and Radeon hardware. ggml-org (Hugging Face Blog). 게시일 2026-11-26. https://huggingface.co/blog/ggml-org/llamacpp-amd-bench (확인일 2026-11-28; tier 2: academic or news)
2. llama.cpp x AMD Performance Explorer. ggml-org (Hugging Face Spaces). https://ggml-org-llamacpp-amd-bench.static.hf.space/index.html (확인일 2026-11-28; tier 2: academic or news)
3. ggml-org/llama.cpp: LLM inference in C/C++. GitHub (ggml-org). https://github.com/ggml-org/llama.cpp (확인일 2026-11-28; tier 2: academic or news)
4. llama-bench README. ggml-org (GitHub). https://raw.githubusercontent.com/ggml-org/llama.cpp/master/tools/llama-bench/README.md (확인일 2026-11-28; tier 2: academic or news)
5. bench-gfx1151.yml Benchmark Workflow. ggml-org (GitHub). https://github.com/ggml-org/llama-install.sh/blob/master/.github/workflows/bench-gfx1151.yml (확인일 2026-11-28; tier 2: academic or news)
6. Llama - Your AI, on your computer. ggml-org / Llama. https://llama.app/ (확인일 2026-11-28; tier 3: official site)

## 이 문서 인용하기

Mimirwiki. "llama.cpp (라마닷시피피)." 버전 a99e7586, 2026-11-28. https://mimirwiki.com/ko/wiki/llama-cpp
