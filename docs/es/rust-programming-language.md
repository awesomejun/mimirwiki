---
title: "Rust (lenguaje de programación)"
subtitle: "Lenguaje de programación de sistemas multiparadigma que garantiza la seguridad de memoria y de hilos en tiempo de compilación sin recolector de basura"
canonical_url: https://mimirwiki.com/es/wiki/rust-programming-language
language: es
page_class: entity
revision_sha256: 50bb2794f09843a4be8d304af9740d8ff3b181eaf15a46d263a8e8ee76af7b9f
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/es/wiki/rust-programming-language.md
  txt: https://mimirwiki.com/es/wiki/rust-programming-language.txt
  json: https://mimirwiki.com/es/wiki/rust-programming-language.json
  jsonld: https://mimirwiki.com/es/wiki/rust-programming-language.jsonld
translations:
  en: https://mimirwiki.com/wiki/rust-programming-language
  ko: https://mimirwiki.com/ko/wiki/rust-programming-language
  ja: https://mimirwiki.com/ja/wiki/rust-programming-language
  zh: https://mimirwiki.com/zh/wiki/rust-programming-language
---

# Rust (lenguaje de programación)

> El 12 de noviembre de 2026, el Rust Release Team publicó la versión estable hito Rust 1.100.0 dentro de su ciclo de lanzamientos cada seis semanas. Tras 10 años y cinco intentos previos de estabilización, Rust 1.100.0 estabilizó el tipo never (!) en todas las posiciones de tipo (convirtiendo core::convert::Infallible en un alias de tipo de ! y estableciendo el respaldo del tipo never en ! para todas las ediciones), junto con el trait central Allocator (std::alloc::Allocator para Box y Vec), core::mem::DropGuard, core::mem::conjure_zst, la comprobación unused_dependencies de [lints.cargo] en Cargo, una nueva estructura del directorio intermedio build-dir y los periodos de espera de dependencias en Cargo (global-min-publish-age).

Rust es un lenguaje de programación de sistemas compilado, multiparadigma y de propósito general, diseñado originalmente por Graydon Hoare en Mozilla Research en 2006, que alcanzó la versión 1.0 en mayo de 2015 y es gestionado desde febrero de 2021 por la organización sin fines de lucro Rust Foundation. Mediante un sistema de tipos basado en propiedad, préstamos y tiempos de vida verificado en tiempo de compilación sin recolector de basura ni entorno de ejecución obligatorio, Rust previene errores de seguridad de memoria (como la desreferenciación de punteros nulos o colgantes y los desbordamientos de búfer) y las condiciones de carrera de datos en código concurrente.

**También conocido como:** Rust, rust-lang, rustc, Cargo, Rust 1.100.0

## Datos clave

- **Organización gestora:** The Rust Foundation (organización sin fines de lucro 501(c)(6); presidenta de la junta Nell Shamrell-Harrington) (al 2026-11-23) [2]
- **Última versión estable:** Rust 1.100.0 (publicada el 12 de noviembre de 2026) (al 2026-11-12) [4]
- **Ediciones del lenguaje:** Rust 2015, Rust 2018, Rust 2021 y Rust 2024 [3]
- **Novedades destacadas de 1.100.0:** Tipo never (!) estabilizado, API std::alloc::Allocator, DropGuard, min-publish-age de Cargo (al 2026-11-12) [4]

## Datos básicos

- **Diseñador original:** Graydon Hoare (patrocinado originalmente por Mozilla Research) [1]
- **Entidad gestora:** The Rust Foundation y los Rust Project Teams [2]
- **Primera versión estable (1.0.0):** 15 de mayo de 2015 [3]
- **Versión estable actual:** 1.100.0 (12 de noviembre de 2026) [4]
- **Cadencia de lanzamientos:** Modelo de tren cada seis semanas (Nightly -> Beta -> Stable) [4]
- **Gestor de paquetes y registro:** Cargo / crates.io (instalador de cadenas de herramientas: rustup) [1]
- **Sistema de tipos:** Estático, fuerte, propiedad y préstamos afines, tipos de datos algebraicos, traits [1]
- **Licencias:** Licencia dual bajo Apache License 2.0 y MIT License [1]

## Descripción general, modelo de propiedad y ecosistema de herramientas

