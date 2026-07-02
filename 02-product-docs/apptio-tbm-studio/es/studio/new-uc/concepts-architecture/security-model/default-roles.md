---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Roles predeterminados"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Control de acceso basado en roles (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/default-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Roles predeterminados

TBM Studio ofrece tres roles predeterminados. Cada rol representa un nivel de acceso común para diferentes tipos de usuarios.

**Administrador (Admin)**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Funciones | Acceso completo a todas las funciones: crear y editar proyectos, gestionar usuarios y roles, configurar los ajustes de seguridad, compilar y publicar proyectos, crear informes, modificar modelos, cargar datos y acceder a todos los entornos (Desarrollo, Prueba, Producción) |
| Responsabilidades habituales | Configuración del sistema, gestión de usuarios, administración de la seguridad, gestión del ciclo de vida de las compilaciones, resolución de problemas, instalación de componentes |
| Cuándo asignar | Responsables financieros de TI que configuran TBM Studio, administradores de sistemas encargados de la plataforma y analistas sénior que gestionan el modelo y el proceso de implementación |
| Permisos clave | AccessDev, AccessStg, AccessProd, Editar modelos, UploadData, ViewViewAllData,, además de todos los permisos de visualización y generación de informes |

Importante:

**Admin y RLS**

La seguridad a nivel de fila no restringe de forma fiable a los usuarios con privilegios de administrador. Los usuarios con privilegios de administrador tienen acceso al modo Studio y pueden, en última instancia, crear informes que eludan el RLS, añadirse a las tablas de asignación del RLS y desactivar el RLS por completo. No confíes en RLS para proteger los datos de los usuarios con privilegios de administrador.

**Usuario avanzado**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Funciones | Puede crear y editar informes, modificar modelos y transformaciones de datos, cargar datos y acceder a entornos de desarrollo y de prueba. Puede revisar los mensajes de error. No se pueden gestionar usuarios ni modificar la configuración a nivel de dominio. |
| Responsabilidades habituales | Crear y mantener modelos de costes, elaborar informes para las partes interesadas, transformar datos y realizar cálculos preliminares |
| Cuándo asignar | Analistas financieros de TI que elaboran modelos de costes, desarrolladores de informes que diseñan y mantienen informes, analistas de datos que gestionan flujos de datos |
| Permisos clave | AccessDev, AccessStg, Editar modelos, UploadData, DrillDown, Editar informes personales, además de los permisos de visualización estándar |

**Usuario de negocio**

|  |  |
| --- | --- |
| **Aspecto** | **Detalles** |
| Funciones | Ver informes y datos en el entorno de producción. Solo se permite la visualización; no se pueden modificar los modelos, las transformaciones ni la configuración del sistema. Puede interactuar con los componentes de tablas editables en los informes cuando se le haya concedido permiso. |
| Responsabilidades habituales | Consultar informes de gastos, analizar el gasto en TI, revisar las asignaciones, introducir datos en tablas editables (si están configuradas) |
| Cuándo asignar | Las partes interesadas de la empresa que necesiten consultar informes, los jefes de departamento que revisen sus datos de costes, cualquier usuario que necesite acceso de solo lectura |
| Permisos clave | AccessProd, ViewReportsSavedForEveryone, ViewObjectReports, ViewMetricReports, DrillDown, además de permisos de visualización limitados |

Nota:

**Funciones adicionales**

Algunas instalaciones incluyen un rol de «Analista» con el permiso «Editar informes personales», lo que permite a los usuarios crear informes personales que solo ellos pueden ver. Consulte a su administrador para obtener la lista completa de roles de su entorno.

**Tema principal:** [Control de acceso basado en roles (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
