---
concept: "Cloudability API (catálogo de referencia de los 62 documentos de endpoints REST — V3 — para automatizar consumo, configuración y gestión programática de Cloudability)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/about-cloudability-api.md
  - kb/02-product-docs/apptio-cloudability-standard/en/getting-started-cloudability-api-v3.md
last_updated: "2026-07-09"
---
# Cloudability API — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Con 62 documentos de referencia técnica, la API de Cloudability es la categoría más extensa de todo este proyecto — comparable en volumen al catálogo de Formulas and Functions de TBM Studio. Este brief se presenta como catálogo condensado por familia de endpoint, no como desarrollo narrativo de cada uno, dado que su valor es de consulta puntual durante integración, no de lectura lineal.

## Cómo lo resuelve IBM Cloudability Standard

**API V3 — el estándar actual**, con guía de introducción (About the Cloudability API, Getting Started with Cloudability API V3) cubriendo autenticación y convenciones base antes de cualquier endpoint específico.

**Reporting y análisis de costo**
- **Cost Reporting End Point** — el corazón de la API: extracción programática de datos de costo con las mismas dimensiones/métricas del catálogo de Data Reference.
- **Calculated Metrics End Point** — métricas derivadas personalizadas, expuestas vía API.
- **Report API Documentation** — referencia general de construcción de reportes vía API.
- **Resource Inventory – Public API End Points** — inventario de recursos de nube.
- **Cloud Sustainability End Points** — métricas de emisiones de carbono vía API.
- **Utilization Reports End Point** — datos de utilización programáticos.

**Organización y estructura de datos (Organize, vía API)**
- **Account Groups End Point / Account Group Entries** — gestión programática de agrupación de cuentas.
- **Business Mappings End Point**, con cuatro sub-documentos de detalle: Structure of a Business Mapping, Business Mapping Expression Language (el lenguaje de reglas para clasificar gasto), Multiple Rules Working Together (precedencia/combinación de reglas), y Business Mapping Templates.
- **Common Dimension Keys** — referencia de claves de dimensión reutilizables entre endpoints.
- **Views End Point** — gestión programática de vistas (filtros a nivel de aplicación).

**Presupuesto y planeación (vía API)**
- **Budgets & Forecasting End Points**, con tres sub-endpoints: Estimates, Budgets and Budget Subscriptions, Forecasts.
- **Cloudability Workload Planning API End Points** — la contraparte API del módulo Workload Planning ya visto en Plan.

**Cost Sharing (vía API)** — cinco endpoints especializados: Cost Sharing End Points (general), Rule Setting, Result Report, Allocations, Rules, y **Cost Sharing Telemetry** — este último para cargar datos de telemetría de uso real que alimentan las Telemetry-Based Allocations ya mencionadas en Getting Started.

**Compromisos y optimización (vía API)** — el reflejo API de todo el capítulo Optimize: Rightsizing End Points, Rightsizing ROI End Points, RI Planner End Point, RI Portfolio End Points (con una variante **Legacy** documentada por separado, y Reservation Portfolio End Point), y Scorecards End Point.

**Governance (vía API)** — cinco sub-áreas alineadas exactamente con el flujo ya documentado en el capítulo Governance: Governance Set Up, Deployment/Project/Preferences Management, Policy Management & Evaluation, Cost Estimation & Resource Recommendation, Pull Requests Tracking, y Metrics & Analytics — confirmando que toda la integración de GitHub/Terraform tiene una superficie API completa, no solo interfaz de usuario.

**Credenciales de proveedor (vía API)** — endpoints dedicados por proveedor: AWS, Azure, GCP, OCI, e **IBM** (confirmando que Cloudability puede ingerir costo de IBM Cloud, no solo de los tres hyperscalers tradicionales).

**Integraciones de datos externas (vía API)** — endpoints dedicados para Snowflake, Databricks, Datadog, MongoDB, **FOCUS Ingress** (el estándar abierto FinOps de formato de factura unificado), y PagerDuty.

**Contenedores (vía API)** — Containers End Points, con cuatro sub-áreas: Provisioning, Clusters, Usage, Labels, Counts — el reflejo API completo de la visibilidad de costo de Kubernetes/OpenShift ya mencionada en Getting Started.

**Administración (vía API)** — Users End Point, User Groups and Entra ID Groups End Point (confirmando integración nativa con Microsoft Entra ID para gestión de grupos), y Anomaly Detection End Point.

## Por qué importa en una conversación con el cliente

La cobertura API 1:1 con prácticamente cada capacidad de la interfaz de usuario (Governance, Cost Sharing, Rightsizing, Business Mappings) es un argumento fuerte para clientes con equipos de plataforma que quieren automatizar la configuración de Cloudability como código, en vez de gestionarla manualmente vía interfaz — vale la pena mencionarlo explícitamente a cualquier cliente con cultura de Infrastructure-as-Code madura.

Business Mapping Expression Language merece mención especial en cualquier conversación de diseño de taxonomía de costo — es el motor de reglas que determina cómo se clasifica automáticamente el gasto de nube según la lógica de negocio del cliente, y entender su capacidad (múltiples reglas, precedencia) es clave antes de diseñar cualquier estructura de Business Mapping compleja.

Cost Sharing Telemetry es el puente API hacia la funcionalidad de Telemetry-Based Allocations — relevante para cualquier cliente que quiera automatizar la carga de datos de uso real desde sus propios sistemas de monitoreo, en vez de depender de asignación manual de costo compartido.

## Documentos fuente

- About the Cloudability API — `kb/02-product-docs/apptio-cloudability-standard/en/about-cloudability-api.md`
- Getting started with Cloudability API V3 — `kb/02-product-docs/apptio-cloudability-standard/en/getting-started-cloudability-api-v3.md`
- (60 documentos adicionales de referencia de endpoints específicos — Account Groups, Anomaly Detection, Budgets & Forecasting, Business Mappings, Calculated Metrics, Containers, Cost Reporting, Resource Inventory, Cloud Sustainability, Cost Sharing, Vendor Credentials por proveedor, Snowflake/Databricks/Datadog/MongoDB/FOCUS/PagerDuty, Governance, Rightsizing/RI Planner/RI Portfolio, Scorecards, Users/User Groups, Utilization Reports, Views, Workload Planning — ver `kb/02-product-docs/apptio-cloudability-standard/en/` para el listado completo por nombre de archivo)

*Nota: dado el volumen (62 documentos), este brief se presenta como catálogo condensado por familia de endpoint, no como desarrollo narrativo individual. Versión en español/portugués se genera en una siguiente pasada.*
