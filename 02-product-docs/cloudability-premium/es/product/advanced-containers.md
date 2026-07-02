---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Cloudability Contenedores avanzados"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/advanced-containers.html"
images:
  - "images/UA-arch.png"
  - "images/adv1.png"
  - "images/adv2.png"
  - "images/prov2.png"
  - "images/prov_clust.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cloudability Contenedores avanzados

**Visión general**

El nuevo módulo Advanced Containers de Cloudability incorpora la visibilidad en tiempo real de los costes de contenedores de Kubecost y otras capacidades al marco Cloudability SaaS, lo que proporciona una visión unificada del gasto en la nube y Kubernetes para los equipos de ingeniería de la plataforma FinOps, y DevOps. *Esta función está disponible actualmente como complemento opcional de pago para todos los clientes de Cloudability Essential, Standard y Premium*. Con esta oferta, puede asignar los costes a un nivel aún más detallado (espacio de nombres, etiqueta, anotación, controlador, servicio, etc.), obtener recomendaciones inmediatas de ahorro para cargas de trabajo de e Kubernetes s y aplicar la gobernanza de costes, todo ello desde la interfaz de Frontdoor. Es compatible con **entornos multinube ( AWS, Azure, GCP, Oracle )** e **híbridos/locales** Kubernetes ( OpenShift y más), por lo que puede gestionar los costes en todos los clústeres que se ejecutan en cualquier lugar.

**Funciones clave disponibles en el módulo Contenedores avanzados**

- **Visibilidad de los costes en tiempo real de Kubernetes**

  Proporciona supervisión continua y en tiempo real del consumo de recursos de Kubernetes y los costes asociados en todos los clústeres, lo que permite obtener información inmediata sobre las tendencias y anomalías en el gasto.

- **Asignación granular de costes y reembolso**

  Proporciona una asignación precisa de los costes en todas las estructuras nativas de Kubernetes, incluidos clústeres, nodos, espacios de nombres, implementaciones, servicios, etiquetas y anotaciones, totalmente conciliadas con los datos reales de facturación de la nube para un showback y un chargeback precisos.

- **Información y recomendaciones sobre optimización**

  Ofrece orientación de optimización integrada y recomendaciones de ahorro viables para reducir el gasto en Kubernetes, al tiempo que se mantiene el rendimiento y la fiabilidad de la carga de trabajo.

- **Presupuestos, alertas y gobernanza**

  Permite una gestión financiera proactiva para entornos de Kubernetes con presupuestos en tiempo real, alertas y controles de gasto a nivel de clúster, equipo o espacio de nombres, alineados con los presupuestos de nube existentes.

**Arquitectura de integración**

