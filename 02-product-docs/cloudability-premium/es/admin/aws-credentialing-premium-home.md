---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conexión con AWS - Guía de integración de clientes"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/aws-credentialing-premium-home.html"
images:
  - "images/AWS-VC.png"
  - "images/AWSp.png"
  - "images/TurboTarget.png"
  - "images/clip_image001_1499665667.png"
  - "images/clip_image002_-1577046812.png"
  - "images/curP.png"
  - "images/curP1.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexión con AWS - Guía de integración de clientes

Descripción general

Esta guía le explica paso a paso cómo conectar de forma segura su entorno de AWS a IBM, Cloudability y Turbonomic. Una vez conectado, podrás disfrutar de una experiencia mejorada en FinOps, tanto en Cloudability como en Turbonomic.

Nota: Para garantizar una compatibilidad y un soporte técnicos óptimos, siga los pasos de conexión tal y como se describen. No se admiten configuraciones CUR personalizadas. Si tienes alguna pregunta, ponte en contacto con **el servicio de asistencia** de IBM.

Requisitos previos

Antes de empezar, asegúrate de que tienes acceso a:

- Consola de AWS
- Privilegios de administrador (o similar) en AWS para la creación de S3 y permisos IAM
- Acceso de administrador a Cloudability Credenciales de vendedor

Cloudability 's AWS El proceso de acreditación requiere dos pasos principales:

- Acreditación de cuentas de gestión
- Acreditación de cuentas vinculadas

AWS Acreditación de cuentas de gestión

Cloudability utiliza la acreditación de cuentas de gestión AWS para:

- Aportar datos de Coste y Utilización para la(s) Cuenta(s) de Gestión acreditada(s).
- Sincronización de las cuentas vinculadas en la(s) cuenta(s) de gestión.

Nota: Para que esto funcione, debe tener activada la facturación consolidada y sus cuentas vinculadas deben transferirse (desde el punto de vista de la facturación) a su cuenta de gestión.

El proceso de obtención de credenciales implica algunos pasos que requerirán que realice acciones tanto en AWS como en Cloudability en varias fases.

Empecemos con el proceso de acreditación:

1. **AWS Consola - Crear un informe de costes y uso de AWS**
   1. En la **consola de gestión AWS**, seleccione el nombre de su cuenta en la parte superior derecha y seleccione **Facturación y gestión de costes**.
   2. En la página **Panel de facturación y gestión de costes**, seleccione **Exportación de datos (en Análisis de costes y uso)**.
   3. Seleccione **Crear**.

Cloudability admite AWS Legacy CUR y CUR 2.0 en ambos formatos.

- gzip - texto/csv
- Parqué - Parqué

A continuación se indican los pasos necesarios para configurar cualquiera de ellos.

Nota: No se admiten otras exportaciones de datos de « AWS » (por ejemplo, el CUR pro forma)

- Cloudability admite exportaciones de datos creadas a nivel de cuenta de gestión.

Cuadro 1. Tabla de configuración

