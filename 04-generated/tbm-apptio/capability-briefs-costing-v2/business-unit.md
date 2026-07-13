---
concept: "Business Unit (consolidación de costo por unidad de negocio, asignación directa vs. indirecta)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/busunitsmod.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/buallocate.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/buinstall.md
last_updated: "2026-07-05"
---
# Business Unit — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El punto de convergencia de todo el modelo

Business Units es, arquitectónicamente, la cima de la cadena de asignación de Costing Standard: consolida costos de Applications, Services y Projects en una sola vista por unidad de negocio. El propio documento de instalación lo advierte explícitamente: **"The Applications and Services Module must be installed and configured before you can install the Business Units component."** Esto confirma y cierra la cadena de dependencias que hemos visto construirse a lo largo de todo Solution Use Cases: CTF Foundation → Applications and Services (Compute, Storage, Applications, Services, etc.) → Business Units → (y de ahí, según vimos en el brief anterior) → Products.

## El concepto

El negocio no organiza su presupuesto por torre de infraestructura ni por aplicación individual — lo organiza por unidad de negocio. Sin una capa de consolidación a ese nivel, cada Business Unit Leader tiene que reconstruir manualmente, cruzando reportes de aplicaciones y servicios, cuánto le cuesta realmente la tecnología que consume — un ejercicio propenso a error y a disputas sobre qué se incluyó o se dejó fuera.

## Cómo lo resuelve Apptio Costing Standard

**Tres casos de uso estándar, uno personalizado**: TCO Showback (vista comprehensiva de servicios consumidos — costos, volúmenes, usuarios, costo unitario), Flexible Allocation Methods and Outcomes (métodos de asignación directa e indirecta para mejorar precisión y confianza), y Drill and Trace of Costs (cómo el costo fluye de infraestructura → aplicaciones → servicios). El caso personalizado, Classify Consumption, rastrea costo y uso por capacidad o proceso de negocio.

**El mecanismo central: separación explícita entre asignación Directa e Indirecta, calculada con cuatro objetos en la cima del modelo.** Esta es la pieza conceptual más importante del módulo:
- **Costos Directos** — basados en consumo real, asignables a un objeto de costo específico (producto, servicio, departamento, proyecto). Labor, software y equipo son ejemplos típicos; representan la mayor porción del gasto controlable.
- **Costos Indirectos** — costos compartidos o de overhead necesarios para operar la organización (instalaciones, utilities, equipo de usuario final, infraestructura general), distribuidos usando ratios definidos como headcount total o headcount departamental.

El modelo calcula esto usando cuatro objetos: **Business Services**, **Service Allocations Direct**, **Service Allocations Indirect**, y **Business Unit Allocation**. El costo de Business Services fluye hacia Service Allocations Direct según un campo explícito de mapeo (`Service_Service Allocations Direct`, presente tanto en el dataset de Business Services como en el de Service Allocations Direct), y hacia Service Allocations Indirect según otro campo específico (`Check for SAD`) — ambos campos viven en la misma tabla **All Business Services** que ya vimos en Services y Products, confirmando que los tres módulos (Services, Products, Business Units) comparten la misma columna vertebral de datos.

**Cinco reportes**, con uno particularmente orientado a la conversación de racionalización de portafolio:
- **Business Unit Review** — gasto, staffing e inversión por unidad de negocio, comparando unidades generadoras de ingreso vs. no generadoras, costo por empleado, y desglose directo vs. indirecto.
- **Business Unit Portfolio** — Run vs. Change (Investment) por unidad de negocio, con aplicaciones y servicios que impulsan ese gasto.
- **Business Unit List** — vista consolidada de todas las unidades: OpEx/CapEx, gasto por tipo de servicio, inversión directa/indirecta/de proyecto.
- **Impact of Retiring Applications** — el reporte más orientado a caso de negocio de toda la colección: cuantifica el **ahorro anual potencial** de retirar o migrar aplicaciones específicas, y qué unidades de negocio cargan el mayor costo de esas aplicaciones candidatas a retiro.
- **Business Unit Model** — trazabilidad estándar de flujo de costo.

**Flujo de asignación completo, documentado paso a paso**: Business Services → Service Allocations Direct (por consumo) y Service Allocations Indirect (por headcount); ambos → Business Unit Allocation; adicionalmente, Projects → Business Unit Allocation de forma directa (los costos de proyecto se asignan directamente a la unidad de negocio asociada, sin pasar por la capa de servicios).

**Dos tablas maestras principales**: Business Unit Allocation Master Data (jerarquía organizacional, datos de headcount para ratios, propiedad de unidad de negocio) y Service Allocations Direct Master Data (relación de consumo directo entre servicios de negocio y unidades de negocio).

**Prerrequisitos**: CTF-Cost Source, CTF-IT Resource Towers, CT Apps-Applications, y CT Apps-Services — confirmando otra vez la cadena de dependencia real dentro de un módulo que en teoría "no depende entre sí" component por componente, pero que en la práctica de Solution Use Cases sí tiene una secuencia lógica obligatoria.

## Por qué importa en una conversación con el cliente

El reporte "Impact of Retiring Applications" es probablemente el mejor gancho de ROI cuantificable de toda la base de conocimiento de Costing Standard hasta ahora: traduce una decisión de racionalización de portafolio directamente a un número de ahorro anual y a quién (qué unidad de negocio) se beneficia — el tipo de cifra que justifica un proyecto de modernización ante un comité de inversión.

La distinción Directo vs. Indirecto es un concepto que vale la pena enseñar explícitamente a un Business Unit Leader escéptico sobre por qué su costo de TI "parece alto": buena parte de ese costo probablemente es overhead compartido asignado por headcount, no consumo directo de su unidad — explicar esta separación con transparencia suele desactivar objeciones sobre "por qué me cobran tanto".

Dado que Business Units cierra la cadena de dependencia de todo el módulo Applications and Services, es también el argumento de venta más fuerte para justificar la inversión completa en los módulos de infraestructura anteriores (Compute, Storage, Data Centers, etc.): sin ellos costeados y fluyendo correctamente hacia Applications y Services, la vista final de Business Unit estará incompleta o será menos defendible.

## Documentos fuente

- Business Unit Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-overview.md`
- Business Unit Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-reports.md`
  - Business Unit Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-business-unit-review
  - Business Unit Portfolio: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-business-unit-portfolio
  - Business Unit List: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-business-unit-list
  - Impact of Retiring Applications: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-impact-retiring-applications
- Business Unit Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/solution-uc/bu-gs.md`
- Business Units Module configuration (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/busunitsmod.md`
- Direct vs indirect allocations — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/buallocate.md`
- Install and configure the CT - Business Units component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/buinstall.md`

*Nota: las cuatro URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*