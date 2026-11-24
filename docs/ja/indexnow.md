---
title: "IndexNow"
subtitle: "ウェブサイトがURLの追加、更新、削除を検索エンジンに通知するためのオープンなHTTPプロトコル"
canonical_url: https://mimirwiki.com/ja/wiki/indexnow
language: ja
page_class: anchor
revision_sha256: 47ec84ecf3b3c8e01088254277a6b20990f3482af8fb94808aa10e527bd74b18
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/indexnow.md
  txt: https://mimirwiki.com/ja/wiki/indexnow.txt
  json: https://mimirwiki.com/ja/wiki/indexnow.json
  jsonld: https://mimirwiki.com/ja/wiki/indexnow.jsonld
translations:
  en: https://mimirwiki.com/wiki/indexnow
  ko: https://mimirwiki.com/ko/wiki/indexnow
  zh: https://mimirwiki.com/zh/wiki/indexnow
---

# IndexNow

> IndexNowは、Microsoft BingとYandexが2021年10月に公開した、追加・更新・削除されたURLを検索エンジンへ通知するためのオープンなHTTPプロトコルである。サイトはホスト上のテキストキーファイルで所有権を検証し、2026-11-23時点でGETリクエストにより1件、POSTリクエストにより最大10,000件のURLを送信できる。各参加エンドポイントは受信した送信内容を他のすべての参加検索エンジンと共有する。

IndexNowは、ホスト上のURLが追加、更新、または削除された際に、ウェブサイト運営者が参加検索エンジンへ通知できるオープンなHTTP通知プロトコルである。Microsoft BingとYandexが2021年10月18日にこのプロトコルを発表し、IndexNow.orgで公開されている仕様は、スポンサーであるMicrosoft Corporation、Yandex N.V.、およびSeznam.cz, a.s.によってクリエイティブ・コモンズ 表示-継承 4.0（CC BY-SA 4.0）ライセンスの下で提供されている。サイトはホスト上に配置したUTF-8テキストキーファイルでドメイン所有権を検証し、単一URLのHTTP GETリクエストまたは最大10,000件のURLを含むJSON POSTバッチをいずれかの参加エンドポイントへ送信すると、送信されたURLは他のすべての参加検索エンジンと自動的に共有される。2026-11-23時点で、indexnow.org/searchengines.jsonの公式レジストリにはBing、Yandex、Seznam、Naver、Yep、Internet Archive、およびAmazonbotの7つの参加エンドポイントが登録されている。

**別名:** IndexNowプロトコル, IndexNow API, IndexNow.org

## 主要な事実

- **公開日:** 2021-10-18 [6]
- **開発元:** Microsoft Bing、Yandex [6]
- **仕様ライセンス:** クリエイティブ・コモンズ 表示-継承 4.0（CC BY-SA 4.0） (時点 2026-11-23) [5]
- **一括送信上限:** HTTP POSTリクエスト1回あたり最大10,000件のURL (時点 2026-11-23) [2]
- **登録エンドポイント:** searchengines.jsonに7件（Bing、Yandex、Seznam、Naver、Yep、Internet Archive、Amazonbot） (時点 2026-11-23) [4]

## ファクトシート

- **種別:** オープンなHTTP URL通知プロトコル [1]
- **公開日:** 2021-10-18 [6]
- **開発元:** Microsoft Bing、Yandex [6]
- **仕様スポンサー:** Microsoft Corporation、Yandex N.V.、Seznam.cz, a.s. (時点 2026-11-23) [5]
- **ライセンス:** クリエイティブ・コモンズ 表示-継承 4.0（CC BY-SA 4.0） (時点 2026-11-23) [5]
- **送信方式:** HTTP GET（1 URL）およびHTTP POST JSON（最大10,000 URL） (時点 2026-11-23) [2]
- **グローバルエンドポイント:** https://api.indexnow.org/indexnow (時点 2026-11-23) [3]
- **所有権検証方式:** サイト上にホストするUTF-8テキストキーファイル（8〜128文字） (時点 2026-11-23) [2]
- **URIエンコード標準:** RFC 3986 [2]
- **登録検索エンジン:** searchengines.jsonに7件登録（Bing、Yandex、Seznam、Naver、Yep、Internet Archive、Amazonbot） (時点 2026-11-23) [4]
- **利用料金:** 無料 (時点 2026-11-23) [8]

## IndexNowの概要と設立の経緯

