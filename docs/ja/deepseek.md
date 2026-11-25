---
title: "DeepSeek"
subtitle: "DeepSeek-V4、DeepSeek-R1、DeepSeek-V3基盤モデルを開発する中国の人工知能研究所"
canonical_url: https://mimirwiki.com/ja/wiki/deepseek
language: ja
page_class: entity
revision_sha256: c3325d185e9c11979353948083f164afd5b4d0b62204e2ee37faa29a2f93cd46
date_modified: 2026-11-25
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

> 2026年11月時点で、DeepSeekのAPIにはコンテキスト長1M、最大出力384Kの2つのモデル、deepseek-flash（DeepSeek-V4.1-Flash-1017）とdeepseek-v4-pro（DeepSeek-V4-Pro-0813）がある。オフピーク料金はピーク料金の半額で、Search、Fetch、OCR、音声のAPIを別途提供している。2026年11月18日12時（北京時間）以降、モデル呼び出し時に実行されるサーバー側の検索およびウェブ取得のツール呼び出しは課金されない。以前のモデルにはDeepSeek-V3（総パラメータ671B、アクティブ37B）と推論モデルDeepSeek-R1がある。

DeepSeekは中国の人工知能（AI）企業であり、サービスは中国に登録住所を置くHangzhou DeepSeek Artificial Intelligence Co., Ltd.が提供している。マルチヘッド潜在アテンション（Multi-head Latent Attention、MLA）およびDeepSeekMoEアーキテクチャに基づく大規模言語モデルを開発しており、DeepSeek-V2、DeepSeek-V3、強化学習による推論モデルDeepSeek-R1、APIで提供するDeepSeek-V4シリーズがある。

**別名:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd., 深度求索

## 主要な事実

- **運営法人:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **現行本番モデル:** deepseek-flash（DeepSeek-V4.1-Flash-1017）および deepseek-v4-pro（DeepSeek-V4-Pro-0813） (時点 2026-11-25) [1]
- **コンテキストおよび最大出力:** 1Mトークンのコンテキストウィンドウ、最大384K出力トークン (時点 2026-11-25) [1]
- **オープンウェイト推論のマイルストーン:** DeepSeek-R1（MITライセンス、2025年1月）および DeepSeek-V3（671B/37B MoE、2024年12月） [4]

## ファクトシート

- **正式名称:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **登録住所:** 中国 [7]
- **中核アーキテクチャ:** マルチヘッド潜在アテンション（MLA）、DeepSeekMoE、マルチトークン予測（MTP） [5]
- **主力APIモデル（2026年11月）:** DeepSeek-V4.1-Flash-1017（deepseek-flash）、DeepSeek-V4-Pro-0813（deepseek-v4-pro） [1]
- **APIコンテキストおよび出力上限:** コンテキスト長1M／最大出力384K [1]
- **API同時実行数制限:** 2,500同時リクエスト（deepseek-flash）、500同時リクエスト（deepseek-v4-pro） [2]
- **マルチモーダル・ツールAPI:** Search API、Fetch API、ファイル解析・OCR API、音声認識（ASR）、音声合成（TTS） [1]
- **オープンソースライセンス（R1）:** MITライセンス（DeepSeek-R1および蒸留モデルの重みとコード） [4]

## DeepSeekの企業概要とアーキテクチャ基盤

DeepSeekのサービスはHangzhou DeepSeek Artificial Intelligence Co., Ltd.が提供している。[7] 同社はモデルアーキテクチャに関する技術報告書を公開し、Mixture-of-Experts（MoE）モデルと推論モデルを発表してきた。[4][5][6]

