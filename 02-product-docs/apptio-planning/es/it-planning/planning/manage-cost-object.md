---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Permisos para objetos de coste"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/manage-cost-object.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Permisos para objetos de coste

Nota: *Sólo los usuarios con funciones de Administrador o Propietario de Proceso Presupuestario pueden gestionar los Permisos de Objetos de Coste.*

Los permisos de objetos de coste controlan qué usuarios tienen acceso a departamentos específicos dentro de un plan. Los administradores pueden gestionar el acceso de forma global en todo el entorno o a nivel de plan individual para garantizar una visibilidad, colaboración y seguridad de los datos adecuadas.

## Permisos globales frente a permisos a nivel de plan

Apptio La planificación admite dos niveles de gestión de accesos:

**Permisos globales para objetos de coste**

La página global de **Permisos de Objetos de Coste** sirve como plantilla para definir los valores predeterminados de acceso de toda la organización.

- Se encuentra en **Configuración → Datos de referencia → Permisos de objetos de coste**.
- Define la configuración de acceso por defecto que se aplica cuando se crean nuevos planes.
- Las modificaciones en los permisos de los objetos de coste se registrarán en el historial de cambios.

**Permisos de usuario a nivel de plan**

Recuerde: la función Permisos de objetos de coste a nivel de plan está habilitada

Los usuarios deben tener el **ManagePlans** permiso (concedido por defecto a los roles de administrador y propietario del proceso presupuestario) para ver o editar los permisos a nivel de plan.

Cada plan incluye su propia página de **Permisos de usuario**, accesible a través de **Plan → Configuración → Permisos de usuario**, que permite a los administradores asignar o ajustar el acceso directamente dentro de un plan.

- Controla el acceso de los usuarios a **nivel de plan** para cada Departamento.
- Anula los permisos globales una vez creado un plan.
- Cuando se crea un plan a partir de una línea de base, los Permisos de Usuario del plan de la línea de base se copian en el nuevo plan.

Cuando se activa la función **«Permisos de objetos de coste a nivel de plan»**, los permisos globales ya no determinan automáticamente el acceso. En su lugar:

- **Nuevo plan (sin referencia):** los permisos globales de objetos de coste se copian en el plan al crearlo.
- **Nuevo plan (con plan de referencia):** Los permisos de usuario del plan de referencia se copian en el nuevo plan.

## Configuración de permisos para objetos de coste

**Para configurar los permisos globales:**

1. Vaya a **Configuración → Permisos de objetos de coste**.
2. Utilice la tabla para definir los niveles de acceso por usuario y Departamento.
3. Utilice **Exportar → Exportar todo** para descargar la lista de permisos como.csv para actualizaciones masivas.

**Para configurar los permisos a nivel de plan:**

1. Vaya a **Configuración** **(icono de engranaje)** → **Perfil de la empresa**.
2. Seleccione **Configuración general → Acceso y permisos.**
3. Asegúrese de que la casilla de verificación **Habilitar permisos de objetos de coste a nivel de plan** esté activada
4. Abra un plan y vaya a **Plan → Configuración → Permisos de usuario**.
5. Utilice la tabla para definir los niveles de acceso por usuario y Departamento.
6. Utilice **la opción «Exportar permisos»** del menú desplegable de la tabla (...) para descargar la lista de permisos en formato.csv y realizar actualizaciones masivas.
7. Utilice **la opción Importar permisos** del menú desplegable de la tabla (...) para cargar el archivo.csv modificado.

