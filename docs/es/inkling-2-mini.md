---
title: "Inkling 2 Mini"
subtitle: "Modelo visión-lenguaje de mezcla de expertos en bucle y pesos abiertos de Thinking Machines Lab, diseñado para inferencia local en portátiles y estaciones de trabajo"
canonical_url: https://mimirwiki.com/es/wiki/inkling-2-mini
language: es
page_class: entity
revision_sha256: ffbd796e6dd6494d463f567e158bcbbf7c09040211941a7877c97d41fb320b96
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/es/wiki/inkling-2-mini.md
  txt: https://mimirwiki.com/es/wiki/inkling-2-mini.txt
  json: https://mimirwiki.com/es/wiki/inkling-2-mini.json
  jsonld: https://mimirwiki.com/es/wiki/inkling-2-mini.jsonld
translations:
  en: https://mimirwiki.com/wiki/inkling-2-mini
  ko: https://mimirwiki.com/ko/wiki/inkling-2-mini
  ja: https://mimirwiki.com/ja/wiki/inkling-2-mini
  zh: https://mimirwiki.com/zh/wiki/inkling-2-mini
---

# Inkling 2 Mini

> Publicado el 20 de noviembre de 2026 bajo licencia Apache 2.0, Inkling 2 Mini (`thinkingmachines/Inkling-2-Mini`) es un modelo visión-lenguaje de mezcla de expertos en bucle de 26 400 millones de parámetros con una ventana de contexto de 1 millón de tokens. Al recorrer sus 12 capas intermedias tres veces por token (48 visitas lógicas de capa, 3400 millones de parámetros activos únicos y 5400 millones de activaciones efectivas) y entrenarse de forma nativa en NVFP4 de 4 bits y MXFP8 de 8 bits (huella aproximada de 20 GB), se ejecuta sin conexión en portátiles de consumo mientras obtiene 48,2 % en DeepSWE v1.1, 79,2 % en SWE-bench Verified y 20,1 en el Artificial Analysis Intelligence Index v5.0.

Inkling 2 Mini es un modelo visión-lenguaje de pesos abiertos publicado el 20 de noviembre de 2026 por Thinking Machines Lab, la empresa de investigación en inteligencia artificial dirigida por la exdirectora de tecnología de OpenAI Mira Murati. Construido sobre una arquitectura Transformer de mezcla de expertos (MoE) en bucle de 24 capas con 26 400 millones de parámetros totales, el modelo ejecuta sus 12 capas intermedias tres veces por token para ofrecer 48 aplicaciones efectivas de capa y 5400 millones de activaciones efectivas de pesos por token a partir de 3400 millones de parámetros activos únicos, ejecutándose localmente en una huella aproximada de 20 GB en precisión mixta (NVFP4/MXFP8) bajo licencia Apache 2.0.

**También conocido como:** Inkling 2 Mini, Thinking Machines Lab, Transformer en bucle, Mezcla de expertos, IA de pesos abiertos, LLM local

## Datos clave

- **Fecha de lanzamiento y licencia:** 20 de noviembre de 2026; Apache 2.0 (con Política de Uso Aceptable) [1]
- **Arquitectura:** MoE en bucle de 24 capas (48 visitas de capa; enrutamiento a 8 de 128 expertos SwiGLU) [2]
- **Recuento de parámetros:** 26 400 M totales, 3400 M activos únicos, 5400 M de activaciones efectivas por token [1]
- **Precisión nativa y tamaño:** NVFP4 (primeras 20 capas) + MXFP8 (últimas 4 capas); punto de control de ~20 GB (17,5 GB en GGUF de 4 bits) [3]
- **Resultados destacados:** 48,2 % DeepSWE v1.1, 79,2 % SWE-bench Verified, 77,9 % SWE-bench Pro v2 Hard, 20,1 AAv5 [1]

## Datos básicos

