---
concept: "Concepts: Data Architecture — el pipeline de tres etapas, tipos de tabla, versionado por período de tiempo, y frescura/validación de datos"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/da-data-architecture.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-data-flow-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-tables-table-types.md
  - kb/02-product-docs/apptio-tbm-studio/en/types-transform-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/types-editable-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/types-how-editable-tables-fit-in-data-flow.md
  - kb/02-product-docs/apptio-tbm-studio/en/types-published-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/types-table-type-decision-matrix.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-transform-pipeline-concepts.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-versioning-time-periods.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-data-freshness-validation.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-data-integration-patterns.md
last_updated: "2026-07-07"
---
# Concepts: Data Architecture — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Mientras el capítulo "How-To: Work with Data" documenta el *cómo* operativo, este capítulo documenta el *por qué* arquitectónico: cómo está diseñado el flujo de datos internamente, y por qué las decisiones de tipo de tabla y versionado importan más allá del paso a paso.

## Cómo lo resuelve Apptio TBM Studio

**El pipeline de tres etapas, con puntos de transformación clave documentados:**

Data Studio (donde el dato entra, se limpia, transforma y prepara) → Model Studio (donde ocurre la asignación de costo, aplicando reglas de negocio a las tablas ya preparadas) → Report Studio (donde se visualiza y analiza el resultado; el dato también puede salir de la plataforma vía Published Tables y APIs).

**Stored data vs. Calculated data — una distinción con implicación práctica directa.** Las tablas fuente y transformadas en Data Studio son datos **almacenados** (persisten en la base de datos del proyecto una vez cargados o guardados, incluyendo entradas de tablas editables). Las asignaciones del modelo y las salidas de reporte son datos **calculados** — se generan durante operaciones de build (Staging o Production) y reflejan el estado actual de las transformaciones, reglas del modelo y configuración de período. Implicación práctica: un dato almacenado persiste hasta que alguien lo cambie explícitamente; un dato calculado cambia automáticamente cuando cambia cualquiera de sus insumos.

**Cinco tipos de tabla, con un decision matrix explícito de "qué necesita" a "qué tabla usar":**
- **Source / File Tables** — punto de entrada para datos externos vía archivo o conexión de base de datos, con auto-detección de tipo de columna (Label/Numeric/State).
- **Transform Tables** — la salida de un pipeline de transformación; se pueden encadenar (transform tables derivadas de otras transform tables) para refinar datos progresivamente.
- **Editable Tables** — el puente entre pipelines automatizados y el juicio humano necesario (clasificación de centro de costo, mapeo de labor, anotaciones de presupuesto).
- **Published Tables** — el mecanismo primario de salida de datos: dataset estable, alineado al modelo, que sistemas externos (Power BI, Snowflake, data lakes empresariales) consultan vía URL de API. Detalle importante: reflejan **valores calculados del modelo, no valores en borrador de ramas de desarrollo**.

**Transform Pipeline Concepts — el motor de procesamiento secuencial.** Cada paso de transformación ejecuta en secuencia, de arriba hacia abajo; la salida de un paso es la entrada del siguiente. Reglas de orden documentadas explícitamente: un paso Filter antes de un Join reduce filas antes de la operación de unión (mejorando performance); un paso Formula después de un Join puede referenciar columnas de ambas tablas unidas; Map Columns típicamente aparece tarde en el pipeline, después de limpieza y enriquecimiento. Los pasos Source, Upload, Import y Table tienen posiciones fijas que no se pueden reordenar.

**Data Lineage — trazabilidad de origen a resultado final**, con tres usos prácticos documentados: precisión (rastrear hacia atrás un número inesperado hasta su origen — dato fuente, paso de transformación, o regla de asignación), auditabilidad (finanzas y cumplimiento necesitan verificar que las asignaciones se remontan a transacciones fuente), y análisis de impacto (antes de cambiar una transformación, seguir el linaje hacia adelante para ver qué objetos del modelo y reportes se verán afectados).

