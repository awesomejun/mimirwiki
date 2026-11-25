---
title: "Google Gemini"
subtitle: "GoogleおよびGoogle DeepMindによるネイティブマルチモーダルAIモデル群、開発者APIプラットフォーム、コンシューマー向けアプリケーションエコシステム"
canonical_url: https://mimirwiki.com/ja/wiki/google-gemini
language: ja
page_class: entity
revision_sha256: 900ebdd7b0bc2223ce2db550b02fb33b711883614506b69b36ea871be919558d
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/google-gemini.md
  txt: https://mimirwiki.com/ja/wiki/google-gemini.txt
  json: https://mimirwiki.com/ja/wiki/google-gemini.json
  jsonld: https://mimirwiki.com/ja/wiki/google-gemini.jsonld
translations:
  en: https://mimirwiki.com/wiki/google-gemini
  ko: https://mimirwiki.com/ko/wiki/google-gemini
  zh: https://mimirwiki.com/zh/wiki/google-gemini
  es: https://mimirwiki.com/es/wiki/google-gemini
---

# Google Gemini

> Google DeepMindが開発したGoogle Geminiは、コンシューマー向けサブスクリプション（Google AI Plus、Pro、Ultra）および開発者向けプラットフォーム（Google AI Studio、Gemini Enterprise Agent Platform）にまたがるネイティブマルチモーダルAIモデルシリーズ・製品エコシステムである。2026年11月時点で、フラッグシップのGemini 4ファミリーはGemini 4 Carbon、Gemini 4 Neon、Gemini 4 Argon、Gemini 4 Hydrogenの4モデルで構成されており、いずれも100万トークンのコンテキストウィンドウ、最大64K/1Mの出力トークン、テキスト・画像・音声・動画・PDF入力に対応している。CarbonとArgonの有料API料金は、2026年11月30日までプロモーション価格として100万トークンあたり入力$2.00／出力$10.00が適用され、2026年12月1日からは$4.00／$20.00となる。

Google Geminiは、Google DeepMindおよびAlphabet Inc.が開発したネイティブマルチモーダル人工知能（AI）基盤モデル群およびアシスタントアプリケーションの中核製品である。2023年12月のGemini 1.0で初めて発表され、Gemini 1.5、2.5、3を経て、化学元素名を冠したGemini 4世代（`gemini-4-carbon`、`gemini-4-neon`、`gemini-4-argon`、`gemini-4-hydrogen`）へと拡張された。Geminiは、20億人以上のユーザーを抱える7製品を含む、ユーザー数5億人超のGoogle全15製品に組み込まれているほか、Google AI Studio、Gemini Developer API、Google CloudのGemini Enterprise Agent Platformの基盤として稼働している。

**別名:** Google Gemini, Google DeepMind, Gemini 4 Carbon, Gemini 4 Neon, マルチモーダルAI, Google AI Studio

## 主要な事実

- **開発元・親会社:** Google DeepMind / Alphabet Inc.（CIK 0001652044; Nasdaq: GOOGL, GOOG） [1]
- **製品統合規模:** ユーザー数5億人以上のGoogle全15製品に統合（うち20億人以上の7製品を含む） [1]
- **Gemini 4フラッグシップ構成:** Gemini 4 Carbon、Gemini 4 Neon、Gemini 4 Argon、Gemini 4 Hydrogen（1Mコンテキスト、最大64K/1M出力） [3]
- **特化型Gemini 3/4モデル:** Gemini 3.8 Flash/Live/TTS、Nano Banana 2.1（画像）、Gemini Omni Flash（15秒動画）、Genie 4（24 fpsワールド） [3]
- **コンシューマー向けサブスクリプション:** Google AI Plus（400 GB、Hydrogen）、Google AI Pro（5 TB、Neon）、Google AI Ultra（20 TB以上、Carbon） [2]

## ファクトシート

