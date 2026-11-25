---
title: "Schema.org"
subtitle: "Vocabulario compartido de datos estructurados para el marcado de páginas web destinado a motores de búsqueda y otras aplicaciones"
canonical_url: https://mimirwiki.com/es/wiki/schema-org
language: es
page_class: anchor
revision_sha256: 10fa59e050dc601147583f80403b207534dcd885efc2a90be7c24a756a94aabf
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/schema-org.md
  txt: https://mimirwiki.com/es/wiki/schema-org.txt
  json: https://mimirwiki.com/es/wiki/schema-org.json
  jsonld: https://mimirwiki.com/es/wiki/schema-org.jsonld
translations:
  en: https://mimirwiki.com/wiki/schema-org
  ko: https://mimirwiki.com/ko/wiki/schema-org
  ja: https://mimirwiki.com/ja/wiki/schema-org
  zh: https://mimirwiki.com/zh/wiki/schema-org
---

# Schema.org

> Schema.org es un vocabulario compartido de datos estructurados fundado en 2011 por Google, Microsoft, Yahoo y Yandex para describir entidades como productos, recetas, eventos y organizaciones en páginas web. Los editores lo codifican con JSON-LD, Microdatos o RDFa. A partir de la versión 30.1 (2026-09-16), el vocabulario define 826 tipos y 1540 propiedades bajo CC BY-SA 3.0.

Schema.org es un vocabulario colaborativo de tipos y propiedades utilizado para incrustar datos estructurados en páginas web para motores de búsqueda y otras aplicaciones. Fundado en 2011 por Google, Microsoft, Yahoo y Yandex, el proyecto mantiene una jerarquía compartida de herencia múltiple derivada de RDF Schema y publica su representación canónica legible por máquina en RDF/Turtle. Los editores web codifican términos de Schema.org en páginas HTML usando JSON-LD, Microdatos o RDFa y, a partir de la versión 30.1 (publicada el 2026-09-16), el vocabulario define 826 tipos, 1540 propiedades, 19 tipos de datos, 96 enumeraciones y 544 miembros de enumeración. La evolución diaria se coordina mediante el Grupo Comunitario de Schema.org del W3C (W3C Schema.org Community Group) y su repositorio público en GitHub, mientras que un Grupo Directivo (Steering Group) aprueba las versiones formales.

**También conocido como:** schema.org, Vocabulario Schema.org, Marcado Schema

## Datos clave

- **Fundación:** 2011 (Google, Microsoft, Yahoo, Yandex) [4]
- **Última versión:** Versión 30.1 (2026-09-16) (al 2026-11-23) [2]
- **Tamaño del vocabulario:** 826 tipos, 1540 propiedades, 19 tipos de datos, 96 enumeraciones, 544 miembros de enumeración (al 2026-11-23) [3]
- **Codificaciones compatibles:** JSON-LD, Microdatos, RDFa [5]
- **Licencia del esquema:** Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0) [6]

## Datos básicos

- **Tipo:** Vocabulario compartido de datos estructurados para la Web [1]
- **Fundación:** 2011 [4]
- **Empresas fundadoras:** Google, Microsoft, Yahoo, Yandex [1]
- **Gobernanza:** Grupo Directivo de Schema.org y Grupo Comunitario de Schema.org del W3C [1]
- **Presidente del Grupo Directivo:** R.V. Guha (al 2026-11-23) [1]
- **Grupo Comunitario:** W3C Schema.org Community Group (510 participantes; lanzado el 2015-03-31) (al 2026-11-23) [7]
- **Última versión:** Versión 30.1 (2026-09-16) (al 2026-11-23) [2]
- **Tamaño del vocabulario:** 826 tipos, 1540 propiedades, 19 tipos de datos, 96 enumeraciones, 544 miembros de enumeración (al 2026-11-23) [3]
- **Representación canónica:** RDF/Turtle [4]
- **Formatos de marcado:** JSON-LD, Microdatos, RDFa [5]
- **Licencias:** CC BY-SA 3.0 (esquemas, documentación, ejemplos); Apache-2.0 (software del sitio) [6]
- **Repositorio:** github.com/schemaorg/schemaorg (5741 commits, 6,3k estrellas) (al 2026-11-23) [8]

