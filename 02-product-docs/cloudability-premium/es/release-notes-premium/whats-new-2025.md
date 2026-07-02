---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "release-notes-premium"
title: "Cloudability Premium o: Novedades para 2025"
breadcrumb:
  - "Cloudability Premium"
  - "Novedades en Cloudability"
source_path: "release-notes-premium/whats-new-2025.html"
images:
  - "images/oci-credentialing-namespace.jpg"
  - "images/threshold-based_alerting4.jpg"
  - "images/wp_json1.jpg"
  - "images/wp_json2.jpg"
  - "images/wp_json3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability Premium o: Novedades para 2025

## Mejoras en la interfaz de usuario de gestión de usuarios y en la vista predeterminada - 19 de diciembre de 2025

Esta versión introduce mejoras en la usabilidad **de la gestión de usuarios** y **la configuración de la vista predeterminada**, lo que mejora la visibilidad y la coherencia tanto para los administradores como para los usuarios.

- **Interfaz de usuario actualizada para la gestión de usuarios** : la experiencia de edición de usuarios se ha trasladado del panel izquierdo a un nuevo panel derecho en **Usuarios y grupos → Usuarios**. El nuevo panel ahora:

  - Muestra todos los tipos de vistas, incluidas **las vistas jerárquicas (HV)** y las vistas compartidas a través de grupos de usuarios
  - Admite la búsqueda y el filtrado por vistas **seleccionadas**, **no seleccionadas** o **todas**
- **Vistas jerárquicas como vistas predeterminadas** : Ahora se pueden seleccionar las HV como vistas predeterminadas:

  - Los administradores pueden asignar un HV como predeterminado para un usuario desde **la gestión de usuarios.**
  - Los usuarios pueden establecer un HV como su vista predeterminada desde **Administrar perfil → Preferencias.**

    Solo los HV a los que el usuario tiene acceso aparecen en la lista; y solo el nodo de nivel más alto al que el usuario tiene acceso puede establecerse como predeterminado.
- **Mejora del comportamiento cuando se eliminan vistas o cambian los permisos**

  - Si se elimina una vista predeterminada (incluida una HV), la vista predeterminada del usuario volverá automáticamente a la vista predeterminada a nivel de la organización.

    Si no existe un valor predeterminado a nivel de organización, la vista predeterminada se establecerá en blanco.
  - Los administradores ahora verán un mensaje de advertencia al eliminar vistas o cambiar permisos que puedan afectar a los valores predeterminados de los usuarios.

## Alertas de anomalías para múltiples usuarios - 19 de diciembre de 2025

Esta versión añade compatibilidad con el intercambio de alertas de anomalías. Ahora los usuarios pueden incluir destinatarios directamente en una alerta, lo que facilita notificar a otras personas sin necesidad de configurar alertas individuales.

Además, ahora hay una nueva pestaña para compartir alertas en la página de configuración de alertas, que ofrece una vista centralizada de todas las suscripciones a alertas.

.

## Credenciales de proveedores: verificación masiva para Azure, OCI y IBM - 19 de diciembre de 2025

Esta versión añade compatibilidad con la acción de verificación masiva en las credenciales de proveedor para Azure, OCI y IBM, lo que facilita la incorporación de cuentas CSP. Con esta versión, la funcionalidad de acciones masivas estará disponible para todos los clientes que dispongan de las siguientes opciones.

- AWS - Guardar en bloque, Actualizar en bloque, Verificar en bloque
- Azure - Verificación masiva
- GCP - Guardar en bloque, verificar en bloque
- OCI - Verificación masiva
- IBM - Verificación masiva

## Mejoras en las alertas por correo electrónico para las credenciales de proveedores – 11 de diciembre de 2025

Cloudability Anuncia mejoras en las alertas por correo electrónico sobre el estado de las credenciales de los proveedores. Las alertas por correo electrónico ahora se mostrarán

- Cloudability estado de la cuenta
- Turbonomic estado del objetivo

Los correos electrónicos resumirán los distintos estados y acciones necesarias en varias cuentas dentro de Cloudability.

## Mejoras en el banner de credenciales de proveedores – 10 de diciembre de 2025

Cloudability Anuncia mejoras en los banners que aparecen en la página de credenciales de proveedores para mostrar lo siguiente:

- Cloudability estado de la cuenta
- Turbonomic estado del objetivo

Los banners resumirán las acciones necesarias en varias cuentas dentro de Cloudability. El banner también actuaría como filtro rápido para diversos estados de cuentas/objetivos al hacer clic sobre los números mostrados.

## Turbonomic Estado objetivo en las credenciales del proveedor: 10 de diciembre de 2025

Cloudability Anuncia el lanzamiento de la visualización del estado de objetivo « Turbonomic » en la pantalla de credenciales de proveedor de Cloudability.

Podrá ver el estado general en una nueva columna denominada «Estado objetivo» y también podrá ver los detalles en la sección de detalles de la cuenta haciendo clic en … y, a continuación, en «Detalles».

Esto permite a los clientes Premium ver en una sola pantalla el estado de sus cuentas Cloudability y Turbonomic.

Esto es aplicable a todas las integraciones de proveedores disponibles con Cloudability Premium

- AWS
- Azure
- GCP
- New Relic
- DataDog

  Nota: Es posible que, en algunos casos excepcionales, los estados entre Cloudability y Turbonomic no coincidan. Si observa esto, envíe un ticket de soporte al equipo de soporte de IBM.

## Panel de control de servicios de IA multicloud – 8 de diciembre de 2025

Cloudability Anuncia el lanzamiento del Panel de servicios de IA multicloud, una solución integral para supervisar los costes de la IA y el aprendizaje automático en AWS, Azure y Google Cloud Platform. Este nuevo panel de control proporciona a los equipos de FinOps información sobre el gasto en IA generativa, lo que permite tomar decisiones basadas en datos para controlar los costes y ampliar al mismo tiempo las iniciativas de IA.

**Cómo empezar**

El panel de servicios de IA multicloud está disponible para todos los clientes de IBM Cloudability que tengan cuentas conectadas en AWS, Azure o GCP. Para acceder al panel de control:

1. Vaya a Inicio > Mi panel de control en la consola de Cloudability
2. Seleccione Multi Cloud | Panel de servicios de IA en la lista de paneles
3. Utilice el selector de rango de fechas para personalizar su período de análisis
4. Desplácese por las secciones del panel de control para explorar los detalles de los costes por servicio y proveedor

Para obtener más información, póngase en contacto con su equipo de cuentas de IBM Cloudability o con su gestor técnico de cuentas.

## Credenciales del proveedor: prevención de la pérdida de datos si el usuario hace clic fuera del panel lateral – 25 de noviembre de 2025

Esta versión añade un modal a la página de credenciales del proveedor si el usuario hace clic fuera del panel lateral mientras rellena la información de las credenciales.

Antes de esta versión, si el usuario hacía clic fuera del panel lateral de la pantalla de credenciales del proveedor, la pantalla desaparecía y los datos introducidos en el formulario se perdían, lo que obligaba al usuario a volver a introducir la información.

## Funcionalidad de gestión automatizada de compromisos - 18 de noviembre de 2025

La funcionalidad de gestión automatizada de compromisos que respalda el Acuerdo de Nivel de Servicio ( Cloudability Savings Automation, CSA) ya está disponible para todos los clientes nuevos y existentes de Cloudability Premium. Los usuarios pueden aprovechar esta funcionalidad para gestionar automáticamente sus compromisos de Compute de AWS con el fin de maximizar sus ahorros y flexibilidad.

Esta funcionalidad se encuentra en el mosaico « Cloudability Savings Automation » (Gestión de eventos) de Frontdoor, que se proporcionará automáticamente a todos los clientes nuevos y existentes de Cloudability Premium.

