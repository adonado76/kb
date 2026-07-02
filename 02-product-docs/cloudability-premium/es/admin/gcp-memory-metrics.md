---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Configurar un agente de supervisión de GCP para el redimensionamiento"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/gcp-memory-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar un agente de supervisión de GCP para el redimensionamiento

Para que Cloudability pueda utilizar métricas de uso adicionales, como la memoria, deberá configurar el agente de supervisión de GCP. Cloudability es compatible tanto con el agente Ops como con el agente de monitorización heredado. Las siguientes instrucciones detallan cómo configurar cada agente:

1. Requisitos previos

   Para instalar el agente, asegúrate de que se cumplan todas las condiciones.

   [Instalación del Ops Agent en máquinas virtuales individuales](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(se abre en una pestaña o una ventana nueva)")

   [Instalación del agente Legacy Cloud Monitoring en máquinas virtuales individuales](https://cloud.google.com/monitoring/agent/monitoring/installation#before_you_begin "(se abre en una pestaña o una ventana nueva)")
2. Instala el agente mediante la línea de comandos

   Para instalar el agente mediante la línea de comandos, sigue estas instrucciones.

   [Instalación de Ops Agent mediante la línea de comandos](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(se abre en una pestaña o una ventana nueva)")

   [Instalación del agente Legacy mediante la línea de comandos](https://cloud.google.com/monitoring/agent/monitoring/installation#joint-install "(se abre en una pestaña o una ventana nueva)")
3. Instala el agente mediante la consola de Google Cloud

   Puedes instalar el agente en una o varias máquinas virtuales de Compute Engine desde el panel de control preconfigurado « VM Instances» de Monitoring.

   [Instalación de Ops Agent mediante la consola de Google Cloud](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(se abre en una pestaña o una ventana nueva)")

   [Instalación del agente Legacy mediante la consola de Google Cloud](https://cloud.google.com/monitoring/agent/monitoring/installation#gce-ui-install "(se abre en una pestaña o una ventana nueva)")

**Tema principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
