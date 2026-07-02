---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Detección de anomalías"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/identify-unusual-spending-patterns-with-anomaly-detection.html"
images:
  - "images/Anomlay_ThirdParty_Jira_SNOW.png"
  - "images/anomaly-detection-new1.png"
  - "images/anomaly-detection-new2.png"
  - "images/anomaly-detection-new3.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Detección de anomalías

La detección de anomalías en Cloudability ayuda a las organizaciones a identificar patrones inusuales o inesperados en el gasto de costes. Esta función independiente de la nube proporciona un análisis exhaustivo de todos los servicios para detectar anomalías en los costes, lo que permite a los usuarios mitigar los picos repentinos de facturación mediante alertas oportunas. Los usuarios pueden supervisar las anomalías directamente en Cloudability o recibir notificaciones por correo electrónico y Pager Duty.

**Principales prestaciones**

- Detecte anomalías en los datos de costes de sus entornos de nube

- Configuración de alertas mediante umbrales absolutos (moneda) y porcentuales

- Explore los detalles de las anomalías y exporte o cree tickets (Jira, ServiceNow )

- Cree tickets en Jira o ServiceNow directamente desde dentro Cloudability

- Acceso programático a las anomalías a través de la API REST

## **Cómo funciona la detección de anomalías**

Formación de segmentos de costes

La formación de segmentos de costes es el proceso de desglosar los costes totales de la nube en segmentos más pequeños basados en el tipo de servicio, la cuenta, la categoría de uso y las etiquetas y asignaciones empresariales más relevantes. Esto ayuda al sistema a identificar patrones de costes únicos y a detectar anomalías con mayor precisión.

Existen dos tipos de segmentos de costes:

**Segmento de costes por nivel de servicio** y **segmento de costes configurable**

La formación del segmento de costes a nivel de servicio se calcula **utilizando los costes totales por fecha, nombre del servicio y familia de uso.**

.![captura de pantalla de detección de anomalías](../../../../03-media/cloudability-premium/images/anomaly-detection-new2.png)

*Las etiquetas y las dimensiones de asignación no se utilizan para el cálculo, por lo que la página **«Detalles»** no muestra las etiquetas ni las dimensiones de negocio.*

**El «segmento de costes configurable»** se calcula a partir de los costes totales agregados por **fecha, nombre del servicio, familia de uso, cuenta** y hasta **4 etiquetas y dimensiones de «Business Mapping»** seleccionadas por el administrador de Cloudability.

A continuación se muestra un ejemplo en el que hemos definido las etiquetas y se elige el algoritmo Business Mapping para identificar las anomalías.

![detalles de detección de anomalías scre](../../../../03-media/cloudability-premium/images/anomaly-detection-new1.png)**Las etiquetas y las dimensiones de asignación se utilizan para el cálculo, por lo que en la página **«Detalles»** se muestran las etiquetas y las dimensiones de negocio.**

Nota:

- Solo los administradores de « Cloudability » pueden seleccionar hasta un total de **4 dimensiones** entre las dimensiones de «Etiquetas» y «Asignación empresarial».
- Estas dimensiones seleccionadas se utilizan para crear segmentos de costes con el fin de detectar anomalías.

**Selección de dimensiones de etiquetas y mapas empresariales**

**Pasos**

1. Accede a la página **«Anomalías»** en IBM Cloudability.
2. Haz clic en **«Configuración de anomalías»** en la barra de acciones superior.
   - Esto abre el panel «**Ajustar la detección de anomalías** ».
3. Selecciona una **etiqueta** o una dimensión **de asignación empresarial** en el menú desplegable y haz clic en «**Añadir** ».
   - Repite este paso para añadir hasta **4 dimensiones de «Etiquetas» y/o «Asignación empresarial** ».
4. Haz clic en **«Guardar»** para aplicar la configuración.
   - Los cambios pueden tardar hasta **24 horas** en surtir efecto.

