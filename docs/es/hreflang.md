---
title: "hreflang"
subtitle: "Atributo HTML y parámetro de enlace que especifica el idioma y la región de destino de recursos web enlazados"
canonical_url: https://mimirwiki.com/es/wiki/hreflang
language: es
page_class: anchor
revision_sha256: 7ff994886bc6a4b15275cc502182b83662a366e3ed361b412a1c17df7eb138e4
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/hreflang.md
  txt: https://mimirwiki.com/es/wiki/hreflang.txt
  json: https://mimirwiki.com/es/wiki/hreflang.json
  jsonld: https://mimirwiki.com/es/wiki/hreflang.jsonld
translations:
  en: https://mimirwiki.com/wiki/hreflang
  ko: https://mimirwiki.com/ko/wiki/hreflang
  ja: https://mimirwiki.com/ja/wiki/hreflang
  zh: https://mimirwiki.com/zh/wiki/hreflang
---

# hreflang

> hreflang es un atributo HTML y parámetro de enlace que identifica el idioma, y opcionalmente la región, de un recurso enlazado mediante etiquetas BCP 47 del RFC 5646. Los sitios web publican anotaciones hreflang a través de elementos HTML link, encabezados HTTP Link o sitemaps XML para que la Búsqueda de Google pueda dirigir a los usuarios a la versión localizada correspondiente de una página.

hreflang es un atributo HTML y parámetro de anotación de enlaces que indica el idioma humano, y opcionalmente la región de destino, de un recurso web enlazado. Definido como un atributo reflejado en el WHATWG HTML Living Standard y emparejado con etiquetas de idioma BCP 47 especificadas por IETF RFC 5646, hreflang no conlleva ningún comportamiento integrado en el navegador para los elementos de ancla y sirve como metadato para procesadores de enlaces externos. En la Búsqueda de Google, los sitios publican anotaciones hreflang con la relación de enlace alternate mediante elementos HTML link, encabezados HTTP Link definidos por el RFC 8288 o sitemaps XML para conectar versiones localizadas de una página. Google exige enlaces recíprocos entre las variantes enumeradas y admite el valor x-default para páginas de respaldo cuando ningún idioma o región enumerados coinciden.

**También conocido como:** atributo hreflang, etiqueta hreflang, anotación hreflang, rel=alternate hreflang

## Datos clave

- **Especificación HTML:** WHATWG HTML Living Standard (actualizado el 2026-11-22) (al 2026-11-23) [1]
- **Estándar de etiquetas de idioma:** IETF BCP 47 / RFC 5646 (septiembre de 2009) [2]
- **Registro de subetiquetas:** IANA Language Subtag Registry (fecha de archivo 2026-11-18) (al 2026-11-23) [4]
- **Especificación de encabezado HTTP:** IETF RFC 8288 (Web Linking, octubre de 2017) [3]
- **Métodos de entrega de Google:** Elementos HTML link, encabezados HTTP Link y sitemaps XML (al 2026-11-23) [6]

## Datos básicos

- **Tipo:** Atributo HTML que sugiere el idioma humano de una URL enlazada [9]
- **Especificación HTML:** WHATWG HTML Living Standard, Sección 4.6 (actualizado el 2026-11-22) (al 2026-11-23) [1]
- **API del DOM:** HyperlinkElementUtils.hreflang (DOMString reflejado) [1]
- **Sintaxis de etiquetas de idioma:** IETF BCP 47 (RFC 5646, septiembre de 2009; deja obsoleto el RFC 4646) [2]
- **Registro de subetiquetas:** IANA Language Subtag Registry (fecha de archivo 2026-11-18) (al 2026-11-23) [4]
- **Especificación de encabezado HTTP:** IETF RFC 8288 (Web Linking, octubre de 2017; deja obsoleto el RFC 5988) [3]
- **Disponibilidad base de link en HTML:** Elemento HTML link ampliamente disponible en navegadores desde julio de 2015 [8]
- **Métodos de entrega de Google:** Elementos HTML link, encabezados HTTP Link y sitemaps XML (al 2026-11-23) [6]
- **Valor de respaldo:** x-default (anunciado por Google Search Central Blog en abril de 2013) [10]
- **Regla de confirmación:** Enlaces autorreferenciados y bidireccionales obligatorios en la Búsqueda de Google (al 2026-11-23) [6]

