---
title: "nginx"
subtitle: "高性能なオープンソースの非同期Webサーバー、リバースプロキシ、ロードバランサー、メールプロキシ"
canonical_url: https://mimirwiki.com/ja/wiki/nginx
language: ja
page_class: entity
revision_sha256: 790ed871f3aa42a4335e23637587e99bbb8bfde51d63ae0ff8a5808a62f9cc16
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/ja/wiki/nginx.md
  txt: https://mimirwiki.com/ja/wiki/nginx.txt
  json: https://mimirwiki.com/ja/wiki/nginx.json
  jsonld: https://mimirwiki.com/ja/wiki/nginx.jsonld
translations:
  en: https://mimirwiki.com/wiki/nginx
  ko: https://mimirwiki.com/ko/wiki/nginx
  zh: https://mimirwiki.com/zh/wiki/nginx
---

# nginx

> 2026年11月23日現在、オープンソース版の最新リリースブランチはnginx 1.31.10（メインライン版、2026年11月23日リリース）およびnginx 1.30.8（安定版）であり、CVE-2026-132779（TLS 1.3でssl_early_dataディレクティブを使用した場合にクライアントが過剰なCPU使用率を引き起こす可能性がある中程度の脆弱性）が修正されている。これらに先立ち、2026年11月18日にリリースされたnginx 1.31.9（メインライン版）および1.30.7（安定版）では、CVSS v4.0スコア9.2（緊急）/ CVSS v3.1スコア8.1（重要）の2件の未認証HTTP/2リモートコード実行脆弱性であるCVE-2026-123007（nginx 1.9.5で導入され10年間潜在していたHTTP/2のsend_window整数アンダーフローおよびヒープバッファオーバーフロー）とCVE-2026-123633（HTTP/2アップストリームプロキシにおけるworker_connections解放後使用）をはじめとする計10件のセキュリティ脆弱性（安定版1.30.7では9件が対象）が修正された。

nginx（大文字表記ではNGINX、「エンジンエックス」と発音）は、イーゴリ・シソエフ（Igor Sysoev）によって開発され、2004年10月に一般公開されたオープンソースのイベント駆動型HTTP Webサーバー、リバースプロキシ、アプリケーションロードバランサー、コンテンツキャッシュ、およびメールプロキシサーバーである。2条項BSDライセンスの下で配布されており、2019年のF5, Inc.によるNGINX, Inc.買収以降は同社が保守を担っている。非同期のマスター・ワーカープロセスアーキテクチャを採用しており、最小限のメモリオーバーヘッドで数万件の同時接続を処理できるよう設計されている。

**別名:** NGINX, Engine-X, NGINX Open Source, NGINX Plus

## 主要な事実

- **原開発者・所有者:** イーゴリ・シソエフ（2004年）、F5, Inc.（2019年5月以降） [1]
- **ライセンス:** 2条項BSDライセンス [1]
- **最新リリース:** 1.31.10（メインライン版、2026年11月23日リリース）および1.30.8（安定版） (時点 2026-11-23) [2]
- **2026年11月のセキュリティ更新:** 1.31.10 / 1.30.8でCVE-2026-132779（ssl_early_dataのCPU過負荷）を修正。1.31.9 / 1.30.7（11月18日）でCVSS 9.2のHTTP/2 RCEであるCVE-2026-123007およびCVE-2026-123633を含む10件のCVEを修正 (時点 2026-11-23) [3]

## ファクトシート

- **原開発者:** イーゴリ・シソエフ（Igor Sysoev） [1]
- **保守主体:** F5, Inc.（NGINX Product Group） [1]
- **初回公開日:** 2004年10月4日（バージョン0.1.0） [1]
- **メインライン版（2026年11月）:** 1.31.10（2026年11月23日） (時点 2026-11-23) [3]
- **安定版（2026年11月）:** 1.30.8（1.31.10とともにCVE-2026-132779の影響を受けないバージョンとして記載） (時点 2026-11-23) [2]
- **実装言語:** C [1]
- **ライセンス:** 2条項BSDライセンス [1]
- **対応プロトコル:** HTTP/1.x、HTTP/2、HTTP/3（QUIC）、TLS/SSL、FastCGI、uwsgi、SCGI、gRPC、IMAP/POP3/SMTP、TCP/UDP [1]

## nginxの概要と非同期イベント駆動型アーキテクチャ

