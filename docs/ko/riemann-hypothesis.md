---
title: "리만 가설 (Riemann Hypothesis)"
subtitle: "리만 제타 함수의 비자명 영점에 관한 1859년 수학 난제로, 2026년 11월 Lean 4 형식 증명 및 독립 검증 완료"
canonical_url: https://mimirwiki.com/ko/wiki/riemann-hypothesis
language: ko
page_class: concept
revision_sha256: bc303f05d6c9eaa262e2a50ce171c5772366428f0a4f9b37162c5ed9a1a5a66d
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 9
alternates:
  md: https://mimirwiki.com/ko/wiki/riemann-hypothesis.md
  txt: https://mimirwiki.com/ko/wiki/riemann-hypothesis.txt
  json: https://mimirwiki.com/ko/wiki/riemann-hypothesis.json
  jsonld: https://mimirwiki.com/ko/wiki/riemann-hypothesis.jsonld
translations:
  en: https://mimirwiki.com/wiki/riemann-hypothesis
  ja: https://mimirwiki.com/ja/wiki/riemann-hypothesis
  zh: https://mimirwiki.com/zh/wiki/riemann-hypothesis
---

# 리만 가설 (Riemann Hypothesis)

> 2026년 11월 20일 앤트로픽(Anthropic) 소속 수학자 레벤트 알푀게(Levent Alpoge)는 클로드(Claude) AI와의 6주간 협업을 통해 리만 가설 및 디리클레 L-함수에 대한 일반화된 리만 가설(GRH)을 완전히 형식화한 1,700만 줄 규모의 Lean 4 증명 라이브러리(Lean v4.33.1 및 Mathlib v4.33.1 기반 175,187개 모듈)를 공개했다. 이 증명은 정칙 유니터리 군 사이의 길이 sqrt(X) 규모의 반복 세타 리프트(iterated theta lifts)를 핵심 기법으로 사용했다. 2026년 11월 21~22일 Lean FRO, Mathlib 이니셔티브 및 MIT의 앤드루 서덜랜드(Andrew Sutherland) 교수는 해당 코드가 오류 없이 컴파일되고 3개의 표준 공리만 사용하며, Mathlib의 공식 리만 가설 명제와 정확히 일치하고 다수의 독립 증명 검사기(nanoda, con-leche, con-ron, lean4lean)를 모두 통과했음을 공인했다(같은 날 공개된 알레산드로 마술로의 비AI 초고에서는 8시간 만에 오류가 발견되었다).

리만 가설(Riemann Hypothesis, 약칭 RH)은 1859년 11월 독일의 수학자 베른하르트 리만(Bernhard Riemann)이 논문 〈주어진 크기보다 작은 소수의 개수에 관하여〉에서 제기한 해석적 정수론의 핵심 가설로, 리만 제타 함수 ζ(s)의 모든 비자명 영점(nontrivial zeros)의 실수부가 1/2(즉, 임계선 Re(s) = 1/2)에 놓여 있다는 명제이다. 1900년 다비트 힐베르트가 제시한 23개 문제 중 여덟 번째 문제이자 2000년 5월 클레이 수학연구소(CMI)가 선정한 7대 밀레니엄 문제(상금 100만 달러) 중 하나로, 소수 정리(Prime Number Theorem)의 오차항과 소수 분포의 정밀한 규칙성을 결정한다.

**다른 이름:** Riemann Hypothesis, RH, 일반화된 리만 가설, GRH, 힐베르트의 여덟 번째 문제

## 핵심 정보

- **최초 제안자:** 베른하르트 리만 (Bernhard Riemann, 1859년) [1]
- **수학적 명제:** 리만 제타 함수 ζ(s) (및 GRH 하의 디리클레 L(χ, s))의 모든 비자명 영점의 실수부는 1/2이다 [1]
- **2026년 11월 20일 형식 증명:** 레벤트 알푀게 (앤트로픽) & 클로드 AI: Lean 4 코드 1,700만 줄 (175,187개 모듈) (기준 2026-11-20) [3]
- **독립 커널 검증 공인:** 2026년 11월 21~22일 Lean FRO, Mathlib 이니셔티브 및 MIT 앤드루 서덜랜드 검증 완료 (기준 2026-11-22) [4]

