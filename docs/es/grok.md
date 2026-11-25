---
title: "Grok"
subtitle: "Familia de modelos de inteligencia artificial generativa, API para desarrolladores y conjunto de aplicaciones agénticas desarrollado por xAI (SpaceX Super Intelligence LLC)"
canonical_url: https://mimirwiki.com/es/wiki/grok
language: es
page_class: entity
revision_sha256: 59d61f74f9539d78d13fd2e1f54991bfc8ea981f9222e6629a2d7bc767bfcbd0
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/grok.md
  txt: https://mimirwiki.com/es/wiki/grok.txt
  json: https://mimirwiki.com/es/wiki/grok.json
  jsonld: https://mimirwiki.com/es/wiki/grok.jsonld
translations:
  en: https://mimirwiki.com/wiki/grok
  ko: https://mimirwiki.com/ko/wiki/grok
  ja: https://mimirwiki.com/ja/wiki/grok
  zh: https://mimirwiki.com/zh/wiki/grok
---

# Grok

> Desarrollada por xAI (SpaceX Super Intelligence LLC), la familia Grok abarca desde el lanzamiento de pesos abiertos Grok-1 Mixture-of-Experts de 314 mil millones de parámetros (Apache 2.0) y Grok-2 (2024) hasta el modelo insignia de finales de 2026 Grok 4.7 (`grok-4.7`), que cuenta con una ventana de contexto de 500,000 tokens, fecha de corte de conocimiento en mayo de 2026, razonamiento cifrado configurable y precios de API de $2.00 por millón de tokens de entrada y $6.00 por millón de tokens de salida. El 12 de octubre de 2026, xAI lanzó The X Subscription ($0 Free, $8 Plus, $30 Premium, $100 Super y $200 Ultra al mes), integrando Grok, Grok Bot, los agentes de programación de Cursor y X Premium en un único cupo semanal compartido de uso de IA.

Grok es una familia de modelos de inteligencia artificial generativa, API para desarrolladores y aplicaciones conversacionales y de programación desarrollada por xAI (que opera en 2026 bajo SpaceX Super Intelligence LLC / SpaceXSI) e integrada en `grok.com`, aplicaciones móviles, la plataforma social X y el entorno de programación Cursor. Encabezada a finales de 2026 por el modelo insignia de razonamiento y programación Grok 4.7 (`grok-4.7`), junto con modelos dedicados de generación de voz (Voice), imágenes (Imagine) y video (Imagine), Grok se ofrece a los desarrolladores mediante la API Responses de xAI y a consumidores y equipos a través de la suscripción unificada The X Subscription.

**También conocido como:** Grok, xAI, SpaceX Super Intelligence, Grok 4.7, The X Subscription, Grok-1

## Datos clave

- **Desarrollador y entidad corporativa:** xAI / SpaceX Super Intelligence LLC (SpaceXSI); suscripciones comercializadas por X Subscription Corp. [4]
- **Modelo insignia de 2026:** Grok 4.7 (grok-4.7): contexto de 500K tokens, corte de conocimiento de mayo de 2026, $2.00 / $6.00 por 1M de tokens de entrada/salida [2]
- **Suite multimodal y de agentes:** Grok Chat, Grok Build, Grok Bot, Imagine (Image 2.0 y Video 1.5), Voice API (grok-voice-3.0), Grokipedia [3]
- **The X Subscription (12 oct 2026):** Plan unificado que agrupa Grok, Grok Bot, Cursor y X Premium ($0 Free, $8 Plus, $30 Premium, $100 Super, $200 Ultra) [4]
- **Lanzamiento de pesos abiertos:** Grok-1 (xai-org/grok-1): MoE de 314 mil millones de parámetros y 8 expertos (2 activos por token), 64 capas, licencia Apache 2.0 [7]

## Datos básicos