Bajo el capó, la integración está impulsada por el **agente** IBM FinOps, un recopilador de datos unificado de código abierto ( [GitHub](https://github.com/kubecost/ibm-finops-agent "(se abre en una pestaña o una ventana nueva)") ) dentro del clúster que sustituye al antiguo agente de métricas Cloudability y al recopilador independiente Prometheus de Kubecost. El agente de uso de recursos ( FinOps ) se ejecuta en cada clúster de Oracle Database ( Kubernetes ) y recopila información sobre el uso de recursos y metadatos directamente desde la API de Oracle Database ( Kubernetes ), el nodo, el núcleo y otras fuentes. A continuación**, envía** esos datos al backend de Cloudability y Kubecost.

A intervalos regulares (por defecto, el agente recopila datos cada 30 segundos y los emite cada 10 minutos), el exportador del agente captura una instantánea del estado del clúster, incluidos los pods, los nodos y las métricas de uso, y la envía a cada emisor habilitado. Esta arquitectura modular garantiza que los datos se recopilen una sola vez y se envíen de manera eficiente tanto al núcleo Cloudability como al módulo Advanced Containers.

Esta arquitectura permite que Cloudability y Kubecost funcionen en tándem: Cloudability proporciona informes de costes de alto nivel, tendencias y contexto multicloud (con todos los servicios en la nube), mientras que Kubecost ofrece información detallada específica de Kubernetes y exploración en tiempo real. La implementación de un único agente simplifica la sobrecarga al eliminar la necesidad de una instancia completa de Prometheus en cada clúster (lo que ahorra memoria/CPU). El agente es ligero y se ejecuta como un único contenedor pod para facilitar el escalado y la resiliencia. Toda la recopilación de datos utiliza API o métricas nativas de Kubernetes, y no se envía ninguna carga útil confidencial (como datos de aplicaciones), solo metadatos de recursos y facturación necesarios para el cálculo de costes.

![](../../../../03-media/cloudability-premium/images/UA-arch.png) (Diagrama de arquitectura para IBM FinOps agent)

**Cómo obtener acceso**

El módulo Advanced Containers de Cloudability es una función adicional opcional de pago disponible para los clientes de Cloudability. Para obtener acceso, póngase en contacto con su representante de IBM / Apptio o con el servicio de asistencia técnica para solicitar acceso a estas nuevas funciones. Confirmarán los requisitos de licencia y habilitarán la función en su entorno de Cloudability (si procede). Si aún no es cliente de IBM / Apptio, póngase en contacto con nosotros [aquí.](https://www.ibm.com/ca-en/contact?contactmodule "(se abre en una pestaña o una ventana nueva)")

Configuración e instalación

La configuración de la integración de Cloudability y Kubecost implica implementar el **agente** IBM FinOps en cada clúster Kubernetes que desee supervisar. Una vez implementado, el agente recopilará y enviará automáticamente los datos a su instancia de Cloudability y Kubecost.

**Resumen del proceso de instalación:**

**1. Recopilar la clave API y los secretos:** Cloudability utiliza su sistema de autenticación centralizado «Frontdoor» Apptio para las API. Puede obtener estas claves siguiendo los pasos que se indican en la sección «**Autenticación** » de esta [documentación.](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=cloudability-kubernetes-cluster-provisioning "(se abre en una pestaña o una ventana nueva)")

**2. Establecer el ID del clúster:** Decida un identificador único para su clúster (por ejemplo, “prod-cluster-1” ). Si utiliza el asistente de la interfaz de usuario Cloudability, deberá introducir el nombre del clúster y la versión de Kubernetes, y este lo integrará en la configuración. El ID del clúster se utiliza para etiquetar los datos enviados a Cloudability y debe permanecer coherente para ese clúster. (Para clústeres de GKE, añada también una etiqueta de clúster en el lado de GCP : etiquete su clúster con la clave gke-cluster y el valor que coincida con el ID del clúster. Esto ayuda a Cloudability asignar los datos de facturación de GKE al clúster correcto

*Consejo:* Se recomienda utilizar una convención de nomenclatura para los ID de clúster que sea única a nivel global en todos los clústeres (por ejemplo, incluir un código de entorno o región). Una vez elegido, no debe cambiar el ID de un clúster, o Cloudability lo tratará como un clúster diferente.

**3. Implemente el agente IBM FinOps en su clúster** : el agente FinOps se proporciona como un gráfico Helm para facilitar su instalación. Puede utilizar el comando « Helm » generado por « Cloudability » (a través del cuadro de diálogo «Provision») o instalar manualmente utilizando el repositorio publicado « Helm ». Para instalar manualmente utilizando Helm 3 en su clúster:

El agente IBM FinOps incluye **dos emisores** : uno para Kubecost y otro para Cloudability. Para enviar datos a ambas plataformas, debe habilitar **ambos emisores** durante la instalación. En la sección *Generate Command* ( **Generar** comando) (debajo de Provision Cluster, Aprovisionar clúster), haga clic en el enlace que se muestra en la captura de pantalla siguiente y siga las instrucciones para habilitar ambos emisores.

**Nota:** *el comando que se muestra en Cloudability Container Insights* ***solo habilita el emisor Cloudability****. Aún deberá configurar el emisor Kubecost por separado siguiendo las instrucciones del enlace.*

![](../../../../03-media/cloudability-premium/images/prov_clust.png)

Esto abrirá la siguiente interfaz de usuario que le guiará a través del proceso de instalación

![](../../../../03-media/cloudability-premium/images/prov2.png)

- Instala o actualiza el agente en tu clúster:

```
helm upgrade --install ibm-finops-agent \
--repo https://kubecost.github.io/finops-agent-chart finops-agent \
--namespace ibm-finops-agent \
--set agent.cloudability.uploadRegion=us-west-2 \
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.cloudabilityEnvId=<yourenvironmentid> \
--set clusterId=test \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey=<AccessKey> \
--set agent.cloudability.secret.cloudabilitySecretKey=<SecretKey> \
--set agent.cloudability.enabled=true \
--set global.federatedStorage.existingSecret=adv-containers-fed-store-config
```

- En el comando anterior, sustituya <YOUR\_CLUSTER\_ID> por el ID de clúster único elegido y proporcione la clave API de Cloudability y el ID de entorno recopilados en el paso 1. Estos valores garantizan que el agente sepa dónde enviar los datos. El gráfico creará una implementación de agente de control de acceso ( Kubernetes ) (o DaemonSet ) para el agente junto con las funciones RBAC necesarias.

- **Permisos:** Asegúrese de tener privilegios de administrador del clúster al realizar la instalación. El gráfico « Helm » configurará una cuenta de servicio y roles de clúster que permitirán al agente leer las métricas necesarias (pods, nodos, espacios de nombres, etc.). Si utiliza políticas RBAC restrictivas, es posible que tenga que conceder manualmente los permisos al agente según la documentación.

- **Red y almacenamiento:** el agente requiere acceso saliente HTTPS desde el clúster. En concreto, debe alcanzar frontdoor.apptio.com (para la autenticación) y api.cloudability.com (o sus equivalentes regionales) en el puerto 443. También carga datos en un depósito de Apptio -owned S3, por lo que es necesario acceder a \*.s3.amazonaws.com (con el nombre del depósito prefijado apptio). Si su clúster está detrás de un proxy o un firewall, configure las reglas de salida para permitir estos puntos finales. Además, el gráfico « Helm **» (Solicitud de volumen persistente)** crea de forma predeterminada una solicitud de volumen persistente (PVC) ( 8Gi por defecto) para el agente. Este almacenamiento se utiliza para almacenar temporalmente los datos de métricas en caso de problemas de conectividad o reinicios del agente, evitando así la pérdida de datos. Asegúrese de que su clúster pueda aprovisionar este PVC (se pueden ajustar los valores si es necesario).

- **Fuente de la imagen:** Tenga en cuenta que la imagen del contenedor del agente FinOps está alojada en IBM Container Registry ( icr.io ), no en Docker Hub. Asegúrese de que las políticas de extracción de imágenes o el firewall de su clúster permiten icr.io/ibm-finops/ \*. Si utiliza un espejo de registro privado, es posible que tenga que extraer y enviar la imagen desde icr.io manualmente (la documentación proporciona un ejemplo de extracción Podman ).

Una vez completada la instalación de Helm, compruebe que el pod del agente se está ejecutando:

```
kubectl get pods -n kubecost
```

Debería ver un pod llamado kubecost-finops-agent-... en estado Running.

**3. Recopilación y verificación de datos** : tras implementar el agente, este comenzará a recopilar datos de inmediato. Sin embargo, el procesamiento de SaaS de Cloudability suele reflejar los nuevos datos **en el plazo de una hora**. En la interfaz de usuario de Cloudability, vaya a **Contenedores avanzados** y compruebe que su clúster aparece en la lista de clústeres aprovisionados. Inicialmente, puede aparecer como «esperando datos». En un plazo de 24 horas, debería empezar a ver la información sobre la asignación de costes para ese clúster en los paneles de control de costes de contenedores de Cloudability. También puede consultar los registros del agente para comprobar si envía datos correctamente (busque las líneas de registro que indican que se han cargado datos).

Una vez que los datos estén fluyendo, Cloudability mostrará los costes asignados a los espacios de nombres, etiquetas, etc. de su clúster junto con tus otros costes de nube. Kubecost (si está instalado) también comenzará a mostrar los datos de costes en su interfaz de usuario en tiempo real (normalmente a los pocos minutos de la implementación). Recuerde que Cloudability se basa en las exportaciones de facturación en la nube para calcular el coste *total* del clúster (por ejemplo, el coste de las máquinas virtuales de los nodos). Si esas exportaciones de facturación aún no están configuradas o actualizadas, es posible que veas datos parciales. Asegúrese de que la integración de facturación en la nube en Cloudability esté configurada (consulte **los requisitos previos** a continuación).

**4. Habilitar SSO/Acceso (si procede)** : si su organización utiliza SSO para productos de Apptio, puede integrar el acceso de Kubecost con el inicio de sesión de Cloudability. El módulo Kubecost puede aprovechar el mismo SSO a través de Apptio Frontdoor, de modo que los usuarios que hayan iniciado sesión en Cloudability puedan acceder sin problemas a Kubecost sin necesidad de iniciar sesión por separado. Trabaje con el soporte técnico de IBM para configurar esta autenticación compartida si tiene previsto utilizar la interfaz de usuario independiente de Kubecost. Esto suele implicar configurar Kubecost con OIDC apuntando a Apptio Frontdoor IdP y otorgar a los usuarios los roles adecuados en Kubecost (que pueden reflejar los roles de Cloudability ).

**Utilización de productos**

Cloudability Advanced Containers consta de **dos componentes integrados** :

**1. Contenedor avanzado (página de resumen dentro de la interfaz de usuario de Cloudability )**

Esto proporciona una experiencia nativa de Cloudability simplificada y adaptada a los flujos de trabajo de FinOps, en la que se destacan los costes de los clústeres, la eficiencia, las tendencias de los espacios de nombres, el gasto en la nube y el uso de la red. Está diseñado para obtener información rápida, informes ejecutivos y visibilidad diaria de los costes.

**2. Aplicación avanzada independiente para contenedores (Kubecost 3.0 Experiencia dentro de Frontdoor)**

Esta es la interfaz completa de Kubecost, que ofrece análisis técnicos detallados de costes, asignaciones granulares, flujos de red, herramientas de diagnóstico y opciones de configuración avanzadas. Está diseñado para equipos de ingeniería, SRE y propietarios de plataformas que necesitan información detallada sobre los costes por hora y controles operativos.

Juntas, estas dos piezas ofrecen **resúmenes** e FinOps-ready es y **profundidad de nivel de ingeniería**, creando una experiencia unificada de contenedores avanzados en Cloudability y Kubecost.

**1. Uso de Kubernetes Análisis de costes en Cloudability**

**1.a. Contenedor avanzado (página de resumen dentro de la interfaz de usuario de Cloudability )**

En Cloudability SaaS, vaya a **Insights > Contenedores avanzados**. Esto abrirá la **página de resumen de contenedores avanzados**.

![](../../../../03-media/cloudability-premium/images/adv1.png)

- **Resumen de costes de alto nivel**

Muestra los costes totales de la nube ( Kubernetes ), los costes totales de la nube y los posibles ahorros mensuales en un solo lugar.

Las superficies cambian semana tras semana, por lo que los usuarios pueden detectar al instante los picos de costes o las anomalías.

Destaca la eficiencia general del grupo, lo que ayuda a los equipos a evaluar las necesidades de optimización y reducción de residuos.

- **Desglose a nivel de clúster**

Enumera todos los clústeres con su gasto individual y estado de salud (activo/sin supervisar).

Ayuda a los usuarios a identificar rápidamente los clústeres más costosos y a validar la conectividad/supervisión.

Proporciona tendencias a lo largo del tiempo para que los equipos puedan ver cómo evolucionan los costes del clúster a diario.

- **Resumen sobre la eficiencia de los recursos**

Muestra la asignación de CPU, RAM, GPU y almacenamiento frente al uso real.

Hace visible el coste de inactividad frente al coste de uso, lo que ayuda a cuantificar el desperdicio en todos los recursos.

Permite tomar decisiones inmediatas sobre el dimensionamiento adecuado y la planificación de la capacidad.

- **Información sobre los costes a nivel de espacio de nombres**

Enumera los principales espacios de nombres que impulsan el gasto en los clústeres.

Incluye gráficos de tendencias para mostrar cuándo y dónde están aumentando los costes del espacio de nombres.

Ayuda a identificar rápidamente las cargas de trabajo ruidosas o en crecimiento.

- **Desglose de los costes de red:**

  Destaca los espacios de nombres con gran carga de red y los servicios con altos volúmenes de salida o tráfico. Superficies con destinos de tráfico costosos entre regiones o zonas. Ayuda a los equipos a controlar los costes ocultos de salida que a menudo se pasan por alto en las revisiones de FinOps.

**Nota:** *Los datos de costes de Advanced Containers se generan en Cloudability tiempo real a partir del uso, mientras que los datos oficiales de facturación de la nube de se actualizan normalmente a diario. Pueden existir discrepancias entre las estimaciones de costes inmediatos de Kubecost y los costes finales facturados que aparecen en Cloudability debido a cuestiones de tiempo, reembolsos o descuentos. A lo largo de un mes completo, las cifras deberían coincidir bastante (especialmente si se utiliza la opción «Cost Adjusted/Amortized» (Coste ajustado/amortizado) en « Cloudability » (Coste de los productos vendidos) para incluir los descuentos). Pero no se alarme si un día determinado la interfaz de usuario de Kubecost muestra X dólares para un espacio de nombres y Cloudability muestra X dólares ± un pequeño porcentaje: esto es normal debido a los diferentes métodos utilizados. La integración tiene como objetivo proporcionar información oportuna, no un libro de contabilidad exacto en todo momento.*

**1.b. Uso del módulo independiente Advance Container**

Para los usuarios que necesitan un análisis más interactivo específico de Kubernetes o un control en tiempo real, se puede utilizar **la interfaz de usuario de** Advanced Containers junto con Cloudability :

![](../../../../03-media/cloudability-premium/images/adv2.png)

- **Acceso a la interfaz de usuario de Advanced Containers:** si se ha implementado Advanced Containers, se puede acceder a él directamente en el navegador a través de Frontdoor. Cloudability También aparece un enlace profundo específico en la página Descripción general de contenedores avanzados, que permite a los usuarios abrir el contenedor avanzado independiente (interfaz de usuario de Kubecost 3.0 ) en una nueva pestaña. Con el SSO compartido, los usuarios pueden navegar sin problemas sin necesidad de iniciar sesión por separado.

- **La interfaz de usuario de Kubecost** ofrece una experiencia más rica e interactiva que la descripción general de Cloudability. Por ejemplo, la vista «Asignación de costes» admite agrupaciones multidimensionales, filtrado avanzado AND/OR (introducido en Kubecost 3.0 ) y visualización inmediata del impacto en los costes. Kubecost también conserva datos históricos detallados, incluida la resolución por hora, con ajustes de retención configurables para facilitar un análisis profundo.

- **Kubernetes Optimización y acciones:** En la interfaz de usuario de Kubecost, puede explorar en profundidad información específica sobre optimización. Por ejemplo:

- **Recomendaciones de ahorro (información sobre ahorro):** una lista de oportunidades como «eliminar volúmenes persistentes no utilizados» o «reducir el tamaño de los nodos inactivos», junto con el ahorro estimado. Se basan en políticas (por ejemplo, detectar si la utilización de un nodo es inferior al 5 % durante 7 días).

- **Información sobre el dimensionamiento adecuado:** Kubecost ofrece recomendaciones **sobre el dimensionamiento adecuado de los contenedores**. Puede ver recomendaciones para las solicitudes de CPU/memoria de cada implementación basadas en el uso real. Kubecost 3.0 añade una nueva interfaz de usuario para gestionar las solicitudes de contenedores en todos los clústeres con solo unos clics. Podría utilizar esto para reducir los recursos solicitados y recortar costes de forma inmediata (especialmente en entornos de autoescalado).

- **Optimización de grupos de nodos (clústeres):** Kubecost puede sugerir cómo ajustar los tipos de instancias de nodos o la configuración de autoescalado. En v3.0, las recomendaciones sobre el tamaño de los nodos tienen en cuenta el uso de la GPU y muestran visualizaciones de la capacidad frente al uso. Estas recomendaciones también tienen en cuenta los precios reales de la nube (incluidos los descuentos para empresas o las instancias reservadas) para ofrecer estimaciones de ahorro realistas.

- **Supervisión de red:** proporciona un mapa visual de los flujos de tráfico de red entre cargas de trabajo, espacios de nombres y servicios, lo que ayuda a los equipos a identificar rutas de salida de alto coste, patrones de comunicación inesperados y posibles cuellos de botella en el rendimiento.

- **Automatización:** aunque Kubecost se centra en las recomendaciones (y puede ejecutar algunas acciones, como aplicar nuevas solicitudes si se le conceden los permisos), al combinarlo con Turbonomic se puede habilitar el cambio de tamaño o la programación automatizados basados en esa información. Esta integración forma parte de la estrategia más amplia « FinOps » (Automatización de la gestión de costes) de IBM, que combina la transparencia de costes de Cloudability, la información sobre contenedores de Kubecost y la automatización de acciones de Turbonomic.

- **Presupuestos y alertas en Adv Containers:** además de la función de presupuestación de Cloudability, Advanced Containers permite configurar **alertas** sobre diversas condiciones a nivel de Kubernetes. Por ejemplo, puede establecer un presupuesto mensual para un espacio de nombres o un equipo, y Advanced Containers puede enviar una alerta (por correo electrónico, Slack, etc.) si el coste previsto superará ese presupuesto Advanced Containers admite tipos de alertas como umbrales presupuestarios, cambios porcentuales en el gasto y alertas de eficiencia para los recursos. Estos se pueden gestionar en la interfaz de usuario de Advanced Containers (sección Alertas). La integración de Cloudability aún no permite crear presupuestos específicos de Kubernetes en la interfaz de usuario de Cloudability, por lo que puede resultar útil utilizar Advanced Containers para obtener alertas presupuestarias detalladas. (La función de presupuesto propia de Cloudability se podía utilizar a nivel de clúster agregado, pero no por espacio de nombres; Advanced Containers llena ese vacío)

**Acceso a la API:**

- Tanto Cloudability como Advanced Containers ofrecen API para recuperar datos sobre costes. La API de Cloudability se puede utilizar para extraer datos de costes combinados (incluidas las asignaciones de contenedores) para su integración con sistemas externos (como CMDB o sistemas de reembolso). Advanced Containers proporciona una API (la API Kubecost) para consultar métricas de costes en tiempo real por agregación (por ejemplo, el coste por etiqueta de los últimos 7 días). En una configuración integrada, puede utilizar la API de Advanced Containers para consultas bajo demanda (ya que es en tiempo real y reside en el clúster) y la API de Cloudability para los informes mensuales oficiales de costes.

Por ejemplo, un ingeniero de plataformas podría consultar la API de contenedores avanzados al final del día para ver el coste de una implementación específica de ese día (para proporcionar una respuesta rápida a los desarrolladores), en lugar de esperar a la actualización de Cloudability del día siguiente. Por otro lado, un analista financiero podría utilizar [la API de](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-essentials/saas?topic=api-containers-end-points "(se abre en una pestaña o una ventana nueva)") Cloudability a final de mes para extraer los costes de contenedores totalmente conciliados (con los descuentos aplicados) e introducirlos en las facturas de devolución.

Para acceder a los puntos finales de la API de contenedores avanzados, necesitará una clave API de Cloudability o un apptio-opentoken para la autenticación. Visite [Introducción a la API de Cloudability V3](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=api-getting-started-cloudability-v3 "(se abre en una pestaña o una ventana nueva)") para obtener más información sobre cómo crear su clave API de Cloudability y generar apptio-opentokens.

Una vez que tenga una clave API de Cloudability o apptio-opentoken, podrá utilizarla para acceder a cualquiera de las API documentadas en [el directorio de API de Kubecost](https://www.ibm.com/docs/en/kubecost/self-hosted/3.x?topic=kubecost-api-directory "(se abre en una pestaña o una ventana nueva)").

Tenga en cuenta **que <kubecost-address>** mencionado en estos puntos finales se sustituirá por < **api.cloudability.com/v3/kubecost** >.

Ejemplo de comando utilizando la clave API:

```
curl 'https://api.cloudability.com/v3/kubecost/model/allocation?window=3d&offset=20&limit=10&accumulate=true' -u '<your_api_key>:'
```

El mismo ejemplo utilizando apptio-opentoken:

```
curl 'https://api.cloudability.com/v3/kubecost/model/allocation?window=3d&offset=20&limit=10&accumulate=true' -H ”apptio-opentoken: <your_apptio-opentoken>” -H “apptio-environmentid: <your_frontdoor_enviornmentId>”
```

**Requisitos previos y compatibilidad**

Antes de habilitar la integración de contenedores avanzados, asegúrese de que su entorno cumple los siguientes requisitos previos y de compatibilidad:

- **Cloudability Datos de cuenta y facturación:** Debe tener una cuenta activa de IBM Cloudability ( SaaS ) con acceso para configurar la función Contenedores. Normalmente, Cloudability ya debería estar configurado con sus **exportaciones de facturación** en la nube:

- **AWS :** un informe de costes y uso (CUR) de AWS configurado y vinculado a Cloudability (normalmente a través de un bucket de S3 ). Esto es necesario para que Cloudability conozca los costes de EC2/EKS, incluidos los costes de los nodos.

- **Azure :** una exportación de Enterprise o Cost Management de Azure, o una conexión API autorizada, para que Cloudability pueda incorporar los detalles de uso de Azure. Esto proporciona un nodo de AKS, VM, los costes, etc.

- **GCP :** una exportación de facturación de BigQuery para GCP vinculada a Cloudability, por lo que están disponibles los costes de GKE y GCE. Además, para GKE, asegúrese de que cada clúster tenga la etiqueta gke-cluster, tal y como se ha descrito anteriormente para la asignación de costes.

- **On-Prem u otro:** Si tiene Kubernetes on-prem, deberá definir manualmente los costes en Advanced Containers (a través de precios personalizados), ya que Cloudability no tendrá una fuente de facturación nativa. Cloudability Aún puede mostrar esos costes si el agente los carga, pero tenga en cuenta que funciones como la amortización o el coste ajustado no se aplican (ya que son específicas de la nube). Es principalmente por motivos de visibilidad.

*Por qué es importante:* Cloudability utiliza los datos de facturación en la nube como fuente fiable de información sobre los costes. El agente FinOps vinculará las métricas de Kubernetes a esas partidas de facturación. Si Cloudability no dispone de los datos de facturación, obtendrá información incompleta sobre los costes. Asegúrese de que sus integraciones en la nube en Cloudability estén actualizadas e incluyan etiquetas/etiquetas de recursos donde sea necesario (especialmente para AWS y GCP, ya que dependen de etiquetas/etiquetas para identificar clústeres).

- *IBM FinOps Agente:* se requiere la versión 1.0.0 o posterior del agente (se incluye con Kubecost 3.0 + o como gráfico independiente).

- *Cloudability SaaS :* Asegúrate de que estás en la última versión de Cloudability (el servicio se actualiza continuamente por IBM ). Las mejoras de Container Insights 2.0 (que utiliza esta integración) se introdujeron en 2024, por lo que cualquier entorno Cloudability posterior a esa fecha es compatible. No hay ningún «número de versión» en SaaS,, pero su representante puede confirmar si la función **Contenedores 2.0** está habilitada.

**Kubernetes Versión del clúster:** Se recomienda Kubernetes **v1.29 o superior**. Kubecost 3.0 apoya oficialmente a K8s 1.29 a través de 1.34. Clústeres que ejecutan versiones anteriores (por ejemplo, 1.21, 1.22, etc.) puede seguir funcionando con el agente, pero no se ha probado exhaustivamente con el nuevo agente. Si tienes clústeres muy antiguos, actualízalos si es posible o consulta IBM. El Kubecost de código abierto tenía matrices de compatibilidad y es posible que tengas que utilizar una versión anterior de Kubecost con integración limitada. Asegúrese también de que sus clústeres tengan instalado el *servidor de métricas* Kubernetes (la mayoría de los K8s gestionados lo tienen); es necesario para las métricas de uso si no se utiliza Prometheus.

- **Helm y herramientas CLI:** Necesitarás Helm 3.x para instalar el agente en cada clúster. También debe tener acceso kubectl a sus clústeres (con privilegios de administrador) para realizar la instalación. Si utiliza ArgoCD o GitOps,, puede incluir la versión Helm del agente FinOps en su configuración; solo asegúrese de que los secretos (claves API) se gestionen adecuadamente.

- **Requisitos de recursos:** El agente de control de rendimiento de Oracle ( FinOps ) es ligero, pero planifique su uso de recursos en cada clúster:

- **CPU/Memoria:**

- **Almacenamiento persistente:** espacio en disco de ~8Gi (predeterminado) para el almacenamiento en caché local. Si su clúster genera un volumen muy alto de métricas (muchos pods fluctuando), supervise este uso; puede aumentar el tamaño del PVC si es necesario.

- **Red:** El agente transmitirá datos a la nube (el tamaño de los datos no es muy grande, normalmente decenas de MB al día por clúster, dependiendo de la actividad). Asegúrese de que este tráfico saliente esté permitido y se tenga en cuenta en sus políticas de salida de red. Si utiliza un proxy, configure las variables de entorno HTTPS\_PROXY para el pod del agente, de modo que pueda enrutar el tráfico correctamente.

- **Seguridad y acceso:** La integración afecta a datos confidenciales sobre costes, por lo que hay que tener en cuenta lo siguiente:

- **RBAC:** El RBAC del agente ( Kubernetes ) es de solo lectura (además de la capacidad de crear sus propios recursos). **No** tiene derechos para modificar las configuraciones de la carga de trabajo (a menos que habilites específicamente las funciones de Kubecost para actuar en el clúster). Revise las funciones que crea si le preocupa. Necesita acceso a recursos como Pods, Nodos, Espacios de nombres, PV, etc y métricas de la API de métricas. También puede utilizar métricas a nivel de clúster (estadísticas de cAdvisor ); en tal caso, accede a ellas a través de la API K8s o kubelet. Asegúrese de que las políticas de seguridad de su clúster (PSP, etc.) permitir que el agente funcione. El contenedor del agente se ejecuta como no root.

- **Claves API:** Trate la clave API de Frontdoor como si fuera una contraseña. Asigna solo los roles mínimos (el rol CloudabilityContainerUploader tal y como se describe). En la configuración de acceso de Cloudability, puede crear un *entorno* independiente para estas cargas de contenedores. Si la clave se ve comprometida, un atacante podría subir datos maliciosos o acceder a determinadas API, por lo que es importante protegerla y cambiarla si es necesario. Cloudability registra el origen de las cargas; el uso de una cuenta de servicio distinta ayuda a realizar un seguimiento de la actividad.

- **Data Privacy :** El diseño de Kubecost consiste en que los datos de costes se calculan localmente: el agente FinOps exporta metadatos y el uso de recursos. No se transmite ninguna carga útil de la aplicación ni datos de clientes, solo información relacionada con los costes. La adquisición de Kubecost por parte de IBM significa que el producto cumple con los estándares de gestión de datos empresariales. Si es necesario, puede obtener una lista con los datos exactos que se envían (por lo general: ID de clústeres, ID de recursos, cantidades de uso, cifras de costes, etc.). Todas las transmisiones están encriptadas ( HTTPS ). No se envían datos a la nube de Kubecost (a menos que utilices su SaaS ); por defecto, solo se envían al almacenamiento de tu instancia de Cloudability y (si se trata de un Kubecost autohospedado) al almacenamiento que hayas configurado.

- **Requisitos de red:** Como se ha mencionado, el clúster debe permitir la salida a puntos finales específicos:

- **Apptio Frontdoor** ( [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(se abre en una pestaña o una ventana nueva)") o variantes regionales como frontdoor-eu.apptio.com para la UE): se utiliza para la autenticación de agentes y la validación de claves API.

- **Cloudability API** ( [https://api.cloudability.com](https://api.cloudability.com/ "(se abre en una pestaña o una ventana nueva)") o dominio regional): se utiliza para cargar datos y cualquier interacción con la API.

- **Apptio Almacenamiento ( S3 )** : el agente subirá los archivos a un depósito de S3 gestionado por Apptio. El nombre del bucket varía según el entorno (comienza por apptio); puede verlo en los registros del agente. Debe permitir \*.s3.amazonaws.com o, más concretamente, el punto final del bucket apptio-<algo> para las operaciones PUT de HTTPS. Si su organización restringe el acceso S3 por bucket, solicite al servicio de asistencia de Apptio el nombre exacto del bucket para su región.

- Si su entorno utiliza un proxy web para el tráfico saliente, configure las variables de entorno del agente en consecuencia (el gráfico Helm puede pasar la configuración del proxy). Si utiliza una VPC privada sin Internet, es posible que tenga que enrutar el tráfico a través de una puerta de enlace NAT o una VPN a los puntos de conexión de Apptio.

- **Container Registry (Configuración de la red):** Permita el acceso a icr.io ( IBM Cloud Container Registry ) para que se pueda extraer la imagen del agente. Si utiliza un espejo de registro interno, puede descargar previamente la imagen icr.io/ibm-finops/agent: <versión> y alojarla internamente.

Al comprobar todos los requisitos previos anteriores, te prepararás para una integración fluida. Es recomendable realizar una pequeña prueba piloto (integrar primero un clúster que no sea de producción y verificar los datos) antes de implementarlo en todos los clústeres.

Resolución de problemas

¿Tienes problemas con la integración? A continuación se indican los problemas más comunes y los pasos para solucionarlos:

- **No aparecen datos en « Cloudability » (** Coste de contenedores): Si después de más de 24 horas no ve ningún dato sobre el coste de los contenedores:

- Verifique que el **pod del agente se esté ejecutando** en el clúster (kubectl get pods -n kubecost). Si es CrashLooping o no está presente, describa el pod para ver los mensajes de error. Las causas más comunes son permisos insuficientes o la imposibilidad de acceder a los puntos finales Cloudability.

- Comprueba los **registros** del agente (kubectl logs -n kubecost deploy/kubecost-finops-agent) en busca de errores. Busca mensajes sobre errores en las subidas o en la autenticación. Por ejemplo, un error 403 de HTTP podría indicar una clave API no válida o un rol incorrecto (comprueba que la clave tiene el rol CloudabilityContainerUploader y que no se ha copiado incorrectamente). Un tiempo de espera de red podría indicar que no puede alcanzar los puntos finales de la API (compruebe su firewall de salida/DNS).

- Asegúrate de que tu **clave API** de Cloudability y tu ID de entorno sean correctos. Si ha generado una clave en Apptio Frontdoor, asegúrese de haber utilizado el entorno correcto (algunos clientes tienen varios entornos Apptio; asegúrese de haber utilizado el que corresponde a su instancia Cloudability ).

- Para los clústeres de GCP GKE, asegúrese de haber completado el paso **de etiquetado de clústeres y asignación de etiquetas**. Si lo ha olvidado, es posible que Cloudability no vincule el uso a ningún clúster (especialmente si ve datos en los registros del agente, pero la interfaz de usuario de Cloudability sigue vacía, esta asignación podría ser el problema). Añade la etiqueta y espera a que se realice una nueva exportación de facturación (puede tardar entre 1 y 2 días para GCP ).

- Comprueba que tus **datos de facturación** en la nube estén actualizados en Cloudability. Si el CUR o la exportación no se actualizan (o no se configuraron antes de implementar el agente), Cloudability podría descartar los datos. Para AWS CUR, asegúrate de que se entrega a diario y de que Cloudability ha incorporado los archivos más recientes.

- Si el clúster utiliza un **proxy**, asegúrese de que el agente lo esté utilizando realmente. Puede ejecutar el pod e intentar un curl a api.cloudability.com para ver si se conecta. Si no es así, configure las variables de entorno HTTP\_PROXY/HTTPS\_PROXY en la implementación.

- Por último, intente volver a implementar el agente con la depuración habilitada (si está disponible en los valores) o póngase en contacto con el servicio de asistencia de Apptio / IBM. El equipo de asistencia de Cloudability puede comprobar por su parte si se ha recibido algún dato o si ha habido problemas de formato.

- **Datos incorrectos o incompletos:** si ves datos pero parecen incorrectos (por ejemplo, falta el coste de un espacio de nombres conocido o es cero):

- Confirma que el espacio de nombres no se haya filtrado. Cloudability De forma predeterminada, puede ocultar los espacios de nombres del sistema (como kube-system) de las vistas de asignación, a menos que elija mostrar los costes compartidos. Comprueba la configuración del filtro.

- Si los costes de almacenamiento o red aparecen como 0 $, confirme que esos costes figuran en su factura de la nube (por ejemplo, que los volúmenes de EBS estén etiquetados correctamente para atribuirlos al clúster). Kubecost puede asignar los costes de salida de red si se configura, pero Cloudability requiere los datos de facturación de la red (para AWS, asegúrese de que los costes de VPC Flow Logs o Data Transfer estén etiquetados o, al menos, asignados).

- Para clústeres locales, si los costes aparecen como 0 $, significa que no ha establecido precios personalizados en Kubecost. Actualice la configuración de precios personalizados (a través de la interfaz de usuario de Kubecost o ConfigMap ) con sus costes por nodo para que el agente pueda informar de valores significativos.

- Si el coste de inactividad parece anormalmente alto, significa que la mayoría de tus solicitudes de recursos son bajas. Esto podría ser correcto (el clúster está prácticamente inactivo) o una señal de que tus solicitudes/límites en Kubernetes no están configurados correctamente (los pods que se ejecutan en BestEffort QoS siempre contarán como uso == solicitud, lo que puede sesgar la asignación). Revise las reglas de « QoS »: Cloudability utiliza solicitudes para pods garantizados y max(Uso, Solicitud) para pods burstables. Por lo tanto, si los equipos no solicitan recursos, es posible que se contabilice el uso, lo que, si es bajo, conduce a una clasificación más «inactiva». Se trata más bien de un problema de ajuste; puede establecer una política según la cual todas las cargas de trabajo deben tener solicitudes/límites.

- En la interfaz de usuario de Kubecost, puede consultar la página **Diagnósticos**. Kubecost 3.0 introdujo una alerta de estado que notifica si falta algún dato o si hay algún problema de integración. Si Kubecost muestra una alerta como «Faltan datos de facturación en la nube» o «No se pueden conciliar los costes», eso puede darte una pista sobre posibles problemas (como la falta de permisos para obtener precios, etc.). Muchas de esas cuestiones también podrían afectar a Cloudability. Utiliza el diagnóstico de Kubecost como una comprobación rápida (dado que se ejecuta localmente, es posible que muestre datos incluso si Cloudability aún no lo hace).

- Si la interfaz de usuario de Cloudability muestra el clúster, pero indica «No hay datos de costes para el periodo seleccionado», asegúrese de que el intervalo de tiempo es correcto (por ejemplo, después del inicio de la integración) y de que se ha producido un uso. Confirma también que el agente sigue funcionando: si alguien lo ha eliminado o se ha bloqueado hace una semana, solo verás los datos históricos hasta ese momento.

- **Rendimiento del agente o del pod de Kubecost:** Si observa que el agente o los pods de Kubecost consumen demasiada CPU/memoria:

- Comprueba si el agente está sobrecargado por instantáneas demasiado frecuentes. El intervalo predeterminado suele ser de unos pocos minutos, pero se puede ajustar si es necesario (hay un valor Helm para el intervalo de instantáneas). Para clústeres extremadamente grandes, considere aumentar el intervalo para reducir la carga (con la contrapartida de datos ligeramente menos granulares).

- Asegúrese de que el agente no compita con otros agentes de supervisión (si todavía tiene un Prometheus que recopila datos similares, podría duplicar la carga de la API). Es mejor desactivar cualquier recopilación de costes heredados una vez que se esté ejecutando un agent FinOps.

- El frontend y el agregador de Kubecost (si los ha implementado) pueden necesitar más recursos para entornos grandes. Supervise su uso de recursos y amplíe la CPU/memoria o habilite el modo multirréplica para la API si es necesario. Kubecost 3.x se trasladó a ClickHouse para agilizar las consultas y mejorar el escalado, pero las consultas intensivas de datos de varios meses pueden seguir siendo muy exigentes. Utilice las funciones Enterprise (si dispone de licencia), como la descarga ETL federada a un ETL centralizado ( ClickHouse ) para escalar a múltiples clústeres.

- **Actualización de componentes:** Si actualiza su versión de Kubernetes o sus cuentas de proveedor de servicios en la nube:

- Tras una actualización de la versión de K8s, el agente debería seguir funcionando (es bastante independiente de la versión, siempre y cuando las API sean estables). Esté atento durante las actualizaciones del clúster; si realiza una actualización in situ, el pod del agente se reiniciará en la nueva versión; compruebe que vuelve a funcionar correctamente.

- Si cambia la configuración del proveedor de servicios en la nube (como los ID de cuenta de AWS o implementa un nuevo depósito CUR, etc.), Actualiza la configuración de Cloudability según corresponda. El agente en sí no necesita cambios, pero Cloudability debe tener continuidad en los datos de facturación para alinear los costes.

- Cuando se publiquen nuevas versiones del **agente** IBM FinOps, planifique actualizar la versión Helm. Consulte las notas de la versión en IBM / Apptio para conocer las mejoras o correcciones de errores (por ejemplo, una futura versión de v1.1 podría reducir los errores de cálculo en reposo, etc.). La actualización del agente se realiza normalmente ejecutando helm upgrade con la nueva versión del gráfico. Esto debería realizarse sin problemas (se reiniciará el pod). Si es posible, hazlo primero en un clúster de prueba.

- Actualización **de Kubecost** : Si ha implementado Kubecost, siga su guía de actualización. Pasar de 2.x a 3.x supone un cambio importante (con la migración a la nueva arquitectura). Asegúrese de realizar una copia de seguridad de cualquier volumen persistente (datos de ClickHouse ) si procede. Después de la actualización, comprueba que el agente FinOps esté activo (en Kubecost 3.x, está habilitado de forma predeterminada; puedes deshabilitar Prometheus, ya que ya no es necesario). La interfaz de usuario de Kubecost debería mostrar los datos como antes.

- **Obtener ayuda:** Si los problemas persisten, utilice los canales de asistencia:

- **IBM Soporte técnico:** Dado que Cloudability y Kubecost son productos de IBM, puede abrir un caso de soporte técnico. Proporcióneles su ID de entorno de Cloudability, su ID de clúster y el periodo de tiempo en el que se produjo el problema. El equipo de soporte puede comprobar los registros del backend. Es posible que soliciten registros de agentes o diagnósticos de Kubecost.

- **Comunidad y documentación:** La comunidad Slack o los foros de Kubecost ( OpenCost, código abierto) pueden ser útiles para preguntas generales sobre anomalías en los costes. Los documentos oficiales ( IBM Docs para Kubecost, Cloudability Knowledge Center) contienen más consejos; por ejemplo, los documentos de Cloudability tienen una página sobre cómo verificar la conexión del agente del contenedor.

- **Herramientas de diagnóstico:** Cloudability no tiene una interfaz de usuario directa para el estado del agente, pero puede utilizar el diagnóstico multiclúster de Kubecost si tiene varios clústeres. Kubecost Enterprise tiene una página de «Diagnóstico multiclúster» para ver el estado de todos los clústeres. Esto puede indicar si el agente de un clúster no está enviando datos.

En resumen, la mayoría de los problemas se deben a errores de configuración (claves API, permisos o datos de facturación faltantes) o limitaciones del entorno (red, versiones antiguas del clúster). Una vez configurada correctamente, la integración suele requerir poco mantenimiento. El agente está diseñado para recuperarse de fallos (utilizando el PVC para almacenar datos en el búfer hasta que se restablezca la conectividad), por lo que las interrupciones breves no deberían provocar la pérdida de datos. Mantener el software actualizado y supervisar su estado mediante alertas garantizará un funcionamiento fluido.

Rendimiento y escala

Esta integración está diseñada para adaptarse a entornos empresariales de gran tamaño. Tanto Kubecost como Cloudability han realizado mejoras para gestionar grandes volúmenes de datos:

- **Agente ligero y escalable:** El agente IBM FinOps tiene un tamaño reducido. Al eliminar la dependencia de los contenedores de código compartido ( Prometheus ) dentro del clúster y ejecutarse como un pod de un solo contenedor, se reduce significativamente la sobrecarga. Se reduce el uso de memoria y se mejora el rendimiento. Cada módulo se centra en la recopilación de datos y las exportaciones periódicas por lotes, lo cual resulta eficiente. El diseño modular de la arquitectura (con emisores independientes) permite activar o desactivar las salidas según sea necesario sin afectar a la recopilación de datos básicos. Si tienes cientos de clústeres, simplemente ejecuta un agente por clúster. Los agentes trabajan en paralelo, escalando horizontalmente. Los datos se agregan en Cloudability, que se basa en un backend de big data capaz de ingestar millones de puntos de datos de costes.

- **Cloudability Escala del backend:** IBM Cloudability ( Apptio ) ha demostrado su capacidad para gestionar entornos cloud de gran tamaño (lo utilizan muchas empresas de la lista Fortune 500 para gastos cloud de decenas de millones). Los datos sobre el coste de los contenedores son solo otro flujo de datos más. El backend de Container Insights almacena muestras de uso de sus clústeres y las fusiona con los datos de facturación. Existen límites (por ejemplo, los datos de frecuencia extremadamente alta se acumularán por horas en los informes), pero el uso típico de Kubernetes (incluso miles de pods) se gestiona mediante un procesamiento diario. Si integra, por ejemplo, 50 clústeres, Cloudability procesará diariamente los archivos subidos de cada clúster. El tiempo de procesamiento puede aumentar ligeramente, pero se encuentra dentro de lo normal. Gartner ha reconocido a Cloudability como líder en herramientas de gestión de proyectos ( FinOps ), en parte debido a su escalabilidad en entornos multicloud y multiequipo.

- **Rendimiento de Kubecost:** Kubecost 3.0 introdujo un motor de consulta más rápido utilizando ClickHouse,, lo que mejora drásticamente la velocidad de obtención de datos de asignación y activos. Las pruebas mostraron mejoras significativas en la velocidad de las consultas de costes en entornos grandes. Por lo tanto, si tiene implementada la interfaz de usuario de Kubecost para analizar meses de datos, debería poder gestionarlos mejor que las versiones anteriores. La arquitectura de Kubecost admite **la federación** para la escalabilidad: puede designar un clúster como el agregador principal que almacena los datos de todos los demás. En este tipo de configuraciones, cada agente envía datos a un almacenamiento de objetos central ( S3, etc.) y el agregador Kubecost lee desde allí. Esto permite un escalado prácticamente ilimitado del número de clústeres, ya que la carga de cada agente es solo su propio clúster y el agregador se encarga del trabajo pesado de las consultas. Las empresas con más de 100 clústeres utilizan este modelo.

- **Resiliencia:** El nuevo diseño del agente (un único contenedor por pod) mejora la resiliencia y la capacidad de depuración. Es más fácil reiniciar o ampliar los componentes si es necesario. El agente utiliza un PVC para recuperarse de las interrupciones, como se ha mencionado, lo que mejora la fiabilidad en condiciones de red inestables. El mecanismo de carga de Cloudability es idempotente: si falla una carga, el agente volverá a intentarlo y Cloudability no contará dos veces los datos, ya que los clasifica por marca de tiempo y clúster.

- **Intervalo de optimización:** De forma predeterminada, el agente puede recopilar datos cada minuto (configurable). En la mayoría de los casos esto está bien, ya que los datos se agregarán por hora/día en Cloudability de todos modos. Si observa que el agente está utilizando demasiada CPU en clústeres grandes, puede reducir la frecuencia de recopilación a, por ejemplo, cada 5 minutos. Esto seguirá capturando datos granulares, pero con menos sobrecarga. Por el contrario, si necesita más datos en tiempo real en Kubecost, puede mantenerlo en 1 minuto o incluso en 30 segundos, pero tenga en cuenta que Cloudability seguirá utilizando principalmente los datos acumulados diariamente (la interfaz de usuario de Kubecost se beneficiaría más de un intervalo más corto).

- **Consideraciones sobre clústeres grandes:** para clústeres con miles de nodos o decenas de miles de pods:

- Asegúrese de que etcd y el servidor API puedan gestionar las llamadas de lista/vigilancia del agente. El agente es eficiente en la extracción de datos (similar a lo que hace un servidor de métricas o un agente de métricas). Si su clúster se encuentra en los límites de etcd, considere segmentar la carga de trabajo o utilizar varios agentes (actualmente no es necesario para un clúster, un agente debería ser suficiente, pero en teoría podría implementar varios en modo de solo lectura para dividir el trabajo).

- El volumen de métricas puede ser elevado. El agente de FinOps se centra en las métricas básicas (CPU, memoria, almacenamiento, uso de la red) relevantes para el coste. No está extrayendo todas las métricas de Prometheus. Por lo tanto, incluso los clústeres grandes deben tener tamaños de datos manejables. Para contextualizar, el código abierto de Kubecost podía gestionar ~10k pods por clúster con Prometheus. El nuevo agente está más optimizado, por lo que se espera una escala similar o mejor. IBM Probablemente probado con grandes clústeres RedHat OpenShift como parte de la ampliación de la supervisión OpenShift.

- **Escala multiclúster:** a medida que añadas más clústeres, supervisa **el rendimiento de los análisis de costes** de Cloudability. En la interfaz de usuario de Cloudability, si ejecuta un informe en 50 clústeres y 2 años de datos con muchas dimensiones, puede resultar pesado; utilice filtros y rangos de tiempo adecuados para que las consultas sean razonables. La API y la interfaz de usuario de Cloudability permiten hasta ciertos límites en una sola llamada (por ejemplo, la recuperación de datos para 500 000 filas de asignación podría agotar el tiempo de espera). Por lo general, lo mejor es desglosarlo por mes o por entorno. Estas son las mejores prácticas generales para Cloudability, no específicas para la integración de Kubecost.

- **Alta disponibilidad:** Cloudability es SaaS y está diseñado para ofrecer una alta disponibilidad. Para Kubecost, si necesita alta disponibilidad (HA), puede ejecutar varias réplicas de su API y utilizar un almacenamiento persistente o un sistema de almacenamiento externo ( ClickHouse ) para garantizar la conmutación por error. El agente FinOps en sí mismo no tiene estado, excepto por la caché PVC; por lo general, se puede ejecutar uno por clúster (no se recomienda ejecutar varios simultáneamente en un clúster, ya que duplicarían los datos, a menos que se desactive uno para un emisor Cloudability ). Si el tiempo de actividad es crítico, asegúrese de supervisar el pod del agente mediante un demonio como Prometheus o Kubernetes liveness probes (el gráfico tiene configuradas pruebas de actividad).

En resumen, la integración está **diseñada para empresas de gran tamaño**. Aprovecha las mejoras arquitectónicas de Kubecost 3.0 para minimizar el espacio ocupado y utiliza el maduro procesamiento de big data de Cloudability para gestionar grandes conjuntos de datos de costes. Tanto si tiene un gran clúster como cientos de clústeres, la solución se puede configurar para satisfacer sus necesidades. Solo hay que seguir las mejores prácticas (identificadores únicos, recursos adecuados, supervisión adecuada) y debería escalarse de forma lineal.

Limitaciones

Aunque la integración de Cloudability y Kubecost es muy potente, es importante tener en cuenta sus limitaciones y matices actuales:

- **Sincronización de datos y tiempo:** como se ha señalado, los datos en tiempo real de Kubecost frente a los datos de facturación de Cloudability pueden dar lugar a **diferencias de tiempo**. La integración (todavía) no transmite datos de forma continua y en tiempo real a Cloudability; los datos se cargan periódicamente y se procesan en lotes diarios. Esto significa que los informes de contenedores de Cloudability se actualizan aproximadamente una vez al día. Si necesitas datos actualizados cada hora, utiliza la interfaz de usuario o la API de Kubecost. Cloudability está trabajando para ofrecer actualizaciones más frecuentes, pero por ahora considéralo **casi en tiempo real** (Kubecost) frente a **conciliado financieramente** ( Cloudability ). Tienen fines ligeramente diferentes.

- **Discrepancias en los costes:** Debido a lo anterior, no se garantiza **una alineación perfecta** en todo momento. Pueden existir pequeñas discrepancias (de un pequeño porcentaje) entre las cifras de Kubecost y las de Cloudability para el mismo periodo de tiempo debido a factores como:

- Cloudability incluidos **los costes amortizados** (RI/SP) que Kubecost podría no incluir a menos que se configure.

- Kubecost utiliza **precios estimados** para algunos recursos en tiempo real, que posteriormente se corrigen con los datos de facturación reales. Por ejemplo, si un proveedor de servicios en la nube aplica precios por niveles o descuentos por uso continuado, el cálculo inicial de Kubecost podría diferir hasta que se concilie la factura.

- Momento de la conversión de divisas (si procede) y tasas fiscales o de asistencia: Cloudability puede incluir cargos a nivel de cuenta en el coste total que Kubecost no distribuye.

**Importante:** El objetivo de la integración es lograr una estrecha alineación. Durante un mes completo, debe conciliar los costes asignados por Kubecost con el 100 % de su factura de cloud (Kubecost Enterprise admite la conciliación con exportaciones de facturación para lograrlo). Sin embargo, en el día a día, considere Kubecost como una vista operativa y Cloudability como la vista contable. No esperes que coincidan al centavo todos los días.

- **Compatibilidad con costes locales:** Cloudability no es compatible de forma nativa con los costes locales. La integración cargará todos los datos de costes que Kubecost calcule para los clústeres locales, pero Cloudability podría clasificarlos de forma diferente o no incluirlos en determinadas vistas agregadas (ya que no están vinculados a una cuenta de proveedor de servicios en la nube). Es posible que veas esos grupos en Contenedores con costes, pero no aparecerán en los informes de proveedores de nube. Además, no se aplicarán amortizaciones ni otros cálculos específicos de la nube. Básicamente, lo trata como un coste personalizado. Esto está bien para mostrar, pero no para la contabilidad oficial. Ten cuidado al utilizar datos locales en Cloudability : son tan precisos como los que introduzcas, pero no hay validación externa.

- Cloudability **:** si implementa Kubecost en varios clústeres con un agregador central, tenga en cuenta que sigue tratando cada clúster de forma individual. Cloudability No sabe qué clústeres pertenecen a un grupo ni cuáles son primarios o secundarios. Cualquier federación Kubecost es transparente para Cloudability. Una limitación es que la interfaz de usuario de Cloudability no agrupa los clústeres por federación. Si tienes docenas de clústeres, Cloudability mostrará docenas de entradas de clústeres. Depende de ti agruparlos o filtrarlos (por ejemplo, por convención de nomenclatura). En Cloudability no existe el concepto de «vista combinada» de varios clústeres, salvo mediante la selección múltiple en un filtro. Esto difiere de la interfaz de usuario de Kubecost, donde un agregador puede mostrar una única vista combinada. Solo ten en cuenta esta distinción.

- **Características ausentes en la interfaz de usuario de Cloudability :** No todas las características de Kubecost están disponibles en la interfaz de usuario de Cloudability. Por ejemplo, **alertas y gobernanza de Kubecost** (alertas presupuestarias, etc.) no se pueden configurar desde Cloudability; para ello, debe utilizar la interfaz de Kubecost. Cloudability Se centra en la presentación de informes de costes y cuenta con su propio sistema de alertas de nivel superior (como la detección de anomalías en el gasto total). Del mismo modo, **las recomendaciones de ahorro** en Cloudability podrían no ser tan detalladas como las de Kubecost. Cloudability ofrece recomendaciones sobre el dimensionamiento adecuado para EC2 y algunas sugerencias sobre el dimensionamiento adecuado de contenedores, pero las de Kubecost suelen ser más detalladas específicamente para Kubernetes. Con el tiempo, IBM podría integrar estas funciones más profundamente, pero actualmente se espera utilizar la interfaz de usuario de Kubecost para la optimización detallada y Cloudability principalmente para la visibilidad y el seguimiento de los resultados.

- **Limitaciones de reescritura/automatización:** Actualmente, la integración es **de solo lectura** con respecto a sus clústeres: extrae datos, pero no realiza cambios. Kubecost se puede configurar para realizar acciones (como aplicar nuevas solicitudes de recursos o expulsar pods inactivos), pero estas no se activan a través de Cloudability. Si desea automatizar el proceso, deberá utilizar las API de Kubecost o Turbonomic. El módulo Savings Automation (Automatización del ahorro) de Cloudability cubre aspectos como el redimensionamiento de máquinas virtuales o la compra de RI, pero no acciones de Kubernetes (todavía). Por lo tanto, cualquier optimización identificada deberá implementarse mediante procesos de « DevOps » (mejora continua) o « Turbonomic » (mejora de la calidad). No hay una opción de «aplicar este reajuste» con un solo clic en la vista de contenedores de Cloudability.

- **Entornos múltiples de Cloudability :** si tiene entornos separados de Cloudability (por ejemplo, uno para producción, otro para desarrollo o para diferentes unidades de negocio), tenga en cuenta que los datos de la integración están vinculados a un entorno a través de la clave API y el ID de entorno. Si accidentalmente utiliza el mismo ID de clúster en dos entornos diferentes de Cloudability, esos datos no se fusionarán, sino que quedarán aislados por entorno. Además, debe implementar agentes independientes (o configurar claves API independientes) si desea enviar intencionadamente algunos datos del clúster a un entorno y otros a otro. Este escenario es poco común, pero hay que tenerlo en cuenta al gestionar entornos y claves API.

- **Descontinuación de agentes heredados:** si utilizabas el antiguo agente contenedor Cloudability (el «agente de métricas» de código abierto de la era 2020), ten en cuenta que se va a descontinuar. El nuevo agente FinOps no es compatible con el formato de datos del agente anterior. No debe ejecutar ambos en el mismo clúster, ya que se producirá un doble recuento o se generarán conflictos. Elimine cualquier agente de métricas antiguo ( DaemonSet/Deployment ) de sus clústeres al pasar a la nueva integración. Esto también significa que algunas funciones heredadas de Cloudability (como ciertos paneles antiguos) podrían ser sustituidas por el nuevo Container Insights. Consulte las notas de migración de IBM, si procede.

- **OpenCost vs Enterprise:** La integración utiliza el modelo « OpenCost » (en el que se basa Kubecost) para el cálculo de costes. El agente FinOps es compatible con OpenCost desde el primer momento. Una limitación a tener en cuenta es que OpenCost (y, por lo tanto, Kubecost Community) no incluye algunas funciones avanzadas como el mapeo empresarial o las fórmulas de reembolso que sí tiene Cloudability. Cloudability permite asignar costes a dimensiones personalizadas (como asignar una etiqueta Kubernetes a un centro de costes corporativo mediante su lógica de etiquetado). Esas asignaciones deben configurarse por separado en Cloudability (por ejemplo, creando una «Asignación empresarial» en Cloudability para asignar nombres de espacios de nombres a nombres de departamentos). La integración no aplicará automáticamente estas asignaciones comerciales a los datos de Kubernetes; deberá configurarlas tal y como lo haría con las etiquetas de la nube.

- **Compatibilidad con plataformas de contenedores no Kubernetes :** esta integración está dirigida específicamente a Kubernetes. Si ejecuta contenedores fuera de K8s (ECS, etc.), Esos se gestionan a través de Cloudability por otros medios (por ejemplo, la asignación de costes ECS a través de AWS CUR). Kubecost no cubre ECS ni otros servicios de contenedores. Por lo tanto, esta integración no es aplicable a entornos no Kubernetes.

- **Cambios futuros:** Se trata de una **nueva integración**, y IBM la está mejorando activamente. Características como más actualizaciones en tiempo real de Cloudability, una mayor integración con Turbonomic o interfaces de usuario unificadas están en la hoja de ruta. Por lo tanto, considere esta versión inicial como la base: consulte siempre las notas de la versión para conocer las nuevas capacidades o la eliminación de limitaciones. Por ejemplo, la compatibilidad con el emisor Turbonomic en el agente está «prevista» (aún no está activa). Cuando eso ocurra, es posible que tengas que actualizar las configuraciones de los agentes para poder aprovecharlo.

- **Problemas conocidos:** En el momento de redactar este documento, consulte la documentación de IBM para conocer los problemas conocidos. Por ejemplo, puede haber casos extremos conocidos como «el coste por terminar pods puede aparecer en 'sin asignar' si no existían al final del periodo» o «si se cambia el ID de un clúster, los datos históricos no se fusionan», etc. Revise siempre los documentos más recientes para consultar estas notas.

En conclusión, hay que tener en cuenta que, aunque la integración mejora considerablemente la gestión de costes de Cloudability Kubernetes, no es una solución milagrosa para todos los casos. Utilice Cloudability y Kubecost conjuntamente para obtener los mejores resultados y comprender la diferencia entre ambos. Siempre que tengas en cuenta estas limitaciones, podrás planificar procesos (por ejemplo, la conciliación de fin de mes con Cloudability o la supervisión diaria con Kubecost) que aprovechen al máximo ambas herramientas sin confusiones.

Siguiendo esta guía, debería poder implementar y utilizar correctamente el módulo Contenedores avanzados de Cloudability. El resultado es una solución potente y completa de gestión de la nube ( FinOps ) que proporciona visibilidad y optimización en toda su huella en la nube, desde los servicios básicos de la nube hasta las aplicaciones en contenedores que se ejecutan en Kubernetes. Esta integración ayuda a salvar la brecha entre las finanzas y la ingeniería, garantizando que todos dispongan de los datos que necesitan para gestionar y optimizar los costes en los entornos híbridos actuales, centrados en la nube y basados en la economía de uso ( Kubernetes ).

**Tema principal:** [Asignación de costes de contenedores](../product/k8s-cost-allocation.html)
