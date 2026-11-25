---
title: "llms.txt"
subtitle: "Propuesta de archivo Markdown que guía a los agentes de IA hacia el contenido clave de un sitio web"
canonical_url: https://mimirwiki.com/es/wiki/llms-txt
language: es
page_class: anchor
revision_sha256: 295b827c96618c96a0ddeb2a41384eecaf00063a81e20735b44e3f78877a4ca7
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/es/wiki/llms-txt.md
  txt: https://mimirwiki.com/es/wiki/llms-txt.txt
  json: https://mimirwiki.com/es/wiki/llms-txt.json
  jsonld: https://mimirwiki.com/es/wiki/llms-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/llms-txt
  ko: https://mimirwiki.com/ko/wiki/llms-txt
  ja: https://mimirwiki.com/ja/wiki/llms-txt
  zh: https://mimirwiki.com/zh/wiki/llms-txt
---

# llms.txt

> llms.txt es una propuesta de convención web consistente en un archivo Markdown, por lo general en /llms.txt, que proporciona a los agentes de IA un resumen breve de un sitio web y enlaces a versiones en Markdown limpias de sus páginas clave. Jeremy Howard publicó la propuesta el 2024-09-03 y lanzó la versión 2 en agosto de 2026. Se trata de una propuesta comunitaria y su publicación es opcional.

llms.txt es una propuesta de convención web mediante la cual un sitio publica un archivo Markdown llamado llms.txt que ofrece a los modelos de lenguaje grande (LLM) y a los agentes de IA un breve resumen del sitio junto con enlaces a contenido más detallado y adecuado para estos modelos. Jeremy Howard publicó la propuesta el 2024-09-03 en llmstxt.org y lanzó una segunda versión, v2, en agosto de 2026. El archivo puede ubicarse en la raíz del sitio (/llms.txt) o en cualquier subruta, y sigue un orden fijo de secciones que los analizadores sintácticos convencionales pueden leer. llmstxt.org presenta llms.txt como una propuesta que permanece abierta a los aportes de la comunidad.

**También conocido como:** /llms.txt, El archivo /llms.txt, Propuesta llms.txt

## Datos clave

- **Primera publicación:** 2024-09-03 [1]
- **Versión actual:** v2 (agosto de 2026) (al 2026-11-21) [2]
- **Autor:** Jeremy Howard [1]
- **Contenido obligatorio:** Un encabezado H1 con el nombre del proyecto o sitio [1]
- **Ubicación:** /llms.txt en la raíz del sitio, o en cualquier subruta [1]

## Datos básicos

- **Tipo:** Propuesta de convención web para un archivo guía en Markdown dirigido a LLM y agentes de IA [1]
- **Autor:** Jeremy Howard [1]
- **Primera publicación:** 2024-09-03 [1]
- **Versión actual:** v2 (agosto de 2026) (al 2026-11-21) [2]
- **Nombre de archivo:** llms.txt [1]
- **Ubicación:** Raíz del sitio (/llms.txt) o cualquier subruta, por ejemplo /docs/llms.txt [1]
- **Formato:** Markdown con un orden fijo de secciones [1]
- **Contenido obligatorio:** Un encabezado H1 con el nombre del proyecto o sitio [1]
- **Descubrimiento:** Relaciones de enlace alternate (tipo text/markdown) y describedby [1]
- **Estado:** Propuesta, abierta a aportes de la comunidad [1]
- **Repositorio:** github.com/AnswerDotAI/llms-txt (licencia Apache-2.0) [3]
- **Herramientas de referencia:** Paquete de Python llms-txt con el comando llms_txt2ctx [4]

## Qué es llms.txt

