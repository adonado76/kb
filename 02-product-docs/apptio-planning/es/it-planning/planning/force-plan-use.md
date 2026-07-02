---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Forzar un plan para utilizar datos de referencia actualizados"
breadcrumb: []
source_path: "it-planning/planning/force-plan-use.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Forzar un plan para utilizar datos de referencia actualizados

Cuando un administrador o propietario de proceso presupuestario actualiza dimensiones en los datos de referencia, los planes existentes no se actualizan simultáneamente. Para obtener información sobre la actualización de dimensiones, consulte [Dimensiones de datos de referencia](manage-reference-data.html "(se abre en una pestaña o una ventana nueva)") y seleccione el enlace de categoría de dimensión adecuado. Los planes están asociados a una instantánea de datos de referencia. El Administrador o Propietario del Proceso Presupuestario puede ver la actualización específica de datos de referencia que se ha realizado y, a continuación, proceder a actualizar el plan para utilizar los datos de referencia más actuales.

Nota: Puede desactivar las restricciones de actualización de datos en un plan abierto. Sin embargo, estas actualizaciones conllevan el riesgo de pérdida de datos. Para más información, consulte [Actualizar datos de referencia en un plan abierto](update-data-open-plan.htm "(se abre en una pestaña o una ventana nueva)").

## Ver y actualizar los datos de referencia

1. Vaya a Planning > Planes y seleccione el plan.
2. En la esquina superior derecha de la página, seleccione Actualizar datos de referencia.
3. Revise los detalles de los datos de referencia. Si los datos están actualizados, seleccione Cancelar. Si no, seleccione Actualizar para actualizar la nueva información.

## Ver y actualizar los datos de referencia de un Open plan

Puede actualizar los datos de referencia de un plan en estado Nuevo o Abierto. Un plan en el Nuevo estado puede aplicar todas las actualizaciones de datos de referencia. Un plan en estado Abierto puede aplicar las siguientes actualizaciones a partir de los datos de referencia:

- Crear objetos de coste de hoja
- Crear dimensiones personalizadas
- Añadir o modificar atributos de dimensión
- Añadir valores a una dimensión

Si su plan se encuentra en estado Abierto y necesita actualizaciones adicionales, puede lograrlo con la siguiente solución. Tenga en cuenta que puede desactivar las notificaciones en el Perfil de la empresa para que, cuando realice cambios, no se envíen correos electrónicos de notificación a los Propietarios de procesos presupuestarios. Véase [Editar el perfil de la empresa](edit-company-profile.htm "(se abre en una pestaña o una ventana nueva)").

1. Archive el plan, dándole un nuevo nombre (consulte [Archivar, restaurar o eliminar planes](manage-plans.htm "(se abre en una pestaña o una ventana nueva)") )
2. Cree un plan y nómbrelo con el nombre del plan original (véase [Crear un plan o previsión](create-budget-plan.htm "(se abre en una pestaña o una ventana nueva)") ). Los nuevos datos de referencia se utilizan automáticamente en el nuevo plan. Recuerda: si has desactivado las notificaciones, vuelve a activarlas.
3. Abra el nuevo plan (véase [Abrir un plan o una previsión](open-plan-forecast.htm "(se abre en una pestaña o una ventana nueva)") ).

Actualmente, no es posible actualizar una parte de referencia en un plan. Al seleccionar la opción **Actualizar Datos de Referencia** en el Plan, se presentan al administrador los detalles relativos a las dimensiones que se actualizarán, cuántas líneas se modificarán y si el usuario procede a aplicar las actualizaciones. A continuación, el administrador puede decidir si procede o no a la actualización de los datos de referencia.
