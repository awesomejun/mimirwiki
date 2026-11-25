---
title: "ClaudeBot"
subtitle: "Rastreador web operado por Anthropic para recopilar contenido web público destinado al entrenamiento de modelos de IA"
canonical_url: https://mimirwiki.com/es/wiki/claudebot
language: es
page_class: entity
revision_sha256: 3886bed4961ef010b873231767be2a1247ba667b6e30ee2fa6576e80d42527e4
date_modified: 2026-11-25
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/claudebot.md
  txt: https://mimirwiki.com/es/wiki/claudebot.txt
  json: https://mimirwiki.com/es/wiki/claudebot.json
  jsonld: https://mimirwiki.com/es/wiki/claudebot.jsonld
translations:
  en: https://mimirwiki.com/wiki/claudebot
  ko: https://mimirwiki.com/ko/wiki/claudebot
  ja: https://mimirwiki.com/ja/wiki/claudebot
  zh: https://mimirwiki.com/zh/wiki/claudebot
---

# ClaudeBot

> ClaudeBot es el rastreador web de entrenamiento operado por Anthropic para recopilar contenido web público destinado a modelos de IA generativa. Anthropic lo separa de Claude-SearchBot para la indexación de búsquedas y de Claude-User para las solicitudes iniciadas por el usuario. Los propietarios de sitios pueden bloquear o limitar ClaudeBot mediante robots.txt y, desde el 30 de octubre de 2026, Anthropic también reconoce una señal de preferencia de entrenamiento del borrador aipref del IETF.

ClaudeBot es un rastreador web automatizado operado por Anthropic para recopilar contenido web públicamente disponible que puede contribuir al entrenamiento de sus modelos de IA generativa, incluido Claude. Anthropic documenta ClaudeBot junto con otros dos robots web independientes: Claude-SearchBot para la indexación de búsquedas y Claude-User para recuperar páginas en respuesta a consultas iniciadas por los usuarios. Los propietarios de sitios web pueden restringir o limitar la tasa de solicitudes de ClaudeBot mediante directivas de robots.txt definidas bajo el estándar RFC 9309, incluida la extensión no estándar Crawl-delay, y a partir del 30 de octubre de 2026 Anthropic comenzó a reconocer una señal de preferencia legible por máquina contra el entrenamiento de IA basada en el borrador del grupo aipref del IETF. Varios operadores de sitios web informaron de elevados volúmenes de solicitudes de ClaudeBot en 2024, y la presentación del Formulario S-1/A-3 de Anthropic del 17 de noviembre de 2026 revela un litigio en curso sobre sus prácticas de rastreo web.

**También conocido como:** Rastreador web de Anthropic, Rastreador ClaudeBot

## Datos clave

- **Operador:** Anthropic (al 2026-11-23) [4]
- **Token de producto:** ClaudeBot (al 2026-11-23) [4]
- **Propósito declarado:** Recopilación de contenido web público para el entrenamiento de modelos de IA generativa (al 2026-11-23) [4]
- **Bots complementarios:** Claude-SearchBot (indexación de búsquedas) y Claude-User (recuperación de páginas iniciada por el usuario) (al 2026-11-23) [4]
- **Controles de exclusión:** Directivas de robots.txt, extensión Crawl-delay y señal de preferencia del borrador IETF aipref (desde 2026-10-30) (al 2026-11-23) [4]

## Datos básicos

- **Nombre:** ClaudeBot [4]
- **Tipo:** Rastreador web automatizado (rastreador de entrenamiento) [4]
- **Operador:** Anthropic (al 2026-11-23) [4]
- **Entidad legal operadora:** Anthropic, PBC (corporación de beneficio público de Delaware, San Francisco, California) (al 2026-11-17) [2]
- **Token de producto:** ClaudeBot (al 2026-11-23) [4]
- **Propósito declarado:** Recopilación de contenido web públicamente disponible para el entrenamiento de modelos de IA (al 2026-11-23) [4]
- **Bots complementarios de Anthropic:** Claude-SearchBot (indexación de búsquedas), Claude-User (recuperación dirigida por el usuario) (al 2026-11-23) [4]
- **Protocolo de exclusión:** Protocolo de Exclusión de Robots (robots.txt, IETF RFC 9309) [1]
- **Directiva de límite de tasa:** Crawl-delay (extensión no estándar de robots.txt) (al 2026-11-23) [4]
- **Señal de preferencia de entrenamiento:** Señal no-AI-training del borrador IETF aipref (reconocida desde 2026-10-30) (al 2026-11-23) [4]
- **Política antielusión:** No intenta eludir los CAPTCHA en los sitios rastreados (al 2026-11-23) [4]
- **Documentación de privacidad:** Política de Privacidad de Anthropic (vigente desde 2026-09-10) y Política de Privacidad para No Usuarios independiente (al 2026-09-10) [5]
- **URL de lista de IP publicada:** https://claude.com/crawling/bots.json (14 prefijos IPv4, creationTime 2026-10-20T00:00:00Z) (al 2026-11-23) [10]

