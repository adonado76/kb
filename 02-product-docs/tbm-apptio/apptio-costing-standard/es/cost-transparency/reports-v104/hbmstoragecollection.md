---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Storage Insights & Colección de optimización"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Colección de almacenamiento"
source_path: "cost-transparency/reports-v104/hbmstoragecollection.html"
images:
  - "resources/images/hbm_images/hbmimages/11691_1.png"
  - "resources/images/hbm_images/hbmimages/11691_2.png"
  - "resources/images/hbm_images/hbmimages/11691_3.png"
  - "resources/images/hbm_images/hbmimages/11691_4.png"
  - "resources/images/hbm_images/hbmimages/11691_5.png"
  - "resources/images/hbm_images/hbmimages/11691_6.png"
  - "resources/images/hbm_images/hbmimages/11691_7.png"
  - "resources/images/hbm_images/hbmimages/11691_8.png"
  - "resources/images/hbm_images/hbmimages/11691_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Storage Insights & Colección de optimización

♦ Se aplica a: Hybrid Business Management en TBM Studio TBM Studio y posteriores

Utilice los informes de almacenamiento para conocer el coste, la capacidad y la utilización de sus recursos de almacenamiento. Los informes de esta colección le permiten analizar su perfil de gastos, comprender las métricas de almacenamiento, analizar los detalles de su almacenamiento (dispositivos y unidades lógicas) y comprender una vista de Aplicaciones de su almacenamiento. La recopilación proporciona informes granulares para que pueda optimizar los costes y la utilización del almacenamiento.

Esta colección de informes está diseñada para las siguientes funciones:

- Director de TI
- Equipo informático en TI
- Jefe de Operaciones
- Propietarios de servicios

Esta colección de informes se ajusta a los siguientes objetivos empresariales:

- Ver los costes de almacenamiento con respecto al plan para servidores locales y en la nube
- Seguimiento de la estrategia de la infraestructura de almacenamiento y del uso de los recursos de almacenamiento para determinar si la tendencia del gasto en almacenamiento es la esperada
- Capacidad de almacenamiento (instalada y direccionable) y evolución interanual

Estos informes permiten determinar lo siguiente:

- Si los niveles de almacenamiento se ajustan adecuadamente a la criticidad empresarial de su cartera de aplicaciones
- Unidades de almacenamiento que se acercan al final de su ciclo de vida útil
- El coste de la capacidad de almacenamiento no asignada
- El coste unitario medio del almacenamiento total disponible
- El coste unitario efectivo del almacenamiento asignado
- La tasa media de utilización por nivel de almacenamiento
- Las oportunidades son recuperar el almacenamiento infrautilizado

## Visualizar la colección de informes

1. Inicie sesión en Apptio.
2. En la página de **inicio**, haga clic en **Hybrid Business Management**.
3. En el menú Colección de informes, seleccione **Almacenamiento**. El informe **Resumen de almacenamiento** se abre por defecto.

## Informe resumido de almacenamiento

Utilice este informe para ver el gasto total en almacenamiento en toda la empresa y una vista de los costes de almacenamiento por torre y subtorre de TI.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_1.png)

**(1) Indicadores clave de rendimiento (KPI)** : los KPI ofrecen una visión de alto nivel del gasto en infraestructura:

- **On Prem Cost YTD** - Este KPI muestra el gasto global en servidores de almacenamiento on-premise YTD. Los gastos del periodo en curso figuran como **gastos a cargo de la empresa**.
- **Public Cloud Coste YTD** - Este KPI muestra el gasto global en servidores públicos de almacenamiento en nube YTD. Los gastos del periodo en curso figuran en **Public Cloud Cost.**
- **TB de espacio direccionable local** : este KPI muestra los terabytes de memoria local disponibles actualmente para programas y procesos. El KPI secundario muestra el coste medio por terabyte como **Coste medio por TB direccionable**.
- **Public Cloud Espacio utilizado TB** - Este KPI muestra los terabytes de memoria de nube pública actualmente en uso. El KPI secundario muestra el coste medio por terabyte de espacio utilizado como **Coste medio por TB de espacio utilizado**.

