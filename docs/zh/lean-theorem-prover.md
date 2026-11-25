---
title: "Lean（定理证明器）"
subtitle: "开源函数式编程语言与交互式证明助手（Lean 4）"
canonical_url: https://mimirwiki.com/zh/wiki/lean-theorem-prover
language: zh
page_class: entity
revision_sha256: c077807ba42fcff74e2c22a534233035d804467b6d54770712411318fe0fa762
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/zh/wiki/lean-theorem-prover.md
  txt: https://mimirwiki.com/zh/wiki/lean-theorem-prover.txt
  json: https://mimirwiki.com/zh/wiki/lean-theorem-prover.json
  jsonld: https://mimirwiki.com/zh/wiki/lean-theorem-prover.jsonld
translations:
  en: https://mimirwiki.com/wiki/lean-theorem-prover
  ko: https://mimirwiki.com/ko/wiki/lean-theorem-prover
  ja: https://mimirwiki.com/ja/wiki/lean-theorem-prover
  es: https://mimirwiki.com/es/wiki/lean-theorem-prover
---

# Lean（定理证明器）

> Lean（Lean 4）是一种采用 Apache-2.0 许可证发布、由 Lean Focused Research Organization 支持的开源编程语言与证明助手。截至 2026-11-24，其最新稳定版本为 v4.36.0（2026-11-16），v4.37.0-rc1（2026-11-18）为候选发布版本；2026-11-23，Google DeepMind 开源了一套 Lean 4 量子程序验证库、形式化规范及证明。

Lean 是一种开源编程语言与交互式证明助手，旨在编写经过形式化验证的数学证明和软件。其代码仓库采用 Apache-2.0 许可证发布，开发工作由 Lean Focused Research Organization 提供支持。Lean 4 于 2023-09-08 发布了首个正式版本（v4.0.0）。截至 2026-11-24，最新稳定版本为 Lean 4.36.0（发布于 2026-11-16），而 Lean 4.37.0-rc1 已于 2026-11-18 作为预发布候选版本推出；随后，Mathlib 于 2026-11-19 发布了对应的预发布版本，Google DeepMind 则于 2026-11-23 公开了 Lean 4 量子程序验证材料。

**别名:** Lean 4, Lean 定理证明器, Lean 编程语言

## 关键事实

- **最新稳定版本:** v4.36.0（2026-11-16） (截至 2026-11-24) [5]
- **当前候选发布版本:** v4.37.0-rc1（2026-11-18，预发布版） (截至 2026-11-24) [6]
- **Lean 4 首个正式版本:** v4.0.0（2023-09-08） [4]
- **许可证:** Apache-2.0 [3]

## 事实摘要

- **类型:** 编程语言与交互式证明助手 [1]
- **支持机构:** Lean Focused Research Organization（Lean FRO） [2]
- **许可证:** Apache-2.0 [3]
- **Lean 4 首个正式版本:** v4.0.0（2023-09-08） [4]
- **最新稳定版本:** v4.36.0（2026-11-16） (截至 2026-11-24) [5]
- **最新预发布版本:** v4.37.0-rc1（2026-11-18） (截至 2026-11-24) [6]
- **主要数学库:** Mathlib（mathlib4） [4]
- **源代码仓库:** github.com/leanprover/lean4 [3]
- **官方网站:** lean-lang.org [1]

## Lean 概述与支持机构

Lean 是一种开源编程语言与证明助手，支持用户编写形式化数学证明和经过验证的软件。[1][3] Lean 4 代码仓库采用 Apache-2.0 许可证发布，Lean Focused Research Organization（Lean FRO）声明其致力于支持 Lean 的发展。[2][3]

Lean FRO 表示其使命是推进 Lean 的核心系统与能力建设，并列出了若干重点方向，包括可扩展性、易用性、证明自动化、文档建设、多元化社区，以及对 AI 研究和经过验证的代码合成的支持。[2] Lean 官方网站重点介绍的内置自动化功能示例包括用于归纳、代数推理和类 SMT 推理的 `grind` 策略，以及用于判定比特向量等式的 `bv_decide`。[1] Lean 4.0.0 发布说明将 Mathlib 描述为 Lean 的主要数学库（`mathlib4`），项目则通过 `lake` 构建工具和 `elan` 工具链管理器进行管理。[4][9]

## Lean 4 发布历史与 2026 年 11 月版本

Lean 4 于 2023-09-08 推出了首个正式版本 `v4.0.0`，当时开发团队宣布计划大约每月发布一次次要版本。[4]

