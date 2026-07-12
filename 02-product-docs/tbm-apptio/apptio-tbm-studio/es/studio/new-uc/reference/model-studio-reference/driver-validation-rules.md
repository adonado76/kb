---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Reglas de validación de controladores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Conductores"
source_path: "studio/new-uc/reference/model-studio-reference/driver-validation-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Reglas de validación de controladores

**Comprobaciones de validación**

- La columna debe existir en la tabla subyacente
- El tipo de datos de las columnas debe ser numérico en el caso de las columnas de valores
- La sintaxis de la fórmula debe ser válida
- Las métricas a las que se hace referencia deben existir en el proyecto
- Las referencias entre proyectos deben apuntar a proyectos accesibles

**Problemas habituales con los controladores**

|  |  |  |
| --- | --- | --- |
| **Emitir** | **Causa** | **Resolución** |
| El conductor muestra 0 $ | La columna contiene datos no numéricos | Comprobar el tipo de columna en Data Studio |
| El conductor ha estado desaparecido durante un tiempo | No hay datos disponibles para ese periodo | Cargar los datos correspondientes a los periodos requeridos |
| Error de fórmula | Sintaxis incorrecta o referencia ausente | Comprueba la sintaxis y las referencias de la fórmula |
| Valores incorrectos | Se ha seleccionado una columna incorrecta | Comprueba que la columna contenga los datos esperados |

*→ Consulta [la sección de resolución de problemas con controladores para obtener soluciones detalladas](../../ts-support/bd-issues.html)*

*→ Consulte [la referencia de](../data-studio-reference.html) Data Studio para obtener información sobre la configuración de los tipos de datos*

**Tema principal:** [Conductores](../../../../studio/new-uc/reference/model-studio-reference/drivers.html)
