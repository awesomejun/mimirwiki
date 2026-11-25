---
title: "OAuth"
subtitle: "アクセストークンを用いてHTTPリソースへの委任アクセスを実現するIETF標準のオープン認可フレームワーク"
canonical_url: https://mimirwiki.com/ja/wiki/oauth
language: ja
page_class: anchor
revision_sha256: b6bfe4f38fb5e1d6ab58c4e41f0a5e8fc5fa4e66b1cd00de1d0f349a82289dc7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/oauth.md
  txt: https://mimirwiki.com/ja/wiki/oauth.txt
  json: https://mimirwiki.com/ja/wiki/oauth.json
  jsonld: https://mimirwiki.com/ja/wiki/oauth.jsonld
translations:
  en: https://mimirwiki.com/wiki/oauth
  ko: https://mimirwiki.com/ko/wiki/oauth
  zh: https://mimirwiki.com/zh/wiki/oauth
  es: https://mimirwiki.com/es/wiki/oauth
---

# OAuth

> OAuthは、アプリケーションがリソースオーナーの認証情報を受け取ることなく、認可サーバーが発行したアクセストークンを用いてHTTPリソースへアクセスできるようにするIETFの認可フレームワークである。2012年10月にRFC 6749としてOAuth 2.0が公開され、2025年1月にRFC 9700によって更新されており、OpenID ConnectやModel Context Protocolの認可に使用されている。

OAuthは、サードパーティアプリケーションがアクセストークンを用いて、リソースオーナーの代理として、または自身の権限でHTTPサービスの保護リソースに限定的にアクセスできるようにするオープンな認可フレームワークである。2007年10月にコミュニティ仕様として安定版となり、2010年4月にRFC 5849でOAuth 1.0として文書化された後、2012年10月にIETFの標準化トラック上でRFC 6749およびRFC 6750のOAuth 2.0に置き換えられた。その後のIETF仕様により、Proof Key for Code Exchange（RFC 7636）、認可サーバーメタデータ（RFC 8414）、OAuth 2.0セキュリティ最新ベストプラクティス（RFC 9700、BCP 240）、保護リソースメタデータ（RFC 9728）でOAuth 2.0が拡張された。2026-11-23時点で、IETF OAuthワーキンググループはOAuth 2.0と後続のセキュリティ要件を単一の仕様に統合するOAuth 2.1（draft-ietf-oauth-v2-1-17）を策定している。

**別名:** OAuth 2.0, OAuth 2.1, OAuth 1.0, OAuth 2.0 認可フレームワーク, RFC 6749

## 主要な事実

- **標準化団体:** Internet Engineering Task Force（IETF）OAuthワーキンググループ [8]
- **中核仕様:** RFC 6749（OAuth 2.0、2012年10月） [1]
- **セキュリティBCP:** RFC 9700 / BCP 240（2025年1月） [6]
- **ロール:** リソースオーナー、リソースサーバー、クライアント、認可サーバー [1]
- **OAuth 2.1ドラフト状況:** draft-ietf-oauth-v2-1-17（有効なインターネットドラフト、2026-10-30更新） (時点 2026-11-23) [8]

## ファクトシート

- **種別:** HTTP認可フレームワーク [1]
- **標準化団体:** Internet Engineering Task Force（IETF）OAuthワーキンググループ [8]
- **OAuth 1.0:** 2007年10月安定版、2009年6月Revision A、RFC 5849（情報提供、2010年4月） [4]
- **OAuth 2.0フレームワーク:** RFC 6749（標準化トラック、2012年10月、編集者D. Hardt） [1]
- **ベアラートークン使用法:** RFC 6750（標準化トラック、2012年10月、TLS必須） [2]
- **PKCE:** RFC 7636（標準化トラック、2015年9月） [3]
- **サーバーメタデータ:** RFC 8414（標準化トラック、2018年6月） [5]
- **セキュリティBCP:** RFC 9700 / BCP 240（2025年1月、RFC 6749・6750・6819を更新） [6]
- **保護リソースメタデータ:** RFC 9728（標準化トラック、2025年4月） [7]
- **OAuth 2.1の状況:** 有効なインターネットドラフト draft-ietf-oauth-v2-1-17（2026-10-30更新、2027-05-04期限） (時点 2026-11-23) [8]
- **OAuth 2.0のロール:** リソースオーナー、リソースサーバー、クライアント、認可サーバー [1]
- **OAuth 2.0に基づくプロトコル:** OpenID Connect、UMA 2.0、IndieAuth [9]

