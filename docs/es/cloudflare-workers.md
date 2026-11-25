---
title: "Cloudflare Workers"
subtitle: "Plataforma de ejecución sin servidor de Cloudflare que ejecuta JavaScript, TypeScript, Python, Rust y WebAssembly mediante aislados V8 y el entorno de ejecución workerd"
canonical_url: https://mimirwiki.com/es/wiki/cloudflare-workers
language: es
page_class: entity
revision_sha256: c3cd73167f583ce1c1bbc0e32b5c5211374f987416bbf27dba414561059ff1d7
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/cloudflare-workers.md
  txt: https://mimirwiki.com/es/wiki/cloudflare-workers.txt
  json: https://mimirwiki.com/es/wiki/cloudflare-workers.json
  jsonld: https://mimirwiki.com/es/wiki/cloudflare-workers.jsonld
translations:
  en: https://mimirwiki.com/wiki/cloudflare-workers
  ko: https://mimirwiki.com/ko/wiki/cloudflare-workers
  ja: https://mimirwiki.com/ja/wiki/cloudflare-workers
  zh: https://mimirwiki.com/zh/wiki/cloudflare-workers
---

# Cloudflare Workers

> Cloudflare Workers es una plataforma de computación sin servidor de Cloudflare que ejecuta JavaScript, TypeScript, Python, Rust y WebAssembly en toda su red global mediante aislados V8 y el entorno de ejecución workerd. Anunciada en 2017, ofrece API estándar web, compatibilidad con Node.js y enlaces de almacenamiento. A fecha de 2026-11-23, Cloudflare ofrece Workers Free y Workers Paid desde $5 al mes.

Cloudflare Workers es una plataforma de computación sin servidor operada por Cloudflare, Inc. que ejecuta aplicaciones de desarrolladores en toda la red global de Cloudflare mediante aislados V8 y el entorno de ejecución de código abierto workerd. Anunciada el 29 de septiembre de 2017, la plataforma ejecuta cargas de trabajo de JavaScript, TypeScript, Python, Rust y WebAssembly (Wasm) con API de plataforma web y un subconjunto implementado de forma nativa de las API de Node.js. Cloudflare publicó workerd, el entorno de ejecución de servidor de JavaScript y WebAssembly que sustenta Cloudflare Workers, bajo la licencia Apache-2.0 el 27 de septiembre de 2022. A fecha de 2026-11-23, Cloudflare ofrece un plan Workers Free limitado a 100,000 solicitudes por día y un plan Workers Paid a partir de $5 USD al mes bajo el modelo de uso Standard, sin cargos por transferencia saliente ni ancho de banda.

**También conocido como:** Workers, CF Workers, workerd

## Datos clave

- **Desarrollador:** Cloudflare, Inc. [2]
- **Modelo de ejecución:** Aislados V8 en toda la red global de Cloudflare [6]
- **Entorno de código abierto:** workerd (licencia Apache-2.0) [10]
- **Límite de Workers Free:** 100,000 solicitudes por día, 10 ms de tiempo de CPU por invocación (al 2026-11-23) [4]
- **Precio de Workers Paid:** Mínimo de $5 USD al mes (10 millones de solicitudes y 30 millones de ms de CPU incluidos) (al 2026-11-23) [4]

## Datos básicos

- **Desarrollador:** Cloudflare, Inc. (SEC CIK 0001477333) [2]
- **Anuncio inicial:** 29 de septiembre de 2017 [12]
- **Motor de ejecución:** Motor de JavaScript V8 (aislados) [6]
- **Entorno de código abierto:** workerd (licencia Apache-2.0, beta anunciada el 27 de septiembre de 2022) [11]
- **Lenguajes de primera clase:** JavaScript, TypeScript, Python, Rust (al 2026-11-23) [7]
- **Lenguajes WebAssembly:** Objetivos WebAssembly (Wasm), incluidos C, C++, Kotlin y Go (al 2026-11-23) [7]
- **Compatibilidad con Node.js:** Habilitada por defecto para fechas de compatibilidad iguales o posteriores a 2026-08-04 (al 2026-11-23) [9]
- **Plan Workers Free:** 100,000 solicitudes por día; 10 ms de tiempo de CPU por invocación (al 2026-11-23) [4]
- **Plan Workers Paid:** Mínimo de $5 USD al mes; 10 millones de solicitudes y 30 millones de ms de CPU incluidos; sin cargos por transferencia saliente (al 2026-11-23) [4]
- **Memoria por aislado:** 128 MB (montículo de JavaScript y asignaciones de WebAssembly) (al 2026-11-23) [5]
- **Tamaño e inicio del Worker:** Paquete sin comprimir de 64 MiB; límite de tiempo de inicio de 1 segundo (al 2026-11-23) [5]
- **Tiempo máximo de CPU (Paid):** 5 minutos por solicitud HTTP (30 segundos por defecto); 15 minutos para Cron Triggers de frecuencia horaria o superior (al 2026-11-23) [5]

