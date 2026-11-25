---
title: "Grok"
subtitle: "xAI（SpaceX Super Intelligence LLC）が開発した生成AIモデル群、開発者向けAPI、およびエージェント型アプリケーションスイート"
canonical_url: https://mimirwiki.com/ja/wiki/grok
language: ja
page_class: entity
revision_sha256: a379dc7512ec2ceb6251a6a9cdadf446b3b4e12cdb920b98085e67367ca2305b
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ja/wiki/grok.md
  txt: https://mimirwiki.com/ja/wiki/grok.txt
  json: https://mimirwiki.com/ja/wiki/grok.json
  jsonld: https://mimirwiki.com/ja/wiki/grok.jsonld
translations:
  en: https://mimirwiki.com/wiki/grok
  ko: https://mimirwiki.com/ko/wiki/grok
  zh: https://mimirwiki.com/zh/wiki/grok
  es: https://mimirwiki.com/es/wiki/grok
---

# Grok

> xAI（SpaceX Super Intelligence LLC）が開発したGrokは、3,140億パラメータのオープンウェイトMixture-of-Expertsモデル「Grok-1」（Apache 2.0）およびGrok-2（2024年）から、2026年後半のフラッグシップモデルGrok 4.7（`grok-4.7`）へと発展した。Grok 4.7は50万トークンのコンテキストウィンドウ、2026年5月の知識カットオフ、設定可能な暗号化推論機能を備え、API料金は入力100万トークンあたり2.00ドル、出力100万トークンあたり6.00ドルである。2026年10月12日、xAIはGrok、Grok Bot、Cursorコーディングエージェント、X Premiumを単一の週間共有AI利用枠に統合した「The X Subscription」（月額$0 Free、$8 Plus、$30 Premium、$100 Super、$200 Ultra）を開始した。

Grokは、xAI（2026年時点ではSpaceX Super Intelligence LLC / SpaceXSIとして運営）が開発した生成AIモデル群、開発者向けAPI、および対話・コーディングアプリケーション群であり、`grok.com`、モバイルアプリ、ソーシャルプラットフォームX、およびコーディング環境Cursorに統合されている。2026年後半時点で、フラッグシップの推論・コーディングモデルであるGrok 4.7（`grok-4.7`）を中核に、専用のVoice、Imagine画像生成、Imagine動画生成モデルを擁しており、開発者向けにはxAI Responses API経由で、一般消費者およびチーム向けには統合プラン「The X Subscription」を通じて提供されている。

**別名:** Grok, xAI, SpaceX Super Intelligence, Grok 4.7, The X Subscription, Grok-1

## 主要な事実

- **開発元および運営法人:** xAI / SpaceX Super Intelligence LLC（SpaceXSI）、サブスクリプション販売はX Subscription Corp. [4]
- **2026年フラッグシップモデル:** Grok 4.7（grok-4.7）：50万トークンコンテキスト、2026年5月知識カットオフ、入力$2.00 / 出力$6.00（100万トークンあたり） [2]
- **マルチモーダル・エージェント製品群:** Grok Chat、Grok Build、Grok Bot、Imagine（Image 2.0およびVideo 1.5）、Voice API（grok-voice-3.0）、Grokipedia [3]
- **The X Subscription（2026年10月12日）:** Grok、Grok Bot、Cursor、X Premiumを統合した単一プラン（Free $0、Plus $8、Premium $30、Super $100、Ultra $200） [4]
- **オープンウェイト公開モデル:** Grok-1（xai-org/grok-1）：3,140億パラメータ、8エキスパートMoE（トークンあたり2つが活性化）、64層、Apache 2.0ライセンス [7]

## ファクトシート

