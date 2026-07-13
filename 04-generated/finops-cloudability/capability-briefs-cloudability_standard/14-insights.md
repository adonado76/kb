---
concept: "Insights (Resource Inventory con métricas de utilización, TrueCost/Tag Explorer, Container Cost Allocation con Advanced Containers/Kubecost, Anomaly Detection, Scorecards, sostenibilidad de nube, y métricas de uso de GenAI)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-resource-inventory.md
  - kb/02-product-docs/apptio-cloudability-standard/en/inventory-aws-resource.md
  - kb/02-product-docs/apptio-cloudability-standard/en/inventory-azure-resource.md
  - kb/02-product-docs/apptio-cloudability-standard/en/inventory-gcp-resource.md
  - kb/02-product-docs/apptio-cloudability-standard/en/inventory-oci-resource.md
  - kb/02-product-docs/apptio-cloudability-standard/en/inventory-resource-faqs.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-truecost-explorer.md
  - kb/02-product-docs/apptio-cloudability-standard/en/explorer-cost-basis-rightsizing-true-cost.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-identify-tagged-untagged-spend-tag-explorer.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-container-cost-allocation.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-analyze-data-your-kubernetes-containers.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-provision-your-container-agent.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-container-costs-allocated-by-vendor.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-vm-family-based-weightings.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-containers-insights-dashboard-widget-guide.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-shared-cost-container-insights-ui.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-container-insights-threshold-based-alerting-configuration-guide.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-agent-observatory-tool.md
  - kb/02-product-docs/apptio-cloudability-standard/en/allocation-cloudability-advanced-containers.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-anomaly-detection.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-scorecards-dashboard-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-cloud-sustainability-reporting.md
  - kb/02-product-docs/apptio-cloudability-standard/en/reporting-cloud-sustainability-methodology.md
  - kb/02-product-docs/apptio-cloudability-standard/en/insights-understand-usage-metrics-genai-services-in-cloudability.md
last_updated: "2026-07-09"
---
# Insights — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Este es el capítulo de mayor volumen y sofisticación técnica de todo el proyecto Cloudability: la capa exploratoria que convierte datos crudos de facturación y consumo en respuestas concretas a preguntas de negocio — qué recurso específico está desperdiciando capacidad, qué proporción del gasto no tiene dueño identificable (sin etiquetar), qué patrón de gasto es anómalo, cómo se compara la organización contra sus pares, y — de forma emergente — cómo se está gastando en servicios de IA generativa.

## Cómo lo resuelve IBM Cloudability Standard

**Resource Inventory — visibilidad a nivel de recurso individual, con métricas de utilización que van más allá del dato de facturación.** Requiere habilitación explícita por parte del equipo de cuenta de Apptio (no autoservicio), con 2-3 días hábiles para que los datos empiecen a aparecer. Tres casos de uso documentados textualmente con su solución: **mapeo de costo a utilización** (combinar inventario con tags/account groups/business mappings para ver exactamente la utilización de CPU/memoria de una instancia específica de un equipo, habilitando showback/chargeback defendible), **reducción de desperdicio** (identificar instancias con CPU/memoria promedio consistentemente baja, o discos con tamaño mucho mayor al dato realmente almacenado), y **optimización de performance** (picos en utilización máxima como señal de necesidad de escalar). Ventana de datos: rolling de tres meses, máximo 31 días por consulta, y **los 3 días más recientes quedan excluidos** por defecto (algunas métricas tardan hasta 72 horas en completarse). KPIs clicables por servicio (ej. "Inactive Instances", "Untagged Instances") permiten filtrado rápido de un clic.

**TrueCost Explorer y Tag Explorer** — ya introducidos en Getting Started, aquí con el detalle de **cost basis para Rightsizing** (True Cost como base de cálculo distinta al costo de factura estándar) y el mecanismo específico de identificar gasto etiquetado vs. sin etiquetar.

**Container Cost Allocation — el sub-área más extensa de este capítulo, con arquitectura propia de agentes.** Requiere desplegar el **IBM FinOps Agent** (recolección de datos, next-generation) y, para recomendaciones de optimización, el **agente kubeturbo de Turbonomic** — ambos vía despliegue HELM por clúster. Soporta las configuraciones de Kubernetes certificadas por CNCF. **Idle Cost Distribution** introduce una categoría de métrica nueva ("Containers") que separa costo **Utilizado, Idle (ocioso) y Fairshare**, tanto en base cash como amortizada — reconociendo que la capacidad sobrante de un clúster tiene un costo real que hay que distribuir, no ignorar. El **Agent Observability Tool** monitorea la salud de los agentes desplegados en tiempo real (últimos 7 días de datos), marcando un clúster como "Inactive" si no reporta en más de 12 horas, con acciones recomendadas explícitas (revisar clústeres inactivos, versiones de agente desactualizadas, nombres de clúster duplicados).

**Advanced Containers (Kubecost) — un módulo nuevo y notable, add-on de pago opcional disponible para Essentials, Standard y Premium.** Trae la visibilidad de costo de contenedores en tiempo real de Kubecost integrada al framework SaaS de Cloudability, con asignación aún más granular (namespace, label, annotation, controller, service) y soporte multi-nube e híbrido/on-prem (incluyendo OpenShift). Ofrece dos experiencias: una vista nativa simplificada dentro de Cloudability (para reporte ejecutivo y visibilidad diaria), y una **aplicación standalone Kubecost 3.0** con capacidades más avanzadas (agrupación multi-dimensional, filtrado AND/OR, resolución horaria, retención configurable) accesible vía deep link con SSO compartido — sin necesidad de login separado.

