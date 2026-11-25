---
title: "NPPES y el Identificador Nacional de Proveedor (NPI)"
subtitle: "Sistema federal estadounidense que asigna identificadores de 10 dígitos a los proveedores de atención médica y los publica en el Registro NPI"
canonical_url: https://mimirwiki.com/es/wiki/nppes-npi-registry
language: es
page_class: anchor
revision_sha256: 6112bf904afd8016ca5b753e097dad78d9d3341030844228f1676efb3bfe6419
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/nppes-npi-registry.md
  txt: https://mimirwiki.com/es/wiki/nppes-npi-registry.txt
  json: https://mimirwiki.com/es/wiki/nppes-npi-registry.json
  jsonld: https://mimirwiki.com/es/wiki/nppes-npi-registry.jsonld
translations:
  en: https://mimirwiki.com/wiki/nppes-npi-registry
  ko: https://mimirwiki.com/ko/wiki/nppes-npi-registry
  ja: https://mimirwiki.com/ja/wiki/nppes-npi-registry
  zh: https://mimirwiki.com/zh/wiki/nppes-npi-registry
---

# NPPES y el Identificador Nacional de Proveedor (NPI)

> NPPES es el sistema de los Centros de Servicios de Medicare y Medicaid de Estados Unidos que asigna los Identificadores Nacionales de Proveedor (NPI), los identificadores estándar de 10 dígitos de HIPAA para proveedores de atención médica. Sus datos públicos pueden consultarse en el Registro NPI, mediante una API de solo lectura y a través de archivos descargables mensuales y semanales. Contar con un NPI no confirma que un proveedor tenga licencia ni credenciales.

El Sistema Nacional de Enumeración de Planes y Proveedores (NPPES, por sus siglas en inglés: National Plan and Provider Enumeration System) es el sistema mediante el cual los Centros de Servicios de Medicare y Medicaid (CMS) de Estados Unidos asignan Identificadores Nacionales de Proveedor (NPI) a los proveedores de atención médica. El NPI es el identificador único estándar de salud para proveedores de atención médica adoptado en virtud de la Ley de Portabilidad y Responsabilidad del Seguro Médico de 1996 (HIPAA): un identificador numérico de 10 posiciones con un dígito de control en la décima posición y sin información codificada sobre el proveedor. CMS publica la parte divulgable públicamente de cada registro de NPPES a través del sitio de búsqueda del Registro NPI, una API de solo lectura y archivos descargables. CMS señala que la emisión de un NPI no garantiza ni valida que un proveedor cuente con licencia o credenciales.

**También conocido como:** NPPES, Sistema Nacional de Enumeración de Planes y Proveedores, National Plan and Provider Enumeration System, NPI, Identificador Nacional de Proveedor, National Provider Identifier, Registro NPI, NPI Registry, NPPES NPI Registry

## Datos clave

- **Formato del identificador:** 10 dígitos numéricos, el último un dígito de control de Luhn [4]
- **Operador:** Centros de Servicios de Medicare y Medicaid (CMS) [6]
- **Versión de la API pública:** 2.1 (versiones 1.0 y 2.0 retiradas) (al 2026-11-21) [5]
- **Límite de resultados de la API:** 200 registros por solicitud, 1200 por búsqueda usando skip (al 2026-11-21) [5]
- **Frecuencia de archivos masivos:** Archivo de reemplazo completo mensual, archivo incremental semanal (al 2026-11-21) [8]

## Datos básicos

- **Nombre completo:** National Plan and Provider Enumeration System (Sistema Nacional de Enumeración de Planes y Proveedores) [6]
- **Operado por:** Centros de Servicios de Medicare y Medicaid (CMS) [6]
- **Identificador emitido:** Identificador Nacional de Proveedor (NPI) [1]
- **Formato del identificador:** Numérico de 10 posiciones, dígito de control en la posición 10 [3]
- **Algoritmo del dígito de control:** Fórmula de Luhn (módulo 10 "doblar-sumar-doblar") [4]
- **Base legal:** Simplificación Administrativa de HIPAA, 45 CFR Parte 162 Subparte D [2]
- **Norma final:** 69 FR 3434, publicada el 2004-01-23 [2]
- **Tipos de entidad:** Tipo 1 (personas físicas), Tipo 2 (organizaciones) [10]
- **Consulta pública:** Registro NPI, npiregistry.cms.hhs.gov [6]
- **API:** API JSON de solo lectura, versión 2.1 (al 2026-11-21) [5]
- **Datos masivos:** Archivo mensual de reemplazo completo, archivos incrementales semanales y archivo mensual de desactivación, todos en Versión 2 (al 2026-11-21) [7]
- **Conjunto de códigos de especialidad:** Health Care Provider Taxonomy, mantenido por el National Uniform Claim Committee [11]

