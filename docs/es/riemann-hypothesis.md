---
title: "Hipótesis de Riemann"
subtitle: "Conjetura de 1859 sobre los ceros no triviales de la función zeta de Riemann, demostrada y verificada formalmente en Lean 4 en noviembre de 2026"
canonical_url: https://mimirwiki.com/es/wiki/riemann-hypothesis
language: es
page_class: concept
revision_sha256: 4c18bca2f9717404f0d13f60f897e12fd18badf1ee2220bb8ebc46195377b03c
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 9
alternates:
  md: https://mimirwiki.com/es/wiki/riemann-hypothesis.md
  txt: https://mimirwiki.com/es/wiki/riemann-hypothesis.txt
  json: https://mimirwiki.com/es/wiki/riemann-hypothesis.json
  jsonld: https://mimirwiki.com/es/wiki/riemann-hypothesis.jsonld
translations:
  en: https://mimirwiki.com/wiki/riemann-hypothesis
  ko: https://mimirwiki.com/ko/wiki/riemann-hypothesis
  ja: https://mimirwiki.com/ja/wiki/riemann-hypothesis
  zh: https://mimirwiki.com/zh/wiki/riemann-hypothesis
---

# Hipótesis de Riemann

> El 20 de noviembre de 2026, el matemático de Anthropic Levent Alpoge publicó una demostración formal completa de la hipótesis de Riemann y la hipótesis generalizada de Riemann (GRH) para funciones L de Dirichlet en Lean 4 (17 millones de líneas, 175 187 módulos en Lean v4.33.1 y Mathlib v4.33.1), creada en seis semanas con Claude AI mediante levantamientos theta iterados en grupos unitarios definidos de longitud proporcional a sqrt(X). Los días 21 y 22 de noviembre de 2026, Lean FRO, Mathlib Initiative y el matemático del MIT Andrew Sutherland certificaron que compila sin errores, usa solo los tres axiomas estándar de Lean, coincide con el enunciado RiemannHypothesis de Mathlib y pasa núcleos independientes (nanoda, con-leche, con-ron y lean4lean), mientras que en un preimpreso sin IA de Alessandro Masullo se hallaron lagunas en ocho horas.

La hipótesis de Riemann (RH), formulada por el matemático alemán Bernhard Riemann en su artículo de noviembre de 1859 'Sobre el número de primos menores que una magnitud dada', es la conjetura fundamental de la teoría analítica de números que afirma que todo cero no trivial de la función zeta de Riemann ζ(s) se encuentra sobre la recta crítica con parte real Re(s) = 1/2. Designada en 1900 como parte del octavo problema de Hilbert y en mayo de 2000 como uno de los siete Problemas del Milenio del Instituto Clay de Matemáticas (dotado con un premio de 1 millón de dólares), rige el término de error en el teorema de los números primos y la distribución de los números primos.

**También conocido como:** RH, Hipótesis generalizada de Riemann, GRH, Octavo problema de Hilbert, Conjetura zeta de Riemann

## Datos clave

- **Formulada por:** Bernhard Riemann (1859) [1]
- **Enunciado matemático:** Todo cero no trivial de ζ(s) (y de L(χ, s) de Dirichlet bajo GRH) tiene parte real Re(s) = 1/2 [1]
- **Demostración formal del 20 de noviembre de 2026:** Levent Alpoge (Anthropic) con Claude AI: 17 millones de líneas de código Lean 4 en 175 187 módulos (al 2026-11-20) [3]
- **Verificación independiente de núcleos:** Certificada los días 21 y 22 de noviembre de 2026 por Lean FRO, Mathlib Initiative y Andrew Sutherland (MIT) (al 2026-11-22) [4]

## Datos básicos

