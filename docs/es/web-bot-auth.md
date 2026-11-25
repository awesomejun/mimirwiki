---
title: "Web Bot Auth"
subtitle: "Protocolo de autenticación criptográfica para clientes HTTP automatizados y agentes de IA basado en RFC 9421 HTTP Message Signatures"
canonical_url: https://mimirwiki.com/es/wiki/web-bot-auth
language: es
page_class: anchor
revision_sha256: cfad48a8cfacc5ec16ba605fa659fef82581b927d6aa3e1f28912ebdc27c54dc
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/web-bot-auth.md
  txt: https://mimirwiki.com/es/wiki/web-bot-auth.txt
  json: https://mimirwiki.com/es/wiki/web-bot-auth.json
  jsonld: https://mimirwiki.com/es/wiki/web-bot-auth.jsonld
translations:
  en: https://mimirwiki.com/wiki/web-bot-auth
  ko: https://mimirwiki.com/ko/wiki/web-bot-auth
  ja: https://mimirwiki.com/ja/wiki/web-bot-auth
  zh: https://mimirwiki.com/zh/wiki/web-bot-auth
---

# Web Bot Auth

> Web Bot Auth es un protocolo de autenticación criptográfica para clientes HTTP automatizados, incluidos rastreadores y agentes de IA, basado en RFC 9421 HTTP Message Signatures. Los clientes firman las solicitudes salientes con una clave privada y publican sus claves públicas en un directorio JWKS, habitualmente en /.well-known/http-message-signatures-directory, lo que permite a los servidores verificar su identidad. El grupo de trabajo webbotauth del IETF desarrolla la especificación.

Web Bot Auth es un protocolo de autenticación criptográfica que permite a los clientes HTTP automatizados, como rastreadores web y agentes de IA, firmar solicitudes salientes mediante RFC 9421 HTTP Message Signatures para que los servidores web puedan verificar su identidad. Los clientes automatizados adjuntan las cabeceras Signature, Signature-Input y Signature-Agent a las solicitudes y publican sus claves públicas de firma en un directorio JSON Web Key Set (JWKS) servido sobre HTTPS, habitualmente en el URI bien conocido /.well-known/http-message-signatures-directory. El grupo de trabajo Web Bot Auth (webbotauth) del Internet Engineering Task Force (IETF) desarrolla la especificación de Standards Track en draft-ietf-webbotauth-httpsig-protocol, redactada por Thibault Meunier, de Cloudflare, y Sandor Major, de Google. Cloudflare incorporó Web Bot Auth con claves de firma Ed25519 a su Verified Bots Program en julio de 2025.

**También conocido como:** webbotauth, HTTP Message Signatures para tráfico automatizado, RFC 9421 Web Bot Auth

## Datos clave

- **Estándar base:** RFC 9421 (HTTP Message Signatures, febrero de 2024) [1]
- **Organismo de estandarización:** Grupo de trabajo Web Bot Auth (webbotauth) del IETF [2]
- **Especificación activa:** draft-ietf-webbotauth-httpsig-protocol-01 (2026-10-29) (al 2026-11-23) [4]
- **Directorio de claves bien conocido:** /.well-known/http-message-signatures-directory [9]
- **Cabeceras HTTP principales:** Signature, Signature-Input, Signature-Agent [9]

## Datos básicos

- **Tipo:** Protocolo criptográfico de autenticación HTTP para clientes automatizados [5]
- **Estándar base:** RFC 9421: HTTP Message Signatures (febrero de 2024) [1]
- **Grupo de trabajo:** IETF Web Bot Auth (webbotauth), área Web and Internet Transport (al 2026-11-23) [2]
- **Presidentes del grupo:** David Schinazi, Rifaat Shekh-Yusef (al 2026-11-23) [2]
- **Autores de la especificación:** Thibault Meunier (Cloudflare), Sandor Major (Google) (al 2026-11-23) [4]
- **Borrador actual:** draft-ietf-webbotauth-httpsig-protocol-01 (publicado el 2026-10-29) (al 2026-11-23) [4]
- **Ruta del directorio de claves:** /.well-known/http-message-signatures-directory [9]
- **Tipo de medio del directorio:** application/http-message-signatures-directory+json [4]
- **Algoritmo admitido por Cloudflare:** Ed25519 (JSON Web Key OKP) (al 2026-10-08) [9]
- **Estado del borrador:** Internet-Draft activo del IETF (previsto para Standards Track) (al 2026-11-23) [4]
- **Repositorio de referencia:** github.com/cloudflare/web-bot-auth (licencia Apache-2.0) [12]

