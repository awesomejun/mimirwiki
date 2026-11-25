---
title: "黎曼猜想"
subtitle: "1859 年提出的关于黎曼 ζ 函数非平凡零点的猜想，已于 2026 年 11 月在 Lean 4 中完成形式化证明与验证"
canonical_url: https://mimirwiki.com/zh/wiki/riemann-hypothesis
language: zh
page_class: concept
revision_sha256: 72c57dfe729e9094e21d55abf7972bc7fcec9bdca3da081e4f6421a8e08f1782
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 9
alternates:
  md: https://mimirwiki.com/zh/wiki/riemann-hypothesis.md
  txt: https://mimirwiki.com/zh/wiki/riemann-hypothesis.txt
  json: https://mimirwiki.com/zh/wiki/riemann-hypothesis.json
  jsonld: https://mimirwiki.com/zh/wiki/riemann-hypothesis.jsonld
translations:
  en: https://mimirwiki.com/wiki/riemann-hypothesis
  ko: https://mimirwiki.com/ko/wiki/riemann-hypothesis
  ja: https://mimirwiki.com/ja/wiki/riemann-hypothesis
  es: https://mimirwiki.com/es/wiki/riemann-hypothesis
---

# 黎曼猜想

> 2026 年 11 月 20 日，Anthropic 数学家莱文特·阿尔波格（Levent Alpoge）发布了黎曼猜想以及狄利克雷 L 函数广义黎曼猜想（GRH）的完整形式化证明，该证明以包含 1700 万行代码的 Lean 4 库形式发布（基于 Lean v4.33.1 和 Mathlib v4.33.1，共 175,187 个模块），由其与 Claude AI 历时六周合作完成，核心方法是在定酉群之间构造长度与 sqrt(X) 成正比的迭代 θ 提升。2026 年 11 月 21 日至 22 日，Lean FRO、Mathlib 计划以及麻省理工学院数学家安德鲁·萨瑟兰认证该库能够无错编译、仅使用 Lean 的三条标准公理、与 Mathlib 中精确的 RiemannHypothesis 命题完全一致，并通过了多个独立证明内核（nanoda、con-leche、con-ron 和 lean4lean）的检验；而同期发布的另一篇由亚历山德罗·马苏洛撰写的非 AI 预印本则在八小时内被指出存在论证漏洞。

黎曼猜想（Riemann Hypothesis，简称 RH）由德国数学家伯恩哈德·黎曼于 1859 年 11 月在其论文《论小于给定数值的素数个数》中提出，是解析数论中的核心基础猜想，断言黎曼 ζ 函数 ζ(s) 的所有非平凡零点均位于实部 Re(s) = 1/2 的临界线上。该猜想于 1900 年被列为希尔伯特第八问题的一部分，并于 2000 年 5 月被克雷数学研究所（CMI）列为七大千禧年大奖难题之一（奖金 100 万美元），它决定了素数定理的误差项以及素数的分布规律。

**别名:** RH, 广义黎曼猜想, GRH, 希尔伯特第八问题, 黎曼 ζ 猜想

## 关键事实

- **提出者:** 伯恩哈德·黎曼（1859 年） [1]
- **数学表述:** ζ(s)（以及 GRH 下的狄利克雷 L(χ, s)）的所有非平凡零点均满足实部 Re(s) = 1/2 [1]
- **2026 年 11 月 20 日形式化证明:** 莱文特·阿尔波格（Anthropic）与 Claude AI：横跨 175,187 个模块的 1700 万行 Lean 4 代码 (截至 2026-11-20) [3]
- **独立内核验证:** 于 2026 年 11 月 21 日至 22 日获 Lean FRO、Mathlib 计划及安德鲁·萨瑟兰（MIT）认证 (截至 2026-11-22) [4]

## 事实摘要

- **学科领域:** 解析数论 / 自守形式 [1]
- **猜想提出者:** 格奥尔格·弗里德里希·伯恩哈德·黎曼（1826–1866），1859 年 [1]
- **重大难题认定:** 希尔伯特第 8 问题（1900 年）；克雷千禧年大奖难题（奖金 1,000,000 美元，2000 年 5 月 24 日公布） [2]
- **形式化证明作者:** 莱文特·阿尔波格（与 Anthropic 的 Claude AI 合作，2026 年 11 月 20 日发布） [3]
- **形式化验证环境:** Lean v4.33.1 / Mathlib v4.33.1（17,000,000+ 行；175,187 个模块；61.57 GB 原始证明导出文件） [5]
- **Main.lean 中已验证定理:** riemannHypothesis、riemannZeta_eq_zero_re 及 3 个狄利克雷 L 函数 GRH 定理（含罗宾与拉加里亚斯不等式） [5]
- **独立证明检验器:** Lean 内核（leanchecker）、nanoda（Rust）、con-leche、con-ron（Rust）、lean4lean [4]

