---
title: "Perplexity"
subtitle: "Motor de respuestas con IA y plataforma API multiproveedor para desarrolladores que ofrece las API Agent, Orchestrator, Search, Context, Monitor, Embeddings y Decisions"
canonical_url: https://mimirwiki.com/es/wiki/perplexity
language: es
page_class: entity
revision_sha256: a3bb16c6f616b2fcb8993c81ed9694733cea13a6a1c1a48852d0317689209eed
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/es/wiki/perplexity.md
  txt: https://mimirwiki.com/es/wiki/perplexity.txt
  json: https://mimirwiki.com/es/wiki/perplexity.json
  jsonld: https://mimirwiki.com/es/wiki/perplexity.jsonld
translations:
  en: https://mimirwiki.com/wiki/perplexity
  ko: https://mimirwiki.com/ko/wiki/perplexity
  ja: https://mimirwiki.com/ja/wiki/perplexity
  zh: https://mimirwiki.com/zh/wiki/perplexity
---

# Perplexity

> Perplexity opera un motor de respuestas de IA basado en la web y una plataforma API de siete servicios: Agent API (`POST https://api.perplexity.ai/v1/agent`), Orchestrator API, Search API ($5.00 por 1,000 solicitudes estándar o $1.00 por 1,000 de Fast Search, hasta 5 consultas por solicitud), Context API, Monitor API ($1.00 por 1,000 ejecuciones o URL obtenidas), Embeddings API y Decisions API. Tras finalizar el soporte heredado de Sonar Chat Completions el 27 de septiembre de 2026, Perplexity migró a los desarrolladores a Agent API, compatible con Open Responses, con acceso unificado a modelos de OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, NVIDIA y Sonar, búsqueda web, financiera y de personas integrada, sandboxes de código y herramientas MCP.

Perplexity es una plataforma de investigación y motor de respuestas basado en inteligencia artificial que combina la indexación web en tiempo real con modelos grandes de lenguaje para ofrecer respuestas fundamentadas con citas, investigación agéntica autónoma y API para desarrolladores. Tras el fin del soporte heredado de Sonar Chat Completions el 27 de septiembre de 2026, la plataforma para desarrolladores de Perplexity (`docs.perplexity.ai`) se organiza en siete servicios modulares: la Agent API multiproveedor, Orchestrator API, Search API, Context API, Monitor API, Embeddings API y Decisions API, junto con la interfaz de línea de comandos `pplx` y los servidores oficiales de Model Context Protocol (MCP).

**También conocido como:** Perplexity, Agent API, Orchestrator API, Search API, PerplexityBot, Motor de respuestas

## Datos clave

- **Conjunto principal de la plataforma API:** Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API, Decisions API [7]
- **Hito de obsolescencia de Sonar:** 27 de septiembre de 2026 (fin del soporte de Sonar Chat Completions; las llamadas síncronas se reformulan a Agent API) [5]
- **Capacidades de Agent API:** Estándar Open Responses, 5 niveles de esfuerzo (de fast a xhigh), enrutamiento multiproveedor, sandboxes, búsqueda financiera y de personas [5]
- **Precios de Search API y Monitor API:** Search API: $5.00/1K solicitudes ($1.00/1K Fast Search, hasta 5 consultas/solicitud); Monitor API: $1.00/1K ejecuciones o URL [4]
- **Rastreadores web y fuentes de IP:** PerplexityBot/1.0 (21 prefijos IPv4) y Perplexity-User/1.0 (10 prefijos IPv4); ninguno entrena modelos fundacionales [1]

## Datos básicos

