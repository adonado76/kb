---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos en cascada"
breadcrumb: []
source_path: "studio/reports/waterfall-charts.html"
images:
  - "resources/images/studio_images/studioimages/icons/check.png"
  - "resources/images/studio_images/studioimages/reports/rep273.png"
  - "resources/images/studio_images/studioimages/reports/rep291.png"
  - "resources/images/studio_images/studioimages/reports/rep292.png"
  - "resources/images/studio_images/studioimages/reports/rep293.png"
  - "resources/images/studio_images/studioimages/reports/rep295.png"
  - "resources/images/studio_images/studioimages/reports/rep296.png"
  - "resources/images/studio_images/studioimages/reports/rep297.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos en cascada

**Se aplica a** : TBM Studio 12.2 y posteriores

Los gráficos de cascada muestran el impacto de los valores positivos y negativos sobre un valor inicial. Normalmente, los valores primero y último se muestran como columnas enteras. En algunos gráficos, se mostrarán columnas enteras adicionales. Los valores intermedios se muestran entre las columnas enteras, como columnas flotantes que indican cambios positivos y negativos. Los valores intermedios suelen denominarse pasos. Por ejemplo, puede haber columnas enteras para Q1, Q2, Q3, y Q4 con valores intermedios flotantes entre las columnas trimestrales.

En la siguiente imagen se muestra un ejemplo de gráfico en cascada:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep273.png)

Nota: Los valores de los gráficos de cascada se muestran siempre en la moneda base establecida para el proyecto. Los gráficos en cascada no admiten multimoneda.

## Utilizar un gráfico en cascada con múltiples colaboradores

Si está creando un gráfico de cascada y desea que varios colaboradores introduzcan pasos intermedios para el gráfico, puede definir un cortador para el gráfico. Las personas pueden seleccionar un valor de corte e introducir pasos para ese valor. Por ejemplo, desea crear un gráfico en cascada que resuma la variación de los costes en varios departamentos. Quiere que los jefes de cada departamento introduzcan los pasos intermedios de su departamento. Se crea un slicer que muestra los departamentos. Cada jefe de departamento selecciona su departamento e introduce los pasos.

