---
title: "Perplexity"
subtitle: "Agent API・Orchestrator API・Search API・Context API・Monitor API・Embeddings API・Decisions API を提供する AI 回答エンジンおよびマルチプロバイダー開発者 API プラットフォーム"
canonical_url: https://mimirwiki.com/ja/wiki/perplexity
language: ja
page_class: entity
revision_sha256: 0c4b73e0fc3b68056c1363e6ddfc6a5590a21edc82e25bcdce0fbc95ff6fa6c6
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ja/wiki/perplexity.md
  txt: https://mimirwiki.com/ja/wiki/perplexity.txt
  json: https://mimirwiki.com/ja/wiki/perplexity.json
  jsonld: https://mimirwiki.com/ja/wiki/perplexity.jsonld
translations:
  en: https://mimirwiki.com/wiki/perplexity
  ko: https://mimirwiki.com/ko/wiki/perplexity
  zh: https://mimirwiki.com/zh/wiki/perplexity
  es: https://mimirwiki.com/es/wiki/perplexity
---

# Perplexity

> Perplexity は、ウェブ検索を根拠とする AI 回答エンジンと、Agent API（`POST https://api.perplexity.ai/v1/agent`）、Orchestrator API、Search API（標準リクエスト 1,000 件あたり 5.00 ドル、Fast Search リクエスト 1,000 件あたり 1.00 ドル、1 リクエストあたり最大 5 クエリ）、Context API、Monitor API（1,000 回の実行または取得 URL あたり 1.00 ドル）、Embeddings API、Decisions API の 7 サービスからなる開発者 API プラットフォームを運営している。2026年9月27日に旧 Sonar Chat Completions のサポートを終了した後、Perplexity は開発者を Open Responses 準拠の Agent API へ移行させた。Agent API では、組み込みのウェブ・金融・人物検索、コードサンドボックス、MCP ツールを活用しながら、OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA、および Sonar モデルへ統一的にアクセスできる。

Perplexity は、リアルタイムのウェブインデックス技術と大規模言語モデル（LLM）を組み合わせ、出典付きの回答、自律的なエージェント型リサーチ、および開発者向け API を提供する人工知能リサーチ・回答エンジンプラットフォームである。2026年9月27日の旧 Sonar Chat Completions サポート終了以降、Perplexity の開発者プラットフォーム（`docs.perplexity.ai`）は、マルチプロバイダー対応の Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API、Decisions API の7つのモジュール式サービスを中心に構成されており、`pplx` コマンドラインインターフェースおよび公式の Model Context Protocol（MCP）サーバーも併せて提供されている。

**別名:** Perplexity, Agent API, Orchestrator API, Search API, PerplexityBot, 回答エンジン

## 主要な事実

- **コア API プラットフォーム製品群:** Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API、Decisions API [7]
- **Sonar 非推奨化マイルストーン:** 2026年9月27日（Sonar Chat Completions のサポート終了、同期呼び出しは Agent API へ自動再構成） [5]
- **Agent API の主な機能:** Open Responses 標準、5段階の effort 階層（fast〜xhigh）、マルチプロバイダールーティング、サンドボックス、Finance Search・People Search [5]
- **Search・Monitor API の料金:** Search API：1,000 リクエストあたり $5.00（Fast Search は 1,000 件あたり $1.00、1 リクエスト最大 5 クエリ）／Monitor API：1,000 回の実行または URL あたり $1.00 [4]
- **ウェブクローラーおよび IP フィード:** PerplexityBot/1.0（IPv4 プレフィックス 21 件）および Perplexity-User/1.0（IPv4 プレフィックス 10 件）。いずれも基盤モデルの学習には使用されない [1]

## ファクトシート

