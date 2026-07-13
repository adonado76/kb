---
concept: "Reference: Model Studio — referencia técnica completa de objetos del modelo, drivers, asignaciones, métricas, diagramas Sankey y reportes de modelo"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/reference-model-objects.md
  - kb/02-product-docs/apptio-tbm-studio/en/objects-model-object-properties.md
  - kb/02-product-docs/apptio-tbm-studio/en/objects-object-relationships-dependencies.md
  - kb/02-product-docs/apptio-tbm-studio/en/objects-object-naming-conventions.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-drivers.md
  - kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-configuration-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-data-requirements.md
  - kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-validation-rules.md
  - kb/02-product-docs/apptio-tbm-studio/en/drivers-deleting-driver.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-allocations.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-all-allocation-configuration-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-order-precedence.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-calculation-behavior.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-model-metrics.md
  - kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-classification.md
  - kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-properties.md
  - kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-aggregation-rules.md
  - kb/02-product-docs/apptio-tbm-studio/en/metrics-custom-metric-creation.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-model-diagrams.md
  - kb/02-product-docs/apptio-tbm-studio/en/diagrams-sankey-diagram-concepts.md
  - kb/02-product-docs/apptio-tbm-studio/en/diagrams-diagram-navigation.md
  - kb/02-product-docs/apptio-tbm-studio/en/diagrams-diagram-customization-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/diagrams-export-sharing.md
  - kb/02-product-docs/apptio-tbm-studio/en/reference-model-reports.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-model-report-types.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-visualization-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-report-parameters.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-common-issues.md
last_updated: "2026-07-07"
---
# Reference: Model Studio — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

El equivalente de referencia técnica exhaustiva de Model Studio, complementando la explicación conceptual ya cubierta en "Concepts: Model Architecture". Aquí el foco es consulta rápida: cada propiedad, cada tipo, cada opción de configuración documentada para lookup.

## Cómo lo resuelve Apptio TBM Studio

**Model Objects — un solo tipo unificado, con propósito determinado por posición y configuración.** A diferencia de lo que su nombre podría sugerir, TBM Studio **no** tiene tipos de objeto de modelo separados en el sistema — soporta **un tipo unificado de objeto** cuyo rol (fuente, intermedio, destino) se determina por su posición en la jerarquía del modelo y su configuración, no por una categoría de sistema distinta. Object Relationships and Dependencies documenta los tipos de relación con su dirección; Object Naming Conventions da patrones recomendados de nomenclatura para mantenibilidad y comprensión del equipo.

**Drivers — tres tipos, reference confirmado.** Complementa lo ya visto en el capítulo How-To: **Unit Driver** (cómo el valor entra a un objeto), y (por el patrón ya establecido en Build Cost Models) los drivers de asignación con lógica de matching y ponderación. Driver Configuration Options, Driver Data Requirements y Driver Validation Rules dan la referencia exhaustiva de cada opción disponible; Deleting a Driver documenta el procedimiento y sus implicaciones.

**Allocations — los cinco tipos ya vistos en Concepts: Model Architecture, aquí con referencia exhaustiva de cada opción de configuración**, más Allocation Order and Precedence (la referencia técnica del mecanismo de secuenciación automática ya explicado conceptualmente) y Allocation Calculation Behavior (el detalle de cómo se comporta el cálculo en casos de borde).

**Model Metrics — tipos de métrica estándar, propiedades, reglas de agregación, y creación de métrica personalizada.** Extiende la distinción Modeled vs. Calculated ya vista en Model Architecture con el catálogo completo de tipos de métrica estándar incluidos out-of-the-box, sus propiedades configurables, y cómo se agregan (suman, promedian, etc.) a través de dimensiones y tiempo.

**Model Diagrams — tres formas de ver el modelo, cada una con un propósito distinto.** **Single-Table View (Model Edit Workspace)** — la vista de una sola tabla ya vista en How-To: Build Cost Models. Las otras dos vistas (Diagram View de estructura completa, y una tercera de navegación/drill) ya fueron mencionadas conceptualmente en "Trace Cost Flows Through the Model" del capítulo How-To. Sankey Diagram Concepts da la referencia formal de cómo crear un Model Report (Home tab → New → Model Report → Edit Metrics para seleccionar qué métricas incluir), más navegación, opciones de personalización, y exportación/compartición del diagrama.