- **Desarrollador:** Thinking Machines Lab [1]
- **Fecha de lanzamiento:** 20 de noviembre de 2026 [1]
- **ID del modelo:** thinkingmachines/Inkling-2-Mini [2]
- **Modelo complementario de investigación:** thinkingmachines/TML-d24-varloop-research (entre 1 y 5 pasadas de bucle variables) [2]
- **Arquitectura:** Transformer de mezcla de expertos dispersa en bucle (24 capas físicas / 48 capas lógicas) [2]
- **Parámetros:** 26 400 M totales / 3400 M activos únicos / 5400 M de activaciones efectivas de pesos por token [1]
- **Ventana de contexto:** 1 000 000 de tokens [5]
- **Modalidades:** Entrada de texto e imagen; salida de texto [5]
- **Precisión numérica:** NVFP4 nativo (capas 0-19) y MXFP8 (capas 20-23) [1]
- **Requisitos de memoria:** Punto de control nativo de ~20 GB (32 GB de RAM/VRAM recomendados; 17-18 GB para GGUF de 4 bits) [5]
- **Precios de API propia:** 0,15 USD / 1 M entrada; 0,50 USD / 1 M salida; 0,015 USD / 1 M acierto de caché (en Tinker) [4]
- **Licencia:** Apache 2.0 (acompañada de la Política de Uso Aceptable del Modelo) [5]

## Descripción general y arquitectura de mezcla de expertos en bucle

Thinking Machines Lab, la empresa de investigación en inteligencia artificial con sede en San Francisco fundada y dirigida por la exdirectora de tecnología de OpenAI Mira Murati, publicó Inkling 2 Mini el 20 de noviembre de 2026 como un modelo visión-lenguaje de pesos abiertos adaptado para ordenadores portátiles locales, estaciones de trabajo de escritorio y agentes autónomos de programación.[1][3] Derivado de la escala de escalado predictivo principal de Thinking Machines y situado por debajo del modelo de mayor tamaño Inkling 2 Small, Inkling 2 Mini se distribuye bajo licencia Apache 2.0 (acompañada de una Política de Uso Aceptable del Modelo) y admite entradas multimodales de texto e imagen en una ventana de contexto de 1 millón de tokens.[1][2][5]

En lugar de depender únicamente de extensas transcripciones externalizadas de cadena de pensamiento (CoT) o de un mayor número de parámetros, Inkling 2 Mini introduce un diseño Transformer de mezcla de expertos (MoE) en bucle.[1][2][3] El decodificador de texto almacena 24 capas físicas con una dimensión oculta de 2304 (la mitad del ancho de 4608 de Inkling 2 Small) y una anchura intermedia por experto de 1152, enrutando cada token a 8 de 128 expertos SwiGLU por visita de capa (frente a 8 de 384 expertos en Inkling 2 Small).[2] Las 24 capas físicas se organizan en cuatro bloques de seis capas que ejecutan 48 visitas lógicas de capa por token:[1][2]

- **Bloque preludio (capas 0-5)**: Se ejecuta una vez por token para proyectar los embeddings en representaciones internas.[1][2]
- **Bloques centrales en bucle (capas 6-17)**: Los dos bloques intermedios de seis capas ejecutan tres pasadas consecutivas por token compartiendo los mismos pesos almacenados (`6 + 3 * 12 + 6 = 48` aplicaciones de capa).[1][2] En estudios internos de escalado en 28 evaluaciones, aplicar el bucle a las 12 capas intermedias superó a aplicarlo a las 12 capas finales en 27 tareas, aportando una ganancia de pérdida equivalente en cómputo de entre 1,51x y 1,91x en el paso de entrenamiento 2000 (y exigiendo un 140 % más de cómputo de inferencia a una línea base sin bucle para igualar su pérdida en trazas agénticas de 512K tokens).[1][3]
- **Bloque final (capas 18-23)**: Se ejecuta una vez por token para decodificar la representación interna refinada.[1][2]

Cada bloque de seis capas comprende cinco capas de atención de ventana deslizante (con una ventana local de 1024 tokens) y una capa de atención completa equipada con convoluciones cortas dinámicas de clave y valor, 24 cabezas de consulta, 8 cabezas de clave-valor, logits de posición relativa aprendidos, un sumidero de atención aprendido y una compuerta de salida.[2] Aunque las tres pasadas por las capas 6-17 reutilizan los mismos pesos de parámetros, cada una de las 48 visitas mantiene su propia caché KV y su propio estado de convolución corta.[2] Para transmitir información entre iteraciones, Inkling 2 Mini implementa residuos de atención (basados en la formulación de residuos de atención de 2026 del equipo de Kimi): cada pasada por el núcleo en bucle comienza con la salida del bloque preludio, mientras que las pasadas 2 y 3 también atienden sobre dos bloques residuales de la pasada anterior ("mensajes entre pasadas") mediante consultas aprendidas y cuatro controladores de compuerta de rango 64 que mezclan el mensaje previo en las entradas de consulta, clave, valor y MoE.[1][2]

