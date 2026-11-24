---
title: "Rust (Programming Language)"
subtitle: "Multi-paradigm systems programming language enforcing compile-time memory safety and thread safety without a garbage collector"
canonical_url: https://mimirwiki.com/wiki/rust-programming-language
language: en
page_class: entity
revision_sha256: 50f11e7e8875fc0b9e4c3fca60bd64b47276a58721fa2d467dae0e7437590aa2
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/wiki/rust-programming-language.md
  txt: https://mimirwiki.com/wiki/rust-programming-language.txt
  json: https://mimirwiki.com/wiki/rust-programming-language.json
  jsonld: https://mimirwiki.com/wiki/rust-programming-language.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/rust-programming-language
  ja: https://mimirwiki.com/ja/wiki/rust-programming-language
  zh: https://mimirwiki.com/zh/wiki/rust-programming-language
---

# Rust (Programming Language)

> On November 12, 2026, the Rust Release Team shipped the milestone Rust 1.100.0 stable release on its six-week release train. After 10 years and five prior stabilization attempts, Rust 1.100.0 stabilized the never type (!) in all type positions (making core::convert::Infallible a type alias for ! and setting the never-type fallback to ! across all editions), alongside the core Allocator trait (std::alloc::Allocator for Box and Vec), core::mem::DropGuard, core::mem::conjure_zst, Cargo's [lints.cargo] unused_dependencies check, a new intermediate build-dir layout, and Cargo dependency cooldowns (global-min-publish-age).

Rust is a general-purpose, multi-paradigm compiled systems programming language originally designed by Graydon Hoare at Mozilla Research in 2006, reaching version 1.0 in May 2015 and stewarded since February 2021 by the non-profit Rust Foundation. Through an ownership, borrowing, and lifetime type system enforced at compile time without a garbage collector or mandatory runtime, Rust prevents memory-safety bugs (such as null/dangling pointer dereferences and buffer overflows) and data races in concurrent code.

**Also known as:** Rust, rust-lang, rustc, Cargo, Rust 1.100.0

## Key facts

- **Steward Organization:** The Rust Foundation (501(c)(6) non-profit; Board Chair Nell Shamrell-Harrington) (as of 2026-11-23) [2]
- **Latest Stable Release:** Rust 1.100.0 (released November 12, 2026) (as of 2026-11-12) [4]
- **Language Editions:** Rust 2015, Rust 2018, Rust 2021, and Rust 2024 [3]
- **Flagship 1.100.0 Features:** Stabilized never type (!), std::alloc::Allocator API, DropGuard, Cargo min-publish-age (as of 2026-11-12) [4]

## Basic facts

- **Original Designer:** Graydon Hoare (originally sponsored by Mozilla Research) [1]
- **Steward:** The Rust Foundation and The Rust Project Teams [2]
- **First Stable Release (1.0.0):** May 15, 2015 [3]
- **Current Stable Release:** 1.100.0 (November 12, 2026) [4]
- **Release Cadence:** Six-week train model (Nightly -> Beta -> Stable) [4]
- **Package Manager & Registry:** Cargo / crates.io (Toolchain installer: rustup) [1]
- **Type System:** Static, strong, affine ownership & borrowing, algebraic data types, traits [1]
- **Licenses:** Dual-licensed under Apache License 2.0 and MIT License [1]

## Overview, Ownership Model, and Tooling Ecosystem

Rust is a statically typed systems programming language engineered around the principle of **'stability without stagnation'**, empowering developers to write low-level, bare-metal, and high-concurrency software with compile-time memory safety guarantees [1][3]. Unlike managed languages that rely on tracing garbage collection (such as Java or Go) or traditional systems languages that delegate manual memory management entirely to the programmer (such as C and C++), Rust enforces deterministic resource management (RAII) through its **ownership and borrow checker** [1][4]: - Every value in Rust has a single owner variable, and the value is automatically dropped via its `Drop` implementation when the owner goes out of scope [4]. - References follow a strict aliasing-xor-mutability rule: at any given point in execution, code may hold either any number of immutable references (`&T`) or exactly one mutable reference (`&mut T`), and references are statically guaranteed via lifetimes never to outlive their referent [1]. - Low-level operations that the compiler cannot statically verify - such as raw pointer dereferencing, FFI calls, or creating zero-sized marker tokens via `std::mem::conjure_zst` - must be explicitly encapsulated inside `unsafe` blocks [4].

Rust ships with an integrated first-party toolchain managed by **`rustup`**, including the LLVM-backed compiler (**`rustc`**), the build system and package manager (**`Cargo`**), the public package registry (**`crates.io`**), the documentation generator (**`rustdoc`**), the linter (**`Clippy`**), and the code formatter (**`rustfmt`**) [1][4].

## Six-Week Release Train and the Edition System

Since the release of **Rust 1.0.0** in May 2015, the Rust project has operated a rapid **six-week train release model** across three channels: **Nightly** (built daily from the `main` branch with experimental `-Z` flags), **Beta** (branched every six weeks for regression testing, preceded by a 'No Tools Breakage Week'), and **Stable** [3][4][5].

