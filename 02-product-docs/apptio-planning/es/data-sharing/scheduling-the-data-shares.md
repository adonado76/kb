---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "data-sharing"
title: "El plan de programación se publica"
breadcrumb: []
source_path: "data-sharing/scheduling-the-data-shares.html"
images:
  - "resources/images/icons/icon-delete.png"
  - "resources/images/icons/icon_details.png"
  - "resources/images/icons/pencil-icon.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# El plan de programación se publica

## Capacidad del programador ADM

En Automated Data Management (ADM) se ha incorporado una función de programación para automatizar el intercambio de datos entre :

- Apptio Planning datos de los planes (presupuesto y previsiones) en Apptio Costing
- Cloudability en Apptio Costing.

Esta capacidad ofrecerá opciones flexibles para programar trabajos de publicación de datos de Plan y Cloudability en Apptio Costing y un lugar centralizado para gestionar el intercambio de datos entre la cartera de productos de Apptio.

Los usuarios administradores pueden ahora crear programaciones diarias, semanales y mensuales utilizando la integración Automated Data Management para publicar datos de Planes y Cloudability de cualquier plan activo en estado Nuevo, Abierto o Final en Apptio Costing (Transparencia de Costes). Además, también pueden seleccionar el periodo concreto en Apptio Costing para el que deben publicarse los datos.

![Capacidad Sceduler](../resources/images/data%20sharing_images/adm-scheduler-capability.png)

## Prerrequisito

- IT Planning, Automated Data Management, TBM Studio deben estar en el mismo entorno.

  ![Planificación informática, Automatización Data Management, TBM Studio](../resources/images/data%20sharing_images/same-env.png)
- Asegúrese de que el permiso DataOrchestrationServiceFeatureFullAccess está activado en el rol que gestionará los horarios de Automated Data Management . Por defecto, las funciones Admin, Apptio Admin y Apptio Partner tienen este permiso activado.
- [Conexión](data_sharing_connections.html) con el proyecto TBM Studio establecido en Automated Data Management
- Automated Data Management debe estar activada en Apptio Planning
- Apptio Planning [se](data_sharing_entity_mapping.html) crean y configuran en Automated Data Management

  ![Prerrequisito](../resources/images/data%20sharing_images/adm-prerequisite1.png)

  ![Prerrequisito](../resources/images/data%20sharing_images/adm-prerequisite2.png)

Nota:

Consulte la [guía de configuración de ADM](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-configure-automated-data-management "(se abre en una pestaña o una ventana nueva)") para configurar la integración entre Apptio Costing y Apptio
Planning.

## Configuración de la planificación para el cálculo de costes

Navegue a la página de Programación de la Entidad para crear, editar o borrar programaciones para publicar un Plan en el Cálculo de Costes. El proceso de creación de la planificación genera múltiples trabajos basados en las entidades seleccionadas y aplica la misma configuración de planificación para cada tipo/entidad de partida de planificación. Sin embargo, el usuario tiene la flexibilidad de gestionar las publicaciones a Cálculo de costes por separado para cada tipo de entidad/partida individual si es necesario.

Automated Data Management mantiene la correspondencia 1:1 entre el tipo de partida Apptio Planning y la entidad Automated Data
Management y el nombre del conjunto de datos en Apptio Costing. El nombre del conjunto de datos puede modificarse en Automated Data Management en función de la configuración del cliente.

Nota: Los desencadenantes manuales están disponibles para publicaciones ad hoc de datos del Plan y Cloudability a Costing.

