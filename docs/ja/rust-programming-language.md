---
title: "Rust（プログラミング言語）"
subtitle: "ガベージコレクタなしでコンパイル時のメモリ安全性とスレッド安全性を保証するマルチパラダイム・システムプログラミング言語"
canonical_url: https://mimirwiki.com/ja/wiki/rust-programming-language
language: ja
page_class: entity
revision_sha256: 857456ae7810b5b0cca4586995f4be9e551dc97ceeed5156503321a8988c8fde
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ja/wiki/rust-programming-language.md
  txt: https://mimirwiki.com/ja/wiki/rust-programming-language.txt
  json: https://mimirwiki.com/ja/wiki/rust-programming-language.json
  jsonld: https://mimirwiki.com/ja/wiki/rust-programming-language.jsonld
translations:
  en: https://mimirwiki.com/wiki/rust-programming-language
  ko: https://mimirwiki.com/ko/wiki/rust-programming-language
  zh: https://mimirwiki.com/zh/wiki/rust-programming-language
  es: https://mimirwiki.com/es/wiki/rust-programming-language
---

# Rust（プログラミング言語）

> 2026年11月12日、Rustリリースチームは6週間ごとのリリーストレインに基づき、節目の安定版リリースであるRust 1.100.0を公開した。10年の歳月と5回の安定化試行を経て、Rust 1.100.0ではすべての型位置でnever型（!）が安定化され、core::convert::Infallibleが!の型エイリアスになるとともに、すべてのエディションでnever型のフォールバックが!に統一された。あわせて、BoxおよびVec向けのコアAllocatorトレイト（std::alloc::Allocator）、core::mem::DropGuard、core::mem::conjure_zst、Cargoの[lints.cargo]におけるunused_dependenciesチェック、新しい中間build-dirレイアウト、およびCargoの依存関係クールダウン機能（global-min-publish-age）も安定化された。

Rustは、2006年にMozilla Researchのグレイドン・ホア（Graydon Hoare）によって当初設計され、2015年5月にバージョン1.0に到達し、2021年2月以降は非営利団体であるRust Foundationによって管理されている、汎用・マルチパラダイムのコンパイル型システムプログラミング言語である。ガベージコレクタや必須のランタイムを用いずに、コンパイル時に強制される所有権（ownership）、借用（borrowing）、ライフタイム（lifetime）の型システムを通じて、メモリ安全性のバグ（ヌルポインタ・ダングリングポインタの参照外しやバッファオーバーフローなど）および並行コードにおけるデータ競合を防止する。

**別名:** Rust, rust-lang, rustc, Cargo, Rust 1.100.0

## 主要な事実

- **管理団体:** Rust Foundation（501(c)(6)非営利団体、理事長：Nell Shamrell-Harrington） (時点 2026-11-23) [2]
- **最新安定版:** Rust 1.100.0（2026年11月12日リリース） (時点 2026-11-12) [4]
- **言語エディション:** Rust 2015、Rust 2018、Rust 2021、Rust 2024 [3]
- **1.100.0の主要機能:** never型（!）の安定化、std::alloc::Allocator API、DropGuard、Cargo min-publish-age (時点 2026-11-12) [4]

## ファクトシート

- **初期設計者:** グレイドン・ホア（Graydon Hoare、当初はMozilla Researchが支援） [1]
- **管理主体:** Rust FoundationおよびRustプロジェクトチーム [2]
- **初回安定版リリース（1.0.0）:** 2015年5月15日 [3]
- **現在の安定版:** 1.100.0（2026年11月12日） [4]
- **リリース周期:** 6週間トレインモデル（Nightly -> Beta -> Stable） [4]
- **パッケージマネージャ・レジストリ:** Cargo / crates.io（ツールチェーンインストーラ：rustup） [1]
- **型システム:** 静的、強い型付け、アフィン所有権・借用、代数的データ型、トレイト [1]
- **ライセンス:** Apache License 2.0およびMIT Licenseのデュアルライセンス [1]

## Rustの概要、所有権モデル、およびツールチェーンエコシステム

