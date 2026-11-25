---
title: "hreflang"
subtitle: "リンク先ウェブリソースの言語および対象地域を指定するHTML属性兼リンクパラメーター"
canonical_url: https://mimirwiki.com/ja/wiki/hreflang
language: ja
page_class: anchor
revision_sha256: a28739892e00f815159fd422e023a4b1dda71c78a4b4134a756df53d92dda9cc
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/hreflang.md
  txt: https://mimirwiki.com/ja/wiki/hreflang.txt
  json: https://mimirwiki.com/ja/wiki/hreflang.json
  jsonld: https://mimirwiki.com/ja/wiki/hreflang.jsonld
translations:
  en: https://mimirwiki.com/wiki/hreflang
  ko: https://mimirwiki.com/ko/wiki/hreflang
  zh: https://mimirwiki.com/zh/wiki/hreflang
  es: https://mimirwiki.com/es/wiki/hreflang
---

# hreflang

> hreflangは、RFC 5646のBCP 47タグを使用して、リンク先リソースの言語および任意で地域を識別するHTML属性兼リンクパラメーターである。ウェブサイトはHTMLのlink要素、HTTP Linkヘッダー、またはXMLサイトマップを通じてhreflangアノテーションを公開し、Google 検索がユーザーに適したローカライズ版ページへ案内できるようにする。

hreflangは、リンク先のウェブ リソースの自然言語、および任意で対象地域を示すHTML属性兼リンクアノテーションパラメーターである。WHATWG HTML Living Standardにおいて反映属性として定義され、IETF RFC 5646で規定されたBCP 47言語タグと組み合わせて用いられる。アンカー要素上ではブラウザの組み込み動作を伴わず、外部のリンク処理系に向けたメタデータとして機能する。Google 検索では、ウェブサイトがalternateリンク関係とhreflangアノテーションを組み合わせ、HTMLのlink要素、RFC 8288で定義されたHTTP Linkヘッダー、またはXMLサイトマップを通じて公開することで、ページのローカライズ版同士を関連付ける。Googleは列挙されたバリエーション間での双方向リンクを要求しており、一致する言語や地域がない場合のフォールバックページ向けにx-default値をサポートしている。

**別名:** hreflang属性, hreflangタグ, hreflangアノテーション, rel=alternate hreflang

## 主要な事実

- **HTML仕様:** WHATWG HTML Living Standard（2026年11月22日更新） (時点 2026-11-23) [1]
- **言語タグ標準:** IETF BCP 47 / RFC 5646（2009年9月） [2]
- **サブタグレジストリ:** IANA言語サブタグレジストリ（ファイル日付 2026-11-18） (時点 2026-11-23) [4]
- **HTTPヘッダー仕様:** IETF RFC 8288（Web Linking、2017年10月） [3]
- **Googleの指定方法:** HTMLのlink要素、HTTP Linkヘッダー、XMLサイトマップ (時点 2026-11-23) [6]

## ファクトシート

- **種別:** リンク先URLの自然言語を示唆するHTML属性 [9]
- **HTML仕様:** WHATWG HTML Living Standard 第4.6節（2026年11月22日更新） (時点 2026-11-23) [1]
- **DOM API:** HyperlinkElementUtils.hreflang（反映DOMString） [1]
- **言語タグ構文:** IETF BCP 47（RFC 5646、2009年9月、RFC 4646を廃止） [2]
- **サブタグレジストリ:** IANA言語サブタグレジストリ（ファイル日付 2026-11-18） (時点 2026-11-23) [4]
- **HTTPヘッダー仕様:** IETF RFC 8288（Web Linking、2017年10月、RFC 5988を廃止） [3]
- **HTML linkのベースライン:** HTMLのlink要素は2015年7月から主要ブラウザで広く利用可能 [8]
- **Googleの指定方法:** HTMLのlink要素、HTTP Linkヘッダー、XMLサイトマップ (時点 2026-11-23) [6]
- **フォールバック値:** x-default（2013年4月にGoogle 検索セントラル ブログで発表） [10]
- **確認ルール:** Google 検索では自己参照および双方向リンクが必須 (時点 2026-11-23) [6]

