---
title: "Microsoft Copilot"
subtitle: "Asistente de inteligencia artificial generativa para consumidores y empresas de Microsoft integrado en Windows, Microsoft 365 y Azure"
canonical_url: https://mimirwiki.com/es/wiki/microsoft-copilot
language: es
page_class: entity
revision_sha256: ad62ae04ae9a6a20fb23d32d5fb1bd33f3a7c2eb4b0109b0dfafb177df0440c7
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/es/wiki/microsoft-copilot.md
  txt: https://mimirwiki.com/es/wiki/microsoft-copilot.txt
  json: https://mimirwiki.com/es/wiki/microsoft-copilot.json
  jsonld: https://mimirwiki.com/es/wiki/microsoft-copilot.jsonld
translations:
  en: https://mimirwiki.com/wiki/microsoft-copilot
  ko: https://mimirwiki.com/ko/wiki/microsoft-copilot
  ja: https://mimirwiki.com/ja/wiki/microsoft-copilot
  zh: https://mimirwiki.com/zh/wiki/microsoft-copilot
---

# Microsoft Copilot

> A noviembre de 2026, Microsoft Copilot comprende el servicio gratuito Copilot Chat fundamentado en la web en copilot.cloud.microsoft, licencias de pago por puesto de Microsoft 365 Copilot (complemento empresarial de $30 por usuario al mes; $18-$32 por usuario al mes en paquetes Microsoft Copilot Business para pymes), el plan empresarial avanzado Microsoft 365 E7 y agentes de Copilot Studio y Cowork facturados según uso. A finales de 2026, Microsoft amplió su catálogo de modelos más allá de OpenAI para integrar los modelos Claude de Anthropic como subprocesador aprobado.

Microsoft Copilot es la familia insignia de asistentes de inteligencia artificial generativa y plataformas de agentes de Microsoft Corporation, que abarca interfaces web y móviles para consumidores, Windows 11, las suites de productividad de Microsoft 365 y Copilot Studio. Fundamentado en modelos fundacionales de frontera de OpenAI y Anthropic junto con datos organizacionales de Microsoft Graph (Work IQ), ofrece búsqueda conversacional, síntesis de documentos y código, y flujos de trabajo empresariales autónomos de múltiples pasos.

**También conocido como:** Microsoft 365 Copilot, Copilot Chat, Copilot Studio, Bing Chat

## Datos clave

- **Desarrollador:** Microsoft Corporation (SEC CIK 0000789019) [1]
- **Precio del complemento empresarial:** $30 por usuario al mes (compromiso anual) (al 2026-11-23) [2]
- **Precios para pymes (Business):** $18/usuario/mes como complemento; $23.50-$32/usuario/mes en paquete con Microsoft 365 Business (al 2026-11-23) [2]
- **Límite por turno de agente:** Duración máxima de turno de 90 minutos; 200 llamadas a herramientas por turno en Copilot Studio (al 2026-11-23) [7]

## Datos básicos

- **Desarrollador:** Microsoft Corporation [1]
- **Punto de acceso web principal:** copilot.microsoft.com (consumidores) / copilot.cloud.microsoft (trabajo y educación) [4]
- **Arquitectura de fundamentación:** Microsoft Graph / Work IQ e índice web de Bing [4]
- **Proveedores de modelos fundacionales:** OpenAI (Azure OpenAI Service) y Anthropic (subprocesador de Claude) [5]
- **Licenciamiento empresarial:** Complemento Microsoft 365 Copilot, Microsoft 365 E7, Microsoft Copilot Business [3]
- **Plataforma de agentes:** Microsoft Copilot Studio (pago por uso o facturación por paquetes de mensajes) [7]
- **Protección de datos empresariales:** Las indicaciones y respuestas comerciales quedan excluidas del entrenamiento de modelos fundacionales [6]
- **Contexto de ingresos de la matriz en el año fiscal 2026:** $331,839 millones ($331.84 mil millones) en ingresos totales de Microsoft según el Formulario 10-K del año fiscal 2026 (finalizado el 30 de junio de 2026) [1]

## Descripción general y arquitectura del producto

Microsoft Copilot es la marca unificada y el marco de orquestación técnica para los asistentes de inteligencia artificial generativa de Microsoft Corporation en entornos de consumo, comerciales y de desarrollo.[1][4] Introducida originalmente en 2023 como Bing Chat y Microsoft 365 Copilot antes de consolidarse bajo el nombre Microsoft Copilot, la plataforma combina modelos de lenguaje de gran tamaño (LLM) con índices de búsqueda web, telemetría del sistema operativo y grafos organizacionales empresariales.[1][4]