En total, Inkling 2 Mini contiene 26 400 millones de parámetros físicos, activa 3400 millones de parámetros únicos en una sola pasada (3100 millones de pesos únicos por token de texto) y aplica 5400 millones de activaciones efectivas de pesos por token a lo largo de las tres pasadas del bucle.[1][4][5]

## Poda de expertos, recuperación por destilación y entrenamiento nativo en NVFP4

Para comprimir una arquitectura de razonamiento de nivel de frontera en una huella de memoria de ~20 GB apta para la memoria de portátiles de consumo, Thinking Machines modificó su proceso principal de entrenamiento mediante poda de expertos a mitad de entrenamiento y entrenamiento nativo en baja precisión de bits:[1][3]

1. **Poda de dos tercios de los expertos y recuperación por destilación**: Partiendo de un punto de control principal más amplio con 384 expertos por capa, Thinking Machines podó dos tercios de los expertos hasta dejar 128 expertos por capa.[1][2][3] A continuación, la red podada se "recuperó" destilando 1 billón de tokens procedentes de un modelo Inkling interno de mayor tamaño, seguido de ajuste fino supervisado (SFT) y 2,2 billones de tokens de aprendizaje por refuerzo (RL).[3] 2. **Precisión nativa NVFP4 y MXFP8**: En lugar de depender de una cuantización posterior al entrenamiento que puede degradar la precisión en programación agéntica, Thinking Machines entrenó y desplegó las primeras 20 capas físicas de forma nativa en precisión NVFP4 de 4 bits y las últimas cuatro capas en precisión MXFP8 de 8 bits.[1][3] Dado que los pesos distribuidos coinciden con el formato numérico empleado durante el entrenamiento, el punto de control original en precisión mixta requiere aproximadamente 20 GB de memoria sin pérdida por cuantización posterior al entrenamiento.[3][5] 3. **Esfuerzo de razonamiento numérico configurable**: La plantilla de conversación del modelo acepta un parámetro `reasoning_effort` expresado como nivel con nombre o como valor decimal continuo entre `0.0` y `0.99`, inyectado en el prompt como mensaje de sistema: `none` (`0.0`), `minimal` (`0.1`), `low` (`0.2`), `medium` (`0.7`), `high` (`0.9`, valor predeterminado), `xhigh` (`0.99`) y `max` (`0.99`).[2] Incluso en el ajuste mínimo, el razonamiento interno no se desactiva por completo.[5]

## Rendimiento en evaluaciones comparativas y eficiencia energética

En 48 evaluaciones comparativas estandarizadas entre modelos de pesos abiertos de menos de 100 000 millones de parámetros (incluidos el modelo denso Qwen3.8-27B de Alibaba, Gemma 4 31B de Google DeepMind, Muse Glimmer de Meta y Nemotron 3.5 Super VL de 124 500 millones de parámetros de NVIDIA), Inkling 2 Mini ocupó el primer puesto en 32 evaluaciones.[1][2] En el Artificial Analysis Intelligence Index v5.0 (AAv5), Inkling 2 Mini obtuvo 20,1 puntos, empatando con el modelo denso Qwen3.8-27B utilizando aproximadamente 5 veces menos parámetros activos, 2,8 veces menos cómputo total (parámetros activos multiplicados por tokens), 4 veces menos tiempo real por tarea (9,0 minutos frente a 38,2 minutos) y un coste 6 veces menor por tarea (0,59 USD frente a 3,53 USD con las tarifas de la API propia Tinker de Thinking Machines de 0,15 USD por 1 M de tokens de entrada, 0,50 USD por 1 M de salida y 0,015 USD por 1 M de aciertos de caché).[1][3][4]

