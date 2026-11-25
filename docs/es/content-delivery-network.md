---
title: "Red de distribución de contenidos"
subtitle: "Red geográficamente distribuida de servidores de caché que entrega contenido web desde ubicaciones cercanas a los usuarios finales"
canonical_url: https://mimirwiki.com/es/wiki/content-delivery-network
language: es
page_class: concept
revision_sha256: 44a5e98f3ce549bd5b8c6cae8f2ee263b8f0f0c3f1c7f5f7b4e63beb95811d2c
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/content-delivery-network.md
  txt: https://mimirwiki.com/es/wiki/content-delivery-network.txt
  json: https://mimirwiki.com/es/wiki/content-delivery-network.json
  jsonld: https://mimirwiki.com/es/wiki/content-delivery-network.jsonld
translations:
  en: https://mimirwiki.com/wiki/content-delivery-network
  ko: https://mimirwiki.com/ko/wiki/content-delivery-network
  ja: https://mimirwiki.com/ja/wiki/content-delivery-network
  zh: https://mimirwiki.com/zh/wiki/content-delivery-network
---

# Red de distribución de contenidos

> Una red de distribución de contenidos (CDN) es un grupo distribuido de servidores que almacena copias de contenido web en ubicaciones cercanas a los usuarios finales. Al actuar como una caché HTTP compartida gestionada entre clientes y servidores de origen, una CDN reduce la latencia, disminuye la carga del servidor de origen y mejora la disponibilidad. Diversos documentos del IETF cubren el almacenamiento en caché HTTP, los encabezados de caché dirigidos, la distribución de servicios anycast y la interconexión de CDN.

Una red de distribución de contenidos (CDN) es un sistema geográficamente distribuido de servidores que almacena copias de objetos web y atiende las solicitudes de los clientes desde ubicaciones cercanas a los usuarios finales. Al actuar como una caché HTTP compartida gestionada entre clientes y servidores de origen, una CDN reduce la latencia de respuesta, disminuye la carga del servidor de origen y mejora la fiabilidad de la entrega bajo tráfico elevado. Diversos documentos del Internet Engineering Task Force (IETF) cubren el almacenamiento en caché HTTP (RFC 9111), el control de caché dirigido para CDN (RFC 9213), la distribución de servicios anycast (RFC 4786) y la interconexión de CDN (RFC 6707 y RFC 7336). Los despliegues comerciales de CDN distribuyen tanto recursos estáticos como contenido web dinámico a través de puntos de presencia (PoP) en todo el mundo, al tiempo que introducen compromisos operativos en frescura de caché, exposición de seguridad y dependencias de disponibilidad de terceros.

**También conocido como:** CDN, Red de entrega de contenidos, Red de distribución de contenidos (CDN), Content Delivery Network

## Datos clave

- **Clasificación de caché:** Caché HTTP compartida gestionada [7]
- **Estándar de caché HTTP:** RFC 9111 (STD 98, junio de 2022) [1]
- **Encabezado de caché dirigido:** CDN-Cache-Control (RFC 9213, junio de 2022) [2]
- **Práctica de enrutamiento anycast:** RFC 4786 (BCP 126, diciembre de 2006), IPv4 e IPv6 mediante IGP o BGP [5]
- **Marco de interconexión:** Planteamiento del problema CDNI (RFC 6707) y marco de trabajo (RFC 7336) [4]

## Datos básicos

