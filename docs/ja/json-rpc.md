---
title: "JSON-RPC"
subtitle: "JSONでエンコードされたステートレスかつトランスポート非依存のリモートプロシージャコールプロトコル"
canonical_url: https://mimirwiki.com/ja/wiki/json-rpc
language: ja
page_class: anchor
revision_sha256: 1c34633447d6a55e4cb61ce4e408872d8597b5f42ae1806545360c747037746e
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/json-rpc.md
  txt: https://mimirwiki.com/ja/wiki/json-rpc.txt
  json: https://mimirwiki.com/ja/wiki/json-rpc.json
  jsonld: https://mimirwiki.com/ja/wiki/json-rpc.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-rpc
  ko: https://mimirwiki.com/ko/wiki/json-rpc
  zh: https://mimirwiki.com/zh/wiki/json-rpc
  es: https://mimirwiki.com/es/wiki/json-rpc
---

# JSON-RPC

> JSON-RPCは、リクエスト、レスポンス、通知、エラー、およびバッチ呼び出しをJSONでエンコードするステートレスかつ軽量なリモートプロシージャコール（RPC）プロトコルである。2010年にJSON-RPC Working Groupによって公開され2013年に更新されたバージョン2.0は、トランスポート非依存でありHTTP、ソケット、単一プロセス内で動作する。MCP、LSP、イーサリアムクライアントのメッセージ交換に用いられている。

JSON-RPCは、JavaScript Object Notation（JSON）でメッセージをエンコードするステートレスかつ軽量なリモートプロシージャコール（RPC）プロトコルである。JSON-RPC Working Groupは2009-05-24の草案を基に2010-03-26にバージョン2.0を公開し、2013-01-04に仕様書本文を最終更新した。2026-11-23現在もJSON-RPC 2.0が現行バージョンである。JSON-RPC仕様はリクエスト、レスポンス、通知、エラー、バッチのデータ構造とそれらの処理規則を定義する一方、トランスポート層の選択は実装に委ねている。JSON-RPCはModel Context Protocol（MCP）、Language Server Protocol（LSP）、イーサリアム実行クライアントAPI、およびOpen vSwitch Database Management Protocol（OVSDB）の基本メッセージ形式として採用されている。

**別名:** JSON-RPC 2.0, JSON-RPC 1.0, JSONリモートプロシージャコール

## 主要な事実

- **現行バージョン:** 2.0（2010-03-26策定、2013-01-04更新） (時点 2026-11-23) [1]
- **初期バージョン:** 1.0（2005年） [2]
- **策定者:** JSON-RPC Working Group [1]
- **データ形式:** JSON（RFC 4627） [1]
- **トランスポート:** トランスポート非依存（同一プロセス内、ソケット、HTTP、その他のメッセージ経路） [1]

## ファクトシート

- **種別:** ステートレス・軽量なリモートプロシージャコール（RPC）プロトコル [1]
- **策定者:** JSON-RPC Working Group [1]
- **初期バージョン:** JSON-RPC 1.0（2005年） [2]
- **現行バージョン:** JSON-RPC 2.0（2010-03-26策定、2013-01-04更新） (時点 2026-11-23) [1]
- **データ形式:** JSON（4種のプリミティブ型と2種の構造化型） [1]
- **JSON標準:** RFC 8259（2017年12月、RFC 7159およびRFC 4627を廃止） (時点 2026-11-23) [4]
- **トランスポート:** トランスポート非依存（同一プロセス内、ソケット、HTTP、その他のメッセージパッシング） [1]
- **メッセージ種別:** リクエスト、レスポンス、通知、エラー、バッチ [1]
- **予約エラーコード:** -32768〜-32000（事前定義 -32700、-32600〜-32603、サーバーエラー -32000〜-32099） [1]
- **拡張プレフィックス:** rpc.（任意のシステム拡張用に予約） [1]
- **インターフェース記述:** OpenRPC Specification（バージョン1.4.x、探索メソッド rpc.discover） (時点 2026-11-23) [10]

