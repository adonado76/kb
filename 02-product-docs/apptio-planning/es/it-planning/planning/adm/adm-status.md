---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Estado de la integración"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctese a Apptio Costing"
source_path: "it-planning/planning/adm/adm-status.html"
images:
  - "resources/images/it_planning_images/int-adm.png"
  - "resources/images/it_planning_images/int-plan.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Estado de la integración

La página Estado de integración proporciona visibilidad sobre el progreso de los intercambios de datos entre Apptio Planificación y Apptio Cálculo de costes mediante (ADM) Data Management automatizado. Esta vista ayuda a los administradores a supervisar las importaciones, las publicaciones y a resolver problemas de integración.

Nota: Estas tareas requieren el rol de administrador con el DataOrchestrationServiceFeatureFullAccess permiso.

Recuerde: La función automatizada Data Management (ADM) está habilitada

## Lo que puedes supervisar

La página Estado de Apptio integración de costes muestra el estado de las actividades ADM relacionadas con la planificación, incluyendo:

- Importación de datos de referencia desde Apptio Cálculo de costes
- Importaciones reales
- Importaciones del plan de referencia
- Los datos del plan se publican en Apptio Cálculo de costes
- Tareas de integración programadas y manuales
- Ejecuciones exitosas, en curso y fallidas

Cada registro incluye marcas de tiempo, estado de ejecución y detalles de errores (cuando corresponda).

## Dónde acceder al estado de integración

Puede ver el estado de la integración desde cualquiera de las siguientes ubicaciones:

**Desde Apptio Planificación**

1. Ve a **Configuración (⚙)**
2. Seleccionar **Integración Apptio de costes**
3. Abre la pestaña **Estado.**

Esta vista muestra únicamente las actividades de integración ADM Apptio relacionadas con la planificación.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-plan.png)

**De Automated Data Management (ADM)**

1. Ve a **Configuración (⚙)**
2. Seleccionar **automatizado Data Management**
3. Navegar a **Estado**

Esta vista muestra toda la actividad de integración de ADM en todas las aplicaciones. Más información: [Estado de ADM](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-status "(se abre en una pestaña o una ventana nueva)")

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-adm.png)

**Tema principal:** [Conectarse a Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.")
