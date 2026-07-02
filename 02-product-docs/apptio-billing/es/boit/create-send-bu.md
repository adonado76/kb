---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Creación y envío de facturas de unidades de negocio"
breadcrumb: []
source_path: "boit/create-send-bu.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Creación y envío de facturas de unidades de negocio

Puede personalizar los mensajes de texto que aparecen en la cabecera y el pie de página de una factura. Los mensajes se almacenan en la tabla Mensajes de factura por correo electrónico. Las descripciones de los tres mensajes son las siguientes:

- **Mensaje global** - Mensaje que se mostrará en la parte superior de cada factura. Esto se añade al mensaje de cabecera por defecto.
- Mensaje de cabecera **predeterminado** : el mensaje predeterminado que se mostrará en la parte superior de cada factura si no se ha definido un mensaje de cabecera predeterminado en la tabla Lista de facturas de destinatarios, o mediante un mensaje introducido en Producción en el momento de enviar la factura.
- **Mensaje de pie de página predeterminado** : el mensaje predeterminado que se mostrará en la parte inferior de cada factura si no se ha definido un mensaje de pie de página en la tabla Lista de facturas de destinatarios.

Para editar los mensajes:

1. En el explorador de proyectos TBM Studio , abra la tabla **Mensajes de factura por correo electrónico**. La tabla se encuentra debajo del grupo.
2. En la pestaña **Inicio**, haga clic en **Exportar** y seleccione **Excel** para exportar la tabla a Excel.
3. Modifique el texto en Excel y guarde el archivo.
4. Cargue el archivo en la tabla Mensajes de factura por correo electrónico.
   - Establezca la fecha de inicio del proyecto.
   - Haga clic en el paso **Cargar**.
   - Haga clic en **Carga inicial** y seleccione **Sobrescribir**.
   - Localice el archivo Excel que desea cargar.

**Designar a los destinatarios y sus datos de facturación**

Los usuarios que recibirán una factura vienen determinados por la lista de usuarios de la tabla Lista de facturas recibidas. Mantenga la lista en una hoja de cálculo Excel y cargue el archivo en. Consulte [Cargar un archivo de datos](../studio/data_studio/upload-data-file.htm "(se abre en una pestaña o una ventana nueva)").

Los campos de la tabla incluyen:

- **Nombre de la factura** - Cada línea debe tener un valor único.
- **Columna Filtro** - Puede limitar las entradas de una factura aplicando un filtro. Introduzca el nombre de una columna de la tabla Datos maestros de asignación de unidades de negocio. Las columnas más utilizadas son Órgano de Gobierno, Unidad de Negocio y Departamento. La columna puede ser una columna personalizada de la tabla de datos maestros.
- **Valor de filtro** - Introduzca un valor de la columna de filtro. Por ejemplo, puede introducir el nombre de una unidad de negocio.
- **Destinatario** - Introduzca el nombre del destinatario seguido de su dirección de correo electrónico. Puede introducir un correo electrónico individual o un alias. Los nombres son opcionales. Sólo se requiere una dirección de correo electrónico.   
   **Ejemplo** : Pat Smith <psmith@abc \_company.com >.
- **Responder a** - El nombre y la dirección de correo electrónico de la persona con la que deben ponerse en contacto los destinatarios para obtener más información sobre la factura.   
   **Ejemplo** : Pat Smith <psmith@abc \_company.com >.   
   **NOTA** : Se puede utilizar un alias de correo electrónico en el campo, pero no se puede introducir una lista de direcciones de correo electrónico.
- **Mensaje de cabecera por defecto** : el primer mensaje que aparece en la parte superior de la factura. Si el campo se deja en blanco, se utilizará el Mensaje Global.
- **Mensaje a pie de página** - El mensaje que aparece en la parte inferior de la factura. Si el campo se deja en blanco, se utilizará el Mensaje de pie de página predeterminado.

**Bloquear a puesta en escena y promover a producción**