## Qué es hreflang

hreflang es un atributo HTML y parámetro de anotación de enlaces que indica el idioma humano, y opcionalmente la región de destino, de un recurso web enlazado.[6][9] En HTML, los enlaces son conexiones conceptuales entre dos recursos creadas por los elementos `a`, `area`, `form` y `link`, agrupadas en enlaces a recursos externos, hipervínculos y enlaces a recursos internos.[1]

En el WHATWG HTML Living Standard (actualizado por última vez el 2026-11-22), la Sección 4.6.3 define `hreflang` en el mixin de interfaz `HyperlinkElementUtils` como un atributo `DOMString` reflejado.[1] MDN Web Docs documenta tanto el elemento HTML `link` (que especifica relaciones entre el documento actual y un recurso externo) como el elemento de ancla HTML `a` (que crea hipervínculos), registrando ambos elementos como ampliamente disponibles en navegadores desde julio de 2015.[8][9] En el elemento `a`, MDN señala que `hreflang` sugiere el idioma humano de la URL enlazada, no conlleva ninguna funcionalidad integrada en el navegador y acepta los mismos valores de etiqueta de idioma que el atributo global `lang`.[9]

En la Búsqueda de Google, los sitios web combinan `hreflang` con la relación de enlace `alternate` para declarar versiones localizadas de una página en distintos idiomas o regiones, de modo que los resultados de búsqueda dirijan a los usuarios a la versión que coincide con su idioma o región.[6]

## Etiquetas de idioma BCP 47 y RFC 5646 utilizadas en hreflang

Los valores de hreflang utilizan etiquetas de idioma BCP 47 especificadas por IETF RFC 5646 («Tags for Identifying Languages»), publicado en septiembre de 2009.[2][5][9] Editado por A. Phillips y M. Davis, el RFC 5646 dejó obsoleto el RFC 4646 (que sustituyó a los RFC 3066 y RFC 1766) y se combina con el RFC 4647 para conformar BCP 47.[2][5]

Una etiqueta de idioma BCP 47 consta de una o más subetiquetas alfanuméricas separadas por guiones (`-`, U+002D), ordenadas como `language-extlang-script-region-variant-extension-privateuse`.[2][5] Cada tipo de subetiqueta se distingue por su longitud, posición y contenido de caracteres, lo que permite a los procesadores identificar categorías de subetiquetas sin una copia local del registro, salvo por un conjunto fijo de etiquetas heredadas (grandfathered) registradas durante la época del RFC 3066.[2]

| Tipo de subetiqueta | Formato | Estándar de origen | Ejemplos |
| --- | --- | --- | --- |
| Idioma principal | 2 a 3 letras (o 5 a 8 letras registradas) | ISO 639 | `en`, `es`, `ast`, `mas` |
| Idioma extendido | 3 letras tras una subetiqueta de macrolengua | ISO 639 | `zh-yue`, `ar-afb` |
| Escritura | 4 letras (introducida en el RFC 4646) | ISO 15924 | `zh-Hans`, `az-Latn` |
| Región | 2 letras o 3 dígitos | ISO 3166-1 / UN M.49 | `fr-CA`, `en-GB`, `de-CH`, `es-419` |
| Variante | 5 a 8 caracteres alfanuméricos, o 1 dígito más 3 alfanuméricos | Registro de IANA | Subetiquetas registradas de dialecto u ortografía |
| Extensión y uso privado | Singleton alfanumérico único (`x` reservado para uso privado) | RFC 5646 | Extensiones de un carácter; etiquetas de uso privado `x-` |

