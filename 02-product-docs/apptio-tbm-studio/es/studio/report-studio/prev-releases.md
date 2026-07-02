---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Versiones anteriores"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Notas del release"
source_path: "studio/report-studio/prev-releases.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Versiones anteriores

## 12.11.21 - Abril de 2026

Atención: El nuevo estudio de informes ya está disponible para todos los usuarios y ofrece una experiencia moderna e intuitiva para crear, personalizar y consultar informes. Esta versión permite una implementación integral, que incluye la creación de informes, la migración y el intercambio de datos.

- **Control administrativo del acceso al visor de informes:** Los administradores ahora pueden controlar si los usuarios finales tienen acceso al visor de informes. Esta opción está activada de forma predeterminada, lo que garantiza que los usuarios finales puedan ver los informes. Los administradores pueden desactivarla en la configuración del proyecto si desean restringir el acceso.
- **Componente de botón:** añade un componente de botón configurable en Report Studio que permite a los usuarios activar acciones como la navegación y la ejecución de scripts al hacer clic. Incluye opciones de formato flexibles para personalizar el aspecto y el comportamiento de los botones dentro de los informes.
- **Reglas de visibilidad de las pestañas:** configura las expresiones de visibilidad de las pestañas dentro de un componente de grupo con pestañas. Las pestañas se mostrarán u ocultarán dinámicamente en el Visor de informes en función de las condiciones definidas.
- **Eje compartido en los gráficos superpuestos:** Los gráficos superpuestos admiten ahora un eje compartido, lo que permite alinear varias series de datos en una escala común para facilitar la comparación y mejorar la legibilidad.
- **Ajustes automáticos de línea para encabezados y celdas de tabla:** Las tablas y las tablas editables ahora admiten el ajuste automático de línea tanto en los encabezados de columna como en las celdas, lo que mejora la legibilidad y garantiza que el contenido sea totalmente visible sin necesidad de cambiar manualmente el tamaño.
- **Vistas guardadas en el Visor de informes:** guarda instantáneas personalizadas de los informes con tus filtros e interacciones preferidos. Cambia fácilmente entre vistas o configura una vista de inicio para navegar más rápido.
- **Enviar informes por correo electrónico desde el visor de informes:** Ahora los usuarios pueden enviar informes directamente desde el visor de informes por correo electrónico. El informe se puede compartir como archivo PDF adjunto o como enlace para ver o descargar el PDF.
- **Asistente de migración para informes:** Utiliza el Asistente de migración para migrar informes del TBM Studio clásico al nuevo Report Studio.
- Se han presentado las colecciones de informes listas para usar en versión preliminar pública.

## 12.11.20 - Febrero de 2026

- **Mostrar valores en las tablas:** explora la distribución de los datos a nivel de columna consultando los valores únicos y su recuento en el menú de la columna.
- **Vista en árbol para tablas** : Las tablas ahora admiten una nueva opción de vista en árbol que permite visualizar datos jerárquicos con filas que se pueden expandir y contraer.
- **Exportar informes a PDF:** Ahora puedes exportar informes a PDF directamente desde el nuevo Report Studio a través de **Archivo -> Descargar como -> PDF**, lo que permite compartirlos rápidamente sin tener que pasar al Visor de informes.
- **Exportar tablas a Excel:** Ahora puedes exportar tablas individuales de un informe directamente a Excel a través del menú desplegable de la tabla, lo que facilita el análisis y el intercambio de los datos del informe fuera de la aplicación. Actualmente disponible en el nuevo visor de informes.
- **Compatibilidad con múltiples divisas:** La compatibilidad con múltiples divisas ya está disponible en Report Studio y Report Viewer. Los administradores pueden probar los informes utilizando diferentes divisas y tipos de cambio, y los usuarios pueden cambiar de divisa en el visor; estas selecciones se reflejan en los informes en formato PDF y Excel.

## 12.11.19 - Enero de 2026

**Creación de informes y recopilaciones de informes con ajustes de visibilidad**

- Los informes ahora incluyen una configuración **de «Visible para»** durante su creación, lo que le permite controlar si un informe es visible para todos, solo para usted o para roles específicos.
- Las colecciones de informes ahora admiten la propiedad **«Visible para»**, lo que permite restringir la visibilidad a todos, solo a usted o a roles seleccionados.

**Actualización del diseño del panel del lienzo del informe** : los paneles Explorador de dimensiones, Datos y Formato para componentes y visualizaciones se han desplazado del lado derecho al lado izquierdo del lienzo del informe.

**Mejoras en los componentes del informe**

- Tabla: compatibilidad con visualizaciones compatibles
- Slicer: se ha añadido una nueva propiedad Slicer Type para dividir componentes con opciones de lista desplegable y vertical, lo que permite una presentación flexible basada en el diseño del informe y las necesidades de interacción del usuario.
- KPI: los KPI ahora admiten la visualización independiente de métricas primarias y secundarias, lo que le permite mostrar cada métrica por separado en lugar de solo en una vista comparativa.
- Los KPI, los selectores de columnas y los pivotes rápidos ahora admiten fórmulas personalizadas.

**Visualizaciones**

- Gráficos de columnas + líneas
- Gráficos de columnas apiladas + líneas
- Ordenación de datos en gráficos: ahora los gráficos admiten la ordenación configurable de datos, lo que le permite ordenar los datos por un valor seleccionado en orden ascendente o descendente desde el panel de datos.

**Opciones mejoradas de depuración de widgets y actualización de datos** : se han añadido nuevas acciones en el encabezado de los widgets para actualizar datos, ver rutas de datos completas y abrir datos de depuración en /data para facilitar la resolución de problemas y la validación.

**Exportar informes a PDF** : el visor de informes le permite exportar el informe que está viendo actualmente a un archivo PDF, lo que facilita la descarga, el intercambio o el archivo del informe en un formato imprimible.

## 12.11.18 - Noviembre de 2025

- **Soporte para la localización** : se ha añadido soporte para la localización en toda la nueva experiencia de Report Studio, lo que permite a los usuarios de todas las regiones disfrutar de una interfaz fluida y coherente en su idioma y formato preferidos.
- **Nuevos componentes** : componente de grupo para organizar y gestionar varios componentes de informes en el lienzo como una sola unidad.
- **Mejoras en la tabla**
  - Posibilidad de **renombrar columnas** directamente dentro de las tablas.
  - Compatibilidad con **filtros de cero** para incluir o excluir explícitamente valores cero.
  - Opción para **ocultar las dimensiones intermedias** y simplificar las vistas de tabla.
  - Mejoras en **las tablas editables** para facilitar la introducción de datos y la usabilidad.
- **Mejoras** en el selector de columnas: el selector de columnas ahora admite la selección basada en fechas, lo que permite a los usuarios controlar las columnas de fechas de forma dinámica.
- **Visualizaciones e interacciones** : compatibilidad con visualizaciones compatibles con navegación detallada habilitada en gráficos para una exploración más profunda de los datos.