Rust es un lenguaje de programación de sistemas de tipado estático diseñado en torno al principio de **«estabilidad sin estancamiento»**, que permite a los desarrolladores escribir software de bajo nivel, bare-metal y de alta concurrencia con garantías de seguridad de memoria en tiempo de compilación.[1][3] A diferencia de los lenguajes gestionados que dependen de la recolección de basura por rastreo (como Java o Go) o de los lenguajes de sistemas tradicionales que delegan por completo la gestión manual de memoria en el programador (como C y C++), Rust aplica una gestión determinista de recursos (RAII) mediante su **sistema de propiedad y verificador de préstamos (borrow checker)**:[1][4] - Cada valor en Rust tiene una única variable propietaria y se libera automáticamente mediante su implementación de `Drop` cuando el propietario sale de ámbito.[4] - Las referencias siguen una regla estricta de exclusividad entre aliasing y mutabilidad: en cualquier punto de la ejecución, el código puede mantener cualquier número de referencias inmutables (`&T`) o exactamente una referencia mutable (`&mut T`), y se garantiza estáticamente mediante tiempos de vida que las referencias nunca sobreviven al valor al que apuntan.[1] - Las operaciones de bajo nivel que el compilador no puede verificar estáticamente (como la desreferenciación de punteros sin procesar, las llamadas FFI o la creación de tokens marcadores de tamaño cero mediante `std::mem::conjure_zst`) deben encapsularse explícitamente dentro de bloques `unsafe`.[4]

Rust se distribuye con una cadena de herramientas oficial integrada gestionada por **`rustup`**, que incluye el compilador basado en LLVM (**`rustc`**), el sistema de compilación y gestor de paquetes (**`Cargo`**), el registro público de paquetes (**`crates.io`**), el generador de documentación (**`rustdoc`**), el analizador estático (**`Clippy`**) y el formateador de código (**`rustfmt`**).[1][4]

## Ciclo de lanzamiento de seis semanas y sistema de ediciones

Desde el lanzamiento de **Rust 1.0.0** en mayo de 2015, el proyecto Rust opera un rápido **modelo de lanzamientos en tren cada seis semanas** distribuido en tres canales: **Nightly** (compilado a diario desde la rama `main` con opciones experimentales `-Z`), **Beta** (ramificado cada seis semanas para pruebas de regresión, precedido por una semana sin rupturas de herramientas o «No Tools Breakage Week») y **Stable**.[3][4][5]

Para evolucionar la sintaxis y los modismos (como introducir nuevas palabras clave reservadas como `async` y `await` o cambiar las reglas de respaldo de inferencia de tipos) sin romper las bases de código existentes, Rust utiliza **ediciones** opcionales (`edition = "2015"`, `"2018"`, `"2021"` y `"2024"` en `Cargo.toml`).[3][4] Las ediciones no fragmentan el ecosistema: todas se compilan hacia las mismas representaciones intermedias internas del compilador (HIR/MIR), lo que permite que un crate compilado en Rust 2015 se enlace e interopere sin problemas con dependencias compiladas en Rust 2024.[3] La migración automatizada entre ediciones se realiza mediante `cargo fix --edition`.[3]

## Lanzamiento hito Rust 1.100.0 (12 de noviembre de 2026)

El **12 de noviembre de 2026**, el Rust Release Team publicó **Rust 1.100.0** (ramificado desde master el 25 de septiembre de 2026), incorporando varias características largamente esperadas para el lenguaje, la biblioteca estándar y la seguridad de la cadena de suministro en Cargo:[4][5][6]

