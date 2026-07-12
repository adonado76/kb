---
tbm_concept: "Working with Dashboards and Reports (dashboards personalizables con 7 tipos de widget, reportes con más de 70 plantillas preconfiguradas, el pipeline de datos de costo, y reconciliación de facturas)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-cloudability-dashboards.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboards-list.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboards-view-configure.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboards-create-edit-widget-in-dashboard.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-chart-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-estimate-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-rightsizing-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-pie-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-number-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-table-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboard-text-widget.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboards-share-dashboard.md
  - kb/02-product-docs/apptio-cloudability-standard/en/dashboards-annotate-in.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-list.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-create-edit-report.md
  - kb/02-product-docs/apptio-cloudability-standard/en/report-subscribe.md
  - kb/02-product-docs/apptio-cloudability-standard/en/report-share.md
  - kb/02-product-docs/apptio-cloudability-standard/en/report-export.md
  - kb/02-product-docs/apptio-cloudability-standard/en/report-copy-dashboard.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-cost-usage-data-availability-in-reporting.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reports-invoice-reconciliation-in-cloudability.md
last_updated: "2026-07-09"
---
# Working with Dashboards and Reports — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

La capa de consumo diario de Cloudability: dashboards visuales personalizables para monitoreo continuo, y reportes ad hoc/programados para análisis profundo — sobre un pipeline de datos de costo con etapas de procesamiento bien definidas, y un procedimiento formal para cuando el número reportado no coincide con la factura real del proveedor.

## Cómo lo resuelve IBM Cloudability Standard

**Dashboards — siete tipos de widget, cada uno para un propósito distinto de visualización.** Chart (tendencias en el tiempo), Estimate (proyecciones), Rightsizing (recomendaciones de dimensionamiento embebidas directamente en el dashboard), Pie (composición proporcional), Number (KPI de valor único), Table (detalle tabular), y Text (contexto narrativo o instrucciones). Los dashboards se pueden **compartir** con colegas, y soportan **anotaciones** — marcar eventos o contexto directamente sobre la visualización (ej. señalar cuándo ocurrió un cambio de arquitectura que explica un salto de costo).

**Reports — más de 70 plantillas preconfiguradas, organizadas por proveedor y servicio específico.** El catálogo documentado cubre reportes granulares por servicio para los cuatro proveedores principales: AWS (EC2, RDS, S3, Lambda, Redshift, DynamoDB, ElastiCache, EMR, Kinesis, Elasticsearch, CloudFront, Fargate, EBS, y reportes específicos de factura como "RI Purchases Last Month"), Azure (Compute, Database, Networking, Storage, Web), GCP (Compute Engine, Kubernetes Engine, Cloud SQL, Bigtable, Dataflow, Pub/Sub, Cloud Storage), y OCI (Compute, Database, Block/Object Storage) — más reportes transversales de optimización ya orientados a acción concreta: **"Highly Underutilized Instances"**, **"Oldest Instances (Over a Month)"**, **"Unassociated ElasticIP Addresses"**, y **"Underutilized [Compute/General Purpose/Storage] Optimized Instances"**. También cubre plataformas de datos ya conectadas en el Capítulo 3 (Databricks, Datadog, MongoDB, Snowflake) con reportes de costo dedicados.

**Report lifecycle**: crear/editar desde cero o desde plantilla, **suscribirse** (entrega programada recurrente), **compartir**, **exportar**, y **copiar un reporte hacia un dashboard** — cerrando el ciclo entre exploración ad hoc y monitoreo visual persistente.

**El pipeline de datos de costo, documentado en sus etapas exactas**: ingesta de datos crudos de costo y uso → normalización → transformación → agregación → decoración, antes de estar disponible para reporte — el mismo tipo de trazabilidad de linaje de datos ya visto conceptualmente en TBM Studio, aquí aplicado específicamente al flujo de facturación de nube.

