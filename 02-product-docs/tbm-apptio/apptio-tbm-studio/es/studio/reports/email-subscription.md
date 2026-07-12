---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Suscripción por correo electrónico"
breadcrumb: []
source_path: "studio/reports/email-subscription.html"
images:
  - "resources/images/studio_images/ESsearch.png"
  - "resources/images/studio_images/bu-1.png"
  - "resources/images/studio_images/bu-2.png"
  - "resources/images/studio_images/bu-3.png"
  - "resources/images/studio_images/bu_toggle.png"
  - "resources/images/studio_images/ds-1.jpg"
  - "resources/images/studio_images/ds-2.jpg"
  - "resources/images/studio_images/ds-3.jpg"
  - "resources/images/studio_images/ds-5.jpg"
  - "resources/images/studio_images/ds2.jpg"
  - "resources/images/studio_images/ds3.jpg"
  - "resources/images/studio_images/ds4.jpg"
  - "resources/images/studio_images/ds5.jpg"
  - "resources/images/studio_images/ds6.jpg"
  - "resources/images/studio_images/ds7.jpg"
  - "resources/images/studio_images/ds8.jpg"
  - "resources/images/studio_images/em-sub-1.jpg"
  - "resources/images/studio_images/email-full.jpg"
  - "resources/images/studio_images/endisES.png"
  - "resources/images/studio_images/es-1.jpg"
  - "resources/images/studio_images/filter-view.jpg"
  - "resources/images/studio_images/ms-1.jpg"
  - "resources/images/studio_images/ms-2.jpg"
  - "resources/images/studio_images/ms-3.jpg"
  - "resources/images/studio_images/pdf-10.jpg"
  - "resources/images/studio_images/pdf-11.jpg"
  - "resources/images/studio_images/pdf-2.jpg"
  - "resources/images/studio_images/pdf-3.jpg"
  - "resources/images/studio_images/pdf-4.jpg"
  - "resources/images/studio_images/pdf-5.jpg"
  - "resources/images/studio_images/pdf-6.jpg"
  - "resources/images/studio_images/pdf-8.jpg"
  - "resources/images/studio_images/pdf-9.jpg"
  - "resources/images/studio_images/pdf-name.jpg"
  - "resources/images/studio_images/pdf1.jpg"
  - "resources/images/studio_images/pf-7.jpg"
  - "resources/images/studio_images/r-notes/dup-sub1.jpg"
  - "resources/images/studio_images/send-now-1.jpg"
  - "resources/images/studio_images/send-now.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Suscripción por correo electrónico

Esta función permite a los TBMA suscribirse periódicamente a informes por correo electrónico. También pueden incluir a otros usuarios en estas suscripciones a informes, que recibirán una notificación al respecto.

Las suscripciones por correo electrónico también pueden ser creadas por usuarios con los siguientes permisos:

- EmailSubscriptionsCreate
- EmailSubscriptionsFilteredCreate

Nota:

- Por razones de seguridad, un correo electrónico sólo puede enviarse a los dominios autorizados en el entorno del cliente. Por ejemplo, para el cliente acme, añadir un correo electrónico para jdoe@acme.com funcionaría, pero añadir un correo electrónico para jdoe@xyz.com no funcionará.
- RLS (Row Level Security) no es compatible con las suscripciones de correo electrónico

## Crear suscripción por correo electrónico

Vaya a cualquier informe, expanda el icono **Exportar** y seleccione **Suscripción por correo electrónico**. Esta opción sólo aparecerá para los TBMA.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/es-1.jpg)

Aparecerá la ventana emergente Suscripciones de correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/em-sub-1.jpg)

Introduzca valores en los siguientes campos. El \* indica un campo obligatorio.

