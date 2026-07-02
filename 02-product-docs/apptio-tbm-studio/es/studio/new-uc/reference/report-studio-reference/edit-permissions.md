---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos de edición"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/edit-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos de edición

Los permisos determinan quién puede realizar operaciones específicas en el componente de tabla editable.

**Permisos a nivel de fila**

Configure los permisos de operación en la sección «Permisos» de la cinta de opciones «Tablas editables»:

|  |  |  |
| --- | --- | --- |
| **Permiso** | **Controles** | **Valor predeterminado** |
| Permiso para añadir filas | ¿Quién puede añadir nuevas filas? | Todo el mundo |
| Permiso para editar fila | ¿Quién puede modificar las filas existentes? | Todo el mundo |
| Permiso para eliminar filas | ¿Quién puede eliminar filas concretas? | Todo el mundo |
| Permiso para duplicar filas | ¿Quién puede duplicar filas? | Todo el mundo |
| Permiso para publicar filas | ¿Quién puede publicar cambios? | Todo el mundo |
| Permiso para eliminar todas las filas | ¿Quién puede eliminar todas las filas de una sola vez? | Administrador y socio |
| Permiso de descarga | ¿Quién puede descargar la tabla? | Todo el mundo |
| Permiso para subir archivos | ¿Quién puede subir datos? | Todo el mundo |
| Permiso para mostrar el historial | ¿Quién puede ver el historial de cambios? | Todo el mundo |

Para cada permiso, seleccione «Todos» o «Roles seleccionados» y especifique los roles permitidos.

**Integración de la seguridad a nivel de fila (RLS)**

Cuando RLS está habilitado en la tabla editable subyacente:

- Los usuarios solo ven las filas que coinciden con su dimensión de seguridad (por ejemplo, su centro de coste)
- El acceso de escritura está restringido únicamente a las filas visibles
- Las filas ocultas se conservan durante las operaciones de publicación
- RLS se aplica además de los permisos a nivel de informe

**Desactivación de la edición dinámica**

Utiliza el campo «Desactivar ediciones» para desactivar la edición de forma condicional en función de condiciones dinámicas:

Ejemplo: `{$CurrentUser:Users.ID}=ddavis@ABCCompany.com`

Esta expresión desactiva la edición para el usuario especificado. Puedes utilizar cualquier expresión de texto dinámico cuyo resultado sea verdadero o falso.

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