| Evaluación comparativa | Categoría | Inkling 2 Mini (5,4 B ef. / 26,4 B) | Qwen3.8-27B (27 B denso) | Gemma 4 31B (30,7 B denso) | Muse Glimmer (30 B denso) | Nemotron 3.5 Super VL (12 B / 124,5 B) |
| --- | --- | --- | --- | --- | --- | --- |
| AA Intelligence Index v5.0 | Inteligencia agregada | 20,1 (1.º empatado) | 20,1 (1.º empatado) | 4,4 | 6,3 | 13,6 |
| Vals Index v2.2 | Empresa / programación agregada | 46,5 % | - | - | - | 29,8 % |
| DeepSWE v1.1 | Ingeniería de software agéntica | 48,2 % | 42,2 % | 0,3 % | 4,4 % | 24,7 % |
| SWE-bench Pro v2 (Hard) | Ingeniería de software difícil (51 tareas) | 77,9 % | 73,8 % | 14,2 % | 44,3 % | 44,1 % |
| SWE-bench Verified | Ingeniería de software solo en Bash | 79,2 % | 77,8 % | 46,1 % | 76,0 % | 71,1 % |
| FrontierCode v2.0 | Fusión de PR de código abierto | 15,1 % | 14,9 % | 0,0 % | 1,5 % | 6,1 % |
| Terminal Bench v4.0 | Ejecución agéntica en terminal | 5,6 % (1.º empatado) | 5,6 % (1.º empatado) | 0,0 % | 0,5 % | 0,0 % |
| BrowseComp | Navegación web agéntica (con compactación) | 79,0 % | 61,6 % | 37,0 % | 63,9 % | 78,9 % |
| DeepSearchQA | Respuesta a preguntas de búsqueda profunda | 85,3 % | 79,7 % | 61,7 % | 74,6 % | 77,7 % |
| MCP Atlas Public | Uso de herramientas Model Context Protocol | 82,7 % | 77,3 % | 54,2 % | 75,5 % | 67,7 % |
| OmniDocBench v1.6 | Comprensión visual de documentos | 92,8 % | 91,5 % | 82,5 % | 90,4 % | 77,9 % |
| LongBench v2 | Razonamiento de contexto largo | 66,9 % | 52,3 % | 52,9 % | 33,1 % | 62,1 % |
| AA-Omniscience v1.1 | Factualidad paramétrica / no alucinación | -8,6 (63,4 %) | -6,4 (71,4 %) | -48,5 (14,5 %) | -32,2 (16,4 %) | -2,9 (69,5 %) |

En pruebas de eficiencia energética realizadas por investigadores del Hazy Research Lab y el Scaling Intelligence Lab de la Universidad de Stanford mediante la metodología Intelligence per Watt en un NVIDIA DGX Spark (128 GB), Inkling 2 Mini (ejecutado en precisión MXFP8 con esfuerzo de razonamiento bajo) alcanzó 0,703 de inteligencia por julio, superando a Qwen3.6-35B-A3B (0,430 en NVFP4), Gemma-4-26B-A4B (0,159 en NVFP4) y Qwen3.5-27B (0,036 en INT4).[1][3]

Dado que el bucle incrementa el cómputo de razonamiento secuencial por token sin ampliar el número total de parámetros almacenados, la memoria factual paramétrica permanece acotada por su capacidad total de 26 400 millones de pesos: en AA-Omniscience v1.1, Inkling 2 Mini obtiene -8,6 con una tasa de no alucinación del 63,4 %, quedando por detrás de modelos más densos cuando las herramientas de búsqueda están desactivadas.[1][3] También queda por detrás de Qwen3.8-27B en restricciones conversacionales multiturno (50,0 % en MultiChallenge y 33,4 % en ComplexConstraints v1.1) y puede presentar bucles de razonamiento repetitivos durante sesiones prolongadas de depuración.[1][5]

## Monitorización de la cadena de pensamiento e investigación de bucles variables

Una cuestión central de seguridad en inteligencia artificial en torno a los transformers en bucle es si ejecutar múltiples pasadas recurrentes de forma interna en el espacio latente reduce la capacidad de monitorizar la cadena de pensamiento (CoT), al permitir que el modelo razone sin externalizar sus pasos en texto.[1][3] Para facilitar la investigación sistemática de supervisión, Thinking Machines publicó un punto de control complementario de investigación con bucle variable, `thinkingmachines/TML-d24-varloop-research`, entrenado para ejecutar entre 1 y 5 pasadas por las 12 capas intermedias (configurable en tiempo de inferencia mediante `text_config={"loop_num_passes": N}`), y colaboró con National Deep Inference Fabric (NDIF) y Goodfire en estudios de interpretabilidad mecanicista.[1][2][3]

