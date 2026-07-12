---
tbm_concept: "Getting Started (posicionamiento de Financial Planning, diferencia frente a Budgets/Forecasts clásico, acceso, y primeros pasos por rol)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/started-what-you-can-do-cloudability-financial-planning.md
  - kb/02-product-docs/apptio-financial-planning/en/gs-how-is-cloudability-financial-planning-different-from-existing-cloudability-budgets-forecasts.md
  - kb/02-product-docs/apptio-financial-planning/en/started-how-access-cloudability-financial-planning.md
  - kb/02-product-docs/apptio-financial-planning/en/started-first-steps-planning-users.md
  - kb/02-product-docs/apptio-financial-planning/en/started-first-steps-planning-process-administrators.md
last_updated: "2026-07-10"
---
# Getting Started — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Cloudability Financial Planning introduce un concepto nuevo — **"Plans"** — que unifica en un solo documento dos cosas que tradicionalmente viven separadas: lo que la organización planea gastar (forecast) y lo que está aprobada a gastar (budget). Es un módulo distinto y más sofisticado que el "Budgets and Forecasts" clásico de Cloudability ya documentado en el capítulo Plan de Cloudability Standard.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Seis capacidades centrales, documentadas explícitamente**: crear planes con forecast generado automáticamente a partir del análisis de patrones de gasto histórico, ajustar agregando nuevas partidas de gasto y cambios; compartir planes con otros usuarios para recolectar y consolidar sus aportes; rastrear cambios y correr un flujo de aprobación; analizar planes con analítica integrada; monitorear desempeño de gasto real vs. plan, con drill-down a los drivers de varianza; y configurar alertas de plan para notificar proactivamente cuando el gasto supera o se proyecta que superará umbrales definidos.

**La diferencia clave frente al Budgets and Forecasts clásico — el forecast dentro de un Plan es editable.** A diferencia de los forecasts tradicionales de Cloudability, el forecast generado automáticamente al crear un Plan puede modificarse directamente, con control completo sobre nivel de granularidad y detalle (dimensiones y períodos de tiempo a elección). Los planes también pueden **segmentarse por cost ownership** y compartirse con otros usuarios para planeación colaborativa — diseñado explícitamente para optimizar procesos de planeación financiera esenciales: presupuesto anual, análisis de varianza mensual, y actualizaciones de forecast recurrentes.

**Flujo de aprobación con separación de responsabilidades** — se pueden asignar usuarios distintos para establecer montos de presupuesto vs. usuarios responsables de proveer actualizaciones de forecast, facilitando procesos de revisión y aprobación con segregación de funciones real.

**Acceso vía el menú Plan** de la navegación de Cloudability, con un rol diferenciado explícito: **Plan Administrators** (usuarios con permisos Cloudability Admin o Cloudability Planning Admin) tienen acceso adicional para configurar dimensiones recomendadas que otros usuarios usarán al crear Planes — funcionalidad disponible bajo Plan Dimensions, en el menú Organize.

**Dos rutas de primeros pasos, por rol:**
- **Planning Users** (contribuyentes en procesos de presupuesto anual y actualización regular de forecast) — aprender a crear y trabajar con planes, actualizar presupuestos, usar la analítica integrada (resumen de forecast, seguimiento de desempeño de gasto, análisis de detalle de varianza), y reporting self-service.
- **Planning and Process Administrators** — el documento de primeros pasos específico para este rol (contenido no capturado en el extracto disponible, pero estructuralmente paralelo al de usuarios).

## Por qué importa en una conversación con el cliente

La distinción "forecast editable dentro de un Plan" vs. "forecast de solo lectura del módulo Budgets and Forecasts clásico" es la pregunta de posicionamiento más importante frente a cualquier cliente que ya use Cloudability Standard — vale la pena aclarar explícitamente que Financial Planning es un módulo complementario más sofisticado, no un reemplazo directo, y ayudar al cliente a decidir cuál necesita según la madurez de su proceso de presupuesto.

La separación de responsabilidades entre quien fija montos de presupuesto y quien actualiza forecasts es un argumento de gobernanza financiera relevante para cualquier cliente con procesos de aprobación FP&A formales — vale la pena posicionarlo como una capacidad de control interno, no solo de conveniencia operativa.

El caso de uso explícito de "presupuesto anual + análisis de varianza mensual + actualización de forecast recurrente" es el ciclo de vida completo de FinOps de planeación — útil como marco de discovery para entender en qué etapa de ese ciclo se encuentra hoy el cliente, y qué parte automatizar primero.

## Documentos fuente

- What you can do with Cloudability Financial Planning — `kb/02-product-docs/apptio-financial-planning/en/started-what-you-can-do-cloudability-financial-planning.md`
- How is Cloudability Financial Planning different from existing Cloudability Budgets and Forecasts — `kb/02-product-docs/apptio-financial-planning/en/gs-how-is-cloudability-financial-planning-different-from-existing-cloudability-budgets-forecasts.md`
- How to access Cloudability Financial Planning — `kb/02-product-docs/apptio-financial-planning/en/started-how-access-cloudability-financial-planning.md`
- First Steps for Planning Users — `kb/02-product-docs/apptio-financial-planning/en/started-first-steps-planning-users.md`
- First steps for Planning and Process Administrators — `kb/02-product-docs/apptio-financial-planning/en/started-first-steps-planning-process-administrators.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
