---
tbm_concept: "Communications (asignación de costo de circuitos, voz y cargos de uso hacia consumidores)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/comm-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/comm-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/comms.md
last_updated: "2026-07-05"
---
# Communications — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Los costos de comunicaciones — circuitos, servicios de voz, cargos basados en uso — suelen ser invisibles a través de data centers, oficinas y servicios de negocio, lo cual dificulta controlar el gasto, asignarlo de forma justa, y entender el verdadero costo de las aplicaciones y servicios que dependen de esa conectividad.

## Cómo lo resuelve Apptio Costing Standard

**Un solo caso de uso, con el mismo patrón de "nodo intermedio de asignación" visto en Network Devices: Communication Cost Allocation.** Asigna el costo de infraestructura de comunicaciones a servidores, dispositivos de usuario final, y servicios de negocio, para establecer TCO defendible de aplicaciones y servicios.

**Sin colección de reportes propia — es, otra vez, una capa de asignación, no un destino final de análisis.** Al igual que Network Devices, Communications no tiene reportes documentados propios; su función es capturar el costo de circuitos y servicios de voz y redistribuirlo hacia los consumidores reales de esa conectividad.

**Tres consumidores típicos**, aunque documentados de forma menos exhaustiva que en Network Devices: servidores que soportan data centers, dispositivos de usuario final que soportan conectividad de oficina, y servicios de negocio específicos como centros de llamadas o kioscos de retail (estos últimos mencionados como ejemplo en el Getting Started, aunque no aparecen como categoría separada en el flujo de asignación documentado).

**Un componente con una tabla y campos mayormente recomendados, no requeridos.** CT Apps-Communications crea el grupo "Communications" con su tabla modelo y master data. A diferencia de Service Desk o Data Centers (donde la mayoría de los campos eran requeridos), aquí solo **Amount, Location Type, Object Identifier y Type** son requeridos — Account, Circuit ID, Location, Offering, Product y Service Provider son recomendados. Esto sugiere un umbral de entrada de datos más bajo que otros módulos de infraestructura.

**El flujo de asignación es simple y de dos pasos**: de IT Resource Towers hacia Communications, y de Communications hacia Servers y Business Services.

**Prerrequisitos**: CTF-Cost Source y CTF-IT Towers — los mismos dos prerrequisitos mínimos vistos en Network Devices.

**Fuentes de datos típicas**: el libro mayor y sistemas de gasto de telecomunicaciones/red.

## Por qué importa en una conversación con el cliente

Communications y Network Devices son, en efecto, un par de módulos hermanos con el mismo propósito arquitectónico (capas de asignación de costo de conectividad hacia consumidores de infraestructura), y vale la pena presentarlos juntos en una conversación de discovery en lugar de tratarlos como dos temas separados — la pregunta relevante para el cliente es la misma en ambos casos: "¿tenemos visibilidad de qué consume nuestra conectividad de red y voz, y podemos asignarla de forma defendible?"

El umbral de datos requeridos más bajo (solo 4 campos obligatorios) hace de este un módulo relativamente rápido de activar comparado con otros de infraestructura — vale la pena mencionarlo si el cliente está priorizando quick wins de visibilidad antes de abordar módulos más exigentes en datos como Mainframe o Data Centers.

## Documentos fuente

- Communications Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/comm-overview.md`
- Communications Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/comm-gs.md`
- CT Apps - Communications component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/comms.md`

*Nota: no se encontraron links públicos de ibm.com/docs embebidos en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*