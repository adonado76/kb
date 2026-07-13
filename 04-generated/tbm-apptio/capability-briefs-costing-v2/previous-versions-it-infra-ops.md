---
concept: "Previous Version Layouts — IT Infrastructure & Operations (benchmarking histórico de eficiencia operativa, gestión de nube reservada/potencial ahorro/calidad de tagging)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itinfraopsreports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/aboutitinfraopsreports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopssummary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsserversefficiency.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsstorageanalysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsstorageefficiency.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsdatacenteranalysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsservicedeskanalysis.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/benchmarkingsummaryreports103.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmsummarycollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmcomputecollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmstoragecollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmprivatecloudcollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmmigrationscollection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/reservedinstances.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/potentialsavings.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/monthlytcoreports12.4.1.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/reconcile.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/taggingquality.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/infrastructure-and-cloud-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/benchmarking-report-collection.md
last_updated: "2026-07-05"
---
# Previous Version Layouts — IT Infrastructure & Operations — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de versión

Igual que Data Quality Reports, este contenido proviene de versiones anteriores del producto (v103, v104). Se documenta aquí porque varios de sus conceptos — benchmarking de eficiencia operativa, gestión de instancias reservadas, calidad de tagging — probablemente persisten en la interfaz actual bajo otros nombres (algunos ya vistos en los briefs de Compute, Storage y Public Cloud), y vale la pena tenerlos mapeados para no prometerle al cliente un reporte con un nombre que ya cambió.

## El concepto

Antes de que el producto organizara sus reportes en la estructura actual de Infrastructure/Solution Use Cases, ya existía una necesidad de responder dos preguntas específicas: qué tan eficientemente se está operando la infraestructura comparado contra un benchmark, y cuánto se está aprovechando (o desperdiciando) la inversión ya comprometida en la nube pública (instancias reservadas, tagging). Esta categoría agrupa los reportes históricos que respondían esas preguntas.

## Cómo lo resuelve Apptio Costing Standard

### IT Operations Reports (v103) — el antecesor directo de Compute/Storage/Data Centers/Service Desk

Seis reportes que, en retrospectiva, son claramente los precursores de los módulos ya documentados: **Summary** (vista consolidada, precursor de los "Summary" ya vistos en Compute/Storage/Data Centers), **Servers Efficiency** (precursor conceptual de Host Server Details y Compute Utilization Summary), **Storage Analysis** y **Storage Efficiency** (precursores de Storage Utilization Summary y Storage LUN Details), **Data Centers Analysis** (precursor de Data Centers Capacity), y **Service Desk Analysis** (precursor de Service Desk Task/Resource Details).

### Hybrid Business Management (HBM) Reports (v104) — cinco colecciones de benchmarking

**Benchmarking Summary Reports (v103)** y su evolución en v104 introducen el concepto de comparar el desempeño de costo y eficiencia de la organización contra **benchmarks externos de industria** — la misma capacidad que reaparece, más adelante en la evolución del producto, integrada directamente en el reporte de Mainframe TCO – Cost Pool Composition & Peer Comparison ya documentado.

Las cinco colecciones HBM (**Summary, Compute, Storage, Private Cloud, Migrations**) sugieren que, en esta versión del producto, el benchmarking de eficiencia se organizaba como su propia línea de reportes paralela a los reportes operativos de cada dominio, en lugar de estar incorporado directamente dentro de cada módulo (como sí ocurre hoy en Mainframe). La colección de **Migrations** es particularmente interesante como precursora conceptual de lo que hoy es el módulo completo de Hybrid IT TCO Impact — comparar el efecto de mover cargas de trabajo entre ambientes, ya documentado con mucho más rigor metodológico (freeze de TCO a 12 meses, workbenches de migración) en ese módulo actual.

### Cloud Reports (v104) — gestión de compromiso de nube pública

**Reserved Instances** — visibilidad de utilización y cobertura de instancias reservadas, el precursor directo de la mecánica de asignación de costo de RI ya documentada en detalle en el brief de Public Cloud (ponderación por familia de instancia, sistema operativo, región).

