---
title: "Cursor"
subtitle: "Agente de programación con IA y entorno de desarrollo de software creado por Anysphere, Inc. e incluido en The X Subscription"
canonical_url: https://mimirwiki.com/es/wiki/cursor
language: es
page_class: entity
revision_sha256: 3fc93a682b4512adb8b28427ff1ac96600b61ee1ef3feba9a65029be7539f478
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 9
alternates:
  md: https://mimirwiki.com/es/wiki/cursor.md
  txt: https://mimirwiki.com/es/wiki/cursor.txt
  json: https://mimirwiki.com/es/wiki/cursor.json
  jsonld: https://mimirwiki.com/es/wiki/cursor.jsonld
translations:
  en: https://mimirwiki.com/wiki/cursor
  ko: https://mimirwiki.com/ko/wiki/cursor
  ja: https://mimirwiki.com/ja/wiki/cursor
  zh: https://mimirwiki.com/zh/wiki/cursor
---

# Cursor

> Cursor es un agente de programación con IA y entorno de desarrollo creado por Anysphere, Inc., fundada en 2022. En junio de 2026, SpaceX acordó adquirir Cursor por 60 000 millones de dólares en acciones. Al 23 de noviembre de 2026, Cursor se comercializa mediante The X Subscription entre $0 y $200 al mes, con soporte para Agent, completado Tab, Cloud Agents, Rules, Skills, MCP, CLI y varios proveedores de modelos.

Cursor es un agente de programación con inteligencia artificial y un entorno de desarrollo de software creado por Anysphere, Inc. para comprender bases de código, planificar e implementar funciones, depurar errores y revisar cambios de código. Fundada en 2022 como Anysphere, la startup acordó en junio de 2026 ser adquirida por SpaceX en una operación en acciones de 60 000 millones de dólares, tras la fusión previa de SpaceX con xAI. Al 23 de noviembre de 2026, Cursor se distribuye como parte de The X Subscription a través de X Subscription Corp. en los planes Free, Plus ($8/mes), Premium ($30/mes), Super ($100/mes), Ultra ($200/mes), Teams ($30 a $200 por puesto/mes) y planes Enterprise personalizados, mientras que los planes heredados de Cursor siguen activos para los suscriptores anteriores. Cursor funciona en un IDE de escritorio integrado, una ventana dedicada Agents Window, una interfaz de línea de comandos (CLI), web e iOS, y admite los modelos propios Grok y Composer junto con modelos de terceros de OpenAI, Anthropic y Google.

**También conocido como:** Cursor IDE, Cursor Editor, Anysphere Cursor

## Datos clave

- **Desarrollador:** Anysphere, Inc. [9]
- **Acuerdo de adquisición de SpaceX:** 60 000 millones de dólares en acciones, informado el 2026-06-16 [1]
- **Precios de planes individuales:** Free ($0), Plus ($8/mes), Premium ($30/mes), Super ($100/mes), Ultra ($200/mes) (al 2026-11-23) [5]
- **Precios del plan Teams:** $30, $100 o $200 por puesto/mes (al 2026-11-23) [5]
- **Certificaciones de seguridad:** SOC 2 Type II, ISO/IEC 27001:2022, ISO/IEC 42001:2023, AIUC-1 (al 2026-11-23) [8]

## Datos básicos

- **Desarrollador:** Anysphere, Inc. [9]
- **Fundación:** 2022 (como Anysphere) [1]
- **Acuerdo de adquisición:** SpaceX, 60 000 millones de dólares en acciones (informado el 2026-06-16, cierre previsto en el 3.er trimestre de 2026) [1]
- **Distribuidor de suscripciones:** X Subscription Corp. (The X Subscription) (al 2026-11-23) [4]
- **Superficies compatibles:** Editor, Agents Window, CLI, Cursor SDK, aplicación para iOS (al 2026-11-23) [6]
- **Personalización:** Plugins, Rules, Skills, Subagents, Hooks, MCP (al 2026-11-23) [3]
- **Modelos de Cursor incluidos:** Grok 4.7, Grok 4.6, Grok 4.5, Composer 2.5 (al 2026-11-23) [5]
- **Planes individuales:** Free ($0), Plus ($8/mes), Premium ($30/mes), Super ($100/mes), Ultra ($200/mes) (al 2026-11-23) [5]
- **Teams y Enterprise:** Teams ($30, $100 o $200/puesto/mes); Enterprise (personalizado) (al 2026-11-23) [5]
- **ARR reportado (junio de 2025):** Más de 500 millones de dólares (informe de Bloomberg y TechCrunch) (al 2025-06-05) [2]
- **Certificaciones de seguridad:** AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023, SOC 2 Type II (al 2026-11-23) [8]
- **Sitio web oficial:** cursor.com [9]

