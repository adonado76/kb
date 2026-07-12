---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Se utiliza la operación de unión del modelo heredado"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-legacy-join.html"
images:
  - "resources/images/studio_images/troubleshooting/legacy-join-automatic-relationship-checkbox.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-link-to-issue.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-locate-legacy-allocation.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns-2.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-warning.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Se utiliza la operación de unión del modelo heredado

El error *Legacy model join operation used* es el resultado de la forma en que se creaban las asignaciones de relaciones de datos en la versión R11 de TBM Studio. Algunas de las asignaciones por defecto están configuradas de esta manera para mantener la compatibilidad con versiones anteriores, así como para minimizar la fricción al actualizar el contenido.

## Acerca de esta tarea

La relación de datos como se muestra:

| Comparación de relaciones de datos | |
| --- | --- |
| R11 relación de datos heredados en TBM Studio R12 | TBM Studio R12 relación de datos |
| En la versión R12 de TBM Studio, este tipo de error, concretamente la casilla de verificación **Relación automática**, se muestra como se ve a continuación. | En R12, las asignaciones de relaciones de datos se crean determinando qué datos de columna deben coincidir entre objetos. A continuación, puede ver las columnas de origen y destino seleccionadas. |

## Recomendación de configuración para la operación de unión del modelo heredado error utilizado

Nota: Debido al versionado de objetos, es posible que tenga que solucionar el problema en varios periodos de tiempo diferentes para el mismo objeto.

Para resolver este error:

1. En la fila Documento, seleccione el enlace para abrir el objeto afectado.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-link-to-issue.png)
2. En la pestaña Inicio, seleccione Salida.
3. Recorra las asignaciones de salida hasta localizar la asignación heredada y selecciónela.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-locate-legacy-allocation.png)

   Se le redirige al objeto Modelo apropiado y al periodo de tiempo en el que existe la asignación heredada. Se enumeran las asignaciones utilizadas para todas las métricas disponibles, no sólo la seleccionada. Recorra las asignaciones disponibles una a una hasta localizar la asignación heredada. Actualmente, TBM Studio no puede dirigirle directamente a la línea de asignación exacta.
4. En Distribuir, desactive la casilla Relación automática y guarde los cambios.
5. Seleccione Sí para continuar.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-warning.png)
6. En Columna de origen y Columna de destino, seleccione los valores necesarios para establecer una nueva relación de datos para la línea de asignación.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns-2.png)

   Puede utilizar una o más relaciones de datos según sea necesario.
7. Confirme los cambios y valide que la asignación funciona como desea. Puede comparar el rendimiento de la nueva configuración con la configuración anterior aún disponible en Staging.
8. Compruebe en los cambios si el nuevo rendimiento es satisfactorio.

Atención: No puede volver a activar la configuración heredada para esta asignación después de registrar su nueva configuración. Apptio El servicio de asistencia puede ayudar a recuperar las configuraciones heredadas si es necesario.