## 기본 정보

- **학문 분야:** 해석적 정수론 (Analytic Number Theory) / 보형 형식 (Automorphic Forms) [1]
- **최초 제안:** 게오르크 프리드리히 베른하르트 리만 (1826-1866), 1859년 11월 [1]
- **주요 난제 지정:** 힐베르트의 제8문제 (1900년); 클레이 수학연구소 밀레니엄 문제 (상금 100만 달러, 2000년 5월 24일) [2]
- **형식 증명 저자:** 레벤트 알푀게 (Levent Alpoge, 앤트로픽 Claude AI 협업, 2026년 11월 20일 공개) [3]
- **형식 검증 환경:** Lean v4.33.1 / Mathlib v4.33.1 (1,700만 줄; 175,187개 모듈; 61.57GB 증명 익스포트) [5]
- **검증된 핵심 정리 (Main.lean):** riemannHypothesis, riemannZeta_eq_zero_re 및 디리클레 L-함수 GRH 정리 3종 (+ 로빈 및 라가리아스 부등식) [5]
- **교차 검증 커널:** Lean 기본 커널(leanchecker), nanoda(Rust), con-leche, con-ron(Rust), lean4lean [4]

## 수학적 정의 및 소수 분포와의 관계

**리만 제타 함수(Riemann zeta function)** $\zeta(s)$는 실수부가 $\text{Re}(s) = \sigma > 1$인 복소수 $s = \sigma + it$에 대하여 다음과 같은 무한 디리클레 급수 및 모든 소수(prime number) $p$에 대한 오일러 곱(Euler product)으로 정의된다 [1]: $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$ 1859년 11월 베를린 과학 아카데미에 제출한 논문에서 독일의 수학자 **베른하르트 리만(Georg Friedrich Bernhard Riemann, 1826-1866)**은 해석적 연속(analytic continuation)을 통해 $\zeta(s)$를 $s = 1$에서의 단순 극점(simple pole) 하나만을 갖는 전 복소평면 $\mathbb{C}$ 상의 유리형 함수로 확장하고, $\zeta(s)$와 $\zeta(1-s)$를 연결하는 함수방정식을 유도했다 [1].

함수방정식의 감마 함수 인자에 의해 $\zeta(s)$는 음의 짝수 $s = -2, -4, -6, \dots$에서 항상 $0$이 되며, 이를 **자명한 영점(trivial zeros)**이라 부른다 [1][5]. 그 외의 모든 영점인 **비자명 영점(nontrivial zeros)**은 임계 영역(critical strip) $0 < \text{Re}(s) < 1$ 내부에 위치한다 [1][5]. **리만 가설(Riemann Hypothesis, RH)**은 $\zeta(s)$의 모든 비자명 영점이 실수부가 정확히 $1/2$인 수직선, 즉 **임계선(critical line)** $\text{Re}(s) = 1/2$ 위에 존재한다는 명제이다 [1]. 이는 주어진 수 $x$ 이하의 소수의 개수를 세는 소수 계량 함수 $\pi(x)$가 로그 적분 함수 $\text{Li}(x)$로부터 벗어나는 오차 한계를 최적의 제곱근 오차인 $\pi(x) = \text{Li}(x) + O(\sqrt{x} \log x)$로 통제한다는 것과 동치이다 [1][3].