Los pasos que aparecen en el gráfico corresponden al departamento seleccionado en el cortador. Para obtener más información, consulte [Utilizar rebanadoras con gráficos en cascada](#Waterfallcharts__Useslicerswithwaterfallcharts).

Todos los gráficos en cascada deben tener al menos un valor inicial y otro final. Un gráfico también puede tener otros valores intermedios. Por ejemplo, un gráfico puede mostrar sólo los valores iniciales y finales del año, o puede incluir los valores de cada trimestre del año.

## Crear un gráfico en cascada

Para crear un gráfico de cascada con un valor inicial y otro final:

1. Haga clic en la pestaña **Informe**.
2. Haga clic en el icono **Cascada**. Se añade un marcador de posición de gráfico al informe y se muestra el panel **Configuración de cascada**.
3. En el panel **Configuración del gráfico de cascada**, seleccione un objeto modelo de la lista desplegable situada en la parte superior del panel.
4. En la sección **Métricas** del **Explorador de proyectos**, arrastre una métrica modelada al área **Valores** del panel.
   - Por defecto, el periodo de tiempo actual se introduce en el área **Hora** del cuadro de diálogo. Si desea cambiar el período de tiempo, abra el selector de fechas de la cabecera y seleccione un período de tiempo diferente y, a continuación, cree el gráfico. Los periodos de tiempo para todos los valores base deben ser los mismos.
5. Arrastre una segunda métrica modelada al área **Métricas**.
   - Como antes, se introduce el Mes en curso en el área **Hora**. Los gráficos de cascada pueden mostrar un cambio de valor a lo largo del tiempo. Para ello, cambie uno de los ajustes del Mes en curso a un periodo de tiempo diferente.
6. Para cambiar el periodo de tiempo, haga clic con el botón derecho del ratón en el periodo de tiempo y pulse **Mayús**.
7. Introduzca un número positivo o negativo que represente el número de periodos a desplazar la fecha y pulse **OK**. Por ejemplo, suponga que sus periodos son meses y que el mes actual es enero de 2013. Si introduce +5, el mes será junio de 2013.
8. Si procede, añada columnas adicionales que representen otros periodos de tiempo (véase [Añadir valores intermedios](#Waterfallcharts__Addintermediatevalues) más abajo).
9. El gráfico mostrará ahora las columnas inicial y final, y una columna intermedia llamada Inexplicado. La columna Sin explicación representa el cambio de valor entre las columnas inicial y final. El siguiente paso consiste en sumar los valores intermedios.

## Añadir valores intermedios

La tabla de pasos intermedios muestra los valores intermedios que han contribuido al cambio entre los valores inicial y final. Lo ideal es que los valores intermedios representen el cambio total entre los valores inicial y final. Cualquier valor no identificado en un paso intermedio se mostrará en una columna llamada **Inexplicado**. Los valores intermedios deben añadirse en el entorno de Producción. Los valores intermedios pueden aplicarse a valores específicos de la cortadora.

Para añadir valores intermedios:

1. Cambie al entorno de producción.
2. Abra el informe con el gráfico de cascada.
3. Haga clic en el botón **Añadir explicación** situado en la parte inferior de la tabla de pasos intermedios**.NOTA** : Las explicaciones se almacenan en la base de datos de Planificación de TI. Si no se ha instalado la base de datos de Planificación informática, no podrá añadir explicaciones.
4. En la fila en blanco añadida a la tabla:
   - Introduzca una etiqueta para el paso en la columna **Paso**.
   - Introduzca un valor positivo o negativo en la columna **Valor**.
   - Introduzca una explicación en la columna **Explicación**.
5. Continúe añadiendo valores intermedios según sea necesario.
6. Puede cambiar el orden de los pasos intermedios entre valores base haciendo clic con el botón derecho del ratón y, a continuación, haciendo clic en **Mover hacia arriba** o **Mover hacia abajo**.

## Filtrar el gráfico

Puede aplicar filtros fijos al gráfico de cascada añadiendo uno o varios campos de datos al área **Filtros** del panel Configuración de cascada. Si quieres dar a los usuarios la posibilidad de seleccionar sus propios filtros, crea un slicer para el gráfico de cascada. Para obtener más información sobre la aplicación de rebanadoras, consulte [Utilizar rebanadoras con gráficos en cascada](#Waterfallcharts__Useslicerswithwaterfallcharts).

Para aplicar filtros fijos al gráfico:

1. Arrastre un campo relevante de la perspectiva **Datos** o de una perspectiva personalizada al área **Filtros**.
2. Haga clic con el botón derecho en la entrada del filtro y haga clic en **Editar filtro**.
3. En el cuadro de diálogo **Editar filtro**, realice sus selecciones y haga clic en **Aceptar**.
4. Para añadir más filtros, repita los pasos anteriores.

## Ocultar la tabla de pasos intermedios

La tabla de pasos intermedios es útil cuando se construye un gráfico de cascada, pero probablemente querrá ocultar la tabla a los usuarios que vayan a ver el gráfico de cascada.

Para ocultar la tabla de pasos intermedios:

1. Haga clic en la pestaña **Cascada**.
2. Desactive la opción **Mostrar tabla**.

## Cambiar los colores del gráfico de cascada

Puede cambiar los colores por defecto utilizados en un gráfico de cascada.

1. Haga clic en la pestaña **Cascada** y, a continuación, en el icono **Colores**.
2. Haz clic en el cuadrado de color a la derecha de cada elemento y haz clic en un color.

Puede cambiar el color de un valor individual en un gráfico de cascada.

1. Seleccione el gráfico.
2. Haga clic en el icono **Colores** de la pestaña **Cascada**. Aparece el cuadro de diálogo de selección de color.
3. Haz clic en **Añadir**.
4. Haga clic en **Llave**.
5. Introduzca el nombre del valor tal y como aparece en la columna Paso.
6. Haga clic en el icono de guardar ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/check.png).
7. Haga clic en el icono de color personalizado ![imagen](../../resources/images/studio_images/studioimages/icons/custom%20color.png) y seleccione un color.
8. Pulse **Guardar**.
9. Para eliminar un color personalizado, haga clic en la x roja delante del nombre del paso y haga clic en **Guardar**.

## Configurar las opciones del gráfico en cascada

Al crear un gráfico de cascada, se añade una pestaña **Cascada**. En esta pestaña, hay varias opciones que puede aplicar al gráfico.

- **Mostrar tabla** - Cuando está marcada, muestra la tabla explicativa debajo del gráfico. Si desea que los usuarios puedan editar el gráfico de cascada, muestre la tabla de explicaciones. Si la tabla de explicaciones está oculta, los usuarios podrán ver el gráfico pero no editarlo.
- **Mostrar filas detalladas** - Muestra los pasos intermedios asociados a valores específicos de la cortadora. Los pasos se muestran en la parte inferior de la tabla de pasos y son de sólo lectura.
- **Explicación en la información sobre herramientas** : cuando está marcada, muestra el texto del campo **Explicación** en la información sobre herramientas de las barras del gráfico de cascada.
- **Número** - Dé formato a los números de un gráfico de cascada utilizando las opciones de **Número**.

## Utilizar cortadoras con gráficos en cascada

Las rebanadoras filtran los valores mostrados en un gráfico de cascada. Cuando se utilizan cortadoras, los pasos intermedios pueden mostrarse u ocultarse en la tabla de pasos. Las rebanadoras y las rebanadoras jerárquicas tienen efectos ligeramente diferentes en los gráficos de cascada.

Las rebanadoras pueden limitar los valores utilizados para generar un gráfico de cascada. Sin embargo, cuando un usuario selecciona un valor en un slicer, los pasos intermedios se sustituyen por una única columna **Sin explicación** en el gráfico. Si desea que un usuario vea los pasos intermedios, seleccione la opción **Mostrar filas detalladas** en la pestaña **Cascada** del gráfico.

Nota: Los cortadores numéricos y temporales no afectan a los gráficos en cascada.

## Cortadoras

Si un usuario selecciona un conjunto de valores de corte y, a continuación, introduce pasos intermedios en un gráfico de cascada, los pasos sólo se podrán editar cuando se seleccione el mismo conjunto de valores de corte. Si el usuario selecciona un conjunto diferente de valores de la cortadora, o borra todas las selecciones en la cortadora, los pasos intermedios se muestran como entradas de sólo lectura debajo de la entrada Sin explicación en la tabla de pasos.

Por ejemplo, en la siguiente imagen, se han introducido los pasos Salarios, Telecomunicaciones, Software y Hardware para el centro de datos de Chicago. Cuando se selecciona Chicago en la cortadora, las entradas son editables en la tabla de pasos. La columna **Contexto** muestra el filtro aplicado por el cortador. Cada paso está representado por una barra en el gráfico:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep291.png)

Si se anula la selección de Chicago en la cortadora, los pasos pasan a ser de sólo lectura y se mueven por debajo de la entrada Inexplicado en la tabla de pasos, como se muestra en la siguiente imagen. Las entradas de la columna **Contexto** describen la configuración de la cortadora que es el origen del paso. En el gráfico aparece una única barra **inexplicada**. Puede convertir un paso de sólo lectura en un paso editable haciendo clic con el botón derecho del ratón sobre el paso y seleccionando **Copiar a explicación**.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep292.png)

Si la opción **Mostrar filas detalladas** de la pestaña **Cascada** del gráfico no está seleccionada, la tabla de pasos no mostrará los pasos como se muestra en la siguiente imagen:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep293.png)

