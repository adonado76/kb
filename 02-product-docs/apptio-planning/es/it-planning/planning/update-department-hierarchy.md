---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Actualizar la jerarquía de departamentos"
breadcrumb: []
source_path: "it-planning/planning/update-department-hierarchy.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Actualizar la jerarquía de departamentos

## Acerca de esta tarea

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a las funciones Admin o Propietario del proceso presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones integradas dependen de otras dimensiones. Para obtener más información, consulte [Relación de atributos y dimensiones de los datos de referencia](manage-reference-data.html#dimensiondepend). Puede importar datos de referencia de dimensiones desde un archivo `.csv` o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas. Para más información, consulte [Gestionar dimensiones](manage-reference-data.html).

Las siguientes dimensiones están vinculadas a la dimensión Departamento:

- Permisos para objetos de coste
- Centro de costes
- Plan Tipo de cambio

## Procedimiento

Si tiene previsto actualizar o reorganizar la jerarquía de departamentos, deberá hacerlo:

1. Actualice los datos de referencia del Centro de costes y del Departamento. Para más información, véase [Gestionar datos de referencia de Financial Dimensions](manage-financial-dimensions.html) ).
2. Actualice los datos de referencia de los Permisos de Objetos de Coste. Para más información, véase [Datos de referencia de Gestionar permisos de objetos de coste](manage-cost-object.html) ).
3. Si se activa la compatibilidad con varias divisas, deberá actualizar los datos de referencia del tipo de divisa del plan. Para más información, véase [Datos de referencia de las Tablas de conversión multidivisa](manage-multi-currency.html) ).
4. Navegue hasta su plan y haga clic en Actualizar datos de referencia. Para más información, véase [Forzar un plan para utilizar datos de referencia actualizados](force-plan-use.html) ).
