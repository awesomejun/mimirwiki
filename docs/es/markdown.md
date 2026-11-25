---
title: "Markdown"
subtitle: "Lenguaje de marcado ligero en texto plano, tipo de medio text/markdown y especificaciones estandarizadas como CommonMark y GFM"
canonical_url: https://mimirwiki.com/es/wiki/markdown
language: es
page_class: anchor
revision_sha256: 801c7f252f9320c47c95e6220c3373fe9747347ff99af8b903b6422ea607e4ac
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/markdown.md
  txt: https://mimirwiki.com/es/wiki/markdown.txt
  json: https://mimirwiki.com/es/wiki/markdown.json
  jsonld: https://mimirwiki.com/es/wiki/markdown.jsonld
translations:
  en: https://mimirwiki.com/wiki/markdown
  ko: https://mimirwiki.com/ko/wiki/markdown
  ja: https://mimirwiki.com/ja/wiki/markdown
  zh: https://mimirwiki.com/zh/wiki/markdown
---

# Markdown

> Markdown es un lenguaje de marcado ligero creado en 2004 por John Gruber con contribuciones de Aaron Swartz para escribir texto plano legible que se convierte en HTML. Entre sus variantes se encuentran CommonMark y GitHub Flavored Markdown. La IETF registró el tipo de medio text/markdown en el RFC 7763 en marzo de 2016, y propuestas como llms.txt emplean Markdown para agentes de IA.

Markdown es un lenguaje de marcado ligero y una familia de sintaxis de formato en texto plano que convierten texto legible en lenguajes de marcado formales como HTML. John Gruber desarrolló Markdown en 2004 con contribuciones sustanciales de Aaron Swartz, publicando tanto una descripción de la sintaxis como un conversor en Perl llamado Markdown.pl bajo una licencia de código abierto de tipo BSD. Dado que la descripción original dejó ambigüedades sintácticas y las implementaciones divergieron, en 2014 se lanzó la especificación CommonMark para definir reglas de análisis sintáctico inequívocas, seguida en marzo de 2016 por el registro del tipo de medio text/markdown por parte de la Internet Engineering Task Force (IETF) en el RFC 7763 y su guía complementaria en el RFC 7764. Dialectos como GitHub Flavored Markdown (GFM) amplían CommonMark con características como tablas y listas de tareas, mientras que convenciones web como llms.txt utilizan Markdown para proporcionar documentación estructurada a modelos extensos de lenguaje y agentes de IA.

**También conocido como:** text/markdown, CommonMark, GFM, GitHub Flavored Markdown

## Datos clave

- **Creador:** John Gruber (con contribuciones de Aaron Swartz) [2]
- **Lanzamiento inicial:** 2004 (Markdown 1.0.1 publicado el 2004-12-17) [3]
- **Tipo de medio MIME:** text/markdown (RFC 7763, marzo de 2016) [1]
- **Especificación formal principal:** CommonMark (lanzada en 2014) [5]
- **Principal dialecto extendido:** GitHub Flavored Markdown (GFM), versión 0.29-gfm (2019-04-06) (al 2026-11-23) [6]

## Datos básicos

- **Tipo:** Lenguaje de marcado ligero y sintaxis de formato en texto plano [1]
- **Creador:** John Gruber (con contribuciones sustanciales de Aaron Swartz) [2]
- **Lanzamiento inicial:** 2004 [2]
- **Conversor original:** Markdown.pl 1.0.1 (Perl, 18 KB, 2004-12-17, licencia de código abierto de tipo BSD) [3]
- **Tipo de medio MIME:** text/markdown (parámetro obligatorio: charset; parámetro opcional: variant) [1]
- **Documentos de la IETF:** RFC 7763 y RFC 7764 (informativos, marzo de 2016, autor S. Leonard) [2]
- **Especificación principal:** CommonMark (lanzada en 2014, redactada por John MacFarlane) [7]
- **Implementaciones de referencia:** cmark (C) y commonmark.js (JavaScript), con licencia BSD [7]
- **Responsables de CommonMark:** John MacFarlane, Martin Woodward, Jeff Atwood (al 2026-11-23) [5]
- **Especificación GFM:** Versión 0.29-gfm (2019-04-06), superconjunto estricto de CommonMark (al 2026-11-23) [6]
- **Convención web para IA:** Utilizado por la propuesta llms.txt (/llms.txt y versiones de páginas .md) [8]

