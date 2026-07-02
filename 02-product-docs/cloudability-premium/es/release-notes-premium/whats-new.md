---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "release-notes-premium"
title: "¿Qué novedades hay en « Cloudability Premium »?"
breadcrumb:
  - "Cloudability Premium"
  - "Novedades en Cloudability"
source_path: "release-notes-premium/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# ¿Qué novedades hay en « Cloudability Premium »?

## Cloudability Premium Compatible con Kubernetes (versión 1.35 ) y OpenShift (versión 4.21 ) - 25 de junio de 2026

Cloudability Premium Ahora es compatible con Kubernetes, 1.35, OpenShift y 4.21. Esta actualización garantiza la compatibilidad continua con las últimas versiones de Kubernetes y OpenShift en los principales proveedores de servicios en la nube, lo que permite a los clientes mantener una visibilidad total de los costes de los contenedores a medida que adoptan nuevas versiones de Kubernetes o OpenShift.

## Cloudability Premium Incorpora las acciones recomendadas de SQL « Azure » a la experiencia de usuario de « Cloudability » para el redimensionamiento avanzado - 25 de junio de 2026

Cloudability ha ampliado los servicios compatibles con el conjunto de funciones de «Advanced Rightsizing» al añadir SQL de « Azure ». Al igual que con los demás servicios compatibles con Advanced Rightsizing, los usuarios con los permisos adecuados pueden consultar las acciones recomendadas, ver las dependencias, los posibles ahorros o inversiones, comprender las políticas que han motivado dicha acción recomendada y mucho más.

Los usuarios también pueden realizar estas acciones directamente desde la interfaz de usuario de Cloudability.

## Cloudability Advanced Containers: experiencia en la asignación de contenedores y activos en el entorno de experiencia de usuario de Cloudability - 24 de junio de 2026

Cloudability ha lanzado una experiencia mejorada de análisis de contenedores al incorporar la potente funcionalidad de asignación de contenedores de « Cloudability Advanced Containers» (con tecnología de Kubecost), que ahora está disponible directamente en la experiencia de « Cloudability » para los clientes que dispongan tanto de « Cloudability » como de « Cloudability Advanced Containers».

Esta versión incluye compatibilidad con el panel de control, la agregación múltiple o única, la configuración de costes compartidos y moreIn. Además, la experiencia de activos de Kubecost también está disponible en Cloudability. Los usuarios pueden utilizar esta función para visualizar y profundizar en activos como «Node», «Disk», «Network», « LoadBalancer, », « ClusterManagement, », etc. De este modo, se integran de forma nativa más contenedores de « Cloudability Advanced Containers» (con tecnología de Kubecost) en « Cloudability », lo que elimina la necesidad de cambiar de aplicación y agiliza los flujos de trabajo.

## Detección de anomalías configurable – 23 de junio de 2026

En la actualidad, la función de detección de anomalías de Cloudability ofrece «dimensiones de anomalías configurables», lo que permite a los administradores seleccionar hasta cuatro etiquetas y dimensiones de mapeo empresarial que resulten más relevantes para su organización. De este modo, se garantiza que los picos de costes se pongan de manifiesto en función de los criterios que importan a sus equipos, en lugar de según los valores predeterminados definidos por el sistema. Las dimensiones de anomalías configurables están limitadas exclusivamente a la configuración de nivel de administrador.

## Cloudability Premium Incorpora las acciones recomendadas de « AWS RDS » a la experiencia de usuario de « Cloudability » para el redimensionamiento avanzado - 5 de junio de 2026

Cloudability ha ampliado los servicios compatibles con el conjunto de funciones de «Advanced Rightsizing» mediante la incorporación de « AWS RDS ». Al igual que con los demás servicios compatibles con Advanced Rightsizing, los usuarios con los permisos adecuados pueden consultar las acciones recomendadas, ver las dependencias, los posibles ahorros o inversiones, comprender las políticas que han motivado dicha acción recomendada y mucho más.

Los usuarios también pueden realizar estas acciones directamente desde la interfaz de usuario de Cloudability.

## Credenciales de proveedor - Permisos detallados de los buckets de GCS – 3 de junio de 2026

Como parte de las mejoras de IAM en GCP, hemos optimizado el script de incorporación de Cloudability GCP para que utilice permisos específicos del depósito Google Cloud Storage en lugar de permisos de almacenamiento más generales a nivel de proyecto.

Con esta actualización, los permisos de « GCP » se trasladan de « CloudabilityRole\_Billing » a una nueva función personalizada a nivel de proyecto, « CloudabilityRole\_Bucket ». Esta función está diseñada para permitir el acceso únicamente a los recursos necesarios del depósito de GCS.

Este cambio mejora la seguridad al limitar el acceso al almacenamiento a determinados buckets, en lugar de permitir un acceso más amplio a todos los buckets del proyecto, de acuerdo con el principio del privilegio mínimo.

Los siguientes permisos se han transferido a la nueva dirección CloudabilityRole\_Bucket.

- storage.buckets.get
- storage.buckets.getIamPolicy
- storage.multipartUploads.abort
- storage.multipartUploads.create
- storage.multipartUploads.list
- storage.multipartUploads.listParts
- storage.objects.create
- storage.objects.delete
- storage.objects.get
- storage.objects.list
- storage.objects.update

Nota: Esta actualización entrará en vigor con la renovación de las credenciales de los clientes actuales. La plantilla más reciente se puede descargar editando la cuenta existente.

## Cloudability Advanced Containers anuncia la compatibilidad con la visualización parcial - 2 de junio de 2026

A partir de hoy, Cloudability Advanced Containers ofrece la función «Partial View Support», que permite a las organizaciones limitar el alcance de la experiencia de Advanced Containers a un subconjunto específico de cuentas en la nube. Esto permite implementaciones multitenant y entornos con control de acceso, en los que los distintos usuarios o equipos solo deben ver los datos de costes relevantes para sus cuentas.

La compatibilidad con vistas parciales se limita **exclusivamente** a las vistas basadas en cuentas. Las vistas deben definirse en función de la pertenencia a una cuenta de Cloud mediante los ID o nombres de cuenta de AccountGroups,, o del proveedor; en esta versión no se admiten otros tipos de vistas, como las basadas en etiquetas o en tags.

En esta versión:

- Ya está disponible **un selector de vistas** en la interfaz de usuario de Advanced Containers, lo que permite a los usuarios seleccionar y cambiar entre las vistas configuradas. La vista seleccionada se guarda en el almacenamiento de « URL » y en el del navegador, lo que facilita añadir a favoritos y compartir vistas específicas.
- Todos los datos de costes —asignaciones, activos y resultados de autocompletado— se filtran automáticamente según las cuentas asociadas a la vista activa.
- La vista activa se mantiene al pasar de la experiencia de contenedores avanzados integrados a la independiente y viceversa.
- Las páginas y los widgets que no admiten el filtrado basado en vistas muestran un mensaje claro en lugar de mostrar datos sin filtrar.

## Cloudability Advanced Containers anuncia la implementación de credenciales compartidas - 2 de junio de 2026

A partir de hoy, Cloudability Advanced Containers (CAC) ofrece «Credenciales compartidas», lo que elimina la necesidad de configurar por separado las integraciones de facturación en la nube dentro de la plataforma Kubecost. Las credenciales de costes en la nube gestionadas en Cloudability ahora son reconocidas automáticamente por Advanced Containers, lo que ofrece a los clientes un único lugar desde el que gestionar sus integraciones en la nube.

En esta versión:

- Las integraciones en la nube configuradas en Cloudability se reflejan automáticamente en Advanced Containers, por lo que no es necesario realizar ninguna configuración duplicada.
- La página de configuración de «Integraciones en la nube» muestra ahora las credenciales obtenidas de Cloudability, con un enlace directo al servicio de credenciales de Cloudability para la gestión de credenciales.
- Los datos sobre los costes de la nube se importan automáticamente a través del canal de datos de la plataforma de análisis de costes de la nube ( Cloudability ), lo que garantiza la precisión del CAC.
- **La API** actualizada de estado de los costes en la nube ofrece información en tiempo real sobre el estado de la importación de datos de costes en la nube por cada cuenta configurada.
- Cuando se utiliza « Cloudability » en «Advanced Containers», los costes de la nube son gestionados por « Cloudability », y se eliminan las secciones duplicadas en la versión independiente de «Advanced Containers», tales como los costes de la nube, los informes de costes de la nube, los presupuestos de costes de la nube y las recopilaciones.

## CFP Intelligent Forecasting BETA - 1 de junio de 2026

Hoy hemos lanzado la función de previsión inteligente para CFP. Esta nueva experiencia ayuda a los equipos a mantener actualizados los planes de CFP, actualizando las líneas de previsión existentes con proyecciones basadas en los últimos datos reales, al tiempo que ofrece a los usuarios una mayor visibilidad y control sobre cómo se generan dichas proyecciones.

La función «Previsión inteligente» de CFP incorpora a los planes de CFP la misma experiencia de previsión basada en modelos que se utiliza en la página «Previsión mejorada». Los usuarios pueden abrir una línea de previsión concreta, consultar los datos históricos reales, ver las proyecciones de varios modelos de previsión, comparar visualmente dichas proyecciones con los valores del plan actual y aplicar el modelo que mejor refleje el gasto futuro previsto.

**Dispositivos clave**

- Revisión interactiva de las previsiones: visualiza un minigráfico integrado que muestra el historial de gastos reales y las previsiones actualizadas directamente en la tabla de líneas de previsión
- Mayor precisión en las previsiones: utiliza el motor de previsión inteligente para evaluar varios modelos y recomendar el que mejor se adapte a cada línea de previsión
- Comparación y control de modelos: comparar los resultados de distintos modelos y aplicar un modelo diferente cuando el modelo recomendado no refleje el gasto futuro previsto
- Comparación entre el plan y los valores: compara visualmente las previsiones generadas por el modelo con los importes del plan actual
- Soporte para la revisión de previsiones: aplicar los resultados de los modelos seleccionados para actualizar los períodos históricos con los datos reales y los períodos futuros con nuevas estimaciones de previsión

**Ámbito**

Esta versión permite realizar nuevas previsiones interactivas para líneas de previsión individuales dentro de los planes CFP. Los usuarios pueden acceder a «Intelligent Forecasting» desde una línea de previsión (haciendo clic en el icono de expansión para mostrar el minigráfico de previsión), consultar los últimos datos reales y las proyecciones, comparar los resultados del modelo recomendado con los de modelos alternativos, comparar los valores proyectados con los del plan actual y aplicar un modelo seleccionado para actualizar los valores de previsión en el plan.

**Próximamente**

En la versión GA, CFP Intelligent Forecasting incorporará la posibilidad de guardar las selecciones de modelos y realizar nuevas previsiones en bloque, lo que facilitará a los usuarios la actualización de las previsiones en función de los últimos datos reales, como parte de un ciclo de actualización mensual habitual.

