---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestión de entidades"
breadcrumb: []
source_path: "it-planning/planning/adm/custom-dimension-entitiy-metric.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestión de entidades

En Planning los clientes pueden crear hasta 13 dimensiones personalizadas para definir los conjuntos de categorías de datos que amplían y mejoran su planificación y análisis financieros.

Para obtener más información sobre las dimensiones personalizadas, consulte [Datos de referencia personalizados](../manage-custom-reference.htm "(se abre en una pestaña o una ventana nueva)").

Para que (Automated Data Management ) ADM actualice automáticamente los cambios en las dimensiones personalizadas a Planning, es necesario actualizar la tabla Entity Mapping en ADM sobre la dimensión personalizada recién creada para que el usuario pueda agregar el nombre del conjunto de datos en TBM Studio de donde provienen los datos fuente.

La adición/eliminación de dimensiones personalizadas en el mapeo de entidades está totalmente automatizada.

Cuando se agrega una nueva Dimensión Personalizada en Planning, Automated Data Management > **Entity Mapping** se actualizará automáticamente con la nueva entrada en la tabla Entity.

1. [Crear](../manage-custom-reference.htm "(se abre en una pestaña o una ventana nueva)")

   ![imagen](../../../resources/images/it%20planning_images/create-custom-dim_949x656.png)
2. Navegue hasta Automated Data Management > Entity Mapping. La dimensión "Orden de Compra" está automáticamente disponible en el Mapeo de Entidades ADM.

   ![imagen](../../../resources/images/it%20planning_images/ent-mapp.png)

Cuando una Dimensión Personalizada es borrada en Planning, el mapeo de entidad correspondiente en el Data Management Automatizado también será borrado si no hay otra aplicación que suscriba la dimensión borrada. En caso de que exista una suscripción activa distinta de Planning para la entidad que se está eliminando, sólo se eliminará la suscripción a Planning para esa dimensión.

**Tema principal:** [Conéctese a Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html)
