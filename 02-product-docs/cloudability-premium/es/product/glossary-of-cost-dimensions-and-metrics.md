---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Glosario de dimensiones y métricas de costes"
breadcrumb:
  - "Cloudability Premium"
  - "Datos de referencia"
source_path: "product/glossary-of-cost-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Glosario de dimensiones y métricas de costes

Cloudability le permiten analizar sus datos de costes y uso para saber exactamente adónde va su dinero. A continuación se identifican las dimensiones y métricas disponibles en sus informes.

## Dimensiones de coste y uso

- ID de cuenta : identificador único relacionado con una cuenta de AWS, una suscripción a Azure, un proyecto de GCP o una tenencia de OCI.
- Nombre de la cuenta : el nombre proporcionado por el cliente que se asocia a cada cuenta de AWS, suscripción de Azure, proyecto de GCP o tenencia de OCI.
- ATUM Torre : Representa una visión general de TI de las funciones tecnológicas de su organización, proporcionando una amplia categorización de costes. Algunos ejemplos de valores son Red, Plataforma, Usuario final y Aplicación.
- ATUM Subtorre : ofrece una categorización más detallada dentro de cada torre, por ejemplo, dividiendo la plataforma en middleware y base de datos.
- ATUM Tipo de servicio : Representa una visión empresarial de alto nivel de su gasto en la nube. Esta es la categorización de nivel superior en servicios con valores tales como servicios de plataforma, servicios de entrega y servicios para el usuario final.
- ATUM Categoría de servicio : ofrece una clasificación más detallada dentro de cada tipo de servicio, por ejemplo, dividiendo los servicios de entrega en operaciones, seguridad y cumplimiento, y asistencia.
- ATUM Nombre del servicio : Se trata de la categorización más detallada relacionada con los servicios, por ejemplo, desglosar la categoría de servicios de operaciones en gestión de eventos, gestión de servicios de TI e implementación y administración.
- Zona de disponibilidad : Combinación de la región y la zona en la que existe un recurso. Por ejemplo, us-east-1a.
- **Azure Nombre del pedido de reserva** : El nombre o descripción del producto o servicio que se ha pedido o consumido actualmente sólo se admite para Azure.
- Nombre del clúster : el «nombre del clúster» de Kubernetes al que pertenecen los elementos de coste subyacentes, como los costes de VM, almacenamiento y red. El valor coincide con el nombre establecido por tu administrador al configurar el clúster en Cloudability.
- Nombre del Cluster : Esta es una dimensión específica del contenedor y actualmente no está soportada.
- Compute Usage Type : Práctica dimensión definida por Cloudability para comprender el tipo de computación de algunos servicios de AWS como EC2 y RDS. Esta dimensión puede ayudar al usuario a comprender rápidamente la región y la categoría (como Spot, Dedicated Host, Mirror Usage) de computación.
- Fecha : La fecha del calendario - con formato "Lun DD, AAAA" (9 de agosto de 2022).
- Día : El día del calendario numérico (por ejemplo, "9 de agosto de 2022" => 9).
- Día de la semana : El día de la semana (por ejemplo, lunes).
- Motor : El motor de la base de datos o de la caché (por ejemplo, Oracle, SQL Server, MySQL o Redis ).
- Categoría de la instancia : la categoría de « VM » o «Base de datos» a la que pertenece una instancia. Las categorías más habituales son las de propósito general, optimización informática y optimización de memoria.
- Familia de instancias : la familia de « VM » o «Database» a la que pertenece una instancia. Suele constituir el prefijo de la definición completa del tipo de instancia. En AWS, «family» incluye el tipo y la generación (por ejemplo, m6a, c6i, t3 ); en Azure, se refiere a la serie (por ejemplo, A, B, D); y en GCP, se refiere al «tipo de serie» (por ejemplo, estándar, highmem). Actualmente no se dispone de datos sobre el ICO.
- Tamaño de la instancia : el tamaño de un VM o o una base de datos. Esto se correlaciona con atributos clave de los recursos, como el número de CPU y la memoria disponible. Valores de ejemplo: «large», «xlarge» y « 2xlarge » para AWS; 2, 4 y 8 para Azure; n1-8-vcpu y n1-16-vcpu para GCP. Actualmente no se dispone de datos sobre el ICO.
- Tipo de instancia: el identificador completo del tipo de instancia de « VM » o de base de datos, que incluye tanto la familia como el tamaño. Este valor forma un componente completo de la SKU del producto (utilizado junto con la ubicación y el SO). Por ejemplo, c6g.large para AWS, Standard\_D2\_v3 para Azure y standard.c2-8-vcpu para GCP. Actualmente no se dispone de datos sobre el ICO.
- Fecha de facturación : La fecha de facturación de cualquier elemento de coste facilitada por el proveedor de la nube. Se comunica en formato "Lun DD, AAAA". El consumo de la nube durante el mes suele tener como fecha de facturación el primer día de ese mes.
- ID de factura : El ID de factura que corresponde a cualquier artículo de coste cargado, tal y como lo proporciona AWS. Para el mes en curso, en el que el coste aún no se ha facturado, verá un valor de "Estimado". Actualmente no hay datos disponibles para Azure, GCP y OCI.
- Descripción del elemento : El texto más descriptivo disponible de cada proveedor de la nube detallando cada elemento de coste. Para las últimas exportaciones detalladas de facturación, esto corresponde a « "LineItemDescription" » para « AWS », « "ProductName" + "additionalInfo" » para « Azure » y « sku.description » para « GCP » y «product/Description» para OCI.
- Tipo de arrendamiento : El modo de pago de los elementos de coste notificados, por defecto "A la carta". Los valores válidos son: A la carta, Plan de ahorro, Reservado y Spot. Se trata de una dimensión de información definida por Cloudability para apoyar la categorización de costes multi-nube.
- Mes (Categoría) : El mes en que se incurrió en cualquier elemento de coste, con formato "Lun". Ejemplos "Jun", "Jul", "Ago". Esto es útil para ver los costes por mes para cualquier año (como mostrar los costes que se produjeron en julio de cualquier año).
- Mes (Año) : El mes y el año de cualquier elemento de coste (formato Mes AAAA) útil para una correcta clasificación cronológica. Ejemplos: Julio de 2021, septiembre de 2022.
- Namespace : El "Namespace" Kubernetes asignado a los elementos de coste subyacentes que pertenecen a un cluster Kubernetes. El importe del coste asignado a cada valor de Namespace se calcula mediante Cloudability analizando la utilización de los recursos del contenedor. Los recursos individuales de la nube, como las instancias de EC2, a menudo se dividen en varios espacios de nombres debido a su naturaleza multiusuario.
- Namespace : Se trata de una dimensión específica del contenedor y actualmente no está soportada.
- Sistema operativo : El sistema operativo de las máquinas virtuales, tal como lo comunican los proveedores de la nube a efectos de facturación. Valores de ejemplo: Linux, Windows, Red Hat Enterprise Linux.
- Operación : Esta dimensión muestra la acción específica realizada sobre un recurso. Por ejemplo, si la red está transfiriendo datos hacia o desde una instancia de VM. Cuando se combina con el ID de recurso, ayuda a los clientes a comprender tanto el origen como las acciones que han contribuido al coste. En las últimas exportaciones detalladas de facturación, esto se corresponde con «Operación» en AWS, "meterName" en Azure, "skuItem.categoryResourceGroup" en GCP y “cost/productSku” en OCI.
- **Número de pieza** : Identificador utilizado para obtener el precio de un contador específico. Actualmente sólo se admite para Azure y OCI.
- ID de la cuenta del pagador : el identificador único relacionado con la cuenta de gestión de AWS, el acuerdo EA/MCA de Azure o la cuenta de facturación de GCP. AWS Las cuentas de miembros, las suscripciones a Azure, los proyectos de GCP y las tenencias de OCI suelen consolidarse en estas «cuentas de pagador».
- Nombre de la cuenta del pagador : el nombre relacionado con la cuenta de gestión de AWS, el acuerdo EA/MCA de Azure o la cuenta de facturación de GCP o la tenencia raíz de OCI. Dependiendo de su situación, este valor puede retroceder al ID de facturación único.
- Nombre del producto : el nombre oficial del producto proporcionado por el proveedor (por ejemplo, Amazon Elastic Compute Cloud, GCP Cloud Storage, Microsoft.Compute u OCI Compute).
- Región : la región en la que existe un recurso o se ha producido un cargo por uso, por ejemplo: us-east-1 para AWS, US East para Azure y us-east1 para GCP y us-ashburn-1 para OCI.
- Clase de reserva : La oferta de compromiso vinculada a cualquier elemento de coste. Algunos ejemplos de valores son las instancias reservadas "estándar" y "convertible", “EC2InstanceSavingsPlans” y “ComputeSavingsPlans” para los planes de ahorro.
- ID de reserva : ID único del compromiso (como instancia reservada y plan de ahorro) vinculado a cualquier elemento de coste proporcionado por el proveedor de la nube. Esto resulta especialmente útil para comprender exactamente qué compromiso o compromisos se han consumido en un subconjunto de uso o en un « VM » específico.
- **Nombre de la** reserva : Nombre de la instancia de reserva adquirida.
- ID de recurso : Se trata de un identificador único utilizado por el proveedor para distinguir los recursos reales que se utilizan. Por ejemplo, podría tratarse del ID de instancia de VM, el nombre del depósito de almacenamiento o el ID del volumen de datos. En el caso de GCP, actualmente utilizamos el ID de SKU para rellenar el ID de recurso.
- **Vendedor** : El vendedor oficial de servicios. El uso de esta dimensión le permite separar las tarifas de mercado de sus otros costes de nube.
- Nombre del servicio : una dimensión creada por Cloudability que estandariza las convenciones de nomenclatura de productos para AWS, Azure, GCP y OCI:
  - AWS EBS se convierte en su propio producto de primer nivel.
  - Datos unificados que estaban mezclados en varios productos:
    - AWS realiza un seguimiento parcial de Cloudwatch como producto y como EC2. Esto separa Cloudwatch en su propio servicio
    - AWS rastrea Glacier parcialmente como producto y en S3. Esto consolida todos los Glacier y S3
    - AWS dispone de un servicio de importación y exportación, así como de un servicio Snowball. Nombre de servicio las consolida.
  - En algunos casos, los datos de AWS y Azure muestran múltiples productos para los mismos servicios:
    - AWS tiene varios nombres para Support. De este modo, se consolidan todas ellas en una única partida de AWS Support.
    - AWS tiene muchos cargos administrativos listados como productos de nivel superior como Amazon Partner Network, re:Invent Tickets, etc. Se consolidan en una única partida: AWS.
    - Azure dispone de Compute, Microsoft.Compute, y Máquinas Virtuales. Todos ellos son iguales y están consolidados en Azure Compute.
  - En algunos casos, AWS y GCP se reflejan entre sí de manera bastante similar en lo que respecta a los nombres de sus servicios:
    - GCP utiliza términos como Google Compute Engine y Google App Engine ( AWS EC2 ), Google Cloud SQL, Google Cloud Firestore y Google Cloud Bigtable ( AWS RDS y DynamoDB ).
  - AWS los archivos de facturación tienen esquemas de denominación de productos incoherentes. Por ejemplo, el uso de acrónimos en lugar de nombres completos (Amazon frente a AWS ). El nombre del servicio sigue un patrón de prefijo único.
    - AWS es el prefijo para todos los Amazon Web Services. Le sigue el nombre que se ve en el menú de la consola AWS (por ejemplo, EC2, S3, RDS, Kinesis, Lambda, etc.).
    - Azure es el prefijo de todos los servicios de Microsoft Azure.
  - Se trata de una dimensión de información definida por Cloudability para apoyar la categorización de costes multi-nube.
