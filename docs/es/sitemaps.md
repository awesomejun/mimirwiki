---
title: "Sitemaps"
subtitle: "Protocolo basado en XML para enumerar URL y metadatos de sitios web para rastreadores de motores de búsqueda"
canonical_url: https://mimirwiki.com/es/wiki/sitemaps
language: es
page_class: anchor
revision_sha256: a5e8631df0db4b7b5f5f868a344c0b8f94f7e92d35a5af06763d38bf60d64548
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/sitemaps.md
  txt: https://mimirwiki.com/es/wiki/sitemaps.txt
  json: https://mimirwiki.com/es/wiki/sitemaps.json
  jsonld: https://mimirwiki.com/es/wiki/sitemaps.jsonld
translations:
  en: https://mimirwiki.com/wiki/sitemaps
  ko: https://mimirwiki.com/ko/wiki/sitemaps
  ja: https://mimirwiki.com/ja/wiki/sitemaps
  zh: https://mimirwiki.com/zh/wiki/sitemaps
---

# Sitemaps

> Sitemaps es un protocolo XML patrocinado por Google, Yahoo y Microsoft que permite a los sitios web enumerar URL rastreables y metadatos para los motores de búsqueda. A fecha de 2026-11-23, la versión 0.9 limita cada archivo sitemap o de índice a 50 000 entradas y 50 MB sin comprimir, admite archivos RSS, Atom y de texto, y permite extensiones. Enumerar URL facilita su descubrimiento, pero la indexación sigue siendo opcional.

Sitemaps es un protocolo web basado en XML que permite a los operadores de sitios web informar a los motores de búsqueda sobre páginas, imágenes, vídeos y otros archivos disponibles para el rastreo, junto con metadatos como las fechas de última modificación. Patrocinada por Google, Inc., Yahoo, Inc. y Microsoft Corporation a través de sitemaps.org, la versión 0.9 del protocolo define esquemas XML para archivos sitemap individuales (urlset) y archivos de índice de sitemaps (sitemapindex), además de admitir fuentes de sindicación y listas de URL en texto plano. A fecha de 2026-11-23, cada archivo sitemap está limitado a 50 000 URL y 50 MB (52 428 800 bytes) sin comprimir, y las extensiones XML de los motores de búsqueda admiten contenidos especializados como imágenes y artículos de noticias. Publicar un sitemap ayuda a los rastreadores de los motores de búsqueda a descubrir URL, mientras que cada motor de búsqueda conserva plena discreción sobre si rastrear o indexar las entradas enumeradas.

**También conocido como:** Protocolo Sitemaps, Sitemap XML, sitemap.xml, Sitemaps 0.9

## Datos clave

