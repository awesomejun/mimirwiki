---
title: "GitHub Copilot"
subtitle: "GitHubが開発したエディタ、ターミナル、デスクトップアプリ、リポジトリ向けのAIコーディングアシスタントおよびエージェントプラットフォーム"
canonical_url: https://mimirwiki.com/ja/wiki/github-copilot
language: ja
page_class: entity
revision_sha256: 6eb895b4f6200038fbfb374a277c7254e5275ea2a38a68f94897fd638a43c99b
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/ja/wiki/github-copilot.md
  txt: https://mimirwiki.com/ja/wiki/github-copilot.txt
  json: https://mimirwiki.com/ja/wiki/github-copilot.json
  jsonld: https://mimirwiki.com/ja/wiki/github-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/github-copilot
  ko: https://mimirwiki.com/ko/wiki/github-copilot
  zh: https://mimirwiki.com/zh/wiki/github-copilot
  es: https://mimirwiki.com/es/wiki/github-copilot
---

# GitHub Copilot

> GitHub CopilotはGitHubが開発したAIコーディングアシスタントおよびエージェントプラットフォームであり、GitHubのクラウドサービスはMicrosoft CorporationのIntelligent Cloudセグメントに計上されている。2021年6月29日にテクニカルプレビューが公開され、2022年6月21日に一般提供が開始された。IDE、ターミナル、デスクトップアプリ、github.comで動作し、2026-11-23時点ではマルチベンダーモデルとAI Credits課金を提供している。

GitHub Copilotは、GitHubが開発した人工知能（AI）コーディングアシスタントおよびエージェントプラットフォームであり、GitHubのクラウドおよびオンプレミス製品はMicrosoft CorporationのIntelligent Cloudセグメント内で報告されている。GitHubは2021年6月29日にOpenAI Codexを用いた限定的なテクニカルプレビューとしてGitHub Copilotを発表し、2022年6月21日に個人開発者向けの一般提供を開始し、2024年12月18日にGitHub Copilot Freeプランを導入した。2026-11-23時点で、GitHub Copilotはコードエディタ、コマンドライン、デスクトップアプリケーション、github.com、GitHub Mobile、Slack、Microsoft Teams上で動作し、OpenAI、Anthropic、Google、Microsoft、xAI、KimiのAIモデルに加え、ユーザー提供のAPIキーやローカルモデルランタイムにも対応している。2026-11-23時点で、GitHubは個人向けプラン（Free、Student、月額10米ドルのPro、月額39米ドルのPro+、月額100米ドルのMax）および組織・企業向けプラン（1シートあたり月額19米ドルのBusiness、1シートあたり月額39米ドルのEnterprise、Copilot access）を提供しており、従量課金機能は1クレジットあたり0.01米ドルのGitHub AI Creditsで課金される。

**別名:** Copilot, GitHub Copilot Pro, GitHub Copilot Business, GitHub Copilot Enterprise

## 主要な事実

- **テクニカルプレビュー開始:** 2021-06-29 [7]
- **一般提供開始:** 2022-06-21 [8]
- **個人向け有料プラン:** Pro（月額10米ドル）、Pro+（月額39米ドル）、Max（月額100米ドル） (時点 2026-11-23) [2]
- **組織・企業向けプラン:** Business（1シートあたり月額19米ドル）、Enterprise（1シートあたり月額39米ドル）、Copilot access（GHECは0米ドル、Standaloneは1ユーザーあたり月額10米ドル） (時点 2026-11-23) [2]
- **クレジット課金単位:** 1 GitHub AI Credit = 0.01米ドル (時点 2026-11-23) [6]

## ファクトシート

