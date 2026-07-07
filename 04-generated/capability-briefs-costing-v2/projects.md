---
tbm_concept: "Projects (inversión de TI, alineación Run/Grow/Transform, riesgo de portafolio)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-projects-component.md
last_updated: "2026-07-05"
---
# Projects — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Un presupuesto de proyecto aprobado no garantiza que el gasto real se mantenga alineado con él, ni que el proyecto siga contribuyendo al objetivo estratégico para el que fue aprobado. Sin visibilidad financiera consolidada del portafolio de proyectos, una organización descubre las desviaciones de presupuesto tarde, y no tiene manera sistemática de responder si su inversión total está balanceada entre mantener lo existente, hacer crecer el negocio, o transformarlo.

## Cómo lo resuelve Apptio Costing Standard

**Cuatro casos de uso estándar**, con un quinto marcado explícitamente como personalizado:
- **Project Spend Alignment** — mapear inversiones de proyecto a ofertas de solución (aplicaciones, servicios, productos, plataformas) y clasificaciones de valor de negocio.
- **Project Spend Variance Analysis** — comparar gasto real contra presupuesto aprobado para identificar sobrecostos temprano.
- **Run–Change o Run–Grow–Transform Classification** — clasificar el gasto de proyecto para entender el balance entre iniciativas operativas, de crecimiento y transformacionales — un marco de clasificación estratégica estándar en la práctica TBM.
- **Project Cost Allocation** — asignar costos de proyecto (incluyendo labor y gasto de vendor) a las ofertas de solución o unidades de negocio correspondientes.
- *(Personalizado)* **Investment ROI for Projects** — evaluar inversiones contra beneficios proyectados, incluyendo validación de resultados post-despliegue.

**Cuatro reportes que cubren desde el detalle individual hasta el riesgo de portafolio:**
- **Project Review** — spend, presupuesto y estado de entrega de los proyectos principales, con KPIs comparando gasto de proyecto contra gasto total de TI, y análisis por iniciativa de negocio, portafolio, gerente de proyecto y patrocinador.
- **Project Portfolio** — vista a nivel de portafolio: composición, consumo, fase de ciclo de vida y estado de finalización a través de iniciativas.
- **Project List** — inventario completo de proyectos con su estado actual, mezcla OpEx/CapEx, y drill-down a KPIs, drivers, proveedores, labor y aplicaciones impactadas por proyecto individual.
- **Projects at Risk** — identifica proyectos en riesgo según estado y tendencia de gasto, y cuantifica la exposición financiera asociada a esos proyectos — el reporte más orientado a acción correctiva inmediata de los cuatro.

**Un componente con tres prerrequisitos, dos de ellos alternativos entre sí.** CTF-Projects requiere CTF-Cost Source y CTF-Labor obligatoriamente, más **CTF-Labor Units o CTF-Time Tracking** (no ambos, según ya vimos en el brief de Workforce) — reforzando que la decisión Labor Units vs. Time Tracking tomada en ese módulo tiene efecto directo aquí también.

**Una lista de campos notablemente orientada a valor de negocio, no solo a finanzas.** A diferencia de Fixed Assets (campos casi todos técnicos/contables), la lista de campos de Projects incluye explícitamente métricas de **valor de negocio**: Value - Gross Expense Reduction, Value - Gross Revenue Increase, Value - OpEx Reduction, Value - Working Capital Reduction — además de los campos esperables (Approved Budget, Business Initiative, Business Sponsor, Project Lifecycle, Status - Budget/Overall/Scope/Timeline). Solo tres campos son estrictamente requeridos (Expense Type, Project ID, Project Name, Spend Type, Status - Overall); el resto son recomendados, lo cual da flexibilidad de implementación por fases.

**Fuentes de datos típicas** son herramientas de gestión de portafolio de proyectos: ServiceNow, Project Portfolio Suite, Clarity PPM, Jira Align/Advanced Roadmaps, MS Project Online/Server, Planview. Existe además una tabla específica de **Project to Application Mapping**, que conecta inversiones de proyecto con las aplicaciones que impactan — clave para entender cómo un proyecto contribuye al costo, cambio o modernización de una aplicación específica.

## Por qué importa en una conversación con el cliente

Los campos de "valor de negocio" (reducción de gasto, incremento de ingreso, reducción de OpEx, reducción de capital de trabajo) son un diferenciador importante frente a herramientas de PPM tradicionales que solo rastrean cronograma y presupuesto — este módulo conecta explícitamente la inversión de proyecto con el resultado de negocio esperado, lo cual es exactamente el tipo de conversación que un CFO quiere tener sobre el portafolio de TI.

El marco Run-Grow-Transform es un excelente punto de entrada para una conversación estratégica con un CIO: preguntar "¿qué porcentaje de su portafolio actual es Run vs. Grow vs. Transform?" suele revelar de inmediato si la organización está invirtiendo demasiado en mantener lo existente y muy poco en crecimiento — una conversación de valor mucho más rica que simplemente reportar gasto total de proyectos.

La conexión Project-to-Application es un puente natural hacia el módulo de Applications (que veremos en Solution Use Cases): permite mostrar en una sola narrativa cómo la inversión de un proyecto se traduce en el costo — y eventualmente en el valor — de una aplicación específica a lo largo de su ciclo de vida.

## Documentos fuente

- Projects Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-overview.md`
- Projects Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-reports.md`
  - Project Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-projects-review
  - Project Portfolio: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-project-portfolio
  - Project List: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-projects-list
  - Projects at Risk: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-projects-risk
- Projects Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/project-getstart.md`
- CTF - Projects component: install and configure — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-projects-component.md`

*Nota: las cuatro URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*