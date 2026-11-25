---
title: "Cursor"
subtitle: "Anysphere, Inc.が開発しThe X Subscriptionに統合されたAIコーディングエージェントおよびソフトウェア開発環境"
canonical_url: https://mimirwiki.com/ja/wiki/cursor
language: ja
page_class: entity
revision_sha256: 15fbd5a46bb988ed6dc6ea809ad889f586e30282269e7010f1da27d8756bef03
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ja/wiki/cursor.md
  txt: https://mimirwiki.com/ja/wiki/cursor.txt
  json: https://mimirwiki.com/ja/wiki/cursor.json
  jsonld: https://mimirwiki.com/ja/wiki/cursor.jsonld
translations:
  en: https://mimirwiki.com/wiki/cursor
  ko: https://mimirwiki.com/ko/wiki/cursor
  zh: https://mimirwiki.com/zh/wiki/cursor
---

# Cursor

> Cursorは、2022年設立のAnysphere, Inc.が開発したAIコーディングエージェントおよびソフトウェア開発環境である。2026年6月、SpaceXは600億ドル規模の株式交換取引でCursorを買収することに合意した。2026-11-23時点で、CursorはThe X Subscriptionを通じて月額0ドルから200ドルで販売されており、Agent、Tab補完、Cloud Agents、Rules、Skills、MCP、CLI、および複数プロバイダーのモデルに対応している。

Cursorは、コードベースの理解、機能の設計と実装、デバッグ、およびコード変更のレビューを目的としてAnysphere, Inc.が開発したAIコーディングエージェントおよびソフトウェア開発環境である。2022年にAnysphereとして設立された同スタートアップは、SpaceXによるxAIとの合併に続き、2026年6月に600億ドル規模の株式交換取引でSpaceXに買収されることに合意した。2026-11-23時点で、CursorはX Subscription Corp.を通じてThe X Subscriptionの一部として提供されており、Free、Plus（月額8ドル）、Premium（月額30ドル）、Super（月額100ドル）、Ultra（月額200ドル）、Teams（1シートあたり月額30ドルから200ドル）、およびカスタムのEnterpriseプランを展開する一方、既存契約者向けのレガシーCursorプランも継続している。Cursorは統合デスクトップIDE、専用のAgents Window、コマンドラインインターフェース（CLI）、ウェブ、およびiOSで動作し、自社モデルのGrokおよびComposerに加え、OpenAI、Anthropic、Googleのサードパーティモデルに対応している。

**別名:** Cursor IDE, Cursor エディタ, Anysphere Cursor

## 主要な事実

- **開発元:** Anysphere, Inc. [9]
- **SpaceXによる買収合意:** 株式600億ドル（2026-06-16報道） [1]
- **個人向けプラン料金:** Free（0ドル）、Plus（月額8ドル）、Premium（月額30ドル）、Super（月額100ドル）、Ultra（月額200ドル） (時点 2026-11-23) [5]
- **Teamsプラン料金:** 1シートあたり月額30ドル、100ドル、または200ドル (時点 2026-11-23) [5]
- **セキュリティ認証:** SOC 2 Type II、ISO/IEC 27001:2022、ISO/IEC 42001:2023、AIUC-1 (時点 2026-11-23) [8]

## ファクトシート

- **開発元:** Anysphere, Inc. [9]
- **設立:** 2022年（Anysphereとして） [1]
- **買収合意:** SpaceX、株式600億ドル（2026-06-16報道、2026年第3四半期完了予定） [1]
- **サブスクリプション販売元:** X Subscription Corp.（The X Subscription） (時点 2026-11-23) [4]
- **対応サーフェス:** エディタ、Agents Window、CLI、Cursor SDK、iOSアプリ (時点 2026-11-23) [6]
- **カスタマイズ機能:** Plugins、Rules、Skills、Subagents、Hooks、MCP (時点 2026-11-23) [3]
- **標準搭載Cursorモデル:** Grok 4.7、Grok 4.6、Grok 4.5、Composer 2.5 (時点 2026-11-23) [5]
- **個人向けプラン:** Free（0ドル）、Plus（月額8ドル）、Premium（月額30ドル）、Super（月額100ドル）、Ultra（月額200ドル） (時点 2026-11-23) [5]
- **Teams・Enterprise:** Teams（1シートあたり月額30ドル、100ドル、または200ドル）、Enterprise（個別見積もり） (時点 2026-11-23) [5]
- **報道ARR（2025年6月）:** 5億ドル超（BloombergおよびTechCrunch報道） (時点 2025-06-05) [2]
- **セキュリティ認証:** AIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023、SOC 2 Type II (時点 2026-11-23) [8]
- **公式サイト:** cursor.com [9]