En los experimentos de monitorización de Thinking Machines sobre el modelo de bucle variable:[1][3]

- **Expansión del horizonte latente sin CoT**: Cuando se impidió al modelo producir tokens visibles de cadena de pensamiento, su horizonte temporal efectivo de tarea se duplicó con creces, pasando de 16 segundos con 1 pasada de bucle a 37 segundos con 3 pasadas de bucle, y su precisión en tareas de razonamiento secuencial siguió mejorando hasta 10 pasadas de bucle (el doble de la profundidad máxima vista durante el entrenamiento).[1][3]
- **Compresión frente a legibilidad de la CoT**: A medida que aumentó la profundidad del bucle, las transcripciones visibles de cadena de pensamiento del modelo se acortaron en más de un 50 %, aunque los supervisores humanos y automatizados constataron que las trazas de CoT restantes seguían siendo legibles y fieles.[1][3]
- **Evaluaciones de sabotaje y comportamiento indebido**: Añadir pasadas recurrentes de bucle no produjo ninguna tendencia al alza en el sabotaje agéntico encubierto en el benchmark de control LinuxArena.[1][3] En evaluaciones internas de seguridad, Inkling 2 Mini registró tasas más bajas de comportamiento indebido general (9,8 %), comportamiento indebido encubierto (8,3 %) y acciones destructivas (10,2 %) que Gemma 4 31B, Muse Glimmer, Qwen3.8-27B y Nemotron 3.5 Super VL, además de obtener 89,5 % en FORTRESS (adversarial) y 97,8 % en StrongREJECT.[1]

## Despliegue local, requisitos de hardware y ecosistema de ejecución

Inkling 2 Mini se lanzó con soporte de inferencia desde el primer día en entornos de ejecución locales y en la nube, incluidos la plataforma Tinker de Thinking Machines, `transformers` de Hugging Face (`AutoModelForMultimodalLM`), `llama.cpp` y Llama App, LM Studio, Unsloth Desktop, MLX en Apple Silicon, Ollama, EXO y SGLang para GPU de centros de datos, junto con un modelo borrador de decodificación especulativa DSpark.[1][2][3][5][6] Thinking Machines mostró el modelo ejecutándose completamente sin conexión en modo avión en un MacBook Pro con Apple M5 Pro (48 GB de memoria unificada), donde construyó un simulador de vuelo en 3D jugable en cuestión de minutos y alimentó simultáneamente a 20 aldeanos autónomos de IA persistentes en la simulación urbana "Thinkyville".[1][3]

| Cuantización / Formato | Tamaño aproximado de archivo | RAM / VRAM mínima | Notas y compatibilidad de ejecución |
| --- | --- | --- | --- |
| Precisión mixta original (NVFP4 + MXFP8) | ~20,0 GB | 32 GB recomendados | Precisión nativa de entrenamiento; ideal para Mac con Apple Silicon de 32 GB+ o GPU con 32 GB+ de VRAM |
| GGUF de 8 bits (`UD-Q8_K_XL` / `Q8_0`) | ~24,0 GB | 24 GB | Equivalente sin pérdida a precisión completa para llama.cpp y Unsloth |
| GGUF de 4 bits (`UD-Q4_K_XL` / `IQ4_NL`) | 17,5 - 17,6 GB | 17 - 18 GB | Cuantización GGUF local recomendada; requiere ~18 GB de memoria del sistema |
| GGUF dinámico de 3 bits / 2 bits / 1 bit | 9,0 - 15,0 GB | 9 - 15 GB | GGUF Unsloth Dynamic 3.0 para portátiles de consumo de 16 GB |
| Proyector de visión (`mmproj-F16.gguf`) | +639 MB | +0,7 GB | Proyector adicional necesario para entradas multimodales de imágenes y documentos en GGUF |

