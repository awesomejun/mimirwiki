---
title: "robots.txt"
subtitle: "Archivo de texto plano del Protocolo de exclusión de robots (RFC 9309) que indica a los rastreadores web a qué URI pueden acceder"
canonical_url: https://mimirwiki.com/es/wiki/robots-txt
language: es
page_class: anchor
revision_sha256: 2a33e0a7210056a9e09747765244ca41242e7aaf73a7c10cadf1850d6b18dc73
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/es/wiki/robots-txt.md
  txt: https://mimirwiki.com/es/wiki/robots-txt.txt
  json: https://mimirwiki.com/es/wiki/robots-txt.json
  jsonld: https://mimirwiki.com/es/wiki/robots-txt.jsonld
translations:
  en: https://mimirwiki.com/wiki/robots-txt
  ko: https://mimirwiki.com/ko/wiki/robots-txt
  ja: https://mimirwiki.com/ja/wiki/robots-txt
  zh: https://mimirwiki.com/zh/wiki/robots-txt
---

# robots.txt

> robots.txt es un archivo de texto plano ubicado en la ruta raíz de un sitio web (/robots.txt) conforme al Protocolo de exclusión de robots (RFC 9309) para indicar a los rastreadores automatizados a qué URI pueden o no acceder. Martijn Koster definió originalmente esta convención en 1994 y el IETF la estandarizó en septiembre de 2022. Sus reglas tienen carácter consultivo y no proporcionan autorización de acceso.

robots.txt es un archivo de texto plano codificado en UTF-8 alojado en la ruta de nivel superior /robots.txt de un servicio web o FTP para especificar a qué URI pueden o no acceder los clientes automatizados, conocidos como rastreadores, según el Protocolo de exclusión de robots (REP). Martijn Koster documentó originalmente esta convención en junio de 1994 tras un consenso en una lista de correo, y el Grupo de Trabajo de Ingeniería de Internet (IETF) la publicó como RFC 9309 en la vía de estándares en septiembre de 2022. El archivo organiza grupos de User-agent emparejados con reglas de ruta Allow y Disallow, junto con registros opcionales como Sitemap. El RFC 9309 define las reglas de robots.txt como solicitudes consultivas que se pide respetar a los rastreadores, y el protocolo no ofrece autorización de acceso ni aplicación técnica obligatoria.

**También conocido como:** /robots.txt, Protocolo de exclusión de robots, REP, RFC 9309, Estándar de exclusión de robots

## Datos clave

- **Estándar:** RFC 9309 (vía de estándares del IETF, septiembre de 2022) [1]
- **Autor original y fecha:** Martijn Koster (consenso en lista de correo del 1994-06-30) [4]
- **Ubicación canónica:** /robots.txt en la raíz del servicio (UTF-8, text/plain) [1]
- **Directivas principales:** User-agent, Allow, Disallow (además de Sitemap opcional) [1]
- **Límite de tamaño de archivo en Google:** 500 KiB; el contenido posterior al límite se ignora (al 2026-11-23) [6]

## Datos básicos

- **Nombre del protocolo:** Protocolo de exclusión de robots (REP) [1]
- **Especificación del IETF:** RFC 9309 (Estándar propuesto, septiembre de 2022) [3]
- **Autores del RFC 9309:** Martijn Koster, Gary Illyes, Henner Zeller, Lizzi Sassman [3]
- **Fecha del consenso original:** 1994-06-30 [4]
- **Ruta del archivo:** /robots.txt (todo en minúsculas, directorio de nivel superior) [1]
- **Codificación y tipo de medio:** UTF-8, text/plain [1]
- **Directivas estandarizadas:** User-agent, Allow, Disallow [1]
- **Caracteres especiales:** # (comentario), * (comodín), $ (fin de coincidencia) [1]
- **Límite de tamaño de archivo en Google:** 500 KiB (al 2026-11-23) [6]
- **Duración predeterminada de caché en Google:** Hasta 24 horas (al 2026-11-23) [6]
- **Analizador de referencia en C++:** github.com/google/robotstxt (licencia Apache-2.0) [8]
- **Grupo de trabajo relacionado del IETF:** AI Preferences (aipref), activo bajo charter-ietf-aipref-01 (al 2026-11-23) [2]

