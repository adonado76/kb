---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Azure Etiquetas"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/azure-resource-group-tags.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Etiquetas

Cloudability admite los siguientes tipos de etiquetas para Azure

- **Etiquetas de nivel de recurso**
  - - Forman parte de los archivos de exportación de Azure y no se requieren permisos adicionales en Cloudability para habilitarlos
      - Formato de las etiquetas - cldy:Azure:ResourceTag:<resource tag key>
- **Etiquetas de grupos de recursos**
  - Para obtener etiquetas de grupos de recursos de Azure, Cloudability necesita permisos adicionales, ya sea
    - management:Reader o Microsoft.Resources/subscriptions/resourceGroups/read en las suscripciones
      - Formato de las etiquetas - cldy:Azure:ResourceGroupTag:<resource group tag key>
- **Etiquetas de nivel de suscripción**
  - Para obtener etiquetas de nivel de suscripción de Azure, Cloudability necesita un permiso adicional
    - subscription:ReadSubscription
      - Formato de las etiquetas - cldy:Azure:SubscriptionLevelTag:<subscription tag key>

Tarea : Permitir el acceso a la información de etiquetas de grupos de recursos para apoyar las actividades de imputación de costes.

El uso de [etiquetas de grupos de recursos de Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources "(se abre en una pestaña o una ventana nueva)") se ha convertido en un mecanismo popular de asignación primaria con un gran número de usuarios de Azure. Supera el doble problema de la escasa cobertura de etiquetas y el hecho de que Azure no devuelve información sobre etiquetas para todos los tipos de recursos. Las etiquetas de grupos de recursos no aparecen de forma nativa en la información detallada de facturación y, por lo tanto, es necesario conceder acceso adicional tal y como se especifica en esta página.

Cloudability tiene un modelo de herencia de etiquetas para Azure : si un recurso individual tiene una etiqueta concreta en los datos de facturación detallados, la utilizaremos primero para rellenar nuestra plataforma de análisis. Si esa etiqueta no aparece en los datos de facturación de ese recurso, Cloudability consultará el grupo de recursos al que pertenece y extraerá de ahí la información de la etiqueta. Si la etiqueta no existe en el grupo de recursos, la consideraremos como "(no establecida)"

Para habilitar la recopilación y el procesamiento de etiquetas de grupos de recursos, sigue los pasos [que se indican aquí](azure-advanced-rightsizing.html) para configurar las credenciales de tus suscripciones.

**Tema principal:** [Conectar Microsoft Azure](../admin/azure-cm-setup-premium.html)