Rustは、**「停滞なき安定（stability without stagnation）」**の原則に基づいて設計された静的型付けシステムプログラミング言語であり、コンパイル時のメモリ安全性保証のもとで低水準・ベアメタル・高並行ソフトウェアを開発できるようにするものである。[1][3] トレーシング型ガベージコレクションに依存するマネージド言語（JavaやGoなど）や、手動メモリ管理を全面的にプログラマに委ねる従来のシステムプログラミング言語（CやC++など）とは異なり、Rustは**所有権および借用チェッカ（ownership and borrow checker）**を通じて決定論的なリソース管理（RAII）を強制する。[1][4] - Rustのすべての値は単一の所有者変数を持ち、所有者がスコープを抜けると、その`Drop`実装によって値が自動的に破棄される。[4] - 参照は厳格な「エイリアシングと可変性の排他（aliasing-xor-mutability）」規則に従う。実行の任意の時点において、コードは任意個の不変参照（`&T`）またはただ1つの可変参照（`&mut T`）のいずれか一方のみを保持でき、さらにライフタイムによって参照が参照先より長く生存しないことが静的に保証される。[1] - 生ポインタの参照外し、FFI呼び出し、`std::mem::conjure_zst`によるゼロサイズマーカートークンの生成といった、コンパイラが静的に検証できない低水準操作は、`unsafe`ブロック内に明示的にカプセル化する必要がある。[4]

Rustには**`rustup`**によって管理される統合型のファーストパーティ・ツールチェーンが付属しており、LLVMベースのコンパイラ（**`rustc`**）、ビルドシステム兼パッケージマネージャ（**`Cargo`**）、公開パッケージレジストリ（**`crates.io`**）、ドキュメント生成器（**`rustdoc`**）、リンタ（**`Clippy`**）、コードフォーマッタ（**`rustfmt`**）が含まれている。[1][4]

## Rustの6週間リリーストレインとエディションシステム

2015年5月の**Rust 1.0.0**リリース以降、Rustプロジェクトは3つのチャネルによる迅速な**6週間トレインリリースモデル**を運用している。すなわち、実験的な`-Z`フラグを備え`main`ブランチから毎日ビルドされる**Nightly**、「No Tools Breakage Week」を経て回帰テストのために6週間ごとに分岐される**Beta**、そして**Stable**である。[3][4][5]

既存のコードベースを破壊することなく、`async`や`await`のような新しい予約語の導入や型推論フォールバック規則の変更といった構文・イディオムを進化させるため、Rustはオプトイン方式の**エディション（Editions）**（`Cargo.toml`内の`edition = "2015"`、`"2018"`、`"2021"`、`"2024"`）を採用している。[3][4] エディションはエコシステムを分断しない。すべてのエディションがコンパイラ内部で同一の中間表現（HIR/MIR）にコンパイルされるため、Rust 2015でコンパイルされたクレートであっても、Rust 2024でコンパイルされた依存関係とシームレスにリンクおよび相互運用できる。[3] エディション間の自動移行は`cargo fix --edition`によって提供されている。[3]

## Rust 1.100.0マイルストーンリリース（2026年11月12日）

**2026年11月12日**、Rustリリースチームは**Rust 1.100.0**（2026年9月25日にmasterから分岐）を公開し、長年待ち望まれていた言語機能、標準ライブラリ、およびCargoのサプライチェーンセキュリティ機能を提供した。[4][5][6]

| 機能・コンポーネント | Rust 1.100.0における安定化の概要 |
| --- | --- |
| **never型（`!`）** | 10年の歳月と5回の試行を経て安定化された。`!`は発散する計算（`return`、`break`、`panic!`、`std::process::exit`）を表す標準の非居住型（uninhabited type）であり、never型から任意の型への自動型強制（never-to-any coercion）を備える。`!`は任意の型位置（例：`Result<T, !>`）で指定できるようになり、`core::convert::Infallible`は`!`の型エイリアスとなり、さらにすべてのエディション（2015、2018、2021、2024）でnever型のフォールバックが`!`に統一された。[4][5][7] |
| **カスタムアロケータAPI（`std::alloc::Allocator`）** | コアの`Allocator`トレイトと`Global`、`System`、および`Box`（`Box::new_in`、`Box::from_raw_in`、`Box::allocator`）と`Vec`（`Vec::new_in`、`Vec::with_capacity_in`、`Vec::from_raw_parts_in`）向けのカスタムアロケータ対応コンストラクタ・アクセサを安定化し、Allocators 1.0目標の基盤を確立した。[4][5] |
| **`core::mem::DropGuard`** | 値とクロージャをラップする新しいRAIIヘルパ（`DropGuard::new(val, | v | ...)`）であり、`Deref`/`DerefMut`を実装し、トランザクションのロールバックパターンなどで`DropGuard::dismiss(guard)`によって明示的に解除されない限り、すべてのスコープ脱出時にクリーンアップクロージャを実行する。[4][5] |
| **`core::mem::conjure_zst`** | アドホックな`transmute(())`や`MaybeUninit`パターンを用いることなく、居住型であるゼロサイズ型（ZST）を安全に実体化するための専用の`unsafe fn conjure_zst<T>() -> T`関数である。[4][5] |
| **Cargo依存関係クールダウン（`min-publish-age`）** | RFC 3923のサプライチェーン保護機能を安定化した。`.cargo/config.toml`の`[registry]`配下に`global-min-publish-age = "3 days"`を設定すると、クールダウン期間が経過するまで`cargo update`が`crates.io`に新規公開されたバージョンをスキップする（`CARGO_RESOLVER_INCOMPATIBLE_PUBLISH_AGE=allow`で上書き可能）。[4][5][6] |
| **CargoリントとBuild-Dirレイアウト** | `Cargo.toml`に`[lints.cargo]`テーブルを導入し、デフォルト警告の`cargo::unused_dependencies`を追加したほか、ビルドステップのハッシュを中心に中間`build-dir`ディレクトリレイアウトを再編成し、`--features`やGitワークツリー間のキャッシュ衝突を防止した。[4][5][6] |
| **プラットフォームおよび標準ライブラリの更新** | `wasm32-wasip3`をTier 2に昇格（WASI SDK 34対応）し、標準ライブラリを**Unicode 18.0.0**に更新したほか、`-Cprofile-sample-use`および`extern "custom"`を安定化し、`str::trim_prefix`、`str::trim_suffix`、`bool::toggle`、`Vec::from_fn`、`Box::map`/`Rc::map`/`Arc::map`を追加した。[4][5] |

