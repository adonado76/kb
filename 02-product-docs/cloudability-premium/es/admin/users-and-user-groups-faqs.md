---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Preguntas frecuentes sobre usuarios y grupos de usuarios"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Gestionar usuarios y grupos de usuarios"
source_path: "admin/users-and-user-groups-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preguntas frecuentes sobre usuarios y grupos de usuarios

## ¿Son Entra ID e IDP sinónimos?

Entra ID es uno de los proveedores de identidad más utilizados. Hay muchos otros PDI como Okta, PingIdentify. Por el momento, sólo admitimos Microsoft Entra ID (también conocido como Azure AD).

## ¿Qué función de Cloudability puede acceder a las funciones?

La función es accesible con el permiso existente " UserManagementFeatureFullAccess". Así, si un usuario ya tenía acceso a la función "Gestión de usuarios", también tendrá acceso a las funciones Grupos de usuarios y Grupos Entra ID.

## ¿Cuántos Grupos de Usuarios o Grupos Entra ID pueden crearse en Cloudability?

No hay límite en el número de Grupos de Usuarios o Grupos Entra ID que pueden crearse.

## ¿Hay algún límite para la longitud del nombre de un grupo de usuarios?

Sí, los nombres de grupo en Cloudability pueden tener hasta 63 caracteres. Este límite coincide con el límite de caracteres para grupos Entra ID en Microsoft Entra ID.

## ¿Cuánto tardan en surtir efecto los cambios al asignar Vistas a Grupos?

Los cambios serían casi inmediatos. Los usuarios que accedan a Ver a través de Grupos podrán ver las vistas casi de inmediato.

## ¿Los cambios realizados en Entra ID se reflejarán automáticamente en Cloudability?

Los cambios realizados en Entra ID no se transferirán automáticamente a Cloudability. Cloudability Los administradores tendrían que sincronizar manualmente utilizando el botón "Sincronizar grupos Entra ID".

## ¿Cuánto tiempo se tarda en sincronizar los grupos Entra ID?

Puede tardar desde unos milisegundos hasta unos minutos en función del número de grupos que se sincronicen y del número de usuarios de cada grupo. Si el proceso de sincronización tarda más, tendrás que esperar. Siempre puede volver y verificar el campo "Última sincronización" para saber si la sincronización se ha completado.

## ¿Qué ocurre si un usuario miembro de Entra ID Group no existe en Cloudability?

Durante la sincronización, Cloudability comprueba si los usuarios del grupo Entra ID existen o no en Cloudabilty. Si un usuario no existe en Cloudability, no se importará. Por lo tanto, si tiene 10 usuarios en un grupo Entra ID y sólo 8 existen en Cloudability, sólo se importarán 8 usuarios.

Nota: Traer a los usuarios que no son de cloudability no es útil, ya que no pueden iniciar sesión en Cloudability de todos modos.

## Al sincronizar grupos Entra ID, ¿por qué no se importan algunos usuarios a Cloudability?

Esto suele ocurrir cuando los usuarios en Entra ID ( Azure AD) no tienen una dirección de correo electrónico válida configurada **o** si el correo electrónico configurado no coincide con el correo electrónico del usuario en Cloudability. Aunque el usuario exista en el grupo, Cloudability sólo importará los usuarios cuyas direcciones de correo electrónico estén presentes y coincidan con las de Cloudability. Compruebe que el ID de correo electrónico del usuario no falta, está vacío o mal configurado en Entra ID.

## ¿Puede un usuario formar parte de varios Grupos de Usuarios?

Sí, los usuarios pueden formar parte de múltiples Grupos, tanto en grupos Entra ID como en Grupos de Usuarios Manuales.

## ¿Podemos utilizar estos grupos con vistas jerárquicas?

Sí. Tanto los Grupos de Usuarios como los Grupos Entra ID estarán disponibles también con los HV.

## ¿Cuál es la hoja de ruta para dar soporte a los grupos de usuarios y a los grupos de Entra ID para compartir informes, paneles de control, alertas, etc.?

Se prevé ofrecer compatibilidad con **grupos de usuarios** y **grupos de ID de Entrap,** pero aún no está disponible en todas las funciones. Actualmente, estos grupos no se pueden utilizar para compartir o alertar en las áreas que se enumeran a continuación:

1. Compartir informes y paneles: Actualmente solo tiene la opción de compartir con toda la organización o con usuarios.
2. Compartir paneles de control de contenedores: actualmente solo existe la opción de compartirlos con toda la organización o con usuarios específicos
3. Creación de alertas para la detección de anomalías
4. Compartir planes de carga de trabajo
5. Creación de alertas para el plan CFP

Las capacidades mencionadas anteriormente están incluidas en la hoja de ruta y estamos trabajando activamente para ampliar el uso compartido y las alertas basadas en grupos en todas estas funciones. Las actualizaciones se comunicarán a medida que la funcionalidad esté disponible.

## ¿Están estos Grupos soportados en Apptio BI?

No, los grupos de usuarios y los grupos de ID de Entrap no son compatibles con Apptio BI. Por no mencionar que los informes y el panel de control de Cloudability respetarán el acceso a las vistas basado en estos grupos.

**Tema principal:** [Gestión de usuarios y grupos de usuarios](../admin/manage-users-and-user-groups.html)
