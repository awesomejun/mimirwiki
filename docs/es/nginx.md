---
title: "nginx"
subtitle: "Servidor web asíncrono de código abierto de alto rendimiento, proxy inverso, balanceador de carga y proxy de correo"
canonical_url: https://mimirwiki.com/es/wiki/nginx
language: es
page_class: entity
revision_sha256: 290229bda72149067c343e3e272bc3151336264f7b12440a005a7ce8f78a8878
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/nginx.md
  txt: https://mimirwiki.com/es/wiki/nginx.txt
  json: https://mimirwiki.com/es/wiki/nginx.json
  jsonld: https://mimirwiki.com/es/wiki/nginx.jsonld
translations:
  en: https://mimirwiki.com/wiki/nginx
  ko: https://mimirwiki.com/ko/wiki/nginx
  ja: https://mimirwiki.com/ja/wiki/nginx
  zh: https://mimirwiki.com/zh/wiki/nginx
---

# nginx

> Al 23 de noviembre de 2026, las ramas de código abierto actuales son nginx 1.31.10 (mainline, lanzada el 23 de noviembre de 2026) y nginx 1.30.8 (estable), que corrigieron CVE-2026-132779 (vulnerabilidad de gravedad media donde la directiva ssl_early_data en TLS 1.3 podía causar uso excesivo de CPU). Siguieron a nginx 1.31.9 (mainline) y 1.30.7 (estable) del 18 de noviembre de 2026, que corrigieron 10 vulnerabilidades de seguridad (9 en la estable 1.30.7), encabezadas por dos fallos críticos de ejecución remota de código HTTP/2 sin autenticación con CVSS v4.0 9.2 (Crítica) / CVSS v3.1 8.1 (Alta): CVE-2026-123007 (subdesbordamiento de entero en send_window HTTP/2 y desbordamiento de búfer en heap de 10 años de antigüedad, introducido en nginx 1.9.5) y CVE-2026-123633 (use-after-free en worker_connections de proxy upstream HTTP/2).

nginx (estilizado como NGINX y pronunciado «engine-x») es un servidor web HTTP de código abierto dirigido por eventos, proxy inverso, balanceador de carga de aplicaciones, caché de contenido y servidor proxy de correo creado originalmente por Igor Sysoev y publicado en octubre de 2004. Distribuido bajo la licencia BSD de 2 cláusulas y mantenido por F5, Inc. desde su adquisición de NGINX, Inc. en 2019, nginx utiliza una arquitectura asíncrona de proceso maestro y procesos trabajadores (master-worker) diseñada para gestionar decenas de miles de conexiones simultáneas con una sobrecarga mínima de memoria.

**También conocido como:** NGINX, Engine-X, NGINX Open Source, NGINX Plus

## Datos clave

- **Autor original y propietario:** Igor Sysoev (2004); F5, Inc. (desde mayo de 2019) [1]
- **Licencia:** Licencia BSD de 2 cláusulas [1]
- **Últimas versiones:** 1.31.10 (mainline, lanzada el 23 de noviembre de 2026) y 1.30.8 (estable) (al 2026-11-23) [2]
- **Actualizaciones de seguridad (nov 2026):** 1.31.10 / 1.30.8 corrigen CVE-2026-132779 (uso de CPU con ssl_early_data); 1.31.9 / 1.30.7 (18 nov) corrigieron 10 CVE, incluidos los RCE HTTP/2 con CVSS 9.2 CVE-2026-123007 y CVE-2026-123633 (al 2026-11-23) [3]

## Datos básicos

