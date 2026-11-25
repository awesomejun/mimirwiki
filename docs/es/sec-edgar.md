---
title: "SEC EDGAR"
subtitle: "Sistema electrónico de presentación de informes y divulgación pública de la Comisión de Bolsa y Valores de Estados Unidos"
canonical_url: https://mimirwiki.com/es/wiki/sec-edgar
language: es
page_class: anchor
revision_sha256: 869f0a9b2c3dcd0d80d4d2f25ffe846730c74f12daa20dedef4a62a772a8dd52
date_modified: 2026-11-21
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert"
source_count: 12
alternates:
  md: https://mimirwiki.com/es/wiki/sec-edgar.md
  txt: https://mimirwiki.com/es/wiki/sec-edgar.txt
  json: https://mimirwiki.com/es/wiki/sec-edgar.json
  jsonld: https://mimirwiki.com/es/wiki/sec-edgar.jsonld
translations:
  en: https://mimirwiki.com/wiki/sec-edgar
  ko: https://mimirwiki.com/ko/wiki/sec-edgar
  ja: https://mimirwiki.com/ja/wiki/sec-edgar
  zh: https://mimirwiki.com/zh/wiki/sec-edgar
---

# SEC EDGAR

> EDGAR (Electronic Data Gathering, Analysis, and Retrieval) es el sistema principal de la Comisión de Bolsa y Valores de Estados Unidos para presentar informes bursátiles como los formularios 10-K, 10-Q y 8-K. Su base de datos pública es de consulta gratuita y cada declarante se identifica mediante una Central Index Key (CIK). Las API JSON de data.sec.gov no requieren clave de API, y el acceso automatizado está limitado a 10 solicitudes por segundo.

EDGAR (Electronic Data Gathering, Analysis, and Retrieval) es el sistema principal de la Comisión de Bolsa y Valores de Estados Unidos (SEC) mediante el cual las empresas y otros sujetos obligados presentan documentos en virtud de la Ley de Valores de 1933, la Ley del Mercado de Valores de 1934, la Ley de Contratos de Fideicomiso de 1939 y la Ley de Sociedades de Inversión de 1940. El acceso a la base de datos pública de EDGAR es gratuito. EDGAR asigna a cada entidad declarante una Central Index Key (CIK) y a cada presentación aceptada un número de acceso (accession number). La SEC también publica historiales de presentaciones y datos financieros extraídos en formato XBRL como JSON mediante API REST en data.sec.gov, que no requieren autenticación ni clave de API.

**También conocido como:** EDGAR, Electronic Data Gathering, Analysis, and Retrieval, Base de datos SEC EDGAR, Sistema de presentación EDGAR, data.sec.gov

## Datos clave

- **Operador:** Comisión de Bolsa y Valores de Estados Unidos (EDGAR Business Office) [1]
- **Identificador de declarante:** Central Index Key (CIK), completada con ceros a la izquierda hasta 10 dígitos en las URL de la API [2]
- **Límite de frecuencia de solicitudes:** 10 solicitudes por segundo por usuario (al 2026-11-21) [3]
- **Autenticación de la API:** Ninguna, no se requiere clave de API (al 2026-11-21) [2]
- **Cobertura de búsqueda de texto completo:** Presentaciones electrónicas desde 2001 (al 2026-11-21) [6]

## Datos básicos

- **Nombre completo:** Electronic Data Gathering, Analysis, and Retrieval [1]
- **Operador:** Comisión de Bolsa y Valores de Estados Unidos [1]
- **Administrado por:** EDGAR Business Office [1]
- **Identificador de declarante:** Central Index Key (CIK) [3]
- **Identificador de presentación:** Número de acceso (accession number), por ejemplo 0001193125-15-118890 [3]
- **Acceso público:** Gratuito [1]
- **API de datos:** API REST de data.sec.gov que devuelven JSON: submissions, company concept, company facts, frames [2]
- **Autenticación de la API:** No requerida (a fecha de 2026-11-21) [2]
- **Límite de frecuencia:** 10 solicitudes por segundo (a fecha de 2026-11-21) [3]
- **Horario de presentación:** Días hábiles, de 6:00 a. m. a 10:00 p. m., hora del este [3]
- **Cobertura de búsqueda de texto completo:** Presentaciones electrónicas desde 2001 [6]
- **Inicio de sesión de declarantes:** Credenciales de cuenta individual de Login.gov con autenticación multifactor [7]