## OAuthの起源とOAuth 1.0からOAuth 2.0への移行

OAuthはサードパーティクライアントのロールをリソースオーナーから分離し、アプリケーションがリソースオーナーの認証情報を保持することなく、認可サーバーが発行したアクセストークンを用いてHTTPリソースにアクセスできるようにする仕組みである。[1] 従来のクライアント・サーバー間のパスワード共有方式では、サードパーティアプリケーションがユーザーのパスワードを平文で保存する必要があり、スコープや有効期間の制限なく広範なアクセス権が付与され、パスワードを変更しない限り個別にアクセスを取り消すことができず、侵害が発生した場合にはユーザーのパスワードとすべての保護データが露出するという問題があった。[1]

OAuth 1.0は、保護リソースへの委任アクセスを実現するため、少人数のウェブ開発者コミュニティによって作成された。[4] 仕様は2007年10月にバージョン1.0として安定版となり、2009年6月にOAuth Core 1.0 Revision A（`oauth.net/core/1.0a`）として改訂された。[4] 原著者らが変更管理権限をIETFに移管した後、IETFは2010年4月にRevision Aと報告された正誤表を網羅した情報提供（Informational）文書としてRFC 5849（E. Hammer-Lahav編集）を公開した。[4] OAuth 1.0では、クライアント（当初はConsumer）、サーバー（当初はService Provider）、およびリソースオーナー（当初はUser）の3つのロールが定義されていた。[4] また、識別子と共有シークレットからなる3種類の認証情報（クライアント認証情報、一時認証情報、トークン認証情報）を使用し、ナンス、タイムスタンプ、および暗号署名（`HMAC-SHA1`、`RSA-SHA1`、または`PLAINTEXT`）によってHTTPリクエストを認証していた。[4]

2012年10月、IETFは標準化トラック上でOAuth 2.0をRFC 6749（D. Hardt編集）として、ベアラートークン使用法をRFC 6750（M. JonesおよびD. Hardt著）として公開した。[1][2] RFC 6749はRFC 5849を置き換えて廃止している。[1] OAuth 2.0はHTTP向けに設計されておりOAuth 1.0との後方互換性はないが、両バージョンはネットワーク上で共存でき、実装が双方をサポートすることも可能である。[1] HTTP以外のプロトコル上でのOAuth 2.0の使用はRFC 6749の範囲外である。[1]

## OAuth 2.0のロール、エンドポイント、トークン、およびグラントタイプ

OAuth 2.0は、HTTPリソースへの委任アクセスのためにRFC 6749で4つのロールを定義している。[1]

| ロール | RFC 6749における定義 |
| --- | --- |
| リソースオーナー（Resource owner） | 保護リソースへのアクセスを許可できる主体。個人の場合はエンドユーザーと呼ばれる |
| リソースサーバー（Resource server） | 保護リソースをホストし、アクセストークンを用いたリクエストを受理・応答するサーバー |
| クライアント（Client） | リソースオーナーの代理として、その認可のもとで保護リソースへのリクエストを行うアプリケーション |
| 認可サーバー（Authorization server） | リソースオーナーを認証し認可を得たうえで、クライアントにアクセストークンを発行するサーバー |

認可サーバーとリソースサーバーは同一のサーバー上で稼働させることも別個のエンティティとして運用することもでき、単一の認可サーバーが複数のリソースサーバーで受け入れられるアクセストークンを発行することも可能である。[1] RFC 6749は、認可サーバーの2つのエンドポイントである認可エンドポイント（Authorization Endpoint）およびトークンエンドポイント（Token Endpoint）と、クライアントのリダイレクトエンドポイント（Redirection Endpoint）を定義している。[1] 抽象フローでは、クライアントがリソースオーナーから認可グラントを取得し、認可サーバーで特定のスコープ・有効期間・アクセス属性を表すアクセストークンと交換して、そのアクセストークンをリソースサーバーに提示する。[1][2] 一部のフローでは、クライアントがリソースオーナーの認可グラントを介さず、自身の認証情報を認可サーバーに直接提示してアクセストークンを取得する。[1][2]