## Qué es Web Bot Auth

Web Bot Auth es un protocolo para autenticar criptográficamente clientes HTTP automatizados, incluidos rastreadores de índices de búsqueda, archivadores web, comprobadores de enlaces, rastreadores de entrenamiento de IA y agentes de IA que actúan en nombre de usuarios finales.[2][5] El protocolo se basa en RFC 9421, la especificación Standards Track del IETF para HTTP Message Signatures publicada en febrero de 2024, que permite firmas digitales separadas sobre componentes seleccionados de un mensaje HTTP.[1][4] Web Bot Auth opera únicamente en la capa HTTP, dejando sin cambios la capa de transporte y la pila TLS para que las firmas sigan siendo verificables a través de proxies inversos, pasarelas y otros intermediarios HTTP.[1][5]

Los mecanismos convencionales de identificación de bots presentan inconvenientes operativos y de seguridad.[2][5] Las cadenas `User-Agent` pueden ser suplantadas por clientes arbitrarios y se ven sobrecargadas cuando un navegador automatizado como Chromium envía una cadena de navegador estándar para asegurar la correcta renderización de la página.[5] Las listas de direcciones IP permitidas exigen mantener listados en plataformas en la nube con propiedad de direcciones por capas, mientras que los bloques de IP dedicados conllevan costes de adquisición, configuración especializada e historial de reputación previo.[5] Los secretos compartidos, como los tokens Bearer de OAuth, requieren registro por sitio y complican la rotación de claves a escala web.[5]

Web Bot Auth aborda estos requisitos bajo dos objetivos declarados y dos restricciones en `draft-ietf-webbotauth-httpsig-protocol`.[5] Sus objetivos son la continuidad de la confianza en el bot entre solicitudes y la vinculación opcional de las claves de firma a un ancla externa, como un nombre de dominio.[5] Sus restricciones son preservar la simplicidad operativa tanto para los clientes automatizados como para los sitios web y no exigir ninguna relación previa establecida entre el cliente y el servidor de origen.[5] Cloudflare propuso públicamente este enfoque el 15 de mayo de 2025 e incorporó HTTP Message Signatures a su Verified Bots Program el 1 de julio de 2025.[10][11]

## Cómo Web Bot Auth firma y verifica las solicitudes HTTP

Web Bot Auth emplea firmas separadas definidas por RFC 9421 para autenticar solicitudes HTTP salientes sin duplicar las cabeceras del mensaje dentro de una carga útil de token independiente.[1][5] Un cliente automatizado selecciona campos de cabecera HTTP y componentes derivados, los serializa en una base de firma canónica según las reglas de RFC 9421 y calcula una firma digital con una clave privada custodiada por el proveedor del bot.[1][5] RFC 9421 define algoritmos como RSASSA-PSS con SHA-512, RSASSA-PKCS1-v1_5 con SHA-256, HMAC con SHA-256, ECDSA con las curvas P-256 y P-384, y EdDSA con la curva edwards25519 (Ed25519).[1] Los vectores de prueba de `draft-ietf-webbotauth-httpsig-protocol-01` cubren RSASSA-PSS con SHA-512 y Ed25519, mientras que la implementación en producción de Cloudflare admite Ed25519.[4][9]

Las solicitudes firmadas incluyen tres campos principales de cabecera HTTP.[1][9] La cabecera `Signature-Input` enumera los componentes cubiertos del mensaje y los parámetros de metadatos de la firma, la cabecera `Signature` transporta los bytes de la firma codificados en base64, y la cabecera `Signature-Agent` identifica la URL HTTPS desde la que puede obtenerse el directorio de claves públicas del cliente.[1][4][5][9] Dado que las firmas de RFC 9421 no cubren directamente los cuerpos de los mensajes HTTP, las aplicaciones que necesitan integridad del cuerpo recurren a una cabecera `Content-Digest` con un hash criptográfico del contenido.[1][9] RFC 9421 también define una cabecera opcional `Accept-Signature` mediante la cual un destinatario puede solicitar que los mensajes HTTP posteriores incluyan firmas.[1]

