---
title: "Inkling 2 Mini"
subtitle: "Thinking Machines LabがローカルノートPCおよびワークステーション推論向けに設計したオープンウェイトのループ型Mixture-of-Expertsビジョン言語モデル"
canonical_url: https://mimirwiki.com/ja/wiki/inkling-2-mini
language: ja
page_class: entity
revision_sha256: 2a531773b95a835444abd8d0fe4d59ea23bed8758d8be0ca35ed469d2e386acc
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/ja/wiki/inkling-2-mini.md
  txt: https://mimirwiki.com/ja/wiki/inkling-2-mini.txt
  json: https://mimirwiki.com/ja/wiki/inkling-2-mini.json
  jsonld: https://mimirwiki.com/ja/wiki/inkling-2-mini.jsonld
translations:
  en: https://mimirwiki.com/wiki/inkling-2-mini
  ko: https://mimirwiki.com/ko/wiki/inkling-2-mini
  zh: https://mimirwiki.com/zh/wiki/inkling-2-mini
  es: https://mimirwiki.com/es/wiki/inkling-2-mini
---

# Inkling 2 Mini

> 2026年11月20日にApache 2.0ライセンスで公開されたInkling 2 Mini（`thinkingmachines/Inkling-2-Mini`）は、100万トークンのコンテキストウィンドウを備える26.4Bパラメータのループ型Mixture-of-Expertsビジョン言語モデルである。中間12層をトークンあたり3回循環実行（論理48層訪問、固有アクティブパラメータ3.4B、実効活性化5.4B）し、4ビットNVFP4および8ビットMXFP8でネイティブ学習（約20 GB）されているため、一般向けノートPCでオフライン動作しつつ、DeepSWE v1.1で48.2%、SWE-bench Verifiedで79.2%、Artificial Analysis Intelligence Index v5.0で20.1を記録した。

Inkling 2 Miniは、元OpenAI最高技術責任者（CTO）のミラ・ムラティ（Mira Murati）が率いるAI研究企業Thinking Machines Labが2026年11月20日に公開したオープンウェイトのビジョン言語モデルである。総パラメータ数264億（26.4B）の24層ループ型Mixture-of-Experts（MoE）Transformerアーキテクチャを採用し、中間12層をトークンごとに3回反復実行することで、34億（3.4B）の固有アクティブパラメータから実質48層分の処理とトークンあたり54億（5.4B）の実効重み活性化を実現しており、Apache 2.0ライセンスの下で約20 GBの混合精度（NVFP4/MXFP8）フットプリントでローカル動作する。

**別名:** Inkling 2 Mini, Thinking Machines Lab, ループ型Transformer, Mixture-of-Experts, オープンウェイトAI, ローカルLLM

## 主要な事実

- **公開日およびライセンス:** 2026年11月20日、Apache 2.0（Acceptable Use Policy付属） [1]
- **アーキテクチャ:** 24層ループ型MoE（48層訪問、128個中8個のSwiGLUエキスパートをルーティング） [2]
- **パラメータ数:** 総計26.4B、固有アクティブ3.4B、トークンあたり実効活性化5.4B [1]
- **ネイティブ精度および容量:** NVFP4（先頭20層）+ MXFP8（末尾4層）、約20 GBチェックポイント（4ビットGGUFは17.5 GB） [3]
- **主要ベンチマーク結果:** DeepSWE v1.1 48.2%、SWE-bench Verified 79.2%、SWE-bench Pro v2 Hard 77.9%、AAv5 20.1 [1]

## ファクトシート

