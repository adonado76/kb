---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Informe Canvas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Trabajar con informes"
source_path: "studio/report-studio/create-first/canvas-layout.html"
images:
  - "resources/images/studio_images/canvas-format-panel.png"
  - "resources/images/studio_images/canvas-layout.png"
  - "resources/images/studio_images/rs-arrangemenu.png"
  - "resources/images/studio_images/rs-editmenu.png"
  - "resources/images/studio_images/rs-filemenu.png"
  - "resources/images/studio_images/rs-viewmenu.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Informe Canvas

El lienzo de informes es donde los administradores crean y editan informes añadiendo componentes, configurando datos y organizando visualizaciones.

## Diseño del lienzo

![Imagen del lienzo del informe](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/canvas-layout.png)

El lienzo del informe está organizado en las siguientes áreas:

- **Área de lienzo del informe** : el espacio de trabajo principal donde se colocan y organizan los componentes y las visualizaciones.
- **Barra de herramientas superior** : ofrece acciones como alinear, agrupar, eliminar, deshacer y rehacer. Componentes y visualizaciones que puedes añadir.
- **Panel de capas (izquierda)** : muestra la jerarquía de los componentes de su informe. Desde aquí, puedes copiar, pegar, reordenar, eliminar o cambiar la pertenencia a un grupo.
- **Explorador de dimensiones (derecha)** : muestra tablas, tablas editables, métricas y tiempo. Utilice esta función para arrastrar y soltar dimensiones en las configuraciones de los componentes.

## Panel de formato de lienzo

El panel Formato del lienzo le permite controlar el aspecto general del lienzo del informe. Esta configuración se aplica a todo el diseño del informe.

- Tamaño del lienzo
  - Elija un tamaño predefinido o establezca dimensiones personalizadas
  - El tamaño del lienzo determina cómo se distribuye el contenido y cómo se ve el informe cuando se exporta a PDF.
- Color de fondo del lienzo
  - Utilice Color de fondo para establecer el color de fondo del lienzo del informe.
  - Aplicado de manera coherente en todo el informe

![Imagen del formato de los elementos del lienzo del informe](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/canvas-format-panel.png)

## Menú Canvas

El lienzo del informe incluye menús que proporcionan acceso a acciones comunes durante la creación o edición de informes.

**Menú Archivo**

El menú **Archivo** contiene acciones a nivel de informe para gestionar las versiones de los informes y guardar los cambios.

![menú de archivos](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-filemenu.png)

- Registrar: guarda los cambios y pone el informe a disposición de otros usuarios.
- Revisar: bloquea el informe para su edición, de modo que pueda realizar cambios sin conflictos.
- Revertir cambios: descarta los cambios no guardados y restaura el informe a la última versión registrada.
- Guardar: guarda manualmente el estado actual del informe.
- Guardar como: crea un nuevo informe guardando una copia del informe actual con un nombre diferente.

**Menú Editar**

El menú **Editar** proporciona acciones para realizar cambios en el contenido del lienzo del informe.

![menú de edición](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-editmenu.png)

- Deshacer: revierte el cambio más reciente.
- Rehacer: vuelve a aplicar el último cambio deshecho.
- Copiar: copia el componente o la visualización seleccionados.
- Pegar: pega el componente o la visualización copiados en el lienzo.

**Ver menú**

El menú Ver controla cómo se muestra el lienzo del informe y cómo se colocan los elementos mientras se diseña un informe.

![ver menú](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-viewmenu.png)

- Tamaño real: muestra el lienzo a su escala original.
- Ajustar a la página: escala el lienzo para que toda la página quepa dentro de la vista disponible.
- Ajustar al ancho: escala el lienzo para ajustarlo al ancho del espacio de trabajo.
- Mostrar cuadrícula: muestra una cuadrícula en el lienzo para ayudar a alinear los componentes.
- Mostrar reglas: muestra reglas horizontales y verticales para un posicionamiento preciso.
- Ajustar a la cuadrícula: alinea automáticamente los componentes con la cuadrícula al moverlos o cambiar su tamaño.
- Mostrar capas: muestra el panel de capas para gestionar el orden de apilamiento de los componentes.

**Organizar menú**

El menú **Organizar** ayuda a organizar y colocar los componentes y las visualizaciones en el lienzo del informe.

![organizar el menú](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-arrangemenu.png)

- Alinear: alinea los componentes seleccionados a lo largo de sus bordes.
- Distribuir: espacia uniformemente los componentes seleccionados horizontalmente (Mayús + Alt + H) o verticalmente (Mayús + Alt + V).
- Traer al frente: mueve el componente seleccionado a la parte superior del orden de capas.
- Enviar al fondo: mueve el componente seleccionado al final del orden de capas.
- Avanzar: mueve el componente seleccionado un paso hacia adelante
- Enviar hacia atrás: mueve el componente seleccionado un paso hacia atrás

## Menú desplegable del encabezado del widget

Cada widget incluye un menú desplegable en el encabezado que ofrece acciones rápidas para actualizar e inspeccionar datos, convertir a visualizaciones compatibles, eliminar y otras operaciones de uso común.

**Actualizar datos**

Utilice esta opción para actualizar manualmente el widget.

- Activa una nueva recuperación de los datos más recientes para el widget.
- Útil cuando los datos subyacentes han cambiado y desea ver los resultados actualizados de inmediato.
- No requiere una recarga completa del informe.
- Úselo después de actualizaciones de datos, cambios de configuración o si el widget parece estar desincronizado.

**Mostrar ruta completa de datos**

Muestra la ruta de datos completa utilizada para generar el widget.

- Abre un modal que muestra la jerarquía completa de datos y referencias.
- Ayuda a comprender cómo se obtienen y procesan los datos del widget.
- Útil para la depuración, la validación y las investigaciones de soporte técnico.
- Úselo para rastrear el linaje de los datos o verificar la fuente de datos que alimenta el widget.

**Abrir en /data**

Abre los datos de depuración del widget en una nueva pestaña.

- Navega a la ruta /data URL asociada al widget.
- Muestra los datos sin procesar o de nivel de depuración utilizados por el componente.
- Destinado principalmente a la resolución de problemas.
- Úsalo para una inspección más profunda de los datos o para la depuración.
