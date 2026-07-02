---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gestionar grupos Entra ID"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Gestionar usuarios y grupos de usuarios"
source_path: "admin/manage-entra-id-groups.html"
images:
  - "images/Picture14.png"
  - "images/Picture15.png"
  - "images/View-assignment-visibility-for-Entra-ID-Groups.png"
  - "images/manage-entra-id-groups-auto-sync1.png"
  - "images/manage-entra-id-groups-auto-sync2.png"
  - "images/manage-entra-id-groups_image1.png"
  - "images/manage-entra-id-groups_image2.png"
  - "images/manage-entra-id-groups_image3.png"
  - "images/manage-entra-id-groups_image4.png"
  - "images/manage-entra-id-groups_image5.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gestionar grupos Entra ID

## Visión general

La **integración de Entra ID Groups** permite a los administradores de Cloudability gestionar el acceso de los usuarios sincronizando la información de los grupos de usuarios directamente desde Microsoft Entra ID (anteriormente Azure Active Directory ). En lugar de crear y mantener manualmente grupos de usuarios en Cloudability, puede importar grupos de Entra ID existentes y asignarlos a Vistas para controlar el acceso.

Esta función agiliza la gestión de permisos alineando los controles de acceso de Cloudability con los grupos Entra ID de su organización. Cualquier actualización de la pertenencia a un grupo en Entra ID (por ejemplo, cuando los usuarios se unen o abandonan equipos) se refleja automáticamente en Cloudability durante la sincronización, lo que garantiza un acceso coherente y actualizado sin intervención manual.

Nota: Entra ID no tiene nada que ver con el inicio de sesión único (SSO).

## Procedimiento

**Requisitos previos**

Antes de empezar, asegúrate:

- Usted es administrador de Cloudability.
- Se han completado las credenciales de Microsoft Entra ID tenant. Para más información, visite [Connect Microsoft Entra ID](connect-microsoft-entra-ID.html)

## Importar grupos Entra ID a Cloudability

Los Grupos Entra ID no pueden crearse manualmente en Cloudability y deben ser importados o sincronizados desde su arrendatario Entra ID. Para importar:

1. Vaya a Configuración > Usuarios y grupos > pestaña Grupos de Entra ID.
2. Haga clic en el botón Sincronizar grupos Entra ID.

   ![sync entra id captura de pantalla](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image1.png)
3. En el cuadro de diálogo que aparece, introduzca los criterios (Ámbito y el filtro de texto en base al cual Cloudability importará los Grupos de ID de Entra) y haga clic en **Siguiente**.

   ![introducir criterios de sincronización captura de pantalla](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image2.png)
4. Haga clic en **Sincronizar ahora** para iniciar la importación.

   ![sync now captura de pantalla](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image3.png)

   Esta acción extrae todos los Grupos Entra ID del inquilino con credenciales que coincidan con los criterios especificados.

   Nota:
   - Los Grupos Entra ID son de sólo lectura : Estos grupos o sus usuarios no pueden ser modificados dentro de Cloudability.
   - Aunque puede eliminar un grupo Entra ID importado de Cloudability, no puede modificar el nombre del grupo o sus usuarios.
   - Criterios de importación : Puede utilizar diferentes criterios de sincronización para importar grupos de Entra ID en Cloudability
   - Duración de la sincronización : La sincronización puede tardar de unos segundos a unos minutos dependiendo del número de grupos y usuarios que se importen.
   - Comportamiento de sincronización :
     - Un grupo existente se sobrescribirá durante la sincronización. Cualquier adición o eliminación de usuarios de Entra ID se sincronizaría.
     - Si se ha eliminado un grupo en Entra ID, no se eliminará automáticamente de Cloudability. Debe eliminarlo manualmente.
     - Sólo se puede eliminar un grupo a la vez.
   - Justificación del comportamiento de sincronización :
     - Cloudability no puede distinguir si un grupo falta debido a un borrado en Entra ID o debido a un cambio en los criterios de sincronización.
     - Un grupo puede seguir asociado a asignaciones de Vista activas. La eliminación automática de un grupo de este tipo podría revocar involuntariamente el acceso de varios usuarios.
5. Haz clic en el icono del ojo de un grupo para consultar la lista de usuarios que pertenecen al grupo.

   ![icono del ojo captura de pantalla](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image4.png)

## Configurar la sincronización automática para los grupos de Entra ID

