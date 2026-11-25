---
title: "Java4Shell (CVE-2026-114938)"
subtitle: "Desbordamiento crítico de búfer en el montón en el intrínseco decodificador Base64 AVX-512 VBMI x86-64 del compilador JIT C2 de OpenJDK HotSpot"
canonical_url: https://mimirwiki.com/es/wiki/java4shell
language: es
page_class: concept
revision_sha256: e2fbc4cd75d6392c448bd69e91f46ed7a7ab28301c96e3c37b6b8d39dd864c3c
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 7
alternates:
  md: https://mimirwiki.com/es/wiki/java4shell.md
  txt: https://mimirwiki.com/es/wiki/java4shell.txt
  json: https://mimirwiki.com/es/wiki/java4shell.json
  jsonld: https://mimirwiki.com/es/wiki/java4shell.jsonld
translations:
  en: https://mimirwiki.com/wiki/java4shell
  ko: https://mimirwiki.com/ko/wiki/java4shell
  ja: https://mimirwiki.com/ja/wiki/java4shell
  zh: https://mimirwiki.com/zh/wiki/java4shell
---

# Java4Shell (CVE-2026-114938)

> Reportada a Oracle por Quang Luong de Calif.io (quien analizó el fallo con 'centaur hacking' asistido por IA) y Albert Yang, con CVSS v4.0 9.2 (Crítica) y CVSS v3.1 8.1 (Alta), CVE-2026-114938 ocurre cuando el intrínseco C2 JIT AVX-512 de decodificación Base64 halla un byte de relleno '=' inesperado en un bloque SIMD de 64 bytes, subdesbordando la longitud restante a -1 y generando una máscara de escritura de 64 bits de todos unos (0xFFFFFFFFFFFFFFFF) para evmovdqub (VMOVDQU8). Con una entrada de 65 caracteres ('A' * 64 + '='), escribe 64 bytes desde el desplazamiento 48 de un búfer de 50 bytes (un desbordamiento de montón de 62 bytes tras el fin del arreglo). Afecta a OpenJDK y Oracle Java SE 17.0.6+, 21, 25 y 27 (y Oracle GraalVM 8u511b33-perf) en CPU Intel Ice Lake+ y AMD Zen 4+; se corrige en OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3 y 27.0.1.0.3.

Java4Shell (identificada como CVE-2026-114938) es una vulnerabilidad crítica de desbordamiento de búfer basado en el montón en el intrínseco del compilador Just-In-Time (JIT) C2 de la máquina virtual OpenJDK HotSpot para java.util.Base64.Decoder en procesadores x86-64 compatibles con el conjunto de instrucciones AVX-512 VBMI. Divulgada el 17 de noviembre de 2026 mediante un aviso de vulnerabilidad fuera de ciclo de OpenJDK y una actualización crítica de parches de seguridad de Oracle, el fallo permite a atacantes remotos no autenticados corromper objetos adyacentes en el montón de Java, lo que puede provocar denegación de servicio (DoS), omisión de autenticación o ejecución remota de código (RCE) previa a la autenticación, enviando una carga útil Base64 especialmente manipulada con un carácter de relleno ('=') mal ubicado.

**También conocido como:** CVE-2026-114938, Java4Shell, Desbordamiento de montón Base64 AVX-512 en OpenJDK, RHSB-2026-018

## Datos clave

- **Identificador CVE y puntuaciones:** CVE-2026-114938 (CVSS v4.0: 9.2 Crítica / CVSS v3.1: 8.1 Alta) (al 2026-11-17) [3]
- **Componente afectado:** Intrínseco x86-64 AVX-512 VBMI de Base64.Decoder en el compilador JIT C2 de OpenJDK HotSpot VM [1]
- **Requisito de hardware:** CPU x86-64 con AVX-512 VBMI (Intel Ice Lake+ / AMD Zen 4+); ARM64 no se ve afectada [4]
- **Versiones corregidas de OpenJDK:** 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3 y 27.0.1.0.3 (publicadas el 17 de noviembre de 2026) (al 2026-11-17) [1]

## Datos básicos

