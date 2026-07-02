---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "release-notes"
title: "Cloudability novedades en 2023"
breadcrumb:
  - "Cloudability Premium"
  - "Novedades en Cloudability"
source_path: "release-notes/whats-new-2023.html"
images:
  - "images/anomaly_detection_threshold_new.jpg"
  - "images/automated_credential.jpg"
  - "images/azure-enabled.jpg"
  - "images/azure-not-enabked.jpg"
  - "images/cldy-bi-8.jpg"
  - "images/cldy-idle-cost.jpg"
  - "images/cldy-res-inv-sorting.jpg"
  - "images/container-metrics-openshift_1.jpg"
  - "images/cost-management.jpg"
  - "images/cost_visibility_usage_metrics_2.jpg"
  - "images/ebs-new.jpg"
  - "images/gpu_support_container_insights.jpg"
  - "images/greentick.jpg"
  - "images/kubernetes-label.jpg"
  - "images/kubernetes.jpg"
  - "images/kubernetes_1.28_versions.jpg"
  - "images/mig-help-image-2.jpg"
  - "images/oci2.jpg"
  - "images/oci_rn.jpg"
  - "images/release_notes_screeenshot.jpg"
  - "images/rn-rightsizing-oci-vms.jpg"
  - "images/rosa1.jpg"
  - "images/usagefamilyremapping.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability novedades en 2023

## Soporte de inventario de recursos para vistas creadas con grupos de cuentas - 28 de diciembre de 2023

Con esta versión, los inventarios de recursos AWS y Azure admitirán las vistas creadas mediante grupos de cuentas en Cloudability. Ahora puede filtrar los datos de Inventario de Recursos basándose en las Vistas que se crean utilizando cualquier combinación de Dimensiones de Etiquetas, Grupos de Cuentas y filtros de Proveedores.

Nota: El Inventario de Recursos, en ambos proveedores de servicios, aún no soporta Vistas basadas en Dimensiones de Negocio. Aparece una página de "vista restringida" si se cambia a una vista con un filtro de dimensión empresarial.

Cómo puede ayudarle esta función

Anteriormente, el Inventario de recursos mostraba una página de "Vista restringida" si se cambiaba a una Vista creada mediante Grupos de cuentas.

## Lógica mejorada para Azure Compute in Resource Inventory - 28 de diciembre de 2023

Esta versión mejora nuestra lógica actual para mostrar los recursos informáticos de Azure en Azure Inventario de recursos en Cloudability. Como resultado, puede esperar ver una reducción en el número de recursos bajo el servicio Compute y un aumento en el número de recursos bajo los servicios Managed Disk en Azure Resource Inventory.

Cómo puede ayudarle esta función

Anteriormente, nuestra lógica para mostrar recursos bajo el servicio Compute tenía en cuenta los recursos instantáneos y esto provocaba que se mostrara un recuento de recursos mayor de lo esperado para sus recursos de computación de Azure. Nuestra nueva lógica es tal que las instantáneas se contabilizarán en el servicio Managed Disk en lugar de en el servicio Compute. De esta forma, puede esperar ver una reducción en el número de recursos bajo el servicio Compute y un aumento en el número de recursos bajo los servicios Managed Disk en Azure Resource Inventory.

## GCP Facturación detallada - 20 de diciembre de 2023

Esta versión incorpora la facturación detallada de « GCP », lo que te permite obtener información detallada sobre los costes a nivel de recurso de « GCP » a través de los informes y paneles de control de « Cloudability ».

Cómo puede ayudarle esta función

GCP ha implantado una facturación detallada en numerosos servicios, lo que permite consultar datos de costes detallados a nivel de recurso, a diferencia de la facturación estándar, que solía proporcionar los datos de costes a nivel de SKU.

Más información sobre el comunicado

Para configurar la facturación detallada de GCP, deberá:

1. Seleccione el elemento de menú “ Configuración ” del menú de navegación principal Cloudability y luego, en el submenú expandido, seleccione “ Credenciales de proveedor ”.
2. En la página «Credenciales», selecciona la pestaña de navegación correspondiente a « GCP » para iniciar el proceso de añadir las credenciales de GCP a Cloudability.
3. Selecciona la opción « GCP Detailed Billing» en la lista desplegable.
4. Añade el identificador de la tabla de facturación detallada « GCP ».
5. Indica el GCP GCS bucket.
6. Agregue la fecha de facturación detallada GCP (año y mes de inicio).
7. Descarga la plantilla y ejecútala en la consol GCP.
8. Una vez completado haga clic en Verificar credenciales. Una marca verde indica que la acreditación se ha realizado correctamente.

GCP Los costes por recurso estarán disponibles en Cloudability, en la sección «Informes y paneles», seleccionando la columna «ID de recurso».

## AWS Acreditación automatizada de cuentas vinculadas - 19 de diciembre de 2023

Con esta versión, podrá acreditar rápidamente sus cuentas vinculadas a AWS. Cloudability ahora aprovecha las organizaciones de AWS, lo que le permite agrupar las cuentas vinculadas bajo las organizaciones y ejecutar la plantilla de formación en nube (CFT) a nivel de organización. Esto reduce el número de ejecuciones de la CFT AWS.

Antes, era necesario descargar el CFT y ejecutarlo individualmente en cada cuenta vinculada.

Cómo activar la acreditación automática

1. Añada sus cuentas vinculadas en la  [organización AWS](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_create.html "(se abre en una pestaña o una ventana nueva)") en la consola AWS.
2. En Cloudability, mientras se acreditan las cuentas de AWS Master Payer, active la casilla de verificación Automated credentialing of linked accounts.
3. ![aws add cedential captura de pantalla](../../../../03-media/cloudability-premium/images/automated_credential.jpg)
4. Generar la plantilla CFT que debe ejecutarse en la consola AWS.
5. Añada credenciales para cualquiera de sus cuentas vinculadas bajo la organización AWS, después guarde y descargue la plantilla, y ejecútela para la cuenta vinculada seleccionada en la consola AWS.
6. En las cuentas vinculadas individuales, seleccione Editar > Descargar > Verificar credenciales para completar la credencialización de las cuentas vinculadas.

## GCP Acreditación automatizada de los proyectos de « GCP » — 19 de diciembre de 2023

Esta versión te permite configurar rápidamente las credenciales de los proyectos de GCP en Cloudability.

Cómo puede ayudarle esta función

Cloudability Ahora permite a las organizaciones de GCP agrupar sus proyectos de GCP y ejecutar el script de shell a nivel organizativo, lo que reduce el número de ejecuciones del script. Antes era necesario descargar el script de shell y ejecutarlo por separado en cada proyecto de GCP de tu organización.

## Presentación de Cloudability en la región de la UE - 19 de diciembre de 2023

Esta versión introduce el alojamiento de Cloudability, nuestra plataforma de gestión de costes en la nube, en la región de la UE.

Cómo puede ayudarle esta función

Esta versión responde a las necesidades específicas de nuestros clientes de la UE, garantizando que sus datos permanezcan dentro de las fronteras de la UE. Mediante la localización de nuestros servicios, pretendemos capacitar a las organizaciones para que refuercen sus esfuerzos de cumplimiento y se ajusten a la normativa relativa a los datos de gestión de costes en la nube.

Más información sobre el comunicado

El lanzamiento del alojamiento Cloudability en la región de la UE reviste gran importancia para nuestros clientes que operan en esta región. Proporciona una solución de gestión de costes en la nube fiable y conforme a la normativa que da prioridad a la residencia de los datos, mejora su privacidad y se ajusta a la normativa de protección de datos.

Nota:

Los clientes que se conecten directamente a Cloudability en la UE no necesitarán ninguna configuración ni instalación adicional. El plan de migración de los clientes actuales se dará a conocer a principios del año que viene.

## Indicación de la región AWS para la política de control de servicios AWS - 19 de diciembre de 2023

Como usuario de AWS, esta versión le permite indicar la región de la política de control de servicios de AWS al acreditar sus cuentas de AWS en Cloudability. Permite a Cloudability ir y comprobar los permisos en la región mencionada.

Cómo puede ayudarle esta función

Antes comprobábamos los permisos de las cuentas AWS sólo en la región us-east-1. Si el SCP está habilitado para una región específica (que no sea us-east-1 ), recibirá un error de " Acceso denegado " al verificar sus cuentas de AWS. Esta versión ha solucionado la situación anterior y permite a Cloudability comprobar los permisos en la región mencionada.

## Compatibilidad con etiquetas de cuenta AWS y etiquetas de suscripción Azure - 18 de diciembre de 2023

Con esta versión, los clientes pueden recuperar sus etiquetas de suscripción a nivel de cuenta AWS y Azure de sus cuentas en la nube en Cloudability. Esta función ayudará a los clientes a crear dimensiones de etiquetas para mejorar la asignación de costes y la devolución de gastos, así como el seguimiento de sus gastos en la nube.

Más información sobre esta versión

Para facilitar la identificación de las etiquetas a nivel de cuenta, hemos añadido los prefijos mencionados a continuación para las etiquetas de cuenta en AWS y Azure respectivamente:

Prefijo para AWS : cldy:aws:accountleveltag:

Prefijo para Azure : cldy:azure:subscriptionleveltag:

Las etiquetas de cuenta aparecerán al crear una dimensión de etiqueta en la pantalla Organizar > Etiquetas y rótulos.

Nota:

- o los clientes de AWS existentes en Cloudability, se concederá un nuevo permiso denominado Organizaciones: ListTagsForResource al rol de Cloudability Rol IAM que se añada en su nube AWS. Este permiso es necesario para obtener etiquetas a nivel de cuenta de las Organizaciones AWS.
- Para los nuevos clientes de AWS, el permiso mencionado se añadirá a la plantilla de credenciales de Cloudability, por lo que no es necesario realizar ningún cambio en la configuración.
- Para los clientes existentes y nuevos de Azure en Cloudability, no se requieren cambios de configuración, y las etiquetas a nivel de suscripción comenzarán a aparecer en el módulo Organizar > Etiquetas y rótulos.

## Cloudability Agente de métricas de contenedores compatible con las versiones OpenShift 4.13, 4.14 - 14 de diciembre de 2023

Esta versión ofrece compatibilidad oficial con la asignación de costes a contenedores en las versiones OpenShift 4.13 y 4.14.

Cómo puede ayudarle esta función

Esta función permite obtener información detallada sobre la utilización de los recursos de los contenedores y los costes asociados para los clústeres que utilizan la variante ROSA y funcionan con estas versiones de OpenShift.

Ahora puede descargar e implantar fácilmente nuestro agente de métricas a través del flujo de trabajo de aprovisionamiento estándar.

![cldy pantalla de métricas del contenedor](../../../../03-media/cloudability-premium/images/container-metrics-openshift_1.jpg)

## Rightsizing ROI - ServiceNow Integration - 13 de diciembre de 2023

Esta versión añade una función de integración OOB ServiceNow con la función Rightsizing de nuestra plataforma Cloudability.

Cómo puede ayudarle esta función

Esta funcionalidad proporciona la capacidad de generar solicitudes de ServiceNow y/o tickets de incidencias que contengan recomendaciones de dimensionamiento automáticamente dentro de su propia instancia de ServiceNow. Esta característica se parece mucho a la actual funcionalidad Rightsizing ROI que puede integrarse con Jira Cloud.

Gracias a la integración de Cloudability y ServiceNow,, ahora puede colaborar de forma rápida y eficaz en torno a los recursos en la nube y las recomendaciones de dimensionamiento. Este sistema automatizado de emisión de tickets aumenta una cadencia de rightsizing más eficiente para promover la optimización de la nube a través de los procesos normales de servicio. También podrá acceder más fácilmente a los registros de los detalles de las recomendaciones en Cloudability, así como en su plataforma ServiceNow, junto con las acciones (si las hubiera) emprendidas en relación con las recomendaciones. Ahora puede calcular y mostrar automáticamente el ahorro obtenido de las acciones resultantes a través de la página Rightsizing ROI en Cloudability.

Más información sobre el comunicado

Para empezar, introduzca sus credenciales de proveedor en ServiceNow en el menú de navegación principal de Cloudability y vaya a Configuración > Credenciales de proveedor > ServiceNow. A continuación, puede configurar una política de Rightsizing ROI accediendo a Configuración > Políticas de Rightsizing y definiendo una política para empezar a capturar automáticamente recomendaciones de rightsizing basadas en los criterios que haya definido. Estos criterios de política de ROI se utilizan para determinar qué recomendaciones de ampliación de derechos tendrán tickets creados automáticamente en su instancia de ServiceNow.

Alternativamente, las recomendaciones de asignación de derechos pueden capturarse manualmente navegando a la página Asignación de derechos en Optimizar > Asignación de derechos y creando manualmente una solicitud (o incidencia) ServiceNow para una recomendación individual desde el menú situado a la derecha de la tabla de recomendaciones. Para ver las recomendaciones de Rightsizing capturadas en Cloudability, navegue hasta Optimize > Rightsizing ROI.

## Cloudability Rightsizing - Opciones de filtrado a nivel de página - 12 de diciembre de 2023

Esta versión añade dos nuevas opciones de filtrado a nivel de página en las páginas de Rightsizing aplicables que proporcionan nuevos métodos de filtrado de recomendaciones basados en 1) la arquitectura de la CPU de computación y 2) el número de recursos dentro de un grupo de computación.

Cómo puede ayudarle esta función

Esta funcionalidad es el primer paso para proporcionar opciones de filtrado de Rightsizing a nivel de página que filtren tanto las recomendaciones principales como las opciones de recomendación adicionales proporcionadas en el panel de detalles. Esta versión incluye 2 nuevas opciones:

1. La opción " Top Multi-Architecture " que está disponible en las páginas de Compute Rightsizing. Esta opción filtra las opciones de recomendación del panel de detalles mostrando al menos 1 recomendaciones de rightsizing para cada arquitectura de CPU - Si hay ahorros de costes disponibles para la arquitectura de CPU. Las recomendaciones del panel de detalles siguen apareciendo por orden de mayor ahorro de costes.
2. La opción " Sólo reducción de recuento " disponible en las páginas de Redimensionamiento de grupos de cálculo (actualmente ASG, MIG). Esta opción filtra todas las recomendaciones mostrando sólo las que reducen el número de instancias del grupo.

Más información sobre el comunicado

Esta versión le ofrece más opciones para filtrar las recomendaciones de dimensionamiento con el fin de satisfacer sus casos de uso y mejorar la usabilidad. Además, disponer de opciones de filtrado a nivel de página que puedan filtrar tanto las recomendaciones principales proporcionadas en la página como las opciones de recomendación adicionales proporcionadas en el panel de detalles permite posibilidades de filtrado más exhaustivas cuando se requiere este nivel de granularidad para tomar las medidas de ahorro adecuadas.

En el menú de navegación principal de Cloudability, en la opción de menú Optimizar, seleccione la opción Redimensionar. La opción " Top Multi-Architecture " está disponible en la página Compute Rightsizing de cada proveedor (por ejemplo, la página compute rightsizing de AWS es EC2 ). La opción " Sólo reducción de recuento " está disponible en la página "Compute Group Rightsizing " de cada proveedor (por ejemplo, la página "Compute Group Rightsizing" de AWS es EC2 ASG). Ambas opciones estarán situadas cerca de la parte superior de sus respectivas páginas, junto a los "Filtros" actuales que ya se ofrecen.

Nota:

La opción " Top Multi-Arquitectura " requerirá que la opción " Permitir recomendaciones entre arquitecturas " esté activada globalmente en la página de Preferencias de Redimensionamiento situada en la opción de menú Configuración como requisito previo. Los cambios en estas preferencias globales pueden tardar hasta 24 horas en surtir efecto.

## Cloudability Recomendaciones sobre tipos de instancias mixtas en el dimensionamiento de AWS ASGs - 7 de diciembre de 2023

Esta versión ofrece nuevas recomendaciones de ajuste de tamaño de Cloudability para grupos de Auto Scaling (ASG) de AWS EC2 con tipos de instancia mixtos.

Cómo puede ayudarle esta función

Cloudability La función «Rightsizing» ofrece ahora recomendaciones para los grupos de escalabilidad (ASG) de AWS EC2 con tipos de instancia mixtos. Anteriormente, las recomendaciones de redimensionamiento sólo estaban disponibles para ASG de tipo instancia única. Al igual que las recomendaciones ASG de tipo instancia única, estas nuevas recomendaciones proporcionan acciones de ahorro de costes a aplicar en el propio grupo, que luego se aplicarán automáticamente a los recursos creados por ese grupo.

Más información sobre el comunicado

Gracias a la nueva compatibilidad con las recomendaciones de ajuste del tamaño para los grupos de ASG con tipos de instancia mixtos, ahora tendrás acceso a recomendaciones adicionales para los grupos de « AWS Auto Scaling », que te permitirán identificar oportunidades de ahorro de costes al detectar los recursos cuyo tamaño se puede ajustar para que se adapten mejor a sus cargas de trabajo subyacentes.

## Cloudability Mejora: Actualización de la asignación de nombres de servicio para AWS Elastic Container Registry - 22 de noviembre de 2023

Esta versión corrige un error para garantizar que AWS Elastic Container Registry se asigna correctamente al nombre de servicio apropiado. Con esta actualización, AWS Elastic Container Registry se asignará ahora con precisión a AWS ECR. Este cambio entra en vigor hoy.

Si necesita que esta actualización se aplique a sus datos históricos, póngase en contacto con nuestro equipo de asistencia o con su representante de cuenta para solicitar un reprocesamiento.

## La imputación de costes de contenedores ya es compatible con Kubernetes 1.28 Versions - 21 de noviembre de 2023

Esta versión anuncia la compatibilidad de Container Cost Allocation con la versión Kubernetes 1.28 en todos los proveedores. Esta función permite a los clientes obtener información detallada sobre el uso de los recursos de los contenedores y los costes asociados para los clústeres que se ejecutan en Kubernetes 1.28.

Ahora los clientes pueden descargar e implantar fácilmente nuestro agente de métricas a través del flujo de trabajo de aprovisionamiento estándar.

![pantalla de imputación de costes de contenedores](../../../../03-media/cloudability-premium/images/kubernetes_1.28_versions.jpg)

## Oracle Motor de contenedores para Kubernetes : Gestión y optimización de costes - 20 de noviembre de 2023

Esta versión introduce la compatibilidad oficial de Cloudability con Oracle Container Engine para Kubernetes (OKE). Esta versión logra la paridad de funciones para OCI, permitiendo a los usuarios asignar costes de forma granular por espacios de nombres y etiquetas, lo que facilita un seguimiento preciso de los costes para que puedan imputarse a la empresa.

Ahora los usuarios pueden mapear y gestionar de forma integrada todos sus clústeres de Kubernetes ( K8s ) en OCI, AWS, Azure y GCP, ya que estamos ampliando la compatibilidad con OKE.

![captura de pantalla de los contenedores oracle](../../../../03-media/cloudability-premium/images/oci2.jpg)

Los aspectos más destacados de esta versión son:

- Asignación de costes de contenedores: Explore y visualice los costes de todos los clústeres de OKE, clasificados por espacios de nombres y etiquetas.
- Informes mejorados: Las dimensiones Cluster Name, Namespace y Label están disponibles en los informes principales, incluidos los informes, los cuadros de mando y TrueCost Explorer.
- Mapas y vistas empresariales: Asigne y categorice los costes de los contenedores junto con los costes habituales de la nube.
- Recomendaciones de redimensionamiento: Optimice la utilización de los recursos y la rentabilidad recibiendo recomendaciones para alinear los valores de solicitud y límite con los requisitos reales de la carga de trabajo, reduciendo el despilfarro y los gastos.

Nota:

Para las instancias GPU, el principal factor de coste es la GPU y OCI no proporciona ningún coste por CPU y Memoria. Por lo tanto, estamos asignando costes de contenedor a nivel de GPU para clusters de GPU pero hay 0 asignación de costes para CPU y Memoria.

## Gestión y optimización de costes para el motor Oracle Kubernetes - 20 de noviembre de 2023

Esta versión introduce la compatibilidad oficial de Cloudability con Oracle Kubernetes Engine (OKE). Esta versión logra la paridad de funciones para OCI, permitiendo a los usuarios asignar costes de forma granular por espacios de nombres y etiquetas, lo que facilita un seguimiento preciso de los costes para que puedan imputarse a la empresa.

Ahora los usuarios pueden mapear y gestionar de forma integrada todos sus clústeres de Kubernetes ( K8s ) en OCI, AWS, Azure y GCP, ya que estamos ampliando la compatibilidad con OKE.

![optimización de la gestión de costes captura de pantalla](../../../../03-media/cloudability-premium/images/oci2.jpg)

Los aspectos más destacados de esta versión son:

- Asignación de costes de contenedores: Explore y visualice los costes de todos los clústeres de OKE, clasificados por espacios de nombres y etiquetas.
- Informes mejorados: Las dimensiones Cluster Name, Namespace y Label están disponibles en los informes principales, incluidos los informes, los cuadros de mando y TrueCost Explorer.
- Mapas y vistas empresariales: Asigne y categorice los costes de los contenedores junto con los costes habituales de la nube.
- Recomendaciones de redimensionamiento: Optimice la utilización de los recursos y la rentabilidad recibiendo recomendaciones para alinear los valores de solicitud y límite con los requisitos reales de la carga de trabajo, reduciendo el despilfarro y los gastos.

Nota:

Para las instancias GPU, el principal factor de coste es la GPU y OCI no proporciona ningún coste por CPU y Memoria. Por lo tanto, estamos asignando costes de contenedor a nivel de GPU para clusters de GPU pero hay 0 asignación de costes para CPU y Memoria.

## Recomendaciones de Rightsizing para máquinas virtuales OCI - 20 de noviembre de 2023

Esta versión soporta Cloudability Rightsizing para Oracle Virtual Machines (VMs). Esta nueva función llama la atención sobre los recursos sobreaprovisionados y ociosos para ofrecer oportunidades de ahorro de costes, identificando los recursos OCI que pueden redimensionarse para adaptarse mejor a las cargas de trabajo subyacentes de los clientes y permitiéndoles realizar un seguimiento de las acciones en Rightsizing ROI.

![recomendaciones de dimensionamiento](../../../../03-media/cloudability-premium/images/rn-rightsizing-oci-vms.jpg)

Cómo puede ayudarle esta función

- Recibir recomendaciones prácticas para varios tipos de máquinas virtuales: Legacy, flex, burstable, bare metal y pools de instancias.
- Recibir análisis detallados de ahorro de costes que tengan en cuenta la CPU, la red y la memoria para plazos de 10 y 30 días.
- Visualización de los posibles ahorros en el uso de OCI, AWS, Azure y GCP Cloud en Rightsizing Explorer.

Más información sobre el comunicado

Para recibir estas recomendaciones, debe pasar por el proceso de acreditación avanzada para sus tenencias de niños, de modo que Cloudability pueda extraer los datos de utilización necesarios para la asignación de derechos. Una vez verificadas las credenciales avanzadas, las recomendaciones pueden tardar hasta 48 horas en aparecer en Cloudability. Las recomendaciones se mostrarán en la página Redimensionamiento, en la nueva pestaña de proveedores " OCI ".

## Azure Informes sobre el inventario de recursos - 15 de noviembre de 2023

Esta versión introduce la función de inventario de recursos de Azure para Cloudability, que le permite elaborar una lista fidedigna de los recursos en nube existentes de Azure facturados durante un periodo de informe específico.

Cómo puede ayudarle esta función

Como usuario de Azure, tiene la flexibilidad de construir esta lista a partir de recursos que abarcan múltiples cuentas y elegir entre diferentes medidas (dimensiones y métricas) para hacer aflorar los detalles relevantes para ellas. Esta información disponible para cada recurso en la nube unifica la facturación, la utilización y los metadatos descriptivos para ofrecerle una visión más completa del inventario.

Azure La función de informes de inventario de recursos debe estar explícitamente activada para su organización en Cloudability. Para ello, debes ponerte en contacto con tu TAM/CSM/punto de contacto de Apptio. Por defecto, sólo los administradores de Cloudability podrán acceder a esta función. Sin embargo, el acceso al inventario también se puede conceder a cualquier rol personalizado asignando al rol personalizado con AWSResourceInventoryFullAccess permisos.

Nota: Aunque el nombre de este permiso dice " AWS ", también se aplica para Azure Inventario de Recursos. En el futuro cambiaremos el nombre del permiso para evitar confusiones.

Más información sobre el comunicado

Puede ver los datos de inventario del mes hasta la fecha para cada servicio. Al activar esta función, los datos de inventario de recursos se volverán a rellenar al principio del mes en curso. Con el tiempo, los datos de inventario estarán disponibles en una ventana móvil de tres meses. Es decir, en cualquier momento podrá acceder a los datos de inventario de recursos del mes en curso junto con los de los dos meses anteriores. Tienes la opción de exportar los informes en formato « CSV ». Estas exportaciones incluyen todas las columnas admitidas para el servicio en cuestión (es decir, no hay límite de 20 columnas).

## Reprocesamiento de datos en autoservicio (Beta) - 15 de noviembre de 2023

Esta versión proporcionará una función de reprocesamiento de datos de autoservicio a los clientes de Cloudability y de Cálculo de costes y planificación que les permitirá reprocesar sus datos sin depender de los equipos de Asistencia o de Éxito del cliente. En comparación con la actual tarea de reprocesamiento, esta función acelera el tiempo de resolución, elimina pasos manuales, crea transparencia en las solicitudes de los usuarios y mejora su experiencia.

Cómo puede ayudarle esta función

Normalmente, cuando se modifica la estrategia empresarial, es necesario ajustar las asignaciones empresariales, los grupos de cuentas y las etiquetas en Cloudability con una actualización retrospectiva de los datos históricos. Aquí es donde entra en escena el reprocesamiento de datos. Si usted es un cliente de Cloudability es posible que sólo necesite el reprocesamiento dentro de Cloudability, sin embargo, si también utiliza Costing & Planning, sus acciones implican la exportación de datos a Costing & Planning también.

La tarea de reprocesamiento diario existente se centra principalmente en el reprocesamiento de los datos del mes en curso. Para volver a procesar los datos históricos, el proceso actual requiere que usted tenga que abrir un ticket de soporte. Este proceso manual depende de la asistencia técnica y requiere mucho tiempo, y es algo que estamos intentando eliminar con esta versión.

Nota:

Esta función no está activada de forma predeterminada, ya que es necesario activarla explícitamente para poder verla en Cloudability. Ponte en contacto con tu TAM/CSM para activarlo.

Más información sobre el comunicado

Para acceder a esta función, vaya a Organize > Data Reprocess en Cloudability o Cloud Data Ingestion (CDI).

![Captura de pantalla del reprocesamiento de datos](../../../../03-media/cloudability-premium/images/release_notes_screeenshot.jpg)

La función tiene dos flujos de trabajo diferentes para dos usuarios distintos: Cloudability Sólo reprocesamiento de datos y Cloudability - Reprocesamiento de datos de cálculo de costes y planificación.

Esta función tiene las siguientes limitaciones en cuanto al número de solicitudes que pueden presentarse en un mes.

