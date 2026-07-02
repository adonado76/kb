---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Arquitectura del modelo de permisos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/permission-model-arch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Arquitectura del modelo de permisos

**Cómo encajan los permisos de los informes en la jerarquía de seguridad**

El modelo de permisos de TBM Studio funciona dentro de una arquitectura de seguridad por capas:

|  |  |  |
| --- | --- | --- |
| **Nivel** | **Ámbito** | **Controlado por** |
| **Dominio** | Todos los proyectos de un dominio | Administración de accesos mejorada |
| **Proyecto** | Todos los activos de un proyecto | Asignación de roles a nivel de proyecto |
| **Recopilación de informes** | Grupos de informes relacionados | Permisos a nivel de colección |
| **Informe** | Informe individual | Permisos a nivel de informe |
| **Componente** | Elementos de un informe | Configuración de la visibilidad de los componentes |
| **Datos (RLS)** | Acceso a los datos a nivel de fila | Proyecto de seguridad a nivel de fila |

Los permisos se aplican de un ámbito más amplio a uno más específico. Un usuario debe disponer de los permisos de acceso adecuados en cada nivel para poder consultar un informe y sus datos. Por ejemplo, un usuario con permiso de visualización a nivel de informe no podrá ver los datos filtrados por RLS a menos que su ID de usuario figure en las tablas de asignación de RLS.

**Relación con los permisos del proyecto**

Los permisos de los informes son un subconjunto del modelo general de permisos del proyecto. La función asignada a un usuario a nivel de proyecto determina sus capacidades básicas:

**Heredado del rol del proyecto:**

- Posibilidad de acceder a TBM Studio y a proyectos concretos
- Posibilidad de crear nuevos informes (requiere permisos para crear contenido)
- Posibilidad de consultar y modificar la configuración
- Acceso a las funciones administrativas

**Configurado a nivel de informe:**

- ¿Qué roles pueden ver informes específicos?
- ¿Qué roles pueden ver componentes específicos dentro de los informes?
- Informar sobre la pertenencia a la colección y la visibilidad

Nota: Las funciones de los proyectos se gestionan a través de la Administración de acceso mejorada. Para obtener información sobre cómo configurar los roles de usuario, consulte la sección «Gestión de usuarios» de 6.2:.

**Relación con la seguridad a nivel de fila (RLS)**

La seguridad a nivel de fila y los permisos de informe tienen fines distintos y funcionan de forma conjunta:

|  |  |  |
| --- | --- | --- |
| **Aspecto** | **Permisos del informe** | **Seguridad a nivel de fila** |
| **Controles** | Acceso a la interfaz de usuario del informe | Acceso a las filas de datos |
| **Granularidad** | Nivel de informe/componente | Filas de datos individuales |
| **Configurado en** | Report Studio | Proyecto de seguridad a nivel de fila |
| **Basado en** | Asignación de roles | Asignación de identificadores de usuario |

Es posible que un usuario tenga permiso para ver un informe, pero que solo pueda ver una parte de los datos debido a la configuración de RLS. Por el contrario, RLS no concede acceso a los informes: los usuarios siguen necesitando los permisos adecuados a nivel de informe.

Importante: La seguridad a nivel de fila afecta a todos los usuarios, pero no protege los datos frente a los usuarios con privilegios de administrador. Los usuarios con privilegios de administrador tienen acceso al modo Studio y pueden crear informes que eludan el RLS, añadirse a las tablas de asignación del RLS o desactivar el RLS por completo. No confíes únicamente en RLS para proteger los datos confidenciales frente a los administradores

.

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
