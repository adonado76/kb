---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Programa de actualización de tablas"
breadcrumb: []
source_path: "studio/data_studio/table-update-schedule.html"
images:
  - "resources/images/studio_images/table-update-schedule.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Programa de actualización de tablas

**Se aplica a** : TBM Studio 12.6 y posteriores

Puede publicar información de una tabla editable en una tabla estándar mediante tres métodos principales:

1. Puede "actualizar" manualmente en TBM Studio.
2. Puede "publicar" manualmente los cambios del informe.
3. Puede "publicar" automáticamente actualizaciones de forma rutinaria.

## Actualizar manualmente en TBM Studio

1. Ir a **TBM Studio**
2. Seleccione su proyecto en el menú de la izquierda
3. En la sección Explorador de proyectos, seleccione la tabla que desea publicar. Por ejemplo: Seleccione la Transformación en Planificación de la demanda (basada en una tabla editable).
4. Seleccione la opción **Tabla editable** en **Pasos**.
5. Una vez seleccionado esto, podrá ver diferentes periodos. Haga clic con el botón derecho del ratón en el icono para actualizar este periodo.

   ![Tabla editable](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/table-update-schedule.png)

## Publicar manualmente los cambios en la superficie de notificación

Puede actualizar los datos de un informe y publicar manualmente los cambios de la tabla editable en la tabla de transformación asociada para ver los resultados el mismo día.

Requisitos previos
:   Para publicar manualmente los cambios del informe, necesita acceso Dev y acceso Stage como usuario, pero no necesita TBM Studio ni acceso Admin.

Cómo publicar manualmente los cambios del informe:
:   Desde un informe con una tabla editable:

    1. Introduzca los cambios deseados y seleccione **Guardar**.
    2. Seleccione **Publicar** en la parte inferior del informe > seleccione **Publicar** de nuevo para la ventana emergente de advertencia.
    3. Introduzca la descripción y seleccione **Check In** en el modal Check In.

## Establecer un calendario de actualización automática de las tablas

1. En la barra de la cinta TBM Studio , seleccione la pestaña **Construir**.
2. Seleccione **Opciones de promoción**.
3. Seleccione **Actualizaciones periódicas para tablas editables**.
4. Programar Repetición = Diaria y fijar Hora de Inicio con Desplazamiento.
5. Seleccione **Añadir nueva Hora de inicio** para crear hasta cuatro horas de ejecución.
6. Deseleccione Activar para desactivar la función.

**Tema principal:** [Tablas editables: Adaptación a las entradas del usuario](../../studio/data_studio/editabletables.html "Se aplica a: TBM Studio 12.6 y posteriores")