## Formato y dígito de control del Identificador Nacional de Proveedor

El Identificador Nacional de Proveedor (NPI) asignado a través de NPPES se define en la normativa federal como un identificador numérico de 10 posiciones, cuya décima posición es un dígito de control, y que no contiene información implícita sobre el proveedor de atención médica.[3] CMS describe el NPI como un número carente de inteligencia (intelligence-free): sus dígitos no codifican datos como el estado de residencia del proveedor ni su especialidad médica.[1]

Un documento de requisitos de CMS fechado el 23 de enero de 2004 especifica que el NPI consta de nueve dígitos numéricos seguidos de un dígito de control, y que inicialmente los NPI se emiten con un primer dígito de 1 o 2 para evitar colisiones con otros identificadores de emisores de tarjetas.[4] El dígito de control se calcula mediante la fórmula de Luhn para el dígito de control módulo 10 "doblar-sumar-doblar". Cuando un NPI se utiliza como identificador de emisor de tarjeta en una tarjeta estándar de identificación de salud, va precedido por el prefijo 80840, donde 80 indica aplicaciones sanitarias y 840 indica Estados Unidos, y el dígito de control se calcula siempre como si ese prefijo estuviera presente. En el caso de un NPI escrito sin el prefijo, esto se logra sumando la constante 24 a la suma de Luhn.[4] En el ejemplo desarrollado por CMS, el identificador de nueve dígitos 123456789 produce el dígito de control 3 y da lugar al NPI 1234567893.[4]

Las reglas de formato del documento de CMS se resumen a continuación.[4]

| Propiedad | Valor |
| --- | --- |
| Longitud | 10 posiciones numéricas |
| Estructura | Identificador de 9 dígitos seguido de 1 dígito de control |
| Primer dígito en la emisión inicial | 1 o 2 |
| Algoritmo del dígito de control | Fórmula de Luhn (módulo 10 "doblar-sumar-doblar") |
| Prefijo de emisor de tarjeta | 80840 |
| Constante sumada cuando el prefijo está ausente | 24 |

## Quién debe obtener y utilizar un Identificador Nacional de Proveedor

El Identificador Nacional de Proveedor debe ser obtenido por todo proveedor de atención médica cubierto, término que la Norma Final del NPI aplica a los proveedores de atención médica que transmiten cualquier información de salud en formato electrónico en relación con una transacción para la cual el Secretario de Salud y Servicios Humanos haya adoptado un estándar.[2] De conformidad con 45 CFR 162.410, un proveedor cubierto debe utilizar su NPI para identificarse en las transacciones estándar, divulgar el NPI cuando lo solicite cualquier entidad que lo necesite para una transacción estándar y notificar los cambios en sus datos obligatorios en un plazo de 30 días desde que se produzcan.[3] Los planes de salud y las cámaras de compensación de atención médica deben emplear en las transacciones estándar el NPI de cualquier proveedor al que se le haya asignado uno, y un plan de salud no puede exigir a un proveedor que ya posee un NPI que obtenga otro.[3]

Un proveedor de atención médica que no sea una entidad cubierta también puede obtener un NPI.[3] La normativa exige además que toda organización que sea proveedor cubierto se asegure de que los prescriptores que sean sus miembros, empleados o contratistas, y que no sean entidades cubiertas por sí mismos, obtengan un NPI a través de NPPES.[3] El preámbulo de la Norma Final cita a enfermeros registrados, higienistas dentales y técnicos como ejemplos de personas que prestan atención médica sin realizar necesariamente transacciones cubiertas y que, no obstante, reúnen los requisitos para obtener un NPI.[2]

