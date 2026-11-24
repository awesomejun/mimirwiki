---
title: "Markdown"
subtitle: "軽量なプレーンテキストマークアップ言語、text/markdownメディアタイプ、およびCommonMarkやGFMなどの標準化仕様"
canonical_url: https://mimirwiki.com/ja/wiki/markdown
language: ja
page_class: anchor
revision_sha256: e34755a3892a5b77058e7b2e04ee4840c490f52e71fbb62581f5ac72e36aa16a
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/ja/wiki/markdown.md
  txt: https://mimirwiki.com/ja/wiki/markdown.txt
  json: https://mimirwiki.com/ja/wiki/markdown.json
  jsonld: https://mimirwiki.com/ja/wiki/markdown.jsonld
translations:
  en: https://mimirwiki.com/wiki/markdown
  ko: https://mimirwiki.com/ko/wiki/markdown
  zh: https://mimirwiki.com/zh/wiki/markdown
---

# Markdown

> Markdownは、読みやすいプレーンテキストを記述してHTMLへ変換するために2004年にジョン・グルーバーがアーロン・スワーツの貢献を得て開発した軽量マークアップ言語である。主なバリアントにはCommonMarkやGitHub Flavored Markdownがある。IETFは2016年3月にRFC 7763でtext/markdownメディアタイプを登録し、llms.txtなどの提案ではAIエージェント向けにMarkdownが用いられている。

Markdownは、読みやすいプレーンテキストをHTMLなどの正式なマークアップ言語へ変換する軽量マークアップ言語およびプレーンテキスト書式構文群である。ジョン・グルーバーがアーロン・スワーツの大きな貢献を得て2004年に開発し、構文解説とともにBSDスタイルのオープンソースライセンスによるPerl製変換ツールMarkdown.plを公開した。オリジナルの解説に構文上の曖昧さが残り実装間の差異が広がったため、明確な構文解析規則を定めるCommonMark仕様が2014年に開始され、続いて2016年3月にはInternet Engineering Task Force（IETF）がRFC 7763でtext/markdownメディアタイプを登録し、コンパニオン文書RFC 7764を発行した。GitHub Flavored Markdown（GFM）などの方言はテーブルやタスクリストなどの機能でCommonMarkを拡張しており、llms.txtのようなWeb慣習は大規模言語モデルやAIエージェントへ構造化ドキュメントを提供する形式としてMarkdownを採用している。

**別名:** マークダウン, text/markdown, CommonMark, GFM, GitHub Flavored Markdown

## 主要な事実

- **開発者:** ジョン・グルーバー（アーロン・スワーツが貢献） [2]
- **初公開:** 2004年（Markdown 1.0.1は2004-12-17公開） [3]
- **MIMEメディアタイプ:** text/markdown（RFC 7763、2016年3月） [1]
- **公式中核仕様:** CommonMark（2014年開始） [5]
- **主要拡張方言:** GitHub Flavored Markdown（GFM）、バージョン0.29-gfm（2019-04-06） (時点 2026-11-23) [6]

## ファクトシート

- **種別:** 軽量マークアップ言語およびプレーンテキスト書式構文 [1]
- **開発者:** ジョン・グルーバー（アーロン・スワーツが大きく貢献） [2]
- **初公開:** 2004年 [2]
- **初期変換ツール:** Markdown.pl 1.0.1（Perl、18 KB、2004-12-17、BSDスタイルオープンソースライセンス） [3]
- **MIMEメディアタイプ:** text/markdown（必須パラメータ：charset、任意パラメータ：variant） [1]
- **IETF文書:** RFC 7763およびRFC 7764（情報提供用、2016年3月、著者S. Leonard） [2]
- **中核仕様:** CommonMark（2014年開始、ジョン・マクファーレン執筆） [7]
- **リファレンス実装:** cmark（C）およびcommonmark.js（JavaScript）、BSDライセンス [7]
- **CommonMarkメンテナー:** ジョン・マクファーレン、Martin Woodward、ジェフ・アトウッド (時点 2026-11-23) [5]
- **GFM仕様:** バージョン0.29-gfm（2019-04-06）、CommonMarkの厳密なスーパーセット (時点 2026-11-23) [6]
- **AI向けWeb慣習:** llms.txt提案（/llms.txtおよび.mdページ版）で使用 [8]

