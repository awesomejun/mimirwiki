---
title: "DeepSeek"
subtitle: "DeepSeek-V4、DeepSeek-R1、DeepSeek-V3基盤モデルを開発する中国の人工知能研究所"
canonical_url: https://mimirwiki.com/ja/wiki/deepseek
language: ja
page_class: entity
revision_sha256: 5d9455f90a89599fd5b296df5c3bf403549afcc7538ce8d223f9d7b711c0084a
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ja/wiki/deepseek.md
  txt: https://mimirwiki.com/ja/wiki/deepseek.txt
  json: https://mimirwiki.com/ja/wiki/deepseek.json
  jsonld: https://mimirwiki.com/ja/wiki/deepseek.jsonld
translations:
  en: https://mimirwiki.com/wiki/deepseek
  ko: https://mimirwiki.com/ko/wiki/deepseek
  zh: https://mimirwiki.com/zh/wiki/deepseek
---

# DeepSeek

> 2026年11月時点で、DeepSeekの開発者プラットフォームは100万トークンのコンテキストウィンドウを持つ2つの主要モデル、deepseek-flash（DeepSeek-V4.1-Flash-1017）とdeepseek-v4-pro（DeepSeek-V4-Pro-0813）を提供している。両モデルとも最大384K出力トークンに対応し、ピーク・オフピークの動的料金体系、ネイティブのSearch・Fetch・OCR・Speech API、および2026年11月18日に有効化された無料のサーバー側内蔵ウェブ検索機能を備えている。それ以前のオープンウェイトのマイルストーンには、DeepSeek-V3（総パラメータ数671B／活性パラメータ数37B）およびMITライセンスで公開されたDeepSeek-R1推論モデル群がある。

DeepSeek（正式法人名：Hangzhou DeepSeek Artificial Intelligence Co., Ltd. および Beijing DeepSeek Artificial Intelligence Co., Ltd.）は、2023年に設立され、中国・浙江省杭州市に本社を置く人工知能（AI）研究企業である。マルチヘッド潜在アテンション（Multi-head Latent Attention、MLA）およびDeepSeekMoEアーキテクチャを採用したオープンウェイト（open-weight）およびAPIホスト型の大規模言語モデル（LLM）を開発しており、DeepSeek-V2、DeepSeek-V3、強化学習推論モデルのDeepSeek-R1、マルチモーダルモデルのDeepSeek-V4シリーズを手掛けている。

**別名:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd., Beijing DeepSeek Artificial Intelligence Co., Ltd., 深度求索

## 主要な事実

- **運営法人:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. / Beijing DeepSeek Artificial Intelligence Co., Ltd. [7]
- **現行本番モデル:** deepseek-flash（DeepSeek-V4.1-Flash-1017）および deepseek-v4-pro（DeepSeek-V4-Pro-0813） (時点 2026-11-23) [1]
- **コンテキストおよび最大出力:** 1Mトークンのコンテキストウィンドウ、最大384K出力トークン (時点 2026-11-23) [1]
- **オープンウェイト推論のマイルストーン:** DeepSeek-R1（MITライセンス、2025年1月）および DeepSeek-V3（671B/37B MoE、2024年12月） [4]

## ファクトシート

- **正式名称:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **本社所在地:** 中国 浙江省 杭州市 [7]
- **中核アーキテクチャ:** マルチヘッド潜在アテンション（MLA）、DeepSeekMoE、マルチトークン予測（MTP） [5]
- **主力APIモデル（2026年11月）:** DeepSeek-V4.1-Flash-1017（deepseek-flash）、DeepSeek-V4-Pro-0813（deepseek-v4-pro） [1]
- **APIコンテキストおよび出力上限:** コンテキスト1,000,000トークン／最大出力384,000トークン（デフォルト64K） [1]
- **API同時実行数制限:** 2,500同時リクエスト（deepseek-flash）、500同時リクエスト（deepseek-v4-pro） [2]
- **マルチモーダル・ツールAPI:** Search API、Fetch API、OCR API、Speech-to-Text API、サーバー側 search_Option [1]
- **オープンソースライセンス（R1）:** MITライセンス（DeepSeek-R1および蒸留モデルの重みとコード） [4]

## DeepSeekの企業概要とアーキテクチャ基盤

