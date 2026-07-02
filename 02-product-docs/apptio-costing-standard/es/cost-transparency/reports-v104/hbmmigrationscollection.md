---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Recopilación de informes sobre recomendaciones de migración - HBM"
breadcrumb: []
source_path: "cost-transparency/reports-v104/hbmmigrationscollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Recopilación de informes sobre recomendaciones de migración - HBM

- Se aplica a: Hybrid Business Management en TBM Studio TBM Studio y posteriores

Utilice los informes Recomendaciones de migración para perfeccionar su estrategia de migración de servidores locales a servidores en nube. Los informes le permiten comparar su gasto actual con el gasto potencial en infraestructura en nube. Utilice esta colección de informes para comprender qué áreas de su infraestructura actual pueden beneficiarse más de la migración, con KPI procesables y perspicaces y análisis de alto nivel. Esta información es especialmente útil para destacar el valor continuado de la migración a la nube.

Nota:

Los precios de los servicios en nube se recogen de las listas de precios publicadas por cada proveedor de nubes públicas. Las listas de precios se importan y actualizan una vez al mes. Los precios incluyen descuentos, impuestos y gastos de asistencia.

Para una introducción a los conceptos de HBM, véase [Acerca de Hybrid Business Management](../home.htm "(se abre en una pestaña o una ventana nueva)"). Para ver la lista completa de informes, consulte [Hybrid Business Management Reports](../../..hbm-reports.htm "(se abre en una pestaña o una ventana nueva)").

Esta colección de informes está diseñada para las siguientes funciones:

- Director de TI
- Grupo de aplicaciones
- Centro de excelencia en la nube

Esta colección de informes se ajusta a los siguientes objetivos empresariales:

- Tome decisiones de migración fundamentadas y basadas en datos
- Comparar los costes de la infraestructura local con la posible infraestructura en nube
- Comprender el valor de la migración

Estos informes permiten determinar lo siguiente:

- ¿Qué servidores debemos migrar primero?
- ¿Cómo podemos demostrar claramente el valor de la migración?
- ¿Cómo debemos priorizar la migración a lo largo del tiempo?

## Visualizar la colección de informes

1. Inicie sesión en Apptio.
2. En la página de **inicio**, haga clic en **Hybrid Business Management**.
3. En el menú de recogida de informes, seleccione **Recomendaciones de migración**. Se abre el informe **Resumen de la migración**.

## Informe resumido de migración

Utilice este informe para comparar los costes actuales de sus servidores locales con los costes potenciales de los servicios en la nube.

Este informe consta de los siguientes elementos:

**(1) KPI** : los KPI proporcionan una comparación de alto nivel de su gasto actual en servidores frente a los costes potenciales de los servidores en nube:

- **Coste anual actual de los** servidores: este KPI muestra el gasto global en servidores. El gasto por hora se muestra como **Coste por hora**.
- **Coste anual de AWS** - Este KPI muestra el coste anual potencial de Amazon Web Services ( AWS ). El gasto por hora se muestra en **AWS Coste por hora**.
- **Coste anual de Azure** - Este KPI muestra el coste anual potencial de Microsoft Azure. El gasto por hora se muestra en **Azure Coste por hora**.
- **Coste anual de Google** - Este KPI muestra el coste anual potencial de Google Cloud Proveedor (GCP). El gasto por hora se muestra en **Google Coste por hora**.

**(2) Filtros** - Los siguientes filtros están disponibles en este informe. Estos filtros son acumulativos y afectan a todos los datos de la página, incluidos los KPI:

- **Aplicación** - Seleccione una aplicación para ver el impacto de su estrategia de migración en una aplicación específica.
- **Entorno** - Seleccione un entorno para ver el impacto de su estrategia de migración en un entorno específico.
- **SO** - Seleccione un sistema operativo para ver el impacto de su estrategia de migración en un sistema operativo específico.
- **Ubicación** - Seleccione una ubicación para ver el impacto de su estrategia de migración en los servidores de una ubicación específica.
- Perfil de **virtualización** - Seleccione un perfil de virtualización para ver el impacto de su estrategia de migración en un tipo específico de servidor.

