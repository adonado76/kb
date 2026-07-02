---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Supervisa la interacción con los informes de uso de Apptio"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Conceptos básicos sobre los informes"
source_path: "studio/admin/monitor-engagement-apptio.html"
images:
  - "resources/images/studio_images/studioimages/icons/setting-icon.png"
  - "resources/images/studio_images/studioimages/studio_apptiousagedashboard_6_sui.png"
  - "resources/images/studio_images/studioimages/usage_summary_sui.png"
  - "resources/images/studio_images/studioimages/use_case_mapping2_sui.png"
  - "resources/images/studio_images/studioimages/use_case_mapping4_sui.png"
  - "resources/images/studio_images/studioimages/use_case_mapping5_sui.png"
  - "resources/images/studio_images/studioimages/use_case_mapping_columns_sui.png"
  - "resources/images/studio_images/studioimages/user_logins_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Supervisa la interacción con los informes de uso de Apptio

PRECAUCIÓN:

Apptio no se puede personalizar. Cualquier personalización provocará un fallo crítico del sistema y será necesario deshacer todos los cambios. Si desea mejorar los informes disponibles, póngase en contacto con Apptio Support o Product Management.

Como administrador de la aplicación Apptio, es posible que desee controlar el número de personas que utilizan las aplicaciones Apptio y los informes que consultan. El panel de control de uso de Apptio es una herramienta de informes analíticos que le ofrece información sobre cómo los usuarios de su organización utilizan las aplicaciones de Apptio. En concreto, ApptioUsage puede ayudarle a identificar lo siguiente:

- En general Apptio informe sobre las métricas de compromiso en toda su organización
- Usuarios activos e inactivos
- Informes populares e impopulares
- Rendimiento de los informes y tiempos de carga

Apptio recomienda que la revisión periódica de sus análisis de uso de Apptio forme parte de su estrategia de adopción.

## Active el panel de control Apptio Usage

Apptio Su uso está disponible en las versiones TBM Studio 12.7.1 y posteriores. Una vez que haya actualizado, debe importar el proyecto de **uso** a su entorno.

1. En TBM Studio, en el menú **Configuración** (![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/setting-icon.png)), haga clic en **Importar**.
2. Haga clic en **Uso** y, a continuación, en **Aceptar**.

   ![panel de uso del prorrateo](../../resources/images/studio_images/studioimages/studio_import%20project_usage_sui.png)

   Espere a que se calcule el proyecto. Los cálculos pueden llevar más de una hora, dependiendo de la complejidad de su proyecto.
3. Una vez finalizados los cálculos, en el menú **Configuración**, haga clic en **Access
   Administration**. También puede conectarse a Enhanced Access
   Administration y navegar hasta **Access Administration**.
4. En la pestaña **Aplicaciones**, junto a **Uso**, haga clic en **Mostrar** para hacerlo visible. Si desea modificar aún más el acceso a las funciones, haga clic en **Editar visibilidad**.

Ahora puede acceder a **Utilización** en el menú Proyecto que enumera todas las aplicaciones de Apptio.

## Configurar la cadencia de actualización de la utilización

Después de activar el proyecto Utilización, puede establecer un calendario de actualizaciones. **Se recomienda empezar con una actualización semanal fuera de horario**, por ejemplo cada sábado o domingo, y ajustar posteriormente la frecuencia si cambian las necesidades.

1. En TBM Studio, haga clic en **Build** > **Promotion Options**.
2. Haga clic en **Actualizaciones periódicas**.
3. Configure la frecuencia de repetición que desee y, a continuación, haga clic en **Guardar**.
4. Haga clic en **Promociones periódicas**.
5. Configure la recurrencia para que se produzca justo después de las actualizaciones y, a continuación, haga clic en **Guardar**

## Apptio Informes del panel de control de uso

Los siguientes informes están disponibles en el panel de control Apptio Usage.

## Informe de resumen de uso

El informe Resumen de uso proporciona una rápida visión general de la participación de los usuarios, lo que resulta especialmente útil para que las TBMA comprendan el valor que los usuarios están obteniendo de Apptio y las áreas de adopción que podrían necesitar más atención. El informe Resumen de uso proporciona información sobre el usuario en los paneles de la izquierda e información sobre el uso en los paneles de la derecha. Cada panel muestra indicadores clave de rendimiento (KPI) que proporcionan información sobre la participación.