| 版本 | 类型 | 发布日期 | 备注 |
| --- | --- | --- | --- |
| v4.0.0 | 稳定版 | 2023-09-08 | Lean 4 首个正式版本 |
| v4.36.0 | 稳定版（截至 2026-11-24 最新） | 2026-11-16 | GitHub 上最新稳定版发布标签 |
| v4.37.0-rc1 | 候选发布版（预发布版） | 2026-11-18 | 包含 370 项已合并变更；正式发布前可能调整 |

截至 2026-11-24，`v4.36.0`（发布于 2026-11-16）是 Lean 4 的最新稳定版本。[5] 2026-11-18，该项目发布了 `v4.37.0-rc1`，并明确将其标注为候选发布版本而非最终正式版本。[6] 其发布说明记录了 370 项已合并变更，包括 71 项功能新增、159 项缺陷修复、108 项性能改进、7 项重构变更、4 项测试套件改进、1 项文档改进和 20 项其他变更，其中一项变更新增了 `shiftLeft.threshold` 选项（默认值为 65536）。[6] 2026-11-19，`leanprover-community/mathlib4` 标记了预发布版本 `v4.37.0-rc1`，以将其工具链升级至该候选发布版本。[7]

## Lean 在形式化验证中的应用与 2026 年 11 月 DeepMind 开源发布

