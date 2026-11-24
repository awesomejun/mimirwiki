---
title: "robots.txt"
subtitle: "ロボット排除プロトコル（RFC 9309）に基づき、ウェブクローラーにアクセス可能なURIを伝えるプレーンテキストファイル"
canonical_url: https://mimirwiki.com/ja/wiki/robots-txt
language: ja
page_class: anchor
revision_sha256: db0a1741ebe469ae9638a758da678bfa14116fb50b1976cfb8517c2142caa63c
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/ja/wiki/robots-txt.md
  txt: https://mimirwiki.com/ja/wiki/robots-txt.txt
  json: https://mimirwiki.com/ja/wiki/robots-txt.json
  jsonld: https://mimirwiki.com/ja/wiki/robots-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/robots-txt
  ko: https://mimirwiki.com/ko/wiki/robots-txt
  zh: https://mimirwiki.com/zh/wiki/robots-txt
---

# robots.txt

> robots.txtは、ロボット排除プロトコル（RFC 9309）に基づきウェブサイトのルートパス（/robots.txt）に配置されるプレーンテキストファイルであり、自動化されたクローラーに対してアクセス可否の対象となるURIを伝える。Martijn Kosterが1994年に規約を初めて定義し、IETFが2022年9月に標準化した。ルールは勧告的なものであり、アクセス認可の機能は提供しない。

robots.txtは、ロボット排除プロトコル（Robots Exclusion Protocol, REP）に基づきウェブまたはFTPサービスの最上位パス/robots.txtで提供されるUTF-8のプレーンテキストファイルであり、クローラーと呼ばれる自動化クライアントがアクセスしてよいURIとアクセスしてはならないURIを指定する。Martijn Kosterが1994年6月にメーリングリストでの合意を受けてこの規約を初めて文書化し、Internet Engineering Task Force（IETF）が2022年9月に標準化過程のRFC 9309として発行した。ファイルはUser-agentグループとAllowおよびDisallowのパスルールで構成され、Sitemapなどの任意レコードも併記できる。RFC 9309はrobots.txtのルールをクローラーに遵守を求める勧告的な要請と定義しており、このプロトコルはアクセス認可や技術的な強制力を提供しない。

**別名:** /robots.txt, ロボット排除プロトコル, Robots Exclusion Protocol, REP, RFC 9309, ロボット排除標準

## 主要な事実

- **標準仕様:** RFC 9309（IETF標準化過程、2022年9月） [1]
- **原著者および合意日:** Martijn Koster（1994-06-30 メーリングリスト合意） [4]
- **標準配置場所:** サービスルートの/robots.txt（UTF-8、text/plain） [1]
- **中核ディレクティブ:** User-agent、Allow、Disallow（任意でSitemap） [1]
- **Googleファイルサイズ上限:** 500 KiB（上限を超える内容は無視） (時点 2026-11-23) [6]

## ファクトシート

- **プロトコル名:** ロボット排除プロトコル（Robots Exclusion Protocol, REP） [1]
- **IETF仕様:** RFC 9309（提案標準、2022年9月） [3]
- **RFC 9309著者:** Martijn Koster, Gary Illyes, Henner Zeller, Lizzi Sassman [3]
- **初回合意日:** 1994-06-30 [4]
- **ファイルパス:** /robots.txt（すべて小文字、最上位ディレクトリ） [1]
- **エンコーディングとメディアタイプ:** UTF-8、text/plain [1]
- **標準化ディレクティブ:** User-agent、Allow、Disallow [1]
- **特殊文字:** #（コメント）、*（ワイルドカード）、$（一致末尾） [1]
- **Googleファイルサイズ上限:** 500 KiB (時点 2026-11-23) [6]
- **Googleデフォルトキャッシュ期間:** 最大24時間 (時点 2026-11-23) [6]
- **参照C++パーサー:** github.com/google/robotstxt（Apache-2.0ライセンス） [8]
- **関連IETFワーキンググループ:** AI Preferences（aipref）、charter-ietf-aipref-01の下で活動中 (時点 2026-11-23) [2]

## robots.txtの概要と起源

robots.txtは、ロボット排除プロトコル（Robots Exclusion Protocol, REP）に基づきウェブサイトまたはFTPホストの最上位パスで提供されるプレーンテキストファイルであり、自動化されたクローラーがアクセス可能なURIを明示する。[1][5] サービス所有者は、インデックス登録のためにリンクを辿る検索エンジンクローラーなどの自動化クライアントが、サイトのリソースを要求する前に避けるべきパスを判断できるよう、このファイルを公開する。[1][7]

