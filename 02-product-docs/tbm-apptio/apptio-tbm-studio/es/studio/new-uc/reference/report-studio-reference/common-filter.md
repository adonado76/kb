---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Patrones de filtrado habituales"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/common-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Patrones de filtrado habituales

**Selector de periodo**

**Objetivo:** Permitir a los usuarios alternar entre las vistas mensual, trimestral y anual.

**Aplicación:**

1. Añadir un selector de columnas
2. Arrastra los valores basados en el tiempo desde la perspectiva «Tiempo»: « CurrentMonth, », « CurrentQuarter » (o «QTD»), «YTD»
3. Configurar como «Selección única» con «Selección obligatoria»
4. Añadir texto dinámico <%=CurrentDate( )%> a los encabezados de las columnas de la tabla

**Filtro jerárquico por regiones**

**Objetivo:** Filtrar por región → país → ciudad.

**Aplicación:**

1. Crear un grupo de perspectivas personalizado
2. Añadir y renombrar campos: 01\_Region, 02\_Country, 03\_City
3. Crear un filtro jerárquico utilizando el grupo
4. Si lo desea, utilice el formato de corte compacto para ahorrar espacio

**Filtro de umbral de coste**

**Objetivo:** Filtrar para mostrar únicamente los costes significativos que superen un mínimo.

**Aplicación:**

1. Añadir «Coste» (o la métrica correspondiente) como filtro
2. Configurar el rango del control deslizante
3. Establecer la posición predeterminada para excluir los valores pequeños
4. Guardar informe con los valores predeterminados

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
