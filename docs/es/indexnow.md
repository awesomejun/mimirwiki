---
title: "IndexNow"
subtitle: "Protocolo HTTP abierto para que los sitios web notifiquen a los motores de búsqueda sobre adiciones, actualizaciones y eliminaciones de URL"
canonical_url: https://mimirwiki.com/es/wiki/indexnow
language: es
page_class: anchor
revision_sha256: 9c70852cf33e9913e2581de298bc5d5dc1c469bc672b2d2b18736b15d729f9d5
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/indexnow.md
  txt: https://mimirwiki.com/es/wiki/indexnow.txt
  json: https://mimirwiki.com/es/wiki/indexnow.json
  jsonld: https://mimirwiki.com/es/wiki/indexnow.jsonld
translations:
  en: https://mimirwiki.com/wiki/indexnow
  ko: https://mimirwiki.com/ko/wiki/indexnow
  ja: https://mimirwiki.com/ja/wiki/indexnow
  zh: https://mimirwiki.com/zh/wiki/indexnow
---

# IndexNow

> IndexNow es un protocolo HTTP abierto lanzado por Microsoft Bing y Yandex en octubre de 2021 para notificar a los motores de búsqueda sobre URL agregadas, actualizadas o eliminadas. Los sitios verifican su propiedad mediante un archivo de texto con clave alojado en el servidor y envían una URL por GET o hasta 10 000 por POST al 23 de noviembre de 2026. Cada punto de conexión participante comparte los envíos con todos los demás.

IndexNow es un protocolo abierto de notificación por HTTP que permite a los propietarios de sitios web informar a los motores de búsqueda participantes cuando se agregan, actualizan o eliminan URL en un host. Microsoft Bing y Yandex anunciaron el protocolo el 18 de octubre de 2021, y su especificación en IndexNow.org está licenciada bajo Creative Commons Atribución-CompartirIgual 4.0 por los patrocinadores Microsoft Corporation, Yandex N.V. y Seznam.cz, a.s. Un sitio verifica la propiedad del dominio mediante un archivo de texto UTF-8 con clave alojado en el servidor y envía solicitudes HTTP GET de una sola URL o lotes JSON por POST de hasta 10 000 URL a cualquier punto de conexión participante, el cual comparte las URL enviadas con todos los demás motores de búsqueda participantes. Al 23 de noviembre de 2026, el registro oficial en indexnow.org/searchengines.json enumera siete puntos de conexión participantes: Bing, Yandex, Seznam, Naver, Yep, Internet Archive y Amazonbot.

**También conocido como:** Protocolo IndexNow, API de IndexNow, IndexNow.org

## Datos clave

