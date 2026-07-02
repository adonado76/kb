---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir fila duplicada"
breadcrumb: []
source_path: "studio/reports/tables/add-duplicate-row.html"
images:
  - "resources/images/studio_images/duplicate-row-et_647x314.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir fila duplicada

La función Duplicar fila mejora y simplifica la asignación de divisiones. El botón de duplicar fila aparecerá en el menú del botón derecho del ratón en el ET o en el informe que tenga ET. Este botón tendrá el mismo permiso que la operación de añadir fila ya que duplicar una fila es similar a añadir una nueva fila pero con algo de contenido. La fila duplicada se añadirá justo debajo de la fila que se está duplicando. Funciona tanto para tablas editables en bruto como enriquecidas. Permite al usuario asignar una línea a más de un artículo para que los costes puedan dividirse entre varias cosas. Se permite la duplicación de varias filas incluso antes de guardarlas. Las filas no desaparecerán si se alcanza el número máximo de filas de la tabla y se activa la paginación. El usuario puede desactivar esta opción a nivel de tabla. Esta función duplicará todas las columnas visibles y ocultas. La columna autoincrementada seguirá estando oculta, pero para las columnas que imponen la unicidad dentro de la tabla:

- Rellenar previamente con el valor incrementado si el autoincremento está activado.
- Establecer como vacío, pero resalte según sea necesario si no se incrementa automáticamente.

## Navegación

1. Haga clic con el botón derecho en una celda y haga clic en **Duplicar fila**

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/duplicate-row-et_647x314.png)
2. La nueva fila duplicada aparece justo debajo de la fila original. Si se trata de una tabla editable en blanco, se duplicarán todos los campos de esa fila, independientemente de si están incluidos en las "Columnas incluidas".
3. Edite la fila como desee.
4. Haga clic en "Guardar"

Nota: La fila duplicada no siempre conserva su posición debajo de la fila original, debido a la forma en que se ordenan las tablas editables.

## Ejemplo

Esta es la Tabla Editable con cuatro columnas, antes de duplicar la fila.

![](../../../resources/images/studio_images/et-dup-1.jpg)

Sin embargo, sólo se incluyen dos columnas en el Informe. Dupliquemos la tercera fila.

![](../../../resources/images/studio_images/et-dup-last.jpg)

Nota: La fila duplicada no siempre conserva su posición debajo de la fila original, debido a la forma en que se ordenan las tablas editables. Muestra valores en todas las columnas, coincidentes con la fila original, a menos que se modifiquen o eliminen manualmente.
