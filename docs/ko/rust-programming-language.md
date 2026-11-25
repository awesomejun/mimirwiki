---
title: "러스트 (Rust 프로그래밍 언어)"
subtitle: "가비지 컬렉터 없이 컴파일 타임에 메모리 안전성과 스레드 안전성을 보장하는 다중 패러다임 시스템 프로그래밍 언어"
canonical_url: https://mimirwiki.com/ko/wiki/rust-programming-language
language: ko
page_class: entity
revision_sha256: 1a6792fcbaa4040895fe633299b00d1ca47c907c65d1fb4f17f4900e135cad14
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/ko/wiki/rust-programming-language.md
  txt: https://mimirwiki.com/ko/wiki/rust-programming-language.txt
  json: https://mimirwiki.com/ko/wiki/rust-programming-language.json
  jsonld: https://mimirwiki.com/ko/wiki/rust-programming-language.jsonld
translations:
  en: https://mimirwiki.com/wiki/rust-programming-language
  ja: https://mimirwiki.com/ja/wiki/rust-programming-language
  zh: https://mimirwiki.com/zh/wiki/rust-programming-language
  es: https://mimirwiki.com/es/wiki/rust-programming-language
---

# 러스트 (Rust 프로그래밍 언어)

> 2026년 11월 12일 러스트 릴리스 팀은 6주 주기의 릴리스 트레인에 따라 기념비적인 Rust 1.100.0 정식(Stable) 버전을 출시했다. Rust 1.100.0은 10년간 5차례의 시도 끝에 네버 타입(Never type, !)을 모든 타입 위치에서 완전히 안정화하여 core::convert::Infallible을 !의 타입 별칭으로 통합하고 전 에디션의 폴백(fallback)을 !로 일원화했으며, 커스텀 할당자 트레이트(std::alloc::Allocator), core::mem::DropGuard, core::mem::conjure_zst, 그리고 카고(Cargo)의 미사용 의존성 린트([lints.cargo])와 공급망 보안용 의존성 쿨다운(global-min-publish-age) 기능을 정식 도입했다.

러스트(Rust)는 2006년 모질라 리서치(Mozilla Research)의 그레이던 호어(Graydon Hoare)가 처음 설계하여 2015년 5월 1.0 정식 버전을 출시하고, 2021년 2월부터 비영리 러스트 재단(Rust Foundation)이 관리하고 있는 범용 다중 패러다임 컴파일 시스템 프로그래밍 언어이다. 가비지 컬렉터(Garbage Collector)나 무거운 런타임 없이도 소유권(Ownership), 빌림(Borrowing), 수명(Lifetime) 타입 시스템을 통해 컴파일 타임에 메모리 안전성 버그(널·댕글링 포인터 역참조, 버퍼 오버플로 등)와 동시성 데이터 레이스(Data Race)를 원천 차단한다.

**다른 이름:** Rust, 러스트 언어, rust-lang, rustc, Cargo, Rust 1.100.0

## 핵심 정보

- **관리 재단:** 러스트 재단 (The Rust Foundation; 이사회 의장 넬 샴렐-해링턴) (기준 2026-11-23) [2]
- **최신 정식 버전:** Rust 1.100.0 (2026년 11월 12일 출시) (기준 2026-11-12) [4]
- **언어 에디션:** Rust 2015, Rust 2018, Rust 2021, Rust 2024 [3]
- **1.100.0 핵심 안정화 기능:** 네버 타입(!), std::alloc::Allocator API, DropGuard, Cargo min-publish-age (기준 2026-11-12) [4]

## 기본 정보

- **초기 설계자:** 그레이던 호어 (Graydon Hoare, 모질라 리서치 후원) [1]
- **관리 주체:** 러스트 재단 (The Rust Foundation) 및 러스트 프로젝트 팀 [2]
- **1.0.0 정식 출시일:** 2015년 5월 15일 [3]
- **현재 최신 버전:** 1.100.0 (2026년 11월 12일) [4]
- **릴리스 주기:** 6주 릴리스 트레인 (Nightly -> Beta -> Stable) [4]
- **패키지 매니저 및 레지스트리:** Cargo / crates.io (툴체인 설치기: rustup) [1]
- **타입 시스템:** 정적 강타입, 아핀 소유권 및 빌림 검사, 대수적 데이터 타입(ADT), 트레이트 [1]
- **라이선스:** Apache License 2.0 및 MIT 라이선스 듀얼 라이선스 [1]

