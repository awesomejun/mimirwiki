---
title: "Supercomputadora Lux"
subtitle: "Supercomputadora de inteligencia artificial y computación de alto rendimiento basada en AMD en el Laboratorio Nacional de Oak Ridge"
canonical_url: https://mimirwiki.com/es/wiki/lux-supercomputer
language: es
page_class: entity
revision_sha256: 6ad8afaf7c674f593ead9eb6f6a3575f4a29d61194324610b16176d17b55b85f
date_modified: 2026-11-23
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 8
alternates:
  md: https://mimirwiki.com/es/wiki/lux-supercomputer.md
  txt: https://mimirwiki.com/es/wiki/lux-supercomputer.txt
  json: https://mimirwiki.com/es/wiki/lux-supercomputer.json
  jsonld: https://mimirwiki.com/es/wiki/lux-supercomputer.jsonld
translations:
  en: https://mimirwiki.com/wiki/lux-supercomputer
  ko: https://mimirwiki.com/ko/wiki/lux-supercomputer
  ja: https://mimirwiki.com/ja/wiki/lux-supercomputer
  zh: https://mimirwiki.com/zh/wiki/lux-supercomputer
---

# Supercomputadora Lux

> La supercomputadora Lux es un sistema de inteligencia artificial y computación de alto rendimiento basado en tecnología AMD y construido por Hewlett Packard Enterprise en el Laboratorio Nacional de Oak Ridge del Departamento de Energía de Estados Unidos. Abierta a usuarios científicos el 16 de noviembre de 2026, Lux debutó en el puesto 14 de la lista TOP500 de noviembre de 2026 con 220,79 petaflops en High Performance Linpack. A fecha de 23 de noviembre de 2026, consta de 504 nodos HPE ProLiant Compute XD685 con 4032 GPU AMD Instinct MI355X y respalda la Genesis Mission del DOE.

La supercomputadora Lux (también denominada supercomputadora Lux SI+HPC) es un clúster de inteligencia artificial y computación de alto rendimiento operado por la Oak Ridge Leadership Computing Facility (OLCF) en el Laboratorio Nacional de Oak Ridge (ORNL) del Departamento de Energía de Estados Unidos, en Oak Ridge, Tennessee. Desarrollada mediante una asociación de coinversión público-privada entre el Departamento de Energía, Advanced Micro Devices (AMD) y Hewlett Packard Enterprise (HPE), Lux abrió a usuarios científicos el 16 de noviembre de 2026 como la primera fábrica de IA dedicada para la Genesis Mission del DOE. Ese mismo día, el sistema debutó en el puesto 14 de la 68.ª edición de la lista TOP500 con 220,79 petaflops de rendimiento en High Performance Linpack (HPL). A fecha de 23 de noviembre de 2026, la documentación del OLCF especifica que Lux se compone de 504 nodos HPE ProLiant Compute XD685 equipados con dos procesadores AMD EPYC 9575F de 64 núcleos y ocho GPU AMD Instinct MI355X por nodo (4032 GPU y aproximadamente 1,1 petabytes de memoria HBM3E en total), lo que ofrece un rendimiento pico del sistema de 317 petaflops en FP64, 20 exaflops en FP8 y 40 exaflops en FP4.

**También conocido como:** Lux, Supercomputadora Lux SI+HPC, Clúster AMD Lux SI, ORNL Lux

## Datos clave

- **Operador y ubicación:** Oak Ridge Leadership Computing Facility (OLCF), Laboratorio Nacional de Oak Ridge, Tennessee [1]
- **Debut en el TOP500:** Puesto 14 en la lista TOP500 de noviembre de 2026 (220,79 petaflops en HPL) (al 2026-11-16) [1]
- **Arquitectura del sistema:** 504 nodos HPE ProLiant Compute XD685; 1008 CPU AMD EPYC 9575F; 4032 GPU AMD Instinct MI355X (al 2026-11-23) [4]
- **Rendimiento pico:** 40 EFLOPS (inferencia FP4), 20 EFLOPS (entrenamiento FP8), 317 PFLOPS (simulación FP64) (al 2026-11-23) [3]
- **Reparto anual de horas-nodo:** 3,5 millones de horas-nodo/año: 50 % Genesis Mission del DOE, 50 % AMD y asignaciones de pago a socios (al 2026-11-23) [3]