## Qué es SEC EDGAR y quién presenta documentos en el sistema

EDGAR, el sistema Electronic Data Gathering, Analysis, and Retrieval, es descrito por la SEC como el sistema principal para que las empresas y otros sujetos obligados presenten documentos en virtud de la Ley de Valores de 1933, la Ley del Mercado de Valores de 1934, la Ley de Contratos de Fideicomiso de 1939 y la Ley de Sociedades de Inversión de 1940.[1] Una página de la SEC revisada por última vez el 28 de noviembre de 2025 señala que el sistema procesa alrededor de 4.700 presentaciones diarias, entrega 3.000 terabytes de datos al público cada año e incorpora un promedio de 40.000 nuevos declarantes anualmente.[1] La EDGAR Business Office es la unidad responsable del sistema y se encarga de su gobernanza, planificación estratégica y soporte a los declarantes.[1]

La SEC establece que tanto las empresas nacionales como las extranjeras deben presentar electrónicamente declaraciones de registro, informes periódicos y otros formularios a través de EDGAR, y que cualquier persona puede consultar y descargar la información sin costo alguno.[3] Además de las presentaciones empresariales, la base de datos pública contiene información proporcionada por fondos mutuos, fondos cotizados en bolsa (ETF), anualidades variables y personas físicas.[1] EDGAR acepta nuevas presentaciones todos los días hábiles, de lunes a viernes, de 6:00 a. m. a 10:00 p. m., hora del este. Algunas presentaciones iniciadas después de las 5:30 p. m., hora del este, o después de las 10:00 p. m. en el caso de los formularios de titularidad 3, 4 y 5, se difunden el siguiente día hábil.[3]

La SEC comenzó a desarrollar un sistema electrónico de divulgación en 1983 y puso el sistema EDGAR operativo a disposición de declarantes voluntarios el 15 de julio de 1992. Las normas emitidas el 23 de febrero de 1993 exigieron la presentación electrónica, con una incorporación gradual que comenzó el 26 de abril de 1993, y las normas que obligaban a los emisores extranjeros a presentar informes mediante EDGAR entraron en vigor el 4 de noviembre de 2002.[9] La página de acceso a datos de la SEC indica que EDGAR comenzó en 1994/1995 y que sus archivos de índice enumeran todas las presentaciones públicas desde el tercer trimestre de 1994 en adelante.[3]

## Identificadores de EDGAR: CIK y números de acceso

EDGAR asigna a cada declarante un identificador numérico único, la Central Index Key (CIK), cuando se registra para realizar presentaciones ante la SEC. Los números CIK siguen siendo exclusivos del declarante y no se reutilizan.[3] Entre los declarantes se incluyen empresas, fondos y personas físicas, y una misma CIK puede estar asociada a más de un nombre cuando una empresa o un fondo ha cambiado de denominación.[3] En las URL de la API de data.sec.gov, la CIK se escribe con 10 dígitos, completada con ceros al principio.[2]

Cada presentación aceptada recibe un número de acceso (accession number), un identificador único asignado automáticamente por EDGAR. En el ejemplo de la SEC, 0001193125-15-118890, los diez primeros dígitos corresponden a la CIK de la entidad que envió la presentación, que puede ser la propia empresa o un agente presentador externo; los dos dígitos siguientes indican el año, y el grupo final es un contador secuencial de las presentaciones realizadas desde esa CIK. Por lo general, aunque no siempre, el contador se reinicia al comienzo de cada año calendario.[3] Los formatos de ambos identificadores se resumen a continuación.[2][3]

| Identificador | Forma escrita en la documentación de la SEC | Qué identifica |
| --- | --- | --- |
| Central Index Key (CIK) | `CIK##########` en las URL de la API, completada con ceros hasta 10 dígitos | Un declarante: empresa, fondo o persona física |
| Número de acceso | `0001193125-15-118890`: CIK del remitente, año en dos dígitos y contador secuencial | Una presentación aceptada |

