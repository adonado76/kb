---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una columna calculada a una tabla"
breadcrumb: []
source_path: "studio/reports/tables/add-calculated-column.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep183.png"
  - "resources/images/studio_images/studioimages/reports/rep217.png"
  - "resources/images/studio_images/studioimages/studio/aug435.png"
  - "resources/images/studio_images/studioimages/studio/aug436.png"
  - "resources/images/studio_images/studioimages/studio/aug456.png"
  - "resources/images/studio_images/studioimages/studio/aug457.png"
  - "resources/images/studio_images/studioimages/studio/stu613.png"
  - "resources/images/studio_images/studioimages/studio/stu614.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una columna calculada a una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Si ha añadido campos al área **Valores** del panel **Configuración de componentes**, puede añadir columnas calculadas a la tabla basándose en los valores. Existen tres tipos de columnas calculadas:

- **Valores** - Son valores calculados a partir de una columna existente en la tabla. Algunos ejemplos son Recuento, Porcentaje y Suma. Los cálculos disponibles dependerán de la columna que seleccione.
- **Comparación** - Compara los valores de una columna con los mismos valores de otro proyecto. Esto es útil para las comparaciones interanuales.
- **Varianza** - Muestra la diferencia entre dos columnas de la tabla.

## Añadir una columna de valores

1. Selecciona la tabla.
2. En el panel **Configuración de componentes**, haga clic con el botón derecho del ratón en un campo del área **Valores** y haga clic en **Configuración del campo de valor**. La aplicación muestra el cuadro de diálogo **Configuración del campo de valor** que se muestra en la siguiente imagen:

   ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep183.png)
3. Seleccione el tipo de cálculo. Para una descripción de los tipos de cálculos, véase más abajo *Tipos de cálculos*.
4. Si desea sustituir una columna existente por los valores calculados, desactive la opción **Añadir un nuevo campo de valor**.

## Tipos de cálculos

Los cálculos disponibles dependen del valor seleccionado. A continuación se describen algunos de los tipos de cálculo más habituales. Para ver una descripción emergente de un cálculo en el producto, pase el puntero del ratón sobre el nombre del cálculo.

- **Recuento** - Devuelve el número de entradas representadas por una fila. En las tablas no agrupadas, el valor será 1. En las tablas agrupadas, será el número de entradas representadas por una entrada varios () en la columna de origen. En la siguiente imagen se muestra un ejemplo.

  ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu613.png)
- **Porcentaje** - Añade una columna a la tabla que muestra el porcentaje que cada entrada de una columna contribuye al valor total de la columna. El nombre por defecto de la columna será el nombre de la columna original seguido del signo %. En la siguiente imagen se muestra un ejemplo.

  ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug436.png)
- **Iconos** de umbral - Muestra iconos rojos y verdes en función de un valor de umbral. Se muestra un icono rojo para los valores por debajo del umbral. Se muestra un icono verde para los valores superiores al umbral. A continuación se muestra un ejemplo. El nombre por defecto de la columna será el nombre de la columna original seguido de la letra T:

  ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug435.png)
- **Flechas de cero** - Muestra una flecha hacia arriba para valores mayores que cero, una flecha lateral para valores iguales a cero y una flecha hacia abajo para valores menores que cero.

  ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug457.png)
- **Sparkline Trend** - Muestra un pequeño gráfico de tendencias que abarca los últimos seis meses. En la siguiente imagen se muestra un ejemplo.

  ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug456.png)

## Añadir una columna de comparación entre proyectos

Para comparar cifras entre proyectos, añada a la tabla una columna de comparación entre proyectos. Por ejemplo, puede que desee comparar los costes de servidor del proyecto actual con los costes de servidor del año anterior. Las columnas de comparación deben basarse en una métrica.

Para añadir una columna de comparación:

1. Seleccione una columna de la tabla y haga clic en el icono **Comparación** de la **pestaña Fórmulas**, o haga clic con el botón derecho del ratón en el encabezado de una columna y seleccione **Añadir columna de comparación** en el menú emergente. La aplicación muestra el diálogo que aparece en la siguiente imagen

   ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu614.png)
2. Introduzca un nombre para la nueva columna.
3. Seleccione el proyecto de origen en la lista desplegable.
4. Seleccione la opción de visualización: valor de origen o difference.You puede añadir tanto una columna de origen como una de diferencia en la misma tabla.
5. Pulse **Aceptar**.

## Añadir una columna de desviación

Una columna de varianza calcula la diferencia entre dos columnas de una tabla. Por ejemplo, si en una tabla tiene una columna de presupuesto y otra de datos reales, puede añadir una columna de desviación para mostrar la diferencia.

Para añadir una columna de desviación:

1. Mantenga pulsada **la tecla Ctrl** y seleccione las dos columnas de la tabla. La segunda columna que seleccione se restará de la primera columna seleccionada.
2. Haga clic en el icono **Varianza** de la pestaña **Fórmulas**. La aplicación muestra el cuadro de diálogo **Crear nueva columna** que se muestra en la siguiente imagen. Resta el valor de la segunda columna de la primera columna de la primera columna.

   ![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep217.png)
3. Introduzca un nombre para la columna.
4. Revise la fórmula y modifíquela si procede.
5. Seleccione el formato de la columna. El **separador de agrupación** es el carácter que pone "miles"
6. Selecciona un tipo.
   - **Automático** : La aplicación elige un formato en función del contenido de la columna.
   - **Numérico** : Número entero o real.
   - **Etiqueta** : Texto. No se pueden realizar operaciones matemáticas en las columnas de etiquetas.
   - **Fecha** : Información de la fecha.
7. Si procede, marque la opción **Sumable**. Cuando está marcada, especifica que la columna se puede sumar de forma segura cuando se agrupa o totaliza. Normalmente, los valores se recalculan. Esto permite que una búsqueda global (que hace referencia a la clave que se utiliza para agrupar los datos) totalice correctamente. No seleccione esta opción si la fórmula de valor realiza cálculos, o el resultado será incorrecto. Si tiene previsto añadir subtotales a la tabla y no desea que se muestren subtotales para la columna, deje este campo sin marcar.

## Añadir una columna separadora

Si desea insertar una columna **espaciadora** en blanco en una tabla por razones estéticas, seleccione la tabla, haga clic en la pestaña **Datos** y haga clic en **Insertar columna espaciadora** en el menú del icono **Insertar**.
