---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Trabajar con el Panel de Integración de la Transparencia de Costes"
breadcrumb: []
source_path: "it-planning/planning/cti_panel.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Trabajar con el Panel de Integración de la Transparencia de Costes

El panel actualizado Cost Transparency Integration (CTI), introducido en la versión Planning 2.78, es un espacio autónomo en el que los usuarios administradores pueden realizar todas las tareas de Cost Transparency Integration dentro de un único panel de control. El nuevo panel ofrece gestión centralizada e importación y exportación con un solo clic y Transparencia de costes.

## Acceso al panel CTI

El panel Cost Transparency Integration le permite realizar todas las tareas CTI, que están divididas en páginas separadas. Las siguientes secciones de este tema describen el contenido de cada página y las tareas correspondientes que se pueden realizar.

1. Inicie sesión en Planning.
2. Abra el menú Configuración.
3. Haga clic en Cost Transparency Integration.

## Configurar el panel CTI

Esta opción contiene los ajustes de configuración del CTI. Este proceso de configuración suele ser completado por los miembros del equipo de entrega de Apptio en la configuración inicial, y rara vez se modifica posteriormente.

No se han introducido cambios en la página de configuración con respecto a versiones anteriores del producto. Para más información sobre ese proceso de configuración, consulte [Integrar con Costing Standard](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.").

## Importaciones reales

La tarea Importar reales la realiza un TBMA (normalmente una vez al mes) para importar los datos de gastos reales de Costing Standard a Planning. Utilice los Reales importados para formar previsiones, realizar análisis de desviaciones y crear otras vistas de comparación.

1. En la página Importar reales CTI, seleccione los meses para los que desea importar reales.

   Si se eligen varios meses, se realizará una importación masiva.
2. Una vez seleccionados todos los meses, pulse el botón azul Importar.

Aparece un mensaje que recomienda ir a la página Estado y comprobar el estado del trabajo. Para el proceso de Importación de Reales, vaya a la página de Estado.

También puede volver a la página de inicio de CTI para continuar con otras tareas de CTI. No se le impide realizar otras tareas de Planning y CTI, aunque esté en curso un trabajo de importación grande o prolongado.

## Importar datos de referencia

PlannPlanninging utiliza los datos de referencia como información de base a efectos de planificación, e incluye información como el plan contable, la jerarquía de departamentos o listas de centros de costes y proveedores. La página Importar datos de referencia le permite extraer datos de referencia de Costing Standard a Planning.

1. Seleccione de la lista los datos de referencia que desea importar.
2. Desplácese hasta la parte inferior de la página y pulse el botón Importar.

Todos los conjuntos de datos de referencia se seleccionan por defecto, lo que permite la importación masiva.

Aparece una ventana emergente que recomienda ir a la página Estado y comprobar el estado del trabajo. Para finalizar el proceso de Importar Datos de Referencia, debe ir a la página Estado y publicar los datos importados cuando el trabajo haya finalizado.

Nota: Se recomienda revisar los datos cargados si se han realizado cambios importantes. Una vez publicados los datos de referencia, no hay forma de revertirlos.

También puede volver a la página de inicio de CTI para continuar con otras tareas de CTI. No se le impide realizar otras tareas de Planning y CTI, aunque esté en curso un trabajo de importación grande o prolongado.

## Publicar en Costing Standard

El modelo de datos Costing Standard sólo admite un presupuesto y una previsión para el análisis. Por consiguiente, sólo se puede pasar uno de cada tipo de plan de Planning a Costing Standard. Utilice la página Publicar en CT para determinar y publicar manualmente los planes adecuados en Transparencia de Costes.

1. Seleccione un plan en el menú desplegable y seleccione todos los tipos de partidas que desea publicar.
2. Haga clic en el botón azul Publicar cuando esté listo, y comenzará un trabajo de publicación.

Todos los tipos de partidas se seleccionan por defecto.

Aparece una ventana emergente que recomienda ir a la página Estado y comprobar el estado del trabajo. Sin embargo, el proceso Publicar en CT no requiere ninguna tarea de seguimiento: podrá encontrar sus datos importados en CT una vez finalizado el trabajo.

También puede volver a la página de inicio de CTI para continuar con otras tareas de CTI. No se le impide realizar otras tareas ITP y CTI aunque esté en curso un trabajo de importación grande o prolongado.

## Estado

Puede acceder a esta página en cualquier momento para visualizar el estado de cada trabajo CTI que se haya intentado, programado o completado.

| Estado | Descripción |
| --- | --- |
| Inicio y fin | Las horas de inicio y fin del trabajo correspondiente. |
| Iniciado por | El correo electrónico del usuario que inició el trabajo. |
| Estado | El progreso del trabajo: QUEUE, SUCCESS, SUCCESS WITH WARNINGS, o FAIL. |
| Acciones | Acciones de seguimiento que deben realizarse:  - Publicar datos una vez que los trabajos de importación se hayan realizado correctamente (por ejemplo, Publicar datos de referencia después de la importación).  - Ver para encontrar y descargar registros de errores de trabajos fallidos. |
