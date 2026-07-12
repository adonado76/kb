---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una columna de fórmulas a una tabla"
breadcrumb: []
source_path: "studio/reports/tables/add-formula-column-to-table.html"
images:
  - "resources/images/studio_images/studioimages/icons/formula-save.png"
  - "resources/images/studio_images/studioimages/reports/rep164.png"
  - "resources/images/studio_images/studioimages/reports/rep340.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una columna de fórmulas a una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede añadir una columna de fórmulas a una tabla. La columna puede basarse en una fórmula personalizada, en las columnas del conjunto de datos que respaldan la tabla o en un valor modelado. Por ejemplo, es posible que desee realizar algunos cálculos complejos basados en dos o más columnas de la tabla. Cuando haga referencia a columnas de una tabla, asegúrese de utilizar el formato table.column para los nombres de columna.

## Añadir una columna de fórmulas

Una columna de fórmula obtiene valores de otras columnas de la tabla y de cálculos. Cuando haga referencia a columnas de una tabla, asegúrese de utilizar el formato table.column para los nombres de columna.

Para añadir una columna de fórmulas a una tabla:

1. Selecciona la tabla.
2. En la pestaña **Datos**, abra el menú **Insertar** y haga clic en **Insertar columna de fórmula**. Aparecerá el cuadro de diálogo **Crear nueva columna**, como se muestra en la siguiente imagen:![Crear nueva columna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep164.png)

   Nota: Si hace clic en **Insertar** en los **Datos** en lugar de abrir el menú, se añadirá a la tabla una columna en blanco llamada **MyNewColumn** a la tabla. Para añadir una fórmula a la columna, haga clic en el nombre de la columna para resaltarla y, a continuación, haga clic en **Editar** en la pestaña **Datos**.
3. Rellene los campos con la información que figura en el cuadro siguiente.
   - **Nombre** - Acepta todos los caracteres alfanuméricos estándar.
   - **Introducir fórmula** - Cualquier fórmula que siga la sintaxis de fórmulas del informe. Cuando utilice columnas en las fórmulas, asegúrese de utilizar el formato *table.column* para el nombre de una columna. Cuando empiece a escribir en el campo, la aplicación mostrará una lista de valores que coinciden con lo que ha escrito. Para más información, consulteSintaxis [de fórmulas y funciones](../../formulas-and-functions/syntax-for-formulas-and-functions.html "Se aplica a: TBM Studio 12.0 y posteriores"). Tenga en cuenta que la tabla editable enriquecida admite la selección de la columna Fórmula como clave principal.
   - **Valor de texto** : seleccione esta opción para utilizar los datos de una columna de texto de la tabla.
   - **Valor numérico** : seleccione esta opción para usar datos de una columna numérica de la tabla. **Valor modelado** : seleccione esta opción para usar datos de un controlador. Esta opción sólo está disponible para las tablas de los informes de objetos generados automáticamente**.Formato** - Seleccione el formato adecuado. Si selecciona **Avanzado**, puede introducir una fórmula que establezca el formato.
   - **Formato** - Seleccione el formato adecuado. Si selecciona **Avanzado**, puede introducir una fórmula que establezca el formato.
   - **Tipo** - Seleccione uno de los cuatro tipos de columna:
     - **Automático** - La aplicación elige un formato en función del contenido de la columna.
     - **Numérico** - Número entero o real.
     - **Etiqueta** - Texto. No se pueden realizar operaciones matemáticas en las columnas de las etiquetas
     - **Fecha** - Información sobre la fecha.
   - **Sumable** - Cuando está marcada, especifica que la columna se puede sumar de forma segura cuando se agrupa o totaliza. Normalmente se recalculan los valores. Esto permite que una búsqueda global (que hace referencia a la clave que se utiliza para agrupar los datos) totalice correctamente. No seleccione esta opción si la fórmula de valor realiza cálculos, o el resultado será incorrect.If. Si tiene previsto añadir subtotales a la tabla y no desea que se muestren subtotales para la columna, deje este campo sin marcar.

## Editar una columna de fórmulas

Si ha añadido una columna de fórmulas a una tabla, puede editar la columna seleccionándola y haciendo clic en **Editar** en la pestaña **Datos**. La aplicación muestra el cuadro de diálogo **Editar columna**, que es idéntico al cuadro de diálogo **Crear nueva columna** mostrado en la Figura A anterior. Tenga en cuenta que para las columnas numéricas, de moneda y de porcentaje, puede establecer el número de decimales. La opción **Utilizar separador de agrupación** añade el separador de "miles" apropiado (coma, punto o espacio) al número en función de la configuración regional del proyecto.

## Editar una fórmula

Puede editar la fórmula de una columna utilizando la barra de fórmulas del panel de edición del informe, como se muestra en la siguiente imagen. A medida que edite la fórmula, aparecerá una lista de funciones, nombres de objetos, tablas y columnas disponibles. Seleccione una entrada de la lista con el ratón o desplácese hasta ella y pulse el tabulador. Para guardar una fórmula, haga clic en el icono de guardar ![Fórmula Ahorro](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/formula-save.png) situado a la izquierda de la barra de fórmulas.

![Editar una fórmula](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep340.png)

## Ocultar una columna de fórmulas

Puede ocultar una columna de fórmulas que haya añadido a una tabla. Para ocultar una columna, haga clic con el botón derecho del ratón en la columna del área **Filas** o **Valores** del panel **Configuración competente** y seleccione **Ocultar**.

## Borrar una columna de fórmulas

1. Selecciona la tabla.
2. En el cuadro de diálogo **Configuración de componentes**, arrastre el nombre de la columna fuera del área **Valores**.
