---
title: "DeepSeek"
subtitle: "Laboratorio chino de investigación en inteligencia artificial que desarrolla los modelos fundacionales DeepSeek-V4, DeepSeek-R1 y DeepSeek-V3"
canonical_url: https://mimirwiki.com/es/wiki/deepseek
language: es
page_class: entity
revision_sha256: 8bb2ba5296adcc93306c2f7140d3bfbc09a515c78004a384d9cc04d3f33cd881
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 7
alternates:
  md: https://mimirwiki.com/es/wiki/deepseek.md
  txt: https://mimirwiki.com/es/wiki/deepseek.txt
  json: https://mimirwiki.com/es/wiki/deepseek.json
  jsonld: https://mimirwiki.com/es/wiki/deepseek.jsonld
translations:
  en: https://mimirwiki.com/wiki/deepseek
  ko: https://mimirwiki.com/ko/wiki/deepseek
  ja: https://mimirwiki.com/ja/wiki/deepseek
  zh: https://mimirwiki.com/zh/wiki/deepseek
---

# DeepSeek

> A noviembre de 2026, la API de DeepSeek enumera dos modelos con una longitud de contexto de 1M y una salida máxima de 384K: deepseek-flash (DeepSeek-V4.1-Flash-1017) y deepseek-v4-pro (DeepSeek-V4-Pro-0813). Las tarifas en horas valle equivalen a la mitad de las tarifas en horas pico, y las API de Search, Fetch, OCR y voz se ofrecen por separado. Desde las 12:00 hora de Pekín del 18 de noviembre de 2026, las llamadas de herramientas del lado del servidor para búsqueda y recuperación web realizadas al invocar un modelo dejaron de facturarse. Entre los modelos anteriores figuran DeepSeek-V3 (671B de parámetros totales / 37B activados) y el modelo de razonamiento DeepSeek-R1.

DeepSeek es una empresa china de inteligencia artificial cuyos servicios son proporcionados por Hangzhou DeepSeek Artificial Intelligence Co., Ltd., una compañía con domicilio registrado en China. Desarrolla modelos de lenguaje de gran tamaño basados en las arquitecturas Multi-head Latent Attention (MLA) y DeepSeekMoE, entre ellos DeepSeek-V2, DeepSeek-V3, el modelo de razonamiento por aprendizaje por refuerzo DeepSeek-R1 y la serie DeepSeek-V4 ofrecida a través de su API.

**También conocido como:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd., 深度求索

## Datos clave

- **Entidades legales:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Modelos actuales en producción:** deepseek-flash (DeepSeek-V4.1-Flash-1017) y deepseek-v4-pro (DeepSeek-V4-Pro-0813) (al 2026-11-25) [1]
- **Contexto y salida máxima:** Ventana de contexto de 1M de tokens; hasta 384K tokens de salida máxima (al 2026-11-25) [1]
- **Hito de razonamiento de pesos abiertos:** DeepSeek-R1 (Licencia MIT, enero de 2025) y DeepSeek-V3 (MoE 671B/37B, diciembre de 2024) [4]

## Datos básicos

- **Nombre oficial:** Hangzhou DeepSeek Artificial Intelligence Co., Ltd. [7]
- **Domicilio registrado:** China [7]
- **Arquitecturas principales:** Multi-head Latent Attention (MLA), DeepSeekMoE, Multi-Token Prediction (MTP) [5]
- **Modelos principales de la API (nov. 2026):** DeepSeek-V4.1-Flash-1017 (deepseek-flash), DeepSeek-V4-Pro-0813 (deepseek-v4-pro) [1]
- **Contexto y salida de la API:** Longitud de contexto de 1M / salida máxima de 384K [1]
- **Límites de concurrencia de la API:** 2,500 solicitudes simultáneas (deepseek-flash); 500 solicitudes simultáneas (deepseek-v4-pro) [2]
- **API multimodales y de herramientas:** Search API, Fetch API, API de análisis de archivos y OCR, reconocimiento de voz a texto (ASR), síntesis de texto a voz (TTS) [1]
- **Licencia de código abierto (R1):** Licencia MIT (pesos y código para DeepSeek-R1 y modelos destilados) [4]

## Descripción general de DeepSeek y fundamentos arquitectónicos

Los servicios de DeepSeek son proporcionados por Hangzhou DeepSeek Artificial Intelligence Co., Ltd.[7] La empresa ha publicado informes técnicos sobre las arquitecturas de sus modelos y ha lanzado modelos de mezcla de expertos (Mixture-of-Experts, MoE) y de razonamiento.[4][5][6]

