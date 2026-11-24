---
title: "リーマン予想"
subtitle: "リーマンゼータ関数の非自明な零点に関する1859年の予想であり、2026年11月にLean 4で形式証明および独立検証が完了した"
canonical_url: https://mimirwiki.com/ja/wiki/riemann-hypothesis
language: ja
page_class: concept
revision_sha256: f759e2c22128b9a87727659566acb7ca89c73d88be196fce911307a177ce5e85
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 9
alternates:
  md: https://mimirwiki.com/ja/wiki/riemann-hypothesis.md
  txt: https://mimirwiki.com/ja/wiki/riemann-hypothesis.txt
  json: https://mimirwiki.com/ja/wiki/riemann-hypothesis.json
  jsonld: https://mimirwiki.com/ja/wiki/riemann-hypothesis.jsonld
translations:
  en: https://mimirwiki.com/wiki/riemann-hypothesis
  ko: https://mimirwiki.com/ko/wiki/riemann-hypothesis
  zh: https://mimirwiki.com/zh/wiki/riemann-hypothesis
---

# リーマン予想

> 2026年11月20日、Anthropic所属の数学者レヴェント・アルポゲ（Levent Alpoge）は、Claude AIと6週間にわたり共同で構築した、リーマン予想およびディリクレL関数に対する一般化リーマン予想（GRH）の完全な形式証明を、1,700万行規模のLean 4ライブラリ（Lean v4.33.1およびMathlib v4.33.1上の175,187モジュール）として公開した。証明では、定値ユニタリ群の間で長さ sqrt(X) に比例する反復テータリフトを用いている。2026年11月21〜22日、Lean FRO、Mathlibイニシアティブ、およびMITの数学者アンドリュー・サザーランドは、このライブラリがエラーなくコンパイルされ、Leanの3つの標準公理のみを使用し、Mathlibの厳密なRiemannHypothesisの定式化と一致し、独立した複数の証明カーネル（nanoda、con-leche、con-ron、lean4lean）を通過したことを認定した。一方、同日に公開されたアレッサンドロ・マスッロによる非AIのプレプリントには、公開から8時間以内に論理的間隙が指摘された。

リーマン予想（Riemann Hypothesis、略称RH）は、ドイツの数学者ベルンハルト・リーマンが1859年11月の論文『与えられた数より小さい素数の個数について』で提唱した解析的整数論の基礎的予想であり、リーマンゼータ関数 ζ(s) のすべての非自明な零点が実部 Re(s) = 1/2 の臨界線上に位置すると主張するものである。1900年にヒルベルトの第8問題の一部として掲げられ、2000年5月にはクレイ数学研究所の7つのミレニアム懸賞問題（賞金100万ドル）の1つに選定された。素数定理の誤差項および素数の分布を支配する命題である。

**別名:** RH, 一般化リーマン予想, GRH, ヒルベルトの第8問題, リーマンゼータ予想

## 主要な事実

- **提唱者:** ベルンハルト・リーマン（1859年） [1]
- **数学的主張:** ζ(s)（およびGRHにおけるディリクレL関数 L(χ, s)）のすべての非自明な零点は実部 Re(s) = 1/2 を持つ [1]
- **2026年11月20日の形式証明:** レヴェント・アルポゲ（Anthropic）とClaude AI：175,187モジュールにわたる1,700万行のLean 4コード (時点 2026-11-20) [3]
- **独立カーネル検証:** 2026年11月21〜22日にLean FRO、Mathlibイニシアティブ、アンドリュー・サザーランド（MIT）が認定 (時点 2026-11-22) [4]

## ファクトシート

- **分野:** 解析的整数論 / 保型形式 [1]
- **提唱者:** ゲオルク・フリードリヒ・ベルンハルト・リーマン（1826–1866）、1859年 [1]
- **懸賞・問題指定:** ヒルベルトの第8問題（1900年）；クレイ数学研究所ミレニアム懸賞問題（賞金1,000,000ドル、2000年5月24日発表） [2]
- **形式証明の著者:** レヴェント・アルポゲ（AnthropicのClaude AIとの共同研究、2026年11月20日発表） [3]
- **形式検証環境:** Lean v4.33.1 / Mathlib v4.33.1（17,000,000行以上；175,187モジュール；生証明エクスポート61.57 GB） [5]
- **Main.leanで検証された定理:** riemannHypothesis、riemannZeta_eq_zero_re、およびディリクレL関数のGRH定理3件（＋ロバンおよびラガリアスの不等式） [5]
- **独立証明チェッカー:** Leanカーネル（leanchecker）、nanoda（Rust）、con-leche、con-ron（Rust）、lean4lean [4]