## 개요, 소유권 모델 및 표준 툴체인 생태계

러스트(Rust)는 **'정체 없는 안정성(stability without stagnation)'**을 핵심 철학으로 삼아 저수준 임베디드·운영체제 커널부터 대규모 분산 웹 서비스까지 컴파일 타임 메모리 안전성을 보장하도록 설계된 정적 타입 시스템 프로그래밍 언어이다 [1][3]. 가비지 컬렉션에 의존하는 관리형 언어(Java, Go 등)나 수동 메모리 해제를 프로그래머에게 일임하는 C·C++와 달리, 러스트는 컴파일러의 **소유권(Ownership) 및 빌림 검사기(Borrow Checker)**를 통해 결정론적 자원 관리(RAII)를 강제한다 [1][4]: - 러스트의 모든 값은 단 하나의 소유자 변수를 가지며, 소유자가 스코프(scope)를 벗어나는 즉시 `Drop` 트레이트 구현을 통해 메모리가 자동 해제된다 [4]. - 참조(Reference)는 엄격한 '별칭 혹은 가변성 배타 규칙(aliasing XOR mutability)'을 따른다. 특정 시점에 불변 참조(`&T`)는 여러 개 존재할 수 있으나 가변 참조(`&mut T`)는 단 하나만 허용되며, 수명(Lifetime) 분석을 통해 참조가 원본 데이터보다 오래 살아남는 댕글링 포인터를 컴파일 타임에 차단한다 [1]. - 원시 포인터 역참조, 외부 함수 인터페이스(FFI) 호출, 또는 `std::mem::conjure_zst`를 통한 크기 0인 타입(ZST) 생성처럼 컴파일러가 정적으로 증명할 수 없는 저수준 연산은 반드시 명시적인 `unsafe` 블록 내부로 격리해야 한다 [4].

러스트는 **`rustup`**으로 관리되는 공식 통합 툴체인을 기본 제공하며, 여기에는 LLVM 기반 컴파일러(**`rustc`**), 빌드 시스템 겸 패키지 매니저(**`Cargo`**), 공개 패키지 레지스트리(**`crates.io`**), 문서 생성기(**`rustdoc`**), 정적 분석 린터(**`Clippy`**), 코드 포매터(**`rustfmt`**)가 포함된다 [1][4].

## 6주 릴리스 트레인 및 에디션(Edition) 시스템

2015년 5월 **Rust 1.0.0** 출시 이후 러스트 프로젝트는 **나이틀리(Nightly, 매일 `main` 브랜치에서 빌드)**, **베타(Beta, 6주마다 분기되어 회귀 테스트 진행)**, **스테이블(Stable, 6주마다 정식 배포)**의 3단계 채널로 구성된 **6주 릴리스 트레인 모델**을 엄격히 운영하고 있다 [3][4][5].

하위 호환성을 깨뜨리지 않으면서도 `async`/`await` 같은 새로운 예약어를 도입하거나 타입 추론 폴백 규칙을 개선하기 위해 러스트는 크레이트별 옵트인(opt-in) 방식의 **에디션(Edition)** 제도(`Cargo.toml` 내 `edition = "2015"`, `"2018"`, `"2021"`, `"2024"`)를 사용한다 [3][4]. 에디션은 생태계를 분열시키지 않는 것이 핵심 원칙으로, 서로 다른 에디션으로 작성된 크레이트라도 컴파일러 내부에서는 동일한 중간 표현(HIR/MIR)으로 변환되어 단일 빌드 내에서 완벽히 상호운용된다 [3]. 개발자는 `cargo fix --edition` 명령을 통해 기존 코드를 새 에디션으로 자동 마이그레이션할 수 있다 [3].

## Rust 1.100.0 마일스톤 릴리스 (2026년 11월 12일)

