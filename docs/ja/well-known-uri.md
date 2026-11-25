---
title: "Well-Known URI"
subtitle: "オリジン全体のメタデータおよびサービス探索のために /.well-known/ パス接頭辞を予約するIETF標準"
canonical_url: https://mimirwiki.com/ja/wiki/well-known-uri
language: ja
page_class: anchor
revision_sha256: 11a2ce700e9944b852891ba6956f4d69af75a11e01c098ca76b69e1ceb4fc248
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/ja/wiki/well-known-uri.md
  txt: https://mimirwiki.com/ja/wiki/well-known-uri.txt
  json: https://mimirwiki.com/ja/wiki/well-known-uri.json
  jsonld: https://mimirwiki.com/ja/wiki/well-known-uri.jsonld
translations:
  en: https://mimirwiki.com/wiki/well-known-uri
  ko: https://mimirwiki.com/ko/wiki/well-known-uri
  zh: https://mimirwiki.com/zh/wiki/well-known-uri
  es: https://mimirwiki.com/es/wiki/well-known-uri
---

# Well-Known URI

> Well-Known URIは、オリジン全体のメタデータおよびサービス探索のためにパスが /.well-known/ で始まるUniform Resource Identifierである。RFC 5785を廃止して2019年5月に発行されたIETF RFC 8615で規定され、HTTP、HTTPS、WS、WSSに適用される。IANAがSpecification Requiredポリシーのもとでレジストリを管理しており、security.txt、acme-challenge、openid-configurationなどのサフィックスが登録されている。

Well-Known URIは、HTTP、HTTPS、WS、WSSなどサポートが明示的に定義されたURIスキームにおいて、パス構成要素が予約接頭辞 /.well-known/ で始まるUniform Resource Identifier（URI）である。Internet Engineering Task Force（IETF）が2019年5月にRFC 8615として発行した本仕様は、RFC 5785（2010年4月）を廃止し、パス衝突を回避しながらオリジン全体のメタデータおよびプロトコル探索のための予測可能な配置場所を標準化している。Internet Assigned Numbers Authority（IANA）は、指定専門家（Designated Expert）のレビューを伴うSpecification RequiredポリシーのもとでWell-Known URIsレジストリを管理しており、security.txt、acme-challenge、oauth-authorization-server、oauth-protected-resource、openid-configurationといったpermanentおよびprovisionalのサフィックスを掲載している。Well-Known URIはオリジンのパス階層の最上位にのみ適用され、各アプリケーションが独自のメタデータ形式、メディアタイプ、および適用範囲を定義する。

**別名:** Well-Known URIs, ウェルノウンURI, /.well-known/, Well-Known Uniform Resource Identifiers, RFC 8615, RFC 5785, .well-known

## 主要な事実

- **現行仕様:** RFC 8615（2019年5月、Standards Track） (時点 2026-11-23) [1]
- **予約パス接頭辞:** オリジンルート上の /.well-known/ [1]
- **旧仕様:** RFC 5785（2010年4月、RFC 8615により廃止） [2]
- **レジストリ:** IANA Well-Known URIs（2010-01-20作成、2026-10-26更新） (時点 2026-11-23) [3]
- **登録ポリシー:** 指定専門家レビューを伴うSpecification Required（RFC 8126） [1]

## ファクトシート

- **種別:** 予約済みURIパス接頭辞に関するインターネット標準 [1]
- **パス接頭辞:** /.well-known/ [1]
- **現行仕様:** RFC 8615（2019年5月、Standards Track） (時点 2026-11-23) [1]
- **著者（RFC 8615）:** Mark Nottingham [1]
- **廃止した仕様:** RFC 5785（2010年4月、Mark Nottingham・E. Hammer-Lahav） [2]
- **更新した仕様:** RFC 7230およびRFC 7595 [1]
- **対応URIスキーム:** http、https、ws、wss、およびサポートを明示的に定義したその他のスキーム [1]
- **レジストリ:** IANA Well-Known URIs（iana.org/assignments/well-known-uris） [3]
- **レジストリの状況:** 2010-01-20作成、2026-10-26最終更新 (時点 2026-11-23) [3]
- **登録ポリシー:** Specification Required（仕様必須） [3]
- **指定専門家:** Mark Nottingham (時点 2026-11-23) [3]
- **サフィックス構文:** RFC 3986 segment-nz（/ 文字不可） [1]

