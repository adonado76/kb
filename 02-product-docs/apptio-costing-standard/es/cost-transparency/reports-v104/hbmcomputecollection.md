---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Optimización informática y recopilación de información"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Colección Computación"
source_path: "cost-transparency/reports-v104/hbmcomputecollection.html"
images:
  - "resources/images/hbm_images/hbmimages/11693_1.png"
  - "resources/images/hbm_images/hbmimages/11693_2.png"
  - "resources/images/hbm_images/hbmimages/11693_3.png"
  - "resources/images/hbm_images/hbmimages/11693_4.png"
  - "resources/images/hbm_images/hbmimages/11693_5.png"
  - "resources/images/hbm_images/hbmimages/11693_6.png"
  - "resources/images/hbm_images/hbmimages/11693_7.png"
  - "resources/images/hbm_images/hbmimages/11693_8.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Optimización informática y recopilación de información

- Se aplica a: Hybrid Business Management en TBM Studio TBM Studio y posteriores

Utilice los informes de informática para conocer el coste, la capacidad y la utilización de sus recursos informáticos. Los informes le permiten analizar su perfil de gastos, comprender las métricas de Compute, comprender las métricas operativas, analizar la utilización del servidor y comprender una vista de Aplicaciones de los detalles del servidor (host y lógico). Utilice esta colección de informes para conocer el estado general de su infraestructura informática en relación con lo planificado, con KPI procesables y reveladores y análisis de alto nivel. Esta información es especialmente útil para comprender dónde está incurriendo en costes de Compute y determinar dónde se están produciendo anomalías en el gasto. Proporciona informes granulares para que pueda optimizar el coste y la utilización de los servidores.

Esta colección de informes está diseñada para las siguientes funciones:

- Director de TI
- Equipo informático de TI
- Jefe de Operaciones
- Propietarios de servicios de TI

Esta colección de informes se ajusta a los siguientes objetivos empresariales:

- Ver los costes informáticos de toda la empresa
- Comprender el coste por hora de virtualización y hora de instancia
- Seguimiento de la estrategia de infraestructura informática y uso de los recursos informáticos
- Realice un seguimiento del equilibrio entre el recuento de servidores, el coste por servidor, los núcleos de CPU, la memoria total, el coste por GB, las horas de instancia y el coste de las horas de instancia para determinar si la tendencia del gasto informático es la esperada

Estos informes permiten determinar lo siguiente:

- ¿Qué plataformas de servidor requieren la compra de unidades adicionales?
- ¿Cuál es el coste por hora de servidor de cada aplicación?
- ¿Qué plataformas y unidades de servidor deben retirarse?
- ¿Dónde están las oportunidades para migrar de la infraestructura local a la nube pública?

## Visualizar la colección de informes

1. Inicie sesión en Apptio.
2. En la página de **inicio**, haga clic en **Hybrid Business Management**.
3. En el menú Colección de informes, seleccione **Calcular**. Por defecto, se abre el informe **Resumen de cálculo**.

## Informe de síntesis

El informe Resumen informático ofrece una visión general del gasto informático total en la empresa, tanto en las instalaciones como en la nube, y ayuda a visualizar el gasto en dimensiones como grupos de costes, entornos, proveedores y torres de TI.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_1.png)

**(1) Indicadores clave de rendimiento (KPI)** : los KPI ofrecen una visión de alto nivel del gasto en infraestructura:

- **Coste YTD** - Este KPI muestra el gasto global en Compute YTD. El gasto del periodo en curso figura como **Coste**.
- **Recuento de servidores** : este KPI muestra el número actual de servidores locales. El KPI secundario muestra el porcentaje de servidores virtuales como **% de servidores virtualizados**.
- **Horas de Instancia Virtual** - Este KPI muestra el uso actual (en horas de instancia) de sus servidores virtuales. El KPI secundario muestra **el Coste por Hora de Instancia**.
- **Horas de Instancia en la** Nube - Este KPI muestra el uso actual (en horas de instancia) de sus servidores públicos y en la nube. El KPI secundario muestra **el Coste por Hora de Instancia**.

**(2) Filtros** - Los siguientes filtros están disponibles en este informe. Estos filtros son acumulativos y afectan a todos los datos de la página, incluidos los KPI:

- **Perfil de virtualización** : seleccione un tipo específico de servidor local o en la nube para ver el impacto del gasto informático en ese tipo de servidor.
- **SO** - Seleccione un sistema operativo (SO) específico para ver el impacto del gasto de Compute en ese SO.
- **Entorno** - Seleccione un entorno específico (como Dev, Prod o Test) para limitar los datos del informe a los servidores de ese entorno.
- **Ubicación** - Seleccione una ubicación específica para ver el impacto del gasto de Compute para esa ubicación.
- **Propósito** - Seleccione un propósito específico del servidor para ver el impacto del gasto de Compute en servidores con el mismo propósito.