## Qué es robots.txt y cómo se originó

robots.txt es un archivo de texto plano que se sirve en la ruta de nivel superior de un sitio web o un host FTP conforme al Protocolo de exclusión de robots (REP) para indicar a qué URI pueden acceder los rastreadores automatizados.[1][5] Los propietarios de servicios publican el archivo para que los clientes automatizados, como los rastreadores de motores de búsqueda que recorren enlaces para indexar contenido, puedan determinar qué rutas evitar antes de solicitar recursos del sitio.[1][7]

Martijn Koster documentó originalmente el protocolo en "A Standard for Robot Exclusion", donde registró un consenso alcanzado el 30 de junio de 1994 en la lista de correo `robots` (`robots-request@nexor.co.uk`) y debatido en la lista de correo técnica de la World Wide Web (`www-talk@info.cern.ch`).[1][4] El documento respondía a incidentes ocurridos en 1993 y 1994 en los que robots web (también llamados wanderers o spiders) enviaban solicitudes rápidas que sobrecargaban servidores, descargaban repetidamente los mismos archivos o recorrían árboles virtuales profundos, contenido temporal o duplicado y scripts CGI con efectos secundarios como votaciones.[4] Se eligió un único archivo en `/robots.txt` porque cualquier servidor web existente podía servirlo sin configuración adicional, los rastreadores podían obtener la política en una sola solicitud y el nombre de archivo se ajustaba a las reglas de nomenclatura de los sistemas operativos con un riesgo mínimo de colisión.[4]

Durante 25 años, REP funcionó como un estándar informal de facto sin respaldo formal de un organismo de estandarización, documentado en la especificación de 1994 y en un Internet-Draft de 1997 titulado "A Method for Web Robots Control".[4][5][8] El formato original de 1994 incluía únicamente los campos `User-agent` y `Disallow` y omitía el campo `Allow` y la coincidencia con comodines.[4][5] En septiembre de 2022, el Grupo de Trabajo de Ingeniería de Internet (IETF) publicó el RFC 9309 ("Robots Exclusion Protocol") como Estándar propuesto (Proposed Standard) dentro de la vía de estándares (Standards Track), redactado por Martijn Koster, Gary Illyes, Henner Zeller y Lizzi Sassman a partir del borrador individual `draft-koster-rep`, con Murray Kucherawy como director de área responsable.[1][3] El RFC 9309 añadió una gramática formal de protocolo, estandarizó `Allow` y los caracteres comodín, y especificó reglas para el manejo de errores y el almacenamiento en caché.[1]

## Ubicación, formato y alcance del archivo robots.txt

Un archivo robots.txt debe colocarse en la ruta `/robots.txt`, completamente en minúsculas, en el directorio de nivel superior de un servicio, siguiendo la forma de URI `scheme:[//authority]/robots.txt` (como `https://www.example.com/robots.txt` o `ftp://ftp.example.com/robots.txt`).[1][5] El RFC 9309 exige que el archivo esté codificado en UTF-8 (RFC 3629) y se sirva con el tipo de medio de Internet `text/plain` (RFC 2046), utilizando saltos de línea CR, LF o CRLF.[1][6] En la implementación de la Búsqueda de Google, los protocolos admitidos son HTTP y HTTPS (obtenidos mediante una solicitud HTTP GET no condicional) y FTP (obtenido mediante un comando anónimo `RETR`).[6]

Las reglas dentro de un archivo robots.txt se aplican únicamente al host, protocolo y número de puerto exactos desde los que se obtiene el archivo.[6] Según documenta Google, el alcance sigue estos límites:[6]

