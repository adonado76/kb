---
tbm_concept: "Report NX Walkthrough (recorrido guiado de habilitación en la interfaz New Report Studio, espejo de RW-01/02/03 pero en la experiencia nueva)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fin-rev-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/fin-rev-capex-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/itf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor_analysis_nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/labor-cto-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/wf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-cto-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-list-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/vendor-review-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/pc-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mf-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-nx-analysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-nx-consumption-review.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-tco-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-usage-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/mainframe-applications-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/app-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-app-cto.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-appiaa.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-applist.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-appnnr.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/nx-apprev.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/service-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/service-review-nx-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/services-listnx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitco-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-platform-mapping-nx.md
last_updated: "2026-07-05"
---
# Report NX Walkthrough — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de calidad de datos

Durante la validación de esta categoría se detectaron **3 archivos fuente cuyo campo `title` en el front-matter no se extrajo correctamente** (aparece como `"***"` en lugar de un título legible). Esto no afecta el contenido del cuerpo de esos documentos, pero sí significa que, en algún punto de la reconstrucción final de este brief hacia el documento consolidado, esos 3 títulos específicos deben confirmarse manualmente contra el archivo fuente original antes de publicarse — no los adiviné para evitar introducir un título incorrecto.

## El mismo propósito de habilitación que RW-01/02/03, ahora en la interfaz New Report Studio

El brief de Getting Started (GS-01) ya estableció que Costing Standard opera actualmente bajo dos experiencias de reporting coexistentes: el **TBM Report Studio clásico** y el **New Report Studio** (desde v12.11.21, con inscripción a preview público requerida en v12.11.19). Report NX Walkthrough es, en esencia, el mismo ejercicio de habilitación de usuario final ya visto en Report Walkthrough (RW-01/02/03), pero específicamente para la nueva interfaz — cubriendo las versiones "NX" de reportes que, en varios casos, ya aparecieron mencionadas de pasada en los briefs de módulo individuales (IT Financials NX, Workforce NX, Vendor NX, Public Cloud NX, Mainframe NX, Applications NX, Services NX, AI TCO NX).

## Cómo lo resuelve Apptio Costing Standard

**Ocho dominios cubiertos, en la misma estructura de walkthrough que sus contrapartes clásicas:**

**Financials NX** — Financial Analysis, Financial Review y Financial Review CapEx en la interfaz nueva, mismos propósitos ya documentados en IT Financials (FU-01).

**Workforce NX** — Labor Review, Labor Analysis y **Labor Cost Take-Out** (esta última confirmando, en el walkthrough dedicado, la mecánica de optimización de tarifa por rol/ubicación/proveedor ya documentada en detalle en el brief de Workforce).

**Vendors NX** — Vendor Review, Vendor List y **Vendor Cost Take-Out**, el equivalente de vendor a la misma mecánica.

**Public Cloud NX** — un solo reporte consolidado, alineado con la naturaleza más ligera de Public Cloud for IT Finance ya documentada en FU-05 y en RW-03.

**Mainframes NX** — el conjunto más extenso de esta categoría, con cinco reportes: Mainframe Applications, Analysis, TCO, Usage y **Consumption Review** — reflejando la riqueza analítica ya vista en el brief de Mainframe (FU/IU-04), con la fórmula de weighting MSU+zIIP y el benchmarking de industria como su contenido más distintivo.

**Applications NX** — el conjunto más granular de reportes individuales: **Application Cost Take-Out** (tercera variante de esta mecánica, confirmando lo ya inferido en RW-03), Infrastructure Analysis by Application, Applications List, New & Retired Apps, y Application Review.

**Services NX** — Services Review y Service List.

**AI TCO NX** — AI TCO and Usage y AI Platform Mapping, ya documentados en detalle en el brief de AI TCO (OU-02).

## Por qué importa en una conversación con el cliente

Este walkthrough es la referencia correcta para cualquier cliente que ya haya migrado (o esté evaluando migrar) a la interfaz New Report Studio — permite confirmar, dominio por dominio, qué reportes ya tienen su versión NX disponible y cuáles todavía dependen de la experiencia clásica, información de planeación de adopción concreta para cualquier proyecto de upgrade de interfaz.

La triple confirmación de Cost Take-Out (Labor, Vendor, y ahora Application) como mecánica consistente a través de tres dominios distintos refuerza el argumento ya hecho en RW-03: vale la pena presentar la optimización de tarifa/costo como una capacidad transversal y repetible del producto, no como una característica aislada de un solo módulo — es, en efecto, el mismo patrón analítico (tarifa promedio vs. tarifa más baja disponible) aplicado sistemáticamente donde tiene sentido de negocio.

## Documentos fuente

*(Mismos reportes documentados en los briefs de IT Financials, Workforce, Vendor, Public Cloud, Mainframe, Applications, Services y AI TCO — ver esos briefs para el detalle de propósito de cada uno.)*

- Financials NX: Financial Analysis, Financial Review, Financial Review CapEx
- Workforce NX: Labor Review, Labor Analysis, Labor Cost Take-Out
- Vendors NX: Vendor Review, Vendor List, Vendor Cost Take-Out
- Public Cloud NX: Public Cloud
- Mainframes NX: Mainframe Applications, Analysis, TCO, Usage, Consumption Review
- Applications NX: Application Cost Take-Out, Infrastructure Analysis by Application, Applications List, New & Retired Apps, Application Review
- Services NX: Services Review, Service List
- AI TCO NX: AI TCO and Usage, AI Platform Mapping

*Nota: 3 títulos de esta categoría no se pudieron extraer limpiamente del front-matter fuente (aparecen como "***") y requieren confirmación manual antes de publicación final — ver nota de calidad de datos al inicio de este brief.*

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos pendientes según lo acordado.*