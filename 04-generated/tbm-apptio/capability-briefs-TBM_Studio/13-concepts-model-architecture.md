---
concept: "Concepts: Model Architecture — objetos del modelo, métricas modeladas vs. calculadas, el motor de asignación con sus cinco tipos, orden de procesamiento, y trazabilidad/validación"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-model-concepts-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-model-objects-relationships.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-metrics-modeled-vs-calculated.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-allocation-engine.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-allocation-order-processing.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-unallocated-costs.md
  - kb/02-product-docs/apptio-tbm-studio/en/architecture-model-validation-tracing.md
last_updated: "2026-07-07"
---
# Concepts: Model Architecture — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Este capítulo es la arquitectura formal detrás de todo lo ya visto operativamente en "How-To: Build Cost Models" — qué es realmente un objeto del modelo, cómo se distinguen las métricas que participan en el motor de asignación de las que no, los cinco tipos de asignación disponibles, y cómo el sistema determina automáticamente el orden de ejecución en un modelo multi-nivel.

## Cómo lo resuelve Apptio TBM Studio

**Qué es un modelo de costo, en su definición más simple**: responde "¿cómo distribuimos justamente costos compartidos hacia las personas y servicios que realmente los usan?" — con el ejemplo canónico de un data center de $2M/año usado por seis unidades de negocio, cuyo costo se reparte según servidores usados, almacenamiento consumido, u otro driver que refleje consumo real.

**Las tres analogías de "cocina" para los tres estudios**: Data Studio es la despensa (ingredientes crudos, organizados y listos); Model Studio es la receta (reglas para combinar ingredientes en un producto terminado); Report Studio (implícito) sería el plato servido.

**Model Object — el bloque de construcción fundamental.** Un contenedor que aloja datos de costo en un nivel particular de la estructura organizacional. Cada objeto del modelo está respaldado por una transform table de Data Studio — agregar un paso "Model" al pipeline de una tabla es lo que la convierte en objeto del modelo. Tres roles de objeto por tipo: **Source Objects** (donde el costo se origina — Cost Source, GL Actuals, en la base del modelo), **Intermediate Objects** (puntos de paso o categorización — Vendors, Labor, IT Towers, Technology Services), y (implícito por el patrón ya visto) objetos finales de consumo — Business Units.

**Relaciones entre objetos, con reglas explícitas**: el costo siempre fluye de "From" a "To" — el grafo del modelo **no puede contener ciclos** (dependencias circulares); un objeto fuente puede asignar simultáneamente a múltiples objetos destino (uno-a-muchos); múltiples objetos fuente pueden asignar hacia el mismo destino (muchos-a-uno).

**Modeled Metrics vs. Calculated Metrics — la distinción arquitectónica más importante del motor.** Una métrica modelada es un valor numérico central que participa **directamente** en el motor de asignación (Cost — el default en todo proyecto —, Budget, Forecast); cuando el costo se asigna de un objeto a otro, las métricas modeladas son los valores que se distribuyen. Una métrica calculada se deriva de una fórmula que referencia métricas modeladas, columnas de tabla, u otras métricas calculadas — **no participa en el motor de asignación**, se computa en el momento del reporte. Guía de decisión explícita: dato crudo que debe fluir por asignaciones → métrica modelada; combinación matemática de otras métricas → métrica calculada.

**El motor de asignación, en su mecánica fundamental**: el *driver* determina las proporciones, la fuente provee el monto total, el destino recibe su porción — el mecanismo detrás de cada asignación en TBM Studio.

**Cinco tipos de asignación, cada uno para un escenario distinto:**
- **Weighted Value** — el más común: distribuye proporcionalmente según la razón de valores en una columna de la tabla destino (baja complejidad).
- **Consumption** — distribuye según la razón de unidades consumidas a capacidad disponible; ideal para modelar uso real de servicios de TI (complejidad media).
- **Standard Value** — mapeo directo: distribuye un valor igual al que ya existe en la tabla destino (baja complejidad).
- **Formula** — control total vía fórmula personalizada que determina cómo cada fila destino recibe su porción.
- **Recursion** — maneja escenarios donde el costo circula entre servicios interconectados (ej. servicios de TI que se dan soporte mutuo, además de soportar unidades de negocio) — el único tipo diseñado explícitamente para relaciones no estrictamente jerárquicas.

**Allocation Order and Processing — secuenciación automática basada en dependencias.** En un modelo multi-nivel, las asignaciones no ejecutan simultáneamente — el orden determina el resultado final, porque las asignaciones posteriores dependen de la salida de las anteriores (Cost Source → Vendors debe completarse antes de que Vendors → Business Units tenga costo que distribuir). TBM Studio determina el orden automáticamente analizando el grafo de dependencias del modelo: **las asignaciones de un objeto ejecutan solo después de que todas las asignaciones entrantes a ese objeto hayan completado**.

**Unallocated Costs y Model Validation and Tracing** — el manejo formal de costo sin distribuir (ya visto operativamente en el capítulo de How-To) y las herramientas de trazabilidad/validación para confirmar que el modelo calcula correctamente antes de confiar en sus resultados.

## Por qué importa en una conversación con el cliente

La regla de que el grafo del modelo **no puede contener ciclos** es una restricción de diseño fundamental a comunicar temprano — un cliente que describe un escenario donde "A financia a B y B a veces financia de vuelta a A" necesita el tipo de asignación **Recursion** específicamente, no una asignación estándar, y vale la pena identificar esto en el discovery de arquitectura del modelo.

Los cinco tipos de asignación con su tabla de "mejor para / complejidad" son la herramienta de diagnóstico correcta en cualquier sesión de diseño de modelo — en lugar de usar Formula (máxima flexibilidad, máxima complejidad) por defecto, vale la pena confirmar si Weighted Value o Consumption ya resuelven el escenario con mucho menos esfuerzo de mantenimiento.

La secuenciación automática por dependencias es un argumento de confiabilidad técnica importante: el cliente no necesita definir manualmente en qué orden se ejecutan decenas de asignaciones en un modelo de 4-6 niveles — el sistema lo determina analizando el grafo, reduciendo el riesgo de error humano de secuenciación.

## Documentos fuente

- Model Concepts Overview — `kb/02-product-docs/apptio-tbm-studio/en/architecture-model-concepts-overview.md`
- Model Objects and Relationships — `kb/02-product-docs/apptio-tbm-studio/en/architecture-model-objects-relationships.md`
- Metrics: Modeled vs. Calculated — `kb/02-product-docs/apptio-tbm-studio/en/architecture-metrics-modeled-vs-calculated.md`
- The Allocation Engine — `kb/02-product-docs/apptio-tbm-studio/en/architecture-allocation-engine.md`
- Allocation Order and Processing — `kb/02-product-docs/apptio-tbm-studio/en/architecture-allocation-order-processing.md`
- Unallocated Costs — `kb/02-product-docs/apptio-tbm-studio/en/architecture-unallocated-costs.md`
- Model Validation and Tracing — `kb/02-product-docs/apptio-tbm-studio/en/architecture-model-validation-tracing.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
