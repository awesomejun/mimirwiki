---
title: "Lean（定理証明支援系）"
subtitle: "オープンソースの関数型プログラミング言語および対話型定理証明支援系（Lean 4）"
canonical_url: https://mimirwiki.com/ja/wiki/lean-theorem-prover
language: ja
page_class: entity
revision_sha256: c2f5a58ef8313fe8c536317326ec1c257d56e2116383dd5e29419151a90629a5
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/lean-theorem-prover.md
  txt: https://mimirwiki.com/ja/wiki/lean-theorem-prover.txt
  json: https://mimirwiki.com/ja/wiki/lean-theorem-prover.json
  jsonld: https://mimirwiki.com/ja/wiki/lean-theorem-prover.jsonld
translations:
  en: https://mimirwiki.com/wiki/lean-theorem-prover
  ko: https://mimirwiki.com/ko/wiki/lean-theorem-prover
  zh: https://mimirwiki.com/zh/wiki/lean-theorem-prover
  es: https://mimirwiki.com/es/wiki/lean-theorem-prover
---

# Lean（定理証明支援系）

> Lean（Lean 4）は、Apache-2.0ライセンスの下で公開され、Lean Focused Research Organizationが開発を支援するオープンソースのプログラミング言語かつ定理証明支援系である。2026-11-24時点の最新安定版はv4.36.0（2026-11-16）、リリース候補版はv4.37.0-rc1（2026-11-18）であり、2026-11-23にはGoogle DeepMindがLean 4による量子プログラム検証ライブラリ、仕様、および証明をオープンソース化した。

Leanは、形式検証された数学的証明およびソフトウェアを記述するために設計された、オープンソースのプログラミング言語かつ対話型定理証明支援系である。そのリポジトリはApache-2.0ライセンスの下で公開されており、開発はLean Focused Research Organizationによって支援されている。Lean 4は2023-09-08に初の公式リリース（v4.0.0）を迎えた。2026-11-24時点の最新安定版はLean 4.36.0（2026-11-16公開）であり、2026-11-18にはプレリリースのリリース候補版としてLean 4.37.0-rc1が公開された。これに続き、2026-11-19には対応するMathlibのプレリリースが公開され、2026-11-23にはGoogle DeepMindがLean 4による量子プログラム検証資料を一般公開した。

**別名:** Lean 4, Lean定理証明器, Leanプログラミング言語

## 主要な事実

- **最新安定版:** v4.36.0（2026-11-16） (時点 2026-11-24) [5]
- **現在のリリース候補版:** v4.37.0-rc1（2026-11-18、プレリリース） (時点 2026-11-24) [6]
- **Lean 4初の公式リリース:** v4.0.0（2023-09-08） [4]
- **ライセンス:** Apache-2.0 [3]

## ファクトシート

- **種別:** プログラミング言語および対話型定理証明支援系 [1]
- **支援組織:** Lean Focused Research Organization（Lean FRO） [2]
- **ライセンス:** Apache-2.0 [3]
- **Lean 4初の公式リリース:** v4.0.0（2023-09-08） [4]
- **最新安定版:** v4.36.0（2026-11-16） (時点 2026-11-24) [5]
- **最新プレリリース:** v4.37.0-rc1（2026-11-18） (時点 2026-11-24) [6]
- **主要数学ライブラリ:** Mathlib（mathlib4） [4]
- **ソースリポジトリ:** github.com/leanprover/lean4 [3]
- **公式ウェブサイト:** lean-lang.org [1]

## Leanの概要と支援組織

Leanは、ユーザーが形式的な数学的証明や検証済みソフトウェアを記述できるオープンソースのプログラミング言語かつ定理証明支援系である。[1][3] Lean 4のリポジトリはApache-2.0ライセンスの下で公開されており、Lean Focused Research Organization（Lean FRO）がLeanの発展を支援していると明言している。[2][3]

Lean FROは、Leanの重要システムと機能の高度化を掲げており、注力分野としてスケーラビリティ、ユーザビリティ、証明自動化、ドキュメント整備、多様なコミュニティ、ならびにAI研究および検証済みコード合成の支援を挙げている。[2] Lean公式サイトで紹介されている組み込み自動化の例には、帰納法、代数推論、SMTに類する推論を行う`grind`タクティクや、ビットベクトル等式を決定する`bv_decide`が含まれる。[1] Lean 4.0.0のリリースノートではMathlibがLeanの主要数学ライブラリ（`mathlib4`）として説明されており、プロジェクトはビルドツール`lake`およびツールチェーン管理ツール`elan`を用いて管理される。[4][9]

## Lean 4のリリース履歴と2026年11月のバージョン

Lean 4は2023-09-08に初の公式リリースとなる`v4.0.0`を公開し、当時、開発チームは約1か月ごとにマイナーリリースを行う計画を発表した。[4]