Los parámetros de metadatos estándar en `Signature-Input` acotan el alcance y el tiempo de vida de la firma.[1][5][9]

| Parámetro o cabecera | Función en Web Bot Auth |
| --- | --- |
| `Signature-Agent` | Transporta la URL HTTPS del directorio de claves públicas del cliente para el descubrimiento en banda.[4][5] |
| `Signature-Input` | Enumera los componentes HTTP cubiertos (como `@authority` y `signature-agent`) y los metadatos de la firma.[1][9] |
| `Signature` | Contiene la firma criptográfica separada sobre la base de firma canonizada.[1][9] |
| `tag` | Identifica el contexto de aplicación, usando `web-bot-auth` para solicitudes de bots y `http-message-signatures-directory` para respuestas firmadas de directorio en la implementación de Cloudflare.[9] |
| `keyid` | Almacena la huella digital JSON Web Key (JWK) codificada en base64url que identifica qué clave pública verifica la firma.[5][9] |
| `created` y `expires` | Especifican marcas de tiempo Unix que delimitan la ventana de validez de la firma para limitar la exposición a ataques de repetición.[5][9] |
| `nonce` | Proporciona un valor opcional por solicitud destinado a mitigar los ataques de repetición.[9] |

## Directorios de claves y modelo de confianza de Web Bot Auth

Web Bot Auth publica las claves públicas de firma en un directorio JSON Web Key Set (JWKS) servido sobre HTTPS, lo que permite a los verificadores descubrir claves en banda a partir de la cabecera `Signature-Agent`.[4][5][6] Borradores individuales anteriores (`draft-meunier-http-message-signatures-directory`, actualizado hasta la revisión 05 el 2 de marzo de 2026) especificaban este formato de directorio por separado antes de que el grupo de trabajo consolidara el descubrimiento de claves en `draft-ietf-webbotauth-httpsig-protocol`.[3][4][6] El borrador registra el tipo de medio `application/http-message-signatures-directory+json` y el URI bien conocido `/.well-known/http-message-signatures-directory`.[4] Conforme a RFC 8615, el prefijo de ruta `/.well-known/` está reservado en la raíz de un origen HTTP o HTTPS, por lo que alojar el directorio de claves en esa ruta vincula el conjunto de claves al operador del dominio.[5][7]

En el modelo de confianza definido por `draft-ietf-webbotauth-httpsig-protocol-01`, la URL HTTPS verificada de `Signature-Agent` sirve como identificador persistente del agente.[5] Una cabecera `Signature-Agent` sin resolver constituye una afirmación no verificada, y los verificadores deben posponer la aplicación de políticas de acceso hasta resolver la URL sobre TLS y comprobar la firma de la solicitud con una clave devuelta por ese directorio.[5] Dado que la identidad se asocia a la URL mientras que `keyid` selecciona una clave concreta, un operador puede rotar claves sin interrumpir la continuidad publicando una clave nueva junto a la existente y retirando posteriormente la anterior.[5] Cuando un verificador posee una clave directamente sin una URL resuelta, la atribución recae en la huella digital `keyid`, que no mantiene continuidad entre rotaciones de claves.[5]

Resolver un directorio de claves sobre TLS establece que el host nombrado en la URL sirvió ese conjunto de claves en el momento de la consulta, y una firma de solicitud válida demuestra que el titular de una de esas claves firmó los componentes cubiertos.[5] Para evitar que terceros repliquen el directorio de otro operador y reclamen esas claves, las respuestas del directorio pueden incluir firmas de mensajes HTTP que prueben la posesión de cada clave privada listada.[4][9] Cuando un verificador obtiene registros de directorio de múltiples fuentes, prevalece el registro más reciente según la marca de tiempo `created` de la firma del directorio o el momento de obtención del propio verificador.[5] La verificación demuestra continuidad criptográfica y posesión de claves, mientras que determinar si un operador es fiable o está autorizado a acceder a un sitio sigue siendo una decisión de política del servidor de origen.[5]

## Estandarización de Web Bot Auth en el IETF

