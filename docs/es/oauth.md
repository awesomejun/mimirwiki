---
title: "OAuth"
subtitle: "Marco de autorización abierto estandarizado por el IETF para el acceso delegado mediante HTTP con tokens de acceso"
canonical_url: https://mimirwiki.com/es/wiki/oauth
language: es
page_class: anchor
revision_sha256: 23c0fab12a38da69dcff58b8ce7bac1050e2ee697e979f87ccc38823f41aa4c7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/oauth.md
  txt: https://mimirwiki.com/es/wiki/oauth.txt
  json: https://mimirwiki.com/es/wiki/oauth.json
  jsonld: https://mimirwiki.com/es/wiki/oauth.jsonld
translations:
  en: https://mimirwiki.com/wiki/oauth
  ko: https://mimirwiki.com/ko/wiki/oauth
  ja: https://mimirwiki.com/ja/wiki/oauth
  zh: https://mimirwiki.com/zh/wiki/oauth
---

# OAuth

> OAuth es un marco de autorización del IETF que permite a una aplicación acceder a recursos HTTP mediante un token de acceso emitido por un servidor de autorización, sin recibir las credenciales del propietario del recurso. Publicado como OAuth 2.0 en el RFC 6749 en octubre de 2012 y actualizado por el RFC 9700 en enero de 2025, OAuth es utilizado por OpenID Connect y en la autorización del Model Context Protocol.

OAuth es un marco de autorización abierto para servicios HTTP que permite a una aplicación de terceros obtener acceso limitado a recursos protegidos en nombre de un propietario del recurso o en nombre propio mediante un token de acceso. Estabilizado originalmente como una especificación comunitaria en octubre de 2007 y documentado como OAuth 1.0 en el RFC 5849 (abril de 2010), el protocolo fue reemplazado en la vía de estándares del IETF (Standards Track) por OAuth 2.0 en los documentos RFC 6749 y RFC 6750 en octubre de 2012. Especificaciones posteriores del IETF ampliaron OAuth 2.0 con Proof Key for Code Exchange (RFC 7636), Authorization Server Metadata (RFC 8414), Best Current Practice for OAuth 2.0 Security (RFC 9700, BCP 240) y Protected Resource Metadata (RFC 9728). A fecha de 2026-11-23, el Grupo de Trabajo OAuth del IETF desarrolla OAuth 2.1 (draft-ietf-oauth-v2-1-17) para consolidar OAuth 2.0 y sus requisitos de seguridad posteriores en una sola especificación.

**También conocido como:** OAuth 2.0, OAuth 2.1, OAuth 1.0, Marco de autorización OAuth 2.0, RFC 6749

## Datos clave

- **Organismo de estandarización:** Grupo de Trabajo OAuth del Internet Engineering Task Force (IETF) [8]
- **Especificación principal:** RFC 6749 (OAuth 2.0, octubre de 2012) [1]
- **BCP de seguridad:** RFC 9700 / BCP 240 (enero de 2025) [6]
- **Roles:** Propietario del recurso, servidor de recursos, cliente, servidor de autorización [1]
- **Estado del borrador OAuth 2.1:** draft-ietf-oauth-v2-1-17 (Internet-Draft activo, actualizado el 2026-10-30) (al 2026-11-23) [8]

## Datos básicos

- **Tipo:** Marco de autorización HTTP [1]
- **Organismo de estandarización:** Grupo de Trabajo OAuth del Internet Engineering Task Force (IETF) [8]
- **OAuth 1.0:** Estabilizado en octubre de 2007; Revision A en junio de 2009; RFC 5849 (informativo, abril de 2010) [4]
- **Marco OAuth 2.0:** RFC 6749 (Standards Track, octubre de 2012; editor D. Hardt) [1]
- **Uso de tokens de portador:** RFC 6750 (Standards Track, octubre de 2012; TLS obligatorio) [2]
- **PKCE:** RFC 7636 (Standards Track, septiembre de 2015) [3]
- **Metadatos del servidor:** RFC 8414 (Standards Track, junio de 2018) [5]
- **BCP de seguridad:** RFC 9700 / BCP 240 (enero de 2025; actualiza los RFC 6749, 6750 y 6819) [6]
- **Metadatos de recursos protegidos:** RFC 9728 (Standards Track, abril de 2025) [7]
- **Estado de OAuth 2.1:** Internet-Draft activo draft-ietf-oauth-v2-1-17 (actualizado el 2026-10-30, vence el 2027-05-04) (al 2026-11-23) [8]
- **Roles de OAuth 2.0:** Propietario del recurso, servidor de recursos, cliente, servidor de autorización [1]
- **Protocolos basados en OAuth 2.0:** OpenID Connect, UMA 2.0, IndieAuth [9]

