---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Ajustes de la asignación de mano de obra"
breadcrumb: []
source_path: "it-planning/planning/iip/allow-over-allocation.html"
images:
  - "resources/images/it_planning_images/allow-allocation-1.jpg"
  - "resources/images/it_planning_images/allow-oa-1.jpg"
  - "resources/images/it_planning_images/allow-oa-2.jpg"
  - "resources/images/it_planning_images/allow-oa-3.jpg"
  - "resources/images/it_planning_images/allow-oa-4.jpg"
  - "resources/images/it_planning_images/allow-oa-5.jpg"
  - "resources/images/it_planning_images/ao-1.jpg"
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Ajustes de la asignación de mano de obra

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

La selección de esta opción ayudará a los responsables del presupuesto a permitir la sobreasignación de recursos. También permite establecer umbrales de asignación "por exceso" y "por defecto" para marcar las asignaciones que superen o queden por debajo de los umbrales configurados. Siga los pasos que se indican a continuación para activar y utilizar esta función.

## Activar Permitir sobreasignación

Vaya a Perfil de la empresa > sección Habilitar capacidades y seleccione la casilla de verificación Actividad laboral. Seleccione la opción Permitir sobreasignación y, a continuación, Guardar y salir de la página de perfil de empresa.

AVISO : La casilla de verificación Actividad Laboral será visible en el Perfil de la Empresa sólo si la casilla de verificación "Habilitar Integrated Investment Planning" está activada.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-1.jpg)

También puede establecer los valores umbral de los recursos que están "sobre" asignados o "infra" asignados. En este caso, si un recurso está infraasignado en un 20% o sobreasignado en un 10% o más, la diferencia se marcará en el color mencionado. Después de configurar los valores umbral, seleccione Guardar y Salir.

Vaya a la pestaña Gastos > Actividad Laboral. Desde ![más icono](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg), active la opción Analizar la asignación de mano de obra.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/ao-1.jpg)

Los recursos se agrupan y las asignaciones que superan el umbral definido (por debajo del 20% y por encima del 10%) se resaltan en los tonos de color adecuados, como se muestra. Las casillas sin color indican que su asignación está dentro de los umbrales definidos.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-allocation-1.jpg)

El tono de la celda coloreada se puede emparejar con la tecla de la parte superior, para entender cuál es el porcentaje de la asignación por exceso o por defecto.

## Detectar y permitir la sobreasignación

Considera que la capacidad de trabajo para Juan en enero de 2024 es de 88 horas y para junio de 2024 es de 160 horas.

Navegue hasta la pestaña Gastos > Actividad Laboral y deslice el conmutador hasta Horas. Pase el ratón sobre cualquier celda sombreada en azul. La ventana emergente dirá que el recurso está infraasignado en cuántas horas, cuál es su capacidad mensual total y cuáles son sus otras asignaciones.

En este escenario, la diferencia entre el valor introducido 48 y la capacidad de 160 de Juan es de 112 horas, y el recurso está infraasignado en 112 horas.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-2.jpg)

Del mismo modo, ahora pase el ratón sobre cualquier celda sombreada en rojo. La ventana emergente dirá que el recurso está sobreasignado por cuántas horas, cuál es su capacidad mensual total y cuáles son sus otras asignaciones.

En este escenario, la diferencia entre el valor introducido 176 y la capacidad de Juan de 88 es de 88 horas, y el recurso está sobreasignado en estas 88.00 horas.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-3.jpg)

A continuación, cambie el conmutador a ETC y pase el ratón sobre cualquier celda sombreada en rojo. La ventana emergente dirá que el recurso está sobreasignado en cuántos ETC, cuál es su capacidad mensual total y cuáles son sus otras asignaciones, todo en ETC.

En este escenario, la diferencia entre el valor introducido 1 y la capacidad de John de 0.5 ETC es de 0.5 ETC, y el recurso está sobreasignado en 0.5 ETC.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-4.jpg)

Del mismo modo, si pasa el ratón sobre cualquier celda sombreada en azul, la ventana emergente le dirá que el recurso está infraasignado en cuántos ETC, cuál es su capacidad mensual total y cuáles son sus otras asignaciones, todo ello en ETC.

En este escenario, la diferencia entre el valor introducido 0.65 y la capacidad de John de 1 ETC es 0.35 ETC, y el recurso está infraasignado en 0.35 ETC.

![imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/allow-oa-5.jpg)
