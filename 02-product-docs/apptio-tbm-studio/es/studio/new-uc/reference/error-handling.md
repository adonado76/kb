---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Manejo de errores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
source_path: "studio/new-uc/reference/error-handling.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Manejo de errores

## Tipos de errores habituales

**Errores en la fuente:**

|  |  |  |
| --- | --- | --- |
| **Error** | **Causa** | **Resolución** |
| Conversión a doble cuerda | Discrepancia de tipo en la referencia de columna | Cambiar el tipo de columna o utilizar una conversión explícita |
| Error al recuperar la tabla de referencia | Se ha eliminado la tabla de origen | Recrear la tabla de origen |

**Errores de importación:**

|  |  |  |
| --- | --- | --- |
| **Error** | **Causa** | **Resolución** |
| Se esperaba un tipo «Label», pero se encontró un tipo numérico | Todos los valores numéricos de la columna «Etiqueta» | Cambia el tipo de entrada a «Cualquiera» |
| La columna no existe | La validación detecta que falta una columna | Eliminar de la validación o añadir a la carga |
| Se ha añadido una columna | Columna inesperada en la carga | Añadir a la validación o eliminar de la carga |

**Errores en las fórmulas:**

|  |  |  |
| --- | --- | --- |
| **Error** | **Causa** | **Resolución** |
| No se encuentra la columna | Falta la columna a la que se hace referencia | Añadir una columna o corregir una fórmula |
| No se encuentra la tabla | Falta la tabla a la que se hace referencia | Actualizar la referencia de la fórmula |
| Búsqueda sin coincidencia | Discrepancia de tipos en las columnas de búsqueda | Alinear los tipos de columna o convertirlos |

**Errores en el proceso:**

|  |  |  |
| --- | --- | --- |
| **Error** | **Causa** | **Resolución** |
| Se ha detectado un ciclo | Referencia circular entre tablas | Eliminar un lado de la referencia circular |
| Se ha detectado una recursión | La tabla hace referencia a sí misma | Corregir la configuración autorreferencial |

**Tema principal:** [Referencia de « Data Studio »](../../../studio/new-uc/reference/data-studio-reference.html)
