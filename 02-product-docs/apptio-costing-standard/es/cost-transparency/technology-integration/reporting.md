---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "IBM Turbonomic Informes"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "IBM Turbonomic"
source_path: "cost-transparency/technology-integration/reporting.html"
images:
  - "resources/images/ct_images/trb-rep-1.jpg"
  - "resources/images/ct_images/trb-rep-2.jpg"
  - "resources/images/ct_images/trb-rep-3.jpg"
  - "resources/images/ct_images/trb-rep-fin.jpg"
  - "resources/images/ct_images/trb-rep-onprem.jpg"
  - "resources/images/ct_images/trb-rep-opr.jpg"
  - "resources/images/ct_images/trb-rep-summ.jpg"
  - "resources/images/ct_images/trb-rep-trnd.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# IBM Turbonomic Informes

El componente Informes de optimización de TI híbrida instala dos informes como parte de una nueva colección de informes denominada "TI híbrida".

## **KPI comunes**

En ambos informes se utiliza un conjunto de indicadores clave de rendimiento (KPI) comunes. Estos KPI se centran en presentar indicadores clave de rendimiento en diversas dimensiones operativas y financieras.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-1.jpg)

- **Coste híbrido** : crea una comprensión de la línea de base de los costes totales de la infraestructura híbrida tanto en las instalaciones como en la nube, utilizando factores de asignación flexibles a través de una métrica modelada independiente que no afecta al modelo de costes principal. El objetivo es reducir el coste híbrido total a lo largo del tiempo a medida que se llevan a cabo las optimizaciones.
- **Ahorros realizados** : muestra cuántos ahorros se han realizado en lo que va del mes y en lo que va del año, según la cuantificación de las acciones ejecutadas que se cargan y agregan en lo que va del mes y en lo que va del año. El objetivo es aumentar los ahorros realizados y realizar un seguimiento de cuánto se ha ahorrado en lo que va de año.
- **Ahorros potenciales:** - Proporciona la última instantánea de los ahorros potenciales basada en el conjunto más reciente de acciones pendientes, que abarca tanto la nube como las instalaciones locales (estas últimas utilizando solo el porcentaje abordable del coste unitario). El objetivo es comprender la «magnitud del premio» y aprovechar al máximo todos los ahorros potenciales.
- **COIN (Índice de optimización de costes)** : mide la oportunidad de optimización como el ahorro potencial dividido por el coste híbrido total, lo que ayuda a evaluar en qué medida se ha optimizado el entorno. Un KPI secundario muestra el porcentaje de ahorro alcanzado como el ahorro realizado dividido por el ahorro total. El objetivo es mantener bajo el COIN en todos los ámbitos, garantizando la mejor optimización de la carga de trabajo.

## Infrastructure Optimization Insights - Informe de proveedores

Este informe está dirigido a los proveedores de servicios técnicos responsables de gestionar la optimización de las infraestructuras.

**Personas destinatarias**

- Propietario del servicio técnico (por ejemplo, Jefe de Informática)
- Finanzas TI

**Ficha Resumen**

La pestaña Resumen permite a los usuarios realizar:

- Análisis de tendencias del coste híbrido, ahorro potencial y ahorro realizado
- Análisis del ahorro basado en dimensiones clave como la categoría operativa, el tipo de acción y la clase de infraestructura
- Desglose del ahorro neto entre ahorro real e inversiones necesarias

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-2.jpg)

**Ficha Información financiera**

La pestaña Información financiera permite:

- Una vista del ahorro potencial por entorno, proveedor y categorías como directo, diferido o evitación de costes
- Pivotaje por oferta, lo que permite conocer el rendimiento financiero a nivel de propietario de servicio técnico
- Índice COIN + Estado, pivotable por Propietario o Categoría
- Economía unitaria, que muestra la relación entre las acciones y el ahorro realizado, lo que ayuda a priorizar las acciones con mayor impacto

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-summ.jpg)

**Ficha Información operativa**

La pestaña Información operativa proporciona:

- Recuentos de acciones pendientes, agrupados por clase de medio ambiente e infraestructuras
- Información sobre la tasa de automatización de las acciones ejecutadas
- Impacto de la optimización, que muestra qué parte de la infraestructura se ha optimizado con IBM Turbonomic frente a la parte que está totalmente optimizada o que aún no se ha optimizado
- Desglose de las acciones entre Pendientes y Ejecutadas y análisis del total de acciones, destacando las áreas clave

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-fin.jpg)

**Ficha Tendencia**

La pestaña Tendencias ofrece los siguientes datos:

- Tendencia COIN para supervisar el índice de acciones ejecutadas frente a las pendientes
- Evolución temporal de las acciones ejecutadas
- Tendencias de las acciones pendientes, ya sea disminuyendo debido a la ejecución de más acciones o aumentando a medida que más infraestructuras entran en el ámbito de la optimización
- Todas las tendencias son pivotables por varias dimensiones

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-opr.jpg)

**Ficha Detalles On-Prem**

La pestaña Detalles On-Prem proporciona:

- Análisis del ahorro potencial y del ahorro realizado a nivel Infra ID/Nombre
- Cuantificación del ahorro basada en el coste unitario a nivel de Oferta de Servicio Técnico, multiplicado por el delta de cantidad específico de cada ID de Infra
- Información sobre infraestructuras sin oportunidades de optimización identificadas, lo que indica que se trata de infraestructuras totalmente optimizadas o de elementos que aún no se han optimizado

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-trnd.jpg)

**Ficha Workbench**

La pestaña Workbench contiene:

- Tarjeta de tarifa unitaria, un informe editable en el que los usuarios fijan el % direccionable, junto con desgloses de ahorro directo, diferido y evitación de costes
- Fichas editables para Objetivo y Ajustes y Edición de filtros

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-onprem.jpg)

## Infrastructure Optimization Insights - Informe para el consumidor

Este informe ofrece información desde la perspectiva de los consumidores de servicios de infraestructura, principalmente los propietarios de aplicaciones.

**Personas destinatarias**

- Propietario de la solución, centrándose principalmente en el propietario de la aplicación
- Esta vista puede ampliarse a vistas de nivel superior, como Servicios y Unidades de Negocio (BU) personas

**Principales diferencias con la vista del proveedor**

- Se utiliza Cargo en lugar de Coste, ya que esta visión se centra en el consumo
- Las dimensiones clave se centran en los metadatos relacionados con la aplicación, como la criticidad empresarial y el objetivo de inversión
- Ofrece menos vistas granulares, sin pestaña de detalles On-Prem ni pestaña de Workbench

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-rep-3.jpg)
