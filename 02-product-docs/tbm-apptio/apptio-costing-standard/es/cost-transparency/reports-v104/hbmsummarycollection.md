---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Recopilación de informes resumidos"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Diseños de versiones anteriores"
  - "Informes híbridos de gestión empresarial"
source_path: "cost-transparency/reports-v104/hbmsummarycollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Recopilación de informes resumidos

Utilice la colección de informes Resumen para ver el coste, la capacidad y la utilización de los servidores locales y de la nube pública. Los informes le permiten analizar su gasto, comprender mejor su infraestructura completa con métricas clave y entender las diferencias de coste entre nubes públicas y privadas. Utilice esta colección de informes para comprender la salud financiera general de su despliegue con respecto al plan, con KPI procesables y perspicaces y análisis de alto nivel. Esta información es especialmente útil para desarrollar una estrategia eficaz de migración a la nube.

Esta colección de informes está diseñada para las siguientes funciones:

- Vicepresidente o Director de Infraestructura o TI
- CIO o CTO

## Visualizar la colección de informes

1. Inicie sesión en Apptio.
2. En la página de **inicio**, haga clic en **Hybrid Business Management**.
3. En el menú Colección de informes, seleccione **Resumen**. El informe de **Despliegue** se abre por defecto.

## Informe de despliegue

Utilice el informe de implantación de HBM para conocer el coste total de sus servidores y poder comparar el coste de los servidores locales con el de los servidores de nube pública.

**CONSEJO** : El *despliegue* se refiere a la ubicación de sus servidores en las instalaciones o en la nube pública. Las implantaciones locales pueden incluir servidores de nube privada, centros de datos locales, centros de datos MSP, co-localización, etc.

**Casos prácticos** :

- Comparación de los costes de infraestructura con el plan
- Equilibrio entre el gasto en nube pública y local
- Seguimiento de la estrategia de infraestructura y uso de recursos en la nube
- Seguimiento del equilibrio entre las torres de recursos informáticos de servidor, almacenamiento y red para determinar si el gasto en infraestructura evoluciona según lo previsto

Este informe contiene los siguientes elementos:

**(1) Indicadores clave de rendimiento (KPI)** : los KPI ofrecen una visión de alto nivel del gasto en infraestructura. Las flechas indican el gasto real actual como porcentaje por encima o por debajo del plan, que se muestra como métrica secundaria.

- **Coste de las infraestructuras hasta la fecha** : este indicador muestra el gasto global en infraestructuras hasta la fecha, con el porcentaje por encima o por debajo de lo previsto. Los gastos previstos se muestran como **Target Spend YTD**.
- **On Prem Cost YTD** - Este KPI muestra el coste global del uso de servidores on-premise YTD, con el porcentaje por encima o por debajo del plan. El gasto previsto se muestra como **Gasto previsto On Prem**.
- **Public Cloud YTD** - Este KPI muestra el coste global del uso de su servidor de nube pública YTD, con el porcentaje por encima o por debajo del plan. El gasto previsto figura en **Public Cloud Target**.

**(2) Resumen de costes de infraestructura** : utilice este gráfico para ver la tendencia general del gasto en infraestructura de nube pública y local. Haga clic en la pestaña **3 años** para ver la tendencia a lo largo de varios años.

Preguntas contestadas:

- ¿Está mi gasto global en infraestructuras en línea con mi estrategia de infraestructuras?
- ¿La evolución de los gastos se ajusta a lo previsto?

**(3) Public Cloud Despliegue** - Utilice este gráfico para ver un resumen de 12 meses del gasto en servidores de nube pública para el año en curso, desglosado por las torres de recursos informáticos de computación, almacenamiento y red. Haga clic en la pestaña **3 años** para ver los datos anuales del año en curso y de los dos años anteriores. El cuadro de la derecha muestra el porcentaje de variación entre los gastos reales y los previstos para el periodo en curso.

Preguntas contestadas:

- ¿Cómo evoluciona la estrategia de infraestructuras?
- ¿Consumimos demasiados recursos en la nube?
- ¿Está funcionando bien nuestra estrategia para pasar a la nube?
- ¿Qué recursos (computación/almacenamiento/red) constituyen la mayor parte de nuestro uso local y en la nube? ¿Es lo esperado?

**(4) Despliegue local** : utilice este gráfico para ver un resumen de los gastos de 12 meses en servidores locales para el año en curso, desglosados por las torres de recursos informáticos de informática, almacenamiento y red. Haga clic en la pestaña **3 años** para ver los datos anuales del año en curso y de los dos años anteriores. El cuadro de la derecha muestra el porcentaje de variación entre el gasto real y el previsto para el periodo en curso.

Preguntas contestadas:

