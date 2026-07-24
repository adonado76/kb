---
concept: "Working with Tables (el control de tabla unificado usado en todo el producto: agrupación, columnas, ordenamiento, y agrupación de períodos de tiempo)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - cloudability-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/tables-overview.md
last_updated: "2026-07-10"
---
# Working with Tables — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Todas las tablas de Financial Planning (las líneas de forecast, presupuesto, detalles de varianza ya vistos en Working with Plans) usan el mismo control de tabla subyacente — un capítulo corto pero de alto valor práctico, ya que dominar esta interacción una sola vez transfiere a cada tabla del producto. Algunas tablas específicas pueden no exponer todas las interacciones documentadas aquí.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Agrupación de filas (Row Group)** — arrastrar una dimensión (no una métrica) a la barra de agrupación resume filas por esa dimensión, con las filas del mismo valor consolidadas en una fila de grupo expandible. Múltiples dimensiones se agrupan de forma anidada.

**Agrupación de columnas — exclusiva de métricas de serie de tiempo.** Análogo a la agrupación de filas pero aplicado a columnas: permite colapsar/expandir grupos de columna para mostrar los períodos individuales resumidos. La **herramienta de agrupación de columnas** en la barra lateral controla explícitamente qué agrupaciones de período mostrar u ocultar — por ejemplo, ocultar un trimestre muestra meses resumidos en años; ocultar un mes muestra solo trimestres resumidos en años; ocultar trimestres y años muestra solo meses. Esta es la mecánica exacta detrás de las vistas mensual/trimestral/anual ya vistas en los reportes de Analyzing Plan Performance.

**Menú de columna** — accesible al pasar el cursor sobre el encabezado de columna (ícono de tres barras apiladas): auto-ajuste de tamaño, agrupación rápida, filtros de columna, y selección de columnas adicionales a mostrar/ocultar.

**Ordenamiento en tres estados** — un clic ordena ascendente, un segundo clic cambia a descendente, un tercer clic limpia el ordenamiento.

**Reordenamiento y redimensionamiento de columna** — arrastrar y soltar el encabezado para reordenar; arrastrar el separador de columna para redimensionar.

**Barra lateral** — acceso rápido unificado a mostrar/ocultar columnas, filtros de columna, y herramientas de agrupación.

## Por qué importa en una conversación con el cliente

Este capítulo es el mejor candidato para una demo rápida de "cómo navegar el producto" al inicio de cualquier sesión de capacitación de usuario final — dominar la interacción de tabla una sola vez transfiere directamente a cada pantalla del producto (Forecast, Budget, Variance Details), reduciendo significativamente la curva de aprendizaje.

La mecánica de agrupación de columnas por período (colapsar mes → trimestre → año) es exactamente el mecanismo detrás del selector de granularidad ya visto en los reportes de varianza (Current Month = diario, Current Quarter/Year = mensual) — vale la pena explicar esta conexión explícitamente para que el usuario entienda que no son funcionalidades separadas, sino la misma mecánica de tabla aplicada consistentemente.

## Documentos fuente

- Overview — `kb/02-product-docs/apptio-financial-planning/en/tables-overview.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