## hreflangの概要

hreflangは、リンク先のウェブ リソースの自然言語、および任意で対象地域を示すHTML属性兼リンクアノテーションパラメーターである。[6][9] HTMLにおいてリンクとは、`a`、`area`、`form`、`link`の各要素によって生成される2つのリソース間の概念的な接続であり、外部リソースへのリンク、ハイパーリンク、内部リソースリンクに分類される。[1]

WHATWG HTML Living Standard（2026年11月22日更新）の第4.6.3節は、`HyperlinkElementUtils`インターフェースミックスイン上に反映`DOMString`属性として`hreflang`を定義している。[1] MDN Web Docsは、現在の文書と外部リソースの関係を指定するHTMLの`link`要素と、ハイパーリンクを作成するHTMLの`a`アンカー要素の双方を解説しており、両要素とも2015年7月から主要ブラウザで広く利用可能であると記録している。[8][9] MDNは、`a`要素における`hreflang`がリンク先URLの自然言語を示唆し、ブラウザの組み込み機能を持たず、グローバル`lang`属性と同じ言語タグ値を受け取ると説明している。[9]

Google 検索では、ウェブサイトが`alternate`リンク関係と`hreflang`を組み合わせて複数言語・複数地域にわたるローカライズ版ページを宣言し、検索結果がユーザーの言語や地域に一致するバージョンを指すようにする。[6]

## hreflangで使用されるBCP 47およびRFC 5646言語タグ

hreflangの値は、2009年9月に公開されたIETF RFC 5646（"Tags for Identifying Languages"）で規定されるBCP 47言語タグを使用する。[2][5][9] A. PhillipsとM. Davisが編集したRFC 5646は、RFC 4646（さらにRFC 3066およびRFC 1766を置き換えた仕様）を廃止し、RFC 4647と合わせてBCP 47を構成している。[2][5]

BCP 47言語タグは、ハイフン（`-`、U+002D）で区切られた1つ以上の英数字サブタグから成り、`language-extlang-script-region-variant-extension-privateuse`の順序で並ぶ。[2][5] 各サブタグ種別は長さ・位置・文字種によって識別されるため、RFC 3066時代に登録された固定の旧来タグ（grandfathered tags）を除き、処理系はレジストリのローカルコピーを持たずにサブタグの分類を判別できる。[2]

| サブタグ種別 | 形式 | 根拠標準 | 例 |
| --- | --- | --- | --- |
| プライマリ言語 | 英字2〜3文字（または登録済み5〜8文字） | ISO 639 | `en`, `es`, `ast`, `mas` |
| 拡張言語 | マクロ言語サブタグに続く英字3文字 | ISO 639 | `zh-yue`, `ar-afb` |
| 文字体系（スクリプト） | 英字4文字（RFC 4646で導入） | ISO 15924 | `zh-Hans`, `az-Latn` |
| 地域 | 英字2文字または数字3桁 | ISO 3166-1 / UN M.49 | `fr-CA`, `en-GB`, `de-CH`, `es-419` |
| バリアント | 英数字5〜8文字、または数字1桁と英数字3文字 | IANAレジストリ | 登録済みの方言または正書法サブタグ |
| 拡張および私用 | 単一の英数字シングルトン（`x`は私用として予約） | RFC 5646 | 単一文字拡張、`x-`私用タグ |

有効なすべてのサブタグは単一のプレーンテキストファイルであるIANA言語サブタグレジストリで管理されており、2026年11月23日時点のファイル日付は2026年11月18日である。[4][5] このレジストリは各言語につき1つのISO 639値を採用し（2文字コードがある場合はそれを選択し、なければ3文字コードを1つ選択する）、RFC 5646の公開時に7,000を超えるISO 639-3の3文字コードを追加した。[5] レジストリのレコードには、`Type`、`Subtag`、`Description`、`Added`、`Suppress-Script`、`Scope`、`Deprecated`、`Preferred-Value`といったフィールドが含まれる。[4][5] たとえば、`bh`（ビハール語群）のエントリには2026年6月14日の廃止日と`Preferred-Value: bih`が設定されている。[4]