![resumen de uso](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/usage_summary_sui.png)

- **(1)** **Filtros de usuario** - Seleccione un tipo o nombre de usuario para filtrar los datos que aparecen en los paneles de la izquierda que muestran datos de usuario.
- **(2)** **Recuento de usuarios** - Este KPI muestra el número de usuarios únicos que se han conectado durante el mes seleccionado y el número medio de conexiones por usuario.
- **(3)** **Accesos** - Este KPI muestra el número de accesos del mes seleccionado en comparación con el mes anterior.
- **(4)** **Accesos y usuarios** - Utilice este gráfico para ver el número de usuarios y accesos del mes hasta la fecha, las tendencias en la actividad de los usuarios y los cambios en la adopción.
- **(5)** **Resumen de inicios de sesión por usuario** - Utilice esta tabla para ver el total de inicios de sesión por usuario del mes, trimestre y año hasta la fecha. Haga clic en cualquier elemento de la columna **Nombre completo** para profundizar en datos específicos del usuario.
- **(6)** **Filtros de** uso: seleccione un entorno, tipo de usuario o nombre de usuario para filtrar los datos que aparecen en los paneles de la derecha que muestran los datos de uso. La configuración por defecto del filtro **Entorno** es **Producción**.
- **(7)** **Vistas** - Este KPI muestra el número de informes vistos durante el mes seleccionado en comparación con el mes anterior.
- **(8)** **Usuarios** - Este KPI muestra el número de usuarios únicos que han visto informes en el mes seleccionado.
- **(9)** **Uso de informes** - Utilice este gráfico para ver el total de informes y el número de espectadores únicos del mes hasta la fecha. Este elemento puede poner de relieve las tendencias en el uso general y ayudarle a comprender el valor de informes específicos.
- **(10)** **Ver resumen por informe** : esta tabla enumera informes específicos y sus cantidades de vistas por mes, trimestre y año hasta la fecha. Haga clic en cualquier elemento de la columna **Nombre del informe** para profundizar en datos específicos, como el tiempo de carga y el caso de uso.

## Informe de accesos de usuarios

El informe de **inicios de sesión de usuarios** muestra detalles más detallados sobre los usuarios, como las horas específicas de inicio de sesión, la duración de la sesión y la actividad durante el inicio de sesión.

![informe de inicio de sesión de usuario](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/user_logins_sui.png)

- **(1)** **Recuento de usuarios** - Este KPI muestra el número de usuarios únicos que se han conectado durante el mes seleccionado y el número medio de conexiones por usuario. Este KPI también incluye la diferencia intermensual en porcentaje.
- **(2)** **Accesos** - Este KPI muestra el número de accesos en lo que va de mes comparado con el número de accesos del mes anterior. Este KPI también incluye la diferencia intermensual en porcentaje.
- **(3)** **Usuario más activo** - El KPI muestra el usuario más activo en su producto Apptio durante el mes seleccionado. Puede utilizar este elemento para identificar rápidamente a los principales adoptantes y examinar cómo utilizan el sistema.
- **(4)** **Filtro de tipo de usuario:** seleccione un tipo de usuario para filtrar los datos de inicio de sesión del usuario.
- **(5)** **Usuarios e inicios de sesión a lo largo del tiempo** - Utilice este gráfico para ver el número de usuarios únicos que han iniciado sesión en comparación con el número total de inicios de sesión del mes hasta la fecha. Lo ideal es que ambos valores aumenten con el tiempo, lo que sugiere una adopción adecuada entre su base de usuarios. Si ambos valores disminuyen, este gráfico puede mostrarle qué periodos debe investigar más.
- **(6)** **Inactividad de usuarios** - Utilice este gráfico para ver una lista de los usuarios menos activos, la hora de su último acceso y si el último inicio de sesión se produjo en los últimos 30 días. Combine la información de este gráfico con la del gráfico Usuarios e inicios de sesión a lo largo del tiempo para identificar a los usuarios que podrían no haber adoptado adecuadamente sus soluciones Apptio.
- **(7)** **Detalles del usuario - Historial de inicio de sesión** - Utilice esta tabla para ver los historiales de inicio de sesión de usuarios individuales, incluida la fecha, la hora y la información del navegador. Haga clic en **Ver historial** en cualquier fila para ver la actividad de un usuario específico mientras estaba conectado. Puede ser una herramienta valiosa para solucionar problemas inesperados que experimenten sus usuarios.

