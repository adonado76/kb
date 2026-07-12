---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Revisar, aprobar o devolver planes u objetos de coste"
breadcrumb: []
source_path: "it-planning/planning/review-approve-return.html"
images:
  - "resources/planning_images/itp_diagram_department-hierarchy.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Revisar, aprobar o devolver planes u objetos de coste

Vea este vídeo de Apptio Education Services: [Comprobación del estado, aprobación o devolución de planes](https://community.apptio.com/videos/1616 "(se abre en una pestaña o una ventana nueva)")

Cuando los Propietarios de Departamento, los Propietarios de Unidad de Negocio y (si está activado) los Propietarios de Proyecto o los Propietarios de Servicio envían su plan o previsiones para sus respectivos Objetos de Coste, los planes enviados son visibles inmediatamente en las páginas Todas las Secciones del Plan. Consulte [Editar el perfil de la empresa](edit-company-profile.html) y [Enviar un plan o previsión](submit-plan-forecast.html "Una vez introducida la información sobre el plan o la previsión, puede enviarla para su aprobación. El propietario del presupuesto puede enviar su plan desde la página Estado o Gastos.") para obtener más información. A continuación, los propietarios pueden revisar el plan del centro de costes y aprobarlo o devolverlo al propietario del presupuesto para que siga trabajando en él.

## Proceso de aprobación

La dimensión Permisos de Objetos de Coste determina quién puede realizar acciones con los Objetos de Coste. Consulte [los datos de referencia de Gestionar permisos de objetos de coste](manage-cost-object.html) para obtener más información. Los niveles de edición de los Permisos para Objetos de Coste incluyen los siguientes:

| Editar nivel | Vista | Editar | Enviar | Aprobar | Rechazar |
| --- | --- | --- | --- | --- | --- |
| Propietario (Owner) | Sí | Sí | Sí | Sí, si el Propietario se encuentra en un Objeto de coste de grupo | Sí, si el Propietario se encuentra en un Objeto de coste de grupo |
| Editar y enviar | Sí | Sí | Sí | Nee | Nee |
| Solo visualización | Sí | Nee | Nee | Nee | Nee |

Si los permisos se conceden a nivel de un objeto de coste de grupo, todos los permisos se aplican a cualquier objeto de coste hijo.

Nota: Los roles Administrador y Propietario de Proceso Presupuestario tienen nivel de edición "Propietario" en el nivel más alto de la jerarquía, incluso si no están listados en la jerarquía de Permisos de Objetos de Coste. Los usuarios deben tener al menos el rol de Propietario del Centro de Coste para tener niveles de edición de Propietario o Editar y Enviar.

Ejemplo

Si la jerarquía de su departamento incluye varios niveles, es posible que desee aplanar el flujo de trabajo de aprobación. Puede configurar la jerarquía de aprobación para omitir determinados niveles, de modo que los departamentos del nodo que omita pasen al propietario del siguiente nivel. En la siguiente imagen, el Grupo E, el Grupo F y el Grupo H son nodos "skip". Los departamentos dentro de esos grupos serían aprobados por el propietario del siguiente nivel: el plan para el Departamento D y el Departamento E sería aprobado por el propietario del Grupo B.

![img](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_department-hierarchy.png)

## Ver y gestionar los planos presentados

Los propietarios de los centros de coste pueden aprobar o rechazar los planes en cualquier momento. Si se asignan varios usuarios como propietarios, sólo será necesario que un usuario apruebe los planes. Si un propietario de nivel superior aprueba un plan, los niveles inferiores lo aprueban automáticamente.

1. En los menús de plan de la parte superior derecha, seleccione un plan, una categoría de objeto de coste y un objeto de coste o grupo de objetos de coste.

   [Más información sobre la navegación en Planificación](navigate-apptio-planning.html)
2. Vaya a Planning > Estado. Seleccione Incluir objetos de coste de sólo visualización para incluir objetos de coste con permisos de sólo visualización.

   Nota: La opción Aplicar permisos de visualización debe estar activada. Véase [Editar el perfil de la empresa](edit-company-profile.html).

   Desde la vista Estado, los usuarios pueden enviar, aprobar y devolver los objetos de coste. Hay dos formas de realizar esas acciones:
   - Columna Acciones - En la vista Estado, en la columna Acciones, en una fila de un objeto de coste o de un objeto de coste de grupo, seleccione Aprobar, Devolver o Enviar.

     Estas acciones pueden realizarse desde el nivel de objeto de coste hoja y desde el nivel de objeto de coste grupo. Cuando se realiza una acción a nivel de objeto de coste de grupo, se actualizan tanto el objeto de coste hoja como el objeto de coste grupo.

     [Más información sobre cómo afectan determinadas acciones a los objetos de coste de hoja y grupo](#ReviewapproveorreturnplansorCostObjects__ApprovalHierarchyActions)
   - Acciones masivas - En la vista Estado, en la primera columna, seleccione los objetos de coste utilizando las casillas de verificación. En el menú desplegable Acciones situado encima de la tabla, seleccione Aprobar seleccionados, Devolver seleccionados o Enviar seleccionados para realizar una acción masiva en los objetos de coste seleccionados.

     Los objetos de coste a nivel de grupo no se ven afectados por las acciones masivas.
   - Para enviar planes al propietario del presupuesto o al propietario del centro de coste, seleccione los elementos, seleccione Acciones y seleccione Enviar seleccionados. También puede seleccionar Enviar en la fila de cada partida individual.
   - Para aprobar planes, seleccione los elementos, seleccione Acciones y seleccione Aprobar seleccionados.
   - Para solicitar al propietario del presupuesto o al propietario del centro de coste que modifique un plan o planes presentados, seleccione los elementos, seleccione Acciones y seleccione Devolver seleccionado.

Una vez presentados todos los presupuestos, seleccione Finalizar plan.

Nota:

- Si varios usuarios comparten el mismo nivel de aprobación, sólo uno debe aprobar los planes.
- Si un propietario de nivel superior aprueba un plan, los niveles inferiores lo aprueban automáticamente.

## Acciones de la jerarquía de aprobación

Nota: El envío a nivel de grupo dará lugar a la aprobación automática de todos los objetos de coste secundarios, incluso si el remitente no tiene permiso explícito de aprobación.

La siguiente tabla describe las Acciones y el comportamiento resultante en Estado para Objetos de Coste:

| Acción | Comportamiento en el objeto de coste Hoja | Comportamiento en el objeto de coste de grupo |
| --- | --- | --- |
| Enviar | Marca el Objeto de Coste como "Enviado"  Crea una nueva instantánea no editable del objeto de coste enviado  Bloquea la edición de las líneas actuales de objetos de coste | Marca todos los Objetos de Coste hoja hijo como "Aprobados"  Crea una nueva instantánea no editable de todos los Objetos de Coste hoja hijos  No se verá afectado ningún objeto de coste de hoja secundaria que ya se encuentre en estado aprobado |
| Aprobar | Marca el objeto de coste como "Aprobado" Nota: Sólo los objetos de coste de hoja en estado "Enviado" tendrán esta opción | Marca el objeto de coste de grupo como "Aprobado" Marca como "Aprobado" cualquier objeto de coste de hoja hijo en estado "Presentado" |
| Rechazar | Marca el objeto de coste como "Rechazado" o "Devuelto" Nota: Sólo los objetos de coste de hoja en estado "Presentado" o "Aprobado" tendrán esta opción | Marca el objeto de coste de grupo como "Rechazado" o "Devuelto"  Cualquier objeto de coste de hoja hijo en estado "Presentado" o "Aprobado" no se verá afectado, a menos que el propietario del objeto de coste decida lo contrario. |

## Instantáneas

Una instantánea es una copia no editable de una partida en un plan abierto. Los usuarios pueden comparar un plan con una instantánea.

Se toma una instantánea automáticamente cuando ocurre una de las siguientes situaciones:

- Se presenta un plan.
- El estado de un plan cambia de Nuevo a Abierto.

Puede utilizar instantáneas al comparar planes.

Ver [Comparar versiones o planes](compare-versions-plans.html)

Cuando se toma una instantánea a nivel de objeto de coste, dicho objeto de coste no puede editarse.

## Tomar una instantánea manualmente

1. Abra el panel de navegación izquierdo y seleccione Planning > Planes.
2. En la lista Planes, seleccione un plan.
3. En la esquina superior derecha, en el menú de sección, seleccione una categoría de objeto de coste.

   ![img](../../resources/images/it%20planning_images/cost-object-category.png)
4. En la esquina superior derecha, en el menú de subsecciones, seleccione un objeto de coste.

   ![img](../../resources/images/it%20planning_images/cost_object_sub-section.png)
5. Seleccione una vista de tabla de partidas.

   ![img](../../resources/images/it%20planning_images/line-item_table_view.png)
6. En el menú desplegable de instantáneas, seleccione Guardar instantánea.

   ![img](../../resources/images/it%20planning_images/snapshot_save.png)
7. Introduzca el nombre de la instantánea.
8. Seleccione Crear.

## Instantáneas de acceso

1. Abra el panel de navegación izquierdo y seleccione Planning > Planes.
2. En la lista Planes, seleccione un plan.
3. En la esquina superior derecha, en el menú de sección, seleccione una categoría de objeto de coste.

   ![img](../../resources/images/it%20planning_images/cost-object-category.png)
4. En la esquina superior derecha, en el menú de subsecciones, seleccione un objeto de coste.

   ![img](../../resources/images/it%20planning_images/cost_object_sub-section.png)
5. Selecciona el desplegable de instantáneas.

   ![img](../../resources/images/it%20planning_images/snapshot_dropdown.png)