DeepSeekは、Hangzhou DeepSeek Artificial Intelligence Co., Ltd. および Beijing DeepSeek Artificial Intelligence Co., Ltd. を通じて事業を展開し、フロンティア基盤モデルおよび開発者向けAPIを構築している。[1][7] 同研究所は2024年から2025年にかけて、詳細なアーキテクチャ技術報告書を公開するとともに、従来のフロンティアモデルに要する計算予算のごく一部で学習されたオープンウェイトの混合エキスパート（Mixture-of-Experts、MoE）モデルおよび推論モデルをリリースしたことで、国際的な注目を集めた。[4][5][6]

DeepSeekの基盤モデルは、**DeepSeek-V2**（2024年5月、総パラメータ数236B、トークンあたりの活性パラメータ数21B）で導入され、**DeepSeek-V3**（2024年12月、総パラメータ数671B、トークンあたりの活性パラメータ数37B）で拡張された2つの構造的革新を土台としている。[5][6] - **マルチヘッド潜在アテンション（Multi-head Latent Attention、MLA）**: 推論時にキー・バリュー（KV）キャッシュ表現を低ランクの潜在ベクトル（low-rank latent vector）へ圧縮することで、長文コンテキスト処理におけるメモリ帯域幅のオーバーヘッドを大幅に削減する。[5][6] - **補助損失を用いない負荷分散を備えたDeepSeekMoE（Auxiliary-Loss-Free Load Balancing）**: 細粒度のルーティングエキスパート（routed experts）と共有エキスパート（shared experts）を組み合わせ、性能低下を招く従来の補助的な負荷分散損失の代わりに動的バイアス調整ルーティング戦略を採用し、マルチトークン予測（Multi-Token Prediction、MTP）の学習目的を導入している。[5] DeepSeek-V3はFP8混合精度学習を用い、わずか278万8,000 H800 GPU時間で14.8兆トークンの事前学習を完了した。[5]

## DeepSeek-R1と推論のための強化学習

2025年1月、DeepSeekは寛容なMITライセンスのもとで**DeepSeek-R1**および**DeepSeek-R1-Zero**を公開し、事前の教師ありファインチューニング（SFT）を行わない大規模な純粋強化学習（RL）のみによって、言語モデルに自己検証（self-verification）、省察（reflection）、および長期的な思考の連鎖（Chain-of-Thought、CoT）推論を創発させられることを実証した。[4]

`DeepSeek-R1-Zero`がベースモデルに直接グループ相対方策最適化（Group Relative Policy Optimization、GRPO）を適用したのに対し、`DeepSeek-R1`はコールドスタートCoTデータと棄却サンプリング（rejection sampling）を用いた多段階学習を取り入れることで言語混在を解消し可読性を高め、数学、競技プログラミング、STEM推論ベンチマークにおいてOpenAI-o1-1217に匹敵する性能を達成した。[4] さらにDeepSeekは、DeepSeek-R1の出力から蒸留した、1.5Bから70Bパラメータ規模の密モデル（dense distilled models、QwenおよびLlamaアーキテクチャベース）6種も併せて公開した。[4]

## DeepSeek-V4シリーズ、料金体系、開発者プラットフォーム（2026年）

2026年後半までに、DeepSeekは本番APIプラットフォーム（`api.deepseek.com`）をマルチモーダルな**DeepSeek-V4**アーキテクチャへ移行し、チャット、推論（`thinking`）、視覚、音声入力を、**1,000,000トークンのコンテキストウィンドウ**および最大**384,000出力トークン**（デフォルト64K）を備えた2つの主要モデルエンドポイントに統合した。[1]

| APIモデルエイリアス | 基盤モデルバージョン | ピーク料金（08:00-24:00 UTC+8） | オフピーク料金（00:00-08:00 UTC+8） | 同時実行数制限 |
| --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017`（2026年10月20日リリース） | 入力：$0.03/M（キャッシュヒット）、$0.30/M（ミス、<=256K）、$0.50/M（>256K）、出力：$1.50-$2.50/M | 入力：$0.03/M（キャッシュヒット）、$0.15/M（<=256K）、$0.25/M（>256K）、出力：$0.75-$1.25/M | 2,500同時リクエスト [1][2] |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813`（2026年8月19日リリース） | 入力：$0.20/M（キャッシュヒット）、$2.00/M（ミス、<=256K）、$4.00/M（>256K）、出力：$12.00-$18.00/M | 入力：$0.20/M（キャッシュヒット）、$1.00/M（<=256K）、$2.00/M（>256K）、出力：$6.00-$9.00/M | 500同時リクエスト [1][2] |