- **Desarrollador:** xAI (SpaceX Super Intelligence LLC / SpaceXSI) [4]
- **Modelo insignia:** Grok 4.7 (grok-4.7) [1]
- **Ventana de contexto:** 500,000 tokens (Grok 4.7); 8,192 tokens (Grok-1 de pesos abiertos) [2]
- **Corte de conocimiento:** Mayo de 2026 (Grok 4.7) [2]
- **Precios de API de Grok 4.7:** $2.00 / 1M tokens de entrada; $6.00 / 1M tokens de salida [1]
- **Precios de API de voz y medios:** STS $0.08/min; TTS $15/1M caracteres; STT $0.10-$0.20/h; Imagen desde $0.02/img; Video desde $0.02/seg [1]
- **Niveles de límites de tasa de API:** Tier 0 ($0) a Tier 4 ($5,000+ de gasto acumulado desde el 1 de ene de 2026): hasta 500 RPS y 100M TPM en Grok 4.5-4.7 [3]
- **Niveles de The X Subscription:** Free ($0), Plus ($8/mes), Premium ($30/mes, 4x), Super ($100/mes, 15x), Ultra ($200/mes, 50x) [6]
- **Plataformas socias en la nube:** API de xAI (api.x.ai/v1), Google Cloud Vertex AI, Microsoft Foundry [1]
- **Licencia de pesos abiertos:** Apache 2.0 (checkpoint Grok-1 de 314B en github.com/xai-org/grok-1) [7]

## Evolución de Grok-1 y Grok-2 a SpaceX Super Intelligence

Grok fue creado por xAI para ofrecer razonamiento conversacional, asistencia de programación y síntesis de información en tiempo real integrada con la red social X.[7][8] Durante su primera generación, xAI publicó el punto de control (checkpoint) base de pesos abiertos Grok-1 (`github.com/xai-org/grok-1` y `huggingface.co/xai-org/grok-1`) bajo la licencia Apache 2.0 junto con código de inferencia de referencia en JAX.[7] Grok-1 es un modelo de lenguaje Mixture-of-Experts (MoE) de 314 mil millones de parámetros construido con 64 capas de transformador, 8 expertos por capa con 2 expertos activados por token, una dimensión de embedding de 6,144, 48 cabezales de atención de consulta y 8 cabezales de clave/valor, embeddings posicionales rotatorios (RoPE), un vocabulario SentencePiece de 131,072 tokens, soporte para fragmentación de activaciones (activation sharding) y cuantización de 8 bits, y una longitud máxima de secuencia de 8,192 tokens.[7]

En agosto de 2024, xAI lanzó Grok-2, seguido el 12 de diciembre de 2024 por una versión mejorada de Grok-2 (`grok-2-1212` y `grok-2-vision-1212`) que operaba tres veces más rápido, desplegó acceso gratuito en la plataforma X junto con búsqueda web en tiempo real, citas de fuentes en línea, un "botón Grok" en la cronología y el generador autorregresivo de imágenes fotorrealistas Aurora, además de reducir los precios de la API a $2 por millón de tokens de entrada y $10 por millón de tokens de salida.[8]

Para 2026, la documentación para desarrolladores, los anuncios de noticias y el portal de precios de xAI operan bajo la entidad corporativa SpaceX Super Intelligence LLC (comercializada como SpaceXSI, con las cuentas sociales `@SpaceXSI` y `@grok`), mientras que las suscripciones directas de autoservicio para consumidores y equipos se comercializan exclusivamente a través de X Subscription Corp.[1][4][5] La cartera de productos se amplió más allá del chat hasta convertirse en una suite completa compuesta por Grok Chat, Grok Build (programación agéntica), Grok Bot (compañeros de equipo autónomos de IA), Grok Imagine (generación de imágenes y video), Grok Voice y Grokipedia.[3][4]

## Grok 4.7 y el catálogo de modelos multimodales

A noviembre de 2026, Grok 4.7 (`grok-4.7`) es el modelo fundacional insignia en toda la plataforma Grok y la API de xAI, recomendado para todas las cargas de trabajo de texto, chat e ingeniería de software.[1][2] Grok 4.7 ofrece una ventana de contexto de 500,000 tokens, esfuerzo de razonamiento configurable, fecha de corte de conocimiento en mayo de 2026 y precios de lista de $2.00 por millón de tokens de entrada y $6.00 por millón de tokens de salida (una reducción del 40% en el costo de salida frente a los precios de $2/$10 de Grok-2).[1][2][8]

Entre los comportamientos técnicos clave de Grok 4.7 y la línea de API de Grok 4.x se incluyen:[2][3]