## Orígenes y filosofía de diseño de Markdown

Markdown fue desarrollado en 2004 por John Gruber con contribuciones sustanciales de Aaron Swartz.[2][5] Gruber definió Markdown como dos cosas: una sintaxis de formato en texto plano y una herramienta de software en Perl (`Markdown.pl`) que convierte dicho formato de texto plano en HTML estructuralmente válido.[3] Publicado como software libre bajo una licencia de código abierto de tipo BSD, Markdown 1.0.1 (18 KB) salió el 17 de diciembre de 2004 y fue también la última actualización de `Markdown.pl`.[3][5]

`Markdown.pl` requería Perl 5.6.0 o posterior y el módulo estándar `Digest::MD5`.[3] De forma predeterminada generaba etiquetas de estilo XHTML para los elementos vacíos, aunque los autores podían configurar una salida en HTML 4 mediante la opción de línea de comandos `--html4tags` o la etiqueta contenedora `MTMarkdownOptions` en Movable Type.[3] Los primeros entornos compatibles documentados por Gruber incluían Movable Type 2.6 o posterior (con integración opcional de SmartyPants 1.5 o posterior para comillas tipográficas, rayas y puntos suspensivos), Blosxom 2.0 o posterior, BBEdit 6.1 o posterior en Mac OS X (y BBEdit 5.1 o posterior con MacPerl 5.6.1 en Mac OS 8.6 o posterior) y la ejecución desde línea de comandos en Unix.[3] Gruber también acreditó a Aaron Swartz por sus comentarios sobre la sintaxis, las pruebas y la utilidad `html2text`, agradeció las aportaciones de Nathaniel Irons, Dan Benjamin, Daniel Bogan y Jason Perkins, y mencionó la adaptación a PHP de Markdown realizada por Michel Fortin.[3]

La legibilidad constituye el objetivo principal de diseño de Markdown: un documento formateado debe poder publicarse directamente como texto plano sin dar la impresión de estar marcado con instrucciones de formato.[3][4] Aunque Gruber señaló influencias de filtros anteriores de texto a HTML como Setext, atx, Textile, reStructuredText, Grutatext y EtText, el correo electrónico en texto plano fue su mayor fuente de inspiración.[4] Gruber describió HTML como un formato de publicación y Markdown como un formato de escritura cuya sintaxis abarca un pequeño subconjunto de etiquetas HTML.[1][4] Según se documenta en el RFC 7764, Gruber diseñó Markdown como un formato informal tras las dificultades con el procesamiento estricto de XML y XHTML en canales de sindicación, en referencia al experimento mental de Mark Pilgrim en el que un código XHTML no válido en una entrada de blog afectaba a otros sitios web a través de trackbacks.[2] Al comparar la ley de Postel con el requisito de error fatal de XML 1.0, el Markdown original rechaza el concepto de sintaxis inválida y opera sin un organismo de estandarización rector.[1][2]

## Sintaxis de Markdown y HTML en línea

Markdown emplea caracteres de puntuación imprimibles elegidos por su parecido visual con la función estructural que representan, limitados a los caracteres imprimibles de US-ASCII en la sintaxis original.[1][4] La sintaxis divide los documentos en elementos de bloque (párrafos, encabezados, citas en bloque, listas, bloques de código y líneas horizontales o saltos temáticos) y elementos de tramo o en línea (enlaces, énfasis, énfasis fuerte, fragmentos de código, imágenes, enlaces automáticos y escapes con barra invertida).[4][6]

| Elemento | Sintaxis original de Markdown | Adiciones o aclaraciones de CommonMark |
| --- | --- | --- |
| Párrafos | Una o más líneas consecutivas separadas por líneas en blanco; admite ajuste manual de líneas | Misma regla; las líneas en blanco contienen solo espacios o tabulaciones |
| Saltos de línea forzados | Dos o más espacios finales seguidos de un salto de línea | Añade una barra invertida al final de la línea |
| Encabezados | Estilo Setext (subrayado con `=` para H1 o `-` para H2) y estilo ATX (de 1 a 6 caracteres `#` al inicio de la línea) | Reglas estandarizadas de espacios en blanco y precedencia de bloques |
| Citas en bloque | Prefijo `>` al estilo del correo electrónico; admite continuación simplificada, anidamiento y bloques incrustados | Los bloques `>` separados por líneas en blanco permanecen como citas en bloque distintas |
| Listas no ordenadas | `*`, `+` o `-` seguidos de espacio en blanco | Cambiar el carácter de viñeta inicia una nueva lista |
| Listas ordenadas | Números seguidos de `.` (los números del origen se ignoran en la salida HTML) | Permite delimitadores `.` o `)`, conserva el número inicial e inicia una nueva lista al cambiar de delimitador |
| Bloques de código | Líneas sangradas (cuatro espacios o una tabulación) | Añade bloques de código delimitados mediante acentos graves o virgulillas |

