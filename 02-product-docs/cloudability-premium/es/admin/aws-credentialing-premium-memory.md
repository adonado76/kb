---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conexión con AWS - Obtención de métricas de memoria para instancias de EC2 (Windows y Linux )"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conexión con AWS - Guía de integración de clientes"
source_path: "admin/aws-credentialing-premium-memory.html"
images:
  - "images/clip_image001_-662737569.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexión con AWS - Obtención de métricas de memoria para instancias de EC2 (Windows y Linux )

Cloudability Rightsizing Engine evalúa la utilización de los recursos subyacentes para cada instancia de EC2 y recomienda los tipos de instancia que mejor se adaptan a cada perfil de utilización. El objetivo final es mantener bajos los costes sin perder de vista los riesgos operativos.

Para obtener las recomendaciones más precisas, hay cuatro métricas de utilización que deben ser evaluadas: CPU, IOPS de disco (en el caso de instancias que tengan discos locales), ancho de banda de red y utilización de memoria. Por una serie de razones de peso, hemos optado por extraer estos datos directamente de CloudWatch. La razón clave es que las métricas a nivel de hipervisor se guardan en CloudWatch por defecto para cada instancia sin que usted haga nada. Esto deja la utilización de memoria como la única métrica que requiere un poco más de esfuerzo por su parte para publicar en CloudWatch. Para ello se utiliza lo que AWS denomina métricas personalizadas, sobre las que puede leer [aquí](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fpublishingmetrics.html "(se abre en una pestaña o una ventana nueva)").

La buena noticia es que AWS ha creado formatos estándar para la publicación de datos de memoria y nosotros hemos adoptado un enfoque racionalizado para ingestar esos datos. Requerimos que sólo se publique una métrica personalizada utilizando el [agente unificado actual.](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Finstall-cloudwatch-agent.html "(se abre en una pestaña o una ventana nueva)")

**Pasos para la integración**

**AWS Agente unificado**

Este es el método preferido para los datos de memoria. Cloudability admite la ubicación estándar y las convenciones de nomenclatura que utiliza el agente unificado al escribir métricas personalizadas en Cloudwatch. Estos detalles son:

- **metric-name** : "mem\_used\_percent" (para Linux )
- **metric-name** : "Mbytes disponibles" (para Windows)
- **espacio de nombres** : CWAgent
- **dimensiones** : InstanceId (es importante añadir sólo esta dimensión)
- **unidad** : porcentaje

**Instrucciones**

AWS proporciona una serie de opciones para instalar el agente que puede encontrar en [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Finstall-cloudwatch-agent-on-ec2-instance.html "(se abre en una pestaña o una ventana nueva)"). El agente unificado proporciona capacidades para publicar muchos tipos de métricas personalizadas.

El siguiente es un ejemplo de una configuración mínima **Linux** para publicar sólo la información de memoria:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

A continuación se muestra un ejemplo de configuración mínima de **Windows** para publicar sólo la información de memoria:

```
{  
						"metrics": { 
						"metrics_collected": { 
						"Memory": { 
						"measurement": [ 
						{"name": "Available Mbytes", "unit":"Megabytes"} 
						], 
						"resources": [ 
						"*" 
						] 
						} 
						},  
						"append_dimensions": { 
						"InstanceId": "${aws:InstanceId}" 
						} 
						} 
						} 
				
```

Nota: Si la métrica **«Mbytes disponibles»** no está disponible, se utilizará la métrica heredada **«% de bytes comprometidos en uso»,** siempre que esté disponible. Por ejemplo, {"name": "% Committed Bytes In Use", "unit":"Percent"}

Nota: Cuando se publique la métrica personalizada, es importante que solo incluya la dimensión « InstanceId ». Esto se debe a que, tal y como se describe en [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch\_concepts.html#dimension-combinations](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fcloudwatch_concepts.html%23dimension-combinations "(se abre en una pestaña o una ventana nueva)"), de AWS, cada combinación de dimensiones constituye una métrica totalmente independiente, que debe consultarse con todos los datos dimensionales.

Si desea publicar varias dimensiones, puede utilizar la palabra clave aggregation\_dimensions como se muestra en el ejemplo siguiente **Linux** ejemplo siguiente. La dimensión extra en este caso es AutoScalingGroupName. En este ejemplo, acabará con tres métricas de memoria publicadas, cada una con una combinación de dimensiones diferente 1) sólo InstanceID 2) sólo AutoScalingGroupName 3) tanto InstanceID como AutoScalingGroupName.

El siguiente es un **Linux** ejemplo:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

