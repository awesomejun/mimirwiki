---
title: "Model Context Protocol"
subtitle: "AIアプリケーションを外部のツールやデータに接続するオープンプロトコル"
canonical_url: https://mimirwiki.com/ja/wiki/model-context-protocol
language: ja
page_class: anchor
revision_sha256: 8d75cc51327a59afe4f4cf868d9d8412d3fc7d69d8681571a372a4f875e56f4e
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/model-context-protocol.md
  txt: https://mimirwiki.com/ja/wiki/model-context-protocol.txt
  json: https://mimirwiki.com/ja/wiki/model-context-protocol.json
  jsonld: https://mimirwiki.com/ja/wiki/model-context-protocol.jsonld
translations:
  en: https://mimirwiki.com/wiki/model-context-protocol
  ko: https://mimirwiki.com/ko/wiki/model-context-protocol
  zh: https://mimirwiki.com/zh/wiki/model-context-protocol
  es: https://mimirwiki.com/es/wiki/model-context-protocol
---

# Model Context Protocol

> Model Context Protocol（MCP）は、AIアプリケーションが共通のインターフェースを通じて外部のツールやデータソースに接続できるようにするオープンプロトコルである。JSON-RPC 2.0のメッセージをstdioまたはStreamable HTTPでやり取りする。Anthropicが2024年11月25日に公開し、2025年12月からはLinux FoundationのAgentic AI Foundationがホストしている。現行バージョンは2026-07-28である。

Model Context Protocol（MCP）は、大規模言語モデルを用いたアプリケーションが外部のデータソースやツールに接続する方法を標準化したオープンプロトコルである。MCPのメッセージはJSON-RPC 2.0に従い、ホスト、クライアント、サーバーの間をstdioとStreamable HTTPという2種類の標準トランスポートで運ばれる。Anthropicが2024年11月25日にオープンソースとして公開し、2025年12月9日の発表で、Linux Foundationのもとに設立されたAgentic AI Foundationに寄贈した。2026年11月21日時点の現行プロトコルバージョンは2026-07-28であり、この改訂でプロトコルはステートレスになった。

**別名:** MCP, モデルコンテキストプロトコル

## 主要な事実

- **初回公開:** 2024-11-25、Anthropic [8]
- **現行プロトコルバージョン:** 2026-07-28 (時点 2026-11-21) [2]
- **メッセージ形式:** JSON-RPC 2.0 [1]
- **標準トランスポート:** stdio、Streamable HTTP [4]
- **ホスト財団:** Agentic AI Foundation（Linux Foundation）、2025-12-09発表 [9]

## ファクトシート

- **種別:** LLMアプリケーションを外部のデータソースやツールに接続するオープンプロトコル [1]
- **開発元:** Anthropic [8]
- **初回公開:** 2024-11-25 [8]
- **現行バージョン:** 2026-07-28 (時点 2026-11-21) [2]
- **バージョン表記:** 日付文字列（YYYY-MM-DD） [2]
- **メッセージ形式:** JSON-RPC 2.0、UTF-8エンコード [4]
- **標準トランスポート:** stdio、Streamable HTTP [4]
- **サーバー機能:** リソース、プロンプト、ツール [1]
- **認可:** 任意。HTTPベースのトランスポートではOAuth 2.1に基づく [5]
- **法人形態:** Model Context Protocol a Series of LF Projects, LLC [6]
- **ライセンス:** Apache License 2.0（コードと仕様）、CC BY 4.0（その他のドキュメント） [6]
- **公式SDK:** TypeScript、Python、C#、Go、Rust、Ruby、Java、Swift、PHP、Kotlin (時点 2026-11-21) [7]

## Model Context Protocolとは

