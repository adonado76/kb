---
tbm_concept: "Data Reference (catálogo de dimensiones y métricas de costo/utilización, las seis variantes de métrica de costo, y diferencias entre la interfaz de reporte y las exportaciones CSV)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/reference-glossary-utilization-dimensions-metrics.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reference-glossary-cost-dimensions-metrics.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reference-making-most-popular-dimensions-metrics-within-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reference-comparing-data-between-report-ui-csv-exports.md
last_updated: "2026-07-09"
---
# Data Reference — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Con docenas de dimensiones y **seis variantes distintas de métrica de costo**, el riesgo real de Cloudability no es la falta de datos, sino elegir la combinación equivocada de dimensión/métrica para una pregunta de negocio específica — generando un número técnicamente correcto, pero conceptualmente engañoso. Este capítulo es el catálogo de referencia y la guía de uso correcto.

## Cómo lo resuelve IBM Cloudability Standard

**Las seis variantes de métrica de costo — la pieza más importante de todo este catálogo, con implicaciones de negocio distintas cada una:**

| Métrica | Qué representa | Cuándo usarla |
|---|---|---|
| **Cost (List)** | Tarifa pública on-demand, sin ningún descuento | Comparación predecible, sin efecto de negociación |
| **Cost (Total)** | La métrica de costo por defecto — el monto facturado real ("cash") | Reporte financiero estándar |
| **Cost (Total Blended)** | Específica de AWS, "difumina" el efecto de RIs/Savings Plans | No recomendada — puede dar cifras inesperadas; usar Total o Amortized |
| **Cost (Amortized)** | Métrica de "devengo": distribuye compromisos (incluyendo upfront) al período/lugar de consumo real | Chargeback/showback correcto cuando hay compromisos activos |
| **Cost (Adjusted)** | Cost (Total) ajustado por reglas de precio personalizado (Custom Pricing) | Clientes con descuentos empresariales negociados |
| **Cost (Adjusted Amortized)** | Cost (Amortized) ajustado por Custom Pricing | La combinación más precisa para clientes con ambos: compromisos y precio negociado |

**Un detalle técnico documentado explícitamente sobre RIs y AWS**: donde AWS no asigna la porción "usada" de una RI a los recursos específicos en `UnblendedCost`, **Cloudability sí la asigna** a los recursos que se beneficiaron de la RI (en vez de cargarla a la cuenta donde se compró) — una mejora de transparencia que habilita showback/chargeback más preciso que la factura cruda del proveedor.

**Dimensiones de costo, organizadas en tres familias de granularidad progresiva** (documentadas explícitamente como guía de "cómo sacarles más provecho"):
- **Service Name** (estandarizada, recomendada para reportes guardados) vs. Product Name (cruda del proveedor, inconsistente entre AWS/Azure/GCP).
- **Usage Family** (categoría de alto nivel: Instance Usage, Data Transfer, Storage, API Request) vs. Usage Type (grano fino, útil con filtros contains/does not contain).
- **Item Description** — el nivel más granular, con ejemplos reales de patrones de filtro (excluir cargos de "sign up" de una compra de RI usando `does not contain sign up`).

**Transaction Type y Compute Usage Type** — dimensiones creadas específicamente por Cloudability (no nativas del proveedor) para separar cargos recurrentes, cargos únicos, créditos, impuestos y uso — con ejemplos de filtro documentados para aislar Redshift, ElastiCache, RDS, y costo On-Demand específicamente.

**Glosario de dimensiones y métricas de utilización** (separado del glosario de costo) — cubre atributos de infraestructura (Availability Zone, Architecture, Instance Type) y métricas de desempeño real (CPU/memoria/red/disco), incluyendo métricas específicas de Auto Scaling Groups (CPU Total, Memory Total, líneas recomendadas vs. reales) usadas en el módulo de Rightsizing.

**Métricas de sostenibilidad** — Estimated Carbon Emissions, Power Consumed, y su desglose en **Operational** (emisiones de la operación diaria del centro de datos) vs. **Embodied** (emisiones de la fabricación y ciclo de vida del hardware físico, prorrateadas según el uso del cliente).

**Comparing Data Between Report UI and CSV Exports — una tabla de mapeo extensa**, documentando explícitamente que los nombres de columna difieren entre la interfaz (nombres legibles como "Cost (Total)") y el CSV exportado (nombres técnicos como `unblended_cost`) — y que algunas unidades de medida difieren deliberadamente (el CSV da precisión decimal completa sin formato, para uso programático; la interfaz redondea para legibilidad).

## Por qué importa en una conversación con el cliente

La tabla de seis variantes de costo es, posiblemente, el recurso de mayor valor práctico de todo este proyecto de Cloudability — vale la pena entregarla directamente a cualquier cliente que esté diseñando su primer reporte de chargeback, ya que elegir la métrica equivocada (por ejemplo, Cost Total en vez de Amortized cuando hay RIs prepagadas activas) genera resultados sistemáticamente distorsionados sin que el error sea evidente.

La mejora de asignación de RI (asignar el costo al recurso beneficiado, no a la cuenta compradora) es un diferenciador de producto real frente a analizar la factura cruda del proveedor directamente — vale la pena destacarlo explícitamente en cualquier conversación donde el cliente compare Cloudability contra construir sus propios reportes desde el CUR de AWS.

La tabla de mapeo CSV-vs-UI es material de referencia técnica esencial para cualquier equipo de datos del cliente que construya pipelines automatizados sobre las exportaciones de Cloudability — evita errores de mapeo de columna al integrar con sistemas externos (data warehouses, BI).

## Documentos fuente

- Glossary of utilization dimensions and metrics — `kb/02-product-docs/apptio-cloudability-standard/en/reference-glossary-utilization-dimensions-metrics.md`
- Glossary of Cost Dimensions and Metrics — `kb/02-product-docs/apptio-cloudability-standard/en/reference-glossary-cost-dimensions-metrics.md`
- Making the most of popular dimensions and metrics within Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/reference-making-most-popular-dimensions-metrics-within-cloudability.md`
- Comparing Data Between Report UI and CSV Exports — `kb/02-product-docs/apptio-cloudability-standard/en/reference-comparing-data-between-report-ui-csv-exports.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