## リーマン予想の数学的定式化と素数の分布

**リーマンゼータ関数** $\zeta(s)$ は、実部 $\text{Re}(s) = \sigma > 1$ を満たす複素数 $s = \sigma + it$ に対して、収束するディリクレ級数およびすべての素数 $p$ にわたるオイラー積によって次のように定義される。[1] $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$ 1859年にベルリン科学アカデミーへ提出した論文において、**ゲオルク・フリードリヒ・ベルンハルト・リーマン**（1826-1866）は解析接続によって $\zeta(s)$ を $s = 1$ に唯一の1位の極を持つ複素平面 $\mathbb{C}$ 全体上の有理型関数へと拡張し、$\zeta(s)$ と $\zeta(1-s)$ を結びつける対称な関数等式を満たすことを示した。[1]

関数等式に含まれるガンマ因子の影響により、$\zeta(s)$ は負の偶数 $s = -2, -4, -6, \dots$ で零となり、これらは**自明な零点**と呼ばれる。[1][5] それ以外のすべての零点である**非自明な零点**は、臨界帯 $0 < \text{Re}(s) < 1$ の内部に存在する。[1][5] **リーマン予想（RH）**は、$\zeta(s)$ のすべての非自明な零点が垂直な**臨界線** $\text{Re}(s) = 1/2$ 上に存在すると主張するものである。[1] 同値な表現として、素数計数関数 $\pi(x)$ と対数積分 $\text{Li}(x)$ を用いると、リーマン予想は最適な平方根誤差評価 $\pi(x) = \text{Li}(x) + O(\sqrt{x} \log x)$ を与える。[1][3]

ダフィット・ヒルベルトは1900年8月9日のパリ国際数学者会議で23の問題の第8問題としてリーマン予想を含め、**2000年5月24日**には**クレイ数学研究所（CMI）**が7つの**ミレニアム懸賞問題**の1つに指定し、検証された証明に対して100万ドルの賞金を設定した。[1][2] 2026年11月以前には、数値計算によって最初の $10^{13}$ 個（10兆個）の非自明な零点が臨界線上にあることが確認されており、またすべてのディリクレ $L$ 関数 $L(\chi, s)$ へ拡張した命題は**一般化リーマン予想（GRH）**と呼ばれる。[1][5]

## 2026年11月20日のレヴェント・アルポゲとClaudeによる形式証明

**2026年11月20日**、所属企業であるAnthropicがナスダック（Nasdaq）への新規株式公開（IPO）を完了した翌日に、数学者**レヴェント・アルポゲ**（Levent Alpoge）は4ページの解説ノート（`alpo.ge/remark.pdf`）および14分割の圧縮アーカイブ（`lean.tar.gz.part01` から `part14`）を公開した。これらには、定理証明支援系 **Lean 4** において仮定を一切置かずに完全に形式化された**リーマン予想**およびディリクレ $L$ 関数に対する**一般化リーマン予想（GRH）**の証明が含まれている。[3][4][8]

アルポゲが公開した時系列によれば、この証明は **2026年10月6日から11月16日まで**の6週間の集中開発期間に、Anthropicの **Claude** AIとの緊密な協働によって構築された。[3][8] 未整理の論証を通常の文章による論文へ書き起こすと25万ページを超える可読性のない文書になると判断したアルポゲは、**175,187個のLeanモジュール**にわたる**1,700万行のコード**から成る、機械検証可能な完全なLeanコードベースを公開することを選択した。[3][4][5]

数学的手法として、アルポゲとClaudeは、関数体上のリーマン予想を高次の因子重複度によって証明する**ステパノフ（Stepanov）の補助多項式法**の数体における固有の類似物を構築した。[3] - 整数環 $\mathbb{Z}$ 上では高階微分による重複度を直接構成することが困難であるため、この証明では符号定値二次形式・パーセバル恒等式（$qN = M_k + R$）およびギナン・ヴェイユ（Guinand-Weil）の明示公式を、完全定値ユニタリ群（および直交群 $O(2, n)$）の間の**反復テータリフト** $U(X_0) \to U(X_1) \to \dots \to U(X_m)$ と組み合わせている。[3] - 各テータリフトがステパノフの重複度の1次数を模倣する。アルポゲがClaudeによって提案された決定的突破口として挙げた点として、長さ $X$ のフォン・マンゴルト和 $\sum_{n \le X} \Lambda(n)$ に対し、証明は長さ **$m \approx \sqrt{X}$** のテータリフトの塔を連結し、**チョウラ・セルバーグ（Chowla-Selberg）公式**、**ジーゲル（Siegel）の質量公式**、**ラリス（Rallis）の内積・シーソー恒等式**、**ボスト（Bost）の傾き不等式**、さらにはベーレント（Behrend）の跡公式およびCM体上の $\text{GL}_n$ の正則代数的偏極尖点保型表現に付随するガロア表現を用いた**岩澤塔**の構成によって、ノルム、レベル、整除性を制御している。[3][9]

