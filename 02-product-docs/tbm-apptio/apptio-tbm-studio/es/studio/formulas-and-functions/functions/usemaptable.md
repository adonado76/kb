---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Use_Map_Table"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/usemaptable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Use_Map_Table

**Se aplica a** : TBM Studio 12.0 y posteriores

Utilice esta función para crear asignaciones entre dos objetos utilizando una fórmula introducida manualmente.

Nota: La compatibilidad con esta función ha quedado obsoleta en la versión 12 de TBM Studio . Aunque esta función sigue disponible, no es posible utilizarla para nuevas asignaciones netas. Si está trabajando con un proyecto actualizado desde la versión 11 (que utiliza esta función), consulte la [Tarea a seguir en v12](#UseMapTablefunction__TasksforStudio12) a continuación, que describe la mejor práctica v12 para conseguir las mismas asignaciones. Apportion anima a los clientes que pasen a TBM Studio v12 a cambiar a este nuevo método. A continuación se ofrece información adicional sobre esta función con fines históricos.

## Dónde utilizarlo

Al definir una asignación entre dos objetos de un modelo, seleccione **Avanzado** como opción de Asignación. La aplicación muestra el cuadro de diálogo **Editar fórmula** donde puede introducir la función. La ventaja de utilizar la función Use\_Map\_Table es que no depende del motor de inferencia para vincular los identificadores de unidad de los dos objetos. Los identificadores del objeto de origen pueden asignarse a identificadores del objeto de destino.

## Sintaxis

`Use_Map_Table(table:weight_column[,source_column,target_column][,format)]`

o

`Use_Map_Table(table:weight_column[,format)]`

## Argumentos

*tabla*

Hace referencia a una tabla de asignación.

*columna\_peso*

La columna de la tabla que contiene los números de ponderación.

*columna\_fuente*

La columna de la tabla que contiene el ID de unidad del objeto fuente.

*columna\_objetivo*

La columna de la tabla que contiene el ID de unidad del objeto de destino.

*formato*

Cuando se utiliza la primera declaración sintáctica (tabla:peso), puede ser "ratio", "porcentaje" o "fracción\_porcentaje", donde el valor predeterminado es "fracción\_porcentaje"

Cuando se utiliza la segunda declaración sintáctica (tabla:peso), puede ser "porcentaje" o "fracción\_porcentaje", donde el valor predeterminado es "fracción\_porcentaje"

## Tipo de retorno

Tipo de las columnas de la tabla de correspondencia.

## Observaciones

Para la primera sintaxis, si el objeto A está transfiriendo valores al objeto B, la tabla de asignación debe incluir los siguientes tipos de columnas:

| A | B | columna\_peso |
| --- | --- | --- |
| Valores de la columna identificador de A | Valores de la columna del identificador B | Porcentaje numérico (por ejemplo: 0.2 = 20%, 1.0 = 100%) |

## Tareas para Studio 12

Si su proyecto fue actualizado de TBM Studio versión 11 a la versión 12, cualquier asignación que utilice use\_map\_table funcionará después de la actualización. Sin embargo, si edita la asignación, deberá modificarla para que funcione en la versión 12. Para ello, convertirá la tabla use\_map\_table en un objeto modelado. A continuación, asignará desde el objeto de origen original al nuevo objeto de asignación y, a continuación, desde el nuevo objeto de asignación al objeto de destino original.

En TBM Studio versión 12, siga estos pasos:

1. Añade un paso de modelado a la tabla de asignación utilizada originalmente en la función use\_map\_table.
2. Asignar desde el objeto fuente original a la tabla de asignación recién modelada.
   - En esta asignación, asegúrese de especificar una relación de datos utilizando el identificador del objeto de origen y la columna source\_column de la tabla de asignación.
   - Actualice esta asignación para ponderar adecuadamente por la columna columna\_peso de la tabla de asignación. La forma de hacerlo dependerá del formato de la función use\_map\_table.
     - Si su formato use\_map\_table es **ratio**, utilice **la ponderación** como regla de distribución y especifique la **columna source\_column** en la tabla de asignación.
     - Si su formato use\_map\_table es porcentual, cree una asignación avanzada con la fórmula:

       ```
       =SOURCE*Mapping
                               Table.weight_column/100
       ```
     - Si su formato use\_map\_table es fraction\_percent, cree una asignación avanzada con la fórmula:`=SOURCE*Mapping Table.weight_column`

       **Ejemplo: Asignación de la tabla de origen a la tabla de asignación**

       ![](../../../resources/images/studio_images/studioimages/studio_mapping%20table_distributing.png)
3. Asignar desde la tabla de asignación recién modelada al objeto de destino original.
   - En esta asignación, asegúrese de especificar una relación de datos utilizando el identificador del objeto de origen y la columna source\_column de la tabla de asignación.
   - Normalmente, la ponderación de esta asignación no importará, ya que cada fila de la tabla de asignación se asigna a una fila del objeto receptor.

## Resumen

El resultado final de este método es el mismo que el de la función original use\_map\_table, sigue las mejores prácticas de TBM Studio versión 12 y permite que las optimizaciones del motor de modelado de Apptio tengan todo su efecto.