- **Subdominios y subdirectorios**: un archivo en `https://example.com/robots.txt` no cubre `https://other.example.com/`, y un archivo colocado en un subdirectorio como `/folder/robots.txt` no es válido.
- **Protocolos y puertos**: las reglas de `https://example.com/` no se aplican a `http://example.com/` ni a `ftp://example.com/`; los puertos estándar (80 para HTTP, 443 para HTTPS y 21 para FTP) coinciden con los nombres de host predeterminados, mientras que los puertos no estándar como `:8181` requieren su propio archivo.
- **IDN y direcciones IP**: los nombres de dominio internacionalizados (IDN) equivalen a sus formas en Punycode (RFC 3492), y un archivo alojado en un nombre de host basado en dirección IP se aplica únicamente al rastreo realizado mediante esa dirección IP.

Al 2026-11-23, Google aplica un tamaño máximo de archivo robots.txt de 500 kibibytes (KiB) e ignora cualquier contenido que supere ese límite.[6] El analizador de Google también ignora las líneas no válidas, incluida una marca de orden de bytes (BOM) de Unicode al inicio, y aplica todas las reglas válidas encontradas en la respuesta.[6]

## Directivas, sintaxis y reglas de coincidencia de robots.txt

La sintaxis de robots.txt definida en el RFC 9309 utiliza la forma aumentada de Backus-Naur (ABNF, RFC 5234) para organizar líneas clave-valor en grupos formados por una o más líneas `User-agent` seguidas de reglas `Allow` y `Disallow`.[1] Los nombres de campo no distinguen entre mayúsculas y minúsculas, los comentarios comienzan con `#` y los rastreadores deben ignorar las reglas `Allow` y `Disallow` que aparezcan antes de la primera línea `User-agent`.[1][4][6]

| Directiva o token | Función en el RFC 9309 y en las implementaciones de rastreadores |
| --- | --- |
| `User-agent` | Identifica al rastreador objetivo mediante un token de producto (letras ASCII, `_`, `-`) o `*` para reglas predeterminadas; se compara sin distinguir entre mayúsculas y minúsculas.[1] |
| `Disallow` | Especifica un prefijo de ruta de URI que comienza con `/` al que el rastreador coincidente no debe acceder; un valor vacío no impone ninguna restricción.[1][6] |
| `Allow` | Especifica un prefijo de ruta de URI que comienza con `/` al que el rastreador coincidente puede acceder; se utiliza para permitir subrutas dentro de directorios bloqueados.[1][6] |
| `Sitemap` | Registro no esencial permitido por el RFC 9309 sin finalizar un grupo; admitido por Google con la URL completa de un mapa del sitio (sitemap).[1][6] |

Cada rastreador selecciona su token de producto, que debe aparecer como subcadena de su encabezado HTTP `User-Agent` (RFC 9110), y combina las reglas de todos los grupos que coinciden con ese token.[1] Cuando no coincide ningún grupo específico, el rastreador sigue el grupo `User-agent: *` si está presente; cuando no existe ninguno de los dos, o cuando el archivo está vacío, no se aplica ninguna regla.[1][4] La coincidencia de rutas comienza en el primer octeto de la ruta y debe distinguir entre mayúsculas y minúsculas.[1] Antes de la comparación, los octetos no ASCII y los caracteres reservados del RFC 3986 deben codificarse mediante porcentaje (percent-encoding), mientras que los caracteres ASCII no reservados codificados mediante porcentaje deben decodificarse.[1] El RFC 9309 exige soporte para tres caracteres especiales: `#` para comentarios, `*` para cero o más apariciones de cualquier carácter y `$` para marcar el final del patrón de coincidencia, mientras que los caracteres literales `*` y `$` se comparan como `%2A` y `%24`.[1]