## JSON-RPCの概要

JSON-RPCは、メソッド呼び出しと応答をJavaScript Object Notation（JSON）データとしてエンコードする、ステートレスかつ軽量なリモートプロシージャコール（RPC）プロトコルである。[1] JSON-RPC 2.0仕様は最小限のデータ構造とその処理規則のみを定義しており、特定のネットワークトランスポートに依存しない設計となっている。[1] 2026-11-23現在、JSON-RPC 2.0はJSON-RPC Working Groupが維持する現行仕様であり、2009-05-24の草案を基に2010-03-26に策定され、2013-01-04に最新の本文更新が行われた。[1]

JSON-RPCは、4種のプリミティブ型（String、Number、Boolean、Null）と2種の構造化型（Object、Array）から成るJSONの型システムを採用している。[1][4] JSON-RPC 2.0の仕様書本文ではJSONの参照規格としてRFC 4627が引用されている。[1] 2017年12月、Internet Engineering Task Force（IETF）はRFC 8259を発行し、それ以前にRFC 4627および`application/json`メディアタイプの初期登録を廃止していたRFC 7159を置き換えた。[4] RFC 8259はJSON文法をECMA-404と整合させており、トップレベルのテキストとしてJSONオブジェクトまたは配列のみを生成する実装はすべての準拠パーサー間で相互運用性を維持できると記している。これは単一オブジェクトとバッチ配列を用いるJSON-RPCの設計と合致している。[1][4]

JSON-RPC 2.0において、クライアントはリクエストオブジェクトを発行してレスポンスオブジェクトを処理する主体であり、サーバーはリクエストオブジェクトを処理してレスポンスオブジェクトを発行する主体である。[1] 単一の実装が異なるピアまたは同一ピアに対して両方の役割を同時に担うことも可能であるが、双方向セッションの調整は上位層に委ねられている。[1] クライアントとサーバー間で照合されるすべてのメンバー名は大文字・小文字を区別し、仕様書では関数（function）、メソッド（method）、プロシージャ（procedure）という用語を同義として扱っている。[1]

## JSON-RPC 2.0のメッセージ構造

JSON-RPC 2.0は、リクエストオブジェクト、通知（Notification）、レスポンスオブジェクトという3つの基本メッセージ形式を定義している。[1] 仕様に準拠するすべてのリクエストオブジェクトおよびレスポンスオブジェクトには、文字列値が厳密に`"2.0"`である`jsonrpc`メンバーを含める必要がある。[1]

JSON-RPC 2.0リクエストオブジェクトはリモートメソッドを呼び出すためのものであり、最大4つのメンバーを持つ。[1]

- `jsonrpc`: プロトコルバージョンを示す必須の文字列であり、常に`"2.0"`とする。
- `method`: 呼び出すプロシージャ名を指定する必須の文字列。`rpc.`（`rpc`に続いてピリオド U+002E）で始まるメソッド名は、RPC内部メソッドおよび任意のシステム拡張用に予約されている。
- `params`: 呼び出しの引数を格納する任意の構造化値。含める場合は、サーバーが期待する順序のJSON配列による位置指定、またはサーバーが期待するパラメーター名と大文字・小文字を含めて完全一致するメンバー名を持つJSONオブジェクトによる名前指定のいずれかで渡す。
- `id`: クライアントが設定する任意の識別子であり、含める場合は文字列、数値、またはNullでなければならない。不明な`id`に対するレスポンスがNullを用いること、およびJSON-RPC 1.0で通知にNullの`id`が使用されていたことから、リクエストの`id`にNullを使用することは非推奨とされている。また、2進浮動小数点形式では多くの10進小数を正確に表現できないため、数値の`id`には小数部を含めないことが望ましい。

JSON-RPC 2.0の通知は、`id`メンバーを省略したリクエストオブジェクトである。[1] `id`を省略することはクライアントが応答を期待しない意思表示であり、サーバーはバッチ内に含まれる通知も含めて、通知に対してレスポンスオブジェクトを返してはならない。[1] レスポンスが返されないため通知は到達確認ができず、パラメーター不正や内部エラーが発生してもクライアントには通知されない。[1]

