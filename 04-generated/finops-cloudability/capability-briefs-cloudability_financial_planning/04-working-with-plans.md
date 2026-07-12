---
tbm_concept: "Working with Plans (ciclo de vida completo: crear, editar forecast/presupuesto, y analizar desempeño con cinco reportes de varianza)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/plans-introduction.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-manage-your.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-finding-your-way-around-plan.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-creating.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-editing.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-making-forecast-adjustments.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-update-baseline-forecast.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-setting-budget-targets.md
  - kb/02-product-docs/apptio-financial-planning/en/plans-viewing-plan-status.md
  - kb/02-product-docs/apptio-financial-planning/en/performance-forecast-summary.md
  - kb/02-product-docs/apptio-financial-planning/en/performance-forecast-variance.md
  - kb/02-product-docs/apptio-financial-planning/en/performance-forecast-variance-details.md
  - kb/02-product-docs/apptio-financial-planning/en/performance-budget-variance.md
  - kb/02-product-docs/apptio-financial-planning/en/performance-budget-variance-details.md
last_updated: "2026-07-10"
---
# Working with Plans — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Este es el capítulo operativo central del producto: el ciclo de vida completo de un Plan, desde su creación hasta el análisis de varianza recurrente. Un Plan es, en esencia, un documento que contiene tanto un forecast como un presupuesto — con el forecast generado automáticamente a partir de actuals, y editable después.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Introduction to Plans — los dos componentes centrales.** El forecast inicial generado se llama **baseline forecast** (representa el gasto de run-rate actual proyectado hacia adelante), editable mediante ajustes y nuevas partidas de gasto — con los cambios de forecast **rastreados por separado**, permitiendo analizar gasto nuevo/modificado de forma independiente del gasto proyectado de run-rate. El baseline puede actualizarse (regenerarse) en cualquier momento. El **presupuesto** vive al mismo nivel de cost ownership que el forecast, permitiendo atar montos de presupuesto al forecast como límite de gasto — y puede modificarse independientemente del forecast, por usuarios distintos.

**Manage Your Plans — la página de listado, con cinco acciones de tabla.** Open Plan (habilitar edición), Close Plan (bloquear edición, solo lectura), Rename Plan (nombre único dentro de una view), Duplicate Plan, y Delete Plan (con confirmación). Los planes se filtran por View Selector — limpiar la selección de view muestra todos los planes del sistema.

**Finding your way around a Plan — estructura estandarizada de cuatro secciones**: Dashboard (analítica interactiva de desempeño actual), Forecast (ver/editar montos), Budget (ver/modificar objetivos), y Status (historial de cambios). Un filtro de Cost Ownership aplica a todas las secciones simultáneamente. El menú de Plan Actions incluye funciones restringidas a **Plan Owner**: Permissions (compartir el plan y gestionar acceso), Dimensions (modificar dimensiones del plan), Alerts (aún no disponible al momento de este documento), y Export Plan a CSV.

**Creating Plans — los parámetros de configuración inicial.** Nombre único dentro de la View; año fiscal y duración (1 a 3 años, empezando en el año fiscal actual o el siguiente); Cost Ownership (obligatoria, único uso permitido para segmentar líneas de presupuesto); Forecast Options (Cost Metric — cualquier métrica de costo disponible incluyendo métricas personalizadas basadas en costo; Excluded Spend — ninguno, solo créditos, solo cargos únicos, o ambos; Forecast Model — cuánto historial evaluar); y Dimensions adicionales ("what", elegidas de recomendadas o todas las disponibles de Cloudability).

**Editing Plans — tres flujos de edición documentados en detalle:**
- **Making forecast adjustments** — agregar una línea de ajuste requiere seleccionar valores de dimensión, incluyendo obligatoriamente cost ownership (limitado a los objetos con permiso de edición otorgado por el Plan Owner). Los montos pueden ingresarse como valor absoluto o como porcentaje del baseline (uno calcula el otro); ingresar un monto a nivel de período resumen (trimestre/año) lo distribuye equitativamente entre los períodos contenidos (ej. $12,000 en FY23 se distribuye como $1,000 en cada mes).
- **Update baseline forecast** — regenera el forecast usando los actuals más recientes y cualquier cambio a los parámetros de generación; los valores de baseline no son editables directamente (solo vía la pestaña Forecast). Solo Plan Owners pueden importar/exportar el baseline vía CSV.
- **Setting budget targets** — el presupuesto se puebla automáticamente con una línea por cada valor único de cost ownership. **Permiso de edición separado entre Budget Edit y Forecast Edit**, permitiendo que distintas personas fijen presupuesto vs. actualicen forecast — la implementación concreta de la segregación de funciones ya mencionada en Getting Started. Mismo comportamiento de entrada por monto/porcentaje y distribución equitativa en períodos resumen.