- **開発元:** Google DeepMind（Alphabet Inc.） [1]
- **初回リリース:** 2023年12月（Gemini 1.0技術レポートを2023年12月19日に提出） [7]
- **現行世代:** Gemini 4（Carbon、Neon、Argon、Hydrogen）および特化型Gemini 3.8 / Omni / Genie 4 [3]
- **対応モダリティ:** 入力：テキスト、画像、音声、動画、PDF／出力：テキスト、音声、画像、動画、インタラクティブワールド [3]
- **コンテキスト・最大出力:** 1,000,000トークンのコンテキストウィンドウ、最大出力64,000 / 1,000,000トークン（Gemini 4ファミリー） [3]
- **Carbon・Argon API料金:** 2026年11月30日まで入力$2.00 / 出力$10.00 / キャッシュ$0.10（100万トークンあたり。2026年12月1日以降は$4 / $20 / $0.20） [4]
- **API利用ティア:** Free、Tier 1（上限$250）、Tier 2（上限$2,000）、Tier 3（上限$20,000-$100,000以上） [5]
- **ローリング支出レート制限:** 10分あたり$10（Tier 1）、10分あたり$200（Tier 2およびTier 3） [5]
- **コンシューマー向けGoogle Oneプラン:** Google AI Plus（400 GB）、Google AI Pro（5 TB）、Google AI Ultra（20 TB以上、150以上の国と地域） [2]
- **開発者向けプラットフォーム:** Google AI Studio、Gemini Developer API、Gemini Enterprise Agent Platform、Google Antigravity [2]

## Gemini 1.0からGemini 4への進化とAlphabetエコシステムでの導入規模

Google DeepMindは2023年12月、画像・音声・動画・テキストの各モダリティを最初から統合的に学習したモデル群としてGeminiアーキテクチャを発表した（`arXiv:2312.11805`、2023年12月19日提出）。[7] 続いて2024年3月にはGemini 1.5（`arXiv:2403.05530`、2024年3月8日提出）を公開し、数百万トークン規模のロングコンテキストにおけるマルチモーダル理解を実現した。[8] さらに2025年7月には、思考トークン（thinking tokens）、高度な推論機能、次世代のエージェント機能を統合したGemini 2.5（`arXiv:2507.06261`、2025年7月7日提出）を発表し、その後Alphabet Inc.の2025会計年度Form 10-K（2026年2月5日提出）で取り上げられたGemini 3世代へと展開された。[1][9]

Alphabet Inc.が米国証券取引委員会（SEC）に提出したForm 10-Kによると、Geminiモデルは20億人以上のユーザーを持つ7製品を含む、ユーザー数5億人超のGoogle全15製品に組み込まれているほか、Gemini EnterpriseやGemini for Google Workspaceといった法人向け製品にも採用されている。[1] 2026年11月までに、Google DeepMindはGemini 4ファミリーによってフロンティアモデルの投入ペースをさらに加速させ、従来のサイズ表記から化学元素名による命名体系（`Carbon`、`Neon`、`Argon`、`Hydrogen`）へと移行した。[3][10]

## Gemini 4および特化型Gemini 3モデルカタログ

Gemini Developer APIおよびGoogle AI Studioにおける現行のモデルカタログは、フラッグシップのGemini 4シリーズ（すべてのバリアントが1,000,000トークンのコンテキストウィンドウ、64,000 / 1,000,000トークンの最大出力制限、テキスト・画像・音声・動画・PDFのネイティブ入力に対応）と、特化型のGemini 3.xおよびインタラクティブメディア向けエンドポイントで構成されている。[3]