Cuando varias reglas coinciden con un URI, los rastreadores deben aplicar la coincidencia más específica, definida como el patrón con mayor número de octetos.[1] Si una regla `Allow` y una regla `Disallow` tienen la misma especificidad, debe aplicarse la regla `Allow`; el propio URI `/robots.txt` está permitido implícitamente.[1] Según el RFC 9309, los rastreadores pueden interpretar otros registros como Sitemaps siempre que no interfieran con el análisis de grupos.[1] Google admite `user-agent`, `allow`, `disallow` y `sitemap`, y no admite `crawl-delay`.[6] Conforme al protocolo Sitemaps, un mapa del sitio XML es un documento UTF-8 `<urlset>` que contiene entradas `<url>` y `<loc>`, con un límite de 50,000 URL y 50 MB (52,428,800 bytes) sin comprimir por archivo, y pueden enumerarse varios mapas del sitio en un archivo `<sitemapindex>`.[10]

Para reducir las diferencias de análisis entre implementaciones, Google publicó como código abierto su biblioteca de producción en C++ de análisis y coincidencia de robots.txt en `github.com/google/robotstxt` bajo la licencia Apache-2.0.[8] El repositorio incluye un binario de pruebas por línea de comandos (`robots_main`) que evalúa un agente de usuario y un URI conforme al RFC 3986 frente a un archivo robots.txt local, devolviendo el código de salida 0 si está permitido y 1 si está prohibido.[8]

## Manejo de códigos de estado HTTP y almacenamiento en caché de robots.txt

Los rastreadores determinan cómo aplicar las reglas de robots.txt en función del código de estado HTTP o del resultado de red devuelto al solicitar `/robots.txt`.[1][6] El RFC 9309 define categorías base para accesos exitosos, redirecciones, respuestas no disponibles y errores de inalcanzabilidad, mientras que los motores de búsqueda publican tiempos de espera operativos y políticas de almacenamiento en caché adicionales.[1][6]

| Clase de respuesta | Especificación del RFC 9309 | Manejo del rastreador de Google (al 2026-11-23) |
| --- | --- | --- |
| `2xx` (Éxito) | Analizar y seguir las reglas válidas del archivo.[1] | Procesar el archivo robots.txt tal como se proporciona.[6] |
| `3xx` (Redirección) | Seguir al menos cinco redirecciones consecutivas (como 301 o 302), incluso entre distintas autoridades, aplicando las reglas obtenidas a la autoridad inicial; tras más de cinco, los rastreadores pueden tratar el archivo como no disponible.[1] | Seguir al menos cinco saltos de redirección y luego detenerse y tratar la respuesta como 404; no se siguen redirecciones lógicas mediante marcos, JavaScript o meta refresh.[6] |
| `4xx` (No disponible) | HTTP 400-499 indica que el archivo no está disponible; los rastreadores pueden acceder a cualquier recurso del servidor.[1] | Todos los errores 4xx excepto 429 se tratan como ausencia de robots.txt (sin restricciones de rastreo); los códigos 4xx distintos de 429 (incluidos 401 y 403) no reducen la frecuencia de rastreo.[6] |
| `5xx` y errores de red (Inalcanzable) | HTTP 500-599 o los errores de red dejan el archivo sin definir; los rastreadores deben asumir una prohibición total.[1] | Detener el rastreo durante 12 horas mientras se reintenta; durante los 30 días siguientes usar la última copia válida en caché (o asumir ausencia de restricciones si no existe caché); pasados 30 días, tratar un sitio generalmente disponible como sin restricciones o detener el rastreo si el sitio presenta problemas generales de disponibilidad.[6] |

Google clasifica los errores de DNS, los tiempos de espera agotados, las respuestas no válidas, las conexiones restablecidas o interrumpidas y los errores de fragmentación (chunking) de HTTP junto con los errores de servidor 5xx.[6] Ante respuestas HTTP 503, Google reintenta obtener robots.txt con mayor frecuencia.[6]

Al 2026-11-23, Google generalmente almacena en caché el contenido de un archivo robots.txt durante un máximo de 24 horas, puede conservar la versión en caché durante más tiempo cuando los intentos de actualización fallan por tiempos de espera agotados o errores 5xx, y puede compartir las reglas en caché entre distintos rastreadores de Google.[6] Google también puede aumentar o reducir el tiempo de vida de la caché según los encabezados de respuesta HTTP `Cache-Control` `max-age`.[6]

