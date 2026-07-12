---
tbm_concept: "Report Walkthrough - Infrastructure (recorrido guiado de habilitación por reportes de infraestructura, más la Planning Integration Collection que conecta con Apptio Planning)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/computereportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/computesummary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/operational-summary_compute.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/spend-profile_compute.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/storage-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/storage-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/storage-lun-details.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/utilization-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/devicedetails.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/operational-summary_storage.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/spend-profile_storage.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/financialview_storage.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/datacenterreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/summary_datacenter.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/operational-summary_datacenter.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/financialview_datacenter.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/infracloudreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/summary_infracloud.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ittowersreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ittowerscomposition.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ittowersperformance.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ittowersplanning.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/it-towers-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/project-list.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/project-portfolio.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/project-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/projects-at-risk.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/projects-report-collecion.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-labor-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-asset-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-vendor-review.md
last_updated: "2026-07-05"
---
# Report Walkthrough — Infrastructure — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El mismo propósito de habilitación ya establecido en RW-01, aplicado a infraestructura y proyectos

Como en el Report Walkthrough Financial, esta categoría no introduce capacidades nuevas — es el recorrido guiado de habilitación de usuario final para los reportes ya documentados en Compute, Storage, Data Centers, Resource Towers y Projects. La única pieza genuinamente nueva es la **Planning Integration Collection**.

## Cómo lo resuelve Apptio Costing Standard

**Compute, Storage, Data Centers, Infra & Cloud y Resource Towers** — el walkthrough cubre los mismos reportes ya documentados en sus respectivos briefs (Compute Summary/Spend Profile/Operational Summary, Storage Summary/LUN Details/Utilization Summary/Device Details/Spend Profile/Financial View, Data Center Summary/Operational Summary/Financial View, IT Towers Composition/Performance/Planning/Review), con sus respectivas colecciones actuando como índices navegables — igual que en RW-01.

**Projects** — cubre Project List, Portfolio, Review y At Risk, ya documentados en el brief de Projects (Financial Use Cases), con su propia colección índice.

### La pieza nueva: Planning Integration Collection (ITP)

**ITP — Labor Review, Asset Review y Vendor Review** son tres reportes que **no aparecieron en ningún brief anterior de Costing Standard**, porque su propósito específico es comparar datos entre Costing Standard y Apptio Planning — el mismo puente de integración ya documentado extensamente desde el lado de Planning en el Capítulo 7.1 de esa base de conocimiento (Cost Transparency Integration / CTI, y su evolución hacia Automated Data Management).

**ITP Labor Review** compara actuals de labor (de Costing Standard, vía el módulo Workforce ya documentado) contra presupuesto y forecast de labor (de Planning) — permitiendo validar si el modelo de asignación de labor de Costing Standard y el modelo de presupuesto de Planning están razonablemente alineados.

**ITP Asset Review** hace el mismo ejercicio para activos fijos: actuals de depreciación de Costing Standard (módulo Fixed Assets) contra el presupuesto/forecast de depreciación de Asset Planning en Planning.

**ITP Vendor Review** compara actuals de gasto con proveedores (Costing Standard, módulo Vendor) contra presupuesto y forecast de contratos (Planning, módulo Contract Planning).

Este patrón — actuals de Costing Standard comparado contra budget/forecast de Planning, dominio por dominio (Labor, Asset, Vendor) — es exactamente la mecánica de integración ya descrita en el brief de "Integraciones con Apptio Costing Standard" de la base de conocimiento de Planning, ahora vista desde su lado de reporte de consumo en Costing Standard.

## Por qué importa en una conversación con el cliente

La Planning Integration Collection es el mejor punto de conexión narrativa entre las dos bases de conocimiento de este proyecto (Apptio Planning y Apptio Costing Standard): en una conversación con un cliente que tiene o está considerando ambos productos, estos tres reportes ITP son la evidencia concreta de que la integración no es solo una promesa técnica — hay reportes reales, out-of-the-box, diseñados específicamente para validar que el modelo de presupuesto (Planning) y el modelo de actuals (Costing Standard) están alineados.

Vale la pena usar estos tres reportes como ejemplo concreto cuando un cliente pregunta "¿cómo sabemos si nuestro presupuesto de Planning realmente refleja lo que Costing Standard está reportando como gasto real?" — la respuesta ya no es conceptual, es "aquí está el reporte que hace exactamente esa comparación, para Labor, Activos y Vendor".

Al igual que en RW-01, este contenido sirve principalmente para materiales de capacitación de usuario final post-implementación, más que para conversaciones de preventa de capacidad — con la excepción de la Planning Integration Collection, que sí tiene valor de conversación de venta cruzada entre ambos productos.

## Documentos fuente

*(Mismos reportes documentados en los briefs de Compute, Storage, Data Centers, Resource Towers y Projects — ver esos briefs para el detalle de propósito de cada uno. Fuente nueva no cubierta anteriormente:)*

- ITP – Labor Review — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-labor-review.md`
- ITP – Asset Review — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-asset-review.md`
- ITP – Vendor Review — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itp-vendor-review.md`
- Compute Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/computereportcollection.md`
- Storage Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/storage-report-collection.md`
- Data Center Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/datacenterreportcollection.md`
- Infra & Cloud Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/infracloudreportcollection.md`
- IT Towers Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ittowersreportcollection.md`
- Projects Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/projects-report-collecion.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos pendientes según lo acordado.*