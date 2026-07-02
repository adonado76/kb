---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar Snowflake"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-snowflake.html"
images:
  - "images/snowflake_1.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Snowflake

Puedes vincular tu cuenta de Snowflake a Cloudability para habilitar la importación de datos de costes detallados de Snowflake para los almacenes, junto con las etiquetas a nivel de almacén y de cuenta de Snowflake.

Nota: Los datos iniciales sobre costes y consumo tardan entre 4 y 24 horas en aparecer en Cloudability.

Si adquieres Snowflake a través del mercado de un proveedor de servicios en la nube y añades datos de costes y uso de Snowflake mediante esta integración, verás que los costes aparecen dos veces en los informes de Cloudability. Por ejemplo, si hubieras comprado « Snowflake » a través de la tienda de AWS, tendrías:

- La partida presupuestaria de alto nivel correspondiente a « AWS ».
- Los artículos que incluyen información detallada sobre los costes de Snowflake y en **AWS Marketplace,** donde figuran como **«Vendedor».**

Tendrás que configurar filtros o vistas para ocultar los costes de Marketplace. Los costes del Marketplace no se incluyen en la factura.

**Requisitos previos**

- Acceso de administrador a Cloudability para consultar las credenciales de los proveedores.
- Accede a Snowflake org, 1.0 o 2.0 (se recomienda 2.0 ) para obtener datos detallados sobre los costes.
- Account Admin permisos en Snowflake 1.0.
- Permisos de administrador global de la organización para Snowflake 2.0.
- Para activar las etiquetas « Snowflake »

  - Cuenta de facturación de «Org 2.0 » con « Enterprise Edition » o superior
  - Vista de SNOWFLAKE.ORGANIZATION\_USAGE. [TAG\_REFERENCES](https://docs.snowflake.com/en/sql-reference/organization-usage/tag_references "(se abre en una pestaña o una ventana nueva)") activada. Se trata de un contenido premium, por lo que puede conllevar costes adicionales Snowflake. Para reducir costes, puedes pedir a Snowflake que desactive todas las vistas premium excepto la que necesitamos (a menos que necesites alguna de estas vistas premium)

Nota: Puedes ejecutar la consulta siguiente en tu consola de Snowflake para comprobar si los valores de las etiquetas son visibles: *SELECT \* FROM SNOWFLAKE.ORGANIZATION\_USAGE.TAG\_REFERENCES;*

Si la vista «Referencias de etiquetas» no está activada, los costes detallados a nivel de almacén seguirán estando disponibles, pero sin la información de las etiquetas.

**Pasos para la integración**

**Snowflake**

Accede a tu cuenta de Snowflake con las credenciales adecuadas para consultar los datos de la cuenta.

**Buscar el nombre de la organización y de la cuenta**

1. Accede a **Snowsight** —el editor SQL basado en web para Snowflake —.
2. Abre el selector de cuentas desde la barra de menú de la esquina inferior izquierda. Aquí se muestra una lista de las cuentas a las que se ha accedido anteriormente.
3. Identifica el nombre de la cuenta y, a continuación, selecciona la cuenta.
4. Pasa el cursor por encima de la cuenta seleccionada para ver más detalles.
5. Copia los datos **del nombre de la organización** y del **nombre de la cuenta**.

   ![captura de pantalla de Snowflake](../../../../03-media/cloudability-premium/images/snowflake_1.jpg)

**Cloudability** 

1. Accede a la aplicación « Cloudability » y haz clic en **«Credenciales de proveedor»**, dentro de **«Configuración»,** en el menú de la izquierda.
2. Facilita la siguiente información:
   - **Nombre de la organización** : Pega el nombre de la organización que has copiado anteriormente de Snowflake.
   - **Snowflake Nombre de la cuenta** : pega el nombre de la cuenta que has copiado anteriormente de Snowflake.
   - **Nombre del almacén** : Indica el nombre de un almacén existente de Snowflake.
   - **Nombre de la base de datos** (para « Cloudability »): Indica un nombre para la base de datos que creará « Cloudability ».
   - **Nombre de usuario** (para Cloudability ): Indica un nombre para el usuario que creará Cloudability. También se creará un rol con el mismo nombre y el sufijo «**\_role** ».

**Cloudability - Generar plantilla**

Una vez introducidos todos los datos, haz clic en «**Credenciales del proveedor** » > «**Generar plantilla** ».

Esto generará la plantilla como un archivo de texto que contenga los detalles de configuración basados en las variables introducidas anteriormente.

**Snowflake - Plantilla de entrada**

1. Copia el contenido del archivo de texto generado.
2. Pega el contenido en la hoja de cálculo o el archivo de configuración correspondiente dentro de la cuenta de Snowflake. Asegúrate de que tienes el rol « **Account Admin** » en Snowflake.
3. Ejecuta la consulta SQL proporcionada y espera hasta que todas las sentencias se hayan ejecutado correctamente.

**Cloudability - Verificar las credenciales.**

1. Vuelve a Cloudability y accede a la pantalla «**Credenciales de proveedor** ».
2. Haz clic en **«Verificar credenciales»** para confirmar el estado de la integración.

   Si la casilla de selección aparece en verde, significa que has integrado correctamente Snowflake.

   Nota: Los enlaces privados aún no son compatibles con Snowflake.

**Preguntas más frecuentes**

**Soy un cliente de Snowflake que ya dispone de credenciales, pero no de datos detallados. ¿Tengo que realizar algún cambio para ver los costes detallados de « Snowflake »?**

Los clientes actuales seguirán viendo los costes del nivel de servicio sin que sea necesario realizar ningún cambio.

Para habilitar los datos granulares, debes volver a introducir las credenciales de las mismas cuentas de Snowflake.

- En Snowflake Org 1.0: obtendrás los costes detallados del almacén, pero no las etiquetas.

- Para acceder tanto a los costes detallados como a las etiquetas, actualiza tu cuenta a una organización de « Snowflake » ( 2.0 ) y, a continuación, vuelve a introducir tus credenciales.

**¿Hay algún paso que deba tener en cuenta antes de pasar a los costes detallados de Snowflake**?

Si ya utilizas **Snowflake** **Org 2.0**, no es necesario realizar ningún paso adicional más allá de **la renovación de credenciales**, ya que Cloudability requiere permisos adicionales para importar costes y etiquetas granulares a nivel de almacén.

**¿Qué etiquetas de « Snowflake » son compatibles?**

Admitimos etiquetas de Snowflake a nivel de almacén y de cuenta en el siguiente formato:

- cldy:copo de nieve:cuenta:<tagkey>
- cldy:copo de nieve:almacén:<tagkey>

Estos deberían asignarse en la página «Etiquetas y etiquetas» tras la primera importación de datos realizada con éxito.

**¿Dónde puedo conseguir la dirección IP para incluirla en la lista blanca?**

Ponte en contacto con el equipo de asistencia de IBM.

**¿Cuántos datos históricos se pueden volver a recuperar?**

Los datos detallados sobre los costes se empiezan a recopilar a partir del mes en que se activa la integración.

En el caso de los meses anteriores, es necesario volver a recuperar los datos. Cloudability permite recuperar datos históricos de **los últimos 12 meses** (incluido el mes actual).

Ponte en contacto con el equipo de asistencia de IBM para solicitar una nueva recopilación de datos.

**¿Por qué no puedo ver las etiquetas en Snowflake org 1.0?**

La visibilidad de las etiquetas requiere:

- Una **cuenta de facturación Snowflake Org 2.0** con Enterprise Edition o superior.
- Se ha activado la vista premium de « SNOWFLAKE.ORGANIZATION\_USAGE. [TAG\_REFERENCES](https://docs.snowflake.com/en/sql-reference/organization-usage/tag_references "(se abre en una pestaña o una ventana nueva)") »

Sin ellos, no es posible importar los datos de las etiquetas.