**Invoice Reconciliation — un procedimiento formal para cuando el número de Cloudability no coincide con la factura real, con matices específicos por proveedor documentados con precisión.** Principio base: los archivos de facturación crudos (CUR de AWS, Cost Export, Cloud Billing Table) son la fuente autoritativa de Cloudability — las facturas pueden incluir cargos o créditos que no aparecen en los datos crudos. Advertencia específica: **los datos de Azure Cost Management excluyen impuestos y ajustes/créditos de facturación** por diseño — no hay que esperar verlos en Cloudability. Procedimiento de reconciliación: filtrar por Invoice Date (primer día del mes) y Payer Account ID, usar un rango de fechas amplio (desde el mes anterior hasta la fecha actual, dado que el Date Picker de Cloudability consulta por **fecha de uso**, no fecha de factura — cargos "fuera de ciclo" muy posteriores al mes de factura pueden quedar fuera de la ventana consultable), y usar la métrica **Cost (Total)**, no amortizado, dado que las facturas reflejan el costo real desembolsado, no el amortizado.

## Por qué importa en una conversación con el cliente

El catálogo de 70+ reportes preconfigurados es un argumento de tiempo-a-valor concreto — un cliente nuevo no necesita construir reportes desde cero para preguntas comunes (instancias subutilizadas, direcciones IP elásticas sin asociar, instancias más antiguas) — esos análisis ya vienen listos.

El procedimiento de reconciliación de facturas es el recurso correcto para cualquier conversación donde el cliente cuestione la exactitud de los números de Cloudability — tener las advertencias específicas por proveedor (especialmente la exclusión de impuestos en Azure) listas de antemano evita que una discrepancia esperada se perciba como un error del producto.

La ventana de tiempo amplia recomendada para reconciliación (por el comportamiento de fecha de uso vs. fecha de factura) es un detalle técnico que vale la pena explicar proactivamente — un cliente que reconcilia con una ventana de fecha estrecha puede concluir erróneamente que faltan cargos, cuando en realidad están fuera del rango de fecha de uso consultado.

## Documentos fuente

- Cloudability Dashboards (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/reports-cloudability-dashboards.md`
- Dashboards List — `kb/02-product-docs/apptio-cloudability-standard/en/dashboards-list.md`
- View/Configure Dashboards — `kb/02-product-docs/apptio-cloudability-standard/en/dashboards-view-configure.md`
- Create/Edit a Widget in a Dashboard — `kb/02-product-docs/apptio-cloudability-standard/en/dashboards-create-edit-widget-in-dashboard.md`
- Chart Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-chart-widget.md`
- Estimate Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-estimate-widget.md`
- Rightsizing Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-rightsizing-widget.md`
- Pie Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-pie-widget.md`
- Number Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-number-widget.md`
- Table Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-table-widget.md`
- Text Widget — `kb/02-product-docs/apptio-cloudability-standard/en/dashboard-text-widget.md`
- Share a Dashboard — `kb/02-product-docs/apptio-cloudability-standard/en/dashboards-share-dashboard.md`
- Annotate in Dashboards — `kb/02-product-docs/apptio-cloudability-standard/en/dashboards-annotate-in.md`
- Cloudability Reports (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/reports-cloudability.md`
- Reports List — `kb/02-product-docs/apptio-cloudability-standard/en/reports-list.md`
- Create/Edit a Report — `kb/02-product-docs/apptio-cloudability-standard/en/reports-create-edit-report.md`
- Subscribe to a Report — `kb/02-product-docs/apptio-cloudability-standard/en/report-subscribe.md`
- Share a Report — `kb/02-product-docs/apptio-cloudability-standard/en/report-share.md`
- Export a Report — `kb/02-product-docs/apptio-cloudability-standard/en/report-export.md`
- Copy a Report to a Dashboard — `kb/02-product-docs/apptio-cloudability-standard/en/report-copy-dashboard.md`
- Cost & Usage Data Availability in Reporting — `kb/02-product-docs/apptio-cloudability-standard/en/reports-cost-usage-data-availability-in-reporting.md`
- Invoice Reconciliation in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/reports-invoice-reconciliation-in-cloudability.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