Los documentos de cada presentación se almacenan en rutas construidas a partir de ambos identificadores. En la ruta de ejemplo de la SEC `/Archives/edgar/data/1122304/000119312515118890/`, el primer directorio corresponde a la CIK y el segundo al número de acceso sin guiones, una estructura disponible para las presentaciones realizadas después del 26 de mayo de 2000. Se permite explorar los directorios de CIK y de número de acceso, pero el directorio superior `/Archives/edgar/data/` no es explorable.[3] La SEC también publica `company_tickers.json`, un archivo que vincula símbolos bursátiles (tickers), CIK y nombres de empresas, el cual se actualiza periódicamente sin garantizar su exactitud ni su alcance.[3]

## Tipos de formularios habituales en EDGAR

EDGAR clasifica cada presentación mediante un tipo de formulario, y la adición de «/A» al tipo de formulario, como 10-K/A, indica una enmienda.[5] Los tipos de formularios que figuran a continuación se encuentran entre los descritos por la SEC en sus guías sobre consulta de presentaciones y sobre el Formulario D.[5][11]

| Tipo de formulario | Descripción |
| --- | --- |
| 10-K | Informe anual con estados financieros anuales auditados |
| 10-Q | Informe trimestral con estados financieros trimestrales no auditados |
| 8-K | Informe de hechos relevantes sobre eventos o información importante, publicado antes del siguiente informe periódico |
| S-1 | Declaración de registro para la oferta y venta de valores al público, a menudo para una oferta pública inicial |
| 4 | Declaración de cambios en la propiedad efectiva por parte de una persona con información privilegiada de la empresa, con plazo de dos días hábiles tras la operación |
| 20-F | Informe anual o declaración de registro de un emisor privado extranjero |
| D | Notificación de una oferta exenta de valores en virtud de la Regulación D |

El Formulario D en EDGAR es una notificación de oferta exenta cuya presentación ante la SEC exige la Regulación D, y debe presentarse dentro de los 15 días posteriores a la primera venta de valores. Según una página de la SEC revisada por última vez el 24 de abril de 2026, la SEC no cobra tarifas por abrir o mantener una cuenta de EDGAR ni por presentar una notificación o enmienda del Formulario D.[11] Una empresa necesita contar con una cuenta de EDGAR, y con ella una CIK, antes de poder presentar un Formulario D.[11]

Los estados financieros de varios tipos de formularios de EDGAR también están disponibles como datos estructurados. Las API XBRL de data.sec.gov cubren los formularios 10-Q, 10-K, 8-K, 20-F, 40-F y 6-K y sus variantes, y la SEC señala que exigió XBRL por primera vez en 2009.[2] La SEC describe XBRL como un formato basado en XML para presentar estados financieros, enviado como archivo XML independiente o incrustado en informes HTML como inline XBRL.[2]

## API de data.sec.gov, marcos XBRL y reglas de acceso justo de la SEC

La SEC aloja API RESTful en data.sec.gov que entregan datos de EDGAR en formato JSON. A fecha de 2026-11-21, estas API no requieren autenticación ni clave de API, y cubren el historial de presentaciones de cada declarante así como los datos XBRL de los estados financieros.[2] A continuación se enumeran los puntos de acceso documentados.[2]

| Punto de acceso | Qué devuelve |
| --- | --- |
| `https://data.sec.gov/submissions/CIK##########.json` | Historial de presentaciones de una entidad, con metadatos como el nombre actual, nombres anteriores, bolsas y símbolos bursátiles |
| `https://data.sec.gov/api/xbrl/companyconcept/CIK##########/us-gaap/AccountsPayableCurrent.json` | Todas las divulgaciones XBRL de un concepto concreto por parte de una empresa |
| `https://data.sec.gov/api/xbrl/companyfacts/CIK##########.json` | Todos los datos de conceptos de una empresa en una sola llamada |
| `https://data.sec.gov/api/xbrl/frames/us-gaap/AccountsPayableCurrent/USD/CY2019Q1I.json` | Un dato por entidad informante para el período calendario solicitado |