通知以外のすべてのリクエストオブジェクトに対し、JSON-RPC 2.0サーバーは単一のJSONレスポンスオブジェクトで応答しなければならない。[1] レスポンスオブジェクトには常に`"jsonrpc": "2.0"`と、リクエストオブジェクトの`id`と一致する`id`メンバー（パースエラーや不正リクエストにより`id`を特定できなかった場合はNull）が含まれる。[1] 各レスポンスオブジェクトは、成功時には`result`メンバー、失敗時には`error`メンバーのいずれか一方を必ず含めなければならず、両方を同一レスポンスオブジェクト内に併存させてはならない。[1]

## JSON-RPC 2.0のエラーオブジェクトと予約コード

JSON-RPC 2.0は、メソッド実行の失敗をレスポンスオブジェクトの`error`メンバーに格納された構造化エラーオブジェクトによって報告する。[1] エラーオブジェクトは2つの必須メンバーと1つの任意メンバーから構成される。すなわち、エラー種別を識別する整数の`code`、簡潔な1文に収めることが望ましい短い文字列説明の`message`、および追加のエラー情報を保持するサーバー定義の任意のプリミティブ値または構造化値である`data`である。[1]

JSON-RPC 2.0では、事前定義されたプロトコルエラー用に-32768から-32000までの整数範囲（両端を含む）が予約されており、XML-RPCのフォールトコードに密接に沿った値が採用されている。[1] この範囲内の未割り当てコードは将来の利用のために予約されており、-32768から-32000の範囲外の整数はアプリケーション定義のエラーに利用できる。[1]

| コード | メッセージ | 意味 |
| --- | --- | --- |
| -32700 | Parse error | サーバーが無効なJSONを受信した、またはJSONテキストの構文解析中にエラーが発生した。 |
| -32600 | Invalid Request | 送信されたJSONが有効なリクエストオブジェクトではない。 |
| -32601 | Method not found | 要求されたメソッドが存在しない、または利用できない。 |
| -32602 | Invalid params | メソッドのパラメーターが無効である。 |
| -32603 | Internal error | JSON-RPCの内部エラーが発生した。 |
| -32000〜-32099 | Server error | 実装定義のサーバーエラー用に予約されている。 |

下位プロトコルはこの予約範囲を維持したまま、独自のエラー体系を構築している。[7] Language Server Protocol（LSP）3.17仕様では、5つの基本JSON-RPCエラーコード（-32700および-32600〜-32603）が維持され、-32099〜-32000の範囲はJSON-RPC予約領域としてマークされている（後方互換性のために旧来の-32002 ServerNotInitializedと-32001 UnknownErrorCodeのみを保持）。そして-32803（RequestFailed）や-32802（ServerCancelled）などのプロトコル固有エラーは-32899から始まる別領域に定義されている。[7]

## JSON-RPCのバッチ処理とトランスポート非依存性

JSON-RPC 2.0では、クライアントが複数のリクエストオブジェクトを1つのJSON配列にまとめて送信する「バッチ（Batch）」処理が認められている。[1] サーバーはバッチ内のすべてのリクエストを処理した後、通知ではない各リクエストオブジェクトに対応するレスポンスオブジェクトを格納したJSON配列を返す。[1] サーバーはバッチ内のリクエストを任意の順序で並列実行し、レスポンスオブジェクトも任意の順序で返却できるため、クライアントは各オブジェクトの`id`メンバーによってリクエストとレスポンスを対応付ける。[1]