**(3) Ahorro potencial por** entorno: utilice este gráfico para ver su ahorro potencial de migración a la nube por entorno. Utilice las opciones situadas encima de la tabla para mostrar u ocultar entornos específicos.

**(4) Ahorro potencial por** centro de datos: utilice este gráfico para ver su ahorro potencial de migración a la nube por centro de datos. Utilice las opciones situadas encima de la tabla para mostrar u ocultar centros de datos específicos.

**(5) Ahorro potencial por finalidad** : utilice este gráfico para ver su ahorro potencial en la migración a la nube por tipo de servidor (servidores de aplicaciones, servidores web, servidores de bases de datos, servidores de directorio y servidores de correo).

Preguntas contestadas:

- ¿Qué proveedores de servicios en la nube son los más rentables?
- ¿Es mejor trasladar primero las cargas de trabajo de los entornos de desarrollo y pruebas a la nube para permitir las pruebas?
- ¿Podemos arriesgarnos a un tiempo de inactividad en nuestro entorno de producción, o contiene datos sensibles que no queremos en la nube pública?
- ¿Es mejor trasladar los servidores web a la nube?
- ¿Debemos consolidar nuestros centros de datos?

## Informe de migración de la carga de trabajo

Utilice este informe para mostrar una vista basada en la carga de trabajo de la comparación de migraciones.

Este informe consta de los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe Resumen de Migración. Véase el elemento 1 del [Informe de síntesis de la migración](hbmmigrationscollection.html).

**(2) Cargas de trabajo, cargas de trabajo rehospedadas y utilización** : utilice las siguientes pestañas para ver los costos y el uso de las cargas de trabajo de migración y las cargas de trabajo rehospedadas:

- **Todas las cargas de trabajo** : utilice este gráfico para comparar el coste de sus diez principales cargas de trabajo en sus servidores locales actuales frente al coste de ejecutar servicios informáticos similares (CPU/RAM) en AWS, Azure y GCP. Utilice los selectores situados a la derecha del gráfico para controlar los datos que se muestran. Debajo del gráfico, la tabla **Detalles de la carga de trabajo** muestra datos detallados de todas sus cargas de trabajo.
- **Rehost Workloads** - Utilice este gráfico para ver sus diez principales cargas de trabajo designadas para ser realojadas en la nube, y para comparar los costes de esas cargas de trabajo en servidores locales frente al coste de ejecutar servicios informáticos similares (CPU/RAM) en AWS, Azure, y Google. Debajo del gráfico, la tabla **Detalles de la carga de trabajo de realojamiento** muestra datos detallados de las cargas de trabajo designadas para realojarse en la nube.
- **Utilización** - Utilice esta tabla para ver y comparar los costes de todas las cargas de trabajo. Haga clic en las casillas de verificación situadas encima de la tabla para añadir columnas adicionales a la tabla. Esta tabla es similar a la de la pestaña **Todas las cargas de trabajo**, pero con datos adicionales.

Preguntas contestadas:

- ¿Qué proveedores de servicios en la nube son los más rentables?
- ¿Es mejor trasladar primero las cargas de trabajo de los entornos de desarrollo y pruebas a la nube para permitir las pruebas? ¿Podemos arriesgarnos a un tiempo de inactividad en nuestro entorno Prod o contiene datos sensibles que no queremos en la nube pública?
- ¿Es mejor trasladar los servidores web a la nube?
- ¿Debemos consolidar nuestros centros de datos?

## AWS Informe sobre migración

Utilice este informe para explorar las estadísticas de migración con los metadatos adicionales que proporciona AWS.

Este informe consta de los siguientes elementos:

**(1) Filtros** - Controle qué datos se muestran en la tabla seleccionando filtros. Los filtros son acumulativos.

