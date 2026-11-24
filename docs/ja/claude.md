---
title: "Claude"
subtitle: "Anthropic, PBCが開発したAIアシスタントおよび大規模言語モデル群"
canonical_url: https://mimirwiki.com/ja/wiki/claude
language: ja
page_class: entity
revision_sha256: be5423d343ddfdccd387ea8a999e52c138daf36382291468bf72fabfae285da0
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 14
alternates:
  md: https://mimirwiki.com/ja/wiki/claude.md
  txt: https://mimirwiki.com/ja/wiki/claude.txt
  json: https://mimirwiki.com/ja/wiki/claude.json
  jsonld: https://mimirwiki.com/ja/wiki/claude.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude
  ko: https://mimirwiki.com/ko/wiki/claude
  zh: https://mimirwiki.com/zh/wiki/claude
---

# Claude

> Claudeは、Anthropic, PBCが開発し2023年3月14日に初回公開されたAIアシスタントおよび大規模言語モデル群である。2026-11-23時点での最新モデルはFable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5であり、いずれも100万トークンのコンテキストウィンドウに対応する。Claudeはサブスクリプション、API、Claude Code、および各種クラウドプラットフォームを通じて利用できる。

Claudeは、米国カリフォルニア州サンフランシスコに本社を置くデラウェア州公益法人（Public Benefit Corporation）であるAnthropic, PBCが開発したAIアシスタントおよび大規模言語モデル（LLM）ファミリーである。Anthropicは2023年3月14日にチャットインターフェースおよび開発者向けAPIを通じてClaudeを一般公開し、その後ターミナルやIDEでのソフトウェア開発向けツールClaude Code、デスクトップワークフロー向けClaude Cowork、およびClaude Platform APIへと製品群を拡大した。2026-11-23時点での現行モデルラインナップはClaude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5、Claude Haiku 5.5の4モデルで構成され、各モデルとも100万トークンのコンテキストウィンドウと最大128,000出力トークンを提供する。ClaudeはFree、Pro、Max、Ultra、Team、Enterprise、Educationの各プランのほか、AnthropicのファーストパーティAPI、さらにAmazon Bedrock、Google Cloud、Microsoft Foundry上で提供されている。

**別名:** クロード, Claude AI, Claude.ai, Claude Platform

## 主要な事実

- **開発元:** Anthropic, PBC（カリフォルニア州サンフランシスコ） [1]
- **初回一般公開日:** 2023-03-14 [3]
- **最新モデル:** Claude Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5 (時点 2026-11-23) [4]
- **コンテキストウィンドウ:** 最新4モデルすべて100万トークン（最大出力128K） (時点 2026-11-23) [4]
- **個人向けサブスクリプションプラン:** Free（0ドル）、Pro（年額請求で月額17ドル、または月額20ドル）、Max（月額100ドル）、Ultra（月額200ドル） (時点 2026-11-23) [6]

## ファクトシート

- **開発元:** Anthropic, PBC（デラウェア州公益法人） [1]
- **初回一般公開日:** 2023-03-14（ClaudeおよびClaude Instant） [3]
- **モデル系列:** Haiku、Sonnet、Opus、Fable、Mythos (時点 2026-11-23) [4]
- **最新モデル:** Claude Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5 (時点 2026-11-23) [4]
- **コンテキストウィンドウと最大出力:** 入力1,000,000トークン、出力128,000トークン（最新モデル） (時点 2026-11-23) [4]
- **知識・学習データカットオフ:** 2026年6月（Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5） (時点 2026-11-23) [4]
- **API基本トークン料金:** 100万入力/出力トークンあたり0.10/0.50ドル（Haiku 5.5）〜8/40ドル（Fable 5.2） (時点 2026-11-23) [5]
- **プラットフォームおよびクライアント:** Web、デスクトップ、iOS、Android、Claude Code、Claude Platform API (時点 2026-11-23) [6]
- **クラウドプラットフォーム:** Amazon Bedrock、Claude Platform on AWS、Google Cloud、Microsoft Foundry (時点 2026-11-23) [4]
- **アライメント手法:** Constitutional AI（教師あり自己修正およびRLAIF） [2]
- **連携プロトコル:** モデルコンテキストプロトコル（MCP、2024-11-25オープンソース化） [11]
- **対応地域:** リスト記載の185か国・地域およびその属領（2026-11-12発効ポリシー） (時点 2026-11-23) [14]

