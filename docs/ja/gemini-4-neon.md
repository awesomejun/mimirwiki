---
title: "Gemini 4 Neon"
subtitle: "Google DeepMindが2026年11月にリリースしたコーディング・科学・エンタープライズ向けマルチモーダル推論モデル"
canonical_url: https://mimirwiki.com/ja/wiki/gemini-4-neon
language: ja
page_class: entity
revision_sha256: 313825f38b953c44f8528c3a677631f03788fc4b6957f021292e9ad06a58aef6
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ja/wiki/gemini-4-neon.md
  txt: https://mimirwiki.com/ja/wiki/gemini-4-neon.txt
  json: https://mimirwiki.com/ja/wiki/gemini-4-neon.json
  jsonld: https://mimirwiki.com/ja/wiki/gemini-4-neon.jsonld
translations:
  en: https://mimirwiki.com/wiki/gemini-4-neon
  ko: https://mimirwiki.com/ko/wiki/gemini-4-neon
  zh: https://mimirwiki.com/zh/wiki/gemini-4-neon
---

# Gemini 4 Neon

> Gemini 4 Neon（`gemini-4-neon`）は、Google DeepMindが2026年11月18日にリリースしたマルチモーダル推論大規模言語モデルである。Gemini 4 Carbonを基に調整されており、統合1,000,000トークンのコンテキストウィンドウでテキスト、画像、音声、動画、PDFを処理し、最大64,000の同期出力トークン（バックグラウンドロングデコードでは1,000,000トークン）と2026年3月の知識カットオフを備える。2026-11-23時点で、標準API料金は100万入力トークンあたり3.00ドル、100万キャッシュ入力トークンあたり0.15ドル、100万出力トークンあたり15.00ドルである。

Gemini 4 Neonは、Google DeepMindが開発し、2026年11月18日にGemini 4 Carbon、Gemini 4 Hydrogen、Gemini 4 Argonとともに第4世代Gemini 4シリーズの一部としてリリースしたマルチモーダル推論大規模言語モデルである。フラッグシップモデルであるGemini 4 Carbonを基に調整されたGemini 4 Neon（`gemini-4-neon`）は、ソフトウェアエンジニアリング、科学研究、サイバーセキュリティ防御、エンタープライズワークフローの全般において、フロンティア級の分析推論と低レイテンシ・低コストを両立するよう設計されている。統合1,000,000トークンのコンテキストウィンドウでテキスト、画像、音声、動画、PDF入力を受け付け、デフォルトの同期出力で最大64,000トークン、バックグラウンドロングデコードにより最大1,000,000出力トークンをサポートする。2026-11-23時点で、Gemini 4 NeonはGoogle AI StudioのGemini API、Google Cloud Model Garden、Gemini for businessを通じて提供されているほか、GeminiアプリおよびGoogle AntigravityにおいてGoogle AI ProおよびGoogle AI Ultraの有料購読者向けに提供されている。

**別名:** gemini-4-neon, Google Gemini 4 Neon, Gemini 4.0 Neon

## 主要な事実

- **リリース日:** 2026-11-18（Google DeepMindのKoray Kavukcuogluが発表） [1]
- **APIモデルコードと系統:** gemini-4-neon（Gemini 4 Carbonから調整） (時点 2026-11-23) [2]
- **コンテキストウィンドウと出力:** 統合100万トークン（デフォルト同期出力64K、バックグラウンドロングデコードで最大100万） (時点 2026-11-23) [2]
- **標準API料金:** 100万トークンあたり 入力$3.00、キャッシュ入力$0.15（95%割引）、出力$15.00 (時点 2026-11-23) [4]
- **知識カットオフ:** 2026年3月 (時点 2026-11-23) [2]

## ファクトシート

