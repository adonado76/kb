---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Guía de configuración de AI TCO"
breadcrumb: []
source_path: "cost-transparency/reports/ai-tco-configguide.html"
images:
  - "resources/images/ct_images/aiarch.png"
  - "resources/images/ct_images/aicomcon.png"
  - "resources/images/ct_images/aiconfig.png"
  - "resources/images/ct_images/aicst.png"
  - "resources/images/ct_images/aictapp.png"
  - "resources/images/ct_images/aictf.png"
  - "resources/images/ct_images/aitco.png"
  - "resources/images/ct_images/aitcoreport.png"
  - "resources/images/ct_images/aius.png"
  - "resources/images/ct_images/arch1.png"
  - "resources/images/ct_images/cldcst.png"
  - "resources/images/ct_images/dataench.png"
  - "resources/images/ct_images/datamap.png"
  - "resources/images/ct_images/inptok.png"
  - "resources/images/ct_images/labcst.png"
  - "resources/images/ct_images/modcnt.png"
  - "resources/images/ct_images/opta.png"
  - "resources/images/ct_images/optb.png"
  - "resources/images/ct_images/othcst.png"
  - "resources/images/ct_images/outtok.png"
  - "resources/images/ct_images/solcnt1.png"
  - "resources/images/ct_images/solcnt2.png"
  - "resources/images/ct_images/solusr.png"
  - "resources/images/ct_images/solusr1.png"
  - "resources/images/ct_images/tokencom.png"
  - "resources/images/ct_images/typenorm.png"
  - "resources/images/ct_images/vencnt.png"
  - "resources/images/ct_images/vencst.png"
  - "resources/images/ct_images/wrkbench.png"
  - "resources/images/icons/aitco.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía de configuración de AI TCO

## Pasos de configuración

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aiconfig.png)

A continuación se describen los pasos de configuración necesarios para obtener informes sobre el coste total de propiedad y el uso de AI sections.:

