---
title: "JSON-RPC"
subtitle: "Protocolo de llamada a procedimiento remoto sin estado e independiente del transporte codificado en JSON"
canonical_url: https://mimirwiki.com/es/wiki/json-rpc
language: es
page_class: anchor
revision_sha256: c8381785e05079908272fd26dc47fba1a146df80cca416a2b9856d96d7789f2b
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/json-rpc.md
  txt: https://mimirwiki.com/es/wiki/json-rpc.txt
  json: https://mimirwiki.com/es/wiki/json-rpc.json
  jsonld: https://mimirwiki.com/es/wiki/json-rpc.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-rpc
  ko: https://mimirwiki.com/ko/wiki/json-rpc
  ja: https://mimirwiki.com/ja/wiki/json-rpc
  zh: https://mimirwiki.com/zh/wiki/json-rpc
---

# JSON-RPC

> JSON-RPC es un protocolo ligero y sin estado de llamada a procedimiento remoto (RPC) que codifica solicitudes, respuestas, notificaciones, errores y llamadas por lotes en JSON. Publicada por el JSON-RPC Working Group en 2010 y actualizada en 2013, la versión 2.0 es independiente del transporte y funciona sobre HTTP, sockets o dentro de un mismo proceso. MCP, LSP y los clientes de Ethereum la utilizan para el intercambio de mensajes.

JSON-RPC es un protocolo ligero y sin estado de llamada a procedimiento remoto (RPC) que codifica mensajes en JavaScript Object Notation (JSON). El JSON-RPC Working Group publicó la versión 2.0 el 2010-03-26 (a partir de un borrador del 2009-05-24) y actualizó el texto de la especificación por última vez el 2013-01-04; a fecha de 2026-11-23, JSON-RPC 2.0 sigue siendo la versión vigente. La especificación JSON-RPC define estructuras de datos para solicitudes, respuestas, notificaciones, errores y lotes junto con sus reglas de procesamiento, dejando la elección de la capa de transporte a cada implementación. JSON-RPC sirve como formato base de mensajes en el Model Context Protocol (MCP), el Language Server Protocol (LSP), las API de clientes de ejecución de Ethereum y el Open vSwitch Database Management Protocol (OVSDB).

**También conocido como:** JSON-RPC 2.0, JSON-RPC 1.0, Llamada a procedimiento remoto JSON

## Datos clave

- **Versión actual:** 2.0 (originada el 2010-03-26, actualizada el 2013-01-04) (al 2026-11-23) [1]
- **Primera versión:** 1.0 (2005) [2]
- **Autor:** JSON-RPC Working Group [1]
- **Formato de datos:** JSON (RFC 4627) [1]
- **Transporte:** Independiente del transporte (en proceso, sockets, HTTP u otros canales de mensajes) [1]

## Datos básicos

- **Tipo:** Protocolo ligero y sin estado de llamada a procedimiento remoto (RPC) [1]
- **Autor:** JSON-RPC Working Group [1]
- **Primera versión:** JSON-RPC 1.0 (2005) [2]
- **Versión actual:** JSON-RPC 2.0 (originada el 2010-03-26, actualizada el 2013-01-04) (al 2026-11-23) [1]
- **Formato de datos:** JSON (cuatro tipos primitivos y dos tipos estructurados) [1]
- **Estándar JSON:** RFC 8259 (diciembre de 2017; deja obsoletos a RFC 7159 y RFC 4627) (al 2026-11-23) [4]
- **Transporte:** Independiente del transporte (en proceso, sockets, HTTP u otro paso de mensajes) [1]
- **Tipos de mensaje:** Request (solicitud), Response (respuesta), Notification (notificación), Error y Batch (lote) [1]
- **Códigos de error reservados:** -32768 a -32000 (predefinidos -32700, -32600 a -32603; servidor -32000 a -32099) [1]
- **Prefijo de extensión:** rpc. (reservado para extensiones opcionales del sistema) [1]
- **Descripción de interfaz:** OpenRPC Specification (versión 1.4.x; método de descubrimiento rpc.discover) (al 2026-11-23) [10]

