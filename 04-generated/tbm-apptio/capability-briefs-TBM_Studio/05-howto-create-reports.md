---
concept: "How-To: Create Reports (fundamentos de reporte, personalización, y reporting avanzado en Report Studio clásico)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/reports-report-basics.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-create-basic-report.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-add-tables-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-add-charts-visualizations.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-use-slicers-interactive-filtering.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-monitor-engagement-apptio-usage-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-putting-it-all-together-your-first-report.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-report-customization.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-create-custom-perspectives.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-build-report-collections.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-design-master-reports-templates.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-configure-report-permissions.md
  - kb/02-product-docs/apptio-tbm-studio/en/customization-summary.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-advanced-reporting.md
  - kb/02-product-docs/apptio-tbm-studio/en/reporting-create-drill-through-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/reporting-add-editable-components-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/reporting-configure-dynamic-sizing-positioning.md
  - kb/02-product-docs/apptio-tbm-studio/en/reporting-export-print-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/reporting-email-subscription.md
last_updated: "2026-07-07"
---
# How-To: Create Reports — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

La capa de consumo del producto: el manual operativo completo del Report Studio clásico (distinto del "New Report Studio", cubierto en categorías separadas de este proyecto), en tres bloques de profundidad creciente.

## Cómo lo resuelve Apptio TBM Studio

### Report Basics — de reporte vacío a primer entregable

**Create a Basic Report** — crear el contenedor: nombre (máximo 31 caracteres si se planea exportar a Excel, para evitar truncamiento) y descripción, que aparece en el buscador de reportes (Report Finder).

**Add Tables to Reports** — el Component Configuration Panel tiene cuatro áreas de arrastrar-y-soltar para construir una tabla estructurada de filas y columnas.

**Add Charts and Visualizations** — seleccionar un objeto del modelo, arrastrar una dimensión al área de Leyenda (ej. "Data Center" genera una barra por centro de datos).

**Use Slicers for Interactive Filtering** — controles de filtro interactivo: cuando un usuario selecciona un valor, todas las tablas y gráficos vinculados se actualizan instantáneamente. Buenos candidatos documentados explícitamente: Business Unit, Data Center, Expense Type, Cost Pool, Vendor — convierte un reporte estático en una herramienta exploratoria.

**Monitor engagement with Apptio Usage reports** — analítica de adopción: quién está usando qué reportes, con qué frecuencia — relevante para justificar inversión de capacitación o identificar reportes huérfanos.

### Report Customization — de reporte individual a plataforma de reporte gobernada

**Create Custom Perspectives** — resuelve la sobrecarga cognitiva del Project Explorer estándar (Tables, Metrics, Time): una "lista de favoritos" curada con campos de múltiples tablas, cada uno bloqueado a su tabla fuente — permite construir reportes con datos de varios niveles del modelo sin exponer toda la superficie de datos disponible.

**Build Report Collections** — agrupar reportes relacionados con un navegador de colección (barra horizontal con acceso de un clic entre reportes del mismo tema) que aparece automáticamente en la parte superior.

**Design Master Reports (Templates)** — funcionan como "diapositivas maestras" de PowerPoint: una capa de plantilla que aparece como "papel tapiz" de fondo, garantizando encabezados, pies de página, navegación y marca consistentes a través de múltiples reportes.

**Configure Report Permissions** — modelo de control de acceso en capas: permisos a nivel de reporte, a nivel de colección, y (para el rol Power User) visibilidad a nivel de componente individual dentro de un mismo reporte.

### Advanced Reporting — interactividad y distribución

**Create Drill-Through Reports** — navegación progresiva de resumen a detalle: valores vinculados aparecen en texto azul en tablas; gráficos también soportan drill-through al hacer clic en una porción de pastel o segmento de barra.