El punto de acceso de presentaciones (`submissions`) devuelve al menos un año de presentaciones o las 1.000 más recientes, lo que sea mayor, y enlaza a archivos adicionales para presentaciones más antiguas. El punto de acceso de marcos (`frames`) acepta un período escrito como `CY####` para datos anuales, `CY####Q#` para datos trimestrales o `CY####Q#I` para datos instantáneos, y devuelve el dato de cada entidad que mejor se ajusta a ese período calendario. Los puntos de acceso XBRL agregan únicamente datos que utilizan una taxonomía no personalizada, como us-gaap, ifrs-full, dei o srt, y que corresponden a la totalidad de la entidad informante.[2] Las API se actualizan en tiempo real a medida que se difunden las presentaciones, con una demora de procesamiento habitual inferior a un segundo para las presentaciones y menor de un minuto para los datos XBRL, y los archivos masivos de ambos conjuntos de datos (`submissions.zip` y `companyfacts.zip`) se vuelven a publicar cada noche alrededor de las 3:00 a. m., hora del este.[2]

El acceso automatizado a EDGAR está sujeto a las reglas de acceso justo de la SEC. A fecha de 2026-11-21, la frecuencia máxima es de 10 solicitudes por segundo, y la SEC pide a los clientes automatizados que declaren un agente de usuario en los encabezados de sus solicitudes. Su valor de ejemplo de `User-Agent` consta del nombre de una empresa seguido de una dirección de correo electrónico de contacto administrativo.[3] El límite se aplica a cada usuario con independencia del número de equipos utilizados, y la SEC se reserva el derecho de bloquear direcciones IP que envíen solicitudes excesivas.[4] data.sec.gov no admite CORS, y la SEC indica que no puede ofrecer soporte técnico para desarrollar o depurar procesos automatizados de descarga.[2]

## Cambios de acceso para declarantes y gestión de cuentas en EDGAR Next

EDGAR Next es el nombre que da la SEC a las enmiendas de normas y formularios sobre el acceso de declarantes y la gestión de cuentas en EDGAR que la Comisión adoptó el 27 de septiembre de 2024.[8] Las enmiendas exigen a los declarantes autorizar a personas identificadas para administrar sus cuentas de EDGAR y obligan a las personas que actúan en nombre de un declarante a presentar credenciales de cuenta individual obtenidas mediante Login.gov. También modernizaron el Formulario ID, la solicitud de acceso a EDGAR, e introdujeron API opcionales mediante las cuales los declarantes pueden realizar presentaciones, recuperar información y ejecutar tareas de gestión de cuentas.[8] El cumplimiento del Formulario ID modificado pasó a ser obligatorio el 24 de marzo de 2025, fecha en la que entraron en vigor todas las enmiendas, y el cumplimiento íntegro de todas las enmiendas se exigió a partir del 15 de septiembre de 2025.[8]

La página de la SEC sobre EDGAR Next, revisada por última vez el 22 de diciembre de 2025, señala que el cumplimiento de EDGAR Next es obligatorio para presentar documentos en EDGAR y que el período de inscripción ha cerrado. Un declarante debe haberse inscrito en EDGAR Next o haber obtenido la aprobación de una solicitud de Formulario ID el 24 de marzo de 2025 o con posterioridad, y quien carezca de acceso debe solicitarlo presentando el Formulario ID en el sitio web EDGAR Filer Management.[7] Iniciar sesión en cualquiera de los tres sitios web de EDGAR (EDGAR Filer Management, EDGAR Online Forms y EDGAR Filing) requiere credenciales de cuenta individual de Login.gov y autenticación multifactor, y los métodos de inicio de sesión anteriores han quedado discontinuados.[7] Las API destinadas a declarantes se documentan por separado de las API públicas de data.sec.gov, en guías que abarcan los tokens de API de declarante y de usuario.[2]

## Qué no acredita una presentación en EDGAR

La existencia de una presentación en SEC EDGAR no significa que la SEC haya verificado su contenido. La División de Finanzas Corporativas de la SEC revisa las presentaciones de forma selectiva y afirma que su proceso de revisión «no constituye una garantía de que la divulgación sea completa y exacta»: la responsabilidad de que la divulgación sea completa y exacta recae en la empresa y en las demás partes implicadas en la elaboración de sus presentaciones.[10] En virtud de la Ley Sarbanes-Oxley de 2002, cada empresa informante recibe algún nivel de revisión por parte de la División al menos una vez cada tres años. La División añade que no evalúa los méritos de una operación ni determina si una inversión resulta adecuada para un inversor en particular.[10]

