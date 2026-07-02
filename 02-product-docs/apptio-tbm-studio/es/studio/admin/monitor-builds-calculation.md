---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Supervisar las construcciones con la cola de cálculo"
breadcrumb: []
source_path: "studio/admin/monitor-builds-calculation.html"
images:
  - "resources/images/studio_images/build-tab.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Supervisar las construcciones con la cola de cálculo

◆ Se aplica a: TBM Studio 12.2 y posteriores. Utilice la tabla Cola de Cálculo para supervisar el estado de las compilaciones para los entornos (Desarrollo, Puesta en Escena y Producción) en su dominio.

Puede acceder a la Cola de Cálculo desde la pestaña **Construir**.![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-tab.png)

Cada vez que un usuario registra un documento, se inicia automáticamente una compilación en los entornos de desarrollo y ensayo. La compilación incorpora todos los documentos registrados desde la última compilación y actualiza todos los números calculados en el proyecto.

Las compilaciones en los entornos de desarrollo y de puesta en escena pueden tener lugar simultáneamente, pero ejecutarlas al mismo tiempo puede provocar un retraso entre las dos compilaciones y que los números de compilación no coincidan. Además, el número de compilación para el entorno de producción podría ser significativamente diferente en función de la frecuencia con la que el entorno de pruebas se transfiere al entorno de producción.

## Comprender las columnas de la tabla

La columna **Estado** muestra uno de los siguientes estados:

- **Pendiente** - Una compilación está en cola y a la espera de ser procesada.
- **Calculando** - Hay una construcción en curso. Junto a este estado se muestra el número de cálculos completados frente al número total de cálculos. En el ejemplo anterior, se completan 140 cálculos de un total de 6.337.
- **Finalizado** - La construcción se ha completado. Junto a este estado se muestra el tiempo transcurrido desde que finalizó la compilación y, entre paréntesis, la duración de la misma.

La columna **Cambios** enumera todos los check-ins procesados durante la compilación.

Para ordenar la tabla por los valores de una columna, seleccione la cabecera de la columna y, a continuación, seleccione una opción de ordenación.

Para mostrar sólo las filas con un determinado valor en una columna, introduzca el texto en el campo de búsqueda situado debajo de cada encabezado de columna.

Nota: Si se encuentra en el proyecto de Bienvenida, la Cola de Cálculo no muestra los entornos (Desarrollo, Puesta en Escena y Producción) en la parte superior de la Cola de Cálculo porque el proyecto de Bienvenida no tiene entornos.

## Preguntas más frecuentes

**¿Qué es Precision Calc?**

El cálculo de precisión es una nueva mejora del rendimiento que reduce el tiempo de cálculo de los cambios que se han registrado. Precision Calculation utiliza la información de linaje para comprender mejor los impactos específicos de los cálculos en función de los tipos de cambios realizados: por ejemplo, cargas de tablas, cambios en los esquemas de datos, transformaciones, métricas calculadas, perspectivas, informes, ajustes del proyecto, etc. En la función Cola de Cálculo, los administradores verán:

- Tiempos de cálculo más rápidos que antes Cálculos de precisión
- Mayor variación en los tiempos de cálculo para distintas construcciones.

**¿Cómo se activa esta función?**

Esta función se activa automáticamente para todos los clientes a partir de la versión Server 12.10.10.1.

**¿Con qué rapidez calcula el tiempo?**

Las construcciones con cambios de "sólo informe" o cambios que no afecten al modelo de cálculo se completarán en segundos. Las construcciones con otros tipos de cambios se calcularán y completarán más rápido que antes. El cálculo de precisión no reducirá el tiempo necesario para realizar un cálculo completo tras un reinicio de instancia con borrado de caché.

**¿Afectará a las optimizaciones realizar cambios en la configuración de la interfaz de usuario?**

Los siguientes cambios en la interfaz de usuario no afectarán a los datos calculados

- Cambiar la especificación de color
- Cambiar el tamaño de página por defecto
- Activar pestañas de aplicación
- Conmutar el espacio de trabajo de autocálculo
- Activar las descripciones de entrada obligatorias
- Cerrar / Reducir el número de periodos calculados
- Cambio de la configuración del proyecto para activar la interfaz de usuario Apex

**¿Cómo optimiza los cálculos?**

El servidor optimizará los cálculos para procesar únicamente las áreas afectadas por los cambios registrados

**¿Cómo puedo optimizar esta función?**

Sustituya el uso de la función [Eval()](../formulas-and-functions/functions/eval.htm "(se abre en una pestaña o una ventana nueva)") por [DynamicColumn( ) para beneficiarse de las mejoras de rendimiento de Precision Calc.](../formulas-and-functions/functions/dynamic-column.htm "(se abre en una pestaña o una ventana nueva)")

Para maximizar las mejoras en el rendimiento de calc de la nueva función "cálculos de precisión", la funcionalidad de la función Eval() se sustituye por DynamicColumn( ) u otros cambios en el código. Los clientes que aún tengan Eval() en la configuración de su proyecto, pueden realizar los cambios necesarios utilizando el documento de [código de sustitución de OOTB Eval(](../formulas-and-functions/updated-eval-formulas.htm "(se abre en una pestaña o una ventana nueva)") ) que contiene información de todos los informes y cambios métricos.

Nota : AVISO: Si ha modificado los informes OOTB, no se eliminará Eval() de los informes de plantillas anteriores (por ejemplo, v104, v105, v106. v107 ).
