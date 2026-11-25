---
title: "Web Bot Auth"
subtitle: "RFC 9421 HTTP Message Signaturesに基づく自動化HTTPクライアントおよびAIエージェント向け暗号認証プロトコル"
canonical_url: https://mimirwiki.com/ja/wiki/web-bot-auth
language: ja
page_class: anchor
revision_sha256: 47f26a340982741568645dcf5b561a7d988878fd62b6ec0c70a4636aad0cf350
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/web-bot-auth.md
  txt: https://mimirwiki.com/ja/wiki/web-bot-auth.txt
  json: https://mimirwiki.com/ja/wiki/web-bot-auth.json
  jsonld: https://mimirwiki.com/ja/wiki/web-bot-auth.jsonld
translations:
  en: https://mimirwiki.com/wiki/web-bot-auth
  ko: https://mimirwiki.com/ko/wiki/web-bot-auth
  zh: https://mimirwiki.com/zh/wiki/web-bot-auth
  es: https://mimirwiki.com/es/wiki/web-bot-auth
---

# Web Bot Auth

> Web Bot Authは、RFC 9421 HTTP Message Signaturesを基盤とし、クローラーやAIエージェントなどの自動化HTTPクライアントを認証する暗号認証プロトコルである。クライアントは秘密鍵で送信リクエストに署名し、通常/.well-known/http-message-signatures-directoryに配置されるJWKSディレクトリに公開鍵を公開することで、サーバーによる身元検証を可能にする。IETFのwebbotauthワーキンググループがこの仕様を策定している。

Web Bot Authは、WebクローラーやAIエージェントなどの自動化HTTPクライアントがRFC 9421 HTTP Message Signaturesを用いて送信リクエストに署名し、Webサーバーがその身元を検証できるようにする暗号認証プロトコルである。自動化クライアントはリクエストにSignature、Signature-Input、Signature-Agentの各ヘッダーを付与し、通常はウェルノウンURI /.well-known/http-message-signatures-directoryにおいてHTTPS経由で提供されるJSON Web Key Set（JWKS）ディレクトリに公開署名鍵を公開する。Internet Engineering Task Force（IETF）のWeb Bot Auth（webbotauth）ワーキンググループは、CloudflareのThibault MeunierとGoogleのSandor Majorが執筆したdraft-ietf-webbotauth-httpsig-protocolを通じてStandards Track仕様を策定している。Cloudflareは2025年7月に、Ed25519署名鍵を用いるWeb Bot AuthをVerified Bots Programに追加した。

**別名:** webbotauth, HTTP Message Signatures for Automated Traffic, RFC 9421 Web Bot Auth

## 主要な事実

- **基盤標準:** RFC 9421（HTTP Message Signatures、2024年2月） [1]
- **標準化団体:** IETF Web Bot Auth（webbotauth）ワーキンググループ [2]
- **現行仕様:** draft-ietf-webbotauth-httpsig-protocol-01（2026-10-29） (時点 2026-11-23) [4]
- **ウェルノウン鍵ディレクトリ:** /.well-known/http-message-signatures-directory [9]
- **主要HTTPヘッダー:** Signature、Signature-Input、Signature-Agent [9]

## ファクトシート

- **種別:** 自動化クライアント向け暗号HTTP認証プロトコル [5]
- **基盤標準:** RFC 9421: HTTP Message Signatures（2024年2月） [1]
- **ワーキンググループ:** IETF Web Bot Auth（webbotauth）、Web and Internet Transportエリア (時点 2026-11-23) [2]
- **ワーキンググループ議長:** David Schinazi、Rifaat Shekh-Yusef (時点 2026-11-23) [2]
- **仕様策定者:** Thibault Meunier（Cloudflare）、Sandor Major（Google） (時点 2026-11-23) [4]
- **現行ドラフト:** draft-ietf-webbotauth-httpsig-protocol-01（2026-10-29公開） (時点 2026-11-23) [4]
- **鍵ディレクトリパス:** /.well-known/http-message-signatures-directory [9]
- **ディレクトリメディアタイプ:** application/http-message-signatures-directory+json [4]
- **Cloudflare対応アルゴリズム:** Ed25519（OKP JSON Web Key） (時点 2026-10-08) [9]
- **ドラフト状況:** 策定中のIETFインターネットドラフト（Standards Track予定） (時点 2026-11-23) [4]
- **参照リポジトリ:** github.com/cloudflare/web-bot-auth（Apache-2.0ライセンス） [12]