## Markdownの起源と設計哲学

Markdownは2004年にジョン・グルーバーがアーロン・スワーツの大きな貢献を得て開発した。[2][5] グルーバーはMarkdownを、プレーンテキスト書式構文と、その書式を構造的に有効なHTMLへ変換するPerl製ソフトウェアツール（`Markdown.pl`）という2つの要素として定義した。[3] BSDスタイルのオープンソースライセンスの下でフリーソフトウェアとして公開されたMarkdown 1.0.1（18 KB）は2004年12月17日にリリースされ、これが`Markdown.pl`の最終更新版となった。[3][5]

`Markdown.pl`の動作にはPerl 5.6.0以降および標準モジュールの`Digest::MD5`が必要であった。[3] デフォルトでは空要素に対してXHTML形式のタグを出力し、`--html4tags`コマンドラインオプションまたはMovable Typeの`MTMarkdownOptions`コンテナタグによってHTML 4出力へ切り替えることができた。[3] グルーバーが文書化した初期の対応環境には、Movable Type 2.6以降（タイポグラフィ用の引用符・ダッシュ・省略記号を処理するSmartyPants 1.5以降との任意連携を含む）、Blosxom 2.0以降、Mac OS X上のBBEdit 6.1以降（およびMac OS 8.6以降でMacPerl 5.6.1と組み合わせるBBEdit 5.1以降）、ならびにUnixコマンドライン実行が含まれていた。[3] またグルーバーは、構文へのフィードバック・テスト・`html2text`ユーティリティを提供したアーロン・スワーツの功績を挙げ、フィードバックを寄せたNathaniel Irons、Dan Benjamin、Daniel Bogan、Jason Perkinsに謝意を示すとともに、Michel FortinによるMarkdownのPHP移植版にも言及した。[3]

Markdownの最優先の設計目標は可読性であり、書式設定された文書が書式指定のタグで覆われているように見えず、プレーンテキストのまま直接公開できることを目指している。[3][4] グルーバーはSetext、atx、Textile、reStructuredText、Grutatext、EtTextといった既存のテキストからHTMLへの変換フィルタの影響を挙げつつ、最大の着想源はプレーンテキストの電子メールであったとしている。[4] グルーバーはHTMLを出版用フォーマット、MarkdownをHTMLタグのごく一部に対応する執筆用フォーマットと位置づけた。[1][4] RFC 7764に記録されている通り、グルーバーはシンジケーションフィードにおける厳格なXMLおよびXHTML処理の課題を受けて非公式な形式としてMarkdownを設計し、1つのブログ記事に含まれる不正なXHTMLがトラックバック経由で他のWebサイトを破綻させるというマーク・ピルグリムの思考実験を引き合いに出している。[2] ポステルの法則とXML 1.0の致命的エラー要件を対比させた結果、オリジナルのMarkdownは不正な構文という概念を排し、管理する標準化団体を持たずに運用されている。[1][2]

## Markdownの構文とインラインHTML

Markdownは構造的な役割に視覚的に似た印字可能な記号文字を用いており、オリジナルの構文では印字可能なUS-ASCII文字に限定されていた。[1][4] 構文は文書をブロック要素（段落、見出し、引用、リスト、コードブロック、水平線または主題区切り）と、スパン要素すなわちインライン要素（リンク、強調、強い強調、コードスパン、画像、自動リンク、バックスラッシュエスケープ）に分類している。[4][6]

