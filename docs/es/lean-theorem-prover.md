---
title: "Lean (demostrador de teoremas)"
subtitle: "Lenguaje de programación funcional de código abierto y asistente interactivo de demostración (Lean 4)"
canonical_url: https://mimirwiki.com/es/wiki/lean-theorem-prover
language: es
page_class: entity
revision_sha256: 21e1cab7955c9aea7b097fcaece95553a79676839d5d87f2a34780fdbbe7f030
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/lean-theorem-prover.md
  txt: https://mimirwiki.com/es/wiki/lean-theorem-prover.txt
  json: https://mimirwiki.com/es/wiki/lean-theorem-prover.json
  jsonld: https://mimirwiki.com/es/wiki/lean-theorem-prover.jsonld
translations:
  en: https://mimirwiki.com/wiki/lean-theorem-prover
  ko: https://mimirwiki.com/ko/wiki/lean-theorem-prover
  ja: https://mimirwiki.com/ja/wiki/lean-theorem-prover
  zh: https://mimirwiki.com/zh/wiki/lean-theorem-prover
---

# Lean (demostrador de teoremas)

> Lean (Lean 4) es un lenguaje de programación y asistente de demostración de código abierto publicado bajo la licencia Apache-2.0 y respaldado por la Lean Focused Research Organization. Al 2026-11-24, su última versión estable es la v4.36.0 (2026-11-16) y la v4.37.0-rc1 (2026-11-18) es una versión candidata; el 2026-11-23, Google DeepMind liberó como código abierto una biblioteca de verificación de programas cuánticos, especificaciones y demostraciones en Lean 4.

Lean es un lenguaje de programación de código abierto y un asistente interactivo de demostración diseñado para escribir demostraciones matemáticas y software verificados formalmente. Su repositorio se publica bajo la licencia Apache-2.0 y su desarrollo cuenta con el apoyo de la Lean Focused Research Organization. Lean 4 tuvo su primer lanzamiento oficial (v4.0.0) el 2023-09-08. Al 2026-11-24, la última versión estable es Lean 4.36.0 (publicada el 2026-11-16), mientras que Lean 4.37.0-rc1 se publicó el 2026-11-18 como versión candidata previa al lanzamiento, seguida de una versión preliminar correspondiente de Mathlib el 2026-11-19 y la publicación por parte de Google DeepMind el 2026-11-23 de materiales de verificación de programas cuánticos en Lean 4.

**También conocido como:** Lean 4, Demostrador de teoremas Lean, Lenguaje de programación Lean

## Datos clave

- **Última versión estable:** v4.36.0 (2026-11-16) (al 2026-11-24) [5]
- **Versión candidata actual:** v4.37.0-rc1 (2026-11-18, versión preliminar) (al 2026-11-24) [6]
- **Primer lanzamiento oficial de Lean 4:** v4.0.0 (2023-09-08) [4]
- **Licencia:** Apache-2.0 [3]

## Datos básicos

- **Tipo:** Lenguaje de programación y asistente interactivo de demostración [1]
- **Organización de apoyo:** Lean Focused Research Organization (Lean FRO) [2]
- **Licencia:** Apache-2.0 [3]
- **Primer lanzamiento oficial de Lean 4:** v4.0.0 (2023-09-08) [4]
- **Última versión estable:** v4.36.0 (2026-11-16) (al 2026-11-24) [5]
- **Última versión preliminar:** v4.37.0-rc1 (2026-11-18) (al 2026-11-24) [6]
- **Biblioteca matemática principal:** Mathlib (mathlib4) [4]
- **Repositorio de código fuente:** github.com/leanprover/lean4 [3]
- **Sitio web oficial:** lean-lang.org [1]

## Descripción general y organización de Lean

Lean es un lenguaje de programación de código abierto y un asistente de demostración que permite a los usuarios escribir demostraciones matemáticas formales y software verificado.[1][3] El repositorio de Lean 4 se publica bajo la licencia Apache-2.0, y la Lean Focused Research Organization (Lean FRO) declara que apoya el crecimiento de Lean.[2][3]

Lean FRO señala que su misión es impulsar los sistemas críticos y las capacidades de Lean, y enumera áreas de enfoque que incluyen escalabilidad, usabilidad, automatización de demostraciones, documentación, una comunidad diversa y apoyo a la investigación en inteligencia artificial y a la síntesis de código verificado.[2] Entre los ejemplos de automatización integrada destacados en el sitio oficial de Lean figuran la táctica `grind` para inducción, razonamiento algebraico y razonamiento de tipo SMT, así como `bv_decide` para decidir ecuaciones sobre vectores de bits.[1] Las notas de lanzamiento de Lean 4.0.0 describen a Mathlib como la principal biblioteca matemática de Lean (`mathlib4`), y los proyectos se gestionan mediante la herramienta de compilación `lake` y el gestor de cadenas de herramientas `elan`.[4][9]

## Historial de versiones de Lean 4 y versiones de noviembre de 2026

Lean 4 alcanzó su primer lanzamiento oficial con `v4.0.0` el 2023-09-08, fecha en la que los desarrolladores anunciaron planes para publicar versiones menores con una frecuencia aproximadamente mensual.[4]