## Qué es JSON-RPC

JSON-RPC es un protocolo ligero y sin estado de llamada a procedimiento remoto (RPC) que codifica invocaciones de métodos y sus contestaciones como datos en JavaScript Object Notation (JSON).[1] La especificación JSON-RPC 2.0 define un conjunto reducido de estructuras de datos y las reglas para procesarlas, manteniendo el protocolo independiente de cualquier transporte de red concreto.[1] A fecha de 2026-11-23, JSON-RPC 2.0 sigue siendo la especificación vigente mantenida por el JSON-RPC Working Group, habiéndose originado el 2010-03-26 a partir de un borrador del 2009-05-24 y habiendo recibido su última actualización de texto el 2013-01-04.[1]

JSON-RPC emplea el sistema de tipos de JSON, que comprende cuatro tipos primitivos (cadena, número, booleano y nulo: String, Number, Boolean y Null) y dos tipos estructurados (objeto y arreglo: Object y Array).[1][4] El texto de JSON-RPC 2.0 cita el RFC 4627 como referencia de JSON.[1] En diciembre de 2017, la Internet Engineering Task Force (IETF) publicó el RFC 8259 para reemplazar al RFC 7159, que a su vez había dejado obsoleto al RFC 4627 y su registro original del tipo de medio `application/json`.[4] El RFC 8259 alinea la gramática de JSON con ECMA-404 y señala que las implementaciones que producen únicamente objetos o arreglos JSON como textos de nivel superior mantienen la interoperabilidad en todos los analizadores conformes, lo cual coincide con el uso en JSON-RPC de objetos individuales y arreglos por lotes.[1][4]

En JSON-RPC 2.0, el cliente (Client) es la parte que origina los objetos Request y gestiona los objetos Response, mientras que el servidor (Server) es la parte que procesa los objetos Request y origina los objetos Response.[1] Una misma implementación puede desempeñar ambos roles al mismo tiempo frente a distintos pares o frente al mismo par, mientras que la especificación delega la coordinación de sesiones bidireccionales a capas superiores.[1] Todos los nombres de miembros comparados entre cliente y servidor distinguen entre mayúsculas y minúsculas, y la especificación trata los términos función, método y procedimiento como intercambiables.[1]

## Estructura de mensajes de JSON-RPC 2.0

JSON-RPC 2.0 define tres formas principales de mensaje: el objeto Request (solicitud), la Notification (notificación) y el objeto Response (respuesta).[1] Todo objeto Request y Response conforme incluye un miembro `jsonrpc` cuyo valor de cadena debe ser exactamente `"2.0"`.[1]

Un objeto Request de JSON-RPC 2.0 invoca un método remoto y contiene hasta cuatro miembros.[1]

- `jsonrpc`: cadena obligatoria que especifica la versión del protocolo, siempre `"2.0"`.
- `method`: cadena obligatoria que nombra el procedimiento a invocar. Los nombres de método que comienzan con `rpc.` (las letras `rpc` seguidas de un punto, U+002E) están reservados para métodos internos de RPC y extensiones opcionales del sistema.
- `params`: valor estructurado opcional que contiene los argumentos de la invocación. Cuando se incluye, los parámetros se suministran por posición como un arreglo JSON en el orden esperado por el servidor, o por nombre como un objeto JSON cuyos nombres de miembros coinciden con los nombres de parámetros esperados por el servidor con distinción exacta entre mayúsculas y minúsculas.
- `id`: identificador opcional establecido por el cliente que debe ser una cadena (String), un número (Number) o nulo (Null) cuando está presente. Se desaconseja usar Null como `id` de solicitud porque las respuestas con un `id` desconocido utilizan Null y JSON-RPC 1.0 empleaba un `id` nulo para las notificaciones; los valores numéricos de `id` también deben omitir partes fraccionarias, ya que los formatos binarios de coma flotante no pueden representar con exactitud muchas fracciones decimales.