| Campo | Descripción |
| --- | --- |
| Recopilación de informes\* | El valor se rellena automáticamente con el nombre de la colección de informes que el informe que está viendo.  Puede cambiar el valor seleccionándolo en la lista desplegable. |
| Nombre del informe | El valor se rellena automáticamente con el nombre del informe que está visualizando.  Puede cambiar el valor seleccionándolo en la lista desplegable. |
| Nombre de la suscripción | El nombre se rellena automáticamente como <Colección de informes - Nombre del informe>. Puede editar este nombre o introducir uno nuevo. |
| Definir el cuerpo del correo electrónico | En 12.11.9, seleccione esta opción para cambiar el asunto y la descripción del correo electrónico que se envía al abonado. Puede introducir un máximo de 3000 caracteres en el cuerpo del correo electrónico. |
| Incluir PDF en archivo adjunto | En 12.11.9, seleccione esta opción para ver una versión en PDF del informe adjunto en el correo electrónico. |
| Carga masiva XLS | Seleccione esta opción si desea enviar suscripciones masivas por correo electrónico con filtros. Si esta opción está activada, el campo **Destinatarios** estará desactivado. |
| Beneficiarios | Introduzca el identificador de correo electrónico de las personas que deben recibir las suscripciones por correo electrónico.  Desde 12.11.8, es posible introducir manualmente una dirección de correo electrónico válida de uno de los dominios admitidos. |
| Período de referencia | El informe se generará en función de este periodo de tiempo. Seleccione una de las opciones:  **Período actual**  Si no se selecciona **Activar periodo de tiempo predeterminado**, ésta será la selección predeterminada.  Si esta opción está activada, el usuario recibirá un correo electrónico/pdf para el mes en curso.  **Período anterior**  Si esta opción está activada, el usuario recibirá un correo electrónico/pdf para el mes anterior,  Si el Periodo por defecto está activado en "Ajustes de tiempo del proyecto" --> Periodo anterior = Periodo por defecto - 1  Si el periodo por defecto está desactivado en "Ajustes de tiempo del proyecto" --> Periodo anterior = Periodo actual - 1  **Periodo predeterminado** (por defecto)- Esta opción sólo aparece si selecciona la opción **Activar periodo de tiempo predeterminado** en la pestaña **Proyecto** >� [Ajustes de tiempo](../admin/configure-project-time.htm "(se abre en una pestaña o una ventana nueva)").  Si este botón de opción está activado, el usuario recibirá un correo electrónico/pdf para el mes predeterminado que se haya establecido en la "Configuración de la hora del proyecto" |
| Con filtros | En 12.11.11, seleccione esta opción para suscribirse a informes filtrados por correo electrónico. |
| Frecuencia | Seleccione una de las opciones:  **Diario** (por defecto)  **Semanal** - Seleccione los días  **Mensual** - Esta es la selección por defecto. Seleccione la fecha  **Hora de envío** \*: Seleccione una hora en el desplegable. La zona horaria predeterminada es la actual.  **Día** \*: Seleccione el día del mes en el desplegable. |
| Fin de la suscripción | Seleccione una de las opciones:  **Nunca** (por defecto) o  **En una fecha** : introduzca o seleccione una fecha futura, en formato <dd-mm-aaaa>. |
| Gestionar suscripciones | Seleccione este enlace para ver, editar y eliminar las suscripciones de correo electrónico. |

Una vez introducidos los valores en todos los campos, seleccione el botón **Suscribir**. Un mensaje de confirmación " *¡Informe suscrito correctamente!* " aparece. La suscripción añadida aquí estará disponible en la ventana emergente Gestionar suscripciones.

Nota: No se permiten las suscripciones duplicadas. Una suscripción está duplicada si tiene el mismo nombre o si es para el mismo informe en el mismo horario.

## Gestionar suscripciones

En la ventana emergente Suscripción de correo electrónico, seleccione el enlace **Gestionar suscripciones**. Aparecerá la ventana emergente Gestionar suscripciones. Puede

- Ver, buscar o editar cualquiera de las suscripciones.
- El icono **Eliminar suscripción(es)** aparece en la versión 12.11.11 y posteriores.
- Utilice la opción de paginación para navegar por las suscripciones.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-1.jpg)