**(3) Gasto mensual en recursos inform** áticos: utilice este gráfico para ver la tendencia de gasto de 1 año en recursos informáticos en sus servidores locales y de nube pública.

**(4) Costes informáticos por** : haga clic en las pestañas **Grupos de costes**, **Torres de TI**, **Entorno** o **Proveedores** para ver gráficos del gasto actual en almacenamiento del mes. La tabla **Detalles** muestra el gasto del mes en curso, del trimestre anterior y del año anterior.

Preguntas contestadas:

- ¿Hay anomalías en nuestro gasto?
- ¿Se ajusta el gasto a nuestra estrategia informática?
- ¿Cómo evoluciona la estrategia de infraestructuras?
- ¿Dónde incurrimos en gastos informáticos?

## Informe sobre el perfil de gastos

Haga clic en **Perfil de gastos** en la pestaña Recopilación de informes para abrir el informe. Este informe muestra un perfil de costes de computación.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_2.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los de Computación - Resumen. Véase el elemento 2 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(3) Gasto mensual actual por** grupo de costes - Utilice este gráfico para ver el gasto actual del servidor por grupo de costes (Servicios externos, Hardware, etc.).

**(4) Tendencia de 13 meses de servidores** - Utilice este gráfico para ver el recuento mensual de servidores, el coste por servidor y el gasto medio anual en servidores, de forma que pueda detectar anomalías y tendencias que no se ajusten a su estrategia empresarial.

**(5) Gasto del servidor por** - Utilice los gráficos circulares **por Perfil**, **por Sistema Operativo** y **por Entorno** para comprender el equilibrio de los costes de su servidor a través de varias métricas.

Preguntas contestadas:

- ¿Cómo evoluciona la estrategia de servidores?
- ¿Dónde incurrimos en gastos de servidor?
- ¿Hay anomalías en el gasto de nuestro servidor?

## Informe de resumen operativo

Haga clic en **Resumen operativo** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para conocer las métricas operativas de sus recursos informáticos (como costes de servidor, núcleos de CPU, coste por hora de instancia, etc. por perfil de virtualización) que se ejecutan en las instalaciones.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_3.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los de Computación - Resumen. Véase el elemento 2 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(3) Métricas operativas por categoría** - Utilice las opciones de la parte superior de este gráfico para mostrar de forma selectiva diversas métricas. En la lista **"Resumido por"** encontrará otras métricas. Utilice el gráfico para ver el gasto operativo actual en función de las opciones que seleccione.

**(4) Detalles** - La tabla **Detalles** proporciona el coste mensual actual para la métrica que seleccione de la lista **Resumido por**, y los recuentos y costes unitarios de todas las CPUs, servidores, memoria y horas de instancia relacionadas.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia operativa?
- ¿Dónde incurrimos en costes operativos?
- ¿Hay anomalías en nuestro gasto operativo?

## Informe de resumen de utilización

Haga clic en **Resumen de utilización** en la pestaña Colección de informes para abrir el informe. Utilice este informe para obtener una perspectiva de cómo la utilización de los recursos informáticos locales está repercutiendo en el coste. Podrá ver las métricas de utilización relacionadas con sus recursos informáticos locales (como costes de servidor, núcleos de CPU, capacidad de memoria, utilización media o máxima, etc.) desglosados por perfil de virtualización.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_4.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los siguientes filtros están disponibles en este informe. Estos filtros son acumulativos y afectan a todos los datos de la página, incluidos los KPI:

- **Perfil de virtualización** : seleccione un tipo específico de servidor local o en la nube para ver el impacto del gasto informático en ese tipo de servidor.
- **SO** - Seleccione un sistema operativo (SO) específico para ver el impacto del gasto de Compute en ese SO.
- **Entorno** - Seleccione un entorno específico (como Dev, Prod o Test) para limitar los datos del informe a los servidores de ese entorno.
- **Clase** - Seleccione una clase (el tamaño de las instancias reservadas) para limitar los datos del informe a una clase específica.
- **Ubicación** - Seleccione una ubicación específica para ver el impacto del gasto de Compute para esa ubicación.
- **Propósito** - Seleccione un propósito específico del servidor para ver el impacto del gasto de Compute en servidores con el mismo propósito.
- **Fabricante** : seleccione un proveedor de servicios en nube específico para limitar los datos del informe a los servicios de ese proveedor.

**(3) Métricas operativas por categoría**

- Este informe es similar al de Resumen Operativo, pero con métricas sobre el uso medio y máximo de la CPU, y el uso medio y máximo de la memoria.
- Utilice las opciones de la parte superior de este gráfico para mostrar de forma selectiva diversas métricas. En la lista **"Resumido por"** encontrará otras métricas.
- La tabla proporciona el coste mensual actual para la métrica que seleccione de la lista **Resumido por**, y los recuentos, costes unitarios, uso medio y pico de uso relacionados con CPUs, servidores, memoria y horas de instancia.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de utilización de los ordenadores?
- ¿Dónde incurrimos en costes de utilización?
- ¿Existen anomalías en la utilización de nuestros ordenadores?