- **Nombre de la plataforma:** Perplexity (Perplexity API Platform y motor de respuestas) [7]
- **Punto de enlace principal de Agent:** POST https://api.perplexity.ai/v1/agent [6]
- **Compatibilidad con estándares API:** Estándar Open Responses (Agent API); formatos de solicitud de OpenAI y Anthropic (Orchestrator API) [5]
- **Familias de modelos compatibles:** Perplexity Sonar, OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI, NVIDIA [5]
- **Preajustes de esfuerzo de Agent:** fast (predeterminado), low, medium, high, xhigh [5]
- **Precios de Search API:** $5.00 / 1,000 solicitudes (web estándar); $1.00 / 1,000 solicitudes (search_type: "fast") [4]
- **Precios de Monitor API:** $0.001 por ejecución exitosa de Search ($1/1K); $0.001 por URL de Page obtenida y contabilizada ($1/1K) [4]
- **Fecha de cierre de Sonar heredado:** 27 de septiembre de 2026 (fin del soporte de Sonar Chat Completions) [5]
- **Integraciones CLI y MCP:** Perplexity CLI (pplx), Perplexity API MCP Server, Perplexity Computer MCP Server, Decider for Mac [7]
- **Rastreadores web oficiales:** PerplexityBot/1.0 (perplexitybot.json) y Perplexity-User/1.0 (perplexity-user.json) [1]

## Arquitectura de siete pilares de la plataforma API de Perplexity

Para finales de 2026, Perplexity evolucionó de un único punto de enlace de chat aumentado por búsqueda a una plataforma modular de siete API para desarrolladores (`docs.perplexity.ai`), acompañada de los SDK oficiales de Python y TypeScript (`perplexity` y `@perplexity-ai/perplexity_ai`), la interfaz de línea de comandos `pplx` (Perplexity CLI), Perplexity API MCP Server y Perplexity Computer MCP Server:[5][6][7]

1. **Agent API (`POST https://api.perplexity.ai/v1/agent`)**: Una interfaz de agente multiproveedor unificada y compatible con Open Responses que ejecuta un bucle interno de razonamiento y herramientas, y devuelve un arreglo `output` tipado que contiene elementos `search_results` estructurados y elementos `message` citados.[5][6] 2. **Orchestrator API**: Una pasarela de enrutamiento multiproveedor que permite a los desarrolladores invocar modelos de Anthropic, OpenAI, Google, xAI y de pesos abiertos con una sola clave de API de Perplexity, tanto en el formato de solicitud de OpenAI como en el de Anthropic, con soporte para enrutamiento automático de modelos (`perplexity/auto`), conmutación por error entre despliegues, preservación del razonamiento entre turnos y almacenamiento en caché de indicaciones (*prompt caching*).[7] 3. **Search API (`POST /search`)**: Una API de recuperación pura que devuelve resultados web clasificados en formato JSON con el texto extraído de la página en el campo `snippet` de cada resultado, sin invocar un modelo de lenguaje generativo ni cobrar tarifas por tokens.[4][7] 4. **Context API**: Extrae Markdown limpio, HTML, enlaces salientes, fragmentos destacados relevantes para la consulta y puntuaciones de actualidad y criterios a partir de URL conocidas.[7] 5. **Monitor API**: Ejecuta monitores de búsqueda y monitores de URL de páginas programados o impulsados por eventos para rastrear cambios web a lo largo del tiempo.[4][7] 6. **Embeddings API**: Genera representaciones vectoriales que incluyen Standard Embeddings, Contextualized Embeddings y Contextualized Embeddings v2.[4][7] 7. **Decisions API**: Produce estimaciones de probabilidad calibradas para cargas de trabajo de pronóstico y toma de decisiones (vinculada al cliente Decider for Mac).[4][7]

## Transición de Sonar Chat Completions a Agent API

Perplexity finalizó oficialmente el soporte para su punto de enlace heredado Sonar Chat Completions (`POST https://api.perplexity.ai/v1/sonar`) el 27 de septiembre de 2026.[5] Con el fin de preservar la retrocompatibilidad de los despliegues en producción existentes, las solicitudes síncronas y en *streaming* de Sonar siguen funcionando al reformularse automáticamente en el servidor hacia solicitudes de Agent API modelo por modelo, mientras que las solicitudes asíncronas heredadas de Sonar ya no se reformulan ni cuentan con soporte y deben migrar al modo en segundo plano (*background mode*) de Agent API.[5]

