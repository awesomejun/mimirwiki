---
title: "Schema.org"
subtitle: "検索エンジンやその他のアプリケーション向けにウェブページをマークアップするための共通構造化データ語彙"
canonical_url: https://mimirwiki.com/ja/wiki/schema-org
language: ja
page_class: anchor
revision_sha256: 6014dedc379bf290d5621bdae36ad9207fb6fba2d5c87c5364e3a5faf2c40cec
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/schema-org.md
  txt: https://mimirwiki.com/ja/wiki/schema-org.txt
  json: https://mimirwiki.com/ja/wiki/schema-org.json
  jsonld: https://mimirwiki.com/ja/wiki/schema-org.jsonld
translations:
  en: https://mimirwiki.com/wiki/schema-org
  ko: https://mimirwiki.com/ko/wiki/schema-org
  zh: https://mimirwiki.com/zh/wiki/schema-org
  es: https://mimirwiki.com/es/wiki/schema-org
---

# Schema.org

> Schema.orgは、ウェブページ上の製品、レシピ、イベント、組織などのエンティティを記述するため、2011年にGoogle、Microsoft、Yahoo、Yandexが共同設立した共通の構造化データ語彙である。ウェブサイト運営者はJSON-LD、Microdata、またはRDFaで記述できる。バージョン30.1（2026年9月16日）時点で、CC BY-SA 3.0のもと826個の型と1,540個のプロパティが定義されている。

Schema.orgは、検索エンジンやその他のアプリケーション向けにウェブページへ構造化データを埋め込むために用いられる、型とプロパティの共同語彙である。2011年にGoogle、Microsoft、Yahoo、Yandexによって設立され、RDF Schemaに由来する多重継承階層を維持し、正規の機械可読表現をRDF/Turtle形式で公開している。ウェブパブリッシャーはJSON-LD、Microdata、またはRDFaを使用してHTMLページ内にSchema.orgの用語をエンコードでき、バージョン30.1（2026年9月16日公開）時点で826個の型、1,540個のプロパティ、19個のデータ型、96個の列挙型、544個の列挙メンバーを定義している。日々の更新や議論はW3C Schema.org コミュニティグループおよび公開GitHubリポジトリを通じて調整され、正式なリリースは運営委員会（Steering Group）が承認する。

**別名:** schema.org, Schema.org 語彙, スキーママークアップ

## 主要な事実

- **設立:** 2011年（Google、Microsoft、Yahoo、Yandex） [4]
- **最新リリース:** バージョン30.1（2026-09-16） (時点 2026-11-23) [2]
- **語彙規模:** 826型、1,540プロパティ、19データ型、96列挙型、544列挙メンバー (時点 2026-11-23) [3]
- **対応エンコーディング:** JSON-LD、Microdata、RDFa [5]
- **スキーマライセンス:** クリエイティブ・コモンズ 表示-継承 3.0（CC BY-SA 3.0） [6]

## ファクトシート

- **種別:** ウェブ向けの共通構造化データ語彙 [1]
- **設立年:** 2011年 [4]
- **設立企業:** Google、Microsoft、Yahoo、Yandex [1]
- **ガバナンス:** Schema.org 運営委員会（Steering Group）およびW3C Schema.org コミュニティグループ [1]
- **運営委員会議長:** R.V. Guha (時点 2026-11-23) [1]
- **コミュニティグループ:** W3C Schema.org コミュニティグループ（参加者510名、2015-03-31発足） (時点 2026-11-23) [7]
- **最新リリース:** バージョン30.1（2026-09-16） (時点 2026-11-23) [2]
- **語彙規模:** 826型、1,540プロパティ、19データ型、96列挙型、544列挙メンバー (時点 2026-11-23) [3]
- **正規表現形式:** RDF/Turtle [4]
- **マークアップ形式:** JSON-LD、Microdata、RDFa [5]
- **ライセンス:** CC BY-SA 3.0（スキーマ、ドキュメント、例）、Apache-2.0（サイトソフトウェア） [6]
- **リポジトリ:** github.com/schemaorg/schemaorg（5,741コミット、6.3kスター） (時点 2026-11-23) [8]

