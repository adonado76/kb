---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Actualización diferida"
breadcrumb: []
source_path: "studio/reports/delayed-refresh.html"
images:
  - "resources/images/studio_images/del-ref-popup_885x911.png"
  - "resources/images/studio_images/delayed-refresh-new_875x416.png"
  - "resources/images/studio_images/df-checkin_855x279.png"
  - "resources/images/studio_images/df-chkout_842x344.png"
  - "resources/images/studio_images/df-report_844x395.png"
  - "resources/images/studio_images/df-tbm_883x327.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Actualización diferida

La función de actualización diferida permite a los usuarios seleccionar filtros, selectores o rebanadores y ver los resultados actualizados en el informe. Esto resulta útil para informes grandes y complejos en los que se realizan múltiples selecciones interactivas.

En 12.10.8, esta función estaba disponible como parte de Report Studio > Barra de navegación, con las opciones En directo, 2 segundos, 5 segundos y Actualización manual.

Desde 12.10.9, la función se ha mejorado para eliminar las opciones Live, 2 segundos y 5 segundos. Las nuevas opciones son:

- **Retraso de actualización: 3s:** El sistema espera 3 segundos antes de actualizar la pantalla.
- **Actualización manual** : Este modo requiere que el usuario seleccione Actualizar para actualizar el informe.

Esta función está disponible en tres vistas:

## Transparencia de costes

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/delayed-refresh-new_875x416.png)

Nota: Los cambios realizados en CT Report Studio no son persistentes para el usuario. Si el usuario cierra la sesión, volverá a aplicarse la configuración predeterminada de 3 segundos.

## TBM Studio

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-tbm_883x327.png)

La función de actualización diferida está disponible para todos los usuarios, con el valor predeterminado de **Refresh Delay: 3s** para todos los proyectos, pero el administrador puede cambiar la configuración a Manual Refresh. Para informes sencillos, se puede establecer en 3 segundos, mientras que para un informe grande con numerosos slicers, pickers, pivots, el usuario puede cambiar a la opción **Actualización manual**. Para cambiar la configuración de actualización, vaya a la pestaña **Proyecto** > **Configuración del proyecto** y cambie el valor del campo **Actualización diferida** en la ventana emergente Editar configuración del proyecto.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/del-ref-popup_885x911.png)

Esta configuración se aplicará a todos los informes. Pero puede cambiar la configuración de actualización para informes específicos siguiendo estos pasos:

1. En la pestaña **Inicio** de un informe, seleccione **Pago**

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chkout_842x344.png)
2. La pestaña **Informe** está activada. Aplique los filtros adecuados y modifique los ajustes de actualización según proceda.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-report_844x395.png)
3. En **Inicio**, seleccione **Guardar** y, a continuación, seleccione la opción **Registro**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-checkin_855x279.png)