## Configurar una alerta

Para configurar una alerta, primero defina e identifique la situación que desea supervisar.

En la ventana de alerta, los usuarios deben rellenar dos secciones:

1. **Seleccionar una** vista - Especifique la vista para la que desea recibir una alerta.
2. **Establecer un umbral** : elige un valor de umbral, ya sea como cifra absoluta **o** como porcentaje.

**¿Qué es una vista en Cloudability?**

A **View** en Cloudability es una potente herramienta de filtrado de datos que ayuda a las organizaciones a personalizar y controlar cómo se muestra y comparte la información sobre el gasto y el uso de la nube. Las vistas permiten crear filtros para los datos de toda la aplicación y asignarlos a distintos usuarios en función de las necesidades de la organización.

Para obtener más información, consulta [la sección «Configuración de vistas» en Cloudability.](../admin/create-and-manage-views.html)

Una vez configurada la vista, cree una alerta en la sección Detección de anomalías de Cloudabilty. Considere el siguiente ejemplo.

Un usuario desea supervisar el gasto de su cuenta en la nube utilizando Cloudability. Configuran una alerta para una Vista seleccionada con los siguientes umbrales:

- Umbral de valor absoluto: 50.000 $
- Umbral porcentual: 20% de porcentaje inusual (calculado a partir de los gastos previstos).
- **Fórmula para el porcentaje inusual:**

  Porcentaje inusual
  =

  Gasto inusual
  Gasto previsto
  \text {Unusual Percentage} = \frac {\text{Unusual Spend}} {\text{Expected Spend}}
- Donde:Gasto previsto=Coste total−Gasto inusual\text {Expected Spend} = \text {Total Cost} - \text {Unusual Spend}![detección de anomalías scre](../../../../03-media/cloudability-premium/images/anomaly-detection-new3.png)

Consideremos ahora los escenarios:

Hipótesis 1 : **Activación del umbral de gastos excepcionales**

**Escenario 2: Umbral porcentual inusual activado**

Si los **gastos previstos** ascienden a **40.000 dólares** y el **umbral de alerta** se fija en **un porcentaje inusual del 20%**, según la fórmula Porcentaje inusual, si los **gastos inusuales** ascienden a **8.000 dólares o más**, se activará la alerta.

Esto se debe a que:Porcentaje inusual=8,00040,000=20%\text {Unusual Percentage} = \frac {8,000}{40,000} = 20\%

También tiene la posibilidad de elegir uno de los valores umbral o ambos.

Acceso a los detalles de la anomalía

Para explorar una anomalía con más detalle, haga clic en el botón Ver informe de la página de detalles. Se abrirá la interfaz de informes, donde podrá añadir dimensiones adicionales o ajustar el intervalo de fechas para un análisis más profundo.

Para acceder a los detalles de la anomalía, siga los pasos que se indican a continuación.

1. Vaya a Insights > Detección de anomalías.
2. En la página Anomalías de gasto, haga clic en Detalles.
3. Seleccione Ver informe para añadir más dimensiones para el análisis.
4. Utilice la opción Editar para modificar el periodo de tiempo o el intervalo de fechas de una vista personalizada.

Esto proporciona una investigación exhaustiva de las anomalías en los costes, ayudándole a comprender mejor los patrones de gasto inusuales.

## Creación de tickets Jira o ServiceNow para anomalías

Puede crear tickets en sus herramientas de gestión de servicios de TI (ITSM) como **Jira Cloud** y **ServiceNow** directamente desde para cada **anomalía** mostrada en la página Anomalía. Esto le permite iniciar investigaciones sobre anomalías identificadas sin salir de Cloudability. Ambas integraciones incluyen sincronización bidireccional para mantener actualizado el estado de los tickets tanto en Cloudability como en su plataforma ITSM.

**Antes de empezar**

**Integración con Jira**

- Configurar Jira Cloud en Cloudability.
- Más información sobre [la integración con Jira: configuración](../admin/connect-jira-cloud.html)