- **Campo:** Teoría analítica de números / Formas automórficas [1]
- **Conjeturada por:** Georg Friedrich Bernhard Riemann (1826-1866) en 1859 [1]
- **Designaciones de premios:** Octavo problema de Hilbert (1900); Problema del Milenio del Instituto Clay (1 000 000 USD, anunciado el 24 de mayo de 2000) [2]
- **Autor de la resolución formal:** Levent Alpoge (en colaboración con Claude AI de Anthropic, anunciada el 20 de noviembre de 2026) [3]
- **Entorno de verificación formal:** Lean v4.33.1 / Mathlib v4.33.1 (más de 17 000 000 de líneas; 175 187 módulos; exportación bruta de 61,57 GB) [5]
- **Teoremas verificados en Main.lean:** riemannHypothesis, riemannZeta_eq_zero_re y 3 teoremas de GRH para funciones L de Dirichlet (+ desigualdades de Robin y Lagarias) [5]
- **Verificadores independientes:** Núcleo de Lean (leanchecker), nanoda (Rust), con-leche, con-ron (Rust), lean4lean [4]

## Formulación matemática y distribución de los números primos

La **función zeta de Riemann** $\zeta(s)$ se define para números complejos $s = \sigma + it$ con parte real $\text{Re}(s) = \sigma > 1$ mediante la serie de Dirichlet convergente y el producto de Euler sobre todos los números primos $p$:[1] $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}}$$ En su artículo de 1859 presentado ante la Academia de Ciencias de Berlín, **Georg Friedrich Bernhard Riemann** (1826-1866) extendió $\zeta(s)$ por prolongación analítica a una función meromorfa en todo el plano complejo $\mathbb{C}$ con un único polo simple en $s = 1$, satisfaciendo una ecuación funcional simétrica que relaciona $\zeta(s)$ y $\zeta(1-s)$.[1]

Debido a los factores gamma de la ecuación funcional, $\zeta(s)$ se anula en los enteros pares negativos $s = -2, -4, -6, \dots$, conocidos como los **ceros triviales**.[1][5] Todos los demás ceros, llamados **ceros no triviales**, se sitúan dentro de la banda crítica $0 < \text{Re}(s) < 1$.[1][5] La **hipótesis de Riemann (RH)** afirma que todo cero no trivial de $\zeta(s)$ se encuentra sobre la **recta crítica** vertical $\text{Re}(s) = 1/2$.[1] De forma equivalente, en términos de la función contadora de números primos $\pi(x)$ y la integral logarítmica $\text{Li}(x)$, la hipótesis de Riemann proporciona la cota óptima de error de raíz cuadrada $\pi(x) = \text{Li}(x) + O(\sqrt{x} \log x)$.[1][3]

David Hilbert incluyó la hipótesis de Riemann como el octavo de sus 23 problemas en el Congreso Internacional de Matemáticos de París el 9 de agosto de 1900, y el **24 de mayo de 2000**, el **Instituto Clay de Matemáticas (CMI)** la designó uno de los siete **Problemas del Milenio**, asignando un premio de 1 millón de dólares a una demostración verificada.[1][2] Antes de noviembre de 2026, los cálculos numéricos habían comprobado que los primeros $10^{13}$ (10 billones) de ceros no triviales yacen sobre la recta crítica, mientras que la **hipótesis generalizada de Riemann (GRH)** extendió la conjetura a todas las funciones $L$ de Dirichlet $L(\chi, s)$.[1][5]

## Demostración del 20 de noviembre de 2026 por Levent Alpoge y Claude

El **20 de noviembre de 2026**, un día después de que su empleador Anthropic completara su oferta pública inicial en el Nasdaq, el matemático **Levent Alpoge** publicó una nota explicativa de 4 páginas (`alpo.ge/remark.pdf`) junto con un archivo comprimido en 14 partes (`lean.tar.gz.part01` a `part14`) que contiene una formalización completa y libre de supuestos en el asistente de demostración **Lean 4** tanto de la **hipótesis de Riemann** como de la **hipótesis generalizada de Riemann (GRH)** para funciones $L$ de Dirichlet.[3][4][8]