**Model Reports — tipos, opciones de visualización, parámetros, y problemas comunes.** El catálogo de referencia de los reportes de modelo (distintos de los reportes de Report Studio) — con su propia sección de troubleshooting de problemas frecuentes.

## Por qué importa en una conversación con el cliente

El hallazgo de que TBM Studio usa **un solo tipo unificado de objeto de modelo** (no tipos separados de sistema para "fuente" vs. "intermedio" vs. "destino") es un detalle arquitectónico importante para corregir cualquier expectativa de un cliente que venga de otra herramienta de modelado con tipos de objeto más rígidos — en TBM Studio, la flexibilidad de rol es una característica de diseño, no una limitación.

Object Naming Conventions es un recurso de gobernanza de proyecto que vale la pena adoptar formalmente desde el inicio de cualquier implementación — establecer un patrón de nomenclatura consistente antes de que el modelo crezca a docenas de objetos evita el caos de nomenclatura ad hoc que es costoso de corregir retroactivamente.

La sección de Common Issues en Model Reports es un recurso de troubleshooting proactivo que vale la pena compartir con el equipo operativo del cliente durante la fase de handover — reduce la dependencia de escalamiento hacia soporte para problemas ya catalogados y resueltos.

## Documentos fuente

- Model Objects (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-model-objects.md`
- Model Object Properties — `kb/02-product-docs/apptio-tbm-studio/en/objects-model-object-properties.md`
- Object Relationships and Dependencies — `kb/02-product-docs/apptio-tbm-studio/en/objects-object-relationships-dependencies.md`
- Object Naming Conventions — `kb/02-product-docs/apptio-tbm-studio/en/objects-object-naming-conventions.md`
- Drivers (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-drivers.md`
- Driver Configuration Options — `kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-configuration-options.md`
- Driver Data Requirements — `kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-data-requirements.md`
- Driver Validation Rules — `kb/02-product-docs/apptio-tbm-studio/en/drivers-driver-validation-rules.md`
- Deleting a Driver — `kb/02-product-docs/apptio-tbm-studio/en/drivers-deleting-driver.md`
- Allocations (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-allocations.md`
- All Allocation Configuration Options — `kb/02-product-docs/apptio-tbm-studio/en/allocations-all-allocation-configuration-options.md`
- Allocation Order and Precedence — `kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-order-precedence.md`
- Allocation Calculation Behavior — `kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-calculation-behavior.md`
- Model Metrics (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-model-metrics.md`
- Metric Classification — `kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-classification.md`
- Metric Properties — `kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-properties.md`
- Metric Aggregation Rules — `kb/02-product-docs/apptio-tbm-studio/en/metrics-metric-aggregation-rules.md`
- Custom Metric Creation — `kb/02-product-docs/apptio-tbm-studio/en/metrics-custom-metric-creation.md`
- Model Diagrams (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-model-diagrams.md`
- Sankey Diagram Concepts — `kb/02-product-docs/apptio-tbm-studio/en/diagrams-sankey-diagram-concepts.md`
- Diagram Navigation — `kb/02-product-docs/apptio-tbm-studio/en/diagrams-diagram-navigation.md`
- Diagram Customization Options — `kb/02-product-docs/apptio-tbm-studio/en/diagrams-diagram-customization-options.md`
- Export and Sharing — `kb/02-product-docs/apptio-tbm-studio/en/diagrams-export-sharing.md`
- Model Reports (índice) — `kb/02-product-docs/apptio-tbm-studio/en/reference-model-reports.md`
- Model Report Types — `kb/02-product-docs/apptio-tbm-studio/en/reports-model-report-types.md`
- Visualization Options — `kb/02-product-docs/apptio-tbm-studio/en/reports-visualization-options.md`
- Report Parameters — `kb/02-product-docs/apptio-tbm-studio/en/reports-report-parameters.md`
- Common Issues — `kb/02-product-docs/apptio-tbm-studio/en/reports-common-issues.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
