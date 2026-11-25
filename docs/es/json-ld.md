---
title: "JSON-LD"
subtitle: "Formato estándar del W3C para serializar datos enlazados (Linked Data) en JSON"
canonical_url: https://mimirwiki.com/es/wiki/json-ld
language: es
page_class: anchor
revision_sha256: 356d821f94f69aa9410de37da004ccf1a50e9dc7581cc031f0c8bb6adca1f0dc
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 10
alternates:
  md: https://mimirwiki.com/es/wiki/json-ld.md
  txt: https://mimirwiki.com/es/wiki/json-ld.txt
  json: https://mimirwiki.com/es/wiki/json-ld.json
  jsonld: https://mimirwiki.com/es/wiki/json-ld.jsonld
translations:
  en: https://mimirwiki.com/wiki/json-ld
  ko: https://mimirwiki.com/ko/wiki/json-ld
  ja: https://mimirwiki.com/ja/wiki/json-ld
  zh: https://mimirwiki.com/zh/wiki/json-ld
---

# JSON-LD

> JSON-LD es una Recomendación del W3C para serializar datos enlazados (Linked Data) en JSON válido. Asocia las claves de los objetos a identificadores globales mediante un contexto para que las aplicaciones puedan interpretar y conectar datos entre distintos sitios web. Estandarizado en 2014 y actualizado a la versión 1.1 en 2020, JSON-LD admite grafos RDF, transformaciones programáticas y datos estructurados en HTML como Schema.org.

JSON-LD (JSON for Linking Data) es una Recomendación del World Wide Web Consortium (W3C) que define una sintaxis ligera basada en JSON para serializar datos enlazados (Linked Data) en la Web. Todo documento JSON-LD es JSON válido conforme a RFC 8259, lo que permite que los analizadores JSON estándar, los servicios web y los motores de almacenamiento basados en JSON lo procesen mientras añade identificadores globales de recursos, contextos, etiquetas de idioma, tipos de datos y grafos dirigidos. El W3C publicó JSON-LD 1.0 el 2014-01-16 y lo reemplazó por el conjunto de especificaciones JSON-LD 1.1 el 2020-07-16, que abarca sintaxis, algoritmos y API de procesamiento, y framing. Las aplicaciones utilizan JSON-LD directamente como JSON, lo convierten hacia y desde grafos y conjuntos de datos del Resource Description Framework (RDF), o lo incrustan en documentos HTML para vocabularios de datos estructurados como Schema.org.

**También conocido como:** JSON for Linked Data, JSON for Linking Data, JSON para datos enlazados, JSON-LD 1.0, JSON-LD 1.1

## Datos clave

- **Organismo de estandarización:** World Wide Web Consortium (W3C) [1]
- **Primera Recomendación del W3C:** JSON-LD 1.0 (2014-01-16) [4]
- **Recomendación actual del W3C:** JSON-LD 1.1 (2020-07-16) (al 2026-11-23) [1]
- **Sintaxis base:** JSON (RFC 8259) [1]
- **Tipo de script HTML:** application/ld+json [8]

## Datos básicos

- **Tipo:** Formato de serialización basado en JSON para datos enlazados (Linked Data) [1]
- **Organismo de estandarización:** World Wide Web Consortium (W3C) [1]
- **Grupo responsable:** W3C JSON-LD Working Group (estatuto vigente hasta enero de 2028) (al 2026-11-23) [7]
- **Primera Recomendación:** JSON-LD 1.0 (2014-01-16; reemplazada el 2020-11-03) [4]
- **Recomendación actual:** JSON-LD 1.1 (2020-07-16) (al 2026-11-23) [1]
- **Recomendaciones 1.1 complementarias:** Processing Algorithms and API; Framing [1]
- **Editores de la versión 1.1:** Gregg Kellogg, Pierre-Antoine Champin, Dave Longley [1]
- **Editores de la versión 1.0:** Manu Sporny, Gregg Kellogg, Markus Lanthaler [4]
- **Formato base:** JSON (IETF RFC 8259) [5]
- **Compatibilidad con modelos de datos:** Grafos RDF 1.1 y conjuntos de datos RDF [6]
- **Repositorio de la especificación:** github.com/w3c/json-ld-syntax [10]