Para obtener más información sobre CSA, consulte la [documentación para usuarios de CSA](https://www.ibm.com/docs/en/cloudability-commercial/savings-automation/saas "(se abre en una pestaña o una ventana nueva)").

## Sostenibilidad en la nube: emisiones incorporadas – 14 de noviembre de 2025

Hoy hemos lanzado la inclusión de las emisiones incorporadas como parte de los informes sobre emisiones de carbono. Esta mejora proporciona una representación más completa del impacto total del carbono en el uso de la nube pública.

Los usuarios ahora pueden ver las emisiones de carbono, incluidas tanto las emisiones operativas como las emisiones incorporadas.

Antes de esta versión, los usuarios que querían medir sus emisiones de carbono solo podían acceder a las emisiones operativas.

Con la inclusión de las emisiones incorporadas, la métrica «Emisiones de carbono estimadas» refleja ahora las emisiones de carbono totales, que son la suma de las emisiones operativas y las emisiones incorporadas.

Nota: Es posible que observe un aumento en los valores estimados de emisiones de carbono a partir de la ejecución de los datos de sostenibilidad de noviembre de 2025 (métricas de sostenibilidad para octubre de 2025), lo cual es previsible y se ajusta a la metodología de cálculo más inclusiva.

## Distribución de costes para informes y paneles de control – 7 de noviembre de 2025

Con esta versión, la función de reparto de costes ya está disponible en los informes de « Cloudability » (Reparto de costes) y en los widgets del panel de control. Ahora puede visualizar sus datos de costes con los costes asignados aplicados, con una visión completa tanto de los costes directos como de los compartidos en sus informes y paneles de control.

- **Activar** o desactivar el reparto de costes por informe o widget: active o desactive el reparto de costes en los informes y widgets nativos de Cloudability para ver cómo los costes asignados afectan a sus datos.
- **Indicadores visuales en toda la interfaz** : las dimensiones empresariales con reglas de asignación ahora muestran iconos de asignación en los selectores de dimensiones, lo que facilita identificar de un vistazo qué dimensiones se ven afectadas por sus reglas de reparto de costes.
- **Validación inteligente y gestión de errores** : el editor gestiona automáticamente la compatibilidad entre dimensiones y métricas.
- **Integración perfecta entre funciones** : el reparto de costes funciona de forma coherente en los informes y paneles de control.

- **Visibilidad completa de los costes** : obtenga una visión global de sus costes, incluidos tanto los gastos directos como los costes asignados a partir de recursos compartidos.

  **Análisis flexible** : alterne entre vistas asignadas y no asignadas para comprender el impacto de sus reglas de distribución de costes.

  **Errores evitados** : la validación automática garantiza que tus informes y widgets siempre utilicen combinaciones compatibles de dimensiones, métricas y filtros.

  **Experiencia coherente** : el reparto de costes funciona de la misma manera en los informes y los paneles de control, lo que facilita la creación y el intercambio de información.

Para obtener más información, visite [Cost Sharing for Reports and Dashboards](../product/cost-sharing-for-reports-and-dashboards.html) (Distribución de costes para informes y paneles de control).

## Centro de optimización en Cloudability : información centralizada para la optimización de compromisos y recursos - 7 de noviembre de 2025

Cloudability Ha añadido nuevas funciones en la sección Optimización para ayudar a los usuarios a obtener una visión centralizada de sus compromisos e iniciativas de optimización de recursos. Estos paneles muestran tanto las oportunidades de optimización prospectivas como los ahorros realizados retrospectivamente y el impacto de estas iniciativas.

Para obtener una visibilidad completa, los usuarios necesitan acceso a los datos de costes, así como permisos para ver los datos de compromiso, redimensionamiento y retorno de la inversión del redimensionamiento.

## Guardar y compartir informes en el inventario de recursos de Cloudability – 31 de octubre de 2025

Anteriormente, los datos del inventario de recursos solo se podían ver en la interfaz de usuario y, en el mejor de los casos, exportarse en formato CSV. Una vez que el usuario salía del módulo Inventario de recursos, los datos consultados y los filtros se restablecían. Con esta versión, ofrecemos la posibilidad de guardar un informe específico con su fecha, servicio y selecciones de filtro, y compartirlo con otros usuarios de la organización concediéndoles permisos de «solo lectura» o «edición». También admitimos la función de fecha «variable» para los informes guardados. La capacidad de guardar y compartir informes de inventario de recursos permitiría la creación de informes de retroalimentación sólidos para que los equipos comprendieran su consumo y modelos de reembolso informados para la facturación interna.

## Opción para excluir recursos de las recomendaciones y mostrar los nombres completos de las regiones en la planificación de cargas de trabajo de Cloudability - 30 de octubre de 2025

Con esta versión, hemos realizado dos mejoras:

1. Opción para que los usuarios administradores especifiquen los tipos de recursos que no deben aparecer en las recomendaciones de WLP para su organización. Esto se puede hacer utilizando cualquiera de estas dos opciones:
   - añadiendo la palabra clave para que las recomendaciones omitan aquellos tipos de recursos que contengan la palabra clave. Por ejemplo: si se asigna el valor «xlarge», se excluirán todos los recursos que tengan «xlarge» en su nombre.
   - añadiendo un asterisco (\*) junto con la palabra clave para que las recomendaciones omitan los tipos de recursos que comienzan con esa palabra clave. Por ejemplo: al introducir el valor « t4\* », se excluirían todos los recursos que comienzan por « t4 ».
2. Anteriormente, WLP solo mostraba los códigos de región (por ejemplo: us-east-1 ). Ahora mostramos el nombre completo de la región junto con sus respectivos códigos de región (entre paréntesis). Por ejemplo: us-east-1 ahora se mostrará como US East N. Virginia ( us-east-1 ). Las regiones también se ordenan alfabéticamente al seleccionarlas en la sección «Información común»

## Optimización del retorno de la inversión: eliminación de tickets y filtros – 24 de octubre de 2025

**Optimización del ROI** : Permitir la eliminación de tickets y el filtrado por fecha

La función de ROI de Cloudability se ha mejorado con nuevas prestaciones para aumentar su facilidad de uso:

**Visualización de ahorros** : Se ha añadido un nuevo gráfico a la página «Rentabilidad de la optimización», que muestra el importe ahorrado en los 30 días del mes en que se implementó o cerró. Esto ayuda a los usuarios a comprender el impacto de las acciones realizadas a lo largo de distintos periodos de tiempo.

**Eliminación de tickets** : ahora los usuarios de Rightsizing ROI pueden eliminar los tickets existentes que ya no son relevantes. Los usuarios pueden eliminar el ruido de los tickets de recomendaciones que ya no son válidos o que desean eliminar, y crear nuevos tickets basados en recomendaciones actualizadas.

**Filtrado por fecha** : ahora los usuarios pueden filtrar por rangos de fechas (fecha de creación o cierre) en el panel de informes de ahorro ( uI ) para centrar su análisis o sus informes de ahorro en periodos de tiempo específicos

La funcionalidad de filtrado y eliminación de tickets es compatible con la interfaz de usuario de Cloudability, así como con la API Rightsizing ROI.

## Selección jerárquica de cuentas para recomendaciones de compromiso de GCP : 16 de octubre de 2025

Hoy hemos lanzado una función adicional para ayudar a nuestros clientes con varias cuentas de facturación de GCP. El selector de cuentas de la página de recomendaciones de GCP ahora permite la selección múltiple y es jerárquico. Como resultado, las recomendaciones para diferentes cuentas de facturación se pueden mostrar en una sola página. Ahora todas las cuentas son la selección predeterminada y se ha añadido la cuenta de facturación a la tabla.

Ahora, explícitamente, la selección de cuentas en Recs es un selector de uso. La recomendación se basa en cualquier gasto que se encuentre en las cuentas seleccionadas.

Para obtener más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Exportar informes en formato regional definido por el usuario – 16 de octubre de 2025

Hoy, **los informes** de Cloudability han introducido una mejora que permite a los usuarios exportar los datos del informe en un formato CSV que es coherente con el formato regional seleccionado en su entorno, utilizando un punto «.» o una coma «,» como separador decimal. La configuración de separator.Locale se puede modificar en la pestaña «Moneda» de la configuración «Administrar perfil» por parte del administrador de la cuenta.

## Mayor transparencia de precios y configuración simplificada de Object Storage en la planificación de cargas de trabajo de Cloudability : 14 de octubre de 2025

1. Estamos introduciendo un nuevo icono de calculadora junto a cada recomendación de precios en Planificación de la carga de trabajo. Al hacer clic en el icono, ahora se muestra la fórmula exacta utilizada para calcular el precio, lo que le ayuda a comprender claramente el desglose de los costes. Esta mejora responde a los comentarios previos de los clientes sobre la conciliación de las diferencias de precio entre Workload Planning y las calculadoras de precios nativas de la nube.
2. Además, hemos eliminado la selección del tipo de recurso para el servicio « Object Storage ». Esta selección era redundante, ya que todas las opciones de configuración de Object Storage ya se muestran en la pantalla Recomendaciones. Esta actualización simplifica la experiencia al tiempo que mantiene una visibilidad completa de las oportunidades de optimización de costes.

## ENFOQUE 1.1 Apoyo en Cloudability – 13 de octubre de 2025

A partir de hoy, los clientes pueden incorporar fácilmente cualquier conjunto de datos en Cloudability que cumpla con la especificación [FOCUS v1.1](https://focus.finops.org/focus-specification/v1-1/ "(se abre en una pestaña o una ventana nueva)"), además de [FOCUS v1.0](https://focus.finops.org/focus-specification/v1-0/ "(se abre en una pestaña o una ventana nueva)"), y obtener visibilidad de los costes del gasto incorporado.

No hay cambios en el proceso de acreditación para el formato FOCUS 1.1, que sigue el mismo proceso que FOCUS 1.0.

## Compromiso de soporte para AWS OpenSearch Instancias reservadas – 10 de octubre de 2025

Hoy hemos lanzado la compatibilidad con las instancias reservadas de AWS OpenSearch. Los compromisos OpenSearch, el octavo tipo de compromiso AWS admitido, brindan un descuento a pedido a cambio de un compromiso de uso por hora de uno o tres años. Este tipo de compromiso se clasifica como un compromiso basado en recursos y, como tal, requiere la selección de parámetros de uso específicos: tipo de instancia, opción de pago y región. Este compromiso se comporta de manera similar a los demás tipos de compromisos no informáticos AWS. Con esta versión, admitimos este tipo de compromiso tanto en la cartera de compromisos como en las recomendaciones.

Para obtener más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Azure Gestión de costes Exportaciones: Compatibilidad con compresión Gzip – 9 de octubre de 2025

Esta versión introduce la compatibilidad con la compresión Gzip para las exportaciones de gestión de costes de Azure. Cloudability Los clientes ahora podrán utilizar:

- Formato de exportación: CSV
- Compresión: Ninguna o Gzip

Esto ayudaría a reducir el tamaño de los archivos exportados des Azure.

## Nuevos permisos de Turbonomic para AWS y Azure – 6 de octubre de 2025

Esta versión introduce nuevos permisos Turbonomic en Cloudability Premium.

**AWS**

- ec2:DescribeInstanceAttribute - Necesario para comprobar los atributos de una instanc EC2, incluido el atributo «stop protection»

**Azure**

- Microsoft.ContainerService/managedClusters/start/action - Requerido por Turbonomic para Azure AKS cluster parking
- Microsoft.ContainerService/managedClusters/stop/action - Requerido por Turbonomic para Azure AKS cluster parking
- Microsoft.Compute/disks/beginGetAccess/action - Necesario para ejecutar acciones de cambio de tamaño de disco/volumen cuando se crean a partir de instantáneas

Visite [la referencia de permisos de visita](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=azure-permissions-reference-microsoft "(se abre en una pestaña o una ventana nueva)") para obtener más información.

Nota: Estos permisos son de naturaleza acumulativa y no afectan al funcionamiento de las cuentas y permisos acreditados existentes. Sin embargo, será necesario volver a acreditarse para añadir estos nuevos permisos.

## Mejora en la configuración del reparto de costes: asignación automática a nuevos valores de dimensión empresarial – 2 de octubre de 2025

Esta versión introduce una mejora en la forma en que las reglas de reparto de costes gestionan los nuevos valores de dimensión empresarial en Cloudability.

Puede configurar sus reglas de reparto de costes y los correspondientes grupos como una declaración de inclusión o exclusión. Al seleccionar «incluir», está incluyendo explícitamente los valores de la dimensión empresarial a los que desea asignar. Al seleccionar «excluir», se asignarán todos los valores de dimensión empresarial (incluidos los nuevos valores de dimensión empresarial) de forma predeterminada, a menos que se elija excluirlos explícitamente.

La nueva función **Excluir** ayuda a eliminar el trabajo manual de actualizar cada regla de reparto de costes cada vez que se añaden nuevos valores a las dimensiones de su negocio.

## Cloudability Contenedores: IBM FinOps Agente: 1 de octubre de 2025

Esta versión presenta el agente IBM FinOps. IBM FinOps Agent consolida y optimiza la recopilación de métricas, al tiempo que introduce nuevas capacidades en materia de seguridad, resiliencia y experiencia de instalación.

IBM FinOps El agente está diseñado para sustituir al antiguo agente Metrics. También servirá como base de datos para futuras versiones de funciones.

Nota: Los agentes de métricas seguirán funcionando. Sin embargo, le recomendamos encarecidamente que comience a migrar a IBM FinOps Agent para acceder a las nuevas funciones y a una mayor fiabilidad.

Nuevas características:

- **Helm Instalación basada en:** Se ajusta a las prácticas recomendadas de Kubernetes para simplificar la implementación y las actualizaciones.
- **Claves API autogestionadas:** se integra con las claves API de Frontdoor, lo que le permite crear, rotar y gestionar credenciales para cumplir con sus requisitos de seguridad.
- **Mayor resiliencia:**
  - **Recuperación ante desastres para cargas:** utiliza volúmenes persistentes para conservar los datos recopilados durante reinicios o problemas de servicio.
  - **Captura de pods de corta duración:** asigna los costes con mayor precisión a las cargas de trabajo transitorias.
- **Arquitectura preparada para el futuro:** proporciona la base para futuras innovaciones en el conocimiento de los contenedores

Visite [Provision your container agent](../product/container-metrics-agent-provisioning.html) para obtener más información.

## Compromiso de apoyo a la base de datos « Azure » (La historia de la comunidad afroamericana de Filadelfia) para PostgreSQL – 30 de septiembre de 2025

Hoy hemos lanzado la compatibilidad con la base de datos Azure para PostgreSQL. El décimo tipo de compromiso Azure compatible, la base de datos Azure para compromisos PostgreSQL, ofrece un descuento en la computación a cambio de un compromiso de uno o tres años de uso por hora. Este tipo de compromiso se clasifica como compromiso basado en recursos y, como tal, requiere la selección de parámetros de uso específicos: opción de implementación, instancia y región. Con esta versión, admitimos este tipo de compromiso tanto en la cartera de compromisos como en las recomendaciones.

Para obtener más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Compromiso de apoyo a la capacidad reservada de Azure Blob Storage – 29 de septiembre de 2025

Hoy hemos lanzado la compatibilidad con la capacidad reservada de Azure Blob Storage. El noveno tipo de compromiso de capacidad reservada de Azure compatible, Azure Blob Storage Los compromisos de capacidad reservada ofrecen un descuento en la capacidad para bloques de datos y para datos de Azure Data Lake Storage a cambio de un compromiso de uno o tres años de uso por hora. Este tipo de compromiso se clasifica como compromiso basado en recursos y, como tal, requiere la selección de parámetros de uso específicos: nivel de acceso, redundancia, tamaño y región. Con esta versión, admitimos este tipo de compromiso tanto en la cartera de compromisos como en las recomendaciones.

Para obtener más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Mejoras en la usabilidad: vistas, usuarios y grupos – 29 de septiembre de 2025

Esta versión ofrece múltiples mejoras de usabilidad en las funciones Vistas, Usuarios y Grupos:

- **Duplicar/Clonar una vista** : como administrador de vistas, a menudo es necesario crear varias vistas que compartan filtros y permisos similares. Recrear manualmente cada vista puede llevar mucho tiempo y resultar repetitivo. Los administradores de vistas ahora pueden utilizar la opción «Duplicar» para duplicar/clonar vistas con un solo clic, copiando filtros, permisos y configuraciones al instante. Solo cambia el nombre y ajusta según sea necesario. Esto ahorra tiempo y reduce los errores al crear vistas similares. Para obtener más información, consulte [Duplicar una vista](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=administration-create-manage-views#topic__title__5 "(se abre en una pestaña o una ventana nueva)").
- **Mostrar uso de la vista predeterminada** : antes de eliminar o restringir el acceso a una vista, los administradores ahora pueden ver quién la está utilizando activamente como predeterminada.

  La nueva opción de la interfaz de usuario «Mostrar uso predeterminado» permite a los administradores ver los usuarios que han establecido una vista como predeterminada, ya sea compartida directamente o a través de grupos. Esto ayudará a los administradores de vistas a tomar decisiones informadas antes de eliminar o restringir vistas. Para obtener más información, consulte [Mostrar uso predeterminado](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=administration-create-manage-views#topic__title__9 "(se abre en una pestaña o una ventana nueva)").
- **Exportación mejorada de « CSV** » para vistas: las exportaciones de « CSV » ahora incluyen los campos «Usuarios de vista predeterminados», «Grupos compartidos con», «Propietario» y «Descripción». La lista **de usuarios de la vista predeterminada** ayuda al administrador a identificar a los usuarios que la utilizan como vista predeterminada. Estas incorporaciones mejoran la visibilidad y la colaboración entre los administradores de View.
- **Validación del nombre de la vista duplicada** : ahora los nombres de las vistas se validan a medida que se escriben durante su creación. Si ya existe un nombre, aparecerá un mensaje de error y el botón Guardar estará desactivado. Esto evita que el panel se cierre y garantiza que introduzcas un nombre único sin perder tu trabajo.
- **Editar varios en la interfaz de usuario de asignación de View** : esta corrección en la interfaz de usuario de asignación de View restaura la visibilidad de los usuarios y grupos para la función «Editar varios». Una nueva advertencia aclara que los cambios se aplican a todas las vistas seleccionadas, lo que evita ediciones masivas accidentales.
- **API públicas para grupos de usuarios y grupos de ID de Entra** : los grupos de usuarios y los grupos de ID de Entra ahora tienen API públicas. Esto facilita la integración y automatización de los flujos de trabajo relacionados con el grupo. Para obtener más información, consulte [la documentación de la API](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=api-user-groups-entra-id-groups-end-point "(se abre en una pestaña o una ventana nueva)").
- **Visibilidad del correo electrónico y búsqueda de correo electrónico en la gestión de usuarios** : la interfaz de usuario de gestión de usuarios (en Configuración > Usuarios y grupos) ahora muestra las direcciones de correo electrónico y admite la búsqueda basada en el correo electrónico. Esto ayuda a los administradores a identificar rápidamente a los usuarios, especialmente cuando los nombres son similares. Para obtener más información, consulte [Administrar usuarios](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=groups-manage-users-user-views-dashboards "(se abre en una pestaña o una ventana nueva)").

## Tablas dinámicas en paneles de control – 24 de septiembre de 2025

Cloudability Los paneles de control incorporan la funcionalidad de las tablas dinámicas. Esta mejora permite a los usuarios utilizar los valores de dimensión como columnas, lo que facilita el análisis del desglose de métricas por cualquier dimensión.

Las tablas dinámicas proporcionan una forma eficaz de resumir, analizar y explorar los datos utilizando los valores de cualquier dimensión como columna de la tabla. Los usuarios pueden agregar fácilmente datos por categoría, fecha o cualquier otra dimensión.

Estas tablas están habilitadas de forma predeterminada para todas las tablas existentes del panel de control de Cloudability. Próximamente se añadirán funciones de control adicionales, como habilitar/deshabilitar pivotes y configurar un valor de pivote predeterminado.

## Integración con Jira Cloud y ServiceNow – 24 de septiembre de 2025

Con esta versión, presentamos la compatibilidad para **integrar Jira Cloud y ServiceNow con Anomaly Detection**. Esto permite a los usuarios crear y realizar un seguimiento rápido de los tickets de investigación de anomalías, con actualizaciones automáticas bidireccionales del estado, lo que agiliza los flujos de trabajo y acelera la resolución de incidentes.

## Apoyo a AWS Lambda en el inventario de recursos de Cloudability – 19 de septiembre de 2025

Con esta versión, introducimos la compatibilidad con el servicio AWS Lambda en Resource Inventory, lo que ayudará a los clientes a crear una lista autorizada de sus recursos lambda de AWS. Pueden combinar información sobre costes, utilización y otros aspectos clave relacionados con los recursos Lambda, como el tamaño de la memoria de la función, la última modificación de la función, el número medio de invocaciones, etc., lo que les ayudaría a tomar medidas de optimización de forma más proactiva.

## Acciones masivas en la acreditación de proveedores AWS / GCP – 18 de septiembre de 2025

Cloudability Las credenciales de proveedor introducen acciones masivas para AWS y GCP. Esto facilita la incorporación de cuentas de AWS y GCP, ya que los usuarios pueden guardar, actualizar o verificar cuentas rápidamente.

AWS Documentación - [AWS Acreditación mediante acciones masivas](../admin/aws-credentialing-bulk-actions.html)

GCP Documentación - [GCP Acreditación mediante acciones masivas](../admin/gcp-credentialing-bulk-actions.html)

Nota: Ponte en contacto con el servicio de asistencia o con tu gestor de cuentas, TAM o CSM de Apptio para solicitar acceso a esta función.

## Mejoras en la usabilidad del inventario de recursos de Cloudability – 10 de septiembre de 2025

Esta versión incluye dos mejoras en la usabilidad

- **Filtrado estadístico mejorado** : anteriormente, los filtros Mostrar superior/inferior del Inventario de recursos siempre se aplicaban al informe completo, incluso si los usuarios tenían otros filtros globales activados. Con esta versión, la selección superior/inferior ahora se aplica directamente al conjunto de datos filtrados, lo que garantiza que los usuarios solo vean los recursos más relevantes. Por ejemplo, si el usuario ha filtrado un informe de 100 registros a 70 (utilizando filtros globales) y luego ha seleccionado el 50 % superior, ahora verá los 35 primeros de esos 70—not de los 100 originales.
- **Nuevo KPI para Azure** : hemos añadido un nuevo KPI denominado «Total de instancias» en el servicio de computación Azure, que permite a los usuarios filtrar rápidamente aquellas instancias de computación que pertenecen a la familia de uso de instancias de otras familias de uso, como Transferencia de datos, Licencias, etc.

## Cloudability Gobernanza - Vista previa pública - 10 de septiembre de 2025

Cloudability lanza Governance Public Preview, una nueva función que ofrece información proactiva sobre los costes y la aplicación de políticas directamente en el flujo de trabajo de ingeniería. A partir de hoy, los equipos pueden asegurarse de que los cambios en la infraestructura sean **rentables** y **cumplan** con las políticas de la organización antes de implementarlos.

Cloudability La gobernanza ya está disponible para **los ingenieros** de DevOps, **los administradores de plataformas** y **los equipos** de FinOps que gestionan recursos de AWS y utilizan **Terraform**, ya sea a través de **Terraform Community**, **HCP Terraform** o **Terraform Enterprise**, para su solución de infraestructura como código. Esta función está diseñada para equipos que alojan sus repositorios de código en **GitHub.com**, incluido **GitHub Enterprise Cloud**.

Anteriormente, las prácticas de « FinOps » (diseño basado en el rendimiento) solían introducirse demasiado tarde en el ciclo de vida del desarrollo, lo que provocaba un desajuste entre los departamentos de finanzas e ingeniería. Este retraso obligó a realizar costosas modificaciones, ya que los equipos dependían de revisiones manuales o auditorías posteriores a la implementación para detectar ineficiencias en los costes e incumplimientos de las políticas, lo que provocó un gasto excesivo, riesgos de cumplimiento y tareas de corrección inesperadas para los ingenieros.

**Cloudability Gobernanza (vista previa pública)**

**Descripción**

Cloudability Governance se integra con GitHub y Terraform para aplicar las políticas de FinOps y aportar visibilidad de los costes al proceso de CI/CD. Las capacidades clave incluyen:

- **Estimación de costes previa a la implementación** : estimaciones de costes en tiempo real de AWS, incluidos precios personalizados y descuentos de EA, directamente en los flujos de trabajo de GitHub y Terraform
- **Selección de recursos con optimización de costes** : recomendaciones para alternativas más económicas de EC2 y RDS con configuraciones similares
- **Aplicación de políticas a nivel de IaC** : aplique etiquetas obligatorias, bloquee recursos heredados y establezca umbrales presupuestarios
- **Supervisión del cumplimiento** : panel de control centralizado para supervisar el cumplimiento de las políticas de FinOps
- **Gestión de relaciones públicas** : identifique y revise las solicitudes de extracción que no cumplen con los requisitos mediante flujos de trabajo de aprobación integrados
- **Ejecutar la integración de tareas con HCP Terraform** : Integre a la perfección la gobernanza de la plataforma de código abierto ( Cloudability ) como una **tarea de ejecución** en los espacios de trabajo de HCP Terraform. Esto permite que las comprobaciones de políticas se activen automáticamente durante la fase de planificación de una ejecución de Terraform, lo que permite la aplicación de medidas consultivas u obligatorias antes de que se aprovisione la infraestructura.

  Esta función cambia la gestión de los costes de la nube de reactiva a proactiva, lo que ayuda a los equipos a evitar el gasto excesivo y las infracciones de políticas antes de que se implemente la infraestructura.

Para obtener más información, consulte [Gobernanza: Introducción.](../admin/governance-getting-started.html)

## Deseleccionar todas las dimensiones en el panel de control – 4 de septiembre de 2025

Cloudability Los paneles introducen una mejora que permite a los usuarios seleccionar una sola dimensión de la leyenda del gráfico. Pueden centrarse fácilmente en una sola dimensión, sin tener que descartar otras dimensiones de la leyenda individualmente.

## Compatibilidad con bases de datos gestionadas por OCI en la planificación de cargas de trabajo: 28 de agosto de 2025

Los usuarios de Planificación de la carga de trabajo pueden crear estimaciones de la carga de trabajo para OCI Managed Database. Anteriormente, el servicio de bases de datos gestionadas era compatible con todos los proveedores de nube excepto OCI. Con esta versión, ofrecemos compatibilidad con MySQL y PostgreSQL, que son los servicios de bases de datos gestionadas disponibles actualmente para OCI.

## Ajustar valores negativos en los gráficos de los paneles de control – 27 de agosto de 2025

Esta versión introduce una mejora que permite a los usuarios escalar automáticamente el eje Y de sus gráficos para ajustar los valores negativos. Anteriormente, todos los ejes de los gráficos comenzaban en 0 y para ver los valores negativos era necesario configurar manualmente la opción estática «escala inicial». Esta opción está habilitada de forma predeterminada para los nuevos gráficos, pero los usuarios pueden desactivarla desmarcando la casilla «Iniciar escala desde el valor más bajo». Los gráficos existentes y los configurados anteriormente no cambiarán su comportamiento.

## Copiar y pegar listas de filtros separadas por comas en paneles y informes – 27 de agosto de 2025

Esta versión introduce una mejora que permite a los usuarios copiar y pegar una lista de filtros separados por comas en los paneles de control y los informes de Cloudability.

Los usuarios pueden:

- Copie la lista de valores de los filtros utilizando Ctrl+C en el campo de valores.
- Pega una lista separada por comas en el campo de valor, utilizando Ctrl+V, que se separará automáticamente en valores individuales.
- Los valores que contienen la coma «,» como parte del valor se escapan de la siguiente manera: «valor único\».

## Mejoras en la usabilidad de los grupos de usuarios y los grupos de ID de Entra – 25 de agosto de 2025

Esta versión introduce más mejoras en la usabilidad de las funciones Grupos de usuarios y Grupos de Entra ID:

- La confirmación de eliminación para los grupos de ID de usuario/Entra ahora muestra el número de usuarios del grupo.
- Los nombres de grupo, que están limitados a 63 caracteres, ahora ofrecen validación en tiempo real y mensajes de error mejorados.
- La clasificación está habilitada en todas las columnas de las listas de usuarios y grupos de ID de Entra, con la clasificación predeterminada por fecha de creación (más reciente primero)
- Se ha añadido un ámbito predeterminado y un texto de sugerencia al modal de sincronización de Entra ID para mejorar la usabilidad.
- Pequeños cambios en la interfaz de usuario en la pantalla Usuarios.

Para obtener más información sobre los grupos de usuarios y los grupos de Entra ID, consulte [Administrar usuarios y grupos de usuarios.](../admin/manage-users-and-user-groups.html)

## Cloudability Contenedores: Presentación del filtro de visualización previa y posterior – 14 de agosto de 2025

Esta versión introduce filtros de visualización previos y posteriores, lo que permite un control preciso sobre el filtro de datos y la visualización en los paneles y widgets de contenedores de Cloudability.

- Los filtros de previsualización se aplican antes de la agregación de datos, de forma similar a los filtros que se utilizan actualmente en Cloudability.
- Los filtros de posvisualización se aplican después de la agregación de datos, lo que permite refinar y centrarse en los resultados mostrados sin alterar los valores agregados.

Los nuevos filtros están disponibles en la vista de tabla del panel de control, así como en los siguientes widgets personalizados:

- Series temporales personalizadas
- Personalizado superior/inferior
- Asignación personalizada frente a inactivo

Los widgets de KPI personalizados solo admiten filtros de previsualización.

Nota: Los filtros previos y posteriores aplicados en los widgets se transfieren al crear alertas automáticamente.

**Mejoras adicionales** :

- Gestión dinámica de entradas para ajustar automáticamente los tipos de entrada en función de las métricas seleccionadas.
- Reglas de validación para evitar combinaciones incompatibles de filtros y métricas.
- Interfaz de usuario nueva y mejorada para facilitar la navegación.
- Capacidad de los filtros para utilizar el operador AND para combinar múltiples condiciones.

Para obtener más información sobre los contenedores de Cloudability, consulte [Contenedores Insights: Guía del panel y los widgets](../product/containers-insight-2-dashboard-widget-guide.html).

## Cloudability Contenedores: Presentación de la herramienta de observabilidad Metrics Agent – 14 de agosto de 2025

Esta versión presenta la herramienta Agent Observability Tool, que le proporciona visibilidad en tiempo real del estado y la salud de los agentes de métricas de Cloudability en todos sus clústeres de Kubernetes. Los datos se representan en una tabla con los siguientes campos como columnas:

- Lista de clústeres: muestra todos los clústeres en los que está instalado un agente de métricas de Cloudability.
- Estado del agente: muestra si su agente está activo o inactivo. El estado se establece como Inactivo si el valor de Última vez visto es superior a 12 horas para el clúster.
- Versión del agente: muestra la versión instalada del agente de métricas para que pueda asegurarse de que está ejecutando la última versión.
- Versión del clúster: muestra la versión de Kubernetes / Openshift que se utiliza para cada clúster.
- Última vez visto: indica la última vez que Cloudability recibió datos del agente de métricas.
- Tipo de clúster: identifica el tipo de clúster (por ejemplo, EKS, ROSA ).
- Proveedor: muestra el proveedor de servicios en la nube asociado al clúster (por ejemplo, AWS ).
- Filtro
  - Filtro de estado de los agentes: filtra la lista por agentes activos, inactivos o todos los agentes para centrarse en los grupos que requieren atención.
  - Filtro de proveedores: filtra los clústeres que se ejecutan en proveedores de nube específicos para una supervisión específica.

Para obtener más información, consulte [la herramienta Agent Observatory Tool](../product/agent-observatory-tool.html).

## Mejoras en la función Usuarios y grupos – 13 de agosto de 2025

Esta versión introduce dos mejoras en las funciones de grupos de usuarios y grupos de Entra ID recientemente lanzadas:

- **Acceso basado en permisos** : anteriormente limitado al rol «Administrador de Cloudability », el acceso a los grupos de usuarios y a los grupos de Entra ID ahora se ajusta a los permisos existentes. Esto garantiza que los administradores que anteriormente tenían acceso a la función de gestión de usuarios seguirán teniendo acceso a Usuarios y grupos sin necesidad de un rol adicional.
- **Eliminar grupos de Entra ID** : Ahora puede eliminar grupos de Entra ID en Cloudability. Esta actualización cumple con un compromiso posterior al lanzamiento general al ofrecer la compatibilidad prometida con la eliminación de grupos de Entra ID.

## FinOps Validador FOCUS de la Fundación en otras fuentes de datos (FOCUS) – 7 de agosto de 2025

Esta versión añade el enlace del validador FOCUS de la Fundación para la Educación en el Cuidado de la Salud ( FinOps ) en la pantalla de acreditación de Otras fuentes de datos (FOCUS) dentro de Cloudability.

Esto ayudaría a validar el archivo con formato FOCUS y a comprobar si hay errores antes de cargar el archivo en el almacenamiento compartido para la entrada de datos.

## Detección de anomalías: mejoras en la experiencia de usuario – 6 de agosto de 2025

Esta versión lanza actualizaciones de la interfaz de usuario de detección de anomalías:

- La función Exportar exporta datos de anomalías del conjunto de datos seleccionado utilizando las dimensiones existentes.
- La columna Porcentaje le permite ver el impacto contextual de las anomalías, lo que mejora el análisis sin conexión, simplifica la generación de informes y facilita el intercambio de información entre equipos sin intervención manual
- La columna «Porcentaje inusual » le ayuda a comparar los picos de costes anormales con los gastos previstos.

Para obtener más información, consulte [Detección de anomalías](../product/identify-unusual-spending-patterns-with-anomaly-detection.html).

## Apoyo a Kubernetes Service en la planificación de la carga de trabajo – 5 de agosto de 2025

Los usuarios de Planificación de la carga de trabajo pueden crear estimaciones de la carga de trabajo para un servici Kubernetes e en diferentes proveedores de nube. Al igual que con las máquinas virtuales y las bases de datos, puede hacerlo para AWS, Azure, GCP y OCI. Seleccione « Kubernetes » (Clústeres de datos de tiempo real) en el menú desplegable «Service Type» (Tipo de servicio) e indique el número de clústeres para generar diferentes opciones de precios. Opcionalmente, defina su configuración de nodo específica para obtener recomendaciones de precios combinadas tanto para clústeres como para máquinas virtuales.

## Cloudability Información sobre contenedores: Cambio en la estrategia de asignación de costes para los clústeres de Azure – 4 de agosto de 2025

Cloudability Introduce la agrupación de métricas y dimensiones en el modo de edición del widget para facilitar la navegación. Los administradores pueden expandir y contraer las listas de medidas basadas en la fuente de datos. Esta función está disponible tanto en los paneles de control como en los informes.

Esta versión mejora la metodología de asignación de costes para los clústeres de Azure Kubernetes para Cloudability Container Insights. Los costes ahora se asignan a nivel de nodo, lo que permite la asignación de PVC (Persistent Volume Claim) para el almacenamiento gestionado por CSI de Azure.

Se han realizado las siguientes mejoras para optimizar la distribución de costes entre las cargas de trabajo:

- Asignación de costes a nivel de nodo: ahora los costes se asignan con precisión en función del nodo real en el que se ejecuta un pod, teniendo en cuenta el tipo de nodo, el tiempo de actividad y los patrones de uso.
- Asignación de costes de PVC: los costes de PVC aprovisionados a través del controlador CSI de Azure ahora se atribuyen directamente a las cargas de trabajo que los consumen.
- Costes varios: Azure - Los gastos generales de los clústeres nativos, como las direcciones IP públicas y los equilibradores de carga, ahora se clasifican claramente en «Varios» para mejorar la visibilidad.
- Mayor precisión a nivel de contenedor: la asignación de costes ahora refleja el uso real de los recursos de la carga de trabajo, en lugar de valores promediados entre todos los nodos.

FinOps y los equipos de ingeniería ahora pueden:

- Obtenga una mayor visibilidad de los costes reales de la carga de trabajo.
- Optimice los tipos de nodos y la programación para lograr una mayor rentabilidad.
- Separar los gastos generales de aplicación e infraestructura.

Para obtener más información, consulte [Asignación de costes de contenedores](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=insights-container-cost-allocation "(se abre en una pestaña o una ventana nueva)").

## Agrupación de métricas y dimensiones en la edición de widgets – 30 de julio de 2025

Cloudability Introduce la agrupación de métricas y dimensiones en el modo de edición del widget para facilitar la navegación. Los administradores pueden expandir y contraer las listas de medidas basadas en la fuente de datos. Esta función está disponible tanto en los paneles de control como en los informes.

## Mejoras en los correos electrónicos con resúmenes de gastos en la nube – 30 de julio de 2025

Se han realizado las siguientes mejoras en el contenido del correo electrónico con el resumen de gastos:

- Se ha añadido el nombre del entorno « Cloudability » en el correo electrónico
- Se ha añadido la fecha de la última actualización de la estimación de fin de mes
- Reducción del plazo de entrega de los correos electrónicos de 10 a 3 horas

## Nuevos permisos de « Turbonomic » (Añadir/Editar/Ver) para « GCP » (Añadir/Editar/Ver) para usuarios Premium – 28 de julio de 2025

Esta versión introduce dos nuevos permisos « Turbonomic » en Cloudability Premium para la detección de MIG ( GCP ):

- *compute.autoscalers.list*
- *compute.instanceTemplates*

Estos permisos permiten a Turbonomic descubrir y recuperar recursos MIG en su entorno mejorando la optimización.

Para obtener una lista detallada de los permisos de Turbonomic en Cloudability, [consul](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=gcp-read-only-permissions-reference "(se abre en una pestaña o una ventana nueva)") te Referencia de permisos de solo lectura: GCP.

## Optimización del ROI: corrección del cálculo del ahorro real – 25 de julio de 2025

Esta versión corrige el problema con la visualización del valor normalizado de ahorro realizado en el cálculo del retorno de la inversión (ROI) de Rightsizing de Cloudability.

Los tickets de ROI de Rightsizing muestran los ahorros realizados normalizados a un período de 30 días. Anteriormente, para algunos tickets creados manualmente con recursos terminados, el valor del ahorro realizado solo se calculaba para un período de 10 días.

Todas las entradas reflejarán un período de cálculo de 30 días, lo que se traducirá en un aumento del valor de sus ahorros históricos realizados.

Para obtener más información, consulte [Puntos finales del ROI de redimensionamiento](../api-v3/rightsizing-roi-end-points.html).

## Alerta por correo electrónico sobre el estado de las credenciales de los proveedores – 24 de julio de 2025

Esta versión introduce alertas por correo electrónico sobre el estado de las cuentas en «Vendor Credentials» (Credenciales de proveedores) en « Cloudability » (Gestión de cuentas de proveedores).

- Alertas opcionales: los administradores pueden suscribirse a alertas diarias, semanales o mensuales. Comprueba si tus cuentas están completamente acreditadas, o si están incompletas o tienen errores.
- Información útil: cada correo electrónico incluye enlaces directos a Cloudability con filtros de proveedores y cuentas preaplicados, lo que facilita actuar cuando sea necesario.

## Añadir nuevos banners para las acciones de credenciales de proveedores – 24 de julio de 2025

Esta versión añade dos banners en la página «Vendor Credentials» (Credenciales de proveedor) que resumen las acciones necesarias en varias cuentas de Cloudability. Estos banners, que actúan como filtros rápidos, resaltan el número de cuentas no válidas e incompletas en las que es necesario tomar medidas.

## Mejoras en la usabilidad de la planificación de la carga de trabajo – 16 de julio de 2025

Esta versión aborda los siguientes retos de usabilidad en la planificación de la carga de trabajo:

- Proporcionar una lista de todos los tipos de recursos compatibles para la importación masiva
- Rellenar automáticamente los parámetros de entrada en el almacenamiento adjunto según la configuración introducida en VM
- Categorización de los tipos de recursos informáticos y de bases de datos en el menú desplegable de tipos de recursos
- Soporte para notificaciones por correo electrónico cuando se ha compartido una carga de trabajo

Para obtener más información, consulte [Obtener recomendaciones para la planificación de la carga de trabajo.](../product/get-recommendations-for-workload-planning.html)

## Cloudability Premium : Desactivación de la integración de Turbonomic para los clientes – 15 de julio de 2025

Esta versión deshabilita Turbonomic como fuente de datos en las credenciales de proveedor para los clientes de Cloudability Premium. Ahora puede seleccionar cualquier período para las actualizaciones automáticas diarias en el panel de control.

Cloudability Premium Los clientes tienen credenciales unificadas entre Cloudability y Turbonomic. Seguirán viendo estas métricas en Turbonomic cambiando a través de su entorno Frontdoor. Para los clientes de Cloudability Standard y Essentials, Turbonomic sigue estando disponible para añadirlo como fuente de datos en Cloudability.

Para obtener más información, consulte [Turbonomic](../product/turbonomic.html).

## Cloudability Paneles: Cambios personalizados de fecha móvil: 9 de julio de 2025

Esta versión añade otra opción a los paneles de control de Cloudability para configurar los intervalos de fechas continuos. Ahora puede seleccionar cualquier período para las actualizaciones automáticas diarias en el panel de control.

## Cloudability Credenciales del proveedor: Descontinuación de la compatibilidad con las API de informes de EA de Azure : 9 de julio de 2025

Esta versión deja de admitir las API en las credenciales de proveedor de Cloudability para Microsoft Azure.

En adelante, utilice las API de gestión de costes o las exportaciones de Azure para añadir cuentas EA de Azure a Cloudability.

Para obtener más información, consulte [Conexión con una API de detalles de costes de EA ( Azure )](../admin/azure-cmapi-ea.html).

## Soporte para grupos de usuarios y grupos de Entra ID en Cloudability – 8 de julio de 2025

Esta versión incluye compatibilidad con grupos de usuarios y grupos de Microsoft Entra ID en Cloudability. Los administradores ahora pueden crear grupos de usuarios manualmente o importarlos desde Entra ID. Esto le ayuda a asignar de manera eficiente vistas a los usuarios en función de equipos, roles o unidades de negocio.

Mejoras:

- Creación manual de grupos de usuarios: cree y gestione grupos de usuarios personalizados en Cloudability y añada usuarios a ellos. Una vez creados, puedes trabajar con estos grupos en la asignación de vistas.
- Integración de grupos de Microsoft Entra ID : Autentique su Microsoft Entra ID e importe grupos de Entra ID a Cloudability utilizando los criterios de sincronización personalizados.

Para obtener más información, consulte [Administrar usuarios y grupos de usuarios](../admin/manage-users-and-user-groups.html) y [Conectar Microsoft Entra ID.](../admin/connect-microsoft-entra-ID.html)

## Cloudability Contenedores: Configuración para configurar un proxy en GetUploadURL– 7 de julio de 2025

Esta versión introduce nuevas opciones de configuración en el agente de métricas Cloudability. Esto proporciona más flexibilidad para gestionar la configuración del proxy para llamadas salientes específicas realizadas por el agente.

El agente de métricas Cloudability realiza dos llamadas salientes:

- La primera llamada genera un URL. La segunda llamada carga los datos en el bucket S3 utilizando el URL.
- La nueva bandera de configuración CLOUDABILITY\_USE\_PROXY\_FOR\_GETTING\_UPLOAD\_URL\_ONLY para el agente de métricas de Cloudability, cuando se establece en true, aplica el proxy solo a la primera llamada.

Para obtener más información, consulte [«Aprovisionamiento de clústeres»](../product/k8s-cluster-provisioning.html) en Kubernetes

## Cloudability Descontinuación de los contenedores 1.0 : 7 de julio de 2025

Esta versión deja de admitir Container Insights 1.0. Ahora se le redirigirá a Container Insights 2.0.

En adelante, utilice las API de gestión de costes o las exportaciones de Azure para añadir cuentas EA de Azure a Cloudability.

Para obtener más información, consulta [Cloudability Container Insights 2.0.](https://community.ibm.com/community/user/blogs/apptio-community-member/2024/07/10/cloudability-container-insights-20 "(se abre en una pestaña o una ventana nueva)").

## Cambiar los intervalos de fechas en los paneles de control de Cloudability – 1 de julio de 2025

Esta versión incluye actualizaciones en los paneles de control de Cloudability que le permiten cambiar el intervalo de fechas para todos los widgets de un informe.

El selector de rango de fechas global está disponible en todos los informes de forma predeterminada.

## Cloudability 2.13.0 : gestión de secretos y actualizaciones de plantillas – 1 de julio de 2025

Esta versión actualiza Metrics Agent versión 2.13.0 con la capacidad de CLOUDABILITY\_API\_KEY para alinearse con las mejores prácticas de Kubernetes para la gestión de secretos. Esto mejora la seguridad de las credenciales utilizadas por el agente.

Las mejoras incluyeron:

- Gestión secreta montada en volumen : CLOUDABILITY\_API\_KEY ahora se almacena como un volumen en el pod del agente de métricas, sustituyendo el método anterior de configurarlo directamente como una variable de entorno.
- Compatibilidad con la interfaz de usuario y el aprovisionamiento de Helm : este cambio se refleja en el flujo de trabajo de aprovisionamiento dentro de la interfaz de usuario y para las instalaciones de Helm a partir de la versión 2.13.0. Para las instalaciones de Helm, descodifique primero la clave base64. Para obtener instrucciones detalladas sobre la configuración, consulta [https://cloudability.github.io/metrics-agent/](https://cloudability.github.io/metrics-agent/ "(se abre en una pestaña o una ventana nueva)").
- Actualización del punto final de aprovisionamiento : Se realizan las siguientes actualizaciones en el punto final de aprovisionamiento para todos los clientes, independientemente de la versión del agente de métricas.
  - La clave API se ha trasladado automáticamente a Kubernetes Secret.
  - Base64 Se utiliza para codificar los datos de la clave API, lo que garantiza la ejecución fluida de kubectl apply -f <plantilla> durante el aprovisionamiento.
- Ruta de archivo configurable : ahora puede definir dónde almacenar la clave API utilizando la variable de entorno CLOUDABILITY\_API\_KEY\_FILEPATH para rutas de montaje personalizadas.

El agente de métricas de Cloudability seguirá admitiendo CLOUDABILITY\_API\_KEY como variable de entorno para garantizar la compatibilidad con versiones anteriores, pero le recomendará que realice la transición a secretos montados en volumen.

Para obtener más información, consulte [«Aprovisionamiento de clústeres»](../product/k8s-cluster-provisioning.html) en Kubernetes.

## Cloudability Datos y vistas jerárquicos – 30 de junio de 2025

Esta versión añade compatibilidad con jerarquías para los mapeos y vistas empresariales con el fin de gestionar los resúmenes de costes en Cloudability.

Cloudability generará automáticamente:

- Un mapeo empresarial para cada capa con lógica de acumulación
- Un conjunto correspondiente de vistas anidadas mediante mapeo

Mejoras:

Cree asignaciones empresariales jerárquicas con precisión en los costes.

- Automatizar los mapeos empresariales para respaldar los resúmenes de costes
- Habilite la generación de informes multinivel con dimensiones empresariales

Optimizar la creación y el mantenimiento de vistas resumidas.

- Generar automáticamente vistas jerárquicas a partir de mapeos jerárquicos de negocios
- Gestiona datos y vistas desde un único punto de control
- Simplifique el uso compartido y la gestión del acceso de los usuarios con la herencia de View Access

- Integración CFP
- Múltiples niveles de propiedad de los costes en los planes
  - Compatible con hasta 5 dimensiones de propiedad de costes
  - Acumular automáticamente los costes por jerarquía presupuestaria
- Utiliza vistas para filtrar planes.
  - Aplicar vistas jerárquicas para filtrar planes
  - Controle el acceso y la visibilidad en función de los niveles de consolidación

Para obtener más información, consulte [Organizar vistas mediante vistas jerárquicas](../admin/hierarchical-views.html).

## Apoyo a Kubernetes v1.33 y OpenShift 4.18 – 30 de junio de 2025

Esta versión incluye compatibilidad con Kubernetes versión 1.33 y OpenShift 4.18 para el agente de contenedores Cloudability. Esta actualización le permite mantener una visibilidad completa de los costes de los contenedores para Kubernetes v1.33 en EKS, GKE, AKS y entornos OKE, así como Open Shift 4.18.

Para obtener más información, consulte [«Aprovisionamiento de clústeres»](../product/k8s-cluster-provisioning.html) en Kubernetes.

## Mejoras en la usabilidad de las vistas – 30 de junio de 2025

Hemos lanzado las siguientes mejoras clave en la usabilidad de Views:

- Visualización de los nombres de los propietarios junto a cada vista para garantizar la transparencia, la responsabilidad y un mejor mantenimiento
- Adición de un campo de descripción para cada vista con el fin de añadir información contextual sobre su finalidad y uso para una mejor gestión de las vistas obsoletas y redundantes

## Costes compartidos en la API de informes – 27 de junio de 2025

Esta versión introduce los costes compartidos en la API de informes de Cloudability. Con las nuevas dimensiones añadidas, como «Tipo de coste» y «Fuente de asignación», ahora puede acceder a los datos sobre los costes asignados de forma más eficiente

Para obtener más información, consulte [Punto final de informes de costes](../api-v3/cost_reporting_endpoints.html).

## Apoyo al inventario de recursos de GCP – 26 de junio de 2025

Esta versión introduce compatibilidad con el inventario de recursos de GCP. Esta función le permite informar sobre sus metadatos de costes, utilización y nivel de recursos para los servicios Compute y Persistent Disk en una única vista.

Puede habilitar la función Inventario de recursos desde el portal Active Admin correspondiente, dependiendo de su ubicación geográfica. En un plazo de 3-4 días hábiles tras su habilitación, recibirá los datos completos del inventario en Cloudability.

Para obtener más información sobre esta función, consulte [Inventario de recursos de GCP](../product/gcp-resource-inventory.html).

## Eliminación del menú desplegable del filtro de etiquetas del panel de control del contenedor – 25 de junio de 2025

Se ha eliminado el filtro desplegable Etiqueta de la página Asignación de costes del contenedor. Los filtros de etiquetas existentes se guardan automáticamente en «Añadir filtro». Vaya a Añadir filtro > Dimensión > Etiqueta para añadir los mismos filtros por clave y valor de etiqueta.

## Alerta de detección de anomalías para el aumento inicial – 25 de junio de 2025

Esta versión incluye mejoras en el algoritmo de detección de anomalías. Estas mejoras garantizan alertas rápidas a los clientes ante los primeros gastos excesivos en cualquier servicio. También incluye cobertura para anomalías de gasto reactivadas.

Para obtener más información sobre esta función, consulte [Detección de anomalías](../product/identify-unusual-spending-patterns-with-anomaly-detection.html).

## Soporte para Google BigQuery en la planificación de la carga de trabajo – 25 de junio de 2025

Los usuarios de Planificación de la carga de trabajo ahora pueden crear estimaciones de la carga de trabajo para un servici Google BigQuery. Seleccione « Google BigQuery » (Servicio de gestión de la carga de trabajo) en el menú desplegable «Service Type» (Tipo de servicio), indique los requisitos de servicio específicos para su carga de trabajo y genere diferentes opciones de precios para « BigQuery » (Carga de trabajo de Oracle Cloud).

Nota: A diferencia de otros servicios de planificación de la carga de trabajo, como máquinas virtuales y bases de datos, que ofrecen recomendaciones de precios de todos los proveedores de nube, este servicio solo ofrece opciones de precios para un servici Google BigQuery e en función de sus requisitos de recursos.

## Cloudability Totales de la tabla de paneles: 17 de junio de 2025

Hemos añadido una fila adicional para los paneles de control de Cloudability que incluye la suma de todas las filas visibles de la tabla en todos los widgets de tabla. Este comportamiento está habilitado de forma predeterminada y se aplica a todas las tablas. En las columnas que contengan números o divisas, la fila adicional mostrará la suma de todas las columnas visibles. En las columnas que contienen porcentajes, la fila adicional volverá a calcular el porcentaje para todo el conjunto de datos.

## Métricas de sostenibilidad en la nube GA – 16 de junio de 2025

Hemos lanzado métricas de sostenibilidad multicloud en Cloudability. Cloudability Los clientes pueden ver rápida y fácilmente estas métricas para obtener información sobre las emisiones de carbono de su nube pública, a las que antes tenían acceso limitado.

Ahora se puede acceder a las siguientes métricas de sostenibilidad desde los informes y paneles de control de Cloudability :

- Emisiones estimadas de carbono ( MTCO2e ) : recoge las emisiones estimadas de carbono en toneladas métricas de dióxido de carbono equivalente.
- Consumo de energía ( kWh ) : captura la energía consumida en kilovatios hora.

Hemos configurado un panel predeterminado en Cloudability para empezar, en la sección Todos los paneles, con el título Panel de ejemplo: sostenibilidad en la nube.

Para utilizar las métricas de sostenibilidad de la nube, siga los pasos que se indican a continuación:

1. Navega a la página de inicio de Cloudability.
2. Haga clic en Nuevo informe /Añadir widget.
3. En la sección «Métricas» ( Cloudability ), desplácese hasta la categoría «Sostenibilidad» (Sustainability).
4. Selecciona las métricas.

## Se añade compatibilidad con las etiquetas « GCP » (Añadir a favoritos) – 28 de mayo de 2025

Hemos lanzado la compatibilidad con las etiquetas GCP en Cloudability.

Anteriormente, Cloudability admitía etiquetas GCP. Con esta versión, Cloudability admite tanto etiquetas GCP como tags para visualizar los costes en todo Cloudability.

Con esta versión, Cloudability comenzará a incorporar etiquetas de GCP obtenidas junto con los datos de facturación de GCP, que se pueden configurar en la página Etiquetas y etiquetas de Cloudability. Una vez configuradas, se tratarán como otra dimensión de etiqueta y se podrán utilizar como etiquetas actuales, etiquetas o incluso como parte de las asignaciones empresariales dentro de Cloudability.

GCP Las etiquetas se muestran en el siguiente formato:

Clave = cldy:gcp:tag:<tagkey>

## Contenedores: Permitir que los widgets «Top 10» admitan diferentes límites – 27 de mayo de 2025

Ahora los usuarios pueden elegir entre una gama más amplia de opciones de clasificación al añadir un widget personalizado superior/inferior en el panel de control de asignación de costes de contenedores. Además de los 10 existentes, el widget ahora admite la opción de widgets superiores/inferiores de 25 a 50, lo que proporciona una mayor flexibilidad y visibilidad de los recursos que generan costes. Esta mejora le permite adaptar la información a sus necesidades de escala y análisis.

## Interfaz de usuario/experiencia de usuario mejoradas en la planificación de la carga de trabajo - 27 de mayo de 2025

Con esta versión, estamos realizando mejoras en la interfaz de usuario para:

1. Sección de información común, añadiendo una nueva carga de trabajo con una vista única para cada CSP
2. La diapositiva «Añadir recurso» se despliega, dando cabida a más campos de entrada cuando se proporcionan requisitos específicos de recursos por parte de un proveedor de servicios en la nube (CSP)
3. Se ha añadido información de ayuda en la interfaz de usuario para guiar a los usuarios a través de la función
4. Selección simplificada de regiones restringiéndola a la sección Proveedores de servicios en Información común únicamente
5. El menú desplegable Tipo de recurso en la sección Añadir recurso con información detallada y descriptiva. Como la configuración completa del recurso (`g5.12xlarge - 48 CPUs, 192 GB RAM,
   3800 GB Local Storage`) en lugar de solo su nombre (`g5.12xlarge`).

## Cloudability : mejora en el cálculo de métricas de sostenibilidad y compatibilidad ampliada con GPU para Azure y OCI Compute – 15 de mayo de 2025

Hemos lanzado un par de mejoras en Cloud Sustainability Metrics.

Hemos mejorado la metodología de cálculo de los indicadores de sostenibilidad en IBM Cloudability. Como resultado, los clientes notarán un aumento en los valores métricos en el futuro. Estos cambios se deben a una corrección aplicada a los cálculos subyacentes y no se aplicarán a los meses históricos.

Además, también hemos ampliado la compatibilidad con métricas de GPU. Aunque ya existía compatibilidad con AWS y GCP, esta versión mejora y añade compatibilidad con Azure y Oracle.

## Cloudability Premium : Actualización de las credenciales de los proveedores a ON/OFF en Acciones automáticas  – 14 de mayo de 2025

Hemos lanzado actualizaciones del estado ON/OFF dentro de las acciones automatizadas en la página de credenciales de proveedores en Cloudability Premium.

Anteriormente, para las credenciales del proveedor:

- Se mostraba OFF si la optimización se había configurado como de solo lectura.
- Se mostraba ON si la optimización se había configurado como Optimizar recursos.

Con esta versión, el encendido/apagado funcionará de la siguiente manera:

- Para AWS y GCP, si se selecciona la acreditación automatizada.
  - Automatizar acciones : ON/OFF seguirá la selección basada en la cuenta principal ( AWS Master Payer/ GCP Billing).
    - Si la cuenta principal está activada, todas las cuentas secundarias (cuentas vinculadas a AWS /proyectos de GCP ) estarán activadas.
    - Si la cuenta principal está desactivada, todas las cuentas secundarias estarán desactivadas.
  - Las cuentas infantiles no se pueden modificar individualmente cuando se opta por la acreditación automatizada.
- Para AWS y GCP, si no se selecciona la acreditación automatizada
  - Tanto las cuentas de padres como las de hijos pueden tener diferentes estados de activación/desactivación en Acciones automáticas.
  - El estado ON/OFF se puede cambiar individualmente sin ninguna dependencia entre el padre y el hijo.
- En el caso de Azure, el estado solo se refleja en las suscripciones durante el proceso de acreditación.

Nota: El estado ON/OFF se basa en la selección realizada en la interfaz de usuario en Cloudability con respecto a la elección de plantillas de solo lectura frente a optimización de recursos y no refleja el estado de Turbonomic.

## Cloudability Cost Sharing - Fuente de asignación en ApptioBI – 13 de mayo de 2025

Cloudability Anuncia el linaje para informar sobre los costes compartidos en ApptioBI. Hemos introducido una nueva dimensión denominada «Fuente de asignación» en ApptioBI,, que mejora la visibilidad de los costes compartidos configurados en Cost Sharing.

Anteriormente, los usuarios solo podían ver un resumen de los costes compartidos, lo que dificultaba el seguimiento de los orígenes. La nueva dimensión «Fuente de asignación», disponible en la proyección «Coste y uso (asignado)», aporta claridad al identificar las fuentes específicas que contribuyen a los costes compartidos. Los usuarios ahora pueden contextualizar fácilmente los datos de costes compartidos dentro de sus informes de ApptioBI.

Dispositivos clave

- Rastrear claramente los costes compartidos hasta sus fuentes originales
- Mejorar la comprensión y la transparencia del reparto de costes para obtener una mejor visión del negocio

Limitaciones

La fuente de asignación no es compatible con widgets que incluyen simultáneamente dos o más dimensiones empresariales con reparto de costes activo. Intentar esta configuración dará lugar a un error.

Mejoras futuras

Integración de la fuente de asignación en los informes. Estamos trabajando en los paneles de control y se espera que estén disponibles en una próxima versión.

## Cloudability Premium : Credenciales de proveedor: añadir y reclasificar permisos Turbonomic – 12 de mayo de 2025

Hoy hemos lanzado actualizaciones de los permisos requeridos por Cloudability Premium ( Cloudability y Turbonomics) para que funcionen a la perfección entre sí.

Anteriormente, algunos permisos en AWS, Azure y GCP faltaban o debían reclasificarse en los flujos de credenciales de proveedores durante la descarga de los scripts AWS, Azure y GCP. Esta versión ha actualizado estos permisos en los scripts para los flujos de credenciales de proveedor de Cloudability Premium.

Nota: Para disfrutar de una experiencia fluida con Cloudability Premium, se recomienda volver a acreditarse en función de estos permisos. También hemos publicado estos permisos en el Centro de servicios de Azure ( IBM Docs ) para Cloudability Premium en cada integración de proveedor de servicios en la nube.

## Cloudability : Compatibilidad con las versiones más recientes de IBM Cloud Archivos de costes: 30 de abril de 2025

Hoy hemos lanzado actualizaciones para la ingestión de la nueva versión de los archivos de costes de IBM Cloud, lo que permite a los clientes seguir viendo el gasto en IBM Cloud dentro de Cloudability.

Recientemente, IBM Cloud ha actualizado las versiones y los formatos de los archivos de costes. La versión más reciente es:

- Resumen de cuenta de nivel CSV – v1.3
- CSV a nivel de instancia: v1.4

Anteriormente, la versión anterior de los archivos de costes de la nube de IBM, tal y como se ha admitido hasta la fecha, seguirá funcionando como de costumbre, lo que hace que este cambio sea reversible.

No hay cambios en los pasos de acreditación ni en los permisos necesarios para la nube de IBM. Tampoco hay nuevas dimensiones ni adiciones métricas en esta versión.

## Métricas empresariales GA – 22 de abril de 2025

Anunciamos el lanzamiento oficial de Business Metrics con una nueva interfaz de usuario de gestión en Cloudability. Anteriormente solo disponible a través de nuestra API, ahora Business Metrics se puede crear y gestionar directamente a través de la interfaz de usuario, lo que facilita la creación de métricas personalizadas para las necesidades de su negocio.

Dispositivos clave

- Nueva interfaz de usuario: cree y gestione métricas empresariales directamente desde la interfaz de usuario en una pestaña dedicada junto a los mapeos empresariales
- Creación intuitiva de métricas: defina métricas personalizadas mediante una interfaz fácil de usar sin necesidad de conocimientos sobre API
- Generador de declaraciones personalizadas: utilice una práctica función de autocompletado para crear fórmulas (expresión de valor) y aproveche la sofisticada función de coincidencia condicional (expresión de coincidencia)
- Integración perfecta: utilice sus métricas empresariales en las funciones de generación de informes y los paneles de control de Cloudability

Ventajas claves

- Contextualizar el gasto en la nube: vincule los costes de la nube a los KPI específicos del negocio que son importantes para su organización
- Economía unitaria: calcule el coste por cliente, transacción o usuario para comprender mejor la economía de su nube
- Calcular ahorros: Crear fórmulas para calcular tipos de ahorros u otras medidas

Cómo empezar

Ahora se puede acceder a las métricas empresariales desde una pestaña situada junto a «Asignaciones empresariales» en la interfaz de usuario. Puedes crear hasta cinco métricas empresariales por cuenta.

Soporte API

Para los usuarios que prefieren gestionar las reglas mediante programación, nuestra API completa para métricas empresariales sigue siendo totalmente compatible con la documentación disponible a través del punto final de mapeos empresariales. Para obtener más información, consulte nuestro portal de documentación o póngase en contacto con su gestor de éxito del cliente.

## Recomendaciones interregionales en la planificación de la carga de trabajo – 21 de abril de 2025

Con esta versión, puede seleccionar varias regiones preferidas en las secciones «Información común» y «Tipo de recurso», y se mostrarán las recomendaciones para el recurso en diferentes regiones.

Anteriormente, las recomendaciones de Planificación de la carga de trabajo se limitaban únicamente a la región específica seleccionada por el usuario, ya fuera en Información común (si el usuario no había definido el tipo de recurso exacto) o en la región específica seleccionada al definir el tipo de recurso exacto.

## Nueva función estándar: administrador de facturación de Cloudability, 21 de abril de 2025

Hoy hemos introducido una nueva función independiente denominada « Cloudability Billing admin» (Administrador de facturación de Cloudability ) para asignar privilegios de administrador de facturación en.

Anteriormente, para asignar a alguien el permiso de administrador de facturación en una organización, el administrador debía crear una función personalizada con el permiso denominado «OrgCurrencyFeatureAccess ». En adelante, un administrador solo tendría que asignar el rol denominado «Administrador de facturación de Cloudability » para proporcionar a un usuario los privilegios de administrador de facturación. Esta sería una función estándar disponible para todas las organizaciones de clientes en todas las SKU de Cloudability.

## Reparto de costes para métricas empresariales – 4 de abril de 2025

Ahora los clientes pueden distribuir los costes compartidos entre todas sus métricas empresariales cuando utilizan la función de reparto de costes.

Cómo puede ayudarte esta función

Anteriormente, solo se admitían reglas de reparto de costes en las métricas de costes predeterminadas que se admitían. Con esta versión, puede asignar cualquier métrica empresarial monetaria (excepto las métricas empresariales no monetarias) que exista en su entorno para una asignación más precisa de los costes compartidos en diferentes contextos. Esto está disponible para todos los clientes y se puede ver en la página Explorer de reparto de costes y en ApptioBI al seleccionar una métrica sobre la que informar.

## Importación y exportación de reglas de asignación de costes – 4 de abril de 2025

Hoy hemos introducido la funcionalidad de importación y exportación para nuestras reglas de asignación de costes. Ahora, puede cargar sus reglas de asignación de costes sin tener que configurarlas en la interfaz de usuario ni hacerlo mediante programación a través de la API.

Admitimos la importación de archivos de tip CSV es para aquellos clientes que deseen aprovechar la generación masiva de reglas de asignación. La plantilla de la aplicación de control de calidad ( CSV ) se puede encontrar en [la documentación del Centro de ayuda](../product/cost-sharing.html).

Cómo puede ayudarte esta función

Para aquellos que deseen editar y/o añadir reglas, ahora pueden exportar la lista de reglas que tienen actualmente en una dimensión empresarial, lo que les proporcionará la lista de reglas que existen actualmente en el formato necesario.

Además de la importación/exportación para las reglas de asignación de costes, también hemos lanzado la funcionalidad de exportación para los datos que se encuentran en la página Explorador, lo que facilita la exportación de los costes directos y compartidos para un conjunto determinado de reglas de asignación de costes.

## Aviso sobre datos de precios obsoletos en la planificación de la carga de trabajo – 27 de marzo de 2025

Con esta versión, los usuarios verán un banner de notificación para las cargas de trabajo que tengan seis meses o más. Utilice el botón «Regenerar» del banner para volver a generar recomendaciones para aquellas cargas de trabajo con precios actualizados.

## Navegación mejorada para las notificaciones por correo electrónico de anomalías - 26 de marzo de 2025

Hoy hemos introducido mejoras en la experiencia de notificación de anomalías por correo electrónico, diseñadas para simplificar la navegación y proporcionar información más clara a los usuarios.

Anteriormente, al hacer clic en el enlace «Ver anomalía» de las notificaciones por correo electrónico, los usuarios eran redirigidos a una página general de detección de anomalías en la que se mostraban todas las anomalías, en lugar de la específica a la que se hacía referencia en el correo electrónico. Además, en ocasiones las anomalías desaparecían o mostraban detalles incorrectos tras procesar los archivos de costes actualizados, lo que aumentaba la confusión.

Con esta versión, se abordan ambos retos para garantizar un proceso de revisión de anomalías más fluido e intuitivo.

Las siguientes mejoras optimizan la experiencia general al proporcionar actualizaciones claras sobre las anomalías:

- Navegación directa con el enlace «Ver anomalía»: ahora los usuarios son redirigidos directamente a la anomalía específica mencionada en el correo electrónico, con su página de detalles abierta para su revisión inmediata.
- Información actualizada sobre el coste: si el coste de una anomalía cambia debido a la actualización de los archivos de costes, aparecerá una ventana emergente con el coste revisado de la anomalía para mayor claridad.
- Notificación de anomalía desaparecida: si una anomalía desaparece después de procesar los archivos de costes actualizados, aparecerá un mensaje emergente para notificar a los usuarios que la anomalía ya no existe.

## La asignación de costes de contenedores ahora es compatible con Kubernetes Versión 1.32 - 19 de marzo de 2025

La asignación de costes de contenedores ahora es compatible con Kubernetes Versión 1.32 - 19 de marzo de 2025Today, anunciamos la compatibilidad de la asignación de costes de contenedores en Kubernetes versión 1.32 en todos los proveedores. Esta función permite a los clientes obtener información detallada sobre el uso de sus recursos de contenedores y los costes asociados a los clústeres que se ejecutan en Kubernetes 1.32.

La asignación de costes de contenedores ahora es compatible con Kubernetes Versión 1.32 - 19 de marzo de 2025Today, anunciamos la compatibilidad de la asignación de costes de contenedores en Kubernetes versión 1.32 en todos los proveedores. Esta función permite a los clientes obtener información detallada sobre el uso de sus recursos de contenedores y los costes asociados a los clústeres que se ejecutan en Kubernetes 1.32.

## Validaciones sobre el acceso a vistas compartidas - 18 de marzo de 2025

En esta versión, hemos añadido una validación adicional cuando los autores de vistas desean reducir los permisos de una vista compartida a privada o desean eliminar el acceso de los usuarios.

Anteriormente, Cloudability permitía a los autores de vistas cambiar el permiso de las vistas compartidas a privado o eliminar usuarios del acceso a la vista sin ninguna restricción. Como resultado, los usuarios que anteriormente habían establecido la vista compartida como vista predeterminada continuaron recibiendo alertas para esa vista incluso después de que los permisos se cambiaran a privados o se les retirara el acceso. Esto solo ocurría cuando la vista compartida estaba configurada como vista predeterminada.

En adelante, antes de que los autores de vistas reduzcan los permisos de una vista compartida, se les mostrará una lista de usuarios que han establecido la vista compartida como vista predeterminada. De lo contrario, el autor de la vista podría cambiar el permiso de visualización a «Privado» o eliminar al usuario del acceso a la vista sin ninguna restricción.

Más información sobre esta versión

Cambiar la vista predeterminada a la vista predeterminada de la organización para los usuarios afectados:

Dado que Cloudability lo permitió anteriormente, los usuarios que aún tienen las vistas privadas como vista predeterminada siguen recibiendo alertas por correo electrónico. Fijaremos la vista predeterminada para esos usuarios desde el backend y estableceremos su vista predeterminada como la vista predeterminada de la organización. Esto garantizará que los usuarios no tengan una vista predeterminada «desaparecida» o inaccesible.

Además, los usuarios afectados pueden iniciar sesión en Cloudability y cambiar su vista predeterminada de la vista predeterminada de la organización a otra vista a la que tengan acceso. Para configurar tu vista predeterminada:

1. Haga clic en el icono de su perfil y seleccione «Gestionar perfil».
2. En tu página de perfil, selecciona la pestaña Preferencias.
3. Seleccione una vista de la vista de cuenta predeterminada.

## Importación masiva mediante archivo Excel para la planificación de la carga de trabajo - 6 de marzo de 2025

Actualmente, Workload Planning admite la importación masiva mediante archivos JSON. Con esta versión, se admitirá la importación de archivos Excel, lo que facilitará el trabajo a los usuarios de Excel. Al igual que con la función de importación masiva JSON, primero puede descargar la plantilla de Excel y, a continuación, introducir toda la información de sus recursos siguiendo las instrucciones proporcionadas en el archivo de la plantilla. Al volver a cargar este archivo Excel, se crearían todos los recursos según la información proporcionada.

## AWS y Azure Recomendaciones de compromiso mejoradas para la accesibilidad - 4 de marzo de 2025

Hoy, Commitments ha publicado las páginas de recomendaciones de compromiso accesibles AWS y Azure. La versión, aunque principalmente estética, traslada las opciones del encabezado del cajón a un sencillo menú desplegable.

## Filtrado mejorado en la página de detección de anomalías - 26 de febrero de 2025

Hoy hemos introducido nuevas capacidades de filtrado en la función de detección de anomalías, lo que facilita la supervisión, el análisis y la actuación ante anomalías en los costes de forma eficiente.

La detección de anomalías permite a las organizaciones identificar comportamientos inusuales o inesperados en sus gastos. Proporciona un análisis completo e independiente de la nube en todos los servicios para detectar anomalías en los datos de costes, lo que ayuda a mitigar los impactos repentinos en la facturación mediante el envío de alertas y permitiendo a los usuarios tomar medidas.

Cómo puede ayudarte esta función

Anteriormente, solo se podía filtrar por vistas u ordenar columnas. Ahora, puede limitar instantáneamente los resultados a los servicios o cuentas relevantes y filtrar las anomalías en función de umbrales de coste específicos para centrarse en los problemas más importantes.

Estos nuevos filtros proporcionarán:

- Filtrado ampliado: filtre las anomalías por nombre de cuenta, servicio, familia de uso, coste total y gasto inusual para obtener una vista más detallada
- Filtrado basado en umbrales: establezca umbrales específicos para el coste y los gastos inusuales a fin de identificar rápidamente las anomalías de gran impacto
- Compatibilidad con múltiples filtros: combine varios filtros para refinar los resultados y analizar las variaciones de costes con precisión

## Inventario de recursos: compatibilidad con columnas para grupos de cuentas - 21 de febrero de 2025

Con esta versión, los usuarios del inventario de recursos pueden añadir grupos de cuentas como columna en la interfaz de usuario para sus informes de inventario. Este detalle adicional puede resultar útil a la hora de analizar los recursos y clasificarlos de forma relevante para el negocio.

## Alertas basadas en umbrales - Interfaz de usuario de Container Insights - 17 de febrero de 2025

Esta versión introduce la capacidad de alertas basadas en umbrales en la interfaz de usuario de Container Insights, lo que permite a las empresas supervisar y gestionar de forma proactiva los costes de los contenedores en todo su entorno de Kubernetes. Esta función aborda el reto que supone supervisar manualmente los cambios en el gasto en multitud de clústeres y espacios de nombres, lo que facilita a las organizaciones mantener el control sobre los costes de sus contenedores.

Cómo puede ayudarte esta función

- Elimine la supervisión manual con alertas automáticas para los umbrales de coste y utilización
- Ahorre tiempo recibiendo notificaciones inmediatas cuando las métricas superen los límites definidos
- Mejora el control de costes en implementaciones de contenedores a gran escala
- Habilite la optimización proactiva de costes con notificaciones oportunas
- Mejora la visibilidad de las tendencias de gasto en contenedores

Más información sobre esta versión

Esta nueva función de alerta optimiza la gestión de los costes de los contenedores al proporcionar sistemas automatizados de supervisión y notificación, lo que ayuda a las organizaciones a mantener un mejor control sobre sus gastos en contenedores sin necesidad de una supervisión manual constante.

Aquí están los detalles de las características:

- Establezca y gestione umbrales personalizados para métricas de coste y utilización directamente desde los widgets del panel de control de Container Insights 2.0
- Configure notificaciones por correo electrónico para infracciones de umbrales, con soporte para hasta 100 alertas por organización
- Gestión sencilla de alertas en la que todos los usuarios pueden configurar alertas para sí mismos, mientras que los usuarios con privilegios de administrador de Cloudability también pueden asignar alertas a otros usuarios
- Soporte para notificaciones por correo electrónico, con planes de ampliarlo a canales de notificación PagerDuty en el futuro

![Captura de pantalla de alertas basadas en umbrales](../../../../03-media/cloudability-premium/images/threshold-based_alerting4.jpg)

Para obtener instrucciones detalladas sobre cómo configurar alertas y comprender la interfaz de administración de alertas, consulte [Container Insights: Guía de configuración de alertas basadas en umbrales](../product/container-insights-threshold-based-alerting-configuration-guide.html).

## Autocompletar proveedor y región para el almacenamiento al crear un recurso de máquina virtual en la planificación de la carga de trabajo - 14 de febrero de 2025

Hoy hemos lanzado una mejora para rellenar automáticamente el proveedor y la región para el almacenamiento (y hacerlos no editables) al crear un recurso de máquina virtual en la planificación de la carga de trabajo.

Anteriormente, al añadir un recurso de máquina virtual, solían aparecer las opciones Proveedor y Región para el recurso de almacenamiento adjunto. Esto no es lógico, ya que el proveedor y la región del almacenamiento adjunto deben ser los mismos que los de la máquina virtual. Con esta versión, rellenaremos automáticamente los campos «Proveedor» y «Región para almacenamiento» (y los haremos no editables) al crear un recurso de máquina virtual en la planificación de la carga de trabajo

## Coste dinámico de la transferencia de datos para Container Cost Insights - 10 de febrero de 2025

Hoy hemos lanzado una mejora en la asignación de costes de contenedores que incluye los costes dinámicos de transferencia de datos en su metodología de asignación.

Cómo puede ayudarte esta función

Con esta versión, Container Insights y la herramienta de análisis asignarán dinámicamente los costes exactos de transferencia de datos a los proveedores de servicios en la nube que ofrecen partidas de facturación separadas para la transferencia de datos.

En concreto, haremos lo siguiente:

- Evaluar los datos de facturación de cada proveedor de servicios en la nube.
- Asignar los costes de red a los proveedores que admiten partidas de facturación por transferencia de datos (EKS, AKS, GKE ).
- Distribuir los costes de red a agrupaciones de costes individuales de Kubernetes (clúster, espacio de nombres, cargas de trabajo, contenedores, etc.).

Esto significa que ya no utilizaremos la asignación predeterminada del 5 % del coste de las instancias a la red.

Más información sobre esta versión

Para los proveedores que no proporcionan partidas de facturación separadas para la transferencia de datos, seguiremos asignando el 5 % del coste de las instancias a las redes. Esto se debe a la falta de datos específicos de facturación de red vinculados a los ID de instancia, lo que hace imposible asignar con precisión los costes a los nodos o pods correctos.

Nota:

Esta mejora aplicará la nueva lógica a partir de la fecha de lanzamiento. Para los clientes que necesiten datos históricos que reflejen este cambio, póngase en contacto con su equipo de cuentas o con el servicio de asistencia. Aceptaremos solicitudes para rellenar datos históricos hasta el 1 de febrero de 2025, con el fin de alinearlos con la nueva metodología de asignación.

## Información mejorada sobre contenedores con facturación a nivel de recursos de GCP : 10 de febrero de 2025

Hoy hemos anunciado la mejora de nuestra función Container Insights para admitir la facturación a nivel de recursos de GCP dentro de Cloudability. Esta actualización supone un importante avance en la mejora de la visibilidad detallada de los costes para nuestros clientes de GCP.

Cómo puede ayudarte esta función

Anteriormente, las exportaciones de facturación de GCP se limitaban a información a nivel de SKU, a diferencia de AWS y Azure, que proporcionaban datos de facturación más detallados a nivel de recursos. Esta limitación ha restringido la profundidad de los informes disponibles en herramientas como Cloudability. Sin embargo, con la introducción de la facturación por recursos de GCP, nuestros clientes ahora pueden acceder a esta información detallada dentro de la solución Cloudability para contenedores.

Sus principales ventajas son:

Informes de costes mejorados : con esta versión, los clientes que opten por la facturación a nivel de recursos de GCP pueden aprovechar la función Container Insights para obtener información más detallada sobre sus costes. Esto incluye informes detallados sobre las instancias, lo que proporciona una comprensión más clara de su utilización de recursos y los costes asociados.

Mejora en la toma de decisiones : la mayor granularidad de los datos de costes permite a los clientes tomar decisiones más informadas sobre su gasto en la nube y la asignación de recursos.

Como parte de esta versión, presentamos una nueva columna en la página «Información sobre contenedores» denominada «Costes varios ». Esta columna reflejará los costes específicos del clúster y estará disponible inicialmente para GCP, con planes de ampliar la compatibilidad a otros proveedores de servicios en la nube (CSP) en un futuro próximo. Estos costes incluyen gastos adicionales asociados a las aplicaciones en contenedores que van más allá de los nodos, los volúmenes y la transferencia de datos. Incluyen diversos servicios y recursos necesarios para las operaciones de clústeres, lo que proporciona una visión completa de todos los costes relacionados con la ejecución de aplicaciones en contenedores.

Se recomienda a los clientes que utilizan GCP que se inscriban en la facturación por recursos para aprovechar al máximo estas nuevas funciones. Para obtener más ayuda o información, consulte nuestra documentación de asistencia o póngase en contacto con nuestro equipo de atención al cliente.

Nota:

En este momento, teniendo en cuenta nuestras capacidades avanzadas, no tenemos previsto ofrecer soporte para [la asignación de costes nativa de GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/cost-allocations "(se abre en una pestaña o una ventana nueva)") de GCP.

## Automatización de las actualizaciones de SKU de GCP y clasificación mejorada dentro de las dimensiones de informes - 3 de febrero de 2025

Hoy hemos lanzado una actualización en la que hemos pasado de un proceso manual a uno automatizado para actualizar la lista de SKU de GCP. GCP Actualiza la lista de SKU periódicamente y esta mejora automatiza la obtención de la última lista de SKU en Cloudability, lo que mejora la clasificación de SKU.

Cómo puede ayudarte esta función

Antes de esta versión, actualizábamos manualmente la lista de SKU de GCP. Esta mejora elimina la posibilidad de errores humanos, lo que reduce significativamente la cadencia de actualización de las referencias de stock y garantiza la precisión y coherencia de los datos para la elaboración de informes e GCP.

Ahora, los clientes de GCP pueden ver los valores más recientes en varias dimensiones en los informes mientras utilizan GCP como proveedor.

Con esta versión, también activaremos un proceso de reprocesamiento de datos para todos los clientes de GCP, de modo que sus SKU reflejen las últimas actualizaciones.

Nota:

Con esta versión y ejecutando el reprocesamiento, el coste total para un cliente de GCP seguiría siendo el mismo. Sin embargo, podría producirse una reclasificación de algunos valores dentro de las dimensiones/informes que podría afectar a los informes o previsiones si se aplican filtros a los informes.

## Disponibilidad de reparto de costes en Cloudability - 30 de enero de 2025

Hoy anunciamos el lanzamiento de Cost Sharing, una nueva y potente función que aporta capacidades automatizadas y detalladas de asignación de costes a su flujo de trabajo de gestión financiera en la nube.

Características principales

Reglas de asignación flexibles

- Configure múltiples estrategias de asignación, incluyendo división equitativa, ponderación fija, distribución proporcional y asignación basada en telemetría
- Aplicar múltiples reglas de asignación dentro de la misma dimensión empresarial
- Compartir los costes entre equipos, departamentos, unidades de negocio y otras dimensiones

Mayor visibilidad de los costes

- La nueva interfaz Explorer proporciona una confirmación visual de las reglas de asignación
- Realice un seguimiento tanto de los costes directos como de los compartidos mediante informes específicos
- Acceda directamente a los valores asignados posteriormente en el análisis de costes
- Visualice los patrones de distribución de costes en toda su organización

Informes exhaustivos

- Nueva proyección de costes y uso (asignado) de Cloudability en Apptio BI
- El filtrado de vista integrado respeta las jerarquías organizativas
- Soporte para informes de showback y chargeback
- Visualice los patrones de distribución de costes en toda su organización

 Impacto empresarial 

Automatice la última milla : cierre finalmente la brecha del gasto no asignado distribuyendo automáticamente los costes de infraestructura compartida

Reduzca el esfuerzo manual : sustituya las hojas de cálculo propensas a errores por una asignación automatizada basada en reglas

Mejora la precisión : crea reglas de asignación coherentes y repetibles que se adapten al tamaño de tu organización

Habilitar la rendición de cuentas : proporcionar a los equipos visibilidad sobre su perfil de costes completo, incluidos los recursos compartidos

Guía de inicio

La función de reparto de costes ya está disponible para todos los clientes. Siga los pasos que se indican a continuación:

1. Vaya a la pestaña Cost Sharing (Distribución de costes) en la sección Organize (Organizar) de Cloudability (Distribución de costes).
2. Crea tu primera regla de asignación utilizando nuestra configuración guiada.
3. Utilice el Explorador para visualizar sus asignaciones.
4. Genere informes utilizando la nueva proyección Asignada.
5. Para obtener documentación detallada y conocer las prácticas recomendadas, visite nuestro Centro de ayuda.

## Planificación de la carga de trabajo: importación de requisitos de recursos - 24 de enero de 2025

Hoy hemos presentado la planificación de la carga de trabajo: importación de requisitos de recursos. Esta función le permite cargar múltiples recursos y requisitos a través de un archivo JSON para una carga de trabajo determinada. Con esto, puede descargar una plantilla JSON o la lista de los recursos existentes e importarlos para ayudarle a introducir y actualizar los requisitos de manera eficiente.

Cómo puede ayudarte esta función

Anteriormente, los usuarios de Planificación de cargas de trabajo solo podían añadir recursos a sus cargas de trabajo de forma manual, lo que ralentizaba el proceso de creación de cargas de trabajo. Con esta nueva funcionalidad, los usuarios ahora pueden cargar múltiples requisitos a la vez y aprovechar la API de planificación de cargas de trabajo, que pronto se compartirá en el Centro de ayuda.

Nota:

Aunque actualmente Cloudability admite el formato JSON para esta funcionalidad, tenemos previsto admitir formatos adicionales en el futuro basándonos en los comentarios de los clientes.

Cómo importar recursos

Para importar recursos, siga los pasos que se indican a continuación.

1. Crear una carga de trabajo.
2. Selecciona «Añadir recursos ».![Captura de pantalla de WP Add Resources](../../../../03-media/cloudability-premium/images/wp_json1.jpg)
3. Selecciona «Importar» para descargar una plantilla o la lista de los recursos existentes en formato JSON.![Captura de pantalla de los recursos de importación de WP](../../../../03-media/cloudability-premium/images/wp_json2.jpg)
4. Sube el archivo JSON después de realizar los cambios necesarios. El archivo importado sobrescribirá los recursos de carga de trabajo actuales.

   ![WP Subir captura de pantalla de Jason](../../../../03-media/cloudability-premium/images/wp_json3.jpg)

Si la importación se realiza correctamente, tus recursos se actualizarán. En caso de error(es), se podrá descargar un informe de errores. Deberá actualizar su archivo según el informe antes de volver a importar los recursos.

Una vez que se hayan cargado los recursos, podrás ver tus recomendaciones y el resumen de la carga de trabajo en el siguiente paso.

## Posibilidad de añadir un espacio de nombres personalizado al acreditar OCI - 20 de enero de 2025

Hoy hemos lanzado actualizaciones de las credenciales de proveedor de OCI que permiten a los clientes añadir un espacio de nombres personalizado al acreditar OCI en Cloudability. Anteriormente, el espacio de nombres sugerido por defecto en Oracle era «Bling». Esta actualización es aplicable tanto a los clientes nuevos como a los existentes que utilizan OCI en Cloudability.

Pasos para añadir el espacio de nombres personalizado en OCI para nuevos clientes

1. En Cloudability, vaya a Configuración > Credenciales del proveedor.
2. Seleccione el botón Añadir fuente de datos > OCI.
3. El nuevo campo de espacio de nombres personalizado está habilitado para rellenar.
4. Siga los pasos indicados en [Conectar Oracle Cloud](../admin/connect-oracle-cloud.html).

Pasos para añadir el espacio de nombres personalizado en OCI para clientes existentes

1. En Cloudability, vaya a Configuración > Credenciales del proveedor.
2. Seleccione la fuente de datos existente > OCI.
3. Seleccione la entrada de credenciales que desea editar y haga clic en Editar.
4. El nuevo campo de espacio de nombres personalizado está habilitado para actualizarse.
5. Actualice el campo según sea necesario y complete los demás pasos tal y como se indica en [Conectar Oracle Cloud](../admin/connect-oracle-cloud.html).

   ![Añadir credencial OCI Captura de pantalla](../../../../03-media/cloudability-premium/images/oci-credentialing-namespace.jpg)

## ATUM Dimensiones cartográficas - 17 de enero de 2025

Hoy, Cloudability ha lanzado cinco dimensiones de « ATUM » (Comportamiento de los visitantes) en Reporting. Estas dimensiones amplían la taxonomía TBM a Cloudability, lo que permite a los clientes comprender el gasto en la nube a través de esta categorización estandarizada.

Las cinco nuevas dimensiones de ATUM lanzadas son:

1. ATUM Torre : Representa una visión general de TI de las funciones tecnológicas de su organización, proporcionando una amplia categorización de costes. Algunos ejemplos de valores son Red, Plataforma, Usuario final y Aplicación.
2. ATUM Subtorre : ofrece una categorización más detallada dentro de cada torre, por ejemplo, dividiendo la plataforma en middleware y base de datos.
3. ATUM Tipo de servicio : Representa una visión empresarial de alto nivel de su gasto en la nube. Esta es la categorización de nivel superior en servicios con valores tales como Servicios de plataforma, Servicios de entrega y Servicios para el usuario final.
4. ATUM Categoría de servicio : ofrece una clasificación más detallada dentro de cada tipo de servicio, por ejemplo, dividiendo los servicios de entrega en operaciones, seguridad y cumplimiento, y asistencia.
5. ATUM Nombre del servicio : es la categorización más detallada relacionada con los servicios, por ejemplo, desglosar la categoría de servicios de operaciones en gestión de eventos, gestión de servicios de TI e implementación y administración.

Cómo puede ayudarte esta función

Las nuevas dimensiones de « ATUM » (Gastos tecnológicos), alineadas con la taxonomía TBM, proporcionan una categorización más detallada de los costes, lo que permite a las organizaciones comprender su gasto tecnológico en múltiples niveles de granularidad.

Estas dimensiones se integran perfectamente en los informes y paneles de control de Cloudability para todos los clientes.

## Planificación de la carga de trabajo – Azure Apoyo al plan de ahorro – 7 de enero de 2025

Hoy en día, proporcionamos a los usuarios de Planificación de cargas de trabajo estimaciones de costes para recursos informáticos de Azure con la opción de compromiso del Plan de ahorro.

Anteriormente, la planificación de la carga de trabajo solo admitía reservas de tipo « Azure » como tipo de compromiso predeterminado para las nuevas cargas de trabajo. Ahora existe la opción de seleccionar el Plan de Ahorro Azure o las ReservasAzure con un plazo de un año o tres años y obtener estimaciones de costes basadas en los ahorros asociados.
