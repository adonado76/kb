---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Preguntas frecuentes para conectar con AWS"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conexión con AWS - Guía de integración de clientes"
source_path: "admin/aws-credentialing-premium-faq.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preguntas frecuentes para conectar con AWS

- **No veo ningún dato de costes después de completar los pasos de acreditación de cuentas, ¿qué hay que hacer?**
  - Verifique que los archivos de facturación correctos están en su cubo S3
  - Vaya a su cubo S3 que aparece en [la página AWS Facturación y gestión de costes](https://us-east-1.console.aws.amazon.com/costmanagement/home?region=us-east-1#/bcm-data-exports "(se abre en una pestaña o una ventana nueva)"), en Análisis de costes y uso - Exportación de datos. Una vez seleccionado, debería ver el prefijo que creó anteriormente, puede hacer clic en él y navegar por las exportaciones de facturación
  - Asegúrese de que ve archivos similares a los siguientes:
    - **<BillingReportName>.csv.gz**
    - **<BillingReportName>-Manifest.json**
  - Si no ve archivos como estos, entonces debe asegurarse de que su informe de Coste y Uso está habilitado para ID de recursos y etiquetas. Para obtener más información, consulte [Configurar credenciales de cuenta consolidadas](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-amazon-web-services#connectamazonwebservices__account_credentials "(se abre en una pestaña o una ventana nueva)").

- **Recientemente he activado el informe AWS Cost and Usage y me he acreditado en Cloudability. ¿Cuánto tardaré en ver los datos de Coste y Utilización?**

  El primer informe de costes y uso puede tardar hasta 24 horas en generarse en AWS. Para obtener más información, consulte: [https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting "(se abre en una pestaña o una ventana nueva)")

- **¿Puedo utilizar directamente la acreditación de cuentas vinculadas en lugar de la acreditación de cuentas consolidadas?**

  Cloudability sólo admite la facturación consolidada y no la facturación a nivel de cuenta vinculada. **El acceso a la facturación** programática se transfiere a la cuenta consolidada, por lo que las cuentas vinculadas no reciben los archivos necesarios en el cubo S3. Debe añadir la cuenta consolidada con el **acceso a facturación programática** activado a Cloudability.

- **¿Cómo actualizo a la última plantilla CloudFormation?**

  Esto puede hacerse utilizando Cloudability Manage AWS credenciales

  - Mantenga actualizadas sus credenciales de AWS en Cloudability con las siguientes instrucciones.
  - **Regenerar una plantilla de formación de nubes**
  - Para regenerar la plantilla de Cloud Formation para reconfigurar su acceso a AWS, haga lo siguiente:
  - En Cloudability, vaya a **Configuración > Credenciales de proveedor > AWS**.**Nota:** La página **Credenciales de vendedor** requiere permisos de administrador para acceder a ella.
  - Guarde y descargue la plantilla actual CloudFormation
  - En AWS navegue hasta CloudFormation à Stacks
  - Averigüe qué pila ha ejecutado previamente para instalar la plantilla Cloudability CloudFormation anterior.
  - Seleccione la misma pila y pulse el botón **actualizar pila**
  - Seleccione ' **hacer una actualización directa** ', seleccione reemplazar plantilla existente y cargue un archivo de plantilla. Cargue el nuevo archivo de plantilla CloudFormation.
  - Si la actualización se realiza correctamente, vuelva a verificar la cuenta.

- A continuación le indicamos cómo actualizar a la última versión todas las cuentas de pagadores y cuentas vinculadas de su organización.
  - Cuentas consolidadas (necesitan acceso a S3 bucket): consulte Configurar credenciales de cuentas consolidadas
  - Cuentas vinculadas (no necesitan acceso a S3 bucket): consulte Configurar el acceso a AWS API

- **¿** **Qué formatos son compatibles con los archivos AWS CUR?**

  Cloudability admite AWS Legacy CUR y CUR 2.0 en ambos formatos.

  - gzip - texto/csv
  - Parqué - Parqué
- **¿Cómo cambiar de CUR heredado a CUR 2.0?**

  Esto puede lograrse de dos maneras:

- **Opción 1: Crear el CUR 2.0 exportar igual que el CUR heredado**
  - La forma más sencilla es crear una exportación CUR 2.0 en el mismo cubo con el mismo nombre de exportación y el mismo prefijo de exportación que el CUR heredado. Si se elige esta opción, no es necesario realizar ningún paso adicional en Cloudability UI. En la siguiente extracción de datos Cloudability empezará a leer automáticamente de CUR 2.0.
- **Opción 2:** **Crear un nuevo CUR 2.0 y actualizar las credenciales**
  - **En AWS :**
    - Cree una nueva exportación CUR 2.0 en AWS Gestión Facturación con un nuevo nombre.
    - Utilice el mismo bucket (que se utilizó para el CUR heredado) para la exportación o cree uno nuevo.
    - Cree la exportación siguiendo los pasos anteriores en la credencialización de cuentas consolidadas.
  - **En Cloudability :**
    - Seleccione la cuenta consolidada para la que se ha configurado CUR 2.0.
    - Haga clic en Editar:
    - Actualice el nombre del cubo S3 (si es nuevo)
    - Actualizar el nombre del informe de costes y utilización (si es nuevo)
    - Actualizar el prefijo de coste y uso. (si es nuevo)
    - Descargue la plantilla de formación en nube (CFT).

    Nota: Esto solo es necesario si creas un nuevo depósito. Si no ha creado un nuevo cubo omita la descarga de CFT, haga clic en Guardar y verificar credenciales.
  - **En AWS :**
    - Cargue y ejecute el CFT como una pila.
  - **En Cloudability**
    - Seleccione la misma cuenta consolidada
    - Haga clic en Editar
    - Pulse Guardar
    - Verificar credencialUna vez que haya cambiado de CUR heredado a CUR 2.0, tendrá que reconfigurar las etiquetas en Cloudability.

    Nota: «Cloudability » busca el archivo de manifiesto en la siguiente ubicación:

    **CUR heredado** - <Prefijo del informe de costes y utilización>/<Nombre del informe de costes y utilización>/YYYYMMDD-YYYYMMDD/<Nombre del informe de costes y utilización> -Manifest.json

    **CUR 2.0** - <Prefijo del informe de costes y uso>/<Nombre del informe de costes y uso>/metadatos/BILLING\_PERIOD=YYYY-MM/<Nombre del informe de costes y uso> -Manifest.json

    La exportación de datos que cree según los pasos de cloudability cargará por defecto los datos en la ubicación anterior. Si se obtiene algún dato histórico, cloudability espera los archivos de manifiesto en la ubicación anterior.

- **¿Admite « Cloudability » archivos CUR personalizados?**

  No, no admitimos archivos CUR personalizados; modificar los archivos CUR puede tener diversas repercusiones en el sistema, dependiendo del cambio que se realice.
- **¿Podemos introducir datos de costes históricos en Cloudability? En caso afirmativo, ¿hasta qué punto se pueden retroceder los datos?**  **¿ingerido?**

  Sí que podemos. Consulte a los equipos de asistencia de IBM Cloudability para saber cómo introducir datos históricos.

- **¿ Cloudability admite el cifrado en los depósitos de S3?**

  Sí, los clientes pueden configurar el cifrado del lado del servidor con claves administradas de Amazon S3 ( SSE-S3 ) en sus depósitos de S3. Cloudability No admite el cifrado mediante KMS ni claves de cifrado proporcionadas por el cliente.
- **¿Qué pasaría si no se actualizaran los permisos de Turbonomic?**

  En caso de que no haya vuelto a acreditar cuentas en Cloudability una vez que haya actualizado a Cloudability Premium entonces:

- **Cloudability**
  - AWS la función de ingestión y optimización de datos de facturación seguirá funcionando.
  - El cuadro de diálogo Automatizar acciones se mostrará en OFF.
  - En la pestaña «Detalles», en «Cuenta consolidada» O «Cuentas vinculadas», todos los permisos específicos de Turbonomic aparecerán marcados con una X ROJA.
- **Turbonomic**
  - Turbonomic no funcionaría debido a la falta de permisos; habría problemas con los destinos en TurbonomicUna vez que los nuevos permisos están habilitados utilizando el CFT con sólo lectura que luego se añade a AWS consola y cuenta (s) se verifica:

- **Cloudability**
  - Las acciones de **Automatizar** seguirán apareciendo como **DESACTIVADAS**.
  - En la pestaña **Detalles**, los permisos Turbo para Coste, facturación y ejecución de facturación aparecerán con una marca de verificación verde.
- **Turbonomic**
  - Turbonomic funcionaría con permisos de **solo lectura**.Una vez que los nuevos permisos están habilitados utilizando el CFT con los recursos **Optimizar** en AWS consola y la cuenta (s) se verifica:

- **Cloudability**
  - Las **acciones Automatizar** se marcarán como **ON**.
  - En la pestaña **Detalles**, todos los permisos aparecen con una marca de verificación verde.
- Turbonomic
  - Turbonomic empezaría a funcionar en función de los permisos **de «Optimizar recursos** ».

    Nota: La **activación** o **desactivación** de acciones automáticas se muestra en la interfaz de usuario de credenciales del proveedor en función de la selección en el interruptor y la descarga de la plantilla.
- **¿El estado de la cuenta Cloudability y el estado del destinatario Turbonomic no coinciden en las pantallas de credenciales de proveedores? ¿Cuáles podrían ser las razones?**

  Los clientes actuales de « Cloudability » que actualicen a « Cloudability Premium » deberán volver a autenticar sus cuentas para obtener los permisos más recientes de « Turbonomic ».

  El desajuste en el estado de la cuenta puede deberse a varias razones:
  - La recertificación no se realizó basándose en las últimas plantillas/permisos.
  - Si se realizó la recertificación, es posible que se hiciera utilizando una versión anterior de la plantilla y, desde entonces, se han añadido algunos permisos nuevos para Cloudability Premium.
  - Si la recertificación no ayuda, póngase en contacto con los equipos IBM de asistencia.

  **¿Se puede utilizar el formato FOCUS en lugar de CUR para la integración si AWS Data?**

  Cloudability admite tanto FOCUS como AWS CUR. Sin embargo, para los datos de AWS recomendamos utilizar el archivo CUR.
- **¿Dónde puedo encontrar Cloudability 's Vendor Credentials APIs for AWS**

  [Punto final de credenciales de vendedor ( AWS )](../api-v3/vendor_credentials_end_point_1.html)
- **¿** **Dónde puedo encontrar los diferentes iconos que aparecen en las descripciones del estado de las cuentas?**

  [Indicadores de estado de las credenciales de los proveedores](vendor-credentials.html)

**Tema principal:** [Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-premium-home.html)