- **Contenido de razonamiento cifrado**: en la API Responses de xAI (`POST https://api.x.ai/v1/responses`), `grok-4.7` siempre devuelve `reasoning.encrypted_content` en su carga útil, incluso cuando el parámetro `include` de la solicitud no lo pide explícitamente.[2]
- **Orden flexible de roles y reglas de parámetros**: los modelos de chat admiten un orden arbitrario de los roles `system`, `user` y `assistant` en los contextos conversacionales.[2] Para `grok-4.20` y todos los modelos posteriores, `logprobs` y `top_logprobs` no son compatibles y se ignoran silenciosamente si se envían.[2]
- **Restricciones de entrada visual**: los modelos de Grok con capacidad de visión aceptan archivos `jpg`/`jpeg` y `png` de hasta 20 MiB por imagen sin límite en la cantidad máxima de imágenes por solicitud (dentro de la ventana de contexto de tokens) y admiten indicaciones intercaladas de imagen y texto en cualquier orden.[2]
- **Anclaje explícito en tiempo real**: de forma predeterminada, los modelos de la API de Grok no tienen acceso a eventos actuales posteriores a su corte de entrenamiento de mayo de 2026, salvo que el invocador habilite herramientas de búsqueda del lado del servidor (Web Search, X Search, Collections RAG, Code Execution o Remote MCP Tools).[1][2]

En el catálogo más amplio de la API de xAI (detallado en las especificaciones de límites de tasa y precios de noviembre de 2026), xAI ofrece varias familias de modelos:[1][2][3]

| Familia de modelos / endpoints | Identificadores de modelos activos | Precios / especificaciones clave |
| --- | --- | --- |
| Lenguaje y razonamiento insignia | `grok-4.7` (último), `grok-4.6`, `grok-4.5`, `grok-4.3` | Contexto de 500K (`grok-4.7`); $2.00 / 1M entrada, $6.00 / 1M salida |
| Agentes especializados y programación | `grok-build-0.1`, `grok-4.20-multi-agent-0309`, `grok-4.20-0309-reasoning`, `grok-4.20-0309-non-reasoning` | Impulsa la programación agéntica de Grok Build, refactorización y flujos de trabajo multiagente |
| Generación de imágenes (Imagine) | `grok-imagine-image-2.0` (Image 2.0), `grok-imagine-image` | Generación 1K / 2K, edición y edición multiimagen desde $0.02 / imagen |
| Generación de video (Imagine) | `grok-imagine-video-1.5` (Video 1.5), `grok-imagine-video-1.5-lite`, `grok-imagine-video` | 480p / 720p / 1080p (hasta 15s en 1080p en Super/Ultra), imagen a video, referencia a video, edición, extensión; desde $0.02 / seg |
| API de voz y audio | `grok-voice-3.0`, Text to Speech (TTS), Speech to Text (STT) | Speech-to-Speech (STS): $0.08/min; TTS: $15.00/1M caracteres; STT por lotes: $0.10/h; STT en streaming: $0.20/h |

## Arquitectura de la API de xAI, integraciones en la nube y niveles de límites de tasa

La plataforma para desarrolladores de xAI expone la moderna API Responses (`https://api.x.ai/v1/responses`), una interfaz REST compatible con OpenAI, el paquete nativo de Python `xai_sdk` basado en gRPC e integraciones oficiales con Vercel AI SDK (`@ai-sdk/xai`), Google Cloud Vertex AI y Microsoft Foundry.[1][3] Entre las capacidades empresariales avanzadas de la API se incluyen Prompt Caching, Context Compaction, Priority Processing, Custom Moderation Controls, Batch API, Deferred Completions, Async Requests, WebSocket Mode, autenticación mTLS, endpoints regionales y marcado de agua de salida (Output Watermarking).[1][3]

Cada equipo en la API de xAI se rige por límites de tasa por modelo en dos dimensiones: solicitudes por segundo (RPS) y tokens por minuto (TPM) para modelos de lenguaje, o sesiones concurrentes (CST) y RPS para endpoints de voz.[3] El tope de solicitudes por segundo de un equipo se deriva de su presupuesto por minuto (`RPM / 48`, con un mínimo de 2 RPS) para evitar el agotamiento por ráfagas en un solo segundo.[3] Todos los tokens de entrada (texto, imagen, audio), tokens de finalización, tokens de razonamiento y tokens de entrada en caché cuentan para el límite de TPM del modelo.[3] Los niveles de límites de tasa se desbloquean de forma automática y permanente (sin descender nunca) según el gasto acumulado en la API desde el 1 de enero de 2026:[3]

