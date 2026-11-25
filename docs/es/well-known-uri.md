---
title: "Well-Known URIs"
subtitle: "Estándar del IETF que reserva el prefijo de ruta /.well-known/ para metadatos de todo el origen y descubrimiento de servicios"
canonical_url: https://mimirwiki.com/es/wiki/well-known-uri
language: es
page_class: anchor
revision_sha256: 7848bf1593c7c573d08dd8773d22444d2893ca69cf7222ca9730ae5d4d8ab88d
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/well-known-uri.md
  txt: https://mimirwiki.com/es/wiki/well-known-uri.txt
  json: https://mimirwiki.com/es/wiki/well-known-uri.json
  jsonld: https://mimirwiki.com/es/wiki/well-known-uri.jsonld
translations:
  en: https://mimirwiki.com/wiki/well-known-uri
  ko: https://mimirwiki.com/ko/wiki/well-known-uri
  ja: https://mimirwiki.com/ja/wiki/well-known-uri
  zh: https://mimirwiki.com/zh/wiki/well-known-uri
---

# Well-Known URIs

> Los Well-Known URIs son identificadores uniformes de recursos cuya ruta comienza con /.well-known/ para metadatos de todo el origen y descubrimiento de servicios. Especificados en la RFC 8615 del IETF (mayo de 2019), que deja obsoleta la RFC 5785, se aplican a HTTP, HTTPS, WS y WSS. IANA mantiene el registro bajo la política Specification Required para sufijos como security.txt, acme-challenge y openid-configuration.

Los Well-Known URIs (identificadores uniformes de recursos conocidos) son identificadores uniformes de recursos cuyo componente de ruta comienza con el prefijo reservado /.well-known/ en esquemas de URI definidos explícitamente para admitirlos, incluidos HTTP, HTTPS, WS y WSS. Publicada por la Internet Engineering Task Force (IETF) en mayo de 2019 como RFC 8615, la especificación deja obsoleta la RFC 5785 (abril de 2010) y estandariza una ubicación predecible para metadatos de todo el origen y descubrimiento de protocolos, evitando colisiones de rutas. La Internet Assigned Numbers Authority (IANA) mantiene el registro Well-Known URIs bajo la política Specification Required con revisión por expertos designados, donde figuran sufijos permanentes y provisionales como security.txt, acme-challenge, oauth-authorization-server, oauth-protected-resource y openid-configuration. Los Well-Known URIs solo se aplican en el nivel superior de la jerarquía de rutas de un origen, y cada aplicación define su propio formato de metadatos, tipos de medios y alcance.

**También conocido como:** /.well-known/, Identificadores uniformes de recursos conocidos, URI conocidos, RFC 8615, RFC 5785, .well-known

## Datos clave

- **Especificación actual:** RFC 8615 (mayo de 2019, Standards Track) (al 2026-11-23) [1]
- **Prefijo de ruta reservado:** /.well-known/ en la raíz del origen [1]
- **Especificación anterior:** RFC 5785 (abril de 2010, sustituida por la RFC 8615) [2]
- **Registro:** IANA Well-Known URIs (creado el 2010-01-20, actualizado el 2026-10-26) (al 2026-11-23) [3]
- **Política de registro:** Specification Required con revisión por expertos designados (RFC 8126) [1]

## Datos básicos

- **Tipo:** Estándar de Internet para un prefijo de ruta URI reservado [1]
- **Prefijo de ruta:** /.well-known/ [1]
- **Especificación actual:** RFC 8615 (mayo de 2019, Standards Track) (al 2026-11-23) [1]
- **Autor (RFC 8615):** Mark Nottingham [1]
- **Sustituye a:** RFC 5785 (abril de 2010, Mark Nottingham y E. Hammer-Lahav) [2]
- **Actualiza:** RFC 7230 y RFC 7595 [1]
- **Esquemas URI admitidos:** http, https, ws, wss y otros esquemas definidos explícitamente para admitirlos [1]
- **Registro:** IANA Well-Known URIs (iana.org/assignments/well-known-uris) [3]
- **Estado del registro:** Creado el 2010-01-20; última actualización el 2026-10-26 (al 2026-11-23) [3]
- **Política de registro:** Specification Required [3]
- **Experto designado:** Mark Nottingham (al 2026-11-23) [3]
- **Sintaxis del sufijo:** RFC 3986 segment-nz (sin el carácter /) [1]

