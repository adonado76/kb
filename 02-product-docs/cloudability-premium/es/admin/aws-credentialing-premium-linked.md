---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "AWS Acreditación de cuentas vinculadas"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conexión con AWS - Guía de integración de clientes"
source_path: "admin/aws-credentialing-premium-linked.html"
images:
  - "images/AWS-linked1.png"
  - "images/TurboTarget.png"
  - "images/aws-linkedp.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image001_1499665667.png"
  - "images/clip_image002_-1398377466.png"
  - "images/clip_image002_-1577046812.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Acreditación de cuentas vinculadas

Nota: Para garantizar una compatibilidad y un soporte técnicos óptimos, siga los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tienes alguna pregunta, ponte en contacto con **el servicio de asistencia** de IBM.

Después de configurar su cuenta de gestión para la ingestión de datos, Cloudability mostrará las cuentas vinculadas bajo la cuenta de gestión en unas pocas horas, pero no contienen ningún dato de la API AWS.

AWS Los datos de la API son necesarios para obtener datos de utilización y compromisos que permitan el conjunto de funciones de optimización (por ejemplo, Rightsizing) en Cloudability.

Para habilitar el acceso a los puntos finales de la API AWS para cada cuenta vinculada, Cloudability genera plantillas CloudFormation para que las cargue en AWS. Esto se puede hacer a través de la automatización (recomendado) o manualmente para cada cuenta vinculada.

Acreditación automática de cuentas vinculadas

Recomendamos utilizar la automatización, ya que simplifica el proceso de acreditación, especialmente cuando se tiene un número significativo de cuentas vinculadas.

Antes de empezar:

- Familiarízate con [los conjuntos de pilas](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-prereqs-self-managed.html#stacksets-prereqs-accountsetup "(se abre en una pestaña o una ventana nueva)") de AWS.
- Asegúrese de que tiene la función IAM en su AWS - AWSCloudFormationStackSetAdministrationRole - esto asegura que las cuentas vinculadas pueden tener los permisos empujado a ellos.
- Asegúrese de haber marcado previamente la opción "Automatización de credenciales de cuentas vinculadas" durante el proceso de Consolidación de credenciales de cuentas.
- Familiarícese con [AWS Credentialing using Bulk Actions](aws-credentialing-bulk-actions.html)

En Cloudability - Navegue hasta la cuenta vinculada

- Vaya a **Configuración > Credenciales de proveedor > AWS**.
- Haga clic con el cursor del ratón sobre... de la cuenta vinculada **(no de la cuenta de gestión)**.
- Seleccione el icono del lápiz para abrir el panel Editar una credencial.
- Añada AWS Región habilitada para SCP (Opcional):
  - En caso de que haya aplicado AWS Service Control Policy/policies (SCP) que restrinjan el acceso en algunas regiones AWS, indique su región permitida; por ejemplo us-east-2. En caso contrario, puede dejarse en blanco. Esto ayuda a Cloudability a realizar llamadas de verificación a la región permitida especificada.
  - Actualmente, la capacidad de Nube permite añadir una única región SCP.
- **Elige entre las opciones avanzadas de ajuste de tamaño «Solo lectura» y **«Automatizar acciones»****
  - La selección **«Solo lectura»** implica que estás concediendo permisos de lectura para tu entorno, pero no para realizar acciones, tanto en Cloudability cost como en Turbonomic cost y Turbonomic.
  - La selección ****de «Automatizar acciones»**** implica que estás concediendo todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.

  Si se selecciona la opción «Acreditación automática de cuentas vinculadas de AWS », la elección entre **«Solo lectura»** y ****«Automatizar acciones»**** en la cuenta vinculada se ajustará a la selección realizada en el nivel superior.

  - Seleccione **Guardar.**
  - Seleccione **Descargar.**![aws](../../../../03-media/cloudability-premium/images/AWS-linked1.png)

En AWS - Cargue la plantilla CloudFormation en la consola de gestión AWS

1. En la **consola de gestión AWS**, trabajando en la cuenta vinculada que está acreditando, en la barra de búsqueda introduzca 'CloudFormation' y selecciónela.
2. Desde la página de **AWS CloudFormation**, seleccione **Crear StackSet**
3. En **Especificar plantilla**, haga lo siguiente:
   - Dejar los parámetros por defecto para permisos y prerrequisitos
   - Seleccione Cargar un archivo de plantilla.
   - Seleccione Elegir archivo y cargue la plantilla que ha descargado de Cloudability.
   - Seleccione **Siguiente**.
4. En la página **de detalles Especificar StackSet**, haga lo siguiente:
   - Introduzca un **nombre StackSet** (por ejemplo, ' Cloudability ').
   - Verifique los **Parámetros** rellenados.
   - Seleccione **Siguiente**.
5. Desplácese por la página **Configure StackSet options** y marque la casilla "I acknowledge that AWS Cloudformation might create IAM resources with customized names" y haga clic en Next.
6. En la página **Revisar**, seleccione **Enviar**.

Su nueva pila tiene inicialmente el estado **CREATE\_IN\_PROGRESS.** Cuando el estado cambie a **CREATE\_COMPLETE,** podrá verificar su credencial en Cloudability. Es posible que tenga que actualizar la página CloudFormation en la interfaz de usuario para confirmarlo.

En Cloudability - Verificar la credencial de cuenta consolidada

Esto puede hacerse mediante acciones masivas o manualmente.

Verificación masiva a través de la interfaz de usuario: [AWS Verificación de credenciales mediante acciones masivas](aws-credentialing-bulk-actions.html)

Verificación manual a través de la interfaz de usuario:

1. Vaya a **Configuración** > **Credenciales de proveedor** > **AWS**.
2. Haga clic en el botón... situado junto a la cuenta cuyas credenciales desea verificar y seleccione Reverificar.
   - Una marca verde (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indica éxito, mientras que una exclamación roja (![](../../../../03-media/cloudability-premium/images/clip_image002_-1398377466.png)) indica errores.

Nota: Este proceso creará un nuevo rol llamado CloudabilityRole\_OU que Cloudability utilizará para verificar los permisos. Recomendamos utilizar código o automatización y el punto final de la API Cloudability cuando se disponga de un número considerable de cuentas vinculadas.

![aws](../../../../03-media/cloudability-premium/images/aws-linkedp.png)

Acreditación manual AWS Cuentas vinculadas

Esto sólo es aplicable si la opción anterior "Autentificación automática de cuentas vinculadas" **se dejó sin marcar** durante el proceso de Consolidación de credenciales de cuentas

En Cloudability - Navegue hasta Cuenta vinculada

- Vaya a **Configuración > Credenciales de proveedor > AWS**
- Haga clic con el cursor del ratón en el... de una cuenta vinculada **(no de gestión)**
- Seleccione el icono del lápiz para abrir el panel Editar una credencial.
- Añada AWS Región habilitada para SCP (Opcional):
- En el caso de que haya aplicado AWS Service Control Policy / políticas (SCP) que restringen el acceso en algunas regiones AWS, indique su región permitida; ejemplo us-east-2. En caso contrario, puede dejarse en blanco. Esto ayuda a Cloudability a realizar llamadas de verificación a la región permitida especificada.
- **Elige entre el reajuste avanzado en modo de solo lectura o **la automatización de acciones****
  - **La** opción «Solo lectura» implica que estás concediendo permisos de lectura para tu entorno, pero no para realizar acciones, tanto en Cloudability cost como en Turbonomic cost y Turbonomic.
  - La selección ****de «Automatizar acciones»**** implica que estás concediendo todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.

Si se selecciona la opción «Acreditación automática de cuentas vinculadas de AWS », la elección entre **«Solo lectura»** y ****«Automatizar acciones»**** en la cuenta vinculada se ajustará a la selección realizada en el nivel superior.

- Seleccione **Guardar**.
- Seleccione **Descargar**.

En AWS - Cargue la plantilla CloudFormation en la consola de gestión AWS

Complete los siguientes pasos para cargar la plantilla CloudFormation en la consola de gestión AWS como una pila. Esto tendrá que hacerse en cada cuenta vinculada.

1. En la **consola de gestión AWS**, trabajando en la cuenta vinculada que está acreditando, en la barra de búsqueda introduzca 'CloudFormation'
2. Selecciónalo.
3. En la página **AWS CloudFormation** página, seleccione **Crear pila (con nuevos recursos (estándar)**
4. En **Especificar plantilla**, haga lo siguiente:
   - Seleccione **Cargar un archivo de plantilla**
   - Seleccione **Elegir archivo** y cargue la plantilla que descargó de Cloudability.
   - Seleccione **Siguiente.**
5. En la página **Especificar detalles de pila**, haga lo siguiente:
   - Introduzca un **nombre para la pila** (por ejemplo, ' Cloudability ')
   - Verifique los **Parámetros** rellenados.
   - Seleccione **Siguiente**.
6. Desplácese por la página **Configurar opciones de pila** y marque la casilla "Reconozco que AWS Cloudformation puede crear recursos IAM con nombres personalizados" y haga clic en Siguiente
7. En la página **Revisar**, seleccione **Enviar**.

En Cloudability - Verificar las credenciales de la cuenta vinculada

Esto puede hacerse mediante acciones masivas o manualmente.

Verificación masiva a través de la interfaz de usuario: [AWS Verificación de credenciales mediante acciones masivas](aws-credentialing-bulk-actions.html)

Verificación manual a través de la interfaz de usuario:

1. Vaya a Configuración > Credenciales de proveedor y haga clic en... y seleccione Volver a verificar.

- Una marca verde (![../../resources/cldy_images/clip_image001_-1832790195.png](../../../../03-media/cloudability-premium/images/clip_image001_1499665667.png)) indica que se ha realizado correctamente, mientras que un signo de exclamación rojo (![../../resources/cldy_images/clip_image002_-821243953.png](../../../../03-media/cloudability-premium/images/clip_image002_-1577046812.png)) indica que hay errores que deben revisarse.
- Este proceso deberá repetirse para cada cuenta Vinculada una por una.

**Estado de las credenciales**

Cloudability La pantalla de credenciales del proveedor muestra el estado de la cuenta desde:

- Cloudability
- Turbonomic

Una vez ejecutadas las últimas plantillas, el estado de la cuenta debería estar sincronizado entre Cloudability y Turbonomic. Para obtener más información sobre el estado de la cuenta, consulte la sección de detalles de la cuenta.

![](../../../../03-media/cloudability-premium/images/TurboTarget.png)

**Tema principal:** [Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-premium-home.html)