## Qué es JSON-LD

JSON-LD (JSON for Linking Data) es una sintaxis ligera estandarizada por el World Wide Web Consortium (W3C) para serializar datos enlazados (Linked Data) en JSON.[1][7] Los datos enlazados conectan información legible por máquina entre documentos y sitios web para que una aplicación pueda seguir enlaces incrustados desde un conjunto de datos hacia recursos relacionados alojados en otros sitios.[1][7] JSON-LD está diseñado para entornos de programación basados en la Web, servicios web REST interoperables y motores de almacenamiento basados en JSON como Apache CouchDB y MongoDB.[1][7]

Todo documento JSON-LD es JSON válido según lo definido por IETF RFC 8259 (que dejó obsoletos a RFC 7159 y al anterior RFC 4627), de modo que los analizadores y bibliotecas JSON existentes pueden analizar documentos JSON-LD directamente.[1][4][5] JSON-LD 1.0 hacía referencia originalmente a RFC 4627, mientras que JSON-LD 1.1 actualizó la referencia base de JSON a RFC 8259.[1][4] Más allá de los tipos primitivos del JSON estándar (cadenas de texto, números, booleanos y `null`) y sus tipos estructurados (objetos y arreglos), JSON-LD incorpora identificadores universales de objetos mediante IRI, correspondencia entre términos e IRI mediante contextos, referencias a recursos entre distintos sitios, anotaciones de idioma para cadenas de texto, tipos de datos para valores como fechas y horas, y representaciones de grafos dirigidos.[1][5]

La especificación JSON-LD 1.0 enumeraba seis objetivos de diseño: simplicidad, compatibilidad, expresividad, concisión, modificaciones mínimas para sistemas JSON existentes y utilidad como RDF.[4] En un uso básico, JSON-LD requiere familiaridad con JSON y dos palabras clave, `@context` y `@id`, sin necesidad de procesadores dedicados de JSON-LD.[4] En API JSON ya desplegadas, los servidores también pueden asociar documentos JSON existentes a un contexto JSON-LD mediante una relación de enlace en la respuesta HTTP, de modo que las cargas útiles JSON existentes puedan interpretarse como JSON-LD con cambios mínimos.[1][4]

## Sintaxis, contextos y palabras clave de JSON-LD

JSON-LD se construye sobre objetos y arreglos JSON e introduce reglas estructurales específicas y palabras clave reservadas con el prefijo `@`.[1] En JSON-LD, los nombres de miembros dentro de un objeto JSON deben ser únicos, mientras que RFC 8259 solo especifica que los nombres de objetos JSON deberían ser únicos.[1][5] En JSON común, los arreglos son secuencias ordenadas de valores; en JSON-LD, las colecciones de arreglos son desordenadas por defecto, salvo que se definan explícitamente como listas.[1][5]

La sintaxis central de JSON-LD gira en torno a contextos y palabras clave que otorgan a los datos JSON un significado inequívoco a escala web.[1][4]

- `@context`: Asocia términos breves de propiedades en un documento JSON a IRI completos para que las claves compartidas entre distintos documentos JSON posean definiciones claras e inequívocas. Un contexto puede referenciarse mediante una URL (como `https://schema.org/` o `https://json-ld.org/contexts/person.jsonld`), y asignar `null` a un término o a su `@id` dentro de un contexto desvincula explícitamente ese término de un IRI.[1][7][8]
- `@id`: Asigna un identificador universal, expresado como un IRI, a un objeto nodo para que otros objetos o documentos externos puedan hacer referencia al mismo recurso.[1][4][7]
- `@type`: Especifica el tipo de un objeto nodo (como `Recipe` o `Person` en el marcado de Schema.org) o asocia un tipo de datos a un valor tipado, y también puede combinarse con `@set`.[1][8]
- `null`: Restablece o ignora valores en el cuerpo de un documento y desvincula asignaciones de términos dentro de `@context`.[1]