## Datos básicos

- **Instalación y operador:** Oak Ridge Leadership Computing Facility (OLCF), Laboratorio Nacional de Oak Ridge (ORNL), Oak Ridge, Tennessee, Estados Unidos [1]
- **Patrocinadores y fabricantes:** Departamento de Energía de Estados Unidos (DOE), Advanced Micro Devices (AMD), Hewlett Packard Enterprise (HPE) [1]
- **Anuncio del proyecto:** 27 de octubre de 2025 (junto con la supercomputadora Discovery de 2028) [6]
- **Apertura a usuarios científicos:** 16 de noviembre de 2026 [1]
- **Clasificación TOP500:** Puesto 14 en la 68.ª lista TOP500 (noviembre de 2026) con 220,79 petaflops en HPL (al 2026-11-16) [1]
- **Nodos de cómputo y plataforma:** 504 nodos HPE ProLiant Compute XD685 (al 2026-11-23) [4]
- **CPU por nodo:** 2 CPU AMD EPYC 9575F de 64 núcleos con 3 TB de memoria DDR5 (8 dominios NUMA) (al 2026-11-23) [4]
- **GPU y capacidad HBM:** 4032 GPU AMD Instinct MI355X (8 por nodo, 288 GB de HBM3E a 8 TB/s cada una; ~1,1 PB de HBM en total) (al 2026-11-23) [4]
- **Rendimiento pico del sistema:** 317 PFLOPS (HPC FP64), 20 EFLOPS (entrenamiento IA FP8), 40 EFLOPS (inferencia IA FP4) (al 2026-11-23) [3]
- **Interconexión y almacenamiento:** NIC AMD Pensando 400G Ultra Ethernet por GPU; 8 NVMe locales de 3,2 TB por nodo; sistema de archivos Lustre Orion de 679 PB (al 2026-11-23) [3]
- **Sistema operativo y planificadores:** Red Hat Enterprise Linux (RHEL) 9.8; AMD ROCm; particiones Slurm y Kubernetes (al 2026-11-23) [4]
- **Capacidad anual y asignación:** 3,5 millones de horas-nodo/año (50 % Genesis Mission del DOE, 50 % AMD y asignaciones de pago a socios) (al 2026-11-23) [3]

## Descripción general de la supercomputadora Lux, asociación público-privada y debut en el TOP500

La supercomputadora Lux es un sistema de inteligencia artificial y computación de alto rendimiento (HPC) instalado en la Oak Ridge Leadership Computing Facility (OLCF), una instalación de usuarios de la Oficina de Ciencia del Departamento de Energía de Estados Unidos (DOE) ubicada en el Laboratorio Nacional de Oak Ridge (ORNL), en Oak Ridge, Tennessee.[1][2] En las publicaciones federales estadounidenses y de ORNL de finales de 2026, el sistema recibe la denominación de supercomputadora «SI+HPC», lo que refleja la transición federal establecida por la Orden Ejecutiva 14434 para utilizar el término «Super Intelligence» (SI) en lugar de «inteligencia artificial» (IA).[1][2][7] Lux opera junto a Frontier, el sistema insignia HPE Cray EX235a de 1,353 exaflops del OLCF que superó la barrera de la exaescala en 2022 y ocupó el puesto 3 en la lista TOP500 de noviembre de 2026.[1][3]

El DOE, ORNL, Advanced Micro Devices (AMD) y Hewlett Packard Enterprise (HPE) anunciaron Lux por primera vez el 27 de octubre de 2025 junto con Discovery, una octava supercomputadora insignia del OLCF basada en la arquitectura HPE Cray Supercomputing GX5000 cuya entrega está prevista para 2028.[1][6] A diferencia de las adquisiciones tradicionales de sistemas de liderazgo de varios años, Lux se adquirió y desplegó en aproximadamente un año mediante una asociación de coinversión público-privada entre el DOE y AMD para ampliar la capacidad de IA y computación científica a corto plazo.[1][3][8]

