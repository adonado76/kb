---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Costes de contenedores asignados por proveedor"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/container-costs-by-vendor.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Costes de contenedores asignados por proveedor

Al asignar costes en función de la utilización, la función Asignación de costes de contenedores tiene en cuenta la siguiente información en función del proveedor.

AWS (EKS/autogestionado)

Para AWS, incluimos el coste de cualquier nodo (instancias de EC2 ) que estuviera presente en el clúster durante el tiempo consultado, así como cualquier volumen EBS adjunto.

GCP (GKE)

En el caso de « GKE », incluimos el coste de cualquier partida de facturación que cumpla las dos condiciones siguientes:

La etiqueta del clúster es clave: gke-cluster

El valor es un nombre de clúster para el que Cloudability está recopilando datos de utilización

Esto también supone una asignación de etiquetas configurada en Cloudability para esa clave de etiqueta. Por lo general, esto incluye, como mínimo, los costes de Compute Engine de GCP.

Azure (AKS)

Para Azure, incluimos cualquier recurso bajo el Grupo de Recursos identificado en la lista de nodos presentes en el clúster durante el tiempo consultado. Normalmente, esto incluye Azure Compute.

Oracle Nube (OKE)

Para OCI, asignamos los costes en función de sus ID de recursos, que se corresponden con partidas de facturación específicas basadas en las métricas que soportan. Esto garantiza que los costes de cada contenedor se reflejen con exactitud en función de su uso. Para saber qué instancias soportan qué métricas, visite [Oracle 's compute pricing](https://www.oracle.com/cloud/compute/pricing/ "(se abre en una pestaña o una ventana nueva)"). Este recurso ayuda a explicar las variaciones en los costes, como por ejemplo por qué algunos nodos acumulan gastos de sistema de archivos mientras que otros no, basándose en los costes por métrica soportados de cada tipo de nodo.

Red Hat OpenShift Servicio en AWS

Cloudability container Cost Insights se ha ampliado para admitir ROSA de forma similar a EKS. El proceso de configuración para importar datos de ROSA a Cloudability sigue los mismos pasos básicos que la configuración de K8s : se descarga un archivo YAML del agente de Cloudability, que luego se utiliza dentro del clúster para [aprovisionar el agente de métricas](k8s-cluster-provisioning.html#k8s-cluster-provisioning__deploythemetricsagent).

Configuraciones compatibles Kubernetes

Como el orquestador de contenedores más popular que existe, hay muchas maneras diferentes de desplegar Kubernetes y OpenShift. Nos esforzamos por ofrecer compatibilidad con todas las versiones certificadas por el CNCF, y mantendremos esta matriz actualizada a medida que ofrezcamos compatibilidad con configuraciones adicionales.

**Tema principal:** [Imputación de costes de contenedores](../product/k8s-cost-allocation.html)
