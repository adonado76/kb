---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Metodología de sostenibilidad de la nube"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Informes de sostenibilidad en la nube"
source_path: "product/cloud_sustainability_methodology.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Metodología de sostenibilidad de la nube

Antes de entrar en la metodología utilizada para calcular las emisiones de carbono, es importante entender primero los dos tipos principales de emisiones implicadas. La huella de carbono suele proceder de dos fuentes principales: las emisiones operativas y las emisiones incorporadas.

**Emisiones operativas**

Las emisiones operativas son el resultado del funcionamiento cotidiano de la infraestructura de nube. Estas emisiones proceden principalmente de la electricidad que consumen los centros de datos en nube para alimentar y refrigerar los servidores, los equipos de red y los dispositivos de almacenamiento que alojan los servicios en nube.

**Emisiones incorporadas**

Las emisiones incorporadas se refieren a la cantidad de carbono emitida durante la fabricación, el transporte y la eliminación de los dispositivos de hardware.

Para estimar las emisiones incorporadas en la nube, calculamos la fracción del total de emisiones incorporadas que corresponde al uso o carga de trabajo del cliente. Por ejemplo, si un usuario utiliza sólo un subconjunto de CPU virtuales disponibles en un servidor físico, se asigna una cantidad proporcional de emisiones incorporadas para representar este uso.

Además, las emisiones se clasifican en dos categorías: directas e indirectas.

- **Emisiones directas** : Liberadas directamente de fuentes propiedad de la organización o controladas por ella.

- **Emisiones indirectas** : Resultan de las actividades de la organización pero se generan a partir de fuentes que no son de su propiedad ni están directamente controladas por ella.

***Una vez más, estas emisiones se clasifican en ámbitos de emisión de carbono.***

- **Alcance 1 (Emisiones directas):** Emisiones generadas por fuentes propiedad de la empresa o controladas por ella.
  - Algunos ejemplos son la combustión de combustible en generadores propiedad de la empresa, procesos de fabricación in situ y calderas propiedad de la empresa.
- **Alcance 2 (Emisiones indirectas):** Emisiones generadas por el consumo de fuentes de energía adquiridas, como electricidad, vapor o gas.
  - Algunos ejemplos son la electricidad comprada para edificios de oficinas o el vapor/gas para procesos industriales.
- **Alcance 3 (Emisiones indirectas):** Emisiones que se producen como consecuencia de las actividades de la empresa pero que se generan dentro de su cadena de suministro. Ejemplo: Emisiones operativas de servicios en nube como máquinas virtuales y almacenamiento proporcionados por los CSP.

Como clientes de servicios en la nube, consumimos recursos ofrecidos por los CSP sin controlar la generación de energía subyacente. Dado que no producimos ni compramos electricidad directamente (de ello se encargan las centrales termosolares), las emisiones operativas derivadas del uso de la nube se clasifican en el Alcance 3.

Nota: *Cloudability considera las emisiones operativas e incorporadas de Alcance 3 y las publica a través de las métricas de sostenibilidad dentro de su plataforma.*

**Metodología de cálculo - Emisiones operativas**

Cloudability se basan en la metodología de la Huella de Carbono en la Nube (CCF), mejorada con factores adicionales como datos de utilización real y modelos de consumo de energía basados en aprendizaje automático.

Este enfoque utiliza una metodología ascendente, en la que las emisiones de los recursos individuales se calculan por separado y luego se agregan para representar las emisiones totales de una organización relacionadas con la nube.

**Fórmula: Emisiones de carbono estimadas (CO₂e) = Consumo de energía por hora × Eficacia del uso de la energía (PUE) × Emisiones de la red × Horas de uso**

Donde:

- **Consumo de energía por hora:** Calculado mediante modelos ML entrenados en especificaciones de máquina y métricas de utilización.

- **Eficacia del uso de la energía (PUE)** : Medida de la eficiencia energética de los centros de datos que publican los CSP.

- **Emisiones de la red** : Carbono emitido por unidad de electricidad generada (media anual).

- **Horas de uso** : Total de horas de funcionamiento de la máquina.

**Fuentes de datos**

|  |  |
| --- | --- |
| Conjunto de datos | Origen |
| Eficacia del uso de la energía (PUE) | GCP PUE – Google Cloud; AWS / Azure – Huella de carbono en la nube; OCI – Oracle Infraestructura en la nube |
| Emisiones de la red | AEMA, EPA, Nuestro Mundo en Datos y Huella de Carbono en la Nube |
| Horas de uso | Derivados de los datos de costes proporcionados por cada proveedor de nube |
| Consumo | Según los datos de utilización recogidos por Cloudability |
| Especificaciones de la máquina | A partir de los datos sobre precios y descripción de recursos recopilados por Cloudability |