**Potential Savings** — identifica oportunidades de ahorro no capturadas (instancias bajo-utilizadas, oportunidades de compra de RI adicionales) — el precursor conceptual de los reportes de optimización ya vistos en Compute Insights & Optimization.

**Monthly TCO Reports (v12.4.1)** — vista de costo total mensual de nube, versión anterior de los reportes Cloud Monthly TCO ya documentados en Public Cloud Integrated.

**Reconcile** — concilia el costo modelado contra la factura real del proveedor — precursor directo del reporte Cloud Monthly Reconciliation ya visto en Public Cloud.

**Tagging Quality** — mide qué porcentaje de recursos de nube tienen tags completos y correctos, una capacidad crítica ya que el brief de Public Cloud estableció que el tagging es el mecanismo central para atribuir gasto de nube a unidades de negocio reales — sin buena calidad de tagging, todo el showback/chargeback de nube pierde precisión. Este reporte es, en efecto, el equivalente de Data Quality Reports pero específico para el dominio de nube pública.

## Por qué importa en una conversación con el cliente

Esta categoría es, sobre todo, un mapa de continuidad histórica útil para conversaciones de upgrade: si un cliente actual sigue usando alguno de estos reportes de v103/v104, este brief ayuda a identificar cuál es su equivalente probable en la versión actual documentada en los briefs de Compute, Storage, Data Centers, Service Desk, Mainframe y Public Cloud — evitando que un upgrade se perciba como "perder" un reporte que en realidad fue reemplazado por una versión mejorada.

El reporte de Tagging Quality merece mención explícita y proactiva en cualquier conversación sobre Public Cloud: es fácil que un cliente adopte el módulo de nube pública sin darse cuenta de que la calidad de su tagging determina directamente la calidad de su showback — vale la pena preguntarlo en discovery antes de prometer resultados de asignación de nube perfectamente precisos.

La colección HBM Migrations, como precursora del actual Hybrid IT TCO Impact, es un buen dato para conversaciones con clientes de larga data del producto: pueden reconocer el concepto general de comparación pre/post migración, y vale la pena explicarles que la versión actual (con freeze de 12 meses y workbenches dedicados) es sustancialmente más rigurosa que lo que probablemente usaron en el pasado.

## Documentos fuente

- IT Infrastructure and Operations reports (índice, v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itinfraopsreports.md`
- About the IT Infrastructure and Operations reports (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/aboutitinfraopsreports.md`
- IT Operations - Summary report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopssummary.md`
- IT Operations - Servers Efficiency Target report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsserversefficiency.md`
- IT Operations - Storage Analysis report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsstorageanalysis.md`
- IT Operations - Storage Efficiency Target report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsstorageefficiency.md`
- IT Operations - Data Centers Analysis report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsdatacenteranalysis.md`
- IT Operations - Service Desk Analysis report (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/itopsservicedeskanalysis.md`
- Benchmarking Summary reports (v103) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v103/benchmarkingsummaryreports103.md`
- Hybrid Business Management - Summary Collection (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmsummarycollection.md`
- Hybrid Business Management - Compute Collection (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmcomputecollection.md`
- Hybrid Business Management - Storage Collection (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmstoragecollection.md`
- Hybrid Business Management - Private Cloud Collection (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmprivatecloudcollection.md`
- Hybrid Business Management - Migrations Collection (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/hbmmigrationscollection.md`
- Reserved Instances report (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/reservedinstances.md`
- Potential Savings report (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/potentialsavings.md`
- Monthly TCO Reports (v12.4.1) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/monthlytcoreports12.4.1.md`
- Reconcile report (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/reconcile.md`
- Tagging Quality report (v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/taggingquality.md`
- Infrastructure and Cloud Report Collection (índice, v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/infrastructure-and-cloud-report-collection.md`
- Benchmarking Report Collection (índice, v104) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports-v104/benchmarking-report-collection.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos pendientes según lo acordado.*
