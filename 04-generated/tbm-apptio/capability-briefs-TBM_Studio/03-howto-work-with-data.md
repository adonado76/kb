---
tbm_concept: "How-To: Work with Data (importación, transformación, captura manual, seguridad y exportación de datos en Data Studio)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/data-import-management.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-upload-data-from-files-excel-csv.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-connect-external-data-sources-datalink.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-version-tables-monthly-data.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-transform-enrich.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-clean-map-using-map-columns.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-join-from-multiple-sources.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-apply-formulas-transform.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-filter-by-date-partition.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-append-multiple-sources.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-manual-entry.md
  - kb/02-product-docs/apptio-tbm-studio/en/entry-create-blank-editable-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/entry-create-enriched-editable-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/entry-configure-dropdowns-validation.md
  - kb/02-product-docs/apptio-tbm-studio/en/entry-set-up-editable-table-publishing.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-security.md
  - kb/02-product-docs/apptio-tbm-studio/en/ds-how-guide-1-apply-row-level-security-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/security-apply-row-level.md
  - kb/02-product-docs/apptio-tbm-studio/en/security-how-guide-2-control-access-user-mapping.md
  - kb/02-product-docs/apptio-tbm-studio/en/security-best-practices-row-level.md
  - kb/02-product-docs/apptio-tbm-studio/en/data-export.md
  - kb/02-product-docs/apptio-tbm-studio/en/export-how-guide-configure-published-tables.md
  - kb/02-product-docs/apptio-tbm-studio/en/export-how-guide-data-via-api.md
last_updated: "2026-07-07"
---
# How-To: Work with Data — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Antes de que exista un modelo de asignación o un reporte, tiene que existir un dato bien cargado, limpio, y correctamente versionado en el tiempo. Este capítulo es el manual operativo completo de Data Studio: cinco bloques que cubren desde la primera carga de un archivo Excel hasta la exportación programática vía API.

## Cómo lo resuelve Apptio TBM Studio

### Data Import & Management — la entrada de datos, en tres formas

**Upload Data from Files** — la vía manual: crear tabla, subir Excel/CSV, configurar fila de inicio, tipos de columna, y — desde v12.1 — **validación de esquema en cargas subsecuentes** (detecta columnas agregadas/eliminadas/con tipo cambiado, y validación de cardinalidad: única o duplicada). Detalle técnico no trivial: el nombre del archivo solo puede tener un punto antes de la extensión, o falla la carga.

**Connect to External Data Sources (DataLink)** — la vía automatizada, documentada en detalle para la integración con ServiceNow (Apps & Services TCO): requiere reportes específicos configurados en TBM Studio con columnas obligatorias (Cost Model, Fiscal period vía fórmula, Business Application, Amount), luego una conexión DataLink con autenticación Basic u OAuth 2.0, agente cloud u on-premise, y programación por tiempo o por evento (encadenada a otra conexión).

**Version Tables for Monthly Data** — el mecanismo de series de tiempo: cuatro variantes de ciclo de refresco (Monthly versions/update monthly, Yearly versions/update monthly — rolling year, Yearly versions/update at start of year — estático, Yearly con carryover automático). Regla operativa importante: los cambios de esquema **solo aplican hacia adelante desde el período seleccionado**, nunca retroactivamente — hay que visitar cada período histórico manualmente si se necesita corregirlo.

### Transform & Enrich Data — cinco operaciones de pipeline, secuenciales

**Map Columns** (alinear datos externos a esquemas maestros canónicos), **Join** (combinar múltiples fuentes), **Apply formulas** (enriquecer con cálculos), **Filter by date partition** (distribuir automáticamente información entre períodos), y **Append** (combinar datasets de la misma estructura) — cada paso se ejecuta secuencialmente de arriba hacia abajo en el pipeline visual, el mismo concepto de "transform pipeline" introducido en Getting Started.

### Manual Data Entry — cuando el dato no viene de un sistema fuente

**Blank Editable Tables** (tabla vacía con columna de llave primaria por defecto, esquema configurado manualmente) vs. **Enriched Editable Tables** (filas generadas automáticamente desde una transform table existente, permitiendo a un usuario de negocio *enriquecerlas* con clasificaciones o anotaciones adicionales sin tocar la fuente original) — una distinción de arquitectura importante: la segunda es la vía correcta cuando se quiere que un usuario de negocio anote datos ya existentes, no cree datos desde cero.

**Configure Dropdowns and Validation** añade reglas de validez a las columnas de estas tablas editables. **Set Up Editable Table Publishing** controla cómo esos datos capturados manualmente fluyen hacia las transform tables y, eventualmente, hacia el modelo de costo — con opciones de publicación manual, programada, o automatizada.

### Data Security — seguridad a nivel de fila (RLS)

