---
title: "llms.txt"
subtitle: "ウェブサイトの主要コンテンツをAIエージェントへ案内するMarkdownファイルの提案"
canonical_url: https://mimirwiki.com/ja/wiki/llms-txt
language: ja
page_class: anchor
revision_sha256: 2d0dfaa83326d48a73a4db233d1d6c855086aee4c42fa0f39405233fae694391
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/ja/wiki/llms-txt.md
  txt: https://mimirwiki.com/ja/wiki/llms-txt.txt
  json: https://mimirwiki.com/ja/wiki/llms-txt.json
  jsonld: https://mimirwiki.com/ja/wiki/llms-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/llms-txt
  ko: https://mimirwiki.com/ko/wiki/llms-txt
  zh: https://mimirwiki.com/zh/wiki/llms-txt
---

# llms.txt

> llms.txtは、通常/llms.txtに配置するMarkdownファイルを用いて、AIエージェントにウェブサイトの簡潔な概要と主要ページのクリーンなMarkdown版へのリンクを提供するウェブ慣例の提案である。ジェレミー・ハワードが2024年9月3日に公開し、2026年8月にバージョン2をリリースした。コミュニティによる提案であり、ファイルの公開は任意である。

llms.txtは、ウェブサイトがllms.txtという名称のMarkdownファイルを公開し、大規模言語モデル（LLM）やAIエージェントに対してサイトの概要と、より詳細でLLMが扱いやすいコンテンツへのリンクを提供するウェブ慣例の提案である。ジェレミー・ハワード（Jeremy Howard）が2024年9月3日にllmstxt.orgで提案を公開し、2026年8月に第2版であるv2をリリースした。このファイルはサイトのルート（/llms.txt）または任意のサブパスに配置でき、一般的なパーサーで読み取れる固定のセクション順序に従う。llmstxt.orgは、llms.txtをコミュニティからの意見を受け付けている提案として位置づけている。

**別名:** /llms.txt, The /llms.txt file, llms.txt 提案

## 主要な事実

- **初版公開日:** 2024-09-03 [1]
- **現行バージョン:** v2（2026年8月） (時点 2026-11-21) [2]
- **提案者:** ジェレミー・ハワード（Jeremy Howard） [1]
- **必須要素:** プロジェクト名またはサイト名を記したH1見出し1つ [1]
- **配置場所:** サイトルートの/llms.txt、または任意のサブパス [1]

## ファクトシート

- **種別:** LLMおよびAIエージェント向けMarkdown案内ファイルに関するウェブ慣例の提案 [1]
- **提案者:** ジェレミー・ハワード（Jeremy Howard） [1]
- **初版公開日:** 2024-09-03 [1]
- **現行バージョン:** v2（2026年8月） (時点 2026-11-21) [2]
- **ファイル名:** llms.txt [1]
- **配置場所:** サイトルート（/llms.txt）または任意のサブパス（例：/docs/llms.txt） [1]
- **形式:** セクション順序が固定されたMarkdown [1]
- **必須要素:** プロジェクト名またはサイト名を記したH1見出し [1]
- **検出手段:** リンク関係alternate（type text/markdown）およびdescribedby [1]
- **ステータス:** コミュニティの意見を受け付けている提案 [1]
- **リポジトリ:** github.com/AnswerDotAI/llms-txt（Apache-2.0ライセンス） [3]
- **リファレンスツール:** llms_txt2ctxコマンドを含むllms-txt Pythonパッケージ [4]

## llms.txtの概要

