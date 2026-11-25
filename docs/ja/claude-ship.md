---
title: "Claude Ship"
subtitle: "GitHubプルリクエストのレビュー、修正、承認を行うAnthropicのエージェント群"
canonical_url: https://mimirwiki.com/ja/wiki/claude-ship
language: ja
page_class: entity
revision_sha256: fb74e70e2c433bc2a35728852143855c8bcb080a962cd5570dfd077525687512
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/claude-ship.md
  txt: https://mimirwiki.com/ja/wiki/claude-ship.txt
  json: https://mimirwiki.com/ja/wiki/claude-ship.json
  jsonld: https://mimirwiki.com/ja/wiki/claude-ship.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude-ship
  ko: https://mimirwiki.com/ko/wiki/claude-ship
  zh: https://mimirwiki.com/zh/wiki/claude-ship
  es: https://mimirwiki.com/es/wiki/claude-ship
---

# Claude Ship

> Claude Shipは、Claude TeamおよびEnterpriseプラン向けにAnthropicが提供する3つのGitHubプルリクエスト向けエージェント群であり、Code Review（一般提供）、PR Steward（パブリックベータ）、Claude Approvals（パブリックベータ）で構成される。2026-11-23に発表され、コードレビューの指摘、修正コミット、ポリシーに基づく承認チェックを自動化する一方、マージの強制はリポジトリ設定とGitHubルールに委ねる。

Claude Shipは、GitHubプルリクエストのレビュー、修正コミットのプッシュ、および承認ポリシーの評価を行うためにAnthropicが開発したAIエージェント群である。2026-11-23に発表されたClaude Shipは、Code Review（2026-10-15より一般提供）、PR Steward（パブリックベータ）、およびClaude Approvals（パブリックベータ）の3つのエージェントで構成される。Claude ShipはClaude TeamおよびEnterpriseプランで利用でき、リポジトリ設定やGitHubのブランチ保護またはルールセット制御と連携して動作する。

**別名:** Claude Ship エージェント, /ship

## 主要な事実

- **開発元:** Anthropic [1]
- **発表日:** 2026-11-23 [1]
- **コンポーネントの提供状況:** Code Review：一般提供、PR StewardおよびClaude Approvals：パブリックベータ (時点 2026-11-24) [1]
- **対象プラン:** GitHub上のClaude TeamおよびEnterpriseプラン (時点 2026-11-24) [4]

## ファクトシート

- **開発元:** Anthropic [1]
- **発表日:** 2026-11-23 [1]
- **構成要素:** Code Review、PR Steward、Claude Approvals [4]
- **Code Reviewの状況:** 一般提供（2026-10-15より開始、2026-03-09よりリサーチプレビュー） (時点 2026-11-24) [3]
- **PR Stewardの状況:** パブリックベータ (時点 2026-11-24) [5]
- **Claude Approvalsの状況:** パブリックベータ (時点 2026-11-24) [6]
- **対応プラットフォーム:** GitHub（github.com、Code ReviewとPR StewardはGitHub Enterprise Serverに対応） (時点 2026-11-24) [5]
- **対象プラン:** Claude TeamおよびEnterprise (時点 2026-11-24) [4]
- **課金モデル:** トークン従量課金（Claude Approvalsに基本料金はないが、ポリシー分類器およびトリガーされたCode Reviewはトークン課金） (時点 2026-11-24) [1]
- **CLIエントリーポイント:** Claude Code内の /ship コマンド [4]

## Claude Shipの概要とリリース履歴

Claude Shipは、GitHubプルリクエストのレビュー、修正、およびポリシーに基づく承認チェックを進めるために[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)が提供するエージェント群である。[1][4] Anthropicは2026-11-23にClaude Shipを発表し、既存のCode Review製品と2つの新しいパブリックベータ版エージェントであるPR StewardおよびClaude Approvalsを統合した。[1] 同日、独立系テクノロジーメディアのTechCrunchとThe Vergeもこのリリースを報じた。[11][12]