El 16 de noviembre de 2026, ORNL y AMD anunciaron que Lux había abierto a usuarios científicos y debutado en el puesto 14 de la 68.ª edición de la lista TOP500 de las supercomputadoras más potentes del mundo.[1][2][5] En la prueba High Performance Linpack (HPL) empleada para las clasificaciones del TOP500, Lux alcanzó 220,79 petaflops (220 790 billones de operaciones de coma flotante por segundo) frente a un pico teórico en FP64 de 317 petaflops indicado por el OLCF.[1][3][8] El historial del OLCF señala que Lux sucede a siete sistemas insignia desplegados en la instalación desde 2004, cuatro de los cuales (Jaguar, Titan en 2012, Summit en 2018 y Frontier en 2022) ocuparon el puesto 1 del TOP500 en el momento de su lanzamiento.[1][3][6]

## Arquitectura de hardware y especificaciones de nodo de la supercomputadora Lux

La supercomputadora Lux está construida sobre nodos de servidor HPE ProLiant Compute XD685 con refrigeración líquida directa, configurados con procesadores, aceleradores y redes de AMD.[1][4][8] Según la guía de usuario de Lux del OLCF a fecha de 23 de noviembre de 2026, el clúster en producción consta de 504 nodos y 4032 GPU, divididos en nodos de inicio de sesión (`login1` a `login3` en `lux.olcf.ornl.gov`) y nodos de cómputo.[4] Cada nodo de cómputo alberga dos CPU AMD EPYC 9575F de 64 núcleos (128 núcleos de CPU por nodo) que comparten 3 TB de memoria de sistema DDR5 repartidos en ocho dominios de acceso no uniforme a memoria (NUMA), con cada dominio NUMA asignado a 16 hilos de hardware y una GPU.[4]

Cada uno de los 504 nodos aloja ocho GPU AMD Instinct MI355X, lo que suma un total de 4032 aceleradores en todo el sistema.[4] Cada GPU MI355X integra ocho Accelerated Compute Dies (XCD) con 256 unidades de cómputo (64 XCD por nodo) y 288 GB de memoria de alto ancho de banda HBM3E que opera a un ancho de banda máximo de 8 TB/s, proporcionando aproximadamente 1,1 petabytes de HBM3E agregada en todo el clúster.[3][4] Dentro de cada nodo, las ocho GPU MI355X se enlazan mediante conexiones GPU a GPU AMD Infinity Fabric que ofrecen un ancho de banda bidireccional máximo de 153,6 GB/s por conexión.[4] La comunicación entre nodos emplea una tarjeta de interfaz de red (NIC) AMD Pensando 400G Ultra Ethernet por GPU, conectada a través de una infraestructura de conmutación HPE Juniper Networking.[3][5][8]

| Especificación | Por nodo / por GPU | Sistema completo (504 nodos, 4032 GPU) |
| --- | --- | --- |
| Plataforma de servidor | HPE ProLiant Compute XD685 | 504 nodos (inicio de sesión y cómputo) |
| Procesadores anfitriones | 2 CPU AMD EPYC 9575F de 64 núcleos, 3 TB de RAM DDR5 | 1008 CPU (64 512 núcleos de CPU), ~1,5 PB de DDR5 |
| Aceleradores GPU | 8 AMD Instinct MI355X (8 XCD, 256 CU por GPU) | 4032 GPU MI355X (32 256 XCD) |
| Memoria de alto ancho de banda | 288 GB de HBM3E por GPU a 8 TB/s de ancho de banda | ~1,1 PB de HBM3E en total |
| Enlaces intranodo y de red | Infinity Fabric GPU-GPU de 153,6 GB/s; NIC 400G Ultra Ethernet/GPU | 4032 NIC AMD Pensando 400G Ultra Ethernet |
| Rendimiento HPC FP64 | ~78,6 TFLOPS FP64 vectorial por GPU (78 TF en el resumen del sistema) | 317 PFLOPS pico teórico; 220,79 PFLOPS en HPL |
| Rendimiento de IA de baja precisión | 157,3 TFLOPS FP16 vectorial; 5 PFLOPS entrenamiento FP8 por GPU | 20 EFLOPS (entrenamiento FP8); 40 EFLOPS (inferencia FP4) |
| Almacenamiento local del nodo | 8 SSD NVMe de 3,2 TB (>24 TB por nodo) | >12 PB de almacenamiento NVMe local agregado |