**Mejores prácticas de diseño de transformaciones, documentadas explícitamente**: centralizar en un master transform único (ej. un "Cost Source Master" que unifique múltiples archivos fuente, con transformaciones y objetos del modelo posteriores referenciando ese master, no archivos individuales); evitar duplicar lógica (crear una transformación intermedia compartida en vez de repetir lógica en cada pipeline); validar tipos de columna temprano; nomenclatura descriptiva; y monitorear tablas no utilizadas (TBM Studio puede identificar tablas no referenciadas por ningún reporte u objeto del modelo).

**Versioning and Time Periods — la plataforma es fundamentalmente mes-céntrica.** Casi todo (datos, modelos, reportes) opera en el contexto de un período mensual específico. Concepto clave: Data Studio impone un único período activo para vistas previas de transformación — no se pueden previsualizar múltiples meses simultáneamente en el espacio de trabajo de transformación; la agregación multi-período ocurre en la capa de reporte, no en Data Studio. El calendario fiscal soporta año calendario estándar o patrones personalizados (ej. agrupación 4-4-5 semanas), con la definición de año fiscal identificable por período de inicio o de fin. **Los períodos cerrados bloquean cargas de datos y recálculos del modelo** — protección explícita contra modificación accidental de datos financieros ya finalizados.

**Data Freshness and Validation** — monitoreo de si el dato se actualizó según su calendario de refresco esperado (crítico: si el archivo de enero no se carga y el modelo calcula usando datos de diciembre, las asignaciones resultantes serán engañosas). Validación en varios niveles: detección de tipo de columna, campos requeridos (su ausencia genera errores de pipeline que bloquean cálculos del modelo posteriores), y validación de cardinalidad.

**Data Integration Patterns** — la elección correcta de mecanismo de entrada (archivo, DataLink, API, tablas editables como patrón de integración para datos donde el juicio humano es la fuente primaria) depende de volumen de datos, frecuencia de actualización, capacidad técnica, y requisitos de gobernanza — con una guía de decisión explícita para elegir entre ellos.

## Por qué importa en una conversación con el cliente

La distinción Stored vs. Calculated data es fundamental para cualquier conversación de troubleshooting con el cliente: un número "incorrecto" en un dato almacenado requiere corregir la fuente; un número "incorrecto" en un dato calculado probablemente requiere revisar la regla de asignación o esperar el siguiente build — confundir estas dos categorías genera diagnósticos equivocados.

El bloqueo de períodos cerrados es un argumento de gobernanza financiera fuerte para cualquier cliente preocupado por modificación accidental de datos ya cerrados contablemente — vale la pena mencionarlo proactivamente en conversaciones con Finanzas sobre integridad de datos históricos.

La recomendación de centralizar en un "master transform" único es un principio de arquitectura que vale la pena aplicar desde el diseño inicial de cualquier implementación — evita la proliferación de lógica de transformación duplicada que se vuelve costosa de mantener a medida que el modelo crece.

## Documentos fuente

- Data Architecture (índice) — `kb/02-product-docs/apptio-tbm-studio/en/da-data-architecture.md`
- Data Flow Overview — `kb/02-product-docs/apptio-tbm-studio/en/architecture-data-flow-overview.md`
- Tables and Table Types (índice) — `kb/02-product-docs/apptio-tbm-studio/en/architecture-tables-table-types.md`
- Transform Tables — `kb/02-product-docs/apptio-tbm-studio/en/types-transform-tables.md`
- Editable Tables — `kb/02-product-docs/apptio-tbm-studio/en/types-editable-tables.md`
- How Editable Tables Fit in the Data Flow — `kb/02-product-docs/apptio-tbm-studio/en/types-how-editable-tables-fit-in-data-flow.md`
- Published Tables — `kb/02-product-docs/apptio-tbm-studio/en/types-published-tables.md`
- Table Type Decision Matrix — `kb/02-product-docs/apptio-tbm-studio/en/types-table-type-decision-matrix.md`
- Transform Pipeline Concepts — `kb/02-product-docs/apptio-tbm-studio/en/architecture-transform-pipeline-concepts.md`
- Versioning and Time Periods — `kb/02-product-docs/apptio-tbm-studio/en/architecture-versioning-time-periods.md`
- Data Freshness and Validation — `kb/02-product-docs/apptio-tbm-studio/en/architecture-data-freshness-validation.md`
- Data Integration Patterns — `kb/02-product-docs/apptio-tbm-studio/en/architecture-data-integration-patterns.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