## Límites consultivos, seguridad e indexación de robots.txt

El RFC 9309 establece que las reglas de robots.txt no constituyen una forma de autorización de acceso y que su cumplimiento depende de que cada rastreador decida seguir el protocolo.[1][7] La especificación original de 1994 ya señalaba que ninguna parte hace cumplir las reglas y que no existe garantía de que todos los robots actuales o futuros las respeten.[4] Los clientes automatizados maliciosos, incluidos los escáneres de vulnerabilidades y los recolectores de direcciones de correo electrónico utilizados por emisores de spam, ignoran habitualmente robots.txt.[5]

Dado que `/robots.txt` es públicamente accesible para cualquier cliente, enumerar rutas en su interior revela qué directorios del servidor desea omitir un administrador frente a los rastreadores.[5] Tanto robotstxt.org como Google documentan que robots.txt no puede mantener oculto material confidencial y que proteger archivos privados requiere controles de acceso como la protección mediante contraseña.[5][7] Además, Google documenta que REP no se aplica a los recuperadores activados por el usuario, como las suscripciones a fuentes (feeds), ni a los rastreadores operados para proteger la seguridad del usuario, como el análisis de malware.[6]

En el caso de los motores de búsqueda, robots.txt gestiona el tráfico de rastreo y el consumo de ancho de banda, mientras que el comportamiento de indexación depende del tipo de archivo y de directivas independientes.[7][9] Bloquear una página HTML, un PDF u otro documento basado en texto en robots.txt impide que Google rastree la página, pero Google puede seguir indexando la URL sin visitarla si páginas externas enlazan a esa URL con texto de anclaje descriptivo, mostrando un resultado de búsqueda sin descripción.[7] Impedir que una página rastreable aparezca en los resultados de búsqueda requiere directivas a nivel de página como el elemento HTML `<meta name="robots">` (por ejemplo, `noindex`) o el encabezado de respuesta HTTP `X-Robots-Tag`, o bien restringir el acceso mediante autenticación.[7][9] En el caso de archivos multimedia como imágenes, vídeos y audio, Google documenta que robots.txt impide que esos archivos aparezcan en los resultados de la Búsqueda de Google, mientras que bloquear archivos de recursos esenciales como hojas de estilo o scripts puede impedir que Google renderice y analice con precisión las páginas que dependen de ellos.[7]

## robots.txt, IETF AIPREF y señalización de preferencias para rastreadores de IA

Además del rastreo de motores de búsqueda, robots.txt se referencia en trabajos de estandarización destinados a expresar preferencias de contenido para el desarrollo, despliegue y uso de modelos de inteligencia artificial (IA).[2] Al 2026-11-23, el grupo de trabajo AI Preferences (`aipref`) del IETF se encuentra activo dentro del área Web and Internet Transport (`wit`) bajo la carta aprobada `charter-ietf-aipref-01`, presidido por Mark Nottingham y Suresh Krishnan, con Mike Bishop como director de área.[2]

La carta de `aipref` define tres entregables: un documento de vocabulario de la vía de estándares (`draft-ietf-aipref-vocab`) que describe preferencias de contenido relacionadas con la IA de forma independiente del mecanismo de entrega, especificaciones de asociación de la vía de estándares (`draft-ietf-aipref-attach`) que vinculan esas preferencias con contenido en protocolos y formatos del IETF, y un método estándar para conciliar múltiples expresiones de preferencias.[2] Ambos borradores figuran en el IETF Datatracker con hitos previstos para agosto de 2026 al 2026-11-23.[2] La carta identifica explícitamente los Well-Known URIs (RFC 8615), como el Protocolo de exclusión de robots (RFC 9309), junto con los campos de encabezado de respuesta HTTP como mecanismos de asociación, e instruye al grupo a coordinarse con el International Press Telecommunications Council (IPTC), la PLUS Coalition, WHATWG y W3C.[2]

