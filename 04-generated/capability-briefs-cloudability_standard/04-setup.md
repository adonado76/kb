---
tbm_concept: "Setup (Cost Sharing/allocation, Business Mappings jerárquicos, Business vs. Calculated Metrics, y configuración base de organización)"
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
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-organize-your-cloud-spend.md
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-tag-label-mapping.md
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-account-groups.md
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-business-mapping.md
  - kb/02-product-docs/apptio-cloudability-standard/en/mapping-organize-data-using-hierarchical-business-mappings.md
  - kb/02-product-docs/apptio-cloudability-standard/en/mapping-business-metrics-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-calculated-metrics.md
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-setting-up-time-zone-preferences.md
  - kb/02-product-docs/apptio-cloudability-standard/en/setup-data-reprocess.md
last_updated: "2026-07-09"
---
# Setup — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Antes de que cualquier dashboard, insight o recomendación de optimización tenga sentido de negocio, el gasto de nube crudo tiene que organizarse según la taxonomía real de la organización — quién paga qué, cómo se reparten los costos compartidos, y qué métricas personalizadas importan más allá de las que el proveedor de nube expone por defecto. Este capítulo cubre esa capa de configuración fundacional.

## Cómo lo resuelve IBM Cloudability Standard

**Cost Sharing — el mecanismo central de showback/chargeback, con cuatro estrategias de asignación.** Compartir costo es tomar un bucket de gasto directo y repartirlo entre destinos. Estrategias documentadas: **Even Split** (reparto igualitario), **Fixed Weighting** (pesos fijos definidos por el usuario), **proportional_metric** (reparto proporcional a una métrica), y **telemetry_consumption** (reparto basado en datos de telemetría real de uso — **exclusivo de Cloudability Standard y Premium**, no disponible en la edición básica). Las reglas se configuran desde Organize → Cost Sharing, sin límite documentado de reglas de asignación. **Import/Export vía CSV** permite generación masiva de reglas sin configurarlas una por una en la interfaz, con una plantilla exacta de columnas (Rule ID, Allocation Method, Source, Destination, Destination Weight, Telemetry Identifier, Metric Name).

**El comportamiento de Cost Sharing en reportes y Views está documentado con precisión**: un toggle dedicado en el editor de Reports/Dashboard Widgets activa la vista de costos ya asignados; y las Views respetan la lógica de reparto — un producto que recibe costo compartido de otro lo ve reflejado en su bucket destino cuando ese bucket está incluido en la View, mostrando tanto su cargo directo como lo recibido por reparto.

**Business Mappings — la taxonomía de negocio propia de la organización, evaluada al momento de la ingesta.** A diferencia de las dimensiones provistas por el vendor o basadas en facturación, las Business Dimensions se construyen con **statements** (declaraciones tipo "case statement") que traducen metadata técnica de facturación en conceptos de negocio. Límite documentado: **máximo 10 Business Dimensions** por organización. El orden de ejecución importa — lógica AND con **evaluación de cortocircuito** (short-circuit), deteniéndose en la primera condición que falla.

**Hierarchical Business Mappings (HBM) — resuelve el problema de mantener jerarquías de rollup a escala.** En vez de crear Business Mappings separados para cada nivel (Team → Department → Group) y mantener manualmente cómo cada Team mapea a su Department, un HBM define la relación de rollup completa vía un **mapping file** (CSV): la columna más a la izquierda es la dimensión base, cada columna subsiguiente es un nivel padre. Se pueden agregar hasta **4 capas adicionales** sobre la dimensión base, y el nombre de la jerarquía se convierte en el nodo raíz de su View jerárquica correspondiente.

**Business Metrics vs. Calculated Metrics — una distinción con implicación de performance directa, documentada explícitamente en una tabla comparativa.** Business Metrics se evalúan **al momento de la ingesta**, aplicándose a cada fila de forma individual. Calculated Metrics se evalúan **al momento de la consulta** (cuando se carga un Dashboard o Reporte), aplicándose sobre el resultado ya agregado — permiten combinar métricas estándar, business metrics, constantes y operaciones aritméticas básicas para KPIs y métricas de unit economics propias de la organización (ej. comparar costo de nube original vs. costo efectivo amortizado, para medir el impacto financiero real de compromisos y descuentos negociados). Calculated Metrics soporta **tres niveles de permiso** que controlan quién puede ver/editar cada métrica.

**Tag & Label Mapping, Account Groups, Time Zone y Data Reprocess** — el resto de la capa de organización: mapeo de etiquetas de proveedor (con la advertencia de FAQ de que las etiquetas de recurso de AWS no aparecen en la página de mapeo si no se configuraron primero explícitamente en AWS Billing Preferences para incluirse en el Cost and Usage Report), agrupación de cuentas para reporte consolidado, preferencias de zona horaria, y **reprocesamiento retrospectivo de datos históricos** cuando cambia una Business Mapping, Account Group, o estrategia de Tags — sin este mecanismo, un cambio de taxonomía solo aplicaría hacia adelante, dejando el historial desalineado con la nueva estructura de negocio.

## Por qué importa en una conversación con el cliente

La distinción telemetry_consumption como exclusiva de Cloudability Standard y Premium es un dato de licenciamiento importante — vale la pena confirmar la edición real del cliente antes de prometer reparto de costo basado en telemetría de uso real.

El límite de 10 Business Dimensions es una restricción de diseño que conviene anticipar en cualquier discovery de taxonomía — si el cliente ya visualiza más de 10 dimensiones de negocio distintas, hay que diseñar deliberadamente cuáles consolidar o resolver vía Hierarchical Business Mappings en lugar de dimensiones planas separadas.

La distinción Business Metrics (ingesta, por fila) vs. Calculated Metrics (consulta, sobre agregado) es la pregunta técnica correcta antes de diseñar cualquier métrica personalizada — confundirlas genera expectativas equivocadas de cuándo y cómo se actualiza un número derivado.

Data Reprocess es el argumento de integridad histórica a mencionar proactivamente en cualquier conversación donde el cliente anticipe una reorganización de negocio (fusión, reestructuración de unidades) — sin este mecanismo, el histórico de reportes quedaría inconsistente con la nueva taxonomía.

## Documentos fuente

- Sharing Cost in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/setup-sharing-cost-in-cloudability.md`
- Cost Sharing in Reports and Dashboards — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-reports-dashboards.md`
- Cost Sharing: Telemetry / Consumption-Based Allocations — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-cost-sharing-telemetry-consumption-based-allocations.md`
- Organize Your Cloud Spend — `kb/02-product-docs/apptio-cloudability-standard/en/setup-organize-your-cloud-spend.md`
- Tag & Label Mapping — `kb/02-product-docs/apptio-cloudability-standard/en/spend-tag-label-mapping.md`
- Account Groups — `kb/02-product-docs/apptio-cloudability-standard/en/spend-account-groups.md`
- Business Mapping — `kb/02-product-docs/apptio-cloudability-standard/en/spend-business-mapping.md`
- Organize Data Using Hierarchical Business Mappings — `kb/02-product-docs/apptio-cloudability-standard/en/mapping-organize-data-using-hierarchical-business-mappings.md`
- Business Metrics in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/mapping-business-metrics-in-cloudability.md`
- Calculated Metrics — `kb/02-product-docs/apptio-cloudability-standard/en/spend-calculated-metrics.md`
- Setting Up Time Zone Preferences — `kb/02-product-docs/apptio-cloudability-standard/en/setup-setting-up-time-zone-preferences.md`
- Data Reprocess — `kb/02-product-docs/apptio-cloudability-standard/en/setup-data-reprocess.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