nginxは、単一サーバーで1万件以上の同時クライアント接続を処理する**C10k問題**を解決するため、ロシアのソフトウェアエンジニアであるイーゴリ・シソエフによって2002年に設計され、2004年10月4日に2条項BSDライセンスの下でオープンソースとして公開された。[1] 接続ごとにスレッドやプロセスを生成する従来のWebサーバーとは異なり、nginxは単一の特権**マスタープロセス**（設定ファイルの読み込み、特権ポートへのバインド、ワーカープロセスのライフサイクル管理を担当）と、1つ以上の非特権・シングルスレッドの**ワーカープロセス**（およびオプションのキャッシュローダー・キャッシュマネージャープロセス）で構成される。[1]

各ワーカープロセスは、オペレーティングシステム固有のカーネル通知機構（Linuxの`epoll`、FreeBSDおよびmacOSの`kqueue`、Solarisのevent ports）を基盤としたノンブロッキングの非同期イベントループを実行する。[1] ワーカープロセスは接続ごとに新しいOSスレッドを生成したり、ディスクI/OやネットワークI/Oでブロックされたりしないため、nginxは予測可能なメモリ使用量で静的アセットの配信、TLS 1.3の終端、HTTP/2およびHTTP/3（QUIC）ストリームの多重化、gRPCやWebSocketトラフィックのプロキシ、およびアップストリームアプリケーションサーバーの負荷分散（`http`、`stream`、`mail`コンテキスト）を実行できる。[1] 2019年5月には、アプリケーションデリバリーベンダーの**F5, Inc.**がNGINX, Inc.を買収し、NGINX Open Source（`nginx.org`）および商用ディストリビューションであるNGINX Plusの双方の開発を継続している。[1][2]

## nginxのリリースブランチ：メインライン1.31.xと安定版1.30.x

nginxプロジェクトは、`nginx.org`上で2つのオープンソースリリースブランチを並行して保守している。[1][2] - **メインラインブランチ**（奇数のマイナーバージョン番号、現在は**1.31.x**、2026年11月23日時点で**1.31.10**）：すべての新機能、プロトコル拡張、バグ修正、およびセキュリティパッチが提供される。[2][3] - **安定版ブランチ**（偶数のマイナーバージョン番号、現在は**1.30.x**、2026年11月時点で**1.30.8**）：毎年メインラインブランチから分岐され、モジュールAPIの後方互換性を損なう変更を導入することなく、重大なバグ修正とセキュリティ修正のバックポートのみを受け取る。[1][2]

**2026年11月18日**、nginxプロジェクトは**nginx 1.31.9**および**nginx 1.30.7**をリリースし、メインライン1.31.9における計10件のCVE（うち9件は安定版1.30.xにも影響）を一括修正した。対象範囲はHTTP/2、HTTP/3、アップストリームプロキシ処理、非同期DNSリゾルバー、メールプロキシモジュール、`try_files`/`alias`によるURI処理、および`stream`のTLS/SNI処理に及ぶ。[2][3] その5日後の**2026年11月23日**には、**CVE-2026-132779**（バージョン`1.21.4-1.31.9`に影響し、TLS 1.3で`ssl_early_data`ディレクティブを使用した場合にクライアントが過剰なCPU使用率を引き起こす可能性がある中程度の脆弱性）およびバックエンドへのSSL接続時にnginxがCPUを占有する可能性があるバグを修正した**nginx 1.31.10**をリリースした（`nginx.org`のセキュリティアドバイザリページでは**1.31.10+**および**1.30.8+**が影響を受けないバージョンとして記載されている）。[2][3]

## 2026年11月のnginxセキュリティアドバイザリとHTTP/2 RCE脆弱性

2026年11月18日および11月23日の更新を通じて、nginxプロジェクトは1.31.xメインラインブランチおよび1.30.x安定版ブランチで修正された計11件の脆弱性を公表した。[2][3] 11月18日の更新（1.31.9および1.30.7）では、クラウドセキュリティ研究機関である**Wiz Research**が2件の緊急かつ未認証のHTTP/2リモートコード実行（RCE）脆弱性、すなわち**CVE-2026-123007**と**CVE-2026-123633**の詳細を公表した。両脆弱性はNISTの米国脆弱性データベース（NVD）で**CVSS v4.0基本値9.2（Critical）**および**CVSS v3.1基本値8.1（High）**と評価されており、コミュニティのアドバイザリでは**nginx2root** / **nginx2shell**の通称で呼ばれている。[4][5][6][8]

