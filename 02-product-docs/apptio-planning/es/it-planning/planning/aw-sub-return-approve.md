---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Presentar, revisar, aprobar y devolver los planes"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
source_path: "it-planning/planning/aw-sub-return-approve.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Presentar, revisar, aprobar y devolver los planes

Apptio La planificación proporciona un flujo de trabajo estructurado para presentar, revisar, aprobar y devolver los presupuestos departamentales. Esto garantiza que todos los datos del plan pasen por los niveles de aprobación adecuados antes de que se finalice el plan.

Independientemente del estado de la presentación, **todos los cambios siempre son visibles en el nivel de Todos los departamentos**. El estado de envío no bloquea ni impide las ediciones. Los pasos de presentación y aprobación están diseñados para garantizar la visibilidad, la coordinación y la responsabilidad, más que para restringir los cambios en los planes.

## Presentación de planes

Cuando un departamento presenta su plan:

- Se crea **una** instantánea de la versión enviada (solo lectura).
- Si las notificaciones por correo electrónico están habilitadas, se notifica a los aprobadores correspondientes según el flujo de trabajo de aprobación en uso.

Puede enviar planes desde la página **Gastos** o la página **Estado**.

**Enviar desde la página de gastos**

1. En el menú **Plan**, seleccione un plan.
2. Navega a **Plan** → **Gastos**.
3. En el menú desplegable **Departamento**, seleccione un departamento.
4. Abre el **menú de puntos suspensivos (⋮)** y selecciona **Enviar**.
5. *(Opcional)* Introduzca un nombre para la instantánea.
6. Pulse **Enviar**.

**Enviar desde la página de estado**

1. Navega a **Plan** → **Estado**.
2. Para enviar varios departamentos, seleccione las casillas de verificación de los departamentos y, a continuación**, Acciones** → **Enviar seleccionados.**
3. Para enviar un departamento, seleccione **Enviar** en la columna **Acciones**.

**¿Qué ocurre después del envío?**

- **Aprobaciones jerárquicas:** se notifica *al propietario del departamento superior* del siguiente nivel.
- **Aprobaciones multinivel:** primero se notifica a los aprobadores del nivel 1, luego a los del nivel 2, y así sucesivamente.

**Notas para aprobaciones jerárquicas:**

- Envío de un **departamento grupal** :
  - Aprueba automáticamente todos los departamentos secundarios
  - Crea instantáneas para todos los hijos
  - Los departamentos infantiles ya aprobados no sufren cambios
- Un departamento de grupo pasa a estar **«En curso»** cuando al menos un niño envía un plan.
- Si un plan es **devuelto**, la versión enviada se marca como «*Devuelta* ». Cualquier edición crea una **nueva versión**.

## Aprobación y devolución de planes

Los usuarios con permisos de aprobación pueden aprobar o devolver planes en cualquier momento. Si varios usuarios comparten el mismo nivel de aprobación, solo se requiere una aprobación para seguir adelante.

En las aprobaciones jerárquicas, los usuarios con nivel de edición **de propietario** actúan como aprobadores. Cuando un propietario de nivel superior aprueba un plan, todas las aprobaciones de nivel inferior se completan automáticamente.

**Revisar planes desde la página de gastos**

1. Navega a **Plan** → **Gastos**.
2. Seleccione un departamento.
3. *(Opcional)* Habilite **la vista Actualizada** para mostrar solo los elementos modificados.
4. Abre el **menú de puntos suspensivos (⋮)** → selecciona **Aprobar** o **Devolver**.
5. Al devolver un plan, puede añadir un comentario.

**Revisar planes desde la página de estado**

1. Vaya a **Planificación** → **Estado**.
2. *(Opcional)* Activar/desactivar **Incluir objetos de coste de solo lectura** (requiere *Aplicar permisos de visualización* ).
3. Aprobar/devolver utilizando:
   1. **Columna Acciones** (Aprobar, Devolver, Comentario) o
   2. **Acciones masivas** seleccionando las casillas de verificación del departamento y, a continuación**, Acciones** → **Aprobar seleccionados** o **Devolver seleccionados.**

Si las notificaciones por correo electrónico están habilitadas, la aprobación de un plan activa el envío de un correo electrónico al aprobador del siguiente nivel.

En las aprobaciones jerárquicas, al devolver un plan se envía un correo electrónico al propietario del nivel anterior, y el plan debe devolverse paso a paso hacia abajo en la jerarquía.