llms.txtは、ウェブサイトが大規模言語モデル（LLM）やAIエージェントに対して自サイトのコンテンツを簡潔に案内するために公開する[Markdown](https://mimirwiki.com/ja/wiki/markdown)ファイルの提案である。[1] この提案では、ウェブページは人間の読者向けに設計されており、HTMLページ上ではナビゲーション、広告、スクリプトが本文情報を取り囲んでいるうえ、ほとんどのウェブサイトはモデルのコンテキストウィンドウに収まりきらないほど大きいと論じている。[1] そのため、llms.txtファイルは簡潔な背景説明や案内、より詳細なMarkdownファイルへのリンクを1か所にまとめる役割を担う。[1]

llms.txt提案は2つの要素で構成される。第1は`llms.txt`ファイル自体であり、第2はエージェントが必要とし得る各ページのクリーンなMarkdown版を、元のページと同じURLに`.md`拡張子を付けて提供することである。[1] エージェントはllms.txtファイルを読み込むか検索して必要な項目を見つけ、該当するリンクをたどることで、詳細情報をオンデマンドで取得することが想定されている。[1]

ジェレミー・ハワード（Jeremy Howard）は2024年9月3日にllms.txt提案を公開し、2026年8月にv2と名付けた改訂版をリリースした。[1][2] この提案はGitHubのAnswerDotAI/llms-txtリポジトリにてApache-2.0ライセンスのもとで管理されている。[3] 提案文書によると、llms.txtファイルはソフトウェアのドキュメントで最も多く利用されている。[1]

## llms.txtのファイル形式

llms.txtファイルはMarkdownで記述され、以下の要素を固定の順序で含む。[1]

- 任意のバイトオーダーマーク（BOM）
- プロジェクト名またはサイト名を記したH1見出し（唯一の必須要素）
- プロジェクトの簡潔な要約を記した引用ブロック（blockquote）
- より詳細な情報を保持する、見出し以外の任意の形式による0個以上のMarkdownセクション
- H2見出しで始まり、さらなる詳細へのリンクリストを含む0個以上のセクション

llms.txtのリンクリストにおける各項目は、`[name](url)`形式のMarkdownハイパーリンクであり、任意でコロンとリンク先ファイルに関する注釈を続けることができる。[1] 「Optional」というタイトルのセクションには、より短いコンテキストが必要な場合にエージェントが省略できる補助的なリンクを配置する。v2ではこのセクションに機械的な意味を与えていたツールが提案から除外されたため、これは単なる慣例となっている。[1][2]

提案がXMLのような構造化形式ではなくMarkdownを採用しているのは、ファイルが言語モデルやエージェントによって読まれることを前提としているためである。一方で、固定のレイアウトを持つことから、従来のパーサーや正規表現による処理も可能である。[1]

## llms.txtの配置場所と検出方法

llms.txtファイルはウェブサイトのルートパスである`/llms.txt`、または`/docs/llms.txt`のような任意のサブパスに配置できる。各ファイルはそのパス配下のURLを対象とし、複数のファイルが該当する場合、エージェントは最も具体的なパスにあるファイルを使用することが想定されている。[1] 提案の初版ではサブパスへの配置を許容しつつもその意味を定義していなかったが、v2でこの規則が追加された。[2]

個別ページについては、llms.txt提案は同一URLに`.md`を付加した形式（`page.html.md`）または拡張子を置換した形式（`page.md`）でMarkdown版を提供することを求めている。ファイル名を含まないURLでは`index.html.md`または`index.md`を用いる。[1] 初版では付加する形式のみが規定されていた。[2]

バージョン2では、標準のリンク関係（link relation）による検出方法が追加された。`rel="alternate"`と`type="text/markdown"`を指定したリンクはページのMarkdown版を指し、`rel="describedby"`はそのページを対象とするllms.txtファイルを指す。いずれもHTMLの`link`要素またはHTTPの`Link`ヘッダーとして記述できる。[1][2] リンク関係タイプ`alternate`および`describedby`は、IANAのLink Relationsレジストリに登録されている。[9] また、本提案はRFC 8615で定義された`/.well-known/`パスプレフィックスを使用しない。well-known URIはオリジンのルートにしか配置できない一方、共有ホスト上で特定のパスのみを管理している作成者が多いためである。[1][8]

## llms.txtとrobots.txtおよびsitemap.xmlの違い

llms.txtと[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)は目的が異なる。IETFが2022年9月にRFC 9309として公開したロボット排除プロトコル（Robots Exclusion Protocol）は、サービス所有者がクローラーによるコンテンツへのアクセス方法を制御するための仕組みである。[7] llms.txt提案はアクセス制御をrobots.txtに委ね、自身の内容については、エージェントがユーザーを支援する際にあるトピックの情報を必要としたときにオンデマンドで利用する情報であると位置づけている。[1]

また、llms.txtはサイト内のインデックス可能な人間向けページを網羅的に列挙する[サイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)（sitemap）とも異なる。提案では、サイトマップがllms.txtの代替にならない理由として3点を挙げている。すなわち、LLMが読み取りやすい版のページが記載されていないことが多い点、外部サイトのURLを含まない点、そしてサイトマップが対象とする文書全体は通常コンテキストウィンドウに対して大きすぎる点である。[1] これに対し、llms.txtは厳選された概要（curated overview）として位置づけられている。[1]

提案者は、llms.txtはモデルの学習ではなく、推論時（質問に回答する時点）での利用に主に役立つと想定していたと述べており、v2の文書でも実際にそのように使われてきたと報告している。[1]

## llms.txtの導入状況とツール

提案者自身が執筆したllms.txt提案のv2文書によると、数千のサイトがllms.txtファイルを公開しており、OpenAI、Anthropic、およびGoogleのGemini APIがそれぞれの開発者向けドキュメント用にllms.txtを公開している。[1] ファイルを自動生成できるプラットフォームやプラグインの例としては、Mintlify、GitBook、Yoast SEO、AIOSEO、Wixが挙げられている。[1]

Mintlifyのドキュメントでは、すべてのドキュメントプロジェクトのルートにllms.txtファイルをホストするとともに、`llms-full.txt`という名称のファイルも生成していると説明している。[10] `llms-full.txt`という名称はこうしたプラットフォームに由来するものであり、llmstxt.orgの提案には登場しない。[1][10] 公開事例の1つとして、[Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol)のドキュメントサイトが`modelcontextprotocol.io/llms.txt`でページのインデックスを提供している。[11]

llmstxt.orgのサイトには、`llms-txt`というPythonパッケージと、llms.txtファイルを解析してXML形式のコンテキストファイルを生成するコマンドラインツール`llms_txt2ctx`が記載されている。[4] 提案の初版ではこのツールが説明されていたが、v2ではコンテキスト展開は提案本体の一部ではなくなった。[2]

## llms.txtの位置づけと限界

llms.txtは提案段階にある。llmstxt.orgは仕様がコミュニティの意見を受け付けている状態であると説明し、その非公式な概要を公開GitHubリポジトリで管理している。[1] 2026年5月5日に最終更新されたChromeのLighthouseドキュメントは、llms.txtを新たな慣例（emerging convention）と呼んでいる。Lighthouseはファイルの提供が任意であるため、サイトが当該ファイルに対して404を返した場合にはllms.txt監査を「該当なし」とし、取得時にサーバーエラーが発生した場合にのみページにフラグを立てる。[5]

llms.txtの公開は、GoogleのAI検索機能に表示されるための要件ではない。2025年12月10日に最終更新されたGoogle 検索セントラルのドキュメントは、AI による概要（AI Overviews）やAI モード（AI Mode）に表示させるために、新たな機械可読ファイルやAI向けテキストファイルを作成する必要はないと明記している。[6]

llms.txtは既存のウェブ慣例を置き換えるものではない。クローラーのアクセス権限の設定は引き続きrobots.txtの役割であり、llms.txtはサイトマップのような網羅的なページインデックスでもない。[1][7] 一方で提案では、llms.txtファイル内でサイトが使用している構造化データマークアップに言及することで、モデルがそのマークアップを文脈に沿って解釈する助けにできると述べている。[1]

## よくある質問

### llms.txtとは何ですか？

llms.txtは、ウェブサイトがAIエージェントに対してサイトの簡潔な概要と、より詳細なコンテンツへのリンクを提供するために公開するMarkdownファイルの提案です。ジェレミー・ハワードが2024年9月3日に公開しました。 [1]

### llms.txtファイルはどこに配置しますか？

ルートパスの/llms.txt、または/docs/llms.txtなどの任意のサブパスに配置します。各ファイルはそのパス配下のURLを対象とし、複数のファイルが存在する場合は最も具体的なパスにあるファイルが適用されます。 [1]

### llms.txtは公式のウェブ標準ですか？

llmstxt.orgはllms.txtをコミュニティからの意見を受け付けている提案であると説明しています。2026年5月5日に最終更新されたChromeのLighthouseドキュメントでも、新たな慣例と呼び、ファイルの提供は任意として扱っています。 [1][5]

### llms.txtはrobots.txtとどう異なりますか？

RFC 9309で規定されているrobots.txtは、クローラーに対してサイトへのどのアクセスが許容されるかを指示します。llms.txtは権限を設定するものではなく、エージェントがオンデマンドで読み込み、サイトの主要コンテンツを見つけるための厳選された概要です。 [1][7]

### GoogleのAI による概要やAI モードにllms.txtは必要ですか？

いいえ。2025年12月10日に最終更新されたGoogle 検索セントラルのドキュメントでは、これらの機能に表示されるために新たな機械可読ファイルやAI向けテキストファイルは不要であると述べられています。 [6]

### llms.txt v2では何が変わりましたか？

2026年8月に公開されたバージョン2では、alternateおよびdescribedbyリンク関係による検出方法が追加され、Markdown版ページのURL形式が2種類認められたほか、サブパスに置かれたファイルの適用範囲が定義され、コンテキスト展開ツールが提案から除外されました。 [2]

## 引用できる文

- llms.txt提案は、ジェレミー・ハワードによって2024年9月3日に公開された。 [1]
- llms.txt提案のバージョン2は、2026年8月に公開された。 [2]
- llms.txtファイルで唯一の必須要素は、プロジェクト名またはサイト名を記したH1見出しである。 [1]
- llms.txtファイルはウェブサイトのルートまたは任意のサブパスに配置でき、そのパス配下のURLを対象とする。 [1]
- llms.txt提案のバージョン2は、検出手段としてtype text/markdownを伴うリンク関係alternateと、describedbyを推奨している。 [1]
- 2026年5月5日に最終更新されたChromeのLighthouseドキュメントは、llms.txtファイルの提供を任意としている。 [5]
- Google 検索セントラルのドキュメントは、AI による概要やAI モードに表示されるために新たな機械可読ファイルやAI向けテキストファイルは不要であると述べている。 [6]
- llms.txt提案は、GitHubのAnswerDotAI/llms-txtリポジトリにてApache-2.0ライセンスのもとで管理されている。 [3]

## 年表

- 2024-09-03: ジェレミー・ハワードがllms.txt提案を公開した。 [1]
- 2026-08: llms.txt提案のバージョン2が公開された。 [2]

## 出典

1. The /llms.txt file, v2 – llms-txt. llmstxt.org. 公開 2024-09-03. https://llmstxt.org/ (閲覧 2026-11-21; tier 3: official site)
2. Changes – llms-txt. llmstxt.org. 公開 2026-08. https://llmstxt.org/changes.html (閲覧 2026-11-21; tier 3: official site)
3. GitHub - AnswerDotAI/llms-txt: The /llms.txt file, helping language models use your website. AnswerDotAI (GitHub). https://github.com/AnswerDotAI/llms-txt (閲覧 2026-11-21; tier 3: official site)
4. Python module & CLI – llms-txt. llmstxt.org. https://llmstxt.org/intro.html (閲覧 2026-11-21; tier 3: official site)
5. llms.txt | Lighthouse | Chrome for Developers. Google (Chrome for Developers). 公開 2026-05-05. https://developer.chrome.com/docs/lighthouse/agentic-browsing/llms-txt (閲覧 2026-11-21; tier 3: official site)
6. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. 公開 2025-12-10. https://developers.google.com/search/docs/appearance/ai-features (閲覧 2026-11-21; tier 3: official site)
7. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (閲覧 2026-11-21; tier 1: government or public registry)
8. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 公開 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (閲覧 2026-11-21; tier 1: government or public registry)
9. Link Relations. Internet Assigned Numbers Authority (IANA). 公開 2026-06-12. https://www.iana.org/assignments/link-relations/link-relations.xhtml (閲覧 2026-11-21; tier 1: government or public registry)
10. llms.txt - Mintlify. Mintlify. https://www.mintlify.com/docs/ai/llmstxt (閲覧 2026-11-21; tier 3: official site)
11. Model Context Protocol (llms.txt documentation index). Model Context Protocol project. https://modelcontextprotocol.io/llms.txt (閲覧 2026-11-21; tier 3: official site)

## このページを引用する

Mimirwiki. "llms.txt." 版 2d0dfaa8, 2026-11-21. https://mimirwiki.com/ja/wiki/llms-txt