**(2) Gasto mensual en almacenamiento** : utilice este gráfico para ver la tendencia de gasto de 1 año en recursos de almacenamiento en sus servidores locales y de nube pública.

**(3) Costes de almacenamiento por** : haga clic en las pestañas **Grupos de costes**, **Torres de TI**, **Entorno** o **Proveedores** para ver gráficos del gasto actual en informática del mes. La tabla **Detalles** muestra el gasto del mes en curso, del trimestre anterior y del año anterior.

Preguntas contestadas:

- ¿Hay anomalías en nuestro gasto?
- ¿Se ajusta el gasto a nuestra estrategia de almacenamiento?
- ¿Cómo evoluciona la estrategia de infraestructuras?
- ¿Dónde incurrimos en gastos de almacenamiento?

## Informe sobre el perfil de gastos

Haga clic en **Perfil de gastos** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para ver los gastos previstos y la utilización de los recursos de Almacenamiento.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_2.png)

**(1) Indicadores clave de rendimiento (KPI)** : los KPI ofrecen una visión de alto nivel del gasto en infraestructura:

- **Coste YTD** - Este KPI muestra el gasto global en servidores YTD. El gasto del periodo en curso figura como **Coste**.
- **TB de espacio instalado** : este KPI muestra la cantidad de capacidad de almacenamiento utilizada en terabytes. El KPI secundario muestra el coste medio por terabyte instalado como **Coste medio por TB instalado**.
- **TB de espacio direccionable** : este KPI muestra los terabytes de memoria local disponibles actualmente para programas y procesos. El KPI secundario muestra el coste medio por terabyte como **Coste medio por TB direccionable**.
- **YoY Variación del coste de TB instalada** : este KPI muestra la variación interanual del coste de la memoria local instalada.

**(2) Gasto del mes en curso por** grupo de costes - Utilice este gráfico para ver el gasto de almacenamiento por grupo de costes para el mes en curso.

**(3) Espacio direccionable (TB) y coste medio por** - Utilice este gráfico para ver la cantidad de memoria disponible en terabytes al mes y el coste medio de ese espacio.

**(4) Gráficos circulares YTD de almacenamiento** - Los gráficos circulares muestran la relación de un tipo específico de almacenamiento por nivel, por ubicación o por fabricante. Utilice esta información como una visión rápida de su perfil de gasto en Almacenamiento.

Preguntas contestadas:

- ¿Hay anomalías en nuestro gasto?
- ¿Se ajusta el gasto a nuestra estrategia de almacenamiento?
- ¿Cómo evoluciona la estrategia de infraestructuras?
- ¿Dónde incurrimos en gastos de almacenamiento?

## Resumen operativo

Haga clic en **Resumen operativo** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para conocer las métricas operativas (como el coste, el coste medio o el espacio direccionable en terabytes) de su almacenamiento local.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_3.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Perfil de Gastos de Almacenamiento. Véase el elemento 1 del [informe Perfil del gasto en almacenamiento](hbmstoragecollection.html).

**(2) Filtros** - Los siguientes filtros están disponibles en este informe. Estos filtros son acumulativos y afectan a todos los datos de la página, incluidos los KPI:

- **Ubicación** - Seleccione una ubicación específica para ver el impacto del gasto en Almacenamiento para esa ubicación.
- **Fabricante** : seleccione un proveedor de servicios en nube específico para limitar los datos del informe a los servicios de ese proveedor.
- **Tipo** - Seleccione un tipo de propósito de servidor para ver el impacto del gasto de Almacenamiento en servidores por tipo.

**(3) Métricas operativas por categoría** - Utilice las opciones de la parte superior de este gráfico para mostrar de forma selectiva diversas métricas. En la lista **Resumir costes por** se encuentran disponibles otras métricas. Utilice el gráfico para ver el gasto actual en Almacenamiento en función de la métrica que seleccione.