**2026년 11월 12일** 러스트 릴리스 팀은 **Rust 1.100.0**(2026년 9월 25일 마스터 분기)을 정식 출시하며 오랜 기간 준비해 온 언어 코어, 표준 라이브러리 및 카고(Cargo) 공급망 보안 기능들을 대거 안정화했다 [4][5][6]:

| 주요 기능 / 컴포넌트 | Rust 1.100.0 안정화 및 변경 내용 |
| --- | --- |
| **네버 타입 (`!`, Never Type)** | 10년간 5차례의 시도 끝에 최종 안정화 완료. 값을 절대 반환하지 않는 발산 연산(`return`, `break`, `panic!`, `std::process::exit`)을 나타내는 비거주 타입(uninhabited type)으로 임의 타입으로의 강제 변환(never-to-any coercion)을 지원한다. 이제 `Result<T, !>`처럼 모든 제네릭 타입 인자 위치에 `!`를 직접 명시할 수 있으며, `core::convert::Infallible`이 `!`의 타입 별칭으로 전환되었고 모든 에디션(2015, 2018, 2021, 2024)의 네버 타입 폴백이 `()`에서 `!`로 통일되었다 [4][5][7]. |
| **커스텀 할당자 API (`std::alloc::Allocator`)** | `Allocator` 코어 트레이트와 `Global`, `System` 할당자, 그리고 `Box`(`Box::new_in`, `Box::from_raw_in`, `Box::allocator`) 및 `Vec`(`Vec::new_in`, `Vec::with_capacity_in`, `Vec::from_raw_parts_in`)의 커스텀 할당자 메서드를 안정화하여 'Allocators 1.0' 프로젝트 목표의 기반을 확립했다 [4][5]. |
| **`core::mem::DropGuard`** | 변수와 클로저를 함께 감싸 스코프 종료 시 무조건 클로저를 실행하는 새로운 RAII 헬퍼 타입이다. `Deref`/`DerefMut`를 구현하여 내부 변수를 그대로 조작할 수 있으며, 트랜잭션이 성공했을 때는 `DropGuard::dismiss(guard)`를 호출해 롤백 클로저 실행을 취소하고 값을 회수할 수 있다 [4][5]. |
| **`core::mem::conjure_zst`** | `transmute(())`나 `MaybeUninit` 우회 패턴 없이 크기 0인 타입(Zero-Sized Type, ZST)의 인스턴스를 안전성이 보장된 컨텍스트에서 명시적으로 생성하는 `unsafe fn conjure_zst<T>() -> T` 함수를 추가했다 [4][5]. |
| **Cargo 의존성 쿨다운 (`min-publish-age`)** | 공급망 공격 방어를 위한 RFC 3923 안정화. `.cargo/config.toml`의 `[registry]` 섹션에 `global-min-publish-age = "3 days"` 등을 설정하면 `cargo update` 시 지정된 기간보다 최근에 배포된 `crates.io` 패키지 버전을 보류하여 악성 패키지 탐지 시간을 확보한다(긴급 시 `CARGO_RESOLVER_INCOMPATIBLE_PUBLISH_AGE=allow`로 개별 허용 가능) [4][5][6]. |
| **Cargo 자체 린트 및 빌드 디렉터리 개편** | `Cargo.toml`의 `[lints.cargo]` 테이블을 도입하고 기본 경고인 `cargo::unused_dependencies`로 미사용 의존성을 탐지한다. 또한 중간 산출물 폴더인 `build-dir`의 디렉터리 구조를 빌드 단계 해시 중심으로 전면 개편해 `--features`나 Git 워크트리 간 캐시 충돌을 해소했다 [4][5][6]. |
| **플랫폼 및 표준 라이브러리 확장** | `wasm32-wasip3` 타깃을 Tier 2로 승격(WASI SDK 34 적용)하고 표준 라이브러리를 **유니코드(Unicode) 18.0.0**으로 업데이트했으며, `-Cprofile-sample-use`, `extern "custom"`, `str::trim_prefix`, `str::trim_suffix`, `bool::toggle`, `Vec::from_fn`, `Box::map`/`Rc::map`/`Arc::map` 등을 안정화했다 [4][5]. |

## 거버넌스 및 러스트 재단(The Rust Foundation)