## Schema.orgの概要

Schema.orgは、インターネット上の構造化データのためのスキーマを作成、維持、普及させる共同のコミュニティ活動である。[1] Google、Microsoft、Yahoo、Yandexは、ウェブマスターが主要な検索エンジン全般で理解される単一の共通マークアップ語彙を採用できるようにするため、[サイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)（`sitemaps.org`）の理念にならい、2011年に共同プロジェクトとしてSchema.orgを設立した。[4][6] ドメイン名 `schema.org` はOpenDomainプロジェクトによって提供された。[6]

標準的なHTML要素は、`h1` 要素で見出しを整形するなどページコンテンツの表示方法をブラウザに指示するものの、その背後にあるエンティティの種類までは明確に示さない。[5] Schema.orgは、映画、人物、組織、製品、イベントといったエンティティに明示的な機械可読ラベルを付与することで、検索エンジンやその他のソフトウェアがサイト間で一貫してページ内容を解釈できるようにし、誤りの生じやすい自動抽出への依存を軽減している。[5][6] 初期の用語の多くは、Microformats、FOAF、OpenCycといった先行する取り組みから着想を得ている。[6]

Schema.orgは、参加する検索エンジンがサポートするスキーマを文書化する共同イニシアチブとして運営されており、W3CやIETFといった公式の標準化団体とは独立している。[6] あらゆる自然言語で書かれたウェブページにSchema.orgマークアップを含めることができる一方、語彙の用語自体およびSchema.orgのサイトドキュメントは英語で記述されている。[6] Facebook Open Graphなどのプロトコルと併用しつつ、Schema.orgは単一のウェブページ内に存在する複数の異なるエンティティや構成要素をきめ細かく記述するためのマークアップを提供する。[6]

## Schema.orgのデータモデルと語彙構造

Schema.orgは、CycLに由来するRDF Schemaから派生した汎用データモデルを採用している。[4] そのスキーマは型の多重継承階層として構成されており、各型は複数の親型からプロパティを継承できる。[4] 最も広範なルート型は `Thing` であり、`name`、`description`、`url`、`image` といった基本プロパティを提供する。より具体的な型は上位の親型から継承され、例えば `LocalBusiness` は `Place` と `Organization` の両方のサブタイプとなっている。[5]