Code ReviewはClaude Ship全体の発表より先に提供されており、Anthropicは2026-03-09にTeamおよびEnterprise組織向けにCode Reviewのリサーチプレビューを導入し、2026-10-15に一般提供を発表した。[2][3] 2026-11-24時点でCode Reviewは一般提供されている一方、PR StewardとClaude Approvalsはパブリックベータの段階にあり、一般提供日は発表されていない。[1][5][6] 開発者は個別のプルリクエストに対してClaude Code内で`/ship`を実行し、変更のプッシュ、プルリクエストの作成、レビューの実行、フィードバックや失敗したチェックへの対応を行うこともできる。[1][4]

## Claude Shipのエージェント構成とプルリクエストのワークフロー

Claude Shipは、設定済みのリポジトリ上で自動実行可能な3つのエージェントにプルリクエスト処理を分割している。[1][4]

- **Code Review**は、複数のエージェントを並列に用いて周辺のコードベースと照合しながらプルリクエストを検査し、誤検知を除外するための検証を行ったうえで、重大度順に問題を順位付けし、概要コメントと該当行へのインラインコメントを投稿する。[2][4] 管理者はリポジトリごとに`Quick`、`Standard`（デフォルト）、`Deep`のレビューレベルを選択できる。[3] Anthropicは一般提供時に、リサーチプレビュー期間中の約20分と比較して、ほとんどのレビューが6〜10分で完了するようになると説明した。[2][3] またAnthropicは、Claude Codeチームにおいて2026年6月から9月にかけてマージされたプルリクエスト数が2倍以上に増加した一方、リバートされた割合は40%以上減少したと報告している。[1]
- **PR Steward**は、クラウドセッション上でオープンなプルリクエストを監視し、変更対象コードに起因するCIチェックの失敗、マージコンフリクト、人間やCode Reviewなどのレビューツールからのフィードバック、およびClaude Approvalsチェックに対応するための修正コミットをプッシュする。[1][5] プッシュのたびに、PR Stewardは変更内容とその取り消し方法を説明するコメントを投稿する。[1] 開発者は`@claude`に指示を添えてコメントすることでPR Stewardを誘導でき、`@claude stop`とコメントするか`claude-pr-steward-watching`ラベルを削除することで停止できる。[1][5] デフォルトでは、PR Stewardはドラフトプルリクエスト、フォークからのプルリクエスト、ボットが作成したプルリクエスト、および書き込み権限を持たない作成者のプルリクエストをスキップする。[5] 製品ドキュメントでは、PR Stewardはプルリクエストの承認やマージを行わない設計であると明記されている。[4][5]
- **Claude Approvals**は、リポジトリ内の`.claude/approvals.yml`に保存されたポリシーファイルに基づいてプルリクエストを評価し、誰の承認がまだ必要かを報告する`Claude Approvals`ステータスチェックを追加する。[6] ポリシールールでは、ファイルパスのパターン、必要な人間の承認枠（seats）、Claudeがコメントのみを行うか承認レビューを投稿できるか、さらにはプルリクエストの属性や自然言語分類器に基づく条件を指定できる。[1][6] 条件はCIの結果を読み取れないため、CIチェックはGitHub側で別途必須チェックとして維持する必要がある。[6] Anthropicは、マージをブロックせずにポリシーの判定結果のみを報告する`observe`モードから運用を開始することを推奨している。[1][6]

## Claude ShipとGitHubのマージ制御

Claude Shipは、実際に何をマージできるかを決定する仕組みとして、リポジトリ設定とGitHubのガバナンス制御に依存している。[4] Anthropicはドキュメントの中で、Claude ShipはAIを使用しているためバグ、セキュリティ脆弱性、その他の問題を見逃す可能性があると注意喚起しており、マージ前に必要な承認を強制するためにブランチ保護を使用するよう推奨している。[4]