Lean FRO 将形式化数学以及软件与硬件验证列为 Lean 的应用领域。[1][2] 2026-11-23，Google DeepMind 宣布在 GitHub 上公开发布由 [Google Gemini](https://mimirwiki.com/zh/wiki/google-gemini)（Gemini 4）智能体团队合成并在 Lean 4 中完成检查的量子程序验证材料。[8][9]

该开源仓库（`google-deepmind/formal-quantum-computation`，采用 Apache-2.0 许可证）以带经典变量的量子霍尔逻辑为基础，依赖于 `Mathlib4` 以及 `QuantumInfo`（隶属于 `Physlib`）。[9] 仓库分为三个部分：核心 `QuantumComputation` 库（涵盖量子电路、量子门、寄存器、量子霍尔逻辑及资源计数）、`QuantumComputationSpecs`（形式化问题规范与基准测试挑战），以及存放所报告程序和 Lean 证明的 `discoveries` 分支。[9][12]

相关研究预印本（`arXiv:2611.09822v3`）最初提交于 2026-11-06，并于 2026-11-16 修订；2026-11-23 的新闻事件为该 Lean 库、规范及证明的公开发布，当天由 The Next Web 和 QubitWire 进行了报道。[8][10][11][12] DeepMind 与 QubitWire 均指出，所报告的资源缩减（例如量子比特与操作综合成本指标降低 11.8 倍，以及惯性约束聚变计算中的纠错量子比特数从 5,650 降至 4,338）是针对形式化规范和成本模型进行数学验证的结果，而非在物理量子硬件上的实测数据；此外，该仓库将经典计算与控制流的显式成本建模列为计划中的后续工作。[8][9][12]

## Lean 验证的范围与局限

正如针对 DeepMind 代码仓库发布的独立报道所指出的，经机器检查的 Lean 证明能够确认程序在所建模的成本假设下满足其形式化规范，但本身并不能证明这些规范或成本模型覆盖了物理硬件的所有瓶颈，也不能证明外部机构已独立复现了相关结果。[12]

## 常见问题

### 截至 2026-11-24，Lean 4 的最新稳定版本是什么？

截至 2026-11-24，Lean 4 的最新稳定版本是发布于 2026-11-16 的 v4.36.0。发布于 2026-11-18 的 Lean 4.37.0-rc1 属于候选发布版本（预发布版），而非最终正式版本。 [5][6]

### Mathlib 在 Lean 生态系统中是什么？

Mathlib（mathlib4）是 Lean 的主要数学库。2026-11-19，Mathlib 代码仓库发布了 v4.37.0-rc1 预发布版本，将其工具链更新以匹配 Lean 4.37.0-rc1。 [4][7]

### Google DeepMind 于 2026-11-23 发布了哪些与 Lean 相关的内容？

2026-11-23，Google DeepMind 宣布公开发布采用 Apache-2.0 许可证的 GitHub 仓库 formal-quantum-computation，其中包含其 2026 年 11 月预印本中的 Lean 4 量子程序库、形式化问题规范以及 Lean 证明。 [8][9][10]

### DeepMind 的 Lean 开源发布是否演示了在物理量子计算机上的运行？

没有。2026-11-23 的公告是 Lean 验证材料的公开发布，所报告的资源改进源于形式化规范和数学成本模型，而非物理量子硬件上的运行耗时测量。 [8][12]

## 可引用的句子

- Lean 是一种采用 Apache-2.0 许可证发布、由 Lean Focused Research Organization 支持的开源编程语言与证明助手。 [1][2][3]
- Lean 4 首个正式版本 Lean 4.0.0 发布于 2023-09-08。 [4]
- 截至 2026-11-24，Lean v4.36.0（发布于 2026-11-16）是 GitHub 上的最新稳定发布版本。 [5]
- Lean 4.37.0-rc1 于 2026-11-18 作为包含 370 项已合并变更的候选发布版本推出，Mathlib 则于 2026-11-19 发布了对应的 v4.37.0-rc1 预发布版本。 [6][7]
- 2026-11-23，Google DeepMind 在 google-deepmind/formal-quantum-computation 中开源了其 Lean 4 量子程序验证库、问题规范和经过验证的解法。 [8][9]
- 配套预印本 arXiv:2611.09822v3 提交于 2026-11-06 并于 2026-11-16 修订，其中报告的电路成本数据源自形式化模型，而非物理量子硬件的实际运行。 [10][12]

## 时间线

- 2023-09-08: Lean 4.0.0 作为 Lean 4 首个正式版本发布。 [4]
- 2026-11-06: 作者提交预印本 arXiv:2611.09822，介绍使用 Gemini 4 智能体在 Lean 中发现经过形式化验证的量子程序（于 2026-11-16 修订为 v3）。 [10]
- 2026-11-16: Lean v4.36.0 作为稳定版本在 GitHub 上发布。 [5]
- 2026-11-18: Lean 4.37.0-rc1 作为包含 370 项已合并变更的候选发布版本推出。 [6]
- 2026-11-19: Mathlib（mathlib4）发布预发布版本 v4.37.0-rc1，将其工具链更新至 Lean 4.37.0-rc1。 [7]
- 2026-11-23: Google DeepMind 宣布在 GitHub 上公开发布其 Lean 4 量子程序验证库、问题规范和经过验证的解法。 [8][9]

## 来源

1. Lean Programming Language. Lean Focused Research Organization. https://lean-lang.org/ (访问于 2026-11-24; tier 3: official site)
2. Lean Focused Research Organization. Lean Focused Research Organization. https://lean-fro.org/ (访问于 2026-11-24; tier 3: official site)
3. leanprover/lean4: Lean 4 programming language and theorem prover. Lean Focused Research Organization. https://github.com/leanprover/lean4 (访问于 2026-11-24; tier 3: official site)
4. Release v4.0.0 - leanprover/lean4. Lean Focused Research Organization. 发布于 2023-09-08. https://github.com/leanprover/lean4/releases/tag/v4.0.0 (访问于 2026-11-24; tier 3: official site)
5. Release v4.36.0 - leanprover/lean4. Lean Focused Research Organization. 发布于 2026-11-16. https://github.com/leanprover/lean4/releases/tag/v4.36.0 (访问于 2026-11-24; tier 3: official site)
6. Lean 4.37.0-rc1 (2026-11-18). Lean Focused Research Organization. 发布于 2026-11-18. https://lean-lang.org/doc/reference/latest/releases/v4.37.0/ (访问于 2026-11-24; tier 3: official site)
7. Release v4.37.0-rc1 - leanprover-community/mathlib4. Lean Community. 发布于 2026-11-19. https://github.com/leanprover-community/mathlib4/releases/tag/v4.37.0-rc1 (访问于 2026-11-24; tier 3: official site)
8. Finding faster quantum algorithms with agents and formal verification. Google DeepMind. 发布于 2026-11-23. https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/ (访问于 2026-11-24; tier 3: official site)
9. google-deepmind/formal-quantum-computation. Google DeepMind. https://github.com/google-deepmind/formal-quantum-computation (访问于 2026-11-24; tier 3: official site)
10. Discovering formally verified quantum programs with AI. arXiv. 发布于 2026-11-16. https://arxiv.org/abs/2611.09822v3 (访问于 2026-11-24; tier 2: academic or news)
11. DeepMind's AI agents found cheaper quantum algorithms, and proved them. The Next Web. 发布于 2026-11-23. https://thenextweb.com/news/google-deepmind-gemini-agents-quantum-algorithms-lean (访问于 2026-11-24; tier 2: academic or news)
12. Google opens the proofs behind its AI-designed quantum programs. QubitWire. 发布于 2026-11-23. https://qubitwire.com/articles/google-deepmind-quantum-program-proofs-public-release (访问于 2026-11-24; tier 2: academic or news)

## 引用本页

Mimirwiki. "Lean（定理证明器）." 版本 c077807b, 2026-11-24. https://mimirwiki.com/zh/wiki/lean-theorem-prover
