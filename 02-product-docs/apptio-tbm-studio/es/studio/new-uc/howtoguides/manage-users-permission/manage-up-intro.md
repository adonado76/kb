---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gestión de usuarios"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gestión de usuarios

|  |  |
| --- | --- |
| **Tipo de contenido:** | Guía práctica |
| **Destinatarios:** | Administradores |
| **Requisitos previos:** | Rol de administrador o usuario avanzado, acceso a la administración de acceso ampliado |
| **Secciones relacionadas:** | Sección 3.4.2 (Control de acceso), sección 6.2 (Referencia de gestión de usuarios) |

## Introducción

La gestión de usuarios es fundamental para controlar quién puede acceder a TBM Studio y qué acciones puede realizar. En esta sección se describen las tareas diarias que deben realizar los administradores para configurar y gestionar el acceso de los usuarios, lo que incluye crear usuarios, asignar roles y configurar roles personalizados para necesidades específicas.

TBM Studio utiliza **Enhanced Access Administration** (también conocido como Frontdoor) como interfaz central para gestionar usuarios y roles en todas las aplicaciones de Apptio. Los usuarios se definen a nivel de dominio, y su acceso a proyectos y funciones específicos se controla mediante la asignación de roles.

## Comprender los roles predeterminados

TBM Studio ofrece varios roles predeterminados que abarcan los patrones de acceso más habituales. Comprender estas funciones te ayuda a asignar los niveles de acceso adecuados y a determinar cuándo es necesario crear funciones personalizadas.

|  |  |  |
| --- | --- | --- |
| **Rol** | **Descripción** | **Uso habitual** |
| **Administrador** | Acceso administrativo completo a todas las funciones, incluida la gestión de usuarios, la configuración de proyectos y todos los datos. | Administradores de TBM, propietarios de sistemas, administradores de seguridad. |
| **Usuario avanzado** | Puede configurar modelos, crear informes, cargar datos y acceder a entornos de desarrollo. No se pueden gestionar los usuarios ni la configuración del dominio. | TBM Architects, analistas financieros de TI que elaboran modelos e informes. |
| **Usuario de negocio** | Ver los informes y datos de producción. Puede interactuar con tablas editables si se le concede permiso. No hay acceso a la configuración. | Partes interesadas de la empresa, ejecutivos y jefes de departamento que consultan los informes. |
| **Analista** | Acceso a la visualización y posibilidad de crear informes personales. Tiene permiso para editar informes personales. | Analistas de negocios que necesitan crear informes puntuales para uso personal. |

Nota: Empieza con los roles predeterminados que mejor se adapten a las necesidades de tus usuarios. Más adelante puedes crear roles personalizados para los usuarios que necesiten una combinación específica de permisos que no se corresponda con ningún rol predeterminado.

- **[Crear y gestionar usuarios](../../../../studio/new-uc/howtoguides/manage-users-permission/create-manage-users.html)**
- **[Asignar roles a los usuarios](../../../../studio/new-uc/howtoguides/manage-users-permission/assign-roles-users.html)**
- **[Configurar roles personalizados](../../../../studio/new-uc/howtoguides/manage-users-permission/config-custom-roles.html)**