- **プラットフォーム名:** Perplexity（Perplexity API Platform & Answer Engine） [7]
- **主要 Agent エンドポイント:** POST https://api.perplexity.ai/v1/agent [6]
- **API 標準互換性:** Open Responses 標準（Agent API）／OpenAI および Anthropic リクエスト形式（Orchestrator API） [5]
- **対応モデルファミリー:** Perplexity Sonar、OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA [5]
- **Agent の effort プリセット:** fast（デフォルト）、low、medium、high、xhigh [5]
- **Search API 料金:** $5.00 / 1,000 リクエスト（標準ウェブ検索）／$1.00 / 1,000 リクエスト（search_type: "fast"） [4]
- **Monitor API 料金:** 成功した Search 実行 1 回あたり $0.001（$1/1K）／カウントされた取得 Page URL 1 件あたり $0.001（$1/1K） [4]
- **旧 Sonar サポート終了日:** 2026年9月27日（Sonar Chat Completions サポート終了） [5]
- **CLI および MCP 統合:** Perplexity CLI（pplx）、Perplexity API MCP Server、Perplexity Computer MCP Server、Decider for Mac [7]
- **公式ウェブクローラー:** PerplexityBot/1.0（perplexitybot.json）および Perplexity-User/1.0（perplexity-user.json） [1]

## Perplexity の 7 本柱 API プラットフォームアーキテクチャ

2026年後半までに、Perplexity は単一の検索拡張チャットエンドポイントから、モジュール式の 7 つの API で構成される開発者プラットフォーム（`docs.perplexity.ai`）へと進化した。公式の Python および TypeScript SDK（`perplexity` および `@perplexity-ai/perplexity_ai`）、`pplx` コマンドラインインターフェース（Perplexity CLI）、Perplexity API MCP Server、ならびに Perplexity Computer MCP Server が提供されている：[5][6][7]

1. **Agent API（`POST https://api.perplexity.ai/v1/agent`）**：内部で推論とツールの実行ループを回し、構造化された `search_results` 項目と出典付きの `message` 項目を含む型付き `output` 配列を返す、Open Responses 準拠の統合マルチプロバイダーエージェントインターフェースである。[5][6] 2. **Orchestrator API**：単一の Perplexity API キーを用い、OpenAI または Anthropic のリクエスト形式で Anthropic、OpenAI、Google、xAI、およびオープンウェイトモデルを呼び出せるマルチプロバイダールーティングゲートウェイである。自動モデルルーティング（`perplexity/auto`）、デプロイメントのフェイルオーバー、ターンをまたぐ推論状態の保持、およびプロンプトキャッシングに対応する。[7] 3. **Search API（`POST /search`）**：生成系言語モデルを呼び出さず、トークン課金も発生させずに、各結果の `snippet` に抽出済みページテキストを含む順位付けされたウェブ検索結果を JSON で返す純粋な検索 API である。[4][7] 4. **Context API**：指定された URL から、整形済み Markdown、HTML、外部リンク、クエリに関連するハイライト、および鮮度・基準スコアを抽出する。[7] 5. **Monitor API**：スケジュール実行またはイベント駆動で Search モニターおよび Page URL モニターを実行し、ウェブ上の変化を経時的に追跡する。[4][7] 6. **Embeddings API**：Standard Embeddings、Contextualized Embeddings、および Contextualized Embeddings v2 を含むベクトル表現を生成する。[4][7] 7. **Decisions API**：予測や意思決定ワークロード向けに較正された確率推定値を生成する（Decider for Mac クライアントと連携する）。[4][7]

## Sonar Chat Completions から Agent API への移行

Perplexity は 2026年9月27日をもって、旧来の Sonar Chat Completions エンドポイント（`POST https://api.perplexity.ai/v1/sonar`）の公式サポートを終了した。[5] 既存の本番環境における後方互換性を維持するため、同期およびストリーミングの Sonar リクエストはバックエンドでモデル単位に自動的に Agent API リクエストへ再構成されて引き続き機能する一方、旧来の非同期 Sonar リクエストは再構成およびサポートの対象外となり、Agent API のバックグラウンドモードへ移行する必要がある。[5]