- **開発元:** Google DeepMind（Alphabet Inc.） [2]
- **リリース日:** 2026-11-18 [1]
- **APIモデルコード:** gemini-4-neon (時点 2026-11-23) [3]
- **ベースモデル系統:** Gemini 4 Carbonから調整（Gemini 4ファミリー：Carbon、Neon、Hydrogen、Argon） [2]
- **対応モダリティ:** 入力：テキスト、画像、音声、動画、PDF / 出力：テキスト (時点 2026-11-23) [3]
- **コンテキストウィンドウと出力上限:** 統合1,000,000トークン / 同期出力最大64,000トークン、バックグラウンドロングデコード最大1,000,000トークン (時点 2026-11-23) [2]
- **知識カットオフ:** 2026年3月 (時点 2026-11-23) [2]
- **標準API料金（グローバル）:** 100万トークンあたり 入力$3.00 / キャッシュ入力$0.15 / 出力（思考トークン含む）$15.00 (時点 2026-11-23) [4]
- **Cloud Priority / Batch料金:** 100万トークンあたり Priority（グローバル）：入力$5.40 / キャッシュ読み取り$0.27 / 出力$27.00、Batch（グローバル）：入力$1.50 / キャッシュ読み取り$0.075 / 出力$7.50 (時点 2026-11-23) [5]
- **提供チャネル:** Geminiアプリ、Gemini API、Google AI Studio、Gemini for business（Model Garden）、Google Antigravity (時点 2026-11-23) [2]
- **一般向けプラン:** Google AI Pro（5 TB）およびGoogle AI Ultra（20 TB以上、AI Proの5倍の上限） (時点 2026-11-23) [8]

## Gemini 4 Neonの概要、リリース、およびGemini 4ファミリーにおける位置づけ

