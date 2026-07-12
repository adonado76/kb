---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Tipo de actividad laboral"
breadcrumb:
  - "Planning"
  - "Planificación de la actividad laboral del proyecto"
source_path: "it-planning/planning/iip/manage-labor-activity-type-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Tipo de actividad laboral

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

Los datos de referencia **del tipo de actividad laboral** definen cómo fluyen los cargos laborales y los cargos cruzados entre el **proveedor** (centro de costes del departamento) y **el consumidor** (centro de costes del proyecto) en función del tipo de actividad laboral realizada.

Cada tipo de actividad laboral especifica las cuentas financieras utilizadas para cargar y acreditar la mano de obra, y si la actividad es capitalizable. Estas asignaciones se utilizan durante [la planificación de la actividad laboral](labor-resource-planning.html) para garantizar que los costes laborales se asignen con precisión a los centros de costes correctos.

## Configurar el tipo de actividad laboral

***Nota:*** *Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.*

1. En el menú de navegación, vaya a: **Datos de referencia** → **Dimensiones estándar** → **Tipo de actividad laboral**
2. Haga clic en el ![menú de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menú y **seleccione Exportar plantilla**.
3. Descargue la plantilla y rellene los campos obligatorios:

   |  |  |
   | --- | --- |
   | **Campo** | **Descripción** |
   | **Nombre** | El nombre de la actividad laboral (por ejemplo, desarrollo, soporte, mantenimiento). Este es el valor seleccionado al planificar el esfuerzo laboral en la pestaña Actividad laboral. |
   | **Cuenta de crédito** | El código de cuenta del centro de coste del departamento (proveedor) que recibe el crédito cuando se proporciona mano de obra a un proyecto u otro centro de coste. |
   | **Cuenta de cargos cruzados** | El código de cuenta del centro de coste del proyecto (consumidor) que recibe el cargo por la mano de obra consumida. |
   | **¿Es capitalizable?** | Indica si la mano de obra para este tipo de actividad puede capitalizarse. - Cierto: los costes laborales son susceptibles de capitalización. - Falso: los costes laborales se contabilizan como gastos. |
   | **Es el valor predeterminado** | Determina el tipo de actividad laboral predeterminado que se aplica cuando los usuarios introducen la mano de obra en la pestaña Actividad laboral. - Solo se puede marcar un tipo de actividad como predeterminado. - Si un usuario no selecciona un tipo de actividad, se aplica el valor predeterminado. |
4. Importa el CSV actualizado.
5. Haga clic en el ![menú de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) menú y **publique** los cambios para que estén disponibles para los planes.
