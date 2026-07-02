---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Implantar el detalle de la fuente de costes pensando en el rendimiento"
breadcrumb: []
source_path: "studio/admin/configurecostsource.html"
images:
  - "resources/images/studio_images/studio_cs_allocates_to_financial_750x432.png"
  - "resources/images/studio_images/studio_cs_base_of_the_model_750x276.png"
  - "resources/images/studio_images/studio_cs_modeled_table_750x394.png"
  - "resources/images/studio_images/studio_cs_or_csd_approach_diagram_thumb_720_0.png"
  - "resources/images/studio_images/studio_csd_allocates_to_financial_750x438.png"
  - "resources/images/studio_images/studio_csd_base_of_the_model_750x354.png"
  - "resources/images/studio_images/studio_full-granularity_report_modeled_table_750x386.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Implantar el detalle de la fuente de costes pensando en el rendimiento

Con frecuencia configuramos la Fuente de Costes para que sea lo más granular posible, y nos olvidamos de determinar si utilizamos o necesitamos esa granularidad. La mayoría de los informes y estrategias de imputación estándar no requieren ni hacen referencia a toda la gama de elementos que solemos ver en los archivos de tipo libro mayor que respaldan nuestra tabla de datos maestros de fuentes de costes. Una mayor granularidad no suele mejorar nuestros informes, pero siempre disminuye su rendimiento.

El propósito de este artículo es discutir formas de reducir la granularidad innecesaria.

## Consideraciones arquitectónicas

Antes de revisar las opciones, determine primero lo siguiente:

- ¿Qué columnas y qué nivel de granularidad necesito para soportar las asignaciones? Por ejemplo, las columnas utilizadas en los controladores, los filtros y las relaciones de datos en las imputaciones fuera de la Fuente de Coste.
- ¿Qué columnas y qué nivel de detalle necesito para elaborar informes?

Aunque las columnas son la forma más sencilla de concebir la granularidad en la Fuente de Costes u otras tablas modeladas, la granularidad requerida puede ser en algunos casos un subconjunto de valores dentro de esas columnas. En tales casos, puede ser posible crear una columna que omita los valores superfluos.

## Agrupar filas para eliminar elementos de datos innecesarios

Si la granularidad necesaria para apoyar las asignaciones y la elaboración de informes es sustancialmente menor que la granularidad de la fuente de costes, esta es la mejor opción.