W3Cは、HTMLおよびXMLにおいて言語タグは大文字と小文字を区別せず、言語サブタグを小文字、文字体系サブタグを先頭大文字、英字の地域サブタグを大文字で表記するのは慣例に過ぎないと述べている。[5] W3Cは、言語タグを可能な限り短く保ち、有用な区別を生まない地域や文字体系サブタグは省略し、`en`、`es`、`fr`に対する`Latn`のような`Suppress-Script`エントリに従うよう推奨している。[4][5] `zh-yue`や`ar-afb`のような従来の言語＋拡張言語の組み合わせについては、同等の単独プライマリ言語サブタグ（`yue`や`afb`）が存在するため、可能な限り単独のサブタグを使用するようW3Cは助言している。[5]

## hreflangアノテーションの実装方法

2026年11月23日時点のGoogle 検索セントラルのドキュメントは、hreflangアノテーションを提供する同等の3つの方法として、HTMLの`link`要素、HTTP `Link`ヘッダー、および[XMLサイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)を規定している。[6] Googleは3つの方法を同等に扱い、同じページで複数の方法を併用しても検索上の追加の利点は得られず、保守の手間が増えるだけである。[6]

| 方法 | 配置と構文 | 主な用途 |
| --- | --- | --- |
| HTMLの`link`要素 | `head`要素内に`rel="alternate"`、`hreflang`、`href`を持つ`link`要素を配置 | サイトマップやHTTPヘッダーを制御できないHTMLページ |
| HTTP `Link`ヘッダー | GETレスポンス内で、各URLを山括弧で囲み`rel="alternate"`と`hreflang`を添えたカンマ区切りの`Link`ヘッダーエントリ | PDFなどの非HTMLファイル |
| XMLサイトマップ | `xhtml` XML名前空間を宣言し、各`loc`要素の配下に`xhtml:link`子エントリを記述 | 複数バージョンURL群の一元管理 |

HTML文書では、正しく構成された`head`要素内に、ページ自身を含むすべてのバリエーションごとに1つずつ`link`要素を配置しなければならない。[6][8] XHTML 1.0では、`link`などの空要素（void element）には末尾のスラッシュが必要である。[8] Googleは、`hreflang`アノテーションを専用の`link`要素に記述しなければならず、単一の`link`要素内で`media`などの他の代替表現属性と組み合わせてはならないと規定している。[6]

HTTPヘッダーについては、2017年10月にM. Nottinghamによって公開されRFC 5988を廃止したIETF RFC 8288（"Web Linking"）が、一般的なウェブリンクモデル（リンクコンテキスト、リンク関係種別、リンクターゲット、任意のターゲット属性）を定義し、HTTP `Link`ヘッダーフィールドへのシリアライズを規定するとともに、RFC 5646の`Language-Tag`構文を取り込んでいる。[3] `alternate`を含む登録済みリンク関係種別はIANAリンク関係レジストリで管理されている。[3] Google 検索では、リソースのGETレスポンスで返される`Link`ヘッダーにすべてのローカライズ版をカンマ区切りで列挙し、各完全修飾URLを山括弧で囲んで`rel="alternate"`と`hreflang`を続け、リソースの全バージョンが同一のヘッダーを返すようにする。[6]

[XMLサイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)では、各ローカライズ版ごとに`loc`要素を設け、`xhtml`名前空間を宣言したうえで、自身を含むすべての言語・地域バリエーションを列挙した子要素`xhtml:link`を組み合わせる。[6] ページに3つのバージョンがある場合、サイトマップには3つの`loc`エントリが含まれ、各エントリが同一の3つの`xhtml:link`子エントリを保持する。[6]

