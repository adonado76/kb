---
concept: "How-To: Build Cost Models (fundamentos del modelo, creación de asignaciones, y modelado avanzado en Model Studio)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/models-model-basics.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-add-table-model.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-understand-model-metrics-cost-budget-forecast.md
  - kb/02-product-docs/apptio-tbm-studio/en/basics-view-model-diagram.md
  - kb/02-product-docs/apptio-tbm-studio/en/models-create-allocations.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-set-up-simple-one-one.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-configure-drivers.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-create-multi-tier.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-handle-unallocated-costs.md
  - kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-troubleshooting-reference.md
  - kb/02-product-docs/apptio-tbm-studio/en/models-advanced-modeling.md
  - kb/02-product-docs/apptio-tbm-studio/en/modeling-use-matching-logic-allocations.md
  - kb/02-product-docs/apptio-tbm-studio/en/modeling-configure-weighting-columns.md
  - kb/02-product-docs/apptio-tbm-studio/en/modeling-trace-cost-flows-through-model.md
  - kb/02-product-docs/apptio-tbm-studio/en/modeling-create-model-reports-sankey-diagrams.md
last_updated: "2026-07-07"
---
# How-To: Build Cost Models — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Este es el corazón operativo de TBM Studio: el manual de Model Studio, donde una tabla de datos ya cargada se convierte en un objeto del modelo que participa en asignaciones de costo. Tres bloques, de lo básico a lo avanzado.

## Cómo lo resuelve Apptio TBM Studio

### Model Basics — de tabla a objeto del modelo

**Add a Table to the Model** — el paso mecánico: agregar un paso "Model" al pipeline de transformación de una tabla convierte su vista en un diagrama Sankey de una sola tabla, con espacio para drivers a la izquierda y destinos de asignación a la derecha.

**Understand Model Metrics (Cost, Budget, Forecast)** — la distinción ya introducida en Getting Started, desarrollada aquí operativamente: cómo estas métricas fluyen específicamente a través de las asignaciones una vez que un objeto está en el modelo.

**View the Model Diagram** — más allá de la vista de una sola tabla, el diagrama completo ("Modeled Metric view") muestra todos los objetos del modelo y sus conexiones — el mapa completo del flujo de costo organizacional.

### Create Allocations — el mecanismo central del producto

**Set Up Simple Allocations (One-to-One)** — distribuir costo de una tabla fuente a una tabla destino usando un atributo medible (headcount, conteo de servidores, metros cuadrados) — el patrón más común y la base de cualquier modelo más complejo.

**Configure Drivers for Allocations** — introduce la distinción central de todo el motor de asignación: **Unit Drivers** (definen cómo el valor entra a un objeto del modelo desde su tabla de datos subyacente) vs. otros tipos de driver que controlan cómo ese valor se distribuye hacia adelante.

**Create Multi-Tier Allocations** — el patrón TBM real, documentado explícitamente: la mayoría de las implementaciones usan **4 a 6 niveles** (Cost Source → Vendors → Technology Services → Applications → Business Units, el mismo ejemplo ya visto en Getting Started), no una asignación directa de un solo paso.

**Handle Unallocated Costs** — qué hacer cuando, después de correr las asignaciones, queda costo sin distribuir (típicamente porque las filas fuente no tienen match con ninguna fila destino, o un filtro excluyó ciertas filas). Documenta errores comunes como "Unable to Find Linked Keys".

**Allocation Troubleshooting Reference** — catálogo de mensajes de error con causa y solución, complementario al capítulo de Troubleshooting general del producto.

### Advanced Modeling — control fino sobre el motor de asignación

**Use Matching Logic for Allocations** — resuelve un problema de escalabilidad real: sin lógica de matching dinámico, asignar costo de data center solo a los servidores en ese mismo data center requeriría una línea de asignación separada por cada ubicación (SEA→SEA, NYC→NYC...). La lógica de matching relaciona columnas dinámicamente, eliminando esa duplicación. Pitfalls documentados: valores no coincidentes exactos (sensibles a mayúsculas/espacios), valores NULL que nunca hacen match, y advertencia explícita sobre "Legacy model join operation" — limpiar el checkbox de relación automática y configurar columnas explícitas.

