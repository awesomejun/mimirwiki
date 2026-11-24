---
title: "Lean 정리 증명기 (Lean 4)"
subtitle: "오픈소스 함수형 프로그래밍 언어이자 대화형 정리 증명기"
canonical_url: https://mimirwiki.com/ko/wiki/lean-theorem-prover
language: ko
page_class: entity
revision_sha256: 9e947be69963840e1c5fb0e0fcbe5f5af16339a9fc49e3a1d333bda47057505f
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ko/wiki/lean-theorem-prover.md
  txt: https://mimirwiki.com/ko/wiki/lean-theorem-prover.txt
  json: https://mimirwiki.com/ko/wiki/lean-theorem-prover.json
  jsonld: https://mimirwiki.com/ko/wiki/lean-theorem-prover.jsonld
translations:
  en: https://mimirwiki.com/wiki/lean-theorem-prover
---

# Lean 정리 증명기 (Lean 4)

> Lean(Lean 4)은 Apache-2.0 라이선스로 공개되고 Lean FRO가 지원하는 오픈소스 프로그래밍 언어이자 정리 증명기이다. 2026-11-24 기준 최신 정식판은 v4.36.0(2026-11-16), 최신 시험판은 v4.37.0-rc1(2026-11-18)이며, 2026-11-23 Google DeepMind가 Lean 4 양자 프로그램 검증 라이브러리·문제 명세·해답을 공개했다.

Lean은 수학 증명과 소프트웨어의 형식 검증(formal verification)을 작성·검사하기 위한 오픈소스 프로그래밍 언어이자 대화형 정리 증명기(proof assistant)이다. 저장소는 Apache-2.0 라이선스로 공개되어 있고 Lean 집중 연구 기구(Lean Focused Research Organization, Lean FRO)가 개발을 지원한다. Lean 4의 첫 정식판(v4.0.0)은 2023-09-08 배포되었다. 2026-11-24 기준 최신 정식판은 Lean 4.36.0(2026-11-16 배포)이며, 2026-11-18 정식판 전 시험 버전(release candidate)인 4.37.0-rc1이 공개되었고 2026-11-19 Mathlib 시험판 배포 및 2026-11-23 Google DeepMind의 Lean 4 양자 프로그램 검증 자료 공개가 이어졌다.

**다른 이름:** Lean 4, Lean, Lean theorem prover

## 핵심 정보

- **최신 정식판:** v4.36.0 (2026-11-16) (기준 2026-11-24) [5]
- **최신 시험판:** v4.37.0-rc1 (2026-11-18, release candidate) (기준 2026-11-24) [6]
- **Lean 4 첫 정식판:** v4.0.0 (2023-09-08) [4]
- **라이선스:** Apache-2.0 [3]

## 기본 정보

- **유형:** 프로그래밍 언어 및 대화형 정리 증명기 [1]
- **지원 조직:** Lean Focused Research Organization (Lean FRO) [2]
- **라이선스:** Apache-2.0 [3]
- **Lean 4 첫 정식판:** v4.0.0 (2023-09-08) [4]
- **최신 정식판:** v4.36.0 (2026-11-16) (기준 2026-11-24) [5]
- **최신 시험판:** v4.37.0-rc1 (2026-11-18) (기준 2026-11-24) [6]
- **대표 수학 라이브러리:** Mathlib (mathlib4) [4]
- **소스 저장소:** github.com/leanprover/lean4 [3]
- **공식 웹사이트:** lean-lang.org [1]

## Lean 개요 및 지원 조직

Lean은 형식화된 수학 증명과 검증된 코드를 작성하기 위한 오픈소스 프로그래밍 언어이자 정리 증명기(proof assistant)이다.[1][3] Lean 4 저장소는 Apache-2.0 라이선스로 공개되어 있으며 Lean 집중 연구 기구(Lean Focused Research Organization, Lean FRO)는 Lean의 성장을 지원한다고 밝히고 있다.[2][3]

Lean FRO는 Lean의 핵심 시스템과 기능을 발전시키는 것을 임무로 밝히고, 중점 분야로 확장성, 사용성, 증명 자동화, 문서화, 다양한 커뮤니티, AI 연구와 검증된 코드 합성 지원을 든다.[2] 공식 웹사이트가 소개하는 내장 자동화 기능에는 귀납법·대수 추론·SMT 유사 추론을 수행하는 `grind` 전술(tactic)과 비트벡터 등식을 판정하는 `bv_decide`가 포함된다.[1] Lean 4.0.0 배포 기록은 Mathlib(`mathlib4`)을 Lean의 주요 수학 라이브러리로 소개하며, 프로젝트는 `lake` 빌드 도구와 `elan` 도구 모음 관리자로 구성된다.[4][9]

## Lean 4 배포 연혁 및 2026년 11월 버전

Lean 4는 2023-09-08 첫 정식판인 `v4.0.0`을 배포했으며, 당시 개발진은 약 월간 주기로 마이너 버전을 정기 배포할 계획이라고 밝혔다.[4]

