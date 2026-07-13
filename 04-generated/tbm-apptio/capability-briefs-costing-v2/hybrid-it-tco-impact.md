---
concept: "Hybrid IT TCO Impact (comparación defendible del TCO antes/después de una migración de aplicación entre on-prem, nube privada y pública)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybrid-it-tco.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybrid-it-tco-config.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-anly.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-imp.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-sum.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-tco-imp-admin.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-over.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/hybrid-it-tco.md
last_updated: "2026-07-05"
---
# Hybrid IT TCO Impact — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Hybrid IT — una mezcla de on-premise, nube privada y nube pública — se ha vuelto el modelo operativo estándar, pero esa flexibilidad trae complejidad financiera real: cuando una aplicación se migra de un ambiente a otro, ¿cómo se demuestra de forma defendible si esa migración realmente ahorró dinero? La mayoría de los procesos de migración prometen ahorro en el caso de negocio inicial, pero rara vez existe un mecanismo sistemático para volver, meses después, y comparar el TCO real antes vs. después con la misma metodología.

## Cómo lo resuelve Apptio Costing Standard

### El mecanismo central: "congelar" el estado anterior antes de que desaparezca

El reto técnico fundamental que resuelve este módulo es que, una vez una aplicación se migra o se retira del modelo de costo, sus datos históricos de TCO dejan de generarse — no hay forma normal de comparar "cómo era antes" una vez que "antes" ya no existe en el sistema. La solución es un mecanismo de **congelamiento (freeze)**: cuando una aplicación marcada para migración llega al estado "Done" (tanto en estado de migración operativa como en estado de asignación Apptio), el sistema calcula y captura un promedio móvil de doce meses (Trailing Twelve Months) de TCO, volúmenes y costo unitario, y lo deposita permanentemente en tablas dedicadas (`Applications Migrated Raw`, `Applications Migrated CP Raw`, `Applications Migrated IT Raw`) vía un conector Apptio-to-Apptio Datalink. A partir de ahí, esa "fotografía congelada" se convierte en la fuente permanente de comparación "antes", independientemente de lo que pase después con el modelo de costo activo.

### Tres bancos de trabajo editables (Workbenches) que habilitan la captura de metadata sin tocar el modelo original

**Applications Workbench** — introduce el campo **Hosted On** (On-Prem, Private Cloud, Public Cloud), obligatorio para todas las aplicaciones, y usa el campo ya existente **Application Investment Objective** (con valor "Migrate" para las aplicaciones sujetas a migración).

**Application Migration Workbench** — tres tablas editables activas solo para aplicaciones marcadas como "Migrate": **Application Migration** (estrategia de migración — Rehost/Replatform/Repurchase/Refactor —, estado operativo y estado de asignación Apptio, mes/año de migración), **Application Migration Relationship** (ID de la aplicación destino — soportando escenarios 1-a-muchos, donde una aplicación migra hacia varias nuevas, con un peso de ponderación configurable y un **Application Migration Group ID** para agrupar comparaciones cuando el detalle individual no tiene sentido financiero), y **Application Migration Settings** (configuración de textos y tracking del reporte).

### Tres métricas modeladas nuevas, diseñadas explícitamente para no alterar el modelo de costo existente

**Cost Pre Migration** — pre-creada, sin configuración manual, expone el TCO mensual promedio "congelado" de la aplicación migrada.

**Cost Post Migration** — un modelo de costo **paralelo** al modelo principal, diseñado deliberadamente para no perturbarlo: vincula el objeto Applications (con los datos de la nueva aplicación destino) con el objeto Applications Migrated (los datos de la aplicación antigua), permitiendo comparar ambos sin modificar cómo se calcula el costo estándar del resto del portafolio.

**App Count Post Migration** — captura el conteo de aplicaciones destino, asegurando que el promedio de doce meses divida correctamente entre el número real de meses que la aplicación ha existido (una aplicación con solo 8 meses de vida no debe dividirse entre 12).

