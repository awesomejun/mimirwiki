---
title: "Lean (Theorem Prover)"
subtitle: "Open-source functional programming language and interactive proof assistant (Lean 4)"
canonical_url: https://mimirwiki.com/wiki/lean-theorem-prover
language: en
page_class: entity
revision_sha256: 67e7441e6a7932ee0dbba35dc0a3d34393f73ef2df3f56ba1e528b462bc710b3
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/lean-theorem-prover.md
  txt: https://mimirwiki.com/wiki/lean-theorem-prover.txt
  json: https://mimirwiki.com/wiki/lean-theorem-prover.json
  jsonld: https://mimirwiki.com/wiki/lean-theorem-prover.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/lean-theorem-prover
  ja: https://mimirwiki.com/ja/wiki/lean-theorem-prover
  zh: https://mimirwiki.com/zh/wiki/lean-theorem-prover
  es: https://mimirwiki.com/es/wiki/lean-theorem-prover
---

# Lean (Theorem Prover)

> Lean (Lean 4) is an open-source programming language and proof assistant published under the Apache-2.0 license and supported by the Lean Focused Research Organization. As of 2026-11-24, its latest stable release is v4.36.0 (2026-11-16) and v4.37.0-rc1 (2026-11-18) is a release candidate; on 2026-11-23, Google DeepMind open-sourced a Lean 4 quantum-program verification library, specifications, and proofs.

Lean is an open-source programming language and interactive proof assistant designed to write formally verified mathematical proofs and software. Its repository is published under the Apache-2.0 license and its development is supported by the Lean Focused Research Organization. Lean 4 had its first official release (v4.0.0) on 2023-09-08. As of 2026-11-24, the latest stable release is Lean 4.36.0 (released 2026-11-16), while Lean 4.37.0-rc1 was published on 2026-11-18 as a pre-release candidate, followed by a matching Mathlib pre-release on 2026-11-19 and Google DeepMind's 2026-11-23 public release of Lean 4 quantum-program verification materials.

**Also known as:** Lean 4, Lean theorem prover, Lean programming language

## Key facts

- **Latest stable release:** v4.36.0 (2026-11-16) (as of 2026-11-24) [5]
- **Current release candidate:** v4.37.0-rc1 (2026-11-18, pre-release) (as of 2026-11-24) [6]
- **Lean 4 first official release:** v4.0.0 (2023-09-08) [4]
- **License:** Apache-2.0 [3]

## Basic facts

- **Type:** Programming language and interactive proof assistant [1]
- **Supporting organization:** Lean Focused Research Organization (Lean FRO) [2]
- **License:** Apache-2.0 [3]
- **Lean 4 first official release:** v4.0.0 (2023-09-08) [4]
- **Latest stable release:** v4.36.0 (2026-11-16) (as of 2026-11-24) [5]
- **Latest pre-release:** v4.37.0-rc1 (2026-11-18) (as of 2026-11-24) [6]
- **Major mathematical library:** Mathlib (mathlib4) [4]
- **Source repository:** github.com/leanprover/lean4 [3]
- **Official website:** lean-lang.org [1]

## Lean overview and organization

Lean is an open-source programming language and proof assistant that enables users to write formal mathematical proofs and verified software.[1][3] The Lean 4 repository is published under the Apache-2.0 license, and the Lean Focused Research Organization (Lean FRO) states that it supports Lean's growth.[2][3]

Lean FRO states that its mission is to advance Lean's critical systems and capabilities, and lists focus areas including scalability, usability, proof automation, documentation, a diverse community, and support for AI research and verified code synthesis.[2] Built-in automation examples highlighted on the official Lean site include the `grind` tactic for induction, algebraic reasoning, and SMT-like reasoning, as well as `bv_decide` for deciding bitvector equations.[1] The Lean 4.0.0 release notes describe Mathlib as Lean's major mathematical library (`mathlib4`), and projects are managed with the `lake` build tool and `elan` toolchain manager.[4][9]

## Lean 4 release history and November 2026 versions

Lean 4 reached its first official release with `v4.0.0` on 2023-09-08, when the developers announced plans for approximately monthly minor releases.[4]