1900년 8월 9일 다비트 힐베르트는 파리 세계수학자대회에서 리만 가설을 23대 문제 중 여덟 번째 문제로 선정했으며, 100년 뒤인 **2000년 5월 24일** 미국 **클레이 수학연구소(Clay Mathematics Institute, CMI)**는 이를 7대 **밀레니엄 문제(Millennium Prize Problems)** 중 하나로 지정하고 100만 달러의 상금을 내걸었다 [1][2]. 2026년 11월 이전까지 컴퓨터 수치 계산을 통해 처음 $10^{13}$개(10조 개)의 비자명 영점이 모두 임계선 위에 있음이 확인되었으나 일반적인 증명은 167년간 미해결로 남아 있었으며, 이를 모든 디리클레 $L$-함수 $L(\chi, s)$로 확장한 명제를 **일반화된 리만 가설(Generalized Riemann Hypothesis, GRH)**이라 한다 [1][5].

## 2026년 11월 20일 레벤트 알푀게와 클로드(Claude)의 형식 증명

소속사 앤트로픽(Anthropic)이 나스닥에 상장한 다음 날인 **2026년 11월 20일**, 수학자 **레벤트 알푀게(Levent Alpoge)**는 자신의 웹사이트에 4쪽 분량의 해설 노트(`alpo.ge/remark.pdf`)와 함께 **리만 가설(RH)** 및 디리클레 $L$-함수에 대한 **일반화된 리만 가설(GRH)**을 추가 가정 없이 완전히 형식 증명한 14개 분할 압축 아카이브(`lean.tar.gz.part01` ~ `part14`)를 공개했다 [3][4][8].

알푀게가 공개한 타임라인에 따르면 이 증명은 **2026년 10월 6일부터 11월 16일까지** 약 6주 동안 앤트로픽의 **클로드(Claude)** AI와의 긴밀한 상호작용을 통해 완성되었다 [3][8]. 알푀게는 아직 단순화되지 않은 방대한 증명을 자연어 논문으로 출력하면 25만 페이지가 넘는 읽을 수 없는 문서('slop')가 된다는 점을 지적하며, 인간이 읽을 수 있는 해설서는 추후 집필하고 우선 기계가 100% 검증할 수 있는 **1,700만 줄(17 million lines)** 규모의 **Lean 4** 코드베이스(**175,187개 모듈**)만 공개하는 결단을 내렸다 [3][4][5].

수학적 핵심 아이디어는 유한체 위 함수체(function fields)에서 리만 가설을 증명할 때 고차 약수 중복도(multiplicity)를 활용하는 **스테파노프(Stepanov) 보조 다항식 방법**을 정수론 및 보형 형식(automorphic forms)의 영역으로 이식한 것이다 [3]: - 정수환 $\mathbb{Z}$ 위에서는 미분을 통한 고차 중복도를 직접 구성하기 어렵기 때문에, 알푀게와 클로드는 부호가 확정된 이차형식 파르세발 항등식($qN = M_k + R$)과 기낭-베유(Guinand-Weil) 명시적 공식을 완전 정칙 유니터리 군(totally definite unitary groups, 및 직교군 $O(2, n)$) 사이의 **반복 세타 리프트(iterated theta lifts)** $U(X_0) \to U(X_1) \to \dots \to U(X_m)$ 사슬과 결합했다 [3]. - 각 세타 리프트가 스테파노프 논증의 중복도 1단계를 모사하며, 알푀게가 '동료 수학자들이 의자에서 떨어질 만한 클로드의 결정적 제안'으로 꼽은 핵심 통찰은 길이 $X$인 폰 망골트 합(von Mangoldt sum, $\sum_{n \le X} \Lambda(n)$)에 대해 세타 리프트 사슬의 길이를 **$m \approx \sqrt{X}$**로 잡는 것이었다 [3]. - 이후 $m$-중 반복 리프트의 노름(norm), 레벨 및 가분성(divisibility) 하한을 **차울라-셀베르그(Chowla-Selberg) 공식**, **지겔 질량 공식(Siegel mass formula)**, **랄리스 시소 항등식(Rallis seesaw identities)**, **보스트 기울기 부등식(Bost slope inequality)**, 그리고 베렌트(Behrend) 대각합 공식과 CM 체 위 $\text{GL}_n$의 정칙 대수적 편극 첨점 보형 표현에 대응하는 갈루아 표현을 결합한 **이와사와 타워(Iwasawa tower)**로 정밀하게 제어하여 GRH를 도출했다 [3][9].

