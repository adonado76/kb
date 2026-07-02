---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Integración de API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
source_path: "studio/new-uc/howtoguides/integrate-extend/api-integration.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Integración de API

**Tipo de contenido:** Colección de guías prácticas

**Destinatarios:** Desarrolladores, administradores técnicos

**Aplicable a:** TBM Studio 12.0 y versiones posteriores

**Requisitos previos:** credenciales de la API, conocimientos de programación y acceso a la red de TBM Studio

## Visión general

La API de la plataforma TBM Studio permite la automatización programática de la carga y descarga de datos. En esta sección se ofrecen guías prácticas para integrar sus sistemas con TBM Studio mediante la API REST, incluyendo la autenticación, las operaciones con datos y los patrones de gestión de errores listos para su implementación en producción.

La API establece una conexión directa entre los sistemas de datos de su empresa y TBM Studio mediante sencillos comandos de tipo « HTTP ». Puedes integrar estos comandos en programadores de tareas, herramientas ETL o aplicaciones personalizadas con una configuración mínima, sin necesidad de instalar software adicional.

Nota: Para la versión 12.9 y posteriores, incluye estos encabezados en todas las llamadas a la API: app-type="Flagship" y app-version="NA"

## Elegir el método de integración

TBM Studio ofrece múltiples opciones de integración. Utilice esta guía de decisión para seleccionar el método adecuado para su caso concreto.

|  |  |  |
| --- | --- | --- |
| **Método** | **Ideal para** | **Requiere** |
| API de la plataforma | Integraciones personalizadas, herramientas ETL de terceros, entornos en los que no se pueden instalar agentes locales | Conocimientos de programación, credenciales de API |
| DataLink (Clásico) | Carga de datos mediante el método «apuntar y hacer clic», usuarios sin conocimientos de programación | DataLink Instalación del agente, licencia de DataLink |
| Tablas publicadas | Exportación de datos de modelos a herramientas de BI externas ( Power BI, Tableau ) | TBM Studio 12.11.3 y superior, configuración de informes |

**Utiliza la API de la plataforma cuando:**

- No es posible instalar un agente local de « DataLink » para cargar datos desde fuentes locales
- Quieres utilizar scripts integrados en una herramienta ETL de terceros
- Debes automatizar la carga de datos mediante los programadores de tareas corporativos
- Necesitas un control programático sobre las operaciones con datos

**Utiliza las tablas publicadas cuando:**

- Debes exportar los datos calculados por el modelo a sistemas externos
- Quieres un esquema estable para su uso en herramientas de BI posteriores
- Necesitas una salida de datos controlada y regulada

Para obtener más información, consulta «[Autenticación de usuarios mediante API](https://community.ibm.com/community/user/viewdocument/user-authentication-using-apis?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)") ».

- **[Guía práctica: Autenticarse en la API](../../../../studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html)**
- **[Guía práctica: cómo subir datos a través de la API](../../../../studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html)**
- **[API](../../../../studio/admin/uploader-service-api.html)**  
   **del servicio Uploader. Aplicable a** : TBM Studio 12.0 y versiones posteriores
- **[Guía práctica: Descargar datos a través de la API](../../../../studio/new-uc/howtoguides/integrate-extend/download-data-api.html)**
- **[Guía práctica: cómo gestionar los errores de la API](../../../../studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html)**
- **[Referencia rápida](../../../../studio/new-uc/howtoguides/integrate-extend/quick-ref.html)**
