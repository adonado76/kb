---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Desplazar datos"
breadcrumb: []
source_path: "studio/data_studio/unpivot-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Desplazar datos

**Se aplica a** : TBM Studio 12.0 y posteriores

A veces es útil convertir los valores de las columnas en filas adicionales. Para ello, utilice el paso **Unpivot** pipeline en una tabla.

Por ejemplo, la siguiente tabla tiene columnas para la ciudad, el estado, la población del censo de 2023 y la población del censo de 2020.

| Ciudad | Estado | 2023 | 2020 |
| --- | --- | --- | --- |
| Nueva York | NY | 8258035 | 8804190 |
| Los Ángeles | CA | 3820914 | 3898747 |
| Chicago | IL | 2664452 | 2746388 |

Para convertir las columnas con los valores censales en filas:

1. Echa **[un vistazo](../admin/navigate-tbm-studio.html#FindyourwayaroundTBMStudio__Checkoutandcheckin)** a la tabla.
2. Añade un paso **Unpivot** al pipeline de la tabla. Para obtener más información, consulte [el canal Pasos de transformación](transform-workspace.html#Thedatatransformworkspace__TransformStepspipeline).
3. Haga clic en **Configurar columnas** y seleccione las columnas que **no** desea convertir en filas. En este ejemplo, elegiríamos "Ciudad" y "Estado".
4. Haga clic en **Guardar** en la cinta.

El resultado es una tabla con dos columnas: *Colapsar columna* y *Colapsar valor*.

- **Colapsar columna:** Incluye los valores correspondientes a las columnas que no has elegido.
- **Contraer valor:** Incluye los valores de las columnas que se convirtieron en filas.

Esa tabla de salida tiene el siguiente aspecto:

| Colapsar columna | Valor de colapso | Ciudad | Estado |
| --- | --- | --- | --- |
| 2023 | 8258035 | Nueva York | NY |
| 2020 | 8804190 | Nueva York | NY |
| 2023 | 3820914 | Los Ángeles | CA |
| 2020 | 3898747 | Los Ángeles | CA |
| 2023 | 2664452 | Chicago | IL |
| 2020 | 2746388 | Chicago | IL |

## Notas importantes

**Evite mezclar tipos de columnas**

Si las columnas que no están seleccionadas incluyen columnas de tipo numérico y de tipo etiqueta, la columna "Contraer valor" resultante será una mezcla de valores numéricos y de etiqueta. Esto puede dar lugar a problemas más adelante en la cadena de producción de la tabla o en otras tablas basadas en la que tiene el paso Unpivot.

Ejemplos de los tipos de problemas que pueden ocurrir incluyen que una columna no esté disponible para elegir en el identificador de un paso del Modelo, o que los valores numéricos de la columna no sean sumables.

Si necesita una columna con valores numéricos y de etiqueta mezclados, le recomendamos que inserte un paso de Fórmula después del paso Desglosar y edite la columna existente para anular el tipo de columna y que sea una etiqueta. Consulte la documentación [Editar una columna](add-edit-columns.html#Addandeditcolumns__Editacolumn) para obtener más información.

**Evitar una expansión excesiva de las filas**

El uso del paso Unpivot amplía el recuento de filas en una cantidad igual al número de filas antes del paso Unpivot multiplicado por el número de columnas que se convierten en filas. Por ejemplo, si el recuento de filas antes de Unpivot es de 10 filas, y Unpivot 2 columnas, entonces el recuento de filas después de Unpivot será: 10 + (2 \* 10) = 30.

Dado que el paso Unpivot permite especificar las columnas que *no* deben convertirse en filas, si el origen de datos cambia para incluir columnas adicionales, puede producirse una expansión inesperada de las filas en función de las propiedades de los datos. Esto puede provocar problemas de rendimiento, como lentitud de carga en TBM Studio o tiempos de cálculo más largos para el proyecto en el que se encuentra la tabla. El grado de impacto en el rendimiento varía en función del número de filas resultantes del pivote y de cómo se utilice la tabla posteriormente.
