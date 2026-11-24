---
title: "Riemann Hypothesis"
subtitle: "1859 conjecture on the nontrivial zeros of the Riemann zeta function, formally proved and verified in Lean 4 in November 2026"
canonical_url: https://mimirwiki.com/wiki/riemann-hypothesis
language: en
page_class: concept
revision_sha256: 03fd6d9ec670be9adb7f24b91a5d92a696a57bccdb10fc5b4ed26e9219310d4c
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 9
alternates:
  md: https://mimirwiki.com/wiki/riemann-hypothesis.md
  txt: https://mimirwiki.com/wiki/riemann-hypothesis.txt
  json: https://mimirwiki.com/wiki/riemann-hypothesis.json
  jsonld: https://mimirwiki.com/wiki/riemann-hypothesis.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/riemann-hypothesis
  ja: https://mimirwiki.com/ja/wiki/riemann-hypothesis
  zh: https://mimirwiki.com/zh/wiki/riemann-hypothesis
---

# Riemann Hypothesis

> On November 20, 2026, Anthropic mathematician Levent Alpoge released a complete formal proof of the Riemann Hypothesis and the Generalized Riemann Hypothesis (GRH) for Dirichlet L-functions as a 17-million-line Lean 4 library (175,187 modules on Lean v4.33.1 and Mathlib v4.33.1), developed over six weeks with Claude AI using iterated theta lifts across definite unitary groups of length proportional to sqrt(X). On November 21-22, 2026, the Lean FRO, the Mathlib Initiative, and MIT mathematician Andrew Sutherland certified that the library compiles cleanly, uses only the three standard Lean axioms, matches Mathlib's exact RiemannHypothesis statement, and passes independent proof kernels (nanoda, con-leche, con-ron, and lean4lean), while a separate non-AI preprint by Alessandro Masullo had gaps identified within eight hours.

The Riemann Hypothesis (RH), formulated by German mathematician Bernhard Riemann in his November 1859 paper 'On the Number of Primes Less Than a Given Magnitude', is the foundational conjecture in analytic number theory asserting that every nontrivial zero of the Riemann zeta function ζ(s) lies on the critical line with real part Re(s) = 1/2. Designated in 1900 as part of Hilbert's Eighth Problem and in May 2000 as one of the seven Clay Mathematics Institute Millennium Prize Problems ($1 million prize), it governs the error term in the Prime Number Theorem and the distribution of prime numbers.

**Also known as:** RH, Generalized Riemann Hypothesis, GRH, Hilbert's Eighth Problem, Riemann Zeta Conjecture

## Key facts

- **Formulated By:** Bernhard Riemann (1859) [1]
- **Mathematical Statement:** Every nontrivial zero of ζ(s) (and Dirichlet L(χ, s) under GRH) has real part Re(s) = 1/2 [1]
- **Nov 20, 2026 Formal Proof:** Levent Alpoge (Anthropic) with Claude AI: 17M lines of Lean 4 code across 175,187 modules (as of 2026-11-20) [3]
- **Independent Kernel Verification:** Certified Nov 21-22, 2026 by Lean FRO, Mathlib Initiative, and Andrew Sutherland (MIT) (as of 2026-11-22) [4]

## Basic facts