Todas las subetiquetas válidas se mantienen en un único archivo de texto plano, el IANA Language Subtag Registry, que tenía como fecha de archivo el 2026-11-18 a fecha de 2026-11-23.[4][5] El registro adopta un valor ISO 639 por idioma (seleccionando un código de dos letras cuando está disponible y, en caso contrario, un código de tres letras) y añadió más de 7000 códigos de tres letras de ISO 639-3 tras la publicación del RFC 5646.[5] Los registros contienen campos como `Type`, `Subtag`, `Description`, `Added`, `Suppress-Script`, `Scope`, `Deprecated` y `Preferred-Value`.[4][5] Por ejemplo, la entrada `bh` (lenguas bihari) lleva una fecha de obsolescencia del 2026-06-14 con `Preferred-Value: bih`.[4]

El W3C indica que las etiquetas de idioma no distinguen entre mayúsculas y minúsculas en HTML y XML; escribir las subetiquetas de idioma en minúsculas, las de escritura con mayúscula inicial y las de región alfabéticas en mayúsculas es únicamente una convención.[5] El W3C aconseja mantener las etiquetas de idioma lo más cortas posible, omitir subetiquetas de región o escritura cuando no aporten una distinción útil y seguir las entradas `Suppress-Script` como `Latn` para `en`, `es` y `fr`.[4][5] Para combinaciones heredadas de idioma más idioma extendido como `zh-yue` o `ar-afb`, el W3C señala que existe una subetiqueta independiente de idioma principal equivalente (`yue` o `afb`) y aconseja utilizar la subetiqueta independiente siempre que sea posible.[5]

## Métodos de implementación para anotaciones hreflang