- **開発元:** Thinking Machines Lab [1]
- **公開日:** 2026年11月20日 [1]
- **モデルID:** thinkingmachines/Inkling-2-Mini [2]
- **研究用コンパニオンモデル:** thinkingmachines/TML-d24-varloop-research（可変1〜5回ループパス） [2]
- **アーキテクチャ:** ループ型スパースMixture-of-Experts Transformer（物理24層 / 論理48層） [2]
- **パラメータ数:** 総計26.4B / 固有アクティブ3.4B / トークンあたり実効重み活性化5.4B [1]
- **コンテキストウィンドウ:** 1,000,000トークン [5]
- **モダリティ:** テキスト・画像入力、テキスト出力 [5]
- **数値精度:** ネイティブNVFP4（層0〜19）およびMXFP8（層20〜23） [1]
- **メモリ要件:** ネイティブチェックポイント約20 GB（32 GB RAM/VRAM推奨、4ビットGGUFは17〜18 GB） [5]
- **ファーストパーティAPI料金:** 入力$0.15 / 100万トークン、出力$0.50 / 100万トークン、キャッシュヒット$0.015 / 100万トークン（Tinker上） [4]
- **ライセンス:** Apache 2.0（Model Acceptable Use Policyを併設） [5]

## Inkling 2 Miniの概要とループ型Mixture-of-Expertsアーキテクチャ

元OpenAI最高技術責任者（CTO）のミラ・ムラティ（Mira Murati）が設立し率いるサンフランシスコのAI研究企業Thinking Machines Labは、2026年11月20日にローカルノートPC、デスクトップワークステーション、および自律型コーディングエージェント向けに最適化されたオープンウェイトのビジョン言語モデルとしてInkling 2 Miniを公開した。[1][3] Thinking Machinesの主力予測スケーリングラダーから派生し、より大規模なInkling 2 Smallモデルの下位に位置づけられるInkling 2 Miniは、Apache 2.0ライセンス（Model Acceptable Use Policyを併設）の下で提供され、100万トークンのコンテキストウィンドウにわたりテキストおよび画像のマルチモーダル入力に対応する。[1][2][5]

Inkling 2 Miniは、長い外部化された思考の連鎖（Chain-of-Thought: CoT）テキストやパラメータ数の拡大のみに依存するのではなく、ループ型Mixture-of-Experts（MoE）Transformer設計を導入している。[1][2][3] テキストデコーダは隠れ次元2,304（Inkling 2 Smallの4,608の半分）、エキスパート中間幅1,152の24の物理層を保持し、各層訪問時にトークンを128個のSwiGLUエキスパートのうち8個へルーティングする（Inkling 2 Smallでは384個中8個）。[2] 24の物理層は6層ずつ4つのブロックに編成され、トークンあたり計48回の論理層訪問を実行する。[1][2]

- **プレリュードブロック（層0〜5）**: 埋め込みを内部表現へ射影するため、トークンあたり1回実行される。[1][2]
- **ループコアブロック（層6〜17）**: 中間の6層ブロック2つが、格納された同一の重みを共有しながらトークンあたり3回連続で実行される（`6 + 3 * 12 + 6 = 48`回の層適用）。[1][2] 28の評価項目にわたる社内スケーリング研究において、中間12層をループする方式は末尾12層をループする方式を27タスクで上回り、学習ステップ2,000時点で1.51倍〜1.91倍の計算量換算ロス改善をもたらした（512Kトークンのエージェントトレースにおいて、非ループ型ベースラインが同等のロスに到達するには140%多くの推論計算量を要した）。[1][3]
- **最終ブロック（層18〜23）**: 洗練された内部表現をデコードするため、トークンあたり1回実行される。[1][2]

各6層ブロックは、5層のスライディングウィンドウアテンション層（ローカルウィンドウ幅1,024トークン）と、動的なキーおよびバリューのショート畳み込み（short convolution）、24個のクエリヘッド、8個のキー・バリューヘッド、学習済み相対位置ロジット、学習済みアテンションシンク、および出力ゲートを備えた1層のフルアテンション層で構成される。[2] 層6〜17を通過する3回のパスはすべて同一のパラメータ重みを再利用する一方、48回の訪問それぞれが固有のKVキャッシュとショート畳み込み状態を個別に保持する。[2] 反復間で情報を伝達するため、Inkling 2 Miniはアテンション残差（Kimi Teamの2026年のアテンション残差定式化に基づく）を実装している。ループコアの各パスはプレリュードブロックの出力から開始され、2回目と3回目のパスでは学習済みクエリと4つのランク64ゲーティングコントローラを介して前パスの2つの残差ブロック（「クロスパス・メッセージ」）にもアテンションを向け、前パスのメッセージをクエリ、キー、バリュー、およびMoE入力へ混合する。[1][2]

