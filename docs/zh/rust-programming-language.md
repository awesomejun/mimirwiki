---
title: "Rust（编程语言）"
subtitle: "无需垃圾回收器即可在编译期强制保障内存安全与线程安全的多范式系统编程语言"
canonical_url: https://mimirwiki.com/zh/wiki/rust-programming-language
language: zh
page_class: entity
revision_sha256: 54f9c1d6a60a9609fe909e5fedcc51b61b37967bc8edbb3c85cac65c2478922d
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/zh/wiki/rust-programming-language.md
  txt: https://mimirwiki.com/zh/wiki/rust-programming-language.txt
  json: https://mimirwiki.com/zh/wiki/rust-programming-language.json
  jsonld: https://mimirwiki.com/zh/wiki/rust-programming-language.jsonld
translations:
  en: https://mimirwiki.com/wiki/rust-programming-language
  ko: https://mimirwiki.com/ko/wiki/rust-programming-language
  ja: https://mimirwiki.com/ja/wiki/rust-programming-language
  es: https://mimirwiki.com/es/wiki/rust-programming-language
---

# Rust（编程语言）

> 2026 年 11 月 12 日，Rust 发布团队按 6 周发布列车周期推出了里程碑式的 Rust 1.100.0 稳定版。历经 10 年与五次先前的稳定化尝试后，Rust 1.100.0 在所有类型位置稳定了 never 类型（!），使 core::convert::Infallible 成为 ! 的类型别名，并在所有版次（Edition）中将 never 类型回退（fallback）统一为 !；同时稳定了用于 Box 与 Vec 的核心 Allocator trait（std::alloc::Allocator）、core::mem::DropGuard、core::mem::conjure_zst、Cargo 的 [lints.cargo] unused_dependencies 检查、全新的中间 build-dir 目录布局以及 Cargo 依赖冷却期（global-min-publish-age）。

Rust 是一种通用、多范式的编译型系统编程语言，最初由 Graydon Hoare 于 2006 年在 Mozilla Research 设计，于 2015 年 5 月发布 1.0 版本，并自 2021 年 2 月起由非营利组织 Rust 基金会（The Rust Foundation）负责托管与治理。通过无需垃圾回收器或强制运行时即可在编译期强制执行的所有权（ownership）、借用（borrowing）与生命周期（lifetime）类型系统，Rust 能够防止内存安全漏洞（如空指针或悬垂指针解引用以及缓冲区溢出）以及并发代码中的数据竞争。

**别名:** Rust, rust-lang, rustc, Cargo, Rust 1.100.0

## 关键事实

- **托管组织:** Rust 基金会（501(c)(6) 非营利组织；董事会主席 Nell Shamrell-Harrington） (截至 2026-11-23) [2]
- **最新稳定版:** Rust 1.100.0（发布于 2026 年 11 月 12 日） (截至 2026-11-12) [4]
- **语言版次:** Rust 2015、Rust 2018、Rust 2021 与 Rust 2024 [3]
- **1.100.0 旗舰特性:** 稳定 never 类型（!）、std::alloc::Allocator API、DropGuard、Cargo min-publish-age (截至 2026-11-12) [4]

## 事实摘要

- **最初设计者:** Graydon Hoare（最初由 Mozilla Research 赞助） [1]
- **托管机构:** Rust 基金会（The Rust Foundation）与 Rust 项目团队 [2]
- **首个稳定版（1.0.0）:** 2015 年 5 月 15 日 [3]
- **当前稳定版:** 1.100.0（2026 年 11 月 12 日） [4]
- **发布周期:** 6 周发布列车模型（Nightly -> Beta -> Stable） [4]
- **包管理器与注册表:** Cargo / crates.io（工具链安装器：rustup） [1]
- **类型系统:** 静态、强类型、仿射所有权与借用、代数数据类型、trait [1]
- **许可证:** Apache License 2.0 与 MIT License 双重许可 [1]

## Rust 概述、所有权模型与工具链生态