A diferencia de Sonar Chat Completions, que aceptaba un arreglo `messages` limitado a los modelos Sonar de Perplexity y devolvía un arreglo `choices` sin tipado, Agent API acepta una carga útil `input` y cumple con la especificación portátil Open Responses.[5] Mediante una única clave de API de Perplexity, los desarrolladores pueden seleccionar modelos entre ocho familias: los modelos Sonar propios de Perplexity, OpenAI (como `openai/gpt-5.6-luna`), Anthropic, Google, xAI, Z.AI, Moonshot AI y NVIDIA, con cadenas configurables de respaldo de modelos.[4][5]

Agent API incluye preajustes de `effort` ajustados para investigación (`fast`, `low`, `medium`, `high` y `xhigh`) y perfiles versionados reutilizables que preconfiguran límites de bucle, presupuestos de tokens y herramientas integradas:[5][7]

- **Búsqueda como código y fundamentación multifuente**: Búsqueda web integrada, obtención de URL, Finance Search y People Search.[5]
- **Entorno aislado de ejecución de código**: Un contenedor aislado (*sandbox*) que ejecuta código generado para calcular resultados matemáticos exactos, analizar datos y devolver archivos generados dentro de una misma solicitud a la API.[5][7]
- **MCP y funciones personalizadas**: Soporte nativo de cliente para servidores externos de Model Context Protocol (MCP), junto con herramientas de funciones personalizadas definidas por el invocador.[5]

## Mecánica de precios y facturación de Search API, Monitor API y Agent API

Perplexity opera un modelo de facturación de pago por uso en todas sus API sin suscripción mensual obligatoria.[6] En Agent API y Orchestrator API, los costos de tokens se facturan de forma transparente según las tarifas publicadas por modelo junto con cargos separados por invocación o por tiempo de contenedor de herramientas (por ejemplo, los entornos aislados de código se facturan por cada bloque iniciado de 20 minutos de tiempo de ejecución del contenedor más las búsquedas web del SDK ejecutadas dentro del entorno aislado, mientras que ciertas invocaciones de herramientas integradas se facturan a $1.00 por cada 1,000 invocaciones).[4][6]

Para cargas de trabajo de recuperación y monitoreo, Perplexity factura estrictamente por solicitud o unidad de ejecución sin cargos por tokens:[4]

| Servicio API | Modo / Unidad | Precio por 1,000 unidades | Costo por unidad y reglas de facturación |
| --- | --- | --- | --- |
| Search API | Búsqueda web estándar (`POST /search`) | $5.00 / 1K solicitudes | $0.005 por solicitud exitosa; una sola solicitud puede agrupar un arreglo de hasta 5 consultas (hasta 20 resultados) como 1 unidad facturable |
| Search API | Fast Search (`search_type: "fast"`) | $1.00 / 1K solicitudes | $0.001 por solicitud exitosa (recuperación de menor latencia; hasta 5 consultas por solicitud contadas como 1 unidad facturable) |
| Monitor API | Ejecución de Search Monitor | $1.00 / 1K ejecuciones | $0.001 por ejecución exitosa de Search, independientemente del número de búsquedas o resultados dentro de la ejecución |
| Monitor API | Obtención de Page Monitor | $1.00 / 1K URL | $0.001 por URL obtenida y contabilizada en una ejecución exitosa de Page |

En Search API, las solicitudes no válidas, las solicitudes limitadas por tasa (`429`) y los errores de origen nunca se facturan, mientras que una respuesta HTTP 200 válida se factura como una unidad incluso si una consulta devuelve cero resultados.[4] En Monitor API, las ejecuciones fallidas y omitidas no generan cargos.[4]

## Rastreadores de Perplexity (PerplexityBot y Perplexity-User) y reglas WAF

Perplexity recopila y verifica información web a través de dos agentes de usuario HTTP diferenciados, ninguno de los cuales se utiliza para rastrear contenido con el fin de entrenar modelos fundacionales de IA:[1]