Para la ejecución local en GGUF con `llama.cpp` o Unsloth, los parámetros de muestreo recomendados son `temperature = 1.0`, `top_p = 1.0`, `top_k = 0` y `min_p = 0.0`, utilizando una compilación con soporte para disposición de capas en bucle y escalas NVFP4 por experto (como `ggml-org/Inkling-2-Mini-GGUF` o `unsloth/Inkling-2-Mini-GGUF`).[2][6]

## Preguntas frecuentes

### ¿Cómo funciona la arquitectura transformer en bucle de Inkling 2 Mini?

En lugar de pasar cada token por sus 24 capas físicas una sola vez, Inkling 2 Mini divide su decodificador en cuatro bloques de seis capas. El primer bloque (capas 0-5) se ejecuta una vez, los dos bloques intermedios (capas 6-17) se ejecutan tres veces en bucle reutilizando los mismos pesos almacenados y el bloque final (capas 18-23) se ejecuta una vez. Mensajes residuales de atención con compuertas transmiten información intermedia de una iteración del bucle a la siguiente, lo que genera 48 aplicaciones de capa y 5400 millones de activaciones efectivas de pesos por token almacenando solo 24 capas (26 400 millones de parámetros totales y 3400 millones de parámetros activos únicos). [2]

### ¿Qué hardware se necesita para ejecutar Inkling 2 Mini de forma local?

El punto de control original en precisión mixta (entrenado de forma nativa en NVFP4 de 4 bits y MXFP8 de 8 bits) ocupa aproximadamente 20 GB, para lo cual Thinking Machines Lab recomienda al menos 32 GB de memoria unificada en ordenadores Mac con Apple Silicon o 32 GB de VRAM en GPU. Mediante cuantizaciones GGUF de 4 bits (como UD-Q4_K_XL o IQ4_NL, de aproximadamente 17,5-17,6 GB) en LM Studio, llama.cpp o Unsloth Desktop, el modelo puede ejecutarse en sistemas con 16 GB a 18 GB de RAM, mientras que la versión GGUF de 8 bits sin pérdida requiere 24 GB. [5]

### ¿Cómo se compara Inkling 2 Mini con Qwen3.8-27B?

En el Artificial Analysis Intelligence Index v5.0, Inkling 2 Mini empata con el modelo denso Qwen3.8-27B de Alibaba con una puntuación de 20,1, al tiempo que lo supera en evaluaciones de programación agéntica y búsqueda como DeepSWE v1.1 (48,2 % frente a 42,2 %), SWE-bench Verified (79,2 % frente a 77,8 %) y BrowseComp (79,0 % frente a 61,6 %). Como Inkling 2 Mini activa solo 5400 millones de parámetros efectivos por token frente a los 27 000 millones del modelo denso de Qwen, utiliza aproximadamente 2,8 veces menos cómputo, completa las tareas del Intelligence Index 4 veces más rápido (9,0 frente a 38,2 minutos) y cuesta 6 veces menos por tarea (0,59 USD frente a 3,53 USD). No obstante, Qwen3.8-27B puntúa más alto en memoria factual paramétrica sin herramientas (AA-Omniscience) y en instrucciones conversacionales con múltiples restricciones. [4]

### ¿Qué es el modelo TML-d24-varloop-research publicado junto con Inkling 2 Mini?

TML-d24-varloop-research es un punto de control de investigación de pesos abiertos que comparte la arquitectura MoE de 24 capas de Inkling 2 Mini, pero fue entrenado para aceptar un número variable de pasadas (de 1 a 5, y probado hasta 10) por sus 12 capas intermedias mediante el parámetro de configuración loop_num_passes. Thinking Machines Lab lo publicó para que los investigadores de seguridad e interpretabilidad puedan medir cómo los bucles latentes recurrentes afectan a la longitud de la cadena de pensamiento, la capacidad de monitorización y la profundidad del razonamiento. [2]

## Frases citables