- **Autor original:** Igor Sysoev [1]
- **Responsable de mantenimiento:** F5, Inc. (NGINX Product Group) [1]
- **Lanzamiento público inicial:** 4 de octubre de 2004 (versión 0.1.0) [1]
- **Versión mainline (nov 2026):** 1.31.10 (23 de noviembre de 2026) (al 2026-11-23) [3]
- **Versión estable (nov 2026):** 1.30.8 (incluida como no vulnerable a CVE-2026-132779 junto con 1.31.10) (al 2026-11-23) [2]
- **Escrito en:** C [1]
- **Licencia:** Licencia BSD de 2 cláusulas [1]
- **Protocolos compatibles:** HTTP/1.x, HTTP/2, HTTP/3 (QUIC), TLS/SSL, FastCGI, uwsgi, SCGI, gRPC, IMAP/POP3/SMTP, TCP/UDP [1]

## Descripción general y arquitectura asíncrona dirigida por eventos

nginx fue diseñado en 2002 por el ingeniero de software ruso Igor Sysoev para resolver el **problema C10k** (gestionar más de 10 000 conexiones simultáneas de clientes en un solo servidor) y se publicó como código abierto bajo la licencia BSD de 2 cláusulas el 4 de octubre de 2004.[1] A diferencia de los servidores web tradicionales basados en un hilo o un proceso por conexión, nginx emplea un único **proceso maestro** (master process) con privilegios (encargado de leer archivos de configuración, vincular puertos privilegiados y gestionar el ciclo de vida de los trabajadores) y uno o más **procesos trabajadores** (worker processes) sin privilegios y de un solo hilo (además de procesos opcionales de carga y gestión de caché).[1]

Cada proceso trabajador ejecuta un bucle de eventos asíncrono y no bloqueante respaldado por mecanismos de notificación del núcleo específicos de cada sistema operativo (`epoll` en Linux, `kqueue` en FreeBSD y macOS, y puertos de eventos en Solaris).[1] Dado que los procesos trabajadores no crean nuevos hilos del sistema operativo ni se bloquean en operaciones de E/S de disco o de red por cada conexión, nginx sirve recursos estáticos, termina TLS 1.3, multiplexa flujos HTTP/2 y HTTP/3 (QUIC), actúa como proxy para tráfico gRPC y WebSocket, y balancea la carga de servidores de aplicaciones upstream (en los contextos `http`, `stream` y `mail`) con un uso determinista de la memoria.[1] En mayo de 2019, el proveedor de entrega de aplicaciones **F5, Inc.** adquirió NGINX, Inc., continuando el desarrollo tanto de NGINX Open Source (`nginx.org`) como de la distribución comercial NGINX Plus.[1][2]

## Ramas de lanzamiento: mainline 1.31.x y estable 1.30.x

El proyecto nginx mantiene dos ramas simultáneas de lanzamiento de código abierto en `nginx.org`:[1][2] - **Rama mainline** (números de versión menor impares, actualmente **1.31.x**, en **1.31.10** al 23 de noviembre de 2026): recibe todas las nuevas funcionalidades, mejoras de protocolos, correcciones de errores y parches de seguridad.[2][3] - **Rama estable** (números de versión menor pares, actualmente **1.30.x**, en **1.30.8** a noviembre de 2026): se bifurca anualmente a partir de la rama mainline y recibe correcciones de errores críticos y retroportaciones de seguridad sin introducir cambios incompatibles hacia atrás en la API de módulos.[1][2]

El **18 de noviembre de 2026**, el proyecto publicó **nginx 1.31.9** y **nginx 1.30.7** para remediar un lote coordinado de 10 vulnerabilidades y exposiciones comunes (CVE) en mainline 1.31.9 (9 de las cuales también afectaban a la rama estable 1.30.x), que abarcaban HTTP/2, HTTP/3, gestión de proxy upstream, el resolvedor DNS asíncrono, el módulo de proxy de correo, el manejo de URI con `try_files`/`alias` y el procesamiento de TLS/SNI en `stream`.[2][3] Cinco días después, el **23 de noviembre de 2026**, el proyecto publicó **nginx 1.31.10** (con la página de avisos de seguridad de `nginx.org` listando **1.31.10+** y **1.30.8+** como no vulnerables) para corregir **CVE-2026-132779** (un fallo de gravedad media que afectaba a las versiones `1.21.4-1.31.9`, donde el uso de la directiva `ssl_early_data` en TLS 1.3 podía permitir a un cliente provocar un consumo excesivo de CPU) y un error por el cual nginx podía acaparar la CPU si se utilizaban conexiones SSL hacia servidores backend.[2][3]