RFC 6750は、トランスポート層セキュリティ（TLS）を伴うHTTP/1.1上でクライアントがベアラートークンを提示する方法を規定しており、TLSの実装と使用を必須としている。[2] ベアラートークンを所持する者は誰でも、暗号鍵の所有を証明することなく関連リソースにアクセスできるため、ベアラートークンは保存時および転送時の漏洩から保護する必要がある。[2] RFC 6750は、`Bearer`スキームを用いた`Authorization`リクエストヘッダーフィールド（`Authorization: Bearer <token>`）、フォームエンコードされたボディパラメーター、およびURIクエリパラメーターの3つの送信方法を定義しており、単一のリクエストで複数の方法を併用することを禁止している。[2] また、IANAに`Bearer`アクセストークン種別と、`WWW-Authenticate`のエラー値である`invalid_request`、`invalid_token`、`insufficient_scope`を登録している。[2]

RFC 6749は、認可コード（Authorization Code）、インプリシット（Implicit）、リソースオーナーパスワードクレデンシャルズ（Resource Owner Password Credentials）、クライアントクレデンシャルズ（Client Credentials）の4つの認可グラントタイプに加え、リフレッシュトークンの発行および拡張グラント（Extension Grants）の仕組みを定義している。[1] その後のIETF仕様では、ブラウザやキーボードを持たない機器向けのデバイス認可グラント（Device Authorization Grant、RFC 8628）などのフローが追加された。[9] 後続のセキュリティ指針であるRFC 9700は安全性の低い動作モードを非推奨とし、OAuthコミュニティサイトはインプリシットグラントとパスワードグラントをレガシーに分類しており、OAuth 2.1は両グラントを除外している。[6][9][10]

## OAuth 2.0のPKCEとセキュリティ最新ベストプラクティス（RFC 9700）

認可コードグラントを使用するOAuth 2.0のパブリッククライアントは認可コード横取り攻撃に対して脆弱であり、IETFはこれに対処するため、2015年9月にRFC 7636（N. Sakimura、J. Bradley、N. Agarwal著）でProof Key for Code Exchange（PKCE、発音は「pixy」）を規定した。[3] スマートフォンなどの端末におけるこの攻撃では、悪意のあるアプリケーションが正規のネイティブOAuth 2.0アプリケーションと同じカスタムURIスキームを登録し、OSのアプリ間リダイレクトを通じて返された認可コードを横取りしてアクセストークンと交換する。[3]

PKCEは、クライアントが認可リクエストごとに暗号学的にランダムな固有の`code_verifier`を生成し、変換後の値である`code_challenge`を認可エンドポイントに送信することを求めることで横取り攻撃を緩和する。[3] トークンエンドポイントに認可コードを送信する際、クライアントは元の`code_verifier`を併せて提示し、認可サーバーが紐づけを検証したうえでトークンを発行する。[3] RFC 7636は初期の`code_challenge_method`値として`plain`と`S256`の2つを定義している。`plain`は認可レスポンスのみが観察される状況を緩和し、`S256`はOSのHTTPログ漏洩などにより攻撃者が認可リクエストも読み取れる状況まで緩和する。[3]

2025年1月、IETFはOAuth 2.0セキュリティ最新ベストプラクティスをRFC 9700（BCP 240、T. Lodderstedt、J. Bradley、A. Labunets、D. Fett著）として公開し、RFC 6749、RFC 6750、およびRFC 6819を更新した。[6] RFC 9700は、現実の実装における弱点、高度なセキュリティを要する導入環境（オープンバンキング、eHealth、電子政府、電子署名など）、動的なクライアント・サーバー関係、およびリダイレクト時のURLフラグメント処理に影響するブラウザの挙動変更に対処している。[6] その中核となる要件は以下の通りである。[6]

