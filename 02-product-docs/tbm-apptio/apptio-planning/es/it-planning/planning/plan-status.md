---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Estado del plan"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
source_path: "it-planning/planning/plan-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Estado del plan

La página de **Estado del Plan** en Apptio Planning proporciona una vista centralizada para el seguimiento del progreso de los planes departamentales a lo largo del proceso de planificación y aprobación. Ayuda a los usuarios a supervisar la propiedad del plan, el estado actual y la actividad reciente en todos los departamentos de un ciclo del plan.

## Resumen de la situación del Plan

El plan de cada departamento pasa por un flujo de trabajo definido de cambios de estado a medida que avanza en el proceso de planificación y aprobación:

- **En curso** - Estado inicial en el que un departamento empieza a trabajar en su plan.
- **Presentado** - Indica que el plan ha sido presentado para su revisión y aprobación.
- **Aprobado** - El plan ha sido revisado y aprobado.
- **Devuelto** - El plan ha sido devuelto para revisiones o aportaciones adicionales.

La tabla de **estado** muestra los siguientes detalles clave para cada departamento:

- **Propietarios** - Los usuarios asignados como propietarios del plan del departamento.
- **Estado** - Estado actual del plan (En curso, Presentado, Aprobado o Devuelto).
- **Última acción** - La fecha y hora de la actualización de estado más reciente.
- **Acciones disponibles** - Acciones contextuales disponibles en función de los permisos del usuario (por ejemplo, Aprobar, Devolver, Comentar).

## Visualización y navegación por la tabla de estado

***Vistas jerárquicas y de lista***

- Para las **aprobaciones jerárquicas**, puede alternar entre una **Vista jerárquica** (para ver los departamentos en su estructura organizativa) y una **Vista de lista** (para una lista plana de todos los departamentos).
- Utilice el **selector de vistas** situado en la parte superior de la página para pasar de una vista a otra.

***Homologaciones multinivel***

- Para los **flujos de trabajo de aprobación multinivel**, la tabla sólo está disponible como **vista de lista**.
- Una columna adicional, **Nivel de aprobación**, muestra el progreso actual del proceso de aprobación - por ejemplo, *"1 de 3 aprobaciones".*
- A medida que se completa cada nivel, el estado pasará secuencialmente por los niveles ( *L1 Aprobado → L2 Aprobado → L3 Aprobado* ), y el plan se mostrará como **Aprobado** una vez que se hayan completado todas las aprobaciones requeridas.

## Aprobación y gestión de planes

Los usuarios con permisos de aprobación pueden gestionar los planes de los departamentos a los que están asignados:

- **Aprobar** - Marca el plan como aprobado para el nivel de aprobación actual.
- **Devolver** : devuelve el plan al propietario del departamento para que lo revise.
- **Comentario** - Permite a los aprobadores o revisores dejar comentarios sin cambiar el estado.

## Acciones masivas y exportación del historial

Puede realizar acciones en varios departamentos a la vez utilizando el **menú Acciones** de la parte superior de la página:

- **Enviar, aprobar** o **devolver de forma** masiva a varios departamentos simultáneamente.
- **Exportar historial** para descargar un registro detallado de todos los cambios de estado, incluidas las marcas de tiempo y los usuarios.

La exportación proporciona una pista de auditoría completa del progreso y las aprobaciones del plan con fines de información y cumplimiento.