- ¿Cómo evoluciona la estrategia de infraestructuras?
- ¿Consumimos demasiados recursos en la nube?
- ¿Está funcionando bien nuestra estrategia para pasar a la nube?
- ¿Qué recursos (servidor/almacenamiento/red) constituyen la mayor parte de nuestro uso local y en la nube? ¿Es lo esperado?

## Informe sobre dominios

Haga clic en **Dominios** en la pestaña Colección de informes para abrir el informe. Utilice el informe Dominios HBM para comprender la distribución de los servicios locales y de nube pública en varios dominios. El informe le permite ver el gasto en sus dominios de infraestructura, capacidad y costes unitarios.

**CONSEJO** : *Dominios* hace referencia a las torres de recursos informáticos en la taxonomía ATUM : Computación, Almacenamiento, Centros de Datos y Red.

**Casos prácticos** :

- Ver los costes de infraestructura por torre de recursos informáticos
- Comprender cómo se distribuyen los costes y la capacidad entre los sistemas informáticos y de almacenamiento en las distintas implantaciones
- Determinar si la capacidad de los recursos está correctamente distribuida entre los despliegues en las instalaciones y en la nube en lo que respecta a la capacidad y el coste unitario
- Visión de alto nivel de los costes de los centros de datos locales

El informe contiene los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe de Despliegue. Véase el elemento 1 del [informe de despliegue](hbmsummarycollection.html).

**(2) Resumen de la torre de infraestructuras** : utilice este gráfico para ver la tendencia de gasto de 1 ó 3 años por dominio (informática, almacenamiento, centros de datos y red) para servidores locales y en la nube.

Preguntas contestadas:

- ¿Se ajusta mi gasto global en infraestructuras a lo previsto?
- ¿Se ajusta al plan la distribución de los gastos entre los distintos ámbitos?

**(3) Compute** - Haga clic en **Compute** para saltar al informe **Resumen de Compute**.

- La pestaña **Coste informático** muestra la tendencia de gasto de 1 año en recursos informáticos por despliegue. El cuadro de la derecha enumera los gastos del mes en curso y el porcentaje de variación de los gastos desde el mes anterior.
- Haga clic en la pestaña **Capacidad de cálculo** para ver la tendencia de 1 año de horas de instancia utilizadas por despliegue. La tabla de la derecha muestra el uso de las horas de instancia durante el mes en curso y el porcentaje de cambio en el uso desde el mes anterior.
- Haga clic en la pestaña **Coste de la Unidad de Cálculo** para ver la tendencia de 1 año del coste de la hora de instancia por despliegue. La tabla de la derecha muestra el coste por hora de instancia para el mes en curso.

Preguntas contestadas:

- ¿Cómo se distribuyen los costes y la capacidad informática entre las distintas implantaciones?
- ¿La métrica del coste unitario prueba/desmiente nuestra hipótesis de estrategia de migración a la nube?
- ¿Tenemos un gasto alto o bajo en las instalaciones o en la nube? ¿Por qué?

**(4) Almacenamiento** - Haga clic en **Almacenamiento** para saltar al informe **Resumen de almacenamiento**.

- La pestaña **Coste de almacenamiento** muestra la tendencia de gasto de 1 año en recursos de almacenamiento por implantación. En el cuadro de la derecha figuran los gastos del mes en curso y el porcentaje de variación del gasto desde el mes anterior.
- Haga clic en la pestaña **Capacidad de almacenamiento** para ver la capacidad de rodadura de 1 año para el espacio direccionable local y el espacio utilizado en la nube pública.
- Haga clic en la pestaña **Coste unitario de almacenamiento** para ver la tendencia de 1 año del coste unitario del espacio direccionable local y del espacio utilizado en la nube pública.

Preguntas contestadas:

- ¿Cómo se distribuyen los costes y la capacidad de almacenamiento entre las distintas implantaciones?
- ¿La métrica del coste unitario prueba/desmiente nuestra hipótesis de estrategia de migración a la nube?
- ¿Tenemos un gasto alto o bajo en las instalaciones o en la nube? ¿Por qué?
- ¿Está la capacidad de recursos correctamente distribuida entre las instalaciones y la nube?

**(5) Centro de datos** - Haga clic en **Centro de datos** para saltar al informe **Resumen del centro de datos**. Utilice este gráfico y esta tabla para ver la tendencia de los costes de sus centros de datos. Esta información puede ayudarle a evaluar los cambios en los costes YTD y el coste de sus centros de datos por pie cuadrado.

Preguntas contestadas:

- ¿Hay anomalías en el uso de los recursos?
- ¿Gasta mucho la organización en alguno de estos ámbitos/recursos? ¿Por qué?