## Cursorの製品機能、カスタマイズ、インターフェース

Cursorは、Anysphere, Inc.の公式ドキュメントにおいて、リポジトリの追跡と理解、Plan Modeを用いた機能のスコープ定義と実装、バグの再現と修正、マージ前の差分検証とチェック実行、および外部開発ツールとの連携などに使う、ソフトウェア構築のためのコーディングエージェントとして説明されている。[3] Freeプランから、Cursor独自モデルを用いたAgent、Chat、およびTab補完への限定的なアクセスが提供される。[6]

CursorのAgentインターフェースは、デスクトップIDE、専用のAgents Window、ウェブクライアント、Cursor for iOS、およびコマンドラインインターフェース（CLI）を横断して動作する。[3][6][7] 2026-11-23時点で、AgentドキュメントはProjects、Agent Review、Planning、Prompting、Voice Chat、Debugging、Design Mode、Tools、およびSecurityを網羅しており、CLIドキュメントはShell Mode、ACP、およびHeadlessまたはCI実行を扱っている。[3] また、CursorはTypeScript、Python、およびBridge連携向けのCursor SDKも公開している。[3]

Cursorはワークフローのカスタマイズ機構を、Plugins、Rules、Skills、Subagents、Hooks、および[モデルコンテキストプロトコル](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）サーバーの6つに整理して文書化している。[3] TeamsおよびEnterpriseプランでは、社内向けのルール、スキル、プラグインを配布するためのチームマーケットプレイスも提供される。[4][5]

Cursorのドキュメントの連携（Integrations）の項目には、GitHub、GitLab、Azure DevOps、Bitbucket、JetBrains、Xcode、Slack、Microsoft Teams、Jira、Linear、Notion、Tailscale、およびDeeplinksが挙げられている。[3]

## Cursor Cloud Agents、Origin、Agent SDK、Voice Chat

Cursorは、Premium以上のサブスクリプションプランでCloud Agents、Automations、Originコードホスティング、およびBugbot AIコードレビューを提供している。[4][5] 2026-11-23時点で、Cloud Agentsのドキュメントは環境セットアップ、ビルド、アプリ、自動化、Bugbot、セキュリティレビュー、脆弱性修正、プルリクエストのルーティングと承認、ロールアウト、モバイルアクセス、セルフホストマシン、およびAPIを網羅している。[3] Originは、CLI、GitHubミラーリング、CI向けCloneKit、プルリクエスト、Code Tours、リポジトリの閲覧・検索、およびアクセスポリシーを備えたリポジトリホスティング機能を提供する。[3]

2026年10月から11月にかけて、Cursorは変更履歴（Changelog）で次のプラットフォーム機能追加を発表した。[7]

- **Origin App Marketplace（2026年10月13日）**: 20以上の連携アプリとともに開設され、公開アプリの提出受付を開始した。デプロイ（[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)、Netlify、Render、Spacelift、Vercel）、CI（Buildkite、CircleCI、CloudBees、Depot、EngFlow、Namespace、RWX）、コードレビュー（CodeRabbit、Greptile、Tenki）、セキュリティ（Artemis Security、Semgrep、Socket Security、Upwind）、モニタリング（Sentry）、プロジェクト管理（Linear）の各分野をカバーする。OriginアプリはアプリJWTとインストールアクセストークンで認証し、Webhookイベントを受信してチェック実行、プルリクエストコメント、およびレビューを書き戻す。[7]
- **Cloud Agent CanvasesおよびEnvironments API（2026年10月16日）**: クラウドエージェントが構築する共有可能なインタラクティブCanvasesを追加し、エージェントのクラウド環境をプログラムで管理するEnvironments APIベータ版を公開した。また、環境あたりの収容能力を最大300リポジトリへ拡張し、大規模環境の読み込み速度を5倍に高速化した。[7]
- **Agent SDK（2026年10月20日）**: 一般提供（GA）を開始した。プロンプト用の`instructions.md`、型付きアクション用の`tools/`、オンデマンド手順用の`skills/`、MCPサーバーツール用の`mcp-connections/`、およびGitHub・GitLab・Bitbucket・Slack・Webhook・cronスケジュールからのトリガー用`channels/`を含むコードフォルダとしてエージェントを定義できる。ローカルセットアップとプレイグラウンド（`npx @cursor/agent-sdk init`、`agent-sdk dev`）、検証（`agent-sdk validate`）、評価およびプルリクエストWebhook再生（`agent-sdk eval`、`agent-sdk github replay`）、テンプレート（セキュリティレビュアー、オーナーポリシー承認者、PR自動修正、LinearまたはJiraトリアージ）、ならびにCursorまたはセルフホストインフラへのデプロイ（`agent-sdk deploy`）を提供する。[7]
- **Live Apps（2026年11月5日）**: クラウドエージェントが有効なすべての有料プラン向けにリリースされた。クラウドエージェントが新規または既存のCursor OriginやGitHubリポジトリからウェブアプリケーションの雛形を構築し、必要に応じてPostgresデータベースをプロビジョニングし、Cursor SSOの背後に認証を配置したうえで、認証情報の露出などを検出する決定論的およびエージェント型セキュリティチェックを実行し、指定したURLへデプロイする。チーム管理者はすべてのアプリとシークレットを監査し、カスタムセキュリティルールの追加、ブロックされた公開の承認、または公開停止を行える。個人ユーザーはアプリを一般公開でき、スクリプトやGrok Bot向けにCursor APIキーを発行できる。[7]

2026年11月6日、CursorはAgents Window、IDE、ウェブ、およびCursor for iOSにわたってコーディングエージェントと音声会話できるVoice Chatを追加し、Siri起動（`"Hey Siri, call Cursor"`）およびiOSロック画面のLive Activity操作に対応した。[7] Voice Chatは[Grok](https://mimirwiki.com/ja/wiki/grok) Voiceで動作し、Ara、Eve、Leo、Rex、Salなどの音声を選択でき、Privacy Modeが有効な場合はデータ無保持（ゼロデータリテンション）で稼働する。[7] Voice Chatは双方向の音声会話機能であり、音声入力によるテキスト変換機能（旧称Voice Mode、IDEでは`Cmd+Shift+Space`で切り替え）とは別機能である。[7]

## Cursorの対応モデルとCursor Router

Cursorは[OpenAI](https://mimirwiki.com/ja/wiki/openai)、[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)、Google、SpaceXSIなどのモデルに対応しており、2026-11-23時点でサブスクリプションの週間使用量プールでカバーされる自社Cursorモデルと、プリペイドクレジットからAPI定価で課金されるサードパーティモデルに分類している。[3][5] 対象モデルでリージョナルデータレジデンシーをオプトインすると、モデル料金に10%が上乗せされる。[5]

Cursorの自社モデルプールには、[Grok](https://mimirwiki.com/ja/wiki/grok) 4.7、Grok 4.6、Grok 4.5、およびComposer 2.5が含まれる。[5] 週間プールを超過した利用に対しては、2026-11-23時点で以下の100万トークンあたりの単価が適用される。[3][5]

| Cursorモデル | デフォルト / 最大コンテキスト | 標準 入力 / キャッシュ読み取り / 出力（100万トークンあたり） | Fastモード 入力 / キャッシュ読み取り / 出力（100万トークンあたり） | 米国データレジデンシー |
| --- | --- | --- | --- | --- |
| Grok 4.7 | 256k / 500k | $2 / $0.5 / $6（500k: $4 / $1 / $12） | $4 / $1 / $12（500k Fast: $6 / $1.5 / $18） | 対応 |
| Grok 4.6 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $12 | 対応 |
| Grok 4.5 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $18 | 対応 |
| Composer 2.5 | 200k / - | $0.5 / $0.2 / $2.5 | $3 / $0.5 / $15 | 対応 |

サードパーティモデルはFreeおよびPlusプランでは利用できず、Premium以上のプランで最初のリクエストからAPI定価で利用できる。[5] 2026-11-23時点で、Cursorのドキュメントには[Claude](https://mimirwiki.com/ja/wiki/claude)、GPT-5.6、[Google Gemini](https://mimirwiki.com/ja/wiki/google-gemini)を含む以下のサードパーティモデルと100万トークンあたりの価格が記載されている。[3][5]

| サードパーティモデル | デフォルト / 最大コンテキスト | 入力 | キャッシュ書き込み | キャッシュ読み取り | 出力 | 米国データレジデンシー |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 300k / 1M | $8 | $10 | $0.2 | $40 | 対応 |
| Claude Opus 5.5 | 300k / 1M | $4 | $5 | $0.2 | $20 | 対応 |
| Claude Sonnet 5.5 | 200k / 1M | $2 | $2.5 | $0.1 | $10 | 対応 |
| Claude Haiku 5.5 | 300k / 1M | $0.1 | $0.125 | $0.01 | $0.5 | 対応 |
| GPT-5.6 Sol | 272k / 1M | $4 | $5 | $0.4 | $20 | 対応 |
| GPT-5.6 Terra | 272k / 1M | $2 | $2.5 | $0.2 | $12 | 対応 |
| GPT-5.6 Luna | 272k / 1M | $0.2 | $0.25 | $0.02 | $1.2 | 対応 |
| Gemini 4 Neon | 200k / 1M | $3 | - | $0.15 | $15 | 対応 |
| Gemini 4 Carbon | 200k / 1M | $2 | - | $0.1 | $10 | 対応 |
| Gemini 4 Argon | 200k / 1M | $2 | - | $0.1 | $10 | 対応 |
| Gemini 4 Hydrogen | 200k / 1M | $1.5 | - | $0.075 | $7.5 | 対応 |
| Gemini 3.1 Pro | 200k / 1M | $2 | - | $0.2 | $12 | 非対応 |
| Gemini 3.8 Flash | 200k / 1M | $0.75 | - | $0.075 | $3.75 | 対応 |
| Muse Wonder | 300k / 1M | $4 | - | $0.2 | $20 | 非対応 |

CursorのAuto機能は、Cursor Routerを通じてCost、Balance、Intelligenceの3モードに分かれている。[5][6] 個人向けプランは従来のAutoモードの後継であるCostモードに対応しており、実際にどのモデルがリクエストを処理してもCursorモデルのリクエストとして週間プールから消費される。[5][6] Cursorは、BalanceおよびIntelligenceモードを提供するCursor RouterをTeamsとEnterpriseプラン向けに提供開始する予定であり、Agents Window、エディタ、CLI、Cursor SDK、およびiOSアプリで利用でき、Enterpriseチームは管理者がオプトインするまで無効の状態で始まると説明している。Cursorモデルへルーティングされたリクエストは週間プールから消費され、サードパーティモデルへルーティングされたリクエストはプリペイドクレジットからAPI定価に加えて対象時はCursor Token Rateが課金される。[5][6]

## Cursorの料金プラン、The X Subscription、レガシー料金体系

Cursorは、Grok、Cursor、およびXを1つに統合したサブスクリプションであるThe X Subscriptionの一部として販売されており、認定再販業者やサードパーティ販売店を介さずX Subscription Corp.から直接提供されている。[4][5][6] 公開されているすべてのサブスクリプション価格にはVATなどの適用税が含まれていない。[4][5] 2026-11-23時点で、CursorはThe X Subscriptionにおいて以下のプランを提示している。[4][5][6]

| プラン | 月額料金 | 年額料金 | 付属週間プール | サードパーティモデル |
| --- | --- | --- | --- | --- |
| Free | $0 | - | 制限あり | 利用不可 |
| Plus | $8 | $80 | 基準（Base） | 利用不可 |
| Premium | $30 | $300 | Plusの4倍 | プリペイドクレジットからAPI定価 |
| Super | $100 | $1,000 | Plusの15倍 | プリペイドクレジットからAPI定価 |
| Ultra | $200 | $2,000 | Plusの50倍 | プリペイドクレジットからAPI定価 |
| Teams | 1シートあたり$30、$100、または$200 | - | シート等級に準拠（Plusの4倍〜50倍） | API定価＋対象モデルにCursor Token Rate |
| Enterprise | 個別見積もり | 個別見積もり | GrokとCursorで共有プール | API定価＋対象モデルにCursor Token Rate |

各有料プランには、エディタ内のAgent、CLI、Cloud Agents、Grok Bot、およびGrokアプリケーション（Chat、Imagine、Voice、Bot）全体で共有される毎週リセット型のCursorモデル使用量プールが1つ含まれる。有料プランにはGrok APIアクセスも付帯するが、API利用は標準モデル単価で別途課金される。[4][5] PlusではCursorモデルが固定設定（Fastモード無効、medium effort、Grok 4.7の256kコンテキストウィンドウ）で動作し、Auto、Cloud Agents、Automations、Bugbot、Origin、サードパーティモデル、およびAPIキー持ち込み（BYOK）は対象外である。[5] Superではピーク時の優先モデルアクセスが追加され、Ultraでは新製品および新モデルへの最優先アクセスが追加される。[4][5] 週間プールを使い切ってもリクエストの品質や速度が低下することはなく、ユーザーは週次リセットを待つか、`grok.com/dashboard/billing`で管理するプリペイドクレジットのチャージ（手動チャージまたは月間上限付きの自動チャージ）を購入するか、上位プランへアップグレードできる。[5] セルフサービスプランは主要なクレジットカードおよびデビットカードに対応し、更新24時間前まで解約可能であり、アップグレードは即時反映、ダウングレードは請求期間終了時に反映される。[4][6]

Teamsプランでは1つのチーム内でPremium、Super、Ultraの各シート等級を混在させることができ（Plusはチーム利用不可）、一元的な請求管理、利用状況分析、チーム全体へのPrivacy Mode強制適用、カスタムChatデータ保持期間、チームマーケットプレイス、およびSAML/OIDC SSOが追加される。[4][5] Enterpriseでは、共有使用量プール、請求書・発注書払いおよび銀行振込、SCIMによるシート管理、きめ細かな支出管理、グループ単位の上限設定、監査ログ、サービスアカウント、高度なネットワークおよびMCP制御、ならびに優先サポートが追加される。[4][5] TeamsおよびEnterpriseプランでは、対象のサードパーティモデルへのリクエストとBYOK利用に対し、入力・出力・キャッシュトークンのすべてに100万トークンあたり0.25ドルのCursor Token Rateが適用される。一方、個人向けプラン、Cursorモデル、Costモードのリクエスト、およびすべての料金帯でキャッシュ読み取り単価が100万トークンあたり0.10ドル未満のサードパーティモデルは免除される。[5]

Cursorはまた、The X Subscription以前に販売されていたレガシープランを既存契約者向けに維持している。[5][6] レガシープランは新規受付を終了しており、契約者が解約するかThe X Subscriptionへ恒久的に切り替えない限り継続する（切り替え時はレガシー契約が日割り払い戻しのうえ解約される）。請求管理は`cursor.com/dashboard/billing`のStripeで行われ、Cursor ModelsとOther Modelsの2つの月間使用量プールと追加リクエスト向けの従量課金が提供される。[5][6] 従来のリクエストベース型レガシープランには、モデルAPI料金に20%を上乗せして拡張コンテキストウィンドウを利用できるMax Modeも含まれていた。[5]

| レガシーCursorプラン | 料金 | The X Subscriptionの相当プラン |
| --- | --- | --- |
| Hobby | 無料 | Free |
| Start（インド限定） | 月額₹649（税込） | Plus |
| Pro | 月額$20 | Premium |
| Pro+ | 月額$60 | Super |
| Ultra | 月額$200 | Ultra |
| Teams Standard | 1ユーザーあたり月額$40 | Teams（Premiumシート） |
| Teams Premium | 1ユーザーあたり月額$120 | Teams（Superシート） |

## Cursorのセキュリティ、コンプライアンス、プライバシー管理

Cursorは、セキュリティアーキテクチャを`cursor.com/security`（最終更新2026年8月25日）に、プライバシーポリシーを`cursor.com/privacy`（最終更新2026年11月6日）に公開している。[8][9] 2026-11-23時点で、CursorはAIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023の認証およびSOC 2 Type IIの保証報告書を取得しており、認証書、報告書、ペネトレーションテストのエグゼクティブサマリーを`trust.cursor.com`で請求に応じて提供し、復委託先（サブプロセッサー）一覧は同じトラストポータルで公開している。[4][8][9] Cursorは少なくとも年1回の第三者によるペネトレーションテスト実施を約束している。[8]

Cursorは、すべてのサブプロセッサーに対してベンダーリスク評価と年次再審査を実施し、多要素認証（MFA）とログ監視を伴う最小権限の原則に基づいてインフラアクセスを管理し、ブロックリストに登録されたモデルへリクエストがルーティングされないよう強制していると説明している。[8] また、中国国内にインフラを使用または維持しておらず、中国に本社を置く企業をサブプロセッサーとして起用していないと明言している。[8] `security-reports@cursor.com`宛に報告されたセキュリティ脆弱性は5営業日以内に受領確認され、重大なセキュリティインシデントは影響を受けるユーザーへメールで通知される。[8] Cursorは自社コードベースの保護にもBugbotおよびCloud Agentの自動化を活用している。[8]

CursorはPrivacy Modeを無料ユーザーを含め誰でも利用できると説明しており、ユーザーが設定から有効化できるほか、チームまたはエンタープライズの管理者も有効化でき、新規チームメンバーにはチーム設定が引き継がれる。[4][8] Privacy Modeが有効な場合、Cursorは技術的制御とプロバイダーとの契約条件に基づき、ユーザーのコードデータがCursorまたはモデルプロバイダーの学習に使用されないとし、Voice Chatもデータ無保持で動作すると述べている。[4][7][8] プライバシーポリシーでは、個人アカウントをAnysphere, Inc.が管轄する一方、Anysphereがデータ処理者として機能する雇用主提供の商用アカウントは顧客契約の適用対象となる。[9] Anysphereは、セキュリティレビュー対象としてフラグが立てられた場合、ユーザーから明示的にフィードバック報告された場合、またはユーザーから明示的な承認を得た場合を除き、入力（Inputs）および提案（Suggestions）をモデル学習に使用しないと明記しており、遺伝情報、生体情報、健康情報、宗教情報を意図的に収集せず、18歳未満のユーザー向けにサービスを提供しないと述べている。[9] ユーザーは設定ダッシュボードから直接アカウントを削除できる。[8]

組織向け導入に関して、CursorはSAML/OIDC SSO、SCIMプロビジョニング、コンプライアンスおよび監査ログ、サービスアカウント、モバイルデバイス管理（MDM）による展開、データ暗号化および顧客管理暗号鍵（CMEK）、自動実行・ブラウザ・ネットワーク制御、ならびにリポジトリ、モデル、MCPサーバー、Grok Botに対するアクセス制御を文書化している。[4][8]

## Cursorの企業沿革、資金調達、SpaceXによる買収合意

Cursorは、2022年に設立され2024年に[OpenAI](https://mimirwiki.com/ja/wiki/openai)のスタートアップアクセラレーターに参加したAnysphere, Inc.によって開発された。[1][9] 2024年後半、Anysphereはプレマネー企業価値25億ドルで1億ドルを調達した。[2] 2025年初頭にはOpenAIやその他の買収候補から買収打診を受けたが、Anysphereはこれらの提案を辞退した。[2]

TechCrunchの報道によると、Anysphereの年間経常収益（ARR）は2025年4月中旬に3億ドルに達し、BloombergおよびTechCrunchが引用した関係者によれば、2025年6月5日までに5億ドルを超えた。[2] 2025年6月5日、TechCrunchはAnysphereが既存投資家のThrive Capital主導のもと、Andreessen Horowitz、Accel、DST Globalの参加を得て、企業価値99億ドルで9億ドルのシリーズCラウンド（1年以内で3度目の資金調達）を完了したと報じた。[1][2] 当時、Cursorは2週間の無料トライアル後に月額20ドルのProまたは月額40ドルのビジネスサブスクリプションへ移行するプランに加え、新設のエンタープライズライセンスを提供していた。[2] 2025年後半、Anysphereはさらに23億ドルを調達し、TechCrunchはSpaceXとの取引発表前の企業価値を約290億ドルと伝えた。[1]

2026年初頭、xAIはCursorの上級エンジニアリングリーダー2名を採用し、2026年4月にはBusiness InsiderがxAIによるCursor向けデータセンター容量の賃貸契約を報じた。[1] SpaceXからの買収提案に先立ち、CursorはAndreessen Horowitz、Thrive Capital、Nvidiaなどの投資家から企業価値500億ドルで20億ドルを調達するラウンドの締結直前にあった。[1] 2026年4月、SpaceXの新規株式公開（IPO）を前に、SpaceXは、600億ドル相当の株式でCursorを買収するか、取引が成立しなかった場合に100億ドルの違約金を支払うという合意を発表した。[1]

2026年6月16日、1株135ドルでのSpaceXのIPOから数日後、かつ2026年初頭のSpaceXとxAIの合併に続き、TechCrunchはSpaceXが600億ドルの株式交換取引でCursorを買収することに合意し、SpaceXが2026年第3四半期の完了を見込んでいると報じた。[1] 2026-11-23時点で、Cursorの公式ウェブサイトおよびドキュメントは、X Subscription Corp.が[Grok](https://mimirwiki.com/ja/wiki/grok)およびXとともに販売するThe X SubscriptionにCursorが統合されていることを示し、SpaceXSI Subscription Termsへのリンクと対応モデルプロバイダーとしてのSpaceXSIの記載を行う一方、ウェブサイトの著作権表示およびプライバシーポリシーには引き続き`Anysphere, Inc.`を記載している。[4][5][8][9]

## よくある質問

### Cursorの料金はいくらですか？

2026-11-23時点で、CursorはThe X Subscriptionを通じて5つの個人向けプランで提供されています。いずれも税別で、Free（月額0ドル）、Plus（月額8ドルまたは年額80ドル）、Premium（月額30ドルまたは年額300ドル）、Super（月額100ドルまたは年額1,000ドル）、Ultra（月額200ドルまたは年額2,000ドル）です。Teamsプランは1シートあたり月額30ドル、100ドル、または200ドルで、Enterpriseプランは個別見積もりとなります。Premium以上のプランにおけるサードパーティモデルは、プリペイドクレジットからAPI定価で別途課金されます。 [4][5]

### ProやPro+などのレガシーCursorプランはどうなりましたか？

Hobby（無料）、インド限定のStart（税込月額649ルピー）、Pro（月額20ドル）、Pro+（月額60ドル）、Ultra（月額200ドル）、Teams Standard（1ユーザーあたり月額40ドル）、Teams Premium（1ユーザーあたり月額120ドル）などのレガシーCursorプランは新規受付を終了しています。既存の契約者は、解約またはThe X Subscriptionへの恒久的な移行を選択しない限り、従来のプラン、2つの月間使用量プール、および従量課金をそのまま維持できます。 [5][6]

### CursorはどのAIモデルに対応していますか？

2026-11-23時点で、有料プランにはCursor独自モデル（Grok 4.7、Grok 4.6、Grok 4.5、Composer 2.5）向けの週間共有使用量プールが含まれています。Premium以上のプランでは、Claude（Anthropic）、GPT-5.6（OpenAI）、Gemini（Google）、Muse Wonderなどのサードパーティモデルも利用でき、プリペイドクレジットからAPI定価で課金されます。 [3][5]

### CursorのPrivacy Modeとセキュリティ認証はどのように機能しますか？

2026-11-23時点で、CursorはAIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023の認証とSOC 2 Type IIの保証報告書を取得しており、関連文書はtrust.cursor.comから請求できます。Privacy Modeは無料ユーザーを含め誰でも利用でき、管理者がチーム全体に強制適用できます。有効にするとユーザーのコードデータがモデル学習に使用されなくなり、Voice Chatもデータ無保持（ゼロデータリテンション）で動作します。 [7][8][9]

### Cursorにはどのようなカスタマイズ機能や自動化機能がありますか？

Cursorの公式ドキュメントでは、Plugins、Rules、Skills、Subagents、Hooks、モデルコンテキストプロトコル（MCP）サーバーの6つのカスタマイズ機構が定義されています。さらに、コマンドラインインターフェース（CLI）、Cloud Agents、Automations、Originコードホスティング、Bugbotコードレビュー、Live Apps、Voice Chat、およびコード定義エージェントを構築・デプロイするためのAgent SDKも備えています。 [3][4][7]

### Cursorの所有企業はどこですか？

Cursorは2022年設立のAnysphere, Inc.によって開発されました。2026年6月16日、TechCrunchはSpaceXが2026年第3四半期の完了を見込み、600億ドル規模の株式交換取引でCursorを買収することに合意したと報じました。2026-11-23時点で、CursorのサブスクリプションはX Subscription Corp.を通じてThe X Subscriptionの一部として販売されていますが、Cursorのプライバシーポリシーおよびウェブサイトの著作権表示には引き続きAnysphere, Inc.が記載されています。 [1][4][9]

## 引用できる文

- Cursorは、2022年に設立され2024年にOpenAIのスタートアップアクセラレーターに参加したAnysphereによって開発された。 [1]
- 2025年6月5日、TechCrunchはAnysphereが企業価値99億ドルで9億ドルを調達し、年間経常収益（ARR）が5億ドルを突破したと報じた。 [2]
- 2026年6月16日、TechCrunchはSpaceXが2026年第3四半期の完了を見込み、600億ドル規模の株式交換取引でCursorを買収することに合意したと報じた。 [1]
- 2026-11-23時点で、CursorはX Subscription Corp.を通じてThe X Subscriptionの一部として直接販売されており、個人向け月額プランは税別で0ドル（Free）、8ドル（Plus）、30ドル（Premium）、100ドル（Super）、200ドル（Ultra）である。 [4][5]
- 2026-11-23時点で、CursorのTeamsおよびEnterpriseプランでは対象のサードパーティモデルへのリクエストおよびAPIキー持ち込み（BYOK）利用に対して100万トークンあたり0.25ドルのCursor Token Rateが加算されるが、個人向けプランにはこの料金は適用されない。 [5]
- 月額20ドルのProや月額60ドルのPro+を含むレガシーCursorプランは、既存の契約者が解約するかThe X Subscriptionへ恒久的に移行しない限り、2つの月間使用量プールを備えたまま継続利用できる。 [5][6]
- 2026-11-23時点で、CursorはAIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023の認証およびSOC 2 Type IIの保証報告書を取得しており、中国国内にインフラストラクチャを保有していないと明言している。 [8]
- 2026年10月から11月にかけて、Cursorは10月13日にOrigin App Marketplace、10月20日にAgent SDK、11月5日にLive Apps、11月6日にGrok Voice搭載のVoice Chatを相次いで公開した。 [7]

## 年表

- 2022: Cursorの開発元であるAnysphereが設立された。 [1]
- 2024: AnysphereがOpenAIのスタートアップアクセラレーターに参加し、2024年後半にプレマネー企業価値25億ドルで1億ドルを調達した。 [1][2]
- 2025-04: TechCrunchが、Anysphereの年間経常収益が3億ドルに達したと報じた。 [2]
- 2025-06-05: TechCrunchが、AnysphereはThrive Capital主導のもと企業価値99億ドルで9億ドルのシリーズCラウンドを調達し、年間経常収益が5億ドルを超えたと報じた。 [1][2]
- 2026-04: xAIによるCursor向けデータセンター容量の賃貸報道と並行して、SpaceXがCursorの600億ドルの株式買収または100億ドルの違約金に関する合意を発表した。 [1]
- 2026-06-16: TechCrunchが、SpaceXは2026年第3四半期の完了を見込み、600億ドルの株式交換取引でCursorを買収することに合意したと報じた。 [1]
- 2026-08-25: Cursorがセキュリティドキュメントを更新し、AIUC-1、ISO/IEC 27001:2022、ISO/IEC 42001:2023の認証およびSOC 2 Type IIの保証報告書を記載した。 [8]
- 2026-10-13: Cursorが20以上のパートナー連携を備えたOrigin App Marketplaceを開設し、公開アプリの提出受付を開始した。 [7]
- 2026-10-16: Cursorがクラウドエージェント向けの共有可能なインタラクティブCanvases、Environments APIベータ版、およびクラウド環境あたり最大300リポジトリの対応を追加した。 [7]
- 2026-10-20: CursorがAgent SDKの一般提供（GA）を開始した。 [7]
- 2026-11-05: Cursorが有料プラン向けにクラウドエージェントからのLive Appsデプロイ機能を提供開始した。 [7]
- 2026-11-06: CursorがGrok Voice搭載のコーディングエージェント向けVoice Chatを公開し、プライバシーポリシーを更新した。 [7][9]

## 出典

1. SpaceX to acquire Cursor for $60B in stock, days after blockbuster IPO | TechCrunch. TechCrunch. 公開 2026-06-16. https://techcrunch.com/2026/06/16/spacex-to-acquire-cursor-for-60b-in-stock-days-after-blockbuster-ipo/ (閲覧 2026-11-23; tier 2: academic or news)
2. Cursor's Anysphere nabs $9.9B valuation, soars past $500M ARR | TechCrunch. TechCrunch. 公開 2025-06-05. https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/ (閲覧 2026-11-23; tier 2: academic or news)
3. Cursor Docs - Agent, Rules, MCP, Skills & CLI. Cursor. https://cursor.com/docs (閲覧 2026-11-23; tier 3: official site)
4. Cursor · Pricing. Cursor. https://cursor.com/pricing (閲覧 2026-11-23; tier 3: official site)
5. Models & Pricing | Cursor Docs. Cursor. https://cursor.com/docs/models-and-pricing (閲覧 2026-11-23; tier 3: official site)
6. Pricing and plans | Cursor Docs. Cursor. https://cursor.com/help/account-and-billing/pricing (閲覧 2026-11-23; tier 3: official site)
7. What's New in Cursor - Latest Updates & Release Notes. Cursor. https://cursor.com/changelog (閲覧 2026-11-23; tier 3: official site)
8. Cursor · Security. Cursor. https://cursor.com/security (閲覧 2026-11-23; tier 3: official site)
9. Cursor · Privacy Policy. Cursor. https://cursor.com/privacy (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Cursor." 版 15fbd5a4, 2026-11-25. https://mimirwiki.com/ja/wiki/cursor
