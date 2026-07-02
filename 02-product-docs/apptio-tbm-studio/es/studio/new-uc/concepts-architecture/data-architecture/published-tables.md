---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas publicadas"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
  - "Tablas y tipos de tablas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas publicadas

**Objetivo:** Compartir datos modelados con sistemas externos en un formato controlado y con un esquema estable.

Las tablas publicadas son el principal mecanismo de exportación de datos en TBM Studio. Proporcionan un conjunto de datos estable y alineado con el modelo que los sistemas externos (como Power BI, Snowflake o los lagos de datos empresariales) pueden recuperar mediante programación a través de una API: URL.

Características principales de las tablas publicadas:

- Son entidades independientes de los informes y las tablas de transformación, diseñadas específicamente para la exportación de datos.
- Reflejan valores calculados del modelo, no valores preliminares de las ramas de desarrollo.
- Se actualizan automáticamente tras completar con éxito los cálculos en el entorno de pruebas o en producción.
- Por defecto, las tablas publicadas se calculan previamente, por lo que están listas de inmediato cuando se solicitan a través de la API.
- Solo los administradores pueden crear o modificar tablas publicadas.

Las tablas publicadas se crearon para sustituir el antiguo método de generar informes bloqueados destinados exclusivamente a la exportación de datos, lo que generaba una carga innecesaria en el sistema durante los cálculos.

Nota:

**Cuándo utilizar tablas publicadas**

Utilice las tablas publicadas cuando necesite importar los resultados del modelo de costes a plataformas de análisis externas, almacenes de datos o sistemas de planificación. Ofrecen un esquema estable que no cambia a medida que evolucionan los informes, lo que los hace ideales para los procesos de integración automatizados

**Tema principal:** [Tablas y tipos de tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