En consonancia con el carácter consultivo del RFC 9309, la carta de `aipref` excluye cuatro áreas de su alcance: la aplicación técnica obligatoria de las preferencias, los protocolos de capa de aplicación para autenticar o autorizar clientes o rastreadores, los registros de preferencias de contenido y las medidas de auditoría o transparencia para el entrenamiento de IA.[2] Fuera de los organismos de estandarización, los proveedores de infraestructura también han introducido controles que separan el descubrimiento en búsquedas del entrenamiento de IA: el 15 de septiembre de 2026, [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare) anunció controles y una designación Accountable que conforman un modelo compartido con Apple, Google y Microsoft para permitir que los propietarios de sitios sigan siendo localizables en las búsquedas mientras prohíben el entrenamiento de IA.[11]

## Preguntas frecuentes

### ¿Qué es un archivo robots.txt?

Un archivo robots.txt es un archivo de texto plano codificado en UTF-8 ubicado en /robots.txt, en el directorio raíz de un host web o FTP, conforme al Protocolo de exclusión de robots (RFC 9309). Indica a los rastreadores automatizados a qué rutas de URI de ese host pueden o no acceder. Martijn Koster documentó originalmente la convención en junio de 1994, y el IETF publicó el RFC 9309 en septiembre de 2022. [1][4]

### ¿Qué directivas admite robots.txt según el RFC 9309?

El RFC 9309 estandariza tres directivas principales: User-agent, Allow y Disallow, junto con los caracteres especiales # para comentarios, * para secuencias comodín y $ para coincidencia al final de la ruta. Los rastreadores también pueden interpretar registros adicionales como Sitemap sin interrumpir el análisis del grupo. Al 2026-11-23, Google admite User-agent, Allow, Disallow y Sitemap, y no admite crawl-delay. [1][6]

### ¿Cómo manejan los rastreadores los errores HTTP 4xx y 5xx para robots.txt?

Según el RFC 9309, las respuestas HTTP 400-499 indican que robots.txt no está disponible, por lo que los rastreadores pueden acceder a cualquier recurso del servidor, mientras que las respuestas HTTP 500-599 indican un archivo inalcanzable y exigen asumir una prohibición total. Al 2026-11-23, Google trata los errores 4xx distintos de 429 como ausencia de restricciones de rastreo y, ante errores 5xx, detiene el rastreo durante 12 horas antes de recurrir a su última copia en caché durante un máximo de 30 días. [1][6]

### ¿Cuál es el límite de tamaño de archivo de Google para robots.txt?

Al 2026-11-23, Google aplica un tamaño máximo de archivo de 500 kibibytes (KiB) para robots.txt. Cualquier contenido posterior al límite de 500 KiB es ignorado por el analizador de Google. [6]

### ¿Impide robots.txt que una página web aparezca en los resultados de búsqueda o protege archivos privados?

No. El RFC 9309 establece explícitamente que las reglas de robots.txt no son una forma de autorización de acceso, y los rastreadores que no cumplen el protocolo pueden ignorar el archivo. En el caso de las páginas web, Google puede seguir indexando una URL bloqueada sin visitarla si otras páginas enlazan a ella, por lo que excluir una página de los resultados de búsqueda o proteger archivos privados requiere mecanismos como el elemento HTML meta robots, los encabezados HTTP X-Robots-Tag o la protección mediante contraseña. [1][7][9]

### ¿Cómo se relaciona el grupo de trabajo AIPREF del IETF con robots.txt?

Al 2026-11-23, el grupo de trabajo activo AI Preferences (aipref) del IETF tiene el mandato de estandarizar un vocabulario y métodos de asociación a protocolos para expresar preferencias sobre la recopilación y el procesamiento de contenido para sistemas de IA. Su carta aprobada incluye explícitamente adjuntar esas preferencias mediante Well-Known URIs (RFC 8615), como el Protocolo de exclusión de robots (RFC 9309), así como mediante campos de encabezado de respuesta HTTP. [2]

