---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad a nivel de fila en los informes"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/rls-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad a nivel de fila en los informes

**Cómo aplica RLS a los datos de los informes**

La seguridad a nivel de fila filtra los datos que se muestran en los componentes del informe en función de la identidad del usuario actual. Cuando se configura el RLS:

1. El sistema identifica al usuario actual
2. Busca al usuario en las tablas de asignación de RLS
3. Solo se muestran las filas que coinciden con los permisos del usuario
4. Los cálculos agregados solo reflejan los datos visibles

**Pasos para la configuración de RLS:**

1. **Crea tablas de correspondencia** en el proyecto de seguridad a nivel de fila que definan qué elementos puede ver cada usuario
2. **Añade pasos** al proceso de RLS para transformar las tablas que deben filtrarse
3. **Configura reglas de filtro** que hagan coincidir las columnas de la tabla con los valores de la tabla de correspondencias

**Interacción entre RLS y los permisos de los informes**

Los permisos de RLS y de informes son independientes, pero complementarios:

|  |  |  |  |
| --- | --- | --- | --- |
| **Situación** | **Permiso para informar** | **Acceso a RLS** | **Experiencia del usuario** |
| **A** | ✓ Concedido | ✓ Todos los datos | Informe completo, todos los datos |
| **P** | ✓ Concedido | ✓ Filtrado | Informe completo, datos filtrados |
| **C** | ✓ Concedido | ✗ No hay datos | Componentes vacíos del informe |
| **S** | ✗ Denegado | — | No se puede acceder al informe |

**Situación habitual:** un usuario tiene acceso a los informes, pero no ve ningún dato. Esto suele indicar que:

- El RLS está configurado en las tablas subyacentes
- El ID del usuario no figura en las tablas de asignación de RLS
- Es necesario añadir al usuario a la lista de acceso RLS correspondiente

**Depuración de RLS**

**Síntoma: El usuario no ve ningún dato en los informes**

Comprueba estos elementos en este orden:

1. **Tablas de asignación de RLS:** Comprueba que el ID del usuario figure en las tablas de asignación correspondientes del proyecto de seguridad a nivel de fila
2. **Formato del ID de usuario:** Asegúrate de que el ID de usuario de las tablas de correspondencia coincida exactamente con el nombre de usuario (se distingue entre mayúsculas y minúsculas)
3. **Pasos del proceso RLS:** Comprueba que los pasos de RLS estén configurados en las tablas que alimentan el informe
4. **Coincidencia de columnas:** comprueba que la columna de filtro de la tabla coincida con los valores de la tabla de asignación

Importante: Las tablas no heredan automáticamente la configuración de RLS. Debes añadir un paso RLS por cada paso del modelo que debas filtrar.

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