Según consta en la guía de usuario de Lux y en la página de resumen del sistema del OLCF a fecha de 23 de noviembre de 2026, cada GPU MI355X individual alcanza una calificación de 78,6 teraflops (redondeados a 78 TF en la página de resumen del sistema) de rendimiento vectorial de doble precisión (FP64) para modelado y simulación, 157,3 teraflops de rendimiento vectorial de media precisión y 5 petaflops de rendimiento de entrenamiento de IA en FP8.[3][4] A nivel de sistema, el OLCF registra picos agregados de 317 petaflops para cargas de trabajo de HPC en FP64, 20 exaflops para entrenamiento de IA en FP8 y 40 exaflops para inferencia de IA en FP4.[3]

## Entorno de software, planificación y almacenamiento de la supercomputadora Lux

La supercomputadora Lux ejecuta Red Hat Enterprise Linux (RHEL) versión 9.8 y utiliza la pila de software abierta AMD ROCm y el entorno de ejecución ROCr, donde cada AMD Instinct MI355X aparece como una GPU individual para los planificadores de trabajos y para `ROCR_VISIBLE_DEVICES`.[1][4] Con el fin de admitir tanto simulaciones tradicionales de supercomputación como cargas de trabajo de IA nativas de la nube sobre el mismo hardware, el OLCF divide Lux en dos particiones de planificación gestionadas por Slurm y Kubernetes.[1][3][4] El tamaño relativo de las particiones de Slurm y Kubernetes se ajusta de forma dinámica a lo largo del tiempo en función de la demanda de los usuarios.[3]

Para la entrada y salida temporal local de alta velocidad, cada nodo de cómputo de Lux incluye ocho unidades de estado sólido Non-Volatile Memory Express (NVMe) de 3,2 TB, lo que ofrece más de 24 TB de almacenamiento NVMe local por nodo.[3][4] Para el almacenamiento paralelo compartido, Lux monta Orion (`/lustre/orion/`), el sistema de archivos paralelo Lustre de todo el centro del OLCF construido sobre hardware HPE ClusterStor.[3][4] La descripción general del sistema del OLCF señala que Orion cuenta con más de 600 petabytes de capacidad, mientras que la guía de usuario de Lux especifica un espacio de nombres utilizable de 679 PB con Progressive File Layout (PFL), que ajusta automáticamente el fraccionamiento de archivos a medida que estos crecen.[3][4]

Dado que Orion se comparte entre Lux, Frontier, el clúster Riker y los nodos de transferencia de datos del OLCF, los equipos de investigación con asignaciones tanto en Frontier como en Lux pueden generar grandes conjuntos de datos de simulación en Frontier, escribirlos directamente en Orion y entrenar modelos de IA sobre esos datos en Lux sin transferencias externas.[3][4] Los usuarios de Lux también tienen acceso al Network File System (NFS) de todo el centro del OLCF para directorios personales y de proyecto, así como a Kronos, el sistema de almacenamiento de archivo cercano en línea del OLCF.[4]

## Política de asignación, acceso comercial y controles de seguridad de la supercomputadora Lux

La supercomputadora Lux proporciona 3,5 millones de horas-nodo al año bajo un modelo de gobernanza por coinversión dividido a partes iguales entre el Departamento de Energía de Estados Unidos y AMD.[1][3] Aproximadamente la mitad de las horas-nodo anuales de Lux se dedican a la Genesis Mission del DOE para investigación científica abierta, mientras que la mitad restante se asigna a AMD para desarrollo y pruebas de tecnología y para el acceso de pago de socios del sector público y privado bajo la tarifa de instalación de usuarios del DOE.[1][3]

Para asignaciones propietarias o de socios de pago, el OLCF exige un compromiso mínimo de 175 000 horas-nodo por periodo de seis meses, con duraciones de proyecto que van de seis meses a cinco años y fechas de inicio flexibles en cualquier mes.[3] Según el OLCF, un compromiso de 175 000 horas-nodo permite respaldar cargas de trabajo como ejecuciones de 400 nodos (3200 GPU) durante un total de 18 días dentro de una ventana de seis meses, o aproximadamente 40 nodos en ejecución continua durante seis meses.[3] Los trabajos de los socios pueden escalar desde ejecuciones en un solo nodo hasta casi la totalidad del sistema, aunque los trabajos de sistema completo tienen un límite ligeramente inferior a 4000 GPU para reservar nodos destinados a servicios persistentes.[3]

