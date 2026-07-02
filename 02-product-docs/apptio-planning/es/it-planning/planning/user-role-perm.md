---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Funciones y permisos de los usuarios"
breadcrumb:
  - "Planning"
  - "cómo empezar"
source_path: "it-planning/planning/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Funciones y permisos de los usuarios

Los roles y permisos de usuario controlan quién puede acceder, editar y gestionar datos en Apptio Planning. Los roles definen el nivel de acceso dentro de la aplicación, mientras que los permisos proporcionan un control más granular sobre tareas específicas.

## Funciones de usuario estándar

Apptio La planificación incluye cinco roles de usuario predefinidos:

1. **Administrador**
   1. Acceso completo a todas las funciones de Apptio Planning.
   2. Incluye permisos administrativos en otras aplicaciones de Apptio a través de FrontDoor.
2. **Propietario del proceso presupuestario**
   1. Acceso completo a todas las funciones de Apptio Planning.
   2. Normalmente se encarga de coordinar el ciclo presupuestario y gestionar los ciclos de vida de los planes.
3. **Propietario del centro de costes**

   1. Pueden editar los gastos de los Departamentos a los que están asignados.
   2. Útil para los contribuyentes al presupuesto a nivel de departamento.
4. **Gestor de proyectos de la PII**
   1. Pueden editar los gastos de los Proyectos a los que están asignados en la Planificación Integrada de Inversiones (PII).
   2. Centrado en la gestión de las finanzas individuales a nivel de proyecto.
5. **Gestor de cartera de la PII**
   1. Puede editar los gastos de los proyectos asignados en la PII.
   2. También puede conceder permisos a los usuarios sobre los proyectos y crear nuevos proyectos.
   3. Normalmente supervisa una cartera de proyectos y asigna permisos.

## Roles personalizados

Además de los roles estándar, puede crear **roles personalizados** en **FrontDoor**. Las funciones personalizadas le permiten adaptar el acceso a las necesidades específicas de su organización.

## Permisos

La siguiente tabla enumera los permisos disponibles y sus descripciones:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Nombre del permiso** | **Descripción** | **Administrador** | **Propietario del proceso presupuestario** | **Propietario del centro de costes** | **Gestor de proyectos de la PII** | **Gestor de cartera de la PII** |
| ApiCanReadData | Permite acceder a los datos de la tabla a través de la API. Necesario para la integración de la transparencia de costes. | x |  |  |  |  |
| CanComment | Permite añadir y visualizar comentarios a nivel de plano. | x | x | x | x | x |
| canEditExternalCode | Concede permiso para editar códigos externos. | x |  |  |  |  |
| CompanyProfileConfig | Permite ver y editar la configuración del perfil de la empresa. | x |  |  |  |  |
| CTIConfig | Permite ver y editar la configuración de la Integración de la Transparencia de Costes. | x | x |  |  |  |
| DataOrchestrationServiceFeatureFullAccess | Proporciona acceso completo a todos los puntos finales/acciones del Servicio de Orquestación de Datos. Necesario para automatizar Data Management. | x |  |  |  |  |
| EditPlanning | Concede permiso para ver y editar planes. | x | x | x | x | x |
| EditReferenceData | Permite editar, importar y publicar datos de referencia. | x | x |  |  |  |
| EditRestrictedDimensions | Permite editar dimensiones y atributos configurados con acceso restringido. | x | x |  |  |  |
| ExternalLineEdit | Concede permiso para editar elementos de línea externos. | x | x |  |  |  |
| IIPProjectExpenseEdit | Concede permiso para ver y editar las partidas del proyecto. También permite editar proyectos en la Lista de proyectos. |  |  |  | x |  |
| IIPProjectManage | Ofrece funciones completas de gestión de proyectos: crear y eliminar proyectos, editar datos de atributos y gestionar los gastos de todos los proyectos de un plan. | x | x |  |  |  |
| IIPProjectPermissionManage | Permite acceder a la página de permisos del proyecto. | x | x |  |  | x |
| ITPCompensationAdjustmentAllPeriodsEdit | Permite editar los ajustes de las retribuciones laborales para todos los periodos del plan. | x | x |  |  |  |
| ITPCompensationAdjustmentEdit | Permite editar los ajustes de compensación laboral sólo para los ciclos de compensación definidos. | x | x | x |  |  |
| ITPPlanSettingsEdit | Concede permiso para editar las páginas de Configuración del Plan. | x | x |  |  |  |
| ITPPlanSettingsView | Concede permiso para ver (pero no editar) las páginas de Configuración del Plan. |  |  |  |  |  |
| ManagePlans | Permite crear, archivar y eliminar planes. | x | x |  |  |  |
| ManageUsers | Concede acceso completo para gestionar las funciones y los permisos de los usuarios en la consola Access Administration. | x |  |  |  |  |
| ViewAssets | Concede visibilidad a la pestaña Activos y permite editar los detalles de las partidas de los activos. | x | x | x | x | x |
| ViewChangeHistoryFeatureViewOnly | Otorga visibilidad al registro de eventos del historial de cambios | x | x |  |  |  |
| ViewContracts | Concede visibilidad a la pestaña Contratos y permite editar los detalles de las partidas de los contratos. | x | x | x | x | x |
| ViewLabor | Concede visibilidad a la pestaña Mano de obra y permite editar los detalles de las partidas de mano de obra. | x | x | x | x | x |
| ViewPlanning | Permite ver los planos, pero no editarlos. | x | x | x | x | x |
| ViewReferenceData | Permite ver pero no editar los datos de referencia. | x | x |  |  |  |
| ViewSpendManagement | Permite la visualización pero no la edición de los reales en la Gestión de gastos. | x | x | x | x | x |
| ViewCloud | Permite ver y editar líneas en la pestaña Nube | x | x | x | x | x |
| CanImporFromCloudability | Proporciona acceso para importar datos desde Cloudability a la pestaña Cloud y para eliminar elementos de línea importados desde Cloudability. | x | x |  |  |  |
| *ITPPredictiveForecastingFeatureFullAccess* | Ofrece acceso completo para generar y consultar previsiones en la planificación. | x | x | x |  |  |

## Permisos para objetos de coste

Los permisos de objetos de coste determinan qué usuarios pueden ver, editar, enviar o aprobar planes a nivel de departamento. Sólo los usuarios con el rol de **Propietario del Centro de Coste** pueden tener asignado el acceso al departamento. Los usuarios con funciones de **Administrador** o **Propietario del proceso presupuestario** tienen acceso automáticamente a todos los departamentos de forma predeterminada. El acceso de los usuarios se gestiona a nivel de plan a través de **Plan** → **Configuración** → **Permisos de usuario.**

Consulte [«Permisos de objetos de coste»](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(se abre en una pestaña o una ventana nueva)") para obtener más información.

## Permisos del proyecto

Los permisos del proyecto determinan qué usuarios pueden ver o editar los gastos del proyecto. Sólo los usuarios con el rol de **Gerente de cartera de IIP** o **Gerente de proyecto de IIP** son elegibles para que se les asigne acceso al proyecto. Los usuarios con funciones de **Administrador** o **Propietario del proceso presupuestario** tienen acceso automáticamente a todos los departamentos de forma predeterminada. El acceso de los usuarios se gestiona a nivel de plan a través de **Plan** → **Proyectos** → **Permisos.**

Consulte [Permisos del proyecto](iip/project-level-access-control.html) para obtener más información. =
