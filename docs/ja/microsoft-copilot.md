---
title: "Microsoft Copilot"
subtitle: "Windows、Microsoft 365、Azure全体に統合されたMicrosoftの一般消費者・企業向け生成AIアシスタント"
canonical_url: https://mimirwiki.com/ja/wiki/microsoft-copilot
language: ja
page_class: entity
revision_sha256: 972607ace4fee878015c3ffa74543ab26b54faee7608f4cb77027928724b5523
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ja/wiki/microsoft-copilot.md
  txt: https://mimirwiki.com/ja/wiki/microsoft-copilot.txt
  json: https://mimirwiki.com/ja/wiki/microsoft-copilot.json
  jsonld: https://mimirwiki.com/ja/wiki/microsoft-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/microsoft-copilot
  ko: https://mimirwiki.com/ko/wiki/microsoft-copilot
  zh: https://mimirwiki.com/zh/wiki/microsoft-copilot
---

# Microsoft Copilot

> 2026年11月時点で、Microsoft Copilotはcopilot.cloud.microsoftで提供される無料のWebグラウンディング版Copilot Chat、有償のシートライセンスであるMicrosoft 365 Copilot（エンタープライズ向けアドオンは1ユーザーあたり月額30ドル、中小企業向けバンドルのMicrosoft Copilot Businessは1ユーザーあたり月額18〜32ドル）、最上位のMicrosoft 365 E7プラン、および従量課金制のCopilot StudioとCoworkエージェントで構成されている。2026年後半には、MicrosoftはOpenAI以外のモデルカタログを拡充し、AnthropicのClaudeモデルを公式の復委託先（サブプロセッサー）として統合した。

Microsoft Copilotは、Microsoft Corporationが一般消費者向けWebおよびモバイルインターフェース、Windows 11、Microsoft 365生産性スイート、Copilot Studioにわたって提供する生成AIアシスタントおよびエージェントプラットフォームの主力製品群である。OpenAIとAnthropicのフロンティア基盤モデルをMicrosoft Graphの組織データ（Work IQ）と連携させ、対話型検索、文書・コード生成、多段階の自律型エンタープライズワークフローを実現している。

**別名:** Microsoft 365 Copilot, Copilot Chat, Copilot Studio, Bing Chat

## 主要な事実

- **開発元:** Microsoft Corporation（SEC CIK 0000789019） [1]
- **エンタープライズ向けアドオン価格:** 1ユーザーあたり月額30ドル（年間契約） (時点 2026-11-23) [2]
- **中小企業（SMB）向け価格:** アドオンは1ユーザーあたり月額18ドル、Microsoft 365 Businessバンドルは月額23.50〜32ドル (時点 2026-11-23) [2]
- **エージェントのターン制限:** Copilot Studioにおいて1ターンあたり最大90分、ツール呼び出し最大200回 (時点 2026-11-23) [7]

## ファクトシート

- **開発元:** Microsoft Corporation [1]
- **主要Webエンドポイント:** copilot.microsoft.com（一般消費者向け）/ copilot.cloud.microsoft（法人・教育機関向け） [4]
- **グラウンディング基盤:** Microsoft Graph / Work IQおよびBing Webインデックス [4]
- **基盤モデルプロバイダー:** OpenAI（Azure OpenAI Service）およびAnthropic（Claude復委託先） [5]
- **エンタープライズライセンス:** Microsoft 365 Copilotアドオン、Microsoft 365 E7、Microsoft Copilot Business [3]
- **エージェントプラットフォーム:** Microsoft Copilot Studio（従量課金またはメッセージパック課金） [7]
- **エンタープライズデータ保護:** 商用プロンプトおよび応答は基盤モデルの学習対象外 [6]
- **親会社の2026会計年度売上高:** 2026会計年度（2026年6月30日終了）Form 10-KにおけるMicrosoft総売上高331,839百万ドル（3,318.4億ドル） [1]

## Microsoft Copilotの概要と製品アーキテクチャ

Microsoft Copilotは、一般消費者、法人、開発者向けサーフェス全体にわたるMicrosoft Corporationの生成AIアシスタントの統一ブランドおよび技術オーケストレーションフレームワークである。[1][4] 当初2023年にBing ChatおよびMicrosoft 365 Copilotとして提供が開始され、その後Microsoft Copilotブランドへ統合された同プラットフォームは、大規模言語モデル（LLM）をWeb検索インデックス、OSテレメトリ、企業の組織グラフと組み合わせている。[1][4]

