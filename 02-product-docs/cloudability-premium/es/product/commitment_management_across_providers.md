---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Cómo difiere la gestión de compromisos entre los distintos proveedores de servicios en la nube"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Optimización de costes en la nube en Cloudability"
source_path: "product/commitment_management_across_providers.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cómo difiere la gestión de compromisos entre los distintos proveedores de servicios en la nube

## Finalidad

El objetivo de este documento es presentar cómo funcionan los descuentos basados en compromisos en los distintos proveedores de servicios en nube (CSP).

## Introducción a los tipos de compromiso

Todos los modelos de precios de descuento basados en el compromiso persiguen el mismo objetivo: intercambiar la previsibilidad del uso y el bloqueo del proveedor por un precio con descuento. Cada proveedor ofrece una forma de pagar menos que a la carta si estás dispuesto a comprometerte, a menudo con una huella de recursos y un nivel de gasto específicos. Los detalles varían, pero las cuestiones prácticas son universales, *¿Qué tipo de descuento estoy recibiendo? ¿Cuánto me comprometo a gastar y durante cuánto tiempo? ¿Cómo se aplica y se comunica el descuento? ¿Cómo se mide el rendimiento?*

En primer lugar, definiremos algunos términos para simplificar el debate.

Compromiso **-** Compromiso es el término que utilizamos para referirnos a estos descuentos en Cloudability.

