---
title: "GPTBot"
subtitle: "Rastreador web automatizado de OpenAI utilizado para recopilar datos de entrenamiento para modelos fundacionales de IA generativa"
canonical_url: https://mimirwiki.com/es/wiki/gptbot
language: es
page_class: entity
revision_sha256: 7fde1535d1627d59796395b3fb94a6b417d384369ebc5549f7173c2bc89eb8f3
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/gptbot.md
  txt: https://mimirwiki.com/es/wiki/gptbot.txt
  json: https://mimirwiki.com/es/wiki/gptbot.json
  jsonld: https://mimirwiki.com/es/wiki/gptbot.jsonld
translations:
  en: https://mimirwiki.com/wiki/gptbot
  ko: https://mimirwiki.com/ko/wiki/gptbot
  ja: https://mimirwiki.com/ja/wiki/gptbot
  zh: https://mimirwiki.com/zh/wiki/gptbot
---

# GPTBot

> A finales de 2026, GPTBot se identifica mediante el token de agente de usuario GPTBot/1.4 (+https://openai.com/gptbot) y publica sus prefijos IPv4 de salida verificables en openai.com/gptbot.json (18 bloques CIDR a fecha de 22 de septiembre de 2026). Los operadores de sitios web pueden bloquear de forma independiente el rastreo para entrenamiento de modelos mediante robots.txt (RFC 9309) desautorizando a GPTBot y permitiendo a OAI-SearchBot (39 bloques IPv4) para mantener su visibilidad en los resultados de búsqueda de ChatGPT, junto con los estándares emergentes IETF AI Preferences (aipref) y las firmas criptográficas de Web Bot Auth.

GPTBot es el principal rastreador web automatizado operado por OpenAI para descubrir y obtener contenido web público que puede utilizarse para entrenar modelos fundacionales de inteligencia artificial generativa. Opera junto con otros tres agentes de usuario de OpenAI con funciones diferenciadas: OAI-SearchBot (para la indexación de búsqueda de ChatGPT), OAI-AdsBot (para la verificación de páginas de destino publicitarias) y ChatGPT-User (para la navegación en tiempo real iniciada por el usuario y acciones de Custom GPT).

**También conocido como:** GPTBot/1.4, OAI-SearchBot, OAI-AdsBot, ChatGPT-User

## Datos clave

- **Operador:** OpenAI (OpenAI OpCo, LLC) [1]
- **Token actual de User-Agent:** GPTBot/1.4 (+https://openai.com/gptbot) (al 2026-11-23) [1]
- **Rangos de IP publicados:** 18 prefijos CIDR IPv4 en openai.com/gptbot.json (actualizado el 2026-09-22) (al 2026-11-23) [2]
- **Agentes complementarios de OpenAI:** OAI-SearchBot/1.4 (búsqueda), OAI-AdsBot/1.0 (anuncios), ChatGPT-User/1.0 (acciones de usuario) (al 2026-11-23) [1]

## Datos básicos

- **Operador:** OpenAI [1]
- **Función principal:** Rastreo de contenido web público para el entrenamiento de modelos fundacionales de IA generativa [1]
- **Cadena User-Agent:** Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot) [1]
- **Manifiesto de verificación de IP:** https://openai.com/gptbot.json (18 prefijos IPv4 a fecha de 2026-09-22) [2]
- **Rastreador complementario de búsqueda:** OAI-SearchBot/1.4 (https://openai.com/searchbot.json, 39 prefijos IPv4) [1]
- **Protocolo de exclusión:** Protocolo de exclusión de robots (IETF RFC 9309 / robots.txt) [5]
- **Estándares emergentes:** IETF AI Preferences (aipref) e IETF Web Bot Auth (webbotauth) [6]

## Descripción general y taxonomía de rastreadores de OpenAI

Introducido por OpenAI en agosto de 2023 y evolucionado hasta la versión 1.4 en 2026, **GPTBot** es el rastreador web dedicado de OpenAI para recopilar texto y medios públicos de internet utilizados para entrenar y mejorar modelos fundacionales de IA generativa.[1] Dado que los editores de sitios web suelen desear distinguir entre la ingesta de datos de entrenamiento, la indexación en motores de búsqueda, las comprobaciones de cumplimiento publicitario y la obtención de páginas en directo iniciada por usuarios, OpenAI separa su tráfico HTTP automatizado en cuatro agentes de usuario distintos con controles `robots.txt` y manifiestos de IP independientes:[1]

| Token de User-Agent | Versión actual | Propósito y política de entrenamiento de modelos | URL del manifiesto de IP |
| --- | --- | --- | --- |
| `GPTBot` | `GPTBot/1.4` | Rastrea contenido potencialmente utilizado para entrenar modelos fundacionales de IA generativa de OpenAI. Evita muros de pago, fuentes con gran cantidad de información personal identificable (PII) y contenido que infrinja las políticas.[1] | `https://openai.com/gptbot.json` (18 prefijos IPv4 a fecha de 2026-09-22) [2] |
| `OAI-SearchBot` | `OAI-SearchBot/1.4` | Indexa sitios web para mostrar enlaces y resúmenes en las funciones de búsqueda de ChatGPT. **No** se utiliza para entrenar modelos fundacionales de OpenAI.[1] | `https://openai.com/searchbot.json` (39 prefijos IPv4 a fecha de 2026-01-02) [3] |
| `OAI-AdsBot` | `OAI-AdsBot/1.0` | Inspecciona las páginas de destino de anunciantes para verificar su calidad, seguridad y cumplimiento de políticas. **No** se utiliza para entrenar modelos fundacionales.[1] | Publicado mediante la documentación de rastreadores de OpenAI [1] |
| `ChatGPT-User` | `ChatGPT-User/1.0` | Se activa en nombre de un usuario humano en tiempo real que solicita a ChatGPT o a un Custom GPT obtener una página web específica. **No** se utiliza para el entrenamiento pasivo de modelos fundacionales.[1] | `https://openai.com/chatgpt-user.json` (actualizado el 2026-11-06) [4] |

La cabecera HTTP `User-Agent` completa enviada por GPTBot a finales de 2026 es `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; GPTBot/1.4; +https://openai.com/gptbot)`.[1]

## Exclusión mediante robots.txt y control de acceso granular

GPTBot cumple con el Protocolo de exclusión de robots estandarizado en **IETF RFC 9309**.[1][5] Los administradores de sitios web pueden bloquear a GPTBot para que no extraiga datos de todo un dominio, o restringirlo a rutas de directorio específicas, añadiendo reglas `User-agent: GPTBot` al archivo `/robots.txt` de su sitio.[1][5]

Dado que OpenAI desacopla los rastreos de entrenamiento de la indexación de búsqueda, un editor que desee excluirse del entrenamiento de modelos de IA pero seguir apareciendo como enlace citado en ChatGPT Search puede desautorizar a `GPTBot` mientras permite explícitamente a `OAI-SearchBot`:[1]

```text User-agent: GPTBot Disallow: /

User-agent: OAI-SearchBot Allow: / ```

OpenAI señala que, tras actualizar las reglas de `robots.txt` de un sitio, la flota distribuida de rastreadores de OpenAI puede tardar aproximadamente 24 horas en actualizar su política de `robots.txt` en caché y cesar las solicitudes.[1]

## Verificación de IP y autenticación criptográfica de bots web

Debido a que rastreadores de terceros suplantan habitualmente la cadena User-Agent de `GPTBot` en las cabeceras HTTP, depender únicamente de la cabecera `User-Agent` resulta insuficiente para la aplicación de reglas de cortafuegos o la analítica.[1][8] OpenAI publica manifiestos JSON de prefijos legibles por máquina para que los operadores de red y las redes de entrega de contenido (CDN) puedan verificar el tráfico auténtico en la capa IP:[1][2][3][4] - **`gptbot.json`**: contiene 18 bloques CIDR IPv4 (como `20.171.206.0/24`, `52.230.152.0/24`, `20.168.17.192/28`, `172.182.202.0/25`, `172.182.204.0/24` y `172.182.214.0/24`) según la marca de tiempo de creación `2026-09-22T00:00:00Z`.[2] - **`searchbot.json`**: contiene 39 bloques CIDR IPv4 a fecha de `2026-01-02T07:01:00.000000Z`.[3] - **`chatgpt-user.json`**: contiene decenas de bloques CIDR IPv4 regionales de salida actualizados a fecha de `2026-11-06T00:00:00Z`.[4]

Más allá de las listas de IP permitidas, proveedores de seguridad en el borde como Cloudflare y el **Grupo de Trabajo IETF Web Bot Auth (`webbotauth`)** han introducido firmas criptográficas de mensajes HTTP (basadas en RFC 9421) para agentes automatizados.[7][8] Mediante la autenticación criptográfica de bots, los rastreadores verificados y los agentes de IA adjuntan las cabeceras `Signature` y `Signature-Input` firmadas con un directorio público de claves Ed25519 o RSA, lo que permite a los servidores de origen y a los WAF verificar matemáticamente la identidad del bot sin depender de consultas frágiles de rangos de IP.[7][8]

## Preferencias de IA del IETF (aipref) e impacto en el ecosistema web

La rápida expansión de los rastreadores de entrenamiento de IA generó un importante debate sobre si `robots.txt` (diseñado originalmente en 1994 para evitar que los rastreadores de búsqueda sobrecargaran los servidores a cambio de tráfico de búsqueda recíproco) es adecuado para expresar políticas de derechos de autor y de uso para aprendizaje automático.[5][6]

Para abordar esta carencia, se constituyó el **Grupo de Trabajo IETF AI Preferences (`aipref`)** con el fin de estandarizar un vocabulario legible por máquina y mecanismos de adjunción que expresen cómo los sistemas de IA pueden o no utilizar contenido digital.[6] Las especificaciones activas del grupo de trabajo, incluidas `draft-ietf-aipref-vocab` (A Vocabulary For Expressing AI Usage Preferences) y `draft-ietf-aipref-attach` (mecanismos para adjuntar preferencias mediante extensiones de `robots.txt` y cabeceras HTTP `Content-Usage`), distinguen entre el procesamiento automatizado general, el entrenamiento de modelos fundacionales (`train-ai` / `ai`) y la búsqueda o fundamentación en inferencia.[6] Mientras tanto, la telemetría de red de los informes de tráfico de IA de Cloudflare indica que `GPTBot` se sitúa sistemáticamente entre los rastreadores de IA con mayor volumen a nivel mundial junto con Bytespider, ClaudeBot y Google-Extended, lo que impulsa la adopción generalizada de controles gestionados de rastreo de IA y arquitecturas de pago por rastreo.[8]

## Preguntas frecuentes

### ¿Cuál es la diferencia entre GPTBot y OAI-SearchBot?

GPTBot (GPTBot/1.4) rastrea páginas web públicas para recopilar datos de entrenamiento para los modelos fundacionales de IA generativa de OpenAI. OAI-SearchBot (OAI-SearchBot/1.4) rastrea sitios web únicamente para indexarlos y enlazarlos dentro de las funciones de búsqueda de ChatGPT y no se utiliza para entrenar los modelos fundacionales de OpenAI. [1]

### ¿Cómo puede un sitio web bloquear a GPTBot sin perder visibilidad en ChatGPT Search?

Un administrador de sitio puede añadir 'User-agent: GPTBot' seguido de 'Disallow: /' en el archivo raíz /robots.txt mientras añade 'User-agent: OAI-SearchBot' seguido de 'Allow: /'. Esto impide que OpenAI extraiga datos del sitio para el entrenamiento de modelos y permite que las páginas se indexen y se citen en las respuestas de búsqueda de ChatGPT. [1][5]

### ¿Cómo pueden verificar los administradores de servidores que una solicitud de GPTBot procede genuinamente de OpenAI?

Los administradores deben cotejar la dirección IP de origen de la solicitud con los bloques CIDR oficiales publicados por OpenAI en https://openai.com/gptbot.json (que enumera 18 prefijos IPv4 a fecha de septiembre de 2026), o utilizar comprobaciones de bots verificados de CDN y firmas de mensajes HTTP estandarizadas bajo el marco IETF Web Bot Auth. [1][2][7][8]

### ¿Qué es ChatGPT-User y por qué se comporta de manera diferente a GPTBot?

ChatGPT-User (ChatGPT-User/1.0) se invoca cuando un usuario humano solicita activamente a ChatGPT o a una acción de Custom GPT que visite una URL específica en tiempo real. Sus IP de salida se publican por separado en https://openai.com/chatgpt-user.json y sus solicitudes no se utilizan para el entrenamiento pasivo de modelos fundacionales. [1][4]

### ¿Qué estándares del IETF rigen a los rastreadores web de IA como GPTBot?

El cumplimiento de robots.txt por parte de GPTBot se rige por IETF RFC 9309 (Protocolo de exclusión de robots). Además, el Grupo de Trabajo IETF AI Preferences (aipref) desarrolla vocabularios estandarizados (draft-ietf-aipref-vocab) y reglas de adjunción HTTP/robots para expresar exclusiones de entrenamiento de IA, mientras que el Grupo de Trabajo IETF Web Bot Auth (webbotauth) estandariza la autenticación criptográfica de bots. [5][6][7]

## Frases citables

- OpenAI separa su tráfico web en cuatro agentes de usuario distintos: GPTBot/1.4 (entrenamiento de modelos), OAI-SearchBot/1.4 (indexación de búsqueda), OAI-AdsBot/1.0 (verificación de páginas de destino publicitarias) y ChatGPT-User/1.0 (solicitudes iniciadas por usuarios). [1]
- El manifiesto oficial de IP de OpenAI para GPTBot (https://openai.com/gptbot.json) enumera 18 prefijos CIDR IPv4 a fecha de su actualización del 22 de septiembre de 2026. [2]
- El manifiesto oficial de IP de OpenAI para OAI-SearchBot (https://openai.com/searchbot.json) enumera 39 prefijos CIDR IPv4 a fecha de su actualización del 2 de enero de 2026. [3]
- Desautorizar a GPTBot en robots.txt impide que OpenAI rastree un sitio para el entrenamiento de modelos fundacionales, mientras que permitir a OAI-SearchBot preserva la indexación en los resultados de búsqueda de ChatGPT. [1][5]
- El Grupo de Trabajo IETF AI Preferences (aipref) desarrolla draft-ietf-aipref-vocab y draft-ietf-aipref-attach para estandarizar preferencias legibles por máquina sobre el entrenamiento y uso de IA. [6]

## Cronología

- 2022-09: El IETF publica el RFC 9309, estandarizando formalmente el Protocolo de exclusión de robots (robots.txt). [5]
- 2023-08: OpenAI lanza GPTBot con controles de exclusión mediante robots.txt y rangos de IP de salida publicados. [1]
- 2024-07: OpenAI introduce OAI-SearchBot para separar la indexación de búsqueda de los rastreos de entrenamiento de modelos fundacionales de GPTBot. [1]
- 2026-01-02: OpenAI actualiza searchbot.json a 39 bloques CIDR IPv4 para OAI-SearchBot. [3]
- 2026-09-22: OpenAI actualiza gptbot.json a 18 prefijos CIDR IPv4 a medida que GPTBot avanza a la versión de agente de usuario GPTBot/1.4. [1][2]
- 2026-11-06: OpenAI actualiza los rangos IPv4 de salida de chatgpt-user.json para acciones de navegación de ChatGPT iniciadas por usuarios en tiempo real. [4]

## Fuentes

1. Overview of OpenAI Crawlers (GPTBot/1.4, OAI-SearchBot/1.4, OAI-AdsBot/1.0, ChatGPT-User/1.0). OpenAI Platform Documentation. https://platform.openai.com/docs/bots (consultado 2026-11-23; tier 3: official site)
2. OpenAI GPTBot Official IPv4 CIDR Prefix Manifest (gptbot.json). OpenAI. publicado 2026-09-22. https://openai.com/gptbot.json (consultado 2026-11-23; tier 3: official site)
3. OpenAI OAI-SearchBot Official IPv4 CIDR Prefix Manifest (searchbot.json). OpenAI. publicado 2026-01-02. https://openai.com/searchbot.json (consultado 2026-11-23; tier 3: official site)
4. OpenAI ChatGPT-User Official IPv4 CIDR Prefix Manifest (chatgpt-user.json). OpenAI. publicado 2026-11-06. https://openai.com/chatgpt-user.json (consultado 2026-11-23; tier 3: official site)
5. RFC 9309: Robots Exclusion Protocol. Internet Engineering Task Force (IETF). publicado 2022-09. https://www.rfc-editor.org/rfc/rfc9309 (consultado 2026-11-23; tier 1: government or public registry)
6. IETF AI Preferences (aipref) Working Group Charter and Active Drafts (draft-ietf-aipref-vocab, draft-ietf-aipref-attach). Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/aipref/about/ (consultado 2026-11-23; tier 1: government or public registry)
7. IETF Web Bot Auth (webbotauth) Working Group Charter. Internet Engineering Task Force (IETF). https://datatracker.ietf.org/wg/webbotauth/about/ (consultado 2026-11-23; tier 1: government or public registry)
8. From Googlebot to GPTBot: Who's Crawling Your Site and Cryptographic Bot Verification. Cloudflare. publicado 2025-05. https://blog.cloudflare.com/from-googlebot-to-gptbot-whos-crawling-your-site-in-2025/ (consultado 2026-11-23; tier 2: academic or news)

## Citar esta página

Mimirwiki. "GPTBot." Versión 7fde1535, 2026-11-24. https://mimirwiki.com/es/wiki/gptbot