## Orígenes de OAuth y transición de OAuth 1.0 a OAuth 2.0

OAuth separa el rol de un cliente de terceros del rol de un propietario del recurso para que una aplicación pueda acceder a recursos HTTP mediante un token de acceso emitido por un servidor de autorización, sin poseer las credenciales del propietario del recurso.[1] En el modelo tradicional de compartición de contraseñas cliente-servidor, las aplicaciones de terceros debían almacenar las contraseñas de los usuarios en texto plano, recibían un acceso amplio sin límites de alcance ni de duración, no podían revocarse individualmente sin cambiar la contraseña y exponían la contraseña del usuario junto con todos los datos protegidos en caso de compromiso.[1]

OAuth 1.0 fue creado por una pequeña comunidad de desarrolladores web para ofrecer acceso delegado a recursos protegidos.[4] La especificación se estabilizó en la versión 1.0 en octubre de 2007 y se revisó en junio de 2009 como OAuth Core 1.0 Revision A (`oauth.net/core/1.0a`).[4] Los autores originales transfirieron el control de cambios al IETF, que publicó el RFC 5849 (editado por E. Hammer-Lahav) en abril de 2010 como documento informativo que abarca Revision A y las erratas notificadas.[4] OAuth 1.0 definía tres roles: cliente (originalmente Consumer), servidor (originalmente Service Provider) y propietario del recurso (originalmente User).[4] Empleaba tres clases de credenciales de identificador y secreto compartido (credenciales de cliente, temporales y de token) y autenticaba las solicitudes HTTP mediante valores nonce, marcas de tiempo y firmas criptográficas (`HMAC-SHA1`, `RSA-SHA1` o `PLAINTEXT`).[4]

En octubre de 2012, el IETF publicó OAuth 2.0 en la vía de estándares (Standards Track) mediante el RFC 6749 (editado por D. Hardt) junto con Bearer Token Usage en el RFC 6750 (de M. Jones y D. Hardt).[1][2] El RFC 6749 reemplaza y deja obsoleto al RFC 5849.[1] OAuth 2.0 está diseñado para HTTP y no es retrocompatible con OAuth 1.0, aunque ambas versiones pueden coexistir en una red y las implementaciones pueden admitir ambas.[1] El uso de OAuth 2.0 sobre protocolos distintos de HTTP queda fuera del alcance del RFC 6749.[1]

## Roles, puntos de conexión, tokens y tipos de concesión de OAuth 2.0

OAuth 2.0 define cuatro roles en el RFC 6749 para el acceso delegado a recursos HTTP.[1]

| Rol | Definición en el RFC 6749 |
| --- | --- |
| Propietario del recurso (Resource owner) | Entidad capaz de conceder acceso a un recurso protegido; denominada usuario final cuando es una persona |
| Servidor de recursos (Resource server) | Servidor que aloja recursos protegidos y acepta y responde solicitudes mediante tokens de acceso |
| Cliente (Client) | Aplicación que realiza solicitudes a recursos protegidos en nombre del propietario del recurso y con su autorización |
| Servidor de autorización (Authorization server) | Servidor que emite tokens de acceso al cliente tras autenticar al propietario del recurso y obtener autorización |

El servidor de autorización y el servidor de recursos pueden ejecutarse en el mismo servidor o como entidades separadas, y un único servidor de autorización puede emitir tokens de acceso aceptados por múltiples servidores de recursos.[1] El RFC 6749 define dos puntos de conexión del servidor de autorización, el punto de conexión de autorización (Authorization Endpoint) y el punto de conexión de tokens (Token Endpoint), junto con el punto de conexión de redirección del cliente (Redirection Endpoint).[1] En el flujo abstracto, un cliente obtiene una concesión de autorización del propietario del recurso, intercambia la concesión en el servidor de autorización por un token de acceso que representa un alcance, una vigencia y unos atributos de acceso específicos, y presenta dicho token al servidor de recursos.[1][2] En algunos flujos, el cliente presenta sus propias credenciales directamente al servidor de autorización para obtener un token de acceso sin una concesión del propietario del recurso.[1][2]