## Frases citables

- Martijn Koster documentó originalmente el Protocolo de exclusión de robots tras un consenso en una lista de correo el 30 de junio de 1994. [1][4]
- El IETF publicó el Protocolo de exclusión de robots como RFC 9309 de la vía de estándares en septiembre de 2022. [1][3]
- El RFC 9309 exige que un archivo robots.txt esté codificado en UTF-8 con el tipo de medio text/plain y se sirva en la ruta /robots.txt completamente en minúsculas. [1]
- Según el RFC 9309, los rastreadores aplican la coincidencia de ruta más específica por longitud en octetos, y una regla Allow tiene prioridad cuando una regla Allow y una regla Disallow son equivalentes. [1]
- Según el RFC 9309, las respuestas HTTP 400-499 para robots.txt permiten acceder a cualquier recurso del servidor, mientras que las respuestas HTTP 500-599 exigen asumir una prohibición total. [1]
- Al 2026-11-23, Google aplica un límite de tamaño de archivo de 500 KiB para robots.txt e ignora el contenido que supera ese límite. [6]
- Google documenta que bloquear una página web en robots.txt no impide que su URL aparezca en los resultados de la Búsqueda de Google si otras páginas enlazan a ella. [7]
- Al 2026-11-23, el grupo de trabajo activo AI Preferences (aipref) del IETF tiene el mandato de especificar cómo adjuntar preferencias de contenido de IA mediante protocolos del IETF, incluidos el RFC 9309 y campos de encabezado de respuesta HTTP. [2]

## Cronología

- 1994-06-30: Se alcanza un consenso en una lista de correo sobre "A Standard for Robot Exclusion", redactado por Martijn Koster. [4]
- 1997: El Internet-Draft "A Method for Web Robots Control" documenta el mecanismo de exclusión de robots.txt. [5]
- 2022-09: El IETF publica el RFC 9309 ("Robots Exclusion Protocol") como Estándar propuesto en la vía de estándares. [1][3]
- 2026-09-15: Cloudflare anuncia controles y una designación Accountable junto con Apple, Google y Microsoft para mantener los sitios localizables en las búsquedas mientras prohíben el entrenamiento de IA. [11]

## Fuentes

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (consultado 2026-11-23; tier 1: government or public registry)
2. AI Preferences (aipref). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (consultado 2026-11-23; tier 1: government or public registry)
3. RFC 9309 - Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://datatracker.ietf.org/doc/rfc9309/ (consultado 2026-11-23; tier 1: government or public registry)
4. A Standard for Robot Exclusion - The Web Robots Pages. robotstxt.org. publicado 1994-06-30. https://www.robotstxt.org/orig.html (consultado 2026-11-23; tier 3: official site)
5. About /robots.txt - The Web Robots Pages. robotstxt.org. https://www.robotstxt.org/robotstxt.html (consultado 2026-11-23; tier 3: official site)
6. How Google Interprets the robots.txt Specification | Google Crawling Infrastructure | Crawling infrastructure | Google for Developers. Google Search Central. https://developers.google.com/crawling/docs/robots-txt/robots-txt-spec (consultado 2026-11-23; tier 3: official site)
7. Robots.txt Introduction and Guide | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/crawling-indexing/robots/intro (consultado 2026-11-23; tier 3: official site)
8. GitHub - google/robotstxt: The repository contains Google's robots.txt parser and matcher as a C++ library (compliant to C++11).. Google (GitHub). https://github.com/google/robotstxt (consultado 2026-11-23; tier 3: official site)
9. Robots.txt - Glossary | MDN. MDN Web Docs. publicado 2025-11-26. https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt (consultado 2026-11-23; tier 3: official site)
10. sitemaps.org - Protocol. sitemaps.org. https://www.sitemaps.org/protocol.html (consultado 2026-11-23; tier 3: official site)
11. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. publicado 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "robots.txt." Versión 2a33e0a7, 2026-11-23. https://mimirwiki.com/es/wiki/robots-txt
