---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear perspectivas personalizadas en los informes"
breadcrumb: []
source_path: "studio/reports/tables/create-custom-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu626.png"
  - "resources/images/studio_images/studioimages/studio/stu627.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear perspectivas personalizadas en los informes

**Se aplica a** : TBM Studio 11.0

Para aumentar las perspectivas estándar de **Tablas**, **Métricas** y **Tiempo**, puede crear perspectivas personalizadas. En la ilustración siguiente, hay una perspectiva personalizada: ABC Company Analytics. Una perspectiva personalizada contiene campos seleccionados de las demás perspectivas que desea poner a disposición de los usuarios empresariales. Una ventaja de las perspectivas personalizadas es que puede añadir campos de varias tablas diferentes y bloquear los campos en la tabla. Esto permite elaborar informes que contengan datos de varias tablas en distintos niveles de un modelo. Además, es mejor utilizar sólo campos bloqueados a tablas en sus informes de producción.

![perspectivas personalizadas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu626.png)

Vea estos vídeos de demostración de Apptio Education Services:

- [Crear una perspectiva personalizada](https://community.apptio.com/videos/1892 "(se abre en una pestaña o una ventana nueva)")
- [Añadir una columna de tarifas](https://community.apptio.com/videos/1893 "(se abre en una pestaña o una ventana nueva)")

O consulte [todos los vídeos de Apptio](https://community.apptio.com/docs/DOC-7714 "(se abre en una pestaña o una ventana nueva)").

## Crear una perspectiva personalizada

Para crear una perspectiva personalizada y añadir campos a la perspectiva:

1. Haga clic con el botón derecho del ratón en la sección **Perspectivas** **del Explorador de proyectos** y haga clic en **Añadir nueva perspectiva**.
2. En el cuadro de diálogo Crear perspectiva, introduzca el nombre de la perspectiva y haga clic en Aceptar.

## Añadir un campo a una perspectiva personalizada

Para añadir un campo a una perspectiva personalizada:

1. Arrastre un campo desde las secciones **Tablas**, **Métricas** o **Tiempo** en el **Explorador de proyectos** al encabezado **Perspectivas** en el **Explorador de proyectos**.
2. Cuando se le solicite, seleccione una perspectiva y haga clic en **Aceptar**.
3. Rellene los campos del cuadro de diálogo Publicar campo.![Publicar campo](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu627.png)
4. Rellene los campos y haga clic en **Publicar**. Los campos se describen a continuación.

**Descripciones de los campos:**

- **Nombre** - El nombre del campo. Puedes aceptar el nombre por defecto o cambiarlo. Si va a bloquear el objeto, una buena práctica es incluir el nombre del objeto en el nombre del campo.
- **Tipo de datos** - Seleccione un tipo de datos de la lista. El tipo controla el formato básico de los datos.
- **Bloquear al objeto** - Este campo se muestra cuando se publica un campo de Datos. Cuando está marcada, garantiza que el campo se aplicará sólo al objeto seleccionado cuando se añadió a la perspectiva. Si no marca esta opción, el campo se aplicará al informe de objetos actualmente seleccionado.
- **Representa un código de jerarquía** - Sólo se aplica a las cortadoras. Cuando está marcada, y el campo publicado se utiliza para definir un slicer, encuentra todos los valores que empiezan por los caracteres de búsqueda introducidos por el usuario más un carácter adicional, y crea un grupo de slicer para cada uno. Por ejemplo, si el usuario escribe "ab", el filtro encontrará "aba", "abc" y "abd" y creará grupos para cada uno de ellos. Para más información sobre esta opción, véase [Representación de códigos jerárquicos en perspectivas](../hierarchy-codes-perspectives.htm "(se abre en una pestaña o una ventana nueva)").
- **Mostrar todas las filas en la consulta** basada en el tiempo - Cuando se marca, si una tabla o gráfico que se basa en el tiempo (e. g.: meses, trimestres, etc.), todas las filas se mostrarán en todos los periodos incluso si uno o más periodos contienen filas con ceros en todos fields.You debe marcar esta opción en todos los cálculos que incluyan una función que extraiga datos de otros periodos de tiempo. Por ejemplo, PreviousYear y YearToDate. Para obtener información más detallada sobre esta opción, consulte [Mostrar todas las filas en la consulta basada en el tiempo](#Createcustomperspectivesinreports__Showallrowsintimebasedqueryoption).
- **Descripción** - El texto introducido en el campo se muestra como información sobre la herramienta cuando un usuario pasa el puntero del ratón sobre el campo. Utilice este campo para proporcionar información a los analistas sobre los datos representados por el campo. Esto es importante porque los analistas pueden no estar familiarizados con los conjuntos de datos del proyecto y el nombre del campo puede no transmitir el contenido. Introducir una explicación completa de los datos ayudará a los analistas a utilizar el campo de forma eficaz a la hora de elaborar tablas y gráficos.
- **Notas** - Información para otros usuarios avanzados que puedan editar el campo.
- **Filtro** - Este campo se muestra si está publicando un campo desde el área **Filtro**. Se trata de un campo no editable.
- **Fórmula** - Este campo se muestra si hay una fórmula asociada al campo. Puedes editar la fórmula.

## Mostrar todas las filas en la opción de consulta basada en el tiempo

Algunas tablas basadas en el tiempo pueden tener una o más filas que no tienen valores para uno o más periodos de tiempo. Por defecto, las filas sin valores no se muestran. Para asegurarse de que se mostrarán todas las filas en todos los periodos, marque la opción **Mostrar todas las filas en la consulta basada en el tiempo**.

Por ejemplo, suponga que tiene una tabla respaldada con los siguientes datos en enero y febrero:

Enero de 20 FY2016

| **Columna A** | **Columna B** |
| --- | --- |
| X | 1 |
| Y | 2 |
| Z | 3 |

Febrero FY2016

| **Columna A** | **Columna B** |
| --- | --- |
| X | 4 |
| Z | 3 |

Tiene dos métricas calculadas: Coste y YearToDate(Cost ). Añada columnas de Coste y YTD a la tabla para visualizar las métricas.

Cuando esté en febrero, no aparecerá la fila Y.

| **Columna A** | **Coste** | **Anual hasta la fecha** |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |

Sin embargo, si ha marcado la opción, se mostrará la fila Y.

| **Columna A** | **Coste** | **Anual hasta la fecha** |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |
| Y |  | 2 |

Además, debe marcar esta opción en todos los cálculos que incluyan una función que extraiga datos de otros periodos de tiempo. Por ejemplo, PreviousYear y YearToDate.

## Cambiar el nombre de una perspectiva personalizada

Para cambiar el nombre de una perspectiva personalizada, haz clic con el botón derecho del ratón en el nombre de la perspectiva y pulsa la opción **Cambiar nombre**.

## Crear una dimensión

Puede agrupar campos en una perspectiva personalizada.

Para crear un grupo de campos y añadir dimensiones al grupo:

1. Haga clic con el botón derecho del ratón en una perspectiva personalizada y haga clic en Añadir nuevo grupo.
2. Arrastre las dimensiones de un área al grupo.

## Borrar una dimensión

Para eliminar una dimensión desde una perspectiva personalizada, haga clic con el botón derecho del ratón y pulse **Eliminar campo**.

## Borrar una perspectiva

Para eliminar, haz clic con el botón derecho del ratón en la barra de título de la perspectiva y selecciona Eliminar.

## Crear una perspectiva sólo para administradores

Si tiene asignada una función de administrador, puede crear perspectivas que sólo sean visibles para otros usuarios con funciones de administrador. Esto resulta útil para crear un lugar en el que almacenar dimensiones de uso frecuente a las que no desea que accedan los analistas.

Para crear una perspectiva sólo para administradores, ponga entre paréntesis el nombre de la perspectiva.
