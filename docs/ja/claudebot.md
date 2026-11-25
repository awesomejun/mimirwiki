---
title: "ClaudeBot"
subtitle: "AIモデル学習用の公開ウェブコンテンツを収集するためAnthropicが運用するウェブクローラー"
canonical_url: https://mimirwiki.com/ja/wiki/claudebot
language: ja
page_class: entity
revision_sha256: 7e5ac18a7c99c46ea2226c96728b98194f7b71ae1362a939a4ed06bec4665655
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/claudebot.md
  txt: https://mimirwiki.com/ja/wiki/claudebot.txt
  json: https://mimirwiki.com/ja/wiki/claudebot.json
  jsonld: https://mimirwiki.com/ja/wiki/claudebot.jsonld
translations:
  en: https://mimirwiki.com/wiki/claudebot
  ko: https://mimirwiki.com/ko/wiki/claudebot
  zh: https://mimirwiki.com/zh/wiki/claudebot
  es: https://mimirwiki.com/es/wiki/claudebot
---

# ClaudeBot

> ClaudeBotは、生成AIモデル向けに公開ウェブコンテンツを収集するためAnthropicが運用する学習用ウェブクローラーである。Anthropicは、検索インデックス作成用のClaude-SearchBotおよびユーザー主導のリクエスト用のClaude-UserとClaudeBotを分離している。サイト所有者はrobots.txtを通じてClaudeBotをブロックまたは速度制限でき、2026年10月30日からはAnthropicがIETF aipref草案の学習プリファレンスシグナルも認識している。

ClaudeBotは、Claudeを含む生成AIモデルの学習に利用される可能性のある公開ウェブコンテンツを収集するため、Anthropicが運用する自動ウェブクローラーである。AnthropicはClaudeBotとあわせて、検索インデックス作成用のClaude-SearchBot、およびユーザー主導のクエリに応じてページを取得するClaude-Userという2つの別個のウェブロボットを文書化している。ウェブサイト所有者は、RFC 9309で定義されたrobots.txtディレクティブ（非標準のCrawl-delay拡張を含む）によってClaudeBotを制限またはレート制限でき、2026年10月30日からはAnthropicがIETF aiprefの草案作業に基づく機械可読なAI学習拒否プリファレンスシグナルの認識を開始した。2024年にはウェブサイト運営者からClaudeBotによる大量のリクエストが報告され、Anthropicが2026年11月17日に提出したForm S-1/A-3届出書では、ウェブクローリング慣行をめぐる継続中の訴訟が開示されている。

**別名:** Anthropicウェブクローラー, ClaudeBotクローラー

## 主要な事実

- **運営主体:** Anthropic (時点 2026-11-23) [4]
- **プロダクトトークン:** ClaudeBot (時点 2026-11-23) [4]
- **公表目的:** 生成AIモデル学習用の公開ウェブコンテンツ収集 (時点 2026-11-23) [4]
- **関連ボット:** Claude-SearchBot（検索インデックス作成）およびClaude-User（ユーザー主導のページ取得） (時点 2026-11-23) [4]
- **オプトアウト制御:** robots.txtディレクティブ、Crawl-delay拡張、IETF aipref草案のプリファレンスシグナル（2026-10-30より） (時点 2026-11-23) [4]

## ファクトシート

