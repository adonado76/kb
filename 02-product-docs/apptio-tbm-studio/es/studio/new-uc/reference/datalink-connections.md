---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DataLink Conexiones"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
source_path: "studio/new-uc/reference/datalink-connections.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DataLink Conexiones

## DataLink Resumen

DataLink proporciona conectividad entre TBM Studio y sistemas externos, tanto para la entrada (importación) como para la salida (exportación) de datos.

**Tipos de conexión:**

|  |  |  |
| --- | --- | --- |
| **Tipo** | **Dirección** | **Descripción** |
| Ingress | Externo a TBM Studio | Importar datos desde sistemas externos |
| Salida | De TBM Studio a un dispositivo externo | Exportar datos a sistemas externos |

## ServiceNow Integración

**Objetivo:** Enviar los datos sobre el coste total de propiedad (TCO) a ServiceNow

**Versiones compatibles de « ServiceNow »:** Quebec, París, Orlando

**Pasos de configuración:**

1. Instalar la aplicación «Apps & Services TCO» en la plataforma « ServiceNow »
2. Configurar informes de TCO en TBM Studio

1. Configurar un conector de salida de DataLink

**Opciones de autenticación:**

|  |  |  |
| --- | --- | --- |
| **Tipo** | **Asistencia para agentes** | **Notas** |
| Básica | En la nube y en las instalaciones | Nombre de usuario y contraseña |
| OAuth 2.0 | Solo en la nube | Se requiere el ID de cliente y el secreto de ServiceNow |

**Tema principal:** [Referencia de « Data Studio »](../../../studio/new-uc/reference/data-studio-reference.html)
