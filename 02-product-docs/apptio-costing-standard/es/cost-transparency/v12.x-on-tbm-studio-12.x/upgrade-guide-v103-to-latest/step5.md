---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Paso 5: Actualizar componentes individuales y comprobar los cambios"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step5.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-10.png"
  - "resources/images/ct_images/upgrade-from-v3-7.png"
  - "resources/images/ct_images/upgrade-from-v3-8.png"
  - "resources/images/ct_images/upgrade-from-v3-9.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Paso 5: Actualizar componentes individuales y comprobar los cambios

1. En el cuadro de diálogo Configuración de componentes, haga doble clic en un componente específico, por ejemplo, **CTF - Fuente de costes**.

   Se abre una página de componentes.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-7.png)
2. Desplácese por debajo de la lista de informes incluidos hasta la sección **Actualización disponible**.
   - Una casilla azul indica que no se han realizado personalizaciones en ningún elemento del componente.
   - Un recuadro amarillo indica que se han encontrado personalizaciones con los datos, las métricas calculadas o los informes.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-8.png)

   En ocasiones, el cuadro amarillo permanece después de revertir todas las personalizaciones. Para continuar, haga clic en el botón **Actualizar** del recuadro amarillo.
3. Si existen personalizaciones, haga clic en **Ver conflictos** o desplácese hasta el final de la página.
4. Revertir los informes personalizados y las métricas calculadas.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-9.png)
5. Para los conjuntos de datos personalizados, revierta los conjuntos de datos personalizados para los siguientes componentes relacionados con Cloud:
   - CTF- Proveedor de servicios en nube
   - CTF- Amazon Web Services
   - CTF- Azure

   Haga una captura de pantalla de sus asignaciones actuales para ayudarle a reasignar los campos de etiquetado.

   Nota: **NO** revierta los conjuntos de datos para ningún otro componente. Si revierte los cambios en los conjuntos de datos, deberá volver a anexar y mapear los archivos de origen a los conjuntos de datos maestros.
6. Haz clic en **Actualizar**.

   La aplicación tarda unos minutos en procesar la actualización. Después de que la página del componente se actualice y vuelva a la página de Configuración del componente, puede continuar. Compruebe que ya no aparece la flecha de actualización.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-10.png)
7. Si ha revertido los cambios del conjunto de datos para los informes de la Nube, reasigne los archivos de origen a los Datos Maestros, como se indica a continuación:
   1. En el Explorador de proyectos, haga clic en **Tablas**.
   2. Haga clic en **Datos maestros**.
   3. Anexar.
   4. Asigne las columnas de origen a las columnas de datos maestros correspondientes.

      Utilice la captura de pantalla que capturó en el paso anterior para verificar las asignaciones.
8. Una vez finalizada la actualización, deberá modificar manualmente los conjuntos de datos que no se hayan revertido. Para v104, consulte la lista acumulativa de [actualizaciones de datos de las plantillas v103 a v104](../../user-guide/template103to104dataupdates-9027.html) para identificar qué cambios son necesarios.
9. Compruebe todos los cambios relacionados con la actualización de un único componente de uno en uno, de la siguiente manera:

   Nota: Si no sigue estos pasos para registrar los componentes de uno en uno, podría producirse un error que le obligaría a perder su trabajo y a reiniciar la actualización desde el principio.

   1. Seleccione **Proyectos** y, a continuación, haga clic en **Registrar**.

      Se abre el cuadro de diálogo Check In.
   2. Seleccione **Todos los elementos** en el panel izquierdo (por defecto).
   3. Introduzca una descripción de los elementos en el panel **Mensaje**.

      Nota: Introduzca una descripción útil, como "Fuente de costes: revertir cambios del conjunto de datos, componente actualizado" Esto es crítico para las actividades de fusión de ramas más adelante en este proceso de actualización. Revise [el Paso 9: Fusionar cambios en el proyecto principal (Trunk)](step9.html) para entender por qué esto es importante.
   4. Pulse **Check In**.
   5. Continúe con el paso 6.

## Información relacionada

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
