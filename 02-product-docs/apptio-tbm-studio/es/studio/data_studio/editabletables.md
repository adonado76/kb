---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas editables: Adaptación a las entradas del usuario"
breadcrumb: []
source_path: "studio/data_studio/editabletables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas editables: Adaptación a las entradas del usuario

**Se aplica a** : TBM Studio 12.6 y posteriores

Las tablas son una forma útil de presentar datos y un elemento habitual en los informes. Existen dos tipos de mesas:

- **Transformar** - Una tabla de transformación es una tabla que puede completar cálculos potencialmente intensivos en tiempo. Estas tablas pasan por el proceso de cálculo Apptio, y pueden recibir datos de tablas editables. Son visibles en la sección **Tablas** del **Explorador de proyectos**.
- **Editables** - Las tablas editables permiten a los usuarios introducir datos en las tablas. Se utiliza una tabla editable para introducir datos que se mantienen directamente en la base de datos del proyecto Apptio. La tabla se utiliza generalmente para apoyar la introducción manual de datos para los que no existe otro sistema fuente. Por ejemplo, para asignar otros grupos de costes a las torres de recursos informáticos.

  [Más información sobre tablas editables](enter-data-manually.html "Se aplica a: TBM Studio R12.0 y posteriores")

A continuación se describen las tablas editables. Para obtener detalles sobre las tablas de transformación, consulte [Data Studio : adquirir y transformar datos](about-data-transforms.html "Se aplica a: TBM Studio 12.0 y posteriores").

## Copiar y pegar datos entre Excel y las tablas de la aplicación

Puedes copiar y pegar datos entre Excel y una tabla editable. Concretamente, puedes:

- Copiar celdas de una tabla editable y pegarlas en Excel.
- Copiar celdas de Excel y pegarlas en una tabla editable.

Se ignora el formato de las celdas. Las celdas pueden pegarse en cualquier lugar de una tabla editable.

Nota: Tanto si empieza en Excel como en una tabla en Apptio, las celdas que copie deben estar en un rango contiguo. Si intenta copiar celdas no adyacentes o un bloque incompleto de celdas, aparecerá un mensaje indicando que la selección no es válida.

## Copiar datos de tablas a Excel

Para copiar datos de una tabla editable a Excel:

1. Seleccione las celdas que desee.
2. Copie las celdas en el portapapeles. En un PC con Windows, pulsa Control+C. En un Mac, pulsa ⌘+C.
3. En Excel, pegue las celdas en el libro.

## Copiar celdas de Excel a una tabla editable

Para copiar datos de Excel a un conjunto de datos sin procesar o a una tabla editable de un informe:

1. En Excel, copia las celdas.
2. Visualizar el informe o conjunto de datos de destino.
3. Realiza una de las siguientes acciones:
   - Para pegar nuevas filas de datos, seleccione **Añadir fila** y, a continuación, seleccione la celda situada más a la izquierda de la nueva fila.
   - Para reemplazar los datos existentes, haga clic para seleccionar la celda superior izquierda del rango que desea pegar.
4. Pega los datos.