| モデル名 | APIエンドポイントコード | ティアおよび主なワークロード特性 |
| --- | --- | --- |
| Gemini 4 Carbon | `gemini-4-carbon` | 最上位のフロンティア推論モデル。拡張された検証ループと思考トークンを用い、高度なソフトウェアエンジニアリング、サイバーセキュリティ防御、高度な数学・科学、1Mトークンの長文デコード生成に対応 |
| Gemini 4 Neon | `gemini-4-neon` | ソフトウェアエンジニアリング、マルチモーダル知識業務、科学ワークフローにおいて高速なエンドツーエンドのタスク完了に最適化されたフロンティア級インテリジェンスモデル |
| Gemini 4 Argon | `gemini-4-argon` | Carbonと比較して高速な応答と1ターンあたりのトークン消費量削減を実現しつつ、Gemini 4の知能を提供する高効率フロンティア推論モデル |
| Gemini 4 Hydrogen | `gemini-4-hydrogen` | 日常的なコーディング、高スループット処理、エージェントワークフロー向けに設計された高速・高コスト効率のGemini 4モデル |
| Gemini 3.8 Flash | `gemini-3.8-flash` | ソフトウェアエンジニアリングおよび自律型エンタープライズワークフロー向けの安定版前世代Flashモデル |
| Gemini 3.8 Live & Extended Thinking | `gemini-3.8-live` / `gemini-3.8-live-extended-thinking` | Live API向けの低遅延音声エージェントモデル（標準版および高負荷バックグラウンド推論版） |
| Gemini 3.8 Flash TTS & Flash-Lite TTS | `gemini-3.8-flash-tts` / `gemini-3.8-flash-lite-tts` | 表現豊かな演技、音声デザイン、音声複製に対応するスタジオ品質および大量処理向けのテキスト音声合成モデル |
| Nano Banana 2.1 / 2 / Pro | `gemini-nano-banana-2.1` / `gemini-3.1-flash-image` / `gemini-3-pro-image` | タイポグラフィ、マルチターン一貫性、大量のビジュアル生成に最適化されたネイティブ画像生成・編集モデル |
| Gemini Omni Flash | `gemini-omni-flash` (`gemini-omni-1.2-flash`) | ネイティブ音声付きで最大15秒の動画を生成・編集でき、キーフレーム補間、動画延長、キャラクター一貫性に対応する動画モデル |
| Genie 4 | `genie-4` | WebRTCおよびWebSockets経由で、同期された48 kHzステレオ音声付きの操作可能な24 fps環境をリアルタイム配信するインタラクティブワールドモデル |
| Gemini Decision 1 | `gemini-decision-1` | Decisions API上で提供される高スループット意思決定モデル（Tier 3で最大15,000 RPM、10M TPM） |

カタログにはこのほか、`gemini-3.6-flash`、`gemini-3.5-flash-lite`、`gemini-3.1-flash-lite`、発話単位の言語検出と話者分離（speaker diarization）を備えた低遅延音声認識モデル`gemini-3.5-transcribe`、70以上の言語に対応するリアルタイム音声翻訳モデル`gemini-3.5-live-translate-preview`の安定版エンドポイントも含まれている。[3]

## Gemini Developer APIの料金体系、利用ティア、レート制限

Gemini Developer APIでは、一部モデルで利用可能かつ送信内容がGoogle製品の改善に使用される場合がある無料ティア（Free tier）と、顧客データがモデル学習に使用されない有料ティア（Paid tier）が提供されている。[4] `gemini-4-carbon`と`gemini-4-argon`はいずれも無料ティアでは利用できず、内部思考トークンや、Google検索によるグラウンディング（Grounding with Google Search。有料ティアでは月5,000回の無料検索リクエストが含まれ、プロジェクトのデフォルト上限は1日1,500リクエスト）使用時のツールシステム指示・関数宣言を含め、処理されたすべてのトークンが課金対象となる。[4][5]

`gemini-4-carbon`および`gemini-4-argon`について、Googleは2026年11月30日までプロモーションローンチ価格を設定しており、2026年12月1日から標準定価へ移行する。[4]

- **入力料金（有料ティア）**：2026年11月30日まで100万トークンあたり$2.00、2026年12月1日以降は100万トークンあたり$4.00。[4]
- **出力料金（思考トークンを含む）**：2026年11月30日まで100万トークンあたり$10.00、2026年12月1日以降は100万トークンあたり$20.00。[4]
- **コンテキストキャッシュ料金（暗黙的キャッシュのみ）**：2026年11月30日まで100万トークンあたり$0.10、2026年12月1日以降は100万トークンあたり$0.20（CarbonおよびArgonでは明示的キャッシュは非対応）。[4]