1. Arquitectura del proyecto - Consulte [aquí](#aitoconfig__arch) la sección de *arquitectura*
2. Instalación de componentes - Consulte la sección de *instalación de componentes* [aquí](#aitoconfig__compinst)
3. Basado en facturas o en el Libro Mayor. Estas 2 opciones se describen a grandes rasgos en la sección *arquitectura* [aquí](#aitoconfig__arch)
4. Cargar fuentes de datos relacionadas con la IA - Consulte [aquí](#aitoconfig__datreq) la sección de *requisitos de datos*
5. Iluminar las nuevas métricas del modelo - Consulte la sección *del modelo* [aquí](#aitoconfig__models)
6. Informes de uso y coste total de propiedad de AI: consulte la sección *de informes* [aquí](#aitoconfig__rep)

## Requisitos previos

Los requisitos previos para la solución AI TCO & Usage son:

- IBM Apptio Costing Standard licencia
- IBM Apptio Versión del servidor: R12.11.14 (o superior)
- Versión de los componentes v120 en la configuración del proyecto

## Instalación de componentes

El núcleo de la solución AI TCO & Usage se presenta a través de 4 componentes. 2 componentes nuevos, creados específicamente para esta solución + 2 componentes existentes que se han ampliado y, por tanto, se espera que se actualicen. En el caso de los nuevos clientes, habrá que instalar los demás componentes "típicos" de mano de obra, proveedor, nube, etc., según la arquitectura general prevista. Los clientes existentes pueden reutilizar estos componentes previamente instalados sin ningún cambio. Antes de instalar estos componentes, es esencial revisar cuidadosamente la arquitectura de su entorno para determinar el mejor enfoque para la implementación. Tendrá que decidir si:

- Instalar los componentes en un proyecto existente, o
- Crear un nuevo proyecto específico para la solución AI TCO & Usage

A continuación se describen los 4 componentes que deben tenerse en cuenta e instalarse por orden de prioridad.

![Imagen 1](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aicomcon.png)

Nota: Para instalar los componentes necesarios, establezca temporalmente la *Versión de componentes* en la Versión 120 en la Configuración del proyecto. Instale los componentes necesarios y, a continuación, revierta el cambio de versión para evitar que se activen indicadores de actualización innecesarios.

![Un cuadrado verde con una cabeza con auriculares](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aitco.png)

1. Componente **TCO y utilización de IA** : Este componente proporciona una visión clara de los gastos y la utilización de la IA en todos los modelos de IA, soluciones de IA y unidades de negocio. Este componente establece el marco subyacente a través de un conjunto de nuevos conjuntos de datos maestros específicos de la IA, bancos de trabajo, modelos y métricas, facilitando la modelización y el cálculo del TCO de la IA y los resultados de uso.

   Instalar como primer componente.

   ![Fotografía](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aictf.png)
2. Componente **CTF - Fuente de costes** : Está disponible una nueva versión del componente CTF - Fuente de costes, que añade los siguientes **campos nuevos** a los Datos maestros de la fuente de costes para admitir el TCO y el uso de AI solution.:
   1. Porcentaje de coste de IA: Trae el Porcentaje de Coste de IA según lo establecido y definido por el usuario en la tabla AI Tablematch.
   2. Importe AI: Multiplica el importe de la Fuente de Coste existente por el Porcentaje de Coste AI para crear un nuevo Importe AI que busca alimentar el nuevo modelo de Coste AI. Para instalar como segundo componente. Si no instala este componente, no verá la métrica "% del coste total de TI a lo largo del año" ni el desglose "Coste de IA por grupo de costes" en sus informes.

      Nota: Para los clientes existentes (que tienen la intención de poblar esta solución utilizando la Fuente de Costos - Libro Mayor) se requiere actualizar el siguiente componente:

   ![Un cuadrado verde con un logotipo blanco y azul](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aictapp.png)
3. Componente **CT Apps - Servicios** : Está disponible una nueva versión del componente CT Apps - Servicios, que añade nuevos campos a All Business Services para dar soporte a la solución AI TCO & Usage.

   Nota: Los clientes existentes deben actualizar el siguiente componente para garantizar la compatibilidad y el acceso a las nuevas funciones.

   1. IsAISolution: Debe establecerse en "Sí" para cualquier Oferta de Servicio que se considere directa o indirectamente una Solución de IA.
   2. Tipo de solución AI: Metadatos que se utilizan como segmentadores en la solución AI TCO & Usage. Los valores sugeridos son:
      1. *Independiente:* Una solución de IA dedicada que funciona de forma independiente como su propio producto o servicio.
      2. *Integrada:* la IA se integra profundamente en un producto existente, convirtiéndose en una función nativa básica.
      3. *Aumentada:* IA incorporada o añadida ligeramente para mejorar una función/proceso, pero no esencial.
   3. Usuarios de soluciones de IA: Resume el nr. de usuarios únicos de soluciones de IA.
   4. Recuento de soluciones AI: Cuenta el nr. de soluciones de IA.

   Se instala como tercer componente. Nota: Si no se actualiza este componente, se romperán los informes de TCO y uso de AI, ya que la mayoría de los informes se crean en el nivel de AI Solutions = Business Services con el filtro establecido en IsAISolution = "Sí".

   ![Un logotipo verde y blanco](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aitcoreport.png)
4. **AI TCO & Usage Reportingcomponent** : Este componente proporciona los informes para la solución AI TCO & Usage. Consta de 2 informes, introducidos en una nueva colección de informes AI. El informe principal AI TCO & Usage permite a las organizaciones supervisar el ciclo de vida completo de las inversiones en IA, abordando de forma proactiva la proliferación de IA mediante el seguimiento del coste total de propiedad (TCO), las tendencias de uso, las averías y las anomalías. Los principales destinatarios son ejecutivos de alto nivel, líderes de negocio y soluciones, y equipos de IA y ciencia de datos. Además, existe un informe secundario sobre el modelo de costes de IA que permite a los usuarios rastrear dinámicamente las asignaciones de costes y uso de IA mediante visualizaciones interactivas de diagramas de Sankey.

   Se instalará como componente final.

## Arquitectura

El primer paso es decidir dónde instalar los componentes de la solución AI TCO & Usage. Tiene varias opciones, y a continuación le presentamos dos posibles enfoques.

**Opción A**

Integre la solución AI TCO & Usage en un proyecto existente y opte por un enfoque basado en GL y Resource Tower.

Este enfoque se recomienda a los clientes existentes que deseen aprovechar o reutilizar la lógica de asignación que ya existe en la métrica principal del modelo de costes. Si cree que sus usuarios objetivo se beneficiarían de un enfoque basado en el Libro Mayor con vistas detalladas de las Torres de Recursos y los Pools de Costes, esta solución es una buena opción. El siguiente diagrama muestra cómo integrar el nuevo objeto Plataformas de IA en su modelo estándar.

![Diagrama de una empresa](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aiarch.png)

*Modelo de medición de costes AI - Basado en GL con torres de recursos*

La solución AI TCO & Usage introduce nuevas métricas que funcionan de forma independiente, incluso cuando se añaden a su proyecto existente. En el diagrama se destaca el nuevo modelo de costes de IA, con las partes existentes **en azul** y las nuevas incorporaciones **en verde**, como las plataformas de IA y los nuevos campos de la fuente de costes y los servicios empresariales. Esto le permite utilizar sus líneas de asignación existentes con el nuevo modelo AI Cost en función de las necesidades, lo que le proporciona más flexibilidad y control.

El controlador del objeto Fuente de costes en la métrica del modelo de costes AI se basa en una nueva columna denominada "Importe AI", que se rellena a partir del conjunto de datos "Fuente de costes AI Tablematch". Este conjunto de datos está diseñado para identificar las transacciones del Libro Mayor relacionadas con la Inteligencia Artificial (IA).

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/opta.png)

Es esencial identificar y rellenar la tabla con las cuentas, centros de coste, proveedores y descripciones de líneas de diario relevantes que usted asocie con **Costes y Uso de AI**, tal y como se demuestra en el ejemplo anterior. Además, la columna Coste AI % es obligatoria y debe contener valores numéricos.

Nota: En caso de duda sobre el % de coste de IA, ajústelo a 100. Las normas de asignación y las correspondencias afinarán aún más los importes de las transacciones para incluir únicamente los costes relacionados con la IA.

La lógica de correspondencia de tablas recuperará detalles de columnas adicionales de los datos de la fuente de costes, cotejando las entradas del extracto cargado y rellenando las columnas pertinentes, siempre que existan en los datos de la fuente de costes.

**Opción B**

Cree un nuevo proyecto para la solución AI TCO & Usage + opte por un enfoque basado en facturas, excluyendo las torres de recursos.

Nota: Optar por el enfoque basado en facturas y excluir las torres de recursos en este punto se consideraría un enfoque personalizado. Técnicamente factible, pero probablemente requerirá el apoyo de los servicios profesionales de Apptio.

Este enfoque se recomienda para los clientes existentes o nuevos que primero quieran referenciar completamente esta nueva solución y el conjunto de casos de uso relacionados con la IA. Además, es adecuada para clientes que creen que los destinatarios de esta solución se beneficiarían de una fuente de verdad basada en facturas con líneas de asignación más directas y sin necesidad de informar sobre desgloses de costes de torres de recursos y grupos de costes. La siguiente imagen muestra la arquitectura.

![Diagrama de una empresa](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/optb.png)

*Modelo de medición de costes AI - Basado en facturas sin torres de recursos*

El marco anterior se aleja del enfoque más tradicional basado en el libro mayor y la fuente de costes, al tiempo que elimina las torres de recursos de la arquitectura. Si bien esto podría acelerar el tiempo de despliegue, dependería de la creación de más asignaciones personalizadas. Si adopta este enfoque, las siguientes vistas de informes ya no funcionarán:

- KPI de "% del coste total de TI YTD"
- Desglose del coste de la IA por "grupo de costes"
- Desglose del coste de la IA por "torres de recursos"

## Gatear-Caminar-Correr

Al empezar a utilizar la solución AI TCO & Usage, no es necesario tener todo configurado desde el principio para empezar a ver el valor. La solución está diseñada para ser flexible, lo que le permite empezar poco a poco y llegar con el tiempo a una comprensión completa de sus costes de IA. Esto significa que puede empezar por lo básico e ir añadiendo más detalles sobre la marcha, sin necesidad de tener todas las piezas colocadas de inmediato. Puedes pensar en ello como un enfoque **de "gatear-caminar-correr"**, en el que empiezas dando pequeños pasos y luego aumentas gradualmente el ritmo a medida que te vas sintiendo más cómodo con la solución. Este enfoque le permite ofrecer valor rápidamente y ganar impulso con el tiempo, lo que facilita sacar el máximo partido de sus inversiones en IA.

![Fotografía](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/arch1.png)

*Coste total de propiedad y uso de la IA - Gatear/Caminar/Correr*

**Arrástrese**

En la fase de rastreo, algunas soluciones de IA pueden configurarse con relativa rapidez con sólo aportar conjuntos de datos relacionados con determinadas áreas. La atención se centra aquí en las soluciones de IA que se compran predominantemente.

- Ejemplo de solución de IA: Microsoft Copilot
- Principales objetos del modelo:
  - Vendedor: Licencia de vendedor
  - Trabajo: Formación y gestión del cambio
  - Otros Seguridad e integración
  - Asignación directa de servicios: Fichero de consumo/utilización
- Valor: Comprenda el coste total de propiedad de Microsoft Copilot como solución de inteligencia artificial, incluidas las perspectivas de las contribuciones laborales. Informar y realizar un seguimiento de la adopción de Microsoft Copilot en toda la organización aportando y aprovechando los datos de consumo/uso asociados.

**Andando**

En la fase inicial, la atención se centrará en las soluciones de IA que empiecen a incorporar el uso de plataformas y/o modelos de IA, apuntalando el coste total de propiedad, junto con usos más avanzados de mano de obra cualificada. Estas soluciones de IA suelen ser una combinación de compra y construcción.

- Ejemplo de solución AI: AskIT
- Objetos principales del modelo (además de los de la fase de rastreo):
  - Nube: Coste y uso del modelo de IA
  - Plataformas de IA: Datos que representan las plataformas y modelos de IA reales
  - Datos: En el caso de datos protegidos por derechos de propiedad intelectual, asegúrese de registrar y representar los costes relacionados con la preparación y formación de los datos
- Valor: Comprender el coste total de propiedad de una solución de IA creada internamente, como AskIT, empezando a aportar datos relacionados con las plataformas de IA y/o los modelos de IA que consume la solución. Informar y realizar un seguimiento de los generadores de costes, así como obtener información sobre el uso del modelo de IA.

**Ejecute**

En la fase de ejecución más avanzada, se espera que la mayoría, si no todos, los objetos típicos modelados se vuelvan aplicables para iluminar el TCO de la IA y los resultados y perspectivas de uso. Se espera que las soluciones de IA representadas en esta fase sean en su mayoría soluciones de IA creadas internamente.

- Ejemplo de solución AI: IndexGPT
- Objetos principales del modelo (además de los de la fase de rastreo y ejecución):
  - Infraestructura: Computación dedicada a la IA (GPU), almacenamiento, base de datos, etc.
  - Seguimiento del tiempo: Manera más consuntiva de garantizar un seguimiento adecuado de la actividad para actividades laborales de alto nivel
- Valor: Obtenga información integral sobre el coste total de propiedad y el uso de la IA en todas sus soluciones de IA, incluidas las más complejas. Algunas de ellas se alojan y construyen internamente y, por tanto, contienen una huella de infraestructura significativa que debe contabilizarse.

## Requisitos de datos

**Datos básicos**

Como muestra la sección centrada en la Arquitectura, la solución AI TCO & Usage introduce un nuevo objeto modelado llamado AI Platforms. Este objeto está destinado a abastecerse de datos centrados en el coste, el uso y la adopción asociados a las plataformas de IA y los modelos de IA.

El archivo incrustado se centra en:

- Los datos necesarios (lista de todas las columnas con su respectiva descripción, si son necesarias o no y el efecto si faltan)
- Aclaraciones sobre las columnas (describe algunos valores de ejemplo y su descripción)
- Datos de muestra (un ejemplo del aspecto que tendrían los datos en las plataformas de IA)
- Sistemas fuente (ejemplos de referencias de posibles sistemas fuente para los datos de la Plataforma AI)

Además del nuevo objeto principal de Plataformas AI, se han actualizado 2 conjuntos de datos maestros para reflejar algunos de los cambios necesarios para iluminar los principales informes AI TCO & Usage.

Se han añadido varias columnas nuevas a los Datos maestros de la fuente de costes y a Todos los servicios empresariales, que se documentan en el mismo archivo incrustado.

Nota: los datos necesarios para rellenar los demás objetos modelados que forman parte del proyecto de esta solución no se tratan aquí. Póngase en contacto con su representante de Apptio para obtener información sobre los demás requisitos de datos tradicionales.

Para conocer los detalles de los requisitos de datos destacados anteriormente, haga clic aquí:

[![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/aitco.png)](../../resources/AITCO-usage.xlsx "(se abre en una pestaña o una ventana nueva)")

**Entorno de trabajo**

Cuando los datos se obtienen para las plataformas de IA, pasan por la siguiente arquitectura:

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/wrkbench.png)

Como se desprende de lo anterior, se espera que los datos sin procesar se añadan en primer lugar a la fuente de las plataformas de IA. A partir de ahí, se expone en 2 tablas editables ("AI Platforms Metadata Enriched" y "AI Platforms Mapping Enriched") que componen el AI Workbench (que se instala como parte del componente AI TCO & Usage). El conjunto de datos maestro de las plataformas de IA se utiliza en última instancia para exponer los datos en las métricas del modelo de IA a través del objeto modelado de las plataformas de IA. A continuación encontrará una breve descripción de cada una de las 2 tablas editables:

- Plataformas de IA Enriquecimiento de datos

  La tabla "AI Platforms Data Enrichment" del Workbench permite el enriquecimiento de metadatos, utilizados para la elaboración de informes, en todas las plataformas y modelos de IA. Cualquier actualización en esta tabla se refleja directamente en la tabla editable "AI Platforms Metadata Enriched", mejorando los datos relacionados con las plataformas de IA para apoyar un seguimiento preciso de los costes y la elaboración de informes. Los datos mejorados se asignan a las "plataformas de IA" a través de la "transformación ET de asignación de plataformas de IA".

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/dataench.png)
- Plataformas de IA Mapeo de datos

  Esta tabla del banco de trabajo permite la asignación de los consumidores de las plataformas de IA y los modelos de IA. Espera la asignación de una Plataforma de IA o Modelo de IA a 1 o varias Ofertas de Soluciones. Alternativamente, puede asignarse a una Unidad de Negocio o a un ID de Usuario en caso de que las Plataformas de IA o los Modelos de IA estén siendo consumidos directamente por usuarios finales. La columna de ponderación de costes es importante, ya que permite una asignación/distribución ponderada de los costes entre los consumidores. Las actualizaciones de esta tabla se reflejan directamente en la tabla editable "AI Platforms Mapping Enrichment", que a su vez se asigna a las plataformas de IA mediante la "AI Platforms Mapping ET Transform".

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/datamap.png)
- Normalización del tipo de token de AI

  Esta tabla editable permite categorizar y normalizar los distintos tipos de token (que llegan a través de los datos brutos) en los tipos de token simplificados de entrada y salida. Esta categorización ayuda a simplificar las vistas de análisis e informes en lo que respecta a la exposición de los detalles de uso de la IA. Las actualizaciones de esta tabla se reflejan directamente en la tabla editable "Normalización de tipos de tokens AI" y en la tabla "Transformación ET de normalización de tipos de tokens AI". Este último se busca en la tabla maestra de plataformas de IA mediante una fórmula.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/typenorm.png)

## Modelos de

Una vez que los requisitos de datos están claros, es importante entender cómo se utilizan estos datos en las diferentes métricas del modelo, especialmente en términos de iluminación de los informes del usuario final.

El componente AI TCO & Usage instala 13 métricas de modelo, que pueden parecer extensas, pero en realidad proporcionan la máxima flexibilidad para el modelado y las asignaciones, además de permitir vistas de informes sencillas. Como ya se indicó en la sección sobre arquitectura, en la que se presentó el nuevo modelo de costes de la IA y los dos enfoques posibles, en esta sección se profundizará en los detalles de los 13 modelos, explicando su finalidad y justificación. Los modelos se clasifican en tres grupos:

- 5 AI Modelos relacionados con los costes
- 5 IA Modelos relacionados con el uso
- 3 Modelos relacionados con el recuento de IA

En la siguiente sección se ofrece un resumen detallado de las métricas modelizadas, junto con su correspondiente lógica de controladores

|  |  |  |
| --- | --- | --- |
| **Métrica modelada** | **Objeto modelado Fuente** | **Lógica del conductor** |
| **Coste de la IA** | Coste | Fórmula:  If(Maestro de fuentes de costes Data.Cost Controlador del modelo de fuentes IN ("OPEX - ACTUALS - FIXED", "OPEX - ACTUALS - VARIABLE"), Datos maestros de fuentes de costes. AI Cantidad),0)  Nota: Filtrado para gastos de IA, a través de AI Tablematch |
| Coste de la nube de IA | Proveedor de servicios en la nube | Métrica:  Coste de la IA |
| Coste del proveedor de IA | Proveedores | Fórmula:  Si(¡Es CSP!="Sí", Coste AI, 0) |
| Coste laboral de la IA | Labores | Fórmula:  Coste de la IA - Coste del proveedor de IA |
| AI Otros costes | Otros fondos de costes | Métrica:  Coste de la IA |
| **Uso de la IA** | Plataformas de IA | Columna:  "Cantidad de uso" de las plataformas de IA |
| Consumo de tokens de IA | Plataformas de IA | Fórmula:  If(AI Platforms.Billing Type="Token Usage",AI Platforms.Usage Quantity,0 ) |
| Fichas de entrada AI | Plataformas de IA | Fórmula:  Si(Plataformas AI. Tipo de token normalizado = "Entrada", Uso AI, 0) |
| Fichas de salida AI | Plataformas de IA | Fórmula:  Si (Plataformas AI. Tipo de token normalizado = "Salida", Uso AI, 0) |
| Usuarios de soluciones de IA | Plataformas de IA | Columna:  "Total de usuarios de la solución AI" de AI Platforms |
|  | Servicios de negocio | Fórmula:  Si( {AI Solution Users to Business Services (AI Platforms- AI Solution Users driver) } =0, {All Business Services.AI Solution Total Users Prep},0) |
| **Recuento AI** |  |  |
| Recuento de proveedores de AI | Proveedores | Fórmula:  If( {AI Cost}!=0,( 1/SumIF(Vendor Maestro Data.Vendor ID,Vendedor Maestro Data.Vendor ID,1 )),0) |
| Recuento de modelos AI | Plataformas de IA | Columna:  "Número de modelos de IA" de las plataformas de IA |
| Recuento de soluciones AI | Plataformas de IA | Columna:  " Recuento de soluciones de IA" de las plataformas de IA |
| Recuento de soluciones AI | Servicios de negocio | Fórmula:  If(AI Soution Count to Business Services(AI Platforms-AI Solution Count Driver))!=0,0, {All Business Services.AI Solution Count} |