## Arquitectura de aislados V8 y entorno de ejecución workerd de Cloudflare Workers

Cloudflare Workers ejecuta aplicaciones de usuario sobre el motor de JavaScript V8 en toda la red global de servidores distribuidos de [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare).[6] Cada servidor ejecuta instancias del entorno de ejecución de Workers, y cada instancia aloja cientos o miles de aislados V8, que son contextos de ejecución ligeros con entornos aislados de memoria independientes.[6] El entorno de ejecución inicializa un único proceso anfitrión de V8 por contenedor y ejecuta scripts de usuario dentro de aislados en ese proceso, mientras que las arquitecturas sin servidor basadas en contenedores inician un proceso de entorno de ejecución de lenguaje o una máquina virtual independiente por cada función.[6] La documentación de Cloudflare indica que un aislado V8 se inicia aproximadamente cien veces más rápido y consume un orden de magnitud menos de memoria al arrancar que un proceso de Node.js en un contenedor o una máquina virtual.[6]

Las solicitudes enrutadas a un subdominio `*.workers.dev` o a un dominio administrado por Cloudflare invocan el controlador `fetch(request, env, ctx)` exportado por un Worker en sintaxis de módulos ES y reciben un objeto `Response`.[6] Cada instancia de Worker procesa las solicitudes, incluidas las solicitudes concurrentes que esperan E/S asíncrona, en un bucle de eventos de un solo hilo.[6] Los aislados pueden ser desalojados cuando los recursos del servidor anfitrión se ven restringidos, cuando un Worker alcanza los límites de recursos o cuando el código presenta un comportamiento sospechoso de intento de escape del entorno aislado.[6] Dado que no existe garantía de que dos solicitudes lleguen a la misma instancia de un Worker, Cloudflare desaconseja almacenar estado mutable en el ámbito global.[6]

El entorno de ejecución de servidor de código abierto que impulsa Cloudflare Workers es `workerd` (pronunciado "worker-dee"), publicado en GitHub bajo la licencia Apache-2.0.[10][11] Los desarrolladores utilizan `workerd` para autoalojar aplicaciones compatibles con Workers, ejecutar entornos locales de desarrollo y pruebas, u operar un proxy HTTP programable directo o inverso.[10] Cloudflare documenta seis principios de diseño para `workerd`:[10]

- Diseño centrado en el servidor orientado específicamente a cargas de trabajo de servidor, excluyendo entornos de línea de comandos (CLI) e interfaces gráficas (GUI).[10]
- API integradas basadas en estándares alineadas con especificaciones de la plataforma web como `fetch()`.[10]
- Nanoservicios que permiten a componentes desplegables de forma independiente invocarse entre sí dentro del mismo hilo y proceso.[10]
- Despliegue homogéneo en las máquinas de un clúster para simplificar el balanceo de carga.[10]
- Enlaces de capacidades que conectan servicios y recursos externos mediante referencias explícitas para reducir la exposición a la falsificación de solicitudes del lado del servidor (SSRF).[10]
- Retrocompatibilidad basada en fechas en la que cada identificador de versión de `workerd` corresponde a la fecha de compatibilidad máxima que admite, preservando el comportamiento histórico de la API para fechas de compatibilidad anteriores.[10]

`workerd` se compila con Bazel y se prueba en Linux y macOS (`x86-64` y `arm64`), así como en Windows (`x86-64`).[10] Su configuración nativa utiliza el formato de texto de Cap'n Proto, y `workerd serve wrangler.jsonc` también carga configuraciones de Wrangler empaquetadas mediante `esbuild`.[10] A fecha de 2026-11-25, el repositorio de GitHub `cloudflare/workerd` registraba 9.3k estrellas, 846 bifurcaciones y 14,147 confirmaciones.[10] Cloudflare advierte que `workerd` de forma independiente no es adecuado como único entorno aislado reforzado frente a errores de implementación y requiere una máquina virtual o un entorno de aislamiento externo para código no confiable, mientras que el servicio alojado de Cloudflare Workers aplica capas adicionales de defensa en profundidad.[10]

## API del entorno de ejecución, estándares web y compatibilidad con Node.js de Cloudflare Workers

Cloudflare Workers implementa API de la plataforma web para que el código de las aplicaciones pueda seguir los estándares web de JavaScript tanto en navegadores como en entornos de ejecución de servidor.[8] Sus API integradas en el entorno de ejecución incluyen Fetch, Request, Response, Headers, Cache, Streams (`ReadableStream`, `WritableStream` y `TransformStream`), Web Crypto, WebSockets, sockets TCP, Encoding, EventSource, MessageChannel, Performance y temporizadores, Scheduler, HTMLRewriter, llamadas a procedimientos remotos (RPC), Context (`ctx`), Bindings (`env`) y controladores de eventos que abarcan los eventos Fetch, Scheduled, Queue, Email, Alarm, Tail y Connect.[8]