## 黎曼猜想的数学表述与素数分布

**黎曼 ζ 函数** $\zeta(s)$ 对于实部满足 $\text{Re}(s) = \sigma > 1$ 的复数 $s = \sigma + it$，由收敛的狄利克雷级数以及遍历所有素数 $p$ 的欧拉乘积定义。[1] $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$ 在 1859 年提交给柏林科学院的论文中，**格奥尔格·弗里德里希·伯恩哈德·黎曼**（1826-1866）通过解析延拓将 $\zeta(s)$ 扩展为整个复平面 $\mathbb{C}$ 上仅在 $s = 1$ 处有一个单极点的亚纯函数，并证明其满足联系 $\zeta(s)$ 与 $\zeta(1-s)$ 的对称函数方程。[1]

由于函数方程中伽马因子的作用，$\zeta(s)$ 在负偶数 $s = -2, -4, -6, \dots$ 处取值为零，这些点称为**平凡零点**。[1][5] 其余所有零点，即**非平凡零点**，均位于临界带 $0 < \text{Re}(s) < 1$ 内。[1][5] **黎曼猜想（RH）**断言 $\zeta(s)$ 的每一个非平凡零点都位于垂直的**临界线** $\text{Re}(s) = 1/2$ 上。[1] 等价地，就素数计数函数 $\pi(x)$ 与对数积分 $\text{Li}(x)$ 而言，黎曼猜想给出了最优的平方根误差界 $\pi(x) = \text{Li}(x) + O(\sqrt{x} \log x)$。[1][3]

大卫·希尔伯特于 1900 年 8 月 9 日在巴黎国际数学家大会上将黎曼猜想列为其 23 个问题中的第 8 个问题；**2000 年 5 月 24 日**，**克雷数学研究所（CMI）**将其列为七大**千禧年大奖难题**之一，为经验证的证明设立 100 万美元奖金。[1][2] 在 2026 年 11 月之前，数值计算已验证前 $10^{13}$ 个（10 万亿个）非平凡零点均位于临界线上，而**广义黎曼猜想（GRH）**则将该猜想推广至所有狄利克雷 $L$ 函数 $L(\chi, s)$。[1][5]

## 2026 年 11 月 20 日莱文特·阿尔波格与 Claude 的形式化证明

**2026 年 11 月 20 日**，即其雇主 Anthropic 在纳斯达克完成首次公开募股的次日，数学家**莱文特·阿尔波格**（Levent Alpoge）发布了一份 4 页的说明文档（`alpo.ge/remark.pdf`）以及 14 个分卷压缩归档文件（`lean.tar.gz.part01` 至 `part14`），其中包含在 **Lean 4** 定理证明器中完成的、不依赖任何额外假设的**黎曼猜想**及狄利克雷 $L$ 函数**广义黎曼猜想（GRH）**的完整形式化证明。[3][4][8]

根据阿尔波格公布的时间线，该证明是在 **2026 年 10 月 6 日至 11 月 16 日**的六周冲刺期内，与 Anthropic 的 **Claude** AI 紧密合作完成的。[3][8] 考虑到将未经简化的论证转化为自然语言论文会产生超过 25 万页难以阅读的文本，阿尔波格选择直接发布完整的可机检 Lean 代码库，涵盖 **175,187 个 Lean 模块**中的 **1700 万行代码**。[3][4][5]

在数学方法上，阿尔波格与 Claude 构造了**斯捷潘诺夫（Stepanov）辅助多项式方法**（该方法利用高阶除子重数证明函数域上的黎曼猜想）在数域上的原生类似物。[3] - 由于在整数环 $\mathbb{Z}$ 上难以直接构造高阶导数重数，该证明将定号二次型与帕塞瓦尔恒等式（$qN = M_k + R$）以及吉南-韦伊（Guinand-Weil）显式公式，与全定酉群（及正交群 $O(2, n)$）之间的**迭代 θ 提升** $U(X_0) \to U(X_1) \to \dots \to U(X_m)$ 相结合。[3] - 每一次 θ 提升对应模拟一阶斯捷潘诺夫重数。阿尔波格指出 Claude 提出的决定性突破在于：针对长度为 $X$ 的冯·曼戈尔特和 $\sum_{n \le X} \Lambda(n)$，证明串联起一条长度为 **$m \approx \sqrt{X}$** 的 θ 提升塔，并通过**乔拉-塞尔伯格（Chowla-Selberg）公式**、**西格尔（Siegel）质量公式**、**拉利斯（Rallis）内积与跷跷板恒等式**、**博斯特（Bost）斜率不等式**，以及结合贝伦德（Behrend）迹公式和附着于 CM 域上 $\text{GL}_n$ 正则代数极化尖点自守表示的伽罗瓦表示所构造的**岩泽塔**，对范数、水平和整除性进行精确控制。[3][9]