Los modelos de DeepSeek utilizan dos arquitecturas introducidas en **DeepSeek-V2** (mayo de 2024, 236B de parámetros totales con 21B activados por token) y adoptadas en **DeepSeek-V3** (diciembre de 2024, 671B de parámetros totales con 37B activados por token):[5][6] - **Multi-head Latent Attention (MLA)**: comprime la caché de clave-valor (KV) en un vector latente para lograr una inferencia eficiente.[5][6] - **DeepSeekMoE**: emplea cómputo disperso con expertos enrutados y compartidos. DeepSeek-V3 incorpora una estrategia sin pérdida auxiliar para el balanceo de carga y un objetivo de entrenamiento de predicción multitoken (Multi-Token Prediction, MTP).[5][6] DeepSeek-V3 fue preentrenado con 14.8 billones de tokens mediante entrenamiento de precisión mixta FP8, y su informe técnico señala que el entrenamiento completo requirió 2.788M de horas de GPU H800.[5]

## DeepSeek-R1 y aprendizaje por refuerzo para el razonamiento

El artículo de DeepSeek-R1, enviado a arXiv el 22 de enero de 2025, describe a **DeepSeek-R1** y **DeepSeek-R1-Zero**, e informa que las capacidades de razonamiento de los modelos de lenguaje de gran tamaño pueden incentivarse mediante aprendizaje por refuerzo (RL) puro, sin trayectorias de razonamiento etiquetadas por humanos, y que durante el entrenamiento emergieron comportamientos como la autorreflexión y la verificación.[4]

`DeepSeek-R1-Zero` se entrenó con Group Relative Policy Optimization (GRPO) sin una fase de ajuste fino supervisado previa al RL. Dado que presentó baja legibilidad y mezcla de idiomas, `DeepSeek-R1` utilizó una canalización multietapa con datos de cadena de pensamiento en arranque en frío, muestreo por rechazo, RL y ajuste fino supervisado.[4] El artículo reporta un rendimiento a la par con OpenAI-o1-1217 en tareas matemáticas, y señala que OpenAI-o1-1217 supera a DeepSeek-R1 en tareas de programación orientadas a la ingeniería.[4] DeepSeek también puso a disposición pública seis modelos destilados, de 1.5B a 70B de parámetros, basados en los modelos Qwen y Llama.[4]

## Serie DeepSeek-V4, precios y plataforma para desarrolladores (2026)

La API de DeepSeek (`api.deepseek.com`) incorporó DeepSeek-V4-Pro y DeepSeek-V4-Flash el 24 de abril de 2026.[3] A noviembre de 2026, la página de precios enumera dos modelos, cada uno con una **longitud de contexto de 1M** y una **salida máxima de 384K**:[1]

| Nombre del modelo | Versión del modelo | Entrada, acierto de caché (pico / valle) | Entrada, fallo de caché (pico / valle) | Salida (pico / valle) | Límite de concurrencia |
| --- | --- | --- | --- | --- | --- |
| `deepseek-flash` | `DeepSeek-V4.1-Flash-1017` | $0.006 / $0.003 | $0.30 / $0.15 | $1.20 / $0.60 | 2,500 |
| `deepseek-v4-pro` | `DeepSeek-V4-Pro-0813` | $0.044 / $0.022 | $1.32 / $0.66 | $3.96 / $1.98 | 500 |

Los precios son por cada 1M de tokens.[1][2] Las tarifas en horas valle equivalen a la mitad de las tarifas en horas pico. Las horas pico son de 01:00 a 04:00 y de 06:00 a 10:00 UTC, de lunes a viernes, excluyendo los días festivos públicos chinos.[1] Ambos modelos admiten modos con razonamiento y sin razonamiento, salida en JSON, llamadas a herramientas, la Responses API y una API en formato Anthropic. La visión es compatible con `deepseek-flash` y no con `deepseek-v4-pro`.[1] Los nombres de modelos heredados `deepseek-v4-flash` y `deepseek-v4-flash-vision-exp` son atendidos por DeepSeek-V4.1-Flash-1017.[1]

Según el registro de cambios, el lanzamiento de disponibilidad general (GA) de DeepSeek-V4-Pro se desplegó el 13 de agosto de 2026, DeepSeek-V4.1-Flash se lanzó el 10 de septiembre de 2026 y se actualizó a DeepSeek-V4.1-Flash-1017 el 17 de octubre de 2026.[3]

## Búsqueda web integrada, API de utilidades y gobernanza de tasas de DeepSeek