総計としてInkling 2 Miniは264億の物理パラメータを含み、単一パスで34億の固有パラメータを活性化し（テキストトークンあたり31億の固有重み）、3回のループパス全体でトークンあたり54億の実効重み活性化を適用する。[1][4][5]

## エキスパート枝刈り、蒸留ヒーリング、およびネイティブNVFP4学習

フロンティア級の推論アーキテクチャを一般向けノートPCのメモリに収まる約20 GBのフットプリントへ圧縮するため、Thinking Machinesは学習途中のエキスパート枝刈りとネイティブ低ビット精度学習を組み込む形で主力学習パイプラインを改変した。[1][3]

1. **3分の2のエキスパート枝刈りと蒸留ヒーリング**: 層あたり384個のエキスパートを持つより広幅な主力チェックポイントから出発し、Thinking Machinesはエキスパートの3分の2を枝刈りして層あたり128個へ削減した。[1][2][3] 枝刈り後のネットワークは、より大規模な社内Inklingモデルから1兆トークンを蒸留することで「ヒーリング（修復）」され、続いて教師ありファインチューニング（SFT）と2.2兆トークンの強化学習（RL）が行われた。[3] 2. **ネイティブNVFP4およびMXFP8精度**: エージェント型コーディング精度を劣化させうる学習後量子化に依存する代わりに、Thinking Machinesは先頭20物理層を4ビットNVFP4精度で、末尾4層を8ビットMXFP8精度でネイティブに学習およびデプロイした。[1][3] 配布される重みが学習時の数値形式と一致するため、アップストリームの混合精度チェックポイントは学習後量子化に伴う劣化なしに約20 GBのメモリで収まる。[3][5] 3. **数値設定可能な推論労力（Reasoning Effort）**: モデルのチャットテンプレートは、名称付きティアまたは`0.0`から`0.99`の連続浮動小数点数として指定できる`reasoning_effort`パラメータを受け付け、システムメッセージとしてプロンプトに注入する。対応するティアは`none`（`0.0`）、`minimal`（`0.1`）、`low`（`0.2`）、`medium`（`0.7`）、`high`（`0.9`、デフォルト）、`xhigh`（`0.99`）、および`max`（`0.99`）である。[2] 最小設定であっても、内部推論が完全に無効化されるわけではない。[5]

## Inkling 2 Miniのベンチマーク性能とエネルギー効率

100B未満のオープンウェイトモデル（Alibabaの密モデルQwen3.8-27B、Google DeepMindのGemma 4 31B、MetaのMuse Glimmer、およびNVIDIAの124.5BモデルNemotron 3.5 Super VLを含む）を比較した48の標準ベンチマークにおいて、Inkling 2 Miniは32の評価項目で1位を獲得した。[1][2] Artificial Analysis Intelligence Index v5.0（AAv5）では20.1を記録して密モデルのQwen3.8-27Bと1位タイとなった一方、アクティブパラメータ数は約5分の1、総計算量（アクティブパラメータ数×トークン数）は2.8分の1、タスクあたりの実時間（ウォールクロック時間）は4分の1（9.0分対38.2分）、タスクあたりコストは6分の1（Thinking MachinesのファーストパーティTinker API料金である入力$0.15/1M、出力$0.50/1M、キャッシュヒット$0.015/1M換算で$0.59対$3.53）に抑えている。[1][3][4]

