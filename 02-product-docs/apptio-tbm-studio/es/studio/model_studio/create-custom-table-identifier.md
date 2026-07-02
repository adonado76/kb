---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear un identificador de tabla personalizado"
breadcrumb: []
source_path: "studio/model_studio/create-custom-table-identifier.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu607.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear un identificador de tabla personalizado

**Se aplica a** : TBM Studio 12.0 y posteriores. El entorno de modelización Apptio proporciona un marco flexible para manipular los datos en agrupaciones que constituyen la base de las asignaciones y los informes. A continuación, se explicarán las mejores prácticas para elegir el identificador adecuado para una tabla modelo determinada.

Los identificadores de tabla se utilizan para vincular tablas modelo a una columna subyacente dentro de una tabla. El identificador es similar a una clave primaria en una base de datos relacional, y la mejor práctica es que el identificador conste de valores únicos. Los valores únicos permiten elaborar informes detallados y desglosar las partidas individuales.

A la hora de elegir un identificador, debe tener en cuenta lo siguiente:

- ¿Cuál es el nivel más granular de agrupación que quiero utilizar en esta tabla?
- ¿Puedo encontrar una única columna que tenga valores únicos para cada fila?
- ¿Es necesario concatenar varias columnas para conseguir la unicidad?
- ¿Cómo se relacionan los datos que respaldan esta tabla con los datos de la(s) tabla(s) a la(s) que asigna?

Por defecto, la aplicación crea un identificador único para cada fila. Sin embargo, puede crear un identificador personalizado que proporcione el nivel de detalle que desee utilizar al asignar valor en el modelo y al crear informes. Por ejemplo, es posible que desee agrupar valores por departamento, cuenta o algún otro valor para reducir los tiempos de cálculo y proporcionar informes de mayor nivel.

Para crear un identificador de tabla personalizado:

1. Haga clic en el paso **Modelo** de la cadena de transformación de tablas.
2. Haga clic en la tabla en la vista **Tabla única** del modelo.
3. En el panel **Filas** que se muestra en la siguiente imagen, marque las columnas que desea utilizar para crear el identificador. Las columnas se añaden a la tabla de la derecha. El cuadro muestra el coste de cada línea y el importe asignado:![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu607.png)
4. Para volver al diagrama de Sankey, haga clic en **Cerrar** en la parte inferior del panel.