La Norma Final del NPI se publicó el 23 de enero de 2004 y entró en vigor el 23 de mayo de 2005, primer día en que los proveedores pudieron presentar solicitudes. Los proveedores cubiertos, las cámaras de compensación de atención médica y los planes de salud distintos de los planes de salud pequeños debían cumplirla a más tardar el 23 de mayo de 2007, y los planes de salud pequeños a más tardar el 23 de mayo de 2008.[2] El preámbulo de la Norma Final describe el NPI como un identificador duradero. Para una persona física está concebido como permanente, y para una organización no se requiere un nuevo NPI tras un cambio de titularidad, nombre, dirección o clasificación taxonómica.[2] Un NPI desactivado no se reasigna a ningún otro proveedor.[3]

## Tipos de entidad en NPPES: NPI de tipo 1 y de tipo 2

NPPES asigna cada Identificador Nacional de Proveedor bajo uno de dos tipos de entidad, seleccionados en la solicitud de NPI. El tipo de entidad 1 abarca a las personas físicas que prestan atención médica, como médicos, odontólogos, enfermeros, quiroprácticos, farmacéuticos y fisioterapeutas. El tipo de entidad 2 abarca a las organizaciones que prestan atención médica o suministran insumos médicos, como hospitales, agencias de atención domiciliaria, empresas de ambulancias, consultas grupales, organizaciones de mantenimiento de la salud, proveedores de equipo médico duradero y farmacias.[10]

El formulario de solicitud CMS-10114 establece que una empresa unipersonal (sole proprietorship) corresponde al tipo de entidad 1 (persona física) y solo puede obtener un NPI, mientras que una persona constituida como sociedad puede poseer un NPI de tipo 1 a título personal y un NPI de tipo 2 para la sociedad.[10] Una organización también puede obtener NPI independientes para sus subunidades (subparts), que el formulario describe como componentes de una organización proveedora que pueden encontrarse en una ubicación distinta o prestar un tipo diferente de atención médica.[3][10] En la API del Registro NPI, los dos tipos aparecen con los valores `NPI-1` y `NPI-2`.[5]

Los proveedores de atención médica pueden solicitar un NPI por tres vías: en línea a través de NPPES, mediante una organización de Intercambio Electrónico de Archivos (Electronic File Interchange) que envía datos de solicitud en lote con el permiso del proveedor, o enviando por correo postal el formulario impreso CMS-10114 al Enumerador de NPI (NPI Enumerator).[12] Se requiere un código principal de Healthcare Provider Taxonomy y se pueden declarar hasta 15 códigos de taxonomía.[9] El conjunto de códigos de taxonomía es mantenido por el National Uniform Claim Committee (NUCC), y cada código es un valor alfanumérico de diez caracteres organizado en tres niveles: agrupación de proveedores, clasificación y área de especialización.[11]

## Búsqueda en el Registro NPI y la API de NPPES (versión 2.1)

CMS describe el Registro NPI en npiregistry.cms.hhs.gov como un directorio gratuito de todos los registros activos del Identificador Nacional de Proveedor. Muestra las partes de un registro NPI que CMS considera de relevancia pública, incluidos el nombre del proveedor, su especialidad (taxonomía) y la dirección de su consultorio o centro de práctica.[6] Los registros pueden buscarse por número NPI, tipo de NPI, descripción taxonómica, nombre del proveedor o de la organización, nombre del funcionario autorizado, ciudad, estado, país y código postal. La búsqueda devuelve únicamente los primeros 2100 resultados coincidentes. Desde el 25 de junio de 2024, NPPES limita el número de consultas al Registro que pueden completarse por hora, aunque la página de búsqueda no especifica el límite horario, y esa misma página indica que las consultas masivas deben utilizar el archivo de difusión de datos.[6]

La API de NPPES es una interfaz de solo lectura que devuelve los datos del Registro en formato JSON y obtiene sus datos de NPPES a diario.[5] Al 2026-11-21 la única versión admitida es la 2.1: CMS señala que las versiones 1.0 y 2.0 están retiradas y que las solicitudes sin indicador de versión ya no funcionan, y figura como "TBD" (por determinar) la fecha prevista de retirada gradual de la versión 2.1. El punto de conexión es `https://npiregistry.cms.hhs.gov/api/?version=2.1`.[5] Los límites de solicitud documentados en la página de ayuda de la API son los siguientes.[5]