Model Context Protocol（MCP）は、大規模言語モデル（LLM）を用いたアプリケーションを外部のデータソースやツールに接続するためのオープンプロトコルである。[1] 仕様は目的として、言語モデルと文脈情報を共有すること、AIシステムにツールや機能を公開すること、組み合わせ可能な統合とワークフローを構築することの3点を挙げている。[1] 仕様は[Language Server Protocol](https://mimirwiki.com/ja/wiki/language-server-protocol)から着想を得たと述べている。Language Server Protocolが開発ツール全体でプログラミング言語のサポートを標準化したのと同様に、MCPはAIアプリケーションに文脈とツールを組み込む方法を標準化する。[1]

MCPには3つの役割がある。ホストは接続を開始するLLMアプリケーション、クライアントはホスト内で動作するコネクター、サーバーは文脈と機能を提供するサービスである。[1] サーバーはリソース（文脈とデータ）、プロンプト（テンプレート化されたメッセージとワークフロー）、ツール（モデルが実行できる関数）を提供できる。クライアントは、サーバーがユーザーに追加情報を求める仕組みであるエリシテーション（elicitation）を提供できる。[1]

[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)は2024年11月25日にMCPをオープンソースの標準として発表した。このとき、仕様とソフトウェア開発キット（SDK）、Claude DesktopアプリでのローカルMCPサーバー対応、MCPサーバーを集めたオープンソースリポジトリが公開された。[8] 発表では、AnthropicのDavid Soria ParraとJustin Spahr-Summersがこのプロトコルを作成したとされている。[8]

## Model Context Protocolのメッセージ形式とアーキテクチャ

Model Context Protocolはすべてのメッセージを[JSON-RPC](https://mimirwiki.com/ja/wiki/json-rpc) 2.0で表現し、メッセージはUTF-8でエンコードしなければならない。[1][4] クライアントはリクエストと通知を送り、サーバーはレスポンスと通知を返す。現行の改訂ではこれ以外の方向は存在せず、サーバーがJSON-RPCリクエストを開始することも、クライアントがJSON-RPCレスポンスを送ることもない。[4]

2026-07-28の改訂以降、MCPはプロトコルレベルでステートレスである。以前の改訂にあった`initialize`ハンドシェイクは廃止され、各リクエストがプロトコルバージョンとクライアントのケイパビリティを`_meta`フィールドに含めて送るようになった。[3] サーバーは、対応するプロトコルバージョン、ケイパビリティ、識別情報を返す`server/discover`メソッドを実装しなければならない。クライアントは最初にこのメソッドを呼び出してもよいが、必須ではない。[2][3]

呼び出しの途中でサーバーがクライアント側の情報を必要とする場合、サーバーは必要な内容を列挙した`input_required`の結果を返し、クライアントは回答を添えて元のリクエストを再送する。仕様はこの方式をMulti Round-Trip Requests（MRTR）と呼んでおり、以前の改訂でサーバーが開始していたリクエストはこの方式に置き換えられた。[3] ツール一覧の変更のような長期にわたる変更通知は、クライアントが`subscriptions/listen`リクエストで開いたストリームで配信される。[3]

## Model Context Protocolのトランスポートと認可

Model Context Protocolは、stdioとStreamable HTTPという2種類の標準トランスポートを定義している。stdioでは、クライアントがサーバーをサブプロセスとして起動し、双方が標準入出力を通じて改行区切りのメッセージをやり取りする。Streamable HTTPでは、各メッセージが単一のMCPエンドポイントへのHTTP POSTとなり、応答は1つのJSONオブジェクト、またはそのリクエストに限定されたServer-Sent Events（SSE）ストリームとして返る。[4] プロトコルの意味論はどちらでも同一である。JSON-RPCのメッセージ形式、メッセージパターン、リクエスト単位のメタデータモデルを保つかぎり、独自のトランスポートも認められる。[4]

Streamable HTTPでは、中継機器が本文を解析せずにリクエストを振り分けられるよう、一部のメタデータがHTTPヘッダーにも複製される。[4] プロトコルバージョンは`MCP-Protocol-Version`ヘッダーで運ばれ、2026-07-28の改訂はPOSTリクエストに`Mcp-Method`と`Mcp-Name`のヘッダーを要求する。[2][3]

MCPにおいて認可は任意である。HTTPベースのトランスポートについて、仕様は[OAuth](https://mimirwiki.com/ja/wiki/oauth) 2.1を基礎としている。保護されたMCPサーバーはOAuth 2.1のリソースサーバーとして、MCPクライアントはOAuth 2.1のクライアントとして動作し、サーバーはクライアントが認可サーバーを見つけられるようにOAuth 2.0 Protected Resource Metadata（RFC 9728）を公開しなければならない。[5] stdioを使う実装はこの手順に従わず、環境から認証情報を取得するものとされている。[5]

## Model Context Protocolのバージョンと2026-07-28改訂

Model Context Protocolのバージョンは`YYYY-MM-DD`形式の日付文字列である。識別子は後方互換性のない変更が最後に行われた日付を示し、後方互換性を保つ更新では変わらない。[2] 2026年11月21日時点の現行バージョンは2026-07-28である。[2] GitHub上の仕様リポジトリのリリースページには、2024-11-05、2025-03-26、2025-06-18、2025-11-25、2026-07-28の各改訂が掲載されている。[10] クライアントとサーバーは複数のバージョンに同時に対応でき、要求されたバージョンに対応しないサーバーは、対応バージョンの一覧を含む`UnsupportedProtocolVersionError`を返す。[2]

メンテナーによる2026-07-28改訂の公開記事は、この改訂を双方向でステートフルなプロトコルからステートレスなリクエスト・レスポンス型プロトコルへの移行と説明している。これにより、ロードバランサーの背後にあるどのサーバーインスタンスでも任意のリクエストを処理できる。[11] 変更履歴は主な変更として次の項目を挙げている。[3]

| 領域 | 2026-07-28改訂での変更 |
| --- | --- |
| セッション | プロトコルレベルのセッションと`Mcp-Session-Id`ヘッダーを廃止 |
| ハンドシェイク | `initialize`ハンドシェイクを廃止し、バージョンとケイパビリティをリクエストごとに送信 |
| ディスカバリー | `server/discover`を追加し、サーバーでの実装を必須化 |
| サーバーからの入力要求 | サーバー起点のリクエストをMulti Round-Trip Requestsに置き換え |
| 通知 | HTTP GETエンドポイントとリソース購読メソッドを`subscriptions/listen`に置き換え |
| タスク | 実験的なコア機能から`io.modelcontextprotocol/tasks`拡張へ移動 |
| 非推奨 | Roots、Sampling、Logging、HTTP+SSEトランスポート、OAuth Dynamic Client Registration |

非推奨（deprecated）とされた機能は、削除の対象となるまで少なくとも12か月間は仕様に残る。ただし迅速削除の例外が適用される場合、この期間は少なくとも90日である。[2] 2026年11月11日、リードメンテナーは6か月ごとのリリース周期を発表し、仕様のリリースをおおむね3月と9月の最終火曜日に行うとした。次回リリースは2027年3月30日を目標とし、バージョン識別子は2027-03-30となる見込みである。[12]

## Model Context Protocolのガバナンスとライセンス

Model Context Protocolは[Linux Foundation](https://mimirwiki.com/ja/wiki/linux-foundation)がホストするプロジェクトである。Linux Foundationは2025年12月9日に[Agentic AI Foundation](https://mimirwiki.com/ja/wiki/agentic-ai-foundation)（AAIF）の設立を発表し、創設プロジェクトとしてAnthropicのMCP、Blockのgoose、OpenAIのAGENTS.mdの3つが寄贈された。[9] 発足時のプラチナメンバーはAmazon Web Services、Anthropic、Block、Bloomberg、[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)、Google、Microsoft、OpenAIであった。[9] プロジェクトのガバナンス文書は、法的形態をModel Context Protocol a Series of LF Projects, LLCとしている。[6]

MCPの技術的な意思決定はメンテナーの階層構造に従う。コントリビューターはイシューやプルリクエストを提出し、メンテナーはSDKやワーキンググループなどの構成要素を担当し、コアメンテナーは仕様の方向性を定め、リードメンテナーが最終的な決定権を持つ。[6] 資格は個人に与えられ、企業に割り当てられた席はない。2026年11月21日時点で、ガバナンスページはDavid Soria ParraとDen Delimarskyをリードメンテナーとして掲載している。[6] 仕様の変更はSpecification Enhancement Proposal（SEP）として提案される。[6]

コードと仕様への貢献にはApache License 2.0が適用される。仕様以外のドキュメントはクリエイティブ・コモンズ 表示 4.0 国際ライセンスで公開される。[6]

## Model Context ProtocolのSDK、普及状況、限界

Model Context Protocolプロジェクトは、10のプログラミング言語で公式SDKを保守している。2026年11月21日時点でSDKページは、TypeScript、Python、C#、Go、Rust、RubyをTier 1、JavaをTier 2、Swift、PHP、KotlinをTier 3に分類している。Tierは機能の完成度、プロトコルへの対応状況、保守への関与の度合いを反映する。[7] 新しい改訂への対応時期はSDKごとに異なる。2026-07-28改訂の公開日には、TypeScript、Python、Go、C#のSDKがこの改訂に対応していた。[7][11]

MCPの普及に関して公表されている数値は、プロジェクトとそのホスト財団によるものである。Linux Foundationは2025年12月9日、公開済みのMCPサーバーが1万を超え、Claude、Cursor、Microsoft Copilot、Gemini、VS Code、ChatGPTがこのプロトコルを採用したと述べた。[9] メンテナーは2026年7月28日、Tier 1のSDKの月間ダウンロード数が5億回近くに達し、TypeScriptとPythonのSDKの累計ダウンロード数がそれぞれ10億回を超えたと報告した。[11]

MCPはプロトコル仕様であり、仕様が保証しない領域がある。仕様は、同意と安全に関する原則をプロトコル自体では強制できないと述べ、ホストに対して、ツールを呼び出す前にユーザーの明示的な同意を得ること、信頼できるサーバーから得たものでないかぎりツールの説明を信頼しないことを求めている。[1] 認可は任意であり、TasksやMCP Appsなどの拡張はコアプロトコルの外にあるオプトイン方式の追加機能である。[1][5] ステートレスであるのはプロトコルであって、アプリケーションではない。呼び出しをまたいで状態を必要とするサーバーは明示的なハンドルを発行し、それを通常のツール引数として受け取る。[3]

## よくある質問

### Model Context Protocolの現行バージョンは何ですか？

2026年11月21日時点の現行プロトコルバージョンは2026-07-28です。バージョンはYYYY-MM-DD形式の日付文字列で、後方互換性のない変更があった場合にのみ変わります。 [2]

### Model Context Protocolは誰が管理していますか？

Linux FoundationのもとでModel Context Protocol a Series of LF Projects, LLCとして運営されており、Anthropicが2025年12月9日に発表されたAgentic AI Foundationに寄贈しました。技術的な意思決定は個人として参加するメンテナーが行い、最終的な決定権はリードメンテナーにあります。 [6][9]

### Model Context Protocolはどのメッセージ形式とトランスポートを使いますか？

メッセージはUTF-8でエンコードされたJSON-RPC 2.0です。標準トランスポートは2種類あり、サーバーをローカルのサブプロセスとして起動するstdioと、メッセージごとに単一のエンドポイントへHTTP POSTを送るStreamable HTTPです。 [1][4]

### Model Context ProtocolにOAuthは必須ですか？

いいえ。MCPでは認可は任意です。HTTPベースのトランスポートで認可を使う場合、仕様はOAuth 2.1を基礎とし、stdioの実装は環境から認証情報を取得します。 [5]

### Model Context Protocolの2026-07-28改訂では何が変わりましたか？

initializeハンドシェイクとプロトコルレベルのセッションが廃止され、各リクエストが自己完結するようになりました。server/discoverメソッドとMulti Round-Trip Requestsが追加され、Roots、Sampling、Loggingは非推奨になりました。 [3]

### Model Context Protocolの公式SDKはどの言語で提供されていますか？

2026年11月21日時点で、TypeScript、Python、C#、Go、Rust、Ruby、Java、Swift、PHP、Kotlin向けの公式SDKがあります。最初の6つはTier 1に分類されています。 [7]

## 引用できる文

- Model Context ProtocolはJSON-RPC 2.0のメッセージを使用する。 [1]
- 2026年11月21日時点で、Model Context Protocolの現行バージョンは2026-07-28である。 [2]
- Anthropicは2024年11月25日にModel Context Protocolをオープンソースとして公開した。 [8]
- Linux Foundationは2025年12月9日、AnthropicがModel Context Protocolを新設のAgentic AI Foundationに寄贈したと発表した。 [9]
- Model Context Protocolは、stdioとStreamable HTTPという2種類の標準トランスポートを定義している。 [4]
- Model Context Protocolの2026-07-28改訂は、initializeハンドシェイクとプロトコルレベルのセッションを廃止し、プロトコルをステートレスにした。 [3]
- Model Context Protocolでは認可は任意であり、HTTPベースのトランスポートではOAuth 2.1を基礎とする。 [5]
- メンテナーによる2026年11月11日の発表によれば、Model Context Protocolの次回の仕様リリースは2027年3月30日を目標としている。 [12]

## 年表

- 2024-11-25: AnthropicがModel Context Protocolをオープンソースとして公開する。 [8]
- 2025-03-26: 2025-03-26改訂が公開される。HTTP+SSEトランスポートはこの改訂から非推奨とされる。 [10][3]
- 2025-06-18: 2025-06-18改訂が公開される。 [10]
- 2025-11-25: タスクを実験的にサポートする2025-11-25改訂が公開される。 [10][12]
- 2025-12-09: Linux FoundationがAgentic AI Foundationの設立を発表し、AnthropicがModel Context Protocolを寄贈する。 [9]
- 2026-07-28: 2026-07-28改訂が公開され、プロトコルがステートレスになる。 [11][3]
- 2026-11-11: リードメンテナーが6か月ごとのリリース周期を発表し、次回リリースの目標日を2027-03-30とする。 [12]

## 出典

1. Specification - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28 (閲覧 2026-11-21; tier 3: official site)
2. Versioning - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/versioning (閲覧 2026-11-21; tier 3: official site)
3. Key Changes - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/changelog (閲覧 2026-11-21; tier 3: official site)
4. Overview - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports (閲覧 2026-11-21; tier 3: official site)
5. Authorization - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (閲覧 2026-11-21; tier 3: official site)
6. Governance and Stewardship - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/community/governance (閲覧 2026-11-21; tier 3: official site)
7. SDKs - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/docs/sdk (閲覧 2026-11-21; tier 3: official site)
8. Introducing the Model Context Protocol. Anthropic. 公開 2024-11-25. https://www.anthropic.com/news/model-context-protocol (閲覧 2026-11-21; tier 3: official site)
9. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. 公開 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (閲覧 2026-11-21; tier 3: official site)
10. Releases · modelcontextprotocol/modelcontextprotocol · GitHub. Model Context Protocol project (GitHub). https://github.com/modelcontextprotocol/modelcontextprotocol/releases (閲覧 2026-11-21; tier 3: official site)
11. The 2026-07-28 Specification. Model Context Protocol Blog. 公開 2026-07-28. https://blog.modelcontextprotocol.io/posts/2026-07-28/ (閲覧 2026-11-21; tier 3: official site)
12. A More Predictable Release Cycle for MCP. Model Context Protocol Blog. 公開 2026-11-11. https://blog.modelcontextprotocol.io/posts/mcp-release-cycle/ (閲覧 2026-11-21; tier 3: official site)

## このページを引用する

Mimirwiki. "Model Context Protocol." 版 8d75cc51, 2026-11-21. https://mimirwiki.com/ja/wiki/model-context-protocol