JSON-LD 1.1 es un superconjunto de JSON-LD 1.0 que mantiene la compatibilidad con los documentos 1.0 salvo donde se indique lo contrario.[1] Su especificación documenta un modo de procesamiento JSON-LD 1.1, vocabularios por defecto, IRI base, IRI compactos, alias de palabras clave, contextos con alcance definido (scoped contexts), propagación de contextos, contextos importados, definiciones protegidas de términos, literales JSON, coerción de tipos, internacionalización de cadenas con dirección base, propiedades anidadas, propiedades inversas, nodos incluidos, múltiples formas de valores indexados (indexación por datos, por propiedad, por idioma, por identificador de nodo y por tipo de nodo) y grafos nombrados con contenedores de grafos.[1]

## Formas de documento, API de procesamiento y framing de JSON-LD

JSON-LD representa grafos dirigidos, lo que significa que una misma información subyacente puede serializarse con múltiples formas.[1][3] Para permitir un procesamiento programático determinista, el conjunto de especificaciones JSON-LD 1.1 define cuatro formas de documento: expandida (Expanded), compactada (Compacted), aplanada (Flattened) y enmarcada (Framed).[1]

La Recomendación complementaria del W3C, JSON-LD 1.1 Processing Algorithms and API, define algoritmos para transformar documentos entre formas y convertir datos hacia y desde RDF, junto con una interfaz de programación de aplicaciones (API) `JsonLdProcessor` y un tipo de configuración `JsonLdOptions` descritos mediante Web IDL.[2] Sus capacidades principales de procesamiento incluyen el procesamiento de contextos (creación de definiciones de términos, creación de contextos inversos y selección de términos), expansión (expansión de IRI y valores), compactación (compactación de IRI y valores), aplanamiento (generación y fusión de mapas de nodos y asignación de identificadores de nodos anónimos), recuperación de documentos y contextos remotos, algoritmos de contenido HTML y serialización y deserialización RDF con preservación de datos de ida y vuelta (round-tripping).[2]

Una tercera Recomendación del W3C, JSON-LD 1.1 Framing, amplía `JsonLdProcessor` y `JsonLdOptions` para permitir a los desarrolladores realizar consultas por ejemplo y aplicar una estructura de árbol específica sobre un grafo JSON-LD.[3] Los grafos de datos enlazados constan de enunciados independientes (tripletas), mientras que las aplicaciones suelen esperar árboles anidados de objetos JSON; un marco (frame) especifica cómo se agrupan los enunciados sobre cada sujeto dentro de delimitadores `{` y `}` y cómo se anidan los sujetos relacionados.[3] La especificación Framing admite coincidencias por propiedades, comodines, propiedades ausentes, valores y `@id`, así como marcos vacíos, contenido por defecto, framing inverso, framing de grafos nombrados y cinco indicadores de framing: incrustación de objetos (object embed), inclusión explícita (explicit inclusion), omisión de valores por defecto (omit default), omisión de grafos (omit graph) y requerir todo (require all).[3]

## JSON-LD y el modelo de datos RDF

JSON-LD está diseñado tanto para desarrolladores que trabajan directamente con JSON sin conocimientos del Resource Description Framework (RDF) como para sistemas que operan sobre datos RDF.[1][4] La Recomendación del W3C RDF 1.1 Concepts and Abstract Syntax, publicada el 2014-02-25, incluye explícitamente a JSON-LD junto con Turtle como sintaxis de serialización para almacenar e intercambiar datos RDF, vinculándolo con RDF Schema y el lenguaje de consulta SPARQL.[6]