Seleccione la casilla **Ver por usuario** para ver las suscripciones por todos los usuarios que forman parte de las suscripciones.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-2.jpg)

Seleccione el enlace **Usuario** para ver la lista de informes a los que está suscrito.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ms-3.jpg)

## Activar/desactivar suscripciones de correo electrónico

Se aplica a: 12.11.14 y posteriores. Esta función permite a los administradores hacer lo siguiente:

- **Activación inmediata de suscripciones** : Dispare (habilite) las suscripciones inmediatamente después del Proceso de finalización mensual (MEP), garantizando actualizaciones y notificaciones puntuales.
- **Suscripción en pausa** : Evita la sobrecarga de correo electrónico pausando (desactivando) las suscripciones durante periodos específicos, lo que permite una mejor gestión del correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/endisES.png)

Al seleccionar la opción **Activar**, la fila de suscripción se desactiva y aparece el mensaje "*Su suscripción de correo electrónico se ha pausado. No recibirá más correos electrónicos hasta que se reanude*".

Al seleccionar la opción Desactivar, aparece un mensaje como "*Su suscripción de correo electrónico se ha reanudado. A partir de ahora, recibirá los correos electrónicos programados en*".

Nota: Los correos electrónicos no se enviarán para las suscripciones en pausa.

## Enviar ahora

**Se aplica a** : 12.11.12 y posteriores

La función Enviar ahora permite a los administradores una forma cómoda de verificar que la suscripción por correo electrónico funciona según lo previsto, garantizando que los suscriptores reciben el contenido esperado. Gracias a esta función, pueden probar con confianza sus suscripciones de correo electrónico, lo que facilita su gestión y mantenimiento.

Se puede acceder a la función Enviar ahora desde dos lugares:

En la ventana emergente **Gestionar suscripciones**, para cada suscripción de correo electrónico

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-now.jpg)

En la pantalla de edición de una suscripción individual de correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/send-now-1.jpg)

Antes de utilizar **Enviar ahora** en la pantalla de edición, debe guardar los cambios realizados en los detalles de la suscripción. Si se realizan cambios pero no se guardan, el botón **Enviar ahora** se desactivará hasta que se guarden los cambios. Una vez guardado, puede seleccionar **Enviar ahora** para enviar un correo electrónico de prueba a los suscriptores, lo que proporciona una forma rápida y sencilla de probar y verificar sus suscripciones de correo electrónico.

## Definir el cuerpo del correo electrónico

Seleccione esta opción para cambiar el asunto y la descripción del correo electrónico que se envía al abonado.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/email-full.jpg)

El asunto y el cuerpo del correo electrónico son personalizables. Desde 12.11.12, se pueden añadir variables dinámicas como el nombre del informe, el periodo del informe y los filtros. A continuación, estas variables se sustituyen por los valores reales de los correos electrónicos.

Cuando reciba la suscripción por correo electrónico, el

**El asunto del correo electrónico** aparece como *<Nombre del informe> MMM\_AAAA {filter1 condition = value}; {filter2 condition = value}; { ... }*

**El cuerpo del correo electrónico** aparece como

Su informe TBM Apptio suscrito está listo: informe <Nombre del informe> para el periodo de <MMM\_YYYY>

- Nombre e identificación del proyecto = XXXX

El **nombre del archivo PDF** o adjunto como *<Nombre\_del\_informe>\_MMM\_AAA*.pdf

El nombre del botón en el correo electrónico será **Ver informe completo en Apptio**.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-name.jpg)

## Opción PDF para informes sencillos

Los administradores pueden crear informes sencillos en PDF para las suscripciones por correo electrónico con una vista de impresión limpia. Siga las siguientes pantallas para el proceso.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-11.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-10.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-9.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-8.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pf-7.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-6.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-5.jpg)

Tenga en cuenta que:

Si existe una vista simple de un informe, el archivo PDF adjunto incluirá la vista simple del informe en la suscripción por correo electrónico.

Si no existe una vista simple de un informe, el archivo PDF adjunto incluirá la "vista de diseño de impresión" del informe en la suscripción por correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-4.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-3.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf-2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pdf1.jpg)

