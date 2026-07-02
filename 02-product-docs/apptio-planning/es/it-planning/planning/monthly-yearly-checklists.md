---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Listas de control mensuales y anuales para administrar la Planificación"
breadcrumb: []
source_path: "it-planning/planning/monthly-yearly-checklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Listas de control mensuales y anuales para administrar la Planificación

◆ Se aplica a: Planning administración. Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Utilice esta lista de comprobación como guía para el mantenimiento de su solución de Planificación.

Nota: Esta lista de comprobación no abarca todos los elementos operativos de todos los escenarios posibles. Su objetivo es facilitar los procedimientos operativos de una solución de configuración típica. Todos los elementos de la lista de control tienen enlaces a instrucciones detalladas.

## Lista de control mensual

- [Importar y publicar datos reales](import-publish-actuals.html)
- [Crear un plan o previsión](create-budget-plan.html) y notificar a los Propietarios de Departamento el periodo de entrada
- [Integrar con transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.")

## Lista de control anual

- [Configure los ajustes de tiempo del proyecto](../../studio/admin/configure-project-time.html "Se aplica a: TBM Studio 12.0 y posteriores. Las opciones que aparecen en el cuadro de diálogo Configurar ajustes de hora del proyecto dependen del tipo de calendario que seleccione.") en Costing Standard.
- Actualice los datos de referencia con la información de la nueva organización. Las dimensiones incorporadas son gestionadas por los Administradores o los Propietarios de Procesos Presupuestarios. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ).
  - Actualice Cuentas, Centros de Coste, Departamentos, Ubicación y Proveedores (véase [Gestionar datos financieros de referencia](manage-financial-dimensions.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ).
  - Actualice los pools de mano de obra externos e internos, las reglas de asignación de mano de obra, las tarifas de mano de obra y las funciones (consulte [Gestionar datos de referencia de mano de obra](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ).
  - Actualice los tipos de contrato y los tipos de IVA (véase [Gestionar los datos de referencia de los contratos](manage-contract-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ).
  - Actualice la clase de activo (consulte [los datos de referencia de Gestionar clase de activo](manage-asset-configuration.html) ).
  - Actualizar permisos de objetos de costo (consulte [los datos de referencia Administrar permisos de objetos de costo](manage-cost-object.html "Los Permisos de Objetos de Coste determinan qué usuarios pueden ver, editar, enviar o aprobar planes a nivel de Departamento (Objetos de Coste). Cada Departamento puede tener uno o más usuarios asignados con permisos de nivel de edición y, para las aprobaciones de varios niveles, permisos de nivel de aprobación.") )
  - Si admite varias monedas, actualice los tipos de moneda real y plan (véase [Datos de referencia de las tablas de tipos de conversión de moneda](manage-multi-currency.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") ).
  - Si [Project Financial Planning está activado](pfp/gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera."), actualice el Proyecto y el Grupo de Proyectos (véase [Gestionar los datos de referencia del Proyecto](pfp/manage-project-configuration.html) ).
- [Crear un plan o previsión](create-budget-plan.html).
- [Introduzca los datos financieros y ajuste los valores de referencia](enter-financial-details.html).
- [Abrir un plano o una previsión](open-plan-forecast.html "Después de crear un plan presupuestario o una previsión, ajuste opcionalmente los valores de referencia, fije los objetivos y abra el plan para que los propietarios del presupuesto puedan editar las partidas individuales. Los propietarios del presupuesto no pueden ver un plan cuando está en estado Nuevo. Al abrir un plan, se envía una notificación por correo electrónico a los propietarios del presupuesto y a todos los usuarios que tengan el permiso Editar y enviar asociado a los objetos de coste de ese plan.").
- Notificar a los Propietarios de Departamento un período de entrada en el presupuesto (fecha de inicio y fin).
- [Cree un plan de trabajo](create-labor-plan.html).
- [Revisar, aprobar o devolver planes u Objetos de Coste](review-approve-return.html).
- [Integración con la transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.").

VEA TAMBIÉN : A medida que actualice los datos de referencia, los siguientes artículos pueden resultarle útiles:

- [Gestionar los datos de referencia para la Planificación](manage-itfmf-reference.html "◆ Se aplica a: Planificación")
- [Forzar un plan para utilizar datos de referencia actualizados](force-plan-use.html)
