---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Navegación por taladro"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Conceptos fundamentales"
source_path: "studio/report-studio/create-first/drill-navigation.html"
images:
  - "resources/images/studio_images/disable-drillthru.png"
  - "resources/images/studio_images/drill1c.png"
  - "resources/images/studio_images/drilld2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navegación por taladro

La navegación por perforación permite a los usuarios explorar los datos de forma interactiva haciendo clic en los gráficos de un informe para ver un informe relacionado más detallado en una ventana modal superpuesta. Esto permite un análisis más profundo y una navegación fluida entre las vistas resumidas y detalladas, todo ello dentro de la misma experiencia de generación de informes.

1. Añadir un drill-through
   1. Abre el panel Configuración de datos del gráfico.
   2. En el menú desplegable de una dimensión, seleccione Configurar Drill-Through.
   3. Nota: Las dimensiones añadidas en la sección Leyenda del panel de datos tienen habilitada la función de exploración.

   ![Imagen de navegación por perforación](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drill1c.png)
2. Configurar los ajustes de exploración: El menú de configuración de la navegación de exploración incluye las siguientes opciones:
   1. Destino de perforación
      1. Seleccione el informe de destino que se abrirá en una superposición del modelo cuando un usuario haga clic en el gráfico.
      2. Esta es la vista detallada vinculada a su gráfico actual.
   2. Mostrar barra de contexto del filtro
      1. Añade una barra de contexto de filtro al informe modal.
      2. Habilitado de forma predeterminada para que los usuarios puedan ver los filtros aplicados al explorar la vista detallada.
   3. Filtros
      1. Filtrar en la fila seleccionada: Filtra el informe de destino utilizando los valores del punto de datos seleccionado.
      2. Filtrar por selección de segmentador aplicada: filtra el informe de destino utilizando las selecciones del segmentador del informe actual.
      3. Insertar filtros del informe actual: aplica todos los filtros actualmente activos en el informe de origen al informe detallado.
   4. Columnas añadidas
      1. Añadir columna seleccionada actualmente: Incluye la columna asociada al punto de datos seleccionado en el informe detallado.
      2. Incluir columnas añadidas al informe actual: Transfiere cualquier columna adicional seleccionada mediante el selector de columnas al informe de destino.

      ![Imagen de la navegación de perforación para la columna seleccionada](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drilld2.png)
   5. Uso de la navegación por perforación
      1. Después de la configuración, los usuarios pueden hacer clic en un punto de datos dentro del gráfico para abrir el informe vinculado en una ventana emergente modal.
      2. Los filtros aplicados y el contexto se reflejan automáticamente, lo que ayuda a los usuarios a rastrear la información desde un resumen de alto nivel hasta datos detallados con un solo clic.
      3. Funciona tanto en el estudio de informes como en el visor de informes.
   6. Los usuarios pueden desactivar las interacciones de desglose configuradas directamente desde el Panel de datos sin necesidad de eliminar y volver a crear la configuración. Esto ofrece una mayor flexibilidad y control a la hora de gestionar las interacciones de los informes y permite activar o desactivar fácilmente la función de desglose a medida que cambian las necesidades de generación de informes.

   ![Imagen que muestra la opción de desactivar el desglose](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/disable-drillthru.png)