| Pasos en AWS | Legado CUR | CUR 2.0 |
| --- | --- | --- |
| Crear exportación > Detalles de la exportación | Exportación de CUR heredados | Exportación de datos estándar |
| Crear exportación > Configuración del contenido de la tabla de datos | Seleccione **Incluir ID de recursos**. **Los datos de imputación de costes fraccionados** deben estar **desmarcados**.  Seleccione **Actualizar automáticamente en la configuración de actualización de datos.** | Seleccione **CUR 2.0**.  - Seleccione **Incluir ID de recursos**. - **Los datos de imputación de costes fraccionados** deben estar **desmarcados** - Seleccione **Cada hora** para la granularidad temporal de los datos del Informe.  Selección de columna - Dejar **por defecto** (todas las columnas) |
| Para las opciones de entrega de exportación de datos, seleccione lo siguiente. | Seleccione **Cada hora** para la granularidad temporal de los datos del Informe.  Seleccione Crear **nueva versión de informe.**  Nota: Esto es necesario para garantizar un funcionamiento fluido entre Cloudability y Turbonomic.  Las opciones de integración de datos de informes no deben seleccionarse.  Asegúrese de que el tipo de compresión es **gzip o parquet** | Asegúrese de que el tipo de compresión esté configurado como **gzip-text/cs o parquet.**  Asegúrese de que está seleccionada la opción Crear **nuevo archivo de exportación de datos** para el versionado de informes.  Nota: Esto es necesario para que Cloudability y Turbonomic funcionen a la perfección entre sí |
| Para la configuración del almacenamiento de exportación de datos. | Sus archivos de informes de costes y uso residirán en este bucket. Tú puedes;   - Introduzca un cubo y un prefijo preexistentes en S3 O - Seleccione **Configurar**. Si se selecciona Configurar   - Seleccione **Crear un cubo** (o seleccione un cubo existente si ya está creado)   - Introduzca un nombre para el cubo S3   - Seleccione la región para crear un nuevo cubo   - Haga clic en **Crear cubo**   - Añadir un **prefijo de ruta s3**   - Añadir etiquetas **(opcional)**   - Seleccione **Crear informe** | Sus archivos de informes de costes y uso residirán en este bucket. Tú puedes;   - Introduzca un cubo y un prefijo preexistentes en S3 O - Seleccione **Configurar**. Si se selecciona Configurar   - Seleccione **Crear un cubo** (o seleccione un cubo existente si ya está creado)   - Introduzca un nombre para el cubo S3   - Seleccione la región para crear un nuevo cubo   - Haga clic en **Crear cubo**   - Añadir un **prefijo de ruta s3**   - Añadir etiquetas **(opcional)**   - Seleccione **Crear** |

Nota: «Cloudability » busca el archivo de manifiesto en la siguiente ubicación:

**CUR heredado** - <Prefijo del informe de costes y utilización>/<Nombre del informe de costes y utilización>/YYYYMMDD-YYYYMMDD/<Nombre del informe de costes y utilización> -Manifest.json

**CUR 2.0** - <Prefijo del informe de costes y uso>/<Nombre del informe de costes y uso>/metadatos/BILLING\_PERIOD=YYYY-MM/<Nombre del informe de costes y uso> -Manifest.json

![cur](../../../../03-media/cloudability-premium/images/curP.png)![cur](../../../../03-media/cloudability-premium/images/curP1.png)

Nota: Los clientes pueden configurar el cifrado del lado del servidor con claves gestionadas de Amazon S3 ( SSE-S3 ) en sus depósitos de S3. Cloudability No admite el cifrado mediante KMS ni claves de cifrado proporcionadas por el cliente.

Por favor, anote los siguientes datos, ya que se introducirán en Cloudability en los pasos siguientes:

1. **ID DE CUENTA DEL PAGADOR: ID de cuenta de administración AWS**
2. **S3 NOMBRE DEL CUBO:** El bucket que contiene su informe de Costes y Usos creado anteriormente
3. **INFORME DE COSTES Y USOS NOMBRE** creado anteriormente
4. **INFORME DE COSTES Y USOS PREFIX** creado anteriormente

Nota: Los clientes existentes en AWS Legacy CUR, pueden continuar en Legacy CUR. Si deseas migrar a CUR 2.0, deberás actualizar tus credenciales en Cloudability con CUR 2.0, ya que no es posible actualizar tu CUR heredado a CUR 2.0.The; la exportación de datos que crees siguiendo los pasos de Cloudability cargará, por defecto, los datos en la ubicación indicada anteriormente. Si se obtiene algún dato histórico, cloudability espera los archivos de manifiesto en la ubicación anterior.

Para más información sobre el paso de CUR heredado a CUR 2.0, consulte las preguntas más frecuentes

Por favor, deje las siguientes opciones sin marcar

- Datos de asignación de costes divididos
- Incluir columnas de reserva de capacidad y granularidad
- Descuentos compatibles manualmente

2. AWS Consola - Activar etiquetas de imputación de costes