A fecha de 23 de noviembre de 2026, Lux opera bajo controles de seguridad DOE Moderate, la misma línea base de seguridad utilizada en Frontier, que permite aplicaciones y datos sujetos a control de exportaciones.[3] El OLCF ha anunciado planes para incorporar controles DOE Moderate-Enhanced en Lux, lo que ampliaría la elegibilidad a cargas de trabajo regidas por el Reglamento sobre el Tráfico Internacional de Armas (ITAR) y a información médica protegida (PHI) conforme a HIPAA.[3]

## Papel de la supercomputadora Lux en la Genesis Mission del DOE y cargas de trabajo científicas

La supercomputadora Lux actúa como la primera fábrica de IA dedicada y la principal incorporación de infraestructura de cómputo para la Genesis Mission del Departamento de Energía de Estados Unidos, una iniciativa nacional que integra supercomputación, modelos fundacionales de IA, sistemas cuánticos e instalaciones experimentales en los 17 laboratorios nacionales del DOE.[1][2][5] Dentro de la Genesis Mission, ORNL también lidera la American Science Cloud (AmSC), una plataforma federada de descubrimiento que conecta la computación, los datos y las redes de alto rendimiento de los laboratorios.[2]

En los anuncios de lanzamiento del 16 de noviembre de 2026, ORNL y AMD detallaron tres asignaciones emblemáticas de investigación de la Genesis Mission que se ejecutan en Lux:[1][2][5][8]

- Diseño de centrales de fusión (FADO): el Fusion Agentic Design Orchestrator emplea flujos de trabajo de IA agéntica para combinar simulaciones de plasma e ingeniería de alta fidelidad, diseño de sistemas de mantenimiento robótico y criterios de fiabilidad, disponibilidad, mantenibilidad e inspeccionabilidad (RAMI) para centrales piloto de fusión.[1][5][8]
- Desarrollo de materiales y fabricación avanzada: una fábrica de modelos fundacionales de IA que entrena modelos fundacionales multimodales a medida para la industria estadounidense, incluida la predicción y el diseño de microestructuras de aleaciones para componentes impresos en 3D y fabricados mediante manufactura aditiva.[1][5][8]
- Sistema terrestre y predicción hídrica a largo plazo: un proyecto de pronóstico con IA que predice la disponibilidad de agua, el caudal y la temperatura de los ríos con semanas o años de antelación para orientar la generación hidroeléctrica y la refrigeración de centrales termoeléctricas en la región de la Autoridad del Valle del Tennessee (TVA).[1][5][8]

Según el comunicado de ORNL del 16 de noviembre de 2026, los investigadores de ORNL lideran seis proyectos adicionales de la Genesis Mission y participan en 30 proyectos multiinstitucionales en la primera fase de la misión, y lideran otros seis proyectos en la segunda fase.[1][2]

## Preguntas frecuentes

### ¿Qué es la supercomputadora Lux y dónde está ubicada?

Lux es una supercomputadora de Super Intelligence (SI, la denominación federal estadounidense para la inteligencia artificial en virtud de la Orden Ejecutiva 14434) y computación de alto rendimiento (HPC) basada en tecnología AMD, operada por la Oak Ridge Leadership Computing Facility (OLCF) en el Laboratorio Nacional de Oak Ridge del Departamento de Energía de Estados Unidos, en Oak Ridge, Tennessee. Construida por Hewlett Packard Enterprise (HPE) mediante una asociación de coinversión público-privada entre el DOE y AMD, Lux abrió a usuarios científicos el 16 de noviembre de 2026. [1][2][4][5]

### ¿Cuál es la clasificación en el TOP500 y el rendimiento pico de Lux?

En la 68.ª edición de la lista TOP500 publicada el 16 de noviembre de 2026, Lux debutó en el puesto 14 a nivel mundial con una puntuación de 220,79 petaflops en la prueba High Performance Linpack (HPL). A fecha de 23 de noviembre de 2026, las especificaciones del sistema del OLCF también indican capacidades pico teóricas de 317 petaflops en FP64 para modelado y simulación, 20 exaflops en FP8 para entrenamiento de IA y 40 exaflops en FP4 para inferencia de IA. [1][3][5]

### ¿Qué hardware y procesadores utiliza cada nodo de cómputo de Lux?