Una notificación (Notification) de JSON-RPC 2.0 es un objeto Request que omite el miembro `id`.[1] Omitir `id` indica que el cliente no espera una contestación, y el servidor no debe devolver ningún objeto Response para una notificación, incluidas las notificaciones enviadas dentro de un lote.[1] Al no devolverse respuesta, las notificaciones no son confirmables y el cliente no recibe ningún aviso si una notificación produce errores como parámetros inválidos o un error interno.[1]

Para cada objeto Request distinto de una notificación, un servidor JSON-RPC 2.0 debe responder con un único objeto JSON Response.[1] Un objeto Response siempre incluye `"jsonrpc": "2.0"` y un miembro `id` que coincide con el `id` del objeto Request, o Null si el servidor no pudo determinar el `id` debido a un error de análisis o una solicitud inválida.[1] Cada objeto Response debe incluir un miembro `result` en caso de éxito o un miembro `error` en caso de fallo, y ambos miembros no deben aparecer juntos en el mismo objeto Response.[1]

## Objeto de error y códigos reservados en JSON-RPC 2.0

JSON-RPC 2.0 notifica los fallos de métodos mediante un objeto Error estructurado ubicado en el miembro `error` del objeto Response.[1] El objeto Error contiene dos miembros obligatorios y uno opcional: `code` (un entero que identifica el tipo de error), `message` (una descripción breve en cadena, preferiblemente limitada a una sola oración concisa) y un miembro opcional `data` que puede contener cualquier valor primitivo o estructurado definido por el servidor con información adicional sobre el error.[1]

JSON-RPC 2.0 reserva el rango de enteros de -32768 a -32000 inclusive para errores de protocolo predefinidos, utilizando códigos estrechamente alineados con los códigos de fallo de XML-RPC.[1] Los códigos no asignados dentro de ese rango permanecen reservados para uso futuro, mientras que los enteros fuera del intervalo de -32768 a -32000 están disponibles para errores definidos por la aplicación.[1]

| Código | Mensaje | Significado |
| --- | --- | --- |
| -32700 | Parse error | El servidor recibió un JSON inválido o se produjo un error al analizar el texto JSON. |
| -32600 | Invalid Request | El JSON enviado no es un objeto Request válido. |
| -32601 | Method not found | El método solicitado no existe o no está disponible. |
| -32602 | Invalid params | Los parámetros del método son inválidos. |
| -32603 | Internal error | Se produjo un error interno de JSON-RPC. |
| -32000 a -32099 | Server error | Reservado para errores de servidor definidos por la implementación. |

Los protocolos derivados se construyen sobre este esquema de errores manteniendo intacto el rango reservado.[7] En la especificación 3.17 del Language Server Protocol (LSP), se conservan los cinco códigos de error básicos de JSON-RPC (-32700 y de -32600 a -32603), el rango de -32099 a -32000 figura como reservado para JSON-RPC (conservando únicamente los códigos heredados -32002 ServerNotInitialized y -32001 UnknownErrorCode por compatibilidad retrospectiva) y los errores propios del protocolo, como -32803 (RequestFailed) y -32802 (ServerCancelled), se definen en un rango separado que comienza en -32899.[7]

## Procesamiento por lotes e independencia del transporte en JSON-RPC

JSON-RPC 2.0 permite que un cliente transmita varios objetos Request en un solo mensaje colocándolos en un arreglo JSON, conocido como lote (Batch).[1] Tras procesar todas las solicitudes del lote, el servidor devuelve un arreglo JSON que contiene un objeto Response por cada objeto Request que no sea una notificación.[1] El servidor puede ejecutar las solicitudes del lote de forma concurrente en cualquier orden y devolver los objetos Response en cualquier orden, por lo que el cliente empareja las respuestas con las solicitudes mediante el miembro `id` de cada objeto.[1]

