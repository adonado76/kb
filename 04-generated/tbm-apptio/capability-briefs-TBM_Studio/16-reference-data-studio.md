---
concept: "Reference: Data Studio — referencia técnica completa de tablas, pasos de transformación, Published Tables, DataLink, interfaz de workspace, operaciones de tabla, manejo de errores y parseo de Excel"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/reference-data-studio.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/tables-creating.md
  - kb/02-product-docs/apptio-tbm-studio/en/tables-table-source-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/tables-data-refresh-cycles.md
  - kb/02-product-docs/apptio-tbm-studio/en/tables-table-column-types.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-transform-steps.md
  - kb/02-product-docs/apptio-tbm-studio/en/steps-adding-transform.md
  - kb/02-product-docs/apptio-tbm-studio/en/steps-complete-transform-step-reference.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-formulas-quick.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-published-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-datalink-connections.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-data-workspace-interface.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-table-operations.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-error-handling.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-enhanced-excel-parsing.md
last_updated: "2026-07-07"
---
# Reference: Data Studio — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

A diferencia de "How-To: Work with Data" (procedimientos paso a paso) y "Concepts: Data Architecture" (por qué está diseñado así), este capítulo es **referencia técnica de consulta rápida**: cada opción, cada tipo, cada configuración de Data Studio documentada de forma exhaustiva para lookup, no para lectura lineal.

## Cómo lo resuelve Apptio TBM Studio

**Tables** — tipos de tabla, opciones de fuente, ciclos de refresco de datos, y tipos de columna, en formato de referencia consultable en lugar de tutorial.

**Transform Steps** — referencia completa de cada tipo de paso de transformación disponible en el pipeline, más el procedimiento de agregar un paso — el catálogo exhaustivo detrás de los cinco pasos ya vistos operativamente en "How-To: Work with Data" (Map Columns, Join, Formulas, Filter, Append).

**Formulas Quick Reference** — acceso rápido a sintaxis de fórmula, complementario al catálogo completo de funciones que se documenta por separado en la categoría 19 de este proyecto.

**Published Tables** — mecanismo dedicado de exportación de datos **sin usar reportes**. Dos métodos de creación documentados (Crear Nuevo desde Home > New > Published Table, y un segundo método no detallado en este extracto). Configuraciones de pre-cálculo: **Active** (el sistema pre-calcula la tabla, lista ante cualquier llamada de API — comportamiento por defecto) vs. una alternativa de cálculo bajo demanda.

**DataLink Connections** — conectividad de ingreso y egreso de datos entre TBM Studio y sistemas externos. La integración con ServiceNow está documentada con las versiones compatibles explícitas: **Quebec, Paris, Orlando** — un detalle concreto de compatibilidad a verificar en cualquier discovery técnico con un cliente que use ServiceNow.

**Data Workspace Interface** — referencia del Project Explorer (navegación y gestión de todos los documentos del proyecto, por tipo) y del panel de Transform Steps (ver y modificar el pipeline de una tabla).

**Table Operations** — operaciones de columna y fila documentadas exhaustivamente, incluyendo **Truncate** para tablas editables (disponible desde v12.11.4), con una tabla de "qué tipo de tabla, qué efecto de truncado" — un detalle de versión que vale la pena confirmar contra la versión real del cliente.

**Error Handling** — catálogo de tipos de error comunes (errores de fuente, con causa y resolución documentadas sistemáticamente).

**Enhanced Excel Parsing** — el detalle técnico más específico de esta categoría: una tabla de manejo de formato comparando el parser antiguo vs. el nuevo, y **la conversión de fecha/hora explicada con las dos referencias temporales relevantes** — el sistema de fecha de Excel (números seriales secuenciales empezando en 1 = 1 de enero de 1900) vs. Unix Epoch (empieza el 1 de enero de 1970, 00:00:00 UTC) — el tipo de detalle que solo importa cuando una fecha se ve "corrida" varios días o décadas después de una carga, y resulta ser un problema de sistema de referencia, no de dato corrupto.

## Por qué importa en una conversación con el cliente

Esta categoría, más que las de How-To o Concepts, es material de referencia para el equipo técnico del cliente durante y después de la implementación — vale la pena posicionarla explícitamente como "el manual que su administrador va a consultar constantemente", no como contenido de una sola lectura.

El detalle de conversión de fecha Excel vs. Unix Epoch es exactamente el tipo de información que ahorra horas de troubleshooting cuando aparece por primera vez un problema real de fechas "corridas" tras una carga — vale la pena tenerlo a mano durante cualquier fase de validación de datos con fechas.

Las versiones específicas de ServiceNow compatibles con DataLink (Quebec, Paris, Orlando) son información de scoping técnico concreta a confirmar antes de prometer esta integración en cualquier propuesta — si el cliente está en una versión más reciente o más antigua de ServiceNow, vale la pena validar compatibilidad explícitamente.

## Documentos fuente

- Data Studio Reference (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-data-studio.md`
- Tables (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-tables.md`
- Creating Tables — `kb/02-product-docs/apptio-tbm-studio/en/tables-creating.md`
- Table Source Options — `kb/02-product-docs/apptio-tbm-studio/en/tables-table-source-options.md`
- Data Refresh Cycles — `kb/02-product-docs/apptio-tbm-studio/en/tables-data-refresh-cycles.md`
- Table Column Types — `kb/02-product-docs/apptio-tbm-studio/en/tables-table-column-types.md`
- Transform Steps (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-transform-steps.md`
- Adding Transform Steps — `kb/02-product-docs/apptio-tbm-studio/en/steps-adding-transform.md`
- Complete Transform Step Reference — `kb/02-product-docs/apptio-tbm-studio/en/steps-complete-transform-step-reference.md`
- Formulas Quick Reference — `kb/02-product-docs/apptio-tbm-studio/en/reference-formulas-quick.md`
- Published Tables — `kb/02-product-docs/apptio-tbm-studio/en/reference-published-tables.md`
- DataLink Connections — `kb/02-product-docs/apptio-tbm-studio/en/reference-datalink-connections.md`
- Data Workspace Interface — `kb/02-product-docs/apptio-tbm-studio/en/reference-data-workspace-interface.md`
- Table Operations — `kb/02-product-docs/apptio-tbm-studio/en/reference-table-operations.md`
- Error Handling — `kb/02-product-docs/apptio-tbm-studio/en/reference-error-handling.md`
- Enhanced Excel Parsing — `kb/02-product-docs/apptio-tbm-studio/en/reference-enhanced-excel-parsing.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