- **Categoría:** Infraestructura de red distribuida y caché HTTP compartida gestionada [7]
- **Nodos de borde:** Centros de datos geográficamente dispersos llamados ubicaciones de borde o puntos de presencia (PoP) [8]
- **Fuentes de origen:** Servidores HTTP autoritativos, servidores web o depósitos de almacenamiento de objetos [8]
- **Especificación de caché HTTP:** IETF RFC 9111 (STD 98, junio de 2022), deja obsoleta la RFC 7234 [1]
- **Control de caché dirigido:** Encabezado de respuesta CDN-Cache-Control (IETF RFC 9213, junio de 2022) [2]
- **Directivas dirigidas obligatorias:** max-age, must-revalidate, no-store, no-cache, private [2]
- **Documento de práctica anycast:** IETF RFC 4786 (BCP 126, diciembre de 2006) sobre IPv4 e IPv6 [5]
- **Planteamiento del problema CDNI:** IETF RFC 6707 (Informativa, septiembre de 2012) [3]
- **Marco de trabajo CDNI:** IETF RFC 7336 (Informativa, agosto de 2014), deja obsoleta la RFC 3466 [4]
- **Recursos principales entregados:** Recursos estáticos (HTML, CSS, JavaScript, imágenes, archivos multimedia) y contenido web dinámico [8]
- **Expiración predeterminada de CloudFront:** 24 horas (mínimo 0 segundos, sin máximo fijo) (al 2026-11-23) [8]
- **Salvaguarda de integridad en el cliente:** Subresource Integrity (SRI) para CDN de recursos estáticos de terceros [6]

## Arquitectura de una red de distribución de contenidos y puntos de presencia

Una red de distribución de contenidos (CDN) opera como un grupo geográficamente disperso de servidores de caché que almacena copias duplicadas de datos web y atiende las solicitudes de los clientes desde ubicaciones cercanas a los usuarios finales.[6][8] Los servidores de origen alojan la versión definitiva de los objetos web, como páginas HTML, hojas de estilo (CSS), archivos JavaScript, imágenes y archivos multimedia, y pueden ser servidores web, servidores HTTP personalizados o servicios de almacenamiento de objetos como depósitos de Amazon S3.[6][8] Las ubicaciones de borde, también denominadas puntos de presencia (PoP), son conjuntos de servidores en centros de datos dispersos donde una CDN almacena en caché copias de esos objetos cerca de los usuarios.[8]

Cuando un cliente solicita un objeto servido a través de una CDN, la red enruta la solicitud hacia una ubicación de borde que proporcione baja latencia.[8] Si ya existe una copia utilizable almacenada en esa ubicación de borde, el servidor la devuelve directamente sin reenviar la solicitud al servidor de origen.[7][8] Si el objeto no está presente, el servidor de borde recupera la versión definitiva del servidor de origen y guarda una copia en caché para solicitudes posteriores.[8] Dado que la distancia geográfica afecta proporcionalmente a la latencia, situar servidores más cerca de los usuarios finales acorta el tiempo de ida y vuelta de la entrega.[6] Los proveedores comerciales como Amazon CloudFront también enrutan las solicitudes a través de una red troncal privada (la red troncal de AWS) para reducir el número de redes intermedias atravesadas, disminuyendo el tiempo hasta el primer byte y aumentando las tasas de transferencia de datos, al tiempo que almacenan copias en múltiples ubicaciones de borde para mejorar la disponibilidad.[8]

En la arquitectura HTTP, una CDN actúa como una caché compartida gestionada desplegada explícitamente por los operadores de servicios para descargar de los servidores de origen el análisis de solicitudes, la restauración de sesiones basadas en cookies, las consultas a bases de datos y la renderización de plantillas.[7] La RFC 6707 identifica tres beneficios principales del despliegue de CDN para contenido almacenable en caché: menor coste de entrega, mejor calidad de experiencia para los usuarios finales y mayor robustez en la entrega.[3] Las CDN se utilizan ampliamente para entregar bibliotecas estáticas (como Bootstrap y jQuery), sitios web estáticos completos y contenido web dinámico.[6][8] A fecha de 2026-11-23, Amazon CloudFront propaga las configuraciones de distribución (servidores de origen, registro, nombres de dominio asignados o personalizados y controles de acceso como URL firmadas y cookies firmadas para contenido privado) a todas las ubicaciones de borde mientras obtiene objetos bajo demanda, ofreciendo tanto distribuciones estándar independientes como distribuciones multiinquilino mediante CloudFront SaaS Manager.[8] A fecha de 2026-11-23, CloudFront mantiene los objetos en caché en las ubicaciones de borde durante 24 horas de forma predeterminada (con un mínimo de 0 segundos y sin máximo fijo), factura por la transferencia de datos salientes desde las ubicaciones de borde y las solicitudes HTTP o HTTPS, y no cobra tarifa de transferencia desde orígenes de AWS (Amazon S3, Elastic Load Balancing y Amazon API Gateway) hacia CloudFront.[8]

