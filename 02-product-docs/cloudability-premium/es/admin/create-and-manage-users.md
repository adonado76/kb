---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gestión de usuarios, vistas de usuario y cuadros de mando"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Gestionar usuarios y grupos de usuarios"
source_path: "admin/create-and-manage-users.html"
images:
  - "images/Manage-Users.png"
  - "images/Picture2.png"
  - "images/add_and_manage_users_4.png"
  - "images/pencil-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gestión de usuarios, vistas de usuario y cuadros de mando

## Visión general

Como administrador de Cloudability, puede gestionar el acceso de un usuario a las vistas y paneles de control de Cloudability. Esto incluye configurar su vista predeterminada, establecer un panel de control predeterminado y conceder acceso a vistas específicas. Otras tareas de gestión de usuarios, como añadir o eliminar funciones, se gestionan a través de **Access Administration**.

[Funciones y permisos en Cloudability](iam.html)

[Aprenda a gestionar los permisos y funciones de los usuarios en Access Administration](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)") .

## Gestión de vistas de usuario y cuadros de mando

1. Vaya a **Configuración** > **Usuarios y grupos > **Usuarios**** pestaña.
2. Seleccione la casilla situada junto al nombre del usuario que desea gestionar y, a continuación, seleccione ![icono de lápiz](../../../../03-media/cloudability-premium/images/pencil-icon.jpg) .
3. También puede buscar al usuario utilizando el nombre de usuario o el correo electrónico.
4. Para editar vistas y cuadros de mando de varios usuarios, seleccione al menos dos usuarios y, a continuación, **Editar varios**.

   ![captura de pantalla de usuarios](../../../../03-media/cloudability-premium/images/Manage-Users.png)
5. En el panel **Editar un usuario** que aparece, puede configurar las siguientes opciones para el usuario:
   - **Vista por defecto** - Establece la vista que el usuario ve por defecto al iniciar sesión
   - Cuadro de mandos **predeterminado** : especifica el cuadro de mandos predeterminado asignado al usuario
   - **Acceso a vistas** : concede al usuario acceso a vistas específicas. Puede filtrarlos según los criterios «Seleccionados», «No seleccionados» y «Todos».

     Nota: Las vistas jerárquicas solo se pueden asignar/desasignar a través de la página Permisos de vistas.

   ![editar captura de pantalla de usuario](../../../../03-media/cloudability-premium/images/add_and_manage_users_4.png)

   Nota:

   Cuando a los usuarios se les asigna una vista, no pueden ver ningún dato hasta que tengan el ViewsFeatureFullAccess permiso. Para obtener más información, visite [Gestión de permisos y roles de usuario.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)")
6. Seleccione Guardar.

## Establecer una vista predeterminada para un nuevo usuario

Cloudability permite configurar una **vista predeterminada** que los nuevos usuarios ven cuando se conectan por primera vez, siempre que se les haya concedido acceso a esa vista. Esta vista por defecto se denomina a menudo **vista por defecto a nivel orgánico**.

Si un administrador no ha establecido una vista predeterminada para un usuario, o si el usuario no ha configurado una en su perfil (*Gestionar perfil > Preferencias* ), Cloudability le asignará automáticamente esta vista predeterminada a nivel de organización al iniciar sesión.

Para configurar la vista por defecto, seleccione un valor en el desplegable **Vista por defecto del nuevo usuario**.

![nueva vista de usuario captura de pantalla](../../../../03-media/cloudability-premium/images/Picture2.png)

Nota: Los usuarios que acceden por primera vez sólo pueden acceder a esta vista. Tras el inicio de sesión inicial, se puede acceder a otras vistas o los administradores pueden conceder permisos adicionales.

**Tema principal:** [Gestión de usuarios y grupos de usuarios](../admin/manage-users-and-user-groups.html)