## Avisos de seguridad de noviembre de 2026 y fallos RCE en HTTP/2

Entre las actualizaciones del 18 y el 23 de noviembre de 2026, el proyecto nginx divulgó 11 vulnerabilidades corregidas en las ramas mainline 1.31.x y estable 1.30.x.[2][3] En la actualización del 18 de noviembre (1.31.9 y 1.30.7), los investigadores de seguridad en la nube de **Wiz Research** detallaron dos vulnerabilidades críticas de ejecución remota de código en HTTP/2 sin autenticación, **CVE-2026-123007** y **CVE-2026-123633**, ambas con una **puntuación base CVSS v4.0 de 9.2 (Crítica)** y una **puntuación base CVSS v3.1 de 8.1 (Alta)** en la Base de Datos Nacional de Vulnerabilidades (NVD) del NIST, y conocidas en avisos de la comunidad bajo los apodos **nginx2root** / **nginx2shell**:[4][5][6][8]

| Identificador CVE | Módulo y versiones afectadas | Mecanismo de la vulnerabilidad | Gravedad / Corregida en |
| --- | --- | --- | --- |
| **CVE-2026-132779** | TLS 1.3 `ssl_early_data` (nginx 1.21.4 - 1.31.9) | Al utilizar la directiva `ssl_early_data`, un cliente puede causar un uso excesivo de CPU.[2][3] | Media (`nginx.org`); corregida en 1.31.10+, 1.30.8+ |
| **CVE-2026-123007** | `ngx_http_v2_module` (nginx 1.9.5 - 1.31.8; fallo de 10 años de antigüedad) | Un subdesbordamiento de entero en la contabilidad de control de flujo `send_window` de HTTP/2 mediante tramas `SETTINGS` y `WINDOW_UPDATE` manipuladas provoca un desbordamiento de búfer basado en heap (`CWE-191`, `CWE-122`).[2][4][6] | CVSS v4.0: 9.2 Crítica / v3.1: 8.1 Alta; corregida en 1.31.9+, 1.30.7+ |
| **CVE-2026-123633** | `ngx_http_v2_module` + proxy upstream (1.19.7 - 1.31.8) | Uso después de liberación (`use-after-free`, `CWE-416`) desencadenado cuando una conexión cliente HTTP/2 hace proxy hacia un backend upstream mientras `worker_connections` está agotado.[2][5][6] | CVSS v4.0: 9.2 Crítica / v3.1: 8.1 Alta; corregida en 1.31.9+, 1.30.7+ |
| **CVE-2026-121810** | `ngx_http_v3_module` (1.25.0 - 1.31.8) | Uso después de liberación (`use-after-free`) en el procesamiento HTTP/3 QUIC cuando `worker_connections` está agotado.[2][3] | Media (`nginx.org`); corregida en 1.31.9+, 1.30.7+ |
| **CVE-2026-123634** | `resolver` DNS asíncrono del núcleo (0.6.18 - 1.31.8) | Uso después de liberación (`use-after-free`) durante la resolución simultánea de nombres en subsolicitudes cuando `resolver` está configurado.[2][3] | Media (`nginx.org`); corregida en 1.31.9+, 1.30.7+ |
| **CVE-2026-113425** | `ngx_mail_module` (0.5.33 - 1.31.8) | Uso después de liberación (`use-after-free`) en el módulo de servidor proxy de correo.[2][3] | Mayor (`nginx.org`); corregida en 1.31.9+, 1.30.7+ |