## Lean FRO, Mathlib 이니셔티브 및 MIT의 독립 커널 교차 검증

AI가 생성에 관여한 대규모 Lean 코드가 실제로 정리를 증명했는지 확인하려면 (1) 정리의 형식 정의가 왜곡되지 않았는지, (2) 코드가 오류 없이 컴파일되는지, (3) 증명된 정리가 목표 명제와 정확히 일치하는지, (4) 숨겨진 공리나 커널 버그 악용 없이 독립 증명 검사기를 통과하는지의 4단계 기준 - 임페리얼 칼리지 런던의 **케빈 버자드(Kevin Buzzard)** 교수가 2026년 11월 12일 Xena 블로그에 정립한 프로토콜 [7] - 을 통과해야 한다 [4].

공개 다음 날인 **2026년 11월 21일**, **Lean FRO(Lean Focused Research Organization)**와 **Mathlib 이니셔티브(Mathlib Initiative)**는 공동 성명을 발표하여 알푀게의 리만 가설 증명이 위 4가지 기준을 모두 완벽히 충족하며 증명이 올바름을 공식 인증(certify)했다 [4]. 동시에 MIT 수학과 **앤드루 서덜랜드(Andrew Sutherland)** 교수는 검증 현황 페이지(`math.mit.edu/~drew/grh/`)를 통해 **Lean v4.33.1** 및 **Mathlib v4.33.1** 환경에서 수행된 교차 검증 결과를 투명하게 공개했다 [5]:

| 검증 항목 | 독립 감사 및 커널 실행 결과 (2026년 11월 22일 기준) |
| --- | --- |
| **1. 샌드박스 재빌드 및 재현성** | 네트워크가 차단된 읽기 전용 샌드박스 머신에서 **175,187개 모듈 전체**가 오류 0건으로 컴파일(`lake build Main`)되었으며, 원본과 바이트 단위로 동일한 **61,570,595,788바이트**(61.57GB) 크기의 원시 증명 익스포트 파일(`sha256: 5ea74b91...244e`)이 재현됨 [4][5]. |
| **2. 공리(Axiom) 및 캐시 무결성** | `Main.lean`의 5대 핵심 정리에 대한 `#print axioms` 감사 결과, 사용자 추가 공리 없이 Lean 코어의 3대 표준 공리(`propext`, `Classical.choice`, `Quot.sound`)만 사용되었으며 8,322개의 Mathlib `.olean` 파일이 공식 캐시와 바이트 단위로 일치함 [5]. |
| **3. 정리 명제 일치 검증** | 독립 비교 도구인 `con-leche --compare` 및 러스트(Rust) 포팅 버전인 `con-ron --compare`(1,468,418개 해답 선언과 51,692개 챌린지 선언 대조)를 통해 Mathlib의 공식 `RiemannHypothesis` 정의(`∀ (s : ℂ) (_ : riemannZeta s = 0) (_ : ¬∃ n : ℕ, s = -2 * (n + 1)) (_ : s ≠ 1), s.re = 1 / 2`) 및 **디리클레 L-함수에 대한 GRH 정리 3종**(`LFunction_ne_zero_of_half_lt_re`, `LFunction_eq_zero_re`, `LFunction_eq_zero_re_of_isPrimitive`)이 정확히 증명되었음을 확인 [4][5]. |
| **4. 다중 독립 커널 검증** | 모든 모듈이 `leanchecker`와 `lean4lean`을 통과했으며, 실행 코드가 배제된 61.57GB 정적 익스포트 파일이 독립 러스트 커널인 **`nanoda`**(80스레드 27분 42초)와 집합론 기반의 정형 검증 증명 검사기인 **`con-leche`**(64스레드 3분 15초) 및 **`con-ron`**(64스레드 7분 6초)에서 모두 승인(exit 0)됨 [4][5]. |