## Informe de detalles del servidor anfitrión

Haga clic en **Detalles del servidor host** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para ver los gastos informáticos específicos de los equipos host físicos locales. El informe proporciona el coste del periodo actual, el número de servidores físicos y el coste unitario, junto con la utilización media y máxima.

**NOTA** : Un *hipervisor*, también llamado monitor de máquina virtual (VMM), es un programa de software que se ejecuta en una plataforma de hardware host real y supervisa la ejecución de los sistemas operativos invitados en las máquinas virtuales.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_5.png)

**(1) KPIs** - Los KPIs proporcionan una visión de alto nivel del gasto de su servidor host:

- **Coste YTD** - Este KPI muestra el gasto total en servidores host YTD. El gasto del periodo en curso figura como **Coste**.
- **Núcleos de CPU del servidor** : este KPI muestra el número actual de núcleos físicos del servidor. El KPI secundario muestra el coste por núcleo como **Coste por núcleo de CPU**.
- **Núcleo CPU Hipervisor** - Este KPI muestra el número actual de procesadores del hipervisor. El KPI secundario muestra el promedio de instancias por hipervisor como **Promedio # Instancias Virtuales por Hipervisor**.
- **Horas de Instancia Virtual** - Este KPI muestra la capacidad actual (como horas de instancia) de sus servidores virtuales. El KPI secundario muestra **el Coste por Hora de Instancia**.

**(2) Filtros** - Los filtros de este informe son los mismos que los del Resumen de utilización. Véase el elemento 2 del [informe Resumen de utilización](hbmcomputecollection.html).

**(3) Datos del servidor anfitrión**

- Utilice las opciones de la parte superior de este gráfico para añadir columnas con el **sistema operativo del hipervisor**, el **nombre de la nube** y la **ubicación** al gráfico.
- Utilice las pestañas **Núcleos de CPU** y **Capacidad de memoria** para ver la capacidad actual, el coste por unidad, la asignación y la utilización media/pico de sus núcleos de CPU y memoria.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de servidores anfitriones?
- ¿Dónde incurrimos en costes de utilización?

## Informe de detalles del servidor lógico

Haga clic en **Detalles del servidor lógico** en la pestaña Colección de informes para abrir el informe. Utilice este informe para ver los gastos informáticos específicos de las máquinas lógicas o virtuales. El informe proporciona el coste del periodo actual, el número de servidores y los costes unitarios, junto con la utilización media y máxima.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_6.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los de Computación - Resumen. Véase el elemento 2 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(3) Detalles del servidor lógico**

- Utilice las opciones situadas a la derecha de este gráfico para añadir columnas que enumeren el nombre del host, la plantilla de instancia, el nombre del entorno, la memoria total y el coste por GB al gráfico.
- Utilice la tabla para ver la capacidad actual, las horas de instancia, el recuento de núcleos, el coste unitario, la asignación y la utilización media/punta de sus servidores lógicos.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de servidores lógicos?
- ¿Dónde incurrimos en gastos?

## Informe Financial View

Haga clic en **Vista financiera** en la pestaña Colección de informes para abrir el informe. Utilice este informe para obtener una visión financiera de su gasto informático por clase, entorno, ubicación, sistema operativo o perfil de virtualización.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_7.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los de Computación - Resumen. Véase el elemento 2 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(3) Coste YTD Por**

- Utilice las opciones de la parte superior de este gráfico para ver el gasto anual en recursos informáticos por grupo de costes (servicios externos, hardware, etc.) frente a las subtorres de TI (servidores, transporte, voz, etc.). Esta información proporciona una visión general de su gasto global en Computación por ATUM Torre y Subtorre.
- La tabla muestra los mismos datos mes a mes, según su selección en la lista **Resumir costes por**.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia informática?
- ¿Dónde incurrimos en gastos informáticos?
- ¿Hay anomalías en nuestro gasto en informática?

## Por informe de aplicaciones

Haga clic en **Por aplicaciones** en la pestaña Colección de informes para abrir el informe. Utilice este informe para ver su gasto en informática por aplicación en todo su perfil de implantación.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11693_8.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Compute - Resumen. Véase el elemento 1 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los de Computación - Resumen. Véase el elemento 2 del [informe Resumen de cálculo](hbmcomputecollection.html).

**(3) Coste YTD por** - Utilice esta tabla para ver el gasto YTD en recursos informáticos por aplicación (por ejemplo, Active Directory, SAP Data Warehouse y Office 365). La tabla muestra el propietario de la aplicación, el perfil de carga de trabajo y el perfil de riesgo de cada aplicación. También se desglosan las horas de servidor y el coste por hora de servidor para cada aplicación.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia informática?
- ¿Dónde incurrimos en gastos informáticos?
- ¿Hay anomalías en nuestro gasto en informática?
- ¿Cuál es la distribución del gasto informático para una aplicación híbrida?