Según la cronología de Alpoge, la demostración se desarrolló durante un periodo intensivo de seis semanas entre el **6 de octubre y el 16 de noviembre de 2026** en estrecha colaboración con **Claude**, la inteligencia artificial de Anthropic.[3][8] Al reconocer que traducir el argumento sin simplificar a un artículo en prosa generaría más de 250 000 páginas de texto ilegible, Alpoge optó por publicar la base de código completa en Lean verificable por máquina, compuesta por **17 millones de líneas de código** repartidas en **175 187 módulos de Lean**.[3][4][5]

En el plano matemático, Alpoge y Claude construyeron un análogo nativo para cuerpos numéricos del **método del polinomio auxiliar de Stepanov**, que emplea multiplicidad de divisores de orden alto para demostrar la hipótesis de Riemann sobre cuerpos de funciones:[3] - Dado que la multiplicidad de derivadas de orden superior es difícil de construir directamente sobre los enteros $\mathbb{Z}$, la demostración combina una identidad de Parseval / cuádrica de signo definido ($qN = M_k + R$) y la fórmula explícita de Guinand-Weil con **levantamientos theta iterados** $U(X_0) \to U(X_1) \to \dots \to U(X_m)$ entre grupos unitarios totalmente definidos (y grupos ortogonales $O(2, n)$).[3] - Cada levantamiento theta imita un orden de multiplicidad de Stepanov. En lo que Alpoge destacó como el avance decisivo sugerido por Claude, para una suma de von Mangoldt $\sum_{n \le X} \Lambda(n)$ de longitud $X$, la demostración encadena una torre de levantamientos theta de longitud **$m \approx \sqrt{X}$**, controlando normas, niveles y divisibilidad mediante la **fórmula de Chowla-Selberg**, la **fórmula de masa de Siegel**, las **identidades de producto interno de Rallis y de balancín (seesaw)**, la **desigualdad de pendiente de Bost** y una construcción de **torre de Iwasawa** que utiliza la fórmula de trazas de Behrend y representaciones de Galois asociadas a representaciones automórficas cuspidales polarizadas algebraicas regulares de $\text{GL}_n$ sobre cuerpos CM.[3][9]

## Certificación independiente por Lean FRO, Mathlib y el MIT

Debido a que las bases de código matemáticas asistidas por IA requieren una auditoría rigurosa para asegurar que el enunciado formalizado del teorema no haya sido alterado ni trivializado y que no se hayan introducido axiomas personalizados ni vulnerabilidades del compilador (un protocolo de cuatro partes descrito por el matemático del Imperial College London **Kevin Buzzard** en el blog del proyecto Xena el 12 de noviembre de 2026[7]), la comunidad de verificación formal auditó de inmediato el repositorio de Alpoge.[4][5]

El **21 de noviembre de 2026**, la **Lean Focused Research Organization (Lean FRO)** y la **Mathlib Initiative** emitieron un comunicado conjunto en el que certificaron que la demostración de Alpoge de la hipótesis de Riemann es completamente válida y cumple los cuatro criterios de verificación.[4] De forma paralela, el matemático del MIT **Andrew Sutherland** publicó un panel de verificación exhaustivo (`math.mit.edu/~drew/grh/`) que documenta las comprobaciones reproducibles completadas en **Lean v4.33.1** y **Mathlib v4.33.1**:[5]

