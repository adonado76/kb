---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Preguntas más frecuentes"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-benchmarking/troubleshooting/faq.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Preguntas más frecuentes

## P. ¿Qué grado de precisión tienen estos puntos de referencia?

A Son estadísticamente sólidos, pero no precisos al centavo. Los puntos de referencia nos indican si estamos por debajo, en la media o por encima en comparación con nuestros pares y en qué aspectos debemos centrar nuestras preguntas. Seguimos basándonos en nuestros propios datos detallados para tomar las decisiones finales.

## P. ¿Podemos ver quiénes son los compañeros?

A Núm. Los participantes son anónimos por diseño. Solo vemos distribuciones agregadas (medianas, cuartiles, bandas), no organizaciones con nombre.

## P. ¿Estar por encima de la media significa que somos ineficientes?

A No automáticamente. Significa que gastamos más que el típico par en esa métrica. Eso podría ser ineficiencia, o podría reflejar decisiones deliberadas como una mayor resiliencia, una regulación más estricta o un modelo de abastecimiento diferente. El punto de referencia nos indica dónde investigar, no que algo esté automáticamente mal.

## P. ¿Por qué este número es diferente al número de mi equipo?

A Porque probablemente estemos utilizando un alcance o una definición diferentes. Las métricas de referencia utilizan definiciones estándar alineadas con TBM, por lo que son comparables entre organizaciones. Cuando observamos diferencias con respecto a las cifras internas, primero conciliamos el alcance y, a continuación, decidimos qué métrica utilizar para cada fin.

## P. ¿Podemos cambiar la forma en que se calcula el índice de referencia?

A Núm. Las definiciones de los puntos de referencia son fijas, por lo que todos comparan lo mismo. Podemos crear métricas internas personalizadas en Costing si necesitamos analizar los datos de otra manera, pero eso es independiente del punto de referencia externo.

## P. Tengo un problema que no puedo resolver por mí mismo. ¿Cómo puedo solicitar ayuda?

