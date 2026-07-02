---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gestión de usuarios"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/user-management.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gestión de usuarios

**Tipo de contenido:** Guía práctica / Referencia

**Destinatarios:** Administradores

**Requisitos previos:** rol de administrador, acceso a la administración de Access

La gestión de usuarios en TBM Studio consiste en crear y gestionar cuentas de usuario, asignar roles y controlar el acceso a proyectos y funciones. La herramienta principal para la gestión de usuarios es la Administración de acceso mejorada (Frontdoor).

## Comprender los roles y los permisos

Los roles determinan qué acciones pueden realizar los usuarios en TBM Studio. A cada usuario se le asignan uno o varios roles, y el nivel de acceso viene determinado por la combinación de los permisos de todos los roles asignados.

**Roles predeterminados del sistema:**

|  |  |
| --- | --- |
| **Rol** | **Funciones** |
| **Administrador** | Acceso completo a todas las funciones, incluyendo la gestión de usuarios, la configuración de proyectos, la configuración de dominios y todas las funciones de TBM Studio. Puede crear y cerrar ramas. |
| **Usuario avanzado** | Acceso al modo TBM Studio para crear modelos, elaborar informes y configurar flujos de datos. No se pueden gestionar los usuarios ni la configuración del dominio. |
| **Usuario de negocio** | Acceso de solo lectura a los informes y paneles de control. Puede interactuar con tablas editables si se configura. No puedo acceder al modo TBM Studio. |

**Nota:** *Se pueden crear roles personalizados para ofrecer un control detallado de los permisos. Póngase en contacto con el administrador del sistema para configurar roles personalizados adaptados a su organización.*

## Gestión de cuentas de usuario

La gestión de cuentas de usuario se lleva a cabo a través de la Administración de acceso mejorada (Frontdoor). Esta interfaz centralizada permite a los administradores crear cuentas, asignar roles y gestionar el acceso en todas las aplicaciones de Apptio.

**Para acceder a la gestión de usuarios:**

1. Haz clic en el icono **de Ajustes** situado en la esquina superior derecha.
2. Selecciona «**Administración de accesos** ».
3. Ve a la pestaña **«Usuarios»** para ver y gestionar las cuentas de usuario.

## Propiedades del usuario

Cada cuenta de usuario tiene propiedades que determinan su experiencia en TBM Studio. Los usuarios pueden modificar algunas de estas propiedades por sí mismos a través del cuadro de diálogo «Mi cuenta».

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| **Correo electrónico** | El nombre de usuario. El usuario no puede modificarlo. |
| **Nombre completo** | Nombre que aparece en la lista de usuarios y en los registros de actividad. |
| **Rol actual** | Función activa que determina los permisos. Los usuarios pueden cambiar entre los roles disponibles. |
| **Moneda** | Moneda predeterminada para los informes. Las preferencias del usuario tienen prioridad sobre la configuración del proyecto. |
| **Entorno local** | Preferencia de formato numérico (por ejemplo, EE. UU.: 12. 345.67, frente a Alemania: 12.345,67). |

## Control de la visibilidad del proyecto

La visibilidad del proyecto determina qué roles pueden ver y acceder a proyectos específicos. Esto te permite restringir el acceso a proyectos confidenciales o en fase de desarrollo.

**Para configurar la visibilidad del proyecto:**

1. Ve a **Configuración > Administración de accesos**.
2. En la pestaña **«Aplicaciones»**, busca tu proyecto.
3. Haz clic en **«Editar visibilidad»** para seleccionar qué roles pueden acceder al proyecto.
4. Haz clic en **«Guardar»** y, a continuación**, en «Mostrar»** para que el proyecto sea visible.