JSON-RPC 2.0は、バッチにおけるエラーや通知の境界ケースについても明確な規則を定めている。[1] バッチのペイロードが無効なJSONであるか空配列（`[]`）である場合、サーバーは配列ではなく、エラーコード-32700（Parse error）または-32600（Invalid Request）と`"id": null`を含む単一のレスポンスオブジェクトを返す。[1] 空でない配列に無効な要素が含まれる場合、サーバーは有効な要素のレスポンスと並べて、無効な要素ごとにInvalid Request（-32600）のエラーオブジェクトを含むレスポンス配列を返す。[1] バッチ内のすべての項目が通知である場合、サーバーは空配列を返してはならず、何も返却してはならない。[1]

JSON-RPC 2.0はメッセージフレーミングとトランスポートバインディングをコア仕様の対象外としており、同一のJSON構造を同一プロセス内、ソケット、HTTP、その他のメッセージパッシング環境でそのまま利用できる。[1] プロトコル開発の初期段階である2008-01-15には、Jeffrey DamickとJSON-RPC Working GroupがJSON-RPC 1.2を対象とした歴史的拡張草案「JSON-RPC over HTTP」を公開した。[3] この草案ではHTTP POSTを推奨メソッドとしつつ、Base64エンコードおよびURLエンコードしたパラメーターを用いるHTTP GETも記述していた（古いクライアントやプロキシでは255バイトを超えるURI長で失敗する可能性がある旨を注記）。また、`Content-Type`および`Accept`ヘッダーに`application/json-rpc`を指定し（`application/json`および`application/jsonrequest`も許容）、`Content-Length`を必須としたうえで、処理結果とHTTPステータスコードの対応付け（成功リクエストに200、通知に204、-32600に400、-32601に404、-32700・-32602・-32603およびサーバーエラー-32099〜-32000に500）を規定していた。[3] JSON-RPC 2.0を採用する各プロトコルは独自のトランスポート規約を定めている。LSPはHTTP形式のASCII `Content-Length`ヘッダーと任意の`Content-Type`ヘッダー（既定値は`application/vscode-jsonrpc; charset=utf-8`）を`\r\n\r\n`で区切ってUTF-8のJSON-RPC 2.0ペイロードをフレーミングしており、イーサリアム実行ノードは一般に`Content-Type: application/json`を付与したHTTP POSTリクエストを受け付ける。[7][8]

## JSON-RPCのバージョン履歴：1.0から2.0へ

JSON-RPC 1.0は2005年に公開されたピアツーピア型のリモートプロシージャコールプロトコルであり、接続された2つのピアがバイトストリーム（TCP/IPソケットを推奨）または複数回のHTTP POSTリクエストを通じて相互にメソッドを呼び出せる仕様であった。[2] JSON-RPC 1.0のリクエストオブジェクトは`method`、位置指定配列に限定された`params`、および任意のJSON型の`id`という3つのプロパティで構成されていた。[2] 通知では`id`に`null`を使用し、レスポンスオブジェクトには常に`result`と`error`の両プロパティを含め、使用しない側を`null`に設定していた。[2] またバージョン1.0では、標準JSON型以外の型付きオブジェクトをピア側でインスタンス化できるよう、クラスヒント用の`__jsonclass__`プロパティも含まれていた。[2]

2009-05-24の草案から2010-03-26に策定され、2013-01-04に更新されたJSON-RPC 2.0は、プロトコルをステートレスなクライアント・サーバー型メッセージ仕様へと簡素化すると同時に、バージョン1.0とのワイヤ互換性を断つ変更を導入した。[1] すべてのJSON-RPC 2.0リクエストおよびレスポンスオブジェクトには`"jsonrpc": "2.0"`が含まれるのに対し、バージョン1.0オブジェクトにはこのメンバーが存在しないため、実装は両バージョンを判別できる。[1]

| 機能 | JSON-RPC 1.0（2005年） | JSON-RPC 2.0（2010年、2013年更新） |
| --- | --- | --- |
| バージョン識別子 | なし | 必須の`"jsonrpc": "2.0"`メンバー |
| パラメーター（`params`） | 配列のみ（位置指定） | 任意の配列（位置指定）またはオブジェクト（名前指定） |
| 通知形式 | `"id": null` | `id`メンバーを省略 |
| レスポンスの`result`と`error` | 両方を含め、未使用フィールドに`null`を設定 | 相互排他的（いずれか一方のみ存在可能） |
| バッチリクエスト | 未定義 | リクエストオブジェクトのJSON配列 |
| クラスヒント（`__jsonclass__`） | 仕様に定義 | 仕様から削除 |
| 通信モデル | ストリームまたはHTTP上のピアツーピア | ステートレスなクライアント・サーバー役割、トランスポート非依存 |

