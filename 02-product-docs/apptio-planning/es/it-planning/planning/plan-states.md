---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Estados del Plan (Nuevo, Abierto, Final)"
breadcrumb:
  - "Planning"
  - "Creación y gestión de planes"
source_path: "it-planning/planning/plan-states.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Estados del Plan (Nuevo, Abierto, Final)

Apptio La planificación utiliza **los Estados del Plan** para controlar el ciclo de vida de un plan. Cada Estado regula quién puede acceder al plan, qué medidas pueden tomarse y cuándo se bloquean los datos para la elaboración de informes. Esto garantiza el control de las versiones y una gobernanza adecuada durante el proceso de planificación.

Nota: Para gestionar los estados del plan se requieren los roles de Administrador o Propietario del Proceso Presupuestario.

## Plan Estados

Los planes pasan por tres estados del ciclo de vida:

- **Nuevo**
  - Creado y gestionado únicamente por administradores.
  - Los Propietarios de Centros de Coste no pueden ver o editar planes en este estado.
- **Abrir**
  - Editable por los Propietarios de Centros de Coste y usuarios autorizados.
  - Si las notificaciones por correo electrónico están activadas, los usuarios con acceso de Edición a un Departamento reciben una notificación cuando se abre un plan.
- **Final**
  - Estado de sólo lectura.
  - Bloquea los valores del plan, conservando la versión aprobada para análisis e informes.

## Cambiar el estado de un plan

Para actualizar el estado de un plan:

1. Navegue hasta el **Plan.**
2. Seleccione el **menú de desbordamiento de tres puntos** en la esquina superior derecha.
3. Para abrir un plano, seleccione la opción **Abrir plano**.
4. Una vez abierto un plan, vuelva al menú de desbordamiento y seleccione **Finalizar plan**.
   1. Si algunos Departamentos tienen cambios sin presentar, puede hacerlo:
      - **Presentar todos los cambios y finalizar** : presenta todos los cambios pendientes y pasa el plan a Final.
      - **Finalizar sin enviar** - finaliza el plan, dejando excluidos los cambios de Departamento no enviados.
5. Los administradores siempre pueden reabrir un plan finalizado si es necesario realizar ajustes.