A fecha de 23 de noviembre de 2026, la guía de usuario de Lux del OLCF documenta 504 nodos HPE ProLiant Compute XD685 y 4032 GPU AMD Instinct MI355X. Cada nodo de cómputo integra dos CPU AMD EPYC 9575F de 64 núcleos con 3 TB de memoria de sistema DDR5, ocho GPU AMD Instinct MI355X (cada una con 288 GB de memoria HBM3E a 8 TB/s de ancho de banda y ocho Accelerated Compute Dies), ocho SSD NVMe locales de 3,2 TB (más de 24 TB por nodo) y tarjetas de red AMD Pensando Ultra Ethernet de 400G. [3][4][5]

### ¿Cómo se distribuye el tiempo de cómputo en Lux entre la Genesis Mission y los socios?

El OLCF asigna aproximadamente la mitad de los 3,5 millones de horas-nodo anuales de Lux a la Genesis Mission del Departamento de Energía de Estados Unidos para investigación científica abierta, mientras que la otra mitad queda disponible para AMD con fines de desarrollo y pruebas y para socios públicos o privados mediante uso propietario de pago según la tarifa de instalación de usuarios del DOE. Las asignaciones de pago para socios exigen un compromiso mínimo de 175 000 horas-nodo por semestre y pueden extenderse de seis meses a cinco años bajo controles de seguridad DOE Moderate. [1][3]

### ¿Qué sistema operativo, planificadores y sistemas de almacenamiento admite Lux?

Lux ejecuta Red Hat Enterprise Linux (RHEL) 9.8 con la pila de software abierta AMD ROCm y divide sus nodos entre una partición Slurm para trabajos tradicionales de HPC por lotes y una partición Kubernetes para entrenamiento de IA, inferencia y orquestación agéntica en contenedores. Todas las asignaciones incluyen acceso al sistema de archivos paralelo Lustre Orion del OLCF (espacio de nombres utilizable de 679 PB sobre HPE ClusterStor) y al sistema de almacenamiento de archivo cercano en línea Kronos. [1][3][4]

### ¿Qué proyectos de investigación científica se ejecutan en la supercomputadora Lux?

En los anuncios del 16 de noviembre de 2026, ORNL y AMD destacaron tres proyectos iniciales de la Genesis Mission asignados a Lux: el Fusion Agentic Design Orchestrator (FADO), orientado a integrar simulaciones de HPC y mantenimiento robótico en el diseño de centrales de fusión; una fábrica de modelos fundacionales de IA para el desarrollo de materiales y la fabricación avanzada (como microestructuras de aleaciones impresas en 3D); y un proyecto de predicción del sistema terrestre que pronostica la disponibilidad de agua, el caudal y la temperatura fluvial en la región de la Autoridad del Valle del Tennessee. [1][2][5][8]

## Frases citables

- La supercomputadora Lux abrió a usuarios científicos en el Laboratorio Nacional de Oak Ridge del Departamento de Energía de Estados Unidos el 16 de noviembre de 2026 y debutó en el puesto 14 de la 68.ª lista TOP500 con 220,79 petaflops de rendimiento en High Performance Linpack. [1][2][5]
- A fecha de 23 de noviembre de 2026, la guía de usuario de Lux del OLCF documenta que el sistema consta de 504 nodos HPE ProLiant Compute XD685 que albergan un total de 4032 GPU AMD Instinct MI355X y dos CPU AMD EPYC 9575F de 64 núcleos por nodo. [4]
- Cada GPU AMD Instinct MI355X de Lux contiene 288 GB de memoria HBM3E con un ancho de banda máximo de 8 TB/s repartidos en 8 Accelerated Compute Dies (256 unidades de cómputo), lo que dota al sistema de aproximadamente 1,1 petabytes de capacidad total de HBM3E. [3][4]
- A fecha de 23 de noviembre de 2026, la Oak Ridge Leadership Computing Facility asigna a Lux un rendimiento pico de 40 exaflops en inferencia de IA con FP4, 20 exaflops en entrenamiento de IA con FP8 y 317 petaflops en modelado y simulación de computación de alto rendimiento con FP64. [3]
- La mitad de los 3,5 millones de horas-nodo anuales de Lux se destinan a la Genesis Mission del Departamento de Energía de Estados Unidos, mientras que la otra mitad se reserva para AMD y para asignaciones de pago a socios del sector público o privado, a partir de un compromiso mínimo de 175 000 horas-nodo por semestre. [1][3]
- Los nodos de cómputo de Lux ejecutan Red Hat Enterprise Linux 9.8, dividen los recursos entre particiones de planificación Slurm y Kubernetes, incluyen ocho unidades NVMe locales de 3,2 TB por nodo y montan el sistema de archivos paralelo Lustre Orion del OLCF (espacio de nombres utilizable de 679 PB). [3][4]
- Las primeras asignaciones de la Genesis Mission en Lux incluyen el Fusion Agentic Design Orchestrator (FADO) para el diseño de centrales de fusión, una fábrica de modelos fundacionales para materiales y fabricación avanzada, y la predicción a largo plazo de agua y caudales fluviales en la región de la Autoridad del Valle del Tennessee. [1][2][5][8]
- El Departamento de Energía de Estados Unidos, ORNL, AMD y HPE anunciaron los proyectos de las supercomputadoras Lux y Discovery el 27 de octubre de 2025 en el marco de una asociación de coinversión público-privada. [6]