- **開発元:** GitHub [7]
- **親会社の報告セグメント:** Microsoft Corporation、Intelligent Cloudセグメント (時点 2026-06-30) [1]
- **テクニカルプレビュー:** 2021-06-29 [7]
- **一般提供開始:** 2022-06-21 [8]
- **無料プラン提供開始:** 2024-12-18 [9]
- **個人向けプラン:** Free（0米ドル）、Student（認証済み学生0米ドル）、Pro（月額10米ドル）、Pro+（月額39米ドル）、Max（月額100米ドル） (時点 2026-11-23) [2]
- **組織・企業向けプラン:** Business（1シートあたり月額19米ドル）、Enterprise（1シートあたり月額39米ドル）、Copilot access（GHECは0米ドル、Standaloneは1ユーザーあたり月額10米ドル） (時点 2026-11-23) [2]
- **従量課金単位:** GitHub AI Credits（1クレジット = 0.01米ドル） (時点 2026-11-23) [6]
- **対応環境:** VS Code、Visual Studio、JetBrains IDE、Xcode、Vim、Neovim、Zed、Eclipse、Raycast、SQL Server Management Studio、CLI、デスクトップアプリ、github.com、GitHub Mobile、Slack、Teams (時点 2026-11-23) [5]
- **対応AIモデルプロバイダー:** OpenAI、Anthropic、Google、Microsoft、xAI、Kimi (時点 2026-11-23) [5]

## GitHub Copilotの提供沿革とMicrosoftにおける開示上の位置づけ

