---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Asignar la mano de obra del departamento"
breadcrumb: []
source_path: "it-planning/planning/allocate-department-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Asignar la mano de obra del departamento

## Antes de empezar

Antes de empezar, asegúrese de activar las funciones de planificación laboral. Véase [Editar el perfil de la empresa](edit-company-profile.dita).

## Acerca de esta tarea

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Una vez configurados los datos de referencia de mano de obra, puede hacer que la mano de obra esté disponible para el trabajo a través de pools de recursos de mano de obra y asignaciones. Para obtener más información, consulte [los datos de referencia de Gestión de la configuración de mano de obra](manage-labor-configuration.dita). Los Propietarios de Departamento pueden asignar a un proyecto, servicio o bolsa de trabajo. Estas asignaciones departamentales también aparecen en las tablas de asignación de mano de obra de sus proyectos y servicios. Las asignaciones de mano de obra también aparecen como cargos en la página del Libro Mayor del departamento para los usuarios con licencia de Project Financial Planning o Service Demand Planning.

## Procedimiento

- **Introducir datos de asignación de mano de obra**

  Trabaje con detalles de mano de obra planificada en la pestaña Mano de obra, página Planificada.

  1. En los menús de Plan en la parte superior derecha, seleccione un Plan, una categoría de Objeto de costo y un objeto de costo o grupo de objetos de costo.

     [Más información sobre la navegación en Planificación](navigate-apptio-planning.html#Toolbar).

     Nota: Los propietarios de centros de costos solo pueden editar sus centros de costos asignados. Para obtener más información, consulte [los datos de referencia de Gestionar permisos de objetos de coste](manage-cost-object.html).
  2. Vaya a Planning >Gastos.
  3. Seleccione la pestaña Trabajo.
  4. Seleccione Existente para planificar los ajustes de compensación laboral para la mano de obra actual.
  5. Seleccione Planificado para planificar los ajustes de remuneración laboral para el trabajo planificado.
  6. Seleccione Editar asignaciones en la columna Asignaciones. La tabla de Asignación de Recursos muestra e incluye las siguientes columnas:
     - Tipo de objeto de coste - El grupo de objetos de coste que se asignará al recurso.
     - A Objeto de Coste - El Objeto de Coste específico a asignar al recurso.
     - A cuenta - La cuenta que recibe el dinero por el servicio.
     - De la cuenta - La cuenta que retira el dinero para pagar el servicio.
     - Cantidad - Los periodos de tiempo (meses, trimestres y años) en los que un porcentaje del recurso se asigna al objeto de coste.
- **Ver datos de asignación de mano de obra**

  Cuando se han introducido las asignaciones, aparece una opción de Asignaciones junto a los enlaces Planificado y Existente en la pestaña Mano de obra. Haga clic en Asignaciones para ver los detalles en una tabla de sólo lectura.

  Puede ver las asignaciones de las siguientes maneras:

  - Un valor porcentual.
  - Un valor equivalente a tiempo completo (ETC).
  - Unidad de medida laboral prefigurada, tal y como se define en el perfil de la empresa. Para más información, consulte [Editar el perfil de la empresa](edit-company-profile.html).