Las otras cinco vulnerabilidades corregidas el 18 de noviembre de 2026 en nginx 1.31.9 (cuatro en 1.30.7) son **CVE-2026-125283** (desbordamiento de búfer al combinar las directivas `try_files` y `alias`), **CVE-2026-120967** (evasión de la verificación de certificados de cliente SSL mediante SNI en handshakes SSL síncronos de `stream`), **CVE-2026-120993** (desreferencia de puntero nulo / fallo de segmentación en un trabajador en el protocolo PROXY v2 con carga dinámica de certificados SSL, que afecta a mainline 1.31.4 - 1.31.8), **CVE-2026-123640** (validación insuficiente de mensajes ClientHello malformados en `ngx_stream_ssl_preread_module`) y **CVE-2026-118899** (bucle infinito del proceso trabajador al leer cuerpos de solicitudes de cliente sobre SSL/TLS 1.3).[2][3]

El registro de cambios de nginx atribuye el descubrimiento de CVE-2026-123007 a Xint.io y el de CVE-2026-123633 a Albert de Vexera AI.[3]

## Análisis técnico de CVE-2026-123007 y CVE-2026-123633

Entre los avisos de noviembre de 2026, **CVE-2026-123007** y **CVE-2026-123633** generaron alertas urgentes del Center for Internet Security (CIS Advisory `2026-136`) y de Wiz Research debido a que permiten la ejecución remota de código sin autenticación en despliegues HTTP/2 estándar:[6][7][8] - **CVE-2026-123007 (desbordamiento de heap en control de flujo HTTP/2 de 10 años de antigüedad)**: presente desde que `ngx_http_v2_module` debutó en nginx 1.9.5 (septiembre de 2015), este fallo se activa a través de una única conexión TCP HTTP/2 en cualquier bloque de servidor con `http2` habilitado.[4][6][8] Mediante el envío de tramas HTTP/2 `SETTINGS` (`SETTINGS_INITIAL_WINDOW_SIZE`) y `WINDOW_UPDATE` manipuladas mientras hay tramas de datos en cola, un atacante provoca un subdesbordamiento de entero en la contabilidad de `send_window`, lo que deriva en un desbordamiento de búfer basado en heap en el proceso trabajador de nginx.[4][6] - **CVE-2026-123633 (use-after-free en proxy upstream HTTP/2)**: afecta a los servidores con HTTP/2 habilitado que reenvían solicitudes a un backend upstream (`proxy_pass`, `fastcgi_pass`, `uwsgi_pass`, `scgi_pass` o `grpc_pass`), un patrón predeterminado en controladores ingress, pasarelas de API y proxies inversos.[5][6] Al abrir conexiones simultáneas para agotar `worker_connections` durante el establecimiento de la conexión upstream, un atacante desencadena un error de uso después de liberación (`use-after-free`) en el heap del proceso trabajador.[5][6]

Mediante la preparación controlada (grooming) del asignador de memoria por grupos de nginx (`ngx_pool_t`), un atacante puede sobrescribir punteros de función dentro de la memoria del trabajador para ejecutar código arbitrario con los privilegios del usuario del proceso trabajador de nginx.[6][8]

**Remediación**: los administradores deben actualizar a **nginx 1.31.10+** (mainline) o **nginx 1.30.8+** (estable), que incluyen tanto las correcciones del 18 de noviembre (`1.31.9+` / `1.30.7+`) como la corrección de `CVE-2026-132779` del 23 de noviembre.[2][3][7] Cuando las actualizaciones inmediatas no sean posibles, las medidas temporales de mitigación incluyen deshabilitar `http2`, `http3` y `ssl_early_data` en los oyentes no confiables, eliminar bloques `resolver` dinámicos que no se utilicen y asegurarse de que los procesos trabajadores de nginx se ejecuten bajo una cuenta sin privilegios en lugar de `root`.[2][3][6][7]

## Preguntas frecuentes

