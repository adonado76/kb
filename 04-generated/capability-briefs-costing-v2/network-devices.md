---
tbm_concept: "Network Devices (costo de LAN/WAN/Voz, asignación a consumidores de infraestructura)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/nd-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/nd-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/networkdevices.md
last_updated: "2026-07-05"
---
# Network Devices — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El costo de red — LAN, WAN, voz, equipo de conectividad — es notoriamente difícil de predecir y controlar: incrementos inesperados surgen de downtime, ancho de banda o software sobre-especificado, enlaces subutilizados, y poca visibilidad del ciclo de vida de los activos de red. A esto se suma un problema de asignación: a medida que sitios se abren, se contraen o se cierran, es difícil asignar el gasto de comunicaciones a las unidades de negocio de forma defendible y consistente.

## Cómo lo resuelve Apptio Costing Standard

**Un solo caso de uso estándar, pero central: Network Utilization and Efficiency.** Monitorea líneas de red, contratos y utilización para optimizar el costo de comunicaciones manteniendo niveles de servicio confiables y minimizando downtime y pérdida de productividad.

**Este módulo no es un fin en sí mismo — es una capa de asignación hacia otros módulos de infraestructura.** A diferencia de Compute o Storage (que tienen colecciones de reportes propias y ricas), Network Devices no tiene su propia colección de reportes documentada. Su propósito es distribuir el costo de equipo de red hacia **cuatro consumidores típicos**: Mainframe (equipo de red que soporta mainframes en data centers), Physical Servers (equipo que soporta infraestructura de servidores), Storage Devices (equipo que soporta plataformas de almacenamiento), y End User Devices (conectividad alámbrica e inalámbrica para PCs, laptops y móviles en oficinas).

**Un componente que instala un solo objeto con dos tablas.** CT Apps-Network Devices crea el grupo "Network Devices" con una tabla modelo y su master data. Los campos requeridos son: Device Count, Device Type, Location Type, Network Devices_Storage Devices, y Object Identifier — con Location, Service ID y Service Name como recomendados.

**El flujo de asignación es explícito y bidireccional en el modelo de costo.** Una vez mapeados los datos, el valor debe fluir **desde** IT Resource Towers y Data Centers **hacia** Network Devices, y **desde** Network Devices **hacia** Physical Server, Storage Devices, End User Devices y Mainframes. Es decir, Network Devices actúa como un nodo intermedio de asignación en la cadena de costo — recibe costo de sus fuentes (torres y data centers) y lo redistribuye hacia los consumidores finales.

**Prerrequisitos**: CTF-Cost Source y CTF-IT Towers.

**Fuentes de datos típicas**: el libro mayor para costo y presupuesto, combinado con herramientas de gestión y monitoreo de red (SolarWinds, Cisco DNA Center, herramientas basadas en SNMP), plataformas CMDB, y sistemas de gestión de activos.

## Por qué importa en una conversación con el cliente

Este módulo es un buen ejemplo para explicar el concepto de "costos compartidos que se redistribuyen" en la práctica TBM: la mayoría de los clientes entiende intuitivamente el costo directo de un servidor o de almacenamiento, pero les cuesta más ver que el costo de la red que conecta todo eso también debe asignarse, y no quedarse "flotando" como un costo genérico de infraestructura sin trazabilidad hacia lo que realmente consume esa red.

Vale la pena posicionar este módulo explícitamente como un prerrequisito de calidad para los reportes de TCO de Compute, Storage, Mainframe y End User Devices — sin Network Devices correctamente mapeado, el TCO de esos otros módulos estará subestimado, porque les faltará su porción de costo de conectividad.

## Documentos fuente

- Network Devices Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/nd-overview.md`
- Network Devices Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/nd-gs.md`
- CT Apps - Network Devices component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/networkdevices.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos a la documentación oficial de IBM pendientes (no se encontraron links embebidos en esta categoría).*