**Perl Agente basado**

Tenga en cuenta que AWS ha eliminado el agente basado en perl, pero sigue estando disponible para su descarga. Cloudability seguirá soportando este método, pero le recomendamos que cambie al nuevo agente unificado si es posible.

Como ya se ha indicado, sólo se necesita una métrica personalizada. La métrica basada en perl tiene este aspecto:

- **metric-name** : MemoryUtilization
- **espacio de nombres** : Sistema/ Linux o Windows/Default
- **dimensiones** : InstanceId (es importante añadir sólo esta dimensión)
- **unidad** : porcentaje

**Instrucciones**

Instale los scripts de supervisión perl CloudWatch tal y como se describe en esta página web AWS. En esta página encontrarás instrucciones para instalar los paquetes necesarios en equipos que ejecuten la imagen AMI de « Amazon Linux » y otros sistemas operativos habituales, como « Red Hat ».

Esta es la configuración crontab que utilizamos en Cloudability para las máquinas Linux :

`* * * * * ~/aws-scripts-mon/mon-put-instance-data.pl --mem-util
--from-cron`

Esto publicará exactamente lo que Cloudability requiere y nada más. Deberías poder confirmar que la métrica de memoria se reporta a intervalos de 5 min.

**Otras opciones** : Otras opciones incluyen la creación de un agente propio que se integre con el SDK de AWS. [Aquí](https://www.ibm.com/links?url=https%3A%2F%2Fgithub.com%2Fa3linux%2Fgo-aws-mon "(se abre en una pestaña o una ventana nueva)") tienes un ejemplo en el que se utiliza « Golang » y con el que algunos de nuestros clientes han obtenido buenos resultados.

**Cómo confirmar el éxito**

Normalmente, en las 24 horas siguientes a la configuración de su instancia de EC2, esta información sobre la memoria estará disponible en Cloudability rightsizing.

He aquí un ejemplo de los datos de memoria resultantes al visualizarlos en la consola AWS Cloudwatch. Esto puede ser útil a efectos de depuración.

![aws](../../../../03-media/cloudability-premium/images/clip_image001_-662737569.jpg)

Nota: Estos son datos de ejemplo del agente basado en perl. Los datos del agente unificado aparecerán de forma similar, pero con el espacio de nombres y el nombre de métrica correspondientes.

Disponer de estos datos de memoria en CloudWatch proporcionará ventajas que van mucho más allá de Cloudability, por lo que recomendamos encarecidamente seguir este camino. Por ejemplo, puede utilizar los datos de la memoria para activar eventos de autoescalado o activar alarmas. Una vez que encuentres el método que te funciona, sería una buena idea incluirlo en tu configuración.

**Obtener recomendaciones basadas en datos de la GPU** Cloudability permite a los usuarios consultar recomendaciones basadas en datos de la GPU procedentes de instancias de AWS EC2.

Cloudability ingiere los datos de procesamiento de la GPU y de utilización de la memoria de sus instancias de AWS. De este modo, Cloudability podrá formular recomendaciones de dimensionamiento que también tengan en cuenta estos datos. Por ejemplo, si no utiliza GPU, se le puede recomendar que cambie a un tipo de instancia que incluya GPU para ahorrar dinero.

Cloudability ofrece 2 opciones para recopilar datos de la GPU:

**Opción 1: Utilice AWS CloudWatch Agente ( Linux solamente)**

Para empezar a recopilar los datos de utilización de la GPU mediante el agente de AWS CloudWatch, primero debes configurar tu agente para que facilite estos datos: [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Agent-NVIDIA-GPU.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Famazoncloudwatch%2Flatest%2Fmonitoring%2Fcloudwatch-agent-nvidia-gpu.html "(se abre en una pestaña o una ventana nueva)")

El siguiente es un ejemplo de una configuración mínima de Linux para publicar sólo la información de la memoria y la GPU:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						]       
						},
						"nvidia_gpu": {
						"measurement": [
						"utilization_gpu",
						"utilization_memory"
						]
						}    
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				}
```

**Opción 2: Utilizar el agente de monitorización de GPU (tanto Linux como Windows)**

Para comenzar a ingerir los datos de utilización de la GPU, debe utilizar el agente de monitorización de la GPU.

Antes de empezar

Tu archivo « VM » debe contener lo siguiente:

- GPU habilitada
- Controladores Nvidia instalados
- Python 2.7 o superior instalado

**Pasos para la integración**

**Instrucciones para Linux VMs**

Ejecute el script Python :

1. Instale Python 2.7 o superior si aún no está disponible y conviértala en la versión por defecto Python.
2. Instale pip >= 20.3.4 si aún no está disponible.
3. Dado que su instancia ya se está ejecutando en la AMI habilitada para GPU, necesita crear un rol IAM que conceda a su instancia el permiso para enviar métricas a Amazon CloudWatch. Cree un rol de servicio EC2 que permita la siguiente política:

   ```
   { "Version": "2012-10-17", "Statement": [ { "Action": [ "cloudwatch:PutMetricData", ], "Effect": "Allow", "Resource": "*" } ] }
   ```
4. Descarga el script personalizado de gpumon de [https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll](https://www.ibm.com/links?url=https%3A%2F%2Fcommunity.apptio.com%2Fviewdocument%2Fcustom-gpumon-python-script-to-coll%3Fcommunitykey%3Df67c7e7c-be1c-4053-9845-2376da697342%26tab%3Dlibrarydocuments "(se abre en una pestaña o una ventana nueva)") y colócalo en el directorio de destino VM.
5. Instale todas las dependencias.

   Para Python 2.7:

   `sudo pip2.7 install Nvidia-ml-py
   boto3`

   Para Python 3 o superior:
6. Ejecuta el comando dado en segundo plano:

   `python gpumon.py <Region> <log file
   path>`

   Por ejemplo nohup python gpumon.py < AWS -Región> <ruta del archivo de registro> &

**Instalar y ejecutar el agente de « Datadog »**

1. Sigue las instrucciones del documento que se indica para configurar el agente de Datadog en [https://docs.datadoghq.com/integrations/nvml/](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.datadoghq.com%2Fintegrations%2Fnvml%2F "(se abre en una pestaña o una ventana nueva)").

Ejecuta el siguiente comando de instalación de la integración del agente en lugar del comando que figura en la documentación de « Datadog »:

`sudo -u dd-agent datadog-agent integration install -t
datadog-nvml==<INTEGRATION_VERSION>`

**Instrucciones para máquinas virtuales Windows**

1. Instale Python 2.7 o superior.
2. Dado que su instancia ya se está ejecutando en la AMI habilitada para GPU, necesita crear un rol IAM que conceda a su instancia el permiso para enviar métricas a Amazon CloudWatch. Cree un rol de servicio EC2 que permita la siguiente política:
3. Establezca la ruta de Python en las variables de entorno de Windows.
4. Descarga el script personalizado «gpumon Python » de [https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll](https://www.ibm.com/links?url=https%3A%2F%2Fcommunity.apptio.com%2Fviewdocument%2Fcustom-gpumon-python-script-to-coll%3Fcommunitykey%3Df67c7e7c-be1c-4053-9845-2376da697342%26tab%3Dlibrarydocuments "(se abre en una pestaña o una ventana nueva)") y actualiza la ruta del archivo de registro según el directorio de archivos de Windows.
5. Ejecute el comando en modo administrador para instalar todas las dependencias.

   Para Python 2.7:

   `pip2.7 install Nvidia-ml-py boto3`

   Para Python 3 y superiores:

   `pip install Nvidia-ml-py boto3`
6. Ejecute la secuencia de comandos para recopilar los datos de utilización de la GPU y enviarlos a Cloud Watch mediante el siguiente comando en modo de administrador:

   `python gpumon.py <AWS-Region> <log file
   path>.`

**Instala y ejecuta el agente de Datadog**

1. Instala el agente de Datadog en tu Windows VM.
2. Establece la ruta ( **C:\Archivos de programa\ Datadog \ Datadog Agent\bin** ) en las variables de entorno de Windows.
3. Ejecuta este comando:

   `agent integration install -t
   datadog-nvml==<INTEGRATION_VERSION>`
4. Instala pip en Windows en la ruta indicada del ejecutable « Python », que utiliza Datadog ( **C:\Program Files\ Datadog \ DatadogAgent\embedded3** )
5. En la línea de comandos en modo administrador, acceda a la ruta **C:\Archivos de programa\ Datadog \ Datadog Agent\embedded3\Scripts** y, a continuación, ejecute el siguiente comando para instalar el paquete.

   `pip3 install grpcio pynvml`
6. Edite el **nvml.d/conf.yaml** en el directorio **conf.d/** en la raíz del directorio de configuración de su Agente, para empezar a recopilar sus datos de rendimiento NVML. Consulte el ejemplo **nvml.d/conf.yaml** para conocer todas las opciones de configuración disponibles.
7. Reinicie el Agente.

**Tema principal:** [Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-premium-home.html)
