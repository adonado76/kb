---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Opciones de origen de la tabla"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
  - "Tablas"
source_path: "studio/new-uc/reference/table-source-option.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opciones de origen de la tabla

Al crear una tabla, debes seleccionar un tipo de origen que determine cómo se introducen los datos en la tabla.

**Carga de archivos**

**Descripción:** Importar datos desde archivos locales o de red

**Formatos compatibles:**

|  |  |  |
| --- | --- | --- |
| **Formato** | **Extensiones** | **Notas** |
| Excel | .xls,.xlsx | Solo un punto en el nombre del archivo |
| CSV | .csv | Valores separados por comas |
| Texto delimitado | .txt | Tabulación, barra vertical, tilde, dos puntos, punto y coma |
| XML | .xml | Datos estructurados |
| ZIP | .zip | Archivos comprimidos |

**Norma para nombrar archivos:** Los nombres de los archivos solo deben contener un punto (.) antes de la extensión.

- example\_data.xlsx - Correcto
- example.data.xlsx - Incorrecto (provoca un error de extensión de archivo no compatible)

**Pasos del proceso:** Fuente > Cargar > Importar > Tabla

**Tabla existente**

**Descripción:** Crear una nueva tabla a partir de los datos de otra tabla, manteniendo un vínculo

**Casos de uso:**

- Creación de subconjuntos filtrados de datos maestros
- Creación de tablas de informes especializadas
- Aplicación de transformaciones adicionales a los datos procesados

**Opciones:**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Datos de origen | Utiliza los datos sin procesar de la tabla de origen |
| Tabla de resultados | Utiliza los datos una vez aplicados todos los pasos de transformación |

**Tema principal:** [Tablas](../../../studio/new-uc/reference/tables.html)
