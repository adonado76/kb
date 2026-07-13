---
concept: "Administration and Operations (patrones de diseño organizacional: showback simple, chargeback, catálogo de servicio, nube, proyecto, entidad legal, y cómo combinarlos)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-billing
status: draft
generated_from:
  - kb/02-product-docs/apptio-billing-standard/en/operations-overview.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-simple-service-showback.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-chargeback-journals.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-service-catalog-centric-design.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-cloud-centric-design.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-project-centric-design.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-legal-entity-transfer-pricing-view.md
  - kb/02-product-docs/apptio-billing-standard/en/operations-combining-patterns-without-creating-chaos.md
last_updated: "2026-07-06"
---
# Administration and Operations — Cómo Apptio Billing Aborda Esta Capacidad

## El concepto

No todas las organizaciones facturan tecnología de la misma forma, ni tienen la misma razón para hacerlo. Este capítulo cataloga los **patrones de diseño organizacional** más comunes con los que se configura Billing — desde el más simple (mostrar el costo sin cobrar nada) hasta el más complejo (facturación real entre entidades legales con precios de transferencia) — y, crucialmente, cómo combinarlos sin que el modelo se vuelva inmanejable.

## Cómo lo resuelve Apptio Billing

**Un espectro de seis patrones, de menor a mayor complejidad organizacional:**

- **Simple service showback** — el patrón más básico: mostrarle a un consumidor cuánto "le tocaría" pagar por su consumo, sin generar ningún movimiento financiero real. Es informativo, no contable — el punto de entrada típico para una organización que recién empieza con Billing.
- **Chargeback with journals** — el siguiente nivel: el cargo se convierte en un movimiento contable real, vía la generación de journals ya vista en el Capítulo 6. Aquí Billing deja de ser solo informativo.
- **Service catalog centric design** — el modelo se organiza alrededor de un catálogo de servicios de TI bien definido — el patrón más natural para una organización con un catálogo de servicios de TI ya maduro (posiblemente ya integrado con una CMDB o ITSM, como vimos en Costing Standard).
- **Cloud centric design** — el modelo se organiza alrededor del consumo de nube específicamente — relevante para organizaciones cuyo mayor centro de atención de costo variable es la nube pública, conectando naturalmente con el módulo de Public Cloud ya documentado en Costing Standard.
- **Project centric design** — el modelo se organiza alrededor de proyectos/iniciativas en lugar de servicios operativos estables — relevante para organizaciones que facturan inversión, no solo operación.
- **Legal entity and transfer pricing view** — el patrón más complejo: facturación real entre entidades legales distintas dentro de la misma organización, con las implicaciones fiscales y de precios de transferencia que eso conlleva — típicamente relevante para conglomerados multinacionales con estructura legal compleja.

**Combining patterns without creating chaos** — quizás el documento más valioso de todo el capítulo desde una perspectiva de consultoría: reconoce explícitamente que las organizaciones reales rara vez usan un solo patrón puro, sino combinaciones (por ejemplo, catálogo de servicio + nube, o proyecto + entidad legal), y da guía de diseño para hacerlo sin que el modelo se vuelva contradictorio o inmantenible.

## Por qué importa en una conversación con el cliente

Este catálogo de seis patrones es, en efecto, un **framework de diagnóstico de discovery** — preguntarle a un cliente cuál de estos patrones (o combinación) describe mejor su realidad organizacional es una de las preguntas más productivas que se pueden hacer al inicio de cualquier compromiso de Billing, porque determina directamente el alcance y la complejidad del proyecto.

La progresión Simple Showback → Chargeback con journals es, otra vez, un excelente argumento de madurez incremental: un cliente nervioso por "empezar a cobrar de verdad" puede comenzar con showback puro (sin riesgo financiero real) y migrar a chargeback una vez que confía en la precisión del modelo.

"Combining patterns without creating chaos" merece mención explícita y proactiva en cualquier discovery donde el cliente describa una realidad híbrida (que es, en la práctica, casi siempre) — es la señal de que Apptio ya anticipó este problema y tiene guía de diseño específica, en lugar de dejar al cliente improvisar una combinación no probada.

## Documentos fuente

- Overview (Administration and Operations) — `kb/02-product-docs/apptio-billing-standard/en/operations-overview.md`
- Simple service showback — `kb/02-product-docs/apptio-billing-standard/en/operations-simple-service-showback.md`
- Chargeback with journals — `kb/02-product-docs/apptio-billing-standard/en/operations-chargeback-journals.md`
- Service catalog centric design — `kb/02-product-docs/apptio-billing-standard/en/operations-service-catalog-centric-design.md`
- Cloud centric design — `kb/02-product-docs/apptio-billing-standard/en/operations-cloud-centric-design.md`
- Project centric design — `kb/02-product-docs/apptio-billing-standard/en/operations-project-centric-design.md`
- Legal entity and transfer pricing view — `kb/02-product-docs/apptio-billing-standard/en/operations-legal-entity-transfer-pricing-view.md`
- Combining patterns without creating chaos — `kb/02-product-docs/apptio-billing-standard/en/operations-combining-patterns-without-creating-chaos.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*