Martijn Kosterは、1994年6月30日に`robots`メーリングリスト（`robots-request@nexor.co.uk`）で到達し、Technical World Wide Webメーリングリスト（`www-talk@info.cern.ch`）で議論された合意を記録した文書「A Standard for Robot Exclusion」で、このプロトコルを最初に文書化した。[1][4] この文書は、1993年から1994年にかけてウェブロボット（ワンダラーやスパイダーとも呼ばれた）が短時間に大量のリクエストを送ってサーバーに過負荷をかけたり、同じファイルを繰り返し取得したり、深い仮想ツリーや一時的・重複コンテンツ、投票のように副作用を伴うCGIスクリプトを巡回したりした事例に対処したものである。[4] `/robots.txt`という単一ファイルが選ばれた理由は、既存のあらゆるウェブサーバーが追加設定なしで提供でき、クローラーが1回のリクエストで方針を取得でき、さらにファイル名が各オペレーティングシステムの命名規則に適合して衝突のリスクが最小限だったためである。[4]

25年間にわたり、REPは標準化団体の正式な裏付けを持たない事実上の標準（デファクトスタンダード）として運用され、1994年の仕様書および1997年のインターネットドラフト「A Method for Web Robots Control」に文書化されていた。[4][5][8] 1994年の初期形式は`User-agent`と`Disallow`フィールドのみを含み、`Allow`フィールドやワイルドカード一致は含まれていなかった。[4][5] 2022年9月、Internet Engineering Task Force（IETF）は個人ドラフト`draft-koster-rep`を基に、Martijn Koster、Gary Illyes、Henner Zeller、Lizzi Sassmanが執筆し、Murray Kucherawyが担当エリアディレクターを務めたRFC 9309（「Robots Exclusion Protocol」）を標準化過程の提案標準（Proposed Standard）として発行した。[1][3] RFC 9309は形式的なプロトコル文法を追加し、`Allow`とワイルドカード文字を標準化するとともに、エラー処理とキャッシュに関するルールを規定した。[1]

## robots.txtの配置場所、形式、および適用範囲

robots.txtファイルは、サービスの最上位ディレクトリにすべて小文字のパス`/robots.txt`として配置する必要があり、`scheme:[//authority]/robots.txt`（例：`https://www.example.com/robots.txt`や`ftp://ftp.example.com/robots.txt`）のURI形式に従う。[1][5] RFC 9309は、ファイルがUTF-8（RFC 3629）でエンコードされ、インターネットメディアタイプ`text/plain`（RFC 2046）で提供され、CR、LF、またはCRLFの改行コードを使用することを規定している。[1][6] Google検索の実装でサポートされるプロトコルは、HTTPおよびHTTPS（非条件付きHTTP GETリクエストで取得）とFTP（匿名`RETR`コマンドで取得）である。[6]

robots.txtファイル内のルールは、そのファイルを取得した正確なホスト、プロトコル、およびポート番号にのみ適用される。[6] Googleのドキュメントによれば、適用範囲は次の境界に従う。[6]

- **サブドメインとサブディレクトリ**：`https://example.com/robots.txt`のファイルは`https://other.example.com/`には適用されず、`/folder/robots.txt`のようにサブディレクトリに配置されたファイルは無効である。
- **プロトコルとポート**：`https://example.com/`のルールは`http://example.com/`や`ftp://example.com/`には適用されない。標準ポート（HTTPは80、HTTPSは443、FTPは21）はデフォルトのホスト名と同一視されるが、`:8181`のような非標準ポートには独自のファイルが必要である。
- **IDNとIPアドレス**：国際化ドメイン名（IDN）はそのPunycode形式（RFC 3492）と同等であり、IPアドレスのホスト名上でホストされたファイルはそのIPアドレスによるクロールにのみ適用される。

2026-11-23時点で、Googleはrobots.txtの最大ファイルサイズを500キビバイト（KiB）に制限しており、その上限を超える内容は無視する。[6] また、Googleのパーサーはファイル先頭のUnicodeバイトオーダーマーク（BOM）を含む無効な行も無視し、応答内に見つかった有効なルールのみを適用する。[6]

## robots.txtのディレクティブ、構文、および照合ルール