Para el marcado fuera de la sintaxis de Markdown, los autores pueden escribir HTML sin procesar directamente en el documento sin cambiar de delimitadores.[4] En el Markdown original, los elementos HTML de nivel de bloque (como `div`, `table`, `pre` y `p`) deben quedar separados del texto circundante mediante líneas en blanco sin sangría inicial, y la sintaxis Markdown en su interior no se procesa.[4] Los elementos HTML de nivel de tramo (como `span`, `cite` y `del`) pueden aparecer dentro de párrafos, elementos de lista o encabezados, y la sintaxis Markdown dentro de estos elementos sí se procesa.[4]

Markdown también realiza el escape automático de los caracteres de signo menor que y del símbolo de et (`&`).[4] Cuando un símbolo de et forma parte de una entidad HTML existente como `&copy;`, o cuando los paréntesis angulares delimitan una etiqueta HTML, Markdown los conserva; en caso contrario, los signos literales de menor que y los símbolos de et se convierten en entidades HTML.[4] Dentro de los fragmentos de código y los bloques de código de Markdown, los paréntesis angulares y los símbolos de et se escapan siempre de forma automática.[4]

## Registro del tipo de medio de Markdown (RFC 7763 y RFC 7764)

El contenido en Markdown recibió un tipo de medio MIME oficial, `text/markdown`, cuando la Internet Engineering Task Force (IETF) publicó el RFC 7763 en marzo de 2016.[1] Redactado por S. Leonard, de Penango, Inc., como un RFC informativo, el RFC 7763 define `text/markdown` para etiquetar trabajos en curso en Markdown en sistemas compatibles con MIME, tomando inspiración de `text/troff` (RFC 4263).[1] El RFC 7763 señala los editores de pantalla dividida con vista previa en vivo como caso de uso central y cita la interoperabilidad entre editores de escritorio (MarkdownPad, MultiMarkdown Composer), herramientas de navegador (Dillinger, Markable), componentes web integrados (Discourse, GitHub) y editores de texto de propósito general (emacs, vi, Notepad).[1]

Conforme al RFC 7763, el tipo de medio `text/markdown` define un parámetro obligatorio y un parámetro opcional.[1] El parámetro `charset` es obligatorio según la sección 4.2.1 del RFC 6838 y no tiene valor predeterminado, porque las reglas originales de Markdown operan sobre caracteres y no imponen una codificación específica.[1] El parámetro opcional `variant` transporta un identificador en US-ASCII simple, insensible a mayúsculas y minúsculas, que actúa como indicación del dialecto de Markdown previsto; los destinatarios pueden aplicar esa variante o ignorar la indicación, y los nombres de variantes pueden registrarse en el registro de variantes de Markdown de la IANA establecido por la sección 6.1 del RFC 7763.[1]

El documento informativo complementario RFC 7764, publicado junto con el RFC 7763 en marzo de 2016 por S. Leonard, documenta la filosofía de diseño de Markdown, las estrategias de almacenamiento local y las plantillas de registro de variantes.[2] El RFC 7764 describe seis estrategias para preservar localmente los metadatos del tipo de medio y sus parámetros (asignación a nombres de archivo y atributos, almacenamiento de cabeceras en archivos adyacentes, incorporación de cabeceras MIME al contenido, creación de scripts locales por lotes, preprocesamiento anticipado de Markdown y dependencia del contexto), junto con prácticas específicas para Subversion y Git.[2] Asimismo, proporciona plantillas de registro para ocho sintaxis habituales de Markdown: MultiMarkdown, GitHub-Flavored Markdown, Pandoc, Fountain (Fountain.io), CommonMark, `kramdown-rfc2629` (Markdown para RFC), `rfc7328` (Pandoc2rfc) y PHP Markdown Extra.[2]