JSON-RPC 2.0 define reglas específicas para casos límite de errores y notificaciones en lotes.[1] Si la carga útil de un lote es un JSON inválido o un arreglo vacío (`[]`), el servidor devuelve un único objeto Response con el código de error -32700 (Parse error) o -32600 (Invalid Request) y `"id": null`.[1] Si un arreglo no vacío contiene elementos inválidos, el servidor devuelve un arreglo de respuestas que incluye un objeto de error Invalid Request (-32600) por cada entrada inválida junto con las respuestas de las entradas válidas.[1] Si todos los elementos de un lote son notificaciones, el servidor no debe devolver un arreglo vacío y no debe devolver nada en absoluto.[1]

JSON-RPC 2.0 deja el entramado de mensajes y los enlaces de transporte fuera de la especificación central, lo que permite que las mismas estructuras JSON funcionen dentro del mismo proceso, sobre sockets, sobre HTTP o en otros entornos de paso de mensajes.[1] En una etapa anterior del desarrollo del protocolo, el 2008-01-15, Jeffrey Damick y el JSON-RPC Working Group publicaron un borrador histórico de extensión denominado "JSON-RPC over HTTP" orientado a JSON-RPC 1.2.[3] Dicho borrador designaba HTTP POST como método preferido y también describía HTTP GET con parámetros codificados en Base64 y en URL (señalando que los clientes y proxies antiguos podían fallar con longitudes de URI superiores a 255 bytes); especificaba encabezados `Content-Type` y `Accept` de `application/json-rpc` (permitiendo `application/json` o `application/jsonrequest`), exigía `Content-Length` y asignaba códigos de estado HTTP a los resultados: 200 para solicitudes exitosas, 204 para notificaciones, 400 para -32600, 404 para -32601 y 500 para -32700, -32602, -32603 y errores de servidor (-32099 a -32000).[3] Los protocolos que adoptan JSON-RPC definen sus propias convenciones de transporte: LSP enmarca las cargas útiles JSON-RPC 2.0 en UTF-8 con encabezados ASCII de estilo HTTP `Content-Length` y un encabezado opcional `Content-Type` (con valor predeterminado `application/vscode-jsonrpc; charset=utf-8`) separados por `\r\n\r\n`, mientras que los nodos de ejecución de Ethereum suelen aceptar solicitudes HTTP POST con `Content-Type: application/json`.[7][8]

## Historial de versiones de JSON-RPC: de 1.0 a 2.0

JSON-RPC 1.0 se publicó en 2005 como un protocolo de llamada a procedimiento remoto entre pares (peer-to-peer) en el que dos pares conectados podían invocar métodos entre sí sobre un flujo de bytes (con preferencia por sockets TCP/IP) o mediante múltiples solicitudes HTTP POST.[2] Un objeto Request de JSON-RPC 1.0 contenía tres propiedades: `method`, `params` (estrictamente un arreglo posicional) e `id` (de cualquier tipo JSON).[2] Las notificaciones empleaban un valor de `id` igual a `null`, y los objetos Response incluían siempre tanto la propiedad `result` como `error`, asignando `null` a la propiedad no utilizada.[2] La versión 1.0 también incluía una propiedad `__jsonclass__` para la indicación de clases, de modo que los pares pudieran instanciar objetos tipados más allá de los tipos estándar de JSON.[2]

JSON-RPC 2.0, originada el 2010-03-26 a partir de un borrador del 2009-05-24 y actualizada el 2013-01-04, simplificó el protocolo en una especificación de mensajes cliente-servidor sin estado e introdujo cambios que rompen la compatibilidad a nivel de cable con la versión 1.0.[1] Las implementaciones pueden distinguir ambas versiones porque todo objeto Request y Response de JSON-RPC 2.0 incluye `"jsonrpc": "2.0"`, mientras que los objetos de la versión 1.0 omiten dicho miembro.[1]