| 要素 | オリジナルのMarkdown構文 | CommonMarkでの追加・明確化 |
| --- | --- | --- |
| 段落 | 空行で区切られた1行以上の連続した行（強制折り返しテキストに対応） | 同一規則を維持し、スペースまたはタブのみの行を空行とみなす |
| 強制改行 | 行末に2つ以上のスペースを置いた後の改行 | 行末のバックスラッシュによる記法を追加 |
| 見出し | Setext形式（H1は`=`、H2は`-`の下線）およびATX形式（行頭に1〜6個の`#`） | 空白文字の扱いとブロック優先順位規則を標準化 |
| 引用 | 電子メール形式の`>`接頭辞（遅延折り返し、入れ子、内部ブロックに対応） | 空行で区切られた`>`ブロックは別個の引用として維持 |
| 順序なしリスト | `*`、`+`、または`-`の後に空白 | 箇条書き記号を変更すると新しいリストを開始 |
| 順序付きリスト | 数字の後に`.`（HTML出力では元の数値を無視） | `.`または`)`の区切り文字を許容し、開始番号を保持、区切り文字変更で新しいリストを開始 |
| コードブロック | インデントされた行（スペース4つまたはタブ1つ） | バッククォートまたはチルダで囲むフェンスドコードブロックを追加 |

Markdownの構文に含まれないマークアップが必要な場合、執筆者はモード切り替えの区切り記号を使わずに生HTMLを文書内へ直接記述できる。[4] オリジナルのMarkdownでは、ブロックレベルHTML要素（`div`、`table`、`pre`、`p`など）は前後のテキストから空行で区切り先頭インデントを付けずに配置する必要があり、その内部のMarkdown構文は処理されない。[4] 一方、スパンレベルHTML要素（`span`、`cite`、`del`など）は段落・リスト項目・見出しの内部に配置でき、スパンレベル要素内のMarkdown構文は処理される。[4]

またMarkdownは小なり記号とアンパサンド文字の自動エスケープを行う。[4] アンパサンドが`&copy;`のような既存のHTMLエンティティの一部である場合や、山括弧がHTMLタグを区切っている場合にはそのまま保持され、それ以外のリテラルな小なり記号とアンパサンドはHTMLエンティティへ変換される。[4] Markdownのコードスパンおよびコードブロック内では、山括弧とアンパサンドは常に自動的にエスケープされる。[4]

## Markdownのメディアタイプ登録（RFC 7763およびRFC 7764）

Markdownコンテンツは、Internet Engineering Task Force（IETF）が2016年3月にRFC 7763を発行したことで、公式MIMEメディアタイプ`text/markdown`を獲得した。[1] Penango, Inc.のS. Leonardが情報提供用RFCとして執筆したRFC 7763は、`text/troff`（RFC 4263）に着想を得て、MIME対応システム間で執筆中のMarkdown文書を識別するための`text/markdown`を定義している。[1] RFC 7763は分割画面のライブプレビューエディタを主要なユースケースとして挙げ、デスクトップエディタ（MarkdownPad、MultiMarkdown Composer）、ブラウザツール（Dillinger、Markable）、統合型Webウィジェット（Discourse、GitHub）、汎用テキストエディタ（emacs、vi、Notepad）間の相互運用性に言及している。[1]

RFC 7763では、`text/markdown`メディアタイプに1つの必須パラメータと1つの任意パラメータが定義されている。[1] `charset`パラメータはRFC 6838第4.2.1節に基づき必須であり、オリジナルのMarkdown規則が文字単位で動作して特定の文字エンコーディングを強制しないため、デフォルト値は存在しない。[1] 任意の`variant`パラメータは、意図するMarkdown方言のヒントとして機能する大文字・小文字非区別のプレーンUS-ASCII識別子を格納する。受信側はそのバリアントを適用することもヒントを無視することもでき、バリアント名はRFC 7763第6.1節で設立されたIANA Markdown Variantsレジストリへ登録できる。[1]

RFC 7763と同時期の2016年3月にS. Leonardが発行したコンパニオン情報提供用文書RFC 7764は、Markdownの設計哲学、ローカル保存戦略、およびバリアント登録テンプレートをまとめている。[2] RFC 7764は、メディアタイプやパラメータのメタデータをローカル環境で保持するための6つの戦略（ファイル名・属性へのマッピング、隣接ファイルへのヘッダ保存、コンテンツへのMIMEヘッダ付与、ローカルバッチスクリプトの作成、Markdownの事前処理、コンテキストへの依存）に加え、SubversionおよびGit向けの具体的な運用方法を示している。[2] さらに、MultiMarkdown、GitHub-Flavored Markdown、Pandoc、Fountain（Fountain.io）、CommonMark、`kramdown-rfc2629`（RFC向けMarkdown）、`rfc7328`（Pandoc2rfc）、PHP Markdown Extraという8つの主要Markdown構文の登録テンプレートを収録している。[2]

