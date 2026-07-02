---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Comprender los compromisos mediante los informes nativos de Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía sobre la funcionalidad avanzada de compromiso"
source_path: "product/understanding_commitments_using_cloudability_native_reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Comprender los compromisos mediante los informes nativos de Cloudability

Los planes de ahorro (SP) son el nuevo instrumento de descuento lanzado por AWS. En este tema se explica en qué se diferencian los planes de ahorro de los descuentos tradicionales con instancias reservadas (RI) y se ofrece información detallada sobre las implicaciones en la facturación. Puede utilizar la dimensión *Tipo de arrendamiento*, junto con otras dimensiones y métricas habituales sobre su uso de SP.

**Comparación de los RI**

- Las tasas de descuento son idénticas entre los SP de instancia de EC2 y los RI estándar, y entre los SP de computación y los RI convertibles.
- Con los planes de ahorro, puede comprometerse por encima del nivel de servicio y regional (en el caso de los planes de ahorro informático). Esto tiene importantes implicaciones en la forma en que planifica y gestiona su factura de la nube.
- En lugar de comprometerte con *horas de instancia*, ahora te comprometes con *horas de dólar*. Puede verificar si los dólares por hora a los que se compromete son los dólares descontados tras el Plan de Ahorro o el coste neto.

**Análisis en profundidad de las implicaciones de facturación**

Las principales diferencias entre cómo se gestionan los planes de ahorro y los RI en la facturación detallada (archivo CUR) se mencionan aquí:

- Las horas de uso cubiertas por los SP se representan en gran medida como horas bajo demanda.
  - La descripción del artículo parece ser **« 0.156 » por On Demand Linux**...
  - Las métricas de costes estándar «coste sin combinar» y «tarifa sin combinar» se basan en las cifras bajo demanda. Esto contrasta con los RI, donde las cifras se reducen considerablemente.
- Mientras que los costes recurrentes de las RI (en el caso de los pagos sin anticipo o con anticipo parcial) aparecían como una sola partida al principio de cada mes para los SP, los costes recurrentes se desglosan en partidas individuales para cada hora del mes. Todas las líneas del mes se cargan al comienzo del mes, lo que significa que usted dispone de informes de costes futuros en el archivo CUR.
- Hay un nuevo tipo de línea de facturación llamada **Negación** que permite que las métricas de costes habituales representen con precisión su factura a nivel mensual.

**Caso de uso**

Veamos cómo se mantiene esto cuando se consume un SP durante una hora. Este es un ejemplo muy sencillo del archivo CUR para un plan de ahorro de instancias sin pago inicial de EC2 :

![Icono de notas](../images/understanding_how_aws_savingsmceclip0.jpg)**Nota:**

Las dos primeras líneas son las horas reales de uso de la instancia EC2 que consumen por completo el SP para esa hora.

**El escenario**

El coste sin combinar se reduce a la tarifa recurrente, que es nuestra tarifa con descuento. Esto es el resultado de que la línea de negación niega completamente las dos líneas de uso. Sin embargo, ni la negación ni las líneas recurrentes incluyen el ID del recurso ni información importante, como las etiquetas. Esto significa que si asigna los costes basándose en etiquetas o ID de recursos, obtendrá el coste *bajo demanda* para las horas cubiertas por los SP y costes muy reducidos para las horas cubiertas por los RI. ¿Qué hacer?

**La solución**

Cloudability Le ofrece dos formas sencillas de distribuir los costes de manera equitativa en un entorno en el que las infraestructuras de investigación (RI) y los proveedores de servicios (SP) influyen en las partidas de costes. La métrica «**Coste (lista)** » elimina por completo el impacto de cualquier descuento basado en compromisos, lo que elimina la naturaleza impredecible de los descuentos aplicados. La métrica «**Coste (amortizado)** » le permite trasladar los beneficios a sus equipos, al tiempo que garantiza un comportamiento coherente entre las RI y las SP. Esta métrica se puede utilizar en todo Cloudability y asocia el coste total (incluido el componente inicial) de las RI y los SP a nivel de recursos. Esto permite un resumen completo del coste real.

**Más información**

- Para conocer el comportamiento histórico de las infraestructuras de investigación, consulte [Comprensión de las métricas de costes de las infraestructuras de investigación ( AWS ): ¿dispone de una métrica de costes real?](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Femerge%2Funderstanding-aws-cost-metrics-do-you-have-a-true-cost-metric%2F "(se abre en una pestaña o una ventana nueva)")
- Para obtener más información sobre los informes, consulte [Informe personalizado](https://www.ibm.com/links?url=https%3A%2F%2Fapp.cloudability.com%2Flogin%23%2Freports%2Freport%3Fdimensions%3Dreservation_identifier%26dimensions%3Denhanced_service_name%26dimensions%3Dtransaction_type%26dimensions%3Doffering_class%26end_date%3D23%3A59%3A59%26filters%3Dlease_type%3D%3Dsavings%2Bplan%26limit%3D50%26metrics%3Dunblended_cost%26metrics%3Dtotal_amortized_cost%26metrics%3Dpublic_on_demand_cost%26order%3Ddesc%26sort_by%3Dunblended_cost%26start_date%3D7%2Bdays%2Bago%2Bat%2B00%3A00%3A00%26title%3Dcustom%2Breport "(se abre en una pestaña o una ventana nueva)").

**Tema principal:** [Guía sobre la funcionalidad de compromiso avanzado](../product/guide_to_advanced_commitment_functionality.html)
