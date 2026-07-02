---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Roles y permisos de usuario"
breadcrumb:
  - "Costing Standard"
  - "Administración"
source_path: "cost-transparency/admin/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Roles y permisos de usuario

IBM Apptio Costing Standard utiliza un control de acceso basado en roles para garantizar que los usuarios tengan la visibilidad y los permisos adecuados en todos los modelos de costes, datos e informes. Los roles definen el nivel de acceso dentro de la aplicación, mientras que los permisos proporcionan un control más detallado sobre tareas específicas. Esta estructura ayuda a las organizaciones a equilibrar la gobernanza, la seguridad y el acceso de autoservicio entre las partes interesadas de las áreas de finanzas, TI y negocios. IBM Apptio utiliza la aplicación **Frontdoor** para gestionar los usuarios, sus roles y permisos en toda la plataforma. Frontdoor proporciona una gestión centralizada de identidades y accesos, lo que garantiza una gobernanza coherente de los usuarios en todos los proyectos y soluciones.

## Gestionar usuarios

Los administradores pueden gestionar los usuarios añadiendo nuevos usuarios, activando o desactivando usuarios existentes, exportando la lista de usuarios y eliminando usuarios cuando ya no sea necesario su acceso.

Para gestionar usuarios, vaya al menú **Configuración** (![engranaje](_829212255.)) y seleccione **Administración de acceso**. La consola de administración de Access se abre con la pestaña **Usuarios** seleccionada de forma predeterminada. Desde esta página, los administradores pueden buscar en todos los registros de usuarios, filtrar y ordenar la lista de usuarios, y ocultar a los usuarios inactivos utilizando los controles disponibles en la parte superior de la página.

Utilice esta pantalla para añadir, actualizar o eliminar el acceso de los usuarios según sea necesario para mantener una gobernanza y una seguridad adecuadas.

Para obtener más información sobre cómo realizar estas acciones, vaya [aquí.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-users "(se abre en una pestaña o una ventana nueva)")

## Gestionar roles y permisos de usuario

Los roles definen un conjunto de permisos y capacidades que controlan las acciones que los usuarios pueden realizar dentro de IBM Apptio. A cada usuario se le asignan uno o más roles que determinan su nivel de acceso y funcionalidad.

Para gestionar los roles, vaya al menú **Configuración (**![engranaje](_8791317.)**)** y seleccione **Administración de acceso**. En el menú de navegación de la izquierda, haz clic en **Roles y permisos**. Esta página permite a los administradores añadir, modificar o eliminar asignaciones de roles para los usuarios dentro de un proyecto.

Para obtener más información sobre cómo gestionar roles y permisos, vaya [aquí.](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)")

## Roles de usuario estándar

IBM Apptio Costing Standard incluye estas funciones predefinidas:

- **Administrador**
- Acceso administrativo completo a las aplicaciones Costing Standard, TBM Studio, Datalink, Planning e Interactive Benchmarking sin restricciones funcionales.
- **Administrador de la empresa**
- Realiza tareas administrativas avanzadas, incluyendo promociones de autoservicio y la configuración y ejecución de DataLink.
- **Usuario avanzado**
- Crea y gestiona proyectos y modelos, carga y transforma datos, y elabora informes y paneles de control.
- **Analista**
- Crea informes y análisis personales utilizando los datos disponibles y consulta los informes existentes.
- **Jefe de servicio**
- Carga datos y revisa informes relacionados con los servicios y el rendimiento operativo.
- **Gestor de proyectos**
- Revisa los informes financieros y operativos relacionados con el proyecto para realizar un seguimiento de los costes, el progreso y los resultados.
- **Finanzas**
- Revisa informes financieros para analizar costes, presupuestos y variaciones en todos los ámbitos de TI.
- **Usuario de negocio**
- Informes compartidos con las opiniones disponibles en toda la organización para obtener información general sobre el negocio.
- **Usuario ejecutivo**
- Visualiza todos los informes publicados para respaldar la toma de decisiones estratégicas y ejecutivas.
- **Solo visualización**
- Proporciona acceso de solo lectura a los informes de producción; los usuarios pueden ver el contenido publicado, pero no pueden modificar ni crear informes.

## Roles personalizados

Además de las funciones estándar, IBM Apptio le permite crear **funciones personalizadas** utilizando la aplicación Frontdoor. Las funciones personalizadas permiten a las organizaciones adaptar el acceso de los usuarios en función de responsabilidades específicas y requisitos de gobernanza.

También puede duplicar una función estándar existente y modificar sus permisos añadiendo o eliminando capacidades para satisfacer las necesidades de su organización.

Para obtener más información sobre cómo crear y gestionar roles personalizados, vaya [aquí](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles#Manageuserpermissionsandroles__Createcustomroles__title__1 "(se abre en una pestaña o una ventana nueva)").
