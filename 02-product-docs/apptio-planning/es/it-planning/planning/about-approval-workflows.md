---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Flujos de trabajo de aprobación"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
source_path: "it-planning/planning/about-approval-workflows.html"
images:
  - "resources/images/it_planning_images/hier-approval.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Flujos de trabajo de aprobación

Los flujos de trabajo de aprobación en Apptio Planning controlan cómo los planes presentados pasan por las etapas de revisión y aprobación, garantizando que los planes se envían a las partes interesadas adecuadas para su aprobación. Estos flujos de trabajo ofrecen flexibilidad para adaptarse a la estructura y el proceso de gobernanza de su organización.

Apptio La planificación admite dos tipos de flujos de trabajo de aprobación:

- **Aprobaciones jerárquicas** : dirige los planes a través de la jerarquía de Departamentos para su revisión y aprobación.
- **Aprobaciones de varios niveles** : define una cadena de aprobación secuencial personalizada (por ejemplo, L1 → L2 → L3 ) para cada Departamento, independientemente de la jerarquía organizativa.

Los administradores pueden elegir el tipo de flujo de trabajo para un ciclo de planificación en función de la estructura y el proceso de toma de decisiones de la organización.

## Autorizaciones jerárquicas

Las aprobaciones jerárquicas dirigen los planes presentados de acuerdo con la jerarquía del Departamento, lo que requiere que las aprobaciones avancen hacia arriba a través de cada nivel hasta que se finaliza el plan general. Este enfoque es el más adecuado cuando las aprobaciones deben seguir la estructura de informes de la organización.

**Características clave:**

- **Enrutamiento basado en la jerarquía de departamentos:** Las aprobaciones fluyen desde los Departamentos hoja hacia arriba hasta sus Departamentos padre.
- **Estado del plan:** El estado de un plan pasa de **En curso** a **Presentado** y, a continuación, a **Aprobado** o **Devuelto**.
- **Varios propietarios por nivel:** Puede asignar varios Propietarios a nivel de Departamento o Grupo, con una sola aprobación necesaria para que el plan avance.
- **Presentación de departamentos de grupo:** Un departamento de grupo puede enviar todos sus departamentos secundarios juntos para su aprobación, y el envío de un departamento de grupo aprueba automáticamente todos los departamentos secundarios que contiene.
- **Comportamiento de rechazo:** Rechazar un plan lo devuelve un nivel en la jerarquía. El propietario de ese nivel tendría que volver a rechazarla para que siguiera avanzando hacia el Departamento de Hojas para su revisión.
- **Soporte para omitir nodos:** Puede configurar los nodos de jerarquía para que se omitan dejando al Propietario sin asignar en ese nivel, haciendo que las aprobaciones pasen al Propietario del siguiente nivel superior.

**Ejemplo**

En el ejemplo siguiente, los Grupos D y E pueden configurarse como nodos "skip". Los planes de los Departamentos A, B, C, D y E pasarán por alto los niveles intermedios y serán aprobados directamente por el propietario del Grupo B.

![aprobación jerárquica](../../../../../03-media/apptio-planning/resources/images/it_planning_images/hier-approval.png)

**Autorizaciones jerárquicas - Permisos de nivel de edición**