## RustのガバナンスとRust Foundation

Rust言語、コンパイラ、および標準ライブラリの技術的な進化は、公開のRequest for Comments（**RFC**）プロセスを通じて**Rustプロジェクトチーム（Rust Project Teams）**が統治する一方、法務、財務、商標、およびインフラストラクチャの管理は、2021年に設立された独立非営利団体である**Rust Foundation**が担っている。[2]

Rust Foundationの理事会（Board of Directors）は、Rustプロジェクトから選出された**プロジェクト理事（Project Directors）**と、企業のプラチナ・シルバースポンサーを代表する**メンバー理事（Member Directors）**が対等な議決権を分かち合う構成となっている。[2] 2026年後半時点で、企業側理事の議席は**Nell Shamrell-Harrington**（理事長、Microsoft代表）、**Jeffrey Vander Stoep**（Google / Android Security）、**Andrew Wafaa**（Arm）、**Predrag Gruevski**（OpenAI）、**Jared Roesch**（NVIDIA）、**Jess Wass**（Meta）、**Jacob Creech**（Solana Foundation）、および**Alexandru Radovici**（シルバーメンバー代表）が務めている。[2] **2026-2028戦略計画（Strategic Plan）**のもと、同財団はRust Innovation Lab、セキュリティ・イニシアティブ（`crates.io`のサプライチェーン強化および自動マルウェアスキャンを支援）、C++/Python相互運用イニシアティブ、ならびにTrusted Trainingプログラムを運営している。[2][4]

## よくある質問

### 2026年11月時点でのプログラミング言語Rustの最新バージョンは何ですか？

最新の安定版バージョンは、2026年11月12日にリリースされたRust 1.100.0です。このリリースでは、never型（!）、BoxおよびVec向けのコアstd::alloc::Allocatorトレイト、core::mem::DropGuard、core::mem::conjure_zst、Cargoの未使用依存関係リント、およびCargoの依存関係クールダウン機能（min-publish-age）が安定化されました。 [1][4][5]

### Rust 1.100.0で安定化されたnever型（!）とは何ですか？

「!」と表記されるnever型は、値を返さない計算（return、break、panic!、std::process::exitなど）を表すRustの標準的な非居住型（uninhabited type）です。10年間の開発を経て、Rust 1.100.0では任意の型引数（Result<T, !>など）で「!」を指定できるようになり、core::convert::Infallibleが「!」の型エイリアスとなったほか、すべてのRustエディションでnever型のフォールバックが「!」に統一されました。 [4][5][7]

### Rust 1.100.0のCargo依存関係クールダウン（min-publish-age）は、サプライチェーンセキュリティをどのように向上させますか？

Rust 1.100.0（RFC 3923）で安定化されたこの機能では、.cargo/config.tomlに「global-min-publish-age」（例：「3 days」）を設定することで、crates.ioに新しく公開されたパッケージバージョンが指定期間を経過するまでCargoの依存関係リゾルバに無視させることができます。これにより、セキュリティスキャナやコミュニティが悪意のあるリリースを検出して取り下げる（yankする）ための時間を確保できます。 [4][5][6]