Perplexity の Sonar モデルに限定された `messages` 配列を受け取り、型付けされていない `choices` 配列を返していた Sonar Chat Completions とは異なり、Agent API は `input` ペイロードを受け取り、ポータブルな Open Responses 仕様に準拠している。[5] 開発者は単一の Perplexity API キーを通じて、Perplexity 独自の Sonar モデル、OpenAI（`openai/gpt-5.6-luna` など）、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA の 8 つのモデルファミリーからモデルを選択でき、設定可能なモデルフォールバックチェーンも構築できる。[4][5]

Agent API は、リサーチ向けに調整された `effort` プリセット（`fast`、`low`、`medium`、`high`、`xhigh`）と、ループ上限、トークン予算、組み込みツールを事前設定できる再利用可能かつバージョン管理された Profiles を備えている：[5][7]

- **Search as Code およびマルチソースグラウンディング**：ウェブ検索、URL 取得、Finance Search、People Search を標準で内蔵している。[5]
- **コード実行サンドボックス**：生成されたコードを隔離されたコンテナサンドボックス内で実行し、単一の API リクエスト内で正確な数値計算、データ分析、および生成ファイルの返却を行う。[5][7]
- **MCP およびカスタム関数**：外部の Model Context Protocol（MCP）サーバーに対するネイティブクライアントサポートと、呼び出し側が定義するカスタム関数ツールを提供する。[5]

## Search API・Monitor API・Agent API の料金体系と課金メカニズム

Perplexity はすべての API において、必須の月額サブスクリプションのない従量課金モデル（pay-as-you-go）を採用している。[6] Agent API および Orchestrator API では、公開されているモデル別単価に基づくトークン料金が透明に課金され、それとは別にツール呼び出し単位またはコンテナ実行時間単位の料金が発生する（たとえば、コードサンドボックスは開始された 20 分ブロック単位のコンテナ実行時間に加えてサンドボックス内で実行された SDK ウェブ検索に対して課金され、一部の組み込みツール呼び出しは 1,000 回あたり 1.00 ドルで課金される）。[4][6]

検索および監視ワークロードについては、Perplexity はトークン料金を一切課さず、リクエスト単位または実行単位のみで厳密に課金する：[4]

| API サービス | モード / 課金単位 | 1,000 単位あたりの料金 | 単価および課金ルール |
| --- | --- | --- | --- |
| Search API | 標準ウェブ検索（`POST /search`） | $5.00 / 1K リクエスト | 成功したリクエスト 1 件あたり $0.005。1 回のリクエストで最大 5 件のクエリ配列（最大 20 件の結果）を 1 課金単位としてまとめて送信可能 |
| Search API | Fast Search（`search_type: "fast"`） | $1.00 / 1K リクエスト | 成功したリクエスト 1 件あたり $0.001（低遅延検索。1 リクエストあたり最大 5 件のクエリを 1 課金単位としてカウント） |
| Monitor API | Search Monitor 実行 | $1.00 / 1K 実行 | 成功した Search 実行 1 回あたり $0.001（実行内の検索回数や結果数にかかわらず一定） |
| Monitor API | Page Monitor 取得 | $1.00 / 1K URL | 成功した Page 実行内でカウントされた取得 URL 1 件あたり $0.001 |

Search API では、無効なリクエスト、レート制限（`429`）を受けたリクエスト、およびアップストリームエラーは一切課金されないが、クエリに一致する結果が 0 件であっても有効な HTTP 200 レスポンスは 1 単位として課金される。[4] Monitor API では、失敗した実行およびスキップされた実行に料金は発生しない。[4]

## Perplexity クローラー（PerplexityBot・Perplexity-User）と WAF ルール

Perplexity は 2 種類の異なる HTTP ユーザーエージェントを通じてウェブ情報を収集・検証しており、いずれも AI 基盤モデルの学習用コンテンツ収集には使用されない：[1]