Web Bot Auth se estandariza a través del grupo de trabajo Web Bot Auth (`webbotauth`) del Internet Engineering Task Force (IETF), integrado en el área Web and Internet Transport (`wit`).[2] Al 23 de noviembre de 2026, el grupo de trabajo permanece activo bajo el estatuto aprobado `charter-ietf-webbotauth-01`, presidido por David Schinazi y Rifaat Shekh-Yusef, con Mike Bishop como director de área.[2] Su estatuto define tres categorías de entregables: especificaciones Standards Track para autenticar clientes automatizados ante sitios web dirigidos a usuarios humanos, especificaciones Standards Track para transmitir metadatos adicionales sobre los bots solicitantes mediante identificadores ampliamente utilizados como nombres de dominio o URL, y documentos Best Current Practice o Informational que aborden el ciclo de vida operativo, la gestión de claves, las consideraciones de despliegue y los efectos sobre la apertura de la web.[2] El grupo de trabajo se coordina con los grupos de trabajo AIPREF, HTTPBIS, OAUTH, TLS y WIMSE.[2]

Al 23 de noviembre de 2026, el grupo de trabajo cuenta con un Internet-Draft adoptado: `draft-ietf-webbotauth-httpsig-protocol-01` ("HTTP Message Signatures for automated traffic"), redactado por Thibault Meunier, de [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare), y Sandor Major, de Google.[3][4][5] La revisión `-01`, un documento de 44 páginas publicado el 29 de octubre de 2026 y con fecha de expiración el 2 de mayo de 2027, sustituye a la serie individual anterior `draft-meunier-webbotauth-httpsig-protocol`, que a su vez reemplazó a `draft-meunier-web-bot-auth-architecture-05` después del 2 de marzo de 2026.[3][4][5] El estatuto establece como hitos previstos abril de 2026 para enviar al IESG las especificaciones Standards Track de autenticación e información de bots, y agosto de 2026 para remitir el documento operativo Best Current Practice.[2]

Junto con el borrador de protocolo adoptado, en la página de documentos de `webbotauth` figuraban 14 Internet-Drafts individuales relacionados al 23 de noviembre de 2026.[3] Estas propuestas exploran mecanismos complementarios, como registros de bots y Signature Agent Cards (`draft-meunier-webbotauth-registry-04`), cabeceras firmadas de metadatos de agentes (`draft-vilgalys-webbotauth-signed-agent-metadata-00`), directorios de claves alojados (`draft-singh-webbotauth-hosted-directories-00`), autenticación anónima de bots (`draft-rescorla-anonymous-webbotauth-01`), notificación de resultados de verificación (`draft-suresh-webbotauth-verification-outcome-00`), prácticas recomendadas para rastreadores (`draft-illyes-webbotauth-cbcp-01`) y publicación de rangos IP basada en JSON (`draft-illyes-webbotauth-jafar-01`).[3] En su condición de Internet-Drafts, estos documentos siguen siendo trabajos en curso sin estatus formal de RFC del IETF.[5][6]

## Implementación y herramientas de Web Bot Auth en Cloudflare

Web Bot Auth está desplegado en producción dentro del Verified Bots Program de Cloudflare, que incorporó HTTP Message Signatures el 1 de julio de 2025.[9][10] Según la referencia para desarrolladores de Cloudflare actualizada el 8 de octubre de 2026, la integración sigue cuatro pasos: generar un par de claves Ed25519 y convertir la clave pública en un JWK (`kty: "OKP"`, `crv: "Ed25519"`, `x` en base64url sin relleno), alojar un directorio JWKS firmado sobre HTTPS en `/.well-known/http-message-signatures-directory`, registrar el bot y la URL del directorio en el panel de Cloudflare bajo el método de verificación `Request Signature`, y firmar las solicitudes salientes.[9] Las respuestas del directorio deben establecer `Content-Type: application/http-message-signatures-directory+json` y adjuntar una firma de mensaje HTTP por cada clave Ed25519 que cubra `@authority;req` con `tag="http-message-signatures-directory"`, `keyid`, `created` y `expires`.[9]