- **開発元:** xAI（SpaceX Super Intelligence LLC / SpaceXSI） [4]
- **フラッグシップモデル:** Grok 4.7（grok-4.7） [1]
- **コンテキストウィンドウ:** 500,000トークン（Grok 4.7）、8,192トークン（Grok-1オープンウェイト） [2]
- **知識カットオフ:** 2026年5月（Grok 4.7） [2]
- **Grok 4.7 API料金:** 入力$2.00 / 100万トークン、出力$6.00 / 100万トークン [1]
- **音声・メディアAPI料金:** STS $0.08/分、TTS $15/100万文字、STT $0.10-$0.20/時間、画像 $0.02/枚〜、動画 $0.02/秒〜 [1]
- **APIレート制限ティア:** Tier 0（$0）〜Tier 4（2026年1月1日以降の累計利用額$5,000以上）：Grok 4.5-4.7で最大500 RPSおよび100M TPM [3]
- **The X Subscription プラン:** Free（$0）、Plus（$8/月）、Premium（$30/月、4倍）、Super（$100/月、15倍）、Ultra（$200/月、50倍） [6]
- **クラウドパートナー基盤:** xAI API（api.x.ai/v1）、Google Cloud Vertex AI、Microsoft Foundry [1]
- **オープンウェイトライセンス:** Apache 2.0（Grok-1 314Bチェックポイント、github.com/xai-org/grok-1） [7]

## Grok-1およびGrok-2からSpaceX Super Intelligenceへの進化

Grokは、ソーシャルネットワークXと統合された対話型推論、コーディング支援、およびリアルタイム情報統合を提供するためにxAIによって開発された。[7][8] 初期世代において、xAIはオープンウェイトのGrok-1ベースチェックポイント（`github.com/xai-org/grok-1`および`huggingface.co/xai-org/grok-1`）を、リファレンス用のJAX推論コードとともにApache 2.0ライセンスで公開した。[7] Grok-1は3,140億パラメータのMixture-of-Experts（MoE）言語モデルであり、64層のTransformer、層あたり8エキスパート（トークンあたり2エキスパートを活性化）、埋め込み次元6,144、クエリアテンションヘッド48個およびキー・バリューヘッド8個、回転位置埋め込み（RoPE）、131,072トークンのSentencePiece語彙、アクティベーションシャーディングおよび8ビット量子化サポート、最大シーケンス長8,192トークンを備えている。[7]

2024年8月にxAIはGrok-2をリリースし、続いて2024年12月12日に3倍高速化したアップグレード版Grok-2（`grok-2-1212`および`grok-2-vision-1212`）を展開した。このリリースでは、Xプラットフォーム上での無料アクセスに加え、リアルタイムWeb検索、インライン出典引用、タイムラインの「Grokボタン」、自己回帰型フォトリアリスティック画像生成モデルAuroraが導入され、API料金は入力100万トークンあたり2ドル、出力100万トークンあたり10ドルに引き下げられた。[8]

2026年時点で、xAIの開発者向けドキュメント、ニュース発表、および料金ポータルは法人SpaceX Super Intelligence LLC（ブランド名SpaceXSI、ソーシャルハンドル`@SpaceXSI`および`@grok`）のもとで運営されており、消費者およびチーム向けの直接セルフサーブ型サブスクリプションはX Subscription Corp.が独占的に販売している。[1][4][5] 製品ポートフォリオもチャットにとどまらず、Grok Chat、Grok Build（エージェント型コーディング）、Grok Bot（自律型AIチームメイト）、Grok Imagine（画像・動画生成）、Grok Voice、およびGrokipediaを含む総合スイートへと拡張された。[3][4]

## Grok 4.7およびマルチモーダルモデルカタログ

2026年11月現在、Grok 4.7（`grok-4.7`）はGrokプラットフォームおよびxAI API全体におけるフラッグシップ基盤モデルであり、あらゆるテキスト、チャット、ソフトウェアエンジニアリングワークロードに推奨されている。[1][2] Grok 4.7は50万トークンのコンテキストウィンドウ、設定可能な推論労力（reasoning effort）、2026年5月の知識カットオフを備え、標準API料金は入力100万トークンあたり2.00ドル、出力100万トークンあたり6.00ドル（Grok-2の$2/$10と比較して出力コストを40%削減）である。[1][2][8]

Grok 4.7およびGrok 4.x APIラインナップの主な技術的仕様は以下の通りである。[2][3]