| 버전 | 구분 | 배포일 | 비고 |
| --- | --- | --- | --- |
| v4.0.0 | 정식판 | 2023-09-08 | Lean 4 첫 정식판 |
| v4.36.0 | 정식판(2026-11-24 기준 최신) | 2026-11-16 | GitHub 기준 최신 정식 배포 태그 |
| v4.37.0-rc1 | 시험판(release candidate) | 2026-11-18 | 370건 변경 반영, 정식판 전 변경 가능 |

2026-11-24 기준 GitHub에 최신 정식판으로 등록된 버전은 2026-11-16 배포된 `v4.36.0`이다.[5] 2026-11-18 공개된 `v4.37.0-rc1`은 정식판이 아닌 출시 후보 시험판(release candidate)임이 변경 기록에 명시되어 있다.[6] 해당 시험판에는 기능 추가 71건, 버그 수정 159건, 성능 개선 108건, 리팩터링 7건, 테스트 개선 4건, 문서 개선 1건, 기타 20건 등 총 370건의 변경이 포함되었으며, 그중 하나는 `shiftLeft.threshold`(기본값 65536) 옵션 추가이다.[6] 이어 2026-11-19 `leanprover-community/mathlib4`가 도구 버전을 `v4.37.0-rc1`로 올린 시험판 태그를 공개했다.[7]

## Lean의 형식 검증 활용과 2026년 11월 DeepMind 검증 자료 공개