### Tres reportes, en niveles progresivos de profundidad (100 → 200 → 300)

**Nivel 100 — Summary**: snapshot de alto nivel del ambiente híbrido actual — TCO total, número de aplicaciones, costo promedio por aplicación, distribución porcentual entre on-prem/privada/pública, filtrable por criticidad de negocio, objetivo de inversión y familia de aplicación, comparado contra el estado objetivo. Dirigido a CIOs y C-Suite.

**Nivel 200 — Insights**: identifica cuántas aplicaciones migradas terminaron con TCO o costo unitario **más alto** que antes (el hallazgo que valida o refuta el caso de negocio de migración), con distribución por tipo de migración (On-Prem → Nube Pública, Nube Pública → Privada, etc.) y por estrategia de migración.

**Nivel 300 — Analysis**: el nivel más granular, a nivel de aplicación individual, mostrando exactamente qué cost pools (labor, activos fijos, vendors) y qué torres/sub-torres de TI están impulsando el cambio financiero — la vista de causa raíz para explicar por qué una migración específica funcionó o no.

Un **reporte Admin adicional** reemplaza el conector mensual manual con una interfaz de "copiar tabla" para trasladar valores del reporte a las tablas de entrada correspondientes.

### La advertencia operativa más importante: la ventana de comparación tiene fecha de caducidad

El propio producto advierte explícitamente: como el método es Trailing Twelve Months, **después de 12 meses la aplicación migrada deja de generar datos comparables** — la ventana de comparación "antes vs. después" tiene un horizonte máximo práctico de 12 meses. Esto es una limitación de diseño, no un error, y debe comunicarse con precisión en cualquier conversación de alcance.

## Por qué importa en una conversación con el cliente

Este módulo es el complemento natural, con datos reales, del reporte "Impact of Retiring Applications" ya visto en Business Units — mientras aquel proyecta ahorro potencial de retirar, este demuestra si una migración ya ejecutada realmente entregó el ahorro prometido. Juntos forman un ciclo completo: proyectar → ejecutar → validar.

El hallazgo de "aplicaciones con TCO más alto después de migrar" (Nivel 200) es, honestamente, uno de los datos más valiosos y potencialmente incómodos que este módulo puede producir — vale la pena posicionarlo con el cliente como una herramienta de honestidad radical sobre el éxito real de sus iniciativas de migración a nube, no solo como una vitrina de éxitos.

El límite de 12 meses de comparación es un detalle de alcance que se debe comunicar proactivamente antes de vender este módulo — un cliente que espera comparar migraciones de hace tres años se llevará una sorpresa si no se le explica esta restricción desde el principio.

La complejidad de configuración (tres componentes en orden específico, tres workbenches, tres métricas modeladas, y un conector Datalink Apptio-to-Apptio) hace de este un módulo con esfuerzo de implementación notablemente más alto que la mayoría de los ya documentados — apropiado como una fase avanzada de madurez, no como un quick win inicial.

## Documentos fuente

- Hybrid IT Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybrid-it-tco.md`
- Hybrid IT TCO Impact Configuration Guide — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybrid-it-tco-config.md`
- Hybrid IT TCO Impact - Analysis — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-anly.md`
- Hybrid IT TCO Impact – Insights — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-imp.md`
- Hybrid IT TCO Impact – Summary — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-it-sum.md`
- Hybrid IT TCO Impact – Admin — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hyb-tco-imp-admin.md`
- Hybrid IT TCO Impact Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-over.md`
- Hybrid IT TCO Impact Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-rep.md`
  - Summary: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-hybrid-it-tco-impact-summary
  - Insights: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-hybrid-it-tco-impact-insights
  - Analysis: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-hybrid-it-tco-impact-analysis
- Hybrid IT TCO Impact Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/hybitsol-gs.md`
- Hybrid IT TCO Impact Solution (guía de configuración detallada) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/hybrid-it-tco.md`

*Nota: las tres URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*