RFC 7763は、テキストエディタが文字方向を変更するUnicode文字などの制御文字を適切に処理する限り、Markdownをプレーンテキストとしてのみ表示する場合のセキュリティリスクは限定的であると指摘している。[1] 一方、MarkdownをHTMLなどの対象フォーマットへ変換すると、スクリプト実行、リダイレクト、リモートコンテンツのダウンロード、個人識別情報の送信といった対象フォーマットのセキュリティ上の懸念を引き継ぐほか、解析とサニタイズを要する生の正式マークアップ断片が埋め込まれる可能性がある。[1]

## Markdown向けのCommonMark仕様

CommonMarkは、Markdown実装間における構文解析の差異を解消するため、2014年に開始された形式的かつ明確なMarkdown構文仕様である。[5] グルーバーによるオリジナルの構文解説では、サブリストのインデント、引用・見出し・インデントコードブロックの前の空行、タイトリストとルーズリストの規則、混在したリスト記号、ブロック要素とインライン要素の優先順位といったエッジケースが規定されていなかった。[5][6] 初期の実装者は`Markdown.pl`を参照したが、同スクリプトにはバグがあり2004年12月17日以降更新されていなかった。[5] その後の10年間で複数のプログラミング言語による数十の実装が分岐し、GitHubのWikiやPandocといったシステム間で同一文書が構文エラーを出さずに異なる表示となる事態が生じた。[5][6] 初期のテストスイートであるMDTestは陳腐化し、BabelMark 2およびBabelmark 3が20以上の実装の出力を比較するために用いられた。[5][7]

CommonMarkの取り組みは2014年にジョン・マクファーレン（Pandoc）、David Greenspan（Meteor）、Vicent Marti（GitHub）、Neil Williams（Reddit）、Benjamin Dumke-von der Ehe（Stack Overflow / Stack Exchange）、ジェフ・アトウッド（Discourse）によって開始された。[5][7] 仕様書は`pandoc`、`peg-markdown`、`lunamark`の保守経験を持つジョン・マクファーレンが執筆し、強調・リンク・画像に関してKārlis Gaņģisが貢献した。[7] 2026-11-23時点で、`commonmark.org`は現在のメンテナーとしてジョン・マクファーレン、Martin Woodward（GitHub）、ジェフ・アトウッドを掲載している。[5]

CommonMarkは、人間の執筆者の視点から構造要素を宣言的に記述した`spec.txt`として執筆されている。[7] すべてのUnicodeコードポイント列は有効なCommonMark文書を構成し、セキュリティのため`U+0000`はUnicode置換文字`U+FFFD`に置き換えられる。[6] 空白がブロック構造を定義する箇所ではタブは4文字のタブストップとして扱われ、内部のタブはそのまま保持される。[6] CommonMarkは2段階の構文解析モデルを定義しており、第1段階でブロック構造（見出し、段落、主題区切り、コードブロック、HTMLブロック、リンク参照定義などのリーフブロックと、引用やリストなどのコンテナブロック）を解決し、第2段階でインライン構造を解決する。この際、ブロック構造の指示子は常にインライン指示子より優先される。[6]

CommonMarkで文書化されたオリジナルMarkdownからの主な変更点には、すべてのASCII記号に対するバックスラッシュエスケープの許可、行末バックスラッシュによる強制改行の追加、インラインリンクおよび参照リンク双方でのシングルクォート囲みリンクタイトルの許可、高コストなバックトラッキングを避けるHTMLブロック規則の改訂、空行で区切られた`>`ブロックを別々の引用として維持する仕様、箇条書き記号や順序付きリストの区切り文字変更時に新しいリストを開始する規則、順序付きリストの開始番号の保持、バッククォートまたはチルダによるフェンスドコードブロックのサポートが含まれる。[7] 仕様リポジトリ（`github.com/commonmark/commonmark-spec`）には、`test/spec_tests.py`で実行でき`commonmark-spec` npmパッケージ経由でJSONとして出力可能な500件以上のMarkdown・HTML並列適合性テストが組み込まれており、さらにBSDライセンスのC（`cmark`）およびJavaScript（`commonmark.js`）によるリファレンス実装が提供されている。[7] 2026-11-23時点で、`commonmark.org`はCommonMarkを採用したサイトおよびプロジェクトとしてDiscourse、GitHub、GitLab、Reddit、Qt、Stack Overflow / Stack Exchange、Swiftを挙げている。[5]

