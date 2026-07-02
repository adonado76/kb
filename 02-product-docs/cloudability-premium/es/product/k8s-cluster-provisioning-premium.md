---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Aprovisionamiento de clústeres para la optimización de contenedores"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Kubernetes Configuración de clústeres"
source_path: "product/k8s-cluster-provisioning-premium.html"
images:
  - "images/conatiner-ua-19.png"
  - "images/containers-metrics-agent-provisioning-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Aprovisionamiento de clústeres para la optimización de contenedores

En « Cloudability Premium », para configurar clústeres de « Kubernetes » es necesario instalar **dos agentes independientes** : el **agente « IBM » de « FinOps »** y el **agente «Kubeturbo» (agente de optimización de contenedores)**.

Esta página se centra específicamente en la instalación y configuración del **agente** Kubeturbo (Optimización); si necesitas instalar el *agente « FinOps »* para la asignación de costes, consulta la página sobre [el aprovisionamiento de clústeres](k8s-cluster-provisioning.html) de Kubernetes.

## Despliegue del Agente Kubeturbo

Descargar el script para el agente de optimización de contenedores de Cloudability (Kubeturbo de Turbonomic )

1. Ve a «Insights» > «Contenedores ».
2. Selecciona el botón «Provision Clusters ».
3. Rellene el formulario con el nombre de su clúster y su versión Kubernetes o su versión OpenShift.
4. Selecciona «Generar script del agente» en la sección «Agente de optimización de contenedores ».

![](../../../../03-media/cloudability-premium/images/conatiner-ua-19.png)

*Los siguientes pasos describen el proceso de instalación del agente Kubeturbo una vez descargado el script.*

Añadir espacio de nombres para el clúster

Por defecto, Kubeturbo se despliega en un espacio de nombres llamado turbo. Le recomendamos que mantenga el nombre por defecto. Sin embargo, si desea especificar un nombre personalizado durante la implantación, proporcione un nombre que cumpla los siguientes requisitos:

- Debe comenzar con caracteres alfanuméricos en minúsculas o el símbolo de guión (-), y debe comenzar y terminar con un carácter alfanumérico. Por ejemplo, mi-nombre y 123-abc son nombres válidos.
- Para un clúster de producción, considere no utilizar el espacio de nombres por defecto.
- Evite crear espacios de nombres con el prefijo kube-. Está reservado para los espacios de nombres del sistema Kubernetes.

Configurar la función de clúster

Puede establecer la variable KUBETURBO\_ROLE como turbo-cluster-admin o turbo-cluster-reader.

- El rol «turbo-cluster-admin» especifica los permisos mínimos que Kubeturbo necesita para supervisar tus cargas de trabajo y ejecutar las acciones de optimización generadas por Turbonomic.
- El rol turbo-cluster-reader especifica los permisos mínimos que Kubeturbo necesita para monitorizar únicamente sus cargas de trabajo. Las acciones de optimización generadas por Turbonomic solo pueden ejecutarse de forma externa (por ejemplo, fuera del clúster).

