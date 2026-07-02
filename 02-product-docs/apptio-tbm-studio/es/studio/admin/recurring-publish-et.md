---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Publicación recurrente de la tabla de transformación"
breadcrumb: []
source_path: "studio/admin/recurring-publish-et.html"
images:
  - "resources/images/studio_images/12118-recsched.png"
  - "resources/images/studio_images/12118-transformtable.png"
  - "resources/images/studio_images/ap-1.jpg"
  - "resources/images/studio_images/ap-2.jpg"
  - "resources/images/studio_images/ap1.jpg"
  - "resources/images/studio_images/auto-promote-1.jpg"
  - "resources/images/studio_images/ef-recpub.jpg"
  - "resources/images/studio_images/en-feat.png"
  - "resources/images/studio_images/erp-1.png"
  - "resources/images/studio_images/rec-pub.png"
  - "resources/images/studio_images/rp-1.png"
  - "resources/images/studio_images/rp-main.png"
  - "resources/images/studio_images/rp-warning.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Publicación recurrente de la tabla de transformación

**Se aplica a** : 12.11.7 y posteriores. La opción Publicación recurrente permite a la TBMA programar calendarios de publicación recurrentes automáticos para tablas editables que tienen tablas de transformación. Una vez activada esta función, la opción 'Publicar en periodo' se convierte en programación por defecto, y se adjuntará en el pipeline de **Tabla Editable**, bajo **Transformar Tabla**. Todos los "Publicar en periodo" se convertirán en programación predeterminada en la página Programación periódica, y la transformación vinculada a la programación estará disponible en la página **Tabla de transformación**.

## Activar la publicación periódica de tablas de transformación

Nota: Antes de habilitar la función, debe establecer el Calendario Recurrente en Opciones de Promoción, de lo contrario el 'Publicar' en la superficie de informes siempre publicará en el período actual.

Para activar esta opción en 12.11.7, vaya a la pestaña **Proyecto** > **Activar funciones** y, a continuación, seleccione la opción **Activar publicación recurrente para tablas de transformación**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/en-feat.png)

Aparece un mensaje de confirmación como el que se muestra.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-warning.png)

La pestaña Publicación periódica está activada en la pestaña TBM Studio > Builds.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rec-pub.png)

Nota: Si la opción **Publicación recurrente** está activada, el botón **Opciones de promoción** > **Actualizaciones recurrentes para tablas editables** estará desactivado.

En la pestaña Construir, seleccione la opción **Publicación periódica**. Aparece la página Publicación periódica con dos pestañas.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-main.png)

## Tabla de transformación

Se trata de una página de sólo lectura que enumera todas las tablas de transformación procedentes de una tabla editable.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/12118-transformtable.png)

Contiene la siguiente información:

| Campos | Descripción |
| --- | --- |
| Nombre de tabla | Nombre de la tabla de transformación. |
| Carpeta | Ubicación de la tabla de transformación. |
| Tabla editable | Nombre de la tabla editable. En 12.11.8, el valor es un hipervínculo, al hacer clic en él se abrirá la tabla editable vinculada. |
| Nombre de planificación | Nombre dado al crear la programación periódica. |
| Recurrencia | El tipo de recurrencia: horaria, diaria, semanal o mensual. |
| Publicar en Período | El periodo de publicación seleccionado al crear el calendario recurrente - los valores son Primer periodo del año fiscal actual, Primer periodo del próximo año fiscal, Primer periodo del proyecto, mes actual, mes anterior, periodo específico y sin actualización recurrente. |
| Habilitada | Si se ha activado o no la programación periódica - los valores son Sí o No. |
| Fecha y hora de la última publicación | La fecha y hora de la última publicación en formato <mon dd, aaaa> <hh:mm> <AM/PM>< timezone>.  Si no se elige un programa recurrente, el valor en NA  Si la programación periódica aún no ha comenzado, el valor es Inicial. |
| Fecha y hora de la próxima publicación | La fecha y hora de la próxima publicación en formato <mon dd, aaaa> <hh:mm> <AM/PM>< timezone>.  Si no se elige un programa recurrente, el valor en NA  Si la programación periódica aún no ha comenzado, el valor es Inicial. |

