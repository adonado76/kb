---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Funciones y permisos en Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
source_path: "admin/iam.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Funciones y permisos en Cloudability

Los roles otorgan a los usuarios permiso para acceder a vistas y funciones específicas dentro de Cloudability.

De forma predeterminada, todos los roles de usuario tienen acceso a algunas funciones básicas de Cloudability, entre las que se incluyen el análisis de costes para la elaboración de informes, los paneles de control y TrueCost Explorer. Se puede acceder a funciones adicionales asignando permisos al rol.

**Puestos en « Cloudability »**

Se pueden asignar los siguientes roles a los usuarios de Cloudability :

| Nombre de rol | Permisos de rol | Tipos de solicitudes |
| --- | --- | --- |
| Usuario del asistente de IA | Los usuarios con este permiso podrán ver el widget del asistente de IA de Apptio en Cloudability y podrán interactuar con él. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| AdvancedContainersFullAccess | Rol de administrador para Cloudability : contenedores avanzados con tecnología de Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| AdvancedContainersViewOnly | Rol de solo lectura para los contenedores avanzados de « Cloudability », con tecnología de Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Captura de datos en la nube | Este rol predeterminado se utiliza para los usuarios de CDI. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Admin | Otorga acceso a todas las funciones de administración de Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Administración de facturación | Permite a los clientes configurar las preferencias de moneda para su organización en Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Usuario de automatización de la gobernanza | Este rol tiene el permiso « GovernanceFeatureConfigurationFullAccess ». El usuario con este rol tendrá acceso completo a las operaciones de configuración (excepto las políticas) de la función «Governance» de Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Responsable de la aprobación de las relaciones públicas en materia de gobernanza | Este rol tiene el permiso « GovernanceFeaturePRApprovalAccess ». El usuario con este rol tendrá acceso para aprobar las solicitudes de incorporación de cambios bloqueadas en la función «Governance» de Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Administración de la política de gobernanza | Este rol tiene el permiso « GovernanceFeaturePolicyFullAccess ». El usuario con este rol tendrá acceso completo a la funcionalidad de configuración de políticas (ver, crear y actualizar políticas) en el apartado «Gobernanza» del menú de funciones de Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Usuario sin restricciones | Este rol cuenta con todos los permisos del rol de usuario « Cloudability » y de « ViewsFeatureFullAccess ». El usuario con este rol tendrá acceso a todos los datos en la nube de tu organización. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Savings Automation Admin | Rol predeterminado para los usuarios que deben tener acceso administrativo a la aplicación Cloudability Savings Automation. | Cloudability Savings Automation |
| Cloudability Savings Automation Usuario | Rol predeterminado para los usuarios que no son administradores de Cloudability Savings Automation. | Cloudability Savings Automation |
| Cloudability Usuario | Acceso limitado a Cloudability sin privilegios para modificar datos. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Gestión de vistas (solo para la migración) | Por favor, NO utilices este rol, ya que está destinado exclusivamente a la migración del indicador «restringido». Dado que estamos dejando de utilizar el indicador «restricted» en Cloudability, a los usuarios que NO tengan dicho indicador se les asigna automáticamente este rol para que puedan seguir accediendo a la página de gestión de vistas. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerProvisioner | Puede configurar e implementar el agente de métricas de contenedores. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerUploader | Permite subir datos de Containers a Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Administrador de Cloudwiry | Rol predeterminado para los usuarios que deben tener acceso administrativo a la aplicación Cloudwiry. | Cloudwiry, Cloudability Savings Automation |
| Usuario de Cloudwiry | Rol predeterminado para los usuarios que deben tener acceso no administrativo a la aplicación Cloudwiry. | Cloudwiry, Cloudability Savings Automation |
| Usuario de la API de MSP | Acceso a todas las funciones de MSP/CCB en su propio entorno. | Facturación comercial (MSP) |
| Administrador de MSP | Acceso a todas las funciones de MSP/CCB en su propio entorno. Acceso de administrador en los entornos de los usuarios finales. | Facturación comercial (MSP) |
| Gestor de facturación de MSP | Acceso al módulo de facturación y a la lista de precios para cada consumidor final. Este perfil podrá editar o establecer tarifas y recargos para cada consumidor final, así como acceder a los datos de costes y consumo de todos los consumidores finales y añadir costes o partidas adicionales. | Facturación comercial (MSP) |