Lean FRO는 Lean이 쓰이는 분야로 형식 수학과 소프트웨어·하드웨어 검증을 든다.[1][2] 2026-11-23 Google DeepMind는 [구글 제미나이](https://mimirwiki.com/ko/wiki/google-gemini)(Gemini 4) 에이전트 팀이 탐색하고 Lean 4로 검증한 양자 프로그램의 검증 자료를 GitHub에 공개한다고 발표했다.[8][9]

Apache-2.0 라이선스로 공개된 저장소(`google-deepmind/formal-quantum-computation`)는 고전 변수를 포함한 양자 호어 논리(quantum Hoare logic)에 기반하며 `Mathlib4`와 `Physlib`의 `QuantumInfo`에 의존한다.[9] 저장소는 핵심 라이브러리(`QuantumComputation`), 형식 문제 명세 및 벤치마크 과제(`QuantumComputationSpecs`), 그리고 보고된 프로그램과 Lean 증명을 담은 `discoveries` 브랜치 세 부분으로 나뉜다.[9][12]

관련 연구 프리프린트(`arXiv:2611.09822v3`)는 2026-11-06 최초 제출되고 2026-11-16 개정되었으며, 2026-11-23 소식은 연구의 신규 제출이 아니라 Lean 라이브러리·명세·증명 자료의 공개 발표로 같은 날 The Next Web과 QubitWire가 보도했다.[8][10][11][12] DeepMind와 QubitWire는 보고된 자원 절감 수치(관성 가둠 핵융합 계산에서 큐비트 수와 연산 수를 결합한 비용 지표 11.8배 절감, 오류 정정 큐비트 5,650개에서 4,338개로 감소 등)가 실물 양자 컴퓨터에서 측정한 실행 속도가 아니라 형식 명세와 비용 모델에 대한 수학적 검증 결과임을 명시하며, 저장소는 고전 연산과 제어 흐름의 명시적 비용 모델링을 향후 과제로 적고 있다.[8][9][12]

## Lean 형식 검증의 범위와 한계

DeepMind 저장소 공개에 대한 독립 보도에서 지적되었듯, 기계가 검사한 Lean 증명은 프로그램이 정해진 명세와 비용 가정 아래 조건을 만족함을 확인해 줄 뿐, 그 명세나 비용 모델이 실제 물리 하드웨어의 모든 병목을 반영하는지 또는 외부 제3자가 결과를 재현했는지까지 스스로 입증하지는 않는다.[12]

## 자주 묻는 질문

### 2026-11-24 기준 Lean 4의 최신 정식 버전은 무엇인가요?

2026-11-24 기준 Lean 4의 최신 정식판은 2026-11-16 배포된 v4.36.0입니다. 2026-11-18 공개된 4.37.0-rc1은 정식판이 아닌 출시 후보 시험판(release candidate)입니다. [5][6]

### Lean 생태계에서 Mathlib은 어떤 역할을 하나요?

Mathlib(mathlib4)은 Lean의 주요 수학 라이브러리입니다. 2026-11-19에는 Lean 4.37.0-rc1 도구 버전을 반영한 Mathlib v4.37.0-rc1 시험판이 공개되었습니다. [4][7]

### Google DeepMind가 2026-11-23 발표한 Lean 관련 내용은 무엇인가요?

Google DeepMind는 2026년 11월 프리프린트에서 다룬 양자 프로그램의 Lean 4 라이브러리, 형식 문제 명세, 검증된 해답을 Apache-2.0 라이선스 GitHub 저장소(formal-quantum-computation)로 공개한다고 발표했습니다. [8][9][10]

### DeepMind의 2026-11-23 발표는 실물 양자 컴퓨터 시연이나 성능 측정인가요?

아닙니다. 2026-11-23 발표는 Lean 검증 자료의 공개이며, 보고된 자원 절감 수치는 실물 양자 컴퓨터 실행 시간이 아니라 형식 명세와 수학적 비용 모델에 근거한 결과입니다. [8][12]

## 인용 문장

- Lean은 Apache-2.0 라이선스로 공개되고 Lean Focused Research Organization이 지원하는 오픈소스 프로그래밍 언어이자 정리 증명기이다. [1][2][3]
- Lean 4의 첫 정식판인 v4.0.0은 2023-09-08 배포되었다. [4]
- 2026-11-24 기준 GitHub에 등록된 Lean 4의 최신 정식판은 2026-11-16 배포된 v4.36.0이다. [5]
- Lean 4.37.0-rc1은 370건의 변경을 포함한 출시 후보 시험판으로 2026-11-18 공개되었고, Mathlib은 이를 반영한 v4.37.0-rc1 시험판을 2026-11-19 공개했다. [6][7]
- Google DeepMind는 2026-11-23 Lean 4 양자 프로그램 검증 라이브러리, 문제 명세, 검증된 해답을 google-deepmind/formal-quantum-computation 저장소로 공개했다. [8][9]
- 관련 프리프린트 arXiv:2611.09822v3은 2026-11-06 제출 및 2026-11-16 개정되었으며, 보고된 회로 비용 수치는 실물 양자 하드웨어 실행이 아닌 형식 모델에서 도출된 값이다. [10][12]

## 연표

- 2023-09-08: Lean 4의 첫 정식판 v4.0.0이 배포되었다. [4]
- 2026-11-06: Gemini 4 에이전트와 Lean 형식 검증으로 양자 프로그램을 탐색한 프리프린트 arXiv:2611.09822가 최초 제출되었다(2026-11-16 v3 개정). [10]
- 2026-11-16: Lean v4.36.0 정식판이 GitHub에 배포되었다. [5]
- 2026-11-18: 370건의 변경이 반영된 출시 후보 시험판 Lean 4.37.0-rc1이 공개되었다. [6]
- 2026-11-19: Mathlib(mathlib4)이 Lean 4.37.0-rc1 도구 버전을 반영한 시험판 v4.37.0-rc1을 공개했다. [7]
- 2026-11-23: Google DeepMind가 Lean 4 양자 프로그램 검증 라이브러리, 문제 명세, 검증된 해답을 GitHub에 공개한다고 발표했다. [8][9]

## 출처

1. Lean Programming Language. Lean Focused Research Organization. https://lean-lang.org/ (확인일 2026-11-24; tier 3: official site)
2. Lean Focused Research Organization. Lean Focused Research Organization. https://lean-fro.org/ (확인일 2026-11-24; tier 3: official site)
3. leanprover/lean4: Lean 4 programming language and theorem prover. Lean Focused Research Organization. https://github.com/leanprover/lean4 (확인일 2026-11-24; tier 3: official site)
4. Release v4.0.0 - leanprover/lean4. Lean Focused Research Organization. 게시일 2023-09-08. https://github.com/leanprover/lean4/releases/tag/v4.0.0 (확인일 2026-11-24; tier 3: official site)
5. Release v4.36.0 - leanprover/lean4. Lean Focused Research Organization. 게시일 2026-11-16. https://github.com/leanprover/lean4/releases/tag/v4.36.0 (확인일 2026-11-24; tier 3: official site)
6. Lean 4.37.0-rc1 (2026-11-18). Lean Focused Research Organization. 게시일 2026-11-18. https://lean-lang.org/doc/reference/latest/releases/v4.37.0/ (확인일 2026-11-24; tier 3: official site)
7. Release v4.37.0-rc1 - leanprover-community/mathlib4. Lean Community. 게시일 2026-11-19. https://github.com/leanprover-community/mathlib4/releases/tag/v4.37.0-rc1 (확인일 2026-11-24; tier 3: official site)
8. Finding faster quantum algorithms with agents and formal verification. Google DeepMind. 게시일 2026-11-23. https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/ (확인일 2026-11-24; tier 3: official site)
9. google-deepmind/formal-quantum-computation. Google DeepMind. https://github.com/google-deepmind/formal-quantum-computation (확인일 2026-11-24; tier 3: official site)
10. Discovering formally verified quantum programs with AI. arXiv. 게시일 2026-11-16. https://arxiv.org/abs/2611.09822v3 (확인일 2026-11-24; tier 2: academic or news)
11. DeepMind's AI agents found cheaper quantum algorithms, and proved them. The Next Web. 게시일 2026-11-23. https://thenextweb.com/news/google-deepmind-gemini-agents-quantum-algorithms-lean (확인일 2026-11-24; tier 2: academic or news)
12. Google opens the proofs behind its AI-designed quantum programs. QubitWire. 게시일 2026-11-23. https://qubitwire.com/articles/google-deepmind-quantum-program-proofs-public-release (확인일 2026-11-24; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "Lean 정리 증명기 (Lean 4)." 버전 9e947be6, 2026-11-24. https://mimirwiki.com/ko/wiki/lean-theorem-prover
