---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Actualizar la visibilidad de los informes de infraestructura tras la actualización de v106"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/ct-upgrade-inf-visibility-after-v106.html"
images:
  - "resources/images/ct_images/ct-upgrade-inf-vis-1.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-2.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-3.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-4.png"
  - "resources/images/ct_images/gear_icon.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Actualizar la visibilidad de los informes de infraestructura tras la actualización de v106

A partir de TBM Studio 12.6 (con la plantilla v106 ), los informes Infra Server y Storage se trasladaron a la colección de informes Infrastructure Insights desde la colección de informes Infrastructure & Cloud en Costing Standard. Debido a este cambio en la navegación, por defecto en Enhanced Access Administration se muestra que los informes son visibles por Nadie, lo que puede crear confusión cuando intente acceder a sus antiguos informes.

Se aplica a: Costing Standard en TBM Studio 12.6 y posteriores, con Plantilla v106 y posteriores

Para corregir la navegación, siga los siguientes pasos para volver a configurar los componentes CT Server y Storage.

## Actualizar a 12.6

1. Asegúrese de actualizar los siguientes componentes durante su actualización a TBM Studio 12.6:
   - CT Apps - Centros de datos
   - CT Apps - Servidores
   - CT Apps - Almacenamiento

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-1.png)

   Para más información, consulte [Actualizar Costing Standard de la plantilla v104+ a la última versión](../../cost-transparency/v12.x%20on%20tbm%20studio%2012.x/upgradect-v104.htm "(se abre en una pestaña o una ventana nueva)").
2. Haga clic en el icono Configuración ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png) y, a continuación, en Access Administration.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-2.png)
3. Haga clic en la pestaña Aplicaciones.
4. En la fila Infrastructure Insights, haga clic en Mostrar.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-3.png)

La columna Visible para cambia de Nadie a Visible para cualquier usuario con permisos para Costing Standard.

El menú de informes Costing Standard muestra ahora Infrastructure Insights. Si hace clic en Infraestructura y Nube, se le redirigirá a la ruta actualizada de los informes de Infraestructura.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-4.png)

## TBM Studio ( 12.6 y posteriores) en Infrastructure Insights

A partir de 12.6, los siguientes informes siguen estando en el núcleo de Costing Standard , pero también son visibles en Infrastructure Insights:

- Computa:
  - Resumen de utilización
  - Detalles del servidor anfitrión
  - Por aplicaciones
- Centros de datos:
  - Resumen
  - Resumen operativo
  - Visión financiera
- Almacenamiento:
  - Resumen de utilización
  - Por aplicaciones
- Servicio de asistencia técnica:
  - Resumen
  - Detalles de tarea
  - Detalles de recurso
  - Por aplicaciones

## Costing Standard ( 12.5 y anteriores) informes en Costing Standard componentes

Los siguientes informes constituían el núcleo de Costing Standard antes de 12.6.

- Computa:
  - Resumen
  - Perfil de gasto
  - Resumen operativo
  - Detalles del servidor lógico
  - Visión financiera
- Almacenamiento:
  - Resumen
  - Perfil de gasto
  - Resumen operativo
  - Detalles de dispositivo
  - Detalles del LUN de almacenamiento
  - Visión financiera

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