- Tenencia : AWS dimensión específica que identifica la tenencia de las instancias de EC2. Los tres valores válidos son compartido, host y dedicado. "compartido" es el valor por defecto.
- Tipo de transacción : El tipo de transacción para cualquier elemento de coste. Los valores válidos son Uso, Cargo recurrente (por ejemplo, cargos de soporte empresarial, instancias reservadas no utilizadas), Único (por ejemplo, compras de instancias reservadas por adelantado), Impuestos y Crédito. Se trata de una dimensión de información definida por Cloudability para apoyar la categorización de costes multi-nube.
- Tipo de utilización : Especifica los detalles operativos de la partida de utilización.
  - Por ejemplo. USW1-BoxUsage:m2.2xlarge describe el uso de la caja de la instancia doble de alta memoria ExtraLarge de Amazon EC2 en la región oeste de EE.UU. (Oregón).
- Familia de uso : se trata de una dimensión estandarizada definida por Cloudability para categorizar los tipos de alto nivel de uso de la nube entre proveedores. Los valores de ejemplo incluyen Uso de Instancia, Transferencia de Datos, Almacenamiento, Solicitud de API, Red, Uso de Balanceador de Carga, Soporte y Operación del Sistema. Utilizada junto con la dimensión de informes Nombre del servicio, la Familia de uso puede ayudar a los usuarios a comprender rápidamente qué está impulsando su gasto en la nube.
- Proveedor : El proveedor de la nube asociado al elemento de coste. Los valores válidos son Amazon, Azure, GCP y OCI.
- Semana (Año) : La semana y el año de cualquier elemento de coste (formato AAAA-AA), útil para una correcta clasificación cronológica. Ejemplos: 2021-06, 2022-52.
- **Semana (Categoría)** : La semana en que se incurrió en cualquier elemento de coste, con formato "WW". Ejemplos "01", "15", "52". Esto es útil para ver los costes por semana para cualquier año (como mostrar los costes que se produjeron en la semana 1 de cualquier año).
- **Año** : El año natural en que se produjo cualquier elemento de coste, con el formato AAAA (por ejemplo, 2022).
- Zona : Este campo es específico de AWS, corresponde a la letra de una zona específica en la que existe una instancia o se ha producido un cargo de uso dentro de una Zona de Disponibilidad. Por ejemplo, la Zona AWS "a" corresponde a las Zonas de Disponibilidad " eu-west-1a " o " ap-southeast-2a ", etc. Este campo no se utiliza para Azure, GCP y OCI.