DeepSeekのモデルは、**DeepSeek-V2**（2024年5月、総パラメータ236B、トークンあたり21Bがアクティブ）で導入され、**DeepSeek-V3**（2024年12月、総パラメータ671B、トークンあたり37Bがアクティブ）でも採用された2つのアーキテクチャを用いている。[5][6] - **マルチヘッド潜在アテンション（MLA）**: キー・バリュー（KV）キャッシュを潜在ベクトルに圧縮し、推論を効率化する。[5][6] - **DeepSeekMoE**: ルーティングされるエキスパートと共有エキスパートを用いる疎な計算構造である。DeepSeek-V3では、補助損失を使わない負荷分散の手法とマルチトークン予測（MTP）の学習目標が加わった。[5][6] DeepSeek-V3はFP8混合精度学習により14.8兆トークンで事前学習され、技術報告書は学習全体に要したのはH800 GPUで278.8万時間だったと述べている。[5]

## DeepSeek-R1と推論のための強化学習

2025年1月22日にarXivへ投稿されたDeepSeek-R1の論文は、**DeepSeek-R1**と**DeepSeek-R1-Zero**を紹介している。論文は、人手でラベル付けした推論過程を使わず、純粋な強化学習（RL）によって大規模言語モデルの推論能力を引き出せること、学習中に自己省察や検証といった振る舞いが現れたことを報告した。[4]

`DeepSeek-R1-Zero`は、RLの前に教師ありファインチューニングを行わず、Group Relative Policy Optimization（GRPO）で学習された。このモデルには可読性の低さと言語の混在という課題があったため、`DeepSeek-R1`ではコールドスタートの思考連鎖データ、棄却サンプリング、RL、教師ありファインチューニングを組み合わせた多段階の学習を行った。[4] 論文は、数学のタスクでOpenAI-o1-1217と同等の性能を示し、エンジニアリング寄りのコーディングタスクではOpenAI-o1-1217がDeepSeek-R1を上回ったと報告している。[4] DeepSeekは、QwenおよびLlamaのモデルを基にした1.5Bから70Bパラメータの蒸留モデル6種も公開した。[4]

## DeepSeek-V4シリーズ、料金体系、開発者プラットフォーム（2026年）

DeepSeekのAPI（`api.deepseek.com`）は、2026年4月24日にDeepSeek-V4-ProとDeepSeek-V4-Flashを追加した。[3] 2026年11月時点の料金ページには2つのモデルがあり、いずれも**コンテキスト長1M**、**最大出力384K**である。[1]

| モデル名 | モデルバージョン | 入力・キャッシュヒット（ピーク／オフピーク） | 入力・キャッシュミス（ピーク／オフピーク） | 出力（ピーク／オフピーク） | 同時実行数上限 |
| --- | --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` | $0.006 / $0.003 | $0.30 / $0.15 | $1.20 / $0.60 | 2,500 |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` | $0.044 / $0.022 | $1.32 / $0.66 | $3.96 / $1.98 | 500 |

料金は100万トークンあたりの価格である。[1][2] オフピーク料金はピーク料金の半額である。ピーク時間は、中国の祝日を除く月曜から金曜の01:00～04:00および06:00～10:00（UTC）である。[1] 両モデルとも思考モードと非思考モード、JSON出力、ツール呼び出し、Responses API、Anthropic形式のAPIに対応する。ビジョンは`deepseek-flash`が対応し、`deepseek-v4-pro`は対応していない。[1] 旧モデル名の`deepseek-v4-flash`と`deepseek-v4-flash-vision-exp`へのリクエストはDeepSeek-V4.1-Flash-1017が処理する。[1]

変更履歴によると、DeepSeek-V4-ProのGA版は2026年8月13日に展開され、DeepSeek-V4.1-Flashは2026年9月10日にリリースされ、2026年10月17日にDeepSeek-V4.1-Flash-1017へアップグレードされた。[3]

## DeepSeekの内蔵ウェブ検索、ユーティリティAPI、レート制御