法人向けサービスのアーキテクチャの中核を担うのが**Work IQ**（旧称Microsoft Graphグラウンディング）であり、既存のロールベースアクセス制御（RBAC）およびMicrosoft Purviewの秘密度ラベルを適用したまま、テナント内のメール、Microsoft Teamsチャット、SharePointサイト、OneDriveドキュメント、予定表メタデータを基盤モデルに接続する。[4][6] 認証済みの企業ユーザーが`copilot.cloud.microsoft`またはOfficeアプリケーション内でプロンプトを送信すると、Copilotオーケストレーターはユーザーに閲覧権限のあるMicrosoft Graph範囲に対して前処理とセマンティック検索を実行し、取得した引用情報でプロンプトを補強したうえで選択されたLLMへペイロードをルーティングし、応答をストリーミングする前に後処理のコンプライアンス、グラウンディング、責任あるAI（Responsible AI）の検査を実施する。[4][6]

## Microsoft Copilotの製品ティア、Microsoft 365 E7および料金体系

MicrosoftはMicrosoft Copilotを、無料の一般消費者向けアクセス、商用ベースラインチャット、シート単位の生産性アドオン、および従量課金制のエージェント消費という区分で提供している。[2][3][4]

| ティア / プラン | 対象ユーザー | 主な機能 | 価格（2026年11月時点） |
| --- | --- | --- | --- |
| **Microsoft Copilot（一般消費者向け）** | 個人ユーザー | Webグラウンディングチャット、画像生成、音声機能、Windows・モバイルアプリ | 無料（有償のCopilot Proティアあり） [4] |
| **Microsoft Copilot Chat** | 法人・教育機関のEntra IDユーザー | エンタープライズデータ保護（EDP）付きWebグラウンディングチャット、Copilot Pages、従量課金エージェント | 対象M365ライセンスに標準付帯（エージェントは従量課金） [4] |
| **Microsoft Copilot Business** | 中小企業（最大300ユーザー） | Word、Excel、PowerPoint、Outlook、Teamsにおける業務データグラウンディング型Copilot | アドオンは1ユーザーあたり月額18ドル、M365 Businessバンドルは月額23.50〜32ドル [2] |
| **Microsoft 365 Copilot（エンタープライズ）** | 大企業テナント（E3/E5が前提） | フルWork IQグラウンディング、アプリ組み込みスキル、Copilot Studioエージェント利用権を含む | 1ユーザーあたり月額30ドル（年間契約） [2][3] |
| **Microsoft 365 E7** | フロンティア企業向け導入 | M365 E5、Microsoft 365 Copilot、高度なエージェント機能を統合した包括的エンタープライズスイート | エンタープライズ契約（EA）価格 [3] |

シート単位のライセンスに加え、Microsoftは**Copilot Cowork**、**Copilot Code**、**Copilot Autopilot**といった特化型の自律ワークフロー向けに従量課金モデルを導入しており、リンクされたAzureサブスクリプションを通じた従量課金、または事前購入するCopilot Credit容量パックによって課金できる。[3][5]

## Microsoft CopilotのマルチモデルオーケストレーションとAnthropic統合

初期のMicrosoft CopilotはAzure OpenAI Service上でホストされるOpenAIモデルのみに依存していたが、Microsoftは2025年から2026年にかけてCopilotをマルチモデルオーケストレーションプラットフォームへと拡張した。[4][5] Microsoftの商用サービス文書およびMicrosoft Learnのドキュメントに示されている通り、Microsoftは自社開発の内部モデルに加え、OpenAIとAnthropic双方のフロンティアモデルを統合している。[4][5]

具体的には、Microsoftは**Anthropic**を公式のMicrosoftオンラインサービス復委託先（Subprocessor）として採用し、企業の管理者やCopilot Studioの開発者がMicrosoft 365 Copilot、Copilot Cowork、Copilot Studio内で高度な推論、コーディング、多段階リサーチのワークフローにAnthropicのClaudeモデルを有効化できるようにした。[5] Anthropicモデルを呼び出す場合も、顧客データは引き続きMicrosoftの商用規約およびエンタープライズデータ保護（EDP）の約束の下で管理されるが、リージョンの提供状況に応じて復委託先データ保護契約に基づきAnthropicの管理インフラ上でリクエストが処理される場合がある。[5][6]

