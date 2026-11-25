---
title: "Optimización para motores generativos"
subtitle: "Métodos y métricas para mejorar la visibilidad y la citación de contenido web en respuestas de búsqueda con IA generativa"
canonical_url: https://mimirwiki.com/es/wiki/generative-engine-optimization
language: es
page_class: concept
revision_sha256: 8e5b743cf5db763df80b5b870a55f7af1552cdb4e63e3d69844566a5a3598de2
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 11
alternates:
  md: https://mimirwiki.com/es/wiki/generative-engine-optimization.md
  txt: https://mimirwiki.com/es/wiki/generative-engine-optimization.txt
  json: https://mimirwiki.com/es/wiki/generative-engine-optimization.json
  jsonld: https://mimirwiki.com/es/wiki/generative-engine-optimization.jsonld
translations:
  en: https://mimirwiki.com/wiki/generative-engine-optimization
  ko: https://mimirwiki.com/ko/wiki/generative-engine-optimization
  ja: https://mimirwiki.com/ja/wiki/generative-engine-optimization
  zh: https://mimirwiki.com/zh/wiki/generative-engine-optimization
---

# Optimización para motores generativos

> La optimización para motores generativos (GEO) es un conjunto de métodos de contenido y estructura destinados a aumentar la visibilidad y la citación de fuentes web en las respuestas generadas por sistemas de búsqueda con IA. Acuñado en noviembre de 2023 por Aggarwal et al. junto con el banco de pruebas GEO-bench, el enfoque GEO abarca flujos multietapa de recuperación y generación, donde los efectos medidos dependen del estado de recuperación y del dominio.

La optimización para motores generativos (GEO, del inglés Generative Engine Optimization) es un paradigma de optimización de contenido web diseñado para incrementar la presencia, la probabilidad de citación y la prominencia de los documentos fuente en respuestas sintetizadas por motores de búsqueda generativos. Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan y Ameet Deshpande introdujeron formalmente el término el 16 de noviembre de 2023 en arXiv:2311.09735, trabajo que fue aceptado en la 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD 2024). Mientras que los motores de búsqueda convencionales devuelven listas clasificadas de enlaces, los motores generativos recuperan documentos web a través de motores de búsqueda subyacentes y emplean modelos lingüísticos de gran tamaño para producir respuestas fundamentadas en lenguaje natural con citas integradas en línea. Una revisión crítica de julio de 2026 describe GEO como un flujo estocástico y parcialmente observable que abarca el rastreo y la indexación, la recuperación, la reclasificación, la citación y la fidelidad, mientras que la documentación de Google Search Central señala, a fecha de 2026-11-23, que los requisitos técnicos de búsqueda y los fundamentos de SEO vigentes se aplican a sus funciones de IA sin optimizaciones independientes.

**También conocido como:** GEO, Generative Engine Optimization, Optimización para motores de respuesta, SEO conversacional

## Datos clave

- **Primera propuesta:** 2023-11-16 (arXiv:2311.09735; aceptado en KDD 2024) [1]
- **Autores originales:** Aggarwal, Murahari, Rajpurohit, Kalyan, Narasimhan y Deshpande [1]
- **Banco de pruebas inicial:** GEO-bench (10 000 consultas en diversos dominios) [2]
- **Ganancias en el banco de pruebas inicial:** Hasta un 40 % de aumento de visibilidad en pruebas de referencia; hasta un 37 % en Perplexity.ai (al 2024-06-28) [2]
- **Requisitos de la Búsqueda de Google:** Sin requisitos técnicos adicionales ni optimizaciones especiales más allá de los requisitos técnicos de la Búsqueda (al 2026-11-23) [7]

## Datos básicos

