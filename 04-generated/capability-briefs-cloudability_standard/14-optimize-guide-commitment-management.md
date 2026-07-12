---
tbm_concept: "Optimize — Guide to Commitment Management (alineación organizacional, portfolio histórico, recomendaciones de compra, preferencias, y alertas de compromisos de nube)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-guide-commitment-management.md
  - kb/02-product-docs/apptio-cloudability-standard/en/gcm-using-commitment-manager-overview-align-organization-commitment-strategy.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-guide-legacy-commitment-manager.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-portfolio-understand-historical-performance.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-recommendations-analyze-savings-opportunities.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-preferences-build-business-case.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-setting-commitment-alerts.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-data-freshness.md
  - kb/02-product-docs/apptio-cloudability-standard/en/management-guide-commitment-faq.md
last_updated: "2026-07-09"
---
# Optimize — Guide to Commitment Management — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Los compromisos de nube (Reserved Instances, Savings Plans, Committed Use Discounts) son la palanca de ahorro más grande y más arriesgada del gasto de nube: bien gestionados, generan descuentos sustanciales; mal gestionados (sobrecompra, expiración sin renovación, baja utilización), generan gasto hundido. Esta guía es el manual operativo completo del ciclo de vida de gestión de compromisos en Cloudability — desde alinear a la organización hasta configurar alertas automáticas.

## Cómo lo resuelve IBM Cloudability Standard

**Commitment Manager Overview — la capa de orientación cross-servicio, cross-vendor.** Combina postura actual (desempeño histórico) y oportunidad futura (recomendaciones modeladas) en una sola vista. Configuración rica: selector de tipo de servicio (multi-select, analiza solo uso "committable"), selector de cuenta jerárquico (payer vs. linked accounts, con estado de selección parcial), y un **período de análisis que permite seleccionar hacia el futuro** — el mes actual se considera "forecast" si aún no ha completado todos sus días. Tres tipos de KPI configurables: Standard (compara dos momentos en el tiempo), Total (agrega todo el período), Average (promedio en el período), cada uno con granularidad semanal o mensual y comparación absoluta/porcentual opcional.

**Guide to Legacy Commitment Manager — la vista operativa clásica.** Requiere credenciales con permisos específicos verificables en Settings → Vendor Credentials (indicador visual verde/rojo bajo "Advanced Features"). El gráfico principal usa una línea roja vertical que separa uso histórico (izquierda) de uso proyectado (derecha), con área verde para cobertura por compromiso y azul para uso on-demand — y un slider para alternar entre vista de costo y vista de "Apply Recommendations".

**Commitment Portfolio — el sistema de registro del desempeño histórico**, con la métrica más importante de todo este capítulo documentada como fórmula exacta:
> **Portfolio Savings Rate (PSR) = Commitment Net Savings ÷ Committable Spend**

PSR aísla el efecto del descuento por compromiso de la tarifa negociada on-demand, siendo una métrica de portafolio más limpia que Effective Savings Rate (ESR) cuando hay tarifas negociadas en juego — cuando la base de costo es "List", PSR y ESR son idénticas. GCP tiene una arquitectura de reporte particular (dos vistas complementarias: Grouped y Ungrouped) porque sus créditos no siempre traen un ID de compromiso por uso individual.

**Commitment Recommendations — el motor de recomendación de compra, con tres métodos de ajuste documentados explícitamente:**
- **Commitment Amount** — especifica un monto a comprometer, y el modelo estima el resultado esperado.
- **Coverage Percentage** — especifica un porcentaje de cobertura objetivo, y el modelo estima qué compra lo lograría.
- **Minimum Sustained Usage** — cubre todo el uso sostenido, con opción de omitir hasta 5% de horas atípicas.

Tres niveles de recomendación (Optimal, Target, Custom) permiten alinear la decisión al apetito de riesgo de la organización — si Optimal excede materialmente a Target, es una señal explícita de que se está dejando ahorro sobre la mesa.

**Commitment Preferences — configuración de dimensiones de análisis (soporte GCP).** Hasta 10 dimensiones de Cloudability (Tags & Labels, Business Mappings, Account Groups) configurables para segmentar recomendaciones — con una restricción de performance documentada explícitamente: dimensiones de alta variabilidad (ej. nombre de recurso) degradan significativamente el rendimiento y se excluyen automáticamente del listado disponible.

**Commitment Alerts — dos tipos, con matices por proveedor.** Expiration (compromisos por vencer en una ventana configurable) y Utilization Threshold (compromisos con utilización bajo un umbral). Detalle operativo importante: los alertas evalúan **todo el portafolio**, no solo la pestaña de vendor activa al momento de configurarlos. Azure Savings Plans no soporta lookback de 90 días (máximo 30); GCP solo puede evaluar utilización a nivel de grupo de compromiso, no por compromiso individual.

## Por qué importa en una conversación con el cliente

La fórmula de PSR es el KPI correcto para cualquier conversación ejecutiva sobre el ROI real del programa de compromisos de un cliente — aísla el efecto del descuento por compromiso, evitando que una tarifa negociada favorable oculte artificialmente el verdadero impacto de las RIs/Savings Plans.

El FAQ documenta un problema operativo real y su solución concreta: una cuenta de facturación consolidada no puede ver compromisos comprados por una cuenta hija **antes** de entrar en la relación de facturación consolidada — la solución (agregar credencial IAM de la cuenta hija además de la cuenta padre) es exactamente el tipo de detalle técnico que evita una conversación de "faltan compromisos en mi portfolio" sin explicación clara.

La recomendación explícita de "compras pequeñas y frecuentes hasta alcanzar la cobertura deseada" (en vez de actuar directamente sobre la recomendación Optimal) es un consejo de gestión de riesgo importante para cualquier cliente nuevo en compromisos multi-año — vale la pena posicionarlo como la mejor práctica estándar de la industria, no una limitación del producto.

## Documentos fuente

- Guide to Commitment Management (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-guide-commitment-management.md`
- Using the Commitment Manager Overview to Align the Organization on Commitment Strategy — `kb/02-product-docs/apptio-cloudability-standard/en/gcm-using-commitment-manager-overview-align-organization-commitment-strategy.md`
- Guide to Legacy Commitment Manager — `kb/02-product-docs/apptio-cloudability-standard/en/management-guide-legacy-commitment-manager.md`
- Using Commitment Portfolio to Understand Historical Performance — `kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-portfolio-understand-historical-performance.md`
- Using Commitment Recommendations to Analyze Savings Opportunities — `kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-recommendations-analyze-savings-opportunities.md`
- Using Commitment Preferences to Build a Business Case — `kb/02-product-docs/apptio-cloudability-standard/en/management-using-commitment-preferences-build-business-case.md`
- Setting Commitment Alerts — `kb/02-product-docs/apptio-cloudability-standard/en/management-setting-commitment-alerts.md`
- Data Freshness — `kb/02-product-docs/apptio-cloudability-standard/en/management-data-freshness.md`
- Guide to Commitment Management FAQ — `kb/02-product-docs/apptio-cloudability-standard/en/management-guide-commitment-faq.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