Nota: No hay límite en el número de filas que se pueden copiar o pegar. Si hay demasiadas búsquedas presentes en un informe, o se aplica formato a muchas columnas al intentar pegar más de 100 registros, puede producirse un error. En este caso, se recomienda utilizar la función [de carga de archivos con anexo](https://help.apptio.com/en-us/studio/reports/table-report-upload-component.dita "(se abre en una pestaña o una ventana nueva)").

## Ver las propiedades del conjunto de datos

Las tablas editables tienen propiedades únicas que controlan el comportamiento de edición de cada columna. Para editar las propiedades de la tabla:

1. Selecciona la tabla.
2. Haga clic en la parte de las columnas de la tubería.
3. Haga clic en la columna que desee modificar.

   Nota: La columna **.PK** es una columna de clave primaria generada por el sistema y tiene un conjunto diferente de propiedades que le son específicas. Además, en una tabla generada, muchas propiedades no están disponibles para las columnas que se incluyen desde la tabla base.

La siguiente imagen muestra las propiedades del conjunto de datos que aparecen en el paso **Configurar columnas**. La pestaña aparece cuando se selecciona una tabla editable en el **Explorador de proyectos.**

![](../../resources/images/studio_images/studioimages/studio_configure%20columns_benchmark%20sub-tower.png)

## Propiedades de columna

Esta tabla describe las propiedades del conjunto de datos en el paso **Configurar columnas**.

| Columna | Descripción |
| --- | --- |
| **Patrón de identificación único** | Esta propiedad sólo existe cuando se visualiza la columna **.PK** generada por el sistema. La entrada es un patrón numérico con el que se mostrará el ID de fila único. Un valor de word-0000 hará que los valores PK sean de la forma word-00001 y word-00002. Los patrones numéricos admiten 2 símbolos especiales para representar el número de fila.  - **0** - Un dígito. Utilícelo si desea que la moneda se muestre con dígitos aunque sea 0. Así, 0000 puede utilizarse para mostrar siempre 4 dígitos, con ceros a la izquierda. - **#** - Un dígito. Si el dígito es cero, no se visualiza. |
| **Nombre** | El nombre de la columna. |
| **Descripción** | Introduzca notas sobre esta columna y por qué existe. |
| **Tipo** | Seleccione el tipo de datos que se esperan en las celdas de la columna. Seleccione una de las siguientes opciones del menú desplegable:  - **Etiqueta** - datos de texto sin formato - **Fecha** - datos en formato de fecha. Al seleccionar esta opción, aparecerá un cuadro de diálogo en el que se le pedirá que introduzca el formato de fecha deseado. Consulte la [función DateFormat](../formulas-and-functions/functions/dateformat.html "Convierte una expresión de fecha a un formato de fecha especificado.") para obtener una lista de los formatos permitidos. Nota: La cadena de formato de fecha no debe ir entre comillas. - **Numérico** - datos numéricos que admiten entradas numéricas en la configuración regional del proyecto |
| **Formato de fecha** | Sólo se activa cuando el campo Tipo está seleccionado como Fecha. Una vez seleccionado, puede cambiar el formato actualizando a un formato permitido. Consulte la [función DateFormat](../formulas-and-functions/functions/dateformat.html "Convierte una expresión de fecha a un formato de fecha especificado.") para obtener una lista de los formatos aplicables. |
| **Valores posibles** | Se utiliza para configurar los desplegables de una columna. Esto puede configurarse de cualquiera de estas maneras:  - Una lista de valores delimitada por comas creará una lista a partir de los valores introducidos. - Una fórmula con la sintaxis %tablename /TableFunction[ ]. - Los nuevos caracteres de línea "\n" no son compatibles.  [Más información sobre la configuración de Valores posibles.](table-functions.html "Se aplica a: TBM Studio 12.0 y posteriores") |
| **Valores posibles Contexto** | Proporciona contexto para utilizar texto dinámico dentro de una fórmula de valores posibles. Esto permite configurar funciones avanzadas como los desplegables dependientes. En caso de duda, seleccione **Fila actual**. |
| **Permitir valores no incluidos en la lista de valores posibles** | Si está marcada, el usuario podrá escribir un valor que no esté en la lista de valores posibles y guardar la tabla. Si no está marcada, debe elegir un valor del menú desplegable. |
| **No permitir edición en celda de valores posibles** | Si está marcada, los usuarios no podrán escribir en la columna. Poder escribir es útil, ya que permite filtrar el desplegable. |
| **Valor predeterminado** | Si se especifica, este valor se introducirá automáticamente para cualquier nueva fila que se añada a la tabla. |
| **Valor obligatorio** | Si está marcada, el usuario no podrá guardar ediciones en esta tabla si una fila no ha especificado un valor para esta columna. |
| **Permitir sólo valores únicos** | Si está marcada, el usuario no podrá guardar ediciones en esta tabla si esta columna contiene valores duplicados. |

Consulte [Configurar programa de actualización de tablas](table-update-schedule.html "Se aplica a: TBM Studio 12.6 y posteriores") para publicar información de una tabla editable en una tabla estándar.

- **[Tabla Funciones](../../studio/data_studio/table-functions.html)**  
   **Se aplica a** : TBM Studio 12.0 y posteriores
- **[GROUPBY](../../studio/data_studio/groupby.html)**
- **[Limit\_Columns](../../studio/data_studio/limit-columns.html)**  
   Determina las columnas mostradas en una tabla. Puede limitar las columnas mediante la **cinta de opciones**.
- **[SORT](../../studio/data_studio/sort.html)**  
   Ordena una tabla en una o más columnas especificadas en la tabla. Puede ordenar una tabla utilizando la cinta de opciones. ¡El!La función SORT puede aplicarse utilizando una, dos o más columnas de una tabla.
- **[Configurar el calendario de actualización de tablas](../../studio/data_studio/table-update-schedule.html)**  
   **Se aplica a** : TBM Studio 12.6 y posteriores