Claude Approvalsのチェックは、GitHubで必須チェックとして設定されている場合にのみマージをブロックし、通常はobserveモードではブロックしない。[4][6] またドキュメントは、チェックが必須に設定されていない場合、作成者自身が唯一の承認枠を満たせる設定（`seats: 1`）や`seats: 0`が指定されている場合、GitHubがClaudeの承認レビューを1件の必須承認としてカウントする場合、またはCode Reviewの通過を前提とせずにClaudeの承認を許可するルールがある場合、他の人間のレビューなしにプルリクエストがマージされ得ると警告している。[6] さらに、`.claude/approvals.yml`ポリシーファイルを追加すると、ルールに`claude/code_review`を明示しない限り、対象ファイルに対する自動Code Reviewが停止する。[6]

GitHub側のマージ強制は、プルリクエストマージキュー（2023-07-12より一般提供）、リポジトリルールセット向けの必須レビュアールール（2026-02-17より一般提供、チーム承認および`!`パス除外パターンに対応）、および従来のブランチ保護ルールからリポジトリルールセットへの自動移行機能（2026-08-11リリース）といったプラットフォーム機能を通じて動作する。[8][9][10]

## Claude Shipの提供範囲、設定、および課金

Claude Shipは2026-11-24時点で、GitHubリポジトリを使用するClaude TeamおよびEnterpriseプランで利用できる。[1][4] Claude組織のOwnerがclaude.aiのOrganization settings > Claude ShipからCode ReviewとPR Stewardを有効にし、GitHubアカウントを接続したうえで、GitHub組織のオーナーがインストールしたClaude GitHub Appを連携させることで導入でき、レビューはリポジトリにワークフローファイルを追加することなくAnthropicのインフラ上で実行される。[5][7] Claude Approvalsは前提条件が満たされた状態で、マージ権限を持つユーザーがデフォルトブランチに`.claude/approvals.yml`を追加すると有効化されるが、Claude組織のOwnerは組織全体でApprovalsを無効にすることもできる。[1][6]

| エージェント | 提供状況（2026-11-24時点） | GitHub環境 | コンプライアンス上の制限 |
| --- | --- | --- | --- |
| Code Review | 一般提供 | github.comおよびGitHub Enterprise Server | Zero Data Retention、HIPAA構成、CMEK |
| PR Steward | パブリックベータ | github.comおよびGitHub Enterprise Server（ポート443） | Zero Data Retention、HIPAA構成、CMEK |
| Claude Approvals | パブリックベータ | github.com（GitHub Enterprise Cloudを含む） | Zero Data Retention、HIPAA構成、CMEK（FERPAまたはAccess Transparency有効時は開始不可） |

Code ReviewとPR Stewardの利用はトークン単位で課金され、管理者は月間の利用上限額を設定できる。[1][5] Claude Approvals自体に基本料金はないが、observeモードを含め、ポリシーによって実行される分類器の評価およびトリガーされたCode Reviewにはトークン課金が適用される。[1][6] Claude Code上でローカルに`/ship`を実行した場合は、通常のClaude Code利用分として計上される。[1] 2026-11-23の発表時点で、Anthropicは対象となるClaude Enterprise組織が2027-01-15までに少なくとも10,000ドル相当のClaude Shipクレジットを申請でき、申請後30日間利用できると発表した。[1]

## よくある質問

### Claude Shipを構成する3つのエージェントは何ですか？

Claude Shipは、Code Review（一般提供）、PR Steward（パブリックベータ）、およびClaude Approvals（パブリックベータ）で構成されています。Code Reviewは重大度順に整理した指摘事項を投稿し、PR Stewardは失敗したチェック・コンフリクト・レビューコメントに対する修正コミットをプッシュし、Claude Approvalsはリポジトリのポリシーファイルに基づいてプルリクエストを評価します。 [1][4]

### PR StewardはGitHubプルリクエストを承認またはマージできますか？

いいえ。Anthropicのドキュメントでは、PR Stewardはプルリクエストの承認やマージを行わない設計であると記載されており、マージ前に必要な承認を強制するにはGitHubのブランチ保護またはルールセットを使用する必要があります。 [4][5]

### Claude Approvalsのobserveモードはどのように動作しますか？

observeモードでは、Claude Approvalsチェックがプルリクエスト上で実行され、マージをブロックすることなく .claude/approvals.yml のポリシーがどのような判定を下すかを表示します。ただし、observeモードであっても、ポリシーによってトリガーされた分類器の実行およびCode Reviewにはトークン課金が適用されます。 [1][6]