- Sólo los usuarios de Cloudability con rol "Admin" y los usuarios de Cloud Data Ingestion (CDI) con rol "Cloud Data Ingestion" podrán acceder a la función.
- Los clientes dispondrán de un número predefinido de Mes-unidades/mes.
- Los clientes dispondrán de un periodo de retrospectiva predefinido de 12 meses.
- No se pueden presentar dos solicitudes de reprocesamiento al mismo tiempo, si tienen periodos que se solapan.

Si sólo utiliza Cloudability : Se trata de un proceso de dos pasos en el que puede seleccionar el Periodo y enviar el trabajo. También puede supervisar el estado del trabajo en la pestaña Estado del trabajo. Para conocer los pasos detallados, consulte [Reprocesamiento de datos para usuarios de Cloudability](../product/data_reprocess.html).

## Apptio BI Informes para Cloudability TotalCost - 9 de noviembre de 2023

Esta versión incluye tres nuevos informes listos para usar en Apptio BI para los clientes de Cloudability TotalCost.

Nuevos informes Apptio BI

Esta versión incluye los siguientes nuevos informes listos para usar: Apptio BI Reports. Estos informes aprovechan los datos de la fuente Cloudability TotalCost. Puede encontrar estos informes en la página Informes.

Visibilidad de los costes

| Descripción | Este informe de Apptio BI ofrece una visión general de los datos de gasto en sus principales fuentes de datos en la nube, concretamente AWS, Azure, GCP y OCI, según corresponda. |
| --- | --- |
| Casos prácticos | Este informe resuelve los siguientes casos de uso: Comprenda el coste total de los principales servicios en nube de su organización.  Información específica sobre el gasto en servicios en la nube de los principales proveedores. |
| Personas | Este informe está dirigido principalmente a los profesionales del Centro de Excelencia de la Nube y de FinOps, así como a los ingenieros que desean tener una visibilidad completa del gasto de sus organizaciones. |
| Preguntas contestadas | El informe responde a las siguientes preguntas: ¿A cuánto ascienden mis gastos en « AWS », « Azure », « GCP » y OCI, en su caso?  ¿Cuánto estoy gastando en los principales servicios (por ejemplo: AWS S3 ) que ofrecen los proveedores de servicios en la nube? |

TotalCost Gastos - Vista de facturas

| Descripción | Este informe de Apptio BI proporciona visibilidad de los costes de facturación en nube antes de ser asignados a los consumidores. Este informe mostrará qué gastos son directos, compartidos y cuál es la tendencia de su presupuesto en todos los proveedores de nube. |
| --- | --- |
| Casos prácticos | Este informe resuelve los siguientes casos de uso:  Comprenda su gasto en la nube antes de que se haya asignado en toda su organización a las entidades consumidoras.  Analizar los gastos por costes directos y compartidos.  Realice un seguimiento de la variación presupuestaria de sus gastos en nube. |
| Personas | Este informe está dirigido principalmente a los profesionales del Centro de Excelencia de la Nube y de FinOps, así como a los ingenieros que desean tener una visibilidad completa del gasto de sus organizaciones. |
| Preguntas contestadas | El informe responde a las siguientes preguntas:  ¿Cuánto gasto mensualmente en todos mis proveedores de nube?  ¿Qué seguimiento hago del gasto en la nube con respecto al plan? ¿Cuál es mi variación presupuestaria?  ¿Qué proporción de mis gastos son directos o compartidos? |

TotalCost Gasto - Perspectiva del consumidor

| Descripción | Este informe de Apptio BI proporciona visibilidad de cómo se han asignado los datos de la nube en su organización a las entidades consumidoras (por ejemplo: unidades de negocio, productos, etc.). |
| --- | --- |
| Casos prácticos | Este informe resuelve los siguientes casos de uso:  Visualice sus costes compartidos entre productos, servicios y proveedores.  Comprender los gastos inmateriales que han sido capturados y categorizados por Cloudability TotalCost. |
| Personas | Este informe está dirigido principalmente a los profesionales del Centro de Excelencia de la Nube y de FinOps, así como a los ingenieros que desean tener una visibilidad completa del gasto de sus organizaciones. |
| Preguntas contestadas | El informe responde a las siguientes preguntas:  ¿Cuáles son los cinco servicios que más gastan?  ¿Cómo ha evolucionado mi coste por proveedor en el último año?  ¿Cuáles son los principales impulsores de los costes compartidos? |

## Compatibilidad con más regiones de « Datadog » - 20 de octubre de 2023

Esta versión incorpora la compatibilidad con más regiones de « Datadog » en Cloudability. Esto ampliaría las ventajas de la integración de ambos productos a todos los clientes de Cloudability que tengan Datadog implementado en regiones fuera de las que actualmente son compatibles.

Nuevas regiones compatibles

A continuación se enumeran las nuevas regiones de « Datadog » compatibles:

- ap1.datadoghq.com
- us3.datadoghq.com
- us5.datadoghq.com

La compatibilidad con las regiones existentes de Datadog se mantiene intacta, y los usuarios de Cloudability que las utilicen no necesitan realizar ninguna actualización por su parte.

- datadoghq.com
- datadoghq.eu

El proceso de acreditación de Datadog en Cloudability sigue siendo el mismo; la única novedad son las nuevas regiones que se pueden seleccionar en la lista desplegable. Para obtener más información sobre cómo conectar Datadog en Cloudability, consulta «[Conectar Datadog a Cloudability](../admin/connect-datadog.html) ».

## Cloudability Compatibilidad de Reservation Portfolio y RI Planner con Azure Cache para Redis y Synapse Analytics - 19 de octubre de 2023

Con esta versión, Cloudability amplía las recientes incorporaciones de los planes de ahorro de Azure, Cosmos DB y la compatibilidad con Databricks para incluir ahora Azure Cache para Redis y Synapse Analytics.

Cómo puede ayudarle esta función

Azure Los clientes de Cache para Redis y Synapse Analytics que optimizan sus gastos a través de reservas (tanto Redis como Synapse Analytics), y planes de precompra (Synapse Analytics) ahora pueden ver y gestionar sus reservas en la Cartera de Reservas. Cloudability amplía los servicios que soporta la Cartera de Reservas en la nube Azure en respuesta al creciente número de clientes que utilizan Azure. Al integrar « Azure Redis » y «Synapse Analytics», « Cloudability » ofrece a estos clientes ventajas adicionales a la hora de sacar partido a las reservas de compras realizadas en la nube de « Azure ».

Más información sobre el comunicado

Las reservas para « Azure » Cache para « Redis » y «Synapse Analytics» dedicadas a los grupos de SQL funcionan de manera similar a las reservas de « Azure » Compute, SQL y « Cosmos DB ». Se mantienen con regularidad y se facturan por horas.

Los planes de precompra de Azure Synapse Analytics funcionan de forma similar a Databricks. Estas reservas son créditos intercambiables que pueden utilizarse durante toda la duración de la reserva. A diferencia de la mayoría de las reservas, no se mantienen con regularidad. Nuestros KPI y encabezados de tabla se han ajustado para reflejar adecuadamente la información en torno a los créditos del plan de precompra y las SCU. Al igual que en Databricks, hemos añadido un tercer gráfico al panel de detalles para ayudar a comprender el desgaste de un compromiso determinado.

Nota:

La compatibilidad con el planificador de instancias reservadas para los planes de precompra de Azure Synapse Analytics no está disponible en este momento.

Nota:

Si aún no lo ha hecho, debe asegurarse de que se han habilitado las credenciales y permisos necesarios en Azure para que Cloudability pueda acceder a sus datos.