## hreflangの相互リンクとURLに関するルール

Google 検索は、ローカライズされたグループ内のすべてのURLが互いを検証できるよう、HTMLの`link`要素、HTTP `Link`ヘッダー、XMLサイトマップのすべてに共通の構造ルールを適用している。[6]

- **自己参照と完全なセット**: ページの言語版または地域版はそれぞれ自身と他のすべてのバリエーションを列挙する必要があり、グループ内のすべてのバージョンで同一のアノテーションセットになるようにする。[6]
- **双方向の確認**: 2つのページが相互に指し合っていない場合、Googleはそのアノテーションを無視する。このルールは、外部ウェブサイトが他サイト上のページの代替バージョンとして自社ページを任意に指定することを防ぐ。[6]
- **部分的な双方向リンク**: すべての言語間で完全な双方向リンクを維持することが現実的でない場合、一部のページで一部の言語を省略できる。Googleは双方向にリンクされたペアを引き続き処理し、新たに追加した言語ページはサイトのオリジナル言語または主要言語のページと双方向にリンクするよう推奨している。[6]
- **完全修飾URL**: すべての代替URLには`https://example.com/foo`のようにトランスポートスキーム（`http`または`https`）を含める必要があり、プロトコル相対URL（`//example.com/foo`）や相対パス（`/foo`）は除外される。[6]
- **クロスドメインのサポート**: 代替URLは同一ドメインに属している必要はない。[6]
- **汎用言語のフォールバック**: 1つの言語の話者を対象とする複数の地域URL（`en-IE`、`en-CA`、`en-AU`など）がある場合、Googleは地域が特定されないユーザー向けに汎用言語エントリ（`en`）を提供することを推奨しており、これには既存の地域URLの1つを再利用できる。[6]

GoogleはURL内の言語別サブドメイン（`en`、`en-gb`、`en-us`、`de`など）からページの対象ユーザーを推測しないため、対象とする各言語や地域は`hreflang`アノテーションで明示的にマッピングする必要がある。[6]

## フォールバックページ向けのx-default hreflang値

`x-default` hreflang値は、ページに明示的に列挙されたいずれのバリエーションにも言語や地域が一致しない訪問者向けのフォールバックURLを指定する。[6] Google 検索セントラル ブログは、2013年4月に国際ランディングページ向けの`x-default` hreflangを導入する発表記事を公開し、その後2023年5月のブログ記事「How x-default can help you」を一覧に掲載した。[10]

Google 検索セントラルのドキュメントは、特に言語・国選択ページや訪問者を自動的にリダイレクトするホームページにおいて`x-default`の使用を取り上げている。[6] Googleのドキュメント例では、イギリス英語（`en-GB`）、アメリカ英語（`en-US`）、汎用英語（`en`）、ドイツ語（`de`）のページを提供するウェブサイトが、言語および地域セレクターを備えた中立的なランディングページである`https://www.example.com/`に`hreflang="x-default"`を割り当てている。[6]

`x-default`値は、標準のBCP 47言語タグと併せて、HTMLの`link`要素、HTTP `Link`ヘッダー、XMLサイトマップのすべてでサポートされている。[6]

## Google 検索におけるhreflangと多言語サイトの処理

Google 検索は、hreflangアノテーションを用いて同等コンテンツのローカライズ版バリエーションを認識し、検索者の言語や地域設定に一致するバージョンを表示する。[6] Googleは、複数言語でコンテンツを提供する多言語ウェブサイト（カナダ企業向けの英語・フランス語版など）と、異なる国のユーザーを明示的に対象とする多地域ウェブサイト（カナダとアメリカなど）を区別しており、1つのサイトが両方に該当し得るとしている。[7]

