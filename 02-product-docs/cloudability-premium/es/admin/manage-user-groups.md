---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gestionar grupos de usuarios"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Gestionar usuarios y grupos de usuarios"
source_path: "admin/manage-user-groups.html"
images:
  - "images/Picture3.png"
  - "images/Picture4.png"
  - "images/Picture5.png"
  - "images/Picture6.png"
  - "images/Picture7.png"
  - "images/Picture8.png"
  - "images/View-assignment-visibility-for-User-Groups.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gestionar grupos de usuarios

## Visión general

Un **grupo de usuarios** en « Cloudability » es un conjunto lógico de usuarios creado para simplificar la gestión del acceso y agilizar la asignación de vistas.

Al organizar a los usuarios en grupos, los administradores pueden aplicar más fácilmente configuraciones uniformes, controlar el acceso a las vistas y garantizar el cumplimiento normativo en toda su práctica de FinOps.

## Procedimiento

**Requisitos previos**

Antes de empezar, asegúrate de que:

- Eres administrador de « Cloudability ».

## Crear un grupo de usuarios en Cloudability

Para crear un grupo de usuarios:

1. Ve a Configuración > Usuarios y grupos > pestaña «Grupos de usuarios ».

   ![Captura de pantalla de los grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture3.png)
2. Para crear un nuevo grupo de usuarios, haz clic en «Nuevo grupo de usuarios ». Puedes crear varios grupos de usuarios a la vez separando los nombres con comas.

   ![Añadir grupos de usuarios (captura de pantalla)](../../../../03-media/cloudability-premium/images/Picture4.png)
3. Haz clic en «Editar usuarios» y añade usuarios al grupo de usuarios a partir de la lista de usuarios.

   ![Editar grupos de usuarios (captura de pantalla)](../../../../03-media/cloudability-premium/images/Picture5.png)
4. Pulse Guardar.

## Eliminar un grupo de usuarios en Cloudability

Para eliminar un grupo de usuarios:

1. Ve a Configuración > Usuarios y grupos > pestaña «Grupos de usuarios ».
2. Busca el grupo que quieras eliminar.
3. Haz clic en los tres puntos (…) icono y selecciona la opción de menú «Eliminar».

Nota: No se permite eliminar un grupo si está asignado actualmente a alguna vista. Aparece el siguiente error:

![Captura de pantalla del error del usuario «gropus»](../../../../03-media/cloudability-premium/images/Picture6.png)

## Ver la visibilidad de las tareas para los grupos de usuarios

Si se había utilizado un grupo de usuarios en la asignación de vistas, el sistema bloqueaba su eliminación. Los administradores pueden ver una **lista de solo lectura de todas las vistas** a las que se ha asignado un grupo. La lista muestra los nombres de las vistas e indica claramente cuándo un grupo no se utiliza en ninguna vista, lo que ayuda a agilizar la limpieza de grupos y a reducir el trabajo manual.

Para identificar qué vistas utilizan el usuario Group.:

1. Ve a Configuración > Usuarios y grupos > pestaña «Grupos de usuarios ».
2. La columna «Vistas» muestra el número de vistas a las que está asignado este grupo de usuarios.
3. Busca el grupo que quieras validar.
4. Haz clic en los tres puntos (…) haga clic en el icono y seleccione «Mostrar vistas» en el menú.
5. En el panel lateral, verás la lista de vistas a las que está asignado este grupo de usuarios.

![Vista asignada a un grupo de usuarios](../../../../03-media/cloudability-premium/images/View-assignment-visibility-for-User-Groups.png)

## Asignar acceso a vistas a grupos de usuarios

Para asignar el acceso a una vista a un grupo de usuarios o a varios grupos de usuarios:

1. Ve a «Organizar» > «Vistas» y crea o edita una vista. Selecciona la opción «Usuarios y grupos» y un valor del menú desplegable «Compartido con ».

   Asigna la vista a uno o varios grupos del menú desplegable (en la categoría «Grupos de usuarios»).

   ![Captura de pantalla de la vista de grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture7.png)

   Haz clic en «Guardar» para asignar la vista a todos los usuarios de los grupos de usuarios.
2. Si lo deseas, puedes añadir a la vista una combinación de grupos de usuarios, grupos de Entra ID y usuarios individuales.

   ![grupos de usuarios entra id captura de pantalla](../../../../03-media/cloudability-premium/images/Picture8.png)
3. Si una vista se creó inicialmente como vista **privada** o a nivel **de organización**, el administrador de vistas puede cambiarla a una vista compartida con «Usuarios y **grupos»** seleccionando la opción «Usuarios y grupos» y asignando los usuarios, los grupos de usuarios y/o los grupos de Entra ID.

**Tema principal:** [Gestionar usuarios y grupos de usuarios](../admin/manage-users-and-user-groups.html)
