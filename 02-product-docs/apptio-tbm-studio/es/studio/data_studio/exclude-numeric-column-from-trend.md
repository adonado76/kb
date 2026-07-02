---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Excluir una columna numérica de una tendencia"
breadcrumb: []
source_path: "studio/data_studio/exclude-numeric-column-from-trend.html"
images:
  - "resources/images/studio_images/studioimages/studio_data_ungroup_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Excluir una columna numérica de una tendencia

◆ Se aplica a: TBM Studio 11.0 y posteriores, TBM Studio 12.0 y posteriores

A veces, al crear un informe ad hoc, se desea determinar la tendencia de algunas cifras y excluir otras. Este artículo describe cómo excluir una o varias columnas de la tendencia.

Este artículo contiene capturas de pantalla de TBM Studio R12, pero los mismos principios se aplican a TBM Studio v.11.

Supongamos que comienza con un informe que contiene una tendencia de los costes de los tres meses anteriores por grupo de costes:

![](../../resources/images/studio_images/studioimages/studio_cost%20pool_exclude%20numeric%20column_sui.png)

Si simplemente añades Presupuesto, obtienes esto:

![](../../resources/images/studio_images/studioimages/studio_exclude%20numeric%20column_budget_sui.png)

Sin embargo, en este ejemplo, nuestro número de presupuesto es el mismo todos los meses, por lo que sólo queremos mostrarlo una vez y que no aparezca debajo de la tendencia. Así que, en su lugar, hacemos lo siguiente:

1. Eliminar temporalmente los valores de tiempo de **las Columnas**.
2. Inserte una columna de fórmula y hágala igual a la métrica Presupuesto:

   ![](../../resources/images/studio_images/studioimages/studio_exclude%20numeric%20column_create%20new_sui.png)
3. Arrastre la columna **Presupuesto** de la sección **Valores** a la sección **Filas**.
4. Haga clic con el botón derecho en la columna Presupuesto y seleccione Desagrupar.

   Si olvida desagrupar la columna cuando vuelva a añadir la tendencia temporal, la tabla tendrá ceros en esa columna.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_data_ungroup_sui.png)
5. Vuelva a añadir la tendencia en las columnas:

   ![](../../resources/images/studio_images/studioimages/studio_data_excluding%20numeric%20column_sui.png)