- Thinking Machines Lab publicó Inkling 2 Mini el 20 de noviembre de 2026 bajo licencia Apache 2.0 como un modelo visión-lenguaje de mezcla de expertos en bucle de 26 400 millones de parámetros compatible con una ventana de contexto de 1 millón de tokens. [1][2][5]
- Las 24 capas físicas del decodificador de Inkling 2 Mini ejecutan 48 visitas lógicas de capa por token ejecutando una vez las capas 0-5, repitiendo tres veces en bucle las capas 6-17 con pesos compartidos y mensajes residuales de atención entre pasadas, y ejecutando una vez las capas 18-23, lo que produce 3400 millones de parámetros activos únicos y 5400 millones de activaciones efectivas de pesos por token. [1][2][5]
- El modelo se comprimió podando dos tercios de sus expertos (de 384 a 128 por capa), destilando 1 billón de tokens de recuperación desde un modelo Inkling de mayor tamaño seguido de 2,2 billones de tokens de aprendizaje por refuerzo, y entrenando las primeras 20 capas de forma nativa en NVFP4 y las últimas 4 capas en MXFP8 para lograr una huella aproximada de 20 GB. [1][2][3]
- En evaluaciones estandarizadas, Inkling 2 Mini lidera a todos los modelos de pesos abiertos de menos de 100 000 millones de parámetros en DeepSWE v1.1 (48,2 %), SWE-bench Pro v2 Hard (77,9 %), SWE-bench Verified (79,2 %), BrowseComp (79,0 %), DeepSearchQA (85,3 %) y OmniDocBench v1.6 (92,8 %), mientras empata con Qwen3.8-27B con 20,1 puntos en el Artificial Analysis Intelligence Index v5.0. [1][3][4]
- En la evaluación Intelligence per Watt de la Universidad de Stanford en un NVIDIA DGX Spark, Inkling 2 Mini obtuvo 0,703 de inteligencia por julio, superando a Qwen3.6-35B-A3B (0,430), Gemma-4-26B-A4B (0,159) y Qwen3.5-27B (0,036). [1][3]
- Los experimentos con el punto de control complementario de bucle variable (TML-d24-varloop-research) mostraron que aumentar las pasadas de bucle de 1 a 3 amplió el horizonte de razonamiento sin CoT del modelo de 16 a 37 segundos, manteniendo la legibilidad de la cadena de pensamiento y sin mostrar aumento en el sabotaje agéntico. [1][2][3]

## Cronología

- 2018: Dehghani et al. publican Universal Transformers, estableciendo los conceptos fundamentales de capas transformer recurrentes con compartición de pesos citados por Thinking Machines Lab. [1]
- 2026-11-20: Thinking Machines Lab publica Inkling 2 Mini y el punto de control complementario TML-d24-varloop-research bajo licencia Apache 2.0, con soporte desde el primer día en Transformers, llama.cpp, MLX, SGLang, LM Studio y Unsloth. [1]
- 2026-11-21: Análisis independientes de evaluaciones comparativas confirman a Inkling 2 Mini en la frontera de Pareto del Artificial Analysis Intelligence Index v5.0 con una puntuación de 20,1. [3]

## Fuentes

1. Introducing Inkling 2 Mini - Thinking Machines Lab. Thinking Machines Lab. publicado 2026-11-20. https://thinkingmachines.ai/news/inkling-2-mini/ (consultado 2026-11-23; tier 3: official site)
2. Welcome Inkling 2 Mini, Cutting-edge Performance for your Local Setup. Hugging Face. publicado 2026-11-20. https://huggingface.co/blog/inkling2mini (consultado 2026-11-23; tier 3: official site)
3. Thinking Machines wows with Inkling 2 Mini looped transformer model that runs locally on laptops. VentureBeat. publicado 2026-11-21. https://venturebeat.com/technology/thinking-machines-wows-with-inkling-2-mini-looped-transformer-model-that-runs-locally-on-laptops (consultado 2026-11-23; tier 2: academic or news)
4. Thinking Machines has released Inkling 2 Mini, an open weights looped transformer. Artificial Analysis. publicado 2026-11-20. https://artificialanalysis.ai/articles/inkling-2-mini (consultado 2026-11-23; tier 2: academic or news)
5. Inkling 2 Mini - LM Studio Model Directory. Element Labs (LM Studio). https://lmstudio.ai/models/inkling-2-mini (consultado 2026-11-23; tier 3: official site)
6. Inkling 2 Mini - Run Locally Guide | Unsloth Documentation. Unsloth. https://unsloth.ai/docs/models/inkling-2-mini (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Inkling 2 Mini." Versión ffbd796e, 2026-11-23. https://mimirwiki.com/es/wiki/inkling-2-mini