Google 検索は、ページの言語を検出するために`hreflang`、HTMLの`lang`属性、またはURLを使用しない。[6][7] Googleはページ上の可視コンテンツからアルゴリズムによってページ言語を判定しており、1ページにつきコンテンツとナビゲーションの双方を単一言語に統一し、並列翻訳を避けるよう推奨している。[6][7]

Googleは`hreflang`の代表的な3つのシナリオを挙げている。主要なユーザー生成コンテンツは単一言語のままテンプレート（ナビゲーションやフッター）のみを翻訳するページ、同一言語内で小さな地域差を設けるページ（アメリカ、イギリス、アイルランド向けの英語など）、および複数言語に完全翻訳されたページである。[6] ページのローカライズ版が重複として扱われるのは、メインコンテンツが未翻訳のまま残っている場合のみである。[6]

Googleは、各言語バージョンに固有のURLを割り当て、`hreflang`アノテーションで関連付けることを推奨している。[7] Cookieやブラウザ設定によってコンテンツを動的に切り替えると、Googlebotは通常アメリカからクロールしHTTPリクエストに`Accept-Language`ヘッダーを含めないため、すべてのバリエーションを発見できなくなるおそれがある。[7] またGoogleは、推測されたユーザー言語に基づく自動リダイレクトを避け、ユーザーが手動でバージョンを選択できるハイパーリンクを用いるよう推奨しており、UTF-8エンコーディングと適切なURLエスケープを用いたURL内のローカライズ語句および国際化ドメイン名（IDN）をサポートしている。[7]

## よくある質問

### hreflangとは何ですか？

hreflangは、BCP 47言語タグを用いて、リンク先のウェブ リソースの自然言語および任意で対象地域を示すHTML属性兼リンクアノテーションパラメーターです。Google 検索では、ウェブサイトがalternateリンク関係とhreflangを組み合わせて、ページのローカライズ版同士を関連付けます。 [2][6][9]

### Google 検索向けにhreflangを実装するにはどの方法が使えますか？

2026年11月23日時点で、Google 検索はhead要素内のHTML link要素、PDFなどの非HTMLファイルに有用なHTTP Linkレスポンスヘッダー、XMLサイトマップ内のxhtml:link子エントリという同等の3つの方法をサポートしています。複数の方法を同時に使用しても、検索上の追加の利点はありません。 [6]

### なぜhreflangリンクは双方向である必要があるのですか？

Google 検索は、ローカライズされたページ群の各ページが自身と他のすべてのバリエーションを参照することを求めており、相互に指し合っていないペアは無視します。この確認ルールにより、別のウェブサイトが管理権限を持たないページの代替バージョンとして無断で自社ページを登録することを防いでいます。 [6]

### hreflang="x-default"は何を意味しますか？

x-default値は、明示的に列挙されたいずれのhreflangタグにも言語や地域が一致しないユーザー向けのフォールバックページを指定します。Googleは2013年4月にx-defaultを発表しており、言語や国の選択ページ、または自動リダイレクトを行うホームページでの使用をドキュメントに記載しています。 [6][10]

### Google 検索はページの言語検出にhreflangを使用しますか？

いいえ。Google 検索は、ページの言語を検出するためにhreflang、HTMLのlang属性、またはURLを使用しません。Googleはページ上の可視コンテンツからアルゴリズムによってページ言語を判定し、hreflangは同一コンテンツのローカライズ版を識別するために使用します。 [6][7]

### hreflangの言語コードと地域コードはどのように記述しますか？

言語タグはIETF BCP 47（RFC 5646）に準拠し、IANA言語サブタグレジストリのサブタグをハイフンで結合します。2文字または3文字のISO 639プライマリ言語サブタグで始まり、必要に応じて4文字のISO 15924文字体系サブタグや、2文字のISO 3166-1または3桁のUN M.49地域サブタグを続けます。HTMLおよびXMLでは言語タグの大文字と小文字は区別されません。 [2][4][5]

## 引用できる文

