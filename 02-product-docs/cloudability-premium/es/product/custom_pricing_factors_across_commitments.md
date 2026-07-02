---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Cómo se negocian los factores de fijación de precios entre los compromisos"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Comprender los conceptos básicos de la gestión de compromisos en Cloudability"
source_path: "product/custom_pricing_factors_across_commitments.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cómo se negocian los factores de fijación de precios entre los compromisos

## Finalidad

Explique cómo interactúan los precios negociados con los programas de compromiso y los KPI para que los equipos lean los resultados de forma coherente en todas las páginas y proveedores.

Los precios negociados también pueden denominarse precios personalizados para compromisos, por lo que los utilizaremos indistintamente

## Precios básicos

**Los precios negociados modifican la línea base:** el gasto comprometido, expresado en términos de equivalente bajo demanda (ODE), refleja las tarifas *de lista* o *ajustadas* según la base de costos seleccionada. Esa elección desemboca en cada uno de los 5 indicadores clave de rendimiento.

**Los precios negociados modifican la tasa de descuento por compromiso -** Además de negociar las tarifas a la carta, los CSP permiten negociar descuentos por compromiso, que a menudo varían según el tipo de compromiso, la región, la instancia, el plazo, etc

**Cuestiones de acumulación -** Los precios negociados pueden acumularse con los compromisos (aditivo) o sustituir a determinadas partidas (no acumulación). Confirme siempre cómo interactúa su contrato con el programa de compromiso de los servicios afectados. Dado que Cloudability Commitments extrae estos precios de sus API públicas, podemos determinar formalmente el resultado/expectativa real de un compromiso o recomendación determinados

## Base de costes - Lista vs. Ajustada

La base de costes determina qué precios se utilizan para la ODE y los cálculos de costes.

**Lista -** Utiliza tarifas públicas/lista tanto para los precios a la carta como para los precios de compromiso.

**Ajustado -** Utiliza sus tarifas negociadas/personalizadas tanto para los precios a la carta como para los precios de compromiso. Como se menciona en la introducción a la sección de tarifas de ahorro, la ESR utiliza una combinación de precios de compromiso negociados y tarifas de lista a la carta cuando se selecciona la base ajustada. De este modo, se garantiza que los precios negociados se incluyan al evaluar la optimización de tarifas al más alto nivel.

**Implicación** - Con la base de costes ajustada, a menudo la demanda, el descuento por compromiso y, por lo tanto, la ODE son todos inferiores a los de la lista. En consecuencia, es probable que la magnitud del Ahorro Neto y del Coste del Compromiso sea menor, ya que el descuento de un compromiso es menor, el coste aplicable al compromiso es menor, o una combinación de ambos.

## Reglas de apilamiento

Los contratos de precios negociados difieren mucho según el tamaño del cliente y el CSP. Naturalmente, los mayores usuarios de servicios en nube tienen ventaja a la hora de negociar descuentos en relación con los clientes más pequeños. A alto nivel, no hay reglas rígidas. Trate lo siguiente como patrones para verificar con sus acuerdos.

**Apilamiento aditivo:** los descuentos negociados reducen la tarifa a la demanda; los descuentos por compromiso se aplican por encima, lo que da lugar a tarifas efectivas más bajas.

**Condiciones sustitutivas:** los precios negociados pueden establecer un límite mínimo que sustituya a los descuentos de catálogo para determinadas referencias o servicios.

**Prioridad del programa -** Algunos programas aplican créditos después de los compromisos, otros reducen la base utilizada para calcular el valor del compromiso.

Aunque Cloudability puede ayudar sistemáticamente a exponer las implicaciones de los precios negociados, es prudente que los profesionales de FinOps comprendan las condiciones negociadas por dentro y por fuera. Confirme el orden de apilamiento de sus servicios. Un malentendido sobre el apilamiento puede llevar a contabilizar dos veces el ahorro previsto.

## Orientación práctica

- Aislar los KPI basados en listas de los KPI basados en negociaciones. Mezclarlos podría dar lugar a una interpretación errónea del rendimiento.
- Preste atención a su base de costes en todas las páginas de compromiso. Asegúrese de que ajustado está configurado por defecto. Documente su base en cuadros de mando compartidos y exportaciones fuera de la aplicación.
- Valide el apilamiento por familia de servicios antes de proceder a las compras.
- Explore la base de coste de lista para comprender mejor el impacto de sus condiciones negociadas. Aproveche estos conocimientos en futuras conversaciones sobre precios negociados.

**Tema principal:** [Comprender los fundamentos de la gestión de los compromisos en Cloudability](../product/commitment_management_basics.html)
