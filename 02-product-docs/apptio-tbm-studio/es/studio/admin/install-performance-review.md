---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Instalar el componente Evaluación del Rendimiento"
breadcrumb: []
source_path: "studio/admin/install-performance-review.html"
images:
  - "resources/images/studio_images/studio-components-version_cropped.png"
  - "resources/images/studio_images/studio_admin_analyze_performance_sui.png"
  - "resources/images/studio_images/studioimages/checkin_sui.png"
  - "resources/images/studio_images/studioimages/components_sui.png"
  - "resources/images/studio_images/studioimages/customized-element-sui.png"
  - "resources/images/studio_images/studioimages/perf-rev-upgrade_sui.png"
  - "resources/images/studio_images/studioimages/project-settings-sui.png"
  - "resources/images/studio_images/studioimages/revert-check-out_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Instalar el componente Evaluación del Rendimiento

Se aplica a: Apptio Costing Standard en TBM Studio 12.5 y posteriores. El componente Performance Review es una utilidad integrada en la aplicación que crea informes que un administrador de Apptio TBM Studio puede utilizar para obtener información sobre el impacto que la configuración actual de su proyecto tiene en el rendimiento de la aplicación.

## Disponibilidad

| Versión de la plataforma | Contenido |
| --- | --- |
| R12.5 y más tarde | v.105 carga útil del contenido |
| R12.9.3 | v.109 carga útil del contenido |

Nota: Para instalar el componente, debe estar en una versión de plataforma que admita la versión de contenido asociada.

## Requisitos previos para la instalación

Siga estos pasos para verificar que su entorno tiene acceso a una versión de contenido adecuada:

1. Abra TBM Studio en el proyecto en el que desee instalar el componente Performance Review.
2. Vaya a Proyecto > Configuración del proyecto.
3. Para validar la versión del contenido, en Versión del componente, asegúrese de que la versión 109 está disponible para seleccionarla.
4. Haga clic en "Cancel".

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-components-version_cropped.png)

## Instale el componente Performance Review en un proyecto con contenido v.109 configurado

Si su proyecto utiliza actualmente la versión de contenido v.109, siga estos pasos para instalar el componente de evaluación del rendimiento.

1. En la pestaña Proyecto del grupo Datos del proyecto, haga clic en Componentes.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/components_sui.png)
2. Haga clic en Revisión del rendimiento.
3. En el cuadro de diálogo Instalación de componentes, haga clic en Activar.

Una vez finalizada la instalación del componente, los informes Analizar rendimiento aparecen en el Explorador de proyectos, en Informes > Cálculo del coste del servicio > Analizar rendimiento.

## Instale el componente Evaluación del rendimiento en un proyecto con una versión de contenido anterior a v.109

Si su proyecto no utiliza la versión de contenido v.109, pero la ve en el menú desplegable Versión de los componentes en la Configuración del proyecto según los Requisitos previos al principio de este documento, aún puede instalarla sin comprometerse a una actualización completa del contenido o incluso sin guardar el cambio de versión del contenido.

Siga estos pasos para instalar el componente Evaluación del rendimiento sin tener que migrar a las plantillas de contenido de v.109.

1. En la pestaña Proyecto del grupo Configuración del proyecto, haga clic en Configuración del proyecto.
2. En la lista desplegable Versión de los componentes, seleccione Versión 109 y, a continuación, haga clic en Guardar.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/project-settings-sui.png)
3. En la pestaña Proyecto, en el grupo Datos del proyecto, haga clic en Componentes. Ahora debería ver el componente Evaluación del rendimiento.
4. Haga clic en Revisión del rendimiento.
5. En el cuadro de diálogo Instalación de componentes, haga clic en Activar. Una vez finalizada la instalación del componente, los informes Analizar rendimiento aparecen en el Explorador de proyectos en Informe > Cálculo del coste del servicio > Analizar rendimiento.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_admin_analyze_performance_sui.png)
6. En la cinta de menús de la parte superior de la pantalla, seleccione Inicio > Revertir cambios.
7. En el cuadro de diálogo Revertir Check Out, seleccione Configuración del proyecto, deje el resto de opciones sin seleccionar y haga clic en Revertir Check Out.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/revert-check-out_sui.png)

   Ha revertido la configuración del proyecto.
8. En la cinta de menús, seleccione Inicio > Registro.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/checkin_sui.png)

   Ya se ha registrado en la nueva versión del Analizador de Rendimiento.

## Actualización del componente de Evaluación del Rendimiento

Si ya tiene instalada una versión anterior del componente Evaluación del rendimiento, deberá revertir las personalizaciones existentes. Siga estos pasos.

1. En la cinta de menús de la parte superior de la pantalla, seleccione Proyecto > Componentes > Evaluación del rendimiento.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/components_sui.png)

   Si hay personalizaciones, aparecerán en la parte inferior de la página. Para revertir los elementos personalizados, haga clic en la flecha situada junto a la personalización. Haga esto para cada personalización.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/customized-element-sui.png)
2. Vaya a la Configuración del proyecto y cambie la Versión de los componentes a la Versión 109.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/project-settings-sui.png)
3. Vuelva a Componentes > Evaluación del rendimiento.
4. Desplácese hacia abajo si es necesario y haga clic en Actualizar.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/perf-rev-upgrade_sui.png)

## Utilizar el componente de evaluación del rendimiento

Para obtener información sobre el uso del componente Evaluación del rendimiento y los informes Analizar el rendimiento, consulte [Uso del componente Evaluación del rendimiento](use%20the%20performance%20review.htm "(se abre en una pestaña o una ventana nueva)").