## Qué son los Well-Known URIs

Los Well-Known URIs son identificadores uniformes de recursos cuyo componente de ruta comienza con `/.well-known/` en esquemas de URI definidos explícitamente para admitir ubicaciones conocidas.[1] La Internet Engineering Task Force (IETF) publicó la especificación vigente de Standards Track, la RFC 8615, en mayo de 2019, redactada por Mark Nottingham.[1] La RFC 8615 deja obsoleta la RFC 5785, publicada por Mark Nottingham y E. Hammer-Lahav en abril de 2010 para establecer el prefijo de ruta `/.well-known/` y el registro de la Internet Assigned Numbers Authority (IANA).[1][2] La RFC 8615 también actualiza la RFC 7230 para reservar el prefijo en los URI `http` y `https`, y actualiza la RFC 7595 para que el registro de esquemas URI de IANA consigne qué esquemas admiten Well-Known URIs.[1]

Las aplicaciones web necesitan con frecuencia descubrir metadatos de ámbito general sobre un origen antes de realizar una solicitud, como ocurre con el [protocolo de exclusión de robots](https://mimirwiki.com/es/wiki/robots-txt) y la Platform for Privacy Preferences (P3P).[1][2] Los mecanismos de metadatos por recurso, como los campos de encabezado HTTP o WebDAV PROPFIND, pueden introducir latencia percibida por el cliente o dificultades de despliegue en esos escenarios.[1][2] HTTP también se utiliza como sustrato para protocolos ajenos a la web que necesitan localizar recursos en un servidor.[1] Designar rutas fijas arbitrarias en la raíz del sitio conlleva el riesgo de colisiones con otras ubicaciones de protocolo y con recursos creados por el propio origen, además de invadir el control que este ejerce sobre su espacio de URI.[1]

Reservar el prefijo único `/.well-known/` aísla las ubicaciones de descubrimiento definidas por protocolos y exige que las especificaciones registren sus sufijos a través de IANA para evitar conflictos de nombres.[1][2] Además de `http` y `https`, la RFC 8615 reserva `/.well-known/` para los URI de WebSocket (`ws`) y Secure WebSocket (`wss`), actualizados mediante la RFC 8307, y permite que otros esquemas de URI adopten los Well-Known URIs cuando sus definiciones de esquema lo autoricen explícitamente.[1] La RFC 5785 señaló que los Well-Known URIs se crearon para exponer información de políticas y metadatos de todo el sitio, ya sea directamente o mediante enlaces a otros URI cuando múltiples viajes de ida y vuelta o comprobaciones por recurso resultan poco prácticos, dejando fuera de su alcance previsto la recuperación general de información y los grandes espacios de nombres de URI.[2]

## Sintaxis y reglas de alcance de los Well-Known URIs

Los Well-Known URIs siguen restricciones estrictas de sintaxis y estructura definidas en la RFC 8615.[1] Para una aplicación que registra el sufijo `example` en `http://www.example.com/`, el Well-Known URI correspondiente es `http://www.example.com/.well-known/example`.[1] Todo sufijo registrado debe ajustarse a la producción `segment-nz` de la RFC 3986, que prohíbe el carácter `/` dentro del propio nombre registrado.[1] La RFC 8615 aconseja a las aplicaciones elegir nombres precisos y desaconseja registrar términos genéricos, citando `example-metadata` o `example.com-metadata` como ejemplos preferibles frente a `metadata`.[1]

Cada registro debe hacer referencia a una especificación que defina el formato, los tipos de medios asociados y los esquemas de URI aplicables al recurso obtenido al desreferenciar el URI.[1] Cuando un registro omite esquemas de URI explícitos, se asumen `http` y `https`.[1] Las aplicaciones utilizan el puerto predeterminado del esquema a menos que la especificación designe explícitamente un puerto alternativo.[1] Los registros también pueden definir la sintaxis para componentes de ruta adicionales, cadenas de consulta, identificadores de fragmento o comportamientos específicos del protocolo, como el manejo de métodos HTTP.[1]

La RFC 8615 deja sin definir el formato y el tipo de medio de la ruta base `/.well-known/`, y los clientes no deben esperar que exista un recurso en esa ubicación.[1] Los Well-Known URIs se ubican estrictamente en la parte superior de la jerarquía de rutas de un URI. Por ejemplo, una ruta que comienza en la raíz como `/.well-known/example` constituye un Well-Known URI, mientras que una ruta anidada como `/foo/.well-known/example` no lo es.[1] La RFC 8615 delega tanto la determinación del nombre de host como el alcance de los metadatos recuperados de un Well-Known URI a cada especificación de aplicación individual.[1]

## Registro de Well-Known URIs de IANA y política de registro

Los Well-Known URIs deben inscribirse en el registro Well-Known URIs de IANA antes de que las aplicaciones acuñen nuevos sufijos bajo `/.well-known/`.[1] Establecido por la RFC 5785 y creado el 2010-01-20, el registro es mantenido por IANA, que coordina los espacios de nombres de parámetros de protocolos del IETF bajo contrato con ICANN para evitar asignaciones conflictivas y respaldar la interoperabilidad.[2][3][8] A fecha de 2026-11-23, la página del registro indica su última actualización el 2026-10-26, nombra a Mark Nottingham como experto designado y ofrece descargas en formatos XML, HTML, TXT y CSV.[3]

Bajo la RFC 8615, los registros siguen la política Specification Required definida en la RFC 8126 (BCP 26, junio de 2017, que dejó obsoleta la RFC 5226) y requieren aprobación con el asesoramiento de uno o más expertos designados.[1][3][8] Las solicitudes se envían a través de la interfaz del registro de IANA o por correo electrónico a la lista `wellknown-uri-review@ietf.org`.[1][3] Cuando la RFC 5785 estableció originalmente el flujo de revisión, fijó un objetivo de 14 días para los expertos designados y permitió escalar las solicitudes sin resolver al Internet Engineering Steering Group (IESG) en `iesg@iesg.org` tras 21 días.[2]

La RFC 8615 exige que cada solicitud de registro proporcione cuatro campos obligatorios más información relacionada opcional:[1]

- **Sufijo de URI**: el nombre relativo a `/.well-known/`
- **Controlador de cambios**: `IETF` para los RFC de Standards Track, o la parte responsable para otras especificaciones
- **Documento(s) de especificación**: una referencia, preferiblemente con un URI recuperable, a la especificación que lo define
- **Estado**: `permanent` (permanente) o `provisional`
- **Información relacionada** (opcional): citas a documentos adicionales

La RFC 8615 añadió la distinción de estado a la plantilla de cuatro campos definida originalmente en la RFC 5785.[1][2] Los valores definidos por los RFC de Standards Track y otros estándares abiertos (según la sección 7.1.1 de la RFC 2026) reciben el estado `permanent`, y los expertos también pueden conceder el estado `permanent` a otros valores cuyo uso esté constatado tras consultar a la comunidad responsable del esquema de URI (habitualmente en la lista de correo del grupo de trabajo correspondiente o en `art@ietf.org`).[1] Otras entradas reciben el estado `provisional`, que los expertos pueden promover posteriormente a `permanent` según su adopción o eliminar en consulta con la comunidad si no se utilizan.[1] Los expertos u otros terceros también pueden registrar sufijos no registrados ampliamente desplegados si existe una especificación de referencia.[1] A fecha de 2026-10-26, la tabla del registro de IANA también marca entradas retiradas como `deprecated` (por ejemplo, `privacy-sandbox-attestations.json`, `related-website-set.json` y `tpcd`) u `obsoleted` (como `http-opportunistic` y `mud`).[3]

## Sufijos registrados destacados de Well-Known URIs

Los Well-Known URIs respaldan la divulgación de seguridad, la emisión automatizada de certificados, los metadatos de identidad y autorización, y el descubrimiento de protocolos entre organismos de normalización como el IETF, el W3C, la OpenID Foundation, OASIS y ETSI.[3] Cinco sufijos permanentes del registro de IANA abarcan la divulgación de seguridad, la automatización de certificados y el descubrimiento de identidad o autorización:[3]

| Sufijo de URI | Especificación definitoria | Estado | Controlador de cambios | Fecha de registro |
| --- | --- | --- | --- | --- |
| `openid-configuration` | OpenID Connect Discovery 1.0 | permanent | OpenID Foundation Artifact Binding Working Group | 2013-08-27 |
| `acme-challenge` | RFC 8555, sección 8.3 | permanent | IETF | 2016-08-18 |
| `oauth-authorization-server` | RFC 8414, sección 3 | permanent | IESG | 2018-03-27 |
| `security.txt` | RFC 9116 | permanent | IETF | 2021-07-13 |
| `oauth-protected-resource` | RFC 9728, sección 3 | permanent | IETF | 2024-10-22 |

`security.txt`, especificado en la RFC 9116 (Informational, abril de 2022) por E. Foudil y Y. Shafranovich, define un archivo de texto plano procesable por máquinas en el que las organizaciones publican sus prácticas de divulgación de vulnerabilidades y los canales de notificación para investigadores de seguridad.[4] El formato utiliza campos clave-valor por línea (incluidos `Contact`, `Expires`, `Encryption`, `Canonical`, `Policy`, `Acknowledgments`, `Preferred-Languages` y `Hiring`), admite comentarios con `#` y recomienda firmas en texto claro de OpenPGP (RFC 4880) combinadas con el campo `Canonical` para autenticar la ubicación del archivo.[4]

`acme-challenge`, registrado bajo la RFC 8555 (Standards Track, marzo de 2019), da soporte al desafío HTTP definido por el protocolo Automatic Certificate Management Environment (ACME).[3][5] ACME automatiza la verificación del control de dominio para certificados X.509 de validación de dominio (DV), así como la emisión y revocación de certificados entre autoridades de certificación y solicitantes, sustituyendo los pasos manuales ad hoc de verificación.[5]

Tres sufijos relacionados sirven al descubrimiento de [OAuth](https://mimirwiki.com/es/wiki/oauth) 2.0 y OpenID Connect. `openid-configuration`, definido por OpenID Connect Discovery 1.0 (finalizado en febrero de 2014, con el conjunto de erratas 2 publicado el 2023-12-15), expone un documento JSON que contiene la configuración de un proveedor OpenID y las ubicaciones de los puntos finales de OAuth 2.0, opcionalmente tras el descubrimiento del emisor mediante WebFinger (RFC 7033).[3][9] `oauth-authorization-server`, especificado en la RFC 8414 (Standards Track, junio de 2018), generaliza ese formato de metadatos JSON para servidores de autorización OAuth 2.0, anunciando campos como `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `scopes_supported` y `response_types_supported` ya sea sobre HTTPS o dentro de un JSON Web Token (JWT) firmado.[3][6] `oauth-protected-resource`, especificado en la RFC 9728 (Standards Track, abril de 2025), proporciona un documento de metadatos JSON paralelo para recursos protegidos de OAuth 2.0 (anunciando `resource`, `authorization_servers`, `jwks_uri`, `scopes_supported` y `bearer_methods_supported`) derivado de forma determinista a partir de cada identificador de recurso, y permite que los servidores de recursos anuncien las URL de metadatos mediante el encabezado `WWW-Authenticate`.[3][7]

A fecha de 2026-10-26, el registro de IANA también incluye entradas permanentes como `webfinger` (RFC 7033), `caldav` y `carddav` (RFC 6764), `host-meta` y `host-meta.json` (RFC 6415), `assetlinks.json` (Google Inc.), `pki-validation` (CA/Browser Forum), `mta-sts.txt` (RFC 8461), `jmap` (RFC 8620), `sbom` (RFC 9472), `api-catalog` (RFC 9727), `agent-card.json` (Linux Foundation) y `webauthn` (W3C), junto con entradas provisionales entre las que figuran `gpc.json`, `change-password`, `did.json` y `tdmrep.json`.[3]

## Consideraciones de seguridad de los Well-Known URIs

Los Well-Known URIs plantean consideraciones de seguridad tanto para diseñadores de protocolos como para operadores de servidores, ya que los recursos bajo `/.well-known/` representan en la práctica a todo un origen.[1] La RFC 8615 destaca amenazas generales como la exposición de datos confidenciales, ataques de denegación de servicio, fallos de autenticación del servidor y del cliente, ataques de revinculación DNS (DNS rebinding) y escenarios en los que un acceso limitado al servidor permite a un atacante alterar el modo en que se sirven los Well-Known URIs.[1] Los operadores de servidores deben restringir el acceso de escritura a las ubicaciones conocidas mediante la configuración del servidor y los permisos del sistema de archivos local, en especial en orígenes compartidos donde coexisten varias entidades.[1] La RFC 8615 también advierte que los sistemas operativos que ocultan directorios con prefijo de punto pueden encubrir ante los administradores modificaciones no autorizadas dentro de un directorio `.well-known`.[1]

En el caso de los URI `http` y `https`, los recursos conocidos son accesibles desde navegadores web y comparten el límite de seguridad del origen con las cookies (RFC 6265), Web Storage y los scripts cargados desde otras rutas del mismo origen.[1] Un atacante que explote una vulnerabilidad de Cross-Site Scripting (XSS) en otro punto del origen puede emitir solicitudes arbitrarias a recursos conocidos.[1] La RFC 8615 enumera mitigaciones y prácticas para los puntos finales conocidos accesibles desde navegadores:[1]

- Cifrar la información confidencial y evitar la compresión en valores sensibles como tokens de autenticación o contraseñas para impedir sondeos de compresión basados en el navegador
- Utilizar identificadores flexibles, como nombres de cookies, para evitar colisiones con otras aplicaciones en el mismo origen, y establecer los atributos de cookie `HttpOnly` y `Path`
- Enviar `X-Content-Type-Options: nosniff`, imponer un tipo de medio `Content-Type` específico de la aplicación y aplicar los encabezados `Content-Security-Policy` y `Referrer-Policy`

Las especificaciones de aplicaciones deben definir explícitamente tanto las reglas de descubrimiento como el alcance de los metadatos para evitar confusiones de límites entre orígenes.[1] La RFC 8615 advierte que aplicar metadatos de `https://example.com/.well-known/example` a otro host o puerto, como `https://department.example.com`, `https://www.example.com` o `https://www.example.com:8000`, presupone una relación administrativa que podría no existir y puede otorgar control a un atacante.[1] Del mismo modo, utilizar un Well-Known URI sobre HTTPS en un nombre de host para arrancar un servicio independiente, como el correo electrónico, puede generar grandes volúmenes de solicitudes HTTP no deseadas hacia servidores web que no implementan el URI, comportándose de forma similar a un ataque de denegación de servicio.[1]

## Limitación de raíz de origen de los Well-Known URIs y llms.txt

Los Well-Known URIs están vinculados estrictamente a la raíz de la jerarquía de rutas de un origen según la RFC 8615, lo que significa que las rutas anidadas como `/foo/.well-known/example` no se consideran Well-Known URIs.[1] Esta restricción a nivel de origen coincide con archivos de descubrimiento para todo el sitio como `/robots.txt` y `/sitemap.xml` (véase [Sitemaps](https://mimirwiki.com/es/wiki/sitemaps)), pero impone limitaciones prácticas a convenciones que requieren metadatos por directorio o publicación en alojamientos compartidos.[1][10]

La propuesta [llms.txt](https://mimirwiki.com/es/wiki/llms-txt), publicada por Jeremy Howard el 2024-09-03 y revisada como v2 el 2026-08-10, ilustra este compromiso arquitectónico.[10] llms.txt especifica colocar un archivo de resumen en Markdown denominado `llms.txt` en la raíz del sitio (`/llms.txt`) o en cualquier subruta (como `/docs/llms.txt`), donde cada archivo abarca las URL situadas bajo su propio directorio y los agentes aplican el archivo más específico cuando existen varios.[10] Para el descubrimiento programático, llms.txt v2 recomienda relaciones de enlace estándar (`rel="alternate"` con `type="text/markdown"` para versiones en Markdown de las páginas y `rel="describedby"` para el archivo `llms.txt` rector) entregadas mediante elementos HTML `link` o encabezados HTTP `Link`.[10]

Al analizar los estándares existentes, la especificación de llms.txt contrasta explícitamente su modelo de subrutas con los Well-Known URIs de la RFC 8615.[10] Dado que los Well-Known URIs existen únicamente en la raíz del origen, los autores que solo controlan un subdirectorio en un servidor compartido (como un sitio de proyecto en GitHub Pages) pueden publicar archivos en su propio directorio, pero no pueden añadir entradas al espacio `/.well-known/` del host.[10] Al funcionar como `index.html` en cualquier ruta, `llms.txt` permite que cualquier editor con permisos de escritura en una ruta describa esa sección concreta de un sitio, un alcance por ruta que una única ubicación en la raíz del origen no puede expresar.[10]

## Preguntas frecuentes

### ¿Qué son los Well-Known URIs?

Los Well-Known URIs son identificadores uniformes de recursos cuya ruta comienza con /.well-known/ en esquemas de URI definidos explícitamente para admitirlos, como HTTP, HTTPS, WS y WSS. Especificados en la RFC 8615 del IETF, proporcionan una ubicación estandarizada para metadatos de todo el origen y descubrimiento de servicios, evitando colisiones con el espacio de URI propio de cada origen. [1]

### ¿En qué se diferencia la RFC 8615 de la RFC 5785?

La RFC 8615 (mayo de 2019) deja obsoleta la RFC 5785 (abril de 2010), actualiza la RFC 7230 para los esquemas http y https, y actualiza la RFC 7595 para que el registro de esquemas URI de IANA registre qué esquemas admiten Well-Known URIs. También añade los estados de registro permanente y provisional, establece explícitamente la restricción a la raíz del origen y amplía las directrices de seguridad sobre la interacción con navegadores, el alcance y los directorios ocultos. [1][2]

### ¿Cómo se registran nuevos sufijos de Well-Known URIs?

Las aplicaciones deben registrar nuevos sufijos en el registro Well-Known URIs de IANA bajo la política Specification Required de la RFC 8126, sujeta a revisión por expertos designados. Las solicitudes se envían a través de la interfaz del registro de IANA o la lista de correo wellknown-uri-review@ietf.org y deben incluir el sufijo de URI, el controlador de cambios, el documento de especificación que lo define y el estado permanente o provisional. [1][3][8]

### ¿Cuáles son algunos sufijos registrados destacados de Well-Known URIs?

Entre los sufijos permanentes del registro de IANA se encuentran security.txt (RFC 9116) para la divulgación de vulnerabilidades, acme-challenge (RFC 8555) para la validación automatizada de dominios en la emisión de certificados, oauth-authorization-server (RFC 8414) y oauth-protected-resource (RFC 9728) para metadatos de OAuth 2.0, y openid-configuration para OpenID Connect Discovery 1.0. [3][4][5][6][7][9]

### ¿Puede ubicarse un Well-Known URI en un subdirectorio como /app/.well-known/?

No. Según la RFC 8615, los Well-Known URIs se ubican estrictamente en la parte superior de la jerarquía de rutas, por lo que /.well-known/example constituye un Well-Known URI, mientras que una ruta anidada como /foo/.well-known/example no lo es. [1]

### ¿Por qué la propuesta llms.txt coloca los archivos fuera de /.well-known/?

La especificación de llms.txt señala que la RFC 8615 restringe los Well-Known URIs a la raíz del origen, lo que impide que los autores que solo controlan un subdirectorio en un alojamiento compartido como GitHub Pages publiquen bajo /.well-known/. Colocar llms.txt en la raíz o en cualquier subruta permite que cada archivo describa su propio directorio, de forma similar a index.html. [1][10]

## Frases citables

- La especificación RFC 8615 del IETF, publicada en mayo de 2019 por Mark Nottingham, define el prefijo de ruta /.well-known/ y deja obsoleta la RFC 5785. [1][2]
- La RFC 8615 reserva /.well-known/ en los URI HTTP, HTTPS, WS y WSS, y actualiza las especificaciones RFC 7230 y RFC 7595. [1]
- Los Well-Known URIs se restringen al nivel superior de la jerarquía de rutas de un origen, y los sufijos registrados deben ajustarse a la sintaxis segment-nz de la RFC 3986 sin el carácter de barra diagonal. [1]
- El registro Well-Known URIs de IANA fue creado el 2010-01-20 y opera bajo la política Specification Required de la RFC 8126 con revisión por expertos designados. [1][3][8]
- A fecha de 2026-11-23, el registro Well-Known URIs de IANA indica como última actualización el 2026-10-26 y nombra a Mark Nottingham como experto designado. [3]
- El sufijo security.txt (RFC 9116) se registró como permanente el 2021-07-13, y el sufijo acme-challenge (RFC 8555, sección 8.3) se registró como permanente el 2016-08-18. [3][4][5]
- El registro de IANA recoge sufijos permanentes para openid-configuration (2013-08-27), oauth-authorization-server (2018-03-27, RFC 8414) y oauth-protected-resource (2024-10-22, RFC 9728). [3][6][7][9]
- La propuesta llms.txt omite el prefijo /.well-known/ porque los Well-Known URIs solo existen en la raíz del origen y no pueden ser publicados por autores que únicamente controlan una subruta en un servidor compartido. [1][10]

## Cronología

- 2010-01-20: IANA crea el registro Well-Known URIs. [3]
- 2010-04: El IETF publica la RFC 5785, redactada por Mark Nottingham y E. Hammer-Lahav, que define el prefijo de ruta /.well-known/ y el procedimiento de registro. [2]
- 2013-08-27: El sufijo openid-configuration se registra como permanente en el registro Well-Known URIs de IANA. [3][9]
- 2016-08-18: El sufijo acme-challenge para la validación de dominio HTTP de ACME se registra como permanente en el registro de IANA. [3][5]
- 2017-06: El IETF publica la RFC 8126 (BCP 26), que actualiza el marco de políticas de registro de IANA, incluida Specification Required. [8]
- 2018-06: El IETF publica la RFC 8414 para OAuth 2.0 Authorization Server Metadata, tras el registro de oauth-authorization-server el 2018-03-27. [3][6]
- 2019-03: El IETF publica la RFC 8555, que especifica el protocolo Automatic Certificate Management Environment (ACME). [5]
- 2019-05: El IETF publica la RFC 8615 de Mark Nottingham, que deja obsoleta la RFC 5785 y actualiza las especificaciones RFC 7230 y RFC 7595. [1]
- 2022-04: El IETF publica la RFC 9116, que define el formato de divulgación de vulnerabilidades security.txt, tras el registro de security.txt el 2021-07-13. [3][4]
- 2025-04: El IETF publica la RFC 9728 para OAuth 2.0 Protected Resource Metadata, tras el registro de oauth-protected-resource el 2024-10-22. [3][7]
- 2026-10-26: IANA registra la última actualización del registro Well-Known URIs a fecha de 2026-11-23. [3]

## Fuentes

1. RFC 8615: Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). publicado 2019-05. https://www.rfc-editor.org/rfc/rfc8615.txt (consultado 2026-11-23; tier 1: government or public registry)
2. RFC 5785: Defining Well-Known Uniform Resource Identifiers (URIs). Internet Engineering Task Force (IETF). publicado 2010-04. https://www.rfc-editor.org/rfc/rfc5785.txt (consultado 2026-11-23; tier 1: government or public registry)
3. Well-Known URIs. Internet Assigned Numbers Authority (IANA). publicado 2026-10-26. https://www.iana.org/assignments/well-known-uris (consultado 2026-11-23; tier 1: government or public registry)
4. RFC 9116: A File Format to Aid in Security Vulnerability Disclosure. Internet Engineering Task Force (IETF). publicado 2022-04. https://www.rfc-editor.org/rfc/rfc9116.txt (consultado 2026-11-23; tier 1: government or public registry)
5. RFC 8555: Automatic Certificate Management Environment (ACME). Internet Engineering Task Force (IETF). publicado 2019-03. https://www.rfc-editor.org/rfc/rfc8555.txt (consultado 2026-11-23; tier 1: government or public registry)
6. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). publicado 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (consultado 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). publicado 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (consultado 2026-11-23; tier 1: government or public registry)
8. RFC 8126: Guidelines for Writing an IANA Considerations Section in RFCs. Internet Engineering Task Force (IETF). publicado 2017-06. https://www.rfc-editor.org/rfc/rfc8126.txt (consultado 2026-11-23; tier 1: government or public registry)
9. Final: OpenID Connect Discovery 1.0 incorporating errata set 2. OpenID Foundation. publicado 2023-12-15. https://openid.net/specs/openid-connect-discovery-1_0.html (consultado 2026-11-23; tier 3: official site)
10. The /llms.txt file, v2 – llms-txt. llmstxt.org. publicado 2024-09-03. https://llmstxt.org/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Well-Known URIs." Versión 7848bf15, 2026-11-23. https://mimirwiki.com/es/wiki/well-known-uri
