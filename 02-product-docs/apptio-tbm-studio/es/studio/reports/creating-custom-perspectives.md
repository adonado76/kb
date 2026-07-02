---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear perspectivas personalizadas"
breadcrumb: []
source_path: "studio/reports/creating-custom-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu555.png"
  - "resources/images/studio_images/studioimages/studio/stu609.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear perspectivas personalizadas

**Se aplica a** : TBM Studio 12.0 y posteriores

Para aumentar las secciones estándar del **Explorador de proyectos**, puede crear perspectivas personalizadas. En la siguiente imagen, hay una perspectiva personalizada: **ABC Company Analytics**. Una perspectiva personalizada contiene campos seleccionados de las otras perspectivas que desea poner a disposición de los usuarios empresariales.

![Explorador de proyectos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu555.png)

Para crear una perspectiva personalizada y añadir campos a la perspectiva:

1. Haga clic con el botón derecho del ratón en la sección **Perspectivas** **del Explorador de proyectos** y seleccione **Añadir nueva perspectiva**.
2. En el cuadro de diálogo **Crear perspectiva**, introduzca el nombre de la perspectiva y haga clic en **Aceptar**.

Los analistas sólo ven las perspectivas personalizadas y la perspectiva **temporal** en el **Explorador de proyectos**. Todos los analistas ven todas las perspectivas personalizadas. No se pueden crear diferentes conjuntos de perspectivas personalizadas para diferentes grupos de analistas. Las perspectivas personalizadas aparecen en orden alfabético en la parte superior del área **Perspectivas**.

## Añadir un campo a una perspectiva personalizada

Para añadir un campo a una perspectiva personalizada:

1. Realice una de las siguientes acciones:
2. Arrastre un campo de las secciones **Tablas**, **Métricas** o **Tiempo** a la barra de título de la sección **Perspectivas** del **Explorador de proyectos**.
3. Arrastre un campo de un área del panel **Configuración de componentes** a la barra de título de la sección **Perspectivas** del **Explorador de proyectos**.
4. Haga clic con el botón derecho en un campo del panel **Configuración de componentes** y seleccione **Publicar**.![Publicar campo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu609.png)
5. Rellene los campos y haga clic en **Publicar**. Los campos se describen a continuación:

## **Descripciones de los campos**

- **Nombre** - El nombre del campo. Puedes aceptar el nombre por defecto o cambiarlo.
- **Tipo de datos** - Seleccione un tipo de datos de la lista. El tipo controla el formato básico de los datos.
- **Representa un código de jerarquía** - Sólo se aplica a las cortadoras. Cuando está marcada, y el campo publicado se utiliza para definir un slicer, encuentra todos los valores que empiezan por los caracteres de búsqueda introducidos por el usuario más un carácter adicional y crea un grupo de slicer para cada uno. Por ejemplo, si el usuario escribe "ab", el filtro encontrará "aba", "abc" y "abd" y creará grupos para cada uno de ellos. Para obtener información más detallada sobre esta opción, consulte [Representar un código de jerarquía en perspectivas](hierarchy-codes-perspectives.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Mostrar todas las filas en una consulta** basada en el tiempo - Cuando está marcada, si una tabla o gráfico está basado en el tiempo (e. g.: meses, trimestres, etc.), todas las filas se mostrarán en todos los periodos, incluso si uno o más periodos contienen filas con ceros en todos los campos. Para obtener información más detallada sobre esta opción, consulte [Mostrar todas las filas en la opción de consulta basada en el tiempo](#Createcustomperspectives__Showallrowsintimebasedqueryoption) más abajo.
- **Descripción** - El texto introducido en el campo se muestra como información sobre la herramienta cuando un usuario pasa el puntero del ratón sobre el campo. Utilice este campo para proporcionar información a los analistas sobre los datos representados por el campo. Esto es importante porque los analistas pueden no estar familiarizados con los conjuntos de datos del proyecto y el nombre del campo puede no transmitir el contenido. Introducir una explicación completa de los datos ayudará a los analistas a utilizar el campo de forma eficaz a la hora de elaborar tablas y gráficos.
- **Notas** - Información para otros usuarios avanzados que puedan editar el campo. La información sólo está disponible en este cuadro de diálogo.
- **Filtro** - Este campo se muestra si está publicando un campo desde el área **Filtro**. Se trata de un campo no editable.
- **Fórmula** - Este campo se muestra si hay una fórmula asociada al campo. Puedes editar la fórmula.

## Mostrar todas las filas en la opción de consulta basada en el tiempo

Algunas tablas basadas en el tiempo pueden tener una o más filas que no tienen valores para uno o más periodos de tiempo. Por defecto, las filas sin valores no se muestran. Para asegurarse de que se mostrarán todas las filas en todos los periodos, marque la opción **Mostrar todas las filas en la consulta basada en el tiempo**.

Por ejemplo, supongamos que tiene los siguientes datos:

**Enero de 20 FY2011**

| Columna A | Columna B |
| --- | --- |
| X | 1 |
| Y | 2 |
| Z | 3 |

**Febrero FY2011**

| Columna A | Columna B |
| --- | --- |
| X | 4 |
| Z | 3 |

Tiene dos métricas calculadas: Coste y YearToDate(Cost ). Añada columnas de Coste y YTD a la tabla para visualizar las métricas.

En febrero no se mostrará la fila Y:

| Columna A | Coste | Anual hasta la fecha |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |

Sin embargo, si ha marcado la opción, se mostrará la fila Y:

| Columna A | Coste | Anual hasta la fecha |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |
| Y |  | 2 |

## Cambiar el nombre de una perspectiva personalizada

Para cambiar el nombre de una perspectiva personalizada, haz clic con el botón derecho del ratón en la perspectiva personalizada y haz clic en Cambiar nombre.

## Crear grupos de campos

Puede agrupar campos en una perspectiva personalizada.

1. Haga clic con el botón derecho del ratón en una perspectiva personalizada y seleccione **Añadir nuevo grupo**.
2. Arrastre los campos de un área al grupo.

Para eliminar un campo de un grupo, arrástrelo a un área en blanco de una perspectiva personalizada.

## Borrar un campo

Para eliminar un campo de una perspectiva personalizada, haga clic con el botón derecho del ratón en el campo y haga clic en **Eliminar campo**.

## Borrar una perspectiva

Para eliminar una perspectiva, haga clic con el botón derecho del ratón en la barra de título de la perspectiva y seleccione Eliminar.

## Crear perspectivas sólo para administradores

Si tiene asignada una función de administrador, puede crear perspectivas que sólo sean visibles para otros usuarios con funciones de administrador. Esto resulta útil para crear un lugar donde almacenar los campos de uso frecuente a los que no desea que accedan los analistas.

Para crear una perspectiva sólo para administradores, ponga entre paréntesis el nombre de la perspectiva.
