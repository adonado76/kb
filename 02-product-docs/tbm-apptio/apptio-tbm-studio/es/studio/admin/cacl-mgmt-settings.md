---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de Calc Management"
breadcrumb: []
source_path: "studio/admin/cacl-mgmt-settings.html"
images:
  - "resources/images/studio_images/cm-ribbon.png"
  - "resources/images/studio_images/pcm-popup.png"
  - "resources/images/studio_images/proj-calc-mgmt.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de Calc Management

Se aplica a: 12.11.0 y posteriores. Los clientes pueden ahora desactivar/activar los cálculos de escalonamiento a nivel de proyecto, de modo que pueden controlar qué proyectos se calculan y, a su vez, reducir el número de cálculos totales.

Calc Management no está activo por defecto. Para activarla, vaya a **Proyecto** > **Activar funciones** y seleccione **Gestión de calc. de proyecto**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/proj-calc-mgmt.png)

## Navegación

Vaya a la pestaña **Construir** de la cinta TBM Studio y seleccione **Gestión de Calc**

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cm-ribbon.png)

La ventana emergente Gestión del cálculo del proyecto aparece con tres pestañas: Configuración del cálculo, Cola de desarrollo y Cola de preparación

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pcm-popup.png)

## Ajustes Calc

Esta pestaña muestra la lista de proyectos con su prioridad junto con el estado del entorno de preparación (activado/desactivado). Puede actualizar la prioridad arrastrando la fila o introduciendo el valor deseado en el cuadro de entrada de prioridad. Además, puede actualizar el estado de cualquier proyecto desde esta pestaña mediante el botón de alternancia. Si desea activar/desactivar todos los proyectos de una sola vez, puede utilizar el botón **Activar todo/ Desactivar todo** situado en la parte superior de la tabla. \*\*

Una vez hecho esto, introduzca un **Motivo** para documentar el propósito del cambio y haga clic en el botón Enviar.

## Cola de desarrollo y cola de montaje

No hay cambios en la funcionalidad de **Dev Queue** y **Staging Queue**. Para saber más, consulte [Calc Prioritization](default-calc-prioritization.htm "(se abre en una pestaña o una ventana nueva)").

## Escenario de varios inquilinos

Hay dos escenarios en un sistema multi-tenant:

- **Con acceso limitado** : Si un usuario tiene acceso a todos o a pocos inquilinos, puede actualizar el estado de los proyectos a los que tiene acceso, pero no puede actualizar la prioridad de ningún proyecto. La cola de escenarios y la cola de desarrollo se desactivarían para un usuario con acceso limitado.
- **Con acceso total** : Si un usuario tiene acceso a todos los inquilinos, puede actualizar el estado o la prioridad de cualquier proyecto que figure en la ficha.