En el núcleo arquitectónico de la oferta comercial se encuentra **Work IQ** (anteriormente denominado fundamentación mediante Microsoft Graph), que conecta los modelos fundacionales con los correos electrónicos de un inquilino, los chats de Microsoft Teams, los sitios de SharePoint, los documentos de OneDrive y los metadatos del calendario, al tiempo que aplica los controles de acceso basados en roles (RBAC) existentes y las etiquetas de confidencialidad de Microsoft Purview.[4][6] Cuando un usuario empresarial autenticado envía una indicación en `copilot.cloud.microsoft` o dentro de una aplicación de Office, el orquestador de Copilot realiza el preprocesamiento y la recuperación semántica dentro del alcance permitido de Microsoft Graph para ese usuario, enriquece la indicación con citas recuperadas, dirige la carga útil al LLM seleccionado y ejecuta comprobaciones posteriores de cumplimiento, fundamentación e inteligencia artificial responsable antes de transmitir la respuesta.[4][6]

## Niveles de producto, Microsoft 365 E7 y precios

Microsoft estructura Copilot en acceso gratuito para consumidores, chat comercial básico, complementos completos de productividad por puesto y consumo de agentes basado en uso:[2][3][4]

| Nivel / Plan | Público objetivo | Capacidades clave | Precios (a nov. de 2026) |
| --- | --- | --- | --- |
| **Microsoft Copilot (Consumidores)** | Consumidores individuales | Chat fundamentado en la web, generación de imágenes, voz, aplicaciones para Windows y móviles | Gratuito (con nivel de pago Copilot Pro) [4] |
| **Microsoft Copilot Chat** | Usuarios comerciales y educativos con Entra ID | Chat fundamentado en la web con Protección de datos empresariales (EDP), Copilot Pages y agentes de pago por uso | Incluido en licencias elegibles de M365; agentes facturados por uso [4] |
| **Microsoft Copilot Business** | Pymes (hasta 300 usuarios) | Copilot fundamentado en datos laborales en Word, Excel, PowerPoint, Outlook y Teams | Complemento de $18/usuario/mes; $23.50-$32/usuario/mes en paquete con M365 Business [2] |
| **Microsoft 365 Copilot (Empresas)** | Inquilinos empresariales (requisitos previos E3/E5) | Fundamentación completa con Work IQ, funciones integradas en aplicaciones y consumo de agentes de Copilot Studio incluido | $30/usuario/mes (compromiso anual) [2][3] |
| **Microsoft 365 E7** | Despliegues empresariales de frontera | Suite empresarial integral que agrupa M365 E5, Microsoft 365 Copilot y capacidades agénticas avanzadas | Precios bajo acuerdo empresarial [3] |

Además del licenciamiento por puesto, Microsoft introdujo modelos de consumo medido para flujos de trabajo autónomos especializados, incluidos **Copilot Cowork**, **Copilot Code** y **Copilot Autopilot**, que pueden facturarse bajo una modalidad de pago por uso mediante una suscripción vinculada de Azure o a través de paquetes prepagados de capacidad de Copilot Credit.[3][5]

## Orquestación multimodelo e integración con Anthropic

Aunque las primeras versiones de Microsoft Copilot dependían exclusivamente de los modelos de OpenAI alojados en Azure OpenAI Service, Microsoft amplió Copilot hasta convertirlo en una plataforma de orquestación multimodelo durante 2025 y 2026.[4][5] Según la documentación comercial del servicio y Microsoft Learn, Microsoft integra sus propios modelos internos junto con modelos de frontera tanto de OpenAI como de Anthropic.[4][5]

En concreto, Microsoft incorporó a **Anthropic** como subprocesador oficial de Microsoft Online Services, lo que permite a los administradores empresariales y a los desarrolladores de Copilot Studio habilitar los modelos Claude de Anthropic para tareas de razonamiento profundo, programación e investigación en varios pasos dentro de Microsoft 365 Copilot, Copilot Cowork y Copilot Studio.[5] Cuando se invocan los modelos de Anthropic, los datos de los clientes siguen regidos por los términos comerciales de Microsoft y los compromisos de Protección de datos empresariales, aunque las solicitudes pueden procesarse en la infraestructura gestionada por Anthropic en virtud de acuerdos de protección de datos de subprocesadores según la disponibilidad regional.[5][6]

