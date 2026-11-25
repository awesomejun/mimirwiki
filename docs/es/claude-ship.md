---
title: "Claude Ship"
subtitle: "Conjunto de agentes de Anthropic para revisar, corregir y aprobar pull requests en GitHub"
canonical_url: https://mimirwiki.com/es/wiki/claude-ship
language: es
page_class: entity
revision_sha256: 64cc942d1e6bf6ddf4dad362f7f417cb07662a1008cde64e0497f4fcb62e1f31
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/claude-ship.md
  txt: https://mimirwiki.com/es/wiki/claude-ship.txt
  json: https://mimirwiki.com/es/wiki/claude-ship.json
  jsonld: https://mimirwiki.com/es/wiki/claude-ship.jsonld
translations:
  en: https://mimirwiki.com/wiki/claude-ship
  ko: https://mimirwiki.com/ko/wiki/claude-ship
  ja: https://mimirwiki.com/ja/wiki/claude-ship
  zh: https://mimirwiki.com/zh/wiki/claude-ship
---

# Claude Ship

> Claude Ship es el conjunto de tres agentes de Anthropic para pull requests de GitHub en los planes Claude Team y Enterprise: Code Review (disponible de forma general), PR Steward (en beta pública) y Claude Approvals (en beta pública). Anunciado el 23 de noviembre de 2026, automatiza los hallazgos de revisión de código, los commits de corrección y las comprobaciones de aprobación basadas en políticas, dejando la aplicación de las fusiones en manos de la configuración del repositorio y las reglas de GitHub.

Claude Ship es un conjunto de agentes de IA desarrollados por Anthropic para revisar, enviar correcciones y evaluar políticas de aprobación en pull requests de GitHub. Anunciado el 23 de noviembre de 2026, Claude Ship agrupa tres agentes: Code Review (disponible de forma general desde el 15 de octubre de 2026), PR Steward (en beta pública) y Claude Approvals (en beta pública). Claude Ship está disponible para los planes Claude Team y Enterprise y opera junto con la configuración del repositorio y los controles de protección de ramas o conjuntos de reglas de GitHub.

**También conocido como:** agentes de Claude Ship, /ship

## Datos clave

- **Desarrollador:** Anthropic [1]
- **Fecha de anuncio:** 2026-11-23 [1]
- **Estado de los componentes:** Code Review: disponible de forma general; PR Steward y Claude Approvals: beta pública (al 2026-11-24) [1]
- **Planes elegibles:** Planes Claude Team y Enterprise en GitHub (al 2026-11-24) [4]

## Datos básicos

- **Desarrollador:** Anthropic [1]
- **Anunciado:** 2026-11-23 [1]
- **Componentes:** Code Review, PR Steward, Claude Approvals [4]
- **Estado de Code Review:** Disponible de forma general (desde el 15 de octubre de 2026; vista previa de investigación el 9 de marzo de 2026) (al 2026-11-24) [3]
- **Estado de PR Steward:** Beta pública (al 2026-11-24) [5]
- **Estado de Claude Approvals:** Beta pública (al 2026-11-24) [6]
- **Plataforma:** GitHub (github.com; compatible con GitHub Enterprise Server para Code Review y PR Steward) (al 2026-11-24) [5]
- **Planes:** Claude Team y Enterprise (al 2026-11-24) [4]
- **Modelo de facturación:** Facturación por uso basada en tokens; Claude Approvals no tiene tarifa base, pero los clasificadores de políticas y las ejecuciones de Code Review activadas se facturan por tokens (al 2026-11-24) [1]
- **Punto de entrada CLI:** Comando /ship en Claude Code [4]

## Descripción general e historial de lanzamientos de Claude Ship