Una presentación en EDGAR tampoco constituye prueba de registro ni de aprobación. El sitio de educación para inversores de la SEC, Investor.gov, indica que realizar una presentación ante la SEC no convierte a una persona o firma en registrada ante la SEC, y que la SEC no emite certificados de registro.[12] La misma página señala que la presentación de un Formulario D no indica nada sobre si una persona o firma está registrada o autorizada ante la SEC.[12]

Las herramientas públicas de EDGAR también presentan límites de cobertura. La búsqueda de texto completo abarca únicamente las presentaciones enviadas electrónicamente desde 2001, incluidos anexos como los exhibits.[6] Algunas presentaciones todavía se entregan en papel y no están disponibles a través de EDGAR, y el personal de la SEC puede retirar o corregir una presentación tras su aceptación a solicitud del declarante, por ejemplo cuando un documento se presentó para el declarante equivocado o duplicaba uno anterior.[3]

## Preguntas frecuentes

### ¿Qué es un número CIK?

Una Central Index Key (CIK) es el identificador numérico único que EDGAR asigna a un declarante cuando se registra para presentar documentos ante la SEC. Los números CIK no se reutilizan y las API de data.sec.gov los escriben completados con ceros a la izquierda hasta 10 dígitos. [3][2]

### ¿Las API de SEC EDGAR requieren una clave de API?

No. A fecha de 2026-11-21, la SEC indica que las API de data.sec.gov no requieren autenticación ni claves de API. Las solicitudes automatizadas están limitadas a 10 solicitudes por segundo, y la SEC pide a los clientes que declaren un agente de usuario en los encabezados de la solicitud. [2][3]

### ¿Verifica la SEC la exactitud de las presentaciones en EDGAR?

La División de Finanzas Corporativas de la SEC revisa las presentaciones de forma selectiva y señala que su proceso de revisión no constituye una garantía de que la divulgación sea completa y exacta. La responsabilidad de que la divulgación sea completa y exacta recae en la empresa y en las demás partes implicadas en la elaboración de sus presentaciones. [10]

### ¿Hasta qué año se remontan las presentaciones en EDGAR?

La SEC indica que EDGAR comenzó en 1994/1995 y que sus archivos de índice enumeran presentaciones públicas desde el tercer trimestre de 1994 en adelante. La búsqueda de texto completo cubre las presentaciones electrónicas enviadas desde 2001. [3][6]

### ¿Qué es EDGAR Next?

EDGAR Next es el conjunto de enmiendas de normas y formularios sobre el acceso de declarantes y la gestión de cuentas que la SEC adoptó el 27 de septiembre de 2024. Las enmiendas entraron en vigor el 24 de marzo de 2025, su cumplimiento pasó a ser obligatorio el 15 de septiembre de 2025 y el inicio de sesión en EDGAR requiere ahora credenciales de cuenta individual de Login.gov con autenticación multifactor. [8][7]

### ¿Cuál es la diferencia entre los formularios 10-K, 10-Q y 8-K?

El Formulario 10-K es el informe anual con estados financieros auditados y el Formulario 10-Q es el informe trimestral con estados financieros no auditados. El Formulario 8-K es un informe de hechos relevantes que divulga eventos o información importante antes del siguiente informe trimestral o anual programado. [5]

## Frases citables

- EDGAR corresponde a las siglas de Electronic Data Gathering, Analysis, and Retrieval. [1]
- Los números CIK asignados por EDGAR siguen siendo exclusivos del declarante y no se reutilizan. [3]
- A fecha de 2026-11-21, las API de data.sec.gov de la SEC no requieren autenticación ni claves de API. [2]
- A fecha de 2026-11-21, la frecuencia máxima de solicitudes de la SEC para el acceso automatizado a EDGAR es de 10 solicitudes por segundo. [3]
- La búsqueda de texto completo de EDGAR cubre las presentaciones enviadas electrónicamente desde 2001. [6]
- La SEC adoptó las enmiendas de normas y formularios de EDGAR Next el 27 de septiembre de 2024. [8]
- La División de Finanzas Corporativas de la SEC afirma que su proceso de revisión de presentaciones no constituye una garantía de que la divulgación sea completa y exacta. [10]
- Un Formulario D debe presentarse dentro de los 15 días posteriores a la primera venta de valores. [11]

