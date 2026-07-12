---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guardar configuración"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/save-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guardar configuración

Las tablas editables utilizan un proceso de guardado en dos fases: guardado local (que conserva los cambios en la tabla editable) y publicación (que actualiza la tabla de transformación asociada).

**Guardar proceso**

Cuando los usuarios realizan cambios:

1. Los cambios se registran en el navegador hasta que se guarden explícitamente
2. Haz clic en «Guardar» en la parte inferior de la tabla para guardar los cambios
3. Los cambios guardados actualizan la tabla editable, pero aún no la cadena de transformación
4. La opción «Mostrar cambios» muestra todas las modificaciones pendientes

**Proceso de publicación**

Para transferir los datos guardados al proceso de transformación:

1. Haz clic en «Publicar» en la parte inferior de la tabla
2. Confirma la acción de publicación en el cuadro de diálogo de advertencia
3. Introduce una descripción y haz clic en «Registrar»
4. La tabla de transformación asociada se actualiza con los nuevos datos

La publicación siempre sobrescribe todo el conjunto de datos de la tabla editable en la tabla de transformación asociada.

**Requisitos previos:** *La publicación manual requiere acceso de desarrollador y acceso a Stage, pero no requiere acceso a TBM Studio ni acceso de administrador.*

**Gestión de errores al guardar**

Cuando falla el guardado o la publicación:

- **Errores de validación:** los datos no válidos impiden la publicación; corrige los errores e inténtalo de nuevo
- **Errores de conexión:** Vuelve a intentar la operación; los cambios se mantienen en el estado local
- **Conflictos de edición simultánea:** consulta la sección «Control de concurrencia» más abajo

**Control de concurrencia**

Las tablas editables aplican un bloqueo a nivel de celda para evitar conflictos:

- Cuando un usuario empieza a editar una celda, esta se bloquea para los demás usuarios
- El bloqueo se mantiene hasta que el usuario guarde o cancele los cambios
- Otros usuarios pueden editar simultáneamente diferentes celdas de la misma fila
- Si todas las celdas de las filas filtradas están bloqueadas, las opciones «Añadir fila», «Eliminar fila» y «Duplicar fila» están desactivadas

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