GitHub Copilotは2021年6月29日、GitHubが[OpenAI](https://mimirwiki.com/ja/wiki/openai)と共同で開発し[OpenAI Codex](https://mimirwiki.com/ja/wiki/openai-codex)を搭載した限定的なテクニカルプレビューとして発表された。[7] 発表当時、GitHubはCopilotを、開いているコードから文脈を読み取って行全体や関数全体を提案するAIペアプログラマーと位置づけ、公開ソースコードの比率が高いデータセットで学習されており、複数の言語、とりわけPython、JavaScript、TypeScript、Ruby、Goで機能すると説明した。[7]

2022年6月21日、GitHubはGitHub Copilotをエディタ拡張機能としてすべての個人開発者向けに一般提供開始し、料金を月額10米ドルまたは年額100米ドルと設定したほか、無料トライアルならびに認証済み学生および人気オープンソースプロジェクトのメンテナーに対する無料提供を用意した。[8] 2024年12月18日には、2021年から2025年までGitHubの最高経営責任者（CEO）を務めたThomas Dohmkeが、GitHub上の開発者数が1億5,000万人に達したことを受け、Visual Studio Codeに統合されGitHubダッシュボードからも利用できるGitHub Copilot Freeを発表した。[9] 提供開始時点のCopilot Freeは月間2,000回のコード補完と50回のチャットメッセージを提供し、[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)の[Claude](https://mimirwiki.com/ja/wiki/claude) 3.5 SonnetおよびOpenAIのGPT-4oに対応し、複数ファイル編集やサードパーティ製エージェントを可能にした一方で、学生、教育者、オープンソースメンテナー向けの無料・無制限のCopilot Pro利用枠はそのまま維持された。[9]

Microsoft Corporationの2026年6月30日終了会計年度のForm 10-K（[SEC EDGAR](https://mimirwiki.com/ja/wiki/sec-edgar)のSEC Central Index Key 0000789019）では、GitHubは開発者がコードを管理しソフトウェア開発ライフサイクル全体にわたってAIおよびエージェントベースのツールを組み込むためのクラウドおよびオンプレミス製品を提供していると記述されている。[1] MicrosoftはGitHubのクラウドサービスをIntelligent Cloudセグメントのサーバー製品およびクラウドサービス区分に含め、GitHubクラウドサービスの収益をAzureおよびその他のクラウドサービスの収益成長指標に算入しており、当該抜粋箇所ではGitHub Copilot単独の収益を別途開示していない。[1] 2026年6月30日終了会計年度のForm 10-Kにおいて、Microsoftが報告した連結業績は以下の通りである。[1]

| Microsoft Corporation連結指標 | 2026会計年度 | 2025会計年度 | 増減率 |
| --- | --- | --- | --- |
| 売上高 | 3,318億3,900万米ドル | 2,817億2,400万米ドル | 18% |
| 売上総利益 | 2,254億6,500万米ドル | 1,938億9,300万米ドル | 16% |
| 営業利益 | 1,552億3,700万米ドル | 1,285億2,800万米ドル | 21% |
| 純利益 | 1,337億4,900万米ドル | 1,018億3,200万米ドル | 31% |
| 希薄化後1株当たり利益 | 17.95米ドル | 抜粋内に記載なし | 抜粋内に記載なし |

## GitHub Copilotのプランと料金体系

GitHub Copilotは2026-11-23時点で、5種類の個人向けプランと3種類の組織・企業向けプランを通じて提供されている。[2][5] GitHubは、すべてのプランにCopilot CLIおよびCopilotアプリが含まれること、ならびにGitHub CopilotがGitHub Enterprise Serverでは利用できないことを明記している。[2] 組織・企業向けサブスクリプションはGitHub FreeまたはGitHub Teamプランの組織、およびGitHub Enterprise Cloudを利用する組織・企業が契約でき、Copilot EnterpriseにはGitHub Enterprise Cloudが必要である。[2][3]

以下の表は、2026-11-23時点のGitHub DocsおよびGitHub Copilotプランページから各プランの料金、月間クレジット付与量、モデル区分をまとめたものである。[2][3][5]

| プラン | 対象 | 掲載価格 | 月間GitHub AI Credits付与量 | モデルアクセスおよび主な差異 |
| --- | --- | --- | --- | --- |
| Copilot Free | 個人 | 0米ドル | 制限付き付与量（月間2,000回のインライン補完） | 自動モデル選択のみ（Docs記載）、Fusion Standard、コミュニティサポート |
| Copilot Student | 個人（認証済み学生） | 0米ドル | 制限付き付与量 | 自動モデル選択のみ（Docs記載）、サードパーティ製エージェント除外 |
| Copilot Pro | 個人 | 月額10米ドル（一部ユーザーは無料） | 基本1,000クレジット（基本10米ドル＋フレックス枠5米ドル、計15米ドル） | 無制限の補完および次の編集提案、モデル選択、Copilot in the cloud、コードレビュー |
| Copilot Pro+ | 個人 | 月額39米ドル | 基本3,900クレジット（基本39米ドル＋フレックス枠31米ドル、計70米ドル） | Opusを含むプレミアムモデル、Fusion Standard・High・Max、監査ログ |
| Copilot Max | 個人 | 月額100米ドル | 基本10,000クレジット（基本100米ドル＋フレックス枠100米ドル、計200米ドル） | 新モデルおよび新機能への優先アクセス、個人向け最大の付与量 |
| Copilot Business | 組織・企業 | 付与シート1件あたり月額19米ドル | 1ユーザーあたり月間1,900クレジット（共有プール） | 幅広いモデルカタログ・プレミアムモデル、集中管理およびポリシー制御 |
| Copilot Enterprise | 企業（GitHub Enterprise Cloud） | 付与シート1件あたり月額39米ドル | 1ユーザーあたり月間3,900クレジット（共有プール） | 新モデルおよび新機能への優先アクセス、Copilot Businessの全機能 |
| Copilot access | 対象企業 | 0米ドル（GitHub Enterprise Cloudライセンス保有ユーザー）または1ユーザーあたり月額10米ドル（Copilot Standalone） | 含まれる付与量なし（初回利用から従量課金） | Copilot Enterpriseと同一の機能およびモデル利用資格 |

2026-11-23時点の個人向けプラン比較ページでは、共有プール利用、エンタープライズ級セキュリティ、知的財産権（IP）補償、github.comでのユーザー管理、利用状況メトリクス、SAML SSO認証がFree、Pro、Pro+、Maxから除外されている。[5] GitHubのPro概要カードにはサードパーティ製エージェント（Claude CodeおよびCodex）がProから含まれると記載されている一方、同ページのCopilot in the cloud機能比較表ではClaude by AnthropicやOpenAI Codexなどのサードパーティ製コーディングエージェントへのクラウド委任（Preview）がPro+およびMaxに含まれると記載されている。[5]

## GitHub CopilotのAI Creditsと課金モデル

GitHub Copilotは2026-11-23時点で、各プランにおける対話型およびエージェント型AIの利用量をGitHub AI Creditsで計測しており、1 AIクレジットは0.01米ドルに相当する。[6] チャット、エージェントモード、コードレビュー、Copilot in the cloud、Copilot CLI、CopilotアプリはAIクレジットを消費し、各操作におけるクレジット消費量は選択したモデルとタスクの複雑さによって変動する。[5][6] インラインコード補完および次の編集提案（next edit suggestions）はAIクレジットを消費せず、組織ユーザーの予算が0米ドルの場合や設定された支出上限に達した場合であっても、有料プランでは無制限のまま維持される。[3][6]

2026-11-23時点の個人向け有料プランでは、月間総クレジットは各プランの月額料金と同額の固定基本枠（Proは10米ドル、Pro+は39米ドル、Maxは100米ドル）と、今後変更される可能性があるとGitHubが注記する変動フレックス枠（Proは5米ドル、Pro+は31米ドル、Maxは100米ドル）で構成される。[5] 月間付与量を使い切った場合、ユーザーは次の月次リセットを待つか、1回の操作あたりのクレジット消費が少ない軽量モデルへ切り替えるか、1クレジットあたり0.01米ドル（10米ドルで1,000クレジット）の追加従量課金向けに米ドル予算を設定できる。なお、追加クレジットの購入はFreeプランでは対象外である。[5][6] Copilot設定の予算追跡機能は、設定予算の75%、90%、100%に到達した際に利用アラートを発行する。[6]

組織および企業向けでは、Copilot BusinessおよびCopilot Enterpriseのライセンスがそれぞれの月間クレジット付与量を組織全体で共有するプールに合算し、管理者が有料の超過利用を許可している場合、プールを超えた利用分が別途請求される。[3][5][6] 管理者が追加の有料利用を許可しない場合、Copilotは次の請求サイクルまで一時停止される。[6] Copilot accessプランでは、含まれる付与量はなく初回利用時から従量課金される。[3] Copilotの各シートは1ユーザー分のライセンスを表し、追加料金が0米ドルのシートであっても割り当てが必要である。Copilot accessおよびCopilot Businessでは、企業オーナーが個人またはエンタープライズチームに直接シートを割り当てることで、チームメンバー全員にシートを付与できる。[3] データレジデンシー対応およびFedRAMP準拠のCopilotリクエストには、モデル乗数に10%の加算が適用される。[3]

## GitHub Copilotの対応AIモデルとCopilot Fusion

GitHub Copilotは2026-11-23時点で6社のプロバイダーにわたるマルチベンダーAIモデルに対応しており、利用可能なモデルはサブスクリプションプラン、機能、クライアント環境によって異なる。[2][4][5] GitHub Docsは、モデルの提供状況が変更される場合があり、モデルが時間の経過とともに更新または置換される可能性があることを明記している。[4] 以下の表は、2026-11-23時点のGitHub Docs（対応モデル一覧表で一般提供、すなわちGAと表記されたモデル）およびGitHub Copilotプランページに掲載されているモデルをまとめたものである。[4][5]

| プロバイダー | 掲載モデル（2026-11-23時点） |
| --- | --- |
| [OpenAI](https://mimirwiki.com/ja/wiki/openai) | GPT-5 mini, GPT-5.2, GPT-5.2-Codex, GPT-5.3-Codex, GPT-5.4, GPT-5.4 mini, GPT-5.4 nano, GPT-5.5, GPT-5.6 Luna, GPT-5.6 Sol, GPT-6 Astra, GPT-6 Luna, GPT-6 Sol, GPT-6.1 Sol, GPT-6.1 Terra, GPT-6.2 Astra, GPT-6.2 Sol |
| [Anthropic](https://mimirwiki.com/ja/wiki/anthropic) | [Claude](https://mimirwiki.com/ja/wiki/claude) Fable 5, Claude Fable 5.1, Claude Fable 5.2, Claude Haiku 4.5, Claude Haiku 5.5, Claude Sonnet 4, Claude Sonnet 4.6, Claude Sonnet 5, Claude Sonnet 5.5, Claude Opus 4.8, Claude Opus 4.8 (fast mode) (preview), Claude Opus 5.5 |
| Google | [Gemini](https://mimirwiki.com/ja/wiki/google-gemini) 3.7 Flash, Gemini 3.8 Flash, Gemini 4 Argon, Gemini 4 Carbon, Gemini 4 Hydrogen, Gemini 4 Neon |
| Microsoft | MAI-Code-1.1-Flash, MAI Code 2, MAI Code 2 Flash |
| xAI | [Grok](https://mimirwiki.com/ja/wiki/grok) 4.5, Grok 4.6, Grok 4.7 |
| Kimi | Kimi K3 |

手動でのモデル選択に加え、GitHub Copilotは2026-11-23時点で自動モデルルーティング機能であるCopilot Fusionを備えている。[5][6] Fusion Standard（Free、Pro、Pro+、Maxに含まれる）は日常業務向けにタスクごとに1つのモデルを選択し、Fusion Fast（Free、Pro、Pro+、Maxに含まれる）はVisual Studio Codeのインラインチャットのみで動作しユーザーによる直接選択はできない。[5] Fusion High（Pro+およびMaxに含まれる）は追加のモデル呼び出しを伴う複数ファイル変更や複雑なバグ修正を対象とし、Fusion Max（Pro+およびMaxに含まれる）はより深い推論と分析を要するタスクを対象とする。[5]

GitHub Copilotはさらに、ユーザー独自のAPIキーで外部クラウドモデルプロバイダーを接続する機能（bring your own key）およびOllamaとFoundry Localを通じたローカルモデルの実行にも対応している。[6]

## GitHub Copilotの対応環境、IDEサポート、エージェント機能

GitHub Copilotは2026-11-23時点でエディタ、ターミナル、デスクトップソフトウェア、Webインターフェース、メッセージングアプリケーション全体にわたって動作し、ある環境で開始したセッションを別の環境で引き継ぐことができる。[5][6] GitHubが挙げる対応エディタおよびIDE環境は、Visual Studio Code、Visual Studio、JetBrains IDE、Xcode、Vim、Neovim、Zed、Eclipse、Raycast、SQL Server Management Studioである。[5][6] エディタ以外では、Copilot CLIによるターミナル、GitHub Copilotデスクトップアプリ（macOS Apple Silicon向けビルドを含む）、github.com、GitHub Mobile、Slack、Microsoft Teams上で動作する。[5][6]

2026-11-23時点でGitHubが掲載している主なコーディングおよびエージェント機能は以下の通りである。[5][6]

- **インライン提案と次の編集提案（Inline suggestions and next edit suggestions）**: 公開リポジトリで使用されている各言語に対応するリアルタイムのコード補完機能であり、Freeプランでは月間2,000回までに制限され、有料プランでは無制限である。[5][6]
- **IDEエージェントモード**: Free、Pro、Pro+、Maxの各プランで、Visual Studio Code、Visual Studio、JetBrains IDE、Eclipse、Xcodeにおいて利用できる。[5]
- **Copilot in the cloud**: 有料プランで利用でき、プルリクエストの有無を問わず調査、計画、コード作成を実行し、Issue、プルリクエスト、エディタ、エージェントパネル、またはサードパーティ製プロジェクト管理ツールから作業を開始・追跡するとともに、並列セッションを実行できる。[5][6]
- **Copilot CLI**: すべてのプランで利用でき、ターミナルから作業し、コーディングエージェントへタスクを委任し、ローカルまたはGitHub上でコード変更とコミットを行い、プログラマティックモードで実行できる。[2][5]
- **コードレビューとモダナイゼーション**: Pro以上のプランで利用でき、GitHub上でのプルリクエストレビュー、コードエディタ内でのローカルファイル差分レビュー、`instructions.md`によるカスタムレビュー指示、およびJavaと.NET向けのアプリモダナイゼーションを提供する。[5][6]
- **自動化とサードパーティ製エージェント**: 再利用可能なエージェントタスクをオンデマンド、スケジュール、または対応トリガーから実行でき、対象プランではClaude by Anthropicや[OpenAI Codex](https://mimirwiki.com/ja/wiki/openai-codex)などのサードパーティ製コーディングエージェントにタスクを委任できる。[5][6]

カスタマイズおよび外部ツール連携のため、GitHub Copilotはカスタム指示（custom instructions）、カスタムエージェント、エージェントスキル、Copilot Spaces、Copilot Connectors、プラグインに加え、IDEエージェントモードとCopilot in the cloudの双方で[Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）サーバーに対応している。[5][6]

## GitHub Copilotのコンテンツフィルタリング、プライバシー、エンタープライズガバナンス

GitHub Copilotは2026-11-23時点で、すべての標準AIモデルに対してコンテンツフィルタリングを適用しており、入力プロンプトと出力補完の双方を有害、攻撃的、または話題から逸脱した内容を検出するフィルターに通過させている。[4] 有効化されている場合、GitHub Copilotはコード参照（code referencing）機能付きの公開コード一致フィルターも実行し、この機能はFree、Pro、Pro+、Maxの各プランに含まれると記載されている。[4][5]

2026-11-23時点の製品プライバシーFAQにおいて、GitHubは利用するクライアント環境と機能に応じてGitHub Copilotが以下の4区分の個人データを処理するとしている。[6]

- **ユーザーエンゲージメントデータ（User Engagement Data）**: 採用または却下された補完、エラーメッセージ、システムログ、製品利用指標など、操作中に記録される仮名識別子。[6]
- **プロンプト（Prompts）**: 提案を生成するために送信されるチャットまたはコード入力および周辺のコンテキスト。[6]
- **提案（Suggestions）**: プロンプトに対して返されるAI生成コード行またはチャット応答。[6]
- **フィードバックデータ（Feedback Data）**: 高評価・低評価のリアクション、任意コメント、サポートへのフィードバックといったリアルタイムのユーザーフィードバック。[6]

組織・企業向けには、Copilot BusinessおよびCopilot Enterpriseが集中シート管理、Copilotポリシー制御、共有クレジットプール、超過利用の可否を決定する管理者向け支出上限機能を追加している。[2][3][6] またエンタープライズプランは、SAML SSO認証、github.comでのユーザー管理、組織の利用状況メトリクス、エンタープライズ級セキュリティ、知的財産権補償といった個人向けプランでは除外される機能を含んでおり、監査ログはPro+以上から掲載されている。[5] データレジデンシー対応またはFedRAMP準拠のリクエスト処理を必要とする組織では、該当リクエストに10%のモデル乗数加算が発生する。[3]

## よくある質問

### GitHub Copilotのプランと料金はどのようになっていますか？

2026-11-23時点で、GitHubは5種類の個人向けプランを提供しています。Free（0米ドル）、Student（認証済み学生向け0米ドル）、Pro（月額10米ドル）、Pro+（月額39米ドル）、Max（月額100米ドル）です。組織・企業向けには、Copilot Business（1シートあたり月額19米ドル）、Copilot Enterprise（1シートあたり月額39米ドル）、およびCopilot access（GitHub Enterprise Cloudライセンス保有ユーザーは0米ドル、Copilot Standaloneは1ユーザーあたり月額10米ドル、従量課金は別途請求）が掲載されています。 [2][3][5]

### GitHub CopilotにおけるGitHub AI Creditsはどのように機能しますか？

2026-11-23時点で、1 GitHub AI Creditは0.01米ドルに相当し、チャット、エージェントモード、コードレビュー、Copilot in the cloud、Copilot CLI、Copilotアプリの利用料が選択モデルとタスクの複雑さに応じてクレジットで消費されます。インラインコード補完と次の編集提案はクレジットを消費せず、有料プランでは無制限です。BusinessおよびEnterpriseの各シートは組織全体で共有されるプールにクレジットを合算し、任意で従量課金の支出予算を設定すると75%、90%、100%の時点でアラートが通知されます。 [3][5][6]

### GitHub CopilotはどのAIモデルに対応していますか？

2026-11-23時点で、GitHub CopilotはOpenAI（GPT-5およびGPT-6シリーズ）、Anthropic（Claude Fable、Haiku、Sonnet、Opusシリーズ）、Google（Gemini 3.7、3.8およびGemini 4シリーズ）、Microsoft（MAI Codeシリーズ）、xAI（Grok 4.5〜4.7）、Kimi（Kimi K3）のモデルに対応しています。ユーザーはCopilot Fusionによる自動ルーティングを利用するか、特定のモデルを手動選択できるほか、独自のAPIキーでクラウドプロバイダーを接続したり、OllamaやFoundry Localを通じてローカルモデルを実行したりすることもできます。 [4][5][6]

### GitHub Copilot Freeにはどのような機能が含まれますか？

2026-11-23時点で、GitHub Copilot Freeはクレジットカード登録不要の0米ドルで利用でき、月間2,000回のインラインコード補完、制限付きのチャットおよびエージェント利用、Copilot CLI、Copilotアプリ、Copilot Spaces、エージェントモードでのModel Context Protocolサーバー連携、Copilot Fusion Standard、コミュニティサポートが含まれます。コードレビュー、Copilot in the cloud、割り当てたエージェントによるプルリクエスト作成、追加クレジットの購入は含まれません。 [2][5][6][9]

### GitHub CopilotはどのIDEやプラットフォームに対応していますか？

2026-11-23時点で、GitHub CopilotはVisual Studio Code、Visual Studio、JetBrains IDE、Xcode、Vim、Neovim、Zed、Eclipse、Raycast、SQL Server Management Studioで利用できます。さらに、Copilot CLIによるターミナル、GitHub Copilotデスクトップアプリ、github.com、GitHub Mobile、Slack、Microsoft Teamsでも動作します。なお、GitHub Enterprise Serverでは利用できません。 [2][5][6]

### MicrosoftはSEC Form 10-KでGitHub Copilotをどのように報告していますか？

Microsoft Corporationの2026年6月30日終了会計年度のForm 10-Kにおいて、GitHubのクラウドサービスはIntelligent Cloudセグメントのサーバー製品およびクラウドサービス区分に含まれ、Azureおよびその他のクラウドサービスの収益成長指標に算入されています。同Form 10-Kは、GitHubをソフトウェア開発ライフサイクル全体にわたってAIおよびエージェントベースの機能を取り込んだクラウドおよびオンプレミスのコラボレーションツールを提供するプラットフォームとして説明していますが、これらの開示ではGitHub Copilot単独の収益は報告されていません。 [1]

## 引用できる文

- GitHubは2021年6月29日、OpenAI Codexを搭載したGitHub Copilotのテクニカルプレビューを公開した。 [7]
- GitHubは2022年6月21日、個人開発者向けに月額10米ドルまたは年額100米ドルでGitHub Copilotの一般提供を開始した。 [8]
- GitHubは2024年12月18日、月間2,000回のコード補完と50回のチャットメッセージを含むGitHub Copilot FreeをVisual Studio Codeで提供開始した。 [9]
- 2026-11-23時点で、GitHubは個人向け有料CopilotプランをProが月額10米ドル、Pro+が月額39米ドル、Maxが月額100米ドルと掲載している。 [2][5]
- 2026-11-23時点で、GitHubはCopilot Businessを付与シート1件あたり月額19米ドル、Copilot Enterpriseを付与シート1件あたり月額39米ドルとしている。 [2][3]
- 2026-11-23時点で、1 GitHub AI Creditは0.01米ドルに相当し、有料プランではインラインコード補完と次の編集提案（next edit suggestions）でクレジットを消費しない。 [3][6]
- 2026-11-23時点で、GitHub CopilotはOpenAI、Anthropic、Google、Microsoft、xAI、Kimiのモデルに対応し、独自のAPIキーを用いるクラウドプロバイダー連携（BYOK）やOllamaおよびFoundry Localによるローカルモデル実行もサポートしている。 [4][5][6]
- Microsoft Corporationの2026年6月30日終了会計年度のForm 10-Kは、GitHubのクラウドサービスをIntelligent Cloudセグメントのサーバー製品およびクラウドサービス区分に含めている。 [1]

## 年表

- 2021-06-29: GitHubがOpenAIと共同開発しOpenAI Codexを搭載したGitHub Copilotの限定テクニカルプレビューを開始した。 [7]
- 2022-06-21: GitHubがすべての個人開発者向けに月額10米ドルまたは年額100米ドルでGitHub Copilotの一般提供を開始し、認証済み学生および人気オープンソースプロジェクトのメンテナーに無料アクセスを提供した。 [8]
- 2024-12-18: GitHubの開発者数が1億5,000万人を突破する中、GitHubがVisual Studio CodeおよびGitHubダッシュボードに統合されたGitHub Copilot Freeの提供を開始した。 [9]
- 2026-06-30: Microsoft Corporationが2026会計年度を終了し、Form 10-KにおいてGitHubのクラウドサービスをIntelligent Cloudセグメント内で報告した。 [1]

## 出典

1. Microsoft Corporation Form 10-K for the fiscal year ended June 30, 2026. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (閲覧 2026-11-23; tier 1: government or public registry)
2. Plans for GitHub Copilot - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/get-started/plans (閲覧 2026-11-23; tier 3: official site)
3. GitHub Copilot seats and billing cycles for organizations and enterprises - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/concepts/billing-and-usage/organizations-and-enterprises/seats-and-billing-cycles (閲覧 2026-11-23; tier 3: official site)
4. Supported AI models in GitHub Copilot - GitHub Docs. GitHub Docs. https://docs.github.com/en/copilot/reference/ai-models/supported-models (閲覧 2026-11-23; tier 3: official site)
5. GitHub Copilot · Plans & pricing for every developer & team · GitHub. GitHub. https://github.com/features/copilot/plans (閲覧 2026-11-23; tier 3: official site)
6. GitHub Copilot · Your AI coding agent · GitHub. GitHub. https://github.com/features/copilot (閲覧 2026-11-23; tier 3: official site)
7. Introducing GitHub Copilot: your AI pair programmer - The GitHub Blog. The GitHub Blog. 公開 2021-06-29. https://github.blog/news-insights/product-news/introducing-github-copilot-ai-pair-programmer/ (閲覧 2026-11-23; tier 3: official site)
8. GitHub Copilot is generally available to all developers - The GitHub Blog. The GitHub Blog. 公開 2022-06-21. https://github.blog/news-insights/product-news/github-copilot-is-generally-available-to-all-developers/ (閲覧 2026-11-23; tier 3: official site)
9. Announcing 150M developers and a new free tier for GitHub Copilot in VS Code - The GitHub Blog. The GitHub Blog. 公開 2024-12-18. https://github.blog/news-insights/product-news/github-copilot-in-vscode-free/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "GitHub Copilot." 版 6eb895b4, 2026-11-23. https://mimirwiki.com/ja/wiki/github-copilot