El 13 de noviembre de 2026, DeepSeek habilitó para los desarrolladores funciones de búsqueda web, entrada de archivos, lectura de URL y seguridad del modelo para `deepseek-flash` en sus API de Messages, Responses y Chat Completions, y ofreció Search y Fetch, OCR, ASR y TTS como API independientes.[3] La página de precios indica las siguientes tarifas:[1] - **Search API (texto)**: $0.75 por cada 1,000 solicitudes exitosas.[1] - **Fetch API**: $0.75 por cada 1,000 solicitudes exitosas.[1] - **API de análisis de archivos y OCR**: $0.225 por cada 1,000 páginas.[1] - **Reconocimiento de voz a texto (ASR)**: precio de lista de $0.116 por hora de audio, precio por tiempo limitado de $0.058.[1] - **Síntesis de texto a voz (TTS)**: precio de lista de $0.45 por cada 10,000 caracteres, precio por tiempo limitado de $0.225.[1]

A partir de las 12:00 del 18 de noviembre de 2026 (hora de Pekín, UTC+8), las llamadas de herramientas del lado del servidor para búsqueda y recuperación web activadas al invocar un modelo dejaron de facturarse. Los resultados devueltos se añaden al contexto del modelo y se facturan como uso de tokens del modelo.[1]

Los límites de concurrencia se calculan a nivel de cuenta: 2,500 para `deepseek-flash` y 500 para `deepseek-v4-pro`. Las solicitudes que superen el límite reciben un código de error HTTP 429.[2] Los desarrolladores pueden pasar un parámetro `user_id`, que DeepSeek utiliza para el aislamiento de seguridad de contenido, el aislamiento de KVCache y el aislamiento de planificación. Para los usuarios habituales de la API, todos los valores de `user_id` se combinan para el límite de concurrencia. Para las cuentas con cuotas de concurrencia ampliadas, cada `user_id` también está limitado a 2,500 para `deepseek-flash` y 500 para `deepseek-v4-pro`.[2]

## Gobernanza de datos y política de privacidad de DeepSeek

Según la Política de privacidad de DeepSeek (actualizada por última vez el 10 de febrero de 2026), los servicios son proporcionados y controlados por Hangzhou DeepSeek Artificial Intelligence Co., Ltd., con domicilio registrado en China.[7] La política establece que DeepSeek recopila, procesa y almacena datos personales en la **República Popular China**.[7] Asimismo, contempla el derecho a oponerse al uso de datos personales para el entrenamiento de sus modelos o la optimización de sus tecnologías.[7] La política no cubre los datos personales recopilados de los usuarios finales de aplicaciones que los desarrolladores construyan sobre la plataforma abierta de DeepSeek; señala que el desarrollador que opera la aplicación es el responsable del tratamiento de dichos datos.[7] DeepSeek también ha puesto a disposición pública modelos destilados de DeepSeek-R1.[4]

## Preguntas frecuentes

### ¿Cuáles son los principales modelos de la API de DeepSeek a noviembre de 2026?

La API de DeepSeek enumera dos modelos: deepseek-flash (versión de modelo DeepSeek-V4.1-Flash-1017) y deepseek-v4-pro (versión de modelo DeepSeek-V4-Pro-0813). Ambos cuentan con una longitud de contexto de 1M y una salida máxima de 384K. [1][3]

### ¿Cómo funcionan las tarifas en horas pico y horas valle de la API de DeepSeek?

Las tarifas en horas valle equivalen a la mitad de las tarifas en horas pico. Las horas pico son de 01:00 a 04:00 y de 06:00 a 10:00 UTC, de lunes a viernes, excluyendo los días festivos públicos chinos; el resto de las horas corresponden a horario valle. Por ejemplo, la entrada con fallo de caché de deepseek-flash cuesta $0.30 por cada 1M de tokens en horas pico y $0.15 en horas valle, y la salida cuesta $1.20 en horas pico y $0.60 en horas valle. [1]

### ¿Cómo funcionan los límites de tasa de la API de DeepSeek y los controles de concurrencia por user_id?

Los límites de concurrencia se calculan a nivel de cuenta: 2,500 para deepseek-flash y 500 para deepseek-v4-pro. Las solicitudes que superen el límite reciben un código de error HTTP 429. Para los usuarios habituales de la API, todos los valores de user_id se combinan para el límite. Para las cuentas con cuotas de concurrencia ampliadas, cada user_id también está limitado a 2,500 para deepseek-flash y 500 para deepseek-v4-pro. [2]

### ¿Qué innovaciones arquitectónicas hicieron destacables a DeepSeek-V3 y DeepSeek-R1?

DeepSeek-V3 (671B de parámetros totales, 37B activos por token) combinó Multi-head Latent Attention (MLA) para una caché KV de bajo consumo de memoria con un enrutador DeepSeekMoE sin pérdida auxiliar y entrenamiento en FP8. Posteriormente, DeepSeek-R1 aplicó aprendizaje por refuerzo puro a gran escala (GRPO) y entrenamiento multietapa con arranque en frío para alcanzar un rendimiento de razonamiento de vanguardia bajo una Licencia MIT abierta. [4][5]

### ¿Dónde almacena DeepSeek los datos enviados a su aplicación web alojada y a su API?