| Versión | Tipo | Fecha de lanzamiento | Notas |
| --- | --- | --- | --- |
| v4.0.0 | Estable | 2023-09-08 | Primer lanzamiento oficial de Lean 4 |
| v4.36.0 | Estable (última al 2026-11-24) | 2026-11-16 | Última etiqueta de versión estable en GitHub |
| v4.37.0-rc1 | Versión candidata (preliminar) | 2026-11-18 | 370 cambios integrados; sujeta a modificaciones antes de la versión final |

Al 2026-11-24, `v4.36.0` (publicada el 2026-11-16) es la última versión estable de Lean 4.[5] El 2026-11-18, el proyecto publicó `v4.37.0-rc1`, etiquetada explícitamente como una versión candidata y no como una versión final.[6] Sus notas de lanzamiento registran 370 cambios integrados, que incluyen 71 nuevas funcionalidades, 159 correcciones, 108 mejoras de rendimiento, 7 refactorizaciones, 4 mejoras en el conjunto de pruebas, 1 mejora de documentación y otros 20 cambios, uno de los cuales añade la opción `shiftLeft.threshold` (valor predeterminado 65536).[6] El 2026-11-19, `leanprover-community/mathlib4` etiquetó la versión preliminar `v4.37.0-rc1` para actualizar su cadena de herramientas a dicha versión candidata.[7]

## Lean en la verificación formal y la publicación de DeepMind de noviembre de 2026

