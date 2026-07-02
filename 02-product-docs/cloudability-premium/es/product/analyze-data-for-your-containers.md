---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Analice los datos de sus contenedores Kubernetes"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/analyze-data-for-your-containers.html"
images:
  - "images/audit2.jpg"
  - "images/cldy-idle-cost.jpg"
  - "images/container-cost-allocation-export.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Analice los datos de sus contenedores Kubernetes

## Imputación de los costes de los contenedores

La función de asignación de costes de contenedores proporciona información más detallada sobre los clústeres aprovisionados. Esto le ayuda a asignar costes con precisión mediante Kubernetes clusters, espacios de nombres, etiquetas, cargas de trabajo y otros métodos.

Para más información, véase [Imputación de costes de contenedores](k8s-cost-allocation.html).

1. En el menú principal, seleccione Insights > Contenedores.
2. Se muestra el menú de Asignación de Costes de Contenedores para que aprovisione sus clusters Kubernetes. ![pantalla de imputación de costes de contenedores](../../../../03-media/cloudability-premium/images/audit2.jpg)

Nota: El uso de EFS en lugar de EBS para el almacenamiento de contenedores no es compatible con Cloudability.

Asignación y recursos ociosos

El coste de los recursos ociosos se distribuye en una dimensión determinada en función del porcentaje del coste total durante ese intervalo.