## Cronología

- 2025-10-27: El Departamento de Energía de Estados Unidos, el Laboratorio Nacional de Oak Ridge, AMD y HPE anuncian los proyectos de las supercomputadoras Lux y Discovery. [6]
- 2026-11-16: La supercomputadora Lux abre a usuarios científicos en ORNL como la primera fábrica de IA de la Genesis Mission del DOE y debuta en el puesto 14 de la 68.ª lista TOP500 con 220,79 petaflops. [1][2][5]
- 2028: Año previsto de entrega de Discovery, la siguiente supercomputadora insignia HPE Cray GX5000 de ORNL anunciada junto con Lux. [1][6]

## Fuentes

1. Lux SI+HPC Supercomputer Debuts in the Top500, Advances Genesis Mission Goals – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). publicado 2026-11-16. https://www.olcf.ornl.gov/2026/11/16/lux-genesis-mission/ (consultado 2026-11-23; tier 1: government or public registry)
2. Lux SI+HPC supercomputer debuts in the Top500, advances Genesis Mission goals – Oak Ridge National Lab. Oak Ridge National Laboratory. publicado 2026-11-16. https://www.ornl.gov/news/lux-sihpc-supercomputer-debuts-in-the-top500-advances-genesis-mission-goals/ (consultado 2026-11-23; tier 1: government or public registry)
3. Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). https://www.olcf.ornl.gov/olcf-resources/compute-systems/lux/ (consultado 2026-11-23; tier 1: government or public registry)
4. Lux User Guide - OLCF User Documentation. Oak Ridge Leadership Computing Facility (ORNL). https://docs.olcf.ornl.gov/systems/lux_user_guide.html (consultado 2026-11-23; tier 1: government or public registry)
5. Lux Supercomputer Opens to Scientific Users at Oak Ridge - AMD Newsroom. Advanced Micro Devices (AMD). publicado 2026-11-16. https://newsroom.amd.com/news/amd-powered-lux-supercomputer-opens-scientific-users/ (consultado 2026-11-23; tier 3: official site)
6. ORNL, AMD, and HPE to Deliver DOE’s Newest AI Supercomputers: Discovery and Lux – Oak Ridge Leadership Computing Facility. Oak Ridge Leadership Computing Facility (ORNL). publicado 2025-10-27. https://www.olcf.ornl.gov/2025/10/27/ornl-amd-and-hpe-to-deliver-does-newest-ai-supercomputers-discovery-and-lux/ (consultado 2026-11-23; tier 1: government or public registry)
7. Oak Ridge National Laboratory unveils Lux supercomputer - DCD. Data Center Dynamics. publicado 2026-11-17. https://www.datacenterdynamics.com/en/news/oak-ridge-national-laboratory-unveils-lux-supercomputer/ (consultado 2026-11-23; tier 2: academic or news)
8. AMD opens up its new Lux supercomputer, powering everything from nuclear fusion to weather predictions | TechRadar. TechRadar. publicado 2026-11-21. https://www.techradar.com/pro/amd-opens-up-its-new-lux-supercomputer-powering-everything-from-nuclear-fusion-to-weather-predictions (consultado 2026-11-23; tier 2: academic or news)

## Citar esta página

Mimirwiki. "Supercomputadora Lux." Versión 6ad8afaf, 2026-11-23. https://mimirwiki.com/es/wiki/lux-supercomputer