En la sintaxis abstracta de RDF 1.1, la información se organiza en grafos RDF, que son conjuntos de tripletas sujeto-predicado-objeto cuyos nodos pueden ser IRI, literales (valores tipados o cadenas con etiqueta de idioma) o nodos anónimos (blank nodes), y en conjuntos de datos RDF, que agrupan un grafo por defecto junto con cero o más grafos nombrados.[6] Los IRI tienen alcance global en RDF, lo que implica que distintas apariciones del mismo IRI denotan el mismo recurso y pueden servir como puntos de partida desreferenciables en la Web.[6]

JSON-LD 1.1 y su especificación Processing Algorithms and API definen algoritmos deterministas para deserializar documentos JSON-LD en conjuntos de datos RDF y serializar conjuntos de datos RDF de vuelta a JSON-LD, funcionando junto a formatos como Turtle y TriG.[1][2] Para admitir las funciones de JSON-LD 1.1 dentro de RDF, la especificación de sintaxis define el tipo de datos `rdf:JSON`, el espacio de nombres `i18n` y la clase `rdf:CompoundLiteral` junto con las propiedades `rdf:language` y `rdf:direction`.[1] La especificación JSON-LD 1.1 también documenta cómo se relaciona JSON-LD con otros formatos de datos enlazados y marcado estructurado, incluidos Turtle, RDFa y Microdata, y JSON-LD 1.0 lo comparaba además con Microformats.[1][4]

## JSON-LD en HTML, Schema.org y motores de búsqueda

Los documentos JSON-LD pueden incrustarse directamente dentro de páginas HTML, una función definida tanto en JSON-LD 1.0 como en JSON-LD 1.1.[1][4] La especificación JSON-LD 1.1 aborda la incrustación de JSON-LD en elementos HTML `script`, la herencia del IRI base a partir del elemento `base` de un documento HTML, las restricciones de contenido para los elementos `script` de JSON-LD y la localización de un elemento `script` JSON-LD específico.[1] Las especificaciones también incluyen apéndices de consideraciones de la IANA, y la guía de datos estructurados de Google Search Central muestra la incrustación en HTML mediante un elemento `script` con `type="application/ld+json"` ubicado en el `head` del documento.[1][4][8]

