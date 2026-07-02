---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Restringir el acceso a los datos salariales"
breadcrumb:
  - "Planning"
  - "Planificación laboral"
source_path: "it-planning/planning/restrict-access-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Restringir el acceso a los datos salariales

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados al rol de Administrador. Ver permisos y roles de Frontdoor.

Es posible que su empresa desee proteger información confidencial, como los índices de remuneración. Puede impedir que los usuarios vean la pestaña Mano de obra (incluidos los detalles del salario de la mano de obra) asignando un rol personalizado que deshabilite el ViewLabor permiso.

## Crear un rol personalizado que restrinja el acceso a la pestaña Trabajo

Cree roles personalizados para proporcionar permisos únicos. Por ejemplo, en las aplicaciones Apptio Planning , todos los roles incorporados permiten el acceso a los detalles salariales de la mano de obra (si están presentes) en la pestaña Mano de obra de la vista Partidas. Un administrador puede crear un rol personalizado que bloquee el acceso a la pestaña Trabajo y luego asignar ciertos usuarios a ese rol siguiendo las siguientes instrucciones:

1. Habilite las funciones de planificación laboral. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").
2. En el menú Apptio Planning , haga clic en el botón Configuración (![icono de configuración](../../resources/images/it%20planning_images/icon_gear.png)) y, a continuación, en **Access
   Administration**.
3. Seleccione Roles.
4. Compruebe que el rol personalizado no existe actualmente. Puede ver los permisos y detalles de las funciones haciendo clic en Ver en la columna Acciones de esa función.
5. Seleccione el rol Propietario del proceso presupuestario que se utilizará como plantilla para crear el nuevo rol personalizado. En la columna Acciones de esa función, haga clic en Clonar.
6. Introduzca un nombre y una descripción para la función (por ejemplo, BPO sin acceso a Trabajo).
7. En la columna Permiso, desactive el permiso ViewLabor. Tenga en cuenta que restringir el acceso a la pestaña Labor no afecta a otros permisos y capacidades de las aplicaciones de Apptio Planning .
8. Haga clic en Siguiente y, a continuación, en Guardar.
9. En el menú principal, haga clic en Aplicaciones. Si se ha modificado la visibilidad de alguna aplicación y el nuevo rol personalizado se aplica a esa aplicación, deberá añadir el nuevo rol personalizado a la visibilidad de esa aplicación.
10. Siga las instrucciones de Modificar funciones de usuario para asignar usuarios a la nueva función personalizada.

La próxima vez que el usuario se conecte a una aplicación de Apptio Planning , el acceso a la pestaña Trabajo estará restringido. Para más información sobre el servicio **Access
Administration**
, consulte Acerca de Frontdoor, la consola Apptio Access Administration .

## Ajustar las opciones del resumen laboral

Las partidas financieras relacionadas con la mano de obra aparecen en el cuadro de gastos. Estos se resumen en Centros de Coste y Cuentas, que pueden proporcionar detalles salariales. Además de limitar el acceso a la pestaña Mano de obra, puede evitar que los usuarios disciernan los detalles salariales ajustando la forma en que se resumen los valores financieros generados por la mano de obra.

1. En el menú Componente, seleccione Planning. Véase [Navegar en las aplicaciones Apptio Planning](navigate-apptio-planning.html "Este tema ofrece una visión general de cómo está organizada la navegación de planificación de Apptio. Los elementos de menú que aparecen en su cuenta dependen de sus permisos de usuario.") . > Gastos.
2. En la pestaña Resumen, seleccione Acciones > Opciones de resumen laboral.
3. Seleccione las dimensiones de datos y los atributos a integrar para los datos financieros relacionados con la mano de obra. Seleccionando más dimensiones y atributos se obtienen datos laborales más granulares; seleccionando menos opciones se obtienen datos laborales menos granulares.