IndexNowは、サイト上のURLが追加、更新、または削除されたことをウェブサイト運営者が参加検索エンジンやウェブクローラーに通知できる無料のオープンなHTTPプロトコルである。[1][8] プッシュ通知がない場合、検索エンジンは定期的なクロールによってウェブサイトの変更を検出する必要があるが、クローラーがすべてのURLを頻繁に再訪問するわけではないため、変更の検出に数日から数週間を要する場合がある。[1][6] コンテンツ変更時に通知を送信することで、検索エンジンは対象URLのクロールを優先し、変更のないページに対する探索的なクロールを抑えることができ、サーバー負荷の軽減につながる。[1][6][8]

Microsoft BingとYandexは、2021年10月18日にIndexNowを発表した。[6] 2026-11-23に確認したIndexNow.orgの利用規約によれば、IndexNow.orgのスポンサーはMicrosoft Corporation、Yandex N.V.、およびSeznam.cz, a.s.である。[5] スポンサー各社は、IndexNow.orgで公開されているプロトコル仕様の著作権をクリエイティブ・コモンズ 表示-継承 4.0（CC BY-SA 4.0）ライセンスの下で許諾しており、その他の知的財産権は付与しないものとしている。また、利用規約はカリフォルニア州法に準拠する。[1][5]

IndexNowの中核となる要件は、検索エンジン間の相互共有である。プロトコルを採用する検索エンジンは、いずれか1つの参加エンドポイントに送信されたすべてのURLを他のすべての参加検索エンジンと自動的に共有することに同意している。[2][3][6] そのため、ウェブサイト運営者は各URLの通知を1つの参加エンドポイントに送信するだけで済む。[3]

## IndexNowの送信方式とHTTPステータスコード

IndexNowは、追加、更新、または削除されたURLを検索エンジンに通知するために、単一URL用のHTTP GETリクエストと複数URL用のHTTP POST JSONリクエストという2種類のHTTP送信方式をサポートしている。[2] いずれの方式も、HTTPクライアント、ブラウザ、スクリプト、あるいは`curl`や`wget`といったコマンドラインユーティリティから実行できる。[2][3]

HTTP GETで1件のURLを送信する場合、サイトは`https://<searchengine>/indexnow?url={url-changed}&key={your-key}`宛てにリクエストを送信し、キーファイルがサイトルート以外に配置されている場合はオプションの`keyLocation`パラメータを付与する。[2][3] 送信するURLはRFC 3986に従ってURLエスケープおよびエンコードする必要があり、たとえば`:`は`%3A`、`/`は`%2F`、`?`は`%3F`、`=`は`%3D`、`&`は`%26`にエンコードする。[2][3]

1回のリクエストで複数のURLを送信する場合、サイトは`Content-Type: application/json; charset=utf-8`ヘッダーを付与して`/indexnow`へ`HTTP POST`リクエストを送信し、`host`、`key`、オプションの`keyLocation`、および`urlList`を含むJSONボディを渡す。[2][3] 2026-11-23時点で、1回のPOSTリクエストでは最大10,000件のURLを受け付け、同一ホストの`http`と`https`のURLを混在させることもできる。[2][3] 1回のペイロードで10,000件を超過すると、リクエストが失敗したりHTTP 422が返されたりする場合がある。[3] また、リダイレクトされたURL（HTTP 301、HTTP 302、またはmeta refresh）や、HTTP 404またはHTTP 410を返す削除済みURLを送信して、検索エンジンに古いエントリの更新や削除を促すことも可能である。[3]

2026-11-23時点で、IndexNow.orgは送信リクエストに対して6種類のHTTP応答コードを規定している。[2][3][7]

| HTTPコード | ステータス | 仕様上の意味 |
| --- | --- | --- |
| 200 | OK | URLまたはURLバッチの送信に成功（受信確認のみを意味する） |
| 202 | Accepted | URLを受信済み、キー所有権の検証が保留中（初回リクエスト時によく発生） |
| 400 | Bad Request | リクエスト形式が無効 |
| 403 | Forbidden | キーが無効（例：キーファイルが存在しない、またはファイル内にキーが含まれていない） |
| 422 | Unprocessable Entity | URLがホストに属していない、キーがスキーマ規則を満たしていない、またはペイロードが上限を超過 |
| 429 | Too Many Requests | リクエスト頻度が過剰またはスパムの疑いありと判定された状態 |

