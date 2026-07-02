---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Organizar vistas mediante vistas jerárquicas"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Crear y gestionar vistas"
source_path: "admin/hierarchical-views.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organizar vistas mediante vistas jerárquicas

## Visión general

¿Qué son las vistas jerárquicas?

Las vistas jerárquicas (HV) organizan las vistas en una estructura de tipo «padre-hijo». En esta jerarquía, una vista puede contener otras vistas —denominadas vistas secundarias— que, a su vez, pueden tener otras vistas secundarias, formando así una estructura anidada.

Una vista que contiene vistas secundarias se denomina «grupo de vistas». La condición de su filtro se hereda automáticamente de sus elementos hijos, lo que representa la unión de todas sus instrucciones de filtro. Esto significa que puedes gestionar la lógica de un grupo de vistas simplemente añadiendo o eliminando vistas secundarias, sin necesidad de editar manualmente los criterios de filtrado.

**Ejemplo:**

- `Marketing` Ver → Filtrar: Etiqueta = «Marketing»
- `Engineering` Ver → Filtrar: Etiqueta = «Ingeniería»
- `All Departments` (padre) → El filtro se establece automáticamente en «Marketing O Ingeniería».

| Nivel | Nombre de ejemplo | Filtro |
| --- | --- | --- |
| Ver grupo | `All Departments` | (hereda todo lo que viene a continuación) |
| Vista secundaria 1 | `Marketing` | Etiqueta = «Marketing» |
| Vista secundaria 2 | `Engineering` | Etiqueta = «Ingeniería» |

Ventajas de las vistas jerárquicas

1. Filtrado simplificado: los filtros secundarios se aplican automáticamente a las vistas principales, lo que elimina la necesidad de gestionar filtros duplicados.
2. Optimiza la gestión del acceso de los usuarios: al asignar un usuario a una vista principal (grupo de vistas), se le concede automáticamente acceso a todas sus vistas secundarias, así como a cualquier vista descendiente que se encuentre más abajo en la jerarquía.
3. Claridad organizativa: visualiza tu gasto en la nube en una estructura que refleje la organización real de tu empresa.
4. Creación y sincronización automáticas con la asignación jerárquica de negocios (HBM): las vistas jerárquicas se generan automáticamente a partir de una asignación jerárquica de negocios (HBM), lo que ahorra tiempo y reduce la configuración manual. Cada valor del archivo de asignación se convierte en una vista, y el archivo define cómo se agrupan las vistas en grupos de vistas. Una vez creada, la estructura HV se mantiene sincronizada y se actualiza automáticamente cada vez que cambia el HBM.

## Configuración de vistas jerárquicas

Crear una vista jerárquica

1. Ve a «Organizar» > «Vistas».
2. Selecciona «Nueva vista jerárquica ». Se abre el cuadro de diálogo «Nueva vista jerárquica ».
3. Selecciona una asignación jerárquica de negocio que se vaya a utilizar para definir las vistas de la jerarquía.
4. Haz clic en «Añadir» para crear la jerarquía de vistas.

Nota:

Esto creará automáticamente vistas que se ajusten a la definición de HBM. Esto puede tardar unos minutos en completarse.

Gestionar vistas jerárquicas

Puedes editar y compartir vistas dentro de la jerarquía, o eliminar toda la jerarquía.

Nota:

No es posible modificar las condiciones de filtrado de las vistas dentro de una vista jerárquica (HV), ni eliminar vistas individuales. Tanto las vistas como sus condiciones de filtrado se controlan mediante la asignación jerárquica de negocios (HBM) asociada al HV.

Modificar los permisos de privacidad de toda la vista jerárquica

Los autores de vistas pueden modificar los permisos (aumentarlos o reducirlos) de la jerarquía de vistas. A continuación te explicamos cómo hacerlo:

1. Ve a «Organizar» > «Vistas».
2. Haz clic en los tres puntos (…) Haga clic en el icono situado en la fila del nodo raíz HV y seleccione «Editar ».

   Se muestra el panel «Editar grupo de vista jerárquica ».
3. Cambia el permiso entre «Toda la organización» y «Usuarios y grupos».

   Nota:

   Al cambiar el modo de privacidad a «Toda la organización» y guardar los cambios, se eliminarán todas las asignaciones de uso compartido de los usuarios existentes para todos los nodos de la jerarquía. Actúa con precaución.

Edición de una vista jerárquica

Los usuarios con acceso de visualización pueden modificar la configuración de uso compartido de una vista jerárquica. Sigue los pasos que se indican a continuación:

1. Ve a «Organizar» > «Vistas».
2. Haz clic en los tres puntos (…) Haga clic en el icono de la fila de la vista que desee editar y seleccione «Editar ».

   Se muestra el panel «Editar grupo de vista jerárquica ».
3. Selecciona «Usuarios y grupos » para compartir tu vista con usuarios concretos. Utiliza el menú desplegable «Compartido con» para seleccionar usuarios, grupos de usuarios o grupos de ID de Entrap específicos con los que compartir la vista.

   Nota:

   Cuando se asigna una vista a los usuarios, estos también heredan automáticamente el acceso a todas las vistas secundarias. En la sección «Permisos de vista heredados» puedes ver los usuarios que han heredado el acceso a la vista actual.

   Una vez asignados, los usuarios no pueden ver ningún dato hasta que dispongan del permiso « ViewsFeatureFullAccess ». Para obtener más información, consulta [«Gestión de permisos y roles de usuario»](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)") =

Cómo eliminar una vista jerárquica

Para eliminar una vista jerárquica, sigue los pasos que se indican a continuación:

1. Ve a «Organizar» > «Vistas».
2. Haz clic en los tres puntos situados junto al nodo raíz y selecciona «Eliminar».
3. Confirma que deseas eliminar el grupo de vistas importado.

   Nota:

   No es posible eliminar vistas individuales dentro de una vista jerárquica (HV); solo se puede eliminar el nodo raíz, y únicamente un usuario que tenga acceso a dicho nodo raíz puede hacerlo.

   Sin embargo, el nodo raíz no se puede eliminar si alguna de sus vistas secundarias está compartida con otros usuarios. Para proceder a la eliminación, primero debes retirar todo el acceso de los usuarios a todo el HV.

   Para eliminar todo el acceso compartido:

   - Edita el nodo raíz y configura su modo de uso compartido en «Toda la organización»; a continuación, haz clic en «Guardar».
   - Vuelve a editar el nodo raíz y cambia el modo de uso compartido de nuevo a «Usuarios y grupos»; a continuación, vuelve a guardar.

   Este proceso debería eliminar todos los accesos de usuario existentes, lo que te permitirá eliminar el nodo raíz.

**Tema principal:** [Crear y gestionar vistas](../admin/create-and-manage-views.html)
