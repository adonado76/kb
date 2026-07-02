---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Actualice los datos de referencia en un plan abierto"
breadcrumb: []
source_path: "it-planning/planning/update-data-open-plan.html"
images:
  - "resources/images/icons/3-dots.jpg"
  - "resources/images/it_planning_images/icon_gear.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Actualice los datos de referencia en un plan abierto

Cuando se crea un plan, éste hereda las versiones publicadas de los datos de referencia cargados actualmente en el módulo **Datos de referencia**. Si posteriormente se modifican los datos de referencia, habrá que actualizar los datos del plan. Dado que los datos de referencia se utilizan para estructurar los datos del plan y para etiquetar las partidas con atributos notificables, ciertos cambios en los datos de referencia pueden provocar la pérdida de datos. Por ejemplo, al eliminar un objeto de coste se eliminarán todas las partidas individuales plan asociadas a ese objeto de coste. Al eliminar una cuenta, todas las partidas etiquetadas con esa cuenta dejarán de ser válidas y, por lo tanto, se eliminarán. Otros cambios, como la eliminación de un proveedor, no provocarán la eliminación de las partidas individuales del plan, pero pueden dar lugar a una pérdida de fidelidad de los informes, ya que las partidas individuales previamente etiquetadas con el proveedor eliminado se etiquetarán ahora con un proveedor en blanco.

## Acerca de esta tarea

Puede actualizar los datos de referencia del plan siempre que los cambios no sean destructivos. Si la actualización sólo añade o modifica elementos de datos de referencia existentes, se permite por defecto. Sin embargo, las actualizaciones de los datos de referencia del plan que puedan causar una pérdida en los datos del plan no suelen estar permitidas. Sin embargo, los administradores pueden desactivar esta restricción en **Configuración**. Para obtener más información, consulte [Eliminar restricciones de actualización](update-data-open-plan.html#Remove). Encontrará más información en [Editar el perfil de la empresa](edit-company-profile.html).

Se crea automáticamente un plan de copia de seguridad para preservar la integridad de los datos cada vez que se realiza una actualización potencialmente destructiva.

Una vez eliminada la restricción, es posible realizar las siguientes actualizaciones:

- Puede eliminar elementos (como Objetos de Coste o Cuentas).
- Puede reorganizar su estructura de datos (por ejemplo, puede asignar un Objeto de Coste a un padre diferente).

Estas capacidades le permiten seguir utilizando su plan actual si su empresa se somete a una reorganización.

En primer lugar, determine si es necesario eliminar estas restricciones para actualizar su plan. Si sus actualizaciones no van a suponer una pérdida de datos, pase a [Actualizar un plan abierto](update-data-open-plan.html#Update).

## Procedimiento

- **Eliminar las restricciones de actualización**
  1. En el menú Apptio Planning , haga clic en el botón Configuración (![icono engranaje](../../../../../03-media/apptio-planning/resources/images/it_planning_images/icon_gear.jpg)) y, a continuación, en Perfil de empresa.

     Se abre la página Perfil de la empresa.
  2. En la sección Configuración, seleccione Desactivar restricciones de actualización de datos de referencia.
  3. Seleccione Guardar y Salir.

     Ahora las restricciones están desactivadas.
- **Actualizar un plan abierto**

  Después de realizar los cambios en sus datos de referencia, puede habilitar un plan actualmente abierto para que se ajuste a dichos cambios. Para obtener más información sobre la actualización de los datos de referencia, consulte [Editar y publicar tablas de datos de referencia](edit-publish-reference.html).

  1. Vaya a Planning>Planes y seleccione un plan.
  2. En el [menú de la subsección Plan](navigate-apptio-planning.html#Plan_Sub-section_Menu) (después de seleccionar Departamentos en el desplegable Sección ), seleccione Todos los departamentos (en el desplegable Departamento ).
  3. Seleccione ![tres puntos más menú](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.jpg) y, a continuación, Actualizar datos de referencia.

     Aparecerá un cuadro de diálogo con información sobre los cambios realizados, incluida la eliminación de partidas.
  4. Revise los cambios y seleccione Actualizar.

     Cuando realice la actualización, se creará automáticamente un plan de copia de seguridad para reflejar su plan anterior a las actualizaciones.
- **Acerca de los planes de respaldo**

  Nota: El historial del plan no se captura en un plan de copia de seguridad.

  Si ha desactivado las restricciones de actualización de datos de referencia, se creará automáticamente un plan de copia de seguridad cada vez que actualice datos de referencia en un plan abierto. El plan de copia de seguridad contiene todos los datos del plan anteriores a la actualización, con la notable excepción del historial del plan. Además, si realiza cambios posteriores en el mismo plan, el plan de copia de seguridad se sobrescribirá con cada cambio. En un momento dado, usted dispone de una copia de seguridad que conserva sus datos (y los datos de referencia de apoyo) anteriores a su actualización más reciente

## Información relacionada

- [update-data-open-plan.html #Updatereferencedatainanopenplan](update-data-open-plan.html#Updatereferencedatainanopenplan)
- [update-data-open-plan.html #Eliminar restricciones de actualización](update-data-open-plan.html#Removeupdaterestrictions)
- [update-data-open-plan.html #Updateanopenplan](update-data-open-plan.html#Updateanopenplan)
- [update-data-open-plan.html #Aboutbackupplans](update-data-open-plan.html#Aboutbackupplans)