**AI Modelos de costes (5)**

Coste de la IA

Principal métrica del modelo de costes que impulsa todos los informes de TCO y uso de AI. En la vista siguiente (enfoque impulsado por la Fuente de Costes - Libro Mayor), se espera que se identifiquen los Gastos de IA (a nivel de Fuente de Costes), se reutilicen las asignaciones existentes (del modelo de Costes) etiquetándolas a esta nueva métrica del modelo de Costes de IA y se establezcan nuevas asignaciones en lo que respecta a las asignaciones de entrada y salida del nuevo objeto Plataformas de IA.

Esta métrica se creó teniendo en cuenta lo siguiente:

- No alterar el modelo de costes existente.
- Permitir que se establezca un vínculo entre las Torres de TI y el objeto Plataformas de IA (que contiene los gastos de IA)
- Permitir que el cliente (que desee seguir ampliando esta métrica modelizada) establezca los controladores adicionales (relacionados específicamente con los costes de IA) en función de sus necesidades

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aicst.png)

Coste de la nube de IA

Esta métrica se ha creado para permitir que el usuario final comprenda de forma rápida y sencilla el controlador de costes de la nube de IA de forma mensual y anual, como parte del análisis desglosado del coste total de propiedad. Simplemente pretende imitar el modelo principal de costes de la IA, centrándose y partiendo del objeto Proveedor de servicios en la nube. Etiquete las líneas de asignación ascendente que deben considerarse parte del Coste de la Nube AI.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cldcst.png)