Un ejemplo común de granularidad excesiva es la fecha de la transacción, u otra información a nivel de transacción. Considere el siguiente escenario para visualizarlo. Si queremos ver cuánto gasta un determinado Centro de Coste en cada Cuenta, no necesitamos la tabla completa de 6 filas ([Tabla de alta granularidad](#ImplementingCostSourceDetailwithperformanceinmind__High-granularity_table) ). La agrupación en los elementos de datos que necesitamos no nos deja con menos información para tomar nuestra decisión, pero redujo nuestro recuento de filas en casi un 50% ([tabla de baja granularidad](#ImplementingCostSourceDetailwithperformanceinmind__Low-granularity) ). Las ventajas de rendimiento son aún mayores cuando se trabaja con las decenas de miles de filas que suelen contener los datos financieros que consumimos.

## Mesa de alta granularidad

| Centro de costes | Cuenta | Importe | Fecha de transacción |
| --- | --- | --- | --- |
| CC123 | 80001 | 400 dólares | 2/4/17 |
| CC123 | 80001 | 585 dólares | 3/4/17 |
| CC123 | 90001 | 500 dólares | 2/4/17 |
| CC456 | 80001 | 450 dólares | 2/4/17 |
| CC456 | 80001 | 400 dólares | 3/4/17 |
| CC789 | 90001 | 500 dólares | 2/4/17 |

## Tabla de baja granularidad

| Centro de costes | Cuenta | Importe | Fecha de transacción |
| --- | --- | --- | --- |
| CC123 | 80001 | 985 dólares | {Various} |
| CC123 | 90001 | 500 dólares | 2/4/17 |
| CC456 | 80001 | 850 dólares | {Various} |
| CC789 | 90001 | 500 dólares | 2/4/17 |

## Utilizar tablas independientes para informes de granularidad completa

Nota: Se trata de una opción avanzada que requiere la creación de informes personalizados o la modificación de informes ya existentes. Esta opción sólo se recomienda cuando se necesitan informes granulares a nivel de línea.

Cuando existe un requisito empresarial para informar sobre los detalles más allá de lo necesario para apoyar las asignaciones, entonces la mejor opción es una tabla *de detalles* independiente. Es la solución más sencilla y evita errores en el futuro, como crear un informe demasiado detallado.

En situaciones más complejas, en las que pueden ser necesarios informes granulares a nivel de línea, podemos satisfacer estos casos de uso sin afectar gravemente al rendimiento del modelo. Una forma de conseguirlo es crear una tabla modelada de *informes* de granularidad completa que no se utilice para las imputaciones y mantenga la tabla modelada de fuentes de costes estándar agrupada sólo en lo estrictamente necesario para la lógica de imputación. Esto significa que los datos están fácilmente disponibles para la elaboración de informes y que también podemos utilizar métricas estándar y personalizadas con ellos, pero nuestro tiempo de cálculo y los ejercicios de elaboración de informes sólo se ven afectados mínimamente.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_cs_modeled_table_750x394.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_full-granularity_report_modeled_table_750x386.png)

## Utilizar una tabla *detallada de fuentes de costes* para apoyar las imputaciones

Si necesita granularidad en la Fuente de Costes para soportar asignaciones a tablas modeladas por encima de la Fuente de Costes, entonces puede insertar una tabla *Detalle Fuente de Costes* entre la Fuente de Costes y esos objetos.

Nota: Si crea nuevos informes con tablas que muestren la relación entre Detalle de la Fuente de Coste y otras tablas modeladas más arriba en el modelo, esto puede erosionar los beneficios del cálculo.

Puede crear una tabla de Detalle de la Fuente de Coste utilizando una transformación de Fuente de Coste.

Transformar el coste Fuente:

1. En la pestaña Inicio, seleccione Nuevo > Tabla.
2. Introduzca el Nombre y la Categoría de la nueva tabla y, a continuación, seleccione Aceptar.
3. Cuando se abra el paso Fuente, seleccione Tabla existente.
4. En el menú desplegable Tabla de entrada, seleccione Datos maestros de la fuente de costes como fuente.

Los siguientes procesos resumen la creación de una tabla de Detalle de la Fuente de Coste:

- Para establecer el identificador de objeto para Detalle de la fuente de coste, seleccione las columnas que forman el identificador original. Contienen la granularidad necesaria.
- El detalle de la fuente de costes es la base del modelo y se asigna a la fuente de costes.
- Para establecer el identificador de objeto para la Fuente de Coste, seleccione las columnas para hacer un *identificador optimizado*. El identificador optimizado es una versión reducida del identificador original, y contiene sólo los campos necesarios para asignar al Detalle de la Fuente de Coste.
- La fuente de costes se asigna a la capa financiera.

Una vez establecidos los identificadores, es necesario ajustar los controladores y las asignaciones para pasar los costes de la Fuente de Coste al Detalle de la Fuente de Coste y de ahí al resto de la capa financiera. El proceso de ajuste de los controladores y las asignaciones varía según las implementaciones, por lo que es difícil describir los pasos específicos en este artículo. En resumen, los controladores y las imputaciones que se asignan desde el detalle de la fuente de coste deben tener exactamente los mismos importes de moneda en la métrica del objeto que tenían cuando se asignaban desde el objeto de la fuente de coste.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_cs_base_of_the_model_750x276.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_csd_allocates_to_financial_750x438.png)

Mediante la imputación a través de la Fuente de Coste Detalle, los usuarios pueden mantener la granularidad adicional en el objeto detalle, al tiempo que evitan que la Fuente de Coste sea demasiado granular.

## Utilice una tabla *detallada de la fuente* de costes Fuente de costes