## Copilot Studioとエージェントのランタイムクォータ

Microsoft Copilot Studioは、Microsoft Copilot ChatおよびMicrosoft Teamsへ直接公開できるカスタム宣言型エージェント、自律ワークフロー、コンピューター操作エージェントを作成するためのローコードおよびプロコード開発環境である。[4][7] 暴走実行を防止しマルチエージェントのオーケストレーションを適切に管理するため、MicrosoftはCopilot Studioエージェントに対して厳格なランタイムクォータと動作制限を設けている。[7]

- **最大ターン実行時間**：単一のエージェントオーケストレーションターンは、タイムアウトするまで最大**90分**（5,400秒）実行できる。[7]
- **1ターンあたりのツール呼び出し回数**：単一ターン内で、コネクタ、アクション、プラグイン全体を通じて最大**200回**のツール呼び出しをサポートする。[7]
- **個別ツールおよびコネクタのタイムアウト**：標準的な同期ツールまたはコネクタの実行は**120秒**でタイムアウトする。[7]
- **エージェントフロー / ワークフローのタイムアウト**：組み込みのPower Automateおよびエージェントワークフローの同期実行上限は**660秒**（11分）である。[7]
- **接続済みエージェントおよび外部エージェント**：内部で接続されたCopilot Studioエージェントへの委任呼び出しは最大**5,400秒**（90分）まで実行できる一方、外部のA2A/MCPエージェントへの呼び出しは**300秒**（5分）でタイムアウトする。[7]
- **会話コンテキストとストリーミング**：オーケストレーションは1会話あたり**100メッセージ**のスライディングコンテキストウィンドウを維持し、Microsoft Teamsにおけるリアルタイムストリーミング応答は1ストリームセグメントあたり**2分**を上限としている。[7]

## Microsoft Copilotのエンタープライズデータ保護とガバナンス

Microsoft Entra IDアカウントでサインインする法人、政府機関、教育機関に対して、MicrosoftはMicrosoft製品条項（Product Terms）およびデータ保護補遺（DPA）に基づく**エンタープライズデータ保護（EDP）**を適用している。[6] EDPの下では、ユーザーのプロンプト、アップロードされたファイル、Microsoft Graphのグラウンディングデータ、および生成された応答はテナント単位で論理的に隔離され、転送時および保存時に暗号化されるほか、**パブリックまたは基盤となる大規模言語モデルの学習に使用されることは一切ない**。[6]

Copilotは既存のMicrosoft Purviewガバナンスポリシーを厳格に継承しており、ドキュメントがRights Management Services（RMS）で暗号化されている場合や、データ抽出を制限する秘密度ラベルが付与されている場合、Copilotは要約をブロックするか、制限付きラベルおよび透かしを生成結果へ直接引き継ぐ。[6] 管理者はMicrosoft Purview Audit、Communication Compliance、およびeDiscoveryを通じて、すべてのプロンプト操作、エージェントのツール呼び出し、引用情報を監査できる。[6]

## よくある質問

### Microsoft Copilot ChatとMicrosoft 365 Copilotの違いは何ですか？

Microsoft Copilot Chatは、対象のMicrosoft Entra ID法人・教育機関アカウント向けにcopilot.cloud.microsoftで追加シート費用なしに提供される基本のWebグラウンディング型アシスタントであり、エンタープライズデータ保護と従量課金制のエージェント利用に対応しています。Microsoft 365 Copilot（エンタープライズ向けは1ユーザーあたり月額30ドル）では、ユーザーのメール、チャット、ファイル全体を対象とするWork IQ（Microsoft Graph）グラウンディングに加え、Word、Excel、PowerPoint、Outlook、Teamsアプリ内への直接統合が追加されます。 [2][4]

### 中小企業向けのMicrosoft Copilot Businessの料金はいくらですか？

中小企業（最大300シート）向けのMicrosoft Copilot Businessは、単体アドオンとして1ユーザーあたり月額18ドルで提供されているほか、年間契約を条件にMicrosoft 365 Business Basic、Standard、またはPremiumプランと組み合わせたプロモーション価格のバンドルとして1ユーザーあたり月額23.50〜32ドルで利用できます。 [2]