両モデルともテキスト、画像、音声の入力を受け付け、テキスト、JSONモード、関数ツール呼び出し、および推論コンテンツ（Reasoning Content）を出力する。[1] 音声トークンを送信する場合、音声入力にはコンテキスト区分およびキャッシュ状態に応じてより高い100万トークンあたりの単価が課金される（`deepseek-flash`は$1.00-$4.00/M、`deepseek-v4-pro`は$7.00-$28.00/M）。[1] `deepseek-chat`や`deepseek-reasoner`といった従来のエイリアスは、自動的にV4シリーズのエンドポイントへマッピングされる。[1]

## DeepSeekの内蔵ウェブ検索、ユーティリティAPI、レート制御

2026年11月18日、DeepSeekはチャット補完（chat completions）エンドポイントをアップグレードし、`search_Option`パラメータを介したネイティブのサーバー側ウェブ検索およびページ取得に対応した。プロモーション展開期間中は、クエリごとの追加検索料金なしで内蔵検索を利用できる。[1][3] 独立したプログラマティックパイプライン向けには、専用のユーティリティエンドポイントも提供している。[1] - **Search API**: 1,000クエリあたり$5.00。[1] - **Fetch API**: 1,000 URL取得あたり$1.00。[1] - **OCR API**: ドキュメント1,000ページあたり$1.00。[1] - **Speech-to-Text API**: 音声文字起こし1時間あたり$0.10。[1]

利用金額ティアごとに厳格な1分あたりのトークン数（TPM）や1分あたりのリクエスト数（RPM）の上限を課す他社プロバイダーとは異なり、DeepSeekは主に処理中の同時実行数（`deepseek-flash`は2,500同時リクエスト、`deepseek-v4-pro`は500同時リクエスト）によってスループットを制御している。[2] マルチテナントアプリケーションを単一ユーザーによる過剰利用から保護するため、開発者はAPIペイロードに`user_id`パラメータを渡すことができ、これにより個別のエンドユーザーIDは**10同時リクエスト**に制限される（上限超過時はその`user_id`に対してのみHTTP `429 Too Many Requests`が返され、親組織のグローバルプールには影響しない）。[2]

## DeepSeekのデータガバナンスとプライバシーポリシー

DeepSeekのプライバシーポリシーによれば、消費者向けウェブ、モバイルアプリ、およびプラットフォームサービスは、Hangzhou DeepSeek Artificial Intelligence Co., Ltd. および Beijing DeepSeek Artificial Intelligence Co., Ltd. によって運営されている。[7] DeepSeekのサービスを通じて収集されたユーザープロンプト、アップロードファイル、会話履歴、およびインタラクションログは、**中華人民共和国**国内に設置されたサーバーに保存され、中華人民共和国のデータ保護法およびサイバーセキュリティ法の適用を受ける。[7] 消費者向けインタラクションデータは、該当するオプトアウトを行わない限り安全性コンプライアンスおよびサービス改善のために確認される場合がある一方、DeepSeek-V2、DeepSeek-V3、DeepSeek-R1のオープンウェイト配布版を利用すれば、企業は外部テレメトリを一切発生させずにプライベートインフラ上でモデルの重みをセルフホストできる。[4][5][7]

## よくある質問

### 2026年11月時点で、DeepSeekの主なAPIモデルは何ですか？

DeepSeekは2つの主要な本番APIモデルを提供しています。高スループットなマルチモーダル推論およびコーディング向けのdeepseek-flash（DeepSeek-V4.1-Flash-1017搭載）と、フロンティア級の深い推論向けのdeepseek-v4-pro（DeepSeek-V4-Pro-0813搭載）です。両モデルとも100万トークンのコンテキストウィンドウと最大384,000出力トークンを備えています。 [1][3]

### DeepSeekのピーク料金とオフピーク料金はどのように機能しますか？

DeepSeekはオフピーク時間帯（北京時間／UTC+8の00:00〜08:00、UTCの16:00〜00:00に相当）において、キャッシュミスの入力トークンおよび出力トークンのAPI料金を50%割引しています。たとえば、deepseek-flashの入力（<=256Kコンテキスト、キャッシュミス）はピーク時の$0.30/Mトークンからオフピーク時は$0.15/Mトークンに下がり、出力は$1.50/Mから$0.75/Mに下がります。 [1]

### DeepSeekのAPIレート制限とuser_idによる同時実行制御はどのように機能しますか？

DeepSeekは処理中の同時実行数上限として、deepseek-flashで2,500同時リクエスト、deepseek-v4-proで500同時リクエストを適用しています。開発者がuser_idフィールドにエンドユーザー識別子を渡すと、DeepSeekはその特定のuser_idを10同時リクエストに制限するため、1人のエンドユーザーが開発者のアカウント全体のクォータを使い切ることを防げます。 [2]