### Rustはガベージコレクタなしでどのようにメモリ安全性を実現していますか？

Rustはコンパイル時に所有権と借用のモデルを強制します。すべての値は単一の所有者を持ち、所有者がスコープを抜けると自動的に破棄されます。また、参照は複数の不変借用（&T）または単一の可変借用（&mut T）のいずれか一方のみを許可する規則に従い、ライフタイムが静的に検証されます。 [1][4]

### Rustエディションとは何ですか？クレート間の互換性は損なわれますか？

Rustエディション（2015、2018、2021、2024）は、Cargo.tomlでクレートごとにオプトイン設定する仕組みであり、既存コードを破壊することなく新しいキーワードや構文変更を導入できるようにするものです。すべてのエディションがコンパイラ内部で同一の中間表現にコンパイルされ、単一のビルド内でシームレスに相互運用できるため、エコシステムが分断されることはありません。 [3]

## 引用できる文

- Rust 1.100.0は2026年11月12日にリリースされ、10年の歳月と5回の安定化試行を経て、すべての型位置でnever型（!）を安定化した。 [4][5][7]
- Rust 1.100.0では、core::convert::Infallibleがnever型（!）への型エイリアスとなり、エディション2015、2018、2021におけるnever型のフォールバックがエディション2024に合わせて()から!へ変更された。 [4][5]
- Rust 1.100.0は、BoxおよびVec向けのstd::alloc::Allocator、core::mem::DropGuard、core::mem::conjure_zst、Unicode 18.0.0サポート、およびwasm32-wasip3のTier 2昇格を安定化した。 [4][5]
- Cargo 1.100は、[lints.cargo]のunused_dependenciesリント、ハッシュベースで整理された新しいbuild-dirディレクトリレイアウト、およびmin-publish-age依存関係クールダウン（RFC 3923）を導入した。 [4][5][6]
- Rust Foundationの理事会はNell Shamrell-Harrington（Microsoft）が理事長を務め、Rustプロジェクト理事とともにGoogle、Arm、OpenAI、NVIDIA、Meta、およびSolana Foundationからのメンバー理事が参加している。 [2]

## 年表

- 2015-05-15: Rust 1.0.0がリリースされ、「停滞なき安定（stability without stagnation）」の後方互換性保証と6週間リリーストレインが確立された。 [3]
- 2018-12: Rust 2018エディションが公開され、Cargoにオプトイン式のエディション移行機構が導入された。 [3]
- 2021-02: Rust言語およびエコシステムの独立非営利管理団体としてRust Foundationが設立された。 [2]
- 2026-09-25: Rust 1.100.0がmasterブランチからベータテストチャネルへ分岐された。 [5]
- 2026-11-12: Rust 1.100.0が安定版チャネルでリリースされ、never型（!）、std::alloc::Allocator、core::mem::DropGuard、およびCargoのmin-publish-age依存関係クールダウンが安定化された。 [4][5][6]

## 出典

1. Rust Programming Language Official Website (Version 1.100.0). The Rust Project. https://rust-lang.org/ (閲覧 2026-11-23; tier 3: official site)
2. About The Rust Foundation: Mission, 2026-2028 Strategy, and Board of Directors. The Rust Foundation. https://rustfoundation.org/about/ (閲覧 2026-11-23; tier 3: official site)
3. What are Editions? - The Rust Edition Guide. The Rust Project. https://doc.rust-lang.org/edition-guide/editions/index.html (閲覧 2026-11-23; tier 3: official site)
4. Announcing Rust 1.100.0. The Rust Release Team / Rust Blog. 公開 2026-11-12. https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/ (閲覧 2026-11-23; tier 3: official site)
5. Rust 1.100.0 Release Notes (rust-lang/rust). GitHub / The Rust Project. 公開 2026-11-12. https://github.com/rust-lang/rust/releases/tag/1.100.0 (閲覧 2026-11-23; tier 3: official site)
6. Cargo 1.100 Changelog (2026-11-12) - The Cargo Book. The Rust Project. 公開 2026-11-12. https://doc.rust-lang.org/cargo/CHANGELOG.html (閲覧 2026-11-23; tier 3: official site)
7. Rust 1.100 Released With The 'Never' Type Finally Stable. Phoronix. 公開 2026-11-12. https://www.phoronix.com/news/Rust-1.100-Released (閲覧 2026-11-23; tier 2: academic or news)

## このページを引用する

Mimirwiki. "Rust（プログラミング言語）." 版 857456ae, 2026-11-24. https://mimirwiki.com/ja/wiki/rust-programming-language