To evolve syntax and idioms - such as introducing new reserved keywords like `async` and `await` or changing type-inference fallback rules - without breaking existing codebases, Rust uses opt-in **Editions** (`edition = "2015"`, `"2018"`, `"2021"`, and `"2024"` in `Cargo.toml`) [3][4]. Editions do not split the ecosystem: all editions compile down to the same internal compiler intermediate representations (HIR/MIR), allowing a crate compiled on Rust 2015 to seamlessly link and interoperate with dependencies compiled on Rust 2024 [3]. Automated migration between editions is provided via `cargo fix --edition` [3].

## Rust 1.100.0 Milestone Release (November 12, 2026)

On **November 12, 2026**, the Rust Release Team published **Rust 1.100.0** (branched from master on September 25, 2026), delivering several long-awaited language, standard library, and Cargo supply-chain security features [4][5][6]:

| Feature / Component | Summary of Stabilization in Rust 1.100.0 |
| --- | --- |
| **The Never Type (`!`)** | Stabilized after 10 years and 5 prior attempts. `!` is the canonical uninhabited type for diverging computations (`return`, `break`, `panic!`, `std::process::exit`) with automatic never-to-any coercion. `!’ can now be named in arbitrary type positions (e.g., `Result<T, !>`), `core::convert::Infallible` is now a type alias for `!`, and the never-type fallback is unified to `!` across all editions (2015, 2018, 2021, and 2024) [4][5][7]. |
| **Custom Allocator API (`std::alloc::Allocator`)** | Stabilizes the core `Allocator` trait alongside `Global`, `System`, and custom-allocator constructors/accessors for `Box` (`Box::new_in`, `Box::from_raw_in`, `Box::allocator`) and `Vec` (`Vec::new_in`, `Vec::with_capacity_in`, `Vec::from_raw_parts_in`), establishing the foundation for the Allocators 1.0 goal [4][5]. |
| **`core::mem::DropGuard`** | New RAII helper wrapping a value and a closure (`DropGuard::new(val, | v | ...)`), implementing `Deref`/`DerefMut` and running the cleanup closure on every scope exit unless explicitly disarmed via `DropGuard::dismiss(guard)` for transactional rollback patterns [4][5]. |
| **`core::mem::conjure_zst`** | Dedicated `unsafe fn conjure_zst<T>() -> T` for safely materializing inhabited zero-sized types (ZSTs) without ad-hoc `transmute(())` or `MaybeUninit` patterns [4][5]. |
| **Cargo Dependency Cooldowns (`min-publish-age`)** | Stabilizes RFC 3923 supply-chain protection: setting `global-min-publish-age = "3 days"` under `[registry]` in `.cargo/config.toml` instructs `cargo update` to skip newly published `crates.io` versions until the cooldown window elapses (overridable via `CARGO_RESOLVER_INCOMPATIBLE_PUBLISH_AGE=allow`) [4][5][6]. |
| **Cargo Lints & Build-Dir Layout** | Introduces the `[lints.cargo]` table in `Cargo.toml` with warn-by-default `cargo::unused_dependencies`, and reorganizes the intermediate `build-dir` directory layout around build-step hashes to prevent cache collisions across `--features` and Git worktrees [4][5][6]. |
| **Platform & Standard Library Updates** | Promotes `wasm32-wasip3` to Tier 2 (with WASI SDK 34), updates the standard library to **Unicode 18.0.0**, stabilizes `-Cprofile-sample-use` and `extern "custom"`, and adds `str::trim_prefix`, `str::trim_suffix`, `bool::toggle`, `Vec::from_fn`, and `Box::map`/`Rc::map`/`Arc::map` [4][5]. |

## Governance and The Rust Foundation

Technical evolution of the language, compiler, and standard library is governed by the **Rust Project Teams** through the public Request for Comments (**RFC**) process, while legal, financial, trademark, and infrastructure stewardship is managed by **The Rust Foundation**, an independent non-profit organization established in 2021 [2].

The Rust Foundation's Board of Directors shares equal voting representation between **Project Directors** elected from the Rust Project and **Member Directors** representing corporate Platinum and Silver sponsors [2]. As of late 2026, corporate board seats are held by **Nell Shamrell-Harrington** (Board Chair, representing Microsoft), **Jeffrey Vander Stoep** (Google / Android Security), **Andrew Wafaa** (Arm), **Predrag Gruevski** (OpenAI), **Jared Roesch** (NVIDIA), **Jess Wass** (Meta), **Jacob Creech** (Solana Foundation), and **Alexandru Radovici** (Silver Member Representative) [2]. Under its **2026-2028 Strategic Plan**, the Foundation operates the Rust Innovation Lab, the Security Initiative (supporting `crates.io` supply-chain hardening and automated malware scanning), the C++/Python Interop Initiative, and Trusted Training programs [2][4].

## Frequently asked questions

### What is the latest version of the Rust programming language as of November 2026?

The latest stable version is Rust 1.100.0, released on November 12, 2026. It stabilized the never type (!), the core std::alloc::Allocator trait for Box and Vec, core::mem::DropGuard, core::mem::conjure_zst, Cargo unused-dependency linting, and Cargo dependency cooldowns (min-publish-age). [1][4][5]

### What is the never type (!) stabilized in Rust 1.100.0?

The never type, written as '!', is Rust's canonical uninhabited type representing computations that never return a value (such as return, break, panic!, or std::process::exit). After 10 years of development, Rust 1.100.0 allows naming '!' in any type argument (such as Result<T, !>), makes core::convert::Infallible a type alias for '!', and unifies the never-type fallback to '!' across all Rust editions. [4][5][7]

### How do Cargo dependency cooldowns (min-publish-age) improve supply-chain security in Rust 1.100.0?

Stabilized in Rust 1.100.0 (RFC 3923), configuring 'global-min-publish-age' (for example, '3 days') in .cargo/config.toml instructs Cargo's dependency resolver to ignore newly published package versions on crates.io until they have been public for that duration, giving security scanners and the community time to detect and yank malicious releases. [4][5][6]

### How does Rust achieve memory safety without a garbage collector?

Rust enforces an ownership and borrowing model at compile time: every value has a single owner and is automatically dropped when its owner leaves scope, and references must obey the rule of either multiple immutable borrows (&T) or a single mutable borrow (&mut T) with statically verified lifetimes. [1][4]

### What are Rust Editions and do they break compatibility between crates?

Rust Editions (2015, 2018, 2021, and 2024) are opt-in per-crate configurations in Cargo.toml that allow Rust to introduce new keywords or syntax changes without breaking existing code. Editions do not split the ecosystem because all editions compile to the same internal compiler representation and interoperate seamlessly within a single build. [3]

## Quotable sentences

- Rust 1.100.0 was released on November 12, 2026, stabilizing the never type (!) in all type positions after 10 years and five prior stabilization attempts. [4][5][7]
- In Rust 1.100.0, core::convert::Infallible became a type alias to the never type (!), and the never-type fallback was changed from () to ! across editions 2015, 2018, and 2021 to match edition 2024. [4][5]
- Rust 1.100.0 stabilized std::alloc::Allocator for Box and Vec, core::mem::DropGuard, core::mem::conjure_zst, Unicode 18.0.0 support, and Tier 2 promotion for wasm32-wasip3. [4][5]
- Cargo 1.100 introduced the [lints.cargo] unused_dependencies lint, a new hash-organized build-dir directory layout, and min-publish-age dependency cooldowns (RFC 3923). [4][5][6]
- The Rust Foundation's Board of Directors is chaired by Nell Shamrell-Harrington (Microsoft) and includes member directors from Google, Arm, OpenAI, NVIDIA, Meta, and the Solana Foundation alongside Rust Project directors. [2]

## Timeline

- 2015-05-15: Rust 1.0.0 is released, establishing the 'stability without stagnation' backward-compatibility guarantee and the six-week release train. [3]
- 2018-12: Rust 2018 Edition launches, introducing the opt-in edition migration mechanism in Cargo. [3]
- 2021-02: The Rust Foundation is established as an independent non-profit steward for the Rust language and ecosystem. [2]
- 2026-09-25: Rust 1.100.0 branches from master into the beta testing channel. [5]
- 2026-11-12: Rust 1.100.0 is released on the stable channel, stabilizing the never type (!), std::alloc::Allocator, core::mem::DropGuard, and Cargo min-publish-age dependency cooldowns. [4][5][6]

## Sources

1. Rust Programming Language Official Website (Version 1.100.0). The Rust Project. https://rust-lang.org/ (checked 2026-11-23; tier 3: official site)
2. About The Rust Foundation: Mission, 2026-2028 Strategy, and Board of Directors. The Rust Foundation. https://rustfoundation.org/about/ (checked 2026-11-23; tier 3: official site)
3. What are Editions? - The Rust Edition Guide. The Rust Project. https://doc.rust-lang.org/edition-guide/editions/index.html (checked 2026-11-23; tier 3: official site)
4. Announcing Rust 1.100.0. The Rust Release Team / Rust Blog. published 2026-11-12. https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/ (checked 2026-11-23; tier 3: official site)
5. Rust 1.100.0 Release Notes (rust-lang/rust). GitHub / The Rust Project. published 2026-11-12. https://github.com/rust-lang/rust/releases/tag/1.100.0 (checked 2026-11-23; tier 3: official site)
6. Cargo 1.100 Changelog (2026-11-12) - The Cargo Book. The Rust Project. published 2026-11-12. https://doc.rust-lang.org/cargo/CHANGELOG.html (checked 2026-11-23; tier 3: official site)
7. Rust 1.100 Released With The 'Never' Type Finally Stable. Phoronix. published 2026-11-12. https://www.phoronix.com/news/Rust-1.100-Released (checked 2026-11-23; tier 2: academic or news)

## Cite this page

Mimirwiki. "Rust (Programming Language)." Version 50f11e7e, 2026-11-23. https://mimirwiki.com/wiki/rust-programming-language
