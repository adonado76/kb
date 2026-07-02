---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Apéndice A: Glosario y acrónimos"
breadcrumb:
  - "Benchmarking"
  - "Cómo empezar"
source_path: "it-benchmarking/key-terminology.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Apéndice A: Glosario y acrónimos

Este apéndice ofrece definiciones claras de los términos y acrónimos utilizados en esta Guía de referencia comparativa. Está pensado para que se pueda escanear y citar rápidamente.

Si estás en una reunión y alguien pregunta «¿qué significa eso exactamente?», esto es lo que deberías transmitir.

## Términos básicos de TBM, ITFM y Apptio

**ATUM (Modelo unificado TBM de Apptio )**

Implementación de TBM por parte de Apptio. Más información sobre ATUM disponible [aquí](https://www.apptio.com/platform/atum "(se abre en una pestaña o una ventana nueva)").

**Informe de costes habilitado para benchmarking**

Un informe de costes que incluye valores de referencia junto con sus propias cifras. Por ejemplo, un informe que muestre el coste por servidor, la mediana de referencia, los cuartiles y la varianza. Estos informes permiten realizar un análisis detallado desde el desfase de referencia hasta las cuentas, los proveedores, los servicios o las aplicaciones.

**Fondo común de costes**

Una categoría de TBM que agrupa los costes según lo que se ha comprado o cómo se contabiliza. Ejemplos: mano de obra, hardware, software, servicios externos, instalaciones. Son transversales y muestran los tipos de costes en todas las torres.

**Cálculo de costes del proyecto**

Un único «contenedor» o punto final de Costing dentro de su entorno de Apptio. Cada proyecto de cálculo de costes tiene sus propias fuentes de datos, asignaciones, lógica de asignación, informes, métricas y permisos, que suelen limitarse a una organización, departamento, región o huella tecnológica específicos. En el contexto del benchmarking, el «proyecto de cálculo de costes» es el contenedor elegido que actúa como sistema de registro, proporcionando los costes anuales de TI por grupo de costes y torre de recursos.

**IBM Apptio (Interactivo) Evaluación comparativa**

El producto que compara sus costes de TI, su estructura y la eficiencia de su infraestructura con referencias externas, utilizando conceptos de TBM. Combina conjuntos de datos externos, sus datos de costes y el perfil de su organización.

**IBM Apptio Cálculo de costes**

El producto « Apptio » que modela y asigna los costes tecnológicos. Anteriormente denominado «Transparencia de costes» En esta guía, el «cálculo de costes» es el sistema preferido para registrar los costes de TI que alimentan el benchmarking.

**ITFM / ITFMA (Gestión financiera de TI / Analista de gestión financiera de TI)**

La función y el analista se centraron en la elaboración de presupuestos, previsiones y análisis financieros en el ámbito de las tecnologías de la información. A menudo comparten responsabilidades con los TBMA en materia de cálculo de costes y evaluación comparativa, y colaboran estrechamente con el departamento financiero.

**Subtorre de recursos (Subtorre)**

Una subunidad de una torre de recursos, muy utilizada para la evaluación comparativa de infraestructuras. Ejemplos: dentro de Compute, puede tener servidores; dentro de Storage, puede tener bloques, archivos y objetos. Las subtorres son donde normalmente se definen los costes unitarios de infraestructura y los indicadores de eficiencia.

**Torre de recursos (Torre)**

Una agrupación lógica importante de capacidades o infraestructura de TI definida por la taxonomía TBM. Ejemplos: usuario final, computación, almacenamiento, red, centro de datos, plataforma, aplicación, seguridad. Las torres le indican dónde se sitúan los costes de TI desde una perspectiva técnica.

**TBM (Gestión de negocios tecnológicos)**

Una disciplina y un marco de gestión que conecta el gasto en tecnología, los recursos y los servicios con los resultados empresariales. En la práctica, el TBM te ofrece una forma estándar de clasificar los costes tecnológicos y hablar de ellos con los responsables financieros y empresariales. TBM define grupos de costes, torres de recursos y subtorres de recursos estándar. Más información sobre la taxonomía TBM disponible [aquí](https://www.tbmcouncil.org/taxonomy "(se abre en una pestaña o una ventana nueva)").

**TBMA (Analista de Gestión de Negocios Tecnológicos)**

El profesional que crea y mantiene el modelo TBM, configura los productos Apptio y explica los resultados. En esta guía, los TBMA suelen ser los principales usuarios del contenido sobre configuración y resolución de problemas.

## Conceptos clave del benchmarking

**Arquetipo**

Un patrón estándar de gasto o estructura de TI que se encuentra al agrupar organizaciones. Ejemplos: «intensivo en mano de obra» frente a «intensivo en proveedores», «intensivo en centros de datos» frente a «orientado a la nube» Los arquetipos explican por qué te diferencias de la media y a qué patrón general te pareces.

**Estándar de comparación**

Una métrica que describe el rendimiento de un grupo de organizaciones en una medida definida. Por ejemplo, el coste medio por servidor para un grupo de empresas similares de su sector y tamaño.

**Perfil de referencia**

Conjunto de valores de referencia calculados para un grupo de referencia específico y un periodo de tiempo determinado. Un perfil es, esencialmente, «la visión de referencia del mundo» con la que se comparan tus datos y que se puede reutilizar en múltiples informes.

**Métricas del sector**

Métricas económicas de TI a nivel empresarial, como el gasto en TI como porcentaje de los ingresos o el gasto en TI por empleado. Se utilizan para responder a la pregunta «¿qué importancia tiene la TI en comparación con el negocio» frente a otras empresas similares?

**Puntos de referencia de infraestructura**

Coste unitario y métricas de eficiencia para torres de infraestructura y subtorres. Ejemplos: coste por servidor, coste por TB, FTE por cada 100 servidores. Se utilizan en análisis profundos a nivel de torre y en trabajos de optimización.

**Puntos de referencia de IT OpEx (puntos de referencia de IT OpEx )**

Métricas que describen cómo se distribuyen los gastos operativos por grupo de costes y por torre de TI. Esto ayuda a responder a la pregunta «¿cómo está estructurado nuestro gasto?» en comparación con nuestros homólogos.

**Grupo de pares**

El conjunto de organizaciones con las que se le compara. Normalmente se filtran por sector, ingresos o rango de tamaño, región y, en ocasiones, otros atributos. Los grupos de pares deben ser lo suficientemente grandes como para cumplir con los umbrales mínimos de muestra; de lo contrario, se suprimirán las métricas.

**Percentil**

Valor que indica la posición en una distribución. El percentil 50 es la mediana. Los percentiles 25 y 75 son los cuartiles inferior y superior.

**Cuartiles / Rango intercuartílico**

El percentil 25 (cuartil inferior), el percentil 50 (mediana) y el percentil 75 (cuartil superior). El rango intercuartílico es la banda entre los percentiles 25 y 75. Los gráficos de referencia suelen mostrar la mediana como una línea o un punto y la banda intercuartílica como un recuadro o una zona sombreada.

## Términos relativos a los datos y al alcance

**Negocios OpEx**

El gasto operativo total de las unidades de negocio respaldadas por la organización de TI incluida en el ámbito. Debe reflejar *todos* los costes operativos empresariales en curso para ese ámbito, no solo los de TI, y se utiliza como denominador para métricas como «gasto en TI como porcentaje del OpEx empresarial» Si usted es una compañía de seguros, incluya los gastos de suscripción y los gastos por pérdidas y ajustes de pérdidas. Si usted es un banco, incluya los gastos por intereses y los gastos no relacionados con intereses. Si usted representa a un gobierno o una organización sin fines de lucro, utilice el presupuesto operativo empresarial para el ámbito de aplicación.

**CapEx / OpEx**

Gastos de capital y gastos operativos. Los puntos de referencia suelen centrarse en los costes periódicos de TI (una visión e OpEx e que incluye la depreciación o amortización de las inversiones capitalizadas). Es importante comprender si los costes relacionados con la gestión de la información ( CapEx ) están incluidos en los costes de TI utilizados para la evaluación comparativa.

**FTE (equivalente a tiempo completo)** : una medida normalizada del número de empleados. En el modelado de costes, la facturación y la evaluación comparativa, FTE **no** se traduce ni hace referencia a un empleado a tiempo completo. Un FTE representa una persona a tiempo completo estándar que trabaja al 100 % de su capacidad. Dos personas a media jornada juntas equivaldrían a un FTE. La medición se utiliza para métricas tales como FTE por cada 100 empleados o FTE por cada 100 servidores.

**Recuento de personas**

El simple recuento de personas incluidas en el ámbito, sin ajustar el número de horas que trabajan. Cada persona cuenta como **1**, independientemente de si trabaja a tiempo completo, a tiempo parcial o es temporal. Normalmente se informa como una instantánea **puntual** (por ejemplo, el número de empleados al final del mes).

**Coste de TI**

Todos los costes que se consideran incluidos en el ámbito de las TI en el modelo TBM. Por lo general, incluye mano de obra, hardware, software, servicios externos e instalaciones que dan soporte a las torres tecnológicas. Puede incluir depreciación y amortización, dependiendo del tratamiento contable. Los costes de TI incluidos en el ámbito excluyen otros costes relacionados con la tecnología que se encuentran en otras organizaciones/departamentos.

**Perfil organizativo**

El conjunto de atributos que definen cómo se muestra ante el motor de referencia. Campos típicos: nombre de la organización, sector, región, ingresos anuales, número de empleados o número de ETC y, en ocasiones, indicadores de complejidad como el número de aplicaciones o clientes. El perfil determina la selección del grupo de pares y las métricas de escalado.

**Ingresos**

Los ingresos empresariales asociados a las unidades de negocio respaldadas por la organización de TI objeto de la evaluación comparativa. Incluya únicamente los ingresos correspondientes a la parte de la empresa a la que realmente se destina el gasto en TI incluido en el ámbito de aplicación, y no los ingresos totales del grupo si el gasto en TI solo cubre una parte de este. Si usted es un banco, determine los ingresos utilizando los ingresos totales por intereses más los ingresos no relacionados con intereses, menos la provisión para pérdidas por préstamos. Si usted es una compañía de seguros, determine los ingresos utilizando las primas brutas emitidas más otros ingresos operativos relevantes.

**Ámbito**

El límite de lo que se incluye en el análisis. Por ejemplo: solo TI corporativa frente a TI más telecomunicaciones, o TI global frente a una sola región. El alcance debe ser coherente entre los costes de TI, los ingresos y la plantilla para que los ratios de referencia tengan sentido.

**Coste unitario**

Un coste normalizado por una medida de volumen o capacidad. Ejemplos: coste por servidor, coste por TB, coste por empleado. Los costes unitarios permiten comparar organizaciones de diferentes tamaños.

**Datos sobre volumen/capacidad**

Recuentos o medidas no financieros utilizados como denominadores en métricas de coste unitario y eficiencia. Ejemplos: número de servidores, TB de almacenamiento, número de dispositivos o puertos de red, número de dispositivos de usuarios finales, recuento de ETC para equipos específicos.

## Términos del programa y de gobernanza

**Registro de cambios (para la evaluación comparativa)**

Un simple registro de los cambios significativos en la configuración que pueden afectar a la interpretación de los resultados. Por ejemplo: cambiar la versión de TBM, cambiar el proyecto de cálculo de costes, cambiar el grupo de pares predeterminado, habilitar el dominio Infra. Se utiliza para explicar cambios estructurales y evitar confusiones.

**Resumen de configuración**

Una breve instantánea documentada de cómo funciona actualmente el benchmarking. Contenido típico: proyecto de cálculo de costes utilizado, versión de TBM, definición predeterminada del grupo de pares, dominios habilitados y año de referencia activo. Se utiliza para mantener a todos honestos y alineados.

**QBR (Revisión trimestral del negocio)**

Un foro periódico en el que se revisa el rendimiento y se toman decisiones. En este contexto, las QBR suelen incluir puntos de referencia para torres o temas clave.

**Propietario de Resource Tower / Responsable de dominio**

La persona responsable de una torre de recursos o dominio específico, como usuario final, red, almacenamiento, computación o seguridad. Los propietarios de Resource Tower utilizan Resource Tower y los parámetros de referencia de infraestructura para comprender cuál es la situación de su zona y qué es lo que hay que cambiar.

**Comité directivo / junta de gobierno**

Un grupo multifuncional de líderes (TI, finanzas y, en ocasiones, negocios) que supervisa la estrategia, las inversiones y el rendimiento de TI. En estas sesiones se suelen utilizar puntos de referencia como contexto externo para las decisiones importantes.

**Responsable del programa TBM/ITFM**

El propietario del programa de gestión financiera de TBM e IT. Esta persona define cómo se utiliza Benchmarking, aprueba los cambios en la configuración estructural y representa a Benchmarking en los foros de gobernanza.

**Programa TBM**

El esfuerzo continuo por utilizar prácticas y herramientas de TBM para gestionar el coste, el consumo y el valor de la tecnología. El benchmarking es uno de los componentes de este programa, junto con el cálculo de costes, la planificación y la gobernanza relacionada.