- WHATWG HTML Living Standard（2026年11月22日更新）は、hreflangをHyperlinkElementUtilsインターフェースミックスイン上の反映DOMString属性として定義している。 [1]
- MDN Web Docsは、HTMLのa要素におけるhreflang属性がリンク先URLの自然言語を示唆し、組み込み機能を持たず、グローバルlang属性と同じ値を受け取ると記載している。 [9]
- 2009年9月にBCP 47の一部として公開されたIETF RFC 5646は、ハイフン区切りのサブタグによる言語タグ構文を規定し、RFC 4646を廃止している。 [2]
- 有効な言語・文字体系・地域サブタグはIANA言語サブタグレジストリで管理されており、2026年11月23日時点のファイル日付は2026年11月18日である。 [4][5]
- 2017年10月に公開されたIETF RFC 8288は、HTTP Linkヘッダーフィールドを規定し、RFC 5646のLanguage-Tag構文を参照している。 [3]
- 2026年11月23日時点で、Google 検索セントラルのドキュメントは、hreflangアノテーションを指定する同等の3つの方法としてHTMLのlink要素、HTTP Linkヘッダー、XMLサイトマップを挙げている。 [6]
- Google 検索は、2つのページが相互にリンクし、かつ各ページが自身とすべての代替バージョンを列挙していない限り、両ページ間のhreflangアノテーションを無視する。 [6]
- Google 検索セントラル ブログは、2013年4月に国際ランディングページ向けのx-default hreflang値を発表した。 [10]

## 年表

- 2009-09: IETFがBCP 47の一部としてRFC 5646（Tags for Identifying Languages）を公開し、RFC 4646を廃止するとともに、7,000を超えるISO 639-3の3文字言語コードをIANA言語サブタグレジストリに追加した。 [2][5]
- 2013-04: Google 検索セントラル ブログが、国際ランディングページ向けのx-default hreflangを導入する発表記事を公開した。 [10]
- 2015-07: MDN Web Docsの記録によると、HTMLのlink要素およびa要素が主要ブラウザでのベースライン利用可能状態に到達した。 [8][9]
- 2017-10: IETFがRFC 8288（Web Linking）を公開し、RFC 5988を廃止するとともに、RFC 5646言語タグ構文を含むHTTP Linkヘッダーのシリアライズを定義した。 [3]

## 出典

1. HTML Standard. WHATWG. 公開 2026-11-22. https://html.spec.whatwg.org/multipage/links.html (閲覧 2026-11-23; tier 1: government or public registry)
2. RFC 5646: Tags for Identifying Languages. Internet Engineering Task Force (IETF). 公開 2009-09. https://www.rfc-editor.org/rfc/rfc5646.txt (閲覧 2026-11-23; tier 1: government or public registry)
3. RFC 8288: Web Linking. Internet Engineering Task Force (IETF). 公開 2017-10. https://www.rfc-editor.org/rfc/rfc8288.txt (閲覧 2026-11-23; tier 1: government or public registry)
4. IANA Language Subtag Registry. Internet Assigned Numbers Authority (IANA). 公開 2026-11-18. https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry (閲覧 2026-11-23; tier 1: government or public registry)
5. Language tags in HTML and XML. World Wide Web Consortium (W3C). https://www.w3.org/International/articles/language-tags/ (閲覧 2026-11-23; tier 1: government or public registry)
6. Localized Versions of your Pages | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/localized-versions (閲覧 2026-11-23; tier 3: official site)
7. Managing Multi-Regional and Multilingual Sites | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (閲覧 2026-11-23; tier 3: official site)
8. <link> HTML external resource link element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/link (閲覧 2026-11-23; tier 3: official site)
9. <a> HTML anchor element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a (閲覧 2026-11-23; tier 3: official site)
10. Introducing "x-default hreflang" for international landing pages | Google Search Central Blog | Google for Developers. Google Search Central Blog. 公開 2013-04. https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "hreflang." 版 a2873989, 2026-11-23. https://mimirwiki.com/ja/wiki/hreflang