JSON-RPC 2.0仕様は、バージョン1.0のピアツーピア機能やクラスヒント機能を含まない形であっても、実用上可能な場合にはバージョン1.0オブジェクトの処理を検討するよう実装に助言している。[1] JSON-RPC 1.0はバージョン2.0の公開後もネットワーク仕様で採用され続けた。2013年12月、IETFは情報提供（Informational）文書としてRFC 7047を発行し、Open vSwitch Database Management Protocol（OVSDB）を定義した。OVSDBは仮想スイッチのブリッジ、ポート、トンネルインターフェース、キュー、QoSポリシーを設定するためのワイヤプロトコルとしてJSON上のJSON-RPC 1.0を使用している。[5]

## JSON-RPCの採用事例とOpenRPCツール

JSON-RPC 2.0は、主要な開発者向け・AI向け・ブロックチェーン向けプロトコルのメッセージ層として採用されている。[6][7][8] [Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）は、2026-11-23時点で最新版となる仕様バージョン2026-07-28において、LLMホストアプリケーション、内部クライアント、およびリソース・プロンプト・ツール・クライアントエリシテーションフローを提供するサーバー間の通信にJSON-RPC 2.0メッセージを使用している。[6] MCPはマイクロソフトが維持するLanguage Server Protocol（LSP、2026-11-23時点で3.17がアーカイブ済み、3.18が現行、3.19が次期予定）に着想を得ており、LSPもコードエディターと言語サーバー間で補完、診断、フォーマット、シンボルナビゲーションなどの操作を行う際にJSON-RPC 2.0メッセージをやり取りする。[6][7]

JSON-RPC 2.0はイーサリアム実行ノードの標準クライアントインターフェースでもある。[8][9] すべてのイーサリアム実行クライアントが統一されたJSON-RPC APIを公開することで、ソフトウェアアプリケーションはノード実装を切り替えながらブロックチェーン状態の照会、過去ブロックやトランザクションレシートの取得、トランザクションの送信を行える。[8][9] イーサリアムのドキュメントでは主要メソッドをゴシップ（`eth_blockNumber`、`eth_sendRawTransaction`）、状態（`eth_getBalance`、`eth_getStorageAt`、`eth_getTransactionCount`、`eth_getCode`、`eth_call`、`eth_estimateGas`）、履歴（`eth_getBlockByNumber`、`eth_getTransactionReceipt`）に分類している。整数の数量はコンパクトな`"0x"`付き16進文字列（ゼロは`"0x0"`）として、未整形バイト配列は偶数長の`"0x"`付き16進文字列としてエンコードされる。[8] イーサリアム実行APIの公式仕様はCC0-1.0ライセンスの下でGitHubリポジトリ`ethereum/execution-apis`にて管理されており、`speccheck`および`hive`シミュレーターの`rpc-compat`テストスイートを用いて各クライアントとの適合性が検証されている。[9] なお、イーサリアムのコンセンサスクライアントは別途Beacon APIを公開しており、コンセンサスクライアントと実行クライアント間のノード内部通信にはEngine APIが用いられる。[8]

JSON-RPC 2.0インターフェースを機械可読な形式で記述・検証するため、OpenRPC Specification（2026-11-23時点でバージョン1.4.x、Apache-2.0ライセンス）はJSON-RPC 2.0 API専用の言語非依存JSONインターフェース記述形式を定義している。[10] 慣例的に`openrpc.json`と名付けられるOpenRPCドキュメントは`openrpc`、`info`、`methods`フィールドを必須とし、パラメーターおよび結果の定義にDraft 07 JSON Schemaを使用し、説明フィールドでGitHub Flavored [Markdown](https://mimirwiki.com/ja/wiki/markdown)をサポートしている。[10] またOpenRPCは、JSON-RPC 2.0の予約済み`rpc.`拡張プレフィックスを用いたサービス探索メソッド`rpc.discover`を定義しており、実行時にAPIのOpenRPCスキーマを取得できるようにしている。[1][10] `ethereum/execution-apis`をはじめとするプロジェクトでは、JSON-RPCメソッドをOpenRPCのYAMLファイルで記述し、検証済みの`openrpc.json`ドキュメントへとコンパイルしている。[9]

## よくある質問

### JSON-RPCとは何ですか？

JSON-RPCは、リクエスト、レスポンス、通知、エラーオブジェクトをJSONでエンコードするステートレスかつ軽量なリモートプロシージャコール（RPC）プロトコルです。バージョン2.0はJSON-RPC Working Groupによって2010-03-26に策定され、2013-01-04に最終更新されました。 [1]

### JSON-RPC 2.0の通知は通常のリクエストとどう違いますか？

JSON-RPC 2.0のリクエストには、サーバーがレスポンスオブジェクトを呼び出しに対応付けるためのidメンバーが含まれます。一方、通知（Notification）はidメンバーを省略したものであり、バッチ内に含まれる場合であってもサーバーは一切のレスポンスを返してはなりません。 [1]

### JSON-RPC 2.0で予約されているエラーコードは何ですか？

JSON-RPC 2.0では、事前定義されたプロトコルエラー用に-32768から-32000までの整数エラーコードが予約されています。具体的には、-32700がParse error、-32600がInvalid Request、-32601がMethod not found、-32602がInvalid params、-32603がInternal errorであり、-32000から-32099は実装定義のサーバーエラー用に予約されています。 [1]

### JSON-RPC 2.0のトランスポートプロトコルとしてHTTPは必須ですか？

いいえ。JSON-RPC 2.0はトランスポート非依存であり、JSONデータ構造と処理規則のみを定義しているため、HTTP、ソケット、同一プロセス内、あるいはその他のメッセージパッシング経路上で動作させることができます。 [1]

### JSON-RPC 1.0とJSON-RPC 2.0では何が変わりましたか？

JSON-RPC 2.0では、必須の"jsonrpc": "2.0"バージョンフィールド、JSONオブジェクトによる名前付きパラメーター、バッチリクエスト配列、相互排他的なresultおよびerrorレスポンスフィールドが追加されました。また、通知の形式が"id": nullからidの省略に変更され、バージョン1.0の__jsonclass__によるクラスヒント機能は廃止されました。 [1][2]

### JSON-RPCを採用している主なプロトコルや仕様にはどのようなものがありますか？

Model Context Protocol（MCP）、Language Server Protocol（LSP）、イーサリアム実行クライアントAPIがJSON-RPC 2.0を採用している一方、Open vSwitch Database Management Protocol（RFC 7047）はJSON-RPC 1.0を使用しています。また、OpenRPCはJSON-RPC 2.0 API専用の機械可読な標準インターフェース記述形式を定義しています。 [5][6][7][8][10]

## 引用できる文

- JSON-RPC 2.0は2009-05-24の草案を基に2010-03-26に策定され、記録上の最終更新は2013-01-04に行われた。 [1]
- すべてのJSON-RPC 2.0リクエストオブジェクトおよびレスポンスオブジェクトには、文字列値が厳密に"2.0"である"jsonrpc"メンバーを含めなければならない。 [1]
- JSON-RPC 2.0レスポンスオブジェクトには"result"メンバーまたは"error"メンバーのいずれか一方を含めなければならず、両方を含めてはならない。 [1]
- JSON-RPC 2.0は事前定義されたプロトコルエラー用に整数エラーコード-32768から-32000を予約しており、そのうち-32000から-32099を実装定義のサーバーエラー用に割り当てている。 [1]
- JSON-RPC 2.0では"rpc."で始まるメソッド名が任意のシステム拡張用に予約されており、OpenRPCのサービス探索メソッド"rpc.discover"などで利用されている。 [1][10]
- IETFは2017年12月にRFC 8259を発行し、RFC 7159およびRFC 4627を置き換える形でJSONデータ交換形式を標準化した。 [4]
- Model Context Protocol（バージョン2026-07-28）とLanguage Server Protocol（バージョン3.17）は、いずれも基本メッセージ形式としてJSON-RPC 2.0を採用している。 [6][7]
- イーサリアムの実行クライアントは、CC0-1.0ライセンスのethereum/execution-apisリポジトリにおいてOpenRPC形式で規定された標準JSON-RPC 2.0 APIを実装している。 [8][9]

## 年表

- 2005: JSON-RPC.ORGが、ストリーム接続およびHTTP上でのピアツーピア型リモートプロシージャコールを定めたJSON-RPC 1.0仕様を公開する。 [2]
- 2008-01-15: Jeffrey DamickとJSON-RPC Working Groupが、バージョン1.2向けの歴史的拡張草案「JSON-RPC over HTTP」を作成する。 [3]
- 2009-05-24: JSON-RPC Working Groupが、後にJSON-RPC 2.0の基盤となる草案バージョンを作成する。 [1]
- 2010-03-26: JSON-RPC Working GroupがJSON-RPC 2.0仕様を公開する。 [1]
- 2013-01-04: JSON-RPC Working GroupがJSON-RPC 2.0仕様書本文における記録上の最終更新を公開する。 [1]
- 2013-12: IETFが情報提供RFC 7047を発行し、JSON-RPC 1.0上に構築されたOpen vSwitch Database Management Protocol（OVSDB）を定義する。 [5]
- 2017-12: IETFがRFC 8259を発行し、RFC 7159およびRFC 4627を置き換える標準化トラックのJSON仕様とする。 [4]
- 2026-07-28: Model Context Protocolプロジェクトが、JSON-RPC 2.0メッセージを用いる仕様バージョン2026-07-28を公開する。 [6]

## 出典

1. JSON-RPC 2.0 Specification. JSON-RPC Working Group. 公開 2010-03-26. https://www.jsonrpc.org/specification (閲覧 2026-11-23; tier 3: official site)
2. JSON-RPC 1.0 Specification (2005). JSON-RPC Working Group. 公開 2005. https://www.jsonrpc.org/specification_v1 (閲覧 2026-11-23; tier 3: official site)
3. JSON-RPC over HTTP. JSON-RPC Working Group. 公開 2008-01-15. https://www.jsonrpc.org/historical/json-rpc-over-http.html (閲覧 2026-11-23; tier 3: official site)
4. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 公開 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (閲覧 2026-11-23; tier 1: government or public registry)
5. RFC 7047: The Open vSwitch Database Management Protocol. Internet Engineering Task Force (IETF). 公開 2013-12. https://www.rfc-editor.org/rfc/rfc7047.txt (閲覧 2026-11-23; tier 1: government or public registry)
6. Specification - Model Context Protocol. Model Context Protocol project. 公開 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28 (閲覧 2026-11-23; tier 3: official site)
7. Language Server Protocol Specification - 3.17. Microsoft (LSP). https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/ (閲覧 2026-11-23; tier 3: official site)
8. JSON-RPC API | ethereum.org. ethereum.org. https://ethereum.org/developers/docs/apis/json-rpc/ (閲覧 2026-11-23; tier 3: official site)
9. GitHub - ethereum/execution-apis: Collection of APIs provided by Ethereum execution layer clients · GitHub. Ethereum (GitHub). https://github.com/ethereum/execution-apis (閲覧 2026-11-23; tier 3: official site)
10. OpenRPC Specification | spec. OpenRPC. https://spec.open-rpc.org/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "JSON-RPC." 版 1c346334, 2026-11-23. https://mimirwiki.com/ja/wiki/json-rpc