## Lean FRO、Mathlib 与麻省理工学院的独立认证

由于 AI 辅助生成的数学代码库需要严格审计，以确保形式化定理的陈述未被篡改或平凡化，且未引入自定义公理或编译器漏洞利用（伦敦帝国理工学院数学家**凯文·巴扎德**于 2026 年 11 月 12 日在 Xena 项目博客中提出了这一四步协议[7]），形式化验证社区随即对阿尔波格的代码库展开了全面审计。[4][5]

**2026 年 11 月 21 日**，**Lean 专项研究组织（Lean FRO）**与 **Mathlib 计划**（Mathlib Initiative）发表联合声明，认证阿尔波格的黎曼猜想证明完全有效并满足全部四项验证标准。[4] 与此同时，麻省理工学院数学家**安德鲁·萨瑟兰**（Andrew Sutherland）发布了详尽的验证面板（`math.mit.edu/~drew/grh/`），记录了基于 **Lean v4.33.1** 和 **Mathlib v4.33.1** 完成的可复现检查结果。[5]

| 验证标准 | 审计观测结果（截至 2026 年 11 月 22 日） |
| --- | --- |
| **1. 编译与可复现性** | 全部 **175,187 个模块**在隔离、断网、只读的沙箱环境中零错误编译（`lake build Main`），精确复现了 **61,570,595,788 字节**（61.57 GB）的原始证明导出文件（`sha256: 5ea74b91...244e`）。[4][5] |
| **2. 公理与规范审计** | `#print axioms` 确认全部五项核心定理**仅**依赖于 Lean 的三条标准基础公理（`propext`、`Classical.choice` 和 `Quot.sound`），无任何用户自定义公理，且 8,322 个 Mathlib `.olean` 缓存文件逐字节未经修改。[5] |
| **3. 精确命题匹配** | 独立比对工具（`con-leche --compare` 及其 Rust 移植版 `con-ron --compare`，将 1,468,418 条解答声明与 51,692 条目标声明逐一校验）确认 `Main.lean` 证明了 Mathlib 中精确的 `RiemannHypothesis` 定义（`∀ (s : ℂ) (_ : riemannZeta s = 0) (_ : ¬∃ n : ℕ, s = -2 * (n + 1)) (_ : s ≠ 1), s.re = 1 / 2`）以及**所有狄利克雷 L 函数的 GRH**（`LFunction_ne_zero_of_half_lt_re`、`LFunction_eq_zero_re`、`LFunction_eq_zero_re_of_isPrimitive`）。[4][5] |
| **4. 多内核证明检验** | 所有模块均通过 `leanchecker` 和 `lean4lean`（在 Lean 中经形式化验证），完整的 61.57 GB 静态导出文件亦获 Rust 内核 **`nanoda`**（80 线程耗时 27 分 42 秒）以及经形式化验证的集合论检验器 **`con-leche`**（64 线程耗时 3 分 15 秒）和 **`con-ron`**（64 线程耗时 7 分 06 秒）独立验收。[4][5] |

作为一项完全独立于 Mathlib 中 $\zeta(s)$ 解析定义的额外检验，萨瑟兰将阿尔波格的证明与**罗宾不等式**（对所有 $n > 5040$ 有 $\sigma(n) < e^{\gamma} n \log \log n$）及**拉加里亚斯不等式**（对所有 $n > 0$ 有 $\sigma(n) \le H_n + e^{H_n} \log H_n$）的独立形式化相结合，无条件推导出了这两条约数和不等式的初等证明。[5]

## 同期人类独立预印本及其对数学界的影响