Coste del proveedor de IA

Esta métrica se ha creado para permitir que el usuario final comprenda de forma rápida y sencilla el controlador de costes del proveedor de IA de forma mensual y anual, como parte del análisis desglosado del coste total de propiedad. Simplemente pretende imitar el modelo principal AI Cost, centrándose y partiendo del objeto Vendedor. Nota: Elimina los proveedores de servicios en nube de esta métrica para garantizar que no se produzca un doble recuento con la métrica del coste de la nube de AI.

Etiquetar las líneas de imputación ascendente que deben considerarse parte del Coste de Proveedor AI.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/vencst.png)

Coste laboral de la IA

Esta métrica se ha creado para que el usuario final pueda comprender de forma rápida y sencilla el impulsor de los costes laborales de la IA mensualmente y a lo largo del año, como parte del análisis desglosado del coste total de propiedad. Simplemente parece imitar el modelo principal AI Cost, centrándose y partiendo del objeto Labor. Nota: Elimina de esta métrica el servicio de coste del proveedor de IA para garantizar que no se produzca un doble recuento con las métricas de coste del proveedor de IA y de la nube.

Etiquete las líneas de asignación ascendente que deben considerarse parte del Coste Laboral AI.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/labcst.png)

AI Otros costes

Esta métrica se ha creado para permitir que el usuario final comprenda de forma rápida y sencilla cualquier otro factor de coste de IA de forma mensual y anual, como parte del análisis desglosado del coste total de propiedad. Simplemente pretende imitar el modelo principal de Costes de la IA, centrándose y partiendo del objeto Otros Pools de Costes.