En las aprobaciones multinivel, al devolver un plan se notifica a todos los usuarios con acceso de edición al departamento final, y el plan se devuelve directamente al propietario original del departamento, sin pasar por los niveles de aprobación intermedios.

## Aprobaciones jerárquicas: acciones y comportamiento de aprobación

|  |  |  |
| --- | --- | --- |
| **Acción** | **Departamento de Hojas** | **Departamento de Grupo** |
| **Enviar** | Actualiza el estado del departamento a **«Enviado»** y crea una instantánea de la versión enviada. Los usuarios con nivel de edición «Propietario» para el departamento enviado reciben una notificación por correo electrónico para revisar y aprobar el plan. | Actualiza el estado del departamento del grupo a **«Enviado»**, aprueba automáticamente todos los departamentos secundarios y crea instantáneas de todos los departamentos finales. Los niños ya aprobados no se ven afectados. Los usuarios con nivel de edición de "Propietario" para el Departamento de grupo enviado reciben una notificación por correo electrónico para revisar y aprobar el plan. |
| **Aprobar** | Actualiza el estado del departamento a **«Aprobado».** El propietario del siguiente nivel en la jerarquía de departamentos recibe una notificación por correo electrónico para revisar y aprobar el plan. | Actualiza el estado del departamento del grupo y cualquier departamento secundario a «**Aprobado** ». El propietario del siguiente nivel en la jerarquía de departamentos recibe una notificación por correo electrónico para revisar y aprobar el plan. |
| **Volver** | Actualiza el estado del departamento a «**Devuelto** ». Los usuarios con nivel de edición de "Propietario" para el Departamento devuelto reciben una notificación por correo electrónico para revisar y volver a enviar el plan. | Actualiza el estado del Departamento de grupo como **Devuelto**. Los Departamentos Infantiles permanecen inalterados a menos que sus propietarios los devuelvan explícitamente. Al devolver un plan, se envía un correo electrónico al propietario del nivel anterior, y el plan debe devolverse paso a paso a lo largo de la jerarquía. |

## Aprobaciones multinivel: acciones y comportamiento de aprobación

|  |  |
| --- | --- |
| **Acción** | **Comportamiento** |
| **Enviar** | Actualiza el estado del departamento a **«Enviado»** y crea una instantánea de la versión enviada. Los aprobadores de nivel 1 reciben una notificación por correo electrónico en la que se les pide que revisen y aprueben el plan presentado. |
| **Aprobar** | Actualiza el estado del departamento a **L[n] Aprobado**. Los aprobadores del nivel [ n+1 ] reciben una notificación por correo electrónico para revisar y aprobar el plan. Una vez completados todos los niveles de aprobación, el estado del Departamento se establece en **Aprobado.** |
| **Volver** | Actualiza el estado del departamento a «**Devuelto** ». Los usuarios con acceso de edición reciben una notificación por correo electrónico para que revisen y vuelvan a enviar el plan. |

## Desbloquear un plan

Los planos enviados, aprobados o devueltos son de solo lectura. Los usuarios con nivel **Edit & Submit** (Editar y enviar) o **Owner** edit (Edición de propietario) pueden desbloquear un plan para continuar editando. Al desbloquearlo, el estado del departamento se restablece a **«En curso»** y el plan vuelve a ser editable.

1. Navega a **Plan** → **Gastos**
2. Seleccione un departamento de hoja y, a continuación, haga clic **en Desbloquear este objeto de coste** en el mensaje del banner, o seleccione el menú Versiones del plan y haga clic en **Desbloquear**.
3. Como alternativa, en **Plan** → **Estado**, seleccione la casilla Departamento y, a continuación, **Acciones** → **Desbloquear seleccionados**.

## Finalización de los planes

Cuando todos los departamentos estén aprobados, los administradores o los responsables del proceso presupuestario pueden **finalizar el plan** desde la página Gastos para bloquearlo.

1. Navega a **Plan** → **Gastos**.
2. Seleccione **Todos los departamentos** en el menú desplegable Departamento.
3. Abre el **menú de puntos suspensivos (⋮)** → selecciona **Finalizar plan**.
4. Seleccione **Finalizar**.

Si hay cambios sin enviar, se le notificará. Estos cambios se incluirán en el plan definitivo, pero no tendrán el estado «**Aprobado** ». Puede volver a abrir un plan en cualquier momento para realizar más cambios.
