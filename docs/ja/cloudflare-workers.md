---
title: "Cloudflare Workers"
subtitle: "V8アイソレートとworkerdランタイム上でJavaScript、TypeScript、Python、Rust、WebAssemblyを実行するCloudflareのサーバーレス実行プラットフォーム"
canonical_url: https://mimirwiki.com/ja/wiki/cloudflare-workers
language: ja
page_class: entity
revision_sha256: 2db4e821dba4aa07d81062be49d650bdd92e0e2830357ab141151a681bd5abd4
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/ja/wiki/cloudflare-workers.md
  txt: https://mimirwiki.com/ja/wiki/cloudflare-workers.txt
  json: https://mimirwiki.com/ja/wiki/cloudflare-workers.json
  jsonld: https://mimirwiki.com/ja/wiki/cloudflare-workers.jsonld
translations:
  en: https://mimirwiki.com/wiki/cloudflare-workers
  ko: https://mimirwiki.com/ko/wiki/cloudflare-workers
  zh: https://mimirwiki.com/zh/wiki/cloudflare-workers
  es: https://mimirwiki.com/es/wiki/cloudflare-workers
---

# Cloudflare Workers

> Cloudflare Workersは、V8アイソレートとworkerdランタイムを用いてCloudflareのグローバルネットワーク上でJavaScript、TypeScript、Python、Rust、WebAssemblyを実行するCloudflareのサーバーレスコンピュートプラットフォームである。2017年に発表され、Web標準API、Node.js互換性、ストレージバインディングを提供する。2026-11-23時点で、Workers Freeプランおよび月額最低5米ドルのWorkers Paidプランが提供されている。

Cloudflare Workersは、Cloudflare, Inc.が運営するサーバーレスコンピュートプラットフォームであり、V8アイソレートとオープンソースのworkerdランタイムを用いて、Cloudflareのグローバルネットワーク上で開発者のアプリケーションを実行する。2017年9月29日に発表された同プラットフォームは、WebプラットフォームAPIおよびネイティブ実装されたNode.js APIのサブセットを備え、JavaScript、TypeScript、Python、Rust、WebAssembly（Wasm）のワークロードを実行する。Cloudflareは2022年9月27日、Cloudflare Workersの基盤となるJavaScriptおよびWebAssemblyサーバーランタイムworkerdをApache-2.0ライセンスで公開した。2026-11-23時点で、Cloudflareは1日あたり100,000リクエストを上限とするWorkers Freeプランと、Standard使用量モデルのもとで月額最低5米ドル（$5 USD）から利用でき、エグレスや帯域幅料金のかからないWorkers Paidプランを提供している。

**別名:** Workers, CF Workers, workerd

## 主要な事実

- **開発元:** Cloudflare, Inc. [2]
- **実行モデル:** Cloudflareのグローバルネットワーク上のV8アイソレート [6]
- **オープンソースランタイム:** workerd（Apache-2.0ライセンス） [10]
- **Workers Free上限:** 1日あたり100,000リクエスト、呼び出しあたりCPU時間10 ms (時点 2026-11-23) [4]
- **Workers Paid料金:** 月額最低5米ドル（1,000万リクエストおよび3,000万CPU ms込み） (時点 2026-11-23) [4]

## ファクトシート

- **開発元:** Cloudflare, Inc.（SEC CIK 0001477333） [2]
- **初回発表日:** 2017年9月29日 [12]
- **実行エンジン:** V8 JavaScriptエンジン（アイソレート） [6]
- **オープンソースランタイム:** workerd（Apache-2.0ライセンス、2022年9月27日にベータ発表） [11]
- **ファーストクラス対応言語:** JavaScript、TypeScript、Python、Rust (時点 2026-11-23) [7]
- **WebAssembly対応言語:** C、C++、Kotlin、GoなどのWebAssembly（Wasm）ターゲット (時点 2026-11-23) [7]
- **Node.js互換性:** 互換性日付2026-08-04以降でデフォルト有効 (時点 2026-11-23) [9]
- **Workers Freeプラン:** 1日あたり100,000リクエスト、呼び出しあたりCPU時間10 ms (時点 2026-11-23) [4]
- **Workers Paidプラン:** 月額最低5米ドル（$5 USD）、月間1,000万リクエスト・3,000万CPU ms込み、エグレス料金なし (時点 2026-11-23) [4]
- **アイソレートあたりメモリ:** 128 MB（JavaScriptヒープおよびWebAssembly割り当て） (時点 2026-11-23) [5]
- **Workerサイズ・起動時間:** 非圧縮バンドル64 MiB、起動時間上限1秒 (時点 2026-11-23) [5]
- **最大CPU時間（Paid）:** HTTPリクエストあたり5分（デフォルト30秒）、1時間以上間隔のCron Triggersは15分 (時点 2026-11-23) [5]