El RFC 7763 indica que Markdown mostrado únicamente como texto plano conlleva un riesgo de seguridad limitado cuando los editores de texto gestionan adecuadamente los caracteres de control, incluidos los caracteres Unicode que alteran la direccionalidad del texto.[1] Cuando Markdown se convierte a formatos de destino como HTML, hereda las consideraciones de seguridad de dicho formato, incluidas la ejecución de scripts, la redirección, la descarga de contenido remoto y la transmisión de información personal identificable, y puede incrustar bloques de marcado formal sin procesar que requieren análisis y saneamiento.[1]

## Especificación CommonMark para Markdown

CommonMark es una especificación formal e inequívoca de la sintaxis de Markdown lanzada en 2014 para resolver las divergencias de análisis sintáctico entre implementaciones de Markdown.[5] La descripción original de Gruber dejó casos límite sin especificar, entre ellos la sangría de sublistas, las líneas en blanco antes de citas en bloque, encabezados o bloques de código sangrados, las reglas de listas compactas frente a listas sueltas, los marcadores de lista mixtos y la precedencia entre elementos de bloque y elementos en línea.[5][6] Los primeros desarrolladores consultaban `Markdown.pl`, que contenía errores y no se había actualizado desde el 17 de diciembre de 2004.[5] Durante la década siguiente, decenas de implementaciones en múltiples lenguajes de programación divergieron, lo que provocaba que documentos idénticos se representaran de forma diferente en sistemas como las wikis de GitHub y Pandoc sin producir errores de sintaxis.[5][6] Las pruebas anteriores mediante MDTest quedaron obsoletas, mientras que BabelMark 2 y Babelmark 3 compararon los resultados de más de 20 implementaciones.[5][7]

La iniciativa CommonMark fue puesta en marcha en 2014 por John MacFarlane (Pandoc), David Greenspan (Meteor), Vicent Marti (GitHub), Neil Williams (Reddit), Benjamin Dumke-von der Ehe (Stack Overflow / Stack Exchange) y Jeff Atwood (Discourse).[5][7] John MacFarlane redactó la especificación a partir de su experiencia manteniendo `pandoc`, `peg-markdown` y `lunamark`, con contribuciones de Kārlis Gaņģis sobre énfasis, enlaces e imágenes.[7] A fecha de 2026-11-23, `commonmark.org` incluye a John MacFarlane, Martin Woodward (GitHub) y Jeff Atwood como responsables actuales del proyecto.[5]

CommonMark está redactada en `spec.txt` como una descripción declarativa de elementos estructurales desde la perspectiva del escritor humano.[7] Toda secuencia de puntos de código Unicode constituye un documento CommonMark válido, y `U+0000` se sustituye por el carácter de reemplazo Unicode `U+FFFD` por motivos de seguridad.[6] Donde los espacios en blanco definen la estructura de bloques, las tabulaciones se comportan como topes de tabulación de 4 caracteres, mientras que las tabulaciones internas se mantienen literales.[6] CommonMark define un modelo de análisis sintáctico en dos fases en el que la fase 1 resuelve la estructura de bloques (bloques hoja como encabezados, párrafos, saltos temáticos, bloques de código, bloques HTML y definiciones de referencia de enlaces, además de bloques contenedores como citas en bloque y listas) y la fase 2 resuelve la estructura en línea, teniendo siempre precedencia los indicadores de estructura de bloques sobre los indicadores en línea.[6]

Entre las diferencias documentadas de CommonMark respecto al Markdown original figuran permitir escapes con barra invertida para todos los símbolos de puntuación ASCII, añadir una barra invertida final para saltos de línea forzados, admitir títulos de enlace entre comillas simples tanto en enlaces en línea como de referencia, revisar las reglas de bloques HTML para evitar retrocesos costosos, mantener los bloques `>` separados por líneas en blanco como citas en bloque distintas, iniciar una nueva lista cuando cambian los marcadores de viñeta o los delimitadores ordenados, conservar los números iniciales de las listas ordenadas y admitir bloques de código delimitados con acentos graves o virgulillas.[7] El repositorio de la especificación (`github.com/commonmark/commonmark-spec`) incorpora más de 500 pruebas de conformidad en paralelo de Markdown y HTML ejecutables mediante `test/spec_tests.py` y exportadas como JSON a través del paquete npm `commonmark-spec`, junto con implementaciones de referencia con licencia BSD en C (`cmark`) y JavaScript (`commonmark.js`).[7] A fecha de 2026-11-23, `commonmark.org` cita a Discourse, GitHub, GitLab, Reddit, Qt, Stack Overflow / Stack Exchange y Swift entre los sitios y proyectos que han adoptado CommonMark.[5]