## Copilot Studio y cuotas de tiempo de ejecución de agentes

Microsoft Copilot Studio funciona como el entorno de creación de bajo código y código profesional para desarrollar agentes declarativos personalizados, flujos de trabajo autónomos y agentes capaces de operar computadoras que se publican directamente en Microsoft Copilot Chat y Microsoft Teams.[4][7] Para evitar ejecuciones descontroladas y gestionar la orquestación multiagente, Microsoft aplica cuotas estrictas de tiempo de ejecución y límites operativos a los agentes de Copilot Studio:[7]

- **Duración máxima de turno**: Un turno individual de orquestación de agente puede ejecutarse hasta **90 minutos** (5,400 segundos) antes de agotarse el tiempo de espera.[7]
- **Llamadas a herramientas por turno**: Un solo turno admite hasta **200 llamadas a herramientas** entre conectores, acciones y complementos.[7]
- **Tiempo de espera individual de herramientas y conectores**: Las ejecuciones sincrónicas estándar de herramientas o conectores agotan el tiempo de espera tras **120 segundos**.[7]
- **Tiempo de espera de flujos de agente / flujos de trabajo**: Las ejecuciones sincrónicas integradas de flujos de Power Automate o flujos de trabajo de agentes tienen un límite de **660 segundos** (11 minutos).[7]
- **Agentes conectados y externos**: Las llamadas delegadas a agentes internos conectados de Copilot Studio pueden ejecutarse hasta **5,400 segundos** (90 minutos), mientras que las invocaciones a agentes externos A2A/MCP agotan el tiempo de espera tras **300 segundos** (5 minutos).[7]
- **Contexto de conversación y transmisión en vivo**: La orquestación mantiene una ventana deslizante de contexto de **100 mensajes** por conversación, y las respuestas transmitidas en vivo en Microsoft Teams tienen un límite de **2 minutos** por segmento de transmisión.[7]

## Protección de datos empresariales y gobernanza

Para las organizaciones comerciales, gubernamentales y educativas que inician sesión con una cuenta de Microsoft Entra ID, Microsoft aplica la **Protección de datos empresariales (EDP)** conforme a los Términos de productos de Microsoft y el Anexo de protección de datos (DPA).[6] Bajo EDP, las indicaciones de los usuarios, los archivos cargados, los datos de fundamentación de Microsoft Graph y las respuestas generadas se aíslan lógicamente por inquilino, se cifran en tránsito y en reposo, y **nunca se utilizan para entrenar modelos de lenguaje de gran tamaño públicos ni fundacionales**.[6]

Copilot hereda estrictamente las políticas de gobernanza existentes de Microsoft Purview: si un documento está cifrado con Rights Management Services (RMS) o cuenta con una etiqueta de confidencialidad que restringe la extracción, Copilot bloquea el resumen o propaga directamente la etiqueta restrictiva y la marca de agua al resultado generado.[6] Los administradores pueden auditar todas las interacciones con indicaciones, invocaciones de herramientas de agentes y citas mediante Microsoft Purview Audit, Communication Compliance y eDiscovery.[6]

## Preguntas frecuentes

### ¿Cuál es la diferencia entre Microsoft Copilot Chat y Microsoft 365 Copilot?

Microsoft Copilot Chat es el asistente básico fundamentado en la web incluido sin costo adicional por puesto para cuentas laborales y educativas elegibles de Microsoft Entra ID en copilot.cloud.microsoft, con Protección de datos empresariales y acceso a agentes bajo pago por uso. Microsoft 365 Copilot ($30 por usuario al mes para empresas) añade la fundamentación de Work IQ (Microsoft Graph) en los correos electrónicos, chats y archivos del usuario, además de la integración directa dentro de Word, Excel, PowerPoint, Outlook y Teams. [2][4]

### ¿Cuánto cuesta Microsoft Copilot Business para pequeñas y medianas empresas?

Para pequeñas y medianas empresas (hasta 300 puestos), Microsoft Copilot Business está disponible como complemento independiente a $18 por usuario al mes, o incluido en paquete con los planes Microsoft 365 Business Basic, Standard o Premium a tarifas promocionales que van de $23.50 a $32 por usuario al mes con compromiso anual. [2]

### ¿Microsoft Copilot utiliza los modelos Claude de Anthropic además de OpenAI?

