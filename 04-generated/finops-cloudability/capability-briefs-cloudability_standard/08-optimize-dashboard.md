---
tbm_concept: "Optimize — Optimization Dashboard (centro de comando de oportunidades de ahorro, con el score COIN como métrica de contextualización)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-optimization-dashboard.md
last_updated: "2026-07-09"
---
# Optimize — Optimization Dashboard — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Con Rightsizing y Commitment Management (documentados en los siguientes capítulos) generando cada uno su propio flujo de recomendaciones, se necesita un punto de entrada único que las consolide — una vista tanto prospectiva (qué oportunidades existen) como retrospectiva (qué se ha ahorrado ya). El Optimization Dashboard es ese centro de comando.

## Cómo lo resuelve IBM Cloudability Standard

**Dos direcciones de vista en un solo dashboard**: hacia adelante (oportunidades de ahorro disponibles vía Commitments y Rightsizing) y hacia atrás (impacto ya logrado por esas mismas iniciativas).

**La página de Opportunities combina dos motores de recomendación**: Resource Optimization (basado en las recomendaciones de Rightsizing) y Commitments (basado en las recomendaciones de compromiso de Cloudability) — resumidas en un solo lugar con enlaces directos a cada detalle.

**COIN Score (Cost Optimization Index Number) — la métrica propia de Cloudability para contextualizar una oportunidad, con fórmula documentada explícitamente:**

`COIN = 100 × (1 − (Optimization Opportunity / Spend))`

Un COIN de 100 implica gasto sin ninguna oportunidad de ahorro disponible. **Optimization Opportunity** es la suma de ahorros de rightsizing disponibles según las preferencias, vista y filtros aplicados. **Spend** es el gasto relevante y optimizable, medido según la preferencia de base de costo seleccionada: con base **On Demand**, usa Cost (List); con base **Effective**, usa Cost (Adjusted Amortized) o, si no está disponible, Cost (Amortized). El COIN está limitado a los servicios soportados por el motor de rightsizing de Cloudability — gasto en servicios no soportados queda fuera del cálculo.

**Preferencias configurables a nivel de organización, con impacto directo en qué se muestra**: **Effective vs. On Demand Cost Basis** (determina tanto qué recomendaciones se muestran como qué métrica alimenta el cálculo de COIN), y **Advanced vs. Basic Recommendations** — esta última **exclusiva de clientes Cloudability Premium**, permitiendo elegir si el dashboard se puebla con las recomendaciones propias del motor de Rightsizing de Cloudability ("Basic") o con las del motor de Turbonomic ("Advanced", refinable vía políticas en lugar de preferencias de dashboard).

## Por qué importa en una conversación con el cliente

El COIN Score es un activo de comunicación ejecutiva de alto valor — reduce una oportunidad de ahorro compleja (múltiples recursos, múltiples servicios) a un solo número normalizado de 0 a 100, fácil de trackear en el tiempo y de presentar a liderazgo sin necesidad de explicar la mecánica de rightsizing subyacente.

La distinción Advanced (Turbonomic) vs. Basic recommendations, exclusiva de Premium, es un dato de licenciamiento importante — vale la pena confirmar la edición real del cliente antes de prometer acceso al motor de recomendaciones de Turbonomic dentro de este dashboard específico.

La dependencia del cálculo de COIN respecto a la base de costo seleccionada (On Demand vs. Effective) es un detalle técnico que vale la pena alinear explícitamente con el equipo de Finanzas del cliente — dos organizaciones con el mismo gasto real pueden ver un COIN distinto simplemente por esta preferencia de configuración.

## Documentos fuente

- Optimization Dashboard — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-optimization-dashboard.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