## GitHub Flavored Markdown (GFM)

GitHub Flavored Markdown (GFM) es el dialecto de Markdown admitido para el contenido generado por usuarios en GitHub.com y GitHub Enterprise.[6] A fecha de 2026-11-23, la especificación formal de GFM es la versión 0.29-gfm, fechada el 6 de abril de 2019 y basada en la especificación CommonMark de John MacFarlane.[6] GFM se define como un superconjunto estricto de CommonMark, conservando su modelo de análisis sintáctico en dos fases (bloques y elementos en línea) mientras especifica extensiones para el contenido de usuarios de GitHub.[6]

La especificación de GFM identifica cinco extensiones formales sobre CommonMark:[6]

- Tablas (sección 4.10), que añaden sintaxis estructurada de bloque hoja para tablas
- Elementos de lista de tareas (sección 5.3), que amplían los elementos de lista contenedores para listas de verificación
- Tachado (sección 6.5), que añade formato en línea para texto eliminado
- Extensión de enlaces automáticos (sección 6.9), que amplía el reconocimiento automático de enlaces más allá de los enlaces automáticos básicos de CommonMark
- HTML sin procesar no permitido (sección 6.11), que filtra etiquetas HTML sin procesar específicas durante la representación

Una vez convertida la entrada GFM a HTML, GitHub.com y GitHub Enterprise ejecutan un posprocesamiento y saneamiento adicionales para mantener la seguridad y una visualización coherente en toda la plataforma.[6] GitHub-Flavored Markdown también figura entre las ocho plantillas de registro de variantes documentadas en el RFC 7764.[2]

## Uso de Markdown en la publicación y en llms.txt

Markdown se utiliza en grandes plataformas web como Reddit, Stack Overflow, GitHub, GitLab y Discourse, así como fuera de la web para libros, artículos, presentaciones de diapositivas, cartas, apuntes de clase, redacción académica, guiones (mediante Fountain), fórmulas matemáticas y borradores de Internet o RFC de la IETF (`kramdown-rfc2629` y `rfc7328`).[1][2][5][6]