Etiquetar las líneas de imputación al alza que deben considerarse parte de la IA Otros costes.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/othcst.png)

**Modelos de utilización de la IA (5)**

Uso de la IA

Junto con la métrica del modelo de costes de IA, esta métrica de uso de IA es la más importante, ya que también impulsa todos los informes de TCO y uso de IA. Sin embargo, es una métrica más simplificada, dado que se origina inmediatamente en el objeto modelado por la plataforma de IA y, por tanto, atraviesa menos capas. El controlador de esta métrica modelizada procede directamente de la columna Cantidad de uso del conjunto de datos maestros de las plataformas de IA. Señala el uso de las Plataformas de IA y/o Modelos de IA. Si se dispone de los datos de relación, se espera que se vinculen a los servicios empresariales (basados en la solución de IA = oferta de servicios) y se espera que los datos se reutilicen en la asignación directa de servicios para resaltar potencialmente cualquier consumo directo de plataformas de IA y/o modelos de IA por parte de las unidades empresariales (basado en el ID de usuario perteneciente a una determinada unidad empresarial).

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/aius.png)

Consumo de tokens de IA

Esta métrica se ha creado como un subconjunto del Uso de IA, centrándose específicamente en los casos en los que el Tipo de facturación = Uso de token. Se utiliza en los informes como KPI principal y para varias vistas de consumo de tokens. Aunque sólo destacamos el controlador en la vista inferior, se espera que siga la misma lógica/línea de asignación que la métrica del modelo de uso de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/tokencom.png)

