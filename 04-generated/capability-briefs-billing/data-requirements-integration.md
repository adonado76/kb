---
tbm_concept: "Data Requirements and Integration (fundamentos de datos compartidos, requisitos por edición, calidad, calendarios, FX, mecanismos de integración)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-billing
status: draft
generated_from:
  - kb/02-product-docs/apptio-billing-standard/en/integration-shared-data-foundations.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-data-requirements-billing-essentials.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-data-requirements-billing-standard.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-data-quality-expectations.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-calendars-periods.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-currencies-fx.md
  - kb/02-product-docs/apptio-billing-standard/en/integration-mechanisms-non-studio-options.md
last_updated: "2026-07-06"
---
# Data Requirements and Integration — Cómo Apptio Billing Aborda Esta Capacidad

## El concepto

Billing no genera sus propios datos de costo desde cero — los hereda de Costing. Antes de configurar cualquier componente de Billing, hay que responder preguntas de fondo sobre esa relación de datos: ¿qué tan alineado está el calendario fiscal entre ambos productos?, ¿qué pasa si hay múltiples monedas?, ¿qué nivel de completitud de datos es aceptable antes de calcular un cargo que un consumidor real va a cuestionar?

## Cómo lo resuelve Apptio Billing

**Fundamentos de datos compartidos.** Billing y Costing comparten una base de datos de referencia — la misma disciplina de reutilizar taxonomía y estructura ya vista en la relación Planning-Costing (vía Cost Transparency Integration/ADM). Este documento establece qué se comparte y qué es específico de Billing.

**Requisitos de datos, documentados por separado para cada edición** — otra vez, la distinción Essentials/Standard determina el nivel de detalle de datos necesario: Essentials requiere un conjunto más acotado (probablemente centrado en el catálogo de ofertas y datos de consumo agregados), mientras Standard requiere datos más granulares para soportar su lógica de precio y varianza más sofisticada.

**Expectativas de calidad de datos**, un concepto ya visto en Costing Standard (Data Quality Reports) pero aquí con una urgencia distinta: en Costing, datos incompletos generan un reporte de costo potencialmente impreciso; en Billing, datos incompletos generan **un cargo real hacia un consumidor de negocio** — el margen de error tolerable es, en la práctica, menor.

**Calendarios y períodos.** Billing necesita una noción consistente de períodos (mensual, alineado a calendario fiscal), y cada registro en las tablas de consumo y tarifa debe referenciar un identificador de período — con consideraciones explícitas de diseño para períodos parciales o eventos de cutover (por ejemplo, un go-live a mitad de mes), documentando cómo tratar esos casos: períodos divididos, ajustes de una sola vez, o tarifas/unidades prorrateadas. La recomendación explícita: si Costing ya usa un calendario fiscal, Billing debe reutilizar la misma estructura para evitar trabajo de reconciliación innecesario.

**Monedas y FX.** Relevante para cualquier organización multi-país — Billing necesita saber en qué moneda se factura cada consumidor y cómo se maneja la conversión cuando el costo subyacente está en una moneda distinta a la de facturación.

**Mecanismos de integración y opciones sin Studio.** Documenta las vías por las cuales los datos fluyen hacia Billing — incluyendo, explícitamente, opciones que no dependen de TBM Studio (el ambiente de modelado tradicional de Apptio), lo cual sugiere caminos de integración más ligeros o vía API/carga directa para organizaciones que no quieren o no pueden operar dentro del ambiente completo de Studio.

## Por qué importa en una conversación con el cliente

La recomendación de reutilizar el calendario fiscal de Costing en Billing es un detalle concreto y accionable de discovery temprano — preguntarlo en la primera sesión técnica evita descubrir, meses después, que ambos productos están reconciliando calendarios distintos.

El tratamiento de períodos parciales/cutover es especialmente relevante para cualquier conversación de Go-Live (cubierta en detalle en el Capítulo 14) — un go-live a mitad de mes es la norma, no la excepción, y vale la pena tener ya definida la estrategia de prorrateo antes de llegar a esa fase del proyecto.

Las expectativas de calidad de datos, más estrictas que en Costing dado que aquí el resultado es un cargo real, son un buen argumento para insistir en una fase de validación de datos robusta antes del primer ciclo de facturación en producción — mejor detectar un problema de datos en un ambiente de prueba que en la primera factura real que ve un consumidor de negocio.

## Documentos fuente

- Shared data foundations — `kb/02-product-docs/apptio-billing-standard/en/integration-shared-data-foundations.md`
- Data requirements for Billing Essentials — `kb/02-product-docs/apptio-billing-standard/en/integration-data-requirements-billing-essentials.md`
- Data requirements for Billing Standard — `kb/02-product-docs/apptio-billing-standard/en/integration-data-requirements-billing-standard.md`
- Data quality expectations — `kb/02-product-docs/apptio-billing-standard/en/integration-data-quality-expectations.md`
- Calendars and periods — `kb/02-product-docs/apptio-billing-standard/en/integration-calendars-periods.md`
- Currencies and FX — `kb/02-product-docs/apptio-billing-standard/en/integration-currencies-fx.md`
- Integration mechanisms and non-Studio options — `kb/02-product-docs/apptio-billing-standard/en/integration-mechanisms-non-studio-options.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*