- **名称:** ClaudeBot [4]
- **種別:** 自動ウェブクローラー（学習用クローラー） [4]
- **運営主体:** Anthropic (時点 2026-11-23) [4]
- **運営法人:** Anthropic, PBC（デラウェア州公益法人、カリフォルニア州サンフランシスコ所在） (時点 2026-11-17) [2]
- **プロダクトトークン:** ClaudeBot (時点 2026-11-23) [4]
- **公表目的:** AIモデル学習用の公開ウェブコンテンツ収集 (時点 2026-11-23) [4]
- **Anthropicの関連ボット:** Claude-SearchBot（検索インデックス作成）、Claude-User（ユーザー指示による取得） (時点 2026-11-23) [4]
- **排除プロトコル:** ロボット排除プロトコル（robots.txt、IETF RFC 9309） [1]
- **レート制限ディレクティブ:** Crawl-delay（非標準のrobots.txt拡張） (時点 2026-11-23) [4]
- **学習プリファレンスシグナル:** IETF aipref草案に基づくAI学習拒否シグナル（2026-10-30より認識） (時点 2026-11-23) [4]
- **回避防止ポリシー:** クロール対象サイトのCAPTCHAバイパスを試みない (時点 2026-11-23) [4]
- **プライバシー文書:** Anthropicプライバシーポリシー（2026-09-10発効）および別個の非ユーザープライバシーポリシー (時点 2026-09-10) [5]
- **公開IPリストURL:** https://claude.com/crawling/bots.json（IPv4プレフィックス14件、creationTime 2026-10-20T00:00:00Z） (時点 2026-11-23) [10]

## ClaudeBotとAnthropicのウェブロボット群

