---
concept: "Public Cloud (dos soluciones — Integrated vs. IT Finance —, TCO de nube, Reserved Instances, mapeo ATUM, tagging para showback)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aws.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/awsreserved.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/awsservices.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azure.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azuremap.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azurereserved.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudatum.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudconcepts.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/clouddailyhourlyreports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudmapping.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloud_mapping_files.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudservices.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudservices-12-5.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mapawstoatum.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mapawstoschema.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/tagazuretoschema.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/summarycloudconfigsteps-4246.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/reservedcosts.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/estmatednonprov.md
last_updated: "2026-07-05"
---
# Public Cloud — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Una decisión de arquitectura antes que nada: dos soluciones, no una

El hallazgo más importante de esta categoría es que Apptio ofrece **dos capacidades de Public Cloud distintas**, no una sola con opciones — y el propio producto documenta explícitamente cómo elegir entre ellas.

| Consideración | Public Cloud Integrated | Public Cloud for IT Finance |
|---|---|---|
| Visibilidad de costo del proveedor | Sí | Sí |
| Incluye costos no-proveedor (labor, soporte) | Sí | No |
| Integrado con Costing Standard y TBM | Sí | No |
| TCO de nube y asignación avanzada | Sí | No |
| Persona objetivo | IT Finance, FinOps, CCoE, Service Owners | IT Finance |
| Tiempo a valor | Moderado | Muy rápido |
| Complejidad de implementación | Alta | Baja |

**Public Cloud Integrated** combina la factura del proveedor de nube con datos financieros empresariales del libro mayor, dando una vista de TCO completa que incluye costos no-proveedor (labor, soporte, servicios compartidos) asignados a la Torre de Recursos TI de Cloud y ponderados por consumo. Está pensado para organizaciones con prácticas maduras de gestión financiera de TI que necesitan chargeback/showback real.

**Public Cloud for IT Finance** es una solución independiente y ligera, enfocada exclusivamente en el gasto facturado por el proveedor, consolidando múltiples proveedores en una vista única sin incorporar costos no-proveedor. Está optimizada para velocidad — se puede habilitar en días, no semanas — ideal para equipos de finanzas que solo necesitan visibilidad rápida sin la complejidad de integración total del modelo.

## El concepto

El gasto en nube pública tiene una característica que lo distingue de todo el resto del gasto de TI: cambia constantemente (los proveedores actualizan su catálogo de servicios y precios de forma continua), y su factura por sí sola no cuenta la historia completa — el costo real de operar en la nube incluye labor, soporte, y servicios compartidos que nunca aparecen en la factura de AWS o Azure. Sin un modelo específico para nube, una organización ve el gasto facturado pero no el costo total de propiedad, y no puede optimizar decisiones de compra (instancias reservadas, right-sizing) con datos consolidados.

## Cómo lo resuelve Apptio Costing Standard

### Casos de uso, en una progresión de madurez documentada explícitamente

1. **Cloud Cost Allocation & Showback (Fundacional)** — asignar y rastrear costos de nube por departamento, equipo, ambiente, aplicación, producto o servicio.
2. **Cloud Usage by Application (Intermedio)** — etiquetar y asociar el consumo de nube con aplicaciones/servicios/productos para reducir sprawl y mejorar el análisis de TCO.
3. **Pre-purchased Cloud Capacity Management (Intermedio)** — monitorear capacidad prepagada (instancias reservadas) para asegurar tarifas más bajas y maximizar utilización.
4. **Cloud Cost Optimization (Avanzado)** — comparar y controlar el gasto de nube para identificar ineficiencias.

### Reportes de Public Cloud Integrated

Cuatro reportes en la colección Cloud: **Cloud Monthly TCO** (gasto mensual total combinando proveedor + no-proveedor, identificando qué aplicaciones/torres impulsan el consumo), **Cloud TCO Cost Driver** (explica la composición del TCO separando componentes de proveedor vs. no-proveedor — labor, software, instalaciones), **Cloud Services Unit Cost** (tendencias de consumo y tarifa efectiva por categoría de servicio — Compute, Storage, Network, Data, Platform), y **Cloud Monthly Reconciliation** (concilia el costo modelado contra la factura original del proveedor, línea por línea, para control financiero y auditoría).

### Reportes de Public Cloud for IT Finance

Los reportes NX de Public Cloud TCO ofrecen un resumen financiero/operativo con YTD y créditos aplicables, tendencia de costo por servicio de nube (AWS y Azure), efectividad del modelo de compra comparado contra benchmarks best-in-class, y tendencia de tarifa unitaria en relación a cambios de consumo — con reportes de drill-down específicos para Cloud Cost Details, CPU Hours y Storage.

### Cómo llegan los datos: la conexión directa con Cloudability

**Public Cloud Integrated** obtiene sus datos de costo de nube desde **Cloudability**, ingeridos vía **Apptio Data Management (ADM)** — el mismo mecanismo de integración cross-producto ya documentado en la base de conocimiento de Apptio Planning. Los datos se refrescan en un cronograma y se cargan en tablas mensuales de facturación específicas por proveedor (`cldy_monthly_aws`, `cldy_monthly_azure`, `cldy_monthly_gcp`), que luego se normalizan vía CLDY Transform Master Data y se clasifican consistentemente vía Cloud Service Provider Master Data, alineadas a la taxonomía ATUM.

**Public Cloud for IT Finance** también usa Cloudability como fuente primaria (mismas tablas `cldy_monthly_*`), más reportes de Reserved Instance vía servicios REST de Cloudability para calcular efectividad de instancias reservadas y savings plans. Requiere mapear **cinco datasets de entrada**: Account Mapping (nombres de cuenta), BU Reference Input (normaliza regiones/identificadores a unidades de negocio), Cloud Tower Mapping (familias de uso de nube a nombres de Torre normalizados), CC Input (centros de costo — los valores no mapeados aparecen como "Unassigned"), y RI Input (horas reservadas para calcular utilización).