**NOTA** : El filtro **Tipo de término** define cómo se consumen y se pagan los servicios informáticos, si bajo demanda o reservados. Si selecciona Reservado, el tipo de pago puede ser Todo por adelantado, Parcialmente por adelantado o Sin adelantado.

**(2) Tabla** - Esta tabla contrasta su infraestructura actual de servidores con las recomendaciones de AWS.

Preguntas contestadas:

- ¿Cómo podemos adaptar AWS a nuestras necesidades?
- ¿Qué opciones hay disponibles en AWS?

## Recomendaciones de migración - Casos de uso adicionales

Utilice este informe para explorar otras opciones a adoptar como parte de una estrategia de migración. Actualmente se contemplan dos casos. Cada caso tiene una tabla en su propia pestaña.

- La pestaña **Tech Refresh** se centra en los servidores antiguos, que son los principales candidatos para la migración a la nube pública.
- La pestaña **Entornos de desarrollo/prueba** se centra en los servidores que ejecutan entornos de prueba. Estos servidores pueden migrarse primero de forma selectiva y con bajo riesgo mientras sigue evaluando su estrategia global.

Este informe consta de los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe Resumen de Migración. Véase el elemento 1 del [Informe de síntesis de la migración](hbmmigrationscollection.html).

**(2) Filtros** - Los cinco primeros filtros de este informe son los mismos que los del informe Resumen de migraciones. Véase el elemento 2 del [Informe de síntesis de la migración](hbmmigrationscollection.html).

- **Fabricante** - Seleccione un fabricante de servidores.

**(3) Recomendaciones** : utilice esta tabla para ver los servidores locales que cumplen determinados criterios relacionados con la antigüedad. Observe que en la imagen anterior no se muestra ningún servidor de este tipo. Haga clic en la pestaña **Entornos de desarrollo/prueba** para ver una tabla que muestra los servidores de desarrollo y prueba.

Preguntas contestadas:

- ¿Qué opciones hay disponibles en AWS?
- ¿Cómo podemos adaptar AWS a nuestras necesidades?

## Comparación de migraciones

Utilice este informe para analizar su infraestructura de servidores en función de diversas combinaciones de requisitos.

Este informe consta de los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe Resumen de Migración. Véase el elemento 1 del [Informe de síntesis de la migración](hbmmigrationscollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los del informe Casos de uso adicionales. Véase el elemento 2 del [informe Casos de uso adicionales](hbmmigrationscollection.html).

**(3) Configuración del servidor** : utilice esta tabla para comparar los costes de los servidores locales con las posibles alternativas en la nube, con datos adicionales como la ubicación del servidor en la nube. Seleccione las opciones sobre la tabla para añadir columnas adicionales a la tabla.

Preguntas contestadas:

- ¿Cómo cambiará la ubicación de mis servidores con la migración?
- ¿Cuál es el coste por hora de uso de un servidor en nube específico?

## Recomendaciones de migración - Comparación de la utilización

Utilice este informe para analizar su infraestructura de servidores en función de diversas combinaciones de requisitos.

Este informe consta de los siguientes elementos:

**(1) KPIs** - Los KPIs de este informe son los mismos que los del informe Resumen de Migración. Véase el elemento 1 del [Informe de síntesis de la migración](hbmmigrationscollection.html).

**(2) Filtros** - Los filtros de este informe son los mismos que los del informe Casos de uso adicionales. Véase el elemento 2 del [informe Casos de uso adicionales](hbmmigrationscollection.html).

**(3) Configuración del servidor** : utilice esta tabla para comparar los costes de los servidores locales con las posibles alternativas en la nube, con datos adicionales como la ubicación del servidor en la nube. Seleccione las opciones sobre la tabla para añadir columnas adicionales a la tabla.

Preguntas contestadas:

- ¿Cómo cambiará la ubicación de mis servidores con la migración?
- ¿Cuál es el coste por hora de uso de un servidor en nube específico?
