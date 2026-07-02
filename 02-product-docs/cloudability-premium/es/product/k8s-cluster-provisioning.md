---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Kubernetes Configuración de clústeres"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "product/k8s-cluster-provisioning.html"
images:
  - "images/container-ua-1.png"
  - "images/container-ua-12.png"
  - "images/container-ua-13.png"
  - "images/container-ua-14.png"
  - "images/container-ua-15.png"
  - "images/container-ua-16.png"
  - "images/container-ua-2.png"
  - "images/container-ua-3.png"
  - "images/container-ua-4.png"
  - "images/container-ua-5.png"
  - "images/container-ua-6.png"
  - "images/container-ua-7.png"
  - "images/container-ua-8.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Kubernetes Configuración de clústeres

Para recopilar los datos necesarios para realizar la asignación de costes de los contenedores, deberá implementar el *agente* IBM FinOps, el agente de recopilación de datos de última generación para Cloudability Containers. En este documento encontrará referencias relacionadas con un escenario de migración desde el agente de métricas heredado de Cloudability; puede ignorarlas sin problema si está realizando la configuración por primera vez.

Configurar el [agente de IBM FinOps](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md "(se abre en una pestaña o una ventana nueva)") para Cloudability

Esto se consigue mediante un despliegue de HELM aprovisionado para cada clúster. Estos comandos HELM pueden ser generados siguiendo los siguientes pasos:

1. Vaya a **Insights > Contenedores**.
2. Seleccione el botón «**Provision Clusters** ».
3. Rellena el formulario con el nombre de tu clúster y, a continuación, indica si utilizas la versión Kubernetes o la versión *OpenShift*.
4. Haz clic en **«Siguiente» > «Generar comando** ».

Implementar el agente unificado

Requisitos previos:

Google Kubernetes Engine ( GKE ) instrucciones específicas

