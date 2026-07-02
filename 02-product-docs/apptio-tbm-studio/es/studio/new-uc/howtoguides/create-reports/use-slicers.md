---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Utiliza los segmentadores para el filtrado interactivo"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Conceptos básicos sobre los informes"
source_path: "studio/new-uc/howtoguides/create-reports/use-slicers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Utiliza los segmentadores para el filtrado interactivo

**Objetivo:** Añadir filtros a los informes para que los usuarios finales puedan filtrar los datos sin necesidad de modificar el informe

**Cuándo utilizarlo:** cuando se desea que los usuarios exploren los datos seleccionando diferentes categorías, periodos de tiempo o valores; cuando las distintas partes interesadas necesitan ver diferentes subconjuntos de los mismos datos

**Tiempo estimado:** 10 minutos

## Comprender los segmentadores

Los filtros interactivos son controles de filtrado que aparecen en el informe. Cuando un usuario hace clic en los valores de un filtro, todas las tablas y gráficos vinculados se actualizan al instante para mostrar únicamente los datos seleccionados. Esto convierte los informes estáticos en herramientas de análisis.

**Conceptos básicos sobre el cortador de llaves:**

- **Valores relacionados** (resaltados): al hacer clic en ellos, cambia lo que se muestra
- **Valores no relacionados** (en gris): no guardan relación con las selecciones actuales
- **Valores seleccionados** : Filtros activos actualmente

## Tipos de cortadoras

- **Filtros de lista:** mostrar los valores de texto como elementos en los que se puede hacer clic (lo más habitual)
- **Control deslizante:** muestra rangos numéricos con un control deslizante que se puede arrastrar
- **Cortadoras compactas:** combina varias cortadoras en un formato desplegable para ahorrar espacio
- **Filtros jerárquicos:** permiten profundizar en los distintos niveles (por ejemplo, Región > País > Ciudad)

## Pasos: Añadir un segmentador básico

1. Abre tu informe y **échale un vistazo**.
2. Haz clic en la pestaña **«Informe»** y, a continuación, haz clic en «**Filtro de filas** ». Aparece un marcador de posición de segmentador en blanco y se abre el panel «Configuración del segmentador».
3. En el **Explorador de proyectos**, busca el campo por el que quieres que los usuarios puedan filtrar. Algunos buenos candidatos para el filtro son: unidad de negocio, centro de datos, tipo de gasto, grupo de costes y proveedor.
4. Arrastra el campo al área **«Filtrar por»** del panel de configuración. El filtro se rellena con los valores de tus datos.
5. Coloca el filtro en el informe haciendo clic en su barra de título y arrastrándolo.
6. Cambia el tamaño del segmentador arrastrando sus bordes.

## Resultados previstos

- El filtro muestra valores en los que se puede hacer clic
- Al hacer clic en un valor, se filtran todas las tablas y gráficos del informe
- Se pueden seleccionar varios elementos pulsando Ctrl y haciendo clic
- El icono de restablecimiento (×) borra todas las selecciones

## Errores habituales

- **Demasiados valores:** los filtros muestran un máximo de 250 valores. Si tienes más datos, aplica un filtro al segmentador o utiliza un segmentador compacto con función de búsqueda.
- **Confusión por valores no relacionados:** los usuarios pueden preguntarse por qué algunos valores aparecen en gris. Considera la posibilidad de añadir una nota en la que se explique que los valores no relacionados no guardan relación con las selecciones actuales.
- **Rendimiento con muchos segmentadores:** los informes con muchos segmentadores pueden ralentizarse. Considera la posibilidad de utilizar segmentadores compactos para agrupar los filtros.

**Tema principal:** [Conceptos básicos sobre los informes](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