| Criterio de verificación | Resultado observado de la auditoría (al 22 de noviembre de 2026) |
| --- | --- |
| **1. Compilación y reproducibilidad** | Los **175 187 módulos** compilaron con cero errores en un entorno aislado, sin red y de solo lectura (`lake build Main`), reproduciendo la exportación bruta exacta de **61 570 595 788 bytes** (61,57 GB) (`sha256: 5ea74b91...244e`).[4][5] |
| **2. Auditoría de axiomas e higiene** | `#print axioms` confirmó que los cinco teoremas principales dependen **únicamente** de los tres axiomas fundacionales estándar de Lean (`propext`, `Classical.choice` y `Quot.sound`), sin axiomas definidos por el usuario y con cachés `.olean` de Mathlib sin modificar byte a byte (8 322 archivos).[5] |
| **3. Coincidencia exacta del enunciado** | Herramientas comparadoras independientes (`con-leche --compare` y su adaptación a Rust `con-ron --compare`, verificando 1 468 418 declaraciones de la solución frente a 51 692 declaraciones de referencia) confirmaron que `Main.lean` demuestra la definición exacta de `RiemannHypothesis` en Mathlib (`∀ (s : ℂ) (_ : riemannZeta s = 0) (_ : ¬∃ n : ℕ, s = -2 * (n + 1)) (_ : s ≠ 1), s.re = 1 / 2`) más la **GRH para todas las funciones L de Dirichlet** (`LFunction_ne_zero_of_half_lt_re`, `LFunction_eq_zero_re`, `LFunction_eq_zero_re_of_isPrimitive`).[4][5] |
| **4. Verificación con múltiples núcleos** | Todos los módulos superaron `leanchecker` y `lean4lean` (verificado en Lean), y la exportación inerte completa de 61,57 GB fue aceptada de forma independiente por el núcleo en Rust **`nanoda`** (en 27 m 42 s con 80 hilos) y por los verificadores de teoría de conjuntos formalmente verificados **`con-leche`** (3 m 15 s con 64 hilos) y **`con-ron`** (7 m 06 s con 64 hilos).[4][5] |

Como comprobación adicional totalmente independiente de la definición analítica de $\zeta(s)$ en Mathlib, Sutherland combinó la demostración de Alpoge con una formalización independiente de la **desigualdad de Robin** ($\sigma(n) < e^{\gamma} n \log \log n$ para todo $n > 5040$) y la **desigualdad de Lagarias** ($\sigma(n) \le H_n + e^{H_n} \log H_n$ para todo $n > 0$), obteniendo demostraciones elementales incondicionales de ambas desigualdades de suma de divisores.[5]

## Preimpreso humano coincidente e impacto en las matemáticas

El mismo día de la publicación de Alpoge (**20 de noviembre de 2026**), el matemático de la Universidad de Stanford **Ravi Vakil** difundió un borrador independiente, redactado íntegramente por un humano, que proponía una demostración de la hipótesis generalizada de Riemann obra del matemático italiano **Alessandro Maria Masullo**, quien había trabajado en el problema durante 12 años sin IA y revisaba el manuscrito con el profesor de Stanford Brian Conrad.[6][8][9] Dado que el anuncio de Alpoge hacía inviable esperar otro año para completar las revisiones, Vakil compartió el borrador de Masullo a mitad del proceso; sin embargo, en un plazo de ocho horas, Vakil actualizó su publicación para informar de que varios matemáticos (asistidos por herramientas de verificación con IA) habían identificado lagunas no resueltas en el manuscrito de Masullo.[6]

En contraste, dado que la demostración en Lean de 17 millones de líneas de Alpoge ha superado la verificación formal con múltiples núcleos, el foco matemático se ha desplazado de debatir si la hipótesis de Riemann y la GRH de Dirichlet son ciertas a extraer simplificaciones conceptuales comprensibles para humanos a partir de la demostración de levantamiento automórfico verificada por máquina.[3][4][9] Cabe señalar que, al 22 de noviembre de 2026, el alcance formal verificado abarca la función zeta de Riemann clásica $\zeta(s)$ y las **funciones $L$ de Dirichlet** para todos los módulos y caracteres, mientras que las funciones zeta de Dedekind, las funciones $L$ de Hecke generales y las funciones $L$ automórficas arbitrarias de rango superior no figuraban entre los enunciados formales comprobados en `Main.lean`.[5]

## Preguntas frecuentes

### ¿Ha sido demostrada y verificada la hipótesis de Riemann?

Sí. El 20 de noviembre de 2026, el matemático Levent Alpoge (trabajando con Claude AI de Anthropic) publicó una demostración formal de 17 millones de líneas de la hipótesis de Riemann y la hipótesis generalizada de Riemann para funciones L de Dirichlet en el asistente de demostración Lean 4. Los días 21 y 22 de noviembre de 2026, la Lean Focused Research Organization (FRO), la Mathlib Initiative y el matemático del MIT Andrew Sutherland certificaron que la demostración compila sin errores, utiliza únicamente los axiomas estándar, coincide con el enunciado oficial de Mathlib y supera múltiples núcleos de verificación independientes. [3][4][5]

