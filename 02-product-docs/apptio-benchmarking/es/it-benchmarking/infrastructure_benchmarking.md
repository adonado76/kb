---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Evaluación comparativa de infraestructuras"
breadcrumb: []
source_path: "it-benchmarking/infrastructure_benchmarking.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Evaluación comparativa de infraestructuras

Esta sección describe la finalidad de las métricas de evaluación comparativa de infraestructuras. El producto Apptio Benchmarking es una aplicación de autoservicio SaaS que puede utilizar para realizar comparaciones de costes entre pares. La evaluación comparativa aborda el qué, pero no el por qué, el cómo o el qué viene después. Puede utilizar los costes de su organización, compararlos con las métricas de referencia e investigar/racionalizar sus datos reales para determinar el por qué y el cómo. A continuación, puede utilizar este conocimiento para crear próximos pasos y resultados viables, y ofrecer valor. Incluso puede trabajar con consultores externos que le ayuden a interpretar las comparaciones y le proporcionen consejos y recomendaciones.

**Infraestructura Métricas de referencia**

Esta categoría incluye métricas de referencia de pares a nivel de torre y subtorre. Los clientes pueden comparar los costes unitarios de sus torres y subtorres y la eficiencia de sus ETC.

| Tipo | Descripción |
| --- | --- |
| **Destinatarios** | Liderazgo TI, I&O, Finanzas TI, TBMO |
| **Propósito** | - Validación - Utilice estas métricas de infraestructura para alinear y validar las métricas por torre/subtorre con la Taxonomía TBM - Comparación: compare los costes unitarios y la eficiencia de los ETC con los valores de referencia de sus homólogos y evalúe en qué punto se encuentra la organización con respecto a las muestras de referencia - Seguimiento: seguimiento y análisis de los costes unitarios y de la eficiencia de los ETC a lo largo del tiempo - Revisión: revisión de las tendencias de los costes unitarios y de la eficiencia de los ETC - Iniciativa: crear iniciativas para impulsar mejoras y fijar objetivos |
| **Utilización** | - Validación - Mensual por I&O, IT Finanzas, TBMO - Comparación - Trimestral o ad hoc por I&O, TBMO - Seguimiento - Mensual por I&O, TBMO - Revisión - Trimestral o mensual por la dirección de TI, I&O, Finanzas de TI - Iniciativa - Semestral o ad hoc por la Dirección de TI, I&O, Finanzas de TI, TBMO |
| **Orientación** | Estas métricas se centran en las características de los gastos de torre por infraestructura. Incorporan volúmenes de infraestructura para calcular los costes unitarios de las subtorres a partir de los costes totales de las subtorres de Transparencia de Costes. Obtenga una comparación comparativa con los costes unitarios de referencia de sus homólogos. El coste y el volumen de TI de la organización deben asignarse y asignarse al nivel de subtorre.  La métrica de Eficiencia de los ETC proporciona una visión de los costes bajo gestión de TI para la subtorre. Esto es útil, ya que la mano de obra es el coste dominante de las infraestructuras. Ayuda a comprender la cobertura informática de la torre y a racionalizarla. Por ejemplo, una empresa puede tener una eficiencia de ETC baja, pero eso es justificable, ya que la estrategia de TI consiste en ofrecer un soporte de alta calidad. Las métricas de TI OpEx proporcionan comparaciones generales, mientras que las métricas de infraestructura se adentran en análisis específicos de torres y subtorres. Normalmente, las referencias de infraestructura se utilizan después del análisis de TI OpEx para revisar los costes específicos de infraestructura. |

Cuadro 5: Intención de infraestructura