**Configure Weighting Columns** — la fórmula exacta está documentada: `Allocation to Row = SOURCE × (Row's Weight / Total Weight of All Matching Rows)`. Comportamientos de borde importantes: si la columna de peso tiene **algún** valor no numérico, la ponderación se ignora por completo y el costo se distribuye parejo; si todos los pesos son cero, aplica la misma distribución pareja (vía la función Ratio); valores NULL no reciben asignación; y **pesos negativos están bloqueados por defecto** al poder producir resultados inesperados.

**Trace Cost Flows Through the Model** — responde "¿de dónde vino este costo?" usando tres vistas complementarias: Single Object Modeler (una tabla a la vez, configuración detallada), Diagram View (estructura completa del modelo), y una tercera vista de drill-down para navegación.

**Create Model Reports (Sankey Diagrams)** — visualización para comunicación con stakeholders: el ancho de cada línea es proporcional al valor que representa, haciendo visualmente evidente qué fuentes contribuyen más costo y cómo se divide ese costo al fluir por el modelo.

## Por qué importa en una conversación con el cliente

El patrón de 4-6 niveles documentado explícitamente es el mejor punto de referencia para calibrar expectativas de complejidad de modelo con un cliente nuevo — si su visión inicial es una asignación de un solo paso, vale la pena mostrarles desde el principio el patrón real de la industria.

La fórmula exacta de ponderación (y sus comportamientos de borde — no numéricos, ceros, NULLs, negativos) es exactamente el tipo de detalle técnico que evita sorpresas costosas durante una validación de modelo: un cliente que ve un resultado "parejo" inesperado probablemente tiene un valor no numérico oculto en su columna de peso, no un bug del producto.

Los diagramas Sankey son el activo de comunicación más fuerte para conversaciones ejecutivas — permiten mostrarle a un CFO, en una sola imagen, exactamente cómo se compone el costo total de un servicio, sin necesidad de que entienda la mecánica de asignación subyacente.

## Documentos fuente

- Model Basics (índice) — `kb/02-product-docs/apptio-tbm-studio/en/models-model-basics.md`
- Add a Table to the Model — `kb/02-product-docs/apptio-tbm-studio/en/basics-add-table-model.md`
- Understand Model Metrics (Cost, Budget, Forecast) — `kb/02-product-docs/apptio-tbm-studio/en/basics-understand-model-metrics-cost-budget-forecast.md`
- View the Model Diagram — `kb/02-product-docs/apptio-tbm-studio/en/basics-view-model-diagram.md`
- Create Allocations (índice) — `kb/02-product-docs/apptio-tbm-studio/en/models-create-allocations.md`
- Set Up Simple Allocations (One-to-One) — `kb/02-product-docs/apptio-tbm-studio/en/allocations-set-up-simple-one-one.md`
- Configure Drivers for Allocations — `kb/02-product-docs/apptio-tbm-studio/en/allocations-configure-drivers.md`
- Create Multi-Tier Allocations — `kb/02-product-docs/apptio-tbm-studio/en/allocations-create-multi-tier.md`
- Handle Unallocated Costs — `kb/02-product-docs/apptio-tbm-studio/en/allocations-handle-unallocated-costs.md`
- Allocation Troubleshooting Reference — `kb/02-product-docs/apptio-tbm-studio/en/allocations-allocation-troubleshooting-reference.md`
- Advanced Modeling (índice) — `kb/02-product-docs/apptio-tbm-studio/en/models-advanced-modeling.md`
- Use Matching Logic for Allocations — `kb/02-product-docs/apptio-tbm-studio/en/modeling-use-matching-logic-allocations.md`
- Configure Weighting Columns — `kb/02-product-docs/apptio-tbm-studio/en/modeling-configure-weighting-columns.md`
- Trace Cost Flows Through the Model — `kb/02-product-docs/apptio-tbm-studio/en/modeling-trace-cost-flows-through-model.md`
- Create Model Reports (Sankey Diagrams) — `kb/02-product-docs/apptio-tbm-studio/en/modeling-create-model-reports-sankey-diagrams.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
