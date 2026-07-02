---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Plataforma API"
breadcrumb: []
source_path: "studio/admin/the-apptio-api.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_api.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Plataforma API

**Se aplica a** : TBM Studio 12.0 y posteriores

Nota: A partir de la versión 12.9, incluya los siguientes valores de cabecera en cualquier llamada a la API de la plataforma.

app-type="Flagship"

app-version="NA"

Esto incluye las llamadas a la API que cargan o descargan en Costing Standard o en otros proyectos de la plataforma. Estas cabeceras se suman a las cabeceras de API que ya pueda estar utilizando.

Apptio puede utilizarse para automatizar la carga de datos a proyectos de Apptio o la descarga de datos de proyectos de Apptio. Esta API se ofrece como alternativa al producto Apptio Datalink . Datalink (Classic) no requiere que el usuario tenga conocimientos especializados de scripting, y dispone de su propia API para facilitar la integración con herramientas ETL de terceros.

Algunas de las razones típicas por las que puede utilizarse la API de la plataforma Apptio en lugar de Datalink (Classic)son las siguientes:

- Imposibilidad de instalar un agente en Apptio Datalink (Classic) para cargar datos de fuentes locales
- El deseo de utilizar secuencias de comandos integradas en una herramienta ETL de terceros

La API Apptio proporciona un enlace directo entre los datos corporativos y Apptio a través de sencillos comandos. Los comandos describen cómo se contabilizan los datos en Apptio y cómo se extraen de Apptio, incluyendo dónde colocar los datos y el período de tiempo apropiado.

Por ejemplo, puede cargar datos mensuales o trimestrales de utilización de servidores o datos del libro mayor para asegurarse de que los informes están actualizados. También puede descargar datos de los conjuntos de datos y componentes de informes de Apptio.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_api.png)

Los comandos pueden integrarse en cualquier programador de tareas, añadirse a cualquier aplicación personalizable con unas pocas líneas de código o emitirse directamente desde una línea de comandos.

La sencillez y versatilidad de la API tiene muchas ventajas:

- Facilidad de implantación: no hay que instalar ningún programa
- Compatibilidad con todos los sistemas de datos corporativos y herramientas de extracción de datos
- Automatización mediante programadores de trabajo corporativos
- Versatilidad mediante opciones de implementación: programador de trabajos, integración de aplicaciones, línea de comandos

## Autenticación API

Para ejecutar una carga o descarga, el script debe autenticarse primero. Consulte [https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys "(se abre en una pestaña o una ventana nueva)") para obtener información sobre cómo autenticarse utilizando estos métodos. Aunque se pueden utilizar roles predefinidos, es posible que prefiera limitar el acceso de las cuentas a la acción específica que se está ejecutando. En este caso, los roles que se autentican deben tener los siguientes conjuntos de permisos mínimos para cargar y descargar:

- Permisos de carga:
- AccessDev
- UploadData
- Cargar datos

  Nota: Tenga en cuenta que los permisos “UploadData” y "Cargar datos" son permisos independientes. Asegúrese de incluir ambos.
- Permisos de descarga:
- AccessProd
- AccessStg
- DrillDown
- Ver Proactive
- AllDataView
- InteractiveBenchmarksAndCostData
- ViewMetricReports
- ViewObjectReports
- ViewReportsSavedForEveryone
- ViewTransformReports
- ViewTransparencyReports
- ViewUnitReports

Tenga en cuenta que algunos de los permisos "Ver" enumerados anteriormente podrían no ser necesarios en función de los productos que tenga instalados y del tipo de datos que esté descargando. En caso de duda, prueba.

**Ejemplos** :

Lea [la Licencia para ver ejemplos](../studio/apis/studio_license_examples.html "Se aplica a: v12.0, v12.1, v12.2+").

- [API URL para cargar una tabla](../studio/apis/studio_api_url_table.html "♦ Se aplica a: v11.x, v12.0, v12.1, v12.2+")
- [API URL ejemplos de carga](../studio/apis/studio_api_url_upload_examples.html "Se aplica a: v11.x, v12.0, v12.1, v12.2+")
- [API: Descarga de datos](../studio/apis/studio_api_download_data.html "Se aplica a: TBM Studio v11.x, v12.0, v12.1, v12.2 y posteriores")
- [API URL para cargar y editar datos de usuario en sistemas anteriores aEnhanced Access Administration](../studio/apis/studio_api_url_upload_edit.html "Se aplica a: v11.x, v12.0, v12.1")
- [Tutorial de la API: Descarga y carga de la tabla v.12 Costing Standard utilizando la herramienta Postman](../studio/apis/studio_tutorial.html)
- [Cómo acceder a la API R12 a través de Enhanced Access Administration mediante curl](../studio/apis/studio_access_api.html)
- [Apptio Scripts de demostración de la API](../studio/apis/studio_demo_scripts.html)