**Disponibilidad y habilitación**

El servicio «CFP Intelligent Forecasting» está disponible para todos los clientes de CFP. La función «Previsión inteligente» requiere la funcionalidad «Actualizar datos reales», por lo que es necesario habilitar esta última antes de poder utilizar la «Previsión inteligente».

Tanto la opción «Actualizar datos reales» como la de «Previsión inteligente» se pueden activar desde la pestaña «Avanzado» de la página «Preferencias de planificación», situada en «Configuración» en el panel de navegación izquierdo de Cloudability. La función «Previsión inteligente» se activa automáticamente para los clientes que hubieran activado la opción «Actualizar datos reales» durante el periodo de implantación inicial.

Más información sobre [la previsión inteligente](../product/efp-forecast.html)

## Cloudability Commitments anuncia la compatibilidad con « AWS » para la página de resumen del Gestor de compromisos mejorado – 1 de junio de 2026

El lunes 1 de junio, el equipo de Compromisos de Cloudability publicó la página de resumen del Gestor de compromisos mejorado. Esta nueva página sustituye al «Commitment Manager» actual, ya que ofrece las mismas funciones y se ha mejorado para que funcione a la perfección como página de inicio de todas las funciones de «Commitment» de Cloudability. Con esta versión, la nueva página de resumen, denominada simplemente *«Commitment Manager»* en el menú de navegación de la izquierda, es compatible con los servicios de AWS en los que ofrecemos un tipo de compromiso: All Compute, RDS, Redshift, Elasticache y OpenSearch.

***Nuevas funciones***

- · El aspecto del gráfico es similar al del gráfico de la página de detalles de la recomendación. Este gráfico se ha mejorado recientemente con la versión [« AWS : Support for Commitment Management» ( 2.0](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0 "(se abre en una pestaña o una ventana nueva)") ).
- Indicadores clave de rendimiento (KPI) mejorados, entre los que se incluyen la tasa de ahorro y la cobertura. Los indicadores clave de rendimiento (KPI) de la página de resumen son los mismos que se muestran en «Cartera» y «Recomendaciones».
- Selección simplificada del periodo de análisis.
- La granularidad de los KPI admite los niveles de semana, mes y total.
- Botón de comparación de KPI.
- Tipos de costes admitidos en Chart: coste real, equivalente bajo demanda (ODE).

***Funcionalidad de paridad***

- Nivel de detalle de los informes diarios.
- Vistas de costes y ahorros: El botón de alternancia «Costes/Ahorros» ya no está disponible. Esta información se presenta ahora en un único gráfico.
- Alternar recomendaciones: se ha trasladado a la barra de encabezado, debajo del menú desplegable «Tipo de recomendación».
- Enlaces de navegación a las páginas «Portafolio» y «Recomendaciones».

***Funcionalidad obsoleta***

- Selección del informe diario: El periodo de referencia de los datos que aparecen en la página se basa ahora en meses. Esto simplifica la página y la adapta al uso principal, que es ofrecer una visión general de alto nivel de tu rendimiento y tus oportunidades.
- Desglose de los gráficos por servicio: Se sigue ofreciendo la posibilidad de generar informes agregados para todos los servicios, pero los costes ya no se desglosan explícitamente por servicio.
- Selección de criterios de recomendación: La recomendación asume ahora la recomendación óptima.
- La página anterior de «Commitment Manager» ha quedado obsoleta y se ha sustituido por esta nueva página. La página anterior ya no está disponible y no se puede recuperar.

Para obtener más información, consulta nuestra documentación de ayuda en [el apartado «Descripción general del Gestor de compromisos para alinear a la organización con la estrategia de compromiso](../product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html) ».

## Cloudability Governance incorpora compatibilidad con « Azure » (versión preliminar pública) – 29 de mayo de 2026

Hoy nos complace anunciar la compatibilidad de « Azure » con « Cloudability Governance».

Los clientes que operan, ya sea de forma predominante o parcial, en una nub Microsoft Azure, ya pueden disfrutar de las prestaciones de « Cloudability Governance».

Esta ampliación permite a las empresas con un uso intensivo de « Azure » aprovechar por fin las funciones de gestión automatizada y proactiva, así como de prevención de costes, de « Cloudability Governance», en lugar de depender exclusivamente de herramientas reactivas posteriores a la facturación.

## Azure Acreditación MCA: asignación automática del rol de «Lector de cuentas de facturación» – 25 de mayo de 2026

Esta versión automatiza la asignación del rol «Billing Account Reader» al sujeto de servicio « Cloudability » para las cuentas MCA de Azure, lo que ayuda a los clientes a darse de alta más rápidamente.

Antes de esta versión, los clientes tenían que asignar este rol manualmente.

## Mejoras en la experiencia del usuario en el ajuste de la capacidad de « Cloudability » - 28 de mayo de 2026

Hoy lanzamos varias mejoras en la experiencia de usuario de «Rightsizing» en Cloudability, que hacen que la navegación y el uso de las funciones de Rightsizing sean más eficientes y fáciles de usar. La lista de mejoras incluye:

- **La selección de servicios ha pasado de las pestañas al menú**. A medida que se añaden más servicios a Rightsizing, hemos sustituido el selector de servicios basado en pestañas por un menú más eficiente, similar al de la página «Compromisos».
- **Se ha eliminado la etiqueta duplicada del tipo de servicio del panel de control**. Ahora, el tipo de servicio solo se muestra en el selector de servicios, lo que elimina la información redundante y libera un valioso espacio en pantalla.
- **La «Base de coste» ha pasado de ser un conjunto de botones de opción a**. El selector de base de coste se ha convertido en un menú, similar a la interfaz del Gestor de compromisos, lo que ofrece una experiencia de usuario más coherente. En el caso de los servicios que solo admiten una única base de coste, este campo es de solo lectura.
- **La línea de tiempo ha pasado a llamarse «Período de análisis» y cuenta con un selector**. El selector de intervalo de tiempo ha pasado a denominarse «Período de análisis» para ajustarse a la terminología utilizada en Commitment Manager. El selector ha pasado de ser botones de opción a un menú para ahorrar espacio en la pantalla. En el caso de los servicios que solo admiten un único periodo de análisis, este campo es de solo lectura.

## Actualizaciones de la base de coste de las recomendaciones avanzadas en Cloudability Premium - 28 de mayo de 2026

Hoy, Cloudability Premium ha actualizado la terminología relativa a la base de coste en las páginas de «Rightsizing» para reflejar mejor cómo se calculan las recomendaciones avanzadas y para distinguir claramente entre la metodología de la base de coste de las recomendaciones avanzadas y la de las recomendaciones básicas.

Hasta hoy, tanto en las recomendaciones avanzadas como en las básicas, las opciones de base de coste disponibles figuraban como «Efectiva» y «Bajo demanda», pero esas opciones tenían un significado diferente en las recomendaciones básicas y en las avanzadas.

Las bases de coste de las recomendaciones avanzadas se han actualizado a «Ajustado» y «Ajustado amortizado» para reflejar mejor los cálculos subyacentes de los costes de los recursos de origen y de destino.

**Ajustado** : se calcula utilizando el coste de caja de un recurso determinado, incluyendo sus tarifas privadas cuando estén disponibles (en cuyo caso el coste de compromiso se considera igual a 0 $), y se compara con el coste de caja previsto para el futuro y la cobertura esperada de los compromisos aplicados a este recurso durante el periodo de referencia. Este cálculo se denomina «On Demand» en la documentación de « Cloudability Premium : Workload Optimization UI» y « Turbonomic ».

**Amortizado ajustado** : se calcula utilizando el coste amortizado de un recurso determinado y los compromisos asociados que se le aplicaron durante el período de referencia (incluidas las tarifas privadas, cuando estén disponibles). El coste futuro del Estado se calcula en función de cómo se prevé que se apliquen esos compromisos, qué partes se prevé que sigan estando disponibles bajo demanda y qué compromiso (si lo hay) queda libre para aplicarse en otro ámbito. Este cálculo se denomina «Efectivo» en la documentación de Cloudability Premium : Interfaz de usuario de optimización de la carga de trabajo y Turbonomic.

## Azure Acreditación MCA: asignación automática del rol de «Lector de cuentas de facturación» – 25 de mayo de 2026

Esta versión automatiza la asignación del rol «Billing Account Reader» al sujeto de servicio « Cloudability » para las cuentas MCA de Azure, lo que ayuda a los clientes a darse de alta más rápidamente.

Antes de esta versión, los clientes tenían que asignar este rol manualmente.

## Métricas calculadas en paneles e informes – 21 de mayo de 2026

Nos complace presentar las métricas calculadas para los paneles e informes de « Cloudability ». Esta potente función le permite definir modelos económicos por unidad y KPI sofisticados desde un centro centralizado, lo que ofrece una mayor visibilidad del gasto en la nube y de la eficiencia operativa mediante métricas personalizadas y reutilizables.

Gestión centralizada de métricas: Crea, edita y elimina métricas calculadas desde un único centro de control dentro del área de producto «Business Mappings». Defina las métricas una sola vez y reutilícelas en todos los paneles e informes, eliminando así las configuraciones redundantes y garantizando la coherencia.

Creación flexible de fórmulas: Crea fórmulas personalizadas utilizando constantes numéricas, operadores aritméticos básicos y métricas existentes. La compatibilidad con fórmulas flexibles permite realizar análisis sofisticados adaptados a las necesidades de su empresa, incluyendo indicadores económicos por unidad, como el coste por recurso o el coste por clúster.

Permisos basados en roles: Los controles de acceso mejorados garantizan una gestión adecuada mediante tres niveles de permisos: Administrador (acceso completo para crear, editar y eliminar todas las métricas), Edición (crear y modificar las propias métricas) y Visualización (acceso de solo lectura).

## Cohesión terminológica en las pantallas de credenciales de proveedores – 19 de mayo de 2026

Hoy hemos actualizado la terminología en todas las pantallas de credenciales de proveedores para garantizar la coherencia.

- Se ha cambiado el nombre de la sección «Optimización de recursos» por «Ajuste avanzado de recursos»
- Se ha actualizado la sección de información para que incluya de forma sistemática «Acciones automatizadas» y «Ajuste avanzado de recursos»
- Se ha cambiado el nombre de los botones de permisión: «Solo lectura» y «Automatizar acciones»

  Nota: Esto no afecta al funcionamiento actual. Es una actualización que solo afecta a la experiencia de usuario.

## Cloudability Commitments incorpora compatibilidad con la cartera de Microsoft Foundry Provisioned Throughput – 19 de mayo de 2026

