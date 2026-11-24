---
title: "JSON-LD"
subtitle: "Linked DataをJSONでシリアライズするためのW3C標準形式"
canonical_url: https://mimirwiki.com/ja/wiki/json-ld
language: ja
page_class: anchor
revision_sha256: 6de73c68a99e54f6d28a356abb237dbf5f7d1bc11df83925a960e480a98d3d3d
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/json-ld.md
  txt: https://mimirwiki.com/ja/wiki/json-ld.txt
  json: https://mimirwiki.com/ja/wiki/json-ld.json
  jsonld: https://mimirwiki.com/ja/wiki/json-ld.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-ld
  ko: https://mimirwiki.com/ko/wiki/json-ld
  zh: https://mimirwiki.com/zh/wiki/json-ld
---

# JSON-LD

> JSON-LDは、有効なJSON形式でLinked DataをシリアライズするためのW3C勧告である。コンテキストを通じてオブジェクトのキーをグローバルな識別子にマッピングすることで、アプリケーションが複数のウェブサイトにまたがるデータを解釈・連結できるようにする。2014年に標準化され、2020年にバージョン1.1へ更新されたJSON-LDは、RDFグラフ、プログラムによる文書変換、およびSchema.orgなどのHTML構造化データをサポートしている。

JSON-LD（JSON for Linking Data）は、ウェブ上でLinked Dataをシリアライズするための軽量なJSONベースの構文を定義するWorld Wide Web Consortium（W3C）勧告である。すべてのJSON-LD文書はRFC 8259に準拠した有効なJSONであるため、標準のJSONパーサー、ウェブサービス、JSONベースのストレージエンジンでそのまま処理できる一方、グローバルなリソース識別子、コンテキスト、言語タグ、データ型、および有向グラフを表現できる。W3Cは2014年1月16日にJSON-LD 1.0を公開し、2020年7月16日に構文、処理アルゴリズムとAPI、およびフレーミングから成るJSON-LD 1.1仕様群によってこれを置き換えた。アプリケーションはJSON-LDをそのままJSONとして利用したり、Resource Description Framework（RDF）のグラフやデータセットと相互変換したりするほか、Schema.orgなどの構造化データ語彙のためにHTML文書へ埋め込んで利用する。

**別名:** JSON for Linked Data, JSON for Linking Data, JSON-LD 1.0, JSON-LD 1.1

## 主要な事実

- **標準化団体:** World Wide Web Consortium（W3C） [1]
- **初回W3C勧告:** JSON-LD 1.0（2014-01-16） [4]
- **現行W3C勧告:** JSON-LD 1.1（2020-07-16） (時点 2026-11-23) [1]
- **基盤構文:** JSON（RFC 8259） [1]
- **HTML scriptタイプ:** application/ld+json [8]

## ファクトシート

- **種別:** Linked DataのためのJSONベースシリアライズ形式 [1]
- **標準化団体:** World Wide Web Consortium（W3C） [1]
- **担当グループ:** W3C JSON-LD Working Group（憲章期間2028年1月まで） (時点 2026-11-23) [7]
- **初回勧告:** JSON-LD 1.0（2014-01-16公開、2020-11-03置き換え） [4]
- **現行勧告:** JSON-LD 1.1（2020-07-16） (時点 2026-11-23) [1]
- **関連1.1勧告:** Processing Algorithms and API、Framing [1]
- **1.1版編集者:** Gregg Kellogg、Pierre-Antoine Champin、Dave Longley [1]
- **1.0版編集者:** Manu Sporny、Gregg Kellogg、Markus Lanthaler [4]
- **基盤形式:** JSON（IETF RFC 8259） [5]
- **データモデル互換性:** RDF 1.1グラフおよびRDFデータセット [6]
- **仕様リポジトリ:** github.com/w3c/json-ld-syntax [10]

## JSON-LDの概要

JSON-LD（JSON for Linking Data）は、Linked DataをJSONでシリアライズするためにWorld Wide Web Consortium（W3C）が標準化した軽量な構文である。[1][7] Linked Dataは文書やウェブサイトをまたいで機械可読データを連結し、アプリケーションがあるデータセットから埋め込まれたリンクをたどって他サイト上の関連リソースへ到達できるようにする仕組みである。[1][7] JSON-LDは、ウェブベースのプログラミング環境、相互運用可能なRESTウェブサービス、およびApache CouchDBやMongoDBといったJSONベースのストレージエンジンでの利用を想定して設計されている。[1][7]