RFC 9309で定義されたrobots.txtの構文は、拡張バッカス・ナウア記法（ABNF、RFC 5234）を用いて、1行以上の`User-agent`行とそれに続く`Allow`および`Disallow`ルールから成るグループとしてキーと値の行を構成する。[1] フィールド名は大文字・小文字を区別せず、コメントは`#`で始まり、最初の`User-agent`行より前に現れる`Allow`および`Disallow`ルールはクローラーが無視すべきとされている。[1][4][6]

| ディレクティブまたはトークン | RFC 9309およびクローラー実装における役割 |
| --- | --- |
| `User-agent` | 対象クローラーを製品トークン（ASCII英字、`_`、`-`）で識別するか、デフォルトルール用に`*`を指定する。大文字・小文字を区別せず照合される。[1] |
| `Disallow` | 一致したクローラーがアクセスしてはならない`/`始まりのURIパス接頭辞を指定する。値が空の場合は制限を課さない。[1][6] |
| `Allow` | 一致したクローラーがアクセスしてよい`/`始まりのURIパス接頭辞を指定し、不許可ディレクトリ内のサブパスを許可するために用いられる。[1][6] |
| `Sitemap` | グループを終了させることなくRFC 9309で許容される非中核レコードであり、Googleはサイトマップの完全なURLによる指定に対応している。[1][6] |

各クローラーは、自身のHTTP `User-Agent`ヘッダー（RFC 9110）の部分文字列となる製品トークンを選択し、そのトークンに一致するすべてのグループのルールを統合して適用する。[1] 特定のグループが一致しない場合は`User-agent: *`グループが存在すればそれに従い、どちらも存在しない場合やファイルが空の場合はルールは一切適用されない。[1][4] パス照合はパスの先頭オクテットから開始され、大文字・小文字を区別すべきである。[1] 比較に先立ち、非ASCIIオクテットおよびRFC 3986の予約文字はパーセントエンコードし、パーセントエンコードされた非予約ASCII文字はデコードしなければならない。[1] RFC 9309は、コメント用の`#`、任意の文字の0回以上の繰り返しを表す`*`、一致パターンの末尾を示す`$`の3つの特殊文字への対応を要求しており、リテラルの`*`と`$`はそれぞれ`%2A`と`%24`として照合する。[1]

1つのURIに複数のルールが一致する場合、クローラーはオクテット数が最も多いパターンとして定義される最も具体的な一致を適用しなければならない。[1] `Allow`ルールと`Disallow`ルールの具体性が同等である場合は`Allow`ルールを使用すべきであり、`/robots.txt`というURI自体は暗黙的に許可される。[1] RFC 9309では、グループ構文解析を妨げない限り、クローラーはサイトマップなどの追加レコードを解釈できる。[1] Googleは`user-agent`、`allow`、`disallow`、`sitemap`に対応しており、`crawl-delay`には対応していない。[6] サイトマッププロトコルでは、XMLサイトマップは`<url>`および`<loc>`エントリを含むUTF-8の`<urlset>`文書であり、1ファイルあたり最大50,000 URLかつ非圧縮時50 MB（52,428,800バイト）までに制限され、複数のサイトマップは`<sitemapindex>`ファイルに一覧化できる。[10]

実装間の構文解析の差異を減らすため、Googleは本番用のC++製robots.txtパーサーおよびマッチャーライブラリをApache-2.0ライセンスの下で`github.com/google/robotstxt`にオープンソース公開した。[8] このリポジトリには、ローカルのrobots.txtファイルに対してユーザーエージェントとRFC 3986 URIを評価し、許可の場合は終了コード0、不許可の場合は1を返すコマンドラインテスト用バイナリ（`robots_main`）が含まれている。[8]

## robots.txtにおけるHTTPステータスコード処理とキャッシュ

クローラーは、`/robots.txt`の取得時に返されるHTTPステータスコードまたはネットワーク結果に基づいて、robots.txtルールの適用方法を決定する。[1][6] RFC 9309は成功、リダイレクト、利用不可、到達不可エラーの基本分類を定義しており、検索エンジンはそれに加えて運用上のタイムアウトやキャッシュ方針を公開している。[1][6]

