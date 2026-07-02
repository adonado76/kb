---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear y gestionar usuarios"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Gestión de usuarios"
source_path: "studio/new-uc/howtoguides/manage-users-permission/create-manage-users.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear y gestionar usuarios

**Objetivo:** Crear nuevas cuentas de usuario y gestionar los usuarios existentes en TBM Studio.

**Cuándo utilizarlo:** al incorporar a nuevos miembros del equipo, actualizar la información de los usuarios o gestionar el ciclo de vida de los usuarios (activar o desactivar cuentas).

**Tiempo estimado:** entre 5 y 10 minutos por usuario

**Requisitos previos**

- Debes tener el rol de administrador o un rol personalizado con permisos de gestión de usuarios.
- Acceso a la administración de acceso mejorado (Frontdoor).
- La dirección de correo electrónico del usuario (que se utiliza como nombre de usuario), su nombre completo y la función que desempeñará.

## Pasos para crear un nuevo usuario

1. **Acceda a la administración de acceso mejorado.** En TBM Studio, haz clic en la pestaña **«Proyecto»** y selecciona «**Controlar el acceso a las aplicaciones de Apptio** ». Esto abre la interfaz de administración de acceso mejorado.
2. **Ve a «Usuarios».** En la Administración de acceso ampliado, busca la sección **«Usuarios»** en el menú de navegación.
3. **Haz clic en «Añadir usuario»** (o en la opción equivalente) para crear una nueva cuenta de usuario.
4. **Introduce los datos del usuario:**
   - **Correo electrónico:** la dirección de correo electrónico del usuario. Este será su nombre de usuario para iniciar sesión.
   - **Nombre completo:** El nombre y los apellidos del usuario tal y como aparecen en el sistema.
   - **Contraseña:** Establece una contraseña inicial (el usuario podrá cambiarla más adelante) o configura el inicio de sesión único (SSO).
5. **Asignar el/los rol(es) inicial(es).** Seleccione la(s) función(es) adecuada(s) de la lista de funciones disponibles. Consulte *la sección «Asignar roles a los usuarios»* más abajo para obtener instrucciones detalladas.
6. **Guarda el usuario.** Haz clic en **«Guardar»** o **«Crear»** para finalizar la creación del usuario.

## Resultados previstos

El nuevo usuario aparece en la lista de usuarios. Ahora el usuario puede iniciar sesión con su dirección de correo electrónico y contraseña. Su nivel de acceso viene determinado por los roles que se les hayan asignado.

## Gestión de usuarios existentes

Puede modificar las cuentas de usuario en cualquier momento a través de la Administración de acceso avanzada:

- **Editar propiedades de usuario:** Actualiza el nombre, el correo electrónico u otra información del perfil.
- **Modificar la asignación de funciones:** añadir o eliminar funciones a medida que cambian las responsabilidades.
- **Restablecer contraseñas:** restablece la contraseña de un usuario si no puede acceder a su cuenta.
- **Desactivar cuentas:** Desactive las cuentas de usuario cuando los empleados dejen la empresa o ya no necesiten acceso.

Advertencia: La desactivación de un usuario no elimina sus datos históricos ni su registro de auditoría. Si necesita eliminar por completo a un usuario por motivos de cumplimiento normativo, póngase en contacto con el servicio de asistencia de Apptio.

## Errores habituales

- **Formato del correo electrónico:** Asegúrate de que las direcciones de correo electrónico tengan el formato correcto. Los usuarios no pueden iniciar sesión si introducen una dirección de correo electrónico incorrecta.
- **Discrepancia de dominio:** los usuarios deben crearse en el dominio correcto para poder acceder a los proyectos correspondientes.
- **Falta la asignación de roles:** los usuarios a los que no se les haya asignado ningún rol no pueden acceder a TBM Studio. Asigna siempre al menos un rol.

**Tema principal:** [Gestión de usuarios](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
