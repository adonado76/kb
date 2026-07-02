---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Prevenir la deslocalización"
breadcrumb: []
source_path: "it-planning/planning/iip/prevent-overallocation.html"
images:
  - "resources/images/it_planning_images/enable-disable-labor-activity.jpg"
  - "resources/images/it_planning_images/fte-oa-error.jpg"
  - "resources/images/it_planning_images/la-import.jpg"
  - "resources/images/it_planning_images/labor-edit.jpg"
  - "resources/images/it_planning_images/labor-over-allocated.jpg"
  - "resources/images/it_planning_images/legacy-view.jpg"
  - "resources/images/it_planning_images/over-allocated-popup.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Prevenir la deslocalización

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

La activación de esta función ayudará a los responsables del presupuesto a evitar la sobreasignación de recursos por encima de la capacidad disponible. Siga los pasos que se indican a continuación para activar y utilizar esta función.

## Activar Evitar la sobreasignación

Vaya a Perfil de la empresa > sección Habilitar capacidades y seleccione la casilla de verificación Actividad laboral.

Nota: La casilla de verificación Actividad Laboral será visible en el Perfil de la Empresa sólo si la casilla de verificación "Habilitar Integrated Investment Planning" está activada.

Las dos opciones aparecen como se indica a continuación.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/enable-disable-labor-activity.jpg)

Seleccione la opción Evitar la sobreasignación y, a continuación, Guardar y Salir en la página de perfil de empresa.

## Detectar y prevenir la deslocalización

En los siguientes escenarios, estamos intentando asignar a John, cuya capacidad mensual para enero es de 88 horas en el proyecto ' P193 - BI Analytics Enhancements' como 8 horas al día.

1. En la vista de gastos heredados, vaya a la pestaña de actividad laboral e introduzca un valor superior a 88 en Ene FY24. Si pasa el ratón por encima de la celda, aparecerá el mensaje de error emergente "*El recurso está sobreasignado para el periodo en 2.0 horas. por favor cambie a Nueva Vista para más detalles*". La diferencia entre el valor introducido 90 y la capacidad de Juan de 88 es de 2 horas.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/legacy-view.jpg)
2. Como el mensaje anterior no mostraba todos los detalles, cambiaremos a la vista de nuevos gastos y deslizaremos el conmutador hasta Horas. Una vez más, introduzca el mismo valor que el anterior en Ene FY24. La celda aparece resaltada con un icono de error rojo, y al pasar el ratón sobre ella se mostrará el mensaje de error que aparece a continuación.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/over-allocated-popup.jpg)

   La ventana emergente indicará que el recurso está sobreasignado para el periodo y proporcionará todos los detalles, como la capacidad mensual total, la asignación a la partida actual, la asignación a otra partida, la sobreasignación y los proyectos asignados, en horas.

   En este escenario, la diferencia entre el valor introducido 90 y la capacidad de Juan de 88 es de 2 horas y se muestra en rojo.
3. Ahora cambiemos a la vista de nuevos gastos y desplacemos el conmutador a ETC. Introduzca un valor superior a 0.5 en Ene FY24. La celda aparece resaltada con un icono de error rojo, y al pasar el ratón sobre ella se mostrará el mensaje de error que aparece a continuación.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/fte-oa-error.jpg)

   La ventana emergente dirá que el recurso está sobreasignado para el periodo, y proporcionará todos los detalles como la capacidad mensual total, la asignación en la partida actual, la asignación en otra partida, la sobreasignación, y los proyectos asignados, en ftes.

   En este escenario, la diferencia entre el valor introducido 0.9 y la capacidad de Juan de 0.5 es 0.4 ftes y esto se muestra en rojo.
4. En el siguiente escenario, impidamos la sobreasignación durante la edición de datos laborales desde la interfaz de usuario de gastos. Para ello, vaya a la pestaña Mano de obra y cambie la asignación de Juan en la celda Feb FY24.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/labor-edit.jpg)

   Aquí vemos que la capacidad mensual total para Juan en febrero de 2024 es de 84 horas (ya que febrero sólo tiene 21 días laborables). Está sobreasignado en 16 horas porque su asignación para Feb FY24 en la pestaña Actividad Laboral era de 100. Véase el 2º escenario anterior.
5. Tomemos ahora el escenario para evitar la sobreasignación durante la importación de Actividad Laboral. Exportar un fichero desde la pestaña Actividad Laboral. En el archivo CSV descargado, cambie la asignación de John para P1 FY2024 como 93, y guarde el archivo. Cuando cargue este archivo y seleccione Importar, aparecerá un mensaje de advertencia como el que se muestra.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/la-import.jpg)

   El mensaje muestra el nombre del fichero de actividad laboral y los problemas que tiene, como la sobreasignación y las modificaciones de filas. Amplíe la sección para ver los detalles de la incidencia.
6. En el último escenario, evitemos la sobreasignación durante la importación de mano de obra. Exportar un fichero desde la pestaña Trabajo. En el archivo CSV descargado, cambie la asignación de John para P2 FY2024 como 0.4, y guarde el archivo. Cuando cargue este archivo y seleccione Importar, aparecerá un mensaje de advertencia como el que se muestra.

   ![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/labor-over-allocated.jpg)

   El mensaje muestra el nombre del archivo de trabajo y los problemas que tiene, como la sobreasignación y las modificaciones de filas. Amplíe la sección para ver los detalles de la incidencia.

Nota:

- Esta función sólo está disponible cuando se asignan recursos individuales a proyectos/inversiones. Si el campo Recurso de la actividad laboral está vacío, no se admite la detección de sobreasignación.
- Cuando la función Evitar sobreasignación está activada, las sobreasignaciones en los planes existentes se detectarán cuando el usuario intente editar esas líneas desde la interfaz de usuario o intente volver a importar los datos de la actividad laboral.
- La modificación del calendario laboral provocará una sobreasignación de recursos si las nuevas horas de trabajo mensuales son inferiores a las anteriores. En tales casos, los gastos imputados en exceso se detectarán al editar o reimportar las líneas de actividad laboral.
- Si se configura el control de acceso a nivel de proyecto y el gestor de proyecto que ha iniciado sesión no tiene acceso para ver todas las asignaciones del recurso seleccionado, seguirá siendo posible detectar la sobreasignación causada por la asignación del recurso a otros proyectos. El código de proyecto de los proyectos en los que está asignado el recurso se mostrará en el mensaje emergente de detección de sobreasignación. Esta información ayudará al gestor de proyectos registrado a resolver la sobreasignación trabajando con los gestores de proyectos de los demás proyectos.
- Si la configuración del perfil de la empresa se cambia a Permitir sobreasignación, no será posible evitar la sobreasignación.
- La funcionalidad para establecer el umbral de sobreasignación y subasignación es un trabajo en curso, se lanzará a principios de Q2 2024.