Las aprobaciones jerárquicas utilizan **el nivel de edición** para controlar quién puede ver, editar, enviar y aprobar dentro de un flujo de trabajo de aprobación. Puede configurar el **Nivel de Edición** de un usuario en **Permisos de Objetos de Coste**. Consulte [los datos de referencia de Gestionar permisos de objetos de coste](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(se abre en una pestaña o una ventana nueva)") para obtener más información.

Nota: Active **Enviar notificaciones por correo electrónico para eventos del proceso de planificación** en el Perfil de la empresa para activar alertas por correo electrónico cuando se abran, envíen, aprueben o devuelvan planes. Consulte [Notificaciones por correo electrónico](manage-email-notifications.html) para obtener más información.

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Editar nivel** | **Vista** | **Editar** | **Enviar/Desbloquear planes** | **Aprobar** | **Volver** | **Alertas de correo electrónico** |
| Propietario (Owner) | Sí | Sí | Sí | Sí | Sí | Sí |
| Editar y enviar | Sí | Sí | Sí | Nee | Nee | Sí |
| Editar | Sí | Sí | Nee | Nee | Nee | Sí |
| Solo visualización | Sí | Nee | Nee | Nee | Nee | Nee |

Nota: La aprobación del presupuesto es jerárquica. Los usuarios con permiso **de «Propietario»** a nivel de un departamento de nivel inferior no pueden aprobar ni devolver los presupuestos de dicho departamento; estas acciones deben ser realizadas por un **«Propietario»** del departamento superior.

## Homologaciones multinivel

Las aprobaciones multinivel permiten a los administradores configurar una cadena de aprobación secuencial personalizada (por ejemplo, L1 → L2 → L3 ) para cada Departamento, independientemente de la jerarquía organizativa. Esto es útil cuando:

- Las aprobaciones deben proceder de funciones específicas o de aprobadores designados en todos los departamentos.
- El proceso de aprobación no se ajusta estrictamente a la estructura organizativa.

**Características clave:**

- **Aprobaciones secuenciales:** Configure hasta 10 niveles de aprobación por Departamento, con aprobaciones que progresan en orden del Nivel 1 al Nivel 2, Nivel 3, y así sucesivamente.
- **Estado del plan:** El estado de un plan pasa de En curso a Presentado, luego progresa a través de **L1 Aprobado**, **L2 Aprobado**, y así sucesivamente, hasta que se completan todas las aprobaciones requeridas y el aprobador final cambia el estado a **Aprobado**.
- **Múltiples Propietarios por nivel:** Puede asignar múltiples Aprobadores por nivel, siendo necesaria sólo una aprobación para que el plan avance.
- **Comportamiento de rechazo:** Si un departamento es rechazado en cualquier nivel, el plan vuelve al principio de la cadena de aprobación, lo que requiere que el propietario del departamento vuelva a enviarlo desde el nivel 1.
- **Planificación asíncrona:** Los departamentos pueden presentar y avanzar de forma independiente a través de la cadena de aprobación.

**Aprobaciones multinivel - Permisos de edición y aprobación**

En los flujos de trabajo multinivel, **el nivel de edición** y **el nivel de aprobación** son permisos independientes, lo que permite a los administradores definir los derechos de edición independientemente de la autoridad de aprobación.

- **Nivel de edición:** Controla si un usuario puede ver, editar o enviar datos del plan.
- **Nivel de aprobación:** Determina si el usuario forma parte de la cadena de aprobación ( L1–L10 ). Un usuario puede tener acceso de edición sin ser un aprobador, o ser un aprobador sin derechos de edición.

Puede configurar el **Nivel de Edición** y el **Nivel de Aprobación** de un usuario en **Permisos de Objetos de Coste**. Para obtener más información, consulte [los datos de referencia de «Gestionar permisos de objetos de coste](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(se abre en una pestaña o una ventana nueva)") ».

Nota: Active **Enviar notificaciones por correo electrónico para eventos del proceso de planificación** en el Perfil de la empresa para activar alertas por correo electrónico cuando se abran, envíen, aprueben o devuelvan planes. Consulte [Notificaciones por correo electrónico](manage-email-notifications.html) para obtener más información.

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Editar nivel** | **Vista** | **Editar** | **Enviar/Desbloquear planes** | **Alertas de correo electrónico** |
| Propietario (Owner) | Sí | Sí | Sí | Sí |
| Editar y enviar | Sí | Sí | Sí | Sí |
| Editar | Sí | Sí | Nee | Sí |
| Solo visualización | Sí | Nee | Nee | Nee |

|  |  |  |  |
| --- | --- | --- | --- |
| **Nivel de aprobación** | **Aprobar** | **Volver** | **Alertas de correo electrónico** |
| Nivel 1- Nivel 10 | Sí | Sí | Sí |
| Ninguna | Nee | Nee | Nee |

## Comparación de flujos de trabajo

|  |  |  |
| --- | --- | --- |
|  | **Autorizaciones jerárquicas** | **Homologaciones multinivel** |
| **Vía de aprobación** | Sigue la jerarquía de Departamentos, avanzando nivel por nivel a través de los Departamentos de origen. | Definido a medida por Departamento, con aprobaciones secuenciales que fluyen en orden ( L1 → L2 → L3, etc.). |
| **Niveles de aprobación** | Se pueden asignar varios propietarios por departamento o grupo de departamentos, y sólo se requiere una aprobación para avanzar. | Admite hasta 10 niveles de aprobación por Departamento. Se pueden asignar varios aprobadores por nivel, y sólo se requiere uno para aprobar. |
| **Presentación en grupo** | Admite la presentación de Departamentos de Grupo, en los que la presentación de un Grupo automáticamente presenta y aprueba todos los Departamentos hijos juntos. | No aplicable. |
| **Flujo de planificación** | Requiere planificación y presentación sincrónicas (los Departamentos hijos deben presentar antes de que el Grupo padre pueda avanzar). | Admite la planificación y revisión asíncronas. Los departamentos pueden presentar y avanzar de forma independiente a través de la cadena de aprobación. |
| **Comportamiento de rechazo** | Si se rechaza, el plan retrocede un nivel en la jerarquía. El Propietario de cada nivel debe seguir rechazando para empujarlo hacia el Departamento de hojas. | Rechazar un departamento lo devuelve al principio del flujo de trabajo, lo que requiere que el departamento vuelva a enviarlo al nivel 1. |
| **Saltar nodos** | Si se deja al propietario sin asignar en un nivel, las aprobaciones se transfieren al siguiente propietario de nivel superior. | No aplicable. |
| **Permisos de usuario** | Permiso de nivel de edición:  - **Propietario:** puede editar, presentar y aprobar o devolver planos. Recibe notificaciones por correo electrónico cuando se aprueban o devuelven los planes. - **Editar y enviar** - Puede editar y enviar planos. - **Editar** - Puede editar los planes pero no puede enviarlos. - **Sólo ver** - Puede ver los planes pero no puede editarlos ni enviarlos. | Permisos de nivel de edición:  - **Propietario:** puede editar y presentar planos. Recibe notificaciones por correo electrónico cuando se aprueban o devuelven los planes. - **Editar y enviar** - Puede editar y enviar planos. - **Editar** - Puede editar los planes pero no puede enviarlos. - **Sólo ver** - Puede ver los planes pero no puede editarlos ni enviarlos.  Permiso de nivel de aprobación:  - Nivel de aprobación: Establezca un nivel de aprobación (1-10) para definir la posición del usuario en el flujo de trabajo de aprobación. |

## Pasos de configuración

1. **Navegue hasta:** Perfil de empresa > **Flujos de trabajo de aprobación**.
2. **Seleccione Tipo de flujo de trabajo:** Seleccione **Aprobación jerárquica** o **Aprobación multinivel**.
3. **Opción de envío de grupo (sólo jerárquico):** Puede desactivar la presentación de grupo seleccionando **Desactivar presentación de plan de objetos de coste de grupo**. Al seleccionar esta opción se elimina la posibilidad de que los Departamentos de Grupo realicen envíos a nivel de grupo. Si necesita un control más detallado de los envíos y las aprobaciones, considere la posibilidad de utilizar las aprobaciones multinivel.
4. **Notificaciones por correo electrónico:** Para notificar a los usuarios los eventos clave durante el proceso de planificación, seleccione **Enviar notificaciones por correo electrónico para eventos del proceso de planificación**.
5. **Guarde y salga** del perfil de empresa.
6. **Asignar aprobadores:** Vaya a Configuración > **Permisos de objetos de coste** y asigne usuarios en función del tipo de flujo de trabajo elegido:
   - **Aprobación jerárquica:** Asigne aprobadores a cada Departamento o Grupo de Departamentos según su estructura organizativa. Establezca Nivel de edición = Propietario para los usuarios que pueden aprobar o rechazar envíos.
   - **Aprobación multinivel:** Asigne a los usuarios un Nivel de Edición para definir su capacidad para ver, editar o enviar planes, y un Nivel de Aprobación ( L1–L10 ) para incluirlos en la cadena de aprobación.
