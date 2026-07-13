---
concept: "Vendor & Vendor Insights (visibilidad de gasto con proveedores, y ciclo completo de contratos/PO/facturas/ARC-RRC)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-over.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-getstar.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctfvendors.md
last_updated: "2026-07-05"
---
# Vendor & Vendor Insights — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Una distinción de alcance que el propio producto documenta explícitamente

Los documentos fuente son inusualmente claros en una distinción que vale la pena preservar: **Vendor** se limita a "análisis de gasto con proveedores" (spend analysis únicamente), mientras **Vendor Insights** extiende ese análisis "más allá de la visibilidad fundacional de gasto hacia facturas, órdenes de compra, contratos y compromisos de servicio". Es decir, no son dos nombres para lo mismo — son dos niveles de profundidad progresivos, y el propio Vendor Overview redirige explícitamente a Vendor Insights para quien necesite contratos, PO o cuentas por pagar.

## El concepto

El gasto con proveedores suele ser, después de labor, el segundo componente más grande del presupuesto de TI — pero también el más fragmentado: docenas o cientos de proveedores, cada uno con su propio contrato, sus propias condiciones, y su propio patrón de facturación. Sin una capa de análisis dedicada, es casi imposible responder preguntas básicas de gobernanza: ¿cuáles son nuestros proveedores más grandes?, ¿hay redundancia entre ellos?, ¿qué contratos vencen pronto?, ¿estamos pagando facturas sin una orden de compra asociada?

## Cómo lo resuelve Apptio Costing Standard

### Vendor (nivel fundacional)

**Siete casos de uso estándar**, todos orientados a visibilidad y racionalización: Top Vendor Spend Analysis (identificar los proveedores de mayor gasto), Track & Eliminate Vendors with the Least Spend (reducir fragmentación consolidando proveedores de bajo gasto), Strategic Vendor Classification (clasificar por importancia estratégica — estratégico, preferido, transaccional), Vendor Spend Visibility, Vendor Consolidation & Rationalization, Vendor Cost Allocation (a centros de costo, proyectos y ofertas de solución), y Vendor Cost Analysis & Benchmarking. Dos casos adicionales — Vendor Budget & Forecasting y Vendor Portfolio Optimization — requieren personalización.

**Cuatro reportes estándar** (con equivalente NX para Vendor Review y Vendor List): **Vendor Review** (distribución y concentración de gasto, detección de redundancia), **Vendor Portfolio** (vista consolidada por torre de recursos TI y cost pool, con split OpEx/CapEx), **Vendor List** (vista tabular detallada por función, ubicación y servicio), y **Vendor Spend by Project** (gasto de proveedor a nivel de proyecto, con rollup por dueño y centro de costo).

**Vendor Cost Take-Out (solo NX)** aplica la misma lógica de optimización vista en Labor Cost Take-Out, pero a nivel de proveedor: tablas de "Vendor by Function", "Vendors by Resource Tower", "Vendors by Pool" y "Vendors by Type" que permiten decidir si consolidar, renegociar o no renovar contratos con proveedores específicos — dirigido explícitamente a Business Unit Leaders, Vendor Managers y Procurement Managers.

**Un solo componente de instalación**: CTF-Vendors, que no se instala automáticamente y requiere cargar el archivo maestro de proveedores (típicamente desde Oracle Financials o SAP ERP Financials) a la tabla Vendor Master Data. Las claves de esa tabla (Cost Source_Vendor Key, Vendor_ITRT Key, Vendor_CSP Key) están predefinidas y **no deben alterarse**.

### Vendor Insights (nivel extendido)

**Siete casos de uso estándar** centrados en gobierno comercial y riesgo financiero, no solo en visibilidad de gasto: Contract Renewals & Expirations (evitar renovación automática no deseada), Contract Terms Analysis, Purchase Orders: Budget Controls & Approvals (identificar gasto sin PO asociado), Purchase Orders: Tracking & Visibility, Accounts Payable: Invoice Validation (detectar discrepancias de facturación y validar cargos ARC/RRC), Contract Service Analysis, y Track Committed Vendor Spend. Tres casos personalizados: Invoice Analysis detallado, integración PO-Contrato, y tracking de SLA de proveedor.

