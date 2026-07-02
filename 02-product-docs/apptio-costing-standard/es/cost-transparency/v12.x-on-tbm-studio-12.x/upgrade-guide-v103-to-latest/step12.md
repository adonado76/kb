---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Paso 12: Actualizar el entorno de producción"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step12.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-26.png"
  - "resources/images/ct_images/upgrade-from-v3-27.png"
  - "resources/images/ct_images/upgrade-from-v3-28.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Paso 12: Actualizar el entorno de producción

Cuando termine de verificar los informes, envíe la aplicación actualizada a Producción.

1. Ir a la página **TBM Studio**.
2. Seleccione el entorno **Staging**.
3. En la cinta **Proyecto**, haga clic en **Bloquear**.

   Un breve mensaje emergente indicará que el entorno está bloqueado. El entorno ya está listo para pasar a Producción.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-26.png)
4. En la cinta **Proyectos**, haga clic en **Opciones de promoción** y, a continuación, realice una de las siguientes acciones:
   - Haga clic en **Promover ahora**. La actualización se envía inmediatamente a Producción.
   - Haga clic en **Promover más tarde** para programar cuándo se publicará la actualización en Producción.

     ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-27.png)
5. En la cinta **Proyecto**, haga clic en **Cola de cálculo** para verificar la compilación de producción.
6. Compare los números de compilación de los entornos de desarrollo, ensayo y producción.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-28.png)

## Información relacionada

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