## Mecánica de caché HTTP en redes de distribución de contenidos (RFC 9111)

El almacenamiento en caché en una red de distribución de contenidos se basa en la especificación HTTP Caching, publicada por el Internet Engineering Task Force (IETF) en junio de 2022 como RFC 9111 (STD 98), editada por R. Fielding (Adobe), M. Nottingham (Fastly) y J. Reschke (greenbytes), que deja obsoleta la RFC 7234.[1] La RFC 9111 define una caché HTTP como un almacén local de mensajes de respuesta junto con el subsistema que controla el almacenamiento, la recuperación y la eliminación, lo que reduce el tiempo de respuesta y el consumo de ancho de banda de red en solicitudes posteriores equivalentes.[1]

El almacenamiento en caché HTTP divide las cachés en cachés privadas, que sirven a un único usuario (normalmente dentro de un navegador web), y cachés compartidas, situadas en intermediarios entre clientes y servidores para atender a múltiples usuarios.[1][7] MDN Web Docs subdivide además las cachés compartidas en cachés proxy, habitualmente operadas fuera del control del desarrollador del servicio, y cachés gestionadas desplegadas explícitamente por los operadores del servicio, entre las que se incluyen proxies inversos, CDN y service workers que utilizan la Cache API.[7] Con la adopción generalizada del cifrado HTTPS, las cachés proxy de red a lo largo del trayecto suelen tunelizar el tráfico cifrado sin inspeccionar ni almacenar respuestas en caché, salvo en entornos empresariales controlados donde un proxy puente TLS descifra el tráfico mediante una autoridad de certificación gestionada por la organización.[7]

Una caché identifica las respuestas almacenadas mediante una clave de caché compuesta como mínimo por el método de solicitud y el URI de destino, aunque muchas cachés desplegadas solo almacenan respuestas `GET` indexadas por URI.[1] Para los recursos con negociación de contenido, las cachés incorporan en la clave de caché los encabezados de solicitud especificados en el encabezado de respuesta `Vary`.[1] La mayoría de los elementos almacenados son respuestas `200 (OK)` a solicitudes `GET`, aunque también pueden almacenarse redirecciones, respuestas `404 (Not Found)` y respuestas `206 (Partial Content)` cuando las reglas lo permiten.[1] Según la sección 3 de la RFC 9111, una caché compartida debe evitar almacenar una respuesta cuando esté presente `no-store`, cuando esté presente `private` sin permitir un almacenamiento compartido modificado, o cuando la solicitud contenga un encabezado `Authorization` sin una directiva de respuesta que permita explícitamente el almacenamiento compartido; el almacenamiento también requiere un método comprendido, un código de estado final y un indicador de caché como `public`, `Expires`, `max-age`, `s-maxage`, una extensión de caché o un código de estado almacenable heurísticamente.[1]

Las respuestas almacenadas existen en uno de dos estados: frescas (reutilizables sin contactar con el origen) u obsoletas (que requieren validación en el origen para renovarse, salvo que una caché desconectada tenga permiso para entregar contenido obsoleto).[1][7] La frescura emplea valores `delta-seconds` no negativos limitados a `2147483648` (2^31, más de 68 años) para evitar desbordamientos de enteros.[1] Las cachés compartidas notifican el tiempo transcurrido en almacenamiento mediante el encabezado `Age`; por ejemplo, una respuesta con `Cache-Control: max-age=604800` (una semana) almacenada por una caché compartida durante un día se sirve con `Age: 86400`, dejando 518 400 segundos de frescura restante para los clientes descendentes.[7] Cuando se omite `Cache-Control`, el almacenamiento heurístico puede reutilizar respuestas con un encabezado `Last-Modified` durante aproximadamente el 10 % del tiempo transcurrido desde la última modificación.[7] Dado que el almacenamiento en caché HTTP base no define ningún mecanismo de eliminación explícita, las cachés gestionadas como las CDN ofrecen purgado fuera de banda mediante paneles de control, llamadas a la API o reinicios, y pueden ejecutar lógica de caché personalizada como reglas de Varnish Configuration Language (VCL).[7]

