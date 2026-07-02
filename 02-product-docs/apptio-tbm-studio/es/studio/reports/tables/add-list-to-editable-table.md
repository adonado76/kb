---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una lista a una tabla editable"
breadcrumb: []
source_path: "studio/reports/tables/add-list-to-editable-table.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep289.png"
  - "resources/images/studio_images/studioimages/studio/aug257.png"
  - "resources/images/studio_images/studioimages/studio/aug258.png"
  - "resources/images/studio_images/studioimages/studio/aug259.png"
  - "resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-example.png"
  - "resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-raw-table.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una lista a una tabla editable

**Se aplica a** : TBM Studio 12.0 y posteriores

Si desea que los usuarios puedan seleccionar un valor para una celda de una tabla editable, puede añadir una lista a la celda como se muestra en la siguiente imagen. Los valores de la lista se extraen de una columna de la tabla definida en el conjunto de datos.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-example.png)

En una lista, la aplicación muestra los 15 primeros valores únicos de los datos de origen. Si la lista contiene más de 15 valores, aparecerá un botón **Buscar** en la parte inferior de la lista. Al hacer clic en el botón Buscar aparece un cuadro de diálogo en el que el usuario puede seleccionar entre toda la lista de valores.

## Crear una lista básica

1. En la pestaña **Datos**, seleccione el conjunto de datos que es la fuente de la tabla editable.
2. En la pestaña **Editar columnas**, seleccione la columna que suministrará los valores para la lista desplegable que aparece en las celdas.
3. En el campo **Valores posibles** del panel **Detalles de columna**, introduzca una lista de valores separados por comas o introduzca la siguiente fórmula para utilizar una lista de valores de una columna de una tabla:
   - Introduzca una sentencia de selección:`%tablename /TableFunction[ ]`Para los ejemplos mostrados en la imagen anterior, la sentencia de selección es:

     ```
     %Data Center Costs/!LIMIT_COLUMNS[Data
                   Center]
     ```
   - La sentencia de selección utiliza valores de la tabla sin procesar que se muestra a continuación. ¡El!La parte LIMIT\_COLUMNS de la sentencia indica a la aplicación que muestre sólo la columna Centro de datos.

     ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-raw-table.png)
   - Para proporcionar un contexto adicional a los usuarios, puede introducir cualquier número de columnas separadas por comas. La primera columna de la lista será el valor introducido en el ejemplo editable table.For :

     ```
     %Data Center
                   Costs/!LIMIT_COLUMNS[Data Center,Remote Hands Cost, Data Center Power Cost,Data
                   Center Leasing Cost]
     ```
   - En el ejemplo anterior, un usuario puede hacer clic en Buscar... para ver cuatro columnas en un cuadro de diálogo de selección emergente, aunque sólo se almacenará el valor del Centro de datos en la tabla editable.
   - Además, puede utilizar texto dinámico en el campo **Valores posibles** para que los valores mostrados en la lista dependan del valor de una columna de la fila. Para más información, consulte [Generar una lista con texto dinámico](#Addalisttoaneditabletable__Generatealistwithdynamictext).
4. En el campo **Contexto de valores posibles**, seleccione **Informe**.
5. En el panel **Detalles de columna** de la pestaña **Editar columnas**, seleccione la opción **Clave primaria**. ¡Si no desea utilizar la clave primaria de la tabla de datos de consulta, puede utilizar la opción!Función GROUPBY en la sentencia de selección de **Valores Posibles**. La sintaxis es:`%tablename
   /!GROUPBY[column name]`

## Permitir a los usuarios editar una lista

Si desea que los usuarios puedan editar los valores de una lista, cree un conjunto de datos con los valores predeterminados y, a continuación, copie y pegue la tabla del conjunto de datos sin procesar en un informe. La tabla del informe será editable, y los usuarios podrán añadir, editar y eliminar entradas de la tabla. Haga referencia al conjunto de datos en el campo **Valores posibles** al crear la lista.

## Generar una lista con texto dinámico

Una lista puede contener valores basados en el valor de otra columna de la tabla. Por ejemplo, supongamos que desea que los usuarios puedan introducir nuevos nombres de centros de datos junto con el estado y la ciudad en la que se encuentran los centros de datos. Cuando un usuario hace clic en **Añadir fila**, puede introducir un nombre para el centro de datos, seleccionar un estado de una lista desplegable y, a continuación, seleccionar una ciudad dentro del estado seleccionado. Sólo se muestran las ciudades del estado seleccionado. A continuación se indican los tres pasos:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug257.png)

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug258.png)

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug259.png)

Para crear las listas:

1. Cree un conjunto de datos que incluya los estados y las ciudades como se muestra en la siguiente imagen:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep289.png)

   En nuestro ejemplo, el conjunto de datos se denomina Estados-Ciudades.
2. Abra el conjunto de datos que incorporará las listas y seleccione la pestaña **Editar columnas**.
3. Seleccione la columna Estado e introduzca lo siguiente en el campo **Valores posibles** :`%States-Cities/!LIMIT_COLUMNS[State]`Esto muestra los valores de la columna Estado cuando un usuario hace clic en una celda de la columna.
4. Deje el campo **Contexto de valores** posibles en **Informe**.
5. Seleccione la columna Ciudad e introduzca lo siguiente en el campo **Valores posibles** :`%States-Cities/!FILTER[State="<%=State%>"]/!LIMIT_COLUMNS[City]`La parte `!FILTER[State="<%=State%>]` de la sentencia indica a la aplicación que busque el valor en la columna Estado y muestre sólo las ciudades que coincidan con el estado.
6. En el campo **Contexto de valores posibles**, seleccione **Fila actual**.
