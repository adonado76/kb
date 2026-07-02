---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Cloudability Incorporación de una nueva instancia de Turbonomic"
breadcrumb:
  - "Cloudability Premium"
  - "Turbonomic Integración"
source_path: "product/turbonomic-integration-cloudability-production.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability Incorporación de una nueva instancia de Turbonomic

## Visión general

En un entorno de producción, cualquier configuración se realiza automáticamente con la ayuda de PPO. La única acción manual necesaria es configurar los permisos para los usuarios en Frontdoor. Esto debe hacerlo el usuario Administrador del cliente.

En esta sección se abordará la diferencia en la configuración de los roles de usuario y los ámbitos entre las instancias de Turbonomic que no utilizan Frontdoor y las instancias de Turbonomic habilitadas para Frontdoor, así como la descripción de los propios permisos disponibles en el entorno de producción.

En una instancia de Cloudability Premium Turbonomic, los usuarios se crean automáticamente al iniciar sesión por primera vez en Turbonomic, según la configuración que tengan en Frontdoor. La configuración de Frontdoor se utiliza para establecer los roles de usuario en Turbonomic (que se basan en los permisos de Frontdoor), pero no hay forma de configurar los ámbitos de Turbonomic desde Frontdoor. La asignación inicial del ámbito de usuario solo se produce cuando el usuario inicia sesión por primera vez (y la cuenta de usuario se crea automáticamente en Turbonomic ). Cabe destacar que, una vez que la cuenta de usuario existe en Turbonomic, modificar los permisos en Frontdoor no afectará al ámbito de este usuario. Para configurar un alcance más detallado, será necesario que el administrador del cliente realice algunos pasos adicionales (en Turbonomic ).

## Ámbitos de aplicación en « Turbonomic »

Los «Scopes» de Turbonomic funcionan de manera similar a las «Views» de Cloudability, pero conviene señalar que no están sincronizados entre Cloudability y Turbonomic, por lo que deben configurarse por separado en cada aplicación. Esto solo ocurre en la fase inicial de la integración entre ambos, en la que el cliente tiene acceso directo a la aplicación Turbonomic. En futuras versiones de nuestra integración, el cliente no podrá iniciar sesión directamente en Turbonomic y no tendrá que configurar esos ámbitos: Cloudability se encargará de todas las acciones necesarias para conceder al usuario acceso a los recursos especificados.

## Permisos de acceso

Aquí encontrarás una lista de todos los permisos disponibles en la instancia de producción de Frontdoor, que pueden utilizarse para la autorización de « Turbonomic ».

| Nombre del permiso | Descripción |
| --- | --- |
| ScopedAutomatorFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic (incluidas «Plan», «Park» y «Place»), pero no pueden configurar la instalación de Turbonomic ni crear políticas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedDeployerFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de « Turbonomic », utilizar «Place» para reservar cargas de trabajo y crear políticas y plantillas de asignación. Sin embargo, los usuarios no pueden ejecutar planes ni acciones recomendadas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedAdvisorFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de Turbonomic, así como ejecutar planes. Sin embargo, los usuarios no pueden utilizar Place para reservar cargas de trabajo, crear políticas ni ejecutar ninguna acción recomendada. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la Página de Inicio y los Cuadros de Mando. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedOperationalObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la Página de Inicio, los Cuadros de Mando, los Grupos y las Políticas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedSharedAdvisorFullAccess | Los usuarios con este permiso pueden ver la Página de Inicio y los Cuadros de Mando, pero sólo pueden ver las Máquinas Virtuales y las Aplicaciones. Los usuarios no pueden realizar acciones de tipo « Turbonomic ». Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| ScopedSharedObserverFullAccess | Los usuarios con este permiso pueden ver la Página de Inicio y los Cuadros de Mando personalizados, pero sólo pueden ver las Máquinas Virtuales y las Aplicaciones. Los usuarios no pueden ver los paneles ejecutivos ni realizar acciones de « Turbonomic ». Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. |
| SiteAdminFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic y modificar los ajustes específicos del sitio para configurar la instalación de Turbonomic. Los usuarios también pueden administrar Grupos, Políticas, Flujos de trabajo, Plantillas, Facturación/Costes y Configuración de destino, pero no Correo electrónico, Licencias, Actualizaciones y Mantenimiento. Los usuarios con este rol pueden establecer el alcance en otras cuentas. |
| AutomatorFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic (incluidas «Plan», «Park» y «Place»), pero no pueden configurar la instalación de Turbonomic ni crear políticas. |
| DeployerFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de « Turbonomic », utilizar «Place» para reservar cargas de trabajo y crear políticas y plantillas de asignación. Sin embargo, los usuarios no pueden ejecutar planes ni acciones recomendadas. |
| AdvisorFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de Turbonomic, así como ejecutar planes. Sin embargo, los usuarios no pueden utilizar Place para reservar cargas de trabajo, crear políticas ni ejecutar ninguna acción recomendada. |
| ObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la Página de Inicio y los Cuadros de Mando. |
| OperationalObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la Página de Inicio, los Cuadros de Mando, los Grupos y las Políticas. |