llms.txt es una propuesta para un archivo [Markdown](https://mimirwiki.com/es/wiki/markdown) que un sitio web publica con el fin de ofrecer a los modelos de lenguaje grande (LLM) y a los agentes de IA una guía concisa de su contenido.[1] La propuesta sostiene que las páginas web están diseñadas para lectores humanos: la navegación, la publicidad y los scripts rodean la información en una página HTML, y la mayoría de los sitios web son demasiado grandes para caber en la ventana de contexto de un modelo.[1] Por ello, un archivo llms.txt reúne en un solo lugar contexto breve, orientación y enlaces a archivos Markdown más detallados.[1]

La propuesta llms.txt consta de dos partes. La primera es el propio archivo `llms.txt`. La segunda es una versión limpia en Markdown de cada página que un agente pueda necesitar, servida en la misma URL que la página original con una extensión `.md`.[1] Se espera que los agentes lean o busquen en el archivo llms.txt, encuentren lo que necesitan y luego sigan los enlaces relevantes, de modo que el detalle se obtenga únicamente bajo demanda.[1]

Jeremy Howard publicó la propuesta llms.txt el 2024-09-03 y lanzó un texto revisado, denominado v2, en agosto de 2026.[1][2] La propuesta se mantiene en el repositorio AnswerDotAI/llms-txt en GitHub bajo la licencia Apache-2.0.[3] Según la propuesta, los archivos llms.txt se utilizan principalmente para documentación de software.[1]

## Formato del archivo llms.txt

Un archivo llms.txt está escrito en Markdown y contiene las siguientes partes en un orden fijo.[1]

- Una marca de orden de bytes (BOM) opcional
- Un encabezado H1 con el nombre del proyecto o sitio, que es la única parte obligatoria
- Una cita en bloque (blockquote) con un resumen breve del proyecto
- Cero o más secciones Markdown de cualquier tipo excepto encabezados, con información más detallada
- Cero o más secciones introducidas por encabezados H2, cada una con una lista de enlaces a información adicional

Cada entrada en una lista de enlaces de llms.txt es un hipervínculo en Markdown con la forma `[name](url)`, seguido opcionalmente de dos puntos y notas sobre el archivo enlazado.[1] Una sección titulada Optional contiene enlaces secundarios que un agente puede omitir cuando se necesita un contexto más corto. En la versión v2 esto es solo una convención, ya que las herramientas que otorgaban un significado mecánico a esa sección ya no forman parte de la propuesta.[1][2]

La propuesta utiliza Markdown en lugar de un formato estructurado como XML porque se prevé que los archivos sean leídos por modelos de lenguaje y agentes. Sin embargo, la estructura fija sigue permitiendo su procesamiento mediante analizadores sintácticos convencionales y expresiones regulares.[1]

## Ubicación y descubrimiento de llms.txt

Un archivo llms.txt puede colocarse en la ruta raíz de un sitio web, `/llms.txt`, o en cualquier subruta como `/docs/llms.txt`. Un archivo cubre las URL situadas bajo su ruta y, cuando aplica más de un archivo, se espera que los agentes utilicen el más específico.[1] La primera versión de la propuesta permitía subrutas sin definir su significado, y la versión v2 añadió esta regla.[2]

Para páginas individuales, la propuesta llms.txt solicita una versión en Markdown en la misma URL, ya sea añadiendo `.md` (`page.html.md`) o reemplazando la extensión (`page.md`). Las URL sin nombre de archivo utilizan `index.html.md` o `index.md`.[1] La primera versión especificaba únicamente la forma añadida.[2]

La versión 2 añadió el descubrimiento mediante relaciones de enlace estándar. Un enlace con `rel="alternate"` y `type="text/markdown"` apunta a la versión en Markdown de una página, y `rel="describedby"` apunta al archivo llms.txt que la cubre. Ambos pueden proporcionarse como elementos HTML `link` o en una cabecera HTTP `Link`.[1][2] Los tipos de relación `alternate` y `describedby` están registrados en el registro Link Relations de la IANA.[9] La propuesta no utiliza el prefijo de ruta `/.well-known/` definido por el RFC 8615, debido a que los URI well-known solo existen en la raíz del origen, mientras que muchos autores solo controlan una ruta en un servidor compartido.[1][8]

## Diferencias entre llms.txt, robots.txt y sitemap.xml

llms.txt y [robots.txt](https://mimirwiki.com/es/wiki/robots-txt) cumplen propósitos distintos. El Protocolo de Exclusión de Robots, publicado por el IETF como RFC 9309 en septiembre de 2022, permite a los propietarios de servicios controlar cómo pueden acceder los rastreadores a su contenido.[7] La propuesta llms.txt deja el control de acceso a robots.txt y describe su propio contenido como información utilizada bajo demanda, cuando un agente necesita conocer un tema mientras asiste a un usuario.[1]

llms.txt también se distingue de un [mapa del sitio](https://mimirwiki.com/es/wiki/sitemaps), que enumera todas las páginas indexables legibles por humanos de un sitio. La propuesta señala tres razones por las que un mapa del sitio no es un sustituto: a menudo no incluye versiones de las páginas legibles por LLM, no incluye URL de sitios externos y los documentos que abarca suelen ser demasiado grandes en conjunto para una ventana de contexto.[1] En cambio, llms.txt se describe como un resumen curado.[1]

La expectativa declarada del autor era que llms.txt resultaría útil principalmente para la inferencia, es decir, su uso en el momento de responder una pregunta, y no para el entrenamiento de modelos. El texto de la versión v2 informa que así es como se ha utilizado el archivo.[1]

## Adopción y herramientas de llms.txt

El texto v2 de la propuesta llms.txt, redactado por su autor, afirma que miles de sitios publican un archivo llms.txt y que OpenAI, Anthropic y la API de Gemini de Google publican uno para su documentación para desarrolladores.[1] También menciona a Mintlify, GitBook, Yoast SEO, AIOSEO y Wix entre las plataformas y complementos capaces de generar el archivo de forma automática.[1]

La documentación de Mintlify indica que aloja un archivo llms.txt en la raíz de cada proyecto de documentación y que también genera un archivo llamado `llms-full.txt`.[10] El nombre `llms-full.txt` proviene de dichas plataformas y no aparece en la propuesta de llmstxt.org.[1][10] Un ejemplo publicado es el sitio de documentación de [Model Context Protocol](https://mimirwiki.com/es/wiki/model-context-protocol), que sirve un índice de sus páginas en `modelcontextprotocol.io/llms.txt`.[11]

El sitio llmstxt.org documenta un paquete de Python, `llms-txt`, con una herramienta de línea de comandos llamada `llms_txt2ctx` que analiza un archivo llms.txt y construye un archivo de contexto XML a partir de él.[4] La primera versión de la propuesta describía esta herramienta. En la versión v2, la expansión de contexto ya no forma parte de la propuesta en sí.[2]

## Estado y límites de llms.txt

llms.txt es una propuesta. llmstxt.org describe la especificación como abierta a aportes de la comunidad y mantiene una descripción informal de esta en un repositorio público de GitHub.[1] La documentación de Lighthouse de Chrome, actualizada por última vez el 2026-05-05, denomina a llms.txt una convención emergente. Lighthouse marca su auditoría de llms.txt como no aplicable cuando un sitio devuelve un 404 para el archivo, porque ofrecerlo es opcional, y solo señala una página cuando se produce un error de servidor durante la recuperación.[5]

Publicar llms.txt no es un requisito para las funciones de búsqueda con IA de Google. La documentación de Google Search Central, actualizada por última vez el 2025-12-10, establece que los propietarios de sitios no necesitan crear nuevos archivos legibles por máquina ni archivos de texto para IA para aparecer en AI Overviews o AI Mode.[6]

llms.txt no reemplaza otras convenciones web. No establece permisos de rastreo, función que sigue correspondiendo a robots.txt, y no es un índice exhaustivo de páginas como lo es un mapa del sitio.[1][7] La propuesta señala que un archivo llms.txt puede hacer referencia al marcado de datos estructurados utilizado en un sitio para ayudar a los modelos a interpretar dicho marcado en contexto.[1]

## Preguntas frecuentes

### ¿Qué es llms.txt?

llms.txt es una propuesta de archivo Markdown que un sitio web publica para ofrecer a los agentes de IA un resumen breve del sitio y enlaces a contenido más detallado. Jeremy Howard publicó la propuesta el 2024-09-03. [1]

### ¿Dónde se coloca un archivo llms.txt?

En la ruta raíz /llms.txt o en cualquier subruta como /docs/llms.txt. Un archivo cubre las URL bajo su ruta, y se aplica el archivo más específico cuando existen varios. [1]

### ¿Es llms.txt un estándar web oficial?

llmstxt.org describe llms.txt como una propuesta abierta a los aportes de la comunidad. La documentación de Lighthouse de Chrome, actualizada por última vez el 2026-05-05, la denomina una convención emergente y trata el archivo como opcional. [1][5]

### ¿En qué se diferencia llms.txt de robots.txt?

robots.txt, especificado en el RFC 9309, indica a los rastreadores qué acceso a un sitio es aceptable. llms.txt no establece permisos. Es un resumen curado que un agente lee bajo demanda para encontrar el contenido clave de un sitio. [1][7]

### ¿Requiere Google llms.txt para AI Overviews o AI Mode?

No. La documentación de Google Search Central, actualizada por última vez el 2025-12-10, indica que no se necesitan nuevos archivos legibles por máquina ni archivos de texto para IA para aparecer en estas funciones. [6]

### ¿Qué cambió en llms.txt v2?

La versión 2, publicada en agosto de 2026, añadió el descubrimiento mediante las relaciones de enlace alternate y describedby, permitió dos formatos de URL para las versiones en Markdown de las páginas, definió qué cubre un archivo en una subruta y eliminó de la propuesta las herramientas de expansión de contexto. [2]

## Frases citables

- La propuesta llms.txt fue publicada por Jeremy Howard el 2024-09-03. [1]
- La versión 2 de la propuesta llms.txt se publicó en agosto de 2026. [2]
- La única parte obligatoria de un archivo llms.txt es un encabezado H1 con el nombre del proyecto o sitio. [1]
- Un archivo llms.txt puede colocarse en la raíz de un sitio web o en cualquier subruta, y cubre las URL situadas bajo su ruta. [1]
- La versión 2 de la propuesta llms.txt recomienda las relaciones de enlace alternate, con tipo text/markdown, y describedby para el descubrimiento. [1]
- La documentación de Lighthouse de Chrome, actualizada por última vez el 2026-05-05, describe como opcional el proporcionar un archivo llms.txt. [5]
- La documentación de Google Search Central establece que no se necesitan nuevos archivos legibles por máquina ni archivos de texto para IA para aparecer en AI Overviews o AI Mode. [6]
- La propuesta llms.txt se mantiene en el repositorio AnswerDotAI/llms-txt en GitHub bajo la licencia Apache-2.0. [3]

## Cronología

- 2024-09-03: Jeremy Howard publica la propuesta llms.txt. [1]
- 2026-08: Se publica la versión 2 de la propuesta llms.txt. [2]

## Fuentes

1. The /llms.txt file, v2 – llms-txt. llmstxt.org. publicado 2024-09-03. https://llmstxt.org/ (consultado 2026-11-21; tier 3: official site)
2. Changes – llms-txt. llmstxt.org. publicado 2026-08. https://llmstxt.org/changes.html (consultado 2026-11-21; tier 3: official site)
3. GitHub - AnswerDotAI/llms-txt: The /llms.txt file, helping language models use your website. AnswerDotAI (GitHub). https://github.com/AnswerDotAI/llms-txt (consultado 2026-11-21; tier 3: official site)
4. Python module & CLI – llms-txt. llmstxt.org. https://llmstxt.org/intro.html (consultado 2026-11-21; tier 3: official site)
5. llms.txt | Lighthouse | Chrome for Developers. Google (Chrome for Developers). publicado 2026-05-05. https://developer.chrome.com/docs/lighthouse/agentic-browsing/llms-txt (consultado 2026-11-21; tier 3: official site)
6. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. publicado 2025-12-10. https://developers.google.com/search/docs/appearance/ai-features (consultado 2026-11-21; tier 3: official site)
7. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (consultado 2026-11-21; tier 1: government or public registry)
8. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). publicado 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (consultado 2026-11-21; tier 1: government or public registry)
9. Link Relations. Internet Assigned Numbers Authority (IANA). publicado 2026-06-12. https://www.iana.org/assignments/link-relations/link-relations.xhtml (consultado 2026-11-21; tier 1: government or public registry)
10. llms.txt - Mintlify. Mintlify. https://www.mintlify.com/docs/ai/llmstxt (consultado 2026-11-21; tier 3: official site)
11. Model Context Protocol (llms.txt documentation index). Model Context Protocol project. https://modelcontextprotocol.io/llms.txt (consultado 2026-11-21; tier 3: official site)

## Citar esta página

Mimirwiki. "llms.txt." Versión 295b827c, 2026-11-21. https://mimirwiki.com/es/wiki/llms-txt
