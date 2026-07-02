---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Dimensionamiento correcto"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
source_path: "product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html"
images:
  - "images/rightsizing-explorer.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Dimensionamiento correcto

Con Rightsizing, puede definir la infraestructura de nube óptima que mejor se adapte a sus necesidades actuales y a corto plazo, de manera que se equilibren el riesgo y el coste para minimizar el desperdicio.

Con los paneles de Rightsizing, puede ver la utilización de los recursos de la nube a lo largo del tiempo. A continuación, puede ver los escenarios recomendados para cada recurso con el fin de informar mejor sus decisiones de dimensionamiento de la nube.

Existen dos cuadros de mandos de Rightsizing:

- Redimensionamiento: Consulte las recomendaciones de dimensionamiento para sus servicios en la nube. [Rightsizing Dashboard](#get-recommendations-for-scaling-your-cloud-resources-with-rightsizing__Rightsiz).
- ROI de Rightsizing: Vea los ahorros potenciales y realizados para los tickets sincronizados con Jira [Rightsizing utilizando una integración de Jira](jira-for-rightsizing.html).

Panel de control de optimización

El panel de Rightsizing muestra por defecto la pestaña Explorador. El Rightsizing Explorer ofrece una visión general de los posibles ahorros en todos los recursos en la nube utilizados por su empresa. Puede utilizar este panel para agrupar, filtrar y navegar por las recomendaciones de dimensionamiento.

[Explorador de derechos](rightsizing-explorer.html).

![captura de pantalla de redimensionamiento](../../../../03-media/cloudability-premium/images/rightsizing-explorer.jpg)

Las pestañas adicionales en Rightsizing son recomendaciones para proveedores de nube específicos.

## Preguntas más frecuentes

¿Por qué el plazo de recomendación por defecto es de 10 días?

10 días capta las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.

¿Cómo se define la inactividad?

El *tiempo de inactividad* se define de forma diferente según el tipo de recurso, pero generalmente se representa de la siguiente manera: Idle para Compute (por ejemplo EC2 ) es el tiempo empleado por debajo del 2% de CPU en una escala de 1-100. Idle para Block Storage / Disk (por ejemplo EBS ) es el porcentaje de horas con cero IOPS. La inactividad para el almacenamiento relacional/base de datos (por ejemplo RDS ) se basa en el número de conexiones/sesiones de base de datos activas en un momento dado.

¿Cómo se determina el gasto?

Los gastos son los gastos de uso de instancia para Informática (por ejemplo EC2 ) y Almacenamiento relacional/Base de datos (por ejemplo RDS ). El almacén de datos (por ejemplo, Redshift ) excluye la transferencia de datos. Para Object y Block Storage (por ejemplo, S3 y EBS ), el gasto se determina por GB Months.

¿Por qué el Gasto total en el Ajuste de derechos no coincide exactamente con los valores mostrados en Informes / Explorador de costes reales?

Rightsizing sólo enumera los recursos para los que ha encontrado al menos un recurso de ahorro, por lo que es probable que estos valores no coincidan exactamente.

¿Por qué veo (no establecido) en Estado para EBS?

La cuenta no tiene permisos suficientes (asegúrese de que su política está actualizada con los permisos más recientes) o el recurso estuvo activo durante menos de una hora (los datos no aparecen en la caché Describe Data de AWS ).

¿Por qué veo N/A para lastAttachedTime para volúmenes EBS no conectados?

Los volúmenes mostrarán la fecha y hora de su última conexión a las instancias de EC2 y la dirección volumeID. Para los volúmenes que no se han adjuntado durante la ventana de asignación de derechos (los últimos 10 días por defecto), se mostrará N/A.

Para EC2, ¿las recomendaciones tienen en cuenta la explosión?

Utilizamos el rendimiento de referencia para los recursos con ráfagas (por ejemplo, los tipos de instancia T2 ) y no tenemos en cuenta la ráfaga a la hora de determinar las recomendaciones. Así nos aseguramos de hacer recomendaciones conservadoras que no supongan un recorte de recursos.

Para EC2, ¿cómo se determina Red y Disco?

AWS no informa de los límites de rendimiento de *red* y *disco* de EC2. Además, la capacidad de rendimiento variará en función tanto de la carga de trabajo (por ejemplo, lectura y escritura secuencial frente a aleatoria) como de la transferencia (por ejemplo, transferencia de datos dentro de una región frente a entre regiones). Utilizamos los límites comúnmente observados en nuestra cartera de clientes para aproximar la capacidad.

¿Por qué se excluyen las Spot Instances de las recomendaciones de ampliación?

Nuestro motor de redimensionamiento tiene en cuenta su carga de trabajo (métricas de utilización) y el coste de ejecutarla (tipo de instancia actual y precio bajo demanda) y genera una lista de recomendaciones entre las que puede elegir para ayudarle a ahorrar dinero. Por otro lado, las instancias puntuales ya se ofrecen con grandes descuentos, por lo que aplicar la reducción de tamaño en estas situaciones supone un ahorro insignificante. Por esta razón, hemos optado por excluir las Spot Instances de la redimensión.

Nota:

Cuando le recomendamos que traslade un tipo de instancia EC2 a una instancia sin almacenamiento local, incorporamos a la recomendación que añada EBS y contabilice ambos en el ahorro.

¿Con qué frecuencia se actualizan las recomendaciones?

Actualizamos a diario nuestras recomendaciones. Puede acceder a las recomendaciones para los recursos 24 horas después de la creación del recurso, siempre que haya suficientes datos de utilización.

¿Cómo determina Cloudability las recomendaciones de dimensionamiento?

Las recomendaciones de dimensionamiento se generan utilizando el algoritmo de dimensionamiento más avanzado de Cloudability. Estas recomendaciones varían según el proveedor de servicios en la nube y el servicio, pero normalmente las métricas que se tienen en cuenta son las que se muestran en los gráficos del panel de detalles de las recomendaciones. Por ejemplo, las recomendaciones informáticas suelen tener en cuenta una combinación de CPU, red, disco, memoria y posiblemente algunas otras métricas, así como la utilización durante los periodos de tiempo seleccionados para comprender las mejores opciones.

¿Qué debo tener en cuenta a la hora de estudiar las recomendaciones de redimensionamiento?

Al examinar las recomendaciones de reajuste de tamaño, primero tiene que comprender la diferencia entre las opciones de base de costes disponibles y la que pretende utilizar. En segundo lugar, actúe con la debida diligencia a la hora de aplicar una determinada recomendación, ya que Cloudability desconoce la finalidad de cada recurso. Es posible que sus equipos hayan mantenido determinados recursos "ociosos" o "infrautilizados" para un fin concreto, pero Cloudability puede recomendar suprimirlos o reducir su tamaño.

En la sección Redimensionamiento, ¿podemos fijar el periodo de retrospectiva (línea de tiempo) en 60 días?

En la actualidad, la redimensión en Cloudability sólo admite periodos retrospectivos de 10 y 30 días.

¿Cuáles son y qué significan los distintos valores de estado que se muestran en Azure disk rightsizing?

En Rightsizing recommendations for Azure disk, los valores de estado son:

- ActiveSAS: El disco tiene actualmente asociado un Uri SAS Activo.
- ActiveSASFrozen: El disco está conectado a un controlador de almacenamiento ( VM ) en estado de hibernación y tiene asociado un URI SAS activo.
- ActiveUpload: Se ha creado un disco para la carga y se ha emitido un token de escritura para cargar en él.
- Conectado: El disco está conectado actualmente a un servidor « VM » en funcionamiento.
- Bloqueado: el disco está conectado a un VM que se encuentra en estado de hibernación.
- ReadyToUpload: Un disco está listo para ser creado por carga solicitando un token de escritura.
- Reservado: El disco está asociado a un objeto « VM » detenido y desasignado.
- Sin conectar: El disco no se está utilizando y se puede conectar a un dispositivo de almacenamiento de datos ( VM ).

Consulte la siguiente documentación de Azure en "fields" para conocer los últimos valores y sus definiciones [https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.management.compute.models.diskstate?view=azure-dotnet-legacy#fields](https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.management.compute.models.diskstate?view=azure-dotnet-legacy#fields "(se abre en una pestaña o una ventana nueva)")

¿Tienen en cuenta las recomendaciones de redimensionamiento los descuentos del proveedor de servicios en la nube (CSP) debidos a los compromisos por hora? Si se aplican las recomendaciones, ¿se reduce el gasto por hora?

Para AWS debe existir una métrica de costes personalizada. Para Azure y GCP, estos proveedores de servicios en la nube proporcionan una hoja de precios. Por lo tanto, no es necesario fijar precios personalizados. Los gastos por hora entrarán en vigor la próxima vez que se ingieran y procesen los datos de costes y uso.

- **[Explorador de optimización de plantilla](../product/rightsizing-explorer.html)**
- **[AWS EC2](../product/rightsizing-for-aws-ec2.html)**
- **[AWS EC2 Grupo de autoescalado (ASG)](../product/rightsizing-for-aws-autoscaling-groups.html)**
- **[AWS EBS](../product/rightsizing-for-aws-elastic-block-store.html)**
- **[AWS ElasticIP](../product/aws_elasticip.html)**
- **[AWS Lambda](../product/rightsizing-aws-lambda.html)**
- **[AWS RDS](../product/rightsizing-for-aws-rds.html)**
- **[Amazon Redshift](../product/aws_redshift.html)**
- **[AWS S3](../product/rightsizing-amazon-s3.html)**
- **[Azure Calcular](../product/rightsizing-for-azure-compute.html)**
- **[Azure Conjuntos de escalabilidad informática](../product/azure_compute_scale_sets.html)**
- **[Azure Disco](../product/rightsizing-for-azure-disks.html)**
- **[Azure SQL](../product/rightsizing-for-azure-sql.html)**
- **[Azure Blob Storage](../product/rightsizing-for-azure-blob-storage.html)**
- **[GCP Google Compute Engine (GCE)](../product/rightsizing-for-gce.html)**
- **[GCP Google Compute Engine (GCE) Grupos de instancias gestionadas (MIG)](../product/rightsizing-for-gcp-gce-mig.html)**
- **[GCP Google Disco persistente (GPD)](../product/rightsizing-for-gpd.html)**
- **[GCP Google Cloud Storage (GCS)](../product/rightsizing-for-gcp-cloud-storage.html)**
- **[Máquinas virtuales OCI (VM)](../product/rightsizing-for-oci-vms.html)**
- **[Acción de autoescalado para redimensionamiento](../product/rightsizing-autoscale-action.html)**
- **[Ajuste del tamaño de los contenedores de « Kubernetes »](../product/k8s-container-rightsizing.html)**
- **[Preferencias de redimensionamiento](../product/rightsizing-preferences.html)**
- **[Recomendaciones sobre el tamaño de la cama](../product/rightsizing-snoozing-recommendations.html)**

**Tema principal:** [«Rightsizing» en « Cloudability Premium »](../product/rightsizing-in-cloudability-premium.html)