## Lean FRO、Mathlibイニシアティブ、およびMITによる独立認定

AI支援による数学コードベースでは、形式化された定理の主張が改変・自明化されていないことや、独自公理やコンパイラの脆弱性悪用が混入していないことを厳格に監査する必要がある。この要件は、インペリアル・カレッジ・ロンドンの数学者**ケヴィン・バザード**（Kevin Buzzard）が2026年11月12日にXena Projectブログで示した4段階プロトコルとして定式化されており、[7] 形式検証コミュニティは直ちにアルポゲのリポジトリの監査に着手した。[4][5]

**2026年11月21日**、**Lean Focused Research Organization（Lean FRO）**と **Mathlibイニシアティブ**（Mathlib Initiative）は共同声明を発表し、アルポゲによるリーマン予想の証明が完全に正当であり4つの検証基準すべてを満たしていることを認定した。[4] 並行して、MITの数学者**アンドリュー・サザーランド**（Andrew Sutherland）は包括的な検証ダッシュボード（`math.mit.edu/~drew/grh/`）を公開し、**Lean v4.33.1** および **Mathlib v4.33.1** 環境で完了した再現可能な検証結果を記録した。[5]

| 検証基準 | 監査結果（2026年11月22日時点） |
| --- | --- |
| **1. コンパイルと再現性** | ネットワークを遮断した読み取り専用の隔離サンドボックス環境で、全 **175,187モジュール**がエラー0件でコンパイルされ（`lake build Main`）、厳密に **61,570,595,788バイト**（61.57 GB）の生証明エクスポート（`sha256: 5ea74b91...244e`）が再現された。[4][5] |
| **2. 公理および健全性の監査** | `#print axioms` により、主要5定理がLeanの3つの標準基礎公理（`propext`、`Classical.choice`、`Quot.sound`）の**み**に依存し、ユーザー定義公理が一切なく、Mathlibの `.olean` キャッシュ（8,322ファイル）もバイト単位で未改変であることが確認された。[5] |
| **3. 定理主張の厳密な一致確認** | 独立比較ツール（`con-leche --compare` およびそのRust移植版 `con-ron --compare` により、1,468,418件の解答宣言を51,692件の課題宣言と照合）によって、`Main.lean` がMathlibの厳密な `RiemannHypothesis` の定義（`∀ (s : ℂ) (_ : riemannZeta s = 0) (_ : ¬∃ n : ℕ, s = -2 * (n + 1)) (_ : s ≠ 1), s.re = 1 / 2`）および**すべてのディリクレL関数に対するGRH**（`LFunction_ne_zero_of_half_lt_re`、`LFunction_eq_zero_re`、`LFunction_eq_zero_re_of_isPrimitive`）を証明していることが確認された。[4][5] |
| **4. 複数カーネルによる証明検査** | 全モジュールが `leanchecker` と `lean4lean`（Lean内で検証済み）を通過し、61.57 GBの静的エクスポート全体がRust実装のカーネル **`nanoda`**（80スレッドで27分42秒）、および形式検証済みの集合論ベースチェッカー **`con-leche`**（64スレッドで3分15秒）と **`con-ron`**（64スレッドで7分06秒）によって独立に受理された。[4][5] |

さらに、Mathlibにおける $\zeta(s)$ の解析的定義から完全に独立した追加検証として、サザーランドはアルポゲの証明を**ロバンの不等式**（すべての $n > 5040$ に対して $\sigma(n) < e^{\gamma} n \log \log n$）および**ラガリアスの不等式**（すべての $n > 0$ に対して $\sigma(n) \le H_n + e^{H_n} \log H_n$）の独立な形式化と結合し、これら2つの約数和不等式の無条件かつ初等的な証明を導出した。[5]

## 同日公開の人間単独プレプリントと数学界への影響

