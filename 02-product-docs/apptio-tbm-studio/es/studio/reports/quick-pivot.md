---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componente Quick Pivot"
breadcrumb: []
source_path: "studio/reports/quick-pivot.html"
images:
  - "resources/images/studio_images/quickpivot.png"
  - "resources/images/studio_images/quickpivot1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente Quick Pivot

**Se aplica a** : TBM Studio 12.0 y posteriores

El componente Partición rápida agrupa las entradas de la tabla por los valores de una columna seleccionada.

Cuando el usuario selecciona una columna del menú desplegable Partición rápida, esa columna pasa a ser la primera de la tabla.

![pivote rápido desplegable](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/quickpivot.png)

Las filas se ordenan por los valores de la columna seleccionada.

![ID de proyecto](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/quickpivot1.png)

## Crear un pivote rápido

1. Abra el informe con la tabla que desea pivotar.
2. En la pestaña **Informe**, haga clic en **QuickPivot**. La aplicación añade un **QuickPivot** objeto al informe y muestra el panel de **configuración QuickPivot**.
3. Utilizando el campo de la parte superior del panel, seleccione la tabla que desea pivotar.
4. Desde el **Explorador de proyectos**, arrastre uno o más campos al área **Pivots** de la **configuración de QuickPivot** panel.The. Los campos que arrastre al área estarán disponibles en la lista desplegable QuickPivot. Los campos bloqueados dan los resultados más predecibles. Sin embargo, por lo general obtendrá resultados satisfactorios si utiliza campos desbloqueados.
5. En la pestaña **QuickPivot** elija una de las opciones de selección.
   - **Selección no obligatoria** : Una opción "ninguno" estará disponible en el QuickPivot
   - **Selección obligatoria** : La opción "ninguno" no estará disponible en el QuickPivot