**(4) Detalles del dispositivo** : esta tabla proporciona el coste mensual actual por ubicación para las métricas que seleccione en la lista **Resumir por**. Haga clic en cualquier enlace de la primera columna para ver la tendencia de gasto del TCO de almacenamiento y los detalles sobre el elemento seleccionado.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de almacenamiento?
- ¿Dónde incurrimos en gastos de almacenamiento?
- ¿Hay anomalías en nuestro gasto en almacenamiento?

## Resumen de utilización

Haga clic en **Resumen de utilización** en la pestaña Colección de informes para abrir el informe. Utilice este informe para comprender el impacto de sus recursos de almacenamiento locales en el coste y para ver las métricas de utilización (como el coste de almacenamiento, el espacio direccionable, el porcentaje de espacio asignado, el porcentaje de espacio utilizado y el coste por terabyte) de sus recursos de almacenamiento locales.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_4.png)

**(1) KPIs** - Los KPIs proporcionan una visión de alto nivel del gasto de su servidor host:

- **Coste YTD** - Este KPI muestra el gasto global en dispositivos de almacenamiento YTD. El gasto del periodo en curso figura como **Coste**.
- **Coste efectivo por TB direccionable** : este KPI muestra el coste efectivo (coste real) por terabyte de memoria local disponible actualmente para programas y procesos. El KPI secundario muestra los terabytes de almacenamiento disponible como **TB de espacio direccionable**.
- **Coste efectivo por TB asignado** : este KPI muestra el coste efectivo (coste real) por terabyte de almacenamiento utilizado. El KPI secundario muestra los terabytes de almacenamiento utilizado como **Espacio asignado TB**.
- **% Asignado de Espacio Direccionable** - Este KPI muestra el porcentaje actual de espacio direccionable que está asignado. El KPI secundario muestra el total de terabytes disponibles como **Espacio disponible TB**.

**(2) Métricas operativas por categoría** : este informe es similar al informe Resumen operativo, pero con métricas adicionales sobre el uso medio y máximo de la CPU, y el uso medio y máximo de la memoria. Utilice las opciones de la parte superior de este gráfico para visualizar la tendencia de los gastos para una métrica seleccionada en función de la métrica seleccionada en **Resumir costes por**.

**(3) Tabla** - La tabla proporciona el coste mensual actual para la métrica que seleccione de la lista **Resumir costes por**, y los recuentos, costes unitarios, uso medio y pico de uso relacionados con CPUs, servidores, memoria y horas de instancia. La primera columna cambia en función de su selección en la columna **Resumir costes por**. Haga clic en cualquier enlace de la primera columna para ver la tendencia de gasto del TCO de almacenamiento y los detalles sobre el elemento seleccionado.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de utilización del almacenamiento?
- ¿Dónde incurrimos en gastos de almacenamiento?
- ¿Existen anomalías en nuestra utilización del almacenamiento?

## Detalles de dispositivo

Haga clic en **Detalles del dispositivo** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para ver su gasto en servidores locales y dispositivos de almacenamiento físico (almacenamiento conectado a la red [NAS] y redes de área de almacenamiento [SAN]). El informe proporciona el coste, el coste YTD y las métricas relacionadas con la asignación y el uso del espacio.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_5.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Resumen de Utilización de Almacenamiento. Véase el elemento 1 del [informe Resumen de utilización](hbmstoragecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los del Resumen Operativo de Almacenamiento. Véase el elemento 2 del [informe Almacenamiento - Perfil de gasto](hbmstoragecollection.html).

**(3) Dispositivo de almacenamiento Detalles adicionales**

- Utilice las opciones de la parte superior de este gráfico para añadir columnas de **Ubicación** y **Fabricante** al gráfico.
- Utilice la tabla para ver detalles sobre dispositivos de almacenamiento específicos y comprender rápidamente el espacio instalado frente al espacio direccionable frente al espacio asignado.
- Haz clic en cualquier enlace de la columna **Aplicaciones compatibles** para ver información sobre las aplicaciones que utilizan el dispositivo de almacenamiento.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_6.png)

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de almacenamiento de dispositivos?
- ¿Dónde incurrimos en gastos de dispositivos de almacenamiento?

