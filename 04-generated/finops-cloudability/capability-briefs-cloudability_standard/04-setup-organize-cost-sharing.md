---
concept: "Cost Sharing (showback/chargeback con cuatro estrategias de asignación, incluyendo telemetry-based, exclusiva de Standard/Premium)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-sharing-cost-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-reports-dashboards.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-telemetry-consumption-based-allocations.md
last_updated: "2026-07-13"
---
# Setup — Organize - Cost Sharing — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Compartir costo es tomar un bucket de gasto directo — por ejemplo, un clúster compartido, una plataforma central de datos, o un servicio de soporte interno — y repartirlo entre los destinos que realmente lo consumen. Es el mecanismo central de showback y chargeback dentro de Cloudability: sin él, cualquier costo compartido quedaría atribuido en su totalidad a quien lo paga directamente, distorsionando la vista real de consumo por equipo o unidad de negocio.

## Cómo lo resuelve IBM Cloudability Standard

**Cuatro estrategias de asignación documentadas:**
- **Even Split** — reparto igualitario entre los destinos definidos.
- **Fixed Weighting** — pesos fijos definidos por el usuario para cada destino.
- **proportional_metric** — reparto proporcional al valor de una métrica existente (ej. repartir el costo de un clúster compartido según el uso de CPU de cada equipo).
- **telemetry_consumption** — reparto basado en datos de telemetría real de uso, subidos por el cliente. **Exclusiva de Cloudability Standard y Premium — no disponible en la edición básica.**

**Configuración sin límite documentado de reglas de asignación**, gestionable desde Organize → Cost Sharing.

**Import/Export vía CSV para generación masiva de reglas**, con una plantilla de columnas exacta: Rule ID, Allocation Method, Source, Destination, Destination Weight, Telemetry Identifier, Metric Name — permite crear o modificar decenas de reglas de una sola vez sin pasar por la interfaz regla por regla.

**Comportamiento documentado con precisión en Reports y Dashboard Widgets**: un toggle dedicado en el editor de Reports/Dashboard Widgets activa la vista de costos ya asignados (post cost-sharing). Las Views respetan esta lógica de reparto — un producto o equipo que recibe costo compartido de otro lo ve reflejado en su bucket destino cuando ese bucket está incluido en la View, mostrando tanto su cargo directo como lo recibido por reparto, sin necesidad de reconciliar ambos manualmente.

**Compatibilidad con Business Metrics denominadas en moneda para asignación en contextos distintos al costo bruto.** Las reglas de Cost Sharing pueden asignarse sobre cualquier Business Metric en moneda existente en el entorno del cliente (excluyendo las no monetarias), lo que permite repartir costo compartido usando una métrica de negocio propia en vez de únicamente costo de nube crudo.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** cuando múltiples equipos comparten infraestructura (un clúster de Kubernetes compartido, un data warehouse central, licencias de una plataforma de observabilidad), Cost Sharing resuelve la pregunta de "¿cuánto de este costo compartido le toca a cada equipo?" de forma sistemática y auditable, en vez de dejarlo como un cálculo manual en spreadsheets que se desactualiza cada mes.

**VALOR DIFERENCIAL:** la distinción de `telemetry_consumption` como exclusiva de Cloudability Standard y Premium es un dato de licenciamiento importante — vale la pena confirmar la edición real del cliente antes de prometer reparto de costo basado en telemetría de uso real, ya que en la edición básica esa estrategia simplemente no está disponible. El soporte de Import/Export vía CSV es un diferenciador operativo relevante para clientes con decenas o cientos de reglas de asignación, donde gestionar cada regla individualmente en la interfaz no escala. La compatibilidad con Business Metrics en moneda abre la conversación de repartir costo compartido usando métricas de unit economics propias del cliente, no solo el costo bruto de nube.

## Documentos fuente

- Sharing Cost in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/setup-sharing-cost-in-cloudability.md`
- Cost Sharing in Reports and Dashboards — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-reports-dashboards.md`
- Cost Sharing: Telemetry / Consumption-Based Allocations — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-telemetry-consumption-based-allocations.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=product-cost-sharing

*Nota: versión en español/portugués se genera en una siguiente pasada.*