| **Entidad ADM** | **Apptio Planning Tipo de partida** | **Apptio Costing Nombre por defecto del conjunto de datos** | Gatillo manual |
| --- | --- | --- | --- |
| Presupuesto financiero | Tipo de partida financiera en un tipo de plan presupuestario | Apptio PlanningF Presupuesto | Plan > Gastos > ficha Resumen > Acciones > Publicar datos financieros en Transparencia de costes... |
| Presupuesto laboral | Tipo de posición de trabajo en un tipo de plan presupuestario | Apptio PlanningF Presupuesto laboral | Plan > Gastos > Ficha Mano de Obra > Acciones > Publicar Mano de Obra en Transparencia de Costes... |
| Presupuesto | Línea de activo fijo Tipo de posición en un tipo de plan presupuestario | Apptio PlanningF Presupuesto de activos | Plan > Gastos > ficha Activos > Acciones > Publicar activos en Transparencia de costes... |
| Presupuesto | Tipo de partida contractual en un tipo de plan presupuestario | Apptio PlanningF Presupuesto contractual | Plan > Gastos > pestaña Contratos > Acciones > Publicar contratos en Transparencia de costes... |
| Presupuesto de actividades laborales | Tipo de partida individual de actividad laboral en un tipo de plan presupuestario | Apptio PlanningF Presupuesto de actividades laborales | Plan > Gastos > Ficha Actividad Laboral > Acciones > Publicar Actividad Laboral en Transparencia de Costes... |
| Previsión financiera | Tipo de partida financiera en un tipo de plan de previsión | Apptio PlanningF Previsión financiera | Plan > Gastos > ficha Resumen > Acciones > Publicar datos financieros en Transparencia de costes... |
| Previsión laboral | Línea de trabajo Tipo de posición en un tipo de plan de previsión | Apptio PlanningF Previsión laboral | Plan > Gastos > Ficha Mano de Obra > Acciones > Publicar Mano de Obra en Transparencia de Costes... |
| Previsión de activos | Tipo de partida individual de activo fijo en un tipo de plan de previsión | Apptio PlanningF Previsión de activos | Plan > Gastos > ficha Activos > Acciones > Publicar activos en Transparencia de costes... |
| Previsión de contratos | Tipo de partida individual de contrato en un tipo de plan de previsión | Apptio PlanningF Previsión de contratos | Plan > Gastos > pestaña Contratos > Acciones > Publicar contratos en Transparencia de costes... |
| Previsión de la actividad laboral | Tipo de partida individual de actividad laboral en un tipo de plan de previsión | Apptio PlanningF Previsión de la actividad laboral | Plan > Gastos > Ficha Actividad Laboral > Acciones > Publicar Actividad Laboral en Transparencia de Costes... |

## Crear un calendario para la planificación

1. Vaya a **Enhanced Access Administration** y seleccione **Automated Data Management**
2. Seleccione **Programa de Entidades** en el panel de la izquierda
3. Seleccione **Add Schedule** ( ApptioOne Planning está seleccionado por defecto en la opción Producer)
4. Introduzca el nombre del programa en el campo **Nombre del programa**

   ![Añadir horario](../resources/images/data%20sharing_images/add-schedule1.png)
5. Seleccione el **nombre del plan** en el menú desplegable para crear la programación
6. Seleccione las **entidades** que desea programar (en función del presupuesto o plan de previsiones seleccionado, se actualizarán las entidades disponibles)

   ![Añadir horario](../resources/images/data%20sharing_images/add-schedule2.png)
7. Establezca el periodo de tiempo en CT que desea publicar
   - Mes actual: Este valor dinámico cambiará a medida que avance en el tiempo. Eg.when Si se selecciona el mes de julio, los datos de Plan y Cloudability se publicarán en el mes de julio en TBM Studio.
   - Mes anterior: Este valor dinámico cambiará a medida que avance en el tiempo. Por ejemplo, Si se elige esta opción, cuando el mes actual sea julio, los datos de Plan y Cloudability se publicarán en el mes de junio en TBM Studio.
   - Mes de inicio del año fiscal: Este valor dinámico cambiará a medida que avance en el tiempo. Por ejemplo, cuando se fije el mes de julio como inicio del año fiscal, los datos del Plan y de Cloudability se publicarán en el mes de julio en TBM Studio.
   - Personalizar: El plan se publicará en el mes de la fecha seleccionada. Esta opción se utiliza cuando el inicio del año fiscal del Plan es diferente al inicio del año fiscal en TBM Studio