- Para los pods clasificados como de Calidad de Servicio Garantizada, Cloudability utiliza los datos de solicitud para la asignación, ya que la cantidad de recursos solicitados está reservada,. Para obtener más información, consulte [Configuración de la calidad de servicio para pods](https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/#qos-classes "(se abre en una pestaña o una ventana nueva)").
- Para los pods clasificados como Burstable, Cloudability utiliza la información de solicitud o de uso, la que sea de mayor valor para la asignación.
- Para los pods clasificados como Best Effort, Cloudability aprovecha la información de uso para la asignación.

Base de coste

El agente de recopilación Cloudability recopila métricas de sus clústeres Kubernetes y las envía a Cloudability para su análisis. Utilizando fuentes métricas nativas, Cloudability asigna costes y proporciona información sobre los recursos ociosos de sus clústeres.

Para más información, consulte [Contenedores](https://app.apptio.com/cloudability#/containers "(se abre en una pestaña o una ventana nueva)").

- Cloudability utiliza el Coste (ajustado) como coste de recurso por defecto para la asignación.
- Si no utiliza una métrica de Coste (Ajustado ), Cloudability utiliza el Coste (Total) en su cálculo.
- Cloudability también admite la métrica Coste (Amortizado ) en la asignación de costes de contenedores. Esto le ayuda a comprender el coste total de su clúster Kubernetes, incluidas las instancias reservadas (RI) y los planes de ahorro (SP) consumidos. Al analizar clusters, cambiar a Coste (Amortizado ) permite incluir el coste completo de los RI y SP consumidos.

Puede dividir los costes por espacio de nombres, servicios y etiquetas.

## Distribución de costes de inactividad

Descripción general

Los contenedores tienen una capacidad de sobrecarga no utilizada por las cargas de trabajo subyacentes. Este uso "ocioso" tiene un coste asociado (para máquinas y volúmenes virtuales). Cloudability distribuye estos costes de contenedores ociosos en sus informes, cuadros de mando e imputación de costes de contenedores.

Introduce la nueva categoría métrica Contenedores junto con otras seis. Puede utilizar estas métricas para ver por separado los costes Utilizados, Ociosos y Compartidos por efectivo o amortizados. ![captura de pantalla de la distribución de costes de inactividad](../../../../03-media/cloudability-premium/images/cldy-idle-cost.jpg)

La función de asignación de costes de contenedores evalúa la utilización de recursos en cada nodo y la añade a los datos de facturación para calcular el coste de cada clúster. Esto asocia el Coste Utilizado a Kubernetes espacio de nombres y valores de etiqueta (disponibles dentro de los informes utilizando el espacio de nombres o una dimensión de etiqueta). Con esta mejora también se puede informar sobre el Coste de inactividad a través de la nueva métrica, asignada a los valores de espacio de nombres y etiquetas proporcionalmente en función de su contribución directa al coste de cada nodo. El Coste Justo es la suma del Coste Utilizado y el Coste Ocioso.

Consideraciones e ideas de informes a tener en cuenta con las nuevas métricas:

- En el caso de los costes no relacionados con los contenedores, las nuevas métricas mostrarán todas 0 $. Para filtrar sólo los datos del contenedor, utilice un filtro del tipo " Nombre del clúster no es igual a (no establecido) "
- Utilice estas métricas con diferentes dimensiones para visualizar fácilmente el costo utilizado frente al costo inactivo. Por ejemplo, lista por nombre de clúster o ID de recurso.
- Por primera vez, utilice conjuntamente el criterio de caja y el de coste amortizado para elaborar informes detallados sobre el coste de los contenedores.

## Exportación de datos de asignación de contenedores

Haga clic en el icono Exportar ![icono exportar csv](../../../../03-media/cloudability-premium/images/container-cost-allocation-export.png) para exportar los datos de imputación de costes en formato.csv.

Puede exportar datos al asignar entre clústeres, o dentro de un único clúster, por Espacio de nombres, Servicio y Etiqueta.

. Definiciones de datos de « CSV »

| Nombre | Definición |
| --- | --- |
| Tipo | Muestra si la fila es de datos de asignación, o si informa sobre el uso o coste no asignado (inactivo). |
| Espacio de nombres | Kubernetes Nombre del objeto del espacio de nombres. |
| Servicio | Kubernetes Service nombre del objeto. |
| Etiqueta | Kubernetes Valor de la etiqueta. |
| cpu/reserved:asignación | Porcentaje de uso de CPU asignado a esa fila durante el periodo consultado. |
| cpu/reserved:fairShare | Porcentaje de uso de CPU asignado a esa fila durante el periodo de tiempo consultado al compartir la distribución entre objetos. |
| cpu/reservado:recurso:medio | Uso medio de la CPU observado durante el periodo de tiempo consultado. |
| cpu/reserved:recurso:unidad | Unidad de medida para el uso de la CPU. |
| memoria/reserved\_rss:asignación | Porcentaje de uso del tamaño del conjunto residente de memoria asignado a esa fila durante el periodo de tiempo consultado. |
| memory/reserved\_rss:fairShare | Porcentaje de uso del tamaño del conjunto residente de memoria asignado a esa fila durante el período de tiempo consultado al distribuir los objetos no asignados (inactivos). |
| memoria/reserved\_rss:recurso:media | Uso medio del tamaño del conjunto residente de memoria observado durante el periodo consultado. |
| memoria/reserved\_rss:recurso:unidad | Unidad de medida para el uso del tamaño del conjunto residente de memoria. |
| red/tx:asignación | Porcentaje de uso de Network TX asignado a esa fila durante el periodo consultado. |
| network/tx:fairShare | Porcentaje de uso de TX de red asignado a esa fila durante el periodo de tiempo consultado al distribuir los objetos no asignados (inactivos). |
| red/tx:recurso:media | Uso medio de transmisión de red observado durante el periodo consultado. |
| red/tx:recurso:unidad | Unidad de medida para el uso de Network TX. |
| red/rx:asignación | Porcentaje de uso de Network RX asignado a esa fila durante el periodo consultado. |
| network/rx:fairShare | Porcentaje de uso de Network RX asignado a esa fila durante el periodo de tiempo consultado al distribuir lo no asignado entre objetos. |
| red/rx:recurso:medio | Uso medio de RX de red observado durante el periodo consultado. |
| red/rx:recurso:unidad | Unidad de medida para el uso de Network RX. |
| sistema de archivos/uso:asignación | Porcentaje de uso del sistema de archivos del contenedor asignado a esa fila durante el periodo consultado. |
| filesystem/usage:fairShare | Porcentaje de uso del sistema de archivos del contenedor asignado a esa fila durante el período de tiempo consultado al distribuir los objetos no asignados (inactivos). |
| sistema de archivos/uso:recurso:medio | Uso medio del sistema de archivos del contenedor observado durante el periodo consultado. |
| sistema de archivos/uso:recurso:unidad | Unidad de medida para el uso del sistema de archivos del contenedor. |
| porcentajes:asignación | Porcentaje total de memoria, CPU, RX/TX de red y sistema de archivos asignados a esa fila durante el periodo consultado. |
| percentages:fairShare | Porcentaje total de memoria, CPU, RX/TX de red y sistema de archivos asignados a esa fila durante el periodo de tiempo consultado al distribuir los objetos no asignados (inactivos). |
| percentages:fairShareUnallocated | Porcentaje global de no asignados (inactivos) en memoria, CPU, RX/TX de red y sistema de archivos que comparte esa fila al distribuir los no asignados (inactivos) entre objetos. |
| costes:asignación | Coste total de memoria, CPU, RX/TX de red y sistema de archivos asignados a esa fila durante el periodo consultado. |
| costs:fairShare | Coste global de los recursos no asignados (inactivos) en memoria, CPU, RX/TX de red y sistema de archivos que comparte esa fila al distribuir los recursos no asignados (inactivos) entre los objetos. |
| costes:no asignados | Coste total no asignado (inactivo) en memoria, CPU, RX/TX de red y sistema de archivos durante el periodo de tiempo consultado cuando no se distribuye entre objetos. |

## Configuraciones compatibles Kubernetes

Hay muchas formas de desplegar Kubernetes. Admitimos todas las versiones certificadas por la CNCF (Cloud Native Computing Foundation):

| Servicio | Proveedor | Memoria/PCU/Disco Media | asignación | asignación |
| --- | --- | --- | --- | --- |
| Ninguna | AWS | Sí | Sí | Sí |
| Ninguna | Azure | Sí | Sí | Sí |
| Ninguna | GCP | Sí | Sí | Sí |
| GKE | GCP | Sí | Sí | Sí |
| EKS | AWS | Sí | Sí | Sí |
| AKS | Azure | Sí | Sí | Sí |

Para obtener más información sobre Kubernetes, consulte los siguientes temas:

- [Kubernetes aprovisionamiento de clústeres](k8s-cluster-provisioning.html)
- [Agente de métricas de Kubernetes : mensajes de error](k8s-metrics-agent.html)
- [Kubernetes Asignación de costes](k8s-cost-allocation.html)
- [Costes de los contenedores asignados por proveedor](container-costs-by-vendor.html)
- [Ajuste del tamaño de los contenedores de « Kubernetes »](k8s-container-rightsizing.html)

**Tema principal:** [Imputación de costes de contenedores](../product/k8s-cost-allocation.html)
