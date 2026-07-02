---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "El espacio de trabajo del informe"
breadcrumb: []
source_path: "studio/reports/report-workspace.html"
images:
  - "resources/images/studio_images/studioimages/access_tbm_studio.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_workspace_800x397.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# El espacio de trabajo del informe

**Se aplica a** : TBM Studio 12.0 y posteriores

El espacio de trabajo del informe se divide en tres paneles.

- **Explorador de proyectos** : Sirve para seleccionar un informe que desee editar.
- Panel de **configuración de componentes** : Sirve para añadir columnas y valores a una tabla o gráfico.
- Espacio de trabajo **de edición de informes** : Construye tu informe en este panel añadiendo tablas y gráficos.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_workspace_800x397.png)

## Explorador de proyectos

El panel **Explorador de proyectos** muestra los documentos disponibles. Los documentos están agrupados en secciones:

- Tablas
- Métricas
- Perspectivas
- Informes

Cuando trabaje con informes, se centrará en la sección **Informes**.

Para mostrar el panel **Explorador de proyectos**, realice una de las siguientes acciones.

1. En TBM Studio 12.2 +: Abra el menú Proyecto/Aplicaciones y haga clic en TBM Studio.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/access_tbm_studio.png)
2. En las versiones anteriores a TBM Studio 12.2:, haga clic en el icono Modo Estudio situado a la derecha de la cabecera Global.

Para cambiar la anchura del panel del Explorador, arrastre el tirador del borde derecho.

Para minimizar el panel del Explorador, haga clic en la flecha de minimización situada en la esquina superior derecha.

Para buscar un informe en el Explorador de proyectos, introduzca texto en el filtro de la sección Informe.

## Panel de configuración de componentes

Utilice el panel **Configuración de componentes** para crear las tablas y gráficos que añada a los informes. Para construir las tablas y los gráficos, arrastre los valores desde el **Explorador de proyectos** a las áreas del panel.

Para construir una tabla o un gráfico, arrastre los campos desde el **Explorador de proyectos** a las áreas de la parte inferior del cuadro de diálogo. A continuación se describen las cuatro áreas.

- **Filas** - Proporciona las entradas para la primera columna de la tabla o el eje x en un gráfico. Si hay entradas duplicadas en la fuente, las entradas se agrupan y se muestra una única entrada para cada valor único. Si añade más de un campo al área, se crean subgrupos en la primera columna de la tabla.
- **Valores** - Proporciona los datos mostrados en el cuerpo de la tabla o gráfico. Puede ocultar un valor haciendo clic con el botón derecho en el valor y seleccionando **Ocultar**.
- **Columnas** - Proporciona las cabeceras de las columnas de la tabla. Arrastre un campo aquí desde una perspectiva. Sólo se puede poner un campo en el área **Columnas**.
- **Filtros** - Filtra las entradas de una columna de la tabla o gráfico. Arrastre aquí los campos desde las perspectivas y otras áreas. Si utiliza una métrica, puede hacer clic con el botón derecho en la métrica y establecer el intervalo de números.
  - Se pueden añadir múltiples campos en todas las áreas excepto en el área **Columnas**. Si un campo no puede aplicarse a un área, aparece un mensaje de advertencia.
  - Para eliminar un campo de un área, arrástrelo fuera del área o haga clic con el botón derecho en el campo y seleccione Eliminar.

## Espacio de trabajo de edición de informes

Utilice el panel del área de trabajo **de edición de informes** para construir el informe añadiendo tablas, gráficos y otros componentes del informe. Para añadir componentes, haga clic en la pestaña **Informe** y haga clic en un componente.