### ¿Cuáles son las últimas versiones de nginx al 23 de noviembre de 2026?

Al 23 de noviembre de 2026, las últimas versiones de código abierto de nginx son 1.31.10 en la rama mainline (lanzada el 23 de noviembre de 2026 en CHANGES) y 1.30.8 en la rama estable (listada como no vulnerable a CVE-2026-132779 junto con 1.31.10+ en la página de avisos de seguridad). Estas corrigen CVE-2026-132779 (uso excesivo de CPU en TLS 1.3 con ssl_early_data) tras los lanzamientos 1.31.9 y 1.30.7 del 18 de noviembre de 2026, que corrigieron 10 CVE. [2][3]

### ¿Qué es CVE-2026-132779 en nginx 1.31.10 y 1.30.8?

CVE-2026-132779 es una vulnerabilidad de gravedad media divulgada el 23 de noviembre de 2026 que afecta a nginx 1.21.4 hasta 1.31.9, donde habilitar la directiva ssl_early_data de TLS 1.3 podía permitir a un cliente provocar un uso excesivo de CPU. Se resuelve en nginx 1.31.10+ y 1.30.8+. [2][3]

### ¿Qué son CVE-2026-123007 y CVE-2026-123633 en nginx?

CVE-2026-123007 y CVE-2026-123633 son dos vulnerabilidades críticas de corrupción de memoria en HTTP/2 (puntuación CVSS v4.0 de 9.2 / CVSS v3.1 de 8.1) analizadas por Wiz Research y corregidas en nginx 1.31.9 y 1.30.7 el 18 de noviembre de 2026. CVE-2026-123007 es un subdesbordamiento de entero y desbordamiento de búfer en heap de 10 años de antigüedad en el manejo de control de flujo send_window de HTTP/2 (presente desde nginx 1.9.5), mientras que CVE-2026-123633 es un use-after-free que se desencadena cuando el proxy upstream HTTP/2 agota worker_connections. [2][4][5][6]

### ¿Cuál es la diferencia entre las ramas mainline y estable de nginx?

La rama mainline de nginx (versiones menores impares, como 1.31.x) recibe todas las nuevas funcionalidades, correcciones de errores y actualizaciones de seguridad, y es la recomendada por el equipo de nginx para la mayoría de los despliegues. La rama estable (versiones menores pares, como 1.30.x) solo recibe correcciones de errores críticos y retroportaciones de seguridad para preservar la compatibilidad con módulos de terceros. [1][2]

### ¿Cómo pueden los administradores mitigar las vulnerabilidades de nginx de noviembre de 2026 si no pueden actualizar de inmediato?

La única solución completa consiste en actualizar a nginx 1.31.10+ o 1.30.8+. Como solución alternativa temporal, los administradores pueden deshabilitar HTTP/2, HTTP/3 y ssl_early_data en los oyentes expuestos al público y verificar que los procesos trabajadores de nginx no estén configurados para ejecutarse como root. [2][3][6][7]

## Frases citables

- El 23 de noviembre de 2026, nginx lanzó la versión mainline 1.31.10 (con security_advisories.html indicando 1.31.10+ y 1.30.8+ como no vulnerables) para corregir CVE-2026-132779, un fallo de gravedad media de uso excesivo de CPU al emplear ssl_early_data en TLS 1.3 (que afecta a 1.21.4-1.31.9). [2][3]
- nginx lanzó la versión mainline 1.31.9 y la versión estable 1.30.7 el 18 de noviembre de 2026, corrigiendo 10 vulnerabilidades de seguridad en 1.31.9 (9 en 1.30.7). [2][3]
- CVE-2026-123007 y CVE-2026-123633 son vulnerabilidades de HTTP/2 que tienen una puntuación base CVSS v4.0 de 9.2 (Crítica) y una puntuación CVSS v3.1 de 8.1 (Alta) en NVD y permiten la ejecución remota de código sin autenticación. [4][5][6]
- CVE-2026-123007 es un subdesbordamiento de entero y desbordamiento de búfer en heap en el manejo de send_window de ngx_http_v2_module que afectó a las versiones de nginx 1.9.5 hasta 1.31.8 y 1.30.6. [2][4][6]
- nginx fue publicado originalmente por Igor Sysoev el 4 de octubre de 2004 bajo la licencia BSD de 2 cláusulas y es mantenido por F5, Inc. desde mayo de 2019. [1]

