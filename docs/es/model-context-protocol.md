---
title: "Model Context Protocol"
subtitle: "Protocolo abierto que conecta aplicaciones de IA con herramientas y datos externos"
canonical_url: https://mimirwiki.com/es/wiki/model-context-protocol
language: es
page_class: anchor
revision_sha256: 066d8253ac3fa35d6cccb27ed756d015e5f67ac451306b2a8720636e39a076de
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/model-context-protocol.md
  txt: https://mimirwiki.com/es/wiki/model-context-protocol.txt
  json: https://mimirwiki.com/es/wiki/model-context-protocol.json
  jsonld: https://mimirwiki.com/es/wiki/model-context-protocol.jsonld
translations:
  en: https://mimirwiki.com/wiki/model-context-protocol
  ko: https://mimirwiki.com/ko/wiki/model-context-protocol
  ja: https://mimirwiki.com/ja/wiki/model-context-protocol
  zh: https://mimirwiki.com/zh/wiki/model-context-protocol
---

# Model Context Protocol

> El Model Context Protocol (MCP) es un protocolo abierto que permite a las aplicaciones de IA conectarse con herramientas y fuentes de datos externas mediante una única interfaz común. Utiliza mensajes JSON-RPC 2.0 sobre stdio o Streamable HTTP. Anthropic lanzó MCP el 2024-11-25, y la Agentic AI Foundation de la Linux Foundation lo aloja desde diciembre de 2025. La versión actual es la 2026-07-28.

El Model Context Protocol (MCP) es un protocolo abierto que estandariza la forma en que las aplicaciones construidas sobre grandes modelos de lenguaje se conectan con fuentes de datos y herramientas externas. Los mensajes de MCP siguen el formato JSON-RPC 2.0 y circulan entre hosts, clientes y servidores mediante dos transportes estándar, stdio y Streamable HTTP. Anthropic publicó el protocolo como código abierto el 2024-11-25 y lo aportó a la Agentic AI Foundation, creada bajo la Linux Foundation, en un anuncio fechado el 2025-12-09. Al 2026-11-21, la versión actual del protocolo es la 2026-07-28, la revisión que hizo que el protocolo no mantenga estado (stateless).

**También conocido como:** MCP

## Datos clave

- **Primer lanzamiento:** 2024-11-25, por Anthropic [8]
- **Versión actual del protocolo:** 2026-07-28 (al 2026-11-21) [2]
- **Formato de mensajes:** JSON-RPC 2.0 [1]
- **Transportes estándar:** stdio y Streamable HTTP [4]
- **Fundación anfitriona:** Agentic AI Foundation (Linux Foundation), anunciada el 2025-12-09 [9]

## Datos básicos

- **Tipo:** Protocolo abierto para conectar aplicaciones basadas en LLM con fuentes de datos y herramientas externas [1]
- **Desarrollador original:** Anthropic [8]
- **Primer lanzamiento:** 2024-11-25 [8]
- **Versión actual:** 2026-07-28 (al 2026-11-21) [2]
- **Formato de versión:** Cadena de fecha, AAAA-MM-DD [2]
- **Formato de mensajes:** JSON-RPC 2.0, codificado en UTF-8 [4]
- **Transportes estándar:** stdio, Streamable HTTP [4]
- **Funciones del servidor:** Recursos, prompts y herramientas [1]
- **Autorización:** Opcional; basada en OAuth 2.1 para transportes sobre HTTP [5]
- **Entidad legal:** Model Context Protocol a Series of LF Projects, LLC [6]
- **Licencia:** Licencia Apache 2.0 (código y especificación); CC BY 4.0 (otra documentación) [6]
- **SDK oficiales:** TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP, Kotlin (al 2026-11-21) [7]

## Qué es el Model Context Protocol