## Detalles del LUN de almacenamiento

Haga clic en **Storage LUN Details** en la pestaña Report collection para abrir el informe. Utilice este informe para ver sus gastos de almacenamiento por número de unidad lógica (LUN). El informe proporciona el coste del periodo actual, el coste YTD, el espacio total y el espacio utilizado.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_7.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Resumen de Utilización de Almacenamiento. Véase el elemento 1 del [informe Resumen de utilización](hbmstoragecollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los del Resumen Operativo de Almacenamiento. Véase el elemento 2 del [informe de síntesis operativa](hbmstoragecollection.html).

**(3) Detalles adicionales del LUN de almacenamiento** : utilice las opciones de la parte superior de la tabla para añadir columnas que enumeren el **Propósito** y la **Ubicación**. Utilice la tabla para ver el coste mensual actual, el coste YTD, el espacio total y el espacio utilizado para su almacenamiento lógico. Haz clic en cualquier enlace de la columna **Aplicaciones compatibles** para ver información sobre las aplicaciones que utilizan el dispositivo de almacenamiento.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de servidores lógicos?
- ¿Dónde incurrimos en gastos?

## Visión financiera

Haga clic en **Vista financiera** en la pestaña Colección de informes para abrir el informe. Utilice este informe como una visión financiera de su gasto en Almacenamiento por ubicación, tipo, fabricante, producto, modelo o fuente.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_8.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Perfil de Gastos de Almacenamiento. Véase el elemento 1 del [informe Perfil del gasto](hbmstoragecollection.html).

**(2) Coste YTD por** - Utilice las opciones de la parte superior de este gráfico para ver el gasto YTD en recursos de Almacenamiento por grupo de costes (Servicios Externos, Hardware, etc.) frente a las subtorres de TI (servidores, transporte, voz, etc.). Esta información proporciona una visión general de su gasto global en almacenamiento por ATUM Torre y Subtorre.

**(3)** Tabla - La tabla muestra los mismos datos mes a mes, según su selección en la lista **Resumir costes por**. Haga clic en cualquier enlace de la primera columna para ver los detalles del fondo de costes de infraestructura sobre el artículo en el que haga clic.

- ¿Cómo evoluciona nuestra estrategia de almacenamiento?
- ¿Dónde incurrimos en gastos de almacenamiento?
- ¿Hay anomalías en nuestro gasto en almacenamiento?

## Por aplicaciones

Haga clic en **Por aplicaciones** en la pestaña Colección de informes para abrir el informe. Utilice este informe para ver su gasto en almacenamiento por aplicación en todo su perfil de virtualización.

Este informe consta de los siguientes elementos:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_9.png)

**(1) KPIs** - Los KPIs de este informe son los mismos que los del Perfil de Gastos de Almacenamiento. Véase el elemento 1 del [informe Perfil del gasto](hbmstoragecollection.html).

**(2) LUN de almacenamiento por aplicación** : utilice esta tabla para ver el gasto hasta la fecha en recursos de LUN de almacenamiento por aplicación (por ejemplo, Active Directory, SAP Data Warehouse y Office 365). La tabla muestra el propietario de la aplicación, el espacio asignado y los porcentajes por nivel y entorno para cada aplicación. Haga clic en cualquier enlace de la columna **Nombre de la aplicación** para ver los detalles del conjunto de costes de infraestructura sobre la aplicación en la que haga clic.

Preguntas contestadas:

- ¿Cómo evoluciona nuestra estrategia de almacenamiento?
- ¿Dónde incurrimos en gastos de almacenamiento?
- ¿Hay anomalías en nuestro gasto en almacenamiento?