Claude Ship es un conjunto de agentes de [Anthropic](https://mimirwiki.com/es/wiki/anthropic) diseñado para hacer avanzar las pull requests de GitHub a través de la revisión, las correcciones y las comprobaciones de aprobación basadas en políticas.[1][4] Anthropic anunció Claude Ship el 23 de noviembre de 2026, combinando su producto existente Code Review con dos nuevos agentes en beta pública: PR Steward y Claude Approvals.[1] Los medios tecnológicos independientes TechCrunch y The Verge informaron del lanzamiento ese mismo día.[11][12]

Code Review es anterior al lanzamiento más amplio de Claude Ship: Anthropic presentó Code Review en vista previa de investigación para organizaciones Team y Enterprise el 9 de marzo de 2026 y anunció su disponibilidad general el 15 de octubre de 2026.[2][3] Al 24 de noviembre de 2026, Code Review está disponible de forma general, mientras que PR Steward y Claude Approvals permanecen en beta pública sin una fecha anunciada de disponibilidad general.[1][5][6] Los desarrolladores también pueden invocar `/ship` en Claude Code en pull requests individuales para subir cambios, abrir una pull request, ejecutar una revisión y atender comentarios y comprobaciones fallidas.[1][4]

## Agentes de Claude Ship y flujo de trabajo de pull requests

Claude Ship divide la gestión de pull requests entre tres agentes que pueden ejecutarse automáticamente en los repositorios configurados.[1][4]

- **Code Review** inspecciona una pull request en relación con el código base circundante mediante varios agentes en paralelo, verifica los hallazgos para filtrar falsos positivos, clasifica los problemas por gravedad y publica un comentario general junto con comentarios en línea sobre las líneas afectadas.[2][4] Los administradores pueden seleccionar los niveles de revisión `Quick`, `Standard` (predeterminado) o `Deep` por repositorio.[3] Anthropic indicó en el anuncio de disponibilidad general que la mayoría de las revisiones finalizaban en un plazo de 6 a 10 minutos, en comparación con aproximadamente 20 minutos durante la vista previa de investigación.[2][3] En el equipo de Claude Code, Anthropic informó que las pull requests fusionadas aumentaron a más del doble entre junio y septiembre de 2026, mientras que la proporción de reversiones se redujo en más de un 40 %.[1]
- **PR Steward** supervisa las pull requests abiertas en una sesión en la nube y envía commits para resolver comprobaciones de CI fallidas causadas por el código modificado, conflictos de fusión, comentarios de revisión de personas o herramientas de revisión como Code Review y la comprobación de Claude Approvals.[1][5] Tras cada envío, PR Steward publica un comentario que describe lo que cambió y cómo deshacerlo.[1] Los desarrolladores pueden dirigir a PR Steward comentando `@claude` con instrucciones, o detenerlo comentando `@claude stop` o eliminando la etiqueta `claude-pr-steward-watching`.[1][5] De forma predeterminada, PR Steward omite las pull requests en borrador, las pull requests procedentes de forks, las pull requests abiertas por bots y los autores sin permisos de escritura.[5] La documentación del producto establece que PR Steward está diseñado para no aprobar ni fusionar pull requests.[4][5]
- **Claude Approvals** evalúa las pull requests según un archivo de políticas del repositorio almacenado en `.claude/approvals.yml` y añade una comprobación de estado `Claude Approvals` que informa quién debe aprobar todavía.[6] Las reglas de política pueden especificar patrones de rutas de archivos, cupos de aprobación humana requeridos, si Claude solo comenta o puede emitir una revisión aprobatoria y condiciones basadas en datos de la pull request o en clasificadores de lenguaje natural.[1][6] Las condiciones no pueden leer los resultados de CI, por lo que las comprobaciones de CI deben mantenerse como comprobaciones requeridas independientes en GitHub.[6] Anthropic recomienda iniciar las políticas en modo `observe`, donde la comprobación informa qué decidiría la política sin bloquear las fusiones.[1][6]

## Claude Ship y controles de fusión en GitHub

Claude Ship depende de la configuración del repositorio y de los controles de gobernanza de GitHub para determinar qué cambios pueden fusionarse realmente.[4] Anthropic señala en su documentación que Claude Ship utiliza IA y puede pasar por alto errores, vulnerabilidades de seguridad u otros problemas, y recomienda a las organizaciones utilizar la protección de ramas para exigir las aprobaciones deseadas antes de fusionar.[4]

En Claude Approvals, la comprobación bloquea una fusión únicamente cuando está configurada como comprobación requerida en GitHub, y normalmente no lo hace mientras se encuentra en modo observe.[4][6] La documentación también advierte que una pull request puede fusionarse sin la revisión de otra persona si la comprobación no es obligatoria, si una regla permite que el autor ocupe el único cupo (`seats: 1`) o establece `seats: 0`, si GitHub contabiliza la revisión aprobatoria de Claude como la única aprobación requerida, o si una regla permite que Claude apruebe sin exigir primero que Code Review se supere con éxito.[6] Además, añadir un archivo de políticas `.claude/approvals.yml` detiene las ejecuciones automáticas de Code Review en los archivos cubiertos, a menos que una regla incluya explícitamente `claude/code_review`.[6]

Por parte de GitHub, la aplicación de las fusiones funciona mediante funciones de la plataforma como las colas de fusión de pull requests (disponibles de forma general desde el 12 de julio de 2023), las reglas de revisores requeridos para conjuntos de reglas de repositorio (disponibles de forma general desde el 17 de febrero de 2026, compatibles con aprobaciones de equipos y patrones de negación de rutas `!`) y la migración automática de las reglas clásicas de protección de ramas a conjuntos de reglas de repositorio (lanzada el 11 de agosto de 2026).[8][9][10]

## Disponibilidad, configuración y facturación de Claude Ship

Claude Ship está disponible en los planes Claude Team y Enterprise para repositorios de GitHub al 24 de noviembre de 2026.[1][4] Un propietario (Owner) de la organización en Claude activa Code Review y PR Steward en Organization settings > Claude Ship en claude.ai, conecta una cuenta de GitHub y vincula la Claude GitHub App instalada por un propietario de la organización de GitHub; las revisiones se ejecutan en la infraestructura de Anthropic sin añadir archivos de flujo de trabajo a los repositorios.[5][7] Claude Approvals se activa una vez que se cumplen los requisitos previos y alguien con permiso de fusión añade `.claude/approvals.yml` a la rama predeterminada, aunque un propietario de la organización de Claude puede desactivar Approvals en toda la organización.[1][6]

| Agente | Estado (al 24 de noviembre de 2026) | Entorno de GitHub | Exclusiones de cumplimiento |
| --- | --- | --- | --- |
| Code Review | Disponible de forma general | github.com y GitHub Enterprise Server | Zero Data Retention, configuración HIPAA, CMEK |
| PR Steward | Beta pública | github.com y GitHub Enterprise Server (puerto 443) | Zero Data Retention, configuración HIPAA, CMEK |
| Claude Approvals | Beta pública | github.com (incluido GitHub Enterprise Cloud) | Zero Data Retention, configuración HIPAA, CMEK; no puede iniciarse con FERPA ni Access Transparency |

El uso de Code Review y PR Steward se factura según tokens, y los administradores pueden configurar límites de gasto mensuales.[1][5] Claude Approvals no conlleva una tarifa base, pero se aplican cargos por tokens para las evaluaciones de clasificadores y las ejecuciones de Code Review activadas por una política, incluso en modo observe.[1][6] Ejecutar `/ship` localmente en Claude Code cuenta como uso habitual de Claude Code.[1] En el anuncio del 23 de noviembre de 2026, Anthropic declaró que las organizaciones elegibles de Claude Enterprise podían reclamar al menos 10 000 USD en créditos de Claude Ship hasta el 15 de enero de 2027, válidos durante 30 días después de reclamarlos.[1]

## Preguntas frecuentes

### ¿Cuáles son los tres agentes de Claude Ship?

Claude Ship está compuesto por Code Review (disponible de forma general), PR Steward (en beta pública) y Claude Approvals (en beta pública). Code Review publica hallazgos ordenados por gravedad, PR Steward envía commits de corrección para comprobaciones fallidas, conflictos y comentarios de revisión, y Claude Approvals evalúa las pull requests frente a un archivo de políticas del repositorio. [1][4]

### ¿Puede PR Steward aprobar o fusionar una pull request de GitHub?

No. La documentación de Anthropic indica que PR Steward está diseñado para no aprobar ni fusionar pull requests, y que los equipos deben apoyarse en la protección de ramas o en los conjuntos de reglas de GitHub para exigir las aprobaciones necesarias antes de la fusión. [4][5]

### ¿Cómo funciona el modo observe de Claude Approvals?

En modo observe, la comprobación de Claude Approvals se ejecuta en las pull requests y muestra qué decidiría la política definida en .claude/approvals.yml sin imponer un bloqueo de fusión. La facturación por tokens sigue aplicándose a las ejecuciones de clasificadores y a las revisiones de Code Review activadas por la política mientras está en modo observe. [1][6]

### ¿Qué organizaciones no pueden utilizar Claude Ship?

Al 24 de noviembre de 2026, Claude Ship no está disponible para organizaciones con Zero Data Retention habilitado, la configuración HIPAA aplicada o claves de cifrado gestionadas por el cliente (CMEK). Además, Claude Approvals no puede iniciarse en organizaciones con configuraciones de FERPA o Access Transparency. [1][6]

## Frases citables

- Anthropic anunció Claude Ship el 23 de noviembre de 2026 para los planes Claude Team y Enterprise en GitHub. [1]
- Code Review entró en vista previa de investigación el 9 de marzo de 2026 y alcanzó la disponibilidad general el 15 de octubre de 2026. [2][3]
- Al 24 de noviembre de 2026, PR Steward y Claude Approvals se encuentran en beta pública. [5][6]
- PR Steward está diseñado para no aprobar ni fusionar pull requests. [4][5]
- Claude Approvals lee las reglas de un archivo de políticas .claude/approvals.yml en el repositorio y no puede leer resultados de CI dentro de las condiciones de las reglas. [6]
- El uso de Claude Ship se factura por tokens, incluidas las evaluaciones de clasificadores y las ejecuciones de Code Review activadas por políticas en modo observe. [1][6]

## Cronología

- 2026-03-09: Anthropic presenta Code Review para Claude Code en vista previa de investigación para organizaciones Team y Enterprise. [2]
- 2026-10-15: Anthropic anuncia la disponibilidad general de Code Review con los niveles de revisión de repositorio Quick, Standard y Deep. [3]
- 2026-11-23: Anthropic anuncia Claude Ship, agrupando Code Review (disponible de forma general) con PR Steward y Claude Approvals en beta pública. [1]

## Fuentes

1. Introducing Claude Ship. Anthropic. publicado 2026-11-23. https://claude.com/resources/articles/introducing-claude-ship (consultado 2026-11-24; tier 3: official site)
2. Bringing Code Review to Claude Code. Anthropic. publicado 2026-03-09. https://claude.com/resources/articles/code-review (consultado 2026-11-24; tier 3: official site)
3. Code Review is now generally available. Anthropic. publicado 2026-10-15. https://claude.com/resources/articles/code-review-is-now-generally-available (consultado 2026-11-24; tier 3: official site)
4. Claude Ship - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/claude-ship (consultado 2026-11-24; tier 3: official site)
5. PR Steward - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/pr-steward (consultado 2026-11-24; tier 3: official site)
6. Claude Approvals - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/approvals (consultado 2026-11-24; tier 3: official site)
7. Set up Code Review - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/code-review-setup (consultado 2026-11-24; tier 3: official site)
8. Required reviewer rule is now generally available. GitHub. publicado 2026-02-17. https://github.blog/changelog/2026-02-17-required-reviewer-rule-is-now-generally-available/ (consultado 2026-11-24; tier 3: official site)
9. Automatically migrate branch protection rules to repository rulesets. GitHub. publicado 2026-08-11. https://github.blog/changelog/2026-08-11-automatically-migrate-branch-protection-rules-to-repository-rulesets/ (consultado 2026-11-24; tier 3: official site)
10. Pull request merge queue is now generally available!. GitHub. publicado 2023-07-12. https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/ (consultado 2026-11-24; tier 3: official site)
11. Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes. TechCrunch. publicado 2026-11-23. https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/ (consultado 2026-11-24; tier 2: academic or news)
12. Claude AI can review pull requests and ship fixes on its own now. The Verge. publicado 2026-11-23. https://www.theverge.com/ai-artificial-intelligence/1040134/anthropic-claude-ship-ai-pull-requests (consultado 2026-11-24; tier 2: academic or news)

## Citar esta página

Mimirwiki. "Claude Ship." Versión 64cc942d, 2026-11-24. https://mimirwiki.com/es/wiki/claude-ship