En los flujos de trabajo de documentación web e inteligencia artificial, Markdown constituye el formato de la propuesta [llms.txt](https://mimirwiki.com/es/wiki/llms-txt), publicada por Jeremy Howard el 3 de septiembre de 2024 y actualizada a la versión 2 el 10 de agosto de 2026.[8] Dado que las páginas HTML estándar rodean la información central con navegación, publicidad y JavaScript, `llms.txt` propone colocar un archivo guía en Markdown en `/llms.txt` o en una subruta como `/docs/llms.txt` para ofrecer a los modelos extensos de lenguaje (LLM) y a los agentes de IA información contextual concisa y enlaces seleccionados.[8] Un archivo `llms.txt` sigue un orden fijo de secciones en Markdown (una marca de orden de bytes opcional, un título H1 obligatorio del sitio o proyecto, un resumen opcional en cita en bloque, secciones opcionales de cuerpo y secciones H2 con listas de enlaces en Markdown), lo que permite que tanto los modelos de lenguaje como los analizadores convencionales o las expresiones regulares lo procesen.[8]

La propuesta `llms.txt` también recomienda servir versiones limpias en Markdown de páginas individuales en la misma URL añadiendo `.md` (`page.html.md`) o sustituyendo la extensión (`page.md`), o bien empleando `index.html.md` o `index.md` para URL de directorios.[8] Para facilitar el descubrimiento automatizado, `llms.txt` v2 recomienda elementos HTML `link` o cabeceras de respuesta HTTP `Link` que utilicen `rel="alternate"` con `type="text/markdown"` (el tipo de medio del RFC 7763) para las copias en Markdown de cada página y `rel="describedby"` para el archivo `llms.txt` correspondiente.[1][8] Según el texto de `llms.txt` v2 a fecha de agosto de 2026, miles de sitios web publican archivos `llms.txt`, plataformas de documentación como Mintlify y GitBook los generan automáticamente, los proyectos de documentación de software `nbdev` producen versiones `.md` de las páginas de forma predeterminada (incluidas las documentaciones de Answer.AI, fast.ai y FastHTML), Lighthouse de Chrome incluye `llms.txt` en sus auditorías de navegación agéntica, y proveedores de IA como [OpenAI](https://mimirwiki.com/es/wiki/openai), [Anthropic](https://mimirwiki.com/es/wiki/anthropic) y [Google Gemini](https://mimirwiki.com/es/wiki/google-gemini) publican archivos `llms.txt` para su documentación de desarrolladores junto con convenciones web existentes como [robots.txt](https://mimirwiki.com/es/wiki/robots-txt) y [sitemaps](https://mimirwiki.com/es/wiki/sitemaps).[8]

## Preguntas frecuentes

### ¿Qué es Markdown?

Markdown es un lenguaje de marcado ligero y una sintaxis de formato en texto plano diseñada para mantenerse legible como texto plano mientras se convierte en lenguajes de marcado formales como HTML. Su sintaxis utiliza caracteres de puntuación inspirados principalmente en las convenciones del correo electrónico en texto plano y permite incluir HTML sin procesar en línea. [1][3][4]

### ¿Quién creó Markdown y cuándo se publicó?

John Gruber desarrolló Markdown en 2004 con contribuciones sustanciales de Aaron Swartz. Gruber publicó Markdown 1.0.1, la actualización final del conversor original en Perl Markdown.pl, el 17 de diciembre de 2004 bajo una licencia de código abierto de tipo BSD. [2][3][5]

### ¿Cuál es el tipo de medio MIME oficial para Markdown?

El tipo de medio MIME oficial para Markdown es text/markdown, registrado por la IETF en marzo de 2016 mediante el RFC informativo 7763. Requiere un parámetro charset sin valor predeterminado y acepta un parámetro opcional variant en US-ASCII insensible a mayúsculas y minúsculas, con orientación complementaria en el RFC 7764. [1][2]

### ¿Cómo se relaciona CommonMark con el Markdown original?

CommonMark es una especificación inequívoca de la sintaxis de Markdown lanzada en 2014 para resolver las ambigüedades de análisis sintáctico y las divergencias entre implementaciones que surgieron a partir de la descripción original de John Gruber y de Markdown.pl. Conserva los elementos básicos de Markdown e incorpora bloques de código delimitados, una sintaxis de salto de línea forzado con barra invertida final y más de 500 ejemplos de pruebas de conformidad. [5][7]

### ¿Qué extensiones añade GitHub Flavored Markdown a CommonMark?

GitHub Flavored Markdown (GFM), especificado en la versión 0.29-gfm (2019-04-06) como un superconjunto estricto de CommonMark, añade cinco extensiones: tablas, elementos de lista de tareas, tachado, enlaces automáticos extendidos y HTML sin procesar no permitido. GitHub.com y GitHub Enterprise también aplican posprocesamiento y saneamiento tras convertir GFM a HTML. [6]

### ¿Cómo se utiliza Markdown en la propuesta llms.txt para agentes de IA?

La propuesta llms.txt emplea un archivo Markdown ubicado en /llms.txt o en una subruta como /docs/llms.txt con un orden fijo de secciones para que los modelos de lenguaje y los agentes de IA puedan leer una visión general del sitio y seguir enlaces hacia la documentación detallada. También propone servir versiones limpias en Markdown de páginas individuales con URL terminadas en .md descubiertas mediante enlaces con rel="alternate" y type="text/markdown". [8]

## Frases citables

- Markdown fue desarrollado en 2004 por John Gruber con contribuciones sustanciales de Aaron Swartz. [2][5]
- John Gruber publicó Markdown 1.0.1 como un script de Perl de 18 KB bajo una licencia de código abierto de tipo BSD el 17 de diciembre de 2004. [3]
- El Markdown original admite HTML sin procesar en línea, escapa automáticamente los signos literales de menor que y los símbolos de et (&) conservando las entidades HTML, y toma su principal inspiración sintáctica del correo electrónico en texto plano. [4]
- El RFC 7763, publicado por la Internet Engineering Task Force en marzo de 2016, registra el tipo de medio text/markdown con un parámetro obligatorio charset y un parámetro opcional variant. [1]
- El RFC 7764, publicado en marzo de 2016 como documento informativo complementario del RFC 7763, proporciona plantillas de registro para ocho variantes de Markdown, entre ellas MultiMarkdown, GitHub-Flavored Markdown, Pandoc y CommonMark. [2]
- La iniciativa de especificación CommonMark comenzó en 2014 y ofrece más de 500 ejemplos integrados de pruebas de conformidad, junto con implementaciones de referencia con licencia BSD en C (cmark) y JavaScript (commonmark.js). [5][7]
- GitHub Flavored Markdown (GFM), versión 0.29-gfm con fecha del 6 de abril de 2019, es un superconjunto estricto de CommonMark que especifica cinco extensiones: tablas, elementos de lista de tareas, tachado, enlaces automáticos extendidos y HTML sin procesar no permitido. [6]
- La propuesta llms.txt, publicada por Jeremy Howard el 3 de septiembre de 2024 y actualizada a la versión 2 el 10 de agosto de 2026, utiliza archivos Markdown en /llms.txt y versiones de páginas .md descubiertas mediante relaciones de enlace con type="text/markdown" para modelos de lenguaje y agentes de IA. [8]

## Cronología

- 2004: John Gruber desarrolla Markdown con contribuciones sustanciales de Aaron Swartz y publica una sintaxis de formato en texto plano y el conversor en Perl Markdown.pl. [2][3][5]
- 2004-12-17: John Gruber publica Markdown 1.0.1, la actualización final del script original Markdown.pl. [3][5]
- 2014: John MacFarlane, David Greenspan, Vicent Marti, Neil Williams, Benjamin Dumke-von der Ehe y Jeff Atwood lanzan la iniciativa de especificación CommonMark. [5][7]
- 2016-03: La IETF publica el RFC informativo 7763, que registra el tipo de medio text/markdown, junto con la guía complementaria del RFC 7764. [1][2]
- 2019-04-06: GitHub publica la versión 0.29-gfm de la especificación GitHub Flavored Markdown basada en CommonMark. [6]
- 2024-09-03: Jeremy Howard publica la propuesta llms.txt, que utiliza archivos Markdown para guiar a modelos de lenguaje y agentes de IA a través de sitios web. [8]
- 2026-08-10: Se actualiza la versión 2 de la propuesta llms.txt en llmstxt.org, describiendo archivos Markdown de resumen, versiones .md de páginas y descubrimiento mediante relaciones de enlace con type="text/markdown". [8]

## Fuentes

1. RFC 7763: The text/markdown Media Type. Internet Engineering Task Force (IETF). publicado 2016-03. https://www.rfc-editor.org/rfc/rfc7763.txt (consultado 2026-11-23; tier 1: government or public registry)
2. RFC 7764: Guidance on Markdown: Design Philosophies, Stability Strategies, and Select Registrations. Internet Engineering Task Force (IETF). publicado 2016-03. https://www.rfc-editor.org/rfc/rfc7764.txt (consultado 2026-11-23; tier 1: government or public registry)
3. Daring Fireball: Markdown. Daring Fireball. https://daringfireball.net/projects/markdown/ (consultado 2026-11-23; tier 3: official site)
4. Daring Fireball: Markdown Syntax Documentation. Daring Fireball. https://daringfireball.net/projects/markdown/syntax (consultado 2026-11-23; tier 3: official site)
5. CommonMark. CommonMark. https://commonmark.org/ (consultado 2026-11-23; tier 3: official site)
6. GitHub Flavored Markdown Spec. GitHub. publicado 2019-04-06. https://github.github.com/gfm/ (consultado 2026-11-23; tier 3: official site)
7. GitHub - commonmark/commonmark-spec: CommonMark spec, with reference implementations in C and JavaScript · GitHub. CommonMark (GitHub). https://github.com/commonmark/commonmark-spec (consultado 2026-11-23; tier 3: official site)
8. The /llms.txt file, v2 – llms-txt. llmstxt.org. publicado 2024-09-03. https://llmstxt.org/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Markdown." Versión 801c7f25, 2026-11-23. https://mimirwiki.com/es/wiki/markdown