| ベンチマーク | カテゴリ | Inkling 2 Mini (実効5.4B / 26.4B) | Qwen3.8-27B (27B 密モデル) | Gemma 4 31B (30.7B 密モデル) | Muse Glimmer (30B 密モデル) | Nemotron 3.5 Super VL (12B / 124.5B) |
| --- | --- | --- | --- | --- | --- | --- |
| AA Intelligence Index v5.0 | 総合知能 | 20.1（1位タイ） | 20.1（1位タイ） | 4.4 | 6.3 | 13.6 |
| Vals Index v2.2 | 総合エンタープライズ / コーディング | 46.5% | - | - | - | 29.8% |
| DeepSWE v1.1 | エージェント型ソフトウェア工学 | 48.2% | 42.2% | 0.3% | 4.4% | 24.7% |
| SWE-bench Pro v2 (Hard) | 高難度ソフトウェア工学（51タスク） | 77.9% | 73.8% | 14.2% | 44.3% | 44.1% |
| SWE-bench Verified | Bash専用ソフトウェア工学 | 79.2% | 77.8% | 46.1% | 76.0% | 71.1% |
| FrontierCode v2.0 | オープンソースPRマージ | 15.1% | 14.9% | 0.0% | 1.5% | 6.1% |
| Terminal Bench v4.0 | ターミナルエージェント実行 | 5.6%（1位タイ） | 5.6%（1位タイ） | 0.0% | 0.5% | 0.0% |
| BrowseComp | エージェント型Webブラウジング（圧縮あり） | 79.0% | 61.6% | 37.0% | 63.9% | 78.9% |
| DeepSearchQA | ディープサーチ質問応答 | 85.3% | 79.7% | 61.7% | 74.6% | 77.7% |
| MCP Atlas Public | Model Context Protocolツール利用 | 82.7% | 77.3% | 54.2% | 75.5% | 67.7% |
| OmniDocBench v1.6 | 文書ビジョン理解 | 92.8% | 91.5% | 82.5% | 90.4% | 77.9% |
| LongBench v2 | 長文コンテキスト推論 | 66.9% | 52.3% | 52.9% | 33.1% | 62.1% |
| AA-Omniscience v1.1 | パラメトリック事実性 / 非ハルシネーション | -8.6 (63.4%) | -6.4 (71.4%) | -48.5 (14.5%) | -32.2 (16.4%) | -2.9 (69.5%) |

スタンフォード大学のHazy Research LabおよびScaling Intelligence Labの研究者がNVIDIA DGX Spark（128 GB）上でIntelligence per Watt手法を用いて実施したエネルギー効率テストでは、Inkling 2 Mini（MXFP8精度、low推論労力で動作）は0.703 intelligence per jouleを達成し、Qwen3.6-35B-A3B（NVFP4で0.430）、Gemma-4-26B-A4B（NVFP4で0.159）、およびQwen3.5-27B（INT4で0.036）を上回った。[1][3]

ループ処理は格納パラメータ総数を増やさずにトークンあたりの逐次推論計算量を増やす仕組みであるため、パラメトリックな事実想起は総重み容量26.4Bによる制約を受ける。AA-Omniscience v1.1においてInkling 2 Miniはスコア-8.6、非ハルシネーション率63.4%にとどまり、検索ツールが無効化された状態では密モデルに後れを取っている。[1][3] また、マルチターン対話制約でもQwen3.8-27Bを下回り（MultiChallengeで50.0%、ComplexConstraints v1.1で33.4%）、長時間のデバッグセッション中に反復的な推論ループを示す場合がある。[1][5]

## 思考の連鎖の監視可能性と可変ループ研究

ループ型Transformerをめぐる中核的なAI安全性の課題は、潜在空間内で複数の反復パスを内部実行することでモデルが思考をテキストとして外部化せずに推論できるようになり、思考の連鎖（CoT）の監視可能性（monitorability）が低下するか否かである。[1][3] 体系的な監督研究を可能にするため、Thinking Machinesは中間12層を1回から5回の範囲で反復実行するよう学習させた研究用可変ループチェックポイント`thinkingmachines/TML-d24-varloop-research`（推論時に`text_config={"loop_num_passes": N}`で設定可能）を併せて公開し、機械的解釈可能性（mechanistic interpretability）研究のためにNational Deep Inference Fabric（NDIF）およびGoodfireと提携した。[1][2][3]