- クライアントのリダイレクトURIを事前登録されたURIと照合する際の完全文字列一致の義務化（ネイティブアプリのlocalhostリダイレクトURIにおけるポート番号を除く）
- クライアントおよび認可サーバーにおけるオープンリダイレクタの公開禁止
- PKCE（認可サーバーのサポートが確認されている場合）、OpenID Connectの`nonce`パラメーター、またはユーザーエージェントに紐づけられた`state`内のワンタイムCSRFトークンによるクロスサイトリクエストフォージェリ（CSRF）対策の義務化
- クライアントが複数の認可サーバーと通信する場合のミックスアップ攻撃対策の義務化（RFC 9207の`iss`パラメーター、IDトークンやJARMレスポンス内の`iss`クレーム、または個別のリダイレクトURIを使用）
- 認可コードグラントにおけるパブリッククライアントへのPKCE義務化、コンフィデンシャルクライアントへのPKCE推奨、およびコンフィデンシャルなOpenID Connectクライアントによる条件付きでの`nonce`使用
- 安全性の低い、または安全でない動作モードの非推奨化と、送信者制約アクセストークン、オーディエンス制限アクセストークン、およびリフレッシュトークン保護に関する指針の提示

IETF OAuthワーキンググループは、より高度なセキュリティ要件やトークンライフサイクル要件を支えるため、Pushed Authorization Requests（PAR、RFC 9126）、Demonstration of Proof of Possession（DPoP、RFC 9449）、Mutual TLS（RFC 8705）、JWT Profile for Access Tokens（RFC 9068）、Token Introspection（RFC 7662）、Token Revocation（RFC 7009）、Token Exchange（RFC 8693）、Rich Authorization Requests（RAR、RFC 9396）、Step-up Authentication Challenge（RFC 9470）、およびSecurity of Cross-Device Flows（RFC 10027）などの追加仕様も策定している。[9]

## OAuth 2.0のメタデータおよびディスカバリ仕様