| Elemento | Valor al 2026-11-21 |
| --- | --- |
| Versión admitida | 2.1 |
| Valor predeterminado de `limit` | 10 |
| Valor máximo de `limit` | 200 resultados por solicitud |
| Valor máximo de `skip` | 1000 registros |
| Máximo de registros para un mismo conjunto de criterios | 1200, en seis solicitudes |
| Formato de respuesta | JSON |

Los parámetros de búsqueda documentados para la versión 2.1 incluyen `number`, `enumeration_type`, `taxonomy_description`, `first_name`, `last_name`, `organization_name`, `city`, `state`, `postal_code`, `country_code`, `limit` y `skip`, y la lista documentada no incluye clave de API ni parámetro de autenticación. Los campos de nombre y código postal admiten un comodín al final después de al menos dos caracteres.[5] La respuesta JSON contiene un arreglo de direcciones cuya primera entrada corresponde a la ubicación principal de práctica y la segunda a la dirección postal, un arreglo de taxonomías de hasta 15 entradas, un arreglo de otros identificadores de hasta 50 entradas y arreglos para otros nombres, puntos de conexión y ubicaciones de práctica adicionales.[5]

## Archivos descargables de difusión de datos de NPPES

Los datos de NPPES también se publican como archivos descargables. CMS comenzó a divulgar los datos de proveedores de NPPES sujetos a publicación en virtud de la Ley de Libertad de Información (FOIA) en septiembre de 2007, en dos formatos: el Registro NPI, una base de datos de solo consulta actualizada diariamente, y el archivo descargable. CMS no cobra ninguna tarifa por consultar o descargar los datos.[8] Se producen tres tipos de archivos: un archivo mensual de reemplazo completo de NPI, un archivo semanal incremental de NPI y un archivo de reemplazo completo de desactivación de NPI. El archivo semanal contiene únicamente los datos correspondientes a una semana determinada, incluidos los NPI recién asignados, las actualizaciones y los NPI recién desactivados, y está pensado para utilizarse junto con el archivo mensual más reciente.[8]

La descarga mensual consiste en un archivo ZIP que contiene un documento léame (readme), un documento de valores de códigos, un archivo de encabezados y un archivo de datos separados por comas en el que cada valor está encerrado entre comillas dobles. CMS advierte que el archivo de datos supera los 4 GB y que no ofrece mesa de ayuda ni soporte técnico para su descarga o uso.[8] Desde el 18 de junio de 2018, cada paquete incluye además tres archivos de referencia: Other Name, Practice Location y Endpoint.[8] En el caso de un NPI desactivado, los archivos divulgan únicamente el NPI y su fecha de desactivación.[8]

Al 2026-11-21 la página NPI Files ofrece únicamente archivos de la Versión 2. NPPES finalizó el soporte para la Versión 1 de los archivos mensuales y semanales a partir del 3 de marzo de 2026, y la Versión 2 amplía los límites de caracteres para los campos First Name y Legal Business Name.[7] El 2026-11-21 la página incluía un archivo mensual fechado el 9 de noviembre de 2026 (un archivo ZIP de 1079,11 MB), una actualización mensual de desactivaciones con la misma fecha y actualizaciones semanales que abarcaban del 2 al 8 de noviembre y del 9 al 15 de noviembre de 2026.[7]

## Qué no verifican NPPES ni el Registro NPI

NPPES y el Registro NPI no verifican la licencia ni las credenciales de un proveedor. La página de búsqueda del Registro, la página de ayuda de la API y la página NPI Files muestran el mismo aviso de CMS: "La emisión de un NPI no garantiza ni valida que el proveedor de atención médica cuente con licencia o credenciales" ("Issuance of an NPI does not ensure or validate that the Health Care Provider is Licensed or Credentialed").[5][6][7] Los datos del Registro y de los archivos descargables son los informados a NPPES por el propio proveedor, por alguien que actúa en su nombre o por el funcionario autorizado de una organización, y CMS solicita a los proveedores que corrijan cualquier información errónea.[8]

Varios campos de NPPES que asemejan credenciales son proporcionados por los propios proveedores. Los elementos de datos divulgados para proveedores individuales incluyen un número de licencia y un código de estado de la licencia.[9] Los códigos de taxonomía son seleccionados por el propio proveedor, y NUCC señala que el alcance de la licencia profesional no forma parte del ámbito del conjunto de códigos de taxonomía.[11] El NPI en sí mismo no contiene información sobre especialidad ni ubicación.[1]