## Cloudflare WorkersのV8アイソレートアーキテクチャとworkerdランタイム

Cloudflare Workersは、[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)のグローバル分散サーバーネットワーク全体で、V8 JavaScriptエンジンを用いてユーザーアプリケーションを実行する。[6] 各サーバーはWorkersランタイムのインスタンスを稼働させており、各ランタイムインスタンスは独立したメモリサンドボックスを持つ軽量な実行コンテキストであるV8アイソレートを数百から数千個ホストしている。[6] コンテナベースのサーバーレスアーキテクチャが関数ごとに個別の言語ランタイムプロセスや仮想マシンを起動するのに対し、Workersランタイムはコンテナごとに単一のV8ホストプロセスを初期化し、そのプロセス内のアイソレート上でユーザースクリプトを実行する。[6] Cloudflareのドキュメントによれば、V8アイソレートはコンテナや仮想マシン上のNode.jsプロセスと比べて約100倍高速に起動し、起動時のメモリ消費量も1桁以上少ない。[6]

`*.workers.dev` サブドメインまたはCloudflare管理ドメインへルーティングされたリクエストは、ESモジュール構文でエクスポートされたWorkerの `fetch(request, env, ctx)` ハンドラを呼び出し、`Response` オブジェクトを受け取る。[6] 各Workerインスタンスは、非同期I/Oの完了を待機する同時リクエストを含め、単一スレッドのイベントループ上でリクエストを処理する。[6] ホストのリソースが逼迫した場合、Workerがリソース制限に達した場合、またはコードがサンドボックス脱出を試みるような不審な挙動を示した場合には、アイソレートが破棄（evict）されることがある。[6] 2つのリクエストがWorkerの同じインスタンスに届く保証はないため、Cloudflareはグローバルスコープに変更可能な状態（mutable state）を保存しないよう推奨している。[6]

Cloudflare Workersを支えるオープンソースのサーバーランタイムは `workerd`（発音は「ワーカーディー」）であり、Apache-2.0ライセンスのもとでGitHubに公開されている。[10][11] 開発者は `workerd` を利用して、Workers互換アプリケーションのセルフホスティング、ローカル開発・テスト環境の構築、あるいはプログラマブルなフォワード・リバースHTTPプロキシの運用を行うことができる。[10] Cloudflareは `workerd` について次の6つの設計原則を示している。[10]

- サーバーファースト設計：CLIやGUI環境を除外し、サーバーワークロードに特化している。[10]
- 標準ベースの組み込みAPI：`fetch()` などのWebプラットフォーム仕様に準拠している。[10]
- ナノサービス（Nanoservices）：独立してデプロイ可能なコンポーネント同士が同一のスレッドおよびプロセス内で相互に呼び出しを行える。[10]
- 均質デプロイメント（Homogeneous deployment）：クラスタ内の全マシンに同一の構成をデプロイすることでロードバランシングを簡素化する。[10]
- ケーパビリティバインディング（Capability bindings）：明示的な参照を通じてサービスや外部リソースを接続し、サーバーサイドリクエストフォージェリ（SSRF）のリスクを低減する。[10]
- 日付ベースの後方互換性：各 `workerd` のバージョン識別子が対応する最大の互換性日付を表し、古い互換性日付に対して過去のAPI挙動を維持する。[10]

`workerd` はBazelでビルドされ、LinuxおよびmacOS（`x86-64` および `arm64`）、ならびにWindows（`x86-64`）上でテストされている。[10] ネイティブ設定にはCap'n Protoテキスト形式を使用し、`workerd serve wrangler.jsonc` を用いることで `esbuild` でバンドルされたWrangler設定も読み込める。[10] 2026-11-25時点で、`cloudflare/workerd` GitHubリポジトリはスター数9.3k、フォーク数846、コミット数14,147を記録している。[10] Cloudflareは、単体の `workerd` は実装バグに対する堅牢なサンドボックスとして単独利用するには適さず、信頼できないコードには外側の仮想マシンやサンドボックスが必要であると警告する一方、ホスト型のCloudflare Workersサービスでは追加の多層防御（defense-in-depth）レイヤーが適用されていると説明している。[10]

## Cloudflare WorkersのランタイムAPI、Web標準、Node.js互換性

Cloudflare Workersは、アプリケーションコードがブラウザとサーバーランタイム間でJavaScriptのWeb標準に従えるよう、WebプラットフォームAPIを実装している。[8] 組み込みランタイムAPIには、Fetch、Request、Response、Headers、Cache、Streams（`ReadableStream`、`WritableStream`、`TransformStream`）、Web Crypto、WebSockets、TCPソケット、Encoding、EventSource、MessageChannel、Performanceとタイマー、Scheduler、HTMLRewriter、リモートプロシージャコール（RPC）、Context（`ctx`）、Bindings（`env`）、さらにFetch、Scheduled、Queue、Email、Alarm、Tail、Connectの各イベントを扱うイベントハンドラが含まれる。[8]