Gemini APIのレート制限はAPIキー単位ではなくGoogle Cloudプロジェクト単位で適用され、1日あたりのリクエストクォータ（RPD）は太平洋時間（PT）の午前0時にリセットされる。[5] RPM、TPM、RPDのクォータに加え、GoogleはプロジェクトのGoogle Cloud累計課金履歴に連動したローリング10分間の支出ベースレート制限（`429 RESOURCE_EXHAUSTED`）を適用している。[5]

| 利用ティア | 適用条件 | 月間課金ティア上限 | ローリング10分間支出制限 | Gemini Omni Flash（RPM / RPD） | Genie 4（同時セッション数 / RPD） | Gemini Decision 1（RPM / TPM / RPD） |
| --- | --- | --- | --- | --- | --- | --- |
| Free | アクティブなプロジェクトまたは無料トライアル | 該当なし | 該当なし | 非対応 | 非対応 | 200 / 50K / 10,000 |
| Tier 1 | 有効な請求先アカウントのリンク | $250 | $10 / 10分 | 8 / 40 | 2 / 50 | 1,500 / 1M / 50,000 |
| Tier 2 | 累計支出$100以上かつ初回支払いから3日経過 | $2,000 | $200 / 10分 | 16 / 200 | 5 / 250 | 5,000 / 4M / 無制限 |
| Tier 3 | 累計支出$1,000以上かつ初回支払いから30日経過 | $20,000 - $100,000以上 | $200 / 10分 | 40 / 2,000 | 10 / 1,000 | 15,000 / 10M / 無制限 |

`genie-4`向けのInteractions APIでは、セッション内のリアルタイム制御メッセージ（`user_action`およびセッション中の`input`イベント）は個別のRPMやRPDクォータを消費しないが、Genie 4はBatch API、Flex推論、Priority推論には対応していない。[5] Google AI Studioの非対応地域にいる開発者は、Google CloudのGemini Enterprise Agent Platformを通じてGeminiモデルを利用できる。[6]

## Google One AIプランおよびGoogle Workspace統合機能

Googleは一般消費者、クリエイター、個人開発者向けに、Gemini機能とGoogle Oneクラウドストレージを組み合わせた3段階のサブスクリプションプランを提供している（いずれも最大5人の追加メンバーとのファミリー共有に対応）。[2]

1. **Google AI Plus（ストレージ400 GB）**：Gemini 4 Hydrogen、Deep Research、Tasks in Gemini、Chrome auto browse、Gemini Notebook、Gmailの校正機能、およびAndroid・iOS向けGmail Live（米国のみ）へのアクセスが含まれる。[2] 2. **Google AI Pro（ストレージ5 TB）**：Geminiアプリ、Google Antigravity、Google AI StudioでのGemini 4 Neon利用を含む4倍のGemini利用枠に加え、月間200のGoogle Colabコンピュートユニット、Google Developer Program経由の月間$10のGoogle Cloudクレジット、Android Studioでの拡張エージェントAI支援、Googleドキュメント・スプレッドシートでのGeminiおよびDocs Live（米国のみ）、Google Flow動画生成、YouTube Premium Lite（個人向け）、Google Health Premium、Google Home Premium Standard（30日間のイベント履歴、月額$10相当）を提供する。[2] 認証済み学生はGoogle AI Proを1年間無料で利用でき、またはフル版のYouTube Premiumとのバンドルを月額$8.99で利用できる。[2] 3. **Google AI Ultra（ストレージ20 TBから、150以上の国と地域で提供）**：AI Proの5倍の利用上限を提供し、Geminiアプリおよび検索のAIモードでのGemini 4 Carbon、Project Genieによるリアルタイムのインタラクティブワールド生成、月間2,000のGoogle Colabコンピュートユニット、月間$40のGoogle Cloudクレジット、YouTube Premium Familyプラン（100以上の国と地域）、Google Health Premium、Google Home Premium Advanced（24時間365日のイベント履歴および説明機能、月額$20相当）が利用可能となる。[2]

Geminiアプリケーションエコシステム全体において、Deep Researchは数百のウェブサイトをリアルタイムで自律的に閲覧・統合して複数ページにわたる調査レポートを生成し、Tasks in Geminiはユーザーに代わってバックグラウンドで複数ステップのWebワークフローを実行する。[2]

## よくある質問

