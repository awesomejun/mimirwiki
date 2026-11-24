---
title: "Java4Shell (CVE-2026-114938)"
subtitle: "OpenJDK HotSpot C2 JIT の x86-64 AVX-512 VBMI Base64 デコーダ組み込み関数における深刻なヒープバッファオーバーフロー脆弱性"
canonical_url: https://mimirwiki.com/ja/wiki/java4shell
language: ja
page_class: concept
revision_sha256: 4eba41b5f988bfbb38a518bda634b4ec785e28fd2b95bd4fa2d63d2d7589e644
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 7
alternates:
  md: https://mimirwiki.com/ja/wiki/java4shell.md
  txt: https://mimirwiki.com/ja/wiki/java4shell.txt
  json: https://mimirwiki.com/ja/wiki/java4shell.json
  jsonld: https://mimirwiki.com/ja/wiki/java4shell.jsonld
translations:
  en: https://mimirwiki.com/wiki/java4shell
  ko: https://mimirwiki.com/ko/wiki/java4shell
  zh: https://mimirwiki.com/zh/wiki/java4shell
---

# Java4Shell (CVE-2026-114938)

> Calif.io の Quang Luong（AI 支援による「ケンタウロス・ハッキング（centaur hacking）」手法で本脆弱性を解析）および Albert Yang によって Oracle に報告され、CVSS v4.0 9.2（緊急）および CVSS v3.1 8.1（重要）と評価された CVE-2026-114938 は、C2 JIT の AVX-512 Base64 デコードブロック組み込み関数が 64 バイトの SIMD ブロック内で予期しない '=' パディングバイトに遭遇した際に発生する。このとき残余長の計算が -1 にアンダーフローし、evmovdqub（VMOVDQU8）命令に対して全ビットが 1 の 64 ビット書き込みマスク（0xFFFFFFFFFFFFFFFF）が生成される。65 文字の入力（'A' * 64 + '='）では、50 バイトの出力バッファのオフセット 48 から 64 バイトが書き込まれ、配列末尾を超えて 62 バイトのヒープオーバーフローが生じる。Intel Ice Lake 以降および AMD Zen 4 以降の CPU 上の OpenJDK および Oracle Java SE 17.0.6+、21、25、27（ならびに Oracle GraalVM 8u511b33-perf）が影響を受け、OpenJDK 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3、27.0.1.0.3 で修正された。

Java4Shell（識別子 CVE-2026-114938）は、AVX-512 VBMI 命令セットをサポートする x86-64 プロセッサ上で動作する OpenJDK HotSpot 仮想マシン（HotSpot VM）の C2 ジャストインタイム（JIT）コンパイラが生成する java.util.Base64.Decoder の組み込み関数（intrinsic）に存在する、深刻なヒープベースのバッファオーバーフロー脆弱性である。2026年11月17日に OpenJDK の緊急セキュリティアドバイザリおよび Oracle の緊急セキュリティパッチアップデート（Critical Security Patch Update）を通じて公開された。この脆弱性を悪用すると、未認証のリモート攻撃者が不正な位置にパディング文字（'='）を含む細工された Base64 ペイロードを送信するだけで、隣接する Java ヒープオブジェクトを破壊でき、サービス拒否（DoS）、認証バイパス、あるいは事前認証リモートコード実行（RCE）を引き起こすことができる。

**別名:** CVE-2026-114938, Java4Shell, OpenJDK AVX-512 Base64 ヒープオーバーフロー, RHSB-2026-018

## 主要な事実

- **CVE 識別子およびスコア:** CVE-2026-114938（CVSS v4.0: 9.2 Critical / CVSS v3.1: 8.1 High） (時点 2026-11-17) [3]
- **影響を受けるコンポーネント:** OpenJDK HotSpot VM C2 JIT x86-64 AVX-512 VBMI Base64.Decoder 組み込み関数 [1]
- **ハードウェア前提条件:** AVX-512 VBMI 対応 x86-64 CPU（Intel Ice Lake 以降 / AMD Zen 4 以降）。ARM64 は影響なし [4]
- **修正済み OpenJDK バージョン:** 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3、27.0.1.0.3（2026年11月17日公開） (時点 2026-11-17) [1]