| 応答分類 | RFC 9309の仕様 | Googleクローラーの処理（2026-11-23時点） |
| --- | --- | --- |
| `2xx`（成功） | ファイル内の有効なルールを解析して従う。[1] | 提供されたrobots.txtファイルをそのまま処理する。[6] |
| `3xx`（リダイレクト） | 別のオーソリティにまたがる場合でも、301や302などの連続リダイレクトを最低5回辿り、取得したルールを元のオーソリティに適用する。5回を超える場合、クローラーはファイルを利用不可として扱える。[1] | リダイレクトを最低5ホップ辿った後に停止し、応答を404として扱う。フレーム、JavaScript、メタリフレッシュによる論理リダイレクトは辿らない。[6] |
| `4xx`（利用不可） | HTTP 400-499はファイルが利用不可であることを示し、クローラーはサーバー上の任意のリソースにアクセスできる。[1] | 429を除くすべての4xxエラーをrobots.txtなし（クロール制限なし）として扱う。429以外の4xxコード（401や403を含む）はクロール速度を低下させない。[6] |
| `5xx`およびネットワークエラー（到達不可） | HTTP 500-599またはネットワークエラーではファイルが未定義となり、クローラーは完全な不許可を仮定しなければならない。[1] | 再試行しながら12時間クロールを停止する。その後の30日間は最後に有効だったキャッシュコピーを使用する（キャッシュがない場合は制限なしとみなす）。30日経過後、サイト全般が利用可能であれば制限なしとして扱い、サイト全般に可用性の問題があればクロールを停止する。[6] |

GoogleはDNSエラー、タイムアウト、無効な応答、接続のリセットまたは中断、HTTPチャンキングエラーを5xxサーバーエラーと同様に分類している。[6] HTTP 503応答に対しては、Googleはより高い頻度でrobots.txtの取得を再試行する。[6]

2026-11-23時点で、Googleは通常robots.txtファイルの内容を最大24時間キャッシュし、タイムアウトや5xxエラーによって更新が失敗した場合はキャッシュ版をより長く保持することがあり、さらに異なるGoogleクローラー間でキャッシュされたルールを共有する場合がある。[6] またGoogleは、HTTPの`Cache-Control` `max-age`応答ヘッダーに基づいてキャッシュ有効期間を延長または短縮することもある。[6]

## robots.txtの勧告的限界、セキュリティ、およびインデックス制御

RFC 9309は、robots.txtのルールがアクセス認可の手段ではないと明記しており、遵守するかどうかは各クローラーの選択に委ねられている。[1][7] 1994年の当初仕様でも、ルールを強制する主体は存在せず、現在および将来のすべてのロボットがルールを尊重する保証はないと記されていた。[4] 脆弱性スキャナーやスパマーが用いるメールアドレス収集ツールなどの悪意ある自動化クライアントは、日常的にrobots.txtを無視する。[5]

`/robots.txt`はあらゆるクライアントから公開アクセス可能であるため、その中にパスを列挙すると、管理者がクローラーに回避させたいサーバーディレクトリが外部に明らかになる。[5] robotstxt.orgとGoogleはいずれも、robots.txtで機密情報を隠匿することはできず、非公開ファイルを保護するにはパスワード保護などのアクセス制御が必要であると明記している。[5][7] さらにGoogleのドキュメントは、フィード購読のようなユーザー起動型フェッチャーや、マルウェア解析などユーザーの安全性保護のために運用されるクローラーにはREPが適用されないと説明している。[6]

検索エンジンにおいてrobots.txtはクロールトラフィックと帯域幅消費を管理する一方、インデックス登録の挙動はファイル種別と別のディレクティブに依存する。[7][9] HTMLページ、PDF、その他のテキストベース文書をrobots.txtでブロックするとGoogleによるページクロールは防げるものの、外部ページが説明的なアンカーテキスト付きでそのURLへリンクしていれば、Googleはページを訪問せずにURLをインデックス登録し、説明文なしの検索結果を表示することがある。[7] クロール可能なページを検索結果に表示させないようにするには、HTMLの`<meta name="robots">`要素（例：`noindex`）や`X-Robots-Tag` HTTP応答ヘッダーといったページ単位のディレクティブを用いるか、認証によってアクセスを制限する必要がある。[7][9] 画像、動画、音声などのメディアファイルについては、robots.txtによってGoogle検索結果への表示を防止できる一方、不可欠なスタイルシートやスクリプトのリソースファイルをブロックすると、依存するページをGoogleが正確にレンダリングおよび解析できなくなる場合がある。[7]

## robots.txt、IETF AIPREF、およびAIクローラーの選好シグナル