Fichas de entrada AI

Esta métrica se ha creado como un subconjunto del Uso de IA y un subconjunto más del Consumo de fichas de IA, ya que se centra específicamente en las fichas de entrada de IA. Se utiliza predominantemente en las pestañas de Detalle de uso en los informes. Nota: Depende de la tabla de normalización de tokens de AI, donde los diferentes tipos de tokens se normalizan en "Entrada" en este caso. Se espera que siga la misma lógica/línea de asignación que la métrica del modelo de consumo de fichas de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/inptok.png)

Fichas de salida AI

Esta métrica se ha creado como un subconjunto del Uso de IA y un subconjunto adicional del Consumo de fichas de IA, ya que se centra específicamente en las fichas de salida de IA. Se utiliza predominantemente en las pestañas de Detalle de uso en los informes. Nota: Depende de la tabla de normalización de tokens de AI, donde los diferentes tipos de tokens se normalizan en "salida" en este caso. Se espera que siga la misma lógica/línea de asignación que la métrica del modelo de consumo de fichas de IA.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/outtok.png)

Usuarios de soluciones de IA

Esta métrica apunta a un tipo diferente de uso de la IA, a saber, la adopción de la IA. Pretende informar sobre el número de usuarios que utilizan/adoptan las soluciones de IA. Se trata de un KPI clave para la elaboración de informes y es fundamental para las perspectivas que se muestran en la pestaña Unidades de negocio de los informes. Para garantizar que esta métrica funcione en todos los niveles, incluida la segmentación de los datos relacionados con el modelo de IA, como el tipo de modelo de IA, se obtiene en 2 niveles. Primero en el objeto modelado Plataforma AI (facilitado a través de una búsqueda en el maestro Plataformas AI), en una segunda instancia en el objeto modelado Servicios Empresariales. El controlador de este último garantiza que no se produzca un doble recuento restando el controlador anterior, establecido en el objeto modelado de la Plataforma AI. Etiquete las líneas de asignación ascendente para garantizar que la métrica funcione cuando se apliquen cortadores de Servicios Empresariales o Unidades de Negocio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solusr.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solusr1.png)