## Suscripciones por correo electrónico con vista filtrada

Esta función permite a los usuarios compartir informes filtrados con destinatarios específicos mediante un sistema de suscripción. El destinatario recibe un hiperenlace para acceder al informe con selecciones de corte preaplicadas, junto con la opción de recibir un documento PDF adjunto. El PDF puede configurarse para que incluya o excluya la Vista simple vinculada manteniendo la configuración de filtro seleccionada.

Vaya a la ventana emergente Suscripción por correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/filter-view.jpg)

Deslice el interruptor de **vistas filtradas**. Aparece el desplegable Filtrar por\*.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds3.jpg)

En 12.11.14, puede seleccionar un valor del menú desplegable o realizar una búsqueda parcial introduciendo la palabra clave.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ESsearch.png)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds4.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-5.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds5.jpg)

Introduzca los valores en el resto de los campos y seleccione el botón **Suscribir**. Un mensaje de confirmación " *¡Informe suscrito correctamente!* " aparece.

El destinatario recibirá un correo electrónico con el enlace al informe con las vistas filtradas.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds6.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds7.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds8.jpg)

## Suscripciones duplicadas

Esta función permite a los usuarios duplicar las suscripciones existentes y evitar crearlas desde cero. No puede duplicar varias suscripciones a la vez.

Seleccione el enlace **Gestionar suscripciones** en la ventana emergente Suscripción de correo electrónico.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-1.jpg)

Seleccione cualquier suscripción: en la parte superior derecha aparecerá el icono **Duplicar suscripción**. Este icono sólo aparece al seleccionar una única suscripción.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-2.jpg)

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/dup-sub1.jpg)

Al seleccionar el icono Duplicar suscripción, aparecerá una nueva ventana emergente con todos los campos rellenados para que coincidan con la suscripción original.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ds-3.jpg)

Realice los cambios oportunos y, a continuación, seleccione el botón **Suscribir**.

## Carga de tablas

La función de carga de tablas está diseñada para la distribución exclusiva de informes por correo electrónico a miles de destinatarios. Esta función permite que la suscripción a un único informe por correo electrónico incluya varias vistas de informes únicas y filtradas para cada destinatario (o un grupo de destinatarios).

En la ventana emergente Suscripción por correo electrónico, deslice el conmutador **Carga masiva XLS**.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu_toggle.png)

Aparece la opción para cargar la tabla y desaparecen los campos **Destinatarios** y **Con filtros**.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-2.png)

Puedes hacer una de las siguientes cosas:

- Arrastre y suelte o adjunte un archivo utilizando el enlace **Examinar ordenador**.
- Haga clic en el enlace **Plantilla en blanco** para descargar la plantilla, rellénela y, a continuación, cárguela utilizando el enlace **Examinar ordenador**. La tabla de plantillas se descargará en función de las columnas filtradas disponibles.

Si el tipo de archivo no es válido, aparecerá un mensaje de error apropiado. El botón **Suscribir** estará desactivado hasta que se cargue correctamente el archivo.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-1.png)

Cierre el mensaje y vuelva a cargar el archivo en el formato correcto. Aparecerá un mensaje que indica que la carga se ha realizado correctamente.

![img](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bu-3.png)

Después de cargar correctamente el archivo, se activa el enlace **Archivo de reglas de suscripción**, lo que indica que ya hay un archivo/datos disponibles.

Una vez introducidos todos los demás datos, haga clic en el botón **Suscribirse**. La tabla se valida para garantizar la integridad de los datos y la distribución precisa de los informes. Por ejemplo, la columna de destinatarios debe contener direcciones de correo electrónico válidas y no dejarse vacía. Además, los nombres de las columnas y sus respectivos tipos de datos deben alinearse correctamente: no debe introducirse una dirección de correo electrónico en una columna de datos de cadena y, del mismo modo, no deben introducirse datos de cadena en una columna que contenga valores numéricos o de fecha.