La documentación de API del entorno de ejecución de Cloudflare señala que Workers reutiliza API de la plataforma web para lograr interoperabilidad entre los entornos de ejecución de JavaScript de WinterCG.[8] En el ecosistema más amplio de estándares, el Comité Técnico 55 de Ecma International, conocido como WinterTC (Technical Committee on Web-interoperable Server Runtimes), estandariza una API común mínima compartida con la web para entornos de ejecución de JavaScript del lado del servidor, colabora con WHATWG y W3C en especificaciones de API web y publica estándares para API interoperables del lado del servidor.[1]

Para ejecutar paquetes de npm que dependen de bibliotecas de Node.js, Cloudflare Workers proporciona un subconjunto de API de Node.js mediante dos mecanismos: implementaciones nativas integradas orientadas a la versión Current de Node.js y capas de compatibilidad (polyfills) inyectadas por Wrangler a través de `unenv` cuyos métodos no implementados no realizan ninguna operación o lanzan errores.[9] El comportamiento del entorno de ejecución se controla mediante la fecha de compatibilidad y las banderas de compatibilidad de un Worker.[8][9] Para fechas de compatibilidad iguales o posteriores a 2026-08-04, Cloudflare Workers habilita tanto `nodejs_compat` como `nodejs_compat_v2` de forma predeterminada, mientras que los proyectos que optan por desactivarlos agregan `no_nodejs_compat` y `no_nodejs_compat_v2`.[9] Las fechas de compatibilidad comprendidas entre 2024-09-23 y 2026-08-03 se adhieren mediante la bandera `nodejs_compat`, que también habilita la inyección automática de polyfills de `unenv`; una bandera independiente `nodejs_als` habilita únicamente `AsyncLocalStorage`.[9]

A fecha de 2026-11-23, Cloudflare documenta la siguiente cobertura de compatibilidad del entorno de ejecución de Node.js:[9]

- Módulos compatibles de forma nativa: `assert`, `AsyncLocalStorage`, `Buffer`, `crypto`, Debugger (mediante integración con Chrome DevTools), Diagnostics Channel, Errors, `EventEmitter`, `fs`, Globals, `http`, `https`, `net`, `path`, `process`, Punycode (obsoleto), Query strings, `stream`, `StringDecoder`, `timers`, `url`, `util`, Web Crypto API, Web Streams API y `zlib`.[9]
- Módulos parcialmente compatibles: Console, `dns`, Module, OS, Performance hooks, Test runner y `tls` (TLS/SSL).[9]
- Módulos stub de solo importación no funcionales habilitados con `nodejs_compat` según la fecha de compatibilidad: `node:http2` (2025-09-01), `node:vm` (2025-10-01), `node:cluster`, `node:domain`, `node:trace_events` y `node:wasi` (2025-12-04), `node:_stream_wrap`, `node:dgram`, `node:inspector` y `node:sqlite` (2026-01-29), y `node:child_process`, `node:readline`, `node:repl`, `node:tty`, `node:v8` y `node:worker_threads` (2026-03-17).[9]

## Lenguajes, herramientas de desarrollo y enlaces de plataforma de Cloudflare Workers

Cloudflare Workers admite múltiples lenguajes de programación, herramientas de desarrollo local, marcos de trabajo web y enlaces directos con los servicios de la plataforma de Cloudflare.[3][7] A fecha de 2026-11-23, la plataforma enumera soporte de primera clase para cuatro lenguajes: JavaScript, TypeScript, Python (mediante Python Workers) y Rust (etiquetado como Beta en la navegación de la documentación).[3][7] Mediante la compatibilidad con binarios de WebAssembly (Wasm), los desarrolladores también pueden desplegar Workers escritos en lenguajes compilados a Wasm, entre ellos C, C++, Kotlin y Go.[7]