Schema.orgのプロパティは複数のドメイン（`domainIncludes`）および複数のレンジ（`rangeIncludes`）を持つことができ、プロパティをまとめるためだけに人為的な中間型を作成するのを避ける実用的な設計となっている。[4] `Class` や `Property` のようなメタレベルの型を通じて、スキーマはリフレクションをサポートし、自身の定義を表現できる。[4] Schema.orgの正規の機械可読表現はRDF/Turtle形式で公開されており、開発者向けドキュメントページではRDFや[JSON-LD](https://mimirwiki.com/ja/wiki/json-ld)などの追加の機械可読形式も提供されている。[3][4]

2026年9月16日に公開されたバージョン30.1（2026年11月23日参照）時点で、Schema.orgは以下の語彙構成要素を定義している。[2][3]

| 構成要素 | 件数（バージョン30.1、2026-11-23時点） |
| --- | --- |
| 型（Types） | 826 |
| プロパティ（Properties） | 1,540 |
| データ型（Datatypes） | 19 |
| 列挙型（Enumerations） | 96 |
| 列挙メンバー（Enumeration members） | 544 |

よく使用されるSchema.orgの型グループには、創作物（`CreativeWork`、`Book`、`Movie`、`MusicRecording`、`Recipe`、`TVSeries`）、埋め込みメディアオブジェクト（`AudioObject`、`ImageObject`、`VideoObject`）、`Event`、健康・医療エンティティ（`MedicalEntity`）、`Organization`、`Person`、`Place`（`LocalBusiness`、`Restaurant`）、`Product` および `Offer`（`AggregateOffer`）、`Review` および `AggregateRating`、`Action` があり、テキストや数値などの値に対応する基本データ型も併せて定義されている。[3] 汎用的なリンク用プロパティとしては、ページが記述する主要なエンティティを特定する `mainEntity` および `mainEntityOfPage` があり、`url`、`sameAs`、`about` とともに用いられる。[4]

Schema.orgはポステルの法則（Postel's Law）に基づく実用的な適合モデルを採用しており、型とプロパティの関連付けを厳格な制約ではなくガイドラインとして扱う。[4] 単一のエンティティ記述に `Book` と `Product` のような複数の独立した型のプロパティを組み合わせることができ、構造化されたエンティティ型が期待される箇所にプレーンテキスト文字列やURLを指定することもよく行われる。また、`Role` や `URL` のような型は任意のプロパティで使用できる。[4][5] すべてのプロパティは複数の値を持つことができ、RDFトリプルのもとではデフォルトで順序のない集合として表現される。[4] 順序やコレクションの意味論が必要な場合、パブリッシャーはRDFリスト（`rdf:List`、JSON-LDでは `@list` で表現）またはRDFコンテナ（`rdf:Seq`、`rdf:Bag`、`rdf:Alt`）を使用でき、これらをサポートするパーサーではプロパティの期待レンジがコレクション内の個々の要素に適用される。[4]

Schema.orgは専門分野をホストセクション（`auto`、`bib`、`health-lifesci`、`meta`、`pending`）に分類しており、これらは単一の定義集合に対するビューとして機能する。[3] 活発に議論されている用語は `pending` に配置され、合意形成前に変更される可能性がある。`meta` には技術的定義やサイト機能のための内部語彙が収められ、`attic` には非推奨または不採用となった用語がアーカイブされており、パブリッシャーには使用しないよう注意喚起されている。[3] コア用語とは異なり、`pending`、`meta`、`attic` はフルリリースを経ずに更新できる。[3] GS1 Web VocabularyやCroissant（機械学習データセット向けのコミュニティメタデータ語彙）などの独立した外部拡張は、運営委員会の公式承認を得ずにSchema.orgを拡張している。[3]

## Schema.orgのエンコーディングと用語識別子

Schema.orgの用語は、[JSON-LD](https://mimirwiki.com/ja/wiki/json-ld)、Microdata、RDFaという3つの主要なシリアライゼーション形式を用いてウェブページに埋め込むことができる。[4][5][6] Schema.orgはプロジェクト発足時に実用的な選択としてMicrodataを重視していたが、語彙の混在やプロパティ関係の反転といった作業がMicrodataでは難しいことを踏まえ、RDFaやJSON-LDにも対応するようドキュメントと例を拡充した。[6]

| 形式 | エンコーディング方式 | 仕様と特徴 |
| --- | --- | --- |
| JSON-LD | `type="application/ld+json"` を指定したHTML `script` 要素内に、`@context` と `@type` を用いたJSONオブジェクトを埋め込む | W3C勧告（`JSON-LD 1.1` は2020-07-16公開、2014-01-16の `JSON-LD 1.0` を置換）。JSON（RFC 8259）と100%互換性があり、RDFグラフと相互運用可能 |
| Microdata | コンテンツ要素にHTML5のインライン属性 `itemscope`、`itemtype`、`itemprop` を付与し、埋め込みアイテムには新たな `itemscope` ブロックを入れ子にする | HTML5とともに導入。アイテムの型は `https://schema.org/Movie` のようなSchema.orgのURLで指定 |
| RDFa（RDFa Lite） | コンテンツ要素にHTMLのインライン属性 `vocab="https://schema.org/"`、`typeof`、`property` を付与する | Microdataとほぼ同型に対応（`itemprop` は `property`、`itemtype` は `typeof` となり、`itemscope` は省略される） |

上記の表は、Schema.org、Google 検索セントラル、およびW3C仕様書に記載されたエンコーディングの詳細をまとめたものである。[4][5][9][10] HTMLマークアップにおいて、Schema.orgは機械可読な曖昧性解消パターンも文書化している。具体的には、日時用に `YYYY-MM-DD` 形式（任意で `T` と `hh:mm` または `hh:mm:ss` を付加）の `datetime` 属性を持つHTML `time` 要素、列挙型や正規参照用に `href` 属性を持つHTML `link` 要素、暗黙的な値のために `content` 属性を持つHTML `meta` 要素が挙げられる。[5]

Schema.orgは当初、`http://schema.org/` のURLをRDF用語識別子とする `http:` ウェブサイトとして開始され、のちに公開ウェブサイトと推奨ドキュメント例を `https://schema.org/` へ移行した。[7] Schema.orgのドキュメントでは、構造化データマークアップにおいて `https://schema.org` と `http://schema.org` のいずれも有効であり広く理解されると明記されている。[7] 静的ファイルホスティングへの移行に伴い、Schema.orgはリモートJSON-LDコンテキストのHTTPコンテンツネゴシエーションを廃止し、`rel="alternate"` および `type="application/ld+json"` で `/docs/jsonldcontext.jsonld` を指すHTTP `Link` ヘッダーに置き換えた。[7] 世界中の既存のRDFパーサーが出力するトリプルを意図せず変更しないよう、このコンテキストドキュメントは引き続き `http:` をベースURLとして維持している。このため、Dan Brickleyは2026年10月30日に、マークアップが `https://schema.org` を参照していてもJSON-LDパーサーは依然として `http://` のトリプルを出力すると指摘し、Schema.orgデータを集約するデータ利用者に対して識別子の正規化（canonicalization）を行うよう助言した。[7]

## Schema.orgのガバナンス、リポジトリ、ライセンス

Schema.orgは、運営委員会（Steering Group）とW3C Schema.org コミュニティグループから成る二層構造で統治されている。[1] 運営委員会は全体的な監督、運営上の意思決定、および正式リリースの承認を担う。[1] GoogleでSchema.orgを立ち上げた共同設立者のR.V. Guhaが個人の資格で運営委員会の議長を務めており（2026年11月23日時点）、設立企業のGoogle、Microsoft、Yahoo、Yandexの各代表、W3C代表、および主要なコミュニティ貢献者が参加している。[1] 2015年4月、運営委員会は全会一致でメンバーを拡大し、Stéphane Corlosquet、Martin Hepp（GoodRelationsの作者）、およびW3Cの議席を追加した。[1] 運営委員会の議論は公開されており、議事録はGitHubに投稿されイシュー#1からリンクされている。[1]

W3C Schema.org コミュニティグループはDan Brickleyによって提案され2015年3月31日に発足し、2015年4月に日々のスキーマ議論、提案作成、拡張レビューのための主要な公開フォーラムとなった。[1][7] W3Cアカウントを持ち、W3C Community Contributor License Agreementに署名すれば誰でも参加でき、W3CはグループのホスティングがW3C会員やスタッフによる承認を意味しないことを明示している。[1][7] 2026年11月23日時点で、コミュニティグループには510名の参加者がおり、Dan Brickley、Dan Scott、Stéphane Corlosquet、Phil Barker、Phil Archer、Ryan Leveringの6名が議長として名を連ねている。[7] Dan Brickleyは日常運営とプロジェクトのウェブマスターも務めており、運営委員会におけるGoogle代表としての役割とは独立して、Schema.orgを代表しコミュニティグループの議長を務めている。[1] 議論はメーリングリスト `public-schemaorg@w3.org` とGitHub上で行われており、健康・医療、スポーツ、アーカイブ、書誌、自動車などの分野における関連W3Cコミュニティグループが専門領域の作業を調整している。[1][7]

Schema.orgは、スキーマ（`data`）、ドキュメント（`docs`）、テンプレート、`versions.json`、およびサイトソフトウェア（`software`、一部は `sdopythonapp` サブモジュールから取り込み）を公開GitHubリポジトリ `github.com/schemaorg/schemaorg` で管理している。[8] 2026年11月23日時点で、このリポジトリには5,741件のコミット、6.3kスター、975件のフォーク、388名のウォッチャー、301件のオープンイシュー、14件のオープンプルリクエストが記録されている。[8] イシュー#1はリリース計画の索引として機能し、イシュー#2および#3は語彙やツール関連の作業を整理している。プルリクエストは継続的インテグレーション（CI）テストによって検証され、リリースのドラフトは `staging.schema.org` で公開検証される。[1][2][8] プロジェクトの貢献ガイドラインでは、検索エンジンに加えてウェブ解析、ブラウザアドオン、クラウドツールといった実際の利用アプリケーションに裏付けられた段階的な修正と追加を優先しており、地域的な実用性や、GoodRelations、GS1、IPTC rNews、MARC、BibFrame、FRBR、BBC、欧州放送連合（European Broadcasting Union）、Music Ontology、MusicBrainzなどの外部標準との整合性を重視している。[8]

Schema.orgは、スキーマ定義、サイトドキュメント、ブログ記事、マークアップ例をクリエイティブ・コモンズ 表示-継承 3.0（CC BY-SA 3.0）ライセンスのもとで公開している。[6] Schema.orgサイトの運用に使用される関連ソフトウェアは、Apache-2.0オープンソースライセンスのもとで公開されている。[6][8]

## Schema.orgのリリース履歴

Schema.orgは、運営委員会および広範なコミュニティによるレビューを経てバージョン付きの正式リリースを公開しており、最新リリースの概要は `https://schema.org/version/latest` で提供されている。[2][8] 2026年11月23日時点で、最新の公開リリースは2026年9月16日に発行されたバージョン30.1である。[2]

バージョン30.1（2026年9月16日）では、EUデジタル製品パスポート（EU Digital Product Passports）の発見を支援する語彙が導入され、`DigitalProductPassport` クラス、`hasDigitalProductPassport`、`Certification` のサブタイプとしての `EnvironmentalProductDeclaration` および `DeclarationOfConformity`、製品プロパティ `authorizedRepresentative`、`importer`、`recycledContentPercentage`、`substanceOfConcern` が追加された。[2] 同リリースではさらに、`consumerNotice`、`isOftenBoughtWith`、`specification`、`valueGroup`、`itemPopularity`、`minimumOrderValue`、および列挙値 `MaximumRetailPrice` を含む小売フィード用プロパティが追加されたほか、順序付きリストの明示的サポートの文書化、用語利用統計の更新、`MedicalSpecialty` への `Ophthalmology` および `Audiology` の追加、採用済み `pending` 用語の一般提供（GA）への昇格も行われた。[2]

バージョン30.1以前の主要な最近のリリースは以下の通りである。[2]

| バージョン | 公開日 | 主な追加および変更点 |
| --- | --- | --- |
| 30.1 | 2026-09-16 | EUデジタル製品パスポート関連の型・プロパティ、小売フィード語彙、順序付きリストの文書化、`pending` からGAへの昇格 |
| 30.0 | 2026-03-19 | GS1、Dublin Core、Open Graphの同等性アノテーションとエクスポート、UN/CEFACTに準拠したEUデジタル製品パスポート例、`Credential` および `Error` クラス、`Quantity` の継承元を `DataType` へ変更 |
| 29.4 | 2025-12-08 | `ConferenceEvent`、`PerformingArtsEvent`、`InstantaneousEvent`、認証アクション（`AuthenticateAction`、`LoginAction`、`ResetPasswordAction`）、`OperatingSystem`、`RuntimePlatform`、`SequentialArt`（`GraphicNovel` を非推奨化）、UN/CEFACT、OWL、OMG、GS1向けOWL同等性 |
| 29.3 | 2025-09-04 | `recipeIngredient` のレンジ拡張、`OnlineMarketplace` および `hasStore` / `isStoreOn` の追加 |
| 29.0 | 2025-03-24 | `FinancialIncentive` 語彙、`Legislation` 上の欧州法令識別子（ELI）プロパティ、配送関連型の改訂（`ShippingConditions`、`ShippingService`、`DeliveryTimeSettings` を非推奨化） |
| 28.0 | 2024-09-17 | ロイヤルティ・会員プログラム関連の型（`MemberProgram`、`MemberProgramTier`、`TierBenefitEnumeration`） |
| 27.02 | 2024-07-01 | 編集用ステージングサイトを `webschemas.org` から `staging.schema.org` へ移行 |
| 27.01 | 2024-06-24 | Schema.orgサイトのデザイン刷新 |
| 27.0 | 2024-05-20 | `hasGS1DigitalLink` および `certificationRating` の追加 |

パッチリリースであるバージョン29.1（2025年4月25日）およびバージョン29.2（2025年5月13日）では、バージョン29.0で生じたリグレッションを修正するとともに、`pronouns`、`companyRegistration`、`Cooperative`、`referee` などのプロパティや型が追加された。[2] また、`pending`、`meta`、`attic` 内の用語はフルリリースの合間にも更新されることがある。[3]

## Schema.orgの検索エンジンでの利用と制約

Schema.orgマークアップは、Google、Microsoft、Yahoo、Yandexなどの検索エンジンによってページ上のエンティティを解釈し、リッチリザルトを表示するために利用されている。[5][6][9] Google 検索セントラルでは、Article（記事）、Breadcrumb（パンくずリスト）、Course list（コースリスト）、Dataset（データセット）、Discussion forum（ディスカッション フォーラム）、Event（イベント）、Fact check（ファクトチェック）、Image metadata（画像メタデータ）、Job posting（求人情報）、Local business（ローカルビジネス）、Organization（組織）、Product snippet（商品スニペット）、Merchant listing（販売者リスティング）、Profile page（プロフィールページ）、Q&A、Recipe（レシピ）、Review snippet（レビュー スニペット）、Software app（ソフトウェア アプリ）、Speakable、Subscription and paywalled content（定期購入とペイウォール コンテンツ）、Vacation rental（バケーション レンタル）、Video（動画）といったコンテンツ種別に対応する構造化データ機能が文書化されている。[9] 例えばレシピページでは、構造化データで材料、カロリー、調理時間をラベル付けすることで、Google検索がリッチリザルトを表示し属性レベルでの絞り込みに対応できる。[9] Wix、WordPress、Shopifyなどのコンテンツ管理システム（CMS）は、HTMLを直接編集せずに構造化データを追加できる組み込み設定やプラグインを提供している。[9]

パブリッシャーは、公式資料で案内されている2つの主要な検証ツールを用いて構文と構造を確認できる。Schema.org マークアップ検証ツール（Schema.org Markup Validator）はSchema.orgの構造を検査してRDFコレクション（`List`、`Bag`、`Seq`、`Alt`）を表示し、Googleのリッチリザルト テスト（Rich Results Test）は構造化データを検証して対象となるGoogle検索機能をプレビューする。[4][9]

Schema.orgおよび検索エンジンのドキュメントでは、構造化データの利用における実践的な境界と制約がいくつか示されている。

- **選択的な機能表示**：Schema.orgのFAQは、検索エンジンがSchema.orgに定義されたすべての情報種別を表示するわけではないと述べており、パブリッシャーはサポートされる具体的な機能について各検索エンジンのドキュメントを確認する必要がある。[6]
- **可視コンテンツの原則**：Schema.orgのガイドラインとGoogle 検索セントラルはいずれも、ページ上でユーザーに表示されるコンテンツのみをマークアップするよう指示しており、構造化データを置くためだけの空ページの作成や、基礎データが正確であっても非表示のマークアップを行うことを避けるよう求めている。[5][6][9]
- **任意かつ部分的なマークアップ**：アイテムのすべてのプロパティをマークアップする必要はなく、正確なサブタイプが存在しない場合はマークアップを行わないか、`Person` のようなより広範な親型を使用するか、あるいは拡張を定義できる。[6]
- **限定されたオントロジー範囲**：Schema.orgは実用的なウェブ公開のためにウェブコンテンツを簡素化しており、包括的なドメインオントロジーは独立した語彙や外部拡張に委ねている。[4][8]
- **パーサーと識別子の多様性**：Schema.orgはすべてのパーサーにRDFコレクションやコンテナの実装を義務付けておらず、ウェブ上のコーパスにはMicrodata、RDFa、JSON-LDにわたって `http://` と `https://` の識別子が混在しているため、データ利用者は識別子の正規化と簡易的な文字列値の処理に対応する必要がある。[4][7]

## よくある質問

### Schema.orgとは何ですか？

Schema.orgは、ウェブページに機械可読な構造化データを追加するための型（タイプ）とプロパティの共同語彙です。主要な検索エンジンや各種アプリケーション間で単一の共通マークアップ語彙をウェブサイトが利用できるようにするため、2011年にGoogle、Microsoft、Yahoo、Yandexが共同で設立しました。 [1][4]

### Schema.orgはW3Cのような公式の標準化団体ですか？

いいえ。Schema.orgは、主要な検索エンジンがサポートするスキーマを文書化する共同活動であり、W3CやIETFのような公式の標準化団体とは異なります。W3Cは公開の議論の場としてSchema.org コミュニティグループをホストしていますが、W3CによるホスティングはW3C会員やスタッフによる公式な承認を意味するものではありません。 [6][7]

### Schema.orgではどのマークアップ形式を使用できますか？

ウェブサイト運営者は、JSON-LD、Microdata、またはRDFa（RDFa Liteを含む）を使用して、Schema.orgの用語をウェブページにエンコードできます。Schema.org語彙自体の正規の機械可読表現は、RDF/Turtle形式で公開されています。 [4][5][6]

### Schema.org語彙の規模はどれくらいですか？

2026年9月16日に公開されたバージョン30.1（2026年11月23日参照）時点で、Schema.org語彙には826個の型、1,540個のプロパティ、19個のデータ型、96個の列挙型、544個の列挙メンバーが含まれています。また、検討中の用語を収めるpendingセクションや、非推奨の用語を保管するatticアーカイブなどのホストセクションも備えています。 [2][3]

### Schema.orgの語彙とソフトウェアにはどのようなライセンスが適用されていますか？

Schema.orgのスキーマ、サイトドキュメント、ブログ記事、マークアップ例は、クリエイティブ・コモンズ 表示-継承 3.0（CC BY-SA 3.0）ライセンスのもとで公開されています。サイトの公開に使用される関連ソフトウェアは、Apache-2.0オープンソースライセンスのもとで公開されています。 [6][8]

### Schema.orgのすべての型が検索エンジンの検索結果に表示されますか？

いいえ。Schema.orgのFAQによれば、検索エンジンは語彙に定義されたあらゆる種類の情報を表示するわけではなく、各検索エンジンがサポートする機能や型を個別に文書化しています。Google 検索セントラルも、ページ上の構造化データは、そのページで訪問者に表示されるコンテンツを記述したものでなければならないと明記しています。 [6][9]

## 引用できる文

- Schema.orgは、ウェブページ向けの共通の構造化データ語彙を提供するため、2011年にGoogle、Microsoft、Yahoo、Yandexによって共同設立された。 [1][4]
- W3C Schema.org コミュニティグループは、Schema.orgの変更や拡張を議論する公開フォーラムとして2015年3月31日に提案・発足した。 [7]
- 2026年11月23日時点で、Schema.orgの最新公開リリースは2026年9月16日に公開されたバージョン30.1である。 [2]
- 2026年11月23日時点で、Schema.org語彙は826個の型、1,540個のプロパティ、19個のデータ型、96個の列挙型、544個の列挙メンバーで構成されている。 [3]
- Schema.orgマークアップはJSON-LD、Microdata、RDFaを用いてウェブページに記述でき、スキーマの正規の機械可読表現はRDF/Turtle形式である。 [4][5]
- Schema.orgのスキーマ、サイトドキュメント、ブログ記事、マークアップ例はクリエイティブ・コモンズ 表示-継承 3.0（CC BY-SA 3.0）でライセンスされており、サイトを支えるソフトウェアにはApache-2.0ライセンスが適用されている。 [6][8]
- JSON-LD 1.1は、2014年1月16日のJSON-LD 1.0勧告を置き換えるW3C勧告として2020年7月16日に公開された。 [10]
- Google 検索セントラルのドキュメントは、ページ上の構造化データが、そのページでユーザーに表示されるコンテンツを記述したものでなければならないと明記している。 [9]

## 年表

- 2011: Google、Microsoft、Yahoo、Yandexが、ウェブページ向けの共通構造化データ語彙を提供するSchema.orgを立ち上げた。 [4][8]
- 2014-01-16: W3CがJSON-LD 1.0をW3C勧告として公開した。 [10]
- 2015-03-31: Dan BrickleyがW3C Schema.org コミュニティグループを提案・発足させた。 [7]
- 2015-04: Schema.org 運営委員会がコミュニティ貢献者のStéphane CorlosquetとMartin Hepp、およびW3C代表を加えて拡大され、W3C コミュニティグループが主要な協業フォーラムとなった。 [1]
- 2020-07-16: W3CがJSON-LD 1.0を置き換えるJSON-LD 1.1をW3C勧告として公開した。 [10]
- 2024-07-01: Schema.orgがバージョン27.02を公開し、編集用ステージングサイトをwebschemas.orgからstaging.schema.orgへ移行した。 [2]
- 2025-03-24: Schema.orgが、金融インセンティブ向けの新語彙、欧州法令識別子（ELI）プロパティ、改訂された配送スキーマを含むバージョン29.0を公開した。 [2]
- 2026-03-19: Schema.orgが、GS1、Dublin Core、Open Graphの同等性アノテーションおよびEUデジタル製品パスポート例を追加したバージョン30.0を公開した。 [2]
- 2026-09-16: Schema.orgが、EUデジタル製品パスポート関連の型、小売フィード用プロパティ、順序付きリストの明示的ドキュメントを追加したバージョン30.1を公開した。 [2]

## 出典

1. About - Schema.org. Schema.org. https://schema.org/docs/about.html (閲覧 2026-11-23; tier 3: official site)
2. Release listing - schema.org. Schema.org. 公開 2026-09-16. https://schema.org/docs/releases.html (閲覧 2026-11-23; tier 3: official site)
3. Schemas - Schema.org. Schema.org. https://schema.org/docs/schemas.html (閲覧 2026-11-23; tier 3: official site)
4. Data model - Schema.org. Schema.org. https://schema.org/docs/datamodel.html (閲覧 2026-11-23; tier 3: official site)
5. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (閲覧 2026-11-23; tier 3: official site)
6. FAQ - schema.org. Schema.org. https://schema.org/docs/faq.html (閲覧 2026-11-23; tier 3: official site)
7. Schema.org Community Group. World Wide Web Consortium (W3C). https://www.w3.org/community/schemaorg/ (閲覧 2026-11-23; tier 1: government or public registry)
8. GitHub - schemaorg/schemaorg: Schema.org - schemas and supporting software · GitHub. Schema.org (GitHub). https://github.com/schemaorg/schemaorg (閲覧 2026-11-23; tier 3: official site)
9. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (閲覧 2026-11-23; tier 3: official site)
10. JSON-LD 1.1. World Wide Web Consortium (W3C). 公開 2020-07-16. https://www.w3.org/TR/json-ld11/ (閲覧 2026-11-23; tier 1: government or public registry)

## このページを引用する

Mimirwiki. "Schema.org." 版 6014dedc, 2026-11-24. https://mimirwiki.com/ja/wiki/schema-org
