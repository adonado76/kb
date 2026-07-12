---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Exportar datos a través de la API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Exportación de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Exportar datos a través de la API

**Objetivo:** Recuperar datos de las tablas y los informes de TBM Studio mediante la API de la plataforma

**Cuándo utilizarlo:** cuando necesites un acceso flexible y bajo demanda a los datos de TBM Studio para integraciones personalizadas, procesos ETL o scripts de automatización

**Requisitos previos:**

- TBM Studio, versión 12.0 o posterior
- Credenciales de autenticación de la API (claves de API o credenciales de usuario)
- Permisos necesarios para descargar datos (permisos de AccessProd,, AccessStg,, DrillDown, y los permisos de visualización pertinentes)
- Conocimientos básicos sobre las solicitudes de tipo « HTTP » y tu lenguaje de programación preferido

**Tiempo estimado:** entre 20 y 30 minutos para la configuración inicial; varía en función del desarrollo de la integración

## Comprender la exportación basada en API

La API de TBM Studio Platform ofrece acceso directo y programático a tus datos sin necesidad de utilizar el producto « DataLink ». Entre los motivos más habituales para utilizar la API se incluyen:

- Integración de la recuperación de datos en herramientas ETL de terceros
- Creación de aplicaciones personalizadas que utilizan datos de TBM
- Automatización de la extracción de datos cuando no es posible instalar los agentes de « DataLink »
- Implementación de lógica condicional o flujos de trabajo complejos de recuperación de datos

## Paso 1: Configurar la autenticación

Antes de realizar llamadas a la API, configura tu autenticación. TBM Studio admite la autenticación mediante clave API (recomendada) y la autenticación mediante nombre de usuario y contraseña.

**Para la autenticación mediante clave API:**

1. En la administración de acceso mejorado, asegúrate de que tu cuenta de usuario tenga configuradas las claves API.
2. Anota los valores de tu **clave pública** y **tu clave secreta**.
3. Asegúrese de que se haya concedido acceso a la clave en el entorno adecuado.

**Permisos necesarios para descargar datos:**

Tu cuenta necesita estos permisos mínimos:

- AccessProd, AccessStg, DrillDown, Visita Proactive, AllDataView
- ViewMetricReports, ViewObjectReports, ViewTransformReports
- ViewTransparencyReports, ViewUnitReports, ViewReportsSavedForEveryone

Nota: Es posible que no se requieran todos los permisos de visualización, dependiendo de los datos que estés descargando. Prueba tu caso de uso concreto.

## Paso 2: Obtener un token de autenticación

Realiza una solicitud POST para obtener un token de acceso:

**Enlace:** https://frontdoor.apptio.com/service/apikeylogin

**Encabezados:**

Aceptar: application/json

Tipo de contenido: application/json

**Cuerpo:**

```
{"keyAccess": "your-public-key", "keySecret":
        "your-secret-key"}
```

**Respuesta:** La respuesta incluye una cookie «apptio-opentoken» que deberás utilizar en las solicitudes posteriores.

## Paso 3: Obtén tu ID de entorno

Si aún no conoces tu ID de entorno, obténlo mediante esta solicitud:

**Enlace:** https://frontdoor.apptio.com/api/environment/[yourdomain.com]/[yourfrontdoorenv ]

Sustituye [ yourdomain.com ] por tu dominio y [yourfrontdoorenv] por el nombre de tu entorno (normalmente «main»).

La respuesta incluye el valor del identificador de entorno que necesitarás para las solicitudes de datos.

## Paso 4: Descargar los datos de la tabla

Una vez completada la autenticación, puedes recuperar datos de las tablas.

**Descarga la API « URL » de TBM Studio:**

- Accede a la tabla en TBM Studio (tabla « Data Studio » o «Published Table»).
- Selecciona la pestaña **«Inicio»**, haz clic en **«Exportar»** y, a continuación, selecciona **«Mostrar API» URL**.
- Copia el archivo « URL » en el formato que prefieras (formato CSV, TSV o JSON).

**Encabezados para todas las solicitudes de descarga:**

Tipo de contenido: text/tab-separated-values (o application/json para JSON)

apptio-opentoken: [tu-token]

apptio-current-environment: [tu-id-de-entorno]

Tipo de aplicación: Insignia

versión de la aplicación: N/A

**Nota:** Los encabezados «app-type» y «app-version» son obligatorios para la versión 12.9 y posteriores de TBM Studio.

**Formatos de archivo compatibles:** CSV, TSV, CSV.GZ, TSV.GZ, XLS, XLSX

**Códigos de retorno y gestión de errores**

|  |  |
| --- | --- |
| **Código** | **Significado** |
| 200 | Correcto |
| 400 | Cadena de API incorrecta (comprueba el formato URL ) |
| 500 | Error interno del servidor (comprueba los permisos o la disponibilidad de los datos) |

## Errores habituales

**Faltan los encabezados obligatorios**

En la versión 12.9 y posteriores, si no se incluyen los encabezados «app-type» y «app-version», se producen errores de autenticación.

**Formato de fecha incorrecto**

Los periodos de tiempo deben seguir las convenciones de Apptio (por ejemplo, « January:2024 » o «actual» para el mes en curso).

**Caducidad de la señal**

Los tokens de autenticación caducan. Implementa la lógica de actualización de tokens en los procesos de larga duración.

**Errores de permisos**

Los errores de descarga suelen deberse a la falta de permisos. Comprueba que tu cuenta disponga del conjunto de permisos necesarios indicado en el paso 1.

## ¿Qué viene ahora?

- Para consultar la documentación completa de la API, incluidas las funciones de carga, véase la sección 5.5 (Referencia de la API)
- Para conocer los patrones de integración de « DataLink », consulta la [documentación](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=datalink "(se abre en una pestaña o una ventana nueva)") de « DataLink »
- Para configurar tablas publicadas para fuentes de datos de BI automatizadas, consulta [aquí](htg-config-pt.html).

**Tema principal:** [Exportación de datos](../../../../studio/new-uc/howtoguides/work-with-data/data-export.html)