すべてのJSON-LD文書はIETF RFC 8259（RFC 7159およびそれ以前のRFC 4627を廃止・置換した標準）が定義する有効なJSONであるため、既存のJSONパーサーやライブラリでそのまま解析できる。[1][4][5] JSON-LD 1.0は当初RFC 4627を参照していたが、JSON-LD 1.1で基盤となるJSONの参照先がRFC 8259へ更新された。[1][4] 標準JSONのプリミティブ型（文字列、数値、真偽値、`null`）および構造型（オブジェクト、配列）に加え、JSON-LDはIRIによるグローバルなオブジェクト識別子、コンテキストを通じた用語とIRIのマッピング、サイト横断のリソース参照、文字列への言語注釈、日付や時刻などの値のデータ型、および有向グラフ表現を追加している。[1][5]

JSON-LD 1.0仕様は、単純性、互換性、表現力、簡潔性、既存JSONシステムへの変更の最小化、およびRDFとしての利用可能性という6つの設計目標を掲げた。[4] 基本的な用途では、専用のJSON-LDプロセッサを用いなくても、JSONと`@context`および`@id`という2つのキーワードの知識だけで利用できる。[4] 運用中のJSON APIにおいては、サーバーがHTTPレスポンスのリンク関係を通じて既存のJSON文書にJSON-LDコンテキストを関連付けることで、既存のJSONペイロードを最小限の変更でJSON-LDとして解釈させることも可能である。[1][4]

## JSON-LDの構文、コンテキスト、およびキーワード

JSON-LDはJSONのオブジェクトと配列を基盤としつつ、独自の構造規則と`@`で始まる予約キーワードを導入している。[1] RFC 8259がJSONオブジェクト内の名前は一意であるべきと規定するにとどまるのに対し、JSON-LDではオブジェクト内のメンバー名は一意でなければならない。[1][5] また、通常のJSONでは配列は順序付きの値列であるが、JSON-LDでは明示的にリストとして定義されない限り、配列コレクションはデフォルトで順序なしとして扱われる。[1][5]

JSON-LDの中核構文は、ウェブ規模でJSONデータに曖昧さのない意味を与えるコンテキストとキーワードを中心に構成されている。[1][4]

- `@context`: JSON文書内の短いプロパティ用語を完全なIRIにマッピングし、異なるJSON文書間で同じキー名が使われても明確に区別された定義を持てるようにする。コンテキストはURL（`https://schema.org/`や`https://json-ld.org/contexts/person.jsonld`など）で参照でき、コンテキスト内で用語またはその`@id`に`null`を割り当てることで、その用語とIRIの紐付けを明示的に解除できる。[1][7][8]
- `@id`: ノードオブジェクトにIRIで表される普遍的な識別子を割り当て、他のオブジェクトや外部文書から同一リソースを参照できるようにする。[1][4][7]
- `@type`: ノードオブジェクトの型（Schema.orgマークアップにおける`Recipe`や`Person`など）を指定するか、型付きの値にデータ型を関連付ける。また、`@set`と組み合わせて使用することもできる。[1][8]
- `null`: 文書本体で値をリセットまたは無視するほか、`@context`内での用語マッピングを解除する。[1]

JSON-LD 1.1はJSON-LD 1.0の上位集合であり、注記のある箇所を除いて1.0文書との互換性を維持している。[1] 1.1仕様には、JSON-LD 1.1処理モード、デフォルト語彙、ベースIRI、コンパクトIRI、キーワードエイリアス、スコープ付きコンテキスト、コンテキスト伝播、インポートコンテキスト、保護された用語定義、JSONリテラル、型強制、基本書字方向を伴う文字列国際化、ネストされたプロパティ、逆プロパティ、インクルードノード、多様なインデックス値（データ、プロパティベース、言語、ノード識別子、ノード型によるインデックス）、およびグラフコンテナを伴う名前付きグラフが規定されている。[1]

## JSON-LDの文書形式、処理API、およびフレーミング

JSON-LDは有向グラフを表現するため、同一の基礎情報を複数の形状でシリアライズできる。[1][3] プログラムによる決定的な処理を支援するため、JSON-LD 1.1仕様群は展開形式（Expanded）、圧縮形式（Compacted）、平坦化形式（Flattened）、およびフレーミング形式（Framed）の4つの文書形式を定義している。[1]