## GitHub Flavored Markdown（GFM）

GitHub Flavored Markdown（GFM）は、GitHub.comおよびGitHub Enterprise上のユーザーコンテンツでサポートされているMarkdown方言である。[6] 2026-11-23時点で、公式なGFM仕様はジョン・マクファーレンのCommonMark仕様に基づく2019年4月6日付のバージョン0.29-gfmである。[6] GFMはCommonMarkの厳密なスーパーセットとして定義されており、CommonMarkの2段階ブロック・インライン解析モデルを維持しつつ、GitHubのユーザーコンテンツ向け拡張を規定している。[6]

GFM仕様はCommonMarkを超える5つの公式拡張を定めている。[6]

- テーブル（第4.10節）：構造化されたリーフブロックの表構文を追加
- タスクリスト項目（第5.3節）：チェックリスト向けにコンテナリスト項目を拡張
- 取り消し線（第6.5節）：インラインの削除テキスト書式を追加
- オートリンク拡張（第6.9節）：基本のCommonMarkオートリンクを超えて自動リンク認識を拡張
- 禁止生HTML（第6.11節）：レンダリング時に特定の生HTMLタグをフィルタリング

GFM入力がHTMLに変換された後、GitHub.comおよびGitHub Enterpriseはプラットフォーム全体でのセキュリティと表示の一貫性を保つため、追加の後処理とサニタイズを実施する。[6] また、GitHub-Flavored MarkdownはRFC 7764に収録された8つのバリアント登録テンプレートにも含まれている。[2]

## 出版とllms.txtにおけるMarkdownの活用

MarkdownはReddit、Stack Overflow、GitHub、GitLab、Discourseといった主要Webプラットフォームで利用されているほか、Web外でも書籍、記事、スライドショー、書簡、講義ノート、学術執筆、脚本（Fountain経由）、数式、IETFインターネットドラフトやRFC（`kramdown-rfc2629`および`rfc7328`）の作成に使われている。[1][2][5][6]