## Métricas de coste y uso

- Coste (Lista) : Esta métrica representa el coste de los artículos que se cobran a los clientes según la tarifa pública a la carta. Esto significa que los compromisos (instancias reservadas y planes de ahorro), los precios de instancias puntuales y los precios personalizados (normalmente descuentos para empresas) no se tienen en cuenta en esta métrica. La métrica se obtiene combinando los datos disponibles en los archivos de facturación detallada del proveedor y sus hojas de precios basadas en API, y actualmente se aplica a todos los servicios de AWS. En Azure, se admite la métrica "Coste (Lista)" para los servicios a la carta. Además, el uso de su instancia de compromiso bajo los tipos de arrendamiento "Reservado" y "Plan de Ahorro" son soportados para servicios selectos - actualmente Azure Compute y Azure Database solamente.

- Coste (Total) : Esta es la métrica de coste por defecto en todo Cloudability. Se trata de una métrica de "efectivo" y representa simplemente el importe facturado asociado a cualquier partida de costes, tal y como lo notifica el proveedor de la nube. Para AWS, esto corresponde a la columna « lineItem/UnblendedCost » del archivo CUR; para Azure, a la columna « CostInBillingCurrency » de la exportación de facturación estándar; para GCP, al atributo «cost» de la tabla « BigQuery »; y para OCI, a la columna « cost/myCost » del informe de costes.
  - **Cómo se asignan las partes "utilizadas" de los costes de las IR:**   
     Cuando AWS no asigna la parte "utilizada" de los RI a los recursos para UnblendedCost, Cloudability la asigna a aquellos recursos que se beneficiaron de los RI. En caso contrario, los gastos se imputarían a la cuenta en la que se adquirió la RI. Gracias a esta mejora, podrá asignar mejor las asignaciones de showback o chargeback, lo que aumentará la transparencia del uso real.