Rust 是一种围绕**“稳定而不停滞（stability without stagnation）”**原则构建的静态类型系统编程语言，使开发者能够在编译期内存安全保证下编写底层、裸机（bare-metal）与高并发软件。[1][3] 与依赖追踪式垃圾回收的托管语言（如 Java 或 Go）或将手动内存管理完全交由程序员的传统系统语言（如 C 与 C++）不同，Rust 通过其**所有权与借用检查器（ownership and borrow checker）**强制实施确定性资源管理（RAII）。[1][4] - Rust 中的每个值都有唯一的所有者变量，当所有者离开作用域时，该值会通过其 `Drop` 实现自动释放。[4] - 引用遵循严格的“别名与可变性互斥（aliasing-xor-mutability）”规则：在执行的任意时刻，代码要么持有任意数量的不可变引用（`&T`），要么仅持有唯一一个可变引用（`&mut T`），并且通过生命周期（lifetime）在静态上保证引用的存活时间绝不会超过其所指对象。[1] - 编译器无法静态验证的底层操作（例如解引用裸指针、FFI 调用，或通过 `std::mem::conjure_zst` 创建零大小标记令牌）必须显式封装在 `unsafe` 代码块内。[4]

Rust 随附由 **`rustup`** 管理的集成官方工具链，包含基于 LLVM 的编译器（**`rustc`**）、构建系统与包管理器（**`Cargo`**）、公共包注册表（**`crates.io`**）、文档生成器（**`rustdoc`**）、静态检查工具（**`Clippy`**）以及代码格式化工具（**`rustfmt`**）。[1][4]

## Rust 的 6 周发布列车与版次（Edition）机制

自 2015 年 5 月发布 **Rust 1.0.0** 以来，Rust 项目持续运行涵盖三个通道的快速 **6 周列车发布模型**：**Nightly**（每日从 `main` 分支构建，支持实验性 `-Z` 标志）、**Beta**（在经历“无工具破坏周（No Tools Breakage Week）”后每 6 周分支一次用于回归测试）以及 **Stable**。[3][4][5]

为了在不破坏现有代码库的前提下演进语法与惯用法（例如引入 `async` 和 `await` 等新保留关键字，或调整类型推断回退规则），Rust 采用可选加入的**版次（Editions）**机制（在 `Cargo.toml` 中配置 `edition = "2015"`、`"2018"`、`"2021"` 与 `"2024"`）。[3][4] 版次不会分裂生态系统：所有版次最终都会编译为相同的编译器内部中间表示（HIR/MIR），从而使基于 Rust 2015 编译的 crate 能够与基于 Rust 2024 编译的依赖项无缝链接并互操作。[3] 版次之间的自动迁移通过 `cargo fix --edition` 提供。[3]

## Rust 1.100.0 里程碑版本（2026 年 11 月 12 日）

**2026 年 11 月 12 日**，Rust 发布团队发布了 **Rust 1.100.0**（于 2026 年 9 月 25 日自 master 分支切出），带来了多项备受期待的语言核心、标准库及 Cargo 供应链安全特性。[4][5][6]

| 特性 / 组件 | Rust 1.100.0 稳定化摘要 |
| --- | --- |
| **Never 类型（`!`）** | 历经 10 年与 5 次先前尝试后正式稳定。`!` 是表示发散计算（`return`、`break`、`panic!`、`std::process::exit`）的标准空类型（uninhabited type），支持自动从 never 类型强制转换为任意类型。如今可在任意类型位置显式书写 `!`（例如 `Result<T, !>`），`core::convert::Infallible` 已成为 `!` 的类型别名，且所有版次（2015、2018、2021 与 2024）的 never 类型回退已统一为 `!`。[4][5][7] |
| **自定义分配器 API（`std::alloc::Allocator`）** | 稳定了核心 `Allocator` trait、`Global` 与 `System` 分配器，以及 `Box`（`Box::new_in`、`Box::from_raw_in`、`Box::allocator`）和 `Vec`（`Vec::new_in`、`Vec::with_capacity_in`、`Vec::from_raw_parts_in`）的自定义分配器构造函数与访问器，为 Allocators 1.0 目标奠定基础。[4][5] |
| **`core::mem::DropGuard`** | 封装值与闭包的全新 RAII 辅助类型（`DropGuard::new(val, | v | ...)`），实现了 `Deref`/`DerefMut`，并在每次离开作用域时执行清理闭包，除非通过 `DropGuard::dismiss(guard)` 显式解除，适用于事务回滚等模式。[4][5] |
| **`core::mem::conjure_zst`** | 专用的 `unsafe fn conjure_zst<T>() -> T` 函数，用于安全地构造可居住的零大小类型（ZST）实例，无需依赖临时的 `transmute(())` 或 `MaybeUninit` 写法。[4][5] |
| **Cargo 依赖冷却期（`min-publish-age`）** | 稳定了 RFC 3923 供应链防护机制：在 `.cargo/config.toml` 的 `[registry]` 下设置 `global-min-publish-age = "3 days"` 后，`cargo update` 将跳过 `crates.io` 上尚未度过冷却期的新发布版本（可通过 `CARGO_RESOLVER_INCOMPATIBLE_PUBLISH_AGE=allow` 覆盖）。[4][5][6] |
| **Cargo Lint 与 Build-Dir 布局** | 在 `Cargo.toml` 中引入 `[lints.cargo]` 表及默认警告的 `cargo::unused_dependencies`，并围绕构建步骤哈希重构了中间 `build-dir` 目录布局，以防止跨 `--features` 与 Git 工作树（worktree）的缓存冲突。[4][5][6] |
| **平台与标准库更新** | 将 `wasm32-wasip3` 提升至 Tier 2（搭配 WASI SDK 34），将标准库更新至 **Unicode 18.0.0**，稳定了 `-Cprofile-sample-use` 与 `extern "custom"`，并新增了 `str::trim_prefix`、`str::trim_suffix`、`bool::toggle`、`Vec::from_fn` 以及 `Box::map`/`Rc::map`/`Arc::map`。[4][5] |