El Model Context Protocol (MCP) es un protocolo abierto que conecta aplicaciones construidas sobre grandes modelos de lenguaje (LLM) con fuentes de datos y herramientas externas.[1] Su especificación señala tres propósitos: compartir información contextual con modelos de lenguaje, exponer herramientas y capacidades a sistemas de IA, y construir integraciones y flujos de trabajo componibles.[1] La especificación cita al [Language Server Protocol](https://mimirwiki.com/es/wiki/language-server-protocol) como inspiración. Dicho protocolo estandarizó el soporte de lenguajes de programación en las herramientas de desarrollo, y MCP aplica la misma idea para añadir contexto y herramientas a las aplicaciones de IA.[1]

MCP asigna tres roles. Un host es la aplicación de LLM que inicia las conexiones, un cliente es un conector dentro del host y un servidor es un servicio que proporciona contexto y capacidades.[1] Los servidores pueden ofrecer recursos (contexto y datos), prompts (mensajes y flujos de trabajo con plantillas) y herramientas (funciones que un modelo puede ejecutar). Los clientes pueden ofrecer elicitación (elicitation), mediante la cual un servidor solicita más información al usuario.[1]

[Anthropic](https://mimirwiki.com/es/wiki/anthropic) anunció MCP como un estándar de código abierto el 2024-11-25. El lanzamiento incluyó la especificación y los kits de desarrollo de software (SDK), soporte local de servidores MCP en las aplicaciones de Claude Desktop y un repositorio de código abierto de servidores MCP.[8] El anuncio atribuyó la creación del protocolo en Anthropic a David Soria Parra y Justin Spahr-Summers.[8]

## Formato de mensajes y arquitectura del Model Context Protocol

El Model Context Protocol codifica cada mensaje en [JSON-RPC](https://mimirwiki.com/es/wiki/json-rpc) 2.0, y los mensajes deben estar codificados en UTF-8.[1][4] Los clientes envían solicitudes y notificaciones, y los servidores contestan con respuestas y notificaciones. En la revisión actual no existe ninguna otra dirección: los servidores no inician solicitudes JSON-RPC y los clientes no envían respuestas JSON-RPC.[4]

Desde la revisión 2026-07-28, MCP no mantiene estado a nivel de protocolo. Se eliminó el saludo inicial (`initialize`) de revisiones anteriores, y cada solicitud incluye ahora su versión del protocolo y las capacidades del cliente en un campo `_meta`.[3] Los servidores deben implementar un método `server/discover` que informe sus versiones de protocolo compatibles, capacidades e identidad. Los clientes pueden llamarlo primero, pero no están obligados a hacerlo.[2][3]

Cuando un servidor necesita algo del lado del cliente en medio de una llamada, devuelve un resultado marcado como `input_required` que enumera la información necesaria, y el cliente vuelve a intentar la solicitud original adjuntando las respuestas. La especificación denomina a este patrón Multi Round-Trip Requests (MRTR) y sustituye a las solicitudes iniciadas por el servidor de revisiones anteriores.[3] Las notificaciones de cambios de larga duración, por ejemplo una lista de herramientas modificada, se entregan en un flujo que el cliente abre mediante una solicitud `subscriptions/listen`.[3]

## Transportes y autorización del Model Context Protocol

El Model Context Protocol define dos transportes estándar, stdio y Streamable HTTP. Con stdio, el cliente ejecuta el servidor como un subproceso y ambos lados intercambian mensajes delimitados por saltos de línea a través de los flujos estándar. Con Streamable HTTP, cada mensaje es una petición HTTP POST a un único punto de conexión MCP, y la respuesta llega bien como un objeto JSON o bien como un flujo de Server-Sent Events (SSE) acotado a esa solicitud.[4] La semántica del protocolo es idéntica en ambos. Se permiten transportes personalizados siempre que conserven el formato de mensajes JSON-RPC, los patrones de mensajería y el modelo de metadatos por solicitud.[4]

En Streamable HTTP, determinados metadatos se reflejan en encabezados HTTP para que los intermediarios puedan enrutar solicitudes sin analizar el cuerpo.[4] La versión del protocolo se transporta en el encabezado `MCP-Protocol-Version`, y la revisión 2026-07-28 exige los encabezados `Mcp-Method` y `Mcp-Name` en las peticiones POST.[2][3]

La autorización es opcional en MCP. Para los transportes basados en HTTP, la especificación se apoya en [OAuth](https://mimirwiki.com/es/wiki/oauth) 2.1: un servidor MCP protegido actúa como servidor de recursos OAuth 2.1, el cliente MCP actúa como cliente OAuth 2.1 y los servidores deben publicar OAuth 2.0 Protected Resource Metadata (RFC 9728) para que los clientes puedan localizar el servidor de autorización.[5] A las implementaciones que utilizan stdio se les indica que no sigan este flujo y que en su lugar lean las credenciales desde el entorno.[5]

## Versiones del Model Context Protocol y la revisión 2026-07-28

Las versiones del Model Context Protocol son cadenas de fecha con el formato `YYYY-MM-DD`. Cada identificador marca la última fecha en que se realizaron cambios incompatibles con versiones anteriores, mientras que las actualizaciones compatibles hacia atrás no lo modifican.[2] Al 2026-11-21, la versión actual es la 2026-07-28.[2] La página de lanzamientos del repositorio de la especificación en GitHub enumera las revisiones 2024-11-05, 2025-03-26, 2025-06-18, 2025-11-25 y 2026-07-28.[10] Los clientes y servidores pueden admitir varias versiones simultáneamente, y un servidor que no admita la versión solicitada devuelve un `UnsupportedProtocolVersionError` con la lista de versiones que admite.[2]

La publicación de lanzamiento de los mantenedores para la revisión 2026-07-28 la describe como una transición desde un protocolo bidireccional con estado hacia un protocolo de solicitud y respuesta sin estado, de modo que cualquier instancia de servidor detrás de un balanceador de carga pueda atender cualquier solicitud.[11] El registro de cambios enumera las siguientes modificaciones principales.[3]

| Área | Cambio en la revisión 2026-07-28 |
| --- | --- |
| Sesiones | Se eliminaron las sesiones a nivel de protocolo y el encabezado `Mcp-Session-Id` |
| Saludo inicial | Se eliminó el saludo `initialize`; la versión y las capacidades se envían en cada solicitud |
| Descubrimiento | Se añadió `server/discover` como requisito obligatorio para los servidores |
| Entrada de servidor a cliente | Multi Round-Trip Requests sustituye a las solicitudes iniciadas por el servidor |
| Notificaciones | `subscriptions/listen` sustituye al punto de conexión HTTP GET y a los métodos de suscripción de recursos |
| Tasks | Movido del núcleo experimental a la extensión `io.modelcontextprotocol/tasks` |
| Obsoletos | Roots, Sampling, Logging, el transporte HTTP+SSE y OAuth Dynamic Client Registration |

Las funciones obsoletas permanecen en la especificación durante al menos doce meses antes de ser elegibles para su eliminación, salvo una excepción de eliminación acelerada de al menos noventa días.[2] El 2026-11-11, los mantenedores principales anunciaron un calendario de lanzamientos semestral, con publicaciones de la especificación previstas generalmente para el último martes de marzo y septiembre. El próximo lanzamiento está previsto para el 2027-03-30 y se espera que lleve el identificador de versión 2027-03-30.[12]

## Gobernanza y licencias del Model Context Protocol

El Model Context Protocol está alojado por la [Linux Foundation](https://mimirwiki.com/es/wiki/linux-foundation). El 2025-12-09, la Linux Foundation anunció la creación de la [Agentic AI Foundation](https://mimirwiki.com/es/wiki/agentic-ai-foundation) (AAIF), con tres aportaciones de proyectos fundadores: MCP de Anthropic, goose de Block y AGENTS.md de OpenAI.[9] Los miembros platino de la fundación en su lanzamiento fueron Amazon Web Services, Anthropic, Block, Bloomberg, [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare), Google, Microsoft y OpenAI.[9] El documento de gobernanza del proyecto indica que su forma jurídica es Model Context Protocol a Series of LF Projects, LLC.[6]

Las decisiones técnicas en MCP siguen una jerarquía de mantenedores. Los colaboradores (Contributors) abren incidencias y solicitudes de extracción, los mantenedores (Maintainers) administran componentes como los SDK y grupos de trabajo, los mantenedores principales del núcleo (Core Maintainers) dirigen la especificación y los mantenedores líderes (Lead Maintainers) tienen la autoridad final.[6] La membresía pertenece a personas individuales y no existen puestos reservados para empresas. Al 2026-11-21, la página de gobernanza incluye a David Soria Parra y Den Delimarsky como Lead Maintainers.[6] Los cambios en la especificación se proponen mediante Specification Enhancement Proposals (SEPs).[6]

Las contribuciones al código y a la especificación se realizan bajo la Licencia Apache 2.0. La documentación distinta de la especificación se publica bajo la licencia Creative Commons Atribución 4.0 Internacional.[6]

## SDK, adopción y límites del Model Context Protocol

El proyecto Model Context Protocol mantiene SDK oficiales en diez lenguajes de programación. Al 2026-11-21, su página de SDK clasifica a TypeScript, Python, C#, Go, Rust y Ruby en el nivel 1 (Tier 1), a Java en el nivel 2 (Tier 2), y a Swift, PHP y Kotlin en el nivel 3 (Tier 3). Los niveles reflejan la completitud de funciones, el soporte del protocolo y el compromiso de mantenimiento.[7] Cada SDK adopta las nuevas revisiones del protocolo según su propio calendario. El día en que se publicó la revisión 2026-07-28, los SDK de TypeScript, Python, Go y C# ya la admitían.[7][11]

Las cifras publicadas sobre la adopción de MCP proceden del proyecto y de su fundación anfitriona. La Linux Foundation afirmó el 2025-12-09 que se habían publicado más de 10 000 servidores MCP y que Claude, Cursor, Microsoft Copilot, Gemini, VS Code y ChatGPT habían adoptado el protocolo.[9] Los mantenedores informaron el 2026-07-28 de que los SDK de nivel 1 se descargaban cerca de 500 millones de veces al mes y que los SDK de TypeScript y Python habían superado cada uno los 1000 millones de descargas totales.[11]

MCP es una especificación de protocolo, y varios aspectos quedan fuera de lo que garantiza. La especificación indica que el protocolo no puede hacer cumplir por sí mismo sus propios principios de consentimiento y seguridad, por lo que pide a los hosts que obtengan el consentimiento explícito del usuario antes de invocar cualquier herramienta y que traten las descripciones de herramientas como no fiables a menos que provengan de un servidor de confianza.[1] La autorización es opcional, y extensiones como Tasks y MCP Apps son complementos opcionales fuera del núcleo del protocolo.[1][5] La ausencia de estado se aplica al protocolo, no a las aplicaciones: un servidor que necesite conservar estado entre llamadas puede emitir un identificador explícito que se devuelve como un argumento habitual de la herramienta.[3]

## Preguntas frecuentes

### ¿Cuál es la versión actual del Model Context Protocol?

Al 2026-11-21, la versión actual del protocolo es la 2026-07-28. Las versiones son cadenas de fecha con el formato AAAA-MM-DD, y el identificador solo cambia cuando se introducen modificaciones incompatibles con versiones anteriores. [2]

### ¿Quién gobierna el Model Context Protocol?

El proyecto está alojado por la Linux Foundation como Model Context Protocol a Series of LF Projects, LLC, y Anthropic lo aportó a la Agentic AI Foundation anunciada el 2025-12-09. Las decisiones técnicas recaen en mantenedores individuales, y los Lead Maintainers tienen la autoridad final. [6][9]

### ¿Qué formato de mensajes y transportes utiliza el Model Context Protocol?

Los mensajes de MCP utilizan JSON-RPC 2.0, codificados en UTF-8. Los dos transportes estándar son stdio, para un servidor ejecutado como subproceso local, y Streamable HTTP, en el que cada mensaje es una petición HTTP POST a un único punto de conexión. [1][4]

### ¿El Model Context Protocol requiere OAuth?

No. La autorización es opcional en MCP. Cuando se utiliza en transportes basados en HTTP, la especificación se basa en OAuth 2.1, mientras que las implementaciones con stdio obtienen las credenciales desde el entorno. [5]

### ¿Qué cambió en la revisión 2026-07-28 del Model Context Protocol?

La revisión eliminó el saludo inicial initialize y las sesiones a nivel de protocolo, de modo que cada solicitud es autocontenida. Añadió el método server/discover y Multi Round-Trip Requests, y marcó como obsoletos Roots, Sampling y Logging. [3]

### ¿Qué lenguajes cuentan con SDK oficiales del Model Context Protocol?

Al 2026-11-21, el proyecto enumera SDK oficiales para TypeScript, Python, C#, Go, Rust, Ruby, Java, Swift, PHP y Kotlin. Los seis primeros están clasificados en el nivel 1 (Tier 1). [7]

## Frases citables

- El Model Context Protocol utiliza mensajes JSON-RPC 2.0. [1]
- La versión actual del Model Context Protocol es la 2026-07-28 al 2026-11-21. [2]
- Anthropic publicó el Model Context Protocol como código abierto el 2024-11-25. [8]
- La Linux Foundation anunció el 2025-12-09 que Anthropic había aportado el Model Context Protocol a la recién creada Agentic AI Foundation. [9]
- El Model Context Protocol define dos transportes estándar, stdio y Streamable HTTP. [4]
- La revisión 2026-07-28 del Model Context Protocol eliminó el saludo inicial initialize y las sesiones a nivel de protocolo, convirtiéndolo en un protocolo sin estado. [3]
- La autorización es opcional en el Model Context Protocol y se basa en OAuth 2.1 para los transportes basados en HTTP. [5]
- El próximo lanzamiento de la especificación del Model Context Protocol está previsto para el 2027-03-30, según el anuncio de los mantenedores del 2026-11-11. [12]

## Cronología

- 2024-11-25: Anthropic publica el Model Context Protocol como código abierto. [8]
- 2025-03-26: Se publica la revisión 2025-03-26; el transporte HTTP+SSE pasa a considerarse obsoleto a partir de esta revisión. [10][3]
- 2025-06-18: Se publica la revisión 2025-06-18. [10]
- 2025-11-25: Se publica la revisión 2025-11-25, con soporte experimental para tareas. [10][12]
- 2025-12-09: La Linux Foundation anuncia la Agentic AI Foundation, con el Model Context Protocol aportado por Anthropic. [9]
- 2026-07-28: Se publica la revisión 2026-07-28, que hace que el protocolo no mantenga estado. [11][3]
- 2026-11-11: Los mantenedores principales anuncian un calendario de lanzamientos semestral y fijan el 2027-03-30 como objetivo para el próximo lanzamiento. [12]

## Fuentes

1. Specification - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28 (consultado 2026-11-21; tier 3: official site)
2. Versioning - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/versioning (consultado 2026-11-21; tier 3: official site)
3. Key Changes - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/changelog (consultado 2026-11-21; tier 3: official site)
4. Overview - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports (consultado 2026-11-21; tier 3: official site)
5. Authorization - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization (consultado 2026-11-21; tier 3: official site)
6. Governance and Stewardship - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/community/governance (consultado 2026-11-21; tier 3: official site)
7. SDKs - Model Context Protocol. Model Context Protocol project. https://modelcontextprotocol.io/docs/sdk (consultado 2026-11-21; tier 3: official site)
8. Introducing the Model Context Protocol. Anthropic. publicado 2024-11-25. https://www.anthropic.com/news/model-context-protocol (consultado 2026-11-21; tier 3: official site)
9. Linux Foundation Announces the Formation of the Agentic AI Foundation (AAIF), Anchored by New Project Contributions Including Model Context Protocol (MCP), goose and AGENTS.md. The Linux Foundation. publicado 2025-12-09. https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation (consultado 2026-11-21; tier 3: official site)
10. Releases · modelcontextprotocol/modelcontextprotocol · GitHub. Model Context Protocol project (GitHub). https://github.com/modelcontextprotocol/modelcontextprotocol/releases (consultado 2026-11-21; tier 3: official site)
11. The 2026-07-28 Specification. Model Context Protocol Blog. publicado 2026-07-28. https://blog.modelcontextprotocol.io/posts/2026-07-28/ (consultado 2026-11-21; tier 3: official site)
12. A More Predictable Release Cycle for MCP. Model Context Protocol Blog. publicado 2026-11-11. https://blog.modelcontextprotocol.io/posts/mcp-release-cycle/ (consultado 2026-11-21; tier 3: official site)

## Citar esta página

Mimirwiki. "Model Context Protocol." Versión 066d8253, 2026-11-21. https://mimirwiki.com/es/wiki/model-context-protocol