Gemini 4 Neonは、Google DeepMindが開発し、2026年11月18日にGoogle DeepMindシニアバイスプレジデント兼GoogleチーフAIアーキテクトであるKoray Kavukcuogluによる発表記事を通じて公開されたマルチモーダル推論大規模言語モデルである。[1][2] 2026-11-23時点でGoogle AI Studioのドキュメントに掲載されている[Google Gemini](https://mimirwiki.com/ja/wiki/google-gemini) 4モデルカタログでは、元素名を用いた4つのモデル、すなわちGemini 4 Carbon（`gemini-4-carbon`）、Gemini 4 Neon（`gemini-4-neon`）、Gemini 4 Hydrogen（`gemini-4-hydrogen`）、Gemini 4 Argon（`gemini-4-argon`）が提供されている。[3]

2026年11月18日に公開されたGoogle DeepMindのモデルカードによると、Gemini 4 NeonはGemini 4 Carbonを基に調整されており、Carbonの基盤アーキテクチャ、学習データセット、データ処理パイプライン、ハードウェアおよびソフトウェアインフラストラクチャを共有している。[2] Googleは、最も困難な長期プロジェクト向けにGemini 4 Carbonを、高速な日常タスク向けにGemini 4 Hydrogenを位置づける一方、Gemini 4 Neonを分析の深さと高速なエンドツーエンド実行およびタスクあたりの低コストを両立する中間フロンティア階層として設計しており、単独で動作させることも、Google Antigravity内で並列実行されるGemini 4 Hydrogenサブエージェントを指揮するオーケストレーターとして機能させることもできる。[1][2]

2026-11-23時点で、Gemini 4 NeonはGeminiアプリ、Gemini Developer API、Google AI Studio、Gemini for business（Google Cloud Model Gardenを含む）、およびエージェント型開発プラットフォームであるGoogle Antigravityの5つの公式チャネルで提供されている。[1][2] 一般およびプロシューマー向けには、Google OneがGoogle AI Proプラン（ストレージ5 TB、月間200のGoogle Colabコンピュートユニット、月間10ドルのGoogle Cloudクレジットを含む）およびGoogle AI Ultraプラン（ストレージ20 TBから、Gemini 4 Carbonを追加、AI Proの5倍のGemini利用上限、月間2,000のColabコンピュートユニット、月間40ドルのGoogle Cloudクレジットを含む）にGemini 4 Neonへのアクセスをバンドルしている一方、エントリーレベルのGoogle AI Plusプラン（ストレージ400 GB）にはGemini 4 Hydrogenが含まれている。[8]

## Gemini 4 Neonの技術仕様、モダリティ、およびロングデコードアーキテクチャ

2026-11-23時点のGemini APIおよびGoogle DeepMindモデルカードによると、Gemini 4 Neon（`gemini-4-neon`）は最大1,000,000トークンの統合入出力コンテキストウィンドウ内で、テキスト文字列、画像、音声、動画ファイル、PDFドキュメントをネイティブに受け付ける。[1][2][3] 生成については、デフォルトの同期出力で最大64,000トークン、バックグラウンドロングデコード使用時で最大1,000,000出力トークンをサポートする。[2][3][4] モデルカードでは、Gemini 4 Neonの知識カットオフが2026年3月と記載されている。[2]

| 仕様 | Gemini 4 Neon（`gemini-4-neon`） |
| --- | --- |
| 開発元 | Google DeepMind（Alphabet Inc.） |
| リリース日 | 2026年11月18日 |
| ベースアーキテクチャおよび系統 | Gemini 4 Carbon（`gemini-4-carbon`）から調整 |
| 入力モダリティ | テキスト、画像、音声、動画、PDF |
| 出力モダリティ | テキスト（推論・思考トークンを含む） |
| コンテキストウィンドウ | 統合入出力1,000,000トークン |
| 最大出力トークン | デフォルト同期64,000 / バックグラウンドロングデコード最大1,000,000 |
| 知識カットオフ | 2026年3月 |
| Gemini APIでのキャッシュ対応 | 暗黙的コンテキストキャッシュ（$0.15 / 1Mトークン、明示的キャッシュ非対応） |

Gemini 4 Neonは、設定可能な思考レベル（デフォルトの`high`および`xhigh`を含む）、長時間のマルチターンエージェントセッションにおけるコンテキスト圧縮（context compaction）、[モデルコンテキストプロトコル](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）サーバーを含むツールオーケストレーション、およびGoogle Antigravityにおける`/swarm`マルチエージェント実行をサポートしている。[1] 発表記事の中でGoogleは、Google AntigravityにおけるGemini 4 Neonのロングデコードおよびエージェントスウォーム機能の4つのリファレンス実装を披露した。すなわち、Blender MCPを駆動してCarbonとHydrogenをブンゼンバーナーの炎で、ArgonとNeonをガス放電管で表現した3D実験台のレンダリング、既製アセットを一切使わずにモンブランおよびシャモニーの標高データ上で120 Hz物理演算を行う10,200行のカスタムシェーダーWebGL2フリーライドスキーシミュレーターの作成、ケンブリッジ大学キングス・カレッジにある1936年のアラン・チューリングの書斎（X.8号室）と動作する万能チューリングマシンを備えたインタラクティブ3D空間の再構築、そして埋め込み画像やApps Scriptを使わずに50万件以上のライブスプレッドシート数式のみで1枚の写真をエッジ検出・3D深度マッピング・シーンリライティング対応の10万セルのGoogleスプレッドシートへ変換する処理である。[1]

## Gemini 4 NeonのAPI・Google Cloud料金、キャッシュ、およびレート制限

Gemini 4 Neonは、Gemini Developer APIの有料ティア（無料ティアでは利用不可）およびGoogle Cloud Model Gardenでのみ提供されている。[4][5] モデルが処理するすべてのトークンが計測および課金対象となり、内部思考トークンや、グラウンディング有効時のツールシステム指示および関数宣言も含まれる。[4] Gemini Developer APIにおけるGemini 4 Neonのコンテキストキャッシュは暗黙的キャッシュのみに対応し、100万キャッシュ入力トークンあたり0.15ドル（基本入力料金3.00ドルから95%割引）で課金される一方、Google検索によるグラウンディング（Grounding with Google Search）はGemini 3以降のモデル全体で共有される月間5,000回の無料検索リクエストが含まれ、以降は1,000リクエストあたり14.00ドル（デフォルトで1日あたり1,500リクエストの上限）となる。[1][4][6]

Google Cloud Model Garden（Agent Platform）では、2026-11-23時点の料金がStandard、Priority、Batchの各処理モード、およびグローバルと非グローバル（リージョン）のエンドポイントによって異なり、明示的キャッシュ書き込み料金は2027年1月12日から適用される予定である。[5]

| プラットフォームおよびサービスティア（2026-11-23時点） | エンドポイントリージョン | 入力（テキスト、画像、動画、音声） | キャッシュ読み取り | キャッシュ書き込み（2027-01-12適用開始） | テキスト出力（応答および推論） |
| --- | --- | --- | --- | --- | --- |
| Gemini Developer API（有料ティア） | グローバル | $3.00 / 1M | $0.15 / 1M（暗黙的） | 非対応 | $15.00 / 1M |
| Google Cloud Model Garden - Standard | グローバル | $3.00 / 1M | $0.15 / 1M | $3.75 / 1M | $15.00 / 1M |
| Google Cloud Model Garden - Standard | 非グローバル | $3.30 / 1M | $0.165 / 1M | $4.125 / 1M | $16.50 / 1M |
| Google Cloud Model Garden - Priority | グローバル | $5.40 / 1M | $0.27 / 1M | $6.75 / 1M | $27.00 / 1M |
| Google Cloud Model Garden - Priority | 非グローバル | $5.94 / 1M | $0.297 / 1M | $7.425 / 1M | $29.70 / 1M |
| Google Cloud Model Garden - Batch | グローバル | $1.50 / 1M | $0.075 / 1M | $1.875 / 1M | $7.50 / 1M |
| Google Cloud Model Garden - Batch | 非グローバル | $1.65 / 1M | $0.0825 / 1M | $2.0625 / 1M | $8.25 / 1M |

Google Cloudでは、HTTP 200ステータスコードを返したリクエストに対してのみ課金され、4xxおよび5xxレスポンスにはトークン料金が発生しない。[5] Gemini Developer APIでは、利用ティアに応じてプロジェクト単位のレート制限および支出ベースのレート制限が適用される。内訳はTier 1（有効な課金アカウント紐付け、月間課金上限250ドル、10分間ローリングウィンドウあたりの支出上限10ドル）、Tier 2（累計支出100ドルかつ3日経過、課金上限2,000ドル、10分間あたり200ドル）、Tier 3（累計支出1,000ドルかつ30日経過、課金上限20,000ドル〜100,000ドル以上、10分間あたり200ドル）であり、上限を超過すると`429 RESOURCE_EXHAUSTED`が返される。[6]

## Gemini 4 Neonのベンチマーク評価

2026年11月18日に公開されたGemini 4 Neonモデルカードおよびリリース発表において、Google DeepMindは能力指数、エージェント型コーディング、エンタープライズ知識業務、科学・数学的推論、マルチモーダル理解、長文コンテキスト検索、サイバーセキュリティの各領域で、Gemini 4 Neonを[Claude](https://mimirwiki.com/ja/wiki/claude) Opus 5.5およびOpenAIの[GPT-6.2](https://mimirwiki.com/ja/wiki/gpt-6-2) Solと比較したベンチマーク評価を報告した。[1][2]

| カテゴリ | ベンチマーク | Gemini 4 Neon | Claude Opus 5.5 | GPT-6.2 Sol |
| --- | --- | --- | --- | --- |
| 能力指数 | Artificial Analysis Intelligence Index v5.0.1 | 61 | 59 | 57 |
| 能力指数 | Vals Index v2.2 | 70.9% | 70.1% | 66.1% |
| エージェント型コーディング | CursorBench 4.1 | 65.4% | 58.1% | 未報告 |
| エージェント型コーディング | Terminal-Bench 4.1（不正調整済み） | 65.2% | 65.8% | 61.5% |
| エージェント型コーディング | FrontierCode 2.0（メインスコア） | 46.2% | 47.3% | 43.8% |
| エージェント型コーディング | SWE-sweep（プロバイダーハーネス / mini-SWEハーネス） | 39.0% / 12.8% | 10.1% / 3.6% | 8.3% / 11.6% |
| 知識業務 | Zapier AutomationBench | 56.3% | 42.5% | 41.3% |
| 知識業務 | Agents' Last Exam v1.1 | 75.8% | 71.6% | 73.0% |
| 科学・数学 | RiemannBench | 84.0% | 80.0% | 80.0% |
| 科学・数学 | Terminal-Bench-Science 0.1 | 70.5% | 63.3% | 68.0% |
| 推論 | HLE-Diamond | 71.3% | 67.9% | 64.0% |
| マルチモーダル | MKA Climb WSR / Chartography / LVBench | 56.5% / 73.5% / 89.0% | 53.0% / 66.3% / 83.7% | 52.7% / 75.1% / 87.6% |
| 長文コンテキスト | GraphWalks（256K〜1M、BFS F1） | 95.2% | 66.8% | 80.1% |
| サイバーセキュリティ | CWE-Bench v2 / SEC-bench Pro / WebExploitBench v1.2 | 70.7% / 90.5% / 51.3% | 67.1% / 未報告 / 37.1% | 66.0% / 88.3% / 未報告 |

モデルカードの表に加え、GoogleはGemini 4 NeonがArtificial Analysis Coding Agent Indexで総合1位（58.6）、Legal Research BenchおよびTax Agent Benchで1位、Andon LabsのVending-Bench 2で1位（シミュレーション上の事業純資産16,843ドル）、さらに4,200件以上の実世界エージェントセッションを対象としたArenaのAgent Arena Indexで世界2位（1336 Elo、ステアラビリティ部門2位）を獲得したと報告した。[1] またArtificial Analysisも2026年11月18日、Gemini 4 Neonがタスクあたりのコストを約17%削減しつつ、Gemini 4 Carbonをわずかに上回る知能スコアを達成したと指摘した。[9]

## Gemini 4 Neonの安全性評価、制限事項、および利用可能地域

Gemini 4 Neonモデルカードによると、このモデルは長時間稼働するエージェントワークフロー、反復的なリポジトリのコーディングおよびデバッグ、マルチモーダル知識業務、ならびにセキュアなコード生成、ペネトレーションテスト、脆弱性の発見・検証・パッチ適用を含む防御的サイバーセキュリティ運用を想定して設計されている。[2] Googleは、Google Antigravityの内部テストにおいて、Gemini 4 NeonがこれまでテストされたGeminiモデルの中で最も低い捏造率（fabrication rate）を記録したと報告した。[1]

Gemini 4 NeonをGemini 4 Hydrogenと比較した内部の自動開発安全性評価において、Google DeepMindはGemini 4 Neonがテキスト対テキストのコンテンツ安全性（差0.00パーセントポイント）、多言語安全性、画像対テキストの安全性のすべてで同等の性能を示し、すべての変動が統計的信頼区間内に収まったと報告した。[2] 拒否時のトーンはGemini 4 Hydrogenと同等に維持されつつ、無害なマルチモーダルプロンプトに対する不当な拒否は減少した。[2]

モデルカードに記載されている制限事項には、自由形式の質問や知識カットオフ以降のクエリにおけるハルシネーションの可能性、2026年3月の知識カットオフ、およびGemini 4 Carbonの安全性・セキュリティフレームワークの下で管理される継続的なフロンティア安全性およびジェイルブレイク耐性対策が含まれる。[2] 2026-11-23時点で、Googleの利用可能地域ドキュメントにはGoogle AI StudioおよびGemini Developer APIがサポートされる215以上の国と地域が掲載されており、対象外地域のユーザーにはGoogle CloudのGemini Enterprise Agent Platformが案内されている。[7]

## よくある質問

### Gemini 4 Neonとはどのようなモデルで、Gemini 4モデルファミリーの中でどのように位置づけられていますか？

Gemini 4 Neon（`gemini-4-neon`）は、GoogleおよびGoogle DeepMindが2026年11月18日にリリースしたマルチモーダル推論大規模言語モデルです。より大規模なフラッグシップモデルであるGemini 4 Carbonを基に調整されており、最大限の長期推論を担うGemini 4 Carbonと、高速な日常実行を担うGemini 4 Hydrogenの中間に位置づけられ、フロンティア級の推論の深さと、より高速なタスク完了およびタスクあたりの低コストを両立しています。 [1][2][3]

### Gemini 4 Neonのコンテキストウィンドウ、対応モダリティ、知識カットオフはどうなっていますか？

Gemini 4 Neonは、統合1,000,000トークンの入出力コンテキストウィンドウ内でテキスト、画像、音声、動画、PDFファイルを受け付け、テキスト出力として同期実行で最大64,000トークン、バックグラウンドロングデコードにより最大1,000,000トークンを生成できます。2026年11月18日に公開されたGoogle DeepMindのモデルカードによると、知識カットオフは2026年3月です。 [2][3][4]

### Gemini APIとGoogle CloudにおけるGemini 4 Neonの料金はいくらですか？

2026-11-23時点で、Gemini Developer API（有料ティアのみ、無料ティアでは利用不可）およびGoogle Cloud Model Gardenのグローバルエンドポイントにおける標準料金は、100万入力トークンあたり3.00ドル、100万キャッシュ入力トークンあたり0.15ドル（95%割引）、100万出力トークン（思考トークンを含む）あたり15.00ドルです。Google Cloud Model Gardenでは、グローバルエンドポイントの100万トークンあたり、Priority料金が入力5.40ドル・キャッシュ読み取り0.27ドル・出力27.00ドル、Batch料金が入力1.50ドル・キャッシュ読み取り0.075ドル・出力7.50ドルとなっており、非グローバルのリージョンエンドポイントには10%の割増料金が適用されます。 [1][4][5]

### どのGoogleサブスクリプションや開発者プラットフォームにGemini 4 Neonが含まれていますか？

2026-11-23時点で、開発者はGoogle AI StudioのGemini API有料ティア、ならびにGoogle CloudのGemini for businessおよびModel Gardenを通じてGemini 4 Neonを利用できます。一般およびプロシューマー向けの購読者については、Google AI Proプラン（ストレージ5 TB）およびGoogle AI Ultraプラン（ストレージ20 TBから、AI Proの5倍のGemini利用上限を提供）に含まれており、Geminiアプリ、Google Antigravity、Google AI Studioで利用できます。 [1][2][4][8]

### コーディング、科学、エンタープライズ向けベンチマークにおけるGemini 4 Neonの性能はどうですか？

2026年11月18日のGoogle DeepMindのリリース発表およびモデルカードによると、Gemini 4 NeonはArtificial Analysis Intelligence Index v5.0.1で61（xhigh思考設定で総合3位）、Artificial Analysis Coding Agent Indexで58.6（総合1位）、Vals Index v2.2で70.9%（総合2位）、ZapierのAutomationBenchで56.3%（総合1位）、Andon LabsのVending-Bench 2で16,843ドル（総合1位）、RiemannBenchで84.0%、Terminal-Bench-Science 0.1で70.5%、HLE-Diamondで71.3%、GraphWalks（256K〜1M BFS）で95.2%、Google Antigravityプロバイダーハーネス内のSWE-sweepで39.0%を記録しました。 [1][2]

## 引用できる文

- Google DeepMindは2026年11月18日、Gemini 4 Carbonを基に調整（adapted）した中位階層のマルチモーダル推論モデルとしてGemini 4 Neonをリリースした。 [1][2]
- Gemini 4 Neon（APIモデルコード：gemini-4-neon）は、統合1,000,000トークンのコンテキストウィンドウでテキスト、画像、音声、動画、PDF入力を受け付け、デフォルトの同期出力で最大64,000トークン、バックグラウンドロングデコードにより最大1,000,000出力トークンをサポートする。 [2][3]
- 2026-11-23時点で、Gemini Developer APIおよびGoogle Cloud Model Garden（グローバルエンドポイント）におけるGemini 4 Neonの標準料金は、100万入力トークンあたり3.00ドル、100万キャッシュ入力トークンあたり0.15ドル、100万出力トークン（思考トークンを含む）あたり15.00ドルである。 [1][4][5]
- 2026-11-23時点で、Google Cloud Model GardenにおけるGemini 4 Neonのグローバル推論料金は、100万トークンあたりPriorityで入力5.40ドル・キャッシュ読み取り0.27ドル・出力27.00ドル、Batchで入力1.50ドル・キャッシュ読み取り0.075ドル・出力7.50ドルであり、非グローバル（リージョン）エンドポイントには10%の割増料金が適用される。 [5]
- Gemini 4 NeonのGoogle DeepMindモデルカードでは、知識カットオフが2026年3月と記載されている。 [2]
- Google DeepMindが報告した2026年11月のベンチマーク評価において、Gemini 4 NeonはArtificial Analysis Intelligence Index v5.0.1で61、Artificial Analysis Coding Agent Indexで58.6（総合1位）、Vals Index v2.2で70.9%、AutomationBenchで56.3%、RiemannBenchで84.0%、Google AntigravityハーネスでのSWE-sweepで39.0%を記録した。 [1][2]
- 2026-11-23時点で、Gemini 4 NeonはGoogle AI StudioのGemini API（有料ティアのみ）、Google Cloud Model GardenおよびGemini for business、さらにGeminiアプリとGoogle AntigravityにおけるGoogle AI ProおよびGoogle AI Ultraの有料購読者向けに提供されている。 [1][2][8]

## 年表

- 2026-03: Gemini 4 NeonのGoogle DeepMindモデルカードに記載された知識カットオフ日である。 [2]
- 2026-11-18: Google DeepMindがGeminiアプリ、Gemini API、Google AI Studio、Gemini for business、Google AntigravityでGemini 4 Neon（gemini-4-neon）をリリースし、Gemini 4 Neonモデルカードを公開した。 [1][2][9]
- 2027-01-12: Gemini 4 NeonにおけるGoogle Cloud Model Gardenのキャッシュ書き込み課金（Standardグローバル $3.75/1M、Priorityグローバル $6.75/1M、Batchグローバル $1.875/1M）の適用開始予定日である。 [5]

## 出典

1. Introducing Gemini 4 Neon. Google (The Keyword). 公開 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (閲覧 2026-11-23; tier 3: official site)
2. Gemini 4 Neon - Model Card - Google DeepMind. Google DeepMind. 公開 2026-11-18. https://deepmind.google/models/model-cards/gemini-4-neon/ (閲覧 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/models?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/pricing?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
5. Agent Platform Pricing | Google Cloud. Google Cloud. https://cloud.google.com/model-garden/pricing (閲覧 2026-11-23; tier 3: official site)
6. Rate limits - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/rate-limits?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
7. Available regions for Google AI Studio and Gemini API - Gemini API | Google AI Studio. Google AI Studio. https://aistudio.google.com/docs/available-regions?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
8. Google AI plans with Cloud Storage - Google One. Google One. https://one.google.com/about/google-ai-plans/ (閲覧 2026-11-23; tier 3: official site)
9. Google continues to accelerate its release cadence with Gemini 4 Neon | Artificial Analysis. Artificial Analysis. 公開 2026-11-18. https://artificialanalysis.ai/articles/gemini-4-neon-intelligence-gain (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "Gemini 4 Neon." 版 313825f3, 2026-11-23. https://mimirwiki.com/ja/wiki/gemini-4-neon