La documentación de Google Search Central, a fecha de 2026-11-23, especifica tres métodos equivalentes para entregar anotaciones hreflang: elementos HTML `link`, encabezados HTTP `Link` y [sitemaps XML](https://mimirwiki.com/es/wiki/sitemaps).[6] Google trata los tres métodos por igual, y utilizar más de un método en las mismas páginas aumenta el trabajo de mantenimiento sin proporcionar ningún beneficio adicional en la Búsqueda.[6]

| Método | Ubicación y sintaxis | Caso de uso típico |
| --- | --- | --- |
| Elementos HTML `link` | Elementos `link` en `head` con `rel="alternate"`, `hreflang` y `href` | Páginas HTML sin control de sitemap ni de encabezados HTTP |
| Encabezados HTTP `Link` | Entradas de encabezado `Link` separadas por comas en respuestas GET con cada URL entre corchetes angulares, `rel="alternate"` y `hreflang` | Archivos que no son HTML, como los PDF |
| Sitemap XML | Entradas secundarias `xhtml:link` bajo cada elemento `loc` con el espacio de nombres XML `xhtml` declarado | Gestión centralizada de conjuntos de URL multiversión |

En los documentos HTML, los elementos `link` deben aparecer dentro de un elemento `head` bien formado, con un elemento `link` por cada variante, incluida la propia página.[6][8] En XHTML 1.0, los elementos vacíos como `link` requieren una barra diagonal final.[8] Google especifica que las anotaciones `hreflang` deben colocarse en elementos `link` dedicados y no deben combinarse con otros atributos de representación alternativa como `media` en un mismo elemento `link`.[6]

Para encabezados HTTP, IETF RFC 8288 («Web Linking», octubre de 2017, de M. Nottingham, que deja obsoleto el RFC 5988) define un modelo general de enlace web (contexto del enlace, tipo de relación del enlace, destino del enlace y atributos opcionales de destino), serializa los enlaces en el campo de encabezado HTTP `Link` e incorpora la sintaxis `Language-Tag` del RFC 5646.[3] Los tipos de relación de enlace registrados, incluido `alternate`, se mantienen en el registro Link Relations de IANA.[3] En la Búsqueda de Google, el encabezado `Link` devuelto en la respuesta GET de un recurso enumera cada versión localizada separada por comas, encerrando cada URL totalmente calificada entre corchetes angulares seguida de `rel="alternate"` y `hreflang`; cada versión del recurso devuelve el mismo encabezado.[6]

En un [sitemap XML](https://mimirwiki.com/es/wiki/sitemaps), cada versión localizada tiene su propio elemento `loc` emparejado con entradas secundarias `xhtml:link` que enumeran cada variante de idioma y región de esa página, incluida ella misma, con el espacio de nombres `xhtml` declarado.[6] Cuando una página tiene tres versiones, el sitemap contiene tres entradas `loc` y cada entrada alberga tres entradas secundarias `xhtml:link` idénticas.[6]

## Enlazado recíproco y reglas de URL para hreflang

La Búsqueda de Google aplica reglas estructurales compartidas en los elementos HTML `link`, los encabezados HTTP `Link` y los sitemaps XML para que cada URL de un grupo localizado verifique a las demás.[6]

- **Autorreferencia y conjuntos completos**: cada versión de idioma o región de una página debe incluirse a sí misma junto con todas las demás variantes, produciendo un conjunto de anotaciones idéntico en cada versión del grupo.[6]
- **Confirmación bidireccional**: si dos páginas no se apuntan mutuamente, Google ignora las anotaciones. Esta regla impide que un sitio web externo se designe arbitrariamente como versión alternativa de la página de otro sitio.[6]
- **Enlazado bidireccional parcial**: cuando mantener enlaces bidireccionales completos en todos los idiomas resulta poco práctico, se pueden omitir algunos idiomas en algunas páginas. Google sigue procesando los pares que se enlazan de forma bidireccional y aconseja enlazar las páginas de idiomas recién añadidas de forma bidireccional con los idiomas de origen o dominantes del sitio.[6]
- **URL totalmente calificadas**: cada URL alternativa debe incluir su esquema de transporte (`http` o `https`), como `https://example.com/foo`, excluyendo URL relativas al protocolo (`//example.com/foo`) y rutas relativas (`/foo`).[6]
- **Compatibilidad entre dominios**: las URL alternativas no necesitan pertenecer al mismo dominio.[6]
- **Idioma genérico comodín**: cuando varias URL regionales se dirigen a hablantes de un mismo idioma (como `en-IE`, `en-CA` y `en-AU`), Google aconseja proporcionar una entrada de idioma genérico (`en`) para usuarios de regiones no especificadas, la cual puede reutilizar una de las URL regionales.[6]

Google no utiliza subdominios específicos de idioma en las URL (como `en`, `en-gb`, `en-us` o `de`) para inferir el público objetivo de una página, por lo que cada idioma o región de destino debe asignarse explícitamente mediante anotaciones `hreflang`.[6]

## El valor hreflang x-default para páginas de respaldo

El valor hreflang `x-default` designa una URL de respaldo para visitantes cuyo idioma o región no coincide con ninguna de las variantes enumeradas explícitamente en una página.[6] Google Search Central Blog publicó un anuncio presentando `x-default` hreflang para páginas de destino internacionales en abril de 2013 y, posteriormente, incluyó una publicación de blog de mayo de 2023 titulada «How x-default can help you».[10]

La documentación de Google Search Central destaca `x-default` especialmente para páginas selectoras de idioma o país y para páginas de inicio que redirigen a los visitantes automáticamente.[6] En el ejemplo documentado por Google, un sitio web que ofrece páginas en inglés del Reino Unido (`en-GB`), inglés de Estados Unidos (`en-US`), inglés genérico (`en`) y alemán (`de`) asigna `hreflang="x-default"` a `https://www.example.com/`, una página de destino neutral que contiene selectores de idioma y región.[6]

El valor `x-default` es compatible con elementos HTML `link`, encabezados HTTP `Link` y sitemaps XML junto con etiquetas de idioma BCP 47 estándar.[6]

## Tratamiento de hreflang y sitios multilingües en la Búsqueda de Google

La Búsqueda de Google utiliza las anotaciones hreflang para reconocer variaciones localizadas de contenido equivalente y presentar la versión que coincide con la configuración de idioma o región de quien realiza la búsqueda.[6] Google distingue los sitios web multilingües (sitios que ofrecen contenido en más de un idioma, como versiones en inglés y francés para una empresa canadiense) de los sitios web multirregionales (sitios dirigidos explícitamente a usuarios de distintos países, como Canadá y Estados Unidos), señalando que un mismo sitio puede ser ambas cosas.[7]

La Búsqueda de Google no utiliza `hreflang`, el atributo HTML `lang` ni las URL para detectar el idioma de una página.[6][7] Google determina el idioma de la página algorítmicamente a partir del contenido visible en la página y aconseja utilizar un único idioma tanto para el contenido como para la navegación en cada página, evitando traducciones en paralelo.[6][7]

Google documenta tres escenarios habituales para `hreflang`: páginas en las que solo se traduce la plantilla (navegación y pie de página) mientras el contenido principal generado por los usuarios permanece en un solo idioma, páginas con pequeñas variaciones regionales en un mismo idioma (como inglés dirigido a Estados Unidos, Reino Unido e Irlanda) y páginas traducidas por completo a varios idiomas.[6] Las versiones localizadas de una página se tratan como duplicados únicamente cuando el contenido principal permanece sin traducir.[6]

Google aconseja asignar URL distintas a cada versión de idioma y enlazarlas mediante anotaciones `hreflang`.[7] Cambiar el contenido dinámicamente mediante cookies o la configuración del navegador puede impedir que Googlebot descubra todas las variaciones, porque Googlebot suele rastrear desde Estados Unidos y envía solicitudes HTTP sin un encabezado `Accept-Language`.[7] Google también desaconseja la redirección automática basada en el idioma supuesto del usuario, favoreciendo hipervínculos que permitan a los usuarios seleccionar las versiones manualmente, y admite palabras localizadas en las URL y nombres de dominio internacionalizados (IDN) utilizando codificación UTF-8 y el escapado de URL adecuado.[7]

## Preguntas frecuentes

### ¿Qué es hreflang?

hreflang es un atributo HTML y parámetro de anotación de enlaces que indica el idioma humano, y opcionalmente la región de destino, de un recurso web enlazado mediante etiquetas de idioma BCP 47. En la Búsqueda de Google, los sitios web combinan hreflang con la relación de enlace alternate para conectar versiones localizadas de una página. [2][6][9]

### ¿Qué métodos se pueden utilizar para implementar hreflang en la Búsqueda de Google?

A fecha de 2026-11-23, la Búsqueda de Google admite tres métodos equivalentes: elementos HTML link dentro del elemento head, encabezados de respuesta HTTP Link (útiles para archivos que no son HTML, como los PDF) y entradas secundarias xhtml:link en sitemaps XML. Utilizar más de un método al mismo tiempo no aporta ningún beneficio adicional en la búsqueda. [6]

### ¿Por qué los enlaces hreflang deben ser bidireccionales?

La Búsqueda de Google exige que cada página de un conjunto localizado haga referencia a sí misma y a todas las demás variantes, e ignora los pares que no se apunten mutuamente. Esta regla de confirmación impide que otro sitio web se designe arbitrariamente como versión alternativa de una página que no controla. [6]

### ¿Qué significa hreflang="x-default"?

El valor x-default identifica una página de respaldo para usuarios cuyo idioma o región no coincide con ninguna etiqueta hreflang enumerada explícitamente. Google anunció x-default en abril de 2013 y documenta su uso para páginas selectoras de idioma o país y páginas de inicio con redirección automática. [6][10]

### ¿Utiliza la Búsqueda de Google hreflang para detectar el idioma de una página?

No. La Búsqueda de Google no utiliza hreflang, el atributo HTML lang ni las URL para detectar el idioma de una página. Google determina el idioma de la página algorítmicamente a partir del contenido visible de la página y utiliza hreflang para identificar variaciones localizadas del mismo contenido. [6][7]

### ¿Cómo se formatean los códigos de idioma y región de hreflang?

Las etiquetas de idioma siguen IETF BCP 47 (RFC 5646) y combinan subetiquetas separadas por guiones del IANA Language Subtag Registry, comenzando con una subetiqueta de idioma principal ISO 639 de dos o tres letras, seguida opcionalmente de una subetiqueta de escritura ISO 15924 de cuatro letras o una subetiqueta de región ISO 3166-1 de dos letras o UN M.49 de tres dígitos. Las etiquetas de idioma no distinguen entre mayúsculas y minúsculas en HTML y XML. [2][4][5]

## Frases citables

- El WHATWG HTML Living Standard (actualizado por última vez el 2026-11-22) define hreflang como un atributo DOMString reflejado en el mixin de interfaz HyperlinkElementUtils. [1]
- MDN Web Docs indica que el atributo hreflang en el elemento HTML a sugiere el idioma humano de la URL enlazada, no tiene funcionalidad integrada y acepta los mismos valores que el atributo global lang. [9]
- IETF RFC 5646, publicado en septiembre de 2009 como parte de BCP 47, especifica la sintaxis de subetiquetas separadas por guiones para las etiquetas de idioma y deja obsoleto el RFC 4646. [2]
- Las subetiquetas válidas de idioma, escritura y región se mantienen en el IANA Language Subtag Registry, que tenía como fecha de archivo el 2026-11-18 a fecha de 2026-11-23. [4][5]
- IETF RFC 8288, publicado en octubre de 2017, especifica el campo de encabezado HTTP Link y hace referencia a la sintaxis Language-Tag del RFC 5646. [3]
- A fecha de 2026-11-23, la documentación de Google Search Central enumera los elementos HTML link, los encabezados HTTP Link y los sitemaps XML como tres métodos equivalentes para especificar anotaciones hreflang. [6]
- La Búsqueda de Google ignora las anotaciones hreflang entre dos páginas a menos que ambas páginas se enlacen mutuamente y cada página se incluya a sí misma junto con todas las versiones alternativas. [6]
- Google Search Central Blog anunció el valor hreflang x-default para páginas de destino internacionales en abril de 2013. [10]

## Cronología

- 2009-09: El IETF publica el RFC 5646 (Tags for Identifying Languages) como parte de BCP 47, dejando obsoleto el RFC 4646 y añadiendo más de 7000 códigos de idioma de tres letras de ISO 639-3 al IANA Language Subtag Registry. [2][5]
- 2013-04: Google Search Central Blog publica un anuncio que presenta x-default hreflang para páginas de destino internacionales. [10]
- 2015-07: Los elementos HTML link y a alcanzan la disponibilidad base en navegadores, según el seguimiento de MDN Web Docs. [8][9]
- 2017-10: El IETF publica el RFC 8288 (Web Linking), dejando obsoleto el RFC 5988 y definiendo la serialización del encabezado HTTP Link con la sintaxis de etiquetas de idioma del RFC 5646. [3]

## Fuentes

1. HTML Standard. WHATWG. publicado 2026-11-22. https://html.spec.whatwg.org/multipage/links.html (consultado 2026-11-23; tier 1: government or public registry)
2. RFC 5646: Tags for Identifying Languages. Internet Engineering Task Force (IETF). publicado 2009-09. https://www.rfc-editor.org/rfc/rfc5646.txt (consultado 2026-11-23; tier 1: government or public registry)
3. RFC 8288: Web Linking. Internet Engineering Task Force (IETF). publicado 2017-10. https://www.rfc-editor.org/rfc/rfc8288.txt (consultado 2026-11-23; tier 1: government or public registry)
4. IANA Language Subtag Registry. Internet Assigned Numbers Authority (IANA). publicado 2026-11-18. https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry (consultado 2026-11-23; tier 1: government or public registry)
5. Language tags in HTML and XML. World Wide Web Consortium (W3C). https://www.w3.org/International/articles/language-tags/ (consultado 2026-11-23; tier 1: government or public registry)
6. Localized Versions of your Pages | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/localized-versions (consultado 2026-11-23; tier 3: official site)
7. Managing Multi-Regional and Multilingual Sites | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (consultado 2026-11-23; tier 3: official site)
8. <link> HTML external resource link element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/link (consultado 2026-11-23; tier 3: official site)
9. <a> HTML anchor element - HTML | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/a (consultado 2026-11-23; tier 3: official site)
10. Introducing "x-default hreflang" for international landing pages | Google Search Central Blog | Google for Developers. Google Search Central Blog. publicado 2013-04. https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "hreflang." Versión 7ff99488, 2026-11-23. https://mimirwiki.com/es/wiki/hreflang