| Version | Type | Release date | Notes |
| --- | --- | --- | --- |
| v4.0.0 | Stable | 2023-09-08 | First official release of Lean 4 |
| v4.36.0 | Stable (Latest as of 2026-11-24) | 2026-11-16 | Latest stable release tag on GitHub |
| v4.37.0-rc1 | Release candidate (pre-release) | 2026-11-18 | 370 landed changes; subject to change before final release |

As of 2026-11-24, `v4.36.0` (released 2026-11-16) is the latest stable release of Lean 4.[5] On 2026-11-18, the project published `v4.37.0-rc1`, explicitly labeled as a release candidate rather than a final release.[6] Its release notes record 370 landed changes, including 71 feature additions, 159 fixes, 108 performance improvements, 7 refactoring changes, 4 test suite improvements, 1 documentation improvement, and 20 other changes, one of which adds the option `shiftLeft.threshold` (default 65536).[6] On 2026-11-19, `leanprover-community/mathlib4` tagged pre-release `v4.37.0-rc1` to bump its toolchain to the release candidate.[7]

## Lean in formal verification and the November 2026 DeepMind release

Lean FRO names formal mathematics and software and hardware verification among the fields where Lean is applied.[1][2] On 2026-11-23, Google DeepMind announced the public release of verification materials on GitHub for quantum programs synthesized with [Google Gemini](https://mimirwiki.com/wiki/google-gemini) (Gemini 4) agent teams and checked in Lean 4.[8][9]

The open-sourced repository (`google-deepmind/formal-quantum-computation`, Apache-2.0 license) is grounded in quantum Hoare logic with classical variables and depends on `Mathlib4` and `QuantumInfo` (part of `Physlib`).[9] It separates three parts: the core `QuantumComputation` library (circuits, gates, registers, quantum Hoare logic, and resource counting), `QuantumComputationSpecs` (formal problem specifications and benchmark challenges), and a `discoveries` branch holding the reported programs and Lean proofs.[9][12]

The underlying research preprint (`arXiv:2611.09822v3`) was first submitted on 2026-11-06 and revised on 2026-11-16; the 2026-11-23 news event was the public release of the Lean library, specifications, and proofs, covered that day by The Next Web and QubitWire.[8][10][11][12] Both DeepMind and QubitWire note that the reported resource reductions (such as an 11.8x reduction in a combined qubit-and-operation cost metric and 4,338 versus 5,650 error-corrected qubits for an inertial confinement fusion calculation) are mathematically verified against formal specifications and cost models rather than measured on physical quantum hardware, and the repository lists explicit costing of classical computation and control flow as planned future work.[8][9][12]

## Lean verification scope and limits

As noted in independent coverage of the DeepMind repository release, a machine-checked Lean proof confirms that a program satisfies its formal specification under the modeled cost assumptions, but does not by itself establish that those specifications or cost models match every physical hardware bottleneck or that external parties have independently reproduced the results.[12]

## Frequently asked questions

### What is the latest stable version of Lean 4 as of 2026-11-24?

As of 2026-11-24, the latest stable release of Lean 4 is v4.36.0, released on 2026-11-16. Lean 4.37.0-rc1, published on 2026-11-18, is a release candidate (pre-release) rather than a final release. [5][6]

### What is Mathlib in the Lean ecosystem?

Mathlib (mathlib4) is Lean's major mathematical library. On 2026-11-19, the Mathlib repository published a v4.37.0-rc1 pre-release updating its toolchain to match Lean 4.37.0-rc1. [4][7]

### What did Google DeepMind release for Lean on 2026-11-23?

On 2026-11-23, Google DeepMind announced the public release of its Apache-2.0 GitHub repository formal-quantum-computation, containing a Lean 4 quantum program library, formal problem specifications, and Lean proofs from its November 2026 preprint. [8][9][10]

### Did the DeepMind Lean release demonstrate execution on a physical quantum computer?

No. The 2026-11-23 announcement was the public release of Lean verification materials, and the reported resource improvements come from formal specifications and mathematical cost models rather than timing on physical quantum hardware. [8][12]

## Quotable sentences

- Lean is an open-source programming language and proof assistant licensed under Apache-2.0 and supported by the Lean Focused Research Organization. [1][2][3]
- Lean 4.0.0, the first official release of Lean 4, was published on 2023-09-08. [4]
- As of 2026-11-24, Lean v4.36.0 (released 2026-11-16) is the latest stable release on GitHub. [5]
- Lean 4.37.0-rc1 was published on 2026-11-18 as a release candidate with 370 landed changes, and Mathlib published a matching v4.37.0-rc1 pre-release on 2026-11-19. [6][7]
- On 2026-11-23, Google DeepMind open-sourced its Lean 4 quantum-program verification library, problem specifications, and verified solutions in google-deepmind/formal-quantum-computation. [8][9]
- The accompanying preprint arXiv:2611.09822v3 was submitted on 2026-11-06 and revised on 2026-11-16, and its reported circuit cost figures are derived from formal models rather than physical quantum hardware runs. [10][12]

## Timeline

- 2023-09-08: Lean 4.0.0 is released as the first official release of Lean 4. [4]
- 2026-11-06: Authors submit preprint arXiv:2611.09822 on discovering formally verified quantum programs in Lean with Gemini 4 agents (revised to v3 on 2026-11-16). [10]
- 2026-11-16: Lean v4.36.0 is published as a stable release on GitHub. [5]
- 2026-11-18: Lean 4.37.0-rc1 is published as a release candidate with 370 landed changes. [6]
- 2026-11-19: Mathlib (mathlib4) publishes pre-release v4.37.0-rc1 updating its toolchain to Lean 4.37.0-rc1. [7]
- 2026-11-23: Google DeepMind announces the public release of its Lean 4 quantum-program verification library, problem specifications, and verified solutions on GitHub. [8][9]

## Sources

1. Lean Programming Language. Lean Focused Research Organization. https://lean-lang.org/ (checked 2026-11-24; tier 3: official site)
2. Lean Focused Research Organization. Lean Focused Research Organization. https://lean-fro.org/ (checked 2026-11-24; tier 3: official site)
3. leanprover/lean4: Lean 4 programming language and theorem prover. Lean Focused Research Organization. https://github.com/leanprover/lean4 (checked 2026-11-24; tier 3: official site)
4. Release v4.0.0 - leanprover/lean4. Lean Focused Research Organization. published 2023-09-08. https://github.com/leanprover/lean4/releases/tag/v4.0.0 (checked 2026-11-24; tier 3: official site)
5. Release v4.36.0 - leanprover/lean4. Lean Focused Research Organization. published 2026-11-16. https://github.com/leanprover/lean4/releases/tag/v4.36.0 (checked 2026-11-24; tier 3: official site)
6. Lean 4.37.0-rc1 (2026-11-18). Lean Focused Research Organization. published 2026-11-18. https://lean-lang.org/doc/reference/latest/releases/v4.37.0/ (checked 2026-11-24; tier 3: official site)
7. Release v4.37.0-rc1 - leanprover-community/mathlib4. Lean Community. published 2026-11-19. https://github.com/leanprover-community/mathlib4/releases/tag/v4.37.0-rc1 (checked 2026-11-24; tier 3: official site)
8. Finding faster quantum algorithms with agents and formal verification. Google DeepMind. published 2026-11-23. https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/ (checked 2026-11-24; tier 3: official site)
9. google-deepmind/formal-quantum-computation. Google DeepMind. https://github.com/google-deepmind/formal-quantum-computation (checked 2026-11-24; tier 3: official site)
10. Discovering formally verified quantum programs with AI. arXiv. published 2026-11-16. https://arxiv.org/abs/2611.09822v3 (checked 2026-11-24; tier 2: academic or news)
11. DeepMind's AI agents found cheaper quantum algorithms, and proved them. The Next Web. published 2026-11-23. https://thenextweb.com/news/google-deepmind-gemini-agents-quantum-algorithms-lean (checked 2026-11-24; tier 2: academic or news)
12. Google opens the proofs behind its AI-designed quantum programs. QubitWire. published 2026-11-23. https://qubitwire.com/articles/google-deepmind-quantum-program-proofs-public-release (checked 2026-11-24; tier 2: academic or news)

## Cite this page

Mimirwiki. "Lean (Theorem Prover)." Version 67e7441e, 2026-11-24. https://mimirwiki.com/wiki/lean-theorem-prover
