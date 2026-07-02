---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Control de accesos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Control de accesos

|  |  |
| --- | --- |
| **Tipo de contenido** | Guías prácticas |
| **Destinatarios** | Administradores, usuarios avanzados |
| **Tiempo de finalización** | 45-60 minutos (varía según el guía) |
| **Requisitos previos** | Usuarios y roles configurados (sección 3.4.1 ), rol de administrador o de usuario avanzado |

## Visión general

TBM Studio ofrece varios niveles de control de acceso para garantizar que los usuarios solo vean los informes y los datos correspondientes a su función. En esta sección se tratan tres enfoques complementarios: los permisos de informes (quién puede ver qué informes), la seguridad a nivel de fila (qué filas de datos pueden ver los usuarios) y los permisos de edición de tablas (quién puede modificar datos específicos).

Estos mecanismos de control de acceso funcionan conjuntamente para crear un modelo de seguridad integral. Puedes combinarlos según las necesidades de tu organización. Para conocer los fundamentos conceptuales de la arquitectura de seguridad de TBM Studio, consulte **la sección «Modelo de seguridad de 4.4:** ». Para obtener más información sobre la implementación de RLS en la capa de datos, consulte **la sección « 3.1.4: : Seguridad de los datos** ».

## Comprensión de los niveles de control de acceso

TBM Studio implementa el control de acceso en tres niveles distintos, cada uno de los cuales tiene una finalidad diferente:

|  |  |  |
| --- | --- | --- |
| **Capa** | **Qué controla** | **Ideal para** |
| **Permisos del informe** | Visibilidad de los informes completos y de sus componentes | Restringir el acceso a paneles de control o colecciones de informes específicos según el rol del usuario |
| **Seguridad a nivel de fila (RLS)** | Qué filas de datos puede ver un usuario en todos los informes | Escenarios multitenant en los que los distintos usuarios deben ver diferentes subconjuntos de datos (por ejemplo, por unidad de negocio o centro de coste) |
| **Permisos de las tablas editables** | ¿Quién puede editar, subir o eliminar datos en las tablas editables? | Introducción de datos distribuida en la que los distintos equipos gestionan sus propios datos de correspondencias o clasificación |

- **[Guía para la toma de decisiones: cómo elegir el sistema de control de acceso adecuado](../../../../studio/new-uc/howtoguides/manage-users-permission/decision-guide.html)**
- **[Configurar permisos de informes por rol](../../../../studio/new-uc/howtoguides/manage-users-permission/set-report-perm.html)**
- **[Implementar la seguridad a nivel de fila para el acceso de los usuarios](../../../../studio/new-uc/howtoguides/manage-users-permission/implement-rls.html)**
- **[Configurar los permisos de las tablas editables](../../../../studio/new-uc/howtoguides/manage-users-permission/config-et-perm.html)**
