---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Editar partidas individuales de actividad laboral"
breadcrumb: []
source_path: "it-planning/planning/iip/allocate-labor-project.html"
images:
  - "resources/images/it_planning_images/layout-err.jpg"
  - "resources/images/it_planning_images/layout-new-view-1.jpg"
  - "resources/images/it_planning_images/layout-new-view-2.jpg"
  - "resources/images/it_planning_images/layout-new-view-3.jpg"
  - "resources/images/it_planning_images/layout-new-view.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Editar partidas individuales de actividad laboral

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Integrated Investment Planning permite a los propietarios de proyectos y a los propietarios de centros de coste asignar recursos a un proyecto como asignación basada en funciones o asignación basada en nombres.

La asignación de mano de obra al proyecto se realiza desde Planning > Gastos > Vista de actividad de mano de obra.

1. Seleccione Proyecto para la imputación de actividad laboral.

   El menú desplegable Centro de costes muestra los centros de costes aplicables al proyecto seleccionado.
2. Seleccione un Centro de costes.

   Normalmente, este centro de costes es la fuente de financiación del proyecto.

   Centro de coste El objeto de coste se rellena automáticamente según lo configurado en los datos de referencia.
3. Seleccione un Centro de coste de recursos.

   Es el Centro de Coste que proporciona los recursos laborales para trabajar en el proyecto.
4. Para asignar recursos a un proyecto en función de un rol, seleccione Rol laboral del proyecto para elegir el rol de recurso que desee.

   Por ejemplo, existe el rol laboral de proyecto Desarrollador y ese es el rol que usted ha asignado, lo que significa que cualquier recurso de ese rol puede ser asignado para trabajar en el proyecto.
5. Para asignar recursos a un proyecto como recurso laboral basado en el nombre o específico del Centro de costes de recursos, seleccione recurso específico en el menú desplegable Recurso.

   El menú Recursos filtra automáticamente sólo los recursos del Centro de Coste de Recursos seleccionado.
6. Seleccione el tipo de actividad.

   La configuración de la actividad en la línea establece la cuenta de centro de coste de cargo y la cuenta de cargo cruzado en función de la configuración de datos de referencia para la cuenta de actividad laboral.

   Para obtener más información, consulte [Configurar la carga cruzada](configure-cross-charge.html)
7. Seleccione Horas o ETC en el botón de alternancia ETC/Horas situado encima de la tabla de Gastos de Actividades Laborales. Introduzca la mano de obra asignada utilizando la unidad ETC o la unidad Horas según el conmutador seleccionado. Asegúrese de la alineación entre los datos disponibles en CSV y el conmutador seleccionado (ETC/horas).
8. Los datos introducidos como ETC se convertirán en Horas utilizando el Calendario Laboral para el recurso asignado.

Para obtener más información sobre la configuración del calendario de trabajo, consulte [Configurar un calendario de trabajo](../configure-working-days.html "El calendario laboral define cuántos días y horas laborables se utilizan para la planificación laboral, lo que influye en la conversión del equivalente a tiempo completo (ETC), la amortización de los costes laborales y los cálculos de gastos mensuales.").

Para obtener más información sobre el uso de calendarios en la planificación de la mano de obra, consulte [Asignación de mano de obra utilizando el calendario de días laborables.](planning-labor-allocation.html)

Los gastos de la actividad laboral del proyecto se generan en la vista Gastos > Resumen.

## Asignación de recursos para el centro de costes de recursos presentado

No se permite la asignación de recursos cuando un Centro de costes de recursos está bloqueado o enviado.

A continuación se explica el comportamiento esperado para las vistas Gastos > Vista clásica/antigua y Gastos > Vista nueva al seleccionar un Centro de coste de recursos que se encuentra en estado bloqueado o enviado.

El centro de coste de recursos "Apps-Back Office" está en estado presentado/bloqueado y el centro de coste de recursos "Apps-Line of Business" no está presentado.

Escenario 1 : Eliminar el centro de coste de recursos que se presenta/bloquea en la línea de Actividad Laboral.

## Gastos > Vista clásica/antigua

En la pestaña Gastos > Actividad Laboral, cambie el centro de coste de recursos de "Aplicaciones-Back Office" a "Aplicaciones-Línea de Negocio". La partida se resalta en rojo y aparece el mensaje de error tal y como se muestra.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/layout-err.jpg)

## Gastos > Nueva vista

Seleccione el desplegable Centro de coste de recursos. Puede ver el indicador y la información de que el Centro de Coste está bloqueado.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/layout-new-view.jpg)

Si sigue seleccionando el Centro de costes bloqueado, aparecerá un mensaje de error de validación como el que se muestra:

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/layout-new-view-1.jpg)

Escenario 2 : Asignar el centro de coste de recursos que se presenta/bloquea en la línea de Actividad Laboral.

## Gastos > Vista clásica/antigua

En la pestaña Gastos > Actividad laboral, cambie el centro de coste de recursos de "Aplicaciones-Línea de negocio" a "Aplicaciones-Back Office" para. El mensaje de error de validación aparece como se muestra:

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/layout-new-view-3.jpg)

## Gastos > Nueva vista

En la pestaña Gastos > Actividad laboral, cambie el centro de coste de recursos de "Aplicaciones-Línea de negocio" a "Aplicaciones-Back Office" para. El mensaje de error de validación aparece como se muestra:

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/layout-new-view-2.jpg)

En todos los casos anteriores, el cambio no se guardará.
