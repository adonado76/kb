---
tbm_concept: "Service Desk (costo por ticket, MTTR, dos niveles de madurez analítica)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/servicedesk.md
last_updated: "2026-07-05"
---
# Service Desk — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El service desk ha evolucionado de simplemente resolver tickets a habilitar valor de negocio sostenido — pero muchas organizaciones tienen visibilidad limitada de la demanda de servicio, taxonomías fragmentadas, y no pueden conectar claramente el costo del soporte con el resultado de negocio. Sin una vista unificada de demanda, drivers de costo y métricas de desempeño, es difícil priorizar mejoras o controlar el costo del service desk de forma informada.

## Cómo lo resuelve Apptio Costing Standard

### El mismo patrón de dos soluciones, aplicado ahora a soporte de TI

**Service Desk Cost Overview (CT Apps – Service Desk)** — vista fundacional para equipos que buscan visibilidad rápida de gasto en tickets, costo por ticket, y desglose básico por categoría, prioridad, severidad y servicio, sin complejidad operativa profunda.

**Service Desk Insights & Optimization (BI – Service Desk Insights)** — analítica operativa más profunda, con drill-down por costo, volumen, prioridad, severidad, ubicación y servicio, ayudando a IT Operations a identificar servicios de alto costo y patrones de demanda.

### Tres casos de uso estándar

Service Desk Cost Transparency (costo total y su distribución por tipo/categoría/servicio de ticket), Ticket Volume and Cost Analysis (por severidad, prioridad, categoría, ubicación y servicio), y Service Performance and Efficiency (MTTR — mean time to resolve —, costo por ticket, tendencias de ticket).

### Reportes: de resumen general a detalle por recurso y por aplicación

La versión Cost Overview aporta un análisis (parte del reporte más amplio "Infrastructure Review") que conecta costo, volumen y severidad de tickets.

La colección Insights & Optimization (disponible en el endpoint separado "Infrastructure Insights") tiene cuatro reportes: **Service Desk Summary** (costo total y volumen de tickets, con KPIs de costo por ticket y MTTR), **Service Desk Task Details** (desglose por tipo de tarea — requests, incidentes, problemas, cambios —, identificando tipos con costo por ticket alto o tiempos de resolución prolongados), **Service Desk Resource Details** (costo y productividad por recurso, equipo o ubicación de soporte, para decisiones de staffing y sourcing), y **Service Desk By Application** (conecta costo y volumen de tickets directamente a las aplicaciones que soportan, identificando qué aplicaciones generan mayor demanda de soporte).

**Un componente fundacional con una lista de campos particularmente orientada a operación de tickets.** CT Apps-Service Desk crea el grupo "Service Desk" con la tabla Tickets y su master data. Los campos requeridos incluyen no solo atributos financieros sino operativos específicos de gestión de tickets: Category, Close Time, Open Time, Priority, **Priority Weight**, Status, Ticket ID, Type, y **Weighting** — este último campo de ponderación es explícitamente requerido, sugiriendo que la asignación de costo a tickets no es uniforme sino ponderada por algún factor de complejidad o impacto (similar en espíritu a la fórmula de weighting vista en Mainframe).

**Prerrequisitos**: CTF-Cost Source, CTF-Labor, y CTF-IT Towers para el nivel Cost Overview; el nivel Insights & Optimization además requiere que CT Apps-Service Desk esté instalado.

**Fuentes de datos**: el libro mayor para costo y presupuesto, combinado con plataformas ITSM y herramientas de soporte para volumen de tickets, severidad, prioridad y esfuerzo de resolución.

## Por qué importa en una conversación con el cliente

El reporte Service Desk By Application es un puente natural hacia conversaciones de racionalización de portafolio de aplicaciones: mostrarle a un dueño de aplicación cuánto cuesta el soporte que genera su sistema es un dato que rara vez se conecta explícitamente en procesos tradicionales de gestión de TI, y suele ser una revelación útil en conversaciones de modernización.

El campo "Weighting" requerido en los datos de tickets es un buen punto para profundizar en discovery técnico: preguntar cómo el cliente actualmente pondera la complejidad o el esfuerzo de un ticket (si lo hace) ayuda a calibrar qué tan preciso será el costeo por ticket desde el primer día.

El patrón de dos niveles, otra vez consistente con Compute, Storage y (ahora) Service Desk, refuerza un argumento de venta que ya puede repetirse en múltiples conversaciones: la arquitectura del producto está diseñada deliberadamente para permitir adopción incremental, módulo por módulo, sin necesidad de comprometerse con la analítica más avanzada desde el primer día.

## Documentos fuente

- Service Desk Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-overview.md`
- Service Desk Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-reports.md`
- Service Desk Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/sd-gs.md`
- CT Apps - Service Desk component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/servicedesk.md`

*Nota: no se encontraron links públicos de ibm.com/docs embebidos en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*