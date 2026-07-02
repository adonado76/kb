---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ApptioOne Precisión"
breadcrumb: []
source_path: "studio/getting_started_with_tbm_studio/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precisión

Apptio utiliza la [https://en.wikipedia.org/wiki/IEEE\_754](https://en.wikipedia.org/wiki/IEEE_754 "(se abre en una pestaña o una ventana nueva)") especificación de [https://en.wikipedia.org/wiki/Double-precision\_floating-point\_format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(se abre en una pestaña o una ventana nueva)") números para representar valores numéricos.

Este estándar proporciona alrededor de 17 - log10(N ) dígitos de precisión (donde N es el número de valores que se suman) para la mayoría de las operaciones, y 15 dígitos de precisión para otras operaciones. Aunque Apptio conserva y muestra números de más de 15 dígitos, estos números pueden cambiar entre compilaciones o cálculos sobre la misma compilación, configuración o datos.

Cuando se redondean los números, Apptio utiliza la regla de desempate de [redondear la mitad para igualar](https://en.wikipedia.org/wiki/Rounding#Round_half_to_even "(se abre en una pestaña o una ventana nueva)") (también conocida como "redondeo de banqueros"), que es la regla por defecto para IEEE 754.

Cuando Apptio suma valores, utiliza el [algoritmo de suma de Kahan](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(se abre en una pestaña o una ventana nueva)") para proporcionar eficientemente la suma más exacta posible.

Tenga en cuenta que Apptio añade una cantidad fudge ( 0.00000001 ) a todos los números mostrados como Round() o NumberFormat( ), para controlar el redondeo de los números en coma flotante.

Por ello, las cifras que figuran en Apptio son exactas a la menor:

- 15 dígitos significativos (dígitos antes y después del punto decimal) o
- 7 decimales (dígitos después del punto decimal)

Apptio muestra por defecto números con 3 decimales.

## Información adicional

Consulte la documentación de ayuda de Apptio sobre [Acerca de la ponderación y los números negativos](../model_studio/about-weighting-and-negative-numbers.html "◆ Se aplica a: TBM Studio 11.8.3.1 y posteriores; TBM Studio 12.0 y posteriores. El objetivo de una ponderación es asignar el número de origen en el que la suma es la misma en el destino.").