## Informe Vistas del informe

El informe Visualizaciones de informes proporciona métricas detalladas sobre la visualización de proyectos e informes.

![informe vistas informe](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_apptiousagedashboard_6_sui.png)

- **(1)** **Visualizaciones** - Este KPI muestra el número total de visualizaciones del informe durante el mes seleccionado, y la diferencia intermensual en porcentaje.
- **(2)** **Informe más visto y espectador más activo** :
  - **Informe más visto** - Este KPI muestra el informe con más vistas durante el mes seleccionado.
  - **Visualizador más activo** - Este KPI muestra el usuario con más visualizaciones de todos los informes durante el mes seleccionado.
- **(3)** **Filtros** - Seleccione un entorno, informe, proyecto o nombre de usuario para filtrar los datos mostrados en el informe.
- **(4)** **Uso a lo largo del tiempo por proyecto** - Utilice este panel para ver el uso por proyecto a lo largo del tiempo. Seleccione una opción encima de los gráficos para mostrar los datos del usuario, los datos del informe, los datos de inicio de sesión o los datos de visualización. El gráfico circular muestra la métrica seleccionada en todos los proyectos. El gráfico de barras muestra la misma métrica en lo que va de mes.
- **(5)** **Informes por visitas** - Utilice este gráfico para ver los informes que reciben más visitas y el número de usuarios únicos que ven esos informes. Puede hacer clic en **Vistas** o en **Recuento de usuarios únicos** para filtrar el gráfico sólo por esa métrica. Haz clic de nuevo para volver a la vista original.
- **(6)** **Informes por usuarios** - Utilice esta tabla para ver las sesiones de usuario ordenadas por nombre de informe. Puede expandir los nombres de los informes para ver todos los usuarios que accedieron al informe y, a continuación, profundizar en la información sobre las sesiones de ese usuario.

## Informe Informe de resultados

El informe Rendimiento muestra los tiempos de carga experimentados por sus usuarios. Estos datos le permiten conocer los problemas de rendimiento y cómo solucionarlos.

![informe de resultados](../../resources/images/studio_images/studioimages/studio_usage%20dashboard_current%20month_sui.png)

- **(1)** **Filtros** - Seleccione un entorno, informe, proyecto o nombre de usuario para filtrar los datos mostrados en el informe.
- **(2)** **Percentiles de tiempo de carga de informes - Top 5** - Utilice este gráfico para ver los cinco informes de carga más lenta. Por ejemplo, el percentil 20 (o " P20 ") de los tiempos de carga de los informes representa el 20% de los tiempos de carga más lentos.
- **(3)** **Informe de latencia - Top 5** - Utilice este gráfico para ayudar a identificar la causa del bajo rendimiento. A continuación, utilice las tablas **Tiempo de carga** y **Latencia** para investigar el origen del problema. Las siguientes métricas de rendimiento proporcionan datos relacionados con los cinco informes de carga más lenta:
  - **Latencia** - Tiempo que tarda el tráfico de red en viajar entre el ordenador de un usuario y el centro de datos de Apptio.
  - **Tiempo de solicitud** - El tiempo que tarda la solicitud en ser recibida por el centro de datos de Apptio.
  - **Tiempo de carga** : tiempo que tarda el centro de datos de Apptio en calcular los datos del informe solicitados tras recibir una petición.