| Característica / Componente | Resumen de la estabilización en Rust 1.100.0 |
| --- | --- |
| **El tipo never (`!`)** | Estabilizado tras 10 años y 5 intentos previos. `!` es el tipo vacío canónico para cómputos divergentes (`return`, `break`, `panic!`, `std::process::exit`) con coerción automática de never a cualquier tipo. Ahora puede nombrarse `!` en posiciones de tipo arbitrarias (por ejemplo, `Result<T, !>`), `core::convert::Infallible` pasa a ser un alias de tipo de `!` y el respaldo del tipo never se unifica en `!` para todas las ediciones (2015, 2018, 2021 y 2024).[4][5][7] |
| **API de asignadores personalizados (`std::alloc::Allocator`)** | Estabiliza el trait central `Allocator` junto con `Global`, `System` y constructores/accesores de asignadores personalizados para `Box` (`Box::new_in`, `Box::from_raw_in`, `Box::allocator`) y `Vec` (`Vec::new_in`, `Vec::with_capacity_in`, `Vec::from_raw_parts_in`), sentando la base para el objetivo Allocators 1.0.[4][5] |
| **`core::mem::DropGuard`** | Nuevo auxiliar RAII que envuelve un valor y un cierre (`DropGuard::new(val, | v | ...)`), implementa `Deref`/`DerefMut` y ejecuta el cierre de limpieza al salir de cada ámbito, salvo que se desactive explícitamente con `DropGuard::dismiss(guard)` para patrones de reversión transaccional.[4][5] |
| **`core::mem::conjure_zst`** | Función dedicada `unsafe fn conjure_zst<T>() -> T` para materializar de forma segura tipos habitados de tamaño cero (ZST) sin recurrir a patrones ad hoc con `transmute(())` o `MaybeUninit`.[4][5] |
| **Periodos de espera de dependencias en Cargo (`min-publish-age`)** | Estabiliza la protección de la cadena de suministro del RFC 3923: configurar `global-min-publish-age = "3 days"` bajo `[registry]` en `.cargo/config.toml` indica a `cargo update` que omita las versiones recién publicadas en `crates.io` hasta que transcurra el periodo de espera (anulable mediante `CARGO_RESOLVER_INCOMPATIBLE_PUBLISH_AGE=allow`).[4][5][6] |
| **Lints de Cargo y diseño de `build-dir`** | Introduce la tabla `[lints.cargo]` en `Cargo.toml` con `cargo::unused_dependencies` activado como advertencia por defecto, y reorganiza la estructura del directorio intermedio `build-dir` en torno a hashes por paso de compilación para evitar colisiones de caché entre `--features` y worktrees de Git.[4][5][6] |
| **Actualizaciones de plataformas y biblioteca estándar** | Promueve `wasm32-wasip3` a Nivel 2 (con WASI SDK 34), actualiza la biblioteca estándar a **Unicode 18.0.0**, estabiliza `-Cprofile-sample-use` y `extern "custom"`, y añade `str::trim_prefix`, `str::trim_suffix`, `bool::toggle`, `Vec::from_fn` y `Box::map`/`Rc::map`/`Arc::map`.[4][5] |

## Gobernanza y The Rust Foundation

La evolución técnica del lenguaje, el compilador y la biblioteca estándar está gobernada por los **Rust Project Teams** mediante el proceso público de solicitudes de comentarios (**RFC**), mientras que la gestión legal, financiera, de marcas registradas y de infraestructura corre a cargo de **The Rust Foundation**, una organización independiente sin fines de lucro creada en 2021.[2]

La Junta Directiva de The Rust Foundation reparte la representación con derecho a voto en partes iguales entre **Project Directors** elegidos desde el Rust Project y **Member Directors** que representan a los patrocinadores corporativos Platinum y Silver.[2] A finales de 2026, los puestos corporativos de la junta están ocupados por **Nell Shamrell-Harrington** (presidenta de la junta, en representación de Microsoft), **Jeffrey Vander Stoep** (Google / Android Security), **Andrew Wafaa** (Arm), **Predrag Gruevski** (OpenAI), **Jared Roesch** (NVIDIA), **Jess Wass** (Meta), **Jacob Creech** (Solana Foundation) y **Alexandru Radovici** (representante de miembros Silver).[2] En el marco de su **Plan Estratégico 2026-2028**, la Fundación gestiona el Rust Innovation Lab, la Security Initiative (que respalda el endurecimiento de la cadena de suministro de `crates.io` y el escaneo automatizado de malware), la C++/Python Interop Initiative y programas de Trusted Training.[2][4]

## Preguntas frecuentes

### ¿Cuál es la última versión del lenguaje de programación Rust en noviembre de 2026?

La última versión estable es Rust 1.100.0, publicada el 12 de noviembre de 2026. Estabilizó el tipo never (!), el trait central std::alloc::Allocator para Box y Vec, core::mem::DropGuard, core::mem::conjure_zst, el análisis de dependencias no utilizadas en Cargo y los periodos de espera de dependencias en Cargo (min-publish-age). [1][4][5]

### ¿Qué es el tipo never (!) estabilizado en Rust 1.100.0?

El tipo never, escrito como '!', es el tipo vacío canónico de Rust que representa cómputos que nunca devuelven un valor (como return, break, panic! o std::process::exit). Tras 10 años de desarrollo, Rust 1.100.0 permite nombrar '!' en cualquier argumento de tipo (como Result<T, !>), convierte core::convert::Infallible en un alias de tipo de '!' y unifica el respaldo del tipo never en '!' en todas las ediciones de Rust. [4][5][7]

### ¿Cómo mejoran los periodos de espera de dependencias de Cargo (min-publish-age) la seguridad de la cadena de suministro en Rust 1.100.0?

Estabilizada en Rust 1.100.0 (RFC 3923), la configuración de 'global-min-publish-age' (por ejemplo, '3 days') en .cargo/config.toml indica al resolvedor de dependencias de Cargo que ignore las versiones de paquetes recién publicadas en crates.io hasta que hayan estado disponibles públicamente durante ese lapso, dando tiempo a los escáneres de seguridad y a la comunidad para detectar y retirar versiones maliciosas. [4][5][6]

