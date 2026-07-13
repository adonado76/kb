---
concept: "Compute (TCO híbrido de servidores físicos/virtuales/nube, utilización, dos niveles de madurez analítica)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/infra-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/servers.md
last_updated: "2026-07-05"
---
# Compute — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de alcance

`infra-summary.md` no es específico de Compute — es el resumen de **toda la sección Infrastructure Use Cases** (Compute, Storage, Network Devices, Mainframe, Data Centers, Service Desk, Communications). Lo incluimos aquí por ser donde vive en la estructura de carpetas, pero se retoma como introducción del capítulo "Infrastructure Use Cases" al ensamblar el documento consolidado.

## El concepto

El compute — servidores físicos, máquinas virtuales, instancias de nube — suele ser el dominio de infraestructura más grande y más difícil de optimizar, porque su costo real depende de una combinación de infraestructura, software, labor y soporte, y su eficiencia depende de qué tan bien la utilización real coincide con la capacidad aprovisionada. Sin una vista unificada de costo y utilización a través de on-premise, nube privada y nube pública, las decisiones de consolidación, right-sizing o migración a la nube se toman con información parcial.

## Cómo lo resuelve Apptio Costing Standard

### Dos soluciones, con el mismo patrón de dos niveles ya visto en Public Cloud

**Compute Cost Overview (CT Apps – Servers)** es la vista fundacional: pocos reportes enfocados (Infrastructure & Cloud Summary, Server TCO), pensada para organizaciones que buscan visibilidad rápida sin complejidad operativa profunda — útil para discusiones tempranas de optimización, alineación de presupuesto, y evaluaciones iniciales de nube privada a pública.

**Compute Insights & Optimization (BI – Server Insights)** es la vista analítica avanzada, construida sobre la anterior: ocho reportes que cubren costo, capacidad, utilización, costo unitario y consumo a nivel de aplicación, a través de infraestructura física, virtual y de nube. Responde preguntas mucho más específicas: qué plataformas de servidor requieren expansión, retiro o migración; cómo están evolucionando los costos unitarios (por hora de servidor, por core, por GB); qué aplicaciones están impulsando anomalías de costo.

### Cuatro casos de uso estándar

Hybrid Compute TCO (comparar costo entre on-premise, nube privada y pública), Server Utilization and Efficiency (identificar capacidad subutilizada), Hybrid Infrastructure Optimization (right-sizing alineado a demanda de negocio), y Track and Communicate Compute Cost Savings (capturar y reportar ahorros realizados y proyectados).

### Reportes — dos colecciones con propósitos distintos

La colección **Compute Cost Overview** tiene dos reportes: **Infrastructure & Cloud Summary** (punto de entrada centralizado — servidores, almacenamiento y nube pública en una sola vista, con navegación hacia reportes detallados) y **Server TCO** (costo total consolidado por perfil de virtualización, ambiente, cost pool y proveedor).

La colección **Compute Insights & Optimization** (disponible en un endpoint separado, "Infrastructure Insights") tiene ocho reportes: Compute Summary (vista general de gasto), Compute Spend Profile (estructura y tendencia de costo, con históricos de 13 meses), Compute Operational Summary (métricas operativas — CPU, memoria, costo por hora de instancia — por perfil de virtualización), Compute Utilization Summary (combina costo, capacidad y utilización para detectar sub/sobre-utilización), Host Server Details (nivel de host físico, identificando candidatos a consolidación por alto costo/baja utilización), Logical Server Details (nivel de máquina virtual, para right-sizing), Compute Financial View (perspectiva financiera por clase, ambiente, ubicación y SO), y Compute by Applications (vista centrada en aplicación, conectando horas de servidor y costo por hora a workloads de negocio específicos).

### El componente CT Apps-Servers: fundacional, sin reportes propios

Un detalle importante de arquitectura: **CT Apps-Servers no agrega reportes nuevos** — es un componente prerrequisito que crea las métricas que después expone el componente Server Insights. Al instalarlo, se crean tres tablas relacionadas: **Servers** (todos los servidores físicos y virtuales, excluyendo hypervisors), **Physical Server** (solo servidores físicos, incluyendo hypervisors), y **Hypervisor** (solo los hypervisors). La lógica de filtrado entre estas tres tablas es específica y requiere disciplina: si una VM puede asociarse al servidor que la hospeda, se lista en la tabla Hypervisor; si no puede asociarse, el costo del hypervisor se distribuye entre las VMs ponderado por su tamaño.

**Prerrequisitos en cascada**: CT Apps-Servers requiere Cost Source e IT Towers; Server Insights (BI) requiere adicionalmente que CT Apps-Servers ya esté instalado — la misma lógica de dependencia por capas vista en otros módulos.

**Fuentes de datos típicas**: herramientas de monitoreo de servidores (CPU, memoria, utilización), plataformas de virtualización (VMware, Hyper-V), sistemas de gestión de activos, CMDBs (para relaciones servidor-aplicación), herramientas de service management, y el libro mayor para costos de hardware/software/labor/soporte asociados.

## Por qué importa en una conversación con el cliente

El patrón de dos niveles (Cost Overview → Insights & Optimization) es, otra vez, una excelente palanca de venta incremental y de secuenciación de proyecto: empezar con visibilidad rápida y expandir hacia análisis operativo profundo cuando el cliente ya validó el valor inicial — el mismo argumento que funciona para Public Cloud Integrated vs. IT Finance.

Los reportes de "Host Server Details" y "Logical Server Details" dan un argumento muy concreto para conversaciones de optimización de infraestructura: identificar hosts con alto costo y baja utilización como candidatos directos a consolidación o retiro es un hallazgo cuantificable, no una recomendación genérica.

El reporte "Compute by Applications" es el puente natural hacia el módulo de Applications (Solution Use Cases): permite mostrar en una sola narrativa cómo el costo de infraestructura de cómputo se traduce en el costo total de una aplicación de negocio específica.

## Documentos fuente

- Summary (Infrastructure Use Cases, sección completa) — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/infra-summary.md`
- Compute Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-overview.md`
- Compute Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-reports.md`
  - Infrastructure & Cloud Summary / Server TCO: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=r-summary
  - Compute Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-compute-summary
  - Compute Spend Profile: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=r-spend-profile
  - Compute Operational Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=r-operational-summary-1
  - Compute Utilization Summary, Host Server Details, Logical Server Details, Compute Financial View, Compute by Applications: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-compute-report-collection-hbm
- Compute Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/compute-gs.md`
- CT Apps - Servers component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/servers.md`

*Nota: las URLs son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*