AIおよびWebドキュメントのワークフローにおいて、Markdownはジェレミー・ハワードが2024年9月3日に公開し2026年8月10日にバージョン2へ更新した[llms.txt](https://mimirwiki.com/ja/wiki/llms-txt)提案のフォーマットとして採用されている。[8] 通常のHTMLページは中核情報の周囲にナビゲーション、広告、JavaScriptを含むため、`llms.txt`は`/llms.txt`または`/docs/llms.txt`などのサブパスにMarkdownガイドファイルを配置し、大規模言語モデル（LLM）やAIエージェントへ簡潔な背景情報と精選されたリンクを提供することを提案している。[8] `llms.txt`ファイルは一定のMarkdownセクション順序（任意のバイトオーダーマーク、必須のH1サイトまたはプロジェクト名、任意の引用要約、任意の本文セクション、Markdownリンクリストを含むH2セクション）に従っており、言語モデルだけでなく従来のパーサーや正規表現でも処理できる。[8]

`llms.txt`提案はさらに、個別ページのクリーンなMarkdown版を同一URLに`.md`を付加した形式（`page.html.md`）または拡張子を置換した形式（`page.md`）で提供すること、ディレクトリURLには`index.html.md`または`index.md`を用いることも推奨している。[8] 自動検出を支援するため、`llms.txt` v2ではHTMLの`link`要素またはHTTPの`Link`レスポンスヘッダを用い、ページのMarkdown版には`rel="alternate"`と`type="text/markdown"`（RFC 7763のメディアタイプ）を、対象を包含する`llms.txt`ファイルには`rel="describedby"`を指定することを推奨している。[1][8] 2026年8月時点の`llms.txt` v2の記述によれば、数千のWebサイトが`llms.txt`ファイルを公開しており、MintlifyやGitBookなどのドキュメントプラットフォームがこれを自動生成し、`nbdev`ソフトウェアドキュメントプロジェクト（Answer.AI、fast.ai、FastHTMLのドキュメントを含む）はデフォルトで各ページの`.md`版を生成している。さらにChromeのLighthouseはエージェンティックブラウジング監査に`llms.txt`を組み込んでおり、[OpenAI](https://mimirwiki.com/ja/wiki/openai)、[Anthropic](https://mimirwiki.com/ja/wiki/anthropic)、[Google Gemini](https://mimirwiki.com/ja/wiki/google-gemini)といったAIプロバイダも、[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)や[サイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)といった既存のWeb慣習と並行して開発者向けドキュメント用の`llms.txt`ファイルを公開している。[8]

## よくある質問

### Markdownとは何ですか？

Markdownは、プレーンテキストのまま読みやすさを保ちつつ、HTMLなどの正式なマークアップ言語へ変換できるように設計された軽量マークアップ言語およびプレーンテキスト書式構文です。主にプレーンテキストの電子メールの慣習に着想を得た記号文字を用い、生HTMLをインラインで記述することもできます。 [1][3][4]

### Markdownは誰がいつ作成しましたか？

Markdownは2004年にジョン・グルーバーがアーロン・スワーツの大きな貢献を得て開発しました。グルーバーは2004年12月17日に、オリジナルのPerl製変換ツールMarkdown.plの最終更新版であるMarkdown 1.0.1をBSDスタイルのオープンソースライセンスで公開しました。 [2][3][5]

### Markdownの公式MIMEメディアタイプは何ですか？

Markdownの公式MIMEメディアタイプはtext/markdownであり、2016年3月にIETFの情報提供用RFC 7763によって登録されました。デフォルト値を持たないcharsetパラメータが必須で、大文字・小文字を区別しないUS-ASCII形式のvariantパラメータを任意で指定でき、関連ガイドラインはRFC 7764に記載されています。 [1][2]

### CommonMarkはオリジナルのMarkdownとどのような関係にありますか？

CommonMarkは、ジョン・グルーバーによるオリジナルの解説とMarkdown.plの公開後に生じた構文解析の曖昧さや実装間の差異を解消するため、2014年に開始された明確なMarkdown仕様です。中核となるMarkdown要素を保持しつつ、フェンスドコードブロック、行末バックスラッシュによる強制改行構文、500件以上の適合性テスト例を備えています。 [5][7]

### GitHub Flavored MarkdownはCommonMarkにどのような拡張を追加していますか？

バージョン0.29-gfm（2019-04-06）でCommonMarkの厳密なスーパーセットとして規定されたGitHub Flavored Markdown（GFM）は、テーブル、タスクリスト項目、取り消し線、拡張オートリンク、禁止生HTMLの5つの拡張を追加しています。また、GitHub.comおよびGitHub EnterpriseはGFMをHTMLに変換した後、追加の後処理とサニタイズを行っています。 [6]

### AIエージェント向けのllms.txt提案ではMarkdownがどのように使われていますか？

llms.txt提案では、/llms.txtや/docs/llms.txtなどのサブパスに一定のセクション順序を持つMarkdownファイルを配置し、言語モデルやAIエージェントがサイト概要を読み取って詳細なドキュメントへのリンクをたどれるようにします。さらに、rel="alternate"およびtype="text/markdown"リンクを通じて検出可能な、個別ページのクリーンな.md版を提供する手法も提案しています。 [8]

## 引用できる文

- Markdownは2004年にジョン・グルーバーがアーロン・スワーツの大きな貢献を得て開発した。 [2][5]
- ジョン・グルーバーは2004年12月17日、BSDスタイルのオープンソースライセンスの下で18 KBのPerlスクリプトとしてMarkdown 1.0.1を公開した。 [3]
- オリジナルのMarkdownはインラインの生HTMLに対応しており、HTMLエンティティを保持しつつリテラルの小なり記号とアンパサンドを自動エスケープし、構文の主な着想をプレーンテキストの電子メールから得ている。 [4]
- Internet Engineering Task Force（IETF）が2016年3月に発行したRFC 7763は、必須のcharsetパラメータと任意のvariantパラメータを持つtext/markdownメディアタイプを登録している。 [1]
- RFC 7763の情報提供用コンパニオン文書として2016年3月に発行されたRFC 7764は、MultiMarkdown、GitHub-Flavored Markdown、Pandoc、CommonMarkを含む8つのMarkdownバリアントの登録テンプレートを提供している。 [2]
- 2014年に開始されたCommonMark仕様策定の取り組みは、500件以上の組み込み適合性テスト例に加え、BSDライセンスのC（cmark）およびJavaScript（commonmark.js）によるリファレンス実装を提供している。 [5][7]
- 2019年4月6日付のGitHub Flavored Markdown（GFM）バージョン0.29-gfmはCommonMarkの厳密なスーパーセットであり、テーブル、タスクリスト項目、取り消し線、拡張オートリンク、禁止生HTMLの5つの拡張を規定している。 [6]
- ジェレミー・ハワードが2024年9月3日に公開し2026年8月10日にv2へ更新したllms.txt提案は、言語モデルやAIエージェント向けに/llms.txtのMarkdownファイルとtype="text/markdown"リンク関係で検出される.mdページ版を用いている。 [8]

## 年表

- 2004: ジョン・グルーバーがアーロン・スワーツの大きな貢献を得てMarkdownを開発し、プレーンテキスト書式構文とPerl製変換ツールMarkdown.plを公開した。 [2][3][5]
- 2004-12-17: ジョン・グルーバーがオリジナルのMarkdown.plスクリプトの最終更新版となるMarkdown 1.0.1を公開した。 [3][5]
- 2014: ジョン・マクファーレン、David Greenspan、Vicent Marti、Neil Williams、Benjamin Dumke-von der Ehe、ジェフ・アトウッドがCommonMark仕様策定の取り組みを開始した。 [5][7]
- 2016-03: IETFがtext/markdownメディアタイプを登録する情報提供用RFC 7763と、コンパニオン文書RFC 7764を発行した。 [1][2]
- 2019-04-06: GitHubがCommonMarkに基づくGitHub Flavored Markdown仕様のバージョン0.29-gfmを公開した。 [6]
- 2024-09-03: ジェレミー・ハワードが言語モデルやAIエージェントにWebサイトを案内するためのMarkdownファイルを用いるllms.txt提案を公開した。 [8]
- 2026-08-10: Markdown概要ファイル、.mdページ版、type="text/markdown"リンク関係による検出方法を記述したllms.txt提案のバージョン2がllmstxt.orgで更新された。 [8]

## 出典

1. RFC 7763: The text/markdown Media Type. Internet Engineering Task Force (IETF). 公開 2016-03. https://www.rfc-editor.org/rfc/rfc7763.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. RFC 7764: Guidance on Markdown: Design Philosophies, Stability Strategies, and Select Registrations. Internet Engineering Task Force (IETF). 公開 2016-03. https://www.rfc-editor.org/rfc/rfc7764.txt (閲覧 2026-11-23; tier 1: government or public registry)
3. Daring Fireball: Markdown. Daring Fireball. https://daringfireball.net/projects/markdown/ (閲覧 2026-11-23; tier 3: official site)
4. Daring Fireball: Markdown Syntax Documentation. Daring Fireball. https://daringfireball.net/projects/markdown/syntax (閲覧 2026-11-23; tier 3: official site)
5. CommonMark. CommonMark. https://commonmark.org/ (閲覧 2026-11-23; tier 3: official site)
6. GitHub Flavored Markdown Spec. GitHub. 公開 2019-04-06. https://github.github.com/gfm/ (閲覧 2026-11-23; tier 3: official site)
7. GitHub - commonmark/commonmark-spec: CommonMark spec, with reference implementations in C and JavaScript · GitHub. CommonMark (GitHub). https://github.com/commonmark/commonmark-spec (閲覧 2026-11-23; tier 3: official site)
8. The /llms.txt file, v2 – llms-txt. llmstxt.org. 公開 2024-09-03. https://llmstxt.org/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Markdown." 版 e34755a3, 2026-11-23. https://mimirwiki.com/ja/wiki/markdown