アルポゲの公開と同日（**2026年11月20日**）、スタンフォード大学の数学者**ラヴィ・ヴァキル**（Ravi Vakil）は、AIを用いずに12年間この問題に取り組み、スタンフォード大学のブライアン・コンラッド教授と草稿を検討していたイタリアの数学者**アレッサンドロ・マリア・マスッロ**（Alessandro Maria Masullo）による、人間単独執筆の一般化リーマン予想証明の草稿を別途公開した。[6][8][9] アルポゲの発表によって改訂のためにさらに1年待つことが現実的でなくなったため、ヴァキルは改訂途中のマスッロの草稿を共有したが、公開から8時間以内にヴァキルは投稿を更新し、複数の数学者（AI検証ツールの支援を受けた）がマスッロの草稿に未解決の論理的間隙を指摘したことを報告した。[6]

対照的に、アルポゲの1,700万行に及ぶLean証明が複数カーネルによる形式検証を通過したことで、数学界の焦点はリーマン予想およびディリクレGRHの真偽を議論する段階から、機械検証済みの保型リフティング証明から人間が理解可能な概念的簡略化を抽出する作業へと移行した。[3][4][9] なお、2026年11月22日時点で検証済みの形式化範囲は、古典的なリーマンゼータ関数 $\zeta(s)$ およびすべての法と指標に対する**ディリクレ $L$ 関数**に限られており、デデキントゼータ関数、一般のヘッケ $L$ 関数、および任意の高階保型 $L$ 関数は `Main.lean` で検証された形式定理の主張には含まれていない。[5]

## よくある質問

### リーマン予想は証明され、検証されましたか？

はい。2026年11月20日、数学者レヴェント・アルポゲ（AnthropicのClaude AIと協働）は、定理証明支援系Lean 4においてリーマン予想およびディリクレL関数に対する一般化リーマン予想を証明した1,700万行の形式証明を公開しました。2026年11月21〜22日には、Lean Focused Research Organization（FRO）、Mathlibイニシアティブ、およびMITの数学者アンドリュー・サザーランドが、この証明がエラーなくコンパイルされ、標準公理のみを使用し、Mathlibの公式な定理主張と一致し、複数の独立した証明カーネルを通過することを認定しました。 [3][4][5]

### リーマン予想は何を主張していますか？

1859年にベルンハルト・リーマンが提唱したリーマン予想は、リーマンゼータ関数 ζ(s) のすべての非自明な零点（すなわち、負の偶数 -2, -4, -6 などを除く ζ(s) = 0 のすべての解）が、実部が厳密に 1/2 に等しい複素数であると主張するものです。 [1][5]

### レヴェント・アルポゲとClaudeはどのような数学的手法でリーマン予想を証明しましたか？

この証明では、関数体におけるステパノフの重複度論法を整数へ適用するため、符号定値二次形式のパーセバル恒等式とギナン・ヴェイユの明示公式を、完全定値ユニタリ群にわたる長さ sqrt(X) に比例する反復テータリフトの連鎖と組み合わせています。さらに、チョウラ・セルバーグ公式、ジーゲルの質量公式、ラリスのシーソー恒等式、ボストの傾き不等式、および岩澤塔の構成を用いて各項を制御しています。 [3][9]

### 1,700万行に及ぶAI支援証明に隠れた誤りや不正がないことはどのように検証されましたか？

4段階のLean検証プロトコルに従い、監査担当者はオフラインのサンドボックス環境で全175,187モジュールを再構築して61.57 GBの静的証明エクスポートを生成し、Leanの3つの標準公理（propext、Classical.choice、Quot.sound）のみが使用されていることを確認しました。さらに、証明された定理が未改変のMathlibにおけるRiemannHypothesisの定義と一致することを照合し、異なる言語で書かれた独立の証明チェッカー（nanoda、con-leche、con-ron、lean4leanなど）で生エクスポートを検証したほか、ロバンおよびラガリアスの初等的な約数和不等式も導出しました。 [4][5][7]

### 2026年11月に別途公開されたアレッサンドロ・マスッロの人間単独による証明の試みはどうなりましたか？

2026年11月20日、スタンフォード大学のラヴィ・ヴァキル教授が、アレッサンドロ・マリア・マスッロによる非AIのGRH証明の改訂途中草稿を公開しました。しかし、公開から8時間以内にAI解析ツールを用いた数学者らによって草稿中の未解決の論理的間隙が指摘されました。一方、アルポゲのLean 4形式証明は完全なカーネル認定を通過しています。 [4][6][9]

## 引用できる文