- **Lanzamiento:** 2021-10-18 [6]
- **Creadores:** Microsoft Bing y Yandex [6]
- **Licencia de la especificación:** Creative Commons Atribución-CompartirIgual 4.0 (CC BY-SA 4.0) (al 2026-11-23) [5]
- **Límite de envío por lote:** Hasta 10 000 URL por solicitud HTTP POST (al 2026-11-23) [2]
- **Puntos de conexión registrados:** 7 en searchengines.json (Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (al 2026-11-23) [4]

## Datos básicos

- **Tipo:** Protocolo abierto de notificación de URL por HTTP [1]
- **Lanzamiento:** 2021-10-18 [6]
- **Creadores:** Microsoft Bing y Yandex [6]
- **Patrocinadores de la especificación:** Microsoft Corporation, Yandex N.V., Seznam.cz, a.s. (al 2026-11-23) [5]
- **Licencia:** Creative Commons Atribución-CompartirIgual 4.0 (CC BY-SA 4.0) (al 2026-11-23) [5]
- **Métodos de envío:** HTTP GET (1 URL) y HTTP POST JSON (hasta 10 000 URL) (al 2026-11-23) [2]
- **Punto de conexión global:** https://api.indexnow.org/indexnow (al 2026-11-23) [3]
- **Método de verificación:** Archivo de texto UTF-8 con clave (8 a 128 caracteres) alojado en el sitio (al 2026-11-23) [2]
- **Estándar de codificación URI:** RFC 3986 [2]
- **Motores de búsqueda registrados:** 7 entradas en searchengines.json (Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazonbot) (al 2026-11-23) [4]
- **Costo:** Gratuito (al 2026-11-23) [8]

## Qué es IndexNow y cómo surgió

IndexNow es un protocolo HTTP abierto y gratuito que permite a los propietarios de sitios web notificar a los motores de búsqueda y rastreadores web participantes cuando se agregan, actualizan o eliminan URL en un sitio.[1][8] Sin notificaciones push, los motores de búsqueda dependen del rastreo periódico para detectar cambios en los sitios web, lo cual puede tardar días o semanas porque los rastreadores no revisitan cada URL con frecuencia.[1][6] Enviar una notificación cuando el contenido cambia permite a los motores de búsqueda priorizar el rastreo de esas URL y limitar el rastreo exploratorio en páginas sin cambios, lo que reduce la carga del servidor.[1][6][8]

Microsoft Bing y Yandex anunciaron IndexNow el 18 de octubre de 2021.[6] Según los Términos de servicio de IndexNow.org consultados el 23 de noviembre de 2026, los patrocinadores de IndexNow.org son Microsoft Corporation, Yandex N.V. y Seznam.cz, a.s.[5] Los patrocinadores licencian sus derechos de autor sobre la especificación del protocolo publicada en IndexNow.org bajo la licencia Creative Commons Atribución-CompartirIgual 4.0 (CC BY-SA 4.0), sin otorgar otros derechos de propiedad intelectual, y los Términos de servicio se rigen por las leyes del Estado de California.[1][5]

Un requisito central de IndexNow es el intercambio entre motores: los motores de búsqueda que adoptan el protocolo acuerdan que cada URL enviada a un punto de conexión participante se comparte automáticamente con todos los demás motores de búsqueda participantes.[2][3][6] Por lo tanto, los propietarios de sitios web envían cada notificación de URL a un único punto de conexión participante.[3]

## Métodos de envío y códigos de estado HTTP de IndexNow

IndexNow admite dos métodos de envío HTTP para notificar a los motores de búsqueda sobre URL agregadas, actualizadas o eliminadas: solicitudes HTTP GET de una sola URL y solicitudes HTTP POST en formato JSON de múltiples URL.[2] Ambos métodos pueden ejecutarse desde cualquier cliente HTTP, navegador, script o herramienta de línea de comandos como `curl` o `wget`.[2][3]

Para enviar una URL mediante HTTP GET, un sitio envía una solicitud a `https://<searchengine>/indexnow?url={url-changed}&key={your-key}`, con un parámetro opcional `keyLocation` cuando el archivo de clave se ubica fuera del directorio raíz del sitio.[2][3] Las URL enviadas deben estar escapadas y codificadas conforme a RFC 3986, por ejemplo codificando `:` como `%3A`, `/` como `%2F`, `?` como `%3F`, `=` como `%3D` y `&` como `%26`.[2][3]

Para enviar varias URL en una sola solicitud, un sitio realiza un `HTTP POST` a `/indexnow` con el encabezado `Content-Type: application/json; charset=utf-8` y un cuerpo JSON que contiene `host`, `key`, el campo opcional `keyLocation` y `urlList`.[2][3] Al 23 de noviembre de 2026, cada solicitud POST acepta hasta 10 000 URL y puede mezclar URL `http` y `https` del mismo host.[2][3] Superar las 10 000 URL en una sola carga útil puede provocar que la solicitud falle o devuelva el código HTTP 422.[3] Los sitios también pueden enviar URL redirigidas (HTTP 301, HTTP 302 o meta refresh) y URL eliminadas que devuelvan HTTP 404 o HTTP 410 para que los motores de búsqueda actualicen o retiren las entradas obsoletas.[3]

Al 23 de noviembre de 2026, IndexNow.org documenta seis códigos de respuesta HTTP para las solicitudes de envío.[2][3][7]

| Código HTTP | Estado | Significado documentado |
| --- | --- | --- |
| 200 | OK | URL o lote de URL enviado correctamente; confirma únicamente la recepción |
| 202 | Accepted | URL recibida mientras la validación de propiedad de la clave está pendiente (habitual en una solicitud inicial) |
| 400 | Bad Request | Formato de solicitud no válido |
| 403 | Forbidden | Clave no válida (por ejemplo, falta el archivo de clave o la clave no aparece en el archivo) |
| 422 | Unprocessable Entity | Las URL no pertenecen al host, la clave incumple las reglas de esquema o la carga útil supera los límites |
| 429 | Too Many Requests | Frecuencia de solicitudes marcada como excesiva o posible spam |

## Reglas de clave API y verificación de propiedad de dominio en IndexNow

IndexNow exige a los propietarios de sitios web que envían URL manualmente que demuestren la propiedad del host de destino alojando un archivo de texto con clave codificado en UTF-8 en ese host.[2][3] Al 23 de noviembre de 2026, la clave debe tener entre 8 y 128 caracteres y contener únicamente letras ASCII minúsculas (`a-z`), letras ASCII mayúsculas (`A-Z`), dígitos (`0-9`) y guiones (`-`).[2][3] La documentación de IndexNow se refiere a estos como caracteres hexadecimales, aunque permite explícitamente `a-z`, `A-Z`, `0-9` y `-`.[2] Las claves pueden generarse con un generador de GUID o UUID, herramientas de línea de comandos o generadores en línea como la herramienta de Bing Webmaster Tools.[3][6][7]

IndexNow define dos formas de alojar el archivo de clave para la verificación.[2]

- Opción 1 (directorio raíz): alojar un archivo UTF-8 llamado `{your-key}.txt` en el directorio raíz del host, como `https://www.example.com/{your-key}.txt`, que contenga únicamente la cadena de la clave.[2][3] La especificación describe la Opción 1 como la configuración preferida, y cubre las URL de todo el host.[2][3]
- Opción 2 (directorio de subruta): alojar uno o más archivos de texto UTF-8 con clave en carpetas de acceso público del mismo host sin requisitos de inicio de sesión, y suministrar la URL del archivo de clave en cada envío mediante el parámetro de consulta `keyLocation` (GET) o el campo JSON (POST).[2][3] En la Opción 2, el directorio del archivo de clave delimita qué URL son válidas: por ejemplo, un archivo de clave en `http://example.com/catalog/key12457EDd.txt` cubre las URL que comienzan con `http://example.com/catalog/`, mientras que las URL bajo `http://example.com/help/` o `http://example.com/image/` no son válidas para esa clave.[2]

Cuando un sitio envía URL, los motores de búsqueda participantes rastrean el archivo de clave para verificar la propiedad del host y continúan reconociendo la clave hasta que el propietario la cambie.[2] Para rotar una clave API sin interrupción del servicio, el propietario del sitio reemplaza el archivo de clave existente por un nuevo archivo `{key}.txt` y comienza a enviar URL con la nueva clave, lo que activa la reverificación automática.[3] Los sitios web que utilizan un sistema de gestión de contenidos, un proveedor de alojamiento o una CDN que gestiona de forma nativa los envíos de IndexNow no necesitan crear un archivo de clave manualmente.[3]

## Motores de búsqueda participantes y puntos de conexión de IndexNow

IndexNow publica un registro JSON legible por máquina con los motores de búsqueda y rastreadores participantes en `https://www.indexnow.org/searchengines.json`.[4] Al 23 de noviembre de 2026, `searchengines.json` enumera siete participantes, cada uno asignado a un punto de conexión `meta.json`.[4] En esa misma fecha, la página principal de IndexNow.org menciona cinco motores de búsqueda compatibles (Microsoft Bing, Naver, Seznam.cz, Yandex y Yep), mientras que las preguntas frecuentes de IndexNow enumeran puntos de conexión de envío para seis servicios nombrados además del punto de conexión global `https://api.indexnow.org/indexnow`.[1][3]

| Clave de registro (`searchengines.json`) | URL de metadatos (`searchengines.json`) | Punto de conexión de envío (`indexnow.org/faq`) |
| --- | --- | --- |
| `bing` | `https://www.bing.com/indexnow/meta.json` | `https://www.bing.com/indexnow` |
| `yandex` | `https://www.yandex.com/indexnow/meta.json` | `https://yandex.com/indexnow` |
| `seznam` | `https://search.seznam.cz/indexnow/meta.json` | `https://search.seznam.cz/indexnow` |
| `naver` | `https://searchadvisor.naver.com/indexnow/meta.json` | `https://searchadvisor.naver.com/indexnow` |
| `yep` | `https://indexnow.yep.com/indexnow/meta.json` | `https://indexnow.yep.com/indexnow` |
| `internetarchive` | `https://web-static.archive.org/indexnow/meta.json` | No figura en la lista de puntos de conexión de las FAQ |
| `amazonbot` | `https://indexnow.amazonbot.amazon/indexnow/meta.json` | `https://indexnow.amazonbot.amazon/indexnow` |

El 19 de mayo de 2025, los gerentes principales de producto de Microsoft AI Bing Fabrice Canel y Krishna Madhavan anunciaron en el Bing Webmaster Blog que Amazon planeaba comenzar a adoptar IndexNow a mediados de junio de 2025 para detectar cambios en el contenido web y reducir el rastreo innecesario.[9] Al 23 de noviembre de 2026, el punto de conexión `amazonbot` de Amazon figura tanto en `searchengines.json` como en las preguntas frecuentes de IndexNow.[3][4]

Según los requisitos publicados en IndexNow.org, un motor de búsqueda que participe en IndexNow debe compartir automáticamente las URL enviadas con todos los demás motores de búsqueda participantes, tener una presencia notable en al menos un mercado o estar estrechamente vinculado al mercado de búsqueda, y realizar una contribución significativa a los envíos de URL.[2]

## Integraciones de IndexNow con CMS, complementos y Cloudflare Crawler Hints

IndexNow está integrado en sistemas de gestión de contenidos (CMS), complementos SEO de terceros y [redes de distribución de contenidos](https://mimirwiki.com/es/wiki/content-delivery-network) (CDN) para que los sitios web puedan emitir notificaciones de cambio de URL automáticamente.[3][7]

El 30 de noviembre de 2021, [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare) se asoció con Microsoft Bing y Yandex para agregar compatibilidad con IndexNow en Cloudflare Crawler Hints y puso Crawler Hints a disposición general de forma gratuita para todos los clientes de Cloudflare.[10] Los clientes de Cloudflare habilitan la integración desde un único ajuste en la sección Configuration bajo la pestaña Cache del panel de Cloudflare, tras lo cual Cloudflare envía señales de IndexNow automáticamente cuando cambia el contenido del sitio.[10] En el anuncio del 30 de noviembre de 2021, Cloudflare informó que aproximadamente el 45 % del tráfico de Internet procedía de rastreadores web y bots, y que un estudio de un año sobre el tráfico de los principales rastreadores de búsqueda halló que el 53 % de las visitas de rastreadores solicitaban páginas sin cambios desde la visita anterior.[10] Para esa fecha, más de 60 000 sitios web únicos de Cloudflare se habían suscrito a Crawler Hints y habían enviado a Bing alrededor de mil millones de avisos de cambio.[10] Al 23 de noviembre de 2026, tanto IndexNow.org como Bing Webmaster Tools enumeran Cloudflare Crawler Hints como una integración nativa de CDN, y la publicación de lanzamiento de octubre de 2021 también señalaba que Akamai planeaba integrar IndexNow.[3][6][7]

Al 23 de noviembre de 2026, IndexNow.org y Bing Webmaster Tools enumeran 16 plataformas CMS que ofrecen integración nativa con IndexNow o compatibilidad mediante complementos y extensiones: WordPress, Shopify, Wix, GoDaddy, Duda, XenForo, Milestone, Joomla!, Drupal, Bitrix24, PrestaShop, MODX, Shopware, OpenCart, Typo3 y Umbraco.[3][7] Bing Webmaster Tools enumera complementos específicos de terceros que incluyen el complemento IndexNow, Yoast, RankMath, AIOSEO y SEOPress para WordPress; InstaIndex para Shopify; Aimy Sitemap PRO y JSitemap para Joomla!; y ReIndex y TurboIndex para Bitrix24.[7]

En el lanzamiento de octubre de 2021, Microsoft Bing publicó código de fuente abierta para ayudar a WordPress y otras plataformas CMS a adoptar IndexNow, informó sobre integraciones planificadas por Wix, Duda, Botify, Oncrawl, Onely y Yext, y señaló que grandes sitios web que utilizaban la API de envío de URL de Bing Webmaster, incluidos eBay, LinkedIn, MSN, GitHub y Bizapedia, planeaban migrar a IndexNow.[6] El 19 de mayo de 2025, Microsoft Bing informó que Shopify y el proveedor de marketing digital y CMS Milestone Inc. habían integrado IndexNow.[9] Los propietarios de sitios web pueden verificar la recepción de las URL enviadas a través del portal de Bing Webmaster Tools.[7]

## Límites del protocolo IndexNow, no participación y relación con los sitemaps

IndexNow funciona como una señal voluntaria de notificación de URL cuyo alcance práctico está delimitado por la participación de los motores de búsqueda, las cuotas de rastreo, los límites de envío y los términos de los patrocinadores.[2][3][4][5][7]

La participación en IndexNow se limita a los servicios registrados en el protocolo. Al 23 de noviembre de 2026, `indexnow.org/searchengines.json` enumera siete puntos de conexión participantes: Bing, Yandex, Seznam, Naver, Yep, Internet Archive y Amazonbot.[4] Debido a que el intercambio automático de URL se aplica únicamente entre motores de búsqueda participantes, los motores de búsqueda ausentes de ese registro no reciben notificaciones de IndexNow a través del protocolo.[2][4] Según los Términos de servicio de IndexNow.org, cada patrocinador se reserva el derecho de modificar la especificación sin previo aviso, de utilizar o discontinuar IndexNow en cualquier producto o servicio en cualquier momento, y no tiene obligación alguna de leer o indexar las URL enviadas.[5]

Recibir una respuesta HTTP `200` de un punto de conexión de IndexNow confirma únicamente que el punto de conexión recibió la URL o la lista de URL enviada.[2] Tanto las preguntas frecuentes de IndexNow como Bing Webmaster Tools indican que enviar una URL no garantiza el rastreo ni la indexación.[3][7] Los motores de búsqueda evalúan cada URL enviada mediante sus propias cuotas de rastreo, lógica de programación y señales de calidad, y cada rastreo activado a través de IndexNow cuenta dentro de la cuota de rastreo del sitio web.[3][7]

IndexNow también impone restricciones de lote y frecuencia. Una sola solicitud POST está limitada a 10 000 URL al 23 de noviembre de 2026, y los envíos excesivos o repetitivos pueden activar la limitación de frecuencia HTTP `429`.[2][3] Las preguntas frecuentes de IndexNow recomiendan enviar únicamente cambios de contenido significativos, esperar al menos 5 minutos antes de volver a enviar la misma URL y enviar el contenido generado por usuarios, como reseñas, comentarios o publicaciones en foros, de manera incremental (por ejemplo, cada reseña de la 1 a la 20, cada quinta hasta 100 y cada décima hasta 1000).[3]

IndexNow está diseñado para complementar los [sitemaps XML](https://mimirwiki.com/es/wiki/sitemaps) y está destinado a URL agregadas, actualizadas o eliminadas después de que un sitio habilita el protocolo.[3][7] Las preguntas frecuentes de IndexNow indican que los sitios deben evitar el envío retroactivo de cambios antiguos o el envío de un sitio completo de una sola vez fuera de eventos importantes como una migración o un rediseño, y deben seguir manteniendo sitemaps XML con marcas de tiempo `lastmod` precisas para ofrecer un inventario completo de URL y facilitar el descubrimiento de páginas que se actualizan con poca frecuencia.[3]

## Preguntas frecuentes

### ¿Qué es IndexNow?

IndexNow es un protocolo HTTP abierto y gratuito lanzado por Microsoft Bing y Yandex el 18 de octubre de 2021 que permite a los propietarios de sitios web notificar a los motores de búsqueda participantes cuando se agregan, actualizan o eliminan URL. Enviar una URL a un punto de conexión participante comparte automáticamente esa notificación con todos los demás motores de búsqueda participantes. [1][2][6][8]

### ¿Qué motores de búsqueda participan en IndexNow?

Al 23 de noviembre de 2026, el registro oficial en indexnow.org/searchengines.json enumera siete puntos de conexión participantes: Bing, Yandex, Seznam, Naver, Yep, Internet Archive y Amazonbot. Los motores de búsqueda que no figuran en este registro no reciben notificaciones de URL a través de IndexNow. [2][4]

### ¿Cuántas URL se pueden enviar en una sola solicitud de IndexNow?

Al 23 de noviembre de 2026, IndexNow admite el envío de una URL por solicitud HTTP GET o hasta 10 000 URL en una sola solicitud HTTP POST en formato JSON UTF-8. Enviar más de 10 000 URL en una sola carga útil POST puede provocar que la solicitud falle o devuelva el código HTTP 422 (Unprocessable Entity). [2][3]

### ¿Cómo verifica IndexNow la propiedad de un sitio web?

Para la configuración manual, el propietario de un sitio crea una clave API de entre 8 y 128 caracteres (a-z, A-Z, 0-9 y guiones) y la aloja en un archivo de texto UTF-8 llamado {your-key}.txt en el directorio raíz del sitio. Como alternativa, el archivo de clave puede alojarse en una subcarpeta de acceso público si su URL se proporciona en el parámetro keyLocation, lo que limita los envíos válidos a las URL situadas dentro de ese directorio. [2][3]

### ¿Una respuesta HTTP 200 de IndexNow garantiza el rastreo o la indexación?

No. Una respuesta HTTP 200 confirma únicamente que el motor de búsqueda recibió la URL o el lote enviado. Los motores de búsqueda siguen aplicando sus propias cuotas de rastreo, lógica de programación y señales de calidad, y cada rastreo resultante cuenta dentro de la cuota de rastreo del sitio. [2][3][7]

### ¿IndexNow reemplaza a los sitemaps XML?

No. La documentación de IndexNow indica que los sitios web deben usar IndexNow junto con sitemaps XML. IndexNow notifica a los motores de búsqueda sobre adiciones, actualizaciones y eliminaciones recientes de URL, mientras que los sitemaps XML con valores lastmod proporcionan un inventario completo del sitio y facilitan el descubrimiento de páginas más antiguas o que cambian con poca frecuencia. [3]

## Frases citables

- Microsoft Bing y Yandex anunciaron el protocolo IndexNow el 18 de octubre de 2021. [6]
- La especificación del protocolo IndexNow en IndexNow.org está licenciada bajo Creative Commons Atribución-CompartirIgual 4.0 por los patrocinadores Microsoft Corporation, Yandex N.V. y Seznam.cz, a.s. [5]
- Al 23 de noviembre de 2026, IndexNow acepta hasta 10 000 URL en una sola solicitud HTTP POST en formato JSON. [2][3]
- Al 23 de noviembre de 2026, una clave API de IndexNow debe tener entre 8 y 128 caracteres compuestos por letras minúsculas, letras mayúsculas, dígitos y guiones. [2][3]
- Al 23 de noviembre de 2026, indexnow.org/searchengines.json enumera siete puntos de conexión participantes: Bing, Yandex, Seznam, Naver, Yep, Internet Archive y Amazonbot. [4]
- El 30 de noviembre de 2021, Cloudflare anunció compatibilidad con IndexNow en Crawler Hints y puso Crawler Hints a disposición general de forma gratuita para los clientes de Cloudflare. [10]
- Una respuesta HTTP 200 de un punto de conexión de IndexNow confirma únicamente la recepción de las URL enviadas y no garantiza el rastreo ni la indexación. [2][3][7]

## Cronología

- 2021-10-18: Microsoft Bing y Yandex anuncian el protocolo de notificación de URL IndexNow. [6]
- 2021-11-30: Cloudflare agrega compatibilidad con IndexNow en Crawler Hints y pone Crawler Hints a disposición general de forma gratuita para todos los clientes de Cloudflare. [10]
- 2025-05-19: Microsoft Bing informa sobre la compatibilidad con IndexNow en Shopify y Milestone Inc. y anuncia que Amazon planea comenzar a adoptar IndexNow a mediados de junio de 2025. [9]

## Fuentes

1. Home | IndexNow.org. IndexNow. https://www.indexnow.org/ (consultado 2026-11-23; tier 3: official site)
2. Documentation | IndexNow.org. IndexNow. https://www.indexnow.org/documentation (consultado 2026-11-23; tier 3: official site)
3. FAQ | IndexNow.org. IndexNow. https://www.indexnow.org/faq (consultado 2026-11-23; tier 3: official site)
4. IndexNow Participating Search Engines JSON. IndexNow. https://www.indexnow.org/searchengines.json (consultado 2026-11-23; tier 3: official site)
5. Terms | IndexNow.org. IndexNow. https://www.indexnow.org/terms (consultado 2026-11-23; tier 3: official site)
6. IndexNow – Instantly Index your web content in Search Engines |.... Microsoft Bing Webmaster Blog. publicado 2021-10-18. https://blogs.bing.com/webmaster/2021/10/IndexNow-Instantly-Index-your-web-content-in-Search-Engines/ (consultado 2026-11-23; tier 3: official site)
7. How to add IndexNow to your website | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow/getstarted (consultado 2026-11-23; tier 3: official site)
8. Why IndexNow | Bing Webmaster Tools. Microsoft Bing. https://www.bing.com/indexnow (consultado 2026-11-23; tier 3: official site)
9. IndexNow Drives Smarter and Faster Content Discovery | Bing.... Microsoft Bing Webmaster Blog. publicado 2025-05-19. https://blogs.bing.com/webmaster/2025/5/IndexNow-Drives-Smarter-and-Faster-Content-Discovery/ (consultado 2026-11-23; tier 3: official site)
10. Cloudflare Supports IndexNow via one-click Integration | Bing.... Microsoft Bing Webmaster Blog. publicado 2021-11-30. https://blogs.bing.com/webmaster/2021/11/Cloudflare-Supports-IndexNow-via-one-click-Integration/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "IndexNow." Versión 9c70852c, 2026-11-23. https://mimirwiki.com/es/wiki/indexnow