## Web Bot Authの概要

Web Bot Authは、検索インデックスクローラー、Webアーカイバー、リンクチェッカー、AI学習用クローラー、およびエンドユーザーを代理するAIエージェントなどの自動化HTTPクライアントを暗号学的に認証するためのプロトコルである。[2][5] このプロトコルは、2024年2月に公開されたHTTP Message Signaturesに関するIETF Standards Track仕様であるRFC 9421を基盤としており、HTTPメッセージの選択された構成要素に対して分離型デジタル署名を行うことを可能にする。[1][4] Web Bot Authはトランスポート層やTLSスタックを変更せずHTTP層のみで動作するため、リバースプロキシやゲートウェイなどのHTTP仲介装置を経由しても署名の検証可能性が保たれる。[1][5]

従来のボット識別手法には運用面およびセキュリティ面の課題が存在する。[2][5] `User-Agent`文字列は任意のクライアントによって偽装可能であり、Chromiumなどの自動化ブラウザが適切なページ描画のために標準的なブラウザ文字列を送信する場合に役割が重複してしまう。[5] IPアドレス許可リストはアドレス所有権が階層化したクラウドプラットフォーム全体でリストを維持する必要があり、専用IPブロックの確保には取得コスト、専門的な設定、および過去のレピュテーション履歴といった負担が伴う。[5] OAuth Bearerトークンなどの共有シークレット方式ではサイトごとの事前登録が必要となり、Webスケールでの鍵ローテーションが煩雑になる。[5]

Web Bot Authは、`draft-ietf-webbotauth-httpsig-protocol`に明記された2つの目標と2つの制約のもとでこれらの要件に対処する。[5] 目標は、リクエストをまたいだボット信頼の継続性の確保と、ドメイン名などの外部アンカーに対する署名鍵の任意の紐付けである。[5] 制約は、自動化クライアントとWebサイト双方の運用上の単純さを保つこと、およびクライアントとオリジンサーバー間の事前関係を不要とすることである。[5] Cloudflareは2025年5月15日にこのアプローチを公開提案し、2025年7月1日にHTTP Message SignaturesをVerified Bots Programに追加した。[10][11]

## Web Bot AuthによるHTTPリクエストの署名と検証

Web Bot Authは、RFC 9421で定義された分離型署名を用いて、メッセージヘッダーを別個のトークンペイロード内に重複させることなく送信HTTPリクエストを認証する。[1][5] 自動化クライアントはHTTPヘッダーフィールドおよび派生コンポーネントを選択し、RFC 9421の規則に従って正規化された署名ベース（signature base）へとシリアライズしたうえで、ボット提供者が保持する秘密鍵でデジタル署名を計算する。[1][5] RFC 9421では、SHA-512を用いたRSASSA-PSS、SHA-256を用いたRSASSA-PKCS1-v1_5、SHA-256を用いたHMAC、P-256およびP-384曲線によるECDSA、およびedwards25519曲線によるEdDSA（Ed25519）などのアルゴリズムが定義されている。[1] `draft-ietf-webbotauth-httpsig-protocol-01`のテストベクターはSHA-512を用いたRSASSA-PSSとEd25519を対象としており、Cloudflareの本番実装はEd25519をサポートしている。[4][9]

署名付きリクエストには3つの主要なHTTPヘッダーフィールドが含まれる。[1][9] `Signature-Input`ヘッダーは署名対象のメッセージコンポーネントと署名メタデータパラメータを列挙し、`Signature`ヘッダーはBase64エンコードされた署名バイト列を格納し、`Signature-Agent`ヘッダーはクライアントの公開鍵ディレクトリを取得できるHTTPS URLを示す。[1][4][5][9] RFC 9421署名はHTTPメッセージボディを直接カバーしないため、ボディの完全性を必要とするアプリケーションはコンテンツの暗号ハッシュを含む`Content-Digest`ヘッダーを併用する。[1][9] またRFC 9421では、受信側が後続のHTTPメッセージに署名を付与するよう要求できる任意の`Accept-Signature`ヘッダーも定義されている。[1]

`Signature-Input`内の標準メタデータパラメータは、署名の適用範囲と有効期間を制限する。[1][5][9]

