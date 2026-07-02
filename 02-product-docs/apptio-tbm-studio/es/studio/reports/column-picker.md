---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componente de selección de columnas"
breadcrumb: []
source_path: "studio/reports/column-picker.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep034.png"
  - "resources/images/studio_images/studioimages/reports/rep325.png"
  - "resources/images/studio_images/studioimages/reports/rep327.png"
  - "resources/images/studio_images/studioimages/studio/stu516.png"
  - "resources/images/studio_images/studioimages/studio/stu517.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de selección de columnas

**Se aplica a** : TBM Studio 12.0 y posteriores

Un selector de columnas permite a los usuarios personalizar una tabla de un informe añadiendo columnas a la tabla. En la siguiente imagen se muestra un ejemplo de selector de columnas y la tabla que lo acompaña. Un selector de columnas se aplica a todas las tablas de un informe, a menos que esté contenido dentro de un objeto de grupo. Si el selector se encuentra en un objeto de grupo, sólo se aplica a las tablas del grupo.

![Selector de columnas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep034.png)

**Puntos clave** :

A continuación se presentan los puntos clave sobre la creación de selectores de columnas:

- Los campos de etiqueta añadidos a un selector se añaden a las tablas como filas (en el contexto del panel **Configuración de componentes** ) agrupadas por los valores de la primera columna de la tabla. En la siguiente imagen se muestra un selector de columna horizontal con opciones de etiqueta:

  ![Configuración de componentes](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep327.png)
- Los campos numéricos añadidos a un selector se añaden a las tablas como valores (en el contexto del cuadro de diálogo **Configuración de componentes** ) en columnas independientes. Si las columnas de la tabla están agrupadas, se añade una columna en cada grupo.
- Los campos bloqueados dan los resultados más predecibles. Sin embargo, por lo general, obtendrá resultados satisfactorios si utiliza campos desbloqueados.
- Un selector de columna puede mostrarse como un conjunto de casillas de verificación o como botones de radio. Utilice casillas de verificación para selecciones múltiples. Utilice botones de opción para selecciones únicas.
- Las casillas de verificación y los botones de opción pueden orientarse vertical u horizontalmente.

## Añadir un selector de columnas

1. En la pestaña **Informe**, haga clic en **Selector de columnas**. Se añade un componente de **selección de columnas** al informe. El panel de configuración del selector de columnas aparece como se muestra en la siguiente imagen:

   ![Añadir un selector de columnas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu516.png)
2. En el campo situado en la parte superior del cuadro de diálogo, seleccione el objeto que representa la tabla en la que se añadirán las columnas.
3. Desde el **Explorador de proyectos**, arrastre uno o varios valores al área **Campos disponibles**.
4. Cierre el cuadro de diálogo haciendo clic en una zona en blanco del informe.

## Elija casillas de verificación o botones de opción

En un selector de columnas, éstas pueden mostrarse como un conjunto de casillas de verificación o botones de radio. Las casillas de verificación permiten al usuario seleccionar una o varias columnas. Los botones de radio permiten al usuario seleccionar una sola columna. La opción **Selección múltiple** muestra casillas de verificación. La opción **Selección única** muestra botones de opción.

Para cambiar la opción de visualización:

1. Seleccione el componente del selector de columnas en el informe.
2. En la pestaña **Selector**, seleccione la opción **Selección única** o **Selección múltiple**.

## Orientación vertical u horizontal

Las opciones del selector pueden orientarse vertical u horizontalmente mediante las opciones de **Diseño** de la pestaña **Selector**.

## Utilizar como selector de fechas

Puede utilizar un selector de columnas para ofrecer a los usuarios la posibilidad de filtrar una tabla por fechas. En el informe que se muestra en la siguiente imagen, el usuario puede seleccionar entre Mes en curso, Semestre en curso y Año hasta la fecha. La selección se refleja en el encabezamiento Jun FY2014 situado encima de las dos columnas agrupadas: Coste y Presupuesto.

![selector de fecha](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep325.png)

Para crear este tipo de informe:

1. Agrupe las columnas de la tabla e introduzca el siguiente texto dinámico para el título del grupo: <%=CurrentDate( )%>.
2. Añada el selector de columna utilizando los valores de fecha como se muestra en la siguiente imagen:

   ![Configuración del selector de columnas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu517.png)