- **(4)** **Tiempo de carga** y **latencia** - Utilice estas tablas para investigar problemas relacionados con el rendimiento. Cada cuadro está organizado por diferentes elementos, pero suelen incluir los siguientes:

  **tiempo del percentil 90**

  **Tiempos más rápidos y más lentos**

  **Porcentaje del tiempo total de espera** - Es el porcentaje del tiempo total de carga para la métrica de rendimiento dada. La línea central oscura es el centro de este gráfico. Cuanto más a la derecha esté la línea, más tiempo se tarda en cargar.

  Haga clic en **Ver detalles** para profundizar en los detalles. Entre los cuadros específicos figuran los siguientes:
  - **Tiempo de carga-** Las entradas se ordenan por Informe / ID de usuario / InitalLoad o SlicersApplied. Un factor que puede aumentar el tiempo de cálculo de la solicitud es el uso de ciertas consultas de soporte en Apptio que no se pueden precalcular.
  - **Latencia** - Las entradas se ordenan por ID de usuario / Dirección IP / Fecha / Application.Two Los factores que podrían aumentar el tiempo de latencia son los problemas de conectividad a Internet o un cortafuegos antivirus.
- **(5)** **Acceso por período del proyecto** - Utilice esta tabla para ver cuándo sus usuarios están utilizando sus informes por mes y período. Estos datos pueden ayudarle a comprender qué periodos de tiempo son los más utilizados por sus usuarios, de modo que pueda pausar los cálculos en los periodos de tiempo menos frecuentes.

## Informes de asignación de casos de uso

A partir de TBM Studio 12.8, dos nuevos informes (Report to Use Case Mapping y User to Persona Mapping) permiten seguir y analizar el uso de los informes en función del caso de uso. Con estos informes, puede comprender qué casos de uso son más importantes para sus usuarios y qué casos de uso no son tan eficaces. Esta información puede ayudar a impulsar conversaciones sobre las áreas de la organización que podrían requerir atención. Los nuevos informes permiten hacer un seguimiento de la siguiente información:

- Seguimiento de los inicios de sesión en función del uso
- Seguimiento de los inicios de sesión en función de la persona de los usuarios finales
- Determine qué casos de uso son de gran impacto para su organización
- Asignar al seguimiento tanto los informes predefinidos como los personalizados

Utilice las siguientes instrucciones para configurar los casos de uso y las personas para que pueda verlos en los nuevos informes de uso de Apptio. Sus casos de uso no tienen por qué ajustarse a los casos de uso de Apptio Value Explorer (AVE).

## Tabla de asignación de informes a casos de uso

1. Extraiga la tabla Report to Use Case Mapping de TBM Studio y rellene las siguientes columnas para cada informe:
   - **Nombre del informe** - Nombre del informe predefinido o personalizado
   - **Caso de** uso - El caso de uso que desea desplegar para alinearlo con el Nombre del informe![mapeo de casos de uso](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/use_case_mapping_columns_sui.png)
2. Vuelva a cargar la tabla rellenada en la tabla de asignación de informe a caso de uso.

   ![tabla de asignación de casos de uso](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/use_case_mapping2_sui.png)

El informe **Uso del informe por caso de uso** ahora se rellena con datos de casos de uso.

## Tabla de asignación de usuario a Persona

La tabla de asignación de usuario a persona asigna cada usuario a su persona dentro de la organización para que pueda realizar un seguimiento de las personas que acceden a cada caso de uso.

1. Extraiga la tabla de TBM Studio y rellene un ID de usuario, un rol y una persona para cada usuario.

   ![uso de la cartografía de personas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/use_case_mapping4_sui.png)

   - **ID de usuario** - Dirección de correo electrónico del usuario (su nombre de usuario en Enhanced
     Access Administration )
   - **Rol** - El rol del usuario en Enhanced Access
     Administration (Admin, Business User, etc.)
   - **Persona** - La persona del usuario final (TBMA, Finanzas de TI, Propietario de la Aplicación, Propietario de la Infraestructura de TI, Propietario del Servicio, etc.)
2. Vuelve a cargar la tabla rellenada en la tabla **User to Persona Mapping**.

   ![asignación de usuario a persona](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/use_case_mapping5_sui.png)

El informe **Uso de informes por caso de uso** ahora permite filtrar por personas para que pueda ver qué persona accede a cada informe.

**Tema principal:** [Conceptos básicos de los informes](../../studio/new-uc/howtoguides/create-reports/report-basic.html)