| パラメータまたはヘッダー | Web Bot Authにおける役割 |
| --- | --- |
| `Signature-Agent` | インバンドでの鍵探索のため、クライアントの公開鍵ディレクトリのHTTPS URLを伝達する。[4][5] |
| `Signature-Input` | 署名対象のHTTPコンポーネント（`@authority`や`signature-agent`など）と署名メタデータを列挙する。[1][9] |
| `Signature` | 正規化された署名ベースに対する分離型暗号署名を格納する。[1][9] |
| `tag` | アプリケーションコンテキストを識別する。Cloudflareの実装ではボットリクエストに`web-bot-auth`、署名付きディレクトリレスポンスに`http-message-signatures-directory`を使用する。[9] |
| `keyid` | 署名を検証する公開鍵を特定するためのBase64URLエンコードされたJSON Web Key（JWK）サムプリントを保持する。[5][9] |
| `created`および`expires` | リプレイ攻撃への露出を制限するため、署名の有効期間を規定するUnixタイムスタンプを指定する。[5][9] |
| `nonce` | リプレイ攻撃の緩和を目的としたリクエストごとの任意の値を提供する。[9] |

## Web Bot Authの鍵ディレクトリと信頼モデル

Web Bot Authは、HTTPS経由で提供されるJSON Web Key Set（JWKS）ディレクトリに公開署名鍵を公開することで、検証者が`Signature-Agent`ヘッダーからインバンドで鍵を探索できるようにする。[4][5][6] 初期の個人ドラフト（`draft-meunier-http-message-signatures-directory`、2026年3月2日のリビジョン05まで更新）ではこのディレクトリ形式が別途規定されていたが、その後ワーキンググループが鍵探索機能を`draft-ietf-webbotauth-httpsig-protocol`に統合した。[3][4][6] このドラフトはメディアタイプ`application/http-message-signatures-directory+json`およびウェルノウンURI `/.well-known/http-message-signatures-directory`を登録している。[4] RFC 8615に基づき、`/.well-known/`パスプレフィックスはHTTPまたはHTTPSオリジンのルートに予約されているため、そのパスに鍵ディレクトリをホストすることで鍵セットがドメイン運用者に紐付けられる。[5][7]

`draft-ietf-webbotauth-httpsig-protocol-01`で定義された信頼モデルでは、検証済みの`Signature-Agent` HTTPS URLがエージェントの永続的な識別子として機能する。[5] 未解決の`Signature-Agent`ヘッダーは未検証の主張に過ぎず、検証者はTLS経由でURLを解決し、そのディレクトリから返された鍵でリクエスト署名を検証するまでアクセスポリシーの適用を保留しなければならない。[5] 識別子がURLに紐付く一方で`keyid`が個別の鍵を選択するため、運用者は既存の鍵と並べて新しい鍵を公開し、後から古い鍵を削除することで継続性を損なわずに鍵をローテーションできる。[5] 検証者が解決済みのURLなしに鍵を直接保持している場合、帰属は`keyid`サムプリントにフォールバックするが、この場合は鍵ローテーションをまたぐ継続性は維持されない。[5]

TLS経由で鍵ディレクトリを解決することにより、URLで指定されたホストが取得時点でその鍵セットを提供したことが確認され、有効なリクエスト署名はそのいずれかの鍵の保有者が署名対象コンポーネントに署名したことを証明する。[5] 第三者が別の運用者のディレクトリをミラーリングして鍵を詐称することを防ぐため、ディレクトリレスポンスには掲載された各秘密鍵の所有を証明するHTTPメッセージ署名を付与できる。[4][9] 検証者が複数のソースからディレクトリレコードを取得した場合、ディレクトリ署名の`created`タイムスタンプまたは検証者自身の取得時刻に基づき、より新しいレコードが優先される。[5] 検証によって証明されるのは暗号学的な継続性と鍵の所有であり、運用者が信頼できるか、あるいはサイトへのアクセスを認可すべきかの判断はオリジンサーバーのポリシー決定に委ねられる。[5]

## IETFにおけるWeb Bot Authの標準化