## Well-Known URIの概要

Well-Known URIは、Well-Knownな配置場所をサポートすることが明示的に定義されたURIスキームにおいて、パス構成要素が `/.well-known/` で始まるUniform Resource Identifierである。[1] Internet Engineering Task Force（IETF）は、Mark Nottinghamが執筆した現行のStandards Track仕様であるRFC 8615を2019年5月に発行した。[1] RFC 8615は、Mark NottinghamおよびE. Hammer-Lahavが2010年4月に発行し、`/.well-known/` パス接頭辞とInternet Assigned Numbers Authority（IANA）のレジストリを創設したRFC 5785を廃止している。[1][2] またRFC 8615は、`http` および `https` URIにおける接頭辞を予約するためRFC 7230を更新し、IANA URI SchemesレジストリでWell-Known URIをサポートするスキームを記録するためRFC 7595も更新している。[1]

Webアプリケーションでは、[ロボット排除プロトコル](https://mimirwiki.com/ja/wiki/robots-txt)（Robots Exclusion Protocol）やPlatform for Privacy Preferences（P3P）に見られるように、リクエストを送信する前にオリジン全体に関するサイト単位のメタデータを探索する必要が頻繁に生じる。[1][2] こうした場面において、HTTPヘッダフィールドやWebDAV PROPFINDといったリソース単位のメタデータ機構は、クライアント側の体感遅延や導入上の困難を招く場合がある。[1][2] さらにHTTPは、ホスト上のリソースを特定する必要がある非Webプロトコルの基盤としても利用されている。[1] サイトルートに任意の固定パスを割り当てる方式は、他のプロトコル用パスやオリジン自身が作成したリソースとの衝突リスクを生み、オリジン自身のURI空間に対する管理権を侵害する。[1]

単一の `/.well-known/` 接頭辞を予約することで、プロトコル定義の探索用ロケーションを分離し、IANAを通じたサフィックス登録を仕様に義務付けることで命名衝突を防止している。[1][2] `http` および `https` に加え、RFC 8615はRFC 8307によって更新されたWebSocket（`ws`）およびSecure WebSocket（`wss`）のURIに対しても `/.well-known/` を予約しており、その他のURIスキームもスキーム定義で明示的に許可すればWell-Known URIを採用できる。[1] RFC 5785は、複数回のラウンドトリップやリソース単位の確認が非現実的な状況で、サイト全体のポリシー情報やメタデータを直接公開するか他のURIへリンクする目的でWell-Known URIが創設されたと述べており、一般的な情報検索や大規模なURI名前空間は意図された適用範囲外としている。[2]

## Well-Known URIの構文とスコープ規則

Well-Known URIは、RFC 8615で定義された厳格な構文および構造上の制約に従う。[1] アプリケーションが `http://www.example.com/` 上で `example` というサフィックスを登録した場合、対応するWell-Known URIは `http://www.example.com/.well-known/example` となる。[1] 登録されるすべてのサフィックスはRFC 3986の `segment-nz` 生成規則に準拠しなければならず、登録名自体に `/` 文字を含めることは禁止されている。[1] RFC 8615は、アプリケーションに対して具体的な名称を選択するよう助言し、汎用的な語句の登録を避けるよう推奨しており、`metadata` よりも `example-metadata` や `example.com-metadata` のような名称を望ましい例として挙げている。[1]

登録申請では、そのURIを逆参照して取得されるリソースの形式、関連するメディアタイプ、および適用対象のURIスキームを定義した仕様を参照する必要がある。[1] 登録時にURIスキームが明示されていない場合は、`http` および `https` が前提とされる。[1] 仕様が代替ポートを明示的に指定していない限り、アプリケーションはそのスキームのデフォルトポートを使用する。[1] また登録には、追加のパス構成要素、クエリ文字列、フラグメント識別子の構文や、HTTPメソッドの処理といったプロトコル固有の動作を含めることもできる。[1]

RFC 8615はベースパスである `/.well-known/` 自体の形式やメディアタイプを未定義としており、クライアントはその場所にリソースが存在すると想定してはならない。[1] Well-Known URIはURIのパス階層の最上位に厳密に配置される。たとえばルートから始まる `/.well-known/example` のようなパスはWell-Known URIに該当するが、`/foo/.well-known/example` のようなネストされたパスは該当しない。[1] RFC 8615は、ホスト名の決定方法およびWell-Known URIから取得したメタデータの適用範囲を、個々のアプリケーション仕様の定義に委ねている。[1]

## IANA Well-Known URIsレジストリと登録ポリシー

Well-Known URIでは、アプリケーションが `/.well-known/` 配下に新しいサフィックスを設ける前に、IANAのWell-Known URIsレジストリへ登録することが求められる。[1] RFC 5785によって設立され2010-01-20に作成されたこのレジストリは、ICANNとの契約のもとでIETFプロトコルパラメータ名前空間を調整し、割り当ての衝突を防いで相互運用性を支えるIANAによって管理されている。[2][3][8] 2026-11-23時点で、レジストリのページは最終更新日を2026-10-26と記録し、指定専門家としてMark Nottinghamを記載しており、XML、HTML、TXT、CSV形式でのダウンロードを提供している。[3]

RFC 8615のもとでは、登録はRFC 8126（BCP 26、2017年6月発行、RFC 5226を廃止）で定義されたSpecification Requiredポリシーに従い、1名以上の指定専門家（Designated Expert）の助言に基づく承認を必要とする。[1][3][8] 申請はIANAレジストリのインターフェース、または `wellknown-uri-review@ietf.org` メーリングリスト宛ての電子メールで提出される。[1][3] RFC 5785が当初レビュー手続きを策定した際には、指定専門家に対して14日間のレビュー目標期間を設定し、21日経過しても未解決の申請は `iesg@iesg.org` を通じてInternet Engineering Steering Group（IESG）へエスカレーションできると規定していた。[2]

RFC 8615は、各登録申請に4つの必須項目と任意の関連情報を含めることを求めている。[1]

- **URI suffix**：`/.well-known/` に対する相対的な名称
- **Change controller**：Standards Track RFCの場合は `IETF`、その他の仕様の場合は責任主体
- **Specification document(s)**：定義仕様への参照（取得可能なURIを含むことが望ましい）
- **Status**：`permanent` または `provisional` のいずれか
- **Related information**（任意）：追加文書への引用

RFC 8615は、RFC 5785で当初定義されていた4項目のテンプレートにステータスの区別を追加した。[1][2] Standards Track RFCおよびその他のオープン標準（RFC 2026 Section 7.1.1に基づく）で定義された値には `permanent` ステータスが付与されるほか、専門家は対象URIスキームを管轄するコミュニティ（通常は関連ワーキンググループのメーリングリストまたは `art@ietf.org`）に照会したうえで、実際に利用されていることが確認された他の値にも `permanent` ステータスを付与できる。[1] それ以外のエントリには `provisional` ステータスが付与され、専門家は普及状況に応じて後から `permanent` へ昇格させたり、利用されていない場合はコミュニティと協議して削除したりできる。[1] また、参照仕様が存在する場合には、広く展開されている未登録のサフィックスを専門家やその他の第三者が登録することも認められている。[1] 2026-10-26時点で、IANAレジストリの表では廃止・非推奨となったエントリも `deprecated`（`privacy-sandbox-attestations.json`、`related-website-set.json`、`tpcd` など）や `obsoleted`（`http-opportunistic`、`mud` など）として明記されている。[3]

## 主な登録済みWell-Known URIサフィックス

Well-Known URIは、IETF、W3C、OpenID Foundation、OASIS、ETSIなどの標準化団体にわたり、セキュリティ脆弱性の開示、自動証明書発行、アイデンティティおよび認可メタデータ、プロトコル探索を支えている。[3] IANAレジストリにおける5つのpermanentサフィックスが、セキュリティ開示、証明書自動化、およびアイデンティティ・認可探索を担っている。[3]

| URIサフィックス | 定義仕様 | ステータス | 変更管理者 | 登録日 |
| --- | --- | --- | --- | --- |
| `openid-configuration` | OpenID Connect Discovery 1.0 | permanent | OpenID Foundation Artifact Binding Working Group | 2013-08-27 |
| `acme-challenge` | RFC 8555, Section 8.3 | permanent | IETF | 2016-08-18 |
| `oauth-authorization-server` | RFC 8414, Section 3 | permanent | IESG | 2018-03-27 |
| `security.txt` | RFC 9116 | permanent | IETF | 2021-07-13 |
| `oauth-protected-resource` | RFC 9728, Section 3 | permanent | IETF | 2024-10-22 |

`security.txt` は、E. FoudilとY. ShafranovichによるRFC 9116（Informational、2022年4月）で規定されており、組織がセキュリティ研究者向けに脆弱性開示方針や報告窓口を公開するための機械可読なプレーンテキストファイルを定義している。[4] この形式は行単位のキー・値フィールド（`Contact`、`Expires`、`Encryption`、`Canonical`、`Policy`、`Acknowledgments`、`Preferred-Languages`、`Hiring` など）を用い、`#` によるコメントをサポートするとともに、ファイルの配置場所を認証するため `Canonical` フィールドと組み合わせたOpenPGPクリアテキスト署名（RFC 4880）を推奨している。[4]

`acme-challenge` は、RFC 8555（Standards Track、2019年3月）のもとで登録され、Automatic Certificate Management Environment（ACME）プロトコルが定義するHTTPチャレンジを支える。[3][5] ACMEは、認証局と申請者の間で行われるドメイン検証（DV）X.509証明書のドメイン管理権確認、ならびに証明書の発行および失効を自動化し、場当たり的な手動検証手順を置き換えるものである。[5]

関連する3つのサフィックスが、[OAuth](https://mimirwiki.com/ja/wiki/oauth) 2.0およびOpenID Connectの探索を担っている。`openid-configuration` はOpenID Connect Discovery 1.0（2014年2月に最終化、2023-12-15にerrata set 2を公開）で定義され、任意でWebFinger（RFC 7033）による発行者探索を行った後、OpenIDプロバイダの設定およびOAuth 2.0エンドポイントの場所を含むJSON文書を公開する。[3][9] `oauth-authorization-server` はRFC 8414（Standards Track、2018年6月）で規定され、そのJSONメタデータ形式をOAuth 2.0認可サーバ向けに一般化して、`issuer`、`authorization_endpoint`、`token_endpoint`、`jwks_uri`、`scopes_supported`、`response_types_supported` などのフィールドをHTTPS経由または署名付きJSON Web Token（JWT）内で通知する。[3][6] `oauth-protected-resource` はRFC 9728（Standards Track、2025年4月）で規定され、各リソース識別子から決定論的に導出されるOAuth 2.0保護リソース向けの並列的なJSONメタデータ文書（`resource`、`authorization_servers`、`jwks_uri`、`scopes_supported`、`bearer_methods_supported` を通知）を提供し、リソースサーバが `WWW-Authenticate` ヘッダを通じてメタデータURLを通知できるようにしている。[3][7]

2026-10-26時点で、IANAレジストリにはこのほかにも、`webfinger`（RFC 7033）、`caldav` および `carddav`（RFC 6764）、`host-meta` および `host-meta.json`（RFC 6415）、`assetlinks.json`（Google Inc.）、`pki-validation`（CA/Browser Forum）、`mta-sts.txt`（RFC 8461）、`jmap`（RFC 8620）、`sbom`（RFC 9472）、`api-catalog`（RFC 9727）、`agent-card.json`（Linux Foundation）、`webauthn`（W3C）といったpermanentエントリに加え、`gpc.json`、`change-password`、`did.json`、`tdmrep.json` などのprovisionalエントリが含まれている。[3]

## Well-Known URIのセキュリティ上の考慮事項

Well-Known URIは、`/.well-known/` 配下のリソースが事実上オリジン全体を代表するため、プロトコル設計者とサーバ運用者の双方にセキュリティ上の考慮事項をもたらす。[1] RFC 8615は、機密データの露出、サービス拒否（DoS）攻撃、サーバおよびクライアントの認証失敗、DNSリバインディング攻撃、そして制限されたサーバアクセス権を悪用して攻撃者がWell-Known URIの提供内容を改ざんするシナリオといった一般的な脅威を挙げている。[1] サーバ運用者は、特に複数の主体が同居する共有オリジンにおいて、サーバ設定とローカルファイルシステム権限の双方を通じてWell-Knownロケーションへの書き込みアクセスを制限しなければならない。[1] またRFC 8615は、ドットで始まるディレクトリを非表示にするオペレーティングシステムでは、`.well-known` ディレクトリ内部の不正な変更が管理者から見えにくくなる点も指摘している。[1]

`http` および `https` URIの場合、Well-KnownリソースはWebブラウザからアクセス可能であり、Cookie（RFC 6265）、Web Storage、および同一オリジン上の他パスから読み込まれたスクリプトとオリジンセキュリティ境界を共有する。[1] オリジン上の別の箇所にあるクロスサイトスクリプティング（XSS）脆弱性を悪用した攻撃者は、Well-Knownリソースに対して任意のリクエストを送信できる。[1] RFC 8615は、ブラウザからアクセス可能なWell-Knownエンドポイントに対して次の緩和策と実践指針を挙げている。[1]

- 機密情報を暗号化し、ブラウザ経由の圧縮プロービングを防ぐため認証トークンやパスワードなどの機密値に対する圧縮を避けること
- 同一オリジン上の他のアプリケーションとの衝突を避けるためCookie名などの識別子を柔軟に設計し、`HttpOnly` および `Path` のCookie属性を設定すること
- `X-Content-Type-Options: nosniff` を送信し、アプリケーション固有の `Content-Type` メディアタイプを強制するとともに、`Content-Security-Policy` および `Referrer-Policy` ヘッダを適用すること

アプリケーション仕様は、オリジンをまたぐ境界の混同を防ぐため、探索規則とメタデータの適用範囲の双方を明示的に定義しなければならない。[1] RFC 8615は、`https://example.com/.well-known/example` から取得したメタデータを `https://department.example.com`、`https://www.example.com`、`https://www.example.com:8000` といった別のホストやポートに適用すると、実際には存在しない管理関係を前提とすることになり、攻撃者に制御権を与えかねないと警告している。[1] 同様に、あるホスト名上のWell-Known HTTPS URIを使って電子メールなど別のサービスをブートストラップすると、そのURIを実装していないWebサーバに対して大量の不要なHTTPリクエストが発生し、サービス拒否攻撃に類似した状況を引き起こす恐れがある。[1]

## Well-Known URIのオリジンルート制約とllms.txt

Well-Known URIはRFC 8615のもとでオリジンのパス階層のルートに厳密に束縛されており、`/foo/.well-known/example` のようなネストされたパスはWell-Known URIに該当しない。[1] このオリジン単位の制約は `/robots.txt` や `/sitemap.xml`（[サイトマップ](https://mimirwiki.com/ja/wiki/sitemaps)を参照）のようなサイト全体の探索ファイルとは整合するものの、ディレクトリ単位のメタデータや共有ホスト上での公開を必要とする規約にとっては実務上の制約となる。[1][10]

Jeremy Howardが2024-09-03に公開し、2026-08-10にv2へ改訂した [llms.txt](https://mimirwiki.com/ja/wiki/llms-txt) 提案は、この設計上のトレードオフを象徴している。[10] llms.txtは、`llms.txt` という名前のMarkdown概要ファイルをサイトルート（`/llms.txt`）または任意のサブパス（`/docs/llms.txt` など）に配置することを定めており、各ファイルは自身のディレクトリ配下のURLを対象とし、複数のファイルが存在する場合にエージェントは最も具体的なパスのファイルを適用する。[10] プログラム的な探索のために、llms.txt v2はHTMLの `link` 要素またはHTTPの `Link` ヘッダで配信される標準のリンク関係（Markdown版ページ用の `type="text/markdown"` を伴う `rel="alternate"`、および管轄する `llms.txt` ファイル用の `rel="describedby"`）を推奨している。[10]

既存標準を論じるなかで、llms.txt仕様はそのサブパスモデルをRFC 8615のWell-Known URIと明示的に対比している。[10] Well-Known URIはオリジンルートにのみ存在するため、共有ホスト（GitHub Pagesのプロジェクトサイトなど）上でサブディレクトリのみを管理する作成者は、自身のディレクトリにファイルを公開できてもホストの `/.well-known/` 空間にエントリを追加することはできない。[10] 任意のパスで `index.html` のように機能することで、`llms.txt` はあるパスへの書き込み権限を持つあらゆる公開者がサイトの特定セクションを記述できるようにしており、単一のオリジンルート上の場所では表現できないパス単位のスコープを実現している。[10]

## よくある質問

### Well-Known URIとは何ですか？

Well-Known URIは、HTTP、HTTPS、WS、WSSなどサポートが明示的に定義されたURIスキームにおいて、パスが /.well-known/ で始まるUniform Resource Identifierです。IETF RFC 8615で規定されており、オリジン独自のURI空間との衝突を避けながら、オリジン全体のメタデータおよびサービス探索のための標準化された場所を提供します。 [1]

### RFC 8615はRFC 5785とどのように異なりますか？

RFC 8615（2019年5月）はRFC 5785（2010年4月）を廃止し、httpおよびhttpsスキーム向けにRFC 7230を更新するとともに、IANA URI SchemesレジストリでWell-Known URI対応スキームを管理できるようRFC 7595を更新しました。また、permanentおよびprovisionalの登録ステータスを追加し、オリジンルートへのパス制限を明記したほか、ブラウザとの相互作用、スコープ設定、隠しディレクトリに関するセキュリティ指針を拡充しています。 [1][2]

### 新しいWell-Known URIサフィックスはどのように登録されますか？

アプリケーションは、RFC 8126のSpecification Requiredポリシーに基づき、指定専門家（Designated Expert）のレビューを経てIANAのWell-Known URIsレジストリに新しいサフィックスを登録する必要があります。申請はIANAレジストリのインターフェースまたは wellknown-uri-review@ietf.org メーリングリストから提出し、URIサフィックス、変更管理者、定義仕様文書、およびpermanentまたはprovisionalのステータスを含める必要があります。 [1][3][8]

### 主な登録済みWell-Known URIサフィックスにはどのようなものがありますか？

IANAレジストリのpermanentサフィックスには、脆弱性開示向けの security.txt（RFC 9116）、証明書発行時の自動ドメイン検証向けの acme-challenge（RFC 8555）、OAuth 2.0メタデータ向けの oauth-authorization-server（RFC 8414）および oauth-protected-resource（RFC 9728）、OpenID Connect Discovery 1.0向けの openid-configuration などがあります。 [3][4][5][6][7][9]

### Well-Known URIを /app/.well-known/ のようなサブディレクトリに配置できますか？

いいえ、できません。RFC 8615では、Well-Known URIはパス階層の最上位に厳密に配置される必要があるため、/.well-known/example はWell-Known URIとして有効ですが、/foo/.well-known/example のようなネストされたパスは該当しません。 [1]

### なぜllms.txt提案は /.well-known/ の外にファイルを配置するのですか？

llms.txt仕様では、RFC 8615がWell-Known URIをオリジンルートに限定しているため、GitHub Pagesのような共有ホスト上でサブディレクトリのみを管理する作成者が /.well-known/ 配下に公開できないと説明しています。ルートまたは任意のサブパスに llms.txt を配置することで、index.html と同様に各ファイルが自身のディレクトリを記述できるようになります。 [1][10]

## 引用できる文

- Mark Nottinghamが執筆し2019年5月に発行されたIETF RFC 8615は、/.well-known/パス接頭辞を定義し、RFC 5785を廃止した。 [1][2]
- RFC 8615はHTTP、HTTPS、WS、WSSの各URIで/.well-known/を予約し、RFC 7230およびRFC 7595を更新している。 [1]
- Well-Known URIはオリジンのパス階層の最上位に限定されており、登録されるサフィックスはスラッシュ文字を含まないRFC 3986のsegment-nz構文に準拠しなければならない。 [1]
- IANAのWell-Known URIsレジストリは2010-01-20に作成され、RFC 8126のSpecification Requiredポリシーおよび指定専門家（Designated Expert）によるレビューのもとで運用されている。 [1][3][8]
- 2026-11-23時点で、IANAのWell-Known URIsレジストリは最終更新日を2026-10-26と記録し、Mark Nottinghamを指定専門家として記載している。 [3]
- security.txtサフィックス（RFC 9116）は2021-07-13にpermanentとして登録され、acme-challengeサフィックス（RFC 8555、Section 8.3）は2016-08-18にpermanentとして登録された。 [3][4][5]
- IANAレジストリには、openid-configuration（2013-08-27）、oauth-authorization-server（2018-03-27、RFC 8414）、およびoauth-protected-resource（2024-10-22、RFC 9728）がpermanentサフィックスとして記録されている。 [3][6][7][9]
- llms.txt提案は、Well-Known URIがオリジンルートにしか配置できず共有ホスト上のサブパスのみを管理する作成者が公開できないため、/.well-known/接頭辞を採用していない。 [1][10]

## 年表

- 2010-01-20: IANAがWell-Known URIsレジストリを作成した。 [3]
- 2010-04: IETFがMark NottinghamおよびE. Hammer-Lahavの執筆によるRFC 5785を発行し、/.well-known/ パス接頭辞と登録手続きを定義した。 [2]
- 2013-08-27: openid-configurationサフィックスがIANAのWell-Known URIsレジストリにpermanentとして登録された。 [3][9]
- 2016-08-18: ACMEのHTTPドメイン検証向けacme-challengeサフィックスがIANAレジストリにpermanentとして登録された。 [3][5]
- 2017-06: IETFがRFC 8126（BCP 26）を発行し、Specification Requiredを含むIANAレジストリポリシーの枠組みを更新した。 [8]
- 2018-06: 2018-03-27のoauth-authorization-server登録に続き、IETFがOAuth 2.0 Authorization Server Metadata向けのRFC 8414を発行した。 [3][6]
- 2019-03: IETFがAutomatic Certificate Management Environment（ACME）プロトコルを規定するRFC 8555を発行した。 [5]
- 2019-05: IETFがMark NottinghamによるRFC 8615を発行し、RFC 5785を廃止するとともにRFC 7230およびRFC 7595を更新した。 [1]
- 2022-04: 2021-07-13のsecurity.txt登録に続き、IETFがsecurity.txt脆弱性開示形式を定義するRFC 9116を発行した。 [3][4]
- 2025-04: 2024-10-22のoauth-protected-resource登録に続き、IETFがOAuth 2.0 Protected Resource Metadata向けのRFC 9728を発行した。 [3][7]
- 2026-10-26: IANAが2026-11-23時点でのWell-Known URIsレジストリ最終更新を記録した。 [3]

## 出典

1. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 公開 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. RFC 5785: Defining Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 公開 2010-04. https://www.rfc-editor.org/rfc/rfc5785.txt (閲覧 2026-11-23; tier 1: government or public registry)
3. Well-Known URIs. Internet Assigned Numbers Authority (IANA). 公開 2026-10-26. https://www.iana.org/assignments/well-known-uris (閲覧 2026-11-23; tier 1: government or public registry)
4. RFC 9116: A File Format to Aid in Security Vulnerability Disclosure. Internet Engineering Task Force (IETF). 公開 2022-04. https://www.rfc-editor.org/rfc/rfc9116.txt (閲覧 2026-11-23; tier 1: government or public registry)
5. RFC 8555: Automatic Certificate Management Environment (ACME). Internet Engineering Task Force (IETF). 公開 2019-03. https://www.rfc-editor.org/rfc/rfc8555.txt (閲覧 2026-11-23; tier 1: government or public registry)
6. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 公開 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (閲覧 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 公開 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (閲覧 2026-11-23; tier 1: government or public registry)
8. RFC 8126: Guidelines for Writing an IANA Considerations Section in RFCs. Internet Engineering Task Force (IETF). 公開 2017-06. https://www.rfc-editor.org/rfc/rfc8126.txt (閲覧 2026-11-23; tier 1: government or public registry)
9. Final: OpenID Connect Discovery 1.0 incorporating errata set 2. OpenID Foundation. 公開 2023-12-15. https://openid.net/specs/openid-connect-discovery-1_0.html (閲覧 2026-11-23; tier 3: official site)
10. The /llms.txt file, v2 – llms-txt. llmstxt.org. 公開 2024-09-03. https://llmstxt.org/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Well-Known URI." 版 11a2ce70, 2026-11-23. https://mimirwiki.com/ja/wiki/well-known-uri