- **Field:** Analytic Number Theory / Automorphic Forms [1]
- **Conjectured By:** Georg Friedrich Bernhard Riemann (1826-1866) in 1859 [1]
- **Prize Designations:** Hilbert's 8th Problem (1900); Clay Millennium Prize Problem ($1,000,000, announced May 24, 2000) [2]
- **Formal Resolution Author:** Levent Alpoge (in collaboration with Anthropic's Claude AI, announced Nov 20, 2026) [3]
- **Formal Verification Environment:** Lean v4.33.1 / Mathlib v4.33.1 (17,000,000+ lines; 175,187 modules; 61.57 GB raw proof export) [5]
- **Verified Theorems in Main.lean:** riemannHypothesis, riemannZeta_eq_zero_re, and 3 Dirichlet L-function GRH theorems (+ Robin & Lagarias inequalities) [5]
- **Independent Proof Checkers:** Lean kernel (leanchecker), nanoda (Rust), con-leche, con-ron (Rust), lean4lean [4]

## Mathematical Formulation and the Distribution of Primes

The **Riemann zeta function** $\zeta(s)$ is defined for complex numbers $s = \sigma + it$ with real part $\text{Re}(s) = \sigma > 1$ by the convergent Dirichlet series and Euler product over all prime numbers $p$ [1]: $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$ In his 1859 paper presented to the Berlin Academy of Sciences, **Georg Friedrich Bernhard Riemann** (1826-1866) extended $\zeta(s)$ by analytic continuation to a meromorphic function on the entire complex plane $\mathbb{C}$ with a single simple pole at $s = 1$, satisfying a symmetric functional equation relating $\zeta(s)$ and $\zeta(1-s)$ [1].

Because of the gamma factors in the functional equation, $\zeta(s)$ vanishes at the negative even integers $s = -2, -4, -6, \dots$, known as the **trivial zeros** [1][5]. All other zeros - the **nontrivial zeros** - lie inside the critical strip $0 < \text{Re}(s) < 1$ [1][5]. The **Riemann Hypothesis (RH)** asserts that every nontrivial zero of $\zeta(s)$ lies on the vertical **critical line** $\text{Re}(s) = 1/2$ [1]. Equivalently, in terms of the prime-counting function $\pi(x)$ and the logarithmic integral $\text{Li}(x)$, RH provides the optimal square-root error bound $\pi(x) = \text{Li}(x) + O(\sqrt{x} \log x)$ [1][3].

David Hilbert included the Riemann Hypothesis as the eighth of his 23 problems at the Paris International Congress of Mathematicians on August 9, 1900, and on **May 24, 2000**, the **Clay Mathematics Institute (CMI)** named it one of the seven **Millennium Prize Problems**, allocating a $1 million prize for a verified proof [1][2]. Prior to November 2026, numerical computations had verified that the first $10^{13}$ (10 trillion) nontrivial zeros lie on the critical line, while the **Generalized Riemann Hypothesis (GRH)** extended the conjecture to all Dirichlet $L$-functions $L(\chi, s)$ [1][5].

## November 20, 2026 Proof by Levent Alpoge and Claude

On **November 20, 2026** - one day after his employer Anthropic completed its initial public offering on the Nasdaq - mathematician **Levent Alpoge** published a 4-page explanatory note (`alpo.ge/remark.pdf`) alongside a 14-part compressed archive (`lean.tar.gz.part01` through `part14`) containing a complete, assumption-free formalization in the **Lean 4** theorem prover of both the **Riemann Hypothesis** and the **Generalized Riemann Hypothesis (GRH)** for Dirichlet $L$-functions [3][4][8].

According to Alpoge's timeline, the proof was developed over a six-week sprint between **October 6 and November 16, 2026** in close collaboration with Anthropic's **Claude** AI [3][8]. Recognizing that translating the unsimplified argument into a prose paper would produce over 250,000 pages of unreadable text, Alpoge elected to release the complete machine-checkable Lean codebase comprising **17 million lines of code** across **175,187 Lean modules** [3][4][5].

Mathematically, Alpoge and Claude constructed a native number-field analogue of **Stepanov's auxiliary polynomial method** (which uses high-order divisor multiplicity to prove the Riemann Hypothesis over function fields) [3]: - Because higher-order derivative multiplicity is difficult to construct directly over the integers $\mathbb{Z}$, the proof combines a sign-definite quadric / Parseval identity ($qN = M_k + R$) and the Guinand-Weil explicit formula with **iterated theta lifts** $U(X_0) \to U(X_1) \to \dots \to U(X_m)$ between totally definite unitary groups (and orthogonal groups $O(2, n)$) [3]. - Each theta lift mimics one order of Stepanov multiplicity. In what Alpoge highlighted as the decisive breakthrough suggested by Claude, for a von Mangoldt sum $\sum_{n \le X} \Lambda(n)$ of length $X$, the proof chains a tower of theta lifts of length **$m \approx \sqrt{X}$**, controlling norms, levels, and divisibility via the **Chowla-Selberg formula**, **Siegel mass formula**, **Rallis inner product / seesaw identities**, **Bost's slope inequality**, and an **Iwasawa tower** construction utilizing Behrend's trace formula and Galois representations attached to regular algebraic polarized cuspidal automorphic representations of $\text{GL}_n$ over CM fields [3][9].

## Independent Certification by Lean FRO, Mathlib, and MIT

Because AI-assisted mathematical codebases require rigorous auditing to ensure the formalized theorem statement has not been altered or trivialized and that no custom axioms or compiler exploits were introduced - a four-part protocol outlined by Imperial College London mathematician **Kevin Buzzard** on the Xena Project blog on November 12, 2026 [7] - the formal verification community immediately audited Alpoge's repository [4][5].

On **November 21, 2026**, the **Lean Focused Research Organization (Lean FRO)** and the **Mathlib Initiative** issued a joint statement certifying that Alpoge's proof of the Riemann Hypothesis is completely valid and satisfies all four verification criteria [4]. Concurrently, MIT mathematician **Andrew Sutherland** published a comprehensive verification dashboard (`math.mit.edu/~drew/grh/`) documenting the reproducible checks completed across **Lean v4.33.1** and **Mathlib v4.33.1** [5]:

| Verification Criterion | Observed Audit Result (as of Nov 22, 2026) |
| --- | --- |
| **1. Compilation & Reproducibility** | All **175,187 modules** compiled with zero errors in an isolated, network-disabled, read-only sandbox (`lake build Main`), reproducing the exact **61,570,595,788-byte** (61.57 GB) raw proof export (`sha256: 5ea74b91...244e`) [4][5]. |
| **2. Axiom & Hygiene Audit** | `#print axioms` confirmed that all five headline theorems depend **only** on Lean's three standard foundational axioms (`propext`, `Classical.choice`, and `Quot.sound`), with zero user-defined axioms and byte-for-byte unmodified Mathlib `.olean` caches (8,322 files) [5]. |
| **3. Exact Statement Matching** | Independent comparator tools (`con-leche --compare` and its Rust port `con-ron --compare`, verifying 1,468,418 solution declarations against 51,692 challenge declarations) confirmed that `Main.lean` proves Mathlib's exact `RiemannHypothesis` definition (`∀ (s : ℂ) (_ : riemannZeta s = 0) (_ : ¬∃ n : ℕ, s = -2 * (n + 1)) (_ : s ≠ 1), s.re = 1 / 2`) plus **GRH for all Dirichlet L-functions** (`LFunction_ne_zero_of_half_lt_re`, `LFunction_eq_zero_re`, `LFunction_eq_zero_re_of_isPrimitive`) [4][5]. |
| **4. Multi-Kernel Proof Checking** | Every module passed `leanchecker` and `lean4lean` (verified in Lean), and the full 61.57 GB inert export was independently accepted by the Rust kernel **`nanoda`** (in 27m 42s on 80 threads) and the formally verified set-theoretic checkers **`con-leche`** (3m 15s on 64 threads) and **`con-ron`** (7m 06s on 64 threads) [4][5]. |

As an additional check completely independent of Mathlib's analytic definition of $\zeta(s)$, Sutherland combined Alpoge's proof with an independent formalization of **Robin's inequality** ($\sigma(n) < e^{\gamma} n \log \log n$ for all $n > 5040$) and **Lagarias's inequality** ($\sigma(n) \le H_n + e^{H_n} \log H_n$ for all $n > 0$), deriving unconditional elementary proofs of both divisor-sum inequalities [5].

## Coincidental Human Preprint and Impact on Mathematics

On the same day as Alpoge's release (**November 20, 2026**), Stanford University mathematician **Ravi Vakil** posted a separate, purely human-authored draft manuscript proposing a proof of the Generalized Riemann Hypothesis by Italian mathematician **Alessandro Maria Masullo**, who had worked on the problem for 12 years without AI and had been reviewing the draft with Stanford professor Brian Conrad [6][8][9]. Because Alpoge's announcement made waiting another year for revisions impractical, Vakil shared Masullo's draft mid-revision; however, within eight hours, Vakil updated his post to report that several mathematicians (assisted by AI verification tools) had identified unaddressed gaps in Masullo's manuscript [6].

By contrast, because Alpoge's 17-million-line Lean proof has passed multi-kernel formal verification, mathematical focus has shifted from debating whether the Riemann Hypothesis and Dirichlet GRH are true to distilling human-comprehensible conceptual simplifications from the machine-verified automorphic-lifting proof [3][4][9]. Note that as of November 22, 2026, the verified formal scope covers the classical Riemann zeta function $\zeta(s)$ and **Dirichlet $L$-functions** for all moduli and characters, whereas Dedekind zeta functions, general Hecke $L$-functions, and arbitrary higher-rank automorphic $L$-functions were not among the formal theorem statements checked in `Main.lean` [5].

## Frequently asked questions

### Has the Riemann Hypothesis been proved and verified?

Yes. On November 20, 2026, mathematician Levent Alpoge (working with Anthropic's Claude AI) released a 17-million-line formal proof of the Riemann Hypothesis and the Generalized Riemann Hypothesis for Dirichlet L-functions in the Lean 4 theorem prover. On November 21-22, 2026, the Lean Focused Research Organization (FRO), the Mathlib Initiative, and MIT mathematician Andrew Sutherland certified that the proof compiles cleanly, uses only standard axioms, matches Mathlib's official theorem statement, and passes multiple independent proof kernels. [3][4][5]

### What does the Riemann Hypothesis state?

Formulated by Bernhard Riemann in 1859, the Riemann Hypothesis states that every nontrivial zero of the Riemann zeta function ζ(s) - meaning every solution to ζ(s) = 0 other than the negative even integers -2, -4, -6, and so on - is a complex number with real part exactly equal to 1/2. [1][5]

### What mathematical method did Levent Alpoge and Claude use to prove the Riemann Hypothesis?

The proof adapts Stepanov's function-field multiplicity argument to the integers by combining a sign-definite quadric Parseval identity and the Guinand-Weil explicit formula with an iterated chain of theta lifts across totally definite unitary groups of length proportional to sqrt(X), controlled via the Chowla-Selberg formula, Siegel mass formula, Rallis seesaw identities, Bost's slope inequality, and an Iwasawa tower construction. [3][9]

### How did mathematicians verify that a 17-million-line AI-assisted proof has no hidden errors or tricks?

Following the four-step Lean verification protocol, auditors rebuilt all 175,187 modules in an offline sandbox to produce an inert 61.57 GB proof export, verified that only the three standard Lean axioms (propext, Classical.choice, Quot.sound) were used, matched the proved theorems against Mathlib's unmodified RiemannHypothesis definition, and checked the raw export using independent proof checkers written in different languages (including nanoda, con-leche, con-ron, and lean4lean), as well as deriving Robin's and Lagarias's elementary divisor-sum inequalities. [4][5][7]

### What happened to Alessandro Masullo's separate November 2026 human proof attempt?

On November 20, 2026, Stanford professor Ravi Vakil posted a mid-revision manuscript of a non-AI GRH proof attempt by Alessandro Maria Masullo. Within eight hours of publication, mathematicians using AI analysis tools identified gaps in Masullo's draft that remain unresolved, whereas Alpoge's Lean 4 formalization passed full kernel certification. [4][6][9]

## Quotable sentences

- Formulated in 1859 by Bernhard Riemann and designated in 2000 as a $1 million Clay Mathematics Institute Millennium Prize Problem, the Riemann Hypothesis states that all nontrivial zeros of the Riemann zeta function have real part 1/2. [1][2]
- On November 20, 2026, Levent Alpoge released a 17-million-line Lean 4 formalization (175,187 modules) proving the Riemann Hypothesis and the Generalized Riemann Hypothesis for Dirichlet L-functions, developed with Anthropic's Claude AI. [3][4][5]
- On November 21, 2026, the Lean FRO and the Mathlib Initiative certified that Alpoge's proof of the Riemann Hypothesis is valid, compiles cleanly against Mathlib, proves the exact Mathlib statement, and passes independent proof checkers including con-leche and con-ron. [4]
- MIT mathematician Andrew Sutherland verified that Alpoge's 175,187 Lean v4.33.1 modules reproduce a 61,570,595,788-byte export using only the three standard axioms (propext, Classical.choice, Quot.sound), accepted by nanoda, con-leche, con-ron, leanchecker, and lean4lean, and unconditionally imply Robin's and Lagarias's divisor-sum inequalities. [5]
- A separate non-AI manuscript on GRH by Alessandro Maria Masullo posted by Ravi Vakil on November 20, 2026 had mathematical problems identified by reviewers within eight hours. [6][9]

## Timeline

- 1859-11: Bernhard Riemann publishes 'On the Number of Primes Less Than a Given Magnitude', formulating the Riemann Hypothesis. [1]
- 1900-08-09: David Hilbert includes the Riemann Hypothesis as Problem 8 in his address to the International Congress of Mathematicians in Paris. [2]
- 2000-05-24: The Clay Mathematics Institute designates the Riemann Hypothesis as one of the seven $1 million Millennium Prize Problems in Paris. [1][2]
- 2026-10-06: Levent Alpoge begins a six-week formalization and proof discovery sprint with Anthropic's Claude AI starting from Stepanov determinants and Bost's slope inequality. [3]
- 2026-11-16: Alpoge and Claude complete the Lean 4 formalization of the Generalized Riemann Hypothesis for Dirichlet L-functions using sqrt(X)-length iterated theta lifts. [3]
- 2026-11-20: Alpoge publicly releases remark.pdf and the 17-million-line Lean 4 proof archive; Ravi Vakil separately posts Alessandro Masullo's human draft, in which gaps are found within eight hours. [3][6][9]
- 2026-11-21: The Lean FRO, the Mathlib Initiative, and Andrew Sutherland (MIT) independently certify the correctness of Alpoge's Lean 4 proof across multiple independent proof kernels. [4][5][8]

## Sources

1. Riemann Hypothesis - Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium/riemann-hypothesis/ (checked 2026-11-23; tier 2: academic or news)
2. The Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium-problems/ (checked 2026-11-23; tier 2: academic or news)
3. Remark on a Proof and Lean Formalization of the Riemann Hypothesis and Generalized Riemann Hypothesis. Levent Alpoge (alpo.ge). published 2026-11-20. https://alpo.ge/remark.pdf (checked 2026-11-23; tier 3: official site)
4. Lean Verification of the Riemann Hypothesis: Joint Statement by the Lean FRO and the Mathlib Initiative. Lean Focused Research Organization & Mathlib Initiative. published 2026-11-21. https://leanprover-community.github.io/blog/posts/riemann-hypothesis/ (checked 2026-11-23; tier 3: official site)
5. RH Lean Proof: Verification Files and Independent Kernel Audit. Andrew Sutherland (Massachusetts Institute of Technology). published 2026-11-22. https://math.mit.edu/~drew/grh/ (checked 2026-11-23; tier 2: academic or news)
6. Hurried Announcement: Alessandro Masullo GRH (with Nov 20-22 Updates). Ravi Vakil (Stanford University / Math 216 Blog). published 2026-11-20. https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/ (checked 2026-11-23; tier 2: academic or news)
7. '...and the proof is checked in Lean' (Four Criteria for Verifying AI-Generated Lean Proofs). Kevin Buzzard (Xena Project). published 2026-11-12. https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/ (checked 2026-11-23; tier 2: academic or news)
8. Two groups verify mathematician's claim that Claude helped prove mathematics problem. The Guardian. published 2026-11-21. https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai (checked 2026-11-23; tier 2: academic or news)
9. AI claimed a solution to the 167-year-old Riemann hypothesis - and a human did, too. TechCrunch. published 2026-11-20. https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/ (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "Riemann Hypothesis." Version 03fd6d9e, 2026-11-24. https://mimirwiki.com/wiki/riemann-hypothesis