## Qué es Schema.org

Schema.org es una actividad colaborativa y comunitaria que crea, mantiene y promueve esquemas para datos estructurados en Internet.[1] Google, Microsoft, Yahoo y Yandex fundaron Schema.org en 2011 como un esfuerzo conjunto en el espíritu de los [sitemaps](https://mimirwiki.com/es/wiki/sitemaps) (`sitemaps.org`) para que los administradores web pudieran adoptar un vocabulario de marcado compartido comprendido por los principales motores de búsqueda.[4][6] El nombre de dominio `schema.org` fue aportado por el proyecto OpenDomain.[6]

Los elementos HTML estándar indican a los navegadores cómo representar el contenido de una página, por ejemplo al dar formato a un encabezado con un elemento `h1`, pero dejan ambiguo el tipo de entidad subyacente.[5] Schema.org añade etiquetas explícitas legibles por máquina para entidades como películas, personas, organizaciones, productos y eventos, de modo que los motores de búsqueda y otros programas puedan interpretar el contenido de la página de manera coherente entre distintos sitios, reduciendo la dependencia de la extracción automatizada propensa a errores.[5][6] Muchos términos iniciales se inspiraron en iniciativas anteriores como Microformats, FOAF y OpenCyc.[6]

Schema.org funciona como una iniciativa colaborativa que documenta los esquemas admitidos por los motores de búsqueda participantes, al margen de organismos formales de estandarización como el W3C o el IETF.[6] Las páginas web escritas en cualquier idioma humano pueden incluir marcado de Schema.org, aunque los propios términos del vocabulario y la documentación del sitio de Schema.org están escritos en inglés.[6] Junto con protocolos como Open Graph de Facebook, Schema.org ofrece un marcado granular para describir múltiples entidades y componentes distintos dentro de una misma página web.[6]

## Modelo de datos y estructura del vocabulario de Schema.org

Schema.org utiliza un modelo de datos genérico derivado de RDF Schema, que a su vez deriva de CycL.[4] Sus esquemas están organizados como una jerarquía de tipos con herencia múltiple en la que cada tipo puede heredar propiedades de varios tipos padres.[4] El tipo raíz más amplio es `Thing`, que proporciona propiedades fundamentales como `name`, `description`, `url` e `image`, mientras que los tipos más específicos heredan de padres más generales; por ejemplo, `LocalBusiness` es un subtipo tanto de `Place` como de `Organization`.[5]

Las propiedades en Schema.org pueden tener múltiples dominios (`domainIncludes`) y múltiples rangos (`rangeIncludes`), una decisión de diseño pragmática que evita crear tipos intermedios artificiales únicamente para agrupar propiedades.[4] Mediante tipos de metanivel como `Class` y `Property`, el esquema admite la reflexión y puede representar sus propias definiciones.[4] La representación canónica legible por máquina de Schema.org se publica en RDF/Turtle, con formatos adicionales legibles por máquina como RDF y [JSON-LD](https://mimirwiki.com/es/wiki/json-ld) disponibles en la página de documentación para desarrolladores.[3][4]

A partir de la versión 30.1, publicada el 2026-09-16 (consultada el 2026-11-23), Schema.org define los siguientes componentes de vocabulario.[2][3]

| Componente | Cantidad (Versión 30.1, a fecha de 2026-11-23) |
| --- | --- |
| Tipos | 826 |
| Propiedades | 1540 |
| Tipos de datos | 19 |
| Enumeraciones | 96 |
| Miembros de enumeración | 544 |

Entre los grupos de tipos de Schema.org más utilizados se encuentran las obras creativas (`CreativeWork`, `Book`, `Movie`, `MusicRecording`, `Recipe`, `TVSeries`), los objetos multimedia incrustados (`AudioObject`, `ImageObject`, `VideoObject`), `Event`, las entidades médicas y de salud (`MedicalEntity`), `Organization`, `Person`, `Place` (`LocalBusiness`, `Restaurant`), `Product` y `Offer` (`AggregateOffer`), `Review` y `AggregateRating`, y `Action`, junto con tipos de datos primitivos para valores como texto y números.[3] Las propiedades generales de enlace incluyen `mainEntity` y `mainEntityOfPage`, que identifican la entidad principal descrita por una página, junto con `url`, `sameAs` y `about`.[4]

Schema.org sigue un modelo de conformidad pragmático basado en la ley de Postel, tratando las asociaciones de tipos y propiedades como directrices.[4] Una misma descripción de entidad puede combinar propiedades de varios tipos independientes, como `Book` y `Product`, y los editores suelen proporcionar cadenas de texto plano o URL donde se esperan tipos de entidad estructurados; tipos como `Role` y `URL` pueden usarse con cualquier propiedad.[4][5] Cualquier propiedad puede contener múltiples valores, que representan un conjunto no ordenado por defecto según las tripletas RDF.[4] Cuando se requiere orden o semántica de colección, los editores pueden utilizar listas RDF (`rdf:List`, expresadas con `@list` en JSON-LD) o contenedores RDF (`rdf:Seq`, `rdf:Bag`, `rdf:Alt`), aplicándose el rango esperado de la propiedad a los elementos individuales de la colección en los analizadores que los admiten.[4]

Schema.org agrupa áreas especializadas en secciones alojadas (`auto`, `bib`, `health-lifesci`, `meta` y `pending`) que actúan como vistas sobre una única colección de definiciones.[3] Los términos en debate activo residen en `pending` y pueden cambiar antes de alcanzar consenso, `meta` contiene vocabulario interno para definiciones técnicas y funcionalidad del sitio, y `attic` archiva términos obsoletos o no aceptados cuyo uso se desaconseja a los editores.[3] A diferencia de los términos del núcleo, `pending`, `meta` y `attic` pueden actualizarse sin necesidad de una versión completa.[3] Extensiones externas independientes, como GS1 Web Vocabulary y Croissant (un vocabulario comunitario de metadatos para conjuntos de datos de aprendizaje automático), amplían Schema.org sin aprobación oficial del Grupo Directivo.[3]

## Codificaciones e identificadores de términos de Schema.org

Los términos de Schema.org pueden incrustarse en páginas web mediante tres formatos principales de serialización: [JSON-LD](https://mimirwiki.com/es/wiki/json-ld), Microdatos y RDFa.[4][5][6] Schema.org dio inicialmente prioridad a Microdatos como opción pragmática al lanzarse el proyecto y posteriormente amplió su documentación y ejemplos a RDFa y JSON-LD, señalando que tareas como combinar vocabularios o invertir relaciones de propiedades resultan más difíciles en Microdatos.[6]

| Formato | Mecanismo de codificación | Especificación y notas |
| --- | --- | --- |
| JSON-LD | Objeto JSON incrustado en elementos HTML `script` con `type="application/ld+json"`, utilizando `@context` y `@type` | Recomendación del W3C (`JSON-LD 1.1` publicada el 2020-07-16, en sustitución de `JSON-LD 1.0` del 2014-01-16); 100 % compatible con JSON (RFC 8259) e interoperable con grafos RDF |
| Microdatos | Atributos HTML5 en línea `itemscope`, `itemtype` e `itemprop` en elementos de contenido, anidando nuevos bloques `itemscope` para elementos incrustados | Introducido con HTML5; los tipos de elemento se indican mediante URL de Schema.org como `https://schema.org/Movie` |
| RDFa (RDFa Lite) | Atributos HTML en línea `vocab="https://schema.org/"`, `typeof` y `property` en elementos de contenido | Se corresponde de forma casi isomórfica con Microdatos (`itemprop` pasa a ser `property`, `itemtype` pasa a ser `typeof` y se omite `itemscope`) |

La tabla anterior resume los detalles de codificación documentados en las especificaciones de Schema.org, Google Search Central y el W3C.[4][5][9][10] En el marcado HTML, Schema.org también documenta patrones de desambiguación legibles por máquina: elementos HTML `time` con atributos `datetime` con formato `YYYY-MM-DD` (opcionalmente seguidos de `T` y `hh:mm` o `hh:mm:ss`) para fechas y horas, elementos HTML `link` con `href` para enumeraciones y referencias canónicas, y elementos HTML `meta` con `content` para valores implícitos.[5]

Schema.org se lanzó en un sitio web `http:` con identificadores de términos RDF que empleaban URL `http://schema.org/` antes de migrar posteriormente su sitio web público y sus ejemplos preferidos de documentación a `https://schema.org/`.[7] La documentación de Schema.org indica que tanto `https://schema.org` como `http://schema.org` siguen siendo válidos y ampliamente comprendidos en el marcado de datos estructurados.[7] Tras pasar al alojamiento de archivos estáticos, Schema.org sustituyó la negociación de contenido HTTP para su contexto JSON-LD remoto por una cabecera HTTP `Link` que apunta a `/docs/jsonldcontext.jsonld` con `rel="alternate"` y `type="application/ld+json"`.[7] Dado que ese documento de contexto conserva `http:` como URL base para que los analizadores RDF existentes en todo el mundo no modifiquen de forma silenciosa las tripletas emitidas, Dan Brickley señaló el 2026-10-30 que los analizadores JSON-LD siguen emitiendo tripletas `http://` incluso cuando el marcado hace referencia a `https://schema.org`, y recomendó a los consumidores de datos canonizar los identificadores al agregar datos de Schema.org.[7]

## Gobernanza, repositorio y licencias de Schema.org

Schema.org se gobierna mediante una estructura de dos niveles compuesta por un Grupo Directivo (Steering Group) y el Grupo Comunitario de Schema.org del W3C (W3C Schema.org Community Group).[1] El Grupo Directivo ejerce la supervisión de alto nivel, gestiona las decisiones operativas y aprueba las versiones formales.[1] El cofundador R.V. Guha, quien inició Schema.org en Google, preside el Grupo Directivo a título individual (a fecha de 2026-11-23), junto con representantes de las empresas fundadoras Google, Microsoft, Yahoo y Yandex, un representante del W3C y colaboradores destacados de la comunidad.[1] En abril de 2015, el Grupo Directivo amplió por unanimidad su composición para incorporar a Stéphane Corlosquet, Martin Hepp (autor de GoodRelations) y un puesto para el W3C.[1] Los debates del Grupo Directivo son públicos, con actas de reuniones publicadas en GitHub y enlazadas desde el issue #1.[1]

El Grupo Comunitario de Schema.org del W3C fue propuesto por Dan Brickley y lanzado el 2015-03-31, convirtiéndose en abril de 2015 en el principal foro público para el debate diario sobre el esquema, la preparación de propuestas y la revisión de extensiones.[1][7] La participación está abierta a cualquier persona con una cuenta del W3C que firme el Acuerdo de Licencia de Colaborador Comunitario del W3C (W3C Community Contributor License Agreement), y el W3C señala que alojar el grupo no implica el respaldo de los miembros ni del personal del W3C.[1][7] A fecha de 2026-11-23, el Grupo Comunitario cuenta con 510 participantes y seis presidentes registrados: Dan Brickley, Dan Scott, Stéphane Corlosquet, Phil Barker, Phil Archer y Ryan Levering.[7] Dan Brickley también dirige las operaciones diarias y actúa como webmaster del proyecto, presidiendo el Grupo Comunitario en nombre de Schema.org de forma independiente a su papel como representante de Google en el Grupo Directivo.[1] Los debates se llevan a cabo en la lista de correo `public-schemaorg@w3.org` y en GitHub, mientras que grupos comunitarios relacionados del W3C coordinan trabajos sectoriales en áreas como salud y medicina, deportes, archivos, bibliografía y automoción.[1][7]

Schema.org mantiene sus esquemas (`data`), documentación (`docs`), plantillas, `versions.json` y el software del sitio (`software`, importado en parte desde el submódulo `sdopythonapp`) en el repositorio público de GitHub `github.com/schemaorg/schemaorg`.[8] A fecha de 2026-11-23, el repositorio registra 5741 commits, 6,3k estrellas, 975 bifurcaciones, 388 observadores, 301 incidencias abiertas y 14 solicitudes de extracción abiertas.[8] El issue #1 funciona como índice de planificación de versiones, los issues #2 y #3 organizan el trabajo de vocabulario y herramientas, las pruebas de integración continua verifican las solicitudes de extracción y los borradores de versiones se preparan en `staging.schema.org`.[1][2][8] Las directrices de contribución del proyecto dan prioridad a correcciones y adiciones incrementales respaldadas por aplicaciones consumidoras reales, incluidas herramientas de analítica web, complementos de navegador y herramientas en la nube además de motores de búsqueda, haciendo hincapié en la usabilidad local y en la alineación con estándares externos como GoodRelations, GS1, IPTC rNews, MARC, BibFrame, FRBR, BBC, la Unión Europea de Radiodifusión, Music Ontology y MusicBrainz.[8]

Schema.org publica sus definiciones de esquemas, documentación del sitio, contenido del blog y ejemplos de marcado bajo la licencia Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0).[6] El software de soporte utilizado para ejecutar el sitio de Schema.org se publica bajo la licencia de código abierto Apache-2.0.[6][8]

## Historial de versiones de Schema.org

Schema.org publica versiones formales numeradas tras la revisión del Grupo Directivo y de la comunidad en general, con un resumen de la versión actual alojado en `https://schema.org/version/latest`.[2][8] A fecha de 2026-11-23, la última versión publicada es la versión 30.1, emitida el 2026-09-16.[2]

La versión 30.1 (2026-09-16) introdujo vocabulario para facilitar el descubrimiento de los Pasaportes Digitales de Productos de la UE (EU Digital Product Passports), añadiendo la clase `DigitalProductPassport`, `hasDigitalProductPassport`, `EnvironmentalProductDeclaration` y `DeclarationOfConformity` (como subtipos de `Certification`), así como las propiedades de producto `authorizedRepresentative`, `importer`, `recycledContentPercentage` y `substanceOfConcern`.[2] La misma versión incorporó propiedades para catálogos minoristas, entre ellas `consumerNotice`, `isOftenBoughtWith`, `specification`, `valueGroup`, `itemPopularity`, `minimumOrderValue` y el valor de enumeración `MaximumRetailPrice`, documentó el soporte explícito para listas ordenadas, actualizó las estadísticas de uso de términos, añadió `Ophthalmology` y `Audiology` a `MedicalSpecialty` y promovió términos adoptados de `pending` a disponibilidad general.[2]

Las principales versiones recientes anteriores a la versión 30.1 incluyen los siguientes hitos.[2]

| Versión | Fecha de lanzamiento | Adiciones y cambios destacados |
| --- | --- | --- |
| 30.1 | 2026-09-16 | Tipos y propiedades del Pasaporte Digital de Productos de la UE, vocabulario de catálogos minoristas, documentación de listas ordenadas, promociones de pending a disponibilidad general |
| 30.0 | 2026-03-19 | Anotaciones y exportaciones de equivalencia con GS1, Dublin Core y Open Graph; ejemplos del Pasaporte Digital de Productos de la UE alineados con UN/CEFACT; clases `Credential` y `Error`; `Quantity` movida para heredar de `DataType` |
| 29.4 | 2025-12-08 | `ConferenceEvent`, `PerformingArtsEvent`, `InstantaneousEvent`, acciones de autenticación (`AuthenticateAction`, `LoginAction`, `ResetPasswordAction`), `OperatingSystem`, `RuntimePlatform`, `SequentialArt` (dejando obsoleta `GraphicNovel`), equivalencias OWL para UN/CEFACT, OWL, OMG y GS1 |
| 29.3 | 2025-09-04 | Rango ampliado de `recipeIngredient`; incorporación de `OnlineMarketplace` y `hasStore` / `isStoreOn` |
| 29.0 | 2025-03-24 | Vocabulario `FinancialIncentive`, propiedades del Identificador Europeo de Legislación (ELI) en `Legislation`, tipos de envío revisados (`ShippingConditions`, `ShippingService`, dejando obsoleta `DeliveryTimeSettings`) |
| 28.0 | 2024-09-17 | Tipos para programas de fidelización y membresía (`MemberProgram`, `MemberProgramTier`, `TierBenefitEnumeration`) |
| 27.02 | 2024-07-01 | Migración del sitio editorial de pruebas de `webschemas.org` a `staging.schema.org` |
| 27.01 | 2024-06-24 | Rediseño del sitio de Schema.org |
| 27.0 | 2024-05-20 | Incorporación de `hasGS1DigitalLink` y `certificationRating` |

Las versiones de corrección 29.1 (2025-04-25) y 29.2 (2025-05-13) resolvieron regresiones introducidas en la versión 29.0 y añadieron propiedades y tipos como `pronouns`, `companyRegistration`, `Cooperative` y `referee`.[2] Los términos en `pending`, `meta` y `attic` también pueden actualizarse entre versiones completas.[3]

## Uso de Schema.org en motores de búsqueda y límites

El marcado de Schema.org es utilizado por motores de búsqueda como Google, Microsoft, Yahoo y Yandex para interpretar entidades de páginas web y alimentar resultados enriquecidos de búsqueda.[5][6][9] Google Search Central documenta funciones de datos estructurados que cubren tipos de contenido como Artículo, Ruta de exploración (Breadcrumb), Lista de cursos, Conjunto de datos, Foro de debate, Evento, Verificación de hechos, Metadatos de imagen, Oferta de empleo, Negocio local, Organización, Fragmento de producto, Ficha de comerciante, Página de perfil, Preguntas y respuestas (Q&A), Receta, Fragmento de reseña, Aplicación de software, Contenido pronunciable (Speakable), Contenido por suscripción y de pago, Alquiler vacacional y Video.[9] En las páginas de recetas, por ejemplo, los datos estructurados etiquetan ingredientes, calorías y tiempos de cocción para que la Búsqueda de Google pueda mostrar resultados enriquecidos y admitir el filtrado por atributos.[9] Sistemas de gestión de contenidos como Wix, WordPress y Shopify ofrecen ajustes integrados o complementos para añadir datos estructurados sin editar HTML directamente.[9]

Los editores pueden verificar la sintaxis y la estructura con dos herramientas principales de validación documentadas en las fuentes: el Validador de marcado de Schema.org (Schema.org Markup Validator), que comprueba las estructuras de Schema.org y señala las colecciones RDF (`List`, `Bag`, `Seq`, `Alt`), y la Prueba de resultados enriquecidos de Google (Rich Results Test), que valida los datos estructurados y previsualiza las funciones aptas para la Búsqueda de Google.[4][9]

La documentación de Schema.org y de los motores de búsqueda identifica varios límites y condiciones prácticas en el uso de datos estructurados:

- **Visualización selectiva de funciones**: Las preguntas frecuentes de Schema.org señalan que los motores de búsqueda no muestran todos los tipos de información definidos en Schema.org, por lo que los editores deben consultar la documentación de cada motor de búsqueda para conocer las funciones específicas admitidas.[6]
- **Requisito de contenido visible**: Tanto las directrices de Schema.org como Google Search Central indican a los editores que marquen únicamente el contenido visible para los usuarios en la página, evitando páginas en blanco creadas solo para alojar datos estructurados y evitando el marcado oculto incluso cuando los datos subyacentes sean exactos.[5][6][9]
- **Marcado opcional y parcial**: Marcar todas las propiedades de un elemento es opcional; cuando no existe un subtipo exacto, los editores pueden dejar el contenido sin marcar, utilizar un tipo padre más amplio como `Person` o definir una extensión.[6]
- **Alcance ontológico acotado**: Schema.org simplifica el contenido web para una publicación práctica y deja las ontologías de dominio exhaustivas en manos de vocabularios independientes y extensiones externas.[4][8]
- **Heterogeneidad de analizadores e identificadores**: Schema.org no exige que todos los analizadores implementen colecciones o contenedores RDF, y el corpus web mezcla identificadores `http://` y `https://` entre Microdatos, RDFa y JSON-LD, lo que obliga a los consumidores de datos a gestionar la canonización y los valores abreviados en cadenas de texto.[4][7]

## Preguntas frecuentes

### ¿Qué es Schema.org?

Schema.org es un vocabulario colaborativo de tipos y propiedades utilizado para añadir datos estructurados legibles por máquina a las páginas web. Google, Microsoft, Yahoo y Yandex fundaron la iniciativa en 2011 para que los sitios web pudieran utilizar un único vocabulario de marcado compartido entre los principales motores de búsqueda y otras aplicaciones. [1][4]

### ¿Es Schema.org un organismo formal de estandarización como el W3C?

No. Schema.org se describe a sí mismo como un esfuerzo colaborativo que documenta esquemas compatibles con los principales motores de búsqueda, independiente de organismos formales de estandarización como el W3C o el IETF. El W3C aloja el Grupo Comunitario de Schema.org como foro público de debate, y dicho alojamiento no implica el respaldo de los miembros ni del personal del W3C. [6][7]

### ¿Qué formatos de marcado pueden utilizarse con Schema.org?

Los editores pueden codificar los términos de Schema.org en páginas web mediante JSON-LD, Microdatos o RDFa (incluido RDFa Lite). La representación canónica legible por máquina del propio vocabulario de Schema.org se publica en RDF/Turtle. [4][5][6]

### ¿Qué tamaño tiene el vocabulario de Schema.org?

A partir de la versión 30.1, publicada el 2026-09-16 (consultada el 2026-11-23), el vocabulario de Schema.org contiene 826 tipos, 1540 propiedades, 19 tipos de datos, 96 enumeraciones y 544 miembros de enumeración. También incluye secciones alojadas como pending para términos en revisión y un archivo attic para términos obsoletos. [2][3]

### ¿Bajo qué licencias se publican los vocabularios y el software de Schema.org?

Los esquemas de Schema.org, la documentación del sitio, el contenido del blog y los ejemplos de marcado se publican bajo la licencia Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0). El software de soporte empleado para publicar el sitio se distribuye bajo la licencia de código abierto Apache-2.0. [6][8]

### ¿Se muestra cada tipo de Schema.org en los resultados de los motores de búsqueda?

No. Según las preguntas frecuentes de Schema.org, los motores de búsqueda no muestran todos los tipos de información definidos en el vocabulario, y cada motor documenta qué funciones y tipos admite. Google Search Central también indica que los datos estructurados de una página deben describir contenido visible para los visitantes en esa misma página. [6][9]

## Frases citables

- Schema.org fue fundado en 2011 por Google, Microsoft, Yahoo y Yandex para ofrecer un vocabulario compartido de datos estructurados para páginas web. [1][4]
- El Grupo Comunitario de Schema.org del W3C (W3C Schema.org Community Group) fue propuesto y lanzado el 2015-03-31 como foro público para debatir cambios y extensiones de Schema.org. [7]
- A fecha de 2026-11-23, la última versión publicada de Schema.org es la versión 30.1, lanzada el 2026-09-16. [2]
- A fecha de 2026-11-23, el vocabulario de Schema.org consta de 826 tipos, 1540 propiedades, 19 tipos de datos, 96 enumeraciones y 544 miembros de enumeración. [3]
- El marcado de Schema.org puede codificarse en páginas web mediante JSON-LD, Microdatos o RDFa, mientras que la representación canónica legible por máquina del esquema se encuentra en RDF/Turtle. [4][5]
- Los esquemas de Schema.org, la documentación del sitio, el contenido del blog y los ejemplos de marcado se distribuyen bajo la licencia Creative Commons Attribution-ShareAlike 3.0 (CC BY-SA 3.0), mientras que el software de soporte del sitio utiliza la licencia Apache-2.0. [6][8]
- JSON-LD 1.1 fue publicado como Recomendación del W3C el 2020-07-16, sustituyendo a la Recomendación JSON-LD 1.0 del 2014-01-16. [10]
- La documentación de Google Search Central establece que los datos estructurados de una página deben describir contenido visible para los usuarios en dicha página. [9]

## Cronología

- 2011: Google, Microsoft, Yahoo y Yandex lanzan Schema.org para ofrecer un vocabulario compartido de datos estructurados para páginas web. [4][8]
- 2014-01-16: El W3C publica JSON-LD 1.0 como Recomendación del W3C. [10]
- 2015-03-31: Dan Brickley propone y lanza el Grupo Comunitario de Schema.org del W3C (W3C Schema.org Community Group). [7]
- 2015-04: El Grupo Directivo de Schema.org se amplía para incluir a los colaboradores de la comunidad Stéphane Corlosquet y Martin Hepp, además de un representante del W3C, y el Grupo Comunitario del W3C se convierte en el principal foro de colaboración. [1]
- 2020-07-16: El W3C publica JSON-LD 1.1 como Recomendación del W3C, sustituyendo a JSON-LD 1.0. [10]
- 2024-07-01: Schema.org lanza la versión 27.02 y migra su sitio editorial de pruebas de webschemas.org a staging.schema.org. [2]
- 2025-03-24: Schema.org lanza la versión 29.0 con nuevo vocabulario para incentivos financieros, propiedades del Identificador Europeo de Legislación (ELI) y esquemas de envío revisados. [2]
- 2026-03-19: Schema.org lanza la versión 30.0, añadiendo anotaciones de equivalencia para GS1, Dublin Core y Open Graph junto con ejemplos del Pasaporte Digital de Productos de la UE. [2]
- 2026-09-16: Schema.org lanza la versión 30.1, añadiendo tipos del Pasaporte Digital de Productos de la UE, propiedades para catálogos minoristas y documentación explícita para listas ordenadas. [2]

## Fuentes

1. About - Schema.org. Schema.org. https://schema.org/docs/about.html (consultado 2026-11-23; tier 3: official site)
2. Release listing - schema.org. Schema.org. publicado 2026-09-16. https://schema.org/docs/releases.html (consultado 2026-11-23; tier 3: official site)
3. Schemas - Schema.org. Schema.org. https://schema.org/docs/schemas.html (consultado 2026-11-23; tier 3: official site)
4. Data model - Schema.org. Schema.org. https://schema.org/docs/datamodel.html (consultado 2026-11-23; tier 3: official site)
5. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (consultado 2026-11-23; tier 3: official site)
6. FAQ - schema.org. Schema.org. https://schema.org/docs/faq.html (consultado 2026-11-23; tier 3: official site)
7. Schema.org Community Group. World Wide Web Consortium (W3C). https://www.w3.org/community/schemaorg/ (consultado 2026-11-23; tier 1: government or public registry)
8. GitHub - schemaorg/schemaorg: Schema.org - schemas and supporting software · GitHub. Schema.org (GitHub). https://github.com/schemaorg/schemaorg (consultado 2026-11-23; tier 3: official site)
9. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (consultado 2026-11-23; tier 3: official site)
10. JSON-LD 1.1. World Wide Web Consortium (W3C). publicado 2020-07-16. https://www.w3.org/TR/json-ld11/ (consultado 2026-11-23; tier 1: government or public registry)

## Citar esta página

Mimirwiki. "Schema.org." Versión 10fa59e0, 2026-11-24. https://mimirwiki.com/es/wiki/schema-org