## Cortadoras jerárquicas

Las rebanadoras jerárquicas actúan de forma muy parecida a las rebanadoras normales, salvo que cuando se selecciona un elemento en una rebanadora jerárquica, se muestran todas las explicaciones introducidas en el nivel actualmente seleccionado de la rebanadora o en un nivel inferior de la jerarquía. Las explicaciones introducidas en el nivel actualmente seleccionado son editables. Las explicaciones introducidas en niveles inferiores son de sólo lectura.

## Ejemplo de gráfico de cascada multiusuario

El Departamento de TI de la empresa ABC desea utilizar un gráfico en cascada para mostrar la variación de los costes durante el primer semestre del año. El vicepresidente construirá el gráfico base y hará que el responsable de cada centro de datos introduzca explicaciones sobre los cambios en sus centros de datos. Se creará un slicer del centro de datos que los responsables podrán utilizar para filtrar el gráfico de cascada de su centro de datos. Después de que los jefes hayan introducido la información de sus pasos, el Vicepresidente del Departamento de TI unificará las explicaciones en unos pocos valores clave.

Hay cinco centros de datos: Chicago, Dallas, Nueva York, Phoenix y Seattle.

Hay cuatro centros de costes: Salarios, Telecomunicaciones, Software y Hardware.

## Construir el gráfico base

El VP construye el gráfico base y crea el slicer del centro de datos como se muestra en la siguiente imagen. Selecciona la opción **Mostrar filas detalladas** para el gráfico de cascada.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep295.png)

## Entrar en el centro de datos Pasos intermedios

El responsable del centro de datos de Chicago entra en Apptio y abre el gráfico de cascada. Selecciona Chicago en la cortadora. Introduce sus pasos intermedios como se muestra en la siguiente imagen. Los responsables de los demás centros de datos hacen lo mismo.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep296.png)

## Elaborar el gráfico final

Una vez que los responsables de los centros de datos han introducido los pasos intermedios, el vicepresidente combina los datos y crea un único paso intermedio para cada centro de coste. El gráfico final se muestra en la siguiente imagen:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep297.png)
