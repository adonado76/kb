---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Bloquear y promover un proyecto"
breadcrumb: []
source_path: "studio/admin/lock-promote-project.html"
images:
  - "resources/images/studio_images/et-hour.png"
  - "resources/images/studio_images/fp-popup.png"
  - "resources/images/studio_images/fp-success.png"
  - "resources/images/studio_images/promote-later.png"
  - "resources/images/studio_images/promotion-options.png"
  - "resources/images/studio_images/recurring-promotion-popup.png"
  - "resources/images/studio_images/staging-lock.png"
  - "resources/images/studio_images/staging.png"
  - "resources/images/studio_images/studioimages/force-promotion.png"
  - "resources/images/studio_images/studioimages/locked_866x93.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Bloquear y promover un proyecto

**Se aplica a** : TBM Studio 12.0 y posteriores. Apptio TBM Studio admite dos modos, *a la carta* y *recurrente*, para las promociones.

## Promociones a la carta

Se trata de una modalidad básica en la que las TBMA promueven construcciones en función de las necesidades. Los TBMA del equipo no están obligados a coordinarse entre sí en esta modalidad. Los siguientes pasos muestran la secuencia de promoción de alto nivel que sigue la TBMA. Consulte [Gestionar promociones a la](#Lockandpromoteaproject__Manage) carta para obtener instrucciones detalladas.

1. TBMA valida la fase de construcción actual.
2. TBMA bloquea el proyecto.

   Nota: Un cálculo en curso puede desencadenar una nueva construcción. De lo contrario, no se activará ninguna nueva construcción.
3. El bloqueo impide nuevas entradas de otros TBMA mientras la construcción y posterior promoción están en curso.
4. TBMA promueve la construcción con una de las dos opciones siguientes (estas opciones sólo están disponibles si el proyecto está bloqueado):
   - Promocionar ahora
   - Promoción posterior

## Promociones recurrentes

Se trata de un modo avanzado. Este modo es apropiado para un equipo que cumpla los siguientes criterios:

- El equipo tiene un ritmo bien establecido de comprobaciones y validaciones según un calendario.
- El equipo quiere asegurarse de que los productos se actualizan con una cadencia conocida para su consumo.
- Los TBMA del equipo se coordinan entre ellos al respecto.

Los siguientes pasos muestran la secuencia de promoción recurrente de alto nivel que sigue la TBMA. Consulte [Gestionar promociones a la](#Lockandpromoteaproject__Manage) carta para obtener instrucciones detalladas.

1. El equipo configura el calendario de promociones.
2. El equipo se asegura de que el escenario se valide con suficiente antelación a la promoción programada.
3. La promoción tiene lugar a la hora prevista.

Si, durante el tiempo de promoción programada preconfigurado, el proyecto está bloqueado, la promoción programada fallará. En consecuencia, el bloqueo no puede utilizarse junto con promociones programadas.

## Gestionar promociones a la carta

- Cuando un proyecto está bloqueado, los usuarios pueden extraer documentos, pero no pueden introducirlos.
- Para que un proyecto pueda promocionarse del entorno de Escenificación al de Producción, el proyecto debe estar bloqueado.
- Sólo los usuarios con privilegios de administrador pueden promover un proyecto al entorno de producción.

  Nota: Cuando un proyecto está bloqueado, el desplegable Entorno de la cabecera global se establece en **Bloqueado**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/locked_866x93.png)

El bloqueo debe coordinarse para que se conozca lo que se promueve. En equipos pequeños, es más fácil hacer un seguimiento informal. Sin embargo, en equipos más grandes o en situaciones en las que se producen frecuentes registros con una variedad de cambios en diferentes documentos dentro del sistema, puede ser necesario coordinar para ayudar a garantizar que cuando se registra el conjunto específico de cambios destinados a la producción, se bloquea la compilación asociada.

Si el escenario está bloqueado, los usuarios no podrán registrarse. El mecanismo de bloqueo se proporciona para que los TBMA dispongan de una forma de bloquear cambios posteriores que puedan afectar a un evento de publicación.

## Bloquear o desbloquear un proyecto

1. Seleccione el entorno Staging.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/staging.png)
2. En la pestaña **Construir** seleccione **Bloquear** (o si ya estaba bloqueado, seleccione **Desbloquear** ).

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/staging-lock.png)

Después de bloquear un proyecto, puedes promocionarlo. Los botones **Promocionar ahora** y **Promocionar más tarde** se activarán y el botón **Forzar promoción** se desactivará.

## Promover un proyecto desde el entorno de Puesta en Escena al de Producción

Para promocionar un proyecto, vaya a la pestaña **Construir** y seleccione **Opciones de promoción**. Seleccione una de las siguientes opciones:

**Promocionar ahora**

Promueve inmediatamente el proyecto. Este botón se desactiva cuando la compilación está desbloqueada o cuando todavía se está ejecutando otra compilación.

**Promoción posterior**

