---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Filtros jerárquicos y en cascada"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/h-c-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtros jerárquicos y en cascada

**Creación de un filtro jerárquico**

Los filtros jerárquicos permiten aplicar filtros de desglose a través de varios niveles de clasificación.

**Requisitos previos:**

- Perspectiva personalizada con campos agrupados
- Campos ordenados para representar los niveles jerárquicos

**Pasos:**

1. Crea un grupo de perspectivas personalizado que contenga los campos jerárquicos
2. Ordena los campos utilizando prefijos secuenciales (por ejemplo, 01\_Type, 02\_SubType, 03\_OS )
3. En la pestaña Informe, haz clic en «Filtro de filas»
4. Arrastra el grupo de perspectivas (no los campos individuales) al área «Cortar por»

**Nota:** No se pueden utilizar guiones (-) en los nombres de los campos. Utiliza dos puntos (:) o guiones bajos (\_) en su lugar.

**Búsqueda por código jerárquico**

Para los campos que representan códigos jerárquicos (por ejemplo, códigos de cuenta, identificadores de centros de coste), active el comportamiento de agrupación especial:

1. Haz clic con el botón derecho del ratón en el campo de la perspectiva personalizada
2. Selecciona «Editar [nombre del campo]»
3. La casilla indica un código jerárquico

**Comportamiento:** Cuando un usuario introduce texto en el campo de búsqueda del segmentador, el sistema busca todos los valores que comienzan por ese texto más un carácter adicional, crea una entrada de grupo para cada combinación única y, al seleccionar un filtro de grupo, muestra todos los valores que coinciden.

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
