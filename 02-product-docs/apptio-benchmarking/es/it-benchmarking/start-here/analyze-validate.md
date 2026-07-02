---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Analizar y validar ATUM Cost Pools"
breadcrumb: []
source_path: "it-benchmarking/start-here/analyze-validate.html"
images:
  - "resources/images/it_benchmarking_images/analyze-validate-1.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-2.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-3.jpg"
  - "resources/images/it_benchmarking_images/analyze-validate-4.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Analizar y validar ATUM Cost Pools

**Resumen**

Puede utilizar Benchmarking para analizar y validar la distribución del conjunto de costes para una fuente de costes alineada con ATUM o como un análisis independiente en la evaluación comparativa interactiva.

**Más allá de la evaluación comparativa**

El producto Benchmarking puede aprovecharse de varias formas distintas, empezando por una introducción a Apptio, pasando por el proceso de implantación y continuando con las operaciones cotidianas, como ayudar a defender el presupuesto de TI. Este artículo se centra en el aspecto de la validación del fondo de costes ATUM de la utilización de Interactive Benchmarking.

**Utilización de Interactive Benchmarking para la validación de grupos de costes**

Puede utilizar Interactive Benchmarking para apoyar la confirmación de imputaciones de pool de costes. Comparando la asignación de cuentas a grupos de costes de una organización con los datos comunitarios de Apptio (ACD), un TBMA puede demostrar que las asignaciones se ajustan bien a ATUM, o identificar áreas en las que podría ser necesario mejorar las asignaciones del modelo.

**Validación del pool de costes**

Utilizando un informe de pool de costes de Interactive Benchmarking (véase la imagen inferior), algunos pools de costes de este ejemplo están por encima o por debajo del rectángulo de color. El rectángulo representa los cuartiles primero a tercero, que comprenden el 50% de los datos. Aunque el valor resaltado, hardware, no está fuera del intervalo (un claro indicador de que la asignación es probablemente errónea), sigue estando en el intervalo más alto de todos los valores.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-1.jpg)

En función del valor elevado en comparación con el intervalo del grupo de costes de hardware, el siguiente paso es navegar hasta el informe Análisis del grupo de costes de transparencia de costes. Se selecciona el subelemento Detalles (véase la imagen siguiente) para ver el conjunto de costes de Hardware para el análisis. Obsérvese que "Depreciación y amortización" y "Asistencia y mantenimiento" son las dos áreas con mayor gasto.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-2.jpg)

El usuario, mientras investiga estos costes, puede seleccionar Hardware en el informe Resumen por grupo de costes (véase la imagen siguiente) para estudiar los costes por partida. El usuario puede estudiar los detalles para saber si hay un mapeo inexacto del pool de costes o si los costes están simplemente por encima del rango.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-3.jpg)

El usuario puede seleccionar la partida para el detalle del libro mayor desde la vista de transacciones de OpEx. A continuación, el usuario puede tomar nota de que existe un cargo importante por depreciación. Esto completa el análisis sobre por qué el valor es más alto. El mayor valor no está relacionado con un problema cartográfico, sino con unos costes reales superiores a la mayoría. El paso siguiente, que queda fuera del alcance de este artículo, es aprovechar otros informes de Transparencia de Costes para completar el cuadro de costes.

![img4](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/analyze-validate-4.jpg)

**Conclusión**

Utilizando el producto Benchmarking , el usuario puede emplear las funciones interactivas de Benchmarking para la validación de la asignación de grupos de costes de Transparencia de Costes. Al comparar los valores asignados y cartografiados con el conjunto de Apptio Community Data (ACD), el cliente puede analizar y validar la exactitud de sus cartografías y examinar más a fondo los detalles para aportar pruebas justificativas.
