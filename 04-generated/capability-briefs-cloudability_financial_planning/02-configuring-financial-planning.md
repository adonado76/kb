---
tbm_concept: "Configuring Cloudability Financial Planning (relación con Views, consideraciones de dimensión, y el rol central de la dimensión de cost ownership)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/planning-introduction.md
  - kb/02-product-docs/apptio-financial-planning/en/planning-view-considerations.md
  - kb/02-product-docs/apptio-financial-planning/en/planning-dimension-considerations.md
  - kb/02-product-docs/apptio-financial-planning/en/planning-cost-ownership.md
last_updated: "2026-07-10"
---
# Configuring Cloudability Financial Planning — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Financial Planning se integra sin fricción con la configuración ya existente de Cloudability — pero hay tres decisiones de diseño conceptual que hay que entender antes de crear el primer plan: cómo se relaciona con las Views, cuántas dimensiones incluir, y por qué la dimensión de cost ownership es obligatoria y central a todo el modelo.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Integración de prerequisito**: si el cliente ya puede reportar gasto real (actuals) usando dimensiones y views configuradas en Cloudability, puede crear planes directamente con esas mismas dimensiones — sin trabajo adicional. Sin embargo, las dimensiones/views diseñadas para reporte de gasto de nube pueden no ser suficientes para un proceso consolidado de presupuesto y forecast recurrente, ameritando views/dimensiones adicionales específicas de planeación.

**View Considerations — la distinción arquitectónica más importante del capítulo: un Plan es una fotografía estática, no un reporte vivo.** Al crear un plan, Financial Planning genera un forecast inicial resumiendo actuals según las dimensiones especificadas, y **guarda ese resultado dentro del plan** para edición posterior. A diferencia de un reporte (donde cambiar la view dispara una nueva consulta y resumen de actuals), **cambiar la view de un plan invalida todos los montos y ediciones previamente guardados** — un plan queda intrínsecamente ligado a la view en la que se creó, igual que los budgets clásicos de Cloudability. Recomendación explícita: crear el plan dentro de una view que abarque todo el gasto que se pretende presupuestar, o usar la dimensión de cost ownership como alternativa a depender exclusivamente de views para segmentar costo.

**Dimension Considerations — el trade-off explícito entre granularidad y usabilidad.** Cada combinación única de valores de dimensión genera una línea de forecast — más dimensiones significa mayor granularidad, pero también más líneas para que los dueños de costo revisen y actualicen. Financial Planning documenta tres casos de uso arquetípicos con necesidades de dimensión distintas: un usuario individual analizando su forecast generado, un dueño de finanzas haciendo análisis what-if sobre un segmento de gasto de nube, y la creación de un forecast anual consolidado compartido entre múltiples dueños de costo para el ciclo de presupuesto anual.

**Dos categorías de dimensión, con límites numéricos explícitos:**
- **Dimensión "who" (cost ownership)** — obligatoria, representa accountability (unidad de negocio, cuenta/suscripción, equipo de producto/app). Un forecast simple puede tener solo una dimensión, y debe ser esta.
- **Dimensiones "what"** — qué se está pronosticando (aplicación, workload, proyecto, proveedor de nube, servicio) — pueden ser múltiples.
- **Límites**: hasta **4 dimensiones de Cloudability** (vinculadas directamente a actuals, usadas para resumir gasto real en líneas de forecast y comparar actual vs. plan) más hasta **20 dimensiones exclusivas del plan** (capturan detalle adicional — drivers o explicaciones de cambios — pero no se pueden comparar contra actuals, ya que solo existen dentro del plan).

**Cost Ownership — la dimensión obligatoria que gobierna segmentación, edición compartida, y granularidad de presupuesto.** Todo plan debe incluir una dimensión de cost ownership, y debe ser una dimensión de Cloudability (no una dimensión exclusiva del plan). Su rol central: divide el plan en segmentos de propiedad distintos, controlando qué puede editar cada usuario cuando el plan se comparte entre múltiples personas — por ejemplo, con cost ownership = "Account", cada usuario asignado a una cuenta específica solo puede modificar las líneas de forecast de su cuenta, filtrando el plan para ver solo "sus" costos. Adicionalmente, **la dimensión de cost ownership determina el nivel de detalle del presupuesto dentro del plan**: cada valor de cost ownership corresponde a exactamente una línea de presupuesto.

## Por qué importa en una conversación con el cliente

La advertencia de que cambiar la view de un plan invalida todo el trabajo previamente guardado es el detalle de diseño más crítico a comunicar antes de que cualquier cliente cree su primer plan de producción — un cambio de view aparentemente inocuo puede destruir semanas de trabajo de edición colaborativa de forecast si no se anticipa.

El trade-off granularidad vs. usabilidad, con los tres casos de uso arquetípicos documentados, es un excelente marco de discovery: preguntarle al cliente en cuál de los tres se reconoce (análisis individual, what-if de finanzas, forecast consolidado anual) determina directamente cuántas dimensiones recomendar y cómo diseñar la estructura del plan.

La elección de la dimensión de cost ownership correcta es, literalmente, la decisión de diseño más importante de cualquier implementación de Financial Planning — determina simultáneamente cómo se reparte el trabajo de edición colaborativa y el nivel de detalle del presupuesto resultante, y vale la pena dedicarle tiempo explícito de discovery antes de crear cualquier plan piloto.

## Documentos fuente

- Introduction — `kb/02-product-docs/apptio-financial-planning/en/planning-introduction.md`
- View Considerations — `kb/02-product-docs/apptio-financial-planning/en/planning-view-considerations.md`
- Dimension Considerations — `kb/02-product-docs/apptio-financial-planning/en/planning-dimension-considerations.md`
- Cost Ownership — `kb/02-product-docs/apptio-financial-planning/en/planning-cost-ownership.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