Los desarrolladores compilan, prueban y despliegan Workers mediante la CLI de Wrangler, Cloudflare Vite Plugin, Miniflare, la integración con Vitest y la integración y entrega continuas (CI/CD) integradas mediante Workers Builds (con integraciones para GitHub y GitLab) o flujos externos como GitHub Actions y GitLab CI/CD.[3] Cloudflare publica guías para marcos de trabajo web y de API como React, Vue, SvelteKit, Next.js (mediante el adaptador OpenNext), Astro, React Router, Remix 3, Nuxt, Angular, Hono, TanStack Start, Qwik, Solid, FastAPI y Flask.[3] Los activos estáticos de interfaz se pueden servir directamente a través de la [red de distribución de contenidos](https://mimirwiki.com/es/wiki/content-delivery-network) y la caché de Cloudflare junto con la lógica del Worker, mientras que Smart Placement optimiza el enrutamiento de solicitudes de servidor hacia almacenes de datos externos.[3] A fecha de 2026-11-23, la documentación de Cloudflare Workers también publica un índice [llms.txt](https://mimirwiki.com/es/wiki/llms-txt), `llms-full.txt`, vistas por página en [Markdown](https://mimirwiki.com/es/wiki/markdown) y enlaces a los servidores de [Model Context Protocol](https://mimirwiki.com/es/wiki/model-context-protocol) de Cloudflare.[3]

En el informe del año fiscal 2025 de Cloudflare presentado en [SEC EDGAR](https://mimirwiki.com/es/wiki/sec-edgar), la compañía clasifica Cloudflare Workers, Cloudflare Workers for Platforms (un entorno de ejecución administrado multiinquilino donde los clientes de plataforma ejecutan código de usuarios finales) y Cloudflare Pages dentro de sus soluciones para desarrolladores de Compute.[2] Los Workers se conectan a servicios de almacenamiento, computación, inteligencia artificial y medios mediante enlaces `env` explícitos:[2][3]

- Almacenamiento y bases de datos: Durable Objects (coordinación con estado en tiempo real), D1 (base de datos SQL sin servidor), Workers KV (almacenamiento clave-valor distribuido globalmente con lecturas en caché en el borde), Queues (colas de mensajes asíncronas sin cargos por transferencia saliente), Hyperdrive (agrupación de conexiones, optimización de enrutamiento y caché de consultas para bases de datos externas) y R2 (almacenamiento de objetos sin cargos por transferencia saliente).[2][3]
- Computación e inteligencia artificial: Workers AI (inferencia de aprendizaje automático en GPU sin servidor), Workflows (ejecución duradera en varios pasos con reintentos automáticos), Vectorize (base de datos vectorial para incrustaciones y búsqueda semántica), Browser Run (instancias programáticas de navegador sin servidor), Service bindings (llamadas HTTP y RPC mediante `WorkerEntrypoint` entre Workers), Dynamic Worker Loaders y Workers for Platforms Dispatcher.[2][3]
- Enlaces de medios y operaciones: Cache, Images, Stream, Media Transformations, Assets, Analytics Engine, Rate Limiting, Secrets, Secrets Store (Beta), certificados mTLS y variables de entorno.[3]

## Planes y precios de Cloudflare Workers

Cloudflare Workers se ofrece mediante un plan Workers Free, un plan Workers Paid con un mínimo mensual por cuenta de $5 USD y cuentas Workers Enterprise basadas en contrato.[4] Las cuentas comienzan por defecto en Workers Free, que proporciona cuotas diarias de uso para Workers, Pages Functions, Workers KV e Hyperdrive.[4] Workers Paid utiliza el modelo de uso Standard, otorga asignaciones mensuales que cubren Workers, Pages Functions, Workers KV, Hyperdrive y Durable Objects, y no aplica cargos adicionales por transferencia de datos saliente ni por ancho de banda.[4] Todas las Pages Functions siguen las mismas reglas de facturación que Workers.[4] Los modelos de uso heredados (Workers Unbound y Workers Bundled) permanecen en algunas configuraciones antiguas, mientras que Cloudflare migró los Workers del modelo Bundled a los precios del modelo Standard el 1 de marzo de 2024 con un límite automático de CPU de 50 milisegundos.[4]

A fecha de 2026-11-23, Cloudflare publica los siguientes precios de computación de Workers en los niveles Free y Paid (Standard):[4]

| Métrica | Workers Free | Workers Paid (Standard) |
| --- | --- | --- |
| Suscripción base | $0 | Mínimo de $5 USD al mes |
| Solicitudes entrantes | 100,000 por día | 10 millones al mes incluidos, luego $0.30 por millón adicional |
| Duración (tiempo real) | Sin costo | Sin costo y sin límite |
| Tiempo de CPU | 10 ms por invocación | 30 millones de ms de CPU al mes incluidos, luego $0.02 por millón de ms de CPU adicional |
| Tiempo máximo de CPU por invocación | 10 ms | 5 minutos HTTP (30 segundos por defecto); 15 minutos para Cron Triggers de frecuencia horaria o superior |
| Solicitudes de activos estáticos | Gratuitas e ilimitadas | Gratuitas e ilimitadas |

Cloudflare no factura las subsolicitudes salientes iniciadas por un Worker.[4] Las conexiones WebSocket cuentan como una sola solicitud en el apretón de manos inicial de actualización (Upgrade), mientras que los mensajes enrutados no generan cargos por mensaje.[4] Cuando Workers Caching está habilitado, los aciertos de caché se facturan a la tarifa por solicitud (incluidos los activos estáticos y las llamadas de Worker a Worker), y el tiempo de CPU se factura únicamente cuando el Worker se ejecuta ante un fallo o una omisión de caché.[4] Los propietarios de cuentas pueden configurar un límite de gasto de Workers para bloquear nuevas invocaciones una vez que los cargos por solicitudes y CPU posteriores a la cuota superen un umbral elegido (excluida la tarifa de suscripción de $5), o configurar alertas por correo electrónico sin bloqueo.[4]

La página de precios de Workers de Cloudflare también enumera cuotas y tarifas de excedente para servicios de desarrollo adyacentes a fecha de 2026-11-23:[4]

| Servicio y métrica | Workers Free | Workers Paid |
| --- | --- | --- |
| Eventos escritos de Workers Logs | 200,000 por día (retención de 3 días) | 20 millones al mes incluidos, luego $0.60 por millón (retención de 7 días) |
| Workers Trace Events Logpush | No disponible | 10 millones de solicitudes al mes incluidas, luego $0.05 por millón |
| Claves leídas de Workers KV | 100,000 por día | 10 millones al mes incluidas, luego $0.50 por millón |
| Claves escritas, eliminadas o listadas de Workers KV | 1,000 por día cada operación | 1 millón al mes incluido, luego $5.00 por millón cada operación |
| Almacenamiento y espacios de nombres de Workers KV | 1 GB; 1,000 espacios de nombres | 1 GB (+$0.50/GB-mes); primeros 1,000 espacios de nombres (+$0.10/espacio de nombres adicional/mes) |
| Consultas de base de datos de Hyperdrive | 100,000 por día | Ilimitadas |
| Operaciones estándar de Queues (por bloque de mensaje de 64 KB) | 10,000 por día (retención de 24 horas; 10,000 colas) | 1 millón al mes (+$0.40/millón; retención de 4 días por defecto hasta 14 días; primeras 10,000 colas incluidas, +$0.10/cola adicional/mes) |
| Pasos y almacenamiento de Workflows | 3,000 pasos por día; 1 GB-mes (solicitudes compartidas con Workers) | 500,000 pasos al mes (+$0.80 por 100,000); 1 GB-mes (+$0.20/GB-mes) |
| Filas leídas de D1 | 5 millones por día | 25 mil millones al mes incluidas, luego $0.001 por millón |
| Filas escritas de D1 | 100,000 por día | 50 millones al mes incluidas, luego $1.00 por millón |
| Almacenamiento y bases de datos de D1 | 5 GB en total; 10 bases de datos | 5 GB (+$0.75/GB-mes); 100,000 bases de datos (+$0.10/base de datos adicional/mes) |

Cloudflare señala que Workers Logs pasará a los precios de Cloudflare Observability a partir del 1 de diciembre de 2026, y que la facturación de pasos y almacenamiento de Workflows comenzará en la fecha anunciada en el registro de cambios de facturación de Workflows.[4] Queues mide las operaciones en cada mensaje individual por bloque de 64 KB (1 KB definido como 1,000 bytes, con aproximadamente 100 bytes de metadatos internos), por lo que una entrega típica consume tres operaciones (escritura, lectura y eliminación) sin cargos por transferencia saliente.[4]

## Límites operativos y de recursos de Cloudflare Workers

Cloudflare Workers aplica límites de cuenta, ejecución, red y despliegue tanto en el plan Workers Free como en el plan Workers Paid.[5] A fecha de 2026-11-23, Cloudflare enumera los siguientes límites principales de cuenta y plataforma:[5]

| Límite | Workers Free | Workers Paid |
| --- | --- | --- |
| Solicitudes diarias | 100,000 por día (se reinicia a las 00:00 UTC) | Sin límite |
| Tiempo de CPU por solicitud HTTP | 10 ms | 5 minutos (30 segundos por defecto) |
| Tiempo de CPU por Cron Trigger | 10 ms | 5 minutos (intervalo menor a 1 hora); 15 minutos (intervalo de 1 hora o superior) |
| Memoria por aislado | 128 MB | 128 MB |
| Subsolicitudes por invocación | 50 (1,000 a servicios internos) | 10,000 (configurable hasta 10 millones) |
| Conexiones salientes simultáneas a la espera de encabezados | 6 | 6 |
| Variables de entorno por Worker (secretos y texto) | 64 (5 KB cada una) | 128 (5 KB cada una) |
| Tamaño del paquete de Worker (sin comprimir) | 64 MiB | 64 MiB |
| Tiempo de inicio del Worker (ámbito global) | 1 segundo | 1 segundo |
| Workers por cuenta | 100 | 500 |
| Retención de versiones | 30 días (se conservan las 100 más recientes) | 30 días (se conservan las 100 más recientes) |
| Cron Triggers por cuenta | 5 | 1,000 |
| Archivos de activos estáticos por versión de Worker | 20,000 (25 MiB por archivo) | 100,000 (25 MiB por archivo) |

El tiempo de CPU contabiliza únicamente la ejecución activa del script y excluye el tiempo de espera de E/S de red como `fetch()`, lecturas de KV o consultas de bases de datos.[5] Cloudflare informa que un Worker promedio consume aproximadamente 2.2 ms de tiempo de CPU por solicitud, mientras que las cargas de trabajo más pesadas que gestionan autenticación, renderizado del lado del servidor o análisis de cargas útiles grandes suelen utilizar entre 10 y 20 ms.[5] Superar el límite diario de solicitudes de Workers Free desencadena el Error 1027 (con rutas configurables en modo de fallo abierto para omitir el Worker o de fallo cerrado para devolver la página de error).[5] Superar los límites de CPU o memoria devuelve el Error 1102 (`exceededCpu` o `exceededMemory` en analítica y Logpush), y superar el límite de inicio de 1 segundo en el ámbito global rechaza el despliegue con el código de error 10021.[5]

El límite de memoria de 128 MB abarca tanto el montículo de JavaScript como las asignaciones de WebAssembly en todo un aislado, que puede gestionar varias solicitudes concurrentes.[5] Cuando un aislado supera los 128 MB, el entorno de ejecución permite que las solicitudes en curso finalicen y dirige las nuevas solicitudes a un aislado nuevo, cancelando las solicitudes entrantes únicamente bajo carga extrema.[5] Los Workers activados por HTTP no tienen un límite estricto de duración en tiempo real mientras el cliente permanezca conectado, y `ctx.waitUntil()` puede extender la ejecución hasta 30 segundos después de que finalice una respuesta o se desconecte un cliente; los Cron Triggers, las alarmas de Durable Objects y los consumidores de Queues tienen un límite de 15 minutos de duración en tiempo real.[5] Durante las actualizaciones rutinarias del entorno de ejecución, los procesos de la versión anterior disponen de hasta 20 minutos para completar las respuestas HTTP en flujo continuo y las conexiones WebSocket existentes.[5]

Cada solicitud de nivel superior (incluidos los Workers invocados mediante Service bindings) permite hasta seis conexiones salientes simultáneas a la espera de encabezados de respuesta entre `fetch()`, KV, Cache, R2, Queues, TCP `connect()` y WebSockets salientes, poniendo en cola las conexiones adicionales hasta que lleguen los encabezados.[5] Los límites de solicitud y respuesta establecen un máximo de 16 KB para las URL y de 128 KB en total para los encabezados de solicitud o de respuesta cada uno, sin un límite aplicado al tamaño del cuerpo de respuesta (sujeto a los límites de caché de la CDN de 512 MB en los planes Free, Pro y Business y de 5 GB en Enterprise).[5] Los límites del cuerpo de solicitud entrante se rigen por el plan de Cloudflare del dominio: 100 MB en Free y Pro, 200 MB en Business y hasta 5 GB de autoservicio en Enterprise (devolviendo HTTP 413 si se exceden), mientras que los cuerpos HTTP salientes enviados desde Durable Objects o Containers tienen un valor predeterminado de 100 MiB.[5] Los límites de enrutamiento permiten 1,000 rutas por zona (50 durante sesiones de `wrangler dev --remote` o Quick Editor), 100 dominios personalizados por zona y 1,000 zonas enrutadas por Worker.[5] Las plataformas multiinquilino que necesiten más de 500 Workers pueden utilizar Workers for Platforms, que admite un número ilimitado de Workers de usuario.[5]

## Historia y divulgaciones operativas de Cloudflare Workers

Cloudflare Workers fue presentado el 29 de septiembre de 2017 en el blog de Cloudflare durante la Birthday Week como una forma de ejecutar JavaScript Service Workers en el borde de la red de Cloudflare.[12] Posteriormente se añadió una actualización fechada el 13 de marzo de 2018 a ese anuncio de lanzamiento para registrar la disponibilidad de la plataforma.[12] Cinco años después del lanzamiento inicial, el 27 de septiembre de 2022, Cloudflare anunció la primera versión beta de `workerd`, liberando como software de código abierto bajo la licencia Apache-2.0 el código del entorno de ejecución de JavaScript y WebAssembly detrás de Cloudflare Workers.[11]

El 1 de marzo de 2024, Cloudflare migró las cuentas del modelo heredado Bundled al modelo de uso Standard.[4] A partir de la fecha de compatibilidad 2024-09-23, habilitar `nodejs_compat` indicó a Wrangler que inyectara automáticamente los polyfills de `unenv`.[9] Los módulos stub de solo importación para módulos de Node.js como `node:http2`, `node:vm`, `node:sqlite`, `node:child_process` y `node:worker_threads` se habilitan con `nodejs_compat` en fechas de compatibilidad comprendidas entre 2025-09-01 y 2026-03-17, y para fechas de compatibilidad iguales o posteriores a 2026-08-04, Workers habilita `nodejs_compat` y `nodejs_compat_v2` de forma predeterminada.[9] Cloudflare también ha programado que Workers Logs adopte los precios de Cloudflare Observability el 1 de diciembre de 2026.[4]

En el informe del año fiscal 2025 de [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare) presentado en [SEC EDGAR](https://mimirwiki.com/es/wiki/sec-edgar), la compañía afirma que el uso por parte de los clientes de sus soluciones para desarrolladores, incluido Cloudflare Workers, le abrió un nuevo mercado en almacenamiento y computación, y que considera que compite cada vez más con los proveedores de nube pública por cargas de trabajo de almacenamiento y computación.[2] En las divulgaciones de riesgos del mismo informe, Cloudflare notificó un incidente operativo en junio de 2025 en el que falló la infraestructura subyacente de almacenamiento de terceros utilizada por el servicio Workers KV, lo que provocó una interrupción del servicio de varias horas que afectó a una parte de los servicios y clientes de Cloudflare.[2] Cloudflare declaró que la interrupción de junio de 2025 no tuvo un impacto material en su negocio, sus resultados de operaciones ni su situación financiera.[2]

## Preguntas frecuentes

### ¿Cómo ejecuta código Cloudflare Workers mediante aislados V8?

Cloudflare Workers ejecuta el motor de JavaScript V8 dentro de procesos compartidos del sistema operativo y asigna un aislado V8 ligero con memoria aislada para cada aplicación de usuario. Una sola instancia del entorno de ejecución ejecuta cientos o miles de aislados y alterna entre ellos, pagando el costo de inicio del proceso del entorno de ejecución una sola vez por contenedor. La documentación de Cloudflare indica que los aislados se inician aproximadamente cien veces más rápido y consumen un orden de magnitud menos de memoria al arrancar que un proceso de Node.js en un contenedor o una máquina virtual. [6]

### ¿Qué es workerd y bajo qué licencia se distribuye?

workerd (pronunciado "worker-dee") es el entorno de ejecución de servidor de código abierto para JavaScript y WebAssembly basado en el mismo código que impulsa Cloudflare Workers, distribuido bajo la licencia Apache-2.0. Cloudflare anunció su primera versión beta el 27 de septiembre de 2022 para el desarrollo local, el autoalojamiento de aplicaciones Workers y el uso como proxy HTTP programable. Cloudflare señala que workerd de forma independiente requiere un entorno de aislamiento externo, como una máquina virtual, cuando se ejecuta código no confiable. [10][11]

### ¿Cuánto cuesta Cloudflare Workers?

A fecha de 2026-11-23, Cloudflare ofrece un plan Workers Free sin costo con 100,000 solicitudes por día y 10 milisegundos de tiempo de CPU por invocación, además de un plan Workers Paid con un mínimo mensual por cuenta de $5 USD. Bajo el modelo de uso Standard, Workers Paid incluye 10 millones de solicitudes y 30 millones de milisegundos de CPU al mes, cobra $0.30 por cada millón de solicitudes adicional y $0.02 por cada millón de milisegundos de CPU adicional, y no aplica cargos por duración ni por ancho de banda saliente. Las solicitudes de activos estáticos y las subsolicitudes iniciadas por un Worker son gratuitas. [4]

### ¿Cuáles son los principales límites de recursos en los planes Free y Paid de Cloudflare Workers?

A fecha de 2026-11-23, tanto el plan Workers Free como el plan Workers Paid aplican 128 MB de memoria por aislado, un tamaño máximo de paquete de Worker sin comprimir de 64 MiB, un límite de tiempo de inicio de 1 segundo y 6 conexiones salientes simultáneas a la espera de encabezados de respuesta. Workers Free limita el tráfico diario a 100,000 solicitudes, el tiempo de CPU HTTP a 10 ms, las subsolicitudes a 50 por solicitud y los totales por cuenta a 100 Workers y 5 Cron Triggers. Workers Paid elimina el límite diario de solicitudes y amplía los límites a 5 minutos de tiempo de CPU HTTP (30 segundos por defecto), 10,000 subsolicitudes por solicitud (configurable hasta 10 millones), 500 Workers y 1,000 Cron Triggers. [5]

### ¿Qué lenguajes de programación admite Cloudflare Workers?

A fecha de 2026-11-23, Cloudflare Workers ofrece soporte de primera clase para JavaScript, TypeScript, Python (mediante Python Workers) y Rust. Dado que el entorno de ejecución también ejecuta WebAssembly (Wasm), los desarrolladores pueden compilar lenguajes adicionales como C, C++, Kotlin y Go para ejecutarlos en Workers. [7]

### ¿Es compatible Cloudflare Workers con las API de Node.js?

Sí. A fecha de 2026-11-23, Cloudflare Workers implementa de forma nativa un subconjunto de las API de Node.js en el entorno de ejecución, que incluye Buffer, crypto, fs, http, https, net, path, process, stream, timers, url, util, zlib y AsyncLocalStorage, complementado por polyfills de unenv en Wrangler y módulos stub de solo importación. Para fechas de compatibilidad iguales o posteriores a 2026-08-04, tanto nodejs_compat como nodejs_compat_v2 se habilitan de forma predeterminada sin banderas adicionales. [9]

## Frases citables

- Cloudflare anunció Cloudflare Workers el 29 de septiembre de 2017 en el blog de Cloudflare. [12]
- Cloudflare Workers ejecuta código de usuario dentro de aislados V8 alojados en procesos de entorno de ejecución compartidos en toda la red global de Cloudflare. [6]
- Cloudflare presentó la primera versión beta de workerd, el entorno de ejecución de JavaScript y WebAssembly que impulsa Cloudflare Workers, bajo la licencia Apache-2.0 el 27 de septiembre de 2022. [10][11]
- A fecha de 2026-11-23, Cloudflare Workers ofrece soporte de primera clase para JavaScript, TypeScript, Python y Rust, además de objetivos de compilación WebAssembly (Wasm) como C, C++, Kotlin y Go. [7]
- Para fechas de compatibilidad iguales o posteriores a 2026-08-04, Cloudflare Workers habilita tanto nodejs_compat como nodejs_compat_v2 de forma predeterminada. [9]
- A fecha de 2026-11-23, el plan Workers Free permite 100,000 solicitudes por día y 10 milisegundos de tiempo de CPU por invocación, mientras que el plan Workers Paid tiene un mínimo mensual de $5 USD e incluye 10 millones de solicitudes y 30 millones de milisegundos de CPU al mes sin cargos por transferencia saliente. [4]
- A fecha de 2026-11-23, Cloudflare Workers aplica un límite de memoria de 128 MB por aislado, un límite de tamaño de Worker sin comprimir de 64 MiB y un límite de tiempo de inicio de 1 segundo tanto en el plan Free como en el plan Paid. [5]
- El informe ante la SEC correspondiente al año fiscal 2025 de Cloudflare revela que una falla en junio de 2025 en la infraestructura de almacenamiento de terceros utilizada por Workers KV provocó una interrupción del servicio de varias horas sin un impacto financiero material. [2]

## Cronología

- 2017-09-29: Cloudflare anuncia Cloudflare Workers en el blog de Cloudflare, presentando JavaScript Service Workers ejecutados en el borde de la red de Cloudflare. [12]
- 2018-03-13: Cloudflare añade una actualización a la entrada de blog de lanzamiento de Cloudflare Workers de septiembre de 2017 registrando la disponibilidad del servicio. [12]
- 2022-09-27: Cloudflare anuncia la primera versión beta de workerd, liberando como código abierto el entorno de ejecución de JavaScript y WebAssembly de Cloudflare Workers bajo la licencia Apache-2.0. [11]
- 2024-03-01: Cloudflare migra las cuentas heredadas de Bundled Workers al modelo de uso Standard y aplica un límite automático de CPU de 50 milisegundos a los Bundled Workers migrados. [4]
- 2024-09-23: Cloudflare Workers comienza a inyectar automáticamente polyfills de unenv de Wrangler cuando nodejs_compat se habilita en esta fecha de compatibilidad o en una posterior. [9]
- 2025-06: Una falla en la infraestructura subyacente de almacenamiento de terceros utilizada por Workers KV provoca una interrupción del servicio de varias horas divulgada en el informe ante la SEC del año fiscal 2025 de Cloudflare. [2]
- 2026-08-04: Cloudflare Workers habilita tanto nodejs_compat como nodejs_compat_v2 de forma predeterminada para los Workers configurados con esta fecha de compatibilidad o una posterior. [9]

## Fuentes

1. WinterTC. Ecma International (WinterTC). https://wintertc.org/ (consultado 2026-11-23; tier 1: government or public registry)
2. cloud-20251231. U.S. Securities and Exchange Commission (EDGAR). https://www.sec.gov/Archives/edgar/data/1477333/000147733326000016/cloud-20251231.htm (consultado 2026-11-23; tier 1: government or public registry)
3. Overview · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/ (consultado 2026-11-23; tier 3: official site)
4. Pricing · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/pricing/ (consultado 2026-11-23; tier 3: official site)
5. Limits · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/platform/limits/ (consultado 2026-11-23; tier 3: official site)
6. How Workers works · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/reference/how-workers-works/ (consultado 2026-11-23; tier 3: official site)
7. Languages · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/languages/ (consultado 2026-11-23; tier 3: official site)
8. Runtime APIs · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/ (consultado 2026-11-23; tier 3: official site)
9. Node.js compatibility · Cloudflare Workers docs. Cloudflare. https://developers.cloudflare.com/workers/runtime-apis/nodejs/ (consultado 2026-11-23; tier 3: official site)
10. GitHub - cloudflare/workerd: The JavaScript / Wasm runtime that powers Cloudflare Workers · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/workerd (consultado 2026-11-23; tier 3: official site)
11. Introducing workerd: the Open Source Workers runtime | Cloudflare Blog. The Cloudflare Blog. publicado 2022-09-27. https://blog.cloudflare.com/workerd-open-source-workers-runtime/ (consultado 2026-11-23; tier 3: official site)
12. Introducing Cloudflare Workers: Run JavaScript Service Workers at the Edge | Cloudflare Blog. The Cloudflare Blog. publicado 2017-09-29. https://blog.cloudflare.com/introducing-cloudflare-workers/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Cloudflare Workers." Versión c3cd7316, 2026-11-25. https://mimirwiki.com/es/wiki/cloudflare-workers
