---
concept: "IBM Apptio Report Studio (New) — Components (controles interactivos) y Visualizations (tablas, KPIs, gráficos) de la interfaz de reporte moderna"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/components-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-slicer.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-hierarchical-slicer.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-column-picker.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-quick-pivot.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-html.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-group.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-tabs.md
  - kb/02-product-docs/apptio-tbm-studio/en/tabs-tab-visibility-rules.md
  - kb/02-product-docs/apptio-tbm-studio/en/components-button-component.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-kpi.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-table.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-column-overflow-menu.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-renaming-columns-in.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-hiding-intermediate-dimensions.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-show-values.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-tree-view.md
  - kb/02-product-docs/apptio-tbm-studio/en/table-export-excel.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-editable-table.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-bar-charts.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-column-charts.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-line-charts.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-pie-charts.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-column-line-overlay-charts.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-heatmaps.md
  - kb/02-product-docs/apptio-tbm-studio/en/visualizations-bubble-charts.md
last_updated: "2026-07-07"
---
# IBM Apptio Report Studio (New) — Components & Visualizations — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Con los conceptos base del New Report Studio ya cubiertos, este capítulo documenta su catálogo completo de piezas de construcción: los **componentes** (controles interactivos y de layout) y las **visualizaciones** (formas de presentar datos).

## Cómo lo resuelve Apptio TBM Studio

### Components — controles interactivos y de organización

**Slicer** — filtra el reporte por una sola dimensión (Application Family, Region, Cost Centre, Time), cambiando rápidamente el contexto de los datos visibles.

**Hierarchical Slicer** — extiende el Slicer a estructuras jerárquicas: inicialmente solo se muestran los valores de Nivel 1, con búsqueda soportada dentro de cada nivel de la jerarquía — útil para datasets grandes con estructura organizacional profunda.

**Column Picker** — permite que el usuario final muestre u oculte columnas de tabla según su necesidad. Detalle técnico refinado: cuando una visualización incluye dimensiones seleccionables vía Column Picker, el panel de datos ahora muestra **dimensiones virtuales ("ghost")** en la sección de Filas, permitiendo configurar navegación de drill-through sobre esas dimensiones sin necesidad de agregarlas primero explícitamente a la visualización.

**Quick Pivot** — agrupa datos dinámicamente por distintas dimensiones sobre la marcha, sin reconstruir el reporte.

**HTML** — texto formateado (encabezados, párrafos, listas), hipervínculos internos/externos, e imágenes o iconos estáticos.

**Group** — agrupa múltiples componentes (selección múltiple con Shift + clic, luego Ctrl/Cmd+G) para mantener contenido relacionado unido, moverlos juntos, o simplificar layouts complejos — con opción de "framed group" con propiedades de formato propias.

**Tabs** — divide un reporte grande o complejo en secciones lógicas, con estilo global configurable (color de barra y fondo de pestaña) y, por pestaña individual, **reglas de visibilidad** propias (documentadas en su propio artículo — probablemente condicionadas por rol o filtro).

**Button** — navegación entre reportes u otras acciones activadas por el usuario.

### Visualizations — nueve tipos soportados

**KPI** — indicador de valor único destacado.

**Table** — la visualización más rica en funcionalidad propia, con seis capacidades documentadas por separado: menú de desborde de columna, renombrar columnas dentro del reporte (sin tocar el esquema subyacente), ocultar dimensiones intermedias, mostrar valores de forma condicional, **vista de árbol** (jerárquica), y exportación directa a Excel.

**Editable Table** — la versión interactiva de captura de datos dentro del New Report Studio, equivalente funcional a los Editable Components ya documentados para el Report Studio clásico.

**Seis tipos de gráfico**: Bar, Column, Line, Pie, **Column + Line (Overlay)** — combina dos tipos de visualización en un mismo gráfico, típicamente para comparar una métrica de barra contra una tendencia de línea —, Heatmaps (patrones de intensidad por color) y Bubble Charts (tres dimensiones de dato: posición X/Y más tamaño de burbuja).

**Todas las visualizaciones comparten un conjunto común de propiedades**, documentado una sola vez y referenciado desde cada página individual — reduce duplicación de documentación y da consistencia de configuración entre visualizaciones.

## Por qué importa en una conversación con el cliente

El catálogo completo de componentes y visualizaciones es el mejor recurso para una sesión de diseño de reporte con un cliente: en lugar de describir capacidades en abstracto, se puede recorrer visualmente cada componente y visualización disponible, ayudando al cliente a especificar exactamente qué necesita en su primer conjunto de reportes.

Las dimensiones virtuales ("ghost") del Column Picker son un detalle técnico que vale la pena mencionar a cualquier arquitecto de reportes del cliente preocupado por la complejidad de configurar drill-through sobre columnas opcionales — resuelve un problema real de configuración que de otra forma requeriría trabajo adicional.

Column + Line (Overlay) Charts es un tipo de visualización particularmente valioso para conversaciones de variance analysis (costo real como barra, tendencia de presupuesto como línea, en un solo gráfico) — vale la pena mencionarlo explícitamente en cualquier conversación donde el cliente pida "ver el real contra el plan en una sola vista".

## Documentos fuente

- Components Overview — `kb/02-product-docs/apptio-tbm-studio/en/components-overview.md`
- Slicer — `kb/02-product-docs/apptio-tbm-studio/en/components-slicer.md`
- Hierarchical Slicer — `kb/02-product-docs/apptio-tbm-studio/en/components-hierarchical-slicer.md`
- Column Picker — `kb/02-product-docs/apptio-tbm-studio/en/components-column-picker.md`
- Quick Pivot — `kb/02-product-docs/apptio-tbm-studio/en/components-quick-pivot.md`
- HTML — `kb/02-product-docs/apptio-tbm-studio/en/components-html.md`
- Group — `kb/02-product-docs/apptio-tbm-studio/en/components-group.md`
- Tabs — `kb/02-product-docs/apptio-tbm-studio/en/components-tabs.md`
- Tab Visibility Rules — `kb/02-product-docs/apptio-tbm-studio/en/tabs-tab-visibility-rules.md`
- Button Component — `kb/02-product-docs/apptio-tbm-studio/en/components-button-component.md`
- Visualizations Overview — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-overview.md`
- KPI — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-kpi.md`
- Table — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-table.md`
- Table Column Overflow Menu — `kb/02-product-docs/apptio-tbm-studio/en/table-column-overflow-menu.md`
- Renaming Columns in Table — `kb/02-product-docs/apptio-tbm-studio/en/table-renaming-columns-in.md`
- Hiding Intermediate Dimensions — `kb/02-product-docs/apptio-tbm-studio/en/table-hiding-intermediate-dimensions.md`
- Show Values — `kb/02-product-docs/apptio-tbm-studio/en/table-show-values.md`
- Tree View — `kb/02-product-docs/apptio-tbm-studio/en/table-tree-view.md`
- Export a Table to Excel — `kb/02-product-docs/apptio-tbm-studio/en/table-export-excel.md`
- Editable Table — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-editable-table.md`
- Bar Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-bar-charts.md`
- Column Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-column-charts.md`
- Line Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-line-charts.md`
- Pie Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-pie-charts.md`
- Column + Line (Overlay) Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-column-line-overlay-charts.md`
- Heatmaps — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-heatmaps.md`
- Bubble Charts — `kb/02-product-docs/apptio-tbm-studio/en/visualizations-bubble-charts.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