- 1859年にベルンハルト・リーマンが提唱し、2000年にクレイ数学研究所の賞金100万ドルのミレニアム懸賞問題に指定されたリーマン予想は、リーマンゼータ関数のすべての非自明な零点の実部が 1/2 であると主張する。 [1][2]
- 2026年11月20日、レヴェント・アルポゲはAnthropicのClaude AIと共同で開発した、リーマン予想およびディリクレL関数に対する一般化リーマン予想を証明する1,700万行（175,187モジュール）のLean 4形式化を公開した。 [3][4][5]
- 2026年11月21日、Lean FROとMathlibイニシアティブは、アルポゲのリーマン予想の証明が正当であり、Mathlibに対してエラーなくコンパイルされ、Mathlibの厳密な主張を証明しており、con-lecheやcon-ronを含む独立した証明チェッカーを通過することを認定した。 [4]
- MITの数学者アンドリュー・サザーランドは、アルポゲの175,187個のLean v4.33.1モジュールが3つの標準公理（propext、Classical.choice、Quot.sound）のみを用いて61,570,595,788バイトのエクスポートを再現し、nanoda、con-leche、con-ron、leanchecker、lean4leanに受理され、ロバンおよびラガリアスの約数和不等式を無条件に含意することを検証した。 [5]
- 2026年11月20日にラヴィ・ヴァキルによって別途公開されたアレッサンドロ・マリア・マスッロによる非AIのGRH草稿には、公開から8時間以内に査読者によって数学的問題が指摘された。 [6][9]

## 年表

- 1859-11: ベルンハルト・リーマンが論文『与えられた数より小さい素数の個数について』を発表し、リーマン予想を提唱した。 [1]
- 1900-08-09: ダフィット・ヒルベルトがパリの国際数学者会議での講演において、リーマン予想を第8問題として含めた。 [2]
- 2000-05-24: クレイ数学研究所がパリでリーマン予想を賞金100万ドルの7つのミレニアム懸賞問題の1つに指定した。 [1][2]
- 2026-10-06: レヴェント・アルポゲがステパノフ行列式とボストの傾き不等式を出発点として、AnthropicのClaude AIとの6週間の形式化・証明探索スプリントを開始した。 [3]
- 2026-11-16: アルポゲとClaudeが、長さ sqrt(X) の反復テータリフトを用いてディリクレL関数に対する一般化リーマン予想のLean 4形式化を完了した。 [3]
- 2026-11-20: アルポゲがremark.pdfおよび1,700万行のLean 4証明アーカイブを一般公開した。同日、ラヴィ・ヴァキルが別途公開したアレッサンドロ・マスッロの人間執筆草稿では、8時間以内に論理的間隙が発見された。 [3][6][9]
- 2026-11-21: Lean FRO、Mathlibイニシアティブ、およびアンドリュー・サザーランド（MIT）が、複数の独立した証明カーネルにわたりアルポゲのLean 4証明の正当性を独立に認定した。 [4][5][8]

## 出典

1. Riemann Hypothesis - Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium/riemann-hypothesis/ (閲覧 2026-11-23; tier 2: academic or news)
2. The Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium-problems/ (閲覧 2026-11-23; tier 2: academic or news)
3. Remark on a Proof and Lean Formalization of the Riemann Hypothesis and Generalized Riemann Hypothesis. Levent Alpoge (alpo.ge). 公開 2026-11-20. https://alpo.ge/remark.pdf (閲覧 2026-11-23; tier 3: official site)
4. Lean Verification of the Riemann Hypothesis: Joint Statement by the Lean FRO and the Mathlib Initiative. Lean Focused Research Organization & Mathlib Initiative. 公開 2026-11-21. https://leanprover-community.github.io/blog/posts/riemann-hypothesis/ (閲覧 2026-11-23; tier 3: official site)
5. RH Lean Proof: Verification Files and Independent Kernel Audit. Andrew Sutherland (Massachusetts Institute of Technology). 公開 2026-11-22. https://math.mit.edu/~drew/grh/ (閲覧 2026-11-23; tier 2: academic or news)
6. Hurried Announcement: Alessandro Masullo GRH (with Nov 20-22 Updates). Ravi Vakil (Stanford University / Math 216 Blog). 公開 2026-11-20. https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/ (閲覧 2026-11-23; tier 2: academic or news)
7. '...and the proof is checked in Lean' (Four Criteria for Verifying AI-Generated Lean Proofs). Kevin Buzzard (Xena Project). 公開 2026-11-12. https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/ (閲覧 2026-11-23; tier 2: academic or news)
8. Two groups verify mathematician's claim that Claude helped prove mathematics problem. The Guardian. 公開 2026-11-21. https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai (閲覧 2026-11-23; tier 2: academic or news)
9. AI claimed a solution to the 167-year-old Riemann hypothesis - and a human did, too. TechCrunch. 公開 2026-11-20. https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/ (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "リーマン予想." 版 f759e2c2, 2026-11-23. https://mimirwiki.com/ja/wiki/riemann-hypothesis