**Factores que Access Administration influyen en el Cloudability**

Los siguientes Access Administration roles se corresponden con los roles correspondientes en Cloudability :

| Nombre de rol | Permisos de rol |
| --- | --- |
| Admin : | Este rol permite añadir, editar o eliminar usuarios en Access Administration . Esta función se aplica a todas las aplicaciones de Apptio, incluida Cloudability. |
| Administrador | Este rol tiene acceso completo a Cloudability.  Este rol se concede a los usuarios que inician sesión en Cloudability con el rol «Admin» o « Cloudability Admin» en Access Administration . |
| Usuario | Este rol tiene acceso limitado a Cloudability.  Este rol se asigna a los usuarios que inician sesión en Cloudability con el rol de usuario Access Administration « Cloudability ». |

**Identidad y control de acceso**

En Cloudability, la gestión de identidades y accesos (IAM) y el control de acceso empresarial (EAC) se utilizan para gestionar las identidades y controlar el acceso a las funciones a las que los usuarios tienen permiso para acceder.

IAM y EAC admiten permisos que controlan las funciones de Cloudability, la creación de roles personalizados alineados con perfiles y la asignación de roles del proveedor de identidad ( IdP ) a los roles estándar y personalizados de Cloudability.

Nota: Los roles específicos asignados a un usuario en Access Administration anularán los roles de la asignación de roles de IdP.

**Perfiles de usuario y casos de uso**

Los permisos de IAM y EAC se basan en roles, lo que permite a los usuarios acceder a las funciones en función de su rol o perfil. La siguiente tabla muestra ejemplos de casos de uso y los perfiles de usuario correspondientes.

| Persona | Caso de uso | Cloudability Uso |
| --- | --- | --- |
| Usuario avanzado | Centro de Excelencia en la Nube ( CCoE )  Enfoque: profundo conocimiento de la gestión de costes en la nube, la administración de plataformas y la capacitación de los compañeros de trabajo | Diariamente |
| Responsable de programa o responsable de producto | Enfoque: los costes de la nube en el contexto del proyecto o producto del que son responsables | De forma puntual; semanal; según las necesidades |
| DevOps Usuario | Operaciones en la nube  Enfoque: optimización y automatización del uso | De forma puntual; semanal |
| Usuario de finanzas | Análisis e informes de cadencia a nivel de la organización  Tema central: planificación, elaboración de presupuestos y previsiones | Semanal; mensual; trimestral |
| Directivo | Alta dirección  Enfoque: panorama financiero y orientación | De forma puntual; trimestral |

No se puede eliminar un rol a menos que se hayan eliminado todos los usuarios asignados a dicho rol.

**Uso del control de identidad y acceso**

Nota:

Debes ser administrador Access Administration para acceder a los controles de identidad y acceso.

Puedes utilizar el Access Administration portal de administración de Access para acceder a las funciones que permiten asignar roles y permisos a los usuarios en Cloudability.

[Gestión de permisos y roles de usuario](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)")

**Permisos admitidos**

Cuando un usuario inicia sesión en Cloudability, los permisos asignados a través del Access
Administration portal de administración de accesos controlan el acceso a las funciones a las que puede acceder el usuario, en función de los permisos que se le hayan asignado.

En la siguiente tabla se muestran los permisos compatibles con Cloudability :

