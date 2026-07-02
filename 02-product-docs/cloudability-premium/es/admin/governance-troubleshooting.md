---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Resolución de problemas"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Resolución de problemas

Antes de solucionar el problema, asegúrese de que se ha completado lo siguiente:

- Tiene asignados el rol y los permisos correctos en Cloudability.
- La aplicación IBM Cloudability GitHub está instalada en su organización GitHub.
- **Clientes HCP / TFE:** Se ha configurado Ejecutar Tarea.
- **Clientes de la comunidad Terraform:**

  - Sus flujos de trabajo de acciones GitHub están configurados para invocar acciones de gobernanza Cloudability y los secretos requeridos GitHub están configurados.
  - La salida del plan Terraform está disponible en el flujo de trabajo PR

## Detalles de la solución de problemas

| Problema | Posible causa | Resolución |
| --- | --- | --- |
| **"Acceso denegado" se muestra en Cloudability UI**  **Ausencia de funciones de gobernanza - ejemplo: imposibilidad de crear políticas** | Asignación incorrecta de funciones/permisos en Cloudability | Asegúrate de que tu usuario disponga de los permisos adecuados que se indican en [la sección «Descripción general de los permisos».](governance-getting-started.html#governance-getting-started__overview) |
| **No se puede instalar la aplicación GitHub** | - Falta de permisos de administrador en GitHub.  - Intento de instalación desde una ubicación incorrecta. | - Asegúrese de que usted es un **GitHub Org Admin** o tiene **acceso de administrador a los repositorios de destino**.  - Utilice el enlace **"Instalar aplicación GitHub "** de la **pestaña "Ajustes de gobernanza** " en Cloudability. |
| **GitHub Aplicación instalada pero no funciona** | - La aplicación no tiene acceso a los repositorios necesarios. - Faltan permisos durante la instalación. | Reinstala la aplicación y asegúrate:   - Tiene acceso de sólo lectura a los metadatos y pull requests. - Tiene acceso de lectura y escritura a los controles. - Se instala para **todos o determinados repositorios** que contengan código Terraform. |
| **Un cambio PR está bloqueado debido a una política de bloqueo fallida en Cloudability y no está siendo aprobado** |  | 1. Por favor, solicite una revisión y aprobación de un usuario con el **GovernanceFeaturePRApproval** o con el rol **Cloudability Governance PR Approver**. 2. Si el autorizador no está disponible temporalmente y es necesario desbloquear el RP urgentemente, tiene dos opciones:    - Pida a un administrador de GitHub que elimine temporalmente la regla de protección de la rama que requiere que las comprobaciones de gobernanza se realicen antes de la fusión.    - Pida a un usuario con **GovernanceFeaturePolicyFullAccess** permiso o el rol **Cloudability Governance Policy Admin** que actualice temporalmente el alcance de la política para que no se aplique al proyecto asociado con este RP específico |
| **GitHub La acción no se ejecuta (para usuarios de Terraform Community)** | - Faltan secretos o las variables de entorno son incorrectas.  - No se ha generado el plan Terraform. | Compruebe que se han configurado los siguientes secretos de GitHub :  - FD\_URL (por ejemplo, [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(se abre en una pestaña o una ventana nueva)") ) - FD\_KEY y FD\_SECRET (de un usuario con el rol " Cloudability Governance Automation User") - FD\_ENV\_ID - CLOUDABILITY\_HOST (por ejemplo, https://api.cloudability.com )   Asegúrese de que su flujo de trabajo incluye:   - Generación de planes Terraform - Pasos de la recuperación de metadatos - Paso de obtención de token de puerta delantera   Nota: Nota: Cloudability Governance espera sólo un terraform plan json de nivel superior para cada invocación. |
| **Se ha aprobado un cambio de RP que no ha superado una política cerrada de Cloudability, pero el cambio no puede aplicarse en HCP** | La tarea HCP Run tiene su propio nivel de aplicación que puede establecerse como consultivo u obligatorio. Si su aplicación se establece como Obligatorio, y una política cerrada falló, el cambio no se puede aplicar, independientemente de la aprobación. | Actualice el nivel de aplicación de la Tarea de ejecución a "Aviso" y active otra ejecución para permitir que se aplique el cambio. |
| **Los repositorios no aparecen tras instalar la aplicación « GitHub »** | El problema se debe a que la instalación se divide en dos fases mediante un flujo de trabajo de aprobació GitHub's. Cuando un administrador aprueba posteriormente la instalación pendiente, se pierde el contexto de la sesión original. Como consecuencia, nunca se notifica a Cloudability que la instalación se ha completado. | 1. Elimina la instalación actual, que está incompleta. 2. Vuelve a instalar la aplicación utilizando una cuenta de GitHub que tenga permisos de instalación inmediata para completar el proceso en un solo paso. |
