---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cargar un fichero de datos"
breadcrumb: []
source_path: "studio/data_studio/upload-data-file.html"
images:
  - "resources/images/studio_images/closed_period.png"
  - "resources/images/studio_images/closed_period_1.png"
  - "resources/images/studio_images/closed_period_2.png"
  - "resources/images/studio_images/closed_period_3.png"
  - "resources/images/studio_images/config-notification_601x120.png"
  - "resources/images/studio_images/data-freshness.png"
  - "resources/images/studio_images/image-upload-data-file-2021_700x328.png"
  - "resources/images/studio_images/late-file-noti.png"
  - "resources/images/studio_images/late-noti-popup.png"
  - "resources/images/studio_images/studioimages/studio/stu571.png"
  - "resources/images/studio_images/studioimages/studio/stu599.png"
  - "resources/images/studio_images/studioimages/studio/stu657.png"
  - "resources/images/studio_images/studioimages/studio/stu680.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cargar un fichero de datos

**Se aplica a** : TBM Studio 12.0 y posteriores. TBM Studio acepta datos de archivos planos en formatos separados por comas, tabulaciones, tuberías, tildes, dos puntos y puntos y coma. Antes de poder cargar datos, debe crear una tabla en la que se cargarán los datos, si no existe ya.

Para obtener más información, consulte [Crear una tabla](create-table.htm "(se abre en una pestaña o una ventana nueva)"). Vea este vídeo de demostración de Apptio Education Services: [Importación de datos y configuración del encabezado en la primera fila (3 min.)](https://community.apptio.com/videos/1642 "(se abre en una pestaña o una ventana nueva)")

O consulte [todos los vídeos de Apptio](https://community.apptio.com/docs/DOC-7714 "(se abre en una pestaña o una ventana nueva)").

## Cargar datos

Sugerencia: Si el nombre del archivo contiene más de un punto (.), TBM Studio devolverá un error de extensión de archivo no compatible y no cargará el archivo. Asegúrese de que el nombre de su archivo sólo tiene un punto antes de la extensión del tipo de archivo. Ejemplos:

- example\_data.xlsx es correcto.
- example.data.xlsx no es correcto.

1. En TBM Studio, consulte un documento. Para más información, consulte [Buenas prácticas: Check out y check in](../admin/bp-check-out.html "(se abre en una pestaña o una ventana nueva)").
2. Haga clic en **Fuente** en el canal de transformación de la tabla.
3. En el campo **Descripción de la** tabla, introduzca una breve descripción de la finalidad de la tabla.
4. Haga clic en **Cargar archivo**.
   - Si ha comprobado una tabla existente, ya debería tener un paso de carga.
   - Si ha creado un nuevo paso, se añadirá un paso de **carga** a la canalización.
5. Realiza una de las siguientes acciones:
   - Haga clic en el panel **Detalles** y busque el archivo que desea cargar.
   - Arrastre un archivo al panel **Detalles**.

     Se añade un paso de **Importación** al proceso.

     ![Cargar datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu599.png)
6. Haga clic en el paso **Importar** de la canalización y revise la configuración:
   - **Iniciar la importación en la fila** : Indique la primera fila de la tabla que se incluirá en la importación. La importación siempre incluye la fila de cabecera en el archivo. El número introducido designa la fila de datos en la que se iniciará la importación. Por ejemplo, en la hoja de cálculo siguiente, si se introduce un 2 en el campo, se empezará por la fila de Nueva York porque es la segunda fila de datos.![Iniciar la importación en la fila](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu657.png)
   - **Columnas a excluir** : Indique si hay columnas que desea excluir.
   - **Codificación de texto** : Si el archivo de datos utiliza una codificación de caracteres determinada, seleccione el esquema de codificación de la lista. Si no está seguro de la codificación, seleccione la opción **Autodetectar codificación**.
   - **Delimitado** : Seleccione el carácter que separa los campos de datos en el archivo. En la mayoría de los casos, será una coma.
   - **Calificador de texto** : Si hay caracteres de texto especiales en los datos, indique el calificador de texto que se utiliza para rodear esos caracteres. Por defecto, las comillas son dobles.
   - **Columnas** : Revise las columnas listadas y, si lo desea, cambie los tipos de columna. Para filtrar por tipo de columna (clave, texto, número, fecha), haga clic en un icono de tipo en el campo de búsqueda de la columna **Tipo**.

     Consejo: El paso Importar admite validaciones de datos y cardinalidad, como se describe a continuación.
7. Para revisar la tabla cargada, haga clic en el paso **Tabla** del pipeline.
8. Si la tabla es aceptable, haga clic en **Guardar** en la pestaña Inicio.
9. Si ha terminado de editar, haga clic en **Registrar**.

## Validación de datos y cardinalidad

(Se aplica a: TBM Studio v12.1 y posteriores)

Al cargar datos, la aplicación puede comprobar la validación de datos y la validación de cardinalidad. Las opciones están disponibles en el paso Importar de las cadenas de transformación.

![Validación de datos y cardinalidad](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu680.png)

La validación de datos se aplica cuando se cargan datos en una tabla existente. Comprueba lo siguiente:

- Columna añadida
- Columna eliminada
- Cardinalidad de columna modificada
- El tipo de columna ha cambiado entre la sustitución de tipo, el documento de la tabla sin procesar existente y el documento de la tabla de preparación

La validación de cardinalidad se aplica a las tablas nuevas y a las ya existentes. Comprueba el contenido de una columna. Puede aplicarse a cada columna por separado. Hay tres opciones:

- Cualquiera: Desactiva la validación de cardinalidad para la columna.
- Uno: Comprueba si la columna contiene valores únicos. No hay duplicados.
- Muchos: Comprueba si todas las entradas de la columna están duplicadas.

## Cargar datos adicionales en una tabla

Puede cargar datos adicionales en una tabla. Por ejemplo, puede que desee cargar datos de costes mensuales. Puede añadir o sustituir los datos existentes por otros nuevos.

La carga de datos adicionales en una tabla puede adoptar dos formas:

- Añadir varios archivos al mismo periodo de tiempo.
- Carga de los datos de una misma tabla en distintos periodos de tiempo, que se describe en esta sección.

Para cargar datos adicionales en una tabla:

1. Echa un vistazo a la tabla.
2. Cambie el selector de fecha al periodo en el que se añadirán los datos. Se añade un marcador de posición al paso Cargar de la cadena de transformación. En la siguiente imagen, se ha añadido un marcador de posición de marzo:![Cargar datos adicionales en una tabla](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu571.png)
3. Haga clic en el marcador de posición y navegue hasta el archivo que desea cargar o arrastre un archivo desde el Explorador de Windows hasta el marcador de posición.
4. Guarda los cambios.

Carga de datos durante un periodo de tiempo no válido
:   Un ejemplo de criterios para las siguientes condiciones

    ![Carga de datos durante un periodo de tiempo no válido](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/closed_period.png)

    ![Carga de datos durante un periodo de tiempo no válido 2](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/closed_period_1.png)

    ![Carga de datos durante un periodo de tiempo no válido 3](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/closed_period_2.png)

    ![Carga de datos durante un periodo de tiempo no válido](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/closed_period_3.png)

## Formatos de datos

La aplicación acepta datos de archivos planos en formatos separados por comas, tabulaciones, tuberías, tildes, dos puntos y puntos y coma. Para cargar un archivo de datos, haga clic en la opción **Cargar archivo**. Antes de poder cargar datos, debe crear una tabla en la que se puedan cargar los datos.

Sugerencia: Si el nombre del archivo contiene más de un punto (.), TBM Studio devolverá un error de extensión de archivo no compatible y no cargará el archivo. Asegúrese de que el nombre de su archivo sólo tiene un punto antes de la extensión del tipo de archivo. Ejemplos:

- example\_data.xlsx es correcto.
- example.data.xlsx no es correcto.

## Ciclos de actualización de datos

Cuando se crea una nueva tabla cargando un archivo de datos, se puede seleccionar un ciclo de actualización en el campo de la parte superior de la pantalla que describe la frecuencia con la que se espera que se actualice un conjunto de datos. Las opciones se muestran a continuación. Esto es sólo descriptivo. No ejecuta cargas.

![Ciclos de actualización de datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/image-upload-data-file-2021_700x328.png)

Consejo: Puede cambiar el Ciclo de Actualización de Datos de **actualizaciones Ad-Hoc** a versiones Mensuales o Anuales. Para ello, debe asegurarse de cargar archivos de datos para cada uno de los periodos de carga que aparecen en el panel de **carga**. Si deja periodos de carga sin archivos de datos, puede afectar al modelo de costes.

A continuación se describen los ciclos de actualización de datos:

|  |  |
| --- | --- |
| Actualizaciones ad hoc | Las actualizaciones se realizarán en función de las necesidades. Los datos pueden añadirse a la tabla existente o sustituirla. No se realizarán comprobaciones de caducidad de datos. |
| 1 versión; sin actualizaciones programadas | Los datos cargados sustituirán a los existentes. No se realizarán comprobaciones de caducidad de datos. |
| 1 versión; Actualización mensual | Los datos se actualizarán cada mes. Los nuevos datos sustituirán a los existentes. En el informe de calidad de datos de Costing Standard , las comprobaciones de caducidad de datos mostrarán los datos como caducados si no se han actualizado en el último mes. |
| 1 versión; actualización anual | Los datos se actualizarán cada año. Los nuevos datos sustituirán a los existentes. En el informe de calidad de datos de Costing Standard , las comprobaciones de caducidad de datos mostrarán los datos como caducados si no se han actualizado en el último año. |
| Versiones mensuales; actualización cada mes | Los datos se actualizarán cada mes. Los nuevos datos se añadirán a un periodo diferente y no sobrescribirán los datos existentes. En el informe de calidad de datos de Costing Standard , las comprobaciones de caducidad de datos mostrarán los datos como caducados si no se han actualizado en el último mes. |
| Versiones anuales; actualización mensual | Cada mes se carga un año de datos que abarcan los últimos 12 meses. Los nuevos datos se añadirán a un periodo diferente y no sobrescribirán los datos existentes. En el informe de calidad de datos de Costing Standard , las comprobaciones de caducidad de datos mostrarán los datos como caducados si no se han actualizado en el último mes. |
| Versiones anuales; actualización a principios de año | Los datos de un año se cargan al principio de cada ejercicio fiscal. Los nuevos datos se añadirán a un periodo diferente y no sobrescribirán los datos existentes. Si no se carga un conjunto de datos para el año siguiente, los datos se arrastrarán al periodo siguiente. En el informe de calidad de datos, las comprobaciones de caducidad de datos mostrarán los datos como caducados si no se han actualizado en el último año. Seleccione esta opción para las tablas en las que los valores son diferentes cada año. |
| Versiones anuales con prórroga; Actualización a principios de año | Los datos de un año se cargan al principio de cada ejercicio fiscal. Los nuevos datos se añadirán a un periodo diferente y no sobrescribirán los datos existentes. Si no se carga un conjunto de datos para el año siguiente, se arrastran los valores del año anterior. Seleccione esta opción para las tablas en las que los valores son prácticamente los mismos cada año. |

## Comprobación de caducidad de datos

Esta función es aplicable a partir de la versión 12.10.8.

El enlace **Haga clic para configurar las notificaciones** le permite configurar las notificaciones a los usuarios cuando los datos cargados hayan caducado. Envía recordatorios a los usuarios para que carguen los nuevos datos, según el ciclo de actualización de datos elegido.

Nota: Este enlace aparece para todas las opciones de actualización de datos, excepto **las actualizaciones Ad-Hoc** y **1 versión; Sin actualizaciones programadas**.

![Comprobación de caducidad de datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/config-notification_601x120.png)

Haga clic en el enlace para proporcionar los detalles y seleccione el botón **Crear**.

![Ventana emergente de notificación](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/late-noti-popup.png)

|  |  |
| --- | --- |
| Enviar notificación por correo electrónico a: | Introduzca la dirección de correo electrónico del usuario al que debe enviarse la notificación. Aquí puede introducir varias direcciones de correo electrónico. |
| Enviar notificación por correo electrónico | Elija el número de días tras los cuales debe enviarse el correo electrónico de notificación. |
| Envío diario de notificaciones por correo electrónico hasta que se complete la carga | Seleccione esta casilla si desea enviar diariamente correos electrónicos de notificación de archivos atrasados. Los correos electrónicos se enviarán hasta que se carguen los nuevos datos. |

Una vez creada la configuración, puede pasar el cursor por encima del enlace para ver los detalles de la configuración.

![detalles de configuración](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/late-file-noti.png)

## Comprobación de la frescura de la fecha

Para comprobar si se han cargado datos actualizados, vaya a la pestaña **Proyecto** y seleccione la opción **Actualización de datos**.

![Comprobación de la frescura de la fecha](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/data-freshness.png)

Puede consultar los siguientes detalles aquí:

- **Resumen de frescura de datos** : muestra la lista de archivos con su información de caducidad
- **Reglas de actualización de datos** : muestra la lista de reglas, con la opción de añadir más reglas

## Crear una tabla a partir de una tabla existente

Para crear una tabla a partir de una tabla existente, haga clic con el botón derecho en un paso de la cadena de transformación y haga clic en **Crear nueva tabla** a partir de este paso. La acción Crear nueva tabla está disponible en algunos pasos de una canalización, pero no en todos. La tabla creada no estará vinculada a la tabla original. Para saber más, pulse [aquí](create-table-from-existing-table.htm "(se abre en una pestaña o una ventana nueva)").
