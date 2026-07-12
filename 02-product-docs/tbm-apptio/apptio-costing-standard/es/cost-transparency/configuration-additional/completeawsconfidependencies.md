---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Complete AWS Dependencias de configuración"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/completeawsconfidependencies.html"
images:
  - "resources/images/ct_images/7848_1.png"
  - "resources/images/ct_images/7848_2.png"
  - "resources/images/ct_images/7848_3.png"
  - "resources/images/ct_images/7848_4.png"
  - "resources/images/ct_images/7848_5.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Complete AWS Dependencias de configuración

- Se aplica a: Apptio Costing Standard o Apptio Cloud Cost Management en TBM Studio 12.3.3 y posteriores

Complete los siguientes pasos para las dependencias de configuración de Amazon Web Services ( AWS ).

## Crear un cubo S3

Para crear un cubo S3, siga estos pasos:

1. Inicie sesión en la consola de gestión AWS para la cuenta con la que desea realizar la integración.
2. En el menú Servicios, vaya a la consola Amazon S3.
3. Seleccione **Crear cubo**.
4. Escriba un nombre para el cubo y seleccione una región donde residirá el cubo.
5. Haga clic en **Crear**.

Para establecer permisos para el cubo, siga estos pasos:

1. En la consola de gestión AWS, vaya a Mi panel de facturación.
2. Seleccione **Preferencias**.
3. En Recibir informes de facturación, escriba el nombre del cubo S3 y seleccione **Política de muestra**.
4. Copie la política.
5. Vaya a la consola Amazon S3 y seleccione el cubo que ha creado.
6. Haga clic en **Propiedades**, **Permisos** y, a continuación, seleccione **Añadir política de cubos**.
7. Pegue la política que ha copiado y, a continuación, haga clic en **Guardar**.

## Habilitar informes de facturación (Asignación de costes)

Para activar todas las opciones de Recibir Facturación:

1. En la consola de gestión AWS, vaya a Mi panel de facturación y seleccione **Preferencias**.
2. En Recibir informes de facturación, asegúrese de que el nombre de su depósito S3 aparezca en **Guardar en depósito S3**.
3. Habilite todas las opciones de informes de facturación seleccionando las siguientes casillas: Informe mensual, Informe detallado de facturación, Informe de imputación de costes e Informe detallado de facturación con recursos y etiquetas.
4. Haga clic en **Guardar preferencias**.

## Habilitar etiquetas para los informes de facturación

Para activar todas las etiquetas en sus informes de facturación:

1. En la consola de gestión AWS, vaya a Mi panel de facturación.
2. Seleccione **Etiquetas de imputación de costes**.
3. Habilite todas las etiquetas que utilizará para analizar sus gastos.

DataLink puede autenticarse con AWS para obtener permisos de acceso a las fuentes de datos de AWS.

**Delegación** - DataLink asumirá un Rol IAM AWS que su organización ha creado para obtener permisos temporales para acceder a sus datos AWS. Recomendamos este enfoque desde el punto de vista de la seguridad.

## Delegación

1. Dentro del nuevo conector DataLink AWS, seleccione **Usar delegación dentro de la sección Credenciales AWS**, luego copie la cadena completa en el campo **ID externo**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_1.png)
2. Si aún no se han creado políticas de seguridad, en su entorno AWS, cree las políticas de seguridad de IAM que se adjuntarán al rol de IAM. Esto se configurará en AWS y será asumido por el conector AWS. Consulte la sección [Políticas](#completeawsconfidependencies__Securitypolicies) de seguridad para conocer las políticas específicas que debe crear.
3. En su consola AWS, navegue hasta el servicio IAM y cree un nuevo rol IAM.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_2.png)
4. Especifique un nombre de rol. Este nombre de rol se introducirá en el conector DataLink AWS, así que cree un nombre que sea DataLink-specific.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_3.png)
5. A continuación, especifique el tipo de rol:

   Seleccione la **función para el acceso entre cuentas**. A continuación, elija **Proporcionar acceso entre su cuenta AWS y una cuenta AWS de terceros**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_4.png)
6. Introduzca el identificador de la cuenta Apptio Datalink (Classic) (007579627371) y el identificador externo (disponible en el conector AWS - véase el paso 1 anterior).

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_5.png)
7. Adjunte las políticas apropiadas (creadas en el paso 2 anterior) al rol.
8. En el nuevo conector DataLink AWS, introduzca el ID de cuenta de su cuenta AWS y el nombre del rol que acaba de crear.

## Políticas de seguridad

Esto creará una política que permitirá al titular (un usuario, grupo o, en nuestro caso, un rol) leer elementos del bucket especificado. Sustituya "mi-cubo" por el nombre del cubo al que desea acceder en DataLink.

S3
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Sid": "Stmt1468715091000", "Effect": "Allow", "Action": [ "s3:GetBucketLocation", "s3:GetObject", "s3:ListBucket" ], "Resource": [ "arn:aws:s3:::my-bucket" ] }, { "Effect": "Allow", "Action": [ "s3:GetObject" ], "Resource": [ "arn:aws:s3:::my-bucket/*" ] } ] }
    ```

Describa EC2 instancias reservadas
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Sid": "Stmt1431460354000", "Effect": "Allow", "Action": [ "ec2:DescribeReservedInstances", "ec2:DescribeReservedInstancesListings", "ec2:DescribeReservedInstancesModifications", "ec2:DescribeReservedInstancesOfferings" ], "Resource": [ "*" ] } ] }
    ```

Describa RDS instancias reservadas
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Action": [ "rds:DescribeReserved*", "rds:ListTagsForResource" ], "Effect": "Allow", "Resource": "*" } ] }
    ```

Describir los controles de los asesores de confianza
:   Esta política es proporcionada por AWS por defecto: AWSSupportAccess

    ```
    { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": ["support:*" ], "Resource": "*" } ] }
    ```

Para obtener más información sobre cómo crear un rol en Amazon Web Services, consulte [Creación de roles IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create.html "(se abre en una pestaña o una ventana nueva)").