## Informe sobre nube pública frente a nube privada

Haga clic en **Nube pública frente a privada** en la pestaña Colección de informes para abrir el informe. Utilice el informe Nube pública frente a nube privada para comprender el coste total de propiedad (TCO) de los servicios de nube pública y nube privada. El informe permite ver la tendencia de los gastos en nube pública por Torre de TI (categoría de servicio) y la tendencia de los gastos en nube privada por reserva de host. Esta información es especialmente útil para analizar la eficiencia y la capacidad de los recursos.

**CONSEJO** : *La nube privada* es un modelo de despliegue de infraestructura que se ejecuta como nube en la nube, pero gestionada por la empresa. No dispone de recursos compartidos como la nube pública.

**Casos prácticos** :

- Comparar el coste total de propiedad de la nube pública con la privada
- Conozca sus costes actuales de CPU, RAM y almacenamiento
- Realice un seguimiento del uso de los recursos a lo largo del tiempo para fundamentar su estrategia de migración a la nube
- Determinar si los costes se ajustan a los recursos y la capacidad de las implantaciones

El informe contiene los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe de Despliegue. Véase el elemento 1 del [informe de despliegue.](hbmsummarycollection.html)

**(2) Public Cloud TCO** - Haga clic **Public Cloud TCO** para ir a la Public Cloud página de inicio. Utilice este gráfico para ver la tendencia del gasto por dominio y servicio durante un año. En el cuadro de la derecha figura el coste de cada servicio para el periodo en curso y el porcentaje de variación desde el periodo anterior. Haga clic en la pestaña **3 años** para ver los datos anuales del año en curso y de los dos años anteriores.

Preguntas contestadas:

- ¿Se ajusta mi gasto global en nube pública a lo previsto?
- ¿Se ajusta al plan la distribución del gasto por categorías de servicios?

**(3)** Nube privada - Haga clic en **Nube privada** para ir al informe Nube privada - VMWare. Utilice este gráfico para ver la tendencia de gasto de 1 año de todos los servidores de nube privada aprovisionados y la tendencia de coste por host de nube privada. La tabla de la derecha enumera los costes de CPU, RAM y almacenamiento para el periodo actual. Haga clic en la pestaña **3 años** para ver los datos anuales del año en curso y de los dos años anteriores.

Preguntas contestadas:

- ¿Se ajusta mi gasto global en nube privada a lo previsto?
- En resumen, ¿se están utilizando los recursos de forma eficiente?
- ¿Cuál es el coste de la capacidad no utilizada?
- ¿Puedo reutilizar esta capacidad antes de comprar más recursos para satisfacer las próximas demandas de la organización?

## Informe sobre la variación de las infraestructuras

Haga clic en **Varianza de la infraestructura** en la pestaña Recopilación de informes para abrir el informe. Utilice este informe para conocer los costes reales de las infraestructuras en comparación con el presupuesto. El informe ofrece varias vistas de las desviaciones de la infraestructura para ayudarle a analizar la eficiencia del presupuesto y el gasto. Esta información es especialmente útil para determinar si el gasto en infraestructuras se ajusta al presupuesto y si es necesario revisarlo.

**Casos prácticos** :

- Comparación de los gastos reales en infraestructuras con los gastos previstos
- Conozca sus costes actuales por torre de recursos informáticos
- Seguimiento de la desviación de gastos para el mes, trimestre y año en curso

El informe contiene los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe de Despliegue. Véase el elemento 1 del [informe de despliegue](hbmsummarycollection.html).

**(2) Gasto real frente a gasto previsto** : utilice este gráfico para ver la tendencia de un año del coste real frente al plan para gastos de infraestructura. El filtro **Despliegue** le permite limitar los datos a datos locales o datos de nube pública. El cuadro **"Detalles"** enumera los costes mensuales por torre informática.

Preguntas contestadas:

- ¿Cómo evolucionan mis costes reales de infraestructura en comparación con el gasto previsto?
- ¿Estoy en línea con el presupuesto?
- ¿Debo revisar mi presupuesto?

**(3) Desviación de los gastos reales del plan** : este gráfico muestra la desviación entre los gastos de infraestructura hasta la fecha y el plan según la métrica que seleccione de la lista. Las barras rojas de la izquierda representan costes por encima del presupuesto. La tabla de la derecha enumera los costes interanuales, el objetivo de gastos y la desviación para cada métrica basada en su selección de la lista. Haga clic en las pestañas **Trimestre hasta la fecha** o **Mes en curso** para alternar entre intervalos de fechas.

Preguntas contestadas:

- ¿Cuál es la diferencia entre mis gastos previstos y los reales?
- ¿Dónde está la mayor variación?
