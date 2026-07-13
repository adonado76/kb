---
concept: "Data Centers (TCO unificado de instalaciones, capacidad power/cooling/espacio, alcance explícitamente limitado a facility)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-nx-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-config-guide.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/datacenters.md
last_updated: "2026-07-05"
---
# Data Centers — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de producto: solución unificada, reemplazando dos anteriores

El propio Overview declara explícitamente que las soluciones previas — "Data Center Cost Overview" y "Data Center Insights & Optimization" — están **deprecadas**, reemplazadas por una solución única: **IBM Apptio Data Center TCO**. Este es el único módulo de Infrastructure Use Cases visto hasta ahora sin el patrón de "dos soluciones coexistentes" (Cost Overview vs. Insights & Optimization) — aquí el producto consolidó a un solo camino.

## El concepto

La demanda de data center está creciendo por workloads de IA, arquitecturas híbridas, repatriación desde la nube y mayor densidad de racks — al mismo tiempo que suben los costos de energía y enfriamiento. Sin una vista unificada de costo, capacidad y restricciones operativas, es difícil planear consolidación, migración o expansión con confianza, y las restricciones de capacidad (power, cooling, espacio) suelen descubrirse de forma reactiva, no proactiva.

## Cómo lo resuelve Apptio Costing Standard

### Cinco casos de uso, en dos versiones ligeramente distintas entre el Overview y la Guía de Configuración

Del Overview: Data Center TCO & Unit Economics (costo por rack, por área, por kilowatt), Capacity Utilization & Constraint Planning (capacidad disponible vs. comprometida en power/cooling/espacio), Vendor Labor & Contract Spend Transparency, Infrastructure Cost Allocation (a compute y storage), y Application & Service Cost Allocation (showback/chargeback a aplicaciones y servicios).

### Un límite de alcance explícito y crítico para no prometer de más

**Data Center TCO se enfoca exclusivamente en costos de instalación y operación** — power y energía, cooling, espacio (leasing, colocation, o instalación propia), mantenimiento y operaciones, seguridad, y labor relacionada con la instalación. **Excluye explícitamente el hardware de infraestructura** (servidores, almacenamiento, dispositivos de red) — esos activos se modelan en sus propios módulos (Compute, Storage, Network Devices) y se conectan a Data Centers solo a través de la lógica de asignación. Esta distinción es fácil de pasar por alto y vale la pena aclararla proactivamente: "Data Center" en este producto significa la instalación física, no todo lo que corre dentro de ella.

### Tres reportes principales, más un reporte administrativo

**Data Centers Review** — vista consolidada de spend, OpEx/CapEx, utilización de racks, consumo de power, y costos de labor/vendor, con capacidad de comparar sitios por región, gerente, tipo de instalación (colocation/leased) y tier.

**Data Centers Capacity** — utilización y capacidad disponible en pies cuadrados, unidades de rack, power y cooling; identifica instalaciones con restricción y compara densidad de potencia por rack entre ubicaciones. Usa **codificación de color basada en umbrales**: rosa si la utilización excede el umbral alto, amarillo si está por debajo del umbral bajo, blanco si está en rango normal.

**Infrastructure & Hosting Details** (solo en la versión Classic/NX de reportes, no mencionado en la guía de configuración más reciente como reporte separado) — vista de qué servidores, almacenamiento, mainframe, aplicaciones y servicios están alojados dentro de cada data center específico.

La **Guía de Configuración** más reciente documenta una arquitectura ligeramente distinta con **Data Centers Review, Data Centers Analysis y Capacity report** como los tres reportes primarios, más un cuarto reporte administrativo (**Data Centers Admin**) para gestionar métodos y ponderaciones de asignación, y un reporte de **Enriquecimiento** para completar datos faltantes sin sobrescribir los existentes.

### Lógica de asignación documentada con un nivel de detalle inusualmente alto

**De IT Resource Tower a Data Center**: por defecto usa una combinación de pies cuadrados ocupados del data center y porcentaje de asignación de infraestructura.

**De Data Center a Infraestructura** (Servers, Storage, Mainframe): impulsado por alineación de ubicación y drivers basados en uso — horas de servidor, GB/TB de almacenamiento, o consumo de mainframe (MIPS/MSUs). El método de asignación es configurable entre dos opciones administrables desde el reporte Data Centers Admin: **Assumed Percentage Split** (split fijo entre Compute y Storage cuando no hay datos granulares) o **Table Upload Method** (asignación basada en datos detallados, como consumo de power, a nivel de data center individual).

**Para la asignación de Network hacia Data Centers**, existen dos estrategias documentadas explícitamente con sus trade-offs: la **Legacy Allocation Strategy** (más precisa, pero requiere datos granulares de dispositivos de red por data center — apropiada para ambientes maduros) y la **Alternative Allocation Strategy** (más simple, usa un driver de alto nivel como ubicación — apropiada cuando no hay datos a nivel de dispositivo).

**Tres categorías de datos requeridas**: datos financieros (vía IT Resource Towers, categorizados bajo una sub-torre dentro de la torre Data Center), datos de uso (tabla Data Centers Feed, con métricas requeridas de uso/capacidad de rack y power, y recomendadas de espacio y cooling — típicamente de plataformas DCIM, BMS, o LogicMonitor), y metadata (identificadores core como Data Center ID/Nombre/Región/Tier, requeridos para asignación y reporte).

**El componente CT Apps-Data Centers, igual que Servers y Storage, no aporta reportes propios** — es fundacional, crea las tablas de datos que exponen los reportes del componente de Optimización.

## Por qué importa en una conversación con el cliente

El límite explícito de alcance (Data Center = instalación, no el hardware dentro de ella) es la aclaración más importante a hacer temprano en cualquier conversación sobre este módulo — evita la expectativa incorrecta de que activar Data Centers dará automáticamente TCO de servidores o almacenamiento; esos siguen siendo módulos separados que se conectan vía asignación.

Las dos opciones de asignación de Network (Legacy vs. Alternative) son un buen ejemplo para explicar el principio general de "empezar simple, refinar con madurez de datos": un cliente sin telemetría granular de dispositivos de red por data center puede empezar con la estrategia Alternative y migrar a Legacy cuando tenga mejores datos.

El reporte de Capacity con codificación de color por umbral es un argumento de valor operativo inmediato para gerentes de instalación: identificar visualmente qué sitios están en riesgo de saturación de power/cooling antes de que se convierta en una crisis de expansión no planeada.

## Documentos fuente

- Data Centers Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-overview.md`
- Data Centers Classic Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-reports.md`
- Data Centers NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-nx-reports.md`
- Data Centers TCO - Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-gs.md`
- Data Centers TCO - Configuration Guide — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/dc-config-guide.md`
- CT Apps - Data Centers component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/datacenters.md`

*Nota: no se encontraron links públicos de ibm.com/docs embebidos en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*