Dos guías paso a paso (Apply Row-Level Security to Tables, Control Access with User Mapping) más un documento de mejores prácticas para planear la estrategia de RLS antes de implementarla — mismo principio de seguridad granular ya visto conceptualmente en el resto del portafolio Apptio, aquí aplicado a nivel de tabla de datos, no solo de reporte.

### Data Export — dos vías de salida

**Published Tables** — un dataset estable, actualizado automáticamente, que sistemas externos (herramientas de BI, data warehouses, u otros proyectos de Costing & Planning) pueden consultar directamente.

**Export Data via API** — acceso programático flexible, bajo demanda, para integraciones personalizadas, pipelines ETL o scripts de automatización — la contraparte de solo-lectura del API de carga ya visto en Getting Started.

## Por qué importa en una conversación con el cliente

La regla de que los cambios de esquema solo aplican hacia adelante (no retroactivamente) es un detalle operativo que vale la pena anticipar en cualquier discovery de migración de datos históricos — un cliente que espera corregir automáticamente el pasado al cambiar un esquema se llevará una sorpresa si no se le explica esto primero.

La distinción entre Blank y Enriched Editable Tables es clave para diseñar correctamente cualquier flujo de captura manual: si el objetivo es que un dueño de negocio *anote* datos que ya existen en el sistema (no que cree datos nuevos), la respuesta correcta es siempre Enriched, no Blank — una elección de diseño que vale la pena confirmar explícitamente durante cualquier fase de configuración.

La integración con ServiceNow vía DataLink es un gancho de conversación fuerte para cualquier cliente que ya use ServiceNow como CMDB/ITSM (el mismo patrón de integración ya documentado extensamente en Costing Standard) — vale la pena preguntar temprano si el cliente ya tiene el Apps & Services TCO app instalado en su instancia de ServiceNow.

## Documentos fuente

- Data Import & Management (índice) — `kb/02-product-docs/apptio-tbm-studio/en/data-import-management.md`
- Upload Data from Files (Excel, CSV) — `kb/02-product-docs/apptio-tbm-studio/en/management-upload-data-from-files-excel-csv.md`
- Connect to External Data Sources (DataLink) — `kb/02-product-docs/apptio-tbm-studio/en/management-connect-external-data-sources-datalink.md`
- Version Tables for Monthly Data — `kb/02-product-docs/apptio-tbm-studio/en/management-version-tables-monthly-data.md`
- Transform & Enrich Data (índice) — `kb/02-product-docs/apptio-tbm-studio/en/data-transform-enrich.md`
- Clean and map data using Map Columns — `kb/02-product-docs/apptio-tbm-studio/en/data-clean-map-using-map-columns.md`
- Join data from multiple sources — `kb/02-product-docs/apptio-tbm-studio/en/data-join-from-multiple-sources.md`
- Apply formulas to transform data — `kb/02-product-docs/apptio-tbm-studio/en/data-apply-formulas-transform.md`
- Filter data by date partition — `kb/02-product-docs/apptio-tbm-studio/en/data-filter-by-date-partition.md`
- Append multiple data sources — `kb/02-product-docs/apptio-tbm-studio/en/data-append-multiple-sources.md`
- Manual Data Entry (índice) — `kb/02-product-docs/apptio-tbm-studio/en/data-manual-entry.md`
- Create Blank Editable Tables — `kb/02-product-docs/apptio-tbm-studio/en/entry-create-blank-editable-tables.md`
- Create Enriched Editable Tables — `kb/02-product-docs/apptio-tbm-studio/en/entry-create-enriched-editable-tables.md`
- Configure Dropdowns and Validation — `kb/02-product-docs/apptio-tbm-studio/en/entry-configure-dropdowns-validation.md`
- Set Up Editable Table Publishing — `kb/02-product-docs/apptio-tbm-studio/en/entry-set-up-editable-table-publishing.md`
- Data Security (índice) — `kb/02-product-docs/apptio-tbm-studio/en/data-security.md`
- How-To Guide 1: Apply Row-Level Security to Tables — `kb/02-product-docs/apptio-tbm-studio/en/ds-how-guide-1-apply-row-level-security-tables.md`
- Apply row-level security — `kb/02-product-docs/apptio-tbm-studio/en/security-apply-row-level.md`
- How-To Guide 2: Control Access with User Mapping — `kb/02-product-docs/apptio-tbm-studio/en/security-how-guide-2-control-access-user-mapping.md`
- Best Practices for Row-Level Security — `kb/02-product-docs/apptio-tbm-studio/en/security-best-practices-row-level.md`
- Data Export (índice) — `kb/02-product-docs/apptio-tbm-studio/en/data-export.md`
- How-To Guide: Configure Published Tables — `kb/02-product-docs/apptio-tbm-studio/en/export-how-guide-configure-published-tables.md`
- How-To Guide: Export Data via API — `kb/02-product-docs/apptio-tbm-studio/en/export-how-guide-data-via-api.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