- **Tipo:** Paradigma de recuperación de información y optimización de contenido web [1]
- **Abreviatura:** GEO [1]
- **Primera propuesta:** 2023-11-16 (arXiv:2311.09735 v1) [1]
- **Publicación en congreso:** 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '24), 25-29 de agosto de 2024 [2]
- **Autores originales:** Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan, Ameet Deshpande [1]
- **Afiliaciones de los autores:** Instituto Indio de Tecnología de Delhi; Universidad de Princeton; investigadores independientes [2]
- **Banco de pruebas inicial:** GEO-bench (10 000 consultas de usuarios de múltiples dominios) [2]
- **Corpus bibliográfico revisado:** 45 estudios entre noviembre de 2023 y julio de 2026 (Martinez, 2026) (al 2026-07-15) [5]
- **Resultado de optimización estructural:** Mejora del 17,3 % en tasa de citación y del 18,5 % en calidad subjetiva en seis motores (GEO-SFE) (al 2026-03-31) [4]
- **Directrices de la Búsqueda de Google:** Los fundamentos estándar de SEO y la elegibilidad de fragmentos se aplican a AI Overviews y AI Mode (al 2026-11-23) [7]

## Qué es la optimización para motores generativos

La optimización para motores generativos (GEO) es un marco destinado a mejorar la forma en que el contenido web aparece y recibe atribución dentro de las respuestas sintetizadas por motores de búsqueda generativos.[1][2] Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan y Ameet Deshpande acuñaron el término en la versión 1 de su prepublicación `arXiv:2311.09735` el 16 de noviembre de 2023, publicaron la revisión v3 el 28 de junio de 2024 y presentaron el trabajo en las actas de la 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '24), celebrada del 25 al 29 de agosto de 2024 en Barcelona.[1][2] Los autores estaban afiliados al Instituto Indio de Tecnología de Delhi, la Universidad de Princeton y puestos de investigación independientes en Seattle.[2]

