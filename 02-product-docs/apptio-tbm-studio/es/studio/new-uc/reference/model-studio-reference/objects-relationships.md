---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Relaciones y dependencias entre objetos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/objects-relationships.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Relaciones y dependencias entre objetos

Los objetos de modelo se conectan mediante asignaciones y controladores. Comprender estas relaciones es fundamental para elaborar modelos de costes precisos.

**Tipos de relaciones**

|  |  |  |
| --- | --- | --- |
| **Relación** | **Dirección** | **Descripción** |
| Controlador | En el objeto | El controlador de unidad introduce el valor de una columna en el objeto modelo |
| Asignación (salida) | Fuera de lugar | Envía el valor de este objeto a los objetos de destino |
| Asignación (entrante) | En el objeto | Recibe valores de los objetos de origen |

**Reglas de dependencia**

- El gráfico del modelo no debe contener ciclos (no debe haber asignaciones circulares)
- Todos los objetos del modelo deben contener datos válidos para el periodo de tiempo activo
- Las tablas de origen y destino deben estar desprotegidas antes de crear asignaciones
- Las asignaciones se ejecutan en un orden determinista basado en el grafo de objetos
- Los errores de transformación bloquean los cálculos del modelo para los objetos afectados

*→ Consulte [el orden de ejecución del modelo para obtener más detalles sobre la secuencia de cálculo](../../concepts-architecture/model-architecture/model-object-relationship.html)*

*→ Consulte [«Errores de asignación circular» para obtener información sobre la resolución de problemas](../../ts-support/rs-issues.html)*

**Tema principal:** [Objetos modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