Web Bot Authは、Internet Engineering Task Force（IETF）のWeb and Internet Transport（`wit`）エリアに属するWeb Bot Auth（`webbotauth`）ワーキンググループで標準化が進められている。[2] 2026-11-23時点で、同ワーキンググループは承認済みの憲章`charter-ietf-webbotauth-01`のもとで活動しており、議長をDavid SchinaziとRifaat Shekh-Yusef、エリアディレクターをMike Bishopが務めている。[2] 憲章では3つの成果物カテゴリが定義されている。すなわち、人間向けWebサイトに対する自動化クライアント認証のためのStandards Track仕様、ドメイン名やURLなどの広く使われる識別子を介してリクエスト元ボットの追加メタデータを伝達するStandards Track仕様、そして運用ライフサイクル、鍵管理、展開上の考慮事項、およびWebの開放性への影響を扱うBest Current PracticeまたはInformational文書である。[2] 同ワーキンググループはAIPREF、HTTPBIS、OAUTH、TLS、およびWIMSEの各ワーキンググループと連携している。[2]

2026-11-23時点で、ワーキンググループが採択しているワーキンググループ・インターネットドラフトは、[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)のThibault MeunierとGoogleのSandor Majorが執筆した`draft-ietf-webbotauth-httpsig-protocol-01`（「HTTP Message Signatures for automated traffic」）の1件である。[3][4][5] 2026年10月29日に公開され2027年5月2日に失効予定の44ページの文書であるリビジョン`-01`は、従来の個人ドラフト系列`draft-meunier-webbotauth-httpsig-protocol`を置き換えたものであり、その系列自体は2026年3月2日以降に`draft-meunier-web-bot-auth-architecture-05`を置き換えたものである。[3][4][5] 憲章には、Standards Trackの認証およびボット情報仕様をIESGへ提出する目標マイルストーンとして2026年4月、Best Current Practice運用文書を提出する目標として2026年8月が記載されている。[2]

採択済みのプロトコルドラフトに加え、2026-11-23時点で`webbotauth`の文書一覧ページには関連する個人インターネットドラフト14件が掲載されている。[3] これらの提案は、ボットレジストリとSignature Agent Cards（`draft-meunier-webbotauth-registry-04`）、署名付きエージェントメタデータヘッダー（`draft-vilgalys-webbotauth-signed-agent-metadata-00`）、ホスト型鍵ディレクトリ（`draft-singh-webbotauth-hosted-directories-00`）、匿名ボット認証（`draft-rescorla-anonymous-webbotauth-01`）、検証結果レポート（`draft-suresh-webbotauth-verification-outcome-00`）、クローラーのベストプラクティス（`draft-illyes-webbotauth-cbcp-01`）、およびJSONベースのIPレンジ公開（`draft-illyes-webbotauth-jafar-01`）といった補完的メカニズムを検討している。[3] インターネットドラフトであるため、これらの文書はいずれも作業中の段階にあり、正式なIETF RFCの地位は有していない。[5][6]

## CloudflareのWeb Bot Auth実装とツール

Web Bot Authは、2025年7月1日にHTTP Message Signaturesを追加したCloudflareのVerified Bots Programにおいて本番運用されている。[9][10] 2026年10月8日に更新されたCloudflareの開発者リファレンスによると、導入手順は4段階で構成される。Ed25519鍵ペアを生成して公開鍵をJWK（`kty: "OKP"`、`crv: "Ed25519"`、パディングなしBase64URLの`x`）に変換し、`/.well-known/http-message-signatures-directory`でHTTPS経由の署名付きJWKSディレクトリをホストし、Cloudflareダッシュボードで`Request Signature`検証方式を選択してボットとディレクトリURLを登録したうえで、送信リクエストに署名を行う。[9] ディレクトリレスポンスでは`Content-Type: application/http-message-signatures-directory+json`を設定し、`@authority;req`を対象として`tag="http-message-signatures-directory"`、`keyid`、`created`、`expires`を含むHTTPメッセージ署名を各Ed25519鍵につき1つ付与する必要がある。[9]