나아가 서덜랜드 교수는 Mathlib의 복소 제타 함수 정의에 혹시라도 정의상 허점이 있을 가능성까지 원천 배제하기 위해, 알푀게의 증명을 리만 가설과 동치인 초등 정수론 명제를 별도로 형식화한 `kimihiro64/Robin1984` 라이브러리와 결합했다 [5]. 그 결과 제타 함수가 전혀 등장하지 않는 약수 합 함수 $\sigma(n) = \sum_{d|n} d$에 대한 **로빈 부등식(Robin's inequality, 모든 $n > 5040$에 대해 $\sigma(n) < e^\gamma n \log \log n$)**과 **라가리아스 부등식(Lagarias's inequality, 모든 $n > 0$에 대해 $\sigma(n) \le H_n + e^{H_n} \log H_n$)**이 아무런 미증명 가정 없이 무조건부 정리로 도출 및 검증되었다 [5].

## 같은 날 공개된 인간 단독 증명 초고와의 비교 및 수학계 파장

공교롭게도 알푀게가 증명을 공개한 **2026년 11월 20일**, 스탠퍼드 대학교 수학과 교수이자 미국수학협회(AMA) 회장인 **라비 바킬(Ravi Vakil)**은 이탈리아의 수학자 **알레산드로 마리아 마술로(Alessandro Maria Masullo)**가 AI를 전혀 사용하지 않고 12년간 연구하여 작성한 일반화된 리만 가설(GRH) 증명 초고를 자신의 블로그에 긴급 공개했다 [6][8][9]. 브라이언 콘래드(Brian Conrad) 스탠퍼드 교수가 수개월간 마술로의 원고를 검토하며 수정 작업을 돕고 있었으나 급변하는 상황 속에 수정 중이던 원고를 우선 공개한 것이었다 [6]. 그러나 공개 약 8시간 만에 바킬 교수는 여러 수학자들이 AI 모델의 보조를 받아 마술로의 증명 초고에서 수학적 결함과 간극을 발견해 제보해 왔음을 공지하며, 해당 문제들이 해결되기 전까지 증명으로 인정될 수 없다고 업데이트했다 [6].

반면 알푀게와 클로드의 1,700만 줄 Lean 4 증명은 다중 독립 커널 검증을 모두 통과함에 따라, 이제 수학계의 과제는 '리만 가설이 참인가'에서 '기계가 검증한 방대한 보형 리프트 증명을 인간 수학자들이 직관적으로 이해하고 수십 페이지 내외의 간결한 논증으로 압축·해독하는 것'으로 전환되었다 [3][4][9]. 참고로 2026년 11월 22일 기준 `Main.lean`에서 형식 검증이 완료된 범위는 고전적 리만 제타 함수 $\zeta(s)$와 모든 법(modulus) 및 지표(character)에 대한 **디리클레 $L$-함수**의 일반화된 리만 가설(GRH)이며, 일반 데데킨트 제타 함수나 임의의 고차 보형 $L$-함수는 이번 검증 명제 목록에 포함되지 않았다 [5].

## 자주 묻는 질문

### 리만 가설(Riemann Hypothesis)이 실제로 증명되고 검증되었나요?

네, 그렇습니다. 2026년 11월 20일 앤트로픽(Anthropic)의 수학자 레벤트 알푀게(Levent Alpoge)가 클로드(Claude) AI와 협업하여 완성한 1,700만 줄 규모의 리만 가설 및 디리클레 L-함수 일반화된 리만 가설(GRH)의 Lean 4 형식 증명을 공개했습니다. 이어 11월 21~22일 Lean FRO, Mathlib 이니셔티브, 그리고 MIT의 앤드루 서덜랜드 교수가 독립 샌드박스 빌드와 다수의 외부 증명 검사기(nanoda, con-leche, con-ron, lean4lean)를 통해 이 증명에 오류가 없음을 공식 인증했습니다. [3][4][5]

### 리만 가설이란 무엇을 주장하는 명제인가요?