- **Versión del protocolo:** 0.9 (http://www.sitemaps.org/schemas/sitemap/0.9) (al 2026-11-23) [1]
- **Patrocinadores:** Google, Inc., Yahoo, Inc. y Microsoft Corporation [3]
- **Límites por archivo:** 50 000 URL y 50 MB (52 428 800 bytes) sin comprimir (al 2026-11-23) [1]
- **Codificación de caracteres:** UTF-8 [1]
- **Licencia de la especificación:** Licencia Creative Commons Atribución-CompartirIgual (versión 2.5) [3]

## Datos básicos

- **Tipo:** Protocolo web para informar a los rastreadores de motores de búsqueda sobre URL rastreables [1]
- **Patrocinadores:** Google, Inc., Yahoo, Inc. y Microsoft Corporation [3]
- **Versión del protocolo:** 0.9 (al 2026-11-23) [1]
- **Espacio de nombres XML:** http://www.sitemaps.org/schemas/sitemap/0.9 (al 2026-11-23) [1]
- **Esquemas XML:** sitemap.xsd (sitemaps) y siteindex.xsd (archivos de índice de sitemaps) (al 2026-11-23) [2]
- **Formatos admitidos:** XML, RSS 2.0, Atom 0.3 o 1.0 y texto plano UTF-8 (al 2026-11-23) [1]
- **Límite de entradas por archivo:** 50 000 URL por sitemap; 50 000 sitemaps por índice de sitemaps (al 2026-11-23) [1]
- **Límite de tamaño por archivo:** 50 MB (52 428 800 bytes) sin comprimir; se admite compresión gzip (al 2026-11-23) [1]
- **Longitud máxima de loc:** Menos de 2048 caracteres (al 2026-11-23) [1]
- **Licencia de la especificación:** Licencia Creative Commons Atribución-CompartirIgual (versión 2.5) [3]
- **Cuota de índices en Google Search Console:** Hasta 500 archivos de índice de sitemaps por sitio (al 2025-12-10) [7]

## Descripción general del protocolo Sitemaps

El protocolo Sitemaps es una especificación basada en XML que permite a los operadores de sitios web informar a los motores de búsqueda sobre páginas, imágenes, vídeos y otros archivos disponibles para el rastreo.[1][5] Sitemaps.org está patrocinado por Google, Inc., Yahoo, Inc. y Microsoft Corporation, y los patrocinadores licencian sus derechos de autor sobre la especificación bajo la Licencia Creative Commons Atribución-CompartirIgual (versión 2.5).[3] Según las Condiciones de servicio de Sitemaps.org, ningún patrocinador está obligado a leer, indexar o utilizar ningún sitemap publicado, y cada patrocinador puede modificar o interrumpir su compatibilidad con el protocolo en cualquier momento.[3]

Además de enumerar URL, un sitemap puede comunicar relaciones y metadatos de archivos, incluidas las fechas de última modificación y las [versiones en idiomas alternativos](https://mimirwiki.com/es/wiki/hreflang) de las páginas.[5] Aunque el esquema XML es el formato principal, el protocolo Sitemaps y Google Search también aceptan fuentes de sindicación y listas de URL en texto plano.[1][6]

- **Sitemap XML**: Formato extensible capaz de transportar metadatos de imágenes, vídeos, noticias y versiones localizadas de páginas. Muchos sistemas de gestión de contenidos (CMS) generan sitemaps XML automáticamente o mediante complementos, aunque mantener las asignaciones XML en sitios grandes o con cambios rápidos puede resultar complejo.[1][6]
- **Fuentes RSS, mRSS y Atom**: Sitemaps.org admite RSS 2.0 y Atom 0.3 o 1.0, interpretando el campo `link` como la URL y el campo opcional `pubDate` (RSS) o `updated` (Atom) como la fecha de modificación.[1] Las fuentes suelen enumerar únicamente URL recientes y deben colocarse en el directorio de nivel más alto que se desee rastrear.[1] Google admite fuentes RSS, mRSS y Atom 1.0 para HTML, contenido textual indexable y metadatos de vídeo, mientras que los metadatos de imágenes y noticias requieren extensiones XML.[6]
- **Sitemap de texto plano**: Archivo de texto UTF-8 que contiene una URL completamente cualificada por línea, sin encabezado, pie de página ni metadatos adicionales, limitado a HTML y otras páginas textuales indexables.[1][6]

Los sistemas de gestión de contenidos como WordPress, Wix y Blogger suelen generar un sitemap de forma automática.[5] Según la documentación de Google Search Central actualizada el 2025-12-10, los sitemaps resultan especialmente útiles para sitios grandes en los que el enlazado interno puede pasar por alto páginas nuevas, sitios nuevos con pocos enlaces externos y sitios con abundante contenido de vídeo, imágenes o Google News.[5] Por el contrario, los sitios pequeños con aproximadamente 500 páginas o menos que están enlazados de forma exhaustiva desde la página de inicio y tienen pocas páginas multimedia o de noticias pueden no necesitar un sitemap.[5]

## Formato XML y elementos de Sitemaps

El protocolo Sitemaps 0.9 define un formato de documento XML codificado en UTF-8 bajo el espacio de nombres `http://www.sitemaps.org/schemas/sitemap/0.9`.[1] Se proporcionan dos archivos oficiales de definición de esquema XML (XSD) para la validación: `http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd` para archivos sitemap y `http://www.sitemaps.org/schemas/sitemap/0.9/siteindex.xsd` para archivos de índice de sitemaps.[2]

Todos los valores XML, incluidas las URL, deben cumplir con RFC 3986 (URI), RFC 3987 (IRI) y el estándar XML, empleando tanto codificación porcentual de URL para caracteres no ASCII como códigos de escape de entidades XML para cinco caracteres reservados: et comercial (`&` como `&amp;`), comilla simple (`'` como `&apos;`), comilla doble (`"` como `&quot;`), signo mayor que (`>` como `&gt;`) y signo menor que (`<` como `&lt;`).[1][2] A fecha de 2026-11-23, el protocolo Sitemaps 0.9 define seis elementos principales para un archivo sitemap.[1]

| Elemento | Requisito | Reglas de valor y función |
| --- | --- | --- |
| `urlset` | Obligatorio | Elemento raíz que encapsula el archivo y declara el espacio de nombres XML del protocolo 0.9.[1] |
| `url` | Obligatorio | Elemento padre para cada entrada de URL; todas las demás etiquetas aparecen como sus elementos hijos.[1] |
| `loc` | Obligatorio | URL de página completamente cualificada que comienza con el protocolo (como `http` o `https`), termina con una barra diagonal final si el servidor la requiere y tiene menos de 2048 caracteres.[1][2] |
| `lastmod` | Opcional | Fecha de última modificación de la página en formato W3C Datetime (`YYYY-MM-DD` o fecha y hora ISO 8601 completa con zona horaria). Registra la fecha de actualización de la página, independiente del momento de generación del sitemap y de las cabeceras HTTP `If-Modified-Since` (304).[1][2] |
| `changefreq` | Opcional | Estimación general de la frecuencia probable de cambio de la página. Los valores válidos son `always` (documentos que cambian en cada acceso), `hourly`, `daily`, `weekly`, `monthly`, `yearly` y `never` (URL archivadas).[1] |
| `priority` | Opcional | Importancia relativa de la URL en comparación con otras URL del mismo sitio, en una escala de `0.0` a `1.0` con un valor predeterminado de `0.5`.[1] |

La especificación y la documentación de Google Search establecen reglas adicionales para las URL enumeradas. Las entradas deben ser URL completas y absolutas porque las rutas relativas como `/mypage.html` no son válidas, y Google intenta rastrear las URL exactamente como están escritas.[2][6] Los operadores de sitios deben incluir únicamente una versión de protocolo cuando existan tanto URL HTTP como HTTPS, eliminar los identificadores de sesión para evitar rastreos incompletos y redundantes, e incluir tanto la URL del conjunto de marcos (frameset) como la del contenido del marco en las páginas con marcos.[2] El orden de las URL dentro de un sitemap no influye en cómo las procesan los motores de búsqueda.[2] Google señala que los sitemaps pueden influir en la selección de la URL canónica y, cuando existen URL separadas para escritorio y dispositivos móviles, recomienda enumerar una sola versión o anotar ambas versiones.[6]

## Archivos de índice de sitemaps y límites de tamaño

Los archivos Sitemaps están limitados a fecha de 2026-11-23 a 50 000 URL y 50 MB (52 428 800 bytes) sin comprimir por archivo tanto en formato XML como en texto plano.[1][2][6] Para reducir el ancho de banda, los operadores de sitios pueden comprimir los archivos sitemap mediante gzip; el archivo sin comprimir debe mantenerse dentro del límite de 50 MB, y las preguntas frecuentes de sitemaps.org especifican gzip para los sitemaps comprimidos.[1][2]

Cuando un sitio supera las 50 000 URL o los 50 MB, las URL deben dividirse en varios archivos sitemap, que luego pueden agruparse dentro de uno o más archivos de índice de sitemaps.[1][2][7] Un archivo de índice de sitemaps utiliza la misma codificación UTF-8 y el mismo espacio de nombres `http://www.sitemaps.org/schemas/sitemap/0.9` que un sitemap individual.[1][7] A fecha de 2026-11-23, cada archivo de índice de sitemaps puede enumerar hasta 50 000 sitemaps, no debe superar los 50 MB (52 428 800 bytes) sin comprimir y admite compresión gzip.[1][2][7]

Un archivo de índice de sitemaps utiliza cuatro elementos XML definidos en el protocolo 0.9.[1][7]

- `sitemapindex` (obligatorio): Elemento raíz que encierra todas las entradas de sitemap enumeradas.[1][7]
- `sitemap` (obligatorio): Elemento padre de cada sitemap individual y único hijo directo de `sitemapindex`.[1][7]
- `loc` (obligatorio): URL con entidades escapadas que identifica la ubicación de un sitemap, que puede ser un sitemap XML, un archivo RSS, un archivo Atom o un archivo de texto plano.[1][7]
- `lastmod` (opcional): Marca temporal en formato W3C Datetime que indica cuándo se modificó el propio archivo sitemap referenciado, con independencia de cuándo cambiaron las páginas individuales enumeradas dentro de ese sitemap.[1][7]

Proporcionar `lastmod` dentro de un índice de sitemaps habilita la obtención incremental de sitemaps, lo que permite a los rastreadores recuperar únicamente los sitemaps actualizados recientemente.[1][2] En sitios con decenas de millones de URL, agrupar las URL que cambian con frecuencia en un conjunto reducido de sitemaps y marcarlas con `lastmod` en el índice de sitemaps ayuda a los motores de búsqueda a descubrir actualizaciones con rapidez.[1][2] A fecha de 2025-12-10, Google Search Console permite a los propietarios de sitios enviar hasta 500 archivos de índice de sitemaps por sitio, y enviar sitemaps separados también facilita el seguimiento del rendimiento por sitemap en Search Console.[6][7]

## Ubicación, alcance y descubrimiento de archivos sitemap

La ubicación de un archivo Sitemaps determina qué URL son válidas dentro de dicho archivo.[1] Según la regla de prefijo de ruta del protocolo, un sitemap alojado en `http://example.com/catalog/sitemap.xml` puede enumerar URL que comiencen por `http://example.com/catalog/`, mientras que las URL situadas en directorios hermanos como `http://example.com/images/` o bajo un esquema diferente como `https://example.com/catalog/page1.php` se consideran no válidas y se descartan.[1] Todas las URL de un sitemap deben compartir el mismo protocolo, host y número de puerto que el archivo sitemap; un sitemap en `http://www.example.com/sitemap.xml` no puede incluir URL de `http://subdomain.example.com`, y un sitemap en `http://www.example.com:100/sitemap.xml` exige ese número de puerto en cada URL enumerada.[1][2]

Dado que el alcance de ruta se aplica a los descendientes del directorio del sitemap, sitemaps.org y Google aconsejan colocar los sitemaps en el directorio raíz del servidor web (`http://example.com/sitemap.xml`) para que una única ubicación cubra todo el sitio.[1][2][6] Siguen permitiéndose sitemaps separados por directorio cuando las políticas de seguridad de una organización compartimentan los permisos de escritura por directorio.[1][2] En Google Search, enviar un sitemap directamente a través de Google Search Console elimina la restricción del directorio principal.[6]

Los archivos de índice de sitemaps siguen reglas paralelas de host y jerarquía: los sitemaps referenciados deben residir en el mismo host y en el mismo directorio que el archivo de índice de sitemaps o en un subdirectorio más profundo.[1][7] El envío entre hosts, en el que un único host sirve sitemaps para varios hosts distintos, requiere demostrar la propiedad de cada host de destino.[1][7]

Una vez publicado un sitemap, las preguntas frecuentes de sitemaps.org describen tres métodos para notificar a los motores de búsqueda: envío directo mediante herramientas de los motores de búsqueda, envío de notificaciones ping a los motores de búsqueda y declaración de la ubicación del sitemap en [robots.txt](https://mimirwiki.com/es/wiki/robots-txt).[2] La especificación del Protocolo de exclusión de robots, publicada por la Internet Engineering Task Force (IETF) como RFC 9309 en septiembre de 2022, señala en la Sección 2.2 (Sintaxis formal) que los implementadores de analizadores de `robots.txt` pueden definir líneas adicionales como Sitemaps.[4] En cuanto a las notificaciones ping, el Google Search Central Blog publicó un anuncio en junio de 2023 indicando que el punto de conexión ping para sitemaps de Google iba a desaparecer.[10]

## Extensiones de Sitemaps para imágenes, noticias y otros contenidos

Los archivos XML de Sitemaps admiten extensiones de protocolo mediante espacios de nombres XML adicionales para tipos de contenido especializados.[1][6] Google Search Central documenta extensiones para imágenes, artículos de noticias, vídeos y [versiones localizadas de páginas](https://mimirwiki.com/es/wiki/hreflang), que pueden colocarse en sitemaps dedicados o combinarse dentro de un sitemap XML existente.[5][6][8][9]

| Extensión | Espacio de nombres XML | Elementos obligatorios | Límites documentados |
| --- | --- | --- | --- |
| Sitemaps 0.9 principal | `http://www.sitemaps.org/schemas/sitemap/0.9` | `urlset`, `url`, `loc` (o `sitemapindex`, `sitemap`, `loc`) | 50 000 URL o sitemaps; 50 MB sin comprimir[1][7] |
| Sitemaps de imágenes de Google | `http://www.google.com/schemas/sitemap-image/1.1` | `image:image`, `image:loc` | Hasta 1000 etiquetas `image:image` por `url`[8] |
| Sitemaps de noticias de Google | `http://www.google.com/schemas/sitemap-news/0.9` | `news:news`, `news:publication`, `news:name`, `news:language`, `news:publication_date` | 1 `news:news` por `url`; hasta 1000 etiquetas `news:news` por sitemap; artículos de los últimos 2 días[9] |

La extensión de sitemap de imágenes de Google ayuda a Googlebot a descubrir imágenes que de otro modo podrían pasar desapercibidas, como las cargadas mediante JavaScript.[8] A fecha de 2025-12-10, cada elemento `url` puede contener hasta 1000 elementos hijos `image:image`, cada uno con un elemento obligatorio `image:loc` con la URL.[8] Las URL de imágenes pueden alojarse en un dominio distinto, como una [red de distribución de contenidos](https://mimirwiki.com/es/wiki/content-delivery-network), siempre que ambos dominios estén verificados en Google Search Console y `robots.txt` permita el rastreo.[8] Google eliminó cuatro etiquetas de imagen previamente documentadas (`image:caption`, `image:geo_location`, `image:title` e `image:license`) de su documentación sobre sitemaps de imágenes, tras un aviso publicado en mayo de 2022 en el Google Search Central Blog que anunciaba la retirada de determinadas etiquetas de extensión de sitemaps.[8][10]

La extensión de sitemap de noticias de Google transmite metadatos de artículos para editores de noticias, quienes pueden ampliar un sitemap general o mantener un sitemap de noticias dedicado para un seguimiento independiente en Search Console.[9] Los editores actualizan su sitemap de noticias existente a medida que se publican nuevos artículos, y Google News rastrea los sitemaps de noticias con la misma frecuencia que el resto del sitio.[9] Las entradas deben limitarse a artículos publicados en los últimos dos días, tras lo cual se eliminan las URL más antiguas o sus bloques `news:news`; si un sitemap de noticias queda vacío temporalmente, Search Console muestra una advertencia de Empty Sitemap para confirmación sin afectar a Google Search.[9] Cada `url` acepta una etiqueta `news:news`, y un único sitemap puede contener hasta 1000 etiquetas `news:news`.[9] Dentro de `news:publication`, `news:name` debe coincidir con el nombre de la publicación en `news.google.com` omitiendo el texto entre paréntesis, y `news:language` utiliza un código ISO 639 de dos o tres letras, con `zh-cn` para chino simplificado y `zh-tw` para chino tradicional.[9] La etiqueta `news:publication_date` registra la fecha de publicación original en el sitio en formato W3C Datetime (`YYYY-MM-DD`, `YYYY-MM-DDThh:mmTZD` o `YYYY-MM-DDThh:mm:ssTZD`).[9]

Google Search Central también señala que las entradas de vídeo en sitemaps pueden especificar la duración del vídeo, la valoración y la clasificación de idoneidad por edad, y que las fuentes RSS, mRSS y Atom 1.0 pueden suministrar metadatos de vídeo junto con HTML y contenido textual indexable.[5][6]

## Tratamiento de metadatos y límites de Sitemaps por los motores de búsqueda

Los motores de búsqueda gestionan de forma distinta las etiquetas opcionales de metadatos de Sitemaps, y el protocolo Sitemaps no impone a los rastreadores ninguna obligación de leer o indexar las URL enumeradas.[1][3] Mientras que `urlset`, `url` y `loc` son obligatorios en el protocolo 0.9, sitemaps.org indica que la compatibilidad con los elementos opcionales (`lastmod`, `changefreq` y `priority`) varía según el motor de búsqueda y remite a los editores a la documentación de cada proveedor.[1][2]

Dentro de la propia especificación del protocolo, `changefreq` se define como una indicación general de rastreo.[1] Los rastreadores pueden visitar páginas etiquetadas como `hourly` con menos frecuencia que una vez por hora, visitar páginas etiquetadas como `yearly` con más frecuencia que una vez al año y comprobar periódicamente URL etiquetadas como `never` en busca de cambios inesperados.[1] Del mismo modo, `priority` expresa la importancia relativa de las URL dentro de un mismo sitio en una escala de `0.0` a `1.0` (valor predeterminado `0.5`); no compara páginas entre dominios diferentes, asignar valores altos a todas las URL no aporta diferenciación relativa, y tanto la especificación como las preguntas frecuentes establecen que no se espera que `priority` afecte al posicionamiento en los resultados de búsqueda.[1][2]

En cuanto a `lastmod`, el protocolo señala que la etiqueta es independiente de las cabeceras de servidor HTTP `If-Modified-Since` (304) y que los motores de búsqueda pueden combinar o evaluar ambas señales de forma diferente.[1] Las preguntas frecuentes de sitemaps.org indican que proporcionar marcas temporales de modificación precisas para archivos estáticos o estimaciones basadas en datos para páginas dinámicas ayuda a los rastreadores a omitir URL sin cambios, reduciendo el ancho de banda y la carga de CPU del servidor.[2] En los archivos de índice de sitemaps, la documentación de Google Search Central actualizada el 2025-12-10 afirma que `lastmod` puede ayudar a Google a programar el rastreo de los sitemaps.[7]

En todos los formatos, Google declara que no tiene preferencia entre sitemaps XML, fuentes RSS/mRSS/Atom 1.0 y sitemaps de texto plano.[6] Google trata los sitemaps como una ayuda para el descubrimiento de URL y una señal que puede influir en la selección de la URL canónica, aunque señala explícitamente que enumerar una URL en un sitemap no garantiza su rastreo ni su indexación.[5][6] Los sitemaps funcionan junto con [robots.txt](https://mimirwiki.com/es/wiki/robots-txt), que comunica los permisos de acceso de los rastreadores según el RFC 9309, y los rastreadores deben contar con permiso en `robots.txt` para acceder al contenido enumerado en los sitemaps.[4][8] Según las Condiciones de servicio de Sitemaps.org, Google, Yahoo y Microsoft se reservan cada uno el derecho de utilizar el protocolo parcialmente o interrumpir su compatibilidad en cualquier servicio.[3]

## Preguntas frecuentes

### ¿Qué es un sitemap?

Un sitemap es un archivo legible por máquina en el que un sitio web enumera páginas, vídeos, imágenes y otros archivos disponibles para el rastreo, junto con metadatos como fechas de última modificación y versiones en idiomas alternativos. Los motores de búsqueda leen los sitemaps para descubrir y rastrear URL de manera más eficiente. [1][5]

### ¿Cuáles son los límites de URL y de tamaño de archivo para un sitemap?

A fecha de 2026-11-23, cada archivo sitemap XML o de texto puede incluir hasta 50 000 URL y no debe superar los 50 MB (52 428 800 bytes) sin comprimir. Un archivo de índice de sitemaps puede hacer referencia a hasta 50 000 sitemaps dentro del mismo límite de 50 MB sin comprimir, y los archivos pueden comprimirse con gzip. [1][2][6][7]

### ¿Qué elementos XML son obligatorios en un sitemap y en un archivo de índice de sitemaps?

Un sitemap XML estándar requiere el elemento raíz urlset que declara el espacio de nombres 0.9, un elemento padre url para cada entrada y un elemento hijo loc que contiene la URL completamente cualificada. Un archivo de índice de sitemaps requiere los elementos sitemapindex, sitemap y loc, con lastmod disponible como etiqueta hija opcional. [1][7]

### ¿La etiqueta priority modifica el posicionamiento en los resultados de búsqueda?

Según el protocolo Sitemaps y sus preguntas frecuentes, priority indica la importancia de una URL en relación con otras URL del mismo sitio en una escala de 0.0 a 1.0 (valor predeterminado 0.5). No compara páginas entre sitios diferentes y no se espera que modifique el posicionamiento en los resultados de búsqueda. [1][2]

### ¿Cómo descubren los motores de búsqueda un archivo sitemap?

Las preguntas frecuentes de sitemaps.org describen el envío directo a los motores de búsqueda, el envío de notificaciones ping a los motores de búsqueda y la inclusión de la ubicación del sitemap en robots.txt, y el RFC 9309 señala que los analizadores de robots.txt pueden admitir líneas Sitemaps. En junio de 2023, el Google Search Central Blog anunció que el punto de conexión ping para sitemaps de Google iba a desaparecer, mientras que Google Search Console sigue siendo un canal de envío directo. [2][4][6][10]

### ¿Todo sitio web necesita un sitemap?

Según la documentación de Google Search Central actualizada el 2025-12-10, los sitemaps son útiles para sitios grandes, sitios nuevos con pocos enlaces externos y sitios con abundante contenido de vídeo, imágenes o noticias. Los sitios pequeños de aproximadamente 500 páginas o menos que están enlazados internamente de forma exhaustiva y carecen de amplias secciones multimedia o de noticias pueden no necesitar un sitemap. [5]

## Frases citables

- Sitemaps.org está patrocinado por Google, Inc., Yahoo, Inc. y Microsoft Corporation, y su especificación de protocolo está licenciada bajo la Licencia Creative Commons Atribución-CompartirIgual (versión 2.5). [3]
- A fecha de 2026-11-23, el protocolo Sitemaps 0.9 requiere codificación UTF-8, el espacio de nombres XML http://www.sitemaps.org/schemas/sitemap/0.9 y los elementos urlset, url y loc, con valores de loc de menos de 2048 caracteres. [1]
- A fecha de 2026-11-23, un único archivo sitemap puede contener como máximo 50 000 URL y no debe superar los 50 MB (52 428 800 bytes) sin comprimir, y un archivo de índice de sitemaps puede enumerar como máximo 50 000 sitemaps dentro del mismo límite de 50 MB sin comprimir. [1][2]
- El protocolo Sitemaps 0.9 proporciona esquemas de validación XML en sitemap.xsd y siteindex.xsd, y admite RSS 2.0, Atom 0.3 o 1.0 y archivos de texto plano UTF-8 como formatos alternativos. [1][2]
- El RFC 9309, publicado por el IETF en septiembre de 2022, señala en su sintaxis formal ABNF para robots.txt que los implementadores de analizadores sintácticos pueden definir líneas adicionales como Sitemaps. [4]
- A fecha de 2025-12-10, Google Search Console permite hasta 500 archivos de índice de sitemaps por sitio, y enviar un sitemap a través de Search Console elimina la restricción predeterminada de alcance del directorio principal. [6][7]
- A fecha de 2025-12-10, la extensión de sitemap de imágenes de Google (http://www.google.com/schemas/sitemap-image/1.1) permite hasta 1000 etiquetas image:image por elemento url, y Google ha eliminado image:caption, image:geo_location, image:title e image:license de su documentación. [8]
- La extensión de sitemap de noticias de Google (http://www.google.com/schemas/sitemap-news/0.9) permite hasta 1000 entradas news:news por sitemap y restringe las entradas a artículos publicados en los últimos dos días. [9]

## Cronología

- 2008-02-27: Sitemaps.org actualiza sus Condiciones de servicio, nombrando a Google, Inc., Yahoo, Inc. y Microsoft Corporation como patrocinadores y especificando la licencia Creative Commons Atribución-CompartirIgual 2.5 para la especificación. [3]
- 2016-11-21: Sitemaps.org actualiza sus preguntas frecuentes documentando los límites de 50 MB (52 428 800 bytes) y 50 000 URL junto con los esquemas XML sitemap.xsd y siteindex.xsd. [2]
- 2022-05: Google Search Central Blog publica un aviso anunciando la eliminación de determinadas etiquetas de extensión de sitemaps. [8][10]
- 2022-09: El IETF publica el RFC 9309 (Protocolo de exclusión de robots), señalando en su sintaxis formal ABNF que los analizadores de robots.txt pueden definir líneas adicionales como Sitemaps. [4]
- 2023-06: Google Search Central Blog publica un anuncio indicando que el punto de conexión ping para sitemaps de Google va a desaparecer. [10]
- 2025-12-10: Google Search Central actualiza su documentación sobre la descripción general de Sitemaps, los archivos de índice de sitemaps y los sitemaps de imágenes. [5][7][8]

## Fuentes

1. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (consultado 2026-11-23; tier 3: official site)
2. sitemaps.org - FAQ. sitemaps.org. publicado 2016-11-21. https://www.sitemaps.org/faq.html (consultado 2026-11-23; tier 3: official site)
3. sitemaps.org - Terms of service. sitemaps.org. publicado 2008-02-27. https://www.sitemaps.org/terms.html (consultado 2026-11-23; tier 3: official site)
4. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (consultado 2026-11-23; tier 1: government or public registry)
5. What Is a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. publicado 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview (consultado 2026-11-23; tier 3: official site)
6. Build and Submit a Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (consultado 2026-11-23; tier 3: official site)
7. Manage Your Sitemaps With Sitemap Index Files | Google Search Central | Documentation | Google for Developers. Google Search Central. publicado 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/large-sitemaps (consultado 2026-11-23; tier 3: official site)
8. Image Sitemaps | Google Search Central | Documentation | Google for Developers. Google Search Central. publicado 2025-12-10. https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps (consultado 2026-11-23; tier 3: official site)
9. Create a News Sitemap | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap (consultado 2026-11-23; tier 3: official site)
10. Sitemaps ping endpoint is going away | Google Search Central Blog | Google for Developers. Google Search Central Blog. publicado 2023-06. https://developers.google.com/search/blog/2023/06/sitemaps-lastmod-ping (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Sitemaps." Versión a5e8631d, 2026-11-23. https://mimirwiki.com/es/wiki/sitemaps