2026年10月8日時点で、Cloudflareのリクエスト検証は初期ドラフト版（`draft-meunier-web-bot-auth-architecture-02`および`draft-meunier-http-message-signatures-directory-03`）に準拠しており、特定の制約を課している。[9] 送信リクエストでは、`https://` URIを二重引用符で囲んだ構造化文字列として`Signature-Agent`を含め、`Signature-Input`に`signature-agent`と少なくとも`@authority`を含め、ASCIIのみのコンポーネント値を使用し、`tag="web-bot-auth"`を設定する必要がある。[9] Cloudflareは後続ドラフトで導入された`Signature-Agent`の辞書構文を拒否し、`@query-params`および`@status`をサポートしておらず、`Signature-Input`にRFC 9421のコンポーネントパラメータ`sf`、`bs`、`key`、`req`、`name`が含まれる場合は検証に失敗する。[9] Cloudflareは`nonce`の送信を推奨しているものの、2026年10月8日時点で同社の検証器はnonceの検証や受信済みnonceのデータベース保存を行っておらず、リプレイ可能期間を制限するために1分程度の短い`expires`間隔を設定することを推奨している。[9] 運用者は`https://crawltest.com/cdn-cgi/web-bot-auth`に対してリクエスト形式と検証動作をテストでき、既知の鍵で検証に成功した場合はHTTP 200、未知の鍵または検証失敗の場合はHTTP 401、形式不正のメッセージの場合はHTTP 400が返される。[9]

Cloudflareはまた、仲介者を介してボット運用者の身元とコンテンツ利用に関するコミットメントを伝達するため、RFC 7239の`Forwarded`ヘッダー（構文例として`Forwarded: for="openai";use="reference"`）を用いる実験的な推移的信頼（transitive trust）メカニズムも文書化しており、この機能は変更される可能性があると明記している。[9] オリジン側で独自に署名検証を行いたいサイト所有者は、Cloudflare Supportに依頼して対象ゾーンでのCloudflareによる検証を無効化し、`cf.bot_management.verified_bot`が設定されないようにすることができる。この場合、検証済みボットは逆引きDNS検証などの方式へフォールバックする。[9]

CloudflareはApache-2.0ライセンスのオープンソースリポジトリ`github.com/cloudflare/web-bot-auth`を保守しており、TypeScriptパッケージ（`http-message-sig`、`jsonwebkey-thumbprint`、`web-bot-auth`）およびRustクレート（`web-bot-auth`、`http-signature-directory`）を収録している。同リポジトリは2026-11-23時点でスター数188、フォーク数52であった。[12] リポジトリにはブラウザ拡張機能、Rust、Caddyプラグイン、Cloudflare Workers向けの署名・検証サンプルが含まれており、あわせて`http-message-signatures-example.research.cloudflare.com`にCloudflare Researchのテストエンドポイントが用意されている。[12] なお、リポジトリのドキュメントには当該ソフトウェアがセキュリティ監査を受けていない旨が記載されている。[12]

## Web Bot Authの適用範囲、セキュリティ、および制約