## Programas recurrentes

Esta página contiene la lista de todos los horarios predeterminados y disponibles.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rp-1.png)

Permite a la TBMA añadir, eliminar o editar horarios. No se permitirá añadir horarios duplicados.

## Añadir un horario

En la pestaña Programaciones periódicas, seleccione **Añadir programación**. La ventana emergente Actualizaciones periódicas para tablas editables aparece como se muestra:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/auto-promote-1.jpg)

Introduzca los datos en los siguientes campos

| Campos | Descripción |
| --- | --- |
| Nombre | Introduzca un nombre para el programa de publicación periódica |
| Período de publicación | Seleccione uno de los valores del desplegable  Primer período del ejercicio en curso (disponible en 12.11.8 )Primer período del ejercicio siguiente (disponible en 12.11.8 )  Primer periodo del proyecto (disponible en 12.11.8 )  Período actual - tal cual  Período anterior - tal cual  Periodo específico - tal cual, posibilidad de seleccionar manualmente el periodo deseado |
| Recurrencia | **Repetir** : Seleccione Cada hora (por defecto), Diario, Semanal o Mensual **cada** <frecuencia de repeticiones> hora/días/mes.  **Hora de inicio** : Introduzca el <hh:mm> <AM/PM> y seleccione **UTC/GMT** <zona horaria> |
| Añadir nueva Hora de inicio | Este botón aparece para la recurrencia Diaria, Semanal y Mensual.  Haga clic en el botón para añadir los valores de **Repetición** y **Hora de inicio** mencionados anteriormente. Puede pulsar este botón 23 veces (para repetir la hora de inicio para cada hora) después de lo cual el botón se desactivará.  Haga clic en el icono x para borrar cualquier hora de inicio |
| Repetir en | Este campo aparece para la recurrencia **Semanal**. Seleccione los días en los que desea que funcione la repetición. |
| Habilitar | Seleccione esta casilla para activar, desactivar o suspender temporalmente la programación. |
| Ascenso automático a producción | Se aplica a 12.11.10 y posteriores. Seleccione esta casilla de verificación para promover automáticamente la programación periódica a producción. |

Seleccione **Guardar**. Aparecerá un mensaje de confirmación y el horario se añadirá a la lista.

- por defecto" es el valor inicial generado por el sistema que aparece cuando se activa la función.
- La planificación "Predeterminada - Sin actualización periódica" no tiene ninguna actualización periódica y no puede editarse ni eliminarse.
- Todas las programaciones de esta página aparecerán en el paso Editable Table pipeline de Transform Table.

## Edición de horarios

El TBMA puede editar o borrar el horario seleccionando el icono correspondiente. Al seleccionar **Guardar**, aparece un mensaje de confirmación como "*Se guarda la nueva programación para las actualizaciones de tablas editables. Puede que haya pocos Transforms registrados. Por favor, regístrese en Transforms.*"

Nota: Los calendarios predeterminados se establecen utilizando las configuraciones heredadas que se encuentran en "Opciones de promoción > Actualizaciones periódicas para tablas editables" y "Publicar en período" del origen de las tablas de transformación en tablas editables.

## Migración de configuraciones existentes a nuevas publicaciones recurrentes

Siga los pasos mencionados si desea activar la función para migrar configuraciones existentes.

Nota: Antes de activar la función de publicación periódica, asegúrese de que todas las transformaciones de las tablas editables están activadas o de lo contrario se revertirán los cambios. No proceda si las tablas de transformación están verificadas.

1. En la pestaña **Proyecto**, seleccione **Activar funciones** y, a continuación, active la casilla de verificación **Activar publicación periódica para tabla de transformación**.

   Si hay varias mesas, espere de 10 a 15 minutos mientras el sistema comprueba y modifica cada transformación
