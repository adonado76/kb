---
concept: "Report Walkthrough - Financial (recorrido guiado de habilitación a través de los reportes financieros ya documentados, para onboarding de usuarios finales)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/financialreview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/financialreviewcapex.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/financialanalysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/costpoolanalysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itfinancialsreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-analysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-cost.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-vendor-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-vendor-detail.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-vendor-insights.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-list.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-portfolio.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-spend-by-project.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendors-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-cost.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-po-burndown.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-spend-without-po.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-contract-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-contract-detail.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-contract-applications.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-contract-expiration-notification.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-contract-expiration-12-6.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-arcrrc-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/vi_content/report-arcrrcru-reconcile.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fixedassets.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fixedassetsreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/businessunitreview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/businessunitlist.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/businessunitportfolio.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/businessunitsreportcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/businessunitdetails.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/projectfinancialdetails.md
last_updated: "2026-07-05"
---
# Report Walkthrough — Financial — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Un propósito distinto al resto de esta base de conocimiento

Todas las categorías anteriores (Getting Started, Financial/Infrastructure/Solution/Other Use Cases, Technology Integrations, Configuration) documentan **capacidades**: qué problema resuelven, cómo se configuran, y por qué importan. **Report Walkthrough tiene un propósito distinto: es un recorrido guiado, reporte por reporte, pensado para entrenar a un usuario final en cómo leer e interactuar con un reporte específico** — qué filtros tiene, cómo interpretar cada visual, qué pregunta de negocio responde cada sección de la pantalla. Es contenido de habilitación (enablement), no de descubrimiento de capacidad.

## El concepto

Un reporte bien diseñado puede seguir siendo subutilizado si el usuario final no sabe cómo navegarlo: qué filtro aplicar primero, qué significa cada columna, cómo pasar de la vista resumen al detalle. Sin un recorrido de habilitación dedicado, la curva de adopción de cada reporte depende de que alguien (típicamente un consultor o power user) enseñe informalmente a cada nuevo usuario — un cuello de botella de escalabilidad para cualquier programa TBM que crece más allá de un puñado de usuarios iniciales.

## Cómo lo resuelve Apptio Costing Standard

**El Report Walkthrough Financial cubre exactamente los mismos reportes ya documentados en los briefs de IT Financials, Workforce, Vendor & Vendor Insights, Fixed Assets y Business Unit** — Financial Review, Financial Review CapEx, Financial Analysis, Cost Pool Analysis, Labor Review, Labor Analysis, Vendor Review, Vendor Portfolio, Vendor List, Vendor Spend by Project, los ocho reportes de Vendor Insights (Dashboard, Summary, PO Burndown, Spend without POs, Contract Summary/Detail/Applications/Expiration/Expiration Notification, ARC RRC Summary/Reconcile), Fixed Assets, y los cinco reportes de Business Unit. La diferencia no está en qué reporte se cubre, sino en **cómo se cubre**: cada entrada del walkthrough describe la interfaz específica del reporte — sus filtros disponibles, la disposición de sus visuales, y una guía paso a paso de cómo un usuario nuevo debería interactuar con él para llegar a una respuesta.

**Dos reportes adicionales no vistos en briefs anteriores, provenientes de una versión intermedia del producto (reports-v104):**
- **Business Unit Details** — un nivel de detalle adicional al ya documentado en Business Unit Review/Portfolio/List, probablemente cubriendo drill-down a nivel de línea individual de gasto por unidad de negocio.
- **Project Financial Details** — un nivel de detalle financiero de proyecto complementario a los reportes de Projects ya documentados (Project Review, Portfolio, List, at Risk), probablemente con desglose línea por línea del gasto de un proyecto específico.

**Las colecciones de reportes (Report Collection) actúan como índices organizativos**, agrupando los reportes individuales de cada dominio (IT Financials Report Collection, Labor Report Collection, Vendors Report Collection, Fixed Assets Report Collection, Business Units Report Collection) — el equivalente de una tabla de contenido navegable dentro de la interfaz del producto.

## Por qué importa en una conversación con el cliente

Este contenido es más valioso para el equipo de **adopción y capacitación de usuarios finales** después de una implementación que para una conversación de preventa — vale la pena diferenciarlo explícitamente: mientras los briefs de FU-01 a FU-07 responden "¿debería mi organización activar este módulo?", el Report Walkthrough responde "ya activamos este módulo, ¿cómo le enseño a doscientos usuarios finales a usarlo bien?".

Es un recurso natural para construir materiales de capacitación o guías rápidas de usuario (quick reference guides) durante la fase de adopción de un proyecto de implementación — se puede reutilizar como base de un programa de habilitación sin tener que redactar esa documentación desde cero.

Los dos reportes adicionales (Business Unit Details, Project Financial Details) valen la pena confirmarlos contra la versión de producto real del cliente, dado que provienen de una versión intermedia (v104) — puede que no estén disponibles o hayan cambiado de nombre en la versión actual que el cliente tiene desplegada.

## Documentos fuente

*(Mismos reportes documentados en los briefs de IT Financials, Workforce, Vendor & Vendor Insights, Fixed Assets y Business Unit — ver esos briefs para el detalle de propósito de cada uno. Fuentes adicionales no cubiertas anteriormente:)*

- Business Unit Details (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/businessunitdetails.md`
- Project Financial Details (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/projectfinancialdetails.md`
- IT Financials Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itfinancialsreportcollection.md`
- Labor Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-report-collection.md`
- Vendors Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendors-report-collection.md`
- Fixed Assets Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fixedassetsreportcollection.md`
- Business Units Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/businessunitsreportcollection.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos pendientes según lo acordado.*