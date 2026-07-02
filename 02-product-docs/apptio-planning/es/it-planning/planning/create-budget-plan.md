---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Crear un plan o previsión presupuestaria"
breadcrumb: []
source_path: "it-planning/planning/create-budget-plan.html"
images:
  - "resources/images/icons/icon-settings_20x20.png"
  - "resources/images/it_planning_images/async-plan-create-1.jpg"
  - "resources/images/it_planning_images/async-plan-create-2.jpg"
  - "resources/images/it_planning_images/new-plan-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Crear un plan o previsión presupuestaria

## Acerca de esta tarea

Vea este vídeo de Apptio Education Services: [Creación y Apertura de Planes](https://community.ibm.com/community/user/viewdocument/creating-and-opening-plans-9-min "(se abre en una pestaña o una ventana nueva)").

## Crear un plan presupuestario

Un Propietario de Proceso Presupuestario crea un nuevo plan presupuestario al principio del ciclo de planificación.

1. Seleccione Planning > Planes > ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-plan-icon.jpg).
2. En Tipo de plan, seleccione Presupuesto.
3. Introduce lo siguiente:

   | Elemento | Descripción |
   | --- | --- |
   | Año de inicio del plan | Seleccione el año para el nuevo presupuesto (normalmente, el año fiscal). La definición depende de la configuración de su calendario fiscal.  Para más información, consulte [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). |
   | Duración del plan (años) | Seleccione la duración del plan.  Para más información, consulte [Planificar para varios años](plan-multiple-years.html "Utilice las funciones de planificación plurianual para planificar y realizar el seguimiento de sus finanzas de TI en un horizonte temporal continuo y plurianual. Puede respaldar planes a largo plazo y previsiones continuas más allá de los límites del ejercicio fiscal."). |
   | Referencia básica | Para incluir datos de referencia en su presupuesto, seleccione un plan presupuestario existente o una previsión anterior. Esto le permite obtener datos de referencia de diferentes ejercicios fiscales o planificar para varios años.  La creación de un plan a partir de la línea de base debería tener el siguiente comportamiento para diferentes tipos de datos: - Otras Finanzas, Demanda de Mano de Obra, Asignaciones de Mano de Obra - copiar valores periódicos basados en la fecha real del calendario, por ejemplo Ene FY18. - Gastos > Mano de Obra - para periodos con valores diferentes de null, se comporta igual que Otras Finanzas. Los periodos con valores nulos se rellenan utilizando los campos Fecha de inicio, Fecha de fin y Cantidad. - Contratos, Activos - generar todos los valores periódicos a partir de metadatos. - Contratos (Amortización Manual), Activos (Amortización Manual) - se comporta igual que Otras Finanzas.  Copia de códigos de partidas individuales  Si selecciona esta opción, puede elegir entre copiar los Códigos de Partida de la línea de base o generar nuevos Códigos de Partida para las partidas copiadas.  [Más información sobre los códigos de partidas individuales](line-item-codes.html)  Rellenar automáticamente los datos del plan  Esta opción aparece si el plan base no contiene las mismas fechas fiscales que el plan recién creado. La función Autocompletar datos del plan rellena los valores del periodo en el nuevo plan que estarían vacíos con el mismo valor para ese mes en el último año del plan base. Por ejemplo, Feb FY21 se copia en Feb FY22 y FY22.  - La función Autocompletar datos del plan no funciona para Gastos > Mano de obra. - Si el nuevo plan comienza en un ejercicio anterior al del plan base, los años precedentes tendrán en blanco los campos Otras finanzas y Demanda de mano de obra. Si ha activado Integrated Investment Planning  Los Grupos de Proyectos no se incorporan a un nuevo plan, sino que utilizan los últimos datos de referencia publicados. Los grupos de proyectos de un plan básico que no figuren en los últimos datos de referencia publicados no se transferirán al nuevo plan. |
   | Nombre del plan | Introduzca el nombre único del presupuesto.  Para ayudar a distinguir los planes presupuestarios de las previsiones en su lista de planes, indique el tipo de plan en el nombre. |
4. Seleccione Crear plan.

Una vez iniciada la creación del plan tras enviar el formulario Crear plan, se crea una nueva entrada en la página Planes con el nombre del nuevo plan y el estado se marca como Pendiente.

Nota: Si el estado de creación del plan es Pendiente, el plan no podrá seleccionarse ni desde la página de planes ni desde el selector de planes de otras páginas.

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/async-plan-create-1.jpg)

Una vez finalizada la creación del plan, se muestra el diálogo de tostado que indica que se ha completado la creación del plan. Ahora se puede seleccionar el plano desde la página de planos, así como desde el selector de planos de otras páginas.

![imagen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/async-plan-create-2.jpg)

Así, la creación del plan es ahora un proceso asíncrono.

La creación del plan, especialmente si se utiliza el plan base, puede tardar varios minutos si hay que copiar una gran cantidad de datos del plan base al nuevo plan. El proceso de creación de planes sincrónicos impide al usuario realizar otras tareas mientras se crea el plan. Este tiempo puede ser utilizado eficazmente por el administrador para realizar otras tareas en la aplicación de planificación hasta que se complete la creación del plan.