Al 8 de octubre de 2026, la verificación de solicitudes de Cloudflare sigue versiones anteriores de los borradores (`draft-meunier-web-bot-auth-architecture-02` y `draft-meunier-http-message-signatures-directory-03`) y aplica restricciones específicas.[9] Las solicitudes salientes deben incluir `Signature-Agent` como una cadena estructurada entre comillas dobles que contenga un URI `https://`, incluir `signature-agent` y al menos `@authority` en `Signature-Input`, usar valores de componentes únicamente en ASCII y establecer `tag="web-bot-auth"`.[9] Cloudflare rechaza la sintaxis de diccionario para `Signature-Agent` introducida en borradores posteriores, no admite `@query-params` ni `@status`, y rechaza la validación si `Signature-Input` utiliza los parámetros de componente de RFC 9421 `sf`, `bs`, `key`, `req` o `name`.[9] Aunque Cloudflare recomienda enviar un `nonce`, al 8 de octubre de 2026 su verificador no valida nonces ni almacena los ya observados en una base de datos; recomienda intervalos cortos de `expires`, como un minuto, para limitar las ventanas de repetición.[9] Los operadores pueden probar el formato y la verificación de solicitudes en `https://crawltest.com/cdn-cgi/web-bot-auth`, que devuelve HTTP 200 para claves conocidas verificadas, HTTP 401 para claves desconocidas o verificaciones fallidas y HTTP 400 para mensajes con formato incorrecto.[9]

Cloudflare también documenta un mecanismo experimental de confianza transitiva basado en la cabecera `Forwarded` de RFC 7239 (como `Forwarded: for="openai";use="reference"` a modo de ejemplo ilustrativo de sintaxis) para transmitir la identidad del operador del bot y los compromisos de uso del contenido a través de intermediarios, señalando que esta función puede cambiar.[9] Los propietarios de sitios que deseen realizar la validación de firmas en el origen pueden pedir al soporte de Cloudflare que desactive la verificación de Cloudflare en su zona para que no rellene `cf.bot_management.verified_bot`, haciendo que los bots verificados recurran a métodos alternativos como la validación inversa de DNS.[9]

Cloudflare mantiene un repositorio de código abierto bajo licencia Apache-2.0 en `github.com/cloudflare/web-bot-auth` con paquetes de TypeScript (`http-message-sig`, `jsonwebkey-thumbprint`, `web-bot-auth`) y crates de Rust (`web-bot-auth`, `http-signature-directory`), que contaba con 188 estrellas y 52 bifurcaciones al 23 de noviembre de 2026.[12] El repositorio incluye ejemplos de firma y verificación para extensiones de navegador, Rust, un complemento de Caddy y Cloudflare Workers, además de un punto de conexión de pruebas de Cloudflare Research en `http-message-signatures-example.research.cloudflare.com`.[12] La documentación del repositorio advierte que el software no ha sido auditado.[12]

## Alcance, seguridad y limitaciones de Web Bot Auth

