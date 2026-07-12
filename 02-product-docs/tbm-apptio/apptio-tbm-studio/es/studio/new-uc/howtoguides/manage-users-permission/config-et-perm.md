---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar los permisos de las tablas editables"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Control de accesos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-et-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar los permisos de las tablas editables

|  |  |
| --- | --- |
| **Objetivo** | Controla qué usuarios o roles pueden editar, cargar o eliminar datos en las tablas editables |
| **Tiempo estimado** | Entre 15 y 20 minutos por tabla editable |
| **Requisitos previos** | Se ha creado una tabla editable; rol de administrador o usuario avanzado; se han configurado los usuarios y los roles |

## Cuándo utilizar este procedimiento

Utilice los permisos de tabla editable cuando sea necesario que distintos usuarios o roles tengan diferentes niveles de acceso de edición a las tablas de introducción de datos. Esto es especialmente importante en los casos de introducción de datos distribuida, en los que los responsables de centros de coste, los propietarios de aplicaciones u otras partes interesadas gestionan sus propias partes de los datos de mapeo o de referencia.

## Tipos de permisos para tablas editables

Las tablas editables admiten varios tipos de permisos:

|  |  |
| --- | --- |
| **Permiso** | **Qué controla** |
| Permiso para subir archivos | ¿Qué roles pueden cargar archivos de datos en la tabla editable? |
| Permiso para mostrar el historial | ¿Qué roles pueden ver el historial de cambios de la tabla? |
| Permiso para eliminar todas las filas | ¿Qué roles pueden eliminar todas las filas de la tabla editable (cuando está habilitada)? |

## Pasos

## Opción A: Configurar permisos básicos basados en roles

1. En el **Explorador de proyectos**, ve al informe que contiene la tabla editable.
2. Echa un vistazo al informe.
3. En la tabla editable que aparece en el informe, abre las **Propiedades avanzadas** de la tabla (clic con el botón derecho > Propiedades > Avanzadas).
4. Configure los siguientes permisos según sea necesario:
   - **Permiso de carga:** Selecciona los roles que pueden cargar datos
   - **Permiso para ver el historial:** Selecciona los roles que pueden ver el historial de cambios
   - **Permiso para eliminar todas las filas:** Selecciona los roles que pueden realizar eliminaciones masivas (si está habilitado)
5. Haz clic en **«Aplicar»** para guardar los cambios.
6. Consulta el informe.

## Opción B: Configurar el acceso avanzado de usuarios y tablas (componente de carga de tablas)

Para controlar con precisión qué usuarios pueden acceder a qué tablas a través del componente «Carga de tablas» en los informes:

1. Crea una tabla editable para definir las asignaciones de acceso con estas columnas:
   - **Tabla:** El nombre de la tabla editable
   - **Rol:** (Opcional) El rol que tiene acceso
   - **Usuario:** (Opcional) La dirección de correo electrónico específica del usuario que tiene acceso
2. Rellena la tabla de asignación de accesos. Por ejemplo:

   |  |  |  |
   | --- | --- | --- |
   | **Tabla** | **Rol** | **Usuario** |
   | Contratos Acme | Usuario avanzado |  |
   | Libro mayor de Acme |  | bob@acme.com |
   | Esquema de la estructura organizativa de Acme IT |  | roxanne@acme.com |
3. En tu informe, añade el componente «**Carga de tabla** ».
4. Haz clic en el botón **«Config»** del componente «Table Upload».
5. Cambia el **tipo de configuración** a «**Avanzado** ».
6. En el campo **«Tabla»**, introduce el nombre de tu tabla editable de asignación de accesos.
7. Haz clic en **«Aplicar»** y guarda el informe.

A partir de ahora, los usuarios solo verán las tablas a las que tienen acceso en el menú desplegable «Carga de tablas».

## Opción C: Aplicar seguridad a nivel de fila a las tablas editables

En los casos en los que los usuarios solo deben ver y editar sus propias filas dentro de una tabla editable (por ejemplo, los responsables de centros de coste que editan los datos de su propio centro de coste):

1. Configure las tablas de asignación de RLS tal y como se describe en la sección anterior («Implementación de la seguridad a nivel de fila»).
2. Habilita el control de acceso basado en roles (RLS) en la tabla editable añadiendo un paso de RLS en el proceso de transformación.
3. Cuando los usuarios accedan a la tabla editable a través de un informe, solo verán las filas que se ajusten a sus permisos de RLS.
4. Los usuarios solo pueden editar las celdas de las filas que pueden ver.

Importante: Cuando un usuario publica una tabla editable filtrada por RLS, las filas ocultas se conservan. La operación de publicación no elimina las filas que el usuario no puede ver.

## Resultados previstos

- Los usuarios solo ven las tablas editables a las que tienen permiso de acceso
- Las funciones de carga, historial y eliminación solo están disponibles para los roles autorizados
- Cuando RLS está habilitado, los usuarios solo pueden ver y editar las filas para las que tienen autorización
- La publicación conserva las filas ocultas por RLS

## Errores habituales

- **Conflictos de edición simultánea:** cuando el usuario A comienza a editar una celda, el usuario B no puede acceder a ella hasta que A guarde los cambios o cancele la edición. Planifica las ventanas de introducción de datos para los equipos distribuidos con el fin de minimizar los conflictos.
- **Errores de validación que impiden la publicación:** los datos no válidos (que no cumplen las reglas de validación) no se pueden publicar. Asegúrese de que los usuarios comprendan los requisitos de validación antes de introducir los datos.
- **Eliminación de filas en tablas enriquecidas:** los usuarios no pueden eliminar filas de las tablas enriquecidas editables, ya que estas se basan en la tabla de transformación de origen.

## Tareas relacionadas

- [Crear tablas editables](../work-with-data/create-blank-et.html)
- [Configurar reglas de validación para tablas editables](../work-with-data/config-dd-valid.html)
- [Configurar calendarios de publicación de tablas editables](../work-with-data/setup-et-publish.html)

**Tema principal:** [Control de acceso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
