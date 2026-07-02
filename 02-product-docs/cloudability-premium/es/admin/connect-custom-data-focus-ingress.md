---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar datos personalizados (FOCUS Ingress)"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-custom-data-focus-ingress.html"
images:
  - "images/focus.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar datos personalizados (FOCUS Ingress)

FinOps Open Cost and Usage Specification ( FOCUS) es un esfuerzo impulsado por la comunidad para desarrollar un esquema estándar para datos de facturación en la nube, SaaS, y otros. El objetivo principal de la especificación FOCUS es facilitar la comprensión, información y gestión de los costes de la nube. La especificación de FOCUS pretende ser adaptable a una variedad de proveedores de servicios en la nube y fuentes de productos SaaS y define columnas (dimensiones y métricas), requisitos específicos de las columnas y atributos (requisitos de toda la especificación).

Puede traer cualquier dato de coste y uso de fuentes de datos adicionales siempre que se haya formateado en el esquema de FOCUS y se adhiera a las columnas que se requieren, según lo definido por la especificación.

Nota:

- No recomendamos utilizar FOCUS para los datos de CSP, ya que el conjunto de datos de costes actual al que Cloudability tiene acceso de forma nativa (CUR/ Azure exports/ GCP Billing, etc.) es mucho más detallado que el conjunto de datos de FOCUS. Con FOCUS sólo obtenemos datos de costes, mientras que las actuales integraciones CSP también aportan datos de utilización que se utilizan en múltiples casos de optimización.
- Si ya ha autenticado su(s) cuenta(s) de CSP a través del conector nativo, no utilice la misma cuenta para conectarse a través del conector FOCUS.
- Para garantizar una compatibilidad y un soporte técnicos óptimos, siga los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tienes alguna pregunta, ponte en contacto con **el servicio de asistencia** de IBM.