A Los tickets de soporte técnico pueden enviarse y revisarse en [el Centro de ayuda de](https://www.ibm.com/mysupport/ "(se abre en una pestaña o una ventana nueva)") IBM. Además, los clientes pueden visitar [Community,](https://community.ibm.com/community/user/groups/community-home?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(se abre en una pestaña o una ventana nueva)") donde otros clientes de IBM Apptio e IBMers colaboran y comparten conocimientos.

## P. Tengo una idea para mejorar Interactive Benchmarking. ¿Cómo puedo enviar la idea a IBM?

A Los clientes pueden enviar sus ideas a través [del portal de ideas](https://ideas.ibm.com/products/7428698806022729746 "(se abre en una pestaña o una ventana nueva)") IBM.

## P. ¿Puedo acceder a los detalles de los índices de referencia de años anteriores?

A No con Interactive Benchmarking. Sin embargo, los informes de referencia habilitados para el cálculo de costes pueden proporcionar la información (si se integran con el cálculo de costes).

## P. Si se integra con Costing, ¿desde qué entorno del proyecto Costing se recuperan los datos de gasto en TI?

A. Solo el entorno de producción.

## P. ¿Debo incluir los gastos que están fuera del control de la organización de TI?

A Núm. No incluya ningún gasto, incluido el «Shadow IT» (TI en la sombra), controlado por otras áreas de su empresa en general.

## P. ¿Qué grupos de costes debo excluir de la evaluación comparativa de la infraestructura?

A Excluir lo siguiente:

- Instalaciones y energía
- Telecomunicaciones
- Servicios internos
- Otros

## P. ¿Dónde incluyo los gastos que pertenecen al grupo de costes de telecomunicaciones?

A Asigne los gastos del grupo de costes de telecomunicaciones a la subtorre «Transporte».

## P. ¿Existen métricas de referencia de infraestructura para los grupos de costes «Instalaciones y energía», «Servicios internos» u «Otros»?

A Núm.

## P. ¿Cómo se contabilizan los costes de la nube pública en las métricas de evaluación comparativa de la infraestructura y l OpEx?

R. En una evaluación comparativ OpEx, los costes de la nube pública se incluyen en el conjunto de costes de servicios externos. En la evaluación comparativa del sector, los costes de la nube pública se incluyen en el gasto en TI.

## P. ¿Incluyo a los contratistas?

A Sí.

## P. ¿Dónde asigno los datos comerciales o las suscripciones a información?

A Asigna estos a la agrupación de costes «Otros».

## P. ¿Qué puedo hacer si quiero ver diferentes KPI para un área específica, por ejemplo, dividirlos por dispositivos en lugar de por usuarios?

A Todos los KPI disponibles aparecen en el producto.

## P. ¿Qué gastos excluyo del gasto total en TI?

A Debe excluir dos tipos de cargos para la evaluación comparativa:

1. Hardware o software específico para la industria, por ejemplo, equipos de fabricación robótica:
   - Equipos fabricados o adquiridos con fines distintos al procesamiento de datos, pero que cuentan con componentes informáticos, tales como máquinas de fabricación robótica, dispositivos especializados para usuarios finales dedicados al comercio de acciones, como auriculares para operadores bursátiles, cajeros automáticos, dispositivos especializados para puntos de venta, escáneres y monitores y sensores de presión arterial en un sistema de control de supervisión y adquisición de datos (SCADA).
   - Equipos de procesamiento de datos similares a electrodomésticos o patentados que tienen un único propósito (normalmente vertical en la industria) y que no pueden utilizarse para otros fines generales, como un ordenador que solo puede controlar el flujo de electricidad a través de la red eléctrica. Dado que no se puede reutilizar, no se incluye en nuestro modelo. Tenga en cuenta que otros sistemas que recopilan datos de este tipo de ordenadores y que pueden utilizarse para otros fines no se consideran tecnología operativa y, por lo tanto, entran dentro del ámbito de nuestro modelo.
2. Gastos que están fuera del control de TI (por ejemplo, «TI en la sombra»).
   - Costes de tecnología o servicios que se revenden, como los salarios de los desarrolladores que participan en la creación de paquetes de software comercial o los empleados con conocimientos de TI que prestan servicios a los clientes externos de la organización.
   - «Cargos cruzados» internos y asignaciones corporativas relacionadas con gastos únicos grandes, significativos o inusuales, tales como reducciones de plantilla, despidos, traslados, jubilaciones, recursos humanos y salario del presidente.
   - Suscripciones y servicios de datos empresariales, como Bloomberg, incluso si son gestionados por la organización de TI.
   - Servicios de externalización de procesos empresariales (BPO), en los que las organizaciones externalizan funciones empresariales completas, como la gestión de nóminas o prestaciones. Esto incluye los casos en los que el proveedor de BPO proporciona acceso al software y también garantiza que los resultados de sus servicios cumplirán los requisitos empresariales, como las normativas fiscales y de retención. El software como servicio ( SaaS ) proporcionado por el proveedor, que solo garantiza que el software funcionará según lo especificado, está dentro del alcance del gasto en TI. La externalización tradicional de funciones de TI, como servidores y correo electrónico, también entra dentro del ámbito de aplicación.
   - La TI en la sombra, que es el gasto estándar en TI que está fuera del control y el soporte del departamento de TI.

## P. ¿Qué gastos excluyo de los parámetros de referencia de infraestructura?

A Los datos de nuestro Benchmark de Infraestructura proceden de ISG. Para garantizar una comparación equitativa, no incluya ninguno de los cuatro gastos comunes que se indican a continuación en ninguno de sus costes cuando compare su rendimiento con los parámetros de referencia de infraestructura:

- Instalaciones y energía
- Servicios internos
- Otros
- Telecomunicaciones

Nota: Asigne todos los gastos del grupo de costes de telecomunicaciones a Red - Transporte, ya que es ahí donde ISG los analiza.

![Gastos comunes de telecomunicaciones para la red](../../resources/images/it%20benchmarking_images/cost-pool-expenses.jpg)

## P. ¿La categoría «Red – Transporte» incluye todos los gastos comunes de telecomunicaciones en los índices de referencia de infraestructura de ISG?

A Sí. ISG asigna todos los gastos relacionados con el grupo de costes «Telecomunicaciones a red: transporte». No incluya los gastos del fondo común de telecomunicaciones para ningún otro índice de referencia de infraestructura.

## P. ¿Cómo contabilizo la depreciación y amortización (D&A)?

Referencias del sector: Las métricas de rendimiento (obtenidas de Rubin) incluyen únicamente los desembolsos en efectivo. La métrica de gasto debe incluir todos los gastos de capital y gastos operativos del año fiscal actual. No incluya D&A en los índices de referencia del sector.

Puntos de referencia de IT OpEx : Las métricas de rendimiento (obtenidas de datos de Apptio ) incluyen únicamente los gastos operativos. Incluya los gastos de D&A, pero no incluya los gastos capitalizados en los índices de referencia de TI OpEx

Puntos de referencia de infraestructura: Las métricas de rendimiento (proporcionadas por ISG) incluyen los desembolsos de efectivo y la depreciación. Incluya los gastos de D&A, así como los gastos capitalizados, en los parámetros de referencia de infraestructura.

Nota: Si ha configurado Benchmarking en Transparencia de costes, su programa de gastos de D&A se importará automáticamente. Si utiliza Interactive Benchmarking, sus gastos de D&A se calculan utilizando un plan de amortización lineal de tres años de sus gastos de capital.

## P. ¿Cómo se contabilizan los costes de la nube pública en Opex e Infra BM?

A. Referencias del sector: todos los gastos en nube pública se incluyen en el gasto en TI.

OpEx Puntos de referencia: Todos los gastos de la nube pública se incluyen en el grupo de costes «Servicios externos» y posteriormente se asignan a «Torre de TI» y «Aplicaciones».

Puntos de referencia de infraestructura: los puntos de referencia de infraestructura son solo para gastos locales. Todos los gastos de la nube pública deben excluirse. Esto se gestiona automáticamente en el modelo de costes Apptio asignando todos los costes de la nube a Entrega = «Nube pública» y excluyendo estos costes de los costes de infraestructura a nivel de torre que se comparan con los puntos de referencia de infraestructura.

## P. ¿Puedo comparar por separado unidades de negocio o regiones específicas?

La mejor manera de comparar unidades de negocio o regiones individuales es introducir los datos financieros y los volúmenes unitarios específicos de cada unidad de negocio o región en Interactive Benchmarking. El software le ofrece la opción de ajustar los arquetipos o compararlos con diferentes sectores según le convenga.

Nota: No existe ninguna funcionalidad que permita conservar los datos para diferentes unidades de negocio/regiones. Tendrá que actualizar los datos a medida que analice las diferentes unidades de negocio/regiones. Los clientes pueden modificar los informes de referencia estándar de costes para mostrar y comparar diferentes referencias basadas en la unidad de negocio o la región. Esto requiere informes personalizados para crear estas vistas y no se proporciona de forma predeterminada.

## P. ¿Debo incluir los gastos de los contratistas?

A Sí. La única razón para no incluir los gastos de los contratistas es si forman parte de los servicios de externalización de procesos empresariales (BPO).

## P. ¿Dónde asigno los gastos de TI específicos del sector, como máquinas de resonancia magnética, robots de cadena de montaje y su software, bombas de infusión y dispositivos POS en el comercio minorista?

A El gasto en TI específico del sector no se incluye en los parámetros de referencia de costes de TI y debe excluirse.

## P. ¿Cómo gestiono el caso en el que mis datos de costes subyacentes están en diferentes divisas?

A.You Primero querrá consolidar las distintas monedas de los datos de costes en una única vista de moneda. A continuación, puede asignar sus datos de costes en una sola moneda a los valores de referencia, tal y como se detalla en la guía de configuración. De forma predeterminada, el modelo de costes « Apptio » requiere que se configure una «divisa base» para estandarizar todos los costes en los modelos de costes. Las diferentes divisas se pueden mostrar en la interfaz de usuario mediante la configuración preferida de multidivisa.

Nota: Se admiten todas las principales divisas.

## P. ¿Dónde asigno las suscripciones a datos e información empresariales?

A Las suscripciones a datos e información empresariales deben asignarse al grupo de costes «Otros». Sin embargo, la comparación de costes de TI no incluye las suscripciones a datos e información empresariales, por lo que es necesario excluir dichos gastos para poder realizar comparaciones equivalentes.

## P. ¿Puedo cambiar las métricas en las que se miden los puntos de referencia, por ejemplo, dividir por dispositivos en lugar de por usuarios?

A Núm. Todos los KPI disponibles aparecen en el producto. Siempre estamos buscando ampliar los KPI que mostramos, así que ponte en contacto con tu gestor de cuentas o responsable de éxito del cliente y comparte con ellos las opiniones y métricas que te interesan.

## P. ¿Debo incluir los gastos de TI relacionados con el cambio, el crecimiento y la transformación en la evaluación comparativa?

A Sí. Todos los gastos operativos están incluidos en los tres índices de referencia: Industria, TI OpEx e e Infraestructura. Los gastos de capital no se incluyen en los índices de referencia de IT OpEx.

## P. Si cambia los volúmenes/cantidades en la pantalla «Infrastructure Benchmarks» (Puntos de referencia de infraestructura), ¿se sobrescribirán los volúmenes/cantidades extraídos de CT?

A No, los cambios en el coste y el volumen realizados directamente en la aplicación Infrastructure Benchmark son exclusivos de Interactive Benchmarking. No se envían al modelo de costes Costing Standard y. Sin embargo, los costes de torre/subtorre y los volúmenes unitarios asociados en el objeto Torres de recursos de TI en el estándar de cálculo de costes se pueden integrar con los benchmarks interactivos.

## P. Al seleccionar el período para extraer los datos de CT a la evaluación comparativa, ¿se utilizan las cifras acumuladas del año hasta la fecha y luego se anualizan, o se anualizan solo en función del mes seleccionado?

A. Los datos de referencia de los costes estándar utilizan un total acumulado de 12 meses para los costes anuales y los costes unitarios.

## P. ¿Qué debería incluirse en la subtorre de la base de datos?

A Incluya sus sistemas de gestión de bases de datos (DBMS) basados en servidor, como Oracle y MS SQL.

No incluya los gastos de hardware en la gestión de datos, ya que estos se asignan a la computación y el almacenamiento.

Incluya los gastos de personal para el soporte operativo y de segundo nivel, incluyendo la administración, la configuración y las actualizaciones.

Incluya también cualquier software de bases de datos, así como servicios gestionados para bases de datos de servidores

## P. ¿De dónde proceden los datos de referencia?

A Los tres segmentos diferentes de la evaluación comparativa se basan en tres fuentes de datos diferentes:

- Los puntos de referencia del sector proceden de Rubin Worldwide
- OpEx Los puntos de referencia de TI proceden de Apptio
- Los parámetros de referencia de infraestructura proceden de ISG

## P. ¿Cómo puedo garantizar comparaciones equivalentes?

Hay varias formas de garantizar la comparabilidad:

Los índices de   
 referencia del sector se ajustan para:

- Sector
- Región
- Tamaño

Puntos de referencia de los e OpEx es de TI

Ajustar los arquetipos del modelo operativo para ambos:

- Aplicaciones (crear o comprar)
- Centros de costes (personal, hardware, software, proveedores)

Puntos de referencia de infraestructura

Ajustar para:

- de transacciones
- Región
- Sector

Nota: En el caso de los parámetros de referencia de infraestructura, el volumen es el factor más importante debido a las economías de escala; la región y el sector tienen un impacto menor.

## P. ¿Cómo funciona el producto con CT y cómo lo configuro adecuadamente, por ejemplo, cambiando los volúmenes en las fuentes IBX a través de CT?

A Consulte la sección sobre configuración para aprender a configurar la evaluación comparativa. Las opciones que seleccione en Interactive Benchmarking no sobrescribirán los datos de volumen o coste en CT