**Modelos de recuento AI (3)**

Recuento de proveedores de AI

Esta métrica se ha creado para garantizar la elaboración de informes precisos sobre el número de proveedores distintos que están en juego en relación con los costes de IA. Aparece como KPI principal en los informes. Sólo recoge los Vendedores con un Coste AI asociado para garantizar que no estén representados todos los Vendedores. Etiquete las líneas de asignación ascendente para garantizar que la métrica funcione cuando se apliquen cortadores de Servicios Empresariales o Unidades de Negocio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/vencnt.png)

Recuento de modelos AI

Esta métrica se ha creado para garantizar la elaboración de informes precisos sobre el número de modelos de IA distintos que están en juego. Aparece como KPI principal en los informes. Procede directamente de una fórmula creada en el conjunto de datos AI Platforms Master. Etiquete las líneas de asignación ascendente para garantizar que la métrica funcione cuando se apliquen cortadores de Servicios Empresariales o Unidades de Negocio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/modcnt.png)

Recuento de soluciones AI

Esta métrica se ha creado para garantizar la elaboración de informes precisos sobre el número de soluciones de IA distintas que están en juego. Aparece como KPI principal en los informes. Para garantizar que esta métrica funcione en todos los niveles, incluida la segmentación de los datos relacionados con el modelo de IA, como el tipo de modelo de IA, se obtiene en 2 niveles. Primero en el objeto modelado Plataforma AI (facilitado a través de una búsqueda en el maestro Plataformas AI), en una segunda instancia en el objeto modelado Servicios Empresariales. El controlador de este último garantiza que no se produzca un doble recuento restando el controlador anterior, establecido en el objeto modelado de la Plataforma AI. Etiquete las líneas de asignación ascendente para garantizar que la métrica funcione cuando se apliquen cortadores de Servicios Empresariales o Unidades de Negocio.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solcnt1.png)

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/solcnt2.png)