Sí. Microsoft opera Copilot sobre una arquitectura multimodelo y ha designado a Anthropic como subprocesador oficial de Online Services, lo que permite a los inquilinos empresariales utilizar los modelos Claude de Anthropic dentro de Microsoft 365 Copilot, Copilot Studio y Copilot Cowork junto con los modelos de OpenAI y Microsoft. [4][5]

### ¿Cuáles son los límites de ejecución y de llamadas a herramientas para los agentes en Microsoft Copilot Studio?

A finales de 2026, un turno de agente de Copilot Studio puede ejecutarse hasta 90 minutos (5,400 segundos) y realizar hasta 200 llamadas a herramientas por turno. Las llamadas sincrónicas individuales a herramientas agotan el tiempo de espera a los 120 segundos, los flujos de agente a los 660 segundos y las llamadas a agentes externos a los 300 segundos. [7]

### ¿Utiliza Microsoft las indicaciones empresariales de Copilot para entrenar sus modelos fundacionales de IA?

No. En virtud de los compromisos de Protección de datos empresariales (EDP) de Microsoft para usuarios comerciales de Entra ID, las indicaciones, el contexto recuperado de Microsoft Graph y las respuestas generadas permanecen aislados dentro del límite del cliente y no se utilizan para entrenar modelos fundacionales. [6]

## Frases citables

- Microsoft 365 Copilot tiene un precio de $30 por usuario al mes para planes empresariales, mientras que Microsoft Copilot Business ofrece un complemento de $18 por usuario al mes y paquetes para pymes de $23.50-$32 por usuario al mes. [2][3]
- Microsoft incorporó a Anthropic como subprocesador de Online Services para proporcionar modelos Claude en Microsoft 365 Copilot, Copilot Studio y Copilot Cowork. [5]
- Microsoft Copilot Studio aplica una duración máxima de turno de 90 minutos (5,400 segundos) y hasta 200 llamadas a herramientas por turno. [7]
- Las llamadas individuales a herramientas en Copilot Studio agotan el tiempo de espera tras 120 segundos, los flujos de trabajo de agentes tras 660 segundos y las invocaciones a agentes externos tras 300 segundos. [7]
- Bajo la Protección de datos empresariales (EDP), las indicaciones y respuestas de los usuarios comerciales de Entra ID no se utilizan para entrenar modelos fundacionales. [6]

## Cronología

- 2023-02: Microsoft lanza el asistente inicial de búsqueda con inteligencia artificial generativa bajo el nombre Bing Chat. [1]
- 2023-11: Microsoft 365 Copilot pasa a estar disponible de forma general para clientes empresariales y Bing Chat cambia de marca a Microsoft Copilot. [1]
- 2026-06-30: Microsoft cierra el año fiscal 2026 con $331.84 mil millones en ingresos anuales e informa en su Formulario 10-K sobre la expansión de Copilot en Microsoft 365, Windows, GitHub y la infraestructura de IA de Azure. [1]
- 2026-11: Microsoft detalla Microsoft 365 E7, los precios de Microsoft Copilot Business para pymes ($18-$32/usuario/mes), la integración de Claude de Anthropic como subprocesador y los límites ampliados de tiempo de ejecución en Copilot Studio de 90 minutos y 200 llamadas a herramientas. [2][3][5][7]

## Fuentes

1. Microsoft Corporation Form 10-K for the Fiscal Year Ended June 30, 2026. U.S. Securities and Exchange Commission (SEC). publicado 2026-07-29. https://www.sec.gov/Archives/edgar/data/789019/000119312526323660/msft-20260630.htm (consultado 2026-11-23; tier 1: government or public registry)
2. Microsoft Copilot Plans and Pricing - AI for Business | Microsoft 365. Microsoft Corporation. https://www.microsoft.com/en-us/copilot/pricing/business (consultado 2026-11-23; tier 3: official site)
3. License Options for Microsoft Copilot | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-license-options (consultado 2026-11-23; tier 3: official site)
4. What is Microsoft Copilot? | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/copilot-overview (consultado 2026-11-23; tier 3: official site)
5. Claude models from Anthropic in Microsoft Online Services | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/implement/connect-to-ai-subprocessor (consultado 2026-11-23; tier 3: official site)
6. Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/copilot/plan/enterprise-data-protection (consultado 2026-11-23; tier 3: official site)
7. Agent runtime limits - Microsoft Copilot Studio | Microsoft Learn. Microsoft Learn. https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/runtime-limits (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Microsoft Copilot." Versión ad62ae04, 2026-11-23. https://mimirwiki.com/es/wiki/microsoft-copilot