| バージョン | 種別 | 公開日 | 備考 |
| --- | --- | --- | --- |
| v4.0.0 | 安定版 | 2023-09-08 | Lean 4初の公式リリース |
| v4.36.0 | 安定版（2026-11-24時点の最新） | 2026-11-16 | GitHub上の最新安定版リリースタグ |
| v4.37.0-rc1 | リリース候補版（プレリリース） | 2026-11-18 | 370件の変更を反映、正式版前に変更される可能性あり |

2026-11-24時点で、`v4.36.0`（2026-11-16公開）がLean 4の最新安定版である。[5] 2026-11-18には、プロジェクトが正式版ではなくリリース候補版であることを明示した上で`v4.37.0-rc1`を公開した。[6] そのリリースノートには、機能追加71件、修正159件、性能改善108件、リファクタリング7件、テストスイート改善4件、ドキュメント改善1件、その他の変更20件からなる計370件の変更が記録されており、その中にはオプション`shiftLeft.threshold`（デフォルト値65536）の追加が含まれる。[6] 2026-11-19には、`leanprover-community/mathlib4`がツールチェーンを同リリース候補版へ引き上げるため、プレリリース`v4.37.0-rc1`にタグを付けた。[7]

## 形式検証におけるLeanと2026年11月のDeepMindによる公開