Web Bot Authは主として人間向けに提供されるWebコンテンツへアクセスする自動化HTTPクライアントの暗号認証を扱うものであり、IETF `webbotauth`憲章では複数の隣接領域を対象外と明記している。[2] 対象外となる項目には、機械向けHTTP APIやエージェント間インターフェースへのアクセス認証、エージェントの背後にいるエンドユーザーの認証、非HTTPプロトコル、非暗号的な識別手法、ボットの意図を表す語彙の定義、ボットのレピュテーション追跡や付与、および非認証のまま動作することを選ぶボットの検出が含まれる。[2] また、Web Bot Authは2022年9月にRFC 9309として標準化されたRobots Exclusion Protocol（[robots.txt](https://mimirwiki.com/ja/wiki/robots-txt)）とも異なる。RFC 9309は`user-agent`トークンごとの自主的なクロール規則を記述するものであり、それらの規則がアクセス認可を構成しないことを明示している。[8]

Web Bot Authにおける暗号検証には明確なセキュリティ境界が存在する。[5] 有効な署名が確認するのは、解決された`Signature-Agent` URLに公開された鍵によってリクエストが署名されたという事実のみであり、運用者が善意であることや特定のリクエストが認可されていることを保証するものではない。[5] この仕組みはリクエスト間で継続的な認識を望む運用者を前提に設計されているため、クライアントがあるURLを放棄して別のURLを新たに立ち上げる行為自体はプロトコル上防止されない。[5] 署名付きリクエストは有効期間内であればリプレイ攻撃を受ける余地があるため、運用者は署名対象コンポーネントの選択と`created`から`expires`までの短い間隔設定によってそのリスクを制限する。[5][9]

インバンド鍵探索の導入には、`draft-ietf-webbotauth-httpsig-protocol-01`のセキュリティおよびプライバシーに関する考慮事項で取り上げられている運用上のリスクが伴う。[4] 検証者は受信リクエストが提示する任意の`Signature-Agent` HTTPS URLを取得するため、サーバーはサーバーサイドリクエストフォージェリ（SSRF）を防ぎ、ディレクトリ取得のリソース消費とキャッシュ動作を制限しなければならない。[4] 同仕様ではさらに、TLS要件、鍵漏洩時の対応、共有シークレットおよび鍵再利用の回避、テスト署名や静的署名の取り扱い、リバースプロキシとの相互作用、ならびにクライアント識別・相関分析およびディレクトリアクセスパターンに伴うプライバシーへの影響についても指摘している。[4] 加えて、`webbotauth`憲章は、ボットクライアントおよびWebサイト双方の運用上のオーバーヘッドを考慮し、アーキテクチャ上のボトルネックを生じさせないようワーキンググループに求めている。[2]

## よくある質問

### Web Bot Authとは何ですか？

Web Bot Authは、WebクローラーやAIエージェントなどの自動化クライアントがRFC 9421 HTTP Message Signaturesを用いて送信リクエストに暗号署名を付与できるようにするHTTP層の認証プロトコルです。サーバーは、JSON Web Key Setディレクトリに公開された公開鍵を使用してその署名を検証します。 [1][4][5]

### Web Bot Authでサーバーはどのようにボットの公開鍵を見つけますか？

署名付きリクエストには、ボットの鍵ディレクトリのHTTPS URLを含むSignature-Agentヘッダーが付与されます。サーバーは通常/.well-known/http-message-signatures-directoryにホストされているそのURLからJSON Web Key Setを取得し、keyidサムプリントパラメータを使用して一致する鍵を選択します。 [4][5][9]

### Web Bot Authは公式のIETF RFC標準ですか？

2026-11-23時点で、Web Bot AuthはIETF Web Bot Auth（webbotauth）ワーキンググループにおいて策定が進行中の仕様です。主要仕様であるdraft-ietf-webbotauth-httpsig-protocol-01は2026年10月29日に公開されたStandards Trackのインターネットドラフトであり、まだRFCとしては発行されていません。 [2][4][5]

### CloudflareはWeb Bot Authでどの暗号鍵をサポートしていますか？

2026年10月8日時点で、CloudflareのWeb Bot Auth統合は、/.well-known/http-message-signatures-directoryにOKP JSON Web Keyとして公開されたEd25519署名鍵をサポートしています。ディレクトリレスポンスには、鍵の所有を証明するために各Ed25519鍵によるHTTPメッセージ署名を含める必要があります。 [9]

### Web Bot Authではボットの識別子を失わずにどのように鍵をローテーションしますか？

draft-ietf-webbotauth-httpsig-protocol-01では、検証済みのSignature-Agent HTTPS URLがエージェントの識別子として機能し、keyidが個別の鍵を選択します。運用者は既存の鍵と並べて新しい公開鍵をディレクトリに公開し、その後で古い鍵を削除することで、同一URLのもとで継続性を維持しながら鍵をローテーションできます。 [5]

### Web Bot Authはrobots.txtを置き換えたり、エンドユーザーを認証したりするものですか？

いいえ。Robots Exclusion Protocol（RFC 9309）はクローラー向けの自主的なアクセスルールを定義するものであり、Web Bot Authは自動化クライアントの身元を暗号学的に検証する仕組みです。また、IETF webbotauthワーキンググループの憲章では、エンドユーザー認証は対象外と明記されています。 [2][8]

## 引用できる文

- Web Bot Authは、RFC 9421（HTTP Message Signatures、2024年2月公開）で定義された分離型デジタル署名を使用して自動化HTTPリクエストを認証する。 [1][4]
- 2026-11-23時点で、IETFのWeb Bot Auth（webbotauth）ワーキンググループは、承認された憲章charter-ietf-webbotauth-01のもとでWeb and Internet Transportエリアにおいて活動している。 [2]
- 採択されたワーキンググループドラフトdraft-ietf-webbotauth-httpsig-protocol-01は、CloudflareのThibault MeunierおよびGoogleのSandor Majorによって2026年10月29日に公開された。 [4][5]
- draft-ietf-webbotauth-httpsig-protocol-01では、検証済みのSignature-Agent HTTPS URLがエージェントの識別子として機能し、識別子の継続性を損なうことなく鍵のローテーションを可能にする。 [5]
- draft-ietf-webbotauth-httpsig-protocol-01は、JWKS鍵ディレクトリを公開するためのウェルノウンURI /.well-known/http-message-signatures-directoryおよびメディアタイプapplication/http-message-signatures-directory+jsonを定義している。 [4][7]
- Cloudflareは2025年7月1日に、HTTP Message Signatures（Web Bot Auth）をVerified Bots Programに追加した。 [10]
- 2026年10月8日時点で、CloudflareのWeb Bot Auth実装はEd25519鍵をサポートしており、/.well-known/http-message-signatures-directoryにおいてHTTPS経由で署名付きディレクトリレスポンスを提供することを要求している。 [9]
- Cloudflareは、Apache-2.0ライセンスのもとでgithub.com/cloudflare/web-bot-authにおいてTypeScriptおよびRust向けのオープンソースWeb Bot Authライブラリとサンプルを保守している。 [12]

## 年表

- 2024-02: IETFがRFC 9421（HTTP Message Signatures）をStandards Track仕様として公開した。 [1]
- 2025-05-15: Cloudflareが、Thibault MeunierおよびMari Galicerによる暗号HTTP署名を用いたボットおよびAIエージェントトラフィック検証の初期提案を公開した。 [11]
- 2025-07-01: CloudflareがHTTP Message SignaturesをVerified Bots Programに追加した。 [10]
- 2026-03-02: Thibault MeunierとSandor Majorがdraft-meunier-web-bot-auth-architectureおよびdraft-meunier-http-message-signatures-directoryのリビジョン05を公開し、その後これらはwebbotauthのプロトコルおよびディレクトリドラフトに置き換えられた。 [3][6]
- 2026-10-08: Cloudflareが、Ed25519鍵ディレクトリ、リクエスト署名、および実験的なRFC 7239 Forwardedヘッダー対応を網羅したWeb Bot Auth開発者ドキュメントを更新した。 [9]
- 2026-10-29: IETF webbotauthワーキンググループがdraft-ietf-webbotauth-httpsig-protocol-01（HTTP Message Signatures for automated traffic）を公開した。 [3][4][5]

## 出典

1. RFC 9421: HTTP Message Signatures. Internet Engineering Task Force (IETF). 公開 2024-02. https://www.rfc-editor.org/rfc/rfc9421.txt (閲覧 2026-11-23; tier 1: government or public registry)
2. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (閲覧 2026-11-23; tier 1: government or public registry)
3. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/documents/ (閲覧 2026-11-23; tier 1: government or public registry)
4. draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic. Internet Engineering Task Force (IETF). 公開 2026-10-29. https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/ (閲覧 2026-11-23; tier 1: government or public registry)
5. draft-ietf-webbotauth-httpsig-protocol-01. Internet Engineering Task Force (IETF). 公開 2026-10-29. https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol (閲覧 2026-11-23; tier 1: government or public registry)
6. draft-meunier-http-message-signatures-directory-05 - HTTP Message Signatures Directory. Internet Engineering Task Force (IETF). 公開 2026-03-02. https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/ (閲覧 2026-11-23; tier 1: government or public registry)
7. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). 公開 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (閲覧 2026-11-23; tier 1: government or public registry)
8. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). 公開 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (閲覧 2026-11-23; tier 1: government or public registry)
9. Web Bot Auth · Cloudflare bot solutions docs. Cloudflare. 公開 2026-10-08. https://developers.cloudflare.com/bots/reference/bot-verification/web-bot-auth/ (閲覧 2026-11-23; tier 3: official site)
10. Message Signatures are now part of our Verified Bots Program, simplifying bot authentication | Cloudflare Blog. The Cloudflare Blog. 公開 2025-07-01. https://blog.cloudflare.com/verified-bots-with-cryptography/ (閲覧 2026-11-23; tier 3: official site)
11. Forget IPs: using cryptography to verify bot and agent traffic | Cloudflare Blog. The Cloudflare Blog. 公開 2025-05-15. https://blog.cloudflare.com/web-bot-auth/ (閲覧 2026-11-23; tier 3: official site)
12. GitHub - cloudflare/web-bot-auth: Sign and verify orchestrated HTTP requests · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/web-bot-auth (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Web Bot Auth." 版 47f26a34, 2026-11-23. https://mimirwiki.com/ja/wiki/web-bot-auth