1. Desde el **panel de control de facturación y gestión de costes**, accede a [**«Etiquetas de asignación de costes**](https://console.aws.amazon.com/billing/home#/tags "(se abre en una pestaña o una ventana nueva)") ».
2. Seleccione las etiquetas que desea incluir.

   Nota: Tenga cuidado con el caso de los camellos. Por ejemplo: Si tiene "Nombre" o "nombre" como clave de etiqueta, ambos deben activarse para que se escriban en CUR.
3. Seleccione **Activar**.

3. Cloudability - Configure las credenciales de la cuenta de gestión AWS

Debe tener derechos de administrador en Cloudability para completar este procedimiento. Si no tiene derechos de administrador, póngase en contacto con el administrador principal de Cloudability de su organización para obtener ayuda.

En Cloudability, vaya a **Configuración>** **Credenciales de proveedor>** **Añadir fuente de datos y seleccione > AWS**.

1. En **Credenciales**, introduzca lo siguiente:
   - **ID de cuenta del pagador (obligatorio)**
   - **S3 Nombre del cubo (obligatorio):** El bucket que contiene su informe de Costes y Usos
   - **Nombre del informe de costes y uso (obligatorio)**
   - **Prefijo del informe de costes y uso (obligatorio)**
   - **AWS Región habilitada para SCP (opcional)**
     - En caso de que haya aplicado [una Política de control de servicio (SCP) de AWS](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Forganizations%2Flatest%2Fuserguide%2Forgs_manage_policies_scps.html "(se abre en una pestaña o una ventana nueva)") que restrinja el acceso en algunas regiones AWS, indique su región *permitida*; por ejemplo: us-east-2. En caso contrario, puede dejarse en blanco. Esto ayuda a Cloudability a realizar llamadas de verificación a la región especificada.
     - Actualmente, Cloudability permite añadir una única región SCP.
   - **Acreditación automática de la(s) cuenta(s) vinculada(s) (Recomendado)**
     - Recomendamos el uso de [credenciales automatizadas de cuentas vinculadas AWS](aws-credentialing-premium-linked.html) si tiene una cantidad significativa de cuentas vinculadas. Esto simplificará el proceso de acreditación ahora y para futuras adiciones de nuevas cuentas.
     - Para utilizar la función de credenciales automatizadas de cuentas vinculadas de Cloudability, es necesario realizar un trabajo adicional en Cloudability y AWS, que incluye la descarga de una plantilla de CloudFormation de una cuenta vinculada y su implementación como StackSet (asegurándose de que se ha establecido la función de IAM correcta para que las cuentas vinculadas hereden los permisos de IAM). Este tema se aborda en detalle en la sección sobre credenciales de cuentas vinculadas.
   - **Elige entre el reajuste avanzado en modo de solo lectura o la automatización de acciones**
     - La selección **«Solo lectura»** implica que estás concediendo permisos de lectura para tu entorno, pero no para realizar acciones, tanto en Cloudability cost como en Turbonomic cost y Turbonomic.
     - La selección **de «Automatizar acciones»** implica que estás concediendo todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir... Turbonomic ejecución y ejecución de facturación Turbonomic.

   Nota: Cuando se selecciona la opción de acreditación automática de las cuentas vinculadas de AWS, la elección entre «**Solo lectura** » y **«Automatizar acciones»** se aplicará también a tus cuentas vinculadas. Si **NO** está seleccionado, la elección entre **«Solo lectura»** y ****«Automatizar acciones»**** deberá realizarse de forma individual para cada cuenta vinculada.
2. Seleccione **Guardar**.
3. Seleccione **Generar plantilla**.
4. Seleccione **Descargar**.
5. Se descargará localmente una plantilla AWS CloudFormation. Guárdela en un lugar seguro para el siguiente paso, ya que tendrá que cargarla en la consola AWS.![aws](../../../../03-media/cloudability-premium/images/AWS-VC.png)

4. AWS Consola - Cargue la plantilla CloudFormation en la consola de gestión AWS

1. En **la consola de gestión AWS**, busque 'CloudFormation' y selecciónelo.
2. En la página **AWS CloudFormation** seleccione **Crear pila (con nuevos recursos (estándar))**.
3. En **Especificar plantilla**, haga lo siguiente:
   - Seleccione **Cargar un archivo de plantilla**.
   - Seleccione **Elegir archivo** y cargue la plantilla que descargó de Cloudability.
   - Seleccione **Siguiente**.
4. En la página **Especificar detalles de pila**, haga lo siguiente:
   - Introduzca un **nombre para la pila** (por ejemplo, ' Cloudability ').
   - Verifique los **Parámetros** rellenados.
   - Seleccione **Siguiente**.
5. Desplácese por la página **Configurar opciones de pila** y marque la casilla "Reconozco que AWS CloudFormation podría crear recursos IAM con nombres personalizados" y haga clic en Siguiente.
6. En la página **Revisar**, seleccione **Enviar**.

Su nueva pila tiene inicialmente el estado **CREATE\_IN\_PROGRESS**. Cuando el estado cambie a **CREATE\_COMPLETE**, podrá verificar su credencial en Cloudability. Es posible que tenga que actualizar la página CloudFormation en la interfaz de usuario para confirmarlo.

5. Cloudability - Verificar las credenciales de la cuenta

1. En Cloudability, vaya a **Configuración > Credenciales de proveedor > AWS**.
2. Haga clic en el botón... situado junto a la cuenta cuyas credenciales desea verificar y seleccione Reverificar.
   - Una marca verde (![../../resources/cldy_images/clip_image001_-1832790195.png](../../../../03-media/cloudability-premium/images/clip_image001_1499665667.png)) indica que se ha realizado correctamente, mientras que un signo de exclamación rojo (![../../resources/cldy_images/clip_image002_-821243953.png](../../../../03-media/cloudability-premium/images/clip_image002_-1577046812.png)) indica que hay errores.

Nota: Este proceso creará un rol IAM llamado CloudabilityRole que Cloudability utilizará para verificar los permisos. En caso de que falle la verificación, vuelva a intentarlo transcurridos 15 minutos.

![aws](../../../../03-media/cloudability-premium/images/AWSp.png)

Una vez finalizado este proceso, en unas pocas horas,

- Cloudability Empezará a mostrar tus datos de facturación y las etiquetas « AWS » en Cloudability.
- También se incluirían los datos sobre precios.
- Cloudability también mostrará las cuentas vinculadas.

El siguiente paso consiste en verificar las cuentas vinculadas.

**Estado de las credenciales**

Cloudability La pantalla de credenciales del proveedor muestra el estado de la cuenta desde:

- Cloudability
- Turbonomic

Una vez ejecutadas las últimas plantillas, el estado de la cuenta debería estar sincronizado entre Cloudability y Turbonomic. Para obtener más información sobre el estado de la cuenta, consulte la sección de detalles de la cuenta.

![](../../../../03-media/cloudability-premium/images/TurboTarget.png)

[AWS Acreditación de cuentas vinculadas](aws-credentialing-premium-linked.html)

[AWS Actualización de los clientes existentes de Cloudability a Cloudability Premium](aws-credentialing-premium-upgrading.html)

[AWS Obtención de métricas de memoria para las instancias de EC2 - Windows y Linux](aws-credentialing-premium-memory.html)

[AWS PREGUNTAS FRECUENTES](aws-credentialing-premium-faq.html)

- **[AWS Acreditación de cuentas vinculadas](../admin/aws-credentialing-premium-linked.html)**
- **[AWS Acreditación mediante acciones masivas](../admin/aws-credentialing-bulk-actions.html)**
- **[Conexión con AWS - Actualización de los clientes existentes de Cloudability a Cloudability Premium](../admin/aws-credentialing-premium-upgrading.html)**
- **[AWS Etiquetas](../admin/support-for-aws-tags.html)**
- **[Conexión con AWS - Obtención de métricas de memoria para instancias de EC2 (Windows y Linux )](../admin/aws-credentialing-premium-memory.html)**
- **[Permisos Referencia - Amazon Web Services](../admin/permissions-reference-aws.html)**
- **[Preguntas frecuentes para conectar con AWS](../admin/aws-credentialing-premium-faq.html)**