Debes añadir una [etiqueta de clúster](https://cloud.google.com/kubernetes-engine/docs/how-to/creating-managing-labels "(se abre en una pestaña o una ventana nueva)") en cada clúster de la siguiente manera:

- Legenda: `gke-cluster`
- Valor: El nombre del clúster que ha configurado en Helm como «Cluster Id». Esto permite a Cloudability asignar los clústeres de GKE a las partidas individuales del archivo de facturación de GCP y distribuir los costes entre sus clústeres. Debe ser único en todos los clústeres aprovisionados por GKE.

Cloudability Tendrá que importar un archivo de facturación con las etiquetas del clúster que haya añadido, lo que puede tardar hasta 48 horas. Una vez que Apptio haya procesado el nuevo archivo de facturación, deberá crear una nueva [asignación de etiquetas](build-an-aws-cost-by-tag-report.html) en Cloudability. Establece una dimensión de etiqueta de « Cloudability » como «Nombre del clúster de GKE » y asígnala a la `gke-cluster` etiqueta.

Asegúrate de que tu cuenta tenga el rol de administrador del clúster antes de implementar el agente de métricas. Por defecto, una cuenta de usuario no tiene el rol cluster-admin. Utiliza el siguiente comando en el clúster « GKE » para asignar a un usuario el rol de administrador del clúster:

```
"kubectl create clusterrolebinding username-cluster-admin-binding --
clusterrole=cluster-admin --user=username@emailaddress.com"
```

**Requisitos de red**

El agente unificado necesita acceso de salida a las siguientes ubicaciones:

- Cloudability Puntos de conexión de la API
- Puntos de conexión de la API de Frontdoor
- S3 Depósitos de carga

Para obtener más información sobre la red de salida, consulta el archivo README en GitHub para el agente unificado aquí: [IBM Gráfico del agente « FinOps » Helm](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md "(se abre en una pestaña o una ventana nueva)")

**Requisitos de almacenamiento:**

El agente de IBM FinOps requiere una solicitud de volumen persistente configurable (por defecto, 8Gi ). Este cambio se realizó para reducir la posibilidad de pérdida de datos si/cuando el agente se reprograma. El agente ahora almacena muestras en este volumen e intentará recuperar cualquier muestra después de un reinicio. Esta mejora incrementa enormemente la capacidad del agente para recuperar datos en situaciones de fallo.

**Container Registry cambiar:**

El agente de métricas de IBM FinOps no se almacena en Docker, a diferencia del agente de métricas existente. En su lugar, el agente de IBM FinOps se almacena en ICR. Por lo tanto, es posible que tengas que actualizar la lista de permitidos de tu registro de contenedores para que la implementación del agente de IBM FinOps pueda descargar la imagen ICR. El registro de contenedores de IBM FinOps Agent es:

```
icr.io/ibm-finops/agent:vx.x.x
```

Si necesita extraer la imagen localmente para copiarla en el registro de su contenedor. Puede ejecutar el siguiente comando docker/podman pull:

```
 podman pull icr.io/ibm-finops/agent:v0.0.25 --platform=linux/amd64
```

**Autentificación:**

Es importante señalar que el agente de métricas heredado de Cloudability utilizaba una clave API específica para contenedores. El agente de IBM FinOps **dejará** de utilizar y de admitir esta clave API. En su lugar, los clientes deben crear una **clave API** para el agente en Frontdoor y reunir su **ID de entorno** de Frontdoor.

**Creación de usuario para gestionar la clave API del contenedor:**

Es necesario que en tu entorno de Frontdoor estén habilitadas las claves API para que funcione la función Container Insights

Se recomienda a los clientes que creen una «cuenta de servicio» específica para el contenedor dentro de su propio dominio para gestionar su clave API en el futuro. De esta forma, la clave API de subida no queda vinculada a un usuario concreto que pudiera desactivarse en el futuro. La persona que cree el nuevo usuario y la clave API debe ser un usuario administrador en su entorno de Frontdoor.

1. Vaya a "Asistente de acceso" en "Administración de acceso", seleccione "Añadir usuario(s)", configure "Cliente" y "Entorno". Por último, pulse "Confirmar"

   ![](../../../../03-media/cloudability-premium/images/container-ua-1.png)
2. Introduzca los datos del usuario y pulse "Siguiente"

   ![](../../../../03-media/cloudability-premium/images/container-ua-2.png)
3. Seleccione "Conceder función(es)", "No enviar al usuario un correo electrónico de activación" y pulse "Confirmar" para crear el usuario

   ![](../../../../03-media/cloudability-premium/images/container-ua-3.png)
4. Asegúrese de que el usuario está seleccionado para la concesión de funciones

   ![](../../../../03-media/cloudability-premium/images/container-ua-4.png)
5. Conceda la función “CloudabilityContainerUploader” al usuario y pulse "Siguiente"/"Confirmar".

   ![](../../../../03-media/cloudability-premium/images/container-ua-5.png)
6. Vaya a "Inicio", busque el usuario recién creado y haga clic en su "Nombre de usuario"

   ![](../../../../03-media/cloudability-premium/images/container-ua-6.png)
7. Pulse "Ver perfil de usuario"

   ![](../../../../03-media/cloudability-premium/images/container-ua-7.png)
8. Añadir una clave API para el usuario

   ![](../../../../03-media/cloudability-premium/images/container-ua-8.png)
9. Introduzca un nombre para la clave API (por ejemplo: IBM -Finops-agent), configure "Sin caducidad" si no está ya configurado, y pulse confirmar.
10. Almacene las credenciales de la clave API (**clave pública** y **clave privada** ) para utilizarlas posteriormente en la instalación en timón del agente.
11. Pulsa "Conceder acceso"
12. Seleccione su entorno y pulse "Siguiente"

    ![](../../../../03-media/cloudability-premium/images/container-ua-12.png)
13. Añade el rol “CloudabilityContainerUploader” a la clave y pulsa "Siguiente". Esta función tiene acceso limitado al punto final de carga de contenedores.

    ![](../../../../03-media/cloudability-premium/images/container-ua-13.png)
14. Compruebe que su clave se ha creado y tiene la función correcta

    ![](../../../../03-media/cloudability-premium/images/container-ua-14.png)

**Identificación del entorno de la puerta de entrada**

1. Navegar hasta la puerta de entrada
2. En la parte superior derecha, seleccione el logotipo Perfil y haga clic en "Cuenta de usuario"

   ![](../../../../03-media/cloudability-premium/images/container-ua-15.png)
3. Vaya a la pestaña Acceso al entorno
4. Recoge el ID del entorno en la pestaña Entorno de la tabla

   1. Asegurarse de que el entorno es el mismo que el que se utiliza para acceder Cloudability

      ![](../../../../03-media/cloudability-premium/images/container-ua-16.png)
   2. Formato de identificación de ejemplo: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

Implementación del agente de métricas con Helm

Requisitos previos:

- Instalación: para poder utilizar los gráficos, es necesario tener instalado « [Helm](https://www.ibm.com/links?url=https%3A%2F%2Fhelm.sh%2F "(se abre en una pestaña o una ventana nueva)") ». Consulta [la documentación](https://www.ibm.com/links?url=https://helm.sh/docs/ "(se abre en una pestaña o una ventana nueva)") de « Helm » para empezar.
- Actualizar las políticas de red del clúster para permitir nuevos requisitos de red (si es necesario)
- Recopilar claves públicas y privadas de la API
- Recopilar el ID de entorno de la puerta de entrada

Importante:

Recomendamos encarecidamente utilizar un nombre de clúster `clusterId` único para cada clúster de Kubernetes. El uso de nombres duplicados puede provocar discrepancias en los datos o una asignación de costes inexacta en los informes de « Cloudability ».

Una vez que Helm se haya configurado correctamente, añada el repositorio como se indica a continuación:

```
helm repo add ibm-finops https://kubecost.github.io/finops-agent-chart
```

Si ya había añadido este repositorio anteriormente, actualícelo:

```
helm repo update
```

Instale Helm Repo

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey="<PublicKey>" \
--set agent.cloudability.secret.cloudabilitySecretKey="<PrivateKey>" \
--set agent.cloudability.secret.cloudabilityEnvId="<FDEnvID>" \
--set clusterId="<ClusterName>" \
--create-namespace -n ibm-finops-agent
```

Para desinstalar Helm Repo:

```
helm uninstall ibm-finops-agent
```

Si tu clúster está ejecutando actualmente el antiguo agente de métricas Cloudability, puedes dejarlo en funcionamiento hasta que compruebes que el nuevo agente IBM FinOps lleva 24 horas subiendo datos correctamente. El agente IBM FinOps se puede instalar y ejecutar en paralelo al agente de métricas Cloudability, pero se recomienda desactivar el agente de métricas Cloudability una vez que el nuevo agente funcione de forma estable en el clúster.

**UploadRegion** depende de la región en la que se encuentre el entorno Cloudability del cliente. Los valores admitidos son los siguientes

- US: nosotros (o us-west-2 )
- UE: eu (o eu-central-1 )
- AU: au (o ap-southeast-2 )
- ME: yo (o me-central-1 )
- CA: ca (o ca-central-1 )
- Hybrid EU *(clientes que tienen puerta de entrada en la UE pero cargan los datos de los contenedores en la región de EE.UU.)* : hybrid-eu
- AU híbrida *(clientes que tienen puerta de entrada AU pero cargan los datos de los contenedores en la región de EE.UU.):* hybrid-au
- ME híbrido *(clientes que tienen ME frontdoor pero cargan los datos de los contenedores en la región de EE.UU.)* : hybrid-me

El nombre `clusterId` del clúster debe ser único y, si ya ha sido configurado por el agente de métricas heredado, debe coincidir con el nombre del clúster `CLOUDABILITY_CLUSTER_NAME` **para evitar problemas en la importación de datos de costes**.

Nota:

El agente unificado admite muchas de las mismas configuraciones que el agente de métricas salientes Cloudability. Si tu agente de métricas actual tiene alguna configuración específica **(por ejemplo, configuraciones de PROXY)**, consulta [aquí](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md#:~:text=%22%22-,Agent%20Configuration,-Name "(se abre en una pestaña o una ventana nueva)") los parámetros compatibles con Helm.

Puede añadirlas a su comando de instalación, por ejemplo:

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey="<PublicKey>" \
--set agent.cloudability.secret.cloudabilitySecretKey="<PrivateKey>" \
--set agent.cloudability.secret.cloudabilityEnvId="<FDEnvID>" \
--set agent.cloudability.outboundProxy="http://x.x.x.x:8080" \
--set agent.cloudability.parseMetricsData="true"
--set clusterId="<ClusterName>" \
--create-namespace -n ibm-finops-agent
```

1. Asegúrese de que el pod ibm-finops-agent se está ejecutando

   ```
   kubectl get pods -n ibm-finops-agent

   ### Example Output Below ###
   NAME                                READY   STATUS    RESTARTS   AGE
   ibm-finops-agent-7bbf99d9fb-kmhh9   1/1     Running   0          1m
   ```
2. Compruebe los registros de los pods para confirmar que el agente está cargando correctamente los datos en Cloudability. **Tardará 10 minutos en ver el primer registro de carga con éxito.**

   ```
   kubectl logs <POD_NAME> -n ibm-finops-agent

   ### Example Output Below ###
   INF Starting IBM Finops Agent...
   DBG HTTP server started on port 9003
   INF Initializing cldy emitter
   INF emitting sample to Cldy 0
   INF added sample to Cldy
   INF emitting sample to Cldy 1
   INF added sample to Cldy
   INF emitting sample to Cldy 2
   INF added sample to Cldy
   INF Attempt 1: performing login request to FrontDoor using KeyAccess and KeySecret
   INF Attempt 1: acquiring presigned URL from Cloudability with acquired Open-token
   INF Attempt 1: uploading sample to Cloudability S3 using presigned URL
   INF successfully uploaded metric sample xxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_xxxx-xx-xx-xx-xx-xx.tgz to cloudability
   ```

**Una vez más, pasarán 10 minutos hasta que aparezca el registro "successfully uploaded metric sample to cloudability". Este es un punto de fallo común en los agentes si no tienen activada la configuración correcta de listas blancas/proxy.**

Una vez transcurridas 24 horas desde que el agente de IBM FinOps se puso en marcha y completó la carga con éxito. Si todavía tienes en funcionamiento una implementación del agente de métricas de Cloudability, ahora puedes desmantelar esa infraestructura y mantener en funcionamiento únicamente el gráfico Helm del agente de IBM FinOps.

Nota:

Los datos del clúster deberían aparecer en Container Insights en un plazo de 24 a 48 horas. Si tienes algún problema con la implementación, ponte en contacto con el servicio de asistencia de IBM Apptio.

Configuración de contenedores avanzados de Cloudability

Si has actualizado a [« Cloudability Advanced Containers»](advanced-containers.html), puedes empezar a aprovisionar clústeres fácilmente siguiendo la guía de configuración integrada en el producto, disponible en la **página de aprovisionamiento de agentes** dentro de tu entorno ( [https://api.cloudability.com/v3/kubecost/monitor:clusters:connect](https://api.cloudability.com/v3/kubecost/monitor:clusters:connect "(se abre en una pestaña o una ventana nueva)") ). La guía es válida para nuevas instalaciones, actualizaciones de agentes anteriores y entornos en los que se desconoce el estado actual del agente. Ofrece instrucciones paso a paso para instalar el agente, comprobar la conectividad y verificar que la instalación se ha realizado correctamente.

Durante la configuración, la guía configura los dos emisores necesarios: el emisor de Container Insights, que mantiene los informes existentes de los contenedores de Cloudability, y el emisor de Advanced Containers, que permite la asignación de costes de Kubernetes, las recomendaciones de optimización y funciones de generación de informes adicionales. Tras la instalación, es posible que los datos del clúster tarden varios minutos en aparecer en « Cloudability : Advanced Containers».

- **[Aprovisionamiento de clústeres para la optimización de contenedores](../product/k8s-cluster-provisioning-premium.html)**