**Add Editable Components to Reports** — la contraparte de reporte de las Editable Tables ya vistas en Data Studio: una capa de captura de datos embebida directamente en el reporte (mapeos de labor, atributos de centro de costo, entradas de presupuesto, explicaciones de varianza) que alimenta las transform tables sin requerir que el usuario tenga acceso a TBM Studio.

**Configure Dynamic Sizing and Positioning** — layouts responsivos que se adaptan a distintos tamaños de pantalla y a visibilidad condicional de componentes por rol, sin dejar espacios vacíos.

**Export and Print Reports / Email Subscription** — los mecanismos de distribución final: exportación/impresión bajo demanda, y suscripción por correo para distribución programada recurrente.

## Por qué importa en una conversación con el cliente

Custom Perspectives es la respuesta directa a la queja más común de analistas de negocio frente a herramientas de modelado complejas ("hay demasiados campos, no sé cuáles usar") — vale la pena posicionarlo proactivamente en cualquier conversación de adopción de usuario final, ya que reduce fricción sin sacrificar la riqueza del modelo subyacente para power users.

Editable Components conecta directamente con las Editable Tables de Data Studio — juntas forman el mecanismo completo de captura de datos de negocio (mapeos de labor, atributos, explicaciones de varianza) sin requerir licencia de TBM Studio para el usuario que solo necesita anotar datos — un argumento de costo de licenciamiento relevante en conversaciones de escala de adopción.

Report Permissions con tres capas (reporte/colección/componente) da la granularidad necesaria para conversaciones de gobernanza de datos sensibles en banca y seguros — vale la pena mostrar explícitamente que el control de acceso no es binario (todo o nada) sino ajustable por capa.

## Documentos fuente

- Report Basics (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reports-report-basics.md`
- Create a Basic Report — `kb/02-product-docs/apptio-tbm-studio/en/basics-create-basic-report.md`
- Add Tables to Reports — `kb/02-product-docs/apptio-tbm-studio/en/basics-add-tables-reports.md`
- Add Charts and Visualizations — `kb/02-product-docs/apptio-tbm-studio/en/basics-add-charts-visualizations.md`
- Use Slicers for Interactive Filtering — `kb/02-product-docs/apptio-tbm-studio/en/basics-use-slicers-interactive-filtering.md`
- Monitor engagement with Apptio Usage reports — `kb/02-product-docs/apptio-tbm-studio/en/basics-monitor-engagement-apptio-usage-reports.md`
- Putting It All Together: Your First Report — `kb/02-product-docs/apptio-tbm-studio/en/basics-putting-it-all-together-your-first-report.md`
- Report Customization (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reports-report-customization.md`
- Create Custom Perspectives — `kb/02-product-docs/apptio-tbm-studio/en/customization-create-custom-perspectives.md`
- Build Report Collections — `kb/02-product-docs/apptio-tbm-studio/en/customization-build-report-collections.md`
- Design Master Reports (Templates) — `kb/02-product-docs/apptio-tbm-studio/en/customization-design-master-reports-templates.md`
- Configure Report Permissions — `kb/02-product-docs/apptio-tbm-studio/en/customization-configure-report-permissions.md`
- Summary — `kb/02-product-docs/apptio-tbm-studio/en/customization-summary.md`
- Advanced Reporting (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reports-advanced-reporting.md`
- Create Drill-Through Reports — `kb/02-product-docs/apptio-tbm-studio/en/reporting-create-drill-through-reports.md`
- Add Editable Components to Reports — `kb/02-product-docs/apptio-tbm-studio/en/reporting-add-editable-components-reports.md`
- Configure Dynamic Sizing and Positioning — `kb/02-product-docs/apptio-tbm-studio/en/reporting-configure-dynamic-sizing-positioning.md`
- Export and Print Reports — `kb/02-product-docs/apptio-tbm-studio/en/reporting-export-print-reports.md`
- Email Subscription — `kb/02-product-docs/apptio-tbm-studio/en/reporting-email-subscription.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
