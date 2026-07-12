---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de la suscripción por correo electrónico"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/email-sub-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de la suscripción por correo electrónico

Las suscripciones por correo electrónico permiten distribuir automáticamente los informes a los usuarios según un calendario programado.

**Configuración de la suscripción**

|  |  |
| --- | --- |
| **Valor** | **Descripción** |
| Nombre de suscripción | Se rellena automáticamente como <Colección de informes - Nombre del informe>. Se puede personalizar. |
| Destinatarios | Direcciones de correo electrónico de los usuarios que recibirán la suscripción. Deben ser direcciones de correo electrónico válidas de dominios autorizados. |
| Período de referencia | El «Período actual» se refiere al período en el que está activa la suscripción. También se puede especificar un periodo fijo. |
| Incluir el PDF como archivo adjunto | Adjunta una versión en PDF del informe al correo electrónico |
| Vistas filtradas | Permite enviar informes con selecciones de segmentador ya aplicadas |
| Carga masiva de archivos XLS | Permite la distribución masiva con vistas filtradas específicas para cada destinatario |

***Nota de seguridad:*** *Los correos electrónicos solo se pueden enviar a dominios autorizados configurados en el entorno del cliente. La seguridad a nivel de fila (RLS) no se aplica a las suscripciones por correo electrónico.*

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
