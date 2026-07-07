---
tbm_concept: "Applications (TCO de aplicación, portafolio, análisis de infraestructura subyacente, ciclo de vida)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/apps.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/appsservicesmod.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutappsservicesmod.md
last_updated: "2026-07-05"
---
# Applications — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Contexto arquitectónico: el "Applications and Services Module"

Este brief revela la arquitectura completa de un módulo que atraviesa varias categorías ya documentadas. El **Applications and Services Module** agrupa diez componentes — CT Apps-Applications, Communications, Data Centers, End User Devices, Mainframes, Network Devices, Servers, Services, Service Desk, y Storage — con tres reglas de arquitectura importantes:

1. **No se instalan automáticamente** al crear un proyecto de Costing Standard; cada uno se instala por separado.
2. **No dependen entre sí** — se puede instalar cualquier combinación, en cualquier orden.
3. Todos requieren que el **Costing Standard Foundation (CTF) Module** esté ya instalado y validado.
4. El módulo completo de Applications and Services es, a su vez, **prerrequisito del módulo de Business Units** — estableciendo la cadena completa: CTF Foundation → Applications and Services → Business Units.

A diferencia del **Costing Standard Foundation Module** (más estandarizado), el documento advierte explícitamente que el **Applications and Services Module suele personalizarse** para ajustarse a los datos disponibles de cada organización — la forma de configurarlo documentada aquí es "una manera de hacerlo", no la única.

## El concepto

Las estrategias de TI puramente reactivas, enfocadas solo en recortar costo, han demostrado ser inefectivas frente a la necesidad de optimizar valor e innovar continuamente. Sin disciplina de portafolio de aplicaciones, la deuda técnica crece, las aplicaciones redundantes se acumulan, y la dependencia de hojas de cálculo fragmenta los datos — haciendo casi imposible entender el costo real de una aplicación, priorizar inversión, o racionalizar sistemas legados con confianza.

## Cómo lo resuelve Apptio Costing Standard

**Cuatro casos de uso estándar, cuatro personalizados.** Estándar: Application TCO/Unit Costs/Usage (costo total combinando labor, software, infraestructura, plataformas), Cost Drivers and Savings Identification, TCO Showback, y Usage and Utilization (costo por usuario). Personalizados: Budget and Forecast by Application, Demand and Capacity Planning, **Application Lifecycle Management** (evaluar costo por etapa de ciclo de vida para decisiones de invertir/tolerar/migrar/retirar), y Technology Stack Consolidation.

**A diferencia de Servers, Storage y otros componentes fundacionales "silenciosos", CT Apps-Applications sí trae reportes propios.** El documento lo aclara explícitamente: "The Applications component provides new reports and also creates metrics that are exposed in the Application Insights Component" — es decir, Applications rompe el patrón de componente puramente fundacional visto en Compute/Storage/Data Centers.

**Cinco reportes en la colección estándar, más un reporte de modelo:**
- **Application Review** — vista ejecutiva de gasto de las aplicaciones principales, por familia de aplicación, con costo por usuario e inversión en cambios/mejoras.
- **Application Portfolio** — expande la vista a todo el portafolio: quién es responsable de qué, gasto por unidad de negocio, drivers de costo por torre TI y proveedor, e impacto de proyectos relacionados.
- **Application List** — detalle analítico por aplicación individual, incluyendo proveedores SaaS asociados y gasto Run vs. Development.
- **Infrastructure Analysis by Application** — porcentaje de uso de aplicación por torre TI (Compute, Storage, Service Desk), incluyendo qué proporción corre en nube pública vs. on-premise — un puente directo hacia los módulos de Compute y Public Cloud ya documentados.
- **New & Retired Apps** — aplicaciones activas vs. retiradas en los últimos 12 meses, con dueños de negocio y TI responsables.
- **Application Model** (reporte de trazabilidad, no de negocio) — muestra cómo el dato de costo se mueve a través del modelo (Allocation Models, estructura Tower/Sub-Tower, Cost Pools), usado para validar y depurar transformaciones de datos.

**Un campo requerido que conecta directamente con la conversación de portafolio: Application Investment Objective.** Junto con Application Family, Application ID y Application Name, este campo (requerido, no solo recomendado) sugiere que el producto espera que cada aplicación tenga clasificado su objetivo de inversión desde el momento de carga de datos — no como un ejercicio posterior.

**El flujo de asignación conecta cuatro fuentes distintas hacia Applications**: IT Resource Towers, Servers, Tickets (de Service Desk), y Projects — confirmando en código lo que ya habíamos inferido narrativamente: Applications es un punto de consolidación que recibe costo desde infraestructura, soporte, y proyectos simultáneamente.

**Prerrequisitos mínimos** (CTF-Cost Source, CTF-IT Towers) pero con una nota clave: aunque los prerrequisitos formales son mínimos, la **calidad real de los reportes de Applications depende de cuántos otros componentes de Applications and Services ya estén instalados** — sin Servers, Storage, Service Desk o Projects mapeados, el reporte "Infrastructure Analysis by Application" tendrá huecos.

## Por qué importa en una conversación con el cliente

La regla "los componentes no dependen entre sí, se pueden instalar en cualquier orden" es una excelente respuesta a la objeción común de "esto parece un proyecto enorme, todo o nada" — un cliente puede empezar con Applications y Servers, y agregar Storage o Service Desk más adelante, sin necesidad de re-arquitectura.

El puente Applications and Services Module → Business Units Module es información de secuenciación de venta valiosa: si un cliente quiere reporte de gasto de TI por unidad de negocio (que veremos en SU-05), primero necesita este módulo funcionando — vale la pena posicionar esa dependencia en cualquier conversación donde Business Units sea el objetivo final.

El reporte Infrastructure Analysis by Application es el mejor punto de síntesis narrativa de todo lo cubierto hasta ahora en Infrastructure Use Cases: permite mostrarle a un dueño de aplicación, en una sola vista, cuánto de su costo viene de Compute, cuánto de Storage, cuánto de tickets de soporte, y qué porción corre en nube pública — la culminación natural de haber costeado cada torre de infraestructura por separado.

## Documentos fuente

- Applications Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-overview.md`
- Applications Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports.md`
  - Application Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-application-review
  - Application Portfolio: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-application-portfolio
  - Application List: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-application-list
  - Infrastructure Analysis by Application: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-infrastructure-analysis-by-application
  - New & Retired Applications: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-new-retired-apps
- Applications NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-reports-nx.md`
- Applications Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/app-gs.md`
- CT Apps - Applications component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/apps.md`
- Applications and Services Module configuration (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/appsservicesmod.md`
- About the Applications and Services Module configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutappsservicesmod.md`

*Nota: las cinco URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*