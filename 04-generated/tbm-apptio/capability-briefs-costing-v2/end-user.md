---
concept: "End User (TCO de dispositivos de usuario final; dos soluciones arquitectónicamente independientes, no en capas)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/sol-summ.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eu-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eud-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eud-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/enduserdevices.md
last_updated: "2026-07-05"
---
# End User — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Nota de alcance

`sol-summ.md` es el resumen de **toda la sección Solution Use Cases** (End User, Applications, Services, Products, Business Units), no específico de End User. Se retoma como introducción del capítulo al ensamblar el documento consolidado.

## Un patrón arquitectónico distinto a todo lo visto hasta ahora

Hasta este punto, cada "par" de soluciones (Public Cloud, Compute, Storage, Service Desk) seguía el mismo patrón: una solución fundacional "Cost Overview" y una solución "Insights & Optimization" que se **construye encima** de la fundacional, compartiendo el mismo modelo de costo central. **End User rompe ese patrón explícitamente**: End User Devices se integra al modelo de costo central (jala datos de IT Resource Towers y Communications), pero **End User Insights es una solución independiente que no requiere configuración del modelo de costo central en absoluto** — carga sus datos directamente en tablas de entrada propias (Active Directory, End User Devices, Labor Data), sin prerrequisitos. El propio documento lo declara: "This is an independent solution that does not require configuration of the core cost model."

## El concepto

Los dispositivos de usuario final — laptops, desktops, tablets, móviles — representan un costo de fleet grande y disperso, con un problema adicional que otros dominios de infraestructura no tienen con la misma intensidad: gobierno de activos a nivel de persona (¿quién tiene qué?, ¿está inactivo?, ¿tiene garantía vigente?). Sin visibilidad de inventario, edad, cumplimiento y asignación, el resultado típico es sobre-compra de refresh, dispositivos huérfanos sin reclamar, y exposición de cumplimiento por sistemas operativos no soportados.

## Cómo lo resuelve Apptio Costing Standard

### End User Devices — integrado, fundacional, sin reportes propios

**Un caso de uso**: Cost Allocation to Services — asignar el costo de dispositivos a servicios de usuario final y servicios de negocio específicos. El documento declara explícitamente: **"There are no out of box reports with this solution"** — es puramente una capa de costeo y asignación, sin analítica visible propia. El flujo de asignación: de IT Resource Towers y Communications hacia End User Devices, y de ahí hacia Business Services. Los campos requeridos son mínimos (Device Count, Device Type; Asset ID Number recomendado) — el umbral de entrada más bajo de todos los módulos vistos hasta ahora.

### End User Insights — independiente, con la colección de reportes más orientada a gestión de activos vista hasta ahora

**Siete casos de uso**: Fleet Spend Visibility, Device Cost Allocation, Device Age & Refresh Analysis, Inventory & Utilization Insights, **Multiple & Orphan Device Identification**, Compliance Monitoring, y Optimization & Cost Reduction.

**Siete reportes**, cada uno resolviendo un problema de gobierno de activos específico:
- **Fleet Overview** — snapshot del fleet completo: tamaño, composición, mezcla de propiedad (empresa/leased/BYOD), edad, exposición EOL, no-cumplimiento, volúmenes de adquisición.
- **Compliance** — dispositivos con sistemas operativos no compatibles, con detección de casos donde el usuario del último login **difiere del dueño asignado del dispositivo** — una señal de posible problema de asignación o cumplimiento.
- **Age Analysis** — distribución de edad en cuatro categorías (ya expirado, 1-6 meses a EOL, 7-12 meses, más de 12 meses), con costo de refresh estimado por categoría.
- **Multiple Devices** — usuarios con más de un dispositivo asignado, para identificar sobre-asignación y oportunidades de recuperación.
- **Orphaned Devices** — el reporte más sofisticado de la colección: identifica dispositivos potencialmente huérfanos bajo **cinco condiciones distintas** (asignados a un Labor ID inactivo en RRHH; asignados a un Labor ID activo pero sin uso en 30-90 días; asignados a un Labor ID que no existe en los datos de RRHH; asignados a un Labor ID no encontrado en RRHH pero con uso reciente — una señal de calidad de datos, no necesariamente de abandono; y sin uso durante el período de inactividad definido).
- **Spare Capacity** — inventario disponible (en stock, desplegado sin asignar, cercano a EOL) para redistribución antes de nueva compra.
- **Warranty Analysis** — perfil de garantía en cuatro grupos de antigüedad, para planeación de refresh basada en vencimiento de garantía, no solo en edad del dispositivo.

**Tres fuentes de datos que se combinan de forma distintiva.** A diferencia de otros módulos que dependen principalmente del libro mayor, End User Insights combina **Active Directory** (actividad de uso y login), **HR/Labor systems** (atributos organizacionales del empleado), y **herramientas de gestión de activos** (hardware, propiedad, ciclo de vida, garantía). Esta combinación de identidad + RRHH + activos es lo que permite la detección sofisticada de dispositivos huérfanos.

**Disponible desde templates v110**, sin prerrequisitos — puede instalarse de forma completamente independiente.

## Por qué importa en una conversación con el cliente

La distinción arquitectónica (End User Devices integrado vs. End User Insights independiente) es importante de explicar correctamente en discovery: un cliente puede adoptar End User Insights de inmediato para gobierno de activos, sin necesidad de tener el modelo de costo central de Costing Standard maduro — es una entrada de valor rápido y de bajo prerrequisito, distinta a otros módulos de infraestructura donde el orden de dependencias es más estricto.

El reporte Orphaned Devices, con sus cinco condiciones de detección, es un argumento de ahorro muy concreto: cada dispositivo huérfano identificado es potencialmente equipo pagado, licenciado, y bajo garantía, sin nadie usándolo — un hallazgo que casi siempre genera un caso de negocio inmediato en una demo o piloto.

El detalle de "usuario del último login distinto al dueño asignado" en el reporte de Compliance es un buen ejemplo para ilustrar cómo el producto no solo agrega datos sino que detecta inconsistencias de gobierno de datos como parte del análisis — vale la pena resaltarlo como un beneficio secundario de calidad de datos, no solo de costeo.

## Documentos fuente

- Summary (Solution Use Cases, sección completa) — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/sol-summ.md`
- End User Summary — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eu-summary.md`
- End User Devices Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eud-overview.md`
- End User Devices Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eud-gs.md`
- End User Insights Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-overview.md`
- End User Insights Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-reports.md`
  - Fleet Overview / End User Insights Reports (general): https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-end-user-devices-reports
- End User Insights Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/eui-gs.md`
  - Configuration steps: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-configure-end-user-devices
- CT Apps - End User Devices component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/enduserdevices.md`

*Nota: las dos URLs son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*