---
tbm_concept: "Optimize — Understanding Commitment Management Basics (terminología de costo estandarizada, KPIs de ahorro/riesgo, mecánica de precios negociados, y estructura de cuenta por proveedor)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-understanding-commitment-management-basics-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitments-approach-cost.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-key-performance-indicators.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-how-negotiated-pricing-factors-across-commitments.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-account-structure-by-vendor.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-table-basics.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-management-basics-faq.md
last_updated: "2026-07-09"
---
# Optimize — Understanding Commitment Management Basics — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Antes de entrar a las guías operativas de Commitment Management (Capítulos 14-16), este capítulo establece el vocabulario y las fórmulas exactas que hacen posible interpretar correctamente cualquier KPI de compromiso — sin esta base, es fácil malinterpretar un número de "ahorro" o "cobertura" al comparar entre páginas o entre proveedores de nube.

## Cómo lo resuelve IBM Cloudability Standard

**Terminología de costo estandarizada, empezando por el concepto fundacional: On-Demand Equivalent (ODE)** — el costo base que se habría pagado si todo el uso correspondiente se hubiera pagado a tarifa on-demand, sin importar si en la realidad se pagó una combinación de on-demand y compromiso.

**Cinco KPIs core, con fórmula y ejemplo numérico documentado explícitamente para Net Savings:**
- **Net Savings** — ahorro bruto menos desperdicio, el valor real capturado. Ejemplo documentado: compromisos que costaron $10K con un ODE de $15K generan un ahorro bruto de $5K; si el 5% de esos compromisos quedó sin utilizar, el desperdicio es $10K × 5% = $500; **Net Savings = $5K − $500 = $4.5K**.
- **Utilization** — qué proporción de los compromisos comprados realmente se consumió (realizado a nivel de portafolio, esperado en recomendaciones según el rango de uso seleccionado).
- **Coverage** — qué porción del uso elegible está cubierta por compromisos vs. on-demand, mostrada como porcentaje.

**Negotiated Pricing (o Custom Pricing, usados indistintamente) — cómo interactúa con los KPIs de compromiso, con dos efectos distintos documentados.** Primero, **cambia la línea base**: el gasto comprometible (ODE) refleja tarifas de lista o tarifas ajustadas según la base de costo elegida, y esa elección se propaga hacia los cinco KPIs. Segundo, **cambia la tasa de descuento del compromiso mismo**: además de negociar tarifas on-demand, los proveedores permiten negociar descuentos de compromiso que varían por tipo, región, instancia y plazo.

**Cost Basis — List vs. Adjusted, la decisión que determina qué tarifas alimentan todo el cálculo.** List usa tarifas públicas/de lista tanto para on-demand como para compromiso. Adjusted usa las tarifas realmente negociadas por el cliente.

**Stacking Rules — cómo se combinan descuentos negociados y descuentos de compromiso, sin reglas universales.** Patrón documentado como el más común: **Additive Stacking** — los descuentos negociados reducen primero la tarifa on-demand, y los descuentos de compromiso se aplican encima de esa tarifa ya reducida, resultando en una tarifa efectiva menor. El documento advierte explícitamente que no hay reglas universales — cada acuerdo de cliente/proveedor puede variar, y estos patrones deben verificarse contra el contrato real.

**Guía práctica documentada explícitamente**: aislar KPIs basados en lista de los basados en negociado (mezclarlos puede dar una interpretación de performance equivocada), asegurar que Adjusted esté configurado como base por defecto y documentar esa base en cualquier dashboard o exportación compartida fuera de la aplicación, validar reglas de stacking por familia de servicio antes de comprar, y explorar la base de costo List para entender el impacto real de los términos negociados — útil como insumo para futuras conversaciones de negociación de precio con el proveedor.

**Account Structure by Vendor — por qué la jerarquía de cuenta importa para compartir, ver y reportar compromisos.** Los beneficios de un compromiso fluyen según el alcance específico de cada proveedor (organización, perfil de facturación, proyecto, región/zona de disponibilidad). Cloudability normaliza esas jerarquías dispares hacia conceptos comunes: **Payer Account** (el dueño de la factura, y típicamente donde se compra formalmente el compromiso — aunque puede comprarse a nivel de cuenta enlazada según el proveedor; si el sharing está activo, el compromiso típicamente se comparte entre todas las cuentas enlazadas del payer). Estructura documentada específicamente para AWS: la cuenta de gestión (payer) recibe la factura consolidada y suele ser la cuenta de compra de RIs/Savings Plans.

## Por qué importa en una conversación con el cliente

La distinción List vs. Adjusted cost basis es la pregunta de discovery más importante antes de mostrarle a un cliente cualquier KPI de compromiso — comparar un Net Savings calculado en base List contra uno calculado en base Adjusted da resultados incomparables, y confundir ambos genera desconfianza en los números presentados.

El ejemplo numérico de Net Savings es directamente reutilizable en cualquier explicación a Finanzas de por qué "ahorro bruto" y "ahorro neto" no son lo mismo — el desperdicio de compromisos infrautilizados debe restarse del ahorro bruto para llegar al valor real capturado.

La advertencia de que no hay reglas universales de stacking entre descuentos negociados y de compromiso es un argumento importante de gestión de expectativas — vale la pena confirmar con el cliente que su equipo de procurement puede validar las reglas reales de su contrato específico, en lugar de asumir el patrón Additive Stacking documentado como más común.

## Documentos fuente

- Understanding Commitment Management Basics in Cloudability (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-understanding-commitment-management-basics-in-cloudability.md`
- Cloudability's Approach to Cost (terminología) — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitments-approach-cost.md`
- Commitment Key Performance Indicators — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-key-performance-indicators.md`
- How Negotiated Pricing Factors Across Commitments — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-how-negotiated-pricing-factors-across-commitments.md`
- Account Structure by Vendor — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-account-structure-by-vendor.md`
- Commitment Table Basics — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-table-basics.md`
- Commitment Management Basics FAQ — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-commitment-management-basics-faq.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