Hoy hemos incorporado la compatibilidad con [Microsoft Foundry Provisioned Throughput (PTU)](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/microsoft-foundry "(se abre en una pestaña o una ventana nueva)"). El [decimotercer](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(se abre en una pestaña o una ventana nueva)") tipo de compromiso de « Azure » compatible: las PTU de Foundry ofrecen un descuento en los servicios de IA a cambio de un compromiso de uso por horas de un mes o un año. Este tipo de compromiso se clasifica como un compromiso basado en recursos y, como tal, requiere la selección de determinados parámetros de uso: región, tipo de implementación y opción de pago. En esta versión, solo la cartera admite este tipo de compromiso. En el futuro, tendremos en cuenta las recomendaciones sobre la construcción.

Para más información, consulte la documentación de ayuda sobre gestión de compromisos. (editado)

## Importación y exportación de definiciones de mapeo empresarial a través de la interfaz de usuario – 15 de mayo de 2026

- Exportación: Ahora los usuarios pueden exportar definiciones individuales de Business Mapping directamente desde la interfaz de usuario a un archivo JSON, lo que facilita compartir o realizar copias de seguridad de la configuración de BM.
- Importación: Ahora los usuarios también pueden importar definiciones de BM a un BM ya existente. El archivo JSON importado rellena la interfaz de usuario con nuevos valores, lo que permite a los usuarios revisar y validar los cambios.

Esta función permite a los clientes gestionar sus definiciones de BM íntegramente a través de la interfaz de usuario, sin necesidad de acceder a la API, lo que agiliza el proceso de importación y exportación de configuraciones de BM.

## Cloudability Commitments anuncia la compatibilidad con « AWS » para la gestión de compromisos 2.0 – 13 de mayo de 2026

Hoy, el equipo de Compromisos de Cloudability ha lanzado la compatibilidad con AWS para la gestión de compromisos 2.0. Con esta versión, los usuarios verán que la «Cartera de compromisos» y las «Recomendaciones» se han transformado para dar soporte a la funcionalidad básica de « 2.0 », que incluye, entre otras cosas:

- Indicadores clave de rendimiento (KPI) mejorados, entre los que se incluyen la tasa de ahorro y la cobertura
- Agrupar «todas» las páginas cuando sea pertinente en toda la cartera
- Compatibilidad con el modal de cobertura
- Página de detalles de las recomendaciones renovada
- Función de ajuste personalizado de las recomendaciones

Esta versión ayuda a los usuarios a elaborar un análisis de viabilidad para una estrategia de compromiso acorde con las mejores prácticas. En concreto, los usuarios ya pueden personalizar las recomendaciones de « Cloudability » para que incluyan análisis de sensibilidad tanto para la estrategia a largo plazo como para la próxima compra incremental. Esto permite a los usuarios combinar tipos de compromiso basados en plazos, en el gasto apalancado y en los recursos, y ajustar los niveles al alza o a la baja en función de las previsiones de uso futuro.

Además, esta funcionalidad empieza a vincular las páginas de compromisos personalizadas con los informes, lo que proporciona la transparencia que nuestros clientes necesitan para aprovechar nuestra aplicación en casos de uso relacionados con la gestión de compromisos, los reembolsos y la rendición de cuentas.

**¿Cómo puedo obtener ayuda?**

Hemos reescrito nuestro contenido de ayuda para adaptarlo a estas importantes mejoras. El contenido comienza con [«Optimización de costes en la nube» en Cloudability](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=optimize-cloud-cost-optimization-in-cloudability "(se abre en una pestaña o una ventana nueva)"). Desde el punto de vista táctico, [las secciones «Utilizar la cartera de compromisos para comprender el rendimiento histórico](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=management-using-commitment-portfolio-understand-historical-performance "(se abre en una pestaña o una ventana nueva)") » y [«Utilizar las recomendaciones de compromiso para analizar oportunidades de ahorro»](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=management-using-commitment-recommendations-analyze-savings-opportunities "(se abre en una pestaña o una ventana nueva)") ofrecen indicaciones sobre cómo sacar partido a las nuevas páginas de cartera y recomendaciones.

**¿Y ahora qué?**

Esta funcionalidad ya se había implementado para los compromisos de « GCP » a finales de 2024. Ahora nos centraremos en incorporar funciones de paridad para Azure.

## Cloudability Commitments anuncia mejoras en las recomendaciones de compromiso de « AWS » – 13 de mayo de 2026

Hoy, el equipo de « Cloudability » ha presentado importantes mejoras en nuestras recomendaciones sobre compromisos de « AWS ». Esta versión puede considerarse una versión secundaria de [Cloudability Commitments anuncia AWS la compatibilidad con la gestión de compromisos 2.0 – 13 de mayo de 2026](#whats-new__cldy-commit-mgnmt2.0). Lo destacamos por separado para llamar la atención sobre los matices que rodean las mejoras en las recomendaciones. Los usuarios pueden esperar las siguientes mejoras:

*Introducción del enfoque de cobertura basado en los costes* : con la incorporación del indicador clave de rendimiento (KPI) de cobertura a AWS, estamos utilizando datos de costes reales en lugar de horas de uso asignadas. Esto diferirá del indicador de tasa de cobertura reservada que figura en los informes, ya que en este caso la cobertura se calcula en función de las horas de uso. Tanto en la cartera de compromisos como en las recomendaciones, la cobertura viene determinada directamente por el coste; concretamente, la parte del gasto equivalente a servicios bajo demanda que estaba cubierta por un compromiso en un momento dado period.This hace que la cobertura resulte más relevante a la hora de tomar decisiones financieras. Las horas de uso son difíciles de comparar entre los distintos tipos de instancias y no se corresponden directamente con lo que gastas o ahorras. La cobertura basada en los costes sí lo hace. Gracias a que « AWS Cost Explorer» calcula la cobertura de las instancias reservadas en horas de uso, el enfoque basado en los costes de « Cloudability » te ofrece una visión más precisa desde el punto de vista financiero, que refleja el impacto real en dólares de tus compromisos, en lugar de un valor aproximado basado en horas que puede variar significativamente entre las distintas familias y tamaños de instancias. En lo que respecta a los planes de ahorro, creemos que ahora nos ajustamos al método de cálculo de la cobertura que utiliza de forma nativa AWS.

*Recomendación basada en los compromisos existentes a lo largo del periodo de análisis*. Anteriormente, las «Recomendaciones de compromiso» solo tenían en cuenta la cobertura de los compromisos *actuales* a la hora de generar nuestras recomendaciones. Ahora utilizaremos la cobertura que haya habido durante el periodo de análisis seleccionado. Aunque esto tiene el inconveniente de que podría ser menos preciso —por ejemplo, si se adquirió o venció un compromiso durante el periodo de análisis—, ahora simplifica el proceso de elaboración de la recomendación. Al acceder a la página de detalles de la recomendación, ahora verás un gráfico que muestra únicamente el coste. La forma correcta de utilizar esta función ahora es examinar el uso durante el periodo de análisis y volver a seleccionar el periodo de análisis que mejor represente el futuro. En muchos casos, esto obligaría a los usuarios a reducir el periodo de análisis a solo una o dos semanas, en lugar del mes completo predeterminado. Se prevé que este cambio tenga un impacto mínimo en los importes recomendados a los clientes tras su implementación. Creemos que se trata de una mejora, ya que el gráfico ahora refleja con precisión lo que habría ocurrido «si hubiera mantenido esta recomendación durante el periodo de análisis seleccionado»

*Incluir/excluir planes de ahorro existentes en las recomendaciones de instancias reservadas* : ahora ofrecemos la posibilidad de ignorar los planes de ahorro existentes en las recomendaciones de instancias reservadas de EC2. Debido a la naturaleza fungible de los planes de ahorro, « AWS » suele asignarlos de forma variable. En consecuencia, las horas en las que los planes de ahorro se asignaban a una combinación concreta de familia de instancias, región, cuenta y sistema operativo provocaban una variabilidad significativa en nuestras recomendaciones, debido a pequeñas diferencias en el periodo de análisis. Esta función te permite ignorar los planes de ahorro, ya que, si existiera una instancia reservada, el uso variable podría aplicarse en otro lugar. Esto ofrece a nuestros usuarios la flexibilidad necesaria para seguir beneficiándose de la mayor tasa de ahorro por compromiso que ofrecen las instancias reservadas.

*Incluir/Excluir cuentas vinculadas* : ahora ofrecemos la posibilidad de generar recomendaciones individuales para cada cuenta vinculada de un mismo pagador. Cuando la función de compartir está activada, seguimos agrupando todas las cuentas vinculadas a una cuenta de pagador al analizar el uso. Esto muestra cómo AWS distribuye los RIs y ofrece el mayor ahorro. La diferencia radica en que, cuando la función de compartir está desactivada y el usuario selecciona una cuenta de pagador, ahora verá una recomendación para cada cuenta, en lugar de solo una recomendación para el uso de la cuenta de pagador.

**¿Cómo puedo obtener ayuda?**

Hemos reescrito nuestro contenido de ayuda para adaptarlo a estas mejoras. El contenido comienza con [«Optimización de costes en la nube» en Cloudability](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=optimize-cloud-cost-optimization-in-cloudability "(se abre en una pestaña o una ventana nueva)").

## Pestañas del panel de control en los paneles de control de Cloudability – 12 de mayo de 2026

Hoy lanzamos una mejora en los paneles de control de Cloudability : incorporamos la compatibilidad con **pestañas en los paneles,** lo que permite a nuestros clientes organizar mejor el contenido de los paneles en varias pestañas dentro de un mismo panel. Esto permite a los usuarios agrupar los widgets por proveedor, por equipo, por unidad de negocio o de cualquier otra forma que haga que los paneles de control resulten más útiles y se adapten mejor a las necesidades específicas de cada cliente.

- Los usuarios pueden arrastrar y soltar las pestañas para cambiar su orden
- Los usuarios pueden duplicar pestañas completas para copiarlas entre paneles
- Los usuarios pueden arrastrar y soltar un widget para moverlo a otra pestaña
- Al copiar widgets, los usuarios pueden elegir en qué pestaña desean copiarlos

## Cloudability Commitments anuncia la compatibilidad con las preferencias de columnas en toda la plataforma – 12 de mayo de 2026

Hoy, el equipo de « Cloudability » ha introducido una pequeña mejora en su tabla. En cuanto a las tablas de toda la cartera y las recomendaciones de AWS y GCP, ahora guardamos la selección de columnas «Mostrar/Ocultar» en el almacenamiento local de tu dispositivo. De este modo, la selección de columnas se mantendrá entre sesiones. Cabe destacar que cada página de compromisos tiene un conjunto diferente de columnas y un orden distinto guardados como predeterminados. Para obtener más información, consulta la [sección «Conceptos básicos de la tabla de compromisos»](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-commitment-table-basics "(se abre en una pestaña o una ventana nueva)") en nuestro Centro de ayuda.

## Mejoras en la tabla de detalles de las recomendaciones de compromiso – 11 de mayo de 2026

Hoy, el equipo de « Cloudability » anuncia oficialmente una serie de mejoras en la página de detalles de las recomendaciones. Esto forma parte oficialmente de la versión [« 2.0 » de Commitment Management](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0 "(se abre en una pestaña o una ventana nueva)"). Le dedico una entrada independiente aquí porque este cambio afecta tanto a AWS como a GCP.

***Selección de la ecuación diferencial ordinaria (EDO) por defecto*** : Se ha añadido un botón de activación/desactivación para la selección de la EDO por defecto (equivalente a «bajo demanda») en la página «Detalles de la recomendación», lo que permite a los usuarios ignorar la EDO por defecto para obtener un gráfico de costes más sencillo. Al desactivar el interruptor, se reduce el eje Y y se hace más hincapié en el coste.

***Función de desglose de compromisos*** : ahora los usuarios pueden desglosar los compromisos desde la página de detalles de la recomendación, y ver los compromisos actuales ya sea en forma de suma total o desglosados individualmente. Esto resulta útil para analizar una recomendación cuyo ámbito de aplicación podría estar cubierto por un tipo de compromiso diferente.

***Información sobre herramientas del gráfico actualizada*** : La información sobre herramientas del gráfico se ha rediseñado para permitir el desplazamiento y presentar los totales de costes en un formato similar al de un estado financiero, mostrando los datos por hora junto con los totales resumidos para mejorar la legibilidad y facilitar el análisis de un solo vistazo.

***Se ha eliminado «Coste total» del menú desplegable de tipos de gráficos*** : «Coste total» ya no está disponible como tipo de gráfico, ya que ahora se puede acceder a los totales a través de la información sobre herramientas actualizada. Se han actualizado los controles de alternancia en consecuencia, teniendo en cuenta los comentarios de los usuarios, que señalaban que la selección anterior resultaba confusa.

***Cambio de nombre del tipo de recomendación*** : el tipo de recomendación «Personalizada» de nivel superior pasa a llamarse «Modificada», y el tipo de recomendación «Ajustada» pasa a llamarse «Personalizada». Estos cambios resuelven los conflictos de nombres provocados por el cambio de nombre de la lista de costes de adquisición. Para obtener más información, consulta «[Uso de las recomendaciones de compromiso para analizar oportunidades de ahorro](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=management-using-commitment-recommendations-analyze-savings-opportunities "(se abre en una pestaña o una ventana nueva)") ».

## Cloudability GCP : Anuncio de diversas mejoras menores en los compromisos – 11 de mayo de 2026

Hoy, el equipo de « Cloudability » anuncia oficialmente una serie de mejoras en nuestra compatibilidad con « GCP ». Son los siguientes:

- Selección mejorada de cuentas para un gran número de cuentas en la cartera y las recomendaciones: los clientes pueden tener miles de cuentas. Ahora agrupamos las cuentas vinculadas en la cuenta del pagador. Esto resulta especialmente útil en el caso de los compromisos, ya que normalmente se adquieren o se comparten a nivel de la cuenta del pagador. Los usuarios ya no tienen que desplazarse sin fin por la pantalla ni saber exactamente qué cuenta buscar.
- Coste de la cartera durante el periodo de análisis: Ahora mostramos el coste total correspondiente al periodo de análisis, además del coste restante. Es posible que los clientes quieran comparar esta cifra con la que aparece en los informes. Ya no es necesario añadir esta columna manualmente ni exportar la tabla a un archivo CSV para hacer la suma.
- Tasas de ahorro de la cartera (PSR) y de compromiso (CSR) en la cartera: La CSR y la PSR son claramente diferentes. El CSR es la tasa de ahorro ponderada de tus compromisos a lo largo del periodo de análisis. El PSR es la tasa de ahorro de tu cartera. CSR = Ahorros / Equivalente bajo demanda del coste de compromiso. PSR = Ahorros / Gasto comprometible. Ver estos dos valores uno al lado del otro ayuda a distinguir entre ambos KPI. Para obtener más información, consulta [los indicadores clave de rendimiento del compromiso](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-commitment-key-performance-indicators "(se abre en una pestaña o una ventana nueva)").

## Cloudability Incorpora compatibilidad con las recomendaciones de niveles de « Azure Blob Storage » – 11 de mayo de 2026

Hoy hemos incorporado la compatibilidad con las recomendaciones de niveles de « Azure Blob Storage ». Cloudability Ahora los usuarios pueden optimizar los costes de almacenamiento de Azure gracias a unas recomendaciones inteligentes sobre la configuración de los niveles de acceso a los contenedores, que incluyen las opciones «Hot», «Cool», «Cold», «Archive» y «Smart Tier».

Para cada contenedor, Cloudability analiza el uso del almacenamiento, los patrones de acceso y los costes operativos con el fin de detectar posibles errores de configuración de los niveles de almacenamiento. Las recomendaciones calculan los costes mensuales totales en todos los niveles disponibles, incluyendo las tasas por eliminación anticipada y los costes de recuperación, con el fin de sugerir la configuración óptima que minimice los costes sin dejar de cumplir los requisitos de rendimiento.

Estas recomendaciones siguen el mismo formato que las recomendaciones de optimización de niveles ya existentes en AWS S3 y Google Cloud Storage, y pueden consultarse en la página Rightsizing Explorer. Esta función es compatible tanto con las transiciones tradicionales entre niveles como con la optimización automática de Smart Tier de Azure, lo que ofrece flexibilidad para diferentes estrategias de gestión del almacenamiento.

Para obtener más información, consulte « [Azure Blob Storage : rightsizing](../product/rightsizing-for-azure-blob-storage.html) ».

Nota:

Los clientes deben conceder permisos a 'Microsoft.Storage/storageAccounts/read' para que todos los elementos de esta función funcionen correctamente.

## Previsiones mejoradas - 4 de mayo de 2026

Hemos lanzado la página «**Previsión mejorada** », una nueva y mejorada experiencia de previsión en la nube para Cloudability.

La página «Previsión mejorada» supone una mejora significativa con respecto a la versión anterior de «Previsión», ya que ofrece las mismas funciones básicas de previsión, pero con mucha más flexibilidad, transparencia y control. Los usuarios pueden seleccionar sus propios factores de previsión, analizar el detalle completo de las partidas de la previsión, beneficiarse de una previsión inteligente más precisa, comparar visualmente los resultados de los modelos y vincular las previsiones a los flujos de trabajo presupuestarios.

**Funcionalidades nuevas y mejoradas (en comparación con la página de previsiones anterior)**

- Factores de gasto seleccionables por el usuario: elige tus propias dimensiones, en lugar de los factores fijos que utiliza la página de previsiones anterior
- Detalle completo de las partidas de la previsión: revisa todas las partidas de la previsión, no solo las 20 principales
- Mayor precisión en las previsiones: utiliza el motor de previsión inteligente para evaluar varios modelos y seleccionar automáticamente el más adecuado, en lugar de basarse en un único modelo fijo
- Comparación y control interactivos de modelos: revisa los detalles de los modelos, compara visualmente los resultados de diferentes modelos y aplica un modelo distinto cuando sea necesario
- Análisis detallado de tipo «Pivot»: agrupa, resume, ordena y filtra los detalles de las partidas de las previsiones directamente en la tabla

[Más información sobre la previsión mejorada](../product/efp-forecast.html)

## Registro y supervisión en la planificación de la carga de trabajo - 29 de abril de 2026

Esta versión introduce compatibilidad con los servicios de registro y supervisión en AWS, Azure y OCI. En « GCP », la función de planificación de cargas de trabajo solo admite actualmente el registro. Esto es similar a cómo los usuarios ya pueden crear presupuestos para servicios como máquinas virtuales y bases de datos.

Los usuarios pueden seleccionar el servicio adecuado en el menú desplegable «Tipo de servicio»: «Registro y supervisión» para AWS, Azure y OCI, y «Registro» para GCP. Una vez introducida la capacidad necesaria y, si se desea, definida su configuración específica, la herramienta de planificación de la carga de trabajo generará opciones de precios adaptadas a sus necesidades.

## Cambio de nombre del « Turbonomic » en FrontDoor a « Cloudability Premium - Optimización de la carga de trabajo» - 29 de abril de 2026

Cloudability Premium Los usuarios notarán un cambio en su entorno de FD, ya que vamos a cambiar el nombre del enlace « Turbonomic » por «**Cloudability Premium - Optimización de la carga de trabajo».** Este cambio se ha realizado para evitar confusiones sobre la propiedad de los productos y, junto con este cambio en los enlaces, también hemos introducido modificaciones en la interfaz de usuario del motor de ajuste de capacidad de Turbonomic.

## Mejoras en la experiencia del usuario en los paneles de control de Cloudability - 28 de abril de 2026

Hoy lanzamos varias mejoras en la experiencia de usuario de los paneles de Cloudability que hacen que ver y crear paneles sea más fácil y más intuitivo. La lista de mejoras incluye:

- **Mantener la configuración de los filtros de los widgets** al cambiar de tipo de widget. Al cambiar el tipo de widget (por ejemplo, de un gráfico a una tabla), la interfaz conservará ahora la configuración de los filtros, de modo que no sea necesario volver a configurarlos por separado para cada tipo de widget.
- **La fila «Otros» de los widgets de tabla se muestra ahora separada del resto de valores** para distinguirla claramente de los resultados reales.
- **Ahora es posible configurar los filtros basados en la fecha mediante un calendario de fácil manejo**. Con este cambio, los usuarios ya no tendrán que introducir manualmente los valores de los filtros de formato de fecha. En su lugar, los usuarios podrán seleccionar una fecha mediante un selector de calendario integrado.
- **Copiar y pegar filtros** desde/hacia el portapapeles. Ahora los usuarios podrán transferir fácilmente una configuración de filtros entre diferentes widgets y guardar un conjunto de filtros para volver a utilizarlo más adelante.
- **Exportar el gráfico como imagen.png.** Ahora los gráficos se pueden exportar y guardar como imágenes en formato PNG.
- **Buscar y filtrar en un widget de tabla**. Ahora todos los widgets de tabla se pueden filtrar mediante un único campo de búsqueda de texto que se aplica a todas las columnas visibles.
- **Exportar como PDF**. Ahora es posible exportar todo el panel de control en formato PDF para facilitar la colaboración con otros usuarios.

## Suscríbete a los informes con el intervalo de fechas de comparación: 28 de abril de 2026

Esta versión incluye una mejora en la funcionalidad de suscripción a los informes de Cloudability. Con este cambio, los usuarios podrán suscribirse a informes que utilicen la función «Comparar fechas», del mismo modo que actualmente pueden suscribirse a informes con una sola fecha.

## Cloudability El COIN Explorer del panel de optimización admite el formato condicional - 20 de abril de 2026

Cloudability ha añadido compatibilidad con el formato condicional en el COIN Explorer, que se encuentra en el panel de control de optimización. En la sección «Preferencias de ajuste de tamaño», los usuarios pueden establecer umbrales para el formato condicional de la puntuación COIN. Los ajustes incluyen un umbral verde/amarillo, así como un umbral amarillo/rojo.

El COIN (Índice de Optimización de Costes) ofrece a las organizaciones una métrica estandarizada para analizar las oportunidades de optimización en el contexto del gasto en esa área de su negocio, de modo que sepan dónde centrar sus esfuerzos y establecer prioridades. Muchas organizaciones llegan incluso a utilizarlo como una tabla de clasificación para comparar la eficiencia de los equipos de toda la organización.

Junto con esta versión, se han introducido varias actualizaciones en el panel de optimización relacionadas con COIN y los ahorros conseguidos, con el fin de mejorar la precisión.

## Ejecutar acciones generadas por el motor de Turbonomic y gestionar políticas desde la interfaz de usuario de Cloudability - 17 de abril de 2026

Cloudability ha incorporado compatibilidad para permitir la ejecución de acciones de optimización generadas por el motor de Turbonomic en la interfaz de usuario de Cloudability, así como la capacidad de gestionar las políticas que impulsan el motor de optimización de Turbonomic y definir políticas de automatización desde la interfaz de usuario de Cloudability. Turbonomic Las acciones generadas por el motor de « VM », así como las relacionadas con el controlador de discos y de cargas de trabajo, ahora se pueden ejecutar desde la página «Rightsizing» > «Avanzado» > «Detalles de la acción».

Esta versión permite a los usuarios gestionar grupos, programaciones, flujos de trabajo y políticas de automatización desde la página «Preferencias de Rightsizing > Avanzado» de la interfaz de usuario de Cloudability. A partir de esta versión, los usuarios con los permisos adecuados pueden gestionar estas configuraciones desde la interfaz de usuario de Cloudability.

Nota:

Es importante asegurarse de que se actualicen las credenciales de todas las cuentas en la nube para garantizar que se apliquen los permisos necesarios que requiere el motor de « Turbonomic », de modo que se pueda ver el conjunto completo de acciones de optimización generadas y presentadas en la página «Rightsizing > Advanced»

## Compatibilidad con las recomendaciones de niveles de « Google Cloud Storage » - 14 de abril de 2026

Cloudability ha incorporado compatibilidad con las recomendaciones de niveles de « Google Cloud Storage ». Cloudability Ahora los usuarios pueden optimizar los costes de GCS gracias a las recomendaciones sobre configuraciones de clases de almacenamiento a nivel de depósito, que incluyen las opciones Estándar, Nearline, Coldline, Archivo y Autoclass. Para cada bucket, Cloudability analiza el uso del almacenamiento, los patrones de acceso y los costes operativos durante un mínimo de 30 días para identificar posibles errores de configuración de las clases de almacenamiento.

Estas recomendaciones siguen el mismo formato que las recomendaciones de optimización de niveles existentes en « AWS S3 » y se podrán consultar en la página «Rightsizing Explorer». Los clientes que tengan activada la facturación por recursos en « GCP » empezarán a recibir automáticamente estas recomendaciones.

Nota:

Los clientes deben conceder permisos de « storage.buckets.list » a todos los elementos de esta función para que funcione correctamente.

## GCP El ajuste de la capacidad informática ahora incluye los costes de licencia - 14 de abril de 2026

Cloudability ha mejorado las recomendaciones de optimización de recursos informáticos de GCP para incluir los costes de las licencias del sistema operativo y del software en los cálculos de ahorro. Cloudability Ahora los usuarios pueden recibir recomendaciones de ajuste de recursos más precisas que tienen en cuenta el coste total de funcionamiento de las instancias de GCP, incluidas las licencias de Windows Server, SQL Server, Red Hat Enterprise Linux, SUSE, Linux Enterprise y Ubuntu Pro.

Anteriormente, las recomendaciones de optimización de « GCP » solo tenían en cuenta los costes de computación (CPU, memoria y almacenamiento), lo que podía dar lugar a estimaciones de ahorro incompletas para las instancias que ejecutaban sistemas operativos o software con licencia. Con esta mejora, las recomendaciones calculan ahora tanto los costes de computación como los de licencia para las instancias de origen y los destinos recomendados, lo que garantiza que se respeten los requisitos de licencia y el número mínimo de núcleos a la hora de sugerir tipos de instancia alternativos.

Estas recomendaciones mejoradas aparecerán en la página «Rightsizing Explorer» y mantendrán el mismo formato que las recomendaciones de recursos de « GCP » ya existentes. Los clientes con instancias de « GCP » que ejecuten sistemas operativos con licencia verán automáticamente estimaciones de ahorro más precisas que reflejen el coste total de propiedad.

## Mejoras en los permisos de solo lectura de los mapas de negocio - 14 de abril de 2026

Hemos implementado una mejora en los permisos de solo lectura del área de asignaciones empresariales. Con este cambio, los usuarios con acceso de solo lectura ya no verán los botones de acción (Editar, Eliminar, Crear, etc.) en dimensiones de negocio, dimensiones jerárquicas y métricas de negocio. Además, hemos unificado la experiencia de visualización en todas las áreas de Business Mappings. Los usuarios con permisos de solo lectura ya pueden acceder de forma sistemática a los detalles de las dimensiones de negocio, las dimensiones jerárquicas y las métricas de negocio.

## Posibilidad de cambiar el nombre de una dimensión empresarial jerárquica - 9 de abril de 2026

Hemos incorporado la posibilidad de cambiar el nombre de las dimensiones empresariales jerárquicas en las asignaciones empresariales. Con este cambio, los usuarios ya pueden editar el nombre de sus dimensiones jerárquicas de negocio directamente desde la interfaz, lo que les ofrece una mayor flexibilidad a la hora de organizar sus estructuras.

## Cloudability Rightsizing establece umbrales de ahorro para « Block Storage » - 7 de abril de 2026

Cloudability Rightsizing ha incorporado una nueva opción en las preferencias de Rightsizing para ofrecer una cantidad mínima de ahorro en « Block Storage » dentro de las «Recomendaciones básicas» de « Cloudability ». Este umbral (definido para recomendaciones de 30 días y prorrateado para recomendaciones de 10 días) permite a las organizaciones establecer el importe mínimo de ahorro para sus recomendaciones de almacenamiento en bloque ( AWS EBS, Azure Disk y GCP Persistent Disk) y descartar aquellas recomendaciones que no alcancen dicho umbral.

Esta versión permite a las organizaciones centrarse en las recomendaciones más relevantes, de forma similar a la funcionalidad ya existente que se estableció para las recomendaciones de ajuste de recursos de Compute

## Cloudability Asistencia técnica para la gestión de « GitHub Enterprise » - 7 de abril de 2026

La incorporación de la compatibilidad con **el servidor** de « GitHub Enterprise » amplía el alcance de « Cloudability Governance» a entornos autohospedados y altamente regulados, lo que permite a las empresas integrar directamente **las comprobaciones de políticas**, **las estimaciones de costes** y **las recomendaciones** de « FinOps » en sus flujos de trabajo locales existentes de « GitHub-based ». Esta mejora permite a los equipos de la plataforma y de FinOps aplicar las mismas medidas de seguridad y los mismos flujos de trabajo de aprobación que utilizan con GitHub.com a los repositorios alojados en su propia infraestructura, alineando así los controles de costes y cumplimiento con los marcos de gobernanza existentes para **GitHub Enterprise**.

## Nuevos permisos de « Turbonomic » para AWS y Azure – 6 de abril de 2026

Esta versión introduce nuevos permisos Turbonomic en Cloudability Premium y forma parte de la actualización trimestral de permisos.

[Consulta la guía de referencia sobre permisos](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=azure-permissions-reference-microsoft "(se abre en una pestaña o una ventana nueva)") de visita para obtener más información.

Nota: Estos permisos son de naturaleza acumulativa y no afectan al funcionamiento de las cuentas y permisos acreditados existentes. Sin embargo, será necesario volver a acreditarse para añadir estos nuevos permisos

## Cloudability x ServiceNow Integración de la CMDB con Business Dimensions - 1 de abril de 2026

Hoy lanzamos **la integración de la base de datos de gestión de configuraciones (CMDB)** de Cloudability y ServiceNow para Business Dimensions.

La integración de la CMDB de Cloudability con ServiceNow permite la sincronización automática entre la CMDB de ServiceNow y las asignaciones empresariales de IBM Cloudability, lo que permite a las organizaciones utilizar ServiceNow como fuente única de información fiable para la estructura empresarial y la lógica de asignación de costes en Cloudability.

Esta integración elimina la necesidad de realizar actualizaciones manuales o mediante API en las asignaciones empresariales de Cloudability, ya que refleja automáticamente los cambios de la CMDB de ServiceNow en Cloudability. La integración solo se puede instalar en versiones certificadas de ServiceNow; las versiones no compatibles bloquearán la instalación por completo.

**Puntos destacados:**

- **Creación automática de esquemas de negocio:** Los esquemas de negocio de « Cloudability » se crean y mantienen automáticamente a partir de los datos de la base de datos de gestión de configuraciones (CMDB) de « ServiceNow ».
- **Gobernanza centralizada:** La base de datos de gestión de configuraciones (CMDB) de ServiceNow actúa como fuente de referencia para los datos sobre la organización, las aplicaciones y los centros de coste que se utilizan para la asignación de costes en la nube.
- **Sincronización casi en tiempo real:** las actualizaciones realizadas en la base de datos de gestión de configuraciones (CMDB) de ServiceNow se reflejan automáticamente en Cloudability sin necesidad de intervención manual.
- **Aplicación nativa ServiceNow :** La integración se ofrece como una aplicación certificada disponible en la tienda ServiceNow.

ServiceNow La integración está disponible en la tienda « ServiceNow » en el siguiente enlace: [https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8](https://store.servicenow.com/store/app/c3864d3d4784fe1482f632c4f16d43c8 "(se abre en una pestaña o una ventana nueva)")

## Datos de identificación de proveedores: posibilidad de dar de baja las cuentas sin datos de identificación - 1 de abril de 2026

Esta versión introduce la posibilidad de archivar **cuentas sin credenciales** directamente desde la pantalla «**Credenciales de proveedores** ».

Anteriormente, las cuentas sin acreditar debían acreditarse primero antes de poder archivarse. Con esta actualización, las cuentas que no hayan sido verificadas ya pueden archivarse directamente mediante el **menú** **de los tres puntos (** **⋯)**, lo que elimina la necesidad de realizar la verificación.

Ahora es posible realizar acciones generales de archivo directamente desde la pantalla «Credenciales de proveedor» para todas las cuentas, independientemente de su estado.

## Detección de anomalías - Comentarios sobre anomalías - 30 de marzo de 2026

Hemos lanzado **la función «Comentarios sobre anomalías** ». A partir de hoy, puedes enviar comentarios rápidos sobre las anomalías detectadas con un simple **«Me gusta» o «No me gusta** ». Esto nos ayuda a determinar si las anomalías que se señalan son realmente útiles. Anteriormente, no existía una forma directa ni estructurada de compartir comentarios, lo que limitaba nuestra capacidad para mejorar la calidad de la detección basándonos en las opiniones reales de los usuarios.

## Importación masiva en WLP - 30 de marzo de 2026

Esta versión introduce una mejora importante en la función de importación masiva de Workload Planning (WLP). Permite a los clientes cargar un archivo estructurado con hasta 500 recursos en una sola operación, independientemente del tipo de servicio, la región y el proveedor de servicios en la nube.

Esta función ayuda a los clientes a planificar las cargas de trabajo de forma más eficiente, ya que elimina la necesidad de añadir recursos manualmente o en pequeños lotes. Ahora los usuarios pueden importar hasta 500 recursos a la vez, recibir recomendaciones al instante y agilizar su proceso de planificación en la nube.

## Credenciales de proveedor: mejoras en la experiencia de usuario del panel de detalles - 24 de marzo de 2026

Esta versión introduce varias mejoras de usabilidad en el panel de detalles **de «Credenciales de proveedor – Permisos»**, lo que facilita a los administradores la revisión y gestión de los permisos a gran escala.

- Los permisos están ahora **mejor organizados en secciones claramente definidas**, lo que mejora la legibilidad y ayuda a los usuarios a comprender rápidamente cómo se agrupan los permisos de cada función.
- Para simplificar aún más la revisión de permisos, hemos añadido **filtros rápidos** que permiten a los administradores alternar al instante entre los permisos **habilitados** y **los deshabilitados**, lo que facilita mucho identificar cuáles no están habilitados.
- También se ha incorporado **una** nueva barra de búsqueda que permite realizar búsquedas rápidas en las secciones de permisos y funciones, lo cual resulta especialmente útil cuando se trabaja con un gran número de permisos.
- Por último, los administradores ya pueden **descargar el estado de los permisos a nivel de cuenta**, lo que permite revisarlos sin conexión y facilita las auditorías a la hora de gestionar configuraciones de permisos complejas.

## Exportar el estado de las cuentas en las credenciales de proveedores - 19 de marzo de 2026

Esta versión incluye la posibilidad de exportar el estado de las credenciales de los proveedores en formato CSV. Esta función ayuda a nuestros clientes a consultar rápidamente el estado de las cuentas cuando el número de cuentas es elevado.

Cada una de las fuentes de datos acreditadas que tengan estado de cuenta se puede exportar en formato CSV. Cada fuente de datos tendrá su propia exportación.

La exportación contiene los datos que aparecen en la página principal de credenciales de proveedor para cada cuenta.

## Snowflake Información sobre costes de almacén y asistencia con etiquetas - 19 de marzo de 2026

Cloudability Ahora ofrece una mayor visibilidad de los costes de « Snowflake » con **detalles a nivel de almacén**, incluidos **los costes de los servicios informáticos y en la nube**, junto con **etiquetas a nivel de cuenta y de almacén** para mejorar la precisión de la asignación y la elaboración de informes. Estas mejoras permiten a los equipos de datos, de « FinOps, » y de ingeniería comprender el gasto en « Snowflake » con un nivel de detalle mucho mayor.

Con esta actualización, los equipos pueden asignar los costes con mayor precisión e identificar los principales factores de coste mediante los paneles de control y las dimensiones de negocio de « Cloudability ». Anteriormente, Cloudability solo ofrecía visibilidad a nivel de servicio, lo que significaba que los clientes no podían ver el coste de cada almacén ni utilizar las etiquetas de Snowflake para la asignación de costes. Cloudability Ahora ofrece información más detallada directamente dentro de los flujos de trabajo existentes, lo que permite una gestión de costes más eficaz y una toma de decisiones fundamentada.

**¿Cómo funciona?**

- **Para los clientes actuales que ya tienen acceso a esta funcionalidad:** no es necesario realizar ninguna acción.
- **Para los clientes que ya utilizan credenciales de Snowflake en Cloudability :**
- Las organizaciones que no hayan renovado su acreditación anteriormente deberán hacerlo para activar estas mejoras. El proceso no ha cambiado: solo tienes que seguir los pasos que se indican en nuestro [Centro de ayuda](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=cloudability-connect-snowflake "(se abre en una pestaña o una ventana nueva)") y ejecutar la plantilla actualizada que se proporciona en la interfaz de usuario.
- **Para los clientes que visitan por primera vez Snowflake en Cloudability :**
- Siga el proceso estándar de acreditación descrito en [Connect Snowflake](../admin/connect-snowflake.html)

Nota: En las instrucciones de Connect Snowflake se ofrece información adicional sobre los requisitos previos para la compatibilidad con etiquetas.

## Informes guardados del inventario de recursos: mejora en el manejo de los intervalos de fechas - 17 de marzo de 2026

Anteriormente, al abrir un informe guardado del Inventario de Recursos (RIS) con un intervalo de fechas no renovable que superaba el periodo máximo admitido de tres meses, el informe no se cargaba y aparecía un mensaje de error.

Con esta actualización, esos informes se cargan correctamente en lugar de dar error. Si el intervalo de fechas guardado supera el límite permitido, Cloudability lo restablece automáticamente al intervalo predeterminado de 7 días y muestra una notificación emergente para informar a los usuarios de que se ha ajustado el intervalo de fechas.

Esta mejora garantiza que se pueda seguir accediendo a los informes guardados incluso cuando los intervalos de fechas en los que están almacenados superen el límite permitido.

## Paneles de control 2.0 - 16 de marzo de 2026

Hoy lanzamos **Dashboards 2.0**, una importante renovación de la interfaz de usuario de toda la experiencia de Dashboards en Cloudability. Esta actualización tiene como objetivo modernizar la tecnología utilizada en los paneles de control, habilitar nuevas funciones en los paneles y acelerar el desarrollo de futuras funcionalidades. Los paneles de control 2.0 resuelven varios problemas de usabilidad y optimizan el diseño general del marco de paneles de control.

**¿Qué puedes esperar?**

- No hay cambios funcionales entre Dashboards 2.0 y la versión anterior de Dashboards. Todas las funciones seguirán siendo las mismas.
- Habrá ligeras diferencias visuales que no afectarán al funcionamiento del producto.

**La función «Dashboards» v2 ya está disponible en todas las regiones.**

## Compatibilidad con OCI en el inventario de recursos - 16 de marzo de 2026

Nos complace anunciar que la función «Inventario de recursos» ahora es compatible con **la Infraestructura en la Nube de Oracle (OCI)**. Con esta versión, ahora puedes consultar los datos de costes, utilización y metadatos a nivel de recursos de los servicios de OCI Compute (máquinas virtuales) en la misma interfaz unificada que ya utilizas para otros proveedores de hiperescala.

El soporte técnico del servicio OCI Compute incluye todas las funciones disponibles actualmente en Resource Inventory. Para habilitar esta función en su organización de Cloudability, póngase en contacto con su TAM, CSM o con el representante de su cuenta de Apptio. En un plazo de 3 a 4 días laborables tras la activación, los datos completos del inventario de OCI para los recursos de computación estarán disponibles en Cloudability.

Para obtener más información, consulta [el Inventario de recursos de OCI](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=inventory-oci-resource "(se abre en una pestaña o una ventana nueva)").

## Cloudability Se añade compatibilidad con la generación dinámica de informes COIN - 6 de marzo de 2026

Cloudability Se ha añadido una nueva pestaña al panel de optimización que permite a los usuarios informar sobre oportunidades de optimización de recursos y contextualizar dichas oportunidades con el gasto subyacente en forma de puntuación COIN (índice de optimización de costes).

Las puntuaciones COIN pueden aprovecharse para comprender y contextualizar mejor las oportunidades, así como para normalizar las oportunidades de optimización entre los diferentes equipos y organizaciones, a fin de que sirvan como tabla de clasificación o forma de medir la eficiencia. En el recién lanzado COIN Explorer, los usuarios pueden añadir o eliminar campos para comprender las puntuaciones COIN con el nivel de detalle deseado, así como exportar estos datos según sea necesario.

Las organizaciones pueden elegir si desean aprovechar su conjunto de recomendaciones básicas o su conjunto de recomendaciones avanzadas para completar el panel de optimización, incluido COIN Explorer.

## Cloudability Rightsizing añade compatibilidad con la métrica « Azure » (Bytes de memoria disponibles) – 4 de marzo de 2026

Hoy hemos presentado métricas de memoria mejoradas para las recomendaciones de ajuste del tamaño de los recursos informáticos de Azure. Cloudability ahora utiliza [la métrica estándar de Azure, "Bytes de memoria disponibles",](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/metrics-supported#microsoftcomputevirtualmachines "(se abre en una pestaña o una ventana nueva)") como alternativa cuando no se dispone de datos personalizados sobre la utilización de la memoria. Esta mejora garantiza que más instancias de Azure reciban recomendaciones completas sobre el dimensionamiento adecuado sin necesidad de que los clientes configuren métricas personalizadas.

Anteriormente, las instancias de Azure sin métricas de memoria personalizadas no podían recibir recomendaciones de ajuste de tamaño basadas en la memoria, lo que limitaba las oportunidades de optimización. Con esta versión, Cloudability calcula automáticamente la utilización de la memoria a partir de la métrica de bytes de memoria disponible integrada en Azure, ampliando la cobertura de las recomendaciones de redimensionamiento en todos los recursos informáticos de Azure.

Esta mejora puede dar lugar a recomendaciones actualizadas y estimaciones de ahorro para instancias de Azure que anteriormente carecían de datos de memoria. Los clientes no tienen que hacer nada: la mejora se aplica automáticamente a todas las recomendaciones informáticas de Azure. Los clientes que ya tengan configuradas métricas de memoria personalizadas no verán ningún cambio en sus recomendaciones.

Para obtener más información, consulta la [documentación de ayuda sobre recomendaciones para el ajuste de recursos](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=recommendations-rightsizing "(se abre en una pestaña o una ventana nueva)").

## Cloudability Compromisos Añade compatibilidad con instancias reservadas de Azure App Service – 23 de febrero de 2026

Hoy hemos implementado soporte para [las instancias reservadas de Azure App Service](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/prepay-app-service "(se abre en una pestaña o una ventana nueva)"). El [duodécimo](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(se abre en una pestaña o una ventana nueva)") tipo de compromiso de « Azure » compatible, Azure App Service. Las «Reserved Stances» ofrecen un descuento en recursos de computación a cambio de un compromiso de uno o tres años de uso por horas. Este tipo de compromiso se clasifica como compromiso basado en recursos y, como tal, requiere la selección de parámetros de uso específicos: nivel, instancia y región. Con esta versión, admitimos este tipo de compromiso tanto en la cartera de compromisos como en las recomendaciones.

Para más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Recomendaciones avanzadas compatibles con el panel de optimización – 23 de febrero de 2026

Cloudability Premium Ha introducido compatibilidad con las recomendaciones avanzadas (con tecnología de Turbonomic ) en el panel de optimización. Ahora, los usuarios que utilizan las recomendaciones avanzadas y aprovechan la potencia y flexibilidad de las políticas personalizables pueden ver esas acciones recomendadas en los campos de informes del panel de optimización y en los cálculos COIN.

Los usuarios pueden seleccionar en la página Preferencias de ajuste > Panel de control si desean mostrar recomendaciones básicas o avanzadas.

## Nombres de mapas empresariales fáciles de usar en las exportaciones de datos - 19 de febrero de 2026

Con esta versión, los paneles y los informes de Cloudability han lanzado una nueva funcionalidad que devolverá los nombres fáciles de usar de métricas empresariales, dimensiones empresariales, grupos de cuentas y etiquetas al exportar datos de CSV desde un informe, un panel o Explore. Anteriormente, las métricas y dimensiones empresariales se exportaban utilizando un identificador de columna (por ejemplo, « category12 »), en lugar de la etiqueta fácil de usar. El comportamiento **predeterminado** de las exportaciones basadas en API **NO cambiará**. Sin embargo, los usuarios podrán añadir la opción "useDimensionNames=true" en la solicitud para activar esta función cuando utilicen la API. Las integraciones API existentes NO se verán afectadas, y los usuarios podrán utilizar los nombres fáciles de usar de Business Mappings si lo desean, añadiendo el indicador a sus solicitudes API.

## Cloudability Alertas de anomalías ignoradas - 19 de febrero de 2026

Hoy hemos lanzado las alertas de ignorar anomalías. A partir de hoy, los usuarios pueden ignorar temporalmente las alertas de anomalías directamente desde la página de configuración de alertas para reducir el ruido durante los eventos de costes previstos y garantizar que solo se muestren las alertas significativas y procesables.

Entre sus principales funciones figuran:

1. Ignorar alertas en el nivel de alerta de anomalías individuales
2. Funcionalidad de ignorar alertas compartidas
3. Seleccionar duración preestablecida para ignorar (7, 14 o 30 días)
4. Defina un intervalo de fechas personalizado para ignorar las alertas.
5. Edita la duración de la omisión (amplíala o acórtala según sea necesario)
6. Programar ignorar para un período futuro
7. Ignora alertas de forma masiva utilizando la opción Ignorar alertas de anomalías masivas
8. Reanudar automáticamente las alertas una vez finalizado el período de ignorar

## Cloudability Commitments anuncia su apoyo al nuevo programa Spend CUD de la Fundación Nacional de la Construcción ( GCP ) – 16 de febrero de 2026

Hoy, IBM Cloudability anuncia su apoyo al nuevo programa CUD de GCP.

*En segundo plano*

A principios de 2025, GCP anunció cambios significativos en la forma de facturar sus compromisos basados en el gasto, [lo que afectó a 13 de sus 17 tipos de compromiso](https://docs.cloud.google.com/docs/cuds-multiprice#affected-cuds "(se abre en una pestaña o una ventana nueva)").

El 15 de julio de 2025, GCP permitió la migración anticipada al nuevo programa CUD basado en gastos. Entre julio de 2025 y principios de febrero de 2026, los usuarios podrán optar voluntariamente por el nuevo modelo de facturación. Durante la primera semana de febrero, GCP comenzó a migrar por la fuerza a sus clientes, completando el proceso el viernes 6 de febrero. Aquí puede consultar una breve descripción general del programa: [*Facturación más sencilla, ahorro más claro: una guía de « FinOps » sobre los CUD actualizados basados en el gasto*](https://cloud.google.com/blog/topics/cost-management/a-finops-professionals-guide-to-updated-spend-based-cuds "(se abre en una pestaña o una ventana nueva)").

Habíamos recomendado a los usuarios que retrasaran la migración, ya que se trataba de un cambio importante en los informes, la cartera de compromisos y las recomendaciones de compromiso.

*Soporte para el nuevo paradigma de facturación*

Con este anuncio, el nuevo paradigma de facturación ahora es compatible tanto con la funcionalidad de informes como con la de compromisos. La cartera de compromisos y las recomendaciones se han restablecido hasta alcanzar una paridad casi total con el modelo de facturación anterior. En cuanto a la presentación de informes, hemos mejorado la experiencia con respecto a la anterior.

A alto nivel, la presentación de informes sobre el coste del compromiso y los residuos es ahora más sencilla y sigue el paradigma ya establecido para AWS y Azure. Además, ahora podemos informar sobre estos datos a nivel de cada CUD. Bajo el paradigma anterior, esto no era posible y representaba un punto débil común para los usuarios que buscaban aplicar una lógica granular de reembolso o reembolso interno.

Estos cambios están activos en producción para todos los usuarios. Para los usuarios que migraron voluntariamente antes de la migración forzosa de febrero, es posible que sea necesario volver a recuperar los datos del mes anterior. Para obtener más información, consulte [la Guía complementaria de GCP CUD.](../product/supplemental_guide_to_gcp_s_spend_cud_program.html)

## Cloudability Soporte para Azure Foundry (Actualización de marca) – 13 de febrero de 2026

Con esta versión, hemos actualizado la dimensión «Nombre del servicio» en Cloudability para alinearla con el cambio de marca de Microsoft de « Azure Cognitive Services» a « Azure Foundry».

El nombre de servicio existente « Azure Cognitive Services» ahora se representará como dos nombres de servicio distintos:

Tabla 1. ¿Qué está cambiando?

| Antes | Después |
| --- | --- |
| Azure Servicios cognitivos | Azure Modelos de fundición Azure |
|  | Azure Herramientas de fundición |

Este cambio refleja la nueva estructura de la marca Foundry de Microsoft, que separa:

- **Modelos de Foundry** : motores de inferencia central ( Azure OpenAI, Phi, DeepSeek, Llama)
- **Herramientas de Foundry** : capacidades de IA preintegradas (voz, lenguaje, inteligencia documental)

**Impacto**

- Todos los datos nuevos reflejarán automáticamente los nombres de servicio actualizados
- Los datos históricos reflejarán los nuevos nombres tras su reprocesamiento

## Ver visibilidad de asignaciones para grupos de usuarios y Entra ID – 11 de febrero de 2026

Hemos mejorado la gestión de grupos añadiendo visibilidad sobre dónde se utilizan **los grupos de usuarios y los grupos de Entra ID** en las vistas. Anteriormente, si se utilizaba un grupo en la asignación de vistas, el sistema bloqueaba su eliminación y los administradores no tenían una forma fácil de identificar qué vistas estaban utilizando el grupo. Esto a menudo requería comprobar manualmente varias vistas.

Con esta mejora, los administradores ahora pueden ver una **lista de solo lectura de todas las vistas** en las que se ha asignado un grupo, directamente desde la página de definición del grupo de usuarios o del grupo de ID de Entra. La lista muestra los nombres de las vistas e indica claramente cuándo un grupo no se utiliza en ninguna vista, lo que ayuda a optimizar la limpieza de grupos y reducir el esfuerzo manual.

Para obtener más información, consulta la documentación de ayuda [sobre «Gestionar grupos de usuarios»](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-user "(se abre en una pestaña o una ventana nueva)") y «[Gestionar grupos de Entra ID](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-entra-id "(se abre en una pestaña o una ventana nueva)") ».

## Programación de sincronización automática para grupos de Entra ID: 5 de febrero de 2026

Hoy hemos añadido **la programación de sincronización automática para los grupos de Entra ID** con el fin de mejorar la usabilidad y reducir el esfuerzo administrativo. Anteriormente, los administradores de Cloudability tenían que sincronizar manualmente los grupos de Entra ID mediante la acción «Sincronizar grupo de Entra ID», lo que podía dar lugar a actualizaciones perdidas, ya que las membresías de los grupos de Entra ID cambian con frecuencia.

Con esta mejora, los administradores de Cloudability ahora pueden configurar **una programación de sincronización automática diaria, semanal o mensual** utilizando criterios de filtro definidos. Los grupos de Entra ID se sincronizan automáticamente según el calendario y los criterios seleccionados, lo que garantiza que Cloudability permanezca alineado de forma coherente con Entra ID, sin necesidad de intervención manual.

Para obtener más información, consulta la documentación de ayuda [sobre la gestión de grupos de Entra ID](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=groups-manage-entra-id "(se abre en una pestaña o una ventana nueva)").

## Cloudability El panel de optimización añade una base de costes efectiva para las recomendaciones de recursos - 2 de febrero de 2026

Hoy, Cloudability ha añadido la base del coste efectivo como una opción para las recomendaciones que aparecen en el Panel de optimización (Beta). La base de costes efectiva permite un cálculo más significativo del COIN al comparar el coste amortizado de los servicios con el ahorro efectivo de costes calculado por las recomendaciones de redimensionamiento de Cloudability. Esta preferencia se encuentra en la sección Preferencias de ajuste de tamaño > Panel de control, junto con otras preferencias y configuraciones que afectan al Panel de control de optimización.

## Cloudability Actualización de los compromisos en torno al próximo apoyo al nuevo programa CUD de GCP - 30 de enero de 2026

[El 16 de enero publicaremos un comunicado inicial](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-whats-new-in-essentials#topic__commitment-gcp-cud-cldy-essentials "(se abre en una pestaña o una ventana nueva)") sobre la migración obligatoria de « GCP » al nuevo programa «Spend CUD». La siguiente información es una actualización de lo que podemos compartir en este momento.

**¿Cuándo es la migración?**

- Si no ha migrado voluntariamente, GCP migrará a sus clientes al nuevo modelo de facturación la próxima semana: del 2 al 5 de febrero de 2026.

**¿Cuándo admitirá Cloudability el nuevo programa?**

- Tenemos previsto lanzar soporte iterativo a medida que ganemos confianza en nuestro lanzamiento. Cloudability Es probable que los informes, la cartera de compromisos y las recomendaciones sobre compromisos se publiquen de forma escalonada.
- Esperamos lanzar el soporte durante la semana del 9 al 13 de febrero de 2026. Esperamos que los clientes puedan disfrutar de todas las funciones a partir del lunes 16 de febrero.
- No es necesario que realice ninguna acción; esperamos admitir el nuevo programa automáticamente cuando se produzca la migración.

**¿Qué tengo que hacer?**

- Para los clientes que ya han migrado, necesitamos volver a recuperar los datos que se remontan al mes en que se inscribieron voluntariamente en el nuevo programa. Le solicitamos que se ponga en contacto con sus equipos de cuentas para proporcionar ese mes en preparación para nuestro lanzamiento de backend.
- Para los clientes que se someterán a la migración obligatoria la próxima semana, es posible que solicitemos una nueva recuperación de febrero para tener el historial completo. Proporcionaremos información actualizada la próxima semana.
- Tenga en cuenta que, para ambas cohortes, daremos soporte al nuevo programa una vez que se haya lanzado nuestra infraestructura. Esta nueva recuperación es un requisito único y solo es necesaria para los meses transcurridos entre el momento en que lanzamos el soporte backend y la migración.

Seguiremos informando sobre los avances a través de este centro de ayuda y de notificaciones en la aplicación. Si tiene alguna otra pregunta o duda, póngase en contacto con su equipo de cuentas.

## Compromiso de apoyo a la base de datos Azure para MySQL Capacidad reservada: 23 de enero de 2026

Hoy hemos implementado soporte para [la capacidad reservada de Azure Database para MySQL](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/understand-reservation-charges-mysql "(se abre en una pestaña o una ventana nueva)"). El [undécimo](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=discount-commitment-types-in-cloudability "(se abre en una pestaña o una ventana nueva)") tipo de compromiso « Azure » compatible, Azure. La base de datos de compromisos « MySQL » ofrece un descuento en recursos de computación a cambio de un compromiso de uno o tres años de uso por horas. Este tipo de compromiso se clasifica como compromisos basados en recursos y, como tal, requiere parámetros de uso específicos de la selección: Opción de despliegue, Instancia y Región. Con esta versión, admitimos este tipo de compromiso tanto en la cartera de compromisos como en las recomendaciones.

Para más información, consulte la documentación de ayuda sobre gestión de compromisos.

## Cloudability Optimización del tamaño de los conjuntos de máquinas virtuales de Azure - 22 de enero de 2026

Cloudability Ha añadido compatibilidad con conjuntos de escalado de máquinas virtuales de Azure en Rightsizing. Cloudability Los usuarios ahora pueden recibir recomendaciones para ajustar su comportamiento de escalado modificando los tipos de instancias utilizadas en el modelo de escalado automático ( ScaleSet ) con el fin de lograr un mejor resultado en términos de costes sin afectar al rendimiento de la aplicación.

Es posible que los clientes tengan que actualizar sus permisos para aprovechar esta versión, incluido el permiso de gestión:Reader o los tres permisos siguientes:

1. Microsoft.Compute/virtualMachineScaleSets/read
2. Microsoft.Compute/virtualMachineScaleSets/virtualMachines/read
3. Microsoft.Compute/virtualMachineScaleSets/extensions/read

Antes de esta versión, los usuarios con recomendaciones de computación de Azure podían haber visto recomendaciones de instancias individuales para instancias que formaban parte de conjuntos de escalado. Estas instancias ahora se tratarán como parte del conjunto de escalas en lugar de individualmente, por lo que algunos clientes pueden ver que sus recomendaciones para instancias de computación de Azure cambian con esta versión para evitar la doble contabilización.

Estas recomendaciones también serán visibles en la página Rightsizing Explorer y también se pueden vincular a tickets de Rightsizing ROI como otros tipos de recomendaciones.

## Contenedores avanzados con tecnología Kubecost – 22 de enero de 2026

Advanced Containers powered by Kubecost es un complemento de pago para Cloudability que proporciona acceso a todas las funciones de Kubecost directamente desde la experiencia de Cloudability.

Advanced Containers amplía la información existente sobre contenedores de Cloudability con capacidades avanzadas de visibilidad, optimización y automatización de costes de Kubernetes.

Con los contenedores avanzados, usted puede:

- Acceda a toda la potencia de Kubecost, incluida la asignación granular de costes de Kubernetes hasta el nivel de pod y contenedor.
- Supervise y optimice las cargas de trabajo de la GPU, incluyendo la visibilidad de los costes de la GPU y la información sobre el dimensionamiento adecuado.
- Habilite la optimización automatizada de la carga de trabajo ( Kubernetes ), incluido el redimensionamiento automatizado y práctico de la CPU y la memoria.
- Consulte los costes de Kubernetes en tiempo real, en lugar de los gastos de contenedores procesados por lotes o con retraso.
- Supervise y asigne los costes de los clústeres locales de Kubernetes, además de los entornos alojados en la nube.

Advanced Containers está disponible como complemento de pago para Cloudability y requiere la implementación del agente Kubecost en los clústeres de Kubernetes supervisados.

Para obtener instrucciones de configuración y detalles adicionales, consulte la documentación de contenedores avanzados de Cloudability.

## AWS - Compatibilidad con el formato CUR 2.0 Parquet: 20 de enero de 2026

Esta versión añade compatibilidad con AWS CUR 2.0 en formato parquet, lo que ayudará a los clientes a configurar cualquiera de los siguientes AWS CUR 2.0 formatos de archivo y compresión, lo que les dará más flexibilidad a la hora de elegir los formatos de compresión

• Texto/csv – gzip

• Parqué - parqué

## Nuevos permisos de Turbonomic para AWS, Azure y GCP – 19 de enero de 2026

Esta versión introduce nuevos permisos Turbonomic en Cloudability Premium y forma parte de la actualización trimestral de permisos.

[Consulta la guía de referencia sobre permisos](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=azure-permissions-reference-microsoft "(se abre en una pestaña o una ventana nueva)") de visita para obtener más información.

Nota: Estos permisos son de naturaleza acumulativa y no afectan al funcionamiento de las cuentas y permisos acreditados existentes. Sin embargo, será necesario volver a acreditarse para añadir estos nuevos permisos

## Cloudability Commitments anuncia su próximo apoyo al nuevo programa Spend CUD de la Fundación Nacional de la Construcción ( GCP ) - 16 de enero de 2026

Google Cloud Platform ( GCP ) ha modificado la fecha de migración obligatoria para el [nuevo programa CUD de gastos,](https://docs.cloud.google.com/docs/cuds-multiprice#how-to-opt-in "(se abre en una pestaña o una ventana nueva)") pasando del 26 de enero a un periodo de varios días: del 2 al 5 de febrero de 2026.

*¿Qué puedo esperar durante la migración?*

- Durante el día de la migración, GCP ha comunicado que los usuarios no podrán adquirir nuevos CUD durante al menos un breve periodo de tiempo, hasta que finalice la migración al nuevo programa de facturación.
- Cuando Cloudability comience a admitir el programa Spend CUD, nuestros sistemas tardarán al menos un día, pero no más de 48 horas, en actualizarse.
- No es necesario que realice ninguna acción: esperamos admitir el nuevo programa automáticamente cuando se produzca la migración

*¿Cómo puedo averiguar mi fecha de migración?*

GCP Envió un anuncio de servicio obligatorio (MSA) el 11 de diciembre de 2025 con su fecha de migración específica. También puede encontrar esta fecha en la página Resumen de facturación de la consola de GCP. Tenga en cuenta que Cloudability no tiene acceso a las fechas de migración de clientes individuales.

*¿Ya te has pasado al nuevo programa Spend CUD?*   
 Si se inscribió en el nuevo programa Spend CUD de forma anticipada, le pedimos disculpas por el retraso en la asistencia. La funcionalidad completa se restablecerá cuando comience el periodo oficial de migración a principios de febrero. Si tiene alguna otra pregunta o duda, póngase en contacto con su equipo de cuentas.

## Cloudability La gobernanza ya está disponible de forma generalizada: 15 de enero de 2026

Esta nueva capacidad aporta información proactiva sobre los costes y la aplicación de políticas directamente al flujo de trabajo de ingeniería, lo que garantiza que los cambios en la infraestructura sean rentables y cumplan con la normativa *antes* de su implementación.

Cloudability Governance ya está disponible para **los ingenieros** de DevOps, **los administradores de plataformas** y **los equipos** de FinOps que gestionan **recursos** de AWS y **utilizan** Terraform (ya sea **a** través de Terraform Community, **HCP Terraform** o **Terraform Enterprise**) para su solución de infraestructura como código. Esta función está diseñada para equipos que alojan sus repositorios de código **en** GitHub.com, incluido **GitHub Enterprise Cloud**.

Anteriormente, las prácticas de FinOps solían introducirse demasiado tarde en el ciclo de vida del desarrollo, lo que provocaba una desalineación entre Finanzas e Ingeniería. Este retraso obligó a realizar costosas modificaciones, ya que los equipos dependían de revisiones manuales o auditorías posteriores a la implementación para detectar ineficiencias en los costes e incumplimientos de las políticas, lo que provocó un gasto excesivo, riesgos de cumplimiento y tareas de corrección inesperadas para los ingenieros.

Cloudability Governance se integra con GitHub y Terraform para llevar la aplicación de políticas de FinOps y la visibilidad de costes a la canalización de CI/CD. Entre sus principales funciones figuran:

- **Estimación de costes previa a la implementación** : estimaciones de costes en tiempo real de AWS, incluidos precios personalizados y descuentos de EA, directamente en los flujos de trabajo de GitHub y Terraform.

- **Selección de recursos con optimización de costes** : recomendaciones para alternativas más económicas a EC2 y RDS con configuraciones similares.

- **Aplicación de políticas a nivel de IaC** : aplique etiquetas obligatorias, bloquee recursos heredados y establezca umbrales presupuestarios.

- **Supervisión del cumplimiento** : panel de control centralizado para supervisar el cumplimiento de las políticas de FinOps.

- **Gestión de relaciones públicas** : identifica y revisa las solicitudes de extracción que no cumplen con los requisitos mediante flujos de trabajo de aprobación integrados.

- **Ejecutar la integración de tareas con HCP Terraform** : Integre a la perfección la gobernanza de la plataforma de código abierto ( Cloudability ) como **una** tarea de ejecución en los espacios de trabajo de HCP Terraform. Esto permite que las comprobaciones de políticas se activen automáticamente durante la fase de planificación de una ejecución de Terraform, lo que permite una aplicación obligatoria o de asesoramiento antes de que se aprovisione la infraestructura.

Esta función hace que la gestión de los costes de la nube pase de ser reactiva a proactiva, ayudando a los equipos a evitar gastos excesivos e infracciones de las políticas antes de desplegar la infraestructura.

Para obtener más información sobre esta función, consulta [la documentación sobre gobernanza de « Cloudability](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=preview-governance-getting-started "(se abre en una pestaña o una ventana nueva)") ».

## Soporte para una base de costes eficaz en Rightsizing Explorer - 14 de enero de 2026

Cloudability Ha añadido compatibilidad con la base de costes efectiva en Rightsizing Explorer. Cloudability Los usuarios ahora pueden ver las recomendaciones de redimensionamiento por coste efectivo o bajo demanda al revisar las oportunidades de redimensionamiento en Explorer.

## Cloudability Rightsizing añade compatibilidad con direcciones ElasticIP no vinculadas a AWS   - 9 de enero de 2026

Cloudability ha añadido AWS ElasticIP aborda el tema del apoyo en Rightsizing. Cloudability Los usuarios ahora pueden recibir recomendaciones para eliminar direcciones ElasticIP no vinculadas como parte de sus iniciativas más amplias de optimización de la carga de trabajo y los recursos.

No se necesitan nuevos permisos para estas recomendaciones, los clientes pueden empezar a ver estas recomendaciones inmediatamente. Estas recomendaciones también serán visibles en la página Rightsizing Explorer y también se pueden vincular a tickets de Rightsizing ROI como otros tipos de recomendaciones.