関連するW3C勧告であるJSON-LD 1.1 Processing Algorithms and APIは、文書形式間の変換アルゴリズムとRDFとの相互変換アルゴリズムを定義するとともに、Web IDLで記述された`JsonLdProcessor`アプリケーションプログラミングインターフェース（API）および`JsonLdOptions`設定型を規定している。[2] 主な処理機能には、コンテキスト処理（用語定義の生成、逆コンテキストの生成、用語選択）、展開（IRIおよび値の展開）、圧縮（IRIおよび値の圧縮）、平坦化（ノードマップの生成・統合および空白ノード識別子の割り当て）、リモート文書およびコンテキストの取得、HTMLコンテンツアルゴリズム、およびデータのラウンドトリップを伴うRDFシリアライズ・デシリアライズが含まれる。[2]

3つ目のW3C勧告であるJSON-LD 1.1 Framingは、`JsonLdProcessor`と`JsonLdOptions`を拡張し、開発者が例示によるクエリを実行してJSON-LDグラフに特定のツリー構造を強制できるようにする。[3] Linked Dataグラフは独立したステートメント（トリプル）の集合である一方、アプリケーションは入れ子になったJSONオブジェクトのツリーを前提とすることが多いため、フレームは各主語に関するステートメントを`{`と`}`の区切りの中にまとめ、関連する主語をどのように入れ子にするかを指定する。[3] Framing仕様は、プロパティ、ワイルドカード、不在プロパティ、値、および`@id`によるマッチングに加え、空フレーム、デフォルトコンテンツ、逆フレーミング、名前付きグラフのフレーミング、さらにオブジェクト埋め込み（object embed）、明示的包含（explicit inclusion）、デフォルト省略（omit default）、グラフ省略（omit graph）、全必須（require all）の5つのフレーミングフラグをサポートしている。[3]

## JSON-LDとRDFデータモデル

JSON-LDは、Resource Description Framework（RDF）の知識を持たずにJSONを直接扱う開発者と、RDFデータを処理するシステムの両方に向けて設計されている。[1][4] 2014年2月25日に公開されたW3C勧告「RDF 1.1 Concepts and Abstract Syntax」は、RDFデータの保存および交換のためのシリアライズ構文としてTurtleと並びJSON-LDを明示しており、RDF SchemaやSPARQLクエリ言語と結び付けている。[6]

RDF 1.1の抽象構文では、情報は主語・述語・目的語のトリプルの集合であるRDFグラフ（各ノードはIRI、データ型付き値または言語タグ付き文字列であるリテラル、あるいは空白ノードとなる）と、デフォルトグラフに0個以上の名前付きグラフを組み合わせたRDFデータセットとして構成される。[6] RDFではIRIがグローバルスコープを持つため、別々の箇所に現れる同一のIRIは同一のリソースを指し、ウェブ上で参照解決（デリファレンス）可能な起点として機能する。[6]

JSON-LD 1.1およびそのProcessing Algorithms and API仕様は、JSON-LD文書をRDFデータセットへデシリアライズし、RDFデータセットをJSON-LDへシリアライズし直す決定的なアルゴリズムを定義しており、TurtleやTriGなどの形式と並んで機能する。[1][2] RDF内でJSON-LD 1.1の機能をサポートするため、構文仕様では`rdf:JSON`データ型、`i18n`名前空間、ならびに`rdf:language`および`rdf:direction`プロパティを備えた`rdf:CompoundLiteral`クラスを定義している。[1] また、JSON-LD 1.1仕様ではTurtle、RDFa、Microdataといった他のLinked Dataおよび構造化マークアップ形式との関係も記述されており、JSON-LD 1.0ではさらにMicroformatsとの比較も含まれていた。[1][4]

## HTML、Schema.org、および検索エンジンにおけるJSON-LD

JSON-LD文書はHTMLページ内に直接埋め込むことができ、この機能はJSON-LD 1.0およびJSON-LD 1.1の双方で定義されている。[1][4] JSON-LD 1.1仕様では、HTMLの`script`要素へのJSON-LDの埋め込み、HTML文書の`base`要素からのベースIRI継承、JSON-LD用`script`要素の内容制限、および特定のJSON-LD `script`要素の特定方法が規定されている。[1] 各仕様にはIANA Considerationsの付録も含まれており、Google 検索セントラルの構造化データガイドでは、文書の`head`内に`type="application/ld+json"`を指定した`script`要素を配置してHTMLへ埋め込む例が示されている。[1][4][8]

