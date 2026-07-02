---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Herramienta del Observatorio de Agentes"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/agent-observatory-tool.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Herramienta del Observatorio de Agentes

## Visión general

La Herramienta de Observabilidad de Agentes proporciona una supervisión en tiempo real de los agentes de las métricas de Cloudability en un formato tabular en todos sus clústeres, lo que le permite realizar un seguimiento del estado de los agentes, detectar problemas y garantizar unos informes de costes precisos.

Nota:

Actualmente los datos están disponibles **sólo para los últimos 7 días**.

Para acceder a la Herramienta de Observabilidad del Agente:

Vaya a **Insights** > **Contenedores** > **Monitor**.

La Herramienta de Observabilidad de Agentes muestra en una tabla la lista de todos los clusters monitorizados para los agentes de métricas instalados.

| Columna | Descripción |
| --- | --- |
| Nombre de clúster | Nombre de su clúster. |
| Estado del agente | Muestra el estado como **Activo/** **Inactivo** para el agente de métricas. |
| Versión para agentes | La versión del agente instalado. |
| Versión de clúster | La versión de Kubernetes / Openshift que se ejecuta en el clúster. |
| Última visualización | Marca de tiempo de la última ingestión de datos realizada con éxito. |
| Tipo de clúster | Identifica el tipo de agrupación (por ejemplo, EKS, ROSA ). |
| Proveedor | El proveedor de servicios en la nube para el clúster (por ejemplo, AWS ). |

## Acciones recomendadas

- Compruebe si hay agentes inactivos: Filtre por estado **Inactivo** para encontrar clústeres que no reporten datos, investigue conexiones, versión y problemas de configuración. Un clúster se marca como **Inactivo** si el valor de **Visto por última vez** es superior a 12 horas.
- Supervise las versiones del agente: Asegúrese de que todos los clústeres ejecutan la última versión del agente para comprobar la compatibilidad, las nuevas funciones y las mejoras de seguridad.
- Revise los Nombres de Cluster duplicados: Si ve un icono de advertencia, actualice los nombres de clúster únicos para obtener informes precisos.
- Controle la actualidad de los datos: Utiliza la columna "**Visto por última vez** " para asegurarte de que los datos son recientes. Los agentes que no se presenten durante más de 24 horas deben ser revisados.

**Tema principal:** [Imputación de costes de contenedores](../product/k8s-cost-allocation.html)