可変ループモデルを用いたThinking Machinesの監視可能性実験では、以下の結果が得られている。[1][3]

- **潜在No-CoTホライズンの拡張**: 可視的な思考の連鎖トークンの出力を制限した場合、モデルの実効タスク時間ホライズンは1ループパスの16秒から3ループパスの37秒へと2倍以上に拡大し、直列推論タスクにおける精度は10ループパス（学習時の最大深度の2倍）まで向上し続けた。[1][3]
- **CoT圧縮と可読性の両立**: ループ深度が増すにつれ、モデルの可視的な思考の連鎖トランスクリプトは50%以上短くなったが、人間および自動の監視者は残存するCoTトレースが引き続き可読かつ忠実であることを確認した。[1][3]
- **サボタージュおよび不正行動評価**: LinuxArena制御ベンチマークにおいて、反復ループパスを追加しても密かなエージェント型サボタージュの上昇傾向は生じなかった。[1][3] 社内安全性評価でも、Inkling 2 Miniは一般的不正行動（9.8%）、密かな不正行動（8.3%）、および破壊的行動（10.2%）のいずれにおいてもGemma 4 31B、Muse Glimmer、Qwen3.8-27B、およびNemotron 3.5 Super VLより低い発生率を記録し、FORTRESS（敵対的）で89.5%、StrongREJECTで97.8%を達成した。[1]

## ローカルデプロイ、ハードウェア要件、およびランタイムエコシステム

Inkling 2 Miniは、Thinking MachinesのTinkerプラットフォーム、Hugging Face `transformers`（`AutoModelForMultimodalLM`）、`llama.cpp`およびLlama App、LM Studio、Unsloth Desktop、Apple Silicon向けMLX、Ollama、EXO、さらにデータセンターGPU向けのSGLangを含むクラウドおよびローカルランタイムでの公開当日サポートとともにリリースされ、DSpark投機的デコーディング用ドラフターモデルも同時に提供された。[1][2][3][5][6] Thinking Machinesは、機内モードのApple M5 Pro MacBook Pro（48 GBユニファイドメモリ）上でモデルを完全オフライン動作させ、数分でプレイ可能な3Dフライトシミュレータを構築しつつ、「Thinkyville」タウンシミュレーション内で20体の永続的な自律型AI住民を同時稼働させるデモを公開した。[1][3]

| 量子化 / フォーマット | 概算ファイルサイズ | 最小RAM / VRAM | 備考およびランタイム互換性 |
| --- | --- | --- | --- |
| アップストリーム混合精度（NVFP4 + MXFP8） | 約20.0 GB | 32 GB推奨 | ネイティブ学習精度。32 GB以上のApple Silicon Macまたは32 GB以上のGPU VRAMに最適 |
| 8ビットGGUF（`UD-Q8_K_XL` / `Q8_0`） | 約24.0 GB | 24 GB | llama.cppおよびUnsloth向けのロスレス・フル精度相当 |
| 4ビットGGUF（`UD-Q4_K_XL` / `IQ4_NL`） | 17.5 - 17.6 GB | 17 - 18 GB | 推奨ローカルGGUF量子化。約18 GBのシステムメモリが必要 |
| 3ビット / 2ビット / 1ビット Dynamic GGUF | 9.0 - 15.0 GB | 9 - 15 GB | 16 GB一般向けノートPC向けのUnsloth Dynamic 3.0 GGUF |
| ビジョンプロジェクタ（`mmproj-F16.gguf`） | +639 MB | +0.7 GB | GGUFで画像および文書のマルチモーダル入力を扱う際に必要なアドオンプロジェクタ |