Si la granularidad de la Fuente de Coste necesaria para soportar requisitos específicos de información excede lo que se necesita para soportar asignaciones a objetos, entonces crear una tabla de Detalle de Fuente de Coste por debajo de Fuente de Coste es una opción. Los informes que necesiten la granularidad extra deben cambiarse para que apunten a Detalle de la Fuente de Coste en lugar de Fuente de Coste.

El proceso es similar al de [Utilizar una tabla de Detalle de Fuente de Coste para soportar imputaciones](#ImplementingCostSourceDetailwithperformanceinmind__UseaCostSourceDetailtabletosupportallocations), pero más simple en el sentido de que normalmente se requiere menos trabajo para implementar los cambios si todas las imputaciones entre Fuente de Coste y objetos en la capa financiera no cambian.

Dependiendo del estado de un proyecto, le recomendamos que utilice una configuración en la que el Detalle de la Fuente de Coste se sitúe por debajo de la Fuente de Coste. Esto se debe a que cuanto más lejos esté un proyecto en desarrollo, más tiempo se tarda en hacer cambios para poner el Detalle de la Fuente de Coste por encima de la Fuente de Coste. Si se trata de un proyecto nuevo, diseñe el modelo de modo que la fuente de costes alimente el detalle de la fuente de costes. Si configura el modelo de forma que Detalle de la fuente de coste sea el objeto inferior, tenga en cuenta los siguientes riesgos.

Nota:

- Si los usuarios crean nuevos informes con tablas que muestren la relación entre el Detalle de la Fuente de Coste y otras tablas modeladas más arriba en el modelo, esto puede erosionar los beneficios del cálculo.
- Si los requisitos cambian y necesita utilizar detalles adicionales para respaldar las imputaciones, es posible que tenga que mover Detalle de la fuente de coste por encima de Fuente de coste.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_csd_base_of_the_model_750x354.png)

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_cs_allocates_to_financial_750x432.png)

## Cómo informar al detalle

Por diseño, el uso de Detalle de la Fuente de Coste en la superficie del informe debe limitarse a una tabla resumen. Esto permite a los usuarios aprovechar la granularidad adicional dentro del objeto, sin experimentar un rendimiento reducido causado por un taladro en el objeto. Si los requisitos de la empresa cambian y surge la necesidad de profundizar en el objeto Detalle de la fuente de coste, le recomendamos que se ponga en contacto con su CSM para seguir revisando las posibles opciones.

## Resumen

Para una referencia fácil en cuanto al enfoque que debe adoptarse cuando se discute el Detalle de la Fuente de Coste, consulte el siguiente cuadro:

[![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_cs_or_csd_approach_diagram_thumb_720_0.png)](../../resources/images/studio_images/studio_cs_or_csd_approach_diagram.png "(se abre en una pestaña o una ventana nueva)")

Para obtener más información sobre la creación de objetos, controladores e informes personalizados, visite TBM Studio's R12 [Knowledge base](https://community.apptio.com/community/apptio/product-central/cost-transparency "(se abre en una pestaña o una ventana nueva)").

Nota:

- Recuerde que el propósito de los datos en Apptio es rellenar informes que ayuden a tomar decisiones. Si un elemento de datos no puede ayudarle a tomar una decisión o a asignar costes, entonces no es un buen candidato para incluirlo en un identificador.
- Ver *{various}* no es necesariamente un signo de mala configuración, especialmente cuando se configura para mejorar el rendimiento.
- Al hacer excepciones a las recomendaciones de granularidad estándar, o al añadir nuevos objetos e informes, busque primero las opciones menos invasivas. A partir de ahí, puede aumentar la granularidad hasta el nivel deseado.
- Tenga en cuenta que Costing Standard no es un sistema contable. La mayoría de los analistas que podrían hacer uso de datos extremadamente granulares a nivel de transacción ya tienen acceso a esa información. El nivel de detalle necesario para la modelización de costes, las asignaciones y las decisiones empresariales estratégicas suele ser mucho menor.