## Informes

El componente AI TCO & Usage Reporting instala las funciones de elaboración de informes para la solución AI TCO & Usage. Se instalan dos informes en una nueva colección de informes AI.

El informe principal AI TCO & Usage permite a las organizaciones supervisar el ciclo de vida completo de las inversiones en IA, abordando de forma proactiva la proliferación de IA mediante el seguimiento del coste total de propiedad (TCO), las tendencias de uso, las averías y las anomalías. El informe está diseñado para ejecutivos de alto nivel, líderes empresariales y de soluciones, y equipos de inteligencia artificial y ciencia de datos, y presenta 4 pestañas con información adaptada a cada una de estas personas:

- *Resumen* - Directivos de alto nivel
- *Modelos de IA* - Equipos de IA y ciencia de datos
- *Soluciones AI* - Líderes de soluciones (Propietarios de servicios)
- *Unidades de negocio* - Líderes empresariales

Además, existe un informe secundario sobre el modelo de costes de IA que permite a los usuarios realizar un seguimiento dinámico de las asignaciones de costes y uso de IA mediante visualizaciones interactivas de diagramas de Sankey.

Para ver las visualizaciones y las principales ventajas de los informes anteriores, haga clic [aquí](ai-tco-report-collection.html).

## Llamadas

- Los componentes AI TCO & Usage y AI TCO & Usage Reporting se publican con la plantilla de componentes v120. Por lo tanto, para ver y descargar estos dos componentes es necesario cambiar la Configuración de plantillas.
- “isAISolution” es una nueva columna crucial, creada en la tabla Todos los servicios empresariales (a través de la actualización del componente correspondiente). Asegúrese de que el valor esté establecido en "Sí" para las Ofertas de servicios que identifique Soluciones AI. Este es un requisito previo para activar los informes de uso y coste total de propiedad de AI.
- Los clientes existentes deben actualizar el componente "CTF - Cost Source", si utilizan el método basado en el Libro Mayor, y el componente "CT - App Services", como se ha indicado anteriormente.