### Claude Shipを利用できないのはどのような組織ですか？

2026-11-24時点で、Zero Data Retentionを有効にしている組織、HIPAA構成を適用している組織、または顧客管理暗号化キー（CMEK）を使用している組織ではClaude Shipを利用できません。さらに、FERPAまたはAccess Transparencyの設定がある組織ではClaude Approvalsを開始できません。 [1][6]

## 引用できる文

- Anthropicは2026-11-23に、GitHub上のClaude TeamおよびEnterpriseプラン向けにClaude Shipを発表した。 [1]
- Code Reviewは2026-03-09にリサーチプレビューを開始し、2026-10-15に一般提供に達した。 [2][3]
- 2026-11-24時点で、PR StewardとClaude Approvalsはパブリックベータの段階にある。 [5][6]
- PR Stewardはプルリクエストを承認またはマージしないように設計されている。 [4][5]
- Claude Approvalsはリポジトリ内の .claude/approvals.yml ポリシーファイルからルールを読み取り、ルール条件内でCI結果を読み取ることはできない。 [6]
- Claude Shipの利用はトークン単位で課金され、observeモードにおける分類器の評価やポリシーによってトリガーされたCode Reviewも課金対象となる。 [1][6]

## 年表

- 2026-03-09: AnthropicがTeamおよびEnterprise組織向けに、Claude Code用Code Reviewのリサーチプレビューを導入した。 [2]
- 2026-10-15: AnthropicがQuick、Standard、Deepのリポジトリレビューレベルを備えたCode Reviewの一般提供を発表した。 [3]
- 2026-11-23: Anthropicが一般提供中のCode Reviewと、パブリックベータ版のPR StewardおよびClaude Approvalsを統合したClaude Shipを発表した。 [1]

## 出典

1. Introducing Claude Ship. Anthropic. 公開 2026-11-23. https://claude.com/resources/articles/introducing-claude-ship (閲覧 2026-11-24; tier 3: official site)
2. Bringing Code Review to Claude Code. Anthropic. 公開 2026-03-09. https://claude.com/resources/articles/code-review (閲覧 2026-11-24; tier 3: official site)
3. Code Review is now generally available. Anthropic. 公開 2026-10-15. https://claude.com/resources/articles/code-review-is-now-generally-available (閲覧 2026-11-24; tier 3: official site)
4. Claude Ship - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/claude-ship (閲覧 2026-11-24; tier 3: official site)
5. PR Steward - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/pr-steward (閲覧 2026-11-24; tier 3: official site)
6. Claude Approvals - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/approvals (閲覧 2026-11-24; tier 3: official site)
7. Set up Code Review - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/code-review-setup (閲覧 2026-11-24; tier 3: official site)
8. Required reviewer rule is now generally available. GitHub. 公開 2026-02-17. https://github.blog/changelog/2026-02-17-required-reviewer-rule-is-now-generally-available/ (閲覧 2026-11-24; tier 3: official site)
9. Automatically migrate branch protection rules to repository rulesets. GitHub. 公開 2026-08-11. https://github.blog/changelog/2026-08-11-automatically-migrate-branch-protection-rules-to-repository-rulesets/ (閲覧 2026-11-24; tier 3: official site)
10. Pull request merge queue is now generally available!. GitHub. 公開 2023-07-12. https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/ (閲覧 2026-11-24; tier 3: official site)
11. Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes. TechCrunch. 公開 2026-11-23. https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/ (閲覧 2026-11-24; tier 2: academic or news)
12. Claude AI can review pull requests and ship fixes on its own now. The Verge. 公開 2026-11-23. https://www.theverge.com/ai-artificial-intelligence/1040134/anthropic-claude-ship-ai-pull-requests (閲覧 2026-11-24; tier 2: academic or news)

## このページを引用する

Mimirwiki. "Claude Ship." 版 fb74e70e, 2026-11-24. https://mimirwiki.com/ja/wiki/claude-ship
