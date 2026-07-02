---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Trabajar con informes maestros"
breadcrumb: []
source_path: "studio/reports/master-reports.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu631.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trabajar con informes maestros

**Se aplica a** : TBM Studio 12.0 y posteriores

Si desea que un conjunto de informes tenga el mismo diseño, puede crear un informe maestro y aplicarlo a cada uno de los informes. Un informe maestro puede incluir todos los componentes de un informe normal, como botones, cuadros de grupo y elementos de acción. El concepto es similar al de las diapositivas maestras en las aplicaciones de presentación. Los informes maestros, por defecto, son siempre informes de nivel superior. Para crear un informe maestro, cree un nuevo informe y haga clic en la opción **Informe maestro** del grupo **Avanzado** de la pestaña **Informe**.

## Informes maestros estándar

La aplicación incluye muchos informes maestros estándar. Aparecen en el menú desplegable **Maestros** de la pestaña **Informe**. Puede utilizar estos informes maestros tal cual o modificarlos y guardarlos utilizando la opción **Guardar como**. No se pueden borrar informes maestros estándar.

## Informes maestros como papel pintado

Piense en los informes maestros como si fueran papel pintado. Cuando se aplica a un informe personalizado, los componentes de un informe maestro no pueden editarse desde un informe personalizado. Son estáticos. Los componentes añadidos a un informe personalizado se sitúan encima del papel pintado. Por ejemplo, si el maestro incluye un cuadro de grupo, puede colocar los componentes de modo que aparezcan dentro del cuadro de grupo, pero sin estar unidos a él.

Si añade un componente con pestañas a un informe maestro, las pestañas funcionarán cuando aplique el informe maestro a un informe. Sin embargo, debe evitar colocar componentes encima del componente con pestañas en el informe personalizado, ya que se mostrarán encima de todas las pestañas. De nuevo, piense en el componente con pestañas como si fuera papel pintado.

## Crear y eliminar informes maestros

Para crear un informe maestro:

1. Compruebe el informe que desea utilizar como maestro.
2. En el grupo **Avanzado** de la pestaña **Informe**, haga clic en la opción **Informe maestro**.
3. Guarda el informe.

Para eliminar un informe maestro:

1. En el modo Edición de informes, haga clic en la sección **Informes** del **Explorador de proyectos**. Filtrar la lista de informes por **Informes maestros**.

   ![Informes maestros](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu631.png)
2. Compruebe el informe que desea eliminar.
3. Haz clic en **Eliminar** en la pestaña **Inicio**.
4. Comprueba el informe.

Nota: Sólo puede eliminar informes maestros de clientes. No puede eliminar los informes maestros estándar que se envían con el producto.

## Aplicar un informe maestro

Para aplicar un informe maestro a un informe personalizado:

1. Echa un vistazo al informe personalizado en el modo de edición.
2. En la pestaña **Informe**, abra la lista desplegable **Maestros** y haga clic en el informe maestro que desee aplicar.

Se pueden aplicar informes maestros a otros informes maestros, pero no es recomendable.

## Eliminar un informe maestro

Para eliminar un informe maestro de un informe personalizado:

1. Seleccione la pestaña **Informe**.
2. Abra la lista desplegable **Maestro** y seleccione **Ninguno** en la parte inferior de la lista.

## Buenas prácticas para los informes maestros

A continuación se indican varias prácticas recomendadas para crear informes maestros.

1. Los informes maestros son ayudas para la maquetación. Por lo general, desea crear contenedores, como cuadros de grupo, dentro de los cuales colocará componentes, como gráficos y tablas.
2. Si añade un componente con pestañas a un informe maestro, asegúrese de añadir componentes a cada una de las pestañas. No podrá añadir componentes a las fichas individuales del informe personalizado en el que aplique el maestro. Los componentes añadidos encima de un componente con pestañas se mostrarán encima de todas las pestañas.
3. Los cuadros de grupo añadidos a un informe maestro pierden su capacidad de agrupación cuando el maestro se aplica a un informe personalizado. Utilice los cuadros de grupo como borde visual alrededor de los componentes.
4. Si añade un botón a un informe maestro que utiliza texto Wiki y no ha especificado un dato URL para el botón, la aplicación utilizará el informe actual como contexto.