El RFC 6750 especifica cómo los clientes presentan tokens de acceso de portador (bearer tokens) sobre HTTP/1.1 con Transport Layer Security (TLS), cuya implementación y uso son obligatorios.[2] Cualquier parte en posesión de un token de portador puede utilizarlo para acceder a los recursos asociados sin demostrar posesión de material criptográfico de clave, por lo que los tokens de portador requieren protección frente a su divulgación tanto en almacenamiento como en tránsito.[2] El RFC 6750 define tres métodos de transmisión: el campo de cabecera de solicitud `Authorization` con el esquema `Bearer` (`Authorization: Bearer <token>`), un parámetro en el cuerpo codificado como formulario y un parámetro de consulta URI, prohibiendo a los clientes utilizar más de un método en una misma solicitud.[2] También registra ante la IANA el tipo de token de acceso `Bearer` y los valores de error `invalid_request`, `invalid_token` e `insufficient_scope` de `WWW-Authenticate`.[2]

El RFC 6749 define cuatro tipos de concesión de autorización: Authorization Code, Implicit, Resource Owner Password Credentials y Client Credentials, además de la emisión de tokens de actualización (Refresh Token) y un mecanismo de concesiones de extensión (Extension Grants).[1] Especificaciones posteriores del IETF añadieron flujos como el Device Authorization Grant (RFC 8628) para dispositivos sin navegador ni teclado.[9] Las directrices de seguridad posteriores en el RFC 9700 declaran obsoletos los modos de operación menos seguros, el sitio comunitario de OAuth clasifica las concesiones Implicit y Password como heredadas, y OAuth 2.1 omite ambas concesiones.[6][9][10]

## PKCE y las mejores prácticas actuales de seguridad de OAuth 2.0 (RFC 9700)

Los clientes públicos de OAuth 2.0 que utilizan la concesión Authorization Code Grant son vulnerables a ataques de interceptación de códigos de autorización, un problema que el IETF abordó en septiembre de 2015 mediante Proof Key for Code Exchange (PKCE, pronunciado "pixy") en el RFC 7636 (de N. Sakimura, J. Bradley y N. Agarwal).[3] En este ataque sobre un dispositivo final como un teléfono inteligente, una aplicación maliciosa registra el mismo esquema URI personalizado que una aplicación nativa legítima de OAuth 2.0, intercepta el código de autorización devuelto mediante la redirección entre aplicaciones del sistema operativo e intercambia ese código por un token de acceso.[3]

PKCE mitiga la interceptación al exigir que el cliente genere un `code_verifier` único y criptográficamente aleatorio para cada solicitud de autorización y envíe un valor transformado denominado `code_challenge` al punto de conexión de autorización.[3] Al enviar el código de autorización al punto de conexión de tokens, el cliente incluye el `code_verifier` original para que el servidor de autorización verifique la vinculación antes de emitir los tokens.[3] El RFC 7636 define dos valores iniciales de `code_challenge_method`: `plain`, que mitiga únicamente la observación de respuestas de autorización, y `S256`, que también mitiga escenarios en los que un atacante puede leer las solicitudes de autorización, por ejemplo mediante registros HTTP filtrados del sistema operativo.[3]

En enero de 2025, el IETF publicó Best Current Practice for OAuth 2.0 Security como RFC 9700 (BCP 240, de T. Lodderstedt, J. Bradley, A. Labunets y D. Fett), actualizando los RFC 6749, 6750 y 6819.[6] El RFC 9700 aborda debilidades observadas en implementaciones reales, despliegues de alta seguridad (incluidos banca abierta, sanidad electrónica, administración electrónica y firmas electrónicas), relaciones dinámicas entre clientes y servidores, y cambios en los navegadores que afectan al tratamiento de los fragmentos de URL durante las redirecciones.[6] Sus requisitos principales incluyen las siguientes medidas.[6]