Los datos de referencia proceden de [ISG](https://isg-one.com/ "(se abre en una pestaña o una ventana nueva)"), una organización líder en servicios de asesoramiento, inteligencia de mercado e información tecnológica (las métricas de las torres de almacenamiento son la excepción y proceden de Rubin Worldwide).

Las métricas incluidas son:

| Torre IT | Subtorre IT | Unidad de medida | Coste unitario | Coste por grupo de costes | Eficiencia ETC |
| --- | --- | --- | --- | --- | --- |
| Computación | Windows | Servidores lógicos/físicos | √ | √ | √ |
| Linux | Servidores lógicos/físicos | √ | √ | √ |
| Unix | Servidores lógicos/físicos | √ | √ | √ |
| Sistema principal | MIPS | √ | √ | √ |
| Almacenamiento (véase NOTA más abajo) | Nivel 1 | TBs instalados | √ | √ |  |
| Nivel 2 | TBs instalados | √ | √ |  |
| Nivel 3 | TBs instalados | √ | √ |  |
| Nivel 4 | TBs instalados | √ | √ |  |
| Red | LAN | Puertos LAN activos | √ | √ | √ |
| WAN | Dispositivos conectados al usuario final | √ | √ | √ |
| Voz | Teléfono | √ | √ | √ |
| Usuario final | Espacio de trabajo (PC) | Ordenadores de sobremesa, portátiles y Thin Clients | √ | √ |  |
| Centro de servicio al usuario | Contactos | √ | √ | √ |
| Comunicaciones |  | Usuarios de TI | √ | √ |  |
| Resultado |  | Millones de imágenes | √ | √ | √ |
| Gestión de TI |  | Usuarios de TI | √ | √ | √ |
| Correo electrónico |  | Usuarios de TI | √ | √ |  |

Cuadro 6 Métricas de referencia de la infraestructura

**Notas**

- En el caso del almacenamiento, la distribución de costes por grupos de costes la proporciona (el proveedor del índice de referencia) a nivel de almacenamiento global. A continuación, se aplica a cada uno de los 4 niveles.
- La lista anterior corresponde a la taxonomía TBM v1.0.

A partir de estas métricas se puede llevar a cabo lo siguiente:

| Uso | Cómo interpretar: resultados y cuestiones a tener en cuenta |
| --- | --- |
| **Validación** - Adecuación de los gastos a la taxonomía TBM | - Articular el valor de las TI y justificar el coste de su prestación, - Mejorar el diálogo y la alineación con los usuarios de la empresa sobre la base de datos reales normalizados y referencias de homólogos   Estos valores del cliente requieren alinear los datos con los buckets correctos de la Taxonomía TBM y comprobar la calidad de las asignaciones. Ayuda a establecer y mantener la confianza en los costes reales de TI (más información).  Es habitual que los usuarios inicien la infraestructura con datos incompletos. Además, estas métricas introducen e incorporan el volumen en el modelo de Transparencia de Costes. Esto permite comprender mejor los factores de coste.   - Los datos nunca son perfectos y la evaluación comparativa ayudará a identificar, priorizar e impulsar datos procesables y mejoras de los procesos que permitan tomar mejores decisiones - Reconocer la naturaleza iterativa de la calidad de los datos y las asignaciones y las comparaciones con puntos de referencia impulsa la capacidad de empezar hoy y mejorar con el tiempo - Inicie este viaje identificando las áreas de alta prioridad con oportunidades y centre los ajustes en estas áreas en primer lugar. Utilizar el proceso de comparación de puntos de referencia para ayudar a identificar las áreas de alta prioridad |
| **Comparación** - Gasto en TI con referencias de infraestructura | Los puntos de referencia abordan el qué, pero no el por qué, el cómo o el qué viene después:   - Investigar la variación de los puntos de referencia y racionalizar las comparaciones impulsará el por qué y el cómo - Es esencial crear próximos pasos accionables, resultados y reconocer el valor   Una secuencia típica de varianza (comparación) es:   1. Empiece por el nivel de la torre para comprender el gasto de material e identificar grandes oportunidades. Algunas posibles cuestiones a investigar son:    - ¿Cuál es la Torre que más gasta?    - ¿Cuál es la mayor desviación con respecto al valor de referencia? Esto nos lleva a ver las subtorres. 2. Revisar los detalles de los costes unitarios de las subtorres, desglosados por composición del grupo de costes, para identificar áreas susceptibles de análisis, decisiones y oportunidades. Identificar áreas de optimización :    - Racionalizar las comparaciones con el punto de referencia para entender por qué por encima/por debajo    - El valor de referencia es un punto de referencia: estar por encima o por debajo no es malo o bueno Algunas posibles cuestiones a investigar son:     - ¿Qué subtorre tiene el mayor gasto basado en el coste total?    - ¿Qué subtorre presenta la mayor desviación con respecto al valor de referencia basado en el coste unitario? Esto ayuda a profundizar en la composición del conjunto de costes y a abordar cuestiones como:     - ¿Coincide la composición con el modelo operativo?    - ¿En qué se diferencian de los homólogos de referencia?    - ¿Son pertinentes las decisiones actuales sobre el modelo operativo o existe una oportunidad de cambio? 3. Revisar la eficiencia de los ETC de las subtorres para identificar áreas en las que mejorar la eficiencia de las operaciones. Algunas preguntas potenciales son:    - ¿Se explota eficazmente la infraestructura?    - ¿Merece la pena plantearse estrategias de abastecimiento alternativas? |
| **Seguimiento** - Coste unitario y eficiencia ETC | Los parámetros de referencia son puntos de referencia; identifique y fije objetivos incrementales alcanzables que se basen en parámetros de referencia. Las decisiones tomadas a partir del análisis comparativo anterior pueden conducir a mejoras incrementales y, potencialmente, a iniciativas de mayor envergadura (identificadas más adelante y, normalmente, en conjunción con revisiones de liderazgo).  Establecimiento de objetivos fiscales bien fundamentados - A partir de las acciones identificadas mediante comparaciones entre homólogos, establezca objetivos para el seguimiento de los avances en materia de costes unitarios y eficiencia de los ETC. Este seguimiento puede realizarse a lo largo del tiempo con datos reales actualizados y datos de referencia de los homólogos (los datos de referencia se actualizan cada 6 meses). |
| **Revisión** - Revisión de la dirección sobre Progreso | Utilizar las métricas anteriores para el seguimiento de los objetivos en revisiones periódicas con el equipo directivo. |
| **Iniciativa** - Identificar e impulsar la iniciativa | Las revisiones impulsan las decisiones estratégicas sobre inversiones en TI e iniciativas de activación. La repercusión de estas iniciativas puede seguirse observando el impacto en los costes según las directrices anteriores. |

Cuadro 7: Resultados de las infraestructuras

Para cada una de estas métricas, el proveedor de datos de referencia ISG proporciona una media junto con ajustadores en tres dimensiones independientes:

- **Escala** - Ajustadores basados en unidades de medida de volúmenes. Es el principal factor que influye en las métricas de infraestructura. El modelo de escala ISG para el coste unitario es una función escalonada del coste unitario sobre el volumen de unidades. El modelo es aplicable a un intervalo de volumen determinado. La función paso a paso, consulte  **¡Error! Fuente de referencia no encontrada.**  , es aplicable en un rango de umbral alto (coste) a umbral bajo (coste).
- **Región** - Ajustadores basados en la región. ISG proporciona ajustadores para las regiones NA, EMEA y APAC; la definición de región es la ubicación donde una organización tiene su sede.
- **Industria** - Ajustadores basados en categorías industriales. ISG proporciona ajustadores para los siguientes segmentos: Banca, Servicios Financieros y Seguros (BFSI), Energía, Fabricación, Comunicaciones y Medios de Comunicación y Entretenimiento (MCM), Tecnología y Otros.

En el producto de evaluación comparativa, consulte ( Apptio, Infrastructure Benchmarking, 2015), se pueden calcular las métricas de infraestructuras homólogas visualizando la distribución y seleccionando los ajustadores. Normalmente se utiliza el ajustador de escala, ya que es el que más contribuye.

El vídeo de presentación del producto Benchmarking ofrece una descripción de los componentes del benchmarking, su valor junto con la lista de métricas y sus proveedores de datos.