- Coste (Total Blended) : Esta métrica de costes es específica de AWS y corresponde a la columna lineItem/BlendedCost del archivo CUR. Esta métrica "mezcla" el impacto de las instancias reservadas y los planes de ahorro. Esto puede dar lugar a cifras inesperadas. Por lo tanto, se recomienda utilizar el Coste (Total) o el Coste (Amortizado).
- Coste (amortizado) : A diferencia del coste (total), que es una medida de "caja", el coste (amortizado) es una medida de coste "devengado", que representa el coste consumido durante cualquier periodo. Esta métrica es útil para garantizar que los compromisos, como las instancias reservadas y los planes de ahorro (incluidos los pagos por adelantado), se asignan al momento y lugar en que se consumen. Para los artículos de AWS, Cloudability se basa en una combinación de columnas de la CUR para obtener este valor. Para Azure se utiliza la columna CostInBillingCurrency de la exportación de facturación amortizada.   
   **Nota:** Las partidas de compromisos iniciales aparecen como 0 $ en esta métrica.
- Coste (ajustado) : Construido a partir de la métrica Coste (total), esta métrica ajusta las cifras para permitir cualquier regla de precios personalizada. Esta métrica se utiliza habitualmente con los datos de AWS para que los descuentos de empresa puedan tenerse en cuenta de forma coherente a nivel de partida de uso en lugar de aparecer de forma masiva a final de mes. Esta métrica sólo aparece para los clientes de Cloudability que han activado el módulo de precios personalizados.
- Coste (Amortizado Ajustado) : Construido a partir de la métrica Coste (Amortizado), esta métrica ajusta las cifras para permitir cualquier regla de precios personalizada. Esta métrica se utiliza normalmente con los datos de AWS para que los descuentos de empresa se puedan tener en cuenta de forma coherente a nivel de partida de uso en lugar de aparecer de forma masiva a final de mes. Esta métrica sólo aparece para los clientes de Cloudability que han activado el módulo de precios personalizados.
- Ajuste de costes : Importe por el que se ha ajustado el coste.

