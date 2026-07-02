---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "SAP LeanIX Introducción"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "SAP LeanIX"
source_path: "cost-transparency/technology-integration/sapleanix/sap-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# SAP LeanIX Introducción

## Cómo empezar

La integración entre SAP LeanIX y IBM Apptio Costing es una integración bidireccional. La integración básica se centra en el flujo de datos desde SAP LeanIX hacia IBM Apptio Costing. La integración avanzada se basa en la integración básica, donde expone las métricas de TCO de la aplicación para su consumo por parte de SAP LeanIX.

**Dispositivos clave**

La siguiente tabla enumera las características incluidas en la integración.

|  |  |
| --- | --- |
| **Integración de base** | **Integración avanzada** |
| - Exportar información de SAP LeanIX a IBM Apptio a través de la API de integración SAP LeanIX - Programa extracciones periódicas de datos de SAP LeanIX a IBM Apptio - Exportación inmediata de los siguientes tipos de hojas informativas con campos predefinidos y todas las relaciones pertinentes: - Organización - Capacidad empresarial - Aplicación - Componente de TI - Proveedor - Proyectos - IBM Apptio Credenciales de usuario de la API - Opciones de configuración para seleccionar qué hojas de datos, relaciones y atributos se exportan - Extensión configurable de los campos que se exportan - Acceda a los paneles y los informes existentes o cree otros nuevos en IBM Apptio | Todas las funciones incluidas en la integración Base, además de las siguientes:  - Importar datos de IBM Apptio a SAP LeanIX - Datos bajo demanda extraídos de IBM Apptio a SAP LeanIX - Enlace a la página de detalles específicos de la hoja informativa en Apptio - Sincronizar hojas informativas - Campos de coste - Vista de costes por nivel de hoja de datos - Hoja informativa: coste a lo largo del tiempo (métrico) - Buscar «Filtrar por tipo de coste» - Vista de costes para informes y diagramas - Ejecución manual o programada de la exportación de datos |

## Habilitar la integración base

El núcleo de la integración entre SAP LeanIX y IBM Apptio Costing se configura en SAP LeanIX.

Toda la información relevante sobre el lado SAP LeanIX se puede encontrar aquí:

[Apptio Integración | Portal de ayuda de SAP](https://help.sap.com/docs/leanix/ea/apptio-integration "(se abre en una pestaña o una ventana nueva)")

## Instalación de componentes

Una vez que la integración básica está en marcha, la integración avanzada se vuelve posible.

Instale el siguiente componente en IBM Apptio Costing:

**Aplicaciones CT: integración** de LeanIX. Este componente instala un informe predefinido que la API SAP LeanIX utiliza para extraer métricas de TCO de aplicaciones directamente a SAP LeanIX para su uso en su solución. El informe incluido se denomina « **LeanIX** » (Informe de exportación de la aplicación) y se encuentra en la carpeta «Application».

Nota: Este componente se encuentra actualmente en fase beta. Póngase en contacto con su administrador para instalarlo desde la lista de componentes disponibles.