## ファクトシート

- **CVE ID:** CVE-2026-114938 [3]
- **通称:** Java4Shell [4]
- **公開日:** 2026年11月17日 [1]
- **発見者:** Quang Luong（Calif.io）および Albert Yang（Oracle によりクレジット記載） [2]
- **CVSS 深刻度:** CVSS v4.0: 9.2（Critical） / CVSS v3.1: 8.1（High） [3]
- **脆弱性の種類:** CWE-122（ヒープベースバッファオーバーフロー） / SIMD 書き込みマスクの整数アンダーフロー [3]
- **影響を受ける Java リリース:** OpenJDK / Oracle JDK 17（17.0.6 以降）、21、25、27。Oracle JDK 8u511b33-perf [2]
- **JVM フラグによる回避策:** -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics（または -XX:UseAVX=2） [5]

## Java4Shell の概要と「ケンタウロス・ハッキング」による発見

**Java4Shell**（`CVE-2026-114938`）は、Java 仮想マシン（JVM）のハードウェアアクセラレーション対応 Base64 デコード処理に存在する深刻なメモリ安全性の脆弱性である。[1][3][4] Java はガベージコレクションを備えたメモリ安全な言語であるため、アプリケーション開発者は認証やスキーマ検証を行う前に、信頼できない HTTP ヘッダ（`Authorization: Basic` や `Bearer` JWT トークンなど）、Cookie、SAML アサーション、JSON フィールドをそのまま `java.util.Base64.getDecoder().decode()` に渡すのが一般的である。[4][5] しかし、頻繁に呼び出されるホットな Java メソッドが HotSpot C2 ジャストインタイム（JIT）コンパイラによってコンパイルされると、JVM は `Base64.Decoder.decodeBlock` のバイトコード実装を、ホスト CPU アーキテクチャ向けに手書きされたアセンブリ組み込み関数（intrinsic）に置き換える。[1][4]

2026年11月の緊急セキュリティパッチアップデート（CSPU）アドバイザリにおいて、Oracle は `CVE-2026-114938` の報告者として **Calif.io の Quang Luong** および **Albert Yang** の名を挙げており、本脆弱性は Oracle および OpenJDK Vulnerability Group との調整を経て **2026年11月17日**に公開された。[1][2][4][7] Calif.io の技術公開記事の中で、Luong は人間のリバースエンジニアリング仮説と大規模言語モデル（LLM）エージェントを組み合わせて OpenJDK の `stubGenerator_x86_64.cpp` 内部にある複雑な手書き x86-64 SIMD アセンブリスタブ生成器を監査する、**「ケンタウロス・ハッキング（centaur hacking）」**と呼ぶワークフローによって本バグを発見した経緯を詳述している。[4]

## Java4Shell の技術的メカニズム: AVX-512 VBMI マスクのアンダーフロー

`CVE-2026-114938` の根本原因は、OpenJDK の C2 JIT Base64 デコーダ組み込み関数（`decodeBlock`）内にある x86-64 **AVX-512 VBMI**（Vector Byte Manipulation Instructions）の高速処理パスに存在する。[1][4] 標準的な Base64 デコードでは、エンコードされた ASCII 文字 4 バイトごとに 3 バイトのデコード済み出力が生成されるため、64 バイトの AVX-512 レジスタ（`ZMM`）1 つ分の Base64 入力からは最大 48 バイトのデコード結果が得られる。[4] 組み込み関数が 64 バイトの SIMD チャンク内で非 Base64 文字または `'='` パディング文字（`0x3d`）を検出した場合、ベクトル化ループを終了し、残りの末尾バイトをスカラーの Java ループに引き渡す設計となっていた。[4]

しかし、最終的なマスク付き SIMD ストア命令 `evmovdqub`（書き込みマスクレジスタ `k` を用いる `VMOVDQU8`）のための残余 `output_len` を計算する際の符号付き・符号なし長計算のバグにより、特定のオフセットに不正な `'='` 文字が存在すると、算出される残余バイト数が `-1`（64 ビットの 2 の補数表現で `0xFFFFFFFFFFFFFFFF`）にアンダーフローする。[4] この値がシフトされるか 64 ビットの AVX-512 opmask レジスタにロードされると、マスクの全ビットが 1（`-1u64`）となり、CPU の `evmovdqub` 命令はレジスタデータ全体の **64 バイト** を出力先の Java `byte[]` 配列に書き込むよう指示される。[4]