在阿尔波格发布证明的同一天（**2026 年 11 月 20 日**），斯坦福大学数学家**拉维·瓦基尔**（Ravi Vakil）发布了另一份完全由人类独立撰写的广义黎曼猜想证明草稿，作者为意大利数学家**亚历山德罗·玛丽亚·马苏洛**（Alessandro Maria Masullo）。马苏洛在未使用 AI 的情况下已研究该问题长达 12 年，此前一直与斯坦福大学教授布莱恩·康拉德共同审阅该手稿。[6][8][9] 由于阿尔波格的发布使得再等待一年进行修订不再现实，瓦基尔在修订中途公开了马苏洛的草稿；然而在八小时内，瓦基尔更新帖子称，多名数学家（在 AI 验证工具的辅助下）已在马苏洛的手稿中发现了未解决的论证漏洞。[6]

相比之下，由于阿尔波格的 1700 万行 Lean 证明已通过多内核形式化验证，数学界的关注点已从争论黎曼猜想和狄利克雷 GRH 是否成立，转向从这份经机器验证的自守提升证明中提炼人类可理解的概念性简化版本。[3][4][9] 需要注意的是，截至 2026 年 11 月 22 日，已完成验证的形式化范围涵盖经典黎曼 ζ 函数 $\zeta(s)$ 以及所有模与特征的**狄利克雷 $L$ 函数**，而戴德金 ζ 函数、一般赫克 $L$ 函数及任意高阶自守 $L$ 函数尚未包含在 `Main.lean` 已检验的形式化定理陈述之中。[5]

## 常见问题

### 黎曼猜想是否已经得到证明并完成验证？

是的。2026 年 11 月 20 日，数学家莱文特·阿尔波格（与 Anthropic 的 Claude AI 合作）在 Lean 4 定理证明器中发布了长达 1700 万行的黎曼猜想及狄利克雷 L 函数广义黎曼猜想的形式化证明。2026 年 11 月 21 日至 22 日，Lean 专项研究组织（FRO）、Mathlib 计划及麻省理工学院数学家安德鲁·萨瑟兰共同认证，该证明编译无误、仅使用标准公理、与 Mathlib 官方定理陈述完全一致，并通过了多个独立证明内核的检验。 [3][4][5]

### 黎曼猜想的具体内容是什么？

黎曼猜想由伯恩哈德·黎曼于 1859 年提出，断言黎曼 ζ 函数 ζ(s) 的所有非平凡零点（即除负偶数 -2、-4、-6 等之外的 ζ(s) = 0 的所有解）都是实部恰好等于 1/2 的复数。 [1][5]

### 莱文特·阿尔波格与 Claude 使用了什么数学方法证明黎曼猜想？

该证明将斯捷潘诺夫的函数域重数论证推广至整数情形，把定号二次型帕塞瓦尔恒等式与吉南-韦伊显式公式同全定酉群上长度与 sqrt(X) 成正比的迭代 θ 提升链相结合，并借助乔拉-塞尔伯格公式、西格尔质量公式、拉利斯跷跷板恒等式、博斯特斜率不等式及岩泽塔构造加以控制。 [3][9]

### 数学家如何确认长达 1700 万行的 AI 辅助证明没有隐藏错误或作弊漏洞？

依据四步 Lean 验证协议，审计人员在离线沙箱中重新编译了全部 175,187 个模块以生成 61.57 GB 的静态证明导出文件，核实仅使用了 Lean 的三条标准公理（propext、Classical.choice、Quot.sound），将所证定理与 Mathlib 未经修改的 RiemannHypothesis 定义进行精确比对，并使用不同编程语言编写的独立证明检验器（包括 nanoda、con-leche、con-ron 和 lean4lean）检验原始导出文件，同时还由此推导出了罗宾不等式与拉加里亚斯不等式两条初等约数和不等式。 [4][5][7]

### 2026 年 11 月同期发布的亚历山德罗·马苏洛的人类独立证明尝试结果如何？

2026 年 11 月 20 日，斯坦福大学教授拉维·瓦基尔发布了亚历山德罗·玛丽亚·马苏洛撰写的一份非 AI 广义黎曼猜想证明修订中草稿。发布后八小时内，借助 AI 分析工具的数学家们在马苏洛的草稿中发现了尚未解决的论证漏洞，而阿尔波格的 Lean 4 形式化证明则通过了完整的内核认证。 [4][6][9]

## 可引用的句子