| CVE識別子 | 影響モジュールおよびバージョン | 脆弱性のメカニズム | 深刻度 / 修正バージョン |
| --- | --- | --- | --- |
| **CVE-2026-132779** | TLS 1.3 `ssl_early_data`（nginx 1.21.4 - 1.31.9） | `ssl_early_data`ディレクティブを使用している場合、クライアントが過剰なCPU使用率を引き起こす可能性がある。[2][3] | Medium（`nginx.org`）、1.31.10+、1.30.8+で修正 |
| **CVE-2026-123007** | `ngx_http_v2_module`（nginx 1.9.5 - 1.31.8、10年間潜在した脆弱性） | 細工された`SETTINGS`および`WINDOW_UPDATE`フレームによりHTTP/2の`send_window`フロー制御計算で整数アンダーフローが発生し、ヒープベースのバッファオーバーフロー（`CWE-191`、`CWE-122`）につながる。[2][4][6] | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High、1.31.9+、1.30.7+で修正 |
| **CVE-2026-123633** | `ngx_http_v2_module` + アップストリームプロキシ（1.19.7 - 1.31.8） | `worker_connections`が枯渇した状態でHTTP/2クライアント接続がアップストリームバックエンドへプロキシされる際に解放後使用（Use-After-Free、`CWE-416`）が発生する。[2][5][6] | CVSS v4.0: 9.2 Critical / v3.1: 8.1 High、1.31.9+、1.30.7+で修正 |
| **CVE-2026-121810** | `ngx_http_v3_module`（1.25.0 - 1.31.8） | `worker_connections`が枯渇した際にHTTP/3 QUIC処理で解放後使用が発生する。[2][3] | Medium（`nginx.org`）、1.31.9+、1.30.7+で修正 |
| **CVE-2026-123634** | コア非同期DNS `resolver`（0.6.18 - 1.31.8） | `resolver`が設定されている環境で、サブリクエスト内の同時名前解決中に解放後使用が発生する。[2][3] | Medium（`nginx.org`）、1.31.9+、1.30.7+で修正 |
| **CVE-2026-113425** | `ngx_mail_module`（0.5.33 - 1.31.8） | メールプロキシサーバーモジュールにおける解放後使用。[2][3] | Major（`nginx.org`）、1.31.9+、1.30.7+で修正 |

2026年11月18日にnginx 1.31.9で修正された残りの5件の脆弱性（1.30.7では4件）は、**CVE-2026-125283**（`try_files`と`alias`ディレクティブを組み合わせた場合のバッファオーバーフロー）、**CVE-2026-120967**（`stream`の同期SSLハンドシェイクにおけるSNI経由のSSLクライアント証明書検証バイパス）、**CVE-2026-120993**（動的SSL証明書読み込みを伴うPROXY protocol v2におけるワーカーのNULLポインタ参照およびセグメンテーションフォルト、メインライン1.31.4 - 1.31.8に影響）、**CVE-2026-123640**（`ngx_stream_ssl_preread_module`における不正なClientHelloメッセージの検証不備）、および**CVE-2026-118899**（SSL/TLS 1.3経由でクライアントリクエストボディを読み込む際のワーカープロセス無限ループ）である。[2][3]

nginxの変更履歴（CHANGES）では、CVE-2026-123007の発見者としてXint.ioが、CVE-2026-123633の発見者としてVexera AIのAlbertがクレジットされている。[3]

## nginxにおけるCVE-2026-123007およびCVE-2026-123633の技術分析

2026年11月のnginxアドバイザリの中でも、**CVE-2026-123007**と**CVE-2026-123633**は標準的なHTTP/2構成に対して未認証でリモートコード実行を可能にするため、Center for Internet Security（CIS Advisory `2026-136`）およびWiz Researchから緊急の警告が発出された。[6][7][8] - **CVE-2026-123007（10年間潜在していたHTTP/2フロー制御ヒープオーバーフロー）**：2015年9月のnginx 1.9.5で`ngx_http_v2_module`が登場して以来存在していた脆弱性であり、`http2`が有効化された任意のserverブロックに対して単一のHTTP/2 TCP接続で引き起こすことができる。[4][6][8] データフレームがキューに積まれている状態で、攻撃者が細工されたHTTP/2の`SETTINGS`（`SETTINGS_INITIAL_WINDOW_SIZE`）および`WINDOW_UPDATE`フレームを送信すると、`send_window`の計算で整数アンダーフローが発生し、nginxワーカープロセス内でヒープベースのバッファオーバーフローを引き起こす。[4][6] - **CVE-2026-123633（HTTP/2アップストリームプロキシ解放後使用）**：HTTP/2を有効にし、リクエストをアップストリームバックエンドへプロキシするサーバー（`proxy_pass`、`fastcgi_pass`、`uwsgi_pass`、`scgi_pass`、または`grpc_pass`）に影響する。これはIngressコントローラー、APIゲートウェイ、リバースプロキシにおける標準的な構成である。[5][6] 攻撃者が多数の同時接続を開いてアップストリーム接続の確立中に`worker_connections`を枯渇させることで、ワーカープロセスのヒープ内で解放後使用（Use-After-Free）が引き起こされる。[5][6]