Algunos datos de NPPES nunca se publican. Se determinó que los números de Seguro Social, los números de identificación personal del contribuyente (ITIN) del IRS y las fechas de nacimiento no son divulgables en virtud de la FOIA y no se hacen públicos.[9] En sentido contrario, un proveedor con un NPI activo no puede excluirse de la divulgación ni suprimir su registro.[8] El preámbulo de la Norma Final de 2004 también estableció que en el sistema de enumeración no se mantendrían vínculos entre los distintos tipos de NPI y que no se incluiría información sobre propiedad ni constitución societaria.[2]

## Preguntas frecuentes

### ¿Qué es un número NPI?

Un Identificador Nacional de Proveedor (NPI) es el identificador único estándar de HIPAA para proveedores de atención médica en Estados Unidos. Es un número de 10 dígitos con un dígito de control en la última posición y sin información codificada sobre el proveedor, asignado mediante NPPES, el sistema de enumeración de los Centros de Servicios de Medicare y Medicaid. [1][3][6]

### ¿Tener un NPI significa que un proveedor cuenta con licencia?

No. CMS indica en el Registro NPI que la emisión de un NPI no garantiza ni valida que un proveedor de atención médica cuente con licencia o credenciales. Los datos de NPPES son declarados por los propios proveedores y los códigos de taxonomía son autoseleccionados. [6][8][11]

### ¿Cómo se calcula el dígito de control del NPI?

El décimo dígito es un dígito de control de Luhn (módulo 10 "doblar-sumar-doblar") calculado como si el prefijo 80840 precediera al número. Cuando el prefijo no se escribe, se suma la constante 24 a la suma de Luhn. En el ejemplo de CMS, 123456789 produce el dígito de control 3, lo que da el NPI 1234567893. [4]

### ¿Cuál es la diferencia entre un NPI de tipo 1 y uno de tipo 2?

Los NPI de tipo de entidad 1 se emiten a personas físicas que prestan atención médica, incluidas las empresas unipersonales, que solo pueden obtener un NPI. Los NPI de tipo de entidad 2 se emiten a organizaciones como hospitales, consultas grupales y farmacias, así como a sus subunidades. [10]

### ¿Cuáles son los límites de la API del Registro NPI?

Al 2026-11-21 la API admite únicamente la versión 2.1, devuelve como máximo 200 resultados por solicitud y permite que el parámetro skip omita hasta 1000 registros, con un máximo de 1200 registros por conjunto de criterios de búsqueda. CMS remite a los usuarios con necesidades masivas al archivo descargable de difusión de datos. [5][6]

### ¿Con qué frecuencia se actualizan los datos públicos de NPPES?

CMS describe el Registro NPI como una base de datos actualizada diariamente, y la API obtiene datos de NPPES cada día. El archivo descargable de reemplazo completo se publica mensualmente y los archivos incrementales se publican cada semana. [5][8]

## Frases citables

- El Identificador Nacional de Proveedor es un identificador numérico de 10 posiciones con un dígito de control en la décima posición. [3]
- El dígito de control del NPI se calcula con la fórmula de Luhn como si el prefijo 80840 precediera al número. [4]
- CMS afirma que la emisión de un NPI no garantiza ni valida que un proveedor de atención médica cuente con licencia o credenciales. [6]
- Al 2026-11-21, la API del Registro NPI de NPPES admite únicamente la versión 2.1. [5]
- Al 2026-11-21, una consulta a la API del Registro NPI de NPPES devuelve un máximo de 200 resultados por solicitud. [5]
- NPPES publica un archivo de reemplazo completo de NPI mensualmente y un archivo incremental de NPI semanalmente. [8]
- La Norma Final del NPI se publicó en el Registro Federal el 23 de enero de 2004 en 69 FR 3434. [2]
- Los números de Seguro Social, los números de identificación personal del contribuyente (ITIN) del IRS y las fechas de nacimiento almacenados en NPPES no se divulgan al público. [9]

## Cronología

