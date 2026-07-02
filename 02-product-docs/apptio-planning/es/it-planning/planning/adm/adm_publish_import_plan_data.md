---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Publicar datos del plan en Apptio Cálculo de costes"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctese a Apptio Costing"
source_path: "it-planning/planning/adm/adm_publish_import_plan_data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publicar datos del plan en Apptio Cálculo de costes

La publicación de datos del plan desde Apptio Planificación a Apptio Cálculo de costes le permite compartir datos definitivos sobre presupuestos y previsiones con su entorno de asignación y transparencia de costes. Gracias a las funciones integradas de integración y programación de Automated Data Management (ADM), puede exportar partidas financieras (finanzas, mano de obra, actividad laboral, contratos, activos) desde Planning e introducirlas directamente en Apptio Costing.

Nota: Estas tareas requieren el rol de administrador con el DataOrchestrationServiceFeatureFullAccess permiso.

Recuerde: La función automatizada Data Management (ADM) está habilitada

## Antes de empezar

Asegúrese de que se cumplan los siguientes requisitos previos:

- **Automatizado Data Management (ADM)** se aprovisiona en su entorno
- ADM está habilitado en Apptio Planificación:
  - Ve a **Configuración (⚙) → Perfil de la empresa.**
  - Seleccionar **Habilitar integración Data Management automatizada**
- **Los conjuntos de datos de integración de planificación** necesarios se instalan en Apptio Costing
- Tienes el rol de administrador con el **DataOrchestrationServiceFeatureFullAccess** permiso.

## Gestión de entidades

Antes de publicar los datos del plan, confirme que **la asignación automatizada Data Management → de entidades** está correctamente configurada para asignar las entidades Apptio de planificación a los conjuntos de datos de cálculo de Apptio costes adecuados.

1. Ve a **Configuración (⚙) → Automatizado Data Management**.
2. Navega hasta **Gestión de entidades**.
3. En la tabla **Entidad**, localice las entidades de planificación que desea publicar, como por ejemplo:
   - Presupuesto financiero
   - Previsión financiera
   - Presupuesto de activos
   - Previsión de activos
   - Presupuesto del contrato
   - Previsión contractual
   - Presupuesto laboral
   - Previsión laboral
   - Presupuesto de actividades laborales
   - Previsión de actividad laboral
4. Para cada entidad, asigne el **conjunto de datos de costes Apptio** correspondiente que recibirá los datos del plan publicado.
5. Seleccione **Actualizar** para guardar los cambios.

Más información: [Gestión de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(se abre en una pestaña o una ventana nueva)")

## Publicación manual

Para publicar manualmente los datos de un plan:

1. Abre el plan en Apptio Planificación.
2. Seleccione el plan deseado de la lista desplegable.
3. Seleccione la pestaña de gastos que desea publicar (por ejemplo: Mano de obra, Actividad laboral, Contratos, Activos, Resumen/Otros).
4. Haga clic en el **menú Acciones → Publicar en Apptio Costing...**
5. La solicitud de publicación se pone en cola y se procesa en segundo plano
6. Supervise el estado del trabajo de publicación a través de la página **Configuración (⚙) → Apptio** **Integración** **de costes → Estado.**

## Publicación programada

Para automatizar las exportaciones periódicas de datos del plan a Apptio Costing (por ejemplo, diarias, semanales o mensuales):

1. Vaya a **Configuración (⚙) → Automatizado → Data Management** **Programación de entidades** para navegar a la interfaz Data Management Automatizado.
2. Haga clic en **Añadir programación**. Conjunto:
   1. **Productor** : Apptio Planificación
   2. **Plan** : Selecciona el plan que deseas publicar
   3. **Entidades (tipos de partidas)** : Elija qué partidas incluir (presupuesto financiero, presupuesto de mano de obra, previsión de contratos, presupuesto de activos, etc.)
3. Defina el período de publicación (por ejemplo, mes actual, mes anterior, inicio del período fiscal o una fecha personalizada) y la frecuencia de programación (diaria, semanal, mensual).
4. Establezca la fecha y hora de inicio y, opcionalmente, la fecha de finalización. A continuación**, cree un calendario**.
5. Una vez configurado, ADM exportará y publicará automáticamente los datos del plan seleccionado en Costing en cada intervalo programado.

Los horarios se pueden editar o eliminar en cualquier momento a través de la misma página Entity Schedule (Horario de entidad) en ADM. Más información: [Publicación del calendario](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-schedule-plan-publishes "(se abre en una pestaña o una ventana nueva)").

**Tema principal:** [Conectarse a Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.")
