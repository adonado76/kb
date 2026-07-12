---
tbm_concept: "IT Financials (visibilidad consolidada de gasto OpEx/CapEx, análisis de variación presupuestal, cost pools)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-getting-started.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-summary.md
last_updated: "2026-07-05"
---
# IT Financials — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de alcance

El documento `itf-summary.md` no es específico de IT Financials — es el resumen de **toda la sección Financial Use Cases** (IT Financials, Vendors, Labor & Time Tracking, Fixed Assets, Public Cloud, Projects, Resource Towers). Lo incluimos aquí porque es donde vive dentro de la estructura de carpetas, pero su contenido es más útil como introducción general al capítulo "Financial Use Cases" que como parte exclusiva de este brief — lo retomamos como tal al ensamblar el documento consolidado.

## El concepto

Antes de poder analizar labor, vendors, activos o nube pública por separado, una organización necesita una vista consolidada de su gasto tecnológico total: cuánto se gastó, contra qué presupuesto, y qué está causando las desviaciones. Sin esta capa base, cualquier análisis de un módulo específico queda descontextualizado — un pico de gasto en un centro de costo no dice nada si no se puede comparar contra el presupuesto general y contra cost pools estándar de la industria.

## Cómo lo resuelve Apptio Costing Standard

**Consolidación de OpEx y CapEx por centro de costo y grupo de cuenta.** IT Financials reúne datos financieros de centros de costo y grupos de cuenta para dar visibilidad consolidada al gasto operativo y de capital, estandarizando cómo se revisan los actuals, el presupuesto y el forecast a través de todos los dominios tecnológicos.

**Casos de uso estándar, listos para usar:**
- **Spend Visibility** — consolidar y revisar OpEx/CapEx por centro de costo y grupo de cuenta para identificar los principales drivers de costo y entender variaciones presupuestales.
- **Budget Variance Analysis** — comparar gasto real contra presupuesto y forecast para identificar desviaciones y tendencias mes a mes.
- **Transaction-Level Insights** — profundizar hasta las transacciones del libro mayor para validar la clasificación del gasto y fortalecer los controles de costo.
- **Spend Reduction Analysis** — identificar gasto fijo vs. variable para descubrir oportunidades de reducir el costo de corrida (run-rate).
- **Cost Pool Analysis** — analizar la distribución de OpEx por Cost Pools (categorías estándar TBM/ATUM) y comparar el gasto de TI contra ingresos y métricas por usuario.

**Un caso de uso adicional documentado como personalizado**: la gestión de acumulaciones (accruals) antes del cierre de mes, para reducir imprecisiones y evitar variaciones presupuestales inesperadas — vale la pena saber que esto no viene out-of-the-box, sino que requiere configuración a medida.

**Cuatro reportes centrales, en dos versiones (Classic y NX).** La colección de reportes de IT Financials incluye:
- **Financial Review** — vista ejecutiva de la variación presupuestal y el gasto OpEx total, desglosado por cost pool y dueño de TI, con gráficos que ayudan a distinguir variaciones reales de errores de categorización. Dirigido a CIO-1 (Oficina TBM), dueños de centro de costo y analistas financieros de TI.
- **Financial Review – CapEx** — la misma vista ejecutiva, pero para gasto de capital.
- **Financial Analysis** — vista detallada mes a mes de variación OpEx/CapEx, variación presupuestal año-a-la-fecha y variación de forecast año-a-la-fecha, a nivel de grupo de cuenta, subgrupo, cuenta y centro de costo.
- **Cost Pool Analysis** — agrega el gasto financiero en las categorías estándar (cost pools) definidas por el TBM Council, desglosando por OpEx/CapEx y por costo fijo/variable.

La versión **NX** de estos reportes (excepto Cost Pool Analysis, que no tiene variante NX documentada aquí) replica el mismo contenido y propósito sobre la interfaz del New Report Studio.

**Dos componentes que se instalan según necesidad.** El componente **CTF-Cost Source** se instala automáticamente al crear el proyecto y provee la estructura de datos maestros para todo el reporting de OpEx. El componente **CTF-CapEx** es opcional y separa el reporting de CapEx del de OpEx — solo necesario si la organización carga datos de capital o requiere reportes específicos de CapEx. Un tercer componente, **CTF-Cost Source NX Reports**, habilita los reportes predefinidos en la interfaz nueva.

**Fuentes de datos típicas.** El gasto y presupuesto normalmente provienen del libro mayor y el catálogo de cuentas, cargados desde sistemas como Oracle, SAP, Lawson, Netsuite o Cognos. Las tablas clave a mapear son: General Ledger, Chart of Accounts, Organizational Hierarchy y Budget.

## Por qué importa en una conversación con el cliente

IT Financials suele ser el primer módulo que un cliente activa, porque es la base sobre la cual se construyen todos los demás análisis (Vendor, Labor, Activos, Nube). Vale la pena posicionar esta capacidad como el "cimiento financiero" antes de prometer análisis más específicos — sin datos de Cost Source cargados y mapeados correctamente, ningún otro módulo puede generar reportes confiables.

La distinción entre reportes **Classic** y **NX** es un buen punto de discovery técnico: preguntar en qué versión de Report Studio está el cliente ayuda a calibrar qué documentación y qué capacitación necesitan.

El caso de uso "Accruals Management" (marcado explícitamente como personalizado, no estándar) es un buen ejemplo para conversaciones de alcance de proyecto: ayuda a diferenciar lo que viene listo para usar de lo que requiere trabajo de configuración adicional — una distinción que suele aparecer en cualquier propuesta de implementación.

## Documentos fuente

- IT Financials Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-overview.md`
- IT Financial Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-reports.md`
  - Financial Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-financial-review
  - Financial Review – CapEx: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-financial-review-capex
  - Financial Analysis: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-financial-analysis
  - Cost Pool Analysis: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-cost-pool-analysis
- IT Financial NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-reports-nx.md`
- IT Financials Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-getting-started.md`
- Summary (Financial Use Cases, sección completa) — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/itf-summary.md`

*Nota: las URLs bajo "IT Financial Reports" son links reales embebidos en el contenido fuente original de IBM (no inferidos), verificados por venir directamente del documento. El resto de fuentes queda pendiente de hipervínculo según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*