Calif.io は、JDK リリースの組み込み関数しきい値に応じた 2 種類の最小決定論的トリガーを実証した。[4] - **OpenJDK 21、25、27**: 65 バイトの文字列 `'A' * 64 + '='` をデコードすると、50 バイトの出力先 `byte[]` 配列が確保される（16 バイトの配列オブジェクトヘッダを含め、HotSpot ヒープ上では 8 バイト境界にアライメントされた 72 バイトのオブジェクトを占有する）。先頭 64 文字が 48 バイトにデコードされた後、マスク付き `evmovdqub` が 50 バイトのペイロードバッファのオフセット 48 から 64 バイトを書き込む（書き込みの 48..63 バイト目は `0x9a` となる）。これにより、**配列の末尾を超えて 62 バイトがオーバーフローし、直後に隣接する Java ヒープオブジェクトのヘッダおよびフィールドを上書きする**。[4] - **OpenJDK 17（17.0.6 から 17.0.21 まで）**: JDK 17 では AVX-512 ループに入る前の最小バッファサイズチェックがより大きく設定されているため、最小トリガーは 129 バイトの文字列 `'A' * 128 + '='` となる。[4]

## 影響を受ける Java バージョン、CPU アーキテクチャ、およびエンタープライズへの影響

`CVE-2026-114938` の悪用には、影響を受ける JVM ビルドと **AVX-512 VBMI** をサポートする x86-64 プロセッサという 2 つの条件が同時に満たされる必要がある。[1][2][4]

| 項目 | 脆弱な構成 | 影響を受けない構成 |
| --- | --- | --- |
| **Java / OpenJDK バージョン** | OpenJDK および Oracle Java SE **17.0.6 - 17.0.21**、**21.0.0 - 21.0.13**、**25.0.0 - 25.0.5**、**27.0.0 - 27.0.1**、Oracle GraalVM / JDK **8u511b33-perf** [1][2] | 標準の OpenJDK 8 および OpenJDK 11（AVX-512 VBMI Base64 組み込み関数を持たない）、OpenJDK 17.0.1 - 17.0.5 [1][4][5] |
| **CPU アーキテクチャ** | **AVX-512 VBMI 対応 x86-64**: Intel Ice Lake、Tiger Lake、Sapphire Rapids、Emerald Rapids、Granite Rapids、AMD Zen 4（EPYC Genoa/Bergamo）および Zen 5（EPYC Turin） [4][5] | **ARM64 / AArch64**（AWS Graviton、Apple Silicon、Ampere）、AVX-512 VBMI 非対応の旧世代 x86-64 CPU（Intel Skylake-SP、AMD Zen 2/Zen 3 など） [4][5] |

62 バイトのヒープオーバーフローによって、スレッドローカル割り当てバッファ（TLAB）内の次のオブジェクトのマークワード、圧縮クラスポインタ（`_klass`）、配列長フィールド、あるいは真偽値・参照フィールドが上書きされるため、攻撃者は隣接するセキュリティトークンを改ざんしたり、隣接する `byte[]` 配列の長さフィールドを水増しして JVM プロセス内で任意の読み書きプリミティブを構築したりすることが可能となる。[4] Calif.io およびエンタープライズベンダーは、**Keycloak**、**Atlassian Jira および Confluence**、**JFrog Artifactory**、**Jenkins**、**PingFederate** を含む主要な Java ミドルウェアおよびアプリケーションにおいて事前認証での影響を実証または確認した。[4][7]

## 修正済みリリース、JVM フラグによる回避策、および CISA の勧告

2026年11月17日、OpenJDK プロジェクト、Oracle、Red Hat（`RHSB-2026-018`）、Amazon Corretto、Eclipse Temurin、および Azul は、問題のある AVX-512 VBMI マスク生成を無効化または境界修正した緊急の帯域外ビルドをリリースした。[1][2][5] - **OpenJDK 17.0.21.0.3** - **OpenJDK 21.0.13.0.3** - **OpenJDK 25.0.5.0.3** - **OpenJDK 27.0.1.0.3**