**Anomaly Detection, con mecánica documentada con precisión.** **Cost Segment Formation** descompone el costo total en segmentos por tipo de servicio, cuenta, categoría de uso y tags/business mappings relevantes, para detectar patrones únicos con mayor precisión. Ciclo de detección: cada 24 horas, re-evaluando y regenerando anomalías de los últimos 7 días — lo cual explica por qué una anomalía puede cambiar de monto o desaparecer sin que haya un error, simplemente el modelo se vuelve más informado dentro de esa ventana. Limitación documentada explícitamente: **solo detecta gasto anómalo hacia arriba, nunca hacia abajo**, y las fórmulas de detección no son configurables (solo el umbral de notificación). Integración con **Jira Cloud y ServiceNow** para crear tickets directamente desde una anomalía, con **sincronización bidireccional** de estado. Soporta **alertas compartidas** entre múltiples usuarios (reduciendo configuración duplicada) y una funcionalidad de **Ignore Alert** para silenciar ruido durante eventos de costo esperados.

**Scorecards** — benchmarking ya introducido en Getting Started, comparando el uso de nube de la organización contra pares de industria y entre unidades de negocio propias.

**Cloud Sustainability Reporting** — huella de carbono (Operacional + Incorporada/Embodied) para servicios soportados, con una metodología documentada por separado.

**Entendiendo métricas de uso de servicios GenAI — la capacidad más reciente documentada en todo el proyecto.** Dos categorías de carga de trabajo: **inferencia** (uso de modelos ya entrenados, facturado por tokens/caracteres, aparece como "Usage Quantity") y **entrenamiento/fine-tuning** (trabajos intensivos en cómputo, facturados por horas de GPU/TPU/instancia, aparece como "Usage Hours"). Ejemplos documentados por proveedor: AWS Bedrock factura por tokens (Usage Quantity), Azure OpenAI/AI Foundry por bloques de 1K tokens. Mejores prácticas FinOps documentadas: normalizar uso (aproximadamente 4 caracteres = 1 token, para comparar entre proveedores de nube), separar cómputo de entrenamiento vs. inferencia, y correlacionar costo con descripción de línea de ítem para identificar uso real.

## Por qué importa en una conversación con el cliente

Advanced Containers (Kubecost) es el anuncio de producto más reciente y estratégicamente relevante de todo el proyecto Cloudability — vale la pena mencionarlo explícitamente como add-on de pago opcional en cualquier conversación con un cliente que ya tiene una práctica de Kubernetes madura y encuentra limitada la granularidad del Container Cost Allocation estándar.

La limitación de Anomaly Detection a solo detectar subidas de gasto (nunca bajadas) es un detalle de alcance importante que vale la pena aclarar proactivamente — un cliente que espera que el sistema le avise de una reducción inesperada de gasto (que podría indicar un problema de facturación al revés) necesita un mecanismo complementario.

Las métricas de uso de GenAI son el gancho de conversación más actual de todo el proyecto — para cualquier cliente que ya esté gastando en AWS Bedrock, Azure OpenAI, o servicios similares, mostrar que Cloudability ya tiene un marco de normalización y mejores prácticas específico para este tipo de gasto es un diferenciador de vigencia de producto.

## Documentos fuente

- Resource Inventory (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/insights-resource-inventory.md`
- AWS/Azure/GCP/OCI Resource Inventory — `kb/02-product-docs/apptio-cloudability-standard/en/inventory-aws-resource.md`, `inventory-azure-resource.md`, `inventory-gcp-resource.md`, `inventory-oci-resource.md`
- Resource Inventory FAQs — `kb/02-product-docs/apptio-cloudability-standard/en/inventory-resource-faqs.md`
- TrueCost Explorer — `kb/02-product-docs/apptio-cloudability-standard/en/insights-truecost-explorer.md`
- Cost Basis for Rightsizing / True Cost — `kb/02-product-docs/apptio-cloudability-standard/en/explorer-cost-basis-rightsizing-true-cost.md`
- Tag Explorer — `kb/02-product-docs/apptio-cloudability-standard/en/insights-identify-tagged-untagged-spend-tag-explorer.md`
- Container Cost Allocation (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/insights-container-cost-allocation.md`
- Analyze Data for Your Kubernetes Containers — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-analyze-data-your-kubernetes-containers.md`
- Provision Your Container Agent — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-provision-your-container-agent.md`
- Container Costs Allocated by Vendor — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-container-costs-allocated-by-vendor.md`
- VM Family-Based Weightings — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-vm-family-based-weightings.md`
- Container Insights Dashboard Widget Guide — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-containers-insights-dashboard-widget-guide.md`
- Shared Cost in Container Insights UI — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-shared-cost-container-insights-ui.md`
- Container Insights Threshold-Based Alerting Configuration — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-container-insights-threshold-based-alerting-configuration-guide.md`
- Agent Observability Tool — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-agent-observatory-tool.md`
- Cloudability Advanced Containers — `kb/02-product-docs/apptio-cloudability-standard/en/allocation-cloudability-advanced-containers.md`
- Anomaly Detection — `kb/02-product-docs/apptio-cloudability-standard/en/insights-anomaly-detection.md`
- Scorecards Dashboard in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/insights-scorecards-dashboard-in-cloudability.md`
- Cloud Sustainability Reporting — `kb/02-product-docs/apptio-cloudability-standard/en/insights-cloud-sustainability-reporting.md`
- Cloud Sustainability Methodology — `kb/02-product-docs/apptio-cloudability-standard/en/reporting-cloud-sustainability-methodology.md`
- Understanding Usage Metrics for GenAI Services — `kb/02-product-docs/apptio-cloudability-standard/en/insights-understand-usage-metrics-genai-services-in-cloudability.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