| Encabezado o directiva | Alcance | Función en la caché HTTP y de CDN |
| --- | --- | --- |
| `Cache-Control: max-age` | Cachés privadas y compartidas | Establece la vigencia de frescura en segundos desde la generación de la respuesta.[1][7] |
| `Cache-Control: s-maxage` | Cachés compartidas | Establece la vigencia de frescura específicamente para cachés compartidas.[1][2] |
| `Cache-Control: private` | Cachés privadas | Restringe el almacenamiento de respuestas personalizadas a cachés de un solo usuario.[1][7] |
| `Cache-Control: no-store` | Todas las cachés estándar | Impide que las cachés almacenen la respuesta.[1] |
| `Cache-Control: no-cache` | Todas las cachés estándar | Exige validación en el origen antes de reutilizar una respuesta almacenada.[1][2] |
| `Age` | Cachés compartidas | Informa los segundos transcurridos desde que se generó la respuesta.[1][7] |
| `Expires` | HTTP/1.0 y HTTP/1.1 heredados | Especifica la expiración de la caché mediante una marca de tiempo explícita.[1][7] |
| `Vary` | Construcción de la clave de caché | Enumera los encabezados de solicitud incorporados en la clave de caché para la negociación de contenido.[1] |

## Control de caché HTTP dirigido y CDN-Cache-Control (RFC 9213)

Los despliegues de redes de distribución de contenidos suelen situarse dentro de topologías de caché multicapa junto con cachés del servidor de origen, cachés de la red de origen y cachés del navegador, lo que genera la necesidad de dirigir distintas políticas de caché a cada clase de caché.[2] Aunque `Cache-Control` incluye `s-maxage` para cachés compartidas, carece de una orientación coherente en otras directivas como `stale-while-revalidate`.[2] Las implementaciones anteriores de CDN dependían de encabezados específicos de cada proveedor, como `Surrogate-Control`, lo que daba lugar a una baja interoperabilidad entre proveedores.[2][7]