### La capa técnica: mapeo ATUM, Reserved Instances y tagging

Tres mecanismos técnicos, documentados con mucho detalle en las guías de configuración, merecen explicación (no como manual paso a paso, sino como principios que un practicante de TBM debe entender):

**Mapeo de servicios a ATUM.** Los conectores CBM y AWS DataLink mapean las líneas de factura de cada proveedor a atributos ATUM (Torres/Sub-Torres de TI, jerarquía de Servicios TBM, unidad de medida normalizada). Como los proveedores actualizan su catálogo de servicios constantemente, **Apptio actualiza estos archivos de mapeo mensualmente** — el historial de versiones documentado se remonta a 2016 para AWS y 2016 para Azure, evidencia de que este es un mantenimiento continuo, no una configuración de una sola vez. Si un cliente usa el Multicloud Connector moderno, el mapeo ocurre automáticamente antes de que la factura llegue al ambiente CBM; con el conector legado, requiere actualización manual del dataset.

**Asignación de costos de Reserved Instances (RI).** Este es uno de los mecanismos más sutiles documentados: los cargos de RI **no aparecen en la factura de las líneas de uso que se benefician de ellas** — llegan como una compra separada. Apptio amortiza el costo upfront de la RI a lo largo de su plazo (mensualmente), y luego **distribuye ese costo amortizado entre las líneas de factura correspondientes**, ponderando por familia de instancia, sistema operativo, región/zona de disponibilidad y cantidad de uso de cada línea. Para instancias EC2 flexibles más nuevas, la asignación usa familia de instancia y región en lugar de tipo específico, ponderando por un factor de normalización de tamaño relativo. Un detalle operativo importante: cuando una RI se modifica, AWS crea una nueva entrada de compra pero no traslada el costo upfront proporcional a la nueva entrada — sin una configuración adicional, la RI modificada aparecerá artificialmente más barata de lo que realmente es.

**Tagging para showback/chargeback.** Las etiquetas de recursos de nube (Application Name, Environment, Cost Center, System Owner, Project) se mapean al esquema de Apptio para poder atribuir el gasto de nube a unidades de negocio reales. En AWS esto se hace vía el AWS Cost Allocation Report; en Azure, las etiquetas llegan como una cadena JSON dentro de la columna Tags de la factura EA y requieren parseo explícito (fórmula por cada tag a extraer).

**Costos no-proveedor estimados**, como opción manual para clientes que aún no tienen actuals del libro mayor cargados en Costing Standard — la alternativa preferida es que estos costos fluyan automáticamente desde el modelo de costos vía el objeto IT Resource Towers marcado como "Is Cloud = Yes".

## Por qué importa en una conversación con el cliente

La elección entre Public Cloud Integrated y Public Cloud for IT Finance es la pregunta de discovery más importante de todo este módulo — y una excelente palanca de venta incremental: un cliente puede empezar con la versión ligera (IT Finance) para obtener valor en días, y migrar después a Integrated cuando su práctica de FinOps madure y necesite TCO completo con labor y servicios compartidos incluidos.

La mecánica de asignación de Reserved Instances es un tema técnico que vale la pena explicar con el ejemplo del "costo artificialmente bajo tras una modificación de RI" — es el tipo de detalle que, si no se anticipa, genera desconfianza en los números del modelo durante un piloto.

La conexión con Cloudability vía ADM es el mismo patrón de integración ya documentado para Apptio Planning — vale la pena señalar esta consistencia arquitectónica en conversaciones donde el cliente evalúa el portafolio completo de Apptio: Cloudability alimenta datos de nube tanto a Planning (para presupuesto/forecast) como a Costing Standard (para actuals y TCO), vía el mismo mecanismo de plataforma.

## Documentos fuente

- Public Cloud Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-overview.md`
- Public Cloud Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-reports.md`
- Public Cloud TCO NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-reports-nx.md`
- Public Cloud Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/pc-getstart.md`
  - Public Cloud for IT Finance reports: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcooverview
  - Public Cloud for IT Finance configuration: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-public-cloud-tcoconfiguration
  - ADM Cloudability entity guide: https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=creation-entity-cloudability
- Amazon Web Services configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aws.md`
- AWS Reserved Instances configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/awsreserved.md`
- AWS Services Mapping — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/awsservices.md`
- Microsoft Azure and other providers configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azure.md`
- Azure Services Mapping — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azuremap.md`
- Azure Reserved Instances — Ingestion and Cost Allocations — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/azurereserved.md`
- Cloud configuration and ATUM 2.0 — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudatum.md`
- Cloud concepts — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudconcepts.md`
- Cloud Daily/Hourly Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/clouddailyhourlyreports.md`
- Cloud mapping — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudmapping.md`
- Cloud Mapping Files — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloud_mapping_files.md`
- Cloud Services configuration in Costing Standard — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudservices.md`
- Configuring Cloud for Costing Standard 12.1–12.5x — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/cloudservices-12-5.md`
- Map AWS Marketplace to ATUM — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mapawstoatum.md`
- Map AWS tags to Apptio Schema — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mapawstoschema.md`
- Tag values in Azure to Apptio Schema — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/tagazuretoschema.md`
- Summary of Cloud Configuration Steps — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/summarycloudconfigsteps-4246.md`
- Reserved Instance Costs - Allocations within Apptio — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/reservedcosts.md`
- Enter estimated non-provider costs — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/estmatednonprov.md`

*Nota: las URLs de "Public Cloud for IT Finance reports/configuration" y "ADM Cloudability entity guide" son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*