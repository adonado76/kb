---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia rápida"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/quick-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia rápida

## Encabezados obligatorios para todas las llamadas a la API ( v12.9+ )

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Finalidad** |
| apptio-opentoken | Tu token de autenticación | Autenticación |
| apptio-entorno-actual | ID de entorno | Entorno de destino |
| tipo de aplicación | Buque insignia | Requisitos para v12.9+ |
| versión de la aplicación | N/D | Requisitos para v12.9+ |
| Tipo de contenido | Varía según la operación | Formato del cuerpo de la solicitud |

## Formatos de archivo compatibles

|  |  |  |
| --- | --- | --- |
| **Formato** | **Extensión** | **Notas** |
| CSV | .csv | Valores separados por comas |
| TSV | .tsv | Valores separados por tabulaciones |
| CSV comprimido | .csv.gz | CSV comprimido con Gzip |
| TSV comprimido | .tsv.gz | TSV comprimido con Gzip |
| Excel | .xlsx | Solo descarga |

## Documentación relacionada

- Referencia de la API de Section 5.5 : documentación completa de los puntos de conexión, detalles de los parámetros y esquemas de respuesta
- [Importación y gestión de datos](../work-with-data/data-import-mgmt.html) : procedimientos de carga manual de datos y configuración de DataLink
- [Gestión de usuarios](../manage-users-permission/manage-up-intro.html) : configuración de cuentas de usuario de la API y asignación de permisos
- [Modelo de seguridad](../../concepts-architecture/studio-model/security-architecture.html) : arquitectura de autenticación y mejores prácticas de seguridad

**Tema principal:** [Integración de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