**JVM コマンドライン回避策**: JDK バイナリを直ちにアップグレードできない本番システムでは、`JAVA_OPTS` に以下のフラグのいずれかを追加して JVM を再起動することで、Base64 C2 組み込み関数を無効化するか AVX-512 の実行を制限できる。[4][5] ```text -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics ``` または、AVX レベルの上限を AVX-512 未満に制限する方法もある: ```text -XX:UseAVX=2 ```

**CISA アラートおよび境界緩和策**: 2026年11月17日、米国サイバーセキュリティ・インフラストラクチャセキュリティ庁（CISA）はカナダサイバーセキュリティセンター（Canadian Centre for Cyber Security）の協力のもとアラートを発出し、サードパーティ製アプリケーションやコンテナイメージ、アプライアンスに同梱されたものを含め JDK および Java ランタイムの資産を棚卸しし、インターネットに公開されたシステムを優先してパッチを適用するよう強く求めた。[6] 即時のパッチ適用が困難な場合、CISA はアプリケーション境界での Base64 入力の制限・検証、入力サイズ制限の強制、未認証アクセスの制限といった一時的な補完対策を講じるとともに、不正なランタイム、予期しない JVM クラッシュ、不審な Java プロセスを監視することを推奨している。[6]

## よくある質問

### Java4Shell（CVE-2026-114938）とは何ですか？

Java4Shell（CVE-2026-114938）は、OpenJDK HotSpot C2 JIT コンパイラの java.util.Base64.Decoder 用 x86-64 AVX-512 VBMI 組み込み関数に存在する深刻なヒープバッファオーバーフロー脆弱性（CVSS v4.0 9.2 / CVSS v3.1 8.1）です。2026年11月17日に公開され、不正な位置に '=' パディング文字を含む Base64 文字列を送信することで、リモート攻撃者が Java ヒープ上の隣接オブジェクトを破壊できます。 [1][3][4]

### CVE-2026-114938 の影響を受ける Java バージョンと CPU はどれですか？

この脆弱性は、OpenJDK および Oracle Java SE 17（バージョン 17.0.6 から 17.0.21）、21（21.0.13 まで）、25（25.0.5 まで）、27（27.0.1 まで）、および Oracle JDK 8u511b33-perf に影響しますが、AVX-512 VBMI をサポートする x86-64 CPU（Intel Ice Lake 以降または AMD Zen 4 以降など）上で動作している場合に限られます。ARM64 サーバーや標準の OpenJDK 8 および 11 ビルドは影響を受けません。 [1][2][4][5]

### 65 バイトの Base64 文字列はどのようにして Java でヒープバッファオーバーフローを引き起こすのですか？

AVX-512 VBMI Base64 decodeBlock 組み込み関数が 64 バイトの SIMD チャンク（48 バイトの出力にデコードされる）を処理した後に予期しない '=' パディングバイト（'A' を 64 回繰り返した後に '=' が続く文字列など）に遭遇すると、長さの計算が -1 にアンダーフローします。これにより 64 ビットの AVX-512 書き込みマスクが全ビット 1（0xFFFFFFFFFFFFFFFF）になり、evmovdqub 命令が 50 バイトのバッファのオフセット 48 から 64 バイトを書き込むため、配列の末尾を超えて隣接する Java ヒープオブジェクトに 62 バイトが上書きされます。 [4]

### Java4Shell を修正する OpenJDK のパッチ済みバージョンはどれですか？

この脆弱性は、2026年11月17日に公開された帯域外 OpenJDK リリース 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3、および 27.0.1.0.3、ならびに対応する 2026年11月の Oracle 緊急セキュリティパッチアップデートおよび Red Hat OpenJDK ビルドで修正されています。 [1][2][5]

### Java をアップグレードせずに JVM フラグで CVE-2026-114938 を緩和するにはどうすればよいですか？

管理者は、JVM の起動引数に '-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics'（または '-XX:UseAVX=2'）を指定して Java プロセスを再起動することで、脆弱なアセンブリ組み込み関数を完全に無効化できます。 [4][5]

## 引用できる文