2026年11月13日、DeepSeekは`deepseek-flash`モデルのMessages、Responses、Chat Completions APIで、ウェブ検索、ファイル入力、URL読み取り、モデル安全の機能を開発者に開放し、SearchとFetch、OCR、ASR、TTSを単体のAPIとしても提供した。[3] 料金ページの価格は次のとおりである。[1] - **Search API（テキスト）**: 成功したリクエスト1,000件あたり$0.75。[1] - **Fetch API**: 成功したリクエスト1,000件あたり$0.75。[1] - **ファイル解析・OCR API**: 1,000ページあたり$0.225。[1] - **音声認識（ASR）**: 音声1時間あたり定価$0.116、期間限定価格$0.058。[1] - **音声合成（TTS）**: 1万文字あたり定価$0.45、期間限定価格$0.225。[1]

2026年11月18日12時（北京時間、UTC+8）以降、モデル呼び出し時に実行されるサーバー側の検索およびウェブ取得のツール呼び出しは課金されない。返された結果はモデルのコンテキストに追加され、モデルのトークン使用量として課金される。[1]

同時実行数の上限はアカウント単位で計算され、`deepseek-flash`は2,500、`deepseek-v4-pro`は500である。上限を超えたリクエストにはHTTP 429エラーが返る。[2] 開発者は`user_id`パラメータを渡すことができ、DeepSeekはこれをコンテンツ安全の分離、KVCacheの分離、スケジューリングの分離に用いる。通常のAPIユーザーでは、すべての`user_id`を合算して上限を計算する。同時実行数の枠を引き上げたアカウントでは、`user_id`ごとにも`deepseek-flash`で2,500、`deepseek-v4-pro`で500の上限が適用される。[2]

## DeepSeekのデータガバナンスとプライバシーポリシー

DeepSeekのプライバシーポリシー（最終更新2026年2月10日）によると、サービスは中国に登録住所を置くHangzhou DeepSeek Artificial Intelligence Co., Ltd.が提供し管理している。[7] ポリシーは、DeepSeekが個人データを**中華人民共和国**で収集、処理、保存すると述べている。[7] モデルの学習や技術の最適化に個人データを使うことを拒否する権利も記載されている。[7] 開発者がDeepSeekのオープンプラットフォームで構築したアプリケーションのエンドユーザーの個人データはこのポリシーの対象外であり、その場合はアプリケーションを運営する開発者が個人データ処理の管理者であるとポリシーは説明している。[7] DeepSeekはDeepSeek-R1の蒸留モデルも公開している。[4]

## よくある質問

### 2026年11月時点で、DeepSeekの主なAPIモデルは何ですか？

DeepSeekのAPIには、deepseek-flash（モデルバージョンDeepSeek-V4.1-Flash-1017）とdeepseek-v4-pro（モデルバージョンDeepSeek-V4-Pro-0813）の2つのモデルがあります。どちらもコンテキスト長は1M、最大出力は384Kです。 [1][3]

### DeepSeekのピーク料金とオフピーク料金はどのように機能しますか？

オフピーク料金はピーク料金の半額です。ピーク時間は、中国の祝日を除く月曜から金曜の01:00～04:00および06:00～10:00（UTC）で、それ以外の時間はすべてオフピークです。たとえばdeepseek-flashのキャッシュミス入力は100万トークンあたりピーク$0.30、オフピーク$0.15、出力はピーク$1.20、オフピーク$0.60です。 [1]

### DeepSeekのAPIレート制限とuser_idによる同時実行制御はどのように機能しますか？

同時実行数の上限はアカウント単位で計算され、deepseek-flashは2,500、deepseek-v4-proは500です。上限を超えたリクエストにはHTTP 429エラーが返ります。通常のAPIユーザーでは、すべてのuser_idを合算して上限を計算します。同時実行数の枠を引き上げたアカウントでは、user_idごとにもdeepseek-flashで2,500、deepseek-v4-proで500の上限が適用されます。 [2]

### DeepSeek-V3とDeepSeek-R1が注目されたアーキテクチャ上の革新は何ですか？