## IndexNowのAPIキー規則とドメイン所有権検証

IndexNowでは、URLを手動送信するウェブサイト運営者に対し、対象ホスト上にUTF-8エンコードのテキストキーファイルをホストすることで所有権を証明することを求めている。[2][3] 2026-11-23時点で、キーは8文字以上128文字以下で、ASCII英小文字（`a-z`）、ASCII英大文字（`A-Z`）、数字（`0-9`）、およびハイフン（`-`）のみを使用できる。[2][3] IndexNowのドキュメントではこれらを16進数文字と呼称しつつ、`a-z`、`A-Z`、`0-9`、および`-`を明示的に許可している。[2] キーはGUIDまたはUUIDジェネレーター、コマンドラインツール、あるいはBing Webmaster Tools内のツールなどのオンラインジェネレーターで生成できる。[3][6][7]

IndexNowは、所有権検証用のキーファイルをホストする方法を2種類定義している。[2]

- Option 1（ルートディレクトリ）：ホストのルートディレクトリに、キー文字列のみを記載した`{your-key}.txt`という名前のUTF-8ファイル（例：`https://www.example.com/{your-key}.txt`）をホストする。[2][3] 仕様ではOption 1が推奨設定とされており、ホスト全体のURLをカバーする。[2][3]
- Option 2（サブパスディレクトリ）：同一ホスト上でログイン不要かつ公開アクセス可能なフォルダに1つ以上のUTF-8テキストキーファイルをホストし、すべての送信においてGETの`keyLocation`クエリパラメータまたはPOSTのJSONフィールドでキーファイルのURLを指定する。[2][3] Option 2ではキーファイルが置かれたディレクトリによって有効なURLの範囲が限定される。たとえば、`http://example.com/catalog/key12457EDd.txt`に配置されたキーファイルは`http://example.com/catalog/`で始まるURLを対象とするが、`http://example.com/help/`や`http://example.com/image/`配下のURLには無効である。[2]

サイトがURLを送信すると、参加検索エンジンはキーファイルをクロールしてホストの所有権を検証し、運営者が変更するまでそのキーを継続して認識する。[2] サービスを中断せずにAPIキーをローテーションするには、既存のキーファイルを新しい`{key}.txt`ファイルに置き換え、新しいキーでURL送信を開始するだけで自動的に再検証が行われる。[3] IndexNowの送信をネイティブに管理するコンテンツ管理システム（CMS）、ホスティングプロバイダー、またはCDNを利用しているウェブサイトは、キーファイルを手動で作成する必要がない。[3]

## IndexNowの参加検索エンジンとエンドポイント

IndexNowは、参加検索エンジンおよびクローラーの機械可読なJSONレジストリを`https://www.indexnow.org/searchengines.json`で公開している。[4] 2026-11-23時点で、`searchengines.json`には7つの参加者が登録されており、それぞれが`meta.json`エンドポイントに対応付けられている。[4] 同日時点で、IndexNow.orgのホームページでは5つの対応検索エンジン（Microsoft Bing、Naver、Seznam.cz、Yandex、およびYep）が挙げられている一方、IndexNow FAQではグローバルエンドポイント`https://api.indexnow.org/indexnow`に加えて6つの個別サービスの送信エンドポイントが掲載されている。[1][3]

| レジストリキー（`searchengines.json`） | メタデータURL（`searchengines.json`） | 送信エンドポイント（`indexnow.org/faq`） |
| --- | --- | --- |
| `bing` | `https://www.bing.com/indexnow/meta.json` | `https://www.bing.com/indexnow` |
| `yandex` | `https://www.yandex.com/indexnow/meta.json` | `https://yandex.com/indexnow` |
| `seznam` | `https://search.seznam.cz/indexnow/meta.json` | `https://search.seznam.cz/indexnow` |
| `naver` | `https://searchadvisor.naver.com/indexnow/meta.json` | `https://searchadvisor.naver.com/indexnow` |
| `yep` | `https://indexnow.yep.com/indexnow/meta.json` | `https://indexnow.yep.com/indexnow` |
| `internetarchive` | `https://web-static.archive.org/indexnow/meta.json` | FAQのエンドポイント一覧には未記載 |
| `amazonbot` | `https://indexnow.amazonbot.amazon/indexnow/meta.json` | `https://indexnow.amazonbot.amazon/indexnow` |