1. **`PerplexityBot`**：Perplexity の検索結果にウェブサイトを表示・リンクするために使用される自動インデックスクローラーである。[1] `robots.txt` の指示を遵守し（変更はおおよそ 24 時間以内に反映される）、ユーザーエージェント文字列 `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)` を送信し、公式の IPv4 許可リストを `https://www.perplexity.ai/perplexitybot.json` で公開している。[1] `2026-11-18T16:30:18` のフィード更新時点で、`perplexitybot.json` には `107.20.236.150/32`、`18.210.92.235/32`、`18.97.1.228/32`、`18.97.9.96/32`〜`18.97.9.103/32`、`3.222.232.239/32`、`3.224.62.45/32`、および `3.41.218.160/32`〜`3.41.218.167/32` の計 21 個の `/32` IPv4 プレフィックスが記載されている。[2] 2. **`Perplexity-User`**：ユーザーが Perplexity に質問し、回答と出典提示のために特定のウェブページへアクセスする必要がある場合に起動されるリアルタイムのユーザー操作フェッチャーである。[1] 取得はユーザーのリクエストによって直接開始されるため、`Perplexity-User` は通常 `robots.txt` のルールを無視し、`Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)` を名乗り、公式の IPv4 許可リストを `https://www.perplexity.ai/perplexity-user.json` で公開している（`2026-10-28T16:48:51` 時点で、`18.97.43.80/32`〜`18.97.43.87/32`、`34.193.163.52/32`、および `44.208.221.197/32` の計 10 個の `/32` IPv4 プレフィックスが記載されている）。[1][3]

Cloudflare WAF や AWS WAF などのウェブアプリケーションファイアウォール（WAF）を運用するサイト管理者に対し、Perplexity は優先度の高い `Skip` または `Allow` ルールにおいて、`http.user_agent` の部分一致とライブ JSON エンドポイント（`perplexitybot.json` および `perplexity-user.json`）に基づく送信元 IP 検証を組み合わせることを推奨している。なお、Cloudflare の無料プランの Bot Fight Mode はカスタム WAF ルールではバイパスできず、有効にしたままにすると Perplexity のボットに対してチャレンジが発生する可能性がある点も案内されている。[1]

## よくある質問

### Perplexity の Sonar Chat Completions API はどうなりましたか？

Sonar Chat Completions のサポートは 2026年9月27日に終了し、Perplexity Agent API（POST https://api.perplexity.ai/v1/agent）に置き換わりました。既存の同期およびストリーミングの Sonar リクエストは、Perplexity がバックエンドで自動的に Agent API 呼び出しへ再構成するため引き続き動作しますが、非同期の Sonar リクエストはサポート終了となっており、Agent API のバックグラウンドモードへ移行する必要があります。 [5]

### Perplexity の Search API の料金体系と課金方法はどのようになっていますか？

Search API は LLM を呼び出さず、トークン料金も発生させずに、抽出されたテキストスニペット付きの順位付けされたウェブ検索結果を JSON で返します。標準検索は成功した POST /search リクエスト 1,000 件あたり 5.00 ドル（1 リクエストあたり 0.005 ドル）、Fast Search（search_type: "fast"）は成功したリクエスト 1,000 件あたり 1.00 ドル（1 リクエストあたり 0.001 ドル）です。1 回の POST /search 呼び出しに最大 5 件のクエリ配列を含めても 1 課金単位として請求されます。無効なリクエスト、レート制限されたリクエスト、または失敗したリクエストは課金されません。 [4]

### Perplexity の Agent API と Orchestrator API の違いは何ですか？

Agent API は Open Responses 仕様に準拠し、組み込みツール（ウェブ検索、Finance Search、People Search、URL 取得、20 分単位のコード実行サンドボックス、MCP サーバー）と事前調整された effort レベル（fast、low、medium、high、xhigh）を用いて複数ステップのエージェントループを完結させ、出典付き回答と型付き検索結果を返します。一方、Orchestrator API はマルチプロバイダーのモデルゲートウェイであり、perplexity/auto によるルーティング、デプロイメントのフェイルオーバー、プロンプトキャッシングを備え、標準の OpenAI または Anthropic リクエスト形式で Anthropic、OpenAI、Google、xAI、およびオープンウェイトモデルを呼び出すことができます。 [7]

### robots.txt における PerplexityBot と Perplexity-User の違いは何ですか？