En junio de 2022, el IETF publicó la RFC 9213 (Standards Track), *Targeted HTTP Cache Control*, escrita por S. Ludin (Akamai), M. Nottingham (Fastly) y Y. Wu ([Cloudflare](https://mimirwiki.com/es/wiki/cloudflare)).[2] La RFC 9213 establece una convención general para los encabezados de respuesta HTTP de control de caché dirigido (Targeted Cache-Control) y define `CDN-Cache-Control` específicamente para las cachés de CDN.[2] Los editores que mantienen una relación de invalidación con su CDN pueden asignar vigencias más largas en `CDN-Cache-Control` mientras conservan vigencias más cortas en `Cache-Control` para navegadores y otros intermediarios.[2]

Los encabezados de control de caché dirigido se definen como campos estructurados de diccionario HTTP (HTTP Dictionary Structured Fields) en los que cada miembro del diccionario es una directiva de respuesta de caché HTTP (incluidas las directivas de extensión), con valores asignados a los tipos Boolean, String, Token, Integer o Decimal de Structured Fields.[2] Dado que el manejo de errores difiere del de `Cache-Control`, las implementaciones utilizan un analizador de Structured Fields para los campos dirigidos e ignoran cualquier campo que esté vacío o produzca un error de análisis, recurriendo a otros mecanismos de control de caché.[2]

Cada caché que implementa la RFC 9213 mantiene una lista ordenada de nombres de encabezado objetivo de mayor a menor prioridad, como `[ExampleCDN-Cache-Control, CDN-Cache-Control]`.[2] Para cada respuesta recibida, la caché selecciona el primer campo válido y no vacío de su lista objetivo para regir el comportamiento de caché e ignora `Cache-Control` y `Expires` en esa respuesta.[2] Los campos dirigidos ausentes de la lista objetivo de una caché deben dejarse pasar sin alterar el comportamiento de dicha caché.[2] Las cachés compatibles deben implementar cinco directivas dentro de los campos dirigidos: `max-age`, `must-revalidate`, `no-store`, `no-cache` y `private`.[2] La precedencia coincide con `Cache-Control`, de modo que `no-store` y `no-cache` invalidan `max-age`, y las directivas de extensión no reconocidas se ignoran.[2]

## Distribución de servicios anycast (RFC 4786)

El enrutamiento anycast, documentado en la práctica recomendada del IETF RFC 4786 (BCP 126, diciembre de 2006) por J. Abley (Afilias Canada) y K. Lindqvist (Netnod Internet Exchange), hace que una misma dirección de servicio sea alcanzable en dos o más nodos discretos, y el sistema de enrutamiento entrega cada solicitud de cliente a uno de ellos.[5] La RFC 4786 describe la práctica para servicios de Internet en general y utiliza los servidores DNS como ejemplo principal.[5] Para desplegar anycast, un operador asocia una dirección de servicio estable (IPv4 o IPv6) con dos o más nodos anycast discretos y anuncia la alcanzabilidad hacia esa dirección dentro de un sistema de enrutamiento.[5]

Cuando un cliente envía paquetes a una dirección de servicio anycast, el sistema de enrutamiento dirige los datagramas a uno de los nodos disponibles en función de la topología de la red y del punto de origen de la solicitud.[5] La región topológica de una red cuyos paquetes llegan a un nodo concreto se denomina su zona de captación (*catchment*).[5] La RFC 4786 distingue dos alcances de despliegue: anycast de alcance local, que propaga rutas mediante un protocolo de pasarela interior (IGP) para que un nodo solo sea visible dentro de un subconjunto del sistema de enrutamiento, y anycast de alcance global, que anuncia la alcanzabilidad en toda la Internet global mediante el protocolo de pasarela de frontera (BGP, RFC 4271).[5] Anycast funciona sin necesidad de referencias de servidor ni DNS round-robin, aunque las aplicaciones pueden combinar anycast con distribución basada en nombres cuando resulte necesario.[5]

La RFC 4786 documenta varias limitaciones operativas inherentes a la distribución de servicios anycast.[5]

- Estado y duración de las transacciones: anycast impone restricciones a las transacciones de larga duración, al estado de transacción en el lado del servidor y a la sincronización de datos entre nodos.[5]
- Distribución desigual de la carga: resulta difícil lograr un balanceo de carga de grano fino entre nodos anycast porque la topología de enrutamiento determina el tamaño de la zona de captación, dejando las cargas de solicitudes y tráfico generalmente desequilibradas entre nodos, aunque anycast respalda la fiabilidad y el escalado de grano grueso.[5]
- Monitorización de disponibilidad: medir la disponibilidad es más complejo bajo anycast porque la alcanzabilidad observada varía según la ubicación de red del cliente, y la población de clientes atendida por cada nodo no es estática ni determinista de forma fiable.[5]

## Estándares de interconexión de redes de distribución de contenidos (RFC 6707 y RFC 7336)

La interconexión de redes de distribución de contenidos (CDNI) permite que redes de distribución de contenidos independientes interoperen entre sí para que una CDN pueda entregar contenido a los usuarios finales en nombre de otra CDN.[3] El crecimiento del tráfico de vídeo y multimedia impulsó a los operadores comerciales de CDN a ampliar su capacidad y llevó a muchos proveedores de servicios de red (NSP) a desplegar sus propias CDN.[3] Dado que una sola CDN puede carecer de presencia geográfica o de recursos suficientes cerca de la red de acceso de cada usuario final, la interconexión de CDN separadas agrupa cobertura y capacidad para la entrega de extremo a extremo desde los proveedores de servicios de contenido (CSP) hasta los usuarios finales.[3]

El IETF definió este espacio de problemas en la RFC 6707 (Informativa, septiembre de 2012, por B. Niven-Jenkins, F. Le Faucheur y N. Bitar) y estableció la arquitectura general en la RFC 7336 (Informativa, agosto de 2014, por L. Peterson, B. Davie y R. van Brandenburg); la RFC 7336 deja obsoleta la RFC 3466.[3][4] En el modelo CDNI, un CSP contrata a una CDN autoritativa o ascendente (`uCDN`), que puede atender solicitudes por sí misma o delegar la entrega a una o más CDN descendentes (`dCDN`), como una CDN operada por un NSP; la CDN descendente final que atiende al usuario final es la CDN de entrega (Delivering CDN).[3][4]

Durante un flujo de entrega interconectado, un agente de usuario contacta primero con la CDN ascendente, que puede redirigir la solicitud mediante redirección DNS o redirección HTTP a una CDN descendente más cercana al usuario.[3][4] La RFC 7336 distingue la redirección iterativa de solicitudes CDNI (donde la CDN ascendente redirige al cliente al sistema de enrutamiento de solicitudes de la CDN descendente según su lógica local) de la redirección recursiva de solicitudes CDNI (donde la CDN ascendente consulta primero la interfaz de redirección de la CDN descendente e incorpora esa respuesta, pudiendo redirigir al cliente directamente a un servidor sustituto descendente).[4] Si la CDN descendente carece del elemento solicitado, adquiere el objeto de la CDN ascendente, que a su vez lo obtiene del CSP cuando es necesario.[3] Las reglas y metadatos de CDNI se aplican a un `CDN-Domain` (un FQDN que representa un conjunto de contenidos), mientras que un `Distinguished CDN-Domain` se asigna estrictamente para la adquisición o redirección entre CDN y nunca aparece en las solicitudes de los clientes.[4]

| Interfaz CDNI | Momento de operación | Función definida en la RFC 6707 y la RFC 7336 |
| --- | --- | --- |
| Interfaz de control CDNI | Arranque y operaciones de disparo | Coordina acciones administrativas e incluye la interfaz de disparo (Trigger Interface) para preposicionar, revalidar y purgar metadatos y contenido ante acciones del CSP.[3][4] |
| Interfaz de enrutamiento de solicitudes CDNI | Síncrona y asíncrona | Gestiona la redirección de solicitudes DNS o HTTP entre CDN ascendentes y descendentes e intercambia anuncios dinámicos de cobertura.[3][4] |
| Interfaz de metadatos CDNI | Síncrona o asíncrona | Intercambia metadatos de distribución y políticas de entrega acotadas a CDN-Domains entre CDN interconectadas.[3][4] |
| Interfaz de registro CDNI | Tiempo real y fuera de línea | Intercambia registros de entrega entre CDN pares para contabilidad y visibilidad operativa.[3][4] |

## Limitaciones, obsolescencia y riesgos de seguridad de las redes de distribución de contenidos

Los despliegues de redes de distribución de contenidos conllevan compromisos operativos y de seguridad relacionados con la obsolescencia de la caché, la privacidad en cachés compartidas, las interrupciones de terceros y la integridad de los recursos.[1][2][6][7]

Dado que HTTP utiliza un único modelo de frescura de extremo a extremo, configurar vigencias de frescura más largas en una CDN que en las cachés descendentes puede reducir la eficiencia de estas últimas.[2] La RFC 9213 ilustra esta interacción con una respuesta entregada con `Age: 1800`, `Cache-Control: max-age=600` y `CDN-Cache-Control: max-age=3600`: pasados 30 minutos, el objeto sigue siendo fresco para la caché de la CDN mientras aparece ya obsoleto para las cachés descendentes regidas por el límite de 600 segundos.[2] Además, una caché desconectada que no puede alcanzar un servidor de origen puede entregar respuestas obsoletas bajo las condiciones permitidas.[1]

Depender de una CDN externa introduce una dependencia de disponibilidad de terceros.[6] MDN Web Docs señala que si una CDN de terceros sufre una interrupción, resulta bloqueada en una región o cierra de forma permanente, los sitios web que dependen de ella dejan de funcionar correctamente.[6] Cargar bibliotecas de terceros como Bootstrap o jQuery desde un dominio de CDN externo también puede degradar el rendimiento en ciertos escenarios: los navegadores deben realizar resoluciones DNS adicionales y establecer conexiones con el host de terceros, y los navegadores modernos particionan las cachés HTTP por origen (mediante doble clave con la identidad del sitio referente para mitigar riesgos de privacidad y ataques de temporización), por lo que la misma biblioteca de terceros debe seguir descargándose por separado para cada sitio.[1][6]

Las cachés compartidas de CDN también presentan riesgos de seguridad y aislamiento de datos.[1][6][7] Comprometer una CDN de terceros permite a los atacantes servir contenido malicioso a los visitantes de los sitios dependientes, lo que hace necesarias salvaguardas en el lado del cliente como Subresource Integrity (SRI) para recursos estáticos de terceros.[6] Almacenar respuestas personalizadas en una caché compartida sin marcarlas con `Cache-Control: private` puede exponer los datos de un usuario a otros usuarios, y la sola presencia de una cookie no marca una respuesta HTTP como privada.[7] La RFC 9111 identifica además el envenenamiento de caché, los ataques de temporización y el almacenamiento en caché de información sensible como consideraciones fundamentales de seguridad para los sistemas de caché HTTP.[1]

## Preguntas frecuentes

### ¿Qué es una red de distribución de contenidos (CDN)?

Una red de distribución de contenidos (CDN) es un grupo geográficamente distribuido de servidores que almacena copias de contenido web y atiende solicitudes desde ubicaciones de borde cercanas a los usuarios finales. Al actuar como una caché HTTP compartida gestionada entre clientes y servidores de origen, una CDN reduce la latencia, disminuye la carga del servidor de origen y mejora la disponibilidad. [6][7][8]

### ¿En qué se diferencia CDN-Cache-Control del encabezado estándar Cache-Control?

Las directivas estándar de Cache-Control definidas en la RFC 9111 se aplican de forma general a navegadores y cachés compartidas, con una capacidad limitada de orientación por capa. CDN-Cache-Control, estandarizado en la RFC 9213 en junio de 2022, es un campo estructurado de diccionario dirigido específicamente a las cachés de CDN, de modo que los editores pueden establecer políticas de caché de CDN separadas mientras la CDN ignora Cache-Control y Expires para esa respuesta. [2][7]

### ¿Qué es el enrutamiento anycast BGP según la RFC 4786?

El enrutamiento anycast BGP de alcance global, documentado en la RFC 4786 (BCP 126), anuncia la misma dirección de servicio IP desde múltiples ubicaciones discretas para que el sistema de enrutamiento elija el nodo para cada solicitud según su topología y el punto donde se origina la solicitud. Respalda la fiabilidad del servicio y el escalado de grano grueso sin requerir referencias DNS round-robin, aunque la carga de tráfico entre nodos tiende a permanecer desigual. [5]

### ¿Qué es la interconexión de CDN (CDNI)?

La interconexión de CDN (CDNI), descrita en la RFC 6707 y estructurada en la RFC 7336, es una relación entre CDN independientes que permite a una CDN ascendente autoritativa delegar la entrega de contenido a una CDN descendente más cercana a los usuarios finales. Coordina la entrega a través de cuatro áreas de interfaz: Control (incluida una interfaz de disparo), Enrutamiento de solicitudes, Metadatos y Registro. [3][4]

### ¿Puede una CDN exponer datos personalizados de usuarios o entregar contenido obsoleto?

Sí. Dado que una CDN opera como una caché compartida, almacenar respuestas personalizadas sin la directiva Cache-Control: private puede exponer el contenido de un usuario a otros usuarios, y las cookies por sí solas no marcan una respuesta como privada. Además, asignar a una CDN una vigencia de frescura mayor que la de las cachés descendentes puede provocar que las respuestas lleguen ya obsoletas a dichas cachés. [2][7]

### ¿Qué riesgos conlleva cargar bibliotecas estáticas desde una CDN de terceros?

MDN Web Docs enumera tres inconvenientes frente al autoalojamiento de recursos estáticos: una interrupción, un bloqueo regional o el cierre de un tercero pueden hacer fallar los sitios web dependientes; una CDN comprometida puede entregar archivos maliciosos si no se mitiga con controles como Subresource Integrity (SRI); y los orígenes separados añaden sobrecarga de resolución DNS y establecimiento de conexión, mientras que el particionamiento de caché de los navegadores impide la reutilización de recursos entre sitios. [6]

## Frases citables

- El IETF publicó la RFC 9111 (STD 98) en junio de 2022 como la especificación HTTP Caching de Standards Track, dejando obsoleta la RFC 7234. [1]
- La RFC 9213, publicada en junio de 2022 por autores de Akamai, Fastly y Cloudflare, define el encabezado de respuesta HTTP CDN-Cache-Control para las cachés de CDN. [2]
- Según la RFC 9213, las cachés que implementan un campo de control de caché dirigido deben admitir las directivas max-age, must-revalidate, no-store, no-cache y private. [2]
- La RFC 4786 (BCP 126), publicada en diciembre de 2006, documenta las prácticas operativas para distribuir servicios en múltiples ubicaciones mediante anycast IPv4 e IPv6 sobre IGP o BGP. [5]
- La RFC 6707 (septiembre de 2012) y la RFC 7336 (agosto de 2014) definen el planteamiento del problema y el marco de trabajo para la interconexión de redes de distribución de contenidos (CDNI); la RFC 7336 deja obsoleta la RFC 3466. [3][4]
- Los navegadores modernos particionan las cachés HTTP por origen por motivos de privacidad, lo que requiere descargas separadas de bibliotecas de CDN de terceros en cada sitio web. [6]
- Las cachés gestionadas, como las CDN, permiten la eliminación explícita de respuestas almacenadas mediante paneles de control, llamadas a la API o reinicios, una capacidad ajena a la especificación base de caché HTTP. [7]
- A fecha de 2026-11-23, Amazon CloudFront almacena objetos en caché en las ubicaciones de borde durante 24 horas de forma predeterminada, con un tiempo de expiración mínimo de 0 segundos y sin máximo fijo. [8]

## Cronología

- 2006-12: El IETF publica la RFC 4786 (BCP 126), Operation of Anycast Services, que documenta las prácticas de anycast IGP de alcance local y BGP de alcance global. [5]
- 2012-09: El IETF publica la RFC 6707, Content Distribution Network Interconnection (CDNI) Problem Statement, que delimita cuatro interfaces CDNI. [3]
- 2014-08: El IETF publica la RFC 7336, Framework for Content Distribution Network Interconnection (CDNI), dejando obsoleta la RFC 3466. [4]
- 2022-06: El IETF publica la RFC 9111 (STD 98), HTTP Caching, que deja obsoleta la RFC 7234, junto con la RFC 9213, Targeted HTTP Cache Control, que estandariza el encabezado de respuesta CDN-Cache-Control. [1][2]

## Fuentes

1. RFC 9111: HTTP Caching. Internet Engineering Task Force (IETF). publicado 2022-06. https://www.rfc-editor.org/rfc/rfc9111.txt (consultado 2026-11-23; tier 1: government or public registry)
2. RFC 9213: Targeted HTTP Cache Control. Internet Engineering Task Force (IETF). publicado 2022-06. https://www.rfc-editor.org/rfc/rfc9213.txt (consultado 2026-11-23; tier 1: government or public registry)
3. RFC 6707: Content Distribution Network Interconnection (CDNI) Problem Statement. Internet Engineering Task Force (IETF). publicado 2012-09. https://www.rfc-editor.org/rfc/rfc6707.txt (consultado 2026-11-23; tier 1: government or public registry)
4. RFC 7336: Framework for Content Distribution Network Interconnection (CDNI). Internet Engineering Task Force (IETF). publicado 2014-08. https://www.rfc-editor.org/rfc/rfc7336.txt (consultado 2026-11-23; tier 1: government or public registry)
5. RFC 4786: Operation of Anycast Services. Internet Engineering Task Force (IETF). publicado 2006-12. https://www.rfc-editor.org/rfc/rfc4786.txt (consultado 2026-11-23; tier 1: government or public registry)
6. CDN - Glossary | MDN. MDN Web Docs. publicado 2025-07-11. https://developer.mozilla.org/en-US/docs/Glossary/CDN (consultado 2026-11-23; tier 3: official site)
7. HTTP caching - HTTP | MDN. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching (consultado 2026-11-23; tier 3: official site)
8. What is Amazon CloudFront? - Amazon CloudFront. Amazon Web Services. https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Red de distribución de contenidos." Versión 44a5e98f, 2026-11-25. https://mimirwiki.com/es/wiki/content-delivery-network