8. Seleccione **Siguiente** para configurar la cadencia de programación
9. Seleccione el **tipo de programación** (diaria, semanal o mensual)
10. Seleccione la **Fecha de inicio** y la **Fecha de finalización** de la programación. Si se selecciona **Sin fecha final**, el campo **Fecha final** estará desactivado
11. Establezca la frecuencia para activar el trabajo
    - Seleccione una o varias veces al día
    - Seleccione una o varias veces por semana
    - Seleccione uno o varios días del mes
12. Seleccione la **hora** y la **zona horaria** para activar el trabajo
13. Seleccione **Crear horario**

## Editar planificación

1. Ir a **Enhanced Access Administration** y **Automated Data Management**
2. Seleccione el menú **Programación de Entidades** del panel izquierdo
3. Seleccione el icono del lápiz (![Editar icono](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) para editar la programación
4. Editar el plan y programar los detalles según sea necesario
5. Seleccione **Guardar horario**

   ![Guardar horario](../resources/images/data%20sharing_images/edit-schedule-new.png)

## Borrar horario

1. Ir a **Enhanced Access Administration** y **Automated Data Management**
2. Seleccione el menú **Programación de Entidades** del panel izquierdo
3. Seleccione el icono del lápiz (![Editar icono](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) para borrar la programación
4. Seleccione el icono Eliminar (![Icono Eliminar](../../../../03-media/apptio-planning/resources/images/icons/icon-delete.png)) y, a continuación, seleccione **Eliminar** en la ventana emergente de confirmación

## Comprobación de estado

1. Ir a **Enhanced Access Administration** y **Automated Data Management**
2. Seleccione el menú **Programación de Entidades** del panel izquierdo
3. Seleccione el icono de notas (![Icono Notas](../../../../03-media/apptio-planning/resources/images/icons/icon_details.png)) para ver los detalles sobre *el estado de la Programación* y el *Historial de Ejecuciones*

   ![Estado de planificación](../resources/images/data%20sharing_images/status-schedule.png)

## Creación de un calendario para Cloudability

1. Vaya a **Enhanced Access Administration** y seleccione **Automated Data Management**
2. Seleccione **Programa de la entidad** > **Detalles de la entidad** en el menú de la izquierda
3. Haga clic en el botón **Añadir horario**.
4. Introduzca el **Nombre de la Programación**.
5. Seleccione el **tipo de programación** (diaria, semanal o mensual).

   Intro

   | **Frecuencia** | **Lo mejor para** | **Ejemplo de uso** |
   | --- | --- | --- |
   | Diariamente | Control de costes en tiempo real | FinOps equipos de seguimiento del gasto diario |
   | Semanalmente | Informes periódicos | Revisiones semanales de costes con las partes interesadas |
   | Mensualmente | Seguimiento presupuestario | Informes financieros mensuales |
   | Personalizada | Necesidades empresariales específicas | Alineación con los ciclos de facturación |
6. Seleccione la **Fecha de inicio** y la **Fecha de finalización** de la programación. Si se selecciona **Sin fecha final**, el campo **Fecha final** estará desactivado.
7. Seleccione los valores adecuados en los campos **Hora** y **Zona horaria** para activar el trabajo.
8. Seleccione **Siguiente** para configurar la cadencia de programación.
9. Haga clic en el botón **Crear horario**.

Nota: Algunas buenas prácticas a tener en cuenta al programar -

- Establezca el horario en horas valle, preferiblemente a primera hora de la mañana.
- Asegúrese de que el horario coincide con su zona horaria local.
- Deje tiempo suficiente para el tratamiento de los datos antes del inicio de las operaciones comerciales.

Importante: Son aplicables las siguientes restricciones del sistema:

- Sólo se permite un horario activo por entorno.
- Cada proveedor de nube sólo puede tener un plan de ejecución por horario.

**Tema principal:** [Conectarse a Apptio Cálculo de costes](../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.")