**Tipo** de compromiso - Un tipo de compromiso es el término Cloudability elegido para describir las diferentes versiones de estos contratos. (Tipo) se utiliza explícitamente para diferenciar el modelo de tarificación del nombre del servicio subyacente. Como pronto aprenderá, algunos servicios, especialmente los informáticos, tienen múltiples tipos de compromiso aplicables. En particular, esta definición se [define en FOCUS](https://focus.finops.org/focus-columns/#commitment-discount-type "(se abre en una pestaña o una ventana nueva)"). Estamos de acuerdo y aceptamos esta definición

**Compromisos basados en recursos -** Entre las nubes, surgen dos patrones. En primer lugar, los compromisos basados en los recursos ofrecen un descuento a cambio de un compromiso de uso de una determinada cantidad de un producto o servicio.

**Compromisos basados en el gasto** - Estos compromisos ofrecen un descuento a cambio de comprometerse a gastar una determinada cantidad en un producto o servicio. Los compromisos basados en el gasto difieren de los compromisos basados en los recursos en que cubren un conjunto más amplio de usos, pero requieren una atención especial a la utilización para no adquirir más compromisos de los que su combinación de cargas de trabajo puede consumir.los compromisos basados en recursos tienen la ventaja de un mayor descuento con una matemática de equilibrio más clara, mientras que la contrapartida es una alineación más estricta con los atributos de uso.

**Categoría** de compromiso - Nos referiremos a si un tipo de compromiso puede clasificarse como recurso o gasto como la categoría de compromiso.cabe destacar que esta definición también [figura en FOCUS](https://focus.finops.org/focus-columns/#commitment-discount-category "(se abre en una pestaña o una ventana nueva)"). Estamos de acuerdo y aceptamos esta definición.

Los PEC tienen nombres formales para cada tipo de compromiso. Aquí intentaremos explicar de forma general cómo varían los nombres de los compromisos según el proveedor -

**Instancia reservada (RI, AWS, Azure ):** ofrece un descuento a cambio de comprometerse a utilizar una cantidad específica de un producto o servicio definido. Comúnmente utilizado para servicios en los que el uso subyacente se define como una instancia de computación. Por ejemplo, la terminología cambiará a «nodo reservado» para AWS Redshift, ya que el uso subyacente se define en nodos. En cualquier caso, en estas situaciones, este concepto funciona de forma similar.

Tenga en cuenta que las instancias reservadas se suelen abreviar como RI.

**Plan de ahorro - SP ( AWS, Azure ) -** Ofrece un descuento a cambio de comprometerse a gastar una cantidad específica (a menudo expresada en dólares por hora) en servicios elegibles. Este tipo de compromiso es específico de AWS y Azure, y solo se aplica al gasto en computación. En el caso de Azure, los planes de ahorro se desglosan explícitamente en una sección separada del resto de reservas en las páginas de compra de su consola.

Tenga en cuenta que los planes de ahorro se suelen abreviar como SP.

**Reservas ( Azure ) -** Azure 's término genérico para los compromisos a través de múltiples servicios.

**Plan de compra anticipada (PPP, Azure ):** una opción de compromiso de gasto de Azure que utiliza créditos fungibles que no caducan por horas y se aplican a todos los servicios elegibles.

Tenga en cuenta que los planes de compra se suelen abreviar como PPP.

**Descuento por uso comprometido** **(CUD, GCP ):** término genérico utilizado por GCP para referirse a los compromisos en múltiples servicios.

**Gastar CUD** **( GCP,** unidades de compromiso de gasto): variante de compromiso basada en el gasto de GCE. Es funcionalmente similar a un plan de ahorro AWS / Azure. Google Compute Engine La variante CUD de gasto (GCE) se denomina específicamente GCE Flex-CUD, mientras que el CUD de recursos es simplemente un GCE CUD. GCP es único en comparación con AWS y Azure, ya que prioriza los compromisos para servicios fuera de la computación.

## Introducción a las opciones de compra

A continuación, hay un puñado de opciones diferentes que definen cómo se estructura e implementa un compromiso.

**Plazo ( AWS,** **Azure, GCP ) -** Término universal utilizado para describir la duración del compromiso, normalmente de 1 o 3 años, con casos especiales en los que puede ser de tan solo 1 mes o de hasta 6 años.

**Opción de pago ( AWS, GCP ):** término que utiliza AWS para describir cómo se factura un compromiso. AWS Tiene tres opciones para muchos de sus compromisos: sin pago inicial (similar al pago mensual de Azure ), pago inicial parcial (donde la mitad del costo se factura por adelantado) y pago inicial. Al igual que Azure, estas opciones de pago ofrecen diferentes descuentos. Como se menciona en Cloudability, utilizamos el término «opción de pago», independiente del proveedor. Este término no se define explícitamente en GCP, ya que todos sus compromisos son sin pago inicial. No obstante, para representar esta información de manera uniforme, asignamos este parámetro a GCP.

**Frecuencia de facturación ( Azure** ) - El término Azure se utiliza para describir cómo se factura un compromiso. Azure tiene dos opciones para muchos de sus compromisos, mensual y por adelantado. Estas frecuencias de facturación conllevan diferentes descuentos. En Cloudability utilizamos el término agnóstico de proveedor, Opción de Pago, para Azure.

**Región ( AWS, Azure, GCP ):** término universal entre los proveedores que define dónde se encuentran los recursos físicos, lo que influye en la agrupación, el potencial de utilización y la flexibilidad. La región es relevante para la mayoría de los tipos de compromiso, excepto los planes de ahorro « AWS » y « Azure ».

**Zona** de Disponibilidad **( AWS** ) - Una Zona de Disponibilidad (AZ) es uno o más centros de datos discretos con energía, refrigeración y redes independientes, conectados dentro de la región mediante conectividad de baja latencia. Algunos compromisos de AWS pueden adquirirse por AZ en lugar de por región. En el caso de los compromisos basados en zonas de disponibilidad, los descuentos son intrínsecamente menores, ya que el contrato ofrece menos previsibilidad al proveedor.

## Introducción a la estructura de cuentas

Más allá de estas opciones básicas de pago, es crucial comprender cómo la estructura de la cuenta dictará la forma de realizar un compromiso.

**Cuenta pagadora -** Cloudability 's vendor agnostic term to describe the parent account experiencing charges.

**Cuenta vinculada -** Cloudability 's vendor agnostic term to describe the child account experiencing charges. Las cuentas vinculadas tienen una relación de muchos a uno con las cuentas pagadoras.

**Unidades** **organizativas** **(OU) - AWS -** Un contenedor similar a una carpeta que se utiliza dentro de AWS Organizations para agrupar varias cuentas AWS bajo una jerarquía común (Raíz → OU → Cuentas). Las OU no poseen recursos ni incurren en gastos por sí mismas: existen para organizar cuentas y aplicar la gobernanza a escala. Estas unidades pueden anidarse y operar por encima del nivel en el que se adquiere un compromiso.

**Cuenta de gestión ( AWS ) -** Similar a la cuenta de pago Cloudability, esta cuenta AWS representa donde los usuarios pueden crear políticas y delegar cuentas de miembros. La cuenta de gestión no tiene por qué estar directamente bajo la raíz, puede situarse en cualquier lugar de la organización.

Cuenta **de miembro** **( AWS ):** similar a una cuenta vinculada, en esta cuenta AWS es donde residen los recursos y se generan los costos.

**Cuenta** **de facturación** **( Azure ):** la cuenta que define el modelo de facturación (EA, MCA, CSP/MPA). Al igual que AWS OUs, este constructo se sitúa por encima del ámbito de relevancia de un compromiso.

Perfil de **facturación ( Azure ) -** Un perfil de facturación representa una factura y la información de facturación relacionada, como los métodos de pago y la dirección de facturación. Es similar a una cuenta de pagador en Cloudability.

**Suscripción ( Azure ) -** En Azure, una suscripción es un contenedor de recursos que también actúa como unidad de facturación. El uso generado por los recursos de una suscripción se factura a través de cualquier modelo de cuenta de facturación en el que se encuentre (EA, MCA, CSP/MPA).

Suscripción de **facturación** **( Azure** ) - Partiendo de la definición de una suscripción, una suscripción de facturación Azure es la suscripción a través de la cual el uso pasa a su factura. Es similar a una cuenta vinculada en Cloudability.

Alcance ( **Azure** ) - En el momento de la compra, el alcance de un compromiso puede cubrir una suscripción o varias. Cuando se comparte, el descuento se aplica a las suscripciones elegibles dentro de su contexto de facturación.

- Cuando se trata de una suscripción única, el descuento por reserva se aplica a los recursos coincidentes de la suscripción seleccionada.
- Cuando se trata de un único grupo de recursos, el descuento por reserva sólo se aplica a los recursos coincidentes del grupo de recursos que seleccione.
- Para los clientes de Enterprise Agreement, el contexto de facturación son todas las suscripciones de la inscripción EA.
- Para los clientes de pago por uso, el contexto de facturación son todas las suscripciones elegibles creadas por el administrador de la cuenta.
- Para Microsoft Customer Agreement, el contexto de facturación es el perfil de facturación.

**Cuenta de facturación ( GCP ):** cuenta de pagador de GCP donde se almacenan los recursos y se generan los costes.

**Proyecto ( GCP ) -** Cuenta vinculada de GCP donde se almacenan los recursos y se generan los costes.

## Introducción a la flexibilidad del tamaño de instancia

**Acerca de la flexibilidad del tamaño de instancia para las versiones de RDS**

Las instancias reservadas (RI) de Amazon RDS ahora se benefician de [la flexibilidad del tamaño de instancia](https://www.ibm.com/links?url=https%3A%2F%2Faws.amazon.com%2Fabout-aws%2Fwhats-new%2F2017%2F10%2Famazon-rds-reserved-instances-offer-instance-size-flexibility%2F "(se abre en una pestaña o una ventana nueva)") (ISF) de manera muy similar a como se aplica la ISF para las instancias de EC2. Hemos actualizado el motor que impulsa nuestro RI Planner para adaptarlo al cambio en nuestras recomendaciones para las instancias de RDS. Comprar con la ventaja ISF reducirá sus gastos administrativos y le permitirá obtener el máximo ahorro.

**¿Qué es ISF?**

ISF es una característica de las instancias de infraestructura (RI) de RDS que permite aplicar los ahorros de una RI a cualquier tamaño de instancia dentro de una familia. Obtienes este beneficio automáticamente cuando compras una RI dentro de la misma región AWS (para configuraciones Single-AZ y Multi-AZ), motor de base de datos y familia de instancias. ISF está disponible para los siguientes motores de bases de datos: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (edición Bring Your Own License).

**¿Cómo funciona ISF?**

ISF gestiona sus reservas mediante un sistema basado en puntos, en el que una escala determina las unidades asignadas a cada tamaño dentro de una familia. Cuando ejecuta una instancia, por ejemplo, db.m3.large, cualquier ISF RI dentro de la familia db.m3 puede aplicarse a la instancia, y el número de puntos que tiene su RI en relación con los puntos para el tamaño de la instancia ejecutada determina cuánto o cuántos RI consume esa hora de instancia. El número de unidades normalizadas por tamaño de instancia de base de datos es el siguiente:

**ISF en el Planificador de RI**

En nuestro Planificador RI, en la pestaña « RDS » (Planificar donaciones), tenemos en cuenta la ISF a la hora de hacer recomendaciones. Seguimos analizando su uso por segundo de las instancias y tenemos en cuenta todo su inventario de RI, incluidas las RI ISF y no ISF, antes de hacer una recomendación. En el caso de las RI de ISF, dado que cualquier tamaño de RI puede aplicarse a una instancia que se ejecute dentro de una familia, ya no será necesario adquirir varios tamaños, sino que se podrá adquirir por familia, base de datos y región en función de unidades normalizadas. En la práctica, puede abstraer el concepto de compra a su perfil de tipo de instancia y, en su lugar, simplemente comprar puntos.

Hay varias formas de lograrlo, pero tras numerosas pruebas internas y conversaciones con nuestros principales clientes, hemos establecido un patrón eficaz que hemos incorporado al planificador.

En el siguiente esquema, el uso de muestras durante un período de tiempo ayuda a ilustrar cómo funciona el ISF. Para cada unidad de tiempo, imagina que estás ejecutando una combinación de instancias. [El objetivo de la línea de flotación](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Fcase-study%2Fatlassian-leverages-apptio-cloudabilitys-big-data-analytics-engine-to-improve-reserved-instance-coverage%2F "(se abre en una pestaña o una ventana nueva)") sigue siendo válido y, en el caso de una utilización del 100 % de RI, le recomendamos que adquiera 10 RI grandes, ya que son el tamaño de instancia más pequeño disponible. Tienes una compra de RI y, cuando tu uso normalizado se mantenga igual o aumente, tus RI seguirán utilizándose perfectamente.

La página **Detalles** del planificador de RI muestra cómo aplicamos ISF a una instancia de RDS.

**Nuestra estrategia ISF « RDS » (Inversión socialmente responsable)**

La filosofía que adoptamos con EC2 ISF se centró en reducir sus gastos generales de gestión y maximizar sus ahorros. Para RDS ISF también, recomendamos el tamaño de instancia más pequeño posible y Single-AZ. Esto permite una cobertura máxima con el menor número posible de paquetes RI. Tenga en cuenta que los paquetes serán grandes y es posible que tenga que [solicitar un aumento](https://www.ibm.com/links?url=https%3A%2F%2Fsignin.aws.amazon.com%2Fsignin%3Fredirect_uri%3Dhttps%253a%252f%252fconsole.aws.amazon.com%252fsupport%252fhome%253fstate%253dhashargs%252523case%25252fcreate%25253fissuetype%25253dservice-limit-increase%252526limittype%25253dservice-code-rds-instances%252526type%25253dservice_limit_increase%252526servicelimitincreasetype%25253drds-instances%2526isauthcode%253dtrue%26client_id%3Darn%253aaws%253aiam%253a%253a015428540659%253auser%252fsupportcenter%26forcemobileapp%3D0%26code_challenge%3Drqkdlstpj9sj50c95lgyoxfcdgnasohhi8yrhlwilo0%26code_challenge_method%3Dsha-256 "(se abre en una pestaña o una ventana nueva)") del límite de compra de RI a Amazon para poder adquirir una gran cantidad de instancias de tamaño pequeño.

Se beneficiará de un ciclo de vida del RI más optimizado con la compra de grandes cantidades, en lugar de como ocurría en el pasado, cuando se realizaban múltiples compras de diferentes tamaños por familia. Esta estrategia también le ayudará a gestionar mejor su inventario si su uso disminuye, ya que le permitirá vender un número mucho más detallado de unidades RI para adaptarse a los nuevos patrones de uso.

**¿Qué es ISF?**

ISF es una característica de las instancias de infraestructura (RI) de RDS que permite aplicar los ahorros de una RI a cualquier tamaño de instancia dentro de una familia. Obtienes este beneficio automáticamente cuando compras una RI dentro de la misma región AWS (para configuraciones Single-AZ y Multi-AZ), motor de base de datos y familia de instancias. ISF está disponible para los siguientes motores de bases de datos: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (edición Bring Your Own License).

**¿Cómo funciona ISF?**

ISF gestiona sus reservas mediante un sistema basado en puntos, en el que una escala determina las unidades asignadas a cada tamaño dentro de una familia. Cuando ejecuta una instancia, por ejemplo, db.m3.large, cualquier ISF RI dentro de la familia db.m3 puede aplicarse a la instancia, y el número de puntos que tiene su RI en relación con los puntos para el tamaño de la instancia ejecutada determina cuánto o cuántos RI consume esa hora de instancia. El número de unidades normalizadas por tamaño de instancia de base de datos es el siguiente:

**ISF en las Recomendaciones de Compromiso**

En nuestras Recomendaciones de Compromiso, tenemos en cuenta el ISF a la hora de formular recomendaciones. Seguimos analizando su uso por segundo de las instancias y tenemos en cuenta todo su inventario de RI, incluidas las RI ISF y no ISF, antes de hacer una recomendación. En el caso de las RI de ISF, dado que cualquier tamaño de RI puede aplicarse a una instancia que se ejecute dentro de una familia, ya no será necesario adquirir varios tamaños, sino que se podrá adquirir por familia, base de datos y región en función de unidades normalizadas. En la práctica, puede abstraer el concepto de compra a su perfil de tipo de instancia y, en su lugar, simplemente comprar puntos.

Hay varias formas de lograrlo, pero tras numerosas pruebas internas y conversaciones con nuestros principales clientes, hemos establecido un patrón eficaz que hemos incorporado al planificador.

En el siguiente esquema, el uso de muestras durante un período de tiempo ayuda a ilustrar cómo funciona el ISF. Para cada unidad de tiempo, imagina que estás ejecutando una combinación de instancias. [El objetivo de la línea de flotación](https://www.ibm.com/links?url=https%3A%2F%2Fwww.apptio.com%2Fcase-study%2Fatlassian-leverages-apptio-cloudabilitys-big-data-analytics-engine-to-improve-reserved-instance-coverage%2F "(se abre en una pestaña o una ventana nueva)") sigue siendo válido y, en el caso de una utilización del 100 % de RI, le recomendamos que adquiera 10 RI grandes, ya que son el tamaño de instancia más pequeño disponible. Tienes una compra de RI y, cuando tu uso normalizado se mantenga igual o aumente, tus RI seguirán utilizándose perfectamente.

La página Detalles de las recomendaciones de compromiso muestra cómo aplicamos ISF a una instancia de RDS.

**Nuestra estrategia ISF « RDS » (Inversión socialmente responsable)**

La filosofía que adoptamos con EC2 ISF se centró en reducir sus gastos generales de gestión y maximizar sus ahorros. Para RDS ISF también, recomendamos el tamaño de instancia más pequeño posible y Single-AZ. Esto permite una cobertura máxima con el menor número posible de paquetes RI. Tenga en cuenta que los paquetes serán grandes y es posible que tenga que [solicitar un aumento](https://www.ibm.com/links?url=https%3A%2F%2Fsignin.aws.amazon.com%2Fsignin%3Fredirect_uri%3Dhttps%253a%252f%252fconsole.aws.amazon.com%252fsupport%252fhome%253fstate%253dhashargs%252523case%25252fcreate%25253fissuetype%25253dservice-limit-increase%252526limittype%25253dservice-code-rds-instances%252526type%25253dservice_limit_increase%252526servicelimitincreasetype%25253drds-instances%2526isauthcode%253dtrue%26client_id%3Darn%253aaws%253aiam%253a%253a015428540659%253auser%252fsupportcenter%26forcemobileapp%3D0%26code_challenge%3Drqkdlstpj9sj50c95lgyoxfcdgnasohhi8yrhlwilo0%26code_challenge_method%3Dsha-256 "(se abre en una pestaña o una ventana nueva)") del límite de compra de RI a Amazon para poder adquirir una gran cantidad de instancias de tamaño pequeño.

Se beneficiará de un ciclo de vida del RI más optimizado con la compra de grandes cantidades, en lugar de como ocurría en el pasado, cuando se realizaban múltiples compras de diferentes tamaños por familia. Esta estrategia también le ayudará a gestionar mejor su inventario si su uso disminuye, ya que le permitirá vender un número mucho más detallado de unidades RI para adaptarse a los nuevos patrones de uso.

## Diferencias generales

Hay varios matices que también es pertinente señalar aquí.

- En AWS y Azure, los compromisos de recursos se adquieren en función del número de unidades de un tamaño predeterminado. Esto contrasta con GCP, donde los CUD de recursos GCE se compran en subcantidades discretas (memoria vCPU,, SSD, GPU).
- AWS y Azure 's spend commitments purchased in terms of cost of the commitment. GCP Los CUD, por el contrario, se compran por su equivalente bajo demanda. Tenga en cuenta que esto cambiará en enero de 2026.
- AWS y Azure incluyen una métrica de cobertura, en términos de horas de uso, en el archivo de facturación. GCP en particular, no incluye esta métrica.

A continuación, empezaremos a profundizar en cómo Cloudability ayuda a optimizar su gasto en la nube.

**Tema principal:** [Optimización de los costes de la nube en Cloudability](../product/cloud_cost_optimization.html)
