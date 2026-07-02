---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Publicar la lista de proyectos en Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctese a Apptio Costing"
source_path: "it-planning/planning/pub-pl-ac.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publicar la lista de proyectos en Apptio Costing

Nota: Estas tareas requieren el rol de administrador con el permiso « DataOrchestrationServiceFeatureFullAccess » (Crear y administrar grupos de usuarios).

**Requisito previo:** ADM ( Data Management ) automatizado habilitado

La lista de proyectos a nivel de plan se puede publicar en Apptio Costing utilizando el método ADM ( Data Management ) automatizado, lo que garantiza que los datos del proyecto permanezcan alineados en todas las aplicaciones.

## Antes de empezar

Asegúrese de que se cumplan los siguientes requisitos previos:

- **El modelo de gestión automatizado ( Data Management, ADM)** se aprovisiona en su entorno
- ADM está habilitado en la planificación de Apptio :
- Ve a **Configuración (⚙) → Perfil de la empresa.**
- Selecciona **Habilitar integración automatizada de Data Management**
- **Los conjuntos de datos de integración de planificación** necesarios se instalan en Apptio Costing
- Tienes el rol de administrador con el permiso « **DataOrchestrationServiceFeatureFullAccess** ».

## Gestión de entidades

Asegúrese de que **la asignación automatizada de entidades ( Data Management ) → Entity Mapping** incluye las asignaciones correctas a los conjuntos de datos de costes de la asignación de entidades ( Apptio ).

1. Ve a **Configuración (⚙) → Automatizado Data Management**
2. Navega hasta **Gestión de entidades**.
3. Localice la entidad **«Lista de proyectos publicados»** en la tabla Entidad.
4. Asigne el **conjunto de datos de costes** Apptio correspondiente a la entidad.
5. Seleccione **Actualizar** para guardar los cambios.

Más información: [Gestión de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(se abre en una pestaña o una ventana nueva)")

## Publicar la lista de proyectos en Apptio Costing

Para publicar la lista de proyectos desde Plan a Cálculo de costes de Apptio :

1. Vaya a **Plan > Lista de proyectos**.
2. Selecciona el **menú desplegable (⋯)**.
3. Seleccione **Publicar en Cálculo de costes de Apptio**.
4. Seleccione el botón **Estado** para ver el estado del trabajo de publicación.

Para obtener más información sobre la gestión de proyectos, consulte [Gestionar proyectos](iip/project-list-document.html).

**Tema principal:** [Conectarse a Apptio Costing](../../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con el cálculo de costes de « Apptio » (ADM) mediante el método automatizado de « Data Management » (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable en todas las aplicaciones de Apptio.")
