---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Glosario de dimensiones y métricas de utilización"
breadcrumb:
  - "Cloudability Premium"
  - "Datos de referencia"
source_path: "product/glossary-of-utilization-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Glosario de dimensiones y métricas de utilización

Cloudability las herramientas de elaboración de informes de la empresa le permiten desglosar los datos de utilización para que pueda saber exactamente cómo se utiliza su infraestructura. Divididas en dos secciones, a continuación se identifican las dimensiones y métricas disponibles en sus informes.

1. [Dimensiones de utilización](#utilization_dimensions "(se abre en una pestaña o una ventana nueva)")
2. [Métricas de utilización](#utilization_metrics "(se abre en una pestaña o una ventana nueva)")

**Dimensiones de utilización**

- ID de cuenta : El número de 12 dígitos AWS utilizado para identificar una cuenta. Para el análisis de costes de las cuentas de facturación consolidada, se refiere a una cuenta vinculada.
- Nombre de la cuenta : El nombre asociado a una cuenta AWS. Para el análisis de costes de las cuentas de facturación consolidada, se refiere a una cuenta vinculada.
- AMI : Esta dimensión filtra los datos que solicita para todas las instancias que ejecutan esta EC2 Imagen de máquina de Amazon (AMI). Disponible para instancias con Monitorización Detallada activada.
- Arquitectura : La arquitectura base del hardware de la instancia (por ejemplo, x86, x86\_64, i386 ).
- Zona de disponibilidad : Combinación de la región y la zona en la que existe una instancia o se ha producido un cargo por uso (por ejemplo, us-east-1a ).
- Velocidad de reloj de la CPU : La velocidad de reloj base de los procesadores de la instancia (GHz).
- Estado actual : Estado actual de la instancia EC2 (por ejemplo, en ejecución, parada). Consulte la [Guía del usuario del ciclo de vida de la instancia AWS](http://docs.aws.amazon.com/awsec2/latest/userguide/ec2-instance-lifecycle.html "(se abre en una pestaña o una ventana nueva)") para obtener información adicional.
- Fecha : La fecha del calendario (por ejemplo, AAAA-MM-DD).
- Día : El día del mes.
- Día de la semana : El día de la semana (por ejemplo, lunes).
- Días de vida : Número total de días transcurridos desde el lanzamiento inicial de la instancia.
- Nombre DNS : El nombre DNS público asociado a una instancia concreta de EC2 (por ejemplo, ec2-54-205-210-122.compute-1.amazonaws.com ).
- Hora : La hora numérica del día (por ejemplo, 1pm => 13).
- Categoría de instancia : La categoría de instancia (por ejemplo, Propósito General, Computación Optimizada, etc.).
- ID de instancia : El ID asociado a una instancia concreta de AWS.
- Nombre de la instancia : El nombre de una instancia concreta de EC2.
- Tipo de instancia : El tamaño de una instancia (por ejemplo, m1.medium ). Para más información, consulte [Dimensiones y métricas de uso frecuente](frequently-used-dimensions-and-metrics.html).
- Dirección IP : La dirección IP asociada a una instancia concreta de EC2.
- **Última ejecución** : Fecha de la última ejecución del recurso.
- Fecha de lanzamiento : La fecha de lanzamiento de una instancia concreta (por ejemplo, 2014-01-22).
- Día de lanzamiento : El día de lanzamiento de una instancia concreta (por ejemplo, el lunes).
- Día de lanzamiento de la semana : El día de la semana en que se lanzó una instancia concreta (por ejemplo, el lunes).
- Mes de lanzamiento : El mes numérico en el que se lanzó una instancia (por ejemplo, 1 => enero).
- Hora de lanzamiento : El valor de fecha y hora que describe cuándo se lanzó una instancia (por ejemplo, 2000-01-01T22:46:34Z ).
- Semana de lanzamiento : La semana del año en la que se lanzó una instancia (es decir, 52 indicaría la última semana de un año natural).
- Año de lanzamiento : Año en el que se lanzó una instancia.
- Mes : El mes natural numérico (por ejemplo, 2014-1-15 => 12).
- OS : El sistema operativo de una instancia (por ejemplo, Linux ).
- Nombre DNS privado : Las instancias de Amazon EC2 necesitan direcciones IP para comunicarse. Las direcciones IP públicas permiten la comunicación a través de Internet.
- IP privada : Las instancias de Amazon EC2 necesitan direcciones IP para comunicarse. Las direcciones IP privadas permiten la comunicación.
- Arquitectura del procesador : La arquitectura de la CPU.
- Región : Región en la que existe una instancia o se ha producido un cargo por uso (por ejemplo, este de EE.UU.).
- IDs de Grupo de Seguridad : Un grupo de seguridad actúa como un cortafuegos que controla el tráfico para una o más instancias. Cada grupo de seguridad se identifica mediante un ID único (por ejemplo, sg-xxxxxxxx).
- Nombres de los grupos de seguridad : Un grupo de seguridad actúa como un cortafuegos que controla el tráfico de una o varias instancias. Cada grupo de seguridad requiere un nombre único (límite 255 caracteres).
- Tipo de almacenamiento : Aún no hay contenido para esta entrada
- ID de subred : El ID de subred asociado a una instancia de EC2. Si aparece un ID de subred, la instancia está en una VPC.
- Virtualización : El entorno virtualizado, si lo hay, que se ejecuta en una instancia determinada.
- Semana : La semana numérica del calendario.
- Año : El año natural (por ejemplo, 2014).
- Zona : Zona de disponibilidad en la que existe una instancia o se ha producido un cargo por uso (por ejemplo, 1a ).

**Métricas de utilización**

- Avg CPU Utilization : Porcentaje de unidades de cálculo asignadas a EC2 que se están utilizando actualmente en la instancia. Esta métrica identifica la potencia de procesamiento necesaria para ejecutar una aplicación en una instancia seleccionada.
- Coste medio estimado : El coste medio estimado de una instancia basado en el marco temporal seleccionado (horas de utilización: coste medio estimado por hora de la instancia).
- Coste horario medio : El coste horario medio basado en las tarifas base establecidas por AWS.
- Coste horario medio por instancia : El coste horario medio por instancia basado en las tarifas base establecidas por AWS.
- Avg Memory Utilization : Porcentaje medio de memoria asignada por las aplicaciones y el sistema operativo para una instancia. Esta métrica excluye la memoria en caché y los búferes.
- Número medio de instancias en ejecución por hora : Número medio de instancias en ejecución por hora. Para más información, consulte [Dimensiones y métricas de uso frecuente](frequently-used-dimensions-and-metrics.html).
- Bandwidth In : El número de bytes recibidos en todas las interfaces de red por la instancia. Esta métrica identifica el volumen de tráfico de red entrante a una aplicación en una única instancia.
- Ancho de banda de salida : El número de bytes enviados en todas las interfaces de red por instancia. Esta métrica identifica el volumen de tráfico de red saliente hacia una aplicación en una única instancia.
- Balance de rá fagas : Proporciona información sobre el porcentaje de créditos de E/S (para gp2 ) o créditos de rendimiento (para st1 y sc1 ) que quedan en el cubo de ráfagas. Se utiliza sólo con volúmenes SSD de uso general ( gp2 ), HDD de rendimiento optimizado ( st1 ) y HDD frío ( sc1 ).
- Coste (Estimado a petición) : El coste estimado basado en los valores que se encuentran en el Fichero de Asignación de Costes AWS.
- CPU Total (línea azul) : El porcentaje normalizado de utilización máxima de la CPU en la hora indicada, basado en el recuento máximo de instancias para todo el ASG en la ventana temporal de 10 o 30 días. Ejemplo: Si hay cinco instancias en un ASG y las 5 instancias están utilizando el 100% de su CPU entonces el **total de CPU** es 100%. Si una instancia está utilizando el 100% de su CPU y las otras cuatro instancias están utilizando el 0% de sus CPUs, entonces **el total de CPU** es del 20%.
- **Utilización de la CPU (Máx)** : El porcentaje máximo de utilización de la CPU alcanzado durante la hora. En el caso de EC2, se trata del porcentaje máximo de unidades de cálculo asignadas a EC2 en uso para una instancia. Cuando se agrega, informa del pico en todas las instancias y en todo el periodo de tiempo.
- Acceso a disco : Total de bytes leídos y escritos para todos los discos efímeros disponibles para la instancia (si su instancia utiliza Amazon EBS, consulte [Métricas de Amazon EBS](http://docs.aws.amazon.com/amazoncloudwatch/latest/developerguide/ebs-metricscollected.html "(se abre en una pestaña o una ventana nueva)") ).
- E/S de disco : Operaciones de lectura y escritura completadas desde todos los discos efímeros disponibles para la instancia.
- Acceso de lectura de disco : Total de bytes leídos de todos los discos efímeros disponibles para la instancia.
- E/S de lectura de disco : Operaciones de lectura completadas desde todos los discos efímeros disponibles para la instancia.
- Disk Write Access : Total de bytes escritos en todos los discos efímeros disponibles para la instancia.
- E/S de escritura en disco : Operaciones de escritura completadas en todos los discos efímeros disponibles para la instancia.
- **GPU Total (%)**  :- El Total de GPU (%) se maneja de la misma manera que el Total de CPU (%). (Consulte la [sección "Optimización del tamaño" para AWS EC2 ASG](rightsizing-for-aws-autoscaling-groups.html) )
- **Memoria GPU Total (%)**  memoria de la GPU (%): La memoria total de la GPU (%) se gestiona de la misma manera que la memoria total de la CPU (%). (Consulte la [sección "Optimización del tamaño" para AWS EC2 ASG](rightsizing-for-aws-autoscaling-groups.html) )
- **GPU Memory Utilization** : Porcentaje de tiempo durante un periodo de muestra en el que se estaba escribiendo o leyendo memoria.

  Nota:

  Para obtener resultados satisfactorios con las métricas de la GPU, asegúrate de haber configurado [las métricas mínimas de la GPU](https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-gpu-monitoring-gpumon.html "(se abre en una pestaña o una ventana nueva)") como requisito previo.
- **Utilización de la GPU** : Porcentaje de tiempo durante un periodo de muestra en el que se ejecutaron uno o más kernels en la GPU.
- Horas desde el lanzamiento : Número de horas transcurridas desde el lanzamiento inicial de una instancia.
- **Recuento de instancias: Total CPU (línea roja)** : El número total de instancias en ejecución para este ASG en la hora indicada.
- **Recuento de instancias: Network Max (línea roja)** : El número total de instancias en ejecución para este ASG en la hora indicada.
- **Recuento de instancias: Total Memoria(línea roja)** : El número total de instancias en ejecución para este ASG en la hora indicada.
- Instancias lanz adas : Número total de instancias lanzadas en un periodo de tiempo determinado.
- Memoria : La cantidad de memoria disponible para la instancia.
- **Memoria total (línea azul)** : El porcentaje normalizado de utilización máxima de memoria en la hora indicada, basado en el recuento máximo de instancias para todo el ASG en la ventana temporal de 10 o 30 días. Ejemplo: Si hay cinco instancias en un ASG y las cinco instancias están utilizando el 100% de su memoria, entonces el **total de Memoria** es 100%. Si una instancia está utilizando el 100% de su memoria y las otras cuatro instancias están utilizando el 0% de su memoria, entonces la **Memoria total** es del 20%.
- **Red máxima (línea azul)** : El número total de bits por segundo utilizados basado en el recuento máximo de instancias para todo el ASG en la hora indicada.
- **Recomendado: Total CPU (línea discontinua amarilla)** : El porcentaje normalizado recomendado de asignación de uso de CPU para todo el ASG en la hora indicada.
- **Recomendado: Total de memoria(línea discontinua amarilla)** : El porcentaje normalizado recomendado de asignación de utilización de memoria para todo el ASG en la hora indicada.
- **Recomendada: Total de la red (línea discontinua amarilla)** : La asignación de red recomendada para todo el ASG en la hora indicada.
- **Recuento de instancias recomendadas: Total CPU (línea amarilla, se muestra al pasar el ratón por encima)** : El número total de instancias recomendadas para este ASG en la hora indicada.
- **Recuento de instancias recomendadas: Total de memoria (línea amarilla, se muestra al pasar el ratón por encima)** : El número total de instancias recomendadas para este ASG en la hora indicada.
- Almacenamiento : La cantidad de almacenamiento disponible para la instancia. Este número no incluirá EBS.
- Dispositivos de almacenamiento : Número total de dispositivos de almacenamiento asociados a una instancia en un periodo de tiempo determinado.
- **Recuento de instancias recomendadas (línea amarilla, se muestra al pasar el ratón por encima)** : El número total de instancias recomendadas para este ASG en la hora indicada.
- Ancho de banda total : Total de bytes transferidos por una instancia concreta.
- Recuento de instancias únicas : El número total de instancias únicas en un estado de ejecución durante un periodo de tiempo determinado.
- Horas de utilización : Número total de horas de utilización de una instancia en un periodo de tiempo determinado.
- Volume Consumed Read Write Ops : La cantidad total de operaciones de lectura y escritura (normalizadas a 256K unidades de capacidad) consumidas en un periodo de tiempo especificado. Sólo se utiliza con volúmenes SSD de IOPS provisionadas.
- Porcentaje de rendimiento del volumen : El porcentaje de operaciones de E/S por segundo (IOPS) entregadas del total de IOPS provisionadas para un volumen de Amazon EBS. Sólo se utiliza con volúmenes SSD de IOPS provisionadas.

  Nota:

  Esta métrica no es compatible con volúmenes habilitados para Multi-Attach.