### ¿Cómo logra Rust la seguridad de memoria sin un recolector de basura?

Rust aplica un modelo de propiedad y préstamos en tiempo de compilación: cada valor tiene un único propietario y se libera automáticamente cuando su propietario sale de ámbito, y las referencias deben cumplir la regla de permitir múltiples préstamos inmutables (&T) o un único préstamo mutable (&mut T) con tiempos de vida verificados estáticamente. [1][4]

### ¿Qué son las ediciones de Rust y rompen la compatibilidad entre crates?

Las ediciones de Rust (2015, 2018, 2021 y 2024) son configuraciones opcionales por crate en Cargo.toml que permiten a Rust introducir nuevas palabras clave o cambios de sintaxis sin romper el código existente. Las ediciones no fragmentan el ecosistema porque todas se compilan hacia la misma representación interna del compilador e interoperan sin problemas dentro de una misma compilación. [3]

## Frases citables

- Rust 1.100.0 se publicó el 12 de noviembre de 2026 y estabilizó el tipo never (!) en todas las posiciones de tipo tras 10 años y cinco intentos previos de estabilización. [4][5][7]
- En Rust 1.100.0, core::convert::Infallible se convirtió en un alias de tipo del tipo never (!), y el respaldo del tipo never cambió de () a ! en las ediciones 2015, 2018 y 2021 para igualar la edición 2024. [4][5]
- Rust 1.100.0 estabilizó std::alloc::Allocator para Box y Vec, core::mem::DropGuard, core::mem::conjure_zst, compatibilidad con Unicode 18.0.0 y la promoción a Nivel 2 de wasm32-wasip3. [4][5]
- Cargo 1.100 introdujo el lint unused_dependencies en [lints.cargo], una nueva estructura del directorio build-dir organizada por hashes y los periodos de espera de dependencias min-publish-age (RFC 3923). [4][5][6]
- La Junta Directiva de The Rust Foundation está presidida por Nell Shamrell-Harrington (Microsoft) e incluye directores miembros de Google, Arm, OpenAI, NVIDIA, Meta y la Solana Foundation junto con directores del Rust Project. [2]

## Cronología

- 2015-05-15: Se publica Rust 1.0.0, estableciendo la garantía de compatibilidad retroactiva de «estabilidad sin estancamiento» y el ciclo de lanzamientos cada seis semanas. [3]
- 2018-12: Se lanza la edición Rust 2018, que introduce el mecanismo opcional de migración entre ediciones en Cargo. [3]
- 2021-02: Se constituye The Rust Foundation como entidad gestora independiente sin fines de lucro para el lenguaje y el ecosistema Rust. [2]
- 2026-09-25: Rust 1.100.0 se ramifica desde master hacia el canal de pruebas beta. [5]
- 2026-11-12: Se publica Rust 1.100.0 en el canal estable, estabilizando el tipo never (!), std::alloc::Allocator, core::mem::DropGuard y los periodos de espera de dependencias min-publish-age de Cargo. [4][5][6]

## Fuentes

1. Rust Programming Language Official Website (Version 1.100.0). The Rust Project. https://rust-lang.org/ (consultado 2026-11-23; tier 3: official site)
2. About The Rust Foundation: Mission, 2026-2028 Strategy, and Board of Directors. The Rust Foundation. https://rustfoundation.org/about/ (consultado 2026-11-23; tier 3: official site)
3. What are Editions? - The Rust Edition Guide. The Rust Project. https://doc.rust-lang.org/edition-guide/editions/index.html (consultado 2026-11-23; tier 3: official site)
4. Announcing Rust 1.100.0. The Rust Release Team / Rust Blog. publicado 2026-11-12. https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/ (consultado 2026-11-23; tier 3: official site)
5. Rust 1.100.0 Release Notes (rust-lang/rust). GitHub / The Rust Project. publicado 2026-11-12. https://github.com/rust-lang/rust/releases/tag/1.100.0 (consultado 2026-11-23; tier 3: official site)
6. Cargo 1.100 Changelog (2026-11-12) - The Cargo Book. The Rust Project. publicado 2026-11-12. https://doc.rust-lang.org/cargo/CHANGELOG.html (consultado 2026-11-23; tier 3: official site)
7. Rust 1.100 Released With The 'Never' Type Finally Stable. Phoronix. publicado 2026-11-12. https://www.phoronix.com/news/Rust-1.100-Released (consultado 2026-11-23; tier 2: academic or news)

## Citar esta página

Mimirwiki. "Rust (lenguaje de programación)." Versión 50bb2794, 2026-11-24. https://mimirwiki.com/es/wiki/rust-programming-language