러스트 언어와 컴파일러, 표준 라이브러리의 기술적 의사결정은 공개 제안서 프로세스인 **RFC(Request for Comments)**를 통해 **러스트 프로젝트 팀(Rust Project Teams)**이 주도하며, 재정·법무·상표권 및 클라우드 인프라 지원은 2021년 설립된 독립 비영리 기구인 **러스트 재단(The Rust Foundation)**이 담당한다 [2].

러스트 재단 이사회(Board of Directors)는 러스트 프로젝트에서 선출된 프로젝트 이사(Project Directors)와 후원 기업을 대표하는 회원사 이사(Member Directors)가 동등한 의결권을 갖는 공동 거버넌스 구조로 운영된다 [2]. 2026년 11월 기준 회원사 이사진에는 이사회 의장인 **넬 샴렐-해링턴(Nell Shamrell-Harrington, 마이크로소프트)**을 비롯해 **제프리 밴더 스톱(구글 안드로이드 보안팀)**, **앤드루 와파(Arm)**, **프레드라그 그루에프스키(오픈AI)**, **재러드 로시(엔비디아)**, **제스 와스(메타)**, **제이콥 크리치(솔라나 재단)**, 그리고 실버 회원사 대표인 **알렉산드루 라도비치**가 참여하고 있다 [2]. 재단은 **2026-2028 전략 계획(Strategic Plan)**에 따라 러스트 이노베이션 랩, `crates.io` 공급망 보안을 강화하는 시큐리티 이니셔티브, 상호운용성(Interop) 이니셔티브 및 공인 교육 프로그램을 운영한다 [2][4].

## 자주 묻는 질문

### 2026년 11월 기준 러스트(Rust) 프로그래밍 언어의 최신 버전은 무엇인가요?

2026년 11월 12일 출시된 Rust 1.100.0이 최신 정식(Stable) 버전입니다. 이 버전에서는 10년간 개발되어 온 네버 타입(!)을 비롯해 Box와 Vec을 위한 std::alloc::Allocator 트레이트, core::mem::DropGuard, core::mem::conjure_zst, Cargo 미사용 의존성 린트, 그리고 공급망 보안용 의존성 쿨다운(min-publish-age) 기능이 안정화되었습니다. [1][4][5]

### Rust 1.100.0에서 최종 안정화된 네버 타입(!)이란 무엇인가요?

코드에서 느낌표('!')로 표기하는 네버 타입(Never type)은 return, break, panic!, std::process::exit처럼 정상적인 값을 반환하지 않고 제어 흐름을 종료(발산)하는 연산의 타입입니다. Rust 1.100.0부터는 Result<T, !>와 같이 모든 타입 위치에서 '!'를 직접 사용할 수 있으며, 기존 core::convert::Infallible이 '!'의 별칭(type alias)으로 통합되었습니다. [4][5][7]

### Cargo 1.100에 도입된 의존성 쿨다운(min-publish-age)은 공급망 보안을 어떻게 강화하나요?

.cargo/config.toml의 [registry] 설정에 'global-min-publish-age = "3 days"'와 같이 최소 배포 경과 시간을 지정하면, cargo update 실행 시 crates.io에 올라온 지 해당 기간이 지나지 않은 신규 버전 설치를 자동으로 보류합니다. 이를 통해 악성 코드가 포함된 패키지가 자동 스캐너나 커뮤니티에 의해 탐지·회수될 수 있는 시간적 완충 장치를 제공합니다. [4][5][6]

### 러스트는 어떻게 가비지 컬렉터 없이 메모리 안전성을 보장하나요?

러스트 컴파일러는 모든 값에 단일 소유자를 부여하고 스코프 종료 시 메모리를 즉시 해제하는 소유권(Ownership) 규칙과, 다수의 불변 참조(&T) 또는 단 하나의 가변 참조(&mut T)만 허용하고 수명(Lifetime)을 검증하는 빌림 검사기(Borrow Checker)를 통해 런타임 가비지 컬렉터 없이 컴파일 타임에 메모리 오류를 차단합니다. [1][4]

### 러스트 에디션(Edition)이 다르면 크레이트 간 호환성이 깨지나요?

