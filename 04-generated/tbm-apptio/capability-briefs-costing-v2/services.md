---
tbm_concept: "Services (TCO de servicio de negocio totalmente cargado, portafolio, showback/chargeback)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/services.md
last_updated: "2026-07-05"
---
# Services — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Una excepción a la regla de independencia entre componentes

El brief de Applications documentó que los componentes del "Applications and Services Module" **no dependen entre sí**. Services es la excepción explícita a esa regla: sus prerrequisitos incluyen no solo CTF-Cost Source y CTF-IT Towers, sino también **CT Apps-Applications** — es decir, para tener Services funcionando, Applications debe estar instalado primero. Esto tiene sentido conceptualmente: un servicio de negocio (ej. "Email corporativo") normalmente se compone de una o más aplicaciones subyacentes, así que el costo de servicio depende de que el costo de aplicación ya esté calculado.

## El concepto

El negocio no consume "torres de infraestructura" ni "aplicaciones" — consume servicios: correo electrónico, CRM, banca en línea. Sin una capa de costeo a nivel de servicio, es difícil comunicarle a un stakeholder de negocio cuánto cuesta realmente lo que usa día a día, porque ese costo está disperso entre labor, infraestructura, aplicaciones, vendors y plataformas subyacentes que el negocio nunca ve directamente.

## Cómo lo resuelve Apptio Costing Standard

**Seis casos de uso**, con un fuerte enfoque en TCO totalmente cargado y comparación: Fully Burdened Solution Offering TCO (por fase de ciclo de vida), Unit Cost Analysis for Efficiency (costo por unidad o por usuario, para tarificación y planeación de demanda), Solution Offering Lifecycle Management (con la misma clasificación Tolerate/Invest/Migrate/Eliminate vista en Applications), Cost Optimization and Rationalization, Communicate IT Spend (Showback), y **Peer Benchmarking** (comparar costo de servicio contra benchmarks internos o de industria — la segunda mención de benchmarking explícito en esta base de conocimiento, después de Mainframe).

**Cuatro reportes, con una estructura de "de lo general a lo específico" familiar:**
- **Services Review** — vista de portafolio: costos totales por servicio, tipo y categoría, con tendencias y volúmenes de consumo, identificando concentración de costo.
- **Services Portfolio** — amplía a nivel organizacional: OpEx/CapEx por categoría, quién consume qué (por unidad de negocio), y qué aplicaciones y torres TI impulsan el costo de cada servicio.
- **Service List** — detalle por servicio individual: objetivo de inversión asignado, ofertas de servicio y aplicaciones relacionadas, tendencia de costo unitario y unidad de medida específica del servicio.
- **Services Model** — reporte de trazabilidad (no de negocio), igual en propósito al "Application Model" ya visto: valida cómo se mueve el dato a través de asignaciones, torres/sub-torres y cost pools.

**Sin tabla maestra tradicional — un patrón de datos distinto al resto de componentes.** El componente CT Apps-Services no tiene una "master data table" separada; en su lugar, la tabla **All Business Services** cumple esa función, conteniendo identificación, categorización, propiedad, métricas de consumo y configuración de asignación de cada servicio. Esta tabla se acompaña de una **Reference List** de solo lectura (tipos y categorías de servicio estándar) que el producto advierte explícitamente no modificar.

**Campos requeridos mezclan identificadores técnicos con conceptos de negocio**: Service ID, Service Name, Service Count y Type son requeridos; Service Owner, Service Category, Lifecycle Stage y Objective son recomendados — permitiendo empezar con lo mínimo técnico y enriquecer la clasificación de negocio progresivamente.

**Fuentes de datos** abarcan plataformas de gestión de servicio (ServiceNow, BMC Remedy, Cherwell) para definiciones y catálogo, CMDB para relaciones servicio-aplicación, herramientas de gestión de portafolio de aplicaciones (ServiceNow APM, LeanIX — conectando con la integración SAP LeanIX que veremos en Technology Integrations) para propiedad y ciclo de vida, y sistemas de gestión financiera de TI para métricas de consumo.

## Por qué importa en una conversación con el cliente

Services es, junto con Products (siguiente categoría), el módulo donde el lenguaje técnico de TI finalmente se traduce a lenguaje de negocio — vale la pena posicionarlo explícitamente como "la capa que un ejecutivo de negocio realmente entiende", después de haber costeado infraestructura y aplicaciones en los módulos anteriores.

La dependencia real con Applications (a diferencia de la independencia general del resto del módulo) es un detalle de secuenciación importante para no prometer mal en una propuesta: si el cliente quiere Services rápido, hay que confirmar que Applications ya esté costeado, o incluirlo explícitamente en el alcance.

El caso de uso de Peer Benchmarking es un buen gancho para conversaciones con clientes que buscan validar externamente si su costo de servicio está en línea con la industria — especialmente relevante en banca y seguros, donde la comparación regulatoria y competitiva de costo operativo es una conversación recurrente con el board.

## Documentos fuente

- Services Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-overview.md`
- Services Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-reports.md`
  - Services Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-services-review
  - Services Portfolio: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-services-portfolio
  - Service List: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-service-list
- Services NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-reports-nx.md`
- Services Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/services-gs.md`
- CT Apps - Services component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/services.md`

*Nota: las tres URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*