Nota: Clientes de EA: regeneren y vuelvan a ejecutar el script a nivel de EA siguiendo las instrucciones que se indican [aquí.](../admin/azure-cm-ea.html#azure-cm-ea__Configur)

Clientes de MCA: Configuren el lector de la cuenta de facturación según el rol siguiendo las instrucciones [que se indican aquí](../admin/azure-cm-ea.html#azure-cm-ea__grant).

## Mejoras en los informes de utilización para « AWS EBS » y GPU - 18 de octubre de 2023

Esta versión introduce varias métricas nuevas para los informes de utilización en AWS EBS y para la GPU en Cloudability.

Estas métricas recién introducidas son las siguientes:

- Balance de rá fagas - Proporciona información sobre el porcentaje de créditos de E/S (para gp2 ) o créditos de rendimiento (para st1 y sc1 ) que quedan en el cubo de ráfagas. Se utiliza sólo con volúmenes SSD de uso general ( gp2 ), HDD de rendimiento optimizado ( st1 ) y HDD frío ( sc1 ).
- Volumen consumido de operaciones de lectura y escritura : cantidad total de operaciones de lectura y escritura (normalizadas en unidades de capacidad de 256K ) consumidas en un periodo de tiempo especificado. Sólo se utiliza con volúmenes SSD de IOPS provisionadas.
- Porcentaje de rendimiento del volumen - El porcentaje de operaciones de E/S por segundo (IOPS) entregadas del total de IOPS aprovisionadas para un volumen de Amazon EBS. Sólo se utiliza con volúmenes SSD de IOPS provisionadas.

  Esta métrica no es compatible con los volúmenes Multi-Attach activados
- Utilización de la GPU - Porcentaje de tiempo durante un periodo de muestra en el que uno o más kernels de la GPU estaban ejecutándose.
- Utilización de la memoria de la GPU - Porcentaje de tiempo durante un periodo de muestra en el que se estaba escribiendo o leyendo memoria.

  Para obtener resultados satisfactorios con las métricas de la GPU, asegúrate de haber configurado [las métricas mínimas de la GPU](https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-gpu-monitoring-gpumon.html "(se abre en una pestaña o una ventana nueva)") como requisito previo.

Cómo puede ayudarle esta función

Esta versión mejora la compatibilidad con las métricas de utilización de AWS en Cloudability y permite a los clientes obtener información detallada sobre las métricas de utilización de AWS EBS y de las GPU.

## Compatibilidad con la integración de « Turbonomic » con « Cloudability » - 17 de octubre de 2023

Esta versión presenta la integración de Turbonomic con Cloudability, lo que permite disponer de funcionalidades adicionales de optimización en la nube y de datos de tu cuenta de Turbonomic dentro de Cloudability para ambos productos.

Cómo puede ayudarle esta función

Para los clientes actuales (y futuros) tanto de Cloudability como de Turbonomic, hay funciones y datos relacionados con la optimización que están disponibles en uno de los productos, pero no en el otro. Anteriormente no existía una integración lista para usar entre Cloudability y Turbonomic, por lo que los clientes de ambos productos tenían que acceder a cada uno de ellos por separado para poder utilizar las funcionalidades que ofrecía cada uno. Esta función pondrá en marcha el proceso de mejora de Cloudability, lo que permitirá a los clientes de ambos productos disponer de funcionalidades adicionales de Turbonomic y ver los datos directamente en la propia página Cloudability.

Más información sobre el comunicado

Para configurar las credenci Turbonomic es, selecciona la opción «Configuración » del menú de navegación principal de Cloudability y, a continuación, en el submenú desplegado, selecciona «Credenciales de proveedores ». En la página «Credenciales», selecciona la pestaña de navegación « Turbonomic » para iniciar el proceso de vincular las credenciales de una cuenta de Turbonomic a Cloudability. Una vez configurada la integración de Cloudability / Turbonomic, accede a la nueva página Turbonomic seleccionando la opción «Optimize » del menú principal de Cloudability y, a continuación, en el submenú desplegado, selecciona « Turbonomic ». Las nuevas funciones y datos se mostrarán a partir de los gráficos de «Inversiones necesarias y ahorros potenciales» y los valores correspondientes, disponibles en Turbonomic.

## Ampliación del soporte para la métrica Cloudability Cost (List) a todos los servicios de Azure - 13 de octubre de 2023

Esta versión introduce una mejora significativa en Cloudability con una métrica de costes más completa y coherente para los gastos en nube.

Nuestra métrica "Coste (Lista)" amplía ahora su soporte para cubrir todo el servicio Azure, además de su soporte existente para Azure Compute y Azure Database.

Cómo puede ayudarle esta función

"Coste (Lista)", es una métrica de costes de Cloudability que proporciona una visión coherente y "no adulterada" de los costes de la nube al excluir los beneficios de las reservas, las instancias Spot y los precios personalizados. En un entorno de nube en el que diversos tipos de descuentos y compromisos influyen continuamente en las tarifas pagadas por el uso de la nube, disponer de una métrica de costes "sin adulterar" tiene un valor incalculable. Hacerlo le permite influir en los descuentos o en la cobertura de los compromisos para que los precios de la nube sean coherentes. Esto no sólo ayuda a la planificación financiera, sino que también es eficaz para medir el impacto de sus iniciativas de eficiencia.

Más información sobre el comunicado

En esta versión, los cambios se centran en ofrecer una visión de futuro. Si está interesado en acceder a datos históricos, póngase en contacto con su equipo de cuentas o con el TAM para que le hagan un backfill.

## Apoyo a la métrica del coste (ajustado amortizado) en Cloudability AWS Inventario de recursos - 4 de octubre de 2023

Esta versión introduce la compatibilidad con la métrica Coste (ajustado amortizado) en la función Inventario de recursos de AWS.

Encontrará esta métrica como una de las columnas por defecto en la parrilla del informe AWS Inventario de recursos.

## Mejora de la detección de anomalías: Soporte para configurar alertas de Email/ PagerDuty en umbral de Porcentaje - 28 de septiembre de 2023

Esta versión introduce una nueva capacidad en la función de detección de anomalías que permite configurar alertas basadas en el umbral porcentual. Esta mejora complementa nuestro actual sistema de alertas, basado en valores absolutos, y le ofrece más flexibilidad y precisión en la gestión de sus alertas.

Cómo puede ayudarle esta función

Con esta actualización, ahora puede configurar las alertas para que se activen en función de umbrales porcentuales, además de las alertas de valor absoluto existentes. Esto significa que tiene la opción de configurar alertas basadas en un cambio porcentual específico con respecto a una línea de base o en valores absolutos, en función de sus necesidades de supervisión. Ambas combinaciones o cualquiera de ellas (Umbral porcentual, Valor absoluto) se admitirán para una vista determinada. Esta flexibilidad le permite adaptar su estrategia de alerta a sus casos de uso y requisitos específicos.

Tenga en cuenta que esta nueva capacidad de alerta de umbral porcentual no es retroactiva. Para aprovechar esta función, deberá establecer nuevas configuraciones para los umbrales porcentuales si son necesarios para su supervisión. Las configuraciones de alerta existentes basadas en valores absolutos seguirán funcionando como antes.

![pantalla de detección de anomalías](../../../../03-media/cloudability-premium/images/anomaly_detection_threshold_new.jpg)

## Mejora de la gestión de etiquetas Kubernetes en Cloudability Container Insights - 28 de septiembre de 2023

Esta versión introduce una mejora en la pestaña de etiquetas Kubernetes de la página Container Insights. Esta mejora perfeccionará la presentación de las etiquetas seleccionando los valores de etiqueta más relevantes y eliminando la concatenación de etiquetas.

Cómo puede ayudarle esta función

Actualmente, cuando los metadatos asociados al contenedor, incluidas las etiquetas de espacio de nombres, etiquetas de servicio, etiquetas de despliegue y etiquetas de nodo, comparten la misma clave de etiqueta pero presentan valores de etiqueta diferentes, estos valores se fusionan. Para mejorar esto, estamos introduciendo un cambio en nuestra cadena de producción. Este cambio garantizará que sólo se muestre el valor de etiqueta más relevante, eliminando la concatenación de etiquetas.

En los casos en que los metadatos asociados al contenedor posean claves de etiqueta con valores de etiqueta contradictorios, nuestro sistema dará prioridad al valor de etiqueta más relevante. La determinación de la pertinencia se basa en la granularidad del recurso. He aquí el orden de relevancia (de mayor a menor):

1. Pod
2. propietario del pod de primer nivel (por ejemplo, ReplicaSets, Daemonsets, Jobs)
3. propietario del pod de segundo nivel (por ejemplo, Deployments)
4. Kubernetes Service
5. Espacio de nombres
6. Nodo

Más información sobre el comunicado

Tras la puesta en producción de este cambio, los usuarios ya no encontrarán valores concatenados en la pestaña Etiquetas de la página Información sobre contenedores para los datos recibidos después de la fecha de puesta en producción. Además, los usuarios pueden notar mayores asignaciones de costes para los valores de las etiquetas que antes se reducían artificialmente debido a que el coste se asignaba a valores concatenados.

- Los datos históricos que contengan valores de etiqueta concatenados permanecerán inalterados.
- GKE Es posible que los clústeres sigan mostrando valores de etiqueta concatenados en el módulo de informes.

Creemos que esta mejora aumentará significativamente la claridad y precisión de la representación de las etiquetas en Container Insights, ofreciendo una experiencia de usuario más ágil e informativa. Le agradecemos su continuo apoyo mientras trabajamos para mejorar nuestra plataforma.

Nota:

Aunque nuestro objetivo es eliminar los valores de etiqueta concatenados, hay casos excepcionales en los que la concatenación sigue produciéndose. Esto incluye los casos en los que un pod está asociado a dos o más servicios diferentes de Kubernetes, y estos servicios tienen valores de etiqueta en conflicto sin que haya otro objeto más relevante que tenga preferencia.

Si tiene alguna pregunta o necesita más información, no dude en ponerse en contacto con el equipo de su cuenta o con el servicio de asistencia.

## Capacidad de clasificación en Cloudability Inventario de recursos - 25 de septiembre de 2023

Esta versión introduce las opciones de clasificación manual, mucho más cómodas, en la función de Inventario de recursos de Cloudability lanzada en julio de 2023. En aquel entonces, la función sólo tenía la opción predeterminada de ordenación automática por Coste (Total) descendente y, con esta versión, los usuarios pueden ordenar sus datos de inventario basándose en cualquiera de las columnas deseadas (dimensiones o métricas) que aparecen en la cuadrícula del informe de inventario.

Ahora los usuarios pueden seleccionar cualquiera de los encabezados de columna que aparecen en la cuadrícula del informe de inventario para ordenar los datos de inventario en orden alfabético (para columnas basadas en texto) o ascendente/descendente (para columnas basadas en números). La opción se indica mediante el habitual icono en forma de flecha, como se muestra a continuación:

![captura de pantalla del inventario de recursos de cloudability](../../../../03-media/cloudability-premium/images/cldy-res-inv-sorting.jpg)

Consulte [Inventario de recursos](../product/aws-resource-inventory.html) para obtener más información sobre la función original.

## Cloudability para OCI - Gestión de costes - 14 de septiembre de 2023

Apptio anuncia una importante mejora de su paquete de productos Cloudability, que ofrece a los profesionales de FinOps acceso inmediato a los datos de costes y uso de Oracle Cloud Infrastructure (OCI) de forma nativa dentro de la plataforma Cloudability.

Cómo puede ayudarle esta función

Esta versión permite a los clientes de OCI:

- Asignar automáticamente todos los costes de OCI a la empresa en función de sus normas específicas, aprovechando las dimensiones empresariales de Cloudability
- Analice su gasto en OCI y mejore la propiedad de los equipos aprovechando los análisis a nivel de recursos, los paneles interactivos multi-nube y las vistas personalizadas
- Impulsar la responsabilidad financiera estableciendo presupuestos de ICO y notificaciones de eventos

  ![captura de pantalla de oci True Cost Explorer](../../../../03-media/cloudability-premium/images/oci_rn.jpg)

Más información sobre el comunicado

Si ya eres cliente de OCI, puedes empezar tu viaje de gestión de costes añadiendo credenciales para tu tenencia siguiendo las instrucciones de [Connect Oracle Cloud](../admin/connect-oracle-cloud.html).

Por defecto, Cloudability ingestará el mes actual de datos OCI después de que sus credenciales sean validadas. Si desea que se incorporen más meses de datos, póngase en contacto con el equipo de Apptio, que estará encantado de ayudarle.

Si necesitas acceso programático para gestionar tus credenciales de OCI, consulta nuestra [documentación](../api-v3/getting_started_with_the_cloudability.html) sobre la API pública.

Para obtener más información sobre cómo gestionar los costes de OCI en Cloudability, únase a la conversación en la [comunidad Apptio](https://community.apptio.com/blogs/soline-plichta/2023/09/14/cloudability-for-oci-cost-management-faq "(se abre en una pestaña o una ventana nueva)").

## Cloudability Computar Tipo de Instancia/ Filtrado de Exclusión de Familia en Preferencias de Redimensionamiento - 30 de agosto de 2023

Esta versión proporciona un nuevo ajuste global en las Preferencias de Asignación de Tamaño que permite excluir recomendaciones de cálculo para un tipo de instancia o familia de instancias específico en función de los valores introducidos.

Cómo puede ayudarle esta función

Anteriormente, Cloudability sólo proporcionaba filtrado por tipo de instancia/familia para las recomendaciones de dimensionamiento de derechos de computación a nivel de página y sólo para las principales recomendaciones dadas, sin posibilidad de filtrar globalmente o por recomendación individual. Esta versión proporciona una nueva configuración global en las Preferencias de Asignación de Derechos para excluir recomendaciones de cálculo que contengan tipos/familias de instancia específicos en función de los valores de exclusión introducidos.

Más información sobre el comunicado

El filtrado y/o exclusión relacionado con la instancia ya existe localmente en las páginas de asignación de derechos de computación utilizando los filtros Familia de Instancias (Nuevo) y Tipo de Instancia (Nuevo). Sin embargo, éstos sólo filtran las recomendaciones que tienen una recomendación superior con estos valores. Esta nueva funcionalidad global de las Preferencias de Asignación de Tamaño le proporciona un mecanismo para excluir todas las recomendaciones de cálculo que cumplan los criterios (valores) introducidos por usted, independientemente de que la recomendación sea una recomendación principal o una de las muchas opciones de recomendación contenidas en el panel de detalles de asignación de tamaño. Existen limitaciones intencionadas y de diseño sobre qué recomendaciones son aplicables a este mecanismo de exclusión: las recomendaciones de "terminar" y "ninguna acción" no estarán sujetas a la lista de exclusión, ya que en realidad no se está recomendando un cambio en el tipo/familia de instancia.

En el menú de navegación principal Cloudability, en la opción de menú Configuración, seleccione la opción Preferencias de redimensionamiento. En las preferencias de Compute ( VM ), hay una opción que permite «Excluir las recomendaciones en las que el tipo de instancia recomendado contenga los siguientes valores». En esta opción, habrá cuadros de texto en los que podrá introducir valores adicionales que excluirán cualquier recomendación de cálculo en la que el tipo de instancia/familia contenga estos valores.

## Analice la contribución al coste de cada tipo de recurso en Container Insights - 18 de agosto de 2023

Esta versión introduce la posibilidad de realizar un seguimiento de los costes asociados a cada tipo de recurso, como la CPU y la memoria, dentro de Container Insights de Cloudability.

Cómo puede ayudarle esta función

Con esta nueva función, podrá ver información exhaustiva sobre los costes de una serie de parámetros de uso, como memoria, CPU, GPU, sistema de archivos, volumen persistente (PV), recepción y transmisión de red.

Más información sobre el comunicado

Las principales características de esta mejora son :

- Seguimiento de costes: Entendemos la importancia de gestionar los gastos, por lo que hemos integrado el seguimiento de costes para una variedad de métricas de uso directamente dentro de la página Container Insights. Esto le permite tomar decisiones informadas sobre la asignación y optimización de recursos.
- Métricas de costes flexibles: Esta función admitirá tanto la métrica de Coste Utilizado como la de Coste Compartido para cada una de las métricas de Uso (por ejemplo: Coste Utilizado de CPU, Coste Compartido de CPU), ofreciéndole la flexibilidad de adaptar el análisis de costes a sus preferencias.
- Amplia cobertura de métricas: Las métricas cubiertas por esta mejora incluyen CPU, memoria, GPU, sistema de archivos, volumen persistente (PV), recepción de red y transmisión de red. Esta cobertura integral le permite obtener una visión profunda de las implicaciones de costes de cada aspecto de su entorno en contenedores.
- Análisis de costes históricos: A partir del 18 de agosto de 2023, se podrá acceder a los datos de costes históricos de todas las métricas compatibles. Esto le permite seguir las tendencias de los costes a lo largo del tiempo y tomar decisiones bien fundadas sobre la utilización de los recursos.
- Compatibilidad con puntos finales públicos: En esta versión, también podrá acceder a estas métricas enriquecidas a través de nuestros puntos finales públicos, lo que garantiza una integración perfecta con los flujos de trabajo existentes para Cloudability API.

Puede seleccionar/deseleccionar manualmente columnas de costes adicionales como se indica a continuación.

![captura de pantalla de las métricas de visibilidad de costes](../../../../03-media/cloudability-premium/images/cost_visibility_usage_metrics_2.jpg)

Nota:

Si tiene alguna pregunta o necesita ayuda, póngase en contacto con el equipo de su cuenta o con el servicio de asistencia.

## Comentarios sobre la mejora de Rightsizing y Rightsizing ROI en Cloudability - 14 de agosto de 2023

Esta versión proporciona mejoras añadidas para la funcionalidad Rightsizing /Rightsizing ROI Comments.

Cómo puede ayudarle esta función

Esta funcionalidad añade un indicador en el icono "Comentarios" cuando se han añadido comentarios y existen para una recomendación. Además, los comentarios que existan para cualquier recomendación específica mostrada en la página Redimensionamiento o en la página Retorno de la inversión se fusionarán y cualquier comentario realizado en cualquiera de las dos páginas aparecerá en ambas.

Más información sobre el comunicado

Hasta esta versión, no se mostraba ningún indicador cuando se hacía un comentario sobre una recomendación de Rightsizing. Para ver si se había hecho algún comentario, había que hacer clic en el icono de comentarios y abrir el modal de comentarios. Esta versión introduce un indicador en el icono de comentarios de la tabla siempre que haya comentarios disponibles.

Anteriormente, los comentarios realizados sobre un recurso específico se almacenaban por separado cuando se realizaban en la página de Asignación de derechos y en la página de ROI de Asignación de derechos. Para evitar confusiones, los comentarios existentes sobre recursos específicos se fusionarán en ambas páginas para crear un único archivo de "Comentarios". A partir de ahora, cada vez que se añada un comentario en cualquiera de las dos páginas, aparecerá en ambas y formará parte de un único archivo de comentarios para ese recurso específico.

Nota:

El indicador de comentarios aparecerá en el icono de comentarios de un recurso en cualquier tabla de asignación de derechos en la que existan comentarios. Esto incluye las páginas Rightsizing y Rightsizing ROI, así como cualquier subpágina aplicable.

## Apptio BI disponible en Cloudability (BETA) - 9 de agosto de 2023

Esta versión integra la completa Apptio BI con Cloudability, eliminando la necesidad de navegar entre varias aplicaciones.

Puede acceder a todos sus informes de Apptio BI, incluidos los informes basados en casos de uso comunes de FinOps, funciones innovadoras y analizar todas las fuentes de datos directamente en Cloudability.

![captura de pantalla de apptio BI Cldy](../../../../03-media/cloudability-premium/images/cldy-bi-8.jpg)

Nota:

Esta versión ya está disponible para los clientes de Cloudability. Si deseas integrar Apptio BI en tu aplicación Cloudability, ponte en contacto con tu equipo de atención al cliente para obtener más ayuda y asesoramiento.

## Cloudability - Presentación de tres nuevas dimensiones Cloudability - 4 de agosto de 2023

En esta versión, se introducen tres nuevas dimensiones para Cloudability Azure Datos de costes específicos.

Cómo puede ayudarle esta función

Estas dimensiones proporcionan información más detallada sobre su gasto en Azure. Estas dimensiones específicas de Azure son:

1. Azure Nombre de la orden de reserva : Esta dimensión le permite rastrear y analizar los costes asociados a los diferentes nombres de órdenes de reserva de Azure. También ayuda a comprender mejor el impacto de las distintas órdenes de reserva en el gasto total y, por tanto, a optimizar las reservas en consecuencia.
2. Número de pieza : La dimensión Número de pieza proporciona una visibilidad detallada de los costes basada en los números de pieza específicos de Azure asociados a sus recursos. Utilizando esta dimensión, puede asignar mejor los costes y tomar decisiones informadas sobre la utilización de los recursos.
3. Nombre de la reserva : Con la dimensión Nombre de la reserva, ahora puede analizar y gestionar los costes relacionados con las diferentes reservas de Azure. También ayuda a obtener información sobre cómo se utilizan las reservas en los distintos recursos y, de este modo, tomar medidas proactivas para optimizar la utilización de las reservas.

Más información sobre el comunicado

Estas nuevas dimensiones son específicas de los datos de costes de Azure y estarán disponibles exclusivamente para los recursos de Azure. Forman parte de nuestros esfuerzos continuos por ofrecer una capacidad de gestión de costes completa y centrada en Azure.

## Soporte de GPU para Container Cost Insights- 31 de julio de 2023

Esta versión introduce visibilidad en el uso de la Unidad de Procesamiento Gráfico (GPU) y los costes asociados para las cargas de trabajo de Kubernetes para Cloudability Container Insights. Esta funcionalidad permite a los usuarios desplegar contenedores en máquinas virtuales respaldadas por GPU, lo que les ayuda a maximizar las ventajas de las capacidades de procesamiento gráfico dedicadas para tareas como el aprendizaje automático, el procesamiento de datos, el renderizado y otras cargas de trabajo de alta carga computacional.

Cómo puede ayudarle esta función

Esta versión introduce una nueva métrica "GPU" en la tabla de uso de la página Container Insights. Con este añadido, puedes ver fácilmente el número de GPUs asignadas a nivel de clúster, espacio de nombres y etiqueta. Los costes asignados a los valores de espacio de nombres y etiquetas consideran ahora un conjunto actualizado de ponderaciones que tienen en cuenta el precio relativo de las GPU en cada nodo. Dado que las distintas máquinas virtuales utilizan hardware diferente, el coste de una GPU está, por lo tanto, vinculado a cada familia de « VM » y al tipo específico de GPU que utiliza dicha familia.

![soporte gpu contenedores captura de pantalla](../../../../03-media/cloudability-premium/images/gpu_support_container_insights.jpg)

Más información sobre el comunicado

Para comprender mejor estos cambios, comparemos la distribución anterior de los costes con la actual.

Anteriormente, nuestro modelo tenía en cuenta la utilización de CPU, memoria, red y disco, lo que resultaba suficiente para las máquinas virtuales estándar. Sin embargo, en las máquinas virtuales respaldadas por GPU los costes pueden ser sustancialmente más elevados, a menudo dos o tres veces superiores a los de máquinas virtuales similares sin GPU. Sin tener en cuenta el impacto de las GPU y quiénes las utilizaban, faltaba una parte de la historia. La siguiente tabla muestra cómo se han mejorado las ponderaciones para una instancia concreta de EC2 respaldada por GPU con este lanzamiento.

|  | Nodo CPU | Nodo CPU peso | Memoria de nodo | Memoria de nodo Peso | GPU de nodo | Nodo GPUs Peso |
| --- | --- | --- | --- | --- | --- | --- |
| Anterior | 8 | 25 % | 40 GB | 75% | 2 | 0 % |
| Actual | 8 | 12.5% | 40 GB | 37.5 | 2 | 50 % |

Con las ponderaciones actualizadas, se ha determinado que la GPU contribuye con el 50 % del coste VM, mientras que la memoria se ha reducido al 37.5 % y la CPU al 12.5 %. El ejemplo siguiente muestra cómo esto afecta a la asignación de costes a tres cargas de trabajo hipotéticas que consumen dicho « VM ».

| Planificación de la carga de trabajo | Consumo de CPU | Utilización de memoria | Utilización de GPU | Asignación de costes anterior | Asignación de costes actualizada |
| --- | --- | --- | --- | --- | --- |
| A | 2 millones de rupias | 16 GB | 1 | 36.25% | 43.125% |
| B | 2 millones de rupias | 8 GB | 1 | 21.25% | 35.625% |
| C | 4 millones de rupias | 16 GB | 0 | 42.5% | 21.25% |

Como se desprende del ejemplo anterior, el modelo actualizado refleja ahora el coste real de la utilización de la GPU, lo que se traduce en una asignación de costes más precisa y justa entre las distintas cargas de trabajo. Las cargas de trabajo A y B muestran un aumento del precio, lo que refleja su utilización del recurso relativamente caro de la GPU. Esta mejora le proporciona una mayor visibilidad de los costes de sus recursos y permite una mejor gestión de los costes.

Nota:

Esta versión es compatible con las cargas de trabajo que utilizan la GPU y que se ejecutan en AWS y GCP. En concreto, el caso de uso que se aborda en esta versión es el de las GPU totalmente reservadas (la compatibilidad con [la implementación MIG de Nvidia](https://www.nvidia.com/en-au/technologies/multi-instance-gpu/ "(se abre en una pestaña o una ventana nueva)") no forma parte de esta versión). Estamos trabajando activamente para incorporar la compatibilidad total con máquinas virtuales con soporte de GPU que se ejecutan en Azure. Actualmente, en el caso de las máquinas virtuales de Azure, se muestra la métrica de uso relativa al consumo de la GPU, pero las ponderaciones de coste no se han actualizado. Esta actualización se refleja a partir del 1 de agosto de 2023 sin ningún impacto en el uso y coste históricos.

## Ajuste de la capacidad de los grupos de instancias gestionadas de « GCP » - 25 de julio de 2023

Esta versión incorpora recomendaciones de ajuste de recursos de « Cloudability » para los grupos de instancias gestionadas (MIG) de GCE de GCP.

Anteriormente, las recomendaciones de «Rightsizing» se proporcionaban únicamente para cada recurso individual, incluso si la máquina había sido generada por un único «clúster» —como un grupo de instancias gestionadas de GCP — y se utilizaba exclusivamente dentro de él. Con esta versión, la herramienta « Cloudability Rightsizing» ofrece recomendaciones para los grupos de migración (MIG) de GCE de GCP. Los clientes pueden llevar a cabo acciones en el propio grupo, que se aplicarán automáticamente a los recursos creados por ese grupo.

Cómo puede ayudarle esta función

GCP Los clientes que utilizan MIG ahora pueden ver automáticamente recomendaciones específicas para ahorrar a nivel de configuración de grupo, en lugar de solo a nivel de cada recurso individual.

El ahorro del grupo será potencialmente mucho mayor que cada recurso dentro del grupo. Además, los recursos que forman parte de grupos de instancias gestionadas se configuran como un grupo, por lo que proporcionar recomendaciones a nivel de grupo y a nivel de máquina virtual individual es óptimo, ya que estos grupos se configuran como una entidad completa.

Más información sobre el comunicado

GCE MIG está disponible en la pestaña « GCP », dentro de la sección «Rightsizing ». GCP Los datos de MIG y las recomendaciones de ajuste de tamaño se muestran automáticamente si el cliente utiliza MIG de GCP.

![GCP Captura de pantalla de Rightsing](../../../../03-media/cloudability-premium/images/mig-help-image-2.jpg)

Esta experiencia de usuario es similar a la funcionalidad de redimensionamiento existente en Apptio para los recursos individuales de la CME. La tabla principal muestra todos los grupos con gastos en el tiempo especificado. Por defecto, los grupos se ordenan por ahorro de costes. Los clientes pueden empezar por la parte superior de la lista para ver los grupos con mayor potencial de ahorro.

Nota:

Las recomendaciones para los recursos MIG no se duplicarán en varios servicios (como CME y CME MIG). Si un recurso forma parte de un grupo de instancias gestionadas, dejará de aparecer en las recomendaciones estándar de ajuste de recursos de GCE de GCP. Sólo aparecerá bajo las recomendaciones de redimensionamiento MIG. En estas recomendaciones sólo se incluirán los recursos a la carta.

## Compatibilidad con la utilización de la GPU para el ajuste de recursos de « GCP » - 25 de julio de 202

Esta versión continúa la mejora correlacionada con la GPU de las recomendaciones de redimensionamiento de Cloudability mediante la ingesta y la utilización del procesamiento y la memoria de la GPU.

Para las cargas de trabajo modernas, como el aprendizaje automático, los clientes encuentran cada vez más útiles las máquinas virtuales en la nube no sólo con CPU, sino también con GPU. Con esta versión, los clientes de « GCP » cuyos datos se importen a « Apptio » a través de GCP o Datadog también podrán incluir sus datos de GPU para recibir recomendaciones mejoradas sobre el dimensionamiento óptimo.

Cómo puede ayudarle esta función

A partir de ahora, los clientes de « GCP » que dispongan de instancias de computación con GPU podrán recibir recomendaciones de ahorro basadas en las métricas de GPU recopiladas por « Apptio », así como recomendaciones sobre tipos de instancia basadas en dichas métricas para los tipos de instancia que incluyan GPU. Estas métricas aportan una nueva dimensión al motor de recomendaciones de Cloudability, lo que permite ofrecer ahorros adicionales a nuestros clientes. Anteriormente, los datos de la GPU no se tenían en cuenta a la hora de ofrecer recomendaciones sobre el dimensionamiento adecuado de la capacidad de cálculo de « GCP ».

Más información sobre el comunicado

En el menú de navegación principal de « Cloudability », selecciona la opción «Optimizar » > selecciona «Rightsizing» y, a continuación, selecciona la pestaña « GCP ».

Las recomendaciones de redimensionamiento para instancias CME con GPU se mostrarán automáticamente si están configuradas correctamente y disponibles. Habrá una pequeña adición a la vista de "detalles" de la recomendación para instancias con GPU, ya que ahora habrá gráficos adicionales tanto para la GPU (%) como para la utilización de la memoria de la GPU.

 Requisitos previos 

1. Cada « VM » debe tener [GPU conectadas](https://cloud.google.com/compute/docs/gpus/create-vm-with-gpus "(se abre en una pestaña o una ventana nueva)").
2. Cada VM debe tener [instalado](https://cloud.google.com/compute/docs/gpus/install-drivers-gpu#verify-driver-install "(se abre en una pestaña o una ventana nueva)") un controlador de GPU.
3. Cada servidor « VM » debe tener instalado « Python » « 3.6 » o una versión posterior.
4. Cada VM debe tener instalados los paquetes necesarios para la creación de entornos virtuales Python.

   N1 no formará parte de esta versión.

## Cambio en la dirección de correo electrónico del remitente para los usuarios de Cloudability - 20 de julio de 2023

arlier Cloudability los usuarios suscritos a correos electrónicos recibirían correos electrónicos de no-reply-support@apptio.com. A partir de esta versión, recibirán correos electrónicos de no-reply@apptio.com debido a las recientes actualizaciones de nuestro servicio de correo electrónico. Cloudability los clientes sólo tendrían que añadir esta nueva dirección de correo electrónico a su lista de confianza, si fuera necesario.

## Cloudability Asistencia para la cartera de reservas de Azure Databricks - 20 de julio de 2023

Con esta versión, Cloudability amplía las recientes incorporaciones de los planes de ahorro Azure y la compatibilidad con Azure Cosmos DB para incluir ahora Azure Databricks.

Cómo puede ayudarle esta función

Azure Databricks Los clientes que optimizan su gasto mediante planes de compra anticipada ya pueden consultar y gestionar sus reservas en la «Cartera de reservas». Cloudability amplía los servicios que soporta la Cartera de Reservas en la nube Azure en respuesta al creciente número de clientes que utilizan Azure. Al incorporar Azure Databricks, Cloudability ofrece a estos clientes un valor añadido a la hora de aprovechar al máximo la compra de reservas en la nube de Azure.

Más información sobre esta versión

Debido a la diferencia en la forma en que estas reservas se aplican al uso, nuestros KPI y encabezados de tabla se han ajustado para reflejar adecuadamente la información en torno a los créditos del plan de precompra, DBCU. Además, hemos añadido un tercer chat en el panel de detalles para ayudar a comprender el desgaste de un compromiso determinado.

Nota: En este momento no hay soporte disponible para el Planificador de Instancias Reservadas.

Nota:

Si aún no lo han hecho, los clientes deben asegurarse de que se han habilitado las credenciales y permisos necesarios en Azure para que Cloudability pueda acceder a sus datos.

Clientes de MCA: Configuren el lector de la cuenta de facturación según el rol siguiendo las instrucciones que se indican [aquí](../admin/azure-cm-ea.html#azure-cm-ea__grant).

Clientes de EA: regeneren y vuelvan a ejecutar el script a nivel de EA siguiendo las instrucciones que se indican [aquí](../admin/azure-cm-ea.html#azure-cm-ea__Configur).

## Compatible con la notificación por correo electrónico a los asignatarios de entradas - 17 de julio de 2023

Esta versión permite que los asignatarios de tickets para la integración nativa de Rightsizing ROI se especifiquen a través de una dirección de correo electrónico y reciban una notificación por correo electrónico cuando se les asigne un ticket de Rightsizing ROI.

Anteriormente, Rightsizing ROI solo estaba disponible con una integración de Jira Cloud. Tras el lanzamiento de la funcionalidad nativa Rightsizing ROI el año pasado, las notificaciones por correo electrónico para los asignatarios de tickets no estaban disponibles, ya que este mecanismo se gestionaba a través de Jira. Se está añadiendo un mecanismo nativo independiente para notificar a los asignatarios de tickets que forman parte de la integración nativa cuando se asigna un ticket para su revisión y/o procesamiento.

Cómo puede ayudarle esta función

Esta funcionalidad permite a los usuarios de Cloudability adjuntar una dirección de correo electrónico a los asignatarios nativos de tickets de Rightsizing ROI para que dichos asignatarios puedan recibir una notificación por correo electrónico cuando se les asigne un ticket de Rightsizing ROI. Las direcciones de correo electrónico disponibles se seleccionarán entre los usuarios existentes de Frontdoor.

Más información sobre esta versión

La funcionalidad está disponible cuando se asignan tickets ROI nativos. En la página de ROI de Rightsizing, el usuario puede seleccionar el botón de detalles de una recomendación de ROI de rightsizing rastreada y, a continuación, seleccionar un asignado con una dirección de correo electrónico que permita las correspondientes notificaciones por correo electrónico. Además de esto, la funcionalidad está disponible cuando el usuario pasa el ratón por encima de los detalles de la recomendación a seguir en Rightsizing ROI y selecciona Create Cloudability Issue.

## AWS Inventario de recursos - 7 de julio de 2023

Esta versión permite a los usuarios acceder a una lista fidedigna de los recursos en nube utilizados y facturados durante determinados periodos de notificación. También permite la flexibilidad de construir listas a partir de recursos que abarcan múltiples cuentas de diferentes dimensiones y métricas.

Cómo puede ayudarle esta función

Esta función, disponible para cada recurso en la nube, unifica la facturación, la utilización y los metadatos descriptivos, y proporciona por primera vez una visión completa del inventario en los informes de Cloudability para los recursos de non-EC2.

Más información sobre el comunicado

Como parte de esta versión, la función de inventario de recursos de AWS debe habilitarse para una organización Cloudability desde la consola Active Admin. Por defecto, sólo los administradores de Cloudability podrán acceder a esta función. Sin embargo, también puede concederse a cualquier rol personalizado asignándole el permiso titulado AWSResourceInventoryFullAccess al mismo.

Nota:

Los « AWS » compatibles con esta función son: EC2, EBS, S3, RDS y Redshift.

Una vez activada la función de inventario de recursos desde el administrador activo, los datos pueden tardar entre 2 y 3 días laborables en empezar a aparecer en los informes de inventario.

Informe de inventario Medidas

- Las medidas se refieren a dimensiones, métricas o etiquetas extraídas de los datos de facturación. Puede incluir hasta 20 columnas de este tipo para un informe individual.
- Cada servicio de AWS admite un conjunto específico de dimensiones y métricas.
- Puede filtrar los informes de inventario utilizando cualquiera de las medidas disponibles en la función.
- Los datos de inventario se ordenan por Coste (Total) en orden descendente (Por defecto).

Indicadores clave de rendimiento en los que se puede hacer clic para filtrarlos rápidamente

Para cada servicio (por ejemplo: EC2, EBS etc.), Los indicadores clave de rendimiento (KPI) se muestran en la parte superior y le proporcionan información resumida clave, como los recursos nuevos u ociosos del mes en curso.

Puede ver y filtrar los informes de Inventario en función de estos KPI para un análisis más detallado.

Ventanas de fecha de informe de inventario

Al activar esta función, los datos de inventario de recursos se volverán a rellenar al principio del mes en curso. Los datos de Inventario suelen estar disponibles para tres meses, incluido el actual y los dos anteriores.

Nota:

Puedes exportar los informes en formato « CSV », incluyendo tantas columnas como sean pertinentes para un servicio concreto, sin ningún tipo de restricción.

## Asignación de costes de contenedores - Mejora de la ponderación CPU/Memoria para la asignación de espacios de nombres y etiquetas - 3 de julio de 2023

Esta versión mejora el modo en que los costes se asignan a los espacios de nombres y etiquetas individuales, ajustándose mejor al modo en que los proveedores de la nube cobran las máquinas virtuales subyacentes.

Mejoras en la imputación de costes de los contenedores

Con esta versión, Cloudability ha mejorado el modo en que se asignan los costes a los valores individuales de Namespace y Label para que coincidan mejor con el modo en que los proveedores de la nube cobran las máquinas virtuales subyacentes. El proceso de desglose y asignación del coste de cada VM consiste en repartir el coste total entre los recursos que lo componen (CPU, memoria, red, etc.) y, a continuación, asignar el coste a cada Namespace y Label en función de la cantidad de estos recursos que hayan consumido. La memoria y la CPU, en conjunto, constituyen el componente más importante (85 %) de los costes de VM.

Hasta ahora, Cloudability utilizaba una proporción estándar para dividir este componente, independientemente del tipo de « VM » (lo que hacía que los costes se inclinaran hacia la memoria). Con esta versión, Cloudability ha hecho que la proporción dependa del tipo de máquina: en las máquinas optimizadas para cálculo, la proporción se inclinará más hacia la CPU en comparación con las máquinas optimizadas para memoria. Esto se ha conseguido fijando los precios de la CPU (horas-núcleo) y la memoria (GB-hora) basándose en un análisis de las diferentes categorías de VM y en cómo estos dos tipos de recursos influyen en los precios de VM. El resultado neto es una representación más precisa de la contribución de cada espacio de nombres y etiqueta a los costes.

Más información sobre esta versión

Esta versión no afecta a la asignación de costes a nivel de clúster. Para obtener más información, únete a la conversación en la [comunidad « Apptio](https://community.apptio.com/home "(se abre en una pestaña o una ventana nueva)") ».

## Contenedor - Asignación de costes para EBS apoyado- 3 de julio de 2023

Esta versión introduce cambios en la página de información del contenedor en Cloudability para ofrecer información más completa sobre la métrica Filesystem.

Cómo puede ayudarle esta función

Anteriormente, Filesystem era la combinación de almacenamiento efímero y persistente para varias construcciones de Kubernetes, incluyendo Cluster, Namespace, etiquetas y Servicios. Con estas actualizaciones, Doing this nos permite proporcionar asignaciones de costes de última generación de uno de los generadores de costes más significativos ( EBS ) a sus clústeres EKS.

Estas mejoras pretenden ofrecer una visión más detallada y holística de la utilización de los recursos y la asignación de costes en entornos de contenedores, lo que permite optimizar y gestionar mejor los gastos en la nube. En esta versión, apoyaremos específicamente los recursos de EBS ( AWS ).

Como parte de estos cambios, Cloudability introduce una dimensión adicional denominada Volumen persistente como columna en la página de insights. Esta nueva dimensión representará con precisión las asignaciones relacionadas con los Filesystems.

Con estas actualizaciones, todo el almacenamiento efímero se categorizará bajo la métrica Filesystem existente, mientras que el uso de Persistent Volume se reflejará bajo la nueva métrica Persistent Volume.

También puede observar que las asignaciones de costes cambian en torno a los espacios de nombres, servicios y etiquetas, especialmente en torno a las cargas de trabajo que utilizan una cantidad muy grande o muy pequeña de Filesystem.

Para aclarar la distinción en las agrupaciones EKS:

| Sistema de archivos | Volúmenes persistentes |
| --- | --- |
| Recurso  Normalmente respaldado por un volumen raíz EBS  Ocasionalmente respaldado por EC2 Instance Store en tipos de instancia más antiguos | Recurso  Soportado  EBS volumen (versiones CSI y en árbol)  Los servicios comunes de AWS aún no son compatibles  Amazon EFS  Amazon FSx |
| Casos de uso típicos  Registros  Directorios Scratch o tmp  Sistema de archivos vinculado al ciclo de vida de sus cargas de trabajo | Casos de uso típicos  Almacenamiento que debe persistir a lo largo de los ciclos de vida de los pods  Conjuntos de estados |

Nota:

Para esta versión

- La dimensión Volumen persistente sólo admite servicios EBS ( AWS ). En consecuencia, para todos los demás servicios y proveedores de nube, el valor reflejado en esta dimensión se denota como No disponible.
- Estas actualizaciones proporcionan una visión más granular de las asignaciones de Filesystem y permiten un mejor análisis y optimización de costes en entornos de contenedores.
- Además de introducir la nueva métrica de volumen persistente para el análisis del uso, también estamos renovando la interfaz de usuario (IU) aprovechando la cuadrícula AG.
- Como parte de esta mejora de la interfaz de usuario, los usuarios podrán personalizar las columnas que aparecen en la página de información. Podrán elegir las columnas concretas que desean ver, lo que les permitirá personalizar la vista en función de sus preferencias y necesidades. Esta función proporcionará a los usuarios un mayor control sobre la información mostrada y agilizará su proceso de análisis.

![pantalla de imputación de costes de contenedores](../../../../03-media/cloudability-premium/images/ebs-new.jpg)

Nota:

- Los recursos (volúmenes o nodos) que cuesten menos de $0.01/hr no se reflejarán en los costes totales del clúster.
- l panel de detalles permanece inalterado, salvo por la adición de información relacionada con la recién introducida dimensión Volumen persistente.

## Cartera de RI y soporte del Planificador para Azure Cosmos DB - 22 de junio de 2023

Esta versión amplía la compatibilidad de los servicios de Azure para incluir Azure Cosmos DB en RI Portfolio y Planner. RI Planner ofrece a los clientes de Cloudability recomendaciones para las instancias de Azure Cosmos DB.

Cómo puede ayudarle esta función

Los clientes pueden ver el ahorro y las ventajas de la compra de RI propuesta, y filtrar las recomendaciones en función del periodo de referencia, la región, el alcance, las condiciones y las cuentas. La cartera de reservas proporcionará a los clientes de Cloudability su actual cartera de reservas para las instancias de Azure Cosmos DB junto con los demás servicios para los que actualmente proporcionamos soporte.

Cloudability amplía los servicios que admiten Reservation Portfolio y Reserved Instance Planner en la nube Azure en respuesta al creciente número de clientes que utilizan Azure. Al incorporar Azure Cosmos DB, Cloudability proporciona a estos clientes un valor adicional en términos de realización del valor de la compra de reservas en la nube Azure. Además, la incorporación de Azure Cosmos DB proporciona a los clientes información práctica y recomendaciones que mejoran sus resultados empresariales, todo ello desde un único panel de control.

Más información sobre el comunicado

Como parte de esta versión, la función Planificador/Recomendación se encontrará ahora en la opción de menú Optimizar > Planificador de instancias reserv adas, mientras que la función Cartera seguirá estando en la opción de menú Información > Cartera de reservas.

Nota:

Si aún no lo han hecho, los clientes deben asegurarse de que se han habilitado las credenciales y permisos necesarios en Azure para que Cloudability pueda acceder a sus datos.

## Compatibilidad con las versiones Kubernetes 1.26 y 1.27 - 15 de junio de 2023

Con esta versión, Container Cost Allocation es oficialmente compatible con la versión Kubernetes 1.26 para todos los proveedores y la versión 1.27 en Amazon Elastic Kubernetes Service (EKS).

Cómo puede ayudarle esta función

Esta función permitirá a los clientes conocer el uso que hacen de los recursos de sus contenedores y el coste de sus clústeres con las dos versiones de Kubernetes.

Los clientes ya deberían poder descargar e implantar nuestro agente de métricas utilizando el flujo de trabajo de aprovisionamiento habitual.

![Captura de pantalla de compatibilidad con Kuberentes](../../../../03-media/cloudability-premium/images/kubernetes.jpg)

Nota:

Nuestro agente de métricas no se ha probado con Azure Kubernetes Service ( AKS ) ni con Google Kubernetes Engine ( GKE ) para la versión 1.27. Una vez que Azure y GCP anuncien oficialmente la compatibilidad con la versión 1.27, validaremos nuestro agente de métricas y actualizaremos nuestras notas de la versión.

## Soporte para clusters Red Hat OpenShift en AWS ( ROSA ) - 7 de junio de 2023

Esta versión introduce soporte para clusters Red Hat OpenShift en AWS ( ROSA ).

Al integrar ROSA en el ecosistema de Cloudability, los usuarios ahora pueden realizar un seguimiento y asignar de forma eficaz los costes asociados a sus clústeres de OpenShift, lo que los equipara a las capacidades de las que ya disponen los usuarios de EKS, GKE y AKS.

Esto permitirá a los clientes de Cloudability que utilicen ROSA acceder a información detallada sobre la asignación de costes adaptada específicamente a sus recursos de contenedores OpenShift.

Nota:

En esta versión se incluye compatibilidad con las versiones de clúster OpenShift 4.10, 4.11 y 4.12.

![captura de pantalla de red hat openshift](../../../../03-media/cloudability-premium/images/rosa1.jpg)

Cómo puede ayudarle esta función

Con esta versión, los usuarios pueden identificar y seleccionar fácilmente su versión de clúster OpenShift preferida al aprovisionar recursos. Esta mejora proporciona a los usuarios una mayor flexibilidad y les permite aprovechar las funciones y mejoras específicas que ofrecen las distintas versiones de OpenShift.

Más información sobre esta versión

Siga estos pasos para ver y elegir versiones de clúster de OpenShift durante el proceso de aprovisionamiento:

1. Vaya a la plataforma Cloudability y navegue hasta la sección Insights.
2. Seleccione Contenedor y luego seleccione Aprovisionar Cluster. Observará que en lugar de la opción Kubernetes Version, ahora existe la opción Cluster Version.
3. Seleccione Versión de clúster para continuar.
4. En el menú desplegable que aparece, no sólo verá las versiones existentes de Kubernetes, sino también las versiones disponibles de OpenShift.
5. Elija la versión deseada de OpenShift en el menú desplegable.

## Azure Cartera del Plan de Ahorro y Recomendaciones apoyadas - 31 de mayo de 2023

Esta versión lanza Azure Savings Plan Recommendations & Portfolio for Compute en Cloudability. Esto ayuda a los clientes a conocer el inventario de su plan de ahorro y a recibir recomendaciones de compra para un ahorro óptimo.

Anteriormente, las recomendaciones sobre planes de ahorro sólo se facilitaban para AWS en Cloudability. Azure los planes de ahorro ofrecen una opción adicional para reducir los costes de los clientes con un gasto informático constante comprometiéndose a un gasto fijo por hora en servicios informáticos durante periodos de uno o tres años.

Cómo puede ayudarle esta función

Azure ahora los clientes pueden ver su inventario del Plan de Ahorro, así como recibir recomendaciones de compra dentro de la plataforma Cloudability. Los clientes pueden ver un inventario de sus Planes de Ahorro actuales en Azure junto con un resumen de los indicadores clave de rendimiento (KPI) de la cantidad total y la comisión horaria de sus Planes de Ahorro. Los clientes también pueden ver en Azure las recomendaciones de compra del Plan de Ahorro, así como los totales resumidos de los indicadores clave de rendimiento de todas las recomendaciones dadas, incluido el número total de compras recomendadas, las comisiones iniciales totales, el ahorro neto estimado y la tasa de ahorro estimada.

Más información sobre esta versión

En el menú de navegación principal Cloudability,

- En Insights, seleccione Planes de ahorro y, a continuación, seleccione la pestaña Azure para acceder a su cartera de planes de ahorro.
- En Optimizar, seleccione Planificador de instancias reservadas y, a continuación, seleccione la pestaña Azure SP para acceder a las recomendaciones de su plan de ahorro.

Nota:

- Para todos los vendedores, las carteras del Plan de Ahorro estarán ahora en el menú Insights y las recomendaciones del Plan de Ahorro en el menú Optimize.
- Si aún no lo han hecho, los clientes deben asegurarse de que se han habilitado las credenciales y permisos necesarios en Azure para que Cloudability tenga acceso a los datos de su Plan de Ahorro.
- Clientes de MCA: Configuren el lector de la cuenta de facturación por rol siguiendo las instrucciones que se indican [aquí](../admin/azure-cm-ea.html#azure-cm-ea__grant).
- Clientes de EA: regeneren y vuelvan a ejecutar el script a nivel de EA siguiendo las instrucciones que se indican [aquí](../admin/azure-cm-ea.html#azure-cm-ea__Configur).

## Reconocimiento de la finalización de recursos en Rightsizing ROI - 31 de mayo de 2023

En esta versión, la terminación de recursos se reconoce al calcular los ahorros realizados en Rightsizing ROI.

Se aplica cuando la acción apropiada de redimensionamiento es dar de baja un recurso individual. Anteriormente, Rightsizing ROI no tenía en cuenta las bajas de recursos a la hora de calcular o mostrar el ahorro obtenido con estas acciones.

Cómo puede ayudarle esta función

Esta funcionalidad permite a los usuarios de Cloudability utilizar la funcionalidad Rightsizing ROI para calcular el ahorro realizado de las recomendaciones accionadas cuando la acción es la terminación del recurso. Una vez que se ha añadido una recomendación de redimensionamiento a través del ROI de redimensionamiento y se ha dado de baja el recurso, el ahorro realizado por la baja se calculará y se mostrará tanto para el recurso individual como añadido al total acumulado de todos los ahorros realizados.

Esto se añade a la ayuda ya proporcionada para los cálculos de ahorro realizados cuando se redimensiona un recurso. Se proporcionará soporte para todos los servicios actualmente soportados por Rightsizing ROI.

Más información sobre esta versión

En el menú de navegación principal Cloudability,

- En el menú Optimizar, seleccione Redimensionar ROI.
- Siempre que se haya dado de baja el recurso, aparecerá una cantidad de Ahorro Realizado al final de la lista de recomendaciones de redimensionamiento rastreadas.
- Nota: El importe de ahorro realizado también se añadirá al total de ahorro realizado que aparece en la parte superior de la página.

## Distribución de costes de inactividad disponible para contenedores en Cloudability core analytics - 19 de mayo de 2023

Esta versión introduce seis nuevas métricas para que los usuarios de Cloudability puedan dividir las dimensiones de los contenedores según sus preferencias.

Es inevitable que la infraestructura en contenedores ejecute una cierta cantidad de capacidad de sobrecarga que no es utilizada por las cargas de trabajo subyacentes. Este uso "inactivo" tiene un coste asociado (para las máquinas virtuales y volúmenes de respaldo) que debe contabilizarse. Hemos introducido la posibilidad de distribuir estos costes de contenedores ociosos en Cloudability core analytics (informes y cuadros de mando). Aunque se trata de una función que ya existe en la función específica de imputación de costes de contenedores, añadirla a los análisis básicos puede ayudar a los usuarios a agilizar los procesos de devolución de cargos y permite elaborar informes de costes más flexibles. Esta distribución se realiza en el contexto de las construcciones Kubernetes namespace y label.

Este soporte se implementa mediante la introducción de una nueva categoría métrica "Contenedores", que pone a disposición seis nuevas métricas. Estas métricas permiten a los usuarios ver por separado los costes utilizados, ociosos y justos, ya sea con una base de efectivo o amortizada. Para los clientes con precios personalizados activados, todos estos se representarán como métricas "ajustadas".

![distribución de costes de inactividad cldy captura de pantalla](../../../../03-media/cloudability-premium/images/cldy-idle-cost.jpg)

Cómo puede ayudarle esta función

La función de asignación de costes de contenedores evalúa la utilización de los recursos en cada nodo y la une a los datos de facturación para calcular el coste de cada clúster y asociar un "coste utilizado" directo a los valores de espacio de nombres y etiquetas de K8s (esto ha estado disponible en los informes básicos utilizando el espacio de nombres o una dimensión de etiqueta). Con esta mejora también se puede informar sobre el coste de inactividad a través de la nueva métrica, que se asigna a los valores de espacio de nombres y etiqueta proporcionalmente en función de su contribución directa al coste de cada nodo. El Coste Justo es simplemente el Coste Utilizado y el Coste Ocioso combinados - se podría pensar que es el coste total.

Más información sobre esta versión

Algunas consideraciones e ideas de informes a tener en cuenta con estas nuevas métricas:

- En el caso de los costes no relacionados con los contenedores, todas estas nuevas métricas aparecerán como 0 $. Para filtrar sólo los datos del contenedor, pruebe con un filtro del tipo "Nombre del clúster no es igual a (no establecido)"
- Utilice estas métricas con diferentes dimensiones para visualizar fácilmente la utilización frente a la inactividad. Por ejemplo, lista por nombre de clúster o ID de recurso.
- Por primera vez, puede utilizar conjuntamente el criterio de caja y el de coste amortizado para elaborar informes detallados sobre el coste de los contenedores.

Con esta versión, las nuevas métricas introducidas reflejarán los datos de costes a partir del 1 de mayo de 2023. Para actualizar datos históricos adicionales, póngase en contacto con el equipo de su cuenta o con el servicio de asistencia para que se complete el reprocesamiento.

## Aviso al representar 500 o más puntos de datos en gráficos de Cloudability - 18 de mayo de 2023

Esta versión añade una función de aviso en Cloudability cuando los usuarios intentan representar 500 o más puntos de datos en los gráficos de Cloudability.

Anteriormente, los usuarios de Cloudability se encontraban con problemas de rendimiento de la página cuando intentaban representar 500 o más puntos de datos en sus visualizaciones de gráficos. Inarguably, 500 or more data points in a single chart do not serve its purpose due to poor readability, the rendering of the same often slowed the entire Dashboards page for our users.

Cómo puede ayudarle esta función

Cloudability mostrará ahora un aviso cuando los usuarios intenten representar 500 o más puntos de datos en sus gráficos, lo que evitará que se produzcan problemas de rendimiento de la página. En el momento de crear el gráfico, es posible que los usuarios no sean conscientes de que están intentando visualizar una medida de alta cardinalidad como el ID de recurso, pero una indicación como ésta les ayudaría a detectar los riesgos potenciales si deciden continuar con la acción. Este aviso se mostrará en todos los gráficos en los que se supere el límite y cada vez que se cargue la página de Cuadros de mando en Cloudability.

Más información sobre esta versión

El aviso tendrá dos CTA:

- Editar consulta - Permite volver a la ventana de edición y reducir los puntos de datos (por debajo de 500).
- Gráfico de todos modos - Los usuarios pueden proceder a renderizar con el número de puntos de datos elegido.

## Soporte de utilización de GPU para AWS ASG Rightsizing - 11 de mayo de 2023

Esta versión continúa la mejora correlacionada con la GPU de las recomendaciones de redimensionamiento de Cloudability mediante la ingesta y la utilización del procesamiento y la memoria de la GPU.

Antes de esta versión, los datos de la GPU no se tenían en cuenta a la hora de recomendar la redimensión del grupo de autoescalado AWS. Con esta versión, los clientes de « AWS » que utilicen grupos de autoescalado y cuyos datos sean importados por « Apptio » a través de CloudWatch o « Datadog » podrán ahora incluir sus datos de GPU para recibir recomendaciones mejoradas de ajuste de recursos que tengan en cuenta dichos datos.

Cómo puede ayudarle esta función

AWS los clientes que utilicen grupos de escalado automático con GPU recibirán ahora recomendaciones de ahorro basadas en las métricas de GPU ingestadas por Apptio. Además de suponer un ahorro adicional para nuestros clientes, estas métricas aportan una nueva dimensión a nuestro motor de recomendación.

Más información sobre esta versión

1. En el menú de navegación principal de Cloudability, seleccione Optimizar > Redimensionamiento
2. Seleccione la pestaña AWS y, a continuación, seleccione AWS ASG.   
    Las recomendaciones de dimensionamiento para los grupos de autoescalado con GPU se mostrarán automáticamente una vez que estén correctamente configurados y disponibles. La vista «Detalles» de la recomendación para los grupos de autoescalado que utilizan GPU incluirá ahora gráficos adicionales sobre la utilización de la GPU (%) y de la memoria de la GPU, al igual que en las recomendaciones de ajuste de tamaño de AWS EC2.

   No es necesaria ninguna configuración adicional para los clientes que ya dispongan de las recomendaciones de optimización de recursos de « AWS Auto Scaling » y de la integración de datos de utilización de GPU configuradas con Cloudability.

## Se han añadido valores «máximos» a la API de Rightsizing y a la exportación de « CSV » - 18 de abril de 2023

En esta versión se anuncia la incorporación de los valores «Throughput Max» e «IOPS Max» tanto a los puntos finales de la API de Rightsizing como a las exportaciones de Rightsizing CSV para cada servicio de disco de los proveedores correspondientes que sean compatibles con Rightsizing.

Más información sobre esta versión

Los valores del punto final de la API se designan como “iopsMax” y “throughputMax”. Los valores del archivo « CSV » exportado incluirán los nombres de columna «IOPS Max» y «Throughput Max».

## Lanzamiento de Cloudability GCP : Recomendaciones sobre descuentos por uso comprometido - 6 de abril de 2023

En este comunicado se anuncia la puesta en marcha de las recomendaciones sobre el descuento por compromiso de uso (CUD) de GCP para los clientes.

Cloudability Ahora ofrece recomendaciones para las unidades de almacenamiento en disco (CUD) de GCP utilizando su propio motor personalizado y una nueva interfaz de análisis. Con esta nueva interfaz, los clientes pueden realizar análisis hipotéticos y tener un mayor control sobre la recomendación generada, lo que les permite ajustar las recomendaciones en función de su uso futuro, su estrategia empresarial y su factor de riesgo.

Cómo puede ayudarle esta función

En primer lugar, los clientes pueden filtrar su consumo para el análisis, lo que les permite incluir o excluir consumos para obtener un análisis más preciso que represente su consumo futuro. Si una carga de trabajo se ha ejecutado durante el periodo de análisis pero no debe incluirse, como una carga de trabajo de pruebas o desarrollo, puede eliminarse del análisis. Además, si una carga de trabajo se va a retirar del servicio o va a sustituir un tipo concreto de uso, como un sistema operativo o un software de base de datos, puede excluir ese uso del análisis. De este modo, su estrategia empresarial se alineará con recomendaciones más precisas para su uso futuro.

Los clientes pueden añadir hasta 10 dimensiones Cloudability a su análisis para filtrar. Estas dimensiones pueden ser cualquiera de los Tags & Labels, Account Groups, o Business Mappings configurados.

En segundo lugar, los clientes pueden ver su uso seleccionado para analizarlo y ajustar las recomendaciones en tiempo real. Esto les permitirá ver los posibles resultados en función de los distintos importes de compromiso. Esto ayuda a los clientes a ver el impacto de unos niveles de compromiso más bajos en caso de una tendencia de uso decreciente o de periodos sostenidos de menor uso.

## Compatibilidad con las API de gestión de costes de Azure - 30 de marzo de 2023

Esta versión incorpora la compatibilidad con las API de gestión de costes de Azure en Cloudability Credentials. Azure Los clientes de EA ya pueden utilizar estas API para obtener tanto el coste real como el coste amortizado mediante las API de gestión de costes.

Microsoft ha dejado de dar soporte a las actuales API de informes Azure, que quedarán obsoletas en octubre de 2023. La API de gestión de costes es una alternativa para recuperar los datos de facturación frente a las exportaciones de cuentas de almacenamiento.

Pasos para obtener credenciales Azure utilizando las nuevas API de gestión de costes:

Pasos para un nuevo cliente:

1. Vaya a la página de credenciales Cloudability y seleccione Azure.
2. Seleccione EA como tipo de cuenta Azure.
3. Ingrese el identificador de inscripción Azure y el identificador de suscripción.
4. Introduzca NA en todos los demás campos.
5. Seleccione Generate Setup Script e instale el script PowerShell. Este script power shell tendrá un nuevo rol llamado Enrollment reader que se utiliza para acceder a la API de Gestión de Costes.
6. Una vez hecho esto, comprueba las credenciales en la interfaz de usuario de Cloudability. ![Azure captura de pantalla de la API de gestión de costes](../../../../03-media/cloudability-premium/images/cost-management.jpg)

Pasos para los clientes existentes de EA con API de informes:

1. Si ya dispone de acceso a la función de lector de inscripciones, introduzca NA en Clave de acceso API y verifique las credenciales.
2. Si el acceso a la función de lector de inscripciones no está disponible, siga los mismos pasos que para un cliente nuevo.

Pasos para clientes EA existentes con almacenamiento Blob:

No hay que hacer nada. En el caso de exportaciones de facturación vía blob, Cloudability continuará obteniendo los archivos de facturación desde allí.

## Permitir recomendaciones de reducción de memoria/GPU sin métricas - 29 de marzo de 2023

Esta versión añade dos nuevos ajustes globales en las Preferencias de Redimensionamiento. Los clientes pueden activar recomendaciones de reducción de memoria sin métricas de utilización de memoria y recomendaciones de reducción de GPU sin métricas de utilización de GPU.

Ajustes de recomendación de memoria/GPU en Preferencias de Redimensionamiento

Cloudability los usuarios con ajustes globales pueden activar/desactivar recomendaciones que supondrían una reducción de la capacidad de componentes específicos (memoria y GPU) aunque las métricas de estos componentes no estén disponibles en Cloudability.

Para cada uno de estos ajustes, si el ajuste está activado, el cliente recibe recomendaciones que podrían suponer un ahorro adicional reduciendo la capacidad del componente, pero sin tener en cuenta las métricas actuales del componente si éstas no están disponibles en Cloudability.

Para cada uno de estos ajustes, si el ajuste está desactivado y las métricas del componente no están disponibles en Cloudability, las recomendaciones se limitarán a una capacidad equivalente o superior (el ajuste GPU sólo se aplica a las instancias basadas en GPU y que utilicen la familia de instancias).

Ambas opciones están desactivadas por defecto.

Cómo puede ayudarle esta función

Estas recomendaciones ayudan a los clientes a ahorrar dinero reduciendo la capacidad de determinados componentes, aunque esas recomendaciones no tengan en cuenta las métricas actuales de esos componentes. Por ejemplo, la familiaridad de un cliente con el recurso le permitiría saber que reducir la capacidad del componente no afectaría a la carga de trabajo.

Más información sobre esta versión

1. En el menú de navegación principal de Cloudability, seleccione Configuración > Preferencias de cambio de tamaño.
2. En Preferencias de computación ( VM ), seleccione la sección Reducción de capacidad.
3. En la sección Reducción de capacidad, consulte Permitir recomendaciones de reducción de memoria sin métricas de utilización de memoria y Permitir recomendaciones de reducción de GPU sin métricas de utilización de GPU. Estas opciones no están marcadas por defecto.

## Azure Actualización de la interfaz de usuario de credenciales de funciones personalizadas - 15 de marzo de 2023

Esta versión muestra los permisos de función personalizados de Azure en la interfaz de usuario de credenciales de Cloudability de forma fácil de usar. Los clientes podrán ver si tienen activada o no la función personalizada Azure en los detalles de las credenciales. Puede haber un par de escenarios en las funciones que se describen a continuación.

1. Cloudability Los clientes con el rol de lector « Azure » y sin ningún rol personalizado seguirán viendo el rol de lector « Azure » representado por una marca verde ( ![Icono de garrapata verde](../../../../03-media/cloudability-premium/images/greentick.jpg) ), y los permisos personalizados no se mostrarán.

   1. Gestión: Reader ![icono de marca verde](../../../../03-media/cloudability-premium/images/greentick.jpg)
   2. Suscripción: ReadSubscription ![icono de marca verde](../../../../03-media/cloudability-premium/images/greentick.jpg)

   ![Azure captura de pantalla del rol personalizado](../../../../03-media/cloudability-premium/images/azure-enabled.jpg)
2. Cloudability Los clientes con el rol Personalizado activado sólo verán los permisos personalizados y no verán el rol de lector de Azure.

   ![utlización Azure captura de pantalla](../../../../03-media/cloudability-premium/images/azure-not-enabked.jpg)

Nota:

- Para tener sólo el rol personalizado Azure, los clientes deben eliminar el rol de lector Azure y luego habilitar el rol personalizado.
- Esto es aplicable a las cuentas de suscripción y no a la cuenta de facturación.

## Separación de etiquetas de grupos de recursos Azure - 2 de marzo de 2023

Esta versión añade a Cloudability la capacidad de diferenciar entre las etiquetas de grupos de recursos Azure y las etiquetas de recursos Azure, de modo que los clientes puedan identificarlas y gestionarlas con claridad.

Separación de etiquetas de nivel de recurso y etiquetas de grupo de recursos

Anteriormente, Cloudability no distinguía entre una etiqueta de Grupo de Recursos y una etiqueta de Recurso, ambas se fusionaban y se trataban como etiquetas de Recurso. Ahora los clientes pueden realizar un mejor seguimiento y gestión de sus Grupos de Recursos creando una nueva dimensión empresarial para ellos, aplicándoles reglas específicas/mapeos empresariales, etc.

Cloudability ahora cambiará el formato de las etiquetas de la siguiente manera:

"cldy:Azure:ResourceGroupTag:<TagKey>" para etiquetas generadas desde el nivel de Grupo de Recursos

"cldy:Azure:ResourceTag:<TagKey>" para las etiquetas generadas a partir del nivel de Recursos

Esta función no es compatible con versiones anteriores. Las etiquetas de grupos de recursos descubiertas y tratadas como etiquetas de recursos en Cloudability antes de esta versión se mantendrán tal cual.

## Asignación de costes de contenedores - Mejora de la ponderación CPU/Memoria para la asignación de espacios de nombres y etiquetas - 1 de marzo de 2023

Esta versión mejora el modo en que los costes se asignan a los espacios de nombres y etiquetas individuales, ajustándose mejor al modo en que los proveedores de la nube cobran las máquinas virtuales subyacentes.

Mejoras en la imputación de costes de los contenedores

Con esta versión, Cloudability ha mejorado el modo en que se asignan los costes a los valores individuales de Namespace y Label para que coincidan mejor con el modo en que los proveedores de la nube cobran las máquinas virtuales subyacentes. El proceso de desglose y asignación del coste de cada VM consiste en repartir el coste total entre los recursos que lo componen (CPU, memoria, red, etc.) y, a continuación, asignar el coste a cada Namespace y Label en función de la cantidad de estos recursos que hayan consumido. La memoria y la CPU, en conjunto, constituyen el componente más importante (85 %) de los costes de VM.

Hasta ahora, Cloudability utilizaba una proporción estándar para dividir este componente, independientemente del tipo de « VM » (lo que hacía que los costes se inclinaran hacia la memoria). Con esta versión, Cloudability ha hecho que la proporción dependa del tipo de máquina: en las máquinas optimizadas para cálculo, la proporción se inclinará más hacia la CPU en comparación con las máquinas optimizadas para memoria. Esto se ha conseguido fijando los precios de la CPU (horas-núcleo) y la memoria (GB-hora) basándose en un análisis de las diferentes categorías de VM y en cómo estos dos tipos de recursos influyen en los precios de VM. El resultado neto es una representación más precisa de la contribución de cada espacio de nombres y etiqueta a los costes.

Más información sobre esta versión

Esta versión no afecta a la asignación de costes a nivel de clúster. Para obtener más información, únete a la conversación en la [comunidad « Apptio](https://community.apptio.com/home "(se abre en una pestaña o una ventana nueva)") ».

## Imputación de los costes de los contenedores - Visualización únicamente de las etiquetas Kubernetes - 26 de enero de 2023

Esta versión incluye mejoras para mostrar sólo las etiquetas Kubernetes asignadas en la página Asignación de costes de contenedores.

Mejoras para mostrar sólo las etiquetas mapeadas Kubernetes

Para mejorar la facilidad de uso y el rendimiento, la página Asignación de costes de contenedores mostrará ahora sólo las claves de etiqueta que se hayan asignado explícitamente en la página Asignación de etiquetas. La página Asignación de costes de contenedores ya no mostrará todas las etiquetas históricas.

Si las teclas de la etiqueta Kubernetes ya están asignadas en su entorno Cloudability, no es necesario realizar ningún cambio. Para añadir más etiquetas Kubernetes, puede solicitar al administrador de Cloudability que asigne las teclas de etiquetas específicas en la página Etiquetas y asignación. Tenga en cuenta que si las teclas de etiqueta de Kubernetes no están asignadas en su entorno, el desplegable Tecla de etiqueta no mostrará ninguna tecla.

![captura de pantalla de los clusters de aprovisionamiento](../../../../03-media/cloudability-premium/images/kubernetes-label.jpg)

Aunque las claves de etiqueta aparecerán en la página Asignación de costes de contenedor inmediatamente después de la asignación, los valores tardarán entre 24 y 48 horas en rellenarse. Esta versión no afecta a los espacios de nombres, los servicios ni la visibilidad de las construcciones de Kubernetes en los cuadros de mando e informes de Cloudability.

## Mejoras de la unidad de medida en las métricas de transferencia de datos, horas GB y meses GB - 18 de enero de 2023

Esta versión incluye cambios para normalizar la unidad de medida de las métricas de uso en Cloudability.

Unidad de medida normalizada para las métricas de uso

Las métricas de uso se mostrarán ahora en gibibytes ( GiB ) en lugar de gigabytes (GB) en Cloudability, lo que eliminará confusiones y facilitará la comprensión de los datos sin necesidad de lidiar con múltiples unidades.

La normalización de la unidad de medida afecta a las siguientes métricas.

| Valor actual | Nuevo valor |
| --- | --- |
| Transferencia de datos (gb) | Transferencia de datos ( GiB ) |
| GB Horas | GiB/horas |
| GB Meses | GiB/meses |

Efectos sobre el redimensionamiento

En la página Redimensionar, todas las medidas se mostrarán en GiB y las etiquetas mostrarán GiB. Tenga en cuenta que las siguientes métricas ya están representadas en GiB:

RDS tamaño de la memoria

GCP calcular el tamaño de la memoria

Azure Tamaño de la memoria SQL

S3 tamaño del cubo

## Apoyo a Kubernetes 1.25 - Asignación de costes de contenedores - 17 de enero de 2023

Esta versión permite que el agente de Container Metrics se ejecute y recopile información de uso de los clústeres que se ejecutan en Kubernetes 1.25 en el entorno de Azure Kubernetes Service ( AKS ).

Compatibilidad con la asignación de costes de contenedores en Kubernetes 1.25 en AKS

Cloudability Ahora es compatible con la asignación de costes de contenedores en Kubernetes 1.25 en entornos AKS. Esta función te permitirá conocer el uso de los recursos de los contenedores y el coste de los clústeres que se ejecutan en Kubernetes 1.25.

Puede descargar y desplegar el agente de Métricas de Contenedores utilizando el flujo de trabajo de aprovisionamiento habitual. Puede seleccionar Kubernetes 1.25 en el selector Kubernetes Version de la página Add Cluster Data.

El agente de Container Metrics no se ha probado con clústeres que ejecuten Kubernetes 1.25 en los entornos de Amazon Elastic Kubernetes Service (EKS) y Google Kubernetes Engine ( GKE ). Esto se llevará a cabo una vez que AWS y GCP anuncien oficialmente que admiten Kubernetes y 1.25.

## Uso Mejoras familiares - 17 de enero de 2023

Esta versión incluye mejoras en la dimensión Familia de usos en Cloudability para ofrecer una mejor calidad de asignación y una mayor cobertura de las partidas de gastos.

Mejoras en la dimensión Familia de uso

Hemos realizado mejoras en la dimensión Familia de uso. Estos cambios se reflejarán en sus partidas de gastos a partir del 1 de enero de 2023. Si necesita reflejar estos cambios más allá de la fecha predeterminada, póngase en contacto con el equipo de su cuenta o con el servicio de asistencia para volver a procesar los datos.

Las mejoras ofrecen las siguientes ventajas.

Mayor cobertura de las partidas de gastos

La cobertura se define como el porcentaje de coste clasificado sobre el total. Casi el 99% de los costes se clasificarán ahora en los valores de familia de uso adecuados, reduciendo así los costes no asignados (es decir, Otros ).

Mejor calidad cartográfica

Para ofrecer una asignación mejorada de las partidas de costes, se han reasignado algunos valores de Familia de Utilización existentes.

El siguiente ejemplo ofrece una visión general de los valores reasignados.

![captura de pantalla mejorada del mapa de costes](../../../../03-media/cloudability-premium/images/usagefamilyremapping.jpg)

Nuevo uso Valores familiares

Esta versión introduce dos valores de la Familia de Uso:.

Seguridad: A continuación se ofrecen algunos ejemplos:

AWS : Amazon GuardDuty, EUW2-PaidKubernetesAuditLogsAnalyzed, $ por mes para Policy-WAF, Amazon Inspector UGE1-agent-assessments, Comprobaciones de seguridad para PaidComplianceCheck, $ por hora de endpoint para AWS Network Firewall

Azure protección avanzada frente a amenazas: Azure Database for PostgreSQL/SQL, Azure Defender::Microsoft Defender for Containers, Microsoft Defender for IoT - Managed Devices - Standard

GCP : Clústeres con autorización binaria activada, Cloud IDS

Balanceador de carga: el uso anterior del balanceador de carga era muy granular. Este valor incluye ahora algunos cambios.