`llama.cpp`またはUnslothでのローカルGGUF実行における推奨サンプリングパラメータは、`temperature = 1.0`、`top_p = 1.0`、`top_k = 0`、`min_p = 0.0`であり、ループ層レイアウトおよびエキスパート単位のNVFP4スケールに対応したビルド（`ggml-org/Inkling-2-Mini-GGUF`や`unsloth/Inkling-2-Mini-GGUF`など）の使用が推奨されている。[2][6]

## よくある質問

### Inkling 2 Miniのループ型Transformerアーキテクチャはどのように機能しますか？

各トークンを24の物理層に1回だけ通過させる代わりに、Inkling 2 Miniはデコーダを6層ずつ4つのブロックに分割します。最初のブロック（層0〜5）は1回実行され、中間の2ブロック（層6〜17）は格納された同一の重みを再利用してループで3回実行され、最終ブロック（層18〜23）が1回実行されます。ゲート付きアテンション残差メッセージが反復間で中間情報を伝達することで、保持するのは24層分（総パラメータ264億、固有アクティブパラメータ34億）のみでありながら、トークンあたり48回の層適用と54億の実効重み活性化を実現します。 [2]

### Inkling 2 Miniをローカルで実行するにはどのようなハードウェアが必要ですか？

アップストリームの混合精度チェックポイント（4ビットNVFP4および8ビットMXFP8でネイティブ学習済み）は約20 GBであり、Thinking Machines LabはApple Silicon Macで32 GB以上のユニファイドメモリ、または32 GB以上のGPU VRAMを推奨しています。LM Studio、llama.cpp、Unsloth Desktopで4ビットGGUF量子化モデル（UD-Q4_K_XLやIQ4_NLなど、約17.5〜17.6 GB）を使用すれば16 GB〜18 GBのRAMを搭載したシステムでも動作し、8ビットのロスレスGGUFには24 GBが必要です。 [5]

### Inkling 2 MiniとQwen3.8-27Bを比較するとどのような違いがありますか？

Artificial Analysis Intelligence Index v5.0において、Inkling 2 MiniはAlibabaの密モデルであるQwen3.8-27Bと20.1で同点となる一方、DeepSWE v1.1（48.2%対42.2%）、SWE-bench Verified（79.2%対77.8%）、BrowseComp（79.0%対61.6%）などのエージェント型コーディングおよび検索ベンチマークで上回ります。密モデルのQwenが27Bパラメータを活性化するのに対し、Inkling 2 Miniのトークンあたり実効活性化パラメータは5.4Bのみであるため、計算量は約2.8分の1、Intelligence Indexタスクの完了時間は4分の1（9.0分対38.2分）、タスクあたりコストは6分の1（$0.59対$3.53）になります。ただし、ツールなしのパラメトリック事実想起（AA-Omniscience）や複数制約のチャット指示ではQwen3.8-27Bの方が高いスコアを示します。 [4]

### Inkling 2 Miniと同時に公開されたTML-d24-varloop-researchとはどのようなモデルですか？

TML-d24-varloop-researchは、Inkling 2 Miniと同じ24層MoEアーキテクチャを共有しつつ、設定パラメータloop_num_passesを通じて中間12層のパス回数を可変（1〜5回で学習、最大10回まで検証）にできるよう訓練されたオープンウェイトの研究用チェックポイントです。Thinking Machines Labは、安全性および解釈可能性の研究者が、潜在空間での反復ループが思考の連鎖の長さ、監視可能性、および推論の深さに与える影響を測定できるようにするため同モデルを公開しました。 [2]

## 引用できる文

