---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crea tu primer informe"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Inicio rápido"
source_path: "studio/report-studio/create-first/first-report.html"
images:
  - "resources/images/studio_images/nrs-fc-1.png"
  - "resources/images/studio_images/nrs-fc-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crea tu primer informe

Esta guía explica cómo crear un nuevo informe en el nuevo Report Studio. Al final de esta guía, tendrás un informe con componentes y visualizaciones listo para ver y compartir.

1. Navegue hasta la pestaña Nuevos informes
   1. Vaya a la pestaña **Nuevos informes** en la página de inicio
   2. Haga clic en el botón **Nuevo** y seleccione **Informe.**
2. Introducir detalles del informe
   1. **Nombre del informe** : asigne un nombre significativo a su informe.
   2. **Descripción (opcional)** : añada una breve descripción para ayudar a los usuarios a comprender el propósito del informe.
   3. **Visible para** : esta propiedad controla quién puede ver y acceder al informe.
      - Todos: el informe es visible para todos los usuarios con acceso al área de informes.
      - Solo yo: el informe solo es visible para usted. Útil para borradores, experimentación o análisis personal.
      - Seleccionar roles: el informe solo es visible para los usuarios asignados a los roles seleccionados. Los roles se seleccionan de una lista desplegable. Habilita el control de acceso basado en roles para los informes.
3. Añadir componentes
   1. En la barra de herramientas, seleccione un componente del menú Componentes.
   2. Elija entre los tipos de componentes disponibles, tales como:
      - Creador de secciones
      - Selector de columnas
      - Pivote rápido
      - HTML
      - Tabuladores
      - Grupo
   3. Elige un cortador
   4. Cuando se añade el cortador, los paneles Datos y Formato se abren a la derecha.
      1. El panel de datos se utiliza para configurar los datos que controlan el segmentador.
      2. El panel Formato se utiliza para personalizar la apariencia y el formato del segmentador.
   5. Configurar datos
      1. En el panel de datos, seleccione un objeto del modelo de datos en el menú desplegable.
      2. Haga clic en «Haga clic aquí o arrastre para añadir datos» para abrir el Explorador de dimensiones.
         - El Dimension Explorer muestra tablas, tablas editables, métricas y tiempo.
      3. Elija la dimensión por la que desea dividir los datos.
      4. Arrastra una dimensión desde Tablas al panel Datos.
      5. Utilice la sección de filtros para aplicar criterios de filtrado adicionales al segmentador.

      ![imagen del panel de datos](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/nrs-fc-1.png)

   Una vez configurado, el cortador filtra el informe en función de la dimensión seleccionada.
4. Añadir visualizaciones
   1. En la barra de herramientas, seleccione una visualización en el menú Visualizaciones
   2. Elija entre las visualizaciones disponibles:
      - ICR
      - Tabla
      - Tabla editable
      - Gráfico de barras
      - Gráfico de barras apiladas
      - Gráfico de columnas
      - Gráfico de columnas apiladas
      - Gráfico de líneas
      - Gráfico circular
   3. Seleccionar tabla
   4. Configurar datos
      1. En el panel de datos, seleccione un objeto del modelo de datos en el menú desplegable.
      2. Configure las secciones Filas, Columnas y Valores del panel de datos añadiendo dimensiones directamente desde el Explorador de dimensiones.
      3. Utilice la sección de filtros para aplicar criterios de filtrado adicionales a la tabla.

      ![Imagen de los datos configurados en la tabla](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/nrs-fc-2.png)
5. Guarde su informe
   1. Dado que la función de autoguardado está activada, los cambios se guardarán automáticamente a medida que cree el informe.
   2. También puede hacer clic manualmente **en** Guardar en cualquier momento para asegurarse de que su trabajo se guarde inmediatamente.