| Nombre del permiso | Descripción | Tipos de solicitudes |
| --- | --- | --- |
| AccountGroupManagementFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Grupos de cuentas» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AccountGroupManagementFeatureViewOnlyAccess | Permite a los usuarios asignados a un rol con este permiso ver, pero no editar, las cuentas y los grupos de cuentas que aparecen en la opción de menú «Grupos de cuentas» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersFullAccess | Permisos de administrador para los contenedores avanzados de Cloudability, con tecnología de Kubecost. | Advanced Containers (con tecnología de Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersViewOnly | Permiso de solo lectura para los contenedores avanzados de Cloudability, con tecnología de Kubecost. | Advanced Containers (con tecnología de Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvisorFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de Turbonomic, así como ejecutar planes. Sin embargo, los usuarios no pueden utilizar Place para reservar cargas de trabajo, crear políticas ni ejecutar ninguna de las acciones recomendadas. | Cloudability Premium, Turbonomic |
| AnomalyDetectionAlertSharingFeatureAddOn | Añade la posibilidad de compartir alertas de suscripción a anomalías con otros usuarios de la misma organización. | Cloudability |
| AnomalyDetectionFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) disponibles en el elemento de menú «Detección de anomalías» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomationFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del apartado «Automatización» del menú de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomatorFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic (incluidas «Plan», «Park» y «Place»), pero no pueden configurar la instalación de Turbonomic ni crear políticas. | Cloudability Premium, Turbonomic |
| AWSResourceInventoryFullAccess | Este permiso debe concederse explícitamente a un usuario si necesita acceder a la función « AWS » (Inventario de recursos) de CLDY. También hay un indicador de función en el backend que permite activar la función « AWS » de Resource Inventory para una organización de cliente concreta. Sin embargo, para que un usuario pueda ver este módulo, debe tener concedido este permiso de usuario. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsAndForecastFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) de las opciones del menú « Cloudability » («Mes actual», «Previsión» y «Presupuestos»). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsFeatureViewOnlyAccess | Permitir a los usuarios asignados a un rol con este permiso ver, pero no modificar, todos los presupuestos y sus valores en la opción de menú «Presupuestos» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Business Mappings» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureViewOnlyAccess | Permitir a los usuarios asignados a un rol con este permiso ver, pero no editar, las correspondencias empresariales y sus definiciones en el elemento de menú «Correspondencias empresariales» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerProvisioning | Permiso para aprovisionar e implementar el agente de métricas de contenedores. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerUploading | Permiso para subir datos de Containers a Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningCanAccess | Este usuario puede acceder a la funcionalidad de planificación de « Cloudability ». | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningFullAccess | Permiso de acceso total global. | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningManage | Crear/Duplicar/Eliminar/Renombrar Plans/ChangeBaseline/Dimensons(CRUD ). | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudwiryAdminFullAccess | Permite a los usuarios asignados a un rol con este permiso acceder a todas las funciones de nivel de administrador de la aplicación Cloudwiry. | Cloudwiry |
| CloudwiryUserFullAccess | Permite a los usuarios asignados a un rol con este permiso acceder a todas las funciones a nivel de usuario de la aplicación Cloudwiry. | Cloudwiry |
| CommitmentPreferencesFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Preferencias de compromiso» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CommitmentPreferencesFeatureViewOnly | Permitir a los usuarios asignados a un rol con este permiso acceder a la funcionalidad para ver la información que aparece en el elemento de menú «Preferencias de compromiso» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureFullAccess | Todo lo que incluye el permiso « "ContainersFeatureViewOnly" », además de la capacidad de crear y actualizar un agente de Cldy Containers. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureViewOnly | Permitir a los usuarios asignados a un rol con este permiso acceder a la funcionalidad para ver la información que aparece en el elemento de menú «Contenedores» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funcionalidades (ver, crear, actualizar) de las asignaciones y reglas incluidas en el elemento de menú « Cloudability » de la función «Cost Sharing», excepto las funciones de telemetría. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureViewOnlyAccess | Permitir a los usuarios asignados a un rol con este permiso ver todas las asignaciones, reglas y sus definiciones en el elemento de menú « Cloudability » de la función «Cost Sharing», pero sin poder editarlas ni eliminarlas. Tampoco pueden acceder a la función de telemetría. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicMaintainFeatureAccess | Permite el acceso completo a todos los puntos finales del Servicio de Modelización, excepto a la función de telemetría. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureFullAccess | Permite a los usuarios asignados a un rol con este permiso acceder a todas las funcionalidades (ver, crear, actualizar) de las asignaciones, las reglas y las subidas de datos de telemetría en el elemento de menú «Cost Sharing» ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureViewOnlyAccess | Permitir a los usuarios asignados a un rol con este permiso ver, pero no editar, el reparto de costes y sus definiciones en el elemento del menú de funciones «Business Mappings > Cost Sharing» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingMaintainFeatureFullAccess | Permite el acceso completo a todos los puntos finales del Servicio de Modelización. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DataTrackingFeatureBasicAccess | Permite a los usuarios asignados a un rol con este permiso acceder a la función « DataTracking » en Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DeployerFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de « Turbonomic », utilizar «Place» para reservar cargas de trabajo y crear políticas y plantillas de asignación. Sin embargo, los usuarios no pueden ejecutar planes ni llevar a cabo ninguna de las acciones recomendadas. | Cloudability Premium, Turbonomic |
| GovernanceFeatureConfigurationFullAccess | Accede a todas las funciones de configuración (ver, crear, actualizar), excepto las políticas, desde la opción de menú «Gobernanza» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePolicyFullAccess | Accede a todas las funciones de configuración de políticas (ver, crear, actualizar) en el apartado «Gobernanza» del menú de funciones de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePRApprovalAccess | Permitir a los usuarios aprobar las solicitudes de incorporación de cambios (Pull Requests) que estén bloqueadas en « Cloudability Governance» por no cumplir con las políticas de gobernanza. Este permiso está incluido en el rol « Cloudability Governance PR Approver». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeatureViewOnly | Accede a la función para ver la información en el menú «Gobernanza» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| InvoiceGeneration | Importar datos, consultar y crear facturas. | Facturación comercial (MSP) |
| MspBillingCloudSpendApiRead | Acceso de lectura a la API de gasto en la nube de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingCustomLineItemsRead | Acceso de lectura a las partidas personalizadas de « Cloudability MSP » / «CCB». | Facturación comercial (MSP) |
| MspBillingCustomLineItemsWrite | Acceso de escritura a las partidas personalizadas de « Cloudability MSP » / «CCB». | Facturación comercial (MSP) |
| MspBillingExternalApiPricingRead | Acceso de lectura a la API de precios externa de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingExternalApiPricingWrite | Acceso de escritura a la API de precios externa de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingPricingRead | Acceso de lectura a los catálogos de precios de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingPricingWrite | Acceso de escritura a los catálogos de precios de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingSettingsRead | Acceso de lectura a la configuración de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| MspBillingSettingsWrite | Acceso de escritura a la configuración de Cloudability MSP /CCB. | Facturación comercial (MSP) |
| ObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluidas la página de inicio y los paneles de control. | Cloudability Premium, Turbonomic |
| OperationalObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la página de inicio, los paneles de control, los grupos y las políticas. | Cloudability Premium, Turbonomic |
| OrgCurrencyFeatureAccess | Permite a los usuarios asignados a un rol con este permiso acceder a la pantalla de divisas y modificar la divisa base predeterminada de una organización. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RateOptimizationFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones disponibles en el elemento de menú «Optimización de tarifas» de la función « Cloudability Savings Automation ». | Cloudability Savings Automation, Cloudwiry |
| RateOptimizationFeatureViewOnly | Permite a los usuarios asignados a un rol con este permiso ver la información que aparece en la opción de menú «Optimización de tarifas» de Cloudability Savings Automation. | Cloudability Savings Automation, Cloudwiry. |
| ReadBillingExternalApi | Puede leer la API externa de facturación. | Facturación comercial (MSP) |
| ReadOrgStructure | Acceso de lectura al servicio de estructura organizativa | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Org Structure Service. |
| ReservationPortfolioFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Cartera de reservas» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ReservedInstancePlannerFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Reserved Instance Planner» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureCanSnooze | Permite a los usuarios asignados a un rol con este permiso realizar acciones (crear, actualizar, eliminar) relacionadas con posponer recomendaciones en el elemento de menú «Rightsizing» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Rightsizing» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureViewOnly | Permitir a los usuarios asignados a un rol con este permiso acceder a la funcionalidad para ver la información que aparece en el elemento de menú «Rightsizing» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Políticas de ajuste de recursos» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureViewOnly | Permitir a los usuarios asignados a un rol con este permiso acceder a la funcionalidad para ver la información que aparece en el elemento de menú «Políticas de ajuste» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Preferencias de ajuste» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureViewOnly | Permitir a los usuarios asignados a un rol con este permiso acceder a la funcionalidad para ver la información que aparece en el elemento de menú «Preferencias de ajuste» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingRoiFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Rightsizing ROI» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SavingsPlansFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Planes de ahorro» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ScopedAdvisorFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de Turbonomic, así como ejecutar planes. Sin embargo, los usuarios no pueden utilizar Place para reservar cargas de trabajo, crear políticas ni ejecutar ninguna de las acciones recomendadas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedAutomatorFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic (incluidas «Plan», «Park» y «Place»), pero no pueden configurar la instalación de Turbonomic ni crear políticas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedDeployerFullAccess | Los usuarios con este permiso pueden ver todos los gráficos y datos de « Turbonomic », utilizar «Place» para reservar cargas de trabajo y crear políticas y plantillas de asignación. Sin embargo, los usuarios no pueden ejecutar planes ni llevar a cabo ninguna de las acciones recomendadas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluidas la página de inicio y los paneles de control. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedOperationalObserverFullAccess | Los usuarios con este permiso pueden ver el entorno, incluyendo la página de inicio, los paneles de control, los grupos y las políticas. Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedSharedAdvisorFullAccess | Los usuarios con este permiso pueden ver la página de inicio y los paneles de control, pero solo ven las máquinas virtuales y las aplicaciones. Los usuarios no pueden realizar acciones de tipo « Turbonomic ». Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScopedSharedObserverFullAccess | Los usuarios con este permiso pueden ver la página de inicio y los paneles personalizados, pero solo pueden ver máquinas virtuales y aplicaciones. Los usuarios no pueden ver los paneles de control ejecutivos ni realizar acciones de « Turbonomic ». Un administrador del sitio de Turbonomic debe establecer un ámbito para este usuario en la vista «Gestión de usuarios» de Turbonomic. | Cloudability Premium, Turbonomic |
| ScorecardsFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Cuadros de mando» de la función « Cloudability » | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SiteAdminFullAccess | Los usuarios con este permiso pueden utilizar todas las funciones de Turbonomic y modificar los ajustes específicos del sitio para configurar la instalación de Turbonomic. Los usuarios también pueden gestionar grupos, políticas, flujos de trabajo, plantillas, facturación y costes, y la configuración de destino, pero no el correo electrónico, las licencias, las actualizaciones ni el mantenimiento. Los usuarios con este rol pueden configurar el ámbito de otras cuentas. | Cloudability Premium, Turbonomic |
| TagExplorerFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Tag Explorer» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Etiquetas» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureViewOnlyAccess | Permite a los usuarios asignados a un rol con este permiso ver, pero no editar, todas las dimensiones de Cloudability y sus claves de etiqueta asignadas, así como las etiquetas de k8, en el elemento de menú «Etiquetas» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TurbonomicFeatureFullAccess | Permitir que los usuarios asignados a un rol con este permiso accedan a todas las funciones (ver, crear, actualizar) del elemento de menú " Turbonomic " de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium |
| UserManagementFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones disponibles en el elemento de menú «Usuarios» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| VendorCredentialsFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Credenciales de proveedores» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Savings Automation, Cloudability Standard, Cloudwiry |
| ViewBillMx | Ver datos. | Facturación comercial (MSP) |
| ViewsFeatureCreateOwnViewsAccess | Permite a los usuarios asignados a un rol con este permiso ver todas las vistas y sus definiciones en el elemento de menú «Vistas» de la función « Cloudability », pero solo podrán editar o eliminar aquellas vistas que hayan creado ellos mismos. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ViewsFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Vistas» de la función « Cloudability ». | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlacementFeatureFullAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Workload Placement» ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureCanAccess | Permitir a los usuarios asignados a un rol con este permiso acceder a todas las funciones (ver, crear, actualizar) del elemento de menú «Planificación de la carga de trabajo» de Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureFullAccess | Permite a los usuarios asignados a un rol de administrador con este permiso acceder a todas las funcionalidades (ver, crear, actualizar) del elemento de menú «Planificación de la carga de trabajo» de Cloudability. También tienen la posibilidad de consultar o actualizar cualquier carga de trabajo creada por otros usuarios. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningPreferencesViewOnly | Permite a los usuarios asignados a un rol de administrador con este permiso configurar las preferencias y restricciones de su organización para la planificación de la carga de trabajo. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WriteOrgStructure | Acceso de escritura al servicio de estructura organizativa. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Servicio de Estructura Organizativa |