### DeepSeek-V3とDeepSeek-R1が注目されたアーキテクチャ上の革新は何ですか？

DeepSeek-V3（総パラメータ数671B、トークンあたりの活性パラメータ数37B）は、低メモリなKVキャッシュを実現するマルチヘッド潜在アテンション（MLA）と、補助損失を用いないDeepSeekMoEルーターおよびFP8学習を組み合わせました。続くDeepSeek-R1では、大規模な純粋強化学習（GRPO）と多段階のコールドスタート学習を適用し、オープンなMITライセンスのもとでフロンティア級の推論性能を達成しました。 [4][5]

### DeepSeekのホスト型ウェブアプリやAPIに送信されたデータはどこに保存されますか？

DeepSeekのプライバシーポリシーに基づき、DeepSeekのホスト型消費者向けサービスおよびプラットフォームサービスに送信されたデータは、中華人民共和国国内のサーバーに保存され、Hangzhou DeepSeek Artificial Intelligence Co., Ltd. によって管理されます。ローカルでのデータレジデンシーを必要とする組織は、DeepSeekのオープンウェイトモデルをセルフホストすることができます。 [4][7]

## 引用できる文

- DeepSeekの本番APIエンドポイントであるdeepseek-flash（DeepSeek-V4.1-Flash-1017）およびdeepseek-v4-pro（DeepSeek-V4-Pro-0813）は、いずれも1Mトークンのコンテキストウィンドウと最大384K出力トークンに対応している。 [1][3]
- DeepSeekは、00:00〜08:00 UTC+8（16:00〜00:00 UTC）のオフピーク時間帯において、deepseek-flashとdeepseek-v4-proの双方でキャッシュミス入力および出力に対して50%の割引料金を提供している。 [1]
- DeepSeekはAPIの同時実行数をdeepseek-flashで2,500同時リクエスト、deepseek-v4-proで500同時リクエストに制限しており、user_idパラメータによりエンドユーザーごとに10同時リクエストの任意上限を設定できる。 [2]
- 2026年11月18日、DeepSeekはチャット補完APIにおいて追加の検索クエリ料金なしで利用できる内蔵のサーバー側ウェブ検索およびページ取得機能を有効化した。 [1][3]
- DeepSeek-V3は14.8Tトークンで学習された総パラメータ数671B（トークンあたりの活性パラメータ数37B）の混合エキスパートモデルであり、DeepSeek-R1は2025年1月にMITライセンスで公開された。 [4][5]

## 年表

- 2024-05: DeepSeekは、マルチヘッド潜在アテンション（MLA）と236B/21BのMoEアーキテクチャを導入したDeepSeek-V2技術報告書を公開した。 [6]
- 2024-12: DeepSeekは、FP8精度で14.8兆トークンを事前学習した671Bパラメータ（活性37B）の混合エキスパートモデルであるDeepSeek-V3を公開した。 [5]
- 2025-01: DeepSeekは、オープンソースのMITライセンスのもとでDeepSeek-R1、DeepSeek-R1-Zero、および6種の蒸留推論モデルを公開した。 [4]
- 2026-08-19: DeepSeekは、1Mコンテキストおよびテキスト・画像・音声のマルチモーダル入力を備えたDeepSeek-V4-Pro-0813（deepseek-v4-pro）をAPIプラットフォーム上で提供開始した。 [1][3]
- 2026-10-20: DeepSeekは、高スループットのdeepseek-flashエンドポイントの基盤モデルとしてDeepSeek-V4.1-Flash-1017を展開した。 [1][3]
- 2026-11-18: DeepSeekは、追加の検索料金なしでチャット補完API内にサーバー側ウェブ検索およびページ取得機能の内蔵サポートを有効化した。 [1][3]

## 出典

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (閲覧 2026-11-23; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (閲覧 2026-11-23; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 公開 2026-11-18. https://api-docs.deepseek.com/updates (閲覧 2026-11-23; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 公開 2025-01-22. https://arxiv.org/abs/2501.12948 (閲覧 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 公開 2024-12-27. https://arxiv.org/abs/2412.19437 (閲覧 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 公開 2024-05-07. https://arxiv.org/abs/2405.04434 (閲覧 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "DeepSeek." 版 5d9455f9, 2026-11-23. https://mimirwiki.com/ja/wiki/deepseek