Las especificaciones de FOCUS se pueden [consultar aquí,](https://focus.finops.org/ "(se abre en una pestaña o una ventana nueva)") y las columnas específicas[, además, aquí](https://focus.finops.org/focus-columns/ "(se abre en una pestaña o una ventana nueva)").

Cloudability actualmente admite

1. Versión FOCUS 1.0
2. Versión FOCUS 1.1

Nota: La opción de acreditación «Datos personalizados» no debe utilizarse para los CSP que ya admitimos de forma nativa (por ejemplo, AWS, Azure, etc.), ya que algunas funciones, como la redimensión, no serán compatibles.

Pasos para la integración

![captura de pantalla de entrada de datos personalizada](../../../../03-media/cloudability-premium/images/focus.jpg)

Gestión de fuentes de datos

Todos los datos que se carguen en cualquiera de los servicios de almacenamiento deben ser los del mes completo hasta la fecha.

Además, los datos deben seguir una estructura específica como:

`<Root
Directory>/<Optional_Sub_Directories>/<Vendor>/<Report_Period>/<Epoch Time
Folder>/<prefix>-Manifest.json`

La M de Manifiesto debe ir siempre en mayúsculas.

- Directorio raíz : Un prefijo como AWS bucket name, Azure container name o GCS bucket name
- Subdirectorios opcionales : Un campo opcional para el cliente. Pueden tener o no subdirectorios adicionales
- Proveedor : Un nombre de proveedor que ayude a identificar el tipo de proveedor
- Período del informe : Período del informe para el que están disponibles los datos. Debe estar en los formatos AAAAMMDD-AAAAMM(+1)DD. Por ejemplo, para el periodo de informe 2023-02, el nombre sería →20230201-20230301.
- Epoch Time Folder : Se utilizará para identificar la última caída de los datos del mes hasta la fecha.
- Manifiesto : Archivo json de metadatos que contiene detalles del conjunto de datos de un periodo de informe específico.

Todas las fuentes de datos personalizadas a través de esta función deben cumplir las especificaciones de FOCUS.

Ejemplo de archivo de manifiesto

```
{
		"compression": "GZIP",
		"content_type": "Parquet",
		"report_id": "uuid-f431e214843b3c19756368",
		"root_dir": "byod-input-prod",
		"all_report_keys": [
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00001.snappy.parquet",
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00002.snappy.parquet"
		],
		"updated_at": "2024-04-04T05:00:22Z",
		"focus_version": "1.0"
	}
```

Tipo de contenido del archivo : JSON

| Cabecera / Campo | Cabecera / Definición de campos | Valor : Obligatorio / Opcional |
| --- | --- | --- |
| compresión | CSV : gzip  Parquet : Todos los soportados por los frameworks Java Hadoop. | Opcional |
| Tipo de contenido | Parquet o CSV | Obligatorio |
| iD del informe | Identificador único de informe generado aleatoriamente. | Opcional |
| directorio\_raiz | S3 Bucket o Azure Directorio o bucket GCS del que obtener el informe. Esto dependerá del tipo de credenciales elegidas. | Obligatorio |
| todas las claves de informe | Es un JSON anidado, es decir, la lista de sólo nuevas rutas absolutas de archivos excluyendo el directorio raíz. | Obligatorio |
| actualizado en | Última hora de actualización del informe. | Opcional |
| versión focus | Versión de FOCUS según [https://finops.dev/focus-spec](https://finops.dev/focus-spec "(se abre en una pestaña o una ventana nueva)") La versión debe coincidir exactamente con la versión especificada en las especificaciones de FOCUS. por ejemplo, 1.0 o 1.1 | Obligatorio |

Pasos de la integración

Nota: Una vez completado el proceso de acreditación en Cloudability (tal y como se describe a continuación), aparecerá una marca de verificación verde junto a los datos de tu acreditación, pero Cloudability deberá comprobar que el archivo de facturación y el archivo de manifiesto se ajustan a los formatos solicitados. Si al cabo de 24 horas no ves ningún dato en Cloudability, ponte en contacto con el equipo de asistencia de Apptio.

Admitimos AWS Simple Storage Service, Google Cloud Storage y Azure Blob Storage como servicios de almacenamiento para alojar datos alineados con FOCUS.

Para añadir credenciales para datos personalizados en Cloudability, siga los pasos que se indican a continuación:

1. En Cloudability, vaya a Configuración > Credenciales de proveedor > Añadir fuente de datos > Otras fuentes de datos.
2. Seleccione Otros orígenes de datos > Añadir una credencial > Se abrirá el panel Añadir cuenta de otros orígenes de datos, haga clic en **Siguiente**.
3. Haga clic en Proveedor de almacenamiento preferido y siga las instrucciones.

AWS Servicio de almacenamiento simple

1. Indique el proveedor para el que deben ingestarse los datos.
2. Introduzca **el ID de la cuenta AWS correspondiente donde se encuentran los archivos**.
3. Introduzca el nombre del depósito « AWS S3 » en «Root Directory » (Directorio raíz).
4. Introduzca subprefijos opcionales en Subdirectorios.
5. Introduzca el prefijo del manifiesto en Prefijo del manifiesto.
6. Haga clic en Generar plantilla.

Para más información, consulta la [página Amazon Web Services](aws-credentialing-standard-enterprise-home.html).

Azure Blob Storage 

1. Introduzca el proveedor para el que se deben ingestar los datos.
2. Introduce el ID de la cuenta de facturación de Azure donde se encuentran los archivos.
3. Introduzca el ID de inquilino.
4. Introduzca el ID de suscripción.
5. Introduzca el nombre del grupo de recursos.
6. Introduzca el nombre de la cuenta de almacenamiento.
7. Introduzca el nombre del contenedor Blob en Directorio raíz.
8. Introduzca los subdirectorios opcionales en Subdirectorios.
9. Introduzca el prefijo del manifiesto en Prefijo del manifiesto.
10. Haga clic en Generar plantilla.

Para más información, consulta la [página Microsoft Azure](azure-cm-setup.html).

Google Cloud Storage Servicio de almacenamiento simple

1. Introduzca el proveedor para el que se deben ingestar los datos.
2. Introduce el ID de la cuenta **de facturación de** GCP donde se encuentran los archivos.
3. Introduzca el nombre del bucket de GCS de GCP en Directorio raíz.
4. Introduzca subprefijos opcionales en Subdirectorios.
5. Introduzca el prefijo del manifiesto en Prefijo del manifiesto.
6. Haga clic en Generar plantilla.

Para más información, consulta la [página Google Cloud](connect-google-cloud.html).

**Preguntas más frecuentes** :

- **¿Puedo utilizar el formato FOCUS para importar datos CSP para AWS, Azure, GCP y OCI?**No recomendamos utilizar FOCUS para los datos CSP, ya que el conjunto de datos de costes actuales que Cloudability obtiene de forma nativa (CUR/ Azure exports etc) es mucho más granular que el conjunto de datos FOCUS. Con FOCUS sólo obtenemos datos de costes, mientras que las actuales integraciones CSP también aportan datos de utilización que se utilizan en múltiples casos de optimización.

- **¿Cuáles son las ventajas de utilizar FOCUS para los datos CSP?**FOCUS puede utilizarse para los conjuntos de datos CSP de regiones o proveedores que no admitimos de forma nativa en Cloudability. E.g.
  - AWS China
  - Ali Nube
  - Cualquier otra nube pública que Cloudability no admita de forma nativa
- **Si aporto datos de otras regiones o proveedores, ¿cuáles son los requisitos previos?**
  - Los datos de FOCUS deben alojarse en un bucket fuera de la región que Cloudability no admite, por ejemplo, no en China, sino en EE.UU., la UE o la UA.
  - Asegúrese de que, al solicitar las credenciales, facilita **los datos de la cuenta en la que están alojados los archivos de exportación de costes.**
  - Los archivos parquet sólo deben comprimirse mientras se generan (usando las técnicas de compresión por defecto de hadoop, avro) y no comprimirse explícitamente.
  - El archivo FOCUS manifest.JSON debe tener las "claves de informe" correctas que especifiquen los archivos de informe exactos a recuperar, incluidas las extensiones de archivo correctas.