OAuth 2.0は当初、デプロイ時点でクライアントがサーバーURLを既知とする静的な関係を前提としていたが、その後のIETF仕様により、動的な環境向けに[Well-Known URI](https://mimirwiki.com/ja/wiki/well-known-uri)でのJSONメタデータ探索が追加された。[5][6][7]

2018年6月に標準化トラックで公開されたOAuth 2.0認可サーバーメタデータ（RFC 8414、M. Jones、N. Sakimura、J. Bradley著）は、OpenID Connect Discovery 1.0を互換性のある形式で一般化し、より広範なOAuth 2.0導入環境に対応させている。[5] クライアントは、クエリやフラグメントを含まない`https`スキームの認可サーバーの`issuer` URLから導出された`.well-known`ロケーション（RFC 5785準拠）よりJSON文書を取得する。この`issuer`識別子はミックスアップ攻撃の防止にも役立つ。[5] メタデータはHTTPS上の自己主張JSONとして、またはJSON Web Token（JWT）内の署名付きクレームとして配信できる。[5] 登録されたメタデータパラメーターには、`issuer`、`authorization_endpoint`、`token_endpoint`、`jwks_uri`、`registration_endpoint`（RFC 7591）、`scopes_supported`、`response_types_supported`、`response_modes_supported`（デフォルトは`query`および`fragment`であり、`form_post`も定義）、`grant_types_supported`が含まれる。[5]

2025年4月に標準化トラックで公開されたOAuth 2.0保護リソースメタデータ（RFC 9728、M.B. Jones、P. Hunt、A. Parecki著）は、クライアントと認可サーバーがOAuth 2.0保護リソースとの連携方法を探索できるようにする、対称的なJSONメタデータ形式を定義している。[7] 各保護リソースは、自身の`https`リソース識別子から決定論的に導出された`.well-known`ロケーション（RFC 8615準拠）に、自己主張形式またはJWT署名付きクレームとしてメタデータを公開する。[7] 登録されたパラメーターには、`resource`（必須）、`authorization_servers`（RFC 8414のissuer識別子リスト）、`jwks_uri`、`scopes_supported`、および`bearer_methods_supported`（`header`、`body`、`query`）が含まれる。[7] RFC 9728はまた、保護リソースが`WWW-Authenticate` HTTPヘッダーを用いて保護リソースメタデータURLをクライアントに動的に通知する方法も規定している。[7]

プログラムによるクライアント登録については、RFC 7591がOAuth 2.0動的クライアント登録プロトコル（Dynamic Client Registration Protocol）を規定し、RFC 7592が実験的な登録管理を定義している。[5][9] 2026-11-23時点で、OAuthワーキンググループはCross-App Access（XAA）などの他のワーキンググループドラフトと並行して、Client ID Metadata Documents（`draft-ietf-oauth-client-id-metadata-document-00`）の策定も進めている。[9][12]

## OAuth 2.1の統合とIETFドラフトの状況

OAuth 2.1は、OAuth 2.0（RFC 6749）、ベアラートークン使用法（RFC 6750）、および後続の諸仕様を単一の文書に統合するIETF OAuthワーキンググループの仕様策定活動である。[8][10] RFC 7636（PKCE）、RFC 8252（ネイティブアプリ向けOAuth 2.0）、RFC 10017（ブラウザベースアプリ向けOAuth）、およびRFC 9700（OAuth 2.0セキュリティ最新ベストプラクティス）による変更点を取り込んでいる。[6][10]

2026-11-23時点で、`draft-ietf-oauth-v2-1-17`（著者Dick Hardt、編集者Aaron Parecki、Torsten Lodderstedt、`draft-parecki-oauth-v2-1`の後継）は標準化トラックを意図した有効なインターネットドラフトであり、承認されればRFC 6749およびRFC 6750を廃止することになる。[8] IETF Datatrackerによると、リビジョン17の最終更新日は2026-10-30（ドラフト日付は2026-10-31）、有効期限は2027-05-04であり、OAuthワーキンググループのマイルストーンとして2026年12月のIESG提出が設定されている。[8] IETFはインターネットドラフトを進行中の作業文書と位置づけており、この文書はまだ確定したRFCとしては公開されていない。[8] ドラフトのソースおよびイシュートラッカーは`github.com/oauth-wg/oauth-v2-1`で管理されている。[8]

OAuthコミュニティのOAuth 2.1向け文書はOAuth 2.0からの7つの主要な相違点を挙げており、これらは2026-11-23時点の`draft-ietf-oauth-v2-1-17`の構成にも反映されている。[8][10]

| 領域 | OAuth 2.1の規定（draft-ietf-oauth-v2-1-17） |
| --- | --- |
| PKCE | 認可コードフローを使用するすべてのOAuthクライアントに必須 |
| リダイレクトURI | 完全文字列一致による比較が必須 |
| インプリシットグラント | 除外（`response_type=token`を削除） |
| リソースオーナーパスワードクレデンシャルズグラント | 除外 |
| URIクエリ文字列内のベアラートークン | 除外。リソースリクエストにはAuthorizationヘッダーフィールドまたはフォームエンコードされたコンテンツパラメーターを使用 |
| パブリッククライアントのリフレッシュトークン | 送信者制約またはローテーションのいずれかが必須 |
| クライアント種別の定義 | パブリッククライアントとコンフィデンシャルクライアントの定義を認証情報の有無へと簡素化 |

ベアラートークンに加え、`draft-ietf-oauth-v2-1-17`には送信者制約アクセストークンに関する独立した節が設けられており、中核のグラントタイプは認可コード、クライアントクレデンシャルズ、リフレッシュトークン、および拡張グラントに限定されている。[8]

## OpenID ConnectおよびModel Context Protocol認可におけるOAuth

OAuth 2.0は、OpenID Connect（OpenID Foundation）、UMA 2.0（Kantara）、IndieAuth（W3C）、および[Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol)（MCP）におけるトランスポート認可といった諸プロトコルの基盤となる認可層を構成している。[9][11][12]

OpenID ConnectはRFC 6749とRFC 6750の上に構築された相互運用可能な認証プロトコルであり、OpenIDプロバイダー（OP）またはアイデンティティプロバイダー（IDP）と呼ばれる認可サーバーが行った認証に基づいてアプリケーションがエンドユーザーの身元を検証し、REST形式のUserInfoエンドポイントからユーザープロフィールのクレームを取得できるようにする。[11] ユーザー認証をOPに委任するアプリケーションはリライングパーティ（RP）と呼ばれる。[11] OpenID Connectのフローでは、RPがOPに認証リクエストを送信し、OPがエンドユーザーを認証して認可を得た後、通常はアクセストークンと併せて、少なくとも`sub`（サブジェクト）クレームと認証メタデータを含むIDトークンを返却する。[11] OpenID Connectはトランスポート暗号化にHTTPS/TLSを用い、ウェブ、モバイル、およびJavaScriptクライアント全体で署名が必要な場合にはJSON Web Token（JWT）構造を利用するほか、アイデンティティデータの暗号化、プロバイダーディスカバリ、セッションログアウトといった任意機能も備えている。[11] OpenID Foundationは、このJSONとRESTに基づく設計を、OpenID 2.0やSAMLのようなXMLベースのアイデンティティプロトコルと対比させている。[11]

Model Context Protocol仕様（バージョン2026-07-28）は、HTTPベースのトランスポート向けに任意のトランスポートレベル認可を定義する一方、STDIOトランスポートを使用する実装は環境から認証情報を取得する。[12] MCPの認可では、保護されたMCPサーバーがOAuth 2.1のリソースサーバーとして機能し、MCPクライアントがリソースオーナーの代理でリクエストを行うOAuth 2.1クライアントとして機能し、認可サーバーがユーザーと対話してアクセストークンを発行する。[12] 2026-11-23時点で、バージョン2026-07-28はOAuthおよびOpenID Connect標準の以下のサブセットを規定している。[12]

- 中核フローとトークン：OAuth 2.1 IETFドラフト（`draft-ietf-oauth-v2-1-13`）およびベアラートークン使用法（RFC 6750）
- 保護リソース探索：MCPサーバーおよびクライアントへのOAuth 2.0保護リソースメタデータ（RFC 9728）の義務化。MCPサーバーはHTTP 401の`WWW-Authenticate: Bearer`ヘッダーに`resource_metadata`（例：`/.well-known/oauth-protected-resource`）と、最小権限およびステップアップ認可のための任意の`scope`案内を含めて返却する
- 認可サーバー探索：認可サーバーはOAuth 2.0認可サーバーメタデータ（RFC 8414）またはOpenID Connect Discovery 1.0を提供する必要があり、MCPクライアントは双方をサポートしなければならない
- リソースおよび発行者の紐づけ：OAuth 2.0リソースインジケーター（RFC 8707）の義務化により、認可リクエストとトークンリクエストの双方にMCPサーバーの正規URIを含む`resource`パラメーターを必須とし、認可コードをトークンエンドポイントに送信する前にRFC 9207の`iss`パラメーターを記録済みの発行者と照合検証する
- クライアント登録：OAuth Client ID Metadata Documents（`draft-ietf-oauth-client-id-metadata-document-00`）、事前登録、または動的クライアント登録（RFC 7591およびOpenID Connect Dynamic Client Registration 1.0）のいずれかを使用する。なお、MCPではRFC 7591は非推奨とされ後方互換性のために維持されている

## よくある質問

### OAuthとは何ですか？

OAuthは、サードパーティアプリケーションがリソースオーナーの認証情報を受け取ることなく、認可サーバーが発行したアクセストークンを使用してHTTPの保護リソースへ限定的にアクセスできるようにするIETFの認可フレームワークです。OAuth 2.0は2012年10月にIETFの標準化トラック文書であるRFC 6749およびRFC 6750として公開されました。 [1][2]

### OAuth 2.0の4つのロールとは何ですか？

RFC 6749では4つのロール（役割）が定義されています。保護リソースへのアクセス権を付与できる主体であるリソースオーナー（個人の場合はエンドユーザー）、保護リソースをホストするリソースサーバー、認可を得て保護リソースへのリクエストを行うクライアント、そしてリソースオーナーを認証してアクセストークンを発行する認可サーバーです。 [1]

### PKCEとは何ですか？なぜOAuth 2.0で使用されるのですか？

2015年9月にRFC 7636で規定されたProof Key for Code Exchange（PKCE）は、動的に生成したランダムなコードベリファイアとそれを変換したコードチャレンジによって認可リクエストとトークンリクエストを紐づけることで、認可コードグラントにおける認可コード横取り攻撃やインジェクション攻撃を緩和します。RFC 9700はパブリッククライアントにPKCEを必須とし、コンフィデンシャルクライアントにも使用を推奨しています。 [3][6]

### OAuth 2.0セキュリティ最新ベストプラクティスであるRFC 9700では何が変わりましたか？

2025年1月にBCP 240として公開されたRFC 9700は、RFC 6749、RFC 6750、およびRFC 6819を更新しています。主な変更点として、リダイレクトURIの完全一致検証（ネイティブアプリのlocalhostリダイレクトURIにおけるポート番号を除く）、オープンリダイレクタの禁止、CSRF対策およびRFC 9207のissパラメーターなどによるミックスアップ攻撃対策の義務化、パブリッククライアントへのPKCE義務化、安全性の低い動作モードの非推奨化が挙げられます。 [6]

### OAuth 2.1は確定した標準規格ですか？

2026-11-23時点で、OAuth 2.1はIETF OAuthワーキンググループの有効なインターネットドラフト（draft-ietf-oauth-v2-1-17、最終更新2026-10-30、有効期限2027-05-04）であり、IESG提出のワーキンググループマイルストーンは2026年12月です。このドラフトはOAuth 2.0と後続のRFCを統合し、インプリシットグラントやリソースオーナーパスワードクレデンシャルズグラント、URIクエリ文字列でのベアラートークン送信を除外したうえで、認可コードフローを使用するすべてのクライアントにPKCEを必須としています。 [8][10]

### OpenID ConnectとModel Context ProtocolはOAuthをどのように利用していますか？

OpenID ConnectはOAuth 2.0（RFC 6749およびRFC 6750）の上に構築された認証プロトコルであり、OpenIDプロバイダーがIDトークンを返し、UserInfoエンドポイントがユーザープロフィールのクレームを提供します。Model Context Protocol仕様バージョン2026-07-28は、任意のHTTPトランスポート認可にOAuth 2.1、RFC 6750、RFC 8414、RFC 9728、RFC 8707、およびRFC 9207を採用しており、保護されたMCPサーバーをOAuth 2.1のリソースサーバーとして扱います。 [11][12]

## 引用できる文

- OAuth 1.0は2007年10月に安定版となり、2009年6月にRevision Aとして改訂され、2010年4月に情報提供（Informational）文書のRFC 5849として公開された。 [4]
- 2012年10月にIETFの標準化トラック（Standards Track）で公開されたRFC 6749は、OAuth 2.0認可フレームワークを定義し、RFC 5849を廃止した。 [1]
- RFC 6750はOAuth 2.0保護リソースにおけるHTTPベアラートークンの使用法を定義し、トランスポート層セキュリティ（TLS）の使用を必須としている。 [2]
- 2015年9月に公開されたRFC 7636は、OAuth 2.0のパブリッククライアントに対する認可コード横取り攻撃を緩和するため、Proof Key for Code Exchange（PKCE）を規定している。 [3]
- RFC 8414（2018年6月）およびRFC 9728（2025年4月）は、OAuth 2.0の認可サーバーと保護リソース向けに.well-known URIから提供されるJSONメタデータ文書を定義している。 [5][7]
- 2025年1月に公開されたRFC 9700（BCP 240）は、OAuth 2.0のセキュリティに関する最新ベストプラクティスをもってRFC 6749、RFC 6750、およびRFC 6819を更新している。 [6]
- 2026-11-23時点で、OAuth 2.1は有効なIETFインターネットドラフト（draft-ietf-oauth-v2-1-17、2026-10-30更新）であり、承認されればRFC 6749およびRFC 6750を廃止する予定である。 [8]
- Model Context Protocol仕様バージョン2026-07-28は、HTTP認可を使用する保護されたMCPサーバーにRFC 9728の実装を必須とし、MCPクライアントにRFC 8707のresourceパラメーターの送信を必須としている。 [12]

## 年表

- 2007-10: ウェブ開発者らがOAuth 1.0プロトコルの安定版を策定した。 [4]
- 2009-06: OAuth Core 1.0 Revision Aがoauth.net/core/1.0aで公開された。 [4]
- 2010-04: IETFがRFC 5849（The OAuth 1.0 Protocol）を情報提供（Informational）RFCとして公開した。 [4]
- 2012-10: IETFがRFC 6749（The OAuth 2.0 Authorization Framework）およびRFC 6750（Bearer Token Usage）を標準化トラックで公開し、RFC 5849を廃止した。 [1][2]
- 2015-09: IETFがOAuthパブリッククライアント向けのProof Key for Code Exchange（PKCE）を規定するRFC 7636を公開した。 [3]
- 2018-06: IETFがOAuth 2.0認可サーバーメタデータを定義するRFC 8414を公開した。 [5]
- 2025-01: IETFがOAuth 2.0セキュリティ最新ベストプラクティスを定めたRFC 9700（BCP 240）を公開し、RFC 6749、RFC 6750、およびRFC 6819を更新した。 [6]
- 2025-04: IETFがOAuth 2.0保護リソースメタデータを定義するRFC 9728を公開した。 [7]
- 2026-07-28: Model Context Protocol仕様バージョン2026-07-28が、HTTPベースのトランスポート認可にOAuth 2.1、RFC 9728、RFC 8414、RFC 8707、およびRFC 9207を規定した。 [12]
- 2026-10-30: IETF DatatrackerにOAuth 2.1インターネットドラフトのリビジョン17（draft-ietf-oauth-v2-1-17）が記録され、有効期限は2027-05-04、IESG提出のワーキンググループマイルストーンは2026年12月とされた。 [8]

## 出典

1. RFC 6749: The OAuth 2.0 Authorization Framework. Internet Engineering Task Force (IETF). 公開 2012-10. https://www.rfc-editor.org/rfc/rfc6749.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. RFC 6750: The OAuth 2.0 Authorization Framework: Bearer Token Usage. Internet Engineering Task Force (IETF). 公開 2012-10. https://www.rfc-editor.org/rfc/rfc6750.txt (閲覧 2026-11-23; tier 1: government or public registry)
3. RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Internet Engineering Task Force (IETF). 公開 2015-09. https://www.rfc-editor.org/rfc/rfc7636.txt (閲覧 2026-11-23; tier 1: government or public registry)
4. RFC 5849: The OAuth 1.0 Protocol. Internet Engineering Task Force (IETF). 公開 2010-04. https://www.rfc-editor.org/rfc/rfc5849.txt (閲覧 2026-11-23; tier 1: government or public registry)
5. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). 公開 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (閲覧 2026-11-23; tier 1: government or public registry)
6. RFC 9700: Best Current Practice for OAuth 2.0 Security. Internet Engineering Task Force (IETF). 公開 2025-01. https://www.rfc-editor.org/rfc/rfc9700.txt (閲覧 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). 公開 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (閲覧 2026-11-23; tier 1: government or public registry)
8. draft-ietf-oauth-v2-1-17 - The OAuth 2.1 Authorization Framework. Internet Engineering Task Force (IETF). 公開 2026-10-30. https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ (閲覧 2026-11-23; tier 1: government or public registry)
9. OAuth 2.0 - OAuth. OAuth Community Site. https://oauth.net/2/ (閲覧 2026-11-23; tier 3: official site)
10. OAuth 2.1. OAuth Community Site. https://oauth.net/2.1/ (閲覧 2026-11-23; tier 3: official site)
11. How OpenID Connect Works - OpenID Foundation. OpenID Foundation. 公開 2023-02-14. https://openid.net/developers/how-connect-works/ (閲覧 2026-11-23; tier 3: official site)
12. Authorization - Model Context Protocol. Model Context Protocol project. 公開 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "OAuth." 版 b6bfe4f3, 2026-11-23. https://mimirwiki.com/ja/wiki/oauth