| Nivel de límite de tasa | Umbral de gasto acumulado (desde el 1 de ene de 2026) | `grok-4.7` / `4.6` / `4.5` (RPS / TPM) | `grok-4.3` / `grok-build-0.1` / `4.20` (RPS / TPM) | `grok-4.20-multi-agent` (RPS / TPM) | `grok-imagine-image-2.0` (RPS) | `grok-imagine-video-1.5` (RPS) | `grok-voice-3.0` (CST) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Tier 0 | $0 (predeterminado) | 150 RPS / 50M TPM | 37 RPS / 10M TPM | 9 RPS / 2.5M TPM | 6 RPS | 10 RPS | 10 CST |
| Tier 1 | $50 | 172 RPS / 53M TPM | 50 RPS / 15M TPM | 12 RPS / 3.7M TPM | 12 RPS | 20 RPS | 20 CST |
| Tier 2 | $250 | 208 RPS / 60M TPM | 75 RPS / 25M TPM | 18 RPS / 6.2M TPM | 25 RPS | 39 RPS | 50 CST |
| Tier 3 | $1,000 | 312 RPS / 74M TPM | 125 RPS / 45M TPM | 31 RPS / 11M TPM | 50 RPS | 79 RPS | 100 CST |
| Tier 4 | $5,000 | 500 RPS / 100M TPM | 208 RPS / 85M TPM | 56 RPS / 21M TPM | 100 RPS | 158 RPS | 200 CST |
| Enterprise | Personalizado (vía sales@x.ai) | Personalizado | Personalizado | Personalizado | Personalizado | Personalizado | Personalizado |

## The X Subscription: unificación de Grok, Grok Bot, Cursor y X Premium

El 12 de octubre de 2026, xAI presentó The X Subscription, un plan de suscripción global consolidado que unifica cuatro productos bajo una sola cuenta de facturación y un cupo semanal compartido de uso de IA: Grok (Chat, Voice, Imagine y Build), Grok Bot (compañeros de equipo autónomos de IA), el IDE Cursor y sus agentes de programación en la nube (incluidos el alojamiento de código mediante Origin y las revisiones de código con IA mediante Bugbot), y los beneficios de la red social X Premium.[4][5][6]

Cada nivel de pago proporciona un cupo de uso de modelos Grok con renovación semanal compartido entre las aplicaciones web y móviles de Grok, la pestaña de Grok en X, Grok Bot y Cursor, lo que ofrece al menos el doble de uso de programación con modelos Grok que el plan independiente anterior comparable de Cursor (y 3 veces más uso de programación en los planes Teams que el antiguo Cursor Teams).[4][5] Los suscriptores independientes existentes de SuperGrok, Cursor y X Premium pueden conservar opcionalmente sus planes anteriores o cambiar a The X Subscription con un reembolso prorrateado automático por el tiempo no utilizado (salvo las suscripciones de Cursor contratadas en la Apple App Store, que deben cancelarse directamente a través de Apple).[4][6]

| Nivel del plan | Precio mensual | Precio anual | Cupo semanal compartido de uso de IA | Funciones clave incluidas en Grok, Cursor y X |
| --- | --- | --- | --- | --- |
| Free | $0 / mes | $0 / año | Limitado | Acceso diario a Grok, asignación inicial del agente de programación de Cursor, X estándar, 6.00% de APY en X Money y 3% de reembolso (con depósito directo) |
| Plus | $8 / mes | $80 / año ($7/mes) | Base (1x) | Cupo compartido de Grok + Cursor, Grok Chat/Voice/Imagine/Build, acceso a la API de Grok, marca de verificación de X Premium, menos anuncios en la cronología, herramientas para creadores (sin Grok Bot; no disponible para Teams) |
| Premium | $30 / mes | $300 / año ($25/mes) | 4x Plus | Desbloquea Grok Bot, los modelos más recientes de Grok, agentes y automatizaciones en la nube de Cursor, alojamiento de código Origin, revisiones de código con IA de Bugbot, navegación sin anuncios en la mayoría de las secciones de X, 6.00% de APY en X Money (anteriormente $90/mes combinados por SuperGrok + Cursor Pro + X Premium+) |
| Super | $100 / mes | $1,000 / año ($84/mes) | 15x Plus | Todo lo incluido en Premium más generación de video de 15 segundos en 1080p, respuestas ultrarrápidas y acceso prioritario en horas pico |
| Ultra | $200 / mes | $2,000 / año ($167/mes) | 50x Plus | Todo lo incluido en Super con un cupo semanal de uso de IA 50 veces superior al de Plus para usuarios avanzados |
| Teams | $30 - $200 / puesto / mes | $300 - $2,000 / puesto / año | 4x a 50x Plus por puesto | Combinación flexible de puestos Premium/Super/Ultra, facturación centralizada, analítica de uso, SSO SAML/OIDC, cumplimiento SOC 2 y mercado interno de equipo para reglas, habilidades y complementos |

