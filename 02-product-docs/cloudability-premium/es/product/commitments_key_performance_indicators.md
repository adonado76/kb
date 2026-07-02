---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Indicadores clave de rendimiento del compromiso"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Comprender los conceptos básicos de la gestión de compromisos en Cloudability"
source_path: "product/commitments_key_performance_indicators.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Indicadores clave de rendimiento del compromiso

## Finalidad

Establecer una comprensión básica de los KPI comunes utilizados en Cloudability Commitments. Para el gestor de compromisos, la cartera y las recomendaciones, utilizamos indicadores clave de rendimiento comunes que cuantifican el ahorro y el riesgo tras tener en cuenta todos los ajustes de costes y precios.

## Indicadores de ahorro

**Ahorro neto** - Ahorro menos despilfarro. Refleja el verdadero valor realizado/esperado por su cartera, compromiso o recomendaciones. Se utiliza tanto a nivel de compromiso individual como agregado.

Ejemplo - Si un conjunto de compromisos costara $10k durante un período determinado, lo que equivaldría a $15k en gastos equivalentes a la demanda. El ahorro bruto de los compromisos sería $15k - $10k = $5k. Si el 5% de estos compromisos quedaran sin utilizar, el despilfarro equivaldría a $10k\*5% = 500 $. Por tanto, el Ahorro Neto = $5k - 500 $ = $4.5k.

**Tasa de ahorro** - En nuestra aplicación aparecen varias tasas de ahorro. Sus definiciones son las siguientes:

**Genéricamente** - Tasa de ahorro = Ahorro / Gasto

**Tasa de Ahorro Efectivo (TEA** ) - El Gasto Comprometido se expresa explícitamente en términos de precio a la carta. Por lo tanto, una base de costes de *lista* significa que no se incluyen ni las tarifas negociadas a la carta ni los compromisos, la ESR se basa únicamente en los precios de lista. Para una base de costes *ajustada*, se utiliza la tarifa de lista a la demanda junto con la tarifa de compromiso negociada. Aunque un poco matizada, esta definición coincide con la de la Fundación FinOps y tiene sentido cuando los precios negociados se incluyen como componente de la optimización de tarifas. Sólo utilizamos este término en el panel de optimizaciones, ya que es crucial aislar el rendimiento del compromiso de los precios negociados en el nivel de características del compromiso.

ESR = (Ahorro en compromisos + Ahorro en tarifas personalizadas) / Gasto comprometido.

**Tasa de ahorro negociada (NSR** **) -** Aunque no se utiliza explícitamente en Cloudability, la NSR es un término que puede utilizarse para aislar sus tarifas negociadas a la carta. El numerador es simplemente el ahorro atribuido a esta tarifa negociada, mientras que el denominador, el Gasto Comprometido, lleva la misma definición que en el caso del ESR.

NSR = Ahorro de tarifa personalizada / Gasto comprometido.

**Tasa de Ahorro de Cartera (PSR)** - PSR es la métrica central que Cloudability Commitments utiliza para comunicar el rendimiento de una cartera o conjunto de recomendaciones. En particular, los gastos comprometidos se ajustan plenamente a la base de costes. Por lo tanto, una base de *costes de lista* implica que el ahorro y el gasto se basan en las tarifas de lista, mientras que *ajustado* implica que el KPI se calcula a partir de las tarifas negociadas.

PSR = Ahorro comprometido / Gasto comprometido.

**Tasa de ahorro** de un compromiso (TAC) - Tasa de ahorro realizada (cartera) o prevista (recomendaciones) de un compromiso. Puede compararse directamente con el CDR para comprender el impacto de la utilización. En particular, este KPI aparece junto a PSR en la cartera cuando procede. Otra forma de describir este KPI cuando aparece en la cartera es la media ponderada de las tasas de ahorro de múltiples compromisos.

CSR = Ahorro de compromiso / ODE de coste de compromiso

**Tasa de descuento del compromiso (CDR)** - Tasa de ahorro dado que el compromiso se utilizó en su totalidad. Este dato lo comparamos con la RSE para demostrar el máximo ahorro que se puede conseguir con un compromiso determinado.

CDR = 𝑆𝑎𝑣𝑖𝑛𝑔𝑠 𝑅𝑎𝑡𝑒 @ 100% 𝑈𝑡𝑖𝑙𝑖𝑧𝑎𝑡𝑖𝑜𝑛.

Los documentos de ayuda posteriores profundizarán en esta terminología y explicarán dónde es pertinente para comprender plenamente el rendimiento de los compromisos y evaluar las oportunidades

## Estrategia e indicadores de riesgo

**Utilización** - Grado en que los compromisos adquiridos se han consumido realmente; ponderado y agregado cuando se muestra como un KPI. Esta métrica se realiza para la cartera pero se espera como resultado del rango de uso seleccionado en las recomendaciones.

**Cobertura** - La parte del uso elegible cubierta por compromisos (frente a la demanda), mostrada como porcentaje y apoyada ampliamente por una modalidad de cobertura.

Ejemplo : una cobertura del 75% significa que tres cuartas partes del uso subvencionable se ha beneficiado de precios reducidos.

**Coste restante del compromiso** : lo que debe desde hoy hasta que venzan todos los compromisos activos, independientemente del intervalo de notificación.

Es importante destacar que, a menudo, los KPI y metadatos de compromiso no se pueden derivar a través de métricas empresariales y, por lo tanto, las páginas de compromiso sólo admiten vistas basadas en cuentas y proveedores. Nos esforzamos por seguir mejorando esta parte de nuestra aplicación y le animamos a que marque las solicitudes en el [portal de ideas IBM](https://ideas.ibm.com/new-idea?product=7428699546216862860&category=7429430490210197213 "(se abre en una pestaña o una ventana nueva)"). Aproveche la categoría "Optimización de tarifas"

**Tema principal:** [Comprender los fundamentos de la gestión de los compromisos en Cloudability](../product/commitment_management_basics.html)