- **暗号化推論コンテンツ（Encrypted Reasoning Content）**：xAI Responses API（`POST https://api.x.ai/v1/responses`）において、`grok-4.7`はリクエストの`include`パラメータで明示的に指定されていない場合でも、ペイロード内に常に`reasoning.encrypted_content`を返す。[2]
- **柔軟なロール順序とパラメータ規則**：チャットモデルは会話コンテキスト内での`system`、`user`、`assistant`ロールの任意順序の配置をサポートしている。[2] `grok-4.20`以降のすべてのモデルでは、`logprobs`および`top_logprobs`は非サポートであり、指定してもエラーを出さず無視される。[2]
- **ビジョン入力の制約**：画像対応のGrokモデルは、1枚あたり最大20 MiBの`jpg`/`jpeg`および`png`ファイルを受け付け、トークンコンテキストウィンドウの範囲内であれば1リクエストあたりの画像枚数に上限はなく、画像とテキストプロンプトを任意の順序で混在させることができる。[2]
- **明示的なリアルタイムグラウンディング**：デフォルトでは、Grok APIモデルは2026年5月の学習カットオフ以降の最新事象にアクセスできず、呼び出し側がサーバーサイド検索ツール（Web Search、X Search、Collections RAG、Code Execution、またはRemote MCP Tools）を有効化する必要がある。[1][2]

2026年11月のレート制限および料金仕様に記載されているxAI APIカタログ全体では、以下のモデルファミリーが提供されている。[1][2][3]

| モデル / エンドポイント系統 | アクティブモデル識別子 | 料金 / 主な仕様 |
| --- | --- | --- |
| フラッグシップ言語・推論 | `grok-4.7`（最新）、`grok-4.6`、`grok-4.5`、`grok-4.3` | 500Kコンテキスト（`grok-4.7`）、入力$2.00 / 100万トークン、出力$6.00 / 100万トークン |
| エージェント・コーディング特化 | `grok-build-0.1`、`grok-4.20-multi-agent-0309`、`grok-4.20-0309-reasoning`、`grok-4.20-0309-non-reasoning` | Grok Buildのエージェント型コーディング、リファクタリング、マルチエージェントワークフローを駆動 |
| 画像生成（Imagine） | `grok-imagine-image-2.0`（Image 2.0）、`grok-imagine-image` | 1K / 2K生成、編集、マルチ画像編集（$0.02 / 枚〜） |
| 動画生成（Imagine） | `grok-imagine-video-1.5`（Video 1.5）、`grok-imagine-video-1.5-lite`、`grok-imagine-video` | 480p / 720p / 1080p（Super/Ultraでは最大15秒の1080p）、画像から動画、参照から動画、編集、延長（$0.02 / 秒〜） |
| 音声・オーディオAPI | `grok-voice-3.0`、Text to Speech（TTS）、Speech to Text（STT） | Speech-to-Speech（STS）：$0.08/分、TTS：$15.00/100万文字、STTバッチ：$0.10/時間、STTストリーミング：$0.20/時間 |

## xAI APIアーキテクチャ、クラウド統合、およびレート制限ティア

xAI開発者プラットフォームは、最新のResponses API（`https://api.x.ai/v1/responses`）、OpenAI互換RESTインターフェース、ネイティブgRPCベースの`xai_sdk` Pythonパッケージに加え、Vercel AI SDK（`@ai-sdk/xai`）、Google Cloud Vertex AI、Microsoft Foundryとの公式統合を提供している。[1][3] エンタープライズ向け高度API機能には、Prompt Caching、Context Compaction、Priority Processing、カスタムモデレーション制御、Batch API、Deferred Completions、非同期リクエスト、WebSocketモード、mTLS認証、リージョン別エンドポイント、出力透かし（Output Watermarking）が含まれる。[1][3]

すべてのxAI APIチームには、言語モデルでは1秒あたりリクエスト数（RPS）と1分あたりトークン数（TPM）、音声エンドポイントでは同時セッション数（CST）とRPSという2軸のモデル別レート制限が適用される。[3] 1秒間のバースト枯渇を防ぐため、チームの毎秒リクエスト上限は毎分予算から算出される（`RPM / 48`、最小2 RPS）。[3] すべてのプロンプトトークン（テキスト、画像、音声）、補完トークン、推論トークン、およびキャッシュ済みプロンプトトークンは、該当モデルのTPM上限に算入される。[3] レート制限ティアは2026年1月1日以降の累計API利用額に応じて自動的かつ永続的に解放され、降格することはない。[3]