**Metodología de cálculo - Emisiones incorporadas**

Las emisiones incorporadas se calculan utilizando la metodología de la Huella de Carbono de las Nubes.

**Fórmula: Emisiones incorporadas = TE × ( TR1 / EL) × (RR / TR2 )**

Dónde

- **TR1** = Tiempo reservado, el tiempo que el hardware está reservado para su uso por parte del software (la cantidad de tiempo que una instancia de cálculo determinada ha estado funcionando)

- **EL** = Expected Lifespan, el tiempo previsto de instalación del equipo (4 años elegidos por el equipo de Teads) [(Dell PowerEdge R740 Full Lifecycle Assessment)](https://www.delltechnologies.com/asset/en-us/products/servers/technical-support/Full_LCA_Dell_R740.pdf "(se abre en una pestaña o una ventana nueva)")

- **RR** = Recursos reservados, el número de recursos reservados para su uso por el software (número de vCPUs de la instancia dada)

- **TR2** = Recursos totales, el número total de recursos disponibles (la instancia más grande vCPUs para la familia dada)

- **TE** = Emisiones totales incorporadas, la suma de las emisiones del Análisis del Ciclo de Vida (ACV) de todos los componentes del hardware. TE estamos calculando con la ayuda de Machine learning.

**Emisiones totales incorporadas (ET)**

Cloudability sigue la metodología de la Huella de Carbono en la Nube (CCF) para calcular las Emisiones Incorporadas, las emisiones de carbono asociadas a la fabricación, el transporte y el procesamiento al final de la vida útil del hardware de la nube, como servidores, redes y equipos de almacenamiento.

Aunque el marco CCF proporciona una base sólida, sus datos públicos sobre emisiones incorporadas no se han actualizado desde 2022. Como resultado, los datos de los principales proveedores de servicios en nube (CSP) para los nuevos tipos de máquinas y generaciones de hardware pueden estar incompletos. Para garantizar una cobertura completa y actualizada, el equipo de Cloudability ha desarrollado un modelo basado en el aprendizaje automático que calcula las emisiones totales incorporadas (ET) de todos los tipos de máquinas disponibles en AWS, Azure y Google Cloud. Esta mejora permite a Cloudability ofrecer estimaciones de carbono incorporado más precisas, actuales y fiables, ayudando a las organizaciones a tomar decisiones informadas en materia de sostenibilidad.

**Ejemplo** : Para la familia de instancias m5, la máquina más grande ( m5.24xlarge ) tiene 96 vCPUs y un total de emisiones incorporadas (TE) de 1610.79 kgCO₂e con una vida útil de 4 años. Si una instancia de m5.xlarge (4 vCPUs ) funciona durante 30 minutos, sus emisiones incorporadas equivalen a 1610.79 × ( 0.5 / 35.040) × (4 / 96) = 0.00134 kgCO₂e.

**Ventajas de esta metodología**

- **Cobertura completa:** Captura tanto las emisiones operativas como las incorporadas, ofreciendo una visión completa del impacto del carbono relacionado con la nube.

- **Coherencia entre nubes:** utiliza una metodología unificada para todos los proveedores de servicios en la nube ( AWS, Azure, GCP y OCI) con el fin de realizar una comparación precisa.

- **Utilización real:** Aprovecha las métricas de utilización real y la modelización basada en el aprendizaje automático para mejorar la precisión en las estimaciones tanto operativas como de carbono incorporado.

- **Estimación actualizada:** Aborda las lagunas de datos en los marcos públicos (como CCF) aplicando modelos ML para estimar los valores de las generaciones de hardware más recientes.

- **Visibilidad granular:** Proporciona información sobre las emisiones a nivel de ID de recurso, con desgloses por región, servicio, proveedor o periodo de tiempo (mes, año, año hasta la fecha, etc.).

- **Perspectiva del ciclo de vida:** Tiene en cuenta las emisiones a lo largo de todo el ciclo de vida del hardware, desde la fabricación y el funcionamiento hasta el desmantelamiento.

- **Apoyo a la toma de decisiones:** Permite correlacionar las tendencias de costes y emisiones para impulsar operaciones en la nube sostenibles y rentables.

**Tema principal:** [Informes de sostenibilidad en la nube](../product/cld-sustainability-reporting.html)