**Viewing Plan status** — vista del último estado de ajuste de cada objeto de costo y sus totales actuales, agrupable/ordenable/filtrable.

**Analyzing Plan Performance — cinco reportes, en dos pares simétricos (Forecast vs. Budget) más un resumen general:**
- **Forecast Summary** — KPIs de Forecast Total y Budget Total, tendencia de gasto en el tiempo, desglose por dimensión, y una tabla tipo pivote de Excel con drill-down.
- **Forecast Variance** — compara Forecast vs. Estimate (actual-a-la-fecha más estimado del resto del período). Fórmula: **Variance = Forecast − Estimate** (negativo indica que el gasto estimado supera al forecast). Granularidad ajustable (Current Month = diaria; Current Quarter/Year = mensual), con las 5 mayores varianzas por dimensión driver.
- **Forecast Variance Details** — desglose tabular período por período, con la misma fórmula de varianza, analizable con funcionalidad tipo pivote.
- **Budget Variance** — el mismo patrón que Forecast Variance, pero comparando **Budget vs. Forecast** en vez de Forecast vs. Estimate. Fórmula: **Variance = Budget − Forecast**.
- **Budget Variance Details** — desglose tabular de varianza de presupuesto, con fórmula **Variance = Budget − actuals/Forecast**.

## Por qué importa en una conversación con el cliente

La separación de permisos Budget Edit vs. Forecast Edit es el mecanismo concreto que hace operativa la segregación de funciones prometida en Getting Started — vale la pena mostrarla explícitamente en cualquier conversación con un cliente que tenga procesos FP&A formales donde presupuesto y forecast los manejan equipos o personas distintas.

Los cinco reportes de Analyzing Plan Performance son el mejor material de demo de todo el producto — en particular, la distinción entre Forecast Variance (real/estimado vs. lo planeado) y Budget Variance (lo planeado vs. lo aprobado) responde dos preguntas de negocio genuinamente distintas, y vale la pena explicar la diferencia con claridad antes de que el cliente las confunda.

El comportamiento de distribución equitativa al ingresar montos en períodos resumen (trimestre/año dividido en partes iguales entre meses) es un detalle operativo importante a comunicar antes de la primera sesión de edición en vivo — un usuario que espera una distribución no lineal (por ejemplo, estacional) se sorprenderá si no se le explica este comportamiento por defecto.

## Documentos fuente

- Introduction to Plans — `kb/02-product-docs/apptio-financial-planning/en/plans-introduction.md`
- Manage Your Plans — `kb/02-product-docs/apptio-financial-planning/en/plans-manage-your.md`
- Finding your way around a Plan — `kb/02-product-docs/apptio-financial-planning/en/plans-finding-your-way-around-plan.md`
- Creating Plans — `kb/02-product-docs/apptio-financial-planning/en/plans-creating.md`
- Editing Plans — `kb/02-product-docs/apptio-financial-planning/en/plans-editing.md`
- Making forecast adjustments — `kb/02-product-docs/apptio-financial-planning/en/plans-making-forecast-adjustments.md`
- Update baseline forecast — `kb/02-product-docs/apptio-financial-planning/en/plans-update-baseline-forecast.md`
- Setting budget targets — `kb/02-product-docs/apptio-financial-planning/en/plans-setting-budget-targets.md`
- Viewing Plan status — `kb/02-product-docs/apptio-financial-planning/en/plans-viewing-plan-status.md`
- Forecast Summary — `kb/02-product-docs/apptio-financial-planning/en/performance-forecast-summary.md`
- Forecast Variance — `kb/02-product-docs/apptio-financial-planning/en/performance-forecast-variance.md`
- Forecast Variance Details — `kb/02-product-docs/apptio-financial-planning/en/performance-forecast-variance-details.md`
- Budget Variance — `kb/02-product-docs/apptio-financial-planning/en/performance-budget-variance.md`
- Budget Variance Details — `kb/02-product-docs/apptio-financial-planning/en/performance-budget-variance-details.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