## Funciones del producto, personalización e interfaces de Cursor

Cursor está documentado por Anysphere, Inc. como un agente de programación para el desarrollo de software, con usos que incluyen el rastreo y la comprensión de repositorios, la definición del alcance y la implementación de funciones mediante Plan Mode, la reproducción y corrección de errores, la inspección de diferencias (diffs) y la ejecución de comprobaciones antes de fusionar cambios, así como la conexión con herramientas externas de desarrollo.[3] Desde el nivel Free, Cursor ofrece acceso limitado a Agent, Chat y completado Tab utilizando los modelos propios de Cursor.[6]

La interfaz de Agent de Cursor abarca un IDE de escritorio, una ventana dedicada Agents Window, un cliente web, Cursor para iOS y una interfaz de línea de comandos (CLI).[3][6][7] Al 23 de noviembre de 2026, la documentación de Agent cubre Projects, Agent Review, Planning, Prompting, Voice Chat, Debugging, Design Mode, Tools y Security, mientras que la documentación de la CLI cubre Shell Mode, ACP y ejecución Headless o en CI.[3] Cursor también publica un Cursor SDK para TypeScript, Python e integraciones Bridge.[3]

Cursor organiza la personalización de flujos de trabajo en seis mecanismos documentados: Plugins, Rules, Skills, Subagents, Hooks y servidores de [Model Context Protocol](https://mimirwiki.com/es/wiki/model-context-protocol) (MCP).[3] En los planes Teams y Enterprise, las organizaciones también disponen de un mercado de equipo para distribuir reglas, habilidades y plugins internos.[4][5]

La sección de Integraciones de la documentación de Cursor incluye GitHub, GitLab, Azure DevOps, Bitbucket, JetBrains, Xcode, Slack, Microsoft Teams, Jira, Linear, Notion, Tailscale y Deeplinks.[3]

## Cloud Agents, Origin, Agent SDK y Voice Chat de Cursor

Cursor incluye Cloud Agents, Automations, el alojamiento de código Origin y revisiones de código con IA mediante Bugbot a partir del nivel de suscripción Premium.[4][5] Al 23 de noviembre de 2026, la documentación de Cloud Agents abarca la configuración de entornos, compilaciones, aplicaciones, automatizaciones, Bugbot, revisión de seguridad, remediación de vulnerabilidades, enrutamiento y aprobación de solicitudes de extracción (pull requests), despliegues progresivos, acceso móvil, máquinas autoalojadas y una API.[3] Origin ofrece alojamiento de repositorios con CLI, replicación con GitHub, CloneKit en CI, pull requests, Code Tours, navegación y búsqueda en repositorios y políticas de acceso.[3]

Entre octubre y noviembre de 2026, Cursor publicó las siguientes incorporaciones a su plataforma en su registro de cambios.[7]

- **Origin App Marketplace (13 de octubre de 2026)**: abrió con más de 20 integraciones y envío público de aplicaciones en despliegues ([Cloudflare](https://mimirwiki.com/es/wiki/cloudflare), Netlify, Render, Spacelift, Vercel), CI (Buildkite, CircleCI, CloudBees, Depot, EngFlow, Namespace, RWX), revisión de código (CodeRabbit, Greptile, Tenki), seguridad (Artemis Security, Semgrep, Socket Security, Upwind), monitorización (Sentry) y gestión de proyectos (Linear). Las aplicaciones de Origin se autentican mediante un JWT de aplicación y tokens de acceso de instalación, reciben eventos de webhook y escriben de vuelta ejecuciones de comprobación, comentarios en pull requests y revisiones.[7]
- **Cloud Agent Canvases y Environments API (16 de octubre de 2026)**: añadió Canvases interactivos compartibles construidos por agentes en la nube, lanzó la beta de la Environments API para la gestión programática de entornos en la nube de agentes, amplió la capacidad de los entornos hasta 300 repositorios y aumentó en 5x la velocidad de carga para entornos grandes.[7]
- **Agent SDK (20 de octubre de 2026)**: alcanzó disponibilidad general para definir agentes como carpetas de código que contienen `instructions.md` para instrucciones (prompts), `tools/` para acciones tipadas, `skills/` para procedimientos bajo demanda, `mcp-connections/` para herramientas de servidores MCP y `channels/` para disparadores desde GitHub, GitLab, Bitbucket, Slack, webhooks y programaciones cron. El SDK ofrece configuración local y entornos de prueba (`npx @cursor/agent-sdk init`, `agent-sdk dev`), validación (`agent-sdk validate`), evaluación y reproducción de webhooks de pull requests (`agent-sdk eval`, `agent-sdk github replay`), plantillas (revisor de seguridad, aprobador de políticas de propietarios, corrector automático de PR y clasificador de Linear o Jira) y despliegue (`agent-sdk deploy`) en Cursor o en infraestructura autoalojada.[7]
- **Live Apps (5 de noviembre de 2026)**: publicado en todos los planes de pago con agentes en la nube habilitados. Un agente en la nube genera la estructura de una aplicación web a partir de un repositorio nuevo o existente de Cursor Origin o GitHub, aprovisiona una base de datos Postgres cuando es necesario, protege la autenticación detrás de Cursor SSO, ejecuta comprobaciones de seguridad deterministas y basadas en agentes para detectar problemas como credenciales expuestas y despliega en una URL elegida. Los administradores de equipo pueden inspeccionar todas las aplicaciones y secretos, añadir reglas de seguridad personalizadas, aprobar publicaciones bloqueadas o retirar aplicaciones; los usuarios individuales pueden compartir aplicaciones públicamente y aprovisionar claves API de Cursor para scripts o Grok Bot.[7]

El 6 de noviembre de 2026, Cursor añadió Voice Chat con agentes de programación en Agents Window, IDE, web y Cursor para iOS, incluida la activación con Siri (`"Hey Siri, call Cursor"`) y controles de Live Activity en la pantalla de bloqueo de iOS.[7] Voice Chat funciona sobre [Grok](https://mimirwiki.com/es/wiki/grok) Voice con voces seleccionables como Ara, Eve, Leo, Rex y Sal, y opera con retención cero de datos cuando Privacy Mode está activado.[7] Voice Chat proporciona conversación hablada bidireccional y es independiente del dictado de voz a texto (anteriormente Voice Mode, que se activa en el IDE con `Cmd+Shift+Space`).[7]

## Modelos compatibles de Cursor y Cursor Router

Cursor admite modelos de [OpenAI](https://mimirwiki.com/es/wiki/openai), [Anthropic](https://mimirwiki.com/es/wiki/anthropic), Google, SpaceXSI y otros proveedores, divididos al 23 de noviembre de 2026 en modelos propios de Cursor cubiertos por la cuota semanal de uso de la suscripción y modelos de terceros facturados al precio de lista de la API mediante crédito prepagado.[3][5] Optar por la residencia regional de datos añade un recargo del 10% al precio del modelo en los modelos elegibles.[5]

La cuota propia de Cursor cubre [Grok](https://mimirwiki.com/es/wiki/grok) 4.7, Grok 4.6, Grok 4.5 y Composer 2.5.[5] Cuando el uso supera la cuota semanal, se aplican las siguientes tarifas por millón de tokens al 23 de noviembre de 2026.[3][5]

| Modelo de Cursor | Contexto predeterminado / máximo | Entrada estándar / lectura de caché / salida (por 1M de tokens) | Modo rápido: entrada / lectura de caché / salida (por 1M de tokens) | Residencia de datos en EE. UU. |
| --- | --- | --- | --- | --- |
| Grok 4.7 | 256k / 500k | $2 / $0.5 / $6 (500k: $4 / $1 / $12) | $4 / $1 / $12 (500k rápido: $6 / $1.5 / $18) | Sí |
| Grok 4.6 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $12 | Sí |
| Grok 4.5 | 256k / - | $2 / $0.5 / $6 | $4 / $1 / $18 | Sí |
| Composer 2.5 | 200k / - | $0.5 / $0.2 / $2.5 | $3 / $0.5 / $15 | Sí |

Los modelos de terceros no están disponibles en los planes Free y Plus, y están disponibles a partir de Premium al precio de lista de la API desde la primera solicitud.[5] Al 23 de noviembre de 2026, la documentación de Cursor enumera los siguientes modelos de terceros, incluidos [Claude](https://mimirwiki.com/es/wiki/claude), GPT-5.6 y los modelos de [Google Gemini](https://mimirwiki.com/es/wiki/google-gemini), con precios por millón de tokens.[3][5]

| Modelo de terceros | Contexto predeterminado / máximo | Entrada | Escritura de caché | Lectura de caché | Salida | Residencia de datos en EE. UU. |
| --- | --- | --- | --- | --- | --- | --- |
| Claude Fable 5.2 | 300k / 1M | $8 | $10 | $0.2 | $40 | Sí |
| Claude Opus 5.5 | 300k / 1M | $4 | $5 | $0.2 | $20 | Sí |
| Claude Sonnet 5.5 | 200k / 1M | $2 | $2.5 | $0.1 | $10 | Sí |
| Claude Haiku 5.5 | 300k / 1M | $0.1 | $0.125 | $0.01 | $0.5 | Sí |
| GPT-5.6 Sol | 272k / 1M | $4 | $5 | $0.4 | $20 | Sí |
| GPT-5.6 Terra | 272k / 1M | $2 | $2.5 | $0.2 | $12 | Sí |
| GPT-5.6 Luna | 272k / 1M | $0.2 | $0.25 | $0.02 | $1.2 | Sí |
| Gemini 4 Neon | 200k / 1M | $3 | - | $0.15 | $15 | Sí |
| Gemini 4 Carbon | 200k / 1M | $2 | - | $0.1 | $10 | Sí |
| Gemini 4 Argon | 200k / 1M | $2 | - | $0.1 | $10 | Sí |
| Gemini 4 Hydrogen | 200k / 1M | $1.5 | - | $0.075 | $7.5 | Sí |
| Gemini 3.1 Pro | 200k / 1M | $2 | - | $0.2 | $12 | No |
| Gemini 3.8 Flash | 200k / 1M | $0.75 | - | $0.075 | $3.75 | Sí |
| Muse Wonder | 300k / 1M | $4 | - | $0.2 | $20 | No |

La función Auto de Cursor divide la selección de modelos en tres modos mediante Cursor Router: Cost, Balance e Intelligence.[5][6] Los planes individuales admiten el modo Cost (sucesor del anterior modo Auto), que se factura como una solicitud de modelo de Cursor contra la cuota semanal independientemente del modelo que atienda la solicitud.[5][6] Cursor señala que Cursor Router, que ofrece los modos Balance e Intelligence, se lanzará para los planes Teams y Enterprise en Agents Window, el editor, la CLI, Cursor SDK y la aplicación para iOS, con los equipos Enterprise iniciando con esta opción desactivada hasta que un administrador la habilite; las rutas hacia modelos de Cursor se descuentan de la cuota semanal, mientras que las rutas hacia modelos de terceros se facturan al precio de lista de la API mediante crédito prepagado más la tarifa Cursor Token Rate cuando corresponde.[5][6]

## Planes de Cursor, The X Subscription y precios heredados

Cursor se comercializa como parte de The X Subscription, una suscripción única que combina Grok, Cursor y X, distribuida directamente a través de X Subscription Corp. sin revendedores autorizados ni vendedores externos.[4][5][6] Todos los precios de suscripción publicados excluyen impuestos aplicables como el IVA.[4][5] Al 23 de noviembre de 2026, Cursor enumera los siguientes planes en The X Subscription.[4][5][6]

| Plan | Precio mensual | Precio anual | Cuota semanal incluida | Modelos de terceros |
| --- | --- | --- | --- | --- |
| Free | $0 | - | Limitada | No disponible |
| Plus | $8 | $80 | Base | No disponible |
| Premium | $30 | $300 | 4x Plus | Precio de lista de la API con crédito prepagado |
| Super | $100 | $1,000 | 15x Plus | Precio de lista de la API con crédito prepagado |
| Ultra | $200 | $2,000 | 50x Plus | Precio de lista de la API con crédito prepagado |
| Teams | $30, $100 o $200 por puesto | - | Según nivel de puesto (4x a 50x Plus) | Precio de lista de la API más Cursor Token Rate en modelos elegibles |
| Enterprise | Personalizado | Personalizado | Compartida entre Grok y Cursor | Precio de lista de la API más Cursor Token Rate en modelos elegibles |

Cada plan de pago ofrece una cuota de renovación semanal para los modelos de Cursor compartida entre Agent en el editor, la CLI, Cloud Agents, Grok Bot y las aplicaciones de Grok (Chat, Imagine, Voice y Bot); el acceso a la API de Grok está incluido en los planes de pago, pero se factura por separado a las tarifas estándar del modelo.[4][5] Plus ejecuta los modelos de Cursor con ajustes fijos (modo rápido desactivado, esfuerzo medio y Grok 4.7 con ventana de contexto de 256k) y excluye Auto, Cloud Agents, Automations, Bugbot, Origin, modelos de terceros y el uso de claves API propias (BYOK).[5] Super añade acceso prioritario a los modelos en horas pico, y Ultra añade acceso anticipado a nuevos productos y modelos.[4][5] Cuando un usuario agota la cuota semanal, Cursor no reduce la calidad ni la velocidad de las solicitudes; los usuarios pueden esperar al reinicio semanal, comprar recargas de crédito prepagado (manuales o mediante Auto Top-up con límite mensual de gasto gestionado en `grok.com/dashboard/billing`) o subir de nivel.[5] Los planes de autoservicio aceptan las principales tarjetas de crédito y débito y permiten cancelar hasta 24 horas antes de la renovación; las mejoras de plan surten efecto de inmediato y las reducciones al finalizar el periodo de facturación.[4][6]

Los planes Teams permiten combinar puestos de nivel Premium, Super y Ultra dentro de un mismo equipo (Plus no está disponible para equipos) y añaden facturación centralizada, analítica de uso, aplicación obligatoria de Privacy Mode para todo el equipo, retención personalizada de datos de Chat, mercado de equipo y SSO mediante SAML/OIDC.[4][5] Enterprise añade uso compartido en grupo, facturación mediante factura u orden de compra y transferencias bancarias, gestión de puestos mediante SCIM, controles granulares de gasto, límites por grupo, registros de auditoría, cuentas de servicio, controles avanzados de red y MCP y soporte prioritario.[4][5] En los planes Teams y Enterprise, las solicitudes elegibles a modelos de terceros y el uso con BYOK conllevan una tarifa Cursor Token Rate de $0.25 por millón de tokens sobre tokens de entrada, salida y en caché; están exentos los planes individuales, los modelos de Cursor, las solicitudes en modo Cost y los modelos de terceros cuyo precio de lectura de caché sea estrictamente inferior a $0.10 por millón de tokens en todos los niveles de precios.[5]

Cursor también mantiene planes heredados vendidos antes de The X Subscription para los suscriptores existentes.[5][6] Los planes heredados están cerrados a nuevos clientes, continúan vigentes salvo cancelación o cambio permanente a The X Subscription (lo que cancela la suscripción heredada con un reembolso prorrateado), se gestionan a través de Stripe en `cursor.com/dashboard/billing` y ofrecen dos cuotas mensuales de uso (Cursor Models y Other Models) con facturación bajo demanda para solicitudes adicionales.[5][6] Los planes heredados basados en solicitudes también incluían Max Mode para ventanas de contexto ampliadas, facturadas a la tarifa de la API del modelo más un 20%.[5]

| Plan heredado de Cursor | Precio | Plan equivalente en The X Subscription |
| --- | --- | --- |
| Hobby | Gratuito | Free |
| Start (solo en India) | ₹649/mes (impuestos incluidos) | Plus |
| Pro | $20/mes | Premium |
| Pro+ | $60/mes | Super |
| Ultra | $200/mes | Ultra |
| Teams Standard | $40/usuario/mes | Teams (puesto Premium) |
| Teams Premium | $120/usuario/mes | Teams (puesto Super) |

## Seguridad, cumplimiento normativo y controles de privacidad de Cursor

Cursor publica su arquitectura de seguridad en `cursor.com/security` (actualizada por última vez el 25 de agosto de 2026) y su Política de Privacidad en `cursor.com/privacy` (actualizada por última vez el 6 de noviembre de 2026).[8][9] Al 23 de noviembre de 2026, Cursor posee las certificaciones AIUC-1, ISO/IEC 27001:2022 e ISO/IEC 42001:2023 junto con una atestación SOC 2 Type II, pone a disposición bajo solicitud los certificados, informes y un resumen ejecutivo de pruebas de penetración a través de `trust.cursor.com`, y publica su lista de subprocesadores en el mismo portal de confianza.[4][8][9] Cursor se compromete a realizar pruebas de penetración de terceros al menos una vez al año.[8]

Cursor afirma que cada subprocesador pasa por una evaluación de riesgos de proveedores y una revisión anual, que el acceso a la infraestructura sigue el principio de mínimo privilegio con autenticación multifactor (MFA) y monitorización de registros, y que se aplican listas de bloqueo de modelos para que las solicitudes nunca se enruten hacia modelos bloqueados.[8] Cursor declara que no utiliza ni mantiene infraestructura en China y que no contrata empresas con sede en China como subprocesadores.[8] Las vulnerabilidades de seguridad notificadas a `security-reports@cursor.com` reciben acuse de recibo en un plazo de cinco días hábiles, y los incidentes críticos de seguridad se comunican por correo electrónico a los usuarios afectados.[8] Cursor también utiliza Bugbot y automatizaciones de Cloud Agents para ayudar a proteger su propia base de código.[8]

Cursor señala que Privacy Mode está disponible para cualquier persona, incluidos los usuarios gratuitos, y puede activarse desde la configuración o por un administrador de equipo o empresa, heredando los nuevos miembros la configuración del equipo.[4][8] Cuando Privacy Mode está activo, Cursor indica que los datos de código del usuario no se utilizan para entrenar modelos ni por Cursor ni por sus proveedores de modelos, con respaldo de controles técnicos y cláusulas contractuales, y que Voice Chat funciona con retención cero de datos.[4][7][8] Según la Política de Privacidad, Anysphere, Inc. cubre las cuentas individuales, mientras que las cuentas comerciales aprovisionadas por empleadores en las que Anysphere actúa como encargado del tratamiento se rigen por los acuerdos con clientes.[9] Anysphere declara que las entradas y sugerencias no se utilizan para entrenar modelos salvo que se marquen para revisión de seguridad, se envíen explícitamente como comentarios o sean aprobadas expresamente por el usuario, y afirma que no recopila deliberadamente datos genéticos, biométricos, de salud o religiosos ni dirige sus servicios a menores de 18 años.[9] Los usuarios pueden eliminar sus cuentas directamente desde el panel de Configuración.[8]

Para despliegues organizativos, Cursor documenta SSO mediante SAML/OIDC, aprovisionamiento SCIM, registros de cumplimiento y auditoría, cuentas de servicio, despliegue mediante gestión de dispositivos móviles (MDM), cifrado de datos y claves de cifrado gestionadas por el cliente (CMEK), controles de ejecución automática, navegador y red, y controles de acceso para repositorios, modelos, servidores MCP y Grok Bot.[4][8]

## Historia corporativa, financiación y acuerdo de adquisición de Cursor por SpaceX

Cursor fue creado por Anysphere, Inc., fundada en 2022 y participante en la aceleradora de startups de [OpenAI](https://mimirwiki.com/es/wiki/openai) en 2024.[1][9] A finales de 2024, Anysphere recaudó 100 millones de dólares con una valoración previa a la inversión de 2500 millones de dólares.[2] A principios de 2025, OpenAI y otros posibles compradores se acercaron a Anysphere para plantear una adquisición, y la empresa rechazó esas ofertas.[2]

Los ingresos recurrentes anualizados (ARR) de Anysphere fueron cifrados por TechCrunch en 300 millones de dólares a mediados de abril de 2025 y superaron los 500 millones de dólares el 5 de junio de 2025, según fuentes citadas por Bloomberg y TechCrunch.[2] El 5 de junio de 2025, TechCrunch informó que Anysphere cerró una ronda Serie C de 900 millones de dólares (su tercera ronda de financiación en un año) con una valoración de 9900 millones de dólares, liderada por el inversor existente Thrive Capital con la participación de Andreessen Horowitz, Accel y DST Global.[1][2] En aquel momento, Cursor ofrecía una prueba gratuita de dos semanas que pasaba a suscripciones mensuales Pro de $20 o empresariales de $40, junto con licencias enterprise recién introducidas.[2] A finales de 2025, Anysphere recaudó 2300 millones de dólares adicionales y TechCrunch situó su valoración en torno a los 29 000 millones de dólares antes de anunciarse el acuerdo con SpaceX.[1]

A principios de 2026, xAI contrató a dos directivos sénior de ingeniería de Cursor, y en abril de 2026 Business Insider informó que xAI había acordado alquilar capacidad de centros de datos a Cursor.[1] Antes de la oferta de adquisición de SpaceX, Cursor se aproximaba a cerrar una ronda de financiación de 2000 millones de dólares con una valoración de 50 000 millones de dólares procedente de inversores como Andreessen Horowitz, Thrive Capital y Nvidia.[1] En abril de 2026, antes de la oferta pública inicial de SpaceX, SpaceX anunció un acuerdo según el cual adquiriría Cursor por 60 000 millones de dólares en acciones o pagaría una indemnización por ruptura de 10 000 millones de dólares si la operación no seguía adelante.[1]

El 16 de junio de 2026, días después de la salida a bolsa de SpaceX a $135 por acción y tras la fusión previa de SpaceX con xAI a comienzos de 2026, TechCrunch informó que SpaceX había acordado adquirir Cursor por 60 000 millones de dólares en acciones, indicando SpaceX que el cierre estaba previsto para el tercer trimestre de 2026.[1] Al 23 de noviembre de 2026, el sitio web público y la documentación de Cursor presentan la plataforma integrada en The X Subscription, vendida por X Subscription Corp. junto con [Grok](https://mimirwiki.com/es/wiki/grok) y X, enlazando a los Términos de Suscripción de SpaceXSI e incluyendo a SpaceXSI entre los proveedores de modelos compatibles, al tiempo que mantienen `Anysphere, Inc.` en el aviso de derechos de autor del sitio web y en la Política de Privacidad.[4][5][8][9]

## Preguntas frecuentes

### ¿Cuánto cuesta Cursor?

Al 23 de noviembre de 2026, Cursor se comercializa a través de The X Subscription con cinco niveles individuales: Free ($0/mes), Plus ($8/mes o $80/año), Premium ($30/mes o $300/año), Super ($100/mes o $1,000/año) y Ultra ($200/mes o $2,000/año), sin impuestos. Los puestos de Teams cuestan $30, $100 o $200 por puesto al mes, y los planes Enterprise tienen precios personalizados. Los modelos de terceros en los planes Premium y superiores se facturan por separado al precio de lista de la API mediante crédito prepagado. [4][5]

### ¿Qué ocurrió con los planes heredados de Cursor como Pro y Pro+?

Los planes heredados de Cursor, incluidos Hobby (gratuito), Start en India (₹649/mes con impuestos incluidos), Pro ($20/mes), Pro+ ($60/mes), Ultra ($200/mes), Teams Standard ($40/usuario/mes) y Teams Premium ($120/usuario/mes), están cerrados a nuevos clientes. Los suscriptores existentes conservan sus planes heredados, sus dos cuotas mensuales de uso y la facturación bajo demanda, a menos que cancelen o elijan un cambio permanente a The X Subscription. [5][6]

### ¿Qué modelos de IA admite Cursor?

Al 23 de noviembre de 2026, los planes de pago incluyen una cuota semanal compartida para los modelos propios de Cursor: Grok 4.7, Grok 4.6, Grok 4.5 y Composer 2.5. En los planes Premium y superiores, Cursor también admite modelos de terceros como Claude (Anthropic), GPT-5.6 (OpenAI), Gemini (Google) y Muse Wonder, facturados al precio de lista de la API mediante crédito prepagado. [3][5]

### ¿Cómo funcionan Privacy Mode y las certificaciones de seguridad de Cursor?

Al 23 de noviembre de 2026, Cursor cuenta con las certificaciones AIUC-1, ISO/IEC 27001:2022 e ISO/IEC 42001:2023 y una atestación SOC 2 Type II, con documentación de respaldo disponible bajo solicitud en trust.cursor.com. Privacy Mode está disponible para cualquier usuario, incluidos los del plan gratuito, puede ser aplicado de forma obligatoria para todo un equipo por los administradores, impide el entrenamiento de modelos con datos de código del usuario y ejecuta Voice Chat con retención cero de datos. [7][8][9]

### ¿Qué funciones de personalización y automatización incluye Cursor?

La documentación de Cursor enumera seis mecanismos de personalización: Plugins, Rules, Skills, Subagents, Hooks y servidores de Model Context Protocol (MCP). Cursor también incluye una interfaz de línea de comandos (CLI), Cloud Agents, Automations, alojamiento de código Origin, revisiones de código con Bugbot, Live Apps, Voice Chat y el Agent SDK para crear y desplegar agentes definidos como código. [3][4][7]

### ¿Quién es el propietario de Cursor?

Cursor fue desarrollado por Anysphere, Inc., fundada en 2022. El 16 de junio de 2026, TechCrunch informó que SpaceX acordó adquirir Cursor en una operación en acciones de 60 000 millones de dólares cuyo cierre estaba previsto para el tercer trimestre de 2026. Al 23 de noviembre de 2026, las suscripciones de Cursor se comercializan a través de X Subscription Corp. como parte de The X Subscription, mientras que Anysphere, Inc. sigue figurando en la Política de Privacidad y en los avisos de derechos de autor del sitio web de Cursor. [1][4][9]

## Frases citables

- Cursor fue desarrollado por Anysphere, empresa fundada en 2022 que participó en la aceleradora de startups de OpenAI en 2024. [1]
- El 5 de junio de 2025, TechCrunch informó que Anysphere recaudó 900 millones de dólares con una valoración de 9900 millones de dólares y superó los 500 millones de dólares en ingresos recurrentes anualizados. [2]
- El 16 de junio de 2026, TechCrunch informó que SpaceX acordó adquirir Cursor en una operación en acciones valorada en 60 000 millones de dólares cuyo cierre estaba previsto para el tercer trimestre de 2026. [1]
- Al 23 de noviembre de 2026, Cursor se comercializa directamente a través de X Subscription Corp. como parte de The X Subscription con niveles mensuales individuales de $0 (Free), $8 (Plus), $30 (Premium), $100 (Super) y $200 (Ultra), sin impuestos. [4][5]
- Al 23 de noviembre de 2026, los planes Teams y Enterprise de Cursor añaden una tarifa Cursor Token Rate de $0.25 por millón de tokens en solicitudes elegibles a modelos de terceros y uso con clave API propia (BYOK), mientras que los planes individuales no pagan esta tarifa. [5]
- Los planes heredados de Cursor, incluidos Pro a $20 al mes y Pro+ a $60 al mes, siguen activos para los suscriptores existentes con dos cuotas mensuales de uso, salvo que cancelen o cambien de forma permanente a The X Subscription. [5][6]
- Al 23 de noviembre de 2026, Cursor cuenta con las certificaciones AIUC-1, ISO/IEC 27001:2022 e ISO/IEC 42001:2023 y una atestación SOC 2 Type II, y declara que no mantiene infraestructura en China. [8]
- Entre octubre y noviembre de 2026, Cursor lanzó el Origin App Marketplace el 13 de octubre, publicó el Agent SDK el 20 de octubre, presentó Live Apps el 5 de noviembre y lanzó Voice Chat impulsado por Grok Voice el 6 de noviembre. [7]

## Cronología

- 2022: Se funda Anysphere, la empresa desarrolladora de Cursor. [1]
- 2024: Anysphere participa en la aceleradora de startups de OpenAI y recauda 100 millones de dólares con una valoración previa a la inversión de 2500 millones de dólares a finales de 2024. [1][2]
- 2025-04: TechCrunch informa que Anysphere alcanza los 300 millones de dólares en ingresos recurrentes anualizados. [2]
- 2025-06-05: TechCrunch informa que Anysphere cierra una ronda Serie C de 900 millones de dólares con una valoración de 9900 millones de dólares liderada por Thrive Capital, con ingresos recurrentes anualizados superiores a 500 millones de dólares. [1][2]
- 2026-04: SpaceX anuncia un acuerdo con Cursor para adquirir la empresa por 60 000 millones de dólares en acciones o pagar una indemnización por ruptura de 10 000 millones de dólares, junto con informes de que xAI alquiló capacidad de centros de datos a Cursor. [1]
- 2026-06-16: TechCrunch informa que SpaceX acuerda adquirir Cursor por 60 000 millones de dólares en acciones, con cierre previsto para el tercer trimestre de 2026. [1]
- 2026-08-25: Cursor actualiza su documentación de seguridad incluyendo las certificaciones AIUC-1, ISO/IEC 27001:2022, ISO/IEC 42001:2023 y la atestación SOC 2 Type II. [8]
- 2026-10-13: Cursor lanza el Origin App Marketplace con más de 20 integraciones de socios y lo abre a envíos públicos. [7]
- 2026-10-16: Cursor añade Canvases interactivos compartibles para agentes en la nube, la beta de la Environments API y soporte para hasta 300 repositorios por entorno en la nube. [7]
- 2026-10-20: Cursor publica el Agent SDK con disponibilidad general. [7]
- 2026-11-05: Cursor lanza el despliegue de Live Apps desde agentes en la nube en los planes de pago. [7]
- 2026-11-06: Cursor lanza Voice Chat con agentes de programación impulsado por Grok Voice y actualiza su Política de Privacidad. [7][9]

## Fuentes

1. SpaceX to acquire Cursor for $60B in stock, days after blockbuster IPO | TechCrunch. TechCrunch. publicado 2026-06-16. https://techcrunch.com/2026/06/16/spacex-to-acquire-cursor-for-60b-in-stock-days-after-blockbuster-ipo/ (consultado 2026-11-23; tier 2: academic or news)
2. Cursor's Anysphere nabs $9.9B valuation, soars past $500M ARR | TechCrunch. TechCrunch. publicado 2025-06-05. https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/ (consultado 2026-11-23; tier 2: academic or news)
3. Cursor Docs - Agent, Rules, MCP, Skills & CLI. Cursor. https://cursor.com/docs (consultado 2026-11-23; tier 3: official site)
4. Cursor · Pricing. Cursor. https://cursor.com/pricing (consultado 2026-11-23; tier 3: official site)
5. Models & Pricing | Cursor Docs. Cursor. https://cursor.com/docs/models-and-pricing (consultado 2026-11-23; tier 3: official site)
6. Pricing and plans | Cursor Docs. Cursor. https://cursor.com/help/account-and-billing/pricing (consultado 2026-11-23; tier 3: official site)
7. What's New in Cursor - Latest Updates & Release Notes. Cursor. https://cursor.com/changelog (consultado 2026-11-23; tier 3: official site)
8. Cursor · Security. Cursor. https://cursor.com/security (consultado 2026-11-23; tier 3: official site)
9. Cursor · Privacy Policy. Cursor. https://cursor.com/privacy (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Cursor." Versión 3fc93a68, 2026-11-25. https://mimirwiki.com/es/wiki/cursor