2025年5月19日、Microsoft AI BingのプリンシパルプロダクトマネージャーであるFabrice CanelとKrishna MadhavanはBing Webmaster Blog上で、Amazonがウェブコンテンツの変更検出と不要なクロールの削減を目的として2025年6月中旬にIndexNowの導入を開始する予定であると発表した。[9] 2026-11-23時点で、Amazonの`amazonbot`エンドポイントは`searchengines.json`とIndexNow FAQの双方に掲載されている。[3][4]

IndexNow.orgで公開されている要件によれば、IndexNowに参加する検索エンジンは、送信されたURLを他のすべての参加検索エンジンと自動的に共有すること、少なくとも1つの市場で顕著な存在感を持つか検索市場と密接に関連していること、およびURL送信に大きく貢献することが求められる。[2]

## IndexNowのCMS、プラグイン、およびCloudflare Crawler Hintsとの統合

IndexNowは、ウェブサイトがURL変更通知を自動発行できるよう、コンテンツ管理システム（CMS）、サードパーティ製SEOプラグイン、および[コンテンツデリバリーネットワーク](https://mimirwiki.com/ja/wiki/content-delivery-network)（CDN）に統合されている。[3][7]

2021年11月30日、[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)はMicrosoft BingおよびYandexと提携してCloudflare Crawler HintsにIndexNowサポートを追加し、Crawler HintsをすべてのCloudflare顧客向けに無料で一般提供した。[10] Cloudflareの顧客は、CloudflareダッシュボードのCacheタブ内にあるConfigurationセクションの単一設定からこの連携を有効化でき、有効化後はサイトコンテンツの変更時にCloudflareがIndexNowシグナルを自動送信する。[10] 2021年11月30日の発表でCloudflareは、インターネットトラフィックの約45%がウェブクローラーとボットによるものであり、主要検索クローラーのトラフィックを対象とした1年間の調査では、クローラー訪問の53%が前回訪問時から変更のないページへのリクエストであったと報告した。[10] 同日までに60,000以上のユニークなCloudflareウェブサイトがCrawler Hintsを有効化し、Bingに対して約10億件の変更ヒントを送信していた。[10] 2026-11-23時点で、IndexNow.orgとBing Webmaster ToolsはともにCloudflare Crawler HintsをネイティブCDN統合として掲載しており、2021年10月の発表記事でもAkamaiがIndexNowの統合を計画していると言及されていた。[3][6][7]

2026-11-23時点で、IndexNow.orgとBing Webmaster Toolsは、ネイティブ統合またはプラグイン・拡張機能を通じてIndexNowをサポートする16のCMSプラットフォームとして、WordPress、Shopify、Wix、GoDaddy、Duda、XenForo、Milestone、Joomla!、Drupal、Bitrix24、PrestaShop、MODX、Shopware、OpenCart、Typo3、およびUmbracoを挙げている。[3][7] Bing Webmaster Toolsでは具体的なサードパーティプラグインとして、WordPress向けのIndexNow plugin、Yoast、RankMath、AIOSEO、SEOPress、Shopify向けのInstaIndex、Joomla!向けのAimy Sitemap PROとJSitemap、およびBitrix24向けのReIndexとTurboIndexが掲載されている。[7]

2021年10月の公開時、Microsoft BingはWordPressをはじめとするCMSプラットフォームによるIndexNow導入を支援するためのオープンソースコードを公開し、Wix、Duda、Botify、Oncrawl、Onely、およびYextによる統合計画を報告するとともに、Bing Webmaster URL送信APIを利用していたeBay、LinkedIn、MSN、GitHub、Bizapediaなどの大規模ウェブサイトがIndexNowへの移行を計画していると述べた。[6] 2025年5月19日には、Microsoft BingはShopifyおよびデジタルマーケティング・CMSプロバイダーのMilestone Inc.がIndexNowを統合したと報告した。[9] ウェブサイト運営者は、Bing Webmaster Toolsポータルから送信済みURLの受信状況を確認できる。[7]

## IndexNowプロトコルの制限、不参加エンジン、およびサイトマップとの関係

IndexNowは任意のURL通知シグナルとして機能し、その実用上の適用範囲は検索エンジンの参加状況、クロール割り当て、送信上限、およびスポンサー規約によって制約を受ける。[2][3][4][5][7]

IndexNowの参加範囲は、プロトコルに登録されているサービスに限定される。2026-11-23時点で、`indexnow.org/searchengines.json`にはBing、Yandex、Seznam、Naver、Yep、Internet Archive、およびAmazonbotの7つの参加エンドポイントが登録されている。[4] URLの自動共有は参加検索エンジン間でのみ行われるため、このレジストリに含まれていない検索エンジンはプロトコル経由でIndexNow通知を受け取らない。[2][4] IndexNow.orgの利用規約の下では、各スポンサーは予告なく仕様を変更する権利、および任意の製品やサービスでいつでもIndexNowの使用を開始・中止する権利を留保しており、送信されたURLを読み取ったりインデックス登録したりする義務を負わない。[5]

IndexNowエンドポイントからHTTP `200` 応答を受け取った場合でも、エンドポイントが送信されたURLまたはURLリストを受信したことのみが確認される。[2] IndexNow FAQとBing Webmaster Toolsの双方は、URLの送信がクロールやインデックス登録を保証するものではないと明記している。[3][7] 検索エンジンは独自のクロール割り当て、スケジューリングロジック、および品質シグナルを用いて送信された各URLを評価し、IndexNow経由で実行されたすべてのクロールはウェブサイトのクロール割り当てに計上される。[3][7]

IndexNowはバッチサイズおよびレート制限も課している。2026-11-23時点で、1回のPOSTリクエストは10,000 URLを上限とし、過剰または反復的な送信はHTTP `429` によるレート制限の対象となる場合がある。[2][3] IndexNow FAQでは、意味のあるコンテンツ変更のみを送信すること、同一URLを再送信する前に最低5分待機すること、およびレビュー、コメント、フォーラム投稿などのユーザー生成コンテンツは段階的に送信すること（例：1件から20件までは各レビューごと、100件までは5件ごと、1,000件までは10件ごと）を推奨している。[3]

IndexNowは[XMLサイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)を補完するよう設計されており、サイトがプロトコルを有効化した後に追加、更新、または削除されたURLを対象としている。[3][7] IndexNow FAQでは、過去の変更を遡及的に送信することや、サイト移行や全面刷新などの大規模な変更時以外にサイト全体を一括送信することを避け、完全なURL一覧の提供と更新頻度の低いページの発見を支援するために、正確な`lastmod`タイムスタンプを備えたXMLサイトマップを引き続き維持すべきであるとしている。[3]

## よくある質問

### IndexNowとは何ですか？

IndexNowは、Microsoft BingとYandexが2021年10月18日に公開した無料のオープンなHTTPプロトコルであり、ウェブサイト運営者がURLの追加、更新、または削除を参加検索エンジンに通知できる仕組みです。参加エンドポイントの1つにURLを送信すると、その通知は他のすべての参加検索エンジンと自動的に共有されます。 [1][2][6][8]

### どの検索エンジンがIndexNowに参加していますか？

2026-11-23時点で、indexnow.org/searchengines.jsonの公式レジストリにはBing、Yandex、Seznam、Naver、Yep、Internet Archive、およびAmazonbotの7つの参加エンドポイントが登録されています。このレジストリに含まれていない検索エンジンは、IndexNowを通じたURL通知を受け取りません。 [2][4]

### 1回のIndexNowリクエストで何件のURLを送信できますか？

2026-11-23時点で、IndexNowはHTTP GETリクエスト1回につき1件のURL、UTF-8 JSON形式のHTTP POSTリクエスト1回につき最大10,000件のURLの送信に対応しています。1回のPOSTペイロードで10,000件を超えるURLを送信すると、リクエストが失敗したりHTTP 422（Unprocessable Entity）が返されたりする場合があります。 [2][3]

### IndexNowはどのようにウェブサイトの所有権を検証しますか？

手動で設定する場合、サイト運営者は8文字から128文字（a-z、A-Z、0-9、およびハイフン）のAPIキーを作成し、サイトルートに{your-key}.txtという名前のUTF-8テキストファイルとしてホストします。あるいは、公開アクセス可能なサブフォルダにキーファイルを配置し、keyLocationパラメータでそのURLを指定することも可能ですが、その場合は当該ディレクトリ配下のURLのみが有効な送信対象となります。 [2][3]

### IndexNowからのHTTP 200応答はクロールやインデックス登録を保証しますか？

いいえ。HTTP 200応答は、検索エンジンが送信されたURLまたはURLバッチを受信したことのみを確認するものです。検索エンジンは引き続き独自のクロール割り当て、スケジューリングロジック、および品質シグナルを適用し、通知によって発生するクロールもサイトのクロール割り当てに計上されます。 [2][3][7]

### IndexNowはXMLサイトマップを置き換えるものですか？

いいえ。IndexNowの公式ドキュメントでは、ウェブサイトはIndexNowとXMLサイトマップを併用すべきであると明記されています。IndexNowは最近のURLの追加、更新、削除を検索エンジンに通知する一方、lastmod値を含むXMLサイトマップはサイト全体のURL一覧を提供し、古いページや更新頻度の低いページの発見を支援します。 [3]

## 引用できる文

- Microsoft BingとYandexは、2021年10月18日にIndexNowプロトコルを発表した。 [6]
- IndexNow.orgに掲載されているIndexNowプロトコル仕様は、スポンサーであるMicrosoft Corporation、Yandex N.V.、およびSeznam.cz, a.s.により、クリエイティブ・コモンズ 表示-継承 4.0ライセンスの下で提供されている。 [5]
- 2026-11-23時点で、IndexNowは1回のHTTP POST JSONリクエストで最大10,000件のURLを受け付ける。 [2][3]
- 2026-11-23時点で、IndexNow APIキーは英小文字、英大文字、数字、およびハイフンで構成される8文字以上128文字以下の文字列でなければならない。 [2][3]
- 2026-11-23時点で、indexnow.org/searchengines.jsonにはBing、Yandex、Seznam、Naver、Yep、Internet Archive、およびAmazonbotの7つの参加エンドポイントが登録されている。 [4]
- 2021年11月30日、CloudflareはCrawler HintsにおけるIndexNowサポートを発表し、Cloudflareの顧客向けにCrawler Hintsを無料で一般提供した。 [10]
- IndexNowエンドポイントからのHTTP 200応答は送信されたURLの受信確認のみを意味し、クロールやインデックス登録を保証するものではない。 [2][3][7]

## 年表

- 2021-10-18: Microsoft BingとYandexがIndexNow URL通知プロトコルを発表した。 [6]
- 2021-11-30: CloudflareがCrawler HintsにIndexNowサポートを追加し、すべてのCloudflare顧客向けにCrawler Hintsを無料で一般提供した。 [10]
- 2025-05-19: Microsoft BingがShopifyおよびMilestone Inc.によるIndexNow対応を報告し、Amazonが2025年6月中旬にIndexNowの導入を開始する予定であることを発表した。 [9]

## 出典

1. Home | IndexNow.org. IndexNow. https://www.indexnow.org/ (閲覧 2026-11-23; tier 3: official site)
2. Documentation | IndexNow.org. IndexNow. https://www.indexnow.org/documentation (閲覧 2026-11-23; tier 3: official site)
3. FAQ | IndexNow.org. IndexNow. https://www.indexnow.org/faq (閲覧 2026-11-23; tier 3: official site)
4. IndexNow Participating Search Engines JSON. IndexNow. https://www.indexnow.org/searchengines.json (閲覧 2026-11-23; tier 3: official site)
5. Terms | IndexNow.org. IndexNow. https://www.indexnow.org/terms (閲覧 2026-11-23; tier 3: official site)
6. IndexNow – Instantly Index your web content in Search Engines |.... Microsoft Bing Webmaster Blog. 公開 2021-10-18. https://blogs.bing.com/webmaster/2021/10/IndexNow-Instantly-Index-your-web-content-in-Search-Engines/ (閲覧 2026-11-23; tier 3: official site)
7. How to add IndexNow to your website | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow/getstarted (閲覧 2026-11-23; tier 3: official site)
8. Why IndexNow | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow (閲覧 2026-11-23; tier 3: official site)
9. IndexNow Drives Smarter and Faster Content Discovery | Bing.... Microsoft Bing Webmaster Blog. 公開 2025-05-19. https://blogs.bing.com/webmaster/2025/5/IndexNow-Drives-Smarter-and-Faster-Content-Discovery/ (閲覧 2026-11-23; tier 3: official site)
10. Cloudflare Supports IndexNow via one-click Integration | Bing.... Microsoft Bing Webmaster Blog. 公開 2021-11-30. https://blogs.bing.com/webmaster/2021/11/Cloudflare-Supports-IndexNow-via-one-click-Integration/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "IndexNow." 版 47ec84ec, 2026-11-23. https://mimirwiki.com/ja/wiki/indexnow