- **ID de CVE:** CVE-2026-114938 [3]
- **Nombre común:** Java4Shell [4]
- **Fecha de divulgación:** 17 de noviembre de 2026 [1]
- **Descubridores:** Quang Luong (Calif.io) y Albert Yang (acreditados por Oracle) [2]
- **Gravedad CVSS:** CVSS v4.0: 9.2 (Crítica) / CVSS v3.1: 8.1 (Alta) [3]
- **Tipo de debilidad:** CWE-122 (Desbordamiento de búfer basado en el montón) / Subdesbordamiento entero en máscara de escritura SIMD [3]
- **Versiones de Java afectadas:** OpenJDK / Oracle JDK 17 (desde 17.0.6), 21, 25, 27; Oracle JDK 8u511b33-perf [2]
- **Mitigación mediante opciones de JVM:** -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics (o -XX:UseAVX=2) [5]

## Descripción general y descubrimiento mediante 'centaur hacking'

**Java4Shell** (`CVE-2026-114938`) es una vulnerabilidad crítica de seguridad de memoria en la rutina de decodificación Base64 acelerada por hardware de la máquina virtual Java (JVM).[1][3][4] Dado que Java es un lenguaje con seguridad de memoria y recolección de basura, los desarrolladores de aplicaciones suelen pasar encabezados HTTP no confiables (como `Authorization: Basic` o tokens JWT `Bearer`), cookies, aserciones SAML y campos JSON directamente a `java.util.Base64.getDecoder().decode()` antes de realizar la autenticación o la validación de esquemas.[4][5] Sin embargo, cuando el compilador Just-In-Time (JIT) C2 de HotSpot compila un método Java de ejecución frecuente, la JVM sustituye la implementación en bytecode de `Base64.Decoder.decodeBlock` por intrínsecos en lenguaje ensamblador escritos a mano y adaptados a la arquitectura del procesador anfitrión.[1][4]

En su aviso de actualización crítica de parches de seguridad (CSPU) de noviembre de 2026, Oracle acredita a **Quang Luong de Calif.io** y a **Albert Yang** por reportar `CVE-2026-114938`, vulnerabilidad coordinada con Oracle y el OpenJDK Vulnerability Group para su divulgación pública el **17 de noviembre de 2026**.[1][2][4][7] En la divulgación técnica de Calif.io, Luong detalló haber encontrado el fallo mediante un flujo de trabajo al que denominó **'centaur hacking'**, combinando hipótesis humanas de ingeniería inversa con agentes basados en grandes modelos de lenguaje para auditar los complejos generadores manuales de stubs en ensamblador SIMD x86-64 dentro de `stubGenerator_x86_64.cpp` de OpenJDK.[4]

## Mecanismo técnico: subdesbordamiento de máscara en AVX-512 VBMI

La causa raíz de `CVE-2026-114938` reside en la ruta rápida x86-64 **AVX-512 VBMI** (Vector Byte Manipulation Instructions) dentro del intrínseco decodificador Base64 (`decodeBlock`) del compilador JIT C2 de OpenJDK.[1][4] En la decodificación Base64 estándar, cada 4 bytes ASCII codificados producen 3 bytes decodificados de salida, por lo que un registro AVX-512 (`ZMM`) de 64 bytes de entrada Base64 produce hasta 48 bytes de salida decodificada.[4] Cuando el intrínseco encuentra un carácter no perteneciente a Base64 o un carácter de relleno `'='` (`0x3d`) dentro de un bloque SIMD de 64 bytes, debe salir del bucle vectorizado y delegar los bytes finales restantes al bucle escalar de Java.[4]

Sin embargo, debido a un error de cálculo de longitud con signo y sin signo al calcular el valor restante `output_len` para la instrucción final de almacenamiento SIMD enmascarado `evmovdqub` (`VMOVDQU8` con registro de máscara de escritura `k`), un carácter `'='` mal ubicado en desplazamientos específicos provoca que el conteo de bytes restantes sufra un subdesbordamiento a `-1` (`0xFFFFFFFFFFFFFFFF` en complemento a dos de 64 bits).[4] Cuando ese valor se desplaza o carga en el registro de máscara de operación AVX-512 de 64 bits, la máscara queda compuesta por todos unos (`-1u64`), ordenando a la instrucción `evmovdqub` del procesador escribir **64 bytes** completos de datos del registro en el arreglo Java `byte[]` de destino.[4]