Aunque los planes de pago incluyen acceso a la consola de la API de Grok, el consumo directo de tokens de la API se factura por separado según las tarifas estándar de la API y no descuenta del cupo semanal de uso de la suscripción.[5] De manera similar, los modelos de terceros ajenos a Grok siguen siendo seleccionables dentro de Cursor en los planes Premium, Super y Ultra, pero se facturan por separado a precios de lista de la API mediante recargas prepagadas y créditos de Additional Usage en lugar de descontarse del cupo incluido de Grok.[4][5][6]

## Preguntas frecuentes

### ¿Cuáles son las especificaciones y los precios de API de Grok 4.7?

Grok 4.7 (grok-4.7) es el modelo insignia de lenguaje, programación y razonamiento de xAI a finales de 2026. Admite una ventana de contexto de 500,000 tokens, esfuerzo de razonamiento configurable (devolviendo siempre reasoning.encrypted_content en la API Responses), fecha de corte de conocimiento en mayo de 2026 y entradas ilimitadas de imágenes de hasta 20 MiB por archivo JPEG/PNG. Los precios estándar de la API son de $2.00 por millón de tokens de entrada y $6.00 por millón de tokens de salida. [2]

### ¿Qué incluye The X Subscription anunciada en octubre de 2026?

Presentada el 12 de octubre de 2026, The X Subscription agrupa Grok (Chat, Voice, generación de imágenes y video con Imagine, y Grok Build), los compañeros de IA Grok Bot, el editor de programación y agentes en la nube Cursor (incluidos el alojamiento de código Origin y las revisiones de código con IA de Bugbot) y X Premium en un solo plan con un cupo semanal compartido de uso de IA. Los niveles son Free ($0), Plus ($8/mes o $80/año), Premium ($30/mes o $300/año, 4x el uso de Plus, reemplazando $90/mes de los planes separados SuperGrok, Cursor Pro y X Premium+), Super ($100/mes o $1,000/año, 15x el uso de Plus) y Ultra ($200/mes o $2,000/año, 50x el uso de Plus). [4]

### ¿Cubre The X Subscription los modelos de terceros en Cursor o los cargos directos por tokens de la API de Grok?

No. El cupo semanal compartido de uso en The X Subscription cubre los modelos Grok utilizados en las aplicaciones de Grok, X, Grok Bot (en Premium y niveles superiores) y Cursor. Los modelos de terceros en Cursor siguen estando disponibles en los planes Premium, Super y Ultra, pero se facturan por separado a precios de lista de la API desde el primer token mediante recargas prepagadas. De manera similar, las llamadas directas a la API de Grok se facturan por separado a las tarifas estándar por token de la API. [6]

### ¿Cómo funcionan los niveles de límites de tasa de la API de xAI?

Los límites de tasa de la API de xAI se aplican por modelo sobre las solicitudes por segundo (RPS, calculadas como RPM / 48 con un mínimo de 2) y los tokens por minuto (TPM, contando tokens de entrada, finalización, razonamiento y caché). Los niveles se desbloquean de manera automática y permanente según el gasto acumulado desde el 1 de enero de 2026: Tier 0 ($0), Tier 1 ($50), Tier 2 ($250), Tier 3 ($1,000) y Tier 4 ($5,000). Para Grok 4.5, 4.6 y 4.7, los límites escalan desde 150 RPS y 50M TPM en Tier 0 hasta 500 RPS y 100M TPM en Tier 4. [3]

## Frases citables