- 黎曼猜想由伯恩哈德·黎曼于 1859 年提出，并于 2000 年被列为奖金 100 万美元的克雷数学研究所千禧年大奖难题，该猜想断言黎曼 ζ 函数的所有非平凡零点实部均为 1/2。 [1][2]
- 2026 年 11 月 20 日，莱文特·阿尔波格发布了与 Anthropic 的 Claude AI 共同开发的 1700 万行 Lean 4 形式化代码（175,187 个模块），证明了黎曼猜想及狄利克雷 L 函数的广义黎曼猜想。 [3][4][5]
- 2026 年 11 月 21 日，Lean FRO 与 Mathlib 计划认证阿尔波格的黎曼猜想证明有效，能在 Mathlib 上无错编译，证明了 Mathlib 中的精确命题，并通过了包括 con-leche 和 con-ron 在内的独立证明检验器。 [4]
- 麻省理工学院数学家安德鲁·萨瑟兰验证了阿尔波格的 175,187 个 Lean v4.33.1 模块仅使用三条标准公理（propext、Classical.choice、Quot.sound）即可复现 61,570,595,788 字节的导出文件，获 nanoda、con-leche、con-ron、leanchecker 和 lean4lean 验收，并无条件蕴含罗宾与拉加里亚斯约数和不等式。 [5]
- 2026 年 11 月 20 日由拉维·瓦基尔另行发布的亚历山德罗·玛丽亚·马苏洛的非 AI 广义黎曼猜想手稿，在八小时内被审阅者指出存在数学问题。 [6][9]

## 时间线

- 1859-11: 伯恩哈德·黎曼发表《论小于给定数值的素数个数》，提出黎曼猜想。 [1]
- 1900-08-09: 大卫·希尔伯特在巴黎国际数学家大会的演讲中将黎曼猜想列为第 8 问题。 [2]
- 2000-05-24: 克雷数学研究所在巴黎将黎曼猜想列为七大奖金 100 万美元的千禧年大奖难题之一。 [1][2]
- 2026-10-06: 莱文特·阿尔波格以斯捷潘诺夫行列式与博斯特斜率不等式为起点，与 Anthropic 的 Claude AI 启动为期六周的形式化与证明探索冲刺。 [3]
- 2026-11-16: 阿尔波格与 Claude 利用长度为 sqrt(X) 的迭代 θ 提升，完成了狄利克雷 L 函数广义黎曼猜想的 Lean 4 形式化证明。 [3]
- 2026-11-20: 阿尔波格公开发布 remark.pdf 与 1700 万行 Lean 4 证明归档；拉维·瓦基尔另行发布了亚历山德罗·马苏洛的人类撰写草稿，后者在八小时内被发现存在漏洞。 [3][6][9]
- 2026-11-21: Lean FRO、Mathlib 计划及安德鲁·萨瑟兰（MIT）在多个独立证明内核上独立认证了阿尔波格 Lean 4 证明的正确性。 [4][5][8]

## 来源

1. Riemann Hypothesis - Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium/riemann-hypothesis/ (访问于 2026-11-23; tier 2: academic or news)
2. The Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium-problems/ (访问于 2026-11-23; tier 2: academic or news)
3. Remark on a Proof and Lean Formalization of the Riemann Hypothesis and Generalized Riemann Hypothesis. Levent Alpoge (alpo.ge). 发布于 2026-11-20. https://alpo.ge/remark.pdf (访问于 2026-11-23; tier 3: official site)
4. Lean Verification of the Riemann Hypothesis: Joint Statement by the Lean FRO and the Mathlib Initiative. Lean Focused Research Organization & Mathlib Initiative. 发布于 2026-11-21. https://leanprover-community.github.io/blog/posts/riemann-hypothesis/ (访问于 2026-11-23; tier 3: official site)
5. RH Lean Proof: Verification Files and Independent Kernel Audit. Andrew Sutherland (Massachusetts Institute of Technology). 发布于 2026-11-22. https://math.mit.edu/~drew/grh/ (访问于 2026-11-23; tier 2: academic or news)
6. Hurried Announcement: Alessandro Masullo GRH (with Nov 20-22 Updates). Ravi Vakil (Stanford University / Math 216 Blog). 发布于 2026-11-20. https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/ (访问于 2026-11-23; tier 2: academic or news)
7. '...and the proof is checked in Lean' (Four Criteria for Verifying AI-Generated Lean Proofs). Kevin Buzzard (Xena Project). 发布于 2026-11-12. https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/ (访问于 2026-11-23; tier 2: academic or news)
8. Two groups verify mathematician's claim that Claude helped prove mathematics problem. The Guardian. 发布于 2026-11-21. https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai (访问于 2026-11-23; tier 2: academic or news)
9. AI claimed a solution to the 167-year-old Riemann hypothesis - and a human did, too. TechCrunch. 发布于 2026-11-20. https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/ (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "黎曼猜想." 版本 72c57dfe, 2026-11-24. https://mimirwiki.com/zh/wiki/riemann-hypothesis
