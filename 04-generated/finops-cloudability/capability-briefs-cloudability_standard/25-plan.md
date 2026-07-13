---
concept: "Plan (presupuestos y forecasting inteligente de gasto de nube, y planeación de arquitectura de workload)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/budgets-forecasts.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-current-month.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-forecast.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-budgets.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-enhanced-forecast.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-intelligent-forecasting.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-get-recommendations-workload-planning.md
  - kb/02-product-docs/apptio-cloudability-standard/en/plan-workload-planning-preferences.md
last_updated: "2026-07-09"
---
# Plan — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Entender el gasto pasado (Insights) y optimizar el presente (Optimize) no responde la pregunta hacia adelante: ¿cuánto vamos a gastar, y cómo lo presupuestamos con confianza? Plan es el módulo de proyección financiera de Cloudability, con un motor de forecasting propio y una capa de planeación de arquitectura de workload.

## Cómo lo resuelve IBM Cloudability Standard

**Current Month — Spending Drivers.** Usa los parámetros Service Name y Usage Family para identificar qué está impulsando cualquier cambio de gasto, visible tanto por mayor gasto absoluto como por mayor cambio relativo al mes anterior — con conceptos misceláneos agrupados bajo "Other" para no saturar la vista.

**Forecast — patrones históricos con inspección de causa raíz.** Muestra patrones de gasto histórico e inspecciona los cambios subyacentes que impulsan el gasto proyectado, ayudando a entender qué se espera que cambie — y sirve como base para crear presupuestos adicionales.

**Budgets — con cuatro bases de costo seleccionables, cada una recomendada para un perfil de cliente distinto.** Los presupuestos se definen a nivel de View (permitiendo trackear unidades de negocio de forma independiente) y están atados a una base de costo específica: **Cash** (la más común, punto de partida por defecto), **Amortized** (recomendada si la organización compra muchas RIs parcial o totalmente prepagadas, para ver la tendencia real de gasto), y **Adjusted / Adjusted Amortized** (si el cliente tiene Custom Pricing calibrado en Cloudability).

**Enhanced Forecast — el motor de pronóstico avanzado, con control de modelo por línea.** Usa Intelligent Forecasting para generar pronósticos desde datos históricos reales, permitiendo comparar modelos de pronóstico, revisar su precisión, y ajustar la selección de modelo para líneas individuales del pronóstico — mejorando precisión y dando control granular cuando se necesita.

**Intelligent Forecasting — el motor subyacente, documentado con su lógica de selección de modelo.** Evalúa múltiples modelos de pronóstico para identificar cuál se ajusta mejor a cada serie de tiempo histórica — diseñados para capturar comportamientos distintos (valores estables, crecimiento/declive lineal, patrones estacionales repetitivos, cambios de variabilidad en el tiempo). Principio documentado explícitamente: **la precisión del pronóstico generalmente mejora con más datos históricos disponibles**, porque el motor puede identificar mejor patrones estacionales recurrentes y tendencias de largo plazo.

**Workload Planning — optimización de arquitectura, no solo de gasto.** Ayuda a optimizar la arquitectura de workload y mejorar la precisión de planeación financiera a través de múltiples proveedores de nube, con recomendaciones generadas específicamente para este propósito.

**Workload Planning Preferences — gobernanza centralizada de las opciones de planeación.** Permite a los equipos FinOps definir y restringir centralmente las opciones disponibles en Workload Planning — visible por defecto solo para el rol Workload Planning Admin, con un permiso separado (`WorkloadPlanningPreferencesViewOnly`) asignable a roles personalizados para dar visibilidad sin permiso de edición.

## Por qué importa en una conversación con el cliente

La elección de base de costo para presupuestos (Cash vs. Amortized vs. Adjusted) es una decisión de discovery importante que depende directamente del perfil de compra de compromisos del cliente — vale la pena preguntar explícitamente qué tan comprometido está el cliente en RIs prepagadas antes de recomendar la base de costo por defecto (Cash), ya que puede distorsionar la tendencia de gasto real percibida.

El principio de que la precisión del pronóstico mejora con más historia disponible es un argumento importante de gestión de expectativas para cualquier cliente nuevo en Cloudability — un pronóstico generado con solo 1-2 meses de datos será menos confiable que uno con 12+ meses, y vale la pena comunicarlo antes de que el cliente confíe plenamente en un forecast temprano.

Workload Planning Preferences con gobernanza centralizada es relevante para conversaciones con clientes que tienen múltiples equipos usando Workload Planning de forma descentralizada — permite a FinOps establecer restricciones organizacionales sin necesariamente revisar cada plan individual.

## Documentos fuente

- Budgets and Forecasts (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/budgets-forecasts.md`
- Current Month — `kb/02-product-docs/apptio-cloudability-standard/en/plan-current-month.md`
- Forecast — `kb/02-product-docs/apptio-cloudability-standard/en/plan-forecast.md`
- Budgets — `kb/02-product-docs/apptio-cloudability-standard/en/plan-budgets.md`
- Enhanced Forecast — `kb/02-product-docs/apptio-cloudability-standard/en/plan-enhanced-forecast.md`
- Intelligent Forecasting — `kb/02-product-docs/apptio-cloudability-standard/en/plan-intelligent-forecasting.md`
- Get Recommendations for Workload Planning — `kb/02-product-docs/apptio-cloudability-standard/en/plan-get-recommendations-workload-planning.md`
- Workload Planning Preferences — `kb/02-product-docs/apptio-cloudability-standard/en/plan-workload-planning-preferences.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