## Claudeの概要、公開経緯、および製品ラインナップ

Claudeは、カリフォルニア州サンフランシスコ（548 Market Street, PMB 90375, San Francisco, California 94104）に主たる執行事務所を置くデラウェア州公益法人[Anthropic](https://mimirwiki.com/ja/wiki/anthropic), PBCによって開発されている。[1] 2026年11月17日に[SEC EDGAR](https://mimirwiki.com/ja/wiki/sec-edgar)へ提出されたForm S-1修正届出書第3号（Amendment No. 3）によれば、Anthropicは共同創業者であるDario Amodei（最高経営責任者）およびDaniela Amodei（社長）によって率いられている。[1] Anthropicは、Notion、Quora（Poe経由）、DuckDuckGo（DuckAssist向け）のほか、Juni Learning、Robin AI、AssemblyAIといった初期パートナーとのクローズドアルファテストを経て、2023年3月14日にClaudeを一般公開した。[3]

2023年3月の公開当時、Claudeはチャットインターフェースおよび開発者コンソールAPIを通じて、Claudeと、より軽量で低コストなClaude Instantの2バージョンで提供された。[3] Anthropicは、初回リリースが要約、検索、共同執筆、質問応答、コーディングなどのタスクに対応すると説明していた。[3]

2026-11-23時点において、Anthropicの製品概要ページではClaudeモデルを基盤とする幅広い製品群が掲載されており、Web・デスクトップ・iOS・Android向けClaudeチャットアプリ、Claude Code、Claude Cowork、ウェイトリスト制のリサーチプレビューであるClaude Duet、Claude Platform、Claude Tag、さらに専門向け製品のClaude SecurityおよびClaude Scienceが含まれる。[6][7] Claudeアプリケーション全般の記載機能には、Artifacts、Design、Docs、Slides、Data、SheetsおよびWhiteboards（ベータ）、Connectors、Plugins、Skills、Extensions、音声モード（Voice mode）、Web検索、Research、タスクスケジューリング、Claude in Chrome、Claude for Google Workspace、およびClaude for Microsoft 365がある。[6][7] 2026年9月、Anthropicはユーザーが1つの会話内でチャットでの問い合わせと多段階のデスクトップ作業を行き来できるよう、Claude CoworkとClaude.aiを単一アプリケーションへ統合する取り組みを開始した。[1]

## Claudeのモデルラインナップと仕様

Claudeモデルは、AnthropicによりModels API（`GET /v1/models`）の`line`フィールドで報告される5つのモデル系列（`haiku`、`sonnet`、`opus`、`fable`、`mythos`）に分類されている。[4] 2026-11-23時点において、Claude Platform Docsには現行ラインナップとしてClaude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5、およびClaude Haiku 5.5の4モデルが記載されている。[4] これら4モデルはいずれもテキストおよび画像入力を受け付けてテキスト出力を生成し、多言語処理、ビジョン、ツール使用、およびアダプティブシンキング（adaptive thinking）に対応する。[4]

| モデル | Claude API ID | コンテキストウィンドウ | 最大出力 | 思考モードとデフォルト努力水準 | 知識カットオフ | 最短廃止予定日 |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | `claude-fable-5-2` | 1Mトークン | 128Kトークン | アダプティブ（常時オン）、high | 2026年6月 | 2027年11月9日 |
| Claude Opus 5.5 | `claude-opus-5-5` | 1Mトークン | 128Kトークン | アダプティブ（常時オン）、medium | 2026年6月 | 2027年9月22日 |
| Claude Sonnet 5.5 | `claude-sonnet-5-5` | 1Mトークン | 128Kトークン | アダプティブ、high | 2026年6月 | 2027年9月28日 |
| Claude Haiku 5.5 | `claude-haiku-5-5` | 1Mトークン | 128Kトークン | アダプティブ、medium | 2026年6月 | 2027年10月7日 |

Claude Platform Docsにおいて、AnthropicはClaude Fable 5.2を高度な推論と長期的なエージェント作業向け、Claude Opus 5.5を一般ワークロードならびに長時間のエージェント型コーディングおよび知識業務向け、Claude Sonnet 5.5を速度と性能の両立向け、Claude Haiku 5.5を分類・抽出・ルーティングなど高スループットかつ低遅延が求められるタスク向けと位置づけている。[4] 4モデルすべてについて、信頼できる知識カットオフおよび学習データカットオフの双方とも2026年6月と記載されている。[4]

2026-11-23時点のClaude Platform Docsには、現行4モデルに加えて追加モデルおよび旧モデルとして、Claude Mythos 5.2、Claude Fable 5.1および5、Claude Mythos 5.1および5、Claude Opus 5・4.8・4.7・4.6・4.5・4.1・4、Claude Sonnet 5・4.6・4.5・4、およびClaude Haiku 4.5も掲載されている。[4] 旧モデルのうち、Claude Opus 4.5、Claude Sonnet 4.5、Claude Sonnet 4、およびClaude Haiku 4.5は200,000トークンのコンテキストウィンドウと最大64,000出力トークンを備え、Claude Opus 4.1およびClaude Opus 4は200,000トークンのコンテキストウィンドウと最大32,000出力トークンを備えている。[4]

開発者は`GET /v1/models`エンドポイントを通じてモデル仕様をプログラムから取得でき、ライフサイクル段階（`active`、`deprecated`、または`retired`）によるフィルタリングのほか、`max_input_tokens`、`max_tokens`、`line`、さらに`thinking.types.disabled`、`thinking.types.between_tools`、`server_tools`（Web検索およびコード実行）、プログラムによるツール呼び出しなどの設定を含む`capabilities`オブジェクトを取得できる。[4] AnthropicのForm S-1/A-3では、クリック・文字入力・アプリケーション操作を通じてグラフィカルユーザーインターフェースを観察・操作するコンピュータユース（computer use）や、単一応答内の連続したツール呼び出しの間に個別の推論ステップを挿入するインターリーブ思考（interleaved thinking）といったClaudeの機能も定義されている。[1]

## Claude Platform APIの料金体系と開発者向け機能

Claude PlatformにおけるClaude APIの利用料金は、基本入力、基本出力、プロンプトキャッシング、およびバッチ処理の各レートについて100万トークン（MTok）あたりの米ドル建てで計量される。[5] 2026-11-23時点において、Claude Platform Docsは現行4モデルに対して以下の料金を公開している。[5]

| モデル | 基本入力 | 基本出力 | キャッシュ書き込み（5分 / 1時間） | キャッシュヒット | バッチ入力 / 出力 |
| --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | $8 / MTok | $40 / MTok | $10 / $16 per MTok | $0.20 / MTok | $4 / $20 per MTok |
| Claude Opus 5.5 | $4 / MTok | $20 / MTok | $5 / $8 per MTok | $0.20 / MTok | $2 / $10 per MTok |
| Claude Sonnet 5.5 | $2 / MTok | $10 / MTok | $2.50 / $4 per MTok | $0.10 / MTok | $1 / $5 per MTok |
| Claude Haiku 5.5（100Kトークン以下のプロンプト） | $0.10 / MTok | $0.50 / MTok | $0.125 / $0.20 per MTok | $0.01 / MTok | $0.05 / $0.25 per MTok |
| Claude Haiku 5.5（100Kトークン超のプロンプト） | $0.50 / MTok | $2.50 / MTok | $0.625 / $1 per MTok | $0.05 / MTok | $0.25 / $1.25 per MTok |

プロンプトキャッシングでは基本入力単価に固定倍率が適用され、5分間のキャッシュ書き込みが1.25倍、1時間のキャッシュ書き込みが2倍となる一方、キャッシュ読み取り倍率はFable 5.2・Mythos 5.2・Fable 5.1・Mythos 5.1で0.025倍、Opus 5.5およびSonnet 5.5で0.05倍、その他のすべてのモデルで0.1倍である。[5] Batch APIは非同期リクエストに対して入力・出力トークンともに50%の割引を提供する。[5] Fastモードは対応モデルで標準料金の2倍（Fable 5.2およびMythos 5.2は$16/$80 per MTok、Opus 5.5は$8/$40 per MTok、Opus 5およびOpus 4.8は$10/$50 per MTok）で毎秒の出力トークン速度を最大2.5倍に引き上げるが、Batch APIとの併用はできない。[5]

Claude 4.6以降のモデルでは、`inference_geo: "us"`パラメータにより米国限定の推論を選択すると、ファーストパーティAPI、Claude Platform on AWS、Anthropic管理型のGoogle Cloudデプロイメント、およびMicrosoft FoundryにおけるAzure US Data Zone Standardデプロイメントのすべてのトークン料金区分に1.1倍の倍率が適用される。[5] Anthropicのドキュメントによれば、Claude 4.7以降のモデル（およびClaude Mythos Preview）は新しいトークナイザーを採用しており、Claude Sonnet 4.6以前のモデルと比較して同一テキストから約30%多くのトークンを生成する。[5] 2026-11-23時点で掲載されている追加モデルの100万トークンあたり基本入力・出力料金は、Claude Mythos 5.2が$8/$40、Fable 5.1・Fable 5・Mythos 5.1・Mythos 5が$10/$50、Opus 5からOpus 4.5までが$5/$25、Opus 4.1およびOpus 4が$15/$75、Sonnet 5が$2/$10、Sonnet 4.6からSonnet 4までが$3/$15、Haiku 4.5が$1/$5である。[5]

トークン料金に加え、2026-11-23時点の`claude.com/pricing`にはClaude Platformの3機能に対する個別料金が記載されており、Managed Agentsがアクティブ実行時間1セッション時間あたり0.08ドル（標準トークン料金は別途）、Web検索が1,000回あたり10ドル（トークン消費を除く）、サンドボックス化されたPythonコード実行が1組織あたり1日50時間まで無料でその後1コンテナ1時間あたり0.05ドルとなっている。[6]

2026-11-23時点において、Claude APIは組織単位の支出上限および1分あたりのリクエスト数（RPM）、1分あたりの入力トークン数（ITPM）、1分あたりの出力トークン数（OTPM）で計測されるレート制限を適用しており、超過時にはHTTP 429レスポンスを返す。[12] 標準利用ティア別の月間支出上限はStartが500米ドル、Buildが1,000米ドル、Scaleが200,000米ドルであり、新規アカウントはEvaluationティアから開始される場合がある。デフォルトのITPM制限にはキャッシュされていない`input_tokens`と`cache_creation_input_tokens`のみが算入され、`cache_read_input_tokens`は除外される。またManaged Agentsでは作成エンドポイントに300 RPM、読み取りエンドポイントに1,200 RPMの制限が課される。[12] 2026-11-23時点のファイアウォール許可リスト用として、Anthropicは固定インバウンドIP範囲に`160.79.104.0/23`、`153.61.224.0/22`、およびIPv6の`2607:6bc0::/48`を、MCPツール呼び出し・Web検索・Webフェッチなどのアウトバウンドリクエスト用IPv4範囲に`160.79.104.0/21`および`153.61.208.0/20`を公開している。[13]

## Claudeの個人・チーム・エンタープライズ・教育向けプラン

Claudeは、`claude.com/pricing`で公開されているサブスクリプションプランを通じて、個人ユーザー、チーム、大企業、および大学向けに提供されている。[6] 2026-11-23時点の料金ページには、個人向け4プラン（Free、Pro、Max、Ultra）、StandardおよびPremiumシートを備えるTeamプラン、セルフサーブおよび営業支援型で提供されるEnterpriseプラン、そして大学全体向けのEducationプランが掲載されている。[6]

| プラン | 記載料金（USD） | 請求条件 | 記載されている利用枠および機能 |
| --- | --- | --- | --- |
| Free | $0 | 無料 | 5時間および週間の制限付き利用、SonnetおよびHaikuモデル、Web・デスクトップ・iOS・Androidチャット、Artifacts、Design、Slides、Docs、Web検索、コード実行、音声モード、最大5件のProjects |
| Pro | 年額請求で月額$17（年$200一括払い）または月額$20 | 月額または年額 | 基準（1倍）の5時間および週間利用枠、Opusへのアクセス、利用クレジットによるFable、Claude Code、Claude Science、Claude Data、SheetsおよびWhiteboards（ベータ）、Research、タスクスケジューリング、Claude in Chrome、Microsoft 365およびOutlookを追加 |
| Max | 月額$100 | 月額 | Proの5倍の5時間および週間利用枠、週間上限の最大50%までFable利用可、月額$100分のAPIクレジット、新機能への早期アクセス、高負荷時の優先アクセス |
| Ultra | 月額$200 | 月額 | 認証済みアカウントは5時間制限なし、Proの10倍の週間利用枠、週間上限の最大50%までFable利用可、月額$200分のAPIクレジット、新機能への早期アクセス、高負荷時の優先アクセス |
| Team | Standard：年額請求で$20/シート/月（月額$25）、Premium：年額請求で$100/シート/月（月額$125） | 月額または年額（2〜150シート） | シート種別の混在が可能、PremiumはStandardの5倍の利用枠および週間上限の最大50%までFable利用可、Claude Cowork、Claude Tag、エンタープライズ検索、プロジェクト共有、SSO、ドメイン検証、一元請求、利用状況分析、月額最大$500の共有APIクレジットを追加 |
| Enterprise | 基本料金$20/シート/月＋APIレートによる従量課金 | 年額（最低20シート） | 組織・ユーザー支出上限、ロールベースアクセス制御、SCIM、監査ログ、Compliance API、カスタムデータ保持設定、ドメインキャプチャ、ネットワークレベルのアクセス制御、IP許可リスト、HIPAA対応オプション、推論フック（inference hooks）、Claude Security（ベータ）を追加 |

個人向けプラン（Free、Pro、Max、Ultra）ではモデル学習がオプトアウト方式と記載されているのに対し、TeamおよびEnterpriseプランでは顧客コンテンツがデフォルトでモデル学習から除外される。[6] すべてのプランでモデルに応じて最大100万トークンのコンテキストウィンドウが記載されており、利用上限は選択モデル、チャットの長さ、およびファイルサイズによって変動する。[6]

営業支援型（sales-assisted）のEnterpriseプランでは、セルフサーブ型Enterpriseにはない選択肢として、AWS Marketplaceでの提供、コンサルテーション、コミット済み支出額に応じた段階的インセンティブ、トライアル、一定支出基準を満たす場合のカスタマーサクセス支援、および掛け払い条件（net terms）付きの請求書払いが追加される。[6] Anthropicはまた、大学の学生・教員・職員を対象に割引料金、学術研究・学習モード、および専用APIクレジットを提供するEducationプランも用意しているが、料金は公開されていない。[6]

2026年11月12日発効のAnthropicの対応地域ポリシー（Supported Regions Policy）に基づき、Claudeアプリケーション（Claude.ai、Claude Code、およびCowork）、Claude API、ならびにクラウドプラットフォームおよび認定リセラー経由で提供されるClaudeモデルは、リストに記載された185か国・地域およびその属領・保護領においてのみ利用可能である。[14] 同ポリシーは、未記載地域に物理的に所在する個人、および未記載地域で設立・本社所在・過半数所有または支配されている法人によるアクセスを除外している。[14]

## Claude Code、Claude Cowork、およびクラウドプラットフォーム提供状況

Claude Codeは、2025年2月にリサーチプレビューとして初めて提供されたAnthropicのエージェント型コーディングツールである。[1][8] AnthropicのForm S-1/A-3および公式GitHubリポジトリ（`anthropics/claude-code`）によれば、Claude Codeはターミナル、IDE、またはGitHub上の`@claude`メンションを通じて動作し、永続的なローカル環境またはサンドボックス化されたクラウド実行環境において自然言語コマンドでコードベースの調査、計画、記述、テスト、デバッグ、およびGitワークフローの管理を実行する。[1][8] AnthropicのForm S-1/A-3は、NASAのエンジニアが火星探査車パーサヴィアランス（Perseverance）のナビゲーションコマンドを計画・記述するためにClaude Codeを使用したことを記している。[1]

2026-11-23時点において、GitHub上の公開リポジトリ`anthropics/claude-code`はスター数156.8k、フォーク数25.1k、コミット数1,110件を記録している。[8] 2026-11-23時点のリポジトリREADMEに記載されているインストール方法は、macOSおよびLinux向けのシェルスクリプト（`curl -fsSL https://claude.ai/install.sh | bash`）およびHomebrew Cask（`brew install --cask claude-code`）、Windows向けのPowerShellスクリプト（`irm https://claude.ai/install.ps1 | iex`）およびWinGet（`winget install Anthropic.ClaudeCode`）であり、npm（`@anthropic-ai/claude-code`）経由のインストールは非推奨（deprecated）とされている。[8] このエージェント型アーキテクチャをデスクトップ上の知識業務へ拡張する形で、Anthropicは2026年1月にファイルの読み取り、アプリケーション操作、および多段階ワークフローの実行を行うClaude Coworkをリサーチプレビューとして公開し、2026年9月からClaude CoworkとClaude.aiの統合を開始した。[1]

AnthropicのファーストパーティAPIに加え、Claudeモデルは主要クラウドプラットフォームを通じても提供されている。[4][5] Amazon Web Servicesでは、Amazon Bedrock（Claude Fable 5.2、Opus 5.5、Sonnet 5.5、Haiku 5.5などの最新リリースを掲載し、最大8時間稼働する自律型エージェント向けのAmazon Bedrock AgentCoreと連携）およびClaude Platform on AWSを通じて利用できる。[4][5][9] Google Cloudでは、Gemini Enterprise Agent Platform上のModel Gardenを通じてGoogle管理型およびAnthropic管理型の双方のデプロイメントで提供されており、2026-11-23時点でFable 5〜5.2、Opus 4.5〜5.5、Sonnet 4.5〜5.5、およびHaiku 4.5と5.5をカバーしている。[4][5][10] また、Azure上でもMicrosoft Foundryを通じてClaudeモデルが提供されている。[4][5]

2026-11-23時点におけるクラウド課金モデルは提供チャネルによって異なる。[5] パートナー運営プラットフォーム（Amazon BedrockおよびGoogle Cloud上のGoogle管理型Claude Models）ではクラウド事業者が顧客へ直接請求し、Claude 4.5以降のモデルにおいてリージョンまたはマルチリージョンエンドポイントを利用する場合はグローバルエンドポイントに対し10%の割増料金が課される。[5] Anthropic運営のマーケットプレイス型プラットフォーム（AWS Marketplace経由のClaude Platform on AWS、およびAzure Marketplace経由のMicrosoft Foundry上のClaude）では、Anthropicが標準レートでトークン使用量を米ドル換算した上で、1 CCUあたり0.01米ドルでClaude Consumption Units（CCU）に変換し、CCUを毎時報告して月末後払いで請求する。[5]

## Constitutional AIによるClaudeの学習とモデルコンテキストプロトコル対応

Claudeモデルは、AnthropicのYuntao Baiおよび50名の共著者が2022年12月15日にarXivへ提出した論文「Constitutional AI: Harmlessness from AI Feedback」で提唱された学習手法であるConstitutional AIを用いてアライメントされている。[2][9] この手法では、明文化された規則や原則のリストを通じて人間の監督が与えられ、学習は2段階で実施される。[2] 教師あり学習段階では、初期モデルが出力を生成し、明文化された原則に照らして自らの出力を批評・修正した上で、修正後の応答データを用いてファインチューニングされる。[2] 続く強化学習段階はAIフィードバックによる強化学習（Reinforcement Learning from AI Feedback、RLAIF）と呼ばれ、AIモデルがサンプリングされた応答ペアを評価して選好データセットを構築し、そのデータセットで訓練した選好モデルを強化学習の報酬シグナルとして使用する。[2] 両段階とも思考の連鎖（chain-of-thought）推論を活用でき、有害なクエリに応答する際にアシスタントが拒否理由を説明できるようにする。[2]

2026年11月17日提出のAnthropicのForm S-1/A-3において、Constitutional AIは「Claudeの憲法（Claude's constitution）」と呼ばれる明文化された原則群に基づいてモデルを訓練する手法と定義されており、これらの原則は「広く安全であること（broadly safe）」「広く倫理的であること（broadly ethical）」「Anthropicのガイドラインに準拠すること」「真に有益であること（genuinely helpful）」の4つの優先事項で構成されている。[1] このプロセスを通じて、モデルは監査可能な明文化された原則に照らし、自身の応答を評価・批評・修正する。[1]

Claudeはまた、AnthropicのDavid Soria ParraおよびJustin Spahr-Summersが開発し2024年11月25日にオープンソース化したオープン標準である[モデルコンテキストプロトコル](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）を通じて外部ツールおよびデータシステムと接続する。[11] MCPは、データソースがMCPサーバーとしてアクセスを公開し、AIアプリケーションがMCPクライアントとして双方向接続を維持するクライアント・サーバー型アーキテクチャを定義している。[11] 公開時にAnthropicはMCPの仕様とSDKを公開し、Claude.aiの全プラン向けClaude DesktopアプリケーションにローカルMCPサーバーサポートを追加するとともに、Google Drive、Slack、GitHub、Git、Postgres、およびPuppeteer向けのオープンソース事前構築MCPサーバーを公開した。[11] Anthropicの発表では、MCP統合の初期採用企業としてBlockおよびApolloが挙げられ、プロトコルに対応する開発者ツール企業としてZed、Replit、Codeium、およびSourcegraphが紹介された。[11]

## よくある質問

### 2026-11-23時点での最新のClaudeモデルは何ですか？

2026-11-23時点において、Claude Platform Docsには現行ラインナップとしてClaude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5、Claude Haiku 5.5の4モデルが掲載されています。4モデルすべてが100万トークンのコンテキストウィンドウ、最大128,000出力トークン、アダプティブシンキング（adaptive thinking）、ビジョン、ツール使用、および2026年6月の知識カットオフを備えています。 [4]

### Claudeのサブスクリプションプランの料金はいくらですか？

2026-11-23時点において、Claudeの個人向けプランはFree（0ドル）、Pro（年額200ドルの一括払いで月額17ドル、または月額請求で20ドル）、Max（月額100ドル）、Ultra（月額200ドル）の4段階です。2〜150シート向けのTeamプランでは、Standardシートが年額請求で1シートあたり月額20ドル（月額請求25ドル）、Premiumシートが年額請求で月額100ドル（月額請求125ドル）と記載されています。Enterpriseプランは最低20シートの年額請求で1シートあたり月額20ドルからとなり、加えてAPIレートに基づく従量課金が適用されます。 [6]

### Claude APIのトークン料金はどのようになっていますか？

2026-11-23時点において、Claude APIの100万入力・出力トークンあたりの基本料金は、Claude Fable 5.2が8ドルおよび40ドル、Claude Opus 5.5が4ドルおよび20ドル、Claude Sonnet 5.5が2ドルおよび10ドルです。Claude Haiku 5.5は、100,000トークン以下のプロンプトでは100万トークンあたり入力0.10ドル・出力0.50ドル、100,000トークンを超えるプロンプトでは入力0.50ドル・出力2.50ドルとなっています。Batch APIを利用すると、入力・出力トークン料金の両方に50%の割引が適用されます。 [5]

### Claude Codeとは何ですか？またどのプランに含まれていますか？

Claude Codeは、2025年2月にリサーチプレビューとして公開されたAnthropicのエージェント型コーディングツールです。ターミナル、IDE、またはGitHub上の@claudeメンションを通じて動作し、コードの計画、記述、テスト、デバッグやGitワークフローの管理を行います。2026-11-23時点において、Claude CodeはPro、Max、Ultra、Team、およびEnterpriseプランに含まれており、Freeプランには含まれていません。 [1][6][8]

### どのクラウドプラットフォームでClaudeモデルが提供されていますか？

2026-11-23時点において、ClaudeモデルはAmazon Web ServicesではAmazon BedrockおよびClaude Platform on AWS、Google CloudではGemini Enterprise Agent Platform上のModel Garden（Google管理型およびAnthropic管理型デプロイメント）、AzureではMicrosoft Foundryを通じて提供されています。Amazon BedrockおよびGoogle管理型のGoogle Cloudデプロイメントでは、Claude 4.5以降のモデルのリージョンまたはマルチリージョンエンドポイントに対して、グローバルエンドポイントより10%の割増料金が適用されます。 [4][5][9][10]

### Constitutional AIとモデルコンテキストプロトコルはClaudeとどのように関係していますか？

Constitutional AIは、2022年12月にAnthropicの研究チームが発表した学習手法であり、教師あり学習とAIフィードバックによる強化学習（RLAIF）を通じて、明文化された原則に基づきClaudeモデルが自身の出力を評価・批評・修正するよう訓練します。モデルコンテキストプロトコル（MCP）は、2024年11月25日にAnthropicがオープンソース化したクライアント・サーバー型のオープン標準であり、Claude Desktopを含むClaudeアプリケーションと外部データソースやツールを接続します。 [1][2][11]

## 引用できる文

- Anthropic, PBCは2023年3月14日、チャットインターフェースおよび開発者向けAPIを通じてClaudeとClaude Instantを一般公開した。 [3]
- 2026-11-23時点における最新のClaudeモデルラインナップは、Claude Fable 5.2、Claude Opus 5.5、Claude Sonnet 5.5、Claude Haiku 5.5の4モデルであり、いずれも100万トークンのコンテキストウィンドウと最大128,000出力トークンを備えている。 [4]
- 2026-11-23時点におけるClaude APIの標準料金は、100万入力・出力トークンあたりFable 5.2が8ドルおよび40ドル、Opus 5.5が4ドルおよび20ドル、Sonnet 5.5が2ドルおよび10ドルであり、Haiku 5.5は100,000トークン以下のプロンプトに対して0.10ドルおよび0.50ドルである。 [5]
- 2026-11-23時点におけるClaudeの個人向けサブスクリプションプランは、Freeが0ドル、Proが年額請求で月額17ドル（月額請求で20ドル）、Maxが月額100ドル、Ultraが月額200ドルである。 [6]
- Anthropicは2025年2月にClaude Codeを、2026年1月にClaude Coworkをそれぞれリサーチプレビューとして公開した。 [1]
- 2026-11-23時点において、ClaudeモデルはAmazon Bedrock、Claude Platform on AWS、Google Cloud、およびMicrosoft Foundryで利用可能である。 [4][5][9][10]
- Anthropicの研究チームは2022年12月15日、教師あり自己修正とAIフィードバックによる強化学習（RLAIF）を解説したConstitutional AIの論文をarXivに提出した。 [2]
- Anthropicは2024年11月25日、モデルコンテキストプロトコル（MCP）の仕様、SDK、およびClaude Desktop向けのローカルサーバーサポートをオープンソース化した。 [11]

## 年表

- 2022-12-15: AnthropicのYuntao Baiおよび50名の共著者が論文「Constitutional AI: Harmlessness from AI Feedback」をarXivに提出した。 [2]
- 2023-03-14: Anthropicが初期パートナーとのクローズドアルファテストを経て、チャットインターフェースおよび開発者向けAPIでClaudeとClaude Instantを一般公開した。 [3]
- 2024-11-25: Anthropicがモデルコンテキストプロトコル（MCP）をオープンソース化し、仕様、SDK、事前構築サーバー、およびClaude DesktopでのローカルMCPサポートを公開した。 [11]
- 2025-02: AnthropicがコーディングエージェントClaude Codeをリサーチプレビューとして公開した。 [1]
- 2026-01: Anthropicが多段階のデスクトップワークフロー向けツールClaude Coworkをリサーチプレビューとして公開した。 [1]
- 2026-09: AnthropicがClaude CoworkとClaude.aiを統合アプリケーションへと一本化する作業を開始した。 [1]
- 2026-11-17: Anthropic, PBCが米国証券取引委員会（SEC）にForm S-1登録届出書の修正届出書第3号（S-1/A-3）を提出した。 [1]

## 出典

1. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 公開 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (閲覧 2026-11-23; tier 1: government or public registry)
2. [2212.08073] Constitutional AI: Harmlessness from AI Feedback. arXiv (Bai et al., Anthropic). 公開 2022-12-15. https://arxiv.org/abs/2212.08073 (閲覧 2026-11-23; tier 2: academic or news)
3. Introducing Claude \ Anthropic. Anthropic. 公開 2023-03-14. https://www.anthropic.com/news/introducing-claude (閲覧 2026-11-23; tier 3: official site)
4. Models overview - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/models/overview (閲覧 2026-11-23; tier 3: official site)
5. Pricing - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/about-claude/pricing (閲覧 2026-11-23; tier 3: official site)
6. Plans & pricing | Claude by Anthropic. Anthropic. https://claude.com/pricing (閲覧 2026-11-23; tier 3: official site)
7. Claude | The AI assistant for work. Anthropic. https://claude.com/product/overview (閲覧 2026-11-23; tier 3: official site)
8. GitHub - anthropics/claude-code: Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands. · GitHub. Anthropic (GitHub). https://github.com/anthropics/claude-code (閲覧 2026-11-23; tier 3: official site)
9. Claude by Anthropic - Models in Amazon Bedrock - AWS. Amazon Web Services. https://aws.amazon.com/bedrock/anthropic/ (閲覧 2026-11-23; tier 3: official site)
10. Anthropic's Claude on Google Cloud models | Gemini Enterprise Agent Platform | Google Cloud Documentation. Google Cloud. https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/partner-models/claude (閲覧 2026-11-23; tier 3: official site)
11. Introducing the Model Context Protocol \ Anthropic. Anthropic. 公開 2024-11-25. https://www.anthropic.com/news/model-context-protocol (閲覧 2026-11-23; tier 3: official site)
12. Rate limits - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/rate-limits (閲覧 2026-11-23; tier 3: official site)
13. IP addresses - Claude Platform Docs. Anthropic. https://platform.claude.com/docs/en/api/ip-addresses (閲覧 2026-11-23; tier 3: official site)
14. Supported Regions Policy \ Anthropic. Anthropic. 公開 2026-11-12. https://www.anthropic.com/supported-countries (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Claude." 版 be5423d3, 2026-11-23. https://mimirwiki.com/ja/wiki/claude