El artículo formaliza los motores generativos (GE) como sistemas de búsqueda que combinan un motor de búsqueda subyacente con múltiples modelos lingüísticos de gran tamaño (LLM), y cita a BingChat, SGE de Google y [Perplexity](https://mimirwiki.com/es/wiki/perplexity) (Perplexity.ai) como ejemplos desplegados.[2] Formalmente, un motor generativo transforma una consulta del usuario y un contexto opcional de personalización en una respuesta en lenguaje natural mediante pasos modulares: un modelo de reformulación de consultas expande la consulta inicial en subconsultas, un motor de búsqueda recupera fuentes web clasificadas, un modelo de resumen condensa cada fuente y un modelo de generación de respuestas redacta una respuesta estructurada con citas integradas en línea.[2] La atribución en línea ofrece a los usuarios un mecanismo para verificar afirmaciones y contrarrestar las alucinaciones de los LLM, y se evalúa en términos de exhaustividad de citas (si las afirmaciones están respaldadas por citas relevantes) y precisión de citas (si las citas adjuntas respaldan realmente las afirmaciones).[2]

La optimización para motores generativos responde a una preocupación estructural de los propietarios de sitios web y los editores de contenido.[1][2] Las respuestas sintetizadas directas reducen la necesidad de que los usuarios hagan clic hacia los sitios de origen, lo que puede disminuir el tráfico orgánico de referencia, mientras que los flujos propietarios de generación limitan la visibilidad de los creadores sobre cómo se ingieren y citan sus páginas.[2] La revisión de Martinez de 2026 exploró la bibliografía bajo familias de términos que incluían optimización para motores de respuesta, SEO conversacional, visibilidad en búsquedas con IA y absorción de citas.[6]

## Marco, métricas y GEO-bench en la optimización para motores generativos

La optimización para motores generativos (GEO) fue formalizada inicialmente por Aggarwal et al. como un marco de optimización de caja negra que toma como entrada una página web fuente y produce una versión revisada con ajustes en la presentación, el estilo del texto y el contenido para aumentar su visibilidad en motores generativos propietarios.[1][2] En esta formulación, un editor busca maximizar la función de visibilidad o impresión de su cita dentro de una respuesta generada, mientras el motor generativo equilibra la impresión de la cita y la relevancia respecto a la consulta mediante una función interna opaca.[2]

La visibilidad en motores generativos difiere de la posición promedio en los resultados de búsqueda convencionales, donde las páginas aparecen en una lista lineal.[2] Las respuestas generativas presentan prosa estructurada que intercala múltiples citas en línea con extensiones de pasaje, ubicaciones y estilos variables.[2] Para evaluar la atribución en esas dimensiones, el marco GEO define métricas de visibilidad personalizables que capturan la relevancia y la influencia de las citas desde perspectivas tanto objetivas como subjetivas.[2]

Para poner a prueba las estrategias de GEO de manera sistemática, Aggarwal et al. publicaron GEO-bench, un banco de pruebas compuesto por 10 000 consultas de usuarios extraídas de diversos dominios y emparejadas con fuentes web relevantes.[1][2] En las evaluaciones sobre GEO-bench, los autores informaron que los métodos de GEO aumentaron la visibilidad de las fuentes hasta en un 40 %.[1][2] La incorporación de citas, citas textuales de fuentes relevantes y estadísticas generó incrementos de visibilidad superiores al 40 % en consultas variadas, aunque la eficacia de cada estrategia varió de forma sustancial según el dominio.[1][2] Los autores también evaluaron sus métodos en [Perplexity](https://mimirwiki.com/es/wiki/perplexity) (Perplexity.ai) como motor generativo en producción, donde informaron ganancias de visibilidad de hasta el 37 %.[2]

## Estudios empíricos sobre la optimización para motores generativos en 2025 y 2026

La investigación sobre la optimización para motores generativos se amplió considerablemente en 2025 y 2026 para abarcar plataformas comerciales de búsqueda con IA, la estructura documental y auditorías metodológicas.[3][4][5] Tres artículos de arXiv publicados entre septiembre de 2025 y julio de 2026 ilustran el paso desde ediciones de contenido evaluadas en un único banco de pruebas hacia comparaciones entre múltiples motores, ingeniería estructural y síntesis crítica.[3][4][5]

| Estudio | Fecha | Alcance | Principales hallazgos informados |
| --- | --- | --- | --- |
| Aggarwal et al. (arXiv:2311.09735 / KDD '24) | 2023-11-16 (v3: 2024-06-28) | GEO-bench de 10 000 consultas y Perplexity.ai | Hasta un 40 % de ganancia de visibilidad en pruebas de referencia; más del 40 % mediante citas, citas textuales y estadísticas; hasta un 37 % en Perplexity.ai.[1][2] |
| Chen et al. (arXiv:2509.08919) | 2025-09-10 | ChatGPT, Perplexity y Gemini frente a la Búsqueda de Google en distintos sectores, idiomas y paráfrasis | Sesgo sistemático hacia los medios ganados de terceros frente a fuentes propias de marca y sociales; amplias diferencias entre motores en diversidad, actualidad y sensibilidad a la formulación.[3] |
| Yu et al. (arXiv:2603.29979) | 2026-03-31 | Ingeniería de características estructurales (GEO-SFE) en seis motores generativos | La optimización de macroestructura, mesoestructura y microestructura elevó la tasa de citación en un 17,3 % y la calidad subjetiva en un 18,5 %, preservando la integridad semántica.[4] |
| Martinez (arXiv:2607.14035) | 2026-07-15 | Revisión crítica exploratoria de 45 estudios (nov. de 2023 a jul. de 2026) | Modela GEO como un flujo estocástico multietapa; halla evidencia concentrada en fuentes ya recuperadas, sin efecto causal multiplataforma estable sobre la descubribilidad orgánica o el tráfico.[5][6] |

En septiembre de 2025, Mahe Chen, Xiaoxuan Wang, Kaiwen Chen y Nick Koudas compararon [ChatGPT](https://mimirwiki.com/es/wiki/chatgpt), [Perplexity](https://mimirwiki.com/es/wiki/perplexity) y [Google Gemini](https://mimirwiki.com/es/wiki/google-gemini) frente a la búsqueda web tradicional de Google en múltiples sectores, idiomas y paráfrasis de consultas.[3] Sus experimentos controlados hallaron que los motores de búsqueda con IA presentan un sesgo sistemático hacia los medios ganados (fuentes autorizadas de terceros) por encima del contenido propio de marca y social, en contraste con la combinación de fuentes más equilibrada de Google.[3] El estudio también documentó variaciones significativas entre los servicios de búsqueda con IA en cuanto a diversidad de dominios, actualidad, estabilidad entre idiomas y sensibilidad a la formulación, lo que llevó a los autores a proponer cuatro prioridades prácticas: estructurar el contenido para facilitar el escaneo y la justificación por máquinas, desarrollar presencia en medios ganados, adaptar las tácticas por motor e idioma, y contrarrestar el sesgo hacia grandes marcas en sitios de nicho.[3]

En marzo de 2026, Junwei Yu, Mufeng Yang, Yepeng Ding y Hiroyuki Sato presentaron GEO-SFE, un marco de ingeniería de características estructurales que aborda la disposición documental junto con las ediciones semánticas del texto.[4] GEO-SFE descompone la estructura de una página web en tres niveles jerárquicos: macroestructura (arquitectura del documento), mesoestructura (fragmentación de la información) y microestructura (énfasis visual).[4] Al evaluar estrategias conscientes de la arquitectura en seis motores generativos, los autores informaron mejoras consistentes del 17,3 % en la tasa de citación y del 18,5 % en la calidad subjetiva, manteniendo la integridad semántica.[4]

En julio de 2026, Olivier Martinez publicó una revisión crítica exploratoria de 45 estudios sobre GEO publicados o aceptados entre el 16 de noviembre de 2023 y el 14 de julio de 2026, junto con una prepublicación anterior presentada en EMNLP en diciembre de 2023 y bibliografía relacionada sobre evaluación de la generación aumentada por recuperación.[5][6] La revisión formaliza GEO como un flujo multietapa que abarca la activación de la búsqueda, el rastreo y la indexación, la recuperación, la reclasificación y asignación de contexto, la citación, la prominencia, la absorción factual, la fidelidad y el comportamiento del usuario, acompañado de un vector de visibilidad que distingue entre descubribilidad, citación, absorción y resultados económicos.[5]

## La optimización para motores generativos y su relación con SEO, RAG, robots.txt y llms.txt

La optimización para motores generativos se interseca con la optimización para motores de búsqueda (SEO), la generación aumentada por recuperación (RAG), los controles de acceso para rastreadores y las convenciones emergentes de publicación legibles por máquina.[2][5][7][9] El SEO convencional se centra en mejorar la clasificación de las páginas en listas de enlaces, mientras que GEO apunta al modo en que los modelos lingüísticos ingieren, resumen y citan las páginas recuperadas.[2] Dado que los motores de búsqueda generativos dependen de índices de búsqueda y modelos de recuperación subyacentes, los mecanismos previos de SEO siguen acoplados a los resultados posteriores de citación.[5][7] La revisión de Martinez de 2026 señala que las intervenciones pueden mejorar una etapa del flujo y perjudicar otra; en particular, las reescrituras ajustadas estrechamente para obtener citas pueden degradar la recuperación previa.[5][6]

Las reglas de acceso para rastreadores determinan si el contenido web llega siquiera a incorporarse en los índices de búsqueda generativa.[7][9] Mediante la convención [robots.txt](https://mimirwiki.com/es/wiki/robots-txt), los propietarios de sitios especifican el acceso automatizado aceptable para bots de indexación y rastreadores.[9] Google Search Central precisa que permitir el rastreo en `robots.txt` y en las capas de red de distribución de contenido (CDN) o alojamiento sigue siendo un requisito básico para aparecer en las funciones de búsqueda con IA.[7] [OpenAI](https://mimirwiki.com/es/wiki/openai) mantiene documentación independiente para desarrolladores en la que describe sus rastreadores web.[10] En la capa de infraestructura de red, [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare) anunció el 1 de julio de 2026 opciones de gestión de tráfico disponibles para todos los clientes que separan los controles de tráfico de IA en tres categorías diferenciadas: búsqueda, agentes y entrenamiento.[11]

Los editores también han debatido [llms.txt](https://mimirwiki.com/es/wiki/llms-txt), una convención web propuesta por Jeremy Howard el 3 de septiembre de 2024 y actualizada a la versión v2 el 10 de agosto de 2026.[9] La propuesta define un archivo resumen curado en Markdown ubicado en `/llms.txt` o en una subruta como `/docs/llms.txt`, acompañado de versiones limpias en `.md` de páginas individuales descubribles mediante elementos HTML `<link>` o encabezados HTTP `Link` con las relaciones de enlace `alternate` (`type="text/markdown"`) y `describedby`.[9] La propuesta distingue `llms.txt` de `robots.txt`, que rige los permisos de rastreo, y de los mapas de sitio (`sitemap.xml`), que enumeran todas las páginas indexables legibles por humanos y suelen ser demasiado extensos en conjunto para la ventana de contexto de un LLM.[9] Asimismo, evita el prefijo de raíz de origen `/.well-known/` definido en el RFC 8615 para que los autores en alojamientos compartidos puedan publicar archivos con alcance limitado a una ruta.[9] A fecha de agosto de 2026, la especificación v2 señala que `llms.txt` se ha utilizado principalmente en tiempo de inferencia, que plataformas de documentación como Mintlify y GitBook lo generan automáticamente, y que [OpenAI](https://mimirwiki.com/es/wiki/openai), [Anthropic](https://mimirwiki.com/es/wiki/anthropic) y Gemini de Google publican archivos `llms.txt` para su documentación de desarrolladores; la propia página de documentación de rastreadores de OpenAI enlaza a `llms.txt` y a direcciones URL de páginas en `.md`.[9][10]

## Directrices de plataformas sobre la optimización para motores generativos

La optimización para motores generativos ha recibido directrices explícitas de plataforma por parte de Google Search Central respecto a AI Overviews y AI Mode en la Búsqueda de Google.[7][8] A fecha de 2026-11-23, la documentación oficial de Google establece que las prácticas fundamentales de SEO siguen siendo relevantes para las funciones de IA en la Búsqueda de Google y que los propietarios de sitios no enfrentan requisitos técnicos adicionales ni optimizaciones especiales para aparecer en AI Overviews o AI Mode.[7] Para ser elegible como enlace de respaldo en cualquiera de ambas funciones, una página debe estar indexada y ser elegible para aparecer en la Búsqueda de Google con un fragmento conforme a los requisitos técnicos estándar de la Búsqueda, aunque el cumplimiento no garantiza el rastreo, la indexación ni la publicación.[7]

Google describe AI Overviews como resúmenes destinados a consultas en las que una visión general aporta valor más allá de la Búsqueda clásica, señalando que con frecuencia no se activan, mientras que describe AI Mode como especialmente útil para consultas que requieren una exploración más profunda, razonamiento o comparaciones complejas.[7] Ambas funciones pueden aplicar una técnica de expansión de consultas ("query fan-out") que emite múltiples búsquedas relacionadas sobre subtemas y fuentes de datos durante la generación de la respuesta para identificar un conjunto más amplio de páginas web de respaldo.[7] Dado que AI Overviews y AI Mode pueden apoyarse en modelos y técnicas distintos, las respuestas y los enlaces de respaldo que muestran pueden variar.[7]

Google enumera los fundamentos vigentes de SEO aplicables a las funciones de búsqueda con IA:[7]

- Permitir el rastreo en `robots.txt` y en la infraestructura de CDN o alojamiento
- Hacer que las páginas sean descubribles mediante enlaces internos del sitio web
- Ofrecer una excelente experiencia de página y mantener el contenido importante disponible en formato textual
- Complementar el texto con imágenes y videos de alta calidad cuando corresponda
- Asegurar que los datos estructurados coincidan con el texto visible en la página
- Mantener actualizada la información de Merchant Center y Business Profile

En el Blog de Google Search Central, Google publicó en mayo de 2025 orientaciones sobre el rendimiento del contenido en sus experiencias de búsqueda con IA, anunció en mayo de 2026 un recurso dedicado a la optimización para la IA generativa en la Búsqueda de Google e introdujo en junio de 2026 informes de rendimiento de Search Generative AI en Search Console.[8]

## Límites metodológicos y fronteras de la evidencia en la optimización para motores generativos

La optimización para motores generativos enfrenta límites metodológicos y empíricos sustanciales documentados en auditorías de 2025 y 2026.[3][5][6] En su revisión crítica de julio de 2026 sobre 45 estudios, Olivier Martinez señala que las afirmaciones comerciales suelen extrapolar la cifra de hasta un 40 % de visibilidad obtenida por Aggarwal et al. como una promesa general de posicionarse alto en ChatGPT, pese a que dicho resultado midió la visibilidad relativa en un simulador donde cinco documentos candidatos ya habían sido colocados dentro del contexto del modelo.[5][6] En toda la bibliografía revisada, la evidencia muestra que modificar un documento ya recuperado puede alterar causalmente su citación o uso dentro de una respuesta, mientras que ninguna técnica revisada demuestra un efecto causal estable, longitudinal y multiplataforma sobre la descubribilidad orgánica o sobre el comportamiento posterior del usuario, como el tráfico y las conversiones.[5][6]

Los hallazgos empíricos también muestran sensibilidad a las condiciones experimentales y a la dinámica competitiva.[5][6] En los estudios analizados, la relevancia temática y la posición en el contexto emergen como los factores más reproducibles que inciden en la citación, mientras que las heurísticas genéricas se transfieren mal entre dominios y modelos.[5] La competencia entre múltiples actores puede erosionar las ganancias individuales de optimización cuando varios editores aplican ediciones similares, lo que ayuda a conciliar resultados aparentemente contradictorios entre estudios de un solo actor y de múltiples actores, como Puerto et al. (2025).[5][6] Las auditorías de motores generativos comerciales informan además una baja superposición de fuentes entre plataformas, una variabilidad considerable entre ejecuciones, sensibilidad a las paráfrasis de consultas y brechas persistentes de fidelidad en las que una fuente puede ser citada sin respaldar una afirmación o parafraseada sin enlace.[3][5][6]

Dado que las reescrituras legítimas de contenido, las secuencias de texto adversarias y las inyecciones indirectas de instrucciones alteran todas el texto consumido por un motor generativo, Martinez plantea que la optimización y la manipulación comparten un mismo canal técnico.[6] Bajo ese análisis, distinguir las prácticas aceptables de GEO de la manipulación depende de la veracidad, la preservación semántica, la transparencia y la ausencia de instrucciones ocultas.[6] Martinez también señala que la bibliografía sobre GEO de 2023-2026 mezcla artículos de congresos revisados por pares, artículos próximos aceptados formalmente, ponencias de talleres y prepublicaciones, y propone un protocolo de evaluación reproducible que incorpora mediciones repetidas, paráfrasis de consultas, condiciones de control, validación humana y pruebas de interferencia entre múltiples actores.[5][6]

## Preguntas frecuentes

### ¿Qué es la optimización para motores generativos (GEO)?

La optimización para motores generativos (GEO, por sus siglas en inglés) es un marco de optimización de caja negra orientado a ajustar la presentación, el estilo y la estructura del contenido web para aumentar su visibilidad y citación en las respuestas producidas por motores de búsqueda generativos. Aggarwal et al. introdujeron el término el 2023-11-16 en arXiv:2311.09735, artículo posteriormente aceptado en KDD 2024. [1][2]

### ¿En qué se diferencia la optimización para motores generativos del SEO tradicional?

La optimización para motores de búsqueda (SEO) tradicional se centra en la posición promedio dentro de una lista clasificada de enlaces. La optimización para motores generativos aborda la síntesis de múltiples documentos, la ubicación de citas en línea, la prominencia y la atribución factual a lo largo de flujos multietapa de recuperación y generación. [2][5]

### ¿Qué halló el estudio original de GEO-bench?

En las evaluaciones sobre el conjunto de datos GEO-bench de 10 000 consultas, Aggarwal et al. informaron aumentos de visibilidad de hasta el 40 % en consultas diversas, mejoras superiores al 40 % al añadir citas, citas textuales y estadísticas, y aumentos de hasta el 37 % en Perplexity.ai. Una revisión de julio de 2026 realizada por Olivier Martinez señaló que las mejoras del banco de pruebas se midieron en un simulador con cinco documentos ya colocados en el contexto, por lo que no demuestran descubribilidad orgánica ni efectos duraderos sobre el tráfico. [2][5][6]

### ¿Qué muestran los estudios académicos de 2025 y 2026 sobre la eficacia de GEO?

Un estudio de septiembre de 2025 de Chen et al. halló que ChatGPT, Perplexity y Gemini favorecen los medios ganados de terceros frente al contenido propio de marca y social, y varían entre motores en diversidad, actualidad y sensibilidad a la formulación. Un estudio de marzo de 2026 de Yu et al. informó mejoras del 17,3 % en la tasa de citación y del 18,5 % en la calidad subjetiva mediante ingeniería de características estructurales en seis motores, mientras que la revisión de 45 estudios de Martinez en julio de 2026 determinó que la relevancia temática y la posición en el contexto son los factores más reproducibles. [3][4][5]

### ¿Requiere Google técnicas especiales de GEO para AI Overviews y AI Mode?

No. A fecha de 2026-11-23, la documentación de Google Search Central establece que las páginas indexadas y elegibles para la Búsqueda de Google con un fragmento no requieren especificaciones técnicas adicionales ni optimizaciones especiales para aparecer como enlaces de respaldo en AI Overviews o AI Mode. [7]

### ¿Cómo se relacionan robots.txt y llms.txt con la optimización para motores generativos?

El archivo robots.txt establece reglas de acceso para rastreadores automatizados, y Google exige permitir el rastreo en robots.txt y en la infraestructura de alojamiento para ser elegible en sus funciones de IA. Cloudflare también permite a los propietarios de sitios separar los controles de tráfico de IA de búsqueda, agentes y entrenamiento desde julio de 2026, mientras que llms.txt es una propuesta independiente de archivo resumen en Markdown diseñada para su uso bajo demanda en tiempo de inferencia por modelos lingüísticos y agentes. [7][9][11]

## Frases citables

- Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan y Ameet Deshpande introdujeron el término Generative Engine Optimization (optimización para motores generativos) el 2023-11-16 en arXiv:2311.09735, trabajo que fue aceptado en KDD 2024. [1][2]
- El banco de pruebas GEO-bench consta de 10 000 consultas de diversos dominios y fuentes web adaptadas para evaluar métodos de visibilidad en motores generativos. [2]
- Aggarwal et al. informaron aumentos de visibilidad de hasta el 40 % en diversas consultas en su evaluación de referencia y de hasta el 37 % en Perplexity.ai, con incrementos superiores al 40 % al incorporar citas, citas textuales de fuentes relevantes y estadísticas. [2]
- Un estudio empírico de septiembre de 2025 realizado por Chen et al. halló que ChatGPT, Perplexity y Gemini muestran un sesgo sistemático hacia los medios ganados de terceros frente al contenido propio de marca y las redes sociales, en comparación con la búsqueda web de Google. [3]
- El marco de ingeniería de características estructurales GEO-SFE informó una mejora del 17,3 % en la tasa de citación y una mejora del 18,5 % en la calidad subjetiva en seis motores generativos en marzo de 2026. [4]
- Una revisión crítica de julio de 2026 realizada por Olivier Martinez, que analizó 45 estudios, concluyó que el contenido ya recuperado puede afectar causalmente su citación o uso, mientras que ninguna técnica revisada demostró un efecto causal estable, longitudinal y multiplataforma sobre la descubribilidad orgánica o el comportamiento posterior del usuario. [5]
- La documentación de Google Search Central indica, a fecha de 2026-11-23, que las páginas indexadas y elegibles para aparecer en la Búsqueda de Google con un fragmento no tienen requisitos técnicos adicionales ni optimizaciones especiales para AI Overviews o AI Mode. [7]
- El 2026-07-01, Cloudflare introdujo opciones de gestión de tráfico que permiten a los propietarios de sitios web distinguir y controlar por separado el tráfico de IA de búsqueda, de agentes y de entrenamiento. [11]

## Cronología

- 2023-11-16: Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan y Ameet Deshpande envían la versión 1 de "GEO: Generative Engine Optimization" a arXiv, introduciendo el término GEO y el banco de pruebas GEO-bench. [1]
- 2024-06-28: Aggarwal et al. publican la revisión v3 del artículo sobre GEO en arXiv antes de su presentación en KDD 2024 (del 25 al 29 de agosto de 2024 en Barcelona). [1][2]
- 2024-09-03: Jeremy Howard publica la propuesta /llms.txt para ofrecer resúmenes curados de sitios web en Markdown a modelos lingüísticos y agentes de IA. [9]
- 2025-05: El Blog de Google Search Central publica orientaciones sobre el rendimiento del contenido en las experiencias de búsqueda con IA de Google. [8]
- 2025-09-10: Chen et al. envían un estudio comparativo de ChatGPT, Perplexity, Gemini y la Búsqueda de Google (arXiv:2509.08919), en el que documentan el sesgo hacia medios ganados y las diferencias entre motores. [3]
- 2026-03-31: Yu et al. envían el estudio de ingeniería de características estructurales GEO-SFE (arXiv:2603.29979), que informa mejoras en la tasa de citación y la calidad subjetiva en seis motores generativos. [4]
- 2026-06: El Blog de Google Search Central anuncia informes de rendimiento de Search Generative AI en Search Console, tras un recurso publicado en mayo de 2026 sobre la optimización para la IA generativa en la Búsqueda de Google. [8]
- 2026-07-01: Cloudflare introduce controles de tráfico de IA que permiten a los propietarios de sitios web distinguir y gestionar por separado el tráfico de búsqueda, de agentes y de entrenamiento. [11]
- 2026-07-15: Olivier Martinez publica una revisión crítica de 45 estudios sobre GEO desde noviembre de 2023 hasta julio de 2026 (arXiv:2607.14035), formalizando un modelo de flujo multietapa y un protocolo de evaluación reproducible. [5][6]
- 2026-08-10: Jeremy Howard actualiza la propuesta /llms.txt a la versión v2, que describe la ubicación del archivo en una subruta y su descubrimiento mediante las relaciones de enlace alternate y describedby. [9]

## Fuentes

1. [2311.09735] GEO: Generative Engine Optimization. arXiv. publicado 2023-11-16. https://arxiv.org/abs/2311.09735 (consultado 2026-11-23; tier 2: academic or news)
2. GEO: Generative Engine Optimization. arXiv. publicado 2024-06-28. https://arxiv.org/html/2311.09735v3 (consultado 2026-11-23; tier 2: academic or news)
3. [2509.08919] Generative Engine Optimization: How to Dominate AI Search. arXiv. publicado 2025-09-10. https://arxiv.org/abs/2509.08919 (consultado 2026-11-23; tier 2: academic or news)
4. [2603.29979] Structural Feature Engineering for Generative Engine Optimization: How Content Structure Shapes Citation Behavior. arXiv. publicado 2026-03-31. https://arxiv.org/abs/2603.29979 (consultado 2026-11-23; tier 2: academic or news)
5. [2607.14035] Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023-2026). arXiv. publicado 2026-07-15. https://arxiv.org/abs/2607.14035 (consultado 2026-11-23; tier 2: academic or news)
6. Optimizing Visibility in Generative Engines: A Critical Survey of Generative Engine Optimization (2023–2026). arXiv. publicado 2026-07-15. https://arxiv.org/html/2607.14035v1 (consultado 2026-11-23; tier 2: academic or news)
7. AI Features and Your Website | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/ai-features (consultado 2026-11-23; tier 3: official site)
8. Top ways to ensure your content performs well in Google's AI experiences on Search | Google Search Central Blog | Google for Developers. Google Search Central Blog. publicado 2025-05. https://developers.google.com/search/blog/2025/05/succeeding-in-ai-search (consultado 2026-11-23; tier 3: official site)
9. The /llms.txt file, v2 – llms-txt. llmstxt.org. publicado 2024-09-03. https://llmstxt.org/ (consultado 2026-11-23; tier 3: official site)
10. Overview of OpenAI Crawlers. OpenAI. https://developers.openai.com/api/docs/bots (consultado 2026-11-23; tier 3: official site)
11. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. publicado 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "Optimización para motores generativos." Versión 8e5b743c, 2026-11-25. https://mimirwiki.com/es/wiki/generative-engine-optimization