Para obtener más información, consulta [las funciones de clúster de Kubeturbo](https://www.ibm.com/docs/en/tarm/8.16.x?topic=requirements-cluster-roles-kubeturbo "(se abre en una pestaña o una ventana nueva)")

Configurar repositorio privado de imágenes

Cuando se proporcionan KUBETURBO\_REGISTRY\_USRNAME y KUBETURBO\_REGISTRY\_PASSWRD, el script los utilizará para crear un secreto de extracción de imágenes para acceder al repositorio privado y extraer las imágenes necesarias.

KUBETURBO\_REGISTRY especifica el prefijo de su registro privado y repo. Sustituye al prefijo por defecto icr.io/ cpopen en las rutas de las imágenes originales.

- Prefijo original : icr.io/ cpopen
- Prefijo de registro privado : myregistry.mycompany.com/kubeturbo

Nota: Todas las imágenes requeridas deben reflejarse en su registro privado con exactamente las mismas etiquetas que en la fuente original.

Configurar el proxy y las credenciales de registro

Proporcione PROXY\_SERVER y KUBETURBO\_REGISTRY\_PASSWRD como cadenas base64-encoded.

Especifique la siguiente configuración de proxy:

- Nombre de host o dirección IP del proxy : especifique la dirección del proxy utilizado para este objetivo.
- Puerto proxy: Especifique el puerto a utilizar con el proxy utilizado para este objetivo. Por defecto, el puerto es 8080.
- Nombre de usuario del proxy: Especifique el nombre de usuario que se utilizará con el proxy.
- Contraseña del proxy: Especifique la contraseña que se utilizará con el proxy.
- Conectarse mediante HTTPS : Seleccione esta opción si Turbonomic se va a conectar al proxy a través de HTTPS.

Pasos de instalación

Una vez descargado el script, cópialo en la ubicación desde la que quieras ejecutarlo, en un entorno en el que estés conectado al clúster de destino en el que deseas implementar el agente.

Ejecuta el comando siguiendo el ejemplo que se muestra a continuación:

```
chmod +x new-js-aks.sh &&./new-js-aks.sh
```

A continuación se ofrece un resumen de la instalación.

```
Parameter            Value
---------            ---------
Mode                 Create/Update
Kubeconfig           default
Host                 https://20.116.237.9
Namespace            turbo
Target Name          new-js-aks
Target Subtype       Kubernetes
Role                 turbo-cluster-admin
Version              8.14.5
Auto-Update          false
Auto-Logging         false
Proxy Server         false
Private Registry     false
```

Confirme la configuración anterior [S/N]: S

Tu configuración actual de « Kubernetes » está establecida de la siguiente manera.

```
NAME                     CLUSTER                  AUTHINFO                                                NAMESPACE
concise-lobster-aks      concise-lobster-aks      clusterUser_concise-lobster-rg_concise-lobster-aks
```

Confirme si el script debe ejecutarse en el clúster anterior [S/N]: S

```
Creating turbo namespace to deploy Kubeturbo operator
namespace/turbo created
secret/turbonomic-credentials created
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100  159k  100  159k    0     0   920k      0 --:--:-- --:--:-- --:--:--  923k

customresourcedefinition.apiextensions.k8s.io/kubeturbos.charts.helm.k8s.io unchanged
serviceaccount/kubeturbo-operator created
clusterrole.rbac.authorization.k8s.io/kubeturbo-operator unchanged
Skip patching ClusterRoleBinding kubeturbo-operator as the clusterRole has bound to the operator service account already.
deployment.apps/kubeturbo-operator created
namespace/turbo configured
Waiting for deployment 'kubeturbo-operator' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-operator-857855c6b5-d9x2c condition met
apply Kubeturbo CR ...
kubeturbo.charts.helm.k8s.io/kubeturbo-release created
Waiting for deployment 'kubeturbo-release' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-release-7d499cf568-cg5sm condition met
Successfully apply Kubeturbo in turbo namespace!

NAME                                SECRETS   AGE
serviceaccount/kubeturbo-operator   0         32s
serviceaccount/turbo-user           0         12s

NAME                                     READY   STATUS    RESTARTS   AGE
pod/kubeturbo-release-7d499cf568-cg5sm   1/1     Running   0          12s

NAME                                 READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/kubeturbo-operator   1/1     1            1           30s
deployment.apps/kubeturbo-release    1/1     1            1           12s

NAME                                       DATA   AGE
configmap/turbo-config-kubeturbo-release   2      12s
Done!
```

Ejecuta el siguiente comando para comprobar que los dos pods están en funcionamiento, tal y como se muestra en el ejemplo siguiente:

```
kubectl get pods -n turbo
```

```
NAME                                  READY   STATUS    RESTARTS   AGE 
kubeturbo-operator-857855c6b5-d9x2c   1/1     Running   0          105s 
kubeturbo-release-7d499cf568-cg5sm    1/1     Running   0          87s
```

La siguiente imagen muestra la instalación.

![Captura de pantalla de la instalación de Kubeturbo](../../../../03-media/cloudability-premium/images/containers-metrics-agent-provisioning-2.jpg)

**Tema principal:** [Configuración de clústeres de Kubernetes](../product/k8s-cluster-provisioning.html)
