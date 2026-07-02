---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de tendencias heredadas"
breadcrumb: []
source_path: "studio/reports/legacy-trend-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendencias heredadas

**Se aplica a** : TBM Studio 12.0 y posteriores

Para los gráficos antiguos, existe una pestaña **Tendencia** en el cuadro de diálogo **Propiedades**. Las propiedades controlan la apariencia del gráfico y los datos mostrados. Los controles incluyen la posibilidad de proyectar valores a lo largo de un número determinado de periodos basándose en datos históricos. Puede añadir proyecciones futuras a los gráficos de tendencias, en los que las proyecciones se basan en un número determinado de meses anteriores.

La pestaña **Tendencia** sólo está disponible para los gráficos antiguos creados con versiones anteriores de la aplicación. Si convierte un gráfico de tendencias en un gráfico heredado, la pestaña no estará disponible.

Las propiedades estándar del gráfico también están disponibles en las otras pestañas del cuadro de diálogo **Propiedades**. Para obtener información sobre las propiedades estándar, consulte [Establecer las propiedades del gráfico](set-chart-properties.htm "(se abre en una pestaña o una ventana nueva)").

**Descripciones de los campos** :

A continuación se describen los campos **Tendencia** :

- Valor de tendencia - La columna utilizada para proporcionar los valores graficados.
- Clave de tendencia - La columna del identificador de la unidad. Este valor debe ser el mismo que el del campo **Etiqueta Eje X** de la pestaña **Gráfico**.
- Rango de tendencia pasada - ¿Hasta dónde quiere que se remonte el gráfico desde el periodo actual? El número introducido se aplicará al periodo actualmente seleccionado: meses, trimestres, años. Por ejemplo, si el periodo seleccionado es de meses e introduce 6 en el campo, el gráfico mostrará el mes actual más los cinco meses anteriores.
- Rango futuro de tendencia: ¿hasta dónde quiere que llegue el gráfico a partir del periodo actual? El número introducido se aplicará al periodo actualmente seleccionado: meses, trimestres, años. Por ejemplo, si el periodo seleccionado es meses y se introduce 6 en el campo, el gráfico mostrará el mes actual más los seis meses siguientes.
- Orden inverso de tendencia - Por defecto, el tiempo en el eje X va del pasado al futuro, de izquierda a derecha. Si selecciona esta opción, el tiempo transcurrirá del futuro al pasado. Por ejemplo, si el gráfico muestra datos de enero de 2010 a diciembre de 2010, el orden inverso mostraría los datos de diciembre de 2010 a enero de 2010.
- Columna Añadir Total de Tendencias - Este campo sólo se aplica a las tablas de tendencias, no a los gráficos de tendencias. Deje este campo en blanco.
- Tendencia Añadir columna media - Este campo sólo se aplica a las tablas de tendencias, no a los gráficos de tendencias. Deje este campo en blanco.
- Rango Futuro de Proyección - El número de periodos de tiempo a proyectar en el futuro basado en el periodo de tiempo actualmente seleccionado. Por ejemplo, si el periodo de tiempo actual es de meses, la proyección será de seis meses en el futuro.
- Rango pasado a utilizar para las proyecciones - El número de periodos de tiempo hacia atrás en el tiempo a utilizar para realizar los cálculos de proyección. Debe ser dos o superior. Si introduce un 0 o 1, la aplicación utilizará el valor del campo **Tendencia Rango Pasado**.
- Unidades a proyectar - Las unidades del gráfico a proyectar. Por ejemplo, si las unidades mostradas en el gráfico son divisiones denominadas Oriental, Central y Occidental, podría elegir proyectar sólo la división Oriental.
- Algoritmo de proyección - Seleccione el algoritmo de proyección que desea utilizar. Se trata de los algoritmos estándar utilizados en el análisis estadístico. El algoritmo por defecto es **Regresión**.
- Grupo Proyección y Tendencia - Este campo sólo se aplica a las tablas de tendencias. Deje este campo en blanco.
- Eliminar valores cero iniciales y finales: elimina los valores cero al principio o al final del gráfico. Esto evita que la línea de tendencia descienda hasta el eje X al principio y al final del gráfico.

## Añadir proyecciones directamente desde un gráfico de tendencias

Si ha creado un gráfico de tendencias heredado y desea proyectar valores en el futuro basándose en los datos existentes en el gráfico, puede añadir una proyección. Para añadir una proyección, haga clic con el botón derecho del ratón en el gráfico y seleccione **Proyectar tendencia** en el menú emergente. La aplicación añadirá una proyección de regresión para un periodo de tiempo equivalente al periodo de tiempo sobre el que se está realizando la tendencia.

Para eliminar la proyección del gráfico, haga clic con el botón derecho del ratón en el gráfico y seleccione **Eliminar proyección** en el menú emergente.

Nota: Las proyecciones no están disponibles para los gráficos Ad Hoc Query.
