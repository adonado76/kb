---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar notificaciones por correo electrónico"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
source_path: "it-planning/planning/manage-email-notifications.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar notificaciones por correo electrónico

Apptio envía automáticamente notificaciones por correo electrónico para eventos clave en el proceso de planificación. Estas notificaciones ayudan a informar a los usuarios sobre las acciones necesarias, los cambios de estado y las actualizaciones realizadas durante los flujos de trabajo de presentación y aprobación del presupuesto.

Los administradores pueden controlar si los usuarios deben recibir notificaciones por correo electrónico o no.

## Notificaciones por correo electrónico sobre cambios en el estado del plan

Las notificaciones por correo electrónico se envían en función del **rol** del usuario, **los permisos de edición** y **su posición en la cadena de aprobación**.

**Cuando se abre un plan**

Los usuarios con acceso de edición al plan ( **Nivel de edición: Propietario, Editar y enviar, Editar** ) reciben una notificación por correo electrónico.

**Cuando se presenta un plan**

- Los usuarios con acceso de edición al departamento enviado ( **nivel de edición: propietario, editar y enviar, editar** ) reciben un correo electrónico confirmando el envío.
- **Los aprobadores de nivel 1** reciben una notificación por correo electrónico solicitando la aprobación.

**Cuando un plan se aprueba parcialmente**

- Los usuarios con acceso de edición al departamento aprobado ( **nivel de edición: propietario, editar y enviar, editar** ) reciben un correo electrónico indicando que el plan ha sido aprobado por el nivel de aprobación actual.
- El **siguiente nivel de aprobación** en la cadena de aprobación recibe un correo electrónico solicitando la aprobación.
- Este proceso continúa a lo largo de todos los niveles de aprobación.

**Cuando un plan se aprueba por completo**

Los usuarios con acceso de edición al departamento aprobado ( **nivel de edición: propietario, editar y enviar, editar** ) reciben un correo electrónico confirmando la aprobación final.

**Cuando se devuelve un plan**

Los usuarios con acceso de edición al Departamento ( **Nivel de edición: Propietario, Editar y enviar, Editar** ) reciben una notificación por correo electrónico indicando que el plan ha sido devuelto.

**Cuando se desbloquea un plan**

Los usuarios con acceso de edición (nivel de edición: propietario, editar y enviar, y editar) para el departamento recibirán una notificación por correo electrónico indicando que su plan ha sido revocado o no enviado.

**Cuando se añade un comentario**

Los usuarios con acceso de edición al departamento relacionado reciben una notificación por correo electrónico.

Estos eventos garantizan que los usuarios estén informados cuando se requiera su revisión o acción. Consulte [Flujos de trabajo de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(se abre en una pestaña o una ventana nueva)") aprobación para obtener más detalles.

## Habilitar notificaciones por correo electrónico

Nota: *Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.*

1. Vaya a **Configuración (icono de engranaje) → Perfil de la empresa**.
2. Habilitar **las notificaciones por correo electrónico para los eventos del proceso de planificación.**
3. Seleccione **Guardar y salir**.
