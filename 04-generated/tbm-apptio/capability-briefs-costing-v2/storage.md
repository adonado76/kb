---
concept: "Storage (TCO de almacenamiento, dos niveles de madurez analítica, capacidad direccionable vs. usada)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/storage.md
last_updated: "2026-07-05"
---
# Storage — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El almacenamiento es un dominio donde la brecha entre capacidad aprovisionada y capacidad realmente usada suele ser enorme, y esa brecha es prácticamente invisible sin instrumentación específica: miles de dispositivos, aplicaciones y ambientes, cada uno con su propia relación entre espacio direccionable y espacio consumido. Sin visibilidad consistente, el resultado típico es sobre-aprovisionamiento, tiering ineficiente (datos poco críticos en almacenamiento caro) y costos más altos de lo necesario — exactamente el mismo patrón de "no se puede optimizar lo que no se puede ver" que aparece en Compute.

## Cómo lo resuelve Apptio Costing Standard

### El mismo patrón de dos soluciones que Compute — no es casualidad, es un patrón de producto consistente

**Storage Cost Overview (CT Apps – Storage)** es la vista fundacional: reportes enfocados (Storage TCO) para visibilidad rápida de costo total y capacidad direccionable vs. usada, sin complejidad operativa profunda — apropiado para discusiones tempranas de optimización y alineación de presupuesto.

**Storage Insights & Optimization (BI – Storage Insights)** es la vista analítica avanzada: responde preguntas específicas como si los tiers de almacenamiento están alineados con la criticidad de la aplicación, qué activos de almacenamiento se acercan al fin de su vida útil, cuánta capacidad no asignada o subutilizada existe, y dónde hay oportunidad de recuperar capacidad y reducir gasto.

### Cuatro casos de uso estándar

Storage Usage and Efficiency (identificar capacidad subutilizada y optimizar ciclos de refresh), Optimize Hybrid Infrastructure (comunicar beneficios de right-sizing a dueños de aplicación), Track and Communicate Hybrid Infrastructure Cost Savings, y Hybrid Infrastructure TCO (comparar costo on-premise vs. nube pública para migración y modernización).

### Ocho reportes en la colección avanzada, con una jerarquía de granularidad clara

La colección Storage Cost Overview aporta un solo reporte: **Storage TCO** (costo y capacidad consolidados, por tipo de sourcing, ambiente, cost pool, torre TI y proveedor, con métricas de espacio direccionable vs. usado).

La colección Storage Insights & Optimization (disponible en el endpoint separado "Infrastructure Insights") tiene ocho reportes organizados de lo general a lo específico: **Storage Summary** (vista empresarial por torre TI, ambiente, proveedor y modelo de sourcing), **Storage Spend Profile** (planeado vs. real, con tendencias de 13 meses de costo por terabyte), **Storage Operational Summary** (vista operativa por ubicación, fabricante y tipo), **Storage Utilization Summary** (costo efectivo por terabyte direccionable y asignado, identificando tiers subutilizados), **Storage Device Details** (nivel de dispositivo físico individual), **Storage LUN Details** (nivel de unidad lógica — el nivel más granular, mostrando qué aplicaciones consumen qué LUN específica), **Storage Financial View** (perspectiva financiera por ubicación, fabricante, producto y cost pool), y **Storage By Application** (vista centrada en aplicación, para chargeback y racionalización).

### Arquitectura de componentes idéntica a Compute

**CT Apps-Storage es fundacional y no agrega reportes propios** — igual que CT Apps-Servers en Compute, crea las tablas y métricas que después expone Storage Insights (BI). Al instalarlo se crean dos grupos de tablas: **Storage** (las LUNs asociadas a los dispositivos físicos) y **Storage Devices** (los dispositivos de almacenamiento físico en sí). Los campos requeridos son notablemente específicos: Actual Units, Environment, Location, Platform, Purpose, Server ID, Sourcing, Storage Device ID, Tier, Total Space, Type — todos marcados como requeridos, no solo recomendados, lo cual indica que este módulo tiene menos tolerancia a datos incompletos que otros ya vistos.

**Prerrequisitos en cascada, igual que Compute**: CT Apps-Storage requiere Cost Source e IT Towers; Storage Insights (BI) requiere adicionalmente que CT Apps-Storage esté ya instalado.

**Fuentes de datos**: sistemas de gestión de activos (inventario de dispositivos y LUN), plataformas de gestión de almacenamiento (capacidad y tier), CMDBs (relaciones con aplicaciones), el libro mayor, y para el nivel Insights & Optimization, adicionalmente VMware vCenter (nube privada) y facturación de nube pública (AWS, Azure, GCP) vía conectores Apptio Datalink.

## Por qué importa en una conversación con el cliente

El paralelismo estructural exacto entre Compute y Storage (mismo patrón de dos niveles, misma lógica de componente fundacional sin reportes propios, mismos prerrequisitos en cascada) es un argumento de eficiencia de implementación importante: un cliente que ya entendió y adoptó el patrón en Compute puede replicar exactamente el mismo modelo mental en Storage, reduciendo la curva de aprendizaje y el esfuerzo de habilitación.

El reporte Storage LUN Details, siendo el nivel más granular documentado en todo este módulo, es el mejor punto de entrada para conversaciones de optimización muy específicas — "qué aplicación está consumiendo esta unidad lógica de almacenamiento cara" es una pregunta que un dueño de aplicación puede responder y actuar de inmediato.

La naturaleza "todo requerido" de los campos de Storage Device (vs. la mezcla de requeridos/recomendados en otros módulos) es un dato concreto para calibrar el esfuerzo de preparación de datos durante el discovery — vale la pena confirmar temprano si el cliente tiene ese nivel de completitud en su inventario de almacenamiento.

## Documentos fuente

- Storage Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-overview.md`
- Storage Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-reports.md`
  - Storage Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-storage-summary
  - Storage Spend Profile: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-spend-profile
  - Storage Operational Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-operational-summary
  - Storage Utilization Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-utilization-summary
  - Storage Device Details: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-device-details
  - Storage LUN Details: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-storage-lun-details
  - Storage Financial View: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-financial-view
  - Storage By Application: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-by-applications
- Storage Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/storage-gs.md`
- CT Apps - Storage component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/storage.md`

*Nota: las URLs son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*