| レート制限ティア | 累計利用額基準（2026年1月1日以降） | `grok-4.7` / `4.6` / `4.5`（RPS / TPM） | `grok-4.3` / `grok-build-0.1` / `4.20`（RPS / TPM） | `grok-4.20-multi-agent`（RPS / TPM） | `grok-imagine-image-2.0`（RPS） | `grok-imagine-video-1.5`（RPS） | `grok-voice-3.0`（CST） |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Tier 0 | $0（デフォルト） | 150 RPS / 50M TPM | 37 RPS / 10M TPM | 9 RPS / 2.5M TPM | 6 RPS | 10 RPS | 10 CST |
| Tier 1 | $50 | 172 RPS / 53M TPM | 50 RPS / 15M TPM | 12 RPS / 3.7M TPM | 12 RPS | 20 RPS | 20 CST |
| Tier 2 | $250 | 208 RPS / 60M TPM | 75 RPS / 25M TPM | 18 RPS / 6.2M TPM | 25 RPS | 39 RPS | 50 CST |
| Tier 3 | $1,000 | 312 RPS / 74M TPM | 125 RPS / 45M TPM | 31 RPS / 11M TPM | 50 RPS | 79 RPS | 100 CST |
| Tier 4 | $5,000 | 500 RPS / 100M TPM | 208 RPS / 85M TPM | 56 RPS / 21M TPM | 100 RPS | 158 RPS | 200 CST |
| Enterprise | カスタム（sales@x.ai経由） | カスタム | カスタム | カスタム | カスタム | カスタム | カスタム |

## The X Subscription：Grok、Grok Bot、Cursor、およびX Premiumの統合

2026年10月12日、xAIは4つの製品を単一の課金アカウントと週間共有AI利用枠に統合するグローバルサブスクリプションプラン「The X Subscription」を発表した。統合対象は、Grok（Chat、Voice、Imagine、Build）、Grok Bot（自律型AIチームメイト）、Cursor IDEおよびクラウドコーディングエージェント（OriginによるコードホスティングおよびBugbotによるAIコードレビューを含む）、ならびにX Premiumのソーシャルネットワーク特典である。[4][5][6]

各有料ティアでは、GrokのWeb/モバイルアプリ、X上のGrokタブ、Grok Bot、およびCursor全体で共有される毎週更新のGrokモデル利用枠が提供される。これにより、同等の従来型単独Cursorプランと比べて少なくとも2倍のGrokモデルによるコーディング利用量（Teamプランでは従来のCursor Teamsと比べて3倍のコーディング利用量）が利用可能である。[4][5] 既存の単独SuperGrok、Cursor、およびX Premiumの契約者は、従来プランを継続するか、未使用期間分の自動日割り払い戻しを受けてThe X Subscriptionへ移行するかを選択できる（ただしApple App Store経由のCursorサブスクリプションはApple側で直接解約する必要がある）。[4][6]

| プランティア | 月額料金 | 年額料金 | 週間共有AI利用枠 | Grok、Cursor、Xに含まれる主な機能 |
| --- | --- | --- | --- | --- |
| Free | $0 / 月 | $0 / 年 | 制限付き | 日次Grokアクセス、入門用Cursorコーディングエージェント枠、標準X機能、6.00% X Money APYおよび3%キャッシュバック（ダイレクトデポジット利用時） |
| Plus | $8 / 月 | $80 / 年（$7/月） | 基本（1倍） | Grok + Cursor共有枠、Grok Chat/Voice/Imagine/Build、Grok APIアクセス、X Premiumチェックマーク、タイムライン広告削減、クリエイターツール（Grok Botなし、Teams不可） |
| Premium | $30 / 月 | $300 / 年（$25/月） | Plusの4倍 | Grok Bot解放、最新Grokモデル、Cursor Cloudエージェントおよび自動化、Originコードホスティング、Bugbot AIコードレビュー、Xの大半の画面で広告非表示、6.00% X Money APY（従来のSuperGrok + Cursor Pro + X Premium+合算$90/月を代替） |
| Super | $100 / 月 | $1,000 / 年（$84/月） | Plusの15倍 | Premiumの全機能に加え、1080p 15秒動画生成、超高速応答、ピーク時間帯の優先アクセス |
| Ultra | $200 / 月 | $2,000 / 年（$167/月） | Plusの50倍 | Superの全機能に加え、パワーユーザー向けのPlus比50倍の週間AI利用枠 |
| Teams | $30 - $200 / シート / 月 | $300 - $2,000 / シート / 年 | シートあたりPlusの4倍〜50倍 | Premium/Super/Ultraシートの混在構成、一元請求、利用分析、SAML/OIDC SSO、SOC 2準拠、社内ルール・スキル・プラグイン向けチームマーケットプレイス |