公開ウェブにおいて、JSON-LDは[Schema.org](https://mimirwiki.com/ja/wiki/schema-org)と組み合わせて利用されている。Schema.orgは、主要検索エンジン（Google、Microsoft、Yandex、Yahoo!）がウェブページの意味を解釈できるようにするための共有語彙である。[9] Schema.orgはMicrodata、RDFa、JSON-LDの3つのマークアップ形式をサポートしており、サイト上の大半の例を3形式すべてで公開している。[9] その型階層は`Thing`（`name`、`description`、`url`、`image`プロパティを持つ）を頂点とし、`CreativeWork`（`Book`、`Movie`、`MusicRecording`、`Recipe`、`TVSeries`を含む）、`Event`、`Organization`、`Person`、`Place`、`LocalBusiness`、`Product`、`Review`といったサブタイプへ分岐している。[9]

Google 検索セントラルは、Google 検索が入れ子になった`Person`の著者情報を参照するSchema.orgの`Recipe`オブジェクトなどのページ内JSON-LD構造化データを読み取り、ページ内容の分類、人物・書籍・企業に関するエンティティ情報の収集、およびリッチリザルトの表示を行う仕組みを文書化している。[8] Schema.orgおよびGoogle 検索セントラルの双方は、構造化データがそのページ上でユーザーに表示されるコンテンツを記述すべきであると明記しており、マークアップのためだけの空ページや非表示コンテンツへのマークアップを避けるよう推奨している。[8][9] Wix、WordPress、Shopifyなどのコンテンツ管理システムを利用するサイト運営者は、プラットフォームの設定やプラグインを通じて構造化データを構成でき、開発者はGoogleのリッチリザルト テストを用いてマークアップの検証や対象検索機能のプレビューを行える。[8]

## JSON-LDのバージョン、ガバナンス、および実装

JSON-LDはJSON for Linking Data Community Groupで発足した後、W3C RDF Working Groupへ移管され、同グループが2014年1月16日にJSON-LD 1.0およびJSON-LD 1.0 Processing Algorithms and APIをW3C勧告として公開した（編集者はManu Sporny、Gregg Kellogg、Markus Lanthaler、共著者はDave Longley、Niklas Lindström）。[2][4] 続くJSON-LD 1.1の策定作業は、JSON-LD Community Groupの最終報告書を基にW3C JSON-LD Working Groupへ引き継がれた。[1] 2019年12月12日の勧告候補（Candidate Release）および2020年5月7日の勧告案（Proposed Recommendation）を経て、同ワーキンググループは2020年7月16日にGregg Kellogg、Pierre-Antoine Champin、Dave Longleyの編集による3つのW3C勧告を公開した。[1][2][3] W3Cは2020年11月3日にJSON-LD 1.0を置き換えられた勧告（Superseded Recommendation）として正式に指定し、新規実装にJSON-LD 1.1を案内しつつ、1.0仕様に対するW3C特許ポリシー上のライセンスコミットメントを維持している。[4]

| 仕様 | 公開日 | 範囲 | リポジトリ |
| --- | --- | --- | --- |
| JSON-LD 1.1 | 2020-07-16 | Linked Data構文、コンテキスト、キーワード、HTML埋め込み、RDFマッピング | `w3c/json-ld-syntax` |
| JSON-LD 1.1 Processing Algorithms and API | 2020-07-16 | 展開、圧縮、平坦化、RDF変換、`JsonLdProcessor` API | `w3c/json-ld-api` |
| JSON-LD 1.1 Framing | 2020-07-16 | 例示によるグラフマッチングおよび決定的ツリー構造 | `w3c/json-ld-framing` |

これら3つの仕様は、W3C JSON-LD Working Groupが策定した公式のJSON-LD 1.1勧告群を構成している。[1][2][3][10]

2026年11月23日時点で、W3C JSON-LD Working Groupは2028年1月まで続く憲章のもとで公式仕様のガバナンスを維持しており、オープンなJSON-LD Community Groupがコミュニティドラフト、議論コール、メーリングリストを調整している。[7] GitHub上の公開リポジトリ`w3c/json-ld-syntax`において、ワーキンググループはJSON-LD 1.1ドラフトが機能凍結（feature frozen）状態にあることを明記し、リポジトリのイシューをバグ報告、既存機能の明確化、および編集上の修正に限定している。[10]

2026年11月23日時点で、json-ld.orgはマークアップのデバッグと可視化のためのウェブベースツール「JSON-LD Playground」を提供し、公式テストスイートと実装レポートを通じて準拠状況を追跡している。また、JavaScript（`json-ld.js`、`jsonld-streaming-parser.js`、`jsonld-streaming-serializer.js`、`rdf-parse.js`）、Python（`PyLD`、`RDFLib`、`TRLD`）、Ruby（`JSON-LD for RDF.rb`）、Go（`JSON-goLD`）、Java（`Titanium`）、C#（`dotNetRDF`）、ErlangおよびElixir（`JSON-LD.ex`）、Rust（`sophia`、`oxjsonld`）、コマンドラインツール（`jsonld-cli`、`ld-cli`）にわたるJSON-LD 1.1準拠ライブラリを掲載し、併せてPHP（`php-json-ld`、`JsonLD`）、Java（`JSONLD-JAVA`）、C#（`json-ld.net`）のJSON-LD 1.0実装も一覧化している。[7] コミュニティドラフトではJSON-LDデータモデルを関連仕様へ拡張しており、人間が記述しやすいYAML向けのYAML-LD、QRコード・PDF417バーコード・NFCタグなど容量制約のある用途向けの圧縮バイナリ形式CBOR-LDのほか、StreamingやJSON-LD-starのドラフトが含まれる。[7]

## よくある質問

### JSON-LDとは何ですか？

JSON-LD（JSON for Linking Data）は、ウェブ上でLinked Dataをシリアライズするための軽量なJSONベースの構文を定義したW3C勧告です。すべてのJSON-LD文書はRFC 8259に準拠した有効なJSONでありながら、コンテキスト、グローバルなIRI識別子、データ型、言語注釈、および有向グラフ構造を追加できます。 [1][5][7]

### JSON-LDにおける@context、@id、@typeの役割は何ですか？

JSON-LDにおいて、@contextは短いJSONプロパティ名を完全なIRIにマッピングし、異なる文書間でもキーが曖昧さのない意味を持つようにします。@idキーワードはノードオブジェクトにグローバルなIRI識別子を割り当て、@typeはノードオブジェクトの型または値のデータ型を指定します。 [1][4][8]

### JSON-LD 1.1ではJSON-LD 1.0から何が更新されましたか？

2020年7月16日に3つのW3C勧告として公開されたJSON-LD 1.1は、注記のある箇所を除き1.0文書との互換性を維持しつつ、2014年のJSON-LD 1.0仕様を置き換えました。基盤となるJSONの参照先をRFC 8259へ更新し、JSON-LD FramingをW3C勧告として標準化したほか、スコープ付きコンテキスト、JSONリテラル、文字列の基本書字方向、追加のインデックス方式などの機能を加えています。 [1][2][3][4]

### JSON-LDの使用にはRDFの知識が必要ですか？

いいえ、必要ありません。W3C仕様では、JSON-LDはRDFの知識がなくても通常のJSONとしてそのまま利用できるとされています。同時に、標準のRDFシリアライズ構文としても機能し、SPARQLなどのツール向けにRDF 1.1グラフおよびデータセットとの相互変換が可能です。 [1][4][6]

### JSON-LD Processing APIとFramingの仕様とは何ですか？

JSON-LD 1.1 Processing Algorithms and APIは、JsonLdProcessorインターフェースおよび展開、圧縮、平坦化、RDF変換のアルゴリズムを定義しています。JSON-LD 1.1 FramingはそのAPIを拡張し、開発者が例示によるクエリを行って有向グラフに決定的な入れ子ツリー構造を適用できるようにします。 [2][3]

### 検索エンジン向けにJSON-LDをHTMLページへ埋め込むにはどうすればよいですか？

JSON-LDは、type属性にapplication/ld+jsonを指定したHTMLのscript要素内に記述し、多くの場合head要素に配置してSchema.orgなどの語彙とともに利用します。Google 検索はページ上の可視コンテンツを記述したJSON-LDを読み取ってエンティティを理解し、リッチリザルトを表示するほか、検証用にリッチリザルト テストを提供しています。 [1][8][9]

## 引用できる文

- W3C RDF Working Groupは2014年1月16日にJSON-LD 1.0をW3C勧告として公開した。 [4]
- W3C JSON-LD Working Groupは2020年7月16日にJSON-LD 1.1、JSON-LD 1.1 Processing Algorithms and API、およびJSON-LD 1.1 FramingをW3C勧告として公開した。 [1][2][3]
- W3Cは2020年11月3日にJSON-LD 1.1を後継としてJSON-LD 1.0を置き換えられた勧告（Superseded Recommendation）に指定した。 [4]
- すべてのJSON-LD 1.1文書はIETF RFC 8259に準拠した有効なJSONであり、オブジェクトのメンバー名は一意で、配列はデフォルトで順序なしとして扱われる。 [1][5]
- RDF 1.1 Concepts and Abstract Syntaxは、RDFデータの保存および交換のためのシリアライズ構文としてTurtleと並びJSON-LDを挙げている。 [6]
- JSON-LD 1.1 Framingにより、開発者は例示によるクエリを実行し、JSON-LDグラフに決定的なツリー構造を適用できる。 [3]
- Schema.orgは、Google、Microsoft、Yandex、およびYahoo!が解釈するマークアップ形式として、MicrodataおよびRDFaと並びJSON-LDをサポートしている。 [9]
- 2026年11月23日時点で、W3C JSON-LD Working Groupの憲章期間は2028年1月までとなっており、GitHubのw3c/json-ld-syntaxリポジトリではJSON-LD 1.1ドラフトが機能凍結状態とされている。 [7][10]

## 年表

- 2014-01-16: W3C RDF Working GroupがJSON-LD 1.0およびJSON-LD 1.0 Processing Algorithms and APIをW3C勧告として公開した。 [2][4]
- 2014-02-25: W3C RDF Working GroupがJSON-LDをRDFシリアライズ構文として挙げたRDF 1.1 Concepts and Abstract SyntaxをW3C勧告として公開した。 [6]
- 2017-12: IETFがJSON-LD 1.1で参照されるJSONデータ交換形式を定義したRFC 8259を公開した。 [1][5]
- 2019-12-12: W3C JSON-LD Working GroupがJSON-LD 1.1、Processing Algorithms and API、およびFramingの勧告候補（Candidate Release）を公開した。 [1][2][3]
- 2020-07-16: W3C JSON-LD Working GroupがJSON-LD 1.1、JSON-LD 1.1 Processing Algorithms and API、およびJSON-LD 1.1 FramingをW3C勧告として公開した。 [1][2][3]
- 2020-11-03: W3CがJSON-LD 1.1を後継としてJSON-LD 1.0を置き換えられた勧告（Superseded Recommendation）に指定した。 [4]

## 出典

1. JSON-LD 1.1. World Wide Web Consortium (W3C). 公開 2020-07-16. https://www.w3.org/TR/json-ld11/ (閲覧 2026-11-23; tier 1: government or public registry)
2. JSON-LD 1.1 Processing Algorithms and API. World Wide Web Consortium (W3C). 公開 2020-07-16. https://www.w3.org/TR/json-ld11-api/ (閲覧 2026-11-23; tier 1: government or public registry)
3. JSON-LD 1.1 Framing. World Wide Web Consortium (W3C). 公開 2020-07-16. https://www.w3.org/TR/json-ld11-framing/ (閲覧 2026-11-23; tier 1: government or public registry)
4. JSON-LD 1.0. World Wide Web Consortium (W3C). 公開 2014-01-16. https://www.w3.org/TR/2014/REC-json-ld-20140116/ (閲覧 2026-11-23; tier 1: government or public registry)
5. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). 公開 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (閲覧 2026-11-23; tier 1: government or public registry)
6. RDF 1.1 Concepts and Abstract Syntax. World Wide Web Consortium (W3C). 公開 2014-02-25. https://www.w3.org/TR/rdf11-concepts/ (閲覧 2026-11-23; tier 1: government or public registry)
7. JSON-LD - JSON for Linked Data. JSON-LD Community Group. https://json-ld.org/ (閲覧 2026-11-23; tier 3: official site)
8. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (閲覧 2026-11-23; tier 3: official site)
9. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (閲覧 2026-11-23; tier 3: official site)
10. GitHub - w3c/json-ld-syntax: JSON-LD 1.1 Specification · GitHub. W3C (GitHub). https://github.com/w3c/json-ld-syntax (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "JSON-LD." 版 6de73c68, 2026-11-23. https://mimirwiki.com/ja/wiki/json-ld