## Cronología

- 1992-07-15: El sistema EDGAR operativo queda disponible para los declarantes de forma voluntaria. [9]
- 1993-02-23: La SEC emite comunicados por los que adopta normas provisionales que exigen la presentación electrónica. [9]
- 1993-04-26: Comienza la incorporación gradual de declarantes al sistema EDGAR. [9]
- 1994-12-19: La Resolución n.º 33-7122 de la SEC convierte las normas provisionales de EDGAR en definitivas y aplicables a todos los declarantes nacionales. [9]
- 1999-06-28: EDGAR comienza a aceptar presentaciones reales enviadas en HTML. [9]
- 2002-11-04: Entran en vigor las normas que exigen a los emisores extranjeros presentar sus informes ante la SEC mediante EDGAR. [9]
- 2024-09-27: La SEC adopta las enmiendas de normas y formularios de EDGAR Next sobre acceso de declarantes y gestión de cuentas. [8]
- 2025-03-24: Entran en vigor las enmiendas de EDGAR Next y pasa a ser obligatorio el cumplimiento del Formulario ID modificado. [8]
- 2025-09-15: Pasa a ser obligatorio el cumplimiento de todas las enmiendas de normas y formularios de EDGAR Next. [8]

## Fuentes

1. SEC.gov | About EDGAR. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/about-edgar (consultado 2026-11-21; tier 1: government or public registry)
2. SEC.gov | EDGAR Application Programming Interfaces (APIs). U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-application-programming-interfaces (consultado 2026-11-21; tier 1: government or public registry)
3. SEC.gov | Accessing EDGAR Data. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/accessing-edgar-data (consultado 2026-11-21; tier 1: government or public registry)
4. SEC.gov | Developer Resources. U.S. Securities and Exchange Commission. https://www.sec.gov/about/developer-resources (consultado 2026-11-21; tier 1: government or public registry)
5. SEC.gov | Using EDGAR to Research Investments. U.S. Securities and Exchange Commission. https://www.sec.gov/search-filings/edgar-search-assistance/using-edgar-research-investments (consultado 2026-11-21; tier 1: government or public registry)
6. SEC.gov | EDGAR Full Text Search FAQ. U.S. Securities and Exchange Commission. https://www.sec.gov/edgar/search/efts-faq.html (consultado 2026-11-21; tier 1: government or public registry)
7. SEC.gov | EDGAR Next: Improving Filer Access and Account Management. U.S. Securities and Exchange Commission. https://www.sec.gov/submit-filings/improving-edgar/edgar-next-improving-filer-access-account-management (consultado 2026-11-21; tier 1: government or public registry)
8. SEC.gov | SEC Adopts Improvements to EDGAR System to Enhance Security, Filer Access, and Account Management. U.S. Securities and Exchange Commission. publicado 2024-09-27. https://www.sec.gov/newsroom/press-releases/2024-155 (consultado 2026-11-21; tier 1: government or public registry)
9. Electronic Filing and EDGAR (October 2006). U.S. Securities and Exchange Commission. publicado 2006-10-03. https://www.sec.gov/info/edgar/regoverview.htm (consultado 2026-11-21; tier 1: government or public registry)
10. SEC.gov | Filing Review Process. U.S. Securities and Exchange Commission. https://www.sec.gov/divisions/corpfin/cffilingreview.htm (consultado 2026-11-21; tier 1: government or public registry)
11. SEC.gov | What is Form D?. U.S. Securities and Exchange Commission. https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/what-form-d (consultado 2026-11-21; tier 1: government or public registry)
12. False Claims of SEC Registration | Investor.gov. U.S. Securities and Exchange Commission, Investor.gov. https://www.investor.gov/protect-your-investments/fraud/types-fraud/false-claims-sec-registration (consultado 2026-11-21; tier 1: government or public registry)

## Citar esta página

Mimirwiki. "SEC EDGAR." Versión 869f0a9b, 2026-11-21. https://mimirwiki.com/es/wiki/sec-edgar
