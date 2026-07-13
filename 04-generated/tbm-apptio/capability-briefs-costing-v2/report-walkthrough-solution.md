---
concept: "Report Walkthrough - Solution (recorrido guiado de habilitación por reportes de Applications/Services, más Cost Take-Out y Public Cloud for IT Finance)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/application-list.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/application-portfolio.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/application-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/applications-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/new-retired-apps.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/impactofretiringapplications.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/infrastructureanalysisby.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/byapplications.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/application-cost.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-portfolio.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/service-list.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/cost-takeout-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pub-cloud-tco-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/public-cloud-config.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pub-cloud-model-views-cs.md
last_updated: "2026-07-05"
---
# Report Walkthrough — Solution — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El mismo propósito de habilitación, con dos piezas que sí aportan contenido nuevo

Como en RW-01 y RW-02, la mayoría de este walkthrough cubre reportes ya documentados en Applications y Services. Dos secciones sí aportan contenido genuinamente nuevo: **Cost Take-Out** como colección consolidada, y el **walkthrough completo de Public Cloud for IT Finance**.

## Cómo lo resuelve Apptio Costing Standard

**Applications** — el walkthrough cubre Application List, Portfolio, Review, New & Retired Apps, Impact of Retiring Applications (¿), Infrastructure Analysis by Application y By Applications, todos ya documentados en el brief de Applications, más un reporte **Application Cost** no visto explícitamente en ese brief anterior — probablemente una vista de costo consolidado por aplicación individual, complementaria a las ya documentadas.

**Services** — cubre Services Portfolio, Review y Service List, ya documentados en el brief de Services.

### Cost Take-Out: la colección consolidada de una capacidad que ya vimos aparecer dos veces

Los briefs de Workforce (Labor Cost Take-Out) y Vendor (Vendor Cost Take-Out) ya documentaron esta mecánica de optimización — comparar tarifas por rol/ubicación/proveedor para identificar ahorro potencial. **Cost Take-Out Reports** es la colección que consolida esa capacidad como su propia categoría de reporting, confirmando que no es un añadido aislado de Labor o Vendor, sino un patrón de análisis transversal del producto — el menú original de IBM referenciaba explícitamente esta colección con **Application Cost Take-Out** como tercera variante (además de Vendor y Labor), sugiriendo que la misma lógica de comparación de costo/tarifa se extiende también al dominio de aplicaciones. También aparecen referenciados aquí el **Costing Standard Workbench** y **Labor Mapping** — herramientas de soporte para mantener los datos de mapeo que alimentan estos análisis de cost take-out.

### Public Cloud for IT Finance: el walkthrough completo de la solución ligera ya introducida en Public Cloud

El brief de Public Cloud (FU-05) ya estableció la distinción entre Public Cloud Integrated y Public Cloud for IT Finance. Aquí encontramos el walkthrough detallado de esta última: **Public Cloud TCO Overview** explica el propósito y alcance de la solución ligera, **Public Cloud Configuration** documenta sus pasos de habilitación específicos (distintos de los de Public Cloud Integrated ya vistos en FU-05), y **Public Cloud Model Views (Costing Standard)** es el reporte de trazabilidad — el mismo patrón de "reporte Model View" ya visto en Applications, Services, Business Units y AI TCO — aplicado específicamente a validar cómo fluye el costo dentro del modelo de Public Cloud for IT Finance.

## Por qué importa en una conversación con el cliente

La existencia de una colección Cost Take-Out consolidada (no solo casos aislados en Labor y Vendor) es un argumento de venta importante para posicionar la optimización de costo como una **capacidad transversal del producto**, no una característica aislada de un solo módulo — vale la pena mencionar explícitamente en conversaciones de ahorro/optimización que este patrón de análisis (tarifa promedio vs. tarifa más baja disponible) se aplica consistentemente a Labor, Vendor, y potencialmente Applications.

El walkthrough completo de Public Cloud for IT Finance, con su propia guía de configuración separada de Public Cloud Integrated, refuerza el argumento ya hecho en el brief de Public Cloud: son dos productos con procesos de habilitación genuinamente distintos, y vale la pena que el cliente entienda cuál está configurando antes de empezar el trabajo técnico.

## Documentos fuente

*(Mismos reportes documentados en los briefs de Applications, Services y Public Cloud — ver esos briefs para el detalle de propósito de cada uno. Fuentes nuevas no cubiertas anteriormente:)*

- Application Cost — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/application-cost.md`
- Cost Take-Out Reports (colección: Vendor, Application, Labor) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/cost-takeout-reports.md`
- Public Cloud TCO Overview (IT Finance) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pub-cloud-tco-overview.md`
- Public Cloud Configuration (IT Finance) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/public-cloud-config.md`
- Public Cloud Model Views (Costing Standard) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pub-cloud-model-views-cs.md`
- Applications Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/applications-report-collection.md`
- Services Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-report-collection.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos pendientes según lo acordado.*