有料プランにはGrok APIコンソールへのアクセスが含まれるものの、直接API呼び出しによるトークン消費は標準API料金で別途課金され、サブスクリプションの週間利用枠からは差し引かれない。[5] 同様に、Premium、Super、UltraプランではCursor内でGrok以外のサードパーティモデルを引き続き選択できるが、付属のGrok利用枠ではなく、プリペイドチャージおよびAdditional Usageクレジットを通じてAPI標準価格で別途課金される。[4][5][6]

## よくある質問

### Grok 4.7の仕様とAPI料金はどうなっていますか？

Grok 4.7（grok-4.7）は、2026年後半時点におけるxAIのフラッグシップ言語・コーディング・推論モデルです。50万トークンのコンテキストウィンドウ、設定可能な推論労力（Responses APIでは常にreasoning.encrypted_contentを返却）、2026年5月の知識カットオフ、およびJPEG/PNGファイル1枚あたり最大20 MiBの無制限画像入力に対応しています。標準API料金は、入力100万トークンあたり2.00ドル、出力100万トークンあたり6.00ドルです。 [2]

### 2026年10月に発表されたThe X Subscriptionには何が含まれますか？

2026年10月12日に導入されたThe X Subscriptionは、Grok（Chat、Voice、Imagine画像・動画生成、Grok Build）、Grok Bot AIチームメイト、Cursorコーディングエディタおよびクラウドエージェント（OriginコードホスティングおよびBugbot AIコードレビューを含む）、ならびにX Premiumを、週間共有AI利用枠を備えた1つのプランに統合したものです。ティアはFree（$0）、Plus（$8/月または$80/年）、Premium（$30/月または$300/年、Plusの4倍の利用枠で従来のSuperGrok・Cursor Pro・X Premium+合算月額$90を代替）、Super（$100/月または$1,000/年、Plusの15倍）、およびUltra（$200/月または$2,000/年、Plusの50倍）で構成されます。 [4]

### The X SubscriptionはCursor内のサードパーティモデルや直接Grok APIのトークン料金もカバーしますか？

いいえ。The X Subscriptionの週間共有利用枠が対象とするのは、Grokアプリ、X、Grok Bot（Premium以上）、およびCursorで使用するGrokモデルのみです。Cursor内のサードパーティモデルはPremium、Super、Ultraプランで引き続き利用できますが、プリペイドチャージ経由で最初のトークンからAPI標準価格にて別途課金されます。同様に、直接のGrok API呼び出しも標準のトークン単価で別途課金されます。 [6]

### xAI APIのレート制限ティアはどのように機能しますか？

xAI APIのレート制限は、1秒あたりリクエスト数（RPS：RPM / 48で算出、最小2）および1分あたりトークン数（TPM：プロンプト、補完、推論、キャッシュ済みトークンをすべて合算）の2軸でモデルごとに適用されます。ティアは2026年1月1日以降の累計利用額に応じて自動的かつ永続的に解放され、Tier 0（$0）、Tier 1（$50）、Tier 2（$250）、Tier 3（$1,000）、Tier 4（$5,000）の段階があります。Grok 4.5、4.6、および4.7の上限は、Tier 0の150 RPSおよび50M TPMから、Tier 4の500 RPSおよび100M TPMまで拡張されます。 [3]

## 引用できる文

