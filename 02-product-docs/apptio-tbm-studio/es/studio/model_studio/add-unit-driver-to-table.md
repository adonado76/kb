---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir un controlador de unidad a una tabla de un modelo"
breadcrumb: []
source_path: "studio/model_studio/add-unit-driver-to-table.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu605.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir un controlador de unidad a una tabla de un modelo

**Se aplica a** : TBM Studio 12.0 y posteriores

Hay dos formas de añadir valor a una tabla en un modelo:

- Utilice una columna de valores en la tabla. Es lo que se conoce como conductor unitario. Los controladores unitarios suelen utilizarse en el nivel más bajo de un modelo.
- Asignar valor a la tabla desde otra tabla. Esto se conoce como asignación. Las asignaciones se suelen utilizar para transferir valor de un nivel a otro de un modelo.

En la siguiente imagen, la tabla **Cost Source Actuals** tiene dos controladores unitarios: **OpEx Variable** y **OpEx Fijo**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu605.png)

La siguiente información describe cómo añadir un controlador de unidad. Para obtener información sobre las asignaciones, consulte **[Crear una asignación](allocate-value-in-model.htm "(se abre en una pestaña o una ventana nueva)")**.

Para añadir un controlador de unidad a una tabla:

1. Haga clic en la tabla en **el Explorador de proyectos** y compruebe la tabla.
2. Añade un paso **Modelo**.
3. Haga clic en el paso **Modelo**.
4. En el área de trabajo **Modelo**, haga clic en **Añadir controlador de unidad** en la columna **Controladores**.
5. En **Añadir a**, haga clic en las métricas a las que se aplicará el controlador.
6. En **Utilización**, haga clic en el tipo de controlador (véase más abajo la explicación de los tipos de controlador).
7. Complete la definición del conductor en función del tipo de conductor que haya seleccionado:
   - **Columna** : seleccione una columna
   - **Métrica** : seleccione una métrica
   - **Fórmula** : introduzca una fórmula

Opcionalmente, en **Notas**, introduzca información sobre el controlador.

Las pestañas **Origen** y **Destino** de la tabla de la derecha del cuadro de diálogo muestran fila por fila cómo se está distribuyendo el valor.

## Tipos de conductores

Hay tres tipos de conductores.

- **Columna** - El valor se toma de una columna de la tabla. Es el tipo de conductor más común.
- **Métrica** - El valor se toma de otra métrica del modelo.
- **Fórmula** - Una ecuación genera el valor. La ecuación puede incluir valores de la tabla o de otras tablas.

## Borrar un controlador

1. Haga clic en el controlador del diagrama Sankey.
2. Haga clic en **Eliminar** en la parte inferior del panel.