攻撃者はnginxのプールアロケータ（`ngx_pool_t`）の状態を精密に制御（ヒープグルーミング）することで、ワーカーメモリ内の関数ポインタを上書きし、nginxワーカーユーザーの権限で任意のコードを実行できる。[6][8]

**対策**：管理者は、11月18日の修正（`1.31.9+` / `1.30.7+`）と11月23日の`CVE-2026-132779`修正の双方を含む**nginx 1.31.10+**（メインライン版）または**nginx 1.30.8+**（安定版）へアップグレードすべきである。[2][3][7] 即時のアップグレードが困難な場合の暫定的な回避策としては、信頼できないリスナー上で`http2`、`http3`、`ssl_early_data`を無効化し、未使用の動的`resolver`ブロックを削除するとともに、nginxワーカープロセスが`root`ではなく非特権アカウントで実行されていることを確認することが挙げられる。[2][3][6][7]

## よくある質問

### 2026年11月23日現在、nginxの最新バージョンは何ですか？

2026年11月23日現在、オープンソース版nginxの最新バージョンはメインラインブランチの1.31.10（2026年11月23日のCHANGESでリリース）と安定版ブランチの1.30.8（セキュリティアドバイザリページにて1.31.10+とともにCVE-2026-132779の影響を受けないバージョンとして記載）です。これらは、10件のCVEを修正した2026年11月18日の1.31.9および1.30.7リリースに続き、CVE-2026-132779（TLS 1.3でssl_early_data使用時の過剰なCPU使用率）を修正しています。 [2][3]

### nginx 1.31.10および1.30.8で修正されたCVE-2026-132779とはどのような脆弱性ですか？

CVE-2026-132779は、2026年11月23日に公表された中程度の深刻度の脆弱性で、nginx 1.21.4から1.31.9までに影響します。TLS 1.3のssl_early_dataディレクティブを有効にしている場合、クライアントが過剰なCPU使用率を引き起こす可能性があります。この問題はnginx 1.31.10+および1.30.8+で解決されています。 [2][3]

### nginxのCVE-2026-123007とCVE-2026-123633とはどのような脆弱性ですか？

CVE-2026-123007とCVE-2026-123633は、Wiz Researchが解析し、2026年11月18日にnginx 1.31.9および1.30.7で修正された2件の緊急なHTTP/2メモリ破壊脆弱性（CVSS v4.0スコア9.2 / CVSS v3.1スコア8.1）です。CVE-2026-123007はHTTP/2のsend_windowフロー制御処理における10年間潜在していた整数アンダーフローおよびヒープバッファオーバーフロー（nginx 1.9.5以降に存在）であり、CVE-2026-123633はHTTP/2アップストリームプロキシ処理でworker_connectionsが枯渇した際に発生する解放後使用（Use-After-Free）脆弱性です。 [2][4][5][6]

### nginxのメインラインブランチと安定版ブランチの違いは何ですか？

nginxのメインラインブランチ（1.31.xなどの奇数マイナーバージョン）は、すべての新機能、バグ修正、セキュリティアップデートを受け取り、nginxチームによって大半の環境で推奨されています。一方、安定版ブランチ（1.30.xなどの偶数マイナーバージョン）は、サードパーティ製モジュールの互換性を維持するため、重大なバグ修正とセキュリティ修正のバックポートのみを受け取ります。 [1][2]

### 即座にアップグレードできない場合、管理者は2026年11月のnginx脆弱性をどのように緩和できますか？

完全な修正はnginx 1.31.10+または1.30.8+へのアップグレードのみです。暫定的な回避策として、管理者は外部公開リスナー上でHTTP/2、HTTP/3、およびssl_early_dataを無効化し、nginxワーカープロセスがroot権限で実行されない設定になっていることを確認できます。 [2][3][6][7]