2. Expanda la sección **Tablas** en el Explorador de proyectos, filtre por **Usar** > **Editable** para ver que todas las tablas de transformación se han comprobado
3. En la pestaña **Crear**, seleccione la función **Publicación periódica**.
4. Seleccione la pestaña **Transformar tabla** para comprobar que las tablas aparecen en la lista.
5. Seleccione la pestaña **Programación periódica** para ver las programaciones "por defecto" que se basan en la configuración existente.
6. Cree nuevas programaciones, según lo desee, basadas en sus casos de uso de tablas editables exclusivas.
7. Cambie cada tabla de transformación del horario anterior "por defecto" a un nuevo horario, si lo desea.

Si activa la función de publicación periódica, sólo se migrará un proyecto cada vez. Si hay más de un proyecto con tablas editables, estos pasos deben repetirse para cada proyecto. Es importante específicamente, deseleccionar y luego volver a seleccionar la opción **Habilitar publicación periódica para la tabla Transformar** en Habilitar funciones

## 12.11.8 y más tarde

Las siguientes mejoras son aplicables a partir de 12.11.8.

- Active esta función desde la **Configuración del proyecto** y, a continuación, seleccione la casilla de verificación **Activar publicación periódica**.

  Nota: Si está migrando de la versión 12.11.7 a 12.11.8, debe activar manualmente esta función desde la pantalla Configuración del proyecto, ya que no estará activada por defecto. No habrá pérdida de configuración; los calendarios y las transformaciones permanecerán intactos y visibles tras la activación.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/erp-1.png)
- Se añaden tres opciones más a "Publicar en período", a saber, "Primer período del ejercicio en curso", "Primer período del ejercicio siguiente" y "Primer período del proyecto".
  - Primer Período del Año Fiscal Actual: Este es el Mes de Inicio del Año Fiscal establecido en la pantalla de Ajuste de Tiempo del Proyecto asociado con el año actual. Ejemplo: Si el Mes de Inicio del Ejercicio Fiscal es Marzo, entonces el Primer Período del Ejercicio Fiscal Actual sería Mar:FY2024.
  - Primer Período del Próximo Año Fiscal : Es igual que el Primer Período del Año Fiscal Actual, excepto que el año cambiará. Ejemplo: Mar:FY2025.
  - Primer Periodo del Proyecto: 'Inicio del Proyecto' establecido en la pantalla de Configuración del Tiempo del Proyecto será el valor para el Primer Periodo del Proyecto. Ejemplo: Si el ajuste es Abr FY2024, entonces el Primer Periodo del Proyecto debe ser Apr:FY2024.
- Se añaden dos nuevas columnas a la pantalla de programación periódica: "Ejecutar ahora" y "Descripción"
- La función "Ejecutar ahora" permite a los administradores ejecutar programas instantáneamente en lugar de esperar a la hora programada.
- La columna "Descripción" le permite añadir descripciones significativas para cada horario.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/12118-recsched.png)

## 12.11.10 y más tarde

Se añade una nueva columna Promover automáticamente a producción a la pestaña Programación periódica. Para ver esta columna, haga lo siguiente:

1. Navegue hasta **Habilitar funciones** y seleccione la opción **Habilitar promoción automática para programaciones periódicas de tablas editables**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ef-recpub.jpg)
2. La casilla de verificación **Promover automáticamente a producción** aparece en la ventana emergente Actualizaciones periódicas para tabla editable.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap-1.jpg)
3. Al seleccionar esta casilla, aparece un mensaje de advertencia. Aparecerá el cuadro de texto **Destinatarios de correo electrónico**, para añadir los identificadores de correo electrónico de las personas a las que desea notificar la promoción automática.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap1.jpg)

   Nota: Si la casilla de verificación no está seleccionada, el valor de Promover automáticamente a producción en la pestaña Programaciones periódicas será No.
4. La columna **Promover automáticamente a producción** también aparece en la pestaña Programaciones periódicas.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ap-2.jpg)