A partir del 4 de marzo de 2024 y de la versión 3.64, esta función estará disponible en todos los entornos principales. El proceso de creación de planes es ahora asíncrono. Puede iniciar el proceso de creación del plan, que seguirá ejecutándose en segundo plano, permitiendo al usuario realizar otras tareas.

Si Integrated Investment Planning está Activado, los proyectos se copiarán en el nuevo plan con uno de los siguientes métodos. Para obtener más información sobre Integrated Investment Planning, consulte [Introducción a Integrated Investment Planning](iip/gs-integrated-investment-planning.html).

- Crear plan sin plan base - Si está creando un plan sin plan base, los proyectos de la dimensión de datos de referencia "Proyecto" se añadirán en el plan.
- Crear plan con plan base - Si está creando un plan con un plan base, los proyectos del plan base se añadirán al nuevo plan.

Después de crear un plan presupuestario, haz lo siguiente:

1. Ajuste los valores de referencia (opcional).

   Para más información, consulte [Introducir datos financieros y ajustar los valores de referencia](enter-financial-details.html)
2. [Fijar objetivos financieros](set-financial-targets.html)
3. Abra el plan para que los propietarios del presupuesto puedan editar las partidas.

Para más información, consulte [Abrir un plan o una previsión.](open-plan-forecast.html "Después de crear un plan presupuestario o una previsión, ajuste opcionalmente los valores de referencia, fije los objetivos y abra el plan para que los propietarios del presupuesto puedan editar las partidas individuales. Los propietarios del presupuesto no pueden ver un plan cuando está en estado Nuevo. Al abrir un plan, se envía una notificación por correo electrónico a los propietarios del presupuesto y a todos los usuarios que tengan el permiso Editar y enviar asociado a los objetos de coste de ese plan.")

Los propietarios del presupuesto no pueden ver un plan cuando está en estado Nuevo. Al abrir un plan, se envía una notificación por correo electrónico a los propietarios del presupuesto y a todos los usuarios que tengan el permiso Editar y enviar asociado a los objetos de coste de ese plan. Véanse [los datos de referencia de los Permisos para Gestionar Objetos de Coste](manage-cost-object.html "Los Permisos de Objetos de Coste determinan qué usuarios pueden ver, editar, enviar o aprobar planes a nivel de Departamento (Objetos de Coste). Cada Departamento puede tener uno o más usuarios asignados con permisos de nivel de edición y, para las aprobaciones de varios niveles, permisos de nivel de aprobación.").

## Crear una previsión

Antes de crear una previsión, compruebe las dimensiones y atributos de los datos reales que desea incluir en la previsión.

Para comprobar las dimensiones y atributos de su empresa:

1. Seleccione ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png) > Perfil de la empresa.
2. Puede encontrar las dimensiones y atributos en Habilitar Capacidades > Resumir reales financieros hasta las siguientes dimensiones y/o atributos.

Para crear una previsión:

1. Seleccione Planning > Planes > ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-plan-icon.jpg).
2. En Tipo de plan, seleccione Previsión.
3. Introduce lo siguiente:

   | Elemento | Descripción |
   | --- | --- |
   | Año de inicio del plan | Seleccione el año para la nueva previsión (normalmente el año fiscal). La definición depende de la configuración de su calendario fiscal.  Para más información, consulte [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). |
   | Duración del plan (años) | Seleccione la duración del plan. |
   | Período inicial de previsión | Seleccione el mes para la nueva previsión. |
   | Referencia básica | si desea incluir datos de referencia en su previsión, en Base, seleccione un plan presupuestario existente o una previsión anterior. |
   | Nombre del plan | introduzca un nombre único para la previsión. |

   Se abre el cuadro de diálogo Nuevo plan.
4. Seleccione Crear plan.

Nota: Los datos reales se extraerán de la Gestión de gastos y se introducirán en el plan de previsiones por períodos. Los datos reales sólo aparecerán en la vista Gastos > Resumen. Para más información, consulte [Abrir y ver los datos reales](import-publish-actuals.html).Project Financial Planning -Integrated Investment Planning: Los datos reales sólo se mostrarán en todas las secciones del plan si el proyecto está aprobado. Los proyectos en estado Propuesto no tendrán datos reales en todas las secciones del plan.

Después de crear un plan de previsiones, haga lo siguiente:

1. Ajuste los valores de referencia (opcional).

   Para más información, consulte [Introducir datos financieros y ajustar valores de referencia](enter-financial-details.html).
2. [Fijar objetivos financieros](set-financial-targets.html)
3. Abra la previsión para que los Propietarios de Centros de Coste puedan editar las partidas.

Para más información, consulte [Abrir un plan o una previsión.](open-plan-forecast.html "Después de crear un plan presupuestario o una previsión, ajuste opcionalmente los valores de referencia, fije los objetivos y abra el plan para que los propietarios del presupuesto puedan editar las partidas individuales. Los propietarios del presupuesto no pueden ver un plan cuando está en estado Nuevo. Al abrir un plan, se envía una notificación por correo electrónico a los propietarios del presupuesto y a todos los usuarios que tengan el permiso Editar y enviar asociado a los objetos de coste de ese plan.")
