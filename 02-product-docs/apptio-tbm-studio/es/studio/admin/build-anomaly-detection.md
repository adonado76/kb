---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Construir la detección de anomalías"
breadcrumb: []
source_path: "studio/admin/build-anomaly-detection.html"
images:
  - "resources/images/studio_images/anol-det.png"
  - "resources/images/studio_images/anomalies-banner.png"
  - "resources/images/studio_images/anomalies-settings.png"
  - "resources/images/studio_images/build-anomaly.png"
  - "resources/images/studio_images/enable-calculation-effort.png"
  - "resources/images/studio_images/yes-no-anaomaly.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Construir la detección de anomalías

La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones. Esta función se basa en los datos recogidos por Calc Explorer, que proporciona información detallada sobre el esfuerzo de cálculo de cada construcción.

La función de detección de anomalías utiliza los datos de Calc Explorer para identificar cambios inusuales en el esfuerzo de cálculo. Compara el esfuerzo de cálculo de cada compilación con el de las anteriores e identifica cualquier cambio significativo. Si se detecta un cambio significativo, la función le avisará y le proporcionará información detallada sobre el cambio.

## Ventajas de la detección de anomalías

La función de detección de anomalías puede ayudarle:

- Identificación y optimización de informes y transformaciones ineficaces
- Reduzca el esfuerzo de cálculo y mejore el rendimiento
- Mejore la calidad general y la fiabilidad de sus informes y transformaciones

## Cómo utilizar la detección de anomalías

Para activar la función de detección de anomalías, haga lo siguiente:

1. Vaya a **Proyecto** > **Habilitar características** y seleccione la casilla **Mostrar panel de anomalías**.
2. Vaya a **TBM Studio** > **Proyecto** > pestaña **Anomalías**.

   ![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/build-anomaly.png)
3. Amplíe el tipo de anomalía e investigue las anomalías detectadas.

   ![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anol-det.png)

   Cuadro 1.

   | Campo | Descripción |
   | --- | --- |
   | Iniciado | Muestra la fecha de inicio del cálculo |
   | Explorador de cálculos | Enlaces a la calc que presentaba la anomalía |
   | Conjunto de cambios | Enlaces a la lista de transformaciones y entidades modificadas con la compilación |
   | Cambios | Enlaces a los mensajes de modificación asociados a la compilación |
4. Tomar las medidas adecuadas para optimizar los informes y las transformaciones según sea necesario.

## Cómo pausar automáticamente el cálculo (Beta)

Se introduce la función Auto-Pausa Cálculos para pausar los cálculos cuando se detecta una anomalía. Para activar esta función,

1. En la pestaña **Anomalías**, seleccione el icono **Configuración**.

   ![Icono de configuración de anomalías](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anomalies-settings.png)
2. En la pestaña **Esfuerzo de cálculo**, active la **pausa automática de los cálculos cuando se detecte una anomalía (Beta)**

   ![Habilitar el esfuerzo de cálculo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enable-calculation-effort.png)
3. Haga clic en **Guardar**

Una vez activada la función y si se detecta una anomalía, aparecerá un banner para confirmar que se ha puesto en pausa el cálculo.

![Mensaje de cabecera](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/anomalies-banner.png)

Cuando resuelva la anomalía, seleccione **Sí** o **No** para desbloquear los cálculos.

![Sí o No](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/yes-no-anaomaly.png)

## Tipos de anomalías

La función puede detectar dos tipos de anomalías:

- **Anomalía de cálculo** : Este tipo de anomalía consiste en un aumento del esfuerzo de cálculo por encima de lo esperado para un calc.
- **Anomalía basada en entidades** : Este tipo de anomalía se produce cuando hay un patrón inusual en la forma de los datos (por ejemplo, un número inusual de filas).
- **Combinadas** : Este tipo de anomalía se produce cuando hay una combinación de anomalías basadas en cálculos y en entidades.

**Anomalías de cálculo**

Se produce una anomalía de cálculo cuando el tiempo de cálculo de una compilación es significativamente superior al habitual. Esto puede deberse a varios factores, como:

- Cargar una gran cantidad de datos, modificar fórmulas o cambiar la configuración de los informes.
- Cambios que aumentan el esfuerzo de cálculo, como añadir nuevos informes o transformaciones.

**Investigación de anomalías de cálculo**

Para investigar una anomalía de cálculo, puede:

- **Ver el conjunto de cambios** : Vea los cambios específicos realizados en la compilación, como los archivos cargados o las fórmulas modificadas.
- **Explorar Calc Explorer** : Analiza el esfuerzo de cálculo de la compilación e identifica las áreas en las que el tiempo de cálculo es superior al habitual.

Con el tiempo, el sistema ofrecerá funciones de explicabilidad que le ayudarán a comprender la causa de la anomalía de cálculo. Esto incluirá información como:

- **Archivos o cambios específicos** : Qué archivos o cambios provocaron el aumento del tiempo de cálculo.
- **Tabla de proporciones de asignación** : cómo los cambios en la tabla de proporciones de asignación afectaron el tiempo de cálculo.

## Resolución de problemas

Si tiene algún problema con la función de detección de anomalías, haga lo siguiente:

- Compruebe los datos de Calc Explorer para asegurarse de que son exactos y están actualizados.
- Investigue las anomalías detectadas y adopte las medidas necesarias para optimizar los informes y las transformaciones.

## Preguntas frecuentes

- P: ¿Para qué sirve la función de detección de anomalías? R: La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones.
- P: ¿Cómo funciona la función de detección de anomalías? R: La función de detección de anomalías utiliza los datos de Calc Explorer para identificar cambios inusuales en el esfuerzo de cálculo. Compara el esfuerzo de cálculo de cada compilación con el de las anteriores e identifica cualquier cambio significativo.
- P: ¿Qué tipos de anomalías puede detectar esta función? R: La función detecta cambios en el esfuerzo de cálculo debidos a cambios de material, aumento del esfuerzo de cálculo o anomalías en la forma de los datos, como valores atípicos, asimetría o cambios de distribución.
