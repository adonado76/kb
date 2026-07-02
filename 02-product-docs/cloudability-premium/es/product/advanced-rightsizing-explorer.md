---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Explorador avanzado de redimensionamiento"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto avanzado"
source_path: "product/advanced-rightsizing-explorer.html"
images:
  - "images/advanced-rightsizing-explorer.png"
  - "images/download_button.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Explorador avanzado de redimensionamiento

## Panel de control del explorador

El panel de control Rightsizing Explorer le permite agrupar, filtrar y navegar por todas sus recomendaciones de optimización avanzadas, que incluyen ahorros e inversiones, lo que le permite comprender mejor sus oportunidades y centrar sus esfuerzos en maximizar el rendimiento y minimizar el desperdicio.

Puede alternar entre la vista de ahorros o inversiones en el explorador.

Nota: Debe asegurarse de que todas las credenciales de sus proveedores actuales tengan los permisos pertinentes de Turbonomic, sin los cuales el motor Turbonomic podría no ser capaz de generar el conjunto de acciones adecuado. Si usted era cliente de Cloudability antes de la actualización a Cloudability Premium, deberá volver a acreditar todas y cada una de las credenciales de los proveedores para concederles un conjunto adicional de permisos.

El Explorador avanzado de redimensionamiento se encuentra en Optimizar > Redimensionamiento > Avanzado > Explorador.

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-explorer.png)

Nota:

Turbonomic Las políticas de configuración se aplican cuando se generan acciones de optimización. El Rightsizing Explorer trabaja con las acciones de optimización después de que se generan. Debido a la agrupación, Cloudability recomienda que ajuste su importe mínimo de ahorro a un valor inferior si utiliza Rightsizing Explorer.

Servicios compatibles

Los servicios que se admiten actualmente son:

- AWS: EC2, EBS
- Azure : Computación, Disco
- GCP o: GCE, GPD

Navegar por el Explorador de redimensionamiento

La forma más eficaz de utilizar el Explorador avanzado de redimensionamiento es filtrar primero, buscar y luego centrarse:

1. Aplica filtros para eliminar primero la mayor cantidad de resultados, como Cuentas, Proveedores, Servicios. Puede seleccionar nodos Sankey para añadir filtros rápidamente
2. Elimine cualquier dimensión innecesaria del menú. Añade dimensiones adicionales de una en una para profundizar y descubrir tendencias adicionales.
3. Seleccione un nodo para ver las recomendaciones individuales que coinciden con los atributos del nodo.
4. Filtre la tabla aún más seleccionando valores específicos en las columnas.

Dimensiones

Las dimensiones se utilizan en el diagrama de Sankey para dividir y agrupar sus recomendaciones de optimización. Cuando se añade una dimensión al diagrama de Sankey, se crea un conjunto de nodos con los valores de esa dimensión. El tamaño del nodo corresponde al importe total de los ahorros o inversiones de las recomendaciones individuales con ese valor dimensional.

Nota:

Solo se admite el coste bajo demanda, ya que la mayoría de los servicios no ofrecen métodos de descuento.

Las dimensiones se configuran a través de la barra de menú situada en la parte superior del diagrama de Sankey.

- Añadir: Seleccione Editar dimensiones y utilice la casilla de verificación situada junto a la dimensión que desee añadir. En cuanto al rendimiento, Cloudability recomienda no añadir múltiples dimensiones demasiado rápido, ya que se podría alcanzar el límite de frecuencia
- Eliminar: Seleccione Editar dimensiones y utilice la casilla de verificación situada junto a la dimensión requerida, o seleccione el botón Eliminar situado junto a la dimensión.
- Reordenar: El orden de las dimensiones se puede cambiar en el diagrama de Sankey modificando el orden en el menú. Seleccione y mantenga pulsados los puntos situados junto al nombre de la dimensión y, a continuación, arrástrelo a la nueva posición.

Más información sobre [Glosario de dimensiones y métricas de costes](glossary-of-cost-dimensions-and-metrics.html)

Más información sobre [Glosario de dimensiones y métricas de utilización](glossary-of-utilization-dimensions-and-metrics.html)

Recomendaciones **de optimización**

Ver recomendaciones

Cuando desee centrarse en un nodo específico y ver las recomendaciones individuales para esa dimensión:

1. Seleccione el nodo en el diagrama de Sankey
2. Seleccionar recomendaciones de visualización

   La tabla de recomendaciones se muestra debajo del diagrama de Sankey, con las recomendaciones para el nodo que ha seleccionado.

   Para descargar una copia de estos datos, seleccione ![Icono de notas](../../../../03-media/cloudability-premium/images/download_button.jpg)

Configurar la tabla

- Para ordenar las columnas de la tabla según sea necesario, seleccione y mantenga pulsado el título de la columna y arrástrelo a la ubicación deseada.
- Para ordenar los datos según una columna, seleccione el encabezado de la columna.

Ver detalles de la recomendación

1. Selecciona los tres puntos situados a la derecha de la recomendación
2. Seleccionar Ver detalles

Puede ver los detalles de las recomendaciones.

## Preguntas frecuentes sobre el redimensionamiento avanzado

¿Con qué frecuencia se actualizan las recomendaciones de optimización?

Actualizamos las recomendaciones de optimización cada hora. Puede acceder a las recomendaciones de recursos 24 horas después de que se haya creado el recurso, siempre que haya suficientes datos de utilización.

**Tema principal:** [Redimensionamiento avanzado](../product/advanced-rightsizing-powered-by-turbonomic.html)