1. **`PerplexityBot`**: El rastreador de indexación automatizado empleado para mostrar y enlazar sitios web en los resultados de búsqueda de Perplexity.[1] Respeta las directivas de `robots.txt` (reflejando los cambios en un plazo aproximado de 24 horas), envía la cadena de agente de usuario `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)` y publica su lista oficial de direcciones IPv4 permitidas en `https://www.perplexity.ai/perplexitybot.json`.[1] Con la actualización de la fuente del `2026-11-18T16:30:18`, `perplexitybot.json` enumera 21 prefijos IPv4 `/32` distribuidos en `107.20.236.150/32`, `18.210.92.235/32`, `18.97.1.228/32`, de `18.97.9.96/32` a `18.97.9.103/32`, `3.222.232.239/32`, `3.224.62.45/32` y de `3.41.218.160/32` a `3.41.218.167/32`.[2] 2. **`Perplexity-User`**: El recuperador en tiempo real por acción del usuario que se activa cuando una persona formula a Perplexity una pregunta que requiere visitar una página web específica para responder y citar.[1] Dado que las recuperaciones son iniciadas directamente por solicitudes del usuario, `Perplexity-User` suele ignorar las reglas de `robots.txt`, se identifica como `Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)` y publica su lista de direcciones IPv4 permitidas en `https://www.perplexity.ai/perplexity-user.json` (que a fecha de `2026-10-28T16:48:51` enumera 10 prefijos IPv4 `/32`: de `18.97.43.80/32` a `18.97.43.87/32`, `34.193.163.52/32` y `44.208.221.197/32`).[1][3]

Para los operadores de sitios que emplean cortafuegos de aplicaciones web (WAF), como Cloudflare WAF o AWS WAF, Perplexity recomienda combinar la coincidencia de subcadenas de `http.user_agent` con la verificación de la IP de origen frente a los puntos de enlace JSON en vivo (`perplexitybot.json` y `perplexity-user.json`) en una regla `Skip` o `Allow` de alta prioridad, señalando que el modo gratuito Bot Fight Mode de Cloudflare no puede eludirse mediante reglas WAF personalizadas y puede seguir desafiando a los bots de Perplexity si permanece habilitado.[1]

## Preguntas frecuentes

### ¿Qué ocurrió con la API Sonar Chat Completions de Perplexity?