- Thinking Machines Labは2026年11月20日、100万トークンのコンテキストウィンドウに対応する264億パラメータのループ型Mixture-of-Expertsビジョン言語モデルとして、Apache 2.0ライセンスの下でInkling 2 Miniを公開した。 [1][2][5]
- Inkling 2 Miniの24物理デコーダ層は、層0〜5を1回、層6〜17を重み共有とクロスパス・アテンション残差メッセージを用いて3回ループ実行し、層18〜23を1回実行することでトークンあたり48回の論理層訪問を行い、3.4Bの固有アクティブパラメータとトークンあたり5.4Bの実効重み活性化を実現している。 [1][2][5]
- 同モデルはエキスパートの3分の2を枝刈り（層あたり384個から128個へ削減）し、より大規模なInklingモデルから1兆のヒーリングトークンを蒸留した後に2.2兆のRLトークンを学習させ、先頭20層をNVFP4、末尾4層をMXFP8でネイティブ学習することで約20 GBのフットプリントへ圧縮された。 [1][2][3]
- 標準評価においてInkling 2 Miniは、DeepSWE v1.1（48.2%）、SWE-bench Pro v2 Hard（77.9%）、SWE-bench Verified（79.2%）、BrowseComp（79.0%）、DeepSearchQA（85.3%）、およびOmniDocBench v1.6（92.8%）で100B未満のすべてのオープンウェイトモデルをリードし、Artificial Analysis Intelligence Index v5.0では20.1でQwen3.8-27Bと1位タイとなった。 [1][3][4]
- NVIDIA DGX Spark上で行われたスタンフォード大学のIntelligence per Watt評価において、Inkling 2 Miniは0.703 intelligence per jouleを記録し、Qwen3.6-35B-A3B（0.430）、Gemma-4-26B-A4B（0.159）、およびQwen3.5-27B（0.036）を上回った。 [1][3]
- コンパニオンの可変ループチェックポイント（TML-d24-varloop-research）を用いた実験では、ループパス数を1回から3回へ増やすことでモデルのNo-CoT推論ホライズンが16秒から37秒へ拡大し、思考の連鎖の可読性を維持しつつエージェント型サボタージュの増加は見られなかった。 [1][2][3]

## 年表

- 2018: DehghaniらがUniversal Transformersを発表し、Thinking Machines Labが引用する重み共有型反復Transformer層の基礎概念を確立した。 [1]
- 2026-11-20: Thinking Machines LabがApache 2.0ライセンスの下でInkling 2 MiniおよびコンパニオンのTML-d24-varloop-researchチェックポイントを公開し、Transformers、llama.cpp、MLX、SGLang、LM Studio、Unslothでの公開当日サポートを開始した。 [1]
- 2026-11-21: 独立したベンチマーク分析により、Inkling 2 MiniがArtificial Analysis Intelligence Index v5.0で20.1を記録しパレートフロンティアに位置することが確認された。 [3]

## 出典

1. Introducing Inkling 2 Mini - Thinking Machines Lab. Thinking Machines Lab. 公開 2026-11-20. https://thinkingmachines.ai/news/inkling-2-mini/ (閲覧 2026-11-23; tier 3: official site)
2. Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup. Hugging Face. 公開 2026-11-20. https://huggingface.co/blog/inkling2mini (閲覧 2026-11-23; tier 3: official site)
3. Thinking Machines wows with Inkling 2 Mini looped transformer model that runs locally on laptops. VentureBeat. 公開 2026-11-21. https://venturebeat.com/technology/thinking-machines-wows-with-inkling-2-mini-looped-transformer-model-that-runs-locally-on-laptops (閲覧 2026-11-23; tier 2: academic or news)
4. Thinking Machines has released Inkling 2 Mini, an open weights looped transformer. Artificial Analysis. 公開 2026-11-20. https://artificialanalysis.ai/articles/inkling-2-mini (閲覧 2026-11-23; tier 2: academic or news)
5. Inkling 2 Mini - LM Studio Model Directory. Element Labs (LM Studio). https://lmstudio.ai/models/inkling-2-mini (閲覧 2026-11-23; tier 3: official site)
6. Inkling 2 Mini - Run Locally Guide | Unsloth Documentation. Unsloth. https://unsloth.ai/docs/models/inkling-2-mini (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Inkling 2 Mini." 版 2a531773, 2026-11-23. https://mimirwiki.com/ja/wiki/inkling-2-mini
