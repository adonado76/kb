---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar Pagerduty"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-pagerduty.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Pagerduty

La siguiente información te ayudará a conectar tus servicios de Pagerduty con Cloudability.

Pasos para la integración

Pagerduty

1. En el menú «Configuración», selecciona «Servicios ».
2. Si vas a crear un nuevo servicio para tu integración, en la página «Servicios», selecciona «Añadir nuevo servicio ».
3. Si vas a añadir tu integración a un servicio ya existente, en la página «Servicios», selecciona el nombre del servicio al que deseas añadir la integración. A continuación, selecciona la pestaña «Integraciones» y haz clic en «Nueva integración ».
4. En el menú «Tipo de integración », selecciona « Cloudability » y rellena el campo «Nombre de la integración ».
5. Si vas a crear un nuevo servicio para tu integración, en Configuración general, introduce un nombre para tu nuevo servicio en el campo Nombre. A continuación, en «Configuración de incidencias », especifica la «Política de escalado », la «Urgencia de la notificación » y el «Comportamiento de la incidencia » para tu nuevo servicio.
6. Selecciona «Añadir servicio » o «Añadir integración » para guardar tu nueva integración. Se te redirigirá a la página «Integraciones» de tu servicio.
7. Copia la clave de integración de tu nueva integración. Esto se utilizará en el procedimiento siguiente.

Cloudability 

1. En Cloudability, ve a Configuración > Credenciales de proveedor > Añadir fuente de datos > PagerDuty. Se abre el panel «Añadir una cuenta de PagerDuty ».

   O

   En Cloudability, ve a «Configuración» > «Credenciales de proveedor » > « PagerDuty ». Selecciona «Añadir un nuevo servicio ». Se abre el panel «Añadir un nuevo servicio »
2. Introduce los datos en los campos «Nombre de la integración» y «Clave de integración ».

Ya estás listo para utilizar Pagerduty en las áreas compatibles de la aplicación « Cloudability ». Por ejemplo, puedes configurar que las alertas sobre anomalías se envíen a PagerDuty:

1. Accede a la página «Detección de anomalías ».
2. Selecciona ALERTAS y configura los ajustes de las alertas de PagerDuty.

Resolución de problemas

¿Qué puede hacer Cloudability con mi clave de integración en Pagerduty?

Los integramos con v2 de la API de eventos de Pagerduty. La API de eventos v2 es una API asíncrona de gran fiabilidad y alta disponibilidad que recoge eventos de herramientas de monitorización. Los eventos enviados a esta API se redirigen a un servicio de Pagerduty y se procesan. Pueden dar lugar a la creación de una nueva alerta o incidente, o a la actualización o resolución de uno ya existente. Anteriormente, la API de eventos también se utilizaba para integrar Pagerduty con sistemas de gestión de incidencias y otras herramientas de software diversas. Hoy recomendamos utilizar la API sincrónica de incidentes para integrar sistemas de gestión de incidencias u otros sistemas de registro con Pagerduty

Por lo tanto, las claves de integración solo permiten enviar alertas a un servicio.