Este botón se desactiva cuando la construcción está desbloqueada.

1. Aparece el cuadro de diálogo Promover más tarde.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/promote-later.png)
2. Seleccione **una** de las opciones:
   - Promover tan pronto como se complete la construcción, pero no después del tiempo especificado
   - Promover a la hora especificada si la construcción se ha completado
3. Introduzca la **fecha** y la **hora** para programar la promoción
4. Marque o desmarque la casilla de verificación **Desbloqueo automático tras una promoción exitosa**
5. Introduzca los identificadores de correo electrónico en el cuadro de texto **Destinatarios de correo electrónico**
6. Seleccione Guardar.

## Promoción de la fuerza

Se aplica a: 12.11.0 y posteriores. El botón **Forzar promoción** le permite promover la última compilación calculada para el proyecto a Producción, sin bloquear el entorno de ensayo. Para forzar la promoción de la compilación, haga lo siguiente:

1. Vaya a la pestaña **Construir** y asegúrese de que la construcción está desbloqueada.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/force-promotion.png)
2. Seleccione el botón **Forzar promoción**. Aparece una ventana emergente de advertencia:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fp-popup.png)
3. Seleccione **Ok** para completar la acción

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fp-success.png)

   .

## Gestionar promociones recurrentes

Nota: Como se describe en la Introducción, la configuración de una promoción recurrente es una función avanzada destinada a equipos maduros.

## Promoción recurrente

1. En la pestaña Entorno de montaje y compilación, seleccione Opciones de promoción.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/promotion-options.png)
2. Seleccione **Promoción recurrente**. Aparecerá el cuadro de diálogo Promoción periódica.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/recurring-promotion-popup.png)
3. Introduzca los datos en los siguientes campos

   | Campos | Descripción |
   | --- | --- |
   | Nombre | Nombre de la promoción recurrente |
   | Descripción | Descripción del motivo por el que se requiere la promoción recurrente |
   | Recurrencia | **Repetir** : Seleccione Diario, Semanal o Mensual cada <frecuencia de repeticiones> días  **Hora de inicio** : Introduzca el <hh:mm> <AM/PM> y seleccione **UTC/GMT** <zona horaria> |
   | Destinatarios de correo electrónico | Introduzca la dirección de correo electrónico de las personas que deben recibir las notificaciones |
   | Habilitar | Seleccione esta casilla para activar/desactivar las notificaciones por correo electrónico |
4. Seleccione **Guardar**

## Actualizaciones periódicas de tablas editables

1. En Opciones de promoción, seleccione **Actualizaciones periódicas para tablas editables**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-hour.png)
2. Introduzca los datos en los siguientes campos

   | Campos | Descripción |
   | --- | --- |
   | Recurrencia | **Repetir** : Seleccione Cada hora (por defecto), Diario, Semanal o Mensual cada <frecuencia de repeticiones> hora/días/mes.  **Hora de inicio** : Introduzca el <hh:mm> <AM/PM> y seleccione **UTC/GMT** <zona horaria> |
   | Añadir nueva Hora de inicio | Este botón aparece para la recurrencia Diaria, Semanal y Mensual.  Haga clic en el botón para añadir los valores de **Repetición** y **Hora de inicio** mencionados anteriormente. Puede pulsar este botón 23 veces (para repetir la hora de inicio para cada hora) después de lo cual el botón se desactivará.  Haga clic en el icono x para borrar cualquier hora de inicio |
   | Repetir en | Este campo aparece para la recurrencia **Semanal**. Seleccione los días en los que desea que funcione la repetición. |
   | Habilitar | Seleccione esta casilla para activar/desactivar las notificaciones por correo electrónico |
3. Seleccione **Guardar**.

## Escenarios y buenas prácticas

**Escenario** - El equipo tiene un ritmo diario de cambios menores, pero un TBMA, o conjunto de TBMAs, quiere realizar una actividad de configuración de larga duración.

**Buenas prácticas** - El equipo puede utilizar promociones de horarios en la sucursal principal. Se puede crear una rama separada para la configuración de larga duración, que utiliza promociones bajo demanda.

**Escenario** El equipo tiene un ritmo diario de cambios menores, pero cada mes se cargan nuevos datos en el sistema con un enlace de datos.

**Buenas prácticas**

- El equipo puede utilizar promociones de horarios en la sucursal principal.
- La carga de datos a través de Datalink (Classic) tiene lugar en una rama, se valida y, a continuación, se fusiona con la rama principal.

**Escenario** - El equipo tiene un ritmo de promoción establecido, pero debido a eventos específicos o alguna interrupción, el equipo necesita realizar una promoción puntual fuera de banda.

**Buenas prácticas**

- El equipo configura y utiliza una promoción programada.
- El equipo puede utilizar la promoción a la carta fuera de banda sin que la promoción programada entre en conflicto con la promoción a la carta. En caso de conflicto, se realiza la promoción a petición y se cancela la promoción programada.