En la Web pública, JSON-LD se combina con [Schema.org](https://mimirwiki.com/es/wiki/schema-org), un vocabulario compartido para marcar entidades en páginas web de modo que los principales motores de búsqueda (Google, Microsoft, Yandex y Yahoo!) puedan interpretar el significado de las páginas.[9] Schema.org admite tres formatos de marcado, a saber, Microdata, RDFa y JSON-LD, y publica la mayoría de los ejemplos de su sitio en los tres formatos.[9] Su jerarquía de tipos parte de `Thing` (con las propiedades `name`, `description`, `url` e `image`) y se ramifica en subtipos como `CreativeWork` (que incluye `Book`, `Movie`, `MusicRecording`, `Recipe` y `TVSeries`), `Event`, `Organization`, `Person`, `Place`, `LocalBusiness`, `Product` y `Review`.[9]

Google Search Central documenta cómo Google Search lee datos estructurados JSON-LD incluidos en la página, como un objeto `Recipe` de Schema.org que hace referencia a un autor `Person` anidado, para clasificar el contenido de la página, recopilar información de entidades sobre personas, libros o empresas y mostrar resultados enriquecidos.[8] Tanto Schema.org como Google Search Central especifican que los datos estructurados deben describir contenido visible para los usuarios en esa página, desaconsejando la creación de páginas vacías destinadas únicamente a alojar marcado o marcado correspondiente a contenido oculto.[8][9] Los propietarios de sitios que utilizan sistemas de gestión de contenidos como Wix, WordPress o Shopify pueden configurar los datos estructurados mediante ajustes de la plataforma o complementos, y los desarrolladores pueden validar el marcado y previsualizar las funciones de búsqueda elegibles con la Prueba de resultados enriquecidos (Rich Results Test) de Google.[8]

## Versiones, gobernanza e implementaciones de JSON-LD

JSON-LD se originó en el JSON for Linking Data Community Group antes de transferirse al W3C RDF Working Group, que publicó JSON-LD 1.0 y JSON-LD 1.0 Processing Algorithms and API como Recomendaciones del W3C el 2014-01-16 (editadas por Manu Sporny, Gregg Kellogg y Markus Lanthaler, con Dave Longley y Niklas Lindström como coautores).[2][4] El trabajo sobre JSON-LD 1.1 pasó luego al W3C JSON-LD Working Group, a partir del Informe Final del JSON-LD Community Group.[1] Tras las versiones candidatas (Candidate Releases) del 2019-12-12 y las Recomendaciones Propuestas (Proposed Recommendations) del 2020-05-07, el Grupo de Trabajo publicó tres Recomendaciones del W3C el 2020-07-16, editadas por Gregg Kellogg, Pierre-Antoine Champin y Dave Longley.[1][2][3] El W3C marcó formalmente JSON-LD 1.0 como Recomendación reemplazada (Superseded Recommendation) el 2020-11-03, dirigiendo las nuevas implementaciones hacia JSON-LD 1.1 mientras mantiene los compromisos de licencia de la Política de Patentes del W3C para la especificación 1.0.[4]

| Especificación | Fecha de publicación | Alcance | Repositorio |
| --- | --- | --- | --- |
| JSON-LD 1.1 | 2020-07-16 | Sintaxis de datos enlazados, contextos, palabras clave, incrustación en HTML, correspondencia con RDF | `w3c/json-ld-syntax` |
| JSON-LD 1.1 Processing Algorithms and API | 2020-07-16 | Expansión, compactación, aplanamiento, conversión a RDF, API `JsonLdProcessor` | `w3c/json-ld-api` |
| JSON-LD 1.1 Framing | 2020-07-16 | Coincidencia de grafos mediante consulta por ejemplo y estructura de árbol determinista | `w3c/json-ld-framing` |

Las tres especificaciones conforman el conjunto oficial de Recomendaciones JSON-LD 1.1 producido por el W3C JSON-LD Working Group.[1][2][3][10]

Al 2026-11-23, el W3C JSON-LD Working Group mantiene la gobernanza formal de las especificaciones bajo un estatuto vigente hasta enero de 2028, mientras que el abierto JSON-LD Community Group coordina borradores comunitarios, reuniones de debate y listas de correo.[7] En el repositorio público `w3c/json-ld-syntax` en GitHub, el Grupo de Trabajo señala que los borradores de JSON-LD 1.1 tienen sus características congeladas, lo que limita las incidencias del repositorio a informes de errores, aclaraciones de características existentes y correcciones editoriales.[10]

Al 2026-11-23, json-ld.org aloja la herramienta web JSON-LD Playground para depurar y visualizar marcado, realiza el seguimiento de la conformidad mediante conjuntos oficiales de pruebas y un informe de implementación, y enumera bibliotecas conformes con JSON-LD 1.1 en JavaScript (`json-ld.js`, `jsonld-streaming-parser.js`, `jsonld-streaming-serializer.js`, `rdf-parse.js`), Python (`PyLD`, `RDFLib`, `TRLD`), Ruby (`JSON-LD for RDF.rb`), Go (`JSON-goLD`), Java (`Titanium`), C# (`dotNetRDF`), Erlang y Elixir (`JSON-LD.ex`), Rust (`sophia`, `oxjsonld`) y herramientas de línea de comandos (`jsonld-cli`, `ld-cli`), junto con implementaciones de JSON-LD 1.0 en PHP (`php-json-ld`, `JsonLD`), Java (`JSONLD-JAVA`) y C# (`json-ld.net`).[7] Los borradores comunitarios amplían el modelo de datos de JSON-LD a especificaciones relacionadas, entre ellas YAML-LD para la redacción legible por humanos en YAML, CBOR-LD para la serialización binaria comprimida en usos con restricciones de espacio como códigos QR, códigos de barras PDF417 y etiquetas NFC, así como borradores de Streaming y JSON-LD-star.[7]

## Preguntas frecuentes

### ¿Qué es JSON-LD?

JSON-LD (JSON for Linking Data) es una Recomendación del W3C que define una sintaxis ligera basada en JSON para serializar datos enlazados (Linked Data) en la Web. Todo documento JSON-LD es JSON válido conforme a RFC 8259, al tiempo que añade contextos, identificadores IRI globales, tipos de datos, anotaciones de idioma y estructuras de grafos dirigidos. [1][5][7]

### ¿Qué hacen @context, @id y @type en JSON-LD?

En JSON-LD, @context asigna nombres breves de propiedades JSON a IRI completos para que las claves tengan significados inequívocos entre documentos. La palabra clave @id asigna un identificador IRI global a un objeto nodo, y @type especifica el tipo de un objeto nodo o el tipo de datos de un valor. [1][4][8]

### ¿Cómo actualizó JSON-LD 1.1 a JSON-LD 1.0?

Publicada como tres Recomendaciones del W3C el 2020-07-16, JSON-LD 1.1 reemplazó a la especificación JSON-LD 1.0 de 2014 manteniendo la compatibilidad con los documentos 1.0 salvo donde se indica expresamente. Actualizó la referencia base de JSON a RFC 8259, estandarizó JSON-LD Framing como Recomendación del W3C y añadió funciones como contextos con alcance definido (scoped contexts), literales JSON, dirección base para cadenas de texto y modos adicionales de indexación. [1][2][3][4]

### ¿Requiere JSON-LD conocimientos de RDF?

No. Las especificaciones del W3C indican que JSON-LD puede utilizarse directamente como JSON común sin conocimientos de RDF, al mismo tiempo que actúa como una sintaxis estándar de serialización RDF que se convierte hacia y desde grafos y conjuntos de datos RDF 1.1 para herramientas como SPARQL. [1][4][6]

### ¿Qué son las especificaciones de API de procesamiento y Framing de JSON-LD?

JSON-LD 1.1 Processing Algorithms and API define la interfaz JsonLdProcessor y los algoritmos de expansión, compactación, aplanamiento y conversión a RDF. JSON-LD 1.1 Framing amplía esa API para que los desarrolladores puedan consultar por ejemplo e imponer una estructura de árbol anidado determinista sobre un grafo dirigido. [2][3]

### ¿Cómo se incrusta JSON-LD en páginas HTML para los motores de búsqueda?

JSON-LD puede incluirse dentro de un elemento HTML script con el atributo type establecido en application/ld+json, habitualmente en el encabezado (head) del documento, utilizando vocabularios como Schema.org. Google Search lee el código JSON-LD integrado en la página que describe contenido visible para comprender entidades y mostrar resultados enriquecidos, y ofrece la herramienta Prueba de resultados enriquecidos (Rich Results Test) para su validación. [1][8][9]

## Frases citables

- El W3C RDF Working Group publicó JSON-LD 1.0 como Recomendación del W3C el 2014-01-16. [4]
- El W3C JSON-LD Working Group publicó JSON-LD 1.1, JSON-LD 1.1 Processing Algorithms and API y JSON-LD 1.1 Framing como Recomendaciones del W3C el 2020-07-16. [1][2][3]
- El W3C marcó JSON-LD 1.0 como Recomendación reemplazada (Superseded Recommendation) el 2020-11-03 en favor de JSON-LD 1.1. [4]
- Todo documento JSON-LD 1.1 es JSON válido según IETF RFC 8259, con nombres de miembros únicos en los objetos y arreglos tratados como desordenados por defecto. [1][5]
- RDF 1.1 Concepts and Abstract Syntax menciona JSON-LD junto con Turtle como sintaxis de serialización para almacenar e intercambiar datos RDF. [6]
- JSON-LD 1.1 Framing permite a los desarrolladores realizar consultas por ejemplo y aplicar una estructura de árbol determinista sobre un grafo JSON-LD. [3]
- Schema.org admite JSON-LD junto con Microdata y RDFa como formatos de marcado comprendidos por Google, Microsoft, Yandex y Yahoo!. [9]
- Al 2026-11-23, el estatuto del W3C JSON-LD Working Group rige hasta enero de 2028, y el repositorio w3c/json-ld-syntax en GitHub indica que los borradores de JSON-LD 1.1 tienen sus características congeladas. [7][10]

## Cronología

- 2014-01-16: El W3C RDF Working Group publica JSON-LD 1.0 y JSON-LD 1.0 Processing Algorithms and API como Recomendaciones del W3C. [2][4]
- 2014-02-25: El W3C RDF Working Group publica RDF 1.1 Concepts and Abstract Syntax como Recomendación del W3C, citando JSON-LD como sintaxis de serialización RDF. [6]
- 2017-12: La IETF publica RFC 8259, que define el formato de intercambio de datos JSON referenciado por JSON-LD 1.1. [1][5]
- 2019-12-12: El W3C JSON-LD Working Group publica las versiones candidatas (Candidate Releases) de JSON-LD 1.1, Processing Algorithms and API y Framing. [1][2][3]
- 2020-07-16: El W3C JSON-LD Working Group publica JSON-LD 1.1, JSON-LD 1.1 Processing Algorithms and API y JSON-LD 1.1 Framing como Recomendaciones del W3C. [1][2][3]
- 2020-11-03: El W3C marca JSON-LD 1.0 como Recomendación reemplazada (Superseded Recommendation) en favor de JSON-LD 1.1. [4]

## Fuentes

1. JSON-LD 1.1. World Wide Web Consortium (W3C). publicado 2020-07-16. https://www.w3.org/TR/json-ld11/ (consultado 2026-11-23; tier 1: government or public registry)
2. JSON-LD 1.1 Processing Algorithms and API. World Wide Web Consortium (W3C). publicado 2020-07-16. https://www.w3.org/TR/json-ld11-api/ (consultado 2026-11-23; tier 1: government or public registry)
3. JSON-LD 1.1 Framing. World Wide Web Consortium (W3C). publicado 2020-07-16. https://www.w3.org/TR/json-ld11-framing/ (consultado 2026-11-23; tier 1: government or public registry)
4. JSON-LD 1.0. World Wide Web Consortium (W3C). publicado 2014-01-16. https://www.w3.org/TR/2014/REC-json-ld-20140116/ (consultado 2026-11-23; tier 1: government or public registry)
5. RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format. Internet Engineering Task Force (IETF). publicado 2017-12. https://www.rfc-editor.org/rfc/rfc8259.txt (consultado 2026-11-23; tier 1: government or public registry)
6. RDF 1.1 Concepts and Abstract Syntax. World Wide Web Consortium (W3C). publicado 2014-02-25. https://www.w3.org/TR/rdf11-concepts/ (consultado 2026-11-23; tier 1: government or public registry)
7. JSON-LD - JSON for Linked Data. JSON-LD Community Group. https://json-ld.org/ (consultado 2026-11-23; tier 3: official site)
8. Intro to How Structured Data Markup Works | Google Search Central | Documentation | Google for Developers. Google Search Central. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data (consultado 2026-11-23; tier 3: official site)
9. Getting Started - schema.org. Schema.org. https://schema.org/docs/gs.html (consultado 2026-11-23; tier 3: official site)
10. GitHub - w3c/json-ld-syntax: JSON-LD 1.1 Specification · GitHub. W3C (GitHub). https://github.com/w3c/json-ld-syntax (consultado 2026-11-23; tier 3: official site)

## Citar esta página

Mimirwiki. "JSON-LD." Versión 356d821f, 2026-11-23. https://mimirwiki.com/es/wiki/json-ld