Lean FRO menciona las matemáticas formales y la verificación de software y hardware entre los campos en los que se aplica Lean.[1][2] El 2026-11-23, Google DeepMind anunció la publicación en GitHub de materiales de verificación para programas cuánticos sintetizados con equipos de agentes de [Google Gemini](https://mimirwiki.com/es/wiki/google-gemini) (Gemini 4) y comprobados en Lean 4.[8][9]

El repositorio de código abierto (`google-deepmind/formal-quantum-computation`, bajo licencia Apache-2.0) se basa en la lógica cuántica de Hoare con variables clásicas y depende de `Mathlib4` y `QuantumInfo` (parte de `Physlib`).[9] Se divide en tres partes: la biblioteca principal `QuantumComputation` (circuitos, puertas, registros, lógica cuántica de Hoare y conteo de recursos), `QuantumComputationSpecs` (especificaciones formales de problemas y desafíos de referencia) y una rama `discoveries` que contiene los programas presentados y las demostraciones en Lean.[9][12]

El artículo preliminar de investigación subyacente (`arXiv:2611.09822v3`) se envió por primera vez el 2026-11-06 y se revisó el 2026-11-16; el acontecimiento noticioso del 2026-11-23 fue la publicación abierta de la biblioteca en Lean, las especificaciones y las demostraciones, cubierta ese mismo día por The Next Web y QubitWire.[8][10][11][12] Tanto DeepMind como QubitWire señalan que las reducciones de recursos comunicadas (como una reducción de 11.8x en una métrica combinada de coste de cúbits y operaciones, y 4338 frente a 5650 cúbits con corrección de errores para un cálculo de fusión por confinamiento inercial) están verificadas matemáticamente frente a especificaciones formales y modelos de coste, y no medidas en hardware cuántico físico; además, el repositorio enumera la estimación explícita del coste de la computación clásica y el flujo de control como trabajo futuro previsto.[8][9][12]

## Alcance y límites de la verificación en Lean

Según se señala en la cobertura independiente sobre la publicación del repositorio de DeepMind, una demostración verificada por máquina en Lean confirma que un programa cumple su especificación formal bajo los supuestos de coste modelados, pero no establece por sí misma que dichas especificaciones o modelos de coste reflejen todos los cuellos de botella del hardware físico ni que terceros hayan reproducido los resultados de forma independiente.[12]

## Preguntas frecuentes

### ¿Cuál es la última versión estable de Lean 4 al 2026-11-24?

Al 2026-11-24, la última versión estable de Lean 4 es v4.36.0, publicada el 2026-11-16. Lean 4.37.0-rc1, publicada el 2026-11-18, es una versión candidata (preliminar) y no una versión final. [5][6]

### ¿Qué es Mathlib en el ecosistema de Lean?

Mathlib (mathlib4) es la principal biblioteca matemática de Lean. El 2026-11-19, el repositorio de Mathlib publicó la versión preliminar v4.37.0-rc1 para actualizar su cadena de herramientas a Lean 4.37.0-rc1. [4][7]

### ¿Qué publicó Google DeepMind para Lean el 2026-11-23?

El 2026-11-23, Google DeepMind anunció la publicación abierta de su repositorio en GitHub formal-quantum-computation bajo licencia Apache-2.0, que contiene una biblioteca de programas cuánticos en Lean 4, especificaciones formales de problemas y demostraciones en Lean procedentes de su artículo preliminar de noviembre de 2026. [8][9][10]

### ¿La publicación de DeepMind en Lean demostró la ejecución en una computadora cuántica física?

No. El anuncio del 2026-11-23 correspondió a la publicación abierta de materiales de verificación en Lean, y las mejoras de recursos comunicadas provienen de especificaciones formales y modelos matemáticos de coste, no de mediciones de tiempo en hardware cuántico físico. [8][12]

## Frases citables

- Lean es un lenguaje de programación y asistente de demostración de código abierto con licencia Apache-2.0 y respaldado por la Lean Focused Research Organization. [1][2][3]
- Lean 4.0.0, el primer lanzamiento oficial de Lean 4, se publicó el 2023-09-08. [4]
- Al 2026-11-24, Lean v4.36.0 (publicada el 2026-11-16) es la última versión estable en GitHub. [5]
- Lean 4.37.0-rc1 se publicó el 2026-11-18 como versión candidata con 370 cambios integrados, y Mathlib publicó una versión preliminar v4.37.0-rc1 correspondiente el 2026-11-19. [6][7]
- El 2026-11-23, Google DeepMind liberó como código abierto su biblioteca de verificación de programas cuánticos en Lean 4, especificaciones de problemas y soluciones verificadas en google-deepmind/formal-quantum-computation. [8][9]
- El artículo preliminar complementario arXiv:2611.09822v3 se envió el 2026-11-06 y se revisó el 2026-11-16, y sus cifras de coste de circuitos derivan de modelos formales en lugar de ejecuciones en hardware cuántico físico. [10][12]

## Cronología

- 2023-09-08: Se publica Lean 4.0.0 como el primer lanzamiento oficial de Lean 4. [4]
- 2026-11-06: Los autores envían el artículo preliminar arXiv:2611.09822 sobre el descubrimiento de programas cuánticos verificados formalmente en Lean con agentes de Gemini 4 (revisado a la v3 el 2026-11-16). [10]
- 2026-11-16: Se publica Lean v4.36.0 como versión estable en GitHub. [5]
- 2026-11-18: Se publica Lean 4.37.0-rc1 como versión candidata con 370 cambios integrados. [6]
- 2026-11-19: Mathlib (mathlib4) publica la versión preliminar v4.37.0-rc1 actualizando su cadena de herramientas a Lean 4.37.0-rc1. [7]
- 2026-11-23: Google DeepMind anuncia la publicación abierta en GitHub de su biblioteca de verificación de programas cuánticos en Lean 4, especificaciones de problemas y soluciones verificadas. [8][9]

## Fuentes

1. Lean Programming Language. Lean Focused Research Organization. https://lean-lang.org/ (consultado 2026-11-24; tier 3: official site)
2. Lean Focused Research Organization. Lean Focused Research Organization. https://lean-fro.org/ (consultado 2026-11-24; tier 3: official site)
3. leanprover/lean4: Lean 4 programming language and theorem prover. Lean Focused Research Organization. https://github.com/leanprover/lean4 (consultado 2026-11-24; tier 3: official site)
4. Release v4.0.0 - leanprover/lean4. Lean Focused Research Organization. publicado 2023-09-08. https://github.com/leanprover/lean4/releases/tag/v4.0.0 (consultado 2026-11-24; tier 3: official site)
5. Release v4.36.0 - leanprover/lean4. Lean Focused Research Organization. publicado 2026-11-16. https://github.com/leanprover/lean4/releases/tag/v4.36.0 (consultado 2026-11-24; tier 3: official site)
6. Lean 4.37.0-rc1 (2026-11-18). Lean Focused Research Organization. publicado 2026-11-18. https://lean-lang.org/doc/reference/latest/releases/v4.37.0/ (consultado 2026-11-24; tier 3: official site)
7. Release v4.37.0-rc1 - leanprover-community/mathlib4. Lean Community. publicado 2026-11-19. https://github.com/leanprover-community/mathlib4/releases/tag/v4.37.0-rc1 (consultado 2026-11-24; tier 3: official site)
8. Finding faster quantum algorithms with agents and formal verification. Google DeepMind. publicado 2026-11-23. https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/ (consultado 2026-11-24; tier 3: official site)
9. google-deepmind/formal-quantum-computation. Google DeepMind. https://github.com/google-deepmind/formal-quantum-computation (consultado 2026-11-24; tier 3: official site)
10. Discovering formally verified quantum programs with AI. arXiv. publicado 2026-11-16. https://arxiv.org/abs/2611.09822v3 (consultado 2026-11-24; tier 2: academic or news)
11. DeepMind's AI agents found cheaper quantum algorithms, and proved them. The Next Web. publicado 2026-11-23. https://thenextweb.com/news/google-deepmind-gemini-agents-quantum-algorithms-lean (consultado 2026-11-24; tier 2: academic or news)
12. Google opens the proofs behind its AI-designed quantum programs. QubitWire. publicado 2026-11-23. https://qubitwire.com/articles/google-deepmind-quantum-program-proofs-public-release (consultado 2026-11-24; tier 2: academic or news)

## Citar esta página

Mimirwiki. "Lean (demostrador de teoremas)." Versión 21e1cab7, 2026-11-24. https://mimirwiki.com/es/wiki/lean-theorem-prover