- Coincidencia exacta de cadenas al comparar los URI de redirección del cliente con los URI prerregistrados, salvo en los números de puerto de URI de redirección localhost en aplicaciones nativas
- Prohibición de exponer redireccionadores abiertos en clientes y servidores de autorización
- Protección obligatoria contra Cross-Site Request Forgery (CSRF) mediante PKCE (cuando se verifica el soporte del servidor de autorización), el parámetro `nonce` de OpenID Connect o tokens CSRF de un solo uso en `state` vinculados al agente de usuario
- Defensas obligatorias contra ataques de confusión (mix-up) cuando un cliente interactúa con más de un servidor de autorización, utilizando el parámetro `iss` (RFC 9207), una notificación `iss` en un ID Token o una respuesta JARM, o URI de redirección distintos
- Uso obligatorio de PKCE para clientes públicos en el flujo Authorization Code Grant, uso recomendado de PKCE para clientes confidenciales y uso condicional de `nonce` por clientes confidenciales de OpenID Connect
- Obsolescencia de modos de operación menos seguros o inseguros, junto con directrices sobre tokens de acceso vinculados al remitente (sender-constrained), tokens de acceso restringidos a una audiencia y protección de tokens de actualización

Otras especificaciones del Grupo de Trabajo OAuth del IETF respaldan requisitos avanzados de seguridad y del ciclo de vida de los tokens, entre ellas Pushed Authorization Requests (PAR, RFC 9126), Demonstration of Proof of Possession (DPoP, RFC 9449), Mutual TLS (RFC 8705), JWT Profile for Access Tokens (RFC 9068), Token Introspection (RFC 7662), Token Revocation (RFC 7009), Token Exchange (RFC 8693), Rich Authorization Requests (RAR, RFC 9396), Step-up Authentication Challenge (RFC 9470) y Security of Cross-Device Flows (RFC 10027).[9]

## Especificaciones de metadatos y descubrimiento de OAuth 2.0

