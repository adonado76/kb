---
tbm_concept: "Data Integration — Other Sources (integraciones más allá de la factura de nube: observabilidad, ITSM, bases de datos, notificaciones, identidad, y Kubernetes)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-turbonomic.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-custom-data-focus-ingress.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-databricks.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-datadog-utilization-data.md
  - kb/02-product-docs/apptio-cloudability-standard/en/data-connect-datadog-cost-usage.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-mongodb.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-snowflake.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-jira-cloud.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-servicenow.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-servicenow-cmdb.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-pagerduty.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-new-relic.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-microsoft-entra-id.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-kubernetes-cluster-provisioning.md
  - kb/02-product-docs/apptio-cloudability-standard/en/provisioning-common-kubernetes-metrics-agent-error-messages.md
last_updated: "2026-07-09"
---
# Data Integration — Other Sources — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Más allá de la factura de los cinco grandes proveedores de nube, el ecosistema tecnológico real de una organización incluye herramientas de observabilidad, ITSM, bases de datos gestionadas, notificaciones y sistemas de identidad — cada una con datos que enriquecen o dependen de la visión de costo de Cloudability. Esta categoría documenta 14 integraciones adicionales, con la integración de ServiceNow CMDB destacándose como la más sofisticada de todo el grupo.

## Cómo lo resuelve IBM Cloudability Standard

**ServiceNow CMDB Integration — la integración más rica documentada en esta categoría, con beneficios explícitos de negocio.** Permite sincronización bidireccional entre el CMDB de ServiceNow y Cloudability, con tres beneficios clave documentados textualmente: **Automated Business Mapping** (crear y mantener Business Mappings usando datos ya existentes del CMDB, reduciendo esfuerzo manual y mejorando precisión), **Centralized Data Management** (el CMDB como única fuente de verdad de estructura organizacional, aplicaciones y centros de costo que dirigen la asignación de costo de nube), y **Real-time Synchronization** (los Business Mappings de Cloudability se mantienen al día automáticamente con los cambios del CMDB). Se instala desde el ServiceNow Store, y expone casos de uso concretos como crear/actualizar Business Dimensions directamente desde ServiceNow usando datos del CMDB — sin necesidad de mantener esa taxonomía por duplicado en ambos sistemas.

**Turbonomic** — la misma integración de optimización ya documentada extensamente en TBM Studio y Costing Standard, aquí conectada específicamente hacia Cloudability para complementar sus propias recomendaciones de Rightsizing con las de Turbonomic.

**FOCUS Ingress (Connect Custom Data)** — un mecanismo de ingesta genérico basado en el estándar de la industria **FOCUS** (FinOps Open Cost and Usage Specification), permitiendo conectar fuentes de costo que no tienen un conector nativo dedicado, siempre que puedan exportar datos en ese formato estandarizado.

**Datadog — con dos integraciones distintas y complementarias.** Una trae datos de **utilización** (métricas de performance de infraestructura, relevantes para Rightsizing) y la otra trae datos de **costo y uso de Datadog en sí mismo** (Datadog como línea de gasto a monitorear dentro de Cloudability, no solo como fuente de métricas).

**Databricks, MongoDB, Snowflake** — conectores para plataformas de datos gestionadas, trayendo su costo y consumo específico hacia el modelo consolidado de Cloudability, un patrón cada vez más relevante dado que estas plataformas suelen representar líneas de gasto crecientes y mal visibilizadas en el gasto de nube tradicional.

**Jira Cloud, PagerDuty, New Relic** — integraciones hacia herramientas de gestión de trabajo, notificaciones/alertas, y observabilidad de aplicaciones — probablemente habilitando flujos de trabajo donde una anomalía de costo o una recomendación de Rightsizing puede generar un ticket de Jira o una alerta de PagerDuty automáticamente, cerrando el ciclo entre detección y acción.

**Microsoft Entra ID** — integración de identidad (el sucesor de Azure Active Directory), relevante para gestión de usuarios y grupos dentro de Cloudability sincronizados con el directorio corporativo del cliente.

**Kubernetes Cluster Provisioning y manejo de errores del Metrics Agent** — el mecanismo técnico detrás de la visibilidad de costo de contenedores ya mencionada en Getting Started, con un artículo dedicado a diagnosticar los mensajes de error más comunes del agente de métricas — sugiriendo que esta es una de las integraciones con mayor superficie de problemas operativos, dado que requiere un agente corriendo dentro del propio clúster del cliente, no solo una credencial de API.

## Por qué importa en una conversación con el cliente

La integración de ServiceNow CMDB es el argumento más fuerte de este capítulo para clientes que ya tienen ServiceNow como fuente de verdad organizacional — evita la duplicación de taxonomía de negocio entre dos sistemas, y conecta directamente con el mismo patrón de integración ServiceNow ya documentado en Costing Standard y TBM Studio, reforzando la consistencia arquitectónica de todo el portafolio Apptio/IBM.

Las dos integraciones de Datadog (utilización vs. costo) son una distinción de discovery importante — vale la pena confirmar cuál necesita el cliente, o si necesita ambas, antes de asumir que "conectar Datadog" es una sola tarea.

El artículo dedicado a errores comunes del Kubernetes Metrics Agent es una señal honesta de que esta integración tiene más fricción operativa que las demás — vale la pena anticipar esto en cualquier propuesta que incluya visibilidad de costo de contenedores, reservando tiempo de troubleshooting en el cronograma.

## Documentos fuente

- Connect Turbonomic — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-turbonomic.md`
- Connect Custom Data (FOCUS Ingress) — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-custom-data-focus-ingress.md`
- Connect Databricks — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-databricks.md`
- Connect Datadog - Utilization Data — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-datadog-utilization-data.md`
- Connect Datadog - Cost & Usage — `kb/02-product-docs/apptio-cloudability-standard/en/data-connect-datadog-cost-usage.md`
- Connect MongoDB — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-mongodb.md`
- Connect Snowflake — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-snowflake.md`
- Connect Jira Cloud — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-jira-cloud.md`
- Connect to ServiceNow — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-servicenow.md`
- Connect to ServiceNow CMDB — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-servicenow-cmdb.md`
- Connect Pagerduty — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-pagerduty.md`
- Connect New Relic — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-new-relic.md`
- Connect Microsoft Entra ID — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-microsoft-entra-id.md`
- Kubernetes Cluster Provisioning — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-kubernetes-cluster-provisioning.md`
- Common Kubernetes Metrics Agent Error Messages — `kb/02-product-docs/apptio-cloudability-standard/en/provisioning-common-kubernetes-metrics-agent-error-messages.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