Nota:

**Esta opción no está disponible a menos que esté activada la opción Precios personalizados.**

- **Transferencia de datos ( GiB ) : Cantidad de datos transferidos en un período de tiempo particular.**
- **GiB Horas : Un gibibyte-hora se refiere al número de gibibytes almacenados en una plataforma en nube en un periodo horario determinado.**

- GiB Meses : se refiere al número de gibibytes de un recurso para AWS, Azure, GCP y OCI en un periodo mensual concreto.
- Peticiones de E/S : Describe el número de peticiones de datos de un servicio de base de datos.
- Meses IOPS : Las operaciones de entrada y salida de almacenamiento por segundo asociadas a los servicios de almacenamiento.
- Horas bajo demanda : La cantidad de horas de computación bajo demanda utilizadas durante el periodo del informe. Para más información, consulte [Dimensiones y métricas de uso frecuente](frequently-used-dimensions-and-metrics.html).
- Tarifa (Blended) : Para cuentas de Facturación Consolidada, la tarifa efectiva de la partida calculada como media del coste de instancias idénticas operando en esa hora en la misma Zona de Disponibilidad.
- Tarifa (sin mezclar) : Coste por hora de una partida. Esto se resume en las horas de un día. Para obtener más información, consulte [Emerge](http://blog.cloudability.com/what-you-need-to-know-about-blended-rates-on-aws/ "(se abre en una pestaña o una ventana nueva)").
- Peticiones : Número de recursos informáticos utilizados en las unidades especificadas por cada servicio. Por ejemplo, su servicio puede determinar el precio en función de la cantidad de almacenamiento, el número de solicitudes o las horas de funcionamiento. Para obtener más información sobre cómo se calcula el uso, haga clic en [AWS Precios](http://aws.amazon.com/pricing/ "(se abre en una pestaña o una ventana nueva)").
- Tasa de Cobertura Reserv ada : Porcentaje del total de horas de uso durante el periodo en el que se aplicaron Instancias Reservadas. Para más información, consulte [Dimensiones y métricas de uso frecuente](frequently-used-dimensions-and-metrics.html).
- Horas reservadas : Número de horas de cálculo reservadas utilizadas durante el periodo de referencia. Para más información, consulte [Dimensiones y métricas de uso frecuente](frequently-used-dimensions-and-metrics.html).
- Recuento de recursos : Esta nueva métrica indica el recuento de recursos únicos en un periodo de tiempo determinado. Esto permite a los clientes comprender el número de activos que controlan y cómo fluye a lo largo del tiempo.
- Horas de uso : Número de recursos informáticos utilizados en las unidades especificadas por cada servicio. Por ejemplo, su servicio puede determinar el precio en función de la cantidad de almacenamiento, el número de solicitudes o las horas de funcionamiento.
- Cantidad consumida : Cantidad consumida para el artículo de coste. La unidad está vinculada a la SKU específica y a cómo se carga. Por ejemplo, este número representará el número de horas de instancia consumidas para las máquinas virtuales, GiB-months para el almacenamiento y GiB para los datos transferidos. Para los gastos de AWS y Azure, esta métrica complementa las métricas de tarifa (sin mezclar) y coste (total) cuando se utilizan juntas en un informe para explicar la cifra que le ha cobrado el proveedor de la nube.

## Métricas de sostenibilidad

- Emisiones de carbono estimadas ( MTCO2e ) : esta métrica captura las emisiones de carbono estimadas en toneladas métricas de equivalentes de dióxido de carbono.
- **Energía consumida ( kWh )** : Energía consumida en kilovatios hora.
- **Emisiones de carbono operativas** **( MTCO2e )** : este indicador representa las emisiones de carbono generadas durante el funcionamiento diario de los servicios en la nube. Proviene principalmente de la electricidad que se utiliza para alimentar y refrigerar los centros de datos mientras se ejecutan las cargas de trabajo.
- **Emisiones de carbono incorporadas** **( MTCO2e )** : este indicador representa la proporción de emisiones de carbono asociadas a la producción y al ciclo de vida de la infraestructura en la nube. En el contexto de la nube, se calcula asignando una parte de las emisiones totales incorporadas de los servidores físicos y los equipos en función de tu uso específico.