### Microsoft CopilotはOpenAIに加えてAnthropicのClaudeモデルも使用していますか？

はい。MicrosoftはマルチモデルアーキテクチャでCopilotを運用しており、Anthropicを公式のオンラインサービス復委託先（Subprocessor）に指定しています。これにより、企業テナントはMicrosoft 365 Copilot、Copilot Studio、Copilot Cowork内で、OpenAIおよびMicrosoftのモデルと並行してAnthropicのClaudeモデルを利用できます。 [4][5]

### Microsoft Copilot Studioのエージェントにおける実行時間とツール呼び出しの上限はどのようになっていますか？

2026年後半時点で、Copilot Studioのエージェントは1ターンあたり最大90分（5,400秒）実行でき、1ターンにつき最大200回のツール呼び出しを行えます。個別の同期ツール呼び出しは120秒、エージェントフローは660秒、外部エージェント呼び出しは300秒でタイムアウトします。 [7]

### Microsoftは企業向けCopilotのプロンプトを基盤AIモデルの学習に使用しますか？

いいえ。商用Entra IDユーザー向けのエンタープライズデータ保護（EDP）の約束に基づき、プロンプト、取得されたMicrosoft Graphコンテキスト、および生成された応答は顧客境界内に隔離され、基盤モデルの学習には使用されません。 [6]

## 引用できる文

- Microsoft 365 Copilotのエンタープライズ向け価格は1ユーザーあたり月額30ドルであり、Microsoft Copilot Businessは月額18ドルのアドオンおよび月額23.50〜32ドルの中小企業向けバンドルを提供している。 [2][3]
- MicrosoftはAnthropicをオンラインサービス復委託先（Subprocessor）として採用し、Microsoft 365 Copilot、Copilot Studio、Copilot Cowork全体でClaudeモデルを提供している。 [5]
- Microsoft Copilot Studioは、1ターンあたりの最大実行時間を90分（5,400秒）、ツール呼び出しを最大200回に制限している。 [7]
- Copilot Studioにおける個別ツール呼び出しのタイムアウトは120秒、エージェントワークフローは660秒、外部エージェント呼び出しは300秒である。 [7]
- エンタープライズデータ保護（EDP）の下では、商用Entra IDユーザーのプロンプトおよび応答は基盤モデルの学習に使用されない。 [6]

## 年表

- 2023-02: MicrosoftがBing Chatの名称で最初の生成AI検索アシスタントをリリースした。 [1]
- 2023-11: 企業顧客向けにMicrosoft 365 Copilotの一般提供（GA）が開始され、Bing ChatがMicrosoft Copilotへリブランドされた。 [1]
- 2026-06-30: Microsoftが年間売上高3,318.4億ドルで2026会計年度を終え、Form 10-KにおいてMicrosoft 365、Windows、GitHub、Azure AIインフラ全体へのCopilotの拡大を報告した。 [1]
- 2026-11: MicrosoftがMicrosoft 365 E7、中小企業向けMicrosoft Copilot Businessの料金（1ユーザーあたり月額18〜32ドル）、AnthropicのClaude復委託先統合、および90分・200回ツール呼び出しへ拡張されたCopilot Studioランタイム上限の詳細を公開した。 [2][3][5][7]

## 出典

1. Microsoft Corporation Form 10-K for the Fiscal Year Ended June 30, 2026. U.S. Securities and Exchange Commission (SEC). 公開 2026-07-29. https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (閲覧 2026-11-23; tier 1: government or public registry)
2. Microsoft Copilot Plans and Pricing - AI for Business | Microsoft 365. Microsoft Corporation. https://www.microsoft.com/en-us/copilot/pricing/business (閲覧 2026-11-23; tier 3: official site)
3. License Options for Microsoft Copilot | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-license-options (閲覧 2026-11-23; tier 3: official site)
4. What is Microsoft Copilot? | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-overview (閲覧 2026-11-23; tier 3: official site)
5. Claude models from Anthropic in Microsoft Online Services | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/implement/connect-to-ai-subprocessor (閲覧 2026-11-23; tier 3: official site)
6. Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/enterprise-data-protection (閲覧 2026-11-23; tier 3: official site)
7. Agent runtime limits - Microsoft Copilot Studio | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/runtime-limits (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Microsoft Copilot." 版 972607ac, 2026-11-23. https://mimirwiki.com/ja/wiki/microsoft-copilot
