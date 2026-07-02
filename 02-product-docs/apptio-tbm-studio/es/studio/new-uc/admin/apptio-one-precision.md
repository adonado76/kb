---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ApptioOne Precisión"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precisión

Apptio utiliza la especificación [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754 "(se abre en una pestaña o una ventana nueva)") para números [de coma flotante de doble precisión](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(se abre en una pestaña o una ventana nueva)") a la hora de representar valores numéricos.

Esta norma ofrece una precisión de aproximadamente entre 17 y log10(N ) dígitos (donde N es el número de valores que se suman) para la mayoría de las operaciones, y de tan solo 15 dígitos para otras operaciones concretas. Por lo tanto, aunque Apptio conserva y muestra números de más de 15 dígitos, estos pueden variar entre distintas versiones o entre cálculos realizados con la misma versión, configuración o datos.

Cuando se redondean los números, Apptio aplica la regla de desempate que consiste en [redondear hacia abajo cuando el resultado está cerca del cero](https://en.wikipedia.org/wiki/Rounding#Rounding_half_away_from_zero "(se abre en una pestaña o una ventana nueva)") ( a.k.a. «redondeo comercial»).

Cuando Apptio suma valores, utiliza el [algoritmo de suma de Kahan](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(se abre en una pestaña o una ventana nueva)") para obtener de forma eficiente la suma más precisa posible.

Cabe señalar también que Apptio añade un margen de redondeo ( 0.00000001 ) a todos los números mostrados mediante Round() o NumberFormat( ). Esto se hace para controlar el redondeo de los números de coma flotante.

Por lo tanto, las cifras que figuran en Apptio son exactas hasta el menor de los siguientes valores:

- 15 dígitos significativos (dígitos antes y después del punto decimal) o
- 7 decimales (dígitos después del punto decimal)

Apptio Por defecto, muestra los números con tres decimales.