**Cuatro componentes instalables de forma incremental, con dependencias estrictas entre sí:**
1. **Vendor Insights Foundation** — visibilidad y racionalización básica (Dashboard, Vendor Summary, Vendor Detail). Requiere datos de Cuentas por Pagar y datos maestros de proveedor.
2. **Vendor Insights PO** — extiende a órdenes de compra (PO Burndown, Spend without POs). **Requiere que Foundation esté completamente instalado y configurado primero.**
3. **Vendor Insights Contracts** — análisis a nivel de contrato (Contract Summary, Contract Expiration, Contract Expiration Notification, Contract to Applications). **Requiere que el componente PO esté instalado antes.**
4. **Vendor Insights ARC/RRC** — análisis de contratos basados en consumo con Additional Resource Charge y Reduced Resource Credit. Se instala después de Contracts.

Esta cadena de dependencias (Foundation → PO → Contracts → ARC/RRC) es un detalle de secuenciación de proyecto que vale la pena tener presente al alcance una implementación por fases.

**Ocho reportes de Vendor Insights**, cada uno atado a su componente: Vendor Insights Dashboard y Vendor Summary (Foundation); Purchase Order Burndown y Spend without POs (PO); Contract Summary, Contract Expiration, Contract Expiration Notification y Contract to Applications (Contracts); ARC RRC Summary y ARC RRC RU Reconcile (ARC/RRC). El reporte de **Contract Expiration Notification** es notable porque puede activarse tanto manualmente como vía **alertas automáticas por correo** cuando se cumplen umbrales de vencimiento — un mecanismo proactivo, no solo de consulta bajo demanda.

**ARC/RRC merece explicación aparte** porque es terminología específica de contratos de consumo: Additional Resource Charge (cargo adicional cuando el consumo excede un umbral) y Reduced Resource Credit (crédito cuando el consumo cae por debajo). El reporte ARC RRC Summary verifica que estos cargos/créditos se apliquen a las tarifas correctas según el uso real, y el ARC RRC RU Reconcile permite conciliar, a nivel de unidad de recurso individual, lo facturado contra lo realmente consumido — clave para detectar sobrefacturación.

**Fuentes de datos típicas** abarcan tres categorías de sistemas: financieros/cuentas por pagar (SAP ECC/AP, Oracle Financials, NetSuite), procurement (SAP Ariba, Coupa, Oracle Procurement Cloud), y gestión de proveedores/contratos (ServiceNow Vendor Management, SAP ERP, Oracle).

## Por qué importa en una conversación con el cliente

La distinción Vendor vs. Vendor Insights es el primer punto a aclarar en cualquier discovery: muchos clientes asumen que "ya tienen visibilidad de proveedores" porque ven el gasto total, pero Vendor Insights responde una pregunta completamente distinta — no cuánto se gastó, sino si ese gasto está gobernado correctamente (con PO, dentro de contrato, sin sobrefacturación).

La cadena de dependencias entre los cuatro componentes de Vendor Insights es un argumento natural para una implementación por fases: empezar con Foundation (rápido de desplegar, alto valor de visibilidad) y avanzar hacia PO, Contracts y ARC/RRC según la madurez y las prioridades del cliente — evita la percepción de que Vendor Insights es "todo o nada".

El caso Contract Expiration Notification con alertas automáticas es un argumento de valor fuerte para clientes preocupados por renovaciones automáticas no deseadas — es una capacidad proactiva, no solo un reporte que alguien tiene que recordar consultar.

La integración con Coupa (mencionada aquí como fuente de datos de procurement) se conecta directamente con la integración de Technology Integrations "Vendor Insights Coupa" que cubriremos en su propia categoría — vale la pena señalar esa conexión si el cliente ya usa Coupa.

## Documentos fuente

- Vendor Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-over.md`
- Vendor Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-reports.md`
  - Vendor Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-vendor-review
  - Vendor Portfolio: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-vendor-portfolio
  - Vendor List: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-vendor-list
  - Vendor Spend by Project: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-vendor-spend-by-project
- Vendor NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-reports-nx.md`
- Vendor Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vendor-getstart.md`
- Vendor Insights Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-overview.md`
- Vendor Insights Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-reports.md`
- Vendor Insights Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/vi-getstar.md`
- CTF Vendors component: install and configure — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctfvendors.md`

*Nota: las URLs de Vendor Review, Portfolio, List y Spend by Project son links reales embebidos en el contenido fuente original de IBM. Los reportes de Vendor Insights (Dashboard, Summary, PO Burndown, Contract*, ARC/RRC) usan enlaces relativos internos (.dita) en el documento fuente, no URLs públicas verificables — quedan pendientes de hipervínculo.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*