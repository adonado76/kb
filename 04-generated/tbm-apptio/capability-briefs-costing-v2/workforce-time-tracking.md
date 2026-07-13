---
concept: "Workforce & Time Tracking (composición de labor, headcount, costo de labor por rol/ubicación, asignación por tiempo reportado)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/tt-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/tt-getstar.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctftimetracking.md
last_updated: "2026-07-05"
---
# Workforce & Time Tracking — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El labor suele ser el mayor componente del gasto de TI, y también el más difícil de entender en detalle: cuánta gente hay, dónde están, si son internos o externos, cuánto cuestan realmente, y cómo ese costo se distribuye entre proyectos, aplicaciones y servicios. Sin esta capacidad, un CFO puede ver el número total de gasto en labor, pero no puede responder preguntas como "¿nos conviene contratar en Seattle o en Chicago?" o "¿cuánto de nuestro headcount es interno vs. externo?".

## Cómo lo resuelve Apptio Costing Standard

**Workforce da visibilidad de composición, no solo de costo total.** Cubre recursos internos, externos, contingentes y offshore, permitiendo analizar mezcla de labor (labor mix), utilización, movimiento de headcount y métricas financieras asociadas. Tres personas distintas la usan: IT Finance (presupuesto y forecast), Cost Center Owner/Manager (headcount y vacantes dentro de su área), y Service/Solution Owner (recursos de labor que soportan sus servicios).

**Cuatro casos de uso estándar, en una secuencia lógica documentada explícitamente por el producto:**
1. **Headcount Planning & Variance** — el punto de entrada principal: visibilidad de headcount aprobado vs. real, para gestionar riesgo de dotación y presupuesto.
2. **Labor Cost Analysis** — entender el costo total de labor y sus drivers, condición previa para cualquier asignación o benchmarking.
3. **Labor Mix Optimization** — una vez visible el headcount, optimizar la mezcla interno/externo/offshore/contingente.
4. **Labor Cost Allocation** — construir sobre la visibilidad de costo para dar trazabilidad hacia proyectos, aplicaciones, productos, servicios y plataformas.

Cuatro casos de uso adicionales requieren personalización: Workforce Planning, Capacity & Demand Forecast, Skills & Resource Allocation, y **Labor Rate Benchmarking** (comparar tarifas internas y de proveedor contra benchmarks de industria).

**Dos reportes centrales — Labor Review y Labor Analysis.** Labor Review da una vista ejecutiva de costo y headcount interno/externo, drivers de variación presupuestal, dirigida a liderazgo de TI, dueños de centro de costo/presupuesto y analistas financieros. Labor Analysis es una vista interactiva ad hoc con filtros dinámicos por centro de costo, rol, tipo de empleado y ubicación, dirigida a analistas financieros y de negocio.

**Labor Cost Take-Out (solo en NX): el reporte con el ejemplo numérico más concreto de toda la documentación revisada hasta ahora.** Compara tarifas de labor por rol, ubicación y proveedor, para identificar dónde ubicar o resourcear un rol a menor costo. El ejemplo documentado: un rol de QA en Seattle con el proveedor TDK puede optimizarse moviéndolo al proveedor PointB en la misma ciudad, ahorrando hasta $13,866. La mecánica es: **Potential cost take-out per headcount = Average Rate − Lowest Rate**, multiplicado por el número de headcount para obtener el ahorro total potencial. Este reporte responde directamente preguntas como "¿cuánto ahorramos contratando un Ingeniero en Seattle vs. Chicago?" o "¿qué proveedor nos da la mejor tarifa?".

**Dos componentes de asignación, mutuamente alternativos.** **CTF-Labor** habilita reporting de costo y headcount FTE/contrato por centro de costo, rol, proyecto y torre de TI. **CTF-Labor Units** permite asignar headcount a través de Proyectos, Aplicaciones y Productos en modelos operativos waterfall, ágil o híbrido, usando las métricas Internal Headcount, External Headcount y Labor Units. **Time Tracking** es la tercera alternativa: asigna costo de labor basado en tiempo reportado real (no en asunciones estáticas), pero el producto documenta explícitamente que normalmente **se usa Time Tracking o Labor Units, no ambos**, ya que combinarlos requiere personalización adicional del modelo.

**Prerrequisitos y datos maestros.** Time Tracking requiere que ya estén instalados CTF-Cost Source y CTF-Labor, y no introduce reportes propios — enriquece los reportes de labor y proyecto existentes con datos de tiempo real. Las fuentes típicas de datos de labor son sistemas de RRHH como SAP, Oracle E-Business Suite, PeopleSoft y Workday, mapeados a la taxonomía de Torres y Sub-Torres de ATUM.

## Por qué importa en una conversación con el cliente

El reporte Labor Cost Take-Out es un excelente gancho de valor cuantificable en una conversación de venta: convierte una intuición ("deberíamos optimizar dónde contratamos") en un número de ahorro concreto y defendible, calculado con una fórmula simple y transparente.

La decisión entre Labor Units y Time Tracking es una pregunta de discovery técnico obligatoria antes de proponer alcance: dependiendo del modelo operativo del cliente (si tiene reporte de tiempo granular real, o si prefiere una asignación basada en pesos/weighting factors), uno u otro es la elección correcta — y mezclarlos sin necesidad agrega complejidad de modelo evitable.

La secuencia de casos de uso estándar (Headcount → Costo → Mezcla → Asignación) es útil como guión de conversación de madurez: la mayoría de los clientes empiezan preguntando por headcount y terminan, con el tiempo, preguntando por asignación de costo a servicios — es un buen mapa de qué ofrecer primero y qué dejar para una segunda fase.

## Documentos fuente

- Workforce Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-overview.md`
- Workforce Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-reports.md`
  - Labor Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-labor-review
  - Labor Analysis: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-labor-analysis
- Workforce NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-reports-nx.md`
- Workforce Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/wf-getstart.md`
- Time Tracking Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/tt-overview.md`
- Time Tracking Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/tt-getstar.md`
- CTF - Time Tracking component: install and configure — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctftimetracking.md`

*Nota: las URLs de Labor Review y Labor Analysis son links reales embebidos en el contenido fuente original de IBM (verificados por venir directamente del documento). El resto queda pendiente de hipervínculo según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*