**ServiceNow integración**

Más información sobre [la integración de « ServiceNow »: configuración](../admin/connect-servicenow-integration.html)

**Crear un billete**

Una vez configurada la integración:

1. Navegue hasta las **Anomalías** en la página de Anomalías.
2. En el **menú de tres puntos (⋮** ) de cualquier anomalía, elija una de las siguientes opciones:

![](../../../../03-media/cloudability-premium/images/Anomlay_ThirdParty_Jira_SNOW.png)

Al hacer clic en **Crear incidencia de Jira Cloud** o **Crear incidencia de ServiceNow** se abre un cuadro de diálogo para crear la incidencia.

Nota:

Si las credenciales de Jira Cloud o ServiceNow no se han configurado para su organización, las opciones de creación de tickets estarán desactivadas.

## Alertas de anomalías para múltiples usuarios

Cloudability Permite compartir suscripciones a alertas de anomalías con otros usuarios. Esta función permite a los equipos recibir notificaciones de anomalías sin necesidad de que cada usuario configure las alertas de forma individual. Los administradores con permiso para compartir pueden compartir suscripciones a alertas con otros usuarios, lo que reduce la duplicación de esfuerzos, mantiene criterios de alerta coherentes y simplifica la incorporación de nuevos usuarios.

Una vez creadas las alertas, los usuarios pueden ver todas las alertas en la pestaña Configuración de alertas. Esta página muestra todas las suscripciones a alertas, incluidas las creadas por el usuario y las compartidas con él. La vista de configuración también identifica al creador de cada alerta.

## Alertas de ignorar anomalías

Cloudability ahora admite la funcionalidad Ignorar alerta de anomalía. Esta función permite a los usuarios ignorar temporalmente las alertas de anomalías directamente desde la página de Configuración de alertas. Ayuda a reducir el ruido durante los eventos de costos esperados y garantiza que solo aparezcan alertas significativas y procesables.

Principales características

1. Ignorar alertas en el nivel de alerta de anomalía individual
2. Admite la función de ignorar alertas compartidas
3. Seleccione la duración de ignoración preestablecida (7, 14 o 30 días)
4. Defina un rango de fechas personalizado para ignorar las alertas.
5. Editar la duración de ignorar (ampliar o acortar según sea necesario)
6. Programar ignorar para un período de tiempo futuro
7. Ignorar alertas de forma masiva utilizando la opción Ignorar alertas de anomalías masivas
8. Reanudar automáticamente las alertas una vez que finalice el período de ignorar

Esta funcionalidad proporciona un mayor control sobre las notificaciones de anomalías y ayuda a los equipos a centrarse en eventos de costos relevantes y procesables.

## Preguntas más frecuentes

1. ¿Con qué frecuencia se detectan las anomalías?

   Las anomalías se detectan cada 24 horas, una vez que se actualizan los datos de costes. Nuestro objetivo es emitir alertas a tiempo y reducir al mínimo las notificaciones innecesarias. Cada vez que se ejecuta el algoritmo de detección de anomalías, éste reevalúa y regenera las anomalías de los últimos siete días.
2. ¿Por qué cambian/desaparecen las anomalías?

   Cada vez que se ejecuta el algoritmo de detección de anomalías, regenera las anomalías de los últimos siete días. Dentro de esta ventana de siete días, el modelo se vuelve más informado, lo que hace posible que las anomalías cambien o desaparezcan.
   - Si el importe de una anomalía determinada cambia, se debe principalmente a la actualización de los datos sobre costes.
   - Si desaparece una anomalía, se debe principalmente a que las cinco etiquetas/dimensiones seleccionadas diariamente difieren, lo que provoca que se sobrescriba la anomalía anterior.
3. ¿Muestra la detección de anomalías un gasto a la baja?

   No, la detección de anomalías sólo muestra gastos inusuales al alza.
4. ¿Podemos cambiar la forma en que se detectan las anomalías?

   Las fórmulas que detectan una anomalía no pueden modificarse, pero los clientes sí pueden cambiar el umbral de las notificaciones que reciben.
5. ¿Puede un reprocesamiento desencadenar nuevas anomalías o alertas?

   Sí, las anomalías pueden aparecer o desaparecer a medida que se reciben nuevos datos de facturación o se actualizan las asignaciones de etiquetas y las asignaciones comerciales.
6. ¿Por qué se me avisó de una anomalía, pero ya no es visible en la interfaz de usuario?

   Cloudability identifica anomalías basándose en los últimos datos de facturación disponibles. Cuando se detecta una anomalía, se envía una alerta para notificárselo al usuario. Sin embargo, los proveedores de servicios en nube (PSC) actualizan continuamente los archivos de facturación, lo que puede provocar cambios en los costes declarados.

   Si las actualizaciones posteriores de la facturación modifican el gasto total de un día determinado, es posible que el algoritmo de detección de anomalías deje de clasificar el gasto de ese día como inusual. Como resultado, la anomalía detectada anteriormente se elimina de la interfaz de usuario.

   Ejemplo: Si un proveedor aplica un ajuste de crédito, reduciendo el gasto total para un día específico, la anomalía previamente marcada ya no se considerará inusual y ya no aparecerá en la interfaz de usuario.
7. ¿Cuáles son los escenarios en los que el usuario no recibirá la alerta?

   - La anomalía informa de un gasto inusual de 300 $, pero el cliente ha establecido un umbral de 350 $. En este caso, no se enviará ninguna alerta.
   - Un usuario establece una suscripción con una Vista específica, pero sus permisos cambian y ya no tiene acceso a esa Vista. En consecuencia, no se enviará ninguna alerta.
   - Una Vista está configurada para activar alertas cuando aparece la etiqueta "team=cldy". Si falta la etiqueta o está configurada como "team=apptio", el Alerter no enviará una alerta.
   - Ya se ha informado de una anomalía con la misma fecha, gasto total, gasto inusual, cuenta, etiquetas y asignaciones comerciales para un usuario en particular. Si se vuelve a recibir una anomalía idéntica, no se enviará otra alerta.

   Las anomalías se detectan cada 24 horas, una vez que se actualizan los datos de costes. Nuestro objetivo es emitir alertas a tiempo y reducir al mínimo las notificaciones innecesarias. Cada vez que se ejecuta el algoritmo de detección de anomalías, éste reevalúa y regenera las anomalías de los últimos siete días.
8. ¿Puedo personalizar la detección de anomalías?

   Sí. La detección de anomalías se puede personalizar seleccionando las dimensiones que se deseen supervisar a través de «**Dimensiones configurables** ». Esto te permite detectar anomalías con el nivel de detalle que mejor se adapte a las necesidades de tu organización.
9. **¿Qué ocurre cuando se detecta una anomalía tanto en el nivel de servicio como en el segmento de costes configurable?**

   Cuando se detecta una anomalía para el mismo servicio (ID de cuenta, familia de uso, nombre del servicio) y las mismas dimensiones configurables, puede darse una de las siguientes situaciones:

   **Solo se notifica la anomalía «Configurable»**

   - Si la anomalía se debe a una única combinación de «Dimensiones configurables» y el importe del gasto anómalo a nivel de «Servicio» es idéntico al importe del gasto a nivel de «Dimensiones configurables», solo se notificará la anomalía relacionada con las «Dimensiones configurables».
   - Esto ayuda a evitar que se notifique dos veces la misma anomalía.

   **Se han notificado ambas anomalías**

   - Si el importe de gasto anómalo a nivel de servicio difiere del importe de gasto a nivel de dimensiones configurables, se notifican ambas anomalías.
   - Esto indica que la anomalía en el nivel de servicio no se explica por completo mediante una única combinación de dimensiones configurables.