CloudflareのランタイムAPIドキュメントは、WorkersがWinterCG系JavaScriptランタイム間での相互運用性を確保するためにWebプラットフォームAPIを再利用していると説明している。[8] より広範な標準化エコシステムにおいては、WinterTC（Technical Committee on Web-interoperable Server Runtimes）として知られるEcma Internationalの技術委員会TC55が、サーバーサイドJavaScriptランタイム向けにWebと共通の最小共通APIを標準化し、WHATWGやW3CとWeb API仕様で連携するとともに、相互運用可能なサーバーサイドAPIの標準を公開している。[1]

Node.jsライブラリに依存するnpmパッケージを実行するため、Cloudflare Workersは2つの仕組みでNode.js APIのサブセットを提供している。すなわち、Node.jsのCurrentリリースを対象としたネイティブ組み込み実装と、Wranglerが `unenv` を通じて注入するポリフィルシム（未実装メソッドはno-opまたはエラーを送出）である。[9] ランタイムの挙動はWorkerの互換性日付と互換性フラグによって制御される。[8][9] 互換性日付が2026-08-04以降の場合、Cloudflare Workersは `nodejs_compat` と `nodejs_compat_v2` の双方をデフォルトで有効化し、オプトアウトするプロジェクトは `no_nodejs_compat` と `no_nodejs_compat_v2` を追加する。[9] 2024-09-23から2026-08-03までの互換性日付では、`nodejs_compat` フラグによってオプトインすることで `unenv` ポリフィルの自動注入も有効となり、別途 `nodejs_als` フラグを使えば `AsyncLocalStorage` のみを有効化できる。[9]

2026-11-23時点で、Cloudflareは次のNode.jsランタイム互換性カバレッジを公表している。[9]

- ネイティブサポートモジュール：`assert`、`AsyncLocalStorage`、`Buffer`、`crypto`、Debugger（Chrome DevTools連携）、Diagnostics Channel、Errors、`EventEmitter`、`fs`、Globals、`http`、`https`、`net`、`path`、`process`、Punycode（非推奨）、Query strings、`stream`、`StringDecoder`、`timers`、`url`、`util`、Web Crypto API、Web Streams API、`zlib`。[9]
- 部分サポートモジュール：Console、`dns`、Module、OS、Performance hooks、Test runner、`tls`（TLS/SSL）。[9]
- 互換性日付に応じて `nodejs_compat` とともに有効化されるインポート専用の非機能スタブモジュール：`node:http2`（2025-09-01）、`node:vm`（2025-10-01）、`node:cluster`・`node:domain`・`node:trace_events`・`node:wasi`（2025-12-04）、`node:_stream_wrap`・`node:dgram`・`node:inspector`・`node:sqlite`（2026-01-29）、`node:child_process`・`node:readline`・`node:repl`・`node:tty`・`node:v8`・`node:worker_threads`（2026-03-17）。[9]

## Cloudflare Workersの対応言語、開発ツール、プラットフォームバインディング

Cloudflare Workersは、複数のプログラミング言語、ローカル開発ツール、Webフレームワーク、およびCloudflareプラットフォームサービスへの直接バインディングをサポートしている。[3][7] 2026-11-23時点で、同プラットフォームはJavaScript、TypeScript、Python（Python Workers経由）、Rust（ドキュメントナビゲーション上はBeta表記）の4言語をファーストクラス対応言語として挙げている。[3][7] また、WebAssembly（Wasm）バイナリサポートを通じて、C、C++、Kotlin、GoなどWasmへコンパイル可能な言語で記述されたWorkerもデプロイできる。[7]