Web Bot Auth aborda la autenticación criptográfica de clientes HTTP automatizados que acceden a contenido web destinado principalmente a usuarios humanos, y el estatuto de `webbotauth` del IETF excluye explícitamente varios problemas adyacentes.[2] Entre los elementos fuera de alcance se encuentran la autenticación del acceso a API HTTP orientadas a máquinas o interfaces agente a agente, la autenticación del usuario final detrás de un agente, los protocolos distintos de HTTP, la identificación no criptográfica, la definición de un vocabulario de intenciones de bots, el seguimiento o asignación de reputación de bots y la detección de bots que optan por permanecer sin autenticar.[2] Web Bot Auth también es distinto del Protocolo de Exclusión de Robots ([robots.txt](https://mimirwiki.com/es/wiki/robots-txt)), estandarizado en RFC 9309 en septiembre de 2022, que expresa reglas voluntarias de rastreo por token `user-agent` y establece explícitamente que dichas reglas no constituyen una autorización de acceso.[8]

La verificación criptográfica en Web Bot Auth presenta límites de seguridad definidos.[5] Una firma válida confirma únicamente que una solicitud fue firmada por una clave publicada en la URL resuelta de `Signature-Agent`, sin certificar que el operador sea benigno ni que una solicitud concreta esté autorizada.[5] Nada en el protocolo impide que un cliente abandone una URL y despliegue otra, ya que el mecanismo está diseñado para operadores que desean un reconocimiento continuo entre solicitudes.[5] Las solicitudes firmadas siguen siendo vulnerables a ataques de repetición dentro de su ventana de validez, que los operadores acotan mediante los componentes cubiertos e intervalos cortos entre `created` y `expires`.[5][9]

El despliegue del descubrimiento de claves en banda introduce riesgos operativos tratados en las consideraciones de seguridad y privacidad de `draft-ietf-webbotauth-httpsig-protocol-01`.[4] Dado que los verificadores consultan URL HTTPS arbitrarias de `Signature-Agent` presentadas en solicitudes entrantes, los servidores deben protegerse contra la falsificación de solicitudes del lado del servidor (SSRF) y limitar los recursos y el comportamiento de caché al obtener directorios.[4] La especificación también destaca los requisitos de TLS, la respuesta ante el compromiso de claves, la evitación de secretos compartidos y de la reutilización de claves, el tratamiento de firmas de prueba o estáticas, las interacciones con proxies inversos y las implicaciones de privacidad derivadas de la identificación de clientes, la correlación y los patrones de acceso a directorios.[4] Además, el estatuto de `webbotauth` indica al grupo de trabajo que tenga en cuenta la sobrecarga operativa sobre los clientes bot y los sitios web y que evite introducir cuellos de botella arquitectónicos.[2]

## Preguntas frecuentes

### ¿Qué es Web Bot Auth?

Web Bot Auth es un protocolo de autenticación en la capa HTTP que permite a los clientes automatizados, como rastreadores web y agentes de IA, firmar criptográficamente solicitudes salientes mediante RFC 9421 HTTP Message Signatures. Los servidores verifican esas firmas con las claves públicas publicadas en un directorio JSON Web Key Set. [1][4][5]

### ¿Cómo encuentra un servidor las claves públicas de un bot en Web Bot Auth?

Una solicitud firmada incluye una cabecera Signature-Agent con una URL HTTPS correspondiente al directorio de claves del bot. Los servidores obtienen el JSON Web Key Set desde esa URL, alojada habitualmente en /.well-known/http-message-signatures-directory, y seleccionan la clave correspondiente mediante el parámetro de huella digital keyid. [4][5][9]

### ¿Es Web Bot Auth un estándar RFC oficial del IETF?

Al 23 de noviembre de 2026, Web Bot Auth es un trabajo activo en curso en el grupo de trabajo Web Bot Auth (webbotauth) del IETF. Su especificación principal, draft-ietf-webbotauth-httpsig-protocol-01, es un Internet-Draft de Standards Track publicado el 29 de octubre de 2026 y no ha sido publicado como RFC. [2][4][5]

### ¿Qué claves criptográficas admite Cloudflare para Web Bot Auth?

Al 8 de octubre de 2026, la integración de Web Bot Auth de Cloudflare admite claves de firma Ed25519 publicadas como JSON Web Keys OKP en /.well-known/http-message-signatures-directory. Las respuestas del directorio deben incluir una firma de mensaje HTTP por cada clave Ed25519 para demostrar la posesión de la clave. [9]

### ¿Cómo gestiona Web Bot Auth la rotación de claves sin perder la identidad del bot?

En draft-ietf-webbotauth-httpsig-protocol-01, la URL HTTPS verificada de Signature-Agent funciona como identificador del agente, mientras que keyid selecciona la clave individual. Un operador rota las claves publicando la nueva clave pública junto a la existente en el directorio y eliminando después la clave anterior, lo que preserva la continuidad bajo la misma URL. [5]

### ¿Sustituye Web Bot Auth a robots.txt o autentica a usuarios finales?

No. El Protocolo de Exclusión de Robots (RFC 9309) define reglas voluntarias de acceso para rastreadores, mientras que Web Bot Auth verifica criptográficamente la identidad del cliente automatizado. El estatuto del grupo de trabajo webbotauth del IETF excluye explícitamente de su alcance la autenticación de usuarios finales. [2][8]

## Frases citables

- Web Bot Auth utiliza firmas digitales separadas definidas por RFC 9421 (HTTP Message Signatures, publicado en febrero de 2024) para autenticar solicitudes HTTP automatizadas. [1][4]
- Al 23 de noviembre de 2026, el grupo de trabajo Web Bot Auth (webbotauth) del IETF opera en el área Web and Internet Transport bajo el estatuto aprobado charter-ietf-webbotauth-01. [2]
- El borrador adoptado por el grupo de trabajo draft-ietf-webbotauth-httpsig-protocol-01 fue publicado el 29 de octubre de 2026 por Thibault Meunier, de Cloudflare, y Sandor Major, de Google. [4][5]
- En draft-ietf-webbotauth-httpsig-protocol-01, la URL HTTPS verificada de Signature-Agent actúa como identificador del agente y permite la rotación de claves sin romper la continuidad de la identidad. [5]
- draft-ietf-webbotauth-httpsig-protocol-01 define el URI bien conocido /.well-known/http-message-signatures-directory y el tipo de medio application/http-message-signatures-directory+json para publicar directorios de claves JWKS. [4][7]
- Cloudflare incorporó HTTP Message Signatures (Web Bot Auth) a su Verified Bots Program el 1 de julio de 2025. [10]
- Al 8 de octubre de 2026, la implementación de Web Bot Auth de Cloudflare admite claves Ed25519 y exige respuestas de directorio firmadas sobre HTTPS en /.well-known/http-message-signatures-directory. [9]
- Cloudflare mantiene bibliotecas y ejemplos de código abierto de Web Bot Auth en TypeScript y Rust en github.com/cloudflare/web-bot-auth bajo la licencia Apache-2.0. [12]

## Cronología

- 2024-02: El IETF publica RFC 9421 (HTTP Message Signatures) como especificación Standards Track. [1]
- 2025-05-15: Cloudflare publica una propuesta inicial de Thibault Meunier y Mari Galicer para verificar el tráfico de bots y agentes de IA mediante firmas criptográficas HTTP. [11]
- 2025-07-01: Cloudflare incorpora HTTP Message Signatures a su Verified Bots Program. [10]
- 2026-03-02: Thibault Meunier y Sandor Major publican la revisión 05 de draft-meunier-web-bot-auth-architecture y draft-meunier-http-message-signatures-directory, posteriormente sustituidos por los borradores de protocolo y directorio de webbotauth. [3][6]
- 2026-10-08: Cloudflare actualiza su documentación para desarrolladores de Web Bot Auth sobre directorios de claves Ed25519, firma de solicitudes y soporte experimental para la cabecera Forwarded de RFC 7239. [9]
- 2026-10-29: El grupo de trabajo webbotauth del IETF publica draft-ietf-webbotauth-httpsig-protocol-01 (HTTP Message Signatures for automated traffic). [3][4][5]

## Fuentes

1. RFC 9421: HTTP Message Signatures. Internet Engineering Task Force (IETF). publicado 2024-02. https://www.rfc-editor.org/rfc/rfc9421.txt (consultado 2026-11-23; tier 1: government or public registry)
2. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (consultado 2026-11-23; tier 1: government or public registry)
3. Web Bot Auth (webbotauth). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/documents/ (consultado 2026-11-23; tier 1: government or public registry)
4. draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic. Internet Engineering Task Force (IETF). publicado 2026-10-29. https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/ (consultado 2026-11-23; tier 1: government or public registry)
5. draft-ietf-webbotauth-httpsig-protocol-01. Internet Engineering Task Force (IETF). publicado 2026-10-29. https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol (consultado 2026-11-23; tier 1: government or public registry)
6. draft-meunier-http-message-signatures-directory-05 - HTTP Message Signatures Directory. Internet Engineering Task Force (IETF). publicado 2026-03-02. https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/ (consultado 2026-11-23; tier 1: government or public registry)
7. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). publicado 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (consultado 2026-11-23; tier 1: government or public registry)
8. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (consultado 2026-11-23; tier 1: government or public registry)
9. Web Bot Auth · Cloudflare bot solutions docs. Cloudflare. publicado 2026-10-08. https://developers.cloudflare.com/bots/reference/bot-verification/web-bot-auth/ (consultado 2026-11-23; tier 3: official site)
10. Message Signatures are now part of our Verified Bots Program, simplifying bot authentication | Cloudflare Blog. The Cloudflare Blog. publicado 2025-07-01. https://blog.cloudflare.com/verified-bots-with-cryptography/ (consultado 2026-11-23; tier 3: official site)
11. Forget IPs: using cryptography to verify bot and agent traffic | Cloudflare Blog. The Cloudflare Blog. publicado 2025-05-15. https://blog.cloudflare.com/web-bot-auth/ (consultado 2026-11-23; tier 3: official site)
12. GitHub - cloudflare/web-bot-auth: Sign and verify orchestrated HTTP requests · GitHub. Cloudflare (GitHub). https://github.com/cloudflare/web-bot-auth (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Web Bot Auth." Versión cfad48a8, 2026-11-23. https://mimirwiki.com/es/wiki/web-bot-auth