La Política de privacidad de DeepSeek establece que recopila, procesa y almacena datos personales en la República Popular China, y que los servicios son proporcionados y controlados por Hangzhou DeepSeek Artificial Intelligence Co., Ltd. La política no cubre a los usuarios finales de aplicaciones que los desarrolladores construyan sobre la plataforma abierta de DeepSeek. [4][7]

## Frases citables

- Los endpoints de producción de la API de DeepSeek deepseek-flash (DeepSeek-V4.1-Flash-1017) y deepseek-v4-pro (DeepSeek-V4-Pro-0813) admiten ambos una ventana de contexto de 1M de tokens y hasta 384K tokens de salida. [1][3]
- Las tarifas en horas valle de la API de DeepSeek equivalen a la mitad de sus tarifas en horas pico; las horas pico son de 01:00 a 04:00 y de 06:00 a 10:00 UTC, de lunes a viernes, excluyendo los días festivos públicos chinos. [1]
- Los límites de concurrencia a nivel de cuenta en la API de DeepSeek son de 2,500 para deepseek-flash y 500 para deepseek-v4-pro; para cuentas con cuotas ampliadas, los mismos límites se aplican también a cada user_id. [2]
- Desde las 12:00 del 18 de noviembre de 2026 (hora de Pekín), las llamadas de herramientas del lado del servidor para búsqueda y recuperación web activadas al invocar un modelo de DeepSeek dejaron de facturarse; los resultados devueltos se facturan como uso de tokens del modelo. [1]
- DeepSeek-V3 es un modelo Mixture-of-Experts de 671B de parámetros con 37B de parámetros activos por token entrenado con 14.8 billones de tokens, y DeepSeek-R1 fue lanzado bajo la Licencia MIT en enero de 2025. [4][5]

## Cronología

- 2024-05: DeepSeek publica el informe técnico de DeepSeek-V2, introduciendo Multi-head Latent Attention (MLA) y una arquitectura MoE de 236B/21B. [6]
- 2024-12: DeepSeek lanza DeepSeek-V3, un modelo Mixture-of-Experts de 671B de parámetros (37B activos) preentrenado con 14.8 billones de tokens con precisión FP8. [5]
- 2025-01: DeepSeek lanza DeepSeek-R1, DeepSeek-R1-Zero y seis modelos de razonamiento destilados bajo la Licencia MIT de código abierto. [4]
- 2026-08-13: El lanzamiento de disponibilidad general (GA) de DeepSeek-V4-Pro se despliega en la aplicación, la web y la API bajo el nombre de modelo deepseek-v4-pro. [1][3]
- 2026-10-17: DeepSeek V4.1 Flash se actualiza a DeepSeek-V4.1-Flash-1017, ofrecido bajo el nombre de modelo deepseek-flash. [1][3]
- 2026-11-18: A partir de las 12:00 hora de Pekín, las llamadas de herramientas del lado del servidor para búsqueda y recuperación web activadas al invocar un modelo dejaron de facturarse. [1]

## Fuentes

1. DeepSeek API Models & Pricing (deepseek-flash, deepseek-v4-pro, Search, Fetch, OCR, Speech). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/pricing (consultado 2026-11-25; tier 3: official site)
2. DeepSeek API Rate Limits and Concurrency Controls (user_id Isolation). DeepSeek Platform Documentation. https://api-docs.deepseek.com/quick_start/rate_limit (consultado 2026-11-25; tier 3: official site)
3. DeepSeek API Change Log and Release Notes (2025-2026). DeepSeek Platform Documentation. publicado 2026-11-13. https://api-docs.deepseek.com/updates (consultado 2026-11-25; tier 3: official site)
4. DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (arXiv:2501.12948). DeepSeek-AI / arXiv. publicado 2025-01-22. https://arxiv.org/abs/2501.12948 (consultado 2026-11-23; tier 2: academic or news)
5. DeepSeek-V3 Technical Report (arXiv:2412.19437). DeepSeek-AI / arXiv. publicado 2024-12-27. https://arxiv.org/abs/2412.19437 (consultado 2026-11-23; tier 2: academic or news)
6. DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model (arXiv:2405.04434). DeepSeek-AI / arXiv. publicado 2024-05-07. https://arxiv.org/abs/2405.04434 (consultado 2026-11-23; tier 2: academic or news)
7. DeepSeek Privacy Policy. Hangzhou DeepSeek Artificial Intelligence Co., Ltd.. https://cdn.deepseek.com/policies/en-US/deepseek-privacy-policy.html (consultado 2026-11-25; tier 3: official site)

## Citar esta página

Mimirwiki. "DeepSeek." Versión 8bb2ba52, 2026-11-25. https://mimirwiki.com/es/wiki/deepseek