### ¿Qué afirma la hipótesis de Riemann?

Formulada por Bernhard Riemann en 1859, la hipótesis de Riemann afirma que todo cero no trivial de la función zeta de Riemann ζ(s), es decir, toda solución de ζ(s) = 0 distinta de los enteros pares negativos -2, -4, -6 y sucesivos, es un número complejo cuya parte real es exactamente igual a 1/2. [1][5]

### ¿Qué método matemático utilizaron Levent Alpoge y Claude para demostrar la hipótesis de Riemann?

La demostración adapta el argumento de multiplicidad en cuerpos de funciones de Stepanov a los enteros combinando una identidad de Parseval de cuádrica de signo definido y la fórmula explícita de Guinand-Weil con una cadena iterada de levantamientos theta entre grupos unitarios totalmente definidos de longitud proporcional a sqrt(X), controlada mediante la fórmula de Chowla-Selberg, la fórmula de masa de Siegel, las identidades de balancín (seesaw) de Rallis, la desigualdad de pendiente de Bost y una construcción de torre de Iwasawa. [3][9]

### ¿Cómo verificaron los matemáticos que una demostración asistida por IA de 17 millones de líneas no contiene errores ocultos ni trucos?

Siguiendo el protocolo de verificación en Lean de cuatro pasos, los auditores recompilaron los 175 187 módulos en un entorno aislado sin conexión para producir una exportación inerte de 61,57 GB, comprobaron que solo se usaron los tres axiomas estándar de Lean (propext, Classical.choice, Quot.sound), cotejaron los teoremas demostrados con la definición sin modificar de RiemannHypothesis en Mathlib y verificaron la exportación bruta con comprobadores independientes escritos en distintos lenguajes (entre ellos nanoda, con-leche, con-ron y lean4lean), además de derivar las desigualdades elementales de suma de divisores de Robin y Lagarias. [4][5][7]

### ¿Qué ocurrió con el intento independiente de demostración humana de Alessandro Masullo en noviembre de 2026?

El 20 de noviembre de 2026, el profesor de Stanford Ravi Vakil publicó un manuscrito a mitad de revisión de un intento de demostración de la GRH sin IA obra de Alessandro Maria Masullo. En un plazo de ocho horas desde su publicación, matemáticos apoyados en herramientas de análisis con IA identificaron lagunas en el borrador de Masullo que siguen sin resolverse, mientras que la formalización en Lean 4 de Alpoge superó la certificación completa por núcleos. [4][6][9]

## Frases citables

- Formulada en 1859 por Bernhard Riemann y designada en 2000 como un Problema del Milenio del Instituto Clay de Matemáticas dotado con 1 millón de dólares, la hipótesis de Riemann afirma que todos los ceros no triviales de la función zeta de Riemann tienen parte real 1/2. [1][2]
- El 20 de noviembre de 2026, Levent Alpoge publicó una formalización en Lean 4 de 17 millones de líneas (175 187 módulos) que demuestra la hipótesis de Riemann y la hipótesis generalizada de Riemann para funciones L de Dirichlet, desarrollada con Claude AI de Anthropic. [3][4][5]
- El 21 de noviembre de 2026, Lean FRO y la Mathlib Initiative certificaron que la demostración de Alpoge de la hipótesis de Riemann es válida, compila sin errores frente a Mathlib, demuestra el enunciado exacto de Mathlib y supera verificadores independientes como con-leche y con-ron. [4]
- El matemático del MIT Andrew Sutherland verificó que los 175 187 módulos de Lean v4.33.1 de Alpoge reproducen una exportación de 61 570 595 788 bytes usando solo los tres axiomas estándar (propext, Classical.choice, Quot.sound), aceptada por nanoda, con-leche, con-ron, leanchecker y lean4lean, e implican incondicionalmente las desigualdades de suma de divisores de Robin y Lagarias. [5]
- Un manuscrito independiente sin IA sobre la GRH de Alessandro Maria Masullo publicado por Ravi Vakil el 20 de noviembre de 2026 presentó problemas matemáticos identificados por los revisores en un plazo de ocho horas. [6][9]

