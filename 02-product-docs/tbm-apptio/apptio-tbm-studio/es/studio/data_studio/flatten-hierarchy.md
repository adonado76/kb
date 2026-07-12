---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Aplanar una jerarquía de datos"
breadcrumb: []
source_path: "studio/data_studio/flatten-hierarchy.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu285.png"
  - "resources/images/studio_images/studioimages/studio/stu286.png"
  - "resources/images/studio_images/studioimages/studio/stu287.png"
  - "resources/images/studio_images/studioimages/studio/stu288.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Aplanar una jerarquía de datos

**Se aplica a** : TBM Studio 12.0 y posteriores

Si está trabajando con una tabla que tiene datos jerárquicos y una columna padre y una columna hija, y coloca esa tabla en un informe, tendrá limitadas las capacidades de corte. Para proporcionar a los usuarios la máxima flexibilidad en el uso de las rebanadoras, aplane el conjunto de datos añadiendo un paso Aplanar jerarquía a la cadena de transformación. Esta función añade columnas a la transformación del conjunto de datos (una columna por cada nivel de la jerarquía). A continuación, puede crear rebanadoras para cada una de las columnas.

## Ejemplo

El conjunto de datos que se muestra en la siguiente imagen se basa en una jerarquía geográfica. Si crea un informe a partir del conjunto de datos y añade cortadores para las columnas **Padre** e **Hijo**, obtendrá el informe que se muestra en la siguiente imagen:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu285.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu286.png)

Supongamos que quiere ver todas las entradas de Estados Unidos. Si selecciona **EE.UU.** en la rebanadora **Padre**, obtendrá el resultado que se muestra en la siguiente imagen:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu287.png)

Pero, ¿y si quiere que los usuarios puedan ver todas las entradas asociadas a EE.UU.? Puede conseguirlo aplanando la jerarquía mediante la función **Aplanar jerarquía**. La función **Aplanar jerarquía** toma la información de una columna **padre** y una columna **hija** y añade columnas de nivel que pueden utilizarse con rebanadoras. El resultado se muestra en la siguiente imagen. Al aplanar la jerarquía, se proporciona a los usuarios la máxima flexibilidad a la hora de utilizar las cortadoras.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu288.png)

Para que la función **Aplanar jerarquía** funcione correctamente:

- Cada combinación padre-hijo debe ser única. Si hay combinaciones duplicadas, aparecerá un mensaje de error en las nuevas columnas generadas.
- Para cada combinación padre-hijo, el hijo no puede tener más de un padre.