- CVE-2026-114938（Java4Shell）は 2026年11月17日に公開され、CVSS v4.0 スコア 9.2（Critical）および CVSS v3.1 スコア 8.1（High）が付与された。 [1][2][3]
- CVE-2026-114938 は、OpenJDK の C2 JIT Base64.Decoder 組み込み関数内にある evmovdqub 命令の AVX-512 VBMI 書き込みマスクにおける -1 への整数アンダーフローによって発生し、50 バイトバッファのオフセット 48 から 64 バイトの書き込み（62 バイトのヒープオーバーフロー）を引き起こす。 [4]
- Oracle の 2026年11月緊急セキュリティパッチアップデート（CSPU）アドバイザリでは、CVE-2026-114938 の報告者として Calif.io の Quang Luong および Albert Yang がクレジットされており、本脆弱性は AVX-512 VBMI をサポートする x86-64 CPU 上の OpenJDK 17.0.6+、21、25、27 に影響する一方、ARM64 および標準の OpenJDK 8/11 は影響を受けない。 [1][2][4][5][7]
- OpenJDK は緊急リリース 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3、および 27.0.1.0.3 で CVE-2026-114938 を修正しており、-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics によって緩和できる。 [1][5]

## 年表

- 2023-01: OpenJDK 17.0.6 に潜在的なマスクアンダーフローのバグを含む AVX-512 VBMI Base64 デコーダ C2 JIT 組み込み関数がバックポートされた。 [1][4]
- 2026-11-17: OpenJDK が Vulnerability Advisory 2026/11/17 を公開し、Oracle が緊急の Critical Security Patch Update をリリース、CISA が CVE-2026-114938 への即時パッチ適用を求めるアラートを発出した。OpenJDK 17.0.21.0.3、21.0.13.0.3、25.0.5.0.3、27.0.1.0.3 が公開された。 [1][2][6]
- 2026-11-18: Calif.io の Quang Luong が技術的な根本原因分析（「Java4Shell」）を公開し、Red Hat が Security Bulletin RHSB-2026-018 を発行した。 [4][5]

## 出典

1. OpenJDK Vulnerability Advisory: 2026/11/17 (CVE-2026-114938 in Hotspot Base64 Intrinsic). OpenJDK Vulnerability Group. 公開 2026-11-17. https://openjdk.org/groups/vulnerability/advisories/2026-11-17 (閲覧 2026-11-23; tier 3: official site)
2. Oracle Critical Security Patch Update Advisory - November 2026. Oracle Corporation. 公開 2026-11-17. https://www.oracle.com/security-alerts/cspunov2026.html (閲覧 2026-11-23; tier 3: official site)
3. NVD Detail for CVE-2026-114938: OpenJDK HotSpot VM AVX-512 Base64 Decoder Heap-Based Buffer Overflow. National Vulnerability Database (NIST). 公開 2026-11-17. https://nvd.nist.gov/vuln/detail/CVE-2026-114938 (閲覧 2026-11-23; tier 1: government or public registry)
4. Java4Shell: Write once, RCE everywhere. Calif.io (Quang Luong). 公開 2026-11-18. https://calif.io/java4shell (閲覧 2026-11-23; tier 3: official site)
5. Red Hat Security Bulletin RHSB-2026-018: OpenJDK AVX-512 Base64 Heap Overflow (CVE-2026-114938). Red Hat, Inc.. 公開 2026-11-18. https://access.redhat.com/security/vulnerabilities/RHSB-2026-018 (閲覧 2026-11-23; tier 3: official site)
6. Critical Java Vulnerability Requires Immediate Patching | CISA. Cybersecurity and Infrastructure Security Agency (CISA). 公開 2026-11-17. https://www.cisa.gov/news-events/alerts/2026/11/17/critical-java-vulnerability-requires-immediate-patching (閲覧 2026-11-24; tier 1: government or public registry)
7. Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ. Tenable Research. 公開 2026-11-17. https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability (閲覧 2026-11-23; tier 3: official site)

## このページを引用する

Mimirwiki. "Java4Shell (CVE-2026-114938)." 版 4eba41b5, 2026-11-24. https://mimirwiki.com/ja/wiki/java4shell
