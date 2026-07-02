---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Comportamiento del cálculo de la asignación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Asignaciones"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-calc-behaviour.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamiento del cálculo de la asignación

**Costes no asignados**

Cuando fallan las asignaciones basadas en criterios de coincidencia, los costes quedan sin asignar en el objeto de origen.

**Causas habituales de los costes no asignados**

- Los valores de las relaciones entre los datos no coinciden entre el origen y el destino
- La tabla de destino está vacía o le faltan las filas esperadas
- Ponderar las sumas de las columnas a cero
- Las condiciones del filtro excluyen todas las filas que coincidan

**Consejo:** Utiliza el panel de vista previa de la asignación para identificar las filas sin asignar antes de guardar los cambios.

**Comportamiento de ponderación negativa**

Por defecto, TBM Studio no realiza la asignación cuando los valores de ponderación incluyen valores negativos. Esto evita que se produzcan resultados inesperados en los cálculos.

**Soluciones alternativas para los valores negativos**

|  |  |
| --- | --- |
| **Enfoque** | **Descripción** |
| Asignación de fórmulas | Utiliza =SOURCE\*( {Table.Weight} /~ {Table.Weight} ) para aplicar una ponderación negativa de forma selectiva |
| Separar los valores | Separa los valores positivos y negativos en el código fuente; utiliza el valor absoluto para la ponderación |
| Corregir los datos de origen | Eliminar los valores negativos de la columna de ponderación en la fuente |

Consulte la sección «Problemas con la ponderación negativa» para obtener información detallada sobre la resolución de problemas

**Tema principal:** [Asignaciones](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
