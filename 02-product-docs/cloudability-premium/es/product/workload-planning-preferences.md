---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Preferencias de planificación de la carga de trabajo"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
  - "Planificación de la carga de trabajo"
source_path: "product/workload-planning-preferences.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preferencias de planificación de la carga de trabajo

Las preferencias de planificación de la carga de trabajo permiten a los equipos de FinOps definir y restringir de forma centralizada las opciones de planificación de la carga de trabajo. Cualquier actualización es opcional y no es necesaria para utilizar la Planificación de la carga de trabajo.

Por defecto, estas preferencias sólo son visibles para Workload Planning Admin, que puede modificarlas. “WorkloadPlanningPreferencesViewOnly” puede asignarse a un rol personalizado para permitir a los usuarios no administradores ver las Preferencias de planificación de la carga de trabajo sin derechos de edición.

Instrucciones 

1. Accede a Ajustes > Trabajo. Preferencias de planificación.
2. Para cada proveedor de servicios, ajuste los parámetros en función de las preferencias y políticas de su organización y haga clic en Guardar. Cualquier cambio entrará en vigor inmediatamente.

Detalles de preferencia

| Campo | Descripción |
| --- | --- |
| Permitir proveedor de servicios | Restringe la visibilidad de un proveedor de servicios específico cuando los usuarios crean una carga de trabajo. Si una carga de trabajo existente utiliza un proveedor de servicios que ha sido desactivado por los administradores, se bloqueará y los usuarios no podrán editarlo. |
| Tipo de arrendamiento preferido | En AWS, Azure y GCP, los administradores pueden decidir mostrar los «precios comprometidos» y los «precios al contado» en la planificación de cargas de trabajo de Cloudability.  "Precios comprometidos" se refiere al precio asociado a potenciales Planes de Ahorro, Reservas o Compromisos, dependiendo de la oferta del proveedor de servicios, y de la selección del usuario.  En el caso de OCI, los usuarios pueden optar por mostrar el "Precio de reserva de capacidad", que ofrece un descuento adicional del 15% en comparación con el precio a la carta y se pierde en el momento de la utilización. También pueden decidir mostrar "Precios al contado". |
| Compromiso Opciones por defecto | Estas preferencias afectarán a los «precios comprometidos» de AWS, Azure y GCP, cuando se muestren en la sección «Planificación de la carga de trabajo» de Cloudability. Los administradores tienen autoridad para desactivar la selección de opciones en la interfaz de usuario. |
| Descuento /Elevación | Para cada proveedor de servicios, los administradores pueden añadir un % de descuento o de mejora adicional. Este porcentaje se aplicará a todos los precios calculados por Cloudability Workload Planning para un proveedor determinado. No se aplica a "Otros" costes añadidos a una carga de trabajo. Cualquier cambio se aplicaría a las cargas de trabajo existentes y a las nuevas. |
| Excluir las recomendaciones en las que el tipo de instancia recomendado contenga los siguientes valores. | Con esta opción, puedes especificar los tipos de recursos que no deben aparecer en las recomendaciones de planificación de la carga de trabajo para tu organización. Esto se puede hacer mediante cualquiera de estas dos opciones:  - añadiendo la palabra clave para que las recomendaciones omitieran aquellos tipos de recursos que contuvieran dicha palabra clave. Por ejemplo: si se introduce el valor «xlarge», se excluirán todos aquellos recursos que contengan «xlarge» en su nombre. - añadiendo un asterisco (\*) junto a la palabra clave, de modo que las recomendaciones omitan aquellos tipos de recursos que empiecen por esa palabra clave. Por ejemplo: si se introduce el valor « t4\* », se excluirían todos aquellos recursos que empiecen por « t4 ». |
