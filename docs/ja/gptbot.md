---
title: "GPTBot"
subtitle: "生成AI基盤モデルの学習データ収集に用いられるOpenAIの自動ウェブクローラー"
canonical_url: https://mimirwiki.com/ja/wiki/gptbot
language: ja
page_class: entity
revision_sha256: 3bedd1a4924f279a5a839146a778669ef3ffa0e6ab019ecb6c516d62c1c799bf
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ja/wiki/gptbot.md
  txt: https://mimirwiki.com/ja/wiki/gptbot.txt
  json: https://mimirwiki.com/ja/wiki/gptbot.json
  jsonld: https://mimirwiki.com/ja/wiki/gptbot.jsonld
translations:
  en: https://mimirwiki.com/wiki/gptbot
  ko: https://mimirwiki.com/ko/wiki/gptbot
  zh: https://mimirwiki.com/zh/wiki/gptbot
  es: https://mimirwiki.com/es/wiki/gptbot
---

# GPTBot

> 2026年後半時点で、GPTBotはUser-Agentトークン「GPTBot/1.4 (+https://openai.com/gptbot)」を用いて自身を識別し、検証可能な送信元IPv4プレフィックスをopenai.com/gptbot.json（2026年9月22日時点で18個のCIDRブロック）にて公開している。ウェブサイト運営者は、robots.txt（RFC 9309）でGPTBotを拒否してモデル学習向けのスクレイピングを遮断しつつ、OAI-SearchBot（39個のIPv4ブロック）を許可してChatGPT検索結果への表示を維持することができ、さらに新興のIETF AI Preferences（aipref）およびWeb Bot Auth暗号署名標準とも連携している。

GPTBotは、生成人工知能（生成AI）基盤モデルの学習に利用され得る公開ウェブコンテンツを発見・取得するためにOpenAIが運用する主要な自動ウェブクローラーである。OpenAIは機能的役割が異なる3つの別個のユーザーエージェント、すなわちOAI-SearchBot（ChatGPTの検索インデックス作成用）、OAI-AdsBot（広告ランディングページの検証用）、およびChatGPT-User（ユーザー主導のリアルタイムブラウジングおよびカスタムGPTアクション用）と並行してGPTBotを運用している。

**別名:** GPTBot/1.4, OAI-SearchBot, OAI-AdsBot, ChatGPT-User

## 主要な事実

- **運営者:** OpenAI（OpenAI OpCo, LLC） [1]
- **現在のUser-Agentトークン:** GPTBot/1.4 (+https://openai.com/gptbot) (時点 2026-11-23) [1]
- **公開IP範囲:** openai.com/gptbot.json内の18個のIPv4 CIDRプレフィックス（2026-09-22更新） (時点 2026-11-23) [2]
- **併用されるOpenAIエージェント:** OAI-SearchBot/1.4（検索）、OAI-AdsBot/1.0（広告）、ChatGPT-User/1.0（ユーザーアクション） (時点 2026-11-23) [1]

## ファクトシート

- **運営者:** OpenAI [1]
- **主な機能:** 生成AI基盤モデルの学習に向けた公開ウェブコンテンツのクロール [1]
- **User-Agent文字列:** Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot) [1]
- **IP検証マニフェスト:** https://openai.com/gptbot.json（2026-09-22時点で18個のIPv4プレフィックス） [2]
- **検索用クローラー:** OAI-SearchBot/1.4（https://openai.com/searchbot.json、39個のIPv4プレフィックス） [1]
- **除外プロトコル:** Robots Exclusion Protocol（IETF RFC 9309 / robots.txt） [5]
- **新興標準:** IETF AI Preferences（aipref）およびIETF Web Bot Auth（webbotauth） [6]

## GPTBotの概要とOpenAIクローラーの分類体系

2023年8月にOpenAIによって導入され、2026年にバージョン1.4へと反復的に更新された**GPTBot**は、生成AI基盤モデルの学習および改善に用いられる公開インターネット上のテキストやメディアを収集するためのOpenAI専用ウェブクローラーである。[1] ウェブサイト運営者が学習データの取り込み、検索エンジンのインデックス作成、広告ポリシーの適合性確認、および実ユーザー起点のリアルタイムなページ取得を区別して制御できるよう、OpenAIは自動化されたHTTPトラフィックを独立した `robots.txt` 制御とIPマニフェストを持つ以下の4つのユーザーエージェントに分離している。[1]

| User-Agentトークン | 現行バージョン | 目的およびモデル学習ポリシー | IPマニフェストURL |
| --- | --- | --- | --- |
| `GPTBot` | `GPTBot/1.4` | OpenAIの生成AI基盤モデルの学習に利用され得るコンテンツをクロールする。ペイウォール、個人識別情報（PII）を多く含むソース、およびポリシー違反コンテンツを回避する。[1] | `https://openai.com/gptbot.json`（2026-09-22時点で18個のIPv4プレフィックス）[2] |
| `OAI-SearchBot` | `OAI-SearchBot/1.4` | ChatGPTの検索機能でリンクや要約を表示するためにウェブサイトをインデックス化する。OpenAIの基盤モデルの学習には**使用されない**。[1] | `https://openai.com/searchbot.json`（2026-01-02時点で39個のIPv4プレフィックス）[3] |
| `OAI-AdsBot` | `OAI-AdsBot/1.0` | 広告主のランディングページの品質、安全性、およびポリシー準拠を検査する。基盤モデルの学習には**使用されない**。[1] | OpenAIのクローラードキュメントにて公開[1] |
| `ChatGPT-User` | `ChatGPT-User/1.0` | 実際のユーザーがChatGPTまたはカスタムGPTに対して特定のウェブページの取得を指示した際に代理で起動される。受動的な基盤モデル学習には**使用されない**。[1] | `https://openai.com/chatgpt-user.json`（2026-11-06更新）[4] |

2026年後半時点でGPTBotが送信する完全なHTTP `User-Agent` ヘッダーは `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot)` である。[1]

## Robots.txtによるオプトアウトと細粒度なアクセス制御

GPTBotは、**IETF RFC 9309** で標準化されたRobots Exclusion Protocolに準拠している。[1][5] サイト管理者は、サイトの `/robots.txt` ファイルに `User-agent: GPTBot` ルールを追加することで、ドメイン全体からのスクレイピングを遮断したり、特定のディレクトリパスのみに制限したりできる。[1][5]

OpenAIは学習用クロールと検索インデックス作成を分離しているため、AIモデルの学習からはオプトアウトしつつChatGPT Searchに引用リンクとして表示され続けたいパブリッシャーは、以下のように `GPTBot` を拒否しながら `OAI-SearchBot` を明示的に許可できる。[1]

```text User-agent: GPTBot Disallow: /

User-agent: OAI-SearchBot Allow: / ```

OpenAIによれば、サイト側が `robots.txt` のルールを更新してから、OpenAIの分散クローラー群がキャッシュされた `robots.txt` ポリシーを更新してリクエストを停止するまでに約24時間かかる場合がある。[1]

## IP検証と暗号学的Web Bot認証

第三者のスクレイパーがHTTPヘッダー内の `GPTBot` User-Agent文字列を日常的に詐称（スプーフィング）するため、`User-Agent` ヘッダーのみに依存する方法はファイアウォール制御やアクセス解析には不十分である。[1][8] そこでOpenAIは、ネットワーク運用者やコンテンツデリバリーネットワーク（CDN）がIPレイヤーで正当なトラフィックを検証できるよう、機械可読なJSON形式のプレフィックスマニフェストを公開している。[1][2][3][4] - **`gptbot.json`**：`2026-09-22T00:00:00Z` の作成タイムスタンプ時点で、18個のIPv4 CIDRブロック（`20.171.206.0/24`、`52.230.152.0/24`、`20.168.17.192/28`、`172.182.202.0/25`、`172.182.204.0/24`、`172.182.214.0/24` など）を収録している。[2] - **`searchbot.json`**：`2026-01-02T07:01:00.000000Z` 時点で39個のIPv4 CIDRブロックを収録している。[3] - **`chatgpt-user.json`**：`2026-11-06T00:00:00Z` 時点で更新された数十個のリージョン別送信元IPv4 CIDRブロックを収録している。[4]

IP許可リストに加えて、Cloudflareなどのエッジセキュリティ事業者および **IETF Web Bot Auth（`webbotauth`）ワーキンググループ** は、自動エージェント向けの暗号学的HTTPメッセージ署名（RFC 9421ベース）を導入している。[7][8] 暗号学的ボット認証では、検証済みクローラーやAIエージェントが公開されたEd25519またはRSA鍵ディレクトリで署名された `Signature` および `Signature-Input` ヘッダーを付与するため、オリジンサーバーやWAFは不安定なIP範囲照合に頼らずにボットの身元を数学的に検証できる。[7][8]

## IETF AI Preferences（aipref）とウェブエコシステムへの影響

AI学習クローラーの急速な拡大に伴い、1994年に検索クローラーによるサーバー過負荷の防止と相互的な検索トラフィックの還元を前提として設計された `robots.txt` が、著作権および機械学習の利用ポリシーを表現する手段として十分かどうかをめぐり大きな議論が生じた。[5][6]

この課題に対処するため、**IETF AI Preferences（`aipref`）ワーキンググループ** が設立され、デジタルコンテンツをAIシステムがどのように利用してよいか、あるいは利用してはならないかを機械可読に表現するための語彙と添付メカニズムの標準化が進められている。[6] 同ワーキンググループの現行仕様である `draft-ietf-aipref-vocab`（AI利用設定を表現するための語彙）および `draft-ietf-aipref-attach`（`robots.txt` 拡張やHTTP `Content-Usage` ヘッダーを介して設定を添付する仕組み）は、一般的な自動処理、基盤モデル学習（`train-ai` / `ai`）、および検索や推論グラウンディングを明確に区別している。[6] 一方、CloudflareのAIトラフィックレポートによるネットワークテレメトリでは、`GPTBot` はBytespider、ClaudeBot、Google-Extendedと並び世界最大級のトラフィック量を持つAIクローラーの一つとして一貫して上位に位置しており、マネージドAIクロール制御やクロール課金（pay-per-crawl）アーキテクチャの広範な導入を後押ししている。[8]

## よくある質問

### GPTBotとOAI-SearchBotの違いは何ですか？

GPTBot（GPTBot/1.4）は、OpenAIの生成AI基盤モデルの学習データを収集するために公開ウェブページをクロールします。一方、OAI-SearchBot（OAI-SearchBot/1.4）はChatGPTの検索機能内でウェブサイトをインデックス化してリンク表示することのみを目的としてクロールしており、OpenAIの基盤モデルの学習には使用されません。 [1]

### ChatGPT Searchでの表示を維持したままGPTBotをブロックするにはどうすればよいですか？

サイト管理者は、ルートの /robots.txt ファイルに「User-agent: GPTBot」と「Disallow: /」を記述し、あわせて「User-agent: OAI-SearchBot」と「Allow: /」を追加することで対応できます。これにより、OpenAIによるモデル学習向けのスクレイピングを防ぎつつ、ChatGPTの検索回答内でページがインデックス化・引用される状態を維持できます。 [1][5]

### サーバー管理者はGPTBotのリクエストが本当にOpenAIからのものかをどのように検証できますか？

管理者は、リクエストの送信元IPアドレスをOpenAIが https://openai.com/gptbot.json で公開している公式CIDRブロック（2026年9月時点で18個のIPv4プレフィックスを記載）と照合するか、CDNのVerified BotチェックおよびIETF Web Bot Authフレームワークで標準化されているHTTPメッセージ署名を利用する必要があります。 [1][2][7][8]

### ChatGPT-Userとは何ですか？なぜGPTBotとは挙動が異なるのですか？

ChatGPT-User（ChatGPT-User/1.0）は、実際のユーザーがChatGPTまたはカスタムGPTアクションに対して特定のURLへリアルタイムにアクセスするよう能動的に指示した際に呼び出されます。送信元IPは https://openai.com/chatgpt-user.json で別途公開されており、そのリクエストは受動的な基盤モデル学習には使用されません。 [1][4]

### GPTBotのようなAIウェブクローラーにはどのようなIETF標準が関わっていますか？

GPTBotのrobots.txt準拠はIETF RFC 9309（Robots Exclusion Protocol）によって規定されています。さらに、IETF AI Preferences（aipref）ワーキンググループがAI学習オプトアウトを表現するための標準語彙（draft-ietf-aipref-vocab）やHTTP/robots添付ルールを策定しており、IETF Web Bot Auth（webbotauth）ワーキンググループが暗号学的ボット認証を標準化しています。 [5][6][7]

## 引用できる文

- OpenAIはウェブトラフィックを4つの異なるユーザーエージェント、すなわちGPTBot/1.4（モデル学習）、OAI-SearchBot/1.4（検索インデックス作成）、OAI-AdsBot/1.0（広告ランディングページ検証）、およびChatGPT-User/1.0（ユーザー起点のリクエスト）に分離している。 [1]
- OpenAIによるGPTBotの公式IPマニフェスト（https://openai.com/gptbot.json）は、2026年9月22日の更新時点で18個のIPv4 CIDRプレフィックスを記載している。 [2]
- OpenAIによるOAI-SearchBotの公式IPマニフェスト（https://openai.com/searchbot.json）は、2026年1月2日の更新時点で39個のIPv4 CIDRプレフィックスを記載している。 [3]
- robots.txtでGPTBotを拒否するとOpenAIによる基盤モデル学習向けのクロールを防止でき、同時にOAI-SearchBotを許可することでChatGPT検索結果へのインデックス登録を維持できる。 [1][5]
- IETF AI Preferences（aipref）ワーキンググループは、機械可読なAI学習および利用設定を標準化するため、draft-ietf-aipref-vocabおよびdraft-ietf-aipref-attachを策定している。 [6]

## 年表

- 2022-09: IETFがRFC 9309を公開し、Robots Exclusion Protocol（robots.txt）を正式に標準化した。 [5]
- 2023-08: OpenAIがrobots.txtによるオプトアウト制御と公開送信元IP範囲を備えたGPTBotをローンチした。 [1]
- 2024-07: OpenAIが検索インデックス作成をGPTBotの基盤モデル学習クロールから分離するため、OAI-SearchBotを導入した。 [1]
- 2026-01-02: OpenAIがOAI-SearchBot用のsearchbot.jsonを39個のIPv4 CIDRブロックに更新した。 [3]
- 2026-09-22: GPTBotがユーザーエージェントバージョンGPTBot/1.4へ移行する中、OpenAIがgptbot.jsonを18個のIPv4 CIDRプレフィックスに更新した。 [1][2]
- 2026-11-06: OpenAIがユーザー主導のリアルタイムChatGPTブラウジングアクション向けにchatgpt-user.jsonの送信元IPv4範囲を更新した。 [4]

## 出典

1. Overview of OpenAI Crawlers (GPTBot/1.4, OAI-SearchBot/1.4, OAI-AdsBot/1.0, ChatGPT-User/1.0). OpenAI Platform Documentation. https://platform.openai.com/docs/bots (閲覧 2026-11-23; tier 3: official site)
2. OpenAI GPTBot Official IPv4 CIDR Prefix Manifest (gptbot.json). OpenAI. 公開 2026-09-22. https://openai.com/gptbot.json (閲覧 2026-11-23; tier 3: official site)
3. OpenAI OAI-SearchBot Official IPv4 CIDR Prefix Manifest (searchbot.json). OpenAI. 公開 2026-01-02. https://openai.com/searchbot.json (閲覧 2026-11-23; tier 3: official site)
4. OpenAI ChatGPT-User Official IPv4 CIDR Prefix Manifest (chatgpt-user.json). OpenAI. 公開 2026-11-06. https://openai.com/chatgpt-user.json (閲覧 2026-11-23; tier 3: official site)
5. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309 (閲覧 2026-11-23; tier 1: government or public registry)
6. IETF AI Preferences (aipref) Working Group Charter and Active Drafts (draft-ietf-aipref-vocab, draft-ietf-aipref-attach). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (閲覧 2026-11-23; tier 1: government or public registry)
7. IETF Web Bot Auth (webbotauth) Working Group Charter. Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (閲覧 2026-11-23; tier 1: government or public registry)
8. From Googlebot to GPTBot: Who's Crawling Your Site and Cryptographic Bot Verification. Cloudflare. 公開 2025-05. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "GPTBot." 版 3bedd1a4, 2026-11-24. https://mimirwiki.com/ja/wiki/gptbot