**Descripción de los campos**

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Objeto de coste | El identificador único para el Departamento o centro de costes. |
| Nombre de usuario | El usuario asignado al Departamento. La lista se basa en los usuarios que tienen acceso al entorno de planificación en Apptio Frontdoor. |
| Editar nivel | Concede permisos de edición: Propietario, Editar y enviar, Editar o Sólo ver. Consulte [«Flujos de trabajo de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(se abre en una pestaña o una ventana nueva)") aprobación» para obtener más información. |
| Nivel de aprobación | Define los derechos de aprobación (niveles 1-10) para las aprobaciones de varios niveles. Consulte [«Flujos de trabajo de](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-about-approval "(se abre en una pestaña o una ventana nueva)") aprobación» para obtener más información. |
| Puede ver columnas sensibles | Permite ver las columnas marcadas como sensibles en el esquema de partidas individuales de Trabajo en las pestañas Trabajo y Resumen. Consulte [*las preguntas frecuentes: Ocultar datos confidenciales sobre el personal*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(se abre en una pestaña o una ventana nueva)")*.* |
| Visualización de datos financieros sensibles | Concede visibilidad a las partidas financieras de la pestaña Resumen que se derivan de los datos Laborales. Consulte [*las preguntas frecuentes: Ocultar datos confidenciales sobre mano de obra*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(se abre en una pestaña o una ventana nueva)")*.* |

Importante:

Cuando está activada la función «Permisos de objetos de coste a nivel de plan»

- Ahora se debe conceder acceso **explícito** a los usuarios a nivel del plan.
- Los permisos globales de objetos de coste por sí solos no proporcionan acceso a los planes.

Nota:

- Los usuarios con funciones de **Administrador** o **Propietario del proceso presupuestario** tienen acceso automáticamente a **todos los Departamentos de** forma predeterminada. Todos los demás usuarios deben tener acceso explícito.
- Para restringir el acceso de los Propietarios de presupuesto sólo a los Departamentos que pueden ver, active **Aplicar permisos de visualización** en el **Perfil de empresa**.
- Cuando está desactivada, los usuarios pueden ver toda la jerarquía de Departamentos pero sólo pueden interactuar con los Departamentos a los que están asignados.
- **Los Permisos de Objeto** de Coste descienden en cascada a través de la jerarquía a menos que un Objeto de Coste de nivel inferior tenga definidos permisos más específicos.

## Comportamiento del acceso en las comparaciones de planes

Si se activa la función «Permisos de objetos de coste a nivel de plan», la comparación de planes funcionará de la siguiente manera:

- Los datos de la tabla «Gastos» se mostrarán en función de los permisos del usuario en el **plan de origen (de comparación)**. Por ejemplo, si un usuario tiene acceso al departamento D1 en el plan de origen *«Plan A»*, pero no tiene acceso a D1 en el plan de comparación *«Plan B»*, el usuario podrá seguir viendo los detalles de la comparación para D1, ya que el acceso está concedido en el plan de origen.
- Los detalles del informe de análisis de desviaciones también se mostrarán en función de los permisos de acceso del usuario en el plan de origen.
- Si se han habilitado los datos relacionados con la mano de obra, el usuario debe tener permiso tanto para las columnas relacionadas con la mano de obra como para los datos financieros de **todos los planes comparados** a fin de poder ver los resultados de la comparación.

## Publicar permisos a nivel de plan para todos los planes

Nota: Esta opción no está disponible cuando la función **de aprobación multinivel** está activada,

**Para aplicar permisos a nivel de plan de forma masiva a todos los planes** :

1. Seleccione los permisos mediante la casilla de verificación en la página **Permisos de usuario** (Plan > Configuración > Permisos de usuario)
2. Haga clic con el botón derecho del ratón o utilice el menú desplegable de la tabla (**...** ) para abrir el menú de acciones y seleccionar **Publicar en todos los planes**.
3. Haga clic **en Confirmar** para aplicar los permisos seleccionados a todos los planes.

**Para aplicar de forma masiva permisos a nivel de plan a los permisos globales de objetos de coste** :

1. Seleccione los permisos mediante la casilla de verificación en la página **Permisos de usuario** (Plan > Configuración > Permisos de usuario)
2. Haga clic con el botón derecho del ratón o utilice el menú desplegable de la tabla (**...** ) para abrir el menú de acciones y seleccionar **Publicar en datos de referencia**.
3. Haga clic en **Confirmar** para aplicar los permisos seleccionados a Configuración > Permisos de objetos de coste

## Publicar permisos de objetos de coste globales en todos los planes

Cuando están habilitados **los permisos de usuario a nivel de plan**, los administradores y los responsables del proceso presupuestario pueden publicar **permisos globales de objetos de coste** directamente en los planes seleccionados. Esto simplifica la gestión centralizada de permisos y mantiene la coherencia entre los distintos planes sin necesidad de intervención manual.

**Para publicar los permisos globales en todos los planes:**

1. Ve a Configuración **→** Permisos de objetos de coste
2. En el **menú de los tres puntos**, selecciona «**Publicar todos los permisos en los planes** ».
3. En el cuadro de diálogo **«Configuración de publicación»**, seleccione una de las siguientes opciones:
   1. **Actualizar permisos** : actualiza únicamente los permisos coincidentes de los permisos globales de objetos de coste y los permisos de usuario a nivel de plan para los planes seleccionados.
   2. **Reemplazar todos los permisos** : elimina todos los permisos existentes de los planes seleccionados y los sustituye por completo por los permisos globales de objetos de coste.
4. Utiliza el menú desplegable de selección múltiple **de planes** para elegir uno, varios o todos los planes a los que se deben aplicar los permisos.
5. Haz clic **en «Confirmar»**

**Resultado:** Todos los permisos de **los permisos globales de objetos de coste** se copian a **los permisos de usuario a nivel de plan** para los planes seleccionados, según la opción de publicación elegida.

## Eliminar de forma masiva los permisos de usuario de todos los planes

Nota: Esta opción no está disponible cuando la función **de aprobación multinivel** está activada,

**Para eliminar de forma masiva los permisos de los usuarios de todos los planes** :

1. Seleccione los permisos mediante la casilla de verificación en la página **Permisos de usuario** (Plan > Configuración > Permisos de usuario)
2. Haga clic con el botón derecho del ratón o utilice el menú desplegable de la tabla (**...** ) para abrir el menú de acciones y seleccionar «**Eliminar permiso de todos los planes** ».
3. Haga clic en **«Confirmar»** para eliminar los permisos seleccionados de todos los planes y de «Configuración > Permisos de objetos de coste».