## Rust 治理结构与 Rust 基金会

Rust 语言、编译器与标准库的技术演进由 **Rust 项目团队（Rust Project Teams）** 通过公开的意见征求（**RFC**）流程进行治理，而法律、财务、商标与基础设施托管则由 2021 年成立的独立非营利组织 **Rust 基金会（The Rust Foundation）** 负责。[2]

Rust 基金会董事会在投票权上由从 Rust 项目选举产生的**项目董事（Project Directors）**与代表白金及白银企业赞助商的**成员董事（Member Directors）**平等共享。[2] 截至 2026 年底，企业董事席位由 **Nell Shamrell-Harrington**（董事会主席，代表 Microsoft）、**Jeffrey Vander Stoep**（Google / Android Security）、**Andrew Wafaa**（Arm）、**Predrag Gruevski**（OpenAI）、**Jared Roesch**（NVIDIA）、**Jess Wass**（Meta）、**Jacob Creech**（Solana 基金会）以及 **Alexandru Radovici**（白银成员代表）担任。[2] 在其 **2026-2028 战略规划（Strategic Plan）**下，基金会运营着 Rust 创新实验室（Rust Innovation Lab）、安全倡议（支持 `crates.io` 供应链加固与自动化恶意软件扫描）、C++/Python 互操作倡议以及可信培训（Trusted Training）项目。[2][4]

## 常见问题

### 截至 2026 年 11 月，Rust 编程语言的最新版本是什么？

最新稳定版是于 2026 年 11 月 12 日发布的 Rust 1.100.0。该版本稳定了 never 类型（!）、用于 Box 与 Vec 的核心 std::alloc::Allocator trait、core::mem::DropGuard、core::mem::conjure_zst、Cargo 未使用依赖检查（lint）以及 Cargo 依赖冷却期（min-publish-age）。 [1][4][5]

### Rust 1.100.0 中稳定化的 never 类型（!）是什么？

写作“!”的 never 类型是 Rust 的标准空类型（uninhabited type），用于表示永不返回值的计算（例如 return、break、panic! 或 std::process::exit）。历经 10 年开发后，Rust 1.100.0 允许在任意类型参数位置书写“!”（例如 Result<T, !>），将 core::convert::Infallible 设为“!”的类型别名，并在所有 Rust 版次中将 never 类型回退统一为“!”。 [4][5][7]

### Rust 1.100.0 中的 Cargo 依赖冷却期（min-publish-age）如何提升供应链安全？

该特性在 Rust 1.100.0（RFC 3923）中稳定：在 .cargo/config.toml 中配置“global-min-publish-age”（例如“3 days”）后，Cargo 的依赖解析器将忽略 crates.io 上公开发布时间不足该时长的新包版本，从而为安全扫描工具与社区争取发现并撤回（yank）恶意发布的时间窗口。 [4][5][6]

### Rust 如何在没有垃圾回收器的情况下实现内存安全？

