---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comportamiento del filtro"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamiento del filtro

**Configuración de valores predeterminados**

Puedes establecer selecciones de filtro predeterminadas que se muestren cuando los usuarios abran un informe por primera vez:

1. Selecciona los valores que desees en el filtro
2. Guardar el informe

Cuando los usuarios abren el informe, los filtros muestran los valores predeterminados seleccionados. Los usuarios pueden modificar sus selecciones durante la sesión.

**Para las cortadoras Global Compact:**

- Los usuarios pueden guardar sus propios ajustes de filtro
- Los ajustes guardados se mantienen al cerrar y volver a iniciar sesión
- Los cambios realizados en un informe se aplican a todos los informes que utilicen el mismo filtro global compacto

**Estados del cortador y retroalimentación visual**

Los valores del Slicer se muestran en tres estados, indicados por colores:

|  |  |  |
| --- | --- | --- |
| **Estado** | **Descripción** | **Interacción con el usuario** |
| Seleccionada | Valores del filtro actualmente activos | Resaltado; haz clic para deseleccionar |
| Relacionado | Valores relacionados con la visualización de datos actuales | Apariencia normal; filtrará los datos si se selecciona |
| No relacionado | Valores no relacionados con los datos que se muestran actualmente | Aparece en gris; al seleccionarlo no ocurre nada |

**Comportamiento del estado:**

- Las selecciones realizadas en un filtro pueden modificar el estado de otros filtros (lo que hace que algunos valores dejen de estar relacionados)
- Valores combinados mediante la lógica OR dentro de un filtro
- Valores combinados mediante la lógica «AND» entre segmentadores

**Opciones de búsqueda**

Al añadir un filtro, configura cómo filtra los valores el cuadro de búsqueda automática:

|  |  |  |
| --- | --- | --- |
| **Opción** | **Comportamiento** | **Ejemplo: El usuario escribe «abc»** |
| Contiene | Busca valores que contengan el texto en cualquier parte | Coincide con: abcefg, defabc, defabcefg |
| Empieza por | Busca valores que empiecen por el texto | Coincide con: abcefg, abc (pero no con dabc ni 1abc ) |
| Búsqueda por grupos | Agrupa los valores por prefijo más un carácter (solo códigos jerárquicos) | Crea grupos: ABC1, ABC2, etc. |

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