| Característica | JSON-RPC 1.0 (2005) | JSON-RPC 2.0 (2010, actualizada en 2013) |
| --- | --- | --- |
| Identificador de versión | Omitido | Miembro obligatorio `"jsonrpc": "2.0"` |
| Parámetros (`params`) | Solo arreglo (posicional) | Arreglo opcional (posicional) u objeto (por nombre) |
| Formato de notificación | `"id": null` | Miembro `id` omitido |
| `result` y `error` en Response | Ambos presentes; el campo no usado se fija en `null` | Mutuamente excluyentes; solo puede existir uno |
| Solicitudes por lotes | No definidas | Arreglo JSON de objetos Request |
| Indicación de clase (`__jsonclass__`) | Definida en la especificación | Omitida de la especificación |
| Modelo de comunicación | Entre pares sobre flujo o HTTP | Roles sin estado de cliente y servidor; independiente del transporte |

JSON-RPC 2.0 recomienda a las implementaciones considerar el manejo de objetos de la versión 1.0 cuando resulte práctico, incluso sin las funciones entre pares ni la indicación de clases de la versión 1.0.[1] JSON-RPC 1.0 siguió apareciendo en especificaciones de redes tras la publicación de 2.0: en diciembre de 2013, el IETF publicó el RFC 7047 informativo, que define el Open vSwitch Database Management Protocol (OVSDB) y utiliza JSON-RPC 1.0 sobre JSON como protocolo de transmisión para configurar puentes de conmutadores virtuales, puertos, interfaces de túnel, colas y políticas de calidad de servicio.[5]

## Adopción de JSON-RPC y herramientas OpenRPC