### Gemini 4 Carbon、Neon、Argon、Hydrogenの違いは何ですか？

4つのGemini 4モデルはいずれも100万トークンのコンテキストウィンドウ、最大64K/1Mの出力トークン、およびテキスト・画像・音声・動画・PDF入力に対応しています。Gemini 4 CarbonはGoogle最強のフロンティア推論モデルであり、拡張された検証ループと思考トークンを使用して、最も難易度の高いソフトウェアエンジニアリング、サイバーセキュリティ、科学の課題に対応します。Gemini 4 Neonは高速なエンドツーエンドのタスク完了に最適化されたフロンティア級の知能を提供します。Gemini 4 ArgonはCarbonと比較して1ターンあたりのトークン消費量と遅延を抑えた高効率フロンティア推論モデルであり、Gemini 4 Hydrogenは日常的なコーディングや大量のエージェントワークフロー向けの高速・高コスト効率モデルです。 [3]

### Gemini Developer APIにおけるGemini 4 CarbonとGemini 4 Argonの料金はいくらですか？

Gemini 4 CarbonおよびGemini 4 Argonはいずれも無料ティアでは提供されていません。有料ティアでは両モデル共通で、2026年11月30日までプロモーション価格として100万トークンあたり入力$2.00、出力（思考トークンを含む）$10.00、暗黙的キャッシュ$0.10が適用されます。2026年12月1日からは標準価格に移行し、両モデルとも100万トークンあたり入力$4.00、出力$20.00、暗黙的キャッシュ$0.20となります。 [4]

### Gemini 4 CarbonとGemini 4 NeonはどのGoogle One AIサブスクリプションプランに含まれていますか？

Google AI Plus（ストレージ400 GB）にはGemini 4 Hydrogenが含まれています。Google AI Pro（ストレージ5 TB）では、Geminiアプリ、Google Antigravity、Google AI StudioでGemini 4 Neonが利用可能になり、月間200のColabコンピュートユニットと月間$10のGoogle Cloudクレジットも付属します。Google AI Ultra（ストレージ20 TBから）では、Geminiアプリおよび検索のAIモードでGemini 4 Carbonが利用可能になるほか、AI Proの5倍の利用上限、Project Genieのインタラクティブワールド、月間2,000のColabコンピュートユニット、月間$40のGoogle Cloudクレジット、YouTube Premium Familyプランが含まれます。 [2]

### Gemini APIの利用ティアと支出ベースのレート制限はどのように機能しますか？

Gemini APIのレート制限はGoogle Cloudプロジェクト単位で適用され、RPM、TPM、RPD（太平洋時間の午前0時にリセット）に加えて、ローリング10分間の支出制限が設けられています。請求先アカウントをリンクするとTier 1（月間上限$250、10分間あたりの支出制限$10）が適用されます。Google Cloudでの累計支出$100以上かつ初回支払いから3日経過でTier 2（月間上限$2,000、10分間あたりの支出制限$200）、累計支出$1,000以上かつ30日経過でTier 3（月間上限$20,000〜$100,000以上、10分間あたりの支出制限$200）が解放されます。 [5]

## 引用できる文