Lean FROは、Leanが活用される分野として形式数学ならびにソフトウェア・ハードウェア検証を挙げている。[1][2] 2026-11-23、Google DeepMindは、[Google Gemini](https://mimirwiki.com/ja/wiki/google-gemini)（Gemini 4）エージェントチームによって合成され、Lean 4で検証された量子プログラムに関する検証資料をGitHubで一般公開すると発表した。[8][9]

オープンソース化されたリポジトリ（`google-deepmind/formal-quantum-computation`、Apache-2.0ライセンス）は古典変数を伴う量子ホーア論理に基づいており、`Mathlib4`および`QuantumInfo`（`Physlib`の一部）に依存している。[9] 同リポジトリは、コアとなる`QuantumComputation`ライブラリ（回路、ゲート、レジスタ、量子ホーア論理、およびリソース計算）、`QuantumComputationSpecs`（形式的な問題仕様およびベンチマーク課題）、そして報告されたプログラムとLean証明を収めた`discoveries`ブランチの3つに分かれている。[9][12]

基礎となる研究プレプリント（`arXiv:2611.09822v3`）は2026-11-06に初回投稿され、2026-11-16に改訂された。2026-11-23のニュースは、Leanライブラリ、仕様、および証明の一般公開であり、同日にThe Next WebおよびQubitWireが報じた。[8][10][11][12] DeepMindとQubitWireはいずれも、報告されたリソース削減（量子ビット数と演算数を組み合わせたコスト指標における11.8倍の削減や、慣性閉じ込め核融合計算における誤り訂正済み量子ビット数の5,650から4,338への削減など）は、物理的な量子ハードウェア上で実測されたものではなく、形式仕様とコストモデルに対して数学的に検証されたものであると指摘しており、リポジトリは古典計算と制御フローの明示的なコスト評価を今後の予定課題として挙げている。[8][9][12]

## Leanによる検証の範囲と限界

DeepMindのリポジトリ公開に関する独立報道で指摘されているように、機械検証されたLeanの証明は、モデル化されたコスト仮定の下でプログラムが形式仕様を満たすことを確認するものであり、その仕様やコストモデルが物理ハードウェアのあらゆるボトルネックと一致すること、あるいは外部の第三者が結果を独立に再現したことを単独で立証するものではない。[12]

## よくある質問

### 2026-11-24時点でのLean 4の最新安定版は何ですか？

2026-11-24時点でのLean 4の最新安定版は、2026-11-16に公開されたv4.36.0です。2026-11-18に公開されたLean 4.37.0-rc1は、正式版ではなくリリース候補版（プレリリース）です。 [5][6]

### LeanエコシステムにおけるMathlibとは何ですか？

Mathlib（mathlib4）はLeanの主要な数学ライブラリです。2026-11-19には、Lean 4.37.0-rc1に合わせてツールチェーンを更新したv4.37.0-rc1のプレリリースがMathlibリポジトリで公開されました。 [4][7]

### Google DeepMindは2026-11-23にLeanに関して何を公開しましたか？

Google DeepMindは2026-11-23に、2026年11月のプレプリントに由来するLean 4量子プログラムライブラリ、形式的な問題仕様、およびLean証明を収めたApache-2.0ライセンスのGitHubリポジトリ「formal-quantum-computation」の一般公開を発表しました。 [8][9][10]

### DeepMindによるLean関連の公開は、物理的な量子コンピュータ上での実行を実証したものですか？

いいえ。2026-11-23の発表はLean検証資料の一般公開であり、報告されたリソース改善は物理的な量子ハードウェアでの実測時間ではなく、形式仕様と数学的コストモデルに基づくものです。 [8][12]

## 引用できる文

- LeanはApache-2.0ライセンスの下で公開され、Lean Focused Research Organizationによって支援されているオープンソースのプログラミング言語かつ定理証明支援系である。 [1][2][3]
- Lean 4初の公式リリースであるLean 4.0.0は、2023-09-08に公開された。 [4]
- 2026-11-24時点で、Lean v4.36.0（2026-11-16公開）がGitHub上の最新安定版リリースである。 [5]
- Lean 4.37.0-rc1は370件の変更を含むリリース候補版として2026-11-18に公開され、Mathlibは2026-11-19に対応するv4.37.0-rc1のプレリリースを公開した。 [6][7]
- 2026-11-23、Google DeepMindはLean 4による量子プログラム検証ライブラリ、問題仕様、および検証済み解をgoogle-deepmind/formal-quantum-computationとしてオープンソース化した。 [8][9]
- 関連するプレプリントarXiv:2611.09822v3は2026-11-06に投稿され2026-11-16に改訂されたものであり、報告された回路コストの数値は物理的な量子ハードウェアでの実行ではなく形式モデルから導出されている。 [10][12]

## 年表

- 2023-09-08: Lean 4初の公式リリースとしてLean 4.0.0が公開された。 [4]
- 2026-11-06: Gemini 4エージェントを用いてLean上で形式検証された量子プログラムを発見するプレプリントarXiv:2611.09822が投稿された（2026-11-16にv3へ改訂）。 [10]
- 2026-11-16: Lean v4.36.0が安定版リリースとしてGitHubで公開された。 [5]
- 2026-11-18: 370件の変更を含むリリース候補版としてLean 4.37.0-rc1が公開された。 [6]
- 2026-11-19: Mathlib（mathlib4）がツールチェーンをLean 4.37.0-rc1に更新したプレリリースv4.37.0-rc1を公開した。 [7]
- 2026-11-23: Google DeepMindがLean 4による量子プログラム検証ライブラリ、問題仕様、および検証済み解のGitHub上での一般公開を発表した。 [8][9]

## 出典

1. Lean Programming Language. Lean Focused Research Organization. https://lean-lang.org/ (閲覧 2026-11-24; tier 3: official site)
2. Lean Focused Research Organization. Lean Focused Research Organization. https://lean-fro.org/ (閲覧 2026-11-24; tier 3: official site)
3. leanprover/lean4: Lean 4 programming language and theorem prover. Lean Focused Research Organization. https://github.com/leanprover/lean4 (閲覧 2026-11-24; tier 3: official site)
4. Release v4.0.0 - leanprover/lean4. Lean Focused Research Organization. 公開 2023-09-08. https://github.com/leanprover/lean4/releases/tag/v4.0.0 (閲覧 2026-11-24; tier 3: official site)
5. Release v4.36.0 - leanprover/lean4. Lean Focused Research Organization. 公開 2026-11-16. https://github.com/leanprover/lean4/releases/tag/v4.36.0 (閲覧 2026-11-24; tier 3: official site)
6. Lean 4.37.0-rc1 (2026-11-18). Lean Focused Research Organization. 公開 2026-11-18. https://lean-lang.org/doc/reference/latest/releases/v4.37.0/ (閲覧 2026-11-24; tier 3: official site)
7. Release v4.37.0-rc1 - leanprover-community/mathlib4. Lean Community. 公開 2026-11-19. https://github.com/leanprover-community/mathlib4/releases/tag/v4.37.0-rc1 (閲覧 2026-11-24; tier 3: official site)
8. Finding faster quantum algorithms with agents and formal verification. Google DeepMind. 公開 2026-11-23. https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/ (閲覧 2026-11-24; tier 3: official site)
9. google-deepmind/formal-quantum-computation. Google DeepMind. https://github.com/google-deepmind/formal-quantum-computation (閲覧 2026-11-24; tier 3: official site)
10. Discovering formally verified quantum programs with AI. arXiv. 公開 2026-11-16. https://arxiv.org/abs/2611.09822v3 (閲覧 2026-11-24; tier 2: academic or news)
11. DeepMind's AI agents found cheaper quantum algorithms, and proved them. The Next Web. 公開 2026-11-23. https://thenextweb.com/news/google-deepmind-gemini-agents-quantum-algorithms-lean (閲覧 2026-11-24; tier 2: academic or news)
12. Google opens the proofs behind its AI-designed quantum programs. QubitWire. 公開 2026-11-23. https://qubitwire.com/articles/google-deepmind-quantum-program-proofs-public-release (閲覧 2026-11-24; tier 2: academic or news)

## このページを引用する

Mimirwiki. "Lean（定理証明支援系）." 版 c2f5a58e, 2026-11-24. https://mimirwiki.com/ja/wiki/lean-theorem-prover
