---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar los planes"
breadcrumb: []
source_path: "it-planning/planning/manage-plans.html"
images:
  - "resources/images/icons/icon-column-freeze_21x20.png"
  - "resources/images/icons/icon-filteron_18x20.png"
  - "resources/images/icons/icon-showhide_19x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar los planes

Con la página Planes, puede gestionar sus planes de forma fácil e intuitiva.

- Para abrir Planes, abra el panel de navegación izquierdo y seleccione Planificación > Planes.

  ![imagen](../../resources/images/it%20planning_images/plans2_430x128.png)

## Elija los planes que desea consultar

Utilice las pestañas de la parte superior de la pantalla para visualizar Todos los planes, Planes activos o Planes archivados.

## Seleccione las columnas que desea visualizar

Puede hacerlo en el panel Mostrar/Ocultar columnas.

- Seleccione ![más](../../resources/images/it%20planning_images/options1_23x20.png) > Abrir Mostrar/Ocultar columnas.
- Seleccione o desactive las casillas de verificación para añadir o eliminar columnas.

## Crear un nuevo plan

1. Seleccione ![añadir icono](../../resources/images/it%20planning_images/new-plan-icon_19x20.png).

   Se abre el cuadro de diálogo Nuevo plan.
2. Introduzca los datos del plan.

   [Más información sobre la creación de planes](create-budget-plan.dita "(se abre en una pestaña o una ventana nueva)")
3. Seleccione Crear plan.

   El nuevo plan se muestra en la página Presupuesto o Previsión.
4. Vuelva a Planes y confirme que el nuevo plan aparece ahora como Plan activo.

   Si Integrated Investment Planning está Activado, los proyectos se copiarán en el nuevo plan con uno de los siguientes métodos. Para obtener más información sobre Integrated Investment Planning, consulte [Introducción a Integrated Investment Planning](iip/gs-integrated-investment-planning.dita "(se abre en una pestaña o una ventana nueva)").

   - Crear plan sin plan base - Si está creando un plan sin plan base, los proyectos de la dimensión de datos de referencia "Proyecto" se añadirán en el plan.
   - Crear plan con plan base - Si está creando un plan con un plan base, los proyectos del plan base se añadirán al nuevo plan.

## Ver los detalles de un plan en el panel Propiedades

El panel de Propiedades muestra la siguiente información sobre un Plan:

- Tipo
- Estado
- Estado (sólo se muestra en la pestaña Todos los planes)
- Fecha de creación
- Plan Longitud
- Año de inicio del plan

Para ver un plano en el panel Propiedades, seleccione ![ver plano](../../resources/images/it%20planning_images/icon-plan-properties_21x20.png).

## Planes de filtrado

Para filtrar los valores mostrados en una columna del plan:

1. Pase el ratón por encima de la cabecera de la columna y seleccione ![Icono de](../../resources/images/it%20planning_images/burger-button_13x9.png).
2. Seleccione ![icono de filtro](../../../../../03-media/apptio-planning/resources/images/icons/icon-filteron_18x20.png) para filtrar los valores de las columnas.

   Recuerda: también puedes utilizar este panel para:
   - Mostrar y ocultar columnas, seleccionando ![icono de columna](../../../../../03-media/apptio-planning/resources/images/icons/icon-showhide_19x20.png)
   - Congelar y descongelar columnas, seleccionando ![descongelar columnas](../../../../../03-media/apptio-planning/resources/images/icons/icon-column-freeze_21x20.png)

   Planificar abre la lista de filtros para que elija. Por defecto, está seleccionado (Seleccionar todo).

   ![imagen](../../resources/images/it%20planning_images/plan-filter.png)
3. Filtre los valores a mostrar en la columna realizando una de las siguientes acciones:
   - Desmarque (Seleccionar todo) y seleccione las casillas de verificación situadas junto a los valores requeridos.
   - Introduzca un término de búsqueda para filtrar los valores. Se muestran en una lista todos los valores que coinciden total o parcialmente con el término de búsqueda. Para aplicar el filtro al plan, seleccione Intro.

   Puede filtrar cualquier columna, excepto las columnas con valores únicos por plan. Las columnas que tienen filtros aplicados aparecen con un icono de filtro en la cabecera.

   ![imagen](../../resources/images/it%20planning_images/current-filters.png)

## Borrar filtros

Para borrar los filtros, seleccione ![filtro](../../resources/images/it%20planning_images/clear-filters_20x20.png) encima del plan.

## Ordenar planes por columna

- Para ordenar los planes por una columna, pase el ratón por encima de la cabecera de la columna y seleccione ![Clasificar](../../resources/images/it%20planning_images/itfmf-ct_images/sort-icon_21x20.png).

## Archivar planes activos

Esto mueve el plan de su lista Activa a su lista Archivada. Puede restaurar un plan archivado al estado Activo en cualquier momento.

Sólo puede archivar planes en la pestaña Planes activos.

- Para archivar un único plan, haga clic con el botón derecho del ratón en el plan que desee archivar y seleccione Archivar.
- Para archivar varios planes, seleccione los planes utilizando la casilla de verificación de edición masiva, haga clic con el botón derecho en cualquiera de los planes que haya seleccionado y seleccione Archivar.

## Restaurar planes archivados

Sólo puede restaurar planes en la pestaña Planes archivados.

- Para restaurar un único plan, haga clic con el botón derecho en el plan que desea restaurar y seleccione Restaurar.
- Para restaurar varios planes, seleccione los planes utilizando la casilla de verificación de edición masiva, haga clic con el botón derecho en cualquiera de los planes que haya seleccionado y seleccione Restaurar.

## Eliminar planes

Puede eliminar planes desde cualquier pestaña.

Nota: Al borrar un plan, éste desaparece definitivamente del sistema.

- Para eliminar un único plan, haga clic con el botón derecho del ratón en el plan que desea eliminar y seleccione Eliminar.
- Para eliminar varios planes, selecciónelos utilizando la casilla de verificación de edición masiva, haga clic con el botón derecho en cualquiera de los planes que haya seleccionado y seleccione Eliminar.

## Plan de supresión suave

Desde la versión ApptioOne Planning 3.50, el proceso de eliminación del plan se realiza ahora en dos pasos:

- Eliminación suave : el plan se elimina de la interfaz de usuario en cuanto un administrador hace clic en el botón Eliminar de la página Planes. Los usuarios ya no podrán acceder al plan eliminado.
- Borrado permanente : los datos del plan se borran automáticamente dos días después del borrado permanente.

Los administradores ya no tienen que esperar a que se ejecute el largo proceso de eliminación de planes; pueden eliminar un plan rápidamente y continuar con otras tareas. En caso de que borres accidentalmente algún plan, hay un plazo de dos días para restaurar los datos del plan registrando un ticket de soporte en Apptio.

No hay ningún cambio para el usuario final en el proceso de eliminación del plan. Los pasos para eliminar el plan descritos aquí siguen siendo válidos. La única diferencia perceptible para el usuario final es que el plano se elimina muy rápidamente de la interfaz de usuario de la aplicación Planificación, independientemente del tamaño del plano.

Si se seleccionan varios planes para eliminar, las solicitudes de eliminación de datos del plan se añaden a una cola y se procesan secuencialmente durante el proceso de limpieza de datos.