PerplexityBot/1.0 は、Perplexity の検索結果にウェブサイトを表示するためにインデックスを作成する自動検索クローラーであり、robots.txt のルールを遵守し（24 時間以内に反映）、perplexity.ai/perplexitybot.json で公開されている IP を使用します。Perplexity-User/1.0 は、実際のユーザーが Perplexity に質問した際にオンデマンドで特定のページを取得するフェッチャーであり、ユーザーの直接的なリクエストに基づいて動作するため、通常は robots.txt を無視し、perplexity.ai/perplexity-user.json の IP を使用します。どちらのクローラーも AI 基盤モデルの学習用データ収集は行いません。 [1]

## 引用できる文

- Perplexity は 2026年9月27日に旧 Sonar Chat Completions のサポートを終了し、同期およびストリーミングの Sonar 呼び出しを自動的に Agent API リクエストへ再構成する一方、非同期の Sonar リクエストを廃止してバックグラウンドモードへ移行させた。 [5]
- Perplexity API Platform は、Agent API、Orchestrator API、Search API、Context API、Monitor API、Embeddings API、Decisions API の 7 つのコア API と、pplx CLI および MCP サーバーで構成されている。 [4][7]
- Agent API（POST https://api.perplexity.ai/v1/agent）は Open Responses 標準に準拠し、5 段階の effort レベル（fast、low、medium、high、xhigh）を提供するとともに、組み込みのウェブ・金融・人物検索、コードサンドボックス、MCP 統合を備え、Sonar、OpenAI、Anthropic、Google、xAI、Z.AI、Moonshot AI、NVIDIA の各モデルへルーティングする。 [5][6]
- Perplexity の Search API はトークン料金なしで、成功した標準リクエスト 1,000 件あたり 5.00 ドル、Fast Search リクエスト 1,000 件あたり 1.00 ドルを課金し、最大 5 件のクエリ配列を含むリクエストを 1 課金単位としてカウントする。 [4]
- Perplexity は、検索インデックス用の PerplexityBot/1.0（2026年11月18日時点で公開 IPv4 /32 プレフィックス 21 件）と、ユーザー起点の取得を行う Perplexity-User/1.0（2026年10月28日時点で公開 IPv4 /32 プレフィックス 10 件）の 2 つのウェブエージェントを運用しており、いずれのボットも AI 基盤モデルの学習目的でコンテンツをクロールしないとしている。 [1][2][3]

## 年表

- 2026-09-27: Perplexity が旧 Sonar Chat Completions の公式サポートを終了し、開発者を Open Responses ベースの Agent API へ移行させた。 [5]
- 2026-10-28: Perplexity が Perplexity-User 向けの公開 IPv4 許可リストフィード（perplexity-user.json）を 10 件の /32 プレフィックスで更新した。 [3]
- 2026-11-18: Perplexity が PerplexityBot 向けの公開 IPv4 許可リストフィード（perplexitybot.json）を 21 件の /32 プレフィックスで更新した。 [2]

## 出典

1. Perplexity Crawlers - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/resources/perplexity-crawlers (閲覧 2026-11-23; tier 3: official site)
2. PerplexityBot Published IPv4 Prefixes (perplexitybot.json). Perplexity. 公開 2026-11-18. https://www.perplexity.ai/perplexitybot.json (閲覧 2026-11-23; tier 3: official site)
3. Perplexity-User Published IPv4 Prefixes (perplexity-user.json). Perplexity. 公開 2026-10-28. https://www.perplexity.ai/perplexity-user.json (閲覧 2026-11-23; tier 3: official site)
4. Pricing - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/getting-started/pricing (閲覧 2026-11-23; tier 3: official site)
5. Migrate from Sonar to the Agent API - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/migrate-from-sonar/overview (閲覧 2026-11-23; tier 3: official site)
6. Agent API Quickstart - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/quickstart (閲覧 2026-11-23; tier 3: official site)
7. Perplexity API Documentation Index (llms.txt). Perplexity. https://docs.perplexity.ai/llms.txt (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Perplexity." 版 0c4b73e0, 2026-11-23. https://mimirwiki.com/ja/wiki/perplexity