Calif.io demostró dos detonantes mínimos deterministas según el umbral del intrínseco de cada versión del JDK:[4] - **OpenJDK 21, 25 y 27**: Al decodificar la cadena de 65 bytes `'A' * 64 + '='`, se reserva un arreglo `byte[]` de destino de 50 bytes (que ocupa un objeto de 72 bytes alineado a 8 bytes en el montón de HotSpot, incluido el encabezado de objeto de arreglo de 16 bytes). Después de que los primeros 64 caracteres se decodifican en 48 bytes, la instrucción enmascarada `evmovdqub` escribe 64 bytes a partir del desplazamiento 48 del búfer de carga útil de 50 bytes (con los bytes 48..63 de la escritura iguales a `0x9a`), **desbordando 62 bytes más allá del final del arreglo hacia el encabezado y los campos del objeto inmediatamente adyacente en el montón de Java**.[4] - **OpenJDK 17 (17.0.6 hasta 17.0.21)**: Debido a una comprobación de tamaño mínimo de búfer mayor antes de entrar en el bucle AVX-512 en JDK 17, el detonante mínimo es la cadena de 129 bytes `'A' * 128 + '='`.[4]

## Versiones de Java afectadas, arquitecturas de CPU e impacto empresarial

La explotación de `CVE-2026-114938` requiere dos condiciones simultáneas: una compilación afectada de la JVM y un procesador x86-64 compatible con **AVX-512 VBMI**:[1][2][4]

| Dimensión | Configuraciones vulnerables | Configuraciones no afectadas |
| --- | --- | --- |
| **Versiones de Java / OpenJDK** | OpenJDK y Oracle Java SE **17.0.6 - 17.0.21**, **21.0.0 - 21.0.13**, **25.0.0 - 25.0.5**, **27.0.0 - 27.0.1**; Oracle GraalVM / JDK **8u511b33-perf** [1][2] | OpenJDK 8 y OpenJDK 11 estándar (carecen del intrínseco Base64 AVX-512 VBMI); OpenJDK 17.0.1 - 17.0.5 [1][4][5] |
| **Arquitecturas de CPU** | **x86-64 con AVX-512 VBMI**: Intel Ice Lake, Tiger Lake, Sapphire Rapids, Emerald Rapids, Granite Rapids; AMD Zen 4 (EPYC Genoa/Bergamo) y Zen 5 (EPYC Turin) [4][5] | **ARM64 / AArch64** (AWS Graviton, Apple Silicon, Ampere); CPU x86-64 más antiguas sin AVX-512 VBMI (p. ej., Intel Skylake-SP, AMD Zen 2/Zen 3) [4][5] |

Dado que el desbordamiento de montón de 62 bytes sobrescribe la palabra de marca (mark word), el puntero comprimido de clase (`_klass`), el campo de longitud de arreglo o los campos booleanos y de referencia del siguiente objeto en el búfer de asignación local por hilo (Thread-Local Allocation Buffer, TLAB), un atacante puede corromper tokens de seguridad adyacentes o inflar el campo de longitud de un arreglo `byte[]` adyacente para construir primitivas arbitrarias de lectura y escritura dentro del proceso de la JVM.[4] Calif.io y proveedores empresariales demostraron o confirmaron impacto previo a la autenticación en middleware y aplicaciones Java de amplio uso, entre ellos **Keycloak**, **Atlassian Jira y Confluence**, **JFrog Artifactory**, **Jenkins** y **PingFederate**.[4][7]

## Versiones corregidas, mitigaciones mediante opciones de JVM y guía de CISA

El 17 de noviembre de 2026, el Proyecto OpenJDK, Oracle, Red Hat (`RHSB-2026-018`), Amazon Corretto, Eclipse Temurin y Azul publicaron compilaciones de emergencia fuera de ciclo que deshabilitan o corrigen los límites de la generación defectuosa de la máscara AVX-512 VBMI:[1][2][5] - **OpenJDK 17.0.21.0.3** - **OpenJDK 21.0.13.0.3** - **OpenJDK 25.0.5.0.3** - **OpenJDK 27.0.1.0.3**