検索エンジンのクロールに加え、robots.txtは人工知能（AI）モデルの開発、展開、および利用に関するコンテンツ選好を表明する標準化作業でも参照されている。[2] 2026-11-23時点で、IETFのAI Preferences（`aipref`）ワーキンググループは、承認済み憲章`charter-ietf-aipref-01`の下でWeb and Internet Transport（`wit`）エリアにおいて活動中であり、Mark NottinghamとSuresh Krishnanが議長を、Mike Bishopがエリアディレクターを務めている。[2]

`aipref`の憲章は3つの成果物を定めている。すなわち、配信メカニズムに依存せずAI関連のコンテンツ選好を記述する標準化過程の語彙文書（`draft-ietf-aipref-vocab`）、IETFプロトコルおよび形式上でそれらの選好をコンテンツに紐付ける標準化過程の付与仕様（`draft-ietf-aipref-attach`）、そして複数の選好表明を調整するための標準手法である。[2] 2026-11-23時点で、両ドラフト成果物はIETF Datatracker上に2026年8月のマイルストーンとして記載されている。[2] 憲章は付与メカニズムとして、HTTP応答ヘッダーフィールドと並び、ロボット排除プロトコル（RFC 9309）などのWell-Known URI（RFC 8615）を明示しており、国際新聞電気通信評議会（IPTC）、PLUS Coalition、WHATWG、およびW3Cとの連携を指示している。[2]

RFC 9309の勧告的な境界と整合する形で、`aipref`憲章は選好の技術的強制、クライアントやクローラーの認証・認可を行うアプリケーション層プロトコル、コンテンツ選好のレジストリ、およびAI学習に関する監査・透明性措置の4領域をスコープから除外している。[2] 標準化団体の外でも、インフラストラクチャ事業者が検索での発見可能性とAI学習を分離する制御を導入しており、2026年9月15日に[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)は、サイト所有者が検索での発見可能性を維持しながらAI学習を不許可にできるよう、Apple、Google、Microsoftとの共有モデルを形成する制御機能およびAccountable指定を発表した。[11]

## よくある質問

### robots.txtファイルとは何ですか？

robots.txtファイルは、ロボット排除プロトコル（RFC 9309）に基づき、ウェブまたはFTPホストのルートディレクトリの/robots.txtに配置されるUTF-8のプレーンテキストファイルです。自動化されたクローラーに対し、そのホスト上でアクセスしてよいURIパスとアクセスしてはならないURIパスを伝えます。Martijn Kosterが1994年6月に初めて文書化し、IETFが2022年9月にRFC 9309として発行しました。 [1][4]

### RFC 9309においてrobots.txtはどのディレクティブに対応していますか？

RFC 9309では、User-agent、Allow、Disallowの3つの中核ディレクティブと、コメント用の#、ワイルドカード用の*、パス末尾一致用の$という特殊文字が標準化されています。クローラーは、グループの構文解析を妨げない範囲でSitemapなどの追加レコードも解釈できます。2026-11-23時点で、GoogleはUser-agent、Allow、Disallow、Sitemapに対応しており、crawl-delayには対応していません。 [1][6]

### クローラーはrobots.txtに対するHTTP 4xxおよび5xxエラーをどのように処理しますか？

RFC 9309では、HTTP 400-499応答はrobots.txtが利用できないことを示すため、クローラーはサーバー上の任意のリソースにアクセスできます。一方、HTTP 500-599応答はファイルに到達できないことを示し、完全な不許可を仮定する必要があります。2026-11-23時点で、Googleは429以外の4xxエラーをクロール制限なしとして扱い、5xxエラー時には12時間クロールを停止したうえで、最大30日間は最後にキャッシュされた有効なコピーを使用します。 [1][6]

### Googleのrobots.txtファイルサイズ上限はどのくらいですか？

2026-11-23時点で、Googleはrobots.txtの最大ファイルサイズを500キビバイト（KiB）に制限しています。500 KiBの上限を超える内容は、Googleのパーサーによって無視されます。 [6]

### robots.txtによってウェブページの検索結果への表示を防いだり、非公開ファイルを保護したりできますか？

いいえ。RFC 9309はrobots.txtのルールがアクセス認可の手段ではないと明記しており、準拠しないクローラーはファイルを無視できます。ウェブページの場合、他のページからリンクされていればGoogleはページを訪問せずに不許可のURLをインデックス登録できるため、検索結果からの除外や非公開ファイルの保護には、HTMLのmeta robots要素、X-Robots-Tag HTTPヘッダー、パスワード保護などの仕組みが必要です。 [1][7][9]