깨지지 않습니다. Rust 2015, 2018, 2021, 2024 에디션은 각 크레이트가 Cargo.toml에서 선택하는 문법 및 키워드 계층일 뿐이며, 컴파일러 내부에서는 모두 동일한 중간 표현으로 컴파일되므로 서로 다른 에디션의 라이브러리들이 하나의 프로젝트에서 완벽하게 함께 빌드되고 링크됩니다. [3]

## 인용 문장

- Rust 1.100.0은 2026년 11월 12일 정식 출시되었으며 10년간 5차례의 시도 끝에 네버 타입(!)을 모든 타입 위치에서 안정화했다. [4][5][7]
- Rust 1.100.0에서 core::convert::Infallible은 네버 타입(!)의 타입 별칭으로 변경되었으며 모든 에디션(2015, 2018, 2021, 2024)의 네버 타입 폴백이 !로 통일되었다. [4][5]
- Rust 1.100.0은 Box와 Vec용 std::alloc::Allocator, core::mem::DropGuard, core::mem::conjure_zst, 유니코드 18.0.0 지원 및 wasm32-wasip3의 Tier 2 승격을 반영했다. [4][5]
- Cargo 1.100은 [lints.cargo] 테이블 기반의 cargo::unused_dependencies 린트, 해시 기반의 신규 build-dir 레이아웃, 그리고 RFC 3923 기반의 min-publish-age 의존성 쿨다운 기능을 도입했다. [4][5][6]
- 러스트 재단 이사회는 넬 샴렐-해링턴(마이크로소프트)이 의장을 맡고 있으며 구글, Arm, 오픈AI, 엔비디아, 메타, 솔라나 재단 소속 이사들과 러스트 프로젝트 선출 이사들로 구성된다. [2]

## 연표

- 2015-05-15: Rust 1.0.0 정식 출시 및 하위 호환성 보장과 6주 릴리스 트레인 체계 확립. [3]
- 2018-12: Cargo 내 옵트인 에디션 전환 메커니즘을 도입한 첫 에디션인 Rust 2018 출시. [3]
- 2021-02: 러스트 언어와 생태계를 지원하는 독립 비영리 기구인 러스트 재단(The Rust Foundation) 출범. [2]
- 2026-09-25: Rust 1.100.0이 마스터 브랜치에서 베타(Beta) 테스트 채널로 분기됨. [5]
- 2026-11-12: 네버 타입(!), std::alloc::Allocator, core::mem::DropGuard 및 Cargo min-publish-age 의존성 쿨다운을 안정화한 Rust 1.100.0 정식 출시. [4][5][6]

## 출처

1. Rust Programming Language Official Website (Version 1.100.0). The Rust Project. https://rust-lang.org/ (확인일 2026-11-23; tier 3: official site)
2. About The Rust Foundation: Mission, 2026-2028 Strategy, and Board of Directors. The Rust Foundation. https://rustfoundation.org/about/ (확인일 2026-11-23; tier 3: official site)
3. What are Editions? - The Rust Edition Guide. The Rust Project. https://doc.rust-lang.org/edition-guide/editions/index.html (확인일 2026-11-23; tier 3: official site)
4. Announcing Rust 1.100.0. The Rust Release Team / Rust Blog. 게시일 2026-11-12. https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/ (확인일 2026-11-23; tier 3: official site)
5. Rust 1.100.0 Release Notes (rust-lang/rust). GitHub / The Rust Project. 게시일 2026-11-12. https://github.com/rust-lang/rust/releases/tag/1.100.0 (확인일 2026-11-23; tier 3: official site)
6. Cargo 1.100 Changelog (2026-11-12) - The Cargo Book. The Rust Project. 게시일 2026-11-12. https://doc.rust-lang.org/cargo/CHANGELOG.html (확인일 2026-11-23; tier 3: official site)
7. Rust 1.100 Released With The 'Never' Type Finally Stable. Phoronix. 게시일 2026-11-12. https://www.phoronix.com/news/Rust-1.100-Released (확인일 2026-11-23; tier 2: academic or news)

## 이 문서 인용하기

Mimirwiki. "러스트 (Rust 프로그래밍 언어)." 버전 1a6792fc, 2026-11-24. https://mimirwiki.com/ko/wiki/rust-programming-language