## ClaudeBot y el conjunto de robots web de Anthropic

ClaudeBot es el rastreador web de entrenamiento operado por [Anthropic](https://mimirwiki.com/es/wiki/anthropic) como parte de un sistema de tres robots destinado a recopilar contenido web, indexar resultados de búsqueda y recuperar páginas para los usuarios de [Claude](https://mimirwiki.com/es/wiki/claude).[4] Al 23 de noviembre de 2026, la documentación de rastreadores de Anthropic divide el acceso automatizado en tres robots diferenciados para que los propietarios de sitios web puedan establecer políticas de acceso independientes para el entrenamiento de modelos, la indexación de búsquedas y la recuperación iniciada por el usuario.[4]

| Bot | Función declarada | Efecto de la desactivación mediante robots.txt |
| --- | --- | --- |
| ClaudeBot | Recopila contenido web que puede contribuir al entrenamiento de modelos de IA generativa | Indica que los materiales futuros del sitio deben excluirse de los conjuntos de datos de entrenamiento de modelos de IA de Anthropic |
| Claude-SearchBot | Navega y analiza contenido web para mejorar la relevancia y precisión de los resultados de búsqueda | Impide la indexación del contenido del sitio para la optimización de búsquedas, lo que puede reducir la visibilidad y precisión en los resultados de búsqueda de los usuarios |
| Claude-User | Accede a sitios web en respuesta a preguntas formuladas por usuarios de Claude | Impide la recuperación del contenido del sitio en respuesta a consultas de usuarios, lo que puede reducir la visibilidad en búsquedas web dirigidas por el usuario |

Anthropic distingue estos tres rastreadores y recuperadores de los navegadores alojados por Anthropic que Claude utiliza para completar tareas en nombre de un usuario, incluido Claude-Agent en Claude Duet, que se documentan por separado.[4]

Al 23 de noviembre de 2026, Anthropic enumera cuatro principios operativos para sus robots web.[4]

- Identificación transparente mediante los tres nombres de bot documentados
- Ritmo de rastreo no intrusivo en dominios individuales, incluido el respeto de `Crawl-delay` cuando proceda
- Cumplimiento de las directivas de exclusión publicadas en `robots.txt`
- Respeto de las tecnologías antielusión, incluida la abstención de eludir los CAPTCHA en los sitios rastreados

## Controles de ClaudeBot mediante robots.txt e IETF aipref

ClaudeBot sigue las directivas de acceso a nivel de sitio publicadas en [robots.txt](https://mimirwiki.com/es/wiki/robots-txt), el archivo de texto estandarizado por el Internet Engineering Task Force (IETF) en la especificación RFC 9309.[1][4] Publicada en septiembre de 2022, RFC 9309 especifica y amplía el Protocolo de Exclusión de Robots definido originalmente por Martijn Koster en 1994.[1] Según RFC 9309, un archivo `robots.txt` organiza las reglas `allow` y `disallow` en grupos encabezados por tokens de producto `user-agent` compuestos únicamente por letras ASCII, guiones bajos y guiones, que los rastreadores comparan sin distinguir entre mayúsculas y minúsculas antes de recurrir al grupo comodín `user-agent: *` si ningún grupo específico coincide.[1] La coincidencia de rutas comienza desde el primer octeto de la ruta del URI, debe distinguir entre mayúsculas y minúsculas y aplica la regla coincidente más larga; RFC 9309 también señala explícitamente que las reglas de `robots.txt` no constituyen una forma de autorización de acceso.[1]

Para excluir ClaudeBot de un sitio web completo, la documentación de Anthropic al 23 de noviembre de 2026 indica a los propietarios de sitios que añadan `User-agent: ClaudeBot` y `Disallow: /` al archivo `robots.txt` en el directorio de nivel superior del sitio y repitan la configuración en cada subdominio que deseen excluir.[4] Para limitar la frecuencia de solicitudes, Anthropic admite la extensión no estándar `Crawl-delay` en `robots.txt` (por ejemplo, `User-agent: ClaudeBot` seguido de `Crawl-delay: 1`).[1][4]

Anthropic señala al 23 de noviembre de 2026 que la exclusión del rastreo requiere actualizar `robots.txt`.[4] Bloquear las direcciones IP de origen desde las que operan los bots de Anthropic puede impedir que los rastreadores lean el archivo `robots.txt` del sitio, por lo que Anthropic advierte que el bloqueo por IP puede no funcionar de forma fiable ni garantizar una exclusión persistente.[4] Anthropic publica sus prefijos IP de rastreadores en formato JSON en `https://claude.com/crawling/bots.json`; al 23 de noviembre de 2026, el archivo registra `creationTime` `2026-10-20T00:00:00Z` y enumera 14 prefijos IPv4, compuestos por `216.73.216.0/22` y 13 direcciones de host único `/32`.[4][10]

El 30 de octubre de 2026, Anthropic comenzó a reconocer una señal de preferencia legible por máquina que permite a los propietarios de sitios web expresar una configuración de "no entrenamiento de IA".[4] La señal se basa en el borrador del grupo de trabajo `aipref` del IETF, y Anthropic afirma que está desplegando el soporte a nivel global en todos sus servicios de forma progresiva, señalando al mismo tiempo que su interpretación puede evolucionar junto con el borrador del estándar.[4] Para cualquier ruta determinada, las reglas de `robots.txt` que nombren explícitamente a `ClaudeBot` tienen prioridad sobre la señal de preferencia general, incluso si esta especifica una configuración distinta; cuando `robots.txt` no menciona a `ClaudeBot`, Anthropic aplica la configuración de preferencia general.[4]

## ClaudeBot en las políticas de privacidad y datos de entrenamiento de Anthropic

ClaudeBot recopila contenido web públicamente disponible que representa una de las categorías de datos de entrenamiento descritas en la Política de Privacidad y en las presentaciones bursátiles de Anthropic.[2][4][5] La Política de Privacidad de Anthropic, en vigor desde el 10 de septiembre de 2026, enumera seis fuentes de datos recopilados o recibidos para entrenar los modelos de Anthropic.[5]

- Información públicamente disponible a través de Internet
- Conjuntos de datos obtenidos mediante acuerdos comerciales con empresas terceras
- Datos proporcionados por usuarios o colaboradores de crowdsourcing, incluidas las entradas (Inputs) y salidas (Outputs) de los Servicios de Anthropic, salvo que los usuarios opten por excluirse en la configuración de su cuenta
- Comentarios proporcionados explícitamente por los usuarios sobre los Servicios de Anthropic
- Materiales marcados para revisión de seguridad, protección o cumplimiento de políticas
- Datos generados internamente por Anthropic

La Política de Privacidad de Anthropic establece que no se aplica al contenido procesado en nombre de clientes empresariales, como las cuentas Enterprise, que se rige por acuerdos con clientes, y remite a los lectores a una Política de Privacidad para No Usuarios independiente para obtener información sobre cómo se entrenan los grandes modelos de lenguaje con datos personales de terceros y qué opciones asisten a los no usuarios.[5] Incluso cuando un usuario consumidor opta por excluirse del entrenamiento de modelos en la configuración de su cuenta, Anthropic indica que las entradas y salidas pueden seguir utilizándose para la mejora de modelos si las conversaciones se marcan para revisión de seguridad o se notifican explícitamente mediante mecanismos de comentarios.[5]

En la Enmienda n.º 3 al Formulario S-1 presentada ante [SEC EDGAR](https://mimirwiki.com/es/wiki/sec-edgar) el 17 de noviembre de 2026 (número de registro 333-299633), Anthropic, PBC señala que utiliza información públicamente disponible en Internet, conjuntos de datos de terceros con licencia o encargados y datos sintéticos generados por sus propios modelos tanto en las fases de preentrenamiento como de posentrenamiento del desarrollo de modelos.[2] La presentación identifica técnicas de extracción web (web scraping) o rastreo web, escaneo de libros y otros métodos como vías mediante las cuales Anthropic recopila información públicamente disponible.[2] En el mismo documento, Anthropic declara que, aunque adopta medidas diseñadas para cumplir la legislación aplicable, los avisos de `robots.txt` y medidas técnicas como muros de pago o inicios de sesión, dichos esfuerzos pueden no tener siempre éxito y Anthropic podría ser incapaz de verificar si el material recopilado está protegido por leyes de privacidad, derechos de autor u otros derechos de propiedad intelectual.[2]

## ClaudeBot y los controles de rastreadores de IA de Cloudflare

ClaudeBot opera en un entorno más amplio de infraestructura web en el que proveedores de red como [Cloudflare](https://mimirwiki.com/es/wiki/cloudflare) clasifican el tráfico automatizado y ofrecen a los propietarios de sitios controles granulares sobre los rastreadores de IA.[6][7] En un análisis de tráfico del 1 de julio de 2025 que abarca de mayo de 2024 a mayo de 2025, Cloudflare informó de que el tráfico de rastreadores de IA y de búsqueda aumentó un 18%, con [GPTBot](https://mimirwiki.com/es/wiki/gptbot) de [OpenAI](https://mimirwiki.com/es/wiki/openai) creciendo un 305% y Googlebot creciendo un 96%.[9]

El 1 de julio de 2026, Cloudflare introdujo opciones de tráfico de IA en todos los planes de clientes para que los propietarios de sitios web puedan distinguir y gestionar por separado el tráfico de Search, Agent y Training.[7] En esa misma fecha, Cloudflare actualizó su taxonomía BotBase para clasificar cada bot rastreado según su comportamiento y el tipo de acceso del operador, sustituyendo la separación anterior entre bots verificados y agentes firmados por un campo de acceso `Direct` frente a `Intermediary`.[6]

| Dimensión de clasificación BotBase | Categoría | Definición de Cloudflare (documentación actualizada 2026-11-12) |
| --- | --- | --- |
| Comportamiento (ajuste preestablecido gestionado de IA) | Training | Rastreo para entrenar o realizar ajuste fino de modelos |
| Comportamiento (ajuste preestablecido gestionado de IA) | Search | Rastreo para construir índices de búsqueda o bases de datos RAG |
| Comportamiento (ajuste preestablecido gestionado de IA) | Agent | Agentes dirigidos por el usuario que visitan una página en nombre de una persona |
| Etiqueta de acceso del operador | Direct | Operado por un único operador específico, normalmente en su propia infraestructura |
| Etiqueta de acceso del operador | Intermediary | Servicio agéntico impulsado por muchos usuarios finales, que introduce confianza transitiva |

Según la documentación de bots verificados de Cloudflare (actualizada por última vez el 12 de noviembre de 2026), el estatus Verified exige una autoidentificación determinista mediante firmas criptográficas de [Web Bot Auth](https://mimirwiki.com/es/wiki/web-bot-auth), una lista de IP publicada con un user-agent estable o DNS inverso, combinada con un comportamiento no abusivo que respete `robots.txt` y las directivas de rastreo a frecuencias de solicitud razonables.[6] Las categorías heredadas del WAF como `AI Crawler`, `AI Search` y `AI Assistant` siguen disponibles por compatibilidad con versiones anteriores junto con la taxonomía actualizada.[6] Cloudflare incluye el incumplimiento de la directiva `crawl-delay` en `robots.txt` como una infracción de política que puede eliminar a un rastreador de IA de su lista global de permitidos, y señala que las infracciones reiteradas o el cumplimiento incoherente entre los distintos bots de una organización pueden dar lugar a la revocación del estatus Verified para todos los bots operados por dicha organización.[6]

El 15 de septiembre de 2026, Cloudflare anunció también la configuración Disallow AI Training y una designación Accountable que permiten a los propietarios de sitios web permanecer indexados para búsquedas al tiempo que prohíben el entrenamiento de IA, e indicó que Apple, Google y Microsoft respetan o se han comprometido a respetar dicha configuración.[8]

## Informes de editores y litigios por extracción web sobre ClaudeBot

ClaudeBot ha suscitado informes operativos públicos por parte de administradores de sitios web sobre elevados volúmenes de solicitudes, mientras que las prácticas más amplias de rastreo web de Anthropic han sido objeto de procedimientos judiciales.[2][3] El 25 de julio de 2024, *The Verge* informó de que el director ejecutivo de iFixit, Kyle Wiens, declaró que ClaudeBot había enviado casi un millón de solicitudes a los servidores de iFixit en un periodo de 24 horas, lo que activó alertas operativas y requirió la intervención del equipo de DevOps de iFixit.[3]

Los Términos de Uso de iFixit prohibían reproducir, copiar o distribuir el contenido del sitio sin permiso previo y expreso por escrito, incluyendo específicamente el aprendizaje automático o el entrenamiento de modelos de IA.[3] Al ser consultada por 404 Media, Anthropic enlazó a su página de preguntas frecuentes que indica que su rastreador se bloquea mediante `robots.txt`.[3] Después de que iFixit añadiera una regla `crawl-delay` a su archivo `robots.txt`, Wiens declaró a *The Verge* que los registros del servidor mostraban que ClaudeBot se había detenido, y la portavoz de Anthropic, Jennifer Martinez, afirmó que Anthropic respeta `robots.txt` y que su rastreador acató la señal una vez que iFixit la implementó.[3]

En el mismo hilo de debate iniciado por Wiens en X en julio de 2024, el cofundador de Read the Docs, Eric Holscher, y el director ejecutivo de Freelancer.com, Matt Barrie, afirmaron que sus sitios web también habían sufrido una extracción intensiva por parte del rastreador de Anthropic.[3] *The Verge* señaló asimismo que, en abril de 2024, el foro web de Linux Mint atribuyó una caída del sitio a la sobrecarga de los servidores causada por la actividad de extracción de ClaudeBot.[3]

En la Enmienda n.º 3 al Formulario S-1 presentada el 17 de noviembre de 2026, Anthropic, PBC reveló que sus actividades de extracción web, rastreo web y recopilación de datos han dado lugar y siguen siendo objeto de litigios que alegan infracciones legales.[2] En concreto, la presentación cita el caso `Reddit, Inc. v. Anthropic PBC`, en el que Reddit alegó que Anthropic accedió indebidamente a publicaciones almacenadas en la plataforma de Reddit vulnerando los derechos legales de Reddit.[2] Anthropic presentó un aviso de traslado a un tribunal federal el 3 de julio de 2025, el caso fue devuelto a un tribunal estatal el 30 de marzo de 2026 y la demanda seguía pendiente al 17 de noviembre de 2026.[2] Anthropic también reveló como riesgo empresarial que un acuerdo o una sentencia desfavorable en litigios sobre rastreo podría obligar a suspender determinadas técnicas de extracción o rastreo, desarrollar métodos alternativos de recopilación de datos o abonar sumas sustanciales.[2]

## Preguntas frecuentes

### ¿Para qué se utiliza ClaudeBot?

Al 23 de noviembre de 2026, Anthropic utiliza ClaudeBot para recopilar contenido web públicamente disponible que puede contribuir al entrenamiento de sus modelos de IA generativa. Anthropic opera Claude-SearchBot por separado para la indexación de búsquedas y Claude-User para recuperar páginas web en respuesta a consultas de los usuarios. [4]

### ¿Cómo pueden los propietarios de sitios web bloquear o limitar la tasa de solicitudes de ClaudeBot?

Los propietarios de sitios web pueden bloquear ClaudeBot añadiendo User-agent: ClaudeBot y Disallow: / al archivo robots.txt de nivel superior en cada dominio y subdominio que deseen excluir. También pueden limitar la frecuencia de rastreo mediante la extensión no estándar Crawl-delay y, a partir del 30 de octubre de 2026, Anthropic reconoce una señal de preferencia contra el entrenamiento de IA basada en el borrador aipref del IETF. [1][4]

### ¿Bloquear ClaudeBot impide que Claude recupere páginas durante una conversación con un usuario?

No. Restringir ClaudeBot indica que el contenido futuro del sitio debe excluirse de los conjuntos de datos de entrenamiento de modelos de IA de Anthropic. La recuperación de páginas iniciada por el usuario utiliza Claude-User y la indexación de búsquedas utiliza Claude-SearchBot, lo que permite a los propietarios de sitios configurar reglas de robots.txt independientes para cada bot. [4]

### ¿Por qué desaconseja Anthropic bloquear ClaudeBot únicamente por dirección IP?

Al 23 de noviembre de 2026, la documentación de rastreadores de Anthropic indica que bloquear las direcciones IP utilizadas por sus bots impide que los rastreadores lean el archivo robots.txt del sitio, por lo que el bloqueo por IP puede no funcionar de forma fiable ni garantizar una exclusión persistente. Anthropic publica una lista de direcciones IP de origen para que los administradores puedan verificar si un rastreador procede de Anthropic. [4]

### ¿Cómo clasifica Cloudflare a los rastreadores de entrenamiento como ClaudeBot?

Según la taxonomía BotBase introducida el 1 de julio de 2026, Cloudflare clasifica los bots por comportamientos que incluyen Training para entrenamiento o ajuste fino de modelos, Search para índices de búsqueda o bases de datos RAG, y Agent para navegación dirigida por el usuario, con configuraciones gestionadas en todos los planes. Cloudflare también exige que los bots verificados (Verified bots) se identifiquen de forma determinista y respeten las directivas de robots.txt, incluida crawl-delay. [6][7]

### ¿Qué litigios relacionados con el rastreo web ha revelado Anthropic en sus presentaciones ante la SEC?

En la Enmienda n.º 3 al Formulario S-1 presentada ante la SEC el 17 de noviembre de 2026, Anthropic, PBC reveló un litigio pendiente en el caso Reddit, Inc. v. Anthropic PBC, que alega un acceso indebido a publicaciones almacenadas en la plataforma de Reddit. Anthropic presentó un aviso de traslado a un tribunal federal el 3 de julio de 2025 y el caso fue devuelto a un tribunal estatal el 30 de marzo de 2026. [2]

## Frases citables

- Al 23 de noviembre de 2026, Anthropic documenta tres robots web: ClaudeBot para la recopilación de datos de entrenamiento de modelos de IA, Claude-SearchBot para la indexación de búsquedas y Claude-User para la recuperación de páginas iniciada por el usuario. [4]
- Al 23 de noviembre de 2026, Anthropic afirma que sus bots web respetan las directivas de robots.txt, admiten la extensión no estándar Crawl-delay y no intentan eludir los CAPTCHA. [4]
- A partir del 30 de octubre de 2026, Anthropic comenzó a reconocer una señal de preferencia legible por máquina contra el entrenamiento de IA basada en el borrador del grupo de trabajo aipref del IETF, con prioridad para las reglas explícitas de robots.txt dirigidas a ClaudeBot. [4]
- La especificación RFC 9309, publicada por el IETF en septiembre de 2022, define el Protocolo de Exclusión de Robots y establece que las reglas de robots.txt no constituyen una forma de autorización de acceso. [1]
- En julio de 2024, el director ejecutivo de iFixit, Kyle Wiens, informó de que ClaudeBot envió casi un millón de solicitudes a los servidores de iFixit en 24 horas y se detuvo después de que iFixit añadiera una directiva crawl-delay en robots.txt. [3]
- La Política de Privacidad de Anthropic, en vigor desde el 10 de septiembre de 2026, enumera la información públicamente disponible en Internet entre seis fuentes de datos utilizadas para entrenar los modelos de Anthropic. [5]
- En la Enmienda n.º 3 al Formulario S-1 presentada ante la SEC el 17 de noviembre de 2026, Anthropic, PBC reveló que el caso Reddit, Inc. v. Anthropic PBC seguía pendiente tras ser devuelto a un tribunal estatal el 30 de marzo de 2026. [2]
- El análisis de rastreadores publicado por Cloudflare el 1 de julio de 2025 informó de que el tráfico de rastreadores de IA y de búsqueda aumentó un 18% entre mayo de 2024 y mayo de 2025, con un incremento del 305% en el tráfico de GPTBot y del 96% en el de Googlebot. [9]

## Cronología

- 2022-09: El IETF publica RFC 9309, que estandariza el Protocolo de Exclusión de Robots (robots.txt). [1]
- 2024-04: El foro web de Linux Mint atribuye una caída del sitio a la sobrecarga de los servidores causada por la actividad de extracción de ClaudeBot. [3]
- 2024-07-25: The Verge informa de que ClaudeBot envió casi un millón de solicitudes a iFixit en 24 horas y se detuvo después de que iFixit añadiera una directiva crawl-delay a robots.txt. [3]
- 2025-07-01: Cloudflare publica un análisis de tráfico de rastreadores que informa de un aumento del 18% en el tráfico de rastreadores de IA y búsqueda entre mayo de 2024 y mayo de 2025, con GPTBot al alza un 305% y Googlebot un 96%. [9]
- 2025-07-03: Anthropic presenta un aviso de traslado a un tribunal federal en Reddit, Inc. v. Anthropic PBC, una demanda que alega acceso indebido a publicaciones de Reddit. [2]
- 2026-03-30: El caso Reddit, Inc. v. Anthropic PBC es devuelto de un tribunal federal a un tribunal estatal. [2]
- 2026-07-01: Cloudflare introduce opciones de tráfico separadas de Search, Agent y Training para todos los clientes y añade las etiquetas de acceso Direct frente a Intermediary en BotBase. [6][7]
- 2026-09-10: Entra en vigor la Política de Privacidad actualizada de Anthropic, que enumera la información públicamente disponible en Internet entre seis fuentes de datos de entrenamiento de modelos. [5]
- 2026-09-15: Cloudflare anuncia la configuración Disallow AI Training y la designación Accountable para permanecer indexado en búsquedas prohibiendo el entrenamiento de IA, e indica que Apple, Google y Microsoft la respetan o se han comprometido a respetarla. [8]
- 2026-10-30: Anthropic comienza a reconocer una señal de preferencia legible por máquina contra el entrenamiento de IA basada en el borrador del grupo de trabajo aipref del IETF. [4]
- 2026-11-17: Anthropic, PBC presenta la Enmienda n.º 3 al Formulario S-1 ante la SEC, revelando métodos de rastreo web, limitaciones de cumplimiento de robots.txt y litigios pendientes sobre rastreo. [2]

## Fuentes

1. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309.txt (consultado 2026-11-23; tier 1: government or public registry)
2. Anthropic, PBC - S-1/A-3. U.S. Securities and Exchange Commission (EDGAR). publicado 2026-11-17. https://www.sec.gov/Archives/edgar/data/2130357/000162828026074338/anthropicpbc-sx1ax3.htm (consultado 2026-11-23; tier 1: government or public registry)
3. Anthropic’s crawler is ignoring websites’ anti-AI scraping policies | The Verge. The Verge. publicado 2024-07-25. https://www.theverge.com/2024/7/25/24205943/anthropic-ai-web-crawler-claudebot-ifixit-scraping-training-data (consultado 2026-11-23; tier 2: academic or news)
4. Does Anthropic crawl data from the web, and how can site owners block the crawler? | Claude Help Center. Anthropic. https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler (consultado 2026-11-23; tier 3: official site)
5. Privacy Policy \ Anthropic. Anthropic. publicado 2026-09-10. https://www.anthropic.com/legal/privacy (consultado 2026-11-23; tier 3: official site)
6. Verified bots · Cloudflare bot solutions docs. Cloudflare. publicado 2026-11-12. https://developers.cloudflare.com/bots/concepts/bot/verified-bots/ (consultado 2026-11-23; tier 3: official site)
7. Your site, your rules: new AI traffic options for all customers | Cloudflare Blog. The Cloudflare Blog. publicado 2026-07-01. https://blog.cloudflare.com/content-independence-day-ai-options/ (consultado 2026-11-23; tier 3: official site)
8. Have it both ways: stay discoverable in search while disallowing AI training | Cloudflare Blog. The Cloudflare Blog. publicado 2026-09-15. https://blog.cloudflare.com/accountable-mixed-use-ai-crawlers/ (consultado 2026-11-23; tier 3: official site)
9. From Googlebot to GPTBot: Who’s crawling your site in 2025 | Cloudflare Blog. The Cloudflare Blog. publicado 2025-07-01. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (consultado 2026-11-23; tier 3: official site)
10. Anthropic Crawler IP Prefixes (bots.json). Anthropic. publicado 2026-10-20. https://claude.com/crawling/bots.json (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "ClaudeBot." Versión 3886bed4, 2026-11-25. https://mimirwiki.com/es/wiki/claudebot
