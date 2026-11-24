---
title: "サイトマップ"
subtitle: "ウェブサイトのURLとメタデータを検索エンジンクローラーに一覧提示するためのXMLベースのプロトコル"
canonical_url: https://mimirwiki.com/ja/wiki/sitemaps
language: ja
page_class: anchor
revision_sha256: e676d27955153993adb1372fd3e7b9ca1fddc724dee454fb37da653fc8fdf4bc
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/sitemaps.md
  txt: https://mimirwiki.com/ja/wiki/sitemaps.txt
  json: https://mimirwiki.com/ja/wiki/sitemaps.json
  jsonld: https://mimirwiki.com/ja/wiki/sitemaps.jsonld
translations:
  en: https://mimirwiki.com/wiki/sitemaps
  ko: https://mimirwiki.com/ko/wiki/sitemaps
  zh: https://mimirwiki.com/zh/wiki/sitemaps
---

# サイトマップ

> サイトマップ（Sitemaps）は、Google、Yahoo、Microsoftが後援するXMLプロトコルであり、ウェブサイトがクロール可能なURLとメタデータを検索エンジンに一覧提示できるようにする仕組みである。2026-11-23時点で、バージョン0.9は各サイトマップまたはインデックスファイルの上限を50,000エントリおよび非圧縮50 MBと定めており、RSS、Atom、テキストファイルや各種拡張機能にも対応する。URLの記載は発見を支援するが、インデックス登録自体は任意である。

サイトマップ（Sitemaps）は、ウェブサイト運営者がクロール可能なページ、画像、動画、その他のファイルおよび最終更新日などのメタデータを検索エンジンに通知するためのXMLベースのウェブプロトコルである。sitemaps.orgを通じてGoogle, Inc.、Yahoo, Inc.、およびMicrosoft Corporationが後援するプロトコルバージョン0.9は、個別のサイトマップファイル（urlset）とサイトマップインデックスファイル（sitemapindex）のXMLスキーマを定義するとともに、シンジケーションフィードやプレーンテキストのURLリストにも対応している。2026-11-23時点で、各サイトマップファイルは50,000 URLおよび非圧縮50 MB（52,428,800バイト）までに制限されており、検索エンジンごとのXML拡張によって画像やニュース記事などの特定コンテンツにも対応できる。サイトマップの公開は検索エンジンクローラーによるURL発見を支援するが、記載されたエントリをクロールまたはインデックス登録するかどうかは各検索エンジンの完全な裁量に委ねられる。

**別名:** Sitemaps, サイトマッププロトコル, XML サイトマップ, sitemap.xml, Sitemaps 0.9

## 主要な事実

- **プロトコルバージョン:** 0.9（http://www.sitemaps.org/schemas/sitemap/0.9） (時点 2026-11-23) [1]
- **後援企業:** Google, Inc.、Yahoo, Inc.、Microsoft Corporation [3]
- **ファイルあたりの上限:** 50,000 URLおよび非圧縮50 MB（52,428,800バイト） (時点 2026-11-23) [1]
- **文字エンコーディング:** UTF-8 [1]
- **仕様ライセンス:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]

## ファクトシート

- **種別:** クロール可能なURLを検索エンジンクローラーに通知するためのウェブプロトコル [1]
- **後援企業:** Google, Inc.、Yahoo, Inc.、Microsoft Corporation [3]
- **プロトコルバージョン:** 0.9 (時点 2026-11-23) [1]
- **XML名前空間:** http://www.sitemaps.org/schemas/sitemap/0.9 (時点 2026-11-23) [1]
- **XMLスキーマ:** sitemap.xsd（サイトマップ）およびsiteindex.xsd（サイトマップインデックスファイル） (時点 2026-11-23) [2]
- **対応形式:** XML、RSS 2.0、Atom 0.3または1.0、UTF-8プレーンテキスト (時点 2026-11-23) [1]
- **ファイルあたりのエントリ上限:** サイトマップ1件あたり50,000 URL、サイトマップインデックス1件あたり50,000サイトマップ (時点 2026-11-23) [1]
- **ファイルあたりのサイズ上限:** 非圧縮で50 MB（52,428,800バイト）、gzip圧縮に対応 (時点 2026-11-23) [1]
- **locの最大文字数:** 2,048文字未満 (時点 2026-11-23) [1]
- **仕様ライセンス:** Creative Commons Attribution-ShareAlike License (version 2.5) [3]
- **Google Search Consoleのインデックス上限:** 1サイトあたり最大500件のサイトマップインデックスファイル (時点 2025-12-10) [7]