DeepSeek-V3（総パラメータ数671B、トークンあたりの活性パラメータ数37B）は、低メモリなKVキャッシュを実現するマルチヘッド潜在アテンション（MLA）と、補助損失を用いないDeepSeekMoEルーターおよびFP8学習を組み合わせました。続くDeepSeek-R1では、大規模な純粋強化学習（GRPO）と多段階のコールドスタート学習を適用し、オープンなMITライセンスのもとでフロンティア級の推論性能を達成しました。 [4][5]

### DeepSeekのホスト型ウェブアプリやAPIに送信されたデータはどこに保存されますか？

DeepSeekのプライバシーポリシーは、個人データを中華人民共和国で収集、処理、保存すること、サービスはHangzhou DeepSeek Artificial Intelligence Co., Ltd.が提供し管理していることを述べています。開発者がDeepSeekのオープンプラットフォームで構築したアプリケーションのエンドユーザーは、このポリシーの対象外です。 [4][7]

## 引用できる文

- DeepSeekの本番APIエンドポイントであるdeepseek-flash（DeepSeek-V4.1-Flash-1017）およびdeepseek-v4-pro（DeepSeek-V4-Pro-0813）は、いずれも1Mトークンのコンテキストウィンドウと最大384K出力トークンに対応している。 [1][3]
- DeepSeekのAPIのオフピーク料金はピーク料金の半額であり、ピーク時間は中国の祝日を除く月曜から金曜の01:00～04:00および06:00～10:00（UTC）である。 [1]
- DeepSeekのAPIのアカウント単位の同時実行数上限はdeepseek-flashが2,500、deepseek-v4-proが500であり、枠を引き上げたアカウントではuser_idごとにも同じ上限が適用される。 [2]
- 2026年11月18日12時（北京時間）以降、DeepSeekのモデル呼び出し時に実行されるサーバー側の検索およびウェブ取得のツール呼び出しは課金されず、返された結果はモデルのトークン使用量として課金される。 [1]
- DeepSeek-V3は14.8Tトークンで学習された総パラメータ数671B（トークンあたりの活性パラメータ数37B）の混合エキスパートモデルであり、DeepSeek-R1は2025年1月にMITライセンスで公開された。 [4][5]

## 年表

- 2024-05: DeepSeekは、マルチヘッド潜在アテンション（MLA）と236B/21BのMoEアーキテクチャを導入したDeepSeek-V2技術報告書を公開した。 [6]
- 2024-12: DeepSeekは、FP8精度で14.8兆トークンを事前学習した671Bパラメータ（活性37B）の混合エキスパートモデルであるDeepSeek-V3を公開した。 [5]
- 2025-01: DeepSeekは、オープンソースのMITライセンスのもとでDeepSeek-R1、DeepSeek-R1-Zero、および6種の蒸留推論モデルを公開した。 [4]
- 2026-08-13: DeepSeek-V4-ProのGA版がアプリ、ウェブ、APIに展開された（モデル名deepseek-v4-pro）。 [1][3]
- 2026-10-17: DeepSeek V4.1 FlashがDeepSeek-V4.1-Flash-1017にアップグレードされた（モデル名deepseek-flash）。 [1][3]
- 2026-11-18: 北京時間12時以降、モデル呼び出し時に実行されるサーバー側の検索およびウェブ取得のツール呼び出しが課金されなくなった。 [1]

## 出典

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (閲覧 2026-11-25; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (閲覧 2026-11-25; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. 公開 2026-11-13. https://api-docs.deepseek.com/updates (閲覧 2026-11-25; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. 公開 2025-01-22. https://arxiv.org/abs/2501.12948 (閲覧 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. 公開 2024-12-27. https://arxiv.org/abs/2412.19437 (閲覧 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. 公開 2024-05-07. https://arxiv.org/abs/2405.04434 (閲覧 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (閲覧 2026-11-25; tier 3: official site)

## このページを引用する

Mimirwiki. "DeepSeek." 版 c3325d18, 2026-11-25. https://mimirwiki.com/ja/wiki/deepseek