Rust 在编译期强制执行所有权与借用模型：每个值都有唯一的所有者，并在所有者离开作用域时自动释放；引用必须遵守“多个不可变借用（&T）或唯一一个可变借用（&mut T）”的规则，且其生命周期在静态阶段接受验证。 [1][4]

### 什么是 Rust 版次（Edition）？不同版次会破坏 crate 之间的兼容性吗？

Rust 版次（2015、2018、2021 与 2024）是在 Cargo.toml 中按 crate 可选启用的配置，允许 Rust 在不破坏现有代码的前提下引入新关键字或语法变更。版次不会分裂生态系统，因为所有版次都会编译为相同的编译器内部表示，并在单次构建中无缝互操作。 [3]

## 可引用的句子

- Rust 1.100.0 于 2026 年 11 月 12 日发布，历经 10 年与五次先前的稳定化尝试后，在所有类型位置稳定了 never 类型（!）。 [4][5][7]
- 在 Rust 1.100.0 中，core::convert::Infallible 成为 never 类型（!）的类型别名，且 2015、2018 与 2021 版次的 never 类型回退从 () 更改为 !，以与 2024 版次保持一致。 [4][5]
- Rust 1.100.0 稳定了用于 Box 与 Vec 的 std::alloc::Allocator、core::mem::DropGuard、core::mem::conjure_zst、Unicode 18.0.0 支持，并将 wasm32-wasip3 提升至 Tier 2。 [4][5]
- Cargo 1.100 引入了 [lints.cargo] unused_dependencies lint、按哈希组织的全新 build-dir 目录布局以及 min-publish-age 依赖冷却期（RFC 3923）。 [4][5][6]
- Rust 基金会董事会由 Nell Shamrell-Harrington（Microsoft）担任主席，成员包括来自 Google、Arm、OpenAI、NVIDIA、Meta 和 Solana 基金会的成员董事以及 Rust 项目董事。 [2]

## 时间线

- 2015-05-15: Rust 1.0.0 发布，确立了“稳定而不停滞（stability without stagnation）”的向后兼容性保证与 6 周发布列车机制。 [3]
- 2018-12: Rust 2018 版次上线，在 Cargo 中引入了可选加入的版次迁移机制。 [3]
- 2021-02: Rust 基金会（The Rust Foundation）成立，作为 Rust 语言与生态系统的独立非营利托管组织。 [2]
- 2026-09-25: Rust 1.100.0 从 master 分支切入 Beta 测试通道。 [5]
- 2026-11-12: Rust 1.100.0 在稳定版通道发布，稳定了 never 类型（!）、std::alloc::Allocator、core::mem::DropGuard 以及 Cargo min-publish-age 依赖冷却期。 [4][5][6]

## 来源

1. Rust Programming Language Official Website (Version 1.100.0). The Rust Project. https://rust-lang.org/ (访问于 2026-11-23; tier 3: official site)
2. About The Rust Foundation: Mission, 2026-2028 Strategy, and Board of Directors. The Rust Foundation. https://rustfoundation.org/about/ (访问于 2026-11-23; tier 3: official site)
3. What are Editions? - The Rust Edition Guide. The Rust Project. https://doc.rust-lang.org/edition-guide/editions/index.html (访问于 2026-11-23; tier 3: official site)
4. Announcing Rust 1.100.0. The Rust Release Team / Rust Blog. 发布于 2026-11-12. https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/ (访问于 2026-11-23; tier 3: official site)
5. Rust 1.100.0 Release Notes (rust-lang/rust). GitHub / The Rust Project. 发布于 2026-11-12. https://github.com/rust-lang/rust/releases/tag/1.100.0 (访问于 2026-11-23; tier 3: official site)
6. Cargo 1.100 Changelog (2026-11-12) - The Cargo Book. The Rust Project. 发布于 2026-11-12. https://doc.rust-lang.org/cargo/CHANGELOG.html (访问于 2026-11-23; tier 3: official site)
7. Rust 1.100 Released With The 'Never' Type Finally Stable. Phoronix. 发布于 2026-11-12. https://www.phoronix.com/news/Rust-1.100-Released (访问于 2026-11-23; tier 2: academic or news)

## 引用本页

Mimirwiki. "Rust（编程语言）." 版本 54f9c1d6, 2026-11-24. https://mimirwiki.com/zh/wiki/rust-programming-language