Los grupos de Entra ID cambian continuamente, lo que puede dificultar mantenerlos totalmente actualizados en Cloudability mediante la sincronización manual. Para eliminar este esfuerzo manual, Cloudability le permite configurar una programación de sincronización automática.

Puedes configurar una **sincronización automática diaria, semanal o mensual** utilizando criterios de filtro específicos. Los grupos de Entra ID se sincronizarán automáticamente según la programación configurada.

Para configurar la sincronización automática para los grupos de Entra ID:

1. Vaya a Configuración > Usuarios y Grupos > pestaña Grupos Entra ID.
2. Haga clic en el icono **del lápiz (Editar)** junto a Sincronización automática.

   ![](../../../../03-media/cloudability-premium/images/manage-entra-id-groups-auto-sync1.png)
3. Para activar la sincronización automática, activa la opción **Activar sincronización automática**.
4. En el modal **Configuración de sincronización automática** :
   1. Revise o actualice los criterios del filtro.
   2. Seleccione la frecuencia de sincronización ( **diaria**, **semanal** o **mensual** ).
   3. Elige la hora de sincronización y **la zona horaria**.![](../../../../03-media/cloudability-premium/images/manage-entra-id-groups-auto-sync2.png)
5. Haga clic en **Guardar** para habilitar la programación de sincronización automática.
6. Para desactivar la sincronización automática en cualquier momento, desactive la opción **«Habilitar sincronización automática»** y guarde los cambios.

## Borrar grupos Entra ID en Cloudability

Si se ha eliminado un grupo en Entra ID, **no** se eliminará automáticamente en Cloudability. Deberá eliminarlo manualmente.

Para eliminar un grupo Entra ID:

1. Vaya a Configuración > Usuarios y Grupos > pestaña Grupos Entra ID.
2. Busque el grupo que desea eliminar.
3. Haga clic en los tres puntos suspensivos (…) icono y selecciona la opción del menú «Eliminar».

Nota: No se puede eliminar un grupo si está asignado a alguna Vista. Aparece el siguiente error:

![borrar grupos entar id](../../../../03-media/cloudability-premium/images/manage-entra-id-groups_image5.png)

## Ver la visibilidad de las asignaciones para los grupos de Entra ID

Si se utilizó un grupo de ID de Entra en la asignación de vistas, el sistema bloqueó su eliminación. Los administradores pueden ver una **lista de solo lectura de todas las vistas** en las que se ha asignado un grupo. La lista muestra los nombres de las vistas e indica claramente cuándo un grupo no se utiliza en ninguna vista, lo que ayuda a optimizar la limpieza de grupos y reducir el esfuerzo manual.

Para identificar qué vistas están utilizando Entra ID Group.:

1. Vaya a Configuración > Usuarios y Grupos > pestaña Grupos Entra ID.
2. La columna Vistas muestra el número de vistas en las que se ha asignado este grupo de ID de Entra.
3. Busca el grupo que deseas validar.
4. Haga clic en los tres puntos suspensivos (…) icono y selecciona «Vistas» en el menú.
5. En el panel lateral, verás la lista de vistas a las que está asignado este grupo de ID de Entra.

![Ver asignado a un grupo de ID de Entra](../../../../03-media/cloudability-premium/images/View-assignment-visibility-for-Entra-ID-Groups.png)

## Asignar acceso de visualización a grupos Entra ID

Para asignar el acceso de la vista a un Grupo Entra ID o a múltiples Grupos Entra ID:

1. Vaya a Organizar > Vistas y cree o edite una Vista. Haga clic en Permisos > Seleccione " Usuarios y grupos " y el menú desplegable Compartido con. Asigne Vista a los grupos Entra ID importados desde el menú desplegable.

   ![asignación de vistas captura de pantalla](../../../../03-media/cloudability-premium/images/Picture14.png)

   Guarde esto para asignar la Vista a todos los usuarios dentro del Grupo(s) Entra ID.
2. Opcionalmente, añada una combinación de Grupos de Usuarios, Grupos Entra ID y Usuarios individuales a la Vista.

   ![editar vistas captura de pantalla](../../../../03-media/cloudability-premium/images/Picture15.png)
3. Si una vista se creó originalmente como **privada** o a nivel de **organización**, el administrador de la vista puede cambiarla a una vista compartida con usuarios y grupos seleccionando la opción **"Usuarios y Grupos"** y asignando los grupos de usuarios, grupos de usuarios y/o Entra ID.

**Tema principal:** [Gestión de usuarios y grupos de usuarios](../admin/manage-users-and-user-groups.html)