OAuth 2.0 asumía inicialmente relaciones estáticas en las que los clientes conocían las URL del servidor en el momento del despliegue, y especificaciones posteriores del IETF añadieron el descubrimiento de metadatos en JSON en [URI well-known](https://mimirwiki.com/es/wiki/well-known-uri) para entornos dinámicos.[5][6][7]

OAuth 2.0 Authorization Server Metadata, publicado en la vía de estándares como RFC 8414 en junio de 2018 (de M. Jones, N. Sakimura y J. Bradley), generaliza OpenID Connect Discovery 1.0 en un formato compatible para despliegues más amplios de OAuth 2.0.[5] Los clientes obtienen un documento JSON desde una ubicación `.well-known` (conforme al RFC 5785) derivada de la URL `issuer` del servidor de autorización, que utiliza el esquema `https` sin componentes de consulta ni fragmento y contribuye además a prevenir ataques de confusión (mix-up).[5] Los metadatos pueden entregarse como JSON autodeclarado sobre HTTPS o como notificaciones firmadas dentro de un JSON Web Token (JWT).[5] Los parámetros de metadatos registrados incluyen `issuer`, `authorization_endpoint`, `token_endpoint`, `jwks_uri`, `registration_endpoint` (RFC 7591), `scopes_supported`, `response_types_supported`, `response_modes_supported` (con valores predeterminados `query` y `fragment`, y `form_post` también definido) y `grant_types_supported`.[5]

OAuth 2.0 Protected Resource Metadata, publicado en la vía de estándares como RFC 9728 en abril de 2025 (de M.B. Jones, P. Hunt y A. Parecki), define un formato paralelo de metadatos en JSON que permite a clientes y servidores de autorización descubrir cómo interactuar con un recurso protegido de OAuth 2.0.[7] Cada recurso protegido publica sus metadatos en una ubicación `.well-known` (conforme al RFC 8615) derivada de manera determinista de su identificador de recurso `https`, ya sea autodeclarada o firmada como notificaciones JWT.[7] Los parámetros registrados incluyen `resource` (obligatorio), `authorization_servers` (una lista de identificadores de emisor del RFC 8414), `jwks_uri`, `scopes_supported` y `bearer_methods_supported` (`header`, `body` y `query`).[7] El RFC 9728 también define cómo los recursos protegidos utilizan la cabecera HTTP `WWW-Authenticate` para informar dinámicamente a los clientes de la URL de metadatos del recurso protegido.[7]

Para el alta programática de clientes, el RFC 7591 especifica el protocolo OAuth 2.0 Dynamic Client Registration Protocol y el RFC 7592 define la gestión experimental del registro.[5][9] A fecha de 2026-11-23, el Grupo de Trabajo OAuth desarrolla asimismo Client ID Metadata Documents (`draft-ietf-oauth-client-id-metadata-document-00`) junto con otros borradores del grupo de trabajo como Cross-App Access (XAA).[9][12]

## Consolidación de OAuth 2.1 y estado del borrador del IETF

OAuth 2.1 es una iniciativa activa de especificación del Grupo de Trabajo OAuth del IETF orientada a consolidar OAuth 2.0 (RFC 6749), Bearer Token Usage (RFC 6750) y especificaciones posteriores en un solo documento.[8][10] Incorpora cambios procedentes de RFC 7636 (PKCE), RFC 8252 (OAuth 2.0 for Native Apps), RFC 10017 (OAuth for Browser-Based Apps) y RFC 9700 (OAuth 2.0 Security Best Current Practice).[6][10]

A fecha de 2026-11-23, `draft-ietf-oauth-v2-1-17` (redactado por Dick Hardt, Aaron Parecki como editor y Torsten Lodderstedt, en sustitución de `draft-parecki-oauth-v2-1`) es un borrador activo (Active Internet-Draft) previsto para la vía de estándares que dejaría obsoletos los documentos RFC 6749 y RFC 6750 si resulta aprobado.[8] El Datatracker del IETF registra la revisión 17 con última actualización el 2026-10-30 (con fecha de borrador 2026-10-31) y fecha de vencimiento el 2027-05-04, con un hito del Grupo de Trabajo OAuth fijado en diciembre de 2026 para remitir el borrador al IESG.[8] El IETF clasifica un Internet-Draft como trabajo en curso y el documento no se ha publicado como un RFC finalizado.[8] El código fuente del borrador y su sistema de seguimiento de incidencias se mantienen en `github.com/oauth-wg/oauth-v2-1`.[8]

La documentación comunitaria de OAuth para OAuth 2.1 enumera siete diferencias principales respecto a OAuth 2.0, reflejadas en la estructura de `draft-ietf-oauth-v2-1-17` a fecha de 2026-11-23.[8][10]

| Área | Regla en OAuth 2.1 (draft-ietf-oauth-v2-1-17) |
| --- | --- |
| PKCE | Obligatorio para todos los clientes OAuth que utilizan el flujo de código de autorización |
| URI de redirección | Deben compararse mediante coincidencia exacta de cadenas |
| Concesión Implicit | Omitida (se elimina `response_type=token`) |
| Concesión Resource Owner Password Credentials | Omitida |
| Tokens de portador en cadenas de consulta URI | Omitidos; las solicitudes de recursos emplean el campo de cabecera Authorization o un parámetro de contenido codificado como formulario |
| Tokens de actualización de clientes públicos | Deben estar vinculados al remitente (sender-constrained) o rotarse |
| Definiciones de tipos de cliente | Las definiciones de cliente público y confidencial se simplifican según si el cliente posee credenciales |

Además de los tokens de portador, `draft-ietf-oauth-v2-1-17` incluye una sección dedicada a los tokens de acceso vinculados al remitente y limita los tipos de concesión básicos a Authorization Code, Client Credentials, Refresh Token y Extension Grants.[8]

## OAuth en OpenID Connect y en la autorización del Model Context Protocol

OAuth 2.0 constituye la capa base de autorización para protocolos como OpenID Connect (OpenID Foundation), UMA 2.0 (Kantara), IndieAuth (W3C) y la autorización de transporte en el [Model Context Protocol](https://mimirwiki.com/es/wiki/model-context-protocol) (MCP).[9][11][12]

OpenID Connect es un protocolo de autenticación interoperable construido sobre los documentos RFC 6749 y RFC 6750 que permite a las aplicaciones verificar la identidad del usuario final basándose en la autenticación realizada por un servidor de autorización, denominado OpenID Provider (OP) o proveedor de identidad (IDP), y obtener notificaciones (claims) del perfil del usuario desde un punto de conexión UserInfo de estilo REST.[11] Las aplicaciones que delegan la autenticación de usuarios en un OP se denominan partes confiadoras (Relying Parties, RP).[11] En un flujo de OpenID Connect, la RP envía una solicitud de autenticación al OP, el OP autentica al usuario final y obtiene autorización, y responde con un token de identidad (Identity Token) que contiene como mínimo una notificación `sub` (sujeto) y metadatos de autenticación, por lo general acompañado de un token de acceso.[11] OpenID Connect se apoya en HTTPS/TLS para el cifrado en tránsito y en estructuras JSON Web Token (JWT) cuando se requieren firmas en clientes web, móviles y JavaScript, admitiendo funciones opcionales como el cifrado de datos de identidad, el descubrimiento de proveedores y el cierre de sesión.[11] La OpenID Foundation contrasta este diseño basado en JSON y REST con protocolos de identidad basados en XML como OpenID 2.0 y SAML.[11]

La especificación del Model Context Protocol (versión 2026-07-28) define una autorización opcional a nivel de transporte para transportes basados en HTTP, mientras que las implementaciones que emplean transportes STDIO obtienen las credenciales del entorno.[12] En la autorización de MCP, un servidor MCP protegido actúa como un servidor de recursos OAuth 2.1, un cliente MCP actúa como un cliente OAuth 2.1 que realiza solicitudes en nombre de un propietario del recurso y un servidor de autorización interactúa con el usuario y emite los tokens de acceso.[12] La versión 2026-07-28 especifica un subconjunto de estándares de OAuth y OpenID Connect a fecha de 2026-11-23.[12]

- Flujo principal y tokens: borrador del IETF de OAuth 2.1 (`draft-ietf-oauth-v2-1-13`) y Bearer Token Usage (RFC 6750)
- Descubrimiento de recursos protegidos: OAuth 2.0 Protected Resource Metadata (RFC 9728) obligatorio en servidores y clientes MCP; los servidores MCP devuelven cabeceras HTTP 401 `WWW-Authenticate: Bearer` con `resource_metadata` (como `/.well-known/oauth-protected-resource`) y una indicación opcional de `scope` para la autorización de mínimo privilegio y la elevación gradual (step-up)
- Descubrimiento del servidor de autorización: los servidores de autorización deben ofrecer OAuth 2.0 Authorization Server Metadata (RFC 8414) u OpenID Connect Discovery 1.0, y los clientes MCP deben admitir ambos
- Vinculación de recurso y emisor: Resource Indicators for OAuth 2.0 (RFC 8707) obligatorio, que exige un parámetro `resource` con el URI canónico del servidor MCP tanto en las solicitudes de autorización como en las de token, y validación del parámetro `iss` del RFC 9207 frente al emisor registrado antes de enviar un código de autorización a un punto de conexión de tokens
- Registro de clientes: OAuth Client ID Metadata Documents (`draft-ietf-oauth-client-id-metadata-document-00`), prerregistro o Dynamic Client Registration (RFC 7591 y OpenID Connect Dynamic Client Registration 1.0), con el RFC 7591 declarado obsoleto en MCP y mantenido por retrocompatibilidad

## Preguntas frecuentes

### ¿Qué es OAuth?

OAuth es un marco de autorización del IETF para servicios HTTP que permite a una aplicación de terceros obtener acceso limitado a recursos protegidos mediante un token de acceso emitido por un servidor de autorización, sin recibir las credenciales del propietario del recurso. OAuth 2.0 se publicó en la vía de estándares del IETF (Standards Track) en los documentos RFC 6749 y RFC 6750 en octubre de 2012. [1][2]

### ¿Cuáles son los cuatro roles en OAuth 2.0?

El RFC 6749 define cuatro roles: el propietario del recurso (resource owner, una entidad capaz de conceder acceso a un recurso protegido, denominada usuario final cuando se trata de una persona), el servidor de recursos (resource server, el servidor que aloja los recursos protegidos), el cliente (client, la aplicación que realiza solicitudes a recursos protegidos con autorización) y el servidor de autorización (authorization server, el servidor que autentica al propietario del recurso y emite los tokens de acceso). [1]

### ¿Qué es PKCE y por qué se utiliza en OAuth 2.0?

Proof Key for Code Exchange (PKCE), especificado en el RFC 7636 en septiembre de 2015, mitiga los ataques de interceptación e inyección de códigos de autorización en la concesión de código de autorización (Authorization Code Grant) al vincular la solicitud de autorización con la solicitud de token mediante un verificador de código aleatorio creado dinámicamente y su desafío de código transformado. El RFC 9700 exige PKCE para clientes públicos y lo recomienda para clientes confidenciales. [3][6]

### ¿Qué cambió en el RFC 9700, las mejores prácticas actuales de seguridad para OAuth 2.0?

Publicado en enero de 2025 como BCP 240, el RFC 9700 actualiza los RFC 6749, 6750 y 6819 al exigir la coincidencia exacta de cadenas para los URI de redirección (excepto los números de puerto en URI de redirección localhost de aplicaciones nativas), prohibir los redireccionadores abiertos, exigir protección contra CSRF y defensas contra ataques de confusión (mix-up) como el parámetro iss del RFC 9207, exigir PKCE para clientes públicos y declarar obsoletos modos de operación menos seguros. [6]

### ¿Es OAuth 2.1 un estándar finalizado?

A fecha de 2026-11-23, OAuth 2.1 es un borrador activo (Internet-Draft) del Grupo de Trabajo OAuth del IETF (draft-ietf-oauth-v2-1-17, actualizado por última vez el 2026-10-30, con vencimiento el 2027-05-04), con un hito del grupo de trabajo fijado en diciembre de 2026 para su envío al IESG. El borrador consolida OAuth 2.0 y diversos RFC posteriores, omite las concesiones Implicit y Resource Owner Password Credentials así como los tokens de portador en cadenas de consulta URI, y exige PKCE para todos los clientes que utilicen el flujo de código de autorización. [8][10]

### ¿Cómo utilizan OAuth OpenID Connect y el Model Context Protocol?

OpenID Connect es un protocolo de autenticación construido sobre OAuth 2.0 (RFC 6749 y RFC 6750) en el que un proveedor OpenID (OpenID Provider) devuelve un token de identidad y un punto de conexión UserInfo proporciona notificaciones (claims) del perfil del usuario. La versión 2026-07-28 de la especificación del Model Context Protocol utiliza OAuth 2.1, RFC 6750, RFC 8414, RFC 9728, RFC 8707 y RFC 9207 para la autorización opcional del transporte HTTP, tratando un servidor MCP protegido como un servidor de recursos OAuth 2.1. [11][12]

## Frases citables

- OAuth 1.0 se estabilizó en octubre de 2007, se revisó como Revision A en junio de 2009 y se publicó como el documento informativo RFC 5849 en abril de 2010. [4]
- El RFC 6749, publicado en la vía de estándares del IETF (Standards Track) en octubre de 2012, define el marco de autorización OAuth 2.0 y deja obsoleto al RFC 5849. [1]
- El RFC 6750 define el uso de tokens de portador (Bearer Tokens) en HTTP para recursos protegidos de OAuth 2.0 y exige el uso de Transport Layer Security (TLS). [2]
- El RFC 7636, publicado en septiembre de 2015, especifica Proof Key for Code Exchange (PKCE) para mitigar ataques de interceptación de códigos de autorización contra clientes públicos de OAuth 2.0. [3]
- El RFC 8414 (junio de 2018) y el RFC 9728 (abril de 2025) definen documentos de metadatos en JSON servidos desde URI .well-known para servidores de autorización y recursos protegidos de OAuth 2.0. [5][7]
- El RFC 9700 (BCP 240), publicado en enero de 2025, actualiza los RFC 6749, 6750 y 6819 con las mejores prácticas actuales de seguridad para OAuth 2.0. [6]
- A fecha de 2026-11-23, OAuth 2.1 es un borrador activo del IETF (Internet-Draft draft-ietf-oauth-v2-1-17, actualizado el 2026-10-30) destinado a dejar obsoletos los RFC 6749 y RFC 6750 en caso de aprobarse. [8]
- La versión 2026-07-28 de la especificación del Model Context Protocol exige que los servidores MCP protegidos que emplean autorización HTTP implementen el RFC 9728 y que los clientes MCP envíen el parámetro resource del RFC 8707. [12]

## Cronología

- 2007-10: Desarrolladores web estabilizan el protocolo OAuth 1.0. [4]
- 2009-06: Se publica OAuth Core 1.0 Revision A en oauth.net/core/1.0a. [4]
- 2010-04: El IETF publica el RFC 5849 (The OAuth 1.0 Protocol) como RFC informativo. [4]
- 2012-10: El IETF publica el RFC 6749 (The OAuth 2.0 Authorization Framework) y el RFC 6750 (Bearer Token Usage) en la vía de estándares, dejando obsoleto al RFC 5849. [1][2]
- 2015-09: El IETF publica el RFC 7636, que especifica Proof Key for Code Exchange (PKCE) para clientes públicos de OAuth. [3]
- 2018-06: El IETF publica el RFC 8414, que define OAuth 2.0 Authorization Server Metadata. [5]
- 2025-01: El IETF publica el RFC 9700 (BCP 240), que establece las mejores prácticas actuales de seguridad para OAuth 2.0 y actualiza los RFC 6749, 6750 y 6819. [6]
- 2025-04: El IETF publica el RFC 9728, que define OAuth 2.0 Protected Resource Metadata. [7]
- 2026-07-28: La versión 2026-07-28 de la especificación del Model Context Protocol especifica OAuth 2.1, RFC 9728, RFC 8414, RFC 8707 y RFC 9207 para la autorización de transporte basada en HTTP. [12]
- 2026-10-30: El Datatracker del IETF registra la revisión 17 del Internet-Draft de OAuth 2.1 (draft-ietf-oauth-v2-1-17), con fecha de vencimiento el 2027-05-04 y un hito del grupo de trabajo en diciembre de 2026 para su envío al IESG. [8]

## Fuentes

1. RFC 6749: The OAuth 2.0 Authorization Framework. Internet Engineering Task Force (IETF). publicado 2012-10. https://www.rfc-editor.org/rfc/rfc6749.txt (consultado 2026-11-23; tier 1: government or public registry)
2. RFC 6750: The OAuth 2.0 Authorization Framework: Bearer Token Usage. Internet Engineering Task Force (IETF). publicado 2012-10. https://www.rfc-editor.org/rfc/rfc6750.txt (consultado 2026-11-23; tier 1: government or public registry)
3. RFC 7636: Proof Key for Code Exchange by OAuth Public Clients. Internet Engineering Task Force (IETF). publicado 2015-09. https://www.rfc-editor.org/rfc/rfc7636.txt (consultado 2026-11-23; tier 1: government or public registry)
4. RFC 5849: The OAuth 1.0 Protocol. Internet Engineering Task Force (IETF). publicado 2010-04. https://www.rfc-editor.org/rfc/rfc5849.txt (consultado 2026-11-23; tier 1: government or public registry)
5. RFC 8414: OAuth 2.0 Authorization Server Metadata. Internet Engineering Task Force (IETF). publicado 2018-06. https://www.rfc-editor.org/rfc/rfc8414.txt (consultado 2026-11-23; tier 1: government or public registry)
6. RFC 9700: Best Current Practice for OAuth 2.0 Security. Internet Engineering Task Force (IETF). publicado 2025-01. https://www.rfc-editor.org/rfc/rfc9700.txt (consultado 2026-11-23; tier 1: government or public registry)
7. RFC 9728: OAuth 2.0 Protected Resource Metadata. Internet Engineering Task Force (IETF). publicado 2025-04. https://www.rfc-editor.org/rfc/rfc9728.txt (consultado 2026-11-23; tier 1: government or public registry)
8. draft-ietf-oauth-v2-1-17 - The OAuth 2.1 Authorization Framework. Internet Engineering Task Force (IETF). publicado 2026-10-30. https://datatracker.ietf.org/doc/draft-ietf-oauth-v2-1/ (consultado 2026-11-23; tier 1: government or public registry)
9. OAuth 2.0 - OAuth. OAuth Community Site. https://oauth.net/2/ (consultado 2026-11-23; tier 3: official site)
10. OAuth 2.1. OAuth Community Site. https://oauth.net/2.1/ (consultado 2026-11-23; tier 3: official site)
11. How OpenID Connect Works - OpenID Foundation. OpenID Foundation. publicado 2023-02-14. https://openid.net/developers/how-connect-works/ (consultado 2026-11-23; tier 3: official site)
12. Authorization - Model Context Protocol. Model Context Protocol project. publicado 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "OAuth." Versión 23c0fab1, 2026-11-23. https://mimirwiki.com/es/wiki/oauth