- 2004-01-23: El Departamento de Salud y Servicios Humanos publica la Norma Final del NPI (69 FR 3434), mediante la cual adopta el Identificador Nacional de Proveedor como identificador único estándar de salud para proveedores de atención médica. [2]
- 2005-05-23: Entra en vigor la Norma Final del NPI y los proveedores de atención médica pueden comenzar a solicitar NPI. [2]
- 2006-05-01: Se habilita el proceso de Intercambio Electrónico de Archivos (Electronic File Interchange) para la enumeración masiva. [9]
- 2007-05-23: Fecha de cumplimiento obligatorio para proveedores de atención médica cubiertos, cámaras de compensación de atención médica y planes de salud distintos de los planes de salud pequeños. [2]
- 2007-05-30: CMS publica en el Registro Federal el Aviso de Difusión de Datos de NPPES (CMS-6060-N). [9]
- 2008-05-23: Fecha de cumplimiento obligatorio para los planes de salud pequeños. [2]
- 2018-06-18: El archivo comprimido descargable de NPPES comienza a incluir los archivos de referencia Other Name, Practice Location y Endpoint. [8]
- 2024-06-25: NPPES comienza a limitar el número de consultas al Registro NPI que pueden completarse por hora. [6]
- 2026-03-03: NPPES finaliza el soporte para la Versión 1 de los archivos descargables mensuales y semanales. [7]

## Fuentes

1. National Provider Identifier Standard (NPI) | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/regulations-and-guidance/administrative-simplification/nationalprovidentstand (consultado 2026-11-21; tier 1: government or public registry)
2. HIPAA Administrative Simplification: Standard Unique Health Identifier for Health Care Providers. Federal Register, Department of Health and Human Services. publicado 2004-01-23. https://www.federalregister.gov/documents/2004/01/23/04-1149/hipaa-administrative-simplification-standard-unique-health-identifier-for-health-care-providers (consultado 2026-11-21; tier 1: government or public registry)
3. 45 CFR Part 162 Subpart D: Standard Unique Health Identifier for Health Care Providers. Electronic Code of Federal Regulations (eCFR). https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-162/subpart-D (consultado 2026-11-21; tier 1: government or public registry)
4. Requirements for National Provider Identifier (NPI) and NPI Check Digit. Centers for Medicare & Medicaid Services. publicado 2004-01-23. https://www.cms.gov/Regulations-and-Guidance/Administrative-Simplification/NationalProvIdentStand/Downloads/NPIcheckdigit.pdf (consultado 2026-11-21; tier 1: government or public registry)
5. NPPES NPI Registry: NPPES API Help. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/api-page (consultado 2026-11-21; tier 1: government or public registry)
6. NPPES NPI Registry: Search NPI Records. Centers for Medicare & Medicaid Services. https://npiregistry.cms.hhs.gov/search (consultado 2026-11-21; tier 1: government or public registry)
7. NPI Files. Centers for Medicare & Medicaid Services. https://download.cms.gov/nppes/NPI_Files.html (consultado 2026-11-21; tier 1: government or public registry)
8. Data Dissemination | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/data-dissemination (consultado 2026-11-21; tier 1: government or public registry)
9. HIPAA Administrative Simplification: National Plan and Provider Enumeration System Data Dissemination. Federal Register, Centers for Medicare & Medicaid Services. publicado 2007-05-30. https://www.federalregister.gov/documents/2007/05/30/07-2651/hipaa-administrative-simplification-national-plan-and-provider-enumeration-system-data-dissemination (consultado 2026-11-21; tier 1: government or public registry)
10. CMS-10114 National Provider Identifier (NPI) Application/Update Form. Centers for Medicare & Medicaid Services. https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/downloads/CMS10114.pdf (consultado 2026-11-21; tier 1: government or public registry)
11. National Uniform Claim Committee - Provider Taxonomy. National Uniform Claim Committee. https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40 (consultado 2026-11-21; tier 3: official site)
12. How to Apply | CMS. Centers for Medicare & Medicaid Services. https://www.cms.gov/medicare/regulations-guidance/administrative-simplification/how-apply (consultado 2026-11-21; tier 1: government or public registry)

## Citar esta página

Mimirwiki. "NPPES y el Identificador Nacional de Proveedor (NPI)." Versión 6112bf90, 2026-11-24. https://mimirwiki.com/es/wiki/nppes-npi-registry
