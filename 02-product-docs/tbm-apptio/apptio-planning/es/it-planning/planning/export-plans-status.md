---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Exportar el historial de un plan"
breadcrumb: []
source_path: "it-planning/planning/export-plans-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Exportar el historial de un plan

## Acerca de esta tarea

Apptio Planning las aplicaciones mantienen un registro de las medidas adoptadas en cada plan. Los administradores y propietarios de procesos presupuestarios pueden ver el historial completo de la actividad de presentación, aprobación y devolución de servicios, departamentos y proyectos individuales, y los administradores pueden exportar esta información. Esta información puede ayudar a responder a las preguntas "quién, qué y cuándo" sobre las acciones de estado de un plan.

## Procedimiento

- **Para exportar todo el historial de versiones de objetos de coste:**

  1. En los menús de Plan en la parte superior derecha, seleccione un Plan, una categoría de Objeto de costo y un objeto de costo o grupo de objetos de costo.

     [Más información sobre la navegación en Planificación](navigate-apptio-planning.html#Toolbar)
  2. Vaya a Planning>Estado. Aparecerá la página Estado del plan.
  3. Seleccione Acciones > Exportar historial. La aplicación de planificación genera un historial de versiones para todos los objetos de coste en formato `.csv` .
- **Los detalles exportados incluyen lo siguiente:**

  - Código objeto de coste.
  - Nombre del objeto de coste.
  - Versión : Versión del Objeto de Coste en la que se ha realizado una acción.
  - Acción : la acción que se ha realizado.
  - Usuario : Nombre del usuario que ha realizado la acción.
  - Fecha/Hora : Cuándo se realizó cada acción. El valor de la hora está en formato GMT/UTC, a menos que se indique lo contrario.
  - Comentario de devolución : El comentario, si lo hay, que se envió con la acción Devolver.

  Nota: Los planes que se encuentren en estado Nuevo o recién abiertos (es decir, que aún no se haya realizado ninguna acción) darán como resultado un.csv en blanco con sólo la fila de cabecera.