**Mitigaciones mediante línea de comandos de la JVM**: Para sistemas en producción que no puedan actualizar de inmediato el binario del JDK, los administradores pueden deshabilitar el intrínseco C2 de Base64 o restringir la ejecución de AVX-512 añadiendo una de las siguientes opciones a `JAVA_OPTS` y reiniciando la JVM:[4][5] ```text -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics ``` o, alternativamente, limitar el nivel de AVX por debajo de AVX-512: ```text -XX:UseAVX=2 ```

**Alerta de CISA y mitigaciones perimetrales**: El 17 de noviembre de 2026, la Agencia de Ciberseguridad y Seguridad de las Infraestructuras de Estados Unidos (CISA), con aportaciones del Centro Canadiense de Ciberseguridad, emitió una alerta en la que instó a las organizaciones a inventariar los JDK y entornos de ejecución de Java (incluidos los empaquetados en aplicaciones de terceros, imágenes de contenedores y dispositivos) y priorizar el parcheo de los sistemas expuestos a Internet.[6] Cuando no sea viable aplicar parches de forma inmediata, CISA recomienda controles compensatorios temporales como restringir y validar la entrada Base64 en el límite de la aplicación, aplicar límites al tamaño de entrada y restringir el acceso no autenticado, mientras se supervisan entornos de ejecución no autorizados, cierres inesperados de la JVM y procesos Java sospechosos.[6]

## Preguntas frecuentes

### ¿Qué es Java4Shell (CVE-2026-114938)?

Java4Shell (CVE-2026-114938) es una vulnerabilidad crítica de desbordamiento de búfer en el montón (CVSS v4.0 9.2 / CVSS v3.1 8.1) en el intrínseco x86-64 AVX-512 VBMI del compilador JIT C2 de OpenJDK HotSpot para java.util.Base64.Decoder. Divulgada el 17 de noviembre de 2026, permite a atacantes remotos corromper objetos adyacentes en el montón de Java mediante el envío de cadenas Base64 malformadas con caracteres de relleno '=' mal ubicados. [1][3][4]

### ¿Qué versiones de Java y procesadores son vulnerables a CVE-2026-114938?

El fallo afecta a OpenJDK y Oracle Java SE 17 (versiones 17.0.6 hasta 17.0.21), 21 (hasta 21.0.13), 25 (hasta 25.0.5) y 27 (hasta 27.0.1), así como a Oracle JDK 8u511b33-perf, pero únicamente cuando se ejecutan en CPU x86-64 compatibles con AVX-512 VBMI (como Intel Ice Lake y posteriores o AMD Zen 4 y posteriores). Los servidores ARM64 y las compilaciones estándar de OpenJDK 8 y 11 no se ven afectados. [1][2][4][5]

### ¿Cómo provoca una cadena Base64 de 65 bytes un desbordamiento de búfer en el montón en Java?

Cuando el intrínseco decodeBlock Base64 AVX-512 VBMI procesa un bloque SIMD de 64 bytes (que se decodifica en 48 bytes de salida) y luego encuentra un byte de relleno '=' inesperado (como 'A' repetida 64 veces seguida de '='), un cálculo de longitud sufre un subdesbordamiento a -1. Esto convierte la máscara de escritura AVX-512 de 64 bits en todos unos (0xFFFFFFFFFFFFFFFF), lo que hace que la instrucción evmovdqub escriba 64 bytes desde el desplazamiento 48 de un búfer de 50 bytes y sobrescriba 62 bytes más allá del final del arreglo en el objeto adyacente del montón de Java. [4]

### ¿Qué versiones corregidas de OpenJDK solucionan Java4Shell?

La vulnerabilidad se corrige en las versiones fuera de ciclo de OpenJDK del 17 de noviembre de 2026: 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3 y 27.0.1.0.3, así como en la actualización crítica de parches de seguridad de Oracle de noviembre de 2026 y en las compilaciones correspondientes de OpenJDK de Red Hat. [1][2][5]

### ¿Cómo se puede mitigar CVE-2026-114938 mediante opciones de la JVM sin actualizar Java?

Los administradores pueden deshabilitar por completo el intrínseco en ensamblador vulnerable pasando '-XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics' (o '-XX:UseAVX=2') a los argumentos de inicio de la JVM y reiniciando el proceso Java. [4][5]

