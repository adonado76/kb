---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configurar la mano de obra"
breadcrumb: []
source_path: "it-planning/planning/manage-labor-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar la mano de obra

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](manage-reference-data.html) ).

![imagen](../../resources/images/it%20planning_images/icon_video.png)

Vea este vídeo de Apptio Education Services: [Configuración de datos de referencia: Dimensiones Laborales](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-labor-d?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)").

## Gestionar las bolsas de trabajo externas o internas en los datos de referencia

◆ Se aplica a: Apptio Planning aplicaciones con Project Financial Planning (ver [Introducción al uso de Project Financial Planning módulo](pfp/gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera.") ) o Service Demand Planning (ver [Introducción al uso de Service Demand Planning módulo](sdp/gs-service-demand.html) )

Las tareas de esta sección requieren que obtenga una licencia para Project Financial Planning o Service Demand Planning, y que edite el perfil de la empresa para habilitar Project Financial Planning o Service Demand Planning. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

Defina pools de mano de obra externa para capturar el coste de mano de obra externa directa de su proyecto o servicio. Tenga en cuenta que antes de configurar los pools de trabajo externos, primero debe actualizar las dimensiones de su departamento.

1. En el perfil de la empresa, active la planificación laboral y, si tiene licencia, Project Financial Planning o Service Demand Planning (consulte [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.") ).
2. En el menú de navegación de la izquierda, seleccione Configuración > Datos de referencia > Pool de trabajo externo o Pool de trabajo interno.
3. Seleccione ![imagen](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo.
4. Abra el archivo.csv descargado y actualice los valores de los datos según sea necesario:
   - Código (obligatorio) - Identificador único abreviado de la bolsa de trabajo.
   - Nombre (obligatorio) - Nombre de la bolsa de trabajo.
   - Código de departamento (sólo bolsa de trabajo interna) - El departamento asociado a la bolsa de trabajo interna.
   - Categoría - Utilice esta columna para ampliar el tipo de bolsa de trabajo. Ejemplos de categorías son Desarrollo, Garantía de calidad y Gestión de proyectos.
   - Tarifa - Tarifa horaria de una persona de la bolsa de trabajo.
   - Proveedor (sólo bolsa de trabajo externa) - El proveedor asociado a la bolsa de trabajo.
   - Pool por defecto (sólo pool de trabajo interno) - El pool de trabajo que se utilizará para las asignaciones directas por departamento. Sólo puede seleccionar una bolsa de trabajo por departamento.
   - Código de moneda - La moneda común para la bolsa de trabajo. Requerido cuando el soporte para múltiples monedas está habilitado en el Perfil de la Empresa. El valor de la moneda común del departamento debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
5. Ahora, Configuración > Pool de trabajo externo o Pool de trabajo interno y, a continuación, importe el archivo.csv actualizado.

## Gestionar los datos de referencia de las tarifas laborales

Un Administrador o Propietario de Proceso Presupuestario puede establecer tarifas laborales tanto para recursos laborales internos como externos. Estas tarifas de mano de obra pueden vincularse a las dimensiones Función, Ubicación y Proveedor.

Las tarifas de mano de obra proporcionan los valores por defecto de la tarjeta de mano de obra, como la compensación anual por rol de mano de obra. Estos valores por defecto se aplican a trabajadores específicos y pueden personalizarse directamente por trabajador. Véase [Crear un plan de trabajo](create-labor-plan.html). Las tarifas laborales de los recursos laborales internos procederán probablemente de su sistema de recursos humanos. Para los recursos laborales externos, como los proveedores, el proveedor debe proporcionar los datos de su tarjeta laboral basada en funciones en un formato que usted pueda utilizar.

1. Habilite las funciones de planificación laboral (véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.") ).
2. En el menú de navegación de la izquierda, seleccione Configuración > Datos de referencia > Tarifas de mano de obra.
3. Seleccione ![imagen](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo.
4. Abra el archivo.csv descargado y actualice los valores de los datos según sea necesario:
   - Tipo de empleado - Determina si esta regla se aplica a recursos laborales internos o externos (como proveedores o contratistas).
   - Rol - Las opciones disponibles para esta dimensión son proporcionadas por los datos de referencia de Roles.
   - Ubicación - Las opciones disponibles para esta dimensión vienen dadas por los datos de referencia de Ubicación.
   - Proveedor - Las opciones disponibles para esta dimensión vienen dadas por los datos de referencia del proveedor.
   - Código de moneda - La moneda común para la asignación laboral. Requerido cuando se activa el soporte para múltiples monedas. El valor de la moneda común del departamento debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Tasa Base - La tasa de compensación laboral por defecto.
5. Ahora, Configuración > Datos de referencia > Tarifas laborales y, a continuación, seleccione ![imagen](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla. Ahora seleccione Importar e importe el archivo.csv actualizado.
6. Seleccione ![imagen](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) y seleccione Publicar para que las tarifas de mano de obra estén disponibles en la planificación y la gestión de gastos. Después de publicar las tarifas de mano de obra, puede tener en cuenta los ajustes planificados de estas tarifas para recursos de mano de obra específicos (véase [Gestionar dimensiones personalizadas](manage-custom-reference.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ).

## Gestionar los datos de referencia de las funciones

Las funciones son títulos descriptivos que se aplican a los recursos laborales. Los valores de función que se asignan a los recursos de mano de obra son los valores de búsqueda clave en las tablas de tarifas de mano de obra.

1. Habilite las funciones de planificación laboral (véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.") ).
2. En el menú de navegación de la izquierda, seleccione Configuración > Datos de referencia > Función.
3. La tabla de datos de referencia de rol incluye el nombre del rol de recurso. No puede editar directamente los valores de la tabla Roles. En su lugar, seleccione ![imagen](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) en la esquina superior derecha de la tabla, seleccione Exportar > Exportar todo. Abra el archivo.csv descargado y actualice los datos de las funciones, y cargue y publique el archivo.csv según sea necesario.

- **[Reglas de Asignación de Mano de Obra](../../it-planning/planning/manage-labor-allocation-rules.html)**  
   Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles Admin o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.
- **[Calendarios de trabajo](../../it-planning/planning/configure-working-days.html)**
- **[Resumir Finanzas Laborales](../../it-planning/planning/labor-summarization.html)**  
   Los usuarios administradores pueden especificar cómo quieren que se resuman sus partidas financieras laborales en la pestaña Resumen. En otras palabras, un usuario administrador puede especificar qué columnas de datos de la pestaña Trabajo aparecerán en la pestaña Resumen.
- **[Ajustes](../../it-planning/planning/plan-labor-compensation.html)** a la Remuneración Laboral  
   Proceso Presupuestario Los propietarios o usuarios con permisos de propietario para un Objeto de Coste pueden contabilizar los ajustes planificados a las tasas de remuneración laboral. Esto puede hacerse para el trabajo en curso o previsto. Puede especificar un cambio porcentual en la remuneración base por recurso laboral y la fecha en la que se hará efectivo el cambio.