JSON-RPC 2.0 actúa como capa de mensajes para varios protocolos relevantes de desarrollo, inteligencia artificial y cadenas de bloques.[6][7][8] El [Model Context Protocol](https://mimirwiki.com/es/wiki/model-context-protocol) (MCP), cuya versión de especificación 2026-07-28 es la más reciente a fecha de 2026-11-23, utiliza mensajes JSON-RPC 2.0 para conectar aplicaciones anfitrionas de modelos de lenguaje grande (LLM), clientes internos y servidores que exponen recursos, indicaciones (prompts), herramientas y flujos de elicitación del cliente.[6] MCP se inspira en el Language Server Protocol (LSP), mantenido por Microsoft (con la versión de especificación 3.17 archivada, la 3.18 listada como actual y la 3.19 como próxima a fecha de 2026-11-23), que transporta mensajes JSON-RPC 2.0 entre editores de código y servidores de lenguaje para operaciones como completado, diagnósticos, formateo y navegación de símbolos.[6][7]

JSON-RPC 2.0 es también la interfaz de cliente estándar para los nodos de ejecución de Ethereum.[8][9] Todo cliente de ejecución de Ethereum expone una API JSON-RPC uniforme para que las aplicaciones de software puedan consultar el estado de la cadena de bloques, recuperar bloques históricos y recibos de transacciones y enviar transacciones en implementaciones de nodos intercambiables.[8][9] La documentación de Ethereum organiza los métodos centrales en difusión (`eth_blockNumber`, `eth_sendRawTransaction`), estado (`eth_getBalance`, `eth_getStorageAt`, `eth_getTransactionCount`, `eth_getCode`, `eth_call`, `eth_estimateGas`) e historial (`eth_getBlockByNumber`, `eth_getTransactionReceipt`), codificando las cantidades enteras como cadenas hexadecimales compactas con prefijo `"0x"` (`"0x0"` para cero) y los arreglos de bytes sin formato como cadenas hexadecimales de longitud par con prefijo `"0x"`.[8] La especificación canónica de la API de ejecución de Ethereum se mantiene bajo licencia CC0-1.0 en el repositorio de GitHub `ethereum/execution-apis` y se valida frente a los clientes mediante `speccheck` y el conjunto de pruebas `rpc-compat` del simulador `hive`.[9] Los clientes de consenso de Ethereum exponen una Beacon API independiente, y los clientes de consenso y ejecución intercambian mensajes internos del nodo a través de la Engine API.[8]

Para describir y validar interfaces JSON-RPC 2.0 de forma legible por máquina, la OpenRPC Specification (versión 1.4.x a fecha de 2026-11-23, bajo licencia Apache-2.0) define un formato de descripción de interfaces JSON independiente del lenguaje exclusivamente para API JSON-RPC 2.0.[10] Un documento OpenRPC, denominado convencionalmente `openrpc.json`, requiere los campos `openrpc`, `info` y `methods`, utiliza JSON Schema Draft 07 para las definiciones de parámetros y resultados y admite GitHub Flavored [Markdown](https://mimirwiki.com/es/wiki/markdown) en los campos de descripción.[10] OpenRPC define además un método de descubrimiento de servicios llamado `rpc.discover` que emplea el prefijo de extensión reservado `rpc.` de JSON-RPC 2.0 para devolver el esquema OpenRPC de una API en tiempo de ejecución.[1][10] Proyectos como `ethereum/execution-apis` redactan sus métodos JSON-RPC en archivos YAML de OpenRPC y los compilan en un documento `openrpc.json` validado.[9]

## Preguntas frecuentes

### ¿Qué es JSON-RPC?

JSON-RPC es un protocolo ligero y sin estado de llamada a procedimiento remoto (RPC) que codifica solicitudes, respuestas, notificaciones y objetos de error en JSON. La versión 2.0 fue originada por el JSON-RPC Working Group el 2010-03-26 y actualizada por última vez el 2013-01-04. [1]

### ¿En qué se diferencia una notificación de JSON-RPC 2.0 de una solicitud normal?

Una solicitud (Request) de JSON-RPC 2.0 incluye un miembro id para que el servidor pueda asociar su objeto de respuesta (Response) con la llamada. Una notificación (Notification) omite el miembro id, y el servidor no debe devolver ninguna respuesta a ella, incluso cuando aparece dentro de un lote (batch). [1]

### ¿Cuáles son los códigos de error reservados en JSON-RPC 2.0?

JSON-RPC 2.0 reserva los códigos de error enteros de -32768 a -32000 para errores de protocolo predefinidos. En concreto, -32700 corresponde a Parse error, -32600 a Invalid Request, -32601 a Method not found, -32602 a Invalid params, -32603 a Internal error, y el rango de -32000 a -32099 está reservado para errores de servidor definidos por la implementación. [1]

### ¿Requiere JSON-RPC 2.0 el uso de HTTP como protocolo de transporte?

No. JSON-RPC 2.0 es independiente del transporte y define únicamente estructuras de datos JSON y reglas de procesamiento, lo que permite que las implementaciones operen sobre HTTP, sockets, dentro del mismo proceso o mediante otros canales de paso de mensajes. [1]

### ¿Qué cambió entre JSON-RPC 1.0 y JSON-RPC 2.0?

JSON-RPC 2.0 añadió el campo de versión obligatorio "jsonrpc": "2.0", parámetros con nombre mediante objetos JSON, arreglos de solicitudes por lotes y campos result y error mutuamente excluyentes en las respuestas. También cambió las notificaciones de "id": null a un id omitido y eliminó la indicación de clase __jsonclass__ de la versión 1.0. [1][2]

### ¿Qué protocolos y especificaciones principales utilizan JSON-RPC?

El Model Context Protocol (MCP), el Language Server Protocol (LSP) y las API de los clientes de ejecución de Ethereum utilizan JSON-RPC 2.0, mientras que el Open vSwitch Database Management Protocol (RFC 7047) utiliza JSON-RPC 1.0. OpenRPC define un formato estándar de descripción de interfaces legible por máquina específicamente para API JSON-RPC 2.0. [5][6][7][8][10]

## Frases citables

- JSON-RPC 2.0 se originó el 2010-03-26 a partir de un borrador del 2009-05-24 y recibió su última actualización documentada el 2013-01-04. [1]
- Todo objeto Request y Response de JSON-RPC 2.0 debe incluir un miembro "jsonrpc" con el valor exacto de cadena "2.0". [1]
- Un objeto Response de JSON-RPC 2.0 debe incluir un miembro "result" o un miembro "error", y no debe incluir ambos. [1]
- JSON-RPC 2.0 reserva los códigos de error enteros de -32768 a -32000 para errores de protocolo predefinidos, con el rango de -32000 a -32099 designado para errores de servidor definidos por la implementación. [1]
- Los nombres de método que comienzan con "rpc." están reservados en JSON-RPC 2.0 para extensiones opcionales del sistema, como el método de descubrimiento de servicios "rpc.discover" de OpenRPC. [1][10]
- El IETF publicó el RFC 8259 en diciembre de 2017 para estandarizar el formato de intercambio de datos JSON, en reemplazo de RFC 7159 y RFC 4627. [4]
- Tanto el Model Context Protocol (versión 2026-07-28) como el Language Server Protocol (versión 3.17) utilizan JSON-RPC 2.0 como formato base de mensajes. [6][7]
- Los clientes de ejecución de Ethereum implementan una API estándar JSON-RPC 2.0 especificada en formato OpenRPC en el repositorio ethereum/execution-apis bajo licencia CC0-1.0. [8][9]

## Cronología

- 2005: JSON-RPC.ORG publica la especificación JSON-RPC 1.0 para llamadas a procedimientos remotos entre pares sobre conexiones de flujo y HTTP. [2]
- 2008-01-15: Jeffrey Damick y el JSON-RPC Working Group redactan el borrador histórico de la extensión JSON-RPC over HTTP para la versión 1.2. [3]
- 2009-05-24: El JSON-RPC Working Group elabora la versión borrador base utilizada posteriormente para conformar JSON-RPC 2.0. [1]
- 2010-03-26: El JSON-RPC Working Group publica la especificación JSON-RPC 2.0. [1]
- 2013-01-04: El JSON-RPC Working Group publica la última actualización documentada del texto de la especificación JSON-RPC 2.0. [1]
- 2013-12: El IETF publica el RFC 7047 informativo, que define el Open vSwitch Database Management Protocol (OVSDB) sobre JSON-RPC 1.0. [5]
- 2017-12: El IETF publica el RFC 8259, que reemplaza a RFC 7159 y RFC 4627 como especificación JSON en la vía de estándares. [4]
- 2026-07-28: El proyecto Model Context Protocol publica la versión de especificación 2026-07-28 basada en mensajes JSON-RPC 2.0. [6]

## Fuentes

1. JSON-RPC 2.0 Specification. JSON-RPC Working Group. publicado 2010-03-26. https://www.jsonrpc.org/specification (consultado 2026-11-23; tier 3: official site)
2. JSON-RPC 1.0 Specification (2005). JSON-RPC Working Group. publicado 2005. https://www.jsonrpc.org/specification_v1 (consultado 2026-11-23; tier 3: official site)
3. JSON-RPC over HTTP. JSON-RPC Working Group. publicado 2008-01-15. https://www.jsonrpc.org/historical/json-rpc-over-http.html (consultado 2026-11-23; tier 3: official site)
4. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). publicado 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (consultado 2026-11-23; tier 1: government or public registry)
5. RFC 7047: The Open vSwitch Database Management Protocol. Internet Engineering Task Force (IETF). publicado 2013-12. https://www.rfc-editor.org/rfc/rfc7047.txt (consultado 2026-11-23; tier 1: government or public registry)
6. Specification - Model Context Protocol. Model Context Protocol project. publicado 2026-07-28. https://modelcontextprotocol.io/specification/2026-07-28 (consultado 2026-11-23; tier 3: official site)
7. Language Server Protocol Specification - 3.17. Microsoft (LSP). https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/ (consultado 2026-11-23; tier 3: official site)
8. JSON-RPC API | ethereum.org. ethereum.org. https://ethereum.org/developers/docs/apis/json-rpc/ (consultado 2026-11-23; tier 3: official site)
9. GitHub - ethereum/execution-apis: Collection of APIs provided by Ethereum execution layer clients · GitHub. Ethereum (GitHub). https://github.com/ethereum/execution-apis (consultado 2026-11-23; tier 3: official site)
10. OpenRPC Specification | spec. OpenRPC. https://spec.open-rpc.org/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "JSON-RPC." Versión c8381785, 2026-11-23. https://mimirwiki.com/es/wiki/json-rpc
