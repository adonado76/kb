---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Buscar entradas duplicadas en una tabla"
breadcrumb: []
source_path: "studio/data_studio/search_for_duplicates.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Buscar entradas duplicadas en una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede haber ocasiones en las que desee buscar entradas duplicadas en una columna de la tabla. Por ejemplo, puede haber creado una columna que servirá como identificador único y quiere estar seguro de que no hay claves duplicadas.

Para buscar entradas duplicadas en una tabla:

1. Haga clic en el paso **Tabla** del canal de transformación, haga clic con el botón derecho del ratón en la cabecera de la columna y, a continuación, haga clic en **Mostrar valores**.
2. En la columna Recuento de los **Valores en...** introduzca **!=1**. Esto buscará filas que no tengan un valor de 1, lo que indicará entradas duplicadas.