### IETF AIPREFワーキンググループはrobots.txtとどのように関係していますか？

2026-11-23時点で、活動中のIETF AI Preferences（aipref）ワーキンググループは、AIシステム向けのコンテンツ収集および処理に関する選好を表現するための語彙とプロトコル付与手法の標準化を憲章としています。承認された憲章には、ロボット排除プロトコル（RFC 9309）などのWell-Known URI（RFC 8615）やHTTP応答ヘッダーフィールドを通じて選好を付与する方法が明記されています。 [2]

## 引用できる文

- Martijn Kosterは、1994年6月30日のメーリングリストでの合意に基づき、ロボット排除プロトコルを最初に文書化した。 [1][4]
- IETFは2022年9月、ロボット排除プロトコルを標準化過程の文書RFC 9309として発行した。 [1][3]
- RFC 9309は、robots.txtファイルをUTF-8でエンコードし、メディアタイプtext/plainを用いてすべて小文字のパス/robots.txtで提供することを規定している。 [1]
- RFC 9309では、クローラーはオクテット長が最も長い具体的なパス一致ルールを適用し、AllowルールとDisallowルールが同等の場合はAllowルールを優先する。 [1]
- RFC 9309では、robots.txtに対するHTTP 400-499応答はサーバー上のすべてのリソースへのアクセスを許可し、HTTP 500-599応答は完全な不許可を仮定することを要求する。 [1]
- 2026-11-23時点で、Googleはrobots.txtに対して500 KiBのファイルサイズ上限を適用しており、その上限を超える内容は無視する。 [6]
- Googleのドキュメントは、robots.txtでウェブページをブロックしても、他のページからそのURLへリンクされていればGoogle検索結果にURLが表示される可能性があると明記している。 [7]
- 2026-11-23時点で、活動中のIETF AI Preferences（aipref）ワーキンググループは、RFC 9309やHTTP応答ヘッダーフィールドを含むIETFプロトコルを用いてAIコンテンツ選好を付与する仕様を策定する憲章を担っている。 [2]

## 年表

- 1994-06-30: Martijn Kosterが執筆した「A Standard for Robot Exclusion」についてメーリングリスト上で合意が形成された。 [4]
- 1997: インターネットドラフト「A Method for Web Robots Control」がrobots.txtによる排除メカニズムを文書化した。 [5]
- 2022-09: IETFがRFC 9309（「Robots Exclusion Protocol」）を標準化過程の提案標準として発行した。 [1][3]
- 2026-09-15: Cloudflareが、サイトを検索で発見可能に保ちつつAI学習を不許可にする制御機能とAccountable指定をApple、Google、Microsoftと共同で発表した。 [11]

## 出典

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. AI Preferences (aipref). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (閲覧 2026-11-23; tier 1: government or public registry)
3. RFC 9309 - Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://datatracker.ietf.org/doc/rfc9309/ (閲覧 2026-11-23; tier 1: government or public registry)
4. A Standard for Robot Exclusion - The Web Robots Pages. robotstxt.org. 公開 1994-06-30. https://www.robotstxt.org/orig.html (閲覧 2026-11-23; tier 3: official site)
5. About /robots.txt - The Web Robots Pages. robotstxt.org. https://www.robotstxt.org/robotstxt.html (閲覧 2026-11-23; tier 3: official site)
6. How Google Interprets the robots.txt Specification | Google Crawling Infrastructure | Crawling infrastructure | Google for Developers. Google Search Central. https://developers.google.com/crawling/docs/robots-txt/robots-txt-spec (閲覧 2026-11-23; tier 3: official site)
7. Robots.txt Introduction and Guide | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/robots/intro (閲覧 2026-11-23; tier 3: official site)
8. GitHub - google/robotstxt: The repository contains Google's robots.txt parser and matcher as a C++ library (compliant to C++11).. Google (GitHub). https://github.com/google/robotstxt (閲覧 2026-11-23; tier 3: official site)
9. Robots.txt - Glossary | MDN. MDN Web Docs. 公開 2025-11-26. https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt (閲覧 2026-11-23; tier 3: official site)
10. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (閲覧 2026-11-23; tier 3: official site)
11. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. 公開 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "robots.txt." 版 db0a1741, 2026-11-23. https://mimirwiki.com/ja/wiki/robots-txt