- A noviembre de 2026, el modelo de lenguaje insignia de xAI es Grok 4.7 (grok-4.7), con una ventana de contexto de 500,000 tokens, fecha de corte de conocimiento en mayo de 2026, contenido de razonamiento cifrado obligatorio en la API Responses y precios de $2.00 por millón de tokens de entrada y $6.00 por millón de tokens de salida. [1][2]
- El lanzamiento de pesos abiertos Grok-1 de xAI (xai-org/grok-1) es un modelo Mixture-of-Experts de 314 mil millones de parámetros con licencia Apache 2.0, 64 capas, 8 expertos por capa (2 utilizados por token), tamaño de embedding de 6,144 y ventana de contexto de 8,192 tokens. [7]
- El 12 de octubre de 2026, xAI (SpaceX Super Intelligence LLC) lanzó The X Subscription, que combina Grok, Grok Bot, Cursor y X Premium en una sola suscripción con un cupo semanal compartido de uso de IA en cinco niveles: Free ($0), Plus ($8/mes), Premium ($30/mes, 4x Plus), Super ($100/mes, 15x Plus) y Ultra ($200/mes, 50x Plus). [4][5][6]
- En la API de xAI, los niveles de límites de tasa escalan de forma permanente según el gasto acumulado desde el 1 de enero de 2026, desde Tier 0 ($0 predeterminado: 150 RPS y 50M TPM en Grok 4.5/4.6/4.7) hasta Tier 4 ($5,000+ de gasto: 500 RPS y 100M TPM en Grok 4.5/4.6/4.7). [3]
- La suite de API multimodal de xAI incluye Grok Voice API (Speech-to-Speech a $0.08/minuto, TTS a $15.00/1M caracteres, STT a $0.10/hora por lotes y $0.20/hora en streaming), Imagine Image 2.0 (desde $0.02/imagen) e Imagine Video 1.5 (desde $0.02/segundo en 480p, 720p y 1080p). [1][2][3]

## Cronología

- 2024-03: xAI publica el punto de control de pesos abiertos Grok-1 Mixture-of-Experts de 314 mil millones de parámetros y el código JAX bajo la licencia Apache 2.0. [7]
- 2024-12-12: xAI despliega la versión más rápida de Grok-2 (grok-2-1212 y grok-2-vision-1212) de forma gratuita para todos los usuarios de X, lanza el generador de imágenes Aurora y reduce los precios de la API a $2/$10 por millón de tokens. [8]
- 2026-05: Fecha de corte de conocimiento del modelo insignia Grok 4.7. [2]
- 2026-10-12: xAI (SpaceX Super Intelligence LLC) lanza The X Subscription, unificando Grok, Grok Bot, Cursor y X Premium en un único plan y cupo de uso compartido. [4]
- 2026-11-13: xAI actualiza su tabla de límites de tasa de la API que cubre Grok 4.7, Grok Build 0.1, Imagine Image 2.0, Imagine Video 1.5 y Grok Voice 3.0. [3]

## Fuentes

1. Grok API Documentation Overview | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). https://docs.x.ai/overview (consultado 2026-11-23; tier 3: official site)
2. Grok Models & Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). publicado 2026-09-21. https://docs.x.ai/developers/models (consultado 2026-11-23; tier 3: official site)
3. Rate Limits | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). publicado 2026-11-13. https://docs.x.ai/developers/rate-limits (consultado 2026-11-23; tier 3: official site)
4. Introducing The X Subscription | SpaceXSI. xAI (SpaceX Super Intelligence LLC). publicado 2026-10-12. https://x.ai/news/x-subscription (consultado 2026-11-23; tier 3: official site)
5. Pricing: Compare Plans | SpaceXSI. xAI (SpaceX Super Intelligence LLC). https://x.ai/pricing (consultado 2026-11-23; tier 3: official site)
6. The X Subscription Pricing | SpaceXSI Docs. xAI (SpaceX Super Intelligence LLC). publicado 2026-10-11. https://docs.x.ai/x-subscription/pricing (consultado 2026-11-23; tier 3: official site)
7. Grok-1 Open Release Repository and Model Specifications (xai-org/grok-1). xAI. https://raw.githubusercontent.com/xai-org/grok-1/main/README.md (consultado 2026-11-23; tier 3: official site)
8. Bringing Grok to Everyone | SpaceXSI. xAI (SpaceX Super Intelligence LLC). publicado 2024-12-12. https://x.ai/news/grok-1212 (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Grok." Versión 59d61f74, 2026-11-23. https://mimirwiki.com/es/wiki/grok