1859년 베른하르트 리만이 제시한 리만 가설은 리만 제타 함수 ζ(s) = 0의 해(영점) 가운데 음의 짝수(-2, -4, -6, ...)인 자명한 영점을 제외한 모든 '비자명 영점'의 실수부가 정확히 1/2(즉, 복소평면의 수직선 Re(s) = 1/2 위)에 놓여 있다는 가설입니다. 이는 소수들이 자연수 안에서 얼마나 고르게 분포하는지를 결정합니다. [1][5]

### 레벤트 알푀게와 클로드 AI는 어떤 수학적 방법으로 리만 가설을 증명했나요?

함수체 위에서 고차 중복도를 이용하는 스테파노프(Stepanov)의 증명법을 정수론으로 확장하기 위해, 이차형식 파르세발 항등식 및 기낭-베유 명시적 공식을 정칙 유니터리 군 사이의 반복 세타 리프트(iterated theta lifts) 사슬과 결합했습니다. 특히 길이 X인 폰 망골트 합에 대해 세타 리프트 사슬의 길이를 sqrt(X)로 설정하고, 차울라-셀베르그 공식, 지겔 질량 공식, 랄리스 시소 항등식, 보스트 기울기 부등식 및 이와사와 타워를 결합해 가분성과 노름을 제어했습니다. [3][9]

### 1,700만 줄이나 되는 AI 협업 증명에 속임수나 정의 왜곡이 없다는 것을 어떻게 확인했나요?