開発者はWrangler CLI、Cloudflare Vite Plugin、Miniflare、Vitest連携、さらにWorkers Buildsによる組み込みCI/CD（GitHubおよびGitLab連携）やGitHub Actions、GitLab CI/CDといった外部パイプラインを用いてWorkerの構築・テスト・デプロイを行う。[3] Cloudflareは、React、Vue、SvelteKit、Next.js（OpenNextアダプタを使用）、Astro、React Router、Remix 3、Nuxt、Angular、Hono、TanStack Start、Qwik、Solid、FastAPI、FlaskなどのWebおよびAPIフレームワーク向けガイドを公開している。[3] 静的なフロントエンドアセットはWorkerロジックとともにCloudflareの[コンテンツデリバリネットワーク](https://mimirwiki.com/ja/wiki/content-delivery-network)およびキャッシュを通じて直接配信でき、Smart Placementは外部データストアに向けたバックエンドリクエストのルーティングを最適化する。[3] 2026-11-23時点で、Cloudflare Workersのドキュメントでは [llms.txt](https://mimirwiki.com/ja/wiki/llms-txt) インデックス、`llms-full.txt`、ページごとの [Markdown](https://mimirwiki.com/ja/wiki/markdown) 表示、およびCloudflareの [Model Context Protocol](https://mimirwiki.com/ja/wiki/model-context-protocol) サーバーへのリンクも提供されている。[3]

[SEC EDGAR](https://mimirwiki.com/ja/wiki/sec-edgar)に提出されたCloudflareの2025会計年度提出書類において、CloudflareはCloudflare Workers、Cloudflare Workers for Platforms（プラットフォーム顧客がエンドユーザーのコードを実行できるマルチテナント型マネージド実行環境）、およびCloudflare PagesをCompute開発者ソリューションとして分類している。[2] Workersは明示的な `env` バインディングを通じて、ストレージ、コンピュート、AI、メディアの各サービスに接続する。[2][3]

- ストレージおよびデータベース：Durable Objects（ステートフルなリアルタイム調整）、D1（サーバーレスSQLデータベース）、Workers KV（エッジキャッシュ読み取りを備えたグローバル分散キーバリューストレージ）、Queues（エグレス料金なしの非同期メッセージキュー）、Hyperdrive（外部データベース向けのコネクションプーリング、ルーティング最適化、クエリキャッシュ）、R2（エグレス料金なしのオブジェクトストレージ）。[2][3]
- コンピュートおよびAI：Workers AI（サーバーレスGPU上の機械学習推論）、Workflows（自動リトライを備えた永続的なマルチステップ実行）、Vectorize（埋め込みおよびセマンティック検索用ベクトルデータベース）、Browser Run（プログラマブルなサーバーレスブラウザインスタンス）、Serviceバインディング（Worker間のHTTPおよび `WorkerEntrypoint` RPC呼び出し）、Dynamic Worker Loaders、Workers for Platforms Dispatcher。[2][3]
- メディアおよび運用バインディング：Cache、Images、Stream、Media Transformations、Assets、Analytics Engine、Rate Limiting、Secrets、Secrets Store（Beta）、mTLS証明書、環境変数。[3]

## Cloudflare Workersのプランと料金体系

Cloudflare Workersは、Workers Freeプラン、月額最低5米ドル（$5 USD）のWorkers Paidプラン、および契約ベースのWorkers Enterpriseアカウントで提供されている。[4] アカウントはデフォルトでWorkers Freeに設定され、Workers、Pages Functions、Workers KV、Hyperdriveの日次無料枠が付与される。[4] Workers PaidはStandard使用量モデルを採用し、Workers、Pages Functions、Workers KV、Hyperdrive、Durable Objectsの月間枠を含み、データ転送（エグレス）や帯域幅に対する追加料金は課されない。[4] すべてのPages FunctionsはWorkersと同一の課金ルールに従う。[4] 一部の古い構成ではレガシー使用量モデル（Workers UnboundおよびWorkers Bundled）が残っているが、Cloudflareは2024年3月1日にBundled WorkersをStandard料金体系へ移行し、50ミリ秒の自動CPU時間上限を適用した。[4]

2026-11-23時点で、CloudflareはFreeおよびPaid（Standard）プランにおけるWorkersコンピュート料金を以下の通り公表している。[4]

| 項目 | Workers Free | Workers Paid（Standard） |
| --- | --- | --- |
| 基本サブスクリプション | $0 | 月額最低$5 USD |
| インバウンドリクエスト | 1日あたり100,000件 | 月間1,000万件込み、以降100万件ごとに$0.30 |
| 実行継続時間（実経過時間） | 無料 | 無料・上限なし |
| CPU時間 | 呼び出しあたり10 ms | 月間3,000万CPU ms込み、以降100万CPU msごとに$0.02 |
| 呼び出しあたり最大CPU時間 | 10 ms | HTTPは5分（デフォルト30秒）、1時間以上間隔のCron Triggersは15分 |
| 静的アセットリクエスト | 無料・無制限 | 無料・無制限 |

Cloudflareは、Workerから発行されるアウトバウンドのサブリクエストには課金しない。[4] WebSocket接続は初期のUpgradeハンドシェイク時に1リクエストとして計上され、ルーティングされるメッセージにはメッセージ単位のリクエスト料金は発生しない。[4] Workers Cachingが有効な場合、キャッシュヒットはリクエスト単価で課金され（静的アセットおよびWorker間呼び出しを含む）、CPU時間はキャッシュミスまたはバイパス時にWorkerが実行された場合のみ課金される。[4] アカウント所有者は、無料枠超過後のリクエストおよびCPU料金（月額5米ドルの基本料金を除く）が指定のしきい値を超えた際に新規呼び出しをブロックするWorkers支出上限を設定できるほか、ブロックを伴わないメールアラートも設定可能である。[4]

CloudflareのWorkers料金ページでは、2026-11-23時点における関連開発者サービスの無料枠および超過単価も以下の通り掲載している。[4]

| サービスおよび指標 | Workers Free | Workers Paid |
| --- | --- | --- |
| Workers Logsの書き込みイベント数 | 1日あたり200,000件（3日間保持） | 月間2,000万件込み、以降100万件ごとに$0.60（7日間保持） |
| Workers Trace Events Logpush | 利用不可 | 月間1,000万リクエスト込み、以降100万件ごとに$0.05 |
| Workers KVのキー読み取り | 1日あたり100,000件 | 月間1,000万件込み、以降100万件ごとに$0.50 |
| Workers KVのキー書き込み・削除・一覧取得 | 各1日あたり1,000件 | 各月間100万件込み、以降各100万件ごとに$5.00 |
| Workers KVのストレージおよび名前空間 | 1 GB、1,000名前空間 | 1 GB（+$0.50/GB-月）、最初の1,000名前空間（追加1名前空間あたり+$0.10/月） |
| Hyperdriveデータベースクエリ | 1日あたり100,000件 | 無制限 |
| Queues標準操作（64 KBメッセージチャンク単位） | 1日あたり10,000件（24時間保持、10,000キュー） | 月間100万件（+$0.40/100万件、デフォルト4日・最大14日保持、最初の10,000キュー込み、追加1キューあたり+$0.10/月） |
| Workflowsステップ数およびストレージ | 1日あたり3,000ステップ、1 GB-月（リクエストはWorkersと共有） | 月間500,000ステップ（100,000ステップごとに+$0.80）、1 GB-月（+$0.20/GB-月） |
| D1読み取り行数 | 1日あたり500万行 | 月間250億行込み、以降100万行ごとに$0.001 |
| D1書き込み行数 | 1日あたり100,000行 | 月間5,000万行込み、以降100万行ごとに$1.00 |
| D1ストレージおよびデータベース数 | 合計5 GB、10データベース | 5 GB（+$0.75/GB-月）、100,000データベース（追加1データベースあたり+$0.10/月） |

Cloudflareは、Workers Logsが2026年12月1日からCloudflare Observabilityの料金体系へ移行すること、およびWorkflowsのステップ・ストレージ課金がWorkflows課金変更履歴で告知された日付から開始されることを明記している。[4] Queuesは各メッセージに対して64 KBチャンク（1 KBは1,000バイトと定義され、内部メタデータ約100バイトを含む）ごとに操作を計測するため、一般的な配信では書き込み・読み取り・削除の3操作を消費し、エグレス料金は発生しない。[4]

## Cloudflare Workersの運用・リソース制限

Cloudflare Workersは、Workers FreeおよびWorkers Paidの両プランにおいてアカウント、実行、ネットワーク、デプロイに関する各種制限を適用している。[5] 2026-11-23時点で、Cloudflareは次の主要アカウント・プラットフォーム制限を公表している。[5]

| 制限項目 | Workers Free | Workers Paid |
| --- | --- | --- |
| 1日あたりのリクエスト数 | 1日あたり100,000件（00:00 UTCリセット） | 上限なし |
| HTTPリクエストあたりのCPU時間 | 10 ms | 5分（デフォルト30秒） |
| Cron TriggerあたりのCPU時間 | 10 ms | 5分（1時間未満の間隔）、15分（1時間以上の間隔） |
| アイソレートあたりのメモリ | 128 MB | 128 MB |
| 呼び出しあたりのサブリクエスト数 | 50件（内部サービス向けは1,000件） | 10,000件（最大1,000万件まで設定可能） |
| レスポンスヘッダー待機中の同時アウトバウンド接続数 | 6 | 6 |
| Workerあたりの環境変数（シークレットおよびテキスト） | 64個（各5 KB） | 128個（各5 KB） |
| Workerバンドルサイズ（非圧縮） | 64 MiB | 64 MiB |
| Worker起動時間（グローバルスコープ） | 1秒 | 1秒 |
| アカウントあたりのWorker数 | 100 | 500 |
| バージョン保持期間 | 30日間（最新100件を保持） | 30日間（最新100件を保持） |
| アカウントあたりのCron Triggers数 | 5 | 1,000 |
| Workerバージョンあたりの静的アセットファイル数 | 20,000件（ファイルあたり25 MiB） | 100,000件（ファイルあたり25 MiB） |

CPU時間はアクティブなスクリプト実行時間のみを計測し、`fetch()`、KV読み取り、データベースクエリといったネットワークI/Oの待機時間は含まない。[5] Cloudflareの報告によれば、平均的なWorkerのCPU時間消費量は1リクエストあたり約2.2 msであり、認証、サーバーサイドレンダリング、大規模ペイロードの解析など負荷の高い処理では通常10-20 msを使用する。[5] Workers Freeの日次リクエスト上限を超過するとError 1027が発生する（ルート設定によりWorkerをバイパスするfail open、またはエラーページを返すfail closedを選択可能）。[5] CPU時間やメモリ上限を超過するとError 1102（分析やLogpush上では `exceededCpu` または `exceededMemory`）が返され、グローバルスコープの起動時間上限1秒を超過するとエラーコード10021でデプロイが拒否される。[5]

128 MBのメモリ上限は、複数の同時リクエストを処理し得るアイソレート全体のJavaScriptヒープおよびWebAssembly割り当ての双方に適用される。[5] アイソレートが128 MBを超過すると、ランタイムは処理中のリクエストの完了を許容しつつ新規リクエストを新しいアイソレートへルーティングし、極端な高負荷時にのみ受信リクエストをキャンセルする。[5] HTTPトリガーによるWorkerにはクライアント接続維持中の厳格な実経過時間（wall-clock duration）上限はなく、`ctx.waitUntil()` によりレスポンス完了後またはクライアント切断後も最大30秒間処理を延長できる。一方、Cron Triggers、Durable Object Alarms、Queue Consumersの実経過時間は15分が上限である。[5] 定期的なランタイム更新時には、旧ランタイムバージョン上のプロセスが既存のストリーミングHTTPレスポンスやWebSocketsを終了（drain）できるよう最大20分間維持される。[5]

各トップレベルリクエスト（Serviceバインディング経由で呼び出されたWorkerを含む）では、`fetch()`、KV、Cache、R2、Queues、TCP `connect()`、アウトバウンドWebSockets全体で、レスポンスヘッダーを待機する同時アウトバウンド接続が最大6件まで許可され、それを超える接続はヘッダー到着までキューに入れられる。[5] リクエストおよびレスポンスの上限は、URLが16 KB、リクエストヘッダーおよびレスポンスヘッダーの合計がそれぞれ128 KBであり、レスポンスボディサイズに強制上限はない（ただしCDNキャッシュの上限はFree・Pro・Businessプランで512 MB、Enterpriseプランで5 GB）。[5] 受信リクエストボディの上限はドメインのCloudflareプランによって決まり、FreeおよびProで100 MB、Businessで200 MB、Enterpriseのセルフサービスで最大5 GB（超過時はHTTP 413を返却）となる。またDurable ObjectsまたはContainersから送信されるアウトバウンドHTTPボディはデフォルトで100 MiBが上限である。[5] ルーティング上限はゾーンあたり1,000ルート（`wrangler dev --remote` またはQuick Editorセッション時は50ルート）、ゾーンあたり100カスタムドメイン、Workerあたり1,000ルーティングゾーンである。[5] 500個を超えるWorkerを必要とするマルチテナントプラットフォームは、ユーザーWorker数に上限のないWorkers for Platformsを利用できる。[5]

## Cloudflare Workersの沿革と運用上の開示事項

Cloudflare Workersは2017年9月29日、Birthday Weekの期間中にCloudflare Blogにて、CloudflareのネットワークエッジでJavaScript Service Workersを実行する仕組みとして発表された。[12] その後、プラットフォームの提供開始を記録した2018年3月13日付の更新がその発表記事に追記された。[12] 初回発表から5年後の2022年9月27日、Cloudflareは `workerd` の最初のベータ版を発表し、Cloudflare Workersの基盤となるJavaScriptおよびWebAssemblyランタイムコードをApache-2.0ライセンスのオープンソースソフトウェアとして公開した。[11]

2024年3月1日、CloudflareはレガシーのBundled料金体系を利用していたアカウントをStandard使用量モデルへ移行した。[4] 互換性日付2024-09-23以降は、`nodejs_compat` を有効にするとWranglerが `unenv` ポリフィルを自動的に注入する仕様となった。[9] `node:http2`、`node:vm`、`node:sqlite`、`node:child_process`、`node:worker_threads` などのNode.jsモジュールのインポート専用スタブは、互換性日付2025-09-01から2026-03-17までの各日付以降に `nodejs_compat` とともに有効になり、互換性日付が2026-08-04以降の場合は `nodejs_compat` と `nodejs_compat_v2` がデフォルトで有効になる。[9] またCloudflareは、2026年12月1日にWorkers LogsへCloudflare Observabilityの料金体系を適用する予定である。[4]

[SEC EDGAR](https://mimirwiki.com/ja/wiki/sec-edgar)に提出された[Cloudflare](https://mimirwiki.com/ja/wiki/cloudflare)の2025会計年度提出書類において、同社は、Cloudflare Workersを含む開発者ソリューションを顧客が利用することでストレージとコンピュートという新しい市場が同社に開かれ、ストレージとコンピュートのワークロードをめぐるパブリッククラウドベンダーとの競争が増えていると考えていると述べている。[2] 同提出書類のリスク開示では、2025年6月にWorkers KVサービスが使用するサードパーティ製ストレージインフラの基盤障害により数時間にわたるサービス停止が発生し、Cloudflareのサービスおよび顧客の一部に影響が及んだ運用インシデントが報告された。[2] Cloudflareは、この2025年6月の障害が事業、経営成績、または財務状況に重大な影響を与えなかったと述べている。[2]

## よくある質問

### Cloudflare WorkersはV8アイソレートを使ってどのようにコードを実行しますか？

Cloudflare Workersは、共有のOSプロセス内でV8 JavaScriptエンジンを実行し、各ユーザーアプリケーションに対してメモリが隔離された軽量なV8アイソレートを割り当てます。単一のランタイムインスタンスが数百から数千のアイソレートを実行・切り替えながら処理するため、ランタイムプロセスの起動コストはコンテナごとに1回しか発生しません。Cloudflareの公式ドキュメントによると、アイソレートはコンテナや仮想マシン内のNode.jsプロセスと比べて約100倍高速に起動し、起動時のメモリ消費量も1桁以上少なくなります。 [6]

### workerdとは何ですか？またどのライセンスで配布されていますか？

workerd（発音は「ワーカーディー」）は、Cloudflare Workersを支えるコードベースに基づくオープンソースのJavaScriptおよびWebAssemblyサーバーランタイムであり、Apache-2.0ライセンスで配布されています。Cloudflareは2022年9月27日、ローカル開発、Workersアプリケーションのセルフホスティング、プログラマブルなHTTPプロキシ構築向けに最初のベータ版を発表しました。なおCloudflareは、信頼できないコードを単体のworkerdで実行する場合は、仮想マシンなどの外部サンドボックスが必要であると説明しています。 [10][11]

### Cloudflare Workersの料金はいくらですか？

2026-11-23時点で、Cloudflareは1日あたり100,000リクエストおよび呼び出しあたり10ミリ秒のCPU時間を含む無料のWorkers Freeプランと、アカウントあたり月額最低5米ドル（$5 USD）のWorkers Paidプランを提供しています。Standard使用量モデルでは、Workers Paidに月間1,000万リクエストと3,000万CPUミリ秒が含まれ、超過分は100万リクエストあたり0.30米ドル、100万CPUミリ秒あたり0.02米ドルが課金されます。実行継続時間（duration）やエグレス帯域幅の料金はかからず、静的アセットリクエストやWorkerから発行されるサブリクエストも無料です。 [4]

### Cloudflare WorkersのFreeプランとPaidプランにおける主なリソース制限は何ですか？

2026-11-23時点で、Workers FreeプランとWorkers Paidプランの双方に、アイソレートあたり128 MBのメモリ、非圧縮Workerバンドルサイズ64 MiB、起動時間1秒、レスポンスヘッダー待機中の同時アウトバウンド接続6件の上限が適用されます。Workers Freeでは、1日あたり100,000リクエスト、HTTP CPU時間10 ms、リクエストあたりサブリクエスト50件、アカウントあたり100個のWorkerと5個のCron Triggersに制限されます。Workers Paidでは1日あたりのリクエスト上限が撤廃され、HTTP CPU時間は最大5分（デフォルト30秒）、リクエストあたりサブリクエスト10,000件（最大1,000万件まで設定可能）、アカウントあたり500個のWorker、1,000個のCron Triggersへと引き上げられます。 [5]

### Cloudflare Workersはどのプログラミング言語をサポートしていますか？

2026-11-23時点で、Cloudflare WorkersはJavaScript、TypeScript、Python（Python Workers経由）、およびRustをファーストクラス言語としてサポートしています。さらにランタイムがWebAssembly（Wasm）を実行できるため、C、C++、Kotlin、Goなどの言語をWasmにコンパイルしてWorkers上で実行することも可能です。 [7]

### Cloudflare WorkersはNode.js APIをサポートしていますか？

はい、サポートしています。2026-11-23時点で、Cloudflare WorkersはBuffer、crypto、fs、http、https、net、path、process、stream、timers、url、util、zlib、AsyncLocalStorageなどを含むNode.js APIのサブセットをランタイム内にネイティブ実装しており、Wranglerによるunenvポリフィルおよびインポート専用のスタブモジュールで補完しています。互換性日付が2026-08-04以降であれば、追加フラグを指定しなくてもnodejs_compatとnodejs_compat_v2がデフォルトで有効になります。 [9]

## 引用できる文

- Cloudflareは2017年9月29日、Cloudflare BlogにてCloudflare Workersを発表した。 [12]
- Cloudflare Workersは、Cloudflareのグローバルネットワーク上の共有ランタイムプロセス内でホストされるV8アイソレート（isolate）上でユーザーコードを実行する。 [6]
- Cloudflareは2022年9月27日、Cloudflare Workersの基盤となるJavaScriptおよびWebAssemblyランタイムworkerdの最初のベータ版をApache-2.0ライセンスで公開した。 [10][11]
- 2026-11-23時点で、Cloudflare WorkersはJavaScript、TypeScript、Python、Rustをファーストクラス言語としてサポートしており、C、C++、Kotlin、GoなどのWebAssembly（Wasm）コンパイルターゲットもサポートしている。 [7]
- 互換性日付（compatibility date）が2026-08-04以降の場合、Cloudflare Workersはnodejs_compatおよびnodejs_compat_v2をデフォルトで有効化する。 [9]
- 2026-11-23時点で、Workers Freeプランは1日あたり100,000リクエストおよび呼び出しあたり10ミリ秒のCPU時間を許容し、Workers Paidプランは月額最低5米ドル（$5 USD）で月間1,000万リクエストと3,000万CPUミリ秒を含み、エグレス（egress）料金は発生しない。 [4]
- 2026-11-23時点で、Cloudflare WorkersはFreeプランとPaidプランの双方で、アイソレートあたり128 MBのメモリ上限、非圧縮Workerサイズ64 MiBの上限、1秒の起動時間上限を適用している。 [5]
- Cloudflareの2025会計年度SEC提出書類では、2025年6月にWorkers KVが利用するサードパーティ製ストレージインフラの障害により数時間のサービス停止が発生したものの、財務上の重大な影響はなかったと開示されている。 [2]

## 年表

- 2017-09-29: CloudflareがCloudflare BlogにてCloudflare Workersを発表し、Cloudflareのエッジで実行されるJavaScript Service Workersを導入した。 [12]
- 2018-03-13: Cloudflareが2017年9月のCloudflare Workers発表ブログ記事に、サービスの提供開始を記録する更新を追記した。 [12]
- 2022-09-27: Cloudflareがworkerdの最初のベータ版を発表し、Cloudflare WorkersのJavaScriptおよびWebAssemblyランタイムをApache-2.0ライセンスでオープンソース化した。 [11]
- 2024-03-01: CloudflareがレガシーのBundled WorkersアカウントをStandard使用量モデルへ移行し、移行されたBundled Workersに50ミリ秒の自動CPU時間上限を適用した。 [4]
- 2024-09-23: Cloudflare Workersが、この互換性日付以降でnodejs_compatが有効な場合にWrangler unenvポリフィルを自動注入する仕様を開始した。 [9]
- 2025-06: Workers KVが使用するサードパーティ製ストレージインフラの基盤障害により数時間のサービス停止が発生し、Cloudflareの2025会計年度SEC提出書類で開示された。 [2]
- 2026-08-04: Cloudflare Workersが、この互換性日付以降に設定されたWorkerでnodejs_compatおよびnodejs_compat_v2をデフォルトで有効化した。 [9]

## 出典

1. WinterTC. Ecma International (WinterTC). https://wintertc.org/ (閲覧 2026-11-23; tier 1: government or public registry)
2. cloud-20251231. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/1477333/000147733326000016/cloud-20251231.htm (閲覧 2026-11-23; tier 1: government or public registry)
3. Overview · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/ (閲覧 2026-11-23; tier 3: official site)
4. Pricing · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/pricing/ (閲覧 2026-11-23; tier 3: official site)
5. Limits · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/limits/ (閲覧 2026-11-23; tier 3: official site)
6. How Workers works · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/reference/how-workers-works/ (閲覧 2026-11-23; tier 3: official site)
7. Languages · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/languages/ (閲覧 2026-11-23; tier 3: official site)
8. Runtime APIs · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/ (閲覧 2026-11-23; tier 3: official site)
9. Node.js compatibility · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/nodejs/ (閲覧 2026-11-23; tier 3: official site)
10. GitHub - cloudflare/workerd: The JavaScript / Wasm runtime that powers Cloudflare Workers · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/workerd (閲覧 2026-11-23; tier 3: official site)
11. Introducing workerd: the Open Source Workers runtime | Cloudflare Blog. The Cloudflare Blog. 公開 2022-09-27. https://blog.cloudflare.com/workerd-open-source-workers-runtime/ (閲覧 2026-11-23; tier 3: official site)
12. Introducing Cloudflare Workers: Run JavaScript Service Workers at the Edge | Cloudflare Blog. The Cloudflare Blog. 公開 2017-09-29. https://blog.cloudflare.com/introducing-cloudflare-workers/ (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Cloudflare Workers." 版 2db4e821, 2026-11-25. https://mimirwiki.com/ja/wiki/cloudflare-workers