## Cronología

- 1859-11: Bernhard Riemann publica 'Sobre el número de primos menores que una magnitud dada', formulando la hipótesis de Riemann. [1]
- 1900-08-09: David Hilbert incluye la hipótesis de Riemann como el problema 8 en su discurso ante el Congreso Internacional de Matemáticos en París. [2]
- 2000-05-24: El Instituto Clay de Matemáticas designa la hipótesis de Riemann como uno de los siete Problemas del Milenio en París, dotados con 1 millón de dólares. [1][2]
- 2026-10-06: Levent Alpoge inicia un periodo intensivo de seis semanas de formalización y descubrimiento de demostraciones con Claude AI de Anthropic, partiendo de determinantes de Stepanov y la desigualdad de pendiente de Bost. [3]
- 2026-11-16: Alpoge y Claude completan la formalización en Lean 4 de la hipótesis generalizada de Riemann para funciones L de Dirichlet mediante levantamientos theta iterados de longitud sqrt(X). [3]
- 2026-11-20: Alpoge publica remark.pdf y el archivo de la demostración en Lean 4 de 17 millones de líneas; Ravi Vakil difunde por separado el borrador humano de Alessandro Masullo, en el que se hallan lagunas en ocho horas. [3][6][9]
- 2026-11-21: Lean FRO, la Mathlib Initiative y Andrew Sutherland (MIT) certifican de forma independiente la validez de la demostración en Lean 4 de Alpoge mediante múltiples núcleos de verificación. [4][5][8]

## Fuentes

1. Riemann Hypothesis - Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium/riemann-hypothesis/ (consultado 2026-11-23; tier 2: academic or news)
2. The Millennium Prize Problems. Clay Mathematics Institute. https://www.claymath.org/millennium-problems/ (consultado 2026-11-23; tier 2: academic or news)
3. Remark on a Proof and Lean Formalization of the Riemann Hypothesis and Generalized Riemann Hypothesis. Levent Alpoge (alpo.ge). publicado 2026-11-20. https://alpo.ge/remark.pdf (consultado 2026-11-23; tier 3: official site)
4. Lean Verification of the Riemann Hypothesis: Joint Statement by the Lean FRO and the Mathlib Initiative. Lean Focused Research Organization & Mathlib Initiative. publicado 2026-11-21. https://leanprover-community.github.io/blog/posts/riemann-hypothesis/ (consultado 2026-11-23; tier 3: official site)
5. RH Lean Proof: Verification Files and Independent Kernel Audit. Andrew Sutherland (Massachusetts Institute of Technology). publicado 2026-11-22. https://math.mit.edu/~drew/grh/ (consultado 2026-11-23; tier 2: academic or news)
6. Hurried Announcement: Alessandro Masullo GRH (with Nov 20-22 Updates). Ravi Vakil (Stanford University / Math 216 Blog). publicado 2026-11-20. https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/ (consultado 2026-11-23; tier 2: academic or news)
7. '...and the proof is checked in Lean' (Four Criteria for Verifying AI-Generated Lean Proofs). Kevin Buzzard (Xena Project). publicado 2026-11-12. https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/ (consultado 2026-11-23; tier 2: academic or news)
8. Two groups verify mathematician's claim that Claude helped prove mathematics problem. The Guardian. publicado 2026-11-21. https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai (consultado 2026-11-23; tier 2: academic or news)
9. AI claimed a solution to the 167-year-old Riemann hypothesis - and a human did, too. TechCrunch. publicado 2026-11-20. https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/ (consultado 2026-11-23; tier 2: academic or news)

## Citar esta página

Mimirwiki. "Hipótesis de Riemann." Versión 4c18bca2, 2026-11-24. https://mimirwiki.com/es/wiki/riemann-hypothesis