## 引用できる文

- 2026年11月23日、nginxはTLS 1.3でのssl_early_data使用時に過剰なCPU使用率を引き起こす中程度の脆弱性CVE-2026-132779（1.21.4-1.31.9に影響）を修正するため、メインライン版1.31.10をリリースした（security_advisories.htmlでは1.31.10+および1.30.8+が影響を受けないバージョンとして記載されている）。 [2][3]
- nginxは2026年11月18日にメインライン版1.31.9および安定版1.30.7をリリースし、1.31.9で10件（1.30.7では9件）のセキュリティ脆弱性を修正した。 [2][3]
- CVE-2026-123007およびCVE-2026-123633は、NVDでCVSS v4.0基本値9.2（Critical）およびCVSS v3.1スコア8.1（High）が付与され、未認証でのリモートコード実行を可能にするHTTP/2の脆弱性である。 [4][5][6]
- CVE-2026-123007は、nginxバージョン1.9.5から1.31.8および1.30.6に影響したngx_http_v2_moduleのsend_window処理における整数アンダーフローおよびヒープバッファオーバーフローである。 [2][4][6]
- nginxは2004年10月4日にイーゴリ・シソエフによって2条項BSDライセンスの下で初公開され、2019年5月以降はF5, Inc.が保守を行っている。 [1]

## 年表

- 2004-10-04: イーゴリ・シソエフが2条項BSDライセンスの下でnginx 0.1.0を一般公開した。 [1]
- 2015-09: nginx 1.9.5がHTTP/2対応のngx_http_v2_moduleを導入した。この実装には後にCVE-2026-123007として特定されるsend_windowロジックが潜在していた。 [2][6]
- 2019-05: F5, Inc.がNGINX, Inc.の買収を完了した。 [1]
- 2026-11-18: nginxが1.31.9（メインライン版）および1.30.7（安定版）をリリースし、CVSS 9.2のHTTP/2 RCE脆弱性であるCVE-2026-123007およびCVE-2026-123633に加え、CVE-2026-121810、CVE-2026-123634、CVE-2026-113425、CVE-2026-125283など計10件のCVEを修正した。 [2][3][6]
- 2026-11-23: nginxがメインライン版1.31.10をリリースし（security_advisories.htmlでは1.31.10+および安定版1.30.8+を非脆弱として記載）、CVE-2026-132779（TLS 1.3でssl_early_data使用時の過剰なCPU使用率）およびバックエンドSSL接続におけるCPU使用率バグを修正した。 [2][3]

## 出典

1. nginx news and official project documentation. nginx.org / F5, Inc.. https://nginx.org/en/ (閲覧 2026-11-23; tier 3: official site)
2. nginx security advisories. nginx.org. 公開 2026-11-23. https://nginx.org/en/security_advisories.html (閲覧 2026-11-23; tier 3: official site)
3. Changes with nginx 1.31.10 (23 Nov 2026) and 1.31.9 (18 Nov 2026). nginx.org. 公開 2026-11-23. https://nginx.org/en/CHANGES (閲覧 2026-11-23; tier 3: official site)
4. NVD - CVE-2026-123007 Detail (nginx HTTP/2 send_window integer underflow and heap-based buffer overflow). National Vulnerability Database (NIST). 公開 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123007 (閲覧 2026-11-23; tier 1: government or public registry)
5. NVD - CVE-2026-123633 Detail (nginx HTTP/2 upstream proxy worker_connections use-after-free). National Vulnerability Database (NIST). 公開 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123633 (閲覧 2026-11-23; tier 1: government or public registry)
6. Unauthenticated Remote Code Execution in NGINX: CVE-2026-123633 and CVE-2026-123007 | Wiz Blog. Wiz Research. 公開 2026-11-18. https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities (閲覧 2026-11-23; tier 3: official site)
7. Multiple Vulnerabilities in NGINX Could Allow for Remote Code Execution (CIS Advisory 2026-136). Center for Internet Security (CIS). 公開 2026-11-19. https://www.cisecurity.org/advisory/multiple-vulnerabilities-in-nginx-could-allow-for-remote-code-execution_2026-136 (閲覧 2026-11-23; tier 2: academic or news)
8. 10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers Execute Code on Servers. The Hacker News. 公開 2026-11-19. https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "nginx." 版 790ed871, 2026-11-23. https://mimirwiki.com/ja/wiki/nginx
