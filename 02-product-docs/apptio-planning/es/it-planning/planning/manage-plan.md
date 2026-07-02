---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Planes de gestión"
breadcrumb:
  - "Planning"
  - "Creación y gestión de planes"
source_path: "it-planning/planning/manage-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planes de gestión

La página **Planes** proporciona un espacio de trabajo central para crear, ver y gestionar sus planes. Desde aquí, puede abrir los planes existentes, configurar las propiedades del plan y realizar acciones del ciclo de vida, como archivar o eliminar.

Nota: Para gestionar planes se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

## Acceso a los planes

1. Abra el panel de navegación izquierdo.
2. Seleccione **Planificación > Planes**.
3. Utilice las pestañas de la parte superior de la página para cambiar de una a otra:
   - **Planes disponibles** - Muestra todos los planes activos a los que pueden acceder los Propietarios de Centros de Coste.
   - **Planes archivados** - Muestra los planes archivados, accesibles sólo para usuarios con roles de Administrador o Propietario de Proceso Presupuestario.
   - **Todos los planes** - Muestra todos los planes del sistema.

## Visualización de las propiedades del plano

Seleccione el **icono del lápiz** situado junto a un plan para abrir el **panel Propiedades**, que muestra los siguientes detalles:

- **Nombre del plan** - Cambie el nombre del plan haciendo clic en el icono del lápiz.
- **Tipo** - Indica si el plan es un *Presupuesto* o una *Previsión*.
- **Estado** - Muestra la fase actual del ciclo de vida (*Nuevo, Abierto o Final* ).
- **Estado** - Muestra si el plan está *Disponible* o *Archivado*.
- **Fecha de creación** - Fecha de creación del plan.
- **Duración del plan** - Número total de años cubiertos por el plan.
- **Año de inicio del plan** - El primer año incluido en el plan.
- **Descripción del plan** : permite a los administradores o a los responsables del proceso presupuestario introducir descripciones del plan, hipótesis clave, orientaciones o anuncios. La descripción aparece en el encabezado del plan en todas las páginas, incluidas «Gastos», «Panel de control» y otras. Los usuarios pueden mostrar u ocultar la descripción en cualquier momento mediante el icono de la campana situado en el encabezado del plan.

## Archivar y restaurar planes

- **Archivar un plan** - Lo mueve de la lista Disponible a Archivado.
  - Para archivar un único plan: haga clic con el botón derecho del ratón en el plan y seleccione **Archivar**.
  - Para archivar varios planes: selecciónelos utilizando la casilla de verificación de edición masiva, haga clic con el botón derecho y seleccione **Archivar**.
- **Restaurar un plan** - Lo devuelve a la lista de disponibles.
  - Para restaurar un único plan: haga clic con el botón derecho del ratón en el plan y seleccione **Restaurar**.
  - Para restaurar varios planes: selecciónelos, haga clic con el botón derecho y seleccione **Restaurar**.

## Borrar planes

La supresión de un plan es un proceso en dos etapas:

- **Eliminación suave** : el plan se elimina inmediatamente de la interfaz de usuario cuando un administrador lo elimina. Es inaccesible para los usuarios, pero puede restaurarse en un plazo de dos días registrando un ticket de soporte.
- **Borrado** permanente: dos días después de un borrado suave, los datos del plan se eliminan de forma permanente.

Este proceso garantiza una eliminación más rápida de la IU y proporciona una ventana de seguridad de dos días para la recuperación. Cuando se eliminan varios planes, se procesan secuencialmente durante la limpieza.

- Para eliminar un único plan: haga clic con el botón derecho y seleccione **Eliminar**.
- Para eliminar varios planes: selecciónelos con la casilla de verificación de edición masiva, haga clic con el botón derecho y seleccione **Eliminar**.