- 2026年2月に提出されたAlphabet Inc.の2025会計年度Form 10-Kによると、Geminiモデルは20億人以上のユーザーを持つ7製品を含め、ユーザー数5億人超のGoogle全15製品に統合されている。 [1]
- Gemini 4モデルファミリーは4つの主要エンドポイント（gemini-4-carbon、gemini-4-neon、gemini-4-argon、gemini-4-hydrogen）で構成され、それぞれ100万トークンのコンテキストウィンドウ、最大64K/1Mの出力トークン、およびテキスト・画像・音声・動画・PDF入力に対応している。 [3]
- Gemini Developer APIにおいて、Gemini 4 CarbonとGemini 4 Argonは無料ティアでは利用できず、2026年11月30日までは100万トークンあたり入力$2.00、出力（思考トークンを含む）$10.00、暗黙的キャッシュ$0.10で提供され、2026年12月1日には$4.00 / $20.00 / $0.20へと倍増する。 [4]
- Googleの特化型APIラインナップには、WebRTC/WebSockets経由で48 kHzステレオ音声付きの操作可能な24 fpsインタラクティブワールドを配信するGenie 4、ネイティブ音声付きで最大15秒の動画を生成・編集するGemini Omni Flash、画像生成モデルのNano Banana 2.1、およびGemini Decision 1が含まれる。 [3][5]
- Gemini Developer APIはローリング10分間の支出レート制限を適用しており、Tier 1（月間上限$250）では$10、Tier 2（月間上限$2,000、累計支出$100以上が必要）およびTier 3（月間上限$20,000-$100,000以上、累計支出$1,000以上かつ30日経過が必要）では$200に制限されている。 [5]
- コンシューマー向けGoogle One AIプランはGemini 4モデルのティアに直接対応しており、Google AI Plus（400 GB）にはGemini 4 Hydrogen、Google AI Pro（5 TB、月間200 Colabコンピュートユニット、月間$10のCloudクレジット）にはGemini 4 Neon、Google AI Ultra（20 TB以上、月間2,000 Colabコンピュートユニット、月間$40のCloudクレジット）にはGemini 4 CarbonおよびProject Genieが含まれる。 [2]

## 年表

- 2023-12-19: Google DeepMindがGemini 1.0技術レポート（arXiv:2312.11805）を提出し、ネイティブマルチモーダルモデルファミリーを発表した。 [7]
- 2024-03-08: Google DeepMindがGemini 1.5技術レポート（arXiv:2403.05530）を提出し、数百万トークンのコンテキストにわたるマルチモーダル理解を実証した。 [8]
- 2025-07-07: Google DeepMindがGemini 2.5技術レポート（arXiv:2507.06261）を提出し、思考トークンとエージェント推論を進化させた。 [9]
- 2026-02-05: Alphabet Inc.が2025会計年度Form 10-Kにおいて、20億人超の7製品を含む5億人超のGoogle全15製品にGeminiが搭載されていることを報告した。 [1]
- 2026-11-18: Google DeepMindがGoogle AI StudioおよびGoogle Antigravityにおいて、Gemini 4 Carbon、Argon、HydrogenのラインナップとともにGemini 4 Neonをリリースした。 [10]

## 出典

1. Alphabet Inc. Form 10-K for the Fiscal Year Ended December 31, 2025 (CIK 0001652044). U.S. Securities and Exchange Commission (EDGAR). 公開 2026-02-05. https://www.sec.gov/Archives/edgar/data/1652044/000165204426000018/goog-20251231.htm (閲覧 2026-11-23; tier 1: government or public registry)
2. Google AI plans with Cloud Storage - Google One. Google. https://one.google.com/about/google-ai-plans/ (閲覧 2026-11-23; tier 3: official site)
3. Models - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/models?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
4. Gemini Developer API pricing - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/pricing?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
5. Rate limits - Gemini API | Google AI Studio. Google. https://aistudio.google.com/docs/rate-limits?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
6. Available regions for Google AI Studio and Gemini API. Google. https://aistudio.google.com/docs/available-regions?auto_signin=false (閲覧 2026-11-23; tier 3: official site)
7. Gemini: A Family of Highly Capable Multimodal Models (arXiv:2312.11805). arXiv / Gemini Team Google. 公開 2023-12-19. https://arxiv.org/abs/2312.11805 (閲覧 2026-11-23; tier 2: academic or news)
8. Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context (arXiv:2403.05530). arXiv / Gemini Team Google. 公開 2024-03-08. https://arxiv.org/abs/2403.05530 (閲覧 2026-11-23; tier 2: academic or news)
9. Gemini 2.5: Pushing the Frontier with Advanced Reasoning, Multimodality, Long Context, and Next Generation Agentic Capabilities (arXiv:2507.06261). arXiv / Google DeepMind. 公開 2025-07-07. https://arxiv.org/abs/2507.06261 (閲覧 2026-11-23; tier 2: academic or news)
10. Introducing Gemini 4 Neon. Google. 公開 2026-11-18. https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Google Gemini." 版 900ebdd7, 2026-11-23. https://mimirwiki.com/ja/wiki/google-gemini
