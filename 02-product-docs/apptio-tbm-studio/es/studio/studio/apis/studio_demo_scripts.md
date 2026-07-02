---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Apptio Scripts de demostración de la API"
breadcrumb: []
source_path: "studio/studio/apis/studio_demo_scripts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Apptio Scripts de demostración de la API

## Introducción

Nota:

En la versión 12.9 y posteriores, incluya los siguientes valores de cabecera en cualquier llamada a la API de la plataforma.

app-type="Flagship"

app-version="NA"

Esto incluye las llamadas a la API que cargan o descargan en Costing Standard o en otros proyectos de la plataforma. Estas cabeceras se suman a las cabeceras de API que ya pueda estar utilizando.

Apptio admite tres API:

- La [API de la plataforma Apptio](../../admin/the-apptio-api.html "Se aplica a: TBM Studio 12.0 y posteriores")
- La [API Enhanced Access Administration](../../../frontdoor/home.html)
- La [API Datalink (Classic)](../../../datalink-classic/datalink/datalink_api_sample_scripts.html)

Este documento proporciona scripts de demostración de la API de la plataforma Apptio en uno o dos lenguajes de scripting de uso común, así como instrucciones sobre cómo configurar los scripts de demostración para las pruebas. También proporciona a los usuarios una orientación sobre la mecánica de uso de la API para que luego puedan aplicar lo aprendido a sus propias soluciones programadas.

Datalink (Classic) utiliza la API Apptio para transportar datos. La API Apptio también puede utilizarse de forma independiente para operaciones de carga o descarga de datos (por ejemplo, operaciones por lotes), que Datalink (Classic) no admite fácilmente. El uso de la API es más complejo y suele requerir conocimientos de programación o scripting para su implementación y mantenimiento. Por lo tanto, se recomienda utilizar Datalink (Classic) a menos que tenga necesidades y recursos avanzados para implementar y mantener la implementación de la API.

La API Apptio es distinta de la API Datalink (Classic) : La API Apptio se utiliza para cargar en las tablas de proyectos Apptio, o descargar de las tablas de proyectos Apptio (incluidas las de los informes), y es la que utiliza Datalink (Classic) bajo el capó. La API Datalink (Classic) se utiliza para automatizar la ejecución del conector del agente Datalink
(Classic) . Para obtener más información sobre la API Datalink
(Classic) , consulte [los scripts de ejemplo de la API Datalink](../../../datalink-classic/datalink/datalink_api_sample_scripts.html) .

El script adjunto a este artículo ha sido probado con las siguientes versiones específicas. No obstante, también debería funcionar con otras versiones:

- r11.8.3.5
- r12.3.2

## Operaciones básicas

El primer script de demostración se llama ApptioAPI\_Demo\_Basic\_v2.ps1. Está escrito en Windows PowerShell,, que está ampliamente disponible en los sistemas Windows, puede aprovechar las bibliotecas.NET y puede ser utilizado por software, como SQL Server Management Studio, para implementar la carga y extracción de SQL Server. Este tema se tratará con más detalle en futuras ediciones de este documento.

El script se adjunta y se comenta. El uso es el siguiente. Se muestra si el script se ejecuta sin argumentos:

Es necesario especificar -arriba o -abajo.

Utilización (mediante claves API):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

Utilización (mediante autenticación de nombre de usuario/contraseña):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

Es posible proporcionar combinaciones de los argumentos opcionales y ejecutar sin modificaciones. Sin embargo, si sólo desea utilizar los indicadores "-up" y "-down", puede editar el script para modificar las variables necesarias. A continuación se explican las variables, lo que contienen y lo que puede necesitar para su configuración.

## Argumentos de autenticación

Los siguientes argumentos admiten la autenticación con claves API. Este es el método preferido para su uso en entornos v12.

*-pubkey «xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx»*

Este argumento proporciona una clave pública API Key válida. Consulte [API de administración de acceso mejorado: Descripción general de las claves API y Preguntas frecuentes](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) para obtener más información sobre cómo obtener una clave pública.

*-secreto "xxxxxxxxxxxxxxxxxxxxxxxx"*

Este argumento proporciona una clave secreta API Key válida. Consulte [API de administración de acceso mejorado: Descripción general de las claves API y Preguntas frecuentes](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) para obtener más información sobre cómo obtener una clave pública.

*-envid «xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx»*

Este argumento proporciona un ID de entorno v12 válido. Consulte [API de administración de acceso mejorado: Actualizar la información de entorno de un usuario](../../../frontdoor/admin-guide/eaa-api/api-get-user-environment.html) para obtener información sobre cómo obtener este ID mediante la API. También puede solicitarlo a Apptio Support o a su CSM o CSE.

Los siguientes argumentos admiten la autenticación mediante nombre de usuario/contraseña. Esto es por compatibilidad con entornos r11 y no debe utilizarse en entornos v12.

*-usuario " user@domain.com " -pass "password"*

Estos argumentos especifican una cuenta de usuario que tiene acceso al proyecto que contiene los datos a descargar y la contraseña de dicha cuenta. Recuerde que si crea una cuenta nueva que admita esta opción, tendrá que editar la cuenta después de crearla para desmarcar la casilla de verificación **Contraseña de un solo uso**, o es posible que la API no responda.

## Descargar argumentos

*-APIURL "API válida URL "*

Este argumento especifica una API válida, entre comillas, Apptio URL. Esto se puede obtener de casi cualquier cosa en Apptio haciendo clic en el icono de exportación, que aparece de la siguiente manera:

![](../../../resources/images/studio_images/studioimages/studio%2028.png)

Este icono aparece en la pestaña r11 Data del estudio en asociación con cualquier vista de Tabla de transformación o Tabla sin procesar, o a través del botón Exportar de TBM Studio en r12 cuando se selecciona una tabla.

En los informes, puede acceder a ella haciendo clic con el botón derecho del ratón en la base de una tabla (por ejemplo, en el área de la fila de totales).

*-downtimeperiod " Apptio periodo de tiempo"*

Este argumento especifica un período de tiempo Apptio correctamente formateado del que descargar (por ejemplo, Aug:FY2016 ). Esto reemplazará cualquier periodo de tiempo que aparezca en la APIURL.

*[-downloadfolder "carpeta en la que descargar"]*

Este argumento especifica la carpeta para los datos descargados.

*[-filename "nombre de archivo"]*

Este argumento especifica el nombre del archivo en el que se descargarán los datos.

## Cargar argumentos

`[-v2]`

Este argumento especifica el uso de la API v2 URL para la carga. Esto es opcional y sólo es necesario en situaciones específicas.

`[-upfile "path to file to upload"]`

Este argumento especifica la ruta a un archivo que se va a cargar.

`[-apptiohost "https://domain-dev.apptio.com"]`

Este argumento especifica la instancia de host Apptio en la que reside el proyecto en el que se está cargando el archivo.

`[-domain "domain.apptio.com"]`

Este argumento especifica el dominio de su empresa.

`[-project "Project Name"]`

Este argumento especifica el nombre del proyecto en el que se cargará el archivo.

`[-table "Table Name"]`

Este argumento especifica el nombre de la tabla en la que deben cargarse los datos.

`[-uptimeperiod "Apptio time period"]`

Este argumento especifica un período de tiempo correctamente formateado Apptio en el que cargar (por ejemplo, Aug:FY2016 ).

`[-transformation overwrite | append]`

Este argumento especifica si la tabla debe sobrescribirse o anexarse.

## Descargar guiones de demostración

Haga clic [aquí](../../../resources/apptio_api_demo_scripts.zip) para descargar los scripts de demostración de la API Apptio.