ClaudeBotは、ウェブコンテンツの収集、検索結果のインデックス作成、および[Claude](https://mimirwiki.com/ja/wiki/claude)ユーザー向けのページ取得を担う3ロボット体制の一部として[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)が運用する学習用ウェブクローラーである。[4] 2026年11月23日時点で、Anthropicのクローラードキュメントは自動アクセスを3つの名称付きロボットに分離しており、ウェブサイト所有者がモデル学習、検索インデックス作成、ユーザー主導の取得それぞれに個別のアクセスポリシーを設定できるようにしている。[4]

| ボット | 公表されている機能 | robots.txtで無効化した場合の効果 |
| --- | --- | --- |
| ClaudeBot | 生成AIモデルの学習に寄与する可能性のあるウェブコンテンツを収集する | そのサイトの今後の資料をAnthropicのAIモデル学習データセットから除外すべきであることを示すシグナルとなる |
| Claude-SearchBot | 検索結果の関連性と精度を向上させるためにウェブコンテンツを巡回・分析する | 検索最適化のためのサイトコンテンツのインデックス作成を防ぎ、ユーザー検索結果での露出や精度が低下する可能性がある |
| Claude-User | Claudeユーザーからの質問に応じてウェブサイトにアクセスする | ユーザークエリに応じたサイトコンテンツの取得を防ぎ、ユーザー指示によるウェブ検索での露出が低下する可能性がある |

Anthropicは、これら3つのクローラーおよびフェッチャーを、Claude DuetのClaude-Agentを含め、ユーザーに代わってタスクを完了するためにClaudeが使用するAnthropicホスト型ブラウザと区別し、別個に文書化している。[4]

2026年11月23日時点で、Anthropicは自社のウェブロボットに関する4つの運用原則を掲げている。[4]

- 文書化された3つのボット名による透明性の高い識別
- 個別ドメインに対する負荷を抑えたクロール間隔の維持（適切な場合の`Crawl-delay`の尊重を含む）
- `robots.txt`で公開されたクロール禁止ディレクティブの遵守
- クロール対象サイトにおけるCAPTCHAバイパスの回避を含む、回避防止技術の尊重

## robots.txtおよびIETF aiprefによるClaudeBotの制御

ClaudeBotは、インターネット技術特別調査委員会（IETF）がRFC 9309で標準化したテキストファイルである[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)に公開されたサイトレベルのアクセスディレクティブに従う。[1][4] 2022年9月に発行されたRFC 9309は、Martijn Kosterが1994年に定義したロボット排除プロトコルを規定・拡張したものである。[1] RFC 9309では、`robots.txt`ファイルは`allow`および`disallow`ルールを、ASCII英字・アンダースコア・ハイフンのみを含む`user-agent`プロダクトトークンで始まるグループに整理し、クローラーは大文字・小文字を区別せずに一致するグループを探したうえで、該当する特定グループがない場合にワイルドカードグループ`user-agent: *`にフォールバックする。[1] パスの一致判定はURIパスの先頭オクテットから始まり、大文字・小文字を区別して最長一致ルールを適用すべきとされており、RFC 9309は`robots.txt`ルールがアクセス認可の手段ではないことも明記している。[1]

ウェブサイト全体からClaudeBotを除外する場合、2026年11月23日時点のAnthropicのドキュメントでは、サイトの最上位ディレクトリにある`robots.txt`ファイルに`User-agent: ClaudeBot`と`Disallow: /`を追加し、オプトアウトしたいすべてのサブドメインで同じ設定を繰り返すよう案内している。[4] リクエスト頻度を制限するため、Anthropicは`robots.txt`の非標準`Crawl-delay`拡張をサポートしている（例：`User-agent: ClaudeBot`に続けて`Crawl-delay: 1`）。[1][4]

2026年11月23日時点で、Anthropicはクローリングからオプトアウトするには`robots.txt`を更新する必要があると述べている。[4] Anthropicのボットが動作する送信元IPアドレスをブロックすると、クローラーがサイトの`robots.txt`ファイルを読み取れなくなる可能性があるため、AnthropicはIPブロックが確実に機能しない、または継続的なオプトアウトを保証しない場合があると指摘している。[4] AnthropicはクローラーのIPプレフィックスを`https://claude.com/crawling/bots.json`にてJSON形式で公開しており、2026年11月23日時点で同ファイルの`creationTime`は`2026-10-20T00:00:00Z`、記載されたIPv4プレフィックスは`216.73.216.0/22`と13個の単一ホスト`/32`アドレスからなる計14件である。[4][10]

2026年10月30日、Anthropicはウェブサイト所有者が「AI学習不可（no AI training）」の設定を表明できる機械可読なプリファレンスシグナルの認識を開始した。[4] このシグナルはIETF `aipref`ワーキンググループの草案作業に基づいており、Anthropicはサービス全体で段階的に世界展開を進める一方、草案標準の進展に応じて解釈が変わる可能性があるとしている。[4] 任意のパスにおいて、`ClaudeBot`を明示的に指定した`robots.txt`ルールは、一般的なプリファレンスシグナルが異なる設定を指定している場合でも優先され、`robots.txt`に`ClaudeBot`の記載がない場合に一般的なプリファレンス設定が適用される。[4]

## Anthropicの学習データおよびプライバシーポリシーにおけるClaudeBot

ClaudeBotが収集する公開ウェブコンテンツは、Anthropicのプライバシーポリシーおよび証券届出書に記載された学習データの1つのカテゴリーに該当する。[2][4][5] 2026年9月10日発効のAnthropicプライバシーポリシー（Privacy Policy）は、Anthropicモデルの学習のために収集または受領する6つのデータソースを列挙している。[5]

- インターネットを通じて公開されている情報
- 第三者企業との商業契約を通じて取得したデータセット
- ユーザーがアカウント設定でオプトアウトしない限り、Anthropicサービスの入力（Inputs）および出力（Outputs）を含む、ユーザーまたはクラウドワーカーから提供されたデータ
- Anthropicサービスに関してユーザーが明示的に提供したフィードバック
- 安全性、セキュリティ、またはポリシー審査のためにフラグが立てられた資料
- Anthropicが社内で生成したデータ

Anthropicのプライバシーポリシーは、Enterpriseアカウントなどの法人顧客に代わって処理されるコンテンツには適用されず顧客契約が適用される旨を明記しており、第三者の個人データを用いた大規模言語モデルの学習方法や非ユーザーに適用される選択肢については、別個の非ユーザープライバシーポリシー（Non-User Privacy Policy）を参照するよう案内している。[5] 一般消費者のユーザーがアカウント設定でモデル学習をオプトアウトした場合でも、会話が安全性審査のためにフラグ付けされた場合やフィードバック機能を通じて明示的に報告された場合には、入力および出力がモデル改善に使用される可能性があるとAnthropicは述べている。[5]

2026年11月17日に[SEC EDGAR](https://mimirwiki.com/ja/wiki/sec-edgar)へ提出されたForm S-1修正届出書第3号（登録番号333-299633）において、Anthropic, PBCは、モデル開発の事前学習（pre-training）および事後学習（post-training）の双方の段階で、公開インターネット情報、ライセンス供与または委託による第三者データセット、および自社モデルが生成した合成データを使用しているとしている。[2] 同届出書は、公開情報を収集する手段としてウェブスクレイピングまたはウェブクローリング技術、書籍スキャンなどの手法を挙げている。[2] Anthropicは同届出書の中で、適用法令、`robots.txt`の通知、ペイウォールやログインなどの技術的措置を遵守するための対策を講じているものの、それらの取り組みが常に成功するとは限らず、収集した資料がプライバシー法、著作権法、その他の知的財産法で保護されているか検証できない場合があるとしている。[2]

## ClaudeBotとCloudflareのAIクローラー制御

ClaudeBotは、[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)などのネットワーク事業者が自動トラフィックを分類し、サイト所有者にAIクローラーに対するきめ細かな制御を提供する広範なウェブインフラ環境の中で動作している。[6][7] 2024年5月から2025年5月を対象とした2025年7月1日のトラフィック分析において、CloudflareはAIおよび検索クローラーのトラフィックが18%増加し、[OpenAI](https://mimirwiki.com/ja/wiki/openai)の[GPTBot](https://mimirwiki.com/ja/wiki/gptbot)が305%、Googlebotが96%増加したと報告した。[9]

2026年7月1日、Cloudflareはすべての顧客プランにおいて、ウェブサイト所有者がSearch、Agent、Trainingの各トラフィックを区別して管理できるAIトラフィックオプションを導入した。[7] 同日、CloudflareはBotBase分類体系を更新し、追跡対象のすべてのボットを挙動と運営者アクセス種別によって分類するようにし、従来のVerified botsと署名済みエージェントの区分を`Direct`対`Intermediary`のアクセスフィールドへ置き換えた。[6]

| BotBase分類軸 | カテゴリー | Cloudflareの定義（2026-11-12更新ドキュメント） |
| --- | --- | --- |
| 挙動（マネージドAIプリセット） | Training | モデルの学習またはファインチューニングのためのクローリング |
| 挙動（マネージドAIプリセット） | Search | 検索インデックスまたはRAGデータベース構築のためのクローリング |
| 挙動（マネージドAIプリセット） | Agent | 人間に代わってページを訪問するユーザー指示型エージェント |
| 運営者アクセスラベル | Direct | 単一の限定された運営者によって、通常は自社インフラ上で運用される |
| 運営者アクセスラベル | Intermediary | 多数のエンドユーザーによって駆動されるエージェント型サービスであり、推移的信頼をもたらす |

CloudflareのVerified botsドキュメント（最終更新2026年11月12日）によれば、Verifiedステータスを得るには、暗号学的な[Web Bot Auth](https://mimirwiki.com/ja/wiki/web-bot-auth)署名、安定したユーザーエージェントを伴う公開IPリスト、または逆引きDNSによる決定論的な自己識別に加え、`robots.txt`およびクロールディレクティブを合理的なリクエストレートで遵守する非濫用的な挙動が求められる。[6] `AI Crawler`、`AI Search`、`AI Assistant`といった従来のWAFカテゴリーも、後方互換性のために更新後の分類体系と並行して引き続き利用可能である。[6] Cloudflareは、`robots.txt`の`crawl-delay`ディレクティブを遵守しない行為を、AIクローラーをグローバル許可リストから除外し得るポリシー違反として挙げており、繰り返しの違反や組織内のボット間での不整合な遵守は、その組織が運用するすべてのボットのVerifiedステータス取り消しにつながる可能性があると述べている。[6]

2026年9月15日、Cloudflareはさらに、ウェブサイト所有者がAI学習を不許可にしつつ検索インデックスへの登録を維持できるDisallow AI Training設定とAccountable指定を発表し、Apple、Google、Microsoftがこの設定に従っている、または従うことを約束していると述べた。[8]

## ClaudeBotに関するパブリッシャーの報告とスクレイピング訴訟

ClaudeBotは高いリクエスト量に関してウェブサイト管理者から公開の運用報告を受けており、またAnthropicの広範なウェブクローリング慣行は法的手続きの対象となっている。[2][3] 2024年7月25日、*The Verge*は、iFixitのCEOであるKyle Wiensが、ClaudeBotが24時間以内にiFixitのサーバーへ約100万件のリクエストを送信し、運用アラームが発生してiFixitのDevOpsチームによる対応が必要になったと述べたと報じた。[3]

iFixitの利用規約（Terms of Use）は、事前の明示的な書面許可なくサイトコンテンツを複製、コピー、配布することを禁止しており、機械学習やAIモデルの学習を明示的に含んでいた。[3] 404 Mediaの問い合わせに対し、Anthropicはクローラーを`robots.txt`でブロックできる旨を示したFAQページへのリンクを提示した。[3] iFixitが`robots.txt`ファイルに`crawl-delay`ルールを追加した後、Wiensはサーバーログ上でClaudeBotが停止したことを確認したと*The Verge*に語り、Anthropic広報担当者のJennifer Martinezは、Anthropicは`robots.txt`を尊重しておりiFixitがシグナルを実装した後にクローラーがそれに従ったと述べた。[3]

WiensがXで開始した同じ2024年7月のディスカッションスレッドにおいて、Read the Docs共同創設者のEric HolscherおよびFreelancer.com CEOのMatt Barrieも、自社のウェブサイトがAnthropicのクローラーによる激しいスクレイピングを受けたと述べた。[3] *The Verge*はまた、2024年4月にLinux Mintのウェブフォーラムがサイト障害の原因をClaudeBotのスクレイピング活動によるサーバー負荷に帰していたことも報じた。[3]

2026年11月17日に提出されたForm S-1修正届出書第3号において、Anthropic, PBCは、自社のスクレイピング、ウェブクローリング、およびデータ収集活動が法令違反を主張する訴訟を引き起こしており、引き続き訴訟の対象であることを開示した。[2] 具体的には、Redditのプラットフォーム上に保存された投稿にAnthropicがRedditの法的権利に反して不正アクセスしたと主張する`Reddit, Inc. v. Anthropic PBC`訴訟を挙げている。[2] Anthropicは2025年7月3日に連邦裁判所への移送通知を提出し、同訴訟は2026年3月30日に州裁判所へ差し戻され、2026年11月17日時点で係属中であった。[2] Anthropicはまた、クローリング訴訟における不利な和解や判決により、特定のスクレイピングまたはクローリング技術の中止、代替的なデータ収集手法の開発、または多額の支払いを余儀なくされる可能性があることを事業リスクとして開示した。[2]

## よくある質問

### ClaudeBotは何のために使用されますか？

2026年11月23日時点で、Anthropicは生成AIモデルの学習に利用される可能性のある公開ウェブコンテンツを収集するためにClaudeBotを使用しています。検索インデックス作成にはClaude-SearchBot、ユーザーのクエリに応じたウェブページ取得にはClaude-Userを別途運用しています。 [4]

### ウェブサイト所有者はどのようにしてClaudeBotをブロックまたはレート制限できますか？

ウェブサイト所有者は、除外したい各ドメインおよびサブドメインの最上位ディレクトリにあるrobots.txtファイルに、User-agent: ClaudeBotとDisallow: /を追加することでClaudeBotをブロックできます。また、非標準のCrawl-delay拡張を使用してクロール頻度を制限でき、2026年10月30日からはAnthropicがIETF aipref草案に基づくAI学習拒否プリファレンスシグナルも認識しています。 [1][4]

### ClaudeBotをブロックすると、ユーザーとの会話中にClaudeがウェブページを取得することも停止しますか？

いいえ。ClaudeBotを制限すると、そのサイトの今後のコンテンツをAnthropicのAIモデル学習データセットから除外するシグナルとして扱われます。ユーザー主導のページ取得にはClaude-User、検索インデックス作成にはClaude-SearchBotが使用されるため、サイト所有者はボットごとに個別のrobots.txtルールを設定できます。 [4]

### AnthropicはなぜIPアドレスのブロックだけでClaudeBotを遮断しないよう助言しているのですか？

2026年11月23日時点のAnthropicのクローラードキュメントによると、自社のボットが使用するIPアドレスをブロックすると、クローラーがサイトのrobots.txtファイルを読み取れなくなるため、IPブロックは確実に機能しない場合や継続的なオプトアウトを保証しない場合があります。Anthropicは、管理者がクローラーの送信元がAnthropicであるか確認できるよう、送信元IPアドレスの一覧を公開しています。 [4]

### CloudflareはClaudeBotのような学習用クローラーをどのように分類していますか？

2026年7月1日に導入されたBotBase分類体系のもとで、Cloudflareはボットをモデル学習・ファインチューニング用のTraining、検索インデックスやRAGデータベース構築用のSearch、ユーザー指示によるブラウジングを行うAgentなどの挙動別に分類し、すべてのプランでマネージドプリセットを提供しています。また、CloudflareはVerified botsに対し、決定論的な自己識別とcrawl-delayを含むrobots.txtディレクティブの遵守を義務付けています。 [6][7]

### Anthropicはウェブクローリングに関してどのような訴訟をSEC届出書で開示していますか？

Anthropic, PBCは2026年11月17日にSECへ提出したForm S-1修正届出書第3号（S-1/A-3）で、Redditプラットフォーム上に保存された投稿への不正アクセスを主張するReddit, Inc. v. Anthropic PBC訴訟が係属中であることを開示しました。Anthropicは2025年7月3日に連邦裁判所への移送通知を提出し、同訴訟は2026年3月30日に州裁判所へ差し戻されました。 [2]

## 引用できる文

- 2026年11月23日時点で、AnthropicはAIモデルの学習データ収集用のClaudeBot、検索インデックス作成用のClaude-SearchBot、ユーザー主導のページ取得用のClaude-Userという3種類のウェブロボットを文書化している。 [4]
- 2026年11月23日時点で、Anthropicは自社のウェブボットがrobots.txtのディレクティブを遵守し、非標準のCrawl-delay拡張をサポートしており、CAPTCHAのバイパスを試みないとしている。 [4]
- 2026年10月30日より、AnthropicはIETF aiprefワーキンググループの草案作業に基づく機械可読なAI学習拒否（no-AI-training）プリファレンスシグナルの認識を開始しており、ClaudeBotを明示したrobots.txtルールが優先される。 [4]
- IETFが2022年9月に発行したRFC 9309はロボット排除プロトコルを規定しており、robots.txtルールはアクセス認可の手段ではないと明記している。 [1]
- 2024年7月、iFixitのCEOであるKyle Wiensは、ClaudeBotが24時間以内にiFixitのサーバーへ約100万件のリクエストを送信し、iFixitがrobots.txtにcrawl-delayディレクティブを追加した後に停止したと報告した。 [3]
- 2026年9月10日発効のAnthropicのプライバシーポリシーは、Anthropicモデルの学習に使用する6つのデータソースの1つとして、インターネット上で公開されている情報を挙げている。 [5]
- Anthropic, PBCが2026年11月17日にSECへ提出したForm S-1修正届出書第3号（S-1/A-3）において、Reddit, Inc. v. Anthropic PBC訴訟は2026年3月30日に州裁判所へ差し戻された後も係属中であることを開示した。 [2]
- Cloudflareが2025年7月1日に公開したクローラー分析では、2024年5月から2025年5月の間にAIおよび検索クローラーのトラフィックが18%増加し、GPTBotのトラフィックは305%、Googlebotのトラフィックは96%増加したと報告されている。 [9]

## 年表

- 2022-09: IETFがロボット排除プロトコル（robots.txt）を標準化するRFC 9309を発行した。 [1]
- 2024-04: Linux Mintのウェブフォーラムが、サイト障害の原因をClaudeBotのスクレイピング活動によるサーバー負荷に帰した。 [3]
- 2024-07-25: The Vergeが、ClaudeBotが24時間以内にiFixitへ約100万件のリクエストを送信し、iFixitがrobots.txtにcrawl-delayディレクティブを追加した後に停止したと報じた。 [3]
- 2025-07-01: Cloudflareがクローラートラフィック分析を公開し、2024年5月から2025年5月の間にAIおよび検索クローラーのトラフィックが18%増加し、GPTBotが305%、Googlebotが96%増加したと報告した。 [9]
- 2025-07-03: Anthropicが、Reddit投稿への不正アクセスを主張するReddit, Inc. v. Anthropic PBC訴訟において、連邦裁判所への移送通知を提出した。 [2]
- 2026-03-30: Reddit, Inc. v. Anthropic PBC訴訟が連邦裁判所から州裁判所へ差し戻された。 [2]
- 2026-07-01: Cloudflareが全顧客向けにSearch、Agent、Trainingの個別トラフィックオプションを導入し、BotBaseにDirect対Intermediaryのアクセスラベルを追加した。 [6][7]
- 2026-09-10: Anthropicの更新版プライバシーポリシーが発効し、モデル学習データの6つのソースの1つとして公開インターネット情報を記載した。 [5]
- 2026-09-15: CloudflareがAI学習を不許可にしつつ検索インデックスへの登録を維持するためのDisallow AI Training設定とAccountable指定を発表し、Apple、Google、Microsoftがこの設定に従っている、または従うことを約束していると述べた。 [8]
- 2026-10-30: AnthropicがIETF aiprefワーキンググループの草案作業に基づく機械可読なAI学習拒否プリファレンスシグナルの認識を開始した。 [4]
- 2026-11-17: Anthropic, PBCがSECへForm S-1修正届出書第3号を提出し、ウェブクローリング手法、robots.txt遵守の限界、および係属中のクローリング訴訟を開示した。 [2]

## 出典

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). 公開 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (閲覧 2026-11-23; tier 1: government or public registry)
3. Anthropic’s crawler is ignoring websites’ anti-AI scraping policies | The Verge. The Verge. 公開 2024-07-25. https://www.theverge.com/2024/7/25/24205943/anthropic-ai-web-crawler-claudebot-ifixit-scraping-training-data (閲覧 2026-11-23; tier 2: academic or news)
4. Does Anthropic crawl data from the web, and how can site owners block the crawler? | Claude Help Center. Anthropic. https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler (閲覧 2026-11-23; tier 3: official site)
5. Privacy Policy \ Anthropic. Anthropic. 公開 2026-09-10. https://www.anthropic.com/legal/privacy (閲覧 2026-11-23; tier 3: official site)
6. Verified bots · Cloudflare bot solutions docs. Cloudflare. 公開 2026-11-12. https://developers.cloudflare.com/bots/concepts/bot/verified-bots/ (閲覧 2026-11-23; tier 3: official site)
7. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. 公開 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (閲覧 2026-11-23; tier 3: official site)
8. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 公開 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (閲覧 2026-11-23; tier 3: official site)
9. From Googlebot to GPTBot: Who’s crawling your site in 2025 | Cloudflare Blog. The Cloudflare Blog. 公開 2025-07-01. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (閲覧 2026-11-23; tier 3: official site)
10. Anthropic Crawler IP Prefixes (bots.json). Anthropic. 公開 2026-10-20. https://claude.com/crawling/bots.json (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "ClaudeBot." 版 7e5ac18a, 2026-11-25. https://mimirwiki.com/ja/wiki/claudebot