- 2026年11月時点で、xAIのフラッグシップ言語モデルはGrok 4.7（grok-4.7）であり、50万トークンのコンテキストウィンドウ、2026年5月の知識カットオフ、Responses APIでの暗号化推論コンテンツの必須返却、および入力100万トークンあたり2.00ドル・出力100万トークンあたり6.00ドルの料金設定を備えている。 [1][2]
- xAIのオープンウェイト公開モデルGrok-1（xai-org/grok-1）は、Apache 2.0ライセンスで提供される3,140億パラメータのMixture-of-Expertsモデルであり、64層、層あたり8エキスパート（トークンあたり2つを使用）、埋め込みサイズ6,144、コンテキストウィンドウ8,192トークンを備えている。 [7]
- 2026年10月12日、xAI（SpaceX Super Intelligence LLC）はGrok、Grok Bot、Cursor、およびX Premiumを単一のサブスクリプションと週間共有AI利用枠に統合したThe X Subscriptionを開始し、Free（$0）、Plus（$8/月）、Premium（$30/月、Plusの4倍）、Super（$100/月、Plusの15倍）、Ultra（$200/月、Plusの50倍）の5ティアで提供している。 [4][5][6]
- xAI APIでは、レート制限ティアは2026年1月1日以降の累計利用額に基づいて永続的に拡張され、Tier 0（$0デフォルト：Grok 4.5/4.6/4.7で150 RPSおよび50M TPM）からTier 4（$5,000以上の利用額：Grok 4.5/4.6/4.7で500 RPSおよび100M TPM）まで上昇する。 [3]
- xAIのマルチモーダルAPIスイートには、Grok Voice API（Speech-to-Speech $0.08/分、TTS $15.00/100万文字、STTバッチ$0.10/時間およびストリーミング$0.20/時間）、Imagine Image 2.0（$0.02/枚〜）、およびImagine Video 1.5（480p、720p、1080p対応、$0.02/秒〜）が含まれる。 [1][2][3]

## 年表

- 2024-03: xAIが3,140億パラメータのオープンウェイトMixture-of-ExpertsモデルGrok-1のチェックポイントとJAXコードをApache 2.0ライセンスで公開した。 [7]
- 2024-12-12: xAIが高速化されたGrok-2（grok-2-1212およびgrok-2-vision-1212）を全Xユーザーに無料公開し、Aurora画像生成モデルを発表するとともにAPI料金を100万トークンあたり$2/$10に引き下げた。 [8]
- 2026-05: フラッグシップモデルGrok 4.7の知識カットオフ日。 [2]
- 2026-10-12: xAI（SpaceX Super Intelligence LLC）がGrok、Grok Bot、Cursor、およびX Premiumを単一プランと共有利用枠に統合するThe X Subscriptionを開始した。 [4]
- 2026-11-13: xAIがGrok 4.7、Grok Build 0.1、Imagine Image 2.0、Imagine Video 1.5、およびGrok Voice 3.0を対象とするAPIレート制限スケジュールを更新した。 [3]

## 出典

1. Grok API Documentation Overview | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). https://docs.x.ai/overview (閲覧 2026-11-23; tier 3: official site)
2. Grok Models & Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 公開 2026-09-21. https://docs.x.ai/developers/models (閲覧 2026-11-23; tier 3: official site)
3. Rate Limits | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 公開 2026-11-13. https://docs.x.ai/developers/rate-limits (閲覧 2026-11-23; tier 3: official site)
4. Introducing The X Subscription | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 公開 2026-10-12. https://x.ai/news/x-subscription (閲覧 2026-11-23; tier 3: official site)
5. Pricing: Compare Plans | SpaceXSI. xAI (SpaceX Super Intelligence LLC). https://x.ai/pricing (閲覧 2026-11-23; tier 3: official site)
6. The X Subscription Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). 公開 2026-10-11. https://docs.x.ai/x-subscription/pricing (閲覧 2026-11-23; tier 3: official site)
7. Grok-1 Open Release Repository and Model Specifications (xai-org/grok-1). xAI. https://raw.githubusercontent.com/xai-org/grok-1/main/README.md (閲覧 2026-11-23; tier 3: official site)
8. Bringing Grok to Everyone | SpaceXSI. xAI (SpaceX Super Intelligence LLC). 公開 2024-12-12. https://x.ai/news/grok-1212 (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Grok." 版 a379dc75, 2026-11-23. https://mimirwiki.com/ja/wiki/grok