## Frases citables

- CVE-2026-114938 (Java4Shell) fue divulgada el 17 de noviembre de 2026 con una puntuación CVSS v4.0 de 9.2 (Crítica) y una puntuación CVSS v3.1 de 8.1 (Alta). [1][2][3]
- CVE-2026-114938 se debe a un subdesbordamiento entero a -1 en la máscara de escritura AVX-512 VBMI de la instrucción evmovdqub dentro del intrínseco Base64.Decoder del compilador JIT C2 de OpenJDK, lo que produce una escritura de 64 bytes desde el desplazamiento 48 de un búfer de 50 bytes (un desbordamiento de montón de 62 bytes). [4]
- El aviso de actualización crítica de parches de seguridad de Oracle de noviembre de 2026 acredita a Quang Luong de Calif.io y a Albert Yang por reportar CVE-2026-114938, que afecta a OpenJDK 17.0.6+, 21, 25 y 27 en CPU x86-64 compatibles con AVX-512 VBMI, mientras que ARM64 y OpenJDK 8/11 estándar no se ven afectados. [1][2][4][5][7]
- OpenJDK corrigió CVE-2026-114938 en las versiones de emergencia 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3 y 27.0.1.0.3, y puede mitigarse mediante -XX:+UnlockDiagnosticVMOptions -XX:-UseBASE64Intrinsics. [1][5]

## Cronología

- 2023-01: OpenJDK 17.0.6 incorpora por retroportación el intrínseco JIT C2 decodificador Base64 AVX-512 VBMI que contiene el error latente de subdesbordamiento de máscara. [1][4]
- 2026-11-17: OpenJDK publica el aviso de vulnerabilidad 2026/11/17, Oracle lanza una actualización crítica de parches de seguridad fuera de ciclo y CISA emite una alerta instando al parcheo inmediato de CVE-2026-114938; se publican OpenJDK 17.0.21.0.3, 21.0.13.0.3, 25.0.5.0.3 y 27.0.1.0.3. [1][2][6]
- 2026-11-18: Quang Luong de Calif.io publica el análisis técnico de causa raíz ('Java4Shell') y Red Hat emite el boletín de seguridad RHSB-2026-018. [4][5]

## Fuentes

1. OpenJDK Vulnerability Advisory: 2026/11/17 (CVE-2026-114938 in Hotspot Base64 Intrinsic). OpenJDK Vulnerability Group. publicado 2026-11-17. https://openjdk.org/groups/vulnerability/advisories/2026-11-17 (consultado 2026-11-23; tier 3: official site)
2. Oracle Critical Security Patch Update Advisory - November 2026. Oracle Corporation. publicado 2026-11-17. https://www.oracle.com/security-alerts/cspunov2026.html (consultado 2026-11-23; tier 3: official site)
3. NVD Detail for CVE-2026-114938: OpenJDK HotSpot VM AVX-512 Base64 Decoder Heap-Based Buffer Overflow. National Vulnerability Database (NIST). publicado 2026-11-17. https://nvd.nist.gov/vuln/detail/CVE-2026-114938 (consultado 2026-11-23; tier 1: government or public registry)
4. Java4Shell: Write once, RCE everywhere. Calif.io (Quang Luong). publicado 2026-11-18. https://calif.io/java4shell (consultado 2026-11-23; tier 3: official site)
5. Red Hat Security Bulletin RHSB-2026-018: OpenJDK AVX-512 Base64 Heap Overflow (CVE-2026-114938). Red Hat, Inc.. publicado 2026-11-18. https://access.redhat.com/security/vulnerabilities/RHSB-2026-018 (consultado 2026-11-23; tier 3: official site)
6. Critical Java Vulnerability Requires Immediate Patching | CISA. Cybersecurity and Infrastructure Security Agency (CISA). publicado 2026-11-17. https://www.cisa.gov/news-events/alerts/2026/11/17/critical-java-vulnerability-requires-immediate-patching (consultado 2026-11-24; tier 1: government or public registry)
7. Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ. Tenable Research. publicado 2026-11-17. https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Java4Shell (CVE-2026-114938)." Versión e2fbc4cd, 2026-11-24. https://mimirwiki.com/es/wiki/java4shell