검증단은 네트워크가 차단된 샌드박스에서 175,187개 모듈을 직접 재컴파일해 61.57GB의 정적 증명 파일을 재현했고, Lean의 3대 표준 공리 외에 어떠한 추가 공리도 쓰이지 않았음을 확인했으며, 증명된 정리가 Mathlib의 공식 리만 가설 정의와 일치함을 비교 도구로 대조했습니다. 또한 제타 함수 정의에 의존하지 않는 초등 정수론 명제인 로빈 부등식(Robin's inequality)과 라가리아스 부등식까지 무조건부 정리로 도출하여 정의 왜곡 가능성을 완전히 배제했습니다. [4][5][7]

### 같은 날 공개된 알레산드로 마술로(Alessandro Masullo)의 인간 단독 증명은 어떻게 되었나요?

2026년 11월 20일 스탠퍼드대 라비 바킬 교수가 이탈리아 수학자 알레산드로 마술로의 비AI GRH 증명 초고를 블로그에 공개했으나, 공개 약 8시간 만에 여러 수학자들이 AI 도구의 보조를 받아 증명 과정의 논리적 결함을 발견해 보고함에 따라 현재로서는 미완성 상태로 남아 있습니다. [6][9]

## 인용 문장

- 1859년 베른하르트 리만이 제기하고 2000년 클레이 수학연구소가 상금 100만 달러의 밀레니엄 문제로 지정한 리만 가설은 리만 제타 함수의 모든 비자명 영점의 실수부가 1/2이라는 명제이다. [1][2]
- 2026년 11월 20일 앤트로픽의 수학자 레벤트 알푀게는 클로드 AI와 협업하여 완성한 1,700만 줄(175,187개 모듈) 규모의 리만 가설 및 디리클레 L-함수 일반화된 리만 가설(GRH) Lean 4 형식 증명을 공개했다. [3][4][5]
- 2026년 11월 21일 Lean FRO와 Mathlib 이니셔티브는 알푀게의 증명이 오류 없이 컴파일되고 Mathlib의 공식 리만 가설 명제를 정확히 증명하며 독립 증명 검사기(con-leche, con-ron 등)를 통과했음을 공식 인증했다. [4]
- MIT의 앤드루 서덜랜드 교수는 175,187개 모듈이 3대 표준 공리만 사용하여 61,570,595,788바이트의 증명 익스포트를 재현하고 nanoda, con-leche, con-ron, lean4lean을 모두 통과하며 로빈 부등식과 라가리아스 부등식을 무조건부로 함의함을 검증했다. [5]
- 2026년 11월 20일 라비 바킬 교수가 별도로 공개한 알레산드로 마술로의 비AI GRH 증명 초고에서는 공개 8시간 만에 수학적 오류들이 보고되었다. [6][9]

## 연표

- 1859-11: 베른하르트 리만이 베를린 과학 아카데미 논문에서 리만 제타 함수의 영점에 관한 리만 가설을 최초 제기. [1]
- 1900-08-09: 다비트 힐베르트가 파리 세계수학자대회에서 발표한 23가지 수학 문제 중 제8문제로 리만 가설을 포함. [2]
- 2000-05-24: 클레이 수학연구소(CMI)가 파리 콜레주 드 프랑스에서 리만 가설을 상금 100만 달러의 7대 밀레니엄 문제 중 하나로 발표. [1][2]
- 2026-10-06: 레벤트 알푀게가 앤트로픽 클로드 AI와 함께 스테파노프 행렬식 및 보스트 기울기 부등식을 출발점으로 6주간의 증명 및 Lean 형식화 착수. [3]
- 2026-11-16: 알푀게와 클로드가 sqrt(X) 길이의 반복 세타 리프트를 이용해 디리클레 L-함수에 대한 일반화된 리만 가설(GRH) 형식 증명 완성. [3]
- 2026-11-20: 알푀게가 remark.pdf와 1,700만 줄의 Lean 4 증명 아카이브를 공개; 같은 날 공개된 알레산드로 마술로의 인간 단독 초고에서는 8시간 만에 결함이 발견됨. [3][6][9]
- 2026-11-21: Lean FRO, Mathlib 이니셔티브 및 MIT 앤드루 서덜랜드 교수가 다중 독립 증명 커널을 통해 알푀게의 리만 가설 증명 무결성을 공식 인증. [4][5][8]

## 출처

1. Riemann Hypothesis - Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium/riemann-hypothesis/ (확인일 2026-11-23; tier 2: academic or news)
2. The Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium-problems/ (확인일 2026-11-23; tier 2: academic or news)
3. Remark on a Proof and Lean Formalization of the Riemann Hypothesis and Generalized Riemann Hypothesis. Levent Alpoge (alpo.ge). 게시일 2026-11-20. https://alpo.ge/remark.pdf (확인일 2026-11-23; tier 3: official site)
4. Lean Verification of the Riemann Hypothesis: Joint Statement by the Lean FRO and the Mathlib Initiative. Lean Focused Research Organization & Mathlib Initiative. 게시일 2026-11-21. https://leanprover-community.github.io/blog/posts/riemann-hypothesis/ (확인일 2026-11-23; tier 3: official site)
5. RH Lean Proof: Verification Files and Independent Kernel Audit. Andrew Sutherland (Massachusetts Institute of Technology). 게시일 2026-11-22. https://math.mit.edu/~drew/grh/ (확인일 2026-11-23; tier 2: academic or news)
6. Hurried Announcement: Alessandro Masullo GRH (with Nov 20-22 Updates). Ravi Vakil (Stanford University / Math 216 Blog). 게시일 2026-11-20. https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/ (확인일 2026-11-23; tier 2: academic or news)
7. '...and the proof is checked in Lean' (Four Criteria for Verifying AI-Generated Lean Proofs). Kevin Buzzard (Xena Project). 게시일 2026-11-12. https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/ (확인일 2026-11-23; tier 2: academic or news)
8. Two groups verify mathematician's claim that Claude helped prove mathematics problem. The Guardian. 게시일 2026-11-21. https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai (확인일 2026-11-23; tier 2: academic or news)
9. AI claimed a solution to the 167-year-old Riemann hypothesis - and a human did, too. TechCrunch. 게시일 2026-11-20. https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/ (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "리만 가설 (Riemann Hypothesis)." 버전 bc303f05, 2026-11-24. https://mimirwiki.com/ko/wiki/riemann-hypothesis
