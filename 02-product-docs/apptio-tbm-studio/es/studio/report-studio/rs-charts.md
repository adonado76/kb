---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos"
breadcrumb: []
source_path: "studio/report-studio/rs-charts.html"
images:
  - "resources/images/studio_images/cv-2b.png"
  - "resources/images/studio_images/drill-1c.png"
  - "resources/images/studio_images/srill-2d.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos

Los gráficos, cuando se utilizan correctamente, pueden transmitir información valiosa con rapidez.

La aplicación ofrece una amplia gama de tipos de gráficos, entre los que se incluyen:

1. Barra (barra y barra apilada)
2. Columna (columna y columna apilada)
3. Línea
4. Gráfico circular
5. ICR

## Visualizaciones compatibles

La función Visualizaciones compatibles permite cambiar rápidamente entre tipos de gráficos compatibles sin tener que reconstruir la visualización. Esto le ayudará a experimentar con distintos formatos visuales y a encontrar el que mejor represente sus datos.

**Pasos a seguir**

1. Seleccione un gráfico
2. Haga clic en un gráfico (por ejemplo, un gráfico de barras) de su informe.
3. Utilizar la opción de conversión
4. En la cabecera del widget, localice el icono Visualizaciones compatibles.
5. Seleccione el icono para ver una lista de visualizaciones compatibles para el tipo de gráfico seleccionado.

   ![imagen de visualizaciones compatibles](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cv-2b.png)
6. Seleccione un tipo de visualización
7. Seleccione entre opciones como:
8. Gráfico de columnas
9. Gráfico de barras apiladas
10. Gráfico de columnas apiladas
11. El gráfico se actualiza instantáneamente al tipo visual elegido, conservando los datos, el formato y la configuración existentes.

## Navegación de perforación para cartas

La navegación de perforación permite a los usuarios explorar los datos de forma interactiva haciendo clic en los gráficos de un informe para ver un informe relacionado más detallado en una superposición modal. Esto permite un análisis más profundo y una navegación fluida entre las vistas resumidas y detalladas, todo dentro de la misma experiencia de elaboración de informes.

Pasos a seguir

1. Añadir una perforación
   1. Abra el panel de configuración de datos del gráfico.
   2. En el menú de desbordamiento de una dimensión, seleccione Configurar desbordamiento.
   3. Nota: Las dimensiones añadidas en la sección Leyenda del panel de datos tienen activado el desglose.

      ![configurar perforación](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drill-1c.png)
2. Configure los ajustes de navegación de perforación: El menú de configuración de navegación de perforación incluye las siguientes opciones:
   1. Destino de perforación
      1. Seleccione el informe de destino que se abrirá en una superposición de modelo cuando un usuario haga clic en el gráfico.
      2. Esta es la vista detallada vinculada a su gráfico actual.
   2. Mostrar la barra de contexto del filtro
      1. Añade una barra de contexto de filtro al informe modal.
      2. Activado por defecto para dar a los usuarios visibilidad sobre los filtros aplicados al explorar la vista de desglose.
   3. Filtros
      1. Filtro en la fila seleccionada: Filtra el informe de destino utilizando los valores del punto de datos seleccionado.
      2. Filtrar según selección de corte aplicada - Filtra el informe de destino utilizando las selecciones de corte del informe actual.
      3. Insertar filtros de informe actuales: aplica todos los filtros actualmente activos en el informe de origen al informe de investigación.
   4. Columnas añadidas
      1. Añade la columna seleccionada actualmente: Incluye la columna asociada al punto de datos sobre el que se ha hecho clic en el informe de desglose.
      2. Incluye las columnas añadidas del informe actual: Transfiere las columnas adicionales seleccionadas a través del selector de columnas al informe de destino.

         ![taladro a través de columna añadida](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/srill-2d.png)
   5. Utilizar la navegación de perforación
      1. Tras la configuración, los usuarios pueden hacer clic en un punto de datos dentro del gráfico para abrir el informe vinculado en una superposición modal.
      2. Los filtros aplicados y el contexto se reflejan automáticamente, lo que ayuda a los usuarios a trazar perspectivas desde un resumen de alto nivel hasta datos detallados con un solo clic.
      3. Funciona tanto en el estudio de informes como en el visor de informes.
