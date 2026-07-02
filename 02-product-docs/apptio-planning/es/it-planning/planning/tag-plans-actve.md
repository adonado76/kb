---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Etiquetar planes como activos"
breadcrumb:
  - "Planning"
  - "Creación y gestión de planes"
source_path: "it-planning/planning/tag-plans-actve.html"
images:
  - "resources/images/it_planning_images/tagpln1.png"
  - "resources/images/it_planning_images/tagpln2.png"
  - "resources/images/it_planning_images/tagpln3.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Etiquetar planes como activos

La función **Etiquetar como activo** permite a los administradores dar prioridad a los planes importantes marcándolos como **Activos**. Esto ayuda a los usuarios a localizar rápidamente los planes más importantes y a centrarse en ellos.

Nota: Para gestionar planes se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Cuando un plan está etiquetado como Activo, lo estará:

- Mostrar una **etiqueta "Activo** " junto al nombre del Plan
- Aparecen automáticamente en la **parte superior del menú desplegable Plan**
- Ser tratado como el **plan por defecto** cuando los usuarios inician sesión

![imagen del plan de etiquetado como activo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln1.png)

## Cómo marcar o desmarcar un plan como activo

Desde la página de planos

- Haga clic con el botón derecho en un plan y seleccione **Etiquetar activo**
- Para eliminar la etiqueta, vuelva a hacer clic con el botón derecho y seleccione **Eliminar etiqueta activa**

![imagen del plano de etiquetas de la página del plano](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln2.png)

Al crear un nuevo plan

- En el modal **Crear Nuevo Plan**, marque **Etiqueta como Activa**
- El plan se marcará como Activo inmediatamente después de su creación

![mag foe nuevo plan](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tagpln3.png)

## Comportamiento de los planes activos

|  |  |
| --- | --- |
| **Comportamiento** | **Descripción** |
| Visualización | La etiqueta Activo aparece junto al nombre del plan en el menú desplegable Plan. |
| Ordenación | Los planes activos aparecen siempre en primer lugar, ordenados alfabéticamente si hay más de uno. |
| Planes no activos | Los planes y carpetas sin la etiqueta Activo aparecen debajo de los planes Activos, también por orden alfabético. |
| Plan por defecto al iniciar sesión | Si sólo hay un plan Activo, los usuarios serán asignados por defecto a ese plan. Si existen varios planes activos, se asignará por defecto a los usuarios el plan creado más recientemente. |
| Norma de archivo | Los planes archivados no pueden etiquetarse como Activos. Si se archiva un plan Activo, la etiqueta se elimina automáticamente. |
| Seguimiento de auditoría | Todos los cambios en el estado Activo de un plan se registran en el Historial de cambios. |
