---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Resolución de problemas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resolución de problemas

**El segmentador no muestra ningún valor**

**Posibles causas:**

- El campo no es compatible con los datos actuales
- Todos los valores excluidos por los filtros a nivel de componente
- !ALL\_ROWS desactivado y no hay datos en el periodo actual
- Campo desde una perspectiva incompatible

**Solución:** Comprueba el origen del campo en la vista en perspectiva, revisa los filtros a nivel de componente, prueba con diferentes intervalos de tiempo y comprueba!Configuración del proyecto ALL\_ROWS.

**La selección del cortador no tiene ningún efecto**

**Posibles causas:**

- Selección de valores no relacionados (en gris)
- El «Slicer» está dentro del cuadro de grupo, pero los componentes están fuera
- El «Slicer» se encuentra en una pestaña distinta a la de los componentes de destino
- Tabla/gráfico heredado no compatible con los segmentadores

**Solución:** Comprueba el ámbito del filtro (a nivel de grupo o de informe), verifica que los componentes utilicen el formato de consulta ad hoc, asegúrate de que el filtro y los componentes se encuentren en la misma pestaña y comprueba si hay filtros conflictivos en otros filtros.

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