Los permisos de los roles de Frontdoor mencionados anteriormente se corresponden directamente con los roles integrados en Turbonomic. Por ejemplo, un permiso del rol «Frontdoor» en **ObserverFullAccess** otorgará el rol **«Observer»** a los usuarios de Turbonomic. Tenga en cuenta que la mayoría de los permisos enumerados anteriormente tienen dos variantes, y la diferencia entre ellas se basa en si al usuario se le asignará un ámbito vacío (sin acceso a ningún recurso), o con un ámbito completo (acceso a todos los recursos). Aparte de los ámbitos, estos dos permisos otorgan el mismo rol en Turbonomic (es decir, **ScopedObserverFullAccess** y **ObserverFullAccess** otorgan el rol **de «Observador»** a un usuario en Turbonomic ). Ten en cuenta que algunos permisos **no** admiten el ámbito de aplicación, ya que conceden acceso a todos los recursos independientemente de este (por ejemplo, **SiteAdminFullAccess** ).

En caso de que se apliquen varios permisos al mismo usuario en Frontdoor, Turbonomic elegirá el permiso con menos privilegios.

## Aplicación de ámbitos a los usuarios en Turbonomic

A los usuarios de Turbonomic se les asigna un rol y un ámbito adecuados durante su primer inicio de sesión (en función de los permisos iniciales del rol «Frontdoor»). Cabe señalar que un usuario no existe en Turbonomic (antes de iniciar sesión por primera vez) y, por lo tanto, no puede preconfigurarse con un ámbito granular.

Para aplicar ámbitos completos al usuario, siga los pasos que se indican a continuación.

1. Un Administrador aplica **ObserverFullAccess** permiso de rol al usuario en Frontdoor.
2. El usuario inicia sesión por primera vez en la instancia de Turbonomic; en ese momento, se crea automáticamente un nuevo usuario en Turbonomic en función de los permisos del rol en Frontdoor.
3. El usuario ya puede acceder a Turbonomic con el rol **de «Observador»** y se le concederá acceso a todos los recursos.

Para aplicar un ámbito limitado al usuario, siga los pasos que se indican a continuación.

1. Un Administrador aplica el permiso **ScopedObserverFullAccess** permiso de rol al usuario en Frontdoor
2. El usuario inicia sesión por primera vez en la instancia de Turbonomic; en ese momento, se crea automáticamente un nuevo usuario en Turbonomic en función de los permisos del rol en Frontdoor
3. Ahora el usuario puede acceder a Turbonomic con el rol **«Scoped Observer»,** pero no tiene acceso a ningún recurso.
4. Un administrador inicia sesión en Turbonomic y configura un ámbito para este usuario con los correspondientes derechos de acceso a los recursos.
5. Cuando el usuario vuelva a iniciar sesión, podrá acceder a Turbonomic con el rol **«Scoped Observer»** y se le asignará el ámbito correspondiente.

## Actualización de los roles de usuario en Turbonomic

Para cambiar el rol de un usuario en Turbonomic, el administrador debe actualizar los permisos asignados a dicho usuario en Frontdoor. Cada vez que se inicie sesión, Turbonomic comprobará los roles asignados actualmente al usuario en Frontdoor y actualizará su configuración cuando sea necesario. Este proceso no afectará a los ámbitos, ya que la comprobación de los ámbitos solo se realiza durante el primer inicio de sesión en Turbonomic.

En caso de que los roles se actualicen directamente en Turbonomic, la configuración de Frontdoor anulará el rol de los usuarios la próxima vez que inicien sesión.

**NOTA** : Cuando se añaden usuarios a Turbonomic en Cloudability Premium, no se eliminan automáticamente al dar de baja su acceso a Frontdoor. En caso de que esto ocurra (por ejemplo, al dar de baja a un usuario), será necesario eliminar manualmente al usuario de Turbonomic. Desde el punto de vista de la seguridad, cabe señalar que, cuando se elimina a un usuario de Frontdoor, dicho usuario ya no podrá acceder a Turbonomic (ya que el acceso lo controla Frontdoor).