Las facturas sólo pueden enviarse desde el entorno de Producción. Debe bloquear el proyecto en el entorno de puesta en escena y, a continuación, promover el proyecto al entorno de producción. Ver [Bloquear y promover un proyecto](https://community.apptio.com/docs/doc-5117 "(se abre en una pestaña o una ventana nueva)").

**Designar las facturas que se enviarán**

1. Cambie al entorno de producción.
2. En la página de inicio, haga clic en **Gestionar y enviar facturas**.
3. Haga clic en la factura que desea enviar o en **Enviar todas las facturas** en la página principal.   
    Sólo enviará las facturas que aún no se hayan enviado.

**Introducir un mensaje personalizado para una factura concreta**

Puede introducir un mensaje personalizado para una factura concreta.

1. Abra la factura que desea editar.
2. Navegue hasta la sección de comentarios situada a la izquierda de la pantalla.
3. Introduzca su comentario en la casilla.
4. Si desea enviar ahora la factura con el mensaje personalizado, haga clic en **Enviar**.
5. Si desea enviar la factura en otro momento, haga clic en **Guardar**.   
    Esto guardará el mensaje personalizado y lo mostrará la próxima vez que abra la factura.
6. Si vuelve a abrir una factura con un mensaje guardado, podrá volver a editar el mensaje o enviar la factura

**Vista previa de una factura**

Puede previsualizar una factura antes de enviarla de dos maneras.

- **Navegue hasta el informe Factura** :
  - Este informe se encuentra en la colección de informes **Cargos por servicio**. Para visualizar el informe, haga clic en **Factura**.
  - Utilice **el Rebanador Global de Jerarquía de Unidades de Negocio** para crear variantes de la factura para su previsualización.   
     Tenga en cuenta que esta pantalla no tendrá ningún impacto en la factura real. Los cambios que realice aquí son sólo para fines de previsualización.
- **Haga clic en la factura y localice el panel de vista previa en la parte derecha de la pantalla** - Esta pantalla le mostrará lo que realmente se enviará. La columna de filtro y el valor definidos en el conjunto de datos se aplicarán aquí y no podrán modificarse en Producción. Esta pantalla es muy similar a la que verá el destinatario al abrir el correo electrónico.

**Enviar factura(s) de la unidad de negocio**

Puede enviar facturas individuales o enviar todas las facturas. Si hace clic en **Enviar todas las facturas**, sólo se enviarán las facturas que no se hayan enviado antes.

Para enviar una sola factura:

1. Haga clic en la factura que desea enviar.
2. Navegue hasta el cuadro de comentarios situado a la izquierda de la pantalla.
3. Introduzca un comentario o deje el mensaje predeterminado.
4. Haga clic en **Enviar**.
5. Observe la barra de estado situada encima del cuadro de comentarios, esta barra de estado le avisará cuando la factura se haya enviado correctamente.
6. Si desea volver a enviar una factura ya enviada:
   1. Abrir la factura enviada anteriormente
   2. Haga clic en **Reiniciar** debajo del cuadro de comentarios a la izquierda de la pantalla.
   3. Haga clic en **Enviar**.
   4. Al restablecer la factura, también podrá enviarla utilizando la función **Enviar todas las facturas**

Para enviar todas las facturas, haga clic en **Enviar todas las facturas** en el Informe de distribución.

**Seguimiento del estado de las facturas**

Una factura puede tener uno de los siguientes estados:

- **No enviada** - La factura no ha sido enviada y requiere una acción por parte del remitente.
- **Enviada** - La factura se ha enviado correctamente pero no ha sido leída por el destinatario.
- **Leída** - La factura ha sido enviada y ha sido leída por el destinatario.
- **Error** - Se ha producido un error al enviar el mensaje. Puede ver el diálogo de errores para investigar.

**Eliminar el enlace del correo electrónico de la factura**

A partir de TBM Studio 2.9.1, puede eliminar del correo electrónico de la factura el enlace que envía a un usuario a la factura que generó el correo electrónico. Puede eliminar este enlace, si es necesario.

Para eliminar el enlace de correo electrónico:

1. En el explorador de proyectos TBM Studio , vaya a **Tablas >**, luego haga clic en **Lista de facturas de destinatarios**
2. En el cuadro de diálogo **Añadir a la lista de facturas del destinatario**, establezca el valor de **Enlace visible** en "no".   
    Cualquier otro valor en esta columna impide la posibilidad de ocultar el enlace. Para eliminar el enlace, el valor debe ser "no".
3. A partir de ahora, todos los correos electrónicos ya no mostrarán el enlace.