## Cronología

- 2004-10-04: Igor Sysoev publica nginx 0.1.0 de forma abierta bajo la licencia BSD de 2 cláusulas. [1]
- 2015-09: nginx 1.9.5 introduce ngx_http_v2_module para soporte de HTTP/2, con la lógica latente de send_window posteriormente identificada como CVE-2026-123007. [2][6]
- 2019-05: F5, Inc. completa la adquisición de NGINX, Inc. [1]
- 2026-11-18: nginx lanza 1.31.9 (mainline) y 1.30.7 (estable), corrigiendo 10 CVE, incluidos los fallos RCE de HTTP/2 con CVSS 9.2 CVE-2026-123007 y CVE-2026-123633, junto con CVE-2026-121810, CVE-2026-123634, CVE-2026-113425 y CVE-2026-125283. [2][3][6]
- 2026-11-23: nginx lanza la versión mainline 1.31.10 (y lista 1.31.10+ y la estable 1.30.8+ como no vulnerables en security_advisories.html), corrigiendo CVE-2026-132779 (uso excesivo de CPU en TLS 1.3 al usar ssl_early_data) y un error de uso de CPU en conexiones SSL hacia backends. [2][3]

## Fuentes

1. nginx news and official project documentation. nginx.org / F5, Inc.. https://nginx.org/en/ (consultado 2026-11-23; tier 3: official site)
2. nginx security advisories. nginx.org. publicado 2026-11-23. https://nginx.org/en/security_advisories.html (consultado 2026-11-23; tier 3: official site)
3. Changes with nginx 1.31.10 (23 Nov 2026) and 1.31.9 (18 Nov 2026). nginx.org. publicado 2026-11-23. https://nginx.org/en/CHANGES (consultado 2026-11-23; tier 3: official site)
4. NVD - CVE-2026-123007 Detail (nginx HTTP/2 send_window integer underflow and heap-based buffer overflow). National Vulnerability Database (NIST). publicado 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123007 (consultado 2026-11-23; tier 1: government or public registry)
5. NVD - CVE-2026-123633 Detail (nginx HTTP/2 upstream proxy worker_connections use-after-free). National Vulnerability Database (NIST). publicado 2026-11-18. https://nvd.nist.gov/vuln/detail/CVE-2026-123633 (consultado 2026-11-23; tier 1: government or public registry)
6. Unauthenticated Remote Code Execution in NGINX: CVE-2026-123633 and CVE-2026-123007 | Wiz Blog. Wiz Research. publicado 2026-11-18. https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities (consultado 2026-11-23; tier 3: official site)
7. Multiple Vulnerabilities in NGINX Could Allow for Remote Code Execution (CIS Advisory 2026-136). Center for Internet Security (CIS). publicado 2026-11-19. https://www.cisecurity.org/advisory/multiple-vulnerabilities-in-nginx-could-allow-for-remote-code-execution_2026-136 (consultado 2026-11-23; tier 2: academic or news)
8. 10-Year-Old NGINX HTTP/2 Flaw Lets Unauthenticated Attackers Execute Code on Servers. The Hacker News. publicado 2026-11-19. https://thehackernews.com/2026/11/10-year-old-nginx-http2-flaw-lets.html (consultado 2026-11-23; tier 2: academic or news)

## Citar esta página

Mimirwiki. "nginx." Versión 290229bd, 2026-11-23. https://mimirwiki.com/es/wiki/nginx