## サイトマッププロトコルの概要

サイトマップ（Sitemaps）プロトコルは、ウェブサイト運営者がクロール可能なページ、画像、動画、その他のファイルを検索エンジンに通知するためのXMLベースの仕様である。[1][5] Sitemaps.orgはGoogle, Inc.、Yahoo, Inc.、およびMicrosoft Corporationによって後援されており、各後援企業は本仕様に関する著作権をクリエイティブ・コモンズ 表示-継承 2.5 ライセンス（Creative Commons Attribution-ShareAlike License version 2.5）の下で提供している。[3] Sitemaps.orgの利用規約によれば、いずれの後援企業も公開されたサイトマップを読み取る、インデックス登録する、または使用する義務を負わず、いつでもプロトコルへの対応を変更または終了することができる。[3]

URLの一覧提示に加えて、サイトマップはファイル間の関係性や最終更新日、ページの[代替言語バージョン](https://mimirwiki.com/ja/wiki/hreflang)といったメタデータを伝達できる。[5] XMLスキーマが主要形式であるものの、サイトマッププロトコルおよびGoogle検索はシンジケーションフィードとプレーンテキストのURLリストにも対応している。[1][6]

- **XMLサイトマップ**: 画像、動画、ニュース、およびローカライズされたページバージョンのメタデータを格納できる拡張可能な形式である。多くのコンテンツ管理システム（CMS）はXMLサイトマップを自動生成するかプラグインを通じて生成するが、大規模または更新頻度の高いサイトではXMLマッピングの維持が複雑になり得る。[1][6]
- **RSS、mRSS、およびAtomフィード**: Sitemaps.orgはRSS 2.0とAtom 0.3または1.0に対応し、`link`フィールドをURLとして、任意の`pubDate`（RSS）または`updated`（Atom）フィールドを更新日として読み取る。[1] フィードは最近のURLのみを含むことが多く、クロール対象となる最上位ディレクトリに配置すべきである。[1] GoogleはHTML、インデックス可能なテキストコンテンツ、および動画メタデータに対してRSS、mRSS、Atom 1.0フィードに対応しているが、画像とニュースのメタデータにはXML拡張が必要である。[6]
- **プレーンテキストサイトマップ**: ヘッダー、フッター、追加のメタデータを含まず、1行につき1つの完全修飾URLを記載するUTF-8テキストファイルであり、HTMLおよびその他のインデックス可能なテキストページに限定される。[1][6]

WordPress、Wix、Bloggerなどのコンテンツ管理システムは、一般的にサイトマップを自動生成する。[5] 2025-12-10に更新されたGoogle 検索セントラルのドキュメントによると、サイトマップは内部リンクだけでは新規ページを見落としやすい大規模サイト、外部リンクが少ない新規サイト、および動画・画像・Google ニュースのコンテンツが豊富なサイトにおいて特に有用である。[5] 一方、およそ500ページ以下でホームページから網羅的に内部リンクが張られており、メディアやニュースページが少ない小規模サイトでは、サイトマップが不要な場合がある。[5]

## サイトマップのXML形式と要素

サイトマッププロトコル 0.9は、名前空間`http://www.sitemaps.org/schemas/sitemap/0.9`の下でUTF-8エンコードされたXML文書形式を定義している。[1] 検証用の公式XMLスキーマ定義ファイルとして、サイトマップファイル用の`http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd`と、サイトマップインデックスファイル用の`http://www.sitemaps.org/schemas/sitemap/0.9/siteindex.xsd`の2つが提供されている。[2]

URLを含むすべてのXML値は、RFC 3986（URI）、RFC 3987（IRI）、およびXML標準に従う必要があり、非ASCII文字に対するURLパーセントエンコーディングと、5つの予約文字に対するXMLエンティティエスケープコードの両方を使用する。対象となる予約文字は、アンパサンド（`&`を`&amp;`）、シングルクォート（`'`を`&apos;`）、ダブルクォート（`"`を`&quot;`）、大なり記号（`>`を`&gt;`）、および小なり記号（`<`を`&lt;`）である。[1][2] 2026-11-23時点で、サイトマッププロトコル 0.9はサイトマップファイル向けに6つの基本要素を定義している。[1]

| 要素 | 要件 | 値の規則と役割 |
| --- | --- | --- |
| `urlset` | 必須 | ファイル全体を囲み、プロトコル 0.9のXML名前空間を宣言するルート要素。[1] |
| `url` | 必須 | 各URLエントリの親要素であり、残りのタグはすべてその子要素として配置される。[1] |
| `loc` | 必須 | プロトコル（`http`や`https`など）で始まり、サーバーが要求する場合は末尾にスラッシュを含み、長さが2,048文字未満である完全修飾ページURL。[1][2] |
| `lastmod` | 任意 | W3C Datetime形式（`YYYY-MM-DD`、またはタイムゾーンを含む完全なISO 8601日時）によるページの最終更新日。サイトマップ生成時刻やHTTP `If-Modified-Since`（304）ヘッダーとは別に、ページの更新日を記録する。[1][2] |
| `changefreq` | 任意 | ページの更新頻度に関する一般的な目安。有効な値は`always`（アクセスごとに変化する文書）、`hourly`、`daily`、`weekly`、`monthly`、`yearly`、および`never`（アーカイブ済みURL）である。[1] |
| `priority` | 任意 | 同一サイト内の他のURLと比較した相対的な重要度。`0.0`から`1.0`の範囲で指定し、既定値は`0.5`である。[1] |

仕様およびGoogle検索のドキュメントでは、記載するURLに関する追加規則も定められている。`/mypage.html`のような相対パスは無効であるため、エントリは完全な絶対URLでなければならず、Googleは記載されたとおりのURLをクロールしようとする。[2][6] サイト運営者はHTTPとHTTPSの両方のURLが存在する場合に片方のプロトコルバージョンのみを記載し、不完全または重複したクロールを避けるためにセッションIDを除去し、フレームを用いたページではフレームセットとフレームコンテンツ双方のURLを含めるべきである。[2] サイトマップ内におけるURLの記載順は、検索エンジンによる処理方法に影響しない。[2] Googleはサイトマップが正規URLの選択に影響を与え得ることを示しており、デスクトップ版とモバイル版でURLが分かれている場合は、どちらか一方のみを記載するか、両バージョンにアノテーションを付与することを推奨している。[6]

## サイトマップインデックスファイルとサイズ制限

2026-11-23時点で、サイトマップファイルはXML形式およびプレーンテキスト形式のいずれにおいても、1ファイルあたり50,000 URLおよび非圧縮50 MB（52,428,800バイト）に制限されている。[1][2][6] 帯域幅を削減するため、サイト運営者はサイトマップファイルをgzipで圧縮できるが、非圧縮状態のファイルサイズは50 MBの上限内に収める必要があり、sitemaps.org FAQは圧縮サイトマップの形式としてgzipを指定している。[1][2]

サイトのURL数が50,000件を超えるかファイルサイズが50 MBを超える場合は、URLを複数のサイトマップファイルに分割し、それらを1つ以上のサイトマップインデックスファイルにまとめる必要がある。[1][2][7] サイトマップインデックスファイルは、個別のサイトマップと同じUTF-8エンコーディングおよび`http://www.sitemaps.org/schemas/sitemap/0.9`名前空間を使用する。[1][7] 2026-11-23時点で、各サイトマップインデックスファイルは最大50,000件のサイトマップを記載でき、非圧縮で50 MB（52,428,800バイト）を超えてはならず、gzip圧縮にも対応している。[1][2][7]

サイトマップインデックスファイルでは、プロトコル 0.9で定義された4つのXML要素を使用する。[1][7]

- `sitemapindex`（必須）: 記載されたすべてのサイトマップエントリを囲むルート要素。[1][7]
- `sitemap`（必須）: 各個別サイトマップの親要素であり、`sitemapindex`の唯一の直接の子要素。[1][7]
- `loc`（必須）: サイトマップの場所を示すエンティティエスケープ済みのURL。対象はXMLサイトマップ、RSSファイル、Atomファイル、またはプレーンテキストファイルのいずれでもよい。[1][7]
- `lastmod`（任意）: 参照先サイトマップファイル内に記載された個別ページの更新時期とは独立して、そのサイトマップファイル自体が更新された日時を示すW3C Datetimeタイムスタンプ。[1][7]

サイトマップインデックス内で`lastmod`を指定すると、クローラーが最近更新されたサイトマップのみを取得する増分サイトマップ取得が可能になる。[1][2] 数千万件のURLを持つサイトでは、頻繁に更新されるURLを少数のサイトマップにまとめてサイトマップインデックスで`lastmod`を付与することで、検索エンジンが更新を迅速に発見しやすくなる。[1][2] 2025-12-10時点で、Google Search Consoleはサイト所有者に対し1サイトあたり最大500件のサイトマップインデックスファイルの送信を許可しており、複数のサイトマップを分けて送信することでSearch Console上のサイトマップ別パフォーマンス追跡にも対応できる。[6][7]

## サイトマップファイルの配置、適用範囲、および発見手法

サイトマップファイルの配置場所によって、そのファイル内で有効となるURLの範囲が決まる。[1] プロトコルのパスプレフィックス規則によれば、`http://example.com/catalog/sitemap.xml`に配置されたサイトマップは`http://example.com/catalog/`で始まるURLを記載できる一方、`http://example.com/images/`のような並列ディレクトリ配下のURLや、`https://example.com/catalog/page1.php`のような異なるスキームのURLは無効として破棄される。[1] サイトマップ内のすべてのURLは、サイトマップファイルと同一のプロトコル、ホスト、およびポート番号を共有しなければならず、`http://www.example.com/sitemap.xml`に`http://subdomain.example.com`のURLを含めることはできず、`http://www.example.com:100/sitemap.xml`では記載するすべてのURLにそのポート番号が必要となる。[1][2]

パス範囲制限はサイトマップ配置ディレクトリ配下の子孫に適用されるため、sitemaps.orgおよびGoogleは1か所の配置でサイト全体を網羅できるよう、ウェブサーバーのルートディレクトリ（`http://example.com/sitemap.xml`）にサイトマップを配置することを推奨している。[1][2][6] 組織のセキュリティポリシーによってディレクトリ単位の書き込み権限が分離されている場合には、ディレクトリごとに個別のサイトマップを配置することも引き続き認められている。[1][2] Google検索では、Google Search Console経由でサイトマップを直接送信すると親ディレクトリ制限が解除される。[6]

サイトマップインデックスファイルにも同様のホストおよび階層規則が適用され、参照するサイトマップはサイトマップインデックスファイルと同一ホスト上かつ同一ディレクトリまたはそれより深いサブディレクトリに存在しなければならない。[1][7] 単一のホストから複数の異なるホスト向けのサイトマップを提供するクロスホスト送信を行うには、各対象ホストの所有権を証明する必要がある。[1][7]

サイトマップ公開後に検索エンジンへ通知する方法として、sitemaps.org FAQは検索エンジンツールを通じた直接送信、検索エンジンへのping送信、および[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)でのサイトマップ場所の宣言という3つの手法を挙げている。[2] Internet Engineering Task Force（IETF）が2022年9月にRFC 9309として発行したRobots Exclusion Protocol仕様では、セクション2.2（Formal Syntax）において`robots.txt`パーサー実装者がSitemapsなどの追加行を定義できると記されている。[4] ping通知に関しては、2023年6月にGoogle 検索セントラル ブログがGoogleのサイトマップpingエンドポイントを廃止する旨の発表を公開した。[10]

## 画像、ニュース、およびその他コンテンツ向けのサイトマップ拡張

サイトマップXMLファイルは、追加のXML名前空間を用いることで特定コンテンツ種別向けのプロトコル拡張に対応している。[1][6] Google 検索セントラルは画像、ニュース記事、動画、および[ローカライズされたページバージョン](https://mimirwiki.com/ja/wiki/hreflang)の拡張仕様を文書化しており、これらは専用のサイトマップに分けることも、既存のXMLサイトマップ内に統合することもできる。[5][6][8][9]

| 拡張 | XML名前空間 | 必須要素 | 文書化された上限 |
| --- | --- | --- | --- |
| コア Sitemaps 0.9 | `http://www.sitemaps.org/schemas/sitemap/0.9` | `urlset`、`url`、`loc`（または`sitemapindex`、`sitemap`、`loc`） | 50,000 URLまたはサイトマップ、非圧縮50 MB[1][7] |
| Google 画像サイトマップ | `http://www.google.com/schemas/sitemap-image/1.1` | `image:image`、`image:loc` | 1つの`url`あたり最大1,000個の`image:image`タグ[8] |
| Google ニュースサイトマップ | `http://www.google.com/schemas/sitemap-news/0.9` | `news:news`、`news:publication`、`news:name`、`news:language`、`news:publication_date` | 1つの`url`あたり`news:news` 1個、1サイトマップあたり最大1,000個の`news:news`タグ、過去2日以内の記事[9] |

Googleの画像サイトマップ拡張は、JavaScript経由で読み込まれる画像など、通常は見落とされ得る画像をGooglebotが発見するのを助ける。[8] 2025-12-10時点で、各`url`要素には最大1,000個の`image:image`子要素を含めることができ、各子要素内には必須の`image:loc` URLを記述する。[8] 画像URLは[コンテンツデリバリネットワーク](https://mimirwiki.com/ja/wiki/content-delivery-network)などの別ドメインでホストすることもできるが、双方のドメインがGoogle Search Consoleで確認済みであり、かつ`robots.txt`でクロールが許可されている必要がある。[8] Googleは2022年5月のGoogle 検索セントラル ブログにおける一部サイトマップ拡張タグの削除発表に続き、画像サイトマップのドキュメントから従来記載されていた4つの画像タグ（`image:caption`、`image:geo_location`、`image:title`、および`image:license`）を削除した。[8][10]

Googleのニュースサイトマップ拡張は、ニュースパブリッシャーが記事メタデータを伝達するために利用するものであり、一般的なサイトマップを拡張することも、Search Consoleでの個別追跡のために専用のニュースサイトマップを運用することもできる。[9] パブリッシャーは新しい記事が公開されるたびに既存のニュースサイトマップを更新し、Google ニュースはサイトの他部分と同じ頻度でニュースサイトマップをクロールする。[9] エントリは過去2日以内に公開された記事に限定する必要があり、それより古いURLまたはその`news:news`ブロックは削除する。ニュースサイトマップが一時的に空になった場合、Search Consoleは確認用の「空のサイトマップ（Empty Sitemap）」警告を表示するが、Google検索自体には影響しない。[9] 各`url`には1つの`news:news`タグを指定でき、単一のサイトマップには最大1,000個の`news:news`タグを含められる。[9] `news:publication`内の`news:name`は`news.google.com`上のパブリケーション名から括弧書きを除いた表記と一致させる必要があり、`news:language`には2文字または3文字のISO 639コード（簡体字中国語は`zh-cn`、繁体字中国語は`zh-tw`）を使用する。[9] `news:publication_date`タグには、サイト上での元の公開日時をW3C Datetime形式（`YYYY-MM-DD`、`YYYY-MM-DDThh:mmTZD`、または`YYYY-MM-DDThh:mm:ssTZD`）で記録する。[9]

Google 検索セントラルはまた、サイトマップの動画エントリで動画の再生時間、評価、年齢制限レーティングを指定できること、ならびにRSS、mRSS、およびAtom 1.0フィードがHTMLやインデックス可能なテキストコンテンツと併せて動画メタデータを提供できることも説明している。[5][6]

## 検索エンジンによるサイトマップのメタデータ処理と制限

検索エンジンはサイトマップの任意メタデータタグをそれぞれ異なる方法で扱っており、サイトマッププロトコルはクローラーに対して記載URLの読み取りやインデックス登録の義務を課していない。[1][3] プロトコル 0.9では`urlset`、`url`、`loc`が必須である一方、sitemaps.orgは任意要素（`lastmod`、`changefreq`、`priority`）への対応状況が検索エンジンごとに異なることを明記し、パブリッシャーに各提供元のドキュメントを参照するよう案内している。[1][2]

プロトコル仕様上、`changefreq`はクロールに関する一般的なヒントとして定義されている。[1] クローラーは`hourly`と指定されたページを1時間に1回未満の頻度で巡回したり、`yearly`と指定されたページを年に1回以上の頻度で巡回したりすることがあり、`never`と指定されたURLであっても予期しない変更を確認するために定期的に巡回する場合がある。[1] 同様に、`priority`は単一サイト内におけるURL間の相対的な重要度を`0.0`から`1.0`（既定値`0.5`）で表現するものであり、異なるドメイン間のページを比較するものではない。すべてのURLに高い値を設定しても相対的な差別化にはならず、仕様およびFAQでは`priority`が検索結果の順位に影響することは想定されていないと明記されている。[1][2]

`lastmod`について、プロトコルはこのタグがサーバーのHTTP `If-Modified-Since`（304）ヘッダーとは独立したものであること、また検索エンジンが両シグナルを異なる方法で組み合わせたり評価したりする可能性があることを記している。[1] sitemaps.org FAQでは、静的ファイルの正確な更新タイムスタンプや動的ページのデータに基づく推定値を指定することで、クローラーが未変更URLをスキップしやすくなり、サーバーの帯域幅とCPU負荷を軽減できると説明している。[2] サイトマップインデックスファイルに関しては、2025-12-10に更新されたGoogle 検索セントラルのドキュメントが、`lastmod`はGoogleがサイトマップのクロールスケジュールを組む際に役立つ場合があると述べている。[7]

形式面において、GoogleはXMLサイトマップ、RSS/mRSS/Atom 1.0フィード、およびプレーンテキストサイトマップの間で優先順位を設けていないと表明している。[6] GoogleはサイトマップをURL発見の補助手段かつ正規URL選択に影響し得るシグナルとして扱う一方、サイトマップにURLを記載してもクロールやインデックス登録は保証されないと明示している。[5][6] サイトマップはRFC 9309に基づきクローラーのアクセス許可を伝える[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)と併用して機能し、サイトマップに記載されたコンテンツへアクセスするには`robots.txt`によってクローラーのアクセスが許可されている必要がある。[4][8] Sitemaps.orgの利用規約の下で、Google、Yahoo、およびMicrosoftはそれぞれ任意のサービスにおいてプロトコルを部分的に利用する権利、または対応を終了する権利を留保している。[3]

## よくある質問

### サイトマップとは何ですか？

サイトマップは、ウェブサイト上のクロール可能なページ、動画、画像などのファイル一覧と、最終更新日や代替言語バージョンといったメタデータを記載した機械可読ファイルです。検索エンジンはサイトマップを読み取ることで、URLをより効率的に発見しクロールできます。 [1][5]

### サイトマップのURL数とファイルサイズの上限はいくつですか？

2026-11-23時点で、XMLまたはテキスト形式のサイトマップファイル1件あたり最大50,000件のURLを含めることができ、非圧縮時のサイズは50 MB（52,428,800バイト）以下である必要があります。サイトマップインデックスファイルも同じ非圧縮50 MBの上限内で最大50,000件のサイトマップを参照でき、ファイルはgzipで圧縮できます。 [1][2][6][7]

### サイトマップおよびサイトマップインデックスファイルで必須のXML要素は何ですか？

標準のXMLサイトマップでは、0.9名前空間を宣言するルート要素urlset、各エントリの親要素url、および完全修飾URLを格納する子要素locが必須です。サイトマップインデックスファイルではsitemapindex、sitemap、locの各要素が必須であり、任意の子タグとしてlastmodを使用できます。 [1][7]

### priorityタグは検索結果の順位に影響しますか？

サイトマッププロトコルおよびFAQによると、priorityは同一サイト内の他のURLと比較した相対的な重要度を0.0から1.0（既定値0.5）の範囲で示す値です。異なるサイト間でページを比較するものではなく、検索結果の順位に影響を与えることは想定されていません。 [1][2]

### 検索エンジンはどのようにしてサイトマップファイルを発見しますか？

sitemaps.org FAQでは、検索エンジンへの直接送信、検索エンジンへのping送信、およびrobots.txtへのサイトマップ場所の記載の3つの方法が説明されており、RFC 9309でもrobots.txtパーサーがSitemaps行に対応できる旨が記載されています。2023年6月にGoogle 検索セントラル ブログはGoogleのサイトマップpingエンドポイントの廃止を発表しましたが、Google Search Consoleは引き続き直接送信の手段として利用できます。 [2][4][6][10]

### すべてのウェブサイトにサイトマップが必要ですか？

2025-12-10に更新されたGoogle 検索セントラルのドキュメントによると、サイトマップは大規模サイト、外部リンクが少ない新規サイト、および動画・画像・ニュースコンテンツが豊富なサイトで特に有用です。一方、およそ500ページ以下で内部リンクが網羅的に張られており、メディアやニュースページが多くない小規模サイトでは、サイトマップが不要な場合があります。 [5]

## 引用できる文

- Sitemaps.orgはGoogle, Inc.、Yahoo, Inc.、およびMicrosoft Corporationによって後援されており、そのプロトコル仕様はクリエイティブ・コモンズ 表示-継承 2.5 ライセンス（Creative Commons Attribution-ShareAlike License version 2.5）の下で提供されている。 [3]
- 2026-11-23時点で、サイトマッププロトコル 0.9はUTF-8エンコーディング、XML名前空間 http://www.sitemaps.org/schemas/sitemap/0.9、および2,048文字未満のloc値を持つurlset、url、locの各要素を必須としている。 [1]
- 2026-11-23時点で、単一のサイトマップファイルに含められるURLは最大50,000件かつ非圧縮サイズ50 MB（52,428,800バイト）以下であり、サイトマップインデックスファイルも同様に非圧縮50 MBの上限内で最大50,000件のサイトマップを記載できる。 [1][2]
- サイトマッププロトコル 0.9は検証用XMLスキーマとしてsitemap.xsdおよびsiteindex.xsdを提供し、代替形式としてRSS 2.0、Atom 0.3または1.0、およびUTF-8プレーンテキストファイルに対応している。 [1][2]
- 2022年9月にIETFが発行したRFC 9309は、robots.txtのABNF形式構文において、パーサー実装者がSitemapsなどの追加行を定義できることを明記している。 [4]
- 2025-12-10時点で、Google Search Consoleは1サイトあたり最大500件のサイトマップインデックスファイルを許可しており、Search Console経由でサイトマップを送信すると既定の親ディレクトリ範囲制限が解除される。 [6][7]
- 2025-12-10時点で、Googleの画像サイトマップ拡張（http://www.google.com/schemas/sitemap-image/1.1）はurl要素ごとに最大1,000個のimage:imageタグを許可しており、Googleはドキュメントからimage:caption、image:geo_location、image:title、image:licenseを削除した。 [8]
- Googleのニュースサイトマップ拡張（http://www.google.com/schemas/sitemap-news/0.9）はサイトマップ1件あたり最大1,000個のnews:newsエントリを許可しており、対象を過去2日以内に公開された記事に制限している。 [9]

## 年表

- 2008-02-27: Sitemaps.orgが利用規約を更新し、Google, Inc.、Yahoo, Inc.、およびMicrosoft Corporationを後援企業として明記するとともに、仕様に対するCreative Commons Attribution-ShareAlike 2.5ライセンスを定めた。 [3]
- 2016-11-21: Sitemaps.orgがFAQを更新し、50 MB（52,428,800バイト）および50,000 URLの上限と、sitemap.xsdおよびsiteindex.xsdのXMLスキーマを文書化した。 [2]
- 2022-05: Google 検索セントラル ブログが一部のサイトマップ拡張タグの削除を発表する通知を公開した。 [8][10]
- 2022-09: IETFがRFC 9309（Robots Exclusion Protocol）を発行し、ABNF形式構文においてrobots.txtパーサーがSitemapsなどの追加行を定義できることを記した。 [4]
- 2023-06: Google 検索セントラル ブログがGoogleのサイトマップpingエンドポイントを廃止する旨の発表を公開した。 [10]
- 2025-12-10: Google 検索セントラルがサイトマップの概要、サイトマップインデックスファイル、および画像サイトマップのドキュメントを更新した。 [5][7][8]

## 出典

1. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (閲覧 2026-11-23; tier 3: official site)
2. sitemaps.org - FAQ. sitemaps.org. 公開 2016-11-21. https://www.sitemaps.org/faq.html (閲覧 2026-11-23; tier 3: official site)
3. sitemaps.org - Terms of service. sitemaps.org. 公開 2008-02-27. https://www.sitemaps.org/terms.html (閲覧 2026-11-23; tier 3: official site)
4. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (閲覧 2026-11-23; tier 1: government or public registry)
5. What Is a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. 公開 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview (閲覧 2026-11-23; tier 3: official site)
6. Build and Submit a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (閲覧 2026-11-23; tier 3: official site)
7. Manage Your Sitemaps With Sitemap Index Files | Google Search Central | Documentation | Google for Developers. Google Search Central. 公開 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/large-sitemaps (閲覧 2026-11-23; tier 3: official site)
8. Image Sitemaps | Google Search Central | Documentation | Google for Developers. Google Search Central. 公開 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps (閲覧 2026-11-23; tier 3: official site)
9. Create a News Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap (閲覧 2026-11-23; tier 3: official site)
10. Sitemaps ping endpoint is going away | Google Search Central Blog | Google for Developers. Google Search Central Blog. 公開 2023-06. https://developers.google.com/search/blog/2023/06/sitemaps-lastmod-ping (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "サイトマップ." 版 e676d279, 2026-11-23. https://mimirwiki.com/ja/wiki/sitemaps
