---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Agente de métricas de Common Kubernetes : mensajes de error"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "product/k8s-metrics-agent.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Agente de métricas de Common Kubernetes : mensajes de error

**Descripción general**

Durante su funcionamiento, el agente de métricas de Cloudability puede registrar mensajes de error específicos. En este artículo se explica cómo consultar los registros de mensajes de error, cuáles son los mensajes de error más habituales y cuáles son las posibles soluciones.

**Revisión de los registros de mensajes de error**

Para consultar los registros de mensajes de error de un pod específico de Metrics Agent, es necesario obtener el nombre del pod antes de solicitar el registro de mensajes de error.

1. Desde la línea de comandos, ejecuta el siguiente comando para ver una lista de todos los pods de Metrics Agent disponibles en un clúster. `kubectl get pods -n cloudability`
2. Ejecuta el siguiente comando para ver el registro de mensajes de error de un pod específico de Metrics Agent. Sustituye <pod-name> por el nombre del pod del agente de métricas detectado en el paso anterior. `kubectl logs <pod-name> -n cloudability`

`Exported metric sample <cluster_UID>_<timestamp> to cloudability`

**Mensajes de error**

| Mensaje de error | Solución |
| --- | --- |
| Advertencia: error no grave: se ha producido un error del agente al recuperar los diagnósticos de tiempo de ejecución: <mensaje detallado> | Es posible que haya que actualizar el rol RBAC en el espacio de nombres Cloudability. Vuelve a configurar el agente de métricas para este clúster tal y como se detalla en « [Kubernetes : cluster provisioning](k8s-cluster-provisioning.html) ». |
| Error al enviar métricas: Error al recuperar el URI de carga: 403 | La clave API de « Cloudability » que se está utilizando actualmente no es válida. Es posible que la clave de la API sea incorrecta o que haya caducado.  Si ha caducado, es necesario volver a habilitar la clave API antes de volver a configurar el agente de métricas, tal y como se detalla en « [Kubernetes cluster provisioning](k8s-cluster-provisioning.html) ». Ponte en contacto con el servicio de asistencia para volver a activar las claves API caducadas.  Si la clave API es incorrecta, vuelve a generarla siguiendo los pasos de aprovisionamiento que se detallan en [« Kubernetes cluster provisioning».](k8s-cluster-provisioning.html) |
| Error al enviar métricas: Error al recuperar el URI de carga: <mensaje detallado> | Es posible que haya problemas de transporte de red que impidan que el agente se comunique con la API de recopilación de métricas.  Este error puede deberse a las configuraciones de seguridad del clúster o a los proxies configurados en los contenedores de « Kubernetes » del cliente. Estas configuraciones las gestionan los administradores del clúster. Ponte en contacto con los administradores de tu clúster de Kubernetes para confirmar que el agente de métricas puede establecer una conexión con: [https://metrics-collector.cloudability.com](https://metrics-collector.cloudability.com/ "(se abre en una pestaña o una ventana nueva)") |
| Advertencia: error no grave: se ha producido un error del agente al recuperar las métricas de origen del nodo: no se han podido recuperar las métricas del nodo. Por favor, comprueba los roles de RBAC: | Es posible que haya que actualizar el rol RBAC en el espacio de nombres Cloudability. Vuelve a configurar el agente de métricas para este clúster tal y como se detalla [en « Kubernetes : cluster provisioning](k8s-cluster-provisioning.html) ». |
| Se ha detectado un nodo Fargate en el clúster; la conexión directa al nodo está desactivada. | No es posible establecer una conexión directa con un nodo de « AWS Fargate », por lo que, cuando se detecta un nodo Fargate en el clúster, el agente pasa a utilizar kube-proxy para todas las conexiones a los nodos del clúster.  Actualmente, la asignación de tareas de EKS Fargate no es compatible con el panel de control de la función de contenedores. Ponte en contacto con tu gestor técnico de cuentas para obtener instrucciones sobre cómo acceder a la información de EKS Fargate a través de la función de generación de informes. |

Si necesitas asistencia directa para resolver problemas relacionados con el agente de métricas de Cloudability, [ponte en contacto con el servicio de asistencia](https://support.cloudability.com/hc/en-us/requests/new "(se abre en una pestaña o una ventana nueva)").