El soporte para Sonar Chat Completions finalizó el 27 de septiembre de 2026 y fue reemplazado por Perplexity Agent API (POST https://api.perplexity.ai/v1/agent). Las solicitudes síncronas y en streaming existentes de Sonar siguen funcionando porque Perplexity las reformula automáticamente en el servidor como llamadas a Agent API, pero las solicitudes asíncronas de Sonar ya no cuentan con soporte y deben migrar al modo en segundo plano de Agent API. [5]

### ¿Cómo se establecen los precios y la facturación de Search API de Perplexity?

Search API devuelve resultados web clasificados con fragmentos de texto extraídos en formato JSON sin invocar un modelo grande de lenguaje ni cobrar tarifas por tokens. La búsqueda estándar cuesta $5.00 por cada 1,000 solicitudes POST /search exitosas ($0.005 por solicitud), y Fast Search (search_type: "fast") cuesta $1.00 por cada 1,000 solicitudes exitosas ($0.001 por solicitud). Una sola llamada a POST /search puede incluir un arreglo de hasta cinco consultas y se sigue facturando como una única unidad. Las solicitudes no válidas, limitadas por tasa o fallidas no se facturan. [4]

### ¿Cuál es la diferencia entre Agent API y Orchestrator API de Perplexity?

Agent API sigue la especificación Open Responses y ejecuta un bucle agéntico completo de varios pasos con herramientas integradas (búsqueda web, Finance Search, People Search, obtención de URL, entornos aislados de ejecución de código de 20 minutos y servidores MCP) y niveles de esfuerzo preajustados (fast, low, medium, high y xhigh), devolviendo una respuesta citada y resultados de búsqueda tipados. Orchestrator API es una pasarela de modelos multiproveedor que permite a los desarrolladores invocar modelos de Anthropic, OpenAI, Google, xAI y de pesos abiertos en formatos estándar de solicitud de OpenAI o Anthropic con enrutamiento perplexity/auto, conmutación por error entre despliegues y almacenamiento en caché de indicaciones. [7]

### ¿Cuál es la diferencia entre PerplexityBot y Perplexity-User en robots.txt?

PerplexityBot/1.0 es el rastreador de búsqueda automatizado de Perplexity que indexa sitios web para que puedan aparecer en los resultados de búsqueda de Perplexity; obedece las reglas de robots.txt (actualizándose en un plazo de 24 horas) y utiliza direcciones IP publicadas en perplexity.ai/perplexitybot.json. Perplexity-User/1.0 obtiene páginas específicas bajo demanda cuando un usuario en vivo formula una pregunta a Perplexity; dado que actúa por solicitud directa del usuario, suele ignorar robots.txt y utiliza las direcciones IP publicadas en perplexity.ai/perplexity-user.json. Ninguno de los dos rastreadores recopila datos para entrenar modelos fundacionales de IA. [1]

## Frases citables

- Perplexity finalizó el soporte para la versión heredada de Sonar Chat Completions el 27 de septiembre de 2026, reformulando automáticamente las llamadas síncronas y en streaming de Sonar en solicitudes de Agent API y discontinuando las solicitudes asíncronas de Sonar en favor del modo en segundo plano. [5]
- La plataforma API de Perplexity consta de siete API principales: Agent API, Orchestrator API, Search API, Context API, Monitor API, Embeddings API y Decisions API, junto con la CLI pplx y servidores MCP. [4][7]
- Agent API (POST https://api.perplexity.ai/v1/agent) sigue el estándar Open Responses, ofrece cinco niveles de esfuerzo (fast, low, medium, high y xhigh) y enruta entre modelos de Sonar, OpenAI, Anthropic, Google, xAI, Z.AI, Moonshot AI y NVIDIA con búsqueda web, financiera y de personas integrada, entornos aislados de código e integración con MCP. [5][6]
- Search API de Perplexity cobra $5.00 por cada 1,000 solicitudes estándar exitosas o $1.00 por cada 1,000 solicitudes de Fast Search sin tarifas por tokens, contabilizando como una sola unidad facturable una solicitud que incluya un arreglo de hasta cinco consultas. [4]
- Perplexity opera dos agentes web, PerplexityBot/1.0 (21 prefijos IPv4 /32 publicados al 18 de noviembre de 2026) para indexación de búsqueda y Perplexity-User/1.0 (10 prefijos IPv4 /32 publicados al 28 de octubre de 2026) para recuperaciones iniciadas por usuarios, y declara que ninguno de los bots rastrea contenido para entrenar modelos fundacionales de IA. [1][2][3]

## Cronología

- 2026-09-27: Perplexity finaliza el soporte oficial de la versión heredada de Sonar Chat Completions y traslada a los desarrolladores hacia Agent API, basada en Open Responses. [5]
- 2026-10-28: Perplexity actualiza la fuente pública de direcciones IPv4 permitidas para Perplexity-User (perplexity-user.json) con 10 prefijos /32. [3]
- 2026-11-18: Perplexity actualiza la fuente pública de direcciones IPv4 permitidas para PerplexityBot (perplexitybot.json) con 21 prefijos /32. [2]

## Fuentes

1. Perplexity Crawlers - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/resources/perplexity-crawlers (consultado 2026-11-23; tier 3: official site)
2. PerplexityBot Published IPv4 Prefixes (perplexitybot.json). Perplexity. publicado 2026-11-18. https://www.perplexity.ai/perplexitybot.json (consultado 2026-11-23; tier 3: official site)
3. Perplexity-User Published IPv4 Prefixes (perplexity-user.json). Perplexity. publicado 2026-10-28. https://www.perplexity.ai/perplexity-user.json (consultado 2026-11-23; tier 3: official site)
4. Pricing - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/getting-started/pricing (consultado 2026-11-23; tier 3: official site)
5. Migrate from Sonar to the Agent API - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/migrate-from-sonar/overview (consultado 2026-11-23; tier 3: official site)
6. Agent API Quickstart - Perplexity API Documentation. Perplexity. https://docs.perplexity.ai/docs/agent-api/quickstart (consultado 2026-11-23; tier 3: official site)
7. Perplexity API Documentation Index (llms.txt). Perplexity. https://docs.perplexity.ai/llms.txt (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Perplexity." Versión a3bb16c6, 2026-11-23. https://mimirwiki.com/es/wiki/perplexity
