---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear un informe"
breadcrumb: []
source_path: "studio/reports/create-a-report.html"
images:
  - "resources/images/studio_images/studioimages/icons/save.png"
  - "resources/images/studio_images/studioimages/reports/rep126.png"
  - "resources/images/studio_images/studioimages/reports/rep339.png"
  - "resources/images/studio_images/studioimages/studio/stu514.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear un informe

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede crear un número ilimitado de informes. Después de crear un informe, puede guardarlo, cambiarle el nombre, restringir las fechas y eliminarlo. Al crear un informe, aparece una pestaña en la parte inferior del área de trabajo. Para crear un informe, vaya a **TBM Studio**, haga clic en la pestaña **Inicio**, en **Nuevo** y, a continuación, en **Informe**.

Vea estos vídeos de Apptio Education Services:

- [Crear un nuevo informe](https://community.apptio.com/videos/1439 "(se abre en una pestaña o una ventana nueva)")
- [Crear un informe de tarifas por unidad](https://community.apptio.com/videos/1894 "(se abre en una pestaña o una ventana nueva)")

O consulte [todos los vídeos de Apptio](https://community.apptio.com/docs/DOC-7714 "(se abre en una pestaña o una ventana nueva)").

## Cómo afectan las funciones a la creación de informes

Sus opciones para crear informes están controladas por su rol y los permisos asignados a ese rol. Existe un permiso de **edición de informes personales** que, si se asigna a su función, le permitirá crear informes personales que sólo usted podrá ver. Este permiso se asigna por defecto al rol **Analista**, pero puede asignarse a cualquier rol. Consulte con su administrador de Apptio para ver si se le ha asignado un rol que tenga este permiso.

## Crear un informe

1. Cambiar a **TBM TBM Studio**.
2. Haz clic en la pestaña **Inicio**, en **Nuevo** y, a continuación, en **Informe**. Tenga en cuenta que los elementos que aparezcan en el cuadro de diálogo dependerán de los permisos de su función.![Crear un informe](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep339.png)
3. Introduzca un nombre para el informe**.NOTICE**

   Si va a exportar informes a Excel, tenga en cuenta que Excel limita los nombres de hoja a 31 caracteres. Si el nombre de un informe supera el límite de caracteres, Excel trunca el nombre y coloca "-0" al final.
4. Introduzca una descripción de la report.The descripción se mostrará en el **buscador de informes**, por lo que es importante que introduzca una descripción que será útil para un usuario final que está viendo e imprimiendo informes.
5. Si está creando el informe uno o más niveles por debajo en la jerarquía de informes, y desea que el informe se cree en el nivel superior, marque la opción **Crear como informe de nivel superior**.
6. Seleccione quién puede ver los informes report.If si crea informes que sólo usted puede ver, las opciones **Visible por** no aparecerán en el cuadro de diálogo.
7. Seleccione el diseño del informe y si desea o no agregar un encabezado al informe (casilla de verificación **Agregar encabezado** a la derecha).

   Después de crear el informe, puede cambiar el diseño y elegir mostrar o no el encabezamiento.
8. Elija el tamaño de pantalla que se utilizará para maquetar el informe.
   - **Estándar** : 1024 píxeles de ancho
   - **Pantalla panorámica** : 1440 píxeles de ancho
9. Para determinados informes, se mostrará una opción **Avanzada** en el cuadro de diálogo que le permitirá elegir cuándo se mostrará el informe seleccionando opciones de las listas desplegables. Las listas disponibles dependerán del informe principal y de si se han filtrado los datos del informe. Un informe de desglose es aquel en el que un usuario desciende de un informe de objetos a otro.

   | Tipo de informe | Opción | Descripción |
   | --- | --- | --- |
   | Sin avería | Incluso cuando se muestra una avería | Muestra el informe incluso si los datos que se introducen en el informe son datos de desglose. |
   | Sólo cuando no muestra una avería | Muestra el informe sólo si los datos que se introducen en el informe no son datos de desglose. |
   | Avería | Incluso cuando no muestra una avería | Muestra el informe incluso si los datos que se introducen en el informe no son datos de desglose. |
   | Sólo cuando se muestra una avería | Muestra el informe sólo si los datos que se introducen en el informe son datos de desglose. |
   | Filtrada | Sólo cuando se filtra así | Esta opción sólo está disponible para los informes filtrados. Muestra el mismo informe pero sólo si el filtrado es el mismo. El filtrado es el mismo si se han definido filtros para las mismas columnas en las tablas de origen. |
   | Aunque se filtre de otra manera | Esta opción sólo está disponible para los informes filtrados. Muestra el mismo informe (aunque se hayan definido diferentes conjuntos de filtros). |
   | Unidad | Para todas las unidades | Esta opción sólo está disponible para los informes de unidad. Aplica el informe a todas las unidades de la columna del identificador de unidad. |
   | Sólo para la *unidad* | Esta opción sólo está disponible para los informes de unidad. Aplica el informe sólo a la unidad especificada en el filtro. |
10. Para guardar el informe y cerrar el cuadro de diálogo, haga clic en **Aceptar**.

Después de crear un informe, puede añadir tablas, gráficos y componentes de formato y navegación.

## Creación y aplicación de paletas de colores

Puede crear y gestionar paletas de colores para un informe. Para saber más, consulte [Paleta de colores personalizada](../admin/color-enhancement.htm "(se abre en una pestaña o una ventana nueva)").

## Guardar un informe

Al crear un informe por primera vez, la aplicación lo guarda automáticamente. Si realiza cambios en un informe y luego se desplaza, el informe se guarda automáticamente.

Cuando se realiza un cambio en un informe, aparece un asterisco (\*) delante del nombre del informe en la pestaña Informe, en la parte inferior del área de trabajo de edición del informe. El asterisco le recuerda que debe guardar el informe.

Para guardar un informe, haga clic en el icono **Guardar** ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/save.png) de la pestaña **Inicio**.

## Guardar un informe con un nuevo nombre

Para hacer una copia del informe y guardarlo con un nuevo nombre de informe:

1. Abra el menú situado bajo el icono **Guardar** y haga clic en **Guardar como**.Aparecerá el cuadro de diálogo **Guardar** como, tal y como se muestra en la siguiente imagen:![Guardar un informe](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu514.png)
2. Introduzca un nombre y una descripción para el informe.
3. Si está creando el informe uno o más niveles por debajo en la jerarquía de informes, y desea que el informe se cree en el nivel superior, marque la opción **Crear como informe de nivel superior**.
4. Seleccione quién puede ver los informes report.If si crea informes que sólo usted puede ver, las opciones **Visible por** no aparecerán en el cuadro de diálogo.
5. Para guardar el informe y cerrar el cuadro de diálogo, haga clic en **Aceptar**.

## **Borrar un informe**

1. En el **Explorador de proyectos**, haga clic en el nombre del informe que desea eliminar.
2. En la pestaña **Inicio**, haz clic en **Eliminar**.
3. Guarda el informe.
4. Comprueba el informe.

## Restringir fechas para un informe

Por defecto, los informes son visibles durante todas las fechas de un proyecto. Sin embargo, puede restringir las fechas en las que un informe es visible configurando la opción **Fecha más temprana aplicable**. Esto puede ser útil si está creando un informe y desea ocultarlo hasta que esté listo para que lo vean los usuarios.

Para fijar la fecha de aplicación más temprana:

1. Haga clic en el informe en el **Explorador de proyectos**.
2. Consulta el informe.
3. En la pestaña **Informe**, haga clic en el icono **Fecha de inicio**. Aparecerá el cuadro de diálogo **Configurar fecha más temprana aplicable**, como se muestra en la siguiente imagen:![Restringir fechas para un informe](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep126.png)
4. Haga clic en el icono de calendario situado al final del campo **A partir de** y seleccione una fecha.

   Cuando se establece una fecha más temprana y un usuario intenta ver el informe antes de esa fecha, la aplicación muestra un mensaje explicando que el informe aún no se puede ver. El usuario tiene la posibilidad de hacer clic en un enlace que le lleva al primer periodo visible.

## Precargar un informe

Los datos que aparecen en algunos informes pueden tardar mucho en calcularse. En la mayoría de los casos, querrá asegurarse de que los datos de un informe se han cargado previamente antes de que los usuarios accedan al informe. Para ello, marque la opción **Activo** en el grupo **Avanzado** de la pestaña **Informe**.

Si tu dominio ha sido configurado para evitar que los usuarios vean informes que no han sido precargados, se mostrará un mensaje que indica a los usuarios que no pueden ver el informe porque no ha sido precargado.

## Dominar un informe

Si desea utilizar el informe como plantilla maestra para otros informes, haga clic en la opción **Informe maestro**. Para más información sobre la utilización de informes maestros, véase [Trabajar con informes maestros](master-reports.htm "(se abre en una pestaña o una ventana nueva)").
