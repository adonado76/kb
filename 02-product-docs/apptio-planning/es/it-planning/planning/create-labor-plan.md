---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Editar partidas de mano de obra"
breadcrumb: []
source_path: "it-planning/planning/create-labor-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Editar partidas de mano de obra

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario del Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Los detalles de mano de obra del personal planificado tienen en cuenta los costes de mano de obra anticipados relacionados con las próximas contrataciones o compromisos internos o externos, y están sujetos a cualquier regla de cálculo de costes de mano de obra que se haya establecido. Consulte [los datos de referencia de Gestión de la configuración de mano de obra](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario del Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor."). La gestión de los detalles laborales del personal planificado le permite hacer lo siguiente:

- Modelizar e informar sobre los costes de mano de obra previstos para todo el periodo de planificación.
- Siga las normas de cálculo de costes laborales aplicables para que los costes laborales planificados se desglosen y proyecten en los códigos de cuenta correctos del libro mayor durante todo el periodo de planificación.

## Antes de empezar

Antes de empezar, asegúrese de activar las funciones de planificación laboral. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

## Introducir datos laborales

Apptio le recomienda que actualice periódicamente los datos del parto previsto con nueva información. Trabaje con detalles de mano de obra planificada en la pestaña Mano de obra, página Planificada. Después de que un recurso de mano de obra planificada haya empezado a incurrir en costes, contabilícelos mediante la partida de Mano de obra existente y elimínelos de las partidas Planificadas. Véase [Introducir o importar datos de partidas individuales](enter-import-line.html "Carga masiva de datos cargando un CSV en su plan financiero.").

1. En los menús de plan de la parte superior derecha, seleccione un plan, una categoría de objeto de coste y un objeto de coste o grupo de objetos de coste.

   [Más información sobre la navegación en Planificación](navigate-apptio-planning.html "Este tema ofrece una visión general de cómo está organizada la navegación de planificación de Apptio. Los elementos de menú que aparecen en su cuenta dependen de sus permisos de usuario.")

   Nota: Los Propietarios de Centros de Coste sólo pueden editar sus Centros de Coste asignados. Véanse [los datos de referencia de los Permisos para Gestionar Objetos de Coste](manage-cost-object.html "Los Permisos de Objetos de Coste determinan qué usuarios pueden ver, editar, enviar o aprobar planes a nivel de Departamento (Objetos de Coste). Cada Departamento puede tener uno o más usuarios asignados con permisos de nivel de edición y, para las aprobaciones de varios niveles, permisos de nivel de aprobación.").
2. Vaya a Planning > Gastos.
3. Seleccione la pestaña Trabajo.
4. Seleccione las subpestañas Planificado o Existente.
5. Introduzca valores, importe un.csv (NOTA : Introduzca FALSE para el valor Es empleado existente para indicar que un recurso está planificado en lugar de actual) o edite los detalles laborales en las siguientes columnas:
   - Objeto de Coste - Identificador único por Objeto de Coste, organizado en filas correspondientes a cada tipo de Objeto de Coste (Departamentos, Servicios y Proyectos). Los propios datos de referencia de los objetos de coste pueden organizarse en relaciones jerárquicas padre e hijo entre departamentos y, si están habilitados, servicios y proyectos.
   - Asignaciones - Le permite asignar mano de obra a un proyecto, Servicio o pool de trabajo (ver [Asignar mano de obra de departamento](allocate-department-labor.html) ).
   - Tipo de empleado - Determina si esta regla se aplica al personal interno o a los recursos laborales externos, como proveedores o contratistas.
   - Rol - Proporciona las opciones disponibles proporcionadas por los datos de referencia Roles.
   - Ubicación - Proporciona las opciones disponibles proporcionadas por los datos de referencia de Ubicación.
   - Vendedor - Determina las opciones disponibles proporcionadas por los datos de referencia del vendedor.
   - Nombre del empleado - El nombre de un recurso laboral específico, si se conoce, u otro identificador único. Para varias personas, puede realizar un seguimiento agregado e introducir un nombre de equipo o función, por ejemplo, Equipo de control de calidad.
   - Divisa - Visible sólo cuando están habilitadas múltiples divisas (ver [Soporte para múltiples divisas](support-multiple-currencies.html)).
   - Remuneración base - Valor del salario base anual de este recurso laboral. Tenga en cuenta lo siguiente:
     - Este valor puede ser el salario bruto previsto de una persona, el salario medio de un equipo de varias personas u otro valor.
     - Este valor se convierte en la base para los cálculos de las reglas laborales. Si trabaja con un equipo de varias personas, el valor de la Remuneración Base debe ser el valor medio por persona (no la suma del equipo). El valor medio por persona multiplicado por el valor de la cantidad dará como resultado el valor del coste global del equipo.
     - El importe de la remuneración básica y el valor de la cantidad (1 para un único recurso) producen los valores de remuneración mensuales distribuidos por línea de trabajo, que a su vez producen acumulativamente el valor total de la remuneración básica para el período de planificación anual.
     - En la página Gastos, pestaña Resumen, los valores de compensación mensuales por línea de mano de obra se ejecutan a través de las reglas de cálculo de costes de mano de obra, se asignan y se cargan a las cuentas correctas del libro mayor por mes aplicable (véase [Gestionar datos de referencia de mano de obra](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario del Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ). La suma de los gastos resultantes de una determinada línea de mano de obra OpEx representa la tasa de mano de obra cargada de ese recurso laboral.
   - Cantidad - Para una asignación individual de recursos laborales a tiempo completo, introduzca 1. Para asignaciones fraccionarias de un recurso a un Centro de costes, introduzca un valor decimal (por ejemplo, 0,5 para una asignación de media jornada). Para una asignación de recursos de mano de obra que represente a varias personas, introduzca la suma de efectivos prevista.
   - Fechas de inicio y fin - Estas fechas determinan las asignaciones iniciales por mes del recurso laboral en el período de planificación actual. Puede introducir fechas anteriores o posteriores al calendario fiscal activo, pero sólo se calcularán las habilitaciones dentro del calendario fiscal activo. El calendario fiscal se define en el Perfil de la Empresa (ver [Editar el Perfil de la Empresa)](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). Para los meses dentro del calendario fiscal activo, pero no dentro del intervalo de fechas establecido, la aplicación Apptio Planning pondrá a cero las asignaciones de recursos.
   - Descripción - Introduzca una descripción de texto para este recurso laboral. Es el mismo valor de Descripción que aparece en la tabla OpEx Partidas.
   - Tasa de Actividad Laboral - Este campo es aplicable si está utilizando el módulo de Planificación de la Actividad Laboral en Project Financial Planning (PFP). En Configuración > Esquema y exportación.csv el nombre de la columna correspondiente es Tasa de mano de obra. El valor de la Tasa de mano de obra se establece automáticamente según los datos de referencia de la Tasa de actividad laboral del Departamento. En caso de que el valor no esté configurado en los datos de referencia, este campo aparecerá en blanco. El valor de este campo puede ser sustituido por el valor introducido por el usuario. Este valor indica la tarifa laboral por hora cobrada por el proyecto cuando el recurso correspondiente se asigna al proyecto.
6. Añada los ajustes de compensación laboral, tal como se describe [aquí](plan-labor-compensation.html "Los Propietarios del Proceso Presupuestario o los usuarios con permisos de propietario para un Objeto de Coste pueden contabilizar los ajustes planificados a las tasas de compensación laboral. Esto puede hacerse para el trabajo en curso o previsto. Puede especificar un cambio porcentual en la remuneración base por recurso laboral y la fecha en la que se hará efectivo el cambio.").

## Asignaciones de mano de obra por mes

El calendario mensual a la derecha de la tabla de partidas de mano de obra muestra los recuentos mensuales de asignaciones de recursos por partida de mano de obra. En la columna de la derecha de la tabla se muestran los costes totales de mano de obra por línea de mano de obra y, en la parte inferior derecha, el coste total de mano de obra.

Las asignaciones iniciales de recursos por línea de mano de obra se calculan mediante el valor Cantidad por mes para cada mes dentro del intervalo de Fecha de inicio y Fecha de finalización. Puede editar o contornear manualmente las asignaciones mensuales de recursos.

Introduzca la asignación de recursos por partida del libro mayor por mes natural que desee. Al hacerlo, se actualizará el Coste total de recursos de la partida seleccionada y el recuento mensual.

Sugerencia:

- Al igual que con otras vistas de elementos de línea, puede añadir o eliminar columnas. Sitúe el cursor del ratón en el encabezamiento de la columna, haga clic en el botón de flecha que aparece y seleccione una opción.
- Para añadir nuevas partidas, sitúe el cursor del ratón en la columna más a la izquierda de una fila, haga clic en el botón de flecha que aparece y seleccione una opción.

## Ver los costes de los proyectos delegados

Si Project Financial Planning Project Financial Planningestá activado, los Propietarios de Proyecto pueden delegar los costes del proyecto a los propietarios de departamentos y servicios. Todos estos propietarios pueden mostrar u ocultar los costes delegados de sus finanzas. Véase [Delegar los costes del proyecto](pfp/delegate-project-costs.html).

## Ver la demanda de mano de obra

Si Project Financial Planning o Service Demand Planning están activados, puede hacer que la mano de obra esté disponible para el trabajo del proyecto o servicio a través de pools de recursos de mano de obra y asignaciones. Los Propietarios de Departamento pueden asignar a un proyecto, servicio o bolsa de trabajo. Estas asignaciones departamentales también aparecen en las tablas de asignación de mano de obra de sus proyectos y servicios. Véase [Asignar el trabajo del departamento](allocate-department-labor.html).

## Ver el coste de la mano de obra totalmente cargada

Los propietarios del presupuesto ahora pueden ver fácilmente el coste de mano de obra totalmente cargado directamente en las columnas Gastos > Mano de obra > Total del ejercicio, eliminando la necesidad de navegar hasta la sección Gastos > Resumen para obtener esta información. Anteriormente, esta columna sólo mostraba la Remuneración Base x Cantidad.

Por ejemplo, en la pestaña Mano de obra, puede ver una línea de mano de obra con un total de 196.888 USD en FY24. Este importe representa el coste de mano de obra totalmente cargado, calculado sobre la base de las normas de asignación de mano de obra configuradas.

![img](../../resources/images/it%20planning_images/3.71-1.png)

El coste de mano de obra totalmente cargado es la suma de las cuentas del libro mayor generadas a partir de Reglas de asignación de mano de obra en la pestaña Resumen. Como se muestra, el total de FY24 en la pestaña Resumen coincide con el total de FY24 en la pestaña Mano de obra.

![img](../../resources/images/it%20planning_